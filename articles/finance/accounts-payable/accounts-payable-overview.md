---
title: Konfigurera leverantörsreskontra – översikt
description: Det här avsnittet innehåller en beskrivning av de sidor som används för att ställa in grundläggande och valfria funktion för Leverantörsreskontra. Även inställningsstegen som du måste vidta innan du börjar ställa in Leverantörsreskontra beskrivs.
author: abruer
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankAccountTable, DeliveryMode, PaymTerm, VendGroup, VendParameters, VendPaymMode, VendTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 24671
ms.assetid: 82561fe7-b2d6-464c-9347-79d0ce0f9743
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a1ca94bf4a6eb9f65d7302c2071fd108be752764
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2180043"
---
# <a name="configure-accounts-payable-overview"></a><span data-ttu-id="8d38b-104">Konfigurera leverantörsreskontra – översikt</span><span class="sxs-lookup"><span data-stu-id="8d38b-104">Configure Accounts payable overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8d38b-105">Det här avsnittet innehåller en beskrivning av de sidor som används för att ställa in grundläggande och valfria funktion för Leverantörsreskontra.</span><span class="sxs-lookup"><span data-stu-id="8d38b-105">This article describes the pages that you use to set up basic and optional functionality for Accounts payable.</span></span> <span data-ttu-id="8d38b-106">Även inställningsstegen som du måste vidta innan du börjar ställa in Leverantörsreskontra beskrivs.</span><span class="sxs-lookup"><span data-stu-id="8d38b-106">It also describes setup steps that you must complete before you start to set up Accounts payable.</span></span>

<a name="prerequisites-for-accounts-payable-setup"></a><span data-ttu-id="8d38b-107">Krav för inställning av leverantörsreskontra</span><span class="sxs-lookup"><span data-stu-id="8d38b-107">Prerequisites for Accounts payable setup</span></span>
----------------------------------------

<span data-ttu-id="8d38b-108">Följande inställning måste göras innan det går att ställa in leverantörsreskontra:</span><span class="sxs-lookup"><span data-stu-id="8d38b-108">Before you can set up Accounts payable, you must complete the following setup:</span></span>

-   <span data-ttu-id="8d38b-109">I Redovisning:</span><span class="sxs-lookup"><span data-stu-id="8d38b-109">In General ledger:</span></span>
    -   <span data-ttu-id="8d38b-110">Om du tänker använda betalningsjournaler, konfigurera betalningsjournaler.</span><span class="sxs-lookup"><span data-stu-id="8d38b-110">If you plan to use payment journals, set up payment journals.</span></span>
    -   <span data-ttu-id="8d38b-111">Om du tänker använda valutakursjusteringar, ställ in valutakoder på sidan Valutor, ställ in valutakurstyper på sidan Valutakurstyp och ställ in valutakurser på sidan Valutakurs.</span><span class="sxs-lookup"><span data-stu-id="8d38b-111">If you plan to run exchange rate adjustments, set up currency codes on the Currencies page, set up exchange rate types on the Exchange rate types page, and set up currency exchange rates on the Currency exchange rates page.</span></span>
-   <span data-ttu-id="8d38b-112">Ställ in bankkonton som används med betalningsmetoder i Kassa- och bankhantering.</span><span class="sxs-lookup"><span data-stu-id="8d38b-112">In Cash and bank management, set up bank accounts to use with methods of payment.</span></span>

## <a name="setup-pages-for-accounts-payable"></a><span data-ttu-id="8d38b-113">Inställningssidor för leverantörsreskontra</span><span class="sxs-lookup"><span data-stu-id="8d38b-113">Setup pages for Accounts payable</span></span>

