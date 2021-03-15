---
title: Konfigurera tillägget Elektronisk fakturering i Regulatory Configuration Services (RCS)
description: I detta ämne beskrivs hur du konfigurerar tillägget Elektronisk fakturering i Dynamics 365 Regulatory Configuration Services (RCS).
author: gionoder
manager: AnnBe
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: bb4a426bb54ee21197f9954d946d60ea55f5eb76
ms.sourcegitcommit: e88c96d1cb817a22db81856cadb563c095ab2671
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/02/2021
ms.locfileid: "5104441"
---
# <a name="configure-the-electronic-invoicing-add-on-in-regulatory-configuration-services-rcs"></a>Konfigurera tillägget Elektronisk fakturering i Regulatory Configuration Services (RCS)

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/banner.md)]

Detta ämne innehåller information om konfigurationsfunktionerna för tillägget Elektronisk fakturering i Dynamics 365 Regulatory Configuration Services (RCS).

Det är via konfigurationsfunktionerna som tillägget Elektronisk fakturering hjälper dig att uppfylla kraven på elektroniska fakturor och regler utan att behöva koda. I de scenarier där elektroniska fakturor måste godkännas elektroniskt av en webbtjänst hjälper konfigurationsfunktionerna dig dessutom att uppfylla kraven på att utbyta meddelanden med en webbtjänst utan att använda någon kod.

## <a name="electronic-reporting"></a>Elektronisk rapportering

Elektronisk rapportering (ER) stöder tillägget Elektronisk fakturering.

Datamodellmappningen och -formaten är konfigurerbara komponenter som skapas och underhålls via ER och används i tillägget Elektronisk fakturering. ER-formatdesignern är verktyget som används för att skapa och underhålla filformat. Den används för att konfigurera de elektroniska faktureringsfunktionerna.

Mer information finns i [Översikt för Elektronisk rapportering (ER)](../../fin-ops-core/dev-itpro/analytics/general-electronic-reporting.md).

## <a name="electronic-invoicing-features"></a>Funktioner för elektronisk fakturering

Funktionerna för elektronisk fakturering ansvarar för att elektroniska fakturor genereras via tillägget Elektronisk fakturering. De kapslar in konfigurationsreglerna och använder dem för att bearbeta data som Microsoft Dynamics 365 Finance och Dynamics 365 Supply Chain Management skickar till tillägget Elektronisk fakturering samt till elektroniska fakturor.

Funktionerna stöder också scenarier där efterlevnad av specifikationerna för filformat krävs och utdatan är en fristående elektronisk fil. I de flesta fall publiceras specifikationerna för filformaten av skattemyndigheten.

Slutligen stöder funktionerna utbyte av meddelanden med externa webbtjänster som har antingen skattemyndigheten eller någon behörig part auktoriserad part som värd, samt även begäranden om auktorisering eller godkännandestämpel på den elektroniska fakturan.

### <a name="availability-of-electronic-invoicing-features"></a>Tillgänglighet för funktioner för elektronisk fakturering

Tillgängligheten till de elektroniska faktureringsfunktionerna beror på land eller region. Vissa funktioner är vanligtvis tillgängliga medan andra endast utgör förhandsversioner.

#### <a name="preview-features"></a>Förhandsfunktioner

Följande tabell visar de elektroniska faktureringsfunktioner som för närvarande utgör förhandsversioner.

