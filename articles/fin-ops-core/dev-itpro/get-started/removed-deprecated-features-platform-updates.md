---
title: Borttagna eller avskrivna plattformsfunktioner
description: I det här avsnittet beskrivs funktioner som har tagits bort, eller har planerats för borttagning i plattformsuppdatering av Finance and Operations-appar.
author: sericks007
manager: AnnBe
ms.date: 03/03/2020
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
ms.openlocfilehash: d394f5ca84efc5beb943d349e45a3d2c9639d83c
ms.sourcegitcommit: 75974ae567bb0eacf0f65cac992b34ce5c680b93
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/03/2020
ms.locfileid: "3095784"
---
# <a name="removed-or-deprecated-platform-features"></a>Borttagna eller avskrivna plattformsfunktioner

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs funktioner som har tagits bort, eller har planerats för borttagning i plattformsuppdatering av Finance and Operations-appar.

- En *borttagen* funktion är inte längre tillgänglig i produkten.
- En *borttagen* funktion är inte i aktiv utveckling och kan tas bort i en kommande uppdatering.

Den här listan är avsedd att hjälpa dig att ta hänsyn till dessa borttagna och inaktuella funktioner för din planerings skull. 

> [!NOTE]
> Detaljerad information om objekt i Finance and Operations-appar hittas i [Tekniska referensrapporter](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep). Du kan jämföra olika versioner av rapporterna för mer information om objekt som har ändrats eller tagits bort i varje version av Finance and Operations-appar.

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

