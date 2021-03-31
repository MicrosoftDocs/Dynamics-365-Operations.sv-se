---
title: Bokföringstyper för leasing
description: Det här ämnet beskriver de bokföringstyper som används för leasingtransaktioner för tillgångar.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
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
ms.openlocfilehash: 9b7d8c545c1addaa570d54855bbad6c576783007
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5229512"
---
# <a name="lease-posting-types"></a><span data-ttu-id="38048-103">Bokföringstyper för leasing</span><span class="sxs-lookup"><span data-stu-id="38048-103">Lease posting types</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="38048-104">Det här ämnet beskriver de bokföringstyper som används för leasingtransaktioner för tillgångar.</span><span class="sxs-lookup"><span data-stu-id="38048-104">This topic describes the posting types that are used for asset leasing transactions.</span></span>

## <a name="lease-asset"></a><span data-ttu-id="38048-105">Leasingtillgång</span><span class="sxs-lookup"><span data-stu-id="38048-105">Lease asset</span></span>

<span data-ttu-id="38048-106">Kontot är kopplat till tillgången med nyttjanderätt (ROU, Right Of Use).</span><span class="sxs-lookup"><span data-stu-id="38048-106">The account is associated with the right-of-use (ROU) asset.</span></span> <span data-ttu-id="38048-107">Det här kontot debiteras när en leasing först redovisas enligt de nya bokföringsstandarderna för leasing, Accounting Standards Codification Topic 842 (ASC 842) och International Financial Reporting Standard 16 (IFRS 16).</span><span class="sxs-lookup"><span data-stu-id="38048-107">This account is debited when a lease is initially recognized under the new lease accounting standards, Accounting Standards Codification Topic 842 (ASC 842) and International Financial Reporting Standard 16 (IFRS 16).</span></span> <span data-ttu-id="38048-108">För en modifierad leasing kan detta konto antingen debiteras eller krediteras, beroende på om ändringen ökar eller minskar leasingskulden.</span><span class="sxs-lookup"><span data-stu-id="38048-108">For a modified lease, this account might be either debited or credited, depending on whether the modification increases or decreases the lease liability.</span></span>

<span data-ttu-id="38048-109">**Exempel på journalposter:** Första redovisningstillfället</span><span class="sxs-lookup"><span data-stu-id="38048-109">**Example journal entries:** Initial recognition</span></span><br>
<span data-ttu-id="38048-110">**Debet:** Leasingtillgång XXX</span><span class="sxs-lookup"><span data-stu-id="38048-110">**Debit:** Lease asset XXX</span></span><br>
<span data-ttu-id="38048-111">**Kredit:** Leasingskuld XXX</span><span class="sxs-lookup"><span data-stu-id="38048-111">**Credit:** Lease liability XXX</span></span>

## <a name="lease-liability"></a><span data-ttu-id="38048-112">Leasingskuld</span><span class="sxs-lookup"><span data-stu-id="38048-112">Lease liability</span></span>

<span data-ttu-id="38048-113">Kontot är kopplat till den leasingskuld som uppstår när betalningarna diskonteras enligt de nya IFRS 16- och ASC 842-standarderna.</span><span class="sxs-lookup"><span data-stu-id="38048-113">The account is associated with the lease liability that occurs when payments are discounted under the new IFRS 16 and ASC 842 standards.</span></span> <span data-ttu-id="38048-114">Det här kontot krediteras när en leasing först redovisas enligt de nya standarderna.</span><span class="sxs-lookup"><span data-stu-id="38048-114">This account is credited when a lease is initially recognized under the new standards.</span></span> <span data-ttu-id="38048-115">Det debiteras för leasingbetalningar och krediteras för upplupna räntor.</span><span class="sxs-lookup"><span data-stu-id="38048-115">It's debited for lease payments and credited for interest accruals.</span></span>

