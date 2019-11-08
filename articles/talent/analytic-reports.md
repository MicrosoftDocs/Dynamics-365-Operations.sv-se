---
title: Använda analysrapporter i Microsoft Dynamics 365 Talent - Attract
description: Det här ämnet beskriver analysrapporterna för insikter om anställningsprocessen i Microsoft Dynamics 365 Talent - Attract
author: fewatson
manager: AnnBe
ms.date: 04/30/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: fewatson
ms.search.validFrom: 2019-04-30
ms.dyn365.ops.version: Talent April 2019 update
ms.openlocfilehash: 5a4d160e8c90725d5ea129a76fd48da1c5af7900
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/03/2019
ms.locfileid: "2551528"
---
# <a name="use-analytic-reports-in-microsoft-dynamics-365-talent---attract"></a><span data-ttu-id="08706-103">Använda analysrapporter i Microsoft Dynamics 365 Talent - Attract</span><span class="sxs-lookup"><span data-stu-id="08706-103">Use analytic reports in Microsoft Dynamics 365 Talent - Attract</span></span>

<span data-ttu-id="08706-104">Analytiska rapporter i Microsoft Dynamics 365 Talent: Attract ger en OOTB-lösning (färdigkonfigurerade) för anställning av processinsikter.</span><span class="sxs-lookup"><span data-stu-id="08706-104">Analytic reports in Microsoft Dynamics 365 Talent: Attract provide an out-of-the-box (OOTB) solution for hiring process insights.</span></span> <span data-ttu-id="08706-105">Tillgängliga funktioner omfattar:</span><span class="sxs-lookup"><span data-stu-id="08706-105">Availabe features include:</span></span>

- <span data-ttu-id="08706-106">**Jobbanalys:** Klicka på **Analys** inom ett jobb för mätvärden på jobbets sökande.</span><span class="sxs-lookup"><span data-stu-id="08706-106">**Job analytics:** Click the **Analytics** tab within a job for metrics on the job's applicants.</span></span>
- <span data-ttu-id="08706-107">**Analysnav:** Klicka  **Analys** på analys när du vill navigera till vänster om aggregerade mått över jobb.</span><span class="sxs-lookup"><span data-stu-id="08706-107">**Analytics hub:** Click **Analytics** on the left navigation for aggregated metrics across jobs.</span></span>
- <span data-ttu-id="08706-108">**Användarspecifik säkerhet** – Åtkomst till rapporter styrs av Attract [roll](security-attract.md) och jobbdeltagarnas roll.</span><span class="sxs-lookup"><span data-stu-id="08706-108">**User-specific security:** Access to reports is controlled by Attract [role](security-attract.md) and job participant role.</span></span>
- <span data-ttu-id="08706-109">**Korsfiltrering:** Klicka på visuella objekt i en rapport om du vill visa andra mått som filtrerats efter valda data.</span><span class="sxs-lookup"><span data-stu-id="08706-109">**Cross-filtering:** Click visuals within a report to view other metrics filtered by selected data.</span></span>

>[!NOTE] 
>- <span data-ttu-id="08706-110">Den här funktionen är för närvarande i [förhandsgranskning](access-preview-feature.md).</span><span class="sxs-lookup"><span data-stu-id="08706-110">This feature is currently in [preview](access-preview-feature.md).</span></span> <span data-ttu-id="08706-111">För att kunna prova måste du ha [**Tillägget för omfattande anställning**](attract-comprehensive-hiring.md).</span><span class="sxs-lookup"><span data-stu-id="08706-111">To try it, you must have the [**Comprehensive Hiring Add-On**](attract-comprehensive-hiring.md).</span></span>
>- <span data-ttu-id="08706-112">Alla allmänna förhandsgranskningsrapporter visas på engelska.</span><span class="sxs-lookup"><span data-stu-id="08706-112">All public preview reports are displayed in English.</span></span>
>- <span data-ttu-id="08706-113">Uppdatera rapporter var 3:e timme.</span><span class="sxs-lookup"><span data-stu-id="08706-113">Reports refresh every 3 hours.</span></span> <span data-ttu-id="08706-114">Den senaste uppdaterings tiden (i den lokala tidszonen) finns högst upp i rapporten.</span><span class="sxs-lookup"><span data-stu-id="08706-114">The last refresh time (in the local timezone) is located at the top of the report.</span></span> <span data-ttu-id="08706-115">Uppdateringstiden är en ungefärlig och varierar beroende på data volym och resursbelastning i din region.</span><span class="sxs-lookup"><span data-stu-id="08706-115">Refresh times are an approximation and vary based on data volume and resource load in your region.</span></span>

## <a name="job-analytics"></a><span data-ttu-id="08706-116">Jobbanalyser</span><span class="sxs-lookup"><span data-stu-id="08706-116">Job Analytics</span></span>

