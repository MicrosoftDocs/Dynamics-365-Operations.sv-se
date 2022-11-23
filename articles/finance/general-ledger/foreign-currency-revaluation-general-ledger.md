---
title: Omvärdering i utländsk valuta för huvudbok
description: 'Den här artikeln innehåller en översikt över följande för redovisningsomräkningsprocessen i utländsk valuta: ställa in, köra processen, beräkningen för processen, samt hur du återför omvärderingtransaktionerna vid behov.'
author: kweekley
ms.date: 11/15/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CurrencyLedgerGainLossAccount
audience: Application User
ms.reviewer: twheeloc
ms.custom: 62153
ms.assetid: 842e8561-560f-4cc6-8668-70cca60b1ba3
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 96ae50e339c63687a4c8114d3c965123fd5e37ab
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/16/2022
ms.locfileid: "9779999"
---
# <a name="foreign-currency-revaluation-for-general-ledger"></a>Omvärdering i utländsk valuta för huvudbok

[!include [banner](../includes/banner.md)]

Den här artikeln innehåller en översikt över följande för redovisningsomräkningsprocessen i utländsk valuta: ställa in, köra processen, beräkningen för processen, samt hur du återför omvärderingtransaktionerna vid behov. 

Som en del av ett periodslut kräver redovisningspraxis att redovisningskonton i utländska valutor omvärderas med hjälp av olika valutakurstyper (aktuella, tidigare, genomsnittliga osv.). Till exempel kräver en redovisningspraxis att tillgångar och skulder ska omvärderas efter aktuell valutakurs, anläggningstillgångar efter den historiska valutakursen, och resultatkonton efter månatligt genomsnitt. Redovisningomräkningen för utländsk valuta kan användas för att omvärdera balansräkningen och resultatkontona. 

> [!NOTE]
> Omräkning i utländsk valuta finns även för Kundreskontra och Leverantörsreskontra. Om du använder dessa moduler ska utestående transaktioner omvärderas med hjälp av omvärdering i utländsk valuta i dessa moduler. AR- och AP-omräkning i utländsk valuta skapar en redovisningspost i redovisningen för att återspegla den orealiserade vinsten eller förlusten, och ser till att redovisningsjournalerna kan stämmas av. Eftersom AR- och AP-omräkning i utländsk valuta skapar redovisningsposter i redovisningen, bör huvudkontona för kundreskontra och leverantörsreskontra exkluderas från redovisningomräkning i utländsk valuta. 

När du kör ombedömningsprocessen kommer saldot i varje huvudkonto som bokförs i utländsk valuta att omvärderas. Orealiserade vinst- eller förlusttransaktioner som skapas under ombedömningsprocessen genereras av systemet. Två transaktioner kan komma att skapas, en för redovisningsvalutan och en andra för rapporteringsvalutan, vid behov. Varje redovisningspost bokför till orealiserad vinst eller förlust samt det huvudkonto som omvärderas.

## <a name="prepare-to-run-foreign-currency-revaluation"></a>Förbereda en körning av omvärdering i utländsk valuta
Innan du kan köra ombedömningsprocessen måste följande inställningar göras.

På sidan **Huvudkonto**:
 - Om huvudkontot ska omvärderas i redovisningen, välj då **Omräkning i utländsk valuta**. Om huvudkontot inte ska omvärderas (till exempel för kundreskontra och leverantörsreskontra, om dessa omvärderats i redovisningsjournalerna), rensa då detta alternativ.
 - Om huvudkontot valts för omvärdering, ange då **valutakurstyp**. Denna valutakurstyp kommer att användas för omvärdering av huvudkontot. Ett separat fält, **Valutakurstyp för ekonomisk rapportering**, finns tillgängligt för ekonomirapporteringen. De två fälten hålls inte synkroniserade, vilket gör att olika valutakurstyper kan användas för omvärdering och ekonomisk rapportering.

