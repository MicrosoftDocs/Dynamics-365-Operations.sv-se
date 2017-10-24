--- 
title: Garantitransaktion
description: "I den här proceduren förklaras processen för garanti."
author: kweekley
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: c2e215f1ae16f907c8b64ea1f05cf67bfb0a04b6
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="letter-of-guarantee-transaction"></a><span data-ttu-id="18738-103">Garantitransaktion</span><span class="sxs-lookup"><span data-stu-id="18738-103">Letter of guarantee transaction</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="18738-104">I den här proceduren förklaras processen för garanti.</span><span class="sxs-lookup"><span data-stu-id="18738-104">This procedure walks through the Letter of guarantee process.</span></span>



<span data-ttu-id="18738-105">Följande uppgifter måste slutföras innan du avslutar den här proceduren:</span><span class="sxs-lookup"><span data-stu-id="18738-105">The following tasks must be complete before completing this procedure:</span></span>

- <span data-ttu-id="18738-106">Ställ in bankkreditlimiter och bokföringsprofiler för garanti.</span><span class="sxs-lookup"><span data-stu-id="18738-106">Set up bank facilities and posting profiles for a letter of guarantee.</span></span>

- <span data-ttu-id="18738-107">Skapa ett kreditlimitavtal för en garanti.</span><span class="sxs-lookup"><span data-stu-id="18738-107">Create a bank facility agreement for a letter of guarantee.</span></span>



<span data-ttu-id="18738-108">I den här proceduren används demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="18738-108">This procedure uses the USMF demo company.</span></span>


## <a name="create-sales-order-with-letter-of-guarantee"></a><span data-ttu-id="18738-109">Skapa försäljningsorder med garanti</span><span class="sxs-lookup"><span data-stu-id="18738-109">Create Sales Order with Letter of Guarantee</span></span>
1. <span data-ttu-id="18738-110">Gå till Leverantörsreskontra > Order > Alla försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="18738-110">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="18738-111">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="18738-111">Click New.</span></span>
3. <span data-ttu-id="18738-112">I fältet Kundkonto, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="18738-112">In the Customer account field, enter or select a value.</span></span>
4. <span data-ttu-id="18738-113">Expandera avsnittet Allmänt.</span><span class="sxs-lookup"><span data-stu-id="18738-113">Expand the General section.</span></span>
5. <span data-ttu-id="18738-114">Ange eller välj ett värde i fältet Plats.</span><span class="sxs-lookup"><span data-stu-id="18738-114">In the Site field, enter or select a value.</span></span>
6. <span data-ttu-id="18738-115">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="18738-115">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="18738-116">Ange eller välj ett värde i fältet Lagerställe.</span><span class="sxs-lookup"><span data-stu-id="18738-116">In the Warehouse field, enter or select a value.</span></span>
8. <span data-ttu-id="18738-117">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="18738-117">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="18738-118">Välj Garanti i fältet Bankdokumenttyp.</span><span class="sxs-lookup"><span data-stu-id="18738-118">In the Bank document type field, select 'Letter of guarantee'.</span></span>
10. <span data-ttu-id="18738-119">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="18738-119">Click OK.</span></span>
11. <span data-ttu-id="18738-120">Ange eller välj ett värde i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="18738-120">In the Item number field, enter or select a value.</span></span>
12. <span data-ttu-id="18738-121">Ange ett tal i fältet Enhetspris.</span><span class="sxs-lookup"><span data-stu-id="18738-121">In the Unit price field, enter a number.</span></span>
13. <span data-ttu-id="18738-122">Expandera avsnittet Radinformation.</span><span class="sxs-lookup"><span data-stu-id="18738-122">Expand the Line details section.</span></span>
14. <span data-ttu-id="18738-123">Klicka på fliken Leverans.</span><span class="sxs-lookup"><span data-stu-id="18738-123">Click the Delivery tab.</span></span>
    * <span data-ttu-id="18738-124">Obs! Välj Leveransdatumkontroll = Ingen.</span><span class="sxs-lookup"><span data-stu-id="18738-124">Note: Select Delivery date control = None</span></span>  
15. <span data-ttu-id="18738-125">I fältet Begärt transportdatum, ange ett datum.</span><span class="sxs-lookup"><span data-stu-id="18738-125">In the Requested ship date field, enter a date.</span></span>
16. <span data-ttu-id="18738-126">I fältet Bekräftat transportdatum, ange ett datum.</span><span class="sxs-lookup"><span data-stu-id="18738-126">In the Confirmed ship date field, enter a date.</span></span>

