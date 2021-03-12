---
title: Momsberäkning för allmänna journalrader
description: Det här ämnet förklarar hur moms beräknas för olika typer av konton (leverantör, kund, redovisning och projekt) på allmänna journalrader.
author: EricWang
manager: Ann Beebe
ms.date: 08/14/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2019-08-14
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: e420632c248b5b43d4983c5eb483cac580e67f20
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4975568"
---
# <a name="sales-tax-calculation-on-general-journal-lines"></a><span data-ttu-id="387f4-103">Momsberäkning för allmänna journalrader</span><span class="sxs-lookup"><span data-stu-id="387f4-103">Sales tax calculation on general journal lines</span></span>
[!include [banner](../includes/banner.md)]

<span data-ttu-id="387f4-104">Det här ämnet förklarar hur moms beräknas för olika typer av konton (leverantör, kund, redovisning och projekt) på allmänna journalrader.</span><span class="sxs-lookup"><span data-stu-id="387f4-104">This topic explains how sales taxes are calculated for different types of accounts (vendor, customer, ledger, and project) on general journal lines.</span></span>

<span data-ttu-id="387f4-105">Processen kan delas in i tre steg:</span><span class="sxs-lookup"><span data-stu-id="387f4-105">The process can be divided into three steps:</span></span>

- <span data-ttu-id="387f4-106">Bestämma momsriktningen.</span><span class="sxs-lookup"><span data-stu-id="387f4-106">Determine the sales tax direction.</span></span>

- <span data-ttu-id="387f4-107">Avgör vilket momsbelopp som ska lagras i ett tillfälligt momsregister.</span><span class="sxs-lookup"><span data-stu-id="387f4-107">Determine the sales tax amount that will be stored a temporary sales tax table.</span></span>

- <span data-ttu-id="387f4-108">Bestäm momsbeloppet och kontot på verifikationen.</span><span class="sxs-lookup"><span data-stu-id="387f4-108">Determine the sales tax amount and account on the voucher.</span></span>

## <a name="determine-the-sales-tax-direction"></a><span data-ttu-id="387f4-109">Bestämma momsriktningen</span><span class="sxs-lookup"><span data-stu-id="387f4-109">Determine the sales tax direction</span></span>

<span data-ttu-id="387f4-110">Hur momsriktningen bestäms beror på typen av konto i verifikationen.</span><span class="sxs-lookup"><span data-stu-id="387f4-110">The way that the sales tax direction is determined depends on the type of account in the voucher.</span></span> <span data-ttu-id="387f4-111">Momsriktningen bestäms av kombinationen av kontotypen och momskoden.</span><span class="sxs-lookup"><span data-stu-id="387f4-111">The sales tax direction is determined by the combination of account type and sales tax code.</span></span> <span data-ttu-id="387f4-112">De följande avsnitten är möjligheterna i mer detaljerat.</span><span class="sxs-lookup"><span data-stu-id="387f4-112">The following sections the possibilities in more detail.</span></span> 

### <a name="account-type-is-project"></a><span data-ttu-id="387f4-113">Kontotyp är projekt</span><span class="sxs-lookup"><span data-stu-id="387f4-113">Account type is Project</span></span>

<span data-ttu-id="387f4-114">Om en verifikation har en journalrad där kontotypen är **projekt**, använder alla journalrader i verifikationen samma momsriktning.</span><span class="sxs-lookup"><span data-stu-id="387f4-114">If a voucher has journal line where the account type is **Project**, all the journal lines in the voucher apply the same tax direction.</span></span> <span data-ttu-id="387f4-115">På bilden nedan visas regeln.</span><span class="sxs-lookup"><span data-stu-id="387f4-115">The following illustration shows the rule.</span></span> <span data-ttu-id="387f4-116">Följande poäng visar de möjliga momsriktningarna för projektkonton.</span><span class="sxs-lookup"><span data-stu-id="387f4-116">The following points show the possible tax directions for project accounts.</span></span>

<span data-ttu-id="387f4-117">•   Om momskoden är importavgift är momsriktningen importavgift.</span><span class="sxs-lookup"><span data-stu-id="387f4-117">•   If the sales tax code is use tax, then sales tax direction is Use Tax.</span></span>

<span data-ttu-id="387f4-118">•   Om momskoden är momsbefriad är momsriktningen är skattefritt inköp.</span><span class="sxs-lookup"><span data-stu-id="387f4-118">•   If the sales tax code is exempt tax, then sales tax direction is Tax Free Purchase.</span></span>

