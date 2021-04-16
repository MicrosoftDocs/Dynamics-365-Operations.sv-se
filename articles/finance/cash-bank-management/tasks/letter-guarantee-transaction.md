---
title: Garantitransaktion
description: I den här proceduren förklaras processen för garanti.
author: kweekley
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: Reasons, SalesTableListPage, SalesCreateOrder, SalesTable, BankLGRequestForm, BankLGRequestFormRequest, BankLGGuarantee, BankLGFormSubmitToBank, BankDocumentAgreementLineLookup, BankLGFormReceiveFromBank, LedgerJournalTable, LedgerJournalTransDaily, BankLGRequestFormGiveToBeneficiary, BankLGFormGiveToBeneficiary, BankLGRequestFormIncreaseValue, BankLGFormIncreaseValue, BankLGRequestFormLiquidate, BankLGFormLiquidate
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 089515287fc5706983b10614f69b4b1cd90178c5
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5834726"
---
# <a name="letter-of-guarantee-transaction"></a><span data-ttu-id="273f3-103">Garantitransaktion</span><span class="sxs-lookup"><span data-stu-id="273f3-103">Letter of guarantee transaction</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="273f3-104">I den här proceduren förklaras processen för garanti.</span><span class="sxs-lookup"><span data-stu-id="273f3-104">This procedure walks through the Letter of guarantee process.</span></span>



<span data-ttu-id="273f3-105">Följande uppgifter måste slutföras innan du avslutar den här proceduren:</span><span class="sxs-lookup"><span data-stu-id="273f3-105">The following tasks must be complete before completing this procedure:</span></span>

- <span data-ttu-id="273f3-106">Ställ in bankkreditlimiter och bokföringsprofiler för garanti.</span><span class="sxs-lookup"><span data-stu-id="273f3-106">Set up bank facilities and posting profiles for a letter of guarantee.</span></span>

- <span data-ttu-id="273f3-107">Skapa ett kreditlimitavtal för en garanti.</span><span class="sxs-lookup"><span data-stu-id="273f3-107">Create a bank facility agreement for a letter of guarantee.</span></span>



<span data-ttu-id="273f3-108">I den här proceduren används demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="273f3-108">This procedure uses the USMF demo company.</span></span>


## <a name="create-sales-order-with-letter-of-guarantee"></a><span data-ttu-id="273f3-109">Skapa försäljningsorder med garanti</span><span class="sxs-lookup"><span data-stu-id="273f3-109">Create Sales Order with Letter of Guarantee</span></span>
1. <span data-ttu-id="273f3-110">Gå till Leverantörsreskontra > Order > Alla försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="273f3-110">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="273f3-111">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="273f3-111">Click New.</span></span>
3. <span data-ttu-id="273f3-112">I fältet Kundkonto, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="273f3-112">In the Customer account field, enter or select a value.</span></span>
4. <span data-ttu-id="273f3-113">Expandera avsnittet Allmänt.</span><span class="sxs-lookup"><span data-stu-id="273f3-113">Expand the General section.</span></span>
5. <span data-ttu-id="273f3-114">Ange eller välj ett värde i fältet Plats.</span><span class="sxs-lookup"><span data-stu-id="273f3-114">In the Site field, enter or select a value.</span></span>
6. <span data-ttu-id="273f3-115">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="273f3-115">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="273f3-116">Ange eller välj ett värde i fältet Lagerställe.</span><span class="sxs-lookup"><span data-stu-id="273f3-116">In the Warehouse field, enter or select a value.</span></span>
8. <span data-ttu-id="273f3-117">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="273f3-117">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="273f3-118">Välj Garanti i fältet Bankdokumenttyp.</span><span class="sxs-lookup"><span data-stu-id="273f3-118">In the Bank document type field, select 'Letter of guarantee'.</span></span>
10. <span data-ttu-id="273f3-119">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="273f3-119">Click OK.</span></span>
11. <span data-ttu-id="273f3-120">Ange eller välj ett värde i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="273f3-120">In the Item number field, enter or select a value.</span></span>
12. <span data-ttu-id="273f3-121">Ange ett tal i fältet Enhetspris.</span><span class="sxs-lookup"><span data-stu-id="273f3-121">In the Unit price field, enter a number.</span></span>
13. <span data-ttu-id="273f3-122">Expandera avsnittet Radinformation.</span><span class="sxs-lookup"><span data-stu-id="273f3-122">Expand the Line details section.</span></span>
14. <span data-ttu-id="273f3-123">Klicka på fliken Leverans.</span><span class="sxs-lookup"><span data-stu-id="273f3-123">Click the Delivery tab.</span></span>
    * <span data-ttu-id="273f3-124">Obs! Välj Leveransdatumkontroll = Ingen.</span><span class="sxs-lookup"><span data-stu-id="273f3-124">Note: Select Delivery date control = None</span></span>  