## <a name="process-letter-of-guaranteerequest"></a><span data-ttu-id="18738-127">Bearbeta garanti_begäran</span><span class="sxs-lookup"><span data-stu-id="18738-127">Process letter of guarantee_Request</span></span>
1. <span data-ttu-id="18738-128">Klicka på Hantera i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="18738-128">On the Action Pane, click Manage.</span></span>
2. <span data-ttu-id="18738-129">Klicka på Garanti.</span><span class="sxs-lookup"><span data-stu-id="18738-129">Click Letter of guarantee.</span></span>
3. <span data-ttu-id="18738-130">I fönstret Åtgärd, klicka på Garanti.</span><span class="sxs-lookup"><span data-stu-id="18738-130">On the Action Pane, click Letter of guarantee.</span></span>
4. <span data-ttu-id="18738-131">Klicka på Begäran om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="18738-131">Click Request to open the drop dialog.</span></span>
5. <span data-ttu-id="18738-132">Ange eller välj ett värde i fältet Typ.</span><span class="sxs-lookup"><span data-stu-id="18738-132">In the Type field, enter or select a value.</span></span>
6. <span data-ttu-id="18738-133">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="18738-133">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="18738-134">Ange ett nummer i fältet Värde.</span><span class="sxs-lookup"><span data-stu-id="18738-134">In the Value field, enter a number.</span></span>
8. <span data-ttu-id="18738-135">I fältet Utgångsdatum anger du datum och tid.</span><span class="sxs-lookup"><span data-stu-id="18738-135">In the Expiration date field, enter a date and time.</span></span>
9. <span data-ttu-id="18738-136">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="18738-136">Click OK.</span></span>
10. <span data-ttu-id="18738-137">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="18738-137">Close the page.</span></span>

## <a name="process-letter-of-guaranteesubmit-to-bank"></a><span data-ttu-id="18738-138">Bearbeta garanti_Skicka till bank</span><span class="sxs-lookup"><span data-stu-id="18738-138">Process letter of guarantee_Submit to bank</span></span>
1. <span data-ttu-id="18738-139">Gå till Kassa- och bankhantering > Garanti > Garanti.</span><span class="sxs-lookup"><span data-stu-id="18738-139">Go to Cash and bank management > Letters of guarantee > Letters of guarantee.</span></span>
2. <span data-ttu-id="18738-140">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="18738-140">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="18738-141">Klicka på Skicka till bank för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="18738-141">Click Submit to bank to open the drop dialog.</span></span>
4. <span data-ttu-id="18738-142">Ange eller välj ett värde i fältet Bankkonto.</span><span class="sxs-lookup"><span data-stu-id="18738-142">In the Bank account field, enter or select a value.</span></span>
5. <span data-ttu-id="18738-143">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="18738-143">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="18738-144">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="18738-144">Click OK.</span></span>

## <a name="process-letter-of-guaranteereceive-from-bank"></a><span data-ttu-id="18738-145">Bearbeta garanti_Ta emot från bank</span><span class="sxs-lookup"><span data-stu-id="18738-145">Process letter of guarantee_Receive from bank</span></span>
1. <span data-ttu-id="18738-146">Klicka på Ta emot från bank för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="18738-146">Click Receive from bank to open the drop dialog.</span></span>
2. <span data-ttu-id="18738-147">I fältet Banknummer, skriv ett värde.</span><span class="sxs-lookup"><span data-stu-id="18738-147">In the Bank number field, type a value.</span></span>
    * <span data-ttu-id="18738-148">Kontrollera värdena i de beräknade marginal- och utgiftsfälten.</span><span class="sxs-lookup"><span data-stu-id="18738-148">Verify the values in the calculated Margin and Expense fields.</span></span>  
3. <span data-ttu-id="18738-149">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="18738-149">Click OK.</span></span>
4. <span data-ttu-id="18738-150">Expandera avsnittet Åtgärder.</span><span class="sxs-lookup"><span data-stu-id="18738-150">Expand the Actions section.</span></span>
    * <span data-ttu-id="18738-151">Kontrollera posten Ta emot från bank.</span><span class="sxs-lookup"><span data-stu-id="18738-151">Verify the 'Receive from bank' record.</span></span>  
