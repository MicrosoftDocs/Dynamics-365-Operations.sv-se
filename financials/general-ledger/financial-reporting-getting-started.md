---
title: Ekonomisk rapportering
description: "Det här avsnittet beskrivs hur du kommer åt ekonomisk rapportering i Microsoft Dynamics 365 för operationer och hur du använder finansiella rapporteringsfunktioner. Den innehåller en beskrivning av de ekonomiska standardrapporter som tillhandahålls."
author: RobinARH
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: FinancialReports
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 10444
ms.assetid: 3eae6dc3-ee06-4b6d-9e7d-1ee2c3b10339
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: d13747f17b5f382b3a530b1f166681eeec0b9d73
ms.lasthandoff: 03/31/2017


---

# <a name="financial-reporting"></a>Ekonomisk rapportering

Det här avsnittet beskrivs hur du kommer åt ekonomisk rapportering i Microsoft Dynamics 365 för operationer och hur du använder finansiella rapporteringsfunktioner. Den innehåller en beskrivning av de ekonomiska standardrapporter som tillhandahålls.

<a name="accessing-financial-reporting"></a>Åtkomst till ekonomisk rapportering
-----------------------------

Du kan hitta den **ekonomisk rapportering** menyn i följande placeras i Dynamics 365 för operationer:

-   **Redovisning**&gt;**förfrågningar och rapporter**
-   **Budgetering**&gt;**Inquires och rapporter**&gt;**grundläggande budgetering**
-   **Budgetering**&gt;**förfrågningar och rapporter**&gt;**budgetplanering**
-   **Budgetering**&gt;**förfrågningar och rapporter**&gt;**budgetkontroll**
-   Konsolideringar

Om du vill skapa och generera ekonomiska rapporter för en juridisk person måste du ange följande information för den juridiska personen:

-   Räkenskapskalender
-   Redovisning
-   Kontoplan
-   Valuta

Funktionerna för ekonomisk rapportering är tillgängliga för användare som har rätt behörigheter och uppgifter tilldelade genom sina säkerhetsroller. Nedan följer dessa privilegier och behörigheter tillsammans med de kopplade rollerna.

### <a name="duties"></a>Programbehörigheter

| Behörighetsetikett                            | Beskrivning                                                             | AOT-namn                         |
|---------------------------------------|-------------------------------------------------------------------------|----------------------------------|
| Underhåll säkerhet för ekonomiska rapporter | Underhåll säkerhet för ekonomiska rapporter och utför administrativa uppgifter. | FinancialReportsSecurityMaintain |
| Underhåll ekonomiska rapporter            | Utforma och underhåll ekonomiska rapporter .                                  | FinancialReportsMaintain         |
| Generera ekonomiska rapporter            | Generera och uppdatera ekonomiska rapporter.                                 | FinancialReportsGenerate         |
| Granska finansiellt resultat          | Granska och analysera finansiellt resultat.                               | FinancialReportsPerfReview       |

### <a name="privileges"></a>Behörigheter

| Privilegieetikett                       | Beskrivning                                                             | AOT-namn                         |
|---------------------------------------|-------------------------------------------------------------------------|----------------------------------|
| Underhåll säkerhet för ekonomiska rapporter | Underhåll säkerhet för ekonomiska rapporter och utför administrativa uppgifter. | FinancialReportsSecurityMaintain |
| Underhåll ekonomiska rapporter            | Utforma och underhåll ekonomiska rapporter .                                  | FinancialReportsMaintainReports  |
| Generera ekonomiska rapporter            | Generera och uppdatera ekonomiska rapporter.                                 | FinancialReportsGenerateReports  |
| Visa ekonomiska rapporter                | Visa ekonomiska rapporter.                                                 | FinancialReportsView             |

### <a name="roles"></a>Roller

| Privilegieetikett                       | Avgift                                  | Roller                                                                           |
|---------------------------------------|---------------------------------------|---------------------------------------------------------------------------------|
| Underhåll säkerhet för ekonomiska rapporter | Underhåll säkerhet för ekonomiska rapporter | Säkerhetsadministratör                                                          |
| Underhåll ekonomiska rapporter            | Underhåll ekonomiska rapporter            | Redovisningschef Redovisningsansvarig, styrekonomens budgetchef |
| Generera ekonomiska rapporter            | Generera ekonomiska rapporter            | Revisorn VD Ekonomichef,                                                            |
| Visa ekonomiska rapporter                | Granska finansiellt resultat          | Ingen tilldelad                                                                   |

