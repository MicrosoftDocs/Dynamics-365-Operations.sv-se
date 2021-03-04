---
title: Borttagna och utfasade funktioner i Dynamics 365 Finance
description: I det här avsnittet beskrivs funktioner som har tagits bort, eller har planerats för borttagning från Dynamics 365 Finance.
author: roschlom
manager: AnnBe
ms.date: 12/07/2020
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
ms.openlocfilehash: a406db6d78302fa05596a58fffb7464222d4bfea
ms.sourcegitcommit: 069ed5789517b550065e5e2317658fec4027359e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/07/2020
ms.locfileid: "4689504"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-finance"></a>Borttagna och utfasade funktioner i Dynamics 365 Finance

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs funktioner som har tagits bort, eller har planerats för borttagning från Dynamics 365 Finance.

- En *borttagen* funktion är inte längre tillgänglig i produkten.
- En *borttagen* funktion är inte i aktiv utveckling och kan tas bort i en kommande uppdatering.

Den här listan är avsedd att hjälpa dig att ta hänsyn till dessa borttagna och inaktuella funktioner för din planerings skull. 

> [!NOTE]
> Detaljerad information om objekt i Finance and Operations-appar hittas i [Tekniska referensrapporter](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep). Du kan jämföra olika versioner av rapporterna för mer information om objekt som har ändrats eller tagits bort i varje version av Finance and Operations-appar.

## <a name="features-removed-or-deprecated-in-the-finance-10016-release"></a>Borttagna eller föråldrade funktioner i Finance 10.0.16 utgåva

### <a name="ledger-transaction-export-format-be-electronic-reporting-format-and-respective-ledger-transaction-export-be-model-for-belgium"></a>"Exportformat för redovisningstransaktioner (BE)" Elektroniskt rapporteringsformat och respektive "Export av redovisningstransaktion (BE)"-modell för Belgien

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Ersätts med ett nytt ER-format enligt modellen "Standardverifieringsfil för skatt (SAF-T)".  |
| **Ersatt av en annan funktion?**   | Ja |
| **Produktområden som påverkas**         | Ansökning |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | Föråldrad: Från den 1 december 2021 planerar vi att inte längre att stödja "Exportformat för redovisningstransaktioner (BE)" Elektroniskt rapporteringsformat och respektive "Export av redovisningstransaktion (BE)"-modell. Det nya formatet "Export av redovisningsdata (BE)" tillsammans med "Modellmappning av redovisningsdata" introduceras i stället enligt modellen "Standardverifieringsfil för skatt (SAF-T)". |

### <a name="vat-100-report-for-the-united-kingdom-in-ssrs-format"></a>"VAT 100"-rapport för Storbritannien i SSRS-format

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Ersätts med nytt ER-format – "Momsdeklaration Excel (UK)" under "Momsdeklarationsmodell".  |
| **Ersatt av en annan funktion?**   | Ja |
| **Produktområden som påverkas**         | Ansökning |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | Föråldrad: Från den 1 december 2021 planerar vi att inte längre stödja "VAT 100"-rapport i SSRS-format. Ett nytt format av typen "Momsdeklaration Excel (UK)" under "Momsdeklarationsmodell" infördes i [funktionen MTD-moms](../localizations/emea-gbr-mtd-vat-integration.md). |

## <a name="features-removed-or-deprecated-in-the-finance-10015-release"></a>Borttagna eller föråldrade funktioner i Finance 10.0.15 utgåva

### <a name="internet-explorer-11-support-for-dynamics-365-is-deprecated"></a>Internet Explorer 11-stöd för Dynamics 365 är inaktuellt

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Från och med december 2020 kommer Microsoft Internet Explorer 11-stöd för samtliga Dynamics 365-produkter att betraktas som inaktuellt, och Internet Explorer 11 kommer inte att stödjas efter augusti 2021.<br><br>Detta påverkar kunder som använder Dynamics 365-produkter som har utformats för användning med ett Internet Explorer 11-gränssnitt. Efter augusti 2021 stöds inte Internet Explorer 11 för sådana Dynamics 365-produkter. |
| **Ersatt av en annan funktion?**   | Vi rekommenderar våra kunder att övergå till Microsoft Edge.|
| **Produktområden som påverkas**         | Alla Dynamics 365-produkter |
| **Distribueringsalternativ**              | Allt|
| **Status**                         | Inaktuell. Internet Explorer 11 kommer inte att stödjas efter augusti 2021.|

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


[!INCLUDE[footer-include](../../includes/footer-banner.md)]