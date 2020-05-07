---
title: Momsbetalningar och avrundningregler
description: Den här artikeln beskriver hur avrundningsregelinställningar på skattemyndigheter fungerar och avrundning av momssaldot under jobbet Kvitta och bokför moms.
author: ShylaThompson
manager: AnnBe
ms.date: 04/20/2020
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
ms.openlocfilehash: adc48d1841903670577684b1c3d773d323c19ea1
ms.sourcegitcommit: e06da171b9cba8163893e30244c52a9ce0901146
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "3275684"
---
# <a name="sales-tax-payments-and-rounding-rules"></a><span data-ttu-id="e5cb3-103">Momsbetalningar och avrundningregler</span><span class="sxs-lookup"><span data-stu-id="e5cb3-103">Sales tax payments and rounding rules</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e5cb3-104">Den här artikeln beskriver hur avrundningsregelinställningar på skattemyndigheter fungerar och avrundning av momssaldot under jobbet Kvitta och bokför moms.</span><span class="sxs-lookup"><span data-stu-id="e5cb3-104">This article explains how the rounding rule setup on the Sales tax authorities works and rounding the sales tax balance during the Settle and post sales tax job.</span></span>

<span data-ttu-id="e5cb3-105">Moms måste regelbundet rapporteras och betalas till skattemyndigheten.</span><span class="sxs-lookup"><span data-stu-id="e5cb3-105">Periodically, sales tax needs to be reported and paid to tax authorities.</span></span> <span data-ttu-id="e5cb3-106">Detta gör du genom att köra kvittnings- och bokföringsmomsprocess på sidan Moms.</span><span class="sxs-lookup"><span data-stu-id="e5cb3-106">This can be done by running the settle and post sales tax process in the Sales tax page.</span></span> <span data-ttu-id="e5cb3-107">Moms för en period kommer att kvittas mot momskontona och momssaldot kommer att bokföras på momskvittningskontot.</span><span class="sxs-lookup"><span data-stu-id="e5cb3-107">Sales tax for a period will be settled against the sales tax accounts and the sales tax balance will be posted to the Sales tax settlement account.</span></span> <span data-ttu-id="e5cb3-108">Momssaldot som bokförs på momskvittningskontot, kan avrundas enligt som krävs av skattemyndigheten genom att ställa in en avrundningsregel på sidan Moms.</span><span class="sxs-lookup"><span data-stu-id="e5cb3-108">The sales tax balance, which is posted on the Sales tax settlement account, can be rounded as required by tax authorities by setting up a rounding rule on the Sales tax page.</span></span> 

<span data-ttu-id="e5cb3-109">Avrundningsdifferensen bokförs på Momsavrundningkontot som valts i fältet Konton för automatisk transaktion i huvudboken.</span><span class="sxs-lookup"><span data-stu-id="e5cb3-109">The rounding difference is posted to the Sales tax rounding account that is selected in the Accounts for automatic transactions field in the General ledger.</span></span>

<span data-ttu-id="e5cb3-110">Exemplet nedanför illustrerar hur avrundningsregeln fungerar för Skattemyndigheten.</span><span class="sxs-lookup"><span data-stu-id="e5cb3-110">The below example illustrates how the rounding rule on Sales tax authority works.</span></span>

## <a name="examples"></a><span data-ttu-id="e5cb3-111">Exempel</span><span class="sxs-lookup"><span data-stu-id="e5cb3-111">Examples</span></span>

<span data-ttu-id="e5cb3-112">Det totala momsen för en period visar ett kreditsaldo på -98 765,43.</span><span class="sxs-lookup"><span data-stu-id="e5cb3-112">The total sales tax for a period shows a credit balance of -98,765.43.</span></span> <span data-ttu-id="e5cb3-113">Den juridiska personen samlade in mer moms än vad som har betalats.</span><span class="sxs-lookup"><span data-stu-id="e5cb3-113">The legal entity collected more sales taxes than it paid.</span></span> <span data-ttu-id="e5cb3-114">Därför är den juridiska personen skyldig pengar till skattemyndigheten.</span><span class="sxs-lookup"><span data-stu-id="e5cb3-114">Therefore, the legal entity owes money to the tax authority.</span></span> 

