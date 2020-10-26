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
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2019-08-14
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: 51d43c8e6d16201e1f8c392c13ead20287782dcc
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/10/2020
ms.locfileid: "3983607"
---
# <a name="sales-tax-calculation-on-general-journal-lines"></a><span data-ttu-id="f6c07-103">Momsberäkning för allmänna journalrader</span><span class="sxs-lookup"><span data-stu-id="f6c07-103">Sales tax calculation on general journal lines</span></span>
[!include [banner](../includes/banner.md)]

<span data-ttu-id="f6c07-104">Det här ämnet förklarar hur moms beräknas för olika typer av konton (leverantör, kund, redovisning och projekt) på allmänna journalrader.</span><span class="sxs-lookup"><span data-stu-id="f6c07-104">This topic explains how sales taxes are calculated for different types of accounts (vendor, customer, ledger, and project) on general journal lines.</span></span>

<span data-ttu-id="f6c07-105">Processen kan delas in i tre steg:</span><span class="sxs-lookup"><span data-stu-id="f6c07-105">The process can be divided into three steps:</span></span>

- <span data-ttu-id="f6c07-106">Bestämma momsriktningen.</span><span class="sxs-lookup"><span data-stu-id="f6c07-106">Determine the sales tax direction.</span></span>

- <span data-ttu-id="f6c07-107">Avgör vilket momsbelopp som ska lagras i ett tillfälligt momsregister.</span><span class="sxs-lookup"><span data-stu-id="f6c07-107">Determine the sales tax amount that will be stored a temporary sales tax table.</span></span>

- <span data-ttu-id="f6c07-108">Bestäm momsbeloppet och kontot på verifikationen.</span><span class="sxs-lookup"><span data-stu-id="f6c07-108">Determine the sales tax amount and account on the voucher.</span></span>

## <a name="determine-the-sales-tax-direction"></a><span data-ttu-id="f6c07-109">Bestämma momsriktningen</span><span class="sxs-lookup"><span data-stu-id="f6c07-109">Determine the sales tax direction</span></span>

<span data-ttu-id="f6c07-110">Hur momsriktningen bestäms beror på typen av konto i verifikationen.</span><span class="sxs-lookup"><span data-stu-id="f6c07-110">The way that the sales tax direction is determined depends on the type of account in the voucher.</span></span> <span data-ttu-id="f6c07-111">Momsriktningen bestäms av kombinationen av kontotypen och momskoden.</span><span class="sxs-lookup"><span data-stu-id="f6c07-111">The sales tax direction is determined by the combination of account type and sales tax code.</span></span> <span data-ttu-id="f6c07-112">De följande avsnitten är möjligheterna i mer detaljerat.</span><span class="sxs-lookup"><span data-stu-id="f6c07-112">The following sections the possibilities in more detail.</span></span> 

### <a name="account-type-is-project"></a><span data-ttu-id="f6c07-113">Kontotyp är projekt</span><span class="sxs-lookup"><span data-stu-id="f6c07-113">Account type is Project</span></span>

<span data-ttu-id="f6c07-114">Om en verifikation har en journalrad där kontotypen är **projekt**, använder alla journalrader i verifikationen samma momsriktning.</span><span class="sxs-lookup"><span data-stu-id="f6c07-114">If a voucher has journal line where the account type is **Project**, all the journal lines in the voucher apply the same tax direction.</span></span> <span data-ttu-id="f6c07-115">På bilden nedan visas regeln.</span><span class="sxs-lookup"><span data-stu-id="f6c07-115">The following illustration shows the rule.</span></span> <span data-ttu-id="f6c07-116">Följande poäng visar de möjliga momsriktningarna för projektkonton.</span><span class="sxs-lookup"><span data-stu-id="f6c07-116">The following points show the possible tax directions for project accounts.</span></span>

