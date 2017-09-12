---
title: "Avskrivningseffekter med återföringar"
description: "Det här avsnittet behandlar potentiella konsekvenser vid återföring av en Anläggningstillgångstransaktion."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetTrans
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 2961
ms.assetid: 63a3ac92-c321-4379-a86a-b1b14915f340
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 7309cb3175f65bc6b806edb875ac9406a8faaf66
ms.contentlocale: sv-se
ms.lasthandoff: 07/18/2017

---

# <a name="depreciation-effects-with-reversals"></a><span data-ttu-id="151e8-103">Avskrivningseffekter med återföringar</span><span class="sxs-lookup"><span data-stu-id="151e8-103">Depreciation effects with reversals</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="151e8-104">Det här avsnittet behandlar potentiella konsekvenser vid återföring av en Anläggningstillgångstransaktion.</span><span class="sxs-lookup"><span data-stu-id="151e8-104">This article discusses potential implications of reversing a fixed asset transaction.</span></span> 

<span data-ttu-id="151e8-105">Du kan återföra transaktioner för anläggningstillgångar och transaktionerna som är kopplade till en anläggningstillgång.</span><span class="sxs-lookup"><span data-stu-id="151e8-105">You can reverse fixed asset transactions, and the transactions that are associated with a fixed asset.</span></span> <span data-ttu-id="151e8-106">Du kan även återkalla en återförd transaktion.</span><span class="sxs-lookup"><span data-stu-id="151e8-106">You can also revoke a reversed transaction.</span></span> 

<span data-ttu-id="151e8-107">Du kan återställa eller återkalla en transaktion som inte är den senaste transaktionen som bokfördes i tillgångsboken.</span><span class="sxs-lookup"><span data-stu-id="151e8-107">You can reverse or revoke a transaction that was not the most recent transaction posted to the book for the asset.</span></span> <span data-ttu-id="151e8-108">Du bör först fastställa om några avskrivningstransaktioner bokfördes efter den transaktion som du återför.</span><span class="sxs-lookup"><span data-stu-id="151e8-108">You should first determine whether any depreciation transactions were posted after the transaction that you are reversing.</span></span> <span data-ttu-id="151e8-109">Detta eftersom avskrivning inte räknas om när du återför en transaktion.</span><span class="sxs-lookup"><span data-stu-id="151e8-109">This is because depreciation is not recalculated when you reverse a transaction.</span></span> <span data-ttu-id="151e8-110">Därför blir avskrivningen ofta för hög eller för låg efter återföringen, vilket exemplen visar.</span><span class="sxs-lookup"><span data-stu-id="151e8-110">Therefore, depreciation often is overstated or understated after the reversal, as shown in the examples.</span></span> 

<span data-ttu-id="151e8-111">Om du vill vara säker på att avskrivningen är korrekt när du återför en transaktion, gå inte vidare med återföringen om du får ett meddelande om att avskrivningen inte räknas om.</span><span class="sxs-lookup"><span data-stu-id="151e8-111">To make sure that depreciation is correct when you reverse a transaction, do not continue with the reversal if you receive a message that states that depreciation will not be recalculated.</span></span> <span data-ttu-id="151e8-112">Återför istället först avskrivningstransaktionen som bokfördes efter att den transaktion som du försökte du återföra och fortsätt sedan med återföringen.</span><span class="sxs-lookup"><span data-stu-id="151e8-112">Instead, first reverse the depreciation transaction that was posted after the transaction you tried to reverse, and then continue with the reversal.</span></span> <span data-ttu-id="151e8-113">Du varnas inte om omberäkningar av avskrivning och du kan gå vidare med återföringen.</span><span class="sxs-lookup"><span data-stu-id="151e8-113">You will not be warned about depreciation recalculations, and you can continue with the reversal.</span></span> 

<span data-ttu-id="151e8-114">Följande exempel visar de omberäkningar som genomförs om du fortsätter utan att beakta meddelandet att först återföra avskrivningstransaktionerna.</span><span class="sxs-lookup"><span data-stu-id="151e8-114">The following examples show the calculations that occur if you continue beyond the message without first reversing the depreciation transactions.</span></span>

