---
title: Kom igång med tillägget elektronisk fakturering
description: Det här avsnittet innehåller information som hjälper dig att komma igång med tillägget elektronisk fakturering i Microsoft Dynamics 365 Finance och Dynamics 365 Supply Chain Management.
author: gionoder
manager: AnnBe
ms.date: 10/08/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 7b2a3aae43d42060c7fcd9e1ea3db814fc5d8f22
ms.sourcegitcommit: f860ac2b18f6bbbfc4a46b497baec2477105b116
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/19/2020
ms.locfileid: "4448190"
---
# <a name="get-started-with-the-electronic-invoicing-add-on"></a>Kom igång med tillägget elektronisk fakturering

[!include [banner](../includes/banner.md)]

Det här avsnittet innehåller information som hjälper dig att komma igång med tillägget elektronisk fakturering. Först guidar vi dig genom konfigurationsstegen i Microsoft Dynamics Lifecycle Services (LCS), Regulatory Configuration Services (RCS) och Dynamics 365 Finance. Därefter beskrivs hur du skickar dokument via tjänsten med hjälp av Dynamics 365 Finance eller Dynamics 365 Supply Chain Management. Du får också lära dig att tolka överföringsloggar.

## <a name="availability"></a>Tillgänglighet

Tillägget elektronisk fakturering är inledningsvis tillgängligt för flera länder. Tillägget kan användas för att skapa elektroniska fakturor och för att skicka följande affärsdokument:

| Land/region  | Affärsdokument                          |
|-----------------|--------------------------------------------|
| Österrike         | Försäljnings- och projektfakturor                 |
| Belgien         | Försäljnings- och projektfakturor                 |
| Brasilien          | Elektroniskt skattedokument modell 55 (NF-e) |
| Danmark         | Försäljnings- och projektfakturor                 |
| Estland         | Försäljnings- och projektfakturor                 |
| Finland         | Försäljnings- och projektfakturor                 |
| Frankrike          | Försäljnings- och projektfakturor                 |
| Tyskland         | Försäljnings- och projektfakturor                 |
| Italien           | Försäljnings- och projektfakturor                 |
| Mexiko          | CFDI-faktura                               |
| Nederländerna     | Försäljnings- och projektfakturor                 |
| Norge          | Försäljnings- och projektfakturor                 |
| Spanien           | Försäljnings- och projektfakturor                 |
| Europa          | PEPPOL försäljnings- och projektfakturor          |
    
## <a name="licensing"></a>Licensiering

Du kan använda tillägget elektronisk fakturering med din aktuella licens. Det krävs inga fler licenser för att använda tjänsten.

## <a name="prerequisites"></a>Förutsättningar

Innan du kan slutföra stegen i detta ämne måste du ha följande förutsättningar :

- Åtkomst till ditt LCS-konto.
- Ett LCS distributionsprojekt som innehåller Finance eller Supply Chain Management version 10.0.13 eller senare.
- Åtkomst till ditt RCS-konto.
- Aktivera globaliseringsfunktionen för ditt RCS-konto via modulen för **funktionshantering**. Mer information finns i [Regulatory Configuration Services (RCS) - globaliseringsfunktioner](rcs-globalization-feature.md)
- Skapa en resurs för nyckelvalv och lagringskonto i Azure. Mer information finns i [Skapa Azure Storage-konto och nyckelvalv](e-invoicing-create-azure-storage-account-key-vault.md).

## <a name="overview"></a>Översikt

Följande illustration visar de fem huvudsteg som du kommer att utföra i det här avsnittet.

![Översikt över fem steg i det här avsnittet](media/e-invoicing-services-get-started-overview-5-steps.png)

