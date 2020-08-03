---
title: Ställa in och använda utskrift av påfyllnadsetikett
description: Det här ämnet beskriver utskrift av påfyllnadsetikett och förklarar hur du ställer in det.
author: GarmMSFT
manager: PJacobse
ms.date: 05/01/2020
ms.topic: configure-wave-label-printing
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWaveLabel, WHSWaveLabelTemplate
audience: Application User
ms.reviewer: PJacobse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: v-olbara
ms.search.validFrom: yyyy-mm-dd
ms.dyn365.ops.version: 10.0.0
ms.openlocfilehash: 49e0ef1b3020cd1236203c0f243f145dd7a7c10d
ms.sourcegitcommit: 137e2bd30f0a85bd2e1baf1cf16b993edd2094f9
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/09/2020
ms.locfileid: "3546465"
---
# <a name="set-up-and-use-wave-label-printing"></a><span data-ttu-id="f4d80-103">Ställa in och använda utskrift av påfyllnadsetikett</span><span class="sxs-lookup"><span data-stu-id="f4d80-103">Set up and use wave label printing</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f4d80-104">Utskrift av påfyllnadsetikett ger en alternativ metod för att skriva ut etiketter genom att introducera en ny påfyllnadsmetod som gör att du kan skapa och skriva ut etiketter direkt från påfyllnadsmallen under påfyllnadskörningen.</span><span class="sxs-lookup"><span data-stu-id="f4d80-104">Wave label printing offers an alternative approach to label printing by introducing a new wave step method that lets you create and print labels directly from the wave template during wave execution.</span></span> <span data-ttu-id="f4d80-105">Därför är etiketterna redan tillgängliga innan arbetare kör arbetsordern på en mobil enhet.</span><span class="sxs-lookup"><span data-stu-id="f4d80-105">Therefore, the labels will already be available before workers run the work order on a mobile device.</span></span> <span data-ttu-id="f4d80-106">Arbetare kan sedan koppla de begärda etiketterna under plockning i stället för efter plockning.</span><span class="sxs-lookup"><span data-stu-id="f4d80-106">Workers can then attach the required labels during picking instead of after picking.</span></span>

<span data-ttu-id="f4d80-107">Utskrift av påfyllnadsetikett använder zebraprogrammeringspråket (ZPL) när du skapar etikettlayout.</span><span class="sxs-lookup"><span data-stu-id="f4d80-107">Wave label printing uses Zebra Programming Language (ZPL) to create label layouts.</span></span> <span data-ttu-id="f4d80-108">En etikettlayout är uppdelad i tre avsnitt (rubrik, brödtext och sidfot) som tillåter etiketter som har en upprepande struktur.</span><span class="sxs-lookup"><span data-stu-id="f4d80-108">A label layout is divided into three sections (header, body, and footer) to allow for labels that have repeating structure.</span></span> <span data-ttu-id="f4d80-109">Mallar för etikettutskrift anger du vilket system som etikettexten ska använda.</span><span class="sxs-lookup"><span data-stu-id="f4d80-109">Wave label templates tell the system which label layout to use.</span></span> <span data-ttu-id="f4d80-110">Användare kan ange vilken skrivare som ska användas.</span><span class="sxs-lookup"><span data-stu-id="f4d80-110">Users can specify which printer is used.</span></span> <span data-ttu-id="f4d80-111">De kan också skriva ut etiketter på flera skrivare samtidigt, eftersom de kräver det.</span><span class="sxs-lookup"><span data-stu-id="f4d80-111">They can also print labels on several printers at the same time, as they require.</span></span> <span data-ttu-id="f4d80-112">Sidan **påfyllnadsetiketthistoriken** visar en post över alla etiketter som har skapats med hjälp av den här inställningen.</span><span class="sxs-lookup"><span data-stu-id="f4d80-112">The **Wave label history** page shows a record of all labels that have been created by using this setup.</span></span>

<span data-ttu-id="f4d80-113">Du kan skriva ut och sortera etiketter baserat på arbetsrubriker, du kan skriva ut avbrottsetiketter per arbetsrubrik och du kan skriva ut behållarens innehållsetiketter, ärendeetiketter och andra liknande etiketter.</span><span class="sxs-lookup"><span data-stu-id="f4d80-113">You can print and collate labels based on work headers, you can print break labels per work header, and you can print container content labels, case labels, and other similar labels.</span></span>

> [!NOTE]
> <span data-ttu-id="f4d80-114">Den här funktionen ersätter inte de befintliga funktionerna för etikettutskrift som baseras på dokumentflödet.</span><span class="sxs-lookup"><span data-stu-id="f4d80-114">This functionality doesn't replace existing label printing functionality that is based on document routing.</span></span>

<span data-ttu-id="f4d80-115">Utskrift av påfyllnadsetikett ger följande förbättringar:</span><span class="sxs-lookup"><span data-stu-id="f4d80-115">Wave label printing offers the following enhancements:</span></span>

- <span data-ttu-id="f4d80-116">Skriv ut etiketter enligt antalet kartonger på en enda arbetsrad, utan att använda skapande av behållare.</span><span class="sxs-lookup"><span data-stu-id="f4d80-116">Print labels according to the number of cartons on a single work line, without using containerization.</span></span> <span data-ttu-id="f4d80-117">(En "kartong" är en enhet som har angetts för enhetssekvensgruppraderna.)</span><span class="sxs-lookup"><span data-stu-id="f4d80-117">(A "carton" is a unit that is designated on unit sequence group lines.)</span></span>
- <span data-ttu-id="f4d80-118">Skriv ut flera olika etikettserier (t.ex. kartonger och lastpallsetiketter).</span><span class="sxs-lookup"><span data-stu-id="f4d80-118">Print several different label sequences (for example, carton and pallet labels).</span></span>
- <span data-ttu-id="f4d80-119">Inkludera etikettuppräkning (t.ex. 1/124, 2/124... 124/124) och definiera intervallet för uppräkningen (t.ex. arbetsrad, lastrad eller leverans).</span><span class="sxs-lookup"><span data-stu-id="f4d80-119">Include label enumeration (for example, 1/124, 2/124, ... 124/124), and define the range of enumeration (for example, work line, load line, or shipment).</span></span>
- <span data-ttu-id="f4d80-120">Skapa och skriv ut ett fraktsedels-ID på etiketter innan fraktsedeln genereras.</span><span class="sxs-lookup"><span data-stu-id="f4d80-120">Create and print a bill of lading ID on labels before the bill of lading is generated.</span></span>
- <span data-ttu-id="f4d80-121">Skapa en unik serie för seriell leveransbehållare (SSCC) för varje kartong och inkludera den på varje etikett.</span><span class="sxs-lookup"><span data-stu-id="f4d80-121">Create a unique serial shipping container code (SSCC) for each carton, and include it on each label.</span></span>
- <span data-ttu-id="f4d80-122">Skapa GS1-kompatibla nummerserier för fraktsedels-ID och SSCC.</span><span class="sxs-lookup"><span data-stu-id="f4d80-122">Create GS1-compliant number sequences for bill of lading IDs and SSCCs.</span></span>
- <span data-ttu-id="f4d80-123">Skriv ut etiketterna på både mobila enheter och den avancerade klienten.</span><span class="sxs-lookup"><span data-stu-id="f4d80-123">Reprint labels from both mobile devices and the rich client.</span></span>
- <span data-ttu-id="f4d80-124">Annullera etiketter (t.ex. i korta plockningsscenarier) och skriv ut dem igen.</span><span class="sxs-lookup"><span data-stu-id="f4d80-124">Void labels (for example, in short pick scenarios), and reprint them.</span></span>
- <span data-ttu-id="f4d80-125">Rensa historik för påfyllnadsetikett.</span><span class="sxs-lookup"><span data-stu-id="f4d80-125">Clean up the wave label history.</span></span>
- <span data-ttu-id="f4d80-126">Förbättringar av layouter av dokumentflöde delas mellan dokumentflödets layout och påfyllnadsetikettens layout.</span><span class="sxs-lookup"><span data-stu-id="f4d80-126">Improvements to document routing layouts are shared between document routing layouts and wave label layouts.</span></span> <span data-ttu-id="f4d80-127">(Mer information finns i [Layout för dokumentflöde för ID-nummer](../warehousing/document-routing-layout-for-license-plates.md) .)</span><span class="sxs-lookup"><span data-stu-id="f4d80-127">(For more information, see [Document routing layout for license plates](../warehousing/document-routing-layout-for-license-plates.md).)</span></span>

<span data-ttu-id="f4d80-128">Dessa förbättringar gör det effektivare att märka kartonger före palletering.</span><span class="sxs-lookup"><span data-stu-id="f4d80-128">These enhancements make it more efficient to label cartons before palletization.</span></span> <span data-ttu-id="f4d80-129">De gynnar främst företag som levererar till stora återförsäljare som automatiskt bekräftar orderkvitton genom att söka igenom varje kartong separat.</span><span class="sxs-lookup"><span data-stu-id="f4d80-129">They especially benefit companies that ship to large retailers that automatically confirm order receipts by scanning each carton separately.</span></span>

> [!NOTE]
> <span data-ttu-id="f4d80-130">Du kan implementera konfigurationsscenarier som beskrivs i det här avsnittet, antingen separat eller i kombination, beroende på dina affärsbehov.</span><span class="sxs-lookup"><span data-stu-id="f4d80-130">You can implement the configuration scenarios that are described in this topic either separately or in combination, depending on your business requirements.</span></span> <span data-ttu-id="f4d80-131">Du kan skapa flera påfyllnadsetikettmallar som fungerar i ordningsföljd (som illustreras i scenario 3).</span><span class="sxs-lookup"><span data-stu-id="f4d80-131">You can design several wave label templates that work in sequence (as illustrated in scenario 3).</span></span> <span data-ttu-id="f4d80-132">Du kan till exempel använda scenario 1 för att skriva ut kartonger och scenario 2 om du vill skriva ut lastpallsetiketter (om lastpallar i lagret varierar i storlek och sammansättning).</span><span class="sxs-lookup"><span data-stu-id="f4d80-132">For example, you can use scenario 1 to print carton labels and scenario 2 to print pallet labels (if pallets in stock vary in size and composition).</span></span>

## <a name="turn-on-the-wave-label-printing-feature"></a><span data-ttu-id="f4d80-133">Aktivera funktionen utskrift av påfyllnadsetiketter</span><span class="sxs-lookup"><span data-stu-id="f4d80-133">Turn on the Wave label printing feature</span></span>

