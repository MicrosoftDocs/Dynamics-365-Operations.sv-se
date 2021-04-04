---
title: Borttagna eller avskrivna plattformsfunktioner
description: I det här avsnittet beskrivs funktioner som har tagits bort, eller har planerats för borttagning i plattformsuppdatering av Finance and Operations-appar.
author: sericks007
manager: AnnBe
ms.date: 02/16/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2020-02-29
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: f363b122e30990f5b36e69fd8fe271bdc15e2e79
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5564004"
---
# <a name="removed-or-deprecated-platform-features"></a>Borttagna eller avskrivna plattformsfunktioner

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs funktioner som har tagits bort, eller har planerats för borttagning i plattformsuppdatering av Finance and Operations-appar.

- En *borttagen* funktion är inte längre tillgänglig i produkten.
- En *borttagen* funktion är inte i aktiv utveckling och kan tas bort i en kommande uppdatering.

Den här listan är avsedd att hjälpa dig att ta hänsyn till dessa borttagna och inaktuella funktioner för din planerings skull. 

Detaljerad information om objekt i Finance and Operations-appar hittas i [Tekniska referensrapporter](https://docs.microsoft.com/dynamics/s-e/global/axtechrefrep_61). Du kan jämföra olika versioner av rapporterna för mer information om objekt som har ändrats eller tagits bort i varje version av Finance and Operations-appar.

## <a name="feature-removed-effective-january-28-2021"></a>Funktion borttagen 28 januari 2021

### <a name="batch-job-to-handle-sql-index-defragmentation"></a>Batchjobbet ska hantera defragmentering av SQL-index

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Den här funktionen har tagits bort för att minska omkostnaderna för hantering, övervakning och underhåll av indexhanteringen för kunder. |
| **Ersatt av en annan funktion?**   | Framåt kommer indexunderhållet att utföras av Microsoft-tjänster. Detta sker kontinuerligt utan att användararbetsbelastningarna påverkas. |
| **Produktområden som påverkas**         | Finance and Operations-appar|
| **Distribueringsalternativ**              | Molnbaserad distribution – påverkar Microsoft-hanterade produktionsmiljöer och Nivå 2 via Nivå 5 miljöer med begränsat läge. |
| **Status**                         | Denna funktion är borttagen. |


## <a name="platform-updates-for-version-10017-of-finance-and-operations-apps"></a>Plattformsuppdateringar för version 10.0.17 för Finance and Operations-appar

> [!IMPORTANT]
> Version 10.0.17 finns tillgänglig i en förhandsversion. Funktionen och dess innehåll kan ändras. Mer information om förhandsversioner finns i [Frågor och svar om tjänstuppdateringar för en version](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/one-version).

### <a name="visual-studio-2015"></a>Visual Studio2015

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | För att stödja de senaste versionerna av Visual Studio måste vissa ändringar göras i tilläggen X++ Visual Studio. Dessa ändringar är inkompatibla med Visual Studio 2015. |
| **Ersatt av en annan funktion?**   | Visual Studio 2017 ersätter Visual Studio 2015 som den distribuerade och begärda versionen. |
| **Produktområden som påverkas**         | Visual Studio utvecklingsverktyg. |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | Inaktuell. Vid uppdatering tas de föregående X++-verktygen bort från Visual Studio 2015 och de uppdaterade verktygen installeras inte i Visual Studio 2015. Det påverkar inte värden för byggen. För att bygga virtuella maskiner måste bygg-pipeline (byggdefinition) uppdateras manuellt för att ändra beroendet från MSBuild 14.0 (Visual Studio 2015) till MSBuild 15.0 (Visual Studio 2017) som beskrivs i [Uppdatera en äldre pipeline i Azure Pipelines](../dev-tools/pipeline-msbuild-update.md). |

### <a name="user-avatar"></a>Användaravatar 

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Användaravatar som visas till höger om navigeringsfältet har hämtats med ett API från rubrikkontrollen Dynamics 365 är utfasad. |
| **Ersatt av en annan funktion?**   | Användarna ser sina initialer i en cirkel i navigeringsfältet istället. Detta är samma visuella som för närvarande används på utvecklingsmaskiner. |
| **Produktområden som påverkas**         | Webbklient |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | Borttagen från version 10.0.17 |

### <a name="enterprise-portal-ep-deprecation"></a>Enterprise Portal (EP) inaktuell  

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Metadata som är associerade med Dynamics AX 2012 Enterprise Portal (EP) är utfasad, eftersom EP aldrig har stöds i Finance and Operations-appar. |
| **Ersatt av en annan funktion?**   | Nr |
| **Produktområden som påverkas**         | Webbklient |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | Inaktuell. All EP-kod ska tas bort i versionen för oktober 2021. |

## <a name="platform-updates-for-version-10015-of-finance-and-operations-apps"></a>Plattformsuppdateringar för version 10.0.15 för Finance and Operations-appar

### <a name="internet-explorer-11-support-for-dynamics-365-is-deprecated"></a>Internet Explorer 11-stöd för Dynamics 365 är inaktuellt

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Från och med december 2020 kommer Microsoft Internet Explorer 11-stöd för samtliga Dynamics 365-produkter att betraktas som inaktuellt, och Internet Explorer 11 kommer inte att stödjas efter augusti 2021.<br><br>Detta påverkar kunder som använder Dynamics 365-produkter som har utformats för användning med ett Internet Explorer 11-gränssnitt. Efter augusti 2021 stöds inte Internet Explorer 11 för sådana Dynamics 365-produkter. |
| **Ersatt av en annan funktion?**   | Vi rekommenderar våra kunder att övergå till Microsoft Edge.|
| **Produktområden som påverkas**         | Alla Dynamics 365-produkter |
| **Distribueringsalternativ**              | Allt|
| **Status**                         | Inaktuell. Internet Explorer 11 kommer inte att stödjas efter augusti 2021.|


### <a name="visual-studio-add-in-to-apply-metadata-hotfixes"></a>Visual Studio tillägg för att tillämpa snabbkorrigeringar för metadata

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Snabbkorrigeringar för metadata stöds inte längre med [en version](../../fin-ops/get-started/one-version.md) tjänst uppdatering som introducerades i juli 2018 med version 8.1. |
| **Ersatt av en annan funktion?**   | Enskilda snabbkorrigeringar för metadata är inte tillgängliga för versioner som stöds. Kumulativa kvalitetsuppdateringar tillämpas i stället. |
| **Produktområden som påverkas**         | Visual Studio tillägg |
| **Distribueringsalternativ**              | Virtuella datorers utveckling |
| **Status**                         | Med version 10.0.15 ingår inte längre tillägget i Visual Studio-verktygen. |


## <a name="platform-updates-for-version-10014-of-finance-and-operations-apps"></a>Plattformsuppdateringar för version 10.0.14 för Finance and Operations-appar

### <a name="online-users-page"></a>Sidan Onlineanvändare 

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Det här är en äldre sida som skapats för tidigare klient/server-arkitektur. Informationen på den här sidan är inte alltid korrekt, vilket kan vara förvirrande och missvisande. |
| **Ersatt av en annan funktion?**   | Vi kommer att tillhandahålla en ny sida i en framtida uppdatering.|
| **Produktområden som påverkas**         | Systemadministration |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | I oktober 2021 kommer det här formuläret att tas bort.   |


## <a name="platform-updates-for-version-10013-of-finance-and-operations-apps"></a>Plattformsuppdateringar för version 10.0.13 för Finance and Operations-appar


### <a name="custom-code-defined-in-ssrs-report-properties"></a>Anpassad kod som definierats i SSRS-rapportens egenskaper 

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | I allmänhet erbjuder anpassad kod begränsade fördelar men kräver samtidigt avsevärd resurshantering och beräkning för stöd. Anpassad kod används främst av rapportförfattare för att anropa offentliga metoder från en anpassad kodsammansättning. Den molnbaserade tjänsten stöder dock inte referenser till anpassade sammansättningar för SSRS-rapporter. |
| **Ersatt av en annan funktion?**   | Rapportförfattare kan välja att fortsätta att referera till offentliga .NET API:er för matematik-, konverterings- och formatåtgärder från valfritt textruteuttryck. Mer information finns i [Lägga till kod i en rapport (SSRS)](https://docs.microsoft.comsql/reporting-services/report-design/add-code-to-a-report-ssrs?view=sql-server-ver15).  |
| **Produktområden som påverkas**         | Delmängd av design för programrapport som definierats i RDL som innehåller anpassad kod. |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | Med version 10.0.13 börjar kompileraren att utfärda en varning för instanser där anpassad kod identifieras i en rapportdefinition för SSRS. Lös problemet genom att öppna rapportdesignens definition och ta bort alla anpassade kodartefakter. Den här varningen kommer att ersättas med ett kompileringsfel i en framtida uppdatering.   |

### <a name="upgrade-of-three-jquery-component-libraries"></a>Uppgradering av tre jQuery-komponentbibliotek 

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Tre jQuery-komponentbibliotek uppdateras för säkerhetskorrigeringar och för att bibehålla valutan.   
| **Ersatt av en annan funktion?**   | Följande bibliotekpåverkas: jQuery (till version 3.5.0 från version 2.1.4), jQuery UI (till version 1.12.1 från version 1.11.4), jQuery qTip (till version 3.0.3 från 2.2.1). Vägledningen för migreringen har tillhandahållits online av jQuery.  |
| **Produktområden som påverkas**         | Utökningsbara kontroller, anpassad JavaScript-kod använda gamla API:er |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | Med version 10.0.13/plattformsuppdatering 37 kan kunderna flytta till de senaste biblioteken genom att aktivera funktionen "uppgradera tre jQuery komponentbibliotek". Det är obligatoriskt att flytta till de nya biblioteken med utgåvan från april 2021 för att kunna migrera berörda API:er.   |

### <a name="existing-grid-controlforcelegacygrid-api"></a>Befintlig rutnätskontroll/forceLegacyGrid() API

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Den befintliga rutnätskontrollen ersätts av den nya rutnätskontrollen. |
| **Ersatt av en annan funktion?**   | Den [nya rutnätskontrollen](../..//fin-ops/get-started/grid-capabilities.md) |
| **Produktområden som påverkas**         | Webbklient |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | I version 10.0.13 är den nya rutnätskontrollen allmänt tillgänglig och kunder kan välja att aktivera den här funktionen. Den nya rutnätskontrollen kommer att vara obligatorisk i versionen oktober 2021. När den nya rutnätskontrollen blir obligatorisk kommer **forceLegacyGrid()** API inte längre att användas. |

### <a name="personalization-without-saved-views"></a>Anpassning utan sparade vyer 

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Undersystemet för anpassning har dragits av med funktionen Sparade vyer så att den har bättre prestanda och erbjuder ytterligare funktioner. |
| **Ersatt av en annan funktion?**   | Sparade vyer |
| **Produktområden som påverkas**         | Webbklient |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | I version 10.0.13/plattformsuppdatering 37 är funktionen Sparade vyer vanligtvis tillgänglig och kunder kan välja att aktivera den här funktionen. Funktionen sparade vyer kommer att vara obligatorisk i versionen oktober 2021. |


## <a name="platform-updates-for-version-10012-of-finance-and-operations-apps"></a>Plattformsuppdateringar för version 10.0.12 för Finance and Operations-appar

### <a name="grid-or-group-control-form-extensions-containing-invalid-field-references"></a>Formulärtillägg för rutnät- eller gruppkontroll som innehåller ogiltiga fältreferenser

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Datagruppegenskapen för rutnäts- eller gruppkontroller används för att automatiskt visa alla fält i en fältgrupp. En rutnäts- eller gruppkontroll som läggs till av tillägget kan innehålla fält som inte längre definieras i fältgruppen, eller saknas fält som är definierade i fältgruppen. Detta kan orsaka inkonsekvent beteende vid körning. Plattformsuppdateringar för version 10.0.12 av Finance and Operations-appar kategoriserar nu det här problemet som ett kompilator *varning*. Du åtgärdar det här problemet genom att öppna formulärtillägget och spara det.
| **Ersatt av en annan funktion?**   | Den här kompilatorvarningen kommer att ersättas med ett kompileringsfel i en framtida uppdatering. |
| **Produktområden som påverkas**         | Visual Studio utvecklingsverktyg. |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | En kompilatorvarning införs i plattformsuppdateringar för version 10.0.12 för Finance and Operations-appar. |

## <a name="platform-updates-for-version-10011-of-finance-and-operations-apps"></a>Plattformsuppdateringar för version 10.0.11 för Finance and Operations-appar

### <a name="explicit-safe-lists-for-self-service-environments"></a>Explicita säkra listor för självbetjäningsmiljöer

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Processen för att flytta IP till säkra listor har ändrats. Självbetjäning stöder inte längre IP säkra listor. |
| **Ersatt av en annan funktion?**   | Mer information finns i [Konfigurera Azure Active Directory villkorlig åtkomst](https://docs.microsoft.com/appcenter/general/configuring-aad-conditional-access).|
| **Produktområden som påverkas**         | Säkerhet |
| **Distribueringsalternativ**              | Moln |
| **Status**                         | **Inaktuell:** Den här funktionen är helt utfasad för självbetjäningsdistributioner. |

### <a name="visual-studio-2015"></a>Visual Studio2015

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | För att stödja de senaste versionerna av Visual Studio måste vissa ändringar göras i tilläggen X++ Visual Studio. Dessa ändringar är inkompatibla med Visual Studio 2015. |
| **Ersatt av en annan funktion?**   | Visual Studio 2017 ersätter Visual Studio 2015 som den distribuerade och begärda versionen. |
| **Produktområden som påverkas**         | Visual Studio utvecklingsverktyg. |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | Virtuella datorer som distribueras med version 10.0.13 (plattformsuppdatering 37) eller senare innehåller Visual Studio 2017. Version 10.0.16 (plattformsuppdatering 40) är den slutliga versionen som har stöd för Visual Studio 2015. Virtuella datorer med endast Visual Studio 2015 kommer inte att kunna uppdateras till version 10.0.17 (plattformsuppdatering 41). |

### <a name="field-groups-containing-invalid-field-references"></a>Fältgrupper innehåller ogiltiga fältreferenser

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Fältgrupper i definitioner av registermetadata kan innehålla fältreferenser som inte är giltiga. Om dessa fältgrupper distribueras kan de orsaka körningsfel i Financial Reporting och Microsoft SQL Server Reporting Services (SSRS). Plattformsuppdatering 23 introducerade kompileraren *varning* om att detta problem med metadata har åtgärdats. Plattformsuppdateringar för version 10.0.11 av Finance and Operations-appar kategoriserar det här problemet som ett kompilator *fel*.<p>Gör så här om du vill åtgärda problemet.</p><ol><li>Ta bort den ogiltiga fältreferensen från tabellens fältgruppdefinition.</li><li>Kompilera om.</li><li>Kontrollera att eventuella fel har åtgärdats.</li></ol> |
| **Ersatt av en annan funktion?**   | Detta kompilatorfel ersätter kompilatorvarningen permanent.  |
| **Produktområden som påverkas**         | Visual Studio utvecklingsverktyg. |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | **Inaktuell:** kompilatorvarningen är ett kompileringsfel i plattformsuppdateringar för version 10.0.11 av Finance and Operations-appar. |

### <a name="isv-licenses-created-by-using-the-sha1-hashing-algorithm"></a>ISV-licenser som skapats med hjälp av SHA1-hashing-algoritm

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Processen för att skapa oberoende program varu leverantörslicenser (ISV) har ändrats. Mer information finns i [oberoende programvaruleverantör (ISV)-licensiering](../dev-tools/isv-licensing.md#appendix-create-self-signed-certificates-for-test-purposes). |
| **Ersatt av en annan funktion?**   | Ja. Skapa licenser med hjälp av Windows PowerShell. |
| **Produktområden som påverkas**         | Visual Studio utvecklingsverktyg. |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | <strong>Inaktuella:</strong> ISV-licenser som skapats med hjälp av SHA1-hashing-algoritmen. Den här algoritmen är beroende av certifikat som har skapats med verktyget MakeCert och detta verktyg är inaktuellt.<p><strong>Inaktuell:</strong> SHA1 för säkerhets- eller hashing-syfte används. SHA1 kommer att upphöra att fungera i början av 2021. Därför bör den inte längre användas.<p><strong>Borttaget</strong> : stöd för inkommande eller utgående begäran via TLS (Transport Layer Security) 1.0 och TLS 1.1. |

## <a name="platform-update-32"></a>Plattform update 32

### <a name="workflow-request-change-dialog-box-no-longer-includes-user-selection-drop-down-list"></a>Dialogrutan ändra arbetsflödesförfrågan innehåller inte längre listrutan för användarval
|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Detta är ett säkerhetsproblem eftersom begäran om ändring kan skickas till en oavsiktlig användare. Detta var också ett användbarhetsproblem eftersom det tvingade användaren att avgöra vem som har skapat arbetsflödet och manuellt välja dem manuellt.  |
| **Ersatt av en annan funktion?**   | Nej |
| **Produktområden som påverkas**         | Arbetsflöde |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | Listrutan för användarval har tagits bort från dialogrutan ändring av begäran i plattformsuppdatering 32. Begäranden om ändring av begäran kommer att skickas automatiskt till upphovspersonen som avsett. Mer information om den här funktionen finns i [åtgärder i godkännandeprocesser för arbetsflöde](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/workflow-actions?toc=%2Fdynamics365%2Fcommerce%2Ftoc.json#request-change). |

### <a name="embedded-drill-through-links-are-no-longer-supported-in-paginated-documents-rendered-by-the-cloud-hosted-service"></a>Inbäddade länkar för detaljerad visning stöds inte längre i sidbrytningsdokument som renderas av den molnbaserade tjänsten 
|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Navigerings-URL:er som är inbäddade i dokument som tillhandahålls av tjänsten kan innehålla känsliga affärsdata. Vi tar bort stöd för inbäddade detaljgranskningslänkar i dokument som en säkerhetsåtgärd för att skydda kundens data ytterligare. Användarna får också nytta av förbättrad prestanda samtidigt som de skapar dokument som ett resultat av ändringen.  |
| **Ersatt av en annan funktion?**   | Nr |
| **Produktområden som påverkas**         | Rapportering |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | Den här funktionen tas aktivt bort från tjänsten.<br><br>Den moderna klienten erbjuder flera alternativ för att producera vyer som innehåller automatiskt genererade länkar som hjälper dig att navigera i programmet. Sidbrytningsdokument som renderas av tjänsten rekommenderas för extern kommunikation som har e-post, arkiverats och skrivits ut för mottagare. Vi har förbättrat upplevelsen att förhandsgranska dokument direkt i webbläsaren, som ger direkt åtkomst till lokala skrivare. Mer information finns i [Förhandsgranska PDF-dokument med ett inbäddat visningsprogram](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/preview-pdf-documents). |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a>Tidigare meddelanden om borttagna eller inaktuella funktioner
Om du vill veta mer om funktioner som har tagits bort eller ersatts i tidigare versioner, se [borttagna eller inaktuella funktioner i tidigare versioner](../migration-upgrade/deprecated-features.md).



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