<span data-ttu-id="38048-116">**Exempel på journalposter:** Första redovisningstillfället</span><span class="sxs-lookup"><span data-stu-id="38048-116">**Example journal entries:** Initial recognition</span></span><br>
<span data-ttu-id="38048-117">**Debet:** Leasingtillgång XXX</span><span class="sxs-lookup"><span data-stu-id="38048-117">**Debit:** Lease asset XXX</span></span><br>
<span data-ttu-id="38048-118">**Kredit:** Leasingskuld XXX</span><span class="sxs-lookup"><span data-stu-id="38048-118">**Credit:** Lease liability XXX</span></span>

<span data-ttu-id="38048-119">**Exempel på journalposter:** Upplupen ränta</span><span class="sxs-lookup"><span data-stu-id="38048-119">**Example journal entries:** Interest accrual</span></span><br>
<span data-ttu-id="38048-120">**Debet:** Räntekostnad XXX</span><span class="sxs-lookup"><span data-stu-id="38048-120">**Debit:** Interest expense XXX</span></span><br>
<span data-ttu-id="38048-121">**Kredit:** Leasingskuld XXX</span><span class="sxs-lookup"><span data-stu-id="38048-121">**Credit:** Lease liability XXX</span></span>

<span data-ttu-id="38048-122">**Exempel på journalposter:** Leasingbetalning</span><span class="sxs-lookup"><span data-stu-id="38048-122">**Example journal entries:** Lease payment</span></span><br>
<span data-ttu-id="38048-123">**Debet:** Leasingskuld XXX</span><span class="sxs-lookup"><span data-stu-id="38048-123">**Debit:** Lease liability XXX</span></span><br>
<span data-ttu-id="38048-124">**Kredit:** Leverantörsskuld/leasingbetalning XXX</span><span class="sxs-lookup"><span data-stu-id="38048-124">**Credit:** Vendor payable/lease payment XXX</span></span>

## <a name="short-term-lease-liability"></a><span data-ttu-id="38048-125">Kortfristig leasingskuld</span><span class="sxs-lookup"><span data-stu-id="38048-125">Short-term lease liability</span></span>

<span data-ttu-id="38048-126">Kontot associeras med korttidsleasingskulden när korttidsleasingens journalpost för omklassificering bokförs.</span><span class="sxs-lookup"><span data-stu-id="38048-126">The account is associated with the short-term lease liability when the short-term lease liability reclass journal entry is posted.</span></span> <span data-ttu-id="38048-127">Det här kontot krediteras för kortfristiga skulder från amorteringsplanen på den sista dagen i månaden.</span><span class="sxs-lookup"><span data-stu-id="38048-127">This account is credited for the short-term liability from the amortization schedule on the last day of the month.</span></span> <span data-ttu-id="38048-128">Samma belopp debiteras på den första dagen i nästa månad.</span><span class="sxs-lookup"><span data-stu-id="38048-128">However, the same amount is debited on the first day of the next month.</span></span>

<span data-ttu-id="38048-129">**Exempel på journalposter:** Omklassificering av kortfristig leasingskuld</span><span class="sxs-lookup"><span data-stu-id="38048-129">**Example journal entries:** Short-term lease liability reclass</span></span><br>
<span data-ttu-id="38048-130">**Debet:** Leasingskuld XXX</span><span class="sxs-lookup"><span data-stu-id="38048-130">**Debit:** Lease liability XXX</span></span><br>
<span data-ttu-id="38048-131">**Kredit:** Kortfristig leasingskuld XXX</span><span class="sxs-lookup"><span data-stu-id="38048-131">**Credit:** Short-term lease liability XXX</span></span><br>
<span data-ttu-id="38048-132">**Debet:** Kortfristig leasingskuld XXX</span><span class="sxs-lookup"><span data-stu-id="38048-132">**Debit:** Short-term lease liability XXX</span></span><br>
<span data-ttu-id="38048-133">**Kredit:** Leasingskuld XXX</span><span class="sxs-lookup"><span data-stu-id="38048-133">**Credit:** Lease liability XXX</span></span>

## <a name="depreciation-expense"></a><span data-ttu-id="38048-134">Avskrivningsutgift</span><span class="sxs-lookup"><span data-stu-id="38048-134">Depreciation expense</span></span>

