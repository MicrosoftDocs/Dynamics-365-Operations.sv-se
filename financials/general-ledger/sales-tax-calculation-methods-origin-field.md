---
title: "Beräkningsmetod för moms i fältet Ursprung"
description: "Den här artikeln beskriver alternativen i fältet Ursprung på momskodsidan och hur moms beräknas utifrån det markerade alternativet för en momskod."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: TaxTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: f5683b8b3e5457a05e5039876eed40357ae84e4b
ms.contentlocale: sv-se
ms.lasthandoff: 07/18/2017

---

# <a name="sales-tax-calculation-methods-in-the-origin-field"></a><span data-ttu-id="b0b2f-103">Beräkningsmetod för moms i fältet Ursprung</span><span class="sxs-lookup"><span data-stu-id="b0b2f-103">Sales tax calculation methods in the Origin field</span></span>

[!include[banner](../includes/banner.md)]

[!include[retail name](../includes/retail-name.md)]


<span data-ttu-id="b0b2f-104">Den här artikeln beskriver alternativen i fältet Ursprung på momskodsidan och hur moms beräknas utifrån det markerade alternativet för en momskod.</span><span class="sxs-lookup"><span data-stu-id="b0b2f-104">This article explains the options in the Origin field on the sales tax codes page and how sales tax is calculated based on the selected option for a sales tax code.</span></span>

<span data-ttu-id="b0b2f-105">För varje momskod som du skapar på sidan Momoskoder väljer du den beräkningsmetod som ska tillämpas på basbeloppet för skatten i fältet Ursprung.</span><span class="sxs-lookup"><span data-stu-id="b0b2f-105">For each sales tax code that you create in the Sales tax codes page, you must select the method of calculation to apply to the tax base amount in the Origin field.</span></span>

## <a name="percentage-of-net-amount"></a><span data-ttu-id="b0b2f-106">Procent av nettobelopp</span><span class="sxs-lookup"><span data-stu-id="b0b2f-106">Percentage of net amount</span></span>
<span data-ttu-id="b0b2f-107">Beräkningsmetoden för procentandel av nettobeloppet är det förvalda värdet i fältet Ursprung.</span><span class="sxs-lookup"><span data-stu-id="b0b2f-107">The Percentage of net amount calculation method is the default value in the Origin field.</span></span> <span data-ttu-id="b0b2f-108">Momsen beräknas som en procentandel av inköps- eller försäljningsbeloppet, exklusive annan eventuell moms.</span><span class="sxs-lookup"><span data-stu-id="b0b2f-108">The sales tax is calculated as a percentage of the purchase or sales amount, excluding any other sales taxes.</span></span>
### <a name="example"></a><span data-ttu-id="b0b2f-109">Exempel</span><span class="sxs-lookup"><span data-stu-id="b0b2f-109">Example</span></span>

<span data-ttu-id="b0b2f-110">Momssatsen är 25%.</span><span class="sxs-lookup"><span data-stu-id="b0b2f-110">The tax rate is 25%.</span></span> <span data-ttu-id="b0b2f-111">Fakturaraden visar en kvantitet på 10 artiklar à 1,00 $ styck och kunden har rätt till en radrabatt på 10 %.</span><span class="sxs-lookup"><span data-stu-id="b0b2f-111">The invoice line shows a quantity of 10 items at 1.00 each, and the customer is allowed a 10% line discount.</span></span> <span data-ttu-id="b0b2f-112">Nettobelopp: (10 x 1,00) -10 % = 9,00 moms: 9,00 x 25 % = 2,25 totalbelopp: 9,00 + 2,25 = 11,25</span><span class="sxs-lookup"><span data-stu-id="b0b2f-112">Net amount: (10 x 1.00) -10% = 9.00 Sales tax: 9.00 x 25% = 2.25 Total amount: 9.00 + 2.25 = 11.25</span></span>

