--- 
title: "Kör formatet för att utföra inventering och summering för elektronisk rapportering (ER)"
description: "I följande steg beskrivs hur en användare som tilldelats en roll som systemadministratör eller utvecklare för elektronisk rapportering kan konfigurera ett format för elektronisk rapportering (ER) att utföra inventering och summering baserat på data tillhörande redan genererad textutmatning."
author: NickSelin
manager: AnnBe
ms.date: 10/28/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 60a34e35a376635669b764457617cb997822bdcd
ms.contentlocale: sv-se
ms.lasthandoff: 08/29/2017

---
# <a name="run-the-format-to-do-counting-and-summing-for-electronic-reporting-er"></a><span data-ttu-id="73769-103">Kör formatet för att utföra inventering och summering för elektronisk rapportering (ER)</span><span class="sxs-lookup"><span data-stu-id="73769-103">Run the format to do counting and summing for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="73769-104">I följande steg beskrivs hur en användare som tilldelats en roll som systemadministratör eller utvecklare för elektronisk rapportering kan konfigurera ett format för elektronisk rapportering (ER) att utföra inventering och summering baserat på data tillhörande redan genererad textutmatning.</span><span class="sxs-lookup"><span data-stu-id="73769-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to do counting and summing based on data of the already generated text output.</span></span> <span data-ttu-id="73769-105">Dessa steg kan utföras i DEMF-företaget.</span><span class="sxs-lookup"><span data-stu-id="73769-105">These steps can be performed in the DEMF company.</span></span>

<span data-ttu-id="73769-106">För att slutföra dessa steg måste du först avsluta stegen i proceduren ”ER Configure format to do counting and summing (Part 3: Use computations to make the output)".</span><span class="sxs-lookup"><span data-stu-id="73769-106">To complete these steps, you must first complete the steps in the “ER Configure format to do counting and summing (Part 3: Use computations to make the output)” procedure.</span></span>

<span data-ttu-id="73769-107">Denna procedur är avsedd för en funktion som lades till i Dynamics 365 for Operations version 1611.</span><span class="sxs-lookup"><span data-stu-id="73769-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="test-this-configuration-for-generation-of-the-intrastat-reports"></a><span data-ttu-id="73769-108">Testa denna konfiguration för att generera Intrastat-rapporterna</span><span class="sxs-lookup"><span data-stu-id="73769-108">Test this configuration for generation of the Intrastat reports</span></span>
1. <span data-ttu-id="73769-109">Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="73769-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="73769-110">Klicka på Reporting configurations.</span><span class="sxs-lookup"><span data-stu-id="73769-110">Click Reporting configurations.</span></span>
3. <span data-ttu-id="73769-111">Expandera "Intrastat model" i trädet.</span><span class="sxs-lookup"><span data-stu-id="73769-111">In the tree, expand 'Intrastat model'.</span></span>
4. <span data-ttu-id="73769-112">Expandera "Intrastat model\Intrastat (DE)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="73769-112">In the tree, expand 'Intrastat model\Intrastat (DE)'.</span></span>
5. <span data-ttu-id="73769-113">Välj "Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing" i trädet.</span><span class="sxs-lookup"><span data-stu-id="73769-113">In the tree, select 'Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing'.</span></span>
6. <span data-ttu-id="73769-114">Klicka på Configurations i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="73769-114">On the Action Pane, click Configurations.</span></span>
7. <span data-ttu-id="73769-115">Klicka på User parameters.</span><span class="sxs-lookup"><span data-stu-id="73769-115">Click User parameters.</span></span>
8. <span data-ttu-id="73769-116">Välj Yes i fältet Run settings.</span><span class="sxs-lookup"><span data-stu-id="73769-116">Select Yes in the Run settings field.</span></span>
9. <span data-ttu-id="73769-117">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="73769-117">Click OK.</span></span>
10. <span data-ttu-id="73769-118">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="73769-118">Click Edit.</span></span>
11. <span data-ttu-id="73769-119">Välj Yes i fältet Run Draft.</span><span class="sxs-lookup"><span data-stu-id="73769-119">Select Yes in the Run Draft field.</span></span>
12. <span data-ttu-id="73769-120">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="73769-120">Click Save.</span></span>
13. <span data-ttu-id="73769-121">Gå till Moms > Inställningar > Utländsk handel > Utländska handelsparametrar.</span><span class="sxs-lookup"><span data-stu-id="73769-121">Go to Tax > Setup > Foreign trade > Foreign trade parameters.</span></span>
14. <span data-ttu-id="73769-122">Expandera avsnittet Elektronisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="73769-122">Expand the Electronic reporting section.</span></span>
15. <span data-ttu-id="73769-123">Välj konfigurationen "Intrastat (DE) with counting & summing".</span><span class="sxs-lookup"><span data-stu-id="73769-123">Select the “Intrastat (DE) with counting & summing” configuration.</span></span>
16. <span data-ttu-id="73769-124">Välj konfigurationen "Intrastat (DE) with counting & summing".</span><span class="sxs-lookup"><span data-stu-id="73769-124">Select the “Intrastat (DE) with counting & summing” configuration.</span></span>
17. <span data-ttu-id="73769-125">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="73769-125">Click Save.</span></span>
18. <span data-ttu-id="73769-126">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="73769-126">Close the page.</span></span>
19. <span data-ttu-id="73769-127">Gå till Moms > Deklarationer > Utländsk handel > Intrastat.</span><span class="sxs-lookup"><span data-stu-id="73769-127">Go to Tax > Declarations > Foreign trade > Intrastat.</span></span>
20. <span data-ttu-id="73769-128">Klicka på Utdata.</span><span class="sxs-lookup"><span data-stu-id="73769-128">Click Output.</span></span>
21. <span data-ttu-id="73769-129">Klicka på Rapport.</span><span class="sxs-lookup"><span data-stu-id="73769-129">Click Report.</span></span>
    * <span data-ttu-id="73769-130">Kör rapportgenereringsprocessen för Intrastat.</span><span class="sxs-lookup"><span data-stu-id="73769-130">Run the Intrastat report generation process.</span></span>  
