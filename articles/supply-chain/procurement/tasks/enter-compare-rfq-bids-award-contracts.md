--- 
title: "Ange och jämför anbudsförfråganbud och tilldela kontrakt"
description: "Den här proceduren visar dig hur du anger svar på en anbudsförfrågan, poäng och jämför bud, och sedan tilldelar budet till en av leverantörerna."
author: mkirknel
manager: AnnBe
ms.date: 06/07/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 140d9f7a48b6cb06f02d3c4e6440d0a99a9d8161
ms.contentlocale: sv-se
ms.lasthandoff: 04/13/2018

---
# <a name="enter-and-compare-rfq-bids-and-award-contracts"></a><span data-ttu-id="088ba-103">Ange och jämför anbudsförfråganbud och tilldela kontrakt</span><span class="sxs-lookup"><span data-stu-id="088ba-103">Enter and compare RFQ bids and award contracts</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="088ba-104">Den här proceduren visar dig hur du anger svar på en anbudsförfrågan, poäng och jämför bud, och sedan tilldelar budet till en av leverantörerna.</span><span class="sxs-lookup"><span data-stu-id="088ba-104">This procedure shows you how to enter replies to an RFQ, score and compare bids, and then award the bid to one of the vendors.</span></span> <span data-ttu-id="088ba-105">Du kan köra den här proceduren i demonstrationsdataföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="088ba-105">You can use this procedure in demo data company USMF.</span></span> <span data-ttu-id="088ba-106">Innan du startar måste du ha en anbudsförfrågan med två rader som har skickats till minst två leverantörer.</span><span class="sxs-lookup"><span data-stu-id="088ba-106">Before you start, you must have an RFQ with two lines that has been sent to at least two vendors.</span></span> <span data-ttu-id="088ba-107">Du kan köra proceduren ”Skapa en anbudsförfrågan” som en förutsättning för att skapa detta.</span><span class="sxs-lookup"><span data-stu-id="088ba-107">You can run the "Create a request for quotation" procedure as a prerequisite to create this.</span></span> <span data-ttu-id="088ba-108">Du måste ha ställt in ett poängkriterium innan du kan köra den här proceduren.</span><span class="sxs-lookup"><span data-stu-id="088ba-108">You need to have set up scoring criteria before you can run this procedure.</span></span>


## <a name="enter-a-reply-from-a-vendor"></a><span data-ttu-id="088ba-109">Ange ett svar från en leverantör</span><span class="sxs-lookup"><span data-stu-id="088ba-109">Enter a reply from a vendor</span></span>
1. <span data-ttu-id="088ba-110">Gå till Anskaffning och källa > Anbudsförfrågningar > Alla anbudsförfrågningar.</span><span class="sxs-lookup"><span data-stu-id="088ba-110">Go to Procurement and sourcing > Requests for quotations > All requests for quotations.</span></span>
2. <span data-ttu-id="088ba-111">Välj en anbudsförfrågan som har statusen Skickad och klicka på länken på Ärendenummer på anbudsförfrågan.</span><span class="sxs-lookup"><span data-stu-id="088ba-111">Select an RFQ that has a status of Sent and click the link on the Request for quotation case number.</span></span>
    * <span data-ttu-id="088ba-112">Anbudsförfrågan ska ha skickats till minst 2 leverantörer.</span><span class="sxs-lookup"><span data-stu-id="088ba-112">The RFQ should have been sent to at least 2 vendors.</span></span>  
3. <span data-ttu-id="088ba-113">Klicka på Rubrik om du vill gå till listan över leverantörer.</span><span class="sxs-lookup"><span data-stu-id="088ba-113">Click Header to go to the list of vendors.</span></span>
4. <span data-ttu-id="088ba-114">+Markera leverantören som du vill ange för ett svar på anbudsförfrågan.</span><span class="sxs-lookup"><span data-stu-id="088ba-114">Select the vendor for whom you want to enter a response on the RFQ.</span></span>
5. <span data-ttu-id="088ba-115">Klicka på Ange svar.</span><span class="sxs-lookup"><span data-stu-id="088ba-115">Click Enter reply.</span></span>
6. <span data-ttu-id="088ba-116">Klicka på Svar i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="088ba-116">On the Action Pane, click Reply.</span></span>
7. <span data-ttu-id="088ba-117">Klicka på Kopiera data för att svara.</span><span class="sxs-lookup"><span data-stu-id="088ba-117">Click Copy data to reply.</span></span>
    * <span data-ttu-id="088ba-118">Denna åtgärd kommer att kopiera valda data, till exempel kvantiteten från anbudsförfrågansärendet till svaret på anbudsförfrågan.</span><span class="sxs-lookup"><span data-stu-id="088ba-118">This action will copy selected data, for example, the quantity from the RFQ case to the RFQ reply.</span></span> <span data-ttu-id="088ba-119">Alternativt kan du hoppa över den här åtgärden och fylla i alla svarfälten manuellt när du redigerar svaret.</span><span class="sxs-lookup"><span data-stu-id="088ba-119">Alternatively you can skip this action and fill in all the response fields manually when you edit the reply.</span></span>  
