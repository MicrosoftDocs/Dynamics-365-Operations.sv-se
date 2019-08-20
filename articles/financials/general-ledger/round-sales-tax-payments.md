---
title: Momsbetalningar och avrundningregler
description: Den här artikeln beskriver hur avrundningsregelinställningar på skattemyndigheter fungerar och avrundning av momssaldot under jobbet Kvitta och bokför moms.
author: ShylaThompson
manager: AnnBe
ms.date: 05/30/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxAuthority
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 6134
ms.assetid: 7dcd3cf5-ebdf-4a9f-806c-1296c7da0331
ms.search.region: Global
ms.author: yijialuan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 168c2fb9edfc994617ef6764a5b9f5949d599882
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2019
ms.locfileid: "1835008"
---
# <a name="sales-tax-payments-and-rounding-rules"></a><span data-ttu-id="03ef8-103">Momsbetalningar och avrundningregler</span><span class="sxs-lookup"><span data-stu-id="03ef8-103">Sales tax payments and rounding rules</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="03ef8-104">Den här artikeln beskriver hur avrundningsregelinställningar på skattemyndigheter fungerar och avrundning av momssaldot under jobbet Kvitta och bokför moms.</span><span class="sxs-lookup"><span data-stu-id="03ef8-104">This article explains how the rounding rule setup on the Sales tax authorities works and rounding the sales tax balance during the Settle and post sales tax job.</span></span>

<span data-ttu-id="03ef8-105">Moms måste regelbundet rapporteras och betalas till skattemyndigheten.</span><span class="sxs-lookup"><span data-stu-id="03ef8-105">Periodically, sales tax needs to be reported and paid to tax authorities.</span></span> <span data-ttu-id="03ef8-106">Detta gör du genom att köra kvittnings- och bokföringsmomsprocess på sidan Moms.</span><span class="sxs-lookup"><span data-stu-id="03ef8-106">This can be done by running the settle and post sales tax process in the Sales tax page.</span></span> <span data-ttu-id="03ef8-107">Moms för en period kommer att kvittas mot momskontona och momssaldot kommer att bokföras på momskvittningskontot.</span><span class="sxs-lookup"><span data-stu-id="03ef8-107">Sales tax for a period will be settled against the sales tax accounts and the sales tax balance will be posted to the Sales tax settlement account.</span></span> <span data-ttu-id="03ef8-108">Momssaldot som bokförs på momskvittningskontot, kan avrundas enligt som krävs av skattemyndigheten genom att ställa in en avrundningsregel på sidan Moms.</span><span class="sxs-lookup"><span data-stu-id="03ef8-108">The sales tax balance, which is posted on the Sales tax settlement account, can be rounded as required by tax authorities by setting up a rounding rule on the Sales tax page.</span></span> 

<span data-ttu-id="03ef8-109">Avrundningsdifferensen bokförs på Momsavrundningkontot som valts i fältet Konton för automatisk transaktion i huvudboken.</span><span class="sxs-lookup"><span data-stu-id="03ef8-109">The rounding difference is posted to the Sales tax rounding account that is selected in the Accounts for automatic transactions field in the General ledger.</span></span>

<span data-ttu-id="03ef8-110">Exemplet nedanför illustrerar hur avrundningsregeln fungerar för Skattemyndigheten.</span><span class="sxs-lookup"><span data-stu-id="03ef8-110">The below example illustrates how the rounding rule on Sales tax authority works.</span></span>

## <a name="examples"></a><span data-ttu-id="03ef8-111">Exempel</span><span class="sxs-lookup"><span data-stu-id="03ef8-111">Examples</span></span>

<span data-ttu-id="03ef8-112">Det totala momsen för en period visar ett kreditsaldo på -98 765,43.</span><span class="sxs-lookup"><span data-stu-id="03ef8-112">The total sales tax for a period shows a credit balance of -98,765.43.</span></span> <span data-ttu-id="03ef8-113">Den juridiska personen samlade in mer moms än vad som har betalats.</span><span class="sxs-lookup"><span data-stu-id="03ef8-113">The legal entity collected more sales taxes than it paid.</span></span> <span data-ttu-id="03ef8-114">Därför är den juridiska personen skyldig pengar till skattemyndigheten.</span><span class="sxs-lookup"><span data-stu-id="03ef8-114">Therefore, the legal entity owes money to the tax authority.</span></span> 

<span data-ttu-id="03ef8-115">Den juridiska personen vill använda en avrundningsmetod som rundar av saldot till närmaste hela 1,00.</span><span class="sxs-lookup"><span data-stu-id="03ef8-115">The legal entity wants to use a rounding method that rounds the balance to the nearest 1.00.</span></span> <span data-ttu-id="03ef8-116">Användaren som ansvarar för momsredovisningen måste då göra följande steg.</span><span class="sxs-lookup"><span data-stu-id="03ef8-116">The user who is responsible for sales tax accounting performs the following steps.</span></span>