15. <span data-ttu-id="273f3-125">I fältet Begärt transportdatum, ange ett datum.</span><span class="sxs-lookup"><span data-stu-id="273f3-125">In the Requested ship date field, enter a date.</span></span>
16. <span data-ttu-id="273f3-126">I fältet Bekräftat transportdatum, ange ett datum.</span><span class="sxs-lookup"><span data-stu-id="273f3-126">In the Confirmed ship date field, enter a date.</span></span>

## <a name="process-letter-of-guarantee_request"></a><span data-ttu-id="273f3-127">Bearbeta garanti_begäran</span><span class="sxs-lookup"><span data-stu-id="273f3-127">Process letter of guarantee_Request</span></span>
1. <span data-ttu-id="273f3-128">Klicka på Hantera i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="273f3-128">On the Action Pane, click Manage.</span></span>
2. <span data-ttu-id="273f3-129">Klicka på Garanti.</span><span class="sxs-lookup"><span data-stu-id="273f3-129">Click Letter of guarantee.</span></span>
3. <span data-ttu-id="273f3-130">I fönstret Åtgärd, klicka på Garanti.</span><span class="sxs-lookup"><span data-stu-id="273f3-130">On the Action Pane, click Letter of guarantee.</span></span>
4. <span data-ttu-id="273f3-131">Klicka på Begäran om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="273f3-131">Click Request to open the drop dialog.</span></span>
5. <span data-ttu-id="273f3-132">Ange eller välj ett värde i fältet Typ.</span><span class="sxs-lookup"><span data-stu-id="273f3-132">In the Type field, enter or select a value.</span></span>
6. <span data-ttu-id="273f3-133">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="273f3-133">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="273f3-134">Ange ett nummer i fältet Värde.</span><span class="sxs-lookup"><span data-stu-id="273f3-134">In the Value field, enter a number.</span></span>
8. <span data-ttu-id="273f3-135">I fältet Utgångsdatum anger du datum och tid.</span><span class="sxs-lookup"><span data-stu-id="273f3-135">In the Expiration date field, enter a date and time.</span></span>
9. <span data-ttu-id="273f3-136">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="273f3-136">Click OK.</span></span>
10. <span data-ttu-id="273f3-137">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="273f3-137">Close the page.</span></span>

## <a name="process-letter-of-guarantee_submit-to-bank"></a><span data-ttu-id="273f3-138">Bearbeta garanti_Skicka till bank</span><span class="sxs-lookup"><span data-stu-id="273f3-138">Process letter of guarantee_Submit to bank</span></span>
1. <span data-ttu-id="273f3-139">Gå till Kassa- och bankhantering > Garanti > Garanti.</span><span class="sxs-lookup"><span data-stu-id="273f3-139">Go to Cash and bank management > Letters of guarantee > Letters of guarantee.</span></span>
2. <span data-ttu-id="273f3-140">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="273f3-140">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="273f3-141">Klicka på Skicka till bank för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="273f3-141">Click Submit to bank to open the drop dialog.</span></span>
4. <span data-ttu-id="273f3-142">Ange eller välj ett värde i fältet Bankkonto.</span><span class="sxs-lookup"><span data-stu-id="273f3-142">In the Bank account field, enter or select a value.</span></span>
5. <span data-ttu-id="273f3-143">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="273f3-143">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="273f3-144">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="273f3-144">Click OK.</span></span>

## <a name="process-letter-of-guarantee_receive-from-bank"></a><span data-ttu-id="273f3-145">Bearbeta garanti_Ta emot från bank</span><span class="sxs-lookup"><span data-stu-id="273f3-145">Process letter of guarantee_Receive from bank</span></span>
1. <span data-ttu-id="273f3-146">Klicka på Ta emot från bank för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="273f3-146">Click Receive from bank to open the drop dialog.</span></span>
2. <span data-ttu-id="273f3-147">I fältet Banknummer, skriv ett värde.</span><span class="sxs-lookup"><span data-stu-id="273f3-147">In the Bank number field, type a value.</span></span>
    * <span data-ttu-id="273f3-148">Kontrollera värdena i de beräknade marginal- och utgiftsfälten.</span><span class="sxs-lookup"><span data-stu-id="273f3-148">Verify the values in the calculated Margin and Expense fields.</span></span>  
3. <span data-ttu-id="273f3-149">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="273f3-149">Click OK.</span></span>
4. <span data-ttu-id="273f3-150">Expandera avsnittet Åtgärder.</span><span class="sxs-lookup"><span data-stu-id="273f3-150">Expand the Actions section.</span></span>
    * <span data-ttu-id="273f3-151">Kontrollera posten Ta emot från bank.</span><span class="sxs-lookup"><span data-stu-id="273f3-151">Verify the 'Receive from bank' record.</span></span>  
