---
title: Översikt över ekonomisk rapportering
description: Det här avsnittet beskriver hur du kommer åt ekonomisk rapportering i Microsoft Dynamics 365 Finance och hur du använder finansiella rapporteringsfunktioner.
author: aprilolson
ms.date: 12/04/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: roschlom
ms.custom: 10444
ms.assetid: 3eae6dc3-ee06-4b6d-9e7d-1ee2c3b10339
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 43ab01d36f032e36a0daed6f94897bba42f8a189
ms.sourcegitcommit: ff09736563d3cd2bc74c7664edd1767b218401cb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "6189007"
---
# <a name="get-started-with-financial-reporting"></a>Kom i gång med Financial reporting 

[!include [banner](../includes/banner.md)]

Det här avsnittet beskriver hur du kommer åt ekonomisk rapportering och hur du använder finansiella rapporteringsfunktioner. Den innehåller även en beskrivning av de ekonomiska standardrapporter som tillhandahålls.

## <a name="accessing-financial-reporting"></a>Åtkomst till ekonomisk rapportering

Menyn **Ekonomisk rapportering** finns på följande platser:

-   **Redovisning** &gt; **Förfrågningar och rapporter**
-   **Budgetering** &gt; **Förfrågningar och rapporter** &gt; **Grundläggande budgetering**
-   **Budgetering** &gt; **Förfrågningar och rapporter** &gt; **Budgetplanering**
-   **Budgetering** &gt; **Förfrågningar och rapporter** &gt; **Budgetkontroll**
-   Konsolideringar

Om du vill skapa och skapa ekonomiska rapporter för en juridisk person måste du ange följande information för den juridiska personen:

-   Räkenskapskalender
-   Ledger
-   Kontoplan
-   Valuta
-   Bokför en transaktion på minst ett konto
-   Huvudkontot visas i kolumnen Markerade i **Redovisning > Redovisningsinställningar > Inställningar för Financial Reporting**

## <a name="granting-security-access-to-financial-reporting"></a>Bevilja säkerhetsåtkomst till Financial Reporting
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

När en användare har lagts till eller om en roll ändras får användaren åtkomst till ekonomisk rapportering inom några minuter. 

> [!NOTE]
> Rollen sysadmin läggs till i alla roller inom ekonomisk rapportering.

## <a name="report-deletions-and-expirations"></a>Rapportborttagningar och förfallodatum
Användare som skapar en rapport kan ta bort sina egna rapporter. Användare med programbehörigheten **Underhåll säkerhet för ekonomiska rapporter** kan ta bort andras rapporter. 

I version 10.0.8 har utgångsdatum fastställts. En ny nödvändig funktion kommer att aktiveras på sidan **Alla** på arbetsytan funktionshantering. Den **ekonomiska rapporten över lagringsprinciper** innehåller följande ändringar:
* Nyligen genererade rapporter markeras automatiskt med ett förfallodatum på 90 dagar från det att de genereras.
* Alla befintliga rapporter från innan funktionen installerades kommer att ges en förfalloperiod på 90 dagar. Datumet kan visas som tomt under en kort tidsperiod tills den ekonomiska rapporteringstjänsten körs, en rapport genereras och tjänsten utför uppdateringen till befintliga rapporter med ett tomt förfallodatum. 
* Användare med den **upprätthålla ekonomisk rapporteringssäkerhet** har åtkomst till den här funktionen. Alla användare i programbehörigheten **Underhåll ekonomisk rapport** som beviljats privilegium **Underhåll utgångsdatum för ekonomisk rapport** kommer också att ha möjlighet att ändra förfalloperioden. Det finns för närvarande två alternativ för kvarhållning: 
  * Ett förfallodatum på 90 dagar.
  * Ett alternativ för att ange att rapporten aldrig ska upphöra att gälla.
  
När ett förfallodatum, t.ex. 90 dagar, har valts används 90 dagar från idag. Detta är ett annat beteende än 90 dagar från det ursprungliga genereringsdatum som angavs när rapporten genererades. 
  
Ytterligare alternativ kommer att beaktas i framtida funktioner. Giltighetstiden på 90 dagar blir standardvärdet, och användare med rätt behörighet kan åsidosätta standardvärdet på listsidan **ekonomirapporter**.    

