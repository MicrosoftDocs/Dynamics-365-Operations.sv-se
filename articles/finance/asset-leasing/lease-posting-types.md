---
title: Bokföringstyper för leasing
description: Det här ämnet beskriver de bokföringstyper som används för leasingtransaktioner för tillgångar.
author: moaamer
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: ddc229f3ab8e048390f27503e2c6c26bd1a6f24f
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5841151"
---
# <a name="lease-posting-types"></a><span data-ttu-id="ba3ec-103">Bokföringstyper för leasing</span><span class="sxs-lookup"><span data-stu-id="ba3ec-103">Lease posting types</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ba3ec-104">Det här ämnet beskriver de bokföringstyper som används för leasingtransaktioner för tillgångar.</span><span class="sxs-lookup"><span data-stu-id="ba3ec-104">This topic describes the posting types that are used for asset leasing transactions.</span></span>

## <a name="lease-asset"></a><span data-ttu-id="ba3ec-105">Leasingtillgång</span><span class="sxs-lookup"><span data-stu-id="ba3ec-105">Lease asset</span></span>

<span data-ttu-id="ba3ec-106">Kontot är kopplat till tillgången med nyttjanderätt (ROU, Right Of Use).</span><span class="sxs-lookup"><span data-stu-id="ba3ec-106">The account is associated with the right-of-use (ROU) asset.</span></span> <span data-ttu-id="ba3ec-107">Det här kontot debiteras när en leasing först redovisas enligt de nya bokföringsstandarderna för leasing, Accounting Standards Codification Topic 842 (ASC 842) och International Financial Reporting Standard 16 (IFRS 16).</span><span class="sxs-lookup"><span data-stu-id="ba3ec-107">This account is debited when a lease is initially recognized under the new lease accounting standards, Accounting Standards Codification Topic 842 (ASC 842) and International Financial Reporting Standard 16 (IFRS 16).</span></span> <span data-ttu-id="ba3ec-108">För en modifierad leasing kan detta konto antingen debiteras eller krediteras, beroende på om ändringen ökar eller minskar leasingskulden.</span><span class="sxs-lookup"><span data-stu-id="ba3ec-108">For a modified lease, this account might be either debited or credited, depending on whether the modification increases or decreases the lease liability.</span></span>

<span data-ttu-id="ba3ec-109">**Exempel på journalposter:** Första redovisningstillfället</span><span class="sxs-lookup"><span data-stu-id="ba3ec-109">**Example journal entries:** Initial recognition</span></span><br>
<span data-ttu-id="ba3ec-110">**Debet:** Leasingtillgång XXX</span><span class="sxs-lookup"><span data-stu-id="ba3ec-110">**Debit:** Lease asset XXX</span></span><br>
<span data-ttu-id="ba3ec-111">**Kredit:** Leasingskuld XXX</span><span class="sxs-lookup"><span data-stu-id="ba3ec-111">**Credit:** Lease liability XXX</span></span>

## <a name="lease-liability"></a><span data-ttu-id="ba3ec-112">Leasingskuld</span><span class="sxs-lookup"><span data-stu-id="ba3ec-112">Lease liability</span></span>

<span data-ttu-id="ba3ec-113">Kontot är kopplat till den leasingskuld som uppstår när betalningarna diskonteras enligt de nya IFRS 16- och ASC 842-standarderna.</span><span class="sxs-lookup"><span data-stu-id="ba3ec-113">The account is associated with the lease liability that occurs when payments are discounted under the new IFRS 16 and ASC 842 standards.</span></span> <span data-ttu-id="ba3ec-114">Det här kontot krediteras när en leasing först redovisas enligt de nya standarderna.</span><span class="sxs-lookup"><span data-stu-id="ba3ec-114">This account is credited when a lease is initially recognized under the new standards.</span></span> <span data-ttu-id="ba3ec-115">Det debiteras för leasingbetalningar och krediteras för upplupna räntor.</span><span class="sxs-lookup"><span data-stu-id="ba3ec-115">It's debited for lease payments and credited for interest accruals.</span></span>

