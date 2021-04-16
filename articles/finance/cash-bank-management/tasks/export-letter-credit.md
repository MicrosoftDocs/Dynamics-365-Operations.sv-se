---
title: Exportremburs
description: I den här proceduren förklaras processen för exportremburs.
author: kweekley
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustTable, CustBankAccounts, DefaultDashboard, SalesTableListPage, SalesCreateOrder, SalesTable, BankLCExport, SalesEditLines,  LedgerJournalTable, LedgerJournalTransCustPaym, CustOpenTrans
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 260ef2d05e1f21708817346af2db2841aa6acdd9
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5834798"
---
# <a name="export-letter-of-credit"></a><span data-ttu-id="7b5d7-103">Exportremburs</span><span class="sxs-lookup"><span data-stu-id="7b5d7-103">Export letter of credit</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="7b5d7-104">I den här proceduren förklaras processen för exportremburs.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-104">This procedure walks through the process of the Export letter of credit.</span></span>

<span data-ttu-id="7b5d7-105">En remburs är ett avtal som har utfärdats av en bank, i vilket banken går med på att säkerställa betalningen på uppdrag av köparen om villkoren i avtalet mellan köparen och säljaren uppfylls.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-105">A letter of credit is an agreement that is issued by a bank, in which the bank agrees to ensure payment on behalf of the buyer, if the terms of the agreement between the buyer and seller are met.</span></span>



<span data-ttu-id="7b5d7-106">Kör procedurerna Ställ in bankkreditlimiter och bokföringsprofiler, och Remburs_Skapa ett kreditlimitavtal före den här proceduren.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-106">Run the 'Set up bank facilities and posting profiles' procedure and the 'Letter of Credit_Create a bank facility agreement' procedure prior to this procedure.</span></span> <span data-ttu-id="7b5d7-107">USMF-demonstrationsföretaget måste väljas för att utföra den här proceduren.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-107">The USMF demo company must be selected in order to run this procedure successfully.</span></span>




## <a name="create-sales-order-for-export-letter-of-credit"></a><span data-ttu-id="7b5d7-108">Skapa en försäljningsorder för exportremburs</span><span class="sxs-lookup"><span data-stu-id="7b5d7-108">Create Sales Order for Export letter of credit</span></span>
1. <span data-ttu-id="7b5d7-109">Gå till Leverantörsreskontra > Order > Alla försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-109">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="7b5d7-110">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-110">Click New.</span></span>
3. <span data-ttu-id="7b5d7-111">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Kundkonto.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-111">In the Customer account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="7b5d7-112">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-112">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="7b5d7-113">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-113">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="7b5d7-114">Utöka eller komprimera avsnittet Allmänt.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-114">Expand or collapse the General section.</span></span>
7. <span data-ttu-id="7b5d7-115">Öppna sökningen genom att klicka på listruteknappen i fältet Plats.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-115">In the Site field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="7b5d7-116">Välj platsen där artikeln som ska utlevereras lagras.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-116">Select the Site where the item to be issued is stocked.</span></span>  
8. <span data-ttu-id="7b5d7-117">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-117">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="7b5d7-118">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Lagerställe.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-118">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="7b5d7-119">Välj det lagerställe där artikeln som ska utlevereras lagras.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-119">Select the Warehouse where item to be issued is stocked.</span></span>  
10. <span data-ttu-id="7b5d7-120">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-120">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="7b5d7-121">Obs! Fältet Bankdokumenttyp bör väljas med värdet Remburs.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-121">Note: The Bank document type field should be selected with the value 'Letter of credit'.</span></span>  
11. <span data-ttu-id="7b5d7-122">Välj Remburs i fältet Bankdokumenttyp.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-122">In the Bank document type field, select 'Letter of credit'.</span></span>
12. <span data-ttu-id="7b5d7-123">Utöka eller komprimera avsnittet Leverans.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-123">Expand or collapse the Delivery section.</span></span>
    * <span data-ttu-id="7b5d7-124">Välj Leveransdatumkontroll = Ingen.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-124">Select Delivery date control = None.</span></span>  
