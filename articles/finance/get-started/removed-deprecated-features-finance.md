---
title: Borttagna och utfasade funktioner i Dynamics 365 Finance
description: I det här avsnittet beskrivs funktioner som har tagits bort, eller har planerats för borttagning från Dynamics 365 Finance.
author: roschlom
ms.date: 04/14/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2020-03-02
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: 93d025759f86ffeb0ee1f1e6e6e2aeb3ab341b75
ms.sourcegitcommit: 4ba25601eba295bd9057f7fb5e85f1f6764f5a27
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/30/2021
ms.locfileid: "5965320"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-finance"></a>Borttagna och utfasade funktioner i Dynamics 365 Finance

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs funktioner som har tagits bort, eller har planerats för borttagning från Dynamics 365 Finance.

- En *borttagen* funktion är inte längre tillgänglig i produkten.
- En *borttagen* funktion är inte i aktiv utveckling och kan tas bort i en kommande uppdatering.

Den här listan är avsedd att hjälpa dig att ta hänsyn till dessa borttagna och inaktuella funktioner för din planerings skull. 

> [!NOTE]
> Detaljerad information om objekt i Finance and Operations-appar hittas i [Tekniska referensrapporter](/dynamics/s-e/global/axtechrefrep_61). Du kan jämföra olika versioner av rapporterna för mer information om objekt som har ändrats eller tagits bort i varje version av Finance and Operations-appar.

## <a name="features-removed-or-deprecated-in-the-finance-10020-release"></a>Borttagna eller föråldrade funktioner i Finance 10.0.20 utgåva

### <a name="rtir-query-invoice-data-request-hu-format-configuration"></a>Formatkonfiguration för begäran om fakturadata genom RTIR-fråga (HU)

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Exkluderad från bearbetning av elektroniska meddelanden rörande driftskompatibilitet med ungerskt online-faktureringssystem |
| **Ersatt av en annan funktion?**   | Nr |
| **Produktområden som påverkas**         | Ansökning |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | Inaktuell: Från och med den 15 april 2022 planerar vi att inte längre stödja formatkonfigurationen "RTFV Query Invoice Data Request (HU)." |


## <a name="features-removed-or-deprecated-in-the-finance-10017-release"></a>Borttagna eller föråldrade funktioner i Finance 10.0.17 utgåva

### <a name="lcs-repository-as-a-storage-option-for-electronic-reporting-configurations"></a>LCS-databas som ett lagringsalternativ för elektroniska rapporteringskonfigurationer

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Utbytt med den nya globala databasen Regulatory Configuration Service (RCS) |
| **Ersatt av en annan funktion?**   | Ja |
| **Produktområden som påverkas**         | Dynamics 365 Finance, Supply Chain Management och Project Operations-produkter|
| **Distribueringsalternativ**              | Allt |
| **Status**                         | Inaktuell: Senast den 1 april 2022 planerar vi att inte längre stödja Microsoft Dynamics Lifecycle Services-databasen (LCS) som lagringsalternativ för konfigurationer av elektronisk rapportering (ER). Nya Microsoft ER-konfigurationer kommer att publiceras för hämtning exklusivt från den globala databasen. Du öppnar den globala databasen från Dynamics 365-produkterna och RCS. Mer information finns i [Importera konfigurationer för elektronisk rapportering (ER) från RCS](../../fin-ops-core/dev-itpro/analytics/tasks/import-configuration-rcs.md). |

## <a name="features-removed-or-deprecated-in-the-finance-10016-release"></a>Borttagna eller föråldrade funktioner i Finance 10.0.16 utgåva

### <a name="vat-declaration-cz-and-control-statement-export-cz-electronic-reporting-formats-for-czech-republic"></a>Elektroniska rapporteringsformat "Momsdeklaration (CZ)" och "Export av kontrollutdrag (CZ)" för Tjeckien

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Ersatta med nya format |
| **Ersatt av en annan funktion?**   | Ja |
| **Produktområden som påverkas**         | Ansökning |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | Inaktuellt: Den 22 januari 2022 planerar vi att inte längre stödja de elektroniska rapporteringsformaten (ER) "Momsdeklaration (CZ)", "Export av kontrollutdrag (CZ)". Istället införs XML- (CZ) och Excel(CZ)-format för momsdeklaration samt Excel-format (CZ) för momskontrollutdrag inom ramarna för modellen "Skattedeklaration". |

### <a name="ledger-transaction-export-format-be-electronic-reporting-format-and-respective-ledger-transaction-export-be-model-for-belgium"></a>"Exportformat för redovisningstransaktioner (BE)" Elektroniskt rapporteringsformat och respektive "Export av redovisningstransaktion (BE)"-modell för Belgien

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Ersätts med ett nytt ER-format enligt modellen "Standardverifieringsfil för skatt (SAF-T)".  |
| **Ersatt av en annan funktion?**   | Ja |
| **Produktområden som påverkas**         | Ansökning |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | Föråldrad: Från den 1 december 2021 planerar vi att inte längre att stödja "Exportformat för redovisningstransaktioner (BE)" Elektroniskt rapporteringsformat och respektive "Export av redovisningstransaktion (BE)"-modell. Det nya formatet "Export av redovisningsdata (BE)" tillsammans med "Modellmappning av redovisningsdata" introduceras i stället enligt modellen "Standardverifieringsfil för skatt (SAF-T)". |

