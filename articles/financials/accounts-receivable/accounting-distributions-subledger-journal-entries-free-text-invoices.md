---
title: "Redovisningsfördelningar och redovisningsjournalposter för fritextfakturor"
description: "Redovisningsfördelningar används för att definiera hur ett belopp ska redovisas. Exempelvis hur intäkten, momsen eller avgifterna ska redovisas på en fritextfaktura. Varje belopp som måste redovisas när leverantörsfakturan journalförs ska ha en eller flera redovisningsfördelningar."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustFreeInvoice
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 3141
ms.assetid: fecd17a2-d7b4-4a20-ac81-eb71abbfa9d1
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: ac321e34086e1861b3d8c539fb3ac5f360679d79
ms.contentlocale: sv-se
ms.lasthandoff: 04/13/2018

---

# <a name="accounting-distributions-and-subledger-journal-entries-for-free-text-invoices"></a><span data-ttu-id="029f0-104">Redovisningsfördelningar och redovisningsjournalposter för fritextfakturor</span><span class="sxs-lookup"><span data-stu-id="029f0-104">Accounting distributions and subledger journal entries for free text invoices</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="029f0-105">Redovisningsfördelningar används för att definiera hur ett belopp ska redovisas. Exempelvis hur intäkten, momsen eller avgifterna ska redovisas på en fritextfaktura.</span><span class="sxs-lookup"><span data-stu-id="029f0-105">Accounting distributions are used to define how an amount will be accounted for, such as how the revenue, tax, or charges will be accounted for on a free text invoice.</span></span> <span data-ttu-id="029f0-106">Varje belopp som måste redovisas när leverantörsfakturan journalförs ska ha en eller flera redovisningsfördelningar.</span><span class="sxs-lookup"><span data-stu-id="029f0-106">Every amount that must be accounted for when the free text invoice is journalized will have one or more accounting distributions.</span></span>

<a name="accounting-distributions"></a><span data-ttu-id="029f0-107">Redovisningsfördelningar</span><span class="sxs-lookup"><span data-stu-id="029f0-107">Accounting distributions</span></span>
------------------------

<span data-ttu-id="029f0-108">Du kan använda följande knappar på sidan Fritextfaktura om du vill visa, och möjligen ändra, redovisningsfördelningarna för varje belopp på fritextfakturan.</span><span class="sxs-lookup"><span data-stu-id="029f0-108">You can use the following buttons in the Free text invoice page to view, and possibly change, the accounting distributions for each amount on the free text invoice.</span></span>

-   <span data-ttu-id="029f0-109">**Fördela belopp**—Visa och ändra redovisningsfördelningarna för en enskild rad och eventuella underordnade rader, till exempel moms eller avgifter.</span><span class="sxs-lookup"><span data-stu-id="029f0-109">**Distribute amounts**—View and change the accounting distributions for an individual line and any child lines, such as taxes or charges.</span></span> <span data-ttu-id="029f0-110">Du kan också visa och ändra redovisningsfördelningarna för den underordnade raden direkt från sidan Momstransaktioner eller sidan Transaktioner för avgifter.</span><span class="sxs-lookup"><span data-stu-id="029f0-110">You can also view and change the accounting distributions for the child line directly from the Sales tax transactions page or the Charges transactions page.</span></span>
    -   <span data-ttu-id="029f0-111">Ändra huvudbeloppen på fritextfakturan, till exempel avgifter eller valutaavrundningsbelopp.</span><span class="sxs-lookup"><span data-stu-id="029f0-111">Change free text invoice header amounts, such as charges or currency rounding amounts.</span></span>
    -   <span data-ttu-id="029f0-112">Ändra radbeloppen för en fritextfaktura</span><span class="sxs-lookup"><span data-stu-id="029f0-112">Change free text invoice line amounts.</span></span>
-   <span data-ttu-id="029f0-113">**Visa fördelningar** – Visa redovisningsfördelningarna för alla rader i dokumentet.</span><span class="sxs-lookup"><span data-stu-id="029f0-113">**View distributions**—View the accounting distributions for all lines on the document.</span></span> <span data-ttu-id="029f0-114">Du kan inte ändra redovisningsfördelningarna från den här vyn.</span><span class="sxs-lookup"><span data-stu-id="029f0-114">You can't change the accounting distributions from this view.</span></span>
    -   <span data-ttu-id="029f0-115">Visa huvud- och radbelopp.</span><span class="sxs-lookup"><span data-stu-id="029f0-115">View header and line amounts.</span></span>