## <a name="percentage-of-gross-amount"></a><span data-ttu-id="b0b2f-113"> Procent av bruttobelopp</span><span class="sxs-lookup"><span data-stu-id="b0b2f-113">Percentage of gross amount</span></span>
<span data-ttu-id="b0b2f-114">Om du väljer metoden Procent av bruttobeloppet beräknas momsen som en procentandel av bruttoförsäljningsbeloppet.</span><span class="sxs-lookup"><span data-stu-id="b0b2f-114">If you select the Percentage of gross amount method, the sales tax is calculated as a percentage of the gross sales amount.</span></span> <span data-ttu-id="b0b2f-115">Bruttobeloppet är radnettobeloppet plus all moms och tillägg för raden utom moms med Ursprung = procentandel av bruttobeloppet.</span><span class="sxs-lookup"><span data-stu-id="b0b2f-115">The gross amount is the line net amount plus all taxes and fees for the line except the one tax with Origin = Percentage of gross amount.</span></span>
### <a name="example"></a><span data-ttu-id="b0b2f-116">Exempel</span><span class="sxs-lookup"><span data-stu-id="b0b2f-116">Example</span></span>

<span data-ttu-id="b0b2f-117">Skattemyndigheten har lagt särskilda avgifter på en artikel.</span><span class="sxs-lookup"><span data-stu-id="b0b2f-117">The tax authority has imposed special duties on an item.</span></span> <span data-ttu-id="b0b2f-118">Avgiftsbeloppen läggs till nettobeloppet innan momsen beräknas.</span><span class="sxs-lookup"><span data-stu-id="b0b2f-118">The duty amounts are added to the net amount before sales tax is calculated.</span></span> <span data-ttu-id="b0b2f-119">Givet följande momskoder:</span><span class="sxs-lookup"><span data-stu-id="b0b2f-119">Given the following sales tax codes:</span></span>
-   <span data-ttu-id="b0b2f-120">AVGIFT 1 = 10 % med beräkningsmetoden Procent av nettobelopp.</span><span class="sxs-lookup"><span data-stu-id="b0b2f-120">DUTY 1 = 10%, using the Percentage of net amount calculation method</span></span>
-   <span data-ttu-id="b0b2f-121">AVGIFT 2 = 20 % med beräkningsmetoden Procent av nettobelopp.</span><span class="sxs-lookup"><span data-stu-id="b0b2f-121">DUTY 2 = 20%, using the Percentage of net amount calculation method</span></span>
-   <span data-ttu-id="b0b2f-122">MOMS = 25 % med beräkningsmetoden Procent av bruttobelopp.</span><span class="sxs-lookup"><span data-stu-id="b0b2f-122">SALESTAX = 25%, using the Percentage of gross amount calculation method</span></span>

<span data-ttu-id="b0b2f-123">Om nettobeloppet är 10,00, är AVGIFT 1 1,00 (10,00 x 10 %) och AVGIFT 2 = 2,00 (10,00 x 20 %).</span><span class="sxs-lookup"><span data-stu-id="b0b2f-123">If the net amount is 10.00, then DUTY 1 is 1.00 (10.00 x 10%) and DUTY 2 = 2.00 (10.00 x 20%).</span></span> <span data-ttu-id="b0b2f-124">Beloppen blir som följer: Bruttobelopp: Nettobelopp + AVGIFT 1 belopp + 2 AVGIFT belopp (10,00 + 1,00 + 2,00) = 13,00 MOMS = 13,00 × 25 % = 3,25 totala AVGIFTER och MOMS: 1,00 + 2,00 + 3,25 = 6,25 totalbelopp: 10,00 + 6,25 = 16,25</span><span class="sxs-lookup"><span data-stu-id="b0b2f-124">The amounts would be as follows: Gross amount: Net amount + DUTY 1 amount + DUTY 2 amount (10.00 + 1.00 + 2.00) = 13.00 SALESTAX = 13.00 x 25% = 3.25 Total DUTIES and SALESTAX: 1.00 + 2.00 + 3.25 = 6.25 Total amount: 10.00 + 6.25 = 16.25</span></span>
| <span data-ttu-id="b0b2f-125">**Obs!**</span><span class="sxs-lookup"><span data-stu-id="b0b2f-125">**Note**</span></span>                                                                                                                                                                                                                 |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="b0b2f-126">Endast en momskod med Ursprung = procentandel av bruttobeloppet kan användas för en transaktion.</span><span class="sxs-lookup"><span data-stu-id="b0b2f-126">Only one tax code with Origin = Percentage of gross amount can be used for a transaction.</span></span> <span data-ttu-id="b0b2f-127">Om mer än en sådan momskod bestäms av en transaktion, visas ett fel att moms inte kan beräknas.</span><span class="sxs-lookup"><span data-stu-id="b0b2f-127">If more than one such tax code is determined for a transaction an error will be displayed that sales tax cannot be calculated.</span></span> |

 
<a name="percentage-of-sales-tax"></a><span data-ttu-id="b0b2f-128">Procent av moms</span><span class="sxs-lookup"><span data-stu-id="b0b2f-128">Percentage of sales tax</span></span>
-----------------------

