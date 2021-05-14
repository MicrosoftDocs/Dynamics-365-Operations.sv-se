---
title: Moms bokförs på fel redovisningskonto i verifikationen
description: Detta avsnitt innehåller felsökningsinformation som kan vara till hjälp när moms bokförs på fel redovisningskonto i verifikationen.
author: qire
manager: beya
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 0404d71f0492e188ed5da62387bb90a336e69c5a
ms.sourcegitcommit: 57668404d61359b33e0c0280f2f7c4eb829b1ed2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/27/2021
ms.locfileid: "5947711"
---
# <a name="tax-is-posted-to-the-wrong-ledger-account-in-the-voucher"></a><span data-ttu-id="4bf38-103">Moms bokförs på fel redovisningskonto i verifikationen</span><span class="sxs-lookup"><span data-stu-id="4bf38-103">Tax is posted to the wrong ledger account in the voucher</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4bf38-104">I samband med bokföring kan moms komma att bokföras på fel redovisningskonto i verifikationen.</span><span class="sxs-lookup"><span data-stu-id="4bf38-104">During posting, tax might be posted to the wrong ledger account in the voucher.</span></span> <span data-ttu-id="4bf38-105">Felsök det här problemet genom att följa stegen i följande avsnitt.</span><span class="sxs-lookup"><span data-stu-id="4bf38-105">To troubleshoot this issue, follow the steps in the following sections as required.</span></span> <span data-ttu-id="4bf38-106">I exemplen i det här avsnittet används en försäljningsorder som affärsdokument.</span><span class="sxs-lookup"><span data-stu-id="4bf38-106">The examples in this topic use a sales order as the business document.</span></span>

## <a name="find-the-tax-code-of-the-incorrectly-posted-tax-transaction"></a><span data-ttu-id="4bf38-107">Hitta momskoden för den felaktigt bokförda momstransaktionen</span><span class="sxs-lookup"><span data-stu-id="4bf38-107">Find the tax code of the incorrectly posted tax transaction</span></span>

1. <span data-ttu-id="4bf38-108">På sidan **Verifikationstransaktioner** väljer du den transaktion som du vill arbeta med och sedan **Bokförd moms**.</span><span class="sxs-lookup"><span data-stu-id="4bf38-108">On the **Voucher transactions** page, select the transaction that you want to work with, and then select **Posted sales tax**.</span></span>

    <span data-ttu-id="4bf38-109">[![Knappen för Bokförd moms på sidan Verifikationstransaktioner](./media/tax-posted-to-wrong-ledger-account-Picture1.png)](./media/tax-posted-to-wrong-ledger-account-Picture1.png)</span><span class="sxs-lookup"><span data-stu-id="4bf38-109">[![Posted sales tax button on the Voucher transactions page](./media/tax-posted-to-wrong-ledger-account-Picture1.png)](./media/tax-posted-to-wrong-ledger-account-Picture1.png)</span></span>

2. <span data-ttu-id="4bf38-110">Kontrollera värdet i fältet **Momskod**.</span><span class="sxs-lookup"><span data-stu-id="4bf38-110">Review the value in the **Sales tax code** field.</span></span> <span data-ttu-id="4bf38-111">I det här exemplet är detta **VAT 19**.</span><span class="sxs-lookup"><span data-stu-id="4bf38-111">In this example, it's **VAT 19**.</span></span>

    <span data-ttu-id="4bf38-112">[![Fältet för momskod på sidan Bokförd moms](./media/tax-posted-to-wrong-ledger-account-Picture2.png)](./media/tax-posted-to-wrong-ledger-account-Picture2.png)</span><span class="sxs-lookup"><span data-stu-id="4bf38-112">[![Sales tax code field on the Posted sales tax page](./media/tax-posted-to-wrong-ledger-account-Picture2.png)](./media/tax-posted-to-wrong-ledger-account-Picture2.png)</span></span>

