---
title: Utöka datatabeller för lagerbehållning
description: Det här avsnittet innehåller ett exempel som visar hur du lägger till utökade fält i vyerna INVENTORSITEONHANDENTITY och INVENTWAREHOUSEONHANDENTITY så att funktionerna i de dataentiteter för lagerbehållning kan fungera med tilläggen.
author: sherry-zheng
ms.date: 07/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-07-27
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 7863f37e66727e2e80ea8c8b013ee49930e7c684
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5829918"
---
# <a name="extend-inventory-on-hand-data-entities"></a><span data-ttu-id="f01de-103">Utöka datatabeller för lagerbehållning</span><span class="sxs-lookup"><span data-stu-id="f01de-103">Extend inventory on-hand data entities</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f01de-104">Microsoft Dynamics 365 Supply Chain Management tillhandahåller funktioner för [Utbyggbarhet](../../fin-ops-core/dev-itpro/extensibility/extensibility-home-page.md) som gör att du kan [lägga till fält i register via tillägg](../../fin-ops-core/dev-itpro/extensibility/add-field-extension.md).</span><span class="sxs-lookup"><span data-stu-id="f01de-104">Microsoft Dynamics 365 Supply Chain Management provides [extensibility](../../fin-ops-core/dev-itpro/extensibility/extensibility-home-page.md) features that let you [add fields to tables through extension](../../fin-ops-core/dev-itpro/extensibility/add-field-extension.md).</span></span> <span data-ttu-id="f01de-105">Det här avsnittet innehåller ett exempel som visar hur du lägger till utökade fält i vyerna `INVENTORSITEONHANDENTITY` och `INVENTWAREHOUSEONHANDENTITY` så att funktionerna i de dataentiteter för lagerbehållning kan fungera med tilläggen.</span><span class="sxs-lookup"><span data-stu-id="f01de-105">This topic provides an example that shows how to add extended fields to the `INVENTORSITEONHANDENTITY` and `INVENTWAREHOUSEONHANDENTITY` views, so that the capabilities of the inventory on-hand data entities can work with the extensions.</span></span> <span data-ttu-id="f01de-106">Mer information om dataentiteter finns i [Datahantering – en översikt](../../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md).</span><span class="sxs-lookup"><span data-stu-id="f01de-106">For more information about data entities, see [Data management overview](../../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md).</span></span>

> [!NOTE]
> <span data-ttu-id="f01de-107">Här följer en lista över några av de tillgängliga enheterna för lagerbehållning:</span><span class="sxs-lookup"><span data-stu-id="f01de-107">Here is a list of some of the inventory on-hand data entities:</span></span>
>
> - <span data-ttu-id="f01de-108">Lagerbehållningen efter plats</span><span class="sxs-lookup"><span data-stu-id="f01de-108">Inventory on-hand by site</span></span>
> - <span data-ttu-id="f01de-109">Lagerbehållningen efter plats V2</span><span class="sxs-lookup"><span data-stu-id="f01de-109">Inventory on-hand by site V2</span></span>
> - <span data-ttu-id="f01de-110">Lagerbehållning enligt lagerställe</span><span class="sxs-lookup"><span data-stu-id="f01de-110">Inventory on-hand by warehouse</span></span>
> - <span data-ttu-id="f01de-111">Lagerbehållning enligt lagerställe v2</span><span class="sxs-lookup"><span data-stu-id="f01de-111">Inventory on-hand by warehouse v2</span></span>

<span data-ttu-id="f01de-112">När du har lagt till fält i register som används i den här `inventSiteOnHandView` vyn måste du synkronisera motorn så att tilläggen känns igen korrekt.</span><span class="sxs-lookup"><span data-stu-id="f01de-112">After you add fields to tables that are used by the `inventSiteOnHandView` view, you must sync the engine so that the extensions are correctly recognized.</span></span>