5. <span data-ttu-id="273f3-152">Klicka för att följa länken i fältet Journalbatchnummer.</span><span class="sxs-lookup"><span data-stu-id="273f3-152">Click to follow the link in the Journal batch number field.</span></span>
6. <span data-ttu-id="273f3-153">Klicka på Rader.</span><span class="sxs-lookup"><span data-stu-id="273f3-153">Click Lines.</span></span>
    * <span data-ttu-id="273f3-154">Kontrollera bokföringen av journalposter.</span><span class="sxs-lookup"><span data-stu-id="273f3-154">Verify the posting of journal entries.</span></span>  
7. <span data-ttu-id="273f3-155">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="273f3-155">Close the page.</span></span>

## <a name="process-letter-of-guarantee_give-to-beneficiary"></a><span data-ttu-id="273f3-156">Bearbeta garanti_Ge till mottagare</span><span class="sxs-lookup"><span data-stu-id="273f3-156">Process letter of guarantee_Give to beneficiary</span></span>
1. <span data-ttu-id="273f3-157">Gå till Leverantörsreskontra > Order > Alla försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="273f3-157">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="273f3-158">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="273f3-158">In the list, click the link in the selected row.</span></span>
3. <span data-ttu-id="273f3-159">Klicka på Hantera i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="273f3-159">On the Action Pane, click Manage.</span></span>
4. <span data-ttu-id="273f3-160">Klicka på Garanti.</span><span class="sxs-lookup"><span data-stu-id="273f3-160">Click Letter of guarantee.</span></span>
5. <span data-ttu-id="273f3-161">I fönstret Åtgärd, klicka på Garanti.</span><span class="sxs-lookup"><span data-stu-id="273f3-161">On the Action Pane, click Letter of guarantee.</span></span>
6. <span data-ttu-id="273f3-162">Klicka på Ge till mottagare för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="273f3-162">Click Give to beneficiary to open the drop dialog.</span></span>
7. <span data-ttu-id="273f3-163">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="273f3-163">Click OK.</span></span>
8. <span data-ttu-id="273f3-164">Gå till Kassa- och bankhantering > Garanti > Garanti.</span><span class="sxs-lookup"><span data-stu-id="273f3-164">Go to Cash and bank management > Letters of guarantee > Letters of guarantee.</span></span>
9. <span data-ttu-id="273f3-165">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="273f3-165">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="273f3-166">Klicka på Ge till mottagare för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="273f3-166">Click Give to beneficiary to open the drop dialog.</span></span>
11. <span data-ttu-id="273f3-167">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="273f3-167">Click OK.</span></span>
12. <span data-ttu-id="273f3-168">Expandera avsnittet Åtgärder.</span><span class="sxs-lookup"><span data-stu-id="273f3-168">Expand the Actions section.</span></span>
    * <span data-ttu-id="273f3-169">Validera posten Ge till mottagare.</span><span class="sxs-lookup"><span data-stu-id="273f3-169">Validate the 'Give to beneficiary' record.</span></span>  

## <a name="process-letter-of-guarantee_increase-value"></a><span data-ttu-id="273f3-170">Bearbeta garanti_Öka värde</span><span class="sxs-lookup"><span data-stu-id="273f3-170">Process letter of guarantee_Increase value</span></span>
1. <span data-ttu-id="273f3-171">Gå till Leverantörsreskontra > Order > Alla försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="273f3-171">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="273f3-172">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="273f3-172">In the list, click the link in the selected row.</span></span>
3. <span data-ttu-id="273f3-173">Klicka på Hantera i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="273f3-173">On the Action Pane, click Manage.</span></span>
4. <span data-ttu-id="273f3-174">Klicka på Garanti.</span><span class="sxs-lookup"><span data-stu-id="273f3-174">Click Letter of guarantee.</span></span>
5. <span data-ttu-id="273f3-175">I fönstret Åtgärd, klicka på Garanti.</span><span class="sxs-lookup"><span data-stu-id="273f3-175">On the Action Pane, click Letter of guarantee.</span></span>
6. <span data-ttu-id="273f3-176">Klicka på Öka värde för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="273f3-176">Click Increase value to open the drop dialog.</span></span>
7. <span data-ttu-id="273f3-177">I fältet Värde att lägga till, ange ett värde.</span><span class="sxs-lookup"><span data-stu-id="273f3-177">In the Value to add field, enter a number.</span></span>
8. <span data-ttu-id="273f3-178">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="273f3-178">Click OK.</span></span>
9. <span data-ttu-id="273f3-179">Gå till Kassa- och bankhantering > Garanti > Garanti.</span><span class="sxs-lookup"><span data-stu-id="273f3-179">Go to Cash and bank management > Letters of guarantee > Letters of guarantee.</span></span>
10. <span data-ttu-id="273f3-180">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="273f3-180">In the list, find and select the desired record.</span></span>
11. <span data-ttu-id="273f3-181">Klicka på Öka värde för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="273f3-181">Click Increase value to open the drop dialog.</span></span>
12. <span data-ttu-id="273f3-182">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="273f3-182">Click OK.</span></span>
13. <span data-ttu-id="273f3-183">Expandera avsnittet Åtgärder.</span><span class="sxs-lookup"><span data-stu-id="273f3-183">Expand the Actions section.</span></span>
    * <span data-ttu-id="273f3-184">Kontrollera posten Öka värde.</span><span class="sxs-lookup"><span data-stu-id="273f3-184">Verify the 'Increase value' record.</span></span>  
