--- 
title: "Analysera enkätresultat"
description: "Enkätstatistiken kan användas för att beräkna medelvärde, summor och procentsatser som baseras på en uppsättning demografiska data."
author: ShielaSogge
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: KMQuestionnaireStatistics, KMQuestionnaireStatisticsLine
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: a70ea145d8c7134a32e8f0fc6980daca9a010bb0
ms.contentlocale: sv-se
ms.lasthandoff: 09/14/2018

---
# <a name="analyzing-questionnaire-results"></a><span data-ttu-id="8a0e7-103">Analysera enkätresultat</span><span class="sxs-lookup"><span data-stu-id="8a0e7-103">Analyzing questionnaire results</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8a0e7-104">Enkätstatistiken kan användas för att beräkna medelvärde, summor och procentsatser som baseras på en uppsättning demografiska data.</span><span class="sxs-lookup"><span data-stu-id="8a0e7-104">Questionnaire statistics can be used to calculate averages, totals, and percentages based on a set of demographic data.</span></span> <span data-ttu-id="8a0e7-105">Gå till Enkät > Visa och analysera resultat > Enkätstatistik om du vill starta proceduren.</span><span class="sxs-lookup"><span data-stu-id="8a0e7-105">To begin this procedure, go to Questionnaire > View and analyze results > Questionnaire statistics.</span></span> <span data-ttu-id="8a0e7-106">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="8a0e7-106">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-a-questionnaire-statistics-record"></a><span data-ttu-id="8a0e7-107">Skapa en enkätstatistikpost</span><span class="sxs-lookup"><span data-stu-id="8a0e7-107">Create a Questionnaire statistics record</span></span>
1. <span data-ttu-id="8a0e7-108">Gå till Enkätsstatistik.</span><span class="sxs-lookup"><span data-stu-id="8a0e7-108">Go to Questionnaire statistics.</span></span>
2. <span data-ttu-id="8a0e7-109">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="8a0e7-109">Click New.</span></span>
3. <span data-ttu-id="8a0e7-110">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="8a0e7-110">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="8a0e7-111">Skriv ett värde i fältet Statistik.</span><span class="sxs-lookup"><span data-stu-id="8a0e7-111">In the Statistics field, type a value.</span></span>
5. <span data-ttu-id="8a0e7-112">Skriv ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="8a0e7-112">In the Description field, type a value.</span></span>
6. <span data-ttu-id="8a0e7-113">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Enkät.</span><span class="sxs-lookup"><span data-stu-id="8a0e7-113">In the Questionnaire field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="8a0e7-114">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="8a0e7-114">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="8a0e7-115">Klicka på fliken Allmänt.</span><span class="sxs-lookup"><span data-stu-id="8a0e7-115">Click the General tab.</span></span>
    * <span data-ttu-id="8a0e7-116">Välj om du vill inkludera anonyma resultat eller resultat från arbetare, kontakter och sökande.</span><span class="sxs-lookup"><span data-stu-id="8a0e7-116">Select if you want to include anonymous results or results from workers, contacts, and applicants.</span></span>  
9. <span data-ttu-id="8a0e7-117">Markera eller avmarkera kryssrutan Arbetare.</span><span class="sxs-lookup"><span data-stu-id="8a0e7-117">Select or clear the Worker check box.</span></span>
    * <span data-ttu-id="8a0e7-118">Om du ska visa resultaten efter tjänsteålder eller ålder, anger du de intervall som du vill använda för att gruppera resultatet.</span><span class="sxs-lookup"><span data-stu-id="8a0e7-118">If you will be viewing the results by seniority or age, specify the intervals that you would like to use for grouping the results.</span></span>  
    * <span data-ttu-id="8a0e7-119">Om du anger 5 för åldersintervallet grupperas resultaten baserat på femårsintervall.</span><span class="sxs-lookup"><span data-stu-id="8a0e7-119">Entering a 5 for the age interval will group the results based on five-year age intervals.</span></span>  
