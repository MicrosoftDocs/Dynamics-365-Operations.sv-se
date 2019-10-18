---
title: Översikt över ekonomisk rapportering
description: Det här avsnittet beskriver hur du kommer åt ekonomisk rapportering i Microsoft Dynamics 365 Finance och hur du använder finansiella rapporteringsfunktioner. Den innehåller en beskrivning av de ekonomiska standardrapporter som tillhandahålls.
author: aprilolson
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 10444
ms.assetid: 3eae6dc3-ee06-4b6d-9e7d-1ee2c3b10339
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: caa449feba22c5804799b5317a8e29c139cc440e
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2179925"
---
# <a name="financial-reporting-overview"></a>Översikt över ekonomisk rapportering

[!include [banner](../includes/banner.md)]

Det här avsnittet beskriver hur du kommer åt ekonomisk rapportering och hur du använder finansiella rapporteringsfunktioner. Den innehåller även en beskrivning av de ekonomiska standardrapporter som tillhandahålls.

<a name="accessing-financial-reporting"></a>Åtkomst till ekonomisk rapportering
-----------------------------

Menyn **Ekonomisk rapportering** finns på följande platser:

-   **Redovisning** &gt; **Förfrågningar och rapporter**
-   **Budgetering** &gt; **Förfrågningar och rapporter** &gt; **Grundläggande budgetering**
-   **Budgetering** &gt; **Förfrågningar och rapporter** &gt; **Budgetplanering**
-   **Budgetering** &gt; **Förfrågningar och rapporter** &gt; **Budgetkontroll**
-   Konsolideringar

Om du vill skapa och skapa ekonomiska rapporter för en juridisk person måste du ange följande information för den juridiska personen:

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
| Skapa ekonomiska rapporter            | Skapa och uppdatera ekonomiska rapporter.                                 | FinancialReportsGenerate         |
| Granska finansiellt resultat          | Granska och analysera finansiellt resultat.                               | FinancialReportsPerfReview       |

### <a name="privileges"></a>Behörigheter

| Privilegieetikett                       | Beskrivning                                                             | AOT-namn                         |
|---------------------------------------|-------------------------------------------------------------------------|----------------------------------|
| Underhåll säkerhet för ekonomiska rapporter | Underhåll säkerhet för ekonomiska rapporter och utför administrativa uppgifter. | FinancialReportsSecuritySystemMaintain |
| Underhåll ekonomiska rapporter            | Utforma och underhåll ekonomiska rapporter .                                  | FinancialReportsMaintainReports  |
| Skapa ekonomiska rapporter            | Skapa och uppdatera ekonomiska rapporter.                                 | FinancialReportsGenerateReports  |
| Visa ekonomiska rapporter                | Visa ekonomiska rapporter.                                                 | FinancialReportsView             |

### <a name="roles"></a>Roller

| Privilegieetikett                       | Avgift                                  | Roller                                                                           |
|---------------------------------------|---------------------------------------|---------------------------------------------------------------------------------|
| Underhåll säkerhet för ekonomiska rapporter | Underhåll säkerhet för ekonomiska rapporter | Säkerhetsadministratör                                                          |
| Underhåll ekonomiska rapporter            | Underhåll ekonomiska rapporter            | Redovisningschef, Redovisningsansvarig, Ekonomicontroller, Budgetchef |
| Skapa ekonomiska rapporter            | Skapa ekonomiska rapporter            | VD, Ekonomichef, Revisor                                                            |
| Visa ekonomiska rapporter                | Granska finansiellt resultat          | Ingen tilldelad                                                                   |

När en användare har lagts till eller om en roll ändras får användaren åtkomst till ekonomisk rapportering inom några minuter. **Obs!** Rollen sysadmin läggs till i alla roller inom ekonomisk rapportering.

## <a name="default-reports"></a>Standardrapporter
Ekonomisk rapportering innehåller 22 standardrapporter. Varje rapport använder standardkategorierna för huvudkonton. Du kan använda dessa rapporter som de är eller som utgångspunkt för din ekonomiska rapportering. Utöver de traditionella boksluten, som till exempel resultaträkning och balansräkning, inkluderar dessa standardrapporter rapporter som visar andra typer av ekonomiska rapporter som du kan skapa. 

<!--Each report in the following table links to an Office Mix presentation about the report.-->

