---
title: "Äldre funktioner"
description: "I det här avsnittet beskrivs funktioner som har tagits bort, eller har planerats för borttagning."
author: sericks007
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.search.scope: Operations, Platform
ms.custom: 21821
ms.assetid: 31019808-4cbf-47d7-b1ba-d791db4281ae
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 6
ms.translationtype: Human Translation
ms.sourcegitcommit: 3267bd1cbd738b5ced9996fc3b28eee211627591
ms.openlocfilehash: 8feffb27b5d08a9c90e97ac0d7e00abf0448d0df
ms.contentlocale: sv-se
ms.lasthandoff: 06/16/2017


---

# Äldre funktioner
<a id="deprecated-features" class="xliff"></a>

[!include[banner](../includes/banner.md)]

I det här avsnittet beskrivs funktioner som har tagits bort, eller har planerats för borttagning.

## Funktioner som har tagits bort från Dynamics 365 for Finance and Operations, Enterprise edition juli 2017 uppdatering
<a id="features-that-have-been-deprecated-in-dynamics-365-for-finance-and-operations-enterprise-edition-july-2017-update" class="xliff"></a>

### Warehouse Mobile Devices-portalen
<a id="warehouse-mobile-devices-portal" class="xliff"></a>

Warehouse mobile devices portalen (WMDP) är en fristående komponent som är avsedd för eget lokal distribution. Denna komponent stöds inte längre i Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition. Ett enhetligt program som förbättrar användarupplevelsen har ersatt funktionen i WMDP. 

