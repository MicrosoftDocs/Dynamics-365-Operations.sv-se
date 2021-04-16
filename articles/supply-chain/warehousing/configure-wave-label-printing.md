---
title: Utskrift av påfyllnadsetikett
description: Det här ämnet beskriver utskrift av påfyllnadsetikett och förklarar hur du ställer in det.
author: GarmMSFT
ms.date: 05/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSWaveLabel, WHSWaveLabelTemplate, WHSWaveLabelLayoutRow, WHSDocumentRouting, WHSWaveTableListPage, WHSPostMethod, WHSMobileDisplayWaveLabelListLookup, WHSWaveLabelType, WHSWaveLabelTemplateGroup, WHSDocumentRoutingLayout
audience: Application User
ms.reviewer: PJacobse
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: yyyy-mm-dd
ms.dyn365.ops.version: 10.0.0
ms.openlocfilehash: fe04b841dbb3bb237de53f74d73f2b3f9162ae6b
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5840447"
---
# <a name="wave-label-printing"></a><span data-ttu-id="2b765-103">Utskrift av påfyllnadsetikett</span><span class="sxs-lookup"><span data-stu-id="2b765-103">Wave label printing</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2b765-104">Utskrift av påfyllnadsetikett ger en alternativ metod för att skriva ut etiketter genom att introducera en ny påfyllnadsmetod som gör att du kan skapa och skriva ut etiketter direkt från påfyllnadsmallen under påfyllnadskörningen.</span><span class="sxs-lookup"><span data-stu-id="2b765-104">Wave label printing offers an alternative approach to label printing by introducing a new wave step method that lets you create and print labels directly from the wave template during wave execution.</span></span> <span data-ttu-id="2b765-105">Därför är etiketterna redan tillgängliga innan arbetare kör arbetsordern på en mobil enhet.</span><span class="sxs-lookup"><span data-stu-id="2b765-105">Therefore, the labels will already be available before workers run the work order on a mobile device.</span></span> <span data-ttu-id="2b765-106">Arbetare kan sedan koppla de begärda etiketterna under plockning i stället för efter plockning.</span><span class="sxs-lookup"><span data-stu-id="2b765-106">Workers can then attach the required labels during picking instead of after picking.</span></span>

<span data-ttu-id="2b765-107">Utskrift av påfyllnadsetikett använder zebraprogrammeringspråket (ZPL) när du skapar etikettlayout.</span><span class="sxs-lookup"><span data-stu-id="2b765-107">Wave label printing uses Zebra Programming Language (ZPL) to create label layouts.</span></span> <span data-ttu-id="2b765-108">En etikettlayout är uppdelad i tre avsnitt (rubrik, brödtext och sidfot) som tillåter etiketter som har en upprepande struktur.</span><span class="sxs-lookup"><span data-stu-id="2b765-108">A label layout is divided into three sections (header, body, and footer) to allow for labels that have repeating structure.</span></span> <span data-ttu-id="2b765-109">Mallar för etikettutskrift anger du vilket system som etikettexten ska använda.</span><span class="sxs-lookup"><span data-stu-id="2b765-109">Wave label templates tell the system which label layout to use.</span></span> <span data-ttu-id="2b765-110">Användare kan ange vilken skrivare som ska användas.</span><span class="sxs-lookup"><span data-stu-id="2b765-110">Users can specify which printer is used.</span></span> <span data-ttu-id="2b765-111">De kan också skriva ut etiketter på flera skrivare samtidigt, eftersom de kräver det.</span><span class="sxs-lookup"><span data-stu-id="2b765-111">They can also print labels on several printers at the same time, as they require.</span></span> <span data-ttu-id="2b765-112">Sidan **påfyllnadsetiketthistoriken** visar en post över alla etiketter som har skapats med hjälp av den här inställningen.</span><span class="sxs-lookup"><span data-stu-id="2b765-112">The **Wave label history** page shows a record of all labels that have been created by using this setup.</span></span>

<span data-ttu-id="2b765-113">Du kan skriva ut och sortera etiketter baserat på arbetsrubriker, du kan skriva ut avbrottsetiketter per arbetsrubrik och du kan skriva ut behållarens innehållsetiketter, ärendeetiketter och andra liknande etiketter.</span><span class="sxs-lookup"><span data-stu-id="2b765-113">You can print and collate labels based on work headers, you can print break labels per work header, and you can print container content labels, case labels, and other similar labels.</span></span>

> [!NOTE]
> <span data-ttu-id="2b765-114">Den här funktionen ersätter inte de befintliga funktionerna för etikettutskrift som baseras på dokumentflödet.</span><span class="sxs-lookup"><span data-stu-id="2b765-114">This functionality doesn't replace existing label printing functionality that is based on document routing.</span></span>

<span data-ttu-id="2b765-115">Utskrift av påfyllnadsetikett ger följande förbättringar:</span><span class="sxs-lookup"><span data-stu-id="2b765-115">Wave label printing offers the following enhancements:</span></span>

- <span data-ttu-id="2b765-116">Skriv ut etiketter enligt antalet kartonger på en enda arbetsrad, utan att använda skapande av behållare.</span><span class="sxs-lookup"><span data-stu-id="2b765-116">Print labels according to the number of cartons on a single work line, without using containerization.</span></span> <span data-ttu-id="2b765-117">(En "kartong" är en enhet som har angetts för enhetssekvensgruppraderna.)</span><span class="sxs-lookup"><span data-stu-id="2b765-117">(A "carton" is a unit that is designated on unit sequence group lines.)</span></span>
- <span data-ttu-id="2b765-118">Skriv ut flera olika etikettserier (t.ex. kartonger och lastpallsetiketter).</span><span class="sxs-lookup"><span data-stu-id="2b765-118">Print several different label sequences (for example, carton and pallet labels).</span></span>
- <span data-ttu-id="2b765-119">Inkludera etikettuppräkning (t.ex. 1/124, 2/124... 124/124) och definiera intervallet för uppräkningen (t.ex. arbetsrad, lastrad eller leverans).</span><span class="sxs-lookup"><span data-stu-id="2b765-119">Include label enumeration (for example, 1/124, 2/124, ... 124/124), and define the range of enumeration (for example, work line, load line, or shipment).</span></span>
- <span data-ttu-id="2b765-120">Skapa och skriv ut ett fraktsedels-ID på etiketter innan fraktsedeln genereras.</span><span class="sxs-lookup"><span data-stu-id="2b765-120">Create and print a bill of lading ID on labels before the bill of lading is generated.</span></span>
- <span data-ttu-id="2b765-121">Skapa en unik serie för seriell leveransbehållare (SSCC) för varje kartong och inkludera den på varje etikett.</span><span class="sxs-lookup"><span data-stu-id="2b765-121">Create a unique serial shipping container code (SSCC) for each carton, and include it on each label.</span></span>
- <span data-ttu-id="2b765-122">Skapa GS1-kompatibla nummerserier för fraktsedels-ID och SSCC.</span><span class="sxs-lookup"><span data-stu-id="2b765-122">Create GS1-compliant number sequences for bill of lading IDs and SSCCs.</span></span>
- <span data-ttu-id="2b765-123">Skriv ut etiketterna på både mobila enheter och den avancerade klienten.</span><span class="sxs-lookup"><span data-stu-id="2b765-123">Reprint labels from both mobile devices and the rich client.</span></span>
- <span data-ttu-id="2b765-124">Annullera etiketter (t.ex. i korta plockningsscenarier) och skriv ut dem igen.</span><span class="sxs-lookup"><span data-stu-id="2b765-124">Void labels (for example, in short pick scenarios), and reprint them.</span></span>
- <span data-ttu-id="2b765-125">Rensa historik för påfyllnadsetikett.</span><span class="sxs-lookup"><span data-stu-id="2b765-125">Clean up the wave label history.</span></span>
- <span data-ttu-id="2b765-126">Förbättringar av layouter av dokumentflöde delas mellan dokumentflödets layout och påfyllnadsetikettens layout.</span><span class="sxs-lookup"><span data-stu-id="2b765-126">Improvements to document routing layouts are shared between document routing layouts and wave label layouts.</span></span> <span data-ttu-id="2b765-127">(Mer information finns i [Layout för dokumentflöde för ID-nummer](../warehousing/document-routing-layout-for-license-plates.md) .)</span><span class="sxs-lookup"><span data-stu-id="2b765-127">(For more information, see [Document routing layout for license plates](../warehousing/document-routing-layout-for-license-plates.md).)</span></span>

<span data-ttu-id="2b765-128">Dessa förbättringar gör det effektivare att märka kartonger före palletering.</span><span class="sxs-lookup"><span data-stu-id="2b765-128">These enhancements make it more efficient to label cartons before palletization.</span></span> <span data-ttu-id="2b765-129">De gynnar främst företag som levererar till stora återförsäljare som automatiskt bekräftar orderkvitton genom att söka igenom varje kartong separat.</span><span class="sxs-lookup"><span data-stu-id="2b765-129">They especially benefit companies that ship to large retailers that automatically confirm order receipts by scanning each carton separately.</span></span>

> [!NOTE]
> <span data-ttu-id="2b765-130">Du kan implementera konfigurationsscenarier som beskrivs i det här avsnittet, antingen separat eller i kombination, beroende på dina affärsbehov.</span><span class="sxs-lookup"><span data-stu-id="2b765-130">You can implement the configuration scenarios that are described in this topic either separately or in combination, depending on your business requirements.</span></span> <span data-ttu-id="2b765-131">Du kan skapa flera påfyllnadsetikettmallar som fungerar i ordningsföljd (som illustreras i scenario 3).</span><span class="sxs-lookup"><span data-stu-id="2b765-131">You can design several wave label templates that work in sequence (as illustrated in scenario 3).</span></span> <span data-ttu-id="2b765-132">Du kan till exempel använda scenario 1 för att skriva ut kartonger och scenario 2 om du vill skriva ut lastpallsetiketter (om lastpallar i lagret varierar i storlek och sammansättning).</span><span class="sxs-lookup"><span data-stu-id="2b765-132">For example, you can use scenario 1 to print carton labels and scenario 2 to print pallet labels (if pallets in stock vary in size and composition).</span></span>

## <a name="turn-on-the-wave-label-printing-feature"></a><span data-ttu-id="2b765-133">Aktivera funktionen utskrift av påfyllnadsetiketter</span><span class="sxs-lookup"><span data-stu-id="2b765-133">Turn on the Wave label printing feature</span></span>