<span data-ttu-id="e5cb3-115">Den juridiska personen vill använda en avrundningsmetod som rundar av saldot till närmaste hela 1,00.</span><span class="sxs-lookup"><span data-stu-id="e5cb3-115">The legal entity wants to use a rounding method that rounds the balance to the nearest 1.00.</span></span> <span data-ttu-id="e5cb3-116">Användaren som ansvarar för momsredovisningen måste då göra följande steg.</span><span class="sxs-lookup"><span data-stu-id="e5cb3-116">The user who is responsible for sales tax accounting performs the following steps.</span></span>

1. <span data-ttu-id="e5cb3-117">Klicka på **Skatt** > **Indirekt moms** > **Moms** > **Skattemyndigheter**.</span><span class="sxs-lookup"><span data-stu-id="e5cb3-117">Click **Tax** > **Indirect taxes** > **Sales tax** > **Sales tax authorities**.</span></span>
2. <span data-ttu-id="e5cb3-118">I snabbfliken **Allmän** i fältet **Avrundningssätt**, välj **Normal**.</span><span class="sxs-lookup"><span data-stu-id="e5cb3-118">On the **General** FastTab, in the **Rounding form** field, select **Normal**.</span></span>
3. <span data-ttu-id="e5cb3-119">I fältet **Avrundning** anger du 1,00.</span><span class="sxs-lookup"><span data-stu-id="e5cb3-119">In the **Round-off** field, enter 1.00.</span></span>
4. <span data-ttu-id="e5cb3-120">När det är dags att betala moms till skattemyndigheten, gå till **Skatt** > **Deklarationer** > **Moms** > **Kvitta och bokför moms**.</span><span class="sxs-lookup"><span data-stu-id="e5cb3-120">When it is time to pay the sales taxes to the tax authority, go to **Tax** > **Declarations** > **Sales tax** > **Settle and post sale tax**.</span></span> <span data-ttu-id="e5cb3-121">På momskvittningskontot kan du se att skatteskuldbeloppet på **98 765,43** avrundas till **98 765**.</span><span class="sxs-lookup"><span data-stu-id="e5cb3-121">On the sales tax settlement account, you can see that the tax liability amount of **98,765.43** is rounded to **98,765**.</span></span>

<span data-ttu-id="e5cb3-122">Följande tabell visar hur ett belopp på 98 765,43 avrundas med hjälp av varje avrundningsmetod som är tillgänglig i fältet **Avrundningsätt** på sidan **Skattemyndigheten**.</span><span class="sxs-lookup"><span data-stu-id="e5cb3-122">The following table shows how an amount of 98,765.43 is rounded by using each rounding method that is available in the **Rounding form** field in the **Sales tax authorities** page.</span></span>

> [!NOTE]                                                                                  
> <span data-ttu-id="e5cb3-123">Om värdet för avrunda är inställt på 0,00 är:</span><span class="sxs-lookup"><span data-stu-id="e5cb3-123">If the round-off value is set as 0.00, then:</span></span>
>
> - <span data-ttu-id="e5cb3-124">Vid normal avrundning är avrundningsbeteendet detsamma som för **Avrundning = 0,01**.</span><span class="sxs-lookup"><span data-stu-id="e5cb3-124">For normal rounding, the rounding behavior is the same as for **Round-off = 0.01**.</span></span>
> - <span data-ttu-id="e5cb3-125">För **Alternativ för avrundningssätt**, **Nedåt**, **Uppåt** och **Egen fördel** är beteendet detsamma som för **Avrundning = 1,00**.</span><span class="sxs-lookup"><span data-stu-id="e5cb3-125">For the **Rounding form options**, **Downward**, **Rounding-up**, and **Own advantage**, the behavior is the same as for **Round-off = 1.00**.</span></span>