1.  <span data-ttu-id="03ef8-117">Klicka på Skatt &gt; Indirekt moms &gt; Moms &gt; Skattemyndigheter</span><span class="sxs-lookup"><span data-stu-id="03ef8-117">Click Tax &gt; Indirect taxes &gt; Sales tax &gt; Sales tax authorities</span></span>
2.  <span data-ttu-id="03ef8-118">I snabbfliken Standard, välj Normal i fältet Avrundningssätt.</span><span class="sxs-lookup"><span data-stu-id="03ef8-118">On the General FastTab, select Normal in the Rounding form field.</span></span>
3.  <span data-ttu-id="03ef8-119">I fältet Avrundning anger du 1,00.</span><span class="sxs-lookup"><span data-stu-id="03ef8-119">In the Round-off field, enter 1.00.</span></span>
4.  <span data-ttu-id="03ef8-120">När det är dags att betala moms till skattemyndigheten öppnar du Kvitta och bokför moms.</span><span class="sxs-lookup"><span data-stu-id="03ef8-120">When it is time to pay the sales taxes to the tax authority, open the Settle and post sales tax page.</span></span> <span data-ttu-id="03ef8-121">(Klicka på Skatt &gt; Deklarationer &gt; Moms &gt; Kvitta och bokför moms.)</span><span class="sxs-lookup"><span data-stu-id="03ef8-121">(Click Tax &gt; Declarations &gt; Sales tax &gt; Settle and post sales tax.)</span></span>
5.  <span data-ttu-id="03ef8-122">På momskvittningkontot avrundas skatteskuldbeloppet på 98 765,43 till 98 765.</span><span class="sxs-lookup"><span data-stu-id="03ef8-122">On the sales tax settlement account, the tax liability amount of 98,765.43 is rounded to 98,765.</span></span>

<span data-ttu-id="03ef8-123">Följande tabell visar hur ett belopp på 98 765,43 avrundas med hjälp av varje avrundningsmetod som är tillgänglig i fältet Avrundningsätt på sidan Skattemyndigheten.</span><span class="sxs-lookup"><span data-stu-id="03ef8-123">The following table shows how an amount of 98,765.43 is rounded by using each rounding method that is available in the Rounding form field in the Sales tax authorities page.</span></span>