22. <span data-ttu-id="73769-131">Ange datumet till "2000-01-01" i fältet Från datum.</span><span class="sxs-lookup"><span data-stu-id="73769-131">In the From date field, set the date to '2000-01-01'.</span></span>
    * <span data-ttu-id="73769-132">Definiera start- och slutdatum för den rapporteringsperiod som innehåller befintliga formulärtransaktioner.</span><span class="sxs-lookup"><span data-stu-id="73769-132">Define start and end dates for the reporting period that include the existing on the form transactions.</span></span>  
23. <span data-ttu-id="73769-133">Ange datumet till "2022-12-31" i fältet Till datum.</span><span class="sxs-lookup"><span data-stu-id="73769-133">In the To date field, set the date to '2022-12-31'.</span></span>
    * <span data-ttu-id="73769-134">Definiera start- och slutdatum för den rapporteringsperiod som innehåller befintliga formulärtransaktioner.</span><span class="sxs-lookup"><span data-stu-id="73769-134">Define start and end dates for the reporting period that include the existing on the form transactions.</span></span>  
24. <span data-ttu-id="73769-135">Välj "Arrivals" i fältet Directions.</span><span class="sxs-lookup"><span data-stu-id="73769-135">In the Direction field, select 'Arrivals'.</span></span>
25. <span data-ttu-id="73769-136">Välj Ja i fältet Generera fil.</span><span class="sxs-lookup"><span data-stu-id="73769-136">Select Yes in the Generate file field.</span></span>
26. <span data-ttu-id="73769-137">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="73769-137">Click OK.</span></span>
    * <span data-ttu-id="73769-138">Granska den skapade utleveransen med sammanfattningsraderna i slutet.</span><span class="sxs-lookup"><span data-stu-id="73769-138">Review the created output with the summary lines in the end.</span></span>  
27. <span data-ttu-id="73769-139">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="73769-139">Click New.</span></span>
28. <span data-ttu-id="73769-140">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="73769-140">In the list, mark the selected row.</span></span>
29. <span data-ttu-id="73769-141">Välj "Dispatches" i fältet Direction.</span><span class="sxs-lookup"><span data-stu-id="73769-141">In the Direction field, select 'Dispatches'.</span></span>
30. <span data-ttu-id="73769-142">Ange eller välj ett värde i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="73769-142">In the Item number field, enter or select a value.</span></span>
31. <span data-ttu-id="73769-143">Ange eller välj ett värde i fältet Artikel.</span><span class="sxs-lookup"><span data-stu-id="73769-143">In the Commodity field, enter or select a value.</span></span>
32. <span data-ttu-id="73769-144">Ange Weight som "10".</span><span class="sxs-lookup"><span data-stu-id="73769-144">Set Weight to '10'.</span></span>
33. <span data-ttu-id="73769-145">Ange Invoice amount som "10000".</span><span class="sxs-lookup"><span data-stu-id="73769-145">Set Invoice amount to '10000'.</span></span>
34. <span data-ttu-id="73769-146">Ange Statistical amount som "10000".</span><span class="sxs-lookup"><span data-stu-id="73769-146">Set Statistical amount to '10000'.</span></span>
35. <span data-ttu-id="73769-147">Klicka på Utdata.</span><span class="sxs-lookup"><span data-stu-id="73769-147">Click Output.</span></span>
36. <span data-ttu-id="73769-148">Klicka på Rapport.</span><span class="sxs-lookup"><span data-stu-id="73769-148">Click Report.</span></span>
37. <span data-ttu-id="73769-149">Välj "Dispatches" i fältet Direction.</span><span class="sxs-lookup"><span data-stu-id="73769-149">In the Direction field, select 'Dispatches'.</span></span>
38. <span data-ttu-id="73769-150">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="73769-150">Click OK.</span></span>
    * <span data-ttu-id="73769-151">Granska den skapade utleveransen med sammanfattningsraderna i slutet.</span><span class="sxs-lookup"><span data-stu-id="73769-151">Review the created output with the summary lines in the end.</span></span> <span data-ttu-id="73769-152">Observera att den har ändrats i jämförelse med den första körningen.</span><span class="sxs-lookup"><span data-stu-id="73769-152">Note that it has been changed in comparison to the first run.</span></span>  

