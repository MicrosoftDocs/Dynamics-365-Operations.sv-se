---
title: Moms beräknas inte, eller också är momsbeloppet noll
description: Detta avsnitt innehåller felsökningsinformation som kan vara till hjälp när momsbeloppet är 0 (noll) eller när moms inte beräknas.
author: shtao
ms.date: 04/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: c398579a0a408e7f5625a3e801a967955c4b1e5b
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020125"
---
# <a name="tax-isnt-calculated-or-the-tax-amount-is-zero"></a><span data-ttu-id="b0d33-103">Moms beräknas inte, eller också är momsbeloppet noll</span><span class="sxs-lookup"><span data-stu-id="b0d33-103">Tax isn't calculated or the tax amount is zero</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b0d33-104">En transaktion kan ha ett radbelopp som inte är 0 (noll), men antingen beräknas inte momsbeloppet, också är det beräknade momsbeloppet 0.</span><span class="sxs-lookup"><span data-stu-id="b0d33-104">A transaction might have a line amount that isn't 0 (zero), but either tax isn't calculated or the calculated tax amount is 0.</span></span> <span data-ttu-id="b0d33-105">Felsök det här problemet genom att följa stegen i följande avsnitt.</span><span class="sxs-lookup"><span data-stu-id="b0d33-105">To troubleshoot this issue, follow the steps in the following sections as required.</span></span>

## <a name="verify-that-tax-codes-are-correctly-selected-by-the-transaction"></a><span data-ttu-id="b0d33-106">Kontrollera att momskoderna har valts korrekt av transaktionen</span><span class="sxs-lookup"><span data-stu-id="b0d33-106">Verify that tax codes are correctly selected by the transaction</span></span>

<span data-ttu-id="b0d33-107">Om transaktionen inte väljer de korrekta momskoderna – eller om den inte väljer några momskoder alls – beräknas inte momsen på den.</span><span class="sxs-lookup"><span data-stu-id="b0d33-107">If the transaction doesn't select the correct tax codes, or if it doesn't select any tax codes, taxes won't be calculated on it.</span></span> <span data-ttu-id="b0d33-108">Följ dessa steg i syfte att kontrollera att momskoderna har valts korrekt av transaktionen.</span><span class="sxs-lookup"><span data-stu-id="b0d33-108">Follow these steps to verify that tax codes are correctly selected by the transaction.</span></span> 

1. <span data-ttu-id="b0d33-109">På transaktionsraden, på snabbfliken **Radinformation**, i fliken **Inställningar**, i avsnittet **Moms** bekräftar du att rätt momsgrupper har valts i fälten för **Artikelgrupp för moms** samt **Momsgrupp**.</span><span class="sxs-lookup"><span data-stu-id="b0d33-109">On the transaction line, on the **Line details** FastTab, on the **Setup** tab, in the **Sales tax** section, verify that the correct tax groups are selected in the **Item sales tax group** and **Sales tax group** fields.</span></span> <span data-ttu-id="b0d33-110">Om rätt momsgrupper inte har valts, väljer du dem.</span><span class="sxs-lookup"><span data-stu-id="b0d33-110">If the correct tax groups aren't selected, select them.</span></span>

    <span data-ttu-id="b0d33-111">[![Fält för Artikelgrupp för moms samt Momsgrupp](./media/tax-not-calculated-tax-amount-zero-Picture1.png)](./media/tax-not-calculated-tax-amount-zero-Picture1.png)</span><span class="sxs-lookup"><span data-stu-id="b0d33-111">[![Item sales tax group and Sales tax group fields](./media/tax-not-calculated-tax-amount-zero-Picture1.png)](./media/tax-not-calculated-tax-amount-zero-Picture1.png)</span></span>

