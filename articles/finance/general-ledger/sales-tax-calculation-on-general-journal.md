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
ms.author: vstehman
ms.search.validFrom: 2019-08-14
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: dd1df355d39065d6959915cc916987d3c58b15a6
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/10/2019
ms.locfileid: "2570204"
---
# <a name="sales-tax-calculation-on-general-journal-lines"></a><span data-ttu-id="081b3-103">Momsberäkning för allmänna journalrader</span><span class="sxs-lookup"><span data-stu-id="081b3-103">Sales tax calculation on general journal lines</span></span>
[!include [banner](../includes/banner.md)]

<span data-ttu-id="081b3-104">Det här ämnet förklarar hur moms beräknas för olika typer av konton (leverantör, kund, redovisning och projekt) på allmänna journalrader.</span><span class="sxs-lookup"><span data-stu-id="081b3-104">This topic explains how sales taxes are calculated for different types of accounts (vendor, customer, ledger, and project) on general journal lines.</span></span>

<span data-ttu-id="081b3-105">Processen kan delas in i tre steg:</span><span class="sxs-lookup"><span data-stu-id="081b3-105">The process can be divided into three steps:</span></span>

- <span data-ttu-id="081b3-106">Bestämma momsriktningen.</span><span class="sxs-lookup"><span data-stu-id="081b3-106">Determine the sales tax direction.</span></span>

- <span data-ttu-id="081b3-107">Avgör vilket momsbelopp som ska lagras i ett tillfälligt momsregister.</span><span class="sxs-lookup"><span data-stu-id="081b3-107">Determine the sales tax amount that will be stored a temporary sales tax table.</span></span>

- <span data-ttu-id="081b3-108">Bestäm momsbeloppet och kontot på verifikationen.</span><span class="sxs-lookup"><span data-stu-id="081b3-108">Determine the sales tax amount and account on the voucher.</span></span>

## <a name="determine-the-sales-tax-direction"></a><span data-ttu-id="081b3-109">Bestämma momsriktningen</span><span class="sxs-lookup"><span data-stu-id="081b3-109">Determine the sales tax direction</span></span>

<span data-ttu-id="081b3-110">Hur momsriktningen bestäms beror på typen av konto i verifikationen.</span><span class="sxs-lookup"><span data-stu-id="081b3-110">The way that the sales tax direction is determined depends on the type of account in the voucher.</span></span> <span data-ttu-id="081b3-111">Momsriktningen bestäms av kombinationen av kontotypen och momskoden.</span><span class="sxs-lookup"><span data-stu-id="081b3-111">The sales tax direction is determined by the combination of account type and sales tax code.</span></span> <span data-ttu-id="081b3-112">De följande avsnitten är möjligheterna i mer detaljerat.</span><span class="sxs-lookup"><span data-stu-id="081b3-112">The following sections the possibilities in more detail.</span></span> 

### <a name="account-type-is-project"></a><span data-ttu-id="081b3-113">Kontotyp är projekt</span><span class="sxs-lookup"><span data-stu-id="081b3-113">Account type is Project</span></span>

<span data-ttu-id="081b3-114">Om en verifikation har en journalrad där kontotypen är **projekt**, använder alla journalrader i verifikationen samma momsriktning.</span><span class="sxs-lookup"><span data-stu-id="081b3-114">If a voucher has journal line where the account type is **Project**, all the journal lines in the voucher apply the same tax direction.</span></span> <span data-ttu-id="081b3-115">På bilden nedan visas regeln.</span><span class="sxs-lookup"><span data-stu-id="081b3-115">The following illustration shows the rule.</span></span> <span data-ttu-id="081b3-116">Följande poäng visar de möjliga momsriktningarna för projektkonton.</span><span class="sxs-lookup"><span data-stu-id="081b3-116">The following points show the possible tax directions for project accounts.</span></span>

<span data-ttu-id="081b3-117">•   Om momskoden är importavgift är momsriktningen importavgift.</span><span class="sxs-lookup"><span data-stu-id="081b3-117">•   If the sales tax code is use tax, then sales tax direction is Use Tax.</span></span>

<span data-ttu-id="081b3-118">•   Om momskoden är momsbefriad är momsriktningen är skattefritt inköp.</span><span class="sxs-lookup"><span data-stu-id="081b3-118">•   If the sales tax code is exempt tax, then sales tax direction is Tax Free Purchase.</span></span>