1. **Inställningar för Azure-resurser:** Konfigurera Azure-lagring och överför digitala certifikat i Azure Key Vault.
2. **LCS-inställningar:** installera tillägget för mikrotjänster.
3. **RCS-inställning:** Ställ in miljö, användaråtkomst och e-faktureringsfunktioner.
4. **Klientinställning:** Konfigurera anslutningen mellan klienten och tillägget elektronisk fakturering och stäng av de gamla funktionerna för att skicka och ta emot svar på elektroniska dokument.
5. **Skicka fakturor:** skicka elektroniska dokument via tillägget elektronisk fakturering och få svar.

> [!NOTE]
> Vissa konfigurationssteg i det här avsnittet är gemensamma och oberoende av land/region. De steg och installationsprocedurer som är specifika för landet beskrivs i lands-/regionspecifika ämnen.

## <a name="lcs-setup"></a>Inställning av LCS

1. Logga in på LCS-kontot.
2. Välj panelen **Hantering av förhandsgranskningsfunktioner** och fältgruppen **Förhandsversionsfunktioner**, välj **BusinessDocumentSubmission**.
3. Markera fältet **aktivera förhandsversion**.
4. Välj LCS distributionsprojekt. Innan du kan välja projektet måste det köras.
5. På snabbfliken **Miljötillägg** välj **Installera ett nytt tillägg**.
6. Välj **Skicka affärsdokument**.
7. I dialogrutan **Tillägg för konfiguration** i fältet **AAD app-ID** anger du **091c98b0-a1c9-4b02-b62c-7753395ccabe**. Det här värdet är ett fast värde.
8. I fältet **AAD innehavar-ID** anger du ID för ditt Azure abonnemangskonto.

    ![Dialogrutan tillägg för konfiguration i LCS](media/e-invoicing-services-get-started-lcs-addin-setup.png)

9. Markera kryss rutan om du vill acceptera villkoren.
10. Välj **Installera**.

## <a name="rcs-setup"></a>Inställning av RCS

Under RCS-inställningar ska du utföra följande uppgifter:

1. Ställ in nyckelvalvet i RCS.
2. Ställ in RCS-integrationen med tilläggsserver för elektronisk fakturering.
3. Skapa en tilläggsmiljö för elektronisk fakturering för organisationen.

### <a name="set-up-the-key-vault-in-rcs"></a>Ställ in nyckelvalvet i RCS

1. Logga in på RCS-kontot.
2. I arbetsytan **globaliseringsfunktioner** i avsnittet **Miljöer**, välj panelen **e-fakturering**.
3. Välj **tjänstemiljöer**.

    ![Välj tjänstemiljöer](media/e-invoicing-services-get-started-select-service-environments.png)

> [!NOTE]
> Alternativet **anslutna program** ger åtkomst för den automatiska konfigurationen av tillägget för elektronisk fakturering i Finance eller Supply Management genom RCS. Den här funktionen är dock fortfarande under utveckling.

4. Klicka på **Key Vault-parametrar** i åtgärdsfönstret.

    ![Välja Key Vault-parametrar](media/e-invoicing-services-get-started-select-key-vault-parameters.png)

5. I åtgärdsfönstret, välj **Ny** för att lägga till ett nyckelvalv.
6. I fältet **URI för nyckelvalv** ange **DNS-namn** attributvärde för nyckelvalvresursen som du konfigurerade i Azure. Information om var du hittar värdet **DNS-namn** se [Skapa Azure Storage-konto och nyckelvalv](e-invoicing-create-azure-storage-account-key-vault.md).

    ![URI-fält för nyckelvalv](media/e-invoicing-services-get-started-enter-key-vault-uri.png)

7. På snabbfliken **Certifikat** väljer **Lägg till** om du vill ange alla digitala certifikatnamn och nyckel valv hemligheter som behövs för att upprätta betrodda anslutningar. I kolumnen **Typ** kan du ange om det är ett certifikat eller en hemlighet. Båda uppsättningarna av värden konfigureras i resurserna för nyckelvalv i Azure.

    ![Lägger till certifikat](media/e-invoicing-services-get-started-add-digital-certificates.png)

