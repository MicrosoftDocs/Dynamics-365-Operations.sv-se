---
title: Importera remburs
description: I den här proceduren förklaras processen för att importera en remburs.
author: kweekley
manager: AnnBe
ms.date: 02/28/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTable, VendBankAccounts, PurchTable, PurchCreateOrder, InventItemIdLookupPurchase, BankLCImport,  PurchEditLines, VendEditInvoice, SrsReportViewerForm, LedgerJournalTable, LedgerJournalTransVendPaym, VendOpenTrans, SysQueryForm, BankAccountTableLookUp
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3d5539fbd17c880d8bbadd47444c9cc53fce039c
ms.sourcegitcommit: 0c1deb100d0bf6dacd14b328968bbc7a9d92583a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/28/2019
ms.locfileid: "771241"
---
# <a name="import-letter-of-credit"></a><span data-ttu-id="5ba02-103">Importera remburs</span><span class="sxs-lookup"><span data-stu-id="5ba02-103">Import letter of credit</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="5ba02-104">I den här proceduren förklaras processen för att importera en remburs.</span><span class="sxs-lookup"><span data-stu-id="5ba02-104">This procedure walks through the process of importing a letter of credit.</span></span> <span data-ttu-id="5ba02-105">Följande måste ställas in innan du avslutar den här proceduren: bankkreditlimiter, bokföringsprofiler, kreditlimitavtal för bank och säljarens bankdetaljer.</span><span class="sxs-lookup"><span data-stu-id="5ba02-105">The following must be set up before completing this procedure: bank facilities, posting profiles, a bank facility agreement and vendor bank details.</span></span>

<span data-ttu-id="5ba02-106">I den här proceduren används demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="5ba02-106">This procedure uses the USMF demo company.</span></span>


## <a name="create-a-purchase-order-with-letter-of-credit"></a><span data-ttu-id="5ba02-107">Skapa en inköpsorder med remburs</span><span class="sxs-lookup"><span data-stu-id="5ba02-107">Create a Purchase order with Letter of credit</span></span>
1. <span data-ttu-id="5ba02-108">Gå till leverantörsskulder > inköpsorder > Alla inköpsorder.</span><span class="sxs-lookup"><span data-stu-id="5ba02-108">Go to Accounts payable > Purchase orders > All purchase orders.</span></span>
2. <span data-ttu-id="5ba02-109">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="5ba02-109">Click New.</span></span>
3. <span data-ttu-id="5ba02-110">Ange eller välj ett värde i fältet Leverantörskonto.</span><span class="sxs-lookup"><span data-stu-id="5ba02-110">In the Vendor account field, enter or select a value.</span></span>
4. <span data-ttu-id="5ba02-111">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="5ba02-111">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="5ba02-112">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="5ba02-112">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="5ba02-113">Expandera avsnittet Allmänt.</span><span class="sxs-lookup"><span data-stu-id="5ba02-113">Expand the General section.</span></span>
7. <span data-ttu-id="5ba02-114">Ange eller välj ett värde i fältet Plats.</span><span class="sxs-lookup"><span data-stu-id="5ba02-114">In the Site field, enter or select a value.</span></span>
8. <span data-ttu-id="5ba02-115">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="5ba02-115">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="5ba02-116">Ange eller välj ett värde i fältet Lagerställe.</span><span class="sxs-lookup"><span data-stu-id="5ba02-116">In the Warehouse field, enter or select a value.</span></span>
10. <span data-ttu-id="5ba02-117">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="5ba02-117">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="5ba02-118">Ange ett datum i fältet Redovisningsdatum.</span><span class="sxs-lookup"><span data-stu-id="5ba02-118">In the Accounting date field, enter a date.</span></span>
12. <span data-ttu-id="5ba02-119">I fältet Leveransdatum, ange ett datum.</span><span class="sxs-lookup"><span data-stu-id="5ba02-119">In the Delivery date field, enter a date.</span></span>
    * <span data-ttu-id="5ba02-120">Obs! Fältet Bankdokumenttyp bör väljas med värdet Remburs.</span><span class="sxs-lookup"><span data-stu-id="5ba02-120">Note: The 'Bank document type' field should be selected with the value  'Letter of credit'.</span></span>  