<span data-ttu-id="38048-135">Kontot är kopplat till den kostnad som är relaterad till avskrivningen av ROU-tillgången enligt IFRS 16, ASC 842 och finansiella leasingavtal enligt IAS 17 och ASC 840.</span><span class="sxs-lookup"><span data-stu-id="38048-135">The account is associated with the expense that is related to the depreciation of the ROU asset under IFRS 16, ASC 842, and finance leases under IAS 17 and ASC 840.</span></span> <span data-ttu-id="38048-136">Det här kontot debiteras när en ROU-tillgång skrivs av varje månad.</span><span class="sxs-lookup"><span data-stu-id="38048-136">This account is debited when an ROU asset is depreciated each month.</span></span>

<span data-ttu-id="38048-137">**Exempel på journalposter:** Upplupen avskrivning</span><span class="sxs-lookup"><span data-stu-id="38048-137">**Example journal entries:** Depreciation accrual</span></span><br>
<span data-ttu-id="38048-138">**Debet:** Avskrivningskostnad XXX</span><span class="sxs-lookup"><span data-stu-id="38048-138">**Debit:** Depreciation expense XXX</span></span><br>
<span data-ttu-id="38048-139">**Kredit:** Ackumulerad avskrivning XXX</span><span class="sxs-lookup"><span data-stu-id="38048-139">**Credit:** Accumulated Depreciation XXX</span></span>

## <a name="gainloss-on-lease-modification"></a><span data-ttu-id="38048-140">Vinst/förlust vid leasingändring</span><span class="sxs-lookup"><span data-stu-id="38048-140">Gain/loss on lease modification</span></span>

<span data-ttu-id="38048-141">Kontot är kopplat till vinster eller förluster som uppstår vid ändringar av leasingavtalet.</span><span class="sxs-lookup"><span data-stu-id="38048-141">The account is associated with any gains or losses that arise from lease modifications.</span></span> <span data-ttu-id="38048-142">En vinst kan uppstå under en leasingändring om ändringen minskar leasingskulden med ett belopp som överstiger det bokförda värdet för ROU-tillgången.</span><span class="sxs-lookup"><span data-stu-id="38048-142">A gain might arise during a lease modification if the modification decreases the lease liability by an amount that exceeds the carrying value of the ROU asset.</span></span>

<span data-ttu-id="38048-143">Ett leasingavtal har till exempel ett aktuellt bokfört värde för låneskulden på 150 000 USD och ett bokfört värde på ROU-tillgången på 100 000 USD.</span><span class="sxs-lookup"><span data-stu-id="38048-143">For example, a lease has a current carrying value of the lease liability of $150,000 and a carrying value of the ROU asset of $100,000.</span></span> <span data-ttu-id="38048-144">Leasingavtalet ändras och denna ändring ger ett nytt nuvärde för de framtida lägsta leasingbetalningarna (PVFMLP) på 40 000 USD.</span><span class="sxs-lookup"><span data-stu-id="38048-144">The lease is modified, and this modification produces a new present value of the future minimum lease payments (PVFMLP) of $40,000.</span></span> <span data-ttu-id="38048-145">Därför debiteras leasingskulden med 110 000 USD (150 000 USD – 40 000 USD).</span><span class="sxs-lookup"><span data-stu-id="38048-145">Therefore, the lease liability will be debited by $110,000 ($150,000 – $40,000).</span></span> <span data-ttu-id="38048-146">Eftersom ROU-tillgången bara är 100 000 USD gör minskningen på 110 000 USD att tillgången minskar under 0 (noll).</span><span class="sxs-lookup"><span data-stu-id="38048-146">Because the ROU asset is only $100,000, the decrease of $110,000 will decrease the asset past 0 (zero).</span></span> <span data-ttu-id="38048-147">Därför anger redovisningsvägledningen att resten ska bokföras på ett vinstkonto.</span><span class="sxs-lookup"><span data-stu-id="38048-147">Therefore, the accounting guidance states that the remainder should be booked to a gain account.</span></span> <span data-ttu-id="38048-148">I det här fallet är den slutliga journalposten en debitering till leasingskulden på 110 000 USD, en kredit till leasingtillgången på 100 000 USD och en kredit till vinstkontot på 10 000 USD.</span><span class="sxs-lookup"><span data-stu-id="38048-148">In this case, the final journal entry will be a debit to the lease liability for $110,000, a credit to the lease asset for $100,000, and a credit to the gain account for $10,000.</span></span>