## <a name="default-reports"></a>Standardrapporter
Ekonomisk rapportering innehåller 22 standardrapporter. Varje rapport använder standardkategorierna för huvudkonton. Du kan använda dessa rapporter som de är eller som utgångspunkt för din ekonomiska rapportering. Utöver de traditionella boksluten, som till exempel resultaträkning och balansräkning, inkluderar dessa standardrapporter rapporter som visar andra typer av ekonomiska rapporter som du kan skapa. 

<!--Each report in the following table links to an Office Mix presentation about the report.-->

| Standardrapport                                                                                         | Beskrivning                                                                                                                                                                                                                                                                                                          |
|--------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Tolv månaders rullande resultaträkning med en kolumn – standardinställning | Visa en organisations vinst för de tidigare tolv månaderna i samma kolumn.                                                                                                                                                                                                                                      |
| Resultaträkning med tolv månaders trend – standardinställning                 | Visa en organisations vinst för de var och en av senaste tolv månaderna. Dessa tolv månader kan omfatta mer än ett räkenskapsår.                                                                                                                                                                                             |
| Utfall kontra budget – standardinställning                                | Visa detaljerad saldoinformation för alla konton för den ursprungliga budgeten och jämför den reviderade budgeten med utfall som har en avvikelse.                                                                                                                                                                          |
| Granskningsinformation – standardinställning                                  | Visa detaljerad saldoinformation för alla konton. Den här rapporten visar debet- och kreditsaldon i rapporteringsvalutan och i lokal valuta, tillsammans med ytterligare transaktionsinformation, såsom användar-id, användaren som senast ändrade data, datum för den senaste ändringen och journal-id. |
| Saldolista – standardinställning                                   | Visa detaljerad saldoinformation för alla konton. Den här rapporten visar ingående och utgående balanser och debet- och kreditsaldon för den aktuella perioden till dags dato, tillsammans med ytterligare transaktionsinformation, såsom verifikationen.                                                                    |
| Balansräkning – standardinställning                                   | Visa organisationens ekonomiska läge för året.                                                                                                                                                                                                                                                             |
| Balansräkning och resultaträkning sida vid sida – standardinställning | Visa organisationens ekonomiska läge och lönsamhet för året sida vid sida.                                                                                                                                                                                                                              |
| Kassaflöde – standardinställning                                       | Visa kontanter som kommer in och lämnar organisationen.                                                                                                                                                                                                                                   |
| Detaljerad JE- och TB-granskning – standardinställning                      | Visa ingående balans och aktivitetsinformation för alla konton.                                                                                                                                                                                                                                                      |
| [Detaljerad råbalans – standardinställning](trial-balance-financial-reports.md)| Visa saldoinformation för alla konton med debet- och kreditsaldon och nettot för dessa saldon, tillsammans med transaktionsdatum, verifikation och journalbeskrivning.                                                                                                                                  |
| Utgifter med treårig kvartalstrend – standardinställning             | Visa utgifter för de senaste tolv kvartalen över de tre senaste åren.                                                                                                                                                                                                                                   |
| Ekonomisk översikt för JE- och TB-granskning – standardinställning            | Visa en översikt över saldona och aktiviteten för finansrubrikerna tillgång, skuld, ägarens eget kapital, intäkt, utgift, vinst eller förlust.                                                                                                                                                                           |
| [Resultaträkning – standardinställning](income-statement-financial-report.md)| Visa organisationens lönsamhet för den aktuella perioden till dags dato.                                                                                                                                                                                                                                   |
| Redovisningstransaktionslista – standardinställning                        | Visa detaljerad saldoinformation för alla konton. Den här rapporten visar debet- och kreditsaldon, tillsammans med ytterligare transaktionsinformation, såsom transaktionsdatum, journalnummer, verifikation och bokföringstyp och spårningsnummer.                                                                            |
| Grader – standardinställning                                          | Visa organisationens solvens, lönsamhet och effektivitetsgrad för året.                                                                                                                                                                                                                           |
| Rullande tolv månaders utgifter – standardinställning                       | Visa utgifter för var och en av de sista 12 månaderna. Dessa tolv månader kan omfatta mer än ett räkenskapsår.                                                                                                                                                                                                       |
| Rullande resultaträkning för kvartal – standardinställning               | Visa organisationens lönsamhet på kvartalsbasis för det senaste året och även året till dags dato.                                                                                                                                                                                                                   |
| Balansräkning sida vid sida – standardinställning                      | Visa organisationens ekonomiska läge för året. Den här rapporten visar tillgångar och skulder och aktiekapitalet sida vid sida.                                                                                                                                                                                |
| [Råbalanssammanfattning – standardinställning](trial-balance-financial-reports.md)| Visa information om saldo för alla konton som har in- och utgående balanser och debet- och kreditsaldon tillsammans med deras nettodifferens.                                                                                                                                                                  |
| [Summerad råbalans på årsbasis – standardinställning](trial-balance-financial-reports.md)| Visa saldoinformation för alla konton som har in- och utgående saldon, och debet- och kreditsaldon tillsammans med deras nettodifferens för aktuellt år och föregående år.                                                                                                                           |
| Veckoförsäljning och rabatt – standardinställning                     | Visa försäljning och rabatter för varje vecka i en månad. Den här rapporten innehåller en fyraveckors summa.                                                                                                                                                                                                              |
| Tillgängliga budgetmedel – standardinställningar                         | Visa en detaljerad jämförelse av reviderad budget, faktisk utgift, budgetreservationer och tillgängliga budgetmedel för alla konton                                                                                                                                                                                  |