<span data-ttu-id="081b3-119">•   Om momskoden är Inomeuropeisk moms är momsriktningen Utgående moms.</span><span class="sxs-lookup"><span data-stu-id="081b3-119">•   If the sales tax code is intracom VAT, then sales tax direction is Sales Tax Payable.</span></span>

<span data-ttu-id="081b3-120">•   Om momskoden är återfört tillägg moms är momsriktningen Utgående moms.</span><span class="sxs-lookup"><span data-stu-id="081b3-120">•   If the sales tax code is reverse charge, then sales tax direction is Sales Tax Payable.</span></span>

<span data-ttu-id="081b3-121">Annars är momsriktningen Ingående moms.</span><span class="sxs-lookup"><span data-stu-id="081b3-121">Otherwise, sales tax direction is Sales Tax Receivable.</span></span>

<span data-ttu-id="081b3-122">Följande diagram visar regeln grafiskt.</span><span class="sxs-lookup"><span data-stu-id="081b3-122">The following diagram illustrates the rule graphically.</span></span>

![Momsriktningsmöjligheter för projektkonton](media/Sales-Tax-Direction-Vendor.jpg)

### <a name="account-type-is-vendor"></a><span data-ttu-id="081b3-124">Kontotypen är leverantör</span><span class="sxs-lookup"><span data-stu-id="081b3-124">Account type is Vendor</span></span>

<span data-ttu-id="081b3-125">Om en verifikation har en journalrad där kontotypen är **leverantör**, använder alla journalrader i verifikationen samma momsriktning.</span><span class="sxs-lookup"><span data-stu-id="081b3-125">If a voucher has journal line where the account type is **Vendor**, all the journal lines in the voucher apply the same tax direction.</span></span> <span data-ttu-id="081b3-126">Följande poäng visar de möjliga momsriktningarna för leverantörskonton.</span><span class="sxs-lookup"><span data-stu-id="081b3-126">The following points show the possible tax directions for vendor accounts.</span></span> 

<span data-ttu-id="081b3-127">•   Om momskoden är momsbefriad är momsriktningen är skattefritt inköp.</span><span class="sxs-lookup"><span data-stu-id="081b3-127">•   If the sales tax code is exempt tax, then sales tax direction is Tax Free Purchase.</span></span>

<span data-ttu-id="081b3-128">•   Om momskoden är Inomeuropeisk moms är momsriktningen Ingående moms.</span><span class="sxs-lookup"><span data-stu-id="081b3-128">•   If the sales tax code is intracom VAT, then sales tax direction is Sales Tax Receivable.</span></span>

<span data-ttu-id="081b3-129">•   Om momskoden är återfört tillägg moms är momsriktningen Ingående moms.</span><span class="sxs-lookup"><span data-stu-id="081b3-129">•   If the sales tax code is reverse charge, then sales tax direction is Sales Tax Receivable.</span></span>


<span data-ttu-id="081b3-130">Annars är momsriktningen Utgående moms.</span><span class="sxs-lookup"><span data-stu-id="081b3-130">Otherwise, sales tax direction is Sales Tax Payable.</span></span>

<span data-ttu-id="081b3-131">Följande diagram visar regeln grafiskt.</span><span class="sxs-lookup"><span data-stu-id="081b3-131">The following diagram illustrates the rule graphically.</span></span>

![Momsriktningsmöjligheter för leverantörskonton](media/Sales-Tax-Direction-Vendor.jpg)

### <a name="account-type-is-customer"></a><span data-ttu-id="081b3-133">Kontotyp är kund</span><span class="sxs-lookup"><span data-stu-id="081b3-133">Account type is Customer</span></span>

<span data-ttu-id="081b3-134">Om en verifikation har en journalrad där kontotypen är **kund**, använder alla journalrader i verifikationen samma momsriktning.</span><span class="sxs-lookup"><span data-stu-id="081b3-134">If a voucher has journal line where the account type is **Customer**, all the journal lines in the voucher apply the same tax direction.</span></span> <span data-ttu-id="081b3-135">Följande poäng visar de möjliga momsriktningarna för kundkonton.</span><span class="sxs-lookup"><span data-stu-id="081b3-135">The following points show the possible tax directions for customer accounts.</span></span>

<span data-ttu-id="081b3-136">•   Om momskoden är importavgift är momsriktningen importavgift.</span><span class="sxs-lookup"><span data-stu-id="081b3-136">•   If the sales tax code is use tax, then sales tax direction is Use Tax.</span></span>

