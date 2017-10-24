---
title: Ekonomisk rapportering
description: "Det här avsnittet beskriver hur du kommer åt ekonomisk rapportering i Microsoft Dynamics 365 for Finance and Operations, Enterprise edition och hur du använder finansiella rapporteringsfunktioner. Den innehåller en beskrivning av de ekonomiska standardrapporter som tillhandahålls."
author: aprilolson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 10444
ms.assetid: 3eae6dc3-ee06-4b6d-9e7d-1ee2c3b10339
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: ed207bdc04041ec2f21cb1038451fc75b8d061a1
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="financial-reporting"></a>Ekonomisk rapportering

[!include[banner](../includes/banner.md)]


Det här avsnittet beskriver hur du kommer åt ekonomisk rapportering i Microsoft Dynamics 365 for Finance and Operations, Enterprise edition och hur du använder finansiella rapporteringsfunktioner. Den innehåller en beskrivning av de ekonomiska standardrapporter som tillhandahålls.

<a name="accessing-financial-reporting"></a>Åtkomst till ekonomisk rapportering
-----------------------------

Menyn **Ekonomisk rapportering** finns på följande platser i Finance and Operations:

-   **Redovisning** &gt; **Förfrågningar och rapporter**
-   **Budgetering** &gt; **Förfrågningar och rapporter** &gt; **Grundläggande budgetering**
-   **Budgetering** &gt; **Förfrågningar och rapporter** &gt; **Budgetplanering**
-   **Budgetering** &gt; **Förfrågningar och rapporter** &gt; **Budgetkontroll**
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
| Underhåll ekonomiska rapporter            | Underhåll ekonomiska rapporter            | Redovisningschef, Redovisningsansvarig, Ekonomicontroller, Budgetchef |
| Generera ekonomiska rapporter            | Generera ekonomiska rapporter            | VD, Ekonomichef, Revisor                                                            |
| Visa ekonomiska rapporter                | Granska finansiellt resultat          | Ingen tilldelad                                                                   |

När en användare har lagts till eller om en roll ändras får användaren åtkomst till ekonomisk rapportering inom några minuter. **Obs!** Rollen sysadmin läggs till i alla roller inom ekonomisk rapportering.

## <a name="default-reports"></a>Standardrapporter
Ekonomisk rapportering innehåller 22 standardrapporter. Varje rapport använder standardkategorierna för huvudkonto i Finance and Operations. Du kan använda dessa rapporter som de är eller som utgångspunkt för din ekonomiska rapportering. Utöver de traditionella boksluten, som till exempel resultaträkning och balansräkning, inkluderar dessa standardrapporter rapporter som visar andra typer av ekonomiska rapporter som du kan skapa. Varje rapport i följande tabell länkar till en Office Mix-presentation om rapporten.

