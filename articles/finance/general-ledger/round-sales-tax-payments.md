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
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2186335"
---
# <a name="sales-tax-payments-and-rounding-rules"></a><span data-ttu-id="7c986-103">Momsbetalningar och avrundningregler</span><span class="sxs-lookup"><span data-stu-id="7c986-103">Sales tax payments and rounding rules</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7c986-104">Den här artikeln beskriver hur avrundningsregelinställningar på skattemyndigheter fungerar och avrundning av momssaldot under jobbet Kvitta och bokför moms.</span><span class="sxs-lookup"><span data-stu-id="7c986-104">This article explains how the rounding rule setup on the Sales tax authorities works and rounding the sales tax balance during the Settle and post sales tax job.</span></span>

<span data-ttu-id="7c986-105">Moms måste regelbundet rapporteras och betalas till skattemyndigheten.</span><span class="sxs-lookup"><span data-stu-id="7c986-105">Periodically, sales tax needs to be reported and paid to tax authorities.</span></span> <span data-ttu-id="7c986-106">Detta gör du genom att köra kvittnings- och bokföringsmomsprocess på sidan Moms.</span><span class="sxs-lookup"><span data-stu-id="7c986-106">This can be done by running the settle and post sales tax process in the Sales tax page.</span></span> <span data-ttu-id="7c986-107">Moms för en period kommer att kvittas mot momskontona och momssaldot kommer att bokföras på momskvittningskontot.</span><span class="sxs-lookup"><span data-stu-id="7c986-107">Sales tax for a period will be settled against the sales tax accounts and the sales tax balance will be posted to the Sales tax settlement account.</span></span> <span data-ttu-id="7c986-108">Momssaldot som bokförs på momskvittningskontot, kan avrundas enligt som krävs av skattemyndigheten genom att ställa in en avrundningsregel på sidan Moms.</span><span class="sxs-lookup"><span data-stu-id="7c986-108">The sales tax balance, which is posted on the Sales tax settlement account, can be rounded as required by tax authorities by setting up a rounding rule on the Sales tax page.</span></span> 

<span data-ttu-id="7c986-109">Avrundningsdifferensen bokförs på Momsavrundningkontot som valts i fältet Konton för automatisk transaktion i huvudboken.</span><span class="sxs-lookup"><span data-stu-id="7c986-109">The rounding difference is posted to the Sales tax rounding account that is selected in the Accounts for automatic transactions field in the General ledger.</span></span>

<span data-ttu-id="7c986-110">Exemplet nedanför illustrerar hur avrundningsregeln fungerar för Skattemyndigheten.</span><span class="sxs-lookup"><span data-stu-id="7c986-110">The below example illustrates how the rounding rule on Sales tax authority works.</span></span>

## <a name="examples"></a><span data-ttu-id="7c986-111">Exempel</span><span class="sxs-lookup"><span data-stu-id="7c986-111">Examples</span></span>

<span data-ttu-id="7c986-112">Det totala momsen för en period visar ett kreditsaldo på -98 765,43.</span><span class="sxs-lookup"><span data-stu-id="7c986-112">The total sales tax for a period shows a credit balance of -98,765.43.</span></span> <span data-ttu-id="7c986-113">Den juridiska personen samlade in mer moms än vad som har betalats.</span><span class="sxs-lookup"><span data-stu-id="7c986-113">The legal entity collected more sales taxes than it paid.</span></span> <span data-ttu-id="7c986-114">Därför är den juridiska personen skyldig pengar till skattemyndigheten.</span><span class="sxs-lookup"><span data-stu-id="7c986-114">Therefore, the legal entity owes money to the tax authority.</span></span> 

<span data-ttu-id="7c986-115">Den juridiska personen vill använda en avrundningsmetod som rundar av saldot till närmaste hela 1,00.</span><span class="sxs-lookup"><span data-stu-id="7c986-115">The legal entity wants to use a rounding method that rounds the balance to the nearest 1.00.</span></span> <span data-ttu-id="7c986-116">Användaren som ansvarar för momsredovisningen måste då göra följande steg.</span><span class="sxs-lookup"><span data-stu-id="7c986-116">The user who is responsible for sales tax accounting performs the following steps.</span></span>