<span data-ttu-id="8d38b-114">Använd följande sidor när du vill ställa in de grundläggande funktioner i Leverantörsreskontra för varje juridisk person.</span><span class="sxs-lookup"><span data-stu-id="8d38b-114">Use the following pages to set up the basic functionality of Accounts payable for each legal entity.</span></span> <span data-ttu-id="8d38b-115">Sidorna visas i rekommenderad inställningsordning.</span><span class="sxs-lookup"><span data-stu-id="8d38b-115">The pages are listed in the recommended order of setup.</span></span> <span data-ttu-id="8d38b-116">Du kan göra inställningsprocessen enklare genom att skapa mallar från de första posterna som du skapas.</span><span class="sxs-lookup"><span data-stu-id="8d38b-116">To make the setup process easier, you can create templates from the first records that you create.</span></span> <span data-ttu-id="8d38b-117">I en mall anges vanligtvis poster i många fält för att avspegla de funktioner organisationen vill implementera för en viss leverantörstyp.</span><span class="sxs-lookup"><span data-stu-id="8d38b-117">In a template, values are typically entered in many fields to reflect the features that the organization wants to implement for a particular type of vendor.</span></span>
1.  <span data-ttu-id="8d38b-118">Definiera betalningsvillkor som du tilldelar till försäljningsorder, inköpsorder, kunder och leverantörer och som fastställer fakturornas förfallodatum på sidan Betalningsvillkor.</span><span class="sxs-lookup"><span data-stu-id="8d38b-118">On the Terms of payment page, define the terms of payment that you assign to sales orders, purchase orders, customers, and vendors, and that determine invoice due dates.</span></span> <span data-ttu-id="8d38b-119">Mer information finns i [Definiera leverantörsbetalningsavgifter](tasks/define-vendor-payment-fees.md).</span><span class="sxs-lookup"><span data-stu-id="8d38b-119">For more information, see [Define vendor payment fees](tasks/define-vendor-payment-fees.md).</span></span>
2.  <span data-ttu-id="8d38b-120">Skapa och underhåll information om hur organisationen betalar sina leverantörer på sidan Betalningsmetoder - leverantörer.</span><span class="sxs-lookup"><span data-stu-id="8d38b-120">On the Methods of payment - vendors page, create and maintain information about how the organization pays its vendors.</span></span>
3.  <span data-ttu-id="8d38b-121">Skapa och underhåll grupper av leverantörer med gemensamma nyckelparametrar för bokföring, kvittning och betalning, rapportering och prognostisering på sidan Leverantörsgrupper.</span><span class="sxs-lookup"><span data-stu-id="8d38b-121">On the Vendor groups page, create and maintain groups of vendors that share important parameters for posting, settlement and payment, reporting, and forecasting.</span></span>
4.  <span data-ttu-id="8d38b-122">Definiera hur leverantörstransaktioner bokförs i redovisningen på sidan Bokföringsprofiler för leverantörer.</span><span class="sxs-lookup"><span data-stu-id="8d38b-122">On the Vendor posting profiles page, define how vendor transactions are posted to the general ledger.</span></span>
5.  <span data-ttu-id="8d38b-123">Konfigurera standardinställningar som tillämpas om en mer specifik inställning inte anges, parametrar för olika funktionstyper samt olika nummersekvenser för leverantörsreskontra på sidan Parametrar för leverantörsreskontra.</span><span class="sxs-lookup"><span data-stu-id="8d38b-123">On the Accounts payable parameters page, set up default settings that are applied if a more specific setting isn't specified, parameters for various kinds of functionality, and the various number sequences for Accounts payable.</span></span>
6.  <span data-ttu-id="8d38b-124">Definiera formatet för olika dokument som rör leverantörer och som används inom organisationen för att spåra inleveranser från leverantörer samt för att ange orsaker för betalningsflöden till leverantörer på sidan Formulärinställningar.</span><span class="sxs-lookup"><span data-stu-id="8d38b-124">On the Form setup page, define the format of various documents that are related to vendors, and that the organization uses to keep track of receipts from vendors and enter reasons for the flow of payments to vendors.</span></span>
7.  <span data-ttu-id="8d38b-125">Skapa och underhåll leverantörskonton och även de skattemyndigheter som organisationen rapporterar moms till på sidan Leverantörer.</span><span class="sxs-lookup"><span data-stu-id="8d38b-125">On the Vendors page, create and maintain vendor accounts, and also the tax authorities that your organization reports sales taxes to.</span></span>

