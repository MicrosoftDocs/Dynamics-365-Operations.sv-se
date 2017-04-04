---
title: "Omvärdering i utländsk valuta för huvudbok"
description: "Det här avsnittet innehåller en översikt över följande för utländsk valuta omvärdering redovisningsprocessen - installationen kör processen för processen och hur du återför omvärderingstransaktioner, om det behövs."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: CurrencyLedgerGainLossAccount
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 62153
ms.assetid: 842e8561-560f-4cc6-8668-70cca60b1ba3
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ef99caf4570969d2b920cec8b53669ce2094965
ms.openlocfilehash: 5d6d13fe44eef7766b4dcaf274c3522bce3da816
ms.lasthandoff: 03/31/2017


---

# <a name="foreign-currency-revaluation-for-general-ledger"></a>Omvärdering i utländsk valuta för huvudbok

Det här avsnittet innehåller en översikt över följande för utländsk valuta omvärdering redovisningsprocessen - installationen kör processen för processen och hur du återför omvärderingstransaktioner, om det behövs. 

Som en del av ett periodslut kräver redovisningspraxis att redovisningskonton i utländska valutor omvärderas med hjälp av olika valutakurstyper (aktuella, tidigare, genomsnittliga osv.). Till exempel kräver en redovisningspraxis att tillgångar och skulder ska omvärderas efter aktuell valutakurs, anläggningstillgångar efter den historiska valutakursen, och resultatkonton efter månatligt genomsnitt. Redovisningomräkningen för utländsk valuta kan användas för att omvärdera balansräkningen och resultatkontona. 

> [!NOTE]
> Omvärdering i utländsk valuta är också tillgängliga i Kundreskontra (AR) och Leverantörsreskontra (AP). Om du använder dessa moduler ska utestående transaktioner omvärderas med hjälp av omvärdering i utländsk valuta i dessa moduler. AR- och AP-omräkning i utländsk valuta skapar en redovisningspost i redovisningen för att återspegla den orealiserade vinsten eller förlusten, och ser till att redovisningsjournalerna kan stämmas av. Eftersom AR- och AP-omräkning i utländsk valuta skapar redovisningsposter i redovisningen, bör huvudkontona för kundreskontra och leverantörsreskontra exkluderas från redovisningomräkning i utländsk valuta. 

När du kör omvärderingsprocessen kommer saldot i varje huvudkonto som bokförs i utländsk valuta att omvärderas. Orealiserade vinst- eller förlusttransaktioner som skapas under omvärderingsprocessen genereras av systemet. Två transaktioner kan skapas för redovisningsvalutan och en sekund för rapporteringsvalutan, om det är relevant. I redovisningen för varje att bokföra Orealiserad vinst eller förlust och huvudkontot som omvärderas.

## <a name="prepare-to-run-foreign-currency-revaluation"></a>Förbereda en körning av omvärdering i utländsk valuta
Innan du kan köra omvärderingsprocessen måste följande inställningar göras.

-   På sidan **Main account**:
-   Om huvudkontot ska omvärderas i redovisningen, välj då **Foreign currency revaluation**. Om huvudkontot inte ska omvärderas (till exempel för kundreskontra och leverantörsreskontra, om dessa omvärderats i redovisningsjournalerna), rensa då detta alternativ.
-   Om huvudkontot valts för omvärdering, ange då **valutakurstyp**. Denna valutakurstyp kommer att användas för omvärdering av huvudkontot. Ett separat fält, **Financial reporting exchange rate type**, finns tillgängligt för ekonomirapporteringen. De två fälten hålls inte synkroniserade, vilket gör att olika valutakurstyper kan användas för omvärdering och ekonomisk rapportering.

-   På sidan **Ledger**:
-   Ange **valutakurstyp**. Om valutakurstypen inte definieras på huvudkontot, kommer denna valutakurstyp att användas i samband med omräkning i utländsk valuta.
-   Ange konton för realiserad vinst, realiserad förlust, orealiserad vinst och orealiserad förlust för valutaomvärdering. Kontona för realiserad vinst och realiserad förlust används för kvittade kundreskontra- och leverantörsreskontratransaktioner, och kontona för orealiserad vinst och orealiserad förlust används för öppna transaktioner samt huvudkonton för redovisning.

