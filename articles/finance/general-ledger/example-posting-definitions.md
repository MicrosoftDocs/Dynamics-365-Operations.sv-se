---
title: Exempel på bokföringsdefinitioner
description: Denna artikel innehåller exempel som visar hur du använder bokföringsdefinitioner för inköpsorderinteckningar och budgetanslag.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JournalizingDefinition, JournalizingDefinitionTrans
audience: Application User
ms.reviewer: roschlom
ms.custom: 15772
ms.assetid: 3864e4da-853f-403d-b906-79631d80b363
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8dbbc727120f5292a3ad94711cf79138b35593bf
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5235147"
---
# <a name="posting-definition-examples"></a><span data-ttu-id="f72a6-103">Exempel: bokföringsdefinitioner</span><span class="sxs-lookup"><span data-stu-id="f72a6-103">Posting definition examples</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f72a6-104">Denna artikel innehåller exempel som visar hur du använder bokföringsdefinitioner för inköpsorderinteckningar och budgetanslag.</span><span class="sxs-lookup"><span data-stu-id="f72a6-104">This article provides examples that show how posting definitions are used for purchase order encumbrances and budget appropriations.</span></span>

<span data-ttu-id="f72a6-105">Innan du läser det här avsnittet, ska du känna till bokföringsdefinitioner och bokföringsdefinitioner för transaktioner.</span><span class="sxs-lookup"><span data-stu-id="f72a6-105">Before you read this topic, you should be familiar with posting definitions and transaction posting definitions.</span></span> <span data-ttu-id="f72a6-106">Mer information finns i [Bokföringsdefinitioner](posting-definitions.md).</span><span class="sxs-lookup"><span data-stu-id="f72a6-106">For information, see [Posting definitions](posting-definitions.md).</span></span> <span data-ttu-id="f72a6-107">Följande exempel kan ställas in på sidan **Bokföringsdefinitioner**.</span><span class="sxs-lookup"><span data-stu-id="f72a6-107">The following examples can be set up on the **Posting definitions** page.</span></span> <span data-ttu-id="f72a6-108">Varje exempel innehåller följande ämnen:</span><span class="sxs-lookup"><span data-stu-id="f72a6-108">Each example contains these sections:</span></span>

-   <span data-ttu-id="f72a6-109">Bokföringsdefinition – matchvillkor</span><span class="sxs-lookup"><span data-stu-id="f72a6-109">Posting definition – Match criteria</span></span>
-   <span data-ttu-id="f72a6-110">Bokföringsdefinition – genererade poster</span><span class="sxs-lookup"><span data-stu-id="f72a6-110">Posting definition – Generated entries</span></span>
-   <span data-ttu-id="f72a6-111">Transaktioner med konton, dimensionsvärden och belopp</span><span class="sxs-lookup"><span data-stu-id="f72a6-111">Transactions with the accounts, dimension values, and amounts</span></span>
-   <span data-ttu-id="f72a6-112">Redovisningposter som genereras med bokföringsdefinitionen</span><span class="sxs-lookup"><span data-stu-id="f72a6-112">Ledger entries generated from the posting definition</span></span>

<span data-ttu-id="f72a6-113">När en matchaning uppstår mellan kontona och dimensionsvärdena i fönstret **Matchvillkor** för bokföringsdefinitionen och konton och dimensionsvärden på transaktionen, redovisningsposter genereras baserat på fönstret **Genererade poster** för bokföringsdefinitionen.</span><span class="sxs-lookup"><span data-stu-id="f72a6-113">When a match occurs between the accounts and dimension values in the **Match criteria** pane for the posting definition and the accounts and dimension values on the transaction, ledger entries are generated based on the **Generated entries** pane for the posting definition.</span></span> 
> [!NOTE]
> <span data-ttu-id="f72a6-114">Använd sidan **Bokföringsdefinitioner för transaktioner** för att koppla en bokföringsdefinition till en specifik transaktionstyp.</span><span class="sxs-lookup"><span data-stu-id="f72a6-114">To associate a posting definition with a specific transaction type, use the **Transaction posting definitions** page.</span></span> <span data-ttu-id="f72a6-115">När du associerar en bokföringsdefinition med en transaktionstyp och väljer **Använd bokföringsdefinitioner** på sidan **Redovisningsparametrar**, måste samtliga transaktioner av vald transaktionstyp använda bokföringsdefinitioner.</span><span class="sxs-lookup"><span data-stu-id="f72a6-115">After you associate a posting definition with a transaction type and select **Use posting definitions** on the **General ledger parameters** page, all transactions of the selected transaction type must use posting definitions.</span></span>

