---
title: Borttagna eller utfasade funktioner i tidigare versioner
description: I det här ämnet beskrivs funktioner som har tagits bort, eller som planerats för borttagning från Dynamics 365 for Finance and Operations och tidigare versioner.
author: sericks007
ms.date: 02/16/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.custom: 21821
ms.assetid: 31019808-4cbf-47d7-b1ba-d791db4281ae
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 76ac50ba2606ffff5a5a90d29ca99c8d67e5f14cce2127f5de6225d1cd8224ef
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6745186"
---
# <a name="removed-or-deprecated-features-in-previous-releases"></a>Borttagna eller utfasade funktioner i tidigare versioner

[!include [banner](../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

> [!IMPORTANT]
> Det här avsnittet uppdateras inte längre. Om du vill visa en aktuell lista över funktioner som har tagits bort från Finance and Operations-appar kan du söka efter innehållet **"borttagna eller gamla funktioner"** som hör till det program du använder.

I det här ämnet beskrivs funktioner som har tagits bort eller utfasat från Dynamics 365 for Finance and Operations och tidigare versioner av produkten.

- En *borttagen* funktion är inte längre tillgänglig i produkten.
- En *borttagen* funktion är inte i aktiv utveckling och kan tas bort i en kommande uppdatering.

Den här listan är avsedd att hjälpa dig att ta hänsyn till dessa borttagna och inaktuella funktioner för din planerings skull. 

Detaljerad information om objekt i Finance and Operations-appar hittas i [Tekniska referensrapporter](/dynamics/s-e/global/axtechrefrep_61). Du kan jämföra olika versioner av rapporterna för mer information om objekt som har ändrats eller tagits bort i varje version av Finance and Operations-appar.

## <a name="finance-1007-with-platform-update-31"></a>Finans 10.0.7 med plattformsuppdatering 31

### <a name="chinese-voucher-types-without-account-groups-selection"></a>Typer av kinesiska verifikationer utan kontogruppsval
|&nbsp;   | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Ändras till funktionen med kontogruppsurval. |
| **Ersatt av en annan funktion?**   | Ja |
| **Produktområden som påverkas**         | Ansökning |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | Föråldrad: 1 december 2020, planerar att inte längre stödja inställningar för kinesiska verifikationstyper utan kontogruppsval. Hitta mer information om den nya funktionsdesignen i vad som är nytt i 10.0.7 |

## <a name="finance-and-operations-1006-with-platform-update-30"></a>Finance and Operations 10.0.6 med plattformsuppdatering 30


### <a name="dimensionhashgethashstr-_message"></a>DimensionHash.getHash(str _message)

|&nbsp;   | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Windows använder inte SHA1, enligt dokumenterad i [Windows tvingande SHA1-certifikat](https://social.technet.microsoft.com/wiki/contents/articles/32288.windows-enforcement-of-sha1-certificates.aspx).  |
| **Ersatt av en annan funktion?**   | Ja |
| **Produktområden som påverkas**         | Ansökning |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | Inaktuell: från den 1 april 2020 måste utvecklare använda de plattforms-API:er som finns i klassen **HasFunction**. |

### <a name="hashcomputesha1hashstring-message"></a>Hash.ComputeSHA1Hash(srängmeddelande)

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Windows använder inte SHA1, enligt dokumenterad i [Windows tvingande SHA1-certifikat](https://social.technet.microsoft.com/wiki/contents/articles/32288.windows-enforcement-of-sha1-certificates.aspx).  |
| **Ersatt av en annan funktion?**   | Ja |
| **Produktområden som påverkas**         | Plattform |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | Inaktuell: från den 1 april 2020 måste utvecklare använda de plattforms-API:er som finns i klassen **HasFunction**. |


### <a name="formdatetimecontrolsetutcstring"></a>FormDateTimeControl.setUtcString()

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Vi tar bort **setUtcString()**-metoden eftersom det finns en bättre ersättningsmetod. |
| **Ersatt av en annan funktion?**   | Ja |
| **Produktområden som påverkas**         | Plattform |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | Inaktuell: 1 oktober 2020, men vi planerar inte längre att använda metoden **setUtcString()**. Utvecklare bör använda metoden **setUtcDateTime()** i stället. |

### <a name="blacklist-report-it--feature-reference-it-00001"></a>Rapport för svarta listan (IT) – funktionsreferens IT-00001

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Krävs inte enligt lag. |
| **Ersatt av en annan funktion?**   | Nej |
| **Produktområden som påverkas**         | Italiensk lokalisering |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | Inaktuell: Från och med den 1 oktober 2020 planerar vi att inte längre ge support för denna rapport. |

### <a name="domestic-tax-report--feature-reference-it-00003"></a>Inhemsk momsrapport – funktionsreferens IT-00003

| &nbsp;  |&nbsp;  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Krävs inte enligt lag. |
| **Ersatt av en annan funktion?**   | Nej |
| **Produktområden som påverkas**         | Italiensk lokalisering |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | Inaktuell: 1 oktober 2020, men vi planerar inte längre att stödja **Inhemsk momsrapport – funktionsreferens IT-00003**. |

## <a name="october-2019-deprecation-announcement"></a>Oktober 2019 avskrivningsmeddelande

### <a name="flowchart-diagrams-in-business-process-modeler"></a>Flödesschemadiagram i affärsprocessmodelleraren

<table>
<tbody>
<tr>
<td><strong>Orsak till inaktuell/borttagning</strong></td>
<td>Vi använder inte komponenten flödesschema i Affärsprocessmodelleraren (BPM), eftersom äldre designen orsakade låg användning.</td>
</tr>
<tr>
<td><strong>Ersatt av en annan funktion?</strong></td>
<td>Nej</td>
</tr>
<tr>
<td><strong>Områden som påverkas</strong></td>
<td>Affärsprocessmodelleraren</td>
</tr>
<tr>
<td><strong>Status</strong></td>
<td>Inaktuell: komponenten flödesschema i BPM förväntas tas bort år 2020. Följande funktion kommer att bli otillgänglig:
<ul>
<li>Alla flödesscheman blir skrivskyddade och kan inte redigeras. Formegenskaperna som är kopplade till flödesscheman kommer heller inte att vara tillgängliga. Dessa flödesscheman innehåller både standardflödesscheman som genereras automatiskt och anpassade flödesscheman som ändras baserat på dessa standard flödesscheman.</li>
<li>Processteg blir skrivskyddade och kan inte redigeras.</li>     
<li>Den inaktuella funktionen Bristanalys kommer inte att vara tillgänglig. Därför skapas ingen lista över luckor automatiskt eller tillgänglig för export.
<p><strong>Obs!</strong> Den här funktionen hade tidigare ersatts av Microsoft Azure DevOps-integreringar.</p>
</li>
<li>Versionshistoriken för flödesschemat kommer inte att vara tillgänglig.</li>
</ul>
</td>
</tr>
</tbody>
</table>

## <a name="finance-and-operations-1005-with-platform-update-29"></a>Finance and Operations 10.0.5 med plattformsuppdatering 29

### <a name="us-payroll-tax-updates"></a>Uppdateringar amerikansk löneskatt

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Vi drar tillbaka skatteuppdateringar för den amerikanska lönefunktionen på grund av låg användning och förbättrade funktioner som nu erbjuds via strategiska integrationer.  |
| **Ersatt av en annan funktion?**   | Ja |
| **Produktområden som påverkas**         | Payroll |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | Föråldrad: 31 juli 2024 planerar vi att inte längre tillhandahålla momsuppdateringar för amerikanska lönekunder. Funktionaliteten kommer att finnas kvar i produkten, men förbättringar kommer inte längre att hålla funktionaliteten uppdaterad och eventuella produktfel kommer att utvärderas från fall till fall. |

>[!NOTE]
> Detta representerar en ändring från det ursprungliga annulleringsdatumet den 1 oktober 2021. Mer information finns i [Momsuppdateringar som dras tillbaka för funktionen amerikansk lönelista i Microsoft Dynamics 365 for Finance and Operations](https://aka.ms/financepayrollfaq).


### <a name="data-management-staging-clean-up"></a>Rensa mellanlagring av datahantering
|&nbsp;   | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Uppfyller inte de grundläggande kraven som behövs för schemaläggning av periodisk rensning. |
| **Ersatt av en annan funktion?**   | Ja, funktionen för rensning av jobbhistorik läggs till för att uppfylla scenarierna holistiskt. |
| **Produktområden som påverkas**         | Datahantering |
| **Distribueringsalternativ**              | Allt  |
| **Status**                         | Inaktuell: Måltidsramen för att ta bort funktioner är december 2020. |

## <a name="finance-and-operations-1004-with-platform-update-28"></a>Finance and Operations 10.0.4 med plattformsuppdatering 28

### <a name="france-fec-accounting-data-export-in-xml"></a>Frankrike: FEC-redovisningsdataexport i XML-format

|  &nbsp; |&nbsp;  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Ersatt av TXT-format, **fransk FEC gransk** är tillgänglig via **redovisning** \> **periodiska uppgifter** \> **dataexport**.
| **Ersatt av en annan funktion?**   | Ja |
| **Produktområden som påverkas**         | Redovisning |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | Inaktuell. Måltidsramen för att ta bort funktioner är juli 2020. |


### <a name="legacy-navigation-bar"></a>Äldre navigeringsfält

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Justering av rubrik med andra Dynamics- och Office-produkter. Mer information finns i [uppdaterat navigeringsfält som justeras mot Office-rubriken.](/business-applications-release-notes/April19/dynamics365-finance-operations/updatednavbar)
| **Ersatt av en annan funktion?**   | Från och med plattformsuppdatering 24, ett omformaterat navigeringsfält med sökfunktionen införd. |
| **Produktområden som påverkas**         | Webbklient |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | Föråldrade: det äldre navigeringsfältet kommer inte längre att vara tillgängligt från och med april 2020. Till den punkten kan kunderna återgå till det äldre navigeringsfältet via sidan **Alternativ för kundprestanda**. |


## <a name="finance-and-operations-1002-with-platform-update-26"></a>Finance and Operations 10.0.2 med plattformsuppdatering 26


### <a name="legacy-default-action-behavior"></a>Äldre standardbeteende för åtgärd

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Äldre standardbeteende för åtgärd i rutnät resulterar i en oväntad kolumn med standardåtgärdslänken efter att rutnätskolumner har beställts om via anpassning. Den nya tröga standardåtgärdsfunktionen korrigerar detta. Mer information finns i [Tröga standardåtgärder i rutnät](/business-applications-release-notes/October18/dynamics365-finance-operations/sticky-default-action). |
| **Ersatt av en annan funktion?**   | Med start i plattformsuppdatering 21 infördes en funktion för ”tröga standardåtgärder”. Den här funktionen kan aktiveras på sidan **Prestandaalternativ för klient**. |
| **Produktområden som påverkas**         | Rutnät i webbklienten |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | Inaktuell: Från och med april 2020 blir tröga standardåtgärder standardbeteendet, utan en mekanism för att återgå till äldre funktion. |

### <a name="legacy-is-one-of-filtering-experience"></a>Äldre "är någon av" filtreringsupplevelsen

|&nbsp;   | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Filtreringsupplevelsen ”är någon av” har gått igenom en ny utformning av plattformsuppdatering 22, med planen att så småningom blir den enda ”är någon av”-filtreringsupplevelsen. |
| **Ersatt av en annan funktion?**   | Med start i plattformsuppdatering 22, är en förbättrad ”är någon av”-filtreringserfarenhet tillgänglig på sidan **Prestandaalternativ för klient**. För mer information, se [Optimerad "är någon av" filtreringsupplevelse](/business-applications-release-notes/October18/dynamics365-finance-operations/improved-isoneof-filtering). |
| **Produktområden som påverkas**         | Webbklient |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | Inaktuell: Från och med april 2020 blir den förbättrade "är någon av"-upplevelsen standardbeteendet, utan en mekanism för att återgå till äldre funktion. |

### <a name="parameter-to-enable-sales-orders-with-multiple-project-contract-funding-sources"></a>Parametern för att aktivera försäljningsorder med flera finansieringskällor för projektkontrakt
Stöd för att skapa projektbaserade försäljningsorder där projektkontraktet har flera finansieringskällor aktiveras med inställningen **Parametrar för projekthantering** **Tillåt försäljningsorder för projekt som har flera finansieringskällor**. Den här parametern är som standard inte aktiverat. 

| &nbsp;  |&nbsp;  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Funktionen kommer alltid att aktiveras alltid när den här parametern har tagits bort. |
| **Ersatt av en annan funktion?**   | Nr. Funktionen för att stödja projektbaserade försäljningsorder med flera finansieringskällor alltid aktiverade.   |
| **Produktområden som påverkas**         |Parametern **Tillåt försäljningsorder för projekt som har flera finansieringskällor** kommer att tas bort. Följande metoder ändras när parametern tas bort: metoden **ctrlSalesOrderTable** i klassen **ProjStatusType**, metoden **validera** för fältet **ProjId** och **kör** metoden i formuläret **SalescreateOrder**. Följande metoder ska vara inaktuell när parametern tas bort: **IsSalesOrderAllowedForMultipleFundingSources** i registerfilen **ProjTable**, metoden **IsAllowSalesOrdersForMultipleFundingSourcesParamEnabled** i registerfilen **ProjTable**, datafältet **AllowSalesOrdersForMultipleFundingSources** i formuläret **ProjParameters** och filerna **ProjParameterEntity**, privat metod **IsAssociatedToMultipleFundingSourcesContract** i regsiterfilen **ProjTable**. |
| **Distribueringsalternativ**              | Allt  |
| **Status**                         | Avskrivning planeras för släpp av påfyllnad, april 2020. |

### <a name="legacy-workflow-reports-for-tracking-and-instance-status"></a>Äldre arbetsflödesrapporter för spårning och instansstatus

|  &nbsp; | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Äldre arbetsflödesrapporter för spårning och instansstatus utfasas eftersom de inte längre refereras från navigeringsrutan. Rapportnamn är WorkflowWorkflowInstanceByStatusReport och WorkflowWorkflowTrackingReport. |
| **Ersatt av en annan funktion?**   | Du kan använda formuläret arbetsflödeshistorik i stället. |
| **Produktområden som påverkas**         | Webbklient |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | Inaktuell: Måltidsramen för att ta bort funktioner är april 2020. |

## <a name="finance-and-operations-1001-with-platform-update-25"></a>Finance and Operations 10.0.1 med plattformsuppdatering 25

### <a name="deprecated-apis-and-potential-breaking-changes"></a>Gamla API:er och eventuell uppdelning av ändringar


#### <a name="deriving-from-internal-classes-is-deprecated"></a>Som härrör från interna klasser är inaktuella

| &nbsp;  |&nbsp;  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Före plattformsuppdatering 25 var det möjligt att skapa en klass eller tabell som härleds från en intern klass/tabell som definieras i ett annat paket/modul. Detta är inte en säker metod för kodning. Per plattformsuppdatering 25 kommer kompileraren att visa ett varningsmeddelande. |
| **Ersatt av en annan funktion?**   | Kompilerarens varning ersätts av ett fel i plattformsuppdatering 26. Ändringen är bakåtkompatibel vid körning, vilket innebär att om du kör plattformsuppdatering 25 eller senare kan detta distribueras i begränsad eller produktionsmiljö utan att behöva ändra anpassad kod. Denna ändring påverkar endast utveckling och kompileringstid.|
| **Produktområden som påverkas**         | Visual Studio utvecklingsverktyg. |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | Inaktuell – Varningen blir ett kompileringsfel i en kommande plattformsuppdatering 26. |

#### <a name="overriding-internal-methods-is-deprecated"></a>Åsidosätta interna metoder är inaktuellt

| &nbsp;  |&nbsp;  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Före plattformsuppdatering 25 var det möjligt att åsidosätta en intern metod i en härledd klass som definieras i ett annat paket/modul. Detta är inte en säker metod för kodning. Per plattformsuppdatering 25 kommer kompileraren att visa ett varningsmeddelande. |
| **Ersatt av en annan funktion?**   | Denna varning ersätts av ett kompileringsfel i plattformsuppdatering 26. Ändringen är bakåtkompatibel vid körning, vilket innebär att om du kör plattformsuppdatering 25 eller senare kan detta distribueras i begränsad eller produktionsmiljö utan att behöva ändra anpassad kod. Denna ändring påverkar endast utveckling och kompileringstid. |
| **Produktområden som påverkas**         | Visual Studio utvecklingsverktyg. |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | Inaktuell – Varningen blir ett kompileringsfel i en kommande plattformsuppdatering 26. |

## <a name="finance-and-operations-1000-with-platform-update-24"></a>Finance and Operations 10.0.0 med plattformsuppdatering 24

### <a name="renaming-released-products"></a>Ändra namn på frisläppta produkter 
| &nbsp;  |&nbsp;  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | När du använder funktionen **Byt namn på primär nyckel** för att ändra ItemId för en frisläppt produkt, uppdateras endast direkta referenser till sekundärnycklar. Alla andra referenser till den frisläppta produkten, t.ex. från produktionsorder, behåller det gamla ItemId. Detta kan leda till inkonsekventa data som kommer att blockera affärsprocesser. |
| **Ersatt av en annan funktion?**   | Nr. |
| **Produktområden som påverkas**         | Produktinformationshantering |
| **Distribueringsalternativ**              | Allt  |
| **Status**                         | Tas bort från Finance and Operations 10.0.0 med plattformsuppdatering 24.|


## <a name="finance-and-operations-813-with-platform-update-23"></a>Finance and Operations 8.1.3 med plattformsuppdatering 23

### <a name="sql-server-reporting-services-reportviewer-control"></a>SQL Server Reporting Services ReportViewer-kontroll
Användare kan använda åtgärden **Exportera** från den inbäddade SQL Server Reporting Services (SSRS) ReportViewe-kontrollen för att hämta dokument som skapas av Finance and Operations-programmen. Denna HTML-baserade presentationen av rapporten ger användare en onumrerad förhandsgranskning av dokumentet.

| &nbsp;  |&nbsp;  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | HTML-baserade förhandsgranskningserfarenhetens onumrerade natur levererar **inte** återgivning med det fysiska dokumentet som slutligen skapats av Finance and Operations. Genom att helt använda PDF som standardformat för affärsdokument, ska användare kunna dra nytta av en modern tittarupplevelse med förbättrad prestanda när programrapporter produceras. |
| **Ersatt av en annan funktion?**   | Framöver kommer PDF-dokument att vara standardformatet för rapporter som återges av Finance and Operations.   |
| **Produktområden som påverkas**         | Ändringen påverkar **inte** kundscenarier där rapporter distribueras elektroniskt eller skickas direkt till en skrivare.    |
| **Distribueringsalternativ**              | Allt  |
| **Status**                         | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen. Funktionen för att automatiskt förhandsgranska programrapporter med en inbäddad PDF-läsare planeras för maj 2019 plattformsuppdateringen. |

### <a name="client-kpi-controls"></a>Klien-KPI-kontroller
Inbäddade KPI:er (Key Performance Indicators) kan utformas i Visual Studio av en utvecklare och ytterligare anpassas av slutanvändaren.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | De originella klientkontrollerna som används för att definiera KPI:er har lågt kundupptag och är beroende av att en utvecklare lägger till spårbara mått. |
| **Ersatt av en annan funktion?**   | PowerBI.com-tjänsten levererar verktyg i världsklass för att definiera och hantera KPI:er baserade på data från externa källor.  I en kommande version låter vi dig bädda in lösningar som finns på PowerBI.com i programmets arbetsytor.   |
| **Produktområden som påverkas**         | Uppdateringen förhindrar att utvecklare inför nya KPI-kontroller i Visual Studio designer.    |
| **Distribueringsalternativ**              | Allt  |
| **Status**                         | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen. |

### <a name="deprecated-apis-and-future-breaking-changes"></a>Gamla API:er och framtida uppdelning av ändringar

#### <a name="field-groups-containing-invalid-field-references"></a>Fältgrupper innehåller ogiltiga fältreferenser

| &nbsp;  |&nbsp;  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Det är möjligt för definitioner av registermetadata att ha fältgrupper som innehåller ogiltiga fältreferenser. Om distribuerad kan det orsaka körningsfel i Ekonomisk rapportering och SQL Server Reporting Services (SSRS). Det här problemet är kategoriserat som en *kompileringsvarning* i stället för ett *fel*, vilket innebär att skapande och distribution av paket som kan distribueras kan fortsätta utan att åtgärda problemet. Åtgärda det här problemet:<br><br>1. Ta bort den ogiltiga fältreferensen från tabellens fältgruppdefinition.<br><br>2. Kompilera om.<br><br>3. Kontrollera att eventuella varningar eller fel åtgärdas. |
| **Ersatt av en annan funktion?**   | Denna varning ersätts av ett kompileringsfel i framtiden. |
| **Produktområden som påverkas**         | Visual Studio utvecklingsverktyg. |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | Inaktuell: varningen är ett kompileringstidsfel med plattformsuppdateringar för version 10.0.11 av Finance and Operations-appar. |

#### <a name="complete-list"></a>Fullständig lista
Du hittar en fullständig lista över API:er som är inaktuella i [Avskrivning av metoder och metadataelement](deprecation-deletion-apis.md).

## <a name="finance-and-operations-81-with-platform-update-20"></a>Finance and Operations 8.1 med plattformsuppdatering 20

### <a name="batch-transfer-rules-for-subledger-journal-account-entries"></a>Batchöverföringsregler för kontoposter i redovisningsjournalen
Det synkrona överföringsläget är inaktuellt i redovisningsparametrarna.  Detta läge ersätts endast av asynkron och schemalagd batch som endast finns som alternativ för överföring. Mer information finns i bloggen [allmänna redovisningsparametrar – Batchöverföringsregler](https://community.dynamics.com/365/financeandoperations/b/financials/archive/2019/03/15/general-ledger-parameters-batch-transfer-rules).

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Vi tar bort det synkrona alternativet på grund av att påverkan av systemets prestanda. |
| **Ersatt av en annan funktion?**   | Asynkron och schemalagd batch är alternativ som ska användas i stället för synkron.   |
| **Produktområden som påverkas**         | Redovisning, Leverantörsreskontra, Kundreskontra, Inköp, Utgift    |
| **Distribueringsalternativ**              | Allt  |
| **Status**                         | Inaktuell: Måltidsramen för att ta bort funktioner är versionen 10.0.|

### <a name="electronic-reporting-for-russia"></a>Elektronisk rapportering för Ryssland
Funktionen för att konfigurera .txt och .xml-format för deklarationer. 

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Ersatt med för elektronisk rapportering. |
| **Ersatt av en annan funktion?**   | Ja. |
| **Produktområden som påverkas**         | Redovisning |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | Tas bort från Finance and Operations 8.1 med plattformsuppdatering 20. |

### <a name="financial-reports-generator-for-russia"></a>Ekonomisk rapportgenerator för Ryssland
Ett verktyg för inställning av datainsamling för redovisning och momsrapporter behövs och exportera data till XLS och DOC-rapportmallar Funktionella delar: exportera data till XLS och DOC rapportmallar, frågor, fasta krav tas bort. 

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Borttagna delar ersätts med elektronisk rapportering. |
| **Ersatt av en annan funktion?**   | Ja. Användargränssnittet för installationen av ekonomirapporter ska användas för att förbereda datainsamlingsregler av huvudbokskonton eller skatteregister. Exportera data till olika filtyper, fasta krav och frågeliknande datainsamlingsregler ska konfigureras i elektronisk rapportering. |
| **Produktområden som påverkas**         | Huvudbok. |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | Tas bort från Finance and Operations 8.1 med plattformsuppdatering 20. |

### <a name="integration-with-external-providers-for-sending-electronic-reporting-through-communication-channels-for-russia"></a>Integration med externa leverantörer för att skicka elektronisk rapportering via kommunikationskanaler för Ryssland
Funktionen exporterar genererade elektroniska filer av deklarationer till mapp för vidare sändning till officiella leverantörer av elektronisk rapportering samt importera tillstånd tillbaka.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Ersatt med konfigurerbara elektroniska meddelanden. |
| **Ersatt av en annan funktion?**   | Ja.  |
| **Produktområden som påverkas**         | Redovisningsuppgifter, skatt |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | Tas bort från Finance and Operations 8.1 med plattformsuppdatering 20. |


### <a name="profit-tax-register-wizard"></a>Guiden för vinstskattregister
Funktion för att skapa mallar för nya vinstskattregister. Den här funktionen skapar X++-objekten för nya register som sedan skapas som mallar med lämplig beräkningslogik tillagd.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Funktionen är inte kompatibel med Finance and Operations utvidgningsmodell. |
| **Ersatt av en annan funktion?**   | Nr |
| **Produktområden som påverkas**         | Skatt |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | Tas bort från Finance and Operations 8.1 med plattformsuppdatering 20. |

### <a name="payroll-and-human-resources-for-russia"></a>Löner och Personal för Ryssland
Rysk landsspecifik modul för hantering av personaladministrationsinformation, tidrapportinformation för anställda, löneredovisning och skapande av löneutdrag. 

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Lön ingår inte i det globala strategiska fokuset i Dynamics 365-portföljen. Partners och ISV:er är bäst placerade för att tillhandahålla lönefunktioner som överensstämmer med lokala regler och skatteuppdateringar.|
| **Ersatt av en annan funktion?**   | Nr|
| **Produktområden som påverkas**         | Hantering av Löner och Personal för Ryssland |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | Inaktuell: Måltidsramen för funktionen som ska tas bort är en av de framtida uppdateringarna av version 10.0. |

## <a name="finance-and-operations-80-with-platform-update-15"></a>Finance and Operations 8.0 med plattformsuppdatering 15
Inga funktioner har tagit bort eller ersatts med den här versionen. Plattformsuppdatering 15 är kumulativ och innehåller nya eller ändrade funktioner från plattformsuppdatering 13, plattformsuppdatering 14 och plattformsuppdatering 15.

## <a name="finance-and-operations-enterprise-edition-73-with-platform-update-12"></a>Finance and Operations, Enterprise edition 7.3 med plattformsuppdatering 12

### <a name="personalized-product-recommendations"></a>Anpassade produktrekommendationer 
Med start den 15 februari 2018 kommer återförsäljare inte längre kunna visa anpassade produktrekommendationer på en butikskassa (POS). Mer information finns i [Översikt över produktrekommendationer](../../../commerce/product-recommendations.md).  

| &nbsp;  |&nbsp;  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Vi tar bort den nuvarande versionen av tjänsten produktrekommendation eftersom vi designar om funktionen med en bättre algoritm och nya butiksorienterade funktioner.  |
| **Ersatt av en annan funktion?**   | Nr. Men vi planerar att återinföra denna funktion senare under 2018 för att ge förbättrat service vid rekommendationer.   |
| **Produktområden som påverkas**         | Anpassade produktrekommendationer i butikskassa.                                                    |
| **Distribueringsalternativ**              | Allt                                                                                      |
| **Status**                         |Borttagen från den 15 februari 2018. Detta påverkar kunder som kör Dynamics 365 for Operations 1611 och senare.  |

### <a name="extension-of-the-list-of-electronic-reporting-er-functions"></a>Utökning av listan över elektronisk rapportering (ER)
Möjligheten att införa anpassade funktioner som ska användas i ER uttrycksverktyget (mer information finns i [utöka listan med elektroniska rapportfunktioner (ER)](../../dev-itpro/analytics/general-electronic-reporting-formulas-list-extension.md)) stöds inte längre. På grund av förändringar av ER API:er, blev API:n för att anropa inbyggda funktioner från ER uttrycksverktyget intern och kan inte längre utökas.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Kodförseglingsinitiativ  |
| **Ersatt av en annan funktion?**   | Ingen. När den nya inbyggda funktionen krävs måste en ny tilläggsbegäran sändas till ER-ramverkets team.<br><br>Som en tillfällig lösning medan den begärda funktionen är under utveckling av ER-teamet kan logiken som krävs programmeras som en metod för en anpassad programklass. Den här metoden kan användas i ER-uttryck som en egenskap för den tillagda ER-datakällan i typen **Application\Class** som refererar till den anpassade programklassen.  |
| **Produktområden som påverkas**         | Elektroniskt rapporteringsramverk                                                      |
| **Distribueringsalternativ**              | Allt                                                                                      |
| **Status**                         | Tas bort från Finance and Operations, Enterprise edition 7.3.    |

### <a name="inventory-by-item-group-and-inventory-by-inventory-dimension-aging-reports"></a>Lager per artikelgrupp och Lager per åldersfördelningsrapport för lagerdimension 

Dessa två rapporter stöds inte längre i Finance and Operations. I stället kan rapporten **Lagerföråldring** användas för att förbättra användarupplevelsen.

| &nbsp;  | &nbsp; |
|--------------|-----------------------|
| **Orsak till avskrivning**       | Dubblettfunktion  |
| **Ersatt av en annan funktion?** | Ja. De två rapporterna har ersatts av rapporten **Lagerföråldring**.     |
| **Produktområden som påverkas**       | Lagerhantering, kostnadshantering        |
| **Distribueringsalternativ**        | Allt|
| **Status**                       | Inaktuell: Menyalternativen för de två rapporterna har tagits bort i version 7.3. Koden för rapporterna finns emellertid kvar i produkten Planen är att ta bort koden i framtida versioner. |

### <a name="power-bi-content-packs-available-on-appsource"></a>Power BI-innehållspaket finns på AppSource
Innehållspaketen **Kostnadshantering**, **Ekonomiska resultat** och **Retail Channel Performance** som publicerades på webbplatsen [Microsoft AppSource](https://appsource.microsoft.com), är inaktuella till följd av produktuppdateringar i Microsoft Power BI. Systemadministrationsformulär som brukade användas för att distribuera dessa innehållspaket till PowerBI.com används även i Finance and Operations.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Produktuppdateringar Microsoft Power BI. |
| **Ersatt av en annan funktion?**   | Innehållspaketen **Kostnadshantering**, **Ekonomiska resultat** och **Butikskanalresultat** som finns på webbplatsen [AppSource](https://appsource.microsoft.com) ersätts med analytiska applikationer som möjliggör lösningsintegrering på databasnivå. Läs mer om analytiska program i [Inbäddad Power BI i arbetsytor](../../dev-itpro/analytics/embed-power-bi-workspaces.md).    |
| **Produktområden som påverkas**         | Kostnadshantering, Ekonomi och Butik                                                                                               |
| **Distribueringsalternativ**              | Endast molnet (integrering med PowerBI.com stöds inte i lokala distributioner.)                                                                                                            |
| **Status**                         | Inaktuell: Måltidsramen för att ta bort funktioner är K2 2018.    |

### <a name="standard-ui-in-data-management-workspace"></a>Standardgränssnitt i arbetsytan för datahantering

Standardgränssnittet i datahantering är det är äldre användargränssnittet som är det standardanvändargränssnitt som visas för användarna när de besöker arbetsytan för datahantering.

| &nbsp;  | &nbsp; |
|------------------|-------------------------|
| **Orsak till inaktuell/borttagning** | Vi investerar i att ge nya användarupplevelser i det nya användargränssnittet.             |
| **Ersatt av en annan funktion?**   | Det nya användargränssnittet som heter *förbättrade vyer* ersätter det gamla användargränssnittet.            |
| **Produktområden som påverkas**         | Arbetsyta för datahantering                                                     |
| **Distribueringsalternativ**              | Allt                                                                           |
| **Status**                         | Inaktuell: Måltidsramen för att ta bort funktioner är Q2 2018. |

### <a name="excise-sales-tax-service-tax-for-india"></a>Punktskatt, moms, tjänstemoms för Indien

Dessa skatter har infogats till indiska GST.

|  &nbsp;                                           |      &nbsp;                                                                   |
|---------------------------------------------|-------------------------------------------------------------------------|
| **Orsak till inaktuell eller borttagning**       | Dessa skatter har infogats till indiska GST.                          |
| **Ersatt av en annan funktion?**            | Indiska GST                                                              |
| **Produktområden som påverkas**                  | Skatt                                                                     |
| **Distribueringsalternativ**                       | Alla moduler                                                   |
| **Status**                                  | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen. |    

### <a name="file-validation-utility-fvu-for-india"></a>Filvalideringsverktyg (FVU) för Indien

|              &nbsp;                               |      &nbsp;                                                                   |
|---------------------------------------------|-------------------------------------------------------------------------|
| **Orsak till inaktuell eller borttagning**       | Brist på kundanvändning                                                  |
| **Ersatt av en annan funktion?**            | Nr                                                                      |
| **Produktområden som påverkas**                  | Indisk källskatt                                                  |
| **Distribueringsalternativ**                       | Alla moduler                                                                    |
| **Status**                                  | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen.   |        

### <a name="tdstcs-certificate-for-india"></a>TDS/TCS-certifikat för Indien

Användare kan hämta denna från myndighetsportalen.

|             &nbsp;                                |    &nbsp;                                                                     |
|---------------------------------------------|-------------------------------------------------------------------------|
| **Orsak till inaktuell eller borttagning**       | Brist på kundanvändning                                                  |
| **Ersatt av en annan funktion?**            | Nr                                                                      |
| **Produktområden som påverkas**                  | Indisk källskatt                                                  |
| **Distribueringsalternativ**                       | Alla moduler                                                                   |
| **Status**                                  | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen.     |    

### <a name="exportimport-exim-incentive-scheme-for-india"></a>Exportera/importera (EXIM) incitamentsschema för Indien


|              &nbsp;                               |        &nbsp;                                                                 |
|---------------------------------------------|-------------------------------------------------------------------------|
| **Orsak till inaktuell eller borttagning**       | Brist på kundanvändning                                                  |
| **Ersatt av en annan funktion?**            | Nr                                                                      |
| **Produktområden som påverkas**                  | Import och export                                                       |
| **Distribueringsalternativ**                       | Alla moduler                                                                    |
| **Status**                                  | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen.  |    


## <a name="dynamics-365-for-retail-72"></a>Dynamics 365 for Retail 7.2

### <a name="personalized-product-recommendations"></a>Anpassade produktrekommendationer 
Med start den 15 februari 2018 kommer återförsäljare inte längre kunna visa anpassade produktrekommendationer på en butikskassa (POS). Mer information finns i [Översikt över produktrekommendationer](../../../commerce/product-recommendations.md).  

|  &nbsp; |  &nbsp;|
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Vi tar bort den nuvarande versionen av tjänsten produktrekommendation eftersom vi designar om funktionen med en bättre algoritm och nya butiksorienterade funktioner.  |
| **Ersatt av en annan funktion?**   | Nr. Men vi planerar att återinföra denna funktion senare under 2018 för att ge förbättrat service vid rekommendationer.   |
| **Produktområden som påverkas**         | Anpassade produktrekommendationer i butikskassa.                                                    |
| **Distribueringsalternativ**              | Allt                                                                                      |
| **Status**                         |Borttagen från den 15 februari 2018. Detta påverkar kunder som kör Dynamics 365 for Retail 7.2 och senare. |


## <a name="finance-and-operations-enterprise-edition-july-2017-with-platform-update-8"></a>Finance and Operations, Enterprise edition juli 2017 med plattformsuppdatering 8

### <a name="currency-conversion-for-accounting-and-reporting-currencies"></a>Valutakonvertering för redovisnings- och rapporteringsvalutor

Valutakonvertering för redovisnings- och rapporteringsvalutor infördes när euro infördes.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Begränsad användning och tillägg av funktionen Kopiera juridisk person som en ersättning.      |
| **Ersatt av en annan funktion?**   | Nej, men funktionerna Kopiera juridisk person och Konfigurationer har lagts till för att göra det enklare att flytta till ett företag som har förändrade grundläggande behov. |
| **Produktområden som påverkas**         | Ekonomisk styrning     |
| **Status**                         | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen.   |


### <a name="warehouse-mobile-devices-portal"></a>Warehouse Mobile Devices-portalen

Warehouse mobile devices portalen (WMDP) är en fristående komponent som är avsedd för eget lokal distribution. Den här komponenten stöds inte längre i Finance and Operations. Ett enhetligt program som förbättrar användarupplevelsen har ersatt funktionen i WMDP.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Dubblettfunktion.       |
| **Ersatt av en annan funktion?**   | Ja. Funktionen har ersatts med Finance and Operations – lagerhållning. Mer information om inställningar, och förutsättningar finns i [Installera och konfigurera lagerstyrningsappen – översikt](../../../supply-chain/warehousing/install-configure-warehousing-app.md). |
| **Produktområden som påverkas**         | Lager- och transporthantering     |
| **Distribueringsalternativ**              | Warehouse mobile devices portalen (WMDP) är en fristående komponent som är avsedd för eget lokal distribution.               |
| **Status**                         | Inaktuell: Måltidsramen för att ta bort funktioner är Q4 2019.   |

### <a name="advanced-bank-reconciliation-matching-rule-for-manual-matching"></a>Avancerad matchningsregel för bankavstämning för manuell matchning

En matchningsregel användes för att välja och markera ett bankdokument när dokumenten manuellt matchades i avstämningskalkylarket.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Begränsad användning.                                                                         |
| **Ersatt av en annan funktion?**   | Nr. Kolumnfiltreringsmöjligheter ska användas för att söka efter dokument för avstämning. |
| **Produktområden som påverkas**         | Kassa- och bankhantering                                                               |
| **Distribueringsalternativ**              | Allt                                                                                    |
| **Status**                         | Borttagen från och med juli 2017.                                                               |

## <a name="dynamics-365-for-operations-1611-with-platform-update-3"></a>Dynamics 365 for Operations 1611 med plattformsuppdatering 3

### <a name="aeb-payment-formats-for-spain"></a>AEB-betalningformat för Spanien

Betalningsformaten för Consejo Superior Bancario användes för att skicka remissafiler till banken för kundbetalningar och leverantörsbetalningar. Innehållet i dessa format bestämdes av Asociación Española de Banca. Det omfattar Cuaderno 19, 32, 58, 34.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Betalningformaten används inte längre.                                  |
| **Ersatt av en annan funktion?**   | Ja, ISO20022 kreditöverföring och betalningsformat för autogiro för Spanien |
| **Produktområden som påverkas**         | Leverantörsreskontra, Kundreskontra                                    |
| **Status**                         | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen.           |

### <a name="bank-payments-transfer-for-lithuania"></a>Bankbetalningar överför för Litauen

Bankbetalningsöverföringar skapades och skrevs ut genom att använda exportformatet för betalningsöverföring (LT) för Litauen. Den litauiska marknaden har börjat använda LITASEN, det enade elektroniska banksystemet år 2005.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Betalningformaten används inte längre.                        |
| **Ersatt av en annan funktion?**   | Ja, ISO20022 betalningsformat för kreditöverföring för Litauen     |
| **Produktområden som påverkas**         | Leverantörsreskontra                                               |
| **Status**                         | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen. |

### <a name="bbs-direkte-remittering-payment-formats-for-norway"></a>BBS Direkte Remittering betalningsformat för Norge

BBS Direkte Remittering betalningsformat inkluderar exportinkasso för kundbetalning (autogiro) och import av returmeddelande.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Betalningformaten används inte längre.  |
| **Ersatt av en annan funktion?**   | Kundbetalningsformatet för AvtaleGiro för Norge kan användas för att skapa autogiro-meddelanden. Import av returmeddelande kommer att implementeras i kommande versioner. |
| **Produktområden som påverkas**         | Leverantörsreskontra, Kundreskontra   |
| **Status**                         | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen.                                                                                                 |

### <a name="chart-of-accounts-tool-for-spain"></a>Verktyg för kontoplan från Spanien

Det här verktyget används när en kontoplan i Spanien kräver stora ändringar. Användarna kan importera en ny kontoplan i Microsoft Excel eller textformat och kan också importera bokslut.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Begränsad användning                                                  |
| **Ersatt av en annan funktion?**   | Nr                                                             |
| **Produktområden som påverkas**         | Huvudbok                                                 |
| **Status**                         | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen. |

### <a name="dom80-payment-format-for-belgium"></a>Dom80 betalningsformat för Belgien

Äldre belgiskt betalningsformat för betalningsinsamling (autogiro).

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Betalningformatet används inte längre.                          |
| **Ersatt av en annan funktion?**   | Ja, ISO 20022 betalningsformat för autogiro för Belgien.         |
| **Produktområden som påverkas**         | Kundreskontra                                            |
| **Status**                         | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen. |

### <a name="dtaezag-payment-formats-for-switzerland"></a>DTA/EZAG-betalningformat för Schweiz

DTA-/EZAG-format integreras i ESR-systemet, eftersom de kan ha ett referensnummer. Eftersom referensnumret inte är obligatoriskt kan dessa format användas för att bearbeta alla leverantörsbetalningar. Dessa format används av företag som har ett bankkonto på en annan plats än “Postfinance.”

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Betalningformaten används inte längre.                        |
| **Ersatt av en annan funktion?**   | Ja, ISO20022 betalningsformat för kreditöverföring för Schweiz.   |
| **Produktområden som påverkas**         | Leverantörsreskontra                                               |
| **Status**                         | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen. |

### <a name="edifact-dirdeb-payment-format-for-austria"></a>EDIFACT – DIRDEB-betalningformat för Österrike

EDIFACT-DIRDEB-betalningsformat för betalningsinsamling (autogiro).

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Betalningformatet används inte längre.                          |
| **Ersatt av en annan funktion?**   | Ja, ISO 20022 betalningsformat för autogiro för Österrike.         |
| **Produktområden som påverkas**         | Kundreskontra                                            |
| **Status**                         | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen. |

### <a name="edivat-for-belgium"></a>EDIVAT för Belgien

EDIVAT är en inaktuell belgisk standard för elektronisk deklaration säker via e-post. Dynamics AX 2012 har kvar den skrivskyddade lösningen för att tillåta åtkomst till de historiska data.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Funktionen används inte längre.                           |
| **Ersatt av en annan funktion?**   | Nr                                                             |
| **Produktområden som påverkas**         | Huvudbok                                                 |
| **Status**                         | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen. |

### <a name="egiro-edifact-cremul-payment-import-format-for-norway"></a>eGiro EDIFACT CREMUL-betalningsformat för Norge

eGiro baseras på den internationella UN EDIFACT CREMUL-standarden (Multiple Credit Advice Message) som används för automatisk bokföring av kundbetalningar. I Dynamics AX, implementeras eGiro som ett importformat för kundbetalningar.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Betalningformatet används inte längre.                                                     |
| **Ersatt av en annan funktion?**   | Ja ISO20022 Camt.054 meddelandeimport. |
| **Produktområden som påverkas**         | Kundreskontra                                                                       |
| **Status**                         | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen.                            |

### <a name="external-inventory-for-poland"></a>Externt lager för Polen

Bevis av varor som tas från en leverantör för försäljning utan inköp. De varor som hanteras i externt lager, som inte påverkar standardlager, kan säljas och sedan köpas in automatiskt. Den här processen skapar verkliga lagerrörelser.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Ersatt av en annan funktion                                    |
| **Ersatt av en annan funktion?**   | Ja, försändelsefunktionen för den inkommande kärnan                |
| **Produktområden som påverkas**         | Leverantörsreskontra, lagerhantering                         |
| **Status**                         | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen. |

### <a name="financial-reports-generator-for-eastern-europe"></a>Ekonomisk rapportgenerator för Östra Europa

Ett verktyg för att ställa in datainsamling för redovisning och momsrapporter behövs och exportera data till XLS och DOC-rapportmallar

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Begränsad användning                                                                            |
| **Ersatt av en annan funktion?**   | Nr. Verktyget ska ersättas av elektroniska rapporteringskonfigurationer i kommande versioner. |
| **Produktområden som påverkas**         | Redovisning                                                                           |
| **Status**                         | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen.                           |

### <a name="import-of-customer-payment-transactions-for-finland"></a>Import av kundbetalningstransaktioner för Finland

Du kan välja ett importformat för finländska betalningar som importerar kundbetalningstransaktioner från en extern fil som tillhandahålls av banken.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Betalningformatet används inte längre.                                                     |
| **Ersatt av en annan funktion?**   | Ja ISO20022 Camt.054 meddelandeimport. |
| **Produktområden som påverkas**         | Kundreskontra                                                                       |
| **Status**                         | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen.                            |

### <a name="import-of-payment-transactions-into-a-general-ledger-journal-for-finland"></a>Import av betalningstransaktioner till en redovisningsjournal för Finland

Ett format som är specifik för Finland används för att importera redovisningstransaktioner till redovisningen.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Betalningformatet används inte längre.                                                     |
| **Ersatt av en annan funktion?**   | Ja ISO20022 Camt.053 import av bankutdrag med avancerad bankavstämning. |
| **Produktområden som påverkas**         | Kundreskontra                                                                       |
| **Status**                         | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen.                            |

### <a name="integration-with-isabel-synchronized-cis-for-belgium"></a>Integration med Isabel-synkroniserad (CIS) för Belgien

Isabel är ramverket för elektronisk bankverksamhet i Europa och en de facto-standard i Belgien.

|  &nbsp; | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Integration med Isabel-klienten har annullerats.   |
| **Ersatt av en annan funktion?**   | Nr. Betalningsformaten som inte längre används ersätts av ISO20022-betalningsformat för kreditöverföring för Belgien. |
| **Produktområden som påverkas**         | Leverantörsreskontra     |
| **Status**                         | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen.    |

### <a name="modifications-in-the-chart-of-accounts-and-accounting-rules-for-spain"></a>Ändringar i kontoplanen och redovisningsreglerna för Spanien

Den här funktionen används för ändringar i kontoplanen och redovisningsreglerna i Spanien. Den mappar konton för att transformera den gamla kontoplanen till den nya kontoplanen och jämföra det föregående räkenskapsåret med det nya räkenskapsåret, även om de bokförts till ett annat kontonummer.

|  &nbsp; |&nbsp;  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Begränsad användning                                                  |
| **Ersatt av en annan funktion?**   | Nr                                                             |
| **Produktområden som påverkas**         | Huvudbok                                                 |
| **Status**                         | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen. |

### <a name="pagamento-fornittori-vendor-payment-format"></a>Pagamento Fornittori leverantörsbetalningsformat

Äldre italienskt betalningsformat för kreditöverföringar.

| &nbsp;  |&nbsp;  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Betalningformatet används inte längre.                          |
| **Ersatt av en annan funktion?**   | Ja, ISO20022 betalningsformat för kreditöverföring för Italien         |
| **Produktområden som påverkas**         | Leverantörsreskontra                                               |
| **Status**                         | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen. |

### <a name="payment-export-formats-for-estonia"></a>Exportformat för betalning för Estland

Formaten Telehansa och Teleservice används för bankbetalningsexport.

| &nbsp;  |&nbsp;  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Betalningformaten används inte längre.                        |
| **Ersatt av en annan funktion?**   | Ja, ISO20022 betalningsformat för kreditöverföring för Estland       |
| **Produktområden som påverkas**         | Leverantörsreskontra                                               |
| **Status**                         | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen. |

### <a name="payment-file-archive-for-norway"></a>Betalningsfilarkiv för Norge

När betalningsfiler skapas arkiverar filarkivet automatiskt alla filer som skapas, även filer som tidigare skrevs eller lästes.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Ersatt av en annan funktion                                        |
| **Ersatt av en annan funktion?**   | Ja, arkiverade elektroniska rapporteringsjobb                            |
| **Produktområden som påverkas**         | Kundreskontra, leverantörsreskontra, organisationadministration |
| **Status**                         | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen.     |

### <a name="payment-import-formats-for-estonia"></a>Importformat för betalning för Estland

Formaten Telehansa och TeleTeenu används för bankbetalningsimport.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Betalningformaten används inte längre.                                                    |
| **Ersatt av en annan funktion?**   | Ja ISO20022 Camt.054 import av bankmeddelanden. |
| **Produktområden som påverkas**         | Kundreskontra                                                                        |
| **Status**                         | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen.                             |

### <a name="payroll-information-in-human-resources"></a>Löneinformation i Personal

Löneinformation i HR

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Den här funktionen har ersatts av huvudsidorna Lön och Personal.  |
| **Ersatt av en annan funktion?**   | **Förmåner**, **Inkomster** och andra relaterade sidor, som tidigare fanns i USA-lönelistan, har konfigurerats om och är nu en del av den grundläggande konfigurationen Personal för att ge stöd för extern lönebearbetning. Den här funktionen kan nås med hjälp av konfigurationsnyckeln **Personal 1** \> **Lönelista**. |
| **Produktområden som påverkas**         | Personal, Lön   |
| **Status**                         | Borttagen från Dynamics 365 for Operations version 1611.    |

### <a name="performance-management-goal-workflow"></a>Arbetsflöde för prestationshanteringmål

Prestationshantering inkluderar målhantering och integration med prestationsgranskning.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Prestationshantering formades om, och antalet målsidor förminskades för att förenkla processen.                 |
| **Ersatt av en annan funktion?**   | Nr. Mål kan visas för chefer via portalen Självbetjäning för chef, och kan ändras och visas av chefen. |
| **Produktområden som påverkas**         | Administration av humankapital       |
| **Status**                         | Borttagen från Dynamics 365 for Operations version 1611.    |

### <a name="postgirot-and-postgirot-utland-payment-formats-for-sweden"></a>Postgirot och Postgirot Utland betalningsformat för Sverige

Postgirot och Postgirot Utland betalningsformat för Sverige.

|&nbsp;   |&nbsp;  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Betalningformaten används inte längre.                        |
| **Ersatt av en annan funktion?**   | Ja, ISO20022 betalningsformat för kreditöverföring för Sverige        |
| **Produktområden som påverkas**         | Leverantörsreskontra                                               |
| **Status**                         | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen. |

### <a name="radio-frequency-identifier"></a>Radiofrekvensidentifiering

Radiofrekvensidentifiering (RFID) är en datainsamlingsteknik som använder elektroniska taggar för att lagra identifieringsdata och en läsare utan krav på fri sikt som fångar upp identifieringsdatan.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Låg kundanvändning och en begränsad uppsättning funktioner.   |
| **Ersatt av en annan funktion?**   | Nr                                              |
| **Produktområden som påverkas**         | Lagerhantering                            |
| **Status**                         | Borttagen Dynamics 365 for Operations 1611. |

### <a name="report-about-state-invoices-numbering-for-latvia"></a>Rapport om numrering av statliga fakturor för Lettland

Lettisk lagstiftning innehåller särskilda regler om hur försäljningsfakturor ska numreras. Funktionen låter dig tilldela specifika nummer till försäljningsfakturor som baseras på användaren eller användargruppen. Du kan sedan skapa en rapport eller en XML-fil. Du kan även skriva ut en rapport om fakturanummer som används.

| &nbsp;  |&nbsp;  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Numrering av statliga fakturor måste inte längre underhållas. Rapporten om använda fakturanummer är inte längre obligatorisk. |
| **Ersatt av en annan funktion?**   | Nr       |
| **Produktområden som påverkas**         | Kundreskontra    |
| **Status**                         | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen.  |

### <a name="set-up-the-names-of-the-manager-and-general-accountant-of-a-company-for-lithuania"></a>Ställ in namnen för chefen och den allmänna revisorn i ett företag för Litauen

Namnen på chefen och den allmänna revisorn i ett företag kan anges i företagsinformationen och användas vid olika lokala rapportutskrifter.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Ersatt av en annan funktion                                     |
| **Ersatt av en annan funktion?**   | Ja, inställningen av för tjänstemän kan användas för samma syfte.   |
| **Produktområden som påverkas**         | Leverantörsreskontra, Kundreskontra och Kassa- och bankhantering |
| **Status**                         | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen.  |

### <a name="shipping-carrier-interface"></a>Transportföretagsgränssnitt

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Dubblettfunktion   |
| **Ersatt av en annan funktion?**   | Delvis ersatt med transporthantering |
| **Produktområden som påverkas**         | Försäljning och marknadsföring, Lagerhantering  |
| **Status**                         | Borttagen från Dynamics 365 for Operations version 1611.  |

### <a name="telepay-payment-formats-for-norway"></a>Telepay betalningsformat för Norge

Telepay betalningsformat inkluderar leverantörsbetalningsexporten (kreditöverföring) och inkasso för kundbetalning (autogiro).

|&nbsp;   |&nbsp;  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Betalningformaten används inte längre.                                                        |
| **Ersatt av en annan funktion?**   | Ja, ISO20022 betalningsformat för kreditöverföring och format för AvtaleGiro-kundbetalning för Norge och även pain.002 och camt.054 import av returfiler för bankmeddelanden. |
| **Produktområden som påverkas**         | Leverantörsreskontra, Kundreskontra                                                          |
| **Status**                         | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen.                                 |

### <a name="vendor-payment-export-formats-for-finland"></a>Exportformat för leverantörsbetalning för Finland

Två format för att exportera betalningar är tillgängliga för Finland. LM02 (FI) används för lokala betalningar och LUM2 (FI) används för utländska betalningar.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Betalningformaten används inte längre.                        |
| **Ersatt av en annan funktion?**   | Ja, ISO20022 betalningsformat för kreditöverföring för Finland       |
| **Produktområden som påverkas**         | Leverantörsreskontra                                               |
| **Status**                         | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen. |

### <a name="warehouse-management-ii"></a>Lagerstyrning II

|  &nbsp; |&nbsp;  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Lagerstyrningssystem II-lösningar (WMS II) som var tillgängliga i modulen **lagerhantering** duplicerar funktionerna som finns i modulen **lagerstyrning** som släpptes i Dynamics AX 2012 R3.                                                                         |
| **Ersatt av en annan funktion?**   | Modulen **Lagerstyrning** som släpptes i AX 2012 R3, Dynamics AX 2012 R3 CU8 och Dynamics AX 2012 R3 CU9 ersätter funktionerna i Lagerstyrning II. Den nya modulen har mer avancerade funktioner och mer flexibla lagerstyrningsprocesser än de som erbjöds av funktionerna i Lagerstyrning II. |
| **Produktområden som påverkas**         | Lagerhantering, försäljning och marknadsföring, anskaffning och källa   |
| **Status**                         | Borttagen från Dynamics 365 for Operations version 1611.    |

### <a name="worker-reminders-in-human-resources"></a>Påminnelser till arbetare i Personal

Löneinformation i HR

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Låg användning                                                           |
| **Ersatt av en annan funktion?**   | Nr                                                                  |
| **Produktområden som påverkas**         | Personal                                                     |
| **Status**                         | Borttagen från Dynamics 365 for Operations version 1611. |

### <a name="workflow-for-creating-goals"></a>Arbetsflöde för att skapa mål

Ett arbetsflöde för hantering av genereringen av medarbetare är en av flera arbetsflöden som är tillgängliga för att hjälpa till att koordinera prestandahanteringsprocessen.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Prestandahantering har gjorts om helt i Finance and Operations.     |
| **Ersatt av en annan funktion?**   | Den omformade prestandahanteringsfunktionen innehåller mer kontroll över innehållet av mål, måtten som används för att spåra framsteg och bilaga med förklarande dokumentation. Mål kan lagras som mallar och sedan återanvändas. Den här funktionen kan hjälpa dig att snabbare ställa in ytterligare mål för medarbetarna. |
| **Produktområden som påverkas**         | Administration av humankapital                 |
| **Status**                         | Borttagen från Dynamics 365 for Operations version 1611. |

## <a name="dynamics-ax-70"></a>Dynamics AX 7.0 


### <a name="ability-to-cancel-changes-to-a-vendor-invoice"></a>Möjligheten att avbryta ändringar i en leverantörsfaktura

| &nbsp;  |&nbsp;  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Prestandaförbättring        |
| **Ersatt av en annan funktion?**   | Nr                             |
| **Produktområden som påverkas**         | Leverantörsreskontra               |
| **Status**                         | Borttagen från och med Dynamics AX 7.0. |

### <a name="aif-axd-and-axbc-integrations"></a>AIF-, AxD- och AxBC-integrationer

I AIF (Application Integration Framework) kan data utbytas med externa system genom affärslogik som exponeras som tjänster. Dynamics AX omfattar tjänster som baseras på dokument och .NET Business Connector (AxBC). Ett dokument skapas genom att använda XML. XML inkluderar rubrikinformation som läggs till för att skapa ett *meddelande* som kan överföras in eller ut från Dynamics AX. Exempel på dokument innehåller försäljningsorder och inköpsorder. Dock kan nästan alla enheter, till exempel en kund, representeras av ett dokument. Tjänster som baseras på dokument använder **Axd \<Document\>**-klasserna.

|  &nbsp; | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Arkitekturen för AIF och AxDs kunde inte skalas till en molntjänst. Det fanns prestandaproblem relaterade till massimport.                                        |
| **Ersatt av en annan funktion?**   | Den här funktionen har ersatts av ramverket för dataimport/dataexport, som stöder återkommande massimport/massexport. För AxBC rekommenderar vi att du använder faktiska tabeller. |
| **Produktområden som påverkas**         | AxDs, AxBCs och AIF   |
| **Status**                         | Borttagen från och med Dynamics AX 7.0.   |

### <a name="billing-code-rate-scripts"></a>Tariffskript för faktureringskod

Faktureringsskript används för att beräkna fakturerbara kostnader för faktureringskoder. Detta skript kräver anpassad utveckling i C-Sharp eller Visual Basic programmeringsspråk. I den aktuella versionen av Dynamics AX stöds inte **tariffskript för faktureringskod**.

| &nbsp;  |&nbsp;  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Stöd för anpassade C Sharp eller Visual Basic-skript har inte lagts till i Dynamics AX 7.0. |
| **Ersatt av en annan funktion?**   | Nej                                                                                      |
| **Produktområden som påverkas**         | Offentlig sektor, kundreskontra                                    |
| **Status**                         | Borttagen från och med Dynamics AX 7.0.                                                          |

### <a name="boms-without-bom-versions"></a>Strukturlistor utan strukturlisteversioner

När konfigurationsnyckeln för **strukturlisteversioner** inaktiverades doldes strukturlisteversioner i alla formulär och systemet framtvingade en 1:1-relation mellan frisläppta produkter och strukturlistor. I den aktuella versionen av Dynamics AX kan konfigurationsnyckeln för **strukturlisteversioner** inte inaktiveras.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Användningen av en konfigurationsnyckel för att kontrollera strukturlisteversioner kan inte skalas till en molnmiljö. |
| **Ersatt av en annan funktion?**   | Nr                                                                                      |
| **Produktområden som påverkas**         | Produktinformationshantering, Lagerhantering                                    |
| **Status**                         | Borttagen från och med Dynamics AX 7.0.                                                          |

### <a name="brazilian-bordero"></a>Brasilian Bordero

Specifik betalningsmetod för brasilianska företag

|  &nbsp; | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Stöd för den brasilianska Bordero-betalningsmetoden har annullerats från brasiliansk lokalisering |
| **Ersatt av en annan funktion?**   | Nr   |
| **Produktområden som påverkas**         | Leverantörsreskontra   |
| **Status**                         | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen. |

### <a name="brazilian-sintegra-statement"></a>Brazilian Sintegra-utdrag

Federala skatteutdrag för ICMS-skatt

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Detta utdrag används inte längre i vissa brasilianska stater. |
| **Ersatt av en annan funktion?**   | Nr. Användare kan använda den allmänna funktionen för elektronisk rapportering för att konfigurera utdraget, om det krävs och i vissa fall. |
| **Produktområden som påverkas**         | Skatteböcker    |
| **Status**                         | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen.   |

### <a name="brazilian-scan-contingency-mode-for-nf-e"></a>Brasiliansk SCAN eventualitetläge för NF-e

(SCAN) eventualitetmiljön används för att skapa, exportera och importera status för Nota Fiscal eletrônica (NF-e) när miljön för Secretaria da Fazenda (SEFAZ) inte är tillgänglig.

|  &nbsp; | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Den här eventualitetsmetoden används inte längre i alla brasilianska stater |
| **Ersatt av en annan funktion?**   | Nr                                                                          |
| **Produktområden som påverkas**         | Kundreskontra                                                         |
| **Status**                         | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen.              |

### <a name="business-analyzer"></a>Business Analyzer

Det här mobila programmet låter användare granska viktiga affärsmått.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Funktionen har ersatts med en annan funktion.   |
| **Ersatt av en annan funktion?**   | Innehållspaketet för övervakning av ekonomiska resultat för Microsoft Power BI kommer att inkludera samma ekonomiska mätvärden som tidigare var tillgängliga i Business Analyzer. |
| **Produktområden som påverkas**         | Huvudbok      |
| **Status**                         | Inaktuell: Användning av Business Analyzer stöds inte längre.    |

### <a name="business-statistics"></a>Affärsstatistik

Konfigurationen av frågor om affärsstatistik som kan hjälpa dig att analysera organisationens resultat

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Gammal metod för BI (Business Intelligence), låg kundanvändning och en begränsad funktionsuppsättning |
| **Ersatt av en annan funktion?**   | Nya BI-lösningar för den aktuella versionen av Dynamics AX                                      |
| **Produktområden som påverkas**         | Anskaffning och sourcing, Leverantörsreskontra, Försäljning och marknadsföring, Kundreskontra         |
| **Status**                         | Borttagen från och med Dynamics AX 7.0.                                                               |

### <a name="change-document-date-function-in-invoice-approval-journal"></a>Funktionen Ändra dokumentets datum i Fakturagodkännandejournal

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Låg användning                                                               |
| **Ersatt av en annan funktion?**   | Ja. Dokumentdatumet för den bokförda leverantörstransaktionen kan ändras. |
| **Produktområden som påverkas**         | Leverantörsreskontra                                                        |
| **Status**                         | Borttagen från och med Dynamics AX 7.0.                                          |

### <a name="clieop03-payment-format-for-the-netherlands"></a>Betalningsformatet ClieOp03 för Nederländerna

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Formatet är inte längre tillämpligt i Nederländerna eftersom det har ersatts av SEPA-funktionen. |
| **Ersatt av en annan funktion?**   | SEPA-betalningsexport  |
| **Produktområden som påverkas**         | Alla moduler     |
| **Status**                         | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen.   |

### <a name="compliance-center"></a>Regelefterlevnadscenter

Regelefterlevnadscentret var en Enterprise Portal-webbplats för att hantera dokumentationskraven för efterlevnadsinsatser som är relaterade till Sarbanes-Oxley-lagen.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Brist på kundanvändning. Microsoft SharePoint innehåller samma kapacitet som var tillgänglig i regelefterlevnadscentret. |
| **Ersatt av en annan funktion?**   | Nr   |
| **Produktområden som påverkas**         | Regelefterlevnad och interna kontroller  |
| **Status**                         | Borttagen från och med Dynamics AX 7.0.    |

### <a name="connector-for-microsoft-dynamics"></a>Connector för Microsoft Dynamics

Verktyget användes för att integrerar viktiga data från Microsoft Dynamics CRM till Dynamics ERP-tillämpningar.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Funktionen har ersatts med en annan funktion. |
| **Ersatt av en annan funktion?**   | Dataverse                                      |
| **Produktområden som påverkas**         | Koppling för Dynamics                         |
| **Status**                         | Borttagen från och med Dynamics AX 7.0.                           |

### <a name="container-unit-and-multi-dimension-on-hand"></a>Behållarenhet och flerdimensionell behållning

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Dubblettfunktion |
| **Ersatt av en annan funktion?**   | Ja. Sedan AX 2012 har den här funktionen ersatts av funktionsuppsättning av konsoliderade batchorder. Den här funktionsuppsättningen inkluderar den konsoliderade behållningsvyn. |
| **Produktområden som påverkas**         | Produktinformationshantering, Produktionskontroll, Lagerhantering, Försäljning och marknadsföring  |
| **Status**                         | Borttagen från och med Dynamics AX 7.0. |

### <a name="cue-group-metadata"></a>Stackikongruppmetadata

|  &nbsp; | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Stackikongrupper användes för att visa en eller flera stackikoner i faktaboxområdet. Upptaget var begränsat och det fanns även prestandaproblem eftersom en poständring i ett överordnat formulär orsakade en fråga per stackikon i stackikongruppen. |
| **Ersatt av en annan funktion?**   | Nr      |
| **Produktområden som påverkas**         | Alla moduler    |
| **Status**                         | Borttagen från och med Dynamics AX 7.0.  |

### <a name="cue-metadata"></a>Stackikonmetadata

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Stackikonmetadata begränsades till information om antal och summor.    |
| **Ersatt av en annan funktion?**   | Panelmetadata introducerades för att ge mer flexibilitet för modellering. Du kan till exempel modellera aktuella antal, navigering och KPI:er (Key Performance Indicator). Metadata för antal på panel är en direkt ersättning av stackikonmetadata. |
| **Produktområden som påverkas**         | Alla moduler           |
| **Status**                         | Borttagen från och med Dynamics AX 7.0.      |

### <a name="danish-check-format"></a>Danskt checkformat

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Stöd för den danska checkformatlayouten har tagits bort, och rapporten har tagits bort från lokalisering för danska. |
| **Ersatt av en annan funktion?**   | Nr    |
| **Produktområden som påverkas**         | Alla moduler    |
| **Status**                         | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen.  |

### <a name="data-partitions"></a>Datapartitioner

Datapartitioner tillhandahåller en logisk separering av data i Dynamics AX-databasen.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Datapartitioner introducerades i Dynamics AX 2012 R2 för möjliggöra isolering av data. I ett vanligt scenario har ett företag ett dotterbolag och data från ett dotterbolag ska inte vara synliga för ett annat dotterföretag, även om båda dotterbolagen hanteras av samma IT-avdelning. Det behövdes dock extra skript och hantering av information i hela programmet för att skapa nya partitioner och förse dem med data och att säkerhetskopiera partitionsdata. I molnet, där vi har tillgång till plattform som en tjänst (PaaS) databas-tjänster (Microsoft Azure SQL-databasen), är det mycket effektivare att använda en databas som isolerade behållare än att utföra isolering i programmet. Oavsett om datapartition är nödvändig för dotterbolag, för flera innehavare eller bara för skalning, anser vi att scenarier kan hanteras bättre via flera olika Finance and Operations-instanser. |
| **Ersatt av en annan funktion?**   | Kunder som använder datapartitioner måste använda flera instanser av Finance and Operations om separering av databaser är en vital faktor.    |
| **Produktområden som påverkas**         | Alla moduler  |
| **Status**                         | Borttagen från och med Dynamics AX 7.0.  |


### <a name="database-and-file-share-storage-for-attachments"></a>Databas- och fildelningslagring för bifogade filer

Dynamics AX 2012 tillåter lagring av bifogade filer i databasen och i delade filer. Båda dessa alternativ stöds inte längre.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Fildelningslagring stöds inte längre eftersom molnbaserad miljöer inte kan kommunicera med lokala filresurser. Databaslagring har ersatts av Azure Blob-lagring. Azure Blob-lagring motsvarar lagring i databasen, eftersom dokument bara nås via klientformulären i Finance and Operations. Detta ger den extra fördelen med utrymme som inte påverkar databasens prestanda negativt. BLOB-lagring är standard Lagringsmekanismen för dokumenthantering och fungerar omedelbart. |
| **Ersatt av en annan funktion?**   | Databaslagring har ersatts av Azure Blob-lagring.   |
| **Produktområden som påverkas**         | Alla moduler  |
| **Status**                         | Borttagen från och med Dynamics AX 7.0.   |

### <a name="delimitation"></a>Avgränsning

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Ingen användning av funktionen påträffades. |
| **Ersatt av en annan funktion?**   | Nr                                     |
| **Produktområden som påverkas**         | Tid och närvaro                    |
| **Status**                         | Borttagen från och med Dynamics AX 7.0.         |

### <a name="desktop-client"></a>Skrivbordsklient

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Dynamics AX-klientupplevelsen har formats om för att förbättra användbarheten över flera plattformar och enheter.                      |
| **Ersatt av en annan funktion?**   | Den nya webbklienten baseras på skrivbordsformulärmetadata och programmeringsmodellen som har ändrats för att ge en heltäckande webbplattform. |
| **Produktområden som påverkas**         | Alla moduler  |
| **Status**                         | Borttagen från och med Dynamics AX 7.0.   |

### <a name="direct-database-connection"></a>Direkt databasanslutning

I Dynamics AX 2012 R3 kunde inte Retail Modern POS ansluta direkt till Channel DB på liknande sätt som till Enterprise POS. Detta var förutom standardkommunikationsmetoden för Retail Modern POS som kommunicerar via Retail Server.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Direkt databasanslutning krävde lägre säkerhetsprotokoll och användes främst för att uppnå högsta möjliga prestanda. På grund av prestanda- och säkerhetsförbättringar som har uppstått i Finance and Operations orsakar nu den här funktionen fler problem än den löser. |
| **Ersatt av en annan funktion?**   | Nr. Endast standardkommunikation för Retail Server stöds nu.  |
| **Produktområden som påverkas**         | Kanal-DB/Retail Modern POS   |
| **Status**                         | Borttagen från och med Dynamics AX 7.0.  |

### <a name="dutch-swift-mt940"></a>Holländsk SWIFT MT940

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Den generiska funktionen används nu i stället för den lokaliserade funktionen.                    |
| **Ersatt av en annan funktion?**   | Ja, den här funktionen har ersatts av funktionen för avancerad bankavstämning. |
| **Produktområden som påverkas**         | Alla moduler                                                                              |
| **Status**                         | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen.                           |

### <a name="ebilanz-xbrl-for-germany"></a>eBilanz (XBRL för Tyskland)

Den här funktionen ger eXtensible Business Reporting Language (XBRL)-utdata som är specifikt utformade för tysk eBilanz-taxonomi.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Brist på kundanvändning  |
| **Ersatt av en annan funktion?**   | Den här funktionen har inte ersatts av en annan funktion, men flera specialiserade XBRL-paket som innehåller omfattande XBRL-funktioner är tillgängliga för den tyska marknaden. |
| **Produktområden som påverkas**         | Management Reporter      |
| **Status**                         | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen.  |

### <a name="enterprise-portal-client"></a>Enterprise Portal-klient

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | En enskild klientplattform har tillhandahållits.  |
| **Ersatt av en annan funktion?**   | Den nya webbklienten baseras på skrivbordsformulärmetadata och programmeringsmodellen som har ändrats för att ge en heltäckande webbplattform. |
| **Produktområden som påverkas**         | Alla moduler  |
| **Status**                         | Borttagen från och med Dynamics AX 7.0.   |

### <a name="environmental-sustainability"></a>Miljöhållbarhet

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Låg kundanvändning och en begränsad uppsättning funktioner.  |
| **Ersatt av en annan funktion?**   | Nr              |
| **Produktområden som påverkas**         | Efterlevnad och interna kontroller, Leverantörsreskontra  |
| **Status**                         | Borttagen från och med Dynamics AX 7.0. |

### <a name="form-activex-and-managed-host-controls"></a>ActiveX och de hanterade värdkontroller för formulär

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | ActiveX och hanterade värdkontroller baseras på den inaktuella skrivbordsklienten. |
| **Ersatt av en annan funktion?**   | Det utökningsbara kontrollramverket stöder utveckling av nya kontroller som baseras på HTML, CSS och JavaScript, och är en klass 1-kontroll i Microsoft Visual Studio Tooling-miljön. |
| **Produktområden som påverkas**         | Alla moduler     |
| **Status**                         | Borttagen från och med Dynamics AX 7.0.       |

### <a name="generate-prenotes-by-using-a-batch"></a>Skapa förauktoriseringar genom att använda en batch

Genereringen av förauktoriseringar kan inte utföras med hjälp av en batch men kan fortfarande utföras av en användare.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Inget formulär finns för att bevara och visa den resulterande filen med förauktoriseringar när den skapats med hjälp av en batch. |
| **Ersatt av en annan funktion?**   | Förauktoriseringar kan fortfarande skapas och användaren har kontroll över var filen sparas.   |
| **Produktområden som påverkas**         | Leverantörsreskontra, Kundreskontra och Kassa- och bankhantering  |
| **Status**                         | Borttagen AX 7.0.    |

### <a name="german-dtaus-payment-export-and-account-statement-import-totals-and-transactions"></a>Tysk DTAUS-betalningsexport och -kontoutdragsimport (summor och transaktioner)

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Formatet är inte längre tillämpligt i Tyskland eftersom det har ersatts av SEPA-funktionen (Single Euro Payments Area).                    |
| **Ersatt av en annan funktion?**   | Ja, funktionen har ersatts av SEPA-betalningsexport och avancerad bankavstämning för import av kontoutdrag. |
| **Produktområden som påverkas**         | Alla moduler  |
| **Status**                         | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen. |

### <a name="german-dtazv-payment-format-in-domestic-currency"></a>Tyskt DTAZV betalningsformat i inhemsk valuta

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Formatet är inte längre tillämpligt i Tyskland eftersom det har ersatts av SEPA-funktionen. |
| **Ersatt av en annan funktion?**   | SEPA-betalningsexport    |
| **Produktområden som påverkas**         | Leverantörsreskontra   |
| **Status**                         | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen.    |

### <a name="german-mt940-import"></a>Tysk MT940-import

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Den generiska funktionen används nu i stället för den lokaliserade funktionen.                    |
| **Ersatt av en annan funktion?**   | Ja, den här funktionen har ersatts av funktionen för avancerad bankavstämning. |
| **Produktområden som påverkas**         | Alla moduler                                                                              |
| **Status**                         | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen.                           |

### <a name="german-xml-eu-sales-list"></a>Tysk XML-baserad EU-försäljningslista

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | XML-formatet för tyska listrapporten över försäljning inom EU stöds inte längre. Det går enbart att använda textfilformatet ELMA5 för att skicka in listrapporten över försäljning inom EU till den tyska skattemyndigheten. |
| **Ersatt av en annan funktion?**   | Nr         |
| **Produktområden som påverkas**         | Skatt        |
| **Status**                         | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen.   |

### <a name="gl-ssrs-reports"></a>GL SSRS-rapporter

Rapporter som innehåller följande menykommandon har tagits bort: **Råbalanssammanfattning**, **Detaljerad råbalans**, **Kontoplan**, **Redovisningsspårning**, **Saldon** och **Saldolista**.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Ekonomiska Microsoft SQL Server Reporting Services-rapporter (SSRS) har ersatts av Management Reporter-funktioner och -standardrapporter. |
| **Ersatt av en annan funktion?**   | Management Reporter (med etiketten **Ekonomisk rapportering** i den aktuella versionen av Dynamics AX)    |
| **Produktområden som påverkas**         | Huvudbok   |
| **Status**                         | Borttagen från och med Dynamics AX 7.0.   |

### <a name="infopart-and-formpart-metadata"></a>InfoPart- och FormPart-metadata

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | InfoPart- och FormPart-metadata möjliggjorde genereringen av faktaboxar för två olika klienter. |
| **Ersatt av en annan funktion?**   | InfoPart-metadata, som var en förenklad formulärdefinition, konverteras till ett formulär med uppgraderingsverktyg. FormPart-metadata, som refererade till ett formulär, ersättas av en mer direkt referens som skapas med uppgraderingsverktyg. |
| **Produktområden som påverkas**         | Alla moduler    |
| **Status**                         | Borttagen från och med Dynamics AX 7.0.        |

### <a name="main-account-list-page"></a>Listsida för huvudkonton

En lista med konton för den juridiska personen och tillhörande saldoinformation

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Information om saldo är tillgänglig på listsidan **Råbalans** efter konto och dimension.  |
| **Ersatt av en annan funktion?**   | **Huvudkonton** innehåller samma lista med konton som listsidan **Huvudkonto**. Rutnätsvyn i **Huvudkonton** visar också en ännu mindre, rutnätslik vy. |
| **Produktområden som påverkas**         | Huvudbok      |
| **Status**                         | Borttagen från och med Dynamics AX 7.0.    |

### <a name="malaysia-and-singapore-bank-cash-flow-report"></a>Rapport om bankkassaflöde för Malaysia och Singapore

Den här funktionen låter användaren skriva ut en kassaflödesrapport som visar transaktioner och information om kassainflöden och kassautflöden för ett visst datumintervall för valda bankkonton.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Samma information kan erhållas från förfrågningsbanktransaktionen. |
| **Ersatt av en annan funktion?**   | Förfrågningsbanktransaktionen                                            |
| **Produktområden som påverkas**         | Kassa- och bankhantering                                                |
| **Status**                         | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen.          |

### <a name="mexican-cfd-electronic-invoice"></a>Mexikansk elektronisk CFD-faktura

Den här funktionen möjliggjorde genereringen av mexikanska e-fakturor med hjälp av CFD-metoden (Comprobante Fiscal Digital), där företaget signerar fakturan genom att begära den relaterade auktoriseringen från myndigheterna. Den här funktioner ger även en månadsvis rapport som innehåller alla e-fakturor som utfärdats under perioden.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Metoden är inte längre tillämplig. Genereringen av elektroniska fakturor genom att använda CFD-metoden drogs tillbaka av skattemyndigheterna och ersattes av CFDI-metoden (Comprobante Fiscal Digital a través de Internet), där signeringen delegeras till tredjepartsleverantören (PAC). Den månatliga rapporten har tagits bort och ett förfrågningsalternativ gör det möjligt för användare att fråga om historiska transaktioner. |
| **Ersatt av en annan funktion?**   | Nr    |
| **Produktområden som påverkas**         | Kundfordringar, Projekt   |
| **Status**                         | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen. |

### <a name="mexico-realized-and-unrealized-vat"></a>Realiserad och orealiserad skatt för Mexiko

Dynamics AX 2012 hanterade orealiserad mervärdesskatt (VAT) genom att använda funktioner specifika för Mexiko för ”orealiserad skatt”.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Dubblettfunktion  |
| **Ersatt av en annan funktion?**   | Ja, den här funktionen har ersatts av standardfunktioner för villkorlig moms som tillhandahålls av basen. |
| **Produktområden som påverkas**         | Skatt   |
| **Status**                         | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen. |

### <a name="microsoft-outlook-integration"></a>Microsoft Outlook-integrering


| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Funktionen har ersatts med en Microsoft Exchange Server-integrering. |
| **Ersatt av en annan funktion?**   | Ja                                                                            |
| **Produktområden som påverkas**         | Sales and Marketing                                                            |
| **Status**                         | Borttagen från och med Dynamics AX 7.0.                                                 |

### <a name="private-blocking-of-inventory-and-warehouse-management-journals"></a>Privat blockering av inventerings- och lagerhanteringsjournaler

Inventerings- och lagerställejournalerna stöder inte längre möjligheten att markera en journal som privat för en vald användare. Endast processen för att blockera journaler som privata för användargrupper och blockering under redigering stöds.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Ingen användning av funktionen påträffades. |
| **Ersatt av en annan funktion?**   | Nr                                     |
| **Produktområden som påverkas**         | Lagerhantering                   |
| **Status**                         | Borttagen från och med Dynamics AX 7.0.         |

### <a name="product-builder"></a>Product Builder

Product Builder användes för att dynamiskt konfigurera artiklar från en försäljningsorder, inköpsorder, tillverkningsorder, försäljningsoffert, projektoffert eller artikelbehov. Baserat på en produktmodell, som hade modellvariabler, kunde användaren välja värden för att uppfylla kundkraven och för att få en unik produktvariant som hade en strukturlista och ett flöde.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Product Builder exponerade X++-kod till slutanvändare och stöds inte i den aktuella versionen av Dynamics AX. Den har tagits bort för att undvika dubbelt underhållsarbete med överlappande, ansenliga kodbaser.  |
| **Ersatt av en annan funktion?**   | Ja. Begränsningsbaserad konfiguration infördes i Dynamics AX 2012 där avskrivningen av Product Builder i kommande versioner har tillkännagivits. Den begränsningsbaserade konfigurationstekniken väljs på produktmallarna för att möjliggöra konfigurationen. Mer information finns i [Produktkonfiguration – översikt](../../../supply-chain/pim/build-product-configuration-model.md). |
| **Produktområden som påverkas**         | Produktinformationshantering, Försäljning och marknadsföring  |
| **Status**                         | Borttagen från och med Dynamics AX 7.0.      |

### <a name="production-floor-app"></a>Appen Produktionsgolv
Detta är appen för pekplattor med Windows 8.1 RT och Windows 8.1 Pro.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Med ändringen till en webbaserad klient är det möjligt att genomföra liknande funktioner med hjälp av inbyggda 7.0 för Dynamics AX-klienten. Jobbkortenhet tillhandahåller ett användargränssnitt för produktionsgolv som är optimerat för formfaktorer tryck- och pekplattor. |
| **Ersatt av en annan funktion?**   | Ja. Jobbkortenhet som ingår i Dynamics AX 7.0.                                                                           |
| **Produktområden som påverkas**         | Produktionskontroll                                                |
| **Status**                         | Inaktuell: Ett borttagningsdatum från Microsoft store har inte ännu ställts in för den här funktionen.                                                |


### <a name="rename-product-dimension"></a>Byt namn på produktdimension

Den här funktionen låter dig ändra namnet på en av de tre standardproduktdimensionerna (storlek, färg eller format) till ett namn som passar bättre för dina affärsbehov. Namnändringen inkluderade alla etiketter där produktdimensionsnamnet användes.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Den aktuella versionen av Dynamics AX stöder inte etikettändringar under körning. |
| **Ersatt av en annan funktion?**   | Nr                                                                            |
| **Produktområden som påverkas**         | Produktinformationshantering                                                |
| **Status**                         | Borttagen från och med Dynamics AX 7.0.                                                |

### <a name="retail-server-connectivity-using-http"></a>Retail Server-anslutning använder HTTP

I Dynamics AX 2012 R3 kan Retail Server med hjälp av HTTP-kommunikation (icke-säker). Detta var förutom standardkommunikationen med HTTPS.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | På grund av nya säkerhetskrav stöds endast säker kommunikation med TLS 1.2 (eller högre om tillgängligt) nu. Installationsprogrammet för självbetjäning konfigurerar automatiskt datorn för den här kommunikationen. |
| **Ersatt av en annan funktion?**   | Nr. Endast standardkommunikation för HTTPS stöds nu. |
| **Produktområden som påverkas**         | Butiksserver  |
| **Status**                         | Borttagen från och med Dynamics AX 7.0. |

### <a name="role-center-pages"></a>Rollcentersidor

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Rollcentersidor skapades på den inaktuella Enterprise Portal-plattformen, som har ersatts av den nya webbklientplattformen i den aktuella versionen av Dynamics AX. |
| **Ersatt av en annan funktion?**   | Det nya arbetsyteformulärmönstret förser användare med en processcentrerad design som tillhandahåller enkel åtkomst till vanliga uppgifter i den processen.                       |
| **Produktområden som påverkas**         | Alla moduler    |
| **Status**                         | Borttagen från och med Dynamics AX 7.0.   |

### <a name="sales-tax-jurisdictions"></a>Skattemyndigheter

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Låg kundanvändning och en begränsad uppsättning funktioner. |
| **Ersatt av en annan funktion?**   | Nr                                           |
| **Produktområden som påverkas**         | USA-moms                                 |
| **Status**                         | Borttagen från och med Dynamics AX 7.0.               |

### <a name="sites-services"></a>Platstjänster

Med hjälp av webbplatstjänster kan du utöka dina affärsprocesser till Internet utan IT-support.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Microsoft Azure-infrastrukturen, som användes av Dynamics AX, har nya kapaciteter som kan användas i stället (exempelvis, Azure-webbplatser). |
| **Ersatt av en annan funktion?**   | Nr   |
| **Produktområden som påverkas**         | Rekrytering av personal, ärendehantering, begäran om offerter, registrering av leverantör, samarbetsplatser för affärsmöjligheter och kampanjer  |
| **Status**                         | Borttagen från och med Dynamics AX 7.0.    |

### <a name="ssas-demand-forecasting-strategy"></a>SSAS-tjänster för efterfrågeprognosticering

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Utformningen av den här funktionen stöds inte i den nya arkitekturen i molnet. |
| **Ersatt av en annan funktion?**   | Efterfrågeprognosticeringsstrategi för Azure-maskininlärning                           |
| **Produktområden som påverkas**         | Huvudplanering                                                              |
| **Status**                         | Borttagen från och med Dynamics AX 7.0.                                               |

### <a name="vendor-invoice-pool-excluding-posting-details"></a>Leverantörsfakturapool utan bokföringsdetaljer

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Låg användning. Den här funktionen har ersatts av fakturajournalen som har en arbetsflödesfunktion. |
| **Ersatt av en annan funktion?**   | Arbetsflödesfunktionerna i Fakturajournal.     |
| **Produktområden som påverkas**         | Leverantörsreskontra |
| **Status**                         | Borttagen från och med Dynamics AX 7.0.    |


### <a name="virtual-company-accounts"></a>Virtuella företagskonton

Funktionen för virtuella företag stöds inte längre i Dynamics AX. Funktionen för virtuella företag gjorde att användarna kunde ställa in register som kunde delas av en uppsättning företag. Du kan hitta en beskrivning av funktionen här: [Företagskonton och konton för virtuella företag](../../fin-ops/get-started/ax4-content-retired.md). Funktionen fungerar genom att gruppera register i samlingar som tilldelas till virtuella företag, som är grupper med befintliga ”verkliga” företag. Frågor skapas så att alla företag i det virtuella företaget kan komma åt data i registren för de associerade registersamlingarna.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | - Virtuella företag måste ställas in innan data lagras i registren. Det är mycket svårt att ställa in virtuella företag efter en befintlig implementering i efterhand.<br><br>- Eftersom det har gjorts så mycket datanormalisering i den aktuella versionen av AX har det blivit svårt att veta vad som ska lägga till i registersamlingarna. Till exempel är det svårt att veta vilka register som ska delas. Alla register som refereras från register som ingår i ett virtuellt företag måste också läggas till. Registernormalisering har inneburit att även enkla huvuddata som är fördelade över flera register måste vara en del av det virtuella företaget. Alla misstag som begås här kommer att leda till funktionsproblem.<br><br>- När ett register ingår i ett virtuellt företag förlorar det information om informationens ursprung, och endast det virtuella företaget registreras.   |
| **Ersatt av en annan funktion?** | Globala register kan användas för att göra register tillgängliga från alla företag. För närvarande finns det ingen ersättning. |   
| **Produktområden som påverkas**       | Alla moduler |   
| **Status**                       | Borttagen från och med Dynamics AX 7.0.   |   

### <a name="windows-8-tablet-app"></a>Windows 8 surfplatteapp

Windows 8 surfplatteapp gav funktion för utgiftsregistrering och godkännande.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Finance and Operations är kompatibel med surfplattor. Surfplatteappen behövs inte längre.    |
| **Ersatt av en annan funktion?**   | Nr.          |
| **Produktområden som påverkas**         | Utläggshantering   |
| **Status**                         | Borttagen: Den här funktionen är bara tillgänglig för Dynamics AX 2012 R3. |

### <a name="workplanner"></a>Arbetsplanerare

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Låg användning |
| **Ersatt av en annan funktion?**   | Nej, men sidan **Profilrelation**, som öppnas från sidan **Profilgrupper** stöder samma affärsscenario som den inaktuella sidan **Arbetsplanerare**. |
| **Produktområden som påverkas**         | Tid och närvaro     |
| **Status**                         | Koden har inte tagits bort. Formuläret JmgWorkPlanner har emellertid inte migrerats.    |

### <a name="x-financial-statements"></a>X++-bokslut

| &nbsp;  | &nbsp; |
|-------------------------------------------------|----------------------------------------------------------------------------------------------------------|
| <strong>Orsak till inaktuell/borttagning</strong> |                         Funktionen har ersatts med en annan funktion.                         |
|  <strong>Ersatt av en annan funktion?</strong>  | Management Reporter (med etiketten <strong>Ekonomisk rapportering</strong> i den aktuella versionen av Dynamics AX) |
|     <strong>Produktområden som påverkas</strong>     |                                              Huvudbok                                              |
|             <strong>Status</strong>             |                                      Borttagen från och med Dynamics AX 2012.                                      |



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