<span data-ttu-id="387f4-119">•   Om momskoden är Inomeuropeisk moms är momsriktningen Utgående moms.</span><span class="sxs-lookup"><span data-stu-id="387f4-119">•   If the sales tax code is intracom VAT, then sales tax direction is Sales Tax Payable.</span></span>

<span data-ttu-id="387f4-120">•   Om momskoden är återfört tillägg moms är momsriktningen Utgående moms.</span><span class="sxs-lookup"><span data-stu-id="387f4-120">•   If the sales tax code is reverse charge, then sales tax direction is Sales Tax Payable.</span></span>

<span data-ttu-id="387f4-121">Annars är momsriktningen Ingående moms.</span><span class="sxs-lookup"><span data-stu-id="387f4-121">Otherwise, sales tax direction is Sales Tax Receivable.</span></span>

<span data-ttu-id="387f4-122">Följande diagram visar regeln grafiskt.</span><span class="sxs-lookup"><span data-stu-id="387f4-122">The following diagram illustrates the rule graphically.</span></span>

![Momsriktningsmöjligheter för projektkonton](media/Sales-Tax-Direction-Vendor.jpg)

### <a name="account-type-is-vendor"></a><span data-ttu-id="387f4-124">Kontotypen är leverantör</span><span class="sxs-lookup"><span data-stu-id="387f4-124">Account type is Vendor</span></span>

<span data-ttu-id="387f4-125">Om en verifikation har en journalrad där kontotypen är **leverantör**, använder alla journalrader i verifikationen samma momsriktning.</span><span class="sxs-lookup"><span data-stu-id="387f4-125">If a voucher has journal line where the account type is **Vendor**, all the journal lines in the voucher apply the same tax direction.</span></span> <span data-ttu-id="387f4-126">Följande poäng visar de möjliga momsriktningarna för leverantörskonton.</span><span class="sxs-lookup"><span data-stu-id="387f4-126">The following points show the possible tax directions for vendor accounts.</span></span> 

<span data-ttu-id="387f4-127">•   Om momskoden är importavgift är momsriktningen importavgift.</span><span class="sxs-lookup"><span data-stu-id="387f4-127">•   If the sales tax code is use tax, then sales tax direction is Use Tax.</span></span>

<span data-ttu-id="387f4-128">•   Om momskoden är momsbefriad är momsriktningen är skattefritt inköp.</span><span class="sxs-lookup"><span data-stu-id="387f4-128">•   If the sales tax code is exempt tax, then sales tax direction is Tax Free Purchase.</span></span>

<span data-ttu-id="387f4-129">•   Om momskoden är Inomeuropeisk moms är momsriktningen Utgående moms.</span><span class="sxs-lookup"><span data-stu-id="387f4-129">•   If the sales tax code is intracom VAT, then sales tax direction is Sales Tax Payable.</span></span>

<span data-ttu-id="387f4-130">•   Om momskoden är återfört tillägg moms är momsriktningen Utgående moms.</span><span class="sxs-lookup"><span data-stu-id="387f4-130">•   If the sales tax code is reverse charge, then sales tax direction is Sales Tax Payable.</span></span>

<span data-ttu-id="387f4-131">Annars är momsriktningen Ingående moms.</span><span class="sxs-lookup"><span data-stu-id="387f4-131">Otherwise, sales tax direction is Sales Tax Receivable.</span></span>

<span data-ttu-id="387f4-132">Följande diagram visar regeln grafiskt.</span><span class="sxs-lookup"><span data-stu-id="387f4-132">The following diagram illustrates the rule graphically.</span></span>

![Momsriktningsmöjligheter för leverantörskonton](media/Sales-Tax-Direction-Vendor.jpg)

### <a name="account-type-is-customer"></a><span data-ttu-id="387f4-134">Kontotyp är kund</span><span class="sxs-lookup"><span data-stu-id="387f4-134">Account type is Customer</span></span>

<span data-ttu-id="387f4-135">Om en verifikation har en journalrad där kontotypen är **kund**, använder alla journalrader i verifikationen samma momsriktning.</span><span class="sxs-lookup"><span data-stu-id="387f4-135">If a voucher has journal line where the account type is **Customer**, all the journal lines in the voucher apply the same tax direction.</span></span> <span data-ttu-id="387f4-136">Följande poäng visar de möjliga momsriktningarna för kundkonton.</span><span class="sxs-lookup"><span data-stu-id="387f4-136">The following points show the possible tax directions for customer accounts.</span></span>