8. <span data-ttu-id="088ba-120">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="088ba-120">Click Edit.</span></span>
9. <span data-ttu-id="088ba-121">Ange ett tal i fältet Enhetspris.</span><span class="sxs-lookup"><span data-stu-id="088ba-121">In the Unit price field, enter a number.</span></span>
10. <span data-ttu-id="088ba-122">Välj den andra offertraden.</span><span class="sxs-lookup"><span data-stu-id="088ba-122">Choose the other quotation line.</span></span>
11. <span data-ttu-id="088ba-123">Ange ett tal i fältet Enhetspris.</span><span class="sxs-lookup"><span data-stu-id="088ba-123">In the Unit price field, enter a number.</span></span>

## <a name="score-the-bid"></a><span data-ttu-id="088ba-124">Poängsätt budet</span><span class="sxs-lookup"><span data-stu-id="088ba-124">Score the bid</span></span>
1. <span data-ttu-id="088ba-125">Klicka på Rubrik om du vill gå till budets poäng.</span><span class="sxs-lookup"><span data-stu-id="088ba-125">Click Header to go to the scoring of the bid.</span></span>
2. <span data-ttu-id="088ba-126">Visa avsnittet Poängsättning av bud.</span><span class="sxs-lookup"><span data-stu-id="088ba-126">Expand the Bid scoring section.</span></span>
3. <span data-ttu-id="088ba-127">Ange ett nummer för ett av poängkriterierna i fältet Poäng.</span><span class="sxs-lookup"><span data-stu-id="088ba-127">In the Score field, enter a number for one of the scoring criteria.</span></span>
    * <span data-ttu-id="088ba-128">Om du hovrar över en av poängkriterierna visar en knappbeskrivning det intervall som poängen måste vara i.</span><span class="sxs-lookup"><span data-stu-id="088ba-128">If you hover over one of the scoring criteria a tooltip shows the range that you have to score within.</span></span> <span data-ttu-id="088ba-129">I denna demonstration kan du lägga till ett värde på mellan 1 och 5 till något av kriterierna.</span><span class="sxs-lookup"><span data-stu-id="088ba-129">In this demo you can add a number between 1 and 5 to any of the criteria.</span></span>  
4. <span data-ttu-id="088ba-130">Välj ett annat poängkriterium.</span><span class="sxs-lookup"><span data-stu-id="088ba-130">Select another scoring criterion.</span></span>
5. <span data-ttu-id="088ba-131">Ange ett nummer i fältet Poäng.</span><span class="sxs-lookup"><span data-stu-id="088ba-131">In the Score field, enter a number.</span></span>
6. <span data-ttu-id="088ba-132">Visa avsnittet Enkäter.</span><span class="sxs-lookup"><span data-stu-id="088ba-132">Expand the Questionnaires section.</span></span>
    * <span data-ttu-id="088ba-133">Om anbudsförfråganfallet har en enkät som skickats till leverantörerna, kan du ange sina svar i avsnittet Enkäter.</span><span class="sxs-lookup"><span data-stu-id="088ba-133">If the RFQ case has a questionnaire that was sent to the vendors, you can enter their responses in the questionnaire section.</span></span>  
7. <span data-ttu-id="088ba-134">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="088ba-134">Close the page.</span></span>

