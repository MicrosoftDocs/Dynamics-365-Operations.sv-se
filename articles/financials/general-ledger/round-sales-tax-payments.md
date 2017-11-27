---
title: Momsbetalningar och avrundningregler
description: "Den här artikeln beskriver hur avrundningsregelinställningar på skattemyndigheter fungerar och avrundning av momssaldot under jobbet Kvitta och bokför moms."
author: twheeloc
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: TaxAuthority
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 6134
ms.assetid: 7dcd3cf5-ebdf-4a9f-806c-1296c7da0331
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 13470282efc6b9135e86355cf8071b841aad3071
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="sales-tax-payments-and-rounding-rules"></a><span data-ttu-id="06a29-103">Momsbetalningar och avrundningregler</span><span class="sxs-lookup"><span data-stu-id="06a29-103">Sales tax payments and rounding rules</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="06a29-104">Den här artikeln beskriver hur avrundningsregelinställningar på skattemyndigheter fungerar och avrundning av momssaldot under jobbet Kvitta och bokför moms.</span><span class="sxs-lookup"><span data-stu-id="06a29-104">This article explains how the rounding rule setup on the Sales tax authorities works and rounding the sales tax balance during the Settle and post sales tax job.</span></span>

<span data-ttu-id="06a29-105">Moms måste regelbundet rapporteras och betalas till skattemyndigheten.</span><span class="sxs-lookup"><span data-stu-id="06a29-105">Periodically, sales tax needs to be reported and paid to tax authorities.</span></span> <span data-ttu-id="06a29-106">Detta gör du genom att köra kvittnings- och bokföringsmomsprocess på sidan Moms.</span><span class="sxs-lookup"><span data-stu-id="06a29-106">This can be done by running the settle and post sales tax process in the Sales tax page.</span></span> <span data-ttu-id="06a29-107">Moms för en period kommer att kvittas mot momskontona och momssaldot kommer att bokföras på momskvittningskontot.</span><span class="sxs-lookup"><span data-stu-id="06a29-107">Sales tax for a period will be settled against the sales tax accounts and the sales tax balance will be posted to the Sales tax settlement account.</span></span> <span data-ttu-id="06a29-108">Momssaldot som bokförs på momskvittningskontot, kan avrundas enligt som krävs av skattemyndigheten genom att ställa in en avrundningsregel på sidan Moms.</span><span class="sxs-lookup"><span data-stu-id="06a29-108">The sales tax balance, which is posted on the Sales tax settlement account, can be rounded as required by tax authorities by setting up a rounding rule on the Sales tax page.</span></span> 

<span data-ttu-id="06a29-109">Avrundningsdifferensen bokförs på Momsavrundningkontot som valts i fältet Konton för automatisk transaktion i huvudboken.</span><span class="sxs-lookup"><span data-stu-id="06a29-109">The rounding difference is posted to the Sales tax rounding account that is selected in the Accounts for automatic transactions field in the General ledger.</span></span>

<span data-ttu-id="06a29-110">Exemplet nedanför illustrerar hur avrundningsregeln fungerar för Skattemyndigheten.</span><span class="sxs-lookup"><span data-stu-id="06a29-110">The below example illustrates how the rounding rule on Sales tax authority works.</span></span>

### <a name="example"></a><span data-ttu-id="06a29-111">Exempel:</span><span class="sxs-lookup"><span data-stu-id="06a29-111">Example:</span></span>

<span data-ttu-id="06a29-112">Det totala momsen för en period visar ett kreditsaldo på -98 765,43.</span><span class="sxs-lookup"><span data-stu-id="06a29-112">The total sales tax for a period shows a credit balance of -98,765.43.</span></span> <span data-ttu-id="06a29-113">Den juridiska personen samlade in mer moms än vad som har betalats.</span><span class="sxs-lookup"><span data-stu-id="06a29-113">The legal entity collected more sales taxes than it paid.</span></span> <span data-ttu-id="06a29-114">Därför är den juridiska personen skyldig pengar till skattemyndigheten.</span><span class="sxs-lookup"><span data-stu-id="06a29-114">Therefore, the legal entity owes money to the tax authority.</span></span> 

<span data-ttu-id="06a29-115">Den juridiska personen vill använda en avrundningsmetod som rundar av saldot till närmaste hela 1,00.</span><span class="sxs-lookup"><span data-stu-id="06a29-115">The legal entity wants to use a rounding method that rounds the balance to the nearest 1.00.</span></span> <span data-ttu-id="06a29-116">Användaren som ansvarar för momsredovisningen måste då göra följande steg.</span><span class="sxs-lookup"><span data-stu-id="06a29-116">The user who is responsible for sales tax accounting performs the following steps.</span></span>

