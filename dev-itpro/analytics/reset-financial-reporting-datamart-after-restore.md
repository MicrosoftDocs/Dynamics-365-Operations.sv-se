---
title: "Återställa datamart med ekonomisk rapportering när du återställer en databas"
description: "Det här avsnittet beskriver hur du återställer datamart med ekonomisk rapportering när du har återställt en Microsoft Dynamics 365 for Finance and Operations-databas."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: shylaw
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 261824
ms.assetid: d0784b2c-fe10-428d-8d07-fd474ca50fcc
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-11-30T00:00:00.000Z
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: c132c04bc64f02201252f03830d3f8309306f19c
ms.contentlocale: sv-se
ms.lasthandoff: 06/13/2017

---

# <a name="reset-the-financial-reporting-data-mart-after-restoring-a-database"></a>Återställa datamart med ekonomisk rapportering när du återställer en databas

[!include[banner](../includes/banner.md)]


Det här avsnittet beskriver hur du återställer datamart med ekonomisk rapportering när du har återställt en Microsoft Dynamics 365 for Finance and Operations-databas. 

Det finns flera olika scenarier då du kan behöva återställa Finance and Operations-databasen från en säkerhetskopia eller kopiera databasen från en annan miljö. I så fall måste du också vidta lämpliga åtgärder för att säkerställa att datamart med ekonomiska rapporter är korrekt med hjälp av den återställda Finance and Operations-databasen. Om du har frågor om att återställa datamart med ekonomisk rapportering av skäl utanför återställning av en Finance and Operations-databas, läs [Återställa Management Reporter-datamart](https://blogs.msdn.microsoft.com/dynamics_financial_reporting/2016/06/28/resetting-the-management-reporter-data-mart/) för mer information. Observera att stegen i processen stöds för Dynamics 365 for Operations maj 2016-versionen (programversion 7.0.1265.23014 och ekonomisk rapportering version 7.0.10000.4) och senare versioner. Om du har en tidigare version av Finance and Operations, kontakta vårt supportteam för hjälp.

## <a name="export-report-definitions"></a>Exportera rapportdefinitioner
Först exporterar du de rapportdesigner som finns i rapportdesignern på följande sätt:

1.  I Report Designer, gå till **Företag** &gt; **Grupper för byggblock**.
2.  Välj den grupp med byggblock som du vill exportera och klicka på **Exportera**. **Anmärkning:** För Finance and Operations stöds bara en byggblocksgrupp, **Standard**.
3.  Välj de rapportdefinitioner som ska exporteras:
    -   Klicka på **Markera alla** om du vill exportera alla dina rapportdefinitioner och de associerade byggblocken.
    -   Om du vill exportera specifika rapporter, rader, kolumner, träd eller dimensionsuppsättningar klickar du på lämpliga flikar och väljer de artiklar du vill exportera. Tryck och håll ned CTRL-knappen om du vill välja flera artiklar på en flik. När du väljer rapporter att exportera, väljer du även associerade rader, kolumner, träd och dimensionsuppsättningar.

4.  Klicka på **Exportera**.
5.  Ange ett filnamn och välj en säker plats där du vill spara de exporterade rapportdefinitionerna.
6.  Klicka på **Spara**.

Filen kan kopieras eller laddas upp till en säker plats, vilket gör det möjligt att importera den till en annan miljö vid ett senare tillfälle. Information om hur du använder ett Microsoft Azure-lagringskonto finns i [Överföra data med verktyget kommandoradsverktyget AzCopy](https://docs.microsoft.com/en-gb/azure/storage/storage-use-azcopy). 
> [!NOTE]
> Microsoft tillhandahåller inget lagringskonto som en del av ditt Finance and Operations-avtal. Du måste antingen köpa ett konto för lagring eller använda ett lagringskonto från en separat Azure-prenumeration. 
> [!WARNING]
> Var medveten om hur enheten D fungerar på virtuella Azure-datorer. Förvara inte de exporterade byggblocksgrupperna här permanent. Mer information om tillfälliga enheter finns i [Förstå den tillfälliga enheten på virtuella Windows Azure-datorer](https://blogs.msdn.microsoft.com/mast/2013/12/06/understanding-the-temporary-drive-on-windows-azure-virtual-machines/).

## <a name="stop-services"></a>Stoppa tjänster
Använda fjärrskrivbordet för att ansluta till alla datorer i miljön och stoppa följande tjänster för Windows via services.msc:

-   World wide web publishing service (gäller alla AOS-datorer)
-   Microsoft Dynamics 365 for Finance and Operations Batch Management Service (endast icke-privata AOS-datorer)
-   Management Reporter 2012 processtjänst (endast på BI-datorer)

Tjänsterna har öppna anslutningar till Finance and Operations-databasen.

## <a name="reset"></a>Återställ
#### <a name="locate-the-latest-dataupgradezip-package"></a>Leta reda på det senaste DataUpgrade.zip-paketet

Leta reda på det senaste DataUpgrade.zip-paketet med hjälp av instruktionerna i [Hämta skriptet DataUpgrade.zip](..\migration-upgrade\upgrade-data-to-latest-update.md). Instruktionerna förklarar hur du hittar rätt version av datauppgraderingspaketet för din miljö.

#### <a name="execute-scripts-against-finance-and-operations-database"></a>Köra skript mot Finance and Operations-databasen

Kör följande skript mot Finance and Operations-databasen (inte mot finansiella rapporteringsdatabasen).

-   DataUpgrade.zip\\AosService\\Scripts\\ConfigureAxReportingIntegration.sql
-   DataUpgrade.zip\\AosService\\Scripts\\GrantAzViewChangeTracking.sql

Dessa skript ser till att inställningar för användare, roller och ändringsspårning är korrekta.

#### <a name="execute-powershell-command-to-reset-database"></a>Köra PowerShell-kommando för att återställa databasen

Kör följande kommando direkt på AOS-datorn för att återställa integrationen mellan Finance and Operations och ekonomisk rapportering:

1.  Öppna Windows PowerShell som administratör.
2.  Kör: F:
3.  Kör: cd F:\\MRApplicationService\\MRInstallDirectory
4.  Kör: Importera-Modul .\\Server\\MRDeploy\\MRDeploy.psd1
5.  Kör: Reset-DatamartIntegration -Reason OTHER -ReasonDetail “&lt;min orsak till att återställa&gt;”
    -   Du uppmanas att ange "Y" för att bekräfta.

Beskrivning av parametrarna:

-   Giltiga värden för -Reason är: SERVICING, BADDATA, OTHER.
-   Parametern -ReasonDetail är fritext.
-   Reason och reasonDetail registreras övervaka telemetri/miljö-övervakning.

## <a name="start-services"></a>Starta tjänster
Använd services.msc för att starta om tjänsterna som du tidigare har stoppat:

-   World wide web publishing service (gäller alla AOS-datorer)
-   Microsoft Dynamics 365 for Finance and Operations Batch Management Service (endast icke-privata AOS-datorer)
-   Management Reporter 2012 processtjänst (endast på BI-datorer)

## <a name="import-report-definitions"></a>Importera rapportdefinitioner
Importera dina rapportdesigner från Report Designer med den fil som skapades vid exporten:

1.  I Report Designer, gå till **Företag** &gt; **Grupper för byggblock**.
2.  Välj den grupp med byggblock som du vill exportera och klicka på **Exportera**. 
    > [!NOTE]
    > För Finance and Operations stöds bara en byggblocksgrupp, **Standard**.
3.  Välj byggblocket **Standard** och klicka på **Importera**.
4.  Välj filen som innehåller de exporterade rapportdefinitionerna och klicka på **Öppna**.
5.  I dialogrutan Importera väljer du de rapportdefinitioner som du vill importera:
    -   Klicka på **Markera alla** om du vill importera alla rapportdefinitioner och stödjande byggblock.
    -   Om du vill importera specifika rapporter väljer du de rader, kolumner, träd eller dimensionsuppsättningar som ska importeras.

6.  Klicka på **Importera**.