## <a name="example-1-depreciation-is-overstated"></a><span data-ttu-id="151e8-115"> Exempel 1: Avskrivningen är för hög</span><span class="sxs-lookup"><span data-stu-id="151e8-115">Example 1: Depreciation is overstated</span></span>
<span data-ttu-id="151e8-116">En tillgång har registrerats med en livslängd på fem år och linjär avskrivning (60 avskrivningsperioder).</span><span class="sxs-lookup"><span data-stu-id="151e8-116">An asset is set up with a 5-year useful life and straight line depreciation (60 depreciation periods).</span></span> <span data-ttu-id="151e8-117">I det här exemplet blir avskrivningen för hög.</span><span class="sxs-lookup"><span data-stu-id="151e8-117">In this example, depreciation is overstated.</span></span>
#### <a name="asset-transaction-history"></a><span data-ttu-id="151e8-118">Tillgångens transaktionshistorik</span><span class="sxs-lookup"><span data-stu-id="151e8-118">Asset transaction history</span></span>

| <span data-ttu-id="151e8-119">Datum</span><span class="sxs-lookup"><span data-stu-id="151e8-119">Date</span></span>       | <span data-ttu-id="151e8-120">Transaktionstyp</span><span class="sxs-lookup"><span data-stu-id="151e8-120">Transaction type</span></span>                                                          | <span data-ttu-id="151e8-121">Belopp</span><span class="sxs-lookup"><span data-stu-id="151e8-121">Amount</span></span>                                    |
|------------|---------------------------------------------------------------------------|-------------------------------------------|
| <span data-ttu-id="151e8-122">1 januari</span><span class="sxs-lookup"><span data-stu-id="151e8-122">January 1</span></span>  | <span data-ttu-id="151e8-123">Anskaffning</span><span class="sxs-lookup"><span data-stu-id="151e8-123">Acquisition</span></span>                                                               | <span data-ttu-id="151e8-124">59 000,00</span><span class="sxs-lookup"><span data-stu-id="151e8-124">59,000.00</span></span>                                 |
| <span data-ttu-id="151e8-125">1 januari</span><span class="sxs-lookup"><span data-stu-id="151e8-125">January 1</span></span>  | <span data-ttu-id="151e8-126">Anskaffningsjustering</span><span class="sxs-lookup"><span data-stu-id="151e8-126">Acquisition adjustment</span></span>                                                    | <span data-ttu-id="151e8-127">1 000,00</span><span class="sxs-lookup"><span data-stu-id="151e8-127">1,000.00</span></span>                                  |
| <span data-ttu-id="151e8-128">31 januari</span><span class="sxs-lookup"><span data-stu-id="151e8-128">January 31</span></span> | <span data-ttu-id="151e8-129">Avskrivning (skapad med ett förslag på en avskrivningsperiod)</span><span class="sxs-lookup"><span data-stu-id="151e8-129">Depreciation (created by using a proposal for one period of depreciation)</span></span> | <span data-ttu-id="151e8-130">1 000,00 Beräkning: Bokfört värde (59 000 + 1 000) / antal kvarstående avskrivningsperioder (60)</span><span class="sxs-lookup"><span data-stu-id="151e8-130">1,000.00Calculation: Book value (59,000 + 1,000) / Number of depreciation periods remaining (60)</span></span> |

#### <a name="reversal-action"></a><span data-ttu-id="151e8-131">Återföringsåtgärd</span><span class="sxs-lookup"><span data-stu-id="151e8-131">Reversal action</span></span>

| <span data-ttu-id="151e8-132">Datum</span><span class="sxs-lookup"><span data-stu-id="151e8-132">Date</span></span>      | <span data-ttu-id="151e8-133">transaktionstyp</span><span class="sxs-lookup"><span data-stu-id="151e8-133">Transaction type</span></span>                | <span data-ttu-id="151e8-134">Belopp</span><span class="sxs-lookup"><span data-stu-id="151e8-134">Amount</span></span>    |
|-----------|---------------------------------|-----------|
| <span data-ttu-id="151e8-135">1 januari</span><span class="sxs-lookup"><span data-stu-id="151e8-135">January 1</span></span> | <span data-ttu-id="151e8-136">Återföring av anskaffningsjustering</span><span class="sxs-lookup"><span data-stu-id="151e8-136">Acquisition adjustment reversal</span></span> | <span data-ttu-id="151e8-137">-1 000,00</span><span class="sxs-lookup"><span data-stu-id="151e8-137">–1,000.00</span></span> |

