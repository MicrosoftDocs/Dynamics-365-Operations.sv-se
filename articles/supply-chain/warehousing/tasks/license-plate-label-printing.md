---
title: Aktivera utskrift av ID-nummer
description: I den här proceduren aktiveras automatisk utskrift av ett EAN-kollinummer (SSCC) efter den sista artikeln som plockas från lagret i arbetsprocessen för försäljningsplocklistan.
author: perlynne
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysCorpNetPrinterList, WHSParameters, NumberSequenceTableListPage, NumberSequenceDetails, WHSDocumentRoutingLayout, WHSDocumentRouting, WHSRFMenuItem, WHSRFMenu, WHSWorkTemplateTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ed74806e5e037570f3ed7f59725eed494c829d34
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2019
ms.locfileid: "1847287"
---
# <a name="enable-license-plate-label-printing"></a><span data-ttu-id="97e56-103">Aktivera utskrift av ID-nummer</span><span class="sxs-lookup"><span data-stu-id="97e56-103">Enable license plate label printing</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="97e56-104">I den här proceduren aktiveras automatisk utskrift av ett EAN-kollinummer (SSCC) efter den sista artikeln som plockas från lagret i arbetsprocessen för försäljningsplocklistan.</span><span class="sxs-lookup"><span data-stu-id="97e56-104">This procedure enables the automatic printing of a Serial shipping container code (SSCC) label after the last item is picked from inventory in a sales picking work process.</span></span> <span data-ttu-id="97e56-105">Du kan köra den här proceduren i demonstrationsdataföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="97e56-105">You can run this procedure in demo data company USMF.</span></span> <span data-ttu-id="97e56-106">Om du kör med dina egna data måste du ha en nummerserie som har ställts in för ID-nummer.</span><span class="sxs-lookup"><span data-stu-id="97e56-106">If you’re run it using your own data, you need to have a number sequence set up for license plates.</span></span> <span data-ttu-id="97e56-107">Du måste konfigurera en etikettskrivare innan du börjar med den här uppgiften.</span><span class="sxs-lookup"><span data-stu-id="97e56-107">You need to set up a label printer before you begin this task.</span></span> <span data-ttu-id="97e56-108">Gå till Organisationsadministration > Inställningar > Nätverksskrivare.</span><span class="sxs-lookup"><span data-stu-id="97e56-108">Go to Organization administration > Setup > Network printers.</span></span> <span data-ttu-id="97e56-109">I åtgärdsfönstret klickar du på Alternativ och sedan på knappen Hämta installationsprogram för dokumentflödesagent.</span><span class="sxs-lookup"><span data-stu-id="97e56-109">On the Action pane, click Options, and then click the Download document routing agent installer button.</span></span> <span data-ttu-id="97e56-110">Kör installationsprogrammet och kontrollera att du har en nätverkskrivare som är inställd på Aktiv innan du fortsätter med proceduren.</span><span class="sxs-lookup"><span data-stu-id="97e56-110">Run the installer and make sure that you have a working network printer set to Active before you continue with the procedure.</span></span>


## <a name="set-up-the-gs1-company-prefix"></a><span data-ttu-id="97e56-111">Ställ in GS1-företagsprefix</span><span class="sxs-lookup"><span data-stu-id="97e56-111">Set up the GS1 company prefix</span></span>
1. <span data-ttu-id="97e56-112">Gå till Lagerstyrning > Inställningar > Parametrar för lagerstyrning.</span><span class="sxs-lookup"><span data-stu-id="97e56-112">Go to Warehouse management > Setup > Warehouse management parameters.</span></span>
2. <span data-ttu-id="97e56-113">Ange det sjusiffriga numret på ditt GS1-företag i fältet GS1-företagsprefix.</span><span class="sxs-lookup"><span data-stu-id="97e56-113">In the GS1 company prefix field, enter the 7 numbers for your GS1 company number.</span></span>
3. <span data-ttu-id="97e56-114">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="97e56-114">Click Save.</span></span>
4. <span data-ttu-id="97e56-115">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="97e56-115">Close the page.</span></span>