## <a name="opening-financial-reports"></a>Öppna ekonomiska rapporter
När du klickar på menyn **Ekonomisk rapportering** visas listan över ekonomiska standardrapporter för företaget. Du kan sedan öppna eller ändra en rapport. Öppna en av standardrapporterna genom att välja rapportnamnet. Första gången rapporten öppnas skapas den automatiskt för föregående månad. Om du exempelvis öppnar en rapport för första gången i augusti 2019 skapas rapporten för den 31 juli 2019. När en rapport har öppnats kan du börja utforska den mer ingående genom att titta närmare på specifika delar av data och ändra rapportsalternativ.

## <a name="creating-and-modifying-financial-reports"></a>Skapa och ändra ekonomiska rapporter
På listan med ekonomiska rapporter kan du skapa en ny rapport eller ändra en befintlig rapport. Om du har rätt behörighet kan du skapa en ny ekonomisk rapport genom att klicka på **Ny** i åtgärdsfönstret. Ett rapportdesignerprogram hämtas till enheten. När rapportdesignern startar kan du skapa den nya rapporten. När du har sparat den nya rapporten visas på listan med ekonomiska rapporter. Listan visar endast rapporter som har skapats för företaget som använder i Dynamics 365 Finance. 

## <a name="reporting-tree-definitions"></a>Rapportträddefinitioner 
En av komponenterna som används för att bygga ekonomiska rapporter är en rapportträdsdefinition. En rapportträddefinition hjälper till att definiera din organisations struktur och hierarki. Det är en korsdimensionell hierarkisk struktur som baseras på de dimensionella relationerna i ekonomiska data. Den innehåller information på rapporteringsenhetsnivå och sammanfattningsnivå för alla enheter i trädet.

Du kan skapa ett obegränsat antal rapportträd för att visa ditt företags data på olika sätt. Varje rapportträd kan innehålla valfri kombination av avdelningar och sammanfattningsenheter, men en rapport definition kan bara länka ett rapportträd åt gången. 


## <a name="troubleshooting-issues-opening-report-designer"></a>Felsökning av problem vid öppnande av rapportdesignern
Det finns några vanliga problem som kan orsaka problem när du öppnar rapportdesigner. De här problemen och stegen för att lösa dem är följande.

Problem 1: Rapportdesigner startar inte när du väljer **ny** eller **Redigera**.