<span data-ttu-id="38048-149">**Exempel på journalposter:** Leasingändring</span><span class="sxs-lookup"><span data-stu-id="38048-149">**Example journal entries:** Lease modification</span></span><br>
<span data-ttu-id="38048-150">**Debet:** Leasingskuld XXX</span><span class="sxs-lookup"><span data-stu-id="38048-150">**Debit:** Lease liability XXX</span></span><br>
<span data-ttu-id="38048-151">**Kredit:** Leasingtillgång XXX</span><span class="sxs-lookup"><span data-stu-id="38048-151">**Credit:** Lease Asset XXX</span></span><br>
<span data-ttu-id="38048-152">**Kredit:** Vinst XXX</span><span class="sxs-lookup"><span data-stu-id="38048-152">**Credit:** Gain XXX</span></span>

## <a name="accumulated-depreciation"></a><span data-ttu-id="38048-153">Ackumulerad avskrivning</span><span class="sxs-lookup"><span data-stu-id="38048-153">Accumulated depreciation</span></span>

<span data-ttu-id="38048-154">Kontot är kopplat till motkontot för ROU-tillgången.</span><span class="sxs-lookup"><span data-stu-id="38048-154">The account is associated with the contra-asset account of the ROU asset.</span></span> <span data-ttu-id="38048-155">Det här kontot krediteras när en avskrivningskostnad bokförs.</span><span class="sxs-lookup"><span data-stu-id="38048-155">This account is credited when a depreciation expense is posted.</span></span>

<span data-ttu-id="38048-156">**Exempel på journalposter:** Upplupen avskrivning</span><span class="sxs-lookup"><span data-stu-id="38048-156">**Example journal entries:** Depreciation accrual</span></span><br>
<span data-ttu-id="38048-157">**Debet:** Avskrivningskostnad XXX</span><span class="sxs-lookup"><span data-stu-id="38048-157">**Debit:** Depreciation expense XXX</span></span><br>
<span data-ttu-id="38048-158">**Kredit:** Ackumulerad avskrivning XXX</span><span class="sxs-lookup"><span data-stu-id="38048-158">**Credit:** Accumulated depreciation XXX</span></span>

## <a name="retained-earnings"></a><span data-ttu-id="38048-159">Balanserade vinstmedel</span><span class="sxs-lookup"><span data-stu-id="38048-159">Retained earnings</span></span>

<span data-ttu-id="38048-160">Kontot är kopplat till balanserade vinstmedel.</span><span class="sxs-lookup"><span data-stu-id="38048-160">The account is associated with retained earnings.</span></span> <span data-ttu-id="38048-161">Detta konto kan antingen debiteras eller krediteras i en journalpost för en övergångsjustering genom att använda den fullständiga retrospektiva metoden eller den kumulativa "catch-up A"-metoden.</span><span class="sxs-lookup"><span data-stu-id="38048-161">This account might be either debited or credited in a transition adjustment journal entry by using the full retrospective method or the cumulative catch-up option A method.</span></span> <span data-ttu-id="38048-162">Skillnaden mellan den ursprungliga ROU-tillgången och leasingskulden bokförs på balanserade vinstmedel.</span><span class="sxs-lookup"><span data-stu-id="38048-162">The difference between the initial ROU asset and lease liability is booked to retained earnings.</span></span> <span data-ttu-id="38048-163">I sällsynta fall kan de balanserade vinstmedlen också påverkas när leasingavtalet ändras, om klassificeringen av ett leasingavtal ändras från finansiellt till operationellt för att skriva upp eller ner ROU-tillgången så att den motsvarar leasingskulden.</span><span class="sxs-lookup"><span data-stu-id="38048-163">In rare cases, the retained earnings might also be affected during lease modification, if the classification of a lease is changed from finance to operating to write the ROU asset up or down so that it equals the lease liability.</span></span>

