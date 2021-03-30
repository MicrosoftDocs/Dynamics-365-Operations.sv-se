---
title: Ställ in tillägg för elektroniska fakturor
description: I det här avsnittet beskrivs hur du ställer in tillägget Elektroniska fakturor i Microsoft Dynamics 365 Finance och Dynamics 365 Supply Chain Management.
author: gionoder
manager: AnnBe
ms.date: 09/22/2020
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
ms.openlocfilehash: 5821a512b2beaf7ba2b8015355f04562f7b3b38a
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5209956"
---
# <a name="set-up-the-electronic-invoicing-add-on"></a>Ställ in tillägg för elektroniska fakturor

[!include [banner](../includes/banner.md)]


Installation av funktionen för tillägget elektronisk fakturering är processen att skapa den konfiguration som krävs genom RCS-miljön (Regulatory Configuration Services) och publicera den konfigurationen på tilläggsservern för elektronisk fakturering. Med hjälp av installationsprogrammet kan du skapa de konfigurerbara reglerna som gör det möjligt för tillägget Elektronisk fakturering att använda ett säkert protokoll via Internet för att kommunicera och utbyta data med en tredje parts enhet via webbtjänster.

Konfigureringsmöjligheter är beroende av formatkonfigurationen för elektronisk rapportering (ER) som ett sätt att skapa och ta emot innehåll som skickas och tas emot via digitala filer. Den använder också samordningen av kommunikationsåtgärder för att skicka förfrågningar till och ta emot svar från tredje parts webbtjänster utan att behöva skriva kod.

## <a name="overview"></a>Översikt

"Funktionen tillägg för elektronisk fakturering är det allmänna namnet för resursen som är konfigurerad och publicerad för att använda tilläggsservern för elektronisk fakturering. Inställningen av funktionen kombinerar bland annat användningen av ER-konfigurationsformat för att skapa konfigurerbara export- och importfiler och användningen av åtgärder och åtgärdsflöden för att möjliggöra skapandet av konfigurerbara regler för att skicka förfrågningar , importera svar och analysera svarsinnehållet.

Följande bild visar huvudkomponenterna i funktionen tillägg för elektronisk fakturering.

![Funktionen tillägg för elektronisk fakturering: översikt](media/e-Invoicing-services-feature-setup-Overview-e-Invoicing-feature.png)

På grund av variationer i fakturaformat och åtgärdsflöden kan funktionsinställningarna variera beroende på land eller region eller efter affärsbehov.

## <a name="set-up-the-electronic-invoicing-add-on-feature"></a>Ställ in funktionen tillägg för elektroniska fakturor

Installationsprocessen måste utföras i din RCS-miljö. Följ de här stegen om du vill skapa en ny funktion för tillägg för elektronisk fakturering.

1. Logga in på RCS-miljön.
2. I arbetsytan **globaliseringsfunktioner** i avsnittet **Funktioner**, välj panelen **Tillägg för elektroniska fakturor**.
3. På sidan **Funktioner för tillägg för elektronisk fakturering** välj **Importera** för att importera konfiguration av ER-datamodell från den globala databasen.
4. Välj **Lägg till** om du vill skapa en funktion för tillägg för elektronisk fakturering. Du kan antingen skapa funktionen från början eller härleda den från en befintlig funktion för tillägg för elektronisk fakturering.

    ![Lägg till en funktion för tillägg för elektronisk fakturering](media/e-Invoicing-services-feature-setup-Select-Add-e-Invoicing-feature.png)

> [!NOTE]
> När du skapar en ny funktion för tillägg för elektronisk fakturering har den ett versionsnummer och standardstatus är inställd på **utkast**.

### <a name="configurations"></a>Konfigurationer

Konfigurationer innehåller de ER-formatkonfigurationer som krävs för omvandling och för att skapa de filer som ska bytas ut under kommunikationen med webbtjänster från andra leverantörer. En funktion för tillägg för elektronisk fakturering kan ha så många ER-filformatkonfigurationer som behövs, baserat på den tekniska specifikation som tillhandahålls av webbtjänstleverantören.

Följ de här stegen om du vill lägga till ER-format till en funktion för tillägg för elektronisk fakturering.