-   På sidan **Currency revaluation accounts**:
-   Välj olika konton för omvärdering valuta för respektive valuta och företag. Om inga konton har definierats används kontona från sidan **Redovisning**.

## <a name="process-foreign-currency-revaluation"></a>Bearbeta en omvärdering i utländsk valuta
Efter slutförda inställningar, använd sidan **Foreign currency revaluation** för att utvärdera beloppen i huvudsidorna. Du kan köra processen i realtid eller schemalägga den för att köra med en batch. 

Sidan **Foreign currency revaluation** visar historiken för respektive omvärderingsprocess, inklusive när processen kördes, vilka kriterier som angavs, en länk till den verifikation som skapades för omvärderingen, samt en post om en tidigare omvärdering har återförts. Välj knappen **Foreign currency revaluation** om du vill köra omvärderingsprocessen. 

Värdena **From date** och **To date** anger datumintervallet för beräkningen av den utländska valutabalans som ska omvärderas. När du omvärderar vinst- och förlustkonton, omvärderas summan av alla transaktioner som förekommer inom datumintervallet. När du omvärderar balansräkningskonton, ignoreras från-datum. Istället bestäms saldot som ska omvärderas genom att gå från början av räkenskapsåret fram till slutdatum. 

Den **Kursdatum** kan användas för att definiera det datum som valutakursen som standard ska gälla. Exempelvis kan du omvärdera saldona mellan datum intervallet för januari 1 till 31 januari, men valutakursen som definierats för den 1 februari. 

Välj vilka huvudkonton som ska omvärderas: Alla, Balansräkning eller Vinst och förlust. Endast huvudkonton som markerats för omvärdering (på kontot huvudsida) att omvärderas. Om du vill begränsa intervallet för huvudkonton ytterligare använda posterna **ta** fliken för att ange ett intervall med huvudkonton eller enskilda huvudkonton. 

Du kan köra omvärderas för en eller flera juridiska personer. Sökningen visas endast de juridiska personer som har tillgång till. Välj de juridiska personerna som du vill köra omvärderas. 

Omvärderingen kan köras för en eller flera utländska valutor. Sökfunktionen tas alla valutor som har bokförts inom det angivna datumintervallet relevanta för typ av huvudkonto (balansräkningen eller resultaträkningen) för de juridiska personer som valt att omvärdera. Redovisningsvalutan ska tas med i listan men inget omvärderas överför redovisningsvalutan. 

Ange **förhandsgranskning innan du bokför** till **Ja** om du vill granska resultatet av omvärdering i redovisningen. Förhandsgranskningen i allmänhet redovisning skiljer sig från simuleringen av omvärdering i utländsk valuta på P.A. och AP. Simuleringen AR och AP är en rapport, men redovisning har en förhandsgranskning som kan bokföras, utan att behöva raderingen omvärdering igen. Resultatet av förhandsgranskningen kan exporteras till Microsoft Excel, om du vill behålla historiken för hur beloppen beräknades. Du kan inte använda batchbearbetning om du vill granska resultatet av omvärderingen. Från förhandsgranskningen har användaren möjlighet att bokföra resultaten för juridiska personerna via knappen **Post**. Om det finns ett problem med resultaten för en juridisk person, har användaren också möjlighet att bokföra en deluppsättning av de juridiska personerna med hjälp av knappen **Select legal entities to post**. 

När processen omvärdering i utländsk valuta är klar skapas en post om du vill visa historik för varje gång du kör.  En separat post skapas för varje juridisk person och bokföringsskikt.

