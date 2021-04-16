---
title: EUR-00011 Skapa rapport med lista över försäljning inom EU
description: Den här proceduren går igenom hur du kan skapa en EU-försäljningslisterapport.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, SalesEditLines,  EUSalesList, EUSalesListSelection, SysQueryForm, SysLookup
audience: Application User
ms.reviewer: kfend
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: epopov
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ce3fa3eaae48499e58228d9d6dbf7ce7e97d2bd8
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5821839"
---
# <a name="eur-00011-generate-the-eu-sales-list-report"></a><span data-ttu-id="a4e8a-103">EUR-00011 Skapa rapport med lista över försäljning inom EU</span><span class="sxs-lookup"><span data-stu-id="a4e8a-103">EUR-00011 Generate the EU sales list report</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a4e8a-104">Den här proceduren går igenom hur du kan skapa en EU-försäljningslisterapport.</span><span class="sxs-lookup"><span data-stu-id="a4e8a-104">This procedure walks you through generating the EU sales list report.</span></span> <span data-ttu-id="a4e8a-105">Detta inkluderar överföring av transaktioner för inomeuropeisk handel till EU-försäljningslistan och körning av rapporten.</span><span class="sxs-lookup"><span data-stu-id="a4e8a-105">This includes transferring intra-community trade transactions to the EU sales list and running the report.</span></span> <span data-ttu-id="a4e8a-106">Proceduren innehåller även generering av en transaktion för inomeuropeisk handel för demonstration.</span><span class="sxs-lookup"><span data-stu-id="a4e8a-106">This procedure also includes creating an intra-community trade transaction for demo purposes.</span></span> <span data-ttu-id="a4e8a-107">Mer information om rapportering av EU-säljlista, inklusive nödvändiga krav, finns i hjälpen.</span><span class="sxs-lookup"><span data-stu-id="a4e8a-107">For more information about EU Sales list reporting, including required prerequisites, refer to Help.</span></span>

<span data-ttu-id="a4e8a-108">Den här proceduren gäller för alla europeiska länder/regioner.</span><span class="sxs-lookup"><span data-stu-id="a4e8a-108">This procedure applies to all European countries/regions.</span></span> <span data-ttu-id="a4e8a-109">Proceduren skapades med hjälp av demonstrationsföretaget DEMF och därför används Tyskland som exempelursprungsland.</span><span class="sxs-lookup"><span data-stu-id="a4e8a-109">The procedure was created using the demo data company DEMF and consequently Germany as an exemplar domestic country/region.</span></span> <span data-ttu-id="a4e8a-110">Proceduren använder också Portugal som exempel på ett EU-land.</span><span class="sxs-lookup"><span data-stu-id="a4e8a-110">The procedure also uses Portugal as an exemplar EU country/region.</span></span> <span data-ttu-id="a4e8a-111">Innan du kan slutföra proceduren, måste du konfigurera rapporteringen av EU-försäljningslistan.</span><span class="sxs-lookup"><span data-stu-id="a4e8a-111">Before you can complete this procedure, you must configure EU sales list reporting.</span></span>

<span data-ttu-id="a4e8a-112">Proceduren är avsedd för kamrerer.</span><span class="sxs-lookup"><span data-stu-id="a4e8a-112">This procedure is intended for accountants.</span></span>


