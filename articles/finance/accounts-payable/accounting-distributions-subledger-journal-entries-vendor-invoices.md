---
title: Redovisningsfördelningar och redovisningsjournalposter för leverantörsfakturor
description: Redovisningsfördelningar används för att definiera hur ett belopp ska redovisas, till exempel hur utgiften, momsen eller avgifterna ska redovisas på en leverantörsfaktura. Varje belopp som måste redovisas när leverantörsfakturan journalförs ska ha en eller flera redovisningsfördelningar.
author: abruer
manager: AnnBe
ms.date: 08/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendEditInvoice
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 26891
ms.assetid: 93dc608a-b5b4-4ec3-83c2-618e3d80a583
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f8e38e6a571bb7f08b32548bcb4af823807a4340
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4448152"
---
# <a name="accounting-distributions-and-subledger-journal-entries-for-vendor-invoices"></a><span data-ttu-id="a38dc-104">Redovisningsfördelningar och redovisningsjournalposter för leverantörsfakturor</span><span class="sxs-lookup"><span data-stu-id="a38dc-104">Accounting distributions and subledger journal entries for vendor invoices</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a38dc-105">Redovisningsfördelningar används för att definiera hur ett belopp ska redovisas, till exempel hur utgiften, momsen eller avgifterna ska redovisas på en leverantörsfaktura.</span><span class="sxs-lookup"><span data-stu-id="a38dc-105">Accounting distributions are used to define how an amount will be accounted for, such as how the expense, tax, or charges will be accounted for on a vendor invoice.</span></span> <span data-ttu-id="a38dc-106">Varje belopp som måste redovisas när leverantörsfakturan journalförs ska ha en eller flera redovisningsfördelningar.</span><span class="sxs-lookup"><span data-stu-id="a38dc-106">Every amount that must be accounted for when the vendor invoice is journalized will have one or more accounting distributions.</span></span> 

<a name="accounting-distributions"></a><span data-ttu-id="a38dc-107">Redovisningsfördelningar</span><span class="sxs-lookup"><span data-stu-id="a38dc-107">Accounting distributions</span></span> 
-------------------------

<span data-ttu-id="a38dc-108">Du kan använda följande knappar i formuläret Leverantörsfaktura om du vill visa, och möjligen ändra, redovisningsfördelningarna för varje belopp på leverantörsfakturan.</span><span class="sxs-lookup"><span data-stu-id="a38dc-108">You can use the following buttons in the Vendor invoice page to view, and possibly modify, the accounting distributions for each amount on the vendor invoice.</span></span>
-   <span data-ttu-id="a38dc-109">**Fördela belopp** – Visa och ändra redovisningsfördelningar för en enskild rad och eventuella underordnade rader, till exempel moms eller avgifter.</span><span class="sxs-lookup"><span data-stu-id="a38dc-109">**Distribute amounts** – View and modify the accounting distributions for an individual line and any child lines, such as taxes or charges.</span></span> <span data-ttu-id="a38dc-110">Du kan också visa och ändra redovisningsfördelningarna för den underordnade raden direkt från sidan Momstransaktioner eller sidan Transaktioner för avgifter.</span><span class="sxs-lookup"><span data-stu-id="a38dc-110">You can also view and modify the accounting distributions for the child line directly from the Sales tax transactions page or the Charges transactions page.</span></span>
    -   <span data-ttu-id="a38dc-111">Ändra huvudbeloppen på leverantörsfakturan, till exempel avgifter eller valutaavrundningsbelopp.</span><span class="sxs-lookup"><span data-stu-id="a38dc-111">Modify vendor invoice header amounts, such as charges or currency rounding amounts.</span></span>
    -   <span data-ttu-id="a38dc-112">Ändra radbelopp på leverantörsfaktura</span><span class="sxs-lookup"><span data-stu-id="a38dc-112">Modify vendor invoice line amounts.</span></span>
-   <span data-ttu-id="a38dc-113">**Visa fördelningar** – Visa redovisningsfördelningarna för alla rader i dokumentet.</span><span class="sxs-lookup"><span data-stu-id="a38dc-113">**View distributions** – View the accounting distributions for all lines on the document.</span></span> <span data-ttu-id="a38dc-114">Du kan inte ändra redovisningsfördelningarna från den här vyn.</span><span class="sxs-lookup"><span data-stu-id="a38dc-114">You cannot modify the accounting distributions from this view.</span></span>
    -   <span data-ttu-id="a38dc-115">Visa huvud- och radbelopp.</span><span class="sxs-lookup"><span data-stu-id="a38dc-115">View header and line amounts.</span></span>