14. <span data-ttu-id="273f3-185">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="273f3-185">In the list, find and select the desired record.</span></span>
15. <span data-ttu-id="273f3-186">Klicka för att följa länken i fältet Journalbatchnummer.</span><span class="sxs-lookup"><span data-stu-id="273f3-186">Click to follow the link in the Journal batch number field.</span></span>
16. <span data-ttu-id="273f3-187">Klicka på Rader.</span><span class="sxs-lookup"><span data-stu-id="273f3-187">Click Lines.</span></span>
    * <span data-ttu-id="273f3-188">Kontrollera de bokförda journalposterna.</span><span class="sxs-lookup"><span data-stu-id="273f3-188">Verify the posted journal entries.</span></span>  

## <a name="process-letter-of-guarantee_liquidate"></a><span data-ttu-id="273f3-189">Bearbeta garanti_Likvidera</span><span class="sxs-lookup"><span data-stu-id="273f3-189">Process letter of guarantee_Liquidate</span></span>
1. <span data-ttu-id="273f3-190">Gå till Leverantörsreskontra > Order > Alla försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="273f3-190">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="273f3-191">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="273f3-191">In the list, click the link in the selected row.</span></span>
3. <span data-ttu-id="273f3-192">Klicka på Hantera i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="273f3-192">On the Action Pane, click Manage.</span></span>
4. <span data-ttu-id="273f3-193">Klicka på Garanti.</span><span class="sxs-lookup"><span data-stu-id="273f3-193">Click Letter of guarantee.</span></span>
5. <span data-ttu-id="273f3-194">I fönstret Åtgärd, klicka på Garanti.</span><span class="sxs-lookup"><span data-stu-id="273f3-194">On the Action Pane, click Letter of guarantee.</span></span>
6. <span data-ttu-id="273f3-195">Klicka på Likvidera för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="273f3-195">Click Liquidate to open the drop dialog.</span></span>
7. <span data-ttu-id="273f3-196">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="273f3-196">Click OK.</span></span>
8. <span data-ttu-id="273f3-197">Gå till Kassa- och bankhantering > Garanti > Garanti.</span><span class="sxs-lookup"><span data-stu-id="273f3-197">Go to Cash and bank management > Letters of guarantee > Letters of guarantee.</span></span>
9. <span data-ttu-id="273f3-198">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="273f3-198">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="273f3-199">Klicka på Likvidera för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="273f3-199">Click Liquidate to open the drop dialog.</span></span>
11. <span data-ttu-id="273f3-200">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="273f3-200">Click OK.</span></span>
12. <span data-ttu-id="273f3-201">Expandera avsnittet Åtgärder.</span><span class="sxs-lookup"><span data-stu-id="273f3-201">Expand the Actions section.</span></span>
    * <span data-ttu-id="273f3-202">Kontrollera posten Likvidera.</span><span class="sxs-lookup"><span data-stu-id="273f3-202">Verify the 'Liquidate' record.</span></span>  
13. <span data-ttu-id="273f3-203">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="273f3-203">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="273f3-204">Klicka för att följa länken i fältet Journalbatchnummer.</span><span class="sxs-lookup"><span data-stu-id="273f3-204">Click to follow the link in the Journal batch number field.</span></span>
15. <span data-ttu-id="273f3-205">Klicka på Rader.</span><span class="sxs-lookup"><span data-stu-id="273f3-205">Click Lines.</span></span>
    * <span data-ttu-id="273f3-206">Kontrollera de bokförda journalposterna.</span><span class="sxs-lookup"><span data-stu-id="273f3-206">Verify the posted journal entries.</span></span>  
16. <span data-ttu-id="273f3-207">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="273f3-207">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]