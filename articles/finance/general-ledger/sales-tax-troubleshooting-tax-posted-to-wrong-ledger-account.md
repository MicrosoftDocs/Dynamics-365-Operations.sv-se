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
# <a name="tax-is-posted-to-the-wrong-ledger-account-in-the-voucher"></a>Moms bokförs på fel redovisningskonto i verifikationen

[!include [banner](../includes/banner.md)]

I samband med bokföring kan moms komma att bokföras på fel redovisningskonto i verifikationen. Felsök det här problemet genom att följa stegen i följande avsnitt. I exemplen i det här avsnittet används en försäljningsorder som affärsdokument.

## <a name="find-the-tax-code-of-the-incorrectly-posted-tax-transaction"></a>Hitta momskoden för den felaktigt bokförda momstransaktionen

1. På sidan **Verifikationstransaktioner** väljer du den transaktion som du vill arbeta med och sedan **Bokförd moms**.

    [![Knappen för Bokförd moms på sidan Verifikationstransaktioner](./media/tax-posted-to-wrong-ledger-account-Picture1.png)](./media/tax-posted-to-wrong-ledger-account-Picture1.png)

2. Kontrollera värdet i fältet **Momskod**. I det här exemplet är detta **VAT 19**.

    [![Fältet för momskod på sidan Bokförd moms](./media/tax-posted-to-wrong-ledger-account-Picture2.png)](./media/tax-posted-to-wrong-ledger-account-Picture2.png)

## <a name="check-the-ledger-posting-group-of-the-tax-code"></a>Kontrollera momskodens redovisningsbokföringsgrupp

1. Gå till **Moms** \> **Indirekta skatter** \> **Moms** \> **Momskoder**.
2. Sök efter och välj momskod, och granska sedan värdet i fältet **Redovisningsbokföringsgrupp**. I detta exempel är detta **VAT**.

    [![Fältet Redovisningsbokföring på sidan Momskoder](./media/tax-posted-to-wrong-ledger-account-Picture3.png)](./media/tax-posted-to-wrong-ledger-account-Picture3.png)

3. Värdet i fältet **Redovisningsbokföringsgrupp** är en länk. Markera länken om du vill visa mer information om gruppens konfiguration. Du kan även markera och hålla ned (eller högerklicka) i fältet och sedan välja **Visa detaljer**.

    [![Kommandot Visa information](./media/tax-posted-to-wrong-ledger-account-Picture4.png)](./media/tax-posted-to-wrong-ledger-account-Picture4.png)

4. Kontrollera att kontonumret är korrekt och i enlighet med transationstyp en i fältet **Momsskuld**. Om det inte är det ska du välja rätt konto att bokföra på. I detta exempel ska momsen för försäljningsordern bokföras på momsskuldkonto 222200.

    [![Fältet Momsskuld på sidan Redovisningsbokföringsgrupper](./media/tax-posted-to-wrong-ledger-account-Picture5.png)](./media/tax-posted-to-wrong-ledger-account-Picture5.png)

    Följande register ger information om respektive fält på sidan **Redovisningsbokföringsgrupper**.

    | Fält                  | beskrivning |
    |------------------------|-------------|
    | Momsskuld      | Huvudkontot för utgående moms som ska inbetalas till skattemyndigheten. |
    | Momsfordran   | Huvudkontot för ingående moms som erhålles från skattemyndigheten. |
    | Importavgift, utgift        | Huvudkontot som används för att bokföra avdragsgill moms som leverantörer inte gör anspråk på eller rapporterar till skattemyndigheten som en del av EU-momsen med omvänd moms på varor och tjänster (GST)/harmoniserad moms (HST). **Använd moms** måste ha valts för momskoden i den momsgrupp som används i denna transaktion. Detta fält är inte tillgängligt om alternativet **Använd momsbeskattningsregler** har valts på sidan **Redovisningsparametrar** . |
    | Importavgift, skuld        | Huvudkontot som används för att bokföra ingående moms som ska inbetalas till skattemyndigheten. |
    | Kvittningskonto     | Det huvudkonto som används för att bokföra nettosaldot för de redovisningskonton som anges i fälten **Använd momsskuld** och **Momsfordran**. |
    | Leverantörskassarabatt   | Det huvudkonto som används för att bokföra en kassarabatt för momskoder som är kopplade till denna redovisningsbokföringsgrupp. |
    | Kundkassarabatt | Det huvudkonto som används för att bokföra en kassarabatt för momskoder som är kopplade till denna redovisningsbokföringsgrupp. |

    Mer information finns i [Konfigurera redovisningsbokföringsgrupper för moms](tasks/set-up-ledger-posting-groups-sales-tax.md)

## <a name="debug-in-code-to-check-ledger-dimensions"></a>Felsöka i kod för att kontrollera redovisningsdimensioner

I koden bestäms bokföringskontot av redovisningsdimensionen. Redovisningsdimensionen sparar post-ID:t för ett konto i databasen.

1. För en försäljningsorder lägger du till en brytpunkt på metoderna **Tax::saveAndPost()** och **Tax::post()**. Var uppmärksam på värdet i **\_ledgerDimension**.

    [![Exempel på försäljningsorderkod som har en brytpunkt](./media/tax-posted-to-wrong-ledger-account-Picture6.png)](./media/tax-posted-to-wrong-ledger-account-Picture6.png)

    För en inköpsorder lägger du till en brytpunkt för metoderna **TaxPost::saveAndPost()** och **TaxPost::postToTaxTrans()**. Var uppmärksam på värdet i **\_ledgerDimension**.

    [![Exempel på inköpsorderkod som har en brytpunkt](./media/tax-posted-to-wrong-ledger-account-Picture7.png)](./media/tax-posted-to-wrong-ledger-account-Picture7.png)

2. Kör följande SQL-fråga för att hitta visningsvärdet för kontot i databasen, baserat på det post-ID som sparas av redovisningsdimensionen.

    ```sql
    select * from DIMENSIONATTRIBUTEVALUECOMBINATION where recid={the value of _ledgerDimension}
    ```

    [![Visa värdet på post-ID:t](./media/tax-posted-to-wrong-ledger-account-Picture8.png)](./media/tax-posted-to-wrong-ledger-account-Picture8.png)

3. Undersöka anropsstacken för att hitta var **_ledgerDimension**-värdet har tilldelats. Värdet kommer vanligtvis från **TmpTaxWorkTrans**. I det här fallet ska du lägga till en brytpunkt vid **TmpTaxWorkTrans::insert()** och **TmpTaxWorkTrans::update()** för att ta reda på var värdet har tilldelats.

## <a name="determine-whether-customization-exists"></a>Bestäm om anpassning finns

Om du har utfört stegen i de föregående avsnitten men inte hittat något problem, ska du fastställa om det finns någon anpassning. Om det inte finns någon anpassning skapar du en Microsoft-servicebegäran för ytterligare support.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