1.  <span data-ttu-id="7c986-117">Klicka på Skatt &gt; Indirekt moms &gt; Moms &gt; Skattemyndigheter</span><span class="sxs-lookup"><span data-stu-id="7c986-117">Click Tax &gt; Indirect taxes &gt; Sales tax &gt; Sales tax authorities</span></span>
2.  <span data-ttu-id="7c986-118">I snabbfliken Standard, välj Normal i fältet Avrundningssätt.</span><span class="sxs-lookup"><span data-stu-id="7c986-118">On the General FastTab, select Normal in the Rounding form field.</span></span>
3.  <span data-ttu-id="7c986-119">I fältet Avrundning anger du 1,00.</span><span class="sxs-lookup"><span data-stu-id="7c986-119">In the Round-off field, enter 1.00.</span></span>
4.  <span data-ttu-id="7c986-120">När det är dags att betala moms till skattemyndigheten öppnar du Kvitta och bokför moms.</span><span class="sxs-lookup"><span data-stu-id="7c986-120">When it is time to pay the sales taxes to the tax authority, open the Settle and post sales tax page.</span></span> <span data-ttu-id="7c986-121">(Klicka på Skatt &gt; Deklarationer &gt; Moms &gt; Kvitta och bokför moms.)</span><span class="sxs-lookup"><span data-stu-id="7c986-121">(Click Tax &gt; Declarations &gt; Sales tax &gt; Settle and post sales tax.)</span></span>
5.  <span data-ttu-id="7c986-122">På momskvittningkontot avrundas skatteskuldbeloppet på 98 765,43 till 98 765.</span><span class="sxs-lookup"><span data-stu-id="7c986-122">On the sales tax settlement account, the tax liability amount of 98,765.43 is rounded to 98,765.</span></span>

<span data-ttu-id="7c986-123">Följande tabell visar hur ett belopp på 98 765,43 avrundas med hjälp av varje avrundningsmetod som är tillgänglig i fältet Avrundningsätt på sidan Skattemyndigheten.</span><span class="sxs-lookup"><span data-stu-id="7c986-123">The following table shows how an amount of 98,765.43 is rounded by using each rounding method that is available in the Rounding form field in the Sales tax authorities page.</span></span>