<span data-ttu-id="081b3-137">•   Om momskoden är momsbefriad är momsriktningen är skattefritt inköp.</span><span class="sxs-lookup"><span data-stu-id="081b3-137">•   If the sales tax code is exempt tax, then sales tax direction is Tax Free Purchase.</span></span>

<span data-ttu-id="081b3-138">•   Om momskoden är Inomeuropeisk moms är momsriktningen Utgående moms.</span><span class="sxs-lookup"><span data-stu-id="081b3-138">•   If the sales tax code is intracom VAT, then sales tax direction is Sales Tax Payable.</span></span>

<span data-ttu-id="081b3-139">•   Om momskoden är återfört tillägg moms är momsriktningen Utgående moms.</span><span class="sxs-lookup"><span data-stu-id="081b3-139">•   If the sales tax code is reverse charge, then sales tax direction is Sales Tax Payable.</span></span>

<span data-ttu-id="081b3-140">Annars är momsriktningen Ingående moms.</span><span class="sxs-lookup"><span data-stu-id="081b3-140">Otherwise, sales tax direction is Sales Tax Receivable.</span></span>

<span data-ttu-id="081b3-141">Följande diagram visar regeln grafiskt.</span><span class="sxs-lookup"><span data-stu-id="081b3-141">The following diagram illustrates the rule graphically.</span></span>

![Momsriktningsmöjligheter för kundkonton](media/Sales-Tax-Direction-Customer.jpg)

### <a name="account-type-is-ledger"></a><span data-ttu-id="081b3-143">Kontotypen är Redovisning</span><span class="sxs-lookup"><span data-stu-id="081b3-143">Account type is Ledger</span></span>

<span data-ttu-id="081b3-144">Följande illustration visar den regel som gäller när en verifikation bara har journalrader där kontotypen är **redovisning**.</span><span class="sxs-lookup"><span data-stu-id="081b3-144">The following illustration shows the rule that applies when a voucher has only journal lines where the account type is **Ledger**.</span></span> <span data-ttu-id="081b3-145">Följande poäng visar de möjliga momsriktningarna för redovisningskonton.</span><span class="sxs-lookup"><span data-stu-id="081b3-145">The following points show the possible tax directions for ledger accounts.</span></span>

<span data-ttu-id="081b3-146">•   Om momskoden är importavgift är momsriktningen importavgift.</span><span class="sxs-lookup"><span data-stu-id="081b3-146">•   If the sales tax code is use tax, then sales tax direction is Use Tax.</span></span>

<span data-ttu-id="081b3-147">•   Om momskoden är momsbefriad är momsriktningen är skattefritt inköp.</span><span class="sxs-lookup"><span data-stu-id="081b3-147">•   If the sales tax code is exempt tax, then sales tax direction is Tax Free Purchase.</span></span>

<span data-ttu-id="081b3-148">Annars, om journalbeloppet är debet (positivt), är momsriktningen för Ingående moms. Om journalbeloppet är kredit (negativ), är momsriktningen Utgående moms.</span><span class="sxs-lookup"><span data-stu-id="081b3-148">Otherwise, if the journal amount is debit (positive) ,sales tax direction is Sales Tax Receivable; if the journal amount is credit (negative) ,sales tax direction is Sales Tax Payable.</span></span>

<span data-ttu-id="081b3-149">Följande diagram visar regeln grafiskt.</span><span class="sxs-lookup"><span data-stu-id="081b3-149">The following diagram illustrates the rule graphically.</span></span>

![Momsriktningsmöjligheter för redovisningskonton](media/Sales-Tax-Direction-Ledger.jpg)

#### <a name="override-the-sales-tax-direction"></a><span data-ttu-id="081b3-151">Åsidosätt momsriktningen</span><span class="sxs-lookup"><span data-stu-id="081b3-151">Override the sales tax direction</span></span>

<span data-ttu-id="081b3-152">Du kan åsidosätta momsriktningen när verifikationen bara innehåller rader där kontotypen är **redovisning**.</span><span class="sxs-lookup"><span data-stu-id="081b3-152">You can override the sales tax direction when the voucher contains only lines where the account type is **Ledger**.</span></span>

<span data-ttu-id="081b3-153">Gå till **Redovisning \> Kontoplan \> Konton \> Huvudkonton** och välj snabbfliken **Juridisk person åsidosätter**.</span><span class="sxs-lookup"><span data-stu-id="081b3-153">Go to **General ledger \> Chart of accounts \> Accounts \> Main accounts**, and select the **Legal entity overrides** FastTab.</span></span>