<span data-ttu-id="b0b2f-129">När du väljer procentsats av moms i fältet Ursprung, beräknas momsen som en procentandel av momsen som har valts i Moms i fältet Moms.</span><span class="sxs-lookup"><span data-stu-id="b0b2f-129">When you select Percentage of sales tax in the Origin field, sales tax is calculated as a percentage of the sales tax that is selected in the Sales tax on sales tax field.</span></span> <span data-ttu-id="b0b2f-130">Momsen som väljs i Moms i fältet Moms beräknas först.</span><span class="sxs-lookup"><span data-stu-id="b0b2f-130">The sales tax that is selected in the Sales tax on sales tax field is calculated first.</span></span> <span data-ttu-id="b0b2f-131">Den andra momsen beräknas därefter baserat på det första momsbeloppet.</span><span class="sxs-lookup"><span data-stu-id="b0b2f-131">The second sales tax is then calculated based on the first sales tax amount.</span></span>
### <a name="example"></a><span data-ttu-id="b0b2f-132">Exempel</span><span class="sxs-lookup"><span data-stu-id="b0b2f-132">Example</span></span>

<span data-ttu-id="b0b2f-133">Givet följande momskoder:</span><span class="sxs-lookup"><span data-stu-id="b0b2f-133">Given the following sales tax codes:</span></span>
-   <span data-ttu-id="b0b2f-134">AVGIFT 1 = 10 % med metoden Procent av nettobelopp.</span><span class="sxs-lookup"><span data-stu-id="b0b2f-134">DUTY 1 = 10%, using the Percentage of net amount method</span></span>
-   <span data-ttu-id="b0b2f-135">AVGIFT 2 = 20 %, med hjälp av metoden Procent av moms med Avgift 1 i Moms i fältet Moms</span><span class="sxs-lookup"><span data-stu-id="b0b2f-135">DUTY 2 = 20%, using the Percentage of sales tax method, with Duty 1 in the Sales tax on sales tax field</span></span>
-   <span data-ttu-id="b0b2f-136">MOMS = 25 % med metoden Procent av bruttobelopp.</span><span class="sxs-lookup"><span data-stu-id="b0b2f-136">SALESTAX = 25%, using the Percentage of gross amount method</span></span>