### <a name="vat-100-report-for-the-united-kingdom-in-ssrs-format"></a>"VAT 100"-rapport för Storbritannien i SSRS-format

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Ersätts med nytt ER-format – "Momsdeklaration Excel (UK)" under "Momsdeklarationsmodell".  |
| **Ersatt av en annan funktion?**   | Ja |
| **Produktområden som påverkas**         | Ansökning |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | Föråldrad: Från den 1 december 2021 planerar vi att inte längre stödja "VAT 100"-rapport i SSRS-format. Ett nytt format av typen "Momsdeklaration Excel (UK)" under "Momsdeklarationsmodell" infördes i [funktionen MTD-moms](../localizations/emea-gbr-mtd-vat-integration.md). |

## <a name="features-removed-or-deprecated-in-the-finance-10015-release"></a>Borttagna eller föråldrade funktioner i Finance 10.0.15 utgåva

### <a name="internet-explorer-11-support-for-dynamics-365-is-deprecated"></a>Internet Explorer 11-stöd för Dynamics 365 är inaktuellt

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Från och med december 2020 kommer Microsoft Internet Explorer 11-stöd för samtliga Dynamics 365-produkter att betraktas som inaktuellt, och Internet Explorer 11 kommer inte att stödjas efter augusti 2021.<br><br>Detta påverkar kunder som använder Dynamics 365-produkter som har utformats för användning med ett Internet Explorer 11-gränssnitt. Efter augusti 2021 stöds inte Internet Explorer 11 för sådana Dynamics 365-produkter. |
| **Ersatt av en annan funktion?**   | Vi rekommenderar våra kunder att övergå till Microsoft Edge.|
| **Produktområden som påverkas**         | Alla Dynamics 365-produkter |
| **Distribueringsalternativ**              | Allt|
| **Status**                         | Inaktuell. Internet Explorer 11 kommer inte att stödjas efter augusti 2021.|

## <a name="features-removed-or-deprecated-in-the-finance-10012-release"></a>Borttagna eller föråldrade funktioner i Finance 10.0.12 utgåva

### <a name="not-deprecated-polish-ssrs-reports-sales-vat-register-purchase-vat-register-eu-summary-vat-register--feature-reference-pl-00014"></a>Ej inaktuella: polska SSRS-rapporter: utgående momsregister, ingående momsregister, sammanfattande EU-momsregister – funktionsreferens PL-00014

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Krävs inte enligt lag.  |
| **Ersatt av en annan funktion?**   | Ja (Excel-format för standardgranskningsfil med momsdeklaration – JPK_VDEK) |
| **Produktområden som påverkas**         | Ansökning |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | Ej inaktuella: Per den 27 juli 2021 planerar vi att fortsätta stödja SSRS-rapporter: **utgående momsregister, ingående momsregister, sammanfattande EU-momsregister – funktionsreferens PL-00014**. Excel-formatexempel för standardverifieringsfil med momsdeklaration (JPK_VDEK) har också införts. |

## <a name="features-removed-or-deprecated-in-the-finance-10011-release"></a>Borttagna eller föråldrade funktioner i Finance 10.0.11 utgåva

### <a name="norwegian-standard-main-accounts"></a>Norska standardhuvudkonton

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Omformat  |
| **Ersatt av en annan funktion?**   | Ja (ersatt med programspecifika parametrar för ER-format) |
| **Produktområden som påverkas**         | Ansökning |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | Föråldrad: den 1 april 2021 planerar vi inte längre stöd för funktioner som är relaterade till standardhuvudkonton: referensfält, relaterad tabell, dataentitet. |

## <a name="features-removed-or-deprecated-in-the-finance-1007-release"></a>Borttagna eller föråldrade funktioner i Finance 10.0.7 utgåva

### <a name="workflow-request-change-dialog-box-no-longer-includes-user-selection-drop-down-list"></a>Dialogrutan ändra arbetsflödesbegäran innehåller inte längre listrutan för användarval

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Ändras till funktionen med kontogruppsurval.  |
| **Ersatt av en annan funktion?**   | Ja |
| **Produktområden som påverkas**         | Arbetsflöde |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | Föråldrad: 1 december 2020, planerar att inte längre stödja inställningar för kinesiska verifikationstyper utan kontogruppsval. Hitta mer information om den nya designen i [Nyheter i 10.0.7](whats-new-changed-10-0-7.md). |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a>Tidigare meddelanden om borttagna eller inaktuella funktioner
Om du vill veta mer om funktioner som har tagits bort eller ersatts i tidigare versioner, se [borttagna eller inaktuella funktioner i tidigare versioner](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