<span data-ttu-id="ba3ec-116">**Exempel på journalposter:** Första redovisningstillfället</span><span class="sxs-lookup"><span data-stu-id="ba3ec-116">**Example journal entries:** Initial recognition</span></span><br>
<span data-ttu-id="ba3ec-117">**Debet:** Leasingtillgång XXX</span><span class="sxs-lookup"><span data-stu-id="ba3ec-117">**Debit:** Lease asset XXX</span></span><br>
<span data-ttu-id="ba3ec-118">**Kredit:** Leasingskuld XXX</span><span class="sxs-lookup"><span data-stu-id="ba3ec-118">**Credit:** Lease liability XXX</span></span>

<span data-ttu-id="ba3ec-119">**Exempel på journalposter:** Upplupen ränta</span><span class="sxs-lookup"><span data-stu-id="ba3ec-119">**Example journal entries:** Interest accrual</span></span><br>
<span data-ttu-id="ba3ec-120">**Debet:** Räntekostnad XXX</span><span class="sxs-lookup"><span data-stu-id="ba3ec-120">**Debit:** Interest expense XXX</span></span><br>
<span data-ttu-id="ba3ec-121">**Kredit:** Leasingskuld XXX</span><span class="sxs-lookup"><span data-stu-id="ba3ec-121">**Credit:** Lease liability XXX</span></span>

<span data-ttu-id="ba3ec-122">**Exempel på journalposter:** Leasingbetalning</span><span class="sxs-lookup"><span data-stu-id="ba3ec-122">**Example journal entries:** Lease payment</span></span><br>
<span data-ttu-id="ba3ec-123">**Debet:** Leasingskuld XXX</span><span class="sxs-lookup"><span data-stu-id="ba3ec-123">**Debit:** Lease liability XXX</span></span><br>
<span data-ttu-id="ba3ec-124">**Kredit:** Leverantörsskuld/leasingbetalning XXX</span><span class="sxs-lookup"><span data-stu-id="ba3ec-124">**Credit:** Vendor payable/lease payment XXX</span></span>

## <a name="short-term-lease-liability"></a><span data-ttu-id="ba3ec-125">Kortfristig leasingskuld</span><span class="sxs-lookup"><span data-stu-id="ba3ec-125">Short-term lease liability</span></span>

<span data-ttu-id="ba3ec-126">Kontot associeras med korttidsleasingskulden när korttidsleasingens journalpost för omklassificering bokförs.</span><span class="sxs-lookup"><span data-stu-id="ba3ec-126">The account is associated with the short-term lease liability when the short-term lease liability reclass journal entry is posted.</span></span> <span data-ttu-id="ba3ec-127">Det här kontot krediteras för kortfristiga skulder från amorteringsplanen på den sista dagen i månaden.</span><span class="sxs-lookup"><span data-stu-id="ba3ec-127">This account is credited for the short-term liability from the amortization schedule on the last day of the month.</span></span> <span data-ttu-id="ba3ec-128">Samma belopp debiteras på den första dagen i nästa månad.</span><span class="sxs-lookup"><span data-stu-id="ba3ec-128">However, the same amount is debited on the first day of the next month.</span></span>

