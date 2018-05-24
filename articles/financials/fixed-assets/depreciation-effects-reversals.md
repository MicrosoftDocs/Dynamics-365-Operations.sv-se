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
ms.search.scope: Core, Operations
ms.custom: 2961
ms.assetid: 63a3ac92-c321-4379-a86a-b1b14915f340
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: fbef7cb9a9fb18809dff96d4a44454d0dc6a31fc
ms.contentlocale: sv-se
ms.lasthandoff: 05/08/2018

---

# <a name="depreciation-effects-with-reversals"></a><span data-ttu-id="37c55-103">Avskrivningseffekter med återföringar</span><span class="sxs-lookup"><span data-stu-id="37c55-103">Depreciation effects with reversals</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="37c55-104">Det här avsnittet behandlar potentiella konsekvenser vid återföring av en Anläggningstillgångstransaktion.</span><span class="sxs-lookup"><span data-stu-id="37c55-104">This article discusses potential implications of reversing a fixed asset transaction.</span></span> 

<span data-ttu-id="37c55-105">Du kan återföra transaktioner för anläggningstillgångar och transaktionerna som är kopplade till en anläggningstillgång.</span><span class="sxs-lookup"><span data-stu-id="37c55-105">You can reverse fixed asset transactions, and the transactions that are associated with a fixed asset.</span></span> <span data-ttu-id="37c55-106">Du kan även återkalla en återförd transaktion.</span><span class="sxs-lookup"><span data-stu-id="37c55-106">You can also revoke a reversed transaction.</span></span> 

<span data-ttu-id="37c55-107">Du kan återställa eller återkalla en transaktion som inte är den senaste transaktionen som bokfördes i tillgångsboken.</span><span class="sxs-lookup"><span data-stu-id="37c55-107">You can reverse or revoke a transaction that was not the most recent transaction posted to the book for the asset.</span></span> <span data-ttu-id="37c55-108">Du bör först fastställa om några avskrivningstransaktioner bokfördes efter den transaktion som du återför.</span><span class="sxs-lookup"><span data-stu-id="37c55-108">You should first determine whether any depreciation transactions were posted after the transaction that you are reversing.</span></span> <span data-ttu-id="37c55-109">Detta eftersom avskrivning inte räknas om när du återför en transaktion.</span><span class="sxs-lookup"><span data-stu-id="37c55-109">This is because depreciation is not recalculated when you reverse a transaction.</span></span> <span data-ttu-id="37c55-110">Därför blir avskrivningen ofta för hög eller för låg efter återföringen, vilket exemplen visar.</span><span class="sxs-lookup"><span data-stu-id="37c55-110">Therefore, depreciation often is overstated or understated after the reversal, as shown in the examples.</span></span> 

<span data-ttu-id="37c55-111">Om du vill vara säker på att avskrivningen är korrekt när du återför en transaktion, gå inte vidare med återföringen om du får ett meddelande om att avskrivningen inte räknas om.</span><span class="sxs-lookup"><span data-stu-id="37c55-111">To make sure that depreciation is correct when you reverse a transaction, do not continue with the reversal if you receive a message that states that depreciation will not be recalculated.</span></span> <span data-ttu-id="37c55-112">Återför istället först avskrivningstransaktionen som bokfördes efter att den transaktion som du försökte du återföra och fortsätt sedan med återföringen.</span><span class="sxs-lookup"><span data-stu-id="37c55-112">Instead, first reverse the depreciation transaction that was posted after the transaction you tried to reverse, and then continue with the reversal.</span></span> <span data-ttu-id="37c55-113">Du varnas inte om omberäkningar av avskrivning och du kan gå vidare med återföringen.</span><span class="sxs-lookup"><span data-stu-id="37c55-113">You will not be warned about depreciation recalculations, and you can continue with the reversal.</span></span> 

<span data-ttu-id="37c55-114">Följande exempel visar de omberäkningar som genomförs om du fortsätter utan att beakta meddelandet att först återföra avskrivningstransaktionerna.</span><span class="sxs-lookup"><span data-stu-id="37c55-114">The following examples show the calculations that occur if you continue beyond the message without first reversing the depreciation transactions.</span></span>

