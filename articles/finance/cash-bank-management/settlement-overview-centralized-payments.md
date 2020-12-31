---
title: Kvittningsöversikt för centraliserade betalningar
description: Det här avsnittet beskriver kvittning för centraliserade betalningar med Microsoft Dynamics 365 Finance.
author: abruer
manager: AnnBe
ms.date: 08/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustOpenTrans
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 222414
ms.assetid: 610f6858-0f37-4d0f-8c68-bab5a971ef4a
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ea661441c6c810d144d423b054c1bef058cdd9d6
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4447996"
---
# <a name="settlement-overview-for-centralized-payments"></a>Kvittningsöversikt för centraliserade betalningar

[!include [banner](../includes/banner.md)]

Organisationer som omfattar flera juridiska personer kan skapa och hantera betalningar genom att använda en enda juridisk person som hanterar alla betalningar. Detta undanröjer behovet av att registrera samma transaktion i flera juridiska personer, och man sparar tid genom att betalningsförslagsprocessen, kvittningsprocessen, redigeringen av öppna och stängda transaktioner för centraliserade betalningar förenklas. 

När en kund- eller leverantörsbetalning registreras för en juridisk person och kvittas mot en faktura som registrerats för en annan juridisk person, kommer relevant kvittning, förfaller till- och förfaller från-transaktioner att skapas automatiskt för respektive juridisk person. En kvittningspost skapas för respektive kombination av faktura och betalning i transaktionen. Varje kvittningspost tilldelas ett nytt verifikationsnummer, baserat på den verifikationsnummersekvens för betalning som angetts på sidan **Parametrar för kundreskontra** för kunder och på sidan **Parametrar för leverantörsreskontra** för leverantörer. 

Om ytterligare kvittningsposter skapas för kassarabatter, omräkningar i utländsk valuta, öresskillnader, över- eller underbetalningar, erhåller de det senare datumet för betalnings- eller fakturatransaktionen. Om kvittningen sker efter det att betalningen har bokförts, använder kvittningsposterna det bokföringsdatum för kvittning som angetts på sidan **Kvitta öppna transaktioner**.

## <a name="posting-types-transaction-types-and-default-descriptions"></a>Bokföringstyper, transaktionstyper och standardbeskrivningar

För koncerninterna transaktioner för kvittningsverifikationer används transaktionstyperna koncernintern kvittningsbokföringstyp, koncernintern kundkvittning och koncernintern leverantörskvittning. Du kan ange information för transaktionstypen på sidan **Standardbeskrivningar**. 

Följande transaktionstyper är tillgängliga för användning vid kvittning i enskilda företag och mellan företag:

-   Bostadsområde
-   Kassarabatt
-   Omräkning i utländsk valuta (inkluderar realiserad och orealiserad omräkning i utländsk valuta)
-   Öresdifferens
-   Överbetalning/underbetalning

Du kan även ange standardbeskrivningar för koncerninterna kvittningsverifikationer.

## <a name="currency-exchange-gains-or-losses"></a>Valutakursvinster eller valutakursförluster

Den valutakurs som används för kund- eller leverantörstransaktioner lagras med transaktionen. Realiserade vinster eller förluster rörande valutakurser bokförs i antingen fakturans juridiska person eller i betalningens juridiska person beroende på vilket alternativ som har valts i fältet **Bokför valutakursvinst eller -förlust** på sidan **Koncernintern redovisning** för den juridiska personen för betalningen. I följande exempel används de här valutorna:
-   Redovisningsvaluta för betalning: EUR
-   Redovisningsvaluta för faktura: USD
-   Betalningstransaktionsvaluta: DKK
-   Fakturatransaktionsvaluta: CAD

### <a name="currency-calculations"></a>Valutaberäkningar

När en faktura som har registrerats i juridisk person kvittas med en betalning som har registrerats i en annan juridisk person, konverteras betalningens transaktionsvaluta (DKK) i tre steg:
1.  Konvertering till betalningens redovisningsvaluta (EUR) med valutakurser från betalningens juridiska person.
2.  Konvertering till fakturans redovisningsvaluta (USD).
3.  Konvertering till transaktionens fakturavaluta (CAD) med valutakurser från fakturans juridiska person.

Under konverteringsprocessen används betalningsdatumets valutakurser. Om det resulterande betalningsbeloppet i fakturans transaktionsvaluta (CAD) är lika med fakturabeloppet (CAD), anses fakturan vara fullt betald. 

När sidan **Kvitta öppna transaktioner** öppna från en betalningsjournal där betalningsbeloppet inte angetts, beräknas kvittningsbeloppet baserat på de fakturor som har valts för kvittning på sidan **Kvitta öppna transaktioner**. Kvittningsbeloppet konverteras i tre steg:
1.  Konvertering till fakturans redovisningsvaluta (USD) med valutakurser från fakturans juridiska person per betalningsdatumet.
2.  Konvertering till betalningens redovisningsvaluta (EUR) med valutakurser från fakturans juridiska person per betalningsdatumet.
3.  Konvertering till betalningens transaktionsvaluta (DKK).

