---
title: ER Konfigurera format för inventering och summering (Del 4 - Köra format)
description: I följande steg beskrivs hur en användare som tilldelats en roll som systemadministratör eller utvecklare för elektronisk rapportering kan konfigurera ett format för elektronisk rapportering (ER) att utföra inventering och summering baserat på data tillhörande redan skapad textutmatning.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, IntrastatParameters, Intrastat, InventItemIdLookupSimple, IntrastatCommodityLookup, ERFormatMappingRunLogTable, DocuView
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f0a80e5b1a79c874ce0a8d24c85be71d0dc5c9c8
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/03/2019
ms.locfileid: "2550566"
---
# <a name="er-configure-format-to-do-counting-and-summing-part-4---run-format"></a><span data-ttu-id="9b5b0-103">ER Konfigurera format för inventering och summering (Del 4 - Köra format)</span><span class="sxs-lookup"><span data-stu-id="9b5b0-103">ER Configure format to do counting and summing (Part 4 - Run format)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="9b5b0-104">I följande steg beskrivs hur en användare som tilldelats en roll som systemadministratör eller utvecklare för elektronisk rapportering kan konfigurera ett format för elektronisk rapportering (ER) att utföra inventering och summering baserat på data tillhörande redan skapad textutmatning.</span><span class="sxs-lookup"><span data-stu-id="9b5b0-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to do counting and summing based on data of the already generated text output.</span></span> <span data-ttu-id="9b5b0-105">Dessa steg kan utföras i DEMF-företaget.</span><span class="sxs-lookup"><span data-stu-id="9b5b0-105">These steps can be performed in the DEMF company.</span></span>

<span data-ttu-id="9b5b0-106">För att slutföra dessa steg måste du först avsluta stegen i proceduren ”ER Configure format to do counting and summing (Part 3: Use computations to make the output)".</span><span class="sxs-lookup"><span data-stu-id="9b5b0-106">To complete these steps, you must first complete the steps in the “ER Configure format to do counting and summing (Part 3: Use computations to make the output)” procedure.</span></span>