<span data-ttu-id="f6c07-117">•   Om momskoden är importavgift är momsriktningen importavgift.</span><span class="sxs-lookup"><span data-stu-id="f6c07-117">•   If the sales tax code is use tax, then sales tax direction is Use Tax.</span></span>

<span data-ttu-id="f6c07-118">•   Om momskoden är momsbefriad är momsriktningen är skattefritt inköp.</span><span class="sxs-lookup"><span data-stu-id="f6c07-118">•   If the sales tax code is exempt tax, then sales tax direction is Tax Free Purchase.</span></span>

<span data-ttu-id="f6c07-119">•   Om momskoden är Inomeuropeisk moms är momsriktningen Utgående moms.</span><span class="sxs-lookup"><span data-stu-id="f6c07-119">•   If the sales tax code is intracom VAT, then sales tax direction is Sales Tax Payable.</span></span>

<span data-ttu-id="f6c07-120">•   Om momskoden är återfört tillägg moms är momsriktningen Utgående moms.</span><span class="sxs-lookup"><span data-stu-id="f6c07-120">•   If the sales tax code is reverse charge, then sales tax direction is Sales Tax Payable.</span></span>

<span data-ttu-id="f6c07-121">Annars är momsriktningen Ingående moms.</span><span class="sxs-lookup"><span data-stu-id="f6c07-121">Otherwise, sales tax direction is Sales Tax Receivable.</span></span>

<span data-ttu-id="f6c07-122">Följande diagram visar regeln grafiskt.</span><span class="sxs-lookup"><span data-stu-id="f6c07-122">The following diagram illustrates the rule graphically.</span></span>

![Momsriktningsmöjligheter för projektkonton](media/Sales-Tax-Direction-Vendor.jpg)

### <a name="account-type-is-vendor"></a><span data-ttu-id="f6c07-124">Kontotypen är leverantör</span><span class="sxs-lookup"><span data-stu-id="f6c07-124">Account type is Vendor</span></span>

<span data-ttu-id="f6c07-125">Om en verifikation har en journalrad där kontotypen är **leverantör**, använder alla journalrader i verifikationen samma momsriktning.</span><span class="sxs-lookup"><span data-stu-id="f6c07-125">If a voucher has journal line where the account type is **Vendor**, all the journal lines in the voucher apply the same tax direction.</span></span> <span data-ttu-id="f6c07-126">Följande poäng visar de möjliga momsriktningarna för leverantörskonton.</span><span class="sxs-lookup"><span data-stu-id="f6c07-126">The following points show the possible tax directions for vendor accounts.</span></span> 

<span data-ttu-id="f6c07-127">•   Om momskoden är importavgift är momsriktningen importavgift.</span><span class="sxs-lookup"><span data-stu-id="f6c07-127">•   If the sales tax code is use tax, then sales tax direction is Use Tax.</span></span>

<span data-ttu-id="f6c07-128">•   Om momskoden är momsbefriad är momsriktningen är skattefritt inköp.</span><span class="sxs-lookup"><span data-stu-id="f6c07-128">•   If the sales tax code is exempt tax, then sales tax direction is Tax Free Purchase.</span></span>

<span data-ttu-id="f6c07-129">•   Om momskoden är Inomeuropeisk moms är momsriktningen Utgående moms.</span><span class="sxs-lookup"><span data-stu-id="f6c07-129">•   If the sales tax code is intracom VAT, then sales tax direction is Sales Tax Payable.</span></span>

<span data-ttu-id="f6c07-130">•   Om momskoden är återfört tillägg moms är momsriktningen Utgående moms.</span><span class="sxs-lookup"><span data-stu-id="f6c07-130">•   If the sales tax code is reverse charge, then sales tax direction is Sales Tax Payable.</span></span>

<span data-ttu-id="f6c07-131">Annars är momsriktningen Ingående moms.</span><span class="sxs-lookup"><span data-stu-id="f6c07-131">Otherwise, sales tax direction is Sales Tax Receivable.</span></span>

