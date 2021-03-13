---
title: ER Konfigurera format för inventering och summering (Del 4 - Köra format)
description: I det här avsnittet beskrivs hur du konfigurerar ett elektroniskt rapporteringsformat för inventering och summering baserat på data i det redan genererade textutdata. (Del 4)
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
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c5576229e8b81824dff6d0b38b8ab5483e04ade8
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/30/2021
ms.locfileid: "5092957"
---
# <a name="er-configure-format-to-do-counting-and-summing-part-4---run-format"></a><span data-ttu-id="63798-104">ER Konfigurera format för inventering och summering (Del 4 - Köra format)</span><span class="sxs-lookup"><span data-stu-id="63798-104">ER Configure format to do counting and summing (Part 4 - Run format)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="63798-105">I följande steg beskrivs hur en användare som tilldelats en roll som systemadministratör eller utvecklare för elektronisk rapportering kan konfigurera ett format för elektronisk rapportering (ER) att utföra inventering och summering baserat på data tillhörande redan skapad textutmatning.</span><span class="sxs-lookup"><span data-stu-id="63798-105">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to do counting and summing based on data of the already generated text output.</span></span> <span data-ttu-id="63798-106">Dessa steg kan utföras i DEMF-företaget.</span><span class="sxs-lookup"><span data-stu-id="63798-106">These steps can be performed in the DEMF company.</span></span>

<span data-ttu-id="63798-107">För att slutföra dessa steg måste du först avsluta stegen i proceduren ”ER Configure format to do counting and summing (Part 3: Use computations to make the output)".</span><span class="sxs-lookup"><span data-stu-id="63798-107">To complete these steps, you must first complete the steps in the "ER Configure format to do counting and summing (Part 3: Use computations to make the output)" procedure.</span></span>

<span data-ttu-id="63798-108">Denna procedur är avsedd för en funktion som lades till i Dynamics 365 for Operations version 1611.</span><span class="sxs-lookup"><span data-stu-id="63798-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="test-this-configuration-for-generation-of-the-intrastat-reports"></a><span data-ttu-id="63798-109">Testa denna konfiguration för att skapa Intrastat-rapporterna</span><span class="sxs-lookup"><span data-stu-id="63798-109">Test this configuration for generation of the Intrastat reports</span></span>
1. <span data-ttu-id="63798-110">Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="63798-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="63798-111">Klicka på Reporting configurations.</span><span class="sxs-lookup"><span data-stu-id="63798-111">Click Reporting configurations.</span></span>
3. <span data-ttu-id="63798-112">Expandera "Intrastat model" i trädet.</span><span class="sxs-lookup"><span data-stu-id="63798-112">In the tree, expand 'Intrastat model'.</span></span>
4. <span data-ttu-id="63798-113">Expandera "Intrastat model\Intrastat (DE)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="63798-113">In the tree, expand 'Intrastat model\Intrastat (DE)'.</span></span>
5. <span data-ttu-id="63798-114">Välj "Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing" i trädet.</span><span class="sxs-lookup"><span data-stu-id="63798-114">In the tree, select 'Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing'.</span></span>
6. <span data-ttu-id="63798-115">Klicka på Configurations i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="63798-115">On the Action Pane, click Configurations.</span></span>
7. <span data-ttu-id="63798-116">Klicka på User parameters.</span><span class="sxs-lookup"><span data-stu-id="63798-116">Click User parameters.</span></span>
8. <span data-ttu-id="63798-117">Välj Yes i fältet Run settings.</span><span class="sxs-lookup"><span data-stu-id="63798-117">Select Yes in the Run settings field.</span></span>
9. <span data-ttu-id="63798-118">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="63798-118">Click OK.</span></span>
10. <span data-ttu-id="63798-119">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="63798-119">Click Edit.</span></span>
11. <span data-ttu-id="63798-120">Välj Yes i fältet Run Draft.</span><span class="sxs-lookup"><span data-stu-id="63798-120">Select Yes in the Run Draft field.</span></span>
12. <span data-ttu-id="63798-121">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="63798-121">Click Save.</span></span>
13. <span data-ttu-id="63798-122">Gå till Skatt > Inställningar > Utländsk handel > Utländska handelsparametrar.</span><span class="sxs-lookup"><span data-stu-id="63798-122">Go to Tax > Setup > Foreign trade > Foreign trade parameters.</span></span>
14. <span data-ttu-id="63798-123">Expandera avsnittet Elektronisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="63798-123">Expand the Electronic reporting section.</span></span>
15. <span data-ttu-id="63798-124">Välj konfigurationen "Intrastat (DE) with counting & summing".</span><span class="sxs-lookup"><span data-stu-id="63798-124">Select the "Intrastat (DE) with counting & summing" configuration.</span></span>
16. <span data-ttu-id="63798-125">Välj konfigurationen "Intrastat (DE) with counting & summing".</span><span class="sxs-lookup"><span data-stu-id="63798-125">Select the "Intrastat (DE) with counting & summing" configuration.</span></span>
17. <span data-ttu-id="63798-126">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="63798-126">Click Save.</span></span>
18. <span data-ttu-id="63798-127">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="63798-127">Close the page.</span></span>
19. <span data-ttu-id="63798-128">Gå till Skatt > Deklarationer > Utländsk handel > Intrastat.</span><span class="sxs-lookup"><span data-stu-id="63798-128">Go to Tax > Declarations > Foreign trade > Intrastat.</span></span>
20. <span data-ttu-id="63798-129">Klicka på Utdata.</span><span class="sxs-lookup"><span data-stu-id="63798-129">Click Output.</span></span>
21. <span data-ttu-id="63798-130">Klicka på Rapport.</span><span class="sxs-lookup"><span data-stu-id="63798-130">Click Report.</span></span>
    * <span data-ttu-id="63798-131">Kör rapportgenereringsprocessen för Intrastat.</span><span class="sxs-lookup"><span data-stu-id="63798-131">Run the Intrastat report generation process.</span></span>  