1.  <span data-ttu-id="06a29-117">Klicka på Skatt &gt; Indirekt moms &gt; Moms &gt; Skattemyndigheter</span><span class="sxs-lookup"><span data-stu-id="06a29-117">Click Tax &gt; Indirect taxes &gt; Sales tax &gt; Sales tax authorities</span></span>
2.  <span data-ttu-id="06a29-118">I snabbfliken Standard, välj Normal i fältet Avrundningssätt.</span><span class="sxs-lookup"><span data-stu-id="06a29-118">On the General FastTab, select Normal in the Rounding form field.</span></span>
3.  <span data-ttu-id="06a29-119">I fältet Avrundning anger du 1,00.</span><span class="sxs-lookup"><span data-stu-id="06a29-119">In the Round-off field, enter 1.00.</span></span>
4.  <span data-ttu-id="06a29-120">När det är dags att betala moms till skattemyndigheten öppnar du Kvitta och bokför moms.</span><span class="sxs-lookup"><span data-stu-id="06a29-120">When it is time to pay the sales taxes to the tax authority, open the Settle and post sales tax page.</span></span> <span data-ttu-id="06a29-121">(Klicka på Skatt &gt; Deklarationer &gt; Moms &gt; Kvitta och bokför moms.)</span><span class="sxs-lookup"><span data-stu-id="06a29-121">(Click Tax &gt; Declarations &gt; Sales tax &gt; Settle and post sales tax.)</span></span>
5.  <span data-ttu-id="06a29-122">På momskvittningkontot avrundas skatteskuldbeloppet på 98 765,43 till 98 765.</span><span class="sxs-lookup"><span data-stu-id="06a29-122">On the sales tax settlement account, the tax liability amount of 98,765.43 is rounded to 98,765.</span></span>

<span data-ttu-id="06a29-123">Följande tabell visar hur ett belopp på 98 765,43 avrundas med hjälp av varje avrundningsmetod som är tillgänglig i fältet Avrundningsätt på sidan Skattemyndigheten.</span><span class="sxs-lookup"><span data-stu-id="06a29-123">The following table shows how an amount of 98,765.43 is rounded by using each rounding method that is available in the Rounding form field in the Sales tax authorities page.</span></span>