Det resulterande betalningsbeloppet överförs till betalningsjournalraden när du stänger sidan **Kvitta öppna transaktioner**.

### <a name="posting-for-gain-or-loss-because-of-different-accounting-currencies"></a>Bokföring av vinst eller förlust till följd av olika redovisningsvalutor

Om det finns en vinst eller en förlust vid valutaväxling kommer denna att bokföras för den juridiska person som angetts för fältet **Bokför valutakursvinst eller -förlust** på sidan **Koncernintern redovisning** för den juridiska personen för betalningen. Vinst- eller förlustbeloppet konverteras till redovisningsvalutan för den juridiska person där vinst- eller förlustbeloppet bokförs, med den växelkurs som definierats för den juridiska personen.

## <a name="cash-discounts"></a>Kassarabatter

Kassarabatter som skapas i samband med kvittningsprocessen mellan företag bokförs i antingen fakturans juridiska person eller i betalningens juridiska person, beroende på vilket alternativ som har valts i fältet **Bokför kassarabatt** på sidan **Koncernintern redovisning** för den juridiska personen för betalningen. En motsvarande kvittningstransaktion skapas i fakturans juridiska person.

## <a name="overpayments-and-underpayments"></a>Överbetalningar och underbetalningar

Toleranser för överbetalning, underbetalning och öresskillnader fastställs baserat på den betalningens juridiska person för överbetalningar samt på fakturans juridiska person för underbetalningar. Redovisningskontot som används bestäms av inställningarna i fältet **Administration av kassarabatt** på sidan **Parametrar för kundreskontra** för kunder, samt i fältet **Administration av kassarabatt** på sidan **Parametrar för leverantörsreskontra** för leverantörer.

-   Om administrationsinställningen för kassarabatt är specificerad (Specific), eller om inställningen inte är specificerad (Unspecific) och den tillämpliga kassarabatten bokförs på en annan juridisk person än överbetalningen, används det automatiska kontot för kassarabatt för konsument, kassarabatt för leverantör eller öresskillnad i redovisningsvaluta. Du kan ange dessa konton på sidan **Konton för automatiska transaktioner**.
-   Om administrationsinställningen för kassarabatt inte är specificerad (Unspecific) och kassarabatten bokförs i samma juridiska person överbetalningen (den juridiska personen förbetalning och faktura är densamma), kommer kontot för kassarabatt att justeras. Om till exempel en faktura på 100,00 med en kassarabatt på 3,00 kvittas med en betalning på 98,00, justeras kassarabattkontot med 1,00. Nettobeloppet för rabatt är 2,00.
-   Om administrationsinställningen för kassarabatt inte är specificerad (Unspecific), kassarabatten bokförs för samma juridiska person som överbetalningen, och överbetalningen eller underbetalningen kvittas med flera fakturor med kassarabatter, justeras kassarabattkontot för den sista fakturan.

Om administrationsinställningen för kassarabatt är ospecificerad (Unspecific) gäller ospecifika regler för betalningskvittning enbart i följande situationer:
-   En överbetalning föreligger.
-   Överbetalningen kvittas mot en eller flera fakturor som har en kassarabatt.
-   Kassarabatten bokförs för samma juridiska person som överbetalningen.

I alla andra situationer bokförs över - eller underbetalningar till det automatiska kontot för kundkassarabatt, leverantörkassarabatt eller öresdifferens i redovisningsvaluta.

## <a name="sales-tax"></a>Moms
Momstransaktioner ligger kvar i den juridiska person där de ursprungligen bokförts. 

Om moms bokförts för en förskottsbetalning, återför kvittningen mellan företag momsen från förskottsbetalningen till förskottsbetalningens juridiska person. Momsen hos fakturans juridiska person blir kvar i fakturans juridiska person.

## <a name="financial-dimensions"></a>Ekonomiska dimensioner
För kundbetalningar använder förfaller till- och förfaller från-transaktioner i betalningens juridiska person ekonomiska dimensioner som har angetts för kundreskontrans samlingskonto från den betalning som kvittas. I fakturans juridiska person använder förfaller till- och förfaller från-transaktioner de ekonomiska dimensioner som har angetts för kundreskontrans samlingskonto från den faktura som kvittas. 

För leverantörsbetalningar använder förfaller till- och förfaller från-transaktioner i betalningens juridiska person de ekonomiska dimensioner som har angetts för leverantörsreskontrans samlingskonto från den betalning som kvittas. I fakturans juridiska person använder förfaller till- och förfaller från-transaktioner de ekonomiska dimensioner som har angetts för leverantörsreskontrans samlingskonto från den faktura som kvittas.

## <a name="withholding-tax"></a>Källskatt
Leverantörskontot som är associerat till fakturan används för att avgöra om källskatt ska beräknas. Om källskatt gäller beräknas denna i den juridiska person som är associerad med fakturan. Om de juridiska personer använder olika valutor, används valutakursen från den juridiska person som är kopplad till fakturan.