8. Om din lands-/regionspecifika faktura kräver en kedja med certifikat för att tillämpa en digital signatur, väljer du en **kedja av certifikat** i åtgärdsfönstret och anger sedan sekvensen av certifikat eller nyckelvalv hemligheter som utgör kedjan.

### <a name="set-up-the-rcs-integration-with-the-electronic-invoicing-add-on-server"></a>Ställ in RCS-integrationen med tilläggsserver för elektronisk fakturering

1. I arbetsytan **globaliseringsfunktioner** i avsnittet **Relaterade inställningar** väljer du länken **parametrar för elektronisk rapportering**.
2. Välj **Klicka här om du vill ansluta till Lifecycle Service**. Om du inte vill ansluta till LCS väljer du **Avbryt**.
3. På fliken **e-faktureringstjänster** i fälten **Tjänsteslutpunkt-URI** anger du värdet enligt tillgängliga geografier: `https://businessdocumentsubmission.us.operations365.dynamics.com/` eller `https://businessdocumentsubmission.eu.operations365.dynamics.com/`.
4. I fältet **app-ID** kontrollera att det visar ID **0cdb527f-a8d1-4bf8-9436-b352c68682b2**. Det här värdet är ett fast värde.
5. I fältet **LCS miljö-ID** anger du ID för ditt LCS abonnemangskonto.

![Ange parametrar för tillägget elektronisk fakturering](media/e-invoicing-services-get-started-enter-e-invoicing-parameters.png)

### <a name="add-an-electronic-invoicing-add-on-environment"></a>Lägg till en miljö för elektronisk fakturering

Du kan skapa olika miljöer för tillägget för elektronisk fakturering, till exempel utvecklings-, test- eller produktionsmiljöer.

1. I arbetsytan **globaliseringsfunktioner** i avsnittet **Miljöer**, välj panelen **e-fakturering**.
2. Skapa en miljö genom att välja **Nytt**.
3. I fältet **Konto för SAS-lagringstoken** anger du namnet på nyckelvalvets hemlighet som du konfigurerade i nyckelvalvet i RCS.

    ![Fältet konto för SAS-lagringstoken](media/e-invoicing-services-get-started-enter-sas-token-secret.png)

4. På snabbfliken **Använder**, välj **Ny** för att bevilja åtkomst till användare för den här miljön.

    ![Lägga till tjänstanvändare](media/e-invoicing-services-get-started-enter-service-users.png)

5. I åtgärdsfönstret **Publicera** för att publicera miljön på tilläggsservern elektronisk fakturering.

    ![Knappen publicera](media/e-invoicing-services-get-started-publish-service-environment.png)

### <a name="e-invoicing-feature-setup"></a>Inställningar för e-faktureringsfunktioner

"e-faktureringsfunktionen" är det allmänna namnet för resursen som är konfigurerad och publicerad för att använda tilläggsservern för elektronisk fakturering. Inställningen av funktionen e-fakturering kombinerar bland annat användningen av konfigurationsformat för elektronisk rapportering (ER) för att skapa konfigurerbara export- och importfiler och användningen av åtgärder och åtgärdsflöden för att möjliggöra skapandet av konfigurerbara regler för att skicka förfrågningar , importera svar och analysera svarsinnehållet.

På grund av varianter i fakturaformat och åtgärdsflöden är funktionen för e-fakturering är beroende av land/region.

## <a name="set-up-electronic-invoicing-add-on-integration-in-finance-or-supply-chain-management"></a>Ställa in integrering av tillägget elektronisk fakturering i Finance eller Supply Chain Management 

Under den här inställningen ska du göra följande uppgifter:

1. Öppna funktionen flygning
2. Aktivera integreringen av tillägget av den elektroniska faktureringsfunktionen med Finance.
3. Ställ in URL för slutpunkt av tillägget för elektronisk fakturering.
4. Importera ER-konfigurationer som är relaterade till den lands-/regionspecifika e-faktureringsfunktionen.
5. Aktivera tillämplig landsspecifik e-faktureringsfunktion.
6. Importera ER-konfigurationerna och ställ in de svarstyper som krävs för att uppdatera ditt lands-/regionsspecifika fakturadokument som ett resultat av överföringsprocessen.