5. <span data-ttu-id="18738-152">Klicka för att följa länken i fältet Journalbatchnummer.</span><span class="sxs-lookup"><span data-stu-id="18738-152">Click to follow the link in the Journal batch number field.</span></span>
6. <span data-ttu-id="18738-153">Klicka på Rader.</span><span class="sxs-lookup"><span data-stu-id="18738-153">Click Lines.</span></span>
    * <span data-ttu-id="18738-154">Kontrollera bokföringen av journalposter.</span><span class="sxs-lookup"><span data-stu-id="18738-154">Verify the posting of journal entries.</span></span>  
7. <span data-ttu-id="18738-155">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="18738-155">Close the page.</span></span>

## <a name="process-letter-of-guaranteegive-to-beneficiary"></a><span data-ttu-id="18738-156">Bearbeta garanti_Ge till mottagare</span><span class="sxs-lookup"><span data-stu-id="18738-156">Process letter of guarantee_Give to beneficiary</span></span>
1. <span data-ttu-id="18738-157">Gå till Leverantörsreskontra > Order > Alla försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="18738-157">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="18738-158">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="18738-158">In the list, click the link in the selected row.</span></span>
3. <span data-ttu-id="18738-159">Klicka på Hantera i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="18738-159">On the Action Pane, click Manage.</span></span>
4. <span data-ttu-id="18738-160">Klicka på Garanti.</span><span class="sxs-lookup"><span data-stu-id="18738-160">Click Letter of guarantee.</span></span>
5. <span data-ttu-id="18738-161">I fönstret Åtgärd, klicka på Garanti.</span><span class="sxs-lookup"><span data-stu-id="18738-161">On the Action Pane, click Letter of guarantee.</span></span>
6. <span data-ttu-id="18738-162">Klicka på Ge till mottagare för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="18738-162">Click Give to beneficiary to open the drop dialog.</span></span>
7. <span data-ttu-id="18738-163">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="18738-163">Click OK.</span></span>
8. <span data-ttu-id="18738-164">Gå till Kassa- och bankhantering > Garanti > Garanti.</span><span class="sxs-lookup"><span data-stu-id="18738-164">Go to Cash and bank management > Letters of guarantee > Letters of guarantee.</span></span>
9. <span data-ttu-id="18738-165">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="18738-165">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="18738-166">Klicka på Ge till mottagare för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="18738-166">Click Give to beneficiary to open the drop dialog.</span></span>
11. <span data-ttu-id="18738-167">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="18738-167">Click OK.</span></span>
12. <span data-ttu-id="18738-168">Expandera avsnittet Åtgärder.</span><span class="sxs-lookup"><span data-stu-id="18738-168">Expand the Actions section.</span></span>
    * <span data-ttu-id="18738-169">Validera posten Ge till mottagare.</span><span class="sxs-lookup"><span data-stu-id="18738-169">Validate the 'Give to beneficiary' record.</span></span>  

## <a name="process-letter-of-guaranteeincrease-value"></a><span data-ttu-id="18738-170">Bearbeta garanti_Öka värde</span><span class="sxs-lookup"><span data-stu-id="18738-170">Process letter of guarantee_Increase value</span></span>
1. <span data-ttu-id="18738-171">Gå till Leverantörsreskontra > Order > Alla försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="18738-171">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="18738-172">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="18738-172">In the list, click the link in the selected row.</span></span>
3. <span data-ttu-id="18738-173">Klicka på Hantera i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="18738-173">On the Action Pane, click Manage.</span></span>
4. <span data-ttu-id="18738-174">Klicka på Garanti.</span><span class="sxs-lookup"><span data-stu-id="18738-174">Click Letter of guarantee.</span></span>
5. <span data-ttu-id="18738-175">I fönstret Åtgärd, klicka på Garanti.</span><span class="sxs-lookup"><span data-stu-id="18738-175">On the Action Pane, click Letter of guarantee.</span></span>
6. <span data-ttu-id="18738-176">Klicka på Öka värde för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="18738-176">Click Increase value to open the drop dialog.</span></span>
7. <span data-ttu-id="18738-177">I fältet Värde att lägga till, ange ett värde.</span><span class="sxs-lookup"><span data-stu-id="18738-177">In the Value to add field, enter a number.</span></span>
8. <span data-ttu-id="18738-178">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="18738-178">Click OK.</span></span>
9. <span data-ttu-id="18738-179">Gå till Kassa- och bankhantering > Garanti > Garanti.</span><span class="sxs-lookup"><span data-stu-id="18738-179">Go to Cash and bank management > Letters of guarantee > Letters of guarantee.</span></span>
10. <span data-ttu-id="18738-180">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="18738-180">In the list, find and select the desired record.</span></span>
11. <span data-ttu-id="18738-181">Klicka på Öka värde för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="18738-181">Click Increase value to open the drop dialog.</span></span>
12. <span data-ttu-id="18738-182">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="18738-182">Click OK.</span></span>
13. <span data-ttu-id="18738-183">Expandera avsnittet Åtgärder.</span><span class="sxs-lookup"><span data-stu-id="18738-183">Expand the Actions section.</span></span>
    * <span data-ttu-id="18738-184">Kontrollera posten Öka värde.</span><span class="sxs-lookup"><span data-stu-id="18738-184">Verify the 'Increase value' record.</span></span>  