<span data-ttu-id="ba3ec-129">**Exempel på journalposter:** Omklassificering av kortfristig leasingskuld</span><span class="sxs-lookup"><span data-stu-id="ba3ec-129">**Example journal entries:** Short-term lease liability reclass</span></span><br>
<span data-ttu-id="ba3ec-130">**Debet:** Leasingskuld XXX</span><span class="sxs-lookup"><span data-stu-id="ba3ec-130">**Debit:** Lease liability XXX</span></span><br>
<span data-ttu-id="ba3ec-131">**Kredit:** Kortfristig leasingskuld XXX</span><span class="sxs-lookup"><span data-stu-id="ba3ec-131">**Credit:** Short-term lease liability XXX</span></span><br>
<span data-ttu-id="ba3ec-132">**Debet:** Kortfristig leasingskuld XXX</span><span class="sxs-lookup"><span data-stu-id="ba3ec-132">**Debit:** Short-term lease liability XXX</span></span><br>
<span data-ttu-id="ba3ec-133">**Kredit:** Leasingskuld XXX</span><span class="sxs-lookup"><span data-stu-id="ba3ec-133">**Credit:** Lease liability XXX</span></span>

## <a name="depreciation-expense"></a><span data-ttu-id="ba3ec-134">Avskrivningsutgift</span><span class="sxs-lookup"><span data-stu-id="ba3ec-134">Depreciation expense</span></span>

<span data-ttu-id="ba3ec-135">Kontot är kopplat till den kostnad som är relaterad till avskrivningen av ROU-tillgången enligt IFRS 16, ASC 842 och finansiella leasingavtal enligt IAS 17 och ASC 840.</span><span class="sxs-lookup"><span data-stu-id="ba3ec-135">The account is associated with the expense that is related to the depreciation of the ROU asset under IFRS 16, ASC 842, and finance leases under IAS 17 and ASC 840.</span></span> <span data-ttu-id="ba3ec-136">Det här kontot debiteras när en ROU-tillgång skrivs av varje månad.</span><span class="sxs-lookup"><span data-stu-id="ba3ec-136">This account is debited when an ROU asset is depreciated each month.</span></span>

<span data-ttu-id="ba3ec-137">**Exempel på journalposter:** Upplupen avskrivning</span><span class="sxs-lookup"><span data-stu-id="ba3ec-137">**Example journal entries:** Depreciation accrual</span></span><br>
<span data-ttu-id="ba3ec-138">**Debet:** Avskrivningskostnad XXX</span><span class="sxs-lookup"><span data-stu-id="ba3ec-138">**Debit:** Depreciation expense XXX</span></span><br>
<span data-ttu-id="ba3ec-139">**Kredit:** Ackumulerad avskrivning XXX</span><span class="sxs-lookup"><span data-stu-id="ba3ec-139">**Credit:** Accumulated Depreciation XXX</span></span>

## <a name="gainloss-on-lease-modification"></a><span data-ttu-id="ba3ec-140">Vinst/förlust vid leasingändring</span><span class="sxs-lookup"><span data-stu-id="ba3ec-140">Gain/loss on lease modification</span></span>

<span data-ttu-id="ba3ec-141">Kontot är kopplat till vinster eller förluster som uppstår vid ändringar av leasingavtalet.</span><span class="sxs-lookup"><span data-stu-id="ba3ec-141">The account is associated with any gains or losses that arise from lease modifications.</span></span> <span data-ttu-id="ba3ec-142">En vinst kan uppstå under en leasingändring om ändringen minskar leasingskulden med ett belopp som överstiger det bokförda värdet för ROU-tillgången.</span><span class="sxs-lookup"><span data-stu-id="ba3ec-142">A gain might arise during a lease modification if the modification decreases the lease liability by an amount that exceeds the carrying value of the ROU asset.</span></span>

