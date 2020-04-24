---
title: Borttagna eller avskrivna plattformsfunktioner
description: I det här avsnittet beskrivs funktioner som har tagits bort, eller har planerats för borttagning i plattformsuppdatering av Finance and Operations-appar.
author: sericks007
manager: AnnBe
ms.date: 04/13/2020
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
ms.openlocfilehash: 0072ca507301fdb880f0595a06377ff01366ca20
ms.sourcegitcommit: cd8a28be0acf31c547db1b8f6703dd4b0f62940c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/14/2020
ms.locfileid: "3260539"
---
# <a name="removed-or-deprecated-platform-features"></a>Borttagna eller avskrivna plattformsfunktioner

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs funktioner som har tagits bort, eller har planerats för borttagning i plattformsuppdatering av Finance and Operations-appar.

- En *borttagen* funktion är inte längre tillgänglig i produkten.
- En *borttagen* funktion är inte i aktiv utveckling och kan tas bort i en kommande uppdatering.

Den här listan är avsedd att hjälpa dig att ta hänsyn till dessa borttagna och inaktuella funktioner för din planerings skull. 

> [!NOTE]
> Detaljerad information om objekt i Finance and Operations-appar hittas i [Tekniska referensrapporter](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep). Du kan jämföra olika versioner av rapporterna för mer information om objekt som har ändrats eller tagits bort i varje version av Finance and Operations-appar.

## <a name="platform-updates-for-version-10011-of-finance-and-operations-apps"></a>Plattformsuppdateringar för version 10.0.11 för Finance and Operations-appar

### <a name="field-groups-containing-invalid-field-references"></a>Fältgrupper innehåller ogiltiga fältreferenser

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Fältgrupper i definitioner av registermetadata kan innehålla fältreferenser som inte är giltiga. Om dessa fältgrupper distribueras kan de orsaka körningsfel i Financial Reporting och Microsoft SQL Server Reporting Services (SSRS). Plattformsuppdatering 23 introducerade kompileraren *varning* om att detta problem med metadata har åtgärdats. Plattformsuppdateringar för version 10.0.11 av Finance and Operations-appar kategoriserar det här problemet som ett kompilator *fel*.<p>Gör så här om du vill åtgärda problemet.</p><ol><li>Ta bort den ogiltiga fältreferensen från tabellens fältgruppdefinition.</li><li>Kompilera om.</li><li>Kontrollera att eventuella fel har åtgärdats.</li></ol> |
| **Ersatt av en annan funktion?**   | Detta kompilatorfel ersätter kompilatorvarningen permanent.  |
| **Produktområden som påverkas**         | Visual Studio utvecklingsverktyg. |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | **Inaktuell:** kompilatorvarningen är nu ett kompileringsfel i plattformsuppdateringar för version 10.0.11 av Finance and Operations-appar. |

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