| Land/region | Funktionsnamn                         | Affärsdokument |
|----------------|--------------------------------------|-------------------|
| Österrike        | Österrikiska elektroniska fakturor (AT)    | Försäljnings- och projektfakturor |
| Belgien        | Belgisk elektronisk faktura (BE)      | Försäljnings- och projektfakturor |
| Brasilien         | Brasiliansk NF-e (BR)                  | Skattedokumentmodell 55, korrigeringsbrev, annulleringar och kasseringar |
| Brasilien         | Brasiliansk NFS-e ABRASF Curitiba (BR) | Skattedokument för tjänster |
| Brasilien         | Brasiliansk NFS-e São Paulo (BR)       | Skattedokument för tjänster |
| Danmark        | Dansk elektronisk faktura (DK)       | Försäljnings- och projektfakturor |
| Egypten          | Egyptisk elektronisk faktura (EG) | Försäljnings- och projektfakturor |
| Estland        | Estnisk elektronisk faktura (EE)     | Försäljnings- och projektfakturor |
| Finland        | Finsk elektronisk faktura (FI)      | Försäljnings- och projektfakturor |
| Frankrike         | Fransk elektronisk faktura (FR)       | Försäljnings- och projektfakturor |
| Tyskland        | Tysk elektronisk faktura (DE)       | Försäljnings- och projektfakturor |
| Italien          | FatturaPA (IT)                       | Försäljnings- och projektfakturor |
| Mexiko         | Mexikansk CFDI (MX)                    | Försäljningsfakturor, följesedlar, lageröverföringar, betalningskomplement och annulleringar |
| Nederländerna    | Holländsk elektronisk faktura (NL)        | Försäljnings- och projektfakturor |
| Norge         | Norsk elektronisk faktura (NO)    | Försäljnings- och projektfakturor |
| Spanien          | Spansk elektronisk faktura (ES)      | Försäljnings- och projektfakturor |
| Europa         | PEPPOL-elektronisk faktura            | PEPPOL-försäljnings- och -projektfakturor |

### <a name="configurable-components-of-electronic-invoicing-features"></a>Konfigurerbara komponenter i elektroniska faktureringsfunktioner

De elektroniska faktureringsfunktionerna består av följande grupper konfigurerbara komponenter:

- **Format** – Med format kan du konfigurera vad tillägget Elektronisk fakturering måste generera när ett elektroniskt dokument blir en elektronisk faktura. Formaten inkluderar formatkonfigurationen för den elektroniska fakturan samt för filer och meddelanden som används för att skicka förfrågningar och ta emot svar när kommunikation med en extern webbtjänst krävs.
- **Åtgärder** – Med åtgärder kan du konfigurera hur tillägget Elektronisk fakturering genererar transformeringen av ett elektroniskt dokument som Finance och Supply Chain Management har skickat till en elektronisk faktura.
- **Tillämpliglighetsregler** – Med tillämplighetsregler kan du konfigurera den kontext som tillägget Elektronisk fakturering måste överväga för att bearbeta en elektronisk faktureringsfunktion.
- **Variabler** – Variabler gör att du kan konfigurera stödet för skapandet av konfigurationslogiken. Variabler kan fungera som indata för värden för att utföra en viss åtgärd. De kan också fungera som ett värdeutbyte mellan Finance och Supply Chain Management och tillägget Elektronisk fakturering.
- **Elektronisk dokumentmodellmappning** – Med hjälp av den elektroniska dokumentmodellmappningen kan du konfigurera ER-modellmappning. Modellmappningen definierar datamappningen för den abstrakta faktura som integreras i tillägget Elektronisk fakturering när elektroniska dokument skickas.
- **Kontextmodell för faktura** – Med hjälp av fakturakontextmodellen kan du konfigurera kontextmodellen för ER-fakturor och definiera sammanhanget för en elektronisk faktureringsfunktion.
- **Svarstyper** – Med svarstyper kan du konfigurera vad tillägget Elektronisk fakturering måste uppdatera i Finance och Supply Chain Management som ett resultat av den elektroniska fakturabearbetningen.

### <a name="formats"></a>Format

Följande listor visar de ER-formatkonfigurationer som är tillgängliga för de elektroniska faktureringsfunktionerna.

#### <a name="austrian-at-electronic-invoices-sales-and-project-invoices-for-austria"></a>Elektroniska fakturor för Österrike (AT): Försäljnings- och projektfakturor för Österrike

- OIOUBL-försäljningsfaktura
- OIOUBL-projektfaktura
- OIOUBL-försäljningskreditfaktura
- Kreditfaktura för OIOUBL-projekt

#### <a name="belgian-be-electronic-invoice-sales-and-project-invoices-for-belgium"></a>Elektronisk faktura för Belgien (BE): Försäljnings- och projektfakturor för Belgien

- UBL-försäljningsfaktura BE
- UBL-projektfaktura BE
- UBL-kreditfaktura för projekt BE
- UBL-försäljningskreditfaktura BE

#### <a name="brazilian-br-nf-e-nf-e-federal-brazil"></a>Brasiliansk (BR) NF-e: NF-e Federal (Brasilien)

- NF-e försändelseformat för export (BR)
- NF-e exportformat för rättelsebrev (BR)
- NF-e annulleringsformat för export (BR)
- NF-e kasseringsformat för export (BR)