<span data-ttu-id="38048-164">**Exempel på journalposter:** Övergångsjustering (metoden fullständigt retroaktivt eller kumulativt "catch-up option A")</span><span class="sxs-lookup"><span data-stu-id="38048-164">**Example journal entries:** Transition adjustment (full retrospective or cumulative catch-up option A method)</span></span><br>
<span data-ttu-id="38048-165">**Debet:** Leasingskuld XXX</span><span class="sxs-lookup"><span data-stu-id="38048-165">**Debit:** Lease liability XXX</span></span><br>
<span data-ttu-id="38048-166">**Kredit:** Leasingtillgång XXX</span><span class="sxs-lookup"><span data-stu-id="38048-166">**Credit:** Lease asset XXX</span></span><br>
<span data-ttu-id="38048-167">**Kredit:** Balanserade vinstmedel XXX</span><span class="sxs-lookup"><span data-stu-id="38048-167">**Credit:** Retained earnings XXX</span></span>

## <a name="variable-payment"></a><span data-ttu-id="38048-168">Variabel betalning</span><span class="sxs-lookup"><span data-stu-id="38048-168">Variable payment</span></span>

<span data-ttu-id="38048-169">Kontot är kopplat till variabla leasingbetalningar som skapas genom en indexerad omvärdering enligt ASC 842, ASC 840 och IAS 17-leasingar.</span><span class="sxs-lookup"><span data-stu-id="38048-169">The account is associated with variable lease payments that are produced by an index revaluation under ASC 842, ASC 840, and IAS 17 leases.</span></span> <span data-ttu-id="38048-170">I betalningsplanen för leasing inkluderas variabla betalningar i kolumnen **Variabel betalning**.</span><span class="sxs-lookup"><span data-stu-id="38048-170">In the lease payment schedule, variable payments are included in the **Variable payment** column.</span></span> <span data-ttu-id="38048-171">Det här kontot debiteras när en faktura skapas mot en betalningsplanrad som innehåller en variabel betalning.</span><span class="sxs-lookup"><span data-stu-id="38048-171">This account is debited when an invoice is created against a payment schedule line that contains a variable payment.</span></span>

<span data-ttu-id="38048-172">**Exempel på journalposter:** Leasingbetalning</span><span class="sxs-lookup"><span data-stu-id="38048-172">**Example journal entries:** Lease payment</span></span><br>
<span data-ttu-id="38048-173">**Debet:** Leasingskuld XXX</span><span class="sxs-lookup"><span data-stu-id="38048-173">**Debit:** Lease liability XXX</span></span><br>
<span data-ttu-id="38048-174">**Debet:** Variabel betalning XXX</span><span class="sxs-lookup"><span data-stu-id="38048-174">**Debit:** Variable payment XXX</span></span><br>
<span data-ttu-id="38048-175">**Kredit:** Leverantörsskuld/leasingbetalning XXX</span><span class="sxs-lookup"><span data-stu-id="38048-175">**Credit:** Vendor payable/lease payment XXX</span></span>

## <a name="deferred-rent-asset-liability"></a><span data-ttu-id="38048-176">Uppskov av leasingavgift (skuld)</span><span class="sxs-lookup"><span data-stu-id="38048-176">Deferred rent asset (liability)</span></span>

<span data-ttu-id="38048-177">Kontot är kopplat till den uppskjutna leasingavgiften eller skulden som produceras av ett leasingavtal med uppskov av leasingavgift.</span><span class="sxs-lookup"><span data-stu-id="38048-177">The account is associated with the deferred rent asset or liability that is produced by a deferred rent treatment lease.</span></span> <span data-ttu-id="38048-178">Det här kontot debiteras när en faktura bokförs mot ett leasingavtal med uppskov av leasingavgift, om leasingbetalningsbeloppet är mer än periodens linjära hyreskostnad.</span><span class="sxs-lookup"><span data-stu-id="38048-178">This account is debited when an invoice is posted against a deferred rent treatment lease, if the lease payment amount is more than the period's straight-line rent expense.</span></span> <span data-ttu-id="38048-179">Det krediteras om leasingbetalningen är mindre än periodens linjära hyreskostnad.</span><span class="sxs-lookup"><span data-stu-id="38048-179">It's credited if the lease payment is less than the period's straight-line rent expense.</span></span>