<span data-ttu-id="b0b2f-137">Nettobelopp: 10,00 AVGIFT 1: 10,00 x 10 % = 1,00 AVGIFT 2: 1,00 x 20 % = 0,20 Bruttobelopp: 10,00 + 1,00 + 0,20 = 11,20 MOMS: 11,20 x 25 % = 2,80 Totala AVGIFTER och MOMS: 1,00 + 0,20 + 2,80 = 4,00 Totalt belopp: 10,00 + 4,00 = 14,00</span><span class="sxs-lookup"><span data-stu-id="b0b2f-137">Net amount: 10.00 DUTY 1: 10.00 x 10% = 1.00 DUTY 2: 1.00 x 20% = 0.20 Gross amount: 10.00 + 1.00 + 0.20 = 11.20 SALESTAX: 11.20 x 25% = 2.80 Total DUTIES and SALESTAX: 1.00 + 0.20 + 2.80 = 4.00 Total amount: 10.00 + 4.00 = 14.00</span></span>
| <span data-ttu-id="b0b2f-138">**Obs!**</span><span class="sxs-lookup"><span data-stu-id="b0b2f-138">**Note**</span></span>                                                                                                                                                                                                                    |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="b0b2f-139">Moms på flera nivåer är inte möjlig.</span><span class="sxs-lookup"><span data-stu-id="b0b2f-139">Multilevel tax on tax calculations are not possible.</span></span> <span data-ttu-id="b0b2f-140">Moms kan inte beräknas baserat på moms som redan har beräknats på en annan moms.</span><span class="sxs-lookup"><span data-stu-id="b0b2f-140">A tax cannot be calculated based on a tax which already is calculated based on another tax.</span></span> <span data-ttu-id="b0b2f-141">Moms på flera nivåer på momskoder kan beräknas för en transaktion.</span><span class="sxs-lookup"><span data-stu-id="b0b2f-141">Multiple single level tax on tax codes can be calculated on a transaction.</span></span> |

## <a name="amount-per-unit"></a><span data-ttu-id="b0b2f-142"> Belopp per enhet</span><span class="sxs-lookup"><span data-stu-id="b0b2f-142">Amount per unit</span></span>
<span data-ttu-id="b0b2f-143">När du väljer belopp per enhet i fältet Ursprung, beräknas momsen som ett fast belopp per enhet multiplicerat med den kvantitet som anges på dokumentraden.</span><span class="sxs-lookup"><span data-stu-id="b0b2f-143">When you select Amount per unit in the Origin field, sales tax is calculated as a fixed amount per unit multiplied with the quantity entered on the document line.</span></span> <span data-ttu-id="b0b2f-144">Enheten väljs i fältet Enhet.</span><span class="sxs-lookup"><span data-stu-id="b0b2f-144">A unit has to be selected in the Unit field.</span></span> <span data-ttu-id="b0b2f-145">Pris per enhet anges på sidan för Momskodsvärden.</span><span class="sxs-lookup"><span data-stu-id="b0b2f-145">The amount per unit is specified in the Sales tax code values page.</span></span>
### <a name="example"></a><span data-ttu-id="b0b2f-146">Exempel</span><span class="sxs-lookup"><span data-stu-id="b0b2f-146">Example</span></span>

<span data-ttu-id="b0b2f-147">Momskoden är inställt som: 1,20 Kronor per enhet = rutan på en försäljningsfakturarad 25 rutor av en artikel är såld Moms beräknas som 25 x 1,20 = 30,00</span><span class="sxs-lookup"><span data-stu-id="b0b2f-147">Sales tax code is set up as: USD 1.20 per unit = box On a sales invoice line 25 boxes of an item are sold Sales tax is calculated as 25 x 1.20 = 30.00</span></span>
| <span data-ttu-id="b0b2f-148">**Obs!**</span><span class="sxs-lookup"><span data-stu-id="b0b2f-148">**Note**</span></span>                                                                                                                                                                                                 |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="b0b2f-149">Om transaktionen anges i en annan enhet än de enheter som anges på momskoden, konverteras den automatiskt baserat på enhetskonverteringarna som ställs in i enhetskonverteringsidan.</span><span class="sxs-lookup"><span data-stu-id="b0b2f-149">If the transaction is entered in different unit than the unit specified on the sales tax code, it is converted automatically based on the unit conversions that are set up in the Unit conversions page.</span></span> |

###  <a name="amount-per-unit-additional-option"></a><span data-ttu-id="b0b2f-150"> Belopp per enhet, extra alternativ</span><span class="sxs-lookup"><span data-stu-id="b0b2f-150">Amount per unit, additional option</span></span>