<span data-ttu-id="08706-117">Jobbanalysrapporter ger en ögonblicksbild av anställningsprocessen för ett jobb.</span><span class="sxs-lookup"><span data-stu-id="08706-117">Job Analytics reports are a snapshot of the hiring process for a job.</span></span>  <span data-ttu-id="08706-118">Nyckelmått är:</span><span class="sxs-lookup"><span data-stu-id="08706-118">Key metrics include:</span></span>

- <span data-ttu-id="08706-119">Aktiva sökande efter etapp</span><span class="sxs-lookup"><span data-stu-id="08706-119">Active applicants by stage</span></span>
- <span data-ttu-id="08706-120">Sökandes källa</span><span class="sxs-lookup"><span data-stu-id="08706-120">Applicant source</span></span>
- <span data-ttu-id="08706-121">Typ av sökande (intern eller extern)</span><span class="sxs-lookup"><span data-stu-id="08706-121">Applicant type (internal or external)</span></span>

## <a name="analytics-hub"></a><span data-ttu-id="08706-122">Analysnav</span><span class="sxs-lookup"><span data-stu-id="08706-122">Analytics Hub</span></span>

<span data-ttu-id="08706-123">Analysnav rapporterar sammansatta data över jobb för att visa trender anställningsprocessen.</span><span class="sxs-lookup"><span data-stu-id="08706-123">Analytics Hub reports aggregate data across jobs to surface trends in the hiring process.</span></span> <span data-ttu-id="08706-124">Attract inkluderar två OOTB-rapporter: Sammanfattning av försäljningsförlopp och trattanalys.</span><span class="sxs-lookup"><span data-stu-id="08706-124">Attract includes two OOTB reports: Pipeline Summary and Funnel Analysis.</span></span>

### <a name="pipeline-summary"></a><span data-ttu-id="08706-125">Sammanfattning av pipeline</span><span class="sxs-lookup"><span data-stu-id="08706-125">Pipeline Summary</span></span>

<span data-ttu-id="08706-126">Rapporten sammanfattning av försäljningsförlopp sammanställer data för lediga jobb.</span><span class="sxs-lookup"><span data-stu-id="08706-126">The Pipeline Summary report aggregates data for open jobs.</span></span> <span data-ttu-id="08706-127">Nyckelmått är:</span><span class="sxs-lookup"><span data-stu-id="08706-127">Key metrics include:</span></span>

- <span data-ttu-id="08706-128">Sökande över alla jobb efter fas</span><span class="sxs-lookup"><span data-stu-id="08706-128">Applicants across all jobs by stage</span></span>
- <span data-ttu-id="08706-129">Sökandes källa</span><span class="sxs-lookup"><span data-stu-id="08706-129">Applicant source</span></span>
- <span data-ttu-id="08706-130">Lediga jobb efter tjänsteåldernivå</span><span class="sxs-lookup"><span data-stu-id="08706-130">Open jobs by seniority level</span></span>

### <a name="funnel-analysis"></a><span data-ttu-id="08706-131">Trattanalys</span><span class="sxs-lookup"><span data-stu-id="08706-131">Funnel Analysis</span></span>

<span data-ttu-id="08706-132">I rapporten för trattanalys sammanställs data för jobb som har stängts som fyllda.</span><span class="sxs-lookup"><span data-stu-id="08706-132">The Funnel Analysis report aggregates data for jobs that have been closed as filled.</span></span> <span data-ttu-id="08706-133">Nyckelmått är:</span><span class="sxs-lookup"><span data-stu-id="08706-133">Key metrics include:</span></span>

- <span data-ttu-id="08706-134">Tid att hyra</span><span class="sxs-lookup"><span data-stu-id="08706-134">Time to hire</span></span>
- <span data-ttu-id="08706-135">Konverteringsmått (vid hovring)</span><span class="sxs-lookup"><span data-stu-id="08706-135">Conversion metrics (on hover)</span></span>
- <span data-ttu-id="08706-136">Frekvens för godkännande av erbjudande</span><span class="sxs-lookup"><span data-stu-id="08706-136">Offer acceptance rate</span></span>

<span data-ttu-id="08706-137">Obs! för den mest exakta tiden för rapportering av tid det tar för att anställa rekommenderar vi att du använder [erbjudandehantering](offer-setup.md), en funktion som är en del av tillägget för omfattande anställning.</span><span class="sxs-lookup"><span data-stu-id="08706-137">Note: For the most accurate time to hire reporting, it is recommended that you use [Offer management](offer-setup.md), a feature available as part of the Comprehensive Hiring Add-On.</span></span>