<span data-ttu-id="38048-180">**Exempel på journalposter:** Leasingbetalning (leasing med uppskov av leasingavgift)</span><span class="sxs-lookup"><span data-stu-id="38048-180">**Example journal entries:** Lease payment (deferred rent treatment lease)</span></span><br>
<span data-ttu-id="38048-181">**Debet:** Leasingkostnad XXX</span><span class="sxs-lookup"><span data-stu-id="38048-181">**Debit:** Lease expense XXX</span></span><br>
<span data-ttu-id="38048-182">**Kredit:** Uppskov av leasingavgift (skuld) XXX</span><span class="sxs-lookup"><span data-stu-id="38048-182">**Credit:** Deferred rent liability XXX</span></span><br>
<span data-ttu-id="38048-183">**Kredit:** Leverantörsskuld/leasingbetalning XXX</span><span class="sxs-lookup"><span data-stu-id="38048-183">**Credit:** Vendor payable/lease payment XXX</span></span>

## <a name="lease-expense"></a><span data-ttu-id="38048-184">Leasingkostnad</span><span class="sxs-lookup"><span data-stu-id="38048-184">Lease expense</span></span>

<span data-ttu-id="38048-185">Kontot är kopplat till leasingkostnaden om leasingavtalet klassificeras som ett leasingavtal med uppskov av leasingavgift.</span><span class="sxs-lookup"><span data-stu-id="38048-185">The account is associated with the lease expense if the lease is classified as a deferred rent treatment lease.</span></span> <span data-ttu-id="38048-186">Det här kontot debiteras när en faktura bokförs mot en leasingavtal med uppskov av leasingavgift.</span><span class="sxs-lookup"><span data-stu-id="38048-186">This account is debited when an invoice is posted against a deferred rent treatment lease.</span></span>

<span data-ttu-id="38048-187">**Exempel på journalposter:** Leasingbetalning (leasing med uppskov av leasingavgift)</span><span class="sxs-lookup"><span data-stu-id="38048-187">**Example journal entries:** Lease payment (deferred rent treatment lease)</span></span><br>
<span data-ttu-id="38048-188">**Debet:** Leasingkostnad XXX</span><span class="sxs-lookup"><span data-stu-id="38048-188">**Debit:** Lease expense XXX</span></span><br>
<span data-ttu-id="38048-189">**Kredit:** Uppskov av leasingavgift (skuld) XXX</span><span class="sxs-lookup"><span data-stu-id="38048-189">**Credit:** Deferred rent liability XXX</span></span><br>
<span data-ttu-id="38048-190">**Kredit:** Leverantörsskuld/leasingbetalning XXX</span><span class="sxs-lookup"><span data-stu-id="38048-190">**Credit:** Vendor payable/lease payment XXX</span></span>

## <a name="impairment-expense"></a><span data-ttu-id="38048-191">Nedskrivningsutgift</span><span class="sxs-lookup"><span data-stu-id="38048-191">Impairment expense</span></span>

<span data-ttu-id="38048-192">Kontot motbokas när en leasing skrivs ner.</span><span class="sxs-lookup"><span data-stu-id="38048-192">The account is posted against when a lease is impaired.</span></span> <span data-ttu-id="38048-193">Det här kontot debiteras men ROU-tillgångskontot krediteras direkt.</span><span class="sxs-lookup"><span data-stu-id="38048-193">This account is debited, whereas the ROU asset account is directly credited.</span></span>