## <a name="example-1-depreciation-is-overstated"></a><span data-ttu-id="37c55-115"> Exempel 1: Avskrivningen är för hög</span><span class="sxs-lookup"><span data-stu-id="37c55-115">Example 1: Depreciation is overstated</span></span>
<span data-ttu-id="37c55-116">En tillgång har registrerats med en livslängd på fem år och linjär avskrivning (60 avskrivningsperioder).</span><span class="sxs-lookup"><span data-stu-id="37c55-116">An asset is set up with a 5-year useful life and straight line depreciation (60 depreciation periods).</span></span> <span data-ttu-id="37c55-117">I det här exemplet blir avskrivningen för hög.</span><span class="sxs-lookup"><span data-stu-id="37c55-117">In this example, depreciation is overstated.</span></span>
#### <a name="asset-transaction-history"></a><span data-ttu-id="37c55-118">Tillgångens transaktionshistorik</span><span class="sxs-lookup"><span data-stu-id="37c55-118">Asset transaction history</span></span>

| <span data-ttu-id="37c55-119">Datum</span><span class="sxs-lookup"><span data-stu-id="37c55-119">Date</span></span>       | <span data-ttu-id="37c55-120">Transaktionstyp</span><span class="sxs-lookup"><span data-stu-id="37c55-120">Transaction type</span></span>                                                          | <span data-ttu-id="37c55-121">Belopp</span><span class="sxs-lookup"><span data-stu-id="37c55-121">Amount</span></span>                                    |
|------------|---------------------------------------------------------------------------|-------------------------------------------|
| <span data-ttu-id="37c55-122">1 januari</span><span class="sxs-lookup"><span data-stu-id="37c55-122">January 1</span></span>  | <span data-ttu-id="37c55-123">Anskaffning</span><span class="sxs-lookup"><span data-stu-id="37c55-123">Acquisition</span></span>                                                               | <span data-ttu-id="37c55-124">59 000,00</span><span class="sxs-lookup"><span data-stu-id="37c55-124">59,000.00</span></span>                                 |
| <span data-ttu-id="37c55-125">1 januari</span><span class="sxs-lookup"><span data-stu-id="37c55-125">January 1</span></span>  | <span data-ttu-id="37c55-126">Anskaffningsjustering</span><span class="sxs-lookup"><span data-stu-id="37c55-126">Acquisition adjustment</span></span>                                                    | <span data-ttu-id="37c55-127">1 000,00</span><span class="sxs-lookup"><span data-stu-id="37c55-127">1,000.00</span></span>                                  |
| <span data-ttu-id="37c55-128">31 januari</span><span class="sxs-lookup"><span data-stu-id="37c55-128">January 31</span></span> | <span data-ttu-id="37c55-129">Avskrivning (skapad med ett förslag på en avskrivningsperiod)</span><span class="sxs-lookup"><span data-stu-id="37c55-129">Depreciation (created by using a proposal for one period of depreciation)</span></span> | <span data-ttu-id="37c55-130">1 000,00 Beräkning: Bokfört värde (59 000 + 1 000) / antal kvarstående avskrivningsperioder (60)</span><span class="sxs-lookup"><span data-stu-id="37c55-130">1,000.00Calculation: Book value (59,000 + 1,000) / Number of depreciation periods remaining (60)</span></span> |

#### <a name="reversal-action"></a><span data-ttu-id="37c55-131">Återföringsåtgärd</span><span class="sxs-lookup"><span data-stu-id="37c55-131">Reversal action</span></span>

| <span data-ttu-id="37c55-132">Datum</span><span class="sxs-lookup"><span data-stu-id="37c55-132">Date</span></span>      | <span data-ttu-id="37c55-133">transaktionstyp</span><span class="sxs-lookup"><span data-stu-id="37c55-133">Transaction type</span></span>                | <span data-ttu-id="37c55-134">Belopp</span><span class="sxs-lookup"><span data-stu-id="37c55-134">Amount</span></span>    |
|-----------|---------------------------------|-----------|
| <span data-ttu-id="37c55-135">1 januari</span><span class="sxs-lookup"><span data-stu-id="37c55-135">January 1</span></span> | <span data-ttu-id="37c55-136">Återföring av anskaffningsjustering</span><span class="sxs-lookup"><span data-stu-id="37c55-136">Acquisition adjustment reversal</span></span> | <span data-ttu-id="37c55-137">-1 000,00</span><span class="sxs-lookup"><span data-stu-id="37c55-137">–1,000.00</span></span> |

