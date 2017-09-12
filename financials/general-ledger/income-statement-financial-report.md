---
title: "Resultaträkning"
description: "Den här artikeln beskriver standardrapporten för inkomstredovisning. Här beskrivs också de byggstenar som associeras med den här rapporten."
author: jcart1106
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 12294
ms.assetid: 30820be0-d943-4f8b-8c25-6414ec393b3d
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 0017d13b7f7594462dfff4ef896f4139607d4bc5
ms.contentlocale: sv-se
ms.lasthandoff: 08/29/2017

---

# <a name="income-statement-financial-report"></a><span data-ttu-id="67d04-104">Resultaträkning</span><span class="sxs-lookup"><span data-stu-id="67d04-104">Income statement financial report</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="67d04-105">Den här artikeln beskriver standardrapporten för inkomstredovisning.</span><span class="sxs-lookup"><span data-stu-id="67d04-105">This article describes the default report for income statements.</span></span> <span data-ttu-id="67d04-106">Här beskrivs också de byggstenar som associeras med den här rapporten.</span><span class="sxs-lookup"><span data-stu-id="67d04-106">It also describes the building blocks that are associated with this report.</span></span> 

<a name="default-income-statement-report"></a><span data-ttu-id="67d04-107">Standardresultaträkning</span><span class="sxs-lookup"><span data-stu-id="67d04-107">Default income statement report</span></span>
-------------------------------

| <span data-ttu-id="67d04-108">Standardrapport</span><span class="sxs-lookup"><span data-stu-id="67d04-108">Default report</span></span>             | <span data-ttu-id="67d04-109">Vad den gör</span><span class="sxs-lookup"><span data-stu-id="67d04-109">What it does</span></span>                                                                                              |
|----------------------------|-----------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="67d04-110">Resultaträkning – standardinställning</span><span class="sxs-lookup"><span data-stu-id="67d04-110">Income Statement – Default</span></span> | <span data-ttu-id="67d04-111">Visar organisationens lönsamhet för den aktuella perioden och även till dags dato.</span><span class="sxs-lookup"><span data-stu-id="67d04-111">Provides a view of the organization’s profitability for the current period and also for the year to date.</span></span> |

## <a name="building-blocks"></a><span data-ttu-id="67d04-112">Byggstenar</span><span class="sxs-lookup"><span data-stu-id="67d04-112">Building blocks</span></span>
<span data-ttu-id="67d04-113">Resultatrapporten använder följande byggstenar.</span><span class="sxs-lookup"><span data-stu-id="67d04-113">The income statement financial report uses the following building blocks.</span></span>

| <span data-ttu-id="67d04-114">Standardrapport</span><span class="sxs-lookup"><span data-stu-id="67d04-114">Default report</span></span>             | <span data-ttu-id="67d04-115">Raddefinition</span><span class="sxs-lookup"><span data-stu-id="67d04-115">Row definition</span></span>                     | <span data-ttu-id="67d04-116">Kolumndefinition</span><span class="sxs-lookup"><span data-stu-id="67d04-116">Column definition</span></span>          |
|----------------------------|------------------------------------|----------------------------|
| <span data-ttu-id="67d04-117">Resultaträkning – standardinställning</span><span class="sxs-lookup"><span data-stu-id="67d04-117">Income Statement - Default</span></span> | <span data-ttu-id="67d04-118">Översiktsresultaträkning – standardinställning</span><span class="sxs-lookup"><span data-stu-id="67d04-118">Summary Income Statement - Default</span></span> | <span data-ttu-id="67d04-119">Periodisk och hittills i år – standardvärde</span><span class="sxs-lookup"><span data-stu-id="67d04-119">Periodic and YTD - Default</span></span> |

### <a name="row-definition"></a><span data-ttu-id="67d04-120">Raddefinition</span><span class="sxs-lookup"><span data-stu-id="67d04-120">Row definition</span></span>

<span data-ttu-id="67d04-121">Raddefinitionen, översiktsresultaträkningen – standardinställning, innehåller ett avsnitt för varje del av en traditionell resultaträkning.</span><span class="sxs-lookup"><span data-stu-id="67d04-121">The row definition, Summary Income Statement – Default, contains a section for each part of a traditional income statement.</span></span> <span data-ttu-id="67d04-122">Huvudkontokategoridimensionen används för att bygga upp raddefinitionen.</span><span class="sxs-lookup"><span data-stu-id="67d04-122">The Main Account Category dimension is used to build this row definition.</span></span> <span data-ttu-id="67d04-123">Därför kan alla generera rapporten, utan att behöva göra några ändringar.</span><span class="sxs-lookup"><span data-stu-id="67d04-123">Therefore, anyone can generate the report without having to make any modifications.</span></span>

### <a name="column-definition"></a><span data-ttu-id="67d04-124">Kolumndefinition</span><span class="sxs-lookup"><span data-stu-id="67d04-124">Column Definition</span></span>

<span data-ttu-id="67d04-125">Dessa kolumndefinitioner innehåller olika typer av kolumner för att tillhandahålla andra nivåer av information och ekonomiska data.</span><span class="sxs-lookup"><span data-stu-id="67d04-125">The column definitions contain different types of columns to provide different levels of detail and financial data.</span></span>

-   <span data-ttu-id="67d04-126">**Periodisk och hittills i år – standardkolumntyper:**</span><span class="sxs-lookup"><span data-stu-id="67d04-126">**Periodic and YTD – Default column types:**</span></span>
    -   <span data-ttu-id="67d04-127">**DESC** – beskrivningen från raddefinitionen.</span><span class="sxs-lookup"><span data-stu-id="67d04-127">**DESC** – The description from the row definition</span></span>
    -   <span data-ttu-id="67d04-128">**FD** – ekonomiska data för den aktuella perioden</span><span class="sxs-lookup"><span data-stu-id="67d04-128">**FD** – Financial data for the current period</span></span>
    -   <span data-ttu-id="67d04-129">**FD** – ekonomiska data hittills i år</span><span class="sxs-lookup"><span data-stu-id="67d04-129">**FD** – Financial data for the year to date</span></span>

 

<a name="see-also"></a><span data-ttu-id="67d04-130">Se även</span><span class="sxs-lookup"><span data-stu-id="67d04-130">See also</span></span>
--------

[<span data-ttu-id="67d04-131">Ekonomisk rapportering</span><span class="sxs-lookup"><span data-stu-id="67d04-131">Financial reporting</span></span>](financial-reporting-getting-started.md)

[<span data-ttu-id="67d04-132">Visa ekonomiska rapporter</span><span class="sxs-lookup"><span data-stu-id="67d04-132">View financial reports</span></span>](view-financial-reports.md)

[<span data-ttu-id="67d04-133">Dynamics-ekonomirapporteringsblogg</span><span class="sxs-lookup"><span data-stu-id="67d04-133">Dynamics Financial Reporting Blog</span></span>](http://blogs.msdn.com/b/dynamics_financial_reporting/)