| <span data-ttu-id="e5cb3-126">Aternativ för avrundningssätt</span><span class="sxs-lookup"><span data-stu-id="e5cb3-126">Rounding form option</span></span>                | <span data-ttu-id="e5cb3-127">Avrundningsvärde = 0,01</span><span class="sxs-lookup"><span data-stu-id="e5cb3-127">Round-off value = 0.01</span></span> | <span data-ttu-id="e5cb3-128">Avrundningsvärde = 0,10</span><span class="sxs-lookup"><span data-stu-id="e5cb3-128">Round-off value = 0.10</span></span> | <span data-ttu-id="e5cb3-129">Avrundningsvärde = 1,00</span><span class="sxs-lookup"><span data-stu-id="e5cb3-129">Round-off value = 1.00</span></span> | <span data-ttu-id="e5cb3-130">Avrundningsvärde = 100,00</span><span class="sxs-lookup"><span data-stu-id="e5cb3-130">Round-off value = 100.00</span></span> | <span data-ttu-id="e5cb3-131">Avrundningsvärde = 0,00</span><span class="sxs-lookup"><span data-stu-id="e5cb3-131">Round-off value = 0.00</span></span>   |
|-------------------------------------|------------------------|------------------------|------------------------|--------------------------|--------------------------|
| <span data-ttu-id="e5cb3-132">Normal</span><span class="sxs-lookup"><span data-stu-id="e5cb3-132">Normal</span></span>                              | <span data-ttu-id="e5cb3-133">98,765.43</span><span class="sxs-lookup"><span data-stu-id="e5cb3-133">98,765.43</span></span>              | <span data-ttu-id="e5cb3-134">98,765.40</span><span class="sxs-lookup"><span data-stu-id="e5cb3-134">98,765.40</span></span>              | <span data-ttu-id="e5cb3-135">98,765.00</span><span class="sxs-lookup"><span data-stu-id="e5cb3-135">98,765.00</span></span>              | <span data-ttu-id="e5cb3-136">98,800.00</span><span class="sxs-lookup"><span data-stu-id="e5cb3-136">98,800.00</span></span>                | <span data-ttu-id="e5cb3-137">98,765.43</span><span class="sxs-lookup"><span data-stu-id="e5cb3-137">98,765.43</span></span>                |
| <span data-ttu-id="e5cb3-138">Nedåt</span><span class="sxs-lookup"><span data-stu-id="e5cb3-138">Downward</span></span>                            | <span data-ttu-id="e5cb3-139">98,765.43</span><span class="sxs-lookup"><span data-stu-id="e5cb3-139">98,765.43</span></span>              | <span data-ttu-id="e5cb3-140">98,765.40</span><span class="sxs-lookup"><span data-stu-id="e5cb3-140">98,765.40</span></span>              | <span data-ttu-id="e5cb3-141">98,765.00</span><span class="sxs-lookup"><span data-stu-id="e5cb3-141">98,765.00</span></span>              | <span data-ttu-id="e5cb3-142">98,700.00</span><span class="sxs-lookup"><span data-stu-id="e5cb3-142">98,700.00</span></span>                | <span data-ttu-id="e5cb3-143">98,765.00</span><span class="sxs-lookup"><span data-stu-id="e5cb3-143">98,765.00</span></span>                |
| <span data-ttu-id="e5cb3-144">Uppåt</span><span class="sxs-lookup"><span data-stu-id="e5cb3-144">Rounding-up</span></span>                         | <span data-ttu-id="e5cb3-145">98,765.43</span><span class="sxs-lookup"><span data-stu-id="e5cb3-145">98,765.43</span></span>              | <span data-ttu-id="e5cb3-146">98,765.50</span><span class="sxs-lookup"><span data-stu-id="e5cb3-146">98,765.50</span></span>              | <span data-ttu-id="e5cb3-147">98,766.00</span><span class="sxs-lookup"><span data-stu-id="e5cb3-147">98,766.00</span></span>              | <span data-ttu-id="e5cb3-148">98,800.00</span><span class="sxs-lookup"><span data-stu-id="e5cb3-148">98,800.00</span></span>                | <span data-ttu-id="e5cb3-149">98,766.00</span><span class="sxs-lookup"><span data-stu-id="e5cb3-149">98,766.00</span></span>                |
| <span data-ttu-id="e5cb3-150">Egen fördel, för ett kreditsaldo</span><span class="sxs-lookup"><span data-stu-id="e5cb3-150">Own advantage, for a credit balance</span></span> | <span data-ttu-id="e5cb3-151">98,765.43</span><span class="sxs-lookup"><span data-stu-id="e5cb3-151">98,765.43</span></span>              | <span data-ttu-id="e5cb3-152">98,765.40</span><span class="sxs-lookup"><span data-stu-id="e5cb3-152">98,765.40</span></span>              | <span data-ttu-id="e5cb3-153">98,765.00</span><span class="sxs-lookup"><span data-stu-id="e5cb3-153">98,765.00</span></span>              | <span data-ttu-id="e5cb3-154">98,700.00</span><span class="sxs-lookup"><span data-stu-id="e5cb3-154">98,700.00</span></span>                | <span data-ttu-id="e5cb3-155">98,765.00</span><span class="sxs-lookup"><span data-stu-id="e5cb3-155">98,765.00</span></span>                |
| <span data-ttu-id="e5cb3-156">Egen fördel, för ett debetsaldo</span><span class="sxs-lookup"><span data-stu-id="e5cb3-156">Own advantage, for a debit balance</span></span>  | <span data-ttu-id="e5cb3-157">98,765.43</span><span class="sxs-lookup"><span data-stu-id="e5cb3-157">98,765.43</span></span>              | <span data-ttu-id="e5cb3-158">98,765.50</span><span class="sxs-lookup"><span data-stu-id="e5cb3-158">98,765.50</span></span>              | <span data-ttu-id="e5cb3-159">98,766.00</span><span class="sxs-lookup"><span data-stu-id="e5cb3-159">98,766.00</span></span>              | <span data-ttu-id="e5cb3-160">98,800.00</span><span class="sxs-lookup"><span data-stu-id="e5cb3-160">98,800.00</span></span>                | <span data-ttu-id="e5cb3-161">98,766.00</span><span class="sxs-lookup"><span data-stu-id="e5cb3-161">98,766.00</span></span>                |