På sidan **Huvudbok**:
 - Ange **valutakurstyp**. Om valutakurstypen inte definieras på huvudkontot, kommer denna valutakurstyp att användas i samband med omräkning i utländsk valuta.
 - Ange konton för realiserad vinst, realiserad förlust, orealiserad vinst och orealiserad förlust för valutaomvärdering. Kontona för realiserad vinst och realiserad förlust används för kvittade kundreskontra- och leverantörsreskontratransaktioner, och kontona för orealiserad vinst och orealiserad förlust används för öppna transaktioner samt huvudkonton för redovisning.

På sidan **Valutaombedömningskonton**:
 - Välj olika konton för omvärdering valuta för respektive valuta och företag. Om inga konton har definierats används kontona från sidan **Redovisning**.

## <a name="process-foreign-currency-revaluation"></a>Bearbeta en omvärdering i utländsk valuta
Efter slutförda inställningar, använd sidan **Omräkning i utländsk valuta** för att utvärdera beloppen i huvudsidorna. Du kan köra processen i realtid eller schemalägga den för att köra med en batch. 

Sidan **Omräkning i utländsk valuta** visar historiken för respektive ombedömningsprocess, inklusive när processen kördes, vilka kriterier som angavs, en länk till den verifikation som skapades för omvärderingen, samt en post om en tidigare omvärdering har återförts. Välj knappen **Omräkning i utländsk valuta** om du vill köra ombedömningsprocessen. 

Värdena **Från datum** och **Till datum** anger datumintervallet för beräkningen av den utländska valutabalans som ska omvärderas. När du omvärderar vinst- och förlustkonton, omvärderas summan av alla transaktioner som förekommer inom datumintervallet. När du omvärderar balansräkningskonton, ignoreras **från-datum**. Istället bestäms saldot som ska omvärderas genom att gå från början av räkenskapsåret fram till **till-datum**. 

Det **Kursdatum** som kan användas för att definiera det datum då valutakursen ska återställas till standardvärdet. Exempelvis kan du omvärdera saldona mellan datumintervallet 1 januari till 31 januari men använda valutakursen som definierats för den 1 februari. 

Välj vilka huvudkonton som ska omvärderas: Alla, Balansräkning eller Vinst och förlust. Endast huvudkonton som markerats för omvärdering (på sidan för **huvudkonto**) kommer att omvärderas. Om du vill begränsa intervallet för huvudkonton ytterligare, använd fliken **Poster att inkludera** för att ange ett intervall med huvudkonton eller enskilda huvudkonton. 

Ombedömningsprocessen kan köras för en eller flera juridiska personer. Sökningen visar endast de juridiska personer som du har tillgång till. Välj den juridiska person som du vill köra bedömningsprocessen för. 

Omvärderingen kan köras för en eller flera utländska valutor. Sökningen omfattar alla valutor som har bokförts inom det angivna datumintervallet för typen av huvudkonto (balansräkning eller resultaträkning) för de juridiska personer som du har valt att omvärdera. Redovisningsvalutan tas med i listan, men inget omvärderas om redovisningsvalutan har valts. 

Ange **Förhandsgranska före bokföring** till **Ja** om du vill granska resultatet av omvärderingen av redovisningen. Förhandsgranskningen av redovisningen skiljer sig från simuleringen av omräkningen i utländsk valuta för kund- och leverantörsreskontra. Kund- och leverantörsreskontrasimuleringen är en rapport, men redovisning har en förhandsgranskning som kan bokföras utan att ombedömningsprocessen behöver köras på nytt. Resultatet av förhandsgranskningen kan exporteras till Microsoft Excel om du vill behålla historiken för hur beloppen beräknades. Du kan inte använda batchbearbetning om du vill granska resultatet av omvärderingen. Från förhandsgranskningen har användaren möjlighet att bokföra resultaten för juridiska personerna via knappen **Post**. Om det finns ett problem med resultaten för en juridisk person, har användaren också möjlighet att bokföra en deluppsättning av de juridiska personerna med hjälp av knappen **Välj valda juridiska personer att bokföra**.

Om du vill utesluta justeringar som har lagts upp med hjälp av **Justeringsjournal för rapporteringsvaluta** från omvärderingsprocessen, ange **Exkludera justeringar av rapporteringsvaluta** till **Ja**. Som standard inkluderas valutajusteringar i omvärderingen. 