1. På sidan **Funktioner för tillägg för elektronisk fakturering** på fliken **Konfigurationer** välj **Lägg till** för att lägga till ER-filformatkonfigurationer för funktion för tillägg för elektronisk fakturering.

    ![Lägg till konfigurationer för funktion för tillägg för elektronisk fakturering](media/e-Invoicing-services-feature-setup-Select-Add-e-Invoicing-feature-Configurations.png)

    > [!NOTE]
    > När du skapar en funktion för tillägg för elektronisk fakturering från början måste du lägga till alla konfigurationer för ER-filformat manuellt. När du härleder en funktion för tillägg för elektronisk fakturering från en befintlig funktion, skapas konfigurationerna för ER-filformat automatiskt eftersom de ärvs från den ursprungliga funktionen för tillägg för elektronisk fakturering.

2. Välj **Redigera** om du vill öppna sidan **Formatdesigner**, där du kan redigera konfigurationen för ER-filformat.

    ![Redigera konfigurationer för funktion för tillägg för elektronisk fakturering](media/e-Invoicing-services-feature-setup-Select-Edit-e-Invoicing-feature-Configurations.png)

    > [!NOTE]
    > När du redigerar formatet är status för konfigurationsversionen inställd på **utkast**.

3. Använd sidan **Formatdesigner** om du vill ändra konfigurationen av filformat. Mer information finns i [Skapa konfigurationer för elektroniska dokument](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/electronic-reporting-configuration).

    ![Formatdesignersida](media/e-Invoicing-services-feature-setup-ER-Format-designer.png)

### <a name="feature-setups"></a>Funktionsinställningar

Funktionsinställningar inkapslar reglerna för kommunikation och säkerhet med en tredje parts webbtjänst. En funktion för tillägg för elektronisk fakturering kan ha så många funktionsinställningar som krävs, baserat på den affärsregel du vill uppnå.

Följ de här stegen om du vill lägga funktionsinställningar till en funktion för tillägg för elektronisk fakturering.

1. På sidan **Funktioner för tillägg för elektronisk fakturering** på fliken **Inställningar** välj **Lägg till** för att lägga till funktionsinställningar till funktionen för tillägg för elektronisk fakturering.

    ![Lägg till inställning av en funktion för tillägg för elektronisk fakturering](media/e-Invoicing-services-feature-setup-Select-Add-e-Invoicing-feature-Setups.png)

    > [!NOTE]
    > När du skapar en funktion för tillägg för elektronisk fakturering från början måste du lägga till alla funktionsinställningar som du behöver. När du härleder en funktion för tillägg för elektronisk fakturering från en befintlig funktion, skapas alla funktionsinställningar automatiskt eftersom de ärvs från den ursprungliga funktionen för tillägg för elektronisk fakturering.

2. Välj **Redigera** om du vill redigera inställning av funktionsversion.

    ![Redigera inställning av en funktion för tillägg för elektronisk fakturering](media/e-Invoicing-services-feature-setup-Select-Edit-e-Invoicing-feature-Setups.png)

3. Använd sidan **Inställning av funktionsversion** för att konfigurera åtgärder, tillämpningsreglerna och variabler.

    ![Åtgärder, tillämpningsreglerna och variabler](media/e-Invoicing-services-feature-setup-View-Actions-Applicability-Rules-Variables.png)

### <a name="actions"></a>Åtgärder

Åtgärder är en fördefinierad lista med operationer som körs i sekventiell ordning. Den här listan representerar fördelningen av steg som krävs för fullständig körning av funktionen tillägg för elektronisk fakturering. Åtgärderna kan inkapslas i samma funktionen tillägg för elektronisk fakturering, kommunikationen i båda riktningarna: skickar en begäran om mål och tar emot ett svar och tolkar dess innehåll.

Varje åtgärd innehåller en fördefinierad lista med parametrar som krävs för att åtgärden ska kunna utföras. Ytterligare parametrar kan valfritt anges.

#### <a name="actions-fasttab"></a>Snabbfliken Åtgärder

På sidan **Inställning av funktionsversion** på fliken **Åtgärder** på snabbfliken **Åtgärder** följer du en eller båda stegen för att hantera åtgärder:

- Välj **Ny** eller **Ta bort** om du vill lägga till nya åtgärder eller ta bort befintliga åtgärder.
- Välj **Upp** eller **Nedåt** om du vill flytta valda åtgärder uppåt eller nedåt i rutnätet och därför ändra ordningen som de körs i. Åtgärderna körs i den ordning som de visas i rutnätet, uppifrån och ned.

![Hantera åtgärder](media/e-Invoicing-services-feature-setup-Manage-Actions.png)

Följande register beskriver de fält som är tillgängliga i snabbfliken **Åtgärder**.

| Fält        | beskrivning |
|--------------|-------------|
| Åtgärd       | Det finns åtta fördefinierade åtgärder:<ul><li><strong>Signera dokument</strong></li><li><strong>FileStoreActionName</strong></li><li><strong>Transformera dokument</strong></li><li><strong>Behandla svar</strong></li><li><strong>Anropa REST-webbtjänst</strong></li><li><strong>Anropa mexikanska PAC-tjänsten</strong></li><li><strong>Ring brasilianska SEFAZ-tjänsten</strong></li><li><strong>Ring upp italienska SDI-tjänsten</strong></li></ul> |
| Namn på åtgärd  | Namnet på åtgärden och dess körningsordning. |
| beskrivning  | En beskrivning av åtgärden. |
| Gör det möjligt med nya försök | En markerad kryssruta anger att åtgärden kan utföras på nytt om det tidigare försöket misslyckas. |
| Försök med åtgärden igen | Om det uppstår ett nytt försök kommer åtgärden att starta om från. Det nya försöket slutar sedan med den aktuella åtgärden (inklusive nytt försök). För åtgärder som har dem anger parametrarna **Minsta undantag** and **Högsta undantag** anger minsta antal och maximala antal försök. |

#### <a name="parameters-fasttab"></a>Snabbfliken parametrar

På snabbfliken **Parametrar** visas parametrarna för den åtgärd som är vald på snabbfliken **Åtgärder**.

![Snabbfliken parametrar](media/e-Invoicing-services-feature-setup-View-Actions-Parameters.png)

Följande register beskriver de fält som är tillgängliga i snabbfliken **Parametrar**.