## <a name="determine-the-sales-tax-amount"></a><span data-ttu-id="081b3-154">Bestämma momsbelopp</span><span class="sxs-lookup"><span data-stu-id="081b3-154">Determine the sales tax amount</span></span>

<span data-ttu-id="081b3-155">I det här avsnittet beskrivs hur tecknet för momsbelopp beräknas.</span><span class="sxs-lookup"><span data-stu-id="081b3-155">This section describes how the sales tax amount sign is calculated.</span></span>

![Sidan momstransaktioner](media/sales-tax-amount-sign.jpg)

<span data-ttu-id="081b3-157">I följande tabell visas den allmänna regeln för bestämning av momsbelopp i det tillfälliga momsregistret.</span><span class="sxs-lookup"><span data-stu-id="081b3-157">The following table shows the generic rule for determining the sign of sales tax amounts in the temporary sales tax table.</span></span>

| <span data-ttu-id="081b3-158">Journalradsbelopp</span><span class="sxs-lookup"><span data-stu-id="081b3-158">Journal line amount</span></span> | <span data-ttu-id="081b3-159">Momsriktning</span><span class="sxs-lookup"><span data-stu-id="081b3-159">Sales tax direction</span></span>  | <span data-ttu-id="081b3-160">Momsbelopptecken</span><span class="sxs-lookup"><span data-stu-id="081b3-160">Sales tax amount sign</span></span> |
|---------------------|----------------------|-----------------------|
| <span data-ttu-id="081b3-161">Positiva</span><span class="sxs-lookup"><span data-stu-id="081b3-161">Positive</span></span>            | <span data-ttu-id="081b3-162">Ingående moms</span><span class="sxs-lookup"><span data-stu-id="081b3-162">Sales Tax Receivable</span></span> | <span data-ttu-id="081b3-163">Positiva</span><span class="sxs-lookup"><span data-stu-id="081b3-163">Positive</span></span>              |
| <span data-ttu-id="081b3-164">Positiva</span><span class="sxs-lookup"><span data-stu-id="081b3-164">Positive</span></span>            | <span data-ttu-id="081b3-165">Utgående moms</span><span class="sxs-lookup"><span data-stu-id="081b3-165">Sales Tax Payable</span></span>    | <span data-ttu-id="081b3-166">Negativa</span><span class="sxs-lookup"><span data-stu-id="081b3-166">Negative</span></span>              |
| <span data-ttu-id="081b3-167">Negativa</span><span class="sxs-lookup"><span data-stu-id="081b3-167">Negative</span></span>            | <span data-ttu-id="081b3-168">Ingående moms</span><span class="sxs-lookup"><span data-stu-id="081b3-168">Sales Tax Receivable</span></span> | <span data-ttu-id="081b3-169">Negativa</span><span class="sxs-lookup"><span data-stu-id="081b3-169">Negative</span></span>              |
| <span data-ttu-id="081b3-170">Negativa</span><span class="sxs-lookup"><span data-stu-id="081b3-170">Negative</span></span>            | <span data-ttu-id="081b3-171">Utgående moms</span><span class="sxs-lookup"><span data-stu-id="081b3-171">Sales Tax Payable</span></span>    | <span data-ttu-id="081b3-172">Positiva</span><span class="sxs-lookup"><span data-stu-id="081b3-172">Positive</span></span>              |

<span data-ttu-id="081b3-173">Det finns en särskild regel för verifikationer som bara har raderna **Projekt** eller **Redovisning** när en moms grupp eller artikelmomsgrupp har valts på raden **Redovisning**.</span><span class="sxs-lookup"><span data-stu-id="081b3-173">There is a special rule for vouchers that have only **Project** or **Ledger** lines, when a sales tax group or item sales tax group is selected on the **Ledger** line.</span></span> <span data-ttu-id="081b3-174">Den här regeln styrs genom aktivering av oberoende momsberäkningsfunktion för allmänna journaler.</span><span class="sxs-lookup"><span data-stu-id="081b3-174">This rule is controlled by Enable independent sales tax calculation feature for general journals.</span></span> <span data-ttu-id="081b3-175">När den här funktionen inaktiveras använder momsbeloppet för raden **redovisning** debet-/kreditriktningen för raden **projekt**.</span><span class="sxs-lookup"><span data-stu-id="081b3-175">When this feature is turned off, the tax amount of the **Ledger** line uses the debit/credit direction of the **Project** line.</span></span> <span data-ttu-id="081b3-176">När den här funktionen aktiveras använder momsbeloppet för raden **redovisning** debet-/kreditriktningen.</span><span class="sxs-lookup"><span data-stu-id="081b3-176">When the feature is turned on, the tax amount of the **Ledger** line uses its own debit/credit direction.</span></span> <span data-ttu-id="081b3-177">I följande tabeller visas regeln för varje scenario.</span><span class="sxs-lookup"><span data-stu-id="081b3-177">The following tables show the rule for each scenario.</span></span> 

