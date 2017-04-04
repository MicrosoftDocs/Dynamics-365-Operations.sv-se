---
title: "Äldre funktioner"
description: "I det här avsnittet beskrivs funktioner som har tagits bort, eller har planerats för borttagning från Dynamics 365 for Operations. Det visar också funktioner som föråldrats i Dynamics AX 7.0-versioner."
author: sericks007
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, Developer, IT Pro
ms.search.scope: Operations, Platform
ms.custom: 21821
ms.assetid: 31019808-4cbf-47d7-b1ba-d791db4281ae
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 2
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: e9ba7239b9ff8b9b97c9dabc06fb2c68760d19d4
ms.lasthandoff: 03/31/2017


---

# <a name="deprecated-features"></a>Äldre funktioner

I det här avsnittet beskrivs funktioner som har tagits bort, eller har planerats för borttagning från Dynamics 365 for Operations. Det visar också funktioner som föråldrats i Dynamics AX 7.0-versioner.

<a name="features-that-have-been-deprecated-in-dynamics-365-for-operations-1611-with-platform-update-3"></a>Funktioner som har föråldrats i Dynamics 365 for Operations 1611 med plattformuppdatering 3
---------------------------------------------------------------------------------------------

### <a name="aeb-payment-formats-for-spain"></a>AEB-betalningformat för Spanien

Betalningsformaten för Consejo Superior Bancario används för att skicka remissafiler till banken för kundbetalningar och leverantörsbetalningar. Innehållet i dessa format bestäms av Asociación Española de Banca. Det omfattar Cuaderno 19, 32, 58, 34.

|                              |                                                                          |
|------------------------------|--------------------------------------------------------------------------|
| Orsak till avskrivning       | Betalningformaten används inte längre.                                  |
| Ersatt av en annan funktion? | Ja, ISO20022 kreditöverföring och betalningsformat för autogiro för Spanien |
| Påverkade moduler             | Leverantörsreskontra, Kundreskontra                                    |

### <a name="bank-payments-transfer-for-lithuania"></a>Bankbetalningar överför för Litauen

Bankbetalningsöverföringar skapas och skrivs ut genom att använda exportformatet för betalningsöverföring (LT) för Litauen. Den litauiska marknaden har börjat använda LITASEN, det enade elektroniska banksystemet år 2005.

|                              |                                                            |
|------------------------------|------------------------------------------------------------|
| Orsak till avskrivning       | Betalningformaten används inte längre.                    |
| Ersatt av en annan funktion? | Ja, ISO20022 betalningsformat för kreditöverföring för Litauen |
| Påverkade moduler             | Leverantörsreskontra                                           |

### <a name="bbs-direkte-remittering-payment-formats-for-norway"></a>BBS Direkte Remittering betalningsformat för Norge

BBS Direkte Remittering betalningsformat inkluderar exportinkasso för kundbetalning (autogiro) och import av returmeddelande.

|                              |                                                                                                                                                                |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Betalningformaten används inte längre.                                                                                                                        |
| Ersatt av en annan funktion? | Kundbetalningsformatet för AvtaleGiro för Norge kan användas för att generera autogiro-meddelanden. Import av returmeddelande kommer att implementeras i kommande versioner. |
| Påverkade moduler             | Leverantörsreskontra, Kundreskontra                                                                                                                          |

### <a name="chart-of-accounts-tool-for-spain"></a>Verktyg för kontoplan från Spanien

Det här verktyget används när en kontoplan i Spanien kräver stora ändringar. Användarna kan importera en ny kontoplan i Microsoft Excel eller textformat och kan också importera bokslut.

|                              |                |
|------------------------------|----------------|
| Orsak till avskrivning       | Begränsad användning  |
| Ersatt av en annan funktion? | Nr             |
| Påverkade moduler             | Huvudbok |

### <a name="dom80-payment-format-for-belgium"></a>Dom80 betalningsformat för Belgien

Äldre belgiskt betalningsformat för betalningsinsamling (autogiro).

|                              |                                                        |
|------------------------------|--------------------------------------------------------|
| Orsak till avskrivning       | Betalningformatet används inte längre.                  |
| Ersatt av en annan funktion? | Ja, ISO 20022 betalningsformat för autogiro för Belgien. |
| Påverkade moduler             | Kundreskontra                                    |

### <a name="dtaezag-payment-formats-for-switzerland"></a>DTA/EZAG-betalningformat för Schweiz

DTA-/EZAG-format integreras i ESR-systemet, eftersom de kan ha ett referensnummer. Eftersom referensnumret inte är obligatoriskt kan dessa format användas för att bearbeta alla leverantörsbetalningar. Dessa format används av företag som har ett bankkonto på en annan plats än “Postfinance.”

|                              |                                                              |
|------------------------------|--------------------------------------------------------------|
| Orsak till avskrivning       | Betalningformaten används inte längre.                      |
| Ersatt av en annan funktion? | Ja, ISO20022 betalningsformat för kreditöverföring för Schweiz. |
| Påverkade moduler             | Leverantörsreskontra                                             |

### <a name="edifact-dirdeb-payment-format-for-austria"></a>EDIFACT - DIRDEB-betalningformat för Österrike

EDIFACT-DIRDEB-betalningsformat för betalningsinsamling (autogiro).

|                              |                                                        |
|------------------------------|--------------------------------------------------------|
| Orsak till avskrivning       | Betalningformatet används inte längre.                  |
| Ersatt av en annan funktion? | Ja, ISO 20022 betalningsformat för autogiro för Österrike. |
| Påverkade moduler             | Kundreskontra                                    |

### <a name="edivat-for-belgium"></a>EDIVAT för Belgien

EDIVAT är en inaktuell belgisk standard för elektronisk deklaration säker via e-post. Microsoft Dynamics AX 2012 har kvar den skrivskyddade lösningen för att tillåta åtkomst till de historiska data.

|                              |                                      |
|------------------------------|--------------------------------------|
| Orsak till avskrivning       | Funktionen används inte längre. |
| Ersatt av en annan funktion? | Nr                                   |
| Påverkade moduler             | Huvudbok                       |