22. <span data-ttu-id="63798-132">Ange datumet till "2000-01-01" i fältet Från datum.</span><span class="sxs-lookup"><span data-stu-id="63798-132">In the From date field, set the date to '2000-01-01'.</span></span>
    * <span data-ttu-id="63798-133">Definiera start- och slutdatum för den rapporteringsperiod som innehåller befintliga formulärtransaktioner.</span><span class="sxs-lookup"><span data-stu-id="63798-133">Define start and end dates for the reporting period that include the existing on the form transactions.</span></span>  
23. <span data-ttu-id="63798-134">Ange datumet till "2022-12-31" i fältet Till datum.</span><span class="sxs-lookup"><span data-stu-id="63798-134">In the To date field, set the date to '2022-12-31'.</span></span>
    * <span data-ttu-id="63798-135">Definiera start- och slutdatum för den rapporteringsperiod som innehåller befintliga formulärtransaktioner.</span><span class="sxs-lookup"><span data-stu-id="63798-135">Define start and end dates for the reporting period that include the existing on the form transactions.</span></span>  
24. <span data-ttu-id="63798-136">Välj "Arrivals" i fältet Directions.</span><span class="sxs-lookup"><span data-stu-id="63798-136">In the Direction field, select 'Arrivals'.</span></span>
25. <span data-ttu-id="63798-137">Välj Ja i fältet Skapa fil.</span><span class="sxs-lookup"><span data-stu-id="63798-137">Select Yes in the Generate file field.</span></span>
26. <span data-ttu-id="63798-138">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="63798-138">Click OK.</span></span>
    * <span data-ttu-id="63798-139">Granska den skapade utleveransen med sammanfattningsraderna i slutet.</span><span class="sxs-lookup"><span data-stu-id="63798-139">Review the created output with the summary lines in the end.</span></span>  
27. <span data-ttu-id="63798-140">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="63798-140">Click New.</span></span>
28. <span data-ttu-id="63798-141">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="63798-141">In the list, mark the selected row.</span></span>
29. <span data-ttu-id="63798-142">Välj "Dispatches" i fältet Direction.</span><span class="sxs-lookup"><span data-stu-id="63798-142">In the Direction field, select 'Dispatches'.</span></span>
30. <span data-ttu-id="63798-143">Ange eller välj ett värde i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="63798-143">In the Item number field, enter or select a value.</span></span>
31. <span data-ttu-id="63798-144">Ange eller välj ett värde i fältet Artikel.</span><span class="sxs-lookup"><span data-stu-id="63798-144">In the Commodity field, enter or select a value.</span></span>
32. <span data-ttu-id="63798-145">Ange Weight som "10".</span><span class="sxs-lookup"><span data-stu-id="63798-145">Set Weight to '10'.</span></span>
33. <span data-ttu-id="63798-146">Ange Invoice amount som "10000".</span><span class="sxs-lookup"><span data-stu-id="63798-146">Set Invoice amount to '10000'.</span></span>
34. <span data-ttu-id="63798-147">Ange Statistical amount som "10000".</span><span class="sxs-lookup"><span data-stu-id="63798-147">Set Statistical amount to '10000'.</span></span>
35. <span data-ttu-id="63798-148">Klicka på Utdata.</span><span class="sxs-lookup"><span data-stu-id="63798-148">Click Output.</span></span>
36. <span data-ttu-id="63798-149">Klicka på Rapport.</span><span class="sxs-lookup"><span data-stu-id="63798-149">Click Report.</span></span>
37. <span data-ttu-id="63798-150">Välj "Dispatches" i fältet Direction.</span><span class="sxs-lookup"><span data-stu-id="63798-150">In the Direction field, select 'Dispatches'.</span></span>
38. <span data-ttu-id="63798-151">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="63798-151">Click OK.</span></span>
    * <span data-ttu-id="63798-152">Granska den skapade utleveransen med sammanfattningsraderna i slutet.</span><span class="sxs-lookup"><span data-stu-id="63798-152">Review the created output with the summary lines in the end.</span></span> <span data-ttu-id="63798-153">Observera att den har ändrats i jämförelse med den första körningen.</span><span class="sxs-lookup"><span data-stu-id="63798-153">Note that it has been changed in comparison to the first run.</span></span>  