## <a name="create-an-intra-community-sales-transaction-for-demo-purposes"></a><span data-ttu-id="a4e8a-113">Skapa en inomeuropeisk försäljningstransaktion för demonstration</span><span class="sxs-lookup"><span data-stu-id="a4e8a-113">Create an intra-community sales transaction for demo purposes</span></span>
1. <span data-ttu-id="a4e8a-114">Gå till Leverantörsreskontra > Order > Alla försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="a4e8a-114">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="a4e8a-115">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="a4e8a-115">Click New.</span></span>
3. <span data-ttu-id="a4e8a-116">Skriv PRT-001 i fältet Kundkonto.</span><span class="sxs-lookup"><span data-stu-id="a4e8a-116">In the Customer account field, type 'PRT-001'.</span></span>
4. <span data-ttu-id="a4e8a-117">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="a4e8a-117">Click OK.</span></span>
5. <span data-ttu-id="a4e8a-118">Skriv "D0001" i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="a4e8a-118">In the Item number field, type 'D0001'.</span></span>
6. <span data-ttu-id="a4e8a-119">Expandera avsnittet Radinformation.</span><span class="sxs-lookup"><span data-stu-id="a4e8a-119">Expand the Line details section.</span></span>
7. <span data-ttu-id="a4e8a-120">Klicka på fliken Inställningar.</span><span class="sxs-lookup"><span data-stu-id="a4e8a-120">Click the Setup tab.</span></span>
8. <span data-ttu-id="a4e8a-121">Skriv FULL i fältet Artikelmomsgrupp.</span><span class="sxs-lookup"><span data-stu-id="a4e8a-121">In the Item sales tax group field, type 'FULL'.</span></span>
9. <span data-ttu-id="a4e8a-122">Klicka på Lägg till rad.</span><span class="sxs-lookup"><span data-stu-id="a4e8a-122">Click Add line.</span></span>
10. <span data-ttu-id="a4e8a-123">Skriv "D0003" i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="a4e8a-123">In the Item number field, type 'D0003'.</span></span>
11. <span data-ttu-id="a4e8a-124">Skriv RED i fältet Artikelmomsgrupp.</span><span class="sxs-lookup"><span data-stu-id="a4e8a-124">In the Item sales tax group field, type 'RED'.</span></span>
12. <span data-ttu-id="a4e8a-125">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="a4e8a-125">Click Save.</span></span>
13. <span data-ttu-id="a4e8a-126">Klicka på Faktura i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="a4e8a-126">On the Action Pane, click Invoice.</span></span>
14. <span data-ttu-id="a4e8a-127">Klicka på Faktura.</span><span class="sxs-lookup"><span data-stu-id="a4e8a-127">Click Invoice.</span></span>
15. <span data-ttu-id="a4e8a-128">Expandera avsnittet Parametrar.</span><span class="sxs-lookup"><span data-stu-id="a4e8a-128">Expand the Parameters section.</span></span>
16. <span data-ttu-id="a4e8a-129">Välj Alla i fältet Kvantitet.</span><span class="sxs-lookup"><span data-stu-id="a4e8a-129">In the Quantity field, select 'All'.</span></span>
17. <span data-ttu-id="a4e8a-130">Expandera avsnittet Inställningar.</span><span class="sxs-lookup"><span data-stu-id="a4e8a-130">Expand the Setup section.</span></span>
18. <span data-ttu-id="a4e8a-131">Ange datumet 01-11-2016 i fältet Fakturadatum.</span><span class="sxs-lookup"><span data-stu-id="a4e8a-131">In the Invoice date field, set the date to '01/11/2016'.</span></span>
19. <span data-ttu-id="a4e8a-132">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="a4e8a-132">Click OK.</span></span>
20. <span data-ttu-id="a4e8a-133">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="a4e8a-133">Click OK.</span></span>

## <a name="transfer-intra-community-trade-transactions-to-the-eu-sales-list"></a><span data-ttu-id="a4e8a-134">Överför transaktioner för inomeuropeisk handel till listan över försäljning inom EU</span><span class="sxs-lookup"><span data-stu-id="a4e8a-134">Transfer intra-community trade transactions to the EU sales list</span></span>
1. <span data-ttu-id="a4e8a-135">Gå till Moms > Deklarationer > Utländsk handel > Lista över försäljning inom EU.</span><span class="sxs-lookup"><span data-stu-id="a4e8a-135">Go to Tax > Declarations > Foreign trade > EU sales list.</span></span>
2. <span data-ttu-id="a4e8a-136">Klicka på Överför.</span><span class="sxs-lookup"><span data-stu-id="a4e8a-136">Click Transfer.</span></span>
3. <span data-ttu-id="a4e8a-137">Välj Ja i fältet Artikel om du vill överföra artikeltransaktioner.</span><span class="sxs-lookup"><span data-stu-id="a4e8a-137">Select Yes in the Item field to transfer item transactions.</span></span>
4. <span data-ttu-id="a4e8a-138">Välj Ja i fältet Tjänst om du vill överföra tjänsttransaktioner.</span><span class="sxs-lookup"><span data-stu-id="a4e8a-138">Select Yes in the Service field to transfer service transactions.</span></span>
    * <span data-ttu-id="a4e8a-139">Du kan även ange ytterligare filter för transaktioner i inomeuropeisk handel du vill överföra.</span><span class="sxs-lookup"><span data-stu-id="a4e8a-139">You can also specify additional filters on intra-community trade transactions to transfer.</span></span>  
