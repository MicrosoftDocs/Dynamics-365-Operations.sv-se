---
title: "Ställ in kvalitetsorder"
description: "I den här proceduren visas om hur du aktiverar en kvalitetshantering process där det inkommande lager måste kontrolleras omedelbart efter fakturaregister."
author: perlynne
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 029511634e56aec7fdd91bad9441cd12951fbd8d
ms.openlocfilehash: fbc99ae02576cb76edecb9ac74b1823305c5936b
ms.contentlocale: sv-se
ms.lasthandoff: 01/17/2018

---
# <a name="set-up-quality-orders"></a><span data-ttu-id="fcfb7-103">Ställ in kvalitetsorder</span><span class="sxs-lookup"><span data-stu-id="fcfb7-103">Set up quality orders</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="fcfb7-104">I den här proceduren visas om hur du aktiverar en kvalitetshantering process där det inkommande lager måste kontrolleras omedelbart efter fakturaregister.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-104">This procedure shows you how to enable a quality management process where incoming inventory must be inspected immediately after arrival registration.</span></span> <span data-ttu-id="fcfb7-105">Proceduren ska ske ut vanligtvis av en chef kvalitetsnormerna.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-105">The procedure will typically be carried out by a quality manager.</span></span> <span data-ttu-id="fcfb7-106">Processen omfattar att en kvalitetsgrupp, om du vill definiera artiklar, som ska tas prov, och en grupp test om du vill gruppera de tester som ska utföras på artiklarna i kvalitetsgruppen.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-106">The process includes the creation of a quality group, to define the items that are going to be sampled, and a test group to group the tests that are to be performed on items in the quality group.</span></span> <span data-ttu-id="fcfb7-107">Du kan köra den här handboken i demoföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-107">You can run this guide in the USMF demo data company.</span></span>


## <a name="enable-quality-management"></a><span data-ttu-id="fcfb7-108">Aktivera kvalitetshantering</span><span class="sxs-lookup"><span data-stu-id="fcfb7-108">Enable quality management</span></span>
1. <span data-ttu-id="fcfb7-109">Gå till Lagerhantering > Inställningar > Parametrar för hantering av lager och lagerstyrning.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-109">Go to Inventory management > Setup > Inventory and warehouse management parameters.</span></span>
2. <span data-ttu-id="fcfb7-110">Klicka på kvalitetshanteringfliken.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-110">Click the Quality management tab.</span></span>
3. <span data-ttu-id="fcfb7-111">Välj alternativet Ja för Använd kvalitetshantering.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-111">Set the Use quality management option to Yes.</span></span>
4. <span data-ttu-id="fcfb7-112">Klicka på Rapportinställning.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-112">Click Report setup.</span></span>
    * <span data-ttu-id="fcfb7-113">I USMF är rapportinställningen för kvalitetshantering redan definierad.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-113">In USMF, the report setup for quality management is already defined.</span></span> <span data-ttu-id="fcfb7-114">Om detta inte görs ska du lägga till nya rader här för de olika rapporttyperna och sedan välj den typ av dokument som ska användas för varje rapport.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-114">If this wasn’t done, you’d add new lines here for the different report types, and select the type of document to be used for each report.</span></span>  
5. <span data-ttu-id="fcfb7-115">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-115">Close the page.</span></span>
6. <span data-ttu-id="fcfb7-116">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-116">Close the page.</span></span>

## <a name="create-a-test"></a><span data-ttu-id="fcfb7-117">Skapa test</span><span class="sxs-lookup"><span data-stu-id="fcfb7-117">Create a test</span></span>
1. <span data-ttu-id="fcfb7-118">Gå till Lagerhantering > Inställningar > Kvalitetskontroll > Tester.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-118">Go to Inventory management > Setup > Quality control > Tests.</span></span>
2. <span data-ttu-id="fcfb7-119">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-119">Click New.</span></span>
3. <span data-ttu-id="fcfb7-120">Ange ett värde i fältet Test.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-120">In the Test field, type a value.</span></span>
4. <span data-ttu-id="fcfb7-121">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-121">In the Description field, type a value.</span></span>
5. <span data-ttu-id="fcfb7-122">Välj Alternativ i fältet Typ.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-122">In the Type field, select 'Option'.</span></span>
    * <span data-ttu-id="fcfb7-123">I det här exemplet ska du välja ”Alternativ” som ska göra det möjligt att tilldela testresultatet baserat på fördefinierade värden.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-123">In this example, we'll select "Option" which will make it possible to assign the test results based on pre-defined values.</span></span>  
6. <span data-ttu-id="fcfb7-124">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-124">Click Save.</span></span>
7. <span data-ttu-id="fcfb7-125">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-125">Close the page.</span></span>