## <a name="optional-setup-pages-for-accounts-payable"></a><span data-ttu-id="8d38b-126">Valfria inställningsformulär för leverantörsreskontra</span><span class="sxs-lookup"><span data-stu-id="8d38b-126">Optional setup pages for Accounts payable</span></span>
<span data-ttu-id="8d38b-127">Utöver de grundläggande funktionerna har Leverantörsreskontra andra funktioner som du kan ställa in.</span><span class="sxs-lookup"><span data-stu-id="8d38b-127">In addition to the basic functionality, Accounts payable has other functionality that you can set up.</span></span>

<span data-ttu-id="8d38b-128">De ytterligare inställningssidorna som används ordnas efter funktion.</span><span class="sxs-lookup"><span data-stu-id="8d38b-128">The additional setup pages are organized by functionality.</span></span>

<span data-ttu-id="8d38b-129">**Policyer**</span><span class="sxs-lookup"><span data-stu-id="8d38b-129">**Policies**</span></span>
-   <span data-ttu-id="8d38b-130">Ställ in leverantörsfakturapolicyer på sidan Leverantörens fakturapolicy.</span><span class="sxs-lookup"><span data-stu-id="8d38b-130">On the Vendor invoice policy page, set up vendor invoice policies.</span></span>

<span data-ttu-id="8d38b-131">**Fakturamatchning**</span><span class="sxs-lookup"><span data-stu-id="8d38b-131">**Invoice matching**</span></span>

-   <span data-ttu-id="8d38b-132">Ställ in toleranser för fakturasummor på sidan Toleranser för fakturasummor.</span><span class="sxs-lookup"><span data-stu-id="8d38b-132">On the Invoice totals tolerances page, set up tolerances for invoice totals.</span></span>
-   <span data-ttu-id="8d38b-133">Ställ in matchningspolicyer för tvåvägs- och trevägsmatchningspolicyer på sidan Matchningspolicy.</span><span class="sxs-lookup"><span data-stu-id="8d38b-133">On the Matching policy page, set up two-way and three-way matching policies.</span></span>
-   <span data-ttu-id="8d38b-134">Ställ in toleranser för enhetspriser på sidan Pristoleranser.</span><span class="sxs-lookup"><span data-stu-id="8d38b-134">On the Price tolerances page, set up tolerances for unit prices.</span></span>
-   <span data-ttu-id="8d38b-135">Ställ in toleransgrupper för artikelpriserna på sidan Toleransgrupper för artikelpris.</span><span class="sxs-lookup"><span data-stu-id="8d38b-135">On the Item price tolerance groups page, set up tolerance groups for item prices.</span></span>
-   <span data-ttu-id="8d38b-136">Ställ in toleransgrupper för leverantörspriserna på sidan Toleransgrupper för leverantörspris.</span><span class="sxs-lookup"><span data-stu-id="8d38b-136">On the Vendor price tolerance groups page, set up  tolerance groups for vendor prices.</span></span>
-   <span data-ttu-id="8d38b-137">Ställ in toleranser för avgifter på sidan Avgiftstoleranser.</span><span class="sxs-lookup"><span data-stu-id="8d38b-137">On the Charges tolerances page, set up tolerances for charges.</span></span>

<span data-ttu-id="8d38b-138">**Arbetsflöde**</span><span class="sxs-lookup"><span data-stu-id="8d38b-138">**Workflow**</span></span>

-   <span data-ttu-id="8d38b-139">Ställ in arbetsflödeskonfigurationen för journalgodkännanden och inköpsrekvisitioner på sidan Arbetsflöden för leverantörsreskontra.</span><span class="sxs-lookup"><span data-stu-id="8d38b-139">On the Accounts payable workflows page, set up workflow configurations for journal approvals and purchase requisitions.</span></span>

<span data-ttu-id="8d38b-140">**Orsaker**</span><span class="sxs-lookup"><span data-stu-id="8d38b-140">**Reasons**</span></span>

-   <span data-ttu-id="8d38b-141">Ställ in orsakskoder på sidan Leverantörsorsaker.</span><span class="sxs-lookup"><span data-stu-id="8d38b-141">On the Vendor reasons page, set up reason codes.</span></span>