### <a name="normal-round-and-round-precision-is-001"></a><span data-ttu-id="e5cb3-162">Normal avrundning och avrundningsprecision är 0,01</span><span class="sxs-lookup"><span data-stu-id="e5cb3-162">Normal round, and round precision is 0.01</span></span>

<table>
  <tr>
    <td><span data-ttu-id="e5cb3-163">Avrundning</span><span class="sxs-lookup"><span data-stu-id="e5cb3-163">Rounding</span></span>
    </td>
    <td><span data-ttu-id="e5cb3-164">Beräkningsprocess</span><span class="sxs-lookup"><span data-stu-id="e5cb3-164">Calculation process</span></span>
    </td>
  </tr>
    <tr>
    <td><span data-ttu-id="e5cb3-165">avrundning (1,015, 0,01) = 1,02</span><span class="sxs-lookup"><span data-stu-id="e5cb3-165">round(1.015, 0.01) = 1.02</span></span>
    </td>
    <td>
      <ol>
        <li><span data-ttu-id="e5cb3-166">avrundning (1,015 / 0,01, 0) = avrundning (101,5, 0) = 102</span><span class="sxs-lookup"><span data-stu-id="e5cb3-166">round(1.015 / 0.01, 0) = round(101.5, 0) = 102</span></span>
        </li>
        <li><span data-ttu-id="e5cb3-167">102 \* 0,01 = 1,02</span><span class="sxs-lookup"><span data-stu-id="e5cb3-167">102 \* 0.01 = 1.02</span></span>
        </li>
      </ol>
    </td>
  </tr>
    <tr>
    <td><span data-ttu-id="e5cb3-168">avrundning (1,014, 0,01) = 1,01</span><span class="sxs-lookup"><span data-stu-id="e5cb3-168">round(1.014, 0.01) = 1.01</span></span>
    </td>
    <td> <ol>
        <li><span data-ttu-id="e5cb3-169">avrundning (1,014 / 0,01, 0) = avrundning (101,4, 0) = 101</span><span class="sxs-lookup"><span data-stu-id="e5cb3-169">round(1.014 / 0.01, 0) = round(101.4, 0) = 101</span></span>
        </li>
        <li><span data-ttu-id="e5cb3-170">101 \* 0,01 = 1,01</span><span class="sxs-lookup"><span data-stu-id="e5cb3-170">101 \* 0.01 = 1.01</span></span>
        </li>
      </ol>
    </td>
  </tr>
    <tr>
    <td><span data-ttu-id="e5cb3-171">avrundning (1,011, 0,02) = 1,02</span><span class="sxs-lookup"><span data-stu-id="e5cb3-171">round(1.011, 0.02) = 1.02</span></span>
    </td>
    <td> <ol>
        <li><span data-ttu-id="e5cb3-172">avrundning (1,011 / 0,02, 0) = avrundning (50,55, 0) = 51</span><span class="sxs-lookup"><span data-stu-id="e5cb3-172">round(1.011 / 0.02, 0) = round(50.55, 0) = 51</span></span>
        </li>
        <li><span data-ttu-id="e5cb3-173">51 \* 0,02 = 1,02</span><span class="sxs-lookup"><span data-stu-id="e5cb3-173">51 \* 0.02 = 1.02</span></span>
        </li>
      </ol>
    </td>
  </tr>
    <tr>
    <td><span data-ttu-id="e5cb3-174">avrundning (1,009, 0,02) = 1,00</span><span class="sxs-lookup"><span data-stu-id="e5cb3-174">round(1.009, 0.02) = 1.00</span></span>
    </td>
    <td> <ol>
        <li><span data-ttu-id="e5cb3-175">avrundning (1,009 / 0,02, 0) = avrundning (50,45, 0) = 50</span><span class="sxs-lookup"><span data-stu-id="e5cb3-175">round(1.009 / 0.02, 0) = round(50.45, 0) = 50</span></span>
        </li>
        <li><span data-ttu-id="e5cb3-176">50 \* 0,02 = 1,00</span><span class="sxs-lookup"><span data-stu-id="e5cb3-176">50 \* 0.02 = 1.00</span></span>
        </li>
      </ol>
    </td>
  </tr>