| Standardrapport                                                                                         | Beskrivning                                                                                                                                                                                                                                                                                                          |
|--------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Tolv månaders rullande resultaträkning med en kolumn – standardinställning | Visa en organisations vinst för de tidigare tolv månaderna i samma kolumn.                                                                                                                                                                                                                                      |
| Resultaträkning med tolv månaders trend – standardinställning                 | Visa en organisations vinst för de var och en av senaste tolv månaderna. Dessa tolv månader kan omfatta mer än ett räkenskapsår.                                                                                                                                                                                             |
| Utfall kontra budget - standardinställning                                | Visa detaljerad saldoinformation för alla konton för den ursprungliga budgeten och jämför den reviderade budgeten med utfall som har en avvikelse.                                                                                                                                                                          |
| Granskningsinformation – standardinställning                                  | Visa detaljerad saldoinformation för alla konton. Den här rapporten visar debet- och kreditsaldon i rapporteringsvalutan och i lokal valuta, tillsammans med ytterligare transaktionsinformation, såsom användar-id, användaren som senast ändrade data, datum för den senaste ändringen och journal-id. |
| Saldolista – standardinställning                                   | Visa detaljerad saldoinformation för alla konton. Den här rapporten visar ingående och utgående balanser och debet- och kreditsaldon för den aktuella perioden till dags dato, tillsammans med ytterligare transaktionsinformation, såsom verifikationen.                                                                    |
| Balansräkning – standardinställning                                   | Visa organisationens ekonomiska läge för året.                                                                                                                                                                                                                                                             |
| Balansräkning och resultaträkning sida vid sida – standardinställning | Visa organisationens ekonomiska läge och lönsamhet för året sida vid sida.                                                                                                                                                                                                                              |
| Kassaflöde – standardinställning                                       | Visa kontanter som kommer in och lämnar organisationen.                                                                                                                                                                                                                                   |
| Detaljerad JE- och TB-granskning – standardinställning                      | Visa ingående balans och aktivitetsinformation för alla konton.                                                                                                                                                                                                                                                      |
| Detaljerad råbalans – standardinställning                         | Visa saldoinformation för alla konton med debet- och kreditsaldon och nettot för dessa saldon, tillsammans med transaktionsdatum, verifikation och journalbeskrivning.                                                                                                                                  |
| Utgifter med treårig kvartalstrend – standardinställning             | Visa utgifter för de senaste tolv kvartalen över de tre senaste åren.                                                                                                                                                                                                                                   |
| Ekonomisk översikt för JE- och TB-granskning – standardinställning            | Visa en översikt över saldona och aktiviteten för finansrubrikerna tillgång, skuld, ägarens eget kapital, intäkt, utgift, vinst eller förlust.                                                                                                                                                                           |
| Resultaträkning – standardinställning                                | Visa organisationens lönsamhet för den aktuella perioden till dags dato.                                                                                                                                                                                                                                   |
| Redovisningstransaktionslista – standardinställning                        | Visa detaljerad saldoinformation för alla konton. Den här rapporten visar debet- och kreditsaldon, tillsammans med ytterligare transaktionsinformation, såsom transaktionsdatum, journalnummer, verifikation och bokföringstyp och spårningsnummer.                                                                            |
| Grader – standardinställning                                          | Visa organisationens solvens, lönsamhet och effektivitetsgrad för året.                                                                                                                                                                                                                           |
| Rullande tolv månaders utgifter – standardinställning                       | Visa utgifter för var och en av de sista 12 månaderna. Dessa tolv månader kan omfatta mer än ett räkenskapsår.                                                                                                                                                                                                       |
| Rullande resultaträkning för kvartal – standardinställning               | Visa organisationens lönsamhet på kvartalsbasis för det senaste året och även året till dags dato.                                                                                                                                                                                                                   |
| Balansräkning sida vid sida – standardinställning                      | Visa organisationens ekonomiska läge för året. Den här rapporten visar tillgångar och skulder och aktiekapitalet sida vid sida.                                                                                                                                                                                |
| Råbalanssammanfattning - standardinställning                          | Visa information om saldo för alla konton som har in- och utgående balanser och debet- och kreditsaldon tillsammans med deras nettodifferens.                                                                                                                                                                  |
| Summerad råbalans på årsbasis – standardinställning           | Visa saldoinformation för alla konton som har in- och utgående saldon, och debet- och kreditsaldon tillsammans med deras nettodifferens för aktuellt år och föregående år.                                                                                                                           |
| Veckoförsäljning och rabatt – standardinställning                     | Visa försäljning och rabatter för varje vecka i en månad. Den här rapporten innehåller en fyraveckors summa.                                                                                                                                                                                                              |
| Tillgängliga budgetmedel - standardinställningar                         | Visa en detaljerad jämförelse av reviderad budget, faktisk utgift, budgetreservationer och tillgängliga budgetmedel för alla konton                                                                                                                                                                                  |

## <a name="opening-financial-reports"></a>Öppna ekonomiska rapporter
När du klickar på menyn **Ekonomisk rapportering** visas listan över ekonomiska standardrapporter för företaget. Du kan sedan öppna eller ändra en rapport. Öppna en av standardrapporterna genom att välja rapportnamnet. Första gången rapporten öppnas skapas den automatiskt för föregående månad. Om du exempelvis öppnar en rapport för första gången i augusti 2016 skapas rapporten för den 31 juli 2016. När en rapport har öppnats kan du börja utforska den mer ingående genom att titta närmare på specifika delar av data och ändra rapportsalternativ.

## <a name="creating-and-modifying-financial-reports"></a>Skapa och ändra ekonomiska rapporter
På listan med ekonomiska rapporter kan du skapa en ny rapport eller ändra en befintlig rapport. Om du har rätt behörighet kan du skapa en ny ekonomisk rapport genom att klicka på **Ny** i åtgärdsfönstret. Ett rapportdesignerprogram hämtas till enheten. När rapportdesignern startar kan du skapa den nya rapporten. När du har sparat den nya rapporten visas på listan med ekonomiska rapporter. Listan visar endast rapporter som har skapats för företaget som använder i Finance. 

> [!NOTE] 
> Den dator som du hämtar rapportdesignerklienten till måste har version 4.6.2 av Microsoft .NET Framework installerat. Den här versionen av Microsoft .NET Framework kan hämtas och installeras från [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=53345). Om du använder Chrome måste du installera tillägget ClickOnce för att hämta rapportdesignerklienten. Om du använder osynligt läge, se då till att tillägget ClickOnce har aktiverats för osynligt läge. Det går även att ändra en rapport på listan med ekonomiska rapporter. Klicka på **Redigera** i åtgärdsfönstret när området runt rapportnamnet markeras. Rapportprogrammet startar.

## <a name="additional-resources"></a>Ytterligare resurser
- [Visa ekonomiska rapporter](view-financial-reports.md)



