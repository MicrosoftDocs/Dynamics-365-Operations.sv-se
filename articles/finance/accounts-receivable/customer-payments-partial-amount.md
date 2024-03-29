---
title: Kundbetalningar för ett delbelopp
description: Ibland kan kunder betala ett belopp som är mindre än beloppet i en faktura. Det här avsnittet innehåller en beskrivning av de olika alternativen för att hantera den här situationen. Vilka alternativ som är tillgängliga för dig beror på dina affärskrav och konfigurationer.
author: ShivamPandey-msft
ms.date: 01/08/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustPaymEntry
audience: Application User
ms.reviewer: kfend
ms.custom: 13011
ms.assetid: 20423a2d-6997-4e1c-a596-a77016600071
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b688e62fcf1f223668b79ca6014da85b01000715
ms.sourcegitcommit: d1683d033fc74adbc4465dd26f7b0055e7639753
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/05/2022
ms.locfileid: "8713484"
---
# <a name="customer-payments-for-a-partial-amount"></a>Kundbetalningar för ett delbelopp

[!include [banner](../includes/banner.md)]

Ibland kan kunder betala ett belopp som är mindre än beloppet i en faktura. Det här avsnittet innehåller en beskrivning av de olika alternativen för att hantera den här situationen. Vilka alternativ som är tillgängliga för dig beror på dina affärskrav och konfigurationer.

## <a name="partial-payment-with-no-discount"></a>Delbetalning utan rabatt

Kunder kan göra en delbetalning eftersom de inte bara har tillräckligt med kontanter för att betala hela fakturan, eller om det finns en tvist om en artikel på fakturan. I den här situationen kan fakturan delvis kvittas mot betalningen. Fakturan kommer att förbli öppen och visar ett saldo.

## <a name="discount-amounts"></a>Rabattbelopp
Du kan erbjuda kunderna en kassarabatt för att betala en faktura före förfallodatumet. Till exempel anger du en faktura på 100,00 som anger en kassarabatt 2 procent, om fakturan betalas inom 10 dagar. Förfallodatumtermerna är 30 dagar. Om du tar emot en betalning på 98,00 inom 10 dagar, registrerar du betalningen på 98,00. Därefter när fakturan har markerats för kvittning, utnyttjas kassarabatten automatiskt.

## <a name="partial-payments-with-cash-discounts"></a>Delbetalningar med kassarabatter
När kunder gör en delbetalning, kan de planera att göra en ytterligare delbetalning för att helt kvitta fakturan. För att få kassarabatt för en delbetalning måste du ange alternativet **Beräkna kassarabatter för delbetalningar** till **Ja** på sidan **Parametrar för kundreskontra**. 

Om du till exempel erbjuder 2 procent kassarabatt om fakturan betalas inom 10 dagar, efter att den har utfärdats. En faktura på 100,00 bokförs. Om du tar emot en betalning på 49,00 dagar inom 10 dagar, anger du ett kreditbelopp på 49,00 i en betalningsjournal. När du kvittar delbetalningen på sidan **Kvitta transaktioner** visas **1,00** i fältet **Kassarabattbelopp att utnyttja**. Rabattbeloppet bokförs på ett kassarabattkonto. 

> [!NOTE] 
> Om du anger en delbetalning och anger hela fakturabeloppet i fältet **Belopp att kvitta**, kommer fältet **Kassarabattbelopp att utnyttja** att beräknas om automatiskt när du bokför transaktionerna.

## <a name="credit-notes-with-discounts"></a>Kreditfakturor med rabatter
Om kunder returnerar vissa av artiklarna i en faktura kanske du utfärdar en kreditfaktura. Om en kassarabatt utfördes på den ursprungliga fakturan, ska kreditnotan till kunden vara netto av kassarabatten som utnyttjades av kunden. Om alternativet **Beräkna kassarabatter för kreditfakturor** anges på sidan **Ja** på sidan **Parametrar för kundreskontra** beräknas rabatten automatiskt för kreditfakturan. 

Om du till exempel erbjuder betalningsvillor som anger 2 procent kassarabatt om fakturan betalas inom 10 dagar, efter att den har utfärdats. En faktura på 100,00 har bokförts, och kunden har utnyttjat kassarabatten. Om kunden returnerar varor, och du utfärdar en kreditfaktura, kan du registrera kreditfakturan för -100,00. När du visar kreditfakturan på sidan **Kvitta öppna transaktioner**, visas **98,00** i fältet **Belopp att kvitta** och **-2,00** visas i fältet **Kassarabattbelopp**. Rabattbeloppet bokförs på ett kassarabattkonto.

## <a name="overpaymentunderpayment-amounts"></a>Över- och underbetalningsbelopp
När kunder gör en betalning kan det finnas ett mycket litet belopp som fortfarande måste kvittas. Till exempel fakturerar du kunden 1 000,00 och kunden betalar 999,90. Om det resterande beloppet är mindre än det belopp som angetts för över- eller underbetalningar på sidan **Parametrar för kundreskontra** bokförs skillnaden automatiskt till ett överbetalning-/underbetalningredovisningskonto.

## <a name="full-settlement"></a>Full betalning
Kunder kan göra en delbetalning där det resterande beloppet inte betalas men är större än det underbetalningsbeloppet som anges på sidan **Leverantörsreskontraparametrar**. Om du vill markera fakturan som helt kvittad kan du använda alternativet **Full kvittning** på sidan **Kvitta transaktion**. (Du kan aktivera den fullständiga kvittningsfunktionen, med hjälp av en konfigurationsnyckel.) Till exempel bokförs en faktura på 1 000,00 och kunden gör en betalning på 990,00. Du har kommit överens om att kunden inte behöver betala återstående 10,00. När du har märkt fakturan för kvittning kan du även markera **Full kvittning**. Fakturan betraktas sedan som helt kvittad. Skillnaden på 10,00 bokförs på ett kassarabattskonto som ytterligare kassarabattbelopp.


Mer information finns i [Sätta in kundbetalningar](tasks/deposit-customer-payments.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