2. <span data-ttu-id="b0d33-112">Gå till **Skatt** \> **Indirekta skatter** \> **Moms** \> **Momsgrupper**.</span><span class="sxs-lookup"><span data-stu-id="b0d33-112">Go to **Tax** \> **Indirect taxes** \> **Sales tax** \> **Sales tax groups**.</span></span>
3. <span data-ttu-id="b0d33-113">Välj lämplig momsgrupp – i snabbfliken **Inställningar** noterar du sedan skattekoden i fältet **Momskod**.</span><span class="sxs-lookup"><span data-stu-id="b0d33-113">Select the appropriate sales tax group, and then, on the **Setup** FastTab, make a note of the tax code in the **Sales tax code** field.</span></span>

    <span data-ttu-id="b0d33-114">[![Sida för momsgrupper](./media/tax-not-calculated-tax-amount-zero-Picture2.png)](./media/tax-not-calculated-tax-amount-zero-Picture2.png)</span><span class="sxs-lookup"><span data-stu-id="b0d33-114">[![Sales tax groups page](./media/tax-not-calculated-tax-amount-zero-Picture2.png)](./media/tax-not-calculated-tax-amount-zero-Picture2.png)</span></span>

4. <span data-ttu-id="b0d33-115">Gå till **Skatt** \> **Indirekta skatter** \> **Moms** \> **Artikelgrupper för moms**.</span><span class="sxs-lookup"><span data-stu-id="b0d33-115">Go to **Tax** \> **Indirect taxes** \> **Sales tax** \> **Item sales tax groups**.</span></span>
5. <span data-ttu-id="b0d33-116">Välj lämplig momsgrupp och kontrollera sedan på snabbfliken **Inställningar** att skattekoden i fältet **Momskod** matchar skattekoden för momsgruppen.</span><span class="sxs-lookup"><span data-stu-id="b0d33-116">Select the appropriate item sales tax group, and then, on the **Setup** FastTab, verify that the tax code in the **Sales tax code** field matches the tax code of the sales tax group.</span></span>

    <span data-ttu-id="b0d33-117">[![Sida för artikelmomsgrupper](./media/tax-not-calculated-tax-amount-zero-Picture3.png)](./media/tax-not-calculated-tax-amount-zero-Picture3.png)</span><span class="sxs-lookup"><span data-stu-id="b0d33-117">[![Item sales tax groups page](./media/tax-not-calculated-tax-amount-zero-Picture3.png)](./media/tax-not-calculated-tax-amount-zero-Picture3.png)</span></span>

6. <span data-ttu-id="b0d33-118">Om skattekoderna inte matchar uppdaterar du momskoden för en av grupperna.</span><span class="sxs-lookup"><span data-stu-id="b0d33-118">If the tax codes don't match, update the sales tax code for one of the groups.</span></span>

## <a name="verify-that-the-selected-tax-codes-arent-exempt-and-that-they-have-the-correct-tax-rate-value"></a><span data-ttu-id="b0d33-119">Kontrollera att de valda momskoderna inte är undantagna och att de har korrekt skattesatsvärde</span><span class="sxs-lookup"><span data-stu-id="b0d33-119">Verify that the selected tax codes aren't exempt and that they have the correct tax rate value</span></span>

<span data-ttu-id="b0d33-120">Om momskoderna är undantagna, eller om momssatsen är 0 (noll) blir momsberäkningen 0.</span><span class="sxs-lookup"><span data-stu-id="b0d33-120">If the tax codes are exempt, or if the tax rate is 0 (zero), the tax calculation result will be 0.</span></span> <span data-ttu-id="b0d33-121">Följ dessa steg för att fastställa om de valda momskoderna är undantagna, samt för att bekräfta att den korrekta momssatsen tillämpas på dem.</span><span class="sxs-lookup"><span data-stu-id="b0d33-121">Follow these steps to determine whether the selected tax codes are exempt and to verify that the correct tax rate is applied to them.</span></span>