<span data-ttu-id="081b3-178">**Regel när funktionen är aktiverad**</span><span class="sxs-lookup"><span data-stu-id="081b3-178">**Rule when the feature is turned on**</span></span>

| <span data-ttu-id="081b3-179">Journalradbelopp för projekt</span><span class="sxs-lookup"><span data-stu-id="081b3-179">Journal line amount of project</span></span> | <span data-ttu-id="081b3-180">Momsriktning</span><span class="sxs-lookup"><span data-stu-id="081b3-180">Sales tax direction</span></span>  | <span data-ttu-id="081b3-181">Momsbelopptecken</span><span class="sxs-lookup"><span data-stu-id="081b3-181">Sales tax amount sign</span></span> |
|--------------------------------|----------------------|-----------------------|
| <span data-ttu-id="081b3-182">Positiva</span><span class="sxs-lookup"><span data-stu-id="081b3-182">Positive</span></span>                       | <span data-ttu-id="081b3-183">Ingående moms</span><span class="sxs-lookup"><span data-stu-id="081b3-183">Sales Tax Receivable</span></span> | <span data-ttu-id="081b3-184">Positiva</span><span class="sxs-lookup"><span data-stu-id="081b3-184">Positive</span></span>              |
| <span data-ttu-id="081b3-185">Negativa</span><span class="sxs-lookup"><span data-stu-id="081b3-185">Negative</span></span>                       | <span data-ttu-id="081b3-186">Ingående moms</span><span class="sxs-lookup"><span data-stu-id="081b3-186">Sales Tax Receivable</span></span> | <span data-ttu-id="081b3-187">Negativa</span><span class="sxs-lookup"><span data-stu-id="081b3-187">Negative</span></span>              |

<span data-ttu-id="081b3-188">**Regel när funktionen är inaktiverad**</span><span class="sxs-lookup"><span data-stu-id="081b3-188">**Rule when the feature is turned off**</span></span>

| <span data-ttu-id="081b3-189">Journalradbelopp för redovisning</span><span class="sxs-lookup"><span data-stu-id="081b3-189">Journal line amount of ledger</span></span>  | <span data-ttu-id="081b3-190">Momsriktning</span><span class="sxs-lookup"><span data-stu-id="081b3-190">Sales tax direction</span></span>  | <span data-ttu-id="081b3-191">Momsbelopptecken</span><span class="sxs-lookup"><span data-stu-id="081b3-191">Sales tax amount sign</span></span> |
|--------------------------------|----------------------|-----------------------|
| <span data-ttu-id="081b3-192">Positiva</span><span class="sxs-lookup"><span data-stu-id="081b3-192">Positive</span></span>                       | <span data-ttu-id="081b3-193">Ingående moms</span><span class="sxs-lookup"><span data-stu-id="081b3-193">Sales Tax Receivable</span></span> | <span data-ttu-id="081b3-194">Positiva</span><span class="sxs-lookup"><span data-stu-id="081b3-194">Positive</span></span>              |
| <span data-ttu-id="081b3-195">Negativa</span><span class="sxs-lookup"><span data-stu-id="081b3-195">Negative</span></span>                       | <span data-ttu-id="081b3-196">Ingående moms</span><span class="sxs-lookup"><span data-stu-id="081b3-196">Sales Tax Receivable</span></span> | <span data-ttu-id="081b3-197">Negativa</span><span class="sxs-lookup"><span data-stu-id="081b3-197">Negative</span></span>              |

## <a name="determine-the-sales-tax-amount-and-account-on-the-voucher"></a><span data-ttu-id="081b3-198">Bestäm momsbeloppet och kontot på verifikationen</span><span class="sxs-lookup"><span data-stu-id="081b3-198">Determine the sales tax amount and account on the voucher</span></span>