<span data-ttu-id="ba3ec-143">Ett leasingavtal har till exempel ett aktuellt bokfört värde för låneskulden på 150 000 USD och ett bokfört värde på ROU-tillgången på 100 000 USD.</span><span class="sxs-lookup"><span data-stu-id="ba3ec-143">For example, a lease has a current carrying value of the lease liability of $150,000 and a carrying value of the ROU asset of $100,000.</span></span> <span data-ttu-id="ba3ec-144">Leasingavtalet ändras och denna ändring ger ett nytt nuvärde för de framtida lägsta leasingbetalningarna (PVFMLP) på 40 000 USD.</span><span class="sxs-lookup"><span data-stu-id="ba3ec-144">The lease is modified, and this modification produces a new present value of the future minimum lease payments (PVFMLP) of $40,000.</span></span> <span data-ttu-id="ba3ec-145">Därför debiteras leasingskulden med 110 000 USD (150 000 USD – 40 000 USD).</span><span class="sxs-lookup"><span data-stu-id="ba3ec-145">Therefore, the lease liability will be debited by $110,000 ($150,000 – $40,000).</span></span> <span data-ttu-id="ba3ec-146">Eftersom ROU-tillgången bara är 100 000 USD gör minskningen på 110 000 USD att tillgången minskar under 0 (noll).</span><span class="sxs-lookup"><span data-stu-id="ba3ec-146">Because the ROU asset is only $100,000, the decrease of $110,000 will decrease the asset past 0 (zero).</span></span> <span data-ttu-id="ba3ec-147">Därför anger redovisningsvägledningen att resten ska bokföras på ett vinstkonto.</span><span class="sxs-lookup"><span data-stu-id="ba3ec-147">Therefore, the accounting guidance states that the remainder should be booked to a gain account.</span></span> <span data-ttu-id="ba3ec-148">I det här fallet är den slutliga journalposten en debitering till leasingskulden på 110 000 USD, en kredit till leasingtillgången på 100 000 USD och en kredit till vinstkontot på 10 000 USD.</span><span class="sxs-lookup"><span data-stu-id="ba3ec-148">In this case, the final journal entry will be a debit to the lease liability for $110,000, a credit to the lease asset for $100,000, and a credit to the gain account for $10,000.</span></span>

<span data-ttu-id="ba3ec-149">**Exempel på journalposter:** Leasingändring</span><span class="sxs-lookup"><span data-stu-id="ba3ec-149">**Example journal entries:** Lease modification</span></span><br>
<span data-ttu-id="ba3ec-150">**Debet:** Leasingskuld XXX</span><span class="sxs-lookup"><span data-stu-id="ba3ec-150">**Debit:** Lease liability XXX</span></span><br>
<span data-ttu-id="ba3ec-151">**Kredit:** Leasingtillgång XXX</span><span class="sxs-lookup"><span data-stu-id="ba3ec-151">**Credit:** Lease Asset XXX</span></span><br>
<span data-ttu-id="ba3ec-152">**Kredit:** Vinst XXX</span><span class="sxs-lookup"><span data-stu-id="ba3ec-152">**Credit:** Gain XXX</span></span>

## <a name="accumulated-depreciation"></a><span data-ttu-id="ba3ec-153">Ackumulerad avskrivning</span><span class="sxs-lookup"><span data-stu-id="ba3ec-153">Accumulated depreciation</span></span>

<span data-ttu-id="ba3ec-154">Kontot är kopplat till motkontot för ROU-tillgången.</span><span class="sxs-lookup"><span data-stu-id="ba3ec-154">The account is associated with the contra-asset account of the ROU asset.</span></span> <span data-ttu-id="ba3ec-155">Det här kontot krediteras när en avskrivningskostnad bokförs.</span><span class="sxs-lookup"><span data-stu-id="ba3ec-155">This account is credited when a depreciation expense is posted.</span></span>

<span data-ttu-id="ba3ec-156">**Exempel på journalposter:** Upplupen avskrivning</span><span class="sxs-lookup"><span data-stu-id="ba3ec-156">**Example journal entries:** Depreciation accrual</span></span><br>
<span data-ttu-id="ba3ec-157">**Debet:** Avskrivningskostnad XXX</span><span class="sxs-lookup"><span data-stu-id="ba3ec-157">**Debit:** Depreciation expense XXX</span></span><br>
<span data-ttu-id="ba3ec-158">**Kredit:** Ackumulerad avskrivning XXX</span><span class="sxs-lookup"><span data-stu-id="ba3ec-158">**Credit:** Accumulated depreciation XXX</span></span>

