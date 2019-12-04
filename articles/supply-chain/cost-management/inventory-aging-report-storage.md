---
title: Lagerföråldringsrapport
description: I det här avsnittet beskrivs de funktioner som gör att du kan köra en lagerföråldringsrapport och göra utdata tillgängliga som ett formulär och ett diagram.
author: AndersGirke
manager: AnnBe
ms.date: 11/11/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CostAdminWorkspace, CostAnalysisWorkspace
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2019-01-10
ms.dyn365.ops.version: ''
ms.openlocfilehash: 21411c104c854224ff3689dc8e080b88d9fc7d23
ms.sourcegitcommit: 9267608347c9781fb4ba70f1384ca24da69c716d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/15/2019
ms.locfileid: "2810261"
---
# <a name="inventory-aging-report"></a><span data-ttu-id="fe583-103">Lagerföråldringsrapport</span><span class="sxs-lookup"><span data-stu-id="fe583-103">Inventory aging report</span></span>


[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="fe583-104">I Microsoft Dynamics 365 Supply Chain Management kan du köra en **Lagerföråldringsrapport** och göra utdata tillgängliga som ett formulär och ett diagram.</span><span class="sxs-lookup"><span data-stu-id="fe583-104">In Microsoft Dynamics 365 Supply Chain Management, you can run an **Inventory aging** report and make the output available as a form and a chart.</span></span> <span data-ttu-id="fe583-105">I formuläret justeras kolumner och aggregerade saldon dynamiskt, beroende på vilken layout som har konfigurerats.</span><span class="sxs-lookup"><span data-stu-id="fe583-105">In the form, columns and aggregate balances are dynamically adjusted, depending on the layout that is configured.</span></span> <span data-ttu-id="fe583-106">Diagrammet innehåller en visuell översikt som stöder filtrering och gör att du kan öka detaljnivån.</span><span class="sxs-lookup"><span data-stu-id="fe583-106">The chart provides a visual overview that supports filtering and lets you drill down into details.</span></span> <span data-ttu-id="fe583-107">Dessutom kan du med hjälp av en dataentitet som kallas **Lagerföråldringsrapport** exportera resultaten av en körning av **Lagerföråldringsrapport** till format som t.ex. Microsoft Excel-fil eller PDF-fil.</span><span class="sxs-lookup"><span data-stu-id="fe583-107">Additionally, a data entity that is named **Inventory aging report** lets you export the results of an **Inventory aging** report run to a format such as a Microsoft Excel file or a PDF file.</span></span>

<span data-ttu-id="fe583-108">Den här metoden för att köra en **Lagerföråldringsrapport** är användbar i fall där utdata innehåller många rader.</span><span class="sxs-lookup"><span data-stu-id="fe583-108">This method of running an **Inventory aging** report is helpful in cases where the output contains many lines.</span></span> <span data-ttu-id="fe583-109">Till exempel kommer udata att innehålla många rader om du har 50 000 artiklar och 300 butiker som har skapats som lagerställen och du begär lagerföråldring per artikel, plats och lagerställe.</span><span class="sxs-lookup"><span data-stu-id="fe583-109">For example, the output will contain many lines if you have 50,000 items and 300 stores that are created as warehouses, and you request inventory aging by item, site, and warehouse.</span></span>

## <a name="run-an-inventory-aging-report"></a><span data-ttu-id="fe583-110">Kör en lagerföråldringsrapport</span><span class="sxs-lookup"><span data-stu-id="fe583-110">Run an Inventory aging report</span></span>

1. <span data-ttu-id="fe583-111">Gå till **kostnadshantering \>förfrågningar och rapporter \>lagring av lagerföråldringsrapport**.</span><span class="sxs-lookup"><span data-stu-id="fe583-111">Go to **Cost management \> Inquiries and reports \> Inventory aging report storage**.</span></span>
1. <span data-ttu-id="fe583-112">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="fe583-112">Select **New**.</span></span>
1. <span data-ttu-id="fe583-113">I fältet **Identifierare för process – Namn** anger du ett unikt namn för rapporten.</span><span class="sxs-lookup"><span data-stu-id="fe583-113">In the **Process Identifier – Name** field, enter a unique name for the report.</span></span>
1. <span data-ttu-id="fe583-114">Välj rapporten **Identifiering – ID** och filtrera efter behov.</span><span class="sxs-lookup"><span data-stu-id="fe583-114">Select the **Identification – ID** report, and filter it as you require.</span></span>

    <span data-ttu-id="fe583-115">Rapportkörningen görs alltid i ett batchjobb.</span><span class="sxs-lookup"><span data-stu-id="fe583-115">Report execution is always done in a batch job.</span></span>

1. <span data-ttu-id="fe583-116">När batchjobbet är klart visas utdata på sidan **lagring av lagerföråldringsrapport**.</span><span class="sxs-lookup"><span data-stu-id="fe583-116">After the batch job is completed, the output is shown on the **Inventory aging report storage** page.</span></span>
1. <span data-ttu-id="fe583-117">Om du vill visa resultatet som ett formulär med en traditionell rutig layout väljer du **Visa detaljer**.</span><span class="sxs-lookup"><span data-stu-id="fe583-117">To view the output as a form that has a traditional grid layout, select **View details**.</span></span> <span data-ttu-id="fe583-118">Om du vill visa resultatet som ett aggregerat diagram väljer du **Visa diagram**.</span><span class="sxs-lookup"><span data-stu-id="fe583-118">To view the output as an aggregated chart, select **View chart**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="fe583-119">Formuläret innehåller delsummor som definieras i rapportlayouten.</span><span class="sxs-lookup"><span data-stu-id="fe583-119">The form won't include subtotals that are defined in the report layout.</span></span>

<span data-ttu-id="fe583-120">Dataentiteten **Lagerföråldringsrapport** låter dig exportera resultatet av **Lagerföråldringsrapport** genom att använda ett filter för fältet **Identifierare för process – Namn** till ett format som datahanteringen stöder.</span><span class="sxs-lookup"><span data-stu-id="fe583-120">The **Inventory aging report** data entity lets you export the output of an **Inventory aging** report by applying a filter for the **Process Identifier – Name** field to any format that Data management supports.</span></span>