## <a name="example-purchase-order-encumbrances"></a><span data-ttu-id="f72a6-116">Exempel: Inköpsorderinteckningar</span><span class="sxs-lookup"><span data-stu-id="f72a6-116">Example: Purchase order encumbrances</span></span>
<span data-ttu-id="f72a6-117">När du aktiverar inteckningsbearbetning genom att välja **Aktivera inteckningsprocess** på sidan **Allmänna redovisningsparametrar**, måste bokföringsdefinitioner användas för att registrera inteckningar i redovisningen för alla konton som ska reserveras.</span><span class="sxs-lookup"><span data-stu-id="f72a6-117">When you enable encumbrance processing by selecting **Enable encumbrance process** on the **General ledger parameters** page, posting definitions must be used to record encumbrances to the general ledger for any accounts that should be reserved.</span></span> <span data-ttu-id="f72a6-118">I de flesta fall reserveras alla utgiftskonton i balansräkningen.</span><span class="sxs-lookup"><span data-stu-id="f72a6-118">In most cases, all expense accounts are reserved on the balance sheet.</span></span> 

<span data-ttu-id="f72a6-119">Bokföringsdefinitioner för inteckningar är inställda för modulen **Inköp** på sidan **Bokföringsdefinitioner**.</span><span class="sxs-lookup"><span data-stu-id="f72a6-119">Posting definitions for encumbrances are set up for the **Purchasing** module on the **Posting definitions** page.</span></span> <span data-ttu-id="f72a6-120">I området **Inköp** på sidan **Bokföringsdefinitioner för transaktioner** kan du välja sidan **Inköpsorder** transaktionstyp för att associera bokföringsdefinitionen med inköpsorder.</span><span class="sxs-lookup"><span data-stu-id="f72a6-120">Then, in the **Purchasing** area of the **Transaction posting definitions** page, you can select the **Purchase order** transaction type to associate the posting definition with purchase orders.</span></span> 

<span data-ttu-id="f72a6-121">Alla verifikationstransaktioner för inköpsorderinteckningar måste balanseras (detta betyder att debet måste vara lika med kredit), i varje unik dimension på en verifikation.</span><span class="sxs-lookup"><span data-stu-id="f72a6-121">All voucher transactions for purchase order encumbrances must balance (that is, debits must equal credits) in each unique dimension on a voucher.</span></span>

### <a name="posting-definition--match-criteria"></a><span data-ttu-id="f72a6-122">Bokföringsdefinition – matchvillkor</span><span class="sxs-lookup"><span data-stu-id="f72a6-122">Posting definition – Match criteria</span></span>

| <span data-ttu-id="f72a6-123">Kontostruktur</span><span class="sxs-lookup"><span data-stu-id="f72a6-123">Account structure</span></span>       | <span data-ttu-id="f72a6-124">Matcha kontonummer</span><span class="sxs-lookup"><span data-stu-id="f72a6-124">Match account number</span></span> | <span data-ttu-id="f72a6-125">Prioritet </span><span class="sxs-lookup"><span data-stu-id="f72a6-125">Priority</span></span> |
|-------------------------|----------------------|----------|
| <span data-ttu-id="f72a6-126">Kontostruktur – Resultat</span><span class="sxs-lookup"><span data-stu-id="f72a6-126">Account Structure - P&L</span></span> | \*                   | <span data-ttu-id="f72a6-127">1</span><span class="sxs-lookup"><span data-stu-id="f72a6-127">1</span></span>        |

<span data-ttu-id="f72a6-128"><em>Ett mellanrumsvärde i fältet \**Matchningskontonummer</em>* betyder att alla matchningskonton i den definierade kontostrukturen är en del av matchningsregeln.</span><span class="sxs-lookup"><span data-stu-id="f72a6-128"><em>A blank value in the \**Match account number</em>* field means that all matching accounts in the defined account structure are part of the matching rule.</span></span>

