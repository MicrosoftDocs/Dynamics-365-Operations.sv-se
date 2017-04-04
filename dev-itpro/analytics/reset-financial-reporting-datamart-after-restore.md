---
title: "Återställa ekonomisk rapportering dataarkivet när du återställer en databas"
description: "Det här avsnittet beskrivs ekonomisk rapportering dataarkivet återställning när du återställer en Microsoft Dynamics 365 för operationer databas."
author: twheeloc
manager: AnnBe
ms.date: 2016-12-08 16 - 20 - 13
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: Operations, Core
ms.custom: 261824
ms.assetid: d0784b2c-fe10-428d-8d07-fd474ca50fcc
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 4d6cf88788dcc5e982e509137aa444a020137a5e
ms.openlocfilehash: 3967cbb869fbb23d5d7716f619e4c22b4a273921
ms.lasthandoff: 03/29/2017


---

# <a name="reset-the-financial-reporting-data-mart-after-restoring-a-database"></a>Återställa ekonomisk rapportering dataarkivet när du återställer en databas

Det här avsnittet beskrivs ekonomisk rapportering dataarkivet återställning när du återställer en Microsoft Dynamics 365 för operationer databas. 

Det finns flera olika scenarier då du kan behöva återställa Dynamics 365 för operationer databasen från en säkerhetskopia eller kopierar databasen från en annan miljö. I så fall måste du också vidtar du lämpliga åtgärder för att säkerställa att finansiella rapporter dataarkivet korrekt använder återställda Dynamics 365 för operationer databasen. Om du har frågor om att återställa finansiell rapportering dataarkivet av skäl utanför återställer en Dynamics 365 för operationer databasen finns i den [återställer dataarkivet Management Reporter](https://blogs.msdn.microsoft.com/dynamics_financial_reporting/2016/06/28/resetting-the-management-reporter-data-mart/) för mer information. Observera att steg i processen stöds för Dynamics 365 för maj 2016 versionen (build App 7.0.1265.23014 och ekonomisk rapportering build 7.0.10000.4) och senare versioner. Om du har en tidigare version av Dynamics 365 för operationer kan Kontakta supportteamet för hjälp.

## <a name="export-report-definitions"></a>Exportera rapportdefinitioner
Först exportera rapportdesigner i rapportdesign på följande sätt:

1.  Rapportdesign, gå till **företag**&gt;**Byggblocksgrupper**.
2.  Markera gruppen vill exportera och klicka på ett byggblock **exportera**. **Anmärkning:** för Dynamics 365 för operationer kan bara en grupp stöds **standard**.
3.  Välj vilka rapportdefinitionerna ska exporteras:
    -   Klicka på **Markera alla** om du vill exportera alla dina rapportdefinitioner och de associerade byggblocken.
    -   Om du vill exportera specifika rapporter, rader, kolumner, träd eller dimensionsuppsättningar klickar du på lämpliga flikar och väljer de artiklar du vill exportera. Tryck och håll ned CTRL-knappen om du vill välja flera artiklar på en flik. När du väljer att exportera rapporter markeras motsvarande rader, kolumner, träd och dimensionsgrupper.

4.  Klicka på **exportera**.
5.  Ange ett filnamn och välj en säker plats där du vill spara de exporterade rapportdefinitionerna.
6.  Click **Save**.

Filen kan kopieras eller överföras till en säker plats, vilket gör det möjligt att importeras till en annan miljö vid ett senare tillfälle. Information om hur du använder ett konto för Microsoft Azure lagring finns i [med verktyget AzCopy för dataöverföring](https://docs.microsoft.com/en-gb/azure/storage/storage-use-azcopy). **Anmärkning:** Microsoft inte anger ett konto för lagring i Dynamics 365 för operationer. Du måste skaffa ett konto för lagring eller Använd ett konto lagring från en separat prenumeration Azure. **Viktigt:** vara medveten om hur enheten D på Azure virtuella datorer. Förvara inte här grupperna exporterade byggblocket permanent. Mer information om tillfälliga enheter Se [förstå temporärkatalog på Windows Azure virtuella datorer](https://blogs.msdn.microsoft.com/mast/2013/12/06/understanding-the-temporary-drive-on-windows-azure-virtual-machines/).

## <a name="stop-services"></a>Stoppa tjänster
Använda Fjärrskrivbord för att ansluta till alla datorer i miljön och stoppar följande tjänster för Windows via services.msc:

-   World wide web publishing service (gäller alla AOS-datorer)
-   Microsoft Dynamics 365 för operationer Batch Management (endast icke-privata AOS-datorer)
-   Management Reporter 2012 Processtjänst (på BI-datorer)

Tjänsterna har öppna anslutningar till Dynamics 365 för operationer databas.

## <a name="reset"></a>Återställ
#### <a name="locate-the-latest-dataupgradezip-package"></a>Leta reda på det senaste DataUpgrade.zip-paketet

Leta reda på den senaste DataUpgrade.zip paket med hjälp av instruktionerna i [hämtar skriptet DataUpgrade.zip](..\migration-upgrade\upgrade-data-to-latest-update.md). Instruktionerna förklarar hur du hittar rätt version av datapaket uppgradering för din miljö.

#### <a name="execute-scripts-against-dynamics-365-for-operations-database"></a>Köra skript för databasen åtgärder mot Dynamics 365

Kör följande skript mot Dynamics 365 för operationer databasen (inte mot finansiella rapporteringsdatabasen).

-   DataUpgrade.zip\\AosService\\skript\\ConfigureAxReportingIntegration.sql
-   DataUpgrade.zip\\AosService\\skript\\GrantAzViewChangeTracking.sql

Dessa skript Se till att användare, roller och spårning inställningar är korrekta.

#### <a name="execute-powershell-command-to-reset-database"></a>Köra PowerShell-kommando för att återställa databasen

Kör följande kommando på AOS-datorn och återställa integrationen mellan Dynamics 365 för operationer och ekonomisk rapportering:

1.  Öppna Windows PowerShell som administratör.
2.  Kör: F:
3.  Kör: cd F:\\MRApplicationService\\MRInstallDirectory
4.  Kör: Import-Module. \\Server\\MRDeploy\\MRDeploy.psd1
5.  Kör: Återställ-DatamartIntegration-OTHER orsak - ReasonDetail "&lt;Mina orsaken till att återställa&gt;"
    -   Du uppmanas att ange "Y" för att bekräfta.

Beskrivning av parametrarna:

-   Giltiga värden för – orsaken är: Underhåll, BADDATA, andra.
-   ReasonDetail - parametern är fri text.
-   Orsak och reasonDetail registreras övervaka telemetri-miljö.

## <a name="start-services"></a>Starta tjänster
Använd services.msc starta om tjänsterna som du tidigare har stoppats:

-   World wide web publishing service (gäller alla AOS-datorer)
-   Microsoft Dynamics 365 för operationer Batch Management (endast icke-privata AOS-datorer)
-   Management Reporter 2012 Processtjänst (på BI-datorer)

## <a name="import-report-definitions"></a>Importera rapportdefinitioner
Importera dina rapportdesigner från Rapportdesign använder filen under exporten:

1.  Rapportdesign, gå till **företag**&gt;**Byggblocksgrupper**.
2.  Markera gruppen vill exportera och klicka på ett byggblock **exportera**. **Anmärkning:** för Dynamics 365 för operationer kan bara en grupp stöds **standard**.
3.  Välj den **standard** uppbyggnad och klicka **Import**.
4.  Markera den fil som innehåller exporterade rapportdefinitioner och på **öppna**.
5.  I dialogrutan Importera väljer du de rapportdefinitioner som du vill importera:
    -   Klicka på **Markera alla** om du vill importera alla rapportdefinitioner och stödjande byggblock.
    -   Om du vill importera specifika rapporter väljer du de rader, kolumner, träd eller dimensionsuppsättningar som ska importeras.

6.  Click **Import**.



