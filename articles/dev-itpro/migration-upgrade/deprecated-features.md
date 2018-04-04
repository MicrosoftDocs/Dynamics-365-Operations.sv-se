---
title: "Äldre funktioner"
description: "I det här avsnittet beskrivs funktioner som har tagits bort, eller har planerats för borttagning."
author: sericks007
manager: AnnBe
ms.date: 02/05/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations
ms.custom: 21821
ms.assetid: 31019808-4cbf-47d7-b1ba-d791db4281ae
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 0618d71fdb4b29bfdacd6b9e1a8ed47e03abe00d
ms.contentlocale: sv-se
ms.lasthandoff: 03/26/2018

---

# <a name="removed-or-deprecated-features"></a>Borttagna och inaktuella funktioner

[!include[banner](../includes/banner.md)]

Det här ämnet beskriver funktioner som är borttagna eller inaktuella för Dynamics 365 for Finance and Operations.

- En *borttagen* funktion är inte längre tillgänglig i produkten.
- En *borttagen* funktion är inte i aktiv utveckling och kan tas bort i en kommande uppdatering.

Den här listan är avsedd att hjälpa dig att ta hänsyn till dessa borttagna och inaktuella funktioner för din planerings skull. 

> [!Note]
> Från och med  Dynamics 365 for Finance and Operations, Enterprise Edition juli 2017 med plattformsuppdatering 8 noteras typen av implementeringar för varje borttagen eller inaktuell funktion. Alla de tidigare versioner som beskrivs i det här ämnet använde endast molndistributioner.

## <a name="dynamics-365-for-finance-and-operations-enterprise-edition-73-with-platform-update-12"></a>Dynamics 365 for Finance and Operations, Enterprise Edition 7.3. med plattformsuppdatering 12

### <a name="personalized-product-recommendations"></a>Anpassade produktrekommendationer 
Med start den 15 februari 2018 kommer återförsäljare inte längre kunna visa anpassade produktrekommendationer på en butikskassa (POS). Mer information i [anpassade produktrekommendationer](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/personalized-product-recommendations)..  

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Vi tar bort den nuvarande versionen av tjänsten produktrekommendation eftersom vi designar om funktionen med en bättre algoritm och nya butiksorienterade funktioner.  |
| **Ersatt av en annan funktion?**   | Nr. Men vi planerar att återinföra denna funktion senare under 2018 för att ge förbättrat service vid rekommendationer.   |
| **Produktområden som påverkas**         | Anpassade produktrekommendationer i butikskassa.                                                    |
| **Distribueringsalternativ**              | Allt                                                                                      |
| **Status**                         |Borttagen från den 15 februari 2018. Detta påverkar kunder som kör Dynamics 365 for Operations 1611 och senare.  |

### <a name="extension-of-the-list-of-electronic-reporting-er-functions"></a>Utökning av listan över elektronisk rapportering (ER)
Möjligheten att införa anpassade funktioner som ska användas i ER uttrycksverktyget (mer information finns i [utöka listan med elektroniska rapportfunktioner](../../dev-itpro/analytics/general-electronic-reporting-formulas-list-extension.md)) stöds inte längre. På grund av förändringar av ER API:er, blev API:n för att anropa inbyggda funktioner från ER uttrycksverktyget intern och kan inte längre utökas.

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Kodförseglingsinitiativ  |
| **Ersatt av en annan funktion?**   | Ingen. När den nya inbyggda funktionen krävs måste en ny tilläggsbegäran sändas till ER-ramverkets team.<br><br>Som en tillfällig lösning medan den begärda funktionen är under utveckling av ER-teamet kan logiken som krävs programmeras som en metod för en anpassad programklass. Den här metoden kan användas i ER-uttryck som en egenskap för den tillagda ER-datakällan i typen **Application\Class** som refererar till den anpassade programklassen.  |
| **Produktområden som påverkas**         | Elektroniskt rapporteringsramverk                                                      |
| **Distribueringsalternativ**              | Allt                                                                                      |
| **Status**                         | Borttagen från och med Dynamics 365 for Finance and Operations, Enterprise Edition 7.3.    |

### <a name="inventory-by-item-group-and-inventory-by-inventory-dimension-aging-reports"></a>Lager per artikelgrupp och Lager per åldersfördelningsrapport för lagerdimension 

Dessa två rapporter stöds inte längre i Finance and Operations. I stället kan rapporten **Lagerföråldring** användas för att förbättra användarupplevelsen.

|   |  |
|--------------|-----------------------|
| **Orsak till avskrivning**       | Dubblettfunktion  |
| **Ersatt av en annan funktion?** | Ja. De två rapporterna har ersatts av rapporten **Lagerföråldring**.     |
| **Produktområden som påverkas**       | Lagerhantering, kostnadshantering        |
| **Distribueringsalternativ**        | Allt|
| **Status**                       | Inaktuell: Menyalternativen för de två rapporterna har tagits bort i version 7.3. Koden för rapporterna finns emellertid kvar i produkten Planen är att ta bort koden i framtida versioner. |

### <a name="power-bi-content-packs-published-to-powerbicom"></a>Power BI innehållspaket publiceras på PowerBI.com
Innehållspaketen **Kostnadshantering**, **Ekonomiska resultat**, och **Resultat för butikskanal** som publicerades på webbplatsen PowerBI.com är inaktuella till följd av produktuppdateringar i Microsoft Power BI. Systemadministrationformulär som brukade användas för att distribuera dessa innehållspaket till PowerBI.com används även i Finance and Operations.

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Produktuppdateringar i Microsoft Power BI. |
| **Ersatt av en annan funktion?**   | Power BI innehållspaket (publiceras på PowerBI.com) ersätts av analytiska program som gör det möjligt för lösningsintegrering på databasnivå. Läs mer om analytiska program i [Inbäddad Power BI i arbetsytor](../../dev-itpro/analytics/embed-power-bi-workspaces.md).    |
| **Produktområden som påverkas**         | Kostnadshantering, Ekonomi och Butik                                                                                               |
| **Distribueringsalternativ**              | Endast molnet (integrering med PowerBI.com stöds inte i lokala distributioner.)                                                                                                            |
| **Status**                         | Inaktuell: Måltidsramen för att ta bort funktioner är K2 2018.    |

### <a name="standard-ui-in-data-management-workspace"></a>Standardgränssnitt i arbetsytan för datahantering

Standardgränssnittet i datahantering är det är äldre användargränssnittet som är det standardanvändargränssnitt som visas för användarna när de besöker arbetsytan för datahantering.

|   |  |
|------------------|-------------------------|
| **Orsak till inaktuell/borttagning** | Vi investerar i att ge nya användarupplevelser i det nya användargränssnittet.             |
| **Ersatt av en annan funktion?**   | Det nya användargränssnittet som heter *förbättrade vyer* ersätter det gamla användargränssnittet.            |
| **Produktområden som påverkas**         | Arbetsyta för datahantering                                                     |
| **Distribueringsalternativ**              | Allt                                                                           |
| **Status**                         | Inaktuell: Måltidsramen för att ta bort funktioner är Q1 2018. |

### <a name="excise-sales-tax-service-tax-for-india"></a>Punktskatt, moms, tjänstemoms för Indien

Dessa skatter har infogats till indiska GST.

|                                             |                                                                         |
|---------------------------------------------|-------------------------------------------------------------------------|
| **Orsak till inaktuell eller borttagning**       | Dessa skatter har infogats till indiska GST.                          |
| **Ersatt av en annan funktion?**            | Indiska GST                                                              |
| **Produktområden som påverkas**                  | Skatt                                                                     |
| **Distribueringsalternativ**                       | Alla moduler                                                   |
| **Status**                                  | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen. |    

### <a name="file-validation-utility-fvu-for-india"></a>Filvalideringsverktyg (FVU) för Indien

