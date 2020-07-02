---
title: Borttagna eller avskrivna plattformsfunktioner
description: I det här avsnittet beskrivs funktioner som har tagits bort, eller har planerats för borttagning i plattformsuppdatering av Finance and Operations-appar.
author: sericks007
manager: AnnBe
ms.date: 06/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2020-02-29
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: 1faee75c9112b3aa584ad021ffdc1144fcf4ba32
ms.sourcegitcommit: 3485d7f36058151cb4fff5c425ef27f56e3ee7d6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/17/2020
ms.locfileid: "3457576"
---
# <a name="removed-or-deprecated-platform-features"></a>Borttagna eller avskrivna plattformsfunktioner

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs funktioner som har tagits bort, eller har planerats för borttagning i plattformsuppdatering av Finance and Operations-appar.

- En *borttagen* funktion är inte längre tillgänglig i produkten.
- En *borttagen* funktion är inte i aktiv utveckling och kan tas bort i en kommande uppdatering.

Den här listan är avsedd att hjälpa dig att ta hänsyn till dessa borttagna och inaktuella funktioner för din planerings skull. 

> [!NOTE]
> Detaljerad information om objekt i Finance and Operations-appar hittas i [Tekniska referensrapporter](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep). Du kan jämföra olika versioner av rapporterna för mer information om objekt som har ändrats eller tagits bort i varje version av Finance and Operations-appar.

## <a name="platform-updates-for-version-10013-of-finance-and-operations-apps"></a>Plattformsuppdateringar för version 10.0.13 för Finance and Operations-appar

> [!NOTE]
> Version 10.0.13 har ännu inte frisläppts. Denna information tillhandahålls för planeringsändamål. Funktionen och dess innehåll för version 10.0.13 kan ändras. Mer information om versioner finns i [Tillgänglighet för tjänstuppdateringar](../../fin-ops/get-started/public-preview-releases.md).


### <a name="upgrade-of-three-jquery-component-libraries"></a>Uppgradering av tre jQuery-komponentbibliotek 

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Tre jQuery-komponentbibliotek uppdateras för säkerhetskorrigeringar och för att bibehålla valutan.   
| **Ersatt av en annan funktion?**   | Följande bibliotekpåverkas: jQuery (till version 3.5.0 från version 2.1.4), jQuery UI (till version 1.12.1 från version 1.11.4), jQuery qTip (till version 3.0.3 från 2.2.1). Vägledningen för migreringen har tillhandahållits online av jQuery.  |
| **Produktområden som påverkas**         | Utökningsbara kontroller, anpassad JavaScript-kod använda gamla API:er |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | Med version 10.0.13/plattformsuppdatering 37 kan kunderna flytta till de senaste biblioteken genom att aktivera funktionen "uppgradera tre jQuery komponentbibliotek". Det är obligatoriskt att flytta till de nya biblioteken med utgåvan från april 2021 för att kunna migrera berörda API:er.   |

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
| **Status**                         | När du har fått till gång till nya virtuella datorer (VM) med Visual Studio 2017 meddelas, måste befintliga virtuella datorer med bara Visual Studio 2015 omdistribueras efter utgivningsvåg 1 av 2021. |

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