13. <span data-ttu-id="7b5d7-125">I fältet Begärt inleveransdatum, ange ett datum.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-125">In the Requested receipt date field, enter a date.</span></span>
14. <span data-ttu-id="7b5d7-126">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-126">Click OK.</span></span>
15. <span data-ttu-id="7b5d7-127">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-127">In the Item number field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="7b5d7-128">Välj den begärda artikeln som ska utlevereras/säljas.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-128">Select the required item to be Issued/Sold.</span></span>  
16. <span data-ttu-id="7b5d7-129">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-129">In the list, find and select the desired record.</span></span>
17. <span data-ttu-id="7b5d7-130">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-130">In the list, click the link in the selected row.</span></span>
18. <span data-ttu-id="7b5d7-131">Ange ett tal i fältet Enhetspris.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-131">In the Unit price field, enter a number.</span></span>
19. <span data-ttu-id="7b5d7-132">Expandera eller dölj avsnittet Raddetaljer.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-132">Expand or collapse the Line details section.</span></span>
20. <span data-ttu-id="7b5d7-133">Klicka på fliken Leverans.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-133">Click the Delivery tab.</span></span>
21. <span data-ttu-id="7b5d7-134">I fältet Begärt transportdatum, ange ett datum.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-134">In the Requested ship date field, enter a date.</span></span>
22. <span data-ttu-id="7b5d7-135">I fältet Bekräftat transportdatum, ange ett datum.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-135">In the Confirmed ship date field, enter a date.</span></span>
23. <span data-ttu-id="7b5d7-136">Klicka på Hantera i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-136">On the Action Pane, click Manage.</span></span>
24. <span data-ttu-id="7b5d7-137">Klicka på Remburs.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-137">Click Letter of credit.</span></span>
25. <span data-ttu-id="7b5d7-138">Skriv ett värde i fältet Bankdokumentnummer.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-138">In the Bank document number field, type a value.</span></span>
26. <span data-ttu-id="7b5d7-139">I fältet Utgångsdatum anger du datum och tid.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-139">In the Expiration date field, enter a date and time.</span></span>
27. <span data-ttu-id="7b5d7-140">Expandera eller dölj avsnittet Bankdetaljer.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-140">Expand or collapse the Bank details section.</span></span>
28. <span data-ttu-id="7b5d7-141">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Utfärdande bank.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-141">In the Issuing bank field, click the drop-down button to open the lookup.</span></span>
29. <span data-ttu-id="7b5d7-142">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-142">In the list, click the link in the selected row.</span></span>
30. <span data-ttu-id="7b5d7-143">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Aviserande bank.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-143">In the Advising bank field, click the drop-down button to open the lookup.</span></span>
31. <span data-ttu-id="7b5d7-144">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-144">In the list, find and select the desired record.</span></span>
32. <span data-ttu-id="7b5d7-145">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-145">In the list, click the link in the selected row.</span></span>
33. <span data-ttu-id="7b5d7-146">Klicka på Hämta försäljningsorderförsändelser.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-146">Click Fetch sales order shipments.</span></span>
34. <span data-ttu-id="7b5d7-147">Klicka på Utfärda bankdokument.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-147">Click Issue bank document.</span></span>
35. <span data-ttu-id="7b5d7-148">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-148">Close the page.</span></span>

## <a name="post-packing-slip"></a><span data-ttu-id="7b5d7-149">Bokför följesedel</span><span class="sxs-lookup"><span data-stu-id="7b5d7-149">Post Packing slip</span></span>
1. <span data-ttu-id="7b5d7-150">Klicka på Plocka och packa i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-150">On the Action Pane, click Pick and pack.</span></span>
2. <span data-ttu-id="7b5d7-151">Klicka på Bokför följesedel.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-151">Click Post packing slip.</span></span>
3. <span data-ttu-id="7b5d7-152">Utöka eller komprimera avsnittet Parametrar.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-152">Expand or collapse the Parameters section.</span></span>
4. <span data-ttu-id="7b5d7-153">Välj "Alla" i fältet Kvantitet.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-153">In the Quantity field, select 'All'.</span></span>
5. <span data-ttu-id="7b5d7-154">Utöka eller komprimera avsnittet Inställningar.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-154">Expand or collapse the Setup section.</span></span>
6. <span data-ttu-id="7b5d7-155">I fältet Följesedel, ange ett datum.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-155">In the Packing slip date field, enter a date.</span></span>
7. <span data-ttu-id="7b5d7-156">Välj försändelsenumret.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-156">Select the Shipment number.</span></span>
8. <span data-ttu-id="7b5d7-157">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-157">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="7b5d7-158">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-158">Click OK.</span></span>
10. <span data-ttu-id="7b5d7-159">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-159">Click OK.</span></span>

## <a name="post-sales-invoice"></a><span data-ttu-id="7b5d7-160">Bokför försäljningsfaktura</span><span class="sxs-lookup"><span data-stu-id="7b5d7-160">Post sales invoice</span></span>
1. <span data-ttu-id="7b5d7-161">Klicka på Faktura i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-161">On the Action Pane, click Invoice.</span></span>
2. <span data-ttu-id="7b5d7-162">Klicka på Faktura.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-162">Click Invoice.</span></span>
3. <span data-ttu-id="7b5d7-163">Utöka eller komprimera avsnittet Översikt.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-163">Expand or collapse the Overview section.</span></span>
4. <span data-ttu-id="7b5d7-164">Välj försändelsenumret.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-164">Select the Shipment number.</span></span>
5. <span data-ttu-id="7b5d7-165">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-165">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="7b5d7-166">Utöka eller komprimera avsnittet Inställningar.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-166">Expand or collapse the Setup section.</span></span>
7. <span data-ttu-id="7b5d7-167">Ange ett datum i fältet Fakturadatum.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-167">In the Invoice date field, enter a date.</span></span>
8. <span data-ttu-id="7b5d7-168">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-168">Click OK.</span></span>
9. <span data-ttu-id="7b5d7-169">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-169">Click OK.</span></span>

