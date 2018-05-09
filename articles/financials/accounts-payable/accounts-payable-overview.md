---
title: "Konfigurera leverantörsreskontra"
description: "Det här avsnittet innehåller en beskrivning av de sidor som används för att ställa in grundläggande och valfria funktion för Leverantörsreskontra i Microsoft Dynamics 365 for Finance and Operations. Även inställningsstegen som du måste vidta innan du börjar ställa in Leverantörsreskontra beskrivs."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/08/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BankAccountTable, DeliveryMode, PaymTerm, VendGroup, VendParameters, VendPaymMode, VendTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 24671
ms.assetid: 82561fe7-b2d6-464c-9347-79d0ce0f9743
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: f8437797f107ca00ca642e56330d58eeeb00ed0f
ms.contentlocale: sv-se
ms.lasthandoff: 05/08/2018

---

# <a name="configure-accounts-payable"></a><span data-ttu-id="23801-104">Konfigurera leverantörsreskontra</span><span class="sxs-lookup"><span data-stu-id="23801-104">Configure Accounts payable</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="23801-105">Det här avsnittet innehåller en beskrivning av de sidor som används för att ställa in grundläggande och valfria funktion för Leverantörsreskontra i Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="23801-105">This article describes the pages that you use to set up basic and optional functionality for Accounts payable in Microsoft Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="23801-106">Även inställningsstegen som du måste vidta innan du börjar ställa in Leverantörsreskontra beskrivs.</span><span class="sxs-lookup"><span data-stu-id="23801-106">It also describes setup steps that you must complete before you start to set up Accounts payable.</span></span>

<a name="prerequisites-for-accounts-payable-setup"></a><span data-ttu-id="23801-107">Krav för inställning av leverantörsreskontra</span><span class="sxs-lookup"><span data-stu-id="23801-107">Prerequisites for Accounts payable setup</span></span>
----------------------------------------

<span data-ttu-id="23801-108">Följande inställning måste göras innan det går att ställa in leverantörsreskontra:</span><span class="sxs-lookup"><span data-stu-id="23801-108">Before you can set up Accounts payable, you must complete the following setup:</span></span>

-   <span data-ttu-id="23801-109">I Redovisning:</span><span class="sxs-lookup"><span data-stu-id="23801-109">In General ledger:</span></span>
    -   <span data-ttu-id="23801-110">Om du tänker använda betalningsjournaler, konfigurera betalningsjournaler.</span><span class="sxs-lookup"><span data-stu-id="23801-110">If you plan to use payment journals, set up payment journals.</span></span>
    -   <span data-ttu-id="23801-111">Om du tänker använda valutakursjusteringar, ställ in valutakoder på sidan Valutor, ställ in valutakurstyper på sidan Valutakurstyp och ställ in valutakurser på sidan Valutakurs.</span><span class="sxs-lookup"><span data-stu-id="23801-111">If you plan to run exchange rate adjustments, set up currency codes on the Currencies page, set up exchange rate types on the Exchange rate types page, and set up currency exchange rates on the Currency exchange rates page.</span></span>
-   <span data-ttu-id="23801-112">Ställ in bankkonton som används med betalningsmetoder i Kassa- och bankhantering.</span><span class="sxs-lookup"><span data-stu-id="23801-112">In Cash and bank management, set up bank accounts to use with methods of payment.</span></span>

## <a name="setup-pages-for-accounts-payable"></a><span data-ttu-id="23801-113">Inställningssidor för leverantörsreskontra</span><span class="sxs-lookup"><span data-stu-id="23801-113">Setup pages for Accounts payable</span></span>