## <a name="create-test-variables-to-define-the-way-test-results-are-recorded"></a><span data-ttu-id="fcfb7-126">Skapa testvariabeln för att definiera hur testresultatet registreras</span><span class="sxs-lookup"><span data-stu-id="fcfb7-126">Create Test variables to define the way test results are recorded</span></span>
1. <span data-ttu-id="fcfb7-127">Gå till Lagerhantering > Inställningar > Kvalitetskontroll > Testvariabler.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-127">Go to Inventory management > Setup > Quality control > Test variables.</span></span>
2. <span data-ttu-id="fcfb7-128">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-128">Click New.</span></span>
3. <span data-ttu-id="fcfb7-129">Ange ett värde i fältet Variabel.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-129">In the Variable field, type a value.</span></span>
4. <span data-ttu-id="fcfb7-130">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-130">In the Description field, type a value.</span></span>
5. <span data-ttu-id="fcfb7-131">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-131">Click Save.</span></span>
6. <span data-ttu-id="fcfb7-132">Klicka på Resultat.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-132">Click Outcomes.</span></span>
7. <span data-ttu-id="fcfb7-133">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-133">Click New.</span></span>
8. <span data-ttu-id="fcfb7-134">Ange ett värde i fältet Resultat.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-134">In the Outcome field, type a value.</span></span>
9. <span data-ttu-id="fcfb7-135">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-135">In the Description field, type a value.</span></span>
10. <span data-ttu-id="fcfb7-136">Välj Godkänd i resultatstatusfältet.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-136">In the Outcome status field, select 'Pass'.</span></span>
11. <span data-ttu-id="fcfb7-137">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-137">Click Save.</span></span>
12. <span data-ttu-id="fcfb7-138">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-138">Click New.</span></span>
13. <span data-ttu-id="fcfb7-139">Ange ett värde i fältet Resultat.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-139">In the Outcome field, type a value.</span></span>
14. <span data-ttu-id="fcfb7-140">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-140">In the Description field, type a value.</span></span>
15. <span data-ttu-id="fcfb7-141">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-141">Click Save.</span></span>
16. <span data-ttu-id="fcfb7-142">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-142">Close the page.</span></span>
17. <span data-ttu-id="fcfb7-143">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-143">Close the page.</span></span>

## <a name="set-up-item-sampling"></a><span data-ttu-id="fcfb7-144">Ställ in artikelsampling</span><span class="sxs-lookup"><span data-stu-id="fcfb7-144">Set up item sampling</span></span>
1. <span data-ttu-id="fcfb7-145">Gå till Lagerhantering > Inställningar > Kvalitetskontroll > Artikelsampling.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-145">Go to Inventory management > Setup > Quality control > Item sampling.</span></span>
2. <span data-ttu-id="fcfb7-146">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-146">Click New.</span></span>
3. <span data-ttu-id="fcfb7-147">Skriv ett värde i samplingsfältet.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-147">In the Item sampling field, type a value.</span></span>
4. <span data-ttu-id="fcfb7-148">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-148">In the Description field, type a value.</span></span>
5. <span data-ttu-id="fcfb7-149">Ange ett nummer i fältet Värde.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-149">In the Value field, enter a number.</span></span>
    * <span data-ttu-id="fcfb7-150">Det här värdet är relaterade till kvantitetspecifikationen som valts i fältet bredvid.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-150">This value relates to the Quantity specification that’s selected in the adjacent field.</span></span>  
6. <span data-ttu-id="fcfb7-151">Dölj eller visa avsnittet Bearbeta.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-151">Expand or collapse the Process section.</span></span>
7. <span data-ttu-id="fcfb7-152">Markera eller avmarkera kryssrutan Full spärr.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-152">Select or clear the Full blocking check box.</span></span>
    * <span data-ttu-id="fcfb7-153">Om du markerar den här väljare, spärras hel komponent eller orderradkvantiteten, om ett test misslyckas.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-153">If you select this option, the whole lot or order line quantity is blocked if a test is failed.</span></span> <span data-ttu-id="fcfb7-154">Om du inte markerar kryssrutan, spärras bara artiklarna i kvalitetsordern.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-154">If you don't select it, only the items in the quality order are blocked.</span></span>  
8. <span data-ttu-id="fcfb7-155">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-155">Click Save.</span></span>
9. <span data-ttu-id="fcfb7-156">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-156">Close the page.</span></span>

