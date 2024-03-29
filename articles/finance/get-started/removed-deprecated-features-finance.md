---
title: Borttagna eller inaktuella funktioner i Dynamics 365 Finance
description: I den här artikeln beskrivs funktioner som har tagits bort, eller har planerats för borttagning från Dynamics 365 Finance.
author: kfend
ms.date: 10/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2020-03-02
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: 25d13aa26565e5753b87c843b43cf46f8276b642
ms.sourcegitcommit: 6c05bcd27e6ee72f01cb66e2cfd1e929e0365830
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/16/2022
ms.locfileid: "9854090"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-finance"></a>Borttagna eller inaktuella funktioner i Dynamics 365 Finance

[!include [banner](../includes/banner.md)]

I den här artikeln beskrivs funktioner som har tagits bort, eller har planerats för borttagning från Dynamics 365 Finance.

- En *borttagen* funktion är inte längre tillgänglig i produkten.
- En *borttagen* funktion är inte i aktiv utveckling och kan tas bort i en kommande uppdatering.

Den här listan är avsedd att hjälpa dig att ta hänsyn till dessa borttagna och inaktuella funktioner för din planerings skull. 

> [!NOTE]
> Detaljerad information om objekt i appar för ekonomi och drift finns i [Tekniska referensrapporter](/dynamics/s-e/global/axtechrefrep_61). Du kan jämföra olika versioner av rapporterna för mer information om objekt som har ändrats eller tagits bort i respektive version av appar för ekonomi och drift.

## <a name="features-removed-or-deprecated-in-the-finance-10031-release"></a>Borttagna eller föråldrade funktioner i Finance 10.0.31 utgåva

### <a name="edifact-paymul-at-configuration-under-payment-model"></a>EDIFACT PAYMUL (AT) konfiguration under Betalningsmodell

| &nbsp;  | &nbsp;  |
|---|---|
| **Orsak till inaktuell/borttagning** | Ersätts med ett nytt format som baseras på ISO 20022 pain.001.001.09. | 
| **Ersatt av en annan funktion?**   | Ja |
| **Produktområden som påverkas**         | Ansökning |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | Inaktuell: Banker i Österrike kommer att avskriva EDICFACT-PAYMUL för gränsöverskridande betalningar senast i november 2022 och ersätter den med XML version pain.001.001.09N. En ny konfiguration har lagts till under den globala konfigurationsdatabasen, som gör det möjligt för användarna att slutföra den gränsöverskridande betalningsförfrågan. |

## <a name="features-removed-or-deprecated-in-the-finance-10030-release"></a>Borttagna eller föråldrade funktioner i Finance 10.0.30 utgåva

### <a name="revenue-recognition"></a>Intäktsredovisning

[Intäktsredovisning](../../finance/accounts-receivable/revenue-recognition-overview.md)

| &nbsp;  | &nbsp;  |
|---|---|
| **Orsak till inaktuell/borttagning** |Ersatt av förbättrad funktionalitet, [abonnemangsfakturering](../../finance/accounts-receivable/subscription-billing-summary.md)
| **Ersatt av en annan funktion?**   | Ja |
| **Produktområden som påverkas** | Ansökning |
| **Distribueringsalternativ** | Allt |
| **Status** | Inaktuell: Efter april 2023 får intäktsredovisningsfunktionen i Dynamics 365 Finance inte längre stöd med åtgärdskorrigeringar. Kunder uppmanas att använda den förbättrade funktionen [prenumerationsfakturering](../../finance/accounts-receivable/subscription-billing-summary.md). I oktober 2023 är intäktsredovisningsfunktionen inte längre tillgänglig. Kunder kommer att uppmanas att gå över till den förbättrade prenumerationsfakturering funktionen. För buntfunktionen som en del av intäktsredovisningen finns det för denna tidpunkt ingen ersättningsfunktion planerad.|

## <a name="features-removed-or-deprecated-in-the-finance-10029-release"></a>Borttagna eller föråldrade funktioner i Finance 10.0.29 utgåva

### <a name="stock-transfer-orders-that-have-tax-on-the-transfer-price"></a>Lageröverföringsorder som har moms på överföringspriset

[Lageröverföringsorder som har moms på överföringspriset](../../finance/localizations/apac-ind-gst-stock-transfer-transactions.md)

