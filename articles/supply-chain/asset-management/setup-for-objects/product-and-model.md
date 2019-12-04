---
title: Tillgångstillverkare och-modeller
description: Det här avsnittet förklarar hur du ställer in tillgångstillverkare och relaterade modeller i Tillgångshantering.
author: josaw1
manager: AnnBe
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b77605070387871335c480e25cbe23af1155d6e8
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/18/2019
ms.locfileid: "2812178"
---
# <a name="asset-manufacturers-and-models"></a><span data-ttu-id="2398f-103">Tillgångstillverkare och-modeller</span><span class="sxs-lookup"><span data-stu-id="2398f-103">Asset manufacturers and models</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="2398f-104">Det här avsnittet förklarar hur du ställer in tillgångstillverkare och relaterade modeller i Tillgångshantering.</span><span class="sxs-lookup"><span data-stu-id="2398f-104">This topic explains how to set up asset manufacturers and related models in Asset Management.</span></span> <span data-ttu-id="2398f-105">Modeller kan relateras till tillgångstyper.</span><span class="sxs-lookup"><span data-stu-id="2398f-105">Models can be related to asset types.</span></span>

## <a name="set-up-product-model-relations"></a><span data-ttu-id="2398f-106">Ställ in produktmodellrelationer</span><span class="sxs-lookup"><span data-stu-id="2398f-106">Set up product-model relations</span></span>

1. <span data-ttu-id="2398f-107">Välj **Tillgångshantering** \> **Inställning** \> **Tillgångar** \> **Tillverkare och modell**.</span><span class="sxs-lookup"><span data-stu-id="2398f-107">Select **Asset management** \> **Setup** \> **Assets** \> **Manufacturer and model**.</span></span>
2. <span data-ttu-id="2398f-108">Skapa en ny produkt genom att välja **Nytt**.</span><span class="sxs-lookup"><span data-stu-id="2398f-108">Select **New** to create a new product.</span></span>
3. <span data-ttu-id="2398f-109">I fältet **tillverkare**,ange ett namn för tillgångstillverkaren.</span><span class="sxs-lookup"><span data-stu-id="2398f-109">In the **Manufacturer** field, enter a name for the asset manufacturer.</span></span>
4. <span data-ttu-id="2398f-110">Ange en beskrivning i fältet **beskrivning**.</span><span class="sxs-lookup"><span data-stu-id="2398f-110">In the **Description** field, enter a description.</span></span>
5. <span data-ttu-id="2398f-111">På snabbfliken **Modeller** väljer du **Lägg till** för att skapa en tillgångsmodell som ska relateras till tillgångstillverkaren.</span><span class="sxs-lookup"><span data-stu-id="2398f-111">On the **Models** FastTab, select **Add** to create an asset model that should be related to the asset manufacturer.</span></span>
6. <span data-ttu-id="2398f-112">I fältet **Modell**,ange ett namn för tillgångsmodellen.</span><span class="sxs-lookup"><span data-stu-id="2398f-112">In the **Model** field, enter a name for the asset model.</span></span>
7. <span data-ttu-id="2398f-113">Ange en beskrivning i fältet **beskrivning**.</span><span class="sxs-lookup"><span data-stu-id="2398f-113">In the **Description** field, enter a description.</span></span>
8. <span data-ttu-id="2398f-114">I fältet **tillgångstyp** väljer du den tillgångstyp som tillverkarmodellen ska relateras till.</span><span class="sxs-lookup"><span data-stu-id="2398f-114">In the **Asset type** field, select the asset type that the manufacturer model should be related to.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2398f-115">Du kan också ställa in relationer för tillgångstyper, tillverkare och modeller i sökningen **tillgångstyper**.</span><span class="sxs-lookup"><span data-stu-id="2398f-115">You can also set up relations for asset types, manufacturers, and models in the **Asset types** lookup.</span></span> <span data-ttu-id="2398f-116">Mer information finns i [Tillgångstyper](../setup-for-objects/object-types.md).</span><span class="sxs-lookup"><span data-stu-id="2398f-116">For more information, see [Asset types](../setup-for-objects/object-types.md).</span></span>

    <span data-ttu-id="2398f-117">På snabbfliken **Detaljer** visar fältet **Modeller** antalet tillgångsmodeller som har ställts in på den valda tillgångstillverkaren.</span><span class="sxs-lookup"><span data-stu-id="2398f-117">In the **Details** FastTab, the **Models** field shows the number of asset models that are set up on the selected asset manufacturer.</span></span> <span data-ttu-id="2398f-118">Fältet **tillgångar** visar antalet tillgångar som använder den valda tillverkaren.</span><span class="sxs-lookup"><span data-stu-id="2398f-118">The **Assets** field shows the number of assets that are using the selected manufacturer.</span></span>
    
    <span data-ttu-id="2398f-119">Fältet **tillgångar** visar antalet objekt som använder den valda tillverkarmodellen.</span><span class="sxs-lookup"><span data-stu-id="2398f-119">The **Assets** field shows the number of objects that are using the manufacturer model.</span></span>