5. <span data-ttu-id="a4e8a-140">Klicka på Överför.</span><span class="sxs-lookup"><span data-stu-id="a4e8a-140">Click Transfer.</span></span>
    * <span data-ttu-id="a4e8a-141">Kontrollera att den inomeuropeiska försäljningstransaktionen överförs till EU-försäljningslistan.</span><span class="sxs-lookup"><span data-stu-id="a4e8a-141">Verify that the intra-community sales transaction is successfully transferred to the EU sales list.</span></span>  

## <a name="generate-the-eu-sales-list-report"></a><span data-ttu-id="a4e8a-142">Generera rapport med lista över försäljning inom EU</span><span class="sxs-lookup"><span data-stu-id="a4e8a-142">Generate the EU sales list report</span></span>
1. <span data-ttu-id="a4e8a-143">Klicka på Rapportering.</span><span class="sxs-lookup"><span data-stu-id="a4e8a-143">Click Reporting.</span></span>
2. <span data-ttu-id="a4e8a-144">Markera Varje månad i fältet Rapporteringsperiod.</span><span class="sxs-lookup"><span data-stu-id="a4e8a-144">In the Reporting period field, select 'Monthly'.</span></span>
3. <span data-ttu-id="a4e8a-145">Ange datumet 01-01-2016 i fältet Från datum.</span><span class="sxs-lookup"><span data-stu-id="a4e8a-145">In the From date field, set the date to '01/01/2016'.</span></span>
4. <span data-ttu-id="a4e8a-146">Välj Ja i fältet Generera fil.</span><span class="sxs-lookup"><span data-stu-id="a4e8a-146">Select Yes in the Generate file field.</span></span>
5. <span data-ttu-id="a4e8a-147">Välj Ja i fältet Generera rapport.</span><span class="sxs-lookup"><span data-stu-id="a4e8a-147">Select Yes in the Generate report field.</span></span>
6. <span data-ttu-id="a4e8a-148">Skriv EUSalesList (EU-försäljningslista) i fältet Filnamn.</span><span class="sxs-lookup"><span data-stu-id="a4e8a-148">In the File name field, type 'EUSalesList'.</span></span>
7. <span data-ttu-id="a4e8a-149">Skriv EUSalesList (EU-försäljningslista) i fältet Rapportfilnamn.</span><span class="sxs-lookup"><span data-stu-id="a4e8a-149">In the Report file name field, type 'EUSalesList'.</span></span>
8. <span data-ttu-id="a4e8a-150">Skriv 123 i fältet Registrerings-ID för EU-försäljningslista.</span><span class="sxs-lookup"><span data-stu-id="a4e8a-150">In the EU Sales List Registration ID field, type '123'.</span></span>
    * <span data-ttu-id="a4e8a-151">Det här fältet är bara tillgängligt för Tyskland.</span><span class="sxs-lookup"><span data-stu-id="a4e8a-151">This field is only available for Germany.</span></span>  
    * <span data-ttu-id="a4e8a-152">Du kan även ange ytterligare filter för transaktioner för inomeuropeisk handel du vill ta med i rapporten.</span><span class="sxs-lookup"><span data-stu-id="a4e8a-152">You can also specify additional filters on intra-community trade transactions to include in the report.</span></span>  
9. <span data-ttu-id="a4e8a-153">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="a4e8a-153">Click OK.</span></span>
    * <span data-ttu-id="a4e8a-154">Kontrollera att popup-fönster visas du vill bekräfta att filen och kontrollrapporten hämtas.</span><span class="sxs-lookup"><span data-stu-id="a4e8a-154">Verify that pop-up windows appear to confirm that the file and the control report are being downloaded.</span></span>  