<span data-ttu-id="23801-114">Använd följande sidor när du vill ställa in de grundläggande funktioner i Leverantörsreskontra för varje juridisk person.</span><span class="sxs-lookup"><span data-stu-id="23801-114">Use the following pages to set up the basic functionality of Accounts payable for each legal entity.</span></span> <span data-ttu-id="23801-115">Sidorna visas i rekommenderad inställningsordning.</span><span class="sxs-lookup"><span data-stu-id="23801-115">The pages are listed in the recommended order of setup.</span></span> <span data-ttu-id="23801-116">Du kan göra inställningsprocessen enklare genom att skapa mallar från de första posterna som du skapas.</span><span class="sxs-lookup"><span data-stu-id="23801-116">To make the setup process easier, you can create templates from the first records that you create.</span></span> <span data-ttu-id="23801-117">I en mall anges vanligtvis poster i många fält för att avspegla de funktioner organisationen vill implementera för en viss leverantörstyp.</span><span class="sxs-lookup"><span data-stu-id="23801-117">In a template, values are typically entered in many fields to reflect the features that the organization wants to implement for a particular type of vendor.</span></span>
1.  <span data-ttu-id="23801-118">Definiera betalningsvillkor som du tilldelar till försäljningsorder, inköpsorder, kunder och leverantörer och som fastställer fakturornas förfallodatum på sidan Betalningsvillkor.</span><span class="sxs-lookup"><span data-stu-id="23801-118">On the Terms of payment page, define the terms of payment that you assign to sales orders, purchase orders, customers, and vendors, and that determine invoice due dates.</span></span> <span data-ttu-id="23801-119">Mer information finns i [Definiera leverantörsbetalningsavgifter](tasks/define-vendor-payment-fees.md).</span><span class="sxs-lookup"><span data-stu-id="23801-119">For more information, see [Define vendor payment fees](tasks/define-vendor-payment-fees.md).</span></span>
2.  <span data-ttu-id="23801-120">Skapa och underhåll information om hur organisationen betalar sina leverantörer på sidan Betalningsmetoder - leverantörer.</span><span class="sxs-lookup"><span data-stu-id="23801-120">On the Methods of payment - vendors page, create and maintain information about how the organization pays its vendors.</span></span>
3.  <span data-ttu-id="23801-121">Skapa och underhåll grupper av leverantörer med gemensamma nyckelparametrar för bokföring, kvittning och betalning, rapportering och prognostisering på sidan Leverantörsgrupper.</span><span class="sxs-lookup"><span data-stu-id="23801-121">On the Vendor groups page, create and maintain groups of vendors that share important parameters for posting, settlement and payment, reporting, and forecasting.</span></span>
4.  <span data-ttu-id="23801-122">Definiera hur leverantörstransaktioner bokförs i redovisningen på sidan Bokföringsprofiler för leverantörer.</span><span class="sxs-lookup"><span data-stu-id="23801-122">On the Vendor posting profiles page, define how vendor transactions are posted to the general ledger.</span></span>
5.  <span data-ttu-id="23801-123">Konfigurera standardinställningar som tillämpas om en mer specifik inställning inte anges, parametrar för olika funktionstyper samt olika nummersekvenser för leverantörsreskontra på sidan Parametrar för leverantörsreskontra.</span><span class="sxs-lookup"><span data-stu-id="23801-123">On the Accounts payable parameters page, set up default settings that are applied if a more specific setting isn't specified, parameters for various kinds of functionality, and the various number sequences for Accounts payable.</span></span>
6.  <span data-ttu-id="23801-124">Definiera formatet för olika dokument som rör leverantörer och som används inom organisationen för att spåra inleveranser från leverantörer samt för att ange orsaker för betalningsflöden till leverantörer på sidan Formulärinställningar.</span><span class="sxs-lookup"><span data-stu-id="23801-124">On the Form setup page, define the format of various documents that are related to vendors, and that the organization uses to keep track of receipts from vendors and enter reasons for the flow of payments to vendors.</span></span>
7.  <span data-ttu-id="23801-125">Skapa och underhåll leverantörskonton och även de skattemyndigheter som organisationen rapporterar moms till på sidan Leverantörer.</span><span class="sxs-lookup"><span data-stu-id="23801-125">On the Vendors page, create and maintain vendor accounts, and also the tax authorities that your organization reports sales taxes to.</span></span>