| <span data-ttu-id="03ef8-124">Aternativ för avrundningssätt</span><span class="sxs-lookup"><span data-stu-id="03ef8-124">Rounding form option</span></span>                | <span data-ttu-id="03ef8-125">Avrundningsvärde = 0,01</span><span class="sxs-lookup"><span data-stu-id="03ef8-125">Round-off value = 0.01</span></span> | <span data-ttu-id="03ef8-126">Avrundningsvärde = 0,10</span><span class="sxs-lookup"><span data-stu-id="03ef8-126">Round-off value = 0.10</span></span> | <span data-ttu-id="03ef8-127">Avrundningsvärde = 1,00</span><span class="sxs-lookup"><span data-stu-id="03ef8-127">Round-off value = 1.00</span></span> | <span data-ttu-id="03ef8-128">Avrundningsvärde = 100,00</span><span class="sxs-lookup"><span data-stu-id="03ef8-128">Round-off value = 100.00</span></span> |
|-------------------------------------|------------------------|------------------------|------------------------|--------------------------|
| <span data-ttu-id="03ef8-129">Normal</span><span class="sxs-lookup"><span data-stu-id="03ef8-129">Normal</span></span>                              | <span data-ttu-id="03ef8-130">98 765,43</span><span class="sxs-lookup"><span data-stu-id="03ef8-130">98,765.43</span></span>              | <span data-ttu-id="03ef8-131">98 765,40</span><span class="sxs-lookup"><span data-stu-id="03ef8-131">98,765.40</span></span>              | <span data-ttu-id="03ef8-132">98 765,00</span><span class="sxs-lookup"><span data-stu-id="03ef8-132">98,765.00</span></span>              | <span data-ttu-id="03ef8-133">98 800,00</span><span class="sxs-lookup"><span data-stu-id="03ef8-133">98,800.00</span></span>                |
| <span data-ttu-id="03ef8-134">Nedåt</span><span class="sxs-lookup"><span data-stu-id="03ef8-134">Downward</span></span>                            | <span data-ttu-id="03ef8-135">98 765,43</span><span class="sxs-lookup"><span data-stu-id="03ef8-135">98,765.43</span></span>              | <span data-ttu-id="03ef8-136">98 765,40</span><span class="sxs-lookup"><span data-stu-id="03ef8-136">98,765.40</span></span>              | <span data-ttu-id="03ef8-137">98 765,00</span><span class="sxs-lookup"><span data-stu-id="03ef8-137">98,765.00</span></span>              | <span data-ttu-id="03ef8-138">98 700,00</span><span class="sxs-lookup"><span data-stu-id="03ef8-138">98,700.00</span></span>                |
| <span data-ttu-id="03ef8-139">Uppåt</span><span class="sxs-lookup"><span data-stu-id="03ef8-139">Rounding-up</span></span>                         | <span data-ttu-id="03ef8-140">98 765,43</span><span class="sxs-lookup"><span data-stu-id="03ef8-140">98,765.43</span></span>              | <span data-ttu-id="03ef8-141">98 765,50</span><span class="sxs-lookup"><span data-stu-id="03ef8-141">98,765.50</span></span>              | <span data-ttu-id="03ef8-142">98 766,00</span><span class="sxs-lookup"><span data-stu-id="03ef8-142">98,766.00</span></span>              | <span data-ttu-id="03ef8-143">98 800,00</span><span class="sxs-lookup"><span data-stu-id="03ef8-143">98,800.00</span></span>                |
| <span data-ttu-id="03ef8-144">Egen fördel, för ett kreditsaldo</span><span class="sxs-lookup"><span data-stu-id="03ef8-144">Own advantage, for a credit balance</span></span> | <span data-ttu-id="03ef8-145">98 765,43</span><span class="sxs-lookup"><span data-stu-id="03ef8-145">98,765.43</span></span>              | <span data-ttu-id="03ef8-146">98 765,40</span><span class="sxs-lookup"><span data-stu-id="03ef8-146">98,765.40</span></span>              | <span data-ttu-id="03ef8-147">98 765,00</span><span class="sxs-lookup"><span data-stu-id="03ef8-147">98,765.00</span></span>              | <span data-ttu-id="03ef8-148">98 700,00</span><span class="sxs-lookup"><span data-stu-id="03ef8-148">98,700.00</span></span>                |
| <span data-ttu-id="03ef8-149">Egen fördel, för ett debetsaldo</span><span class="sxs-lookup"><span data-stu-id="03ef8-149">Own advantage, for a debit balance</span></span>  | <span data-ttu-id="03ef8-150">98,765.43</span><span class="sxs-lookup"><span data-stu-id="03ef8-150">98,765.43</span></span>              | <span data-ttu-id="03ef8-151">98,765.50</span><span class="sxs-lookup"><span data-stu-id="03ef8-151">98,765.50</span></span>              | <span data-ttu-id="03ef8-152">98,766.00</span><span class="sxs-lookup"><span data-stu-id="03ef8-152">98,766.00</span></span>              | <span data-ttu-id="03ef8-153">98,800.00</span><span class="sxs-lookup"><span data-stu-id="03ef8-153">98,800.00</span></span>                |


### <a name="no-rounding-at-all-since-the-round-off-is-000"></a><span data-ttu-id="03ef8-154">Ingen avrundning, eftersom avrundningen är 0,00</span><span class="sxs-lookup"><span data-stu-id="03ef8-154">No rounding at all, since the round-off is 0.00</span></span>

<span data-ttu-id="03ef8-155">avrundning (1,0151, 0,00) = 1,0151 avrundning (1,0149, 0,00) = 1,0149</span><span class="sxs-lookup"><span data-stu-id="03ef8-155">round(1.0151, 0.00) = 1.0151 round(1.0149, 0.00) = 1.0149</span></span>

### <a name="normal-round-and-round-precision-is-001"></a><span data-ttu-id="03ef8-156">Normal avrundning och avrundningsprecision är 0,01</span><span class="sxs-lookup"><span data-stu-id="03ef8-156">Normal round, and round precision is 0.01</span></span>