## <a name="mark-eu-sales-list-lines-as-reported"></a><span data-ttu-id="a4e8a-155">Markera rader i EU-försäljningslistan som rapporterade</span><span class="sxs-lookup"><span data-stu-id="a4e8a-155">Mark EU sales list lines as Reported</span></span>
1. <span data-ttu-id="a4e8a-156">Klicka på Markera.</span><span class="sxs-lookup"><span data-stu-id="a4e8a-156">Click Mark.</span></span>
2. <span data-ttu-id="a4e8a-157">Klicka på Markera som rapporterad.</span><span class="sxs-lookup"><span data-stu-id="a4e8a-157">Click Mark as reported.</span></span>
3. <span data-ttu-id="a4e8a-158">Välj raden för fältet Fakturadatum i listan.</span><span class="sxs-lookup"><span data-stu-id="a4e8a-158">In the list, select the row for the Invoice date field.</span></span>
4. <span data-ttu-id="a4e8a-159">Skriv 01/01/2016..01/31/2016 i fältet Kriterier.</span><span class="sxs-lookup"><span data-stu-id="a4e8a-159">In the Criteria field, type '01/01/2016..01/31/2016'.</span></span>
5. <span data-ttu-id="a4e8a-160">Välj raden för fältet Rapporteringsstatus i listan.</span><span class="sxs-lookup"><span data-stu-id="a4e8a-160">In the list, select the row for the Reporting status field.</span></span>
6. <span data-ttu-id="a4e8a-161">Markera Inkluderat i fältet Kriterier.</span><span class="sxs-lookup"><span data-stu-id="a4e8a-161">In the Criteria field, select 'Included'.</span></span>
    * <span data-ttu-id="a4e8a-162">Du kan även ange ytterligare filter för transaktioner för inomeuropeisk handel du vill markera som rapporterade.</span><span class="sxs-lookup"><span data-stu-id="a4e8a-162">You can also specify additional filters on intra-community trade transactions to mark as Reported.</span></span>  
7. <span data-ttu-id="a4e8a-163">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="a4e8a-163">Click OK.</span></span>
8. <span data-ttu-id="a4e8a-164">Välj Rapportet i fältet för val.</span><span class="sxs-lookup"><span data-stu-id="a4e8a-164">In the Selection field, select 'Reported'.</span></span>

## <a name="mark-eu-sales-list-lines-as-closed"></a><span data-ttu-id="a4e8a-165">Markera rader i EU-försäljningslistan som stängda</span><span class="sxs-lookup"><span data-stu-id="a4e8a-165">Mark EU sales list lines as Closed</span></span>
1. <span data-ttu-id="a4e8a-166">Klicka på Markera.</span><span class="sxs-lookup"><span data-stu-id="a4e8a-166">Click Mark.</span></span>
2. <span data-ttu-id="a4e8a-167">Klicka på Markera som stängd.</span><span class="sxs-lookup"><span data-stu-id="a4e8a-167">Click Mark as closed.</span></span>
3. <span data-ttu-id="a4e8a-168">Markera raden för fältet Fakturadatum i listan.</span><span class="sxs-lookup"><span data-stu-id="a4e8a-168">In the list, mark the row for the Invoice date field.</span></span>
4. <span data-ttu-id="a4e8a-169">Skriv 01/01/2016..01/31/2016 i fältet Kriterier.</span><span class="sxs-lookup"><span data-stu-id="a4e8a-169">In the Criteria field, type '01/01/2016..01/31/2016'.</span></span>
5. <span data-ttu-id="a4e8a-170">Markera raden för fältet Rapporteringsstatus i listan.</span><span class="sxs-lookup"><span data-stu-id="a4e8a-170">In the list, mark the row for the Reporting status field.</span></span>
6. <span data-ttu-id="a4e8a-171">Markera Rapporterat i fältet Kriterier.</span><span class="sxs-lookup"><span data-stu-id="a4e8a-171">In the Criteria field, select 'Reported'.</span></span>
    * <span data-ttu-id="a4e8a-172">Du kan även ange ytterligare filter för transaktioner för inomeuropeisk handel du vill markera som stängda.</span><span class="sxs-lookup"><span data-stu-id="a4e8a-172">You can also specify additional filters on intra-community trade transactions to mark as Closed.</span></span>  
7. <span data-ttu-id="a4e8a-173">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="a4e8a-173">Click OK.</span></span>
8. <span data-ttu-id="a4e8a-174">Välj Stängt i fältet för val.</span><span class="sxs-lookup"><span data-stu-id="a4e8a-174">In the Selection field, select 'Closed'.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]