## <a name="check-the-ledger-posting-group-of-the-tax-code"></a><span data-ttu-id="4bf38-113">Kontrollera momskodens redovisningsbokföringsgrupp</span><span class="sxs-lookup"><span data-stu-id="4bf38-113">Check the ledger posting group of the tax code</span></span>

1. <span data-ttu-id="4bf38-114">Gå till **Moms** \> **Indirekta skatter** \> **Moms** \> **Momskoder**.</span><span class="sxs-lookup"><span data-stu-id="4bf38-114">Go to **Tax** \> **Indirect taxes** \> **Sales tax** \> **Sales tax codes**.</span></span>
2. <span data-ttu-id="4bf38-115">Sök efter och välj momskod, och granska sedan värdet i fältet **Redovisningsbokföringsgrupp**.</span><span class="sxs-lookup"><span data-stu-id="4bf38-115">Find and select the tax code, and then review the value in the **Ledger posting group** field.</span></span> <span data-ttu-id="4bf38-116">I detta exempel är detta **VAT**.</span><span class="sxs-lookup"><span data-stu-id="4bf38-116">In this example, it's **VAT**.</span></span>

    <span data-ttu-id="4bf38-117">[![Fältet Redovisningsbokföring på sidan Momskoder](./media/tax-posted-to-wrong-ledger-account-Picture3.png)](./media/tax-posted-to-wrong-ledger-account-Picture3.png)</span><span class="sxs-lookup"><span data-stu-id="4bf38-117">[![Ledger posting group field on the Sales tax codes page](./media/tax-posted-to-wrong-ledger-account-Picture3.png)](./media/tax-posted-to-wrong-ledger-account-Picture3.png)</span></span>

3. <span data-ttu-id="4bf38-118">Värdet i fältet **Redovisningsbokföringsgrupp** är en länk.</span><span class="sxs-lookup"><span data-stu-id="4bf38-118">The value in the **Ledger posting group** field is a link.</span></span> <span data-ttu-id="4bf38-119">Markera länken om du vill visa mer information om gruppens konfiguration.</span><span class="sxs-lookup"><span data-stu-id="4bf38-119">To view the details of the group's configuration, select the link.</span></span> <span data-ttu-id="4bf38-120">Du kan även markera och hålla ned (eller högerklicka) i fältet och sedan välja **Visa detaljer**.</span><span class="sxs-lookup"><span data-stu-id="4bf38-120">Alternatively, select and hold (or right-click) in the field, and then select **View details**.</span></span>

    <span data-ttu-id="4bf38-121">[![Kommandot Visa information](./media/tax-posted-to-wrong-ledger-account-Picture4.png)](./media/tax-posted-to-wrong-ledger-account-Picture4.png)</span><span class="sxs-lookup"><span data-stu-id="4bf38-121">[![View details command](./media/tax-posted-to-wrong-ledger-account-Picture4.png)](./media/tax-posted-to-wrong-ledger-account-Picture4.png)</span></span>