## <a name="variable-payment"></a><span data-ttu-id="ba3ec-159">Variabel betalning</span><span class="sxs-lookup"><span data-stu-id="ba3ec-159">Variable payment</span></span>

<span data-ttu-id="ba3ec-160">Kontot är kopplat till variabla leasingbetalningar som skapas genom en indexerad omvärdering enligt ASC 842, ASC 840 och IAS 17-leasingar.</span><span class="sxs-lookup"><span data-stu-id="ba3ec-160">The account is associated with variable lease payments that are produced by an index revaluation under ASC 842, ASC 840, and IAS 17 leases.</span></span> <span data-ttu-id="ba3ec-161">I betalningsplanen för leasing inkluderas variabla betalningar i kolumnen **Variabel betalning**.</span><span class="sxs-lookup"><span data-stu-id="ba3ec-161">In the lease payment schedule, variable payments are included in the **Variable payment** column.</span></span> <span data-ttu-id="ba3ec-162">Det här kontot debiteras när en faktura skapas mot en betalningsplanrad som innehåller en variabel betalning.</span><span class="sxs-lookup"><span data-stu-id="ba3ec-162">This account is debited when an invoice is created against a payment schedule line that contains a variable payment.</span></span>

<span data-ttu-id="ba3ec-163">**Exempel på journalposter:** Leasingbetalning</span><span class="sxs-lookup"><span data-stu-id="ba3ec-163">**Example journal entries:** Lease payment</span></span><br>
<span data-ttu-id="ba3ec-164">**Debet:** Leasingskuld XXX</span><span class="sxs-lookup"><span data-stu-id="ba3ec-164">**Debit:** Lease liability XXX</span></span><br>
<span data-ttu-id="ba3ec-165">**Debet:** Variabel betalning XXX</span><span class="sxs-lookup"><span data-stu-id="ba3ec-165">**Debit:** Variable payment XXX</span></span><br>
<span data-ttu-id="ba3ec-166">**Kredit:** Leverantörsskuld/leasingbetalning XXX</span><span class="sxs-lookup"><span data-stu-id="ba3ec-166">**Credit:** Vendor payable/lease payment XXX</span></span>

## <a name="deferred-rent-asset-liability"></a><span data-ttu-id="ba3ec-167">Uppskov av leasingavgift (skuld)</span><span class="sxs-lookup"><span data-stu-id="ba3ec-167">Deferred rent asset (liability)</span></span>

<span data-ttu-id="ba3ec-168">Kontot är kopplat till den uppskjutna leasingavgiften eller skulden som produceras av ett leasingavtal med uppskov av leasingavgift.</span><span class="sxs-lookup"><span data-stu-id="ba3ec-168">The account is associated with the deferred rent asset or liability that is produced by a deferred rent treatment lease.</span></span> <span data-ttu-id="ba3ec-169">Det här kontot debiteras när en faktura bokförs mot ett leasingavtal med uppskov av leasingavgift, om leasingbetalningsbeloppet är mer än periodens linjära hyreskostnad.</span><span class="sxs-lookup"><span data-stu-id="ba3ec-169">This account is debited when an invoice is posted against a deferred rent treatment lease, if the lease payment amount is more than the period's straight-line rent expense.</span></span> <span data-ttu-id="ba3ec-170">Det krediteras om leasingbetalningen är mindre än periodens linjära hyreskostnad.</span><span class="sxs-lookup"><span data-stu-id="ba3ec-170">It's credited if the lease payment is less than the period's straight-line rent expense.</span></span>