### <a name="posting-definition--generated-entries"></a><span data-ttu-id="f72a6-129">Bokföringsdefinition – genererade poster</span><span class="sxs-lookup"><span data-stu-id="f72a6-129">Posting definition – Generated entries</span></span>

| <span data-ttu-id="f72a6-130">Kontostruktur</span><span class="sxs-lookup"><span data-stu-id="f72a6-130">Account structure</span></span> | <span data-ttu-id="f72a6-131">Genererat kontonummer</span><span class="sxs-lookup"><span data-stu-id="f72a6-131">Generated account number</span></span>                    | <span data-ttu-id="f72a6-132">Debet/kredit har skapats</span><span class="sxs-lookup"><span data-stu-id="f72a6-132">Generated debit/credit</span></span> |
|-------------------|---------------------------------------------|------------------------|
| <span data-ttu-id="f72a6-133">Saldo</span><span class="sxs-lookup"><span data-stu-id="f72a6-133">Balance</span></span>           | <span data-ttu-id="f72a6-134">300143 – (Inteckningkonto)</span><span class="sxs-lookup"><span data-stu-id="f72a6-134">300143 - -(Encumbrance account)</span></span>             | <span data-ttu-id="f72a6-135">Samma</span><span class="sxs-lookup"><span data-stu-id="f72a6-135">Same</span></span>                   |
| <span data-ttu-id="f72a6-136">Saldo</span><span class="sxs-lookup"><span data-stu-id="f72a6-136">Balance</span></span>           | <span data-ttu-id="f72a6-137">300144 – - (Reservera för inteckningkonto)</span><span class="sxs-lookup"><span data-stu-id="f72a6-137">300144 - -(Reserve for encumbrance account)</span></span> | <span data-ttu-id="f72a6-138">Balanserar</span><span class="sxs-lookup"><span data-stu-id="f72a6-138">Balancing</span></span>              |

### <a name="transactions-with-the-accounts-dimension-values-and-amounts"></a><span data-ttu-id="f72a6-139">Transaktioner med konton, dimensionsvärden och belopp</span><span class="sxs-lookup"><span data-stu-id="f72a6-139">Transactions with the accounts, dimension values, and amounts</span></span>

<span data-ttu-id="f72a6-140">Kontona och dimensionsvärden kommer antingen från redovisningsfördelningarna, som du anger för en inköpsorderrad, eller från konton och dimensioner som genereras automatiskt baserat på standardinställningarna för leverantörer, artiklar, kategorier och dimensionsmallar.</span><span class="sxs-lookup"><span data-stu-id="f72a6-140">The accounts and dimension values come either from the accounting distributions that you enter for a purchase order line, or from the accounts and dimensions that are automatically generated based on the default settings for vendors, items, categories, and dimension templates.</span></span>

| <span data-ttu-id="f72a6-141">Konto + dimensioner</span><span class="sxs-lookup"><span data-stu-id="f72a6-141">Account + dimensions</span></span>           | <span data-ttu-id="f72a6-142">Debet</span><span class="sxs-lookup"><span data-stu-id="f72a6-142">Debit</span></span>  | <span data-ttu-id="f72a6-143">Kredit</span><span class="sxs-lookup"><span data-stu-id="f72a6-143">Credit</span></span> | <span data-ttu-id="f72a6-144">Kommentar</span><span class="sxs-lookup"><span data-stu-id="f72a6-144">Comment</span></span> |
|--------------------------------|--------|--------|---------|
| <span data-ttu-id="f72a6-145">606400-OU\_1-OU\_3566-Training</span><span class="sxs-lookup"><span data-stu-id="f72a6-145">606400-OU\_1-OU\_3566-Training</span></span> | <span data-ttu-id="f72a6-146">250.00</span><span class="sxs-lookup"><span data-stu-id="f72a6-146">250.00</span></span> |        |         |

### <a name="ledger-entries-generated-from-the-posting-definition"></a><span data-ttu-id="f72a6-147">Redovisningposter som genereras med bokföringsdefinitionen</span><span class="sxs-lookup"><span data-stu-id="f72a6-147">Ledger entries generated from the posting definition</span></span>

<span data-ttu-id="f72a6-148">Genererade redovisningsposter skapas för att registrera inteckningarna.</span><span class="sxs-lookup"><span data-stu-id="f72a6-148">Generated ledger entries are created to record the encumbrances.</span></span>

