---
title: Resultaträkning
description: Den här artikeln beskriver standardrapporten för inkomstredovisning. Här beskrivs också de byggstenar som associeras med den här rapporten.
author: jcart1106
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: roschlom
ms.custom: 12294
ms.assetid: 30820be0-d943-4f8b-8c25-6414ec393b3d
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fab0e9d5e550b1848c3483b3172836e258353ebb
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5249081"
---
# <a name="income-statement-financial-report"></a><span data-ttu-id="39091-104">Resultaträkning</span><span class="sxs-lookup"><span data-stu-id="39091-104">Income statement financial report</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="39091-105">Den här artikeln beskriver standardrapporten för inkomstredovisning.</span><span class="sxs-lookup"><span data-stu-id="39091-105">This article describes the default report for income statements.</span></span> <span data-ttu-id="39091-106">Här beskrivs också de byggstenar som associeras med den här rapporten.</span><span class="sxs-lookup"><span data-stu-id="39091-106">It also describes the building blocks that are associated with this report.</span></span> 

<a name="default-income-statement-report"></a><span data-ttu-id="39091-107">Standardresultaträkning</span><span class="sxs-lookup"><span data-stu-id="39091-107">Default income statement report</span></span>
-------------------------------

| <span data-ttu-id="39091-108">Standardrapport</span><span class="sxs-lookup"><span data-stu-id="39091-108">Default report</span></span>             | <span data-ttu-id="39091-109">Vad den gör</span><span class="sxs-lookup"><span data-stu-id="39091-109">What it does</span></span>                                                                                              |
|----------------------------|-----------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="39091-110">Resultaträkning – standardinställning</span><span class="sxs-lookup"><span data-stu-id="39091-110">Income Statement – Default</span></span> | <span data-ttu-id="39091-111">Visar organisationens lönsamhet för den aktuella perioden och även till dags dato.</span><span class="sxs-lookup"><span data-stu-id="39091-111">Provides a view of the organization’s profitability for the current period and also for the year to date.</span></span> |

## <a name="building-blocks"></a><span data-ttu-id="39091-112">Byggstenar</span><span class="sxs-lookup"><span data-stu-id="39091-112">Building blocks</span></span>
<span data-ttu-id="39091-113">Resultatrapporten använder följande byggstenar.</span><span class="sxs-lookup"><span data-stu-id="39091-113">The income statement financial report uses the following building blocks.</span></span>

| <span data-ttu-id="39091-114">Standardrapport</span><span class="sxs-lookup"><span data-stu-id="39091-114">Default report</span></span>             | <span data-ttu-id="39091-115">Raddefinition</span><span class="sxs-lookup"><span data-stu-id="39091-115">Row definition</span></span>                     | <span data-ttu-id="39091-116">Kolumndefinition</span><span class="sxs-lookup"><span data-stu-id="39091-116">Column definition</span></span>          |
|----------------------------|------------------------------------|----------------------------|
| <span data-ttu-id="39091-117">Resultaträkning – standardinställning</span><span class="sxs-lookup"><span data-stu-id="39091-117">Income Statement - Default</span></span> | <span data-ttu-id="39091-118">Översiktsresultaträkning – standardinställning</span><span class="sxs-lookup"><span data-stu-id="39091-118">Summary Income Statement - Default</span></span> | <span data-ttu-id="39091-119">Periodisk och hittills i år – standardvärde</span><span class="sxs-lookup"><span data-stu-id="39091-119">Periodic and YTD - Default</span></span> |

### <a name="row-definition"></a><span data-ttu-id="39091-120">Raddefinition</span><span class="sxs-lookup"><span data-stu-id="39091-120">Row definition</span></span>

<span data-ttu-id="39091-121">Raddefinitionen, översiktsresultaträkningen – standardinställning, innehåller ett avsnitt för varje del av en traditionell resultaträkning.</span><span class="sxs-lookup"><span data-stu-id="39091-121">The row definition, Summary Income Statement – Default, contains a section for each part of a traditional income statement.</span></span> <span data-ttu-id="39091-122">Huvudkontokategoridimensionen används för att bygga upp raddefinitionen.</span><span class="sxs-lookup"><span data-stu-id="39091-122">The Main Account Category dimension is used to build this row definition.</span></span> <span data-ttu-id="39091-123">Därför kan alla generera rapporten, utan att behöva göra några ändringar.</span><span class="sxs-lookup"><span data-stu-id="39091-123">Therefore, anyone can generate the report without having to make any modifications.</span></span>

### <a name="column-definition"></a><span data-ttu-id="39091-124">Kolumndefinition</span><span class="sxs-lookup"><span data-stu-id="39091-124">Column Definition</span></span>

<span data-ttu-id="39091-125">Dessa kolumndefinitioner innehåller olika typer av kolumner för att tillhandahålla andra nivåer av information och ekonomiska data.</span><span class="sxs-lookup"><span data-stu-id="39091-125">The column definitions contain different types of columns to provide different levels of detail and financial data.</span></span>

-   <span data-ttu-id="39091-126">**Periodisk och hittills i år – standardkolumntyper:**</span><span class="sxs-lookup"><span data-stu-id="39091-126">**Periodic and YTD – Default column types:**</span></span>
    -   <span data-ttu-id="39091-127">**DESC** – beskrivningen från raddefinitionen.</span><span class="sxs-lookup"><span data-stu-id="39091-127">**DESC** – The description from the row definition</span></span>
    -   <span data-ttu-id="39091-128">**FD** – ekonomiska data för den aktuella perioden</span><span class="sxs-lookup"><span data-stu-id="39091-128">**FD** – Financial data for the current period</span></span>
    -   <span data-ttu-id="39091-129">**FD** – ekonomiska data hittills i år</span><span class="sxs-lookup"><span data-stu-id="39091-129">**FD** – Financial data for the year to date</span></span>



<a name="additional-resources"></a><span data-ttu-id="39091-130">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="39091-130">Additional resources</span></span>
--------

[<span data-ttu-id="39091-131">Översikt över ekonomisk rapportering</span><span class="sxs-lookup"><span data-stu-id="39091-131">Financial reporting overview</span></span>](financial-reporting-getting-started.md)

[<span data-ttu-id="39091-132">Visa ekonomiska rapporter</span><span class="sxs-lookup"><span data-stu-id="39091-132">View financial reports</span></span>](view-financial-reports.md)

[<span data-ttu-id="39091-133">Dynamics-ekonomirapporteringsblogg</span><span class="sxs-lookup"><span data-stu-id="39091-133">Dynamics Financial Reporting Blog</span></span>](https://community.dynamics.com/365/financeandoperations/b/dynamics-365-finance-blog)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]