## <a name="enter-a-reply-for-another-vendor"></a><span data-ttu-id="088ba-135">Ange ett svar för en annan leverantör</span><span class="sxs-lookup"><span data-stu-id="088ba-135">Enter a reply for another vendor</span></span>
1. <span data-ttu-id="088ba-136">Välj nästa leverantör genom att avmarkera den leverantör som du precis har angett svaret för och välj sedan raden för nästa leverantör.</span><span class="sxs-lookup"><span data-stu-id="088ba-136">Select the next vendor by clearing the vendor you have just entered the reply for and then selecting the row for the next vendor.</span></span>
2. <span data-ttu-id="088ba-137">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="088ba-137">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="088ba-138">Klicka på Ange svar.</span><span class="sxs-lookup"><span data-stu-id="088ba-138">Click Enter reply.</span></span>
4. <span data-ttu-id="088ba-139">Klicka på Kopiera data för att svara.</span><span class="sxs-lookup"><span data-stu-id="088ba-139">Click Copy data to reply.</span></span>
5. <span data-ttu-id="088ba-140">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="088ba-140">Click Edit.</span></span>
6. <span data-ttu-id="088ba-141">Ange ett tal i fältet Enhetspris.</span><span class="sxs-lookup"><span data-stu-id="088ba-141">In the Unit price field, enter a number.</span></span>
7. <span data-ttu-id="088ba-142">Välj den andra offertraden.</span><span class="sxs-lookup"><span data-stu-id="088ba-142">Choose the other quotation line.</span></span>
8. <span data-ttu-id="088ba-143">Ange ett tal i fältet Enhetspris.</span><span class="sxs-lookup"><span data-stu-id="088ba-143">In the Unit price field, enter a number.</span></span>

## <a name="score-the-second-bid"></a><span data-ttu-id="088ba-144">Poängsätt det andra budet</span><span class="sxs-lookup"><span data-stu-id="088ba-144">Score the second bid</span></span>
1. <span data-ttu-id="088ba-145">Klicka på Rubrik om du vill gå till budets poäng.</span><span class="sxs-lookup"><span data-stu-id="088ba-145">Click Header to go to scoring of the bid.</span></span>
2. <span data-ttu-id="088ba-146">Ange ett nummer i fältet Poäng.</span><span class="sxs-lookup"><span data-stu-id="088ba-146">In the Score field, enter a number.</span></span>
3. <span data-ttu-id="088ba-147">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="088ba-147">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="088ba-148">Ange ett nummer i fältet Poäng.</span><span class="sxs-lookup"><span data-stu-id="088ba-148">In the Score field, enter a number.</span></span>

## <a name="compare-the-replies"></a><span data-ttu-id="088ba-149">Jämför svaren</span><span class="sxs-lookup"><span data-stu-id="088ba-149">Compare the replies</span></span>
1. <span data-ttu-id="088ba-150">Klicka på Allmänt i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="088ba-150">On the Action Pane, click General.</span></span>
2. <span data-ttu-id="088ba-151">Klicka på Jämför svar.</span><span class="sxs-lookup"><span data-stu-id="088ba-151">Click Compare replies.</span></span>
3. <span data-ttu-id="088ba-152">Ange ett nummer i fältet Rangordning.</span><span class="sxs-lookup"><span data-stu-id="088ba-152">In the Rank field, enter a number.</span></span>
    * <span data-ttu-id="088ba-153">På den här sidan visas buden med rubriken och raderna och den totala på poängen på rubriknivån.</span><span class="sxs-lookup"><span data-stu-id="088ba-153">This page shows the bids with the header and lines, and the total score on the header level.</span></span> <span data-ttu-id="088ba-154">Du kan jämföra raderna genom att sortera i rutnätet så att jämförbara rader finns bredvid varandra.</span><span class="sxs-lookup"><span data-stu-id="088ba-154">You can compare the lines by sorting in the grid so that comparable lines are next to each other.</span></span> <span data-ttu-id="088ba-155">Informationen innehåller även: Kvantitet: Den kvantitet som anges av leverantören.</span><span class="sxs-lookup"><span data-stu-id="088ba-155">The information also includes:   Quantity: The quantity quoted by the vendor.</span></span> <span data-ttu-id="088ba-156">Detta kanske inte är lika med kvantiteten som specificerats i anbudsförfrågan.</span><span class="sxs-lookup"><span data-stu-id="088ba-156">This might not equal the quantity specified in the RFQ.</span></span>   <span data-ttu-id="088ba-157">Nettobelopp: priset som anges av en leverantör, att betala av eventuella rabatter, för artiklarna på raden.</span><span class="sxs-lookup"><span data-stu-id="088ba-157">Net amount: The price quoted by a vendor, after subtracting any discounts, for the items on the line.</span></span>   <span data-ttu-id="088ba-158">Avvikelse: Antal dagar som leveransdatumet i budhuvud eller raden avviker från det begärda leveransdatumet i huvudet för anbudsförfrågan eller anbudsförfråganraden.</span><span class="sxs-lookup"><span data-stu-id="088ba-158">Deviation: The number of days that the delivery date in the bid header or line deviates from the requested delivery date in the RFQ header or RFQ line.</span></span>   <span data-ttu-id="088ba-159">Du kan ange en ranking för varje bud.</span><span class="sxs-lookup"><span data-stu-id="088ba-159">You can enter a rank for each bid.</span></span>  