| Standardrapport                                                                                         | beskrivning                                                                                                                                                                                                                                                                                                          |
|--------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [Tolv månaders rullande resultaträkning med en kolumn – standardinställning](https://mix.office.com/watch/76kc7bm3wnt1) | Visa en organisations vinst för de tidigare tolv månaderna i samma kolumn.                                                                                                                                                                                                                                      |
| [Resultaträkning med tolv månaders trend – standardinställning](https://mix.office.com/watch/12brmfge5p8r)                 | Visa en organisations vinst för de var och en av senaste tolv månaderna. Dessa tolv månader kan omfatta mer än ett räkenskapsår.                                                                                                                                                                                             |
| [Utfall kontra budget - standardinställning](https://mix.office.com/watch/fi439lkwr0no)                                | Visa detaljerad saldoinformation för alla konton för den ursprungliga budgeten och jämför den reviderade budgeten med utfall som har en avvikelse.                                                                                                                                                                          |
| [Granskningsinformation – standardinställning](https://mix.office.com/watch/1i15nzd3nwkyh)                                  | Visa detaljerad saldoinformation för alla konton. Den här rapporten visar debet- och kreditsaldon i rapporteringsvalutan och i lokal valuta, tillsammans med ytterligare transaktionsinformation, såsom användar-id, användaren som senast ändrade data, datum för den senaste ändringen och journal-id. |
| [Saldolista – standardinställning](https://mix.office.com/watch/1kezwu2a10fq4)                                   | Visa detaljerad saldoinformation för alla konton. Den här rapporten visar ingående och utgående balanser och debet- och kreditsaldon för den aktuella perioden till dags dato, tillsammans med ytterligare transaktionsinformation, såsom verifikationen.                                                                    |
| [Balansräkning – standardinställning](https://mix.office.com/watch/zkgq0u7visw9)                                   | Visa organisationens ekonomiska läge för året.                                                                                                                                                                                                                                                             |
| [Balansräkning och resultaträkning sida vid sida – standardinställning](https://mix.office.com/watch/zkgq0u7visw9) | Visa organisationens ekonomiska läge och lönsamhet för året sida vid sida.                                                                                                                                                                                                                              |
| [Kassaflöde – standardinställning](https://mix.office.com/watch/jd3go9pz6390)                                       | Visa kontanter som kommer in och lämnar organisationen.                                                                                                                                                                                                                                   |
| [Detaljerad JE- och TB-granskning – standardinställning](https://mix.office.com/watch/1sw9fmtwgjb1f)                      | Visa ingående balans och aktivitetsinformation för alla konton.                                                                                                                                                                                                                                                      |
| [Detaljerad råbalans – standardinställning](https://mix.office.com/watch/1ewwgbpv0iwrl)                         | Visa saldoinformation för alla konton med debet- och kreditsaldon och nettot för dessa saldon, tillsammans med transaktionsdatum, verifikation och journalbeskrivning.                                                                                                                                  |
| [Utgifter med treårig kvartalstrend – standardinställning](https://mix.office.com/watch/gwm4zu7tmtj8)             | Visa utgifter för de senaste tolv kvartalen över de tre senaste åren.                                                                                                                                                                                                                                   |
| [Ekonomisk översikt för JE- och TB-granskning – standardinställning](https://mix.office.com/watch/1sw9fmtwgjb1f)            | Visa en översikt över saldona och aktiviteten för finansrubrikerna tillgång, skuld, ägarens eget kapital, intäkt, utgift, vinst eller förlust.                                                                                                                                                                           |
| [Resultaträkning – standardinställning](https://mix.office.com/watch/sbuhgl5hzuhi)                                | Visa organisationens lönsamhet för den aktuella perioden till dags dato.                                                                                                                                                                                                                                   |
| [Redovisningstransaktionslista – standardinställning](https://mix.office.com/watch/19h9v2rmh48vy)                        | Visa detaljerad saldoinformation för alla konton. Den här rapporten visar debet- och kreditsaldon, tillsammans med ytterligare transaktionsinformation, såsom transaktionsdatum, journalnummer, verifikation och bokföringstyp och spårningsnummer.                                                                            |
| [Grader – standardinställning](https://mix.office.com/watch/b08hfc5h92me)                                          | Visa organisationens solvens, lönsamhet och effektivitetsgrad för året.                                                                                                                                                                                                                           |
| [Rullande tolv månaders utgifter – standardinställning](https://mix.office.com/watch/iywod5qmqhz7)                       | Visa utgifter för var och en av de sista 12 månaderna. Dessa tolv månader kan omfatta mer än ett räkenskapsår.                                                                                                                                                                                                       |
| [Rullande resultaträkning för kvartal – standardinställning](https://mix.office.com/watch/1k4yl6a6oyxqc)               | Visa organisationens lönsamhet på kvartalsbasis för det senaste året och även året till dags dato.                                                                                                                                                                                                                   |
| [Balansräkning sida vid sida – standardinställning](https://mix.office.com/watch/zkgq0u7visw9)                      | Visa organisationens ekonomiska läge för året. Den här rapporten visar tillgångar och skulder och aktiekapitalet sida vid sida.                                                                                                                                                                                |
| [Råbalanssammanfattning - standardinställning](https://mix.office.com/watch/1ewwgbpv0iwrl)                          | Visa information om saldo för alla konton som har in- och utgående balanser och debet- och kreditsaldon tillsammans med deras nettodifferens.                                                                                                                                                                  |
| [Summerad råbalans på årsbasis – standardinställning](https://mix.office.com/watch/1ewwgbpv0iwrl)           | Visa saldoinformation för alla konton som har in- och utgående saldon, och debet- och kreditsaldon tillsammans med deras nettodifferens för aktuellt år och föregående år.                                                                                                                           |
| [Veckoförsäljning och rabatt – standardinställning](https://mix.office.com/watch/112ng0hy5de0j)                     | Visa försäljning och rabatter för varje vecka i en månad. Den här rapporten innehåller en fyraveckors summa.                                                                                                                                                                                                              |
| [Tillgängliga budgetmedel - standardinställningar](https://mix.office.com/watch/15hcpezcbx7tv)                         | Visa en detaljerad jämförelse av reviderad budget, faktisk utgift, budgetreservationer och tillgängliga budgetmedel för alla konton                                                                                                                                                                                  |

## <a name="opening-financial-reports"></a>Öppna ekonomiska rapporter
När du klickar på menyn **Ekonomisk rapportering** visas listan över ekonomiska standardrapporter för företaget. Du kan sedan öppna eller ändra en rapport. Öppna en av standardrapporterna genom att välja rapportnamnet. Första gången rapporten öppnas skapas den automatiskt för föregående månad. Om du exempelvis öppnar en rapport för första gången i augusti 2016 genereras rapporten för den 31 juli 2016. När en rapport har öppnats kan du börja utforska den mer ingående genom att titta närmare på specifika delar av data och ändra rapportsalternativ.

## <a name="creating-and-modifying-financial-reports"></a>Skapa och ändra ekonomiska rapporter
På listan med ekonomiska rapporter kan du skapa en ny rapport eller ändra en befintlig rapport. Om du har rätt behörighet kan du skapa en ny ekonomisk rapport genom att klicka på **Ny** i åtgärdsfönstret. Ett rapportdesignerprogram hämtas till enheten. När rapportdesignern startar kan du skapa den nya rapporten. När du har sparat den nya rapporten visas på listan med ekonomiska rapporter. Listan visar endast rapporter som har skapats för företaget som använder i Finance and Operations. Mer information om att skapa och ändra ekonomiska rapporter i Dynamics 365 for Finance and Operations finns i följande [blogginlägg](https://blogs.msdn.microsoft.com/dynamics_financial_reporting/tag/learning/) från Dynamics ekonomirapporteringsblogg. **Obs!** Den dator som du hämtar rapportdesignerklienten till måste har version 4.6.2 av Microsoft .NET Framework installerat. Den här versionen av Microsoft .NET Framework kan hämtas och installeras [här](https://www.microsoft.com/en-us/download/details.aspx?id=53345). Om du använder Chrome måste du installera tillägget ClickOnce för att hämta rapportdesignerklienten. Om du använder osynligt läge, se då till att tillägget ClickOnce har aktiverats för osynligt läge. Det går även att ändra en rapport på listan med ekonomiska rapporter. Klicka på **Redigera** i åtgärdsfönstret när området runt rapportnamnet markeras. Rapportprogrammet startar.

<a name="see-also"></a>Se även
--------

[Visa ekonomiska rapporter](view-financial-reports.md)

[Dynamics-ekonomirapporteringsblogg](http://blogs.msdn.com/b/dynamics_financial_reporting/)