| <span data-ttu-id="06a29-124">Aternativ för avrundningssätt</span><span class="sxs-lookup"><span data-stu-id="06a29-124">Rounding form option</span></span>                | <span data-ttu-id="06a29-125">Avrundningsvärde = 0,01</span><span class="sxs-lookup"><span data-stu-id="06a29-125">Round-off value = 0.01</span></span> | <span data-ttu-id="06a29-126">Avrundningsvärde = 0,10</span><span class="sxs-lookup"><span data-stu-id="06a29-126">Round-off value = 0.10</span></span> | <span data-ttu-id="06a29-127">Avrundningsvärde = 1,00</span><span class="sxs-lookup"><span data-stu-id="06a29-127">Round-off value = 1.00</span></span> | <span data-ttu-id="06a29-128">Avrundningsvärde = 100,00</span><span class="sxs-lookup"><span data-stu-id="06a29-128">Round-off value = 100.00</span></span> |
|-------------------------------------|------------------------|------------------------|------------------------|--------------------------|
| <span data-ttu-id="06a29-129">Normal</span><span class="sxs-lookup"><span data-stu-id="06a29-129">Normal</span></span>                              | <span data-ttu-id="06a29-130">98 765,43</span><span class="sxs-lookup"><span data-stu-id="06a29-130">98,765.43</span></span>              | <span data-ttu-id="06a29-131">98 765,40</span><span class="sxs-lookup"><span data-stu-id="06a29-131">98,765.40</span></span>              | <span data-ttu-id="06a29-132">98 765,00</span><span class="sxs-lookup"><span data-stu-id="06a29-132">98,765.00</span></span>              | <span data-ttu-id="06a29-133">98 800,00</span><span class="sxs-lookup"><span data-stu-id="06a29-133">98,800.00</span></span>                |
| <span data-ttu-id="06a29-134">Nedåt</span><span class="sxs-lookup"><span data-stu-id="06a29-134">Downward</span></span>                            | <span data-ttu-id="06a29-135">98 765,43</span><span class="sxs-lookup"><span data-stu-id="06a29-135">98,765.43</span></span>              | <span data-ttu-id="06a29-136">98 765,40</span><span class="sxs-lookup"><span data-stu-id="06a29-136">98,765.40</span></span>              | <span data-ttu-id="06a29-137">98 765,00</span><span class="sxs-lookup"><span data-stu-id="06a29-137">98,765.00</span></span>              | <span data-ttu-id="06a29-138">98 700,00</span><span class="sxs-lookup"><span data-stu-id="06a29-138">98,700.00</span></span>                |
| <span data-ttu-id="06a29-139">Uppåt</span><span class="sxs-lookup"><span data-stu-id="06a29-139">Rounding-up</span></span>                         | <span data-ttu-id="06a29-140">98 765,43</span><span class="sxs-lookup"><span data-stu-id="06a29-140">98,765.43</span></span>              | <span data-ttu-id="06a29-141">98 765,50</span><span class="sxs-lookup"><span data-stu-id="06a29-141">98,765.50</span></span>              | <span data-ttu-id="06a29-142">98 766,00</span><span class="sxs-lookup"><span data-stu-id="06a29-142">98,766.00</span></span>              | <span data-ttu-id="06a29-143">98 800,00</span><span class="sxs-lookup"><span data-stu-id="06a29-143">98,800.00</span></span>                |
| <span data-ttu-id="06a29-144">Egen fördel, för ett kreditsaldo</span><span class="sxs-lookup"><span data-stu-id="06a29-144">Own advantage, for a credit balance</span></span> | <span data-ttu-id="06a29-145">98 765,43</span><span class="sxs-lookup"><span data-stu-id="06a29-145">98,765.43</span></span>              | <span data-ttu-id="06a29-146">98 765,40</span><span class="sxs-lookup"><span data-stu-id="06a29-146">98,765.40</span></span>              | <span data-ttu-id="06a29-147">98 765,00</span><span class="sxs-lookup"><span data-stu-id="06a29-147">98,765.00</span></span>              | <span data-ttu-id="06a29-148">98 700,00</span><span class="sxs-lookup"><span data-stu-id="06a29-148">98,700.00</span></span>                |
| <span data-ttu-id="06a29-149">Egen fördel, för ett debetsaldo</span><span class="sxs-lookup"><span data-stu-id="06a29-149">Own advantage, for a debit balance</span></span>  | <span data-ttu-id="06a29-150">98 765,43</span><span class="sxs-lookup"><span data-stu-id="06a29-150">98,765.43</span></span>              | <span data-ttu-id="06a29-151">98 765,50</span><span class="sxs-lookup"><span data-stu-id="06a29-151">98,765.50</span></span>              | <span data-ttu-id="06a29-152">98 766,00</span><span class="sxs-lookup"><span data-stu-id="06a29-152">98,766.00</span></span>              | <span data-ttu-id="06a29-153">98 800,00</span><span class="sxs-lookup"><span data-stu-id="06a29-153">98,800.00</span></span>                |

> [!NOTE]                                                                                  
> <span data-ttu-id="06a29-154">Om du väljer Egen fördel är alltid avrundningen till fördelen för den juridiska personen.</span><span class="sxs-lookup"><span data-stu-id="06a29-154">If you select Own advantage, the rounding is always to the advantage of the legal entity.</span></span> 

<span data-ttu-id="06a29-155">Mer information finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="06a29-155">For more information, see the following topics:</span></span>
- [<span data-ttu-id="06a29-156">Momsöversikt</span><span class="sxs-lookup"><span data-stu-id="06a29-156">Sales tax overview</span></span>](indirect-taxes-overview.md)
- [<span data-ttu-id="06a29-157">Skapa en momsbetalning</span><span class="sxs-lookup"><span data-stu-id="06a29-157">Create a sales tax payment</span></span>](tasks/create-sales-tax-payment.md)
- [<span data-ttu-id="06a29-158">Skapa försäljningstransaktioner i dokument</span><span class="sxs-lookup"><span data-stu-id="06a29-158">Create sales transactions on documents</span></span>](tasks/create-sales-tax-transactions-documents.md)
- [<span data-ttu-id="06a29-159">Visa bokförda momstransaktioner</span><span class="sxs-lookup"><span data-stu-id="06a29-159">View posted sales tax transactions</span></span>](tasks/view-posted-sales-tax-transactions.md)