> [!NOTE]
> <span data-ttu-id="2398f-120">En tillgångstyp kan inte ha någon modellrelation för tillgångstillverkare, den kan relateras till en modell för tillgångstillverkare, eller så kan den relateras till flera tillgångstillverkares modeller.</span><span class="sxs-lookup"><span data-stu-id="2398f-120">An asset type can have no asset manufacturer model relations, it can be related to one asset manufacturer model, or it can be related multiple asset manufacturer models.</span></span> <span data-ttu-id="2398f-121">Om en tillgångstyp är relaterad till minst en tillverkarmodell, kan endast de kombinationer som har ställts in i sökningen **Tillverkarmodell** väljas på dessa tillgångshanteringssidor där en kombination av en tillgångstyp, tillverkare och modell kan ställas in.</span><span class="sxs-lookup"><span data-stu-id="2398f-121">If an asset type is related to at least one manufacturer model, only the combinations that are set up in the **Manufacturer model** lookup can be selected on those Asset Management pages where a combination of an asset type, manufacturer, and model can be set up.</span></span> <span data-ttu-id="2398f-122">Dessa sidor innehåller **Alla tillgångar**, **servicenivåer för tillgång**, **standarder för jobbtyp** och **budgetrader för underhåll**.</span><span class="sxs-lookup"><span data-stu-id="2398f-122">These pages include **All assets**, **Asset service levels**, **Job type defaults**, and **Maintenance budget lines**.</span></span> <span data-ttu-id="2398f-123">Om vissa tillgångstyper inte är relaterade till någon tillverkarmodell visas endast de tillgångstyper och tillverkarmodeller som också har någon relation till tillgångstyper på sidorna.</span><span class="sxs-lookup"><span data-stu-id="2398f-123">If some asset types aren't related to any manufacturer model, only those asset types, and manufacturer models that also have no relation to asset types, are shown on the pages.</span></span>

## <a name="select-a-manufacturer-and-model-on-an-object"></a><span data-ttu-id="2398f-124">Välja en tillverkare och modell på ett objekt</span><span class="sxs-lookup"><span data-stu-id="2398f-124">Select a manufacturer and model on an object</span></span>

1. <span data-ttu-id="2398f-125">Välj **Tillgångshantering** \> **Allmänt** \> **Tillgångar** \> **Alla tillgångar**</span><span class="sxs-lookup"><span data-stu-id="2398f-125">Select **Asset management** \> **Common** \> **Assets** \> **All assets**.</span></span>
2. <span data-ttu-id="2398f-126">I kolumnen **tillgång**, välj länken för tillgången.</span><span class="sxs-lookup"><span data-stu-id="2398f-126">In the **Asset** column, select the link for the asset.</span></span> <span data-ttu-id="2398f-127">Sidan **Detaljer** visas.</span><span class="sxs-lookup"><span data-stu-id="2398f-127">The **Details** page appears.</span></span>
3. <span data-ttu-id="2398f-128">Välj **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="2398f-128">Select **Edit**.</span></span>
4. <span data-ttu-id="2398f-129">På snabbfliken **allmänt** väljer du värden i fälten **tillverkare** och **modell**.</span><span class="sxs-lookup"><span data-stu-id="2398f-129">On the **General** FastTab, select values in the **Manufacturer** and **Model** fields.</span></span>