#### <a name="depreciation-effect"></a><span data-ttu-id="151e8-138">Avskrivningseffekt</span><span class="sxs-lookup"><span data-stu-id="151e8-138">Depreciation effect</span></span>

| <span data-ttu-id="151e8-139">Datum</span><span class="sxs-lookup"><span data-stu-id="151e8-139">Date</span></span>        | <span data-ttu-id="151e8-140">transaktionstyp</span><span class="sxs-lookup"><span data-stu-id="151e8-140">Transaction type</span></span>        | <span data-ttu-id="151e8-141">Belopp</span><span class="sxs-lookup"><span data-stu-id="151e8-141">Amount</span></span>                                                                                |
|-------------|-------------------------|---------------------------------------------------------------------------------------|
| <span data-ttu-id="151e8-142">28 februari</span><span class="sxs-lookup"><span data-stu-id="151e8-142">February 28</span></span> | <span data-ttu-id="151e8-143">Avskrivning (förslag)</span><span class="sxs-lookup"><span data-stu-id="151e8-143">Depreciation (proposal)</span></span> | <span data-ttu-id="151e8-144">983,05 Beräkning: Bokfört värde (59 000 - 1 000 avskrivning) / antal kvarstående avskrivningsperioder (59)</span><span class="sxs-lookup"><span data-stu-id="151e8-144">983.05Calculation: Book value (59,000 - 1,000 depreciation) / Number of depreciation periods remaining (59)</span></span> |

<span data-ttu-id="151e8-145">Avskrivningens värde är 16,95 för högt (1 000 – 983,05).</span><span class="sxs-lookup"><span data-stu-id="151e8-145">Depreciation is overstated by 16.95 (1,000 - 983.05).</span></span>

## <a name="example-2-depreciation-is-understated"></a><span data-ttu-id="151e8-146"> Exempel 2: Avskrivningen är för låg</span><span class="sxs-lookup"><span data-stu-id="151e8-146">Example 2: Depreciation is understated</span></span>
<span data-ttu-id="151e8-147">En tillgång har registrerats med en livslängd på fem år och linjär avskrivning (60 avskrivningsperioder).</span><span class="sxs-lookup"><span data-stu-id="151e8-147">An asset is set up with a 5-year useful life and straight line depreciation (60 depreciation periods).</span></span> <span data-ttu-id="151e8-148">I det här exemplet blir avskrivningen för låg.</span><span class="sxs-lookup"><span data-stu-id="151e8-148">In this example, depreciation is understated.</span></span>
#### <a name="asset-transaction-history"></a><span data-ttu-id="151e8-149">Tillgångens transaktionshistorik</span><span class="sxs-lookup"><span data-stu-id="151e8-149">Asset transaction history</span></span>

| <span data-ttu-id="151e8-150">Datum</span><span class="sxs-lookup"><span data-stu-id="151e8-150">Date</span></span>       | <span data-ttu-id="151e8-151">transaktionstyp</span><span class="sxs-lookup"><span data-stu-id="151e8-151">Transaction type</span></span>                                                          | <span data-ttu-id="151e8-152">Belopp</span><span class="sxs-lookup"><span data-stu-id="151e8-152">Amount</span></span>                                      |
|------------|---------------------------------------------------------------------------|---------------------------------------------|
| <span data-ttu-id="151e8-153">1 januari</span><span class="sxs-lookup"><span data-stu-id="151e8-153">January 1</span></span>  | <span data-ttu-id="151e8-154">Anskaffning</span><span class="sxs-lookup"><span data-stu-id="151e8-154">Acquisition</span></span>                                                               | <span data-ttu-id="151e8-155">59 000,00</span><span class="sxs-lookup"><span data-stu-id="151e8-155">59,000.00</span></span>                                   |
| <span data-ttu-id="151e8-156">1 januari</span><span class="sxs-lookup"><span data-stu-id="151e8-156">January 1</span></span>  | <span data-ttu-id="151e8-157">Nedskrivning</span><span class="sxs-lookup"><span data-stu-id="151e8-157">Write-down adjustment</span></span>                                                     | <span data-ttu-id="151e8-158">1 000,00</span><span class="sxs-lookup"><span data-stu-id="151e8-158">1,000.00</span></span>                                    |
| <span data-ttu-id="151e8-159">31 januari</span><span class="sxs-lookup"><span data-stu-id="151e8-159">January 31</span></span> | <span data-ttu-id="151e8-160">Avskrivning (skapad med ett förslag på en avskrivningsperiod)</span><span class="sxs-lookup"><span data-stu-id="151e8-160">Depreciation (created by using a proposal for one period of depreciation)</span></span> | <span data-ttu-id="151e8-161">966,67 Beräkning: Bokfört värde (59 000 - 1 000) / antal kvarstående avskrivningsperioder (60)</span><span class="sxs-lookup"><span data-stu-id="151e8-161">966.67Calculation: Book value (59,000 - 1,000) / Number of depreciation periods remaining (60)</span></span> |