<span data-ttu-id="387f4-137">•   Om momskoden är momsbefriad är momsriktningen är skattefritt inköp.</span><span class="sxs-lookup"><span data-stu-id="387f4-137">•   If the sales tax code is exempt tax, then sales tax direction is Tax Free Purchase.</span></span>

<span data-ttu-id="387f4-138">•   Om momskoden är Inomeuropeisk moms är momsriktningen Ingående moms.</span><span class="sxs-lookup"><span data-stu-id="387f4-138">•   If the sales tax code is intracom VAT, then sales tax direction is Sales Tax Receivable.</span></span>

<span data-ttu-id="387f4-139">•   Om momskoden är återfört tillägg moms är momsriktningen Ingående moms.</span><span class="sxs-lookup"><span data-stu-id="387f4-139">•   If the sales tax code is reverse charge, then sales tax direction is Sales Tax Receivable.</span></span>

<span data-ttu-id="387f4-140">Annars är momsriktningen Utgående moms.</span><span class="sxs-lookup"><span data-stu-id="387f4-140">Otherwise, sales tax direction is Sales Tax Payable.</span></span>

<span data-ttu-id="387f4-141">Följande diagram visar regeln grafiskt.</span><span class="sxs-lookup"><span data-stu-id="387f4-141">The following diagram illustrates the rule graphically.</span></span>

![Momsriktningsmöjligheter för kundkonton](media/Sales-Tax-Direction-Customer.jpg)

### <a name="account-type-is-ledger"></a><span data-ttu-id="387f4-143">Kontotypen är Redovisning</span><span class="sxs-lookup"><span data-stu-id="387f4-143">Account type is Ledger</span></span>

<span data-ttu-id="387f4-144">Följande illustration visar den regel som gäller när en verifikation bara har journalrader där kontotypen är **redovisning**.</span><span class="sxs-lookup"><span data-stu-id="387f4-144">The following illustration shows the rule that applies when a voucher has only journal lines where the account type is **Ledger**.</span></span> <span data-ttu-id="387f4-145">Följande poäng visar de möjliga momsriktningarna för redovisningskonton.</span><span class="sxs-lookup"><span data-stu-id="387f4-145">The following points show the possible tax directions for ledger accounts.</span></span>

<span data-ttu-id="387f4-146">•   Om momskoden är importavgift är momsriktningen importavgift.</span><span class="sxs-lookup"><span data-stu-id="387f4-146">•   If the sales tax code is use tax, then sales tax direction is Use Tax.</span></span>

<span data-ttu-id="387f4-147">•   Om momskoden är momsbefriad är momsriktningen är skattefritt inköp.</span><span class="sxs-lookup"><span data-stu-id="387f4-147">•   If the sales tax code is exempt tax, then sales tax direction is Tax Free Purchase.</span></span>

<span data-ttu-id="387f4-148">Annars, om journalbeloppet är debet (positivt), är momsriktningen för Ingående moms. Om journalbeloppet är kredit (negativ), är momsriktningen Utgående moms.</span><span class="sxs-lookup"><span data-stu-id="387f4-148">Otherwise, if the journal amount is debit (positive) ,sales tax direction is Sales Tax Receivable; if the journal amount is credit (negative) ,sales tax direction is Sales Tax Payable.</span></span>

<span data-ttu-id="387f4-149">Följande diagram visar regeln grafiskt.</span><span class="sxs-lookup"><span data-stu-id="387f4-149">The following diagram illustrates the rule graphically.</span></span>

![Momsriktningsmöjligheter för redovisningskonton](media/Sales-Tax-Direction-Ledger.jpg)

#### <a name="override-the-sales-tax-direction"></a><span data-ttu-id="387f4-151">Åsidosätt momsriktningen</span><span class="sxs-lookup"><span data-stu-id="387f4-151">Override the sales tax direction</span></span>

<span data-ttu-id="387f4-152">Du kan åsidosätta momsriktningen när verifikationen bara innehåller rader där kontotypen är **redovisning**.</span><span class="sxs-lookup"><span data-stu-id="387f4-152">You can override the sales tax direction when the voucher contains only lines where the account type is **Ledger**.</span></span>

<span data-ttu-id="387f4-153">Gå till **Redovisning \> Kontoplan \> Konton \> Huvudkonton** och välj snabbfliken **Juridisk person åsidosätter**.</span><span class="sxs-lookup"><span data-stu-id="387f4-153">Go to **General ledger \> Chart of accounts \> Accounts \> Main accounts**, and select the **Legal entity overrides** FastTab.</span></span>

