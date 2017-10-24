---
title: "Återställa datamart med ekonomisk rapportering när du återställer en databas"
description: "Det här avsnittet beskriver hur du återställer datamart med ekonomisk rapportering när du har återställt en Microsoft Dynamics 365 for Finance and Operations-databas."
author: ShylaThompson
manager: AnnBe
ms.date: 08/15/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: shylaw
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 261824
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 47e70cb1291e390b42b7feff844b2aca141f09b7
ms.openlocfilehash: 200b1a03a0ea95ec2d75850f9a8aebda966e38d6
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="reset-the-financial-reporting-data-mart-after-restoring-a-database"></a>Återställa datamart med ekonomisk rapportering när du återställer en databas

[!include[banner](../includes/banner.md)]


Det här avsnittet beskriver hur du återställer datamart med ekonomisk rapportering när du har återställt en Microsoft Dynamics 365 for Finance and Operations-databas.

Om du återställer Finance and Operations-databasen från en säkerhetskopia eller kopierar databasen från en annan miljö måste du följa stegen i det här avsnittet och kontrollera att den ekonomiska rapporteringens datamart använder den återställda Finance and Operations-databasen. 
> [!Note] 
> Stegen i processen stöds för Dynamics 365 for Operations maj 2016-versionen (programversion 7.0.1265.23014 och ekonomisk rapportering version 7.0.10000.4) och senare versioner. Om du har en tidigare version av Finance and Operations, kontakta vårt supportteam för hjälp.

## <a name="export-report-definitions"></a>Exportera rapportdefinitioner
Först exporterar du de rapportdesigner som finns i rapportdesignern på följande sätt:

1.  I Report Designer, gå till **Företag** &gt; **Grupper för byggblock**.
2.  Välj den grupp med byggblock som du vill exportera och klicka på **Exportera**. 

    > [!Note] 
    > För Finance and Operations stöds bara en byggblocksgrupp, **Standard**.
    
3.  Välj de rapportdefinitioner som ska exporteras:
    -   Klicka på **Markera alla** om du vill exportera alla dina rapportdefinitioner och de associerade byggblocken.
    -   Om du vill exportera specifika rapporter, rader, kolumner, träd eller dimensionsuppsättningar klickar du på lämpliga flikar och väljer de artiklar du vill exportera. Håll knappen Ctrl intryckt för att välja flera olika artiklar i en flik. När du väljer vilka rapporter du vill exportera kommer tillhörande rader, kolumner, träd och dimensionsuppsättningar att väljas.

4.  Klicka på **Exportera**.
5.  Ange ett filnamn och välj en säker plats där du vill spara de exporterade rapportdefinitionerna.
6.  Klicka på **Spara**.

Filen kan kopieras eller laddas upp till en säker plats, vilket gör det möjligt att importera den till en annan miljö vid ett senare tillfälle. Information om hur du använder ett Microsoft Azure-lagringskonto finns i [Överföra data med verktyget kommandoradsverktyget AzCopy](/azure/storage/storage-use-azcopy). 
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
### <a name="locate-and-download-the-latest-minorversiondataupgradezip-package"></a>Leta upp och hämta senaste MinorVersionDataUpgrade.zip-paketet

Leta reda på det senaste MinorVersionDataUpgrade-paketet med hjälp av instruktionerna i [Hämta det senaste distributionspaketet för datauppgradering](..\migration-upgrade\upgrade-data-to-latest-update.md#download-the-latest-data-upgrade-deployable-packages). Instruktionerna förklarar hur du hittar och hämtar rätt version av datauppgraderingspaketet. En uppgradering krävs inte för att hämta MinorVersionDataUpgrade.zip-paketet. Du behöver bara utföra åtgärderna i ”Hämta senaste distributionspaketet för datauppgradering” utan att utföra någon av de övriga stegen i artikeln för att hämta en kopia av paketet MinorVersionDataUpgrade.zip.

### <a name="execute-scripts-against-finance-and-operations-database"></a>Köra skript mot Finance and Operations-databasen

Kör följande skript mot Finance and Operations-databasen (inte mot finansiella rapporteringsdatabasen).

-   DataUpgrade.zip\\AosService\\Scripts\\ConfigureAxReportingIntegration.sql
-   DataUpgrade.zip\\AosService\\Scripts\\GrantAzViewChangeTracking.sql

Dessa skript ser till att inställningar för användare, roller och ändringsspårning är korrekta.

### <a name="execute-powershell-command-to-reset-database"></a>Köra PowerShell-kommando för att återställa databasen

Kör följande kommandon på AOS-datorn i PowerShell eller som administratör om du vill återställa integreringen mellan Finance and Operations och finansiell rapportering:

```
F:
cd F:\MRApplicationService\MRInstallDirectory
Import-Module .\Server\MRDeploy\MRDeploy.psd1
Reset-DatamartIntegration -Reason OTHER -ReasonDetail “<my reason for resetting>”

```
> [!NOTE]
> När du har kört kommandona kommer du att ombedjas trycka på "Y" för att bekräfta.

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