<span data-ttu-id="ba3ec-171">**Exempel på journalposter:** Leasingbetalning (leasing med uppskov av leasingavgift)</span><span class="sxs-lookup"><span data-stu-id="ba3ec-171">**Example journal entries:** Lease payment (deferred rent treatment lease)</span></span><br>
<span data-ttu-id="ba3ec-172">**Debet:** Leasingkostnad XXX</span><span class="sxs-lookup"><span data-stu-id="ba3ec-172">**Debit:** Lease expense XXX</span></span><br>
<span data-ttu-id="ba3ec-173">**Kredit:** Uppskov av leasingavgift (skuld) XXX</span><span class="sxs-lookup"><span data-stu-id="ba3ec-173">**Credit:** Deferred rent liability XXX</span></span><br>
<span data-ttu-id="ba3ec-174">**Kredit:** Leverantörsskuld/leasingbetalning XXX</span><span class="sxs-lookup"><span data-stu-id="ba3ec-174">**Credit:** Vendor payable/lease payment XXX</span></span>

## <a name="lease-expense"></a><span data-ttu-id="ba3ec-175">Leasingkostnad</span><span class="sxs-lookup"><span data-stu-id="ba3ec-175">Lease expense</span></span>

<span data-ttu-id="ba3ec-176">Kontot är kopplat till leasingkostnaden om leasingavtalet klassificeras som ett leasingavtal med uppskov av leasingavgift.</span><span class="sxs-lookup"><span data-stu-id="ba3ec-176">The account is associated with the lease expense if the lease is classified as a deferred rent treatment lease.</span></span> <span data-ttu-id="ba3ec-177">Det här kontot debiteras när en faktura bokförs mot en leasingavtal med uppskov av leasingavgift.</span><span class="sxs-lookup"><span data-stu-id="ba3ec-177">This account is debited when an invoice is posted against a deferred rent treatment lease.</span></span>

<span data-ttu-id="ba3ec-178">**Exempel på journalposter:** Leasingbetalning (leasing med uppskov av leasingavgift)</span><span class="sxs-lookup"><span data-stu-id="ba3ec-178">**Example journal entries:** Lease payment (deferred rent treatment lease)</span></span><br>
<span data-ttu-id="ba3ec-179">**Debet:** Leasingkostnad XXX</span><span class="sxs-lookup"><span data-stu-id="ba3ec-179">**Debit:** Lease expense XXX</span></span><br>
<span data-ttu-id="ba3ec-180">**Kredit:** Uppskov av leasingavgift (skuld) XXX</span><span class="sxs-lookup"><span data-stu-id="ba3ec-180">**Credit:** Deferred rent liability XXX</span></span><br>
<span data-ttu-id="ba3ec-181">**Kredit:** Leverantörsskuld/leasingbetalning XXX</span><span class="sxs-lookup"><span data-stu-id="ba3ec-181">**Credit:** Vendor payable/lease payment XXX</span></span>

## <a name="impairment-expense"></a><span data-ttu-id="ba3ec-182">Nedskrivningsutgift</span><span class="sxs-lookup"><span data-stu-id="ba3ec-182">Impairment expense</span></span>

<span data-ttu-id="ba3ec-183">Kontot motbokas när en leasing skrivs ner.</span><span class="sxs-lookup"><span data-stu-id="ba3ec-183">The account is posted against when a lease is impaired.</span></span> <span data-ttu-id="ba3ec-184">Det här kontot debiteras men ROU-tillgångskontot krediteras direkt.</span><span class="sxs-lookup"><span data-stu-id="ba3ec-184">This account is debited, whereas the ROU asset account is directly credited.</span></span>

<span data-ttu-id="ba3ec-185">**Exempel på journalposter:** Leasingbetalning</span><span class="sxs-lookup"><span data-stu-id="ba3ec-185">**Example journal entries:** Lease payment</span></span><br>
<span data-ttu-id="ba3ec-186">**Debet:** Nedskrivningsutgift XXX</span><span class="sxs-lookup"><span data-stu-id="ba3ec-186">**Debit:** Impairment expense XXX</span></span><br>
<span data-ttu-id="ba3ec-187">**Kredit:** ROU-tillgång XXX</span><span class="sxs-lookup"><span data-stu-id="ba3ec-187">**Credit:** ROU asset XXX</span></span>