<span data-ttu-id="a38dc-116">Om leverantörsfakturan refererar till en inköpsorder, kan du dela upp och ändra redovisningsfördelningarna för rader som innehåller en artikel som inte finns i lager.</span><span class="sxs-lookup"><span data-stu-id="a38dc-116">If the vendor invoice references a purchase order, you can split and modify the accounting distributions for lines that contain an item that is not stocked.</span></span> <span data-ttu-id="a38dc-117">Om leverantörsfakturaraden inte refererar till en inköpsorderrad kan du också ta bort en redovisningsfördelning.</span><span class="sxs-lookup"><span data-stu-id="a38dc-117">If the vendor invoice line does not reference a purchase order line, you can also delete an accounting distribution.</span></span> <span data-ttu-id="a38dc-118">Du kan inte dela eller ta bort rader för tillägg, moms och radrabatter.</span><span class="sxs-lookup"><span data-stu-id="a38dc-118">You cannot split or delete lines for charges, taxes, and line discounts.</span></span> <span data-ttu-id="a38dc-119">Du kan ändra redovisningskonto, men du kan inte ändra beloppen eller procentsatserna.</span><span class="sxs-lookup"><span data-stu-id="a38dc-119">You can modify the ledger account, but you cannot change the amounts or percentages.</span></span>
> [!NOTE]                                                                                                                                 
> <span data-ttu-id="a38dc-120">Om den överordnade raden innehåller en artikel som inte lagerförs, och redovisningsfördelningarna är delade, kommer den underordnade raden delas automatiskt för att matcha de ekonomiska dimensionerna för den överordnade raden.</span><span class="sxs-lookup"><span data-stu-id="a38dc-120">If the parent line contains an item that is not stocked and the accounting distributions are split, the child line will be split automatically to match the financial dimensions of the parent line.</span></span> <span data-ttu-id="a38dc-121">Redovisningsfördelningarna för den underordnade raden kan inte ytterligare delas eller tas bort, men beroende på inställningarna för den underordnade raden kan det gå att ändra huvudbokskontot för redovisningsfördelningarna för den underordnade raden.</span><span class="sxs-lookup"><span data-stu-id="a38dc-121">The accounting distributions for the child line cannot be additionally split or deleted, but depending on the setup of the child line, you might be able to modify the ledger account for the accounting distributions of the child line.</span></span>