1. <span data-ttu-id="b0d33-122">Gå till **Skatt** \> **Indirekta skatter** \> **Moms** \> **Momsgrupper**.</span><span class="sxs-lookup"><span data-stu-id="b0d33-122">Go to **Tax** \> **Indirect taxes** \> **Sales tax** \> **Sales tax groups**.</span></span>
2. <span data-ttu-id="b0d33-123">Välj lämplig momsgrupp och kontrollera sedan, i snabbfliken **Inställningar**, att kryssrutan **Undantagen** har rensats.</span><span class="sxs-lookup"><span data-stu-id="b0d33-123">Select the appropriate sales tax group, and then, on the **Setup** FastTab, verify that the **Exempt** check box is cleared.</span></span> <span data-ttu-id="b0d33-124">Rensa om denna har markerats.</span><span class="sxs-lookup"><span data-stu-id="b0d33-124">If it's selected, clear it.</span></span>

    <span data-ttu-id="b0d33-125">[![Kryssrutan Undantagen på sidan Momsgrupper](./media/tax-not-calculated-tax-amount-zero-Picture4.png)](./media/tax-not-calculated-tax-amount-zero-Picture4.png)</span><span class="sxs-lookup"><span data-stu-id="b0d33-125">[![Exempt check box on the Sales tax groups page](./media/tax-not-calculated-tax-amount-zero-Picture4.png)](./media/tax-not-calculated-tax-amount-zero-Picture4.png)</span></span>

3. <span data-ttu-id="b0d33-126">Gå till **Moms** \> **Indirekta skatter** \> **Moms** \> **Momskoder**.</span><span class="sxs-lookup"><span data-stu-id="b0d33-126">Go to **Tax** \> **Indirect taxes** \> **Sales tax** \> **Sales tax codes**.</span></span>
4. <span data-ttu-id="b0d33-127">Välj lämplig momskod och kontrollera sedan att momssatsvärdet i fältet **Värde** inte är 0 (noll).</span><span class="sxs-lookup"><span data-stu-id="b0d33-127">Select the appropriate sales tax code, and then verify that the tax rate value in the **Value** field isn't 0 (zero).</span></span> <span data-ttu-id="b0d33-128">Om det är 0 uppdaterar du fältet så att det får rätt momssats.</span><span class="sxs-lookup"><span data-stu-id="b0d33-128">If it's 0, update the field so that it's set to the correct tax rate.</span></span>

    <span data-ttu-id="b0d33-129">[![Värdefält på värdesidan för moms](./media/tax-not-calculated-tax-amount-zero-Picture5.png)](./media/tax-not-calculated-tax-amount-zero-Picture5.png)</span><span class="sxs-lookup"><span data-stu-id="b0d33-129">[![Value field on the Sales tax code values page](./media/tax-not-calculated-tax-amount-zero-Picture5.png)](./media/tax-not-calculated-tax-amount-zero-Picture5.png)</span></span>

## <a name="determine-whether-zero-is-the-correct-tax-amount"></a><span data-ttu-id="b0d33-130">Fastställ om noll är korrekt momsbelopp</span><span class="sxs-lookup"><span data-stu-id="b0d33-130">Determine whether zero is the correct tax amount</span></span>

<span data-ttu-id="b0d33-131">I vissa scenarier är momsbeloppet 0 (noll) korrekt.</span><span class="sxs-lookup"><span data-stu-id="b0d33-131">In some scenarios, a tax amount of 0 (zero) is correct.</span></span> <span data-ttu-id="b0d33-132">Följ anvisningarna nedan och ta reda på om 0 är korrekt momsbelopp för transaktionen.</span><span class="sxs-lookup"><span data-stu-id="b0d33-132">Follow these steps to determine whether 0 is the correct tax amount for your transaction.</span></span>

