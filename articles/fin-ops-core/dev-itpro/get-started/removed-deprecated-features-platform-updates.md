---
title: Borttagna eller avskrivna plattformsfunktioner
description: I detta ämne beskrivs funktioner som har tagits bort, eller som planerats för borttagning i plattformsuppdateringar av appar för ekonomi och drift.
author: sericks007
ms.date: 03/03/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2020-02-29
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: 6b4c514d34e4afbaac4afabed6865496747c0411
ms.sourcegitcommit: 2e554371f5005ef26f8131ac27eb171f0bb57b4e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/04/2022
ms.locfileid: "8384730"
---
# <a name="removed-or-deprecated-platform-features"></a>Borttagna eller utfasade plattformsfunktioner

[!include [banner](../includes/banner.md)]

I detta ämne beskrivs funktioner som har tagits bort, eller som planerats för borttagning i plattformsuppdateringar av appar för ekonomi och drift.

- En *borttagen* funktion är inte längre tillgänglig i produkten.
- En *borttagen* funktion är inte i aktiv utveckling och kan tas bort i en kommande uppdatering.

Den här listan är avsedd att hjälpa dig att ta hänsyn till dessa borttagna och inaktuella funktioner för din planerings skull. 

Detaljerad information om objekt i appar för ekonomi och drift finns i [Tekniska referensrapporter](/dynamics/s-e/global/axtechrefrep_61). Du kan jämföra olika versioner av rapporterna för mer information om objekt som har ändrats eller tagits bort i varje version av appar för ekonomi och drift.

## <a name="feature-removal-effective-october-2021"></a>Funktionsborttagning som gäller oktober 2021

### <a name="microsoft-azure-sql-reports-in-lifecycle-services-lcs"></a>Microsoft Azure SQL-rapporter i Lifecycle Services (LCS)

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Alla aktiviteter och övervakning utförs internt, per plattform, via automation. Detta kräver inte någon manuell inblandning.|
| **Ersatt av en annan funktion?**   | Ja, det finns nu ett automatiskt system, vilket gör att dessa funktioner inte är föråldrade. |
| **Produktområden som påverkas**         | SQL-rapporter: Aktuell DTU, Aktuell DTU-information, Hämta låsdetaljer, Lista över aktuell planguide, Hämta lista över fråge-ID:n, Hämta SQL-frågeplan för ett givet plan-ID, Hämta frågeplaner och körningsstatus, Hämta begränsningskonfiguration, Hämta väntestatistik, Lista de dyraste frågorna |
| **Distribueringsalternativ**              | Molnbaserad distribution: Påverkar Microsoft-hanterade produktionsmiljöer och Nivå 2 till Nivå 5 sandbox-miljöer. |
| **Status**                         | Borttagen |

### <a name="azure-sql-actions-in-lcs"></a>Azure SQL-åtgärder i LCS

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Vi fasar ut vissa SQL-åtgärder i LCS. Alla aktiviteter och övervakning utförs internt, per plattform, via automation. Detta kräver inte någon manuell inblandning. |
| **Ersatt av en annan funktion?**   | Ja, det finns nu ett automatiskt system, vilket gör att dessa funktioner inte är föråldrade. |
| **Produktområden som påverkas**         | SQL-åtgärder: Skapa en planguide för att tvinga plan-ID, Skapa en planguide för att lägga till tabelltips, Ta bort planguide, Inaktivera/aktivera sidlås och låseskalering, Uppdatera statistik i en tabell, Återskapa index, Skapa index |
| **Distribueringsalternativ**              | Molnbaserad distribution: Påverkar Microsoft-hanterade produktionsmiljöer och Nivå 2 till Nivå 5 sandbox-miljöer. |
| **Status**                         | Borttagen |


## <a name="feature-deprecation-effective-october-2021"></a>Utfasning av funktioner från oktober 2021