4. <span data-ttu-id="088ba-160">Välj rubrikrad för det andra budet som du vill rangordna.</span><span class="sxs-lookup"><span data-stu-id="088ba-160">Select the header line for the other bid that you want to rank.</span></span>
5. <span data-ttu-id="088ba-161">Ange ett nummer i fältet Rangordning.</span><span class="sxs-lookup"><span data-stu-id="088ba-161">In the Rank field, enter a number.</span></span>
6. <span data-ttu-id="088ba-162">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="088ba-162">Click Save.</span></span>

## <a name="reject-a-bid"></a><span data-ttu-id="088ba-163">Avvisa ett bud</span><span class="sxs-lookup"><span data-stu-id="088ba-163">Reject a bid</span></span>
1. <span data-ttu-id="088ba-164">Välj rubrikrad för det budet som du vill avvisa.</span><span class="sxs-lookup"><span data-stu-id="088ba-164">Select the header line for the bid that you want to reject.</span></span>
    * <span data-ttu-id="088ba-165">Du kan bara godkänna, avvisa eller returnera ett bud eller rader inom ett bud i taget.</span><span class="sxs-lookup"><span data-stu-id="088ba-165">You can only accept, reject, or return one bid or lines within one bid at a time.</span></span>  
2. <span data-ttu-id="088ba-166">Markera kryssrutan Markera.</span><span class="sxs-lookup"><span data-stu-id="088ba-166">Select the Mark check box.</span></span>
    * <span data-ttu-id="088ba-167">Om du väljer Markera kryssrutan i budets Rubrik kommer även alla rader att markeras.</span><span class="sxs-lookup"><span data-stu-id="088ba-167">If you select the Mark check box on the Header of the bid then all the lines will be marked as well.</span></span> <span data-ttu-id="088ba-168">Du kan också välja att markera en deluppsättning av raderna i budet om du vill avvisa eller godkänna dessa.</span><span class="sxs-lookup"><span data-stu-id="088ba-168">You could also choose to mark a subset of the lines within the bid to reject or accept those.</span></span> <span data-ttu-id="088ba-169">Det går att acceptera en leverantörs bud för alla rader i en anbudsförfrågan och sedan tilldela andra anbudsförfrågansrader till en annan leverantör, men du måste göra detta i 2, ett bud i taget.</span><span class="sxs-lookup"><span data-stu-id="088ba-169">It’s possible to accept one vendor’s bid for some lines of an RFQ, and then award other RFQ lines to a different vendor, however you need to do this in 2 steps, one bid at a time.</span></span> <span data-ttu-id="088ba-170">Du kan bara godkänna antingen originalanbudsraden eller dess alternativ, men inte båda, om det finns alternativa rader.</span><span class="sxs-lookup"><span data-stu-id="088ba-170">If alternate lines are present, you can only accept either the original bid line or its alternate, but not both.</span></span>  
3. <span data-ttu-id="088ba-171">Klicka på Avvisa.</span><span class="sxs-lookup"><span data-stu-id="088ba-171">Click Reject.</span></span>
4. <span data-ttu-id="088ba-172">Klicka på Parametrar för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="088ba-172">Click Parameters to open the drop dialog.</span></span>
5. <span data-ttu-id="088ba-173">Ange eller välj ett värde i fältet Orsak för avvisande.</span><span class="sxs-lookup"><span data-stu-id="088ba-173">In the Reason reject field, enter or select a value.</span></span>
    * <span data-ttu-id="088ba-174">Skälet till avvisande kommer att lagras på svaret.</span><span class="sxs-lookup"><span data-stu-id="088ba-174">The reason for rejection will be stored on the reply.</span></span>  
6. <span data-ttu-id="088ba-175">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="088ba-175">Click OK.</span></span>
7. <span data-ttu-id="088ba-176">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="088ba-176">Click OK.</span></span>
8. <span data-ttu-id="088ba-177">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="088ba-177">Close the page.</span></span>
9. <span data-ttu-id="088ba-178">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="088ba-178">Close the page.</span></span>
10. <span data-ttu-id="088ba-179">Uppdatera sidan.</span><span class="sxs-lookup"><span data-stu-id="088ba-179">Refresh the page.</span></span>