När en användare har lagts till eller om en roll ändras får användaren åtkomst till ekonomisk rapportering inom några minuter. **Anmärkning:** läggs rollen sysadmin på alla roller i ekonomiska rapporter.

## <a name="default-reports"></a>Standardrapporter
Ekonomisk rapportering innehåller 22 standardrapporter. Varje rapport använder standardkategorierna huvudkontot i Dynamics 365 för operationer. Du kan använda dessa rapporter som de är eller som utgångspunkt för din ekonomiska rapportering. Utöver de traditionella boksluten, som till exempel resultaträkning och balansräkning, inkluderar dessa standardrapporter rapporter som visar andra typer av ekonomiska rapporter som du kan skapa. Varje rapport i följande tabell länkar i en presentation Office Mix om rapporten.

| Standardrapport                                                                                         | beskrivning                                                                                                                                                                                                                                                                                                          |
|--------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [12 Month Rolling Single Column Income Statement – Default](https://mix.office.com/watch/76kc7bm3wnt1) | Visa en organisations vinst för de tidigare tolv månaderna i samma kolumn.                                                                                                                                                                                                                                      |
| [12 Month Trend Income Statement – Default](https://mix.office.com/watch/12brmfge5p8r)                 | Visa en organisations vinst för de var och en av senaste tolv månaderna. Dessa tolv månader kan omfatta mer än ett räkenskapsår.                                                                                                                                                                                             |
| [Actual vs Budget – Default](https://mix.office.com/watch/fi439lkwr0no)                                | Visa detaljerad saldoinformation för alla konton för den ursprungliga budgeten och jämför den reviderade budgeten med utfall som har en avvikelse.                                                                                                                                                                          |
| [Audit Details – Default](https://mix.office.com/watch/1i15nzd3nwkyh)                                  | Visa detaljerad saldoinformation för alla konton. Den här rapporten visar debet- och kreditsaldon i rapporteringsvalutan och i lokal valuta, tillsammans med ytterligare transaktionsinformation, såsom användar-id, användaren som senast ändrade data, datum för den senaste ändringen och journal-id. |
| [Balance List – Default](https://mix.office.com/watch/1kezwu2a10fq4)                                   | Visa detaljerad saldoinformation för alla konton. Den här rapporten visar ingående och utgående balanser och debet- och kreditsaldon för den aktuella perioden till dags dato, tillsammans med ytterligare transaktionsinformation, såsom verifikationen.                                                                    |
| [Balance Sheet – Default](https://mix.office.com/watch/zkgq0u7visw9)                                   | Visa organisationens ekonomiska läge för året.                                                                                                                                                                                                                                                             |
| [Balance Sheet and Income Statement Side by Side - Default](https://mix.office.com/watch/zkgq0u7visw9) | Visa organisationens ekonomiska läge och lönsamhet för året sida vid sida.                                                                                                                                                                                                                              |
| [Cash Flow – Default](https://mix.office.com/watch/jd3go9pz6390)                                       | Visa kontanter som kommer in och lämnar organisationen.                                                                                                                                                                                                                                   |
| [Detailed JE and TB Review – Default](https://mix.office.com/watch/1sw9fmtwgjb1f)                      | Visa ingående balans och aktivitetsinformation för alla konton.                                                                                                                                                                                                                                                      |
| [Detailed Trial Balance - Default](https://mix.office.com/watch/1ewwgbpv0iwrl)                         | Visa saldoinformation för alla konton med debet- och kreditsaldon och nettot för dessa saldon, tillsammans med transaktionsdatum, verifikation och journalbeskrivning.                                                                                                                                  |
| [Expenses Three Year Quarterly Trend – Default](https://mix.office.com/watch/gwm4zu7tmtj8)             | Visa utgifter för de senaste tolv kvartalen över de tre senaste åren.                                                                                                                                                                                                                                   |
| [Financial Captions JE and TB Review – Default](https://mix.office.com/watch/1sw9fmtwgjb1f)            | Visa en översikt över saldona och aktiviteten för finansrubrikerna tillgång, skuld, ägarens eget kapital, intäkt, utgift, vinst eller förlust.                                                                                                                                                                           |
| [Income Statement – Default](https://mix.office.com/watch/sbuhgl5hzuhi)                                | Visa organisationens lönsamhet för den aktuella perioden till dags dato.                                                                                                                                                                                                                                   |
| [Ledger Transaction List – Default](https://mix.office.com/watch/19h9v2rmh48vy)                        | Visa detaljerad saldoinformation för alla konton. Den här rapporten visar debet- och kreditsaldon, tillsammans med ytterligare transaktionsinformation, såsom transaktionsdatum, journalnummer, verifikation och bokföringstyp och spårningsnummer.                                                                            |
| [Ratios – Default](https://mix.office.com/watch/b08hfc5h92me)                                          | Visa organisationens solvens, lönsamhet och effektivitetsgrad för året.                                                                                                                                                                                                                           |
| [Rolling 12 Month Expenses – Default](https://mix.office.com/watch/iywod5qmqhz7)                       | Visa utgifter för var och en av de sista 12 månaderna. Dessa tolv månader kan omfatta mer än ett räkenskapsår.                                                                                                                                                                                                       |
| [Rolling Quarter Income Statement – Default](https://mix.office.com/watch/1k4yl6a6oyxqc)               | Visa organisationens lönsamhet var tredje månad för det föregående året och hittills under året.                                                                                                                                                                                                                   |
| [Side by Side Balance Sheet – Default](https://mix.office.com/watch/zkgq0u7visw9)                      | Visa organisationens ekonomiska läge för året. Den här rapporten visar tillgångar och skulder och aktiekapitalet sida vid sida.                                                                                                                                                                                |
| [Summary Trial Balance – Default](https://mix.office.com/watch/1ewwgbpv0iwrl)                          | Visa information om saldo för alla konton som har in- och utgående balanser och debet- och kreditsaldon tillsammans med deras nettodifferens.                                                                                                                                                                  |
| [Summary Trial Balance Year Over Year – Default](https://mix.office.com/watch/1ewwgbpv0iwrl)           | Visa saldoinformation för alla konton som har ingående och utgående saldon och debet- och kreditsaldon samt deras net skillnaden för innevarande och föregående år.                                                                                                                           |
| [Weekly Sales and Discounts - Default](https://mix.office.com/watch/112ng0hy5de0j)                     | Visa försäljning och rabatter för varje vecka i en månad. Den här rapporten innehåller en fyraveckors summa.                                                                                                                                                                                                              |
| [De tillgängliga budgetmedlen - standard](https://mix.office.com/watch/15hcpezcbx7tv)                         | Visa en detaljerad jämförelse av reviderade budgeten, faktiska utgifter, Budgetreservationer och tillgängliga budgetmedlen för alla konton                                                                                                                                                                                  |

## <a name="opening-financial-reports"></a>Öppna ekonomiska rapporter
När du klickar på menyn **Ekonomisk rapportering** visas listan över ekonomiska standardrapporter för företaget. Du kan sedan öppna eller ändra en rapport. Öppna en av standardrapporterna genom att välja rapportnamnet. Första gången rapporten öppnas skapas den automatiskt för föregående månad. Om du öppnar en rapport första gången i augusti 2016 exempelvis genereras rapporten för 31 juli 2016. När en rapport har öppnats kan du börja utforska den mer ingående genom att titta närmare på specifika delar av data och ändra rapportsalternativ.

## <a name="creating-and-modifying-financial-reports"></a>Skapa och ändra ekonomiska rapporter
På listan med ekonomiska rapporter kan du skapa en ny rapport eller ändra en befintlig rapport. Om du har rätt behörighet kan du skapa en ny ekonomisk rapport genom att klicka på **New** i åtgärdsfönstret. Ett report designer-program hämtas till enheten. När report designer startar kan du skapa den nya rapporten. När du har sparat den nya rapporten visas på listan med ekonomiska rapporter. I listan visas endast rapporter som har skapats för företaget som du använder i Dynamics 365 för operationer. Mer information om att skapa och ändra ekonomiska rapporter i Dynamics 365 för åtgärder avser dessa [blogginlägg](https://blogs.msdn.microsoft.com/dynamics_financial_reporting/tag/learning/) rapportering blogg från Dynamics ekonomi. **Anmärkning:** du hämtar report designer-klienten på måste ha version 4.6.2 av Microsoft .NET Framework installerade på den datorn. Den här versionen av Microsoft .NET Framework kan hämtas och installeras från [här](https://www.microsoft.com/en-us/download/details.aspx?id=53345). Om du använder krom, måste du installera tillägget ClickOnce för att hämta report designer-klienten. Om du använder läget incognito Kontrollera ClickOnce-utökningen är aktiverad för incognito. Det går även att ändra en rapport på listan med ekonomiska rapporter. Klicka på **Redigera** i åtgärdsfönstret när området runt rapportnamnet markeras. Rapportprogrammet startar.

<a name="see-also"></a>Se även
--------

[View financial reports](view-financial-reports.md)

[Dynamics-ekonomirapporteringsblogg](http://blogs.msdn.com/b/dynamics_financial_reporting/)