### <a name="show-related-document-attachments-feature"></a>Funktionen "Visa relaterade dokumentbilagor"

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Funktionen returnerade oväntade resultat. |
| **Ersatt av en annan funktion?**   | Nej. Alla ytterligare planer angående den här funktionen kommer att kommuniceras genom vår standardprocess för utgivningsvåg. |
| **Produktområden som påverkas**         | Webbklient – erfarenhet av dokumentbilagan |
| **Distribueringsalternativ**              | Alla |
| **Status**                         | Inaktuell  |

## <a name="platform-updates-for-version-10023-of-finance-and-operations-apps"></a>Plattformsuppdateringar för version 10.0.23 av appar för ekonomi och drift

### <a name="ondbsynchronize-event"></a>Händelse för OnDBSynchronize

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Det finns ingen kontroll över hur den här händelsen kan utföras. |
| **Ersatt av en annan funktion?**   | Ja, flytta befintliga metoder som prenumererar på händelsen **OnDBSynchronize** till en utökad SysSetup-klass. |
| **Produktområden som påverkas**         | Databassynkronisering |
| **Distribueringsalternativ**              | Alla |
| **Status**                         | Inaktuell. Planerat borttagningsdatum är oktober 2022. |


### <a name="systemnotificationsmanageraddnotification-api"></a>SystemNotificationsManager.AddNotification API

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Microsoft kräver ytterligare parametrar när meddelanden läggs till. |
| **Ersatt av en annan funktion?**   | Ja **SystemNotificationsManager.AddSystemNotification()** API. Detta API kräver att du explicit anger ExpirationDateTime och RuleID för genererade meddelanden. |
| **Produktområden som påverkas**         | Webbklient |
| **Distribueringsalternativ**              | Alla |
| **Status**                         | Inaktuell. Planerat borttagningsdatum är april 2023. |

## <a name="platform-updates-for-version-10021-of-finance-and-operations-apps"></a>Plattformsuppdateringar för version 10.0.21 av appar för ekonomi och drift

### <a name="skype-for-business-online-support"></a>Support för Skype för företag online

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Skype för företag online har tagits bort. Mer information finns i [Tjänsten Skype för företag online har tagits bort](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/the-skype-for-business-online-service-has-retired/ba-p/2596601). |
| **Ersatt av en annan funktion?**   | Inte för närvarande, även om vi kan överväga att lägga till närvaro från Teams i framtiden.|
| **Produktområden som påverkas**         | Webbklient |
| **Distribueringsalternativ**              | Alla |
| **Status**                         | Inaktuell. Inställningen **Skype aktiverat** har inaktiverats med start i version 10.0.21. Borttagningen av den här inställningen är avsedd för april 2022. Funktionen kommer dock att upphöra att fungera när Skype-teamet har stängt av tjänsten. |
 
## <a name="feature-deprecation-effective-august-2021"></a>Utfasning av funktioner från augusti 2021

### <a name="microsoft-azure-sql-reports-in-lifecycle-services-lcs"></a>Microsoft Azure SQL-rapporter i Lifecycle Services (LCS)

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Alla aktiviteter och övervakning utförs internt, per plattform, via automation. Detta kräver inte någon manuell inblandning.|
| **Ersatt av en annan funktion?**   | Ja, det finns nu ett automatiskt system, vilket gör att dessa funktioner inte är föråldrade. |
| **Produktområden som påverkas**         | SQL-rapporter: Aktuell DTU, Aktuell DTU-information, Hämta låsdetaljer, Lista över aktuell planguide, Hämta lista över fråge-ID:n, Hämta SQL-frågeplan för ett givet plan-ID, Hämta frågeplaner och körningsstatus, Hämta begränsningskonfiguration, Hämta väntestatistik, Lista de dyraste frågorna |
| **Distribueringsalternativ**              | Molnbaserad distribution: Påverkar Microsoft-hanterade produktionsmiljöer och Nivå 2 till Nivå 5 sandbox-miljöer. |
| **Status**                         | Inaktuell: Planerat borttagningsdatum i oktober 2021. |