## <a name="setup-the-sscc-license-plate-number-sequence"></a><span data-ttu-id="97e56-116">Ställ in nummerserien för SSCC-ID-numret</span><span class="sxs-lookup"><span data-stu-id="97e56-116">Setup the SSCC license plate number sequence</span></span>
1. <span data-ttu-id="97e56-117">Gå till Organisationsadministration > Nummerserier > Nummerserier.</span><span class="sxs-lookup"><span data-stu-id="97e56-117">Go to Organization administration > Number sequences > Number sequences.</span></span>
2. <span data-ttu-id="97e56-118">Markera ett alternativ i fältet Område.</span><span class="sxs-lookup"><span data-stu-id="97e56-118">In the Area field, select an option.</span></span>
3. <span data-ttu-id="97e56-119">Markera ett alternativ i fältet Referens.</span><span class="sxs-lookup"><span data-stu-id="97e56-119">In the Reference field, select an option.</span></span>
4. <span data-ttu-id="97e56-120">Skriv ett värde i fältet Företag.</span><span class="sxs-lookup"><span data-stu-id="97e56-120">In the Company field, type a value.</span></span>
5. <span data-ttu-id="97e56-121">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="97e56-121">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="97e56-122">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="97e56-122">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="97e56-123">Expandera avsnittet Segment.</span><span class="sxs-lookup"><span data-stu-id="97e56-123">Expand the Segments section.</span></span>
8. <span data-ttu-id="97e56-124">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="97e56-124">Click Edit.</span></span>
9. <span data-ttu-id="97e56-125">Välj den första raden i segmentregistret</span><span class="sxs-lookup"><span data-stu-id="97e56-125">In the Segments table, select the first row</span></span>
10. <span data-ttu-id="97e56-126">Klicka på Ta bort.</span><span class="sxs-lookup"><span data-stu-id="97e56-126">Click Remove.</span></span>
11. <span data-ttu-id="97e56-127">Klicka på Ta bort.</span><span class="sxs-lookup"><span data-stu-id="97e56-127">Click Remove.</span></span>
12. <span data-ttu-id="97e56-128">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="97e56-128">Click Save.</span></span>
13. <span data-ttu-id="97e56-129">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="97e56-129">Close the page.</span></span>

## <a name="create-the-document-route-layout"></a><span data-ttu-id="97e56-130">Skapa dokumentflödeslayouten</span><span class="sxs-lookup"><span data-stu-id="97e56-130">Create the document route layout</span></span>
1. <span data-ttu-id="97e56-131">Gå till Lagerstyrning > Inställningar > Dokumentflöde > Dokumentflödets layouter.</span><span class="sxs-lookup"><span data-stu-id="97e56-131">Go to Warehouse management > Setup > Document routing > Document routing layouts.</span></span>
    * <span data-ttu-id="97e56-132">Aktivera SSCC-layout.</span><span class="sxs-lookup"><span data-stu-id="97e56-132">Enable the SSCC layout.</span></span>  
2. <span data-ttu-id="97e56-133">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="97e56-133">Click New.</span></span>
3. <span data-ttu-id="97e56-134">Skriv ett värde i fältet Layout-ID.</span><span class="sxs-lookup"><span data-stu-id="97e56-134">In the Layout ID field, type a value.</span></span>
4. <span data-ttu-id="97e56-135">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="97e56-135">In the Description field, type a value.</span></span>
5. <span data-ttu-id="97e56-136">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="97e56-136">In the list, find and select the desired record.</span></span>
6. <span data-ttu-id="97e56-137">Klicka på Infoga vid textens slut.</span><span class="sxs-lookup"><span data-stu-id="97e56-137">Click Insert at end of text.</span></span>
7. <span data-ttu-id="97e56-138">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="97e56-138">Click Save.</span></span>
8. <span data-ttu-id="97e56-139">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="97e56-139">Close the page.</span></span>

## <a name="set-up-the-document-routing"></a><span data-ttu-id="97e56-140">Ställ in dokumentflödet</span><span class="sxs-lookup"><span data-stu-id="97e56-140">Set up the document routing</span></span>
1. <span data-ttu-id="97e56-141">Gå till Lagerstyrning > Inställningar > Dokumentflöde > Dokumentflöde.</span><span class="sxs-lookup"><span data-stu-id="97e56-141">Go to Warehouse management > Setup > Document routing > Document routing.</span></span>
2. <span data-ttu-id="97e56-142">Välj ett alternativ i fältet Arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="97e56-142">In the Work order type field, select an option.</span></span>
3. <span data-ttu-id="97e56-143">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="97e56-143">Click New.</span></span>
4. <span data-ttu-id="97e56-144">Ange ett värde i fältet Lagerställe.</span><span class="sxs-lookup"><span data-stu-id="97e56-144">In the Warehouse field, type a value.</span></span>
5. <span data-ttu-id="97e56-145">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="97e56-145">In the Name field, type a value.</span></span>
6. <span data-ttu-id="97e56-146">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="97e56-146">Click New.</span></span>
7. <span data-ttu-id="97e56-147">Ange eller välj ett värde i fältet Layout-ID.</span><span class="sxs-lookup"><span data-stu-id="97e56-147">In the Layout ID field, enter or select a value.</span></span>
8. <span data-ttu-id="97e56-148">I namnfältet väljer du det skrivarnamn som du vill använda.</span><span class="sxs-lookup"><span data-stu-id="97e56-148">In the Name field, enter the printer name that you want to use..</span></span>
9. <span data-ttu-id="97e56-149">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="97e56-149">Click Save.</span></span>
10. <span data-ttu-id="97e56-150">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="97e56-150">Close the page.</span></span>