<span data-ttu-id="b0b2f-151">I fliken Beräkning kan du välja om ett belopp per enhet för beräknad moms ska beräknas före andra momskoder och läggas till nettobeloppet med ursprunget = procent av nettobeloppet beräknas.</span><span class="sxs-lookup"><span data-stu-id="b0b2f-151">On the Calculation tab, you can select whether an amount per unit calculated tax is calculated before other tax codes and added to the net amount before other tax codes with Origin = Percentage of net amount are calculated.</span></span>

### <a name="examples"></a><span data-ttu-id="b0b2f-152">Exempel</span><span class="sxs-lookup"><span data-stu-id="b0b2f-152">Examples</span></span>

<span data-ttu-id="b0b2f-153">Anta att du beräknar 2 momskoder på en transaktion:</span><span class="sxs-lookup"><span data-stu-id="b0b2f-153">Assume we calculate 2 tax codes on a transaction:</span></span>

-   <span data-ttu-id="b0b2f-154">AVGIFT: Ursprung = belopp per enhet och moms, värdet är 5,00 per enhet = stk</span><span class="sxs-lookup"><span data-stu-id="b0b2f-154">DUTY: Origin = Amount per unit and a sales tax, the value is set to 5.00 per unit = pcs</span></span>
-   <span data-ttu-id="b0b2f-155">MOMS: Ursprung = enligt exemplen nedan, värdet är 25 %</span><span class="sxs-lookup"><span data-stu-id="b0b2f-155">SALESTAX: Origin = as shown in the examples below, the value is set to 25%</span></span>

<span data-ttu-id="b0b2f-156">Vi säljer 1 del av en artikel till enhetspriset på 10,00</span><span class="sxs-lookup"><span data-stu-id="b0b2f-156">We sell 1 piece of an item at a unit price of 10.00</span></span>
#### <a name="example-1"></a><span data-ttu-id="b0b2f-157">Exempel 1</span><span class="sxs-lookup"><span data-stu-id="b0b2f-157">Example 1</span></span>

<span data-ttu-id="b0b2f-158">MOMS: Ursprung = procentandel av bruttobeloppet, alternativet Beräknat före moms påverkar inte, eftersom MOMS beräknas som en procentandel av bruttobeloppet.</span><span class="sxs-lookup"><span data-stu-id="b0b2f-158">SALESTAX: Origin = Percentage of gross amount method The Calculate before sales tax option has no effect, because SALESTAX is calculated as a percentage of the gross amount.</span></span> <span data-ttu-id="b0b2f-159">AVGIFT: 1 × 5,00 = 5,00 bruttobelopp: 10,00 + 5,00 = 15,00 MOMS: 15,00 x 25 % = 3,75 Total moms: 5,00 + 3,75 = 8,75 Totalt belopp: 10,00 + 8,75 = 18,75</span><span class="sxs-lookup"><span data-stu-id="b0b2f-159">DUTY: 1 x 5.00 = 5.00 Gross amount: 10.00 + 5.00 = 15.00 SALESTAX: 15.00 x 25% = 3.75 Total sales tax: 5.00 + 3.75 = 8.75 Total amount: 10.00 + 8.75 = 18.75</span></span>

#### <a name="example-2"></a><span data-ttu-id="b0b2f-160">Exempel 2</span><span class="sxs-lookup"><span data-stu-id="b0b2f-160">Example 2</span></span>

<span data-ttu-id="b0b2f-161">MOMS: Ursprung = procentandelen av nettobeloppet, alternativet Beräknat före moms markeras inte för beräkningen av AVGIFT.</span><span class="sxs-lookup"><span data-stu-id="b0b2f-161">SALESTAX: Origin = Percentage of net amount The Calculate before sales tax option is not selected for the DUTY calculation.</span></span> <span data-ttu-id="b0b2f-162">Nettobelopp: 10,00 AVGIFT: 1 x 5,00 = 5,00 MOMS: 10,00 x 25 % = 2,50 Total moms: 5,00 + 2,50 = 7,50 Totalt belopp: 10,00 + 7,50 = 17,50</span><span class="sxs-lookup"><span data-stu-id="b0b2f-162">Net amount: 10.00 DUTY: 1 x 5.00 = 5.00 SALESTAX: 10.00 x 25% = 2.50 Total sales tax: 5.00 + 2.50 = 7.50 Total amount: 10.00 + 7.50 = 17.50</span></span>