### <a name="azure-sql-actions-in-lcs"></a>Azure SQL-åtgärder i LCS

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Vi fasar ut vissa SQL-åtgärder i LCS. Alla aktiviteter och övervakning utförs internt, per plattform, via automation. Detta kräver inte någon manuell inblandning. |
| **Ersatt av en annan funktion?**   | Ja, det finns nu ett automatiskt system, vilket gör att dessa funktioner inte är föråldrade. |
| **Produktområden som påverkas**         | SQL-åtgärder: Skapa en planguide för att tvinga plan-ID, Skapa en planguide för att lägga till tabelltips, Ta bort planguide, Inaktivera/aktivera sidlås och låseskalering, Uppdatera statistik i en tabell, Återskapa index, Skapa index |
| **Distribueringsalternativ**              | Molnbaserad distribution: Påverkar Microsoft-hanterade produktionsmiljöer och Nivå 2 till Nivå 5 sandbox-miljöer. |
| **Status**                         | Inaktuell: Planerat borttagningsdatum i oktober 2021. |

## <a name="feature-deprecation-effective-may-2021"></a>Utfasning av funktioner från maj 2021

### <a name="globalization-portal-in-lifecycle-services-lcs"></a>Globaliseringsportal i Lifecycle Services (LCS)

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Vi avaktar globaliseringsportalen i LCS eftersom den här funktionen har ersatts av andra LCS-baserade tjänster. |
| **Ersatt av en annan funktion?**   | Ja, den här funktionen ersätts av LCS [Problemsökning](../lifecycle-services/issue-search-lcs.md) och [Tjänst för inlämning av dynamiska regler](../lcs-solutions/submit-localization-alerts.md). |
| **Produktområden som påverkas**         | Globaliseringsportal i LCS|
| **Distribueringsalternativ**              | Molndistribution |
| **Status**                         | Inaktuell: Planerat borttagningsdatum i maj 2022. |


## <a name="feature-removed-effective-january-28-2021"></a>Funktion borttagen 28 januari 2021

### <a name="batch-job-to-handle-sql-index-defragmentation"></a>Batchjobbet ska hantera defragmentering av SQL-index

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Den här funktionen har tagits bort för att minska omkostnaderna för hantering, övervakning och underhåll av indexhanteringen för kunder. |
| **Ersatt av en annan funktion?**   | Framåt kommer indexunderhållet att utföras av Microsoft-tjänster. Detta sker kontinuerligt utan att användararbetsbelastningarna påverkas. |
| **Produktområden som påverkas**         | appar för ekonomi och drift|
| **Distribueringsalternativ**              | Molnbaserad distribution – påverkar Microsoft-hanterade produktionsmiljöer och Nivå 2 via Nivå 5 miljöer med begränsat läge. |
| **Status**                         | Denna funktion är borttagen. |


## <a name="platform-updates-for-version-10017-of-finance-and-operations-apps"></a>Plattformsuppdateringar för version 10.0.17 av appar för ekonomi och drift


### <a name="visual-studio-2015"></a>Visual Studio2015

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | För att stödja de senaste versionerna av Visual Studio måste vissa ändringar göras i tilläggen X++ Visual Studio. Dessa ändringar är inkompatibla med Visual Studio 2015. |
| **Ersatt av en annan funktion?**   | Visual Studio 2017 ersätter Visual Studio 2015 som den distribuerade och begärda versionen. |
| **Produktområden som påverkas**         | Visual Studio utvecklingsverktyg. |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | Inaktuell: Vid uppdatering tas de föregående X++-verktygen bort från Visual Studio 2015 och de uppdaterade verktygen installeras inte i Visual Studio 2015. Det påverkar inte värden för byggen. För att bygga virtuella maskiner måste bygg-pipeline (byggdefinition) uppdateras manuellt för att ändra beroendet från MSBuild 14.0 (Visual Studio 2015) till MSBuild 15.0 (Visual Studio 2017) som beskrivs i [Uppdatera en äldre pipeline i Azure Pipelines](../dev-tools/pipeline-msbuild-update.md). |