|                                             |                                                                         |
|---------------------------------------------|-------------------------------------------------------------------------|
| **Orsak till inaktuell eller borttagning**       | Brist på kundanvändning                                                  |
| **Ersatt av en annan funktion?**            | Nr                                                                      |
| **Produktområden som påverkas**                  | Indisk källskatt                                                  |
| **Distribueringsalternativ**                       | Alla moduler                                                                    |
| **Status**                                  | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen.   |        

### <a name="tdstcs-certificate-for-india"></a>TDS/TCS-certifikat för Indien

Användare kan hämta denna från myndighetsportalen.

|                                             |                                                                         |
|---------------------------------------------|-------------------------------------------------------------------------|
| **Orsak till inaktuell eller borttagning**       | Brist på kundanvändning                                                  |
| **Ersatt av en annan funktion?**            | Nr                                                                      |
| **Produktområden som påverkas**                  | Indisk källskatt                                                  |
| **Distribueringsalternativ**                       | Alla moduler                                                                   |
| **Status**                                  | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen.     |    

### <a name="exportimport-exim-incentive-scheme-for-india"></a>Exportera/importera (EXIM) incitamentsschema för Indien


|                                             |                                                                         |
|---------------------------------------------|-------------------------------------------------------------------------|
| **Orsak till inaktuell eller borttagning**       | Brist på kundanvändning                                                  |
| **Ersatt av en annan funktion?**            | Nr                                                                      |
| **Produktområden som påverkas**                  | Import och export                                                       |
| **Distribueringsalternativ**                       | Alla moduler                                                                    |
| **Status**                                  | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen.  |    


## <a name="dynamics-365-for-retail-72"></a>Dynamics 365 for Retail 7.2

### <a name="personalized-product-recommendations"></a>Anpassade produktrekommendationer 
Med start den 15 februari 2018 kommer återförsäljare inte längre kunna visa anpassade produktrekommendationer på en butikskassa (POS). Mer information i [anpassade produktrekommendationer](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/personalized-product-recommendations)..  

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Vi tar bort den nuvarande versionen av tjänsten produktrekommendation eftersom vi designar om funktionen med en bättre algoritm och nya butiksorienterade funktioner.  |
| **Ersatt av en annan funktion?**   | Nr. Men vi planerar att återinföra denna funktion senare under 2018 för att ge förbättrat service vid rekommendationer.   |
| **Produktområden som påverkas**         | Anpassade produktrekommendationer i butikskassa.                                                    |
| **Distribueringsalternativ**              | Allt                                                                                      |
| **Status**                         |Borttagen från den 15 februari 2018. Detta påverkar kunder som kör Dynamics 365 for Retail 7.2 och senare. |


## <a name="dynamics-365-for-finance-and-operations-enterprise-edition-july-2017-with-platform-update-8"></a>Dynamics 365 for Finance and Operations, Enterprise Edition juli 2017 med plattformsuppdatering 8

### <a name="warehouse-mobile-devices-portal"></a>Warehouse Mobile Devices-portalen