## <a name="run-this-configuration-in-debug-mode-to-review-the-collected-counting--summing-data"></a><span data-ttu-id="63798-154">Kör denna konfiguration i felsökningsläge för att granska insamlade inventerings- och summeringsdata</span><span class="sxs-lookup"><span data-stu-id="63798-154">Run this configuration in debug mode to review the collected counting & summing data</span></span>
1. <span data-ttu-id="63798-155">Gå till Organisationsadministration > Elektronisk rapportering > Konfigurationer.</span><span class="sxs-lookup"><span data-stu-id="63798-155">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="63798-156">Expandera "Intrastat model" i trädet.</span><span class="sxs-lookup"><span data-stu-id="63798-156">In the tree, expand 'Intrastat model'.</span></span>
3. <span data-ttu-id="63798-157">Expandera "Intrastat model\Intrastat (DE)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="63798-157">In the tree, expand 'Intrastat model\Intrastat (DE)'.</span></span>
4. <span data-ttu-id="63798-158">Välj "Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing" i trädet.</span><span class="sxs-lookup"><span data-stu-id="63798-158">In the tree, select 'Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing'.</span></span>
5. <span data-ttu-id="63798-159">Klicka på Configurations i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="63798-159">On the Action Pane, click Configurations.</span></span>
6. <span data-ttu-id="63798-160">Klicka på User parameters.</span><span class="sxs-lookup"><span data-stu-id="63798-160">Click User parameters.</span></span>
7. <span data-ttu-id="63798-161">Välj Yes i fältet Run in debug mode.</span><span class="sxs-lookup"><span data-stu-id="63798-161">Select Yes in the Run in debug mode field.</span></span>
8. <span data-ttu-id="63798-162">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="63798-162">Click OK.</span></span>
9. <span data-ttu-id="63798-163">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="63798-163">Close the page.</span></span>
10. <span data-ttu-id="63798-164">Gå till Skatt > Deklarationer > Utländsk handel > Intrastat.</span><span class="sxs-lookup"><span data-stu-id="63798-164">Go to Tax > Declarations > Foreign trade > Intrastat.</span></span>
11. <span data-ttu-id="63798-165">Klicka på Utdata.</span><span class="sxs-lookup"><span data-stu-id="63798-165">Click Output.</span></span>
12. <span data-ttu-id="63798-166">Klicka på Rapport.</span><span class="sxs-lookup"><span data-stu-id="63798-166">Click Report.</span></span>
13. <span data-ttu-id="63798-167">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="63798-167">Click OK.</span></span>
14. <span data-ttu-id="63798-168">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="63798-168">Close the page.</span></span>
15. <span data-ttu-id="63798-169">Gå till Organisationsadministration > Elektronisk rapportering > Konfigurationer.</span><span class="sxs-lookup"><span data-stu-id="63798-169">Go to Organization administration > Electronic reporting > Configurations.</span></span>
16. <span data-ttu-id="63798-170">Expandera "Intrastat model" i trädet.</span><span class="sxs-lookup"><span data-stu-id="63798-170">In the tree, expand 'Intrastat model'.</span></span>
17. <span data-ttu-id="63798-171">Expandera "Intrastat model\Intrastat (DE)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="63798-171">In the tree, expand 'Intrastat model\Intrastat (DE)'.</span></span>
18. <span data-ttu-id="63798-172">Välj "Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing" i trädet.</span><span class="sxs-lookup"><span data-stu-id="63798-172">In the tree, select 'Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing'.</span></span>
19. <span data-ttu-id="63798-173">Klicka på Debug logs.</span><span class="sxs-lookup"><span data-stu-id="63798-173">Click Debug logs.</span></span>
    * <span data-ttu-id="63798-174">Observera att en post för loggfelsökning har skapats för utförandeprocessen för den valda konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="63798-174">Note that a debug log record has been created for the execution process of the selected configuration.</span></span>  
20. <span data-ttu-id="63798-175">Klicka på Koppla.</span><span class="sxs-lookup"><span data-stu-id="63798-175">Click Attach.</span></span>
21. <span data-ttu-id="63798-176">Klicka på Öppna.</span><span class="sxs-lookup"><span data-stu-id="63798-176">Click Open.</span></span>
    * <span data-ttu-id="63798-177">Förhandsvisa den skapade XML-filen som innehåller inventerings- och summeringsinformation som samlades in i samband med körningen av den valda konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="63798-177">Review the created XML file that contains counting and summing details that were collected during the execution of the selected configuration.</span></span>  