| &nbsp;  | &nbsp;  |
|---|---|
| **Orsak till inaktuell/borttagning** | Ersatt av förbättrad funktionalitet, [lageröverföringsorder för Indien](../../finance/localizations/apac-ind-stock-transfer.md)|
| **Ersatt av en annan funktion?**   | Ja |
| **Produktområden som påverkas** | Ansökning |
| **Distribueringsalternativ** | Allt |
| **Status** | Inaktuell: Efter april 2023, funktionen **Lageröverföringsorder som har moms på överföringspriset** kommer inte längre att få support med felkorrigeringar och säkerhetskorrigeringar. Kunder uppmanas att använda den förbättrade funktionen [Lageröverföringsorder för Indien](../../finance/localizations/apac-ind-stock-transfer.md). Efter oktober 2023 kommer funktionen **Lageröverföringsorder som har moms på överföringspriset** inte längre att vara tillgängliga och kunder uppmanas att flytta till den förbättrade funktionen. |

### <a name="bank-statement-import-and-export-of-positive-pay-file"></a>Bankutdrag, import och export av positiv betalningsfil

| &nbsp;  | &nbsp;  |
|---|---|
| **Orsak till inaktuell/borttagning** |Ersätts av förbättrad funktionalitet, importera bankutdrag och exportera positiva lönefiler.| 
| **Ersatt av en annan funktion?**   | Ja |
| **Produktområden som påverkas**         | Ansökning |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | Inaktiverad: XSLT-funktion för import och export av filer får inte längre stöd med felkorrigeringar och säkerhetskorrigeringar. Kunderna uppmanas att använda de förbättrade funktionerna: [Ställ in positiva lönefiler genom att använda elektronisk rapportering](../../finance/accounts-payable/set-up-positive-pay-er.md) och [Ställ in avancerad bankavstämningsimport med hjälp av elektronisk rapportering](../../finance/accounts-payable/import-bai2-er.md). Efter september 2022 är XSLT-funktionen inte längre tillgänglig och kunderna uppmanas att flytta till den förbättrade funktionen.|


## <a name="features-removed-or-deprecated-in-the-finance-10026-release"></a>Borttagna eller föråldrade funktioner i Finance 10.0.26 utgåva

### <a name="sales-tax-report-for-finland-design-based-on-reporting-codes"></a>Momsrapport för Finland (design baserad på rapporteringskoder)

[Momsrapport för Finland](../localizations/emea-fin-sales-tax-payment-report-finland.md)

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Ersätt med en ny momsdeklarationsdesign, [momsdeklaration för Finland](../localizations/emea-fin-vat-declaration.md). |
| **Ersatt av en annan funktion?**   | Ja |
| **Produktområden som påverkas**         | Ansökning |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | Inaktuell: Senast den 1 mars 2023 planerar vi att inte längre stödja momsrapporten för Finland (finsk rapportlayout). Nya format för **momsdeklaration TXT (FI**) och **momsdeklaration Excel (FI)** Elektronisk rapportering (ER) införs under modellen **momsdeklaration**. |

## <a name="features-removed-or-deprecated-in-the-finance-10024-release"></a>Borttagna eller föråldrade funktioner i Finance 10.0.24 utgåva

### <a name="sales-tax-report-for-sweden-design-based-on-reporting-codes"></a>Momsrapport för Sverige (design baserad på rapporteringskoder)

[Momsrapport för Sverige](../localizations/emea-swe-sales-tax-payment-report-sweden.md)

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Ersätt med en ny momsdeklarationsdesign, [momsdeklaration för Sverige](../localizations/emea-swe-vat-declaration-sweden.md) |
| **Ersatt av en annan funktion?**   | Ja |
| **Produktområden som påverkas**         | Ansökning |
| **Distribueringsalternativ**              | Alla |
| **Status**                         | Inaktuell: Senast den 1 december 2022 planerar vi att inte längre stödja momsrapporten för Sverige (svensk rapportlayout). Nya format för **momsdeklaration XML (SE**) och **momsdeklaration Excel (SE)** Elektronisk rapportering (ER) införs under modellen **momsdeklaration**. |

### <a name="vat-statement-for-austria-design-based-on-reporting-codes"></a>Momsutdrag för Österrike (design baserad på rapporteringskoder)