<span data-ttu-id="8d38b-142">**Avgifter**</span><span class="sxs-lookup"><span data-stu-id="8d38b-142">**Charges**</span></span>

-   <span data-ttu-id="8d38b-143">Ställ in koder för avgifter som används i inköpsorder på sidan Kod för avgifter.</span><span class="sxs-lookup"><span data-stu-id="8d38b-143">On the Charges code page, set up codes for the charges that are used in purchase orders.</span></span>
-   <span data-ttu-id="8d38b-144">På sidan Leverantörsavgiftsgrupp, skapa och underhåll avgiftsgrupper för leverantörer.</span><span class="sxs-lookup"><span data-stu-id="8d38b-144">On the Vendor charges group page, create and maintain charges groups for vendors.</span></span>
-   <span data-ttu-id="8d38b-145">På sidan Avgiftsgrupper för artikel, skapa och underhåll avgiftsgrupper för artiklar.</span><span class="sxs-lookup"><span data-stu-id="8d38b-145">On the Item charge groups page, create and maintain charges groups for items.</span></span>
-   <span data-ttu-id="8d38b-146">På sidan Automatiska avgifter, definiera de inköpstillägg som tilldelas automatiskt för order.</span><span class="sxs-lookup"><span data-stu-id="8d38b-146">On the Auto charges page, define the charges that are automatically assigned to orders.</span></span>

<span data-ttu-id="8d38b-147">**Fyllnadsartiklar**</span><span class="sxs-lookup"><span data-stu-id="8d38b-147">**Supplementary items**</span></span>

-   <span data-ttu-id="8d38b-148">På sidan Fyllnadsartikelgrupper - Leverantör, skapa och underhåll fyllnadsartikelgrupper för leverantörer.</span><span class="sxs-lookup"><span data-stu-id="8d38b-148">On the Supplementary item groups - Vendor page, create and maintain supplementary item groups for vendors.</span></span>
-   <span data-ttu-id="8d38b-149">På sidan Fyllnadsartikelgrupper - Lager, skapa och underhåll fyllnadsartikelgrupper för artiklar.</span><span class="sxs-lookup"><span data-stu-id="8d38b-149">On the Supplementary item groups - Inventory page, create and maintain supplementary item groups for items.</span></span>

<span data-ttu-id="8d38b-150">**Fördelning**</span><span class="sxs-lookup"><span data-stu-id="8d38b-150">**Distribution**</span></span>

-   <span data-ttu-id="8d38b-151">Skapa och underhåll villkor för en artikels överföring från säljaren till köparen på sidan Leveransvillkor.</span><span class="sxs-lookup"><span data-stu-id="8d38b-151">On the Terms of delivery page, create and maintain the conditions for an item's transfer from seller to buyer.</span></span>
-   <span data-ttu-id="8d38b-152">På sidan Leveranssätt, skapa och underhåll transportsätt som används när en order levereras från säljaren till köparen.</span><span class="sxs-lookup"><span data-stu-id="8d38b-152">On the Modes of delivery page, create and maintain the methods of transport that are used when an order is delivered from the seller to the buyer.</span></span>
-   <span data-ttu-id="8d38b-153">På sidan Destinationskoder, skapa och underhåll identifierare och beskrivningar för leveransdestinationer.</span><span class="sxs-lookup"><span data-stu-id="8d38b-153">On the Destination codes page, create and maintain identifiers and descriptions for delivery destinations.</span></span>

<span data-ttu-id="8d38b-154">**Formulär**</span><span class="sxs-lookup"><span data-stu-id="8d38b-154">**Forms**</span></span>