13. <span data-ttu-id="5ba02-121">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="5ba02-121">Click OK.</span></span>
14. <span data-ttu-id="5ba02-122">Ange eller välj ett värde i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="5ba02-122">In the Item number field, enter or select a value.</span></span>
15. <span data-ttu-id="5ba02-123">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="5ba02-123">In the list, find and select the desired record.</span></span>
16. <span data-ttu-id="5ba02-124">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="5ba02-124">In the list, click the link in the selected row.</span></span>
17. <span data-ttu-id="5ba02-125">Expandera raddetaljavsnittet.</span><span class="sxs-lookup"><span data-stu-id="5ba02-125">Expand the Line details section.</span></span>
18. <span data-ttu-id="5ba02-126">Klicka på fliken Leverans.</span><span class="sxs-lookup"><span data-stu-id="5ba02-126">Click the Delivery tab.</span></span>
19. <span data-ttu-id="5ba02-127">I fältet Leveransdatum, ange ett datum.</span><span class="sxs-lookup"><span data-stu-id="5ba02-127">In the Delivery date field, enter a date.</span></span>
20. <span data-ttu-id="5ba02-128">I fältet Bekräftat leveransdatum, ange ett datum.</span><span class="sxs-lookup"><span data-stu-id="5ba02-128">In the Confirmed delivery date field, enter a date.</span></span>
21. <span data-ttu-id="5ba02-129">Ange ett tal i fältet Enhetspris.</span><span class="sxs-lookup"><span data-stu-id="5ba02-129">In the Unit price field, enter a number.</span></span>
    * <span data-ttu-id="5ba02-130">Definiera detaljer om rembursen.</span><span class="sxs-lookup"><span data-stu-id="5ba02-130">Define the Letter of credit details.</span></span>  
22. <span data-ttu-id="5ba02-131">Klicka på Hantera i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="5ba02-131">On the Action Pane, click Manage.</span></span>
23. <span data-ttu-id="5ba02-132">Klicka på Remburs/importinkasso.</span><span class="sxs-lookup"><span data-stu-id="5ba02-132">Click Letter of credit / import collection.</span></span>
24. <span data-ttu-id="5ba02-133">I fältet Ansökningsdatum, ange datum och tid.</span><span class="sxs-lookup"><span data-stu-id="5ba02-133">In the Application date field, enter a date and time.</span></span>
    * <span data-ttu-id="5ba02-134">Kontrollera att fältet Bankkonto har ett aktivt bankkonto som standard, baserat på ansökningsdatumet.</span><span class="sxs-lookup"><span data-stu-id="5ba02-134">Verify that the 'Bank account' field has the default active Bank account, which is based on the application date.</span></span>  