</table>

> [!NOTE]                                                                                  
> <span data-ttu-id="e5cb3-177">Om du väljer Egen fördel är alltid avrundningen till fördelen för den juridiska personen.</span><span class="sxs-lookup"><span data-stu-id="e5cb3-177">If you select Own advantage, the rounding is always to the advantage of the legal entity.</span></span> 

<span data-ttu-id="e5cb3-178">Mer information finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="e5cb3-178">For more information, see the following topics:</span></span>
- [<span data-ttu-id="e5cb3-179">Momsöversikt</span><span class="sxs-lookup"><span data-stu-id="e5cb3-179">Sales tax overview</span></span>](indirect-taxes-overview.md)
- [<span data-ttu-id="e5cb3-180">Skapa en momsbetalning</span><span class="sxs-lookup"><span data-stu-id="e5cb3-180">Create a sales tax payment</span></span>](tasks/create-sales-tax-payment.md)
- [<span data-ttu-id="e5cb3-181">Skapa momstransaktioner i dokument</span><span class="sxs-lookup"><span data-stu-id="e5cb3-181">Create sales tax transactions on documents</span></span>](tasks/create-sales-tax-transactions-documents.md)
- [<span data-ttu-id="e5cb3-182">Visa bokförda momstransaktioner</span><span class="sxs-lookup"><span data-stu-id="e5cb3-182">View posted sales tax transactions</span></span>](tasks/view-posted-sales-tax-transactions.md)
- [<span data-ttu-id="e5cb3-183">avrundningsfunktionen</span><span class="sxs-lookup"><span data-stu-id="e5cb3-183">round Function</span></span>](https://msdn.microsoft.com/library/aa850656.aspx)


