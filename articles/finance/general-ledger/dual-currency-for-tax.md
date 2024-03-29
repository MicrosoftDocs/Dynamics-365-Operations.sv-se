---
title: Stöd för moms på dubbel valuta
description: I den här artikeln beskrivs hur du utökar redovisningsfunktionen för dubbla valutor i momsdomänen och vilken inverkan som momsen ska beräknas och bokföras
author: EricWang
ms.date: 12/11/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: kfend
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2020-01-14
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: 13d70d964a83c2efba090244d549bdb38ad25af2
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8909052"
---
# <a name="dual-currency-support-for-sales-tax"></a>Stöd för moms på dubbel valuta
[!include [banner](../includes/banner.md)]

I den här artikeln beskrivs hur du utökar redovisning av dubbla valutor för moms och vilken inverkan för beräkning, bokföring och kvittningar av moms.

Funktionen med dubbla valutor för Dynamics 365 Finance infördes i version 8.1 (oktober 2018). Den ändrar hur redovisningstransaktioner i rapporteringsvalutan beräknas.

I tidigare versioner konverterades transaktionerna till rapportvalutan i följande ordning: 

- Transaktionssumman har beräknats i transaktionsvalutan > transaktionsbelopp konverterades till redovisningsvalutan > redovisningsvalutabeloppet har konverterats till rapportvalutan

När funktionen för dubbla valutor har aktiverats konverterades transaktionerna till rapportvalutan i följande ordning:

- Transaktionsvalutabelopp > Rapporteringsvalutabelopp

Mer information om dubbla valutor finns i [dubbla valutor](dual-currency.md).

Som en följd av stöd för dubbla valutor finns två nya funktioner i funktionshantering: 

- Momskonvertering (nyhet i version 10.0.13)
- Ange finansiella dimensioner i kontona för realiserade valutajusteringsresultat för momsavräkning (ny i version 10.0.17)

Stöd till dubbel valuta för moms garanterar att moms beräknas korrekt i momsvalutan och att saldot för momskvittningen beräknas korrekt i både redovisningsvalutan och rapporteringsvalutan.

## <a name="sales-tax-conversion"></a>Momskonvertering

Parametern **Momskonvertering** innehåller två alternativ för konvertering av momsbelopp från transaktionsvaluta till momsvaluta. 

- Redovisningsvaluta: Sökvägen är "Belopp i transaktionsvaluta> Belopp i redovisningsvaluta> Belopp i momsvaluta". Redovisningsvalutans valutakurstyp (konfigureras i redovisningsinställningarna) kommer att användas för valutakonverteringen.
- Rapporteringsvaluta: Sökvägen är "Belopp i transaktionsvaluta> Belopp i rapporteringsvaluta> Belopp i momsvaluta". Rapporteringsvalutans valutakurstyp (konfigureras i redovisningsinställningarna) kommer att användas för valutakonverteringen.

### <a name="example"></a>Exempel

Ett enkelt exempel på att visa den här funktionen är:

Inställning av valuta för redovisning och moms

| Transaktionsvaluta | Redovisningsvaluta | Rapporteringsvaluta | Skattevaluta |
| -------------------- | ------------------- | ------------------ | ------------ |
| Euro                  | USD                 | GBP                | GBP          |

Valutakurs

| Från valuta | Till valuta | Faktor | Valutakurs |
| ------------- | ----------- | ------ | ------------- |
| Euro           | USD         | 1      | 1.11          |
| Euro           | GBP         | 1      | 0.83          |
| USD           | GBP         | 1      | 0.75          |

Beräkning av momsbelopp i olika parameteralternativ

Momsbelopp = 100 EUR

| Konverteringsparametrar för moms | Transaktionsvaluta (EUR) | Redovisningsvaluta (USD) | Rapporteringsvaluta (GBP) | Skattevaluta (GBP) |
| ------------------------------- | -------------------------- | ------------------------- | ------------------------ | ------------------ |
| Redovisningsvaluta             | 100                        | 111                       | 83                       | **83.25**          |
| Rapporteringsvaluta              | 100                        | 111                       | 83                       | **83**             |

Den här parametern kan konfigureras utifrån skattemyndighetens behov.


### <a name="upgrade-consideration"></a>Uppgradera beaktanden

Den här funktionen kan endast användas för nya transaktioner. För att momstransaktionen redan har sparats i TAXTRANS-registret men ännu inte kvittats, kommer systemet inte att räkna om momsbeloppet i momsvaluta eftersom valutakursen vid tidpunkten för bokföringsskatt redan saknas.

För att förhindra föregående scenario rekommenderar vi att du ändrar detta parameter värde i en ny (ren) momskvittningsperiod som inte innehåller några oreglerade momstransaktioner. Om du vill ändra detta värde i mitten av en momskvittningsperiod kör du programmet "kvitta och bokför moms" för aktuell momskvittningsperiod innan du ändrar detta parametervärde.