## <a name="create-a-quality-group"></a><span data-ttu-id="fcfb7-157">Skapa en kvalitetsgrupp</span><span class="sxs-lookup"><span data-stu-id="fcfb7-157">Create a quality group</span></span>
1. <span data-ttu-id="fcfb7-158">Gå till Lagerhantering > Inställningar > Kvalitetskontroll > Kvalitetsgrupper.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-158">Go to Inventory management > Setup > Quality control > Quality groups.</span></span>
2. <span data-ttu-id="fcfb7-159">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-159">Click New.</span></span>
3. <span data-ttu-id="fcfb7-160">Skriv ett värde i fältet Kvalitetsgrupp.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-160">In the Quality group field, type a value.</span></span>
    * <span data-ttu-id="fcfb7-161">Använd ett beskrivande namn som hjälper dig att identifiera vilken typ av artiklar som gruppen ska innehålla (dina samplingvillkor).</span><span class="sxs-lookup"><span data-stu-id="fcfb7-161">Use a descriptive name to help you identify which kind of items the group will contain (your sampling criteria).</span></span>  
4. <span data-ttu-id="fcfb7-162">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-162">In the Description field, type a value.</span></span>
5. <span data-ttu-id="fcfb7-163">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-163">Click Save.</span></span>
6. <span data-ttu-id="fcfb7-164">Klicka på Lägg till artiklar.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-164">Click Add items.</span></span>
7. <span data-ttu-id="fcfb7-165">Markera raden med artikelnumret</span><span class="sxs-lookup"><span data-stu-id="fcfb7-165">Select the Item number row</span></span>
    * <span data-ttu-id="fcfb7-166">I det här exemplet ska vara kört filtrera utifrån artikelnumret.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-166">In this example the filtering will be run based on  the item number.</span></span>  
8. <span data-ttu-id="fcfb7-167">Ange ett värde i fältet Kriterier.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-167">In the Criteria field, type a value.</span></span>
    * <span data-ttu-id="fcfb7-168">Till exempel typ T\* som ska filtreras på artikelnummer som börjar med T.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-168">For example, type T\* to filter on the item numbers that start with T.</span></span>  
9. <span data-ttu-id="fcfb7-169">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-169">Click OK.</span></span>
10. <span data-ttu-id="fcfb7-170">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-170">Click OK.</span></span>
11. <span data-ttu-id="fcfb7-171">Klicka på Kvalitetsgrupper för artiklar.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-171">Click Item quality groups.</span></span>
12. <span data-ttu-id="fcfb7-172">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-172">Close the page.</span></span>
13. <span data-ttu-id="fcfb7-173">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-173">Close the page.</span></span>

## <a name="create-a-test-group"></a><span data-ttu-id="fcfb7-174">Skapa en testgrupp</span><span class="sxs-lookup"><span data-stu-id="fcfb7-174">Create a test group</span></span>
1. <span data-ttu-id="fcfb7-175">Gå till Lagerhantering > Inställningar > Kvalitetskontroll > Testgrupper.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-175">Go to Inventory management > Setup > Quality control > Test groups.</span></span>
2. <span data-ttu-id="fcfb7-176">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-176">Click New.</span></span>
3. <span data-ttu-id="fcfb7-177">Skriv ett värde i fältet Testgrupp.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-177">In the Test group field, type a value.</span></span>
    * <span data-ttu-id="fcfb7-178">Ge testgruppen ett namn som hjälper dig att komma ihåg vilken typ av testerna körs, och vilken kvalitetsgrupp den ska kopplas till.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-178">Give the Test group a name that will help you remember what kind of tests are being run, and which quality group it should be associated with.</span></span> <span data-ttu-id="fcfb7-179">Du kan till exempel använda den med en kvalitetsgrupp för att välja artiklar som börjar med ”T” och du kan kalla den ”T-artikeltest".</span><span class="sxs-lookup"><span data-stu-id="fcfb7-179">For example, it it’s to be used with a quality group that selects items starting with “T”, you could call it “T-item tests”.</span></span>  
4. <span data-ttu-id="fcfb7-180">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-180">In the Description field, type a value.</span></span>
5. <span data-ttu-id="fcfb7-181">Välj artikelsamplingraden som du skapade i artikelsamplingfältet förut.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-181">In the Item sampling field, select the item sampling line that you created before.</span></span>
6. <span data-ttu-id="fcfb7-182">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-182">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="fcfb7-183">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-183">Click Add.</span></span>
8. <span data-ttu-id="fcfb7-184">Ange ett nummer i fältet Sekvensnummer.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-184">In the Sequence number field, enter a number.</span></span>
9. <span data-ttu-id="fcfb7-185">I fältet Test väljer du det test som du skapade tidigare.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-185">In the Test field, select the test that you created earlier.</span></span>
10. <span data-ttu-id="fcfb7-186">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-186">In the list, find and select the desired record.</span></span>
11. <span data-ttu-id="fcfb7-187">Klicka på fliken Testa.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-187">Click the Test tab.</span></span>
12. <span data-ttu-id="fcfb7-188">I fältet Variabel väljer du den testvariabel som du skapade tidigare</span><span class="sxs-lookup"><span data-stu-id="fcfb7-188">In the Variable field, select the test variable that you created before</span></span>
13. <span data-ttu-id="fcfb7-189">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-189">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="fcfb7-190">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Standardkund.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-190">In the Default outcome field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="fcfb7-191">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-191">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="fcfb7-192">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-192">Click Save.</span></span>
17. <span data-ttu-id="fcfb7-193">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-193">Close the page.</span></span>