>[!TIP] 
><span data-ttu-id="08706-138">Försök att hovra över visuella bilder om du vill ha mer information.</span><span class="sxs-lookup"><span data-stu-id="08706-138">Try hovering over visuals for additional information.</span></span> <span data-ttu-id="08706-139">Om du till exempel hovrar över **aktiva sökande** visas visuella, genomsnittsdagarna i stadiet.</span><span class="sxs-lookup"><span data-stu-id="08706-139">For example, hovering over **Active applicants** visuals will display the average days in stage.</span></span> <span data-ttu-id="08706-140">Analys av den här informationen kan ge insikter som är kritiska för att minska tiden för anställare och ge rekryterare möjlighet att fokusera på olika sätt att minska den tid som ägnas åt varje etapp.</span><span class="sxs-lookup"><span data-stu-id="08706-140">Analyzing this information can provide insights critical to reducing time to hire and enable recruiters to focus on ways to reduce the time spent in each stage.</span></span>

## <a name="user-specific-security"></a><span data-ttu-id="08706-141">Användarspecifik säkerhet</span><span class="sxs-lookup"><span data-stu-id="08706-141">User-specific security</span></span>

<span data-ttu-id="08706-142">Attract-rapporter är tillgängliga för rollerna admin, läs alla, rekryterare och Anställande chef [roller](security-attract.md).</span><span class="sxs-lookup"><span data-stu-id="08706-142">Attract reports are accessible for Admin, Read All, Recruiter, and Hiring Manager [roles](security-attract.md).</span></span> <span data-ttu-id="08706-143">Ej tilldelade användare har inte tillgång till någon av analysrapportsidorna (Jobbanalys och Analysnav).</span><span class="sxs-lookup"><span data-stu-id="08706-143">Unassigned users do not have access to either of the analytic report pages (Job Analytics or Analytics Hub).</span></span>

<span data-ttu-id="08706-144">Jobbanalys-rapporter visar data för det valda jobbet.</span><span class="sxs-lookup"><span data-stu-id="08706-144">Job Analytics reports display data for the selected job.</span></span> <span data-ttu-id="08706-145">Analysnav rapporterar sammanslagna data över alla jobb som en användare kan visa.</span><span class="sxs-lookup"><span data-stu-id="08706-145">Analytics Hub reports aggregate data across all jobs a user can view.</span></span> <span data-ttu-id="08706-146">Användare som kan visa både mina jobb och alla jobb på jobbsidan har samma vyer tillgängliga i analysnavet.</span><span class="sxs-lookup"><span data-stu-id="08706-146">Users that can view both My jobs and All jobs on the Jobs page have the same views available in the Analytics Hub.</span></span>

## <a name="cross-filter"></a><span data-ttu-id="08706-147">Korsfilter</span><span class="sxs-lookup"><span data-stu-id="08706-147">Cross-filter</span></span>

<span data-ttu-id="08706-148">En av de fantastiska funktionerna i Power BI är hur alla visuella element på en rapportsida är sammankopplade.</span><span class="sxs-lookup"><span data-stu-id="08706-148">One of the great features of Power BI is the way all visuals on a report page are interconnected.</span></span> <span data-ttu-id="08706-149">Om du markerar en datapunkt på något av de visuella elementen, är alla andra visuella element på sidan som innehåller data ändringar baserade på den markeringen.</span><span class="sxs-lookup"><span data-stu-id="08706-149">If you select a data point on one of the visuals, all the other visuals on the page that contain that data change, based on that selection.</span></span> <span data-ttu-id="08706-150">Läs mer och se ett exempel på [hur visuella element korsfiltrerar varandra i en Power BI-rapport.](https://docs.microsoft.com/power-bi/consumer/end-user-interactions)</span><span class="sxs-lookup"><span data-stu-id="08706-150">Find out more and see an example in [How visuals cross-filter each other in a Power BI report](https://docs.microsoft.com/power-bi/consumer/end-user-interactions).</span></span>

## <a name="export-to-excel"></a><span data-ttu-id="08706-151">Exportera till Excel</span><span class="sxs-lookup"><span data-stu-id="08706-151">Export to Excel</span></span>

<span data-ttu-id="08706-152">Om du vill visa rapportdata i Excel kan du klicka på alternativmenyn (tre punkter) på en bild och välja **Exportera underliggande data**.</span><span class="sxs-lookup"><span data-stu-id="08706-152">To view report data in Excel, you can click the options menu (three dots) on a visual and select **Export underlying data**.</span></span> <span data-ttu-id="08706-153">Exporterade data exporteras som filtrerade och respekterar användarbehörigheterna för att Attract.</span><span class="sxs-lookup"><span data-stu-id="08706-153">Exported data will export as filtered, respecting user permissions in Attract.</span></span> <span data-ttu-id="08706-154">Mer information finns i [exportera data från visualiseringar](https://docs.microsoft.com/power-bi/visuals/power-bi-visualization-export-data)</span><span class="sxs-lookup"><span data-stu-id="08706-154">For more information, see [Export data from visualizations](https://docs.microsoft.com/power-bi/visuals/power-bi-visualization-export-data).</span></span>