### <a name="open-flighted-feature"></a>Öppna funktionen flygning
Integreringsfunktionen för elektronisk faktura aktiveras via flygning. Flygning är ett begrepp som gör att en funktion kan vara PÅ eller AV som standard. Med följande steg aktiverar du en flygning i en icke-produktionsmiljö. 

1. Kör följande SQL-kommando:

    INFOGA I SYSFLIGHTING (FLIGHTNAME, ENABLED) VÄRDEN ('BusinessDocumentSubmissionServiceEnabled', 1)
    
    INFOGA I SYSFLIGHTING (FLIGHTNAME, ENABLED) VÄRDEN ('ElectronicInvoicingServiceIntegrationFeature', 1)
    
2. När du har gjort ovanstående ändring utför du en IISReset på alla AOS

### <a name="turn-on-the-electronic-invoicing-add-on-integration-feature"></a>Aktivera integrationsfunktionen för tillägget för elektronisk fakturering

1. Logga in på Finance eller Supply Chain Management.
2. I arbetsytan **Funktionshantering** söker du efter den nya funktionen **konfigurerbara integreringstillägg för elektronisk fakturering**. Om funktionen fortfarande inte visas på sidan funktionshantering kör du funktionen **Sök efter uppdateringar**
3. Välj funktionen och välj sedan **aktivera nu**.

### <a name="set-up-the-service-endpoint-url"></a>Ställ in URL för tjänstslutpunkt

1. Gå till **organisationsadministration \> inställning \> parametrar för elektroniska dokument**.
2. På fliken **sändningstjänst** i fältet **URL för tjänstslutpunkt** anger du `https://businessdocumentsubmission.us.operations365.dynamics.com/`.
3. I fältet **miljö** anger du namnet på tilläggsmiljön för elektronisk fakturering som du skapade under installationen av RCS.

![Ange tjänstparametrar](media/e-invoicing-services-get-started-enter-service-endpoint.png)

### <a name="import-the-er-configurations"></a>Importera ER-konfigurationer

Om du vill göra det möjligt att samla affärsdata och skicka dem till tillägget elektronisk fakturering måste du importera konfigurationen ER-datamodell och ER-datamodell som är relaterade till den lands-/regionspecifika e-faktureringsfunktion som du vill använda.

1. I arbetsytan **elektronisk rapportering** i avsnittet **konfigurationsprovider** väljer du panelen **Microsoft**. Kontrollera att konfigurationsprovidern är **aktiverad**. För information om hur du ställer in en leverantör på **Aktiv**, se [Skapa konfigurationsleverantörer och markera dem som aktiva](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11).
3. Välj **Databaser**.
4. Markera **Global resurs** och välj sedan **Öppna**.
5. I dialogrutan **Ansluta till Lifecycle Services** välj **Klicka här för att ansluta till Lifecycle Service**.
6. Beroende på vilket land eller region du vill använda e-faktureringsfunktionen för, måste du importera lämplig datamodell, mappning av datamodell och format. Information om de ER-konfigurationer som du bör importera finns i avsnittet lands-/regionspecifika "komma igång med det elektroniska tillägget för fakturering".
7. Importera **kontextmodell för kundfaktura**. Den här modellen innehåller ytterligare parametrar som bland annat beskriver miljön i Finance som används för tillägget för elektronisk fakturering när affärsdata skickas in.

### <a name="turn-on-countryregion-specific-e-invoicing-features"></a><a name="region-specific"></a>Aktivera landsspecifika e-faktureringsfunktioner

Om du vill aktivera lands-/regionspecifika e-faktureringsfunktioner så att de fungerar tillsammans med tillägget för elektronisk fakturering, måste du aktivera funktionen i varje juridisk person där du vill använda den. Efteråt går det inte längre att använda den gamla integrationen av elektronisk fakturering och integrationen med det nya tillägget för elektronisk fakturering aktiveras.