25. <span data-ttu-id="5ba02-135">Skriv ett värde i fältet Bankdokumentnummer.</span><span class="sxs-lookup"><span data-stu-id="5ba02-135">In the Bank document number field, type a value.</span></span>
26. <span data-ttu-id="5ba02-136">Ange datum och tid i fältet Inleveransdatum.</span><span class="sxs-lookup"><span data-stu-id="5ba02-136">In the Date of receipt field, enter a date and time.</span></span>
27. <span data-ttu-id="5ba02-137">Expandera bankdokumentavsnittet.</span><span class="sxs-lookup"><span data-stu-id="5ba02-137">Expand the Bank document section.</span></span>
28. <span data-ttu-id="5ba02-138">I fältet Utgångsdatum anger du datum och tid.</span><span class="sxs-lookup"><span data-stu-id="5ba02-138">In the Expiration date field, enter a date and time.</span></span>
29. <span data-ttu-id="5ba02-139">Expandera avsnittet Bankdetaljer.</span><span class="sxs-lookup"><span data-stu-id="5ba02-139">Expand the Bank details section.</span></span>
30. <span data-ttu-id="5ba02-140">Ange eller välj ett värde i fältet Aviserande bank.</span><span class="sxs-lookup"><span data-stu-id="5ba02-140">In the Advising bank field, enter or select a value.</span></span>
31. <span data-ttu-id="5ba02-141">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="5ba02-141">In the list, click the link in the selected row.</span></span>
32. <span data-ttu-id="5ba02-142">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="5ba02-142">Click Save.</span></span>
33. <span data-ttu-id="5ba02-143">Klicka på Hämta inköpsorderförsändelser.</span><span class="sxs-lookup"><span data-stu-id="5ba02-143">Click Fetch purchase order shipments.</span></span>
34. <span data-ttu-id="5ba02-144">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="5ba02-144">Close the page.</span></span>
35. <span data-ttu-id="5ba02-145">Klicka på Inköp i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="5ba02-145">On the Action Pane, click Purchase.</span></span>
36. <span data-ttu-id="5ba02-146">Klicka på Bekräfta.</span><span class="sxs-lookup"><span data-stu-id="5ba02-146">Click Confirm.</span></span>
37. <span data-ttu-id="5ba02-147">Klicka på Hantera i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="5ba02-147">On the Action Pane, click Manage.</span></span>
38. <span data-ttu-id="5ba02-148">Klicka på Remburs/importinkasso.</span><span class="sxs-lookup"><span data-stu-id="5ba02-148">Click Letter of credit / import collection.</span></span>
39. <span data-ttu-id="5ba02-149">Klicka på Process.</span><span class="sxs-lookup"><span data-stu-id="5ba02-149">Click Process.</span></span>
40. <span data-ttu-id="5ba02-150">Klicka på Bekräfta.</span><span class="sxs-lookup"><span data-stu-id="5ba02-150">Click Confirm.</span></span>
    * <span data-ttu-id="5ba02-151">Kontrollera att lokalsaldot minskar inköpsorderbeloppet.</span><span class="sxs-lookup"><span data-stu-id="5ba02-151">Verify that the Facility balance reduces the purchase order amount.</span></span>  <span data-ttu-id="5ba02-152">I det här exemplet är Inköpsbelopp = 500,00 och Kreditlimitgräns = 10000,00 vilket ger Lokalsaldo = 9500,00.</span><span class="sxs-lookup"><span data-stu-id="5ba02-152">In this example, Purchase amount = 500.00,  Facility limit = 10000.00,  therefore, Facility balance = 9500.00.</span></span>  
41. <span data-ttu-id="5ba02-153">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="5ba02-153">Close the page.</span></span>
42. <span data-ttu-id="5ba02-154">Ange ett tal i fältet Enhetspris.</span><span class="sxs-lookup"><span data-stu-id="5ba02-154">In the Unit price field, enter a number.</span></span>
43. <span data-ttu-id="5ba02-155">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="5ba02-155">Click Save.</span></span>
44. <span data-ttu-id="5ba02-156">Klicka på Inköp i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="5ba02-156">On the Action Pane, click Purchase.</span></span>
45. <span data-ttu-id="5ba02-157">Klicka på Bekräfta.</span><span class="sxs-lookup"><span data-stu-id="5ba02-157">Click Confirm.</span></span>
    * <span data-ttu-id="5ba02-158">Ändra rembursen till följd av ändringen i enhetspris.</span><span class="sxs-lookup"><span data-stu-id="5ba02-158">Amend the Letter of credit, due to the change in Unit price.</span></span>  
46. <span data-ttu-id="5ba02-159">Klicka på Hantera i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="5ba02-159">On the Action Pane, click Manage.</span></span>
47. <span data-ttu-id="5ba02-160">Klicka på Remburs/importinkasso.</span><span class="sxs-lookup"><span data-stu-id="5ba02-160">Click Letter of credit / import collection.</span></span>
    * <span data-ttu-id="5ba02-161">Ändra rembursen till följd av ändringen i inköpsenhetspris.</span><span class="sxs-lookup"><span data-stu-id="5ba02-161">Amend the letter of credit, due to the change in Purchase unit price.</span></span>  