### <a name="egiro-edifact-cremul-payment-import-format-for-norway"></a>eGiro EDIFACT CREMUL-betalningsformat för Norge

eGiro baseras på den internationella UN EDIFACT CREMUL-standarden (Multiple Credit Advice Message) som används för automatisk bokföring av kundbetalningar. I Microsoft Dynamics AX tillämpas eGiro som ett importformat för kundbetalning.

|                              |                                                                                           |
|------------------------------|-------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Betalningformatet används inte längre.                                                     |
| Ersatt av en annan funktion? | Nr. Formatet ersätts med ISO 20022 uttryck Importformat i framtida versioner. |
| Påverkade moduler             | Kundreskontra                                                                       |

### <a name="external-inventory-for-poland"></a>Externt lager för Polen

Bevis av varor som tas från en leverantör för försäljning utan inköp. De varor som hanteras i externt lager, som inte påverkar standardlager, kan säljas och sedan köpas in automatiskt. Den här processen skapar verkliga lagerrörelser.

|                              |                                                 |
|------------------------------|-------------------------------------------------|
| Orsak till avskrivning       | Ersatt av en annan funktion                     |
| Ersatt av en annan funktion? | Ja, försändelsefunktionen för den inkommande kärnan |
| Påverkade moduler             | Leverantörsreskontra, lagerhantering          |

### <a name="financial-reports-generator-for-eastern-europe"></a>Ekonomisk rapportgenerator för Östra Europa

Ett verktyg för att ställa in datainsamling för redovisning och momsrapporter behövs och exportera data till XLS och DOC-rapportmallar

|                              |                                                                                          |
|------------------------------|------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Begränsad användning                                                                            |
| Ersatt av en annan funktion? | Nr. Verktyget ersätts med elektronisk rapportering i framtida utgåvor konfigurationer. |
| Påverkade moduler             | Redovisning                                                                           |

### <a name="import-of-customer-payment-transactions-for-finland"></a>Import av kundbetalningstransaktioner för Finland

Du kan välja ett importformat för finska betalningar som importerar kundbetalningstransaktioner från en extern fil som tillhandahålls av banken.

|                              |                                                                                           |
|------------------------------|-------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Betalningformatet används inte längre.                                                     |
| Ersatt av en annan funktion? | Nr. Formatet ersätts med ISO 20022 uttryck Importformat i framtida versioner. |
| Påverkade moduler             | Kundreskontra                                                                       |

### <a name="import-of-payment-transactions-into-a-general-ledger-journal-for-finland"></a>Import av betalningstransaktioner till en redovisningsjournal för Finland

Ett format som är specifik för Finland används för att importera redovisningstransaktioner till redovisningen.

|                              |                                                                                           |
|------------------------------|-------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Betalningformatet används inte längre.                                                     |
| Ersatt av en annan funktion? | Nr. Formatet ersätts med ISO 20022 uttryck Importformat i framtida versioner. |
| Påverkade moduler             | Kundreskontra                                                                       |

### <a name="integration-with-isabel-synchronized-cis-for-belgium"></a>Integration med Isabel-synkroniserad (CIS) för Belgien

Isabel är ramverket för elektronisk bankverksamhet i Europa och en de facto-standard i Belgien.

|                              |                                                                                                                      |
|------------------------------|----------------------------------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Integration med Isabel-klienten har annullerats.                                                                |
| Ersatt av en annan funktion? | Nr. Betalningsformat som inte längre används byts ISO20022 kredit överföringen betalningsformat för Belgien. |
| Påverkade moduler             | Leverantörsreskontra                                                                                                     |

### <a name="modifications-in-the-chart-of-accounts-and-accounting-rules-for-spain"></a>Ändringar i kontoplanen och redovisningsreglerna för Spanien

Den här funktionen används för ändringar i kontoplanen och redovisningsreglerna i Spanien. Den mappar konton för att transformera den gamla kontoplanen till den nya kontoplanen och jämföra det föregående räkenskapsåret med det nya räkenskapsåret, även om de bokförts till ett annat kontonummer.

|                              |                |
|------------------------------|----------------|
| Orsak till avskrivning       | Begränsad användning  |
| Ersatt av en annan funktion? | Nr             |
| Påverkade moduler             | Huvudbok |

### <a name="pagamento-fornittori-vendor-payment-format"></a>Pagamento Fornittori leverantörsbetalningsformat

Äldre italienskt betalningsformat för kreditöverföringar.

|                              |                                                        |
|------------------------------|--------------------------------------------------------|
| Orsak till avskrivning       | Betalningformatet används inte längre.                  |
| Ersatt av en annan funktion? | Ja, ISO20022 betalningsformat för kreditöverföring för Italien |
| Påverkade moduler             | Leverantörsreskontra                                       |

### <a name="payment-export-formats-for-estonia"></a>Exportformat för betalning för Estland

Formaten Telehansa och Teleservice används för bankbetalningsexport.

|                              |                                                          |
|------------------------------|----------------------------------------------------------|
| Orsak till avskrivning       | Betalningformaten används inte längre.                  |
| Ersatt av en annan funktion? | Ja, ISO20022 betalningsformat för kreditöverföring för Estland |
| Påverkade moduler             | Leverantörsreskontra                                         |

### <a name="payment-file-archive-for-norway"></a>Betalningsfilarkiv för Norge

När betalningsfiler genereras arkiverar filarkivet automatiskt alla filer som skapas, även filer som tidigare skrevs eller lästes.

|                              |                                                                    |
|------------------------------|--------------------------------------------------------------------|
| Orsak till avskrivning       | Ersatt av en annan funktion                                        |
| Ersatt av en annan funktion? | Ja, arkiverade elektroniska rapporteringsjobb                            |
| Påverkade moduler             | Kundreskontra, leverantörsreskontra, organisationadministration |

### <a name="payment-import-formats-for-estonia"></a>Importformat för betalning för Estland

