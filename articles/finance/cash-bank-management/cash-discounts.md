---
title: Kassarabatter
description: Kassarabatter ställs in och delas för Leverantörsreskontra och Kundreskontra.  Den tillgängliga kassarabatten kan definieras på kundfakturan eller leverantörsfakturan och dras av om fakturan betalas innan kassarabattsdatumet har förfallit.
author: kweekley
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CashDisc
audience: Application User
ms.reviewer: roschlom
ms.custom: 3741
ms.assetid: c25f9d85-2702-46aa-8e61-0b4886e069b3
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9d4f6d5bdf4f2fdc4529d9f51515ed2ac4b5b3b5
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4985322"
---
# <a name="cash-discounts"></a>Kassarabatter

[!include [banner](../includes/banner.md)]

Kassarabatter ställs in och delas för Leverantörsreskontra och Kundreskontra.  Den tillgängliga kassarabatten kan definieras på kundfakturan eller leverantörsfakturan och dras av om fakturan betalas innan kassarabattsdatumet har förfallit. 

## <a name="cash-discounts"></a>Kassarabatter

Kassarabatter för både kunder eller leverantörer kan skapas på sidan Kassarabatter. Du kan också definiera, genom att använda fältet Nästa rabattkod, en serie kassarabatter som följer efter varandra när tidigare kassarabattdatum förfaller. Mer information finns i ”Exempel: Serie med kassarabatter” senare i det här avsnittet. Om fakturan, kredittransaktionen (antingen en betalning eller en kreditfaktura) eller båda anges i en annan valuta än redovisningsvalutan för den juridiska personen beräknas kassarabatten med hjälp av valutakursen för datumet för betalningen eller kreditfakturan. Om faktura- och kreditdokumentet anges i olika juridiska personer, och om redovisningsvalutorna förde juridiska personerna skiljer sig, hämtas valutakursen från den juridiska personen på fakturan, från datumet för kreditdokumentet. Mer information finns i ”Exempel: Valutakurser för kassarabatter” senare i det här avsnittet.

## <a name="defaulting-order-of-cash-discount-main-account"></a>Ange standardordning för kassarabatthuvudkontot

Om en faktura betalas i tid för en kassarabatt bokförs rabatten automatiskt på ett huvudkonto för kassarabatter enligt följande standardprioritet:
1.  Huvudkontot som angetts i fältet Alternativt kassarabattskonto på sidan Kvitta öppna transaktioner för kunden eller på sidan Kvitta öppna transaktioner.
2.  Huvudkontot som angetts i fältet Kundkassarabatt eller fältet Leverantörskassarabatt i redovisningsbokföringsgruppen som är tilldelad till momskoden på fakturan. Ställ in redovisningsbokföringsgrupper på sidan för redovisningsbokföringsgrupper och tilldela dem till momskoder på sidan Momskoder.
3.  Huvudredovisningskontot på sidan Kassarabatter i fältet Huvudkonto för kundrabatter eller fältet Huvudkonto för leverantörsrabatter för kassarabattkoden på den kvittade fakturan.
4.  Huvudkontot för kassarabatter så som detta definierats på sidan Konton för automatiska transaktioner.

## <a name="example-series-of-cash-discounts"></a> Exempel: Serie med kassarabatter
Ställ in tre kassarabattkoder enligt följande:
-   Kod 5D10% – En kassarabatt på 10 % om beloppet betalas inom 5 dagar.
-   Kod 10D5% – En kassarabatt på 5 % om beloppet betalas inom 10 dagar.
-   Kod 14D2% – En kassarabatt på 2 % om beloppet betalas inom 14 dagar.

I fältet Nästa rabattkod:
-   Välj 10D5% för koden 5D10%.
-   Välj 14D2% för koden 10D5%.
-   För koden 14D2% låter du fältet Nästa rabattkod vara tomt.

De tre kassarabatterna följer efter varandra allteftersom betalningsdatumet passerar det föregående kassarabattdatumet på fakturan. Endast en kassarabatt beviljas när fakturan betalats, baserat på vilket kassarabattdatum som följer i serien med kassarabatter.

## <a name="example-exchange-rates-for-cash-discounts"></a> Exempel: Valutakurser för kassarabatter
Din juridisk persons redovisningsvaluta är EUR och följande valutakurser anges för USD:
-   1 februari = 110
-   1 mars = 80

En faktura på 1000 USD med villkor för kassarabatt på 20D2% bokförs den 15 februari. Fakturans belopp i redovisningsvalutan är 1 100 EUR. En betalning på 980 USD kvittas mot fakturan den 1 mars. Kassarabattbeloppet är 20 USD. Redovisningsvalutabeloppet för betalningen är 784 EUR. Redovisningsvalutabeloppet för kassarabatten beräknas med hjälp av valutakursen för den 1 mars 1: 20 \* 80 / 100 = 16 EUR.

> [!NOTE]
> Om alternativet Beräkna kassarabatter för delbetalningar har valts på sidan Parametrar för kundreskontra eller sidan Parametrar för leverantörsreskontra används valutakursen som gäller på datumet för respektive delbetalning. 