## <a name="distributing-amounts"></a><span data-ttu-id="a38dc-122">Fördela belopp</span><span class="sxs-lookup"><span data-stu-id="a38dc-122">Distributing amounts</span></span>
<span data-ttu-id="a38dc-123">När du registrerar en leverantörsfaktura, kommer varje belopp fördelas på följande sätt.</span><span class="sxs-lookup"><span data-stu-id="a38dc-123">When you enter a vendor invoice, each amount will be distributed as follows.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a38dc-124">Typ av leverantörsfakturarad</span><span class="sxs-lookup"><span data-stu-id="a38dc-124">Type of vendor invoice line</span></span></th>
<th><span data-ttu-id="a38dc-125">Prioritetsordning som avgör var huvudkontot visas från</span><span class="sxs-lookup"><span data-stu-id="a38dc-125">Order of priority that determines where the main account is displayed from</span></span></th>
<th><span data-ttu-id="a38dc-126">Prioritetsordning som bestämmer vilken ekonomisk standarddimension som visas</span><span class="sxs-lookup"><span data-stu-id="a38dc-126">Order of priority that determines which default financial dimension is displayed</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="a38dc-127">Produkt i lager</span><span class="sxs-lookup"><span data-stu-id="a38dc-127">Stocked product</span></span></td>
<td><ol>
<li><span data-ttu-id="a38dc-128">Redovisningsfördelningen för inköpsorderraden.</span><span class="sxs-lookup"><span data-stu-id="a38dc-128">The accounting distribution for the purchase order line.</span></span></li>
<li><span data-ttu-id="a38dc-129">Huvudkontofältet när inköpomkostnad för produkt har valts i bokföringsidan.</span><span class="sxs-lookup"><span data-stu-id="a38dc-129">The Main account field when Purchase expenditure for product is selected in the Posting page.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="a38dc-130">Använd kontofördelningen för inköpsorderraden, om fakturaraden refererar till en inköpsorderrad.</span><span class="sxs-lookup"><span data-stu-id="a38dc-130">If the invoice line references a purchase order line, use the account distribution for the purchase order line.</span></span></li>
<li><span data-ttu-id="a38dc-131">Använd standardvärdena för ekonomiska dimensionen på leverantörsfakturan.</span><span class="sxs-lookup"><span data-stu-id="a38dc-131">Use the default financial dimension values on the vendor invoice.</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="a38dc-132">En anskaffningskategori eller en produkt som inte finns i lager</span><span class="sxs-lookup"><span data-stu-id="a38dc-132">A procurement category or a product that is not stocked</span></span></td>
<td><ol>
<li><span data-ttu-id="a38dc-133">Redovisningsfördelningen för inköpsorderraden, om leverantörsfakturaraden refererar till en inköpsorderrad.</span><span class="sxs-lookup"><span data-stu-id="a38dc-133">The accounting distribution for the purchase order line, if the vendor invoice line references a purchase order line.</span></span></li>
<li><span data-ttu-id="a38dc-134">Huvudkontofältet när inköpomkostnad för utgift har valts i bokföringsidan.</span><span class="sxs-lookup"><span data-stu-id="a38dc-134">The Main account field when Purchase expenditure for expense is selected in the Posting page.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="a38dc-135">Använd kontofördelningen för inköpsorderraden, om fakturaraden refererar till en inköpsorderrad.</span><span class="sxs-lookup"><span data-stu-id="a38dc-135">If the invoice line references a purchase order line, use the account distribution for the purchase order line.</span></span></li>
<li><span data-ttu-id="a38dc-136">Om huvudkontot är ett allokeringskonto ska du använda standardvärdet från allokeringskontodefinitionen.</span><span class="sxs-lookup"><span data-stu-id="a38dc-136">If the main account is an allocation account, use the default value from the allocation account definition.</span></span></li>
<li><span data-ttu-id="a38dc-137">Använd standardvärdena för ekonomiska dimensionen på leverantörsfakturan.</span><span class="sxs-lookup"><span data-stu-id="a38dc-137">Use the default financial dimension values on the vendor invoice.</span></span></li>
<li><span data-ttu-id="a38dc-138">Använd värdena för den ekonomiska dimensionen från leverantörsfakturaraden.</span><span class="sxs-lookup"><span data-stu-id="a38dc-138">Use the financial dimension values from the vendor invoice line.</span></span></li>
<li><span data-ttu-id="a38dc-139">Använd de förvalda värdena för ekonomiska dimensioner från huvudkontot på sidan Kontoplan.</span><span class="sxs-lookup"><span data-stu-id="a38dc-139">Use the default financial dimension values from the main account in the Chart of Accounts page.</span></span></li>
</ol></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="a38dc-140">Anläggningstillgång</span><span class="sxs-lookup"><span data-stu-id="a38dc-140">Fixed asset</span></span></td>
<td><ol>
<li><span data-ttu-id="a38dc-141">Redovisningsfördelningen för inköpsorderraden, om leverantörsfakturaraden refererar till en inköpsorderrad.</span><span class="sxs-lookup"><span data-stu-id="a38dc-141">The accounting distribution for the purchase order line, if the vendor invoice line references a purchase order line.</span></span></li>
<li><span data-ttu-id="a38dc-142">Om anskaffning har valts i fältet Transaktionstyp i formuläret Leverantörsfaktura, väljs fältet Huvudkonto när Anskaffning har markerats i formuläret Bokföringsprofiler för anläggningstillgångar.</span><span class="sxs-lookup"><span data-stu-id="a38dc-142">If Acquisition is selected in the Transaction type field in the Vendor invoice form, the Main account field when Acquisition is selected in the Fixed asset posting profiles page.</span></span></li>
<li><span data-ttu-id="a38dc-143">Om Anskaffningsjustering har valts i fältet Transaktionstyp i formuläret Leverantörsfaktura, väljs fältet Huvudkonto när Anskaffningsjustering har markerats i formuläret Bokföringsprofiler för anläggningstillgångar.</span><span class="sxs-lookup"><span data-stu-id="a38dc-143">If Acquisition adjustment is selected in the Transaction type field, the Main account field when Acquisition adjustment is selected in the Fixed asset posting profiles page.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="a38dc-144">Använd redovisningsfördelningen för inköpsorderraden, om fakturaraden refererar till en inköpsorderrad.</span><span class="sxs-lookup"><span data-stu-id="a38dc-144">Use the account distribution for the purchase order line, if the invoice line references a purchase order line.</span></span></li>
<li><span data-ttu-id="a38dc-145">Använd värdena för den ekonomiska dimensionen från leverantörsfakturaraden.</span><span class="sxs-lookup"><span data-stu-id="a38dc-145">Use the financial dimension values from the vendor invoice line.</span></span></li>
<li><span data-ttu-id="a38dc-146">Använd de förvalda värdena för ekonomiska dimensioner från huvudkontot på sidan Kontoplan.</span><span class="sxs-lookup"><span data-stu-id="a38dc-146">Use the default financial dimension values from the main account in the Chart of Accounts page.</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="a38dc-147">Projektet har definierats på leverantörsfakturaraden</span><span class="sxs-lookup"><span data-stu-id="a38dc-147">Project defined on the vendor invoice line</span></span></td>
<td><ol>
<li><span data-ttu-id="a38dc-148">Redovisningsfördelningen för inköpsorderraden, om fakturaraden refererar till en inköpsorderrad.</span><span class="sxs-lookup"><span data-stu-id="a38dc-148">The accounting distribution for the purchase order line, if the invoice line references a purchase order line.</span></span></li>
<li><span data-ttu-id="a38dc-149">Om Saldo väljs i fältet Bokföringskostnader - artikel på sidan Projektgrupp i fältet Huvudkonto när Kostnad har markerats på sidan Inställning av redovisningsbokföring.</span><span class="sxs-lookup"><span data-stu-id="a38dc-149">If Balance is selected in the Post costs - item field in the Project groups page, the Main account field when Cost is selected in the Ledger posting setup page.</span></span></li>
<li><span data-ttu-id="a38dc-150">Om Vinst och förlust väljs i fältet Bokföringskostnader - artikel på sidan Projektgrupp i fältet Huvudkonto när Kostnad - artikel har markerats på sidan Inställning av redovisningsbokföring.</span><span class="sxs-lookup"><span data-stu-id="a38dc-150">If Profit and loss is selected in the Post costs - item field in the Project groups page, the Main account field when Cost - item is selected in the Ledger posting setup page.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="a38dc-151">Använd kontofördelningen för inköpsorderraden, om fakturaraden refererar till en inköpsorderrad.</span><span class="sxs-lookup"><span data-stu-id="a38dc-151">If the invoice line references a purchase order line, use the account distribution for the purchase order line.</span></span></li>
</ol></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="a38dc-152">Radrabatt</span><span class="sxs-lookup"><span data-stu-id="a38dc-152">Line discount</span></span></td>
<td><ol>
<li><span data-ttu-id="a38dc-153">Redovisningsfördelningen för inköpsorderraden, om fakturaraden refererar till en inköpsorderrad.</span><span class="sxs-lookup"><span data-stu-id="a38dc-153">The accounting distribution for the purchase order line, if the invoice line references a purchase order line.</span></span></li>
<li><span data-ttu-id="a38dc-154">Fältet Huvudkonto, när Rabatt är markerat på sidan Bokföring.</span><span class="sxs-lookup"><span data-stu-id="a38dc-154">The Main account field when Discount is selected in the Posting page.</span></span></li>
<li><span data-ttu-id="a38dc-155">Om ett huvudkonto för en rabatt inte har definierats på bokföringsprofilen, redovisningsfördelningen för det slutliga priset på inköpsorderraden.</span><span class="sxs-lookup"><span data-stu-id="a38dc-155">If a main account for a discount is not defined on the posting profile, the accounting distribution of the extended price on the purchase order line.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="a38dc-156">Använd redovisningsfördelningen för inköpsorderraden, om fakturaraden refererar till en inköpsorderrad.</span><span class="sxs-lookup"><span data-stu-id="a38dc-156">If the invoice line references a purchase order line, use the accounting distribution for the purchase order line.</span></span></li>
<li><span data-ttu-id="a38dc-157">Använd värdena för de ekonomiska dimensionerna från redovisningsfördelningarna för det slutliga priset för leverantörsorderraden.</span><span class="sxs-lookup"><span data-stu-id="a38dc-157">Use the financial dimensions from the accounting distributions for the extended price on the vendor invoice line.</span></span></li>
<li><span data-ttu-id="a38dc-158">Använd värdena för den ekonomiska dimensionen på leverantörsfakturaraden.</span><span class="sxs-lookup"><span data-stu-id="a38dc-158">Use the financial dimension values for the vendor invoice line.</span></span></li>
<li><span data-ttu-id="a38dc-159">Använd de förvalda värdena för ekonomiska dimensioner från huvudkontot på sidan Kontoplan.</span><span class="sxs-lookup"><span data-stu-id="a38dc-159">Use the default financial dimension values from the main account in the Chart of Accounts page.</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="a38dc-160">Avgift på inköp som anges på fliken Pris och rabatt för inköpsorderraden</span><span class="sxs-lookup"><span data-stu-id="a38dc-160">Purchase charge, which is entered on the Price and discount tab of the purchase order line</span></span></td>
<td><ol>
<li><span data-ttu-id="a38dc-161">Redovisningsfördelningen för inköpsorderraden, om fakturaraden refererar till en inköpsorderrad.</span><span class="sxs-lookup"><span data-stu-id="a38dc-161">The accounting distribution for the purchase order line, if the invoice line references a purchase order line.</span></span></li>
<li><span data-ttu-id="a38dc-162">Redovisningsfördelningen av det slutliga priset på inköpsorderraden.</span><span class="sxs-lookup"><span data-stu-id="a38dc-162">The accounting distribution of the extended price on the purchase order line.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="a38dc-163">Använd kontofördelningen för inköpsorderraden, om fakturaraden refererar till en inköpsorderrad.</span><span class="sxs-lookup"><span data-stu-id="a38dc-163">If the invoice line references a purchase order line, use the account distribution for the purchase order line.</span></span></li>
<li><span data-ttu-id="a38dc-164">Använd värdena för de ekonomiska dimensionerna från redovisningsfördelningarna för det slutliga priset för leverantörsorderraden.</span><span class="sxs-lookup"><span data-stu-id="a38dc-164">Use the financial dimensions from the accounting distributions for the extended price on the vendor invoice line.</span></span></li>
</ol></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="a38dc-165">Radavgift</span><span class="sxs-lookup"><span data-stu-id="a38dc-165">Line charge</span></span></td>
<td><ol>
<li><span data-ttu-id="a38dc-166">Redovisningsfördelningen för inköpsorderraden, om fakturaraden refererar till en inköpsorderrad.</span><span class="sxs-lookup"><span data-stu-id="a38dc-166">The accounting distribution for the purchase order line, if the invoice line references a purchase order line.</span></span></li>
<li><span data-ttu-id="a38dc-167">Om Redovisningskonto har valts i debettypfältet i formuläret Avgiftskod väljs debetkontotypen på sidan Avgiftskod.</span><span class="sxs-lookup"><span data-stu-id="a38dc-167">If Ledger account is selected in the debit Type field in the Charges code form, the debit Account field in the Charges code page.</span></span></li>
<li><span data-ttu-id="a38dc-168">Om Artikel har valts i debetfältet i formuläret Avgiftskod, är redovisningsfördelningen för det slutliga priset på inköpsorderraden.</span><span class="sxs-lookup"><span data-stu-id="a38dc-168">If Item is selected in the debit Type field in the Charges code form, the accounting distribution for the extended price on the purchase order line.</span></span></li>
<li><span data-ttu-id="a38dc-169">Om Kund/leverantör har valts i debettypfältet i formuläret Avgiftskod väljs kreditkontotypen på sidan Avgiftskod.</span><span class="sxs-lookup"><span data-stu-id="a38dc-169">If Customer/Vendor is selected in the debit Type field in the Charges code form, the credit Account field in the Charges code page.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="a38dc-170">Använd kontofördelningen för inköpsorderraden, om fakturaraden refererar till en inköpsorderrad.</span><span class="sxs-lookup"><span data-stu-id="a38dc-170">If the invoice line references a purchase order line, use the account distribution for the purchase order line.</span></span></li>
<li><span data-ttu-id="a38dc-171">Använd värdena för de ekonomiska dimensionerna från redovisningsfördelningarna för det slutliga priset för leverantörsorderraden.</span><span class="sxs-lookup"><span data-stu-id="a38dc-171">Use the financial dimensions from the accounting distributions for the extended price on the vendor invoice line.</span></span></li>
<li><span data-ttu-id="a38dc-172">Använd värdena för den ekonomiska dimensionen från leverantörsfakturaraden.</span><span class="sxs-lookup"><span data-stu-id="a38dc-172">Use the financial dimension values from the vendor invoice line.</span></span></li>
<li><span data-ttu-id="a38dc-173">Använd de förvalda värdena för ekonomiska dimensioner från huvudkontot på sidan Kontoplan.</span><span class="sxs-lookup"><span data-stu-id="a38dc-173">Use the default financial dimension values from the main account in the Chart of Accounts page.</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="a38dc-174">Moms, med följande villkor:</span><span class="sxs-lookup"><span data-stu-id="a38dc-174">Tax, with the following condition:</span></span>
<ul>
<li><span data-ttu-id="a38dc-175">Alternativet Tillämpa amerikanska skatteregler har valts på sidan Allmänna redovisningparametrar.</span><span class="sxs-lookup"><span data-stu-id="a38dc-175">The Apply U.S. taxation rules option is selected in the General ledger parameters page.</span></span></li>
</ul></td>
<td><ol>
<li><span data-ttu-id="a38dc-176">Redovisningsfördelningen för inköpsorderraden, om fakturaraden refererar till en inköpsorderrad.</span><span class="sxs-lookup"><span data-stu-id="a38dc-176">The accounting distribution for the purchase order line, if the invoice line references a purchase order line.</span></span></li>
<li><span data-ttu-id="a38dc-177">Redovisningsfördelningen av det slutliga priset eller tillägget.</span><span class="sxs-lookup"><span data-stu-id="a38dc-177">The accounting distribution of the extended price or charge.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="a38dc-178">Använd kontofördelningen för inköpsorderraden, om fakturaraden refererar till en inköpsorderrad.</span><span class="sxs-lookup"><span data-stu-id="a38dc-178">If the invoice line references a purchase order line, use the account distribution for the purchase order line.</span></span></li>
<li><span data-ttu-id="a38dc-179">Använd värdena för de ekonomiska dimensionerna från redovisningsfördelningarna för det slutliga priset för leverantörsorderraden.</span><span class="sxs-lookup"><span data-stu-id="a38dc-179">Use the financial dimensions from the accounting distributions for the extended price on the vendor invoice line.</span></span></li>
<li><span data-ttu-id="a38dc-180">Använd värdena för den ekonomiska dimensionen från leverantörsfakturaraden.</span><span class="sxs-lookup"><span data-stu-id="a38dc-180">Use the financial dimension values from the vendor invoice line.</span></span></li>
</ol></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="a38dc-181">Moms, med följande villkor:</span><span class="sxs-lookup"><span data-stu-id="a38dc-181">Tax, with the following conditions:</span></span>
<ul>
<li><span data-ttu-id="a38dc-182">Alternativet Tillämpa amerikanska skatteregler har avmarkerats på sidan Allmänna redovisningparametrar.</span><span class="sxs-lookup"><span data-stu-id="a38dc-182">The Apply U.S. taxation rules option is cleared in the General ledger parameters page.</span></span></li>
<li><span data-ttu-id="a38dc-183">Fältet Importavgift för momsgruppen är avmarkerat i momsgruppsidan.</span><span class="sxs-lookup"><span data-stu-id="a38dc-183">The Use tax field for the sales tax group is cleared in the Sales tax groups page.</span></span></li>
</ul></td>
<td><ol>
<li><span data-ttu-id="a38dc-184">Om momsbeloppet är återbetalningsbart, fältet Momsfordran på sidan Redovisningsbokföringsgrupper.</span><span class="sxs-lookup"><span data-stu-id="a38dc-184">If the tax amount is recoverable, the Sales tax receivable field in the Ledger posting groups page.</span></span></li>
<li><span data-ttu-id="a38dc-185">Om momsbeloppet inte är återvinningsbart, det slutliga priset eller redovisningsfördelningen för avgiften.</span><span class="sxs-lookup"><span data-stu-id="a38dc-185">If the tax amount is not recoverable, the extended price or the accounting distribution for the charge.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="a38dc-186">Använd kontofördelningen för inköpsorderraden, om fakturaraden refererar till en inköpsorderrad.</span><span class="sxs-lookup"><span data-stu-id="a38dc-186">If the invoice line references a purchase order line, use the account distribution for the purchase order line.</span></span></li>
<li><span data-ttu-id="a38dc-187">Använd värdena för de ekonomiska dimensionerna från det slutliga priset eller från redovisningsfördelningarna för avgiften på leverantörsorderraden.</span><span class="sxs-lookup"><span data-stu-id="a38dc-187">Use the financial dimensions from the extended price or the accounting distributions for the charge on the vendor invoice line.</span></span></li>
<li><span data-ttu-id="a38dc-188">Använd värdena för den ekonomiska dimensionen från leverantörsfakturaraden.</span><span class="sxs-lookup"><span data-stu-id="a38dc-188">Use the financial dimension values from the vendor invoice line.</span></span></li>
<li><span data-ttu-id="a38dc-189">Använd de förvalda värdena för ekonomiska dimensioner från huvudkontot på sidan Kontoplan.</span><span class="sxs-lookup"><span data-stu-id="a38dc-189">Use the default financial dimension values from the main account in the Chart of Accounts page.</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="a38dc-190">Moms, med följande villkor:</span><span class="sxs-lookup"><span data-stu-id="a38dc-190">Tax, with the following conditions:</span></span>
<ul>
<li><span data-ttu-id="a38dc-191">Alternativet Tillämpa amerikanska skatteregler har avmarkerats på sidan Allmänna redovisningparametrar.</span><span class="sxs-lookup"><span data-stu-id="a38dc-191">The Apply U.S. taxation rules option is cleared in the General ledger parameters page.</span></span></li>
<li><span data-ttu-id="a38dc-192">Fältet Importavgift för momsgruppen är markerat i momsgruppsidan.</span><span class="sxs-lookup"><span data-stu-id="a38dc-192">The Use tax field for the sales tax group is selected in the Sales tax groups page.</span></span></li>
</ul></td>
<td><ol>
<li><span data-ttu-id="a38dc-193">Om momsbeloppet är återbetalningsbart, fältet Momsfordran på sidan Redovisningsbokföringsgrupper.</span><span class="sxs-lookup"><span data-stu-id="a38dc-193">If the tax amount is recoverable, the Sales tax receivable field in the Ledger posting groups page.</span></span></li>
<li><span data-ttu-id="a38dc-194">Om momsbeloppet inte är återbetalningsbart, fältet Importavgift, utgift på sidan Redovisningsbokföringsgrupper.</span><span class="sxs-lookup"><span data-stu-id="a38dc-194">If the tax amount is not recoverable, the Use tax expense field in the Ledger posting groups page.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="a38dc-195">Använd kontofördelningen för inköpsorderraden, om fakturaraden refererar till en inköpsorderrad.</span><span class="sxs-lookup"><span data-stu-id="a38dc-195">If the invoice line references a purchase order line, use the account distribution for the purchase order line.</span></span></li>
<li><span data-ttu-id="a38dc-196">Använd värdena för de ekonomiska dimensionerna från det slutliga priset eller från redovisningsfördelningarna för avgiften på leverantörsorderraden.</span><span class="sxs-lookup"><span data-stu-id="a38dc-196">Use the financial dimensions from the extended price or the accounting distributions for the charge on the vendor invoice line.</span></span></li>
<li><span data-ttu-id="a38dc-197">Använd värdena för den ekonomiska dimensionen från leverantörsfakturaraden.</span><span class="sxs-lookup"><span data-stu-id="a38dc-197">Use the financial dimension values from the vendor invoice line.</span></span></li>
<li><span data-ttu-id="a38dc-198">Använd de förvalda värdena för ekonomiska dimensioner från huvudkontot på sidan Kontoplan.</span><span class="sxs-lookup"><span data-stu-id="a38dc-198">Use the default financial dimension values from the main account in the Chart of Accounts page.</span></span></li>
</ol></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="a38dc-199">Huvudtillägg</span><span class="sxs-lookup"><span data-stu-id="a38dc-199">Header charge</span></span></td>
<td><ol>
<li><span data-ttu-id="a38dc-200">Om Redovisningskonto har valts i debettypfältet i formuläret Avgiftskod väljs debetkontotypen på sidan Avgiftskod.</span><span class="sxs-lookup"><span data-stu-id="a38dc-200">If Ledger account is selected in the debit Type field in the Charges code form, the debit Account field in the Charges code page.</span></span></li>
<li><span data-ttu-id="a38dc-201">Om Kund/leverantör har valts i debettypfältet i formuläret Avgiftskod väljs kreditkontotypen på sidan Avgiftskod.</span><span class="sxs-lookup"><span data-stu-id="a38dc-201">If Customer/Vendor is selected in the debit Type field in the Charges code form, the credit Account field in the Charges code page.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="a38dc-202">Använd kontofördelningen för inköpsorderraden, om fakturaraden refererar till en inköpsorderrad.</span><span class="sxs-lookup"><span data-stu-id="a38dc-202">If the invoice line references a purchase order line, use the account distribution for the purchase order line.</span></span></li>
<li><span data-ttu-id="a38dc-203">Om huvudkontot är ett allokeringskonto ska du använda standardvärdet från allokeringskontodefinitionen.</span><span class="sxs-lookup"><span data-stu-id="a38dc-203">If the main account is an allocation account, use the default value from the allocation account definition.</span></span></li>
<li><span data-ttu-id="a38dc-204">Använd värdena i standardmallen för ekonomiska dimensionen från leverantörsfakturarubriken.</span><span class="sxs-lookup"><span data-stu-id="a38dc-204">Use the financial dimension default template values from the vendor invoice header.</span></span></li>
<li><span data-ttu-id="a38dc-205">Använd värdena för den ekonomiska dimensionen från leverantörsfakturaraden.</span><span class="sxs-lookup"><span data-stu-id="a38dc-205">Use the financial dimension values from the vendor invoice line.</span></span></li>
<li><span data-ttu-id="a38dc-206">Använd de förvalda värdena för ekonomiska dimensioner från huvudkontot på sidan Kontoplan.</span><span class="sxs-lookup"><span data-stu-id="a38dc-206">Use the default financial dimension values from the main account in the Chart of Accounts page.</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="a38dc-207">Rubrikrabatt</span><span class="sxs-lookup"><span data-stu-id="a38dc-207">Header discount</span></span></td>
<td><ol>
<li><span data-ttu-id="a38dc-208">Fältet Huvudkonto för bokföringstypen Leverantörsfakturarabatt på sidan Konton för automatiska transaktioner.</span><span class="sxs-lookup"><span data-stu-id="a38dc-208">The Main account field for the Vendor invoice discount posting type in the Accounts for automatic transactions page.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="a38dc-209">Använd kontofördelningen för inköpsorderraden, om fakturaraden refererar till en inköpsorderrad.</span><span class="sxs-lookup"><span data-stu-id="a38dc-209">If the invoice line references a purchase order line, use the account distribution for the purchase order line.</span></span></li>
<li><span data-ttu-id="a38dc-210">Använd värdena för de ekonomiska dimensionerna från redovisningsfördelningarna för det slutliga priset för leverantörsorderraden.</span><span class="sxs-lookup"><span data-stu-id="a38dc-210">Use the financial dimensions from the accounting distributions for the extended price on the vendor invoice line.</span></span></li>
<li><span data-ttu-id="a38dc-211">Använd värdena för den ekonomiska dimensionen från leverantörsfakturaraden.</span><span class="sxs-lookup"><span data-stu-id="a38dc-211">Use the financial dimension values from the vendor invoice line.</span></span></li>
<li><span data-ttu-id="a38dc-212">Använd de förvalda värdena för ekonomiska dimensioner från huvudkontot på sidan Kontoplan.</span><span class="sxs-lookup"><span data-stu-id="a38dc-212">Use the default financial dimension values from the main account in the Chart of Accounts page.</span></span></li>
</ol></td>
</tr>
</tbody>
</table>


