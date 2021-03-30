---
title: Lagring av Lagerföråldringsrapport
description: I det här avsnittet beskrivs de funktioner som gör att du kan köra en lagerföråldringsrapport och göra utdata tillgängliga som ett formulär och ett diagram.
author: AndersGirke
manager: tfehr
ms.date: 11/11/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventAgingStorage, InventAgingStorageChart, InventAgingStorageDetails
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2019-01-10
ms.dyn365.ops.version: ''
ms.openlocfilehash: 40b15448677f319c650c667cd7c4981c343f7a02
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5205356"
---
# <a name="inventory-aging-report-storage"></a><span data-ttu-id="cf0da-103">Lagring av Lagerföråldringsrapport</span><span class="sxs-lookup"><span data-stu-id="cf0da-103">Inventory aging report storage</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="cf0da-104">I Microsoft Dynamics 365 Supply Chain Management kan du köra en **lagring av lagerföråldringsrapport** och göra utdata tillgängliga som ett formulär och ett diagram.</span><span class="sxs-lookup"><span data-stu-id="cf0da-104">In Microsoft Dynamics 365 Supply Chain Management, you can run an **Inventory aging report storage** report and make the output available as a form and a chart.</span></span> <span data-ttu-id="cf0da-105">I formuläret justeras kolumner och aggregerade saldon dynamiskt, beroende på vilken layout som har konfigurerats.</span><span class="sxs-lookup"><span data-stu-id="cf0da-105">In the form, columns and aggregate balances are dynamically adjusted, depending on the layout that is configured.</span></span> <span data-ttu-id="cf0da-106">Diagrammet innehåller en visuell översikt som stöder filtrering och gör att du kan öka detaljnivån.</span><span class="sxs-lookup"><span data-stu-id="cf0da-106">The chart provides a visual overview that supports filtering and lets you drill down into details.</span></span> <span data-ttu-id="cf0da-107">Dessutom kan du med hjälp av en dataentitet som kallas **Lagerföråldringsrapport** exportera resultaten av en körning av **Lagring av Lagerföråldringsrapport** till format som t.ex. Microsoft Excel-fil eller PDF-fil.</span><span class="sxs-lookup"><span data-stu-id="cf0da-107">Additionally, a data entity that is named **Inventory aging report** lets you export the results of an **Inventory aging report storage** report run to a format such as a Microsoft Excel file or a PDF file.</span></span>

<span data-ttu-id="cf0da-108">Den här metoden för att köra en **Lagring av Lagerföråldringsrapport** är användbar i fall där utdata innehåller många rader.</span><span class="sxs-lookup"><span data-stu-id="cf0da-108">This method of running an **Inventory aging report storage** report is helpful in cases where the output contains many lines.</span></span> <span data-ttu-id="cf0da-109">Till exempel kommer udata att innehålla många rader om du har 50 000 artiklar och 300 butiker som har skapats som lagerställen och du begär lagerföråldring per artikel, plats och lagerställe.</span><span class="sxs-lookup"><span data-stu-id="cf0da-109">For example, the output will contain many lines if you have 50,000 items and 300 stores that are created as warehouses, and you request inventory aging by item, site, and warehouse.</span></span>

## <a name="enable-the-inventory-value-storage-report-feature"></a><span data-ttu-id="cf0da-110">Aktivera funktionen lagringsrapport för lagervärde</span><span class="sxs-lookup"><span data-stu-id="cf0da-110">Enable the Inventory value storage report feature</span></span>

<span data-ttu-id="cf0da-111">Innan du kan använda den här funktionen måste du aktivera den i ditt system.</span><span class="sxs-lookup"><span data-stu-id="cf0da-111">Before you can use this feature, you must enable it on your system.</span></span> <span data-ttu-id="cf0da-112">Administratörer kan använda inställningarna [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den om det behövs.</span><span class="sxs-lookup"><span data-stu-id="cf0da-112">Administrators can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the feature status and enable it if needed.</span></span> <span data-ttu-id="cf0da-113">Här visas funktionen i listan:</span><span class="sxs-lookup"><span data-stu-id="cf0da-113">Here, the feature is listed as:</span></span>

- <span data-ttu-id="cf0da-114">**Modul** - Kostnadshantering</span><span class="sxs-lookup"><span data-stu-id="cf0da-114">**Module** - Cost management</span></span>
- <span data-ttu-id="cf0da-115">**Funktionsnamn** - Lagring av Lagerföråldringsrapport</span><span class="sxs-lookup"><span data-stu-id="cf0da-115">**Feature name** - Inventory aging report storage</span></span>

## <a name="run-an-inventory-aging-report-storage"></a><span data-ttu-id="cf0da-116">Kör en lagring av Lagerföråldringsrapport</span><span class="sxs-lookup"><span data-stu-id="cf0da-116">Run an Inventory aging report storage</span></span>

1. <span data-ttu-id="cf0da-117">Gå till **kostnadshantering \>förfrågningar och rapporter \>lagring av lagerföråldringsrapport**.</span><span class="sxs-lookup"><span data-stu-id="cf0da-117">Go to **Cost management \> Inquiries and reports \> Inventory aging report storage**.</span></span>
1. <span data-ttu-id="cf0da-118">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="cf0da-118">Select **New**.</span></span>
1. <span data-ttu-id="cf0da-119">I fältet **Identifierare för process – Namn** anger du ett unikt namn för rapporten.</span><span class="sxs-lookup"><span data-stu-id="cf0da-119">In the **Process Identifier – Name** field, enter a unique name for the report.</span></span>
1. <span data-ttu-id="cf0da-120">Välj rapporten **Identifiering – ID** och filtrera efter behov.</span><span class="sxs-lookup"><span data-stu-id="cf0da-120">Select the **Identification – ID** report, and filter it as you require.</span></span>

    <span data-ttu-id="cf0da-121">Rapportkörningen görs alltid i ett batchjobb.</span><span class="sxs-lookup"><span data-stu-id="cf0da-121">Report execution is always done in a batch job.</span></span>

1. <span data-ttu-id="cf0da-122">När batchjobbet är klart visas utdata på sidan **lagring av lagerföråldringsrapport**.</span><span class="sxs-lookup"><span data-stu-id="cf0da-122">After the batch job is completed, the output is shown on the **Inventory aging report storage** page.</span></span>
1. <span data-ttu-id="cf0da-123">Om du vill visa resultatet som ett formulär med en traditionell rutig layout väljer du **Visa detaljer**.</span><span class="sxs-lookup"><span data-stu-id="cf0da-123">To view the output as a form that has a traditional grid layout, select **View details**.</span></span> <span data-ttu-id="cf0da-124">Om du vill visa resultatet som ett aggregerat diagram väljer du **Visa diagram**.</span><span class="sxs-lookup"><span data-stu-id="cf0da-124">To view the output as an aggregated chart, select **View chart**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="cf0da-125">Formuläret innehåller delsummor som definieras i rapportlayouten.</span><span class="sxs-lookup"><span data-stu-id="cf0da-125">The form won't include subtotals that are defined in the report layout.</span></span>

<span data-ttu-id="cf0da-126">Dataentiteten **Lagerföråldringsrapport** låter dig exportera resultatet av **Lagring av Lagerföråldringsrapport** genom att använda ett filter för fältet **Identifierare för process – Namn** till ett format som datahanteringen stöder.</span><span class="sxs-lookup"><span data-stu-id="cf0da-126">The **Inventory aging report** data entity lets you export the output of an **Inventory aging report storage** report by applying a filter for the **Process Identifier – Name** field to any format that Data management supports.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]