4. <span data-ttu-id="4bf38-122">Kontrollera att kontonumret är korrekt och i enlighet med transationstyp en i fältet **Momsskuld**.</span><span class="sxs-lookup"><span data-stu-id="4bf38-122">In the **Sales tax payable** field, verify that the account number is correct, according to the transaction type.</span></span> <span data-ttu-id="4bf38-123">Om det inte är det ska du välja rätt konto att bokföra på.</span><span class="sxs-lookup"><span data-stu-id="4bf38-123">If it isn't, select the correct account to post to.</span></span> <span data-ttu-id="4bf38-124">I detta exempel ska momsen för försäljningsordern bokföras på momsskuldkonto 222200.</span><span class="sxs-lookup"><span data-stu-id="4bf38-124">In this example, the sales tax of the sales order should be posted to sales tax payable account 222200.</span></span>

    <span data-ttu-id="4bf38-125">[![Fältet Momsskuld på sidan Redovisningsbokföringsgrupper](./media/tax-posted-to-wrong-ledger-account-Picture5.png)](./media/tax-posted-to-wrong-ledger-account-Picture5.png)</span><span class="sxs-lookup"><span data-stu-id="4bf38-125">[![Sales tax payable field on the Ledger posting groups page](./media/tax-posted-to-wrong-ledger-account-Picture5.png)](./media/tax-posted-to-wrong-ledger-account-Picture5.png)</span></span>

    <span data-ttu-id="4bf38-126">Följande register ger information om respektive fält på sidan **Redovisningsbokföringsgrupper**.</span><span class="sxs-lookup"><span data-stu-id="4bf38-126">The following table provides information about each field on the **Ledger posting groups** page.</span></span>

    | <span data-ttu-id="4bf38-127">Fält</span><span class="sxs-lookup"><span data-stu-id="4bf38-127">Field</span></span>                  | <span data-ttu-id="4bf38-128">beskrivning</span><span class="sxs-lookup"><span data-stu-id="4bf38-128">Description</span></span> |
    |------------------------|-------------|
    | <span data-ttu-id="4bf38-129">Momsskuld</span><span class="sxs-lookup"><span data-stu-id="4bf38-129">Sales tax payable</span></span>      | <span data-ttu-id="4bf38-130">Huvudkontot för utgående moms som ska inbetalas till skattemyndigheten.</span><span class="sxs-lookup"><span data-stu-id="4bf38-130">The main account for outgoing sales taxes that are payable to the tax authority.</span></span> |
    | <span data-ttu-id="4bf38-131">Momsfordran</span><span class="sxs-lookup"><span data-stu-id="4bf38-131">Sales tax receivable</span></span>   | <span data-ttu-id="4bf38-132">Huvudkontot för ingående moms som erhålles från skattemyndigheten.</span><span class="sxs-lookup"><span data-stu-id="4bf38-132">The main account for incoming taxes that are received from the tax authority.</span></span> |
    | <span data-ttu-id="4bf38-133">Importavgift, utgift</span><span class="sxs-lookup"><span data-stu-id="4bf38-133">Use tax expense</span></span>        | <span data-ttu-id="4bf38-134">Huvudkontot som används för att bokföra avdragsgill moms som leverantörer inte gör anspråk på eller rapporterar till skattemyndigheten som en del av EU-momsen med omvänd moms på varor och tjänster (GST)/harmoniserad moms (HST).</span><span class="sxs-lookup"><span data-stu-id="4bf38-134">The main account that is used to post deductible use taxes that vendors don't claim or report to the tax authority as part of European Union (EU) reverse charge Goods and Services Tax (GST)/Harmonized Sales Tax (HST).</span></span> <span data-ttu-id="4bf38-135">**Använd moms** måste ha valts för momskoden i den momsgrupp som används i denna transaktion.</span><span class="sxs-lookup"><span data-stu-id="4bf38-135">**Use tax** must be selected for the sales tax code in the sales tax group that is used in the transaction.</span></span> <span data-ttu-id="4bf38-136">Detta fält är inte tillgängligt om alternativet **Använd momsbeskattningsregler** har valts på sidan **Redovisningsparametrar** .</span><span class="sxs-lookup"><span data-stu-id="4bf38-136">This field isn't available if **Apply sales tax taxation rules** is selected on the **General ledger parameters** page.</span></span> |
    | <span data-ttu-id="4bf38-137">Importavgift, skuld</span><span class="sxs-lookup"><span data-stu-id="4bf38-137">Use tax payable</span></span>        | <span data-ttu-id="4bf38-138">Huvudkontot som används för att bokföra ingående moms som ska inbetalas till skattemyndigheten.</span><span class="sxs-lookup"><span data-stu-id="4bf38-138">The main account that is used to post incoming use taxes that are payable to tax authorities.</span></span> |
    | <span data-ttu-id="4bf38-139">Kvittningskonto</span><span class="sxs-lookup"><span data-stu-id="4bf38-139">Settlement account</span></span>     | <span data-ttu-id="4bf38-140">Det huvudkonto som används för att bokföra nettosaldot för de redovisningskonton som anges i fälten **Använd momsskuld** och **Momsfordran**.</span><span class="sxs-lookup"><span data-stu-id="4bf38-140">The main account that is used to post the net balance of the ledger accounts that are specified in the **Use tax payable** and **Sales tax receivable** fields.</span></span> |
    | <span data-ttu-id="4bf38-141">Leverantörskassarabatt</span><span class="sxs-lookup"><span data-stu-id="4bf38-141">Vendor cash discount</span></span>   | <span data-ttu-id="4bf38-142">Det huvudkonto som används för att bokföra en kassarabatt för momskoder som är kopplade till denna redovisningsbokföringsgrupp.</span><span class="sxs-lookup"><span data-stu-id="4bf38-142">The main account that is used to post a cash discount for sales tax codes that are associated with this ledger posting group.</span></span> |
    | <span data-ttu-id="4bf38-143">Kundkassarabatt</span><span class="sxs-lookup"><span data-stu-id="4bf38-143">Customer case discount</span></span> | <span data-ttu-id="4bf38-144">Det huvudkonto som används för att bokföra en kassarabatt för momskoder som är kopplade till denna redovisningsbokföringsgrupp.</span><span class="sxs-lookup"><span data-stu-id="4bf38-144">The main account that is used to post a cash discount for sales tax codes that are associated with this ledger posting group.</span></span> |

    <span data-ttu-id="4bf38-145">Mer information finns i [Konfigurera redovisningsbokföringsgrupper för moms](tasks/set-up-ledger-posting-groups-sales-tax.md)</span><span class="sxs-lookup"><span data-stu-id="4bf38-145">For more information, see, [Set up Ledger posting groups for sales tax](tasks/set-up-ledger-posting-groups-sales-tax.md)</span></span>