#### <a name="reversal-action"></a><span data-ttu-id="151e8-162">Återföringsåtgärd</span><span class="sxs-lookup"><span data-stu-id="151e8-162">Reversal action</span></span>

| <span data-ttu-id="151e8-163">Datum</span><span class="sxs-lookup"><span data-stu-id="151e8-163">Date</span></span>      | <span data-ttu-id="151e8-164">transaktionstyp</span><span class="sxs-lookup"><span data-stu-id="151e8-164">Transaction type</span></span>               | <span data-ttu-id="151e8-165">Belopp</span><span class="sxs-lookup"><span data-stu-id="151e8-165">Amount</span></span>    |
|-----------|--------------------------------|-----------|
| <span data-ttu-id="151e8-166">1 januari</span><span class="sxs-lookup"><span data-stu-id="151e8-166">January 1</span></span> | <span data-ttu-id="151e8-167">Återföring av nedskrivningsjustering</span><span class="sxs-lookup"><span data-stu-id="151e8-167">Write-down adjustment reversal</span></span> | <span data-ttu-id="151e8-168">-1 000,00</span><span class="sxs-lookup"><span data-stu-id="151e8-168">–1,000.00</span></span> |

#### <a name="depreciation-effect"></a><span data-ttu-id="151e8-169">Avskrivningseffekt</span><span class="sxs-lookup"><span data-stu-id="151e8-169">Depreciation effect</span></span>

| <span data-ttu-id="151e8-170">Datum</span><span class="sxs-lookup"><span data-stu-id="151e8-170">Date</span></span>        | <span data-ttu-id="151e8-171">transaktionstyp</span><span class="sxs-lookup"><span data-stu-id="151e8-171">Transaction type</span></span>        | <span data-ttu-id="151e8-172">Belopp</span><span class="sxs-lookup"><span data-stu-id="151e8-172">Amount</span></span>                                                                                       |
|-------------|-------------------------|----------------------------------------------------------------------------------------------|
| <span data-ttu-id="151e8-173">28 februari</span><span class="sxs-lookup"><span data-stu-id="151e8-173">February 28</span></span> | <span data-ttu-id="151e8-174">Avskrivning (förslag)</span><span class="sxs-lookup"><span data-stu-id="151e8-174">Depreciation (proposal)</span></span> | <span data-ttu-id="151e8-175">983,62 Beräkning: Bokfört värde (59 000 - 966,67 avskrivning) / antal kvarstående avskrivningsperioder (59)</span><span class="sxs-lookup"><span data-stu-id="151e8-175">983.62Calculation: Book value (59,000 - 966.67 depreciation) / Number of depreciation periods remaining (59)</span></span> |

<span data-ttu-id="151e8-176">Avskrivningens värde är 16,95 för lågt (983,62 – 966,67).</span><span class="sxs-lookup"><span data-stu-id="151e8-176">Depreciation is understated by 16.95 (983.62 - 966.67).</span></span>



<a name="see-also"></a><span data-ttu-id="151e8-177">Se även</span><span class="sxs-lookup"><span data-stu-id="151e8-177">See also</span></span>
--------

[<span data-ttu-id="151e8-178">Avskrivning av anläggningstillgång</span><span class="sxs-lookup"><span data-stu-id="151e8-178">Fixed asset depreciation</span></span>](fixed-asset-depreciation.md)