| <span data-ttu-id="7c986-124">Aternativ för avrundningssätt</span><span class="sxs-lookup"><span data-stu-id="7c986-124">Rounding form option</span></span>                | <span data-ttu-id="7c986-125">Avrundningsvärde = 0,01</span><span class="sxs-lookup"><span data-stu-id="7c986-125">Round-off value = 0.01</span></span> | <span data-ttu-id="7c986-126">Avrundningsvärde = 0,10</span><span class="sxs-lookup"><span data-stu-id="7c986-126">Round-off value = 0.10</span></span> | <span data-ttu-id="7c986-127">Avrundningsvärde = 1,00</span><span class="sxs-lookup"><span data-stu-id="7c986-127">Round-off value = 1.00</span></span> | <span data-ttu-id="7c986-128">Avrundningsvärde = 100,00</span><span class="sxs-lookup"><span data-stu-id="7c986-128">Round-off value = 100.00</span></span> |
|-------------------------------------|------------------------|------------------------|------------------------|--------------------------|
| <span data-ttu-id="7c986-129">Normal</span><span class="sxs-lookup"><span data-stu-id="7c986-129">Normal</span></span>                              | <span data-ttu-id="7c986-130">98 765,43</span><span class="sxs-lookup"><span data-stu-id="7c986-130">98,765.43</span></span>              | <span data-ttu-id="7c986-131">98 765,40</span><span class="sxs-lookup"><span data-stu-id="7c986-131">98,765.40</span></span>              | <span data-ttu-id="7c986-132">98 765,00</span><span class="sxs-lookup"><span data-stu-id="7c986-132">98,765.00</span></span>              | <span data-ttu-id="7c986-133">98 800,00</span><span class="sxs-lookup"><span data-stu-id="7c986-133">98,800.00</span></span>                |
| <span data-ttu-id="7c986-134">Nedåt</span><span class="sxs-lookup"><span data-stu-id="7c986-134">Downward</span></span>                            | <span data-ttu-id="7c986-135">98 765,43</span><span class="sxs-lookup"><span data-stu-id="7c986-135">98,765.43</span></span>              | <span data-ttu-id="7c986-136">98 765,40</span><span class="sxs-lookup"><span data-stu-id="7c986-136">98,765.40</span></span>              | <span data-ttu-id="7c986-137">98 765,00</span><span class="sxs-lookup"><span data-stu-id="7c986-137">98,765.00</span></span>              | <span data-ttu-id="7c986-138">98 700,00</span><span class="sxs-lookup"><span data-stu-id="7c986-138">98,700.00</span></span>                |
| <span data-ttu-id="7c986-139">Uppåt</span><span class="sxs-lookup"><span data-stu-id="7c986-139">Rounding-up</span></span>                         | <span data-ttu-id="7c986-140">98 765,43</span><span class="sxs-lookup"><span data-stu-id="7c986-140">98,765.43</span></span>              | <span data-ttu-id="7c986-141">98 765,50</span><span class="sxs-lookup"><span data-stu-id="7c986-141">98,765.50</span></span>              | <span data-ttu-id="7c986-142">98 766,00</span><span class="sxs-lookup"><span data-stu-id="7c986-142">98,766.00</span></span>              | <span data-ttu-id="7c986-143">98 800,00</span><span class="sxs-lookup"><span data-stu-id="7c986-143">98,800.00</span></span>                |
| <span data-ttu-id="7c986-144">Egen fördel, för ett kreditsaldo</span><span class="sxs-lookup"><span data-stu-id="7c986-144">Own advantage, for a credit balance</span></span> | <span data-ttu-id="7c986-145">98 765,43</span><span class="sxs-lookup"><span data-stu-id="7c986-145">98,765.43</span></span>              | <span data-ttu-id="7c986-146">98 765,40</span><span class="sxs-lookup"><span data-stu-id="7c986-146">98,765.40</span></span>              | <span data-ttu-id="7c986-147">98 765,00</span><span class="sxs-lookup"><span data-stu-id="7c986-147">98,765.00</span></span>              | <span data-ttu-id="7c986-148">98 700,00</span><span class="sxs-lookup"><span data-stu-id="7c986-148">98,700.00</span></span>                |
| <span data-ttu-id="7c986-149">Egen fördel, för ett debetsaldo</span><span class="sxs-lookup"><span data-stu-id="7c986-149">Own advantage, for a debit balance</span></span>  | <span data-ttu-id="7c986-150">98,765.43</span><span class="sxs-lookup"><span data-stu-id="7c986-150">98,765.43</span></span>              | <span data-ttu-id="7c986-151">98,765.50</span><span class="sxs-lookup"><span data-stu-id="7c986-151">98,765.50</span></span>              | <span data-ttu-id="7c986-152">98,766.00</span><span class="sxs-lookup"><span data-stu-id="7c986-152">98,766.00</span></span>              | <span data-ttu-id="7c986-153">98,800.00</span><span class="sxs-lookup"><span data-stu-id="7c986-153">98,800.00</span></span>                |


### <a name="no-rounding-at-all-since-the-round-off-is-000"></a><span data-ttu-id="7c986-154">Ingen avrundning, eftersom avrundningen är 0,00</span><span class="sxs-lookup"><span data-stu-id="7c986-154">No rounding at all, since the round-off is 0.00</span></span>

<span data-ttu-id="7c986-155">avrundning (1,0151, 0,00) = 1,0151 avrundning (1,0149, 0,00) = 1,0149</span><span class="sxs-lookup"><span data-stu-id="7c986-155">round(1.0151, 0.00) = 1.0151 round(1.0149, 0.00) = 1.0149</span></span>

### <a name="normal-round-and-round-precision-is-001"></a><span data-ttu-id="7c986-156">Normal avrundning och avrundningsprecision är 0,01</span><span class="sxs-lookup"><span data-stu-id="7c986-156">Normal round, and round precision is 0.01</span></span>