## <a name="debug-in-code-to-check-ledger-dimensions"></a><span data-ttu-id="4bf38-146">Felsöka i kod för att kontrollera redovisningsdimensioner</span><span class="sxs-lookup"><span data-stu-id="4bf38-146">Debug in code to check ledger dimensions</span></span>

<span data-ttu-id="4bf38-147">I koden bestäms bokföringskontot av redovisningsdimensionen.</span><span class="sxs-lookup"><span data-stu-id="4bf38-147">In the code, the posting account is determined by the ledger dimension.</span></span> <span data-ttu-id="4bf38-148">Redovisningsdimensionen sparar post-ID:t för ett konto i databasen.</span><span class="sxs-lookup"><span data-stu-id="4bf38-148">The ledger dimension saves the record ID of an account in the database.</span></span>

1. <span data-ttu-id="4bf38-149">För en försäljningsorder lägger du till en brytpunkt på metoderna **Tax::saveAndPost()** och **Tax::post()**.</span><span class="sxs-lookup"><span data-stu-id="4bf38-149">For a sales order, add a breakpoint at the **Tax::saveAndPost()** and **Tax::post()** methods.</span></span> <span data-ttu-id="4bf38-150">Var uppmärksam på värdet i **\_ledgerDimension**.</span><span class="sxs-lookup"><span data-stu-id="4bf38-150">Pay attention to the value of **\_ledgerDimension**.</span></span>

    <span data-ttu-id="4bf38-151">[![Exempel på försäljningsorderkod som har en brytpunkt](./media/tax-posted-to-wrong-ledger-account-Picture6.png)](./media/tax-posted-to-wrong-ledger-account-Picture6.png)</span><span class="sxs-lookup"><span data-stu-id="4bf38-151">[![Sales order code sample that has a breakpoint](./media/tax-posted-to-wrong-ledger-account-Picture6.png)](./media/tax-posted-to-wrong-ledger-account-Picture6.png)</span></span>

    <span data-ttu-id="4bf38-152">För en inköpsorder lägger du till en brytpunkt för metoderna **TaxPost::saveAndPost()** och **TaxPost::postToTaxTrans()**.</span><span class="sxs-lookup"><span data-stu-id="4bf38-152">For a purchase order, add a breakpoint at the **TaxPost::saveAndPost()** and **TaxPost::postToTaxTrans()** methods.</span></span> <span data-ttu-id="4bf38-153">Var uppmärksam på värdet i **\_ledgerDimension**.</span><span class="sxs-lookup"><span data-stu-id="4bf38-153">Pay attention to the value of **\_ledgerDimension**.</span></span>

    <span data-ttu-id="4bf38-154">[![Exempel på inköpsorderkod som har en brytpunkt](./media/tax-posted-to-wrong-ledger-account-Picture7.png)](./media/tax-posted-to-wrong-ledger-account-Picture7.png)</span><span class="sxs-lookup"><span data-stu-id="4bf38-154">[![Purchase order code sample that has a breakpoint](./media/tax-posted-to-wrong-ledger-account-Picture7.png)](./media/tax-posted-to-wrong-ledger-account-Picture7.png)</span></span>