## <a name="optional-setup-pages-for-accounts-payable"></a><span data-ttu-id="23801-126">Valfria inställningsformulär för leverantörsreskontra</span><span class="sxs-lookup"><span data-stu-id="23801-126">Optional setup pages for Accounts payable</span></span>
<span data-ttu-id="23801-127">Utöver de grundläggande funktionerna har Leverantörsreskontra andra funktioner som du kan ställa in.</span><span class="sxs-lookup"><span data-stu-id="23801-127">In addition to the basic functionality, Accounts payable has other functionality that you can set up.</span></span>

<span data-ttu-id="23801-128">De ytterligare inställningssidorna som används ordnas efter funktion.</span><span class="sxs-lookup"><span data-stu-id="23801-128">The additional setup pages are organized by functionality.</span></span>

<span data-ttu-id="23801-129">**Policyer**</span><span class="sxs-lookup"><span data-stu-id="23801-129">**Policies**</span></span>
-   <span data-ttu-id="23801-130">Ställ in leverantörsfakturapolicyer på sidan Leverantörens fakturapolicy.</span><span class="sxs-lookup"><span data-stu-id="23801-130">On the Vendor invoice policy page, set up vendor invoice policies.</span></span>

<span data-ttu-id="23801-131">**Fakturamatchning**</span><span class="sxs-lookup"><span data-stu-id="23801-131">**Invoice matching**</span></span>

-   <span data-ttu-id="23801-132">Ställ in toleranser för fakturasummor på sidan Toleranser för fakturasummor.</span><span class="sxs-lookup"><span data-stu-id="23801-132">On the Invoice totals tolerances page, set up tolerances for invoice totals.</span></span>
-   <span data-ttu-id="23801-133">Ställ in matchningspolicyer för tvåvägs- och trevägsmatchningspolicyer på sidan Matchningspolicy.</span><span class="sxs-lookup"><span data-stu-id="23801-133">On the Matching policy page, set up two-way and three-way matching policies.</span></span>
-   <span data-ttu-id="23801-134">Ställ in toleranser för enhetspriser på sidan Pristoleranser.</span><span class="sxs-lookup"><span data-stu-id="23801-134">On the Price tolerances page, set up tolerances for unit prices.</span></span>
-   <span data-ttu-id="23801-135">Ställ in toleransgrupper för artikelpriserna på sidan Toleransgrupper för artikelpris.</span><span class="sxs-lookup"><span data-stu-id="23801-135">On the Item price tolerance groups page, set up tolerance groups for item prices.</span></span>
-   <span data-ttu-id="23801-136">Ställ in toleransgrupper för leverantörspriserna på sidan Toleransgrupper för leverantörspris.</span><span class="sxs-lookup"><span data-stu-id="23801-136">On the Vendor price tolerance groups page, set up  tolerance groups for vendor prices.</span></span>
-   <span data-ttu-id="23801-137">Ställ in toleranser för avgifter på sidan Avgiftstoleranser.</span><span class="sxs-lookup"><span data-stu-id="23801-137">On the Charges tolerances page, set up tolerances for charges.</span></span>

<span data-ttu-id="23801-138">**Arbetsflöde**</span><span class="sxs-lookup"><span data-stu-id="23801-138">**Workflow**</span></span>

-   <span data-ttu-id="23801-139">Ställ in arbetsflödeskonfigurationen för journalgodkännanden och inköpsrekvisitioner på sidan Arbetsflöden för leverantörsreskontra.</span><span class="sxs-lookup"><span data-stu-id="23801-139">On the Accounts payable workflows page, set up workflow configurations for journal approvals and purchase requisitions.</span></span>

<span data-ttu-id="23801-140">**Orsaker**</span><span class="sxs-lookup"><span data-stu-id="23801-140">**Reasons**</span></span>