## <a name="determine-the-sales-tax-amount"></a><span data-ttu-id="387f4-154">Bestämma momsbelopp</span><span class="sxs-lookup"><span data-stu-id="387f4-154">Determine the sales tax amount</span></span>

<span data-ttu-id="387f4-155">I det här avsnittet beskrivs hur tecknet för momsbelopp beräknas.</span><span class="sxs-lookup"><span data-stu-id="387f4-155">This section describes how the sales tax amount sign is calculated.</span></span>

![Sidan momstransaktioner](media/sales-tax-amount-sign.jpg)

<span data-ttu-id="387f4-157">I följande tabell visas den allmänna regeln för bestämning av momsbelopp i det tillfälliga momsregistret.</span><span class="sxs-lookup"><span data-stu-id="387f4-157">The following table shows the generic rule for determining the sign of sales tax amounts in the temporary sales tax table.</span></span>

| <span data-ttu-id="387f4-158">Journalradsbelopp</span><span class="sxs-lookup"><span data-stu-id="387f4-158">Journal line amount</span></span> | <span data-ttu-id="387f4-159">Momsriktning</span><span class="sxs-lookup"><span data-stu-id="387f4-159">Sales tax direction</span></span>  | <span data-ttu-id="387f4-160">Momsbelopptecken</span><span class="sxs-lookup"><span data-stu-id="387f4-160">Sales tax amount sign</span></span> |
|---------------------|----------------------|-----------------------|
| <span data-ttu-id="387f4-161">Positiva</span><span class="sxs-lookup"><span data-stu-id="387f4-161">Positive</span></span>            | <span data-ttu-id="387f4-162">Ingående moms</span><span class="sxs-lookup"><span data-stu-id="387f4-162">Sales Tax Receivable</span></span> | <span data-ttu-id="387f4-163">Positiva</span><span class="sxs-lookup"><span data-stu-id="387f4-163">Positive</span></span>              |
| <span data-ttu-id="387f4-164">Positiva</span><span class="sxs-lookup"><span data-stu-id="387f4-164">Positive</span></span>            | <span data-ttu-id="387f4-165">Utgående moms</span><span class="sxs-lookup"><span data-stu-id="387f4-165">Sales Tax Payable</span></span>    | <span data-ttu-id="387f4-166">Negativa</span><span class="sxs-lookup"><span data-stu-id="387f4-166">Negative</span></span>              |
| <span data-ttu-id="387f4-167">Negativa</span><span class="sxs-lookup"><span data-stu-id="387f4-167">Negative</span></span>            | <span data-ttu-id="387f4-168">Ingående moms</span><span class="sxs-lookup"><span data-stu-id="387f4-168">Sales Tax Receivable</span></span> | <span data-ttu-id="387f4-169">Negativa</span><span class="sxs-lookup"><span data-stu-id="387f4-169">Negative</span></span>              |
| <span data-ttu-id="387f4-170">Negativa</span><span class="sxs-lookup"><span data-stu-id="387f4-170">Negative</span></span>            | <span data-ttu-id="387f4-171">Utgående moms</span><span class="sxs-lookup"><span data-stu-id="387f4-171">Sales Tax Payable</span></span>    | <span data-ttu-id="387f4-172">Positiva</span><span class="sxs-lookup"><span data-stu-id="387f4-172">Positive</span></span>              |

<span data-ttu-id="387f4-173">Det finns en särskild regel för verifikationer som bara har raderna **Projekt** eller **Redovisning** när en moms grupp eller artikelmomsgrupp har valts på raden **Redovisning**.</span><span class="sxs-lookup"><span data-stu-id="387f4-173">There is a special rule for vouchers that have only **Project** or **Ledger** lines, when a sales tax group or item sales tax group is selected on the **Ledger** line.</span></span> <span data-ttu-id="387f4-174">Den här regeln styrs genom aktivering av oberoende momsberäkningsfunktion för allmänna journaler.</span><span class="sxs-lookup"><span data-stu-id="387f4-174">This rule is controlled by Enable independent sales tax calculation feature for general journals.</span></span> <span data-ttu-id="387f4-175">När den här funktionen inaktiveras använder momsbeloppet för raden **redovisning** debet-/kreditriktningen för raden **projekt**.</span><span class="sxs-lookup"><span data-stu-id="387f4-175">When this feature is turned off, the tax amount of the **Ledger** line uses the debit/credit direction of the **Project** line.</span></span> <span data-ttu-id="387f4-176">När den här funktionen aktiveras använder momsbeloppet för raden **redovisning** debet-/kreditriktningen.</span><span class="sxs-lookup"><span data-stu-id="387f4-176">When the feature is turned on, the tax amount of the **Ledger** line uses its own debit/credit direction.</span></span> <span data-ttu-id="387f4-177">I följande tabeller visas regeln för varje scenario.</span><span class="sxs-lookup"><span data-stu-id="387f4-177">The following tables show the rule for each scenario.</span></span> 