När processen för omräkning i utländsk valuta är klar skapas en post där du kan spåra historiken för respektive körning. En separat post skapas för varje juridisk person och bokföringsskikt.

## <a name="calculate-unrealized-gainloss"></a>Beräkna orealiserad vinst/förlust
Orealiserade vinst-/förlusttransaktioner skapas på olika sätt mellan redovisningomvärderingen och ombedömningsprocessen för kund- respektive leverantörsreskonto. I kund- och leverantörsreskontra återförs den föregående omvärderingen helt (förutsatt att transaktionen ännu inte har kvittats), och en ny ombedömningstransaktion skapas för den orealiserade vinsten/förlusten baserat på den nya valutakursen. Detta sker eftersom vi omvärderar varje enskild transaktion i kund- och leverantörsreskontra. Föregående omvärdering återförs inte i redovisningen. I stället skapas en transaktion för deltat mellan saldot för huvudkontot, inklusive eventuella föregående ombedömningsbelopp, och det nya värdet baserat på valutakursen för kursdatumet. 

**Exempel** Följande saldon finns för huvudkonto 110110.

| Datum   | Redovisningskonto| Transaktionsbelopp | Redovisningsbelopp |
|------------|--------------------|------------------------|-----------------------|
| 20 januari | 110110 (kassa)      | 500 EUR (debet)        | 1000 USD (debet)      |

Huvudkontot omvärderas den 31 januari.  Orealiserad vinst/förlust beräknas på följande sätt.

| Aktuell balans i transaktionsvaluta | Aktuell balans i redovisningsvaluta | Valutakurs vid omvärdering | Nytt belopp för redovisningsvaluta | Orealiserad vinst/förlust    |
|--------------------|---------------------------|----------------------------------|------------------------------------|-----------------------------|
| 500 EUR            | 1 000 USD                  | 166.6667                         | 833,33 USD (500 x 1,666667)        | 166,67 förlust (833,33 – 1 000) |

Följande redovisningspost skapas.

| Datum   | Redovisningskonto       | Debet | Kredit |
|------------|--------------------------|-----------|------------|
| 31 januari | 110110 (kassa)            |           | 166.67     |
| 31 januari | 801400 (Orealiserad förlust) | 166.67    |            |

Inga nya transaktioner bokförs för månaden februari.  Huvudkontot omvärderas den 28 februari.

| Aktuell balans i transaktionsvaluta | Aktuell balans i redovisningsvaluta | Valutakurs vid omvärdering | Nytt belopp för redovisningsvaluta | Orealiserad vinst/förlust    |
|---------------------------------------|-----------------------------------|-------------------------------|--------------------|-----------------------------|
| 500 EUR                 | 833,33 USD (1 000 – 166,67)       | 250.0000              | 1 250 USD (500 x 2,5)               | 416,67 vinst (1 250 – 833,33) |

Följande redovisningspost skapas.

| Datum    | Redovisningskonto       | Debet | Kredit |
|-------------|--------------------------|-----------|------------|
| 28 februari | 110110 (kassa)            | 416.67    |            |
| 28 februari | 801600 (Orealiserad vinst) |           | 416.67     |

## <a name="reverse-foreign-currency-revaluation"></a>Återför omräkning i utländsk valuta
Om du måste återföra omvärderingtransaktionen, välj knappen **Återför transaktion** på sidan **Omräkning i utländsk valuta**. En historisk ny post om omräkning i utländsk valuta skapas för att bibehålla den historiska redovisningsspårningen för när omvärdering genomfördes eller återfördes. 

Du kan ångra resultatet för omvärderingen av datumordning, men du kanske även måste återföra en nyare omvärdering för att säkerställa korrekta saldon för varje omvärderade huvudkonto. Återföringarna kan ske oberoende av datumordning, detta eftersom det inte går att kontrollera vilka huvudkonton som omvärderas och frekvensen för när de omvärderas. En organisation kan exempelvis välja att omvärdera sina huvudsakliga kassakonton kvartalsvis, men alla andra huvudkonton månadsvis.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
