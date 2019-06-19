---
title: Balansräkning
description: Den här artikeln beskriver standardrapporter för balansräkningar. Den beskrivs också de byggstenar som associeras med dessa rapporter.
author: jcart1106
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: FinanicalReports
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 12274
ms.assetid: 52f78229-f531-4d16-b337-e2628994acb6
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2d54748daa27011e0222123ee2b9a19b9288734c
ms.sourcegitcommit: 574d4dda83dcab94728a3d35fc53ee7e2b90feb0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/22/2019
ms.locfileid: "1595326"
---
# <a name="balance-sheet-financial-reports"></a><span data-ttu-id="fd225-104">Balansräkning</span><span class="sxs-lookup"><span data-stu-id="fd225-104">Balance sheet financial reports</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fd225-105">Den här artikeln beskriver standardrapporter för balansräkningar.</span><span class="sxs-lookup"><span data-stu-id="fd225-105">This article describes the default reports for balance sheets.</span></span> <span data-ttu-id="fd225-106">Den beskrivs också de byggstenar som associeras med dessa rapporter.</span><span class="sxs-lookup"><span data-stu-id="fd225-106">It also describes the building blocks that are associated with these reports.</span></span> 

<a name="default-balance-sheet-reports"></a><span data-ttu-id="fd225-107">Standardbalansräkning</span><span class="sxs-lookup"><span data-stu-id="fd225-107">Default balance sheet reports</span></span>
-----------------------------

<span data-ttu-id="fd225-108">Det finns två standardrapporter för balansräkning.</span><span class="sxs-lookup"><span data-stu-id="fd225-108">There are two default balance sheet reports.</span></span> <span data-ttu-id="fd225-109">På en rapport staplas avsnitten.</span><span class="sxs-lookup"><span data-stu-id="fd225-109">On one report, the sections are stacked.</span></span> <span data-ttu-id="fd225-110">På den andra rapporten visas är avsnitten bredvid varandra.</span><span class="sxs-lookup"><span data-stu-id="fd225-110">On the other report, the sections are side by side.</span></span>

| <span data-ttu-id="fd225-111">Standardrapport</span><span class="sxs-lookup"><span data-stu-id="fd225-111">Default report</span></span>                       | <span data-ttu-id="fd225-112">Vad den gör</span><span class="sxs-lookup"><span data-stu-id="fd225-112">What it does</span></span>                                                                                                                           |
|--------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="fd225-113">Balansräkning – standardinställning</span><span class="sxs-lookup"><span data-stu-id="fd225-113">Balance Sheet – Default</span></span>              | <span data-ttu-id="fd225-114">Visar organisationens ekonomiska läge för året.</span><span class="sxs-lookup"><span data-stu-id="fd225-114">Provides a view of the organization's financial position for the year.</span></span>                                                                 |
| <span data-ttu-id="fd225-115">Balansräkning sida vid sida – standardinställning</span><span class="sxs-lookup"><span data-stu-id="fd225-115">Side by Side Balance Sheet – Default</span></span> | <span data-ttu-id="fd225-116">Visar organisationens ekonomiska läge för året.</span><span class="sxs-lookup"><span data-stu-id="fd225-116">Provides a view of the organization's financial position for the year.</span></span> <span data-ttu-id="fd225-117">Tillgångar och skulder och aktiekapitalet visas sida vid sida.</span><span class="sxs-lookup"><span data-stu-id="fd225-117">Assets and liability and shareholder’s equity are side by side.</span></span> |

## <a name="building-blocks"></a><span data-ttu-id="fd225-118">Byggstenar</span><span class="sxs-lookup"><span data-stu-id="fd225-118">Building blocks</span></span>
<span data-ttu-id="fd225-119">Balansräkningen använder följande byggstenar.</span><span class="sxs-lookup"><span data-stu-id="fd225-119">The balance sheet financial reports use the following building blocks.</span></span>

| <span data-ttu-id="fd225-120">Standardrapport</span><span class="sxs-lookup"><span data-stu-id="fd225-120">Default report</span></span>                       | <span data-ttu-id="fd225-121">Raddefinition</span><span class="sxs-lookup"><span data-stu-id="fd225-121">Row definition</span></span>                       | <span data-ttu-id="fd225-122">Kolumndefinition</span><span class="sxs-lookup"><span data-stu-id="fd225-122">Column definition</span></span>             |
|--------------------------------------|--------------------------------------|-------------------------------|
| <span data-ttu-id="fd225-123">Balansräkning – standardinställning</span><span class="sxs-lookup"><span data-stu-id="fd225-123">Balance Sheet - Default</span></span>              | <span data-ttu-id="fd225-124">Balansräkning – standardinställning</span><span class="sxs-lookup"><span data-stu-id="fd225-124">Balance Sheet - Default</span></span>              | <span data-ttu-id="fd225-125">Hittills i år och avvikelse - standardinställning</span><span class="sxs-lookup"><span data-stu-id="fd225-125">YTD and Variance - Default</span></span>    |
| <span data-ttu-id="fd225-126">Balansräkning sida vid sida – standardinställning</span><span class="sxs-lookup"><span data-stu-id="fd225-126">Side by Side Balance Sheet – Default</span></span> | <span data-ttu-id="fd225-127">Balansräkning sida vid sida – standardinställning</span><span class="sxs-lookup"><span data-stu-id="fd225-127">Side by Side Balance Sheet – Default</span></span> | <span data-ttu-id="fd225-128">Kolumn för ackumulerat för året - standardinställning</span><span class="sxs-lookup"><span data-stu-id="fd225-128">Year to Date Column - Default</span></span> |