<span data-ttu-id="f6c07-132">Följande diagram visar regeln grafiskt.</span><span class="sxs-lookup"><span data-stu-id="f6c07-132">The following diagram illustrates the rule graphically.</span></span>

![Momsriktningsmöjligheter för leverantörskonton](media/Sales-Tax-Direction-Vendor.jpg)

### <a name="account-type-is-customer"></a><span data-ttu-id="f6c07-134">Kontotyp är kund</span><span class="sxs-lookup"><span data-stu-id="f6c07-134">Account type is Customer</span></span>

<span data-ttu-id="f6c07-135">Om en verifikation har en journalrad där kontotypen är **kund**, använder alla journalrader i verifikationen samma momsriktning.</span><span class="sxs-lookup"><span data-stu-id="f6c07-135">If a voucher has journal line where the account type is **Customer**, all the journal lines in the voucher apply the same tax direction.</span></span> <span data-ttu-id="f6c07-136">Följande poäng visar de möjliga momsriktningarna för kundkonton.</span><span class="sxs-lookup"><span data-stu-id="f6c07-136">The following points show the possible tax directions for customer accounts.</span></span>

<span data-ttu-id="f6c07-137">•   Om momskoden är momsbefriad är momsriktningen är skattefritt inköp.</span><span class="sxs-lookup"><span data-stu-id="f6c07-137">•   If the sales tax code is exempt tax, then sales tax direction is Tax Free Purchase.</span></span>

<span data-ttu-id="f6c07-138">•   Om momskoden är Inomeuropeisk moms är momsriktningen Ingående moms.</span><span class="sxs-lookup"><span data-stu-id="f6c07-138">•   If the sales tax code is intracom VAT, then sales tax direction is Sales Tax Receivable.</span></span>

<span data-ttu-id="f6c07-139">•   Om momskoden är återfört tillägg moms är momsriktningen Ingående moms.</span><span class="sxs-lookup"><span data-stu-id="f6c07-139">•   If the sales tax code is reverse charge, then sales tax direction is Sales Tax Receivable.</span></span>

<span data-ttu-id="f6c07-140">Annars är momsriktningen Utgående moms.</span><span class="sxs-lookup"><span data-stu-id="f6c07-140">Otherwise, sales tax direction is Sales Tax Payable.</span></span>

<span data-ttu-id="f6c07-141">Följande diagram visar regeln grafiskt.</span><span class="sxs-lookup"><span data-stu-id="f6c07-141">The following diagram illustrates the rule graphically.</span></span>

![Momsriktningsmöjligheter för kundkonton](media/Sales-Tax-Direction-Customer.jpg)

### <a name="account-type-is-ledger"></a><span data-ttu-id="f6c07-143">Kontotypen är Redovisning</span><span class="sxs-lookup"><span data-stu-id="f6c07-143">Account type is Ledger</span></span>

<span data-ttu-id="f6c07-144">Följande illustration visar den regel som gäller när en verifikation bara har journalrader där kontotypen är **redovisning**.</span><span class="sxs-lookup"><span data-stu-id="f6c07-144">The following illustration shows the rule that applies when a voucher has only journal lines where the account type is **Ledger**.</span></span> <span data-ttu-id="f6c07-145">Följande poäng visar de möjliga momsriktningarna för redovisningskonton.</span><span class="sxs-lookup"><span data-stu-id="f6c07-145">The following points show the possible tax directions for ledger accounts.</span></span>

<span data-ttu-id="f6c07-146">•   Om momskoden är importavgift är momsriktningen importavgift.</span><span class="sxs-lookup"><span data-stu-id="f6c07-146">•   If the sales tax code is use tax, then sales tax direction is Use Tax.</span></span>