## <a name="run-this-configuration-in-debug-mode-to-review-the-collected-counting--summing-data"></a><span data-ttu-id="73769-153">Kör denna konfiguration i felsökningsläge för att granska insamlade inventerings- och summeringsdata</span><span class="sxs-lookup"><span data-stu-id="73769-153">Run this configuration in debug mode to review the collected counting & summing data</span></span>
1. <span data-ttu-id="73769-154">Gå till Organisationsadministration > Elektronisk rapportering > Konfigurationer.</span><span class="sxs-lookup"><span data-stu-id="73769-154">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="73769-155">Expandera "Intrastat model" i trädet.</span><span class="sxs-lookup"><span data-stu-id="73769-155">In the tree, expand 'Intrastat model'.</span></span>
3. <span data-ttu-id="73769-156">Expandera "Intrastat model\Intrastat (DE)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="73769-156">In the tree, expand 'Intrastat model\Intrastat (DE)'.</span></span>
4. <span data-ttu-id="73769-157">Välj "Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing" i trädet.</span><span class="sxs-lookup"><span data-stu-id="73769-157">In the tree, select 'Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing'.</span></span>
5. <span data-ttu-id="73769-158">Klicka på Configurations i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="73769-158">On the Action Pane, click Configurations.</span></span>
6. <span data-ttu-id="73769-159">Klicka på User parameters.</span><span class="sxs-lookup"><span data-stu-id="73769-159">Click User parameters.</span></span>
7. <span data-ttu-id="73769-160">Välj Yes i fältet Run in debug mode.</span><span class="sxs-lookup"><span data-stu-id="73769-160">Select Yes in the Run in debug mode field.</span></span>
8. <span data-ttu-id="73769-161">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="73769-161">Click OK.</span></span>
9. <span data-ttu-id="73769-162">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="73769-162">Close the page.</span></span>
10. <span data-ttu-id="73769-163">Gå till Moms > Deklarationer > Utländsk handel > Intrastat.</span><span class="sxs-lookup"><span data-stu-id="73769-163">Go to Tax > Declarations > Foreign trade > Intrastat.</span></span>
11. <span data-ttu-id="73769-164">Klicka på Utdata.</span><span class="sxs-lookup"><span data-stu-id="73769-164">Click Output.</span></span>
12. <span data-ttu-id="73769-165">Klicka på Rapport.</span><span class="sxs-lookup"><span data-stu-id="73769-165">Click Report.</span></span>
13. <span data-ttu-id="73769-166">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="73769-166">Click OK.</span></span>
14. <span data-ttu-id="73769-167">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="73769-167">Close the page.</span></span>
15. <span data-ttu-id="73769-168">Gå till Organisationsadministration > Elektronisk rapportering > Konfigurationer.</span><span class="sxs-lookup"><span data-stu-id="73769-168">Go to Organization administration > Electronic reporting > Configurations.</span></span>
16. <span data-ttu-id="73769-169">Expandera "Intrastat model" i trädet.</span><span class="sxs-lookup"><span data-stu-id="73769-169">In the tree, expand 'Intrastat model'.</span></span>
17. <span data-ttu-id="73769-170">Expandera "Intrastat model\Intrastat (DE)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="73769-170">In the tree, expand 'Intrastat model\Intrastat (DE)'.</span></span>
18. <span data-ttu-id="73769-171">Välj "Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing" i trädet.</span><span class="sxs-lookup"><span data-stu-id="73769-171">In the tree, select 'Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing'.</span></span>
19. <span data-ttu-id="73769-172">Klicka på Debug logs.</span><span class="sxs-lookup"><span data-stu-id="73769-172">Click Debug logs.</span></span>
    * <span data-ttu-id="73769-173">Observera att en post för loggfelsökning har skapats för utförandeprocessen för den valda konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="73769-173">Note that a debug log record has been created for the execution process of the selected configuration.</span></span>  
20. <span data-ttu-id="73769-174">Klicka på Koppla.</span><span class="sxs-lookup"><span data-stu-id="73769-174">Click Attach.</span></span>
21. <span data-ttu-id="73769-175">Klicka på Öppna.</span><span class="sxs-lookup"><span data-stu-id="73769-175">Click Open.</span></span>
    * <span data-ttu-id="73769-176">Förhandsvisa den skapade XML-filen som innehåller inventerings- och summeringsinformation som samlades in i samband med körningen av den valda konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="73769-176">Review the created XML file that contains counting and summing details that were collected during the execution of the selected configuration.</span></span>  