<table>
  <tr>
    <td><span data-ttu-id="03ef8-157">Avrundning</span><span class="sxs-lookup"><span data-stu-id="03ef8-157">Rounding</span></span>
    </td>
    <td><span data-ttu-id="03ef8-158">Beräkningsprocess</span><span class="sxs-lookup"><span data-stu-id="03ef8-158">Calculation process</span></span>
    </td>
  </tr>
    <tr>
    <td><span data-ttu-id="03ef8-159">avrundning (1,015, 0,01) = 1,02</span><span class="sxs-lookup"><span data-stu-id="03ef8-159">round(1.015, 0.01) = 1.02</span></span>
    </td>
    <td>
      <ol>
        <li><span data-ttu-id="03ef8-160">avrundning (1,015 / 0,01, 0) = avrundning (101,5, 0) = 102</span><span class="sxs-lookup"><span data-stu-id="03ef8-160">round(1.015 / 0.01, 0) = round(101.5, 0) = 102</span></span>
        </li>
        <li><span data-ttu-id="03ef8-161">102 \* 0,01 = 1,02</span><span class="sxs-lookup"><span data-stu-id="03ef8-161">102 \* 0.01 = 1.02</span></span>
        </li>
      </ol>
    </td>
  </tr>
    <tr>
    <td><span data-ttu-id="03ef8-162">avrundning (1,014, 0,01) = 1,01</span><span class="sxs-lookup"><span data-stu-id="03ef8-162">round(1.014, 0.01) = 1.01</span></span>
    </td>
    <td> <ol>
        <li><span data-ttu-id="03ef8-163">avrundning (1,014 / 0,01, 0) = avrundning (101,4, 0) = 101</span><span class="sxs-lookup"><span data-stu-id="03ef8-163">round(1.014 / 0.01, 0) = round(101.4, 0) = 101</span></span>
        </li>
        <li><span data-ttu-id="03ef8-164">101 \* 0,01 = 1,01</span><span class="sxs-lookup"><span data-stu-id="03ef8-164">101 \* 0.01 = 1.01</span></span>
        </li>
      </ol>
    </td>
  </tr>
    <tr>
    <td><span data-ttu-id="03ef8-165">avrundning (1,011, 0,02) = 1,02</span><span class="sxs-lookup"><span data-stu-id="03ef8-165">round(1.011, 0.02) = 1.02</span></span>
    </td>
    <td> <ol>
        <li><span data-ttu-id="03ef8-166">avrundning (1,011 / 0,02, 0) = avrundning (50,55, 0) = 51</span><span class="sxs-lookup"><span data-stu-id="03ef8-166">round(1.011 / 0.02, 0) = round(50.55, 0) = 51</span></span>
        </li>
        <li><span data-ttu-id="03ef8-167">51 \* 0,02 = 1,02</span><span class="sxs-lookup"><span data-stu-id="03ef8-167">51 \* 0.02 = 1.02</span></span>
        </li>
      </ol>
    </td>
  </tr>
    <tr>
    <td><span data-ttu-id="03ef8-168">avrundning (1,009, 0,02) = 1,00</span><span class="sxs-lookup"><span data-stu-id="03ef8-168">round(1.009, 0.02) = 1.00</span></span>
    </td>
    <td> <ol>
        <li><span data-ttu-id="03ef8-169">avrundning (1,009 / 0,02, 0) = avrundning (50,45, 0) = 50</span><span class="sxs-lookup"><span data-stu-id="03ef8-169">round(1.009 / 0.02, 0) = round(50.45, 0) = 50</span></span>
        </li>
        <li><span data-ttu-id="03ef8-170">50 \* 0,02 = 1,00</span><span class="sxs-lookup"><span data-stu-id="03ef8-170">50 \* 0.02 = 1.00</span></span>
        </li>
      </ol>
    </td>
  </tr>
</table>

> [!NOTE]                                                                                  
> <span data-ttu-id="03ef8-171">Om du väljer Egen fördel är alltid avrundningen till fördelen för den juridiska personen.</span><span class="sxs-lookup"><span data-stu-id="03ef8-171">If you select Own advantage, the rounding is always to the advantage of the legal entity.</span></span> 

<span data-ttu-id="03ef8-172">Mer information finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="03ef8-172">For more information, see the following topics:</span></span>
- [<span data-ttu-id="03ef8-173">Momsöversikt</span><span class="sxs-lookup"><span data-stu-id="03ef8-173">Sales tax overview</span></span>](indirect-taxes-overview.md)
- [<span data-ttu-id="03ef8-174">Skapa en momsbetalning</span><span class="sxs-lookup"><span data-stu-id="03ef8-174">Create a sales tax payment</span></span>](tasks/create-sales-tax-payment.md)
- [<span data-ttu-id="03ef8-175">Skapa försäljningstransaktioner i dokument</span><span class="sxs-lookup"><span data-stu-id="03ef8-175">Create sales transactions on documents</span></span>](tasks/create-sales-tax-transactions-documents.md)
- [<span data-ttu-id="03ef8-176">Visa bokförda momstransaktioner</span><span class="sxs-lookup"><span data-stu-id="03ef8-176">View posted sales tax transactions</span></span>](tasks/view-posted-sales-tax-transactions.md)
- [<span data-ttu-id="03ef8-177">avrundningsfunktionen</span><span class="sxs-lookup"><span data-stu-id="03ef8-177">round Function</span></span>](https://msdn.microsoft.com/library/aa850656.aspx)