| <span data-ttu-id="f72a6-149">Konto + dimensioner</span><span class="sxs-lookup"><span data-stu-id="f72a6-149">Account + dimensions</span></span>           | <span data-ttu-id="f72a6-150">Debet</span><span class="sxs-lookup"><span data-stu-id="f72a6-150">Debit</span></span>  | <span data-ttu-id="f72a6-151">Kredit</span><span class="sxs-lookup"><span data-stu-id="f72a6-151">Credit</span></span> | <span data-ttu-id="f72a6-152">Kommentar</span><span class="sxs-lookup"><span data-stu-id="f72a6-152">Comment</span></span> |
|--------------------------------|--------|--------|---------|
| <span data-ttu-id="f72a6-153">300143-OU\_1-OU\_3566-utbildning</span><span class="sxs-lookup"><span data-stu-id="f72a6-153">300143-OU\_1-OU\_3566-Training</span></span> | <span data-ttu-id="f72a6-154">250.00</span><span class="sxs-lookup"><span data-stu-id="f72a6-154">250.00</span></span> |        |         |
| <span data-ttu-id="f72a6-155">300144-OU\_1-OU\_3566-Training</span><span class="sxs-lookup"><span data-stu-id="f72a6-155">300144-OU\_1-OU\_3566-Training</span></span> |        | <span data-ttu-id="f72a6-156">250.00</span><span class="sxs-lookup"><span data-stu-id="f72a6-156">250.00</span></span> |         |

<span data-ttu-id="f72a6-157">I det här exemplet matchar alla konton, som är en del av kontostrukturen – Resultat matchar bokföringsdefinitionvillkoren.</span><span class="sxs-lookup"><span data-stu-id="f72a6-157">In this example, any account that is part of Account Structure - P&L matches the posting definition criteria.</span></span> <span data-ttu-id="f72a6-158">När 606500-OU\_1-OU\_3566-utbildning ska utvärderas, genereras därför poster för de konton som anges i fönstret **Genererade poster** för bokföringsdefinitionen.</span><span class="sxs-lookup"><span data-stu-id="f72a6-158">Therefore, when 606500-OU\_1-OU\_3566-Training is evaluated, generated entries are created for the accounts that are defined in the **Generated entries** pane for the posting definition.</span></span>

## <a name="example-budget-appropriations"></a><span data-ttu-id="f72a6-159">Exempel: Budgetanslag</span><span class="sxs-lookup"><span data-stu-id="f72a6-159">Example: Budget appropriations</span></span>
<span data-ttu-id="f72a6-160">När du aktiverar budgettransaktioner genom att välja **Aktivera budgetanslag** på sidan **Allmänna redovisningsparametrar**, måste bokföringsdefinitioner användas för att bokföra budgetregisterposter i redovisningen.</span><span class="sxs-lookup"><span data-stu-id="f72a6-160">When you enable budget appropriation by selecting **Enable budget appropriation** on the **General ledger parameters** page, posting definitions must be used to record budget register entries to the general ledger.</span></span> <span data-ttu-id="f72a6-161">När en budgetkontrollkonfiguration är aktiv och aktiveras, kan bokföringsdefinitioner och transaktionbokföringsdefinitioner användas som stöd för registreringen av poster för anslag, ändringar, överföringar, projekt, anläggningstillgångar och leverans- och efterfrågeprognoser i redovisningen.</span><span class="sxs-lookup"><span data-stu-id="f72a6-161">When a budget control configuration is active and is turned on, posting definitions and transaction posting definitions can be used to support the recording of entries for appropriations, revisions, transfers, projects, fixed assets, and supply and demand forecasts to the general ledger.</span></span> 

<span data-ttu-id="f72a6-162">Om du vill ställa in en bokföringsdefinition för budgetregisterposter som har budgettypen **Ursprunglig budget** och som har anslag aktiverade, välj modulen **Budget** på sidan **Bokföringsdefinitioner** .</span><span class="sxs-lookup"><span data-stu-id="f72a6-162">To set up a posting definition for budget register entries that has a budget type of **Original budget**, and that has appropriations enabled, select the **Budget** module on the **Posting definitions** page.</span></span> <span data-ttu-id="f72a6-163">Sedan i området **Budget** på sidan **Bokföringsdefinitioner för transaktioner** kan du använda budgetkoder för att koppla bokföringsdefinitionen med budgetregisterposter som ha budgettypen **Ursprunglig budget**</span><span class="sxs-lookup"><span data-stu-id="f72a6-163">Then, in the **Budget** area of the **Transaction posting definitions** page, you can use budget codes to associate the posting definition with budget register entries that have a budget type of **Original budget**.</span></span> 