-   <span data-ttu-id="8d38b-155">På sidan Formulärnoteringar, skapa den standardtext som visas på olika sidor.</span><span class="sxs-lookup"><span data-stu-id="8d38b-155">On the Form notes page, create the standard text that appears on various pages.</span></span>
-   <span data-ttu-id="8d38b-156">På sidan Parametrar för formulärsortering, ange sorteringsordning för rekvisitioner, inleveranslistor, följesedlar och fakturor.</span><span class="sxs-lookup"><span data-stu-id="8d38b-156">On the Form sorting parameters page, set up the sorting order for requisitions, receipt lists, packing slips, and invoices.</span></span>
-   <span data-ttu-id="8d38b-157">På sidan Inställningar för utskriftshantering, ställ in information om utskriftshantering för original och kopior av sidor.</span><span class="sxs-lookup"><span data-stu-id="8d38b-157">On the Print management setup page, set up print management information for originals and copies of pages.</span></span>

<span data-ttu-id="8d38b-158">**Betalningar**</span><span class="sxs-lookup"><span data-stu-id="8d38b-158">**Payments**</span></span>

-   <span data-ttu-id="8d38b-159">På sidan, ställ in och underhåll villkoren för erhållande av kassarabatter.</span><span class="sxs-lookup"><span data-stu-id="8d38b-159">On the Cash discounts page, set up and manage the terms for obtaining cash discounts.</span></span> <span data-ttu-id="8d38b-160">Kassarabattkoderna är kopplade till leverantörer och tillämpas på inköpsorder.</span><span class="sxs-lookup"><span data-stu-id="8d38b-160">The cash discount codes are linked to vendors and are applied to purchase orders.</span></span>
-   <span data-ttu-id="8d38b-161">På sidan Betalningsplaner, ställ in betalningsplaner som används för hantering av avbetalningar till leverantörer.</span><span class="sxs-lookup"><span data-stu-id="8d38b-161">On the Payment schedules page, set up the payment schedules that are used to manage installment payments to vendors.</span></span>
-   <span data-ttu-id="8d38b-162">På sidan Betalningsdagar, definiera betalningsdagar som används för beräkning av förfallodatum och ange betalningsdagar för en specifik dag i veckan eller månaden.</span><span class="sxs-lookup"><span data-stu-id="8d38b-162">On the Payment days page, define the payment days that are used to calculate due dates, and specify payment days for a specific day of the week or month.</span></span>
-   <span data-ttu-id="8d38b-163">På sidan Betalningsavgift, skapa och underhåll betalningsavgifter som är associerade med leverantörer.</span><span class="sxs-lookup"><span data-stu-id="8d38b-163">On the Payment fee page, create and maintain the payment fees that are associated with vendors.</span></span>
-   <span data-ttu-id="8d38b-164">På sidan Betalningsinstruktion, skapa och underhåll betalningsinstruktioner.</span><span class="sxs-lookup"><span data-stu-id="8d38b-164">On the Payment instruction page, create and maintain payment instructions.</span></span>

<span data-ttu-id="8d38b-165">**Statistik**</span><span class="sxs-lookup"><span data-stu-id="8d38b-165">**Statistics**</span></span>

-   <span data-ttu-id="8d38b-166">På sidan Definitioner för åldersfördelningsperiod, ställ in användardefinierade intervall för analys av förfallodagsfördelningen för leverantörskonton.</span><span class="sxs-lookup"><span data-stu-id="8d38b-166">On the Aging period definitions page, set up user-defined intervals that are used to analyze the maturity distribution of vendor accounts.</span></span>
-   <span data-ttu-id="8d38b-167">På sidan Affärsområde, skapa affärsområdeskoderna (LOB) som tilldelas leverantörer.</span><span class="sxs-lookup"><span data-stu-id="8d38b-167">On the Line of business page, create the line of business (LOB) codes that are assigned to vendors.</span></span>

<span data-ttu-id="8d38b-168">**Skatt 1099**</span><span class="sxs-lookup"><span data-stu-id="8d38b-168">**Tax 1099**</span></span>

-   <span data-ttu-id="8d38b-169">På sidan **1099-fält** bekräftar och uppdaterar du de minimibelopp som måste rapporteras till Internal Revenue Service (IRS), baserade på de senaste IRS-kraven.</span><span class="sxs-lookup"><span data-stu-id="8d38b-169">On the **1099 fields** page, verify and update the minimum amounts that must be reported to the Internal Revenue Service (IRS), based on the latest IRS requirements.</span></span>