### <a name="user-avatar"></a>Användaravatar 

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Användaravatar som visas till höger om navigeringsfältet har hämtats med ett API från rubrikkontrollen Dynamics 365 är utfasad. |
| **Ersatt av en annan funktion?**   | Användarna ser sina initialer i en cirkel i navigeringsfältet istället. Detta är samma visuella som för närvarande används på utvecklingsmaskiner. |
| **Produktområden som påverkas**         | Webbklient |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | Borttagen från version 10.0.17 |

### <a name="enterprise-portal-ep-deprecation"></a>Enterprise Portal (EP) inaktuell  

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Metadata som är associerade med Dynamics AX 2012 Enterprise Portal (EP) är utfasad eftersom EP aldrig haft stöd i Ekonomi- och Drift-appar. |
| **Ersatt av en annan funktion?**   | Nej |
| **Produktområden som påverkas**         | Webbklient |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | Inaktuell: All EP-kod ska tas bort i versionen för oktober 2021. |

## <a name="deprecation-effective-december-2020"></a>Utfasning från december 2020

### <a name="internet-explorer-11-support-for-dynamics-365-is-deprecated"></a>Internet Explorer 11-stöd för Dynamics 365 är inaktuellt

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Från och med december 2020 kommer Microsoft Internet Explorer 11-stöd för samtliga Dynamics 365- och Dynamics Lifecycle Services (LCS)-produkter att dras in, och Internet Explorer 11 kommer inte att stödjas efter augusti 2021.<br><br>Detta påverkar kunder som använder Dynamics 365-produkter och LCS som har utformats för användning med ett Internet Explorer 11-gränssnitt. Efter augusti 2021 stöds inte Internet Explorer 11 för sådana Dynamics 365-produkter eller LCS. |
| **Ersatt av en annan funktion?**   | Vi rekommenderar våra kunder att övergå till Microsoft Edge.|
| **Produktområden som påverkas**         | Alla Dynamics 365-produkter och LCS |
| **Distribueringsalternativ**              | Allt|
| **Status**                         | Inaktuell: Internet Explorer 11 kommer inte att stödjas efter augusti 2021.|

## <a name="platform-updates-for-version-10015-of-finance-and-operations-apps"></a>Plattformsuppdateringar för version 10.0.15 av appar för ekonomi och drift

### <a name="visual-studio-add-in-to-apply-metadata-hotfixes"></a>Visual Studio tillägg för att tillämpa snabbkorrigeringar för metadata

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Snabbkorrigeringar för metadata stöds inte längre med [en version](../../fin-ops/get-started/one-version.md) tjänst uppdatering som introducerades i juli 2018 med version 8.1. |
| **Ersatt av en annan funktion?**   | Enskilda snabbkorrigeringar för metadata är inte tillgängliga för versioner som stöds. Kumulativa kvalitetsuppdateringar tillämpas i stället. |
| **Produktområden som påverkas**         | Visual Studio tillägg |
| **Distribueringsalternativ**              | Virtuella datorers utveckling |
| **Status**                         | Med version 10.0.15 ingår inte längre tillägget i Visual Studio-verktygen. |


## <a name="platform-updates-for-version-10014-of-finance-and-operations-apps"></a>Plattformsuppdateringar för version 10.0.14 av appar för ekonomi och drift

### <a name="online-users-page"></a>Sidan Onlineanvändare 

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Det här är en äldre sida som skapats för tidigare klient/server-arkitektur. Informationen på den här sidan är inte alltid korrekt, vilket kan vara förvirrande och missvisande. |
| **Ersatt av en annan funktion?**   | Vi kommer att tillhandahålla en ny sida i en framtida uppdatering.|
| **Produktområden som påverkas**         | Systemadministration |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | I oktober 2021 kommer det här formuläret att tas bort.   |


## <a name="platform-updates-for-version-10013-of-finance-and-operations-apps"></a>Plattformsuppdateringar för version 10.0.13 av appar för ekonomi och drift