48. <span data-ttu-id="5ba02-162">Klicka på Process.</span><span class="sxs-lookup"><span data-stu-id="5ba02-162">Click Process.</span></span>
49. <span data-ttu-id="5ba02-163">Klicka på Ändra.</span><span class="sxs-lookup"><span data-stu-id="5ba02-163">Click Amend.</span></span>
50. <span data-ttu-id="5ba02-164">Klicka på Ta bort.</span><span class="sxs-lookup"><span data-stu-id="5ba02-164">Click Remove.</span></span>
51. <span data-ttu-id="5ba02-165">Klicka på Ja.</span><span class="sxs-lookup"><span data-stu-id="5ba02-165">Click Yes.</span></span>
52. <span data-ttu-id="5ba02-166">Klicka på Hämta inköpsorderförsändelser.</span><span class="sxs-lookup"><span data-stu-id="5ba02-166">Click Fetch purchase order shipments.</span></span>
53. <span data-ttu-id="5ba02-167">Klicka på Process.</span><span class="sxs-lookup"><span data-stu-id="5ba02-167">Click Process.</span></span>
54. <span data-ttu-id="5ba02-168">Klicka på Bekräfta.</span><span class="sxs-lookup"><span data-stu-id="5ba02-168">Click Confirm.</span></span>
    * <span data-ttu-id="5ba02-169">Kontrollera att lokalsaldot minskar inköpsorderbeloppet.</span><span class="sxs-lookup"><span data-stu-id="5ba02-169">Verify that the Facility balance reduces the purchase order amount.</span></span>  <span data-ttu-id="5ba02-170">I det här exemplet är det redigerade Inköpsbelopp = 600,00 och Kreditlimitgräns = 10000,00 vilket ger Lokalsaldo = 9400,00.</span><span class="sxs-lookup"><span data-stu-id="5ba02-170">In this example, edited Purchase amount = 600.00,  Facility limit = 10000.00,  therefore, Facility balance = 9400.00.</span></span>  
55. <span data-ttu-id="5ba02-171">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="5ba02-171">Close the page.</span></span>

## <a name="post-packing-slip"></a><span data-ttu-id="5ba02-172">Bokför följesedel</span><span class="sxs-lookup"><span data-stu-id="5ba02-172">Post Packing slip</span></span>
1. <span data-ttu-id="5ba02-173">Klicka på Ta emot i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="5ba02-173">On the Action Pane, click Receive.</span></span>
2. <span data-ttu-id="5ba02-174">Klicka på Produktinleverans.</span><span class="sxs-lookup"><span data-stu-id="5ba02-174">Click Product receipt.</span></span>
3. <span data-ttu-id="5ba02-175">Ange ett värde i fältet PurchParmTable_Num.</span><span class="sxs-lookup"><span data-stu-id="5ba02-175">In the PurchParmTable_Num field, type a value.</span></span>
    * <span data-ttu-id="5ba02-176">Välj försändelsenumret som skapas med hänvisning till rembursen.</span><span class="sxs-lookup"><span data-stu-id="5ba02-176">Select the Shipment number created with reference to the Letter of credit.</span></span>  
4. <span data-ttu-id="5ba02-177">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="5ba02-177">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="5ba02-178">I fältet Produktinleveransdatum, ange ett datum.</span><span class="sxs-lookup"><span data-stu-id="5ba02-178">In the Product receipt date field, enter a date.</span></span>
6. <span data-ttu-id="5ba02-179">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="5ba02-179">Click OK.</span></span>
7. <span data-ttu-id="5ba02-180">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="5ba02-180">Close the page.</span></span>
8. <span data-ttu-id="5ba02-181">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="5ba02-181">Close the page.</span></span>