Formaten Telehansa och TeleTeenu används för bankbetalningsimport.

|                              |                                                                                            |
|------------------------------|--------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Betalningformaten används inte längre.                                                    |
| Ersatt av en annan funktion? | Nr. Formaten ersätts med ISO 20022 uttryck Importformat i framtida versioner. |
| Påverkade moduler             | Kundreskontra                                                                        |

### <a name="performance-management-goal-workflow"></a>Arbetsflöde för prestationshanteringmål

Prestationshantering inkluderar målhantering och integration med prestationsgranskning.

|                              |                                                                                                                          |
|------------------------------|--------------------------------------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Prestationshantering formades om, och antalet målsidor förminskades för att förenkla processen.                 |
| Ersatt av en annan funktion? | Nr. Mål kan är synliga för projektledare Manager Self Service-portalen och ändras och visas av projektledaren. |
| Påverkade moduler             | Administration av humankapital                                                                                                 |

### <a name="postgirot-and-postgirot-utland-payment-formats-for-sweden"></a>Postgirot och Postgirot Utland betalningsformat för Sverige

Postgirot och Postgirot Utland betalningsformat för Sverige.

|                              |                                                         |
|------------------------------|---------------------------------------------------------|
| Orsak till avskrivning       | Betalningformaten används inte längre.                 |
| Ersatt av en annan funktion? | Ja, ISO20022 betalningsformat för kreditöverföring för Sverige |
| Påverkade moduler             | Leverantörsreskontra                                        |

### <a name="radio-frequency-identifier"></a>Radiofrekvens-ID

Radiofrekvensidentifiering (RFID) är en teknik för insamling av uppgifter som använder elektroniska taggar för att lagra identifieringsdata och en läsare nr rad av utan krav att samla in data för identifiering.

|                              |                                               |
|------------------------------|-----------------------------------------------|
| Orsak till avskrivning       | Låg Kundförbrukning och en begränsad funktion. |
| Ersatt av en annan funktion? | Ingen                                            |
| Påverkade moduler             | Lagerhantering                          |

### <a name="report-about-state-invoices-numbering-for-latvia"></a>Rapport om numrering av statliga fakturor för Lettland

Lettisk lagstiftning innehåller särskilda regler om hur försäljningsfakturor ska numreras. Det gör att du kan tilldela specifika försäljningsfakturor, baserat på användare eller användargrupp. Du kan sedan skapa en rapport eller en XML-fil. Du kan även skriva ut en rapport om fakturanummer som används.

|                              |                                                                                                                          |
|------------------------------|--------------------------------------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Numrering av statliga fakturor måste inte längre underhållas. Rapporten om använda fakturanummer är inte längre obligatorisk. |
| Ersatt av en annan funktion? | Nr                                                                                                                       |
| Påverkade moduler             | Kundreskontra                                                                                                      |

### <a name="set-up-the-names-of-the-manager-and-general-accountant-of-a-company-for-lithuania"></a>Ställ in namnen för chefen och den allmänna revisorn i ett företag för Litauen

Namnen på chefen och den allmänna revisorn i ett företag kan anges i företagsinformationen och användas vid olika lokala rapportutskrifter.

|                              |                                                                 |
|------------------------------|-----------------------------------------------------------------|
| Orsak till avskrivning       | Ersatt av en annan funktion                                     |
| Ersatt av en annan funktion? | Ja, inställningen av för tjänstemän kan användas för samma syfte.   |
| Påverkade moduler             | Leverantörsreskontra, Kundreskontra och Kassa- och bankhantering |

### <a name="telepay-payment-formats-for-norway"></a>Telepay betalningsformat för Norge

Telepay betalningsformat inkluderar leverantörsbetalningsexporten (kreditöverföring) och inkasso för kundbetalning (autogiro).

|                              |                                                                                                |
|------------------------------|------------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Betalningformaten används inte längre.                                                        |
| Ersatt av en annan funktion? | Ja, ISO20022 betalningsformat för kreditöverföring och AvtaleGiro kundbetalningsformat för Norge |
| Påverkade moduler             | Leverantörsreskontra, Kundreskontra                                                          |

### <a name="vendor-payment-export-formats-for-finland"></a>Exportformat för leverantörsbetalning för Finland

Två format för att exportera betalningar är tillgängliga för Finland. LM02 (FI) används för lokala betalningar och LUM2 (FI) används för utländska betalningar.

|                              |                                                          |
|------------------------------|----------------------------------------------------------|
| Orsak till avskrivning       | Betalningformaten används inte längre.                  |
| Ersatt av en annan funktion? | Ja, ISO20022 betalningsformat för kreditöverföring för Finland |
| Påverkade moduler             | Leverantörsreskontra                                         |

### <a name="workflow-for-creating-goals"></a>Arbetsflöde för att skapa mål

Ett arbetsflöde för hantering av genereringen av medarbetare är en av flera arbetsflöden som är tillgängliga för att hjälpa till att koordinera prestandahanteringsprocessen.

|                              |                                                                                                                                                                                                                                                                                                                                        |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Prestandahantering har helt formats om i Microsoft Dynamics 365 for Operations.                                                                                                                                                                                                                                        |
| Ersatt av en annan funktion? | Den omformade prestandahanteringsfunktionen innehåller mer kontroll över innehållet av mål, måtten som används för att spåra framsteg och bilaga med förklarande dokumentation. Mål kan lagras som mallar och sedan återanvändas. Den här funktionen kan hjälpa dig att snabbare ställa in ytterligare mål för medarbetarna. |
| Påverkade moduler             | Administration av humankapital                                                                                                                                                                                                                                                                                                               |

## <a name="features-deprecated-in-dynamics-ax-70-releases"></a>Funktioner som är föråldrade i Dynamics AX 7.0-versioner
### <a name="ability-to-cancel-changes-to-a-vendor-invoice"></a>Möjligheten att avbryta ändringar i en leverantörsfaktura

|                              |                         |
|------------------------------|-------------------------|
| Orsak till avskrivning       | Prestandaförbättring |
| Ersatt av en annan funktion? | Nej                      |
| Påverkade moduler             | Leverantörsreskontra        |