### <a name="custom-code-defined-in-ssrs-report-properties"></a>Anpassad kod som definierats i SSRS-rapportens egenskaper 

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | I allmänhet erbjuder anpassad kod begränsade fördelar men kräver samtidigt avsevärd resurshantering och beräkning för stöd. Anpassad kod används främst av rapportförfattare för att anropa offentliga metoder från en anpassad kodsammansättning. Den molnbaserade tjänsten stöder dock inte referenser till anpassade sammansättningar för SSRS-rapporter. |
| **Ersatt av en annan funktion?**   | Rapportförfattare kan välja att fortsätta att referera till offentliga .NET API:er för matematik-, konverterings- och formatåtgärder från valfritt textruteuttryck. Mer information finns i [Lägga till kod i en rapport (SSRS)](/sql/reporting-services/report-design/add-code-to-a-report-ssrs).  |
| **Produktområden som påverkas**         | Delmängd av design för programrapport som definierats i RDL som innehåller anpassad kod. |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | Med version 10.0.13 börjar kompileraren att utfärda en varning för instanser där anpassad kod identifieras i en rapportdefinition för SSRS. Lös problemet genom att öppna rapportdesignens definition och ta bort alla anpassade kodartefakter. Den här varningen kommer att ersättas med ett kompileringsfel i en framtida uppdatering.   |

### <a name="upgrade-of-three-jquery-component-libraries"></a>Uppgradering av tre jQuery-komponentbibliotek 

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Tre jQuery-komponentbibliotek uppdateras för säkerhetskorrigeringar och för att bibehålla valutan.   
| **Ersatt av en annan funktion?**   | Följande bibliotekpåverkas: jQuery (till version 3.5.0 från version 2.1.4), jQuery UI (till version 1.12.1 från version 1.11.4), jQuery qTip (till version 3.0.3 från 2.2.1). Vägledningen för migreringen har tillhandahållits online av jQuery.  |
| **Produktområden som påverkas**         | Utökningsbara kontroller, anpassad JavaScript-kod använda gamla API:er |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | Med version 10.0.13/plattformsuppdatering 37 kan kunderna flytta till de senaste biblioteken genom att aktivera funktionen "uppgradera tre jQuery komponentbibliotek". Det är obligatoriskt att flytta till de nya biblioteken med utgåvan från april 2021 för att kunna migrera berörda API:er.   |