### <a name="row-definition"></a><span data-ttu-id="fd225-129">Raddefinition</span><span class="sxs-lookup"><span data-stu-id="fd225-129">Row definition</span></span>

<span data-ttu-id="fd225-130">Raddefinitioner för båda balansräkningsrapporterna innehåller avsnitt för varje del i en traditionell balansräkning.</span><span class="sxs-lookup"><span data-stu-id="fd225-130">The row definitions for both balance sheet reports contain sections for each part of a traditional balance sheet.</span></span> <span data-ttu-id="fd225-131">I rapporten där elementen visas bredvid varandra finns en kolumnbrytning så att skulder och eget kapital visas bredvid tillgångar.</span><span class="sxs-lookup"><span data-stu-id="fd225-131">The side-by-side report includes a column break, so that liability and the owner’s equity appear next to assets.</span></span> <span data-ttu-id="fd225-132">Huvudkontokategoridimensionen används för att bygga upp båda raddefinitionerna.</span><span class="sxs-lookup"><span data-stu-id="fd225-132">The Main Account Category dimension is used to build both row definitions.</span></span> <span data-ttu-id="fd225-133">Därför kan alla generera rapporterna, utan att behöva göra några ändringar.</span><span class="sxs-lookup"><span data-stu-id="fd225-133">Therefore, anyone can generate the reports without having to make any modifications.</span></span>

### <a name="column-definition"></a><span data-ttu-id="fd225-134">Kolumndefinition</span><span class="sxs-lookup"><span data-stu-id="fd225-134">Column definition</span></span>

<span data-ttu-id="fd225-135">Dessa kolumndefinitioner innehåller olika typer av kolumner för att tillhandahålla andra nivåer av information och ekonomiska data.</span><span class="sxs-lookup"><span data-stu-id="fd225-135">The column definitions contain different types of columns to provide different levels of detail and financial data.</span></span>

-   <span data-ttu-id="fd225-136">**Hittills i år och avvikelse – standardkolumntyper:**</span><span class="sxs-lookup"><span data-stu-id="fd225-136">**YTD and Variance – Default column types:**</span></span>
    -   <span data-ttu-id="fd225-137">**DESC** – beskrivningen från raddefinitionen.</span><span class="sxs-lookup"><span data-stu-id="fd225-137">**DESC** – The description from the row definition</span></span>
    -   <span data-ttu-id="fd225-138">**FD** – ackumulerat för året för innevarande år</span><span class="sxs-lookup"><span data-stu-id="fd225-138">**FD** – Year-to-date financial data for the current year</span></span>
    -   <span data-ttu-id="fd225-139">**FD** – ackumulerat för året för det senaste året</span><span class="sxs-lookup"><span data-stu-id="fd225-139">**FD** – Year-to-date financial data for the last year</span></span>
    -   <span data-ttu-id="fd225-140">**CALC** – avvikelsen från subtraktionen av förra året från innevarande år</span><span class="sxs-lookup"><span data-stu-id="fd225-140">**CALC** – The variance from subtracting last year from this year</span></span>

<!-- -->

-   <span data-ttu-id="fd225-141">**Kolumn för ackumulerat för året - standardinställning:**</span><span class="sxs-lookup"><span data-stu-id="fd225-141">**Year to Date Column – Default:**</span></span>
    -   <span data-ttu-id="fd225-142">**DESC** – beskrivningen från raddefinitionen.</span><span class="sxs-lookup"><span data-stu-id="fd225-142">**DESC** – The description from the row definition</span></span>
    -   <span data-ttu-id="fd225-143">**FD** – ackumulerat för året för innevarande år</span><span class="sxs-lookup"><span data-stu-id="fd225-143">**FD** – Year-to-date financial data for the current year</span></span>



<a name="additional-resources"></a><span data-ttu-id="fd225-144">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="fd225-144">Additional resources</span></span>
--------

[<span data-ttu-id="fd225-145">Ekonomisk rapportering</span><span class="sxs-lookup"><span data-stu-id="fd225-145">Financial reporting</span></span>](financial-reporting-getting-started.md)

[<span data-ttu-id="fd225-146">Visa ekonomiska rapporter</span><span class="sxs-lookup"><span data-stu-id="fd225-146">View financial reports</span></span>](view-financial-reports.md)

[<span data-ttu-id="fd225-147">Dynamics-ekonomirapporteringsblogg</span><span class="sxs-lookup"><span data-stu-id="fd225-147">Dynamics Financial Reporting Blog</span></span>](https://blogs.msdn.com/b/dynamics_financial_reporting/)