### <a name="aif-axd-and-axbc-integrations"></a>AIF-, AxD- och AxBC-integrationer

I AIF (Application Integration Framework) kan data utbytas med externa system genom affärslogik som exponeras som tjänster. Microsoft Dynamics AX omfattar tjänster som baseras på dokument och .NET Business Connector (AxBC). Ett dokument skapas genom att använda XML. XML inkluderar rubrikinformation som läggs till för att skapa ett *meddelande* som kan överföras till eller från Microsoft Dynamics AX. Exempel på dokument innehåller försäljningsorder och inköpsorder. Dock kan nästan alla enheter, till exempel en kund, representeras av ett dokument. Tjänster som är baserade på dokument används den **Axd &lt;*dokument*&gt;** klasser.

|                              |                                                                                                                                                                                                          |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Arkitekturen för AIF och AxDs kunde inte skalas till en molntjänst. Det fanns prestandaproblem relaterade till massimport.                                                                               |
| Ersatt av en annan funktion? | I den aktuella versionen av Dynamics AX har den här funktionen ersatts av ramverket för dataimport/dataexport som stöder återkommande massimport/massexport. För AxBC rekommenderar vi att du använder faktiska tabeller. |
| Påverkade moduler             | AxDs, AxBCs och AIF                                                                                                                                                                                     |

### <a name="boms-without-bom-versions"></a>Strukturlistor utan strukturlisteversioner

När konfigurationsnyckeln för **strukturlisteversioner** inaktiverades doldes strukturlisteversioner i alla formulär och systemet framtvingade en 1:1-relation mellan frisläppta produkter och strukturlistor. I den aktuella versionen av Dynamics AX kan konfigurationsnyckeln för **strukturlisteversioner** inte inaktiveras.

|                              |                                                                                         |
|------------------------------|-----------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Användningen av en konfigurationsnyckel för att kontrollera strukturlisteversioner kan inte skalas till en molnmiljö. |
| Ersatt av en annan funktion? | Nej                                                                                      |
| Påverkade moduler             | Produktinformationshantering, Lagerhantering                                    |

### <a name="brazilian-bordero"></a>Brasilian Bordero

Specifik betalningsmetod för brasilianska företag

|                              |                                                                                                       |
|------------------------------|-------------------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Stöd för den brasilianska Bordero-betalningsmetoden har annullerats från brasiliansk lokalisering |
| Ersatt av en annan funktion? | Nr                                                                                                    |
| Påverkade moduler             | Leverantörsreskontra                                                                                      |

### <a name="brazilian-sintegra-statement"></a>Brazilian Sintegra-utdrag

Federala skatteutdrag för ICMS-moms

|                              |                                                                                                                       |
|------------------------------|-----------------------------------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Detta utdrag används inte längre i vissa brasilianska stater.                                                     |
| Ersatt av en annan funktion? | Nr. Användare kan använda allmänna elektroniska Rapporteringsverktyg konfigurera utdraget om det krävs under vissa förhållanden. |
| Påverkade moduler             | Skatteböcker                                                                                                          |

### <a name="brazilian-scan-contingency-mode-for-nf-e"></a>Brasiliansk SCAN eventualitetläge för NF-e

(SCAN) eventualitetmiljön används för att generera, exportera och importera status för Nota Fiscal eletrônica (NF-e) när miljön för Secretaria da Fazenda (SEFAZ) inte är tillgänglig.

|                              |                                                                             |
|------------------------------|-----------------------------------------------------------------------------|
| Orsak till avskrivning       | Den här eventualitetsmetoden används inte längre i alla brasilianska stater |
| Ersatt av en annan funktion? | Nr                                                                          |
| Påverkade moduler             | Kundreskontra                                                         |

### <a name="business-analyzer"></a>Business Analyzer

Det här mobila programmet låter användare granska viktiga affärsmått.

|                              |                                                                                                                                                               |
|------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Funktionen har ersatts med en annan funktion.                                                                                                      |
| Ersatt av en annan funktion? | Innehållspaketet för övervakning av ekonomiska resultat för Microsoft PowerBI kommer att inkludera samma ekonomiska mätvärden som tidigare var tillgängliga i Business Analyzer. |
| Påverkade moduler             | Huvudbok                                                                                                                                                |

### <a name="business-statistics"></a>Affärsstatistik

Konfigurationen av frågor om affärsstatistik som kan hjälpa dig att analysera organisationens resultat

|                              |                                                                                              |
|------------------------------|----------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Gammal metod för BI (Business Intelligence), låg kundanvändning och en begränsad funktionsuppsättning |
| Ersatt av en annan funktion? | Nya BI-lösningar för den aktuella versionen av Dynamics AX                                      |
| Påverkade moduler             | Anskaffning och sourcing, Leverantörsreskontra, Försäljning och marknadsföring, Kundreskontra         |

### <a name="change-document-date-function-in-invoice-approval-journal"></a>Funktionen Ändra dokumentets datum i Fakturagodkännandejournal

|                              |                                                                         |
|------------------------------|-------------------------------------------------------------------------|
| Orsak till avskrivning       | Låg användning                                                               |
| Ersatt av en annan funktion? | Ja. Dokumentdatumet för den bokförda leverantörstransaktionen kan ändras. |
| Påverkade moduler             | Leverantörsreskontra                                                        |

### <a name="clieop03-payment-format-for-the-netherlands"></a>Betalningsformatet ClieOp03 för Nederländerna

|                              |                                                                                                            |
|------------------------------|------------------------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Formatet är inte längre tillämpligt i Nederländerna eftersom det har ersatts av SEPA-funktionen. |
| Ersatt av en annan funktion? | SEPA-betalningsexport                                                                                       |
| Påverkade moduler             | Alla                                                                                                        |

### <a name="compliance-center"></a>Regelefterlevnadscenter

Regelefterlevnadscentret var en Enterprise Portal-webbplats för att hantera dokumentationskraven för efterlevnadsinsatser som är relaterade till Sarbanes-Oxley-lagen.