<span data-ttu-id="f4d80-134">Innan du kan använda funktionen *utskrift av påfyllnadsmall* den aktiveras i ditt system.</span><span class="sxs-lookup"><span data-stu-id="f4d80-134">Before you can use the *Wave label printing* feature, it must be turned on in your system.</span></span> <span data-ttu-id="f4d80-135">Administratörer kan använda arbetsytan [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den om det behövs.</span><span class="sxs-lookup"><span data-stu-id="f4d80-135">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="f4d80-136">Funktionen visas på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="f4d80-136">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="f4d80-137">**Modul:** *Lagerstyrning*</span><span class="sxs-lookup"><span data-stu-id="f4d80-137">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="f4d80-138">**Funktionsnamn:** *utskrift av påfyllnadsetiketter*</span><span class="sxs-lookup"><span data-stu-id="f4d80-138">**Feature name:** *Wave label printing*</span></span>

## <a name="scenario-1-wave-label-printing-where-a-single-wave-label-is-generated"></a><span data-ttu-id="f4d80-139">Scenario 1: utskrift av påfyllnadsetiketter där en enskild påfyllnadsetikett genereras</span><span class="sxs-lookup"><span data-stu-id="f4d80-139">Scenario 1: Wave label printing where a single wave label is generated</span></span>

<span data-ttu-id="f4d80-140">Det här scenariot visar hur ett företag kan skriva ut leveransetiketter för en stor återförsäljare som automatiskt bekräftar orderkvitton genom att söka igenom varje kartong separat.</span><span class="sxs-lookup"><span data-stu-id="f4d80-140">This scenario shows how a company can print shipping labels for a large retailer that automatically confirms order receipts by scanning each carton separately.</span></span>

<span data-ttu-id="f4d80-141">Det här scenariot visar komplett flöde.</span><span class="sxs-lookup"><span data-stu-id="f4d80-141">This scenario shows the end-to-end flow.</span></span>

### <a name="make-demo-data-available"></a><span data-ttu-id="f4d80-142">Gör demodata tillgängliga</span><span class="sxs-lookup"><span data-stu-id="f4d80-142">Make demo data available</span></span>

<span data-ttu-id="f4d80-143">För att följa detta scenario måste du ha demonstrationsdata installerad och du måste välja juridiska personen **USMF**.</span><span class="sxs-lookup"><span data-stu-id="f4d80-143">To follow this scenario, you must have demo data installed, and you must select the **USMF** legal entity.</span></span>

### <a name="make-sure-that-the-wave-label-method-is-available"></a><span data-ttu-id="f4d80-144">Kontrollera att påfyllnadsetikett metoden är tillgänglig</span><span class="sxs-lookup"><span data-stu-id="f4d80-144">Make sure that the wave label method is available</span></span>

<span data-ttu-id="f4d80-145">Du måste kanske återskapa dina metoder för påfyllnadsprocess för att göra påfyllnadsetikett metoden tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="f4d80-145">You might have to regenerate the wave process methods to make the wave label printing method available.</span></span>

1. <span data-ttu-id="f4d80-146">Gå till **Lagerstyrning \> Inställningar \> Påfyllnader \> Metoder för påfyllnadsprocess**.</span><span class="sxs-lookup"><span data-stu-id="f4d80-146">Go to **Warehouse management \> Setup \> Waves \> Wave process methods**.</span></span>
1. <span data-ttu-id="f4d80-147">Kontrollera att **waveLabelPrinting** finns i listan.</span><span class="sxs-lookup"><span data-stu-id="f4d80-147">Confirm that **waveLabelPrinting** is in the list.</span></span> <span data-ttu-id="f4d80-148">Om den inte finns med väljer du **återskapa metoder** i åtgärdsfönstret för att lägga till den.</span><span class="sxs-lookup"><span data-stu-id="f4d80-148">If it isn't, select **Regenerate methods** on the Action Pane to add it.</span></span>

### <a name="configure-a-wave-template"></a><span data-ttu-id="f4d80-149">Konfigurera en påfyllnadsmall</span><span class="sxs-lookup"><span data-stu-id="f4d80-149">Configure a wave template</span></span>

<span data-ttu-id="f4d80-150">Med påfyllnadsmallar kan du länka specifika förekomster av påfyllnadsmetoder till en motsvarande påfyllnadsetikettsmall.</span><span class="sxs-lookup"><span data-stu-id="f4d80-150">Wave templates let you link specific instances of wave methods to a corresponding wave label template.</span></span>

1. <span data-ttu-id="f4d80-151">Gå till **Lagerstyrning \> Inställningar \> Påfyllnader \> Påfyllnadsmallar**.</span><span class="sxs-lookup"><span data-stu-id="f4d80-151">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
1. <span data-ttu-id="f4d80-152">Välj en mall som **62 standard för leverans**.</span><span class="sxs-lookup"><span data-stu-id="f4d80-152">Select a template, such as **62 Shipping Default**.</span></span>
1. <span data-ttu-id="f4d80-153">På snabbfliken **metoder** flyttar du metoden **utskrift av påfyllnadsetiketter** till kolumnen **valda metoder**.</span><span class="sxs-lookup"><span data-stu-id="f4d80-153">On the **Methods** FastTab, move the **Wave label printing** method to the **Selected methods** column.</span></span>
1. <span data-ttu-id="f4d80-154">I kolumnen **Valda metoder** välj metoden **Utskrift av påfyllnadsetiketter** och ange dess fält **Kod för påfyllnadssteg** till *PrintLabel*.</span><span class="sxs-lookup"><span data-stu-id="f4d80-154">In the **Selected methods** column, select the **Wave label printing** method, and set its **Wave step code** field to *PrintLabel*.</span></span> <span data-ttu-id="f4d80-155">För mer information om koder för påfyllnadssteg, se [Koder för påfyllnadssteg](wave-step-codes.md).</span><span class="sxs-lookup"><span data-stu-id="f4d80-155">For more information about wave step codes, see [Wave step codes](wave-step-codes.md).</span></span>

### <a name="create-a-wave-label-layout"></a><span data-ttu-id="f4d80-156">Skapa en layout för påfyllnadsetiketten</span><span class="sxs-lookup"><span data-stu-id="f4d80-156">Create a wave label layout</span></span>

<span data-ttu-id="f4d80-157">Etikettlayouten bestämmer vilken information som ska skrivas ut på etiketten och hur den visas. Här anger du koden för ZPL som skickas till skrivaren.</span><span class="sxs-lookup"><span data-stu-id="f4d80-157">The label layout controls what information is printed on the label and how it's laid out. Here, you enter the ZPL code that is sent to the printer.</span></span>

1. <span data-ttu-id="f4d80-158">Gå till **Lagerstyrning \> Inställningar \> Dokumentflöde \> Layout för påfyllnadsetikett**.</span><span class="sxs-lookup"><span data-stu-id="f4d80-158">Go to **Warehouse management \> Setup \> Document routing \> Wave label layouts**.</span></span>
1. <span data-ttu-id="f4d80-159">Skapa en post med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="f4d80-159">Create a record that has the following settings:</span></span>

    - <span data-ttu-id="f4d80-160">**Etikettlayout-ID:** *kartong*</span><span class="sxs-lookup"><span data-stu-id="f4d80-160">**Label layout ID:** *Carton*</span></span>
    - <span data-ttu-id="f4d80-161">**Beskrivning:** *kartong (SSCC)*</span><span class="sxs-lookup"><span data-stu-id="f4d80-161">**Description:** *Carton (SSCC)*</span></span>

1. <span data-ttu-id="f4d80-162">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="f4d80-162">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="f4d80-163">I åtgärdsfönstret, välj **Inställningar för påfyllnadsetikettrad**.</span><span class="sxs-lookup"><span data-stu-id="f4d80-163">On the Action Pane, select **Wave label row settings**.</span></span>

    <span data-ttu-id="f4d80-164">Sidan **Inställningar för påfyllnadsetikettrad** visas.</span><span class="sxs-lookup"><span data-stu-id="f4d80-164">The **Wave label row settings** page appears.</span></span> <span data-ttu-id="f4d80-165">Här kan du konfigurera den dynamiska delen av etiketten.</span><span class="sxs-lookup"><span data-stu-id="f4d80-165">Here, you can configure the dynamic part of the label.</span></span>

1. <span data-ttu-id="f4d80-166">Lägg till en rad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="f4d80-166">Add a row that has the following settings:</span></span>

    - <span data-ttu-id="f4d80-167">**Rad-ID:** *WaveLabel*</span><span class="sxs-lookup"><span data-stu-id="f4d80-167">**Row Id:** *WaveLabel*</span></span>
    - <span data-ttu-id="f4d80-168">**Radtabellnamn:** *WHSWaveLabel*</span><span class="sxs-lookup"><span data-stu-id="f4d80-168">**Row table name:** *WHSWaveLabel*</span></span>
    - <span data-ttu-id="f4d80-169">**Radens startposition:** *0*</span><span class="sxs-lookup"><span data-stu-id="f4d80-169">**Row start position:** *0*</span></span>

        <span data-ttu-id="f4d80-170">I det här fältet definieras den lodräta position där raden ska börja etiketten.</span><span class="sxs-lookup"><span data-stu-id="f4d80-170">This field defines the vertical position where the row will begin on the label.</span></span>

    - <span data-ttu-id="f4d80-171">**Radhöjd:** *0*</span><span class="sxs-lookup"><span data-stu-id="f4d80-171">**Row height:** *0*</span></span>

        <span data-ttu-id="f4d80-172">I det här fältet definieras höjden på varje rad (i punkter) enligt ZPL-standard.</span><span class="sxs-lookup"><span data-stu-id="f4d80-172">This field defines the height of each row (in points), according to the ZPL standard.</span></span> <span data-ttu-id="f4d80-173">Radhöjden är positiv för vågräta etiketter och är negativ för lodräta etiketter.</span><span class="sxs-lookup"><span data-stu-id="f4d80-173">The row height is positive for horizontal labels and negative for vertical labels.</span></span> <span data-ttu-id="f4d80-174">Eftersom det bara finns en rad i det här exemplet kan du ställa in värdet på *0* (noll).</span><span class="sxs-lookup"><span data-stu-id="f4d80-174">Because there is just one row in this example, you can set the value to *0* (zero).</span></span>

    - <span data-ttu-id="f4d80-175">**Rader per sida:** *1*</span><span class="sxs-lookup"><span data-stu-id="f4d80-175">**Rows per page:** *1*</span></span>

        <span data-ttu-id="f4d80-176">I det här fältet definieras antalet rader som kan skrivas ut på varje etikett.</span><span class="sxs-lookup"><span data-stu-id="f4d80-176">This field defines the number of rows that can be printed on each label.</span></span>

        > [!NOTE]
        > <span data-ttu-id="f4d80-177">Den här inställningen gör att en separat ZPL-etikett skrivs ut för varje post i tabellen med påfyllnadsetiketter.</span><span class="sxs-lookup"><span data-stu-id="f4d80-177">This setup will cause a separate ZPL label to be printed for each record in the wave labels table.</span></span>

1. <span data-ttu-id="f4d80-178">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f4d80-178">Close the page.</span></span>
1. <span data-ttu-id="f4d80-179">I åtgärdsfönstret väljer du **Redigera fråga**.</span><span class="sxs-lookup"><span data-stu-id="f4d80-179">On the Action Pane, select **Edit query**.</span></span>
1. <span data-ttu-id="f4d80-180">I frågeredigerarens dialogruta, på fliken **Intervall** lägg till en rad med följande värden:</span><span class="sxs-lookup"><span data-stu-id="f4d80-180">In the query editor dialog box, on the **Range** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="f4d80-181">**Tabell:** *Arbetsrader*</span><span class="sxs-lookup"><span data-stu-id="f4d80-181">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="f4d80-182">**Härlett register:** *Arbetsrader*</span><span class="sxs-lookup"><span data-stu-id="f4d80-182">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="f4d80-183">**Fält:** *arbetstyp*</span><span class="sxs-lookup"><span data-stu-id="f4d80-183">**Field:** *Work type*</span></span>
    - <span data-ttu-id="f4d80-184">**Kriterier:** *Plocka*</span><span class="sxs-lookup"><span data-stu-id="f4d80-184">**Criteria:** *Pick*</span></span>

    <span data-ttu-id="f4d80-185">Den här frågan ser till att endast arbetsrader av typen plockning skrivs ut på etiketten, inte artikelrader av typen radtyp.</span><span class="sxs-lookup"><span data-stu-id="f4d80-185">This query ensures that only pick-type work lines will be printed on the label, not put-type work lines.</span></span>

1. <span data-ttu-id="f4d80-186">Om du vill kunna skriva ut fraktsedels-ID väljer du på fliken **kopplingar**, sedan **arbetsrader** och kopplar tabellen **leveranser** till den.</span><span class="sxs-lookup"><span data-stu-id="f4d80-186">If you want to be able to print the bill of lading ID, on the **Joins** tab, select the **Work lines** table, and join the **Shipments** table to it.</span></span>
1. <span data-ttu-id="f4d80-187">Stäng dialogrutan frågeredigeraren.</span><span class="sxs-lookup"><span data-stu-id="f4d80-187">Close the query editor dialog box.</span></span>
1. <span data-ttu-id="f4d80-188">På snabbfliken **Layout för skrivartext** finns tre avsnitt där du kan skriva skrivarkod: **rubrikavsnitt**, **brödtext** och **sidfotsavsnitt**.</span><span class="sxs-lookup"><span data-stu-id="f4d80-188">The **Printer text Layout** FastTab has three sections where you can write printer code: **Header section**, **Body section**, and **Footer section**.</span></span> <span data-ttu-id="f4d80-189">I avsnittet **rubrikavsnitt** i fältet **etikettrubrik** anger du koden för önskad rubrik.</span><span class="sxs-lookup"><span data-stu-id="f4d80-189">In the **Header section** section, in the **Label header** field, enter code for the required header.</span></span> <span data-ttu-id="f4d80-190">Om du till exempel använder Zebra-skrivare kan du använda följande kod.</span><span class="sxs-lookup"><span data-stu-id="f4d80-190">For example, if you're using Zebra printers, you can use the following code.</span></span>

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

1. <span data-ttu-id="f4d80-191">I avsnittet **brödtext** i fältet **etikettext** anger du ZPL-koden för önskad text.</span><span class="sxs-lookup"><span data-stu-id="f4d80-191">In the **Body section** section, in the **Label body** field, enter ZPL code for the required body.</span></span> <span data-ttu-id="f4d80-192">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="f4d80-192">Here is an example.</span></span>

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

1. <span data-ttu-id="f4d80-193">I avsnittet **brödtext** i fältet **etikettsidfot** anger du ZPL-koden för önskad sidfot.</span><span class="sxs-lookup"><span data-stu-id="f4d80-193">In the **Body section** section, in the **Label footer** field, enter ZPL code for the required footer.</span></span> <span data-ttu-id="f4d80-194">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="f4d80-194">Here is an example.</span></span>

    ```plaintext
    ^PQ1^XZ
    ```

    > [!NOTE]
    > <span data-ttu-id="f4d80-195">Installationen kommer att skriva ut en kopia av varje etikett.</span><span class="sxs-lookup"><span data-stu-id="f4d80-195">This setup will print one copy of each label.</span></span> <span data-ttu-id="f4d80-196">Om du vill ha fler kopior (t.ex. en kopia för varje sida av lastpallen) anger du värdet **n** för avsnittet **\^PQn** i sidfoten till det antal kopior som krävs.</span><span class="sxs-lookup"><span data-stu-id="f4d80-196">If you require more copies (for example, one copy for each side of the pallet), set the **n** value for the **\^PQn** section in the footer to the required number of copies.</span></span> <span data-ttu-id="f4d80-197">Om du till exempel vill skriva ut fyra kopior av varje etikett anger du **\^PQ4**.</span><span class="sxs-lookup"><span data-stu-id="f4d80-197">For example, to print four copies of each label, specify **\^PQ4**.</span></span>

<span data-ttu-id="f4d80-198">Nu kan du använda din etikett.</span><span class="sxs-lookup"><span data-stu-id="f4d80-198">Your label is now ready to use.</span></span>

### <a name="create-a-wave-label-type"></a><span data-ttu-id="f4d80-199">Skapa en typ för påfyllnadsetiketten</span><span class="sxs-lookup"><span data-stu-id="f4d80-199">Create a wave label type</span></span>

<span data-ttu-id="f4d80-200">Påfyllnadsetikettyper används för att länka påfyllnadsetikettmallar till en enhet på enhetssekvensgrupprader.</span><span class="sxs-lookup"><span data-stu-id="f4d80-200">Wave label types are used to link wave label templates to a unit on unit sequence group lines.</span></span>

1. <span data-ttu-id="f4d80-201">Gå till **Lagerstyrning \> Inställningar \> Dokumentflöde \> Typer av påfyllnadsetikett**.</span><span class="sxs-lookup"><span data-stu-id="f4d80-201">Go to **Warehouse management \> Setup \> Document routing \> Wave label types**.</span></span>
1. <span data-ttu-id="f4d80-202">Lägg till en typ av påfyllnadsetikett med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="f4d80-202">Add a wave label type that has the following settings:</span></span>

    - <span data-ttu-id="f4d80-203">**Etikettyp:** *kartong*</span><span class="sxs-lookup"><span data-stu-id="f4d80-203">**Label type:** *Carton*</span></span>
    - <span data-ttu-id="f4d80-204">**Beskrivning:** *kartong*</span><span class="sxs-lookup"><span data-stu-id="f4d80-204">**Description:** *Carton*</span></span>

### <a name="set-up-unit-sequence-groups"></a><span data-ttu-id="f4d80-205">Konfigurera enhetssekvensgrupper</span><span class="sxs-lookup"><span data-stu-id="f4d80-205">Set up unit sequence groups</span></span>

<span data-ttu-id="f4d80-206">Ställ sedan in enhetsseriegruppen för typ av påfyllnadsnivå.</span><span class="sxs-lookup"><span data-stu-id="f4d80-206">Next, set up the unit sequence group for the wave label type.</span></span>

1. <span data-ttu-id="f4d80-207">Gå till **Lagerstyrning \> Inställningar \> Lagerställe \> Enhetsseriegrupp**.</span><span class="sxs-lookup"><span data-stu-id="f4d80-207">Go to **Warehouse management \> Setup \> Warehouse \> Unit sequence groups**.</span></span>
1. <span data-ttu-id="f4d80-208">Välj gruppen **Ea Box PL**.</span><span class="sxs-lookup"><span data-stu-id="f4d80-208">Select the **Ea Box PL** group.</span></span>
1. <span data-ttu-id="f4d80-209">För raden **ruta** ange fältet **typ av påfyllnadsnivå** till *kartong*.</span><span class="sxs-lookup"><span data-stu-id="f4d80-209">For the **Box** line, set the **Wave level type** field to *Carton*.</span></span>

### <a name="create-a-wave-label-template"></a><span data-ttu-id="f4d80-210">Skapa en mall för påfyllnadsetikett</span><span class="sxs-lookup"><span data-stu-id="f4d80-210">Create a wave label template</span></span>

<span data-ttu-id="f4d80-211">Skapa sedan mall för påfyllnadsetikett för typen av påfyllnadsetikett.</span><span class="sxs-lookup"><span data-stu-id="f4d80-211">Next, create the wave label template for the wave label type.</span></span>

1. <span data-ttu-id="f4d80-212">Gå till **Lagerstyrning \> Inställningar \> Dokumentflöde \> Mall för påfyllnadsetikett**.</span><span class="sxs-lookup"><span data-stu-id="f4d80-212">Go to **Warehouse management \> Setup \> Document routing \> Wave label templates**.</span></span>
1. <span data-ttu-id="f4d80-213">Lägg till en mall för påfyllnadsnivå och ange följande värden i rubriken:</span><span class="sxs-lookup"><span data-stu-id="f4d80-213">Add a wave level template, and set the following values in the header:</span></span>

    - <span data-ttu-id="f4d80-214">**Namn på etikettmallen:** *kartongetiketter*</span><span class="sxs-lookup"><span data-stu-id="f4d80-214">**Label template name:** *Carton labels*</span></span>
    - <span data-ttu-id="f4d80-215">**Beskrivning:** *kartongetiketter*</span><span class="sxs-lookup"><span data-stu-id="f4d80-215">**Description:** *Carton labels*</span></span>
    - <span data-ttu-id="f4d80-216">**Kod för påfyllnadssteg:** *PrintLabel*</span><span class="sxs-lookup"><span data-stu-id="f4d80-216">**Wave step code:** *PrintLabel*</span></span>
    - <span data-ttu-id="f4d80-217">**Lagerställe:** *62*</span><span class="sxs-lookup"><span data-stu-id="f4d80-217">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="f4d80-218">På snabbfliken **Allmänt** ställer du in fältet **typ av påfyllnadsetikett** till *kartong*.</span><span class="sxs-lookup"><span data-stu-id="f4d80-218">On the **General** FastTab, set the **Wave label type** field to *Carton*.</span></span>
1. <span data-ttu-id="f4d80-219">På snabbfliken **information om påfyllnadsetikettens mall** och lägg till en ny rad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="f4d80-219">On the **Wave label template details** FastTab, add a new row that has the following settings:</span></span>

    - <span data-ttu-id="f4d80-220">**Etikettlayout-ID:** *kartong*</span><span class="sxs-lookup"><span data-stu-id="f4d80-220">**Label layout ID:** *Carton*</span></span>
    - <span data-ttu-id="f4d80-221">**Skrivarnamn:** Välj en lämplig ZPL-skrivare.</span><span class="sxs-lookup"><span data-stu-id="f4d80-221">**Printer name:** Select an appropriate ZPL printer.</span></span>
    - <span data-ttu-id="f4d80-222">**Kör fråga:** *Ja* (den här inställningen är valfri, men rekommenderas för optimal prestanda.)</span><span class="sxs-lookup"><span data-stu-id="f4d80-222">**Run query:** *Yes* (This setting is optional, but it's recommended for optimal performance.)</span></span>

1. <span data-ttu-id="f4d80-223">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="f4d80-223">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="f4d80-224">Valfritt: om du ställer in en kundspecifik etikettdesign måste du skapa en fråga för att hitta kundens konto.</span><span class="sxs-lookup"><span data-stu-id="f4d80-224">Optional: If you're setting up a customer-specific label design, you must create a query to find the customer's account.</span></span> <span data-ttu-id="f4d80-225">På snabbfliken **information om påfyllnadsetikettens mall** välj **Redigera fråga**.</span><span class="sxs-lookup"><span data-stu-id="f4d80-225">On the **Wave label template details** FastTab, select **Edit query**.</span></span> <span data-ttu-id="f4d80-226">I frågeredigerarens dialogruta, på fliken **Intervall** lägg till en rad med följande värden:</span><span class="sxs-lookup"><span data-stu-id="f4d80-226">Then, in the query editor dialog box, on the **Range** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="f4d80-227">**Register:** *försändelser*</span><span class="sxs-lookup"><span data-stu-id="f4d80-227">**Table:** *Shipments*</span></span>
    - <span data-ttu-id="f4d80-228">**Härlett register:** *försändelser*</span><span class="sxs-lookup"><span data-stu-id="f4d80-228">**Derived table:** *Shipments*</span></span>
    - <span data-ttu-id="f4d80-229">**Fält:** *Kontonummer*</span><span class="sxs-lookup"><span data-stu-id="f4d80-229">**Field:** *Account number*</span></span>
    - <span data-ttu-id="f4d80-230">**Kriterier:** Ange relevant kundkontonummer.</span><span class="sxs-lookup"><span data-stu-id="f4d80-230">**Criteria:** Enter the relevant customer account number.</span></span>

    <span data-ttu-id="f4d80-231">När du är klar klickar du på **OK** för att stänga dialogrutan för frågeredigeraren.</span><span class="sxs-lookup"><span data-stu-id="f4d80-231">When you've finished, select **OK** to close the query editor dialog box.</span></span>

1. <span data-ttu-id="f4d80-232">I åtgärdsfönstret, välj **Redigera fråga** för att öppna en dialogruta för frågeredigeraren för hela etikettmallen.</span><span class="sxs-lookup"><span data-stu-id="f4d80-232">On the Action Pane, select **Edit query** to open the query editor dialog box for the whole label template.</span></span>
1. <span data-ttu-id="f4d80-233">I frågeredigerarens dialogruta, på fliken **Sortera** lägg till en rad med följande värden:</span><span class="sxs-lookup"><span data-stu-id="f4d80-233">In the query editor dialog box, on the **Sorting** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="f4d80-234">**Tabell:** *Arbetsrader*</span><span class="sxs-lookup"><span data-stu-id="f4d80-234">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="f4d80-235">**Härlett register:** *Arbetsrader*</span><span class="sxs-lookup"><span data-stu-id="f4d80-235">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="f4d80-236">**Fält:** *referens till läs in rad-ID (post-ID)*</span><span class="sxs-lookup"><span data-stu-id="f4d80-236">**Field:** *Reference load line id (Record-ID)*</span></span>
    - <span data-ttu-id="f4d80-237">**Sökriktning:** *Stigande*</span><span class="sxs-lookup"><span data-stu-id="f4d80-237">**Search direction:** *Ascending*</span></span>

1. <span data-ttu-id="f4d80-238">Stäng dialogrutan för frågeredigeraren genom att välja **OK**.</span><span class="sxs-lookup"><span data-stu-id="f4d80-238">Select **OK** to close the query editor dialog box.</span></span>
1. <span data-ttu-id="f4d80-239">En meddelande ruta ber dig bekräfta åtgärden grupperingsåterställning.</span><span class="sxs-lookup"><span data-stu-id="f4d80-239">A message box prompts you to confirm the grouping reset operation.</span></span> <span data-ttu-id="f4d80-240">Klicka på **Ja** när du vill fortsätta.</span><span class="sxs-lookup"><span data-stu-id="f4d80-240">Select **Yes** to continue.</span></span>
1. <span data-ttu-id="f4d80-241">I åtgärdsfönstret, välj **mallgruppen för påfyllnadsetikett**.</span><span class="sxs-lookup"><span data-stu-id="f4d80-241">On the Action Pane, select **Wave label template group**.</span></span>
1. <span data-ttu-id="f4d80-242">I dialogrutan **mallgruppen för påfyllnadsetikett** välj raden där fältet **referensfältnamn** anges till *referens till läs in rad-ID* och markerar sedan kryssrutan **etikettversions-ID** för den här raden.</span><span class="sxs-lookup"><span data-stu-id="f4d80-242">In the **Wave label template group** dialog box, select the row where the **Reference field name** field is set to *Reference load line id*, and then select the **Label build ID** check box for this row.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f4d80-243">Med den här inställningen skapas en etikettserie ("kartong 1 av X") per lastrad i hela påfyllnaden, oavsett inställningen för arbetsgrupperingen.</span><span class="sxs-lookup"><span data-stu-id="f4d80-243">This setup will create one label sequence ("Carton 1 of X") per load line throughout the wave, regardless of the work grouping setup.</span></span> <span data-ttu-id="f4d80-244">Denna etikettserie kan skrivas ut på etikettlayouten.</span><span class="sxs-lookup"><span data-stu-id="f4d80-244">This label sequence can be printed on the label layout.</span></span>

### <a name="configure-number-sequence-extensions"></a><span data-ttu-id="f4d80-245">Konfigurera nummerserietillägg</span><span class="sxs-lookup"><span data-stu-id="f4d80-245">Configure number sequence extensions</span></span>

<span data-ttu-id="f4d80-246">Nummerserietillägg styr GS1 efterlevnaden av specifika nummerserier.</span><span class="sxs-lookup"><span data-stu-id="f4d80-246">Number sequence extensions control the GS1 compliance of specific number sequences.</span></span> <span data-ttu-id="f4d80-247">Den här konfigurationen är valfri för det aktuella scenariot.</span><span class="sxs-lookup"><span data-stu-id="f4d80-247">This configuration is optional for the current scenario.</span></span> <span data-ttu-id="f4d80-248">Mer information och instruktioner för konfigurering finns i [Konfigurera tillägg för nummerserier](../warehousing/configure-number-sequence-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="f4d80-248">For more information and configuration instructions, see [Configure number sequence extensions](../warehousing/configure-number-sequence-extensions.md).</span></span>

### <a name="create-a-sales-order-and-release-it-to-the-warehouse"></a><span data-ttu-id="f4d80-249">Skapa en försäljningsorder och släpp den på lagerstället</span><span class="sxs-lookup"><span data-stu-id="f4d80-249">Create a sales order and release it to the warehouse</span></span>

1. <span data-ttu-id="f4d80-250">Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="f4d80-250">Go to **Sales and marketing \> Sales order \> All sales orders**.</span></span>
1. <span data-ttu-id="f4d80-251">Skapa en försäljningsorder med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="f4d80-251">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="f4d80-252">**Kundkonto:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="f4d80-252">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="f4d80-253">**Lagerställe:** *62*</span><span class="sxs-lookup"><span data-stu-id="f4d80-253">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="f4d80-254">Lägg till två försäljningsorderrader med följande inställning:</span><span class="sxs-lookup"><span data-stu-id="f4d80-254">Add two sales order lines that have the following settings:</span></span>

    - <span data-ttu-id="f4d80-255">Försäljningsorderrad 1:</span><span class="sxs-lookup"><span data-stu-id="f4d80-255">Sales order line 1:</span></span>

        - <span data-ttu-id="f4d80-256">**Artikelnummer:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="f4d80-256">**Item number:** *A0001*</span></span>
        - <span data-ttu-id="f4d80-257">**Kvantitet:** *9024*</span><span class="sxs-lookup"><span data-stu-id="f4d80-257">**Quantity:** *9024*</span></span>
        - <span data-ttu-id="f4d80-258">**Enhet:** *ea* (9024 ea = 376 låda = 47 PL)</span><span class="sxs-lookup"><span data-stu-id="f4d80-258">**Unit:** *ea* (9024 ea = 376 Box = 47 PL)</span></span>

    - <span data-ttu-id="f4d80-259">Försäljningsorderrad 2:</span><span class="sxs-lookup"><span data-stu-id="f4d80-259">Sales order line 2:</span></span>

        - <span data-ttu-id="f4d80-260">**Artikelnummer:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="f4d80-260">**Item number:** *A0002*</span></span>
        - <span data-ttu-id="f4d80-261">**Kvantitet:** *9016*</span><span class="sxs-lookup"><span data-stu-id="f4d80-261">**Quantity:** *9016*</span></span>
        - <span data-ttu-id="f4d80-262">**Enhet:** *ea* (9016 ea = 322 box = 46 PL)</span><span class="sxs-lookup"><span data-stu-id="f4d80-262">**Unit:** *ea* (9016 ea = 322 Box = 46 PL)</span></span>

    > [!NOTE]
    > <span data-ttu-id="f4d80-263">Artiklarna och kvantiteterna som anges här är endast exempel.</span><span class="sxs-lookup"><span data-stu-id="f4d80-263">The items and quantities that are provided here are only examples.</span></span> <span data-ttu-id="f4d80-264">De måste använda den enhetsseriegrupp som du definierade tidigare, och lämpliga enhetskonverteringar från *ea* till *Box* till *PL* måste definieras för dem och de måste ha lager i lagerställe *62*.</span><span class="sxs-lookup"><span data-stu-id="f4d80-264">They must use the unit sequence group that you defined earlier, appropriate unit conversions from *ea* to *Box* to *PL* must be defined for them, and they must have stock in warehouse *62*.</span></span> <span data-ttu-id="f4d80-265">Mer information finns i [måttenhet och lagerprinciper](unit-measure-stocking-policies.md).</span><span class="sxs-lookup"><span data-stu-id="f4d80-265">For more information, see [Unit of measure and stocking policies](unit-measure-stocking-policies.md).</span></span>

1. <span data-ttu-id="f4d80-266">Välj försäljningsorderrad 1.</span><span class="sxs-lookup"><span data-stu-id="f4d80-266">Select sales order line 1.</span></span> <span data-ttu-id="f4d80-267">I avsnittet **Försäljningsorderrad** i menyn **Lager** välj **Reservationer**.</span><span class="sxs-lookup"><span data-stu-id="f4d80-267">Then, in the **Sales order line** section, on the **Inventory** menu, select **Reservations**.</span></span>
1. <span data-ttu-id="f4d80-268">På sidan **Reservation** i åtgärdsfönstret, välj **Reservera parti** och stäng sedan sidan.</span><span class="sxs-lookup"><span data-stu-id="f4d80-268">On the **Reservation** page, on the Action Pane, select **Reserve lot**, and then close the page.</span></span>
1. <span data-ttu-id="f4d80-269">Upprepa steg 4 och 5 för försäljningsorderrad 2.</span><span class="sxs-lookup"><span data-stu-id="f4d80-269">Repeat steps 4 and 5 for sales order line 2.</span></span>
1. <span data-ttu-id="f4d80-270">I åtgärdsfönstret på fliken **Lagerställe** välj **Frisläpp till regel för lagerställe**.</span><span class="sxs-lookup"><span data-stu-id="f4d80-270">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="f4d80-271">Då inträffar följande händelser:</span><span class="sxs-lookup"><span data-stu-id="f4d80-271">The following events occur:</span></span>

    - <span data-ttu-id="f4d80-272">I systemet bearbetas den skapade utleveransen med hjälp av mallen som inkluderar utskriftssteget för etikett.</span><span class="sxs-lookup"><span data-stu-id="f4d80-272">The system processes the created shipment by using the template that includes the label printing step.</span></span> <span data-ttu-id="f4d80-273">Etikettlayouten används för att definiera etikettens format, och resultatet blir en etikett som skrivs ut på den skrivare som väljs i etikettmallen.</span><span class="sxs-lookup"><span data-stu-id="f4d80-273">The label layout will be used to define the format of the label, and the result will be a label that is printed on the printer that is selected in the label template.</span></span>
    - <span data-ttu-id="f4d80-274">Påfyllnadsetiketter genereras och skrivs ut.</span><span class="sxs-lookup"><span data-stu-id="f4d80-274">Wave labels are generated and printed.</span></span> <span data-ttu-id="f4d80-275">Antalet etiketter är lika med antalet kartonger (i det här exemplet är 376 boxetiketter för rad 1 och 322 boxetiketter för rad 2).</span><span class="sxs-lookup"><span data-stu-id="f4d80-275">The number of labels will equal the number of cartons (in this example, 376 Box labels for line 1 and 322 Box labels for line 2).</span></span>
    - <span data-ttu-id="f4d80-276">Ett nytt fraktsedels-ID genereras för leveranserna.</span><span class="sxs-lookup"><span data-stu-id="f4d80-276">A new bill of lading ID is generated for the shipments.</span></span> <span data-ttu-id="f4d80-277">Om du har konfigurerat nummerserietilläggen följer påfyllnadsetikett-ID nummerformatet **SSCC-18**.</span><span class="sxs-lookup"><span data-stu-id="f4d80-277">If you configured the number sequence extensions, the wave label IDs will follow the **SSCC-18** number format.</span></span> 

<span data-ttu-id="f4d80-278">Du kan visa och skriva ut påfyllnadsetiketter på följande sidor.</span><span class="sxs-lookup"><span data-stu-id="f4d80-278">You can view and reprint wave labels from the following pages.</span></span> <span data-ttu-id="f4d80-279">I åtgärdsfönstret, på varje sida, på fliken **Leveranser**, i gruppen **Relaterad information**, väljer du **påfyllnadsetiketter**.</span><span class="sxs-lookup"><span data-stu-id="f4d80-279">On the Action Pane of each page, on the **Shipments** tab, in the **Related information** group, select **Wave labels**.</span></span>

- <span data-ttu-id="f4d80-280">Alla leveranser \> leveransinformation</span><span class="sxs-lookup"><span data-stu-id="f4d80-280">All shipments \> Shipment details</span></span>
- <span data-ttu-id="f4d80-281">Alla laster \> Läs in information</span><span class="sxs-lookup"><span data-stu-id="f4d80-281">All loads \> Load details</span></span>
- <span data-ttu-id="f4d80-282">Alla påfyllnader</span><span class="sxs-lookup"><span data-stu-id="f4d80-282">All waves</span></span>
- <span data-ttu-id="f4d80-283">Påfyllnadsetiketter</span><span class="sxs-lookup"><span data-stu-id="f4d80-283">Wave labels</span></span>
- <span data-ttu-id="f4d80-284">Etiketthistorik för påfyllnad</span><span class="sxs-lookup"><span data-stu-id="f4d80-284">Wave label history</span></span>

## <a name="scenario-2-wave-label-printing-for-containerization-without-wave-label-records"></a><span data-ttu-id="f4d80-285">Scenario 2: påfyllnadsetikett utskrift för skapande av behållare (utan påfyllnadsetikettposter)</span><span class="sxs-lookup"><span data-stu-id="f4d80-285">Scenario 2: Wave label printing for containerization (without wave label records)</span></span>

<span data-ttu-id="f4d80-286">I det här scenariot kan du skriva ut påfyllnadsetiketter när du använder skapande av behållare för att automatiskt dela upp objekt i kartonger och därför inte kräva en påfyllnadsetikettpost.</span><span class="sxs-lookup"><span data-stu-id="f4d80-286">This scenario lets you print wave labels when you use containerization to automatically split items into cartons and therefore don't require a wave label record.</span></span> <span data-ttu-id="f4d80-287">I det här fallet fungerar behållar-ID som platshållare för SSCC.</span><span class="sxs-lookup"><span data-stu-id="f4d80-287">In this case, the container ID acts as a placeholder for the SSCC.</span></span>

<span data-ttu-id="f4d80-288">Här är de viktigaste skillnaderna mellan det här scenariot och scenario 1:</span><span class="sxs-lookup"><span data-stu-id="f4d80-288">Here are the main differences between this scenario and scenario 1:</span></span>

- <span data-ttu-id="f4d80-289">**Mallar för påfyllnadsetiketter:** du väljer ingen typ av påfyllnadsetikett i mallen för påfyllnadsetiketter och du behöver inte använda en gruppering för att skapa etiketter.</span><span class="sxs-lookup"><span data-stu-id="f4d80-289">**Wave label templates:** You won't select a wave label type on the wave label template, and you won't require a label build grouping.</span></span> <span data-ttu-id="f4d80-290">Annars kan du konfigurera mallen för påfyllnadsetikett och länka till påfyllnadsmallen på samma sätt som beskrivs i scenario 1.</span><span class="sxs-lookup"><span data-stu-id="f4d80-290">Otherwise, you will configure the wave label template and link to the wave template in the same way that is described in scenario 1.</span></span> <span data-ttu-id="f4d80-291">Du måste lämna typ av påfyllnadsetikett tom om du vill förhindra att påfyllnadsetiketter genereras.</span><span class="sxs-lookup"><span data-stu-id="f4d80-291">You must leave the wave label type blank to prevent wave labels from being generated.</span></span>
- <span data-ttu-id="f4d80-292">**Layout för påfyllnadsetiketter:** du kan konfigurera radinställningarna för layouten för påfyllnadsetiketter för arbetsrader i stället för påfyllnadsetikettposter.</span><span class="sxs-lookup"><span data-stu-id="f4d80-292">**Wave label layouts:** You will configure the wave label layout row settings for work lines instead of wave label records.</span></span> <span data-ttu-id="f4d80-293">Du måste konfigurera radinställningen för etikettlayout med hjälp av registret **WHSWorkLine** i stället för registret **WHSWaveLabel**.</span><span class="sxs-lookup"><span data-stu-id="f4d80-293">You must configure the row setting for the label layout by using the **WHSWorkLine** table instead of the **WHSWaveLabel** table.</span></span> <span data-ttu-id="f4d80-294">Inställningen **rader per sida** styr antalet rader som brödtextavsnittet ska ha.</span><span class="sxs-lookup"><span data-stu-id="f4d80-294">The **Rows per page** setting controls the number of rows that the body section will have.</span></span> 

<span data-ttu-id="f4d80-295">Den här konfigurationen är också lämplig för affärsscenarier där flera olika artiklar förpackas i en etikettruta eller till en lastpall, och denna förpackningsprocess kan definieras genom att arbetet skapas (t.ex. arbete som grupperats per leverans).</span><span class="sxs-lookup"><span data-stu-id="f4d80-295">This configuration is also suitable for business scenarios where multiple different items are packed into one labeled box or into a pallet, and this packing process can be defined by work creation (for example, work that is grouped by shipment).</span></span>

<span data-ttu-id="f4d80-296">Det här scenariot visar komplett flöde.</span><span class="sxs-lookup"><span data-stu-id="f4d80-296">This scenario shows the end-to-end flow.</span></span>

### <a name="make-demo-data-available"></a><span data-ttu-id="f4d80-297">Gör demodata tillgängliga</span><span class="sxs-lookup"><span data-stu-id="f4d80-297">Make demo data available</span></span>

<span data-ttu-id="f4d80-298">För att följa detta scenario måste du ha demonstrationsdata installerad och du måste välja juridiska personen **USMF**.</span><span class="sxs-lookup"><span data-stu-id="f4d80-298">To follow this scenario, you must have demo data installed, and you must select the **USMF** legal entity.</span></span>

### <a name="make-sure-that-the-wave-label-method-is-available"></a><span data-ttu-id="f4d80-299">Kontrollera att påfyllnadsetikett metoden är tillgänglig</span><span class="sxs-lookup"><span data-stu-id="f4d80-299">Make sure that the wave label method is available</span></span>

<span data-ttu-id="f4d80-300">Du måste kanske återskapa dina metoder för påfyllnadsprocess för att göra påfyllnadsetikett metoden tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="f4d80-300">You might have to regenerate the wave process methods to make the wave label printing method available.</span></span>

1. <span data-ttu-id="f4d80-301">Gå till **Lagerstyrning \> Inställningar \> Påfyllnader \> Metoder för påfyllnadsprocess**.</span><span class="sxs-lookup"><span data-stu-id="f4d80-301">Go to **Warehouse management \> Setup \> Waves \> Wave process methods**.</span></span>
1. <span data-ttu-id="f4d80-302">Kontrollera att **waveLabelPrinting** finns i listan.</span><span class="sxs-lookup"><span data-stu-id="f4d80-302">Confirm that **waveLabelPrinting** is in the list.</span></span> <span data-ttu-id="f4d80-303">Om den inte finns med väljer du **återskapa metoder** i åtgärdsfönstret för att lägga till den.</span><span class="sxs-lookup"><span data-stu-id="f4d80-303">If it isn't, select **Regenerate methods** on the Action Pane to add it.</span></span>

### <a name="set-up-a-wave-template"></a><span data-ttu-id="f4d80-304">Ställa in en påfyllnadsmall</span><span class="sxs-lookup"><span data-stu-id="f4d80-304">Set up a wave template</span></span>

<span data-ttu-id="f4d80-305">Med påfyllnadsmallar kan du länka specifika förekomster av påfyllnadsmetoder till en motsvarande påfyllnadsetikettsmall.</span><span class="sxs-lookup"><span data-stu-id="f4d80-305">Wave templates let you link specific instances of wave methods to a corresponding wave label template.</span></span>

1. <span data-ttu-id="f4d80-306">Gå till **Lagerstyrning \> Inställningar \> Påfyllnader \> Påfyllnadsmallar**.</span><span class="sxs-lookup"><span data-stu-id="f4d80-306">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
1. <span data-ttu-id="f4d80-307">Välj en mall som **63 skapande av behållare**.</span><span class="sxs-lookup"><span data-stu-id="f4d80-307">Select a template, such as **63 Containerization**.</span></span>
1. <span data-ttu-id="f4d80-308">På snabbfliken **metoder** flyttar du metoden **utskrift av påfyllnadsetiketter** till kolumnen **valda metoder**.</span><span class="sxs-lookup"><span data-stu-id="f4d80-308">On the **Methods** FastTab, move the **Wave label printing** method to the **Selected methods** column.</span></span>
1. <span data-ttu-id="f4d80-309">I kolumnen **Valda metoder** välj metoden **Utskrift av påfyllnadsetiketter** och ange dess fält **Kod för påfyllnadssteg** till *PrintLabel*.</span><span class="sxs-lookup"><span data-stu-id="f4d80-309">In the **Selected methods** column, select the **Wave label printing** method, and set its **Wave step code** field to *PrintLabel*.</span></span> <span data-ttu-id="f4d80-310">För mer information om koder för påfyllnadssteg, se [Koder för påfyllnadssteg](wave-step-codes.md).</span><span class="sxs-lookup"><span data-stu-id="f4d80-310">For more information about wave step codes, see [Wave step codes](wave-step-codes.md).</span></span>

### <a name="create-a-wave-label-layout"></a><span data-ttu-id="f4d80-311">Skapa en layout för påfyllnadsetiketten</span><span class="sxs-lookup"><span data-stu-id="f4d80-311">Create a wave label layout</span></span>

1. <span data-ttu-id="f4d80-312">Gå till **Lagerstyrning \> Inställningar \> Dokumentflöde \> Layout för påfyllnadsetikett**.</span><span class="sxs-lookup"><span data-stu-id="f4d80-312">Go to **Warehouse management \> Setup \> Document routing \> Wave label layouts**.</span></span>
1. <span data-ttu-id="f4d80-313">Skapa en post med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="f4d80-313">Create a record that has the following settings:</span></span>

    - <span data-ttu-id="f4d80-314">**Etikettlayout-ID:** *kartong*</span><span class="sxs-lookup"><span data-stu-id="f4d80-314">**Label layout ID:** *Carton*</span></span>
    - <span data-ttu-id="f4d80-315">**Beskrivning:** *kartong (SSCC)*</span><span class="sxs-lookup"><span data-stu-id="f4d80-315">**Description:** *Carton (SSCC)*</span></span>

1. <span data-ttu-id="f4d80-316">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="f4d80-316">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="f4d80-317">I åtgärdsfönstret, välj **Inställningar för påfyllnadsetikettrad**.</span><span class="sxs-lookup"><span data-stu-id="f4d80-317">On the Action Pane, select **Wave label row settings**.</span></span>

    <span data-ttu-id="f4d80-318">Sidan **Inställningar för påfyllnadsetikettrad** visas.</span><span class="sxs-lookup"><span data-stu-id="f4d80-318">The **Wave label row settings** page appears.</span></span> <span data-ttu-id="f4d80-319">Här kan du konfigurera den dynamiska delen av etiketten.</span><span class="sxs-lookup"><span data-stu-id="f4d80-319">Here, you can configure the dynamic part of the label.</span></span>

1. <span data-ttu-id="f4d80-320">Lägg till en rad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="f4d80-320">Add a row that has the following settings:</span></span>

    - <span data-ttu-id="f4d80-321">**Rad-ID:** *WorkLine*</span><span class="sxs-lookup"><span data-stu-id="f4d80-321">**Row Id:** *WorkLine*</span></span>
    - <span data-ttu-id="f4d80-322">**Radtabellnamn:** *WHSWorkLine*</span><span class="sxs-lookup"><span data-stu-id="f4d80-322">**Row table name:** *WHSWorkLine*</span></span>
    - <span data-ttu-id="f4d80-323">**Radens startposition:** *500*</span><span class="sxs-lookup"><span data-stu-id="f4d80-323">**Row start position:** *500*</span></span>

        <span data-ttu-id="f4d80-324">I det här fältet definieras den lodräta position där raden ska börja etiketten.</span><span class="sxs-lookup"><span data-stu-id="f4d80-324">This field defines the vertical position where the row will begin on the label.</span></span>

    - <span data-ttu-id="f4d80-325">**Radhöjd:** *-50*</span><span class="sxs-lookup"><span data-stu-id="f4d80-325">**Row height:** *-50*</span></span>

        <span data-ttu-id="f4d80-326">I det här fältet definieras höjden på varje rad.</span><span class="sxs-lookup"><span data-stu-id="f4d80-326">This field defines the height of each row.</span></span> <span data-ttu-id="f4d80-327">Radhöjden är positiv för vågräta etiketter och är negativ för lodräta etiketter.</span><span class="sxs-lookup"><span data-stu-id="f4d80-327">The row height is positive for horizontal labels and negative for vertical labels.</span></span>

    - <span data-ttu-id="f4d80-328">**Rader per sida:** *5*</span><span class="sxs-lookup"><span data-stu-id="f4d80-328">**Rows per page:** *5*</span></span>

        <span data-ttu-id="f4d80-329">I det här fältet definieras antalet rader som kan skrivas ut på varje etikett.</span><span class="sxs-lookup"><span data-stu-id="f4d80-329">This field defines the number of rows that can be printed on each label.</span></span>

        > [!NOTE]
        > <span data-ttu-id="f4d80-330">Denna inställning kommer att skriva ut flera ZPL-etiketter per arbete, där varje sida kan innehålla upp till fem arbetsrader.</span><span class="sxs-lookup"><span data-stu-id="f4d80-330">This setup will print several ZPL labels per work, where each page can hold up to five work lines.</span></span> <span data-ttu-id="f4d80-331">Om en etikett till exempel skrivs ut för en behållare med 12 rader skrivs tre etiketter ut.</span><span class="sxs-lookup"><span data-stu-id="f4d80-331">For example, if a label is printed for a container that has 12 lines, three labels will be printed.</span></span> <span data-ttu-id="f4d80-332">Om du vill skriva ut en separat etikett för varje plockningsrad anger du det här värdet till *1*.</span><span class="sxs-lookup"><span data-stu-id="f4d80-332">If you want to print a separate label for each pick line, set this value to *1*.</span></span>

1. <span data-ttu-id="f4d80-333">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f4d80-333">Close the page.</span></span>
1. <span data-ttu-id="f4d80-334">I åtgärdsfönstret väljer du **Redigera fråga**.</span><span class="sxs-lookup"><span data-stu-id="f4d80-334">On the Action Pane, select **Edit query**.</span></span>
1. <span data-ttu-id="f4d80-335">I frågeredigerarens dialogruta, på fliken **Intervall** lägg till en rad med följande värden:</span><span class="sxs-lookup"><span data-stu-id="f4d80-335">In the query editor dialog box, on the **Range** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="f4d80-336">**Tabell:** *Arbetsrader*</span><span class="sxs-lookup"><span data-stu-id="f4d80-336">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="f4d80-337">**Härlett register:** *Arbetsrader*</span><span class="sxs-lookup"><span data-stu-id="f4d80-337">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="f4d80-338">**Fält:** *arbetstyp*</span><span class="sxs-lookup"><span data-stu-id="f4d80-338">**Field:** *Work type*</span></span>
    - <span data-ttu-id="f4d80-339">**Kriterier:** *Plocka*</span><span class="sxs-lookup"><span data-stu-id="f4d80-339">**Criteria:** *Pick*</span></span>

1. <span data-ttu-id="f4d80-340">Om du vill kunna skriva ut fraktsedels-ID väljer du på fliken **kopplingar**, sedan **arbetsrader** och kopplar tabellen **leveranser** till den.</span><span class="sxs-lookup"><span data-stu-id="f4d80-340">If you want to be able to print the bill of lading ID, on the **Joins** tab, select the **Work lines** table, and join the **Shipments** table to it.</span></span>
1. <span data-ttu-id="f4d80-341">Stäng dialogrutan frågeredigeraren.</span><span class="sxs-lookup"><span data-stu-id="f4d80-341">Close the query editor dialog box.</span></span>
1. <span data-ttu-id="f4d80-342">På snabbfliken **Layout för skrivartext** finns tre avsnitt där du kan skriva skrivarkod: **rubrikavsnitt**, **brödtext** och **sidfotsavsnitt**.</span><span class="sxs-lookup"><span data-stu-id="f4d80-342">The **Printer text Layout** FastTab has three sections where you can write printer code: **Header section**, **Body section**, and **Footer section**.</span></span> <span data-ttu-id="f4d80-343">I avsnittet **rubrikavsnitt** i fältet **etikettrubrik** anger du koden för önskad rubrik.</span><span class="sxs-lookup"><span data-stu-id="f4d80-343">In the **Header section** section, in the **Label header** field, enter code for the required header.</span></span> <span data-ttu-id="f4d80-344">Om du till exempel använder Zebra-skrivare kan du använda följande kod.</span><span class="sxs-lookup"><span data-stu-id="f4d80-344">For example, if you're using Zebra printers, you can use the following code.</span></span>

    ```plaintext
    CT~~CD,~CC^~CT~
    ^XA
    ^LH10,10
    ^FO0,0 ^AT ^FD$WHSWorkTable.ContainerId$ ^FS
    ^FO0,75 ^AT ^FD$WHSWorkLine.ShipmentId$ ^FS
    ^FO0,150 ^AT ^FD$WHSShipmentTable.BillOfLadingId$ ^FS
    ```

1. <span data-ttu-id="f4d80-345">I avsnittet **brödtext** i fältet **etikettext** anger du ZPL-koden för önskad text.</span><span class="sxs-lookup"><span data-stu-id="f4d80-345">In the **Body section** section, in the **Label body** field, enter ZPL code for the required body.</span></span> <span data-ttu-id="f4d80-346">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="f4d80-346">Here is an example.</span></span>

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

1. <span data-ttu-id="f4d80-347">I avsnittet **brödtext** i fältet **etikettsidfot** anger du ZPL-koden för önskad sidfot.</span><span class="sxs-lookup"><span data-stu-id="f4d80-347">In the **Body section** section, in the **Label footer** field, enter ZPL code for the required footer.</span></span> <span data-ttu-id="f4d80-348">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="f4d80-348">Here is an example.</span></span>

    ```plaintext
    ^PQ1^XZ
    ```

    > [!NOTE]
    > <span data-ttu-id="f4d80-349">Installationen kommer att skriva ut en kopia av varje etikett.</span><span class="sxs-lookup"><span data-stu-id="f4d80-349">This setup will print one copy of each label.</span></span> <span data-ttu-id="f4d80-350">Om du vill ha fler kopior (t.ex. en kopia för varje sida av lastpallen) anger du värdet **n** för avsnittet **\^PQn** i sidfoten till det antal kopior som krävs.</span><span class="sxs-lookup"><span data-stu-id="f4d80-350">If you require more copies (for example, one copy for each side of the pallet), set the **n** value for the **\^PQn** section in the footer to the required number of copies.</span></span> <span data-ttu-id="f4d80-351">Om du till exempel vill skriva ut fyra kopior av varje etikett anger du **\^PQ4**.</span><span class="sxs-lookup"><span data-stu-id="f4d80-351">For example, to print four copies of each label, specify **\^PQ4**.</span></span>

<span data-ttu-id="f4d80-352">Nu kan du använda din etikett.</span><span class="sxs-lookup"><span data-stu-id="f4d80-352">Your label is now ready to use.</span></span>

### <a name="create-a-wave-label-template"></a><span data-ttu-id="f4d80-353">Skapa en mall för påfyllnadsetikett</span><span class="sxs-lookup"><span data-stu-id="f4d80-353">Create a wave label template</span></span>

1. <span data-ttu-id="f4d80-354">Gå till **Lagerstyrning \> Inställningar \> Dokumentflöde \> Mall för påfyllnadsetikett**.</span><span class="sxs-lookup"><span data-stu-id="f4d80-354">Go to **Warehouse management \> Setup \> Document routing \> Wave label templates**.</span></span>
1. <span data-ttu-id="f4d80-355">Lägg till en mall för påfyllnadsnivå och ange följande värden i rubriken:</span><span class="sxs-lookup"><span data-stu-id="f4d80-355">Add a wave level template, and set the following values in the header:</span></span>

    - <span data-ttu-id="f4d80-356">**Namn på etikettmallen:** *behållaretiketter*</span><span class="sxs-lookup"><span data-stu-id="f4d80-356">**Label template name:** *Container labels*</span></span>
    - <span data-ttu-id="f4d80-357">**Beskrivning:** *behållaretiketter*</span><span class="sxs-lookup"><span data-stu-id="f4d80-357">**Description:** *Container labels*</span></span>
    - <span data-ttu-id="f4d80-358">**Kod för påfyllnadssteg:** *PrintLabel*</span><span class="sxs-lookup"><span data-stu-id="f4d80-358">**Wave step code:** *PrintLabel*</span></span>
    - <span data-ttu-id="f4d80-359">**Lagerställe:** *63*</span><span class="sxs-lookup"><span data-stu-id="f4d80-359">**Warehouse:** *63*</span></span>

1. <span data-ttu-id="f4d80-360">På snabbfliken **information om påfyllnadsetikettens mall** och lägg till en rad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="f4d80-360">On the **Wave label template details** FastTab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="f4d80-361">**Etikettlayout-ID:** *behållare*</span><span class="sxs-lookup"><span data-stu-id="f4d80-361">**Label layout ID:** *Container*</span></span>
    - <span data-ttu-id="f4d80-362">**Skrivarnamn:** Välj en lämplig ZPL-skrivare.</span><span class="sxs-lookup"><span data-stu-id="f4d80-362">**Printer name:** Select an appropriate ZPL printer.</span></span>
    - <span data-ttu-id="f4d80-363">**Kör fråga:** *Ja* (den här inställningen är valfri, men rekommenderas för optimal prestanda.)</span><span class="sxs-lookup"><span data-stu-id="f4d80-363">**Run query:** *Yes* (This setting is optional, but it's recommended for optimal performance.)</span></span>

1. <span data-ttu-id="f4d80-364">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="f4d80-364">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="f4d80-365">Valfritt: om du ställer in en kundspecifik etikettdesign måste du skapa en fråga för att hitta kundens konto.</span><span class="sxs-lookup"><span data-stu-id="f4d80-365">Optional: If you're setting up a customer-specific label design, you must create a query to find the customer's account.</span></span> <span data-ttu-id="f4d80-366">På snabbfliken **information om påfyllnadsetikettens mall** välj **Redigera fråga**.</span><span class="sxs-lookup"><span data-stu-id="f4d80-366">On the **Wave label template details** FastTab, select **Edit query**.</span></span> <span data-ttu-id="f4d80-367">I frågeredigerarens dialogruta, på fliken **Intervall** lägg till en rad med följande värden:</span><span class="sxs-lookup"><span data-stu-id="f4d80-367">Then, in the query editor dialog box, on the **Range** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="f4d80-368">**Register:** *försändelser*</span><span class="sxs-lookup"><span data-stu-id="f4d80-368">**Table:** *Shipments*</span></span>
    - <span data-ttu-id="f4d80-369">**Härlett register:** *försändelser*</span><span class="sxs-lookup"><span data-stu-id="f4d80-369">**Derived table:** *Shipments*</span></span>
    - <span data-ttu-id="f4d80-370">**Fält:** *Kontonummer*</span><span class="sxs-lookup"><span data-stu-id="f4d80-370">**Field:** *Account number*</span></span>
    - <span data-ttu-id="f4d80-371">**Kriterier:** Ange relevant kundkontonummer.</span><span class="sxs-lookup"><span data-stu-id="f4d80-371">**Criteria:** Enter the relevant customer account number.</span></span>

    <span data-ttu-id="f4d80-372">När du är klar klickar du på **OK** för att stänga dialogrutan för frågeredigeraren.</span><span class="sxs-lookup"><span data-stu-id="f4d80-372">When you've finished, select **OK** to close the query editor dialog box.</span></span>

### <a name="configure-number-sequence-extensions"></a><span data-ttu-id="f4d80-373">Konfigurera nummerserietillägg</span><span class="sxs-lookup"><span data-stu-id="f4d80-373">Configure number sequence extensions</span></span>

<span data-ttu-id="f4d80-374">Nummerserietillägg styr GS1 efterlevnaden av specifika nummerserier.</span><span class="sxs-lookup"><span data-stu-id="f4d80-374">Number sequence extensions control the GS1 compliance of specific number sequences.</span></span> <span data-ttu-id="f4d80-375">Den här konfigurationen är valfri för det aktuella scenariot.</span><span class="sxs-lookup"><span data-stu-id="f4d80-375">This configuration is optional for the current scenario.</span></span> <span data-ttu-id="f4d80-376">Mer information och instruktioner för konfigurering finns i [Konfigurera tillägg för nummerserier](../warehousing/configure-number-sequence-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="f4d80-376">For more information and configuration instructions, see [Configure number sequence extensions](../warehousing/configure-number-sequence-extensions.md).</span></span>

### <a name="create-a-sales-order-and-release-it-to-the-warehouse"></a><span data-ttu-id="f4d80-377">Skapa en försäljningsorder och släpp den på lagerstället</span><span class="sxs-lookup"><span data-stu-id="f4d80-377">Create a sales order and release it to the warehouse</span></span>

1. <span data-ttu-id="f4d80-378">Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="f4d80-378">Go to **Sales and marketing \> Sales order \> All sales orders**.</span></span>
1. <span data-ttu-id="f4d80-379">Skapa en försäljningsorder med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="f4d80-379">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="f4d80-380">**Kundkonto:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="f4d80-380">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="f4d80-381">**Lagerställe:** *63*</span><span class="sxs-lookup"><span data-stu-id="f4d80-381">**Warehouse:** *63*</span></span>

1. <span data-ttu-id="f4d80-382">Lägg till fem försäljningsorderrader:</span><span class="sxs-lookup"><span data-stu-id="f4d80-382">Add five sales order lines:</span></span>

    - <span data-ttu-id="f4d80-383">Försäljningsorderrad 1:</span><span class="sxs-lookup"><span data-stu-id="f4d80-383">Sales order line 1:</span></span>

        - <span data-ttu-id="f4d80-384">**Artikelnummer:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="f4d80-384">**Item number:** *A0001*</span></span>
        - <span data-ttu-id="f4d80-385">**Kvantitet:** *10*</span><span class="sxs-lookup"><span data-stu-id="f4d80-385">**Quantity:** *10*</span></span>

    - <span data-ttu-id="f4d80-386">Försäljningsorderrad 2:</span><span class="sxs-lookup"><span data-stu-id="f4d80-386">Sales order line 2:</span></span>

        - <span data-ttu-id="f4d80-387">**Artikelnummer:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="f4d80-387">**Item number:** *A0002*</span></span>
        - <span data-ttu-id="f4d80-388">**Kvantitet:** *20*</span><span class="sxs-lookup"><span data-stu-id="f4d80-388">**Quantity:** *20*</span></span>

    - <span data-ttu-id="f4d80-389">Försäljningsorderrad 3:</span><span class="sxs-lookup"><span data-stu-id="f4d80-389">Sales order line 3:</span></span>

        - <span data-ttu-id="f4d80-390">**Artikelnummer:** *L0006*</span><span class="sxs-lookup"><span data-stu-id="f4d80-390">**Item number:** *L0006*</span></span>
        - <span data-ttu-id="f4d80-391">**Kvantitet:** *20*</span><span class="sxs-lookup"><span data-stu-id="f4d80-391">**Quantity:** *20*</span></span>

    - <span data-ttu-id="f4d80-392">Försäljningsorderrad 4:</span><span class="sxs-lookup"><span data-stu-id="f4d80-392">Sales order line 4:</span></span>

        - <span data-ttu-id="f4d80-393">**Artikelnummer:** *L0100*</span><span class="sxs-lookup"><span data-stu-id="f4d80-393">**Item number:** *L0100*</span></span>
        - <span data-ttu-id="f4d80-394">**Kvantitet:** *40*</span><span class="sxs-lookup"><span data-stu-id="f4d80-394">**Quantity:** *40*</span></span>

    - <span data-ttu-id="f4d80-395">Försäljningsorderrad 5:</span><span class="sxs-lookup"><span data-stu-id="f4d80-395">Sales order line 5:</span></span>

        - <span data-ttu-id="f4d80-396">**Artikelnummer:** *L0101*</span><span class="sxs-lookup"><span data-stu-id="f4d80-396">**Item number:** *L0101*</span></span>
        - <span data-ttu-id="f4d80-397">**Kvantitet:** *50*</span><span class="sxs-lookup"><span data-stu-id="f4d80-397">**Quantity:** *50*</span></span>

    > [!NOTE]
    > <span data-ttu-id="f4d80-398">Artiklarna och kvantiteterna som anges här är endast exempel.</span><span class="sxs-lookup"><span data-stu-id="f4d80-398">The items and quantities that are provided here are only examples.</span></span> <span data-ttu-id="f4d80-399">De måste ha lager i det angivna lagerstället.</span><span class="sxs-lookup"><span data-stu-id="f4d80-399">They must have stock in the specified warehouse.</span></span>

1. <span data-ttu-id="f4d80-400">Välj försäljningsorderrad 1.</span><span class="sxs-lookup"><span data-stu-id="f4d80-400">Select sales order line 1.</span></span> <span data-ttu-id="f4d80-401">I avsnittet **Försäljningsorderrad** i menyn **Lager** välj **Reservationer**.</span><span class="sxs-lookup"><span data-stu-id="f4d80-401">Then, in the **Sales order line** section, on the **Inventory** menu, select **Reservations**.</span></span>
1. <span data-ttu-id="f4d80-402">På sidan **Reservation** i åtgärdsfönstret, välj **Reservera parti** och stäng sedan sidan.</span><span class="sxs-lookup"><span data-stu-id="f4d80-402">On the **Reservation** page, on the Action Pane, select **Reserve lot**, and then close the page.</span></span>
1. <span data-ttu-id="f4d80-403">Upprepa steg 4 och 5 för varje ytterligare försäljningsorderrad.</span><span class="sxs-lookup"><span data-stu-id="f4d80-403">Repeat steps 4 and 5 for each additional sales order line.</span></span>
1. <span data-ttu-id="f4d80-404">I åtgärdsfönstret på fliken **Lagerställe** välj **Frisläpp till regel för lagerställe**.</span><span class="sxs-lookup"><span data-stu-id="f4d80-404">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="f4d80-405">Då inträffar följande händelser:</span><span class="sxs-lookup"><span data-stu-id="f4d80-405">The following events occur:</span></span>

    - <span data-ttu-id="f4d80-406">I systemet bearbetas den skapade utleveransen med hjälp av mallen som inkluderar utskriftssteget för etikett.</span><span class="sxs-lookup"><span data-stu-id="f4d80-406">The system processes the created shipment using the template that includes the label printing step.</span></span> <span data-ttu-id="f4d80-407">Etikettlayouten används för att definiera etikettens format, och slutresultatet blir en etikett som har fem rader och som skrivs ut på den skrivare som väljs i etikettmallen.</span><span class="sxs-lookup"><span data-stu-id="f4d80-407">The label layout will be used to define the format of the label, and the end result will be a label that has five lines and that is printed on the printer that is selected in the label template.</span></span>
    - <span data-ttu-id="f4d80-408">Ett nytt fraktsedels-ID genereras för leveranserna.</span><span class="sxs-lookup"><span data-stu-id="f4d80-408">A new bill of lading ID is generated for the shipments.</span></span> <span data-ttu-id="f4d80-409">Om du har konfigurerat nummerserietilläggen följer påfyllnadsetikett-ID nummerformatet **SSCC-18**.</span><span class="sxs-lookup"><span data-stu-id="f4d80-409">If you configured the number sequence extensions, the wave label IDs will follow the **SSCC-18** number format.</span></span> 

<span data-ttu-id="f4d80-410">Du kan skriva ut dessa påfyllnadsetiketter igen genom att gå till **Lagerstyrning \> Frågor och rapporter \> Påfyllnadsetiketthistorik**.</span><span class="sxs-lookup"><span data-stu-id="f4d80-410">You can reprint these wave labels by going to **Warehouse management \> Inquiries and reports \> Wave label history**.</span></span>

## <a name="scenario-3-wave-label-printing-for-multi-tiered-labels"></a><span data-ttu-id="f4d80-411">Scenario 3: utskrift av påfyllnadsetikett för etiketter med flera nivåer</span><span class="sxs-lookup"><span data-stu-id="f4d80-411">Scenario 3: Wave label printing for multi-tiered labels</span></span>

<span data-ttu-id="f4d80-412">Det här scenariot visar hur du använder funktionen utskrift av påfyllnadsetikett när lagerprocesserna kräver flera nivåer för leveransetiketter.</span><span class="sxs-lookup"><span data-stu-id="f4d80-412">This scenario shows how to use the wave label printing functionality when the warehousing processes require several tiers of shipping labels.</span></span> <span data-ttu-id="f4d80-413">Till exempel kan separata etiketter behöva skrivas ut för kartonger och lastpallar, och en avbrottsetikett måste skrivas ut för en hel leverans.</span><span class="sxs-lookup"><span data-stu-id="f4d80-413">For example, separate labels might have to be printed for cartons and pallets, and a break label might have to be printed for a whole shipment.</span></span> <span data-ttu-id="f4d80-414">Avbrottsetiketter är en separat typ av etikett som kan användas som avgränsare mellan rullar och behållare, t.ex. etiketter för leverans-ID och en streckkod, så att etiketterna enkelt kan sorteras när de har skrivits ut.</span><span class="sxs-lookup"><span data-stu-id="f4d80-414">Break labels are a separate type of label that can be used as a divider between rolls and containers, such as labels for the shipment ID and a barcode, so that the labels can easily be sorted after they are printed.</span></span>

<span data-ttu-id="f4d80-415">Den huvudsakliga skillnaden mellan konfigurationen av scenariot och konfigurationen av scenario 1, förutom att bryta etiketter är aktiverade, är att flera typer av påfyllnadetiketter måste associeras med påfyllnadsetikettmallen och enhetssekvensgruppraderna.</span><span class="sxs-lookup"><span data-stu-id="f4d80-415">The main difference between the configuration of this scenario and the configuration of scenario 1, besides the fact that break labels are enabled, is that multiple wave label types must be associated with wave label templates and unit sequence group lines.</span></span> <span data-ttu-id="f4d80-416">För att kunna utföra den här konfigurationen ställer du in följande element för det här scenariot:</span><span class="sxs-lookup"><span data-stu-id="f4d80-416">To accomplish this configuration, you set up the following elements for this scenario:</span></span>

- <span data-ttu-id="f4d80-417">**Metoder för påfyllnadsbearbetning:** du markerar en påfyllnadsetiketts metod som "upprepningsbar", lägger till den två (eller fler) tiderna i påfyllnadsmallen och ställer in olika koder för påfyllnadssteg.</span><span class="sxs-lookup"><span data-stu-id="f4d80-417">**Wave processing methods:** You will mark the wave label method as "repeatable," add it two (or more) times to the wave template, and set different wave step codes.</span></span>
- <span data-ttu-id="f4d80-418">**Mallar för påfyllnadsetikett:** du kommer att konfigurera mallarna för påfyllnadsetikett och länka dem till påfyllnadsmallen.</span><span class="sxs-lookup"><span data-stu-id="f4d80-418">**Wave label templates:** You will configure the wave label templates and link them to the wave template.</span></span> <span data-ttu-id="f4d80-419">Varje påfyllnadsetikettmall har en egen typ av påfyllnadsetikett.</span><span class="sxs-lookup"><span data-stu-id="f4d80-419">Each wave label template has its own wave label type.</span></span>
- <span data-ttu-id="f4d80-420">**Layout för påfyllnadsetiketter:** du kan skapa flera layouter för påfyllnadsetiketter.</span><span class="sxs-lookup"><span data-stu-id="f4d80-420">**Wave label layouts:** You will create multiple wave label layouts.</span></span> <span data-ttu-id="f4d80-421">Det finns en separat etikettlayout för varje "nivå" med etiketter och det får också en layout för avbrottsetiketten.</span><span class="sxs-lookup"><span data-stu-id="f4d80-421">There will be a separate label layout for each "tier" of labels, and there will also be a break label layout.</span></span>

<span data-ttu-id="f4d80-422">Det här scenariot visar komplett flöde.</span><span class="sxs-lookup"><span data-stu-id="f4d80-422">This scenario shows the end-to-end flow.</span></span>

### <a name="make-demo-data-available"></a><span data-ttu-id="f4d80-423">Gör demodata tillgängliga</span><span class="sxs-lookup"><span data-stu-id="f4d80-423">Make demo data available</span></span>

<span data-ttu-id="f4d80-424">För att följa detta scenario måste du ha demonstrationsdata installerad och du måste välja juridiska personen **USMF**.</span><span class="sxs-lookup"><span data-stu-id="f4d80-424">To follow this scenario, you must have demo data installed, and you must select the **USMF** legal entity.</span></span>

### <a name="set-up-a-wave-process-method"></a><span data-ttu-id="f4d80-425">Ställa in en påfyllnadsprocessmetod</span><span class="sxs-lookup"><span data-stu-id="f4d80-425">Set up a wave process method</span></span>

1. <span data-ttu-id="f4d80-426">Gå till **Lagerstyrning \> Inställningar \> Påfyllnader \> Metoder för påfyllnadsprocess**.</span><span class="sxs-lookup"><span data-stu-id="f4d80-426">Go to **Warehouse management \> Setup \> Waves \> Wave process methods**.</span></span>
1. <span data-ttu-id="f4d80-427">Kontrollera att **waveLabelPrinting** finns i listan.</span><span class="sxs-lookup"><span data-stu-id="f4d80-427">Confirm that **waveLabelPrinting** is in the list.</span></span> <span data-ttu-id="f4d80-428">Om den inte finns med väljer du **återskapa metoder** i åtgärdsfönstret för att lägga till den.</span><span class="sxs-lookup"><span data-stu-id="f4d80-428">If it isn't, select **Regenerate methods** on the Action Pane to add it.</span></span>
1. <span data-ttu-id="f4d80-429">För metoden **waveLabelPrinting** markera kryssrutan **gör metoden upprepningsbar**.</span><span class="sxs-lookup"><span data-stu-id="f4d80-429">For the **waveLabelPrinting** method, select the **Make method repeatable** check box.</span></span>

### <a name="set-up-a-wave-template"></a><span data-ttu-id="f4d80-430">Ställa in en påfyllnadsmall</span><span class="sxs-lookup"><span data-stu-id="f4d80-430">Set up a wave template</span></span>

1. <span data-ttu-id="f4d80-431">Gå till **Lagerstyrning \> Inställningar \> Påfyllnader \> Påfyllnadsmallar**.</span><span class="sxs-lookup"><span data-stu-id="f4d80-431">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
2. <span data-ttu-id="f4d80-432">Välj en mall som **62 standard för leverans**.</span><span class="sxs-lookup"><span data-stu-id="f4d80-432">Select a template, such as **62 Shipping Default**.</span></span>
3. <span data-ttu-id="f4d80-433">På snabbfliken **metoder** flyttar du metoden **utskrift av påfyllnadsetiketter** till kolumnen **valda metoder**.</span><span class="sxs-lookup"><span data-stu-id="f4d80-433">On the **Methods** FastTab, move the **Wave label printing** method to the **Selected methods** column.</span></span>
4. <span data-ttu-id="f4d80-434">I kolumnen **valda metoder** tilldelar du ett värde för **Kod för påfyllnadssteg** som *kartong* till metoden **utskrift av påfyllnadsetikett**.</span><span class="sxs-lookup"><span data-stu-id="f4d80-434">In the **Selected methods** column, assign a **Wave step code** value, such as *Carton*, to the **Wave label printing** method.</span></span> <span data-ttu-id="f4d80-435">För mer information om koder för påfyllnadssteg, se [Koder för påfyllnadssteg](wave-step-codes.md).</span><span class="sxs-lookup"><span data-stu-id="f4d80-435">For more information about wave step codes, see [Wave step codes](wave-step-codes.md).</span></span>
5. <span data-ttu-id="f4d80-436">Flytta metoden **utskrift av påfyllnadsetikett** till kolumnen **valda metoder** en andra gång.</span><span class="sxs-lookup"><span data-stu-id="f4d80-436">Move the **Wave label printing** method to the **Selected methods** column a second time.</span></span>
6. <span data-ttu-id="f4d80-437">I kolumnen **valda metoder** tilldelar du ett annat värde för **Kod för påfyllnadssteg** som *lastpall* till den andra metoden **utskrift av påfyllnadsetikett**.</span><span class="sxs-lookup"><span data-stu-id="f4d80-437">In the **Selected methods** column, assign a different **Wave step code** value, such as *Pallet*, to the second **Wave label printing** method.</span></span> <span data-ttu-id="f4d80-438">För mer information om koder för påfyllnadssteg, se [Koder för påfyllnadssteg](wave-step-codes.md).</span><span class="sxs-lookup"><span data-stu-id="f4d80-438">For more information about wave step codes, see [Wave step codes](wave-step-codes.md).</span></span>

### <a name="create-three-wave-label-layouts"></a><span data-ttu-id="f4d80-439">Skapa tre layouter för påfyllnadsetiketten</span><span class="sxs-lookup"><span data-stu-id="f4d80-439">Create three wave label layouts</span></span>

1. <span data-ttu-id="f4d80-440">Gå till **Lagerstyrning \> Inställningar \> Dokumentflöde \> Layout för påfyllnadsetikett**.</span><span class="sxs-lookup"><span data-stu-id="f4d80-440">Go to **Warehouse management \> Setup \> Document routing \> Wave label layouts**.</span></span>
1. <span data-ttu-id="f4d80-441">Skapa en post med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="f4d80-441">Create a record that has the following settings:</span></span>

    - <span data-ttu-id="f4d80-442">**Etikettlayout-ID:** *kartong*</span><span class="sxs-lookup"><span data-stu-id="f4d80-442">**Label layout ID:** *Carton*</span></span>
    - <span data-ttu-id="f4d80-443">**Beskrivning:** *kartong (SSCC)*</span><span class="sxs-lookup"><span data-stu-id="f4d80-443">**Description:** *Carton (SSCC)*</span></span>

1. <span data-ttu-id="f4d80-444">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="f4d80-444">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="f4d80-445">I åtgärdsfönstret, välj **Inställningar för påfyllnadsetikettrad**.</span><span class="sxs-lookup"><span data-stu-id="f4d80-445">On the Action Pane, select **Wave label row settings**.</span></span>

    <span data-ttu-id="f4d80-446">Sidan **Inställningar för påfyllnadsetikettrad** visas.</span><span class="sxs-lookup"><span data-stu-id="f4d80-446">The **Wave label row settings** page appears.</span></span> <span data-ttu-id="f4d80-447">Här kan du konfigurera den dynamiska delen av etiketten.</span><span class="sxs-lookup"><span data-stu-id="f4d80-447">Here, you can configure the dynamic part of the label.</span></span>

1. <span data-ttu-id="f4d80-448">Lägg till en rad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="f4d80-448">Add a row that has the following settings:</span></span>

    - <span data-ttu-id="f4d80-449">**Rad-ID:** *WaveLabel*</span><span class="sxs-lookup"><span data-stu-id="f4d80-449">**Row Id:** *WaveLabel*</span></span>
    - <span data-ttu-id="f4d80-450">**Radtabellnamn:** *WHSWaveLabel*</span><span class="sxs-lookup"><span data-stu-id="f4d80-450">**Row table name:** *WHSWaveLabel*</span></span>
    - <span data-ttu-id="f4d80-451">**Radens startposition:** *0*</span><span class="sxs-lookup"><span data-stu-id="f4d80-451">**Row start position:** *0*</span></span>

        <span data-ttu-id="f4d80-452">I det här fältet definieras den lodräta position där raden ska börja etiketten.</span><span class="sxs-lookup"><span data-stu-id="f4d80-452">This field defines the vertical position where the row will begin on the label.</span></span>

    - <span data-ttu-id="f4d80-453">**Radhöjd:** *0*</span><span class="sxs-lookup"><span data-stu-id="f4d80-453">**Row height:** *0*</span></span>

        <span data-ttu-id="f4d80-454">I det här fältet definieras höjden på varje rad (i punkter) enligt ZPL-standard.</span><span class="sxs-lookup"><span data-stu-id="f4d80-454">This field defines the height of each row (in points), according to the ZPL standard.</span></span> <span data-ttu-id="f4d80-455">Radhöjden är positiv för vågräta etiketter och är negativ för lodräta etiketter.</span><span class="sxs-lookup"><span data-stu-id="f4d80-455">The row height is positive for horizontal labels and negative for vertical labels.</span></span> <span data-ttu-id="f4d80-456">Eftersom det bara finns en rad i det här exemplet kan du ställa in värdet på *0* (noll).</span><span class="sxs-lookup"><span data-stu-id="f4d80-456">Because there is just one row in this example, you can set the value to *0* (zero).</span></span>

    - <span data-ttu-id="f4d80-457">**Rader per sida:** *1*</span><span class="sxs-lookup"><span data-stu-id="f4d80-457">**Rows per page:** *1*</span></span>

        <span data-ttu-id="f4d80-458">I det här fältet definieras antalet rader som kan skrivas ut på varje etikett.</span><span class="sxs-lookup"><span data-stu-id="f4d80-458">This field defines the number of rows that can be printed on each label.</span></span>

        > [!NOTE]
        > <span data-ttu-id="f4d80-459">Den här inställningen gör att en separat ZPL-etikett skrivs ut för varje post i tabellen med påfyllnadsetiketter.</span><span class="sxs-lookup"><span data-stu-id="f4d80-459">This setup will cause a separate ZPL label to be printed for each record in the wave labels table.</span></span>

1. <span data-ttu-id="f4d80-460">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f4d80-460">Close the page.</span></span>
1. <span data-ttu-id="f4d80-461">I åtgärdsfönstret väljer du **Redigera fråga**.</span><span class="sxs-lookup"><span data-stu-id="f4d80-461">On the Action Pane, select **Edit query**.</span></span>
1. <span data-ttu-id="f4d80-462">I frågeredigerarens dialogruta, på fliken **Intervall** lägg till en rad med följande värden:</span><span class="sxs-lookup"><span data-stu-id="f4d80-462">In the query editor dialog box, on the **Range** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="f4d80-463">**Tabell:** *Arbetsrader*</span><span class="sxs-lookup"><span data-stu-id="f4d80-463">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="f4d80-464">**Härlett register:** *Arbetsrader*</span><span class="sxs-lookup"><span data-stu-id="f4d80-464">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="f4d80-465">**Fält:** *arbetstyp*</span><span class="sxs-lookup"><span data-stu-id="f4d80-465">**Field:** *Work type*</span></span>
    - <span data-ttu-id="f4d80-466">**Kriterier:** *Plocka*</span><span class="sxs-lookup"><span data-stu-id="f4d80-466">**Criteria:** *Pick*</span></span>

    <span data-ttu-id="f4d80-467">Den här frågan ser till att endast arbetsrader av typen plockning skrivs ut på etiketten, inte artikelrader av typen radtyp.</span><span class="sxs-lookup"><span data-stu-id="f4d80-467">This query ensures that only pick-type work lines will be printed on the label, not put-type work lines.</span></span>

1. <span data-ttu-id="f4d80-468">Om du vill kunna skriva ut fraktsedels-ID väljer du på fliken **kopplingar**, sedan **arbetsrader** och kopplar tabellen **leveranser** till den.</span><span class="sxs-lookup"><span data-stu-id="f4d80-468">If you want to be able to print the bill of lading ID, on the **Joins** tab, select the **Work lines** table, and join the **Shipments** table to it.</span></span> 
1. <span data-ttu-id="f4d80-469">Stäng dialogrutan frågeredigeraren.</span><span class="sxs-lookup"><span data-stu-id="f4d80-469">Close the query editor dialog box.</span></span>
1. <span data-ttu-id="f4d80-470">På snabbfliken **Layout för skrivartext** finns tre avsnitt där du kan skriva skrivarkod: **rubrikavsnitt**, **brödtext** och **sidfotsavsnitt**.</span><span class="sxs-lookup"><span data-stu-id="f4d80-470">The **Printer text Layout** FastTab has three sections where you can write printer code: **Header section**, **Body section**, and **Footer section**.</span></span> <span data-ttu-id="f4d80-471">I avsnittet **rubrikavsnitt** i fältet **etikettrubrik** anger du koden för önskad rubrik.</span><span class="sxs-lookup"><span data-stu-id="f4d80-471">In the **Header section** section, in the **Label header** field, enter code for the required header.</span></span> <span data-ttu-id="f4d80-472">Om du till exempel använder Zebra-skrivare kan du använda följande kod.</span><span class="sxs-lookup"><span data-stu-id="f4d80-472">For example, if you're using Zebra printers, you can use the following code.</span></span>


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

1. <span data-ttu-id="f4d80-473">I avsnittet **brödtext** i fältet **etikettext** anger du ZPL-koden för önskad text.</span><span class="sxs-lookup"><span data-stu-id="f4d80-473">In the **Body section** section, in the **Label body** field, enter ZPL code for the required body.</span></span> <span data-ttu-id="f4d80-474">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="f4d80-474">Here is an example.</span></span>

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

1. <span data-ttu-id="f4d80-475">I avsnittet **brödtext** i fältet **etikettsidfot** anger du ZPL-koden för önskad sidfot.</span><span class="sxs-lookup"><span data-stu-id="f4d80-475">In the **Body section** section, in the **Label footer** field, enter ZPL code for the required footer.</span></span> <span data-ttu-id="f4d80-476">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="f4d80-476">Here is an example.</span></span>

    ```plaintext
    ^PQ1^XZ
    ```

    > [!NOTE]
    > <span data-ttu-id="f4d80-477">Installationen kommer att skriva ut en kopia av varje etikett.</span><span class="sxs-lookup"><span data-stu-id="f4d80-477">This setup will print one copy of each label.</span></span> <span data-ttu-id="f4d80-478">Om du vill ha fler kopior (t.ex. en kopia för varje sida av lastpallen) anger du värdet **n** för avsnittet **\^PQn** i sidfoten till det antal kopior som krävs.</span><span class="sxs-lookup"><span data-stu-id="f4d80-478">If you require more copies (for example, one copy for each side of the pallet), set the **n** value for the **\^PQn** section in the footer to the required number of copies.</span></span> <span data-ttu-id="f4d80-479">Om du till exempel vill skriva ut fyra kopior av varje etikett anger du **\^PQ4**.</span><span class="sxs-lookup"><span data-stu-id="f4d80-479">For example, to print four copies of each label, specify **\^PQ4**.</span></span>

1. <span data-ttu-id="f4d80-480">Nu kan du använda din första etikett.</span><span class="sxs-lookup"><span data-stu-id="f4d80-480">The first label is now ready to use.</span></span>
1. <span data-ttu-id="f4d80-481">Skapa en andra layoutpost med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="f4d80-481">Create a second layout record that has the following settings:</span></span>

    - <span data-ttu-id="f4d80-482">**Etikettlayout-ID:** *lastpall*</span><span class="sxs-lookup"><span data-stu-id="f4d80-482">**Label layout ID:** *Pallet*</span></span>
    - <span data-ttu-id="f4d80-483">**Beskrivning:** *lastpall*</span><span class="sxs-lookup"><span data-stu-id="f4d80-483">**Description:** *Pallet*</span></span>

1. <span data-ttu-id="f4d80-484">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="f4d80-484">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="f4d80-485">I åtgärdsfönstret, välj **Inställningar för påfyllnadsetikettrad**.</span><span class="sxs-lookup"><span data-stu-id="f4d80-485">On the Action Pane, select **Wave label row settings**.</span></span>

    <span data-ttu-id="f4d80-486">Sidan **Inställningar för påfyllnadsetikettrad** visas.</span><span class="sxs-lookup"><span data-stu-id="f4d80-486">The **Wave label row settings** page appears.</span></span> <span data-ttu-id="f4d80-487">Här kan du konfigurera den dynamiska delen av etiketten.</span><span class="sxs-lookup"><span data-stu-id="f4d80-487">Here, you can configure the dynamic part of the label.</span></span>

1. <span data-ttu-id="f4d80-488">Lägg till en rad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="f4d80-488">Add a row that has the following settings:</span></span>

    - <span data-ttu-id="f4d80-489">**Rad-ID:** *WaveLabel*</span><span class="sxs-lookup"><span data-stu-id="f4d80-489">**Row Id:** *WaveLabel*</span></span>
    - <span data-ttu-id="f4d80-490">**Radtabellnamn:** *WHSWaveLabel*</span><span class="sxs-lookup"><span data-stu-id="f4d80-490">**Row table name:** *WHSWaveLabel*</span></span>
    - <span data-ttu-id="f4d80-491">**Radens startposition:** *0*</span><span class="sxs-lookup"><span data-stu-id="f4d80-491">**Row start position:** *0*</span></span>

        <span data-ttu-id="f4d80-492">I det här fältet definieras den lodräta position där raden ska börja etiketten.</span><span class="sxs-lookup"><span data-stu-id="f4d80-492">This field defines the vertical position where the row will begin on the label.</span></span>

    - <span data-ttu-id="f4d80-493">**Radhöjd:** *0*</span><span class="sxs-lookup"><span data-stu-id="f4d80-493">**Row height:** *0*</span></span>

        <span data-ttu-id="f4d80-494">I det här fältet definieras höjden på varje rad (i punkter) enligt ZPL-standard.</span><span class="sxs-lookup"><span data-stu-id="f4d80-494">This field defines the height of each row (in points), according to the ZPL standard.</span></span> <span data-ttu-id="f4d80-495">Radhöjden är positiv för vågräta etiketter och är negativ för lodräta etiketter.</span><span class="sxs-lookup"><span data-stu-id="f4d80-495">The row height is positive for horizontal labels and negative for vertical labels.</span></span> <span data-ttu-id="f4d80-496">Eftersom det bara finns en rad i det här exemplet kan du ställa in värdet på *0* (noll).</span><span class="sxs-lookup"><span data-stu-id="f4d80-496">Because there is just one row in this example, you can set the value to *0* (zero).</span></span>

    - <span data-ttu-id="f4d80-497">**Rader per sida:** *1*</span><span class="sxs-lookup"><span data-stu-id="f4d80-497">**Rows per page:** *1*</span></span>

        <span data-ttu-id="f4d80-498">I det här fältet definieras antalet rader som kan skrivas ut på varje etikett.</span><span class="sxs-lookup"><span data-stu-id="f4d80-498">This field defines the number of rows that can be printed on each label.</span></span>

        > [!NOTE]
        > <span data-ttu-id="f4d80-499">Den här inställningen gör att en separat ZPL-etikett skrivs ut för varje post i tabellen med påfyllnadsetiketter.</span><span class="sxs-lookup"><span data-stu-id="f4d80-499">This setup causes a separate ZPL label to be printed for each record in the wave labels table.</span></span>

1. <span data-ttu-id="f4d80-500">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f4d80-500">Close the page.</span></span>
1. <span data-ttu-id="f4d80-501">I åtgärdsfönstret väljer du **Redigera fråga**.</span><span class="sxs-lookup"><span data-stu-id="f4d80-501">On the Action Pane, select **Edit query**.</span></span>
1. <span data-ttu-id="f4d80-502">I frågeredigerarens dialogruta, på fliken **Intervall** lägg till en rad med följande värden:</span><span class="sxs-lookup"><span data-stu-id="f4d80-502">In the query editor dialog box, on the **Range** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="f4d80-503">**Tabell:** *Arbetsrader*</span><span class="sxs-lookup"><span data-stu-id="f4d80-503">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="f4d80-504">**Härlett register:** *Arbetsrader*</span><span class="sxs-lookup"><span data-stu-id="f4d80-504">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="f4d80-505">**Fält:** *arbetstyp*</span><span class="sxs-lookup"><span data-stu-id="f4d80-505">**Field:** *Work type*</span></span>
    - <span data-ttu-id="f4d80-506">**Kriterier:** *Plocka*</span><span class="sxs-lookup"><span data-stu-id="f4d80-506">**Criteria:** *Pick*</span></span>

    <span data-ttu-id="f4d80-507">Den här frågan ser till att endast arbetsrader av typen plockning skrivs ut på etiketten, inte artikelrader av typen radtyp.</span><span class="sxs-lookup"><span data-stu-id="f4d80-507">This query ensures that only pick-type work lines will be printed on the label, not put-type work lines.</span></span>

1. <span data-ttu-id="f4d80-508">Om du vill kunna skriva ut fraktsedels-ID väljer du på fliken **kopplingar**, sedan **arbetsrader** och kopplar tabellen **leveranser** till den.</span><span class="sxs-lookup"><span data-stu-id="f4d80-508">If you want to be able to print the bill of lading ID, on the **Joins** tab, select the **Work lines** table, and join the **Shipments** table to it.</span></span>
1. <span data-ttu-id="f4d80-509">Stäng dialogrutan frågeredigeraren.</span><span class="sxs-lookup"><span data-stu-id="f4d80-509">Close the query editor dialog box.</span></span>
1. <span data-ttu-id="f4d80-510">På snabbfliken **Layout för skrivartext** finns tre avsnitt där du kan skriva skrivarkod: **rubrikavsnitt**, **brödtext** och **sidfotsavsnitt**.</span><span class="sxs-lookup"><span data-stu-id="f4d80-510">The **Printer text Layout** FastTab has three sections where you can write printer code: **Header section**, **Body section**, and **Footer section**.</span></span> <span data-ttu-id="f4d80-511">I avsnittet **rubrikavsnitt** i fältet **etikettrubrik** anger du koden för önskad rubrik.</span><span class="sxs-lookup"><span data-stu-id="f4d80-511">In the **Header section** section, in the **Label header** field, enter code for the required header.</span></span> <span data-ttu-id="f4d80-512">Om du till exempel använder Zebra-skrivare kan du använda följande kod.</span><span class="sxs-lookup"><span data-stu-id="f4d80-512">For example, if you're using Zebra printers, you can use the following code.</span></span>

    ```plaintext
    CT~~CD,~CC^~CT~
    ^XA
    ^LH10,10
    ^FO0,0 ^AT ^FD$WHSWaveLabel.WaveLabelId$ ^FS
    ^FO0,75 ^AT ^FD$WHSWorkLine.ShipmentId$ ^FS
    ^FO0,150 ^AT ^FD$WHSShipmentTable.BillOfLadingId$ ^FS
    ```

1. <span data-ttu-id="f4d80-513">I avsnittet **brödtext** i fältet **etikettext** anger du ZPL-koden för önskad text.</span><span class="sxs-lookup"><span data-stu-id="f4d80-513">In the **Body section** section, in the **Label body** field, enter ZPL code for the required body.</span></span> <span data-ttu-id="f4d80-514">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="f4d80-514">Here is an example.</span></span>

    ```plaintext
    <Row name="WaveLabel">
    ^FO0,450 ^AT ^FDItem ^FS
    ^FO200,450 ^AT ^FDQuantity ^FS
    ^FO0,[[YPos]] ^AT ^FD$WHSWaveLabel.LabelItemId$ ^FS
    ^FO200,[[YPos]] ^AT ^FD$WHSWaveLabel.QtyWork$ ^FS
    </Row>
    ```

1. <span data-ttu-id="f4d80-515">I avsnittet **brödtext** i fältet **etikettsidfot** anger du ZPL-koden för önskad sidfot.</span><span class="sxs-lookup"><span data-stu-id="f4d80-515">In the **Body section** section, in the **Label footer** field, enter ZPL code for the required footer.</span></span> <span data-ttu-id="f4d80-516">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="f4d80-516">Here is an example.</span></span>

    ```plaintext
    ^PQ1^XZ
    ```

    > [!NOTE]
    > <span data-ttu-id="f4d80-517">Installationen kommer att skriva ut en kopia av varje etikett.</span><span class="sxs-lookup"><span data-stu-id="f4d80-517">This setup will print one copy of each label.</span></span> <span data-ttu-id="f4d80-518">Om du vill ha fler kopior (t.ex. en kopia för varje sida av lastpallen) anger du värdet **n** för avsnittet **\^PQn** i sidfoten till det antal kopior som krävs.</span><span class="sxs-lookup"><span data-stu-id="f4d80-518">If you require more copies (for example, one copy for each side of the pallet), set the **n** value for the **\^PQn** section in the footer to the required number of copies.</span></span> <span data-ttu-id="f4d80-519">Om du till exempel vill skriva ut fyra kopior av varje etikett anger du **\^PQ4**.</span><span class="sxs-lookup"><span data-stu-id="f4d80-519">For example, to print four copies of each label, specify **\^PQ4**.</span></span>

1. <span data-ttu-id="f4d80-520">Nu kan du använda din andra etikett.</span><span class="sxs-lookup"><span data-stu-id="f4d80-520">The second label is now ready to use.</span></span>
1. <span data-ttu-id="f4d80-521">Skapa en tredje layoutpost med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="f4d80-521">Create a third layout record that has the following settings:</span></span>

    - <span data-ttu-id="f4d80-522">**Etikettlayout-ID:** *Avbrott*</span><span class="sxs-lookup"><span data-stu-id="f4d80-522">**Label layout ID:** *Break*</span></span>
    - <span data-ttu-id="f4d80-523">**Beskrivning:** *avbrottsetikett*</span><span class="sxs-lookup"><span data-stu-id="f4d80-523">**Description:** *Break label*</span></span>

1. <span data-ttu-id="f4d80-524">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="f4d80-524">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="f4d80-525">På snabbfliken **Layout för skrivartext** finns tre avsnitt där du kan skriva skrivarkod: **rubrikavsnitt**, **brödtext** och **sidfotsavsnitt**.</span><span class="sxs-lookup"><span data-stu-id="f4d80-525">The **Printer text Layout** FastTab has three sections where you can write printer code: **Header section**, **Body section**, and **Footer section**.</span></span> <span data-ttu-id="f4d80-526">I avsnittet **rubrikavsnitt** i fältet **etikettrubrik** anger du ZPL-koden för önskad rubrik.</span><span class="sxs-lookup"><span data-stu-id="f4d80-526">In the **Header section** section, in the **Label header** field, enter ZPL code for the required header.</span></span> <span data-ttu-id="f4d80-527">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="f4d80-527">Here is an example.</span></span>

    ```plaintext
    CT~~CD,~CC^~CT~
    ^XA
    ^LH10,10
    ^FO0,0 ^AT ^FD$WHSWorkLine.ShipmentId$ ^FS
    ```

1. <span data-ttu-id="f4d80-528">Den här gången behövs ingen brödtext.</span><span class="sxs-lookup"><span data-stu-id="f4d80-528">This time, no body is required.</span></span> <span data-ttu-id="f4d80-529">Ange därför bara den text som krävs i avsnittet **sidfotsavsnitt**.</span><span class="sxs-lookup"><span data-stu-id="f4d80-529">Therefore, just enter the required text in the **Footer section** section.</span></span> <span data-ttu-id="f4d80-530">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="f4d80-530">Here is an example.</span></span>

    ```plaintext
    ^XZ
    ```

    <span data-ttu-id="f4d80-531">Nu kan du använda din tredje etikett.</span><span class="sxs-lookup"><span data-stu-id="f4d80-531">The third label is now ready to use.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f4d80-532">Den tredje etiketten är en avbrottsetikett som ska användas som avgränsare mellan etikettrullar.</span><span class="sxs-lookup"><span data-stu-id="f4d80-532">This third label is a break label that will be used as a divider between label rolls.</span></span>

### <a name="create-two-wave-label-types"></a><span data-ttu-id="f4d80-533">Skapa två typer av påfyllnadsetiketten</span><span class="sxs-lookup"><span data-stu-id="f4d80-533">Create two wave label types</span></span>

1. <span data-ttu-id="f4d80-534">Gå till **Lagerstyrning \> Inställningar \> Dokumentflöde \> Typer av påfyllnadsetikett**.</span><span class="sxs-lookup"><span data-stu-id="f4d80-534">Go to **Warehouse management \> Setup \> Document routing \> Wave label types**.</span></span>
1. <span data-ttu-id="f4d80-535">Skapa en post med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="f4d80-535">Create a record that has the following settings:</span></span>

    - <span data-ttu-id="f4d80-536">**Etikettyp:** *kartong*</span><span class="sxs-lookup"><span data-stu-id="f4d80-536">**Label type:** *Carton*</span></span>
    - <span data-ttu-id="f4d80-537">**Beskrivning:** *kartong*</span><span class="sxs-lookup"><span data-stu-id="f4d80-537">**Description:** *Carton*</span></span>

1. <span data-ttu-id="f4d80-538">Skapa en andra post med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="f4d80-538">Create a second record that has the following settings:</span></span>

    - <span data-ttu-id="f4d80-539">**Etikettyp:** *lastpall*</span><span class="sxs-lookup"><span data-stu-id="f4d80-539">**Label type:** *Pallet*</span></span>
    - <span data-ttu-id="f4d80-540">**Beskrivning:** *lastpall*</span><span class="sxs-lookup"><span data-stu-id="f4d80-540">**Description:** *Pallet*</span></span>

### <a name="set-up-unit-sequence-groups"></a><span data-ttu-id="f4d80-541">Konfigurera enhetssekvensgrupper</span><span class="sxs-lookup"><span data-stu-id="f4d80-541">Set up unit sequence groups</span></span>

1. <span data-ttu-id="f4d80-542">Gå till **Lagerstyrning \> Inställningar \> Lagerställe \> Enhetsseriegrupp**.</span><span class="sxs-lookup"><span data-stu-id="f4d80-542">Go to **Warehouse management \> Setup \> Warehouse \> Unit sequence groups**.</span></span>
1. <span data-ttu-id="f4d80-543">Välj eller skapa en grupp för **Ea Box PL**.</span><span class="sxs-lookup"><span data-stu-id="f4d80-543">Select or create an **Ea Box PL** group.</span></span>
1. <span data-ttu-id="f4d80-544">För raden **ruta** ange fältet **typ av påfyllnadsnivå** till *kartong*.</span><span class="sxs-lookup"><span data-stu-id="f4d80-544">For the **Box** line, set the **Wave level type** field to *Carton*.</span></span>
1. <span data-ttu-id="f4d80-545">För raden **PL** ange fältet **typ av påfyllnadsnivå** till *lastpall*.</span><span class="sxs-lookup"><span data-stu-id="f4d80-545">For the **PL** line, set the **Wave level type** field to *Pallet*.</span></span>

### <a name="create-wave-label-templates"></a><span data-ttu-id="f4d80-546">Skapa mallar för påfyllnadsetikett</span><span class="sxs-lookup"><span data-stu-id="f4d80-546">Create wave label templates</span></span>

1. <span data-ttu-id="f4d80-547">Gå till **Lagerstyrning \> Inställningar \> Dokumentflöde \> Mall för påfyllnadsetikett**.</span><span class="sxs-lookup"><span data-stu-id="f4d80-547">Go to **Warehouse management \> Setup \> Document routing \> Wave label templates**.</span></span>
1. <span data-ttu-id="f4d80-548">Skapa en etikettmall med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="f4d80-548">Create a label template that has the following settings:</span></span>

    - <span data-ttu-id="f4d80-549">**Namn på etikettmallen:** *kartongetiketter*</span><span class="sxs-lookup"><span data-stu-id="f4d80-549">**Label template name:** *Carton labels*</span></span>
    - <span data-ttu-id="f4d80-550">**Beskrivning:** *kartongetiketter*</span><span class="sxs-lookup"><span data-stu-id="f4d80-550">**Description:** *Carton labels*</span></span>
    - <span data-ttu-id="f4d80-551">**Kod för påfyllnadssteg:** *kartong*</span><span class="sxs-lookup"><span data-stu-id="f4d80-551">**Wave step code:** *Carton*</span></span>
    - <span data-ttu-id="f4d80-552">**Lagerställe:** *62*</span><span class="sxs-lookup"><span data-stu-id="f4d80-552">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="f4d80-553">På snabbfliken **allmänna** i fältet **typ av påfyllnadsetikett** väljer du ett värde som *kartong*.</span><span class="sxs-lookup"><span data-stu-id="f4d80-553">On the **General** FastTab, in the **Wave label type** field, select a value, such as *Carton*.</span></span>
1. <span data-ttu-id="f4d80-554">På snabbfliken **information om påfyllnadsetikettens mall** och lägg till en rad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="f4d80-554">On the **Wave label template details** FastTab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="f4d80-555">**Etikettlayout-ID:** *kartong*</span><span class="sxs-lookup"><span data-stu-id="f4d80-555">**Label layout ID:** *Carton*</span></span>
    - <span data-ttu-id="f4d80-556">**Skrivarnamn:** Välj en lämplig ZPL-skrivare.</span><span class="sxs-lookup"><span data-stu-id="f4d80-556">**Printer name:** Select an appropriate ZPL printer.</span></span>
    - <span data-ttu-id="f4d80-557">**Kör fråga:** *Ja* (den här inställningen är valfri, men rekommenderas för optimal prestanda.)</span><span class="sxs-lookup"><span data-stu-id="f4d80-557">**Run query:** *Yes* (This setting is optional, but it's recommended for optimal performance.)</span></span>

1. <span data-ttu-id="f4d80-558">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="f4d80-558">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="f4d80-559">Valfritt: om du ställer in en kundspecifik etikettdesign måste du skapa en fråga för att hitta kundens konto.</span><span class="sxs-lookup"><span data-stu-id="f4d80-559">Optional: If you're setting up a customer-specific label design, you must create a query to find the customer's account.</span></span> <span data-ttu-id="f4d80-560">På snabbfliken **information om påfyllnadsetikettens mall** välj **Redigera fråga**.</span><span class="sxs-lookup"><span data-stu-id="f4d80-560">On the **Wave label template details** FastTab, select **Edit query**.</span></span> <span data-ttu-id="f4d80-561">I frågeredigerarens dialogruta, på fliken **Intervall** lägg till en rad med följande värden:</span><span class="sxs-lookup"><span data-stu-id="f4d80-561">Then, in the query editor dialog box, on the **Range** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="f4d80-562">**Register:** *försändelser*</span><span class="sxs-lookup"><span data-stu-id="f4d80-562">**Table:** *Shipments*</span></span>
    - <span data-ttu-id="f4d80-563">**Härlett register:** *försändelser*</span><span class="sxs-lookup"><span data-stu-id="f4d80-563">**Derived table:** *Shipments*</span></span>
    - <span data-ttu-id="f4d80-564">**Fält:** *Kontonummer*</span><span class="sxs-lookup"><span data-stu-id="f4d80-564">**Field:** *Account number*</span></span>
    - <span data-ttu-id="f4d80-565">**Kriterier:** Ange relevant kundkontonummer.</span><span class="sxs-lookup"><span data-stu-id="f4d80-565">**Criteria:** Enter the relevant customer account number.</span></span>

    <span data-ttu-id="f4d80-566">När du är klar klickar du på **OK** för att stänga dialogrutan för frågeredigeraren.</span><span class="sxs-lookup"><span data-stu-id="f4d80-566">When you've finished, select **OK** to close the query editor dialog box.</span></span>

1. <span data-ttu-id="f4d80-567">I åtgärdsfönstret, välj **Redigera fråga** för att öppna en dialogruta för frågeredigeraren för hela etikettmallen.</span><span class="sxs-lookup"><span data-stu-id="f4d80-567">On the Action Pane, select **Edit query** to open the query editor dialog box for the whole label template.</span></span>
1. <span data-ttu-id="f4d80-568">I frågeredigerarens dialogruta, på fliken **Sortera** lägg till en rad med följande värden:</span><span class="sxs-lookup"><span data-stu-id="f4d80-568">In the query editor dialog box, on the **Sorting** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="f4d80-569">**Tabell:** *Arbetsrader*</span><span class="sxs-lookup"><span data-stu-id="f4d80-569">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="f4d80-570">**Härlett register:** *Arbetsrader*</span><span class="sxs-lookup"><span data-stu-id="f4d80-570">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="f4d80-571">**Fält:** *referens till läs in rad-ID (post-ID)*</span><span class="sxs-lookup"><span data-stu-id="f4d80-571">**Field:** *Reference load line id (Record-ID)*</span></span>
    - <span data-ttu-id="f4d80-572">**Sökriktning:** *Stigande*</span><span class="sxs-lookup"><span data-stu-id="f4d80-572">**Search direction:** *Ascending*</span></span>

1. <span data-ttu-id="f4d80-573">Lägg till en andra rad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="f4d80-573">Add a second row that has the following settings:</span></span>

    - <span data-ttu-id="f4d80-574">**Tabell:** *Arbetsrader*</span><span class="sxs-lookup"><span data-stu-id="f4d80-574">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="f4d80-575">**Härlett register:** *Arbetsrader*</span><span class="sxs-lookup"><span data-stu-id="f4d80-575">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="f4d80-576">**Fält:** *leverans-ID*</span><span class="sxs-lookup"><span data-stu-id="f4d80-576">**Field:** *Shipment ID*</span></span>
    - <span data-ttu-id="f4d80-577">**Sökriktning:** *Stigande*</span><span class="sxs-lookup"><span data-stu-id="f4d80-577">**Search direction:** *Ascending*</span></span>

1. <span data-ttu-id="f4d80-578">Stäng dialogrutan för frågeredigeraren genom att välja **OK**.</span><span class="sxs-lookup"><span data-stu-id="f4d80-578">Select **OK** to close the query editor dialog box.</span></span>
1. <span data-ttu-id="f4d80-579">En meddelande ruta ber dig bekräfta åtgärden grupperingsåterställning.</span><span class="sxs-lookup"><span data-stu-id="f4d80-579">A message box prompts you to confirm the grouping reset operation.</span></span> <span data-ttu-id="f4d80-580">Klicka på **Ja** när du vill fortsätta.</span><span class="sxs-lookup"><span data-stu-id="f4d80-580">Select **Yes** to continue.</span></span>
1. <span data-ttu-id="f4d80-581">I åtgärdsfönstret, välj **mallgruppen för påfyllnadsetikett**.</span><span class="sxs-lookup"><span data-stu-id="f4d80-581">On the Action Pane, select **Wave label template group**.</span></span>
1. <span data-ttu-id="f4d80-582">I dialogrutan **mallgruppen för påfyllnadsetikett** för raden där fältet **Namn på referensfält** anges till *leverans-ID* anger du följande värden:</span><span class="sxs-lookup"><span data-stu-id="f4d80-582">In the **Wave label template group** dialog box, for the row where the **Reference field name** field is set to *Shipment ID*, set the following values:</span></span>

    - <span data-ttu-id="f4d80-583">**Skriv ut avbrottsetikett:** Markera den här kryssrutan.</span><span class="sxs-lookup"><span data-stu-id="f4d80-583">**Print break label:** Select this check box.</span></span>
    - <span data-ttu-id="f4d80-584">**Layout-ID för etikett:** Välj en avbrottsetikett.</span><span class="sxs-lookup"><span data-stu-id="f4d80-584">**Label layout ID:** Select a break label.</span></span> <span data-ttu-id="f4d80-585">(Välj t.ex. etikettlayouten *Avbrott* som du skapade tidigare i det här scenariot.)</span><span class="sxs-lookup"><span data-stu-id="f4d80-585">(For example, select the *Break* label layout that you created earlier in this scenario.)</span></span>
    - <span data-ttu-id="f4d80-586">**Skrivarnamn:** Välj skrivare för avbrottsetiketten.</span><span class="sxs-lookup"><span data-stu-id="f4d80-586">**Printer name:** Select the printer for the break label.</span></span> <span data-ttu-id="f4d80-587">(I syfte att dela upp etikettrullar bör du välja samma skrivare som väljs på snabbfliken **information om påfyllnadsetikettens mall**.</span><span class="sxs-lookup"><span data-stu-id="f4d80-587">(Typically, for the purpose of splitting label rolls, you should select the same printer that is selected on the **Wave label template details** FastTab.</span></span> <span data-ttu-id="f4d80-588">Andra scenarier är dock möjliga.)</span><span class="sxs-lookup"><span data-stu-id="f4d80-588">However, other scenarios are possible.)</span></span>

1. <span data-ttu-id="f4d80-589">Från raden där fältet **Namn på referensfält** anges till *referens till läs in rad-ID*, markera kryssrutan **etikettversions-ID**.</span><span class="sxs-lookup"><span data-stu-id="f4d80-589">For the row where the **Reference field name** field is set to *Reference load line id*, select the **Label build ID** check box.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f4d80-590">Med den här inställningen skapas en etikettserie ("kartong 1 av X") per lastrad i hela påfyllnaden, oavsett inställningen för arbetsgrupperingen.</span><span class="sxs-lookup"><span data-stu-id="f4d80-590">This setup will create one label sequence ("Carton 1 of X") per load line throughout the wave, regardless of the work grouping setup.</span></span> <span data-ttu-id="f4d80-591">Denna etikettserie kan skrivas ut på etikettlayouten.</span><span class="sxs-lookup"><span data-stu-id="f4d80-591">This label sequence can be printed on a label layout.</span></span> <span data-ttu-id="f4d80-592">Dessutom kommer etiketter för olika försändelser att åtskiljas med den valda avbrottsetiketten.</span><span class="sxs-lookup"><span data-stu-id="f4d80-592">Additionally, labels for different shipments will be separated by the selected break label.</span></span>

1. <span data-ttu-id="f4d80-593">Klicka på **OK** om du vill stänga dialogrutan **mallgruppen för påfyllnadsetikett**.</span><span class="sxs-lookup"><span data-stu-id="f4d80-593">Select **OK** to close the **Wave label template group** dialog box.</span></span>
1. <span data-ttu-id="f4d80-594">Skapa en andra etikettmall med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="f4d80-594">Create a second label template that has the following settings:</span></span>

    - <span data-ttu-id="f4d80-595">**Namn på etikettmallen:** *lastpalletiketter*</span><span class="sxs-lookup"><span data-stu-id="f4d80-595">**Label template name:** *Pallet labels*</span></span>
    - <span data-ttu-id="f4d80-596">**Beskrivning:** *lastpalletiketter*</span><span class="sxs-lookup"><span data-stu-id="f4d80-596">**Description:** *Pallet labels*</span></span>
    - <span data-ttu-id="f4d80-597">**Kod för påfyllnadssteg:** *lastpall*</span><span class="sxs-lookup"><span data-stu-id="f4d80-597">**Wave step code:** *Pallet*</span></span>
    - <span data-ttu-id="f4d80-598">**Lagerställe:** *62*</span><span class="sxs-lookup"><span data-stu-id="f4d80-598">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="f4d80-599">På snabbfliken **allmänna** i fältet **typ av påfyllnadsetikett** väljer du ett värde som *lastpall*.</span><span class="sxs-lookup"><span data-stu-id="f4d80-599">On the **General** FastTab, in the **Wave label type** field, select a value, such as *Pallet*.</span></span>
1. <span data-ttu-id="f4d80-600">På snabbfliken **information om påfyllnadsetikettens mall** och lägg till en rad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="f4d80-600">On the **Wave label template details** FastTab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="f4d80-601">**Etikettlayout-ID:** *lastpall*</span><span class="sxs-lookup"><span data-stu-id="f4d80-601">**Label layout ID:** *Pallet*</span></span>
    - <span data-ttu-id="f4d80-602">**Skrivarnamn:** Välj en lämplig ZPL-skrivare.</span><span class="sxs-lookup"><span data-stu-id="f4d80-602">**Printer name:** Select an appropriate ZPL printer.</span></span>
    - <span data-ttu-id="f4d80-603">**Kör fråga:** *Ja* (den här inställningen är valfri, men rekommenderas för optimal prestanda.)</span><span class="sxs-lookup"><span data-stu-id="f4d80-603">**Run query:** *Yes* (This setting is optional, but it's recommended for optimal performance.)</span></span>

1. <span data-ttu-id="f4d80-604">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="f4d80-604">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="f4d80-605">Valfritt: om du ställer in en kundspecifik etikettdesign måste du skapa en fråga för att hitta kundens konto.</span><span class="sxs-lookup"><span data-stu-id="f4d80-605">Optional: If you're setting up a customer-specific label design, you must create a query to find the customer's account.</span></span> <span data-ttu-id="f4d80-606">På snabbfliken **information om påfyllnadsetikettens mall** välj **Redigera fråga**.</span><span class="sxs-lookup"><span data-stu-id="f4d80-606">On the **Wave label template details** FastTab, select **Edit query**.</span></span> <span data-ttu-id="f4d80-607">I frågeredigerarens dialogruta, på fliken **Intervall** lägg till en rad med följande värden:</span><span class="sxs-lookup"><span data-stu-id="f4d80-607">Then, in the query editor dialog box, on the **Range** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="f4d80-608">**Register:** *försändelser*</span><span class="sxs-lookup"><span data-stu-id="f4d80-608">**Table:** *Shipments*</span></span>
    - <span data-ttu-id="f4d80-609">**Härlett register:** *försändelser*</span><span class="sxs-lookup"><span data-stu-id="f4d80-609">**Derived table:** *Shipments*</span></span>
    - <span data-ttu-id="f4d80-610">**Fält:** *Kontonummer*</span><span class="sxs-lookup"><span data-stu-id="f4d80-610">**Field:** *Account number*</span></span>
    - <span data-ttu-id="f4d80-611">**Kriterier:** Ange relevant kundkontonummer.</span><span class="sxs-lookup"><span data-stu-id="f4d80-611">**Criteria:** Enter the relevant customer account number.</span></span>

    <span data-ttu-id="f4d80-612">När du är klar klickar du på **OK** för att stänga dialogrutan för frågeredigeraren.</span><span class="sxs-lookup"><span data-stu-id="f4d80-612">When you've finished, select **OK** to close the query editor dialog box.</span></span> 

1. <span data-ttu-id="f4d80-613">I åtgärdsfönstret, välj **Redigera fråga** för att öppna en dialogruta för frågeredigeraren för hela etikettmallen.</span><span class="sxs-lookup"><span data-stu-id="f4d80-613">On the Action Pane, select **Edit query** to open the query editor dialog box for the whole label template.</span></span>
1. <span data-ttu-id="f4d80-614">I frågeredigerarens dialogruta, på fliken **Sortera** lägg till en rad med följande värden:</span><span class="sxs-lookup"><span data-stu-id="f4d80-614">In the query editor dialog box, on the **Sorting** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="f4d80-615">**Tabell:** *Arbetsrader*</span><span class="sxs-lookup"><span data-stu-id="f4d80-615">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="f4d80-616">**Härlett register:** *Arbetsrader*</span><span class="sxs-lookup"><span data-stu-id="f4d80-616">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="f4d80-617">**Fält:** *referens till läs in rad-ID (post-ID)*</span><span class="sxs-lookup"><span data-stu-id="f4d80-617">**Field:** *Reference load line id (Record-ID)*</span></span>
    - <span data-ttu-id="f4d80-618">**Sökriktning:** *Stigande*</span><span class="sxs-lookup"><span data-stu-id="f4d80-618">**Search direction:** *Ascending*</span></span>

1. <span data-ttu-id="f4d80-619">Lägg till en andra rad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="f4d80-619">Add a second row that has the following settings:</span></span>

    - <span data-ttu-id="f4d80-620">**Tabell:** *Arbetsrader*</span><span class="sxs-lookup"><span data-stu-id="f4d80-620">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="f4d80-621">**Härlett register:** *Arbetsrader*</span><span class="sxs-lookup"><span data-stu-id="f4d80-621">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="f4d80-622">**Fält:** *leverans-ID*</span><span class="sxs-lookup"><span data-stu-id="f4d80-622">**Field:** *Shipment ID*</span></span>
    - <span data-ttu-id="f4d80-623">**Sökriktning:** *Stigande*</span><span class="sxs-lookup"><span data-stu-id="f4d80-623">**Search direction:** *Ascending*</span></span>

1. <span data-ttu-id="f4d80-624">Stäng dialogrutan för frågeredigeraren genom att välja **OK**.</span><span class="sxs-lookup"><span data-stu-id="f4d80-624">Select **OK** to close the query editor dialog box.</span></span>
1. <span data-ttu-id="f4d80-625">En meddelande ruta ber dig bekräfta åtgärden grupperingsåterställning.</span><span class="sxs-lookup"><span data-stu-id="f4d80-625">A message box prompts you to confirm the grouping reset operation.</span></span> <span data-ttu-id="f4d80-626">Klicka på **Ja** när du vill fortsätta.</span><span class="sxs-lookup"><span data-stu-id="f4d80-626">Select **Yes** to continue.</span></span>
1. <span data-ttu-id="f4d80-627">I åtgärdsfönstret, välj **mallgruppen för påfyllnadsetikett**.</span><span class="sxs-lookup"><span data-stu-id="f4d80-627">On the Action Pane, select **Wave label template group**.</span></span>
1. <span data-ttu-id="f4d80-628">I dialogrutan **mallgruppen för påfyllnadsetikett** för raden där fältet **Namn på referensfält** anges till *leverans-ID* anger du följande värden:</span><span class="sxs-lookup"><span data-stu-id="f4d80-628">In the **Wave label template group** dialog box, for the row where the **Reference field name** field is set to *Shipment ID*, set the following values:</span></span>

    - <span data-ttu-id="f4d80-629">**Skriv ut avbrottsetikett:** Markera den här kryssrutan.</span><span class="sxs-lookup"><span data-stu-id="f4d80-629">**Print break label:** Select this check box.</span></span>
    - <span data-ttu-id="f4d80-630">**Layout-ID för etikett:** Välj en avbrottsetikett.</span><span class="sxs-lookup"><span data-stu-id="f4d80-630">**Label layout ID:** Select a break label.</span></span> <span data-ttu-id="f4d80-631">(Välj t.ex. etikettlayouten *Avbrott* som du skapade tidigare i det här scenariot.)</span><span class="sxs-lookup"><span data-stu-id="f4d80-631">(For example, select the *Break* label layout that you created earlier in this scenario.)</span></span>
    - <span data-ttu-id="f4d80-632">**Skrivarnamn:** Välj skrivare för avbrottsetiketten.</span><span class="sxs-lookup"><span data-stu-id="f4d80-632">**Printer name:** Select the printer for the break label.</span></span> <span data-ttu-id="f4d80-633">(I syfte att dela upp etikettrullar bör du välja samma skrivare som väljs på snabbfliken **information om påfyllnadsetikettens mall**.</span><span class="sxs-lookup"><span data-stu-id="f4d80-633">(Typically, for the purpose of splitting label rolls, you should select the same printer that is selected on the **Wave label template details** FastTab.</span></span> <span data-ttu-id="f4d80-634">Andra scenarier är dock möjliga.)</span><span class="sxs-lookup"><span data-stu-id="f4d80-634">However, other scenarios are possible.)</span></span>

1. <span data-ttu-id="f4d80-635">Från raden där fältet **Namn på referensfält** anges till *referens till läs in rad-ID*, markera kryssrutan **etikettversions-ID**.</span><span class="sxs-lookup"><span data-stu-id="f4d80-635">For the row where the **Reference field name** field is set to *Reference load line id*, select the **Label build ID** check box.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f4d80-636">Med den här inställningen skapas en etikettserie ("kartong 1 av X") per lastrad i hela påfyllnaden, oavsett inställningen för arbetsgrupperingen.</span><span class="sxs-lookup"><span data-stu-id="f4d80-636">This setup will create one label sequence ("Carton 1 of X") per load line throughout the wave, regardless of the work grouping setup.</span></span> <span data-ttu-id="f4d80-637">Denna etikettserie kan skrivas ut på etikettlayouten.</span><span class="sxs-lookup"><span data-stu-id="f4d80-637">This label sequence can be printed on a label layout.</span></span> <span data-ttu-id="f4d80-638">Dessutom kommer etiketter för olika försändelser att åtskiljas med den valda avbrottsetiketten.</span><span class="sxs-lookup"><span data-stu-id="f4d80-638">Additionally, labels for different shipments will be separated by the selected break label.</span></span>

### <a name="configure-number-sequence-extensions"></a><span data-ttu-id="f4d80-639">Konfigurera nummerserietillägg</span><span class="sxs-lookup"><span data-stu-id="f4d80-639">Configure number sequence extensions</span></span>

<span data-ttu-id="f4d80-640">Nummerserietillägg styr GS1 efterlevnaden av specifika nummerserier.</span><span class="sxs-lookup"><span data-stu-id="f4d80-640">Number sequence extensions control the GS1 compliance of specific number sequences.</span></span> <span data-ttu-id="f4d80-641">Den här konfigurationen är valfri för det aktuella scenariot.</span><span class="sxs-lookup"><span data-stu-id="f4d80-641">This configuration is optional for the current scenario.</span></span> <span data-ttu-id="f4d80-642">Mer information och instruktioner för konfigurering finns i [Konfigurera tillägg för nummerserier](../warehousing/configure-number-sequence-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="f4d80-642">For more information and configuration instructions, see [Configure number sequence extensions](../warehousing/configure-number-sequence-extensions.md).</span></span>

### <a name="create-a-sales-order-and-release-it-to-the-warehouse"></a><span data-ttu-id="f4d80-643">Skapa en försäljningsorder och släpp den på lagerstället</span><span class="sxs-lookup"><span data-stu-id="f4d80-643">Create a sales order and release it to the warehouse</span></span>

1. <span data-ttu-id="f4d80-644">Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="f4d80-644">Go to **Sales and marketing \> Sales order \> All sales orders**.</span></span>
1. <span data-ttu-id="f4d80-645">Skapa en försäljningsorder med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="f4d80-645">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="f4d80-646">**Kundkonto:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="f4d80-646">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="f4d80-647">**Lagerställe:** *62*</span><span class="sxs-lookup"><span data-stu-id="f4d80-647">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="f4d80-648">Lägg till två försäljningsorderrader:</span><span class="sxs-lookup"><span data-stu-id="f4d80-648">Add two sales order lines:</span></span>

    - <span data-ttu-id="f4d80-649">Försäljningsorderrad 1:</span><span class="sxs-lookup"><span data-stu-id="f4d80-649">Sales order line 1:</span></span>

        - <span data-ttu-id="f4d80-650">**Artikelnummer:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="f4d80-650">**Item number:** *A0001*</span></span>
        - <span data-ttu-id="f4d80-651">**Kvantitet:** *9024*</span><span class="sxs-lookup"><span data-stu-id="f4d80-651">**Quantity:** *9024*</span></span>
        - <span data-ttu-id="f4d80-652">**Enhet:** *ea* (9024 ea = 376 låda = 47 PL)</span><span class="sxs-lookup"><span data-stu-id="f4d80-652">**Unit:** *ea* (9024 ea = 376 Box = 47 PL)</span></span>

    - <span data-ttu-id="f4d80-653">Försäljningsorderrad 2:</span><span class="sxs-lookup"><span data-stu-id="f4d80-653">Sales order line 2:</span></span>

        - <span data-ttu-id="f4d80-654">**Artikelnummer:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="f4d80-654">**Item number:** *A0002*</span></span>
        - <span data-ttu-id="f4d80-655">**Kvantitet:** *9016*</span><span class="sxs-lookup"><span data-stu-id="f4d80-655">**Quantity:** *9016*</span></span>
        - <span data-ttu-id="f4d80-656">**Enhet:** *ea* (9016 ea = 322 box = 46 PL)</span><span class="sxs-lookup"><span data-stu-id="f4d80-656">**Unit:** *ea* (9016 ea = 322 Box = 46 PL)</span></span>

    > [!NOTE]
    > <span data-ttu-id="f4d80-657">Artiklarna och kvantiteterna som anges här är endast exempel.</span><span class="sxs-lookup"><span data-stu-id="f4d80-657">The items and quantities that are provided here are only examples.</span></span> <span data-ttu-id="f4d80-658">De måste använda den enhetsseriegrupp som du definierade tidigare, och lämpliga enhetskonverteringar från *ea* till *Box* till *PL* måste definieras för dem och de måste ha lager i lagerställe *62*.</span><span class="sxs-lookup"><span data-stu-id="f4d80-658">They must use the unit sequence group that you defined earlier, appropriate unit conversions from *ea* to *Box* to *PL* must be defined for them, and they must have stock in warehouse *62*.</span></span> <span data-ttu-id="f4d80-659">Mer information finns i [måttenhet och lagerprinciper](unit-measure-stocking-policies.md).</span><span class="sxs-lookup"><span data-stu-id="f4d80-659">For more information, see [Unit of measure and stocking policies](unit-measure-stocking-policies.md).</span></span>

1. <span data-ttu-id="f4d80-660">Välj försäljningsorderrad 1.</span><span class="sxs-lookup"><span data-stu-id="f4d80-660">Select sales order line 1.</span></span> <span data-ttu-id="f4d80-661">I avsnittet **Försäljningsorderrad** i menyn **Lager** välj **Reservationer**.</span><span class="sxs-lookup"><span data-stu-id="f4d80-661">Then, in the **Sales order line** section, on the **Inventory** menu, select **Reservations**.</span></span>
1. <span data-ttu-id="f4d80-662">På sidan **Reservation** i åtgärdsfönstret, välj **Reservera parti** och stäng sedan sidan.</span><span class="sxs-lookup"><span data-stu-id="f4d80-662">On the **Reservation** page, on the Action Pane, select **Reserve lot**, and then close the page.</span></span>
1. <span data-ttu-id="f4d80-663">Upprepa steg 4 och 5 för försäljningsorderrad 2.</span><span class="sxs-lookup"><span data-stu-id="f4d80-663">Repeat steps 4 and 5 for sales order line 2.</span></span>
1. <span data-ttu-id="f4d80-664">I åtgärdsfönstret på fliken **Lagerställe** välj **Frisläpp till regel för lagerställe**.</span><span class="sxs-lookup"><span data-stu-id="f4d80-664">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="f4d80-665">Då inträffar följande händelser:</span><span class="sxs-lookup"><span data-stu-id="f4d80-665">The following events occur:</span></span> 

    - <span data-ttu-id="f4d80-666">I systemet bearbetas den skapade utleveransen med hjälp av mallen som inkluderar utskriftssteget för etikett.</span><span class="sxs-lookup"><span data-stu-id="f4d80-666">The system processes the created shipment by using the template that includes the label printing step.</span></span> <span data-ttu-id="f4d80-667">Etikettlayouten används för att definiera etikettens format, och resultatet blir en etikett som skrivs ut på den skrivare som väljs i etikettmallen.</span><span class="sxs-lookup"><span data-stu-id="f4d80-667">The label layout will be used to define the format of the label, and the result will be a label that is printed on the printer that is selected in the label template.</span></span>
    - <span data-ttu-id="f4d80-668">Påfyllnadsetiketter genereras och skrivs ut.</span><span class="sxs-lookup"><span data-stu-id="f4d80-668">Wave labels are generated and printed.</span></span> <span data-ttu-id="f4d80-669">Antalet etiketter är lika med antalet kartonger (i det här exemplet är 376 boxetiketter för rad 1, 322 boxetiketter för rad 2, 47 PL-etiketter för rad 1, 47 PL-etiketter för rad 2 och två avbrottsetiketter med leverans-ID).</span><span class="sxs-lookup"><span data-stu-id="f4d80-669">The number of labels will equal the number of cartons (in this example, 376 Box labels for line 1, 322 Box labels for line 2, 47 PL labels for line 1, 47 PL labels for line 2, and two break labels that have the shipment ID).</span></span>
    - <span data-ttu-id="f4d80-670">Ett nytt fraktsedels-ID genereras för leveranserna.</span><span class="sxs-lookup"><span data-stu-id="f4d80-670">A new bill of lading ID is generated for the shipments.</span></span> <span data-ttu-id="f4d80-671">Om du har konfigurerat nummerserietilläggen följer påfyllnadsetikett-ID nummerformatet **SSCC-18**.</span><span class="sxs-lookup"><span data-stu-id="f4d80-671">If you configured the number sequence extensions, the wave label IDs will follow the **SSCC-18** number format.</span></span> 

<span data-ttu-id="f4d80-672">Du kan visa och skriva ut påfyllnadsetiketter på följande sidor:</span><span class="sxs-lookup"><span data-stu-id="f4d80-672">You can view and reprint wave labels from the following pages:</span></span>

- <span data-ttu-id="f4d80-673">Alla leveranser \> leveransinformation</span><span class="sxs-lookup"><span data-stu-id="f4d80-673">All shipments \> Shipment details</span></span>
- <span data-ttu-id="f4d80-674">Alla laster \> Läs in information</span><span class="sxs-lookup"><span data-stu-id="f4d80-674">All loads \> Load details</span></span>
- <span data-ttu-id="f4d80-675">Alla påfyllnader</span><span class="sxs-lookup"><span data-stu-id="f4d80-675">All waves</span></span>
- <span data-ttu-id="f4d80-676">Påfyllnadsetiketter</span><span class="sxs-lookup"><span data-stu-id="f4d80-676">Wave labels</span></span>
- <span data-ttu-id="f4d80-677">Etiketthistorik för påfyllnad</span><span class="sxs-lookup"><span data-stu-id="f4d80-677">Wave label history</span></span>

<span data-ttu-id="f4d80-678">För de flesta av dessa sidor hittar du den relevanta funktionen genom att välja **Påfyllnadsetiketter** i gruppen **Relaterad information** i fliken **leveranser** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="f4d80-678">For most of these pages, you can find the relevant function by selecting **Wave labels** in the **Related information** group on the **Shipments** tab of the Action Pane.</span></span>