-   <span data-ttu-id="23801-141">Ställ in orsakskoder på sidan Leverantörsorsaker.</span><span class="sxs-lookup"><span data-stu-id="23801-141">On the Vendor reasons page, set up reason codes.</span></span>

<span data-ttu-id="23801-142">**Avgifter**</span><span class="sxs-lookup"><span data-stu-id="23801-142">**Charges**</span></span>

-   <span data-ttu-id="23801-143">Ställ in koder för avgifter som används i inköpsorder på sidan Kod för avgifter.</span><span class="sxs-lookup"><span data-stu-id="23801-143">On the Charges code page, set up codes for the charges that are used in purchase orders.</span></span>
-   <span data-ttu-id="23801-144">På sidan Leverantörsavgiftsgrupp, skapa och underhåll avgiftsgrupper för leverantörer.</span><span class="sxs-lookup"><span data-stu-id="23801-144">On the Vendor charges group page, create and maintain charges groups for vendors.</span></span>
-   <span data-ttu-id="23801-145">På sidan Avgiftsgrupper för artikel, skapa och underhåll avgiftsgrupper för artiklar.</span><span class="sxs-lookup"><span data-stu-id="23801-145">On the Item charge groups page, create and maintain charges groups for items.</span></span>
-   <span data-ttu-id="23801-146">På sidan Automatiska avgifter, definiera de inköpstillägg som tilldelas automatiskt för order.</span><span class="sxs-lookup"><span data-stu-id="23801-146">On the Auto charges page, define the charges that are automatically assigned to orders.</span></span>

<span data-ttu-id="23801-147">**Fyllnadsartiklar**</span><span class="sxs-lookup"><span data-stu-id="23801-147">**Supplementary items**</span></span>

-   <span data-ttu-id="23801-148">På sidan Fyllnadsartikelgrupper - Leverantör, skapa och underhåll fyllnadsartikelgrupper för leverantörer.</span><span class="sxs-lookup"><span data-stu-id="23801-148">On the Supplementary item groups - Vendor page, create and maintain supplementary item groups for vendors.</span></span>
-   <span data-ttu-id="23801-149">På sidan Fyllnadsartikelgrupper - Lager, skapa och underhåll fyllnadsartikelgrupper för artiklar.</span><span class="sxs-lookup"><span data-stu-id="23801-149">On the Supplementary item groups - Inventory page, create and maintain supplementary item groups for items.</span></span>

<span data-ttu-id="23801-150">**Fördelning**</span><span class="sxs-lookup"><span data-stu-id="23801-150">**Distribution**</span></span>

-   <span data-ttu-id="23801-151">Skapa och underhåll villkor för en artikels överföring från säljaren till köparen på sidan Leveransvillkor.</span><span class="sxs-lookup"><span data-stu-id="23801-151">On the Terms of delivery page, create and maintain the conditions for an item's transfer from seller to buyer.</span></span>
-   <span data-ttu-id="23801-152">På sidan Leveranssätt, skapa och underhåll transportsätt som används när en order levereras från säljaren till köparen.</span><span class="sxs-lookup"><span data-stu-id="23801-152">On the Modes of delivery page, create and maintain the methods of transport that are used when an order is delivered from the seller to the buyer.</span></span>
-   <span data-ttu-id="23801-153">På sidan Destinationskoder, skapa och underhåll identifierare och beskrivningar för leveransdestinationer.</span><span class="sxs-lookup"><span data-stu-id="23801-153">On the Destination codes page, create and maintain identifiers and descriptions for delivery destinations.</span></span>

<span data-ttu-id="23801-154">**Formulär**</span><span class="sxs-lookup"><span data-stu-id="23801-154">**Forms**</span></span>