[Detaljerad momsinformation för Österrike](../localizations/emea-aut-vat-statement-details.md)

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Ersätt med en ny momsdeklarationsdesign, [momsdeklaration för Österrike](../localizations/emea-aut-vat-declaration-austria.md) |
| **Ersatt av en annan funktion?**   | Ja |
| **Produktområden som påverkas**         | Ansökning |
| **Distribueringsalternativ**              | Alla |
| **Status**                         | Inaktuell: Den 1 december 2022 planerar vi att inte längre stödja **momsdeklarationen (AT)** elektronisk rapportering (ER) under **momsdeklarationsmodellen**. Nya format för **momsdeklaration XML (AT)** och **momsdeklaration Excel (AT)** införs under modellen **momsdeklaration**. |

### <a name="elster-declaration-for-germany-design-based-on-reporting-codes-electronic-tax-declaration-log-menu-item-and-page-electronic-tax-declaration-setup-menu-item-and-page-german-report-layout-taxreport_de-ssrs-format"></a>ELSTER-deklaration för Tyskland (design baserad på rapporteringskoder) menyalternativ \"Elektronisk momsdeklarationslogg\" och sidan menyalternativ \"Inställningar för elektronisk momsdeklaration\" och sidan tysk rapportlayout (TaxReport_DE) SSRS-format

[Momsutdrag](../localizations/emea-de-vat-declaration.md)</br>
[Konfigurera elektronisk skattedeklaration för Tyskland](../../fin-ops-core/dev-itpro/analytics/tasks/setup-electronic-tax-declaration-germany.md)</br>

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Ersätt med en ny momsdeklarationsdesign, [momsdeklaration för Tyskland](../localizations/emea-deu-vat-declaration-germany.md) |
| **Ersatt av en annan funktion?**   | Ja |
| **Produktområden som påverkas**         | Ansökning |
| **Distribueringsalternativ**              | Alla |
| **Status**                         | Inaktuell: Den 1 december 2022 kommer inte längre stödja formaten **Elster (DE)** och **Elster modell** elektronisk rapportering (ER). Nya ER-format för **momsdeklaration XML (DE)** och **momsdeklaration Excel (DE)** införs under modellen **momsdeklaration**. Vi kommer inte längre ge stöd för menyalternativ **Skatt** \> **Deklarationer** \> **Moms** \> **Elektronisk momsdeklarationslogg** och sidan **Skatt** \> **Inställning** \> **Moms** \> **Inställningar för elektronisk momsdeklaration** och sidan **Tax** \> **Inställning** \> **Moms tax** \> **Elektroniska momsintyg** och tysk rapportlayout (TaxReport\_DE) SQL Server Reporting Services (SSRS)-format. Processen för momsrapportering i Tyskland stöds i funktionen [Elektroniska meddelanden](../general-ledger/electronic-messaging.md). Mer information finns i [momsdeklaration för Tyskland](../localizations/emea-deu-vat-declaration-germany.md). |

### <a name="ob-declaration-for-netherlands-design-based-on-reporting-codes-electronic-ob-declaration-menu-item-and-page-dutch-report-layout-taxreport_nl-ssrs-format"></a>OB-deklaration för Nederländerna (design baserad på rapporteringskoder), menyalternativet \"Elektronisk OB-deklaration\" och sidan, nederländsk rapportlayout (TaxReport_NL) SSRS-format

[OB-deklarationsnummer](../localizations/emea-nl-vat-declaration.md)

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Ersätt med en ny momsdeklarationsdesign, [momsdeklaration för Nederländerna](../localizations/emea-nl-vat-declaration-netherlands.md) |
| **Ersatt av en annan funktion?**   | Ja |
| **Produktområden som påverkas**         | Ansökning |
| **Distribueringsalternativ**              | Alla |
| **Status**                         | Inaktuell: Den 1 december 2022 kommer vi inte längre stödja **OB-deklarationen (NL)** och **modellen OB-deklaration** elektronisk rapportering (ER). Nya ER-format för **momsdeklaration XML (NL)** och **momsdeklaration Excel (NL)** införs under modellen **momsdeklaration**. Vi kommer inte längre att stödja menyalternativ och sida **Skatt** \> **Deklarationer** \> **Moms** \> **Elektronisk OB-deklaration** och den nederländska rapportlayouten (TaxReport_NL) SSRS-format. Processen för momsrapportering i Nederländerna stöds i funktionen [Elektroniska meddelanden](../general-ledger/electronic-messaging.md). Mer information finns i [momsdeklaration för Nederländerna](../localizations/emea-nl-vat-declaration-netherlands.md). |

