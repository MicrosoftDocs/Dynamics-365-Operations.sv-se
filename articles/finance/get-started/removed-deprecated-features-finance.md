---
title: Borttagna och utfasade funktioner i Dynamics 365 Finance
description: I det här avsnittet beskrivs funktioner som har tagits bort, eller har planerats för borttagning från Dynamics 365 Finance.
author: roschlom
manager: AnnBe
ms.date: 03/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: roschlom
ms.search.scope: Operations
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2020-03-02
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: aebce032d7d780b296ba74fea4467425a3cbe1a7
ms.sourcegitcommit: 4e9b3746790355f9f72bbfddc099c4065a49ad63
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/30/2020
ms.locfileid: "3175118"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-finance"></a>Borttagna och utfasade funktioner i Dynamics 365 Finance

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs funktioner som har tagits bort, eller har planerats för borttagning från Dynamics 365 Finance.

- En *borttagen* funktion är inte längre tillgänglig i produkten.
- En *borttagen* funktion är inte i aktiv utveckling och kan tas bort i en kommande uppdatering.

Den här listan är avsedd att hjälpa dig att ta hänsyn till dessa borttagna och inaktuella funktioner för din planerings skull. 

> [!NOTE]
> Detaljerad information om objekt i Finance and Operations-appar hittas i [Tekniska referensrapporter](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep). Du kan jämföra olika versioner av rapporterna för mer information om objekt som har ändrats eller tagits bort i varje version av Finance and Operations-appar.

## <a name="features-removed-or-deprecated-in-the-finance-10012-release"></a>Borttagna eller föråldrade funktioner i Finance 10.0.12 utgåva

### <a name="polish-ssrs-reports-sales-vat-register-purchase-vat-register-eu-summary-vat-register--feature-reference-pl-00014"></a>Polsk SSRS-rapporter: utgående momsregister, ingående momsregister, sammanfattande EU-momsregister – funktionsreferens PL-00014

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Krävs inte enligt lag.  |
| **Ersatt av en annan funktion?**   | Ja (Excel-format för standardgranskningsfil med momsdeklaration - JPK_VDEK) |
| **Produktområden som påverkas**         | Ansökning |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | Föråldrad: den 1 juli 2021 planerar vi att inte längre stödja SSRS-rapporter: **utgående momsregister, ingående momsregister, sammanfattande EU-momsregister – funktionsreferens PL-00014**. Excel-format exempel för standard granskningsfil med momsdeklaration (JPK_VDEK) kommer att införas i stället. |

## <a name="features-removed-or-deprecated-in-the-finance-10011-release"></a>Borttagna eller föråldrade funktioner i Finance 10.0.11 utgåva

### <a name="norwegian-standard-main-accounts"></a>Norska standardhuvudkonton

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Omformat  |
| **Ersatt av en annan funktion?**   | Ja (ersatt med programspecifika parametrar för ER-format) |
| **Produktområden som påverkas**         | Ansökning |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | Föråldrad: den 1 april 2021 planerar vi inte längre stöd för funktioner som är relaterade till standardhuvudkonton: referensfält, relaterad tabell, dataentitet. |

## <a name="features-removed-or-deprecated-in-the-finance-1007-release"></a>Borttagna eller föråldrade funktioner i Finance 10.0.7 utgåva

### <a name="workflow-request-change-dialog-box-no-longer-includes-user-selection-drop-down-list"></a>Dialogrutan ändra arbetsflödesförfrågan innehåller inte längre listrutan för användarval
|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Ändras till funktionen med kontogruppsurval.  |
| **Ersatt av en annan funktion?**   | Ja |
| **Produktområden som påverkas**         | Arbetsflöde |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | Föråldrad: 1 december 2020, planerar att inte längre stödja inställningar för kinesiska verifikationstyper utan kontogruppsval. Hitta mer information om den nya designen i [Nyheter i 10.0.7](whats-new-changed-10-0-7.md). |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a>Tidigare meddelanden om borttagna eller inaktuella funktioner
Om du vill veta mer om funktioner som har tagits bort eller ersatts i tidigare versioner, se [borttagna eller inaktuella funktioner i tidigare versioner](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md).