## <a name="calculate-unrealized-gainloss"></a>Beräkna orealiserad vinst/förlust
Orealiserade vinst-/förlusttransaktioner skapas på olika sätt mellan redovisningomvärderingen och omvärderingsprocessen för kund- respektive leverantörsreskonto. I kund- och leverantörsreskontra återförs den föregående omvärderingen helt (förutsatt att transaktionen ännu inte har kvittats), och en ny omvärderingstransaktion skapas för den orealiserade vinsten/förlusten baserat på den nya valutakursen. Detta sker eftersom vi omvärderar varje enskild transaktion i kund- och leverantörsreskontra. Föregående omvärderingen återförs inte i redovisningen. I stället skapas en transaktion för listan mellan saldot för huvudkontot, inklusive eventuella tidigare omvärderingsbelopp och det nya värdet utifrån växelkursen för datumet tariff. 

**Till exempel** finns följande saldona för 110110 för huvudkonto.

|            |                    |                        |                       |
|------------|--------------------|------------------------|-----------------------|
| **Datum**   | **Redovisningskonto** | **Transaktionsbelopp** | **Redovisningsbelopp** |
| 20 januari | 110110 (kassa)      | 500 EUR (debet)        | 1000 USD (debet)      |

Huvudkontot omvärderas 31 januari.  Orealiserad vinst/förlust beräknas på följande sätt.

|                                             |                                            |                                  |                                    |                             |
|---------------------------------------------|--------------------------------------------|----------------------------------|------------------------------------|-----------------------------|
| **Aktuell balans i transaktionsvaluta** | **Aktuell balans i redovisningsvaluta** | **Valutakurs vid omvärdering** | **Nytt belopp för redovisningsvaluta** | **Orealiserad vinst/förlust**    |
| 500 EUR                                     | 1 000 USD                                   | 166.6667                         | 833,33 EUR (500 x 1,666667)        | 166,67 förlust (833,33 – 1 000) |

Följande redovisningspost skapas.

|            |                          |           |            |
|------------|--------------------------|-----------|------------|
| **Datum**   | **Redovisningskonto**       | **Debet** | **Kredit** |
| 31 januari | 110110 (kassa)            |           | 166.67     |
| 31 januari | 801400 (Orealiserad förlust) | 166.67    |            |

Inga nya transaktioner bokförs för månaden februari.  Huvudkontot omvärderas den 28 februari.

|                                             |                                            |                                  |                                    |                             |
|---------------------------------------------|--------------------------------------------|----------------------------------|------------------------------------|-----------------------------|
| **Aktuell balans i transaktionsvaluta** | **Aktuell balans i redovisningsvaluta** | **Valutakurs vid omvärdering** | **Nytt belopp för redovisningsvaluta** | **Orealiserad vinst/förlust**    |
| 500 EUR                                     | 833,33 USD (1 000 - 166,67)                 | 250.0000                         | 1 250 USD (500 x 2,5)               | 416,67 vinst (1 250 – 833,33) |

Följande redovisningspost skapas.

|             |                          |           |            |
|-------------|--------------------------|-----------|------------|
| **Datum**    | **Redovisningskonto**       | **Debet** | **Kredit** |
| 28 februari | 110110 (kassa)            | 416.67    |            |
| 28 februari | 801600 (Orealiserad vinst) |           | 416.67     |

## <a name="reverse-foreign-currency-revaluation"></a>Återför omräkning i utländsk valuta
Om du måste återföra omvärderingtransaktionen, välj knappen **Reverse transaction** på sidan **Foreign currency revaluation**. En historisk ny post om omräkning i utländsk valuta skapas för att bibehålla den historiska redovisningsspårningen för när omvärdering genomfördes eller återfördes. 

Du kan ångra resultatet för omvärderingen av datumordning, men du kanske även återföra en nyare omvärdering så korrekta saldon för varje omvärderade huvudkonto. Återföringarna beror på inaktuell ordern inte går att kontrollera vilka huvudkonton omvärderas och frekvensen för när omvärderas. Till exempel väljer en organisation att omvärdera deras huvudsakliga kassakonton kvartalsvis, men inga huvudkonton månadsvis.