<span data-ttu-id="f6c07-147">•   Om momskoden är momsbefriad är momsriktningen är skattefritt inköp.</span><span class="sxs-lookup"><span data-stu-id="f6c07-147">•   If the sales tax code is exempt tax, then sales tax direction is Tax Free Purchase.</span></span>

<span data-ttu-id="f6c07-148">Annars, om journalbeloppet är debet (positivt), är momsriktningen för Ingående moms. Om journalbeloppet är kredit (negativ), är momsriktningen Utgående moms.</span><span class="sxs-lookup"><span data-stu-id="f6c07-148">Otherwise, if the journal amount is debit (positive) ,sales tax direction is Sales Tax Receivable; if the journal amount is credit (negative) ,sales tax direction is Sales Tax Payable.</span></span>

<span data-ttu-id="f6c07-149">Följande diagram visar regeln grafiskt.</span><span class="sxs-lookup"><span data-stu-id="f6c07-149">The following diagram illustrates the rule graphically.</span></span>

![Momsriktningsmöjligheter för redovisningskonton](media/Sales-Tax-Direction-Ledger.jpg)

#### <a name="override-the-sales-tax-direction"></a><span data-ttu-id="f6c07-151">Åsidosätt momsriktningen</span><span class="sxs-lookup"><span data-stu-id="f6c07-151">Override the sales tax direction</span></span>

<span data-ttu-id="f6c07-152">Du kan åsidosätta momsriktningen när verifikationen bara innehåller rader där kontotypen är **redovisning**.</span><span class="sxs-lookup"><span data-stu-id="f6c07-152">You can override the sales tax direction when the voucher contains only lines where the account type is **Ledger**.</span></span>

<span data-ttu-id="f6c07-153">Gå till **Redovisning \> Kontoplan \> Konton \> Huvudkonton** och välj snabbfliken **Juridisk person åsidosätter**.</span><span class="sxs-lookup"><span data-stu-id="f6c07-153">Go to **General ledger \> Chart of accounts \> Accounts \> Main accounts**, and select the **Legal entity overrides** FastTab.</span></span>

## <a name="determine-the-sales-tax-amount"></a><span data-ttu-id="f6c07-154">Bestämma momsbelopp</span><span class="sxs-lookup"><span data-stu-id="f6c07-154">Determine the sales tax amount</span></span>

<span data-ttu-id="f6c07-155">I det här avsnittet beskrivs hur tecknet för momsbelopp beräknas.</span><span class="sxs-lookup"><span data-stu-id="f6c07-155">This section describes how the sales tax amount sign is calculated.</span></span>

![Sidan momstransaktioner](media/sales-tax-amount-sign.jpg)

<span data-ttu-id="f6c07-157">I följande tabell visas den allmänna regeln för bestämning av momsbelopp i det tillfälliga momsregistret.</span><span class="sxs-lookup"><span data-stu-id="f6c07-157">The following table shows the generic rule for determining the sign of sales tax amounts in the temporary sales tax table.</span></span>