#### <a name="brazilian-nfs-e-br-nfs-e-abrasf-curitiba-city"></a>Brasiliansk NFS-e (BR): NFS-e ABRASF Curitiba city

- NFS-e ABRASF Curitiba (BR)
- NFS-e ABRASF Inquire Curitiba (BR)

#### <a name="brazilian-br-nfs-e-nfs-e-so-paulo-city"></a>Brasiliansk (BR) NFS-e: NFS-e São Paulo city

- NFS-e Sao Paulo (BR)

#### <a name="danish-dk-electronic-invoice-sales-and-project-invoices-for-denmark"></a>Elektronisk faktura för Danmark (DK): Försäljnings- och projektfakturor för Danmark

- OIOUBL-försäljningsfaktura
- OIOUBL-projektfaktura
- OIOUBL-försäljningskreditfaktura
- Kreditfaktura för OIOUBL-projekt

#### <a name="dutch-nl-electronic-invoice-sales-and-project-invoices-for-netherlands"></a>Elektronisk faktura för Nederländerna (NL): Försäljnings- och projektfakturor för Nederländerna

- UBL-försäljningsfaktura NL
- UBL-projektfaktura NL
- UBL-kreditfaktura för projekt NL
- UBL-försäljningskreditfaktura NL

#### <a name="egyptian-eg-electronic-invoice-sales-and-project-invoices-for-egypt"></a>Elektronisk faktura för Egypten (EG): Försäljnings- och projektfakturor för Egypten

- Försäljningsfaktura (EG) (Fakturering)
- Projektfaktura (EG) (Fakturering)

#### <a name="estonian-ee-electronic-invoice-sales-and-project-invoices-for-estonia"></a>Elektronisk faktura för Estland (EE): Försäljnings- och projektfakturor för Estland

- Försäljningsfaktura (EE)
- Projektfaktura (EE)

#### <a name="finnish-fi-electronic-invoice-sales-and-project-invoices-for-finland"></a>Elektronisk faktura för Finland (FI): Försäljnings- och projektfakturor för Finland

- Försäljningsfaktura (FI)
- Projektfaktura (FI)

#### <a name="french-fr-electronic-invoice-sales-and-project-invoices-for-france"></a>Elektronisk faktura för Frankrike (FR): Försäljnings- och projektfakturor för Frankrike

- UBL-försäljningsfaktura FR
- UBL-projektfaktura FR
- UBL-kreditfaktura för projekt FR
- UBL-försäljningskreditfaktura FR

#### <a name="german-de-electronic-invoice-sales-and-project-invoices-for-germany"></a>Elektronisk faktura för Tyskland (DE): Försäljnings- och projektfakturor för Tyskland

- Försäljningsfaktura (DE)
- Projektfaktura (DE)

#### <a name="italian-it-electronic-invoice-sales-and-project-invoices-for-italy"></a>Elektronisk faktura för Italien (IT): Försäljnings- och projektfakturor för Italien

- Försäljningsfaktura (IT)
- Projektfaktura (IT)

#### <a name="mexican-mx-cfdi-cfdi-for-mexico"></a>Mexikansk (MX) CFDI: CFDI för Mexiko

- CFDI-fakturaformat (MX)
- CFDI Följesedel (MX)
- CFDI-lageröverföring (MX)
- CFDI-betalningsformat (MX)
- CFDI-format för annullering av faktura (MX)

#### <a name="norwegian-no-electronic-invoice-sales-and-project-invoices-for-norway"></a>Elektronisk faktura för Norge (NO): Försäljnings- och projektfakturor för Norge

- OIOUBL-försäljningsfaktura
- OIOUBL-projektfaktura
- OIOUBL-försäljningskreditfaktura
- Kreditfaktura för OIOUBL-projekt

#### <a name="peppol-electronic-invoice-peppol-sales-and-project-invoices"></a>PEPPOL-elektronisk faktura: PEPPOL-försäljnings- och -projektfakturor

- PEPPOL-försäljningsfaktura
- PEPPOL-projektfaktura
- PEPPOL-försäljningskreditfaktura
- Kreditfaktura för PEPPOL-projekt

#### <a name="spanish-es-electronic-invoice-sales-and-project-invoices-for-spain"></a>Elektronisk faktura för Spanien (ES): Försäljnings- och projektfakturor för Spanien