1. Gå till **organisationsadministration \> inställning \> parametrar för elektroniska dokument**.
2. På fliken **Funktioner** i raden för funktionen som är relaterad till din lands-/regionspecifika e-faktureringsfunktion markerar du kryssrutan i kolumnen **Aktiverad**. Information om vilken funktion som du bör aktivera finns i avsnittet lands-/regionspecifika "komma igång med det elektroniska tillägget för fakturering".

![Aktivera e-faktureringsfunktionen](media/e-invoicing-services-get-started-enable-invoicing-feature.png)

> [!NOTE]
> Om du har flera juridiska personer som konfigurerats för olika länder eller regioner, kan du aktivera funktionen för lands-/regionsspecifik e-fakturering för varje juridisk person.

### <a name="import-er-configurations-and-set-up-the-response-types-to-update-your-countryregion-specific-invoice-document"></a>Importera ER-konfigurationer och ställ in svarstyperna för att uppdatera ditt lands-/regionspecifika fakturadokument

Om det överförda fakturadokumentet kräver en uppdatering efter det att sändningen har avsänts till statliga auktoriseringstjänster, måste du importera en särskild ER-datamodell och konfigurationer för att kunna uppdatera status för fakturadokumentet eller något annat fält som ska uppdateras.

1. I arbetsytan **elektronisk rapportering** i avsnittet **konfigurationsprovider** väljer du panelen **Microsoft**.
2. Välj **Databaser**.
3. Markera **Global resurs** och välj sedan **Öppna**.
4. Importera **Modell för svarsmeddelande**, **Importformat för svarsmeddelande**, **Modell för svarsmeddelande för mappning till destination** och **Importformat för filinnehåll**.
5. Gå till **organisationsadministration \> inställning \> parametrar för elektroniska dokument**.
6. På fliken **Elektroniskt dokument** välj **Lägg till** för att ange namnet på tabellen som är relaterad till ditt lands-/regionspecifika fakturadokument. Information om vilket registernamn som du bör välj finns i avsnittet lands-/regionspecifika "komma igång med det elektroniska tillägget för fakturering".
7. Välj **svarstyper** för att konfigurera svarstyper. Information om vilket registernamn som du bör välj finns i avsnittet lands-/regionspecifika "komma igång med det elektroniska tillägget för fakturering".

![Ställ in svarstyper](media/e-invoicing-services-get-started-set-up-response-types.png)