|                              |                                                                                                                        |
|------------------------------|------------------------------------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Brist på kundanvändning. Microsoft SharePoint innehåller samma kapacitet som var tillgänglig i regelefterlevnadscentret. |
| Ersatt av en annan funktion? | Nej                                                                                                                     |
| Påverkade moduler             | Regelefterlevnad och interna kontroller                                                                                       |

### <a name="connector-for-microsoft-dynamics"></a>Connector för Microsoft Dynamics

Verktyget användes för att integrerar viktiga data från Microsoft Dynamics CRM till Microsoft Dynamics ERP-tillämpningar.

|                              |                                                          |
|------------------------------|----------------------------------------------------------|
| Orsak till avskrivning       | Funktionen har ersatts med en annan funktion. |
| Ersatt av en annan funktion? | Dynamics Integrator                                      |
| Påverkade moduler             | Connector för Microsoft Dynamics                         |

### <a name="container-unit-and-multi-dimension-on-hand"></a>Behållarenhet och flerdimensionell behållning

|                              |                                                                                                                                                                 |
|------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Dubblettfunktion                                                                                                                                         |
| Ersatt av en annan funktion? | Ja. Sedan AXET 2012 har den här funktionen ersatts av funktionsuppsättning av konsoliderade batchorder. Den här funktionsuppsättningen inkluderar den konsoliderade behållningsvyn. |
| Påverkade moduler             | Produktinformationshantering, Produktionskontroll, Lagerhantering, Försäljning och marknadsföring                                                                   |

### <a name="cue-group-metadata"></a>Stackikongruppmetadata

|                              |                                                                                                                                                                                                                               |
|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Stackikongrupper användes för att visa en eller flera stackikoner i faktaboxområdet. Upptaget var begränsat och det fanns även prestandaproblem eftersom en poständring i ett överordnat formulär orsakade en fråga per stackikon i stackikongruppen. |
| Ersatt av en annan funktion? | Nej                                                                                                                                                                                                                            |
| Påverkade moduler             | Alla                                                                                                                                                                                                                           |

### <a name="cue-metadata"></a>Stackikonmetadata

|                              |                                                                                                                                                                                                                                         |
|------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Stackikonmetadata begränsades till information om antal och summor.                                                                                                                                                                                   |
| Ersatt av en annan funktion? | Panelmetadata introducerades för att ge mer flexibilitet för modellering. Du kan till exempel modellera aktuella antal, navigering och KPI:er (Key Performance Indicator). Metadata för antal på panel är en direkt ersättning av stackikonmetadata. |
| Påverkade moduler             | Alla                                                                                                                                                                                                                                     |

### <a name="danish-check-format"></a>Danskt checkformat

|                              |                                                                                                                         |
|------------------------------|-------------------------------------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Stöd för den danska checkformatlayouten har tagits bort, och rapporten har tagits bort från lokalisering för danska. |
| Ersatt av en annan funktion? | Nej                                                                                                                      |
| Påverkade moduler             | Alla                                                                                                                     |

### <a name="data-partitions"></a>Datapartitioner

Datapartitioner tillhandahåller en logisk separering av data i Microsoft Dynamics AX-databasen.

|                              |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Datapartitioner introducerades i Microsoft Dynamics AX 2012 R2 för möjliggöra isolering av data. I ett vanligt scenario har ett företag ett dotterbolag och data från ett dotterbolag ska inte vara synliga för ett annat dotterföretag, även om båda dotterbolagen hanteras av samma IT-avdelning. Det behövdes dock extra skript och hantering av information i hela programmet för att skapa nya partitioner och förse dem med data och att säkerhetskopiera partitionsdata. I molnet, där vi har tillgång till plattform som en tjänst (PaaS) databas-tjänster (Microsoft Azure SQL-databasen), är det mycket effektivare att använda en databas som isolerade behållare än att utföra isolering i programmet. Oavsett om datapartition är nödvändig för dotterbolag, för flera innehavare eller för skalning tror vi att scenarier kan hanteras bättre via flera olika databaser eller flera Dynamics AX-instanser. |
| Ersatt av en annan funktion? | Datapartitioner ersätts med stöd för flera databaser eller Dynamics AX-instanser i en framtida version.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| Påverkade moduler             | Alla                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |

### <a name="delimitation"></a>Avgränsning

|                              |                                        |
|------------------------------|----------------------------------------|
| Orsak till avskrivning       | Ingen användning av funktionen påträffades. |
| Ersatt av en annan funktion? | Nej                                     |
| Påverkade moduler             | Tid och närvaro                    |

### <a name="desktop-client"></a>Skrivbordsklient

|                              |                                                                                                                                        |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Dynamics AX-klientupplevelsen har formats om för att förbättra användbarheten över flera plattformar och enheter.                      |
| Ersatt av en annan funktion? | Den nya webbklienten baseras på skrivbordsformulärmetadata och programmeringsmodellen som har ändrats för att ge en heltäckande webbplattform. |
| Påverkade moduler             | Alla                                                                                                                                    |

### <a name="dutch-swift-mt940"></a>Holländsk SWIFT MT940

|                              |                                                                                                                                                                                                                                       |
|------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Den generiska funktionen används nu i stället för den lokaliserade funktionen.                                                                                                                                                                 |
| Ersatt av en annan funktion? | Ja, den här funktionen har ersatts av funktionen för avancerad bankavstämning. Dessutom planeras implementering av kontoutdragsimporten för camt.053 ISO20022 för den allmänna journalen i nästa uppdatering av Dynamics AX. |
| Påverkade moduler             | Alla                                                                                                                                                                                                                                   |

### <a name="ebilanz-xbrl-for-germany"></a>eBilanz (XBRL för Tyskland)

Den här funktionen ger eXtensible Business Reporting Language (XBRL)-utdata som är specifikt utformade för tysk eBilanz-taxonomi.