-   <span data-ttu-id="23801-155">På sidan Formulärnoteringar, skapa den standardtext som visas på olika sidor.</span><span class="sxs-lookup"><span data-stu-id="23801-155">On the Form notes page, create the standard text that appears on various pages.</span></span>
-   <span data-ttu-id="23801-156">På sidan Parametrar för formulärsortering, ange sorteringsordning för rekvisitioner, inleveranslistor, följesedlar och fakturor.</span><span class="sxs-lookup"><span data-stu-id="23801-156">On the Form sorting parameters page, set up the sorting order for requisitions, receipt lists, packing slips, and invoices.</span></span>
-   <span data-ttu-id="23801-157">På sidan Inställningar för utskriftshantering, ställ in information om utskriftshantering för original och kopior av sidor.</span><span class="sxs-lookup"><span data-stu-id="23801-157">On the Print management setup page, set up print management information for originals and copies of pages.</span></span>

<span data-ttu-id="23801-158">**Betalningar**</span><span class="sxs-lookup"><span data-stu-id="23801-158">**Payments**</span></span>

-   <span data-ttu-id="23801-159">På sidan, ställ in och underhåll villkoren för erhållande av kassarabatter.</span><span class="sxs-lookup"><span data-stu-id="23801-159">On the Cash discounts page, set up and manage the terms for obtaining cash discounts.</span></span> <span data-ttu-id="23801-160">Kassarabattkoderna är kopplade till leverantörer och tillämpas på inköpsorder.</span><span class="sxs-lookup"><span data-stu-id="23801-160">The cash discount codes are linked to vendors and are applied to purchase orders.</span></span>
-   <span data-ttu-id="23801-161">På sidan Betalningsplaner, ställ in betalningsplaner som används för hantering av avbetalningar till leverantörer.</span><span class="sxs-lookup"><span data-stu-id="23801-161">On the Payment schedules page, set up the payment schedules that are used to manage installment payments to vendors.</span></span>
-   <span data-ttu-id="23801-162">På sidan Betalningsdagar, definiera betalningsdagar som används för beräkning av förfallodatum och ange betalningsdagar för en specifik dag i veckan eller månaden.</span><span class="sxs-lookup"><span data-stu-id="23801-162">On the Payment days page, define the payment days that are used to calculate due dates, and specify payment days for a specific day of the week or month.</span></span>
-   <span data-ttu-id="23801-163">På sidan Betalningsavgift, skapa och underhåll betalningsavgifter som är associerade med leverantörer.</span><span class="sxs-lookup"><span data-stu-id="23801-163">On the Payment fee page, create and maintain the payment fees that are associated with vendors.</span></span>
-   <span data-ttu-id="23801-164">På sidan Betalningsinstruktion, skapa och underhåll betalningsinstruktioner.</span><span class="sxs-lookup"><span data-stu-id="23801-164">On the Payment instruction page, create and maintain payment instructions.</span></span>

<span data-ttu-id="23801-165">**Statistik**</span><span class="sxs-lookup"><span data-stu-id="23801-165">**Statistics**</span></span>

-   <span data-ttu-id="23801-166">På sidan Definitioner för åldersfördelningsperiod, ställ in användardefinierade intervall för analys av förfallodagsfördelningen för leverantörskonton.</span><span class="sxs-lookup"><span data-stu-id="23801-166">On the Aging period definitions page, set up user-defined intervals that are used to analyze the maturity distribution of vendor accounts.</span></span>
-   <span data-ttu-id="23801-167">På sidan Affärsområde, skapa affärsområdeskoderna (LOB) som tilldelas leverantörer.</span><span class="sxs-lookup"><span data-stu-id="23801-167">On the Line of business page, create the line of business (LOB) codes that are assigned to vendors.</span></span>

<span data-ttu-id="23801-168">**Skatt 1099**</span><span class="sxs-lookup"><span data-stu-id="23801-168">**Tax 1099**</span></span>

-   <span data-ttu-id="23801-169">På sidan **1099-fält** bekräftar och uppdaterar du de minimibelopp som måste rapporteras till Internal Revenue Service (IRS), baserade på de senaste IRS-kraven.</span><span class="sxs-lookup"><span data-stu-id="23801-169">On the **1099 fields** page, verify and update the minimum amounts that must be reported to the Internal Revenue Service (IRS), based on the latest IRS requirements.</span></span>