## <a name="verify-import-letter-of-credit-status"></a><span data-ttu-id="5ba02-182">Kontrollera statusen för Importremburs.</span><span class="sxs-lookup"><span data-stu-id="5ba02-182">Verify Import letter of credit status</span></span>
1. <span data-ttu-id="5ba02-183">Gå till Kassa- och bankhantering > Remburser > Importremburs och importinkasso.</span><span class="sxs-lookup"><span data-stu-id="5ba02-183">Go to Cash and bank management > Letters of credit > Import letter of credit and import collection.</span></span>
2. <span data-ttu-id="5ba02-184">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="5ba02-184">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="5ba02-185">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="5ba02-185">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="5ba02-186">Kontrollera statusen för Importremburs.</span><span class="sxs-lookup"><span data-stu-id="5ba02-186">Verify the Import letter of credit status.</span></span>     
4. <span data-ttu-id="5ba02-187">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="5ba02-187">Close the page.</span></span>
5. <span data-ttu-id="5ba02-188">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="5ba02-188">Close the page.</span></span>

## <a name="post-purchase-invoice"></a><span data-ttu-id="5ba02-189">Bokför Inköpsfaktura</span><span class="sxs-lookup"><span data-stu-id="5ba02-189">Post purchase invoice</span></span>
1. <span data-ttu-id="5ba02-190">Gå till leverantörsskulder > inköpsorder > Alla inköpsorder.</span><span class="sxs-lookup"><span data-stu-id="5ba02-190">Go to Accounts payable > Purchase orders > All purchase orders.</span></span>
    * <span data-ttu-id="5ba02-191">Välj den inköpsorder som skapades med rembursen.</span><span class="sxs-lookup"><span data-stu-id="5ba02-191">Select the purchase order that was created with letter of credit.</span></span>  
2. <span data-ttu-id="5ba02-192">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="5ba02-192">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="5ba02-193">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="5ba02-193">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="5ba02-194">Klicka på Faktura i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="5ba02-194">On the Action Pane, click Invoice.</span></span>
5. <span data-ttu-id="5ba02-195">Klicka på faktura.</span><span class="sxs-lookup"><span data-stu-id="5ba02-195">Click Invoice.</span></span>
6. <span data-ttu-id="5ba02-196">Ange ett värde i fältet Antal.</span><span class="sxs-lookup"><span data-stu-id="5ba02-196">In the Number field, type a value.</span></span>
7. <span data-ttu-id="5ba02-197">Ange eller välj ett värde i fältet Försändelsenummer.</span><span class="sxs-lookup"><span data-stu-id="5ba02-197">In the Shipment number field, enter or select a value.</span></span>
8. <span data-ttu-id="5ba02-198">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="5ba02-198">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="5ba02-199">Ange ett datum i fältet Fakturadatum.</span><span class="sxs-lookup"><span data-stu-id="5ba02-199">In the Invoice date field, enter a date.</span></span>
10. <span data-ttu-id="5ba02-200">Klicka på Uppdatera matchningsstatus.</span><span class="sxs-lookup"><span data-stu-id="5ba02-200">Click Update match status.</span></span>
11. <span data-ttu-id="5ba02-201">Klicka på Bokför.</span><span class="sxs-lookup"><span data-stu-id="5ba02-201">Click Post.</span></span>
12. <span data-ttu-id="5ba02-202">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="5ba02-202">Close the page.</span></span>
13. <span data-ttu-id="5ba02-203">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="5ba02-203">Close the page.</span></span>

## <a name="verify-import-letter-of-credit-status"></a><span data-ttu-id="5ba02-204">Kontrollera statusen för Importremburs.</span><span class="sxs-lookup"><span data-stu-id="5ba02-204">Verify Import letter of credit status</span></span>
1. <span data-ttu-id="5ba02-205">Gå till Kassa- och bankhantering > Remburser > Importremburs och importinkasso.</span><span class="sxs-lookup"><span data-stu-id="5ba02-205">Go to Cash and bank management > Letters of credit > Import letter of credit and import collection.</span></span>
2. <span data-ttu-id="5ba02-206">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="5ba02-206">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="5ba02-207">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="5ba02-207">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="5ba02-208">Kontrollera importrembursen.</span><span class="sxs-lookup"><span data-stu-id="5ba02-208">Verify the Import letter of credit2.</span></span>  
    * <span data-ttu-id="5ba02-209">Kontrollera: Försändelsestatus = information om fakturerade bankkreditlimiter</span><span class="sxs-lookup"><span data-stu-id="5ba02-209">Validate :  Shipment status = Invoiced  Bank facility details</span></span>  