|                              |                                                                                                                                                                        |
|------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Brist på kundanvändning                                                                                                                                                 |
| Ersatt av en annan funktion? | Den här funktionen har inte ersatts av en annan funktion, men flera specialiserade XBRL-paket som innehåller omfattande XBRL-funktioner är tillgängliga för den tyska marknaden. |
| Påverkade moduler             | Management Reporter                                                                                                                                                    |

### <a name="enterprise-portal-client"></a>Enterprise Portal-klient

|                              |                                                                                                                                        |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | En enskild klientplattform har tillhandahållits.                                                                                            |
| Ersatt av en annan funktion? | Den nya webbklienten baseras på skrivbordsformulärmetadata och programmeringsmodellen som har ändrats för att ge en heltäckande webbplattform. |
| Påverkade moduler             | Alla                                                                                                                                    |

### <a name="environmental-sustainability"></a>Miljöhållbarhet

|                              |                                                    |
|------------------------------|----------------------------------------------------|
| Orsak till avskrivning       | Låg kundanvändning och en begränsad uppsättning funktioner.       |
| Ersatt av en annan funktion? | Nej                                                 |
| Påverkade moduler             | Efterlevnad och interna kontroller, Leverantörsreskontra |

### <a name="form-activex-and-managed-host-controls"></a>ActiveX och de hanterade värdkontroller för formulär

|                              |                                                                                                                                                                                               |
|------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | ActiveX och hanterade värdkontroller baseras på den inaktuella skrivbordsklienten.                                                                                                             |
| Ersatt av en annan funktion? | Det utökningsbara kontrollramverket stöder utveckling av nya kontroller som baseras på HTML, CSS och JavaScript, och är en klass 1-kontroll i Microsoft Visual Studio Tooling-miljön. |
| Påverkade moduler             | Alla                                                                                                                                                                                           |

### <a name="generate-prenotes-by-using-a-batch"></a>Generera förauktoriseringar genom att använda en batch

Genereringen av förauktoriseringar kan inte utföras med hjälp av en batch men kan fortfarande utföras av en användare.

|                              |                                                                                                        |
|------------------------------|--------------------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Inget formulär finns för att bevara och visa den resulterande filen med förauktoriseringar när den genererats med hjälp av en batch. |
| Ersatt av en annan funktion? | Förauktoriseringar kan fortfarande genereras och användaren har kontroll över var filen sparas.   |
| Påverkade moduler             | Leverantörsreskontra, Kundreskontra och Kassa- och bankhantering                                        |

### <a name="german-dtaus-payment-export-and-account-statement-import-totals-and-transactions"></a>Tysk DTAUS-betalningsexport och -kontoutdragsimport (summor och transaktioner)

|                              |                                                                                                                                                                                                                                                                                                |
|------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Formatet är inte längre tillämpligt i Tyskland eftersom det har ersatts av SEPA-funktionen (Single Euro Payments Area).                                                                                                                                                                 |
| Ersatt av en annan funktion? | Ja, funktionen har ersatts av SEPA-betalningsexport och avancerad bankavstämning för import av kontoutdrag. Dessutom planeras implementering av kontoutdragsimporten för camt.053 ISO20022 för den allmänna journalen i nästa uppdatering av Dynamics AX. |
| Påverkade moduler             | Alla                                                                                                                                                                                                                                                                                            |

### <a name="german-dtazv-payment-format"></a>Tyskt DTAZV-betalningsformat

|                              |                                                                                                    |
|------------------------------|----------------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Formatet är inte längre tillämpligt i Tyskland eftersom det har ersatts av SEPA-funktionen. |
| Ersatt av en annan funktion? | SEPA-betalningsexport                                                                               |
| Påverkade moduler             | Alla                                                                                                |

### <a name="german-mt940-import"></a>Tysk MT940-import

|                              |                                                                                                                                                                                                                                       |
|------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Den generiska funktionen används nu i stället för den lokaliserade funktionen.                                                                                                                                                                 |
| Ersatt av en annan funktion? | Ja, den här funktionen har ersatts av funktionen för avancerad bankavstämning. Dessutom planeras implementering av kontoutdragsimporten för camt.053 ISO20022 för den allmänna journalen i nästa uppdatering av Dynamics AX. |
| Påverkade moduler             | Alla                                                                                                                                                                                                                                   |

### <a name="german-xml-eu-sales-list"></a>Tysk XML-baserad EU-försäljningslista

|                              |                                                                                                                                                                                    |
|------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | XML-formatet för tyska listrapporten över försäljning inom EU stöds inte längre. Det går enbart att använda textfilformatet ELMA5 för att skicka in listrapporten över försäljning inom EU till den tyska skattemyndigheten. |
| Ersatt av en annan funktion? | Nej                                                                                                                                                                                 |
| Påverkade moduler             | Moms                                                                                                                                                                                |

### <a name="gl-ssrs-reports"></a>GL SSRS-rapporter

Rapporter som innehåller följande menykommandon har tagits bort: **Råbalanssammanfattning**, **Detaljerad råbalans**, **Kontoplan**, **Redovisningsspårning**, **Saldon** och **Saldolista**.

|                              |                                                                                                                                              |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Ekonomiska Microsoft SQL Server Reporting Services-rapporter (SSRS) har ersatts av Management Reporter-funktioner och -standardrapporter. |
| Ersatt av en annan funktion? | Management Reporter (med etiketten **Ekonomisk rapportering** i den aktuella versionen av Dynamics AX)                                                  |
| Påverkade moduler             | Huvudbok                                                                                                                               |

### <a name="infopart-and-formpart-metadata"></a>InfoPart- och FormPart-metadata

|                              |                                                                                                                                                                                                                                |
|------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | InfoPart- och FormPart-metadata möjliggjorde genereringen av faktaboxar för två olika klienter.                                                                                                                                    |
| Ersatt av en annan funktion? | InfoPart-metadata, som var en förenklad formulärdefinition, konverteras till ett formulär med uppgraderingsverktyg. FormPart-metadata, som refererade till ett formulär, ersättas av en mer direkt referens som skapas med uppgraderingsverktyg. |
| Påverkade moduler             | Alla                                                                                                                                                                                                                            |