1. <span data-ttu-id="f01de-113">Utöka `InventSiteOnHandView` vyn genom att lägga till tilläggsfältet.</span><span class="sxs-lookup"><span data-stu-id="f01de-113">Extend the `InventSiteOnHandView` view by adding the extension field.</span></span>
1. <span data-ttu-id="f01de-114">Utöka `InventSiteOnHandAggregatedView` vyn med tilläggsfälten.</span><span class="sxs-lookup"><span data-stu-id="f01de-114">Extend the `InventSiteOnHandAggregatedView` view with the extension fields.</span></span>
1. <span data-ttu-id="f01de-115">Utöka `InventSiteOnHandAggregatedViewBuilder` viewBuilder-klassen genom att ändra `getExtensionFields()`-metoden.</span><span class="sxs-lookup"><span data-stu-id="f01de-115">Extend the `InventSiteOnHandAggregatedViewBuilder` viewBuilder class by modifying the `getExtensionFields()` method.</span></span> <span data-ttu-id="f01de-116">På det här sättet mappar du gamla visningsfält till nya viewBuilder när synkroniseringen körs.</span><span class="sxs-lookup"><span data-stu-id="f01de-116">In this way, you map old view fields to new view fields when viewBuilder synchronization is run.</span></span>

<span data-ttu-id="f01de-117">Du har till exempel lagt till följande fyra fält i `InventTable`-registret via tillägg:</span><span class="sxs-lookup"><span data-stu-id="f01de-117">For example, you've added the following four fields to the `InventTable` table through extension:</span></span>

- <span data-ttu-id="f01de-118">Anpassat fält 1</span><span class="sxs-lookup"><span data-stu-id="f01de-118">Custom field 1</span></span>
- <span data-ttu-id="f01de-119">Anpassat fält 2</span><span class="sxs-lookup"><span data-stu-id="f01de-119">Custom field 2</span></span>
- <span data-ttu-id="f01de-120">Anpassat fält 3</span><span class="sxs-lookup"><span data-stu-id="f01de-120">Custom field 3</span></span>
- <span data-ttu-id="f01de-121">Anpassat fält 4</span><span class="sxs-lookup"><span data-stu-id="f01de-121">Custom field 4</span></span>

<span data-ttu-id="f01de-122">I så fall måste du ändra `getExtensionFields()`-metoden på följande sätt.</span><span class="sxs-lookup"><span data-stu-id="f01de-122">In the case, you must modify the `getExtensionFields()` method in the following way.</span></span>

```xpp
[ExtensionOf(classStr(InventSiteOnHandAggregatedViewBuilder))]
public final class InventOnHandAggregatedViewBuilder\_Extension
{
    protected Map getExtensionFields()
    {
        next getExtensionFields();
        Map extensionFields = new Map(Types::Int64, Types::Int64);
        extensionFields.insert(fieldNum(InventSiteOnHandView, Custom field 1), fieldNum(InventSiteOnHandAggregatedView, Custom field 1));
        extensionFields.insert(fieldNum(InventSiteOnHandView, Custom field 2), fieldNum(InventSiteOnHandAggregatedView, Custom field 2));
        extensionFields.insert(fieldNum(InventSiteOnHandView, Custom field 3), fieldNum(InventSiteOnHandAggregatedView, Custom field 3));
        extensionFields.insert(fieldNum(InventSiteOnHandView, Custom field 4), fieldNum(InventSiteOnHandAggregatedView, Custom field 4));
        return extensionFields;
    }
}
```

<span data-ttu-id="f01de-123">När du har slutfört de här stegen kan du utöka lagerbehållningen per webbplats och lagerbehållning med dataentiteter för lagerställen genom att lägga till de nya fälten.</span><span class="sxs-lookup"><span data-stu-id="f01de-123">After you complete these steps, you can extend the inventory on-hand by site and inventory on-hand by warehouse data entities by adding the new fields.</span></span> <span data-ttu-id="f01de-124">På så sätt säkerställer du att de utökade fälten känns igen och tas med vid datamigrering som använder dessa dataentiteter.</span><span class="sxs-lookup"><span data-stu-id="f01de-124">In this way, you ensure that the extended fields are recognized and included during data migration that uses those data entities.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]