<span data-ttu-id="387f4-178">**Regel när funktionen är aktiverad**</span><span class="sxs-lookup"><span data-stu-id="387f4-178">**Rule when the feature is turned on**</span></span>

| <span data-ttu-id="387f4-179">Journalradbelopp för projekt</span><span class="sxs-lookup"><span data-stu-id="387f4-179">Journal line amount of project</span></span> | <span data-ttu-id="387f4-180">Momsriktning</span><span class="sxs-lookup"><span data-stu-id="387f4-180">Sales tax direction</span></span>  | <span data-ttu-id="387f4-181">Momsbelopptecken</span><span class="sxs-lookup"><span data-stu-id="387f4-181">Sales tax amount sign</span></span> |
|--------------------------------|----------------------|-----------------------|
| <span data-ttu-id="387f4-182">Positiva</span><span class="sxs-lookup"><span data-stu-id="387f4-182">Positive</span></span>                       | <span data-ttu-id="387f4-183">Ingående moms</span><span class="sxs-lookup"><span data-stu-id="387f4-183">Sales Tax Receivable</span></span> | <span data-ttu-id="387f4-184">Positiva</span><span class="sxs-lookup"><span data-stu-id="387f4-184">Positive</span></span>              |
| <span data-ttu-id="387f4-185">Negativa</span><span class="sxs-lookup"><span data-stu-id="387f4-185">Negative</span></span>                       | <span data-ttu-id="387f4-186">Ingående moms</span><span class="sxs-lookup"><span data-stu-id="387f4-186">Sales Tax Receivable</span></span> | <span data-ttu-id="387f4-187">Negativa</span><span class="sxs-lookup"><span data-stu-id="387f4-187">Negative</span></span>              |

<span data-ttu-id="387f4-188">**Regel när funktionen är inaktiverad**</span><span class="sxs-lookup"><span data-stu-id="387f4-188">**Rule when the feature is turned off**</span></span>

| <span data-ttu-id="387f4-189">Journalradbelopp för redovisning</span><span class="sxs-lookup"><span data-stu-id="387f4-189">Journal line amount of ledger</span></span>  | <span data-ttu-id="387f4-190">Momsriktning</span><span class="sxs-lookup"><span data-stu-id="387f4-190">Sales tax direction</span></span>  | <span data-ttu-id="387f4-191">Momsbelopptecken</span><span class="sxs-lookup"><span data-stu-id="387f4-191">Sales tax amount sign</span></span> |
|--------------------------------|----------------------|-----------------------|
| <span data-ttu-id="387f4-192">Positiva</span><span class="sxs-lookup"><span data-stu-id="387f4-192">Positive</span></span>                       | <span data-ttu-id="387f4-193">Ingående moms</span><span class="sxs-lookup"><span data-stu-id="387f4-193">Sales Tax Receivable</span></span> | <span data-ttu-id="387f4-194">Positiva</span><span class="sxs-lookup"><span data-stu-id="387f4-194">Positive</span></span>              |
| <span data-ttu-id="387f4-195">Negativa</span><span class="sxs-lookup"><span data-stu-id="387f4-195">Negative</span></span>                       | <span data-ttu-id="387f4-196">Ingående moms</span><span class="sxs-lookup"><span data-stu-id="387f4-196">Sales Tax Receivable</span></span> | <span data-ttu-id="387f4-197">Negativa</span><span class="sxs-lookup"><span data-stu-id="387f4-197">Negative</span></span>              |

## <a name="determine-the-sales-tax-amount-and-account-on-the-voucher"></a><span data-ttu-id="387f4-198">Bestäm momsbeloppet och kontot på verifikationen</span><span class="sxs-lookup"><span data-stu-id="387f4-198">Determine the sales tax amount and account on the voucher</span></span>