<a name="distributing-taxes"></a><span data-ttu-id="a38dc-213">Fördela moms</span><span class="sxs-lookup"><span data-stu-id="a38dc-213">Distributing taxes</span></span>
------------------

<span data-ttu-id="a38dc-214">Redovisningsfördelning för skatter går inte att skapa förrän skatter har beräknats.</span><span class="sxs-lookup"><span data-stu-id="a38dc-214">Accounting distributions for taxes cannot be created until taxes are calculated.</span></span> <span data-ttu-id="a38dc-215">Om du vill beräkna moms måste du färdigställa en av följande uppgifter på sidan Leverantörsfaktura.</span><span class="sxs-lookup"><span data-stu-id="a38dc-215">To calculate sales taxes, you must complete one of the following tasks in the Vendor invoice page:</span></span>
-   <span data-ttu-id="a38dc-216">Visa fakturasumman.</span><span class="sxs-lookup"><span data-stu-id="a38dc-216">View the invoice total.</span></span>
-   <span data-ttu-id="a38dc-217">Visa momsen.</span><span class="sxs-lookup"><span data-stu-id="a38dc-217">View the sales tax.</span></span>
-   <span data-ttu-id="a38dc-218">Visa redovisningsjournalen.</span><span class="sxs-lookup"><span data-stu-id="a38dc-218">View the subledger journal.</span></span>
-   <span data-ttu-id="a38dc-219">Visa redovisningsfördelningar för den slutförda leverantörsfakturan.</span><span class="sxs-lookup"><span data-stu-id="a38dc-219">View accounting distributions for the complete vendor invoice.</span></span>
-   <span data-ttu-id="a38dc-220">Spärra leverantörsfakturan.</span><span class="sxs-lookup"><span data-stu-id="a38dc-220">Place the vendor invoice on hold.</span></span>
-   <span data-ttu-id="a38dc-221">Bokför leverantörsfakturan.</span><span class="sxs-lookup"><span data-stu-id="a38dc-221">Post the vendor invoice.</span></span>