#### <a name="example-3"></a><span data-ttu-id="b0b2f-163">Exempel 3</span><span class="sxs-lookup"><span data-stu-id="b0b2f-163">Example 3</span></span>

<span data-ttu-id="b0b2f-164">MOMS: Ursprung = procentandelen av nettobeloppet, alternativet Beräknat före moms markeras för beräkningen av AVGIFT.</span><span class="sxs-lookup"><span data-stu-id="b0b2f-164">SALESTAX: Origin = Percentage of net amount The Calculate before sales tax option is selected for the DUTY calculation.</span></span> <span data-ttu-id="b0b2f-165">Nettobelopp: 10,00 AVGIFT: 1 x 5,00 = 5,00 MOMS: (10,00 + 5,00) x 25 % = 3,75 Total moms: 5,00 + 3,75 = 8,75 Totalt belopp: 10,00 + 8,75 = 18, 75</span><span class="sxs-lookup"><span data-stu-id="b0b2f-165">Net amount: 10.00 DUTY: 1 x 5.00 = 5.00 SALESTAX: (10.00 + 5.00) x 25% = 3.75 Total sales tax: 5.00 + 3.75 = 8.75 Total amount: 10.00 + 8.75 = 18.75</span></span>

#### <a name="example-4"></a><span data-ttu-id="b0b2f-166">Exempel 4</span><span class="sxs-lookup"><span data-stu-id="b0b2f-166">Example 4</span></span>

<span data-ttu-id="b0b2f-167">Resultatet av exempel 3 och exempel 1 är samma, eftersom det bara fanns en avgift.</span><span class="sxs-lookup"><span data-stu-id="b0b2f-167">The result of Example 3 and Example 1 is the same, because there is only one duty.</span></span> <span data-ttu-id="b0b2f-168">Anta att du har två AVGIFTER, och endast en av dem är inkluderad i nettobeloppet för momsberäkningen: AVGIFT 1: 5,00 med hjälp av metoden Belopp per enhet och alternativet Beräkna före moms är markerade AVGIFT 2: 2,50 med hjälp av metoden Belopp per enhet och alternativet Beräkna före moms är inte markerade Moms: 25 % med hjälp av metoden Procent av nettobelopp: 10,00 AVGIFT 1: 1 x 5,00 = 5,00 AVGIFT 2: 1 x 2,50 = 2,50 Nettobelopp som omfattas av moms: 10,00 + 5,00 = 15,00 MOMS: 15,00 x 2 5% = 3,75 Total moms, inklusive tullavgifter: 5,00 + 2,50 + 3,75 = 11,25 Totalt belopp: 10,00 + 11,25 = 21,25, 25 % MOMS beräknas för summan av nettobeloppet (10,00) + AVGIFT 1 (5,00) = 15,00.</span><span class="sxs-lookup"><span data-stu-id="b0b2f-168">Assume that you have two DUTIES, and only one of them is included in the net amount for the sales tax calculation: DUTY 1: 5.00, using the Amount per unit method, and the Calculate before sales tax option is selected DUTY 2: 2.50, using the Amount per unit method, and the Calculate before sales tax option is not selected Sales tax: 25%, using the Percentage of net amount method Net amount: 10.00 DUTY 1: 1 x 5.00 = 5.00 DUTY 2: 1 x 2.50 = 2.50 Net amount subject to sales tax: 10.00 + 5.00 = 15.00 SALESTAX: 15.00 x 25% = 3.75 Total sales taxes, including duties: 5.00 + 2.50 + 3.75 = 11.25 Total amount: 10.00 + 11.25 = 21.25 The 25% SALESTAX is calculated for the sum of the net amount (10.00) + DUTY 1 (5.00) = 15.00.</span></span> <span data-ttu-id="b0b2f-169">AVGIFT 2 läggs till skattebeloppet efter att momsen beräknats.</span><span class="sxs-lookup"><span data-stu-id="b0b2f-169">DUTY 2 is added to the tax amount after the sales tax is calculated.</span></span>