## <a name="distributing-amounts"></a><span data-ttu-id="029f0-116">Fördela belopp</span><span class="sxs-lookup"><span data-stu-id="029f0-116">Distributing amounts</span></span>
<span data-ttu-id="029f0-117">När du anger en fritextfaktura kommer varje belopp fördelas på följande sätt.</span><span class="sxs-lookup"><span data-stu-id="029f0-117">When you enter a free text invoice, each amount will be distributed as follows.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="029f0-118">Typ av penningbelopp</span><span class="sxs-lookup"><span data-stu-id="029f0-118">Type of monetary amount</span></span></th>
<th><span data-ttu-id="029f0-119">Var huvudkontot visas från</span><span class="sxs-lookup"><span data-stu-id="029f0-119">Where the main account is displayed from</span></span></th>
<th><span data-ttu-id="029f0-120">Prioritetsordning som bestämmer vilken ekonomisk standarddimension som visas</span><span class="sxs-lookup"><span data-stu-id="029f0-120">Order of priority that determines which default financial dimension is displayed</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="029f0-121">Fritextfakturarad</span><span class="sxs-lookup"><span data-stu-id="029f0-121">Free text invoice line</span></span></td>
<td><span data-ttu-id="029f0-122">Redovisningskontot på fritextfakturaraden.</span><span class="sxs-lookup"><span data-stu-id="029f0-122">The ledger account on the free text invoice line.</span></span></td>
<td><ol>
<li><span data-ttu-id="029f0-123">Om huvudkontot är ett allokeringskonto ska du använda standardvärdet från allokeringskontodefinitionen.</span><span class="sxs-lookup"><span data-stu-id="029f0-123">If the main account is an allocation account, use the default value from the allocation account definition.</span></span></li>
<li><span data-ttu-id="029f0-124">Om huvudkontot inte är ett allokeringskonto ska du använda standardmallen för ekonomiska dimensioner på fritextfakturaraden.</span><span class="sxs-lookup"><span data-stu-id="029f0-124">If the main account is not an allocation account, use the financial dimension default template on the free text invoice line.</span></span></li>
<li><span data-ttu-id="029f0-125">Använd de förvalda värdena för ekonomiska dimensioner på fritextfakturaraden.</span><span class="sxs-lookup"><span data-stu-id="029f0-125">Use the default financial dimension values on the free text invoice line.</span></span></li>
<li><span data-ttu-id="029f0-126">Använd de förvalda värdena för ekonomiska dimensioner från redovisningskontot på sidan Kontoplan.</span><span class="sxs-lookup"><span data-stu-id="029f0-126">Use the default financial dimension values from the ledger account in the Chart of accounts page.</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="029f0-127">Fritextfakturarad för en kombination av Anläggningstillgångsnummer och värdemodell</span><span class="sxs-lookup"><span data-stu-id="029f0-127">Free text invoice line for a fixed asset number and value model combination</span></span>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><span data-ttu-id="029f0-128"><strong>Obs! </strong></span><span class="sxs-lookup"><span data-stu-id="029f0-128"><strong>Note</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="029f0-129">Huvudkontot på fritextfakturaraden kommer att vara kontot för avyttring av anläggningstillgångar.</span><span class="sxs-lookup"><span data-stu-id="029f0-129">The main account on the free text invoice line will be the fixed asset disposal account.</span></span></td>
</tr>
</tbody>
</table>
</div></td>
<td><span data-ttu-id="029f0-130">Redovisningskontot på fritextfakturaraden.</span><span class="sxs-lookup"><span data-stu-id="029f0-130">The ledger account on the free text invoice line.</span></span></td>
<td><ol>
<li><span data-ttu-id="029f0-131">Använd de förvalda värdena för ekonomiska dimensioner på fritextfakturaraden.</span><span class="sxs-lookup"><span data-stu-id="029f0-131">Use the default financial dimension values on the free text invoice line.</span></span></li>
<li><span data-ttu-id="029f0-132">Använd de förvalda värdena för ekonomiska dimensioner från redovisningskontot på sidan Kontoplan.</span><span class="sxs-lookup"><span data-stu-id="029f0-132">Use the default financial dimension values from the ledger account in the Chart of accounts page.</span></span></li>
</ol></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="029f0-133">Radrabatt på fritextfaktura</span><span class="sxs-lookup"><span data-stu-id="029f0-133">Free text invoice discount amount</span></span></td>
<td><span data-ttu-id="029f0-134">Fältet Huvudkonto för kundrabatter på sidan Kassarabatter.</span><span class="sxs-lookup"><span data-stu-id="029f0-134">The Main account for customer discounts field in the Cash discounts page.</span></span></td>
<td><ol>
<li><span data-ttu-id="029f0-135">Om huvudkontot är ett allokeringskonto ska du använda standardvärdet från allokeringskontodefinitionen.</span><span class="sxs-lookup"><span data-stu-id="029f0-135">If the main account is an allocation account, use the default value from the allocation account definition.</span></span></li>
<li><span data-ttu-id="029f0-136">Om huvudkontot inte är ett allokeringskonto ska du använda standardmallen för ekonomiska dimensioner på fritextfakturaraden.</span><span class="sxs-lookup"><span data-stu-id="029f0-136">If the main account is not an allocation account, use the financial dimension default template on the free text invoice line.</span></span></li>
<li><span data-ttu-id="029f0-137">Använd de förvalda värdena för ekonomiska dimensioner på fritextfakturaraden.</span><span class="sxs-lookup"><span data-stu-id="029f0-137">Use the default financial dimension values on the free text invoice line.</span></span></li>
<li><span data-ttu-id="029f0-138">Använd de förvalda värdena för ekonomiska dimensioner från redovisningskontot på sidan Kontoplan.</span><span class="sxs-lookup"><span data-stu-id="029f0-138">Use the default financial dimension values from the ledger account in the Chart of accounts page.</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="029f0-139">Momsbelopp på fritextfaktura</span><span class="sxs-lookup"><span data-stu-id="029f0-139">Free text invoice sales tax amount</span></span></td>
<td><span data-ttu-id="029f0-140">Fältet Momsskuld på sidan Redovisningsbokföringsgrupper.</span><span class="sxs-lookup"><span data-stu-id="029f0-140">The Sales tax payable field in the Ledger posting groups page.</span></span></td>
<td><ol>
<li><span data-ttu-id="029f0-141">Använd ekonomiska dimensioner som definieras på fritextfakturaradbeloppet eller fördelningarna för avgiftsradbeloppet.</span><span class="sxs-lookup"><span data-stu-id="029f0-141">Use the financial dimensions that are defined on the free text invoice line amount or the distributions for the charge line amount.</span></span></li>
<li><span data-ttu-id="029f0-142">Använd de förvalda värdena för ekonomiska dimensioner på fritextfakturaraden.</span><span class="sxs-lookup"><span data-stu-id="029f0-142">Use the default financial dimension values on the free text invoice line.</span></span></li>
<li><span data-ttu-id="029f0-143">Använd de förvalda värdena för ekonomiska dimensioner från redovisningskontot på sidan Kontoplan.</span><span class="sxs-lookup"><span data-stu-id="029f0-143">Use the default financial dimension values from the ledger account in the Chart of accounts page.</span></span></li>
</ol></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="029f0-144">Avgiftsradbelopp på fritextfaktura</span><span class="sxs-lookup"><span data-stu-id="029f0-144">Free text invoice charge line amount</span></span></td>
<td><span data-ttu-id="029f0-145">Fältet Kreditkonto på sidan Kod för avgifter.</span><span class="sxs-lookup"><span data-stu-id="029f0-145">The Credit account field in the Charges code page.</span></span></td>
<td><ol>
<li><span data-ttu-id="029f0-146">Om huvudkontot är ett allokeringskonto ska du använda standardvärdet från allokeringskontodefinitionen.</span><span class="sxs-lookup"><span data-stu-id="029f0-146">If the main account is an allocation account, use the default value from the allocation account definition.</span></span></li>
<li><span data-ttu-id="029f0-147">Om huvudkontot inte är ett allokeringskonto ska du använda standardmallen för ekonomiska dimensioner på fritextfakturaraden.</span><span class="sxs-lookup"><span data-stu-id="029f0-147">If the main account is not an allocation account, use the financial dimension default template on the free text invoice line.</span></span></li>
<li><span data-ttu-id="029f0-148">Använd de förvalda värdena för ekonomiska dimensioner på fritextfakturaraden.</span><span class="sxs-lookup"><span data-stu-id="029f0-148">Use the default financial dimension values on the free text invoice line.</span></span></li>
<li><span data-ttu-id="029f0-149">Använd de förvalda värdena för ekonomiska dimensioner från redovisningskontot på sidan Kontoplan.</span><span class="sxs-lookup"><span data-stu-id="029f0-149">Use the default financial dimension values from the ledger account in the Chart of accounts page.</span></span></li>
</ol></td>
</tr>
</tbody>
</table>