## <a name="create-mobile-device-menu"></a><span data-ttu-id="97e56-151">Skapa meny på mobil enhet</span><span class="sxs-lookup"><span data-stu-id="97e56-151">Create mobile device menu</span></span>
1. <span data-ttu-id="97e56-152">Gå till Lagerstyrning > Inställningar > Mobil enhet > Menyalternativ på mobil enhet.</span><span class="sxs-lookup"><span data-stu-id="97e56-152">Go to Warehouse management > Setup > Mobile device > Mobile device menu items.</span></span>
2. <span data-ttu-id="97e56-153">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="97e56-153">Click New.</span></span>
3. <span data-ttu-id="97e56-154">Skriv ett värde i fältet Menyalternativ.</span><span class="sxs-lookup"><span data-stu-id="97e56-154">In the Menu item name field, type a value.</span></span>
4. <span data-ttu-id="97e56-155">Ange ett värde i fältet Titel.</span><span class="sxs-lookup"><span data-stu-id="97e56-155">In the Title field, type a value.</span></span>
5. <span data-ttu-id="97e56-156">Markera ett alternativ i fältet Läge.</span><span class="sxs-lookup"><span data-stu-id="97e56-156">In the Mode field, select an option.</span></span>
6. <span data-ttu-id="97e56-157">Välj Ja i fältet Använd befintligt arbete.</span><span class="sxs-lookup"><span data-stu-id="97e56-157">Select Yes in the Use existing work field.</span></span>
7. <span data-ttu-id="97e56-158">Välj Ja i fältet Generera nummerplåt.</span><span class="sxs-lookup"><span data-stu-id="97e56-158">Select Yes in the Generate license plate field.</span></span>
8. <span data-ttu-id="97e56-159">Expandera arbetsklassavsnittet.</span><span class="sxs-lookup"><span data-stu-id="97e56-159">Expand the Work classes section.</span></span>
9. <span data-ttu-id="97e56-160">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="97e56-160">Click New.</span></span>
10. <span data-ttu-id="97e56-161">Skriv ett värde i fältet Arbetsklass-ID.</span><span class="sxs-lookup"><span data-stu-id="97e56-161">In the Work class ID field, type a value.</span></span>
11. <span data-ttu-id="97e56-162">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="97e56-162">Click Save.</span></span>
12. <span data-ttu-id="97e56-163">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="97e56-163">Close the page.</span></span>
13. <span data-ttu-id="97e56-164">Gå till Lagerstyrning > Inställningar > Mobil enhet > Meny på mobil enhet.</span><span class="sxs-lookup"><span data-stu-id="97e56-164">Go to Warehouse management > Setup > Mobile device > Mobile device menu.</span></span>
14. <span data-ttu-id="97e56-165">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="97e56-165">In the list, find and select the desired record.</span></span>
15. <span data-ttu-id="97e56-166">I trädet markerar du "Välj menyalternativet du skapade tidigare i trädet".</span><span class="sxs-lookup"><span data-stu-id="97e56-166">In the tree, select 'In the tree, select the menu item that you created before.'.</span></span>
16. <span data-ttu-id="97e56-167">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="97e56-167">Click Edit.</span></span>
17. <span data-ttu-id="97e56-168">Klicka på pilen för att lägga till menykommandot till menyn.</span><span class="sxs-lookup"><span data-stu-id="97e56-168">Click on the arrow to add the menu item to the menu.</span></span>
18. <span data-ttu-id="97e56-169">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="97e56-169">Click Save.</span></span>
19. <span data-ttu-id="97e56-170">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="97e56-170">Close the page.</span></span>

## <a name="update-a-work-template"></a><span data-ttu-id="97e56-171">Uppdatera en arbetsuppgiftsmall</span><span class="sxs-lookup"><span data-stu-id="97e56-171">Update a work template</span></span>
1. <span data-ttu-id="97e56-172">Gå till Lagerstyrning > Inställningar > Arbete > Arbetsmallar.</span><span class="sxs-lookup"><span data-stu-id="97e56-172">Go to Warehouse management > Setup > Work > Work templates.</span></span>
2. <span data-ttu-id="97e56-173">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="97e56-173">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="97e56-174">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="97e56-174">Click Edit.</span></span>
4. <span data-ttu-id="97e56-175">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="97e56-175">Click New.</span></span>
5. <span data-ttu-id="97e56-176">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="97e56-176">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="97e56-177">Välj "Skriv ut" i fältet Arbetstyp.</span><span class="sxs-lookup"><span data-stu-id="97e56-177">In the Work type field, select 'Print'.</span></span>
7. <span data-ttu-id="97e56-178">I fältet Arbetsklass-ID, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="97e56-178">In the Work class ID field, enter or select a value.</span></span>
8. <span data-ttu-id="97e56-179">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="97e56-179">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="97e56-180">Klicka på Flytta upp.</span><span class="sxs-lookup"><span data-stu-id="97e56-180">Click Move up.</span></span>
10. <span data-ttu-id="97e56-181">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="97e56-181">Click Save.</span></span>
11. <span data-ttu-id="97e56-182">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="97e56-182">Close the page.</span></span>