2. <span data-ttu-id="4bf38-155">Kör följande SQL-fråga för att hitta visningsvärdet för kontot i databasen, baserat på det post-ID som sparas av redovisningsdimensionen.</span><span class="sxs-lookup"><span data-stu-id="4bf38-155">Run the following SQL query to find the display value of the account in the database, based on the record ID that is saved by the ledger dimension.</span></span>

    ```sql
    select * from DIMENSIONATTRIBUTEVALUECOMBINATION where recid={the value of _ledgerDimension}
    ```

    <span data-ttu-id="4bf38-156">[![Visa värdet på post-ID:t](./media/tax-posted-to-wrong-ledger-account-Picture8.png)](./media/tax-posted-to-wrong-ledger-account-Picture8.png)</span><span class="sxs-lookup"><span data-stu-id="4bf38-156">[![Display value of the record ID](./media/tax-posted-to-wrong-ledger-account-Picture8.png)](./media/tax-posted-to-wrong-ledger-account-Picture8.png)</span></span>

3. <span data-ttu-id="4bf38-157">Undersöka anropsstacken för att hitta var **_ledgerDimension**-värdet har tilldelats.</span><span class="sxs-lookup"><span data-stu-id="4bf38-157">Examine the callstack to find where the **_ledgerDimension** value is assigned.</span></span> <span data-ttu-id="4bf38-158">Värdet kommer vanligtvis från **TmpTaxWorkTrans**.</span><span class="sxs-lookup"><span data-stu-id="4bf38-158">Usually, the value is from **TmpTaxWorkTrans**.</span></span> <span data-ttu-id="4bf38-159">I det här fallet ska du lägga till en brytpunkt vid **TmpTaxWorkTrans::insert()** och **TmpTaxWorkTrans::update()** för att ta reda på var värdet har tilldelats.</span><span class="sxs-lookup"><span data-stu-id="4bf38-159">In this case, you should add a breakpoint at **TmpTaxWorkTrans::insert()** and **TmpTaxWorkTrans::update()** to find where the value assigned.</span></span>

## <a name="determine-whether-customization-exists"></a><span data-ttu-id="4bf38-160">Bestäm om anpassning finns</span><span class="sxs-lookup"><span data-stu-id="4bf38-160">Determine whether customization exists</span></span>

<span data-ttu-id="4bf38-161">Om du har utfört stegen i de föregående avsnitten men inte hittat något problem, ska du fastställa om det finns någon anpassning.</span><span class="sxs-lookup"><span data-stu-id="4bf38-161">If you've completed the steps in the previous sections but have found no issue, determine whether customization exists.</span></span> <span data-ttu-id="4bf38-162">Om det inte finns någon anpassning skapar du en Microsoft-servicebegäran för ytterligare support.</span><span class="sxs-lookup"><span data-stu-id="4bf38-162">If no customization exists, create a Microsoft service request for further support.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