Den här funktionen lägger till redovisningsposter som klargör vinster och förluster från valutautbyten. Inmatningarna görs i de realiserade vinst- och förlustkontona för valutajusteringar när omvärdering görs vid momskvittning. Mer information finns i avsnittet [Automatiskt saldo för momskvittning i rapporteringsvaluta](#tax-settlement-auto-balance-in-reporting-currency) senare i den här artikeln.

> [!NOTE]
> Vid kvittningen tas informationen för ekonomiska dimensioner från momskonton, som är balansräkningskonton, och anges i valutajusteringsvinst- och förlustkonton, som är resultatkonton. Eftersom restriktioner för värdet av ekonomiska dimensioner skiljer sig mellan balansräkningskonton och resultatkonton, kan ett fel inträffa under processen Kvitta och bokföra moms. För att undvika att behöva ändra kontostrukturer kan du aktivera funktionen "Fyll i ekonomiska dimensioner till realiserade valutajusteringskonton för vinst/förlust för momskvittning". Den här funktionen tvingar ekonomiska dimensioner att använda valutajusteringskonton för vinst/förlust. 

## <a name="track-reporting-currency-tax-amount"></a>Spåra momsbelopp i rapporteringsvaluta

Tre nya fält lades till i momsrelaterade register för spårning av belopp i rapporteringsvalutan. Dessa fält ligger i tabellerna TAXUNCOMMITTED och TAXTRANS:

- TaxAmountRep: momsbelopp i rapporteringsvaluta
- TaxBaseAmountRep: basbelopp i rapporteringsvaluta
- TaxInCostPriceRep: ej avdragsgillt belopp i rapporteringsvaluta

För moms som endast har sparats i registret TAXUNCOMMITTED men inte bokförts ännu kommer systemet att omberäkna momsbeloppet i rapportvalutan vid tidpunkten för bokföring och sparande i TAXTRANS-registret.

Den här versionen kommer inte att innehålla ändringar av rapporter och formulär som visar momsbeloppet i rapportvalutan. Ändringar i rapporter och formulär kommer att levereras i framtida versioner.



## <a name="tax-settlement-auto-balance-in-reporting-currency"></a>Automatiskt saldo för momskvittning i rapporteringsvaluta

Om momskvittningen inte är balanserad i rapportvalutan av en viss anledning, till exempel om momskonverteringssökvägen är "Redovisningsvaluta", eller om valutakursändringen har ändrats i en enskild momskvittningsperiod, så kommer systemet automatiskt att generera redovisningsposter för att justera momsbeloppavvikelsen och förskjuta den mot kontot för realiserad valutakursvinst/förlust, som konfigureras i redovisningsinställningarna.

Med hjälp av föregående exempel kan du visa den här funktionen, anta att data i registret TAXTRANS vid tidpunkten för bokföringen är följande.

| Konverteringsparametrar för moms | Transaktionsvaluta (EUR) | Redovisningsvaluta (USD) | Rapporteringsvaluta (GBP) | Skattevaluta (GBP) |
| ------------------------------- | -------------------------- | ------------------------- | ------------------------ | ------------------ |
| Redovisningsvaluta             | 100                        | 111                       | 83                       | **83.25**          |
| Rapporteringsvaluta              | 100                        | 111                       | 83                       | **83**             |

När du kör programmet momskvittning vid ett månadsslut kommer redovisningsposten att vara följande.
#### <a name="scenario-sales-tax-conversion--accounting-currency"></a>Scenario: momskonvertering = "redovisningsvaluta"

| Huvudkonto           | Transaktionsvaluta (GBP) | Redovisningsvaluta (USD) | Rapporteringsvaluta (GBP) |
| ---------------------- | -------------------------- | ------------------------- | ------------------------ |
| Utgående/ingående moms | -83,25                     | -111                      | -83,25                   |
| Momskvittering         | 83.25                      | 111                       | 83.25                    |
| Realiserad vinst/förlust     | 0                          | 0                         | -0,25                    |
| Utgående/ingående moms | 0                          | 0                         | 0.25                     |

#### <a name="scenario-sales-tax-conversion--reporting-currency"></a>Scenario: momskonvertering = "rappporteringsvaluta"


| Huvudkonto           | Transaktionsvaluta (GBP) | Redovisningsvaluta (USD) | Rapporteringsvaluta (GBP) |
| ---------------------- | -------------------------- | ------------------------- | ------------------------ |
| Utgående/ingående moms | -83                        | -110,67                   | -83                      |
| Momskvittering         | 83                         | 110.67                    | 83                       |
| Realiserad vinst/förlust     | 0                          | 0.33                      | 0                        |
| Utgående/ingående moms | 0                          | -0,33                     | 0                        |



Mer information finns i följande avsnitt:

- [Dubbel valuta](dual-currency.md)
- [Momsöversikt](indirect-taxes-overview.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