| <span data-ttu-id="f6c07-158">Journalradsbelopp</span><span class="sxs-lookup"><span data-stu-id="f6c07-158">Journal line amount</span></span> | <span data-ttu-id="f6c07-159">Momsriktning</span><span class="sxs-lookup"><span data-stu-id="f6c07-159">Sales tax direction</span></span>  | <span data-ttu-id="f6c07-160">Momsbelopptecken</span><span class="sxs-lookup"><span data-stu-id="f6c07-160">Sales tax amount sign</span></span> |
|---------------------|----------------------|-----------------------|
| <span data-ttu-id="f6c07-161">Positiva</span><span class="sxs-lookup"><span data-stu-id="f6c07-161">Positive</span></span>            | <span data-ttu-id="f6c07-162">Ingående moms</span><span class="sxs-lookup"><span data-stu-id="f6c07-162">Sales Tax Receivable</span></span> | <span data-ttu-id="f6c07-163">Positiva</span><span class="sxs-lookup"><span data-stu-id="f6c07-163">Positive</span></span>              |
| <span data-ttu-id="f6c07-164">Positiva</span><span class="sxs-lookup"><span data-stu-id="f6c07-164">Positive</span></span>            | <span data-ttu-id="f6c07-165">Utgående moms</span><span class="sxs-lookup"><span data-stu-id="f6c07-165">Sales Tax Payable</span></span>    | <span data-ttu-id="f6c07-166">Negativa</span><span class="sxs-lookup"><span data-stu-id="f6c07-166">Negative</span></span>              |
| <span data-ttu-id="f6c07-167">Negativa</span><span class="sxs-lookup"><span data-stu-id="f6c07-167">Negative</span></span>            | <span data-ttu-id="f6c07-168">Ingående moms</span><span class="sxs-lookup"><span data-stu-id="f6c07-168">Sales Tax Receivable</span></span> | <span data-ttu-id="f6c07-169">Negativa</span><span class="sxs-lookup"><span data-stu-id="f6c07-169">Negative</span></span>              |
| <span data-ttu-id="f6c07-170">Negativa</span><span class="sxs-lookup"><span data-stu-id="f6c07-170">Negative</span></span>            | <span data-ttu-id="f6c07-171">Utgående moms</span><span class="sxs-lookup"><span data-stu-id="f6c07-171">Sales Tax Payable</span></span>    | <span data-ttu-id="f6c07-172">Positiva</span><span class="sxs-lookup"><span data-stu-id="f6c07-172">Positive</span></span>              |

<span data-ttu-id="f6c07-173">Det finns en särskild regel för verifikationer som bara har raderna **Projekt** eller **Redovisning** när en moms grupp eller artikelmomsgrupp har valts på raden **Redovisning**.</span><span class="sxs-lookup"><span data-stu-id="f6c07-173">There is a special rule for vouchers that have only **Project** or **Ledger** lines, when a sales tax group or item sales tax group is selected on the **Ledger** line.</span></span> <span data-ttu-id="f6c07-174">Den här regeln styrs genom aktivering av oberoende momsberäkningsfunktion för allmänna journaler.</span><span class="sxs-lookup"><span data-stu-id="f6c07-174">This rule is controlled by Enable independent sales tax calculation feature for general journals.</span></span> <span data-ttu-id="f6c07-175">När den här funktionen inaktiveras använder momsbeloppet för raden **redovisning** debet-/kreditriktningen för raden **projekt**.</span><span class="sxs-lookup"><span data-stu-id="f6c07-175">When this feature is turned off, the tax amount of the **Ledger** line uses the debit/credit direction of the **Project** line.</span></span> <span data-ttu-id="f6c07-176">När den här funktionen aktiveras använder momsbeloppet för raden **redovisning** debet-/kreditriktningen.</span><span class="sxs-lookup"><span data-stu-id="f6c07-176">When the feature is turned on, the tax amount of the **Ledger** line uses its own debit/credit direction.</span></span> <span data-ttu-id="f6c07-177">I följande tabeller visas regeln för varje scenario.</span><span class="sxs-lookup"><span data-stu-id="f6c07-177">The following tables show the rule for each scenario.</span></span> 

<span data-ttu-id="f6c07-178">**Regel när funktionen är aktiverad**</span><span class="sxs-lookup"><span data-stu-id="f6c07-178">**Rule when the feature is turned on**</span></span>

