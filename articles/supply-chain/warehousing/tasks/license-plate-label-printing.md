---
title: Aktivera utskrift av ID-nummer
description: I det här avsnittet visar vi hur du aktiverar automatisk utskrift av ett EAN-kollinummer (SSCC) efter den sista artikeln som plockas från lagret i arbetsprocessen för försäljningsplocklistan.
author: perlynne
manager: tfehr
ms.date: 07/19/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysCorpNetPrinterList, WHSParameters, NumberSequenceTableListPage, NumberSequenceDetails, WHSDocumentRoutingLayout, WHSDocumentRouting, WHSRFMenuItem, WHSRFMenu, WHSWorkTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 43dc913e84fa53179855d7ab8dbbf4d179e2cc63
ms.sourcegitcommit: 8a2127c5af6cdbda30ccc1f9bef9bd4ab61e9e50
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/18/2020
ms.locfileid: "3383054"
---
# <a name="enable-license-plate-label-printing"></a><span data-ttu-id="b1b57-103">Aktivera utskrift av ID-nummer</span><span class="sxs-lookup"><span data-stu-id="b1b57-103">Enable license plate label printing</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b1b57-104">I det här avsnittet visar vi hur du aktiverar automatisk utskrift av ett EAN-kollinummer (SSCC) efter den sista artikeln som plockas från lagret i arbetsprocessen för försäljningsplocklistan.</span><span class="sxs-lookup"><span data-stu-id="b1b57-104">This topic shows how to enable the automatic printing of a Serial shipping container code (SSCC) label after the last item is picked from inventory in a sales picking work process.</span></span> <span data-ttu-id="b1b57-105">Du kan köra den här proceduren i demonstrationsdataföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="b1b57-105">You can run this procedure in demo data company USMF.</span></span> <span data-ttu-id="b1b57-106">Om du kör med dina egna data måste du ha en nummerserie som har ställts in för ID-nummer.</span><span class="sxs-lookup"><span data-stu-id="b1b57-106">If you're run it using your own data, you need to have a number sequence set up for license plates.</span></span> <span data-ttu-id="b1b57-107">Du måste konfigurera en etikettskrivare innan du börjar med den här uppgiften.</span><span class="sxs-lookup"><span data-stu-id="b1b57-107">You need to set up a label printer before you begin this task.</span></span> <span data-ttu-id="b1b57-108">Gå till Organisationsadministration > Inställningar > Nätverksskrivare.</span><span class="sxs-lookup"><span data-stu-id="b1b57-108">Go to Organization administration > Setup > Network printers.</span></span> <span data-ttu-id="b1b57-109">I åtgärdsfönstret klickar du på Alternativ och sedan på knappen Hämta installationsprogram för dokumentflödesagent.</span><span class="sxs-lookup"><span data-stu-id="b1b57-109">On the Action Pane, click Options, and then click the Download document routing agent installer button.</span></span> <span data-ttu-id="b1b57-110">Kör installationsprogrammet och kontrollera att du har en nätverkskrivare som är inställd på Aktiv innan du fortsätter med proceduren.</span><span class="sxs-lookup"><span data-stu-id="b1b57-110">Run the installer and make sure that you have a working network printer set to Active before you continue with the procedure.</span></span>


## <a name="set-up-the-gs1-company-prefix"></a><span data-ttu-id="b1b57-111">Ställ in GS1-företagsprefix</span><span class="sxs-lookup"><span data-stu-id="b1b57-111">Set up the GS1 company prefix</span></span>
1. <span data-ttu-id="b1b57-112">Gå till **Navigeringsfönster > Moduler > Lagerstyrning > Inställningar > Parametrar för lagerstyrning**.</span><span class="sxs-lookup"><span data-stu-id="b1b57-112">Go to **Navigation pane > Modules > Warehouse management > Setup > Warehouse management parameters**.</span></span>
2. <span data-ttu-id="b1b57-113">Ange det sjusiffriga numret på ditt GS1-företag i fältet **GS1-företagsprefix**.</span><span class="sxs-lookup"><span data-stu-id="b1b57-113">In the **GS1 company prefix** field, enter the 7 numbers for your GS1 company number.</span></span>
3. <span data-ttu-id="b1b57-114">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="b1b57-114">Select **Save**.</span></span>
4. <span data-ttu-id="b1b57-115">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="b1b57-115">Close the page.</span></span>