#### <a name="depreciation-effect"></a><span data-ttu-id="37c55-138">Avskrivningseffekt</span><span class="sxs-lookup"><span data-stu-id="37c55-138">Depreciation effect</span></span>

| <span data-ttu-id="37c55-139">Datum</span><span class="sxs-lookup"><span data-stu-id="37c55-139">Date</span></span>        | <span data-ttu-id="37c55-140">transaktionstyp</span><span class="sxs-lookup"><span data-stu-id="37c55-140">Transaction type</span></span>        | <span data-ttu-id="37c55-141">Belopp</span><span class="sxs-lookup"><span data-stu-id="37c55-141">Amount</span></span>                                                                                |
|-------------|-------------------------|---------------------------------------------------------------------------------------|
| <span data-ttu-id="37c55-142">28 februari</span><span class="sxs-lookup"><span data-stu-id="37c55-142">February 28</span></span> | <span data-ttu-id="37c55-143">Avskrivning (förslag)</span><span class="sxs-lookup"><span data-stu-id="37c55-143">Depreciation (proposal)</span></span> | <span data-ttu-id="37c55-144">983,05 Beräkning: Bokfört värde (59 000 - 1 000 avskrivning) / antal kvarstående avskrivningsperioder (59)</span><span class="sxs-lookup"><span data-stu-id="37c55-144">983.05Calculation: Book value (59,000 - 1,000 depreciation) / Number of depreciation periods remaining (59)</span></span> |

<span data-ttu-id="37c55-145">Avskrivningens värde är 16,95 för högt (1 000 – 983,05).</span><span class="sxs-lookup"><span data-stu-id="37c55-145">Depreciation is overstated by 16.95 (1,000 - 983.05).</span></span>

## <a name="example-2-depreciation-is-understated"></a><span data-ttu-id="37c55-146"> Exempel 2: Avskrivningen är för låg</span><span class="sxs-lookup"><span data-stu-id="37c55-146">Example 2: Depreciation is understated</span></span>
<span data-ttu-id="37c55-147">En tillgång har registrerats med en livslängd på fem år och linjär avskrivning (60 avskrivningsperioder).</span><span class="sxs-lookup"><span data-stu-id="37c55-147">An asset is set up with a 5-year useful life and straight line depreciation (60 depreciation periods).</span></span> <span data-ttu-id="37c55-148">I det här exemplet blir avskrivningen för låg.</span><span class="sxs-lookup"><span data-stu-id="37c55-148">In this example, depreciation is understated.</span></span>
#### <a name="asset-transaction-history"></a><span data-ttu-id="37c55-149">Tillgångens transaktionshistorik</span><span class="sxs-lookup"><span data-stu-id="37c55-149">Asset transaction history</span></span>

| <span data-ttu-id="37c55-150">Datum</span><span class="sxs-lookup"><span data-stu-id="37c55-150">Date</span></span>       | <span data-ttu-id="37c55-151">transaktionstyp</span><span class="sxs-lookup"><span data-stu-id="37c55-151">Transaction type</span></span>                                                          | <span data-ttu-id="37c55-152">Belopp</span><span class="sxs-lookup"><span data-stu-id="37c55-152">Amount</span></span>                                      |
|------------|---------------------------------------------------------------------------|---------------------------------------------|
| <span data-ttu-id="37c55-153">1 januari</span><span class="sxs-lookup"><span data-stu-id="37c55-153">January 1</span></span>  | <span data-ttu-id="37c55-154">Anskaffning</span><span class="sxs-lookup"><span data-stu-id="37c55-154">Acquisition</span></span>                                                               | <span data-ttu-id="37c55-155">59 000,00</span><span class="sxs-lookup"><span data-stu-id="37c55-155">59,000.00</span></span>                                   |
| <span data-ttu-id="37c55-156">1 januari</span><span class="sxs-lookup"><span data-stu-id="37c55-156">January 1</span></span>  | <span data-ttu-id="37c55-157">Nedskrivning</span><span class="sxs-lookup"><span data-stu-id="37c55-157">Write-down adjustment</span></span>                                                     | <span data-ttu-id="37c55-158">1 000,00</span><span class="sxs-lookup"><span data-stu-id="37c55-158">1,000.00</span></span>                                    |
| <span data-ttu-id="37c55-159">31 januari</span><span class="sxs-lookup"><span data-stu-id="37c55-159">January 31</span></span> | <span data-ttu-id="37c55-160">Avskrivning (skapad med ett förslag på en avskrivningsperiod)</span><span class="sxs-lookup"><span data-stu-id="37c55-160">Depreciation (created by using a proposal for one period of depreciation)</span></span> | <span data-ttu-id="37c55-161">966,67 Beräkning: Bokfört värde (59 000 - 1 000) / antal kvarstående avskrivningsperioder (60)</span><span class="sxs-lookup"><span data-stu-id="37c55-161">966.67Calculation: Book value (59,000 - 1,000) / Number of depreciation periods remaining (60)</span></span> |