4. <span data-ttu-id="5ba02-210">Klicka på Visa.</span><span class="sxs-lookup"><span data-stu-id="5ba02-210">Click View.</span></span>
5. <span data-ttu-id="5ba02-211">Klicka på Skriv ut ansökning.</span><span class="sxs-lookup"><span data-stu-id="5ba02-211">Click Print application.</span></span>
6. <span data-ttu-id="5ba02-212">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="5ba02-212">Click OK.</span></span>
    * <span data-ttu-id="5ba02-213">Kontrollera att rembursansökningen skrivs ut.</span><span class="sxs-lookup"><span data-stu-id="5ba02-213">Verify that the Letter of credit application gets printed.</span></span>  
7. <span data-ttu-id="5ba02-214">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="5ba02-214">Close the page.</span></span>
8. <span data-ttu-id="5ba02-215">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="5ba02-215">Close the page.</span></span>
9. <span data-ttu-id="5ba02-216">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="5ba02-216">Close the page.</span></span>

## <a name="post-vendor-payment-journal-for-the-created-purchase-invoice-with-letter-of-credit"></a><span data-ttu-id="5ba02-217">Bokför leverantörsbetalningsjournalen för den skapade inköpsfakturan med remburs</span><span class="sxs-lookup"><span data-stu-id="5ba02-217">Post Vendor payment journal for the created purchase invoice with letter of credit</span></span>
1. <span data-ttu-id="5ba02-218">Gå till Leverantörsreskontra > Betalningar > Betalningsjournal.</span><span class="sxs-lookup"><span data-stu-id="5ba02-218">Go to Accounts payable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="5ba02-219">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="5ba02-219">Click New.</span></span>
3. <span data-ttu-id="5ba02-220">Ange eller välj ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="5ba02-220">In the Name field, enter or select a value.</span></span>
4. <span data-ttu-id="5ba02-221">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="5ba02-221">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="5ba02-222">Klicka på Rader.</span><span class="sxs-lookup"><span data-stu-id="5ba02-222">Click Lines.</span></span>
6. <span data-ttu-id="5ba02-223">Ange ett datum i fältet Datum.</span><span class="sxs-lookup"><span data-stu-id="5ba02-223">In the Date field, enter a date.</span></span>
7. <span data-ttu-id="5ba02-224">Ange önskade värden i fältet Konto.</span><span class="sxs-lookup"><span data-stu-id="5ba02-224">In the Account field, specify the desired values.</span></span>
8. <span data-ttu-id="5ba02-225">Klicka på Kvitta transaktioner.</span><span class="sxs-lookup"><span data-stu-id="5ba02-225">Click Settle transactions.</span></span>
9. <span data-ttu-id="5ba02-226">Expandera avsnittet Summor.</span><span class="sxs-lookup"><span data-stu-id="5ba02-226">Expand the Totals section.</span></span>
10. <span data-ttu-id="5ba02-227">I fältet Visa, välj ett alternativ.</span><span class="sxs-lookup"><span data-stu-id="5ba02-227">In the Show field, select an option.</span></span>
    * <span data-ttu-id="5ba02-228">Kontrollera att fälten Bankdokumentnummer och Försändelsenummer har uppdaterats.</span><span class="sxs-lookup"><span data-stu-id="5ba02-228">Verify that the Bank document number and Shipment number fields have been updated.</span></span>  
11. <span data-ttu-id="5ba02-229">Markera kryssrutan Markera.</span><span class="sxs-lookup"><span data-stu-id="5ba02-229">Select the Mark check box.</span></span>
12. <span data-ttu-id="5ba02-230">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="5ba02-230">Click OK.</span></span>
13. <span data-ttu-id="5ba02-231">Klicka på fliken Betalning.</span><span class="sxs-lookup"><span data-stu-id="5ba02-231">Click the Payment tab.</span></span>
    * <span data-ttu-id="5ba02-232">Kontrollera att fälten Bankdokumentnummer och Försändelsenummer har uppdaterats.</span><span class="sxs-lookup"><span data-stu-id="5ba02-232">Verify that the Bank document number and Shipment number fields have been updated.</span></span>  
