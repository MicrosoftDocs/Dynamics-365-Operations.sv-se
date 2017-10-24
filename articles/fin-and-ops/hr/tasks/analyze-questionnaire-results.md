--- 
title: "Analysera enkätresultat"
description: "Enkätstatistiken kan användas för att beräkna medelvärde, summor och procentsatser som baseras på en uppsättning demografiska data."
author: ShielaSogge
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Operations
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: c243a84b63215ab44e2929c64dbc4aced7061474
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="analyze-questionnaire-results"></a><span data-ttu-id="8344e-103">Analysera enkätresultat</span><span class="sxs-lookup"><span data-stu-id="8344e-103">Analyze questionnaire results</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8344e-104">Enkätstatistiken kan användas för att beräkna medelvärde, summor och procentsatser som baseras på en uppsättning demografiska data.</span><span class="sxs-lookup"><span data-stu-id="8344e-104">Questionnaire statistics can be used to calculate averages, totals, and percentages based on a set of demographic data.</span></span> <span data-ttu-id="8344e-105">Gå till Enkät > Visa och analysera resultat > Enkätstatistik om du vill starta proceduren.</span><span class="sxs-lookup"><span data-stu-id="8344e-105">To begin this procedure, go to Questionnaire > View and analyze results > Questionnaire statistics.</span></span> <span data-ttu-id="8344e-106">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="8344e-106">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-a-questionnaire-statistics-record"></a><span data-ttu-id="8344e-107">Skapa en enkätstatistikpost</span><span class="sxs-lookup"><span data-stu-id="8344e-107">Create a Questionnaire statistics record</span></span>
1. <span data-ttu-id="8344e-108">Gå till Enkätsstatistik.</span><span class="sxs-lookup"><span data-stu-id="8344e-108">Go to Questionnaire statistics.</span></span>
2. <span data-ttu-id="8344e-109">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="8344e-109">Click New.</span></span>
3. <span data-ttu-id="8344e-110">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="8344e-110">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="8344e-111">Skriv ett värde i fältet Statistik.</span><span class="sxs-lookup"><span data-stu-id="8344e-111">In the Statistics field, type a value.</span></span>
5. <span data-ttu-id="8344e-112">Skriv ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="8344e-112">In the Description field, type a value.</span></span>
6. <span data-ttu-id="8344e-113">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Enkät.</span><span class="sxs-lookup"><span data-stu-id="8344e-113">In the Questionnaire field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="8344e-114">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="8344e-114">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="8344e-115">Klicka på fliken Allmänt.</span><span class="sxs-lookup"><span data-stu-id="8344e-115">Click the General tab.</span></span>
    * <span data-ttu-id="8344e-116">Välj om du vill inkludera anonyma resultat eller resultat från arbetare, kontakter och sökande.</span><span class="sxs-lookup"><span data-stu-id="8344e-116">Select if you want to include anonymous results or results from workers, contacts, and applicants.</span></span>  
9. <span data-ttu-id="8344e-117">Markera eller avmarkera kryssrutan Arbetare.</span><span class="sxs-lookup"><span data-stu-id="8344e-117">Select or clear the Worker check box.</span></span>
    * <span data-ttu-id="8344e-118">Om du ska visa resultaten efter tjänsteålder eller ålder, anger du de intervall som du vill använda för att gruppera resultatet.</span><span class="sxs-lookup"><span data-stu-id="8344e-118">If you will be viewing the results by seniority or age, specify the intervals that you would like to use for grouping the results.</span></span>  
    * <span data-ttu-id="8344e-119">Om du anger 5 för åldersintervallet grupperas resultaten baserat på femårsintervall.</span><span class="sxs-lookup"><span data-stu-id="8344e-119">Entering a 5 for the age interval will group the results based on five-year age intervals.</span></span>  