## <a name="calculated-percentage-of-net-amount"></a><span data-ttu-id="b0b2f-170"> Beräknad procent av nettobeloppet</span><span class="sxs-lookup"><span data-stu-id="b0b2f-170">Calculated percentage of net amount</span></span>
<span data-ttu-id="b0b2f-171">Den beräknade procentandelen av nettobeloppet hanterar momsberäkningen annorlunda beroende på inställningen av parametern Moms ingår i beloppen för dokumentet eller journalen.</span><span class="sxs-lookup"><span data-stu-id="b0b2f-171">The Calculated percentage of net amount handles tax calculation differently depending on the setting of the Amounts include sales tax parameter for the document or journal.</span></span>
### <a name="example-1"></a><span data-ttu-id="b0b2f-172">Exempel 1</span><span class="sxs-lookup"><span data-stu-id="b0b2f-172">Example 1</span></span>

<span data-ttu-id="b0b2f-173">Dokumentet/journalen ställs in på Moms ingår i beloppen = Ja, Transaktionens radbelopp: 10,00 Momssats 25 % Moms: Transaktionens radbelopp * (10,00 × 25 %) = 2,50 basbelopp för moms (ursprungsbelopp): Transaktionens radbelopp - moms (10,00 - 2,50) = 7,50</span><span class="sxs-lookup"><span data-stu-id="b0b2f-173">Document / journal is set to Amounts include sales tax = Yes Transaction line amount: 10.00 Tax rate: 25% Sales tax: Transaction line amount x tax rate (10.00 x 25%) = 2.50 Tax base amount (origin amount): Transaction line amount - Sales tax (10.00 - 2.50) = 7.50</span></span>

### <a name="example-2"></a><span data-ttu-id="b0b2f-174">Exempel 2</span><span class="sxs-lookup"><span data-stu-id="b0b2f-174">Example 2</span></span>

<span data-ttu-id="b0b2f-175">Dokumentet/journalen ställs in på Moms ingår i beloppen = Nej, Transaktionens radbelopp: 10,00 Momssats: 25 % (Transaktionens radbelopp x Momssats) / (100 - Momssats) (10,00 x 25 %) / (100 % - 25 %) = 3,33 Basbelopp för moms (ursprungsbelopp): Transaktionens radbelopp = 10,00 </span><span class="sxs-lookup"><span data-stu-id="b0b2f-175">Document / journal is set to Amounts include sales tax = No Transaction line amount: 10.00 Tax rate: 25% Sales tax: (Transaction line amount x tax rate) / (100 - tax rate) (10.00 x 25%) / (100% - 25%) = 3.33 Tax base amount (origin amount): Transaction line amount = 10.00</span></span>



<a name="see-also"></a><span data-ttu-id="b0b2f-176">Se även</span><span class="sxs-lookup"><span data-stu-id="b0b2f-176">See also</span></span>
--------

[<span data-ttu-id="b0b2f-177">Bestämning av momssatser baserat på fälten Marginal base och Calculation method</span><span class="sxs-lookup"><span data-stu-id="b0b2f-177">Determining sale tax rates based on the Marginal base and Calculation method fields</span></span>](marginal-base-field.md)

[<span data-ttu-id="b0b2f-178">Alternativ för hela belopp och intervallberäkning för momskoder</span><span class="sxs-lookup"><span data-stu-id="b0b2f-178">Whole amount and Interval calculation options for sales tax codes</span></span>](whole-amount-interval-options-sales-tax-codes.md)