<span data-ttu-id="38048-194">**Exempel på journalposter:** Leasingbetalning</span><span class="sxs-lookup"><span data-stu-id="38048-194">**Example journal entries:** Lease payment</span></span><br>
<span data-ttu-id="38048-195">**Debet:** Nedskrivningsutgift XXX</span><span class="sxs-lookup"><span data-stu-id="38048-195">**Debit:** Impairment expense XXX</span></span><br>
<span data-ttu-id="38048-196">**Kredit:** ROU-tillgång XXX</span><span class="sxs-lookup"><span data-stu-id="38048-196">**Credit:** ROU asset XXX</span></span>

## <a name="lease-payment"></a><span data-ttu-id="38048-197">Leasingbetalning</span><span class="sxs-lookup"><span data-stu-id="38048-197">Lease payment</span></span>

<span data-ttu-id="38048-198">Kontot motbokas om parametern **Betala till leverantör** är inaktiverad.</span><span class="sxs-lookup"><span data-stu-id="38048-198">The account is posted against if the **Pay to Vendor** parameter is turned off.</span></span> <span data-ttu-id="38048-199">Det här kontot krediteras i stället för leverantörsskulden om parametern är inaktiverad.</span><span class="sxs-lookup"><span data-stu-id="38048-199">This account is credited instead of the vendor payable if the parameter is turned off.</span></span>

<span data-ttu-id="38048-200">**Exempel på journalposter:** Leasingbetalning</span><span class="sxs-lookup"><span data-stu-id="38048-200">**Example journal entries:** Lease payment</span></span><br>
<span data-ttu-id="38048-201">**Debet:** Leasingskuld XXX</span><span class="sxs-lookup"><span data-stu-id="38048-201">**Debit:** Lease liability XXX</span></span><br>
<span data-ttu-id="38048-202">**Kredit:** Leasingbetalning XXX</span><span class="sxs-lookup"><span data-stu-id="38048-202">**Credit:** Lease payment XXX</span></span>

## <a name="expense-type-postings"></a><span data-ttu-id="38048-203">Bokföring av utgiftstyp</span><span class="sxs-lookup"><span data-stu-id="38048-203">Expense type postings</span></span>

<span data-ttu-id="38048-204">Det konto som väljs för varje utgiftstyp debiteras när en betalning för den utgiftstypen genereras.</span><span class="sxs-lookup"><span data-stu-id="38048-204">The account that is selected for each expense type is debited when a payment for that expense type is generated.</span></span> <span data-ttu-id="38048-205">Kontot som anges för utgiftstypen **Försäkring** debiteras till exempel när en faktura eller en betalningsjournalpost skapas från verkställighetskostnaden för försäkringsutgift.</span><span class="sxs-lookup"><span data-stu-id="38048-205">For example, the account that is specified for the **Insurance** expense type is debited whenever an invoice or payment journal entry is created from the executory cost schedule for insurance expense.</span></span>

<span data-ttu-id="38048-206">**Exempel på journalposter:** Försäkringsbetalning</span><span class="sxs-lookup"><span data-stu-id="38048-206">**Example journal entries:** Insurance payment</span></span><br>
<span data-ttu-id="38048-207">**Debet:** Konto XXX av försäkringsutgiftstyp</span><span class="sxs-lookup"><span data-stu-id="38048-207">**Debit:** Insurance expense type account XXX</span></span><br>
<span data-ttu-id="38048-208">**Kredit:** Motkonto XXX</span><span class="sxs-lookup"><span data-stu-id="38048-208">**Credit:** Offset account XXX</span></span>

> [!NOTE]
> <span data-ttu-id="38048-209">Motkontot väljs på leasingnivå på raderna för betalningsplanen för verkställighetskostnad.</span><span class="sxs-lookup"><span data-stu-id="38048-209">The offset account is selected at the lease level on the lines for the executory cost payment schedule.</span></span> <span data-ttu-id="38048-210">Det här motkontot kan kopplas till leverantören eller till ett huvudbokskonto.</span><span class="sxs-lookup"><span data-stu-id="38048-210">This offset account can associated with the vendor, or with a ledger account.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]