## <a name="distributing-taxes"></a><span data-ttu-id="029f0-150">Fördela moms</span><span class="sxs-lookup"><span data-stu-id="029f0-150">Distributing taxes</span></span>
<span data-ttu-id="029f0-151">Redovisningsfördelning för skatter går inte att skapa förrän skatter har beräknats.</span><span class="sxs-lookup"><span data-stu-id="029f0-151">Accounting distributions for taxes cannot be created until taxes are calculated.</span></span> <span data-ttu-id="029f0-152">Om du vill beräkna moms måste du färdigställa en av följande uppgifter i formuläret Fritextfaktura:</span><span class="sxs-lookup"><span data-stu-id="029f0-152">To calculate sales taxes, you must complete one of the following tasks in the Free text invoice form:</span></span>
-   <span data-ttu-id="029f0-153">Visa momsen.</span><span class="sxs-lookup"><span data-stu-id="029f0-153">View the sales tax.</span></span>
-   <span data-ttu-id="029f0-154">Visa fakturasumman.</span><span class="sxs-lookup"><span data-stu-id="029f0-154">View the invoice total.</span></span>
-   <span data-ttu-id="029f0-155">Visa kassaflödet.</span><span class="sxs-lookup"><span data-stu-id="029f0-155">View the cash flow.</span></span>
-   <span data-ttu-id="029f0-156">Visa redovisningsfördelningar för hela fritextfakturan.</span><span class="sxs-lookup"><span data-stu-id="029f0-156">View accounting distributions for the whole free text invoice.</span></span>
-   <span data-ttu-id="029f0-157">Visa redovisningsjournalen.</span><span class="sxs-lookup"><span data-stu-id="029f0-157">View the subledger journal.</span></span>

