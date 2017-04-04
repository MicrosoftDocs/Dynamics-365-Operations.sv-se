---
title: "Leverantörsbetalningar för ett delvist belopp"
description: "Ibland kan du utföra betalningar som är mindre än beloppet i en faktura till en leverantör. Den här artikeln beskriver de olika alternativen för att hantera den här situationen. Vilka alternativ som är tillgängliga för dig beror på dina affärskrav och konfigurationer."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
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
translationtype: Human Translation
ms.sourcegitcommit: 2cb439e871d57f74c296697cfc42705fb0121bb7
ms.openlocfilehash: 4d243e6a9a68b69a6b32748344fc606ff3f2d965
ms.lasthandoff: 03/31/2017


---

# <a name="vendor-payments-for-a-partial-amount"></a>Leverantörsbetalningar för ett delvist belopp

Ibland kan du utföra betalningar som är mindre än beloppet i en faktura till en leverantör. Den här artikeln beskriver de olika alternativen för att hantera den här situationen. Vilka alternativ som är tillgängliga för dig beror på dina affärskrav och konfigurationer. 

<a name="cash-discount-amounts"></a>Kassarabattbelopp
---------------------

En leverantör kan erbjuda dig en kassarabatt för att betala en faktura före förfallodatumet. Till exempel anger du en faktura på 100,00 som anger en kassarabatt 2 procent, om fakturan betalas inom 10 dagar. Förfallodatumtermerna är 30 dagar. Om ett betalningsförslag används kassarabatten som villkor för att välja en faktura om förslaget körs på eller före kassarabattsdatumet, fakturan som har valts för betalning och skapas betalningen för 98.00. En kassarabatt kan också hämtas ett direkt stöd som skapats manuellt.

## <a name="partial-payments-with-cash-discounts"></a>Delbetalningar med kassarabatter
När du gör en delvis betalning, kan du planera att göra en ytterligare delvis betalning för att helt kvitta fakturan. Ska en kassarabatt för en delbetalning måste du ange den ** beräkna kassarabatter för delbetalningar ** att **Ja** på de **konto leverantörsreskontraparametrar** sida. 

Om du till exempel får 2 procent kassarabatt om fakturan betalas inom 10 dagar, efter att den har utfärdats. En faktura på 100,00 bokförs. Om du gör en betalning av 49.00 inom 10 dagar, kan du ange ett debetbelopp på 49.00 i en betalningsjournal. När du kvittar på delbetalningen på den **kvitta öppna transaktioner** sidan **1,00** visas i den **Kassarabattbeloppet ta** fält. 

> [!NOTE] 
> Om du anger en delbetalning och lämnar hela fakturabeloppet i den **kvittningsbeloppet** fältet den **Kassarabattbeloppet ta** omberäknas automatiskt när du bokför transaktioner.

## <a name="credit-notes-with-cash-discounts"></a>Kreditfakturor med kassarabatter
Du kanske returnerar vissa av artiklarna i en faktura och tar emot en kreditfaktura. Om en kassarabatt utfördes på den ursprungliga fakturan, kan du dra av värdet för rabatter och ta emot en återbetalning för rätt beloppet. Om den ** beräkna kassarabatter för kreditfakturor ** är **Ja** på de **parametrar för leverantörsreskontra** sidan rabatten beräknas automatiskt för kreditfakturan. 

Om du till exempel får 2 procent kassarabatt om fakturan betalas inom 10 dagar, efter att den har utfärdats. En faktura på 100,00 bokförs. Om du återlämnar varorna och få en kreditfaktura kan du ange kreditfakturan för hela beloppet för den ursprungliga fakturan 100,00 tillsammans med 2 procent kassarabatten som definieras också i kreditnotan.  När du visar kreditfakturan på de **kvitta transaktioner** sidan **98.00** visas i den **kvittningsbeloppet** fältet och **-2.00** visas i den **Kassarabattbeloppet** fält. Rabattbeloppet bokförs på ett kassarabattkonto.

## <a name="overpaymentunderpayment-amounts"></a>Över- och underbetalningsbelopp
Du kanske vill göra en delvis betalning, där beloppet som fortfarande måste kvittas är mycket litet. Exempelvis är leverantörsfakturan för 1 000,00 och du betalar 999,90. Om det resterande beloppet är mindre än det belopp som angetts för över- eller underbetalningar på sidan **Parametrar för leverantörsreskontra** bokförs skillnaden automatiskt till ett överbetalning-/underbetalningredovisningskonto.