14. <span data-ttu-id="18738-185">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="18738-185">In the list, find and select the desired record.</span></span>
15. <span data-ttu-id="18738-186">Klicka för att följa länken i fältet Journalbatchnummer.</span><span class="sxs-lookup"><span data-stu-id="18738-186">Click to follow the link in the Journal batch number field.</span></span>
16. <span data-ttu-id="18738-187">Klicka på Rader.</span><span class="sxs-lookup"><span data-stu-id="18738-187">Click Lines.</span></span>
    * <span data-ttu-id="18738-188">Kontrollera de bokförda journalposterna.</span><span class="sxs-lookup"><span data-stu-id="18738-188">Verify the posted journal entries.</span></span>  

## <a name="process-letter-of-guaranteeliquidate"></a><span data-ttu-id="18738-189">Bearbeta garanti_Likvidera</span><span class="sxs-lookup"><span data-stu-id="18738-189">Process letter of guarantee_Liquidate</span></span>
1. <span data-ttu-id="18738-190">Gå till Leverantörsreskontra > Order > Alla försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="18738-190">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="18738-191">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="18738-191">In the list, click the link in the selected row.</span></span>
3. <span data-ttu-id="18738-192">Klicka på Hantera i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="18738-192">On the Action Pane, click Manage.</span></span>
4. <span data-ttu-id="18738-193">Klicka på Garanti.</span><span class="sxs-lookup"><span data-stu-id="18738-193">Click Letter of guarantee.</span></span>
5. <span data-ttu-id="18738-194">I fönstret Åtgärd, klicka på Garanti.</span><span class="sxs-lookup"><span data-stu-id="18738-194">On the Action Pane, click Letter of guarantee.</span></span>
6. <span data-ttu-id="18738-195">Klicka på Likvidera för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="18738-195">Click Liquidate to open the drop dialog.</span></span>
7. <span data-ttu-id="18738-196">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="18738-196">Click OK.</span></span>
8. <span data-ttu-id="18738-197">Gå till Kassa- och bankhantering > Garanti > Garanti.</span><span class="sxs-lookup"><span data-stu-id="18738-197">Go to Cash and bank management > Letters of guarantee > Letters of guarantee.</span></span>
9. <span data-ttu-id="18738-198">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="18738-198">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="18738-199">Klicka på Likvidera för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="18738-199">Click Liquidate to open the drop dialog.</span></span>
11. <span data-ttu-id="18738-200">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="18738-200">Click OK.</span></span>
12. <span data-ttu-id="18738-201">Expandera avsnittet Åtgärder.</span><span class="sxs-lookup"><span data-stu-id="18738-201">Expand the Actions section.</span></span>
    * <span data-ttu-id="18738-202">Kontrollera posten Likvidera.</span><span class="sxs-lookup"><span data-stu-id="18738-202">Verify the 'Liquidate' record.</span></span>  
13. <span data-ttu-id="18738-203">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="18738-203">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="18738-204">Klicka för att följa länken i fältet Journalbatchnummer.</span><span class="sxs-lookup"><span data-stu-id="18738-204">Click to follow the link in the Journal batch number field.</span></span>
15. <span data-ttu-id="18738-205">Klicka på Rader.</span><span class="sxs-lookup"><span data-stu-id="18738-205">Click Lines.</span></span>
    * <span data-ttu-id="18738-206">Kontrollera de bokförda journalposterna.</span><span class="sxs-lookup"><span data-stu-id="18738-206">Verify the posted journal entries.</span></span>  
16. <span data-ttu-id="18738-207">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="18738-207">Close the page.</span></span>