## <a name="subledger-journals-for-free-text-invoices"></a><span data-ttu-id="029f0-158"> Redovisningsjournaler för fritextfakturor</span><span class="sxs-lookup"><span data-stu-id="029f0-158">Subledger journals for free text invoices</span></span>
<span data-ttu-id="029f0-159">Innan du bokför en fritextfaktura kan du visa hela redovisningsposten för fakturan, som inkluderar debiteringar och krediteringar, för att kontrollera att fakturan bokförs till rätt konton.</span><span class="sxs-lookup"><span data-stu-id="029f0-159">Before you post a free text invoice, you can view the full accounting entry of the invoice, which includes debits and credits, to verify that the invoice is being posted to the correct accounts.</span></span> <span data-ttu-id="029f0-160">Denna vy av hela redovisningsposten kallas en redovisningsjournal.</span><span class="sxs-lookup"><span data-stu-id="029f0-160">This view of the full accounting entry is called a subledger journal.</span></span> <span data-ttu-id="029f0-161">Om posten i reskontrajournalen är fel när du granskar den innan du journalför fritextfakturan kan du inte ändra posten i reskontrajournalen.</span><span class="sxs-lookup"><span data-stu-id="029f0-161">If the subledger journal entry is incorrect when you preview it before you journalize the free text invoice, you can't change the subledger journal entry.</span></span> <span data-ttu-id="029f0-162">I stället måste du ändra redovisningsfördelningarna eller bokföringsprofilen.</span><span class="sxs-lookup"><span data-stu-id="029f0-162">Instead, you must change the accounting distributions or the posting profile.</span></span> <span data-ttu-id="029f0-163">Redovisningsfördelningarna används för att definiera ena sidan i redovisningposten, debet eller kredit.</span><span class="sxs-lookup"><span data-stu-id="029f0-163">The accounting distributions are used to define one side of the accounting entry, the debit or the credit.</span></span> <span data-ttu-id="029f0-164">Den förskjutande kontoposten i reskontrajournalen skapas från bokföringsprofilerna, till exempel från kundkontot eller moms.</span><span class="sxs-lookup"><span data-stu-id="029f0-164">The offsetting subledger journal account entry is created from the posting profiles, such as from the customer account or the tax.</span></span>