### <a name="existing-grid-controlforcelegacygrid-api"></a>Befintlig rutnätskontroll/forceLegacyGrid() API

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Den befintliga rutnätskontrollen ersätts av den nya rutnätskontrollen. |
| **Ersatt av en annan funktion?**   | Den [nya rutnätskontrollen](../..//fin-ops/get-started/grid-capabilities.md) |
| **Produktområden som påverkas**         | Webbklient |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | I version 10.0.13 är den nya rutnätskontrollen allmänt tillgänglig och kunder kan välja att aktivera den här funktionen. Den nya rutnätskontrollen blir som standard på med versionen från oktober 2021 och är för närvarande obligatorisk i april 2022. När den nya rutnätskontrollen blir obligatorisk kommer **forceLegacyGrid()** API inte längre att användas. |

### <a name="personalization-without-saved-views"></a>Anpassning utan sparade vyer 

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Undersystemet för anpassning har dragits av med funktionen Sparade vyer så att den har bättre prestanda och erbjuder ytterligare funktioner. |
| **Ersatt av en annan funktion?**   | Sparade vyer |
| **Produktområden som påverkas**         | Webbklient |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | I version 10.0.13/plattformsuppdatering 37 är funktionen Sparade vyer vanligtvis tillgänglig och kunder kan välja att aktivera den här funktionen. Funktionen sparade vyer kommer att vara obligatorisk i versionen oktober 2021. |


## <a name="platform-updates-for-version-10012-of-finance-and-operations-apps"></a>Plattformsuppdateringar för version 10.0.12 av appar för ekonomi och drift

### <a name="grid-or-group-control-form-extensions-containing-invalid-field-references"></a>Formulärtillägg för rutnät- eller gruppkontroll som innehåller ogiltiga fältreferenser

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Datagruppegenskapen för rutnäts- eller gruppkontroller används för att automatiskt visa alla fält i en fältgrupp. En rutnäts- eller gruppkontroll som läggs till av tillägget kan innehålla fält som inte längre definieras i fältgruppen, eller saknas fält som är definierade i fältgruppen. Detta kan orsaka inkonsekvent beteende vid körning. Plattformsuppdateringar för version 10.0.12 av appar för ekonomi och drift kategoriserar nu det här problemet som ett *kompilatorvarning*. Du åtgärdar det här problemet genom att öppna formulärtillägget och spara det.
| **Ersatt av en annan funktion?**   | Den här kompilatorvarningen kommer att ersättas med ett kompileringsfel i en framtida uppdatering. |
| **Produktområden som påverkas**         | Visual Studio utvecklingsverktyg. |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | En kompilatorvarning införs i plattformsuppdateringar för version 10.0.12 för appar för ekonomi och drift. |

## <a name="platform-updates-for-version-10011-of-finance-and-operations-apps"></a>Plattformsuppdateringar för version 10.0.11 av appar för ekonomi och drift

### <a name="explicit-safe-lists-for-self-service-environments"></a>Explicita säkra listor för självbetjäningsmiljöer

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Processen för att flytta IP till säkra listor har ändrats. Självbetjäning stöder inte längre IP säkra listor. |
| **Ersatt av en annan funktion?**   | Mer information finns i [Konfigurera Azure Active Directory villkorlig åtkomst](/appcenter/general/configuring-aad-conditional-access).|
| **Produktområden som påverkas**         | Säkerhet |
| **Distribueringsalternativ**              | Moln |
| **Status**                         | Inaktuell: Den här funktionen är helt utfasad för självbetjäningsdistributioner. |

### <a name="visual-studio-2015"></a>Visual Studio2015

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | För att stödja de senaste versionerna av Visual Studio måste vissa ändringar göras i tilläggen X++ Visual Studio. Dessa ändringar är inkompatibla med Visual Studio 2015. |
| **Ersatt av en annan funktion?**   | Visual Studio 2017 ersätter Visual Studio 2015 som den distribuerade och begärda versionen. |
| **Produktområden som påverkas**         | Visual Studio utvecklingsverktyg. |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | Virtuella datorer som distribueras med version 10.0.13 (plattformsuppdatering 37) eller senare innehåller Visual Studio 2017. Version 10.0.16 (plattformsuppdatering 40) är den slutliga versionen som har stöd för Visual Studio 2015. Virtuella datorer med endast Visual Studio 2015 kommer inte att kunna uppdateras till version 10.0.17 (plattformsuppdatering 41). |

### <a name="field-groups-containing-invalid-field-references"></a>Fältgrupper innehåller ogiltiga fältreferenser

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Fältgrupper i definitioner av registermetadata kan innehålla fältreferenser som inte är giltiga. Om dessa fältgrupper distribueras kan de orsaka körningsfel i Financial Reporting och Microsoft SQL Server Reporting Services (SSRS). Plattformsuppdatering 23 introducerade kompileraren *varning* om att detta problem med metadata har åtgärdats. Plattformsuppdateringar för version 10.0.11 av appar för ekonomi och drift kategoriserar nu det här problemet som ett *kompilatorfel*.<p>Gör så här om du vill åtgärda problemet.</p><ol><li>Ta bort den ogiltiga fältreferensen från tabellens fältgruppdefinition.</li><li>Kompilera om.</li><li>Kontrollera att eventuella fel har åtgärdats.</li></ol> |
| **Ersatt av en annan funktion?**   | Detta kompilatorfel ersätter kompilatorvarningen permanent.  |
| **Produktområden som påverkas**         | Visual Studio utvecklingsverktyg. |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | Inaktuell: Kompilatorvarningen är ett kompilatorfel i plattformsuppdateringar för version 10.0.11 av appar för ekonomi och drift. |

### <a name="isv-licenses-created-by-using-the-sha1-hashing-algorithm"></a>ISV-licenser som skapats med hjälp av SHA1-hashing-algoritm

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Processen för att skapa oberoende program varu leverantörslicenser (ISV) har ändrats. Mer information finns i [oberoende programvaruleverantör (ISV)-licensiering](../dev-tools/isv-licensing.md#appendix-create-self-signed-certificates-for-test-purposes). |
| **Ersatt av en annan funktion?**   | Ja. Skapa licenser med hjälp av Windows PowerShell. |
| **Produktområden som påverkas**         | Visual Studio utvecklingsverktyg. |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | Inaktuella: ISV-licenser som skapats med hjälp av SHA1-hashing-algoritmen. Den här algoritmen är beroende av certifikat som har skapats med verktyget MakeCert och detta verktyg är inaktuellt.<br><br>Inaktuell: SHA1 för säkerhets- eller hashing-syfte används. SHA1 kommer att upphöra att fungera i början av 2021. Därför bör den inte längre användas.<br><br>Borttaget : stöd för inkommande eller utgående begäran via TLS (Transport Layer Security) 1.0 och TLS 1.1. |

## <a name="platform-update-32"></a>Plattform update 32

### <a name="workflow-request-change-dialog-box-no-longer-includes-user-selection-drop-down-list"></a>Dialogrutan ändra arbetsflödesförfrågan innehåller inte längre listrutan för användarval

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Detta är ett säkerhetsproblem eftersom begäran om ändring kan skickas till en oavsiktlig användare. Detta var också ett användbarhetsproblem eftersom det tvingade användaren att avgöra vem som har skapat arbetsflödet och manuellt välja dem manuellt.  |
| **Ersatt av en annan funktion?**   | Nej |
| **Produktområden som påverkas**         | Arbetsflöde |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | Listrutan för användarval har tagits bort från dialogrutan ändring av begäran i plattformsuppdatering 32. Begäranden om ändring av begäran kommer att skickas automatiskt till upphovspersonen som avsett. Mer information om den här funktionen finns i [åtgärder i godkännandeprocesser för arbetsflöde](../../fin-ops/organization-administration/workflow-actions.md?toc=%2fdynamics365%2fcommerce%2ftoc.json#request-change). |

### <a name="embedded-drill-through-links-are-no-longer-supported-in-paginated-documents-rendered-by-the-cloud-hosted-service"></a>Inbäddade länkar för detaljerad visning stöds inte längre i sidbrytningsdokument som renderas av den molnbaserade tjänsten 

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Navigerings-URL:er som är inbäddade i dokument som tillhandahålls av tjänsten kan innehålla känsliga affärsdata. Vi tar bort stöd för inbäddade detaljgranskningslänkar i dokument som en säkerhetsåtgärd för att skydda kundens data ytterligare. Användarna får också nytta av förbättrad prestanda samtidigt som de skapar dokument som ett resultat av ändringen.  |
| **Ersatt av en annan funktion?**   | Nej |
| **Produktområden som påverkas**         | Rapportering |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | Den här funktionen tas aktivt bort från tjänsten.<br><br>Den moderna klienten erbjuder flera alternativ för att producera vyer som innehåller automatiskt genererade länkar som hjälper dig att navigera i programmet. Sidbrytningsdokument som renderas av tjänsten rekommenderas för extern kommunikation som har e-post, arkiverats och skrivits ut för mottagare. Vi har förbättrat upplevelsen att förhandsgranska dokument direkt i webbläsaren, som ger direkt åtkomst till lokala skrivare. Mer information finns i [Förhandsgranska PDF-dokument med ett inbäddat visningsprogram](../analytics/preview-pdf-documents.md). |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a>Tidigare meddelanden om borttagna eller inaktuella funktioner
Om du vill veta mer om funktioner som har tagits bort eller ersatts i tidigare versioner, se [borttagna eller inaktuella funktioner i tidigare versioner](../migration-upgrade/deprecated-features.md).



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