| Fält       | beskrivning |
|-------------|-------------|
| Namn        | En fördefinierad lista med parametrar. Mer information finns i avsnittet [lista över parametrar per åtgärd](#list-of-parameters-by-action). |
| beskrivning | En beskrivning av parametern. |
| Värde       | Värdet för parametern. |

#### <a name="list-of-parameters-by-action"></a>Lista över parametrar efter åtgärd

Vilka parametrar som är tillgängliga varierar beroende på vilken åtgärd som är vald på snabbfliken **Åtgärder**.

###### <a name="action-sign-document"></a>Åtgärd: Signera dokument

| Parameter                             | beskrivning |
|---------------------------------------|-------------|
| Infil                            | Dokumentfilen med indata-XML som måste signeras med hjälp av en elektronisk signatur. |
| Certifikatnamn                      | Namnet på certifikatet i arkivet. |
| Signaturtyp                        | Vilken typ av signatur som ska användas. |
| Namn på metodsignatur                 | Namnet på den metodsignatur som används för att skapa en elektronisk signatur. |
| Namn på Digest-metod                    | Den Digest-metod som används för att generera en Digest-sträng i den digitala signaturen. |
| Namn på kanonisk metod          | Detta är den kanoniska metod som används för att beräkna hash-signatur. |
| Namn på referensattribut              | Namnet på attributet som anger var referens-ID ska infogas i signaturelementet. |
| Namn på element som ska signeras               | Namnet på XML-elementet i dokumentet som måste signeras med hjälp av en elektronisk signatur. Om inget element anges, signeras roten för dokumentet. |
| Namn på element som ska infoga signatur   | Namnet på det XML-element där en genererad digital signatur ska infogas. Om inget element anges, infogas signaturen i dokumentets rot. |
| XLST-fil med Digest-transformering       | XSLT-filen (Extensible Stylesheet Language Transformations) som innehåller Digest-omvandlingsregler för generering av Digest-strängen för en elektronisk signatur. |
| Sökväg till infogning av Digest-sträng          | Sökvägen i **\<elementName\> .\<Attribute.Path\>** format, för platsen där den genererade Digest-strängen måste infogas. |
| Plats för certifikatnummer           | Namnet på elementet och attributet där certifikatnumret ska placeras. |
| Plats för certifikatdata          | Namnet på elementet och attributet där certifikatdata (base64) måste infogas. |
| Certifikatnumret är i ASCII-format | Ett värde som anger om certifikatnummer är kodat i ASCII-format. |

###### <a name="action-filestoreactionname"></a>Åtgärd: FileStoreActionName

| Parameter  | beskrivning |
|------------|-------------|
| Infil | Den indatafil som ska lagras. |

###### <a name="action-transform-document"></a>Åtgärd: transformera dokument

| Parameter                       | beskrivning |
|---------------------------------|-------------|
| Infil                      | Källfilen som innehåller de data som måste köras för åtgärden. |
| Riktning                       | Ett värde som anger om import- eller exportformatet ska användas. |
| Konfigurations-ID                | Formatet som ska köras. |
| Konfigurationsversion           | Om ingen konfigurations version anges kommer den senaste versionen att användas. |
| Konfigurationsintegreringspunkt | Källfilen som tillhandahåller data till rapportkörningen. |

###### <a name="action-process-response"></a>Åtgärd: Behandla svar

| Parameter                    | beskrivning |
|------------------------------|-------------|
| Infil                   | Det svar som ska analyseras. |
| Lista med rapporteringskonfiguration | En lista med konfigurationer som används för att tolka svar. |

###### <a name="action-call-rest-web-service"></a>Åtgärd: Anropa REST-webbtjänst

| Parameter                   | beskrivning |
|-----------------------------|-------------|
| Webbtjänst-URL             | Den URL som begäran ska skickas till. |
| Timeout för webbegäran         | Maximal tid (i millisekunder) att vänta på ett webbtjänstsvar. |
| Begär åtgärdstyp      | Den typ av HTTP-begäran som ska åtgärdas (t.ex. **GET**, **POST** eller **DELETE**). |
| Certifikatnamn           | Certifikatnamn. |
| Kodning för svarstext      | Den förväntade kodningen av HTTP-svaret så att den kan avkodas korrekt. |
| Innehållstyp för HTTP-begäran   | Rubrik för innehållstypen i HTTP-begäran. |
| Innehållstext för HTTP-begäran   | HTTP begärandetext. (Brödtexten kan vara tom.) |
| Frågevärden för HTTP-parametrar | Frågevärden för parameter som används för att fylla URL:en med variabelparametrar. |
| Begär flöde               | Flödesvägen för HTTP-begäran. Variabelparametrarna kan skrivas i notationen **\{paramName\}**. Här följer ett exempel: **"api/{id}/submit"**. |
| Flödesparameterlista        | De flödesparametrar i nyckelvärdes notation som används för att infoga variabler i flödet. |
| Anpassade HTTP-huvuden         | De anpassade HTTP-huvuden som ska läggas till i begäran. |
| HTTP-begäran cookies        | En lista med cookies i nyckelvärdes notation som ska placeras i HTTP-cookies huvudbegäran. |
| Säkerhetsprotokoll           | Det säkerhetsprotokoll som ska användas för HTTP-begäran för att kommunicera med servern. (Som standard används Transport Layer Security \[TLS\] 1.2.) |

###### <a name="action-call-mexican-pac-service"></a>Åtgärd: Anropa mexikanska PAC-tjänsten

| Parameter                | beskrivning |
|--------------------------|-------------|
| Infil               | Filen som innehåller XML-data som ska skickas till webbtjänsten som en metod för parameterinmatning. |
| URL-adress              | Webbtjänstadressen (slutpunkten). |
| Namn på webbmetod (åtgärd) | Namnet på den webbmetod (åtgärd) som måste köras. |
| Intyg             | Den certifikatkedja som krävs för klientautentisering av webbtjänsten. Klientcertifikatet bör vara det sista certifikatet i kedjan. Rot- och mellanliggande certifikat måste först anges. |
| Timeout för webbegäran      | Maximal tid (i millisekunder) att vänta på ett webbtjänstsvar. |
| Återförsöksintervall           | Intervallet mellan försöken att anropa och ta emot ett svar från webbtjänsten. Om inget intervall anges görs inga fler försök efter det att det första anropet misslyckas. |
| Antal nya försök              | Det maximala antalet återförsök som försöker anropa och hämta ett svar från webbtjänsten. |
| Försök igen till               | Den maximala tid (i millisekunder) som nya försök att anropa kan fortsätta. |
| Minsta undantag         | Minsta undantagsfrekvens för exponentiell beräkning av återförsöksintervall. |
| Högsta undantag         | Högsta undantagsfrekvens för exponentiell beräkning av återförsöksintervall. |
| Säkerhetsprotokoll        | Det säkerhetsprotokoll som ska användas för HTTP-begäran för att kommunicera med servern. (Som standard används TLS 1.2.) |

###### <a name="action-call-brazilian-sefaz-service"></a>Åtgärd: Anropa brasilianska SEFAZ-tjänsten

| Parameter                | beskrivning |
|--------------------------|-------------|
| Infil               | Filen som innehåller XML-data som ska skickas till webbtjänsten som en metod för parameterinmatning. |
| URL-adress              | Webbtjänstadressen (slutpunkten). |
| Namn på webbmetod (åtgärd) | Namnet på den webbmetod (åtgärd) som måste köras. |
| Intyg             | Den certifikatkedja som krävs för klientautentisering av webbtjänsten. Klientcertifikatet bör vara det sista certifikatet i kedjan. Rot- och mellanliggande certifikat måste först anges. |
| Timeout för webbegäran      | Maximal tid (i millisekunder) att vänta på ett webbtjänstsvar. |
| Återförsöksintervall           | Intervallet mellan försöken att anropa och ta emot ett svar från webbtjänsten. Om inget intervall anges görs inga fler försök efter det att det första anropet misslyckas. |
| Antal nya försök              | Det maximala antalet återförsök som försöker anropa och hämta ett svar från webbtjänsten. |
| Försök igen till               | Den maximala tid (i millisekunder) som nya försök att anropa kan fortsätta. |
| Minsta undantag         | Minsta undantagsfrekvens för exponentiell beräkning av återförsöksintervall. |
| Högsta undantag         | Högsta undantagsfrekvens för exponentiell beräkning av återförsöksintervall. |
| Säkerhetsprotokoll        | Det säkerhetsprotokoll som ska användas för HTTP-begäran för att kommunicera med servern. (Som standard används TLS 1.2.) |

###### <a name="action-call-italian-sdi-service"></a>Åtgärd: Anropa italienska SDI-tjänsten

| Parameter                | beskrivning |
|--------------------------|-------------|
| Infil               | Filen som innehåller XML-data som ska skickas till webbtjänsten som en metod för parameterinmatning. |
| URL-adress              | Webbtjänstadressen (slutpunkten). |
| Namn på webbmetod (åtgärd) | Namnet på den webbmetod (åtgärd) som måste köras. |
| Intyg             | Den certifikatkedja som krävs för klientautentisering av webbtjänsten. Klientcertifikatet bör vara det sista certifikatet i kedjan. Rot- och mellanliggande certifikat måste först anges. |
| Timeout för webbegäran      | Maximal tid (i millisekunder) att vänta på ett webbtjänstsvar. |
| Återförsöksintervall           | Intervallet mellan försöken att anropa och ta emot ett svar från webbtjänsten. Om inget intervall anges görs inga fler försök efter det att det första anropet misslyckas. |
| Antal nya försök              | Det maximala antalet återförsök som försöker anropa och hämta ett svar från webbtjänsten. |
| Försök igen till               | Den maximala tid (i millisekunder) som nya försök att anropa kan fortsätta. |
| Minsta undantag         | Minsta undantagsfrekvens för exponentiell beräkning av återförsöksintervall. |
| Högsta undantag         | Högsta undantagsfrekvens för exponentiell beräkning av återförsöksintervall. |
| Säkerhetsprotokoll        | Det säkerhetsprotokoll som ska användas för HTTP-begäran för att kommunicera med servern. (Som standard används TLS 1.2.) |

### <a name="applicability-rules"></a>Tillämplighetsregler

Med tillämplighetsregler kan du skapa logiska regler som bestämmer användningskontexten för funktionsinställningarna. Således bestämmer matchningen mellan det sammanhang som ges av affärsdokumentet som skickas för behandling, tillsammans med kriterierna för tillämpbarhetsregeln vilken tilläggsfunktion för elektronisk fakturering som används för att behandla den inlämningen.

#### <a name="set-up-applicability-rules"></a>Ställ in tillämplighetsregler

1. På sidan **Inställningar av funktionsversion** på fliken **Tillämplighetsregler** välj **Ny** för att lägga till en tillämplighetsregel.

    ![Hantera tillämplighetsregler](media/e-Invoicing-services-feature-setup-Manage-Actions-Applicability-rules.png)

2. I rutnätet väljer du de satser som ska grupperas.
3. Välj **Gruppsats**.

    ![Grupperingssatser](media/e-Invoicing-services-feature-setup-Manage-Applicability-rules-Group-clause.png)

    När satser grupperas läggs en ny kolumn till i rutnätet. Den här kolumnen anger den logiska operatorn för grupperade satser.

    ![Logisk operator för grupperade satser](media/e-Invoicing-services-feature-setup-Manage-Applicability-rules-Group-criterias.png)

Om du vill dela upp grupperade satser markerar du de grupperade satserna som ska delas upp och väljer sedan **dela upp sats**.

![Dela upp satser](media/e-Invoicing-services-feature-setup-Manage-Applicability-rules-UnGroup-criterias.png)

> [!NOTE]
> När du delar upp en sats ska du alltid börja med den innersta grupperingsnivån.

Följande register beskriver de fält som är tillgängliga på fliken **Tillämplighetsregler**.

| Fält         | beskrivning |
|---------------|-------------|
| Och/eller        | Den logiska operatorn. |
| Fält         | Det fält som ska användas för att skapa regeln. |
| Typ av operator | Typen av operator:<ul><li>Lika</li><li>Inte lika med</li><li>Större än/mindre än</li><li>Större än eller lika med/mindre än eller lika med</li><li>Innehåller</li><li>Börja med</li></ul> |
| Värde         | Kriteriet för regeln. |

### <a name="variables"></a>Variabler

Du kan skapa variabler och sedan använda dem som indatavärde för en parameter för en viss åtgärd. Du kan också använda dem för att utbyta, mellan tillägget Elektronisk fakturering och klienten, information som är resultatet av att en viss åtgärd utförs som en del i flödet av överföringar.

#### <a name="set-up-variables"></a>Ställ in variabler

- På sidan **inställning av funktionsversion** på fliken **variabler** välj **ny** eller **ta bort** för att hantera variabler.

    ![Hantera variabler](media/e-Invoicing-services-feature-setup-Manage-Variables.png)

Följande register beskriver de fält som är tillgängliga på fliken **variabler**.

| Fält       | beskrivning |
|-------------|-------------|
| Namn        | Namn på variabeln. |
| beskrivning | En kort beskrivning av variabeln. |
| Typ        | Typen av variabeln:<ul><li><strong>Konstant</strong> – innehållet i variabeln är fast.</li><li><strong>Från klient</strong> – variabelns innehåll hämtas från Microsoft Dynamics 365-klienten när överföringsprocessen kördes.</li><li><strong>Till klient</strong> – variabelns innehåll görs tillgänglig för import av Microsoft Dynamics 365-klienten när överföringsprocessen kördes.</li></ul> |
| Datatyp   | Datatyp för variabeln:<ul><li>Booleskt</li><li>Datum</li><li>Antal</li><li>UUID</li><li>Sträng</li><li>Fil</li></ul> |
| Värde       | Variabelns värde eller namnet på åtgärden som anger variabelns värde. |

### <a name="validate-the-feature-setup"></a>Validera funktionsinställningarna

- På sidan **Inställning av funktionsversion** i åtgärdsfönstret väljer du **validera** för att validera inställning av funktionsversion.

   ![Klicka på knappen Validera](media/e-Invoicing-services-feature-setup-Select-Validate-Button.png)

Vid valideringen kontrolleras konsekvensen i hela konfigurationen. Om till exempel en specifik parameter för en åtgärd är obligatorisk men värdet fortfarande är tomt, identifierar valideringen den här inkonsekvensen och du får en varning.

## <a name="environments"></a>Miljöer

En miljö för tillägg för elektronisk fakturering måste vara kopplad till funktionen för tillägg för elektronisk fakturering och aktiveras för den. Miljöer för tillägg för elektronisk fakturering måste skapas och publiceras i förväg, genom konfigurationen av globaliseringsfunktionerna i organisationens RCS-konto.

Följ dessa steg för att aktivera en miljö för tillägg för elektronisk fakturering för funktionen för tillägg för elektronisk fakturering.

1. På sidan **Funktioner för tillägg för elektronisk fakturering** på fliken **Miljöer** välj **Aktivera** för att lägga till miljö för tillägg för elektronisk fakturering.
2. I fältet **gäller från** anger du det datum då den nya miljön ska börja gälla.

![Aktivera en miljö för elektronisk fakturering](media/e-Invoicing-services-feature-setup-Select-Enable-e-Invoicing-feature-Environment.png)

## <a name="organizations"></a>Organisationer

Funktionen tillägg för elektronisk fakturering kan delas mellan flera organisationer.

- På sidan **Funktioner för tillägg för elektronisk fakturering** på **Organisationer** väljer du **Dela med** om du vill lägga till den organisation som du vill dela funktionen tillägg för elektronisk fakturering med.

Om du vill sluta dela funktionen tillägg för elektronisk fakturering med organisationen väljer du **ta bort delning**.

## <a name="versions"></a>Versioner

Versioner hjälper till att styra livscykeln för den elektroniska faktureringsfunktionen genom att hantera dess status. Du kan skapa en ny version av en befintlig tilläggsfunktion för elektronisk fakturering, eller när all konfiguration för tilläggsfunktionen för elektronisk fakturering är klar kan du ändra funktionens status till **Slutför** och sedan **Publicera**.

### <a name="create-a-new-version-of-an-existing-electronic-invoicing-add-on-feature"></a>Skapa en ny version av en befintlig funktion för tillägg för elektronisk fakturering

1. På sidan **Funktioner för tillägg för elektronisk fakturering** i rutnätet till vänster välj funktion för tillägg för elektronisk fakturering.
2. På **versioner** välj **Ny** om du vill lägga till en ny version av funktionen tillägg för elektronisk fakturering.

### <a name="change-the-status-of-the-electronic-invoicing-add-on-feature"></a>Ändra status för den funktionen tillägg för elektronisk fakturering

Följ de här stegen om du vill hantera livscykeln för en funktion för tillägg för elektronisk fakturering.

1. På sidan **Funktioner för tillägg för elektronisk fakturering** i rutnätet till vänster välj funktion för tillägg för elektronisk fakturering.
2. På fliken **versioner** välj **Ändra status** och ändrar sedan statusen från **utkast** till **slutförd**.
3. Du uppmanas att bekräfta att du vill slutföra funktionen tillägg för elektronisk fakturering och alla dess komponenter. Välj **Ja** om du vill bekräfta åtgärden eller **Nej** om du vill avbryta åtgärden.

    > [!NOTE]
    > När du väljer **Ja** ändras statusen för konfigurationsversioner, som är komponenter i funktionen tillägg för elektronisk fakturering automatiskt från **Utkast** till **Slutförd**.

4. Välj **Ändra status** och ändrar sedan statusen från **Slutför** till **Publicera**.
5. Du uppmanas att bekräfta att du vill publicera funktionen tillägg för elektronisk fakturering och alla dess komponenter till den globala databasen. Välj **Ja** om du vill bekräfta åtgärden eller **Nej** om du vill avbryta åtgärden.

    > [!NOTE]
    > När du väljer **Ja** ändras status för konfigurationsversioner automatiskt från **slutförd** till **delad**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]