<span data-ttu-id="2b765-134">Innan du kan använda funktionen *utskrift av påfyllnadsmall* den aktiveras i ditt system.</span><span class="sxs-lookup"><span data-stu-id="2b765-134">Before you can use the *Wave label printing* feature, it must be turned on in your system.</span></span> <span data-ttu-id="2b765-135">Administratörer kan använda arbetsytan [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den om det behövs.</span><span class="sxs-lookup"><span data-stu-id="2b765-135">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="2b765-136">Funktionen visas på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="2b765-136">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="2b765-137">**Modul:** *Lagerstyrning*</span><span class="sxs-lookup"><span data-stu-id="2b765-137">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="2b765-138">**Funktionsnamn:** *utskrift av påfyllnadsetiketter*</span><span class="sxs-lookup"><span data-stu-id="2b765-138">**Feature name:** *Wave label printing*</span></span>

## <a name="scenario-1-wave-label-printing-where-a-single-wave-label-is-generated"></a><span data-ttu-id="2b765-139">Scenario 1: utskrift av påfyllnadsetiketter där en enskild påfyllnadsetikett genereras</span><span class="sxs-lookup"><span data-stu-id="2b765-139">Scenario 1: Wave label printing where a single wave label is generated</span></span>

<span data-ttu-id="2b765-140">Det här scenariot visar hur ett företag kan skriva ut leveransetiketter för en stor återförsäljare som automatiskt bekräftar orderkvitton genom att söka igenom varje kartong separat.</span><span class="sxs-lookup"><span data-stu-id="2b765-140">This scenario shows how a company can print shipping labels for a large retailer that automatically confirms order receipts by scanning each carton separately.</span></span>

<span data-ttu-id="2b765-141">Det här scenariot visar komplett flöde.</span><span class="sxs-lookup"><span data-stu-id="2b765-141">This scenario shows the end-to-end flow.</span></span>

### <a name="make-demo-data-available"></a><span data-ttu-id="2b765-142">Gör demodata tillgängliga</span><span class="sxs-lookup"><span data-stu-id="2b765-142">Make demo data available</span></span>

<span data-ttu-id="2b765-143">För att följa detta scenario måste du ha demonstrationsdata installerad och du måste välja juridiska personen **USMF**.</span><span class="sxs-lookup"><span data-stu-id="2b765-143">To follow this scenario, you must have demo data installed, and you must select the **USMF** legal entity.</span></span>

### <a name="make-sure-that-the-wave-label-method-is-available"></a><span data-ttu-id="2b765-144">Kontrollera att påfyllnadsetikett metoden är tillgänglig</span><span class="sxs-lookup"><span data-stu-id="2b765-144">Make sure that the wave label method is available</span></span>

<span data-ttu-id="2b765-145">Du måste kanske återskapa dina metoder för påfyllnadsprocess för att göra påfyllnadsetikett metoden tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="2b765-145">You might have to regenerate the wave process methods to make the wave label printing method available.</span></span>

1. <span data-ttu-id="2b765-146">Gå till **Lagerstyrning \> Inställningar \> Påfyllnader \> Metoder för påfyllnadsprocess**.</span><span class="sxs-lookup"><span data-stu-id="2b765-146">Go to **Warehouse management \> Setup \> Waves \> Wave process methods**.</span></span>
1. <span data-ttu-id="2b765-147">Kontrollera att **waveLabelPrinting** finns i listan.</span><span class="sxs-lookup"><span data-stu-id="2b765-147">Confirm that **waveLabelPrinting** is in the list.</span></span> <span data-ttu-id="2b765-148">Om den inte finns med väljer du **återskapa metoder** i åtgärdsfönstret för att lägga till den.</span><span class="sxs-lookup"><span data-stu-id="2b765-148">If it isn't, select **Regenerate methods** on the Action Pane to add it.</span></span>

### <a name="configure-a-wave-template"></a><span data-ttu-id="2b765-149">Konfigurera en påfyllnadsmall</span><span class="sxs-lookup"><span data-stu-id="2b765-149">Configure a wave template</span></span>

<span data-ttu-id="2b765-150">Med påfyllnadsmallar kan du länka specifika förekomster av påfyllnadsmetoder till en motsvarande påfyllnadsetikettsmall.</span><span class="sxs-lookup"><span data-stu-id="2b765-150">Wave templates let you link specific instances of wave methods to a corresponding wave label template.</span></span>

1. <span data-ttu-id="2b765-151">Gå till **Lagerstyrning \> Inställningar \> Påfyllnader \> Påfyllnadsmallar**.</span><span class="sxs-lookup"><span data-stu-id="2b765-151">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
1. <span data-ttu-id="2b765-152">Välj en mall som **62 standard för leverans**.</span><span class="sxs-lookup"><span data-stu-id="2b765-152">Select a template, such as **62 Shipping Default**.</span></span>
1. <span data-ttu-id="2b765-153">På snabbfliken **metoder** flyttar du metoden **utskrift av påfyllnadsetiketter** till kolumnen **valda metoder**.</span><span class="sxs-lookup"><span data-stu-id="2b765-153">On the **Methods** FastTab, move the **Wave label printing** method to the **Selected methods** column.</span></span>
1. <span data-ttu-id="2b765-154">I kolumnen **Valda metoder** välj metoden **Utskrift av påfyllnadsetiketter** och ange dess fält **Kod för påfyllnadssteg** till *PrintLabel*.</span><span class="sxs-lookup"><span data-stu-id="2b765-154">In the **Selected methods** column, select the **Wave label printing** method, and set its **Wave step code** field to *PrintLabel*.</span></span> <span data-ttu-id="2b765-155">För mer information om koder för påfyllnadssteg, se [Koder för påfyllnadssteg](wave-step-codes.md).</span><span class="sxs-lookup"><span data-stu-id="2b765-155">For more information about wave step codes, see [Wave step codes](wave-step-codes.md).</span></span>

### <a name="create-a-wave-label-layout"></a><span data-ttu-id="2b765-156">Skapa en layout för påfyllnadsetiketten</span><span class="sxs-lookup"><span data-stu-id="2b765-156">Create a wave label layout</span></span>

<span data-ttu-id="2b765-157">Etikettlayouten bestämmer vilken information som ska skrivas ut på etiketten och hur den visas. Här anger du koden för ZPL som skickas till skrivaren.</span><span class="sxs-lookup"><span data-stu-id="2b765-157">The label layout controls what information is printed on the label and how it's laid out. Here, you enter the ZPL code that is sent to the printer.</span></span>

1. <span data-ttu-id="2b765-158">Gå till **Lagerstyrning \> Inställningar \> Dokumentflöde \> Layout för påfyllnadsetikett**.</span><span class="sxs-lookup"><span data-stu-id="2b765-158">Go to **Warehouse management \> Setup \> Document routing \> Wave label layouts**.</span></span>
1. <span data-ttu-id="2b765-159">Skapa en post med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="2b765-159">Create a record that has the following settings:</span></span>

    - <span data-ttu-id="2b765-160">**Etikettlayout-ID:** *kartong*</span><span class="sxs-lookup"><span data-stu-id="2b765-160">**Label layout ID:** *Carton*</span></span>
    - <span data-ttu-id="2b765-161">**Beskrivning:** *kartong (SSCC)*</span><span class="sxs-lookup"><span data-stu-id="2b765-161">**Description:** *Carton (SSCC)*</span></span>

1. <span data-ttu-id="2b765-162">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="2b765-162">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="2b765-163">I åtgärdsfönstret, välj **Inställningar för påfyllnadsetikettrad**.</span><span class="sxs-lookup"><span data-stu-id="2b765-163">On the Action Pane, select **Wave label row settings**.</span></span>

    <span data-ttu-id="2b765-164">Sidan **Inställningar för påfyllnadsetikettrad** visas.</span><span class="sxs-lookup"><span data-stu-id="2b765-164">The **Wave label row settings** page appears.</span></span> <span data-ttu-id="2b765-165">Här kan du konfigurera den dynamiska delen av etiketten.</span><span class="sxs-lookup"><span data-stu-id="2b765-165">Here, you can configure the dynamic part of the label.</span></span>

1. <span data-ttu-id="2b765-166">Lägg till en rad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="2b765-166">Add a row that has the following settings:</span></span>

    - <span data-ttu-id="2b765-167">**Rad-ID:** *WaveLabel*</span><span class="sxs-lookup"><span data-stu-id="2b765-167">**Row Id:** *WaveLabel*</span></span>
    - <span data-ttu-id="2b765-168">**Radtabellnamn:** *WHSWaveLabel*</span><span class="sxs-lookup"><span data-stu-id="2b765-168">**Row table name:** *WHSWaveLabel*</span></span>
    - <span data-ttu-id="2b765-169">**Radens startposition:** *0*</span><span class="sxs-lookup"><span data-stu-id="2b765-169">**Row start position:** *0*</span></span>

        <span data-ttu-id="2b765-170">I det här fältet definieras den lodräta position där raden ska börja etiketten.</span><span class="sxs-lookup"><span data-stu-id="2b765-170">This field defines the vertical position where the row will begin on the label.</span></span>

    - <span data-ttu-id="2b765-171">**Radhöjd:** *0*</span><span class="sxs-lookup"><span data-stu-id="2b765-171">**Row height:** *0*</span></span>

        <span data-ttu-id="2b765-172">I det här fältet definieras höjden på varje rad (i punkter) enligt ZPL-standard.</span><span class="sxs-lookup"><span data-stu-id="2b765-172">This field defines the height of each row (in points), according to the ZPL standard.</span></span> <span data-ttu-id="2b765-173">Radhöjden är positiv för vågräta etiketter och är negativ för lodräta etiketter.</span><span class="sxs-lookup"><span data-stu-id="2b765-173">The row height is positive for horizontal labels and negative for vertical labels.</span></span> <span data-ttu-id="2b765-174">Eftersom det bara finns en rad i det här exemplet kan du ställa in värdet på *0* (noll).</span><span class="sxs-lookup"><span data-stu-id="2b765-174">Because there is just one row in this example, you can set the value to *0* (zero).</span></span>

    - <span data-ttu-id="2b765-175">**Rader per sida:** *1*</span><span class="sxs-lookup"><span data-stu-id="2b765-175">**Rows per page:** *1*</span></span>

        <span data-ttu-id="2b765-176">I det här fältet definieras antalet rader som kan skrivas ut på varje etikett.</span><span class="sxs-lookup"><span data-stu-id="2b765-176">This field defines the number of rows that can be printed on each label.</span></span>

        > [!NOTE]
        > <span data-ttu-id="2b765-177">Den här inställningen gör att en separat ZPL-etikett skrivs ut för varje post i tabellen med påfyllnadsetiketter.</span><span class="sxs-lookup"><span data-stu-id="2b765-177">This setup will cause a separate ZPL label to be printed for each record in the wave labels table.</span></span>

1. <span data-ttu-id="2b765-178">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="2b765-178">Close the page.</span></span>
1. <span data-ttu-id="2b765-179">I åtgärdsfönstret väljer du **Redigera fråga**.</span><span class="sxs-lookup"><span data-stu-id="2b765-179">On the Action Pane, select **Edit query**.</span></span>
1. <span data-ttu-id="2b765-180">I frågeredigerarens dialogruta, på fliken **Intervall** lägg till en rad med följande värden:</span><span class="sxs-lookup"><span data-stu-id="2b765-180">In the query editor dialog box, on the **Range** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="2b765-181">**Tabell:** *Arbetsrader*</span><span class="sxs-lookup"><span data-stu-id="2b765-181">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="2b765-182">**Härlett register:** *Arbetsrader*</span><span class="sxs-lookup"><span data-stu-id="2b765-182">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="2b765-183">**Fält:** *arbetstyp*</span><span class="sxs-lookup"><span data-stu-id="2b765-183">**Field:** *Work type*</span></span>
    - <span data-ttu-id="2b765-184">**Kriterier:** *Plocka*</span><span class="sxs-lookup"><span data-stu-id="2b765-184">**Criteria:** *Pick*</span></span>

    <span data-ttu-id="2b765-185">Den här frågan ser till att endast arbetsrader av typen plockning skrivs ut på etiketten, inte artikelrader av typen radtyp.</span><span class="sxs-lookup"><span data-stu-id="2b765-185">This query ensures that only pick-type work lines will be printed on the label, not put-type work lines.</span></span>

1. <span data-ttu-id="2b765-186">Om du vill kunna skriva ut fraktsedels-ID väljer du på fliken **kopplingar**, sedan **arbetsrader** och kopplar tabellen **leveranser** till den.</span><span class="sxs-lookup"><span data-stu-id="2b765-186">If you want to be able to print the bill of lading ID, on the **Joins** tab, select the **Work lines** table, and join the **Shipments** table to it.</span></span>
1. <span data-ttu-id="2b765-187">Stäng dialogrutan frågeredigeraren.</span><span class="sxs-lookup"><span data-stu-id="2b765-187">Close the query editor dialog box.</span></span>
1. <span data-ttu-id="2b765-188">På snabbfliken **Layout för skrivartext** finns tre avsnitt där du kan skriva skrivarkod: **rubrikavsnitt**, **brödtext** och **sidfotsavsnitt**.</span><span class="sxs-lookup"><span data-stu-id="2b765-188">The **Printer text Layout** FastTab has three sections where you can write printer code: **Header section**, **Body section**, and **Footer section**.</span></span> <span data-ttu-id="2b765-189">I avsnittet **rubrikavsnitt** i fältet **etikettrubrik** anger du koden för önskad rubrik.</span><span class="sxs-lookup"><span data-stu-id="2b765-189">In the **Header section** section, in the **Label header** field, enter code for the required header.</span></span> <span data-ttu-id="2b765-190">Om du till exempel använder Zebra-skrivare kan du använda följande kod.</span><span class="sxs-lookup"><span data-stu-id="2b765-190">For example, if you're using Zebra printers, you can use the following code.</span></span>

    ```plaintext
    CT~~CD,~CC^~CT~
    ^XA~TA000~JSN^LT0^MNW^MTT^PON^PMN^LH0,0^JMA^PR8,8~SD15^JUS^LRN^CI0^XZ
    ^XA
    ^MMT
    ^PW812
    ^LL1218
    ^LS0
    ^FT85,505^A0N,28,28^FH\^FD$WHSShipmentTable.CustomerReq$^FS
    ^FO1,173^GB809,0,1^FS
    ^FO0,391^GB809,0,1^FS
    ^FO3,599^GB809,0,2^FS
    ^FO420,176^GB0,216,1^FS
    ^FO313,3^GB0,169,1^FS
    ^FO0,807^GB809,0,1^FS
    ^FT529,370^A0N,28,26^FH\^FD$WHSShipmentTable.BillOfLadingId$^FS
    ^BY2,3,132^FT25,344^BCN,,N,N
    ^FD>:(420)>38102>63^FS
    ^FT526,315^A0N,28,28^FH\^FD ^FS
    ^FT437,248^A0N,28,28^FH\^FDCARR: $WHSShipmentTable.SCAC$^FS
    ^FT425,201^A0N,23,24^FH\^FDCARRIER:^FS
    ^FT17,68^A0N,20,19^FH\^FDIntershipping, Inc.^FS
    ^FT15,99^A0N,20,19^FH\^FD1000 Shipping Lane^FS
    ^FT16,158^A0N,20,19^FH\^FD ^FS
    ^FT438,368^A0N,28,28^FH\^FDB/L#^FS
    ^FT15,128^A0N,20,19^FH\^FDShelbyville TN 38102^FS
    ^FT19,203^A0N,23,24^FH\^FD(420) SHIP TO POSTAL CODE^FS
    ^FT331,39^A0N,28,28^FH\^FDShip To:^FS
    ^FT14,39^A0N,28,28^FH\^FDShip From:^FS
    ^FT331,67^A0N,23,24^FH\^FDWAL-MART DC 1111A-ABC DIS^FS
    ^FT330,98^A0N,23,24^FH\^FDDEPT 10^FS
    ^FT329,166^A0N,23,24^FH\^FDSpringfield TN 39021^FS
    ^FT330,134^A0N,23,24^FH\^FD100 Main Street^FS
    ^FT19,504^A0N,28,28^FH\^FDPO#:^FS
    ^FT437,316^A0N,28,28^FH\^FDPRO#^FS
    ^FT105,371^A0N,28,28^FB130,1,0,C^FH\^FD(420)39021^FS
    ```

1. <span data-ttu-id="2b765-191">I avsnittet **brödtext** i fältet **etikettext** anger du ZPL-koden för önskad text.</span><span class="sxs-lookup"><span data-stu-id="2b765-191">In the **Body section** section, in the **Label body** field, enter ZPL code for the required body.</span></span> <span data-ttu-id="2b765-192">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="2b765-192">Here is an example.</span></span>

    ```plaintext
    <Row name="WaveLabel">
    ^FT127,439^A0N,28,28^FH\^FD$WHSWaveLabel.SeqNum$^FS
    ^FT256,439^A0N,28,28^FH\^FD$WHSWaveLabel.NumberOfLabels$^FS
    ^FT17,439^A0N,28,28^FH\^FDCARTON^FS
    ^FT522,422^A0N,23,24^FH\^FDVPN:^FS
    ^FT74,1156^A0N,28,28^FH\^FDSSCC-18^FS
    ^FT21,579^A0N,28,28^FH\^FDItem name:^FS
    ^FT107,580^A0N,28,28^FH\^FD$WHSWaveLabel.LabelItemName$^FS
    ^FT576,423^A0N,23,21^FH\^FD$WHSWaveLabel.LabelItemId$^FS
    ^FT252,1155^A0N,32,31^FH\^FD(00)$WHSWaveLabel.WaveLabelId$^FS
    ^BY4,3,283^FT66,1115^BCN,,N,N
    ^FD>;>800$WHSWaveLabel.WaveLabelId$^FS
    ^FT194,439^A0N,28,28^FH\^FDof^FS
    </Row>
    ```

1. <span data-ttu-id="2b765-193">I avsnittet **brödtext** i fältet **etikettsidfot** anger du ZPL-koden för önskad sidfot.</span><span class="sxs-lookup"><span data-stu-id="2b765-193">In the **Body section** section, in the **Label footer** field, enter ZPL code for the required footer.</span></span> <span data-ttu-id="2b765-194">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="2b765-194">Here is an example.</span></span>

    ```plaintext
    ^PQ1^XZ
    ```

    > [!NOTE]
    > <span data-ttu-id="2b765-195">Installationen kommer att skriva ut en kopia av varje etikett.</span><span class="sxs-lookup"><span data-stu-id="2b765-195">This setup will print one copy of each label.</span></span> <span data-ttu-id="2b765-196">Om du vill ha fler kopior (t.ex. en kopia för varje sida av lastpallen) anger du värdet **n** för avsnittet **\^PQn** i sidfoten till det antal kopior som krävs.</span><span class="sxs-lookup"><span data-stu-id="2b765-196">If you require more copies (for example, one copy for each side of the pallet), set the **n** value for the **\^PQn** section in the footer to the required number of copies.</span></span> <span data-ttu-id="2b765-197">Om du till exempel vill skriva ut fyra kopior av varje etikett anger du **\^PQ4**.</span><span class="sxs-lookup"><span data-stu-id="2b765-197">For example, to print four copies of each label, specify **\^PQ4**.</span></span>

<span data-ttu-id="2b765-198">Nu kan du använda din etikett.</span><span class="sxs-lookup"><span data-stu-id="2b765-198">Your label is now ready to use.</span></span>

### <a name="create-a-wave-label-type"></a><span data-ttu-id="2b765-199">Skapa en typ för påfyllnadsetiketten</span><span class="sxs-lookup"><span data-stu-id="2b765-199">Create a wave label type</span></span>

<span data-ttu-id="2b765-200">Påfyllnadsetikettyper används för att länka påfyllnadsetikettmallar till en enhet på enhetssekvensgrupprader.</span><span class="sxs-lookup"><span data-stu-id="2b765-200">Wave label types are used to link wave label templates to a unit on unit sequence group lines.</span></span>

1. <span data-ttu-id="2b765-201">Gå till **Lagerstyrning \> Inställningar \> Dokumentflöde \> Typer av påfyllnadsetikett**.</span><span class="sxs-lookup"><span data-stu-id="2b765-201">Go to **Warehouse management \> Setup \> Document routing \> Wave label types**.</span></span>
1. <span data-ttu-id="2b765-202">Lägg till en typ av påfyllnadsetikett med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="2b765-202">Add a wave label type that has the following settings:</span></span>

    - <span data-ttu-id="2b765-203">**Etikettyp:** *kartong*</span><span class="sxs-lookup"><span data-stu-id="2b765-203">**Label type:** *Carton*</span></span>
    - <span data-ttu-id="2b765-204">**Beskrivning:** *kartong*</span><span class="sxs-lookup"><span data-stu-id="2b765-204">**Description:** *Carton*</span></span>

### <a name="set-up-unit-sequence-groups"></a><span data-ttu-id="2b765-205">Konfigurera enhetssekvensgrupper</span><span class="sxs-lookup"><span data-stu-id="2b765-205">Set up unit sequence groups</span></span>

<span data-ttu-id="2b765-206">Ställ sedan in enhetsseriegruppen för typ av påfyllnadsnivå.</span><span class="sxs-lookup"><span data-stu-id="2b765-206">Next, set up the unit sequence group for the wave label type.</span></span>

1. <span data-ttu-id="2b765-207">Gå till **Lagerstyrning \> Inställningar \> Lagerställe \> Enhetsseriegrupp**.</span><span class="sxs-lookup"><span data-stu-id="2b765-207">Go to **Warehouse management \> Setup \> Warehouse \> Unit sequence groups**.</span></span>
1. <span data-ttu-id="2b765-208">Välj gruppen **Ea Box PL**.</span><span class="sxs-lookup"><span data-stu-id="2b765-208">Select the **Ea Box PL** group.</span></span>
1. <span data-ttu-id="2b765-209">För raden **ruta** ange fältet **typ av påfyllnadsnivå** till *kartong*.</span><span class="sxs-lookup"><span data-stu-id="2b765-209">For the **Box** line, set the **Wave level type** field to *Carton*.</span></span>

### <a name="create-a-wave-label-template"></a><span data-ttu-id="2b765-210">Skapa en mall för påfyllnadsetikett</span><span class="sxs-lookup"><span data-stu-id="2b765-210">Create a wave label template</span></span>

<span data-ttu-id="2b765-211">Skapa sedan mall för påfyllnadsetikett för typen av påfyllnadsetikett.</span><span class="sxs-lookup"><span data-stu-id="2b765-211">Next, create the wave label template for the wave label type.</span></span>

1. <span data-ttu-id="2b765-212">Gå till **Lagerstyrning \> Inställningar \> Dokumentflöde \> Mall för påfyllnadsetikett**.</span><span class="sxs-lookup"><span data-stu-id="2b765-212">Go to **Warehouse management \> Setup \> Document routing \> Wave label templates**.</span></span>
1. <span data-ttu-id="2b765-213">Lägg till en mall för påfyllnadsnivå och ange följande värden i rubriken:</span><span class="sxs-lookup"><span data-stu-id="2b765-213">Add a wave level template, and set the following values in the header:</span></span>

    - <span data-ttu-id="2b765-214">**Namn på etikettmallen:** *kartongetiketter*</span><span class="sxs-lookup"><span data-stu-id="2b765-214">**Label template name:** *Carton labels*</span></span>
    - <span data-ttu-id="2b765-215">**Beskrivning:** *kartongetiketter*</span><span class="sxs-lookup"><span data-stu-id="2b765-215">**Description:** *Carton labels*</span></span>
    - <span data-ttu-id="2b765-216">**Kod för påfyllnadssteg:** *PrintLabel*</span><span class="sxs-lookup"><span data-stu-id="2b765-216">**Wave step code:** *PrintLabel*</span></span>
    - <span data-ttu-id="2b765-217">**Lagerställe:** *62*</span><span class="sxs-lookup"><span data-stu-id="2b765-217">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="2b765-218">På snabbfliken **Allmänt** ställer du in fältet **typ av påfyllnadsetikett** till *kartong*.</span><span class="sxs-lookup"><span data-stu-id="2b765-218">On the **General** FastTab, set the **Wave label type** field to *Carton*.</span></span>
1. <span data-ttu-id="2b765-219">På snabbfliken **information om påfyllnadsetikettens mall** och lägg till en ny rad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="2b765-219">On the **Wave label template details** FastTab, add a new row that has the following settings:</span></span>

    - <span data-ttu-id="2b765-220">**Etikettlayout-ID:** *kartong*</span><span class="sxs-lookup"><span data-stu-id="2b765-220">**Label layout ID:** *Carton*</span></span>
    - <span data-ttu-id="2b765-221">**Skrivarnamn:** Välj en lämplig ZPL-skrivare.</span><span class="sxs-lookup"><span data-stu-id="2b765-221">**Printer name:** Select an appropriate ZPL printer.</span></span>
    - <span data-ttu-id="2b765-222">**Kör fråga:** *Ja* (den här inställningen är valfri, men rekommenderas för optimal prestanda.)</span><span class="sxs-lookup"><span data-stu-id="2b765-222">**Run query:** *Yes* (This setting is optional, but it's recommended for optimal performance.)</span></span>

1. <span data-ttu-id="2b765-223">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="2b765-223">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="2b765-224">Valfritt: om du ställer in en kundspecifik etikettdesign måste du skapa en fråga för att hitta kundens konto.</span><span class="sxs-lookup"><span data-stu-id="2b765-224">Optional: If you're setting up a customer-specific label design, you must create a query to find the customer's account.</span></span> <span data-ttu-id="2b765-225">På snabbfliken **information om påfyllnadsetikettens mall** välj **Redigera fråga**.</span><span class="sxs-lookup"><span data-stu-id="2b765-225">On the **Wave label template details** FastTab, select **Edit query**.</span></span> <span data-ttu-id="2b765-226">I frågeredigerarens dialogruta, på fliken **Intervall** lägg till en rad med följande värden:</span><span class="sxs-lookup"><span data-stu-id="2b765-226">Then, in the query editor dialog box, on the **Range** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="2b765-227">**Register:** *försändelser*</span><span class="sxs-lookup"><span data-stu-id="2b765-227">**Table:** *Shipments*</span></span>
    - <span data-ttu-id="2b765-228">**Härlett register:** *försändelser*</span><span class="sxs-lookup"><span data-stu-id="2b765-228">**Derived table:** *Shipments*</span></span>
    - <span data-ttu-id="2b765-229">**Fält:** *Kontonummer*</span><span class="sxs-lookup"><span data-stu-id="2b765-229">**Field:** *Account number*</span></span>
    - <span data-ttu-id="2b765-230">**Kriterier:** Ange relevant kundkontonummer.</span><span class="sxs-lookup"><span data-stu-id="2b765-230">**Criteria:** Enter the relevant customer account number.</span></span>

    <span data-ttu-id="2b765-231">När du är klar klickar du på **OK** för att stänga dialogrutan för frågeredigeraren.</span><span class="sxs-lookup"><span data-stu-id="2b765-231">When you've finished, select **OK** to close the query editor dialog box.</span></span>

1. <span data-ttu-id="2b765-232">I åtgärdsfönstret, välj **Redigera fråga** för att öppna en dialogruta för frågeredigeraren för hela etikettmallen.</span><span class="sxs-lookup"><span data-stu-id="2b765-232">On the Action Pane, select **Edit query** to open the query editor dialog box for the whole label template.</span></span>
1. <span data-ttu-id="2b765-233">I frågeredigerarens dialogruta, på fliken **Sortera** lägg till en rad med följande värden:</span><span class="sxs-lookup"><span data-stu-id="2b765-233">In the query editor dialog box, on the **Sorting** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="2b765-234">**Tabell:** *Arbetsrader*</span><span class="sxs-lookup"><span data-stu-id="2b765-234">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="2b765-235">**Härlett register:** *Arbetsrader*</span><span class="sxs-lookup"><span data-stu-id="2b765-235">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="2b765-236">**Fält:** *referens till läs in rad-ID (post-ID)*</span><span class="sxs-lookup"><span data-stu-id="2b765-236">**Field:** *Reference load line id (Record-ID)*</span></span>
    - <span data-ttu-id="2b765-237">**Sökriktning:** *Stigande*</span><span class="sxs-lookup"><span data-stu-id="2b765-237">**Search direction:** *Ascending*</span></span>

1. <span data-ttu-id="2b765-238">Stäng dialogrutan för frågeredigeraren genom att välja **OK**.</span><span class="sxs-lookup"><span data-stu-id="2b765-238">Select **OK** to close the query editor dialog box.</span></span>
1. <span data-ttu-id="2b765-239">En meddelande ruta ber dig bekräfta åtgärden grupperingsåterställning.</span><span class="sxs-lookup"><span data-stu-id="2b765-239">A message box prompts you to confirm the grouping reset operation.</span></span> <span data-ttu-id="2b765-240">Klicka på **Ja** när du vill fortsätta.</span><span class="sxs-lookup"><span data-stu-id="2b765-240">Select **Yes** to continue.</span></span>
1. <span data-ttu-id="2b765-241">I åtgärdsfönstret, välj **mallgruppen för påfyllnadsetikett**.</span><span class="sxs-lookup"><span data-stu-id="2b765-241">On the Action Pane, select **Wave label template group**.</span></span>
1. <span data-ttu-id="2b765-242">I dialogrutan **mallgruppen för påfyllnadsetikett** välj raden där fältet **referensfältnamn** anges till *referens till läs in rad-ID* och markerar sedan kryssrutan **etikettversions-ID** för den här raden.</span><span class="sxs-lookup"><span data-stu-id="2b765-242">In the **Wave label template group** dialog box, select the row where the **Reference field name** field is set to *Reference load line id*, and then select the **Label build ID** check box for this row.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2b765-243">Med den här inställningen skapas en etikettserie ("kartong 1 av X") per lastrad i hela påfyllnaden, oavsett inställningen för arbetsgrupperingen.</span><span class="sxs-lookup"><span data-stu-id="2b765-243">This setup will create one label sequence ("Carton 1 of X") per load line throughout the wave, regardless of the work grouping setup.</span></span> <span data-ttu-id="2b765-244">Denna etikettserie kan skrivas ut på etikettlayouten.</span><span class="sxs-lookup"><span data-stu-id="2b765-244">This label sequence can be printed on the label layout.</span></span>

### <a name="configure-number-sequence-extensions"></a><span data-ttu-id="2b765-245">Konfigurera nummerserietillägg</span><span class="sxs-lookup"><span data-stu-id="2b765-245">Configure number sequence extensions</span></span>

<span data-ttu-id="2b765-246">Nummerserietillägg styr GS1 efterlevnaden av specifika nummerserier.</span><span class="sxs-lookup"><span data-stu-id="2b765-246">Number sequence extensions control the GS1 compliance of specific number sequences.</span></span> <span data-ttu-id="2b765-247">Den här konfigurationen är valfri för det aktuella scenariot.</span><span class="sxs-lookup"><span data-stu-id="2b765-247">This configuration is optional for the current scenario.</span></span> <span data-ttu-id="2b765-248">Mer information och instruktioner för konfigurering finns i [Konfigurera tillägg för nummerserier](../warehousing/configure-number-sequence-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="2b765-248">For more information and configuration instructions, see [Configure number sequence extensions](../warehousing/configure-number-sequence-extensions.md).</span></span>

### <a name="create-a-sales-order-and-release-it-to-the-warehouse"></a><span data-ttu-id="2b765-249">Skapa en försäljningsorder och släpp den på lagerstället</span><span class="sxs-lookup"><span data-stu-id="2b765-249">Create a sales order and release it to the warehouse</span></span>

1. <span data-ttu-id="2b765-250">Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="2b765-250">Go to **Sales and marketing \> Sales order \> All sales orders**.</span></span>
1. <span data-ttu-id="2b765-251">Skapa en försäljningsorder med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="2b765-251">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="2b765-252">**Kundkonto:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="2b765-252">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="2b765-253">**Lagerställe:** *62*</span><span class="sxs-lookup"><span data-stu-id="2b765-253">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="2b765-254">Lägg till två försäljningsorderrader med följande inställning:</span><span class="sxs-lookup"><span data-stu-id="2b765-254">Add two sales order lines that have the following settings:</span></span>

    - <span data-ttu-id="2b765-255">Försäljningsorderrad 1:</span><span class="sxs-lookup"><span data-stu-id="2b765-255">Sales order line 1:</span></span>

        - <span data-ttu-id="2b765-256">**Artikelnummer:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="2b765-256">**Item number:** *A0001*</span></span>
        - <span data-ttu-id="2b765-257">**Kvantitet:** *9024*</span><span class="sxs-lookup"><span data-stu-id="2b765-257">**Quantity:** *9024*</span></span>
        - <span data-ttu-id="2b765-258">**Enhet:** *ea* (9024 ea = 376 låda = 47 PL)</span><span class="sxs-lookup"><span data-stu-id="2b765-258">**Unit:** *ea* (9024 ea = 376 Box = 47 PL)</span></span>

    - <span data-ttu-id="2b765-259">Försäljningsorderrad 2:</span><span class="sxs-lookup"><span data-stu-id="2b765-259">Sales order line 2:</span></span>

        - <span data-ttu-id="2b765-260">**Artikelnummer:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="2b765-260">**Item number:** *A0002*</span></span>
        - <span data-ttu-id="2b765-261">**Kvantitet:** *9016*</span><span class="sxs-lookup"><span data-stu-id="2b765-261">**Quantity:** *9016*</span></span>
        - <span data-ttu-id="2b765-262">**Enhet:** *ea* (9016 ea = 322 box = 46 PL)</span><span class="sxs-lookup"><span data-stu-id="2b765-262">**Unit:** *ea* (9016 ea = 322 Box = 46 PL)</span></span>

    > [!NOTE]
    > <span data-ttu-id="2b765-263">Artiklarna och kvantiteterna som anges här är endast exempel.</span><span class="sxs-lookup"><span data-stu-id="2b765-263">The items and quantities that are provided here are only examples.</span></span> <span data-ttu-id="2b765-264">De måste använda den enhetsseriegrupp som du definierade tidigare, och lämpliga enhetskonverteringar från *ea* till *Box* till *PL* måste definieras för dem och de måste ha lager i lagerställe *62*.</span><span class="sxs-lookup"><span data-stu-id="2b765-264">They must use the unit sequence group that you defined earlier, appropriate unit conversions from *ea* to *Box* to *PL* must be defined for them, and they must have stock in warehouse *62*.</span></span> <span data-ttu-id="2b765-265">Mer information finns i [måttenhet och lagerprinciper](unit-measure-stocking-policies.md).</span><span class="sxs-lookup"><span data-stu-id="2b765-265">For more information, see [Unit of measure and stocking policies](unit-measure-stocking-policies.md).</span></span>

1. <span data-ttu-id="2b765-266">Välj försäljningsorderrad 1.</span><span class="sxs-lookup"><span data-stu-id="2b765-266">Select sales order line 1.</span></span> <span data-ttu-id="2b765-267">I avsnittet **Försäljningsorderrad** i menyn **Lager** välj **Reservationer**.</span><span class="sxs-lookup"><span data-stu-id="2b765-267">Then, in the **Sales order line** section, on the **Inventory** menu, select **Reservations**.</span></span>
1. <span data-ttu-id="2b765-268">På sidan **Reservation** i åtgärdsfönstret, välj **Reservera parti** och stäng sedan sidan.</span><span class="sxs-lookup"><span data-stu-id="2b765-268">On the **Reservation** page, on the Action Pane, select **Reserve lot**, and then close the page.</span></span>
1. <span data-ttu-id="2b765-269">Upprepa steg 4 och 5 för försäljningsorderrad 2.</span><span class="sxs-lookup"><span data-stu-id="2b765-269">Repeat steps 4 and 5 for sales order line 2.</span></span>
1. <span data-ttu-id="2b765-270">I åtgärdsfönstret på fliken **Lagerställe** välj **Frisläpp till regel för lagerställe**.</span><span class="sxs-lookup"><span data-stu-id="2b765-270">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="2b765-271">Då inträffar följande händelser:</span><span class="sxs-lookup"><span data-stu-id="2b765-271">The following events occur:</span></span>

    - <span data-ttu-id="2b765-272">I systemet bearbetas den skapade utleveransen med hjälp av mallen som inkluderar utskriftssteget för etikett.</span><span class="sxs-lookup"><span data-stu-id="2b765-272">The system processes the created shipment by using the template that includes the label printing step.</span></span> <span data-ttu-id="2b765-273">Etikettlayouten används för att definiera etikettens format, och resultatet blir en etikett som skrivs ut på den skrivare som väljs i etikettmallen.</span><span class="sxs-lookup"><span data-stu-id="2b765-273">The label layout will be used to define the format of the label, and the result will be a label that is printed on the printer that is selected in the label template.</span></span>
    - <span data-ttu-id="2b765-274">Påfyllnadsetiketter genereras och skrivs ut.</span><span class="sxs-lookup"><span data-stu-id="2b765-274">Wave labels are generated and printed.</span></span> <span data-ttu-id="2b765-275">Antalet etiketter är lika med antalet kartonger (i det här exemplet är 376 boxetiketter för rad 1 och 322 boxetiketter för rad 2).</span><span class="sxs-lookup"><span data-stu-id="2b765-275">The number of labels will equal the number of cartons (in this example, 376 Box labels for line 1 and 322 Box labels for line 2).</span></span>
    - <span data-ttu-id="2b765-276">Ett nytt fraktsedels-ID genereras för leveranserna.</span><span class="sxs-lookup"><span data-stu-id="2b765-276">A new bill of lading ID is generated for the shipments.</span></span> <span data-ttu-id="2b765-277">Om du har konfigurerat nummerserietilläggen följer påfyllnadsetikett-ID nummerformatet **SSCC-18**.</span><span class="sxs-lookup"><span data-stu-id="2b765-277">If you configured the number sequence extensions, the wave label IDs will follow the **SSCC-18** number format.</span></span> 

<span data-ttu-id="2b765-278">Du kan visa och skriva ut påfyllnadsetiketter på följande sidor.</span><span class="sxs-lookup"><span data-stu-id="2b765-278">You can view and reprint wave labels from the following pages.</span></span> <span data-ttu-id="2b765-279">I åtgärdsfönstret, på varje sida, på fliken **Leveranser**, i gruppen **Relaterad information**, väljer du **påfyllnadsetiketter**.</span><span class="sxs-lookup"><span data-stu-id="2b765-279">On the Action Pane of each page, on the **Shipments** tab, in the **Related information** group, select **Wave labels**.</span></span>

- <span data-ttu-id="2b765-280">Alla leveranser \> leveransinformation</span><span class="sxs-lookup"><span data-stu-id="2b765-280">All shipments \> Shipment details</span></span>
- <span data-ttu-id="2b765-281">Alla laster \> Läs in information</span><span class="sxs-lookup"><span data-stu-id="2b765-281">All loads \> Load details</span></span>
- <span data-ttu-id="2b765-282">Alla påfyllnader</span><span class="sxs-lookup"><span data-stu-id="2b765-282">All waves</span></span>
- <span data-ttu-id="2b765-283">Påfyllnadsetiketter</span><span class="sxs-lookup"><span data-stu-id="2b765-283">Wave labels</span></span>
- <span data-ttu-id="2b765-284">Etiketthistorik för påfyllnad</span><span class="sxs-lookup"><span data-stu-id="2b765-284">Wave label history</span></span>

## <a name="scenario-2-wave-label-printing-for-containerization-without-wave-label-records"></a><span data-ttu-id="2b765-285">Scenario 2: påfyllnadsetikett utskrift för skapande av behållare (utan påfyllnadsetikettposter)</span><span class="sxs-lookup"><span data-stu-id="2b765-285">Scenario 2: Wave label printing for containerization (without wave label records)</span></span>

<span data-ttu-id="2b765-286">I det här scenariot kan du skriva ut påfyllnadsetiketter när du använder skapande av behållare för att automatiskt dela upp objekt i kartonger och därför inte kräva en påfyllnadsetikettpost.</span><span class="sxs-lookup"><span data-stu-id="2b765-286">This scenario lets you print wave labels when you use containerization to automatically split items into cartons and therefore don't require a wave label record.</span></span> <span data-ttu-id="2b765-287">I det här fallet fungerar behållar-ID som platshållare för SSCC.</span><span class="sxs-lookup"><span data-stu-id="2b765-287">In this case, the container ID acts as a placeholder for the SSCC.</span></span>

<span data-ttu-id="2b765-288">Här är de viktigaste skillnaderna mellan det här scenariot och scenario 1:</span><span class="sxs-lookup"><span data-stu-id="2b765-288">Here are the main differences between this scenario and scenario 1:</span></span>

- <span data-ttu-id="2b765-289">**Mallar för påfyllnadsetiketter:** du väljer ingen typ av påfyllnadsetikett i mallen för påfyllnadsetiketter och du behöver inte använda en gruppering för att skapa etiketter.</span><span class="sxs-lookup"><span data-stu-id="2b765-289">**Wave label templates:** You won't select a wave label type on the wave label template, and you won't require a label build grouping.</span></span> <span data-ttu-id="2b765-290">Annars kan du konfigurera mallen för påfyllnadsetikett och länka till påfyllnadsmallen på samma sätt som beskrivs i scenario 1.</span><span class="sxs-lookup"><span data-stu-id="2b765-290">Otherwise, you will configure the wave label template and link to the wave template in the same way that is described in scenario 1.</span></span> <span data-ttu-id="2b765-291">Du måste lämna typ av påfyllnadsetikett tom om du vill förhindra att påfyllnadsetiketter genereras.</span><span class="sxs-lookup"><span data-stu-id="2b765-291">You must leave the wave label type blank to prevent wave labels from being generated.</span></span>
- <span data-ttu-id="2b765-292">**Layout för påfyllnadsetiketter:** du kan konfigurera radinställningarna för layouten för påfyllnadsetiketter för arbetsrader i stället för påfyllnadsetikettposter.</span><span class="sxs-lookup"><span data-stu-id="2b765-292">**Wave label layouts:** You will configure the wave label layout row settings for work lines instead of wave label records.</span></span> <span data-ttu-id="2b765-293">Du måste konfigurera radinställningen för etikettlayout med hjälp av registret **WHSWorkLine** i stället för registret **WHSWaveLabel**.</span><span class="sxs-lookup"><span data-stu-id="2b765-293">You must configure the row setting for the label layout by using the **WHSWorkLine** table instead of the **WHSWaveLabel** table.</span></span> <span data-ttu-id="2b765-294">Inställningen **rader per sida** styr antalet rader som brödtextavsnittet ska ha.</span><span class="sxs-lookup"><span data-stu-id="2b765-294">The **Rows per page** setting controls the number of rows that the body section will have.</span></span> 

<span data-ttu-id="2b765-295">Den här konfigurationen är också lämplig för affärsscenarier där flera olika artiklar förpackas i en etikettruta eller till en lastpall, och denna förpackningsprocess kan definieras genom att arbetet skapas (t.ex. arbete som grupperats per leverans).</span><span class="sxs-lookup"><span data-stu-id="2b765-295">This configuration is also suitable for business scenarios where multiple different items are packed into one labeled box or into a pallet, and this packing process can be defined by work creation (for example, work that is grouped by shipment).</span></span>

<span data-ttu-id="2b765-296">Det här scenariot visar komplett flöde.</span><span class="sxs-lookup"><span data-stu-id="2b765-296">This scenario shows the end-to-end flow.</span></span>

### <a name="make-demo-data-available"></a><span data-ttu-id="2b765-297">Gör demodata tillgängliga</span><span class="sxs-lookup"><span data-stu-id="2b765-297">Make demo data available</span></span>

<span data-ttu-id="2b765-298">För att följa detta scenario måste du ha demonstrationsdata installerad och du måste välja juridiska personen **USMF**.</span><span class="sxs-lookup"><span data-stu-id="2b765-298">To follow this scenario, you must have demo data installed, and you must select the **USMF** legal entity.</span></span>

### <a name="make-sure-that-the-wave-label-method-is-available"></a><span data-ttu-id="2b765-299">Kontrollera att påfyllnadsetikett metoden är tillgänglig</span><span class="sxs-lookup"><span data-stu-id="2b765-299">Make sure that the wave label method is available</span></span>

<span data-ttu-id="2b765-300">Du måste kanske återskapa dina metoder för påfyllnadsprocess för att göra påfyllnadsetikett metoden tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="2b765-300">You might have to regenerate the wave process methods to make the wave label printing method available.</span></span>

1. <span data-ttu-id="2b765-301">Gå till **Lagerstyrning \> Inställningar \> Påfyllnader \> Metoder för påfyllnadsprocess**.</span><span class="sxs-lookup"><span data-stu-id="2b765-301">Go to **Warehouse management \> Setup \> Waves \> Wave process methods**.</span></span>
1. <span data-ttu-id="2b765-302">Kontrollera att **waveLabelPrinting** finns i listan.</span><span class="sxs-lookup"><span data-stu-id="2b765-302">Confirm that **waveLabelPrinting** is in the list.</span></span> <span data-ttu-id="2b765-303">Om den inte finns med väljer du **återskapa metoder** i åtgärdsfönstret för att lägga till den.</span><span class="sxs-lookup"><span data-stu-id="2b765-303">If it isn't, select **Regenerate methods** on the Action Pane to add it.</span></span>

### <a name="set-up-a-wave-template"></a><span data-ttu-id="2b765-304">Ställa in en påfyllnadsmall</span><span class="sxs-lookup"><span data-stu-id="2b765-304">Set up a wave template</span></span>

<span data-ttu-id="2b765-305">Med påfyllnadsmallar kan du länka specifika förekomster av påfyllnadsmetoder till en motsvarande påfyllnadsetikettsmall.</span><span class="sxs-lookup"><span data-stu-id="2b765-305">Wave templates let you link specific instances of wave methods to a corresponding wave label template.</span></span>

1. <span data-ttu-id="2b765-306">Gå till **Lagerstyrning \> Inställningar \> Påfyllnader \> Påfyllnadsmallar**.</span><span class="sxs-lookup"><span data-stu-id="2b765-306">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
1. <span data-ttu-id="2b765-307">Välj en mall som **63 skapande av behållare**.</span><span class="sxs-lookup"><span data-stu-id="2b765-307">Select a template, such as **63 Containerization**.</span></span>
1. <span data-ttu-id="2b765-308">På snabbfliken **metoder** flyttar du metoden **utskrift av påfyllnadsetiketter** till kolumnen **valda metoder**.</span><span class="sxs-lookup"><span data-stu-id="2b765-308">On the **Methods** FastTab, move the **Wave label printing** method to the **Selected methods** column.</span></span>
1. <span data-ttu-id="2b765-309">I kolumnen **Valda metoder** välj metoden **Utskrift av påfyllnadsetiketter** och ange dess fält **Kod för påfyllnadssteg** till *PrintLabel*.</span><span class="sxs-lookup"><span data-stu-id="2b765-309">In the **Selected methods** column, select the **Wave label printing** method, and set its **Wave step code** field to *PrintLabel*.</span></span> <span data-ttu-id="2b765-310">För mer information om koder för påfyllnadssteg, se [Koder för påfyllnadssteg](wave-step-codes.md).</span><span class="sxs-lookup"><span data-stu-id="2b765-310">For more information about wave step codes, see [Wave step codes](wave-step-codes.md).</span></span>

### <a name="create-a-wave-label-layout"></a><span data-ttu-id="2b765-311">Skapa en layout för påfyllnadsetiketten</span><span class="sxs-lookup"><span data-stu-id="2b765-311">Create a wave label layout</span></span>

1. <span data-ttu-id="2b765-312">Gå till **Lagerstyrning \> Inställningar \> Dokumentflöde \> Layout för påfyllnadsetikett**.</span><span class="sxs-lookup"><span data-stu-id="2b765-312">Go to **Warehouse management \> Setup \> Document routing \> Wave label layouts**.</span></span>
1. <span data-ttu-id="2b765-313">Skapa en post med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="2b765-313">Create a record that has the following settings:</span></span>

    - <span data-ttu-id="2b765-314">**Etikettlayout-ID:** *kartong*</span><span class="sxs-lookup"><span data-stu-id="2b765-314">**Label layout ID:** *Carton*</span></span>
    - <span data-ttu-id="2b765-315">**Beskrivning:** *kartong (SSCC)*</span><span class="sxs-lookup"><span data-stu-id="2b765-315">**Description:** *Carton (SSCC)*</span></span>

1. <span data-ttu-id="2b765-316">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="2b765-316">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="2b765-317">I åtgärdsfönstret, välj **Inställningar för påfyllnadsetikettrad**.</span><span class="sxs-lookup"><span data-stu-id="2b765-317">On the Action Pane, select **Wave label row settings**.</span></span>

    <span data-ttu-id="2b765-318">Sidan **Inställningar för påfyllnadsetikettrad** visas.</span><span class="sxs-lookup"><span data-stu-id="2b765-318">The **Wave label row settings** page appears.</span></span> <span data-ttu-id="2b765-319">Här kan du konfigurera den dynamiska delen av etiketten.</span><span class="sxs-lookup"><span data-stu-id="2b765-319">Here, you can configure the dynamic part of the label.</span></span>

1. <span data-ttu-id="2b765-320">Lägg till en rad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="2b765-320">Add a row that has the following settings:</span></span>

    - <span data-ttu-id="2b765-321">**Rad-ID:** *WorkLine*</span><span class="sxs-lookup"><span data-stu-id="2b765-321">**Row Id:** *WorkLine*</span></span>
    - <span data-ttu-id="2b765-322">**Radtabellnamn:** *WHSWorkLine*</span><span class="sxs-lookup"><span data-stu-id="2b765-322">**Row table name:** *WHSWorkLine*</span></span>
    - <span data-ttu-id="2b765-323">**Radens startposition:** *500*</span><span class="sxs-lookup"><span data-stu-id="2b765-323">**Row start position:** *500*</span></span>

        <span data-ttu-id="2b765-324">I det här fältet definieras den lodräta position där raden ska börja etiketten.</span><span class="sxs-lookup"><span data-stu-id="2b765-324">This field defines the vertical position where the row will begin on the label.</span></span>

    - <span data-ttu-id="2b765-325">**Radhöjd:** *-50*</span><span class="sxs-lookup"><span data-stu-id="2b765-325">**Row height:** *-50*</span></span>

        <span data-ttu-id="2b765-326">I det här fältet definieras höjden på varje rad.</span><span class="sxs-lookup"><span data-stu-id="2b765-326">This field defines the height of each row.</span></span> <span data-ttu-id="2b765-327">Radhöjden är positiv för vågräta etiketter och är negativ för lodräta etiketter.</span><span class="sxs-lookup"><span data-stu-id="2b765-327">The row height is positive for horizontal labels and negative for vertical labels.</span></span>

    - <span data-ttu-id="2b765-328">**Rader per sida:** *5*</span><span class="sxs-lookup"><span data-stu-id="2b765-328">**Rows per page:** *5*</span></span>

        <span data-ttu-id="2b765-329">I det här fältet definieras antalet rader som kan skrivas ut på varje etikett.</span><span class="sxs-lookup"><span data-stu-id="2b765-329">This field defines the number of rows that can be printed on each label.</span></span>

        > [!NOTE]
        > <span data-ttu-id="2b765-330">Denna inställning kommer att skriva ut flera ZPL-etiketter per arbete, där varje sida kan innehålla upp till fem arbetsrader.</span><span class="sxs-lookup"><span data-stu-id="2b765-330">This setup will print several ZPL labels per work, where each page can hold up to five work lines.</span></span> <span data-ttu-id="2b765-331">Om en etikett till exempel skrivs ut för en behållare med 12 rader skrivs tre etiketter ut.</span><span class="sxs-lookup"><span data-stu-id="2b765-331">For example, if a label is printed for a container that has 12 lines, three labels will be printed.</span></span> <span data-ttu-id="2b765-332">Om du vill skriva ut en separat etikett för varje plockningsrad anger du det här värdet till *1*.</span><span class="sxs-lookup"><span data-stu-id="2b765-332">If you want to print a separate label for each pick line, set this value to *1*.</span></span>

1. <span data-ttu-id="2b765-333">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="2b765-333">Close the page.</span></span>
1. <span data-ttu-id="2b765-334">I åtgärdsfönstret väljer du **Redigera fråga**.</span><span class="sxs-lookup"><span data-stu-id="2b765-334">On the Action Pane, select **Edit query**.</span></span>
1. <span data-ttu-id="2b765-335">I frågeredigerarens dialogruta, på fliken **Intervall** lägg till en rad med följande värden:</span><span class="sxs-lookup"><span data-stu-id="2b765-335">In the query editor dialog box, on the **Range** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="2b765-336">**Tabell:** *Arbetsrader*</span><span class="sxs-lookup"><span data-stu-id="2b765-336">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="2b765-337">**Härlett register:** *Arbetsrader*</span><span class="sxs-lookup"><span data-stu-id="2b765-337">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="2b765-338">**Fält:** *arbetstyp*</span><span class="sxs-lookup"><span data-stu-id="2b765-338">**Field:** *Work type*</span></span>
    - <span data-ttu-id="2b765-339">**Kriterier:** *Plocka*</span><span class="sxs-lookup"><span data-stu-id="2b765-339">**Criteria:** *Pick*</span></span>

1. <span data-ttu-id="2b765-340">Om du vill kunna skriva ut fraktsedels-ID väljer du på fliken **kopplingar**, sedan **arbetsrader** och kopplar tabellen **leveranser** till den.</span><span class="sxs-lookup"><span data-stu-id="2b765-340">If you want to be able to print the bill of lading ID, on the **Joins** tab, select the **Work lines** table, and join the **Shipments** table to it.</span></span>
1. <span data-ttu-id="2b765-341">Stäng dialogrutan frågeredigeraren.</span><span class="sxs-lookup"><span data-stu-id="2b765-341">Close the query editor dialog box.</span></span>
1. <span data-ttu-id="2b765-342">På snabbfliken **Layout för skrivartext** finns tre avsnitt där du kan skriva skrivarkod: **rubrikavsnitt**, **brödtext** och **sidfotsavsnitt**.</span><span class="sxs-lookup"><span data-stu-id="2b765-342">The **Printer text Layout** FastTab has three sections where you can write printer code: **Header section**, **Body section**, and **Footer section**.</span></span> <span data-ttu-id="2b765-343">I avsnittet **rubrikavsnitt** i fältet **etikettrubrik** anger du koden för önskad rubrik.</span><span class="sxs-lookup"><span data-stu-id="2b765-343">In the **Header section** section, in the **Label header** field, enter code for the required header.</span></span> <span data-ttu-id="2b765-344">Om du till exempel använder Zebra-skrivare kan du använda följande kod.</span><span class="sxs-lookup"><span data-stu-id="2b765-344">For example, if you're using Zebra printers, you can use the following code.</span></span>

    ```plaintext
    CT~~CD,~CC^~CT~
    ^XA
    ^LH10,10
    ^FO0,0 ^AT ^FD$WHSWorkTable.ContainerId$ ^FS
    ^FO0,75 ^AT ^FD$WHSWorkLine.ShipmentId$ ^FS
    ^FO0,150 ^AT ^FD$WHSShipmentTable.BillOfLadingId$ ^FS
    ```

1. <span data-ttu-id="2b765-345">I avsnittet **brödtext** i fältet **etikettext** anger du ZPL-koden för önskad text.</span><span class="sxs-lookup"><span data-stu-id="2b765-345">In the **Body section** section, in the **Label body** field, enter ZPL code for the required body.</span></span> <span data-ttu-id="2b765-346">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="2b765-346">Here is an example.</span></span>

    ```plaintext
    <Row name="WorkLine">
    <Heading>
    //Optional heading for section of rows
    </Heading>
    ^FO0,450 ^AT ^FDItem ^FS
    ^FO200,450 ^AT ^FDQuantity ^FS
    ^FO0,[[YPos]] ^AT ^FD$WHSWorkLine.ItemId$ ^FS
    ^FO200,[[YPos]] ^AT ^FD$WHSWorkLine.QtyWork$ ^FS
    </Row>
    ```

1. <span data-ttu-id="2b765-347">I avsnittet **brödtext** i fältet **etikettsidfot** anger du ZPL-koden för önskad sidfot.</span><span class="sxs-lookup"><span data-stu-id="2b765-347">In the **Body section** section, in the **Label footer** field, enter ZPL code for the required footer.</span></span> <span data-ttu-id="2b765-348">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="2b765-348">Here is an example.</span></span>

    ```plaintext
    ^PQ1^XZ
    ```

    > [!NOTE]
    > <span data-ttu-id="2b765-349">Installationen kommer att skriva ut en kopia av varje etikett.</span><span class="sxs-lookup"><span data-stu-id="2b765-349">This setup will print one copy of each label.</span></span> <span data-ttu-id="2b765-350">Om du vill ha fler kopior (t.ex. en kopia för varje sida av lastpallen) anger du värdet **n** för avsnittet **\^PQn** i sidfoten till det antal kopior som krävs.</span><span class="sxs-lookup"><span data-stu-id="2b765-350">If you require more copies (for example, one copy for each side of the pallet), set the **n** value for the **\^PQn** section in the footer to the required number of copies.</span></span> <span data-ttu-id="2b765-351">Om du till exempel vill skriva ut fyra kopior av varje etikett anger du **\^PQ4**.</span><span class="sxs-lookup"><span data-stu-id="2b765-351">For example, to print four copies of each label, specify **\^PQ4**.</span></span>

<span data-ttu-id="2b765-352">Nu kan du använda din etikett.</span><span class="sxs-lookup"><span data-stu-id="2b765-352">Your label is now ready to use.</span></span>

### <a name="create-a-wave-label-template"></a><span data-ttu-id="2b765-353">Skapa en mall för påfyllnadsetikett</span><span class="sxs-lookup"><span data-stu-id="2b765-353">Create a wave label template</span></span>

1. <span data-ttu-id="2b765-354">Gå till **Lagerstyrning \> Inställningar \> Dokumentflöde \> Mall för påfyllnadsetikett**.</span><span class="sxs-lookup"><span data-stu-id="2b765-354">Go to **Warehouse management \> Setup \> Document routing \> Wave label templates**.</span></span>
1. <span data-ttu-id="2b765-355">Lägg till en mall för påfyllnadsnivå och ange följande värden i rubriken:</span><span class="sxs-lookup"><span data-stu-id="2b765-355">Add a wave level template, and set the following values in the header:</span></span>

    - <span data-ttu-id="2b765-356">**Namn på etikettmallen:** *behållaretiketter*</span><span class="sxs-lookup"><span data-stu-id="2b765-356">**Label template name:** *Container labels*</span></span>
    - <span data-ttu-id="2b765-357">**Beskrivning:** *behållaretiketter*</span><span class="sxs-lookup"><span data-stu-id="2b765-357">**Description:** *Container labels*</span></span>
    - <span data-ttu-id="2b765-358">**Kod för påfyllnadssteg:** *PrintLabel*</span><span class="sxs-lookup"><span data-stu-id="2b765-358">**Wave step code:** *PrintLabel*</span></span>
    - <span data-ttu-id="2b765-359">**Lagerställe:** *63*</span><span class="sxs-lookup"><span data-stu-id="2b765-359">**Warehouse:** *63*</span></span>

1. <span data-ttu-id="2b765-360">På snabbfliken **information om påfyllnadsetikettens mall** och lägg till en rad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="2b765-360">On the **Wave label template details** FastTab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="2b765-361">**Etikettlayout-ID:** *behållare*</span><span class="sxs-lookup"><span data-stu-id="2b765-361">**Label layout ID:** *Container*</span></span>
    - <span data-ttu-id="2b765-362">**Skrivarnamn:** Välj en lämplig ZPL-skrivare.</span><span class="sxs-lookup"><span data-stu-id="2b765-362">**Printer name:** Select an appropriate ZPL printer.</span></span>
    - <span data-ttu-id="2b765-363">**Kör fråga:** *Ja* (den här inställningen är valfri, men rekommenderas för optimal prestanda.)</span><span class="sxs-lookup"><span data-stu-id="2b765-363">**Run query:** *Yes* (This setting is optional, but it's recommended for optimal performance.)</span></span>

1. <span data-ttu-id="2b765-364">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="2b765-364">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="2b765-365">Valfritt: om du ställer in en kundspecifik etikettdesign måste du skapa en fråga för att hitta kundens konto.</span><span class="sxs-lookup"><span data-stu-id="2b765-365">Optional: If you're setting up a customer-specific label design, you must create a query to find the customer's account.</span></span> <span data-ttu-id="2b765-366">På snabbfliken **information om påfyllnadsetikettens mall** välj **Redigera fråga**.</span><span class="sxs-lookup"><span data-stu-id="2b765-366">On the **Wave label template details** FastTab, select **Edit query**.</span></span> <span data-ttu-id="2b765-367">I frågeredigerarens dialogruta, på fliken **Intervall** lägg till en rad med följande värden:</span><span class="sxs-lookup"><span data-stu-id="2b765-367">Then, in the query editor dialog box, on the **Range** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="2b765-368">**Register:** *försändelser*</span><span class="sxs-lookup"><span data-stu-id="2b765-368">**Table:** *Shipments*</span></span>
    - <span data-ttu-id="2b765-369">**Härlett register:** *försändelser*</span><span class="sxs-lookup"><span data-stu-id="2b765-369">**Derived table:** *Shipments*</span></span>
    - <span data-ttu-id="2b765-370">**Fält:** *Kontonummer*</span><span class="sxs-lookup"><span data-stu-id="2b765-370">**Field:** *Account number*</span></span>
    - <span data-ttu-id="2b765-371">**Kriterier:** Ange relevant kundkontonummer.</span><span class="sxs-lookup"><span data-stu-id="2b765-371">**Criteria:** Enter the relevant customer account number.</span></span>

    <span data-ttu-id="2b765-372">När du är klar klickar du på **OK** för att stänga dialogrutan för frågeredigeraren.</span><span class="sxs-lookup"><span data-stu-id="2b765-372">When you've finished, select **OK** to close the query editor dialog box.</span></span>

### <a name="configure-number-sequence-extensions"></a><span data-ttu-id="2b765-373">Konfigurera nummerserietillägg</span><span class="sxs-lookup"><span data-stu-id="2b765-373">Configure number sequence extensions</span></span>

<span data-ttu-id="2b765-374">Nummerserietillägg styr GS1 efterlevnaden av specifika nummerserier.</span><span class="sxs-lookup"><span data-stu-id="2b765-374">Number sequence extensions control the GS1 compliance of specific number sequences.</span></span> <span data-ttu-id="2b765-375">Den här konfigurationen är valfri för det aktuella scenariot.</span><span class="sxs-lookup"><span data-stu-id="2b765-375">This configuration is optional for the current scenario.</span></span> <span data-ttu-id="2b765-376">Mer information och instruktioner för konfigurering finns i [Konfigurera tillägg för nummerserier](../warehousing/configure-number-sequence-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="2b765-376">For more information and configuration instructions, see [Configure number sequence extensions](../warehousing/configure-number-sequence-extensions.md).</span></span>

### <a name="create-a-sales-order-and-release-it-to-the-warehouse"></a><span data-ttu-id="2b765-377">Skapa en försäljningsorder och släpp den på lagerstället</span><span class="sxs-lookup"><span data-stu-id="2b765-377">Create a sales order and release it to the warehouse</span></span>

1. <span data-ttu-id="2b765-378">Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="2b765-378">Go to **Sales and marketing \> Sales order \> All sales orders**.</span></span>
1. <span data-ttu-id="2b765-379">Skapa en försäljningsorder med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="2b765-379">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="2b765-380">**Kundkonto:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="2b765-380">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="2b765-381">**Lagerställe:** *63*</span><span class="sxs-lookup"><span data-stu-id="2b765-381">**Warehouse:** *63*</span></span>

1. <span data-ttu-id="2b765-382">Lägg till fem försäljningsorderrader:</span><span class="sxs-lookup"><span data-stu-id="2b765-382">Add five sales order lines:</span></span>

    - <span data-ttu-id="2b765-383">Försäljningsorderrad 1:</span><span class="sxs-lookup"><span data-stu-id="2b765-383">Sales order line 1:</span></span>

        - <span data-ttu-id="2b765-384">**Artikelnummer:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="2b765-384">**Item number:** *A0001*</span></span>
        - <span data-ttu-id="2b765-385">**Kvantitet:** *10*</span><span class="sxs-lookup"><span data-stu-id="2b765-385">**Quantity:** *10*</span></span>

    - <span data-ttu-id="2b765-386">Försäljningsorderrad 2:</span><span class="sxs-lookup"><span data-stu-id="2b765-386">Sales order line 2:</span></span>

        - <span data-ttu-id="2b765-387">**Artikelnummer:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="2b765-387">**Item number:** *A0002*</span></span>
        - <span data-ttu-id="2b765-388">**Kvantitet:** *20*</span><span class="sxs-lookup"><span data-stu-id="2b765-388">**Quantity:** *20*</span></span>

    - <span data-ttu-id="2b765-389">Försäljningsorderrad 3:</span><span class="sxs-lookup"><span data-stu-id="2b765-389">Sales order line 3:</span></span>

        - <span data-ttu-id="2b765-390">**Artikelnummer:** *L0006*</span><span class="sxs-lookup"><span data-stu-id="2b765-390">**Item number:** *L0006*</span></span>
        - <span data-ttu-id="2b765-391">**Kvantitet:** *20*</span><span class="sxs-lookup"><span data-stu-id="2b765-391">**Quantity:** *20*</span></span>

    - <span data-ttu-id="2b765-392">Försäljningsorderrad 4:</span><span class="sxs-lookup"><span data-stu-id="2b765-392">Sales order line 4:</span></span>

        - <span data-ttu-id="2b765-393">**Artikelnummer:** *L0100*</span><span class="sxs-lookup"><span data-stu-id="2b765-393">**Item number:** *L0100*</span></span>
        - <span data-ttu-id="2b765-394">**Kvantitet:** *40*</span><span class="sxs-lookup"><span data-stu-id="2b765-394">**Quantity:** *40*</span></span>

    - <span data-ttu-id="2b765-395">Försäljningsorderrad 5:</span><span class="sxs-lookup"><span data-stu-id="2b765-395">Sales order line 5:</span></span>

        - <span data-ttu-id="2b765-396">**Artikelnummer:** *L0101*</span><span class="sxs-lookup"><span data-stu-id="2b765-396">**Item number:** *L0101*</span></span>
        - <span data-ttu-id="2b765-397">**Kvantitet:** *50*</span><span class="sxs-lookup"><span data-stu-id="2b765-397">**Quantity:** *50*</span></span>

    > [!NOTE]
    > <span data-ttu-id="2b765-398">Artiklarna och kvantiteterna som anges här är endast exempel.</span><span class="sxs-lookup"><span data-stu-id="2b765-398">The items and quantities that are provided here are only examples.</span></span> <span data-ttu-id="2b765-399">De måste ha lager i det angivna lagerstället.</span><span class="sxs-lookup"><span data-stu-id="2b765-399">They must have stock in the specified warehouse.</span></span>

1. <span data-ttu-id="2b765-400">Välj försäljningsorderrad 1.</span><span class="sxs-lookup"><span data-stu-id="2b765-400">Select sales order line 1.</span></span> <span data-ttu-id="2b765-401">I avsnittet **Försäljningsorderrad** i menyn **Lager** välj **Reservationer**.</span><span class="sxs-lookup"><span data-stu-id="2b765-401">Then, in the **Sales order line** section, on the **Inventory** menu, select **Reservations**.</span></span>
1. <span data-ttu-id="2b765-402">På sidan **Reservation** i åtgärdsfönstret, välj **Reservera parti** och stäng sedan sidan.</span><span class="sxs-lookup"><span data-stu-id="2b765-402">On the **Reservation** page, on the Action Pane, select **Reserve lot**, and then close the page.</span></span>
1. <span data-ttu-id="2b765-403">Upprepa steg 4 och 5 för varje ytterligare försäljningsorderrad.</span><span class="sxs-lookup"><span data-stu-id="2b765-403">Repeat steps 4 and 5 for each additional sales order line.</span></span>
1. <span data-ttu-id="2b765-404">I åtgärdsfönstret på fliken **Lagerställe** välj **Frisläpp till regel för lagerställe**.</span><span class="sxs-lookup"><span data-stu-id="2b765-404">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="2b765-405">Då inträffar följande händelser:</span><span class="sxs-lookup"><span data-stu-id="2b765-405">The following events occur:</span></span>

    - <span data-ttu-id="2b765-406">I systemet bearbetas den skapade utleveransen med hjälp av mallen som inkluderar utskriftssteget för etikett.</span><span class="sxs-lookup"><span data-stu-id="2b765-406">The system processes the created shipment using the template that includes the label printing step.</span></span> <span data-ttu-id="2b765-407">Etikettlayouten används för att definiera etikettens format, och slutresultatet blir en etikett som har fem rader och som skrivs ut på den skrivare som väljs i etikettmallen.</span><span class="sxs-lookup"><span data-stu-id="2b765-407">The label layout will be used to define the format of the label, and the end result will be a label that has five lines and that is printed on the printer that is selected in the label template.</span></span>
    - <span data-ttu-id="2b765-408">Ett nytt fraktsedels-ID genereras för leveranserna.</span><span class="sxs-lookup"><span data-stu-id="2b765-408">A new bill of lading ID is generated for the shipments.</span></span> <span data-ttu-id="2b765-409">Om du har konfigurerat nummerserietilläggen följer påfyllnadsetikett-ID nummerformatet **SSCC-18**.</span><span class="sxs-lookup"><span data-stu-id="2b765-409">If you configured the number sequence extensions, the wave label IDs will follow the **SSCC-18** number format.</span></span> 

<span data-ttu-id="2b765-410">Du kan skriva ut dessa påfyllnadsetiketter igen genom att gå till **Lagerstyrning \> Frågor och rapporter \> Påfyllnadsetiketthistorik**.</span><span class="sxs-lookup"><span data-stu-id="2b765-410">You can reprint these wave labels by going to **Warehouse management \> Inquiries and reports \> Wave label history**.</span></span>

## <a name="scenario-3-wave-label-printing-for-multi-tiered-labels"></a><span data-ttu-id="2b765-411">Scenario 3: utskrift av påfyllnadsetikett för etiketter med flera nivåer</span><span class="sxs-lookup"><span data-stu-id="2b765-411">Scenario 3: Wave label printing for multi-tiered labels</span></span>

<span data-ttu-id="2b765-412">Det här scenariot visar hur du använder funktionen utskrift av påfyllnadsetikett när lagerprocesserna kräver flera nivåer för leveransetiketter.</span><span class="sxs-lookup"><span data-stu-id="2b765-412">This scenario shows how to use the wave label printing functionality when the warehousing processes require several tiers of shipping labels.</span></span> <span data-ttu-id="2b765-413">Till exempel kan separata etiketter behöva skrivas ut för kartonger och lastpallar, och en avbrottsetikett måste skrivas ut för en hel leverans.</span><span class="sxs-lookup"><span data-stu-id="2b765-413">For example, separate labels might have to be printed for cartons and pallets, and a break label might have to be printed for a whole shipment.</span></span> <span data-ttu-id="2b765-414">Avbrottsetiketter är en separat typ av etikett som kan användas som avgränsare mellan rullar och behållare, t.ex. etiketter för leverans-ID och en streckkod, så att etiketterna enkelt kan sorteras när de har skrivits ut.</span><span class="sxs-lookup"><span data-stu-id="2b765-414">Break labels are a separate type of label that can be used as a divider between rolls and containers, such as labels for the shipment ID and a barcode, so that the labels can easily be sorted after they are printed.</span></span>

<span data-ttu-id="2b765-415">Den huvudsakliga skillnaden mellan konfigurationen av scenariot och konfigurationen av scenario 1, förutom att bryta etiketter är aktiverade, är att flera typer av påfyllnadetiketter måste associeras med påfyllnadsetikettmallen och enhetssekvensgruppraderna.</span><span class="sxs-lookup"><span data-stu-id="2b765-415">The main difference between the configuration of this scenario and the configuration of scenario 1, besides the fact that break labels are enabled, is that multiple wave label types must be associated with wave label templates and unit sequence group lines.</span></span> <span data-ttu-id="2b765-416">För att kunna utföra den här konfigurationen ställer du in följande element för det här scenariot:</span><span class="sxs-lookup"><span data-stu-id="2b765-416">To accomplish this configuration, you set up the following elements for this scenario:</span></span>

- <span data-ttu-id="2b765-417">**Metoder för påfyllnadsbearbetning:** du markerar en påfyllnadsetiketts metod som "upprepningsbar", lägger till den två (eller fler) tiderna i påfyllnadsmallen och ställer in olika koder för påfyllnadssteg.</span><span class="sxs-lookup"><span data-stu-id="2b765-417">**Wave processing methods:** You will mark the wave label method as "repeatable," add it two (or more) times to the wave template, and set different wave step codes.</span></span>
- <span data-ttu-id="2b765-418">**Mallar för påfyllnadsetikett:** du kommer att konfigurera mallarna för påfyllnadsetikett och länka dem till påfyllnadsmallen.</span><span class="sxs-lookup"><span data-stu-id="2b765-418">**Wave label templates:** You will configure the wave label templates and link them to the wave template.</span></span> <span data-ttu-id="2b765-419">Varje påfyllnadsetikettmall har en egen typ av påfyllnadsetikett.</span><span class="sxs-lookup"><span data-stu-id="2b765-419">Each wave label template has its own wave label type.</span></span>
- <span data-ttu-id="2b765-420">**Layout för påfyllnadsetiketter:** du kan skapa flera layouter för påfyllnadsetiketter.</span><span class="sxs-lookup"><span data-stu-id="2b765-420">**Wave label layouts:** You will create multiple wave label layouts.</span></span> <span data-ttu-id="2b765-421">Det finns en separat etikettlayout för varje "nivå" med etiketter och det får också en layout för avbrottsetiketten.</span><span class="sxs-lookup"><span data-stu-id="2b765-421">There will be a separate label layout for each "tier" of labels, and there will also be a break label layout.</span></span>

<span data-ttu-id="2b765-422">Det här scenariot visar komplett flöde.</span><span class="sxs-lookup"><span data-stu-id="2b765-422">This scenario shows the end-to-end flow.</span></span>

### <a name="make-demo-data-available"></a><span data-ttu-id="2b765-423">Gör demodata tillgängliga</span><span class="sxs-lookup"><span data-stu-id="2b765-423">Make demo data available</span></span>

<span data-ttu-id="2b765-424">För att följa detta scenario måste du ha demonstrationsdata installerad och du måste välja juridiska personen **USMF**.</span><span class="sxs-lookup"><span data-stu-id="2b765-424">To follow this scenario, you must have demo data installed, and you must select the **USMF** legal entity.</span></span>

### <a name="set-up-a-wave-process-method"></a><span data-ttu-id="2b765-425">Ställa in en påfyllnadsprocessmetod</span><span class="sxs-lookup"><span data-stu-id="2b765-425">Set up a wave process method</span></span>

1. <span data-ttu-id="2b765-426">Gå till **Lagerstyrning \> Inställningar \> Påfyllnader \> Metoder för påfyllnadsprocess**.</span><span class="sxs-lookup"><span data-stu-id="2b765-426">Go to **Warehouse management \> Setup \> Waves \> Wave process methods**.</span></span>
1. <span data-ttu-id="2b765-427">Kontrollera att **waveLabelPrinting** finns i listan.</span><span class="sxs-lookup"><span data-stu-id="2b765-427">Confirm that **waveLabelPrinting** is in the list.</span></span> <span data-ttu-id="2b765-428">Om den inte finns med väljer du **återskapa metoder** i åtgärdsfönstret för att lägga till den.</span><span class="sxs-lookup"><span data-stu-id="2b765-428">If it isn't, select **Regenerate methods** on the Action Pane to add it.</span></span>
1. <span data-ttu-id="2b765-429">För metoden **waveLabelPrinting** markera kryssrutan **gör metoden upprepningsbar**.</span><span class="sxs-lookup"><span data-stu-id="2b765-429">For the **waveLabelPrinting** method, select the **Make method repeatable** check box.</span></span>

### <a name="set-up-a-wave-template"></a><span data-ttu-id="2b765-430">Ställa in en påfyllnadsmall</span><span class="sxs-lookup"><span data-stu-id="2b765-430">Set up a wave template</span></span>

1. <span data-ttu-id="2b765-431">Gå till **Lagerstyrning \> Inställningar \> Påfyllnader \> Påfyllnadsmallar**.</span><span class="sxs-lookup"><span data-stu-id="2b765-431">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
2. <span data-ttu-id="2b765-432">Välj en mall som **62 standard för leverans**.</span><span class="sxs-lookup"><span data-stu-id="2b765-432">Select a template, such as **62 Shipping Default**.</span></span>
3. <span data-ttu-id="2b765-433">På snabbfliken **metoder** flyttar du metoden **utskrift av påfyllnadsetiketter** till kolumnen **valda metoder**.</span><span class="sxs-lookup"><span data-stu-id="2b765-433">On the **Methods** FastTab, move the **Wave label printing** method to the **Selected methods** column.</span></span>
4. <span data-ttu-id="2b765-434">I kolumnen **valda metoder** tilldelar du ett värde för **Kod för påfyllnadssteg** som *kartong* till metoden **utskrift av påfyllnadsetikett**.</span><span class="sxs-lookup"><span data-stu-id="2b765-434">In the **Selected methods** column, assign a **Wave step code** value, such as *Carton*, to the **Wave label printing** method.</span></span> <span data-ttu-id="2b765-435">För mer information om koder för påfyllnadssteg, se [Koder för påfyllnadssteg](wave-step-codes.md).</span><span class="sxs-lookup"><span data-stu-id="2b765-435">For more information about wave step codes, see [Wave step codes](wave-step-codes.md).</span></span>
5. <span data-ttu-id="2b765-436">Flytta metoden **utskrift av påfyllnadsetikett** till kolumnen **valda metoder** en andra gång.</span><span class="sxs-lookup"><span data-stu-id="2b765-436">Move the **Wave label printing** method to the **Selected methods** column a second time.</span></span>
6. <span data-ttu-id="2b765-437">I kolumnen **valda metoder** tilldelar du ett annat värde för **Kod för påfyllnadssteg** som *lastpall* till den andra metoden **utskrift av påfyllnadsetikett**.</span><span class="sxs-lookup"><span data-stu-id="2b765-437">In the **Selected methods** column, assign a different **Wave step code** value, such as *Pallet*, to the second **Wave label printing** method.</span></span> <span data-ttu-id="2b765-438">För mer information om koder för påfyllnadssteg, se [Koder för påfyllnadssteg](wave-step-codes.md).</span><span class="sxs-lookup"><span data-stu-id="2b765-438">For more information about wave step codes, see [Wave step codes](wave-step-codes.md).</span></span>

### <a name="create-three-wave-label-layouts"></a><span data-ttu-id="2b765-439">Skapa tre layouter för påfyllnadsetiketten</span><span class="sxs-lookup"><span data-stu-id="2b765-439">Create three wave label layouts</span></span>

1. <span data-ttu-id="2b765-440">Gå till **Lagerstyrning \> Inställningar \> Dokumentflöde \> Layout för påfyllnadsetikett**.</span><span class="sxs-lookup"><span data-stu-id="2b765-440">Go to **Warehouse management \> Setup \> Document routing \> Wave label layouts**.</span></span>
1. <span data-ttu-id="2b765-441">Skapa en post med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="2b765-441">Create a record that has the following settings:</span></span>

    - <span data-ttu-id="2b765-442">**Etikettlayout-ID:** *kartong*</span><span class="sxs-lookup"><span data-stu-id="2b765-442">**Label layout ID:** *Carton*</span></span>
    - <span data-ttu-id="2b765-443">**Beskrivning:** *kartong (SSCC)*</span><span class="sxs-lookup"><span data-stu-id="2b765-443">**Description:** *Carton (SSCC)*</span></span>

1. <span data-ttu-id="2b765-444">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="2b765-444">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="2b765-445">I åtgärdsfönstret, välj **Inställningar för påfyllnadsetikettrad**.</span><span class="sxs-lookup"><span data-stu-id="2b765-445">On the Action Pane, select **Wave label row settings**.</span></span>

    <span data-ttu-id="2b765-446">Sidan **Inställningar för påfyllnadsetikettrad** visas.</span><span class="sxs-lookup"><span data-stu-id="2b765-446">The **Wave label row settings** page appears.</span></span> <span data-ttu-id="2b765-447">Här kan du konfigurera den dynamiska delen av etiketten.</span><span class="sxs-lookup"><span data-stu-id="2b765-447">Here, you can configure the dynamic part of the label.</span></span>

1. <span data-ttu-id="2b765-448">Lägg till en rad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="2b765-448">Add a row that has the following settings:</span></span>

    - <span data-ttu-id="2b765-449">**Rad-ID:** *WaveLabel*</span><span class="sxs-lookup"><span data-stu-id="2b765-449">**Row Id:** *WaveLabel*</span></span>
    - <span data-ttu-id="2b765-450">**Radtabellnamn:** *WHSWaveLabel*</span><span class="sxs-lookup"><span data-stu-id="2b765-450">**Row table name:** *WHSWaveLabel*</span></span>
    - <span data-ttu-id="2b765-451">**Radens startposition:** *0*</span><span class="sxs-lookup"><span data-stu-id="2b765-451">**Row start position:** *0*</span></span>

        <span data-ttu-id="2b765-452">I det här fältet definieras den lodräta position där raden ska börja etiketten.</span><span class="sxs-lookup"><span data-stu-id="2b765-452">This field defines the vertical position where the row will begin on the label.</span></span>

    - <span data-ttu-id="2b765-453">**Radhöjd:** *0*</span><span class="sxs-lookup"><span data-stu-id="2b765-453">**Row height:** *0*</span></span>

        <span data-ttu-id="2b765-454">I det här fältet definieras höjden på varje rad (i punkter) enligt ZPL-standard.</span><span class="sxs-lookup"><span data-stu-id="2b765-454">This field defines the height of each row (in points), according to the ZPL standard.</span></span> <span data-ttu-id="2b765-455">Radhöjden är positiv för vågräta etiketter och är negativ för lodräta etiketter.</span><span class="sxs-lookup"><span data-stu-id="2b765-455">The row height is positive for horizontal labels and negative for vertical labels.</span></span> <span data-ttu-id="2b765-456">Eftersom det bara finns en rad i det här exemplet kan du ställa in värdet på *0* (noll).</span><span class="sxs-lookup"><span data-stu-id="2b765-456">Because there is just one row in this example, you can set the value to *0* (zero).</span></span>

    - <span data-ttu-id="2b765-457">**Rader per sida:** *1*</span><span class="sxs-lookup"><span data-stu-id="2b765-457">**Rows per page:** *1*</span></span>

        <span data-ttu-id="2b765-458">I det här fältet definieras antalet rader som kan skrivas ut på varje etikett.</span><span class="sxs-lookup"><span data-stu-id="2b765-458">This field defines the number of rows that can be printed on each label.</span></span>

        > [!NOTE]
        > <span data-ttu-id="2b765-459">Den här inställningen gör att en separat ZPL-etikett skrivs ut för varje post i tabellen med påfyllnadsetiketter.</span><span class="sxs-lookup"><span data-stu-id="2b765-459">This setup will cause a separate ZPL label to be printed for each record in the wave labels table.</span></span>

1. <span data-ttu-id="2b765-460">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="2b765-460">Close the page.</span></span>
1. <span data-ttu-id="2b765-461">I åtgärdsfönstret väljer du **Redigera fråga**.</span><span class="sxs-lookup"><span data-stu-id="2b765-461">On the Action Pane, select **Edit query**.</span></span>
1. <span data-ttu-id="2b765-462">I frågeredigerarens dialogruta, på fliken **Intervall** lägg till en rad med följande värden:</span><span class="sxs-lookup"><span data-stu-id="2b765-462">In the query editor dialog box, on the **Range** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="2b765-463">**Tabell:** *Arbetsrader*</span><span class="sxs-lookup"><span data-stu-id="2b765-463">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="2b765-464">**Härlett register:** *Arbetsrader*</span><span class="sxs-lookup"><span data-stu-id="2b765-464">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="2b765-465">**Fält:** *arbetstyp*</span><span class="sxs-lookup"><span data-stu-id="2b765-465">**Field:** *Work type*</span></span>
    - <span data-ttu-id="2b765-466">**Kriterier:** *Plocka*</span><span class="sxs-lookup"><span data-stu-id="2b765-466">**Criteria:** *Pick*</span></span>

    <span data-ttu-id="2b765-467">Den här frågan ser till att endast arbetsrader av typen plockning skrivs ut på etiketten, inte artikelrader av typen radtyp.</span><span class="sxs-lookup"><span data-stu-id="2b765-467">This query ensures that only pick-type work lines will be printed on the label, not put-type work lines.</span></span>

1. <span data-ttu-id="2b765-468">Om du vill kunna skriva ut fraktsedels-ID väljer du på fliken **kopplingar**, sedan **arbetsrader** och kopplar tabellen **leveranser** till den.</span><span class="sxs-lookup"><span data-stu-id="2b765-468">If you want to be able to print the bill of lading ID, on the **Joins** tab, select the **Work lines** table, and join the **Shipments** table to it.</span></span> 
1. <span data-ttu-id="2b765-469">Stäng dialogrutan frågeredigeraren.</span><span class="sxs-lookup"><span data-stu-id="2b765-469">Close the query editor dialog box.</span></span>
1. <span data-ttu-id="2b765-470">På snabbfliken **Layout för skrivartext** finns tre avsnitt där du kan skriva skrivarkod: **rubrikavsnitt**, **brödtext** och **sidfotsavsnitt**.</span><span class="sxs-lookup"><span data-stu-id="2b765-470">The **Printer text Layout** FastTab has three sections where you can write printer code: **Header section**, **Body section**, and **Footer section**.</span></span> <span data-ttu-id="2b765-471">I avsnittet **rubrikavsnitt** i fältet **etikettrubrik** anger du koden för önskad rubrik.</span><span class="sxs-lookup"><span data-stu-id="2b765-471">In the **Header section** section, in the **Label header** field, enter code for the required header.</span></span> <span data-ttu-id="2b765-472">Om du till exempel använder Zebra-skrivare kan du använda följande kod.</span><span class="sxs-lookup"><span data-stu-id="2b765-472">For example, if you're using Zebra printers, you can use the following code.</span></span>


    ```plaintext
    CT~~CD,~CC^~CT~
    ^XA~TA000~JSN^LT0^MNW^MTT^PON^PMN^LH0,0^JMA^PR8,8~SD15^JUS^LRN^CI0^XZ
    ^XA
    ^MMT
    ^PW812
    ^LL1218
    ^LS0
    ^FT85,505^A0N,28,28^FH\^FD$WHSShipmentTable.CustomerReq$^FS
    ^FO1,173^GB809,0,1^FS
    ^FO0,391^GB809,0,1^FS
    ^FO3,599^GB809,0,2^FS
    ^FO420,176^GB0,216,1^FS
    ^FO313,3^GB0,169,1^FS
    ^FO0,807^GB809,0,1^FS
    ^FT529,370^A0N,28,26^FH\^FD$WHSShipmentTable.BillOfLadingId$^FS
    ^BY2,3,132^FT25,344^BCN,,N,N
    ^FD>:(420)>38102>63^FS
    ^FT526,315^A0N,28,28^FH\^FD ^FS
    ^FT437,248^A0N,28,28^FH\^FDCARR: $WHSShipmentTable.SCAC$^FS
    ^FT425,201^A0N,23,24^FH\^FDCARRIER:^FS
    ^FT17,68^A0N,20,19^FH\^FDIntershipping, Inc.^FS
    ^FT15,99^A0N,20,19^FH\^FD1000 Shipping Lane^FS
    ^FT16,158^A0N,20,19^FH\^FD ^FS
    ^FT438,368^A0N,28,28^FH\^FDB/L#^FS
    ^FT15,128^A0N,20,19^FH\^FDShelbyville TN 38102^FS
    ^FT19,203^A0N,23,24^FH\^FD(420) SHIP TO POSTAL CODE^FS
    ^FT331,39^A0N,28,28^FH\^FDShip To:^FS
    ^FT14,39^A0N,28,28^FH\^FDShip From:^FS
    ^FT331,67^A0N,23,24^FH\^FDWAL-MART DC 1111A-ABC DIS^FS
    ^FT330,98^A0N,23,24^FH\^FDDEPT 10^FS
    ^FT329,166^A0N,23,24^FH\^FDSpringfield TN 39021^FS
    ^FT330,134^A0N,23,24^FH\^FD100 Main Street^FS
    ^FT19,504^A0N,28,28^FH\^FDPO#:^FS
    ^FT437,316^A0N,28,28^FH\^FDPRO#^FS
    ^FT105,371^A0N,28,28^FB130,1,0,C^FH\^FD(420)39021^FS
    ```

1. <span data-ttu-id="2b765-473">I avsnittet **brödtext** i fältet **etikettext** anger du ZPL-koden för önskad text.</span><span class="sxs-lookup"><span data-stu-id="2b765-473">In the **Body section** section, in the **Label body** field, enter ZPL code for the required body.</span></span> <span data-ttu-id="2b765-474">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="2b765-474">Here is an example.</span></span>

    ```plaintext
    <Row name="WaveLabel">
    ^FT127,439^A0N,28,28^FH\^FD$WHSWaveLabel.SeqNum$^FS
    ^FT256,439^A0N,28,28^FH\^FD$WHSWaveLabel.NumberOfLabels$^FS
    ^FT17,439^A0N,28,28^FH\^FDCARTON^FS
    ^FT522,422^A0N,23,24^FH\^FDVPN:^FS
    ^FT74,1156^A0N,28,28^FH\^FDSSCC-18^FS
    ^FT21,579^A0N,28,28^FH\^FDItem name:^FS
    ^FT107,580^A0N,28,28^FH\^FD$WHSWaveLabel.LabelItemName$^FS
    ^FT576,423^A0N,23,21^FH\^FD$WHSWaveLabel.LabelItemId$^FS
    ^FT252,1155^A0N,32,31^FH\^FD(00)$WHSWaveLabel.WaveLabelId$^FS
    ^BY4,3,283^FT66,1115^BCN,,N,N
    ^FD>;>800$WHSWaveLabel.WaveLabelId$^FS
    ^FT194,439^A0N,28,28^FH\^FDof^FS
    </Row>
    ```

1. <span data-ttu-id="2b765-475">I avsnittet **brödtext** i fältet **etikettsidfot** anger du ZPL-koden för önskad sidfot.</span><span class="sxs-lookup"><span data-stu-id="2b765-475">In the **Body section** section, in the **Label footer** field, enter ZPL code for the required footer.</span></span> <span data-ttu-id="2b765-476">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="2b765-476">Here is an example.</span></span>

    ```plaintext
    ^PQ1^XZ
    ```

    > [!NOTE]
    > <span data-ttu-id="2b765-477">Installationen kommer att skriva ut en kopia av varje etikett.</span><span class="sxs-lookup"><span data-stu-id="2b765-477">This setup will print one copy of each label.</span></span> <span data-ttu-id="2b765-478">Om du vill ha fler kopior (t.ex. en kopia för varje sida av lastpallen) anger du värdet **n** för avsnittet **\^PQn** i sidfoten till det antal kopior som krävs.</span><span class="sxs-lookup"><span data-stu-id="2b765-478">If you require more copies (for example, one copy for each side of the pallet), set the **n** value for the **\^PQn** section in the footer to the required number of copies.</span></span> <span data-ttu-id="2b765-479">Om du till exempel vill skriva ut fyra kopior av varje etikett anger du **\^PQ4**.</span><span class="sxs-lookup"><span data-stu-id="2b765-479">For example, to print four copies of each label, specify **\^PQ4**.</span></span>

1. <span data-ttu-id="2b765-480">Nu kan du använda din första etikett.</span><span class="sxs-lookup"><span data-stu-id="2b765-480">The first label is now ready to use.</span></span>
1. <span data-ttu-id="2b765-481">Skapa en andra layoutpost med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="2b765-481">Create a second layout record that has the following settings:</span></span>

    - <span data-ttu-id="2b765-482">**Etikettlayout-ID:** *lastpall*</span><span class="sxs-lookup"><span data-stu-id="2b765-482">**Label layout ID:** *Pallet*</span></span>
    - <span data-ttu-id="2b765-483">**Beskrivning:** *lastpall*</span><span class="sxs-lookup"><span data-stu-id="2b765-483">**Description:** *Pallet*</span></span>

1. <span data-ttu-id="2b765-484">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="2b765-484">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="2b765-485">I åtgärdsfönstret, välj **Inställningar för påfyllnadsetikettrad**.</span><span class="sxs-lookup"><span data-stu-id="2b765-485">On the Action Pane, select **Wave label row settings**.</span></span>

    <span data-ttu-id="2b765-486">Sidan **Inställningar för påfyllnadsetikettrad** visas.</span><span class="sxs-lookup"><span data-stu-id="2b765-486">The **Wave label row settings** page appears.</span></span> <span data-ttu-id="2b765-487">Här kan du konfigurera den dynamiska delen av etiketten.</span><span class="sxs-lookup"><span data-stu-id="2b765-487">Here, you can configure the dynamic part of the label.</span></span>

1. <span data-ttu-id="2b765-488">Lägg till en rad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="2b765-488">Add a row that has the following settings:</span></span>

    - <span data-ttu-id="2b765-489">**Rad-ID:** *WaveLabel*</span><span class="sxs-lookup"><span data-stu-id="2b765-489">**Row Id:** *WaveLabel*</span></span>
    - <span data-ttu-id="2b765-490">**Radtabellnamn:** *WHSWaveLabel*</span><span class="sxs-lookup"><span data-stu-id="2b765-490">**Row table name:** *WHSWaveLabel*</span></span>
    - <span data-ttu-id="2b765-491">**Radens startposition:** *0*</span><span class="sxs-lookup"><span data-stu-id="2b765-491">**Row start position:** *0*</span></span>

        <span data-ttu-id="2b765-492">I det här fältet definieras den lodräta position där raden ska börja etiketten.</span><span class="sxs-lookup"><span data-stu-id="2b765-492">This field defines the vertical position where the row will begin on the label.</span></span>

    - <span data-ttu-id="2b765-493">**Radhöjd:** *0*</span><span class="sxs-lookup"><span data-stu-id="2b765-493">**Row height:** *0*</span></span>

        <span data-ttu-id="2b765-494">I det här fältet definieras höjden på varje rad (i punkter) enligt ZPL-standard.</span><span class="sxs-lookup"><span data-stu-id="2b765-494">This field defines the height of each row (in points), according to the ZPL standard.</span></span> <span data-ttu-id="2b765-495">Radhöjden är positiv för vågräta etiketter och är negativ för lodräta etiketter.</span><span class="sxs-lookup"><span data-stu-id="2b765-495">The row height is positive for horizontal labels and negative for vertical labels.</span></span> <span data-ttu-id="2b765-496">Eftersom det bara finns en rad i det här exemplet kan du ställa in värdet på *0* (noll).</span><span class="sxs-lookup"><span data-stu-id="2b765-496">Because there is just one row in this example, you can set the value to *0* (zero).</span></span>

    - <span data-ttu-id="2b765-497">**Rader per sida:** *1*</span><span class="sxs-lookup"><span data-stu-id="2b765-497">**Rows per page:** *1*</span></span>

        <span data-ttu-id="2b765-498">I det här fältet definieras antalet rader som kan skrivas ut på varje etikett.</span><span class="sxs-lookup"><span data-stu-id="2b765-498">This field defines the number of rows that can be printed on each label.</span></span>

        > [!NOTE]
        > <span data-ttu-id="2b765-499">Den här inställningen gör att en separat ZPL-etikett skrivs ut för varje post i tabellen med påfyllnadsetiketter.</span><span class="sxs-lookup"><span data-stu-id="2b765-499">This setup causes a separate ZPL label to be printed for each record in the wave labels table.</span></span>

1. <span data-ttu-id="2b765-500">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="2b765-500">Close the page.</span></span>
1. <span data-ttu-id="2b765-501">I åtgärdsfönstret väljer du **Redigera fråga**.</span><span class="sxs-lookup"><span data-stu-id="2b765-501">On the Action Pane, select **Edit query**.</span></span>
1. <span data-ttu-id="2b765-502">I frågeredigerarens dialogruta, på fliken **Intervall** lägg till en rad med följande värden:</span><span class="sxs-lookup"><span data-stu-id="2b765-502">In the query editor dialog box, on the **Range** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="2b765-503">**Tabell:** *Arbetsrader*</span><span class="sxs-lookup"><span data-stu-id="2b765-503">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="2b765-504">**Härlett register:** *Arbetsrader*</span><span class="sxs-lookup"><span data-stu-id="2b765-504">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="2b765-505">**Fält:** *arbetstyp*</span><span class="sxs-lookup"><span data-stu-id="2b765-505">**Field:** *Work type*</span></span>
    - <span data-ttu-id="2b765-506">**Kriterier:** *Plocka*</span><span class="sxs-lookup"><span data-stu-id="2b765-506">**Criteria:** *Pick*</span></span>

    <span data-ttu-id="2b765-507">Den här frågan ser till att endast arbetsrader av typen plockning skrivs ut på etiketten, inte artikelrader av typen radtyp.</span><span class="sxs-lookup"><span data-stu-id="2b765-507">This query ensures that only pick-type work lines will be printed on the label, not put-type work lines.</span></span>

1. <span data-ttu-id="2b765-508">Om du vill kunna skriva ut fraktsedels-ID väljer du på fliken **kopplingar**, sedan **arbetsrader** och kopplar tabellen **leveranser** till den.</span><span class="sxs-lookup"><span data-stu-id="2b765-508">If you want to be able to print the bill of lading ID, on the **Joins** tab, select the **Work lines** table, and join the **Shipments** table to it.</span></span>
1. <span data-ttu-id="2b765-509">Stäng dialogrutan frågeredigeraren.</span><span class="sxs-lookup"><span data-stu-id="2b765-509">Close the query editor dialog box.</span></span>
1. <span data-ttu-id="2b765-510">På snabbfliken **Layout för skrivartext** finns tre avsnitt där du kan skriva skrivarkod: **rubrikavsnitt**, **brödtext** och **sidfotsavsnitt**.</span><span class="sxs-lookup"><span data-stu-id="2b765-510">The **Printer text Layout** FastTab has three sections where you can write printer code: **Header section**, **Body section**, and **Footer section**.</span></span> <span data-ttu-id="2b765-511">I avsnittet **rubrikavsnitt** i fältet **etikettrubrik** anger du koden för önskad rubrik.</span><span class="sxs-lookup"><span data-stu-id="2b765-511">In the **Header section** section, in the **Label header** field, enter code for the required header.</span></span> <span data-ttu-id="2b765-512">Om du till exempel använder Zebra-skrivare kan du använda följande kod.</span><span class="sxs-lookup"><span data-stu-id="2b765-512">For example, if you're using Zebra printers, you can use the following code.</span></span>

    ```plaintext
    CT~~CD,~CC^~CT~
    ^XA
    ^LH10,10
    ^FO0,0 ^AT ^FD$WHSWaveLabel.WaveLabelId$ ^FS
    ^FO0,75 ^AT ^FD$WHSWorkLine.ShipmentId$ ^FS
    ^FO0,150 ^AT ^FD$WHSShipmentTable.BillOfLadingId$ ^FS
    ```

1. <span data-ttu-id="2b765-513">I avsnittet **brödtext** i fältet **etikettext** anger du ZPL-koden för önskad text.</span><span class="sxs-lookup"><span data-stu-id="2b765-513">In the **Body section** section, in the **Label body** field, enter ZPL code for the required body.</span></span> <span data-ttu-id="2b765-514">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="2b765-514">Here is an example.</span></span>

    ```plaintext
    <Row name="WaveLabel">
    ^FO0,450 ^AT ^FDItem ^FS
    ^FO200,450 ^AT ^FDQuantity ^FS
    ^FO0,[[YPos]] ^AT ^FD$WHSWaveLabel.LabelItemId$ ^FS
    ^FO200,[[YPos]] ^AT ^FD$WHSWaveLabel.QtyWork$ ^FS
    </Row>
    ```

1. <span data-ttu-id="2b765-515">I avsnittet **brödtext** i fältet **etikettsidfot** anger du ZPL-koden för önskad sidfot.</span><span class="sxs-lookup"><span data-stu-id="2b765-515">In the **Body section** section, in the **Label footer** field, enter ZPL code for the required footer.</span></span> <span data-ttu-id="2b765-516">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="2b765-516">Here is an example.</span></span>

    ```plaintext
    ^PQ1^XZ
    ```

    > [!NOTE]
    > <span data-ttu-id="2b765-517">Installationen kommer att skriva ut en kopia av varje etikett.</span><span class="sxs-lookup"><span data-stu-id="2b765-517">This setup will print one copy of each label.</span></span> <span data-ttu-id="2b765-518">Om du vill ha fler kopior (t.ex. en kopia för varje sida av lastpallen) anger du värdet **n** för avsnittet **\^PQn** i sidfoten till det antal kopior som krävs.</span><span class="sxs-lookup"><span data-stu-id="2b765-518">If you require more copies (for example, one copy for each side of the pallet), set the **n** value for the **\^PQn** section in the footer to the required number of copies.</span></span> <span data-ttu-id="2b765-519">Om du till exempel vill skriva ut fyra kopior av varje etikett anger du **\^PQ4**.</span><span class="sxs-lookup"><span data-stu-id="2b765-519">For example, to print four copies of each label, specify **\^PQ4**.</span></span>

1. <span data-ttu-id="2b765-520">Nu kan du använda din andra etikett.</span><span class="sxs-lookup"><span data-stu-id="2b765-520">The second label is now ready to use.</span></span>
1. <span data-ttu-id="2b765-521">Skapa en tredje layoutpost med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="2b765-521">Create a third layout record that has the following settings:</span></span>

    - <span data-ttu-id="2b765-522">**Etikettlayout-ID:** *Avbrott*</span><span class="sxs-lookup"><span data-stu-id="2b765-522">**Label layout ID:** *Break*</span></span>
    - <span data-ttu-id="2b765-523">**Beskrivning:** *avbrottsetikett*</span><span class="sxs-lookup"><span data-stu-id="2b765-523">**Description:** *Break label*</span></span>

1. <span data-ttu-id="2b765-524">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="2b765-524">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="2b765-525">På snabbfliken **Layout för skrivartext** finns tre avsnitt där du kan skriva skrivarkod: **rubrikavsnitt**, **brödtext** och **sidfotsavsnitt**.</span><span class="sxs-lookup"><span data-stu-id="2b765-525">The **Printer text Layout** FastTab has three sections where you can write printer code: **Header section**, **Body section**, and **Footer section**.</span></span> <span data-ttu-id="2b765-526">I avsnittet **rubrikavsnitt** i fältet **etikettrubrik** anger du ZPL-koden för önskad rubrik.</span><span class="sxs-lookup"><span data-stu-id="2b765-526">In the **Header section** section, in the **Label header** field, enter ZPL code for the required header.</span></span> <span data-ttu-id="2b765-527">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="2b765-527">Here is an example.</span></span>

    ```plaintext
    CT~~CD,~CC^~CT~
    ^XA
    ^LH10,10
    ^FO0,0 ^AT ^FD$WHSWorkLine.ShipmentId$ ^FS
    ```

1. <span data-ttu-id="2b765-528">Den här gången behövs ingen brödtext.</span><span class="sxs-lookup"><span data-stu-id="2b765-528">This time, no body is required.</span></span> <span data-ttu-id="2b765-529">Ange därför bara den text som krävs i avsnittet **sidfotsavsnitt**.</span><span class="sxs-lookup"><span data-stu-id="2b765-529">Therefore, just enter the required text in the **Footer section** section.</span></span> <span data-ttu-id="2b765-530">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="2b765-530">Here is an example.</span></span>

    ```plaintext
    ^XZ
    ```

    <span data-ttu-id="2b765-531">Nu kan du använda din tredje etikett.</span><span class="sxs-lookup"><span data-stu-id="2b765-531">The third label is now ready to use.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2b765-532">Den tredje etiketten är en avbrottsetikett som ska användas som avgränsare mellan etikettrullar.</span><span class="sxs-lookup"><span data-stu-id="2b765-532">This third label is a break label that will be used as a divider between label rolls.</span></span>

### <a name="create-two-wave-label-types"></a><span data-ttu-id="2b765-533">Skapa två typer av påfyllnadsetiketten</span><span class="sxs-lookup"><span data-stu-id="2b765-533">Create two wave label types</span></span>

1. <span data-ttu-id="2b765-534">Gå till **Lagerstyrning \> Inställningar \> Dokumentflöde \> Typer av påfyllnadsetikett**.</span><span class="sxs-lookup"><span data-stu-id="2b765-534">Go to **Warehouse management \> Setup \> Document routing \> Wave label types**.</span></span>
1. <span data-ttu-id="2b765-535">Skapa en post med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="2b765-535">Create a record that has the following settings:</span></span>

    - <span data-ttu-id="2b765-536">**Etikettyp:** *kartong*</span><span class="sxs-lookup"><span data-stu-id="2b765-536">**Label type:** *Carton*</span></span>
    - <span data-ttu-id="2b765-537">**Beskrivning:** *kartong*</span><span class="sxs-lookup"><span data-stu-id="2b765-537">**Description:** *Carton*</span></span>

1. <span data-ttu-id="2b765-538">Skapa en andra post med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="2b765-538">Create a second record that has the following settings:</span></span>

    - <span data-ttu-id="2b765-539">**Etikettyp:** *lastpall*</span><span class="sxs-lookup"><span data-stu-id="2b765-539">**Label type:** *Pallet*</span></span>
    - <span data-ttu-id="2b765-540">**Beskrivning:** *lastpall*</span><span class="sxs-lookup"><span data-stu-id="2b765-540">**Description:** *Pallet*</span></span>

### <a name="set-up-unit-sequence-groups"></a><span data-ttu-id="2b765-541">Konfigurera enhetssekvensgrupper</span><span class="sxs-lookup"><span data-stu-id="2b765-541">Set up unit sequence groups</span></span>

1. <span data-ttu-id="2b765-542">Gå till **Lagerstyrning \> Inställningar \> Lagerställe \> Enhetsseriegrupp**.</span><span class="sxs-lookup"><span data-stu-id="2b765-542">Go to **Warehouse management \> Setup \> Warehouse \> Unit sequence groups**.</span></span>
1. <span data-ttu-id="2b765-543">Välj eller skapa en grupp för **Ea Box PL**.</span><span class="sxs-lookup"><span data-stu-id="2b765-543">Select or create an **Ea Box PL** group.</span></span>
1. <span data-ttu-id="2b765-544">För raden **ruta** ange fältet **typ av påfyllnadsnivå** till *kartong*.</span><span class="sxs-lookup"><span data-stu-id="2b765-544">For the **Box** line, set the **Wave level type** field to *Carton*.</span></span>
1. <span data-ttu-id="2b765-545">För raden **PL** ange fältet **typ av påfyllnadsnivå** till *lastpall*.</span><span class="sxs-lookup"><span data-stu-id="2b765-545">For the **PL** line, set the **Wave level type** field to *Pallet*.</span></span>

### <a name="create-wave-label-templates"></a><span data-ttu-id="2b765-546">Skapa mallar för påfyllnadsetikett</span><span class="sxs-lookup"><span data-stu-id="2b765-546">Create wave label templates</span></span>

1. <span data-ttu-id="2b765-547">Gå till **Lagerstyrning \> Inställningar \> Dokumentflöde \> Mall för påfyllnadsetikett**.</span><span class="sxs-lookup"><span data-stu-id="2b765-547">Go to **Warehouse management \> Setup \> Document routing \> Wave label templates**.</span></span>
1. <span data-ttu-id="2b765-548">Skapa en etikettmall med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="2b765-548">Create a label template that has the following settings:</span></span>

    - <span data-ttu-id="2b765-549">**Namn på etikettmallen:** *kartongetiketter*</span><span class="sxs-lookup"><span data-stu-id="2b765-549">**Label template name:** *Carton labels*</span></span>
    - <span data-ttu-id="2b765-550">**Beskrivning:** *kartongetiketter*</span><span class="sxs-lookup"><span data-stu-id="2b765-550">**Description:** *Carton labels*</span></span>
    - <span data-ttu-id="2b765-551">**Kod för påfyllnadssteg:** *kartong*</span><span class="sxs-lookup"><span data-stu-id="2b765-551">**Wave step code:** *Carton*</span></span>
    - <span data-ttu-id="2b765-552">**Lagerställe:** *62*</span><span class="sxs-lookup"><span data-stu-id="2b765-552">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="2b765-553">På snabbfliken **allmänna** i fältet **typ av påfyllnadsetikett** väljer du ett värde som *kartong*.</span><span class="sxs-lookup"><span data-stu-id="2b765-553">On the **General** FastTab, in the **Wave label type** field, select a value, such as *Carton*.</span></span>
1. <span data-ttu-id="2b765-554">På snabbfliken **information om påfyllnadsetikettens mall** och lägg till en rad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="2b765-554">On the **Wave label template details** FastTab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="2b765-555">**Etikettlayout-ID:** *kartong*</span><span class="sxs-lookup"><span data-stu-id="2b765-555">**Label layout ID:** *Carton*</span></span>
    - <span data-ttu-id="2b765-556">**Skrivarnamn:** Välj en lämplig ZPL-skrivare.</span><span class="sxs-lookup"><span data-stu-id="2b765-556">**Printer name:** Select an appropriate ZPL printer.</span></span>
    - <span data-ttu-id="2b765-557">**Kör fråga:** *Ja* (den här inställningen är valfri, men rekommenderas för optimal prestanda.)</span><span class="sxs-lookup"><span data-stu-id="2b765-557">**Run query:** *Yes* (This setting is optional, but it's recommended for optimal performance.)</span></span>

1. <span data-ttu-id="2b765-558">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="2b765-558">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="2b765-559">Valfritt: om du ställer in en kundspecifik etikettdesign måste du skapa en fråga för att hitta kundens konto.</span><span class="sxs-lookup"><span data-stu-id="2b765-559">Optional: If you're setting up a customer-specific label design, you must create a query to find the customer's account.</span></span> <span data-ttu-id="2b765-560">På snabbfliken **information om påfyllnadsetikettens mall** välj **Redigera fråga**.</span><span class="sxs-lookup"><span data-stu-id="2b765-560">On the **Wave label template details** FastTab, select **Edit query**.</span></span> <span data-ttu-id="2b765-561">I frågeredigerarens dialogruta, på fliken **Intervall** lägg till en rad med följande värden:</span><span class="sxs-lookup"><span data-stu-id="2b765-561">Then, in the query editor dialog box, on the **Range** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="2b765-562">**Register:** *försändelser*</span><span class="sxs-lookup"><span data-stu-id="2b765-562">**Table:** *Shipments*</span></span>
    - <span data-ttu-id="2b765-563">**Härlett register:** *försändelser*</span><span class="sxs-lookup"><span data-stu-id="2b765-563">**Derived table:** *Shipments*</span></span>
    - <span data-ttu-id="2b765-564">**Fält:** *Kontonummer*</span><span class="sxs-lookup"><span data-stu-id="2b765-564">**Field:** *Account number*</span></span>
    - <span data-ttu-id="2b765-565">**Kriterier:** Ange relevant kundkontonummer.</span><span class="sxs-lookup"><span data-stu-id="2b765-565">**Criteria:** Enter the relevant customer account number.</span></span>

    <span data-ttu-id="2b765-566">När du är klar klickar du på **OK** för att stänga dialogrutan för frågeredigeraren.</span><span class="sxs-lookup"><span data-stu-id="2b765-566">When you've finished, select **OK** to close the query editor dialog box.</span></span>

1. <span data-ttu-id="2b765-567">I åtgärdsfönstret, välj **Redigera fråga** för att öppna en dialogruta för frågeredigeraren för hela etikettmallen.</span><span class="sxs-lookup"><span data-stu-id="2b765-567">On the Action Pane, select **Edit query** to open the query editor dialog box for the whole label template.</span></span>
1. <span data-ttu-id="2b765-568">I frågeredigerarens dialogruta, på fliken **Sortera** lägg till en rad med följande värden:</span><span class="sxs-lookup"><span data-stu-id="2b765-568">In the query editor dialog box, on the **Sorting** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="2b765-569">**Tabell:** *Arbetsrader*</span><span class="sxs-lookup"><span data-stu-id="2b765-569">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="2b765-570">**Härlett register:** *Arbetsrader*</span><span class="sxs-lookup"><span data-stu-id="2b765-570">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="2b765-571">**Fält:** *referens till läs in rad-ID (post-ID)*</span><span class="sxs-lookup"><span data-stu-id="2b765-571">**Field:** *Reference load line id (Record-ID)*</span></span>
    - <span data-ttu-id="2b765-572">**Sökriktning:** *Stigande*</span><span class="sxs-lookup"><span data-stu-id="2b765-572">**Search direction:** *Ascending*</span></span>

1. <span data-ttu-id="2b765-573">Lägg till en andra rad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="2b765-573">Add a second row that has the following settings:</span></span>

    - <span data-ttu-id="2b765-574">**Tabell:** *Arbetsrader*</span><span class="sxs-lookup"><span data-stu-id="2b765-574">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="2b765-575">**Härlett register:** *Arbetsrader*</span><span class="sxs-lookup"><span data-stu-id="2b765-575">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="2b765-576">**Fält:** *leverans-ID*</span><span class="sxs-lookup"><span data-stu-id="2b765-576">**Field:** *Shipment ID*</span></span>
    - <span data-ttu-id="2b765-577">**Sökriktning:** *Stigande*</span><span class="sxs-lookup"><span data-stu-id="2b765-577">**Search direction:** *Ascending*</span></span>

1. <span data-ttu-id="2b765-578">Stäng dialogrutan för frågeredigeraren genom att välja **OK**.</span><span class="sxs-lookup"><span data-stu-id="2b765-578">Select **OK** to close the query editor dialog box.</span></span>
1. <span data-ttu-id="2b765-579">En meddelande ruta ber dig bekräfta åtgärden grupperingsåterställning.</span><span class="sxs-lookup"><span data-stu-id="2b765-579">A message box prompts you to confirm the grouping reset operation.</span></span> <span data-ttu-id="2b765-580">Klicka på **Ja** när du vill fortsätta.</span><span class="sxs-lookup"><span data-stu-id="2b765-580">Select **Yes** to continue.</span></span>
1. <span data-ttu-id="2b765-581">I åtgärdsfönstret, välj **mallgruppen för påfyllnadsetikett**.</span><span class="sxs-lookup"><span data-stu-id="2b765-581">On the Action Pane, select **Wave label template group**.</span></span>
1. <span data-ttu-id="2b765-582">I dialogrutan **mallgruppen för påfyllnadsetikett** för raden där fältet **Namn på referensfält** anges till *leverans-ID* anger du följande värden:</span><span class="sxs-lookup"><span data-stu-id="2b765-582">In the **Wave label template group** dialog box, for the row where the **Reference field name** field is set to *Shipment ID*, set the following values:</span></span>

    - <span data-ttu-id="2b765-583">**Skriv ut avbrottsetikett:** Markera den här kryssrutan.</span><span class="sxs-lookup"><span data-stu-id="2b765-583">**Print break label:** Select this check box.</span></span>
    - <span data-ttu-id="2b765-584">**Layout-ID för etikett:** Välj en avbrottsetikett.</span><span class="sxs-lookup"><span data-stu-id="2b765-584">**Label layout ID:** Select a break label.</span></span> <span data-ttu-id="2b765-585">(Välj t.ex. etikettlayouten *Avbrott* som du skapade tidigare i det här scenariot.)</span><span class="sxs-lookup"><span data-stu-id="2b765-585">(For example, select the *Break* label layout that you created earlier in this scenario.)</span></span>
    - <span data-ttu-id="2b765-586">**Skrivarnamn:** Välj skrivare för avbrottsetiketten.</span><span class="sxs-lookup"><span data-stu-id="2b765-586">**Printer name:** Select the printer for the break label.</span></span> <span data-ttu-id="2b765-587">(I syfte att dela upp etikettrullar bör du välja samma skrivare som väljs på snabbfliken **information om påfyllnadsetikettens mall**.</span><span class="sxs-lookup"><span data-stu-id="2b765-587">(Typically, for the purpose of splitting label rolls, you should select the same printer that is selected on the **Wave label template details** FastTab.</span></span> <span data-ttu-id="2b765-588">Andra scenarier är dock möjliga.)</span><span class="sxs-lookup"><span data-stu-id="2b765-588">However, other scenarios are possible.)</span></span>

1. <span data-ttu-id="2b765-589">Från raden där fältet **Namn på referensfält** anges till *referens till läs in rad-ID*, markera kryssrutan **etikettversions-ID**.</span><span class="sxs-lookup"><span data-stu-id="2b765-589">For the row where the **Reference field name** field is set to *Reference load line id*, select the **Label build ID** check box.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2b765-590">Med den här inställningen skapas en etikettserie ("kartong 1 av X") per lastrad i hela påfyllnaden, oavsett inställningen för arbetsgrupperingen.</span><span class="sxs-lookup"><span data-stu-id="2b765-590">This setup will create one label sequence ("Carton 1 of X") per load line throughout the wave, regardless of the work grouping setup.</span></span> <span data-ttu-id="2b765-591">Denna etikettserie kan skrivas ut på etikettlayouten.</span><span class="sxs-lookup"><span data-stu-id="2b765-591">This label sequence can be printed on a label layout.</span></span> <span data-ttu-id="2b765-592">Dessutom kommer etiketter för olika försändelser att åtskiljas med den valda avbrottsetiketten.</span><span class="sxs-lookup"><span data-stu-id="2b765-592">Additionally, labels for different shipments will be separated by the selected break label.</span></span>

1. <span data-ttu-id="2b765-593">Klicka på **OK** om du vill stänga dialogrutan **mallgruppen för påfyllnadsetikett**.</span><span class="sxs-lookup"><span data-stu-id="2b765-593">Select **OK** to close the **Wave label template group** dialog box.</span></span>
1. <span data-ttu-id="2b765-594">Skapa en andra etikettmall med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="2b765-594">Create a second label template that has the following settings:</span></span>

    - <span data-ttu-id="2b765-595">**Namn på etikettmallen:** *lastpalletiketter*</span><span class="sxs-lookup"><span data-stu-id="2b765-595">**Label template name:** *Pallet labels*</span></span>
    - <span data-ttu-id="2b765-596">**Beskrivning:** *lastpalletiketter*</span><span class="sxs-lookup"><span data-stu-id="2b765-596">**Description:** *Pallet labels*</span></span>
    - <span data-ttu-id="2b765-597">**Kod för påfyllnadssteg:** *lastpall*</span><span class="sxs-lookup"><span data-stu-id="2b765-597">**Wave step code:** *Pallet*</span></span>
    - <span data-ttu-id="2b765-598">**Lagerställe:** *62*</span><span class="sxs-lookup"><span data-stu-id="2b765-598">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="2b765-599">På snabbfliken **allmänna** i fältet **typ av påfyllnadsetikett** väljer du ett värde som *lastpall*.</span><span class="sxs-lookup"><span data-stu-id="2b765-599">On the **General** FastTab, in the **Wave label type** field, select a value, such as *Pallet*.</span></span>
1. <span data-ttu-id="2b765-600">På snabbfliken **information om påfyllnadsetikettens mall** och lägg till en rad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="2b765-600">On the **Wave label template details** FastTab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="2b765-601">**Etikettlayout-ID:** *lastpall*</span><span class="sxs-lookup"><span data-stu-id="2b765-601">**Label layout ID:** *Pallet*</span></span>
    - <span data-ttu-id="2b765-602">**Skrivarnamn:** Välj en lämplig ZPL-skrivare.</span><span class="sxs-lookup"><span data-stu-id="2b765-602">**Printer name:** Select an appropriate ZPL printer.</span></span>
    - <span data-ttu-id="2b765-603">**Kör fråga:** *Ja* (den här inställningen är valfri, men rekommenderas för optimal prestanda.)</span><span class="sxs-lookup"><span data-stu-id="2b765-603">**Run query:** *Yes* (This setting is optional, but it's recommended for optimal performance.)</span></span>

1. <span data-ttu-id="2b765-604">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="2b765-604">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="2b765-605">Valfritt: om du ställer in en kundspecifik etikettdesign måste du skapa en fråga för att hitta kundens konto.</span><span class="sxs-lookup"><span data-stu-id="2b765-605">Optional: If you're setting up a customer-specific label design, you must create a query to find the customer's account.</span></span> <span data-ttu-id="2b765-606">På snabbfliken **information om påfyllnadsetikettens mall** välj **Redigera fråga**.</span><span class="sxs-lookup"><span data-stu-id="2b765-606">On the **Wave label template details** FastTab, select **Edit query**.</span></span> <span data-ttu-id="2b765-607">I frågeredigerarens dialogruta, på fliken **Intervall** lägg till en rad med följande värden:</span><span class="sxs-lookup"><span data-stu-id="2b765-607">Then, in the query editor dialog box, on the **Range** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="2b765-608">**Register:** *försändelser*</span><span class="sxs-lookup"><span data-stu-id="2b765-608">**Table:** *Shipments*</span></span>
    - <span data-ttu-id="2b765-609">**Härlett register:** *försändelser*</span><span class="sxs-lookup"><span data-stu-id="2b765-609">**Derived table:** *Shipments*</span></span>
    - <span data-ttu-id="2b765-610">**Fält:** *Kontonummer*</span><span class="sxs-lookup"><span data-stu-id="2b765-610">**Field:** *Account number*</span></span>
    - <span data-ttu-id="2b765-611">**Kriterier:** Ange relevant kundkontonummer.</span><span class="sxs-lookup"><span data-stu-id="2b765-611">**Criteria:** Enter the relevant customer account number.</span></span>

    <span data-ttu-id="2b765-612">När du är klar klickar du på **OK** för att stänga dialogrutan för frågeredigeraren.</span><span class="sxs-lookup"><span data-stu-id="2b765-612">When you've finished, select **OK** to close the query editor dialog box.</span></span> 

1. <span data-ttu-id="2b765-613">I åtgärdsfönstret, välj **Redigera fråga** för att öppna en dialogruta för frågeredigeraren för hela etikettmallen.</span><span class="sxs-lookup"><span data-stu-id="2b765-613">On the Action Pane, select **Edit query** to open the query editor dialog box for the whole label template.</span></span>
1. <span data-ttu-id="2b765-614">I frågeredigerarens dialogruta, på fliken **Sortera** lägg till en rad med följande värden:</span><span class="sxs-lookup"><span data-stu-id="2b765-614">In the query editor dialog box, on the **Sorting** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="2b765-615">**Tabell:** *Arbetsrader*</span><span class="sxs-lookup"><span data-stu-id="2b765-615">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="2b765-616">**Härlett register:** *Arbetsrader*</span><span class="sxs-lookup"><span data-stu-id="2b765-616">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="2b765-617">**Fält:** *referens till läs in rad-ID (post-ID)*</span><span class="sxs-lookup"><span data-stu-id="2b765-617">**Field:** *Reference load line id (Record-ID)*</span></span>
    - <span data-ttu-id="2b765-618">**Sökriktning:** *Stigande*</span><span class="sxs-lookup"><span data-stu-id="2b765-618">**Search direction:** *Ascending*</span></span>

1. <span data-ttu-id="2b765-619">Lägg till en andra rad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="2b765-619">Add a second row that has the following settings:</span></span>

    - <span data-ttu-id="2b765-620">**Tabell:** *Arbetsrader*</span><span class="sxs-lookup"><span data-stu-id="2b765-620">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="2b765-621">**Härlett register:** *Arbetsrader*</span><span class="sxs-lookup"><span data-stu-id="2b765-621">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="2b765-622">**Fält:** *leverans-ID*</span><span class="sxs-lookup"><span data-stu-id="2b765-622">**Field:** *Shipment ID*</span></span>
    - <span data-ttu-id="2b765-623">**Sökriktning:** *Stigande*</span><span class="sxs-lookup"><span data-stu-id="2b765-623">**Search direction:** *Ascending*</span></span>

1. <span data-ttu-id="2b765-624">Stäng dialogrutan för frågeredigeraren genom att välja **OK**.</span><span class="sxs-lookup"><span data-stu-id="2b765-624">Select **OK** to close the query editor dialog box.</span></span>
1. <span data-ttu-id="2b765-625">En meddelande ruta ber dig bekräfta åtgärden grupperingsåterställning.</span><span class="sxs-lookup"><span data-stu-id="2b765-625">A message box prompts you to confirm the grouping reset operation.</span></span> <span data-ttu-id="2b765-626">Klicka på **Ja** när du vill fortsätta.</span><span class="sxs-lookup"><span data-stu-id="2b765-626">Select **Yes** to continue.</span></span>
1. <span data-ttu-id="2b765-627">I åtgärdsfönstret, välj **mallgruppen för påfyllnadsetikett**.</span><span class="sxs-lookup"><span data-stu-id="2b765-627">On the Action Pane, select **Wave label template group**.</span></span>
1. <span data-ttu-id="2b765-628">I dialogrutan **mallgruppen för påfyllnadsetikett** för raden där fältet **Namn på referensfält** anges till *leverans-ID* anger du följande värden:</span><span class="sxs-lookup"><span data-stu-id="2b765-628">In the **Wave label template group** dialog box, for the row where the **Reference field name** field is set to *Shipment ID*, set the following values:</span></span>

    - <span data-ttu-id="2b765-629">**Skriv ut avbrottsetikett:** Markera den här kryssrutan.</span><span class="sxs-lookup"><span data-stu-id="2b765-629">**Print break label:** Select this check box.</span></span>
    - <span data-ttu-id="2b765-630">**Layout-ID för etikett:** Välj en avbrottsetikett.</span><span class="sxs-lookup"><span data-stu-id="2b765-630">**Label layout ID:** Select a break label.</span></span> <span data-ttu-id="2b765-631">(Välj t.ex. etikettlayouten *Avbrott* som du skapade tidigare i det här scenariot.)</span><span class="sxs-lookup"><span data-stu-id="2b765-631">(For example, select the *Break* label layout that you created earlier in this scenario.)</span></span>
    - <span data-ttu-id="2b765-632">**Skrivarnamn:** Välj skrivare för avbrottsetiketten.</span><span class="sxs-lookup"><span data-stu-id="2b765-632">**Printer name:** Select the printer for the break label.</span></span> <span data-ttu-id="2b765-633">(I syfte att dela upp etikettrullar bör du välja samma skrivare som väljs på snabbfliken **information om påfyllnadsetikettens mall**.</span><span class="sxs-lookup"><span data-stu-id="2b765-633">(Typically, for the purpose of splitting label rolls, you should select the same printer that is selected on the **Wave label template details** FastTab.</span></span> <span data-ttu-id="2b765-634">Andra scenarier är dock möjliga.)</span><span class="sxs-lookup"><span data-stu-id="2b765-634">However, other scenarios are possible.)</span></span>

1. <span data-ttu-id="2b765-635">Från raden där fältet **Namn på referensfält** anges till *referens till läs in rad-ID*, markera kryssrutan **etikettversions-ID**.</span><span class="sxs-lookup"><span data-stu-id="2b765-635">For the row where the **Reference field name** field is set to *Reference load line id*, select the **Label build ID** check box.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2b765-636">Med den här inställningen skapas en etikettserie ("kartong 1 av X") per lastrad i hela påfyllnaden, oavsett inställningen för arbetsgrupperingen.</span><span class="sxs-lookup"><span data-stu-id="2b765-636">This setup will create one label sequence ("Carton 1 of X") per load line throughout the wave, regardless of the work grouping setup.</span></span> <span data-ttu-id="2b765-637">Denna etikettserie kan skrivas ut på etikettlayouten.</span><span class="sxs-lookup"><span data-stu-id="2b765-637">This label sequence can be printed on a label layout.</span></span> <span data-ttu-id="2b765-638">Dessutom kommer etiketter för olika försändelser att åtskiljas med den valda avbrottsetiketten.</span><span class="sxs-lookup"><span data-stu-id="2b765-638">Additionally, labels for different shipments will be separated by the selected break label.</span></span>

### <a name="configure-number-sequence-extensions"></a><span data-ttu-id="2b765-639">Konfigurera nummerserietillägg</span><span class="sxs-lookup"><span data-stu-id="2b765-639">Configure number sequence extensions</span></span>

<span data-ttu-id="2b765-640">Nummerserietillägg styr GS1 efterlevnaden av specifika nummerserier.</span><span class="sxs-lookup"><span data-stu-id="2b765-640">Number sequence extensions control the GS1 compliance of specific number sequences.</span></span> <span data-ttu-id="2b765-641">Den här konfigurationen är valfri för det aktuella scenariot.</span><span class="sxs-lookup"><span data-stu-id="2b765-641">This configuration is optional for the current scenario.</span></span> <span data-ttu-id="2b765-642">Mer information och instruktioner för konfigurering finns i [Konfigurera tillägg för nummerserier](../warehousing/configure-number-sequence-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="2b765-642">For more information and configuration instructions, see [Configure number sequence extensions](../warehousing/configure-number-sequence-extensions.md).</span></span>

### <a name="create-a-sales-order-and-release-it-to-the-warehouse"></a><span data-ttu-id="2b765-643">Skapa en försäljningsorder och släpp den på lagerstället</span><span class="sxs-lookup"><span data-stu-id="2b765-643">Create a sales order and release it to the warehouse</span></span>

1. <span data-ttu-id="2b765-644">Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="2b765-644">Go to **Sales and marketing \> Sales order \> All sales orders**.</span></span>
1. <span data-ttu-id="2b765-645">Skapa en försäljningsorder med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="2b765-645">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="2b765-646">**Kundkonto:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="2b765-646">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="2b765-647">**Lagerställe:** *62*</span><span class="sxs-lookup"><span data-stu-id="2b765-647">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="2b765-648">Lägg till två försäljningsorderrader:</span><span class="sxs-lookup"><span data-stu-id="2b765-648">Add two sales order lines:</span></span>

    - <span data-ttu-id="2b765-649">Försäljningsorderrad 1:</span><span class="sxs-lookup"><span data-stu-id="2b765-649">Sales order line 1:</span></span>

        - <span data-ttu-id="2b765-650">**Artikelnummer:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="2b765-650">**Item number:** *A0001*</span></span>
        - <span data-ttu-id="2b765-651">**Kvantitet:** *9024*</span><span class="sxs-lookup"><span data-stu-id="2b765-651">**Quantity:** *9024*</span></span>
        - <span data-ttu-id="2b765-652">**Enhet:** *ea* (9024 ea = 376 låda = 47 PL)</span><span class="sxs-lookup"><span data-stu-id="2b765-652">**Unit:** *ea* (9024 ea = 376 Box = 47 PL)</span></span>

    - <span data-ttu-id="2b765-653">Försäljningsorderrad 2:</span><span class="sxs-lookup"><span data-stu-id="2b765-653">Sales order line 2:</span></span>

        - <span data-ttu-id="2b765-654">**Artikelnummer:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="2b765-654">**Item number:** *A0002*</span></span>
        - <span data-ttu-id="2b765-655">**Kvantitet:** *9016*</span><span class="sxs-lookup"><span data-stu-id="2b765-655">**Quantity:** *9016*</span></span>
        - <span data-ttu-id="2b765-656">**Enhet:** *ea* (9016 ea = 322 box = 46 PL)</span><span class="sxs-lookup"><span data-stu-id="2b765-656">**Unit:** *ea* (9016 ea = 322 Box = 46 PL)</span></span>

    > [!NOTE]
    > <span data-ttu-id="2b765-657">Artiklarna och kvantiteterna som anges här är endast exempel.</span><span class="sxs-lookup"><span data-stu-id="2b765-657">The items and quantities that are provided here are only examples.</span></span> <span data-ttu-id="2b765-658">De måste använda den enhetsseriegrupp som du definierade tidigare, och lämpliga enhetskonverteringar från *ea* till *Box* till *PL* måste definieras för dem och de måste ha lager i lagerställe *62*.</span><span class="sxs-lookup"><span data-stu-id="2b765-658">They must use the unit sequence group that you defined earlier, appropriate unit conversions from *ea* to *Box* to *PL* must be defined for them, and they must have stock in warehouse *62*.</span></span> <span data-ttu-id="2b765-659">Mer information finns i [måttenhet och lagerprinciper](unit-measure-stocking-policies.md).</span><span class="sxs-lookup"><span data-stu-id="2b765-659">For more information, see [Unit of measure and stocking policies](unit-measure-stocking-policies.md).</span></span>

1. <span data-ttu-id="2b765-660">Välj försäljningsorderrad 1.</span><span class="sxs-lookup"><span data-stu-id="2b765-660">Select sales order line 1.</span></span> <span data-ttu-id="2b765-661">I avsnittet **Försäljningsorderrad** i menyn **Lager** välj **Reservationer**.</span><span class="sxs-lookup"><span data-stu-id="2b765-661">Then, in the **Sales order line** section, on the **Inventory** menu, select **Reservations**.</span></span>
1. <span data-ttu-id="2b765-662">På sidan **Reservation** i åtgärdsfönstret, välj **Reservera parti** och stäng sedan sidan.</span><span class="sxs-lookup"><span data-stu-id="2b765-662">On the **Reservation** page, on the Action Pane, select **Reserve lot**, and then close the page.</span></span>
1. <span data-ttu-id="2b765-663">Upprepa steg 4 och 5 för försäljningsorderrad 2.</span><span class="sxs-lookup"><span data-stu-id="2b765-663">Repeat steps 4 and 5 for sales order line 2.</span></span>
1. <span data-ttu-id="2b765-664">I åtgärdsfönstret på fliken **Lagerställe** välj **Frisläpp till regel för lagerställe**.</span><span class="sxs-lookup"><span data-stu-id="2b765-664">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="2b765-665">Då inträffar följande händelser:</span><span class="sxs-lookup"><span data-stu-id="2b765-665">The following events occur:</span></span> 

    - <span data-ttu-id="2b765-666">I systemet bearbetas den skapade utleveransen med hjälp av mallen som inkluderar utskriftssteget för etikett.</span><span class="sxs-lookup"><span data-stu-id="2b765-666">The system processes the created shipment by using the template that includes the label printing step.</span></span> <span data-ttu-id="2b765-667">Etikettlayouten används för att definiera etikettens format, och resultatet blir en etikett som skrivs ut på den skrivare som väljs i etikettmallen.</span><span class="sxs-lookup"><span data-stu-id="2b765-667">The label layout will be used to define the format of the label, and the result will be a label that is printed on the printer that is selected in the label template.</span></span>
    - <span data-ttu-id="2b765-668">Påfyllnadsetiketter genereras och skrivs ut.</span><span class="sxs-lookup"><span data-stu-id="2b765-668">Wave labels are generated and printed.</span></span> <span data-ttu-id="2b765-669">Antalet etiketter är lika med antalet kartonger (i det här exemplet är 376 boxetiketter för rad 1, 322 boxetiketter för rad 2, 47 PL-etiketter för rad 1, 47 PL-etiketter för rad 2 och två avbrottsetiketter med leverans-ID).</span><span class="sxs-lookup"><span data-stu-id="2b765-669">The number of labels will equal the number of cartons (in this example, 376 Box labels for line 1, 322 Box labels for line 2, 47 PL labels for line 1, 47 PL labels for line 2, and two break labels that have the shipment ID).</span></span>
    - <span data-ttu-id="2b765-670">Ett nytt fraktsedels-ID genereras för leveranserna.</span><span class="sxs-lookup"><span data-stu-id="2b765-670">A new bill of lading ID is generated for the shipments.</span></span> <span data-ttu-id="2b765-671">Om du har konfigurerat nummerserietilläggen följer påfyllnadsetikett-ID nummerformatet **SSCC-18**.</span><span class="sxs-lookup"><span data-stu-id="2b765-671">If you configured the number sequence extensions, the wave label IDs will follow the **SSCC-18** number format.</span></span> 

<span data-ttu-id="2b765-672">Du kan visa och skriva ut påfyllnadsetiketter på följande sidor:</span><span class="sxs-lookup"><span data-stu-id="2b765-672">You can view and reprint wave labels from the following pages:</span></span>

- <span data-ttu-id="2b765-673">Alla leveranser \> leveransinformation</span><span class="sxs-lookup"><span data-stu-id="2b765-673">All shipments \> Shipment details</span></span>
- <span data-ttu-id="2b765-674">Alla laster \> Läs in information</span><span class="sxs-lookup"><span data-stu-id="2b765-674">All loads \> Load details</span></span>
- <span data-ttu-id="2b765-675">Alla påfyllnader</span><span class="sxs-lookup"><span data-stu-id="2b765-675">All waves</span></span>
- <span data-ttu-id="2b765-676">Påfyllnadsetiketter</span><span class="sxs-lookup"><span data-stu-id="2b765-676">Wave labels</span></span>
- <span data-ttu-id="2b765-677">Etiketthistorik för påfyllnad</span><span class="sxs-lookup"><span data-stu-id="2b765-677">Wave label history</span></span>

<span data-ttu-id="2b765-678">För de flesta av dessa sidor hittar du den relevanta funktionen genom att välja **Påfyllnadsetiketter** i gruppen **Relaterad information** i fliken **leveranser** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="2b765-678">For most of these pages, you can find the relevant function by selecting **Wave labels** in the **Related information** group on the **Shipments** tab of the Action Pane.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2b765-679">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="2b765-679">Additional resources</span></span>

- [<span data-ttu-id="2b765-680">Skriva ut på nytt och annullera påfyllnadsetiketter</span><span class="sxs-lookup"><span data-stu-id="2b765-680">Reprint and void wave labels</span></span>](reprint-and-void-wave-labels.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]