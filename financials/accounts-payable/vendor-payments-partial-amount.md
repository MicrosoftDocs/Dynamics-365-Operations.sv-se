---
title: "Leverantörsbetalningar för ett delvist belopp"
description: "Ibland kan du utföra betalningar som är mindre än beloppet i en faktura till en leverantör. Den här artikeln beskriver de olika alternativen för att hantera den här situationen. Vilka alternativ som är tillgängliga för dig beror på dina affärskrav och konfigurationer."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 14321
ms.assetid: 9a17075e-5325-4d55-a1e5-1791b8c460a0
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 48812d33be6b84bbe0eac15adc4bd41a3ea8706b
ms.contentlocale: sv-se
ms.lasthandoff: 05/25/2017


---

# <a name="vendor-payments-for-a-partial-amount"></a>Leverantörsbetalningar för ett delvist belopp

[!include[banner](../includes/banner.md)]


Ibland kan du utföra betalningar som är mindre än beloppet i en faktura till en leverantör. Den här artikeln beskriver de olika alternativen för att hantera den här situationen. Vilka alternativ som är tillgängliga för dig beror på dina affärskrav och konfigurationer. 

<a name="cash-discount-amounts"></a>Kassarabattbelopp
---------------------

En leverantör kan erbjuda dig en kassarabatt för att betala en faktura före förfallodatumet. Till exempel anger du en faktura på 100,00 som anger en kassarabatt 2 procent, om fakturan betalas inom 10 dagar. Förfallodatumtermerna är 30 dagar. Om ett betalningsförslag använder kassarabatt som villkor för att välja en faktura om om förslaget körs på eller före kassarabattsdatumet, kommer fakturan att markeras till betalning och betalningen skapas för 98,00. En kassarabatt kan också användas för en enstaka betalning som skapats manuellt.

## <a name="partial-payments-with-cash-discounts"></a>Delbetalningar med kassarabatter
När du gör en delvis betalning, kan du planera att göra en ytterligare delvis betalning för att helt kvitta fakturan. För att använda en kassarabatt för en delbetalning måste du ange alternativet **Beräkna kassarabatter för delbetalningar ** till **Ja** på sidan **Obetalda parametrar för konto**. 

Om du till exempel får 2 procent kassarabatt om fakturan betalas inom 10 dagar, efter att den har utfärdats. En faktura på 100,00 bokförs. Om du gör en betalning på 49,00 inom 10 dagar, anger du ett debetbelopp på 49,00 i en betalningsjournal. När du kvittar delbetalningen på sidan **Kvitta öppna transaktioner** visas **1,00** i fältet **Kassarabattbelopp att utnyttja**. 

> [!NOTE] 
> Om du anger en delbetalning och anger hela fakturabeloppet i fältet **Belopp att kvitta**, kommer fältet **Kassarabattbelopp att utnyttja** att beräknas om automatiskt när du bokför transaktionerna.

## <a name="credit-notes-with-cash-discounts"></a>Kreditfakturor med kassarabatter
Du kanske returnerar vissa av artiklarna i en faktura och tar emot en kreditfaktura. Om en kassarabatt utfördes på den ursprungliga fakturan, kan du dra av värdet för rabatter och ta emot en återbetalning för rätt beloppet. Om alternativet **Beräkna kassarabatter för kreditfakturor** anges till **Ja** på sidan **Parametrar för leverantörsreskontra** beräknas rabatten automatiskt för kreditfakturan. 

Om du till exempel får 2 procent kassarabatt om fakturan betalas inom 10 dagar, efter att den har utfärdats. En faktura på 100,00 bokförs. Om du återlämnar varorna och få en kreditfaktura kan du ange kreditfakturan för hela beloppet för den ursprungliga fakturan, 100,00 tillsammans med 2 procents kassarabatten som också definieras på kreditnotan.  När du visar kreditfakturan på sidan **Kvitta transaktioner**, visas **98,00** i fältet **Belopp att kvitta** och **-2,00** visas i fältet **Kassarabattbelopp**. Rabattbeloppet bokförs på ett kassarabattkonto.

## <a name="overpaymentunderpayment-amounts"></a>Över- och underbetalningsbelopp
Du kanske vill göra en delvis betalning, där beloppet som fortfarande måste kvittas är mycket litet. Exempelvis är leverantörsfakturan för 1 000,00 och du betalar 999,90. Om det resterande beloppet är mindre än det belopp som angetts för över- eller underbetalningar på sidan **Parametrar för leverantörsreskontra** bokförs skillnaden automatiskt till ett överbetalning-/underbetalningredovisningskonto.