| <span data-ttu-id="f6c07-179">Journalradbelopp för projekt</span><span class="sxs-lookup"><span data-stu-id="f6c07-179">Journal line amount of project</span></span> | <span data-ttu-id="f6c07-180">Momsriktning</span><span class="sxs-lookup"><span data-stu-id="f6c07-180">Sales tax direction</span></span>  | <span data-ttu-id="f6c07-181">Momsbelopptecken</span><span class="sxs-lookup"><span data-stu-id="f6c07-181">Sales tax amount sign</span></span> |
|--------------------------------|----------------------|-----------------------|
| <span data-ttu-id="f6c07-182">Positiva</span><span class="sxs-lookup"><span data-stu-id="f6c07-182">Positive</span></span>                       | <span data-ttu-id="f6c07-183">Ingående moms</span><span class="sxs-lookup"><span data-stu-id="f6c07-183">Sales Tax Receivable</span></span> | <span data-ttu-id="f6c07-184">Positiva</span><span class="sxs-lookup"><span data-stu-id="f6c07-184">Positive</span></span>              |
| <span data-ttu-id="f6c07-185">Negativa</span><span class="sxs-lookup"><span data-stu-id="f6c07-185">Negative</span></span>                       | <span data-ttu-id="f6c07-186">Ingående moms</span><span class="sxs-lookup"><span data-stu-id="f6c07-186">Sales Tax Receivable</span></span> | <span data-ttu-id="f6c07-187">Negativa</span><span class="sxs-lookup"><span data-stu-id="f6c07-187">Negative</span></span>              |

<span data-ttu-id="f6c07-188">**Regel när funktionen är inaktiverad**</span><span class="sxs-lookup"><span data-stu-id="f6c07-188">**Rule when the feature is turned off**</span></span>

| <span data-ttu-id="f6c07-189">Journalradbelopp för redovisning</span><span class="sxs-lookup"><span data-stu-id="f6c07-189">Journal line amount of ledger</span></span>  | <span data-ttu-id="f6c07-190">Momsriktning</span><span class="sxs-lookup"><span data-stu-id="f6c07-190">Sales tax direction</span></span>  | <span data-ttu-id="f6c07-191">Momsbelopptecken</span><span class="sxs-lookup"><span data-stu-id="f6c07-191">Sales tax amount sign</span></span> |
|--------------------------------|----------------------|-----------------------|
| <span data-ttu-id="f6c07-192">Positiva</span><span class="sxs-lookup"><span data-stu-id="f6c07-192">Positive</span></span>                       | <span data-ttu-id="f6c07-193">Ingående moms</span><span class="sxs-lookup"><span data-stu-id="f6c07-193">Sales Tax Receivable</span></span> | <span data-ttu-id="f6c07-194">Positiva</span><span class="sxs-lookup"><span data-stu-id="f6c07-194">Positive</span></span>              |
| <span data-ttu-id="f6c07-195">Negativa</span><span class="sxs-lookup"><span data-stu-id="f6c07-195">Negative</span></span>                       | <span data-ttu-id="f6c07-196">Ingående moms</span><span class="sxs-lookup"><span data-stu-id="f6c07-196">Sales Tax Receivable</span></span> | <span data-ttu-id="f6c07-197">Negativa</span><span class="sxs-lookup"><span data-stu-id="f6c07-197">Negative</span></span>              |

## <a name="determine-the-sales-tax-amount-and-account-on-the-voucher"></a><span data-ttu-id="f6c07-198">Bestäm momsbeloppet och kontot på verifikationen</span><span class="sxs-lookup"><span data-stu-id="f6c07-198">Determine the sales tax amount and account on the voucher</span></span>

<span data-ttu-id="f6c07-199">När du bokför moms hämtas huvudkontot från profilen för redovisningens bokföringsgrupprofil.</span><span class="sxs-lookup"><span data-stu-id="f6c07-199">When you post sales taxes, the main account is retrieved from the ledger posting group profile.</span></span> <span data-ttu-id="f6c07-200">När moms inkommer använder systemet det konto för ingående moms som anges i profilen.</span><span class="sxs-lookup"><span data-stu-id="f6c07-200">When sales taxes are receivable, the system uses the Sales Tax Receivable account that is specified in the profile.</span></span> <span data-ttu-id="f6c07-201">För moms som ska betalas använder systemet det konto för utgående moms som anges i profilen.</span><span class="sxs-lookup"><span data-stu-id="f6c07-201">For sales taxes that are payable, the system uses Sales Tax Payable account that is specified in the profile.</span></span>