### <a name="main-account-list-page"></a>Listsida för huvudkonton

En lista med konton för den juridiska personen och tillhörande saldoinformation

|                              |                                                                                                                                                                                    |
|------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Information om saldo är tillgänglig på listsidan **Råbalans** efter konto och dimension.                                                                                      |
| Ersatt av en annan funktion? | **Huvudkonton** innehåller samma lista med konton som listsidan **Huvudkonto**. Rutnätsvyn i **Huvudkonton** visar också en ännu mindre, rutnätslik vy. |
| Påverkade moduler             | Huvudbok                                                                                                                                                                     |

### <a name="malaysia-and-singapore-bank-cash-flow-report"></a>Rapport om bankkassaflöde för Malaysia och Singapore

Den här funktionen låter användaren skriva ut en kassaflödesrapport som visar transaktioner och information om kassainflöden och kassautflöden för ett visst datumintervall för valda bankkonton.

|                              |                                                                         |
|------------------------------|-------------------------------------------------------------------------|
| Orsak till avskrivning       | Samma information kan erhållas från förfrågningsbanktransaktionen. |
| Ersatt av en annan funktion? | Förfrågningsbanktransaktionen                                            |
| Påverkade moduler             | Kassa- och bankhantering                                                |

### <a name="mexican-cfd-electronic-invoice"></a>Mexikansk elektronisk CFD-faktura

Den här funktionen möjliggjorde genereringen av mexikanska e-fakturor med hjälp av CFD-metoden (Comprobante Fiscal Digital), där företaget signerar fakturan genom att begära den relaterade auktoriseringen från myndigheterna. Den här funktioner ger även en månadsvis rapport som innehåller alla e-fakturor som utfärdats under perioden.

|                              |                                                                                                                                                                                                                                                                                                                                                                                                           |
|------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Metoden är inte längre tillämplig. Genereringen av elektroniska fakturor genom att använda CFD-metoden drogs tillbaka av skattemyndigheterna och ersattes av CFDI-metoden (Comprobante Fiscal Digital a través de Internet), där signeringen delegeras till tredjepartsleverantören (PAC). Den månatliga rapporten har tagits bort och ett förfrågningsalternativ gör det möjligt för användare att fråga om historiska transaktioner. |
| Ersatt av en annan funktion? | Nej                                                                                                                                                                                                                                                                                                                                                                                                        |
| Påverkade moduler             | Kundfordringar, Projekt                                                                                                                                                                                                                                                                                                                                                                              |

### <a name="mexico-realized-and-unrealized-vat"></a>Realiserad och orealiserad moms för Mexiko

Microsoft Dynamics AX 2012 hanterade orealiserad mervärdesskatt (VAT) genom att använda funktioner specifika för Mexiko för ”orealiserad moms”.

|                              |                                                                                                                     |
|------------------------------|---------------------------------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Dubblettfunktion                                                                                             |
| Ersatt av en annan funktion? | Ja, den här funktionen har ersatts av standardfunktioner för villkorlig moms som tillhandahålls av basen. |
| Påverkade moduler             | Moms                                                                                                                 |

### <a name="microsoft-outlook-integration"></a>Microsoft Outlook-integrering

|                              |                                                                                |
|------------------------------|--------------------------------------------------------------------------------|
| Orsak till avskrivning       | Den här funktionen har ersatts av Microsoft Exchange Server-integrering. |
| Ersatt av en annan funktion? | Ja                                                                            |
| Påverkade moduler             | Försäljning och marknadsföring                                                            |

### <a name="payroll-information-in-human-resources"></a>Löneinformation i Personal

Löneinformation i HR

|                              |                                                                                                                                                                                                                                                                                                                              |
|------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Den här funktionen har ersatts av huvudsidorna Lön och Personal.                                                                                                                                                                                                                                              |
| Ersatt av en annan funktion? | **Förmåner**, **Inkomster** och andra relaterade sidor, som tidigare fanns i USA-lönelistan, har konfigurerats om och är nu en del av den grundläggande konfigurationen Personal för att ge stöd för extern lönebearbetning. Den här funktionen är att komma åt den **personal 1**&gt;**lön** konfigurationsnyckel. |
| Påverkade moduler             | Personal, Lön                                                                                                                                                                                                                                                                                                     |

### <a name="private-blocking-of-inventory-and-warehouse-management-journals"></a>Privat blockering av inventerings- och lagerhanteringsjournaler

Inventerings- och lagerställejournalerna stöder inte längre möjligheten att markera en journal som privat för en vald användare. Endast processen för att blockera journaler som privata för användargrupper och blockering under redigering stöds.

|                              |                                        |
|------------------------------|----------------------------------------|
| Orsak till avskrivning       | Ingen användning av funktionen påträffades. |
| Ersatt av en annan funktion? | Nej                                     |
| Påverkade moduler             | Lagerhantering                   |

### <a name="product-builder"></a>Product Builder

Product Builder användes för att dynamiskt konfigurera artiklar från en försäljningsorder, inköpsorder, tillverkningsorder, försäljningsoffert, projektoffert eller artikelbehov. Baserat på en produktmodell, som hade modellvariabler, kunde användaren välja värden för att uppfylla kundkraven och för att få en unik produktvariant som hade en strukturlista och ett flöde.

|                              |                                                                                                                                                                                                         |
|------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Product Builder exponerade X++-kod till slutanvändare och stöds inte i den aktuella versionen av Dynamics AX. Den har tagits bort för att undvika dubbelt underhållsarbete med överlappande, ansenliga kodbaser. |
| Ersatt av en annan funktion? | Produktkonfiguration                                                                                                                                                                                   |
| Påverkade moduler             | Produktinformationshantering, Försäljning och marknadsföring                                                                                                                                                     |

### <a name="rename-product-dimension"></a>Byt namn på produktdimension

Den här funktionen låter dig ändra namnet på en av de tre standardproduktdimensionerna (storlek, färg eller format) till ett namn som passar bättre för dina affärsbehov. Namnändringen inkluderade alla etiketter där produktdimensionsnamnet användes.