<span data-ttu-id="081b3-199">När du bokför moms hämtas huvudkontot från profilen för redovisningens bokföringsgrupprofil.</span><span class="sxs-lookup"><span data-stu-id="081b3-199">When you post sales taxes, the main account is retrieved from the ledger posting group profile.</span></span> <span data-ttu-id="081b3-200">När moms inkommer använder systemet det konto för ingående moms som anges i profilen.</span><span class="sxs-lookup"><span data-stu-id="081b3-200">When sales taxes are receivable, the system uses the Sales Tax Receivable account that is specified in the profile.</span></span> <span data-ttu-id="081b3-201">För moms som ska betalas använder systemet det konto för utgående moms som anges i profilen.</span><span class="sxs-lookup"><span data-stu-id="081b3-201">For sales taxes that are payable, the system uses Sales Tax Payable account that is specified in the profile.</span></span>

<span data-ttu-id="081b3-202">Tabellen nedan visar den allmänna regeln.</span><span class="sxs-lookup"><span data-stu-id="081b3-202">The following table shows the generic rule.</span></span>

| <span data-ttu-id="081b3-203">Momsriktning</span><span class="sxs-lookup"><span data-stu-id="081b3-203">Sales tax direction</span></span>  | <span data-ttu-id="081b3-204">Momsbelopptecken</span><span class="sxs-lookup"><span data-stu-id="081b3-204">Sales tax amount sign</span></span> | <span data-ttu-id="081b3-205">Momskonto</span><span class="sxs-lookup"><span data-stu-id="081b3-205">Sales tax account</span></span>      | <span data-ttu-id="081b3-206">Belopp på verifikationen</span><span class="sxs-lookup"><span data-stu-id="081b3-206">Amount on voucher</span></span> |
|----------------------|-----------------------|------------------------|-------------------|
| <span data-ttu-id="081b3-207">Ingående moms</span><span class="sxs-lookup"><span data-stu-id="081b3-207">Sales Tax Receivable</span></span> | <span data-ttu-id="081b3-208">Positiva</span><span class="sxs-lookup"><span data-stu-id="081b3-208">Positive</span></span>              | <span data-ttu-id="081b3-209">Konto för ingående moms</span><span class="sxs-lookup"><span data-stu-id="081b3-209">Tax Receivable Account</span></span> | <span data-ttu-id="081b3-210">Positiv (Debet)</span><span class="sxs-lookup"><span data-stu-id="081b3-210">Positive (Debit)</span></span>  |
| <span data-ttu-id="081b3-211">Ingående moms</span><span class="sxs-lookup"><span data-stu-id="081b3-211">Sales Tax Receivable</span></span> | <span data-ttu-id="081b3-212">Negativa</span><span class="sxs-lookup"><span data-stu-id="081b3-212">Negative</span></span>              | <span data-ttu-id="081b3-213">Konto för ingående moms</span><span class="sxs-lookup"><span data-stu-id="081b3-213">Tax Receivable Account</span></span> | <span data-ttu-id="081b3-214">Negativ (kredit)</span><span class="sxs-lookup"><span data-stu-id="081b3-214">Negative(Credit)</span></span>  |
| <span data-ttu-id="081b3-215">Utgående moms</span><span class="sxs-lookup"><span data-stu-id="081b3-215">Sales Tax Payable</span></span>    | <span data-ttu-id="081b3-216">Positiva</span><span class="sxs-lookup"><span data-stu-id="081b3-216">Positive</span></span>              | <span data-ttu-id="081b3-217">Konto för utgående moms</span><span class="sxs-lookup"><span data-stu-id="081b3-217">Tax Payable Account</span></span>    | <span data-ttu-id="081b3-218">Negativ (kredit)</span><span class="sxs-lookup"><span data-stu-id="081b3-218">Negative(Credit)</span></span>  |
| <span data-ttu-id="081b3-219">Utgående moms</span><span class="sxs-lookup"><span data-stu-id="081b3-219">Sales Tax Payable</span></span>    | <span data-ttu-id="081b3-220">Negativa</span><span class="sxs-lookup"><span data-stu-id="081b3-220">Negative</span></span>              | <span data-ttu-id="081b3-221">Konto för utgående moms</span><span class="sxs-lookup"><span data-stu-id="081b3-221">Tax Payable Account</span></span>    | <span data-ttu-id="081b3-222">Positiv (Debet)</span><span class="sxs-lookup"><span data-stu-id="081b3-222">Positive (Debit)</span></span>  |