- Försäljningsfaktura (ES)
- Projektfaktura (ES)

### <a name="actions"></a>Åtgärder

I följande tabell visas en lista över tillgängliga åtgärder samt om dessa för tillfället är tillgängliga eller fortfarande är i förhandsgranskning.

| Åtgärd                                        | beskrivning                                                                  | Tillgänglighet         |
|-----------------------------------------------|------------------------------------------------------------------------------|----------------------|
| Transformera dokument                            | Transformera dokumentet genom att köra Elektronisk rapportering.                   | Allmänt tillgängligt  |
| Signera xml-dokument                             | Signera xml-dokument med digital signatur.                                   | I förhandsgranskning           |
| Signera json-dokument för egyptisk skattemyndighet | Signera json-dokument med digital signatur för egyptisk skattemyndighet.       | Allmänt tillgängligt  |
| Integrera med egyptisk ETA-tjänst           | Kommunicera med egyptisk skattemyndighet.                                     | Allmänt tillgängligt  |
| Ring brasiliansk SEFAZ-tjänst                  | Integrera med brasiliansk SEFAZ-tjänst för sändning av skattedokument.       | I förhandsgranskning           |
| Ring mexikansk PAC-tjänst                      | Integrera med mexikansk PAC-tjänst för CFDI-sändning.                      | I förhandsgranskning           |
| Behandla svar                              | Analysera svaret från webbtjänstsamtalet.                     | Allmänt tillgängligt  |
| Använd MS Power Automate                         | Integrera med flödet inbyggt i Microsoft Power Automate.                       | I förhandsgranskning           |

## <a name="configuration-providers"></a>Konfigurationsleverantörer

Konfigurationsleverantörerna tillhandahåller elektroniska faktureringsfunktioner och deras ER-komponenter, till exempel modellmappning, formatkonfiguration och sammanhangsmodell. De publicerar de elektroniska faktureringsfunktionerna och ER-komponenterna i den associerade globala databasen. Därifrån kan andra organisationer hämta dem.

Innan du konfigurerar de elektroniska faktureringsfunktionerna via RCS måste du konfigurera din egen organisation som konfigurationsleverantör i modulen **Elektronisk rapportering**. För information om hur du ställer in en konfigurationsleverantör som **Aktiv**, se [Skapa konfigurationsleverantörer och markera dem som aktiva](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).

## <a name="viewing-electronic-invoicing-features-in-the-global-repository"></a>Visa elektroniska faktureringsfunktioner i den globala databasen

Om du vill bläddra i de elektroniska faktureringsfunktionerna som är tillgängliga i den globala databasen för en viss konfigurationsleverantör, synkroniserar du organisationens RCS-instans. När synkroniseringen är klar uppdateras listan med tillgängliga funktioner för elektronisk fakturering.

## <a name="importing-electronic-invoicing-features"></a>OImportera funktioner för elektronisk fakturering

Innan du använder eller konfigurerar de elektroniska faktureringsfunktionerna måste du importera dem till organisationens RCS-instans. Importåtgärden skapar en lokal kopia av funktionerna och kopierar alla ER-artefakter som funktionerna använder (till exempel formatkonfigurationer och modellkonfigurationer) till organisationens RCS-instans.

Du kan importera de elektroniska faktureringsfunktionerna från valfri konfigurationsleverantör.

## <a name="creating-electronic-invoicing-features"></a>Skapa funktioner för elektronisk fakturering

Du kan skapa en funktion för elektronisk fakturering från grunden eller också härleda den från en annan funktion för elektronisk fakturering.

När du skapar en elektronisk faktureringsfunktion från grunden måste du lägga till ER-komponenterna manuellt (till exempel funktionsversions- och andra konfigurationer som funktionens versionsinställning och programinställningar). När du skapar en funktion genom att härleda den från en annan funktion, ärver den nya funktionen alla konfigurationer från den ursprungliga. 

## <a name="electronic-invoicing-feature-version"></a>Funktionsversion för elektronisk fakturering

Funktionerna för elektronisk fakturering uppdateras genom olika versioner. När en ny version skapas ökar versionsnumret automatiskt. Ett "gäller från"-datum kan definieras för den nya versionen.

Versioner av elektroniska faktureringsfunktioner har en livscykel med upp till tre statusar:

- **Utkast** – Om en funktionsversion har det här statusvärdet kan du redigera dess konfigurationsattribut och alla dess artefakter (till exempel filformatkonfigurationer).
- **Komplett** – Om en funktionsversion har denna status, har den publicerats i den globala databas som är associerad med din organisation. Det går inte längre att redigera funktionsversionen eller någon av ER-komponenterna.
- **Publicerad** – Om en funktionsversion har denna status har den publicerats i tillägget Elektronisk fakturering. Det går inte längre att redigera funktionsversionen eller någon av ER-komponenterna.

### <a name="feature-configurations"></a>Funktionskonfigurationer

Funktionskonfigurationer innehåller alla ER-formatkonfigurationer som de elektroniska faktureringsfunktionerna använder. Alla elektroniska filer som en elektronisk faktureringsfunktion använder under bearbetningen kommer från de formatkonfigurationer som har lagts till i den funktionens funktionskonfigurationer.

Från funktionskonfigurationerna kan du öppna ER-formatdesignern, som är det ER-verktyg som används för att skapa formatkonfigurationer.

### <a name="feature-setup"></a>Funktionskonfiguration

Funktionsinställningar används i kombination med funktionskonfigurationer. Varje funktionsinställning innehåller en uppsättning åtgärder, tillämplighetsregler och variabler som ger förväntat beteende så att en elektronisk faktureringsfunktion kan uppfylla ett visst krav på den elektroniska fakturan.

### <a name="application-setup"></a>Programkonfiguration

Programinställningen måste associeras med ett tidigare skapat anslutet program.

Via programinställningarna kan du konfigurera den del av en elektronisk faktureringsfunktion som måste göras i Finance och Supply Chain Management. Minst tre konfigurerbara komponenter är obligatoriska, oavsett funktionen för elektronisk fakturering:

- **Registernamn** – Den entitet i Finance och Supply Chain Management som innehåller bokförda fakturor och som den elektroniska faktureringsfunktionen bygger på.
- **Kontext** – Namnet på den fakturakontextmodell som konfigurerats via ER.
- **Mappning av affärsdokument** – Namnet på den fakturamappningsmodell som konfigurerats via ER.

> [!IMPORTANT]
> Konfigurationen som anges i programinställningarna kan visas i Finance och Supply Chain Management. Gå till **Organisationsadministration \> Inställningar \> Parameter för elektroniska dokument**. På fliken **Elektroniskt dokument** väljer du **Distribuera** och sedan alternativet **Anslutet program**.

### <a name="deploying-feature-versions"></a>Distribuera funktionsversioner

I RCS använder du kommandot **Distribuera** för att rikta och publicera en version av en elektronisk faktureringsversion. Välj **Distribuera** och sedan ett av följande alternativ för att definiera distributionens mål: 

- **Tjänstemiljö** – När målet för distributionen är tjänstemiljön, publiceras versionen av den elektroniska faktureringsfunktionen i tjänstemiljön. Tillägget Elektronisk fakturering är sedan redo att ta emot och bearbeta elektroniska dokument som Finance och Supply Chain Management skickar.
- **Anslutet program** – När målet för distributionen är det anslutna programmet skrivs konfigurationen som tillhandahålls via programinställningarna i den Finance- och Supply Chain Management-instans som tidigare associerades med den.

Endast elektroniska faktureringsfunktionsversioner med **Slutförd** kan distribueras till antingen en tjänstemiljö eller ett anslutet program.

### <a name="removing-feature-versions"></a>Ta bort funktionsversioner

I RCS använder du kommandot **Avdistribuera** om du vill ta bort en specifik version av den elektroniska faktureringsfunktionen från en tjänstemiljö i tillägget Elektronisk fakturering.

> [!IMPORTANT]
> Kommandot **Avdistribuera** fungerar endast i tjänstemiljöer. Det tar inte bort elektroniska faktureringsfunktionsversioner från anslutna program.

### <a name="rebasing-electronic-invoicing-features"></a>Basera om funktioner för elektronisk fakturering

När en funktion för elektronisk fakturering härleds från en annan, uppdaterar kommandot **Basera om** den härledda funktionen med de ändringar som har införts i den ursprungliga funktionen.

## <a name="additional-resources"></a>Ytterligare resurser

- [Utfärda elektroniska fakturor i Finance and Supply Chain Management](e-invoicing-issuing-electronic-invoices-finance-supply-chain-management.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]