## <a name="shipment-document-submitted-status"></a><span data-ttu-id="7b5d7-170">Status för skickade försändelsedokument</span><span class="sxs-lookup"><span data-stu-id="7b5d7-170">Shipment document submitted status</span></span>
1. <span data-ttu-id="7b5d7-171">Klicka på Hantera i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-171">On the Action Pane, click Manage.</span></span>
2. <span data-ttu-id="7b5d7-172">Klicka på Remburs.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-172">Click Letter of credit.</span></span>
3. <span data-ttu-id="7b5d7-173">Utöka eller komprimera avsnittet Rader.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-173">Expand or collapse the Lines section.</span></span>
    * <span data-ttu-id="7b5d7-174">Obs! Fältet Dokument som skickas måste vara inställt på Ja.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-174">Note: The 'Document submitted' field should be set to 'Yes'.</span></span>  

## <a name="verify-export-letter-of-credit"></a><span data-ttu-id="7b5d7-175">Verifiera exportremburs</span><span class="sxs-lookup"><span data-stu-id="7b5d7-175">Verify Export letter of credit</span></span>
1. <span data-ttu-id="7b5d7-176">Gå till Kassa- och bankhantering > Remburser > Exportremburs och importinkasso.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-176">Go to Cash and bank management > Letters of credit > Export letter of credit and import collection.</span></span>
2. <span data-ttu-id="7b5d7-177">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-177">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="7b5d7-178">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-178">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="7b5d7-179">Kontrollera att exportrembursen har försändelsestatusen Fakturerad.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-179">Verify that the Export letter of credit has a Shipment status of 'Invoiced'.</span></span>  

## <a name="customer-payment"></a><span data-ttu-id="7b5d7-180">Kundbetalning</span><span class="sxs-lookup"><span data-stu-id="7b5d7-180">Customer payment</span></span>
1. <span data-ttu-id="7b5d7-181">Gå till Kundreskontra > Betalningar > Betalningsjournal.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-181">Go to Accounts receivable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="7b5d7-182">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-182">Click New.</span></span>
3. <span data-ttu-id="7b5d7-183">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-183">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="7b5d7-184">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-184">In the Name field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="7b5d7-185">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-185">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="7b5d7-186">Klicka på Rader.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-186">Click Lines.</span></span>
7. <span data-ttu-id="7b5d7-187">Ange ett datum i fältet Datum.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-187">In the Date field, enter a date.</span></span>
8. <span data-ttu-id="7b5d7-188">Ange önskade värden i fältet Konto.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-188">In the Account field, specify the desired values.</span></span>
9. <span data-ttu-id="7b5d7-189">Klicka på Kvittning.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-189">Click Settlement.</span></span>
10. <span data-ttu-id="7b5d7-190">Markera kryssrutan i rubriken för Summor.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-190">Select the check box on the header of Totals.</span></span>
    * <span data-ttu-id="7b5d7-191">Obs! Ställ in fältet Visa till Remburs.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-191">Note: Set the Show field to 'Letter of credit'.</span></span>  
11. <span data-ttu-id="7b5d7-192">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-192">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="7b5d7-193">Markera eller avmarkera kryssrutan Markera.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-193">Select or clear the Mark check box.</span></span>
13. <span data-ttu-id="7b5d7-194">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-194">Click OK.</span></span>
14. <span data-ttu-id="7b5d7-195">Klicka på fliken Betalning.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-195">Click the Payment tab.</span></span>
    * <span data-ttu-id="7b5d7-196">Kontrollera informationen om bankdokumentnumret och försändelsenumret</span><span class="sxs-lookup"><span data-stu-id="7b5d7-196">Verify Bank document number and Shipment number details</span></span>  
15. <span data-ttu-id="7b5d7-197">Klicka på Bokför.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-197">Click Post.</span></span>

## <a name="verify-export-letter-of-credit-after-payment"></a><span data-ttu-id="7b5d7-198">Verifiera exportremburs efter betalning</span><span class="sxs-lookup"><span data-stu-id="7b5d7-198">Verify Export letter of credit after payment</span></span>
1. <span data-ttu-id="7b5d7-199">Gå till Kassa- och bankhantering > Remburser > Exportremburs och importinkasso.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-199">Go to Cash and bank management > Letters of credit > Export letter of credit and import collection.</span></span>
2. <span data-ttu-id="7b5d7-200">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-200">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="7b5d7-201">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-201">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="7b5d7-202">Kontrollera att Försändelsens status = Betalning mottagen och att Saldobelopp = 0,00.</span><span class="sxs-lookup"><span data-stu-id="7b5d7-202">Verify Shipment status = Payment received and balance amount = 0.00.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]