## <a name="setup-the-sscc-license-plate-number-sequence"></a><span data-ttu-id="b1b57-116">Ställ in nummerserien för SSCC-ID-numret</span><span class="sxs-lookup"><span data-stu-id="b1b57-116">Setup the SSCC license plate number sequence</span></span>
1. <span data-ttu-id="b1b57-117">Gå till **Navigeringsfönster > Moduler > Organisationsadministration > Nummerserier > Nummerserier**.</span><span class="sxs-lookup"><span data-stu-id="b1b57-117">Go to **Navigation pane > Modules > Organization administration > Number sequences > Number sequences**.</span></span>
2. <span data-ttu-id="b1b57-118">Välj ett alternativ i fältet **Område**.</span><span class="sxs-lookup"><span data-stu-id="b1b57-118">In the **Area** field, select an option.</span></span>
3. <span data-ttu-id="b1b57-119">Välj ett alternativ i fältet **Referens**.</span><span class="sxs-lookup"><span data-stu-id="b1b57-119">In the **Reference** field, select an option.</span></span>
4. <span data-ttu-id="b1b57-120">Skriv ett värde i fältet **Företag**.</span><span class="sxs-lookup"><span data-stu-id="b1b57-120">In the **Company** field, type a value.</span></span>
5. <span data-ttu-id="b1b57-121">Expandera avsnittet **Segment**.</span><span class="sxs-lookup"><span data-stu-id="b1b57-121">Expand the **Segments** section.</span></span>
6. <span data-ttu-id="b1b57-122">Välj **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="b1b57-122">Select **Edit**.</span></span>
7. <span data-ttu-id="b1b57-123">Välj den första raden i tabellen **Segment**</span><span class="sxs-lookup"><span data-stu-id="b1b57-123">In the **Segments** table, select the first row</span></span>
8. <span data-ttu-id="b1b57-124">Välj **Ta bort**.</span><span class="sxs-lookup"><span data-stu-id="b1b57-124">Select **Remove**.</span></span>
9. <span data-ttu-id="b1b57-125">Välj **Ta bort**.</span><span class="sxs-lookup"><span data-stu-id="b1b57-125">Select **Remove**.</span></span>
10. <span data-ttu-id="b1b57-126">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="b1b57-126">Select **Save**.</span></span>
11. <span data-ttu-id="b1b57-127">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="b1b57-127">Close the page.</span></span>

## <a name="create-the-document-route-layout"></a><span data-ttu-id="b1b57-128">Skapa dokumentflödeslayouten</span><span class="sxs-lookup"><span data-stu-id="b1b57-128">Create the document route layout</span></span>
1. <span data-ttu-id="b1b57-129">Gå till **Navigeringsfönster > Moduler > Lagerstyrning > Inställningar > Dokumentflöde > Dokumentflödets layouter**.</span><span class="sxs-lookup"><span data-stu-id="b1b57-129">Go to **Navigation pane > Modules > Warehouse management > Setup > Document routing > Document routing layouts**.</span></span> <span data-ttu-id="b1b57-130">Aktivera SSCC-layout.</span><span class="sxs-lookup"><span data-stu-id="b1b57-130">Enable the SSCC layout.</span></span>  
2. <span data-ttu-id="b1b57-131">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="b1b57-131">Select **New**.</span></span>
3. <span data-ttu-id="b1b57-132">Ange ett värde i fältet **Layout-ID**.</span><span class="sxs-lookup"><span data-stu-id="b1b57-132">In the **Layout ID** field, type a value.</span></span>
4. <span data-ttu-id="b1b57-133">I fältet **Beskrivning** anger du ett värde.</span><span class="sxs-lookup"><span data-stu-id="b1b57-133">In the **Description** field, type a value.</span></span>
5. <span data-ttu-id="b1b57-134">Välj **Infoga vid textens slut**.</span><span class="sxs-lookup"><span data-stu-id="b1b57-134">Select **Insert at end of text**.</span></span>
6. <span data-ttu-id="b1b57-135">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="b1b57-135">Select **Save**.</span></span>
7. <span data-ttu-id="b1b57-136">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="b1b57-136">Close the page.</span></span>