<span data-ttu-id="f72a6-164">När budgetanslag och budgeterade bokföringsdefinitioner aktiveras, registreras de här registerposterna för budgetkontroll och i redovisningen.</span><span class="sxs-lookup"><span data-stu-id="f72a6-164">When budget appropriations and posting definitions are enabled, the budget register entries are recorded for budget control and in the general ledger.</span></span>

### <a name="posting-definition--match-criteria"></a><span data-ttu-id="f72a6-165">Bokföringsdefinition – matchvillkor</span><span class="sxs-lookup"><span data-stu-id="f72a6-165">Posting definition – Match criteria</span></span>

| <span data-ttu-id="f72a6-166">Kontostruktur</span><span class="sxs-lookup"><span data-stu-id="f72a6-166">Account structure</span></span>       | <span data-ttu-id="f72a6-167">Matcha kontonummer</span><span class="sxs-lookup"><span data-stu-id="f72a6-167">Match account number</span></span> | <span data-ttu-id="f72a6-168">Prioritet </span><span class="sxs-lookup"><span data-stu-id="f72a6-168">Priority</span></span> |
|-------------------------|----------------------|----------|
| <span data-ttu-id="f72a6-169">Kontostruktur – Resultat</span><span class="sxs-lookup"><span data-stu-id="f72a6-169">Account Structure - P&L</span></span> | \*                   | <span data-ttu-id="f72a6-170">1</span><span class="sxs-lookup"><span data-stu-id="f72a6-170">1</span></span>        |

<span data-ttu-id="f72a6-171"><em>Ett mellanrumsvärde i fältet \**Matchningskontonummer</em>* betyder att alla matchningskonton i den definierade kontostrukturen är en del av matchningsregeln.</span><span class="sxs-lookup"><span data-stu-id="f72a6-171"><em>A blank value in the \**Match account number</em>* field means that all matching accounts in the defined account structure are part of the matching rule.</span></span>

### <a name="posting-definition--generated-entries"></a><span data-ttu-id="f72a6-172">Bokföringsdefinition – genererade poster</span><span class="sxs-lookup"><span data-stu-id="f72a6-172">Posting definition – Generated entries</span></span>

| <span data-ttu-id="f72a6-173">Kontostruktur</span><span class="sxs-lookup"><span data-stu-id="f72a6-173">Account structure</span></span> | <span data-ttu-id="f72a6-174">Genererat kontonummer</span><span class="sxs-lookup"><span data-stu-id="f72a6-174">Generated account number</span></span>              | <span data-ttu-id="f72a6-175">Debet/kredit har skapats</span><span class="sxs-lookup"><span data-stu-id="f72a6-175">Generated debit/credit</span></span> |
|-------------------|---------------------------------------|------------------------|
| <span data-ttu-id="f72a6-176">Kontostruktur</span><span class="sxs-lookup"><span data-stu-id="f72a6-176">Account structure</span></span> | <span data-ttu-id="f72a6-177">300145 – - (uppskattad intäkt)</span><span class="sxs-lookup"><span data-stu-id="f72a6-177">300145 - -(Estimated revenue account)</span></span> | <span data-ttu-id="f72a6-178">Samma</span><span class="sxs-lookup"><span data-stu-id="f72a6-178">Same</span></span>                   |
| <span data-ttu-id="f72a6-179">Kontostruktur</span><span class="sxs-lookup"><span data-stu-id="f72a6-179">Account structure</span></span> | <span data-ttu-id="f72a6-180">300146 – (Anslagskonto)</span><span class="sxs-lookup"><span data-stu-id="f72a6-180">300146 - -(Appropriation account)</span></span>     | <span data-ttu-id="f72a6-181">Balanserar</span><span class="sxs-lookup"><span data-stu-id="f72a6-181">Balancing</span></span>              |

### <a name="transactions-with-the-accounts-dimension-values-and-amounts"></a><span data-ttu-id="f72a6-182">Transaktioner med konton, dimensionsvärden och belopp</span><span class="sxs-lookup"><span data-stu-id="f72a6-182">Transactions with the accounts, dimension values, and amounts</span></span>