## <a name="define-when-quality-orders-will-be-created"></a><span data-ttu-id="fcfb7-194">Definiera när kvalitetsorder ska skapas</span><span class="sxs-lookup"><span data-stu-id="fcfb7-194">Define when quality orders will be created</span></span>
1. <span data-ttu-id="fcfb7-195">Gå till Lagerhantering > Inställningar > Kvalitetskontroll > Kvalitetsassociationer.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-195">Go to Inventory management > Setup > Quality control > Quality associations.</span></span>
2. <span data-ttu-id="fcfb7-196">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-196">Click New.</span></span>
3. <span data-ttu-id="fcfb7-197">Välj ett alternativ i fältet Referenstyp.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-197">In the Reference type field, select an option.</span></span>
4. <span data-ttu-id="fcfb7-198">Välj Grupp i fältet Artikelkod.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-198">In the Item code field, select 'Group'.</span></span>
    * <span data-ttu-id="fcfb7-199">I det här exemplet ska du markera Grupp och använder kvalitetsgruppen som du skapade förut.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-199">In this example, we’ll select "Group" and use the quality group we created before.</span></span> <span data-ttu-id="fcfb7-200">Du kan även ange den här avsnittet som Register för att ange artiklar manuellt eller välja Alla för att lägga till alla artiklar till kvalitetsordern.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-200">You could also set this to "Table" to specify the items manually, or select "All" to add all items to the quality order.</span></span>  
5. <span data-ttu-id="fcfb7-201">I fältet Artikel väljer du den kvalitetsgrupp som du skapade förut.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-201">In the Item field, select the quality group that you created before.</span></span>
    * <span data-ttu-id="fcfb7-202">Alternativen som är tillgängliga i fältet Artikel, beror på vad som du har angett i fältet Artikelkod.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-202">The options available in the Item field depend on what you set in the Item code field.</span></span>  
6. <span data-ttu-id="fcfb7-203">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-203">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="fcfb7-204">Dölj eller visa avsnittet Bearbeta.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-204">Expand or collapse the Process section.</span></span>
8. <span data-ttu-id="fcfb7-205">Välj ett alternativ i fältet Händelsetyp.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-205">In the Event type field, select an option.</span></span>
    * <span data-ttu-id="fcfb7-206">Det är händelsen som utlöser testet.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-206">This is the event that triggers the test.</span></span> <span data-ttu-id="fcfb7-207">De tillgängliga väljarna beror på vilken här processen du valde i referenstypfältet.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-207">The options available here depend on which process you selected in the Reference type field.</span></span>  
9. <span data-ttu-id="fcfb7-208">Markera ett alternativ i fältet Körning.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-208">In the Execution field, select an option.</span></span>
10. <span data-ttu-id="fcfb7-209">Dölj eller visa avsnittet Kvalitetsorderprocess.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-209">Expand or collapse the Quality order process section.</span></span>
11. <span data-ttu-id="fcfb7-210">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Händelsespärr.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-210">In the Event blocking field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="fcfb7-211">Det här fältet visar en lista med processer som det är möjligt att spärra, om kvalitetsordern fortfarande är öppen.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-211">This field shows the list of processes that it’s possible to block if the quality order is still open.</span></span> <span data-ttu-id="fcfb7-212">Väljarna beror på vad du valde i händelsetypfältet.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-212">The options depend on what you selected in the Event type field.</span></span>  
12. <span data-ttu-id="fcfb7-213">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-213">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="fcfb7-214">Det blir beroende på de föregående välja värden.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-214">This will be depending on the previous selected values.</span></span> <span data-ttu-id="fcfb7-215">Välj, om följande processer måste spärras, medan ha öppna kvalitetsorder som är kopplade till en källdokument, rad.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-215">Select if the following processes must be blocked while having open quality orders linked to a source document line.</span></span>  
13. <span data-ttu-id="fcfb7-216">dölj eller vis avsnittet Specifikationer.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-216">Expand or collapse the Specifications section.</span></span>
14. <span data-ttu-id="fcfb7-217">I fältet Testgrupp väljer du den testgrupp som du skapade tidigare.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-217">In the Test group field, select the test group that you created before.</span></span>
15. <span data-ttu-id="fcfb7-218">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-218">In the list, find and select the desired record.</span></span>
16. <span data-ttu-id="fcfb7-219">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-219">Click Save.</span></span>
17. <span data-ttu-id="fcfb7-220">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="fcfb7-220">Close the page.</span></span>