## <a name="optional-setup-for-other-modules"></a><span data-ttu-id="23801-170">**Valfria inställningar för andra moduler**</span><span class="sxs-lookup"><span data-stu-id="23801-170">**Optional setup for other modules**</span></span>
<span data-ttu-id="23801-171">**Organisationsadministration**</span><span class="sxs-lookup"><span data-stu-id="23801-171">**Organization administration**</span></span>

-   <span data-ttu-id="23801-172">På sidan Nummerserier, ställ in nummerseriegrupper för fakturanummer.</span><span class="sxs-lookup"><span data-stu-id="23801-172">On the Number sequences page, set up number sequence groups for invoice numbers.</span></span>
-   <span data-ttu-id="23801-173">Ange adressinformation på efterföljande sidor:</span><span class="sxs-lookup"><span data-stu-id="23801-173">On the following pages, set up address information:</span></span>
    -   <span data-ttu-id="23801-174">Adressinställning</span><span class="sxs-lookup"><span data-stu-id="23801-174">Address setup</span></span>
    -   <span data-ttu-id="23801-175">NAF-koder</span><span class="sxs-lookup"><span data-stu-id="23801-175">NAF codes</span></span>
    -   <span data-ttu-id="23801-176">Importera postnr</span><span class="sxs-lookup"><span data-stu-id="23801-176">Import ZIP/postal codes</span></span>

<span data-ttu-id="23801-177">**Redovisning**</span><span class="sxs-lookup"><span data-stu-id="23801-177">**General ledger**</span></span>

-   <span data-ttu-id="23801-178">På sidanEkonomiska dimensioner, ställ in ekonomiska dimensioner.</span><span class="sxs-lookup"><span data-stu-id="23801-178">On the Financial dimensions page, set up financial dimensions.</span></span>
-   <span data-ttu-id="23801-179">Konfigurera skatteinformation på följande sidor:</span><span class="sxs-lookup"><span data-stu-id="23801-179">On the following pages, set up tax information:</span></span>
    -   <span data-ttu-id="23801-180">Momskoder</span><span class="sxs-lookup"><span data-stu-id="23801-180">Sales tax codes</span></span>
    -   <span data-ttu-id="23801-181">Momsgrupper</span><span class="sxs-lookup"><span data-stu-id="23801-181">Sales tax groups</span></span>
    -   <span data-ttu-id="23801-182">Artikelmomsgrupper</span><span class="sxs-lookup"><span data-stu-id="23801-182">Item sales tax groups</span></span>
    -   <span data-ttu-id="23801-183">Kontogrupp</span><span class="sxs-lookup"><span data-stu-id="23801-183">Account group</span></span>
    -   <span data-ttu-id="23801-184">Momsbefrielsekoder</span><span class="sxs-lookup"><span data-stu-id="23801-184">Sales tax exempt codes</span></span>
    -   <span data-ttu-id="23801-185">Skattemyndigheter</span><span class="sxs-lookup"><span data-stu-id="23801-185">Sales tax jurisdictions</span></span>
    -   <span data-ttu-id="23801-186">Skattemyndigheter</span><span class="sxs-lookup"><span data-stu-id="23801-186">Sales tax authorities</span></span>
    -   <span data-ttu-id="23801-187">Momskvittningsperioder</span><span class="sxs-lookup"><span data-stu-id="23801-187">Sales tax settlement periods</span></span>

<span data-ttu-id="23801-188">**Kassa- och bankhantering**</span><span class="sxs-lookup"><span data-stu-id="23801-188">**Cash and bank management**</span></span>

-   <span data-ttu-id="23801-189">Ställ in centralbankens syfteskoder på sidan Syfteskoder för betalning</span><span class="sxs-lookup"><span data-stu-id="23801-189">On the Payment purpose codes page, set up the Central Bank purpose code.</span></span>