|                              |                                                                               |
|------------------------------|-------------------------------------------------------------------------------|
| Orsak till avskrivning       | Den aktuella versionen av Dynamics AX stöder inte etikettändringar under körning. |
| Ersatt av en annan funktion? | Nej                                                                            |
| Påverkade moduler             | Produktinformationshantering                                                |

### <a name="role-center-pages"></a>Rollcentersidor

|                              |                                                                                                                                                                          |
|------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Rollcentersidor skapades på den inaktuella Enterprise Portal-plattformen, som har ersatts av den nya webbklientplattformen i den aktuella versionen av Dynamics AX. |
| Ersatt av en annan funktion? | Det nya arbetsyteformulärmönstret förser användare med en processcentrerad design som tillhandahåller enkel åtkomst till vanliga uppgifter i den processen.                       |
| Påverkade moduler             | Alla                                                                                                                                                                      |

### <a name="sales-tax-jurisdictions"></a>Skattemyndigheter

|                              |                                              |
|------------------------------|----------------------------------------------|
| Orsak till avskrivning       | Låg kundanvändning och en begränsad uppsättning funktioner |
| Ersatt av en annan funktion? | Nej                                           |
| Påverkade moduler             | USA-moms                                 |

### <a name="shipping-carrier-interface"></a>Transportföretagsgränssnitt

|                              |                                                                                                                                                 |
|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Dubblettfunktion                                                                                                                         |
| Ersatt av en annan funktion? | Ja, den här funktionen har delvis ersatts av Transporthantering, men har ännu inte ersatts av grundläggande Lagerstyrning (Lagerstyrningssystem I). |
| Påverkade moduler             | Försäljning och marknadsföring, Lagerhantering                                                                                                       |

### <a name="sites-services"></a>Platstjänster

Med hjälp av webbplatstjänster kan du utöka dina affärsprocesser till Internet utan IT-support.

|                              |                                                                                                                                          |
|------------------------------|------------------------------------------------------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Microsoft Azure-infrastrukturen, som användes av Dynamics AX, har nya kapaciteter som kan användas i stället (exempelvis, Azure-webbplatser). |
| Ersatt av en annan funktion? | Nej                                                                                                                                       |
| Påverkade moduler             | Personalrekrytering, Fallhantering, Anbudsförfrågningar, Leverantörsregistrering                                                                  |

### <a name="ssas-demand-forecasting-strategy"></a>SSAS efterfrågan prognostisering strategi

|                              |                                                                              |
|------------------------------|------------------------------------------------------------------------------|
| Orsak till avskrivning       | Utformningen av den här funktionen stöds inte i den nya arkitekturen i molnet. |
| Ersatt av en annan funktion? | Azure maskin inlärning efterfrågan prognostisering strategi                           |
| Påverkade moduler             | Planering                                                                     |

### <a name="travel-requisitions"></a>Reserekvisitioner

|                              |                                                                 |
|------------------------------|-----------------------------------------------------------------|
| Orsak till avskrivning       | Låg användning och de flesta funktioner fanns i Enterprise Portal. |
| Ersatt av en annan funktion? | Nej                                                              |
| Påverkade moduler             | Utläggshantering                                              |

### <a name="vendor-invoice-pool-excluding-posting-details"></a>Leverantörsfakturapool utan bokföringsdetaljer

|                              |                                                                                                         |
|------------------------------|---------------------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Låg användning. Den här funktionen har ersatts av fakturajournalen som har en arbetsflödesfunktion. |
| Ersatt av en annan funktion? | Arbetsflödesfunktionerna i Fakturajournal.                                                           |
| Påverkade moduler             | Leverantörsreskontra                                                                                        |

### <a name="virtual-company-accounts"></a>Virtuella företagskonton

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

### <a name="warehouse-management-ii"></a>Lagerstyrning II

|                              |                                                                                                                                                                                                                                                                                                             |
|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Lagerstyrningssystem II-lösningar (WMS II) som var tillgängliga i modulen **Lagerhantering** duplicerar funktionerna som finns i modulen **Lagerstyrning** som släpptes i Microsoft Dynamics AX 2012 R3.                                                                         |
| Ersatt av en annan funktion? | Modulen **Lagerstyrning** som släpptes i AX 2012 R3, Microsoft Dynamics AX 2012 R3 CU8, och Microsoft Dynamics AX 2012 R3 CU9 ersätter funktionerna i Lagerstyrning II. Den nya modulen har mer avancerade funktioner och mer flexibla lagerstyrningsprocesser än de som erbjöds av funktionerna i Lagerstyrning II. |
| Påverkade moduler             | Lagerhantering, försäljning och marknadsföring, anskaffning och källa                                                                                                                                                                                                                                         |

### <a name="worker-reminders-in-human-resources"></a>Påminnelser till arbetare i Personal

Löneinformation i HR

|                              |                 |
|------------------------------|-----------------|
| Orsak till avskrivning       | Låg användning       |
| Ersatt av en annan funktion? | Nej              |
| Påverkade moduler             | Personal |

### <a name="workplanner"></a>Arbetsplanerare

|                              |                                                                                                                                                                      |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Låg användning                                                                                                                                                            |
| Ersatt av en annan funktion? | Nej, men sidan **Profilrelation**, som öppnas från sidan **Profilgrupper** stöder samma affärsscenario som den inaktuella sidan **Arbetsplanerare**. |
| Påverkade moduler             | Tid och närvaro                                                                                                                                                  |

### <a name="x-financial-statements"></a>X++-bokslut

|                              |                                                                                             |
|------------------------------|---------------------------------------------------------------------------------------------|
| Orsak till avskrivning       | Funktionen har ersatts med en annan funktion.                                    |
| Ersatt av en annan funktion? | Management Reporter (med etiketten **Ekonomisk rapportering** i den aktuella versionen av Dynamics AX) |
| Påverkade moduler             | Huvudbok                                                                              |