## <a name="optional-setup-for-other-modules"></a><span data-ttu-id="8d38b-170">**Valfria inställningar för andra moduler**</span><span class="sxs-lookup"><span data-stu-id="8d38b-170">**Optional setup for other modules**</span></span>
<span data-ttu-id="8d38b-171">**Organisationsadministration**</span><span class="sxs-lookup"><span data-stu-id="8d38b-171">**Organization administration**</span></span>

-   <span data-ttu-id="8d38b-172">På sidan Nummerserier, ställ in nummerseriegrupper för fakturanummer.</span><span class="sxs-lookup"><span data-stu-id="8d38b-172">On the Number sequences page, set up number sequence groups for invoice numbers.</span></span>
-   <span data-ttu-id="8d38b-173">Ange adressinformation på efterföljande sidor:</span><span class="sxs-lookup"><span data-stu-id="8d38b-173">On the following pages, set up address information:</span></span>
    -   <span data-ttu-id="8d38b-174">Adressinställning</span><span class="sxs-lookup"><span data-stu-id="8d38b-174">Address setup</span></span>
    -   <span data-ttu-id="8d38b-175">NAF-koder</span><span class="sxs-lookup"><span data-stu-id="8d38b-175">NAF codes</span></span>
    -   <span data-ttu-id="8d38b-176">Importera postnr</span><span class="sxs-lookup"><span data-stu-id="8d38b-176">Import ZIP/postal codes</span></span>

<span data-ttu-id="8d38b-177">**Redovisning**</span><span class="sxs-lookup"><span data-stu-id="8d38b-177">**General ledger**</span></span>

-   <span data-ttu-id="8d38b-178">På sidanEkonomiska dimensioner, ställ in ekonomiska dimensioner.</span><span class="sxs-lookup"><span data-stu-id="8d38b-178">On the Financial dimensions page, set up financial dimensions.</span></span>
-   <span data-ttu-id="8d38b-179">Konfigurera skatteinformation på följande sidor:</span><span class="sxs-lookup"><span data-stu-id="8d38b-179">On the following pages, set up tax information:</span></span>
    -   <span data-ttu-id="8d38b-180">Momskoder</span><span class="sxs-lookup"><span data-stu-id="8d38b-180">Sales tax codes</span></span>
    -   <span data-ttu-id="8d38b-181">Momsgrupper</span><span class="sxs-lookup"><span data-stu-id="8d38b-181">Sales tax groups</span></span>
    -   <span data-ttu-id="8d38b-182">Artikelmomsgrupper</span><span class="sxs-lookup"><span data-stu-id="8d38b-182">Item sales tax groups</span></span>
    -   <span data-ttu-id="8d38b-183">Kontogrupp</span><span class="sxs-lookup"><span data-stu-id="8d38b-183">Account group</span></span>
    -   <span data-ttu-id="8d38b-184">Momsbefrielsekoder</span><span class="sxs-lookup"><span data-stu-id="8d38b-184">Sales tax exempt codes</span></span>
    -   <span data-ttu-id="8d38b-185">Skattemyndigheter</span><span class="sxs-lookup"><span data-stu-id="8d38b-185">Sales tax jurisdictions</span></span>
    -   <span data-ttu-id="8d38b-186">Skattemyndigheter</span><span class="sxs-lookup"><span data-stu-id="8d38b-186">Sales tax authorities</span></span>
    -   <span data-ttu-id="8d38b-187">Momskvittningsperioder</span><span class="sxs-lookup"><span data-stu-id="8d38b-187">Sales tax settlement periods</span></span>

<span data-ttu-id="8d38b-188">**Kassa- och bankhantering**</span><span class="sxs-lookup"><span data-stu-id="8d38b-188">**Cash and bank management**</span></span>

-   <span data-ttu-id="8d38b-189">Ställ in centralbankens syfteskoder på sidan Syfteskoder för betalning</span><span class="sxs-lookup"><span data-stu-id="8d38b-189">On the Payment purpose codes page, set up the Central Bank purpose code.</span></span>