<span data-ttu-id="f72a6-183">Du anger konton, dimensionsvärden och belopp för budgetkontoposten på sidan **Budgetregisterpost**.</span><span class="sxs-lookup"><span data-stu-id="f72a6-183">You enter the accounts, dimension values, and amounts for the budget account entry on the **Budget register entry** page.</span></span>

| <span data-ttu-id="f72a6-184">Konto + dimensioner</span><span class="sxs-lookup"><span data-stu-id="f72a6-184">Account + dimensions</span></span>           | <span data-ttu-id="f72a6-185">Debet</span><span class="sxs-lookup"><span data-stu-id="f72a6-185">Debit</span></span> | <span data-ttu-id="f72a6-186">Kredit</span><span class="sxs-lookup"><span data-stu-id="f72a6-186">Credit</span></span> | <span data-ttu-id="f72a6-187">Kommentar</span><span class="sxs-lookup"><span data-stu-id="f72a6-187">Comment</span></span> |
|--------------------------------|-------|--------|---------|
| <span data-ttu-id="f72a6-188">606400-OU\_1-OU\_3566-Training</span><span class="sxs-lookup"><span data-stu-id="f72a6-188">606400-OU\_1-OU\_3566-Training</span></span> |       | <span data-ttu-id="f72a6-189">250.00</span><span class="sxs-lookup"><span data-stu-id="f72a6-189">250.00</span></span> |         |

### <a name="ledger-entries-generated-from-the-posting-definition"></a><span data-ttu-id="f72a6-190">Redovisningposter som genereras med bokföringsdefinitionen</span><span class="sxs-lookup"><span data-stu-id="f72a6-190">Ledger entries generated from the posting definition</span></span>

<span data-ttu-id="f72a6-191">Genererade redovisningsposter skapas för att registrera den ursprungliga budgeten i varje dimension.</span><span class="sxs-lookup"><span data-stu-id="f72a6-191">Generated ledger entries are created to record the original budget in each dimension.</span></span>

| <span data-ttu-id="f72a6-192">Konto + dimensioner</span><span class="sxs-lookup"><span data-stu-id="f72a6-192">Account + dimensions</span></span>           | <span data-ttu-id="f72a6-193">Debet</span><span class="sxs-lookup"><span data-stu-id="f72a6-193">Debit</span></span>  | <span data-ttu-id="f72a6-194">Kredit</span><span class="sxs-lookup"><span data-stu-id="f72a6-194">Credit</span></span> | <span data-ttu-id="f72a6-195">Kommentar</span><span class="sxs-lookup"><span data-stu-id="f72a6-195">Comment</span></span> |
|--------------------------------|--------|--------|---------|
| <span data-ttu-id="f72a6-196">300145-OU\_1-OU\_3566-Training</span><span class="sxs-lookup"><span data-stu-id="f72a6-196">300145-OU\_1-OU\_3566-Training</span></span> |        | <span data-ttu-id="f72a6-197">250.00</span><span class="sxs-lookup"><span data-stu-id="f72a6-197">250.00</span></span> |         |
| <span data-ttu-id="f72a6-198">300146-OU\_1-OU\_3566-Training</span><span class="sxs-lookup"><span data-stu-id="f72a6-198">300146-OU\_1-OU\_3566-Training</span></span> | <span data-ttu-id="f72a6-199">250.00</span><span class="sxs-lookup"><span data-stu-id="f72a6-199">250.00</span></span> |        |         |

<span data-ttu-id="f72a6-200">I det här exemplet matchar alla konton, som är en del av kontostrukturen – Resultat matchar bokföringsdefinitionvillkoren.</span><span class="sxs-lookup"><span data-stu-id="f72a6-200">In this example, any account that is part of Account Structure - P&L matches the posting definition criteria.</span></span> <span data-ttu-id="f72a6-201">När 606400-OU\_1-OU\_3566-utbildning utvärderas, skapas därför genererade bokföringsposter.</span><span class="sxs-lookup"><span data-stu-id="f72a6-201">Therefore, when 606400-OU\_1-OU\_3566-Training is evaluated, the generated ledger entries are created.</span></span>







[!INCLUDE[footer-include](../../includes/footer-banner.md)]