## <a name="set-up-the-document-routing"></a><span data-ttu-id="b1b57-137">Ställ in dokumentflödet</span><span class="sxs-lookup"><span data-stu-id="b1b57-137">Set up the document routing</span></span>
1. <span data-ttu-id="b1b57-138">Gå till **Navigeringsfönster > Moduler > Lagerstyrning > Inställningar > Dokumentflöde > Dokumentflöde**.</span><span class="sxs-lookup"><span data-stu-id="b1b57-138">Go to **Navigation pane > Modules > Warehouse management > Setup > Document routing > Document routing**.</span></span>
2. <span data-ttu-id="b1b57-139">Välj ett alternativ i fältet **Arbetsordertyp**.</span><span class="sxs-lookup"><span data-stu-id="b1b57-139">In the **Work order type** field, select an option.</span></span>
3. <span data-ttu-id="b1b57-140">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="b1b57-140">Select **New**.</span></span>
4. <span data-ttu-id="b1b57-141">Ange ett värde i fältet **Lagerställe**.</span><span class="sxs-lookup"><span data-stu-id="b1b57-141">In the **Warehouse** field, type a value.</span></span>
5. <span data-ttu-id="b1b57-142">Skriv ett värde i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="b1b57-142">In the **Name** field, type a value.</span></span>
6. <span data-ttu-id="b1b57-143">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="b1b57-143">Select **New**.</span></span>
7. <span data-ttu-id="b1b57-144">Ange eller välj ett värde i fältet **Layout-ID**.</span><span class="sxs-lookup"><span data-stu-id="b1b57-144">In the **Layout ID** field, enter or select a value.</span></span>
8. <span data-ttu-id="b1b57-145">I fältet **Namn**, ange printernamnet som du vill använda.</span><span class="sxs-lookup"><span data-stu-id="b1b57-145">In the **Name** field, enter the printer name that you want to use.</span></span>
9. <span data-ttu-id="b1b57-146">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="b1b57-146">Select **Save**.</span></span>
10. <span data-ttu-id="b1b57-147">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="b1b57-147">Close the page.</span></span>

