---
title: Ställa in och använda utskrift av påfyllnadsetikett
description: Det här ämnet beskriver utskrift av påfyllnadsetikett och förklarar hur du ställer in det.
author: GarmMSFT
manager: PJacobse
ms.date: 05/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWaveLabel, WHSWaveLabelTemplate, WHSWaveLabelLayoutRow, WHSDocumentRouting, WHSWaveTableListPage, WHSPostMethod, WHSMobileDisplayWaveLabelListLookup, WHSWaveLabelType, WHSWaveLabelTemplateGroup, WHSDocumentRoutingLayout
audience: Application User
ms.reviewer: PJacobse
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: yyyy-mm-dd
ms.dyn365.ops.version: 10.0.0
ms.openlocfilehash: a08f10c1f5c3ff5b9023f37614c4e113b3a6b30d
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5211776"
---
# <a name="set-up-and-use-wave-label-printing"></a><span data-ttu-id="662f5-103">Ställa in och använda utskrift av påfyllnadsetikett</span><span class="sxs-lookup"><span data-stu-id="662f5-103">Set up and use wave label printing</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="662f5-104">Utskrift av påfyllnadsetikett ger en alternativ metod för att skriva ut etiketter genom att introducera en ny påfyllnadsmetod som gör att du kan skapa och skriva ut etiketter direkt från påfyllnadsmallen under påfyllnadskörningen.</span><span class="sxs-lookup"><span data-stu-id="662f5-104">Wave label printing offers an alternative approach to label printing by introducing a new wave step method that lets you create and print labels directly from the wave template during wave execution.</span></span> <span data-ttu-id="662f5-105">Därför är etiketterna redan tillgängliga innan arbetare kör arbetsordern på en mobil enhet.</span><span class="sxs-lookup"><span data-stu-id="662f5-105">Therefore, the labels will already be available before workers run the work order on a mobile device.</span></span> <span data-ttu-id="662f5-106">Arbetare kan sedan koppla de begärda etiketterna under plockning i stället för efter plockning.</span><span class="sxs-lookup"><span data-stu-id="662f5-106">Workers can then attach the required labels during picking instead of after picking.</span></span>

<span data-ttu-id="662f5-107">Utskrift av påfyllnadsetikett använder zebraprogrammeringspråket (ZPL) när du skapar etikettlayout.</span><span class="sxs-lookup"><span data-stu-id="662f5-107">Wave label printing uses Zebra Programming Language (ZPL) to create label layouts.</span></span> <span data-ttu-id="662f5-108">En etikettlayout är uppdelad i tre avsnitt (rubrik, brödtext och sidfot) som tillåter etiketter som har en upprepande struktur.</span><span class="sxs-lookup"><span data-stu-id="662f5-108">A label layout is divided into three sections (header, body, and footer) to allow for labels that have repeating structure.</span></span> <span data-ttu-id="662f5-109">Mallar för etikettutskrift anger du vilket system som etikettexten ska använda.</span><span class="sxs-lookup"><span data-stu-id="662f5-109">Wave label templates tell the system which label layout to use.</span></span> <span data-ttu-id="662f5-110">Användare kan ange vilken skrivare som ska användas.</span><span class="sxs-lookup"><span data-stu-id="662f5-110">Users can specify which printer is used.</span></span> <span data-ttu-id="662f5-111">De kan också skriva ut etiketter på flera skrivare samtidigt, eftersom de kräver det.</span><span class="sxs-lookup"><span data-stu-id="662f5-111">They can also print labels on several printers at the same time, as they require.</span></span> <span data-ttu-id="662f5-112">Sidan **påfyllnadsetiketthistoriken** visar en post över alla etiketter som har skapats med hjälp av den här inställningen.</span><span class="sxs-lookup"><span data-stu-id="662f5-112">The **Wave label history** page shows a record of all labels that have been created by using this setup.</span></span>

<span data-ttu-id="662f5-113">Du kan skriva ut och sortera etiketter baserat på arbetsrubriker, du kan skriva ut avbrottsetiketter per arbetsrubrik och du kan skriva ut behållarens innehållsetiketter, ärendeetiketter och andra liknande etiketter.</span><span class="sxs-lookup"><span data-stu-id="662f5-113">You can print and collate labels based on work headers, you can print break labels per work header, and you can print container content labels, case labels, and other similar labels.</span></span>

> [!NOTE]
> <span data-ttu-id="662f5-114">Den här funktionen ersätter inte de befintliga funktionerna för etikettutskrift som baseras på dokumentflödet.</span><span class="sxs-lookup"><span data-stu-id="662f5-114">This functionality doesn't replace existing label printing functionality that is based on document routing.</span></span>

<span data-ttu-id="662f5-115">Utskrift av påfyllnadsetikett ger följande förbättringar:</span><span class="sxs-lookup"><span data-stu-id="662f5-115">Wave label printing offers the following enhancements:</span></span>

- <span data-ttu-id="662f5-116">Skriv ut etiketter enligt antalet kartonger på en enda arbetsrad, utan att använda skapande av behållare.</span><span class="sxs-lookup"><span data-stu-id="662f5-116">Print labels according to the number of cartons on a single work line, without using containerization.</span></span> <span data-ttu-id="662f5-117">(En "kartong" är en enhet som har angetts för enhetssekvensgruppraderna.)</span><span class="sxs-lookup"><span data-stu-id="662f5-117">(A "carton" is a unit that is designated on unit sequence group lines.)</span></span>
- <span data-ttu-id="662f5-118">Skriv ut flera olika etikettserier (t.ex. kartonger och lastpallsetiketter).</span><span class="sxs-lookup"><span data-stu-id="662f5-118">Print several different label sequences (for example, carton and pallet labels).</span></span>
- <span data-ttu-id="662f5-119">Inkludera etikettuppräkning (t.ex. 1/124, 2/124... 124/124) och definiera intervallet för uppräkningen (t.ex. arbetsrad, lastrad eller leverans).</span><span class="sxs-lookup"><span data-stu-id="662f5-119">Include label enumeration (for example, 1/124, 2/124, ... 124/124), and define the range of enumeration (for example, work line, load line, or shipment).</span></span>
- <span data-ttu-id="662f5-120">Skapa och skriv ut ett fraktsedels-ID på etiketter innan fraktsedeln genereras.</span><span class="sxs-lookup"><span data-stu-id="662f5-120">Create and print a bill of lading ID on labels before the bill of lading is generated.</span></span>
- <span data-ttu-id="662f5-121">Skapa en unik serie för seriell leveransbehållare (SSCC) för varje kartong och inkludera den på varje etikett.</span><span class="sxs-lookup"><span data-stu-id="662f5-121">Create a unique serial shipping container code (SSCC) for each carton, and include it on each label.</span></span>
- <span data-ttu-id="662f5-122">Skapa GS1-kompatibla nummerserier för fraktsedels-ID och SSCC.</span><span class="sxs-lookup"><span data-stu-id="662f5-122">Create GS1-compliant number sequences for bill of lading IDs and SSCCs.</span></span>
- <span data-ttu-id="662f5-123">Skriv ut etiketterna på både mobila enheter och den avancerade klienten.</span><span class="sxs-lookup"><span data-stu-id="662f5-123">Reprint labels from both mobile devices and the rich client.</span></span>
- <span data-ttu-id="662f5-124">Annullera etiketter (t.ex. i korta plockningsscenarier) och skriv ut dem igen.</span><span class="sxs-lookup"><span data-stu-id="662f5-124">Void labels (for example, in short pick scenarios), and reprint them.</span></span>
- <span data-ttu-id="662f5-125">Rensa historik för påfyllnadsetikett.</span><span class="sxs-lookup"><span data-stu-id="662f5-125">Clean up the wave label history.</span></span>
- <span data-ttu-id="662f5-126">Förbättringar av layouter av dokumentflöde delas mellan dokumentflödets layout och påfyllnadsetikettens layout.</span><span class="sxs-lookup"><span data-stu-id="662f5-126">Improvements to document routing layouts are shared between document routing layouts and wave label layouts.</span></span> <span data-ttu-id="662f5-127">(Mer information finns i [Layout för dokumentflöde för ID-nummer](../warehousing/document-routing-layout-for-license-plates.md) .)</span><span class="sxs-lookup"><span data-stu-id="662f5-127">(For more information, see [Document routing layout for license plates](../warehousing/document-routing-layout-for-license-plates.md).)</span></span>

<span data-ttu-id="662f5-128">Dessa förbättringar gör det effektivare att märka kartonger före palletering.</span><span class="sxs-lookup"><span data-stu-id="662f5-128">These enhancements make it more efficient to label cartons before palletization.</span></span> <span data-ttu-id="662f5-129">De gynnar främst företag som levererar till stora återförsäljare som automatiskt bekräftar orderkvitton genom att söka igenom varje kartong separat.</span><span class="sxs-lookup"><span data-stu-id="662f5-129">They especially benefit companies that ship to large retailers that automatically confirm order receipts by scanning each carton separately.</span></span>

> [!NOTE]
> <span data-ttu-id="662f5-130">Du kan implementera konfigurationsscenarier som beskrivs i det här avsnittet, antingen separat eller i kombination, beroende på dina affärsbehov.</span><span class="sxs-lookup"><span data-stu-id="662f5-130">You can implement the configuration scenarios that are described in this topic either separately or in combination, depending on your business requirements.</span></span> <span data-ttu-id="662f5-131">Du kan skapa flera påfyllnadsetikettmallar som fungerar i ordningsföljd (som illustreras i scenario 3).</span><span class="sxs-lookup"><span data-stu-id="662f5-131">You can design several wave label templates that work in sequence (as illustrated in scenario 3).</span></span> <span data-ttu-id="662f5-132">Du kan till exempel använda scenario 1 för att skriva ut kartonger och scenario 2 om du vill skriva ut lastpallsetiketter (om lastpallar i lagret varierar i storlek och sammansättning).</span><span class="sxs-lookup"><span data-stu-id="662f5-132">For example, you can use scenario 1 to print carton labels and scenario 2 to print pallet labels (if pallets in stock vary in size and composition).</span></span>

## <a name="turn-on-the-wave-label-printing-feature"></a><span data-ttu-id="662f5-133">Aktivera funktionen utskrift av påfyllnadsetiketter</span><span class="sxs-lookup"><span data-stu-id="662f5-133">Turn on the Wave label printing feature</span></span>