## <a name="lease-payment"></a><span data-ttu-id="ba3ec-188">Leasingbetalning</span><span class="sxs-lookup"><span data-stu-id="ba3ec-188">Lease payment</span></span>

<span data-ttu-id="ba3ec-189">Kontot motbokas om parametern **Betala till leverantör** är inaktiverad.</span><span class="sxs-lookup"><span data-stu-id="ba3ec-189">The account is posted against if the **Pay to Vendor** parameter is turned off.</span></span> <span data-ttu-id="ba3ec-190">Det här kontot krediteras i stället för leverantörsskulden om parametern är inaktiverad.</span><span class="sxs-lookup"><span data-stu-id="ba3ec-190">This account is credited instead of the vendor payable if the parameter is turned off.</span></span>

<span data-ttu-id="ba3ec-191">**Exempel på journalposter:** Leasingbetalning</span><span class="sxs-lookup"><span data-stu-id="ba3ec-191">**Example journal entries:** Lease payment</span></span><br>
<span data-ttu-id="ba3ec-192">**Debet:** Leasingskuld XXX</span><span class="sxs-lookup"><span data-stu-id="ba3ec-192">**Debit:** Lease liability XXX</span></span><br>
<span data-ttu-id="ba3ec-193">**Kredit:** Leasingbetalning XXX</span><span class="sxs-lookup"><span data-stu-id="ba3ec-193">**Credit:** Lease payment XXX</span></span>

## <a name="expense-type-postings"></a><span data-ttu-id="ba3ec-194">Bokföring av utgiftstyp</span><span class="sxs-lookup"><span data-stu-id="ba3ec-194">Expense type postings</span></span>

<span data-ttu-id="ba3ec-195">Det konto som väljs för varje utgiftstyp debiteras när en betalning för den utgiftstypen genereras.</span><span class="sxs-lookup"><span data-stu-id="ba3ec-195">The account that is selected for each expense type is debited when a payment for that expense type is generated.</span></span> <span data-ttu-id="ba3ec-196">Kontot som anges för utgiftstypen **Försäkring** debiteras till exempel när en faktura eller en betalningsjournalpost skapas från verkställighetskostnaden för försäkringsutgift.</span><span class="sxs-lookup"><span data-stu-id="ba3ec-196">For example, the account that is specified for the **Insurance** expense type is debited whenever an invoice or payment journal entry is created from the executory cost schedule for insurance expense.</span></span>

<span data-ttu-id="ba3ec-197">**Exempel på journalposter:** Försäkringsbetalning</span><span class="sxs-lookup"><span data-stu-id="ba3ec-197">**Example journal entries:** Insurance payment</span></span><br>
<span data-ttu-id="ba3ec-198">**Debet:** Konto XXX av försäkringsutgiftstyp</span><span class="sxs-lookup"><span data-stu-id="ba3ec-198">**Debit:** Insurance expense type account XXX</span></span><br>
<span data-ttu-id="ba3ec-199">**Kredit:** Motkonto XXX</span><span class="sxs-lookup"><span data-stu-id="ba3ec-199">**Credit:** Offset account XXX</span></span>

> [!NOTE]
> <span data-ttu-id="ba3ec-200">Motkontot väljs på leasingnivå på raderna för betalningsplanen för verkställighetskostnad.</span><span class="sxs-lookup"><span data-stu-id="ba3ec-200">The offset account is selected at the lease level on the lines for the executory cost payment schedule.</span></span> <span data-ttu-id="ba3ec-201">Det här motkontot kan kopplas till leverantören eller till ett huvudbokskonto.</span><span class="sxs-lookup"><span data-stu-id="ba3ec-201">This offset account can associated with the vendor, or with a ledger account.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