## <a name="e-invoicing-feature-names-by-country"></a>Namn på e-faktureringsfunktion efter land 
I följande tabell beskrivs andra e-faktureringsfunktioner som kan hämtas från den globala lagringsplatsen för elektronisk rapportering för att generera elektroniska fakturor.
I RCS kan du hämta de e-faktureringsfunktioner som finns i den här tabellen, ER-konfiguration och tillgängliga e-faktureringsfunktioner.
I Finance kan du aktivera de relaterade funktionsreferenserna på sidan **Parametrar för elektroniskt dokument** om du vill skicka elektroniska fakturor till dessa länder. Mer information finns i avsnittet [Aktivera lands-/regionspecifika e-faktureringsfunktioner](#region-specific) tidigare i det här avsnittet.

| Funktionsnamn                      | beskrivning                                 | ER-konfigurationer                                                                                                  | Inställningar                                                                                                                                                         | Land/region  | Funktionsreferens      |
|-----------------------------------|---------------------------------------------|--------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------|------------------------|
| Österrikiska elektroniska fakturor (AT) | Försäljnings- och projektfakturor för Österrike      | - OIOUBL-försäljningsfaktura <br>- OIOUBL-projektfaktura <br>- OIOUBL-försäljningskreditfaktura <br>- Kreditfaktura för OIOUBL-projekt | - Generering av försäljningsfaktura (AT) <br>- Generering av projektfaktura (AT) <br>- Generering av försäljningskreditfaktura (AT) <br>- Generering av kreditfaktura för projekt (AT)         | Österrike         | EUR-00023              |
| Belgisk elektronisk faktura (BE)   | Försäljnings- och projektfakturor för Belgien      | - UBL försäljningsfaktura BE <br>- UBL projektfaktura BE <br>- UBL kreditfaktura för projekt BE <br>- UBL försäljningskreditfaktura BE | - Generering av försäljningsfaktura (BE)<br>- Generering av projektfaktura (BE) <br>- Generering av försäljningskreditfaktura (BE) <br>- Generering av kreditfaktura för projekt (BE)         | Belgien         | EUR-00023              |
| Dansk elektronisk faktura (DK)    | Försäljnings- och projektfakturor för Danmark      | - OIOUBL-försäljningsfaktura <br>- OIOUBL-projektfaktura <br>- OIOUBL-försäljningskreditfaktura <br>- Kreditfaktura för OIOUBL-projekt | - Generering av försäljningsfaktura (DK) <br>- Generering av projektfaktura (DK) <br>- Generering av försäljningskreditfaktura (DK)<br>- Generering av kreditfaktura för projekt (DK)         | Danmark         | EUR-00023<br> DK-00001 |
| Holländsk elektronisk faktura (NL)     | Försäljnings- och projektfakturor för Nederländerna  | - UBL försäljningsfaktura NL <br>- UBL projektfaktura NL <br>- UBL försäljningskreditfaktura NL <br>- UBL kreditfaktura för projekt NL | - Generering av försäljningsfaktura (NL) <br> - Generering av projektfaktura (NL) <br> - Generering av försäljningskreditfaktura (NL) <br>- Generering av kreditfaktura för projekt (NL)          | Nederländerna | EUR-00023              |
| Estnisk elektronisk faktura (EE)  | Försäljnings- och projektfakturor för Estland      | - Försäljningsfaktura (EE) <br> - Projektfaktura (EE)                                                                     | - Generering av försäljningsfaktura (EE) <br>- Generering av projektfaktura (EE)                                                                                           | Estland         | EUR-00023              |
| Finsk elektronisk faktura (FI)   | Försäljnings- och projektfakturor för Finland      | - Försäljningsfaktura (FI) <br>- Generering av projektfaktura (FI)                                                          | - Generering av försäljningsfaktura (FI) <br>- Generering av projektfaktura (FI)                                                                                           | Finland         | EUR-00023              |
| Fransk elektronisk faktura (FR)    | Försäljnings- och projektfakturor för Frankrike    | - UBL försäljningsfaktura FR <br> - UBL projektfaktura FR <br> - UBL försäljningskreditfaktura FR <br>- UBL kreditfaktura för projekt FR | - Generering av försäljningsfaktura (FR) <br> - Generering av projektfaktura (FR) <br>- Generering av försäljningskreditfaktura (FR) <br>- Generering av kreditfaktura för projekt (FR)         | Frankrike          | EUR-00023              |
| Tysk elektronisk faktura (DE)    | Försäljnings- och projektfakturor för Tyskland      |- Försäljningsfaktura (DE) <br> - Projektfaktura <DE>                                                                     | - Generering av försäljningsfaktura (DE) <br>- Generering av projektfaktura (DE)                                                                                           | Tyskland         | EUR-00023              |
| Norsk elektronisk faktura (NO) | Försäljnings- och projektfakturor för Norge       | - OIOUBL-försäljningsfaktura <br>- OIOUBL-projektfaktura <br>- OIOUBL-försäljningskreditfaktura <br>- Kreditfaktura för OIOUBL-projekt | - Generering av försäljningsfaktura (NO) <br>- Generering av projektfaktura (NO) <br>- Generering av försäljningskreditfaktura (NO) <br>- Generering av kreditfaktura för projekt (NO)          | Norge          | EUR-00023<br> NO-00010 |
| Spansk elektronisk faktura (ES)   | Försäljnings- och projektfakturor för Spanien        | - Försäljningsfaktura (ES) <br>- Projektfaktura (ES)                                                                     | - Generering av försäljningsfaktura (ES) <br>- Generering av projektfaktura (ES)                                                                                           | Spanien           | EUR-00023 <br>ES-00025 |
| Italiensk elektronisk faktura (IT)   | Försäljnings- och projektfakturor för Italien        | - (Förhandsgranskning) försäljningsfaktura (IT) <br> - Projektfaktura (IT)                                                           | - Försäljningsfaktura <br> - Projektfaktura                                                                                                                           | Italien           | EUR-00023 <br>IT-00036 |
| PEPPOL elektronisk faktura         | Generering av PEPPOL försäljnings- och projektfaktura | - PEPPOL-försäljningsfaktura <br>- PEPPOL-projektfaktura <br>- PEPPOL-försäljningskreditfaktura <br> - Kreditfaktura för PEPPOL-projekt | - Generering av PEPPOL-försäljningsfaktura <br>- Generering av PEPPOL-projektfaktura <br>- Generering av PEPPOL-försäljningskreditfaktura <br>- Generering av PEPPOL-kreditfaktura för projekt |                 | EUR-00023              |


## <a name="electronic-invoice-processing-in-finance-and-supply-chain-management"></a>Elektronisk fakturabearbetning i Finance och Supply Chain Management

Under bearbetningen ska du utföra följande uppgifter:

1. Skicka ett affärsdokument (faktura) via tillägget för elektronisk fakturering.
2. Visa körningsloggar för överföring.

### <a name="submit-business-documents"></a>Skicka affärsdokument

Under den vanliga sändningsprocessen är kommunikationen mellan klienten och tillägget för elektronisk fakturering dubbelriktad. Syftet är att utföra två huvuduppgifter när elektroniska dokument lämnas in:

1. Skicka alla elektroniska dokument som väntar på att skickas från Finance och som har korrekt status för överföring och uppfyller urvalskriterierna.
2. Importera, till Finance, det svar som tillägget elektronisk fakturering returnerar för tidigare skickade elektroniska dokument. Efter importen tolkas svaren och affärsdokumentens status uppdateras därefter.

Du kan skicka affärsdokument antingen manuellt eller utifrån dina tidsplaneringskrav.

1. Gå till **organisationsadministration \> periodisk \> elektroniska dokument \> skicka elektroniska dokument**.
2. Ställ alltid in alternativet **Skicka dokument igen** till **Nej** för första inlämningen av ett dokument. Om du måste skicka ett dokument på nytt via tjänsten ställer du in det här alternativet på **Ja**.
3. På snabbfliken **Poster att inkludera** välj **Filter** för att öppna dialogrutan **fråga** där du kan skapa en fråga för att välja dokument för överföring.

![Skicka in dialogrutan elektroniska dokument](media/e-invoicing-services-get-started-submission-form.png)

### <a name="filter-query"></a>Filterfråga

1. I dialogrutan **Förfrågan** på fliken **Område** anger du filterkriterier genom att använda fälten **Register**, **Härlett register**, **Fält** och **Kriterier**.
2. Välj **Lägg till** om du vill lägga till så många ytterligare kriterier som du behöver för att välja affärsdokumenten.

    ![Ställa in kriterier för överföringsfilter](media/e-invoicing-services-get-started-set-up-submission-filter-criteria.png)

3. Välj **OK** för att stänga dialogrutan **Förfrågning**.
4. Välj **OK** om du vill skicka de valda affärsdokumenten till tillägget elektronisk fakturering.

    > [!NOTE]
    > Under ditt första försök att skicka ett dokument via tjänsten uppmanas du att bekräfta anslutningen med tillägget för elektronisk fakturering. Välj **Klicka här för att ansluta till tjänsten inlämning av elektroniska dokument**.
    >
    > ![Meddelanderuta för tjänsten anslut till elektronisk dokument](media/e-invoicing-services-get-started-dialog-form-connect-e-Invoicing-services.png)
    >
    > Om anslutningen lyckas får du ett bekräftelsemeddelande.
    >
    > ![Bekräftelse av anslutning till tillägget för elektronisk fakturering](media/e-invoicing-services-get-started-confirmation-connection-e-invoicing-services.png)

5. Stäng dialogrutan.

> [!NOTE]
> Efter varje överföring visar åtgärdscentret antalet överförda dokument.
>
> ![Åtgärdscentermeddelanden](media/e-invoicing-services-get-started-view-action-center-messages.png)

### <a name="submission-by-batch"></a>Överföring per batch

I stället för att skicka dokument manuellt kan du automatisera överföringsprocessen och köra den i bakgrunden, baserat på en konfigurerad frekvens för batch-körning.

1. I dialogrutan **Skicka elektroniska dokument** på snabbfliken **Kör i bakgrunden** ange **Batch-bearbetning** till **Ja**.
2. På fliken **återkommande**, konfigurera frekvensen för batchbearbetning.

![Ställa in överföring per batch](media/e-invoicing-services-get-started-set-up-submission-batch.png)

### <a name="view-all-submission-logs"></a>Visa alla överföringsloggar

1. Gå till **organisationsadministration \> periodisk \> elektroniska dokument \> logg för inlämning av elektroniska dokument**.
2. I fältet **dokumenttyp** välj den dokumenttyp som du vill filtrera efter.

    ![Välja dokumenttyp för att visa överföringsloggar för](media/e-invoicing-services-get-started-select-document-type-for-viewing-submission-log.png)

    > [!IMPORTANT]
    > Värdet som visas i kolumnen **överföringsstatus** representerar den status som är relaterad till slutförandet av själva överföringsprocessen. Det anger om flödet för åtgärder som har konfigurerats i RCS kördes fram till slutet, oavsett om det elektroniska dokumentet godkändes eller avvisades. Värdet i kolumnen **Överföringsstatus** representerar inte status för det överförda dokumentet. Du kan visa status för det inskickade dokumentet (dvs. om dokumentet har godkänts eller avvisats) på snabbfliken **bearbetar åtgärdslogg** i informationen om överföringsloggen, som beskrivs härnäst.

3. I åtgärdsfönstret, välj **Frågor \> Överföringsinformation**.
4. Visa information om överföringsloggen.

    ![Information om överföringsloggen](media/e-invoicing-services-get-started-view-submission-log-form.png)

Resultaten som visas i överföringsloggen beror på hur funktionen för e-fakturering har ställts in i RCS. Oavsett inställningen har överföringsloggen emellertid alltid tre snabbflikar:

- **Bearbeta åtgärder** – på den här snabbfliken visas körningsloggen för de åtgärder som är konfigurerade i funktionsversionen som ställdes in i RCS. Kolumnen **Status** visar om åtgärden har utförts utan fel.
- **Åtgärdsfiler** – på den här snabbfliken visas de mellanliggande filer som genererades under körningen av åtgärderna. Du kan välja **vy** om du vill hämta filen och visa dess innehåll.
- **Bearbeta åtgärdslogg** – på den här snabbfliken visas resultaten av kommunikationen mellan tillägget för elektronisk fakturering och målwebbtjänsten. Det visar också vad som har returnerats av bearbetningen av webbtjänst.

## <a name="related-topics"></a>Relaterade ämnen

- [Tillägg för elektronisk fakturering: översikt](e-invoicing-service-overview.md)
- [Kom igång med tillägget elektronisk fakturering för Brasilien](e-invoicing-bra-get-started.md)
- [Kom igång med tillägget elektronisk fakturering för Mexiko](e-invoicing-mex-get-started.md)
- [Kom igång med tillägget elektronisk fakturering för Italien](e-invoicing-ita-get-started.md)
- [Ställ in tillägg för elektroniska fakturor](e-invoicing-setup.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]