## <a name="accept-a-bid"></a><span data-ttu-id="088ba-180">Acceptera ett bud</span><span class="sxs-lookup"><span data-stu-id="088ba-180">Accept a bid</span></span>
1. <span data-ttu-id="088ba-181">Välj budet som du vill godkänna och klicka sedan på länken i fältet Anbudsförfrågan.</span><span class="sxs-lookup"><span data-stu-id="088ba-181">Select the bid that you want to accept and then click the link in the Request for quotation field.</span></span>
2. <span data-ttu-id="088ba-182">Klicka på Svar i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="088ba-182">On the Action Pane, click Reply.</span></span>
3. <span data-ttu-id="088ba-183">Klicka på Godkänn.</span><span class="sxs-lookup"><span data-stu-id="088ba-183">Click Accept.</span></span>
    * <span data-ttu-id="088ba-184">Om du har valt specifika rader och inte andra kommer åtgärden godkänn endast att inkludera de markerade raderna.</span><span class="sxs-lookup"><span data-stu-id="088ba-184">If you have marked specific lines and not others then the accept action will only include the marked lines.</span></span> <span data-ttu-id="088ba-185">Om du vill godkänna alla rader på budet behöver du inte markera raderna.</span><span class="sxs-lookup"><span data-stu-id="088ba-185">If you want to accept all lines on the bid then you do not have to mark the lines.</span></span>  
4. <span data-ttu-id="088ba-186">Klicka på Parametrar för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="088ba-186">Click Parameters to open the drop dialog.</span></span>
    * <span data-ttu-id="088ba-187">På så sätt kan du registrera en orsak till att godkänna budet.</span><span class="sxs-lookup"><span data-stu-id="088ba-187">This allows you to record a reason for accepting the bid.</span></span> <span data-ttu-id="088ba-188">Skälet till avvisande kommer att lagras på svaret.</span><span class="sxs-lookup"><span data-stu-id="088ba-188">The reason will be stored on the bid.</span></span>  
5. <span data-ttu-id="088ba-189">Ange eller välj ett värde i fältet Orsak till godkännande.</span><span class="sxs-lookup"><span data-stu-id="088ba-189">In the Reason accept field, enter or select a value.</span></span>
6. <span data-ttu-id="088ba-190">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="088ba-190">Click OK.</span></span>
7. <span data-ttu-id="088ba-191">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="088ba-191">Click OK.</span></span>
    * <span data-ttu-id="088ba-192">När du klickar på OK genererar detta en inköpsorder baserat på de rader som ingår i godkännandet av anbudsförfrågan.</span><span class="sxs-lookup"><span data-stu-id="088ba-192">When you click OK this generates a purchase order based on the lines that are included in the RFQ acceptance.</span></span> <span data-ttu-id="088ba-193">Om det finns andra bud som inte har bearbetats (godkända, avvisade eller returnerade) kommer systemet att uppmana dig att avvisa de återstående buden.</span><span class="sxs-lookup"><span data-stu-id="088ba-193">If there are other bids that have not been processed (accepted, rejected, or returned) then the system will prompt you to reject the remaining bids.</span></span>  

## <a name="view-the-purchase-order-thats-been-generated"></a><span data-ttu-id="088ba-194">Visa den inköpsorder som har genererats</span><span class="sxs-lookup"><span data-stu-id="088ba-194">View the purchase order that's been generated</span></span>
1. <span data-ttu-id="088ba-195">Klicka på Allmänt i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="088ba-195">On the Action Pane, click General.</span></span>
2. <span data-ttu-id="088ba-196">Klicka på Inköpsorder.</span><span class="sxs-lookup"><span data-stu-id="088ba-196">Click Purchase order.</span></span>
    * <span data-ttu-id="088ba-197">Här kan du se inköpsordern som genererades, när du godkände budet.</span><span class="sxs-lookup"><span data-stu-id="088ba-197">Here you can see the purchase order that was generated when you accepted the bid.</span></span>  
3. <span data-ttu-id="088ba-198">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="088ba-198">Close the page.</span></span>
4. <span data-ttu-id="088ba-199">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="088ba-199">Close the page.</span></span>
5. <span data-ttu-id="088ba-200">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="088ba-200">Close the page.</span></span>
6. <span data-ttu-id="088ba-201">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="088ba-201">Close the page.</span></span>