<span data-ttu-id="9b5b0-107">Denna procedur är avsedd för en funktion som lades till i Dynamics 365 for Operations version 1611.</span><span class="sxs-lookup"><span data-stu-id="9b5b0-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="test-this-configuration-for-generation-of-the-intrastat-reports"></a><span data-ttu-id="9b5b0-108">Testa denna konfiguration för att skapa Intrastat-rapporterna</span><span class="sxs-lookup"><span data-stu-id="9b5b0-108">Test this configuration for generation of the Intrastat reports</span></span>
1. <span data-ttu-id="9b5b0-109">Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="9b5b0-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="9b5b0-110">Klicka på Reporting configurations.</span><span class="sxs-lookup"><span data-stu-id="9b5b0-110">Click Reporting configurations.</span></span>
3. <span data-ttu-id="9b5b0-111">Expandera "Intrastat model" i trädet.</span><span class="sxs-lookup"><span data-stu-id="9b5b0-111">In the tree, expand 'Intrastat model'.</span></span>
4. <span data-ttu-id="9b5b0-112">Expandera "Intrastat model\Intrastat (DE)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="9b5b0-112">In the tree, expand 'Intrastat model\Intrastat (DE)'.</span></span>
5. <span data-ttu-id="9b5b0-113">Välj "Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing" i trädet.</span><span class="sxs-lookup"><span data-stu-id="9b5b0-113">In the tree, select 'Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing'.</span></span>
6. <span data-ttu-id="9b5b0-114">Klicka på Configurations i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="9b5b0-114">On the Action Pane, click Configurations.</span></span>
7. <span data-ttu-id="9b5b0-115">Klicka på User parameters.</span><span class="sxs-lookup"><span data-stu-id="9b5b0-115">Click User parameters.</span></span>
8. <span data-ttu-id="9b5b0-116">Välj Yes i fältet Run settings.</span><span class="sxs-lookup"><span data-stu-id="9b5b0-116">Select Yes in the Run settings field.</span></span>
9. <span data-ttu-id="9b5b0-117">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="9b5b0-117">Click OK.</span></span>
10. <span data-ttu-id="9b5b0-118">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="9b5b0-118">Click Edit.</span></span>
11. <span data-ttu-id="9b5b0-119">Välj Yes i fältet Run Draft.</span><span class="sxs-lookup"><span data-stu-id="9b5b0-119">Select Yes in the Run Draft field.</span></span>
12. <span data-ttu-id="9b5b0-120">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="9b5b0-120">Click Save.</span></span>
13. <span data-ttu-id="9b5b0-121">Gå till Skatt > Inställningar > Utländsk handel > Utländska handelsparametrar.</span><span class="sxs-lookup"><span data-stu-id="9b5b0-121">Go to Tax > Setup > Foreign trade > Foreign trade parameters.</span></span>
14. <span data-ttu-id="9b5b0-122">Expandera avsnittet Elektronisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="9b5b0-122">Expand the Electronic reporting section.</span></span>
15. <span data-ttu-id="9b5b0-123">Välj konfigurationen "Intrastat (DE) with counting & summing".</span><span class="sxs-lookup"><span data-stu-id="9b5b0-123">Select the “Intrastat (DE) with counting & summing” configuration.</span></span>
16. <span data-ttu-id="9b5b0-124">Välj konfigurationen "Intrastat (DE) with counting & summing".</span><span class="sxs-lookup"><span data-stu-id="9b5b0-124">Select the “Intrastat (DE) with counting & summing” configuration.</span></span>
17. <span data-ttu-id="9b5b0-125">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="9b5b0-125">Click Save.</span></span>
18. <span data-ttu-id="9b5b0-126">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="9b5b0-126">Close the page.</span></span>
19. <span data-ttu-id="9b5b0-127">Gå till Skatt > Deklarationer > Utländsk handel > Intrastat.</span><span class="sxs-lookup"><span data-stu-id="9b5b0-127">Go to Tax > Declarations > Foreign trade > Intrastat.</span></span>
20. <span data-ttu-id="9b5b0-128">Klicka på Utdata.</span><span class="sxs-lookup"><span data-stu-id="9b5b0-128">Click Output.</span></span>
21. <span data-ttu-id="9b5b0-129">Klicka på Rapport.</span><span class="sxs-lookup"><span data-stu-id="9b5b0-129">Click Report.</span></span>
    * <span data-ttu-id="9b5b0-130">Kör rapportgenereringsprocessen för Intrastat.</span><span class="sxs-lookup"><span data-stu-id="9b5b0-130">Run the Intrastat report generation process.</span></span>  
22. <span data-ttu-id="9b5b0-131">Ange datumet till "2000-01-01" i fältet Från datum.</span><span class="sxs-lookup"><span data-stu-id="9b5b0-131">In the From date field, set the date to '2000-01-01'.</span></span>
    * <span data-ttu-id="9b5b0-132">Definiera start- och slutdatum för den rapporteringsperiod som innehåller befintliga formulärtransaktioner.</span><span class="sxs-lookup"><span data-stu-id="9b5b0-132">Define start and end dates for the reporting period that include the existing on the form transactions.</span></span>  
23. <span data-ttu-id="9b5b0-133">Ange datumet till "2022-12-31" i fältet Till datum.</span><span class="sxs-lookup"><span data-stu-id="9b5b0-133">In the To date field, set the date to '2022-12-31'.</span></span>
    * <span data-ttu-id="9b5b0-134">Definiera start- och slutdatum för den rapporteringsperiod som innehåller befintliga formulärtransaktioner.</span><span class="sxs-lookup"><span data-stu-id="9b5b0-134">Define start and end dates for the reporting period that include the existing on the form transactions.</span></span>  