1. <span data-ttu-id="b0d33-133">Gå till **Redovisning** \> **Inställningar för transaktionsregister** \> **Redovisningsparametrar**.</span><span class="sxs-lookup"><span data-stu-id="b0d33-133">Go to **General ledger** \> **Ledger setup** \> **General ledger parameters**.</span></span>
2. <span data-ttu-id="b0d33-134">På fliken **Moms**, i fältet **Beräkningsmetod**, bekräftar du att **Summa** har valts.</span><span class="sxs-lookup"><span data-stu-id="b0d33-134">On the **Sales tax** tab, in the **Calculation method** field, verify that **Total** is selected.</span></span>

    <span data-ttu-id="b0d33-135">[![Fältet för beräkningsmetod på sidan Redovisningsparametrar](./media/tax-not-calculated-tax-amount-zero-Picture6.png)](./media/tax-not-calculated-tax-amount-zero-Picture6.png)</span><span class="sxs-lookup"><span data-stu-id="b0d33-135">[![Calculation method field on the General ledger parameters page](./media/tax-not-calculated-tax-amount-zero-Picture6.png)](./media/tax-not-calculated-tax-amount-zero-Picture6.png)</span></span>

3. <span data-ttu-id="b0d33-136">Gå till **Moms** \> **Indirekta skatter** \> **Moms** \> **Momskoder**.</span><span class="sxs-lookup"><span data-stu-id="b0d33-136">Go to **Tax** \> **Indirect taxes** \> **Sales tax** \> **Sales tax codes**.</span></span>
4. <span data-ttu-id="b0d33-137">Välj lämplig momskod, välj **Beräkning** \> **Marginalbas** och bekräfta att marginalbasen angetts som **Nettobelopp för fakturasaldo** eller **Fakturasumma inkl. andra momsbelopp**.</span><span class="sxs-lookup"><span data-stu-id="b0d33-137">Select the appropriate sales tax code, select **Calculation** \> **Marginal base**, and verify that the marginal base is set to **Net amount of invoice balance** or **Invoice total incl. other sales tax amounts**.</span></span> <span data-ttu-id="b0d33-138">Mer information finns i [Fakturasumma inkl. andra momsbelopp](marginal-base-field.md#invoice-total-incl-other-sales-tax-amounts).</span><span class="sxs-lookup"><span data-stu-id="b0d33-138">For more information, see the [Invoice total incl. other sales tax amounts](marginal-base-field.md#invoice-total-incl-other-sales-tax-amounts).</span></span>
5. <span data-ttu-id="b0d33-139">Om de korrekta värdena ställts in i steg 2 och 4 ska du avgöra om det totala beloppet för transaktionen är 0 (noll).</span><span class="sxs-lookup"><span data-stu-id="b0d33-139">If the correct values are set in steps 2 and 4, determine whether the total amount of the transaction is 0 (zero).</span></span> <span data-ttu-id="b0d33-140">Om totalbeloppet är 0 är ett momsbelopp på 0 det förväntade resultatet.</span><span class="sxs-lookup"><span data-stu-id="b0d33-140">If the total amount is 0, a tax amount of 0 is the expected result.</span></span> <span data-ttu-id="b0d33-141">Eftersom momsberäkningen baseras på det totala fakturasaldot och det beloppet inte är rad för rad, fördelas momsbeloppet 0 på varje rad efter momsberäkningen.</span><span class="sxs-lookup"><span data-stu-id="b0d33-141">Because the tax calculation is based on the total amount of the invoice balance, and that amount isn't line by line, the tax amount of 0 will be allocated to each line after the tax calculation.</span></span>

## <a name="determine-whether-customization-exists"></a><span data-ttu-id="b0d33-142">Bestäm om anpassning finns</span><span class="sxs-lookup"><span data-stu-id="b0d33-142">Determine whether customization exists</span></span>

<span data-ttu-id="b0d33-143">Om du har utfört stegen i de föregående avsnitten men inte hittat något problem, ska du fastställa om det finns någon anpassning.</span><span class="sxs-lookup"><span data-stu-id="b0d33-143">If you've completed the steps in the previous sections but have found no issue, determine whether customization exists.</span></span> <span data-ttu-id="b0d33-144">Om det inte finns någon anpassning skapar du en Microsoft-servicebegäran för ytterligare support.</span><span class="sxs-lookup"><span data-stu-id="b0d33-144">If no customization exists, create a Microsoft service request for further support.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