<span data-ttu-id="662f5-134">Innan du kan använda funktionen *utskrift av påfyllnadsmall* den aktiveras i ditt system.</span><span class="sxs-lookup"><span data-stu-id="662f5-134">Before you can use the *Wave label printing* feature, it must be turned on in your system.</span></span> <span data-ttu-id="662f5-135">Administratörer kan använda arbetsytan [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den om det behövs.</span><span class="sxs-lookup"><span data-stu-id="662f5-135">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="662f5-136">Funktionen visas på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="662f5-136">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="662f5-137">**Modul:** *Lagerstyrning*</span><span class="sxs-lookup"><span data-stu-id="662f5-137">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="662f5-138">**Funktionsnamn:** *utskrift av påfyllnadsetiketter*</span><span class="sxs-lookup"><span data-stu-id="662f5-138">**Feature name:** *Wave label printing*</span></span>

## <a name="scenario-1-wave-label-printing-where-a-single-wave-label-is-generated"></a><span data-ttu-id="662f5-139">Scenario 1: utskrift av påfyllnadsetiketter där en enskild påfyllnadsetikett genereras</span><span class="sxs-lookup"><span data-stu-id="662f5-139">Scenario 1: Wave label printing where a single wave label is generated</span></span>

<span data-ttu-id="662f5-140">Det här scenariot visar hur ett företag kan skriva ut leveransetiketter för en stor återförsäljare som automatiskt bekräftar orderkvitton genom att söka igenom varje kartong separat.</span><span class="sxs-lookup"><span data-stu-id="662f5-140">This scenario shows how a company can print shipping labels for a large retailer that automatically confirms order receipts by scanning each carton separately.</span></span>

<span data-ttu-id="662f5-141">Det här scenariot visar komplett flöde.</span><span class="sxs-lookup"><span data-stu-id="662f5-141">This scenario shows the end-to-end flow.</span></span>

### <a name="make-demo-data-available"></a><span data-ttu-id="662f5-142">Gör demodata tillgängliga</span><span class="sxs-lookup"><span data-stu-id="662f5-142">Make demo data available</span></span>

<span data-ttu-id="662f5-143">För att följa detta scenario måste du ha demonstrationsdata installerad och du måste välja juridiska personen **USMF**.</span><span class="sxs-lookup"><span data-stu-id="662f5-143">To follow this scenario, you must have demo data installed, and you must select the **USMF** legal entity.</span></span>

### <a name="make-sure-that-the-wave-label-method-is-available"></a><span data-ttu-id="662f5-144">Kontrollera att påfyllnadsetikett metoden är tillgänglig</span><span class="sxs-lookup"><span data-stu-id="662f5-144">Make sure that the wave label method is available</span></span>

<span data-ttu-id="662f5-145">Du måste kanske återskapa dina metoder för påfyllnadsprocess för att göra påfyllnadsetikett metoden tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="662f5-145">You might have to regenerate the wave process methods to make the wave label printing method available.</span></span>

1. <span data-ttu-id="662f5-146">Gå till **Lagerstyrning \> Inställningar \> Påfyllnader \> Metoder för påfyllnadsprocess**.</span><span class="sxs-lookup"><span data-stu-id="662f5-146">Go to **Warehouse management \> Setup \> Waves \> Wave process methods**.</span></span>
1. <span data-ttu-id="662f5-147">Kontrollera att **waveLabelPrinting** finns i listan.</span><span class="sxs-lookup"><span data-stu-id="662f5-147">Confirm that **waveLabelPrinting** is in the list.</span></span> <span data-ttu-id="662f5-148">Om den inte finns med väljer du **återskapa metoder** i åtgärdsfönstret för att lägga till den.</span><span class="sxs-lookup"><span data-stu-id="662f5-148">If it isn't, select **Regenerate methods** on the Action Pane to add it.</span></span>

### <a name="configure-a-wave-template"></a><span data-ttu-id="662f5-149">Konfigurera en påfyllnadsmall</span><span class="sxs-lookup"><span data-stu-id="662f5-149">Configure a wave template</span></span>

<span data-ttu-id="662f5-150">Med påfyllnadsmallar kan du länka specifika förekomster av påfyllnadsmetoder till en motsvarande påfyllnadsetikettsmall.</span><span class="sxs-lookup"><span data-stu-id="662f5-150">Wave templates let you link specific instances of wave methods to a corresponding wave label template.</span></span>

1. <span data-ttu-id="662f5-151">Gå till **Lagerstyrning \> Inställningar \> Påfyllnader \> Påfyllnadsmallar**.</span><span class="sxs-lookup"><span data-stu-id="662f5-151">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
1. <span data-ttu-id="662f5-152">Välj en mall som **62 standard för leverans**.</span><span class="sxs-lookup"><span data-stu-id="662f5-152">Select a template, such as **62 Shipping Default**.</span></span>
1. <span data-ttu-id="662f5-153">På snabbfliken **metoder** flyttar du metoden **utskrift av påfyllnadsetiketter** till kolumnen **valda metoder**.</span><span class="sxs-lookup"><span data-stu-id="662f5-153">On the **Methods** FastTab, move the **Wave label printing** method to the **Selected methods** column.</span></span>
1. <span data-ttu-id="662f5-154">I kolumnen **Valda metoder** välj metoden **Utskrift av påfyllnadsetiketter** och ange dess fält **Kod för påfyllnadssteg** till *PrintLabel*.</span><span class="sxs-lookup"><span data-stu-id="662f5-154">In the **Selected methods** column, select the **Wave label printing** method, and set its **Wave step code** field to *PrintLabel*.</span></span> <span data-ttu-id="662f5-155">För mer information om koder för påfyllnadssteg, se [Koder för påfyllnadssteg](wave-step-codes.md).</span><span class="sxs-lookup"><span data-stu-id="662f5-155">For more information about wave step codes, see [Wave step codes](wave-step-codes.md).</span></span>

### <a name="create-a-wave-label-layout"></a><span data-ttu-id="662f5-156">Skapa en layout för påfyllnadsetiketten</span><span class="sxs-lookup"><span data-stu-id="662f5-156">Create a wave label layout</span></span>

<span data-ttu-id="662f5-157">Etikettlayouten bestämmer vilken information som ska skrivas ut på etiketten och hur den visas. Här anger du koden för ZPL som skickas till skrivaren.</span><span class="sxs-lookup"><span data-stu-id="662f5-157">The label layout controls what information is printed on the label and how it's laid out. Here, you enter the ZPL code that is sent to the printer.</span></span>

1. <span data-ttu-id="662f5-158">Gå till **Lagerstyrning \> Inställningar \> Dokumentflöde \> Layout för påfyllnadsetikett**.</span><span class="sxs-lookup"><span data-stu-id="662f5-158">Go to **Warehouse management \> Setup \> Document routing \> Wave label layouts**.</span></span>
1. <span data-ttu-id="662f5-159">Skapa en post med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="662f5-159">Create a record that has the following settings:</span></span>

    - <span data-ttu-id="662f5-160">**Etikettlayout-ID:** *kartong*</span><span class="sxs-lookup"><span data-stu-id="662f5-160">**Label layout ID:** *Carton*</span></span>
    - <span data-ttu-id="662f5-161">**Beskrivning:** *kartong (SSCC)*</span><span class="sxs-lookup"><span data-stu-id="662f5-161">**Description:** *Carton (SSCC)*</span></span>

1. <span data-ttu-id="662f5-162">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="662f5-162">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="662f5-163">I åtgärdsfönstret, välj **Inställningar för påfyllnadsetikettrad**.</span><span class="sxs-lookup"><span data-stu-id="662f5-163">On the Action Pane, select **Wave label row settings**.</span></span>

    <span data-ttu-id="662f5-164">Sidan **Inställningar för påfyllnadsetikettrad** visas.</span><span class="sxs-lookup"><span data-stu-id="662f5-164">The **Wave label row settings** page appears.</span></span> <span data-ttu-id="662f5-165">Här kan du konfigurera den dynamiska delen av etiketten.</span><span class="sxs-lookup"><span data-stu-id="662f5-165">Here, you can configure the dynamic part of the label.</span></span>

1. <span data-ttu-id="662f5-166">Lägg till en rad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="662f5-166">Add a row that has the following settings:</span></span>

    - <span data-ttu-id="662f5-167">**Rad-ID:** *WaveLabel*</span><span class="sxs-lookup"><span data-stu-id="662f5-167">**Row Id:** *WaveLabel*</span></span>
    - <span data-ttu-id="662f5-168">**Radtabellnamn:** *WHSWaveLabel*</span><span class="sxs-lookup"><span data-stu-id="662f5-168">**Row table name:** *WHSWaveLabel*</span></span>
    - <span data-ttu-id="662f5-169">**Radens startposition:** *0*</span><span class="sxs-lookup"><span data-stu-id="662f5-169">**Row start position:** *0*</span></span>

        <span data-ttu-id="662f5-170">I det här fältet definieras den lodräta position där raden ska börja etiketten.</span><span class="sxs-lookup"><span data-stu-id="662f5-170">This field defines the vertical position where the row will begin on the label.</span></span>

    - <span data-ttu-id="662f5-171">**Radhöjd:** *0*</span><span class="sxs-lookup"><span data-stu-id="662f5-171">**Row height:** *0*</span></span>

        <span data-ttu-id="662f5-172">I det här fältet definieras höjden på varje rad (i punkter) enligt ZPL-standard.</span><span class="sxs-lookup"><span data-stu-id="662f5-172">This field defines the height of each row (in points), according to the ZPL standard.</span></span> <span data-ttu-id="662f5-173">Radhöjden är positiv för vågräta etiketter och är negativ för lodräta etiketter.</span><span class="sxs-lookup"><span data-stu-id="662f5-173">The row height is positive for horizontal labels and negative for vertical labels.</span></span> <span data-ttu-id="662f5-174">Eftersom det bara finns en rad i det här exemplet kan du ställa in värdet på *0* (noll).</span><span class="sxs-lookup"><span data-stu-id="662f5-174">Because there is just one row in this example, you can set the value to *0* (zero).</span></span>

    - <span data-ttu-id="662f5-175">**Rader per sida:** *1*</span><span class="sxs-lookup"><span data-stu-id="662f5-175">**Rows per page:** *1*</span></span>

        <span data-ttu-id="662f5-176">I det här fältet definieras antalet rader som kan skrivas ut på varje etikett.</span><span class="sxs-lookup"><span data-stu-id="662f5-176">This field defines the number of rows that can be printed on each label.</span></span>

        > [!NOTE]
        > <span data-ttu-id="662f5-177">Den här inställningen gör att en separat ZPL-etikett skrivs ut för varje post i tabellen med påfyllnadsetiketter.</span><span class="sxs-lookup"><span data-stu-id="662f5-177">This setup will cause a separate ZPL label to be printed for each record in the wave labels table.</span></span>

1. <span data-ttu-id="662f5-178">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="662f5-178">Close the page.</span></span>
1. <span data-ttu-id="662f5-179">I åtgärdsfönstret väljer du **Redigera fråga**.</span><span class="sxs-lookup"><span data-stu-id="662f5-179">On the Action Pane, select **Edit query**.</span></span>
1. <span data-ttu-id="662f5-180">I frågeredigerarens dialogruta, på fliken **Intervall** lägg till en rad med följande värden:</span><span class="sxs-lookup"><span data-stu-id="662f5-180">In the query editor dialog box, on the **Range** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="662f5-181">**Tabell:** *Arbetsrader*</span><span class="sxs-lookup"><span data-stu-id="662f5-181">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="662f5-182">**Härlett register:** *Arbetsrader*</span><span class="sxs-lookup"><span data-stu-id="662f5-182">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="662f5-183">**Fält:** *arbetstyp*</span><span class="sxs-lookup"><span data-stu-id="662f5-183">**Field:** *Work type*</span></span>
    - <span data-ttu-id="662f5-184">**Kriterier:** *Plocka*</span><span class="sxs-lookup"><span data-stu-id="662f5-184">**Criteria:** *Pick*</span></span>

    <span data-ttu-id="662f5-185">Den här frågan ser till att endast arbetsrader av typen plockning skrivs ut på etiketten, inte artikelrader av typen radtyp.</span><span class="sxs-lookup"><span data-stu-id="662f5-185">This query ensures that only pick-type work lines will be printed on the label, not put-type work lines.</span></span>

1. <span data-ttu-id="662f5-186">Om du vill kunna skriva ut fraktsedels-ID väljer du på fliken **kopplingar**, sedan **arbetsrader** och kopplar tabellen **leveranser** till den.</span><span class="sxs-lookup"><span data-stu-id="662f5-186">If you want to be able to print the bill of lading ID, on the **Joins** tab, select the **Work lines** table, and join the **Shipments** table to it.</span></span>
1. <span data-ttu-id="662f5-187">Stäng dialogrutan frågeredigeraren.</span><span class="sxs-lookup"><span data-stu-id="662f5-187">Close the query editor dialog box.</span></span>
1. <span data-ttu-id="662f5-188">På snabbfliken **Layout för skrivartext** finns tre avsnitt där du kan skriva skrivarkod: **rubrikavsnitt**, **brödtext** och **sidfotsavsnitt**.</span><span class="sxs-lookup"><span data-stu-id="662f5-188">The **Printer text Layout** FastTab has three sections where you can write printer code: **Header section**, **Body section**, and **Footer section**.</span></span> <span data-ttu-id="662f5-189">I avsnittet **rubrikavsnitt** i fältet **etikettrubrik** anger du koden för önskad rubrik.</span><span class="sxs-lookup"><span data-stu-id="662f5-189">In the **Header section** section, in the **Label header** field, enter code for the required header.</span></span> <span data-ttu-id="662f5-190">Om du till exempel använder Zebra-skrivare kan du använda följande kod.</span><span class="sxs-lookup"><span data-stu-id="662f5-190">For example, if you're using Zebra printers, you can use the following code.</span></span>

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

1. <span data-ttu-id="662f5-191">I avsnittet **brödtext** i fältet **etikettext** anger du ZPL-koden för önskad text.</span><span class="sxs-lookup"><span data-stu-id="662f5-191">In the **Body section** section, in the **Label body** field, enter ZPL code for the required body.</span></span> <span data-ttu-id="662f5-192">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="662f5-192">Here is an example.</span></span>

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

1. <span data-ttu-id="662f5-193">I avsnittet **brödtext** i fältet **etikettsidfot** anger du ZPL-koden för önskad sidfot.</span><span class="sxs-lookup"><span data-stu-id="662f5-193">In the **Body section** section, in the **Label footer** field, enter ZPL code for the required footer.</span></span> <span data-ttu-id="662f5-194">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="662f5-194">Here is an example.</span></span>

    ```plaintext
    ^PQ1^XZ
    ```

    > [!NOTE]
    > <span data-ttu-id="662f5-195">Installationen kommer att skriva ut en kopia av varje etikett.</span><span class="sxs-lookup"><span data-stu-id="662f5-195">This setup will print one copy of each label.</span></span> <span data-ttu-id="662f5-196">Om du vill ha fler kopior (t.ex. en kopia för varje sida av lastpallen) anger du värdet **n** för avsnittet **\^PQn** i sidfoten till det antal kopior som krävs.</span><span class="sxs-lookup"><span data-stu-id="662f5-196">If you require more copies (for example, one copy for each side of the pallet), set the **n** value for the **\^PQn** section in the footer to the required number of copies.</span></span> <span data-ttu-id="662f5-197">Om du till exempel vill skriva ut fyra kopior av varje etikett anger du **\^PQ4**.</span><span class="sxs-lookup"><span data-stu-id="662f5-197">For example, to print four copies of each label, specify **\^PQ4**.</span></span>

<span data-ttu-id="662f5-198">Nu kan du använda din etikett.</span><span class="sxs-lookup"><span data-stu-id="662f5-198">Your label is now ready to use.</span></span>

### <a name="create-a-wave-label-type"></a><span data-ttu-id="662f5-199">Skapa en typ för påfyllnadsetiketten</span><span class="sxs-lookup"><span data-stu-id="662f5-199">Create a wave label type</span></span>

<span data-ttu-id="662f5-200">Påfyllnadsetikettyper används för att länka påfyllnadsetikettmallar till en enhet på enhetssekvensgrupprader.</span><span class="sxs-lookup"><span data-stu-id="662f5-200">Wave label types are used to link wave label templates to a unit on unit sequence group lines.</span></span>

1. <span data-ttu-id="662f5-201">Gå till **Lagerstyrning \> Inställningar \> Dokumentflöde \> Typer av påfyllnadsetikett**.</span><span class="sxs-lookup"><span data-stu-id="662f5-201">Go to **Warehouse management \> Setup \> Document routing \> Wave label types**.</span></span>
1. <span data-ttu-id="662f5-202">Lägg till en typ av påfyllnadsetikett med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="662f5-202">Add a wave label type that has the following settings:</span></span>

    - <span data-ttu-id="662f5-203">**Etikettyp:** *kartong*</span><span class="sxs-lookup"><span data-stu-id="662f5-203">**Label type:** *Carton*</span></span>
    - <span data-ttu-id="662f5-204">**Beskrivning:** *kartong*</span><span class="sxs-lookup"><span data-stu-id="662f5-204">**Description:** *Carton*</span></span>

### <a name="set-up-unit-sequence-groups"></a><span data-ttu-id="662f5-205">Konfigurera enhetssekvensgrupper</span><span class="sxs-lookup"><span data-stu-id="662f5-205">Set up unit sequence groups</span></span>

<span data-ttu-id="662f5-206">Ställ sedan in enhetsseriegruppen för typ av påfyllnadsnivå.</span><span class="sxs-lookup"><span data-stu-id="662f5-206">Next, set up the unit sequence group for the wave label type.</span></span>

1. <span data-ttu-id="662f5-207">Gå till **Lagerstyrning \> Inställningar \> Lagerställe \> Enhetsseriegrupp**.</span><span class="sxs-lookup"><span data-stu-id="662f5-207">Go to **Warehouse management \> Setup \> Warehouse \> Unit sequence groups**.</span></span>
1. <span data-ttu-id="662f5-208">Välj gruppen **Ea Box PL**.</span><span class="sxs-lookup"><span data-stu-id="662f5-208">Select the **Ea Box PL** group.</span></span>
1. <span data-ttu-id="662f5-209">För raden **ruta** ange fältet **typ av påfyllnadsnivå** till *kartong*.</span><span class="sxs-lookup"><span data-stu-id="662f5-209">For the **Box** line, set the **Wave level type** field to *Carton*.</span></span>

### <a name="create-a-wave-label-template"></a><span data-ttu-id="662f5-210">Skapa en mall för påfyllnadsetikett</span><span class="sxs-lookup"><span data-stu-id="662f5-210">Create a wave label template</span></span>

<span data-ttu-id="662f5-211">Skapa sedan mall för påfyllnadsetikett för typen av påfyllnadsetikett.</span><span class="sxs-lookup"><span data-stu-id="662f5-211">Next, create the wave label template for the wave label type.</span></span>

1. <span data-ttu-id="662f5-212">Gå till **Lagerstyrning \> Inställningar \> Dokumentflöde \> Mall för påfyllnadsetikett**.</span><span class="sxs-lookup"><span data-stu-id="662f5-212">Go to **Warehouse management \> Setup \> Document routing \> Wave label templates**.</span></span>
1. <span data-ttu-id="662f5-213">Lägg till en mall för påfyllnadsnivå och ange följande värden i rubriken:</span><span class="sxs-lookup"><span data-stu-id="662f5-213">Add a wave level template, and set the following values in the header:</span></span>

    - <span data-ttu-id="662f5-214">**Namn på etikettmallen:** *kartongetiketter*</span><span class="sxs-lookup"><span data-stu-id="662f5-214">**Label template name:** *Carton labels*</span></span>
    - <span data-ttu-id="662f5-215">**Beskrivning:** *kartongetiketter*</span><span class="sxs-lookup"><span data-stu-id="662f5-215">**Description:** *Carton labels*</span></span>
    - <span data-ttu-id="662f5-216">**Kod för påfyllnadssteg:** *PrintLabel*</span><span class="sxs-lookup"><span data-stu-id="662f5-216">**Wave step code:** *PrintLabel*</span></span>
    - <span data-ttu-id="662f5-217">**Lagerställe:** *62*</span><span class="sxs-lookup"><span data-stu-id="662f5-217">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="662f5-218">På snabbfliken **Allmänt** ställer du in fältet **typ av påfyllnadsetikett** till *kartong*.</span><span class="sxs-lookup"><span data-stu-id="662f5-218">On the **General** FastTab, set the **Wave label type** field to *Carton*.</span></span>
1. <span data-ttu-id="662f5-219">På snabbfliken **information om påfyllnadsetikettens mall** och lägg till en ny rad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="662f5-219">On the **Wave label template details** FastTab, add a new row that has the following settings:</span></span>

    - <span data-ttu-id="662f5-220">**Etikettlayout-ID:** *kartong*</span><span class="sxs-lookup"><span data-stu-id="662f5-220">**Label layout ID:** *Carton*</span></span>
    - <span data-ttu-id="662f5-221">**Skrivarnamn:** Välj en lämplig ZPL-skrivare.</span><span class="sxs-lookup"><span data-stu-id="662f5-221">**Printer name:** Select an appropriate ZPL printer.</span></span>
    - <span data-ttu-id="662f5-222">**Kör fråga:** *Ja* (den här inställningen är valfri, men rekommenderas för optimal prestanda.)</span><span class="sxs-lookup"><span data-stu-id="662f5-222">**Run query:** *Yes* (This setting is optional, but it's recommended for optimal performance.)</span></span>

1. <span data-ttu-id="662f5-223">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="662f5-223">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="662f5-224">Valfritt: om du ställer in en kundspecifik etikettdesign måste du skapa en fråga för att hitta kundens konto.</span><span class="sxs-lookup"><span data-stu-id="662f5-224">Optional: If you're setting up a customer-specific label design, you must create a query to find the customer's account.</span></span> <span data-ttu-id="662f5-225">På snabbfliken **information om påfyllnadsetikettens mall** välj **Redigera fråga**.</span><span class="sxs-lookup"><span data-stu-id="662f5-225">On the **Wave label template details** FastTab, select **Edit query**.</span></span> <span data-ttu-id="662f5-226">I frågeredigerarens dialogruta, på fliken **Intervall** lägg till en rad med följande värden:</span><span class="sxs-lookup"><span data-stu-id="662f5-226">Then, in the query editor dialog box, on the **Range** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="662f5-227">**Register:** *försändelser*</span><span class="sxs-lookup"><span data-stu-id="662f5-227">**Table:** *Shipments*</span></span>
    - <span data-ttu-id="662f5-228">**Härlett register:** *försändelser*</span><span class="sxs-lookup"><span data-stu-id="662f5-228">**Derived table:** *Shipments*</span></span>
    - <span data-ttu-id="662f5-229">**Fält:** *Kontonummer*</span><span class="sxs-lookup"><span data-stu-id="662f5-229">**Field:** *Account number*</span></span>
    - <span data-ttu-id="662f5-230">**Kriterier:** Ange relevant kundkontonummer.</span><span class="sxs-lookup"><span data-stu-id="662f5-230">**Criteria:** Enter the relevant customer account number.</span></span>

    <span data-ttu-id="662f5-231">När du är klar klickar du på **OK** för att stänga dialogrutan för frågeredigeraren.</span><span class="sxs-lookup"><span data-stu-id="662f5-231">When you've finished, select **OK** to close the query editor dialog box.</span></span>

1. <span data-ttu-id="662f5-232">I åtgärdsfönstret, välj **Redigera fråga** för att öppna en dialogruta för frågeredigeraren för hela etikettmallen.</span><span class="sxs-lookup"><span data-stu-id="662f5-232">On the Action Pane, select **Edit query** to open the query editor dialog box for the whole label template.</span></span>
1. <span data-ttu-id="662f5-233">I frågeredigerarens dialogruta, på fliken **Sortera** lägg till en rad med följande värden:</span><span class="sxs-lookup"><span data-stu-id="662f5-233">In the query editor dialog box, on the **Sorting** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="662f5-234">**Tabell:** *Arbetsrader*</span><span class="sxs-lookup"><span data-stu-id="662f5-234">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="662f5-235">**Härlett register:** *Arbetsrader*</span><span class="sxs-lookup"><span data-stu-id="662f5-235">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="662f5-236">**Fält:** *referens till läs in rad-ID (post-ID)*</span><span class="sxs-lookup"><span data-stu-id="662f5-236">**Field:** *Reference load line id (Record-ID)*</span></span>
    - <span data-ttu-id="662f5-237">**Sökriktning:** *Stigande*</span><span class="sxs-lookup"><span data-stu-id="662f5-237">**Search direction:** *Ascending*</span></span>

1. <span data-ttu-id="662f5-238">Stäng dialogrutan för frågeredigeraren genom att välja **OK**.</span><span class="sxs-lookup"><span data-stu-id="662f5-238">Select **OK** to close the query editor dialog box.</span></span>
1. <span data-ttu-id="662f5-239">En meddelande ruta ber dig bekräfta åtgärden grupperingsåterställning.</span><span class="sxs-lookup"><span data-stu-id="662f5-239">A message box prompts you to confirm the grouping reset operation.</span></span> <span data-ttu-id="662f5-240">Klicka på **Ja** när du vill fortsätta.</span><span class="sxs-lookup"><span data-stu-id="662f5-240">Select **Yes** to continue.</span></span>
1. <span data-ttu-id="662f5-241">I åtgärdsfönstret, välj **mallgruppen för påfyllnadsetikett**.</span><span class="sxs-lookup"><span data-stu-id="662f5-241">On the Action Pane, select **Wave label template group**.</span></span>
1. <span data-ttu-id="662f5-242">I dialogrutan **mallgruppen för påfyllnadsetikett** välj raden där fältet **referensfältnamn** anges till *referens till läs in rad-ID* och markerar sedan kryssrutan **etikettversions-ID** för den här raden.</span><span class="sxs-lookup"><span data-stu-id="662f5-242">In the **Wave label template group** dialog box, select the row where the **Reference field name** field is set to *Reference load line id*, and then select the **Label build ID** check box for this row.</span></span>

    > [!NOTE]
    > <span data-ttu-id="662f5-243">Med den här inställningen skapas en etikettserie ("kartong 1 av X") per lastrad i hela påfyllnaden, oavsett inställningen för arbetsgrupperingen.</span><span class="sxs-lookup"><span data-stu-id="662f5-243">This setup will create one label sequence ("Carton 1 of X") per load line throughout the wave, regardless of the work grouping setup.</span></span> <span data-ttu-id="662f5-244">Denna etikettserie kan skrivas ut på etikettlayouten.</span><span class="sxs-lookup"><span data-stu-id="662f5-244">This label sequence can be printed on the label layout.</span></span>

### <a name="configure-number-sequence-extensions"></a><span data-ttu-id="662f5-245">Konfigurera nummerserietillägg</span><span class="sxs-lookup"><span data-stu-id="662f5-245">Configure number sequence extensions</span></span>

<span data-ttu-id="662f5-246">Nummerserietillägg styr GS1 efterlevnaden av specifika nummerserier.</span><span class="sxs-lookup"><span data-stu-id="662f5-246">Number sequence extensions control the GS1 compliance of specific number sequences.</span></span> <span data-ttu-id="662f5-247">Den här konfigurationen är valfri för det aktuella scenariot.</span><span class="sxs-lookup"><span data-stu-id="662f5-247">This configuration is optional for the current scenario.</span></span> <span data-ttu-id="662f5-248">Mer information och instruktioner för konfigurering finns i [Konfigurera tillägg för nummerserier](../warehousing/configure-number-sequence-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="662f5-248">For more information and configuration instructions, see [Configure number sequence extensions](../warehousing/configure-number-sequence-extensions.md).</span></span>

### <a name="create-a-sales-order-and-release-it-to-the-warehouse"></a><span data-ttu-id="662f5-249">Skapa en försäljningsorder och släpp den på lagerstället</span><span class="sxs-lookup"><span data-stu-id="662f5-249">Create a sales order and release it to the warehouse</span></span>

1. <span data-ttu-id="662f5-250">Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="662f5-250">Go to **Sales and marketing \> Sales order \> All sales orders**.</span></span>
1. <span data-ttu-id="662f5-251">Skapa en försäljningsorder med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="662f5-251">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="662f5-252">**Kundkonto:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="662f5-252">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="662f5-253">**Lagerställe:** *62*</span><span class="sxs-lookup"><span data-stu-id="662f5-253">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="662f5-254">Lägg till två försäljningsorderrader med följande inställning:</span><span class="sxs-lookup"><span data-stu-id="662f5-254">Add two sales order lines that have the following settings:</span></span>

    - <span data-ttu-id="662f5-255">Försäljningsorderrad 1:</span><span class="sxs-lookup"><span data-stu-id="662f5-255">Sales order line 1:</span></span>

        - <span data-ttu-id="662f5-256">**Artikelnummer:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="662f5-256">**Item number:** *A0001*</span></span>
        - <span data-ttu-id="662f5-257">**Kvantitet:** *9024*</span><span class="sxs-lookup"><span data-stu-id="662f5-257">**Quantity:** *9024*</span></span>
        - <span data-ttu-id="662f5-258">**Enhet:** *ea* (9024 ea = 376 låda = 47 PL)</span><span class="sxs-lookup"><span data-stu-id="662f5-258">**Unit:** *ea* (9024 ea = 376 Box = 47 PL)</span></span>

    - <span data-ttu-id="662f5-259">Försäljningsorderrad 2:</span><span class="sxs-lookup"><span data-stu-id="662f5-259">Sales order line 2:</span></span>

        - <span data-ttu-id="662f5-260">**Artikelnummer:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="662f5-260">**Item number:** *A0002*</span></span>
        - <span data-ttu-id="662f5-261">**Kvantitet:** *9016*</span><span class="sxs-lookup"><span data-stu-id="662f5-261">**Quantity:** *9016*</span></span>
        - <span data-ttu-id="662f5-262">**Enhet:** *ea* (9016 ea = 322 box = 46 PL)</span><span class="sxs-lookup"><span data-stu-id="662f5-262">**Unit:** *ea* (9016 ea = 322 Box = 46 PL)</span></span>

    > [!NOTE]
    > <span data-ttu-id="662f5-263">Artiklarna och kvantiteterna som anges här är endast exempel.</span><span class="sxs-lookup"><span data-stu-id="662f5-263">The items and quantities that are provided here are only examples.</span></span> <span data-ttu-id="662f5-264">De måste använda den enhetsseriegrupp som du definierade tidigare, och lämpliga enhetskonverteringar från *ea* till *Box* till *PL* måste definieras för dem och de måste ha lager i lagerställe *62*.</span><span class="sxs-lookup"><span data-stu-id="662f5-264">They must use the unit sequence group that you defined earlier, appropriate unit conversions from *ea* to *Box* to *PL* must be defined for them, and they must have stock in warehouse *62*.</span></span> <span data-ttu-id="662f5-265">Mer information finns i [måttenhet och lagerprinciper](unit-measure-stocking-policies.md).</span><span class="sxs-lookup"><span data-stu-id="662f5-265">For more information, see [Unit of measure and stocking policies](unit-measure-stocking-policies.md).</span></span>

1. <span data-ttu-id="662f5-266">Välj försäljningsorderrad 1.</span><span class="sxs-lookup"><span data-stu-id="662f5-266">Select sales order line 1.</span></span> <span data-ttu-id="662f5-267">I avsnittet **Försäljningsorderrad** i menyn **Lager** välj **Reservationer**.</span><span class="sxs-lookup"><span data-stu-id="662f5-267">Then, in the **Sales order line** section, on the **Inventory** menu, select **Reservations**.</span></span>
1. <span data-ttu-id="662f5-268">På sidan **Reservation** i åtgärdsfönstret, välj **Reservera parti** och stäng sedan sidan.</span><span class="sxs-lookup"><span data-stu-id="662f5-268">On the **Reservation** page, on the Action Pane, select **Reserve lot**, and then close the page.</span></span>
1. <span data-ttu-id="662f5-269">Upprepa steg 4 och 5 för försäljningsorderrad 2.</span><span class="sxs-lookup"><span data-stu-id="662f5-269">Repeat steps 4 and 5 for sales order line 2.</span></span>
1. <span data-ttu-id="662f5-270">I åtgärdsfönstret på fliken **Lagerställe** välj **Frisläpp till regel för lagerställe**.</span><span class="sxs-lookup"><span data-stu-id="662f5-270">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="662f5-271">Då inträffar följande händelser:</span><span class="sxs-lookup"><span data-stu-id="662f5-271">The following events occur:</span></span>

    - <span data-ttu-id="662f5-272">I systemet bearbetas den skapade utleveransen med hjälp av mallen som inkluderar utskriftssteget för etikett.</span><span class="sxs-lookup"><span data-stu-id="662f5-272">The system processes the created shipment by using the template that includes the label printing step.</span></span> <span data-ttu-id="662f5-273">Etikettlayouten används för att definiera etikettens format, och resultatet blir en etikett som skrivs ut på den skrivare som väljs i etikettmallen.</span><span class="sxs-lookup"><span data-stu-id="662f5-273">The label layout will be used to define the format of the label, and the result will be a label that is printed on the printer that is selected in the label template.</span></span>
    - <span data-ttu-id="662f5-274">Påfyllnadsetiketter genereras och skrivs ut.</span><span class="sxs-lookup"><span data-stu-id="662f5-274">Wave labels are generated and printed.</span></span> <span data-ttu-id="662f5-275">Antalet etiketter är lika med antalet kartonger (i det här exemplet är 376 boxetiketter för rad 1 och 322 boxetiketter för rad 2).</span><span class="sxs-lookup"><span data-stu-id="662f5-275">The number of labels will equal the number of cartons (in this example, 376 Box labels for line 1 and 322 Box labels for line 2).</span></span>
    - <span data-ttu-id="662f5-276">Ett nytt fraktsedels-ID genereras för leveranserna.</span><span class="sxs-lookup"><span data-stu-id="662f5-276">A new bill of lading ID is generated for the shipments.</span></span> <span data-ttu-id="662f5-277">Om du har konfigurerat nummerserietilläggen följer påfyllnadsetikett-ID nummerformatet **SSCC-18**.</span><span class="sxs-lookup"><span data-stu-id="662f5-277">If you configured the number sequence extensions, the wave label IDs will follow the **SSCC-18** number format.</span></span> 

<span data-ttu-id="662f5-278">Du kan visa och skriva ut påfyllnadsetiketter på följande sidor.</span><span class="sxs-lookup"><span data-stu-id="662f5-278">You can view and reprint wave labels from the following pages.</span></span> <span data-ttu-id="662f5-279">I åtgärdsfönstret, på varje sida, på fliken **Leveranser**, i gruppen **Relaterad information**, väljer du **påfyllnadsetiketter**.</span><span class="sxs-lookup"><span data-stu-id="662f5-279">On the Action Pane of each page, on the **Shipments** tab, in the **Related information** group, select **Wave labels**.</span></span>

- <span data-ttu-id="662f5-280">Alla leveranser \> leveransinformation</span><span class="sxs-lookup"><span data-stu-id="662f5-280">All shipments \> Shipment details</span></span>
- <span data-ttu-id="662f5-281">Alla laster \> Läs in information</span><span class="sxs-lookup"><span data-stu-id="662f5-281">All loads \> Load details</span></span>
- <span data-ttu-id="662f5-282">Alla påfyllnader</span><span class="sxs-lookup"><span data-stu-id="662f5-282">All waves</span></span>
- <span data-ttu-id="662f5-283">Påfyllnadsetiketter</span><span class="sxs-lookup"><span data-stu-id="662f5-283">Wave labels</span></span>
- <span data-ttu-id="662f5-284">Etiketthistorik för påfyllnad</span><span class="sxs-lookup"><span data-stu-id="662f5-284">Wave label history</span></span>

## <a name="scenario-2-wave-label-printing-for-containerization-without-wave-label-records"></a><span data-ttu-id="662f5-285">Scenario 2: påfyllnadsetikett utskrift för skapande av behållare (utan påfyllnadsetikettposter)</span><span class="sxs-lookup"><span data-stu-id="662f5-285">Scenario 2: Wave label printing for containerization (without wave label records)</span></span>

<span data-ttu-id="662f5-286">I det här scenariot kan du skriva ut påfyllnadsetiketter när du använder skapande av behållare för att automatiskt dela upp objekt i kartonger och därför inte kräva en påfyllnadsetikettpost.</span><span class="sxs-lookup"><span data-stu-id="662f5-286">This scenario lets you print wave labels when you use containerization to automatically split items into cartons and therefore don't require a wave label record.</span></span> <span data-ttu-id="662f5-287">I det här fallet fungerar behållar-ID som platshållare för SSCC.</span><span class="sxs-lookup"><span data-stu-id="662f5-287">In this case, the container ID acts as a placeholder for the SSCC.</span></span>

<span data-ttu-id="662f5-288">Här är de viktigaste skillnaderna mellan det här scenariot och scenario 1:</span><span class="sxs-lookup"><span data-stu-id="662f5-288">Here are the main differences between this scenario and scenario 1:</span></span>

- <span data-ttu-id="662f5-289">**Mallar för påfyllnadsetiketter:** du väljer ingen typ av påfyllnadsetikett i mallen för påfyllnadsetiketter och du behöver inte använda en gruppering för att skapa etiketter.</span><span class="sxs-lookup"><span data-stu-id="662f5-289">**Wave label templates:** You won't select a wave label type on the wave label template, and you won't require a label build grouping.</span></span> <span data-ttu-id="662f5-290">Annars kan du konfigurera mallen för påfyllnadsetikett och länka till påfyllnadsmallen på samma sätt som beskrivs i scenario 1.</span><span class="sxs-lookup"><span data-stu-id="662f5-290">Otherwise, you will configure the wave label template and link to the wave template in the same way that is described in scenario 1.</span></span> <span data-ttu-id="662f5-291">Du måste lämna typ av påfyllnadsetikett tom om du vill förhindra att påfyllnadsetiketter genereras.</span><span class="sxs-lookup"><span data-stu-id="662f5-291">You must leave the wave label type blank to prevent wave labels from being generated.</span></span>
- <span data-ttu-id="662f5-292">**Layout för påfyllnadsetiketter:** du kan konfigurera radinställningarna för layouten för påfyllnadsetiketter för arbetsrader i stället för påfyllnadsetikettposter.</span><span class="sxs-lookup"><span data-stu-id="662f5-292">**Wave label layouts:** You will configure the wave label layout row settings for work lines instead of wave label records.</span></span> <span data-ttu-id="662f5-293">Du måste konfigurera radinställningen för etikettlayout med hjälp av registret **WHSWorkLine** i stället för registret **WHSWaveLabel**.</span><span class="sxs-lookup"><span data-stu-id="662f5-293">You must configure the row setting for the label layout by using the **WHSWorkLine** table instead of the **WHSWaveLabel** table.</span></span> <span data-ttu-id="662f5-294">Inställningen **rader per sida** styr antalet rader som brödtextavsnittet ska ha.</span><span class="sxs-lookup"><span data-stu-id="662f5-294">The **Rows per page** setting controls the number of rows that the body section will have.</span></span> 

<span data-ttu-id="662f5-295">Den här konfigurationen är också lämplig för affärsscenarier där flera olika artiklar förpackas i en etikettruta eller till en lastpall, och denna förpackningsprocess kan definieras genom att arbetet skapas (t.ex. arbete som grupperats per leverans).</span><span class="sxs-lookup"><span data-stu-id="662f5-295">This configuration is also suitable for business scenarios where multiple different items are packed into one labeled box or into a pallet, and this packing process can be defined by work creation (for example, work that is grouped by shipment).</span></span>

<span data-ttu-id="662f5-296">Det här scenariot visar komplett flöde.</span><span class="sxs-lookup"><span data-stu-id="662f5-296">This scenario shows the end-to-end flow.</span></span>

### <a name="make-demo-data-available"></a><span data-ttu-id="662f5-297">Gör demodata tillgängliga</span><span class="sxs-lookup"><span data-stu-id="662f5-297">Make demo data available</span></span>

<span data-ttu-id="662f5-298">För att följa detta scenario måste du ha demonstrationsdata installerad och du måste välja juridiska personen **USMF**.</span><span class="sxs-lookup"><span data-stu-id="662f5-298">To follow this scenario, you must have demo data installed, and you must select the **USMF** legal entity.</span></span>

### <a name="make-sure-that-the-wave-label-method-is-available"></a><span data-ttu-id="662f5-299">Kontrollera att påfyllnadsetikett metoden är tillgänglig</span><span class="sxs-lookup"><span data-stu-id="662f5-299">Make sure that the wave label method is available</span></span>

<span data-ttu-id="662f5-300">Du måste kanske återskapa dina metoder för påfyllnadsprocess för att göra påfyllnadsetikett metoden tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="662f5-300">You might have to regenerate the wave process methods to make the wave label printing method available.</span></span>

1. <span data-ttu-id="662f5-301">Gå till **Lagerstyrning \> Inställningar \> Påfyllnader \> Metoder för påfyllnadsprocess**.</span><span class="sxs-lookup"><span data-stu-id="662f5-301">Go to **Warehouse management \> Setup \> Waves \> Wave process methods**.</span></span>
1. <span data-ttu-id="662f5-302">Kontrollera att **waveLabelPrinting** finns i listan.</span><span class="sxs-lookup"><span data-stu-id="662f5-302">Confirm that **waveLabelPrinting** is in the list.</span></span> <span data-ttu-id="662f5-303">Om den inte finns med väljer du **återskapa metoder** i åtgärdsfönstret för att lägga till den.</span><span class="sxs-lookup"><span data-stu-id="662f5-303">If it isn't, select **Regenerate methods** on the Action Pane to add it.</span></span>

### <a name="set-up-a-wave-template"></a><span data-ttu-id="662f5-304">Ställa in en påfyllnadsmall</span><span class="sxs-lookup"><span data-stu-id="662f5-304">Set up a wave template</span></span>

<span data-ttu-id="662f5-305">Med påfyllnadsmallar kan du länka specifika förekomster av påfyllnadsmetoder till en motsvarande påfyllnadsetikettsmall.</span><span class="sxs-lookup"><span data-stu-id="662f5-305">Wave templates let you link specific instances of wave methods to a corresponding wave label template.</span></span>

1. <span data-ttu-id="662f5-306">Gå till **Lagerstyrning \> Inställningar \> Påfyllnader \> Påfyllnadsmallar**.</span><span class="sxs-lookup"><span data-stu-id="662f5-306">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
1. <span data-ttu-id="662f5-307">Välj en mall som **63 skapande av behållare**.</span><span class="sxs-lookup"><span data-stu-id="662f5-307">Select a template, such as **63 Containerization**.</span></span>
1. <span data-ttu-id="662f5-308">På snabbfliken **metoder** flyttar du metoden **utskrift av påfyllnadsetiketter** till kolumnen **valda metoder**.</span><span class="sxs-lookup"><span data-stu-id="662f5-308">On the **Methods** FastTab, move the **Wave label printing** method to the **Selected methods** column.</span></span>
1. <span data-ttu-id="662f5-309">I kolumnen **Valda metoder** välj metoden **Utskrift av påfyllnadsetiketter** och ange dess fält **Kod för påfyllnadssteg** till *PrintLabel*.</span><span class="sxs-lookup"><span data-stu-id="662f5-309">In the **Selected methods** column, select the **Wave label printing** method, and set its **Wave step code** field to *PrintLabel*.</span></span> <span data-ttu-id="662f5-310">För mer information om koder för påfyllnadssteg, se [Koder för påfyllnadssteg](wave-step-codes.md).</span><span class="sxs-lookup"><span data-stu-id="662f5-310">For more information about wave step codes, see [Wave step codes](wave-step-codes.md).</span></span>

### <a name="create-a-wave-label-layout"></a><span data-ttu-id="662f5-311">Skapa en layout för påfyllnadsetiketten</span><span class="sxs-lookup"><span data-stu-id="662f5-311">Create a wave label layout</span></span>

1. <span data-ttu-id="662f5-312">Gå till **Lagerstyrning \> Inställningar \> Dokumentflöde \> Layout för påfyllnadsetikett**.</span><span class="sxs-lookup"><span data-stu-id="662f5-312">Go to **Warehouse management \> Setup \> Document routing \> Wave label layouts**.</span></span>
1. <span data-ttu-id="662f5-313">Skapa en post med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="662f5-313">Create a record that has the following settings:</span></span>

    - <span data-ttu-id="662f5-314">**Etikettlayout-ID:** *kartong*</span><span class="sxs-lookup"><span data-stu-id="662f5-314">**Label layout ID:** *Carton*</span></span>
    - <span data-ttu-id="662f5-315">**Beskrivning:** *kartong (SSCC)*</span><span class="sxs-lookup"><span data-stu-id="662f5-315">**Description:** *Carton (SSCC)*</span></span>

1. <span data-ttu-id="662f5-316">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="662f5-316">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="662f5-317">I åtgärdsfönstret, välj **Inställningar för påfyllnadsetikettrad**.</span><span class="sxs-lookup"><span data-stu-id="662f5-317">On the Action Pane, select **Wave label row settings**.</span></span>

    <span data-ttu-id="662f5-318">Sidan **Inställningar för påfyllnadsetikettrad** visas.</span><span class="sxs-lookup"><span data-stu-id="662f5-318">The **Wave label row settings** page appears.</span></span> <span data-ttu-id="662f5-319">Här kan du konfigurera den dynamiska delen av etiketten.</span><span class="sxs-lookup"><span data-stu-id="662f5-319">Here, you can configure the dynamic part of the label.</span></span>

1. <span data-ttu-id="662f5-320">Lägg till en rad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="662f5-320">Add a row that has the following settings:</span></span>

    - <span data-ttu-id="662f5-321">**Rad-ID:** *WorkLine*</span><span class="sxs-lookup"><span data-stu-id="662f5-321">**Row Id:** *WorkLine*</span></span>
    - <span data-ttu-id="662f5-322">**Radtabellnamn:** *WHSWorkLine*</span><span class="sxs-lookup"><span data-stu-id="662f5-322">**Row table name:** *WHSWorkLine*</span></span>
    - <span data-ttu-id="662f5-323">**Radens startposition:** *500*</span><span class="sxs-lookup"><span data-stu-id="662f5-323">**Row start position:** *500*</span></span>

        <span data-ttu-id="662f5-324">I det här fältet definieras den lodräta position där raden ska börja etiketten.</span><span class="sxs-lookup"><span data-stu-id="662f5-324">This field defines the vertical position where the row will begin on the label.</span></span>

    - <span data-ttu-id="662f5-325">**Radhöjd:** *-50*</span><span class="sxs-lookup"><span data-stu-id="662f5-325">**Row height:** *-50*</span></span>

        <span data-ttu-id="662f5-326">I det här fältet definieras höjden på varje rad.</span><span class="sxs-lookup"><span data-stu-id="662f5-326">This field defines the height of each row.</span></span> <span data-ttu-id="662f5-327">Radhöjden är positiv för vågräta etiketter och är negativ för lodräta etiketter.</span><span class="sxs-lookup"><span data-stu-id="662f5-327">The row height is positive for horizontal labels and negative for vertical labels.</span></span>

    - <span data-ttu-id="662f5-328">**Rader per sida:** *5*</span><span class="sxs-lookup"><span data-stu-id="662f5-328">**Rows per page:** *5*</span></span>

        <span data-ttu-id="662f5-329">I det här fältet definieras antalet rader som kan skrivas ut på varje etikett.</span><span class="sxs-lookup"><span data-stu-id="662f5-329">This field defines the number of rows that can be printed on each label.</span></span>

        > [!NOTE]
        > <span data-ttu-id="662f5-330">Denna inställning kommer att skriva ut flera ZPL-etiketter per arbete, där varje sida kan innehålla upp till fem arbetsrader.</span><span class="sxs-lookup"><span data-stu-id="662f5-330">This setup will print several ZPL labels per work, where each page can hold up to five work lines.</span></span> <span data-ttu-id="662f5-331">Om en etikett till exempel skrivs ut för en behållare med 12 rader skrivs tre etiketter ut.</span><span class="sxs-lookup"><span data-stu-id="662f5-331">For example, if a label is printed for a container that has 12 lines, three labels will be printed.</span></span> <span data-ttu-id="662f5-332">Om du vill skriva ut en separat etikett för varje plockningsrad anger du det här värdet till *1*.</span><span class="sxs-lookup"><span data-stu-id="662f5-332">If you want to print a separate label for each pick line, set this value to *1*.</span></span>

1. <span data-ttu-id="662f5-333">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="662f5-333">Close the page.</span></span>
1. <span data-ttu-id="662f5-334">I åtgärdsfönstret väljer du **Redigera fråga**.</span><span class="sxs-lookup"><span data-stu-id="662f5-334">On the Action Pane, select **Edit query**.</span></span>
1. <span data-ttu-id="662f5-335">I frågeredigerarens dialogruta, på fliken **Intervall** lägg till en rad med följande värden:</span><span class="sxs-lookup"><span data-stu-id="662f5-335">In the query editor dialog box, on the **Range** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="662f5-336">**Tabell:** *Arbetsrader*</span><span class="sxs-lookup"><span data-stu-id="662f5-336">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="662f5-337">**Härlett register:** *Arbetsrader*</span><span class="sxs-lookup"><span data-stu-id="662f5-337">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="662f5-338">**Fält:** *arbetstyp*</span><span class="sxs-lookup"><span data-stu-id="662f5-338">**Field:** *Work type*</span></span>
    - <span data-ttu-id="662f5-339">**Kriterier:** *Plocka*</span><span class="sxs-lookup"><span data-stu-id="662f5-339">**Criteria:** *Pick*</span></span>

1. <span data-ttu-id="662f5-340">Om du vill kunna skriva ut fraktsedels-ID väljer du på fliken **kopplingar**, sedan **arbetsrader** och kopplar tabellen **leveranser** till den.</span><span class="sxs-lookup"><span data-stu-id="662f5-340">If you want to be able to print the bill of lading ID, on the **Joins** tab, select the **Work lines** table, and join the **Shipments** table to it.</span></span>
1. <span data-ttu-id="662f5-341">Stäng dialogrutan frågeredigeraren.</span><span class="sxs-lookup"><span data-stu-id="662f5-341">Close the query editor dialog box.</span></span>
1. <span data-ttu-id="662f5-342">På snabbfliken **Layout för skrivartext** finns tre avsnitt där du kan skriva skrivarkod: **rubrikavsnitt**, **brödtext** och **sidfotsavsnitt**.</span><span class="sxs-lookup"><span data-stu-id="662f5-342">The **Printer text Layout** FastTab has three sections where you can write printer code: **Header section**, **Body section**, and **Footer section**.</span></span> <span data-ttu-id="662f5-343">I avsnittet **rubrikavsnitt** i fältet **etikettrubrik** anger du koden för önskad rubrik.</span><span class="sxs-lookup"><span data-stu-id="662f5-343">In the **Header section** section, in the **Label header** field, enter code for the required header.</span></span> <span data-ttu-id="662f5-344">Om du till exempel använder Zebra-skrivare kan du använda följande kod.</span><span class="sxs-lookup"><span data-stu-id="662f5-344">For example, if you're using Zebra printers, you can use the following code.</span></span>

    ```plaintext
    CT~~CD,~CC^~CT~
    ^XA
    ^LH10,10
    ^FO0,0 ^AT ^FD$WHSWorkTable.ContainerId$ ^FS
    ^FO0,75 ^AT ^FD$WHSWorkLine.ShipmentId$ ^FS
    ^FO0,150 ^AT ^FD$WHSShipmentTable.BillOfLadingId$ ^FS
    ```

1. <span data-ttu-id="662f5-345">I avsnittet **brödtext** i fältet **etikettext** anger du ZPL-koden för önskad text.</span><span class="sxs-lookup"><span data-stu-id="662f5-345">In the **Body section** section, in the **Label body** field, enter ZPL code for the required body.</span></span> <span data-ttu-id="662f5-346">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="662f5-346">Here is an example.</span></span>

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

1. <span data-ttu-id="662f5-347">I avsnittet **brödtext** i fältet **etikettsidfot** anger du ZPL-koden för önskad sidfot.</span><span class="sxs-lookup"><span data-stu-id="662f5-347">In the **Body section** section, in the **Label footer** field, enter ZPL code for the required footer.</span></span> <span data-ttu-id="662f5-348">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="662f5-348">Here is an example.</span></span>

    ```plaintext
    ^PQ1^XZ
    ```

    > [!NOTE]
    > <span data-ttu-id="662f5-349">Installationen kommer att skriva ut en kopia av varje etikett.</span><span class="sxs-lookup"><span data-stu-id="662f5-349">This setup will print one copy of each label.</span></span> <span data-ttu-id="662f5-350">Om du vill ha fler kopior (t.ex. en kopia för varje sida av lastpallen) anger du värdet **n** för avsnittet **\^PQn** i sidfoten till det antal kopior som krävs.</span><span class="sxs-lookup"><span data-stu-id="662f5-350">If you require more copies (for example, one copy for each side of the pallet), set the **n** value for the **\^PQn** section in the footer to the required number of copies.</span></span> <span data-ttu-id="662f5-351">Om du till exempel vill skriva ut fyra kopior av varje etikett anger du **\^PQ4**.</span><span class="sxs-lookup"><span data-stu-id="662f5-351">For example, to print four copies of each label, specify **\^PQ4**.</span></span>

<span data-ttu-id="662f5-352">Nu kan du använda din etikett.</span><span class="sxs-lookup"><span data-stu-id="662f5-352">Your label is now ready to use.</span></span>

### <a name="create-a-wave-label-template"></a><span data-ttu-id="662f5-353">Skapa en mall för påfyllnadsetikett</span><span class="sxs-lookup"><span data-stu-id="662f5-353">Create a wave label template</span></span>

1. <span data-ttu-id="662f5-354">Gå till **Lagerstyrning \> Inställningar \> Dokumentflöde \> Mall för påfyllnadsetikett**.</span><span class="sxs-lookup"><span data-stu-id="662f5-354">Go to **Warehouse management \> Setup \> Document routing \> Wave label templates**.</span></span>
1. <span data-ttu-id="662f5-355">Lägg till en mall för påfyllnadsnivå och ange följande värden i rubriken:</span><span class="sxs-lookup"><span data-stu-id="662f5-355">Add a wave level template, and set the following values in the header:</span></span>

    - <span data-ttu-id="662f5-356">**Namn på etikettmallen:** *behållaretiketter*</span><span class="sxs-lookup"><span data-stu-id="662f5-356">**Label template name:** *Container labels*</span></span>
    - <span data-ttu-id="662f5-357">**Beskrivning:** *behållaretiketter*</span><span class="sxs-lookup"><span data-stu-id="662f5-357">**Description:** *Container labels*</span></span>
    - <span data-ttu-id="662f5-358">**Kod för påfyllnadssteg:** *PrintLabel*</span><span class="sxs-lookup"><span data-stu-id="662f5-358">**Wave step code:** *PrintLabel*</span></span>
    - <span data-ttu-id="662f5-359">**Lagerställe:** *63*</span><span class="sxs-lookup"><span data-stu-id="662f5-359">**Warehouse:** *63*</span></span>

1. <span data-ttu-id="662f5-360">På snabbfliken **information om påfyllnadsetikettens mall** och lägg till en rad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="662f5-360">On the **Wave label template details** FastTab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="662f5-361">**Etikettlayout-ID:** *behållare*</span><span class="sxs-lookup"><span data-stu-id="662f5-361">**Label layout ID:** *Container*</span></span>
    - <span data-ttu-id="662f5-362">**Skrivarnamn:** Välj en lämplig ZPL-skrivare.</span><span class="sxs-lookup"><span data-stu-id="662f5-362">**Printer name:** Select an appropriate ZPL printer.</span></span>
    - <span data-ttu-id="662f5-363">**Kör fråga:** *Ja* (den här inställningen är valfri, men rekommenderas för optimal prestanda.)</span><span class="sxs-lookup"><span data-stu-id="662f5-363">**Run query:** *Yes* (This setting is optional, but it's recommended for optimal performance.)</span></span>

1. <span data-ttu-id="662f5-364">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="662f5-364">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="662f5-365">Valfritt: om du ställer in en kundspecifik etikettdesign måste du skapa en fråga för att hitta kundens konto.</span><span class="sxs-lookup"><span data-stu-id="662f5-365">Optional: If you're setting up a customer-specific label design, you must create a query to find the customer's account.</span></span> <span data-ttu-id="662f5-366">På snabbfliken **information om påfyllnadsetikettens mall** välj **Redigera fråga**.</span><span class="sxs-lookup"><span data-stu-id="662f5-366">On the **Wave label template details** FastTab, select **Edit query**.</span></span> <span data-ttu-id="662f5-367">I frågeredigerarens dialogruta, på fliken **Intervall** lägg till en rad med följande värden:</span><span class="sxs-lookup"><span data-stu-id="662f5-367">Then, in the query editor dialog box, on the **Range** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="662f5-368">**Register:** *försändelser*</span><span class="sxs-lookup"><span data-stu-id="662f5-368">**Table:** *Shipments*</span></span>
    - <span data-ttu-id="662f5-369">**Härlett register:** *försändelser*</span><span class="sxs-lookup"><span data-stu-id="662f5-369">**Derived table:** *Shipments*</span></span>
    - <span data-ttu-id="662f5-370">**Fält:** *Kontonummer*</span><span class="sxs-lookup"><span data-stu-id="662f5-370">**Field:** *Account number*</span></span>
    - <span data-ttu-id="662f5-371">**Kriterier:** Ange relevant kundkontonummer.</span><span class="sxs-lookup"><span data-stu-id="662f5-371">**Criteria:** Enter the relevant customer account number.</span></span>

    <span data-ttu-id="662f5-372">När du är klar klickar du på **OK** för att stänga dialogrutan för frågeredigeraren.</span><span class="sxs-lookup"><span data-stu-id="662f5-372">When you've finished, select **OK** to close the query editor dialog box.</span></span>

### <a name="configure-number-sequence-extensions"></a><span data-ttu-id="662f5-373">Konfigurera nummerserietillägg</span><span class="sxs-lookup"><span data-stu-id="662f5-373">Configure number sequence extensions</span></span>

<span data-ttu-id="662f5-374">Nummerserietillägg styr GS1 efterlevnaden av specifika nummerserier.</span><span class="sxs-lookup"><span data-stu-id="662f5-374">Number sequence extensions control the GS1 compliance of specific number sequences.</span></span> <span data-ttu-id="662f5-375">Den här konfigurationen är valfri för det aktuella scenariot.</span><span class="sxs-lookup"><span data-stu-id="662f5-375">This configuration is optional for the current scenario.</span></span> <span data-ttu-id="662f5-376">Mer information och instruktioner för konfigurering finns i [Konfigurera tillägg för nummerserier](../warehousing/configure-number-sequence-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="662f5-376">For more information and configuration instructions, see [Configure number sequence extensions](../warehousing/configure-number-sequence-extensions.md).</span></span>

### <a name="create-a-sales-order-and-release-it-to-the-warehouse"></a><span data-ttu-id="662f5-377">Skapa en försäljningsorder och släpp den på lagerstället</span><span class="sxs-lookup"><span data-stu-id="662f5-377">Create a sales order and release it to the warehouse</span></span>

1. <span data-ttu-id="662f5-378">Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="662f5-378">Go to **Sales and marketing \> Sales order \> All sales orders**.</span></span>
1. <span data-ttu-id="662f5-379">Skapa en försäljningsorder med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="662f5-379">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="662f5-380">**Kundkonto:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="662f5-380">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="662f5-381">**Lagerställe:** *63*</span><span class="sxs-lookup"><span data-stu-id="662f5-381">**Warehouse:** *63*</span></span>

1. <span data-ttu-id="662f5-382">Lägg till fem försäljningsorderrader:</span><span class="sxs-lookup"><span data-stu-id="662f5-382">Add five sales order lines:</span></span>

    - <span data-ttu-id="662f5-383">Försäljningsorderrad 1:</span><span class="sxs-lookup"><span data-stu-id="662f5-383">Sales order line 1:</span></span>

        - <span data-ttu-id="662f5-384">**Artikelnummer:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="662f5-384">**Item number:** *A0001*</span></span>
        - <span data-ttu-id="662f5-385">**Kvantitet:** *10*</span><span class="sxs-lookup"><span data-stu-id="662f5-385">**Quantity:** *10*</span></span>

    - <span data-ttu-id="662f5-386">Försäljningsorderrad 2:</span><span class="sxs-lookup"><span data-stu-id="662f5-386">Sales order line 2:</span></span>

        - <span data-ttu-id="662f5-387">**Artikelnummer:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="662f5-387">**Item number:** *A0002*</span></span>
        - <span data-ttu-id="662f5-388">**Kvantitet:** *20*</span><span class="sxs-lookup"><span data-stu-id="662f5-388">**Quantity:** *20*</span></span>

    - <span data-ttu-id="662f5-389">Försäljningsorderrad 3:</span><span class="sxs-lookup"><span data-stu-id="662f5-389">Sales order line 3:</span></span>

        - <span data-ttu-id="662f5-390">**Artikelnummer:** *L0006*</span><span class="sxs-lookup"><span data-stu-id="662f5-390">**Item number:** *L0006*</span></span>
        - <span data-ttu-id="662f5-391">**Kvantitet:** *20*</span><span class="sxs-lookup"><span data-stu-id="662f5-391">**Quantity:** *20*</span></span>

    - <span data-ttu-id="662f5-392">Försäljningsorderrad 4:</span><span class="sxs-lookup"><span data-stu-id="662f5-392">Sales order line 4:</span></span>

        - <span data-ttu-id="662f5-393">**Artikelnummer:** *L0100*</span><span class="sxs-lookup"><span data-stu-id="662f5-393">**Item number:** *L0100*</span></span>
        - <span data-ttu-id="662f5-394">**Kvantitet:** *40*</span><span class="sxs-lookup"><span data-stu-id="662f5-394">**Quantity:** *40*</span></span>

    - <span data-ttu-id="662f5-395">Försäljningsorderrad 5:</span><span class="sxs-lookup"><span data-stu-id="662f5-395">Sales order line 5:</span></span>

        - <span data-ttu-id="662f5-396">**Artikelnummer:** *L0101*</span><span class="sxs-lookup"><span data-stu-id="662f5-396">**Item number:** *L0101*</span></span>
        - <span data-ttu-id="662f5-397">**Kvantitet:** *50*</span><span class="sxs-lookup"><span data-stu-id="662f5-397">**Quantity:** *50*</span></span>

    > [!NOTE]
    > <span data-ttu-id="662f5-398">Artiklarna och kvantiteterna som anges här är endast exempel.</span><span class="sxs-lookup"><span data-stu-id="662f5-398">The items and quantities that are provided here are only examples.</span></span> <span data-ttu-id="662f5-399">De måste ha lager i det angivna lagerstället.</span><span class="sxs-lookup"><span data-stu-id="662f5-399">They must have stock in the specified warehouse.</span></span>

1. <span data-ttu-id="662f5-400">Välj försäljningsorderrad 1.</span><span class="sxs-lookup"><span data-stu-id="662f5-400">Select sales order line 1.</span></span> <span data-ttu-id="662f5-401">I avsnittet **Försäljningsorderrad** i menyn **Lager** välj **Reservationer**.</span><span class="sxs-lookup"><span data-stu-id="662f5-401">Then, in the **Sales order line** section, on the **Inventory** menu, select **Reservations**.</span></span>
1. <span data-ttu-id="662f5-402">På sidan **Reservation** i åtgärdsfönstret, välj **Reservera parti** och stäng sedan sidan.</span><span class="sxs-lookup"><span data-stu-id="662f5-402">On the **Reservation** page, on the Action Pane, select **Reserve lot**, and then close the page.</span></span>
1. <span data-ttu-id="662f5-403">Upprepa steg 4 och 5 för varje ytterligare försäljningsorderrad.</span><span class="sxs-lookup"><span data-stu-id="662f5-403">Repeat steps 4 and 5 for each additional sales order line.</span></span>
1. <span data-ttu-id="662f5-404">I åtgärdsfönstret på fliken **Lagerställe** välj **Frisläpp till regel för lagerställe**.</span><span class="sxs-lookup"><span data-stu-id="662f5-404">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="662f5-405">Då inträffar följande händelser:</span><span class="sxs-lookup"><span data-stu-id="662f5-405">The following events occur:</span></span>

    - <span data-ttu-id="662f5-406">I systemet bearbetas den skapade utleveransen med hjälp av mallen som inkluderar utskriftssteget för etikett.</span><span class="sxs-lookup"><span data-stu-id="662f5-406">The system processes the created shipment using the template that includes the label printing step.</span></span> <span data-ttu-id="662f5-407">Etikettlayouten används för att definiera etikettens format, och slutresultatet blir en etikett som har fem rader och som skrivs ut på den skrivare som väljs i etikettmallen.</span><span class="sxs-lookup"><span data-stu-id="662f5-407">The label layout will be used to define the format of the label, and the end result will be a label that has five lines and that is printed on the printer that is selected in the label template.</span></span>
    - <span data-ttu-id="662f5-408">Ett nytt fraktsedels-ID genereras för leveranserna.</span><span class="sxs-lookup"><span data-stu-id="662f5-408">A new bill of lading ID is generated for the shipments.</span></span> <span data-ttu-id="662f5-409">Om du har konfigurerat nummerserietilläggen följer påfyllnadsetikett-ID nummerformatet **SSCC-18**.</span><span class="sxs-lookup"><span data-stu-id="662f5-409">If you configured the number sequence extensions, the wave label IDs will follow the **SSCC-18** number format.</span></span> 

<span data-ttu-id="662f5-410">Du kan skriva ut dessa påfyllnadsetiketter igen genom att gå till **Lagerstyrning \> Frågor och rapporter \> Påfyllnadsetiketthistorik**.</span><span class="sxs-lookup"><span data-stu-id="662f5-410">You can reprint these wave labels by going to **Warehouse management \> Inquiries and reports \> Wave label history**.</span></span>

## <a name="scenario-3-wave-label-printing-for-multi-tiered-labels"></a><span data-ttu-id="662f5-411">Scenario 3: utskrift av påfyllnadsetikett för etiketter med flera nivåer</span><span class="sxs-lookup"><span data-stu-id="662f5-411">Scenario 3: Wave label printing for multi-tiered labels</span></span>

<span data-ttu-id="662f5-412">Det här scenariot visar hur du använder funktionen utskrift av påfyllnadsetikett när lagerprocesserna kräver flera nivåer för leveransetiketter.</span><span class="sxs-lookup"><span data-stu-id="662f5-412">This scenario shows how to use the wave label printing functionality when the warehousing processes require several tiers of shipping labels.</span></span> <span data-ttu-id="662f5-413">Till exempel kan separata etiketter behöva skrivas ut för kartonger och lastpallar, och en avbrottsetikett måste skrivas ut för en hel leverans.</span><span class="sxs-lookup"><span data-stu-id="662f5-413">For example, separate labels might have to be printed for cartons and pallets, and a break label might have to be printed for a whole shipment.</span></span> <span data-ttu-id="662f5-414">Avbrottsetiketter är en separat typ av etikett som kan användas som avgränsare mellan rullar och behållare, t.ex. etiketter för leverans-ID och en streckkod, så att etiketterna enkelt kan sorteras när de har skrivits ut.</span><span class="sxs-lookup"><span data-stu-id="662f5-414">Break labels are a separate type of label that can be used as a divider between rolls and containers, such as labels for the shipment ID and a barcode, so that the labels can easily be sorted after they are printed.</span></span>

<span data-ttu-id="662f5-415">Den huvudsakliga skillnaden mellan konfigurationen av scenariot och konfigurationen av scenario 1, förutom att bryta etiketter är aktiverade, är att flera typer av påfyllnadetiketter måste associeras med påfyllnadsetikettmallen och enhetssekvensgruppraderna.</span><span class="sxs-lookup"><span data-stu-id="662f5-415">The main difference between the configuration of this scenario and the configuration of scenario 1, besides the fact that break labels are enabled, is that multiple wave label types must be associated with wave label templates and unit sequence group lines.</span></span> <span data-ttu-id="662f5-416">För att kunna utföra den här konfigurationen ställer du in följande element för det här scenariot:</span><span class="sxs-lookup"><span data-stu-id="662f5-416">To accomplish this configuration, you set up the following elements for this scenario:</span></span>

- <span data-ttu-id="662f5-417">**Metoder för påfyllnadsbearbetning:** du markerar en påfyllnadsetiketts metod som "upprepningsbar", lägger till den två (eller fler) tiderna i påfyllnadsmallen och ställer in olika koder för påfyllnadssteg.</span><span class="sxs-lookup"><span data-stu-id="662f5-417">**Wave processing methods:** You will mark the wave label method as "repeatable," add it two (or more) times to the wave template, and set different wave step codes.</span></span>
- <span data-ttu-id="662f5-418">**Mallar för påfyllnadsetikett:** du kommer att konfigurera mallarna för påfyllnadsetikett och länka dem till påfyllnadsmallen.</span><span class="sxs-lookup"><span data-stu-id="662f5-418">**Wave label templates:** You will configure the wave label templates and link them to the wave template.</span></span> <span data-ttu-id="662f5-419">Varje påfyllnadsetikettmall har en egen typ av påfyllnadsetikett.</span><span class="sxs-lookup"><span data-stu-id="662f5-419">Each wave label template has its own wave label type.</span></span>
- <span data-ttu-id="662f5-420">**Layout för påfyllnadsetiketter:** du kan skapa flera layouter för påfyllnadsetiketter.</span><span class="sxs-lookup"><span data-stu-id="662f5-420">**Wave label layouts:** You will create multiple wave label layouts.</span></span> <span data-ttu-id="662f5-421">Det finns en separat etikettlayout för varje "nivå" med etiketter och det får också en layout för avbrottsetiketten.</span><span class="sxs-lookup"><span data-stu-id="662f5-421">There will be a separate label layout for each "tier" of labels, and there will also be a break label layout.</span></span>

<span data-ttu-id="662f5-422">Det här scenariot visar komplett flöde.</span><span class="sxs-lookup"><span data-stu-id="662f5-422">This scenario shows the end-to-end flow.</span></span>

### <a name="make-demo-data-available"></a><span data-ttu-id="662f5-423">Gör demodata tillgängliga</span><span class="sxs-lookup"><span data-stu-id="662f5-423">Make demo data available</span></span>

<span data-ttu-id="662f5-424">För att följa detta scenario måste du ha demonstrationsdata installerad och du måste välja juridiska personen **USMF**.</span><span class="sxs-lookup"><span data-stu-id="662f5-424">To follow this scenario, you must have demo data installed, and you must select the **USMF** legal entity.</span></span>

### <a name="set-up-a-wave-process-method"></a><span data-ttu-id="662f5-425">Ställa in en påfyllnadsprocessmetod</span><span class="sxs-lookup"><span data-stu-id="662f5-425">Set up a wave process method</span></span>

1. <span data-ttu-id="662f5-426">Gå till **Lagerstyrning \> Inställningar \> Påfyllnader \> Metoder för påfyllnadsprocess**.</span><span class="sxs-lookup"><span data-stu-id="662f5-426">Go to **Warehouse management \> Setup \> Waves \> Wave process methods**.</span></span>
1. <span data-ttu-id="662f5-427">Kontrollera att **waveLabelPrinting** finns i listan.</span><span class="sxs-lookup"><span data-stu-id="662f5-427">Confirm that **waveLabelPrinting** is in the list.</span></span> <span data-ttu-id="662f5-428">Om den inte finns med väljer du **återskapa metoder** i åtgärdsfönstret för att lägga till den.</span><span class="sxs-lookup"><span data-stu-id="662f5-428">If it isn't, select **Regenerate methods** on the Action Pane to add it.</span></span>
1. <span data-ttu-id="662f5-429">För metoden **waveLabelPrinting** markera kryssrutan **gör metoden upprepningsbar**.</span><span class="sxs-lookup"><span data-stu-id="662f5-429">For the **waveLabelPrinting** method, select the **Make method repeatable** check box.</span></span>

### <a name="set-up-a-wave-template"></a><span data-ttu-id="662f5-430">Ställa in en påfyllnadsmall</span><span class="sxs-lookup"><span data-stu-id="662f5-430">Set up a wave template</span></span>

1. <span data-ttu-id="662f5-431">Gå till **Lagerstyrning \> Inställningar \> Påfyllnader \> Påfyllnadsmallar**.</span><span class="sxs-lookup"><span data-stu-id="662f5-431">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
2. <span data-ttu-id="662f5-432">Välj en mall som **62 standard för leverans**.</span><span class="sxs-lookup"><span data-stu-id="662f5-432">Select a template, such as **62 Shipping Default**.</span></span>
3. <span data-ttu-id="662f5-433">På snabbfliken **metoder** flyttar du metoden **utskrift av påfyllnadsetiketter** till kolumnen **valda metoder**.</span><span class="sxs-lookup"><span data-stu-id="662f5-433">On the **Methods** FastTab, move the **Wave label printing** method to the **Selected methods** column.</span></span>
4. <span data-ttu-id="662f5-434">I kolumnen **valda metoder** tilldelar du ett värde för **Kod för påfyllnadssteg** som *kartong* till metoden **utskrift av påfyllnadsetikett**.</span><span class="sxs-lookup"><span data-stu-id="662f5-434">In the **Selected methods** column, assign a **Wave step code** value, such as *Carton*, to the **Wave label printing** method.</span></span> <span data-ttu-id="662f5-435">För mer information om koder för påfyllnadssteg, se [Koder för påfyllnadssteg](wave-step-codes.md).</span><span class="sxs-lookup"><span data-stu-id="662f5-435">For more information about wave step codes, see [Wave step codes](wave-step-codes.md).</span></span>
5. <span data-ttu-id="662f5-436">Flytta metoden **utskrift av påfyllnadsetikett** till kolumnen **valda metoder** en andra gång.</span><span class="sxs-lookup"><span data-stu-id="662f5-436">Move the **Wave label printing** method to the **Selected methods** column a second time.</span></span>
6. <span data-ttu-id="662f5-437">I kolumnen **valda metoder** tilldelar du ett annat värde för **Kod för påfyllnadssteg** som *lastpall* till den andra metoden **utskrift av påfyllnadsetikett**.</span><span class="sxs-lookup"><span data-stu-id="662f5-437">In the **Selected methods** column, assign a different **Wave step code** value, such as *Pallet*, to the second **Wave label printing** method.</span></span> <span data-ttu-id="662f5-438">För mer information om koder för påfyllnadssteg, se [Koder för påfyllnadssteg](wave-step-codes.md).</span><span class="sxs-lookup"><span data-stu-id="662f5-438">For more information about wave step codes, see [Wave step codes](wave-step-codes.md).</span></span>

### <a name="create-three-wave-label-layouts"></a><span data-ttu-id="662f5-439">Skapa tre layouter för påfyllnadsetiketten</span><span class="sxs-lookup"><span data-stu-id="662f5-439">Create three wave label layouts</span></span>

1. <span data-ttu-id="662f5-440">Gå till **Lagerstyrning \> Inställningar \> Dokumentflöde \> Layout för påfyllnadsetikett**.</span><span class="sxs-lookup"><span data-stu-id="662f5-440">Go to **Warehouse management \> Setup \> Document routing \> Wave label layouts**.</span></span>
1. <span data-ttu-id="662f5-441">Skapa en post med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="662f5-441">Create a record that has the following settings:</span></span>

    - <span data-ttu-id="662f5-442">**Etikettlayout-ID:** *kartong*</span><span class="sxs-lookup"><span data-stu-id="662f5-442">**Label layout ID:** *Carton*</span></span>
    - <span data-ttu-id="662f5-443">**Beskrivning:** *kartong (SSCC)*</span><span class="sxs-lookup"><span data-stu-id="662f5-443">**Description:** *Carton (SSCC)*</span></span>

1. <span data-ttu-id="662f5-444">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="662f5-444">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="662f5-445">I åtgärdsfönstret, välj **Inställningar för påfyllnadsetikettrad**.</span><span class="sxs-lookup"><span data-stu-id="662f5-445">On the Action Pane, select **Wave label row settings**.</span></span>

    <span data-ttu-id="662f5-446">Sidan **Inställningar för påfyllnadsetikettrad** visas.</span><span class="sxs-lookup"><span data-stu-id="662f5-446">The **Wave label row settings** page appears.</span></span> <span data-ttu-id="662f5-447">Här kan du konfigurera den dynamiska delen av etiketten.</span><span class="sxs-lookup"><span data-stu-id="662f5-447">Here, you can configure the dynamic part of the label.</span></span>

1. <span data-ttu-id="662f5-448">Lägg till en rad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="662f5-448">Add a row that has the following settings:</span></span>

    - <span data-ttu-id="662f5-449">**Rad-ID:** *WaveLabel*</span><span class="sxs-lookup"><span data-stu-id="662f5-449">**Row Id:** *WaveLabel*</span></span>
    - <span data-ttu-id="662f5-450">**Radtabellnamn:** *WHSWaveLabel*</span><span class="sxs-lookup"><span data-stu-id="662f5-450">**Row table name:** *WHSWaveLabel*</span></span>
    - <span data-ttu-id="662f5-451">**Radens startposition:** *0*</span><span class="sxs-lookup"><span data-stu-id="662f5-451">**Row start position:** *0*</span></span>

        <span data-ttu-id="662f5-452">I det här fältet definieras den lodräta position där raden ska börja etiketten.</span><span class="sxs-lookup"><span data-stu-id="662f5-452">This field defines the vertical position where the row will begin on the label.</span></span>

    - <span data-ttu-id="662f5-453">**Radhöjd:** *0*</span><span class="sxs-lookup"><span data-stu-id="662f5-453">**Row height:** *0*</span></span>

        <span data-ttu-id="662f5-454">I det här fältet definieras höjden på varje rad (i punkter) enligt ZPL-standard.</span><span class="sxs-lookup"><span data-stu-id="662f5-454">This field defines the height of each row (in points), according to the ZPL standard.</span></span> <span data-ttu-id="662f5-455">Radhöjden är positiv för vågräta etiketter och är negativ för lodräta etiketter.</span><span class="sxs-lookup"><span data-stu-id="662f5-455">The row height is positive for horizontal labels and negative for vertical labels.</span></span> <span data-ttu-id="662f5-456">Eftersom det bara finns en rad i det här exemplet kan du ställa in värdet på *0* (noll).</span><span class="sxs-lookup"><span data-stu-id="662f5-456">Because there is just one row in this example, you can set the value to *0* (zero).</span></span>

    - <span data-ttu-id="662f5-457">**Rader per sida:** *1*</span><span class="sxs-lookup"><span data-stu-id="662f5-457">**Rows per page:** *1*</span></span>

        <span data-ttu-id="662f5-458">I det här fältet definieras antalet rader som kan skrivas ut på varje etikett.</span><span class="sxs-lookup"><span data-stu-id="662f5-458">This field defines the number of rows that can be printed on each label.</span></span>

        > [!NOTE]
        > <span data-ttu-id="662f5-459">Den här inställningen gör att en separat ZPL-etikett skrivs ut för varje post i tabellen med påfyllnadsetiketter.</span><span class="sxs-lookup"><span data-stu-id="662f5-459">This setup will cause a separate ZPL label to be printed for each record in the wave labels table.</span></span>

1. <span data-ttu-id="662f5-460">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="662f5-460">Close the page.</span></span>
1. <span data-ttu-id="662f5-461">I åtgärdsfönstret väljer du **Redigera fråga**.</span><span class="sxs-lookup"><span data-stu-id="662f5-461">On the Action Pane, select **Edit query**.</span></span>
1. <span data-ttu-id="662f5-462">I frågeredigerarens dialogruta, på fliken **Intervall** lägg till en rad med följande värden:</span><span class="sxs-lookup"><span data-stu-id="662f5-462">In the query editor dialog box, on the **Range** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="662f5-463">**Tabell:** *Arbetsrader*</span><span class="sxs-lookup"><span data-stu-id="662f5-463">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="662f5-464">**Härlett register:** *Arbetsrader*</span><span class="sxs-lookup"><span data-stu-id="662f5-464">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="662f5-465">**Fält:** *arbetstyp*</span><span class="sxs-lookup"><span data-stu-id="662f5-465">**Field:** *Work type*</span></span>
    - <span data-ttu-id="662f5-466">**Kriterier:** *Plocka*</span><span class="sxs-lookup"><span data-stu-id="662f5-466">**Criteria:** *Pick*</span></span>

    <span data-ttu-id="662f5-467">Den här frågan ser till att endast arbetsrader av typen plockning skrivs ut på etiketten, inte artikelrader av typen radtyp.</span><span class="sxs-lookup"><span data-stu-id="662f5-467">This query ensures that only pick-type work lines will be printed on the label, not put-type work lines.</span></span>

1. <span data-ttu-id="662f5-468">Om du vill kunna skriva ut fraktsedels-ID väljer du på fliken **kopplingar**, sedan **arbetsrader** och kopplar tabellen **leveranser** till den.</span><span class="sxs-lookup"><span data-stu-id="662f5-468">If you want to be able to print the bill of lading ID, on the **Joins** tab, select the **Work lines** table, and join the **Shipments** table to it.</span></span> 
1. <span data-ttu-id="662f5-469">Stäng dialogrutan frågeredigeraren.</span><span class="sxs-lookup"><span data-stu-id="662f5-469">Close the query editor dialog box.</span></span>
1. <span data-ttu-id="662f5-470">På snabbfliken **Layout för skrivartext** finns tre avsnitt där du kan skriva skrivarkod: **rubrikavsnitt**, **brödtext** och **sidfotsavsnitt**.</span><span class="sxs-lookup"><span data-stu-id="662f5-470">The **Printer text Layout** FastTab has three sections where you can write printer code: **Header section**, **Body section**, and **Footer section**.</span></span> <span data-ttu-id="662f5-471">I avsnittet **rubrikavsnitt** i fältet **etikettrubrik** anger du koden för önskad rubrik.</span><span class="sxs-lookup"><span data-stu-id="662f5-471">In the **Header section** section, in the **Label header** field, enter code for the required header.</span></span> <span data-ttu-id="662f5-472">Om du till exempel använder Zebra-skrivare kan du använda följande kod.</span><span class="sxs-lookup"><span data-stu-id="662f5-472">For example, if you're using Zebra printers, you can use the following code.</span></span>


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

1. <span data-ttu-id="662f5-473">I avsnittet **brödtext** i fältet **etikettext** anger du ZPL-koden för önskad text.</span><span class="sxs-lookup"><span data-stu-id="662f5-473">In the **Body section** section, in the **Label body** field, enter ZPL code for the required body.</span></span> <span data-ttu-id="662f5-474">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="662f5-474">Here is an example.</span></span>

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

1. <span data-ttu-id="662f5-475">I avsnittet **brödtext** i fältet **etikettsidfot** anger du ZPL-koden för önskad sidfot.</span><span class="sxs-lookup"><span data-stu-id="662f5-475">In the **Body section** section, in the **Label footer** field, enter ZPL code for the required footer.</span></span> <span data-ttu-id="662f5-476">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="662f5-476">Here is an example.</span></span>

    ```plaintext
    ^PQ1^XZ
    ```

    > [!NOTE]
    > <span data-ttu-id="662f5-477">Installationen kommer att skriva ut en kopia av varje etikett.</span><span class="sxs-lookup"><span data-stu-id="662f5-477">This setup will print one copy of each label.</span></span> <span data-ttu-id="662f5-478">Om du vill ha fler kopior (t.ex. en kopia för varje sida av lastpallen) anger du värdet **n** för avsnittet **\^PQn** i sidfoten till det antal kopior som krävs.</span><span class="sxs-lookup"><span data-stu-id="662f5-478">If you require more copies (for example, one copy for each side of the pallet), set the **n** value for the **\^PQn** section in the footer to the required number of copies.</span></span> <span data-ttu-id="662f5-479">Om du till exempel vill skriva ut fyra kopior av varje etikett anger du **\^PQ4**.</span><span class="sxs-lookup"><span data-stu-id="662f5-479">For example, to print four copies of each label, specify **\^PQ4**.</span></span>

1. <span data-ttu-id="662f5-480">Nu kan du använda din första etikett.</span><span class="sxs-lookup"><span data-stu-id="662f5-480">The first label is now ready to use.</span></span>
1. <span data-ttu-id="662f5-481">Skapa en andra layoutpost med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="662f5-481">Create a second layout record that has the following settings:</span></span>

    - <span data-ttu-id="662f5-482">**Etikettlayout-ID:** *lastpall*</span><span class="sxs-lookup"><span data-stu-id="662f5-482">**Label layout ID:** *Pallet*</span></span>
    - <span data-ttu-id="662f5-483">**Beskrivning:** *lastpall*</span><span class="sxs-lookup"><span data-stu-id="662f5-483">**Description:** *Pallet*</span></span>

1. <span data-ttu-id="662f5-484">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="662f5-484">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="662f5-485">I åtgärdsfönstret, välj **Inställningar för påfyllnadsetikettrad**.</span><span class="sxs-lookup"><span data-stu-id="662f5-485">On the Action Pane, select **Wave label row settings**.</span></span>

    <span data-ttu-id="662f5-486">Sidan **Inställningar för påfyllnadsetikettrad** visas.</span><span class="sxs-lookup"><span data-stu-id="662f5-486">The **Wave label row settings** page appears.</span></span> <span data-ttu-id="662f5-487">Här kan du konfigurera den dynamiska delen av etiketten.</span><span class="sxs-lookup"><span data-stu-id="662f5-487">Here, you can configure the dynamic part of the label.</span></span>

1. <span data-ttu-id="662f5-488">Lägg till en rad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="662f5-488">Add a row that has the following settings:</span></span>

    - <span data-ttu-id="662f5-489">**Rad-ID:** *WaveLabel*</span><span class="sxs-lookup"><span data-stu-id="662f5-489">**Row Id:** *WaveLabel*</span></span>
    - <span data-ttu-id="662f5-490">**Radtabellnamn:** *WHSWaveLabel*</span><span class="sxs-lookup"><span data-stu-id="662f5-490">**Row table name:** *WHSWaveLabel*</span></span>
    - <span data-ttu-id="662f5-491">**Radens startposition:** *0*</span><span class="sxs-lookup"><span data-stu-id="662f5-491">**Row start position:** *0*</span></span>

        <span data-ttu-id="662f5-492">I det här fältet definieras den lodräta position där raden ska börja etiketten.</span><span class="sxs-lookup"><span data-stu-id="662f5-492">This field defines the vertical position where the row will begin on the label.</span></span>

    - <span data-ttu-id="662f5-493">**Radhöjd:** *0*</span><span class="sxs-lookup"><span data-stu-id="662f5-493">**Row height:** *0*</span></span>

        <span data-ttu-id="662f5-494">I det här fältet definieras höjden på varje rad (i punkter) enligt ZPL-standard.</span><span class="sxs-lookup"><span data-stu-id="662f5-494">This field defines the height of each row (in points), according to the ZPL standard.</span></span> <span data-ttu-id="662f5-495">Radhöjden är positiv för vågräta etiketter och är negativ för lodräta etiketter.</span><span class="sxs-lookup"><span data-stu-id="662f5-495">The row height is positive for horizontal labels and negative for vertical labels.</span></span> <span data-ttu-id="662f5-496">Eftersom det bara finns en rad i det här exemplet kan du ställa in värdet på *0* (noll).</span><span class="sxs-lookup"><span data-stu-id="662f5-496">Because there is just one row in this example, you can set the value to *0* (zero).</span></span>

    - <span data-ttu-id="662f5-497">**Rader per sida:** *1*</span><span class="sxs-lookup"><span data-stu-id="662f5-497">**Rows per page:** *1*</span></span>

        <span data-ttu-id="662f5-498">I det här fältet definieras antalet rader som kan skrivas ut på varje etikett.</span><span class="sxs-lookup"><span data-stu-id="662f5-498">This field defines the number of rows that can be printed on each label.</span></span>

        > [!NOTE]
        > <span data-ttu-id="662f5-499">Den här inställningen gör att en separat ZPL-etikett skrivs ut för varje post i tabellen med påfyllnadsetiketter.</span><span class="sxs-lookup"><span data-stu-id="662f5-499">This setup causes a separate ZPL label to be printed for each record in the wave labels table.</span></span>

1. <span data-ttu-id="662f5-500">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="662f5-500">Close the page.</span></span>
1. <span data-ttu-id="662f5-501">I åtgärdsfönstret väljer du **Redigera fråga**.</span><span class="sxs-lookup"><span data-stu-id="662f5-501">On the Action Pane, select **Edit query**.</span></span>
1. <span data-ttu-id="662f5-502">I frågeredigerarens dialogruta, på fliken **Intervall** lägg till en rad med följande värden:</span><span class="sxs-lookup"><span data-stu-id="662f5-502">In the query editor dialog box, on the **Range** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="662f5-503">**Tabell:** *Arbetsrader*</span><span class="sxs-lookup"><span data-stu-id="662f5-503">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="662f5-504">**Härlett register:** *Arbetsrader*</span><span class="sxs-lookup"><span data-stu-id="662f5-504">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="662f5-505">**Fält:** *arbetstyp*</span><span class="sxs-lookup"><span data-stu-id="662f5-505">**Field:** *Work type*</span></span>
    - <span data-ttu-id="662f5-506">**Kriterier:** *Plocka*</span><span class="sxs-lookup"><span data-stu-id="662f5-506">**Criteria:** *Pick*</span></span>

    <span data-ttu-id="662f5-507">Den här frågan ser till att endast arbetsrader av typen plockning skrivs ut på etiketten, inte artikelrader av typen radtyp.</span><span class="sxs-lookup"><span data-stu-id="662f5-507">This query ensures that only pick-type work lines will be printed on the label, not put-type work lines.</span></span>

1. <span data-ttu-id="662f5-508">Om du vill kunna skriva ut fraktsedels-ID väljer du på fliken **kopplingar**, sedan **arbetsrader** och kopplar tabellen **leveranser** till den.</span><span class="sxs-lookup"><span data-stu-id="662f5-508">If you want to be able to print the bill of lading ID, on the **Joins** tab, select the **Work lines** table, and join the **Shipments** table to it.</span></span>
1. <span data-ttu-id="662f5-509">Stäng dialogrutan frågeredigeraren.</span><span class="sxs-lookup"><span data-stu-id="662f5-509">Close the query editor dialog box.</span></span>
1. <span data-ttu-id="662f5-510">På snabbfliken **Layout för skrivartext** finns tre avsnitt där du kan skriva skrivarkod: **rubrikavsnitt**, **brödtext** och **sidfotsavsnitt**.</span><span class="sxs-lookup"><span data-stu-id="662f5-510">The **Printer text Layout** FastTab has three sections where you can write printer code: **Header section**, **Body section**, and **Footer section**.</span></span> <span data-ttu-id="662f5-511">I avsnittet **rubrikavsnitt** i fältet **etikettrubrik** anger du koden för önskad rubrik.</span><span class="sxs-lookup"><span data-stu-id="662f5-511">In the **Header section** section, in the **Label header** field, enter code for the required header.</span></span> <span data-ttu-id="662f5-512">Om du till exempel använder Zebra-skrivare kan du använda följande kod.</span><span class="sxs-lookup"><span data-stu-id="662f5-512">For example, if you're using Zebra printers, you can use the following code.</span></span>

    ```plaintext
    CT~~CD,~CC^~CT~
    ^XA
    ^LH10,10
    ^FO0,0 ^AT ^FD$WHSWaveLabel.WaveLabelId$ ^FS
    ^FO0,75 ^AT ^FD$WHSWorkLine.ShipmentId$ ^FS
    ^FO0,150 ^AT ^FD$WHSShipmentTable.BillOfLadingId$ ^FS
    ```

1. <span data-ttu-id="662f5-513">I avsnittet **brödtext** i fältet **etikettext** anger du ZPL-koden för önskad text.</span><span class="sxs-lookup"><span data-stu-id="662f5-513">In the **Body section** section, in the **Label body** field, enter ZPL code for the required body.</span></span> <span data-ttu-id="662f5-514">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="662f5-514">Here is an example.</span></span>

    ```plaintext
    <Row name="WaveLabel">
    ^FO0,450 ^AT ^FDItem ^FS
    ^FO200,450 ^AT ^FDQuantity ^FS
    ^FO0,[[YPos]] ^AT ^FD$WHSWaveLabel.LabelItemId$ ^FS
    ^FO200,[[YPos]] ^AT ^FD$WHSWaveLabel.QtyWork$ ^FS
    </Row>
    ```

1. <span data-ttu-id="662f5-515">I avsnittet **brödtext** i fältet **etikettsidfot** anger du ZPL-koden för önskad sidfot.</span><span class="sxs-lookup"><span data-stu-id="662f5-515">In the **Body section** section, in the **Label footer** field, enter ZPL code for the required footer.</span></span> <span data-ttu-id="662f5-516">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="662f5-516">Here is an example.</span></span>

    ```plaintext
    ^PQ1^XZ
    ```

    > [!NOTE]
    > <span data-ttu-id="662f5-517">Installationen kommer att skriva ut en kopia av varje etikett.</span><span class="sxs-lookup"><span data-stu-id="662f5-517">This setup will print one copy of each label.</span></span> <span data-ttu-id="662f5-518">Om du vill ha fler kopior (t.ex. en kopia för varje sida av lastpallen) anger du värdet **n** för avsnittet **\^PQn** i sidfoten till det antal kopior som krävs.</span><span class="sxs-lookup"><span data-stu-id="662f5-518">If you require more copies (for example, one copy for each side of the pallet), set the **n** value for the **\^PQn** section in the footer to the required number of copies.</span></span> <span data-ttu-id="662f5-519">Om du till exempel vill skriva ut fyra kopior av varje etikett anger du **\^PQ4**.</span><span class="sxs-lookup"><span data-stu-id="662f5-519">For example, to print four copies of each label, specify **\^PQ4**.</span></span>

1. <span data-ttu-id="662f5-520">Nu kan du använda din andra etikett.</span><span class="sxs-lookup"><span data-stu-id="662f5-520">The second label is now ready to use.</span></span>
1. <span data-ttu-id="662f5-521">Skapa en tredje layoutpost med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="662f5-521">Create a third layout record that has the following settings:</span></span>

    - <span data-ttu-id="662f5-522">**Etikettlayout-ID:** *Avbrott*</span><span class="sxs-lookup"><span data-stu-id="662f5-522">**Label layout ID:** *Break*</span></span>
    - <span data-ttu-id="662f5-523">**Beskrivning:** *avbrottsetikett*</span><span class="sxs-lookup"><span data-stu-id="662f5-523">**Description:** *Break label*</span></span>

1. <span data-ttu-id="662f5-524">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="662f5-524">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="662f5-525">På snabbfliken **Layout för skrivartext** finns tre avsnitt där du kan skriva skrivarkod: **rubrikavsnitt**, **brödtext** och **sidfotsavsnitt**.</span><span class="sxs-lookup"><span data-stu-id="662f5-525">The **Printer text Layout** FastTab has three sections where you can write printer code: **Header section**, **Body section**, and **Footer section**.</span></span> <span data-ttu-id="662f5-526">I avsnittet **rubrikavsnitt** i fältet **etikettrubrik** anger du ZPL-koden för önskad rubrik.</span><span class="sxs-lookup"><span data-stu-id="662f5-526">In the **Header section** section, in the **Label header** field, enter ZPL code for the required header.</span></span> <span data-ttu-id="662f5-527">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="662f5-527">Here is an example.</span></span>

    ```plaintext
    CT~~CD,~CC^~CT~
    ^XA
    ^LH10,10
    ^FO0,0 ^AT ^FD$WHSWorkLine.ShipmentId$ ^FS
    ```

1. <span data-ttu-id="662f5-528">Den här gången behövs ingen brödtext.</span><span class="sxs-lookup"><span data-stu-id="662f5-528">This time, no body is required.</span></span> <span data-ttu-id="662f5-529">Ange därför bara den text som krävs i avsnittet **sidfotsavsnitt**.</span><span class="sxs-lookup"><span data-stu-id="662f5-529">Therefore, just enter the required text in the **Footer section** section.</span></span> <span data-ttu-id="662f5-530">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="662f5-530">Here is an example.</span></span>

    ```plaintext
    ^XZ
    ```

    <span data-ttu-id="662f5-531">Nu kan du använda din tredje etikett.</span><span class="sxs-lookup"><span data-stu-id="662f5-531">The third label is now ready to use.</span></span>

    > [!NOTE]
    > <span data-ttu-id="662f5-532">Den tredje etiketten är en avbrottsetikett som ska användas som avgränsare mellan etikettrullar.</span><span class="sxs-lookup"><span data-stu-id="662f5-532">This third label is a break label that will be used as a divider between label rolls.</span></span>

### <a name="create-two-wave-label-types"></a><span data-ttu-id="662f5-533">Skapa två typer av påfyllnadsetiketten</span><span class="sxs-lookup"><span data-stu-id="662f5-533">Create two wave label types</span></span>

1. <span data-ttu-id="662f5-534">Gå till **Lagerstyrning \> Inställningar \> Dokumentflöde \> Typer av påfyllnadsetikett**.</span><span class="sxs-lookup"><span data-stu-id="662f5-534">Go to **Warehouse management \> Setup \> Document routing \> Wave label types**.</span></span>
1. <span data-ttu-id="662f5-535">Skapa en post med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="662f5-535">Create a record that has the following settings:</span></span>

    - <span data-ttu-id="662f5-536">**Etikettyp:** *kartong*</span><span class="sxs-lookup"><span data-stu-id="662f5-536">**Label type:** *Carton*</span></span>
    - <span data-ttu-id="662f5-537">**Beskrivning:** *kartong*</span><span class="sxs-lookup"><span data-stu-id="662f5-537">**Description:** *Carton*</span></span>

1. <span data-ttu-id="662f5-538">Skapa en andra post med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="662f5-538">Create a second record that has the following settings:</span></span>

    - <span data-ttu-id="662f5-539">**Etikettyp:** *lastpall*</span><span class="sxs-lookup"><span data-stu-id="662f5-539">**Label type:** *Pallet*</span></span>
    - <span data-ttu-id="662f5-540">**Beskrivning:** *lastpall*</span><span class="sxs-lookup"><span data-stu-id="662f5-540">**Description:** *Pallet*</span></span>

### <a name="set-up-unit-sequence-groups"></a><span data-ttu-id="662f5-541">Konfigurera enhetssekvensgrupper</span><span class="sxs-lookup"><span data-stu-id="662f5-541">Set up unit sequence groups</span></span>

1. <span data-ttu-id="662f5-542">Gå till **Lagerstyrning \> Inställningar \> Lagerställe \> Enhetsseriegrupp**.</span><span class="sxs-lookup"><span data-stu-id="662f5-542">Go to **Warehouse management \> Setup \> Warehouse \> Unit sequence groups**.</span></span>
1. <span data-ttu-id="662f5-543">Välj eller skapa en grupp för **Ea Box PL**.</span><span class="sxs-lookup"><span data-stu-id="662f5-543">Select or create an **Ea Box PL** group.</span></span>
1. <span data-ttu-id="662f5-544">För raden **ruta** ange fältet **typ av påfyllnadsnivå** till *kartong*.</span><span class="sxs-lookup"><span data-stu-id="662f5-544">For the **Box** line, set the **Wave level type** field to *Carton*.</span></span>
1. <span data-ttu-id="662f5-545">För raden **PL** ange fältet **typ av påfyllnadsnivå** till *lastpall*.</span><span class="sxs-lookup"><span data-stu-id="662f5-545">For the **PL** line, set the **Wave level type** field to *Pallet*.</span></span>

### <a name="create-wave-label-templates"></a><span data-ttu-id="662f5-546">Skapa mallar för påfyllnadsetikett</span><span class="sxs-lookup"><span data-stu-id="662f5-546">Create wave label templates</span></span>

1. <span data-ttu-id="662f5-547">Gå till **Lagerstyrning \> Inställningar \> Dokumentflöde \> Mall för påfyllnadsetikett**.</span><span class="sxs-lookup"><span data-stu-id="662f5-547">Go to **Warehouse management \> Setup \> Document routing \> Wave label templates**.</span></span>
1. <span data-ttu-id="662f5-548">Skapa en etikettmall med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="662f5-548">Create a label template that has the following settings:</span></span>

    - <span data-ttu-id="662f5-549">**Namn på etikettmallen:** *kartongetiketter*</span><span class="sxs-lookup"><span data-stu-id="662f5-549">**Label template name:** *Carton labels*</span></span>
    - <span data-ttu-id="662f5-550">**Beskrivning:** *kartongetiketter*</span><span class="sxs-lookup"><span data-stu-id="662f5-550">**Description:** *Carton labels*</span></span>
    - <span data-ttu-id="662f5-551">**Kod för påfyllnadssteg:** *kartong*</span><span class="sxs-lookup"><span data-stu-id="662f5-551">**Wave step code:** *Carton*</span></span>
    - <span data-ttu-id="662f5-552">**Lagerställe:** *62*</span><span class="sxs-lookup"><span data-stu-id="662f5-552">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="662f5-553">På snabbfliken **allmänna** i fältet **typ av påfyllnadsetikett** väljer du ett värde som *kartong*.</span><span class="sxs-lookup"><span data-stu-id="662f5-553">On the **General** FastTab, in the **Wave label type** field, select a value, such as *Carton*.</span></span>
1. <span data-ttu-id="662f5-554">På snabbfliken **information om påfyllnadsetikettens mall** och lägg till en rad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="662f5-554">On the **Wave label template details** FastTab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="662f5-555">**Etikettlayout-ID:** *kartong*</span><span class="sxs-lookup"><span data-stu-id="662f5-555">**Label layout ID:** *Carton*</span></span>
    - <span data-ttu-id="662f5-556">**Skrivarnamn:** Välj en lämplig ZPL-skrivare.</span><span class="sxs-lookup"><span data-stu-id="662f5-556">**Printer name:** Select an appropriate ZPL printer.</span></span>
    - <span data-ttu-id="662f5-557">**Kör fråga:** *Ja* (den här inställningen är valfri, men rekommenderas för optimal prestanda.)</span><span class="sxs-lookup"><span data-stu-id="662f5-557">**Run query:** *Yes* (This setting is optional, but it's recommended for optimal performance.)</span></span>

1. <span data-ttu-id="662f5-558">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="662f5-558">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="662f5-559">Valfritt: om du ställer in en kundspecifik etikettdesign måste du skapa en fråga för att hitta kundens konto.</span><span class="sxs-lookup"><span data-stu-id="662f5-559">Optional: If you're setting up a customer-specific label design, you must create a query to find the customer's account.</span></span> <span data-ttu-id="662f5-560">På snabbfliken **information om påfyllnadsetikettens mall** välj **Redigera fråga**.</span><span class="sxs-lookup"><span data-stu-id="662f5-560">On the **Wave label template details** FastTab, select **Edit query**.</span></span> <span data-ttu-id="662f5-561">I frågeredigerarens dialogruta, på fliken **Intervall** lägg till en rad med följande värden:</span><span class="sxs-lookup"><span data-stu-id="662f5-561">Then, in the query editor dialog box, on the **Range** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="662f5-562">**Register:** *försändelser*</span><span class="sxs-lookup"><span data-stu-id="662f5-562">**Table:** *Shipments*</span></span>
    - <span data-ttu-id="662f5-563">**Härlett register:** *försändelser*</span><span class="sxs-lookup"><span data-stu-id="662f5-563">**Derived table:** *Shipments*</span></span>
    - <span data-ttu-id="662f5-564">**Fält:** *Kontonummer*</span><span class="sxs-lookup"><span data-stu-id="662f5-564">**Field:** *Account number*</span></span>
    - <span data-ttu-id="662f5-565">**Kriterier:** Ange relevant kundkontonummer.</span><span class="sxs-lookup"><span data-stu-id="662f5-565">**Criteria:** Enter the relevant customer account number.</span></span>

    <span data-ttu-id="662f5-566">När du är klar klickar du på **OK** för att stänga dialogrutan för frågeredigeraren.</span><span class="sxs-lookup"><span data-stu-id="662f5-566">When you've finished, select **OK** to close the query editor dialog box.</span></span>

1. <span data-ttu-id="662f5-567">I åtgärdsfönstret, välj **Redigera fråga** för att öppna en dialogruta för frågeredigeraren för hela etikettmallen.</span><span class="sxs-lookup"><span data-stu-id="662f5-567">On the Action Pane, select **Edit query** to open the query editor dialog box for the whole label template.</span></span>
1. <span data-ttu-id="662f5-568">I frågeredigerarens dialogruta, på fliken **Sortera** lägg till en rad med följande värden:</span><span class="sxs-lookup"><span data-stu-id="662f5-568">In the query editor dialog box, on the **Sorting** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="662f5-569">**Tabell:** *Arbetsrader*</span><span class="sxs-lookup"><span data-stu-id="662f5-569">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="662f5-570">**Härlett register:** *Arbetsrader*</span><span class="sxs-lookup"><span data-stu-id="662f5-570">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="662f5-571">**Fält:** *referens till läs in rad-ID (post-ID)*</span><span class="sxs-lookup"><span data-stu-id="662f5-571">**Field:** *Reference load line id (Record-ID)*</span></span>
    - <span data-ttu-id="662f5-572">**Sökriktning:** *Stigande*</span><span class="sxs-lookup"><span data-stu-id="662f5-572">**Search direction:** *Ascending*</span></span>

1. <span data-ttu-id="662f5-573">Lägg till en andra rad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="662f5-573">Add a second row that has the following settings:</span></span>

    - <span data-ttu-id="662f5-574">**Tabell:** *Arbetsrader*</span><span class="sxs-lookup"><span data-stu-id="662f5-574">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="662f5-575">**Härlett register:** *Arbetsrader*</span><span class="sxs-lookup"><span data-stu-id="662f5-575">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="662f5-576">**Fält:** *leverans-ID*</span><span class="sxs-lookup"><span data-stu-id="662f5-576">**Field:** *Shipment ID*</span></span>
    - <span data-ttu-id="662f5-577">**Sökriktning:** *Stigande*</span><span class="sxs-lookup"><span data-stu-id="662f5-577">**Search direction:** *Ascending*</span></span>

1. <span data-ttu-id="662f5-578">Stäng dialogrutan för frågeredigeraren genom att välja **OK**.</span><span class="sxs-lookup"><span data-stu-id="662f5-578">Select **OK** to close the query editor dialog box.</span></span>
1. <span data-ttu-id="662f5-579">En meddelande ruta ber dig bekräfta åtgärden grupperingsåterställning.</span><span class="sxs-lookup"><span data-stu-id="662f5-579">A message box prompts you to confirm the grouping reset operation.</span></span> <span data-ttu-id="662f5-580">Klicka på **Ja** när du vill fortsätta.</span><span class="sxs-lookup"><span data-stu-id="662f5-580">Select **Yes** to continue.</span></span>
1. <span data-ttu-id="662f5-581">I åtgärdsfönstret, välj **mallgruppen för påfyllnadsetikett**.</span><span class="sxs-lookup"><span data-stu-id="662f5-581">On the Action Pane, select **Wave label template group**.</span></span>
1. <span data-ttu-id="662f5-582">I dialogrutan **mallgruppen för påfyllnadsetikett** för raden där fältet **Namn på referensfält** anges till *leverans-ID* anger du följande värden:</span><span class="sxs-lookup"><span data-stu-id="662f5-582">In the **Wave label template group** dialog box, for the row where the **Reference field name** field is set to *Shipment ID*, set the following values:</span></span>

    - <span data-ttu-id="662f5-583">**Skriv ut avbrottsetikett:** Markera den här kryssrutan.</span><span class="sxs-lookup"><span data-stu-id="662f5-583">**Print break label:** Select this check box.</span></span>
    - <span data-ttu-id="662f5-584">**Layout-ID för etikett:** Välj en avbrottsetikett.</span><span class="sxs-lookup"><span data-stu-id="662f5-584">**Label layout ID:** Select a break label.</span></span> <span data-ttu-id="662f5-585">(Välj t.ex. etikettlayouten *Avbrott* som du skapade tidigare i det här scenariot.)</span><span class="sxs-lookup"><span data-stu-id="662f5-585">(For example, select the *Break* label layout that you created earlier in this scenario.)</span></span>
    - <span data-ttu-id="662f5-586">**Skrivarnamn:** Välj skrivare för avbrottsetiketten.</span><span class="sxs-lookup"><span data-stu-id="662f5-586">**Printer name:** Select the printer for the break label.</span></span> <span data-ttu-id="662f5-587">(I syfte att dela upp etikettrullar bör du välja samma skrivare som väljs på snabbfliken **information om påfyllnadsetikettens mall**.</span><span class="sxs-lookup"><span data-stu-id="662f5-587">(Typically, for the purpose of splitting label rolls, you should select the same printer that is selected on the **Wave label template details** FastTab.</span></span> <span data-ttu-id="662f5-588">Andra scenarier är dock möjliga.)</span><span class="sxs-lookup"><span data-stu-id="662f5-588">However, other scenarios are possible.)</span></span>

1. <span data-ttu-id="662f5-589">Från raden där fältet **Namn på referensfält** anges till *referens till läs in rad-ID*, markera kryssrutan **etikettversions-ID**.</span><span class="sxs-lookup"><span data-stu-id="662f5-589">For the row where the **Reference field name** field is set to *Reference load line id*, select the **Label build ID** check box.</span></span>

    > [!NOTE]
    > <span data-ttu-id="662f5-590">Med den här inställningen skapas en etikettserie ("kartong 1 av X") per lastrad i hela påfyllnaden, oavsett inställningen för arbetsgrupperingen.</span><span class="sxs-lookup"><span data-stu-id="662f5-590">This setup will create one label sequence ("Carton 1 of X") per load line throughout the wave, regardless of the work grouping setup.</span></span> <span data-ttu-id="662f5-591">Denna etikettserie kan skrivas ut på etikettlayouten.</span><span class="sxs-lookup"><span data-stu-id="662f5-591">This label sequence can be printed on a label layout.</span></span> <span data-ttu-id="662f5-592">Dessutom kommer etiketter för olika försändelser att åtskiljas med den valda avbrottsetiketten.</span><span class="sxs-lookup"><span data-stu-id="662f5-592">Additionally, labels for different shipments will be separated by the selected break label.</span></span>

1. <span data-ttu-id="662f5-593">Klicka på **OK** om du vill stänga dialogrutan **mallgruppen för påfyllnadsetikett**.</span><span class="sxs-lookup"><span data-stu-id="662f5-593">Select **OK** to close the **Wave label template group** dialog box.</span></span>
1. <span data-ttu-id="662f5-594">Skapa en andra etikettmall med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="662f5-594">Create a second label template that has the following settings:</span></span>

    - <span data-ttu-id="662f5-595">**Namn på etikettmallen:** *lastpalletiketter*</span><span class="sxs-lookup"><span data-stu-id="662f5-595">**Label template name:** *Pallet labels*</span></span>
    - <span data-ttu-id="662f5-596">**Beskrivning:** *lastpalletiketter*</span><span class="sxs-lookup"><span data-stu-id="662f5-596">**Description:** *Pallet labels*</span></span>
    - <span data-ttu-id="662f5-597">**Kod för påfyllnadssteg:** *lastpall*</span><span class="sxs-lookup"><span data-stu-id="662f5-597">**Wave step code:** *Pallet*</span></span>
    - <span data-ttu-id="662f5-598">**Lagerställe:** *62*</span><span class="sxs-lookup"><span data-stu-id="662f5-598">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="662f5-599">På snabbfliken **allmänna** i fältet **typ av påfyllnadsetikett** väljer du ett värde som *lastpall*.</span><span class="sxs-lookup"><span data-stu-id="662f5-599">On the **General** FastTab, in the **Wave label type** field, select a value, such as *Pallet*.</span></span>
1. <span data-ttu-id="662f5-600">På snabbfliken **information om påfyllnadsetikettens mall** och lägg till en rad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="662f5-600">On the **Wave label template details** FastTab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="662f5-601">**Etikettlayout-ID:** *lastpall*</span><span class="sxs-lookup"><span data-stu-id="662f5-601">**Label layout ID:** *Pallet*</span></span>
    - <span data-ttu-id="662f5-602">**Skrivarnamn:** Välj en lämplig ZPL-skrivare.</span><span class="sxs-lookup"><span data-stu-id="662f5-602">**Printer name:** Select an appropriate ZPL printer.</span></span>
    - <span data-ttu-id="662f5-603">**Kör fråga:** *Ja* (den här inställningen är valfri, men rekommenderas för optimal prestanda.)</span><span class="sxs-lookup"><span data-stu-id="662f5-603">**Run query:** *Yes* (This setting is optional, but it's recommended for optimal performance.)</span></span>

1. <span data-ttu-id="662f5-604">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="662f5-604">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="662f5-605">Valfritt: om du ställer in en kundspecifik etikettdesign måste du skapa en fråga för att hitta kundens konto.</span><span class="sxs-lookup"><span data-stu-id="662f5-605">Optional: If you're setting up a customer-specific label design, you must create a query to find the customer's account.</span></span> <span data-ttu-id="662f5-606">På snabbfliken **information om påfyllnadsetikettens mall** välj **Redigera fråga**.</span><span class="sxs-lookup"><span data-stu-id="662f5-606">On the **Wave label template details** FastTab, select **Edit query**.</span></span> <span data-ttu-id="662f5-607">I frågeredigerarens dialogruta, på fliken **Intervall** lägg till en rad med följande värden:</span><span class="sxs-lookup"><span data-stu-id="662f5-607">Then, in the query editor dialog box, on the **Range** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="662f5-608">**Register:** *försändelser*</span><span class="sxs-lookup"><span data-stu-id="662f5-608">**Table:** *Shipments*</span></span>
    - <span data-ttu-id="662f5-609">**Härlett register:** *försändelser*</span><span class="sxs-lookup"><span data-stu-id="662f5-609">**Derived table:** *Shipments*</span></span>
    - <span data-ttu-id="662f5-610">**Fält:** *Kontonummer*</span><span class="sxs-lookup"><span data-stu-id="662f5-610">**Field:** *Account number*</span></span>
    - <span data-ttu-id="662f5-611">**Kriterier:** Ange relevant kundkontonummer.</span><span class="sxs-lookup"><span data-stu-id="662f5-611">**Criteria:** Enter the relevant customer account number.</span></span>

    <span data-ttu-id="662f5-612">När du är klar klickar du på **OK** för att stänga dialogrutan för frågeredigeraren.</span><span class="sxs-lookup"><span data-stu-id="662f5-612">When you've finished, select **OK** to close the query editor dialog box.</span></span> 

1. <span data-ttu-id="662f5-613">I åtgärdsfönstret, välj **Redigera fråga** för att öppna en dialogruta för frågeredigeraren för hela etikettmallen.</span><span class="sxs-lookup"><span data-stu-id="662f5-613">On the Action Pane, select **Edit query** to open the query editor dialog box for the whole label template.</span></span>
1. <span data-ttu-id="662f5-614">I frågeredigerarens dialogruta, på fliken **Sortera** lägg till en rad med följande värden:</span><span class="sxs-lookup"><span data-stu-id="662f5-614">In the query editor dialog box, on the **Sorting** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="662f5-615">**Tabell:** *Arbetsrader*</span><span class="sxs-lookup"><span data-stu-id="662f5-615">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="662f5-616">**Härlett register:** *Arbetsrader*</span><span class="sxs-lookup"><span data-stu-id="662f5-616">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="662f5-617">**Fält:** *referens till läs in rad-ID (post-ID)*</span><span class="sxs-lookup"><span data-stu-id="662f5-617">**Field:** *Reference load line id (Record-ID)*</span></span>
    - <span data-ttu-id="662f5-618">**Sökriktning:** *Stigande*</span><span class="sxs-lookup"><span data-stu-id="662f5-618">**Search direction:** *Ascending*</span></span>

1. <span data-ttu-id="662f5-619">Lägg till en andra rad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="662f5-619">Add a second row that has the following settings:</span></span>

    - <span data-ttu-id="662f5-620">**Tabell:** *Arbetsrader*</span><span class="sxs-lookup"><span data-stu-id="662f5-620">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="662f5-621">**Härlett register:** *Arbetsrader*</span><span class="sxs-lookup"><span data-stu-id="662f5-621">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="662f5-622">**Fält:** *leverans-ID*</span><span class="sxs-lookup"><span data-stu-id="662f5-622">**Field:** *Shipment ID*</span></span>
    - <span data-ttu-id="662f5-623">**Sökriktning:** *Stigande*</span><span class="sxs-lookup"><span data-stu-id="662f5-623">**Search direction:** *Ascending*</span></span>

1. <span data-ttu-id="662f5-624">Stäng dialogrutan för frågeredigeraren genom att välja **OK**.</span><span class="sxs-lookup"><span data-stu-id="662f5-624">Select **OK** to close the query editor dialog box.</span></span>
1. <span data-ttu-id="662f5-625">En meddelande ruta ber dig bekräfta åtgärden grupperingsåterställning.</span><span class="sxs-lookup"><span data-stu-id="662f5-625">A message box prompts you to confirm the grouping reset operation.</span></span> <span data-ttu-id="662f5-626">Klicka på **Ja** när du vill fortsätta.</span><span class="sxs-lookup"><span data-stu-id="662f5-626">Select **Yes** to continue.</span></span>
1. <span data-ttu-id="662f5-627">I åtgärdsfönstret, välj **mallgruppen för påfyllnadsetikett**.</span><span class="sxs-lookup"><span data-stu-id="662f5-627">On the Action Pane, select **Wave label template group**.</span></span>
1. <span data-ttu-id="662f5-628">I dialogrutan **mallgruppen för påfyllnadsetikett** för raden där fältet **Namn på referensfält** anges till *leverans-ID* anger du följande värden:</span><span class="sxs-lookup"><span data-stu-id="662f5-628">In the **Wave label template group** dialog box, for the row where the **Reference field name** field is set to *Shipment ID*, set the following values:</span></span>

    - <span data-ttu-id="662f5-629">**Skriv ut avbrottsetikett:** Markera den här kryssrutan.</span><span class="sxs-lookup"><span data-stu-id="662f5-629">**Print break label:** Select this check box.</span></span>
    - <span data-ttu-id="662f5-630">**Layout-ID för etikett:** Välj en avbrottsetikett.</span><span class="sxs-lookup"><span data-stu-id="662f5-630">**Label layout ID:** Select a break label.</span></span> <span data-ttu-id="662f5-631">(Välj t.ex. etikettlayouten *Avbrott* som du skapade tidigare i det här scenariot.)</span><span class="sxs-lookup"><span data-stu-id="662f5-631">(For example, select the *Break* label layout that you created earlier in this scenario.)</span></span>
    - <span data-ttu-id="662f5-632">**Skrivarnamn:** Välj skrivare för avbrottsetiketten.</span><span class="sxs-lookup"><span data-stu-id="662f5-632">**Printer name:** Select the printer for the break label.</span></span> <span data-ttu-id="662f5-633">(I syfte att dela upp etikettrullar bör du välja samma skrivare som väljs på snabbfliken **information om påfyllnadsetikettens mall**.</span><span class="sxs-lookup"><span data-stu-id="662f5-633">(Typically, for the purpose of splitting label rolls, you should select the same printer that is selected on the **Wave label template details** FastTab.</span></span> <span data-ttu-id="662f5-634">Andra scenarier är dock möjliga.)</span><span class="sxs-lookup"><span data-stu-id="662f5-634">However, other scenarios are possible.)</span></span>

1. <span data-ttu-id="662f5-635">Från raden där fältet **Namn på referensfält** anges till *referens till läs in rad-ID*, markera kryssrutan **etikettversions-ID**.</span><span class="sxs-lookup"><span data-stu-id="662f5-635">For the row where the **Reference field name** field is set to *Reference load line id*, select the **Label build ID** check box.</span></span>

    > [!NOTE]
    > <span data-ttu-id="662f5-636">Med den här inställningen skapas en etikettserie ("kartong 1 av X") per lastrad i hela påfyllnaden, oavsett inställningen för arbetsgrupperingen.</span><span class="sxs-lookup"><span data-stu-id="662f5-636">This setup will create one label sequence ("Carton 1 of X") per load line throughout the wave, regardless of the work grouping setup.</span></span> <span data-ttu-id="662f5-637">Denna etikettserie kan skrivas ut på etikettlayouten.</span><span class="sxs-lookup"><span data-stu-id="662f5-637">This label sequence can be printed on a label layout.</span></span> <span data-ttu-id="662f5-638">Dessutom kommer etiketter för olika försändelser att åtskiljas med den valda avbrottsetiketten.</span><span class="sxs-lookup"><span data-stu-id="662f5-638">Additionally, labels for different shipments will be separated by the selected break label.</span></span>

### <a name="configure-number-sequence-extensions"></a><span data-ttu-id="662f5-639">Konfigurera nummerserietillägg</span><span class="sxs-lookup"><span data-stu-id="662f5-639">Configure number sequence extensions</span></span>

<span data-ttu-id="662f5-640">Nummerserietillägg styr GS1 efterlevnaden av specifika nummerserier.</span><span class="sxs-lookup"><span data-stu-id="662f5-640">Number sequence extensions control the GS1 compliance of specific number sequences.</span></span> <span data-ttu-id="662f5-641">Den här konfigurationen är valfri för det aktuella scenariot.</span><span class="sxs-lookup"><span data-stu-id="662f5-641">This configuration is optional for the current scenario.</span></span> <span data-ttu-id="662f5-642">Mer information och instruktioner för konfigurering finns i [Konfigurera tillägg för nummerserier](../warehousing/configure-number-sequence-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="662f5-642">For more information and configuration instructions, see [Configure number sequence extensions](../warehousing/configure-number-sequence-extensions.md).</span></span>

### <a name="create-a-sales-order-and-release-it-to-the-warehouse"></a><span data-ttu-id="662f5-643">Skapa en försäljningsorder och släpp den på lagerstället</span><span class="sxs-lookup"><span data-stu-id="662f5-643">Create a sales order and release it to the warehouse</span></span>

1. <span data-ttu-id="662f5-644">Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="662f5-644">Go to **Sales and marketing \> Sales order \> All sales orders**.</span></span>
1. <span data-ttu-id="662f5-645">Skapa en försäljningsorder med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="662f5-645">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="662f5-646">**Kundkonto:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="662f5-646">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="662f5-647">**Lagerställe:** *62*</span><span class="sxs-lookup"><span data-stu-id="662f5-647">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="662f5-648">Lägg till två försäljningsorderrader:</span><span class="sxs-lookup"><span data-stu-id="662f5-648">Add two sales order lines:</span></span>

    - <span data-ttu-id="662f5-649">Försäljningsorderrad 1:</span><span class="sxs-lookup"><span data-stu-id="662f5-649">Sales order line 1:</span></span>

        - <span data-ttu-id="662f5-650">**Artikelnummer:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="662f5-650">**Item number:** *A0001*</span></span>
        - <span data-ttu-id="662f5-651">**Kvantitet:** *9024*</span><span class="sxs-lookup"><span data-stu-id="662f5-651">**Quantity:** *9024*</span></span>
        - <span data-ttu-id="662f5-652">**Enhet:** *ea* (9024 ea = 376 låda = 47 PL)</span><span class="sxs-lookup"><span data-stu-id="662f5-652">**Unit:** *ea* (9024 ea = 376 Box = 47 PL)</span></span>

    - <span data-ttu-id="662f5-653">Försäljningsorderrad 2:</span><span class="sxs-lookup"><span data-stu-id="662f5-653">Sales order line 2:</span></span>

        - <span data-ttu-id="662f5-654">**Artikelnummer:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="662f5-654">**Item number:** *A0002*</span></span>
        - <span data-ttu-id="662f5-655">**Kvantitet:** *9016*</span><span class="sxs-lookup"><span data-stu-id="662f5-655">**Quantity:** *9016*</span></span>
        - <span data-ttu-id="662f5-656">**Enhet:** *ea* (9016 ea = 322 box = 46 PL)</span><span class="sxs-lookup"><span data-stu-id="662f5-656">**Unit:** *ea* (9016 ea = 322 Box = 46 PL)</span></span>

    > [!NOTE]
    > <span data-ttu-id="662f5-657">Artiklarna och kvantiteterna som anges här är endast exempel.</span><span class="sxs-lookup"><span data-stu-id="662f5-657">The items and quantities that are provided here are only examples.</span></span> <span data-ttu-id="662f5-658">De måste använda den enhetsseriegrupp som du definierade tidigare, och lämpliga enhetskonverteringar från *ea* till *Box* till *PL* måste definieras för dem och de måste ha lager i lagerställe *62*.</span><span class="sxs-lookup"><span data-stu-id="662f5-658">They must use the unit sequence group that you defined earlier, appropriate unit conversions from *ea* to *Box* to *PL* must be defined for them, and they must have stock in warehouse *62*.</span></span> <span data-ttu-id="662f5-659">Mer information finns i [måttenhet och lagerprinciper](unit-measure-stocking-policies.md).</span><span class="sxs-lookup"><span data-stu-id="662f5-659">For more information, see [Unit of measure and stocking policies](unit-measure-stocking-policies.md).</span></span>

1. <span data-ttu-id="662f5-660">Välj försäljningsorderrad 1.</span><span class="sxs-lookup"><span data-stu-id="662f5-660">Select sales order line 1.</span></span> <span data-ttu-id="662f5-661">I avsnittet **Försäljningsorderrad** i menyn **Lager** välj **Reservationer**.</span><span class="sxs-lookup"><span data-stu-id="662f5-661">Then, in the **Sales order line** section, on the **Inventory** menu, select **Reservations**.</span></span>
1. <span data-ttu-id="662f5-662">På sidan **Reservation** i åtgärdsfönstret, välj **Reservera parti** och stäng sedan sidan.</span><span class="sxs-lookup"><span data-stu-id="662f5-662">On the **Reservation** page, on the Action Pane, select **Reserve lot**, and then close the page.</span></span>
1. <span data-ttu-id="662f5-663">Upprepa steg 4 och 5 för försäljningsorderrad 2.</span><span class="sxs-lookup"><span data-stu-id="662f5-663">Repeat steps 4 and 5 for sales order line 2.</span></span>
1. <span data-ttu-id="662f5-664">I åtgärdsfönstret på fliken **Lagerställe** välj **Frisläpp till regel för lagerställe**.</span><span class="sxs-lookup"><span data-stu-id="662f5-664">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="662f5-665">Då inträffar följande händelser:</span><span class="sxs-lookup"><span data-stu-id="662f5-665">The following events occur:</span></span> 

    - <span data-ttu-id="662f5-666">I systemet bearbetas den skapade utleveransen med hjälp av mallen som inkluderar utskriftssteget för etikett.</span><span class="sxs-lookup"><span data-stu-id="662f5-666">The system processes the created shipment by using the template that includes the label printing step.</span></span> <span data-ttu-id="662f5-667">Etikettlayouten används för att definiera etikettens format, och resultatet blir en etikett som skrivs ut på den skrivare som väljs i etikettmallen.</span><span class="sxs-lookup"><span data-stu-id="662f5-667">The label layout will be used to define the format of the label, and the result will be a label that is printed on the printer that is selected in the label template.</span></span>
    - <span data-ttu-id="662f5-668">Påfyllnadsetiketter genereras och skrivs ut.</span><span class="sxs-lookup"><span data-stu-id="662f5-668">Wave labels are generated and printed.</span></span> <span data-ttu-id="662f5-669">Antalet etiketter är lika med antalet kartonger (i det här exemplet är 376 boxetiketter för rad 1, 322 boxetiketter för rad 2, 47 PL-etiketter för rad 1, 47 PL-etiketter för rad 2 och två avbrottsetiketter med leverans-ID).</span><span class="sxs-lookup"><span data-stu-id="662f5-669">The number of labels will equal the number of cartons (in this example, 376 Box labels for line 1, 322 Box labels for line 2, 47 PL labels for line 1, 47 PL labels for line 2, and two break labels that have the shipment ID).</span></span>
    - <span data-ttu-id="662f5-670">Ett nytt fraktsedels-ID genereras för leveranserna.</span><span class="sxs-lookup"><span data-stu-id="662f5-670">A new bill of lading ID is generated for the shipments.</span></span> <span data-ttu-id="662f5-671">Om du har konfigurerat nummerserietilläggen följer påfyllnadsetikett-ID nummerformatet **SSCC-18**.</span><span class="sxs-lookup"><span data-stu-id="662f5-671">If you configured the number sequence extensions, the wave label IDs will follow the **SSCC-18** number format.</span></span> 

<span data-ttu-id="662f5-672">Du kan visa och skriva ut påfyllnadsetiketter på följande sidor:</span><span class="sxs-lookup"><span data-stu-id="662f5-672">You can view and reprint wave labels from the following pages:</span></span>

- <span data-ttu-id="662f5-673">Alla leveranser \> leveransinformation</span><span class="sxs-lookup"><span data-stu-id="662f5-673">All shipments \> Shipment details</span></span>
- <span data-ttu-id="662f5-674">Alla laster \> Läs in information</span><span class="sxs-lookup"><span data-stu-id="662f5-674">All loads \> Load details</span></span>
- <span data-ttu-id="662f5-675">Alla påfyllnader</span><span class="sxs-lookup"><span data-stu-id="662f5-675">All waves</span></span>
- <span data-ttu-id="662f5-676">Påfyllnadsetiketter</span><span class="sxs-lookup"><span data-stu-id="662f5-676">Wave labels</span></span>
- <span data-ttu-id="662f5-677">Etiketthistorik för påfyllnad</span><span class="sxs-lookup"><span data-stu-id="662f5-677">Wave label history</span></span>

<span data-ttu-id="662f5-678">För de flesta av dessa sidor hittar du den relevanta funktionen genom att välja **Påfyllnadsetiketter** i gruppen **Relaterad information** i fliken **leveranser** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="662f5-678">For most of these pages, you can find the relevant function by selecting **Wave labels** in the **Related information** group on the **Shipments** tab of the Action Pane.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]