## <a name="subledger-journals-for-vendor-invoices"></a><span data-ttu-id="a38dc-222">Redovisningsjournaler för leverantörsfakturor</span><span class="sxs-lookup"><span data-stu-id="a38dc-222">Subledger journals for vendor invoices</span></span>
<span data-ttu-id="a38dc-223">Innan du bokför en leverantörsfaktura kan du visa hela redovisningsposten för fakturan, som inkluderar debiteringar och krediteringar, för att kontrollera att fakturan bokförs till rätt konton.</span><span class="sxs-lookup"><span data-stu-id="a38dc-223">Before you post a vendor invoice, you can view the full accounting entry of the invoice, which includes debits and credits, to verify that the invoice is being posted to the correct accounts.</span></span> <span data-ttu-id="a38dc-224">Denna vy av hela redovisningsposten kallas en redovisningsjournal.</span><span class="sxs-lookup"><span data-stu-id="a38dc-224">This view of the full accounting entry is called a subledger journal.</span></span> 

<span data-ttu-id="a38dc-225">Om posten i reskontrajournalen är fel när du granskar den innan du journalför leverantörsfakturan, kan du inte ändra posten i reskontrajournalen.</span><span class="sxs-lookup"><span data-stu-id="a38dc-225">If the subledger journal entry is incorrect when you preview it before you journalize the vendor invoice, you cannot modify the subledger journal entry.</span></span> <span data-ttu-id="a38dc-226">I stället måste du ändra redovisningsfördelningarna eller bokföringsprofilen.</span><span class="sxs-lookup"><span data-stu-id="a38dc-226">Instead, you must modify the accounting distributions or the posting profile.</span></span> <span data-ttu-id="a38dc-227">Redovisningsfördelningarna används för att definiera ena sidan i redovisningposten, debet eller kredit.</span><span class="sxs-lookup"><span data-stu-id="a38dc-227">The accounting distributions are used to define one side of the accounting entry, the debit or the credit.</span></span> <span data-ttu-id="a38dc-228">Den förskjutande kontoposten i reskontrajournalen skapas med hjälp av bokföringsprofilerna, till exempel från leverantörskontot eller moms.</span><span class="sxs-lookup"><span data-stu-id="a38dc-228">The offsetting subledger journal account entry is created by using the posting profiles, such as from the vendor account or tax.</span></span>