<table>
  <tr>
    <td><span data-ttu-id="7c986-157">Avrundning</span><span class="sxs-lookup"><span data-stu-id="7c986-157">Rounding</span></span>
    </td>
    <td><span data-ttu-id="7c986-158">Beräkningsprocess</span><span class="sxs-lookup"><span data-stu-id="7c986-158">Calculation process</span></span>
    </td>
  </tr>
    <tr>
    <td><span data-ttu-id="7c986-159">avrundning (1,015, 0,01) = 1,02</span><span class="sxs-lookup"><span data-stu-id="7c986-159">round(1.015, 0.01) = 1.02</span></span>
    </td>
    <td>
      <ol>
        <li><span data-ttu-id="7c986-160">avrundning (1,015 / 0,01, 0) = avrundning (101,5, 0) = 102</span><span class="sxs-lookup"><span data-stu-id="7c986-160">round(1.015 / 0.01, 0) = round(101.5, 0) = 102</span></span>
        </li>
        <li><span data-ttu-id="7c986-161">102 \* 0,01 = 1,02</span><span class="sxs-lookup"><span data-stu-id="7c986-161">102 \* 0.01 = 1.02</span></span>
        </li>
      </ol>
    </td>
  </tr>
    <tr>
    <td><span data-ttu-id="7c986-162">avrundning (1,014, 0,01) = 1,01</span><span class="sxs-lookup"><span data-stu-id="7c986-162">round(1.014, 0.01) = 1.01</span></span>
    </td>
    <td> <ol>
        <li><span data-ttu-id="7c986-163">avrundning (1,014 / 0,01, 0) = avrundning (101,4, 0) = 101</span><span class="sxs-lookup"><span data-stu-id="7c986-163">round(1.014 / 0.01, 0) = round(101.4, 0) = 101</span></span>
        </li>
        <li><span data-ttu-id="7c986-164">101 \* 0,01 = 1,01</span><span class="sxs-lookup"><span data-stu-id="7c986-164">101 \* 0.01 = 1.01</span></span>
        </li>
      </ol>
    </td>
  </tr>
    <tr>
    <td><span data-ttu-id="7c986-165">avrundning (1,011, 0,02) = 1,02</span><span class="sxs-lookup"><span data-stu-id="7c986-165">round(1.011, 0.02) = 1.02</span></span>
    </td>
    <td> <ol>
        <li><span data-ttu-id="7c986-166">avrundning (1,011 / 0,02, 0) = avrundning (50,55, 0) = 51</span><span class="sxs-lookup"><span data-stu-id="7c986-166">round(1.011 / 0.02, 0) = round(50.55, 0) = 51</span></span>
        </li>
        <li><span data-ttu-id="7c986-167">51 \* 0,02 = 1,02</span><span class="sxs-lookup"><span data-stu-id="7c986-167">51 \* 0.02 = 1.02</span></span>
        </li>
      </ol>
    </td>
  </tr>
    <tr>
    <td><span data-ttu-id="7c986-168">avrundning (1,009, 0,02) = 1,00</span><span class="sxs-lookup"><span data-stu-id="7c986-168">round(1.009, 0.02) = 1.00</span></span>
    </td>
    <td> <ol>
        <li><span data-ttu-id="7c986-169">avrundning (1,009 / 0,02, 0) = avrundning (50,45, 0) = 50</span><span class="sxs-lookup"><span data-stu-id="7c986-169">round(1.009 / 0.02, 0) = round(50.45, 0) = 50</span></span>
        </li>
        <li><span data-ttu-id="7c986-170">50 \* 0,02 = 1,00</span><span class="sxs-lookup"><span data-stu-id="7c986-170">50 \* 0.02 = 1.00</span></span>
        </li>
      </ol>
    </td>
  </tr>
</table>

> [!NOTE]                                                                                  
> <span data-ttu-id="7c986-171">Om du väljer Egen fördel är alltid avrundningen till fördelen för den juridiska personen.</span><span class="sxs-lookup"><span data-stu-id="7c986-171">If you select Own advantage, the rounding is always to the advantage of the legal entity.</span></span> 

<span data-ttu-id="7c986-172">Mer information finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="7c986-172">For more information, see the following topics:</span></span>
- [<span data-ttu-id="7c986-173">Momsöversikt</span><span class="sxs-lookup"><span data-stu-id="7c986-173">Sales tax overview</span></span>](indirect-taxes-overview.md)
- [<span data-ttu-id="7c986-174">Skapa en momsbetalning</span><span class="sxs-lookup"><span data-stu-id="7c986-174">Create a sales tax payment</span></span>](tasks/create-sales-tax-payment.md)
- [<span data-ttu-id="7c986-175">Skapa försäljningstransaktioner i dokument</span><span class="sxs-lookup"><span data-stu-id="7c986-175">Create sales transactions on documents</span></span>](tasks/create-sales-tax-transactions-documents.md)
- [<span data-ttu-id="7c986-176">Visa bokförda momstransaktioner</span><span class="sxs-lookup"><span data-stu-id="7c986-176">View posted sales tax transactions</span></span>](tasks/view-posted-sales-tax-transactions.md)
- [<span data-ttu-id="7c986-177">avrundningsfunktionen</span><span class="sxs-lookup"><span data-stu-id="7c986-177">round Function</span></span>](https://msdn.microsoft.com/library/aa850656.aspx)