10. <span data-ttu-id="8a0e7-120">Ange ett nummer i fältet Ålder.</span><span class="sxs-lookup"><span data-stu-id="8a0e7-120">In the Age field, enter a number.</span></span>
    * <span data-ttu-id="8a0e7-121">Välj om du vill köra beräkningen mot hela enkäten, för varje resultatgrupp, för varje fråga eller för varje frågerad.</span><span class="sxs-lookup"><span data-stu-id="8a0e7-121">Select if you want to run the calculation against the entire questionnaire, for each result group, for each question, or for each question row.</span></span>  
    * <span data-ttu-id="8a0e7-122">Välj hur du vill gruppera resultaten.</span><span class="sxs-lookup"><span data-stu-id="8a0e7-122">Select how you would like to group the results.</span></span>  
    * <span data-ttu-id="8a0e7-123">Om du till exempel beräknar medelpoäng per fråga kanske du vill se frågorna grupperade efter resultatgrupp.</span><span class="sxs-lookup"><span data-stu-id="8a0e7-123">For example, if you calculate the average points per question, you may want to see the questions grouped by Result group.</span></span>  
    * <span data-ttu-id="8a0e7-124">Välj de data som beräkningen ska baseras på.</span><span class="sxs-lookup"><span data-stu-id="8a0e7-124">Select the data to base the calculation on.</span></span>  
    * <span data-ttu-id="8a0e7-125">Om du till exempel vill se den genomsnittsprocent som har tagits emot i enkäten hos dina arbetare kontra det genomsnittliga antal poäng som har tagits emot hos dina arbetare.</span><span class="sxs-lookup"><span data-stu-id="8a0e7-125">For example, if you want to see the average percent received on the questionnaire across your workers versus the average number of points achieved across your workers.</span></span>  
11. <span data-ttu-id="8a0e7-126">Klicka på fliken Intervall.</span><span class="sxs-lookup"><span data-stu-id="8a0e7-126">Click the Range tab.</span></span>
    * <span data-ttu-id="8a0e7-127">Använd intervall för att begränsa resultatuppsättningen till endast de som uppfyller intervallkriterierna.</span><span class="sxs-lookup"><span data-stu-id="8a0e7-127">Use ranges to limit your result set to only those meeting the Range criteria.</span></span>  
12. <span data-ttu-id="8a0e7-128">Klicka på fliken Gruppera efter.</span><span class="sxs-lookup"><span data-stu-id="8a0e7-128">Click the Grouping by tab.</span></span>
    * <span data-ttu-id="8a0e7-129">Använd grupperingarna för att ange hur resultatet ska visas.</span><span class="sxs-lookup"><span data-stu-id="8a0e7-129">Use Groupings to determine how the results should be displayed.</span></span>  
    * <span data-ttu-id="8a0e7-130">Du kan till exempel gruppera resultaten först efter kön och sedan efter ålder.</span><span class="sxs-lookup"><span data-stu-id="8a0e7-130">For example, group the results first by gender, then by age.</span></span>  
13. <span data-ttu-id="8a0e7-131">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="8a0e7-131">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="8a0e7-132">Flytta grupperingarna till vald sida och placera dem i önskad ordning.</span><span class="sxs-lookup"><span data-stu-id="8a0e7-132">Move the groupings into the Selected side and place them in the desired order.</span></span>  

## <a name="execute-the-statistics-calculation"></a><span data-ttu-id="8a0e7-133">Utför statistikberäkningen</span><span class="sxs-lookup"><span data-stu-id="8a0e7-133">Execute the statistics calculation</span></span>
1. <span data-ttu-id="8a0e7-134">Klicka på Kör.</span><span class="sxs-lookup"><span data-stu-id="8a0e7-134">Click Execute.</span></span>
    * <span data-ttu-id="8a0e7-135">Välj vilken beräkningsfunktion som du vill utföra på resultaten.</span><span class="sxs-lookup"><span data-stu-id="8a0e7-135">Select which calculation function you would like to perform on the results.</span></span>  
    * <span data-ttu-id="8a0e7-136">Beräkna till exempel genomsnittsprocent för enkäten för de valda grupperingarna eller summera poängen över resultatgrupper för de valda grupperingarna.</span><span class="sxs-lookup"><span data-stu-id="8a0e7-136">For example, calculate the average percentages across the questionnaire for the selected groupings or total the points across the result groups for the selected groupings.</span></span>  
2. <span data-ttu-id="8a0e7-137">Markera eller avmarkera kryssrutan Radera tidigare sökningar.</span><span class="sxs-lookup"><span data-stu-id="8a0e7-137">Select or clear the Delete previous searches check box.</span></span>
3. <span data-ttu-id="8a0e7-138">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="8a0e7-138">Click OK.</span></span>

## <a name="view-the-results-of-the-questionnaire-statistics-run"></a><span data-ttu-id="8a0e7-139">Visa resultaten av enkätstatistikkörningen.</span><span class="sxs-lookup"><span data-stu-id="8a0e7-139">View the results of the questionnaire statistics run.</span></span>
1. <span data-ttu-id="8a0e7-140">Klicka på Resultat.</span><span class="sxs-lookup"><span data-stu-id="8a0e7-140">Click Result.</span></span>
2. <span data-ttu-id="8a0e7-141">Klicka på Resultat.</span><span class="sxs-lookup"><span data-stu-id="8a0e7-141">Click Result.</span></span>
3. <span data-ttu-id="8a0e7-142">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="8a0e7-142">Close the page.</span></span>