24. <span data-ttu-id="9b5b0-135">Välj "Arrivals" i fältet Directions.</span><span class="sxs-lookup"><span data-stu-id="9b5b0-135">In the Direction field, select 'Arrivals'.</span></span>
25. <span data-ttu-id="9b5b0-136">Välj Ja i fältet Skapa fil.</span><span class="sxs-lookup"><span data-stu-id="9b5b0-136">Select Yes in the Generate file field.</span></span>
26. <span data-ttu-id="9b5b0-137">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="9b5b0-137">Click OK.</span></span>
    * <span data-ttu-id="9b5b0-138">Granska den skapade utleveransen med sammanfattningsraderna i slutet.</span><span class="sxs-lookup"><span data-stu-id="9b5b0-138">Review the created output with the summary lines in the end.</span></span>  
27. <span data-ttu-id="9b5b0-139">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="9b5b0-139">Click New.</span></span>
28. <span data-ttu-id="9b5b0-140">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="9b5b0-140">In the list, mark the selected row.</span></span>
29. <span data-ttu-id="9b5b0-141">Välj "Dispatches" i fältet Direction.</span><span class="sxs-lookup"><span data-stu-id="9b5b0-141">In the Direction field, select 'Dispatches'.</span></span>
30. <span data-ttu-id="9b5b0-142">Ange eller välj ett värde i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="9b5b0-142">In the Item number field, enter or select a value.</span></span>
31. <span data-ttu-id="9b5b0-143">Ange eller välj ett värde i fältet Artikel.</span><span class="sxs-lookup"><span data-stu-id="9b5b0-143">In the Commodity field, enter or select a value.</span></span>
32. <span data-ttu-id="9b5b0-144">Ange Weight som "10".</span><span class="sxs-lookup"><span data-stu-id="9b5b0-144">Set Weight to '10'.</span></span>
33. <span data-ttu-id="9b5b0-145">Ange Invoice amount som "10000".</span><span class="sxs-lookup"><span data-stu-id="9b5b0-145">Set Invoice amount to '10000'.</span></span>
34. <span data-ttu-id="9b5b0-146">Ange Statistical amount som "10000".</span><span class="sxs-lookup"><span data-stu-id="9b5b0-146">Set Statistical amount to '10000'.</span></span>
35. <span data-ttu-id="9b5b0-147">Klicka på Utdata.</span><span class="sxs-lookup"><span data-stu-id="9b5b0-147">Click Output.</span></span>
36. <span data-ttu-id="9b5b0-148">Klicka på Rapport.</span><span class="sxs-lookup"><span data-stu-id="9b5b0-148">Click Report.</span></span>
37. <span data-ttu-id="9b5b0-149">Välj "Dispatches" i fältet Direction.</span><span class="sxs-lookup"><span data-stu-id="9b5b0-149">In the Direction field, select 'Dispatches'.</span></span>
38. <span data-ttu-id="9b5b0-150">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="9b5b0-150">Click OK.</span></span>
    * <span data-ttu-id="9b5b0-151">Granska den skapade utleveransen med sammanfattningsraderna i slutet.</span><span class="sxs-lookup"><span data-stu-id="9b5b0-151">Review the created output with the summary lines in the end.</span></span> <span data-ttu-id="9b5b0-152">Observera att den har ändrats i jämförelse med den första körningen.</span><span class="sxs-lookup"><span data-stu-id="9b5b0-152">Note that it has been changed in comparison to the first run.</span></span>  