Warehouse mobile devices portalen (WMDP) är en fristående komponent som är avsedd för eget lokal distribution. Denna komponent stöds inte längre i Finance and Operations. Ett enhetligt program som förbättrar användarupplevelsen har ersatt funktionen i WMDP.

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Dubblettfunktion.       |
| **Ersatt av en annan funktion?**   | Ja. Den här funktionen har ersatts av Finance and Operations - lagring. Mer information om inställningar och krav finns i [installera och konfigurera Microsoft Dynamics 365 for Finance and Operations - lagring](https://docs.microsoft.com/en-us/dynamics365/unified-operations/supply-chain/warehousing/install-configure-warehousing-app). |
| **Produktområden som påverkas**         | Lager- och transporthantering     |
| **Distribueringsalternativ**              | Warehouse mobile devices portalen (WMDP) är en fristående komponent som är avsedd för eget lokal distribution.               |
| **Status**                         | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen.   |

### <a name="advanced-bank-reconciliation-matching-rule-for-manual-matching"></a>Avancerad matchningsregel för bankavstämning för manuell matchning

En matchningsregel användes för att välja och markera ett bankdokument när dokumenten manuellt matchades i avstämningskalkylarket.

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Begränsad användning.                                                                         |
| **Ersatt av en annan funktion?**   | Nr. Kolumnfiltreringsmöjligheter ska användas för att söka efter dokument för avstämning. |
| **Produktområden som påverkas**         | Kassa- och bankhantering                                                               |
| **Distribueringsalternativ**              | Allt                                                                                    |
| **Status**                         | Borttagen från och med juli 2017.                                                               |

## <a name="dynamics-365-for-operations-1611-with-platform-update-3"></a>Dynamics 365 for Operations 1611 med uppdatering 3

### <a name="aeb-payment-formats-for-spain"></a>AEB-betalningformat för Spanien

Betalningsformaten för Consejo Superior Bancario användes för att skicka remissafiler till banken för kundbetalningar och leverantörsbetalningar. Innehållet i dessa format bestämdes av Asociación Española de Banca. Det omfattar Cuaderno 19, 32, 58, 34.

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Betalningformaten används inte längre.                                  |
| **Ersatt av en annan funktion?**   | Ja, ISO20022 kreditöverföring och betalningsformat för autogiro för Spanien |
| **Produktområden som påverkas**         | Leverantörsreskontra, Kundreskontra                                    |
| **Status**                         | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen.           |

### <a name="bank-payments-transfer-for-lithuania"></a>Bankbetalningar överför för Litauen

Bankbetalningsöverföringar skapades och skrevs ut genom att använda exportformatet för betalningsöverföring (LT) för Litauen. Den litauiska marknaden har börjat använda LITASEN, det enade elektroniska banksystemet år 2005.

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Betalningformaten används inte längre.                        |
| **Ersatt av en annan funktion?**   | Ja, ISO20022 betalningsformat för kreditöverföring för Litauen     |
| **Produktområden som påverkas**         | Leverantörsreskontra                                               |
| **Status**                         | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen. |

### <a name="bbs-direkte-remittering-payment-formats-for-norway"></a>BBS Direkte Remittering betalningsformat för Norge

BBS Direkte Remittering betalningsformat inkluderar exportinkasso för kundbetalning (autogiro) och import av returmeddelande.

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Betalningformaten används inte längre.  |
| **Ersatt av en annan funktion?**   | Kundbetalningsformatet för AvtaleGiro för Norge kan användas för att generera autogiro-meddelanden. Import av returmeddelande kommer att implementeras i kommande versioner. |
| **Produktområden som påverkas**         | Leverantörsreskontra, Kundreskontra   |
| **Status**                         | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen.                                                                                                 |

### <a name="chart-of-accounts-tool-for-spain"></a>Verktyg för kontoplan från Spanien

Det här verktyget används när en kontoplan i Spanien kräver stora ändringar. Användarna kan importera en ny kontoplan i Microsoft Excel eller textformat och kan också importera bokslut.

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Begränsad användning                                                  |
| **Ersatt av en annan funktion?**   | Nr                                                             |
| **Produktområden som påverkas**         | Huvudbok                                                 |
| **Status**                         | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen. |

### <a name="dom80-payment-format-for-belgium"></a>Dom80 betalningsformat för Belgien

Äldre belgiskt betalningsformat för betalningsinsamling (autogiro).

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Betalningformatet används inte längre.                          |
| **Ersatt av en annan funktion?**   | Ja, ISO 20022 betalningsformat för autogiro för Belgien.         |
| **Produktområden som påverkas**         | Kundreskontra                                            |
| **Status**                         | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen. |

### <a name="dtaezag-payment-formats-for-switzerland"></a>DTA/EZAG-betalningformat för Schweiz

DTA-/EZAG-format integreras i ESR-systemet, eftersom de kan ha ett referensnummer. Eftersom referensnumret inte är obligatoriskt kan dessa format användas för att bearbeta alla leverantörsbetalningar. Dessa format används av företag som har ett bankkonto på en annan plats än “Postfinance.”

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Betalningformaten används inte längre.                        |
| **Ersatt av en annan funktion?**   | Ja, ISO20022 betalningsformat för kreditöverföring för Schweiz.   |
| **Produktområden som påverkas**         | Leverantörsreskontra                                               |
| **Status**                         | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen. |

### <a name="edifact-dirdeb-payment-format-for-austria"></a>EDIFACT - DIRDEB-betalningformat för Österrike

EDIFACT-DIRDEB-betalningsformat för betalningsinsamling (autogiro).

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Betalningformatet används inte längre.                          |
| **Ersatt av en annan funktion?**   | Ja, ISO 20022 betalningsformat för autogiro för Österrike.         |
| **Produktområden som påverkas**         | Kundreskontra                                            |
| **Status**                         | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen. |

### <a name="edivat-for-belgium"></a>EDIVAT för Belgien

EDIVAT är en inaktuell belgisk standard för elektronisk deklaration säker via e-post. Microsoft Dynamics AX 2012 har kvar den skrivskyddade lösningen för att tillåta åtkomst till de historiska data.

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Funktionen används inte längre.                           |
| **Ersatt av en annan funktion?**   | Nr                                                             |
| **Produktområden som påverkas**         | Huvudbok                                                 |
| **Status**                         | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen. |

### <a name="egiro-edifact-cremul-payment-import-format-for-norway"></a>eGiro EDIFACT CREMUL-betalningsformat för Norge

eGiro baseras på den internationella UN EDIFACT CREMUL-standarden (Multiple Credit Advice Message) som används för automatisk bokföring av kundbetalningar. I Microsoft Dynamics AX tillämpas eGiro som ett importformat för kundbetalning.

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Betalningformatet används inte längre.                                                     |
| **Ersatt av en annan funktion?**   | Nr. Formatet ska ersättas med ISO 20022-utdragsimportformat i kommande versioner. |
| **Produktområden som påverkas**         | Kundreskontra                                                                       |
| **Status**                         | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen.                            |

### <a name="external-inventory-for-poland"></a>Externt lager för Polen

Bevis av varor som tas från en leverantör för försäljning utan inköp. De varor som hanteras i externt lager, som inte påverkar standardlager, kan säljas och sedan köpas in automatiskt. Den här processen skapar verkliga lagerrörelser.

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Ersatt av en annan funktion                                    |
| **Ersatt av en annan funktion?**   | Ja, försändelsefunktionen för den inkommande kärnan                |
| **Produktområden som påverkas**         | Leverantörsreskontra, lagerhantering                         |
| **Status**                         | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen. |

### <a name="financial-reports-generator-for-eastern-europe"></a>Ekonomisk rapportgenerator för Östra Europa

Ett verktyg för att ställa in datainsamling för redovisning och momsrapporter behövs och exportera data till XLS och DOC-rapportmallar

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Begränsad användning                                                                            |
| **Ersatt av en annan funktion?**   | Nr. Verktyget ska ersättas av elektroniska rapporteringskonfigurationer i kommande versioner. |
| **Produktområden som påverkas**         | Redovisning                                                                           |
| **Status**                         | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen.                           |

### <a name="import-of-customer-payment-transactions-for-finland"></a>Import av kundbetalningstransaktioner för Finland

Du kan välja ett importformat för finska betalningar som importerar kundbetalningstransaktioner från en extern fil som tillhandahålls av banken.

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Betalningformatet används inte längre.                                                     |
| **Ersatt av en annan funktion?**   | Nr. Formatet ska ersättas med ISO 20022-utdragsimportformat i kommande versioner. |
| **Produktområden som påverkas**         | Kundreskontra                                                                       |
| **Status**                         | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen.                            |

### <a name="import-of-payment-transactions-into-a-general-ledger-journal-for-finland"></a>Import av betalningstransaktioner till en redovisningsjournal för Finland

Ett format som är specifik för Finland används för att importera redovisningstransaktioner till redovisningen.

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Betalningformatet används inte längre.                                                     |
| **Ersatt av en annan funktion?**   | Nr. Formatet ska ersättas med ISO 20022-utdragsimportformat i kommande versioner. |
| **Produktområden som påverkas**         | Kundreskontra                                                                       |
| **Status**                         | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen.                            |

### <a name="integration-with-isabel-synchronized-cis-for-belgium"></a>Integration med Isabel-synkroniserad (CIS) för Belgien

Isabel är ramverket för elektronisk bankverksamhet i Europa och en de facto-standard i Belgien.

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Integration med Isabel-klienten har annullerats.   |
| **Ersatt av en annan funktion?**   | Nr. Betalningsformaten som inte längre används ersätts av ISO20022-betalningsformat för kreditöverföring för Belgien. |
| **Produktområden som påverkas**         | Leverantörsreskontra     |
| **Status**                         | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen.    |

### <a name="modifications-in-the-chart-of-accounts-and-accounting-rules-for-spain"></a>Ändringar i kontoplanen och redovisningsreglerna för Spanien

Den här funktionen används för ändringar i kontoplanen och redovisningsreglerna i Spanien. Den mappar konton för att transformera den gamla kontoplanen till den nya kontoplanen och jämföra det föregående räkenskapsåret med det nya räkenskapsåret, även om de bokförts till ett annat kontonummer.

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Begränsad användning                                                  |
| **Ersatt av en annan funktion?**   | Nr                                                             |
| **Produktområden som påverkas**         | Huvudbok                                                 |
| **Status**                         | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen. |

### <a name="pagamento-fornittori-vendor-payment-format"></a>Pagamento Fornittori leverantörsbetalningsformat

Äldre italienskt betalningsformat för kreditöverföringar.

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Betalningformatet används inte längre.                          |
| **Ersatt av en annan funktion?**   | Ja, ISO20022 betalningsformat för kreditöverföring för Italien         |
| **Produktområden som påverkas**         | Leverantörsreskontra                                               |
| **Status**                         | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen. |

### <a name="payment-export-formats-for-estonia"></a>Exportformat för betalning för Estland

Formaten Telehansa och Teleservice används för bankbetalningsexport.

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Betalningformaten används inte längre.                        |
| **Ersatt av en annan funktion?**   | Ja, ISO20022 betalningsformat för kreditöverföring för Estland       |
| **Produktområden som påverkas**         | Leverantörsreskontra                                               |
| **Status**                         | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen. |

### <a name="payment-file-archive-for-norway"></a>Betalningsfilarkiv för Norge

När betalningsfiler genereras arkiverar filarkivet automatiskt alla filer som skapas, även filer som tidigare skrevs eller lästes.

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Ersatt av en annan funktion                                        |
| **Ersatt av en annan funktion?**   | Ja, arkiverade elektroniska rapporteringsjobb                            |
| **Produktområden som påverkas**         | Kundreskontra, leverantörsreskontra, organisationadministration |
| **Status**                         | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen.     |

### <a name="payment-import-formats-for-estonia"></a>Importformat för betalning för Estland

Formaten Telehansa och TeleTeenu används för bankbetalningsimport.

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Betalningformaten används inte längre.                                                    |
| **Ersatt av en annan funktion?**   | Nr. Formaten ska ersättas med ISO 20022-utdragsimportformat i kommande versioner. |
| **Produktområden som påverkas**         | Kundreskontra                                                                        |
| **Status**                         | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen.                             |

### <a name="payroll-information-in-human-resources"></a>Löneinformation i Personal

Löneinformation i HR

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Den här funktionen har ersatts av huvudsidorna Lön och Personal.  |
| **Ersatt av en annan funktion?**   | **Förmåner**, **Inkomster** och andra relaterade sidor, som tidigare fanns i USA-lönelistan, har konfigurerats om och är nu en del av den grundläggande konfigurationen Personal för att ge stöd för extern lönebearbetning. Den här funktionen kan nås med hjälp av konfigurationsnyckeln **Personal 1** \> **Lönelista**. |
| **Produktområden som påverkas**         | Personal, Lön   |
| **Status**                         | Togs nort från och med Dynamics 365 for Operations version 1611.    |

### <a name="performance-management-goal-workflow"></a>Arbetsflöde för prestationshanteringmål

Prestationshantering inkluderar målhantering och integration med prestationsgranskning.

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Prestationshantering formades om, och antalet målsidor förminskades för att förenkla processen.                 |
| **Ersatt av en annan funktion?**   | Nr. Mål kan visas för chefer via portalen Självbetjäning för chef, och kan ändras och visas av chefen. |
| **Produktområden som påverkas**         | Administration av humankapital       |
| **Status**                         | Togs nort från och med Dynamics 365 for Operations version 1611.    |

### <a name="postgirot-and-postgirot-utland-payment-formats-for-sweden"></a>Postgirot och Postgirot Utland betalningsformat för Sverige

Postgirot och Postgirot Utland betalningsformat för Sverige.

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Betalningformaten används inte längre.                        |
| **Ersatt av en annan funktion?**   | Ja, ISO20022 betalningsformat för kreditöverföring för Sverige        |
| **Produktområden som påverkas**         | Leverantörsreskontra                                               |
| **Status**                         | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen. |

### <a name="radio-frequency-identifier"></a>Radiofrekvensidentifiering

Radiofrekvensidentifiering (RFID) är en datainsamlingsteknik som använder elektroniska taggar för att lagra identifieringsdata och en läsare utan krav på fri sikt som fångar upp identifieringsdatan.

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Låg kundanvändning och en begränsad uppsättning funktioner.   |
| **Ersatt av en annan funktion?**   | Nr                                              |
| **Produktområden som påverkas**         | Lagerhantering                            |
| **Status**                         | Togs nort från och med Dynamics 365 for Operations 1611. |

### <a name="report-about-state-invoices-numbering-for-latvia"></a>Rapport om numrering av statliga fakturor för Lettland

Lettisk lagstiftning innehåller särskilda regler om hur försäljningsfakturor ska numreras. Funktionen låter dig tilldela specifika nummer till försäljningsfakturor som baseras på användaren eller användargruppen. Du kan sedan skapa en rapport eller en XML-fil. Du kan även skriva ut en rapport om fakturanummer som används.

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Numrering av statliga fakturor måste inte längre underhållas. Rapporten om använda fakturanummer är inte längre obligatorisk. |
| **Ersatt av en annan funktion?**   | Nr       |
| **Produktområden som påverkas**         | Kundreskontra    |
| **Status**                         | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen.  |

### <a name="set-up-the-names-of-the-manager-and-general-accountant-of-a-company-for-lithuania"></a>Ställ in namnen för chefen och den allmänna revisorn i ett företag för Litauen

Namnen på chefen och den allmänna revisorn i ett företag kan anges i företagsinformationen och användas vid olika lokala rapportutskrifter.

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Ersatt av en annan funktion                                     |
| **Ersatt av en annan funktion?**   | Ja, inställningen av för tjänstemän kan användas för samma syfte.   |
| **Produktområden som påverkas**         | Leverantörsreskontra, Kundreskontra och Kassa- och bankhantering |
| **Status**                         | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen.  |

### <a name="shipping-carrier-interface"></a>Transportföretagsgränssnitt

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Dubblettfunktion   |
| **Ersatt av en annan funktion?**   | Delvis ersatt med transporthantering |
| **Produktområden som påverkas**         | Försäljning och marknadsföring, Lagerhantering  |
| **Status**                         | Togs nort från och med Dynamics 365 for Operations version 1611.  |

### <a name="telepay-payment-formats-for-norway"></a>Telepay betalningsformat för Norge

Telepay betalningsformat inkluderar leverantörsbetalningsexporten (kreditöverföring) och inkasso för kundbetalning (autogiro).

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Betalningformaten används inte längre.                                                        |
| **Ersatt av en annan funktion?**   | Ja, ISO20022 betalningsformat för kreditöverföring och AvtaleGiro kundbetalningsformat för Norge |
| **Produktområden som påverkas**         | Leverantörsreskontra, Kundreskontra                                                          |
| **Status**                         | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen.                                 |

### <a name="vendor-payment-export-formats-for-finland"></a>Exportformat för leverantörsbetalning för Finland

Två format för att exportera betalningar är tillgängliga för Finland. LM02 (FI) används för lokala betalningar och LUM2 (FI) används för utländska betalningar.

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Betalningformaten används inte längre.                        |
| **Ersatt av en annan funktion?**   | Ja, ISO20022 betalningsformat för kreditöverföring för Finland       |
| **Produktområden som påverkas**         | Leverantörsreskontra                                               |
| **Status**                         | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen. |

### <a name="warehouse-management-ii"></a>Lagerstyrning II

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Lagerstyrningssystem II-lösningar (WMS II) som var tillgängliga i modulen **Lagerhantering** duplicerar funktionerna som finns i modulen **Lagerstyrning** som släpptes i Microsoft Dynamics AX 2012 R3.                                                                         |
| **Ersatt av en annan funktion?**   | Modulen **Lagerstyrning** som släpptes i AX 2012 R3, Microsoft Dynamics AX 2012 R3 CU8, och Microsoft Dynamics AX 2012 R3 CU9 ersätter funktionerna i Lagerstyrning II. Den nya modulen har mer avancerade funktioner och mer flexibla lagerstyrningsprocesser än de som erbjöds av funktionerna i Lagerstyrning II. |
| **Produktområden som påverkas**         | Lagerhantering, försäljning och marknadsföring, anskaffning och källa   |
| **Status**                         | Togs nort från och med Dynamics 365 for Operations version 1611.    |

### <a name="worker-reminders-in-human-resources"></a>Påminnelser till arbetare i Personal

Löneinformation i HR

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Låg användning                                                           |
| **Ersatt av en annan funktion?**   | Nr                                                                  |
| **Produktområden som påverkas**         | Personal                                                     |
| **Status**                         | Togs nort från och med Dynamics 365 for Operations version 1611. |

### <a name="workflow-for-creating-goals"></a>Arbetsflöde för att skapa mål

Ett arbetsflöde för hantering av genereringen av medarbetare är en av flera arbetsflöden som är tillgängliga för att hjälpa till att koordinera prestandahanteringsprocessen.

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Prestandahantering har helt formats om i Microsoft Dynamics 365 for Finance and Operations.     |
| **Ersatt av en annan funktion?**   | Den omformade prestandahanteringsfunktionen innehåller mer kontroll över innehållet av mål, måtten som används för att spåra framsteg och bilaga med förklarande dokumentation. Mål kan lagras som mallar och sedan återanvändas. Den här funktionen kan hjälpa dig att snabbare ställa in ytterligare mål för medarbetarna. |
| **Produktområden som påverkas**         | Administration av humankapital                 |
| **Status**                         | Togs nort från och med Dynamics 365 for Operations version 1611. |

## <a name="dynamics-ax-70"></a>Dynamics AX 7.0 


### <a name="ability-to-cancel-changes-to-a-vendor-invoice"></a>Möjligheten att avbryta ändringar i en leverantörsfaktura

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Prestandaförbättring        |
| **Ersatt av en annan funktion?**   | Nr                             |
| **Produktområden som påverkas**         | Leverantörsreskontra               |
| **Status**                         | Borttagen från och med Dynamics AX 7.0. |

### <a name="aif-axd-and-axbc-integrations"></a>AIF-, AxD- och AxBC-integrationer

I AIF (Application Integration Framework) kan data utbytas med externa system genom affärslogik som exponeras som tjänster. Microsoft Dynamics AX omfattar tjänster som baseras på dokument och .NET Business Connector (AxBC). Ett dokument skapas genom att använda XML. XML inkluderar rubrikinformation som läggs till för att skapa ett *meddelande* som kan överföras till eller från Microsoft Dynamics AX. Exempel på dokument innehåller försäljningsorder och inköpsorder. Dock kan nästan alla enheter, till exempel en kund, representeras av ett dokument. Tjänster som baseras på dokument använder **Axd \<dokument\>**-klasserna.

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Arkitekturen för AIF och AxDs kunde inte skalas till en molntjänst. Det fanns prestandaproblem relaterade till massimport.                                        |
| **Ersatt av en annan funktion?**   | Den här funktionen har ersatts av ramverket för dataimport/dataexport, som stöder återkommande massimport/massexport. För AxBC rekommenderar vi att du använder faktiska tabeller. |
| **Produktområden som påverkas**         | AxDs, AxBCs och AIF   |
| **Status**                         | Borttagen från och med Dynamics AX 7.0.   |

### <a name="boms-without-bom-versions"></a>Strukturlistor utan strukturlisteversioner

När konfigurationsnyckeln för **strukturlisteversioner** inaktiverades doldes strukturlisteversioner i alla formulär och systemet framtvingade en 1:1-relation mellan frisläppta produkter och strukturlistor. I den aktuella versionen av Dynamics AX kan konfigurationsnyckeln för **strukturlisteversioner** inte inaktiveras.

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Användningen av en konfigurationsnyckel för att kontrollera strukturlisteversioner kan inte skalas till en molnmiljö. |
| **Ersatt av en annan funktion?**   | Nr                                                                                      |
| **Produktområden som påverkas**         | Produktinformationshantering, Lagerhantering                                    |
| **Status**                         | Borttagen från och med Dynamics AX 7.0.                                                          |

### <a name="brazilian-bordero"></a>Brasilian Bordero

Specifik betalningsmetod för brasilianska företag

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Stöd för den brasilianska Bordero-betalningsmetoden har annullerats från brasiliansk lokalisering |
| **Ersatt av en annan funktion?**   | Nr   |
| **Produktområden som påverkas**         | Leverantörsreskontra   |
| **Status**                         | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen. |

### <a name="brazilian-sintegra-statement"></a>Brazilian Sintegra-utdrag

Federala skatteutdrag för ICMS-moms

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Detta utdrag används inte längre i vissa brasilianska stater. |
| **Ersatt av en annan funktion?**   | Nr. Användare kan använda den allmänna funktionen för elektronisk rapportering för att konfigurera utdraget, om det krävs och i vissa fall. |
| **Produktområden som påverkas**         | Skatteböcker    |
| **Status**                         | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen.   |

### <a name="brazilian-scan-contingency-mode-for-nf-e"></a>Brasiliansk SCAN eventualitetläge för NF-e

(SCAN) eventualitetmiljön används för att generera, exportera och importera status för Nota Fiscal eletrônica (NF-e) när miljön för Secretaria da Fazenda (SEFAZ) inte är tillgänglig.

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Den här eventualitetsmetoden används inte längre i alla brasilianska stater |
| **Ersatt av en annan funktion?**   | Nr                                                                          |
| **Produktområden som påverkas**         | Kundreskontra                                                         |
| **Status**                         | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen.              |

### <a name="business-analyzer"></a>Business Analyzer

Det här mobila programmet låter användare granska viktiga affärsmått.

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Funktionen har ersatts med en annan funktion.   |
| **Ersatt av en annan funktion?**   | Innehållspaketet för övervakning av ekonomiska resultat för Microsoft PowerBI kommer att inkludera samma ekonomiska mätvärden som tidigare var tillgängliga i Business Analyzer. |
| **Produktområden som påverkas**         | Huvudbok      |
| **Status**                         | Inaktuell: Användning av Business Analyzer stöds inte längre.    |

### <a name="business-statistics"></a>Affärsstatistik

Konfigurationen av frågor om affärsstatistik som kan hjälpa dig att analysera organisationens resultat

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Gammal metod för BI (Business Intelligence), låg kundanvändning och en begränsad funktionsuppsättning |
| **Ersatt av en annan funktion?**   | Nya BI-lösningar för den aktuella versionen av Dynamics AX                                      |
| **Produktområden som påverkas**         | Anskaffning och sourcing, Leverantörsreskontra, Försäljning och marknadsföring, Kundreskontra         |
| **Status**                         | Borttagen från och med Dynamics AX 7.0.                                                               |

### <a name="change-document-date-function-in-invoice-approval-journal"></a>Funktionen Ändra dokumentets datum i Fakturagodkännandejournal

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Låg användning                                                               |
| **Ersatt av en annan funktion?**   | Ja. Dokumentdatumet för den bokförda leverantörstransaktionen kan ändras. |
| **Produktområden som påverkas**         | Leverantörsreskontra                                                        |
| **Status**                         | Borttagen från och med Dynamics AX 7.0.                                          |

### <a name="clieop03-payment-format-for-the-netherlands"></a>Betalningsformatet ClieOp03 för Nederländerna

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Formatet är inte längre tillämpligt i Nederländerna eftersom det har ersatts av SEPA-funktionen. |
| **Ersatt av en annan funktion?**   | SEPA-betalningsexport  |
| **Produktområden som påverkas**         | Alla moduler     |
| **Status**                         | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen.   |

### <a name="compliance-center"></a>Regelefterlevnadscenter

Regelefterlevnadscentret var en Enterprise Portal-webbplats för att hantera dokumentationskraven för efterlevnadsinsatser som är relaterade till Sarbanes-Oxley-lagen.

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Brist på kundanvändning. Microsoft SharePoint innehåller samma kapacitet som var tillgänglig i regelefterlevnadscentret. |
| **Ersatt av en annan funktion?**   | Nr   |
| **Produktområden som påverkas**         | Regelefterlevnad och interna kontroller  |
| **Status**                         | Borttagen från och med Dynamics AX 7.0.    |

### <a name="connector-for-microsoft-dynamics"></a>Connector för Microsoft Dynamics

Verktyget användes för att integrerar viktiga data från Microsoft Dynamics CRM till Microsoft Dynamics ERP-tillämpningar.

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Funktionen har ersatts med en annan funktion. |
| **Ersatt av en annan funktion?**   | Common data service                                      |
| **Produktområden som påverkas**         | Connector för Microsoft Dynamics                         |
| **Status**                         | Borttagen från och med Dynamics AX 7.0.                           |

### <a name="container-unit-and-multi-dimension-on-hand"></a>Behållarenhet och flerdimensionell behållning

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Dubblettfunktion |
| **Ersatt av en annan funktion?**   | Ja. Sedan AXET 2012 har den här funktionen ersatts av funktionsuppsättning av konsoliderade batchorder. Den här funktionsuppsättningen inkluderar den konsoliderade behållningsvyn. |
| **Produktområden som påverkas**         | Produktinformationshantering, Produktionskontroll, Lagerhantering, Försäljning och marknadsföring  |
| **Status**                         | Borttagen från och med Dynamics AX 7.0. |

### <a name="cue-group-metadata"></a>Stackikongruppmetadata

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Stackikongrupper användes för att visa en eller flera stackikoner i faktaboxområdet. Upptaget var begränsat och det fanns även prestandaproblem eftersom en poständring i ett överordnat formulär orsakade en fråga per stackikon i stackikongruppen. |
| **Ersatt av en annan funktion?**   | Nr      |
| **Produktområden som påverkas**         | Alla moduler    |
| **Status**                         | Borttagen från och med Dynamics AX 7.0.  |

### <a name="cue-metadata"></a>Stackikonmetadata

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Stackikonmetadata begränsades till information om antal och summor.    |
| **Ersatt av en annan funktion?**   | Panelmetadata introducerades för att ge mer flexibilitet för modellering. Du kan till exempel modellera aktuella antal, navigering och KPI:er (Key Performance Indicator). Metadata för antal på panel är en direkt ersättning av stackikonmetadata. |
| **Produktområden som påverkas**         | Alla moduler           |
| **Status**                         | Borttagen från och med Dynamics AX 7.0.      |

### <a name="danish-check-format"></a>Danskt checkformat

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Stöd för den danska checkformatlayouten har tagits bort, och rapporten har tagits bort från lokalisering för danska. |
| **Ersatt av en annan funktion?**   | Nr    |
| **Produktområden som påverkas**         | Alla moduler    |
| **Status**                         | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen.  |

### <a name="data-partitions"></a>Datapartitioner

Datapartitioner tillhandahåller en logisk separering av data i Microsoft Dynamics AX-databasen.

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Datapartitioner introducerades i Microsoft Dynamics AX 2012 R2 för möjliggöra isolering av data. I ett vanligt scenario har ett företag ett dotterbolag och data från ett dotterbolag ska inte vara synliga för ett annat dotterföretag, även om båda dotterbolagen hanteras av samma IT-avdelning. Det behövdes dock extra skript och hantering av information i hela programmet för att skapa nya partitioner och förse dem med data och att säkerhetskopiera partitionsdata. I molnet, där vi har tillgång till plattform som en tjänst (PaaS) databas-tjänster (Microsoft Azure SQL-databasen), är det mycket effektivare att använda en databas som isolerade behållare än att utföra isolering i programmet. Oavsett om datapartition är nödvändig för dotterbolag, för flera innehavare eller bara för skalning, anser vi att scenarier kan hanteras bättre via flera olika Finance and Operations-instanser. |
| **Ersatt av en annan funktion?**   | Kunder som använder datapartitioner måste använda flera instanser av Finance and Operations om separering av databaser är en vital faktor.    |
| **Produktområden som påverkas**         | Alla moduler  |
| **Status**                         | Borttagen från och med Dynamics AX 7.0.  |


### <a name="database-and-file-share-storage-for-attachments"></a>Databas- och fildelningslagring för bifogade filer

Microsoft Dynamics AX 2012 tillåter lagring av bifogade filer i databasen och i delade filer. Båda dessa alternativ stöds inte längre.

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Fildelningslagring stöds inte längre eftersom molnbaserad miljöer inte kan kommunicera med lokala filresurser. Databaslagring har ersatts av Azure Blob-lagring. Azure Blob-lagring motsvarar lagring i databasen, eftersom dokument bara nås via klientformulären i Dynamics 365 for Finance and Operations. Detta ger den extra fördelen med utrymme som inte påverkar databasens prestanda negativt. BLOB-lagring är standard Lagringsmekanismen för dokumenthantering och fungerar omedelbart. |
| **Ersatt av en annan funktion?**   | Databaslagring har ersatts av Azure Blob-lagring.   |
| **Produktområden som påverkas**         | Alla moduler  |
| **Status**                         | Borttagen från och med Dynamics AX 7.0.   |

### <a name="delimitation"></a>Avgränsning

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Ingen användning av funktionen påträffades. |
| **Ersatt av en annan funktion?**   | Nr                                     |
| **Produktområden som påverkas**         | Tid och närvaro                    |
| **Status**                         | Borttagen från och med Dynamics AX 7.0.         |

### <a name="desktop-client"></a>Skrivbordsklient

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Dynamics AX-klientupplevelsen har formats om för att förbättra användbarheten över flera plattformar och enheter.                      |
| **Ersatt av en annan funktion?**   | Den nya webbklienten baseras på skrivbordsformulärmetadata och programmeringsmodellen som har ändrats för att ge en heltäckande webbplattform. |
| **Produktområden som påverkas**         | Alla moduler  |
| **Status**                         | Borttagen från och med Dynamics AX 7.0.   |

### <a name="direct-database-connection"></a>Direkt databasanslutning

I Dynamics AX 2012 R3 kunde inte Retail Modern POS ansluta direkt till Channel DB på liknande sätt som till Enterprise POS. Detta var förutom standardkommunikationsmetoden för Retail Modern POS som kommunicerar via Retail Server.

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Direkt databasanslutning krävde lägre säkerhetsprotokoll och användes främst för att uppnå högsta möjliga prestanda. På grund av prestanda- och säkerhetsförbättringar som har uppstått i Dynamics 365 for Finance and Operations orsakar nu den här funktionen fler problem än den löser. |
| **Ersatt av en annan funktion?**   | Nr. Endast standardkommunikation för Retail Server stöds nu.  |
| **Produktområden som påverkas**         | Channel DB/Retail Modern POS   |
| **Status**                         | Borttagen från och med Dynamics AX 7.0.  |

### <a name="dutch-swift-mt940"></a>Holländsk SWIFT MT940

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Den generiska funktionen används nu i stället för den lokaliserade funktionen.                    |
| **Ersatt av en annan funktion?**   | Ja, den här funktionen har ersatts av funktionen för avancerad bankavstämning. |
| **Produktområden som påverkas**         | Alla moduler                                                                              |
| **Status**                         | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen.                           |

### <a name="ebilanz-xbrl-for-germany"></a>eBilanz (XBRL för Tyskland)

Den här funktionen ger eXtensible Business Reporting Language (XBRL)-utdata som är specifikt utformade för tysk eBilanz-taxonomi.

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Brist på kundanvändning  |
| **Ersatt av en annan funktion?**   | Den här funktionen har inte ersatts av en annan funktion, men flera specialiserade XBRL-paket som innehåller omfattande XBRL-funktioner är tillgängliga för den tyska marknaden. |
| **Produktområden som påverkas**         | Management Reporter      |
| **Status**                         | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen.  |

### <a name="enterprise-portal-client"></a>Enterprise Portal-klient

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | En enskild klientplattform har tillhandahållits.  |
| **Ersatt av en annan funktion?**   | Den nya webbklienten baseras på skrivbordsformulärmetadata och programmeringsmodellen som har ändrats för att ge en heltäckande webbplattform. |
| **Produktområden som påverkas**         | Alla moduler  |
| **Status**                         | Borttagen från och med Dynamics AX 7.0.   |

### <a name="environmental-sustainability"></a>Miljöhållbarhet

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Låg kundanvändning och en begränsad uppsättning funktioner.  |
| **Ersatt av en annan funktion?**   | Nr              |
| **Produktområden som påverkas**         | Efterlevnad och interna kontroller, Leverantörsreskontra  |
| **Status**                         | Borttagen från och med Dynamics AX 7.0. |

### <a name="form-activex-and-managed-host-controls"></a>ActiveX och de hanterade värdkontroller för formulär

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | ActiveX och hanterade värdkontroller baseras på den inaktuella skrivbordsklienten. |
| **Ersatt av en annan funktion?**   | Det utökningsbara kontrollramverket stöder utveckling av nya kontroller som baseras på HTML, CSS och JavaScript, och är en klass 1-kontroll i Microsoft Visual Studio Tooling-miljön. |
| **Produktområden som påverkas**         | Alla moduler     |
| **Status**                         | Borttagen från och med Dynamics AX 7.0.       |

### <a name="generate-prenotes-by-using-a-batch"></a>Generera förauktoriseringar genom att använda en batch

Genereringen av förauktoriseringar kan inte utföras med hjälp av en batch men kan fortfarande utföras av en användare.

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Inget formulär finns för att bevara och visa den resulterande filen med förauktoriseringar när den genererats med hjälp av en batch. |
| **Ersatt av en annan funktion?**   | Förauktoriseringar kan fortfarande genereras och användaren har kontroll över var filen sparas.   |
| **Produktområden som påverkas**         | Leverantörsreskontra, Kundreskontra och Kassa- och bankhantering  |
| **Status**                         | Borttagen från och med AX 7.0.    |

### <a name="german-dtaus-payment-export-and-account-statement-import-totals-and-transactions"></a>Tysk DTAUS-betalningsexport och -kontoutdragsimport (summor och transaktioner)

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Formatet är inte längre tillämpligt i Tyskland eftersom det har ersatts av SEPA-funktionen (Single Euro Payments Area).                    |
| **Ersatt av en annan funktion?**   | Ja, funktionen har ersatts av SEPA-betalningsexport och avancerad bankavstämning för import av kontoutdrag. |
| **Produktområden som påverkas**         | Alla moduler  |
| **Status**                         | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen. |

### <a name="german-dtazv-payment-format"></a>Tyskt DTAZV-betalningsformat

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Formatet är inte längre tillämpligt i Tyskland eftersom det har ersatts av SEPA-funktionen. |
| **Ersatt av en annan funktion?**   | SEPA-betalningsexport    |
| **Produktområden som påverkas**         | Alla moduler   |
| **Status**                         | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen.    |

### <a name="german-mt940-import"></a>Tysk MT940-import

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Den generiska funktionen används nu i stället för den lokaliserade funktionen.                    |
| **Ersatt av en annan funktion?**   | Ja, den här funktionen har ersatts av funktionen för avancerad bankavstämning. |
| **Produktområden som påverkas**         | Alla moduler                                                                              |
| **Status**                         | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen.                           |

### <a name="german-xml-eu-sales-list"></a>Tysk XML-baserad EU-försäljningslista

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | XML-formatet för tyska listrapporten över försäljning inom EU stöds inte längre. Det går enbart att använda textfilformatet ELMA5 för att skicka in listrapporten över försäljning inom EU till den tyska skattemyndigheten. |
| **Ersatt av en annan funktion?**   | Nr         |
| **Produktområden som påverkas**         | Skatt        |
| **Status**                         | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen.   |

### <a name="gl-ssrs-reports"></a>GL SSRS-rapporter

Rapporter som innehåller följande menykommandon har tagits bort: **Råbalanssammanfattning**, **Detaljerad råbalans**, **Kontoplan**, **Redovisningsspårning**, **Saldon** och **Saldolista**.

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Ekonomiska Microsoft SQL Server Reporting Services-rapporter (SSRS) har ersatts av Management Reporter-funktioner och -standardrapporter. |
| **Ersatt av en annan funktion?**   | Management Reporter (med etiketten **Ekonomisk rapportering** i den aktuella versionen av Dynamics AX)    |
| **Produktområden som påverkas**         | Huvudbok   |
| **Status**                         | Borttagen från och med Dynamics AX 7.0.   |

### <a name="infopart-and-formpart-metadata"></a>InfoPart- och FormPart-metadata

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | InfoPart- och FormPart-metadata möjliggjorde genereringen av faktaboxar för två olika klienter. |
| **Ersatt av en annan funktion?**   | InfoPart-metadata, som var en förenklad formulärdefinition, konverteras till ett formulär med uppgraderingsverktyg. FormPart-metadata, som refererade till ett formulär, ersättas av en mer direkt referens som skapas med uppgraderingsverktyg. |
| **Produktområden som påverkas**         | Alla moduler    |
| **Status**                         | Borttagen från och med Dynamics AX 7.0.        |

### <a name="main-account-list-page"></a>Listsida för huvudkonton

En lista med konton för den juridiska personen och tillhörande saldoinformation

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Information om saldo är tillgänglig på listsidan **Råbalans** efter konto och dimension.  |
| **Ersatt av en annan funktion?**   | **Huvudkonton** innehåller samma lista med konton som listsidan **Huvudkonto**. Rutnätsvyn i **Huvudkonton** visar också en ännu mindre, rutnätslik vy. |
| **Produktområden som påverkas**         | Huvudbok      |
| **Status**                         | Borttagen från och med Dynamics AX 7.0.    |

### <a name="malaysia-and-singapore-bank-cash-flow-report"></a>Rapport om bankkassaflöde för Malaysia och Singapore

Den här funktionen låter användaren skriva ut en kassaflödesrapport som visar transaktioner och information om kassainflöden och kassautflöden för ett visst datumintervall för valda bankkonton.

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Samma information kan erhållas från förfrågningsbanktransaktionen. |
| **Ersatt av en annan funktion?**   | Förfrågningsbanktransaktionen                                            |
| **Produktområden som påverkas**         | Kassa- och bankhantering                                                |
| **Status**                         | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen.          |

### <a name="mexican-cfd-electronic-invoice"></a>Mexikansk elektronisk CFD-faktura

Den här funktionen möjliggjorde genereringen av mexikanska e-fakturor med hjälp av CFD-metoden (Comprobante Fiscal Digital), där företaget signerar fakturan genom att begära den relaterade auktoriseringen från myndigheterna. Den här funktioner ger även en månadsvis rapport som innehåller alla e-fakturor som utfärdats under perioden.

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Metoden är inte längre tillämplig. Genereringen av elektroniska fakturor genom att använda CFD-metoden drogs tillbaka av skattemyndigheterna och ersattes av CFDI-metoden (Comprobante Fiscal Digital a través de Internet), där signeringen delegeras till tredjepartsleverantören (PAC). Den månatliga rapporten har tagits bort och ett förfrågningsalternativ gör det möjligt för användare att fråga om historiska transaktioner. |
| **Ersatt av en annan funktion?**   | Nr    |
| **Produktområden som påverkas**         | Kundfordringar, Projekt   |
| **Status**                         | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen. |

### <a name="mexico-realized-and-unrealized-vat"></a>Realiserad och orealiserad moms för Mexiko

Microsoft Dynamics AX 2012 hanterade orealiserad mervärdesskatt (VAT) genom att använda funktioner specifika för Mexiko för ”orealiserad moms”.

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Dubblettfunktion  |
| **Ersatt av en annan funktion?**   | Ja, den här funktionen har ersatts av standardfunktioner för villkorlig moms som tillhandahålls av basen. |
| **Produktområden som påverkas**         | Skatt   |
| **Status**                         | Inaktuell: Borttagningsdatum har inte ställts in för den här funktionen. |

### <a name="microsoft-outlook-integration"></a>Microsoft Outlook-integrering


|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Den här funktionen har ersatts av Microsoft Exchange Server-integrering. |
| **Ersatt av en annan funktion?**   | Ja                                                                            |
| **Produktområden som påverkas**         | Försäljning och marknadsföring                                                            |
| **Status**                         | Borttagen från och med Dynamics AX 7.0.                                                 |

### <a name="private-blocking-of-inventory-and-warehouse-management-journals"></a>Privat blockering av inventerings- och lagerhanteringsjournaler

Inventerings- och lagerställejournalerna stöder inte längre möjligheten att markera en journal som privat för en vald användare. Endast processen för att blockera journaler som privata för användargrupper och blockering under redigering stöds.

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Ingen användning av funktionen påträffades. |
| **Ersatt av en annan funktion?**   | Nr                                     |
| **Produktområden som påverkas**         | Lagerhantering                   |
| **Status**                         | Borttagen från och med Dynamics AX 7.0.         |

### <a name="product-builder"></a>Product Builder

Product Builder användes för att dynamiskt konfigurera artiklar från en försäljningsorder, inköpsorder, tillverkningsorder, försäljningsoffert, projektoffert eller artikelbehov. Baserat på en produktmodell, som hade modellvariabler, kunde användaren välja värden för att uppfylla kundkraven och för att få en unik produktvariant som hade en strukturlista och ett flöde.

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Product Builder exponerade X++-kod till slutanvändare och stöds inte i den aktuella versionen av Dynamics AX. Den har tagits bort för att undvika dubbelt underhållsarbete med överlappande, ansenliga kodbaser.  |
| **Ersatt av en annan funktion?**   | Ja. Begränsningsbaserad konfiguration infördes i Dynamics AX 2012 där avskrivningen av Product Builder i kommande versioner har tillkännagivits. Den begränsningsbaserade konfigurationstekniken väljs på produktmallarna för att möjliggöra konfigurationen. Mer information finns i [skapa en modell för produktkonfiguration](https://docs.microsoft.com/en-us/dynamics365/unified-operations/supply-chain/pim/build-product-configuration-model). |
| **Produktområden som påverkas**         | Produktinformationshantering, Försäljning och marknadsföring  |
| **Status**                         | Borttagen från och med Dynamics AX 7.0.      |

### <a name="rename-product-dimension"></a>Byt namn på produktdimension

Den här funktionen låter dig ändra namnet på en av de tre standardproduktdimensionerna (storlek, färg eller format) till ett namn som passar bättre för dina affärsbehov. Namnändringen inkluderade alla etiketter där produktdimensionsnamnet användes.

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Den aktuella versionen av Dynamics AX stöder inte etikettändringar under körning. |
| **Ersatt av en annan funktion?**   | Nr                                                                            |
| **Produktområden som påverkas**         | Produktinformationshantering                                                |
| **Status**                         | Borttagen från och med Dynamics AX 7.0.                                                |

### <a name="retail-server-connectivity-using-http"></a>Retail Server-anslutning använder HTTP

I Dynamics AX 2012 R3 kan Retail Server med hjälp av HTTP-kommunikation (icke-säker). Detta var förutom standardkommunikationen med HTTPS.

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | På grund av nya säkerhetskrav stöds endast säker kommunikation med TLS 1.2 (eller högre om tillgängligt) nu. Installationsprogrammet för självbetjäning konfigurerar automatiskt datorn för den här kommunikationen. |
| **Ersatt av en annan funktion?**   | Nr. Endast standardkommunikation för HTTPS stöds nu. |
| **Produktområden som påverkas**         | Retail Server  |
| **Status**                         | Borttagen från och med Dynamics AX 7.0. |

### <a name="role-center-pages"></a>Rollcentersidor

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Rollcentersidor skapades på den inaktuella Enterprise Portal-plattformen, som har ersatts av den nya webbklientplattformen i den aktuella versionen av Dynamics AX. |
| **Ersatt av en annan funktion?**   | Det nya arbetsyteformulärmönstret förser användare med en processcentrerad design som tillhandahåller enkel åtkomst till vanliga uppgifter i den processen.                       |
| **Produktområden som påverkas**         | Alla moduler    |
| **Status**                         | Borttagen från och med Dynamics AX 7.0.   |

### <a name="sales-tax-jurisdictions"></a>Skattemyndigheter

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Låg kundanvändning och en begränsad uppsättning funktioner. |
| **Ersatt av en annan funktion?**   | Nr                                           |
| **Produktområden som påverkas**         | USA-moms                                 |
| **Status**                         | Borttagen från och med Dynamics AX 7.0.               |

### <a name="sites-services"></a>Platstjänster

Med hjälp av webbplatstjänster kan du utöka dina affärsprocesser till Internet utan IT-support.

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Microsoft Azure-infrastrukturen, som användes av Dynamics AX, har nya kapaciteter som kan användas i stället (exempelvis, Azure-webbplatser). |
| **Ersatt av en annan funktion?**   | Nr   |
| **Produktområden som påverkas**         | Rekrytering av personal, ärendehantering, begäran om offerter, registrering av leverantör, samarbetsplatser för affärsmöjligheter och kampanjer  |
| **Status**                         | Borttagen från och med Dynamics AX 7.0.    |

### <a name="ssas-demand-forecasting-strategy"></a>SSAS-tjänster för efterfrågeprognosticering

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Utformningen av den här funktionen stöds inte i den nya arkitekturen i molnet. |
| **Ersatt av en annan funktion?**   | Efterfrågeprognosticeringsstrategi för Azure-maskininlärning                           |
| **Produktområden som påverkas**         | Huvudplanering                                                              |
| **Status**                         | Borttagen från och med Dynamics AX 7.0.                                               |

### <a name="vendor-invoice-pool-excluding-posting-details"></a>Leverantörsfakturapool utan bokföringsdetaljer

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Låg användning. Den här funktionen har ersatts av fakturajournalen som har en arbetsflödesfunktion. |
| **Ersatt av en annan funktion?**   | Arbetsflödesfunktionerna i Fakturajournal.     |
| **Produktområden som påverkas**         | Leverantörsreskontra |
| **Status**                         | Borttagen från och med Dynamics AX 7.0.    |


### <a name="virtual-company-accounts"></a>Virtuella företagskonton

Funktionen för virtuella företag stöds inte längre i Dynamics AX. Funktionen för virtuella företag gjorde att användarna kunde ställa in register som kunde delas av en uppsättning företag. Du kan hitta en beskrivning av funktionen här: [Företagskonton och konton för virtuella företag](https://msdn.microsoft.com/en-us/library/aa834382(v=ax.10).aspx). Funktionen fungerar genom att gruppera register i samlingar som tilldelas till virtuella företag, som är grupper med befintliga ”verkliga” företag. Frågor skapas så att alla företag i det virtuella företaget kan komma åt data i registren för de associerade registersamlingarna.

|   |  | 
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | - Virtuella företag måste ställas in innan data lagras i registren. Det är mycket svårt att ställa in virtuella företag efter en befintlig implementering i efterhand.<br><br>- Eftersom det har gjorts så mycket datanormalisering i den aktuella versionen av Microsoft Dynamics AX har det blivit svårt att veta vad som ska lägga till i registersamlingarna. Till exempel är det svårt att veta vilka register som ska delas. Alla register som refereras från register som ingår i ett virtuellt företag måste också läggas till. Registernormalisering har inneburit att även enkla huvuddata som är fördelade över flera register måste vara en del av det virtuella företaget. Alla misstag som begås här kommer att leda till funktionsproblem.<br><br>- När ett register ingår i ett virtuellt företag förlorar det information om informationens ursprung, och endast det virtuella företaget registreras.   |
| **Ersatt av en annan funktion?** | Globala register kan användas för att göra register tillgängliga från alla företag. För närvarande finns det ingen ersättning. |   
| **Produktområden som påverkas**       | Alla moduler |   
| **Status**                       | Borttagen från och med Dynamics AX 7.0.   |   

### <a name="windows-8-tablet-app"></a>Windows 8 surfplatteapp

Windows 8 surfplatteapp gav funktion för utgiftsregistrering och godkännande.

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Finance and Operations är kompatibel med surfplattor. Surfplatteappen behövs inte längre.    |
| **Ersatt av en annan funktion?**   | Nr.          |
| **Produktområden som påverkas**         | Utläggshantering   |
| **Status**                         | Borttagen: Den här funktionen är bara tillgänglig för Dynamics AX 2012 R3. |

### <a name="workplanner"></a>Arbetsplanerare

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Låg användning |
| **Ersatt av en annan funktion?**   | Nej, men sidan **Profilrelation**, som öppnas från sidan **Profilgrupper** stöder samma affärsscenario som den inaktuella sidan **Arbetsplanerare**. |
| **Produktområden som påverkas**         | Tid och närvaro     |
| **Status**                         | Koden har inte tagits bort. Formuläret JmgWorkPlanner har emellertid inte migrerats.    |

### <a name="x-financial-statements"></a>X++-bokslut

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Funktionen har ersatts med en annan funktion.                                    |
| **Ersatt av en annan funktion?**   | Management Reporter (med etiketten **Ekonomisk rapportering** i den aktuella versionen av Dynamics AX) |
| **Produktområden som påverkas**         | Huvudbok                                                                              |
| **Status**                         | Borttagen från och med Dynamics AX 2012.                                                              |