#### <a name="reversal-action"></a><span data-ttu-id="37c55-162">Återföringsåtgärd</span><span class="sxs-lookup"><span data-stu-id="37c55-162">Reversal action</span></span>

| <span data-ttu-id="37c55-163">Datum</span><span class="sxs-lookup"><span data-stu-id="37c55-163">Date</span></span>      | <span data-ttu-id="37c55-164">transaktionstyp</span><span class="sxs-lookup"><span data-stu-id="37c55-164">Transaction type</span></span>               | <span data-ttu-id="37c55-165">Belopp</span><span class="sxs-lookup"><span data-stu-id="37c55-165">Amount</span></span>    |
|-----------|--------------------------------|-----------|
| <span data-ttu-id="37c55-166">1 januari</span><span class="sxs-lookup"><span data-stu-id="37c55-166">January 1</span></span> | <span data-ttu-id="37c55-167">Återföring av nedskrivningsjustering</span><span class="sxs-lookup"><span data-stu-id="37c55-167">Write-down adjustment reversal</span></span> | <span data-ttu-id="37c55-168">-1 000,00</span><span class="sxs-lookup"><span data-stu-id="37c55-168">–1,000.00</span></span> |

#### <a name="depreciation-effect"></a><span data-ttu-id="37c55-169">Avskrivningseffekt</span><span class="sxs-lookup"><span data-stu-id="37c55-169">Depreciation effect</span></span>

| <span data-ttu-id="37c55-170">Datum</span><span class="sxs-lookup"><span data-stu-id="37c55-170">Date</span></span>        | <span data-ttu-id="37c55-171">transaktionstyp</span><span class="sxs-lookup"><span data-stu-id="37c55-171">Transaction type</span></span>        | <span data-ttu-id="37c55-172">Belopp</span><span class="sxs-lookup"><span data-stu-id="37c55-172">Amount</span></span>                                                                                       |
|-------------|-------------------------|----------------------------------------------------------------------------------------------|
| <span data-ttu-id="37c55-173">28 februari</span><span class="sxs-lookup"><span data-stu-id="37c55-173">February 28</span></span> | <span data-ttu-id="37c55-174">Avskrivning (förslag)</span><span class="sxs-lookup"><span data-stu-id="37c55-174">Depreciation (proposal)</span></span> | <span data-ttu-id="37c55-175">983,62 Beräkning: Bokfört värde (59 000 - 966,67 avskrivning) / antal kvarstående avskrivningsperioder (59)</span><span class="sxs-lookup"><span data-stu-id="37c55-175">983.62Calculation: Book value (59,000 - 966.67 depreciation) / Number of depreciation periods remaining (59)</span></span> |

<span data-ttu-id="37c55-176">Avskrivningens värde är 16,95 för lågt (983,62 – 966,67).</span><span class="sxs-lookup"><span data-stu-id="37c55-176">Depreciation is understated by 16.95 (983.62 - 966.67).</span></span>



<a name="additional-resources"></a><span data-ttu-id="37c55-177">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="37c55-177">Additional resources</span></span>
--------

[<span data-ttu-id="37c55-178">Avskrivning av anläggningstillgång</span><span class="sxs-lookup"><span data-stu-id="37c55-178">Fixed asset depreciation</span></span>](fixed-asset-depreciation.md)