|                                  |                                                 |
|----------------------------------|-------------------------------------------------|
| **Orsak till avskrivning**       | Dubblettfunktion.                        |
| **Ersatt av en annan funktion?** | Ja. Den här funktionen har ersatts av Finance and Operations - lagring. Mer information om inställningar och krav finns i [installera och konfigurera Microsoft Dynamics 365 for Finance and Operations - lagring](https://docs.microsoft.com/en-us/dynamics365/unified-operations/supply-chain/warehousing/install-configure-warehousing-app). |
| **Påverkade moduler**             | Lager- och transporthantering |

### Avancerad matchningsregel för bankavstämning för manuell matchning
<a id="advanced-bank-reconciliation-matching-rule-for-manual-matching" class="xliff"></a>

En matchningsregel användes för att välja och markera ett bankdokument när dokumenten manuellt matchades i avstämningskalkylarket.

|                                  |                                                                                        |
|----------------------------------|----------------------------------------------------------------------------------------|
| **Orsak till avskrivning**       | Begränsad användning.                                                                         |
| **Ersatt av en annan funktion?** | Nr. Kolumnfiltreringsmöjligheter ska användas för att söka efter dokument för avstämning. |
| **Påverkade moduler**             | Kassa- och bankhantering                                                               |

### Windows 8 surfplatteapp
<a id="windows-8-tablet-app" class="xliff"></a>

Windows 8 surfplatteapp gav funktion för utgiftsregistrering och godkännande.

|                                  |                                                                                          |
|----------------------------------|------------------------------------------------------------------------------------------|
| **Orsak till avskrivning**       | Finance and Operations är kompatibel med surfplattor. Surfplatteappen behövs inte längre. |
| **Ersatt av en annan funktion?** | Nr.                                                                                      |
| **Påverkade moduler**             | Utläggshantering                                                                       |


Funktioner som har föråldrats i Dynamics 365 for Operations 1611 med plattformuppdatering 3
<a id="features-that-have-been-deprecated-in-dynamics-365-for-operations-1611-with-platform-update-3" class="xliff"></a>
---------------------------------------------------------------------------------------------

### AEB-betalningformat för Spanien
<a id="aeb-payment-formats-for-spain" class="xliff"></a>

Betalningsformaten för Consejo Superior Bancario används för att skicka remissafiler till banken för kundbetalningar och leverantörsbetalningar. Innehållet i dessa format bestäms av Asociación Española de Banca. Det omfattar Cuaderno 19, 32, 58, 34.

|                              |                                                                          |
|------------------------------|--------------------------------------------------------------------------|
| Orsak till avskrivning       | Betalningformaten används inte längre.                                  |
| Ersatt av en annan funktion? | Ja, ISO20022 kreditöverföring och betalningsformat för autogiro för Spanien |
| Påverkade moduler             | Leverantörsreskontra, Kundreskontra                                    |

### Bankbetalningar överför för Litauen
<a id="bank-payments-transfer-for-lithuania" class="xliff"></a>

Bankbetalningsöverföringar skapas och skrivs ut genom att använda exportformatet för betalningsöverföring (LT) för Litauen. Den litauiska marknaden har börjat använda LITASEN, det enade elektroniska banksystemet år 2005.

|                              |                                                            |
|------------------------------|------------------------------------------------------------|
| Orsak till avskrivning       | Betalningformaten används inte längre.                    |
| Ersatt av en annan funktion? | Ja, ISO20022 betalningsformat för kreditöverföring för Litauen |
| Påverkade moduler             | Leverantörsreskontra                                           |

### BBS Direkte Remittering betalningsformat för Norge
<a id="bbs-direkte-remittering-payment-formats-for-norway" class="xliff"></a>

BBS Direkte Remittering betalningsformat inkluderar exportinkasso för kundbetalning (autogiro) och import av returmeddelande.

|                              |                                                                                                                                                                |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Betalningformaten används inte längre.                                                                                                                        |
| Ersatt av en annan funktion? | Kundbetalningsformatet för AvtaleGiro för Norge kan användas för att generera autogiro-meddelanden. Import av returmeddelande kommer att implementeras i kommande versioner. |
| Påverkade moduler             | Leverantörsreskontra, Kundreskontra                                                                                                                          |

### Verktyg för kontoplan från Spanien
<a id="chart-of-accounts-tool-for-spain" class="xliff"></a>

Det här verktyget används när en kontoplan i Spanien kräver stora ändringar. Användarna kan importera en ny kontoplan i Microsoft Excel eller textformat och kan också importera bokslut.

|                              |                |
|------------------------------|----------------|
| Orsak till avskrivning       | Begränsad användning  |
| Ersatt av en annan funktion? | Nr             |
| Påverkade moduler             | Huvudbok |

### Dom80 betalningsformat för Belgien
<a id="dom80-payment-format-for-belgium" class="xliff"></a>

Äldre belgiskt betalningsformat för betalningsinsamling (autogiro).

|                              |                                                        |
|------------------------------|--------------------------------------------------------|
| Orsak till avskrivning       | Betalningformatet används inte längre.                  |
| Ersatt av en annan funktion? | Ja, ISO 20022 betalningsformat för autogiro för Belgien. |
| Påverkade moduler             | Kundreskontra                                    |

### DTA/EZAG-betalningformat för Schweiz
<a id="dtaezag-payment-formats-for-switzerland" class="xliff"></a>

DTA-/EZAG-format integreras i ESR-systemet, eftersom de kan ha ett referensnummer. Eftersom referensnumret inte är obligatoriskt kan dessa format användas för att bearbeta alla leverantörsbetalningar. Dessa format används av företag som har ett bankkonto på en annan plats än “Postfinance.”

|                              |                                                              |
|------------------------------|--------------------------------------------------------------|
| Orsak till avskrivning       | Betalningformaten används inte längre.                      |
| Ersatt av en annan funktion? | Ja, ISO20022 betalningsformat för kreditöverföring för Schweiz. |
| Påverkade moduler             | Leverantörsreskontra                                             |

### EDIFACT - DIRDEB-betalningformat för Österrike
<a id="edifact-dirdeb-payment-format-for-austria" class="xliff"></a>

EDIFACT-DIRDEB-betalningsformat för betalningsinsamling (autogiro).

|                              |                                                        |
|------------------------------|--------------------------------------------------------|
| Orsak till avskrivning       | Betalningformatet används inte längre.                  |
| Ersatt av en annan funktion? | Ja, ISO 20022 betalningsformat för autogiro för Österrike. |
| Påverkade moduler             | Kundreskontra                                    |

### EDIVAT för Belgien
<a id="edivat-for-belgium" class="xliff"></a>

EDIVAT är en inaktuell belgisk standard för elektronisk deklaration säker via e-post. Microsoft Dynamics AX 2012 har kvar den skrivskyddade lösningen för att tillåta åtkomst till de historiska data.

|                              |                                      |
|------------------------------|--------------------------------------|
| Orsak till avskrivning       | Funktionen används inte längre. |
| Ersatt av en annan funktion? | Nr                                   |
| Påverkade moduler             | Huvudbok                       |

### eGiro EDIFACT CREMUL-betalningsformat för Norge
<a id="egiro-edifact-cremul-payment-import-format-for-norway" class="xliff"></a>

eGiro baseras på den internationella UN EDIFACT CREMUL-standarden (Multiple Credit Advice Message) som används för automatisk bokföring av kundbetalningar. I Microsoft Dynamics AX tillämpas eGiro som ett importformat för kundbetalning.

|                              |                                                                                           |
|------------------------------|-------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Betalningformatet används inte längre.                                                     |
| Ersatt av en annan funktion? | Nr. Formatet ska ersättas med ISO 20022-utdragsimportformat i kommande versioner. |
| Påverkade moduler             | Kundreskontra                                                                       |

### Externt lager för Polen
<a id="external-inventory-for-poland" class="xliff"></a>

Bevis av varor som tas från en leverantör för försäljning utan inköp. De varor som hanteras i externt lager, som inte påverkar standardlager, kan säljas och sedan köpas in automatiskt. Den här processen skapar verkliga lagerrörelser.

|                              |                                                 |
|------------------------------|-------------------------------------------------|
| Orsak till avskrivning       | Ersatt av en annan funktion                     |
| Ersatt av en annan funktion? | Ja, försändelsefunktionen för den inkommande kärnan |
| Påverkade moduler             | Leverantörsreskontra, lagerhantering          |

### Ekonomisk rapportgenerator för Östra Europa
<a id="financial-reports-generator-for-eastern-europe" class="xliff"></a>

Ett verktyg för att ställa in datainsamling för redovisning och momsrapporter behövs och exportera data till XLS och DOC-rapportmallar

|                              |                                                                                          |
|------------------------------|------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Begränsad användning                                                                            |
| Ersatt av en annan funktion? | Nr. Verktyget ska ersättas av elektroniska rapporteringskonfigurationer i kommande versioner. |
| Påverkade moduler             | Redovisning                                                                           |

### Import av kundbetalningstransaktioner för Finland
<a id="import-of-customer-payment-transactions-for-finland" class="xliff"></a>

Du kan välja ett importformat för finska betalningar som importerar kundbetalningstransaktioner från en extern fil som tillhandahålls av banken.

|                              |                                                                                           |
|------------------------------|-------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Betalningformatet används inte längre.                                                     |
| Ersatt av en annan funktion? | Nr. Formatet ska ersättas med ISO 20022-utdragsimportformat i kommande versioner. |
| Påverkade moduler             | Kundreskontra                                                                       |

### Import av betalningstransaktioner till en redovisningsjournal för Finland
<a id="import-of-payment-transactions-into-a-general-ledger-journal-for-finland" class="xliff"></a>

Ett format som är specifik för Finland används för att importera redovisningstransaktioner till redovisningen.

|                              |                                                                                           |
|------------------------------|-------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Betalningformatet används inte längre.                                                     |
| Ersatt av en annan funktion? | Nr. Formatet ska ersättas med ISO 20022-utdragsimportformat i kommande versioner. |
| Påverkade moduler             | Kundreskontra                                                                       |

### Integration med Isabel-synkroniserad (CIS) för Belgien
<a id="integration-with-isabel-synchronized-cis-for-belgium" class="xliff"></a>

Isabel är ramverket för elektronisk bankverksamhet i Europa och en de facto-standard i Belgien.

|                              |                                                                                                                      |
|------------------------------|----------------------------------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Integration med Isabel-klienten har annullerats.                                                                |
| Ersatt av en annan funktion? | Nr. Betalningsformaten som inte längre används ersätts av ISO20022-betalningsformat för kreditöverföring för Belgien. |
| Påverkade moduler             | Leverantörsreskontra                                                                                                     |

### Ändringar i kontoplanen och redovisningsreglerna för Spanien
<a id="modifications-in-the-chart-of-accounts-and-accounting-rules-for-spain" class="xliff"></a>

Den här funktionen används för ändringar i kontoplanen och redovisningsreglerna i Spanien. Den mappar konton för att transformera den gamla kontoplanen till den nya kontoplanen och jämföra det föregående räkenskapsåret med det nya räkenskapsåret, även om de bokförts till ett annat kontonummer.

|                              |                |
|------------------------------|----------------|
| Orsak till avskrivning       | Begränsad användning  |
| Ersatt av en annan funktion? | Nr             |
| Påverkade moduler             | Huvudbok |

### Pagamento Fornittori leverantörsbetalningsformat
<a id="pagamento-fornittori-vendor-payment-format" class="xliff"></a>

Äldre italienskt betalningsformat för kreditöverföringar.

|                              |                                                        |
|------------------------------|--------------------------------------------------------|
| Orsak till avskrivning       | Betalningformatet används inte längre.                  |
| Ersatt av en annan funktion? | Ja, ISO20022 betalningsformat för kreditöverföring för Italien |
| Påverkade moduler             | Leverantörsreskontra                                       |

### Exportformat för betalning för Estland
<a id="payment-export-formats-for-estonia" class="xliff"></a>

Formaten Telehansa och Teleservice används för bankbetalningsexport.

|                              |                                                          |
|------------------------------|----------------------------------------------------------|
| Orsak till avskrivning       | Betalningformaten används inte längre.                  |
| Ersatt av en annan funktion? | Ja, ISO20022 betalningsformat för kreditöverföring för Estland |
| Påverkade moduler             | Leverantörsreskontra                                         |

### Betalningsfilarkiv för Norge
<a id="payment-file-archive-for-norway" class="xliff"></a>

När betalningsfiler genereras arkiverar filarkivet automatiskt alla filer som skapas, även filer som tidigare skrevs eller lästes.

|                              |                                                                    |
|------------------------------|--------------------------------------------------------------------|
| Orsak till avskrivning       | Ersatt av en annan funktion                                        |
| Ersatt av en annan funktion? | Ja, arkiverade elektroniska rapporteringsjobb                            |
| Påverkade moduler             | Kundreskontra, leverantörsreskontra, organisationadministration |

### Importformat för betalning för Estland
<a id="payment-import-formats-for-estonia" class="xliff"></a>

Formaten Telehansa och TeleTeenu används för bankbetalningsimport.

|                              |                                                                                            |
|------------------------------|--------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Betalningformaten används inte längre.                                                    |
| Ersatt av en annan funktion? | Nr. Formaten ska ersättas med ISO 20022-utdragsimportformat i kommande versioner. |
| Påverkade moduler             | Kundreskontra                                                                        |

### Arbetsflöde för prestationshanteringmål
<a id="performance-management-goal-workflow" class="xliff"></a>

Prestationshantering inkluderar målhantering och integration med prestationsgranskning.

|                              |                                                                                                                          |
|------------------------------|--------------------------------------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Prestationshantering formades om, och antalet målsidor förminskades för att förenkla processen.                 |
| Ersatt av en annan funktion? | Nr. Mål kan visas för chefer via portalen Självbetjäning för chef, och kan ändras och visas av chefen. |
| Påverkade moduler             | Administration av humankapital                                                                                                 |

### Postgirot och Postgirot Utland betalningsformat för Sverige
<a id="postgirot-and-postgirot-utland-payment-formats-for-sweden" class="xliff"></a>

Postgirot och Postgirot Utland betalningsformat för Sverige.

|                              |                                                         |
|------------------------------|---------------------------------------------------------|
| Orsak till avskrivning       | Betalningformaten används inte längre.                 |
| Ersatt av en annan funktion? | Ja, ISO20022 betalningsformat för kreditöverföring för Sverige |
| Påverkade moduler             | Leverantörsreskontra                                        |

### Radiofrekvensidentifiering
<a id="radio-frequency-identifier" class="xliff"></a>

Radiofrekvensidentifiering (RFID) är en datainsamlingsteknik som använder elektroniska taggar för att lagra identifieringsdata och en läsare utan krav på fri sikt som fångar upp identifieringsdatan.

|                              |                                               |
|------------------------------|-----------------------------------------------|
| Orsak till avskrivning       | Låg kundanvändning och en begränsad uppsättning funktioner. |
| Ersatt av en annan funktion? | Ingen                                            |
| Påverkade moduler             | Lagerhantering                          |

### Rapport om numrering av statliga fakturor för Lettland
<a id="report-about-state-invoices-numbering-for-latvia" class="xliff"></a>

Lettisk lagstiftning innehåller särskilda regler om hur försäljningsfakturor ska numreras. Funktionen låter dig tilldela specifika nummer till försäljningsfakturor som baseras på användaren eller användargruppen. Du kan sedan skapa en rapport eller en XML-fil. Du kan även skriva ut en rapport om fakturanummer som används.

|                              |                                                                                                                          |
|------------------------------|--------------------------------------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Numrering av statliga fakturor måste inte längre underhållas. Rapporten om använda fakturanummer är inte längre obligatorisk. |
| Ersatt av en annan funktion? | Nr                                                                                                                       |
| Påverkade moduler             | Kundreskontra                                                                                                      |

### Ställ in namnen för chefen och den allmänna revisorn i ett företag för Litauen
<a id="set-up-the-names-of-the-manager-and-general-accountant-of-a-company-for-lithuania" class="xliff"></a>

Namnen på chefen och den allmänna revisorn i ett företag kan anges i företagsinformationen och användas vid olika lokala rapportutskrifter.

|                              |                                                                 |
|------------------------------|-----------------------------------------------------------------|
| Orsak till avskrivning       | Ersatt av en annan funktion                                     |
| Ersatt av en annan funktion? | Ja, inställningen av för tjänstemän kan användas för samma syfte.   |
| Påverkade moduler             | Leverantörsreskontra, Kundreskontra och Kassa- och bankhantering |

### Telepay betalningsformat för Norge
<a id="telepay-payment-formats-for-norway" class="xliff"></a>

Telepay betalningsformat inkluderar leverantörsbetalningsexporten (kreditöverföring) och inkasso för kundbetalning (autogiro).

|                              |                                                                                                |
|------------------------------|------------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Betalningformaten används inte längre.                                                        |
| Ersatt av en annan funktion? | Ja, ISO20022 betalningsformat för kreditöverföring och AvtaleGiro kundbetalningsformat för Norge |
| Påverkade moduler             | Leverantörsreskontra, Kundreskontra                                                          |

### Exportformat för leverantörsbetalning för Finland
<a id="vendor-payment-export-formats-for-finland" class="xliff"></a>

Två format för att exportera betalningar är tillgängliga för Finland. LM02 (FI) används för lokala betalningar och LUM2 (FI) används för utländska betalningar.

|                              |                                                          |
|------------------------------|----------------------------------------------------------|
| Orsak till avskrivning       | Betalningformaten används inte längre.                  |
| Ersatt av en annan funktion? | Ja, ISO20022 betalningsformat för kreditöverföring för Finland |
| Påverkade moduler             | Leverantörsreskontra                                         |

### Arbetsflöde för att skapa mål
<a id="workflow-for-creating-goals" class="xliff"></a>

Ett arbetsflöde för hantering av genereringen av medarbetare är en av flera arbetsflöden som är tillgängliga för att hjälpa till att koordinera prestandahanteringsprocessen.

|                              |                                                                                                                                                                                                                                                                                                                                        |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Prestandahantering har helt formats om i Microsoft Dynamics 365 for Finance and Operations.                                                                                                                                                                                                                                        |
| Ersatt av en annan funktion? | Den omformade prestandahanteringsfunktionen innehåller mer kontroll över innehållet av mål, måtten som används för att spåra framsteg och bilaga med förklarande dokumentation. Mål kan lagras som mallar och sedan återanvändas. Den här funktionen kan hjälpa dig att snabbare ställa in ytterligare mål för medarbetarna. |
| Påverkade moduler             | Administration av humankapital                                                                                                                                                                                                                                                                                                               |

## Funktioner som är föråldrade i Dynamics AX 7.0-versioner
<a id="features-deprecated-in-dynamics-ax-70-releases" class="xliff"></a>
### Möjligheten att avbryta ändringar i en leverantörsfaktura
<a id="ability-to-cancel-changes-to-a-vendor-invoice" class="xliff"></a>

|                              |                         |
|------------------------------|-------------------------|
| Orsak till avskrivning       | Prestandaförbättring |
| Ersatt av en annan funktion? | Nej                      |
| Påverkade moduler             | Leverantörsreskontra        |

### AIF-, AxD- och AxBC-integrationer
<a id="aif-axd-and-axbc-integrations" class="xliff"></a>

I AIF (Application Integration Framework) kan data utbytas med externa system genom affärslogik som exponeras som tjänster. Microsoft Dynamics AX omfattar tjänster som baseras på dokument och .NET Business Connector (AxBC). Ett dokument skapas genom att använda XML. XML inkluderar rubrikinformation som läggs till för att skapa ett *meddelande* som kan överföras till eller från Microsoft Dynamics AX. Exempel på dokument innehåller försäljningsorder och inköpsorder. Dock kan nästan alla enheter, till exempel en kund, representeras av ett dokument. Tjänster som baseras på dokument använder klasserna **Axd &lt;*Dokument*&gt;**.

|                              |                                                                                                                                                                                                          |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Arkitekturen för AIF och AxDs kunde inte skalas till en molntjänst. Det fanns prestandaproblem relaterade till massimport.                                                                               |
| Ersatt av en annan funktion? | I den aktuella versionen av Dynamics AX har den här funktionen ersatts av ramverket för dataimport/dataexport som stöder återkommande massimport/massexport. För AxBC rekommenderar vi att du använder faktiska tabeller. |
| Påverkade moduler             | AxDs, AxBCs och AIF                                                                                                                                                                                     |

### Strukturlistor utan strukturlisteversioner
<a id="boms-without-bom-versions" class="xliff"></a>

När konfigurationsnyckeln för **strukturlisteversioner** inaktiverades doldes strukturlisteversioner i alla formulär och systemet framtvingade en 1:1-relation mellan frisläppta produkter och strukturlistor. I den aktuella versionen av Dynamics AX kan konfigurationsnyckeln för **strukturlisteversioner** inte inaktiveras.

|                              |                                                                                         |
|------------------------------|-----------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Användningen av en konfigurationsnyckel för att kontrollera strukturlisteversioner kan inte skalas till en molnmiljö. |
| Ersatt av en annan funktion? | Nej                                                                                      |
| Påverkade moduler             | Produktinformationshantering, Lagerhantering                                    |

### Brasilian Bordero
<a id="brazilian-bordero" class="xliff"></a>

Specifik betalningsmetod för brasilianska företag

|                              |                                                                                                       |
|------------------------------|-------------------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Stöd för den brasilianska Bordero-betalningsmetoden har annullerats från brasiliansk lokalisering |
| Ersatt av en annan funktion? | Nr                                                                                                    |
| Påverkade moduler             | Leverantörsreskontra                                                                                      |

### Brazilian Sintegra-utdrag
<a id="brazilian-sintegra-statement" class="xliff"></a>

Federala skatteutdrag för ICMS-moms

|                              |                                                                                                                       |
|------------------------------|-----------------------------------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Detta utdrag används inte längre i vissa brasilianska stater.                                                     |
| Ersatt av en annan funktion? | Nr. Användare kan använda den allmänna funktionen för elektronisk rapportering för att konfigurera utdraget, om det krävs och i vissa fall. |
| Påverkade moduler             | Skatteböcker                                                                                                          |

### Brasiliansk SCAN eventualitetläge för NF-e
<a id="brazilian-scan-contingency-mode-for-nf-e" class="xliff"></a>

(SCAN) eventualitetmiljön används för att generera, exportera och importera status för Nota Fiscal eletrônica (NF-e) när miljön för Secretaria da Fazenda (SEFAZ) inte är tillgänglig.

|                              |                                                                             |
|------------------------------|-----------------------------------------------------------------------------|
| Orsak till avskrivning       | Den här eventualitetsmetoden används inte längre i alla brasilianska stater |
| Ersatt av en annan funktion? | Nr                                                                          |
| Påverkade moduler             | Kundreskontra                                                         |

### Business Analyzer
<a id="business-analyzer" class="xliff"></a>

Det här mobila programmet låter användare granska viktiga affärsmått.

|                              |                                                                                                                                                               |
|------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Funktionen har ersatts med en annan funktion.                                                                                                      |
| Ersatt av en annan funktion? | Innehållspaketet för övervakning av ekonomiska resultat för Microsoft PowerBI kommer att inkludera samma ekonomiska mätvärden som tidigare var tillgängliga i Business Analyzer. |
| Påverkade moduler             | Huvudbok                                                                                                                                                |

### Affärsstatistik
<a id="business-statistics" class="xliff"></a>

Konfigurationen av frågor om affärsstatistik som kan hjälpa dig att analysera organisationens resultat

|                              |                                                                                              |
|------------------------------|----------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Gammal metod för BI (Business Intelligence), låg kundanvändning och en begränsad funktionsuppsättning |
| Ersatt av en annan funktion? | Nya BI-lösningar för den aktuella versionen av Dynamics AX                                      |
| Påverkade moduler             | Anskaffning och sourcing, Leverantörsreskontra, Försäljning och marknadsföring, Kundreskontra         |

### Funktionen Ändra dokumentets datum i Fakturagodkännandejournal
<a id="change-document-date-function-in-invoice-approval-journal" class="xliff"></a>

|                              |                                                                         |
|------------------------------|-------------------------------------------------------------------------|
| Orsak till avskrivning       | Låg användning                                                               |
| Ersatt av en annan funktion? | Ja. Dokumentdatumet för den bokförda leverantörstransaktionen kan ändras. |
| Påverkade moduler             | Leverantörsreskontra                                                        |

### Betalningsformatet ClieOp03 för Nederländerna
<a id="clieop03-payment-format-for-the-netherlands" class="xliff"></a>

|                              |                                                                                                            |
|------------------------------|------------------------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Formatet är inte längre tillämpligt i Nederländerna eftersom det har ersatts av SEPA-funktionen. |
| Ersatt av en annan funktion? | SEPA-betalningsexport                                                                                       |
| Påverkade moduler             | Alla                                                                                                        |

### Regelefterlevnadscenter
<a id="compliance-center" class="xliff"></a>

Regelefterlevnadscentret var en Enterprise Portal-webbplats för att hantera dokumentationskraven för efterlevnadsinsatser som är relaterade till Sarbanes-Oxley-lagen.

|                              |                                                                                                                        |
|------------------------------|------------------------------------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Brist på kundanvändning. Microsoft SharePoint innehåller samma kapacitet som var tillgänglig i regelefterlevnadscentret. |
| Ersatt av en annan funktion? | Nej                                                                                                                     |
| Påverkade moduler             | Regelefterlevnad och interna kontroller                                                                                       |

### Connector för Microsoft Dynamics
<a id="connector-for-microsoft-dynamics" class="xliff"></a>

Verktyget användes för att integrerar viktiga data från Microsoft Dynamics CRM till Microsoft Dynamics ERP-tillämpningar.

|                              |                                                          |
|------------------------------|----------------------------------------------------------|
| Orsak till avskrivning       | Funktionen har ersatts med en annan funktion. |
| Ersatt av en annan funktion? | Dynamics Integrator                                      |
| Påverkade moduler             | Connector för Microsoft Dynamics                         |

### Behållarenhet och flerdimensionell behållning
<a id="container-unit-and-multi-dimension-on-hand" class="xliff"></a>

|                              |                                                                                                                                                                 |
|------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Dubblettfunktion                                                                                                                                         |
| Ersatt av en annan funktion? | Ja. Sedan AXET 2012 har den här funktionen ersatts av funktionsuppsättning av konsoliderade batchorder. Den här funktionsuppsättningen inkluderar den konsoliderade behållningsvyn. |
| Påverkade moduler             | Produktinformationshantering, Produktionskontroll, Lagerhantering, Försäljning och marknadsföring                                                                   |

### Stackikongruppmetadata
<a id="cue-group-metadata" class="xliff"></a>

|                              |                                                                                                                                                                                                                               |
|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Stackikongrupper användes för att visa en eller flera stackikoner i faktaboxområdet. Upptaget var begränsat och det fanns även prestandaproblem eftersom en poständring i ett överordnat formulär orsakade en fråga per stackikon i stackikongruppen. |
| Ersatt av en annan funktion? | Nej                                                                                                                                                                                                                            |
| Påverkade moduler             | Alla                                                                                                                                                                                                                           |

### Stackikonmetadata
<a id="cue-metadata" class="xliff"></a>

|                              |                                                                                                                                                                                                                                         |
|------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Stackikonmetadata begränsades till information om antal och summor.                                                                                                                                                                                   |
| Ersatt av en annan funktion? | Panelmetadata introducerades för att ge mer flexibilitet för modellering. Du kan till exempel modellera aktuella antal, navigering och KPI:er (Key Performance Indicator). Metadata för antal på panel är en direkt ersättning av stackikonmetadata. |
| Påverkade moduler             | Alla                                                                                                                                                                                                                                     |

### Danskt checkformat
<a id="danish-check-format" class="xliff"></a>

|                              |                                                                                                                         |
|------------------------------|-------------------------------------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Stöd för den danska checkformatlayouten har tagits bort, och rapporten har tagits bort från lokalisering för danska. |
| Ersatt av en annan funktion? | Nej                                                                                                                      |
| Påverkade moduler             | Alla                                                                                                                     |

### Datapartitioner
<a id="data-partitions" class="xliff"></a>

Datapartitioner tillhandahåller en logisk separering av data i Microsoft Dynamics AX-databasen.

|                              |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Datapartitioner introducerades i Microsoft Dynamics AX 2012 R2 för möjliggöra isolering av data. I ett vanligt scenario har ett företag ett dotterbolag och data från ett dotterbolag ska inte vara synliga för ett annat dotterföretag, även om båda dotterbolagen hanteras av samma IT-avdelning. Det behövdes dock extra skript och hantering av information i hela programmet för att skapa nya partitioner och förse dem med data och att säkerhetskopiera partitionsdata. I molnet, där vi har tillgång till plattform som en tjänst (PaaS) databas-tjänster (Microsoft Azure SQL-databasen), är det mycket effektivare att använda en databas som isolerade behållare än att utföra isolering i programmet. Oavsett om datapartition är nödvändig för dotterbolag, för flera innehavare eller för skalning tror vi att scenarier kan hanteras bättre via flera olika databaser eller flera Dynamics AX-instanser. |
| Ersatt av en annan funktion? | Datapartitioner ersätts med stöd för flera databaser eller Dynamics AX-instanser i en framtida version.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| Påverkade moduler             | Alla                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |

### Avgränsning
<a id="delimitation" class="xliff"></a>

|                              |                                        |
|------------------------------|----------------------------------------|
| Orsak till avskrivning       | Ingen användning av funktionen påträffades. |
| Ersatt av en annan funktion? | Nej                                     |
| Påverkade moduler             | Tid och närvaro                    |

### Skrivbordsklient
<a id="desktop-client" class="xliff"></a>

|                              |                                                                                                                                        |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Dynamics AX-klientupplevelsen har formats om för att förbättra användbarheten över flera plattformar och enheter.                      |
| Ersatt av en annan funktion? | Den nya webbklienten baseras på skrivbordsformulärmetadata och programmeringsmodellen som har ändrats för att ge en heltäckande webbplattform. |
| Påverkade moduler             | Allt                                                                                                                                    |

### Direkt databasanslutning
<a id="direct-database-connection" class="xliff"></a>

I Dynamics AX 2012 R3 kunde inte Retail Modern POS ansluta direkt till Channel DB på liknande sätt som till Enterprise POS. Detta var förutom standardkommunikationsmetoden för Retail Modern POS som kommunicerar via Retail Server.  

|                              |                                                                                         |
|------------------------------|-----------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Direkt databasanslutning krävde lägre säkerhetsprotokoll och användes främst för att uppnå högsta möjliga prestanda. På grund av prestanda- och säkerhetsförbättringar som har uppstått i Dynamics 365 for Operations orsakar nu den här funktionen fler problem än den löser. |
| Ersatt av en annan funktion? | Nr. Endast standardkommunikation för Retail Server stöds nu.    |
| Påverkade moduler             | Channel DB/Retail Modern POS                                    |

### Holländsk SWIFT MT940
<a id="dutch-swift-mt940" class="xliff"></a>

|                              |                                                                                                                                                                                                                                       |
|------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Den generiska funktionen används nu i stället för den lokaliserade funktionen.                                                                                                                                                                 |
| Ersatt av en annan funktion? | Ja, den här funktionen har ersatts av funktionen för avancerad bankavstämning. Dessutom planeras implementering av kontoutdragsimporten för camt.053 ISO20022 för den allmänna journalen i nästa uppdatering av Dynamics AX. |
| Påverkade moduler             | Alla                                                                                                                                                                                                                                   |

### eBilanz (XBRL för Tyskland)
<a id="ebilanz-xbrl-for-germany" class="xliff"></a>

Den här funktionen ger eXtensible Business Reporting Language (XBRL)-utdata som är specifikt utformade för tysk eBilanz-taxonomi.

|                              |                                                                                                                                                                        |
|------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Brist på kundanvändning                                                                                                                                                 |
| Ersatt av en annan funktion? | Den här funktionen har inte ersatts av en annan funktion, men flera specialiserade XBRL-paket som innehåller omfattande XBRL-funktioner är tillgängliga för den tyska marknaden. |
| Påverkade moduler             | Management Reporter                                                                                                                                                    |

### Enterprise Portal-klient
<a id="enterprise-portal-client" class="xliff"></a>

|                              |                                                                                                                                        |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | En enskild klientplattform har tillhandahållits.                                                                                            |
| Ersatt av en annan funktion? | Den nya webbklienten baseras på skrivbordsformulärmetadata och programmeringsmodellen som har ändrats för att ge en heltäckande webbplattform. |
| Påverkade moduler             | Alla                                                                                                                                    |

### Miljöhållbarhet
<a id="environmental-sustainability" class="xliff"></a>

|                              |                                                    |
|------------------------------|----------------------------------------------------|
| Orsak till avskrivning       | Låg kundanvändning och en begränsad uppsättning funktioner.       |
| Ersatt av en annan funktion? | Nej                                                 |
| Påverkade moduler             | Efterlevnad och interna kontroller, Leverantörsreskontra |

### ActiveX och de hanterade värdkontroller för formulär
<a id="form-activex-and-managed-host-controls" class="xliff"></a>

|                              |                                                                                                                                                                                               |
|------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | ActiveX och hanterade värdkontroller baseras på den inaktuella skrivbordsklienten.                                                                                                             |
| Ersatt av en annan funktion? | Det utökningsbara kontrollramverket stöder utveckling av nya kontroller som baseras på HTML, CSS och JavaScript, och är en klass 1-kontroll i Microsoft Visual Studio Tooling-miljön. |
| Påverkade moduler             | Alla                                                                                                                                                                                           |

### Generera förauktoriseringar genom att använda en batch
<a id="generate-prenotes-by-using-a-batch" class="xliff"></a>

Genereringen av förauktoriseringar kan inte utföras med hjälp av en batch men kan fortfarande utföras av en användare.

|                              |                                                                                                        |
|------------------------------|--------------------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Inget formulär finns för att bevara och visa den resulterande filen med förauktoriseringar när den genererats med hjälp av en batch. |
| Ersatt av en annan funktion? | Förauktoriseringar kan fortfarande genereras och användaren har kontroll över var filen sparas.   |
| Påverkade moduler             | Leverantörsreskontra, Kundreskontra och Kassa- och bankhantering                                        |

### Tysk DTAUS-betalningsexport och -kontoutdragsimport (summor och transaktioner)
<a id="german-dtaus-payment-export-and-account-statement-import-totals-and-transactions" class="xliff"></a>

|                              |                                                                                                                                                                                                                                                                                                |
|------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Formatet är inte längre tillämpligt i Tyskland eftersom det har ersatts av SEPA-funktionen (Single Euro Payments Area).                                                                                                                                                                 |
| Ersatt av en annan funktion? | Ja, funktionen har ersatts av SEPA-betalningsexport och avancerad bankavstämning för import av kontoutdrag. Dessutom planeras implementering av kontoutdragsimporten för camt.053 ISO20022 för den allmänna journalen i nästa uppdatering av Dynamics AX. |
| Påverkade moduler             | Alla                                                                                                                                                                                                                                                                                            |

### Tyskt DTAZV-betalningsformat
<a id="german-dtazv-payment-format" class="xliff"></a>

|                              |                                                                                                    |
|------------------------------|----------------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Formatet är inte längre tillämpligt i Tyskland eftersom det har ersatts av SEPA-funktionen. |
| Ersatt av en annan funktion? | SEPA-betalningsexport                                                                               |
| Påverkade moduler             | Alla                                                                                                |

### Tysk MT940-import
<a id="german-mt940-import" class="xliff"></a>

|                              |                                                                                                                                                                                                                                       |
|------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Den generiska funktionen används nu i stället för den lokaliserade funktionen.                                                                                                                                                                 |
| Ersatt av en annan funktion? | Ja, den här funktionen har ersatts av funktionen för avancerad bankavstämning. Dessutom planeras implementering av kontoutdragsimporten för camt.053 ISO20022 för den allmänna journalen i nästa uppdatering av Dynamics AX. |
| Påverkade moduler             | Alla                                                                                                                                                                                                                                   |

### Tysk XML-baserad EU-försäljningslista
<a id="german-xml-eu-sales-list" class="xliff"></a>

|                              |                                                                                                                                                                                    |
|------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | XML-formatet för tyska listrapporten över försäljning inom EU stöds inte längre. Det går enbart att använda textfilformatet ELMA5 för att skicka in listrapporten över försäljning inom EU till den tyska skattemyndigheten. |
| Ersatt av en annan funktion? | Nej                                                                                                                                                                                 |
| Påverkade moduler             | Moms                                                                                                                                                                                |

### GL SSRS-rapporter
<a id="gl-ssrs-reports" class="xliff"></a>

Rapporter som innehåller följande menykommandon har tagits bort: **Råbalanssammanfattning**, **Detaljerad råbalans**, **Kontoplan**, **Redovisningsspårning**, **Saldon** och **Saldolista**.

|                              |                                                                                                                                              |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Ekonomiska Microsoft SQL Server Reporting Services-rapporter (SSRS) har ersatts av Management Reporter-funktioner och -standardrapporter. |
| Ersatt av en annan funktion? | Management Reporter (med etiketten **Ekonomisk rapportering** i den aktuella versionen av Dynamics AX)                                                  |
| Påverkade moduler             | Huvudbok                                                                                                                               |

### InfoPart- och FormPart-metadata
<a id="infopart-and-formpart-metadata" class="xliff"></a>

|                              |                                                                                                                                                                                                                                |
|------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | InfoPart- och FormPart-metadata möjliggjorde genereringen av faktaboxar för två olika klienter.                                                                                                                                    |
| Ersatt av en annan funktion? | InfoPart-metadata, som var en förenklad formulärdefinition, konverteras till ett formulär med uppgraderingsverktyg. FormPart-metadata, som refererade till ett formulär, ersättas av en mer direkt referens som skapas med uppgraderingsverktyg. |
| Påverkade moduler             | Alla                                                                                                                                                                                                                            |

### Listsida för huvudkonton
<a id="main-account-list-page" class="xliff"></a>

En lista med konton för den juridiska personen och tillhörande saldoinformation

|                              |                                                                                                                                                                                    |
|------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Information om saldo är tillgänglig på listsidan **Råbalans** efter konto och dimension.                                                                                      |
| Ersatt av en annan funktion? | **Huvudkonton** innehåller samma lista med konton som listsidan **Huvudkonto**. Rutnätsvyn i **Huvudkonton** visar också en ännu mindre, rutnätslik vy. |
| Påverkade moduler             | Huvudbok                                                                                                                                                                     |

### Rapport om bankkassaflöde för Malaysia och Singapore
<a id="malaysia-and-singapore-bank-cash-flow-report" class="xliff"></a>

Den här funktionen låter användaren skriva ut en kassaflödesrapport som visar transaktioner och information om kassainflöden och kassautflöden för ett visst datumintervall för valda bankkonton.

|                              |                                                                         |
|------------------------------|-------------------------------------------------------------------------|
| Orsak till avskrivning       | Samma information kan erhållas från förfrågningsbanktransaktionen. |
| Ersatt av en annan funktion? | Förfrågningsbanktransaktionen                                            |
| Påverkade moduler             | Kassa- och bankhantering                                                |

### Mexikansk elektronisk CFD-faktura
<a id="mexican-cfd-electronic-invoice" class="xliff"></a>

Den här funktionen möjliggjorde genereringen av mexikanska e-fakturor med hjälp av CFD-metoden (Comprobante Fiscal Digital), där företaget signerar fakturan genom att begära den relaterade auktoriseringen från myndigheterna. Den här funktioner ger även en månadsvis rapport som innehåller alla e-fakturor som utfärdats under perioden.

|                              |                                                                                                                                                                                                                                                                                                                                                                                                           |
|------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Metoden är inte längre tillämplig. Genereringen av elektroniska fakturor genom att använda CFD-metoden drogs tillbaka av skattemyndigheterna och ersattes av CFDI-metoden (Comprobante Fiscal Digital a través de Internet), där signeringen delegeras till tredjepartsleverantören (PAC). Den månatliga rapporten har tagits bort och ett förfrågningsalternativ gör det möjligt för användare att fråga om historiska transaktioner. |
| Ersatt av en annan funktion? | Nej                                                                                                                                                                                                                                                                                                                                                                                                        |
| Påverkade moduler             | Kundfordringar, Projekt                                                                                                                                                                                                                                                                                                                                                                              |

### Realiserad och orealiserad moms för Mexiko
<a id="mexico-realized-and-unrealized-vat" class="xliff"></a>

Microsoft Dynamics AX 2012 hanterade orealiserad mervärdesskatt (VAT) genom att använda funktioner specifika för Mexiko för ”orealiserad moms”.

|                              |                                                                                                                     |
|------------------------------|---------------------------------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Dubblettfunktion                                                                                             |
| Ersatt av en annan funktion? | Ja, den här funktionen har ersatts av standardfunktioner för villkorlig moms som tillhandahålls av basen. |
| Påverkade moduler             | Moms                                                                                                                 |

### Microsoft Outlook-integrering
<a id="microsoft-outlook-integration" class="xliff"></a>

|                              |                                                                                |
|------------------------------|--------------------------------------------------------------------------------|
| Orsak till avskrivning       | Den här funktionen har ersatts av Microsoft Exchange Server-integrering. |
| Ersatt av en annan funktion? | Ja                                                                            |
| Påverkade moduler             | Försäljning och marknadsföring                                                            |

### Löneinformation i Personal
<a id="payroll-information-in-human-resources" class="xliff"></a>

Löneinformation i HR

|                              |                                                                                                                                                                                                                                                                                                                              |
|------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Den här funktionen har ersatts av huvudsidorna Lön och Personal.                                                                                                                                                                                                                                              |
| Ersatt av en annan funktion? | **Förmåner**, **Inkomster** och andra relaterade sidor, som tidigare fanns i USA-lönelistan, har konfigurerats om och är nu en del av den grundläggande konfigurationen Personal för att ge stöd för extern lönebearbetning. Den här funktionen kan nås med hjälp av konfigurationsnyckeln **Personal 1** &gt; **Lönelista**. |
| Påverkade moduler             | Personal, Lön                                                                                                                                                                                                                                                                                                     |

### Privat blockering av inventerings- och lagerhanteringsjournaler
<a id="private-blocking-of-inventory-and-warehouse-management-journals" class="xliff"></a>

Inventerings- och lagerställejournalerna stöder inte längre möjligheten att markera en journal som privat för en vald användare. Endast processen för att blockera journaler som privata för användargrupper och blockering under redigering stöds.

|                              |                                        |
|------------------------------|----------------------------------------|
| Orsak till avskrivning       | Ingen användning av funktionen påträffades. |
| Ersatt av en annan funktion? | Nej                                     |
| Påverkade moduler             | Lagerhantering                   |

### Product Builder
<a id="product-builder" class="xliff"></a>

Product Builder användes för att dynamiskt konfigurera artiklar från en försäljningsorder, inköpsorder, tillverkningsorder, försäljningsoffert, projektoffert eller artikelbehov. Baserat på en produktmodell, som hade modellvariabler, kunde användaren välja värden för att uppfylla kundkraven och för att få en unik produktvariant som hade en strukturlista och ett flöde.

|                              |                                                                                                                                                                                                         |
|------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Product Builder exponerade X++-kod till slutanvändare och stöds inte i den aktuella versionen av Dynamics AX. Den har tagits bort för att undvika dubbelt underhållsarbete med överlappande, ansenliga kodbaser. |
| Ersatt av en annan funktion? | Produktkonfiguration                                                                                                                                                                                   |
| Påverkade moduler             | Produktinformationshantering, Försäljning och marknadsföring                                                                                                                                                     |

### Byt namn på produktdimension
<a id="rename-product-dimension" class="xliff"></a>

Den här funktionen låter dig ändra namnet på en av de tre standardproduktdimensionerna (storlek, färg eller format) till ett namn som passar bättre för dina affärsbehov. Namnändringen inkluderade alla etiketter där produktdimensionsnamnet användes.

|                              |                                                                               |
|------------------------------|-------------------------------------------------------------------------------|
| Orsak till avskrivning       | Den aktuella versionen av Dynamics AX stöder inte etikettändringar under körning. |
| Ersatt av en annan funktion? | Ingen                                                                            |
| Påverkade moduler             | Produktinformationshantering                                                |

### Retail Server-anslutning använder HTTP
<a id="retail-server-connectivity-using-http" class="xliff"></a>

I Dynamics AX 2012 R3 kan Retail Server med hjälp av HTTP-kommunikation (icke-säker). Detta var förutom standardkommunikationen med HTTPS.

|                              |                                                                               |
|------------------------------|-------------------------------------------------------------------------------|
| Orsak till avskrivning       | På grund av nya säkerhetskrav stöds endast säker kommunikation med TLS 1.2 (eller högre om tillgängligt) nu. Installationsprogrammet för självbetjäning konfigurerar automatiskt datorn för den här kommunikationen. |
| Ersatt av en annan funktion? | Nr. Endast standardkommunikation för HTTPS stöds nu.                                                                           |
| Påverkade moduler             | Butiksserver                                                |

### Rollcentersidor
<a id="role-center-pages" class="xliff"></a>

|                              |                                                                                                                                                                          |
|------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Rollcentersidor skapades på den inaktuella Enterprise Portal-plattformen, som har ersatts av den nya webbklientplattformen i den aktuella versionen av Dynamics AX. |
| Ersatt av en annan funktion? | Det nya arbetsyteformulärmönstret förser användare med en processcentrerad design som tillhandahåller enkel åtkomst till vanliga uppgifter i den processen.                       |
| Påverkade moduler             | Alla                                                                                                                                                                      |

### Skattemyndigheter
<a id="sales-tax-jurisdictions" class="xliff"></a>

|                              |                                              |
|------------------------------|----------------------------------------------|
| Orsak till avskrivning       | Låg kundanvändning och en begränsad uppsättning funktioner |
| Ersatt av en annan funktion? | Nej                                           |
| Påverkade moduler             | USA-moms                                 |

### Transportföretagsgränssnitt
<a id="shipping-carrier-interface" class="xliff"></a>

|                              |                                                                                                                                                 |
|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Dubblettfunktion                                                                                                                         |
| Ersatt av en annan funktion? | Ja, den här funktionen har delvis ersatts av Transporthantering, men har ännu inte ersatts av grundläggande Lagerstyrning (Lagerstyrningssystem I). |
| Påverkade moduler             | Försäljning och marknadsföring, Lagerhantering                                                                                                       |

### Platstjänster
<a id="sites-services" class="xliff"></a>

Med hjälp av webbplatstjänster kan du utöka dina affärsprocesser till Internet utan IT-support.

|                              |                                                                                                                                          |
|------------------------------|------------------------------------------------------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Microsoft Azure-infrastrukturen, som användes av Dynamics AX, har nya kapaciteter som kan användas i stället (exempelvis, Azure-webbplatser). |
| Ersatt av en annan funktion? | Nej                                                                                                                                       |
| Påverkade moduler             | Personalrekrytering, Fallhantering, Anbudsförfrågningar, Leverantörsregistrering                                                                  |

### SSAS-tjänster för efterfrågeprognosticering
<a id="ssas-demand-forecasting-strategy" class="xliff"></a>

|                              |                                                                              |
|------------------------------|------------------------------------------------------------------------------|
| Orsak till avskrivning       | Utformningen av den här funktionen stöds inte i den nya arkitekturen i molnet. |
| Ersatt av en annan funktion? | Efterfrågeprognosticeringsstrategi för Azure-maskininlärning                           |
| Påverkade moduler             | Planering                                                                     |

### Reserekvisitioner
<a id="travel-requisitions" class="xliff"></a>

|                              |                                                                 |
|------------------------------|-----------------------------------------------------------------|
| Orsak till avskrivning       | Låg användning och de flesta funktioner fanns i Enterprise Portal. |
| Ersatt av en annan funktion? | Nej                                                              |
| Påverkade moduler             | Utläggshantering                                              |

### Leverantörsfakturapool utan bokföringsdetaljer
<a id="vendor-invoice-pool-excluding-posting-details" class="xliff"></a>

|                              |                                                                                                         |
|------------------------------|---------------------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Låg användning. Den här funktionen har ersatts av fakturajournalen som har en arbetsflödesfunktion. |
| Ersatt av en annan funktion? | Arbetsflödesfunktionerna i Fakturajournal.                                                           |
| Påverkade moduler             | Leverantörsreskontra                                                                                        |

### Virtuella företagskonton
<a id="virtual-company-accounts" class="xliff"></a>

Funktionen för virtuella företag stöds inte längre i Dynamics AX. Funktionen för virtuella företag gjorde att användarna kunde ställa in register som kunde delas av en uppsättning företag. Du kan hitta en beskrivning av funktionen här: [Företagskonton och konton för virtuella företag](https://msdn.microsoft.com/en-us/library/aa834382(v=ax.10).aspx). Funktionen fungerar genom att gruppera register i samlingar som tilldelas till virtuella företag, som är grupper med befintliga ”verkliga” företag. Frågor skapas så att alla företag i det virtuella företaget kan komma åt data i registren för de associerade registersamlingarna.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td>Orsak till avskrivning</td>
<td><ul>
<li>Virtuella företag måste ställas in innan data lagras i registren. Det är mycket svårt att ställa in virtuella företag efter en befintlig implementering i efterhand.</li>
<li>Eftersom det har gjorts så mycket datanormalisering i den aktuella versionen av Microsoft Dynamics AX har det blivit svårt att veta vad som ska lägga till i registersamlingarna. Till exempel är det svårt att veta vilka register som ska delas. Alla register som refereras från register som ingår i ett virtuellt företag måste också läggas till. Registernormalisering har inneburit att även enkla huvuddata som är fördelade över flera register måste vara en del av det virtuella företaget. Alla misstag som begås här kommer att leda till funktionsproblem.</li>
<li>När ett register ingår i ett virtuellt företag förlorar det information om informationens ursprung, och endast det virtuella företaget registreras.</li>
</ul></td>
</tr>
<tr class="even">
<td>Ersatt av en annan funktion?</td>
<td>Globala register kan användas för att göra register tillgängliga från alla företag. För närvarande finns det ingen ersättning.</td>
</tr>
<tr class="odd">
<td>Påverkade moduler</td>
<td>Inte tillämpligt</td>
</tr>
</tbody>
</table>

### Lagerstyrning II
<a id="warehouse-management-ii" class="xliff"></a>

|                              |                                                                                                                                                                                                                                                                                                             |
|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Lagerstyrningssystem II-lösningar (WMS II) som var tillgängliga i modulen **Lagerhantering** duplicerar funktionerna som finns i modulen **Lagerstyrning** som släpptes i Microsoft Dynamics AX 2012 R3.                                                                         |
| Ersatt av en annan funktion? | Modulen **Lagerstyrning** som släpptes i AX 2012 R3, Microsoft Dynamics AX 2012 R3 CU8, och Microsoft Dynamics AX 2012 R3 CU9 ersätter funktionerna i Lagerstyrning II. Den nya modulen har mer avancerade funktioner och mer flexibla lagerstyrningsprocesser än de som erbjöds av funktionerna i Lagerstyrning II. |
| Påverkade moduler             | Lagerhantering, försäljning och marknadsföring, anskaffning och källa                                                                                                                                                                                                                                         |

### Påminnelser till arbetare i Personal
<a id="worker-reminders-in-human-resources" class="xliff"></a>

Löneinformation i HR

|                              |                 |
|------------------------------|-----------------|
| Orsak till avskrivning       | Låg användning       |
| Ersatt av en annan funktion? | Nej              |
| Påverkade moduler             | Personal |

### Arbetsplanerare
<a id="workplanner" class="xliff"></a>

|                              |                                                                                                                                                                      |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Låg användning                                                                                                                                                            |
| Ersatt av en annan funktion? | Nej, men sidan **Profilrelation**, som öppnas från sidan **Profilgrupper** stöder samma affärsscenario som den inaktuella sidan **Arbetsplanerare**. |
| Påverkade moduler             | Tid och närvaro                                                                                                                                                  |

### X++-bokslut
<a id="x-financial-statements" class="xliff"></a>

|                              |                                                                                             |
|------------------------------|---------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Funktionen har ersatts med en annan funktion.                                    |
| Ersatt av en annan funktion? | Management Reporter (med etiketten **Ekonomisk rapportering** i den aktuella versionen av Dynamics AX) |
| Påverkade moduler             | Huvudbok                                                                              |