## <a name="run-this-configuration-in-debug-mode-to-review-the-collected-counting--summing-data"></a><span data-ttu-id="9b5b0-153">Kör denna konfiguration i felsökningsläge för att granska insamlade inventerings- och summeringsdata</span><span class="sxs-lookup"><span data-stu-id="9b5b0-153">Run this configuration in debug mode to review the collected counting & summing data</span></span>
1. <span data-ttu-id="9b5b0-154">Gå till Organisationsadministration > Elektronisk rapportering > Konfigurationer.</span><span class="sxs-lookup"><span data-stu-id="9b5b0-154">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="9b5b0-155">Expandera "Intrastat model" i trädet.</span><span class="sxs-lookup"><span data-stu-id="9b5b0-155">In the tree, expand 'Intrastat model'.</span></span>
3. <span data-ttu-id="9b5b0-156">Expandera "Intrastat model\Intrastat (DE)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="9b5b0-156">In the tree, expand 'Intrastat model\Intrastat (DE)'.</span></span>
4. <span data-ttu-id="9b5b0-157">Välj "Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing" i trädet.</span><span class="sxs-lookup"><span data-stu-id="9b5b0-157">In the tree, select 'Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing'.</span></span>
5. <span data-ttu-id="9b5b0-158">Klicka på Configurations i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="9b5b0-158">On the Action Pane, click Configurations.</span></span>
6. <span data-ttu-id="9b5b0-159">Klicka på User parameters.</span><span class="sxs-lookup"><span data-stu-id="9b5b0-159">Click User parameters.</span></span>
7. <span data-ttu-id="9b5b0-160">Välj Yes i fältet Run in debug mode.</span><span class="sxs-lookup"><span data-stu-id="9b5b0-160">Select Yes in the Run in debug mode field.</span></span>
8. <span data-ttu-id="9b5b0-161">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="9b5b0-161">Click OK.</span></span>
9. <span data-ttu-id="9b5b0-162">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="9b5b0-162">Close the page.</span></span>
10. <span data-ttu-id="9b5b0-163">Gå till Skatt > Deklarationer > Utländsk handel > Intrastat.</span><span class="sxs-lookup"><span data-stu-id="9b5b0-163">Go to Tax > Declarations > Foreign trade > Intrastat.</span></span>
11. <span data-ttu-id="9b5b0-164">Klicka på Utdata.</span><span class="sxs-lookup"><span data-stu-id="9b5b0-164">Click Output.</span></span>
12. <span data-ttu-id="9b5b0-165">Klicka på Rapport.</span><span class="sxs-lookup"><span data-stu-id="9b5b0-165">Click Report.</span></span>
13. <span data-ttu-id="9b5b0-166">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="9b5b0-166">Click OK.</span></span>
14. <span data-ttu-id="9b5b0-167">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="9b5b0-167">Close the page.</span></span>
15. <span data-ttu-id="9b5b0-168">Gå till Organisationsadministration > Elektronisk rapportering > Konfigurationer.</span><span class="sxs-lookup"><span data-stu-id="9b5b0-168">Go to Organization administration > Electronic reporting > Configurations.</span></span>
16. <span data-ttu-id="9b5b0-169">Expandera "Intrastat model" i trädet.</span><span class="sxs-lookup"><span data-stu-id="9b5b0-169">In the tree, expand 'Intrastat model'.</span></span>
17. <span data-ttu-id="9b5b0-170">Expandera "Intrastat model\Intrastat (DE)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="9b5b0-170">In the tree, expand 'Intrastat model\Intrastat (DE)'.</span></span>
18. <span data-ttu-id="9b5b0-171">Välj "Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing" i trädet.</span><span class="sxs-lookup"><span data-stu-id="9b5b0-171">In the tree, select 'Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing'.</span></span>
19. <span data-ttu-id="9b5b0-172">Klicka på Debug logs.</span><span class="sxs-lookup"><span data-stu-id="9b5b0-172">Click Debug logs.</span></span>
    * <span data-ttu-id="9b5b0-173">Observera att en post för loggfelsökning har skapats för utförandeprocessen för den valda konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="9b5b0-173">Note that a debug log record has been created for the execution process of the selected configuration.</span></span>  
20. <span data-ttu-id="9b5b0-174">Klicka på Koppla.</span><span class="sxs-lookup"><span data-stu-id="9b5b0-174">Click Attach.</span></span>
21. <span data-ttu-id="9b5b0-175">Klicka på Öppna.</span><span class="sxs-lookup"><span data-stu-id="9b5b0-175">Click Open.</span></span>
    * <span data-ttu-id="9b5b0-176">Förhandsvisa den skapade XML-filen som innehåller inventerings- och summeringsinformation som samlades in i samband med körningen av den valda konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="9b5b0-176">Review the created XML file that contains counting and summing details that were collected during the execution of the selected configuration.</span></span>  