10. <span data-ttu-id="8344e-120">Ange ett nummer i fältet Ålder.</span><span class="sxs-lookup"><span data-stu-id="8344e-120">In the Age field, enter a number.</span></span>
    * <span data-ttu-id="8344e-121">Välj om du vill köra beräkningen mot hela enkäten, för varje resultatgrupp, för varje fråga eller för varje frågerad.</span><span class="sxs-lookup"><span data-stu-id="8344e-121">Select if you want to run the calculation against the entire questionnaire, for each result group, for each question, or for each question row.</span></span>  
    * <span data-ttu-id="8344e-122">Välj hur du vill gruppera resultaten.</span><span class="sxs-lookup"><span data-stu-id="8344e-122">Select how you would like to group the results.</span></span>  
    * <span data-ttu-id="8344e-123">Om du till exempel beräknar medelpoäng per fråga kanske du vill se frågorna grupperade efter resultatgrupp.</span><span class="sxs-lookup"><span data-stu-id="8344e-123">For example, if you calculate the average points per question, you may want to see the questions grouped by Result group.</span></span>  
    * <span data-ttu-id="8344e-124">Välj de data som beräkningen ska baseras på.</span><span class="sxs-lookup"><span data-stu-id="8344e-124">Select the data to base the calculation on.</span></span>  
    * <span data-ttu-id="8344e-125">Om du till exempel vill se den genomsnittsprocent som har tagits emot i enkäten hos dina arbetare kontra det genomsnittliga antal poäng som har tagits emot hos dina arbetare.</span><span class="sxs-lookup"><span data-stu-id="8344e-125">For example, if you want to see the average percent received on the questionnaire across your workers versus the average number of points achieved across your workers.</span></span>  
11. <span data-ttu-id="8344e-126">Klicka på fliken Intervall.</span><span class="sxs-lookup"><span data-stu-id="8344e-126">Click the Range tab.</span></span>
    * <span data-ttu-id="8344e-127">Använd intervall för att begränsa resultatuppsättningen till endast de som uppfyller intervallkriterierna.</span><span class="sxs-lookup"><span data-stu-id="8344e-127">Use ranges to limit your result set to only those meeting the Range criteria.</span></span>  
12. <span data-ttu-id="8344e-128">Klicka på fliken Gruppera efter.</span><span class="sxs-lookup"><span data-stu-id="8344e-128">Click the Grouping by tab.</span></span>
    * <span data-ttu-id="8344e-129">Använd grupperingarna för att ange hur resultatet ska visas.</span><span class="sxs-lookup"><span data-stu-id="8344e-129">Use Groupings to determine how the results should be displayed.</span></span>  
    * <span data-ttu-id="8344e-130">Du kan till exempel gruppera resultaten först efter kön och sedan efter ålder.</span><span class="sxs-lookup"><span data-stu-id="8344e-130">For example, group the results first by gender, then by age.</span></span>  
13. <span data-ttu-id="8344e-131">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="8344e-131">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="8344e-132">Flytta grupperingarna till vald sida och placera dem i önskad ordning.</span><span class="sxs-lookup"><span data-stu-id="8344e-132">Move the groupings into the Selected side and place them in the desired order.</span></span>  

## <a name="execute-the-statistics-calculation"></a><span data-ttu-id="8344e-133">Utför statistikberäkningen</span><span class="sxs-lookup"><span data-stu-id="8344e-133">Execute the statistics calculation</span></span>
1. <span data-ttu-id="8344e-134">Klicka på Kör.</span><span class="sxs-lookup"><span data-stu-id="8344e-134">Click Execute.</span></span>
    * <span data-ttu-id="8344e-135">Välj vilken beräkningsfunktion som du vill utföra på resultaten.</span><span class="sxs-lookup"><span data-stu-id="8344e-135">Select which calculation function you would like to perform on the results.</span></span>  
    * <span data-ttu-id="8344e-136">Beräkna till exempel genomsnittsprocent för enkäten för de valda grupperingarna eller summera poängen över resultatgrupper för de valda grupperingarna.</span><span class="sxs-lookup"><span data-stu-id="8344e-136">For example, calculate the average percentages across the questionnaire for the selected groupings or total the points across the result groups for the selected groupings.</span></span>  
2. <span data-ttu-id="8344e-137">Markera eller avmarkera kryssrutan Radera tidigare sökningar.</span><span class="sxs-lookup"><span data-stu-id="8344e-137">Select or clear the Delete previous searches check box.</span></span>
3. <span data-ttu-id="8344e-138">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="8344e-138">Click OK.</span></span>

## <a name="view-the-results-of-the-questionnaire-statistics-run"></a><span data-ttu-id="8344e-139">Visa resultaten av enkätstatistikkörningen.</span><span class="sxs-lookup"><span data-stu-id="8344e-139">View the results of the questionnaire statistics run.</span></span>
1. <span data-ttu-id="8344e-140">Klicka på Resultat.</span><span class="sxs-lookup"><span data-stu-id="8344e-140">Click Result.</span></span>
2. <span data-ttu-id="8344e-141">Klicka på Resultat.</span><span class="sxs-lookup"><span data-stu-id="8344e-141">Click Result.</span></span>
3. <span data-ttu-id="8344e-142">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="8344e-142">Close the page.</span></span>