## <a name="create-mobile-device-menu"></a><span data-ttu-id="b1b57-148">Skapa meny på mobil enhet</span><span class="sxs-lookup"><span data-stu-id="b1b57-148">Create mobile device menu</span></span>
1. <span data-ttu-id="b1b57-149">Gå till **Navigeringsfönster > Moduler > Lagerstyrning > Inställningar > Mobil enhet > Menyalternativ på mobil enhet**.</span><span class="sxs-lookup"><span data-stu-id="b1b57-149">Go to **Navigation pane > Modules > Warehouse management > Setup > Mobile device > Mobile device menu items**.</span></span>
2. <span data-ttu-id="b1b57-150">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="b1b57-150">Select **New**.</span></span>
3. <span data-ttu-id="b1b57-151">Ange ett värde i fältet **Menyalternativnamn**.</span><span class="sxs-lookup"><span data-stu-id="b1b57-151">In the **Menu item name** field, type a value.</span></span>
4. <span data-ttu-id="b1b57-152">Ange ett värde i fältet **Rubrik**.</span><span class="sxs-lookup"><span data-stu-id="b1b57-152">In the **Title** field, type a value.</span></span>
5. <span data-ttu-id="b1b57-153">Välj ett alternativ i fältet **Metod**.</span><span class="sxs-lookup"><span data-stu-id="b1b57-153">In the **Mode** field, select an option.</span></span>
6. <span data-ttu-id="b1b57-154">Välj **Ja** i fältet **Använd befintligt arbete**.</span><span class="sxs-lookup"><span data-stu-id="b1b57-154">Select **Yes** in the **Use existing work** field.</span></span>
7. <span data-ttu-id="b1b57-155">Välj **Ja** i fältet **Generera registreringsskylt**.</span><span class="sxs-lookup"><span data-stu-id="b1b57-155">Select **Yes** in the **Generate license plate** field.</span></span>
8. <span data-ttu-id="b1b57-156">Expandera avsnittet **Arbetsklasser**.</span><span class="sxs-lookup"><span data-stu-id="b1b57-156">Expand the **Work classes** section.</span></span>
9. <span data-ttu-id="b1b57-157">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="b1b57-157">Select **New**.</span></span>
10. <span data-ttu-id="b1b57-158">Ange ett värde i fältet **Arbetsklass-ID**.</span><span class="sxs-lookup"><span data-stu-id="b1b57-158">In the **Work class ID** field, type a value.</span></span>
11. <span data-ttu-id="b1b57-159">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="b1b57-159">Select **Save**.</span></span>
12. <span data-ttu-id="b1b57-160">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="b1b57-160">Close the page.</span></span>
13. <span data-ttu-id="b1b57-161">Gå till **Navigeringsfönster > Moduler > Lagerstyrning > Inställningar > Mobil enhet > Meny på mobil enhet**.</span><span class="sxs-lookup"><span data-stu-id="b1b57-161">Go to **navigation pane > Modules > Warehouse management > Setup > Mobile device > Mobile device menu**.</span></span>
14. <span data-ttu-id="b1b57-162">Välj menyalternativet som du nyss skapade i trädet.</span><span class="sxs-lookup"><span data-stu-id="b1b57-162">In the tree, select the menu item that you created before.</span></span>
15. <span data-ttu-id="b1b57-163">Välj **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="b1b57-163">Select **Edit**.</span></span>
16. <span data-ttu-id="b1b57-164">Välj pilen för att lägga till menyalternativet på menyn.</span><span class="sxs-lookup"><span data-stu-id="b1b57-164">Select the arrow to add the menu item to the menu.</span></span>
17. <span data-ttu-id="b1b57-165">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="b1b57-165">Select **Save**.</span></span>
18. <span data-ttu-id="b1b57-166">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="b1b57-166">Close the page.</span></span>

## <a name="update-a-work-template"></a><span data-ttu-id="b1b57-167">Uppdatera en arbetsuppgiftsmall</span><span class="sxs-lookup"><span data-stu-id="b1b57-167">Update a work template</span></span>
1. <span data-ttu-id="b1b57-168">Gå till **Navigeringsfönster > Moduler > Lagerstyrning > Inställningar > Arbete > Arbetsmallar**.</span><span class="sxs-lookup"><span data-stu-id="b1b57-168">Go to **Navigation pane > Modules > Warehouse management > Setup > Work > Work templates**.</span></span>
2. <span data-ttu-id="b1b57-169">Välj **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="b1b57-169">Select **Edit**.</span></span>
3. <span data-ttu-id="b1b57-170">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="b1b57-170">Select **New**.</span></span>
4. <span data-ttu-id="b1b57-171">Välj **Skriv ut** i fältet **Arbetstyp**.</span><span class="sxs-lookup"><span data-stu-id="b1b57-171">In the **Work type** field, select **Print**.</span></span>
5. <span data-ttu-id="b1b57-172">Ange eller välj ett värde i fältet **Arbetsklass-ID**.</span><span class="sxs-lookup"><span data-stu-id="b1b57-172">In the **Work class ID** field, enter or select a value.</span></span>
6. <span data-ttu-id="b1b57-173">Välj **Flytta upp**.</span><span class="sxs-lookup"><span data-stu-id="b1b57-173">Select **Move up**.</span></span>
7. <span data-ttu-id="b1b57-174">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="b1b57-174">Select **Save**.</span></span>
8. <span data-ttu-id="b1b57-175">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="b1b57-175">Close the page.</span></span>