## <a name="features-removed-or-deprecated-in-the-finance-10020-release"></a>Borttagna eller föråldrade funktioner i Finance 10.0.20 utgåva

### <a name="rtir-query-invoice-data-request-hu-electronic-reporting-er-format-configuration"></a>Formatkonfiguration för "begäran om fakturadata genom RTIR-fråga" – elektronisk rapportering (ER)

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Exkluderad från bearbetning av elektroniska meddelanden rörande driftskompatibilitet med ungerskt online-faktureringssystem |
| **Ersatt av en annan funktion?**   | Nej |
| **Produktområden som påverkas**         | Ansökning |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | Inaktuell: Från och med den 15 april 2022 planerar vi att inte längre stödja formatkonfigurationen "RTFV Query Invoice Data Request (HU)." |

### <a name="french-fec-audit-file-electronic-reporting-er-format-for-france-under-german-audit-file-output-format"></a>"Fransk FEC-granskningsfil" Elektronisk rapportering (ER) för Frankrike under formatet "Tysk granskningsfil utdata"

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Ersätts med det nya formatet för "FEC-granskningsfil (FR)" |
| **Ersatt av en annan funktion?**   | Ja |
| **Produktområden som påverkas**         | Ansökning |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | Inaktuell: den 1 maj 2022 planerar vi att inte längre stödja "French FEC audit file" Elektronisk rapportering (ER) för Frankrike under formatet "Tysk granskningsfil utdata". Nytt FEC-granskningsfilformat (FR) presenteras istället under "Dataexportmodellen". |

## <a name="features-removed-or-deprecated-in-the-finance-10017-release"></a>Borttagna eller föråldrade funktioner i Finance 10.0.17 utgåva

### <a name="lcs-repository-as-a-storage-option-for-electronic-reporting-configurations"></a>LCS-databas som ett lagringsalternativ för elektroniska rapporteringskonfigurationer

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Utbytt med den nya globala databasen Regulatory Configuration Service (RCS) |
| **Ersatt av en annan funktion?**   | Ja |
| **Produktområden som påverkas**         | Dynamics 365 Finance, Supply Chain Management och Project Operations-produkter|
| **Distribueringsalternativ**              | Allt |
| **Status**                         | Inaktuell: Senast den 1 april 2022 planerar vi att inte längre stödja Microsoft Dynamics Lifecycle Services-databasen (LCS) som lagringsalternativ för konfigurationer av elektronisk rapportering (ER). Nya Microsoft ER-konfigurationer kommer att publiceras för hämtning exklusivt från den globala databasen. Du öppnar den globala databasen från Dynamics 365-produkterna och RCS. Mer information finns i [Importera ER-konfigurationer från RCS](../../fin-ops-core/dev-itpro/analytics/tasks/import-configuration-rcs.md) och [Regulatory Configuration Service – Lagringsavskrivning för Lifecycle Services-lagring](../localizations/rcs-lcs-repo-dep-faq.md). |

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
| **Orsak till inaktuell/borttagning** | Ersätts med ett nytt ER-format enligt modellen "Standardgranskningsfil för skatt (SAF-T)".  |
| **Ersatt av en annan funktion?**   | Ja |
| **Produktområden som påverkas**         | Ansökning |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | Föråldrad: Från den 1 december 2021 planerar vi att inte längre att stödja "Exportformat för redovisningstransaktioner (BE)" Elektroniskt rapporteringsformat och respektive "Export av redovisningstransaktion (BE)"-modell. Det nya formatet "Export av redovisningsdata (BE)" tillsammans med "Modellmappning av redovisningsdata" introduceras i stället enligt modellen "Standardgranskningsfil för skatt (SAF-T)". |

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
| **Status**                         | Ej inaktuella: Per den 27 juli 2021 planerar vi att fortsätta stödja SSRS-rapporter: **utgående momsregister, ingående momsregister, sammanfattande EU-momsregister – funktionsreferens PL-00014**. Excel-formatexempel för standardgranskningsfil med momsdeklaration (JPK_VDEK) har också införts. |

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