<span data-ttu-id="387f4-199">När du bokför moms hämtas huvudkontot från profilen för redovisningens bokföringsgrupprofil.</span><span class="sxs-lookup"><span data-stu-id="387f4-199">When you post sales taxes, the main account is retrieved from the ledger posting group profile.</span></span> <span data-ttu-id="387f4-200">När moms inkommer använder systemet det konto för ingående moms som anges i profilen.</span><span class="sxs-lookup"><span data-stu-id="387f4-200">When sales taxes are receivable, the system uses the Sales Tax Receivable account that is specified in the profile.</span></span> <span data-ttu-id="387f4-201">För moms som ska betalas använder systemet det konto för utgående moms som anges i profilen.</span><span class="sxs-lookup"><span data-stu-id="387f4-201">For sales taxes that are payable, the system uses Sales Tax Payable account that is specified in the profile.</span></span>

<span data-ttu-id="387f4-202">Tabellen nedan visar den allmänna regeln.</span><span class="sxs-lookup"><span data-stu-id="387f4-202">The following table shows the generic rule.</span></span>

| <span data-ttu-id="387f4-203">Momsriktning</span><span class="sxs-lookup"><span data-stu-id="387f4-203">Sales tax direction</span></span>  | <span data-ttu-id="387f4-204">Momsbelopptecken</span><span class="sxs-lookup"><span data-stu-id="387f4-204">Sales tax amount sign</span></span> | <span data-ttu-id="387f4-205">Momskonto</span><span class="sxs-lookup"><span data-stu-id="387f4-205">Sales tax account</span></span>      | <span data-ttu-id="387f4-206">Belopp på verifikationen</span><span class="sxs-lookup"><span data-stu-id="387f4-206">Amount on voucher</span></span> |
|----------------------|-----------------------|------------------------|-------------------|
| <span data-ttu-id="387f4-207">Ingående moms</span><span class="sxs-lookup"><span data-stu-id="387f4-207">Sales Tax Receivable</span></span> | <span data-ttu-id="387f4-208">Positiva</span><span class="sxs-lookup"><span data-stu-id="387f4-208">Positive</span></span>              | <span data-ttu-id="387f4-209">Konto för ingående moms</span><span class="sxs-lookup"><span data-stu-id="387f4-209">Tax Receivable Account</span></span> | <span data-ttu-id="387f4-210">Positiv (Debet)</span><span class="sxs-lookup"><span data-stu-id="387f4-210">Positive (Debit)</span></span>  |
| <span data-ttu-id="387f4-211">Ingående moms</span><span class="sxs-lookup"><span data-stu-id="387f4-211">Sales Tax Receivable</span></span> | <span data-ttu-id="387f4-212">Negativa</span><span class="sxs-lookup"><span data-stu-id="387f4-212">Negative</span></span>              | <span data-ttu-id="387f4-213">Konto för ingående moms</span><span class="sxs-lookup"><span data-stu-id="387f4-213">Tax Receivable Account</span></span> | <span data-ttu-id="387f4-214">Negativ (kredit)</span><span class="sxs-lookup"><span data-stu-id="387f4-214">Negative(Credit)</span></span>  |
| <span data-ttu-id="387f4-215">Utgående moms</span><span class="sxs-lookup"><span data-stu-id="387f4-215">Sales Tax Payable</span></span>    | <span data-ttu-id="387f4-216">Positiva</span><span class="sxs-lookup"><span data-stu-id="387f4-216">Positive</span></span>              | <span data-ttu-id="387f4-217">Konto för utgående moms</span><span class="sxs-lookup"><span data-stu-id="387f4-217">Tax Payable Account</span></span>    | <span data-ttu-id="387f4-218">Negativ (kredit)</span><span class="sxs-lookup"><span data-stu-id="387f4-218">Negative(Credit)</span></span>  |
| <span data-ttu-id="387f4-219">Utgående moms</span><span class="sxs-lookup"><span data-stu-id="387f4-219">Sales Tax Payable</span></span>    | <span data-ttu-id="387f4-220">Negativa</span><span class="sxs-lookup"><span data-stu-id="387f4-220">Negative</span></span>              | <span data-ttu-id="387f4-221">Konto för utgående moms</span><span class="sxs-lookup"><span data-stu-id="387f4-221">Tax Payable Account</span></span>    | <span data-ttu-id="387f4-222">Positiv (Debet)</span><span class="sxs-lookup"><span data-stu-id="387f4-222">Positive (Debit)</span></span>  |