* I Internet Explorer, välj **inställningar** och sedan **Internetalternativ**. Välj fliken **säkerhet**. Välj betrodda platser och välj sedan **platser**. I **Lägg till denna webbplats till zon**, ange "\*\.dynamics.com" (utan citattecken) och välj sedan **Lägg till**. 
* I Internet Explorer, välj **inställningar** och sedan **Internetalternativ**. Välj fliken **säkerhet**. Välj tillförlitliga platser. Ändra alternativet till i området märkt Säkerhetsnivå för denna zon till **Medel-låg**.
* Inaktivera blockering av popup-fönster i webbläsaren.
* Arbetsstationer måste installera Microsoft .NET ramverk 4.6.2 eller senare. Den här versionen av Microsoft .NET Framework kan hämtas och installeras från [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=53345).
* Om du använder webbläsaren Chrome måste du installera tillägget ClickOnce för att hämta rapportdesignerklienten. Om du använder Chrome i osynligt läge, se då till att tillägget ClickOnce har aktiverats för osynligt läge. Mer information om Chrome ClickOnce-tillägget finns i [Systemkrav för molnbaserad distribution](../../fin-ops-core/fin-ops/get-started/system-requirements.md).
* Om du använder Microsoft Edge med en Chrome-webbläsare behöver du inte installera ett ClickOnce-tillägg för Edge Chromium. Du måste dock aktivera alternativet ClickOnce för att kunna hämta Report Designer-klienten. Om du använder osynligt läge, se då till att tillägget ClickOnce har aktiverats för osynligt läge.
     1. Öppna en ny webbläsare i Microsoft Edge.
     2. Ange **edge://flags** och välj **Retur**.
     3. Sök efter alternativet **ClickOnce Support** eller använd denna direktlänk: **edge://flags/#edge-click-once**.
     4. Ställ in menyalternativet på **aktiverad**.
     5. Välj **starta om webbläsare**.

Problem 2: användaren har inte tilldelats de behörigheter som krävs för att använda Financial Reporting. 

* Om du vill kontrollera att användaren saknar behörighet väljer du **Ja** vid felet "det går inte att ansluta till Financial Reporting-servern. Välj Ja om du vill fortsätta och ange en annan serveradress." Välj sedan **Testanslutning**. Om du inte har behörighet visas ett meddelande om att anslutningsförsöket misslyckades. Användaren har inte den behörighet som krävs för att ansluta till servern. Kontakta systemadministratören.
* De behörigheter som krävs visas ovan i [beviljande av säkerhetsåtkomst till Financial Reporting](#granting-security-access-to-financial-reporting). Säkerheten i Financial Reporting baseras på dessa behörigheter. Du får inte åtkomst om inte dessa privilegier (eller någon annan säkerhetsroll som omfattar dessa privilegier) tilldelas dig. 
* Integreringsuppgift **Företagets användarleverantör till företaget** (som också ansvarar för och kallas användarintegration) körs med ett 5-minuters intervall. Det kan ta upp till 10 minuter innan alla behörighetsändringar börjar gälla i Financial Reporting. 
  Om en annan användare kan öppna rapportdesigner, väljer du **verktyg** och väljer **integrationsstatus**. Kontrollera att integrationskartan, "Företagets användarleverantör till företaget", har körts korrekt eftersom du tilldelades behörighet att använda Financial Reporting. 
* Det kan vara möjligt att ett annat fel har hindrat **Dynamics-användare till den Financial Reporting användarintegration** från att slutföras. Det kan också hända att en återställning av datamart har initierats och ännu inte slutförts, eller att ett annat systemfel har inträffat. Försök köra processen igen senare. Kontakta systemadministratören om problemet kvarstår.

Problem 3: du kan gå vidare till sidan logga in rapport i ClickOnce rapportdesigner, men du kan inte slutföra inloggningen i rapportdesigner. 

* Den tid som anges på din lokala dator när du anger dina inloggningsuppgifter måste ligga inom fem minuter efter tiden på den Financial Reporting-servern. Om det finns en skillnad på mer än fem minuter kommer systemet inte att tillåta inloggning. 
* I det här fallet rekommenderar vi att du aktiverar Windows-alternativet för att ställa in datorns tid automatiskt. 

## <a name="additional-resources"></a>Ytterligare resurser
- [Visa ekonomiska rapporter](view-financial-reports.md)
- [Rapportträddefinitioner i ekonomiska rapporter](../../fin-ops-core/dev-itpro/analytics/financial-reporting-tree-definitions.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]