<span data-ttu-id="f6c07-202">Tabellen nedan visar den allmänna regeln.</span><span class="sxs-lookup"><span data-stu-id="f6c07-202">The following table shows the generic rule.</span></span>

| <span data-ttu-id="f6c07-203">Momsriktning</span><span class="sxs-lookup"><span data-stu-id="f6c07-203">Sales tax direction</span></span>  | <span data-ttu-id="f6c07-204">Momsbelopptecken</span><span class="sxs-lookup"><span data-stu-id="f6c07-204">Sales tax amount sign</span></span> | <span data-ttu-id="f6c07-205">Momskonto</span><span class="sxs-lookup"><span data-stu-id="f6c07-205">Sales tax account</span></span>      | <span data-ttu-id="f6c07-206">Belopp på verifikationen</span><span class="sxs-lookup"><span data-stu-id="f6c07-206">Amount on voucher</span></span> |
|----------------------|-----------------------|------------------------|-------------------|
| <span data-ttu-id="f6c07-207">Ingående moms</span><span class="sxs-lookup"><span data-stu-id="f6c07-207">Sales Tax Receivable</span></span> | <span data-ttu-id="f6c07-208">Positiva</span><span class="sxs-lookup"><span data-stu-id="f6c07-208">Positive</span></span>              | <span data-ttu-id="f6c07-209">Konto för ingående moms</span><span class="sxs-lookup"><span data-stu-id="f6c07-209">Tax Receivable Account</span></span> | <span data-ttu-id="f6c07-210">Positiv (Debet)</span><span class="sxs-lookup"><span data-stu-id="f6c07-210">Positive (Debit)</span></span>  |
| <span data-ttu-id="f6c07-211">Ingående moms</span><span class="sxs-lookup"><span data-stu-id="f6c07-211">Sales Tax Receivable</span></span> | <span data-ttu-id="f6c07-212">Negativa</span><span class="sxs-lookup"><span data-stu-id="f6c07-212">Negative</span></span>              | <span data-ttu-id="f6c07-213">Konto för ingående moms</span><span class="sxs-lookup"><span data-stu-id="f6c07-213">Tax Receivable Account</span></span> | <span data-ttu-id="f6c07-214">Negativ (kredit)</span><span class="sxs-lookup"><span data-stu-id="f6c07-214">Negative(Credit)</span></span>  |
| <span data-ttu-id="f6c07-215">Utgående moms</span><span class="sxs-lookup"><span data-stu-id="f6c07-215">Sales Tax Payable</span></span>    | <span data-ttu-id="f6c07-216">Positiva</span><span class="sxs-lookup"><span data-stu-id="f6c07-216">Positive</span></span>              | <span data-ttu-id="f6c07-217">Konto för utgående moms</span><span class="sxs-lookup"><span data-stu-id="f6c07-217">Tax Payable Account</span></span>    | <span data-ttu-id="f6c07-218">Negativ (kredit)</span><span class="sxs-lookup"><span data-stu-id="f6c07-218">Negative(Credit)</span></span>  |
| <span data-ttu-id="f6c07-219">Utgående moms</span><span class="sxs-lookup"><span data-stu-id="f6c07-219">Sales Tax Payable</span></span>    | <span data-ttu-id="f6c07-220">Negativa</span><span class="sxs-lookup"><span data-stu-id="f6c07-220">Negative</span></span>              | <span data-ttu-id="f6c07-221">Konto för utgående moms</span><span class="sxs-lookup"><span data-stu-id="f6c07-221">Tax Payable Account</span></span>    | <span data-ttu-id="f6c07-222">Positiv (Debet)</span><span class="sxs-lookup"><span data-stu-id="f6c07-222">Positive (Debit)</span></span>  |