14. <span data-ttu-id="5ba02-233">Klicka på Bokför.</span><span class="sxs-lookup"><span data-stu-id="5ba02-233">Click Post.</span></span>
15. <span data-ttu-id="5ba02-234">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="5ba02-234">Close the page.</span></span>
16. <span data-ttu-id="5ba02-235">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="5ba02-235">Close the page.</span></span>

## <a name="verify-import-letter-of-credit-status-after-invoice-paid"></a><span data-ttu-id="5ba02-236">Kontrollera importrembursens status när fakturan är betald</span><span class="sxs-lookup"><span data-stu-id="5ba02-236">Verify Import letter of credit status after Invoice paid</span></span>
1. <span data-ttu-id="5ba02-237">Gå till Kassa- och bankhantering > Remburser > Importremburs och importinkasso.</span><span class="sxs-lookup"><span data-stu-id="5ba02-237">Go to Cash and bank management > Letters of credit > Import letter of credit and import collection.</span></span>
2. <span data-ttu-id="5ba02-238">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="5ba02-238">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="5ba02-239">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="5ba02-239">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="5ba02-240">Kontrollera statusen för Importremburs.</span><span class="sxs-lookup"><span data-stu-id="5ba02-240">Verify the Import letter of credit status.</span></span>   
4. <span data-ttu-id="5ba02-241">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="5ba02-241">Close the page.</span></span>

## <a name="verify-the-bank-facility-limit-and-utilization-report"></a><span data-ttu-id="5ba02-242">Verifiera rapporten över bankkreditlimiter och utnyttjande</span><span class="sxs-lookup"><span data-stu-id="5ba02-242">Verify the Bank facility limit and utilization report</span></span>
1. <span data-ttu-id="5ba02-243">Gå till Kassa- och bankhantering > Förfrågningar och rapporter > Remburser eller garantier > Rapport om bankkreditlimiter och utnyttjande.</span><span class="sxs-lookup"><span data-stu-id="5ba02-243">Go to Cash and bank management > Inquiries and reports > Letters of credit or guarantee > Bank facilities and utilization report.</span></span>
2. <span data-ttu-id="5ba02-244">Expandera avsnittet Poster som ska ingå.</span><span class="sxs-lookup"><span data-stu-id="5ba02-244">Expand the Records to include section.</span></span>
3. <span data-ttu-id="5ba02-245">Klicka på Filter.</span><span class="sxs-lookup"><span data-stu-id="5ba02-245">Click Filter.</span></span>
    * <span data-ttu-id="5ba02-246">Definiera fältet Kriterier med det obligatoriska bankkontot.</span><span class="sxs-lookup"><span data-stu-id="5ba02-246">Define the Criteria field with the required bank account.</span></span>  
4. <span data-ttu-id="5ba02-247">Ange eller välj ett värde i fältet Kriterier.</span><span class="sxs-lookup"><span data-stu-id="5ba02-247">In the Criteria field, enter or select a value.</span></span>
5. <span data-ttu-id="5ba02-248">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="5ba02-248">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="5ba02-249">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="5ba02-249">Click OK.</span></span>
7. <span data-ttu-id="5ba02-250">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="5ba02-250">Click OK.</span></span>
    * <span data-ttu-id="5ba02-251">Kontrollera rapport som innehåller transaktionerna.</span><span class="sxs-lookup"><span data-stu-id="5ba02-251">Verify the report which lists the transactions.</span></span>  
    * <span data-ttu-id="5ba02-252">Kontrollera att rapporten innehåller transaktionerna med bankdokumentnummer, kreditlimitgräns, utnyttjat belopp och lokalsaldobeloppet.</span><span class="sxs-lookup"><span data-stu-id="5ba02-252">Verify the report lists the transactions with Bank document number, Facility limit, utilized amount and the facility balance amount.</span></span>  
8. <span data-ttu-id="5ba02-253">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="5ba02-253">Close the page.</span></span>

