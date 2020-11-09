---
title: Kom igång med tillägget elektronisk fakturering för Brasilien
description: Det här avsnittet innehåller information som hjälper dig att komma igång med tillägget elektronisk fakturering för Brasilien i Microsoft Dynamics 365 Finance och Dynamics 365 Supply Chain Management.
author: gionoder
manager: AnnBe
ms.date: 09/04/2020
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
ms.openlocfilehash: fb3ec2d60875d7a0747d64b397aafaa0a3d26348
ms.sourcegitcommit: d6250ee5ced43be39e789324a895fd1c07178935
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/19/2020
ms.locfileid: "4039879"
---
# <a name="get-started-with-the-electronic-invoicing-add-on-for-brazil"></a>Kom igång med tillägget elektronisk fakturering för Brasilien 

[!include [banner](../includes/banner.md)]


> [!IMPORTANT]
> Det elektroniska faktureringstillägget för Brasilien stöder för närvarande inte alla funktioner som är tillgängliga i integrationen av skattedokument som är inbyggd i Microsoft Dynamics 365 Finance och Dynamics 365 Supply Chain Management.

Det här avsnittet innehåller information som hjälper dig att komma igång med tillägget elektronisk fakturering för Brasilien. Den guidar dig genom de konfigurationssteg som är beroende av RCS (Regulatory Configuration Services) och i Finance och Supply Chain Management. Det vägleder dig genom processen att skicka ett NF-e skattedokument (elektroniskt skattedokument modell 55) via tjänsten och förklarar hur du granskar bearbetningsresultaten och status för skattedokumenten.

## <a name="prerequisites"></a>Förutsättningar

Innan du slutför stegen i det här avsnittet måste du slutföra stegen i [komma igång med tillägget elektronisk fakturering](e-invoicing-get-started.md).

## <a name="rcs-setup"></a>Inställning av RCS

Under RCS-inställningar ska du utföra följande uppgifter:

1. Importera e-faktureringsfunktionen för NF-e skattedokument.
2. Granska filformaten som krävs för att skicka NF-e skattedokument för auktorisering.
3. Granska filformaten som krävs för att begära annullering av en godkänd NF-e.
4. Konfigurera händelsen som krävs för att skicka NF-e skattedokument för auktorisering.
5. Konfigurera händelsen som krävs för att begära annullering av en godkänd NF-e.
6. Tilldela e-faktureringsfunktionen till en miljö för tillägget för elektronisk fakturering.
7. Publicera e-faktureringsfunktionen.

> [!NOTE]
> "e-faktureringsfunktionen" är det allmänna namnet för resursen som är konfigurerad och publicerad för att använda tilläggsservern för elektronisk fakturering. Inställningen av funktionen e-fakturering kombinerar bland annat användningen av konfigurationsformat för elektronisk rapportering (ER) för att skapa konfigurerbara export- och importfiler och användningen av åtgärder och åtgärdsflöden för att möjliggöra skapandet av konfigurerbara regler för att skicka förfrågningar , importera svar och analysera svarsinnehållet.

## <a name="import-the-e-invoicing-feature"></a>Importera e-faktureringsfunktion

1. Logga in på RCS-kontot
2. I arbetsytan **globaliseringsfunktioner** i avsnittet **Funktioner** , välj panelen **e-fakturering**.
3. På sidan **e-faktureringsfunktioner** väljer du **Importera** för att importera e-faktureringsfunktion för NF-e-skattedokument från den globala databasen.

    ![Importera-knapp](media/e-Invoicing-services-get-started-BRA-Select-Import-e-Invoicing-feature.png)

4. Välj funktionen för NF-e-skattedokumen och välj sedan **Importera**.

    ![Importera NF-e-funktionen](media/e-Invoicing-services-get-started-BRA-Select-Import-NF-e-feature.png)

### <a name="create-a-new-version-of-the-nf-e-fiscal-document-feature"></a>Skapa en ny version av funktionen NF-e-skattedokument

- På sidan **e-faktureringsfunktioner** på fliken **Versioner** välj Ändra status **Ny**.

![Lägger till en ny version av e-faktureringsfunktion](media/e-Invoicing-services-get-started-BRA-Select-New-e-Invoicing-feature-version.png)

### <a name="update-the-configuration-version"></a>Uppdatera konfigurationsversionen

1. På sidan **e-faktureringsfunktioner** på fliken **Konfigurationer** välj **Lägg till** eller **Ta bort** för att hantera konfigurationsversioner (konfigurationer för ER-filformat).

    ![Hantera konfiguration av e-faktureringsfunktioner](media/e-Invoicing-services-get-started-BRA-Manage-e-Invoicing-feature-configurations.png)

    - När du skapar en ny version av funktionen NF-e-skattedokument ärvs alla konfigurationsversioner (ER-filformat) från den senaste versionen.
    - Följande konfigurationsversioner krävs för att skicka NF-e-skattedokument för auktorisering:

        - NFe skicka exportformat
        - NFe import av svarsmeddelande
        - NFe import av fellogg

    - Följande konfigurationsversion krävs för att skicka NF-e-annulleringen:

        - NFe annullera exportformat

2. Välj en konfigurationsversion i listan och välj sedan **Redigera** eller **Visa** för att öppna sidan **Formatdesigner** , där du kan redigera eller visa konfigurationen.

    ![Öppna sidan Formatdesigner](media/e-Invoicing-services-get-started-BRA-Configuration-ER-fomat-designer.png)

3. Använd sidan **Formatdesigner** för att redigera eller visa filkonfigurationerna i ER-format. Mer information finns i [Skapa konfigurationer för elektroniska dokument](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/electronic-reporting-configuration).

    ![Formatdesignersida](media/e-Invoicing-services-get-started-BRA-ER-Format-designer.png)

### <a name="manage-the-e-invoicing-feature-setups"></a>Hantera inställningen för e-faktureringsfunktionen

- På sidan **e-faktureringsfunktioner** på fliken **Inställningar** välj **Lägg till** eller **Ta bort** för att hantera inställningsfunktionen för e-fakturering (t.ex. NF-e-händelser).

![Hantera inställningen för e-faktureringsfunktionen](media/e-Invoicing-services-get-started-BRA-Manage-e-Invoicing-feature-setup.png)

När du skapar en ny version av funktionen för NF-e-skattedokument som härleds från en annan e-faktureringsfunktion, ärvs alla funktionsinställningar (NF-e-händelser) från den senaste versionen.

För att skicka NF-e skattedokument för auktorisering krävs funktionsinställningen **Skicka**.

Om du vill skicka in en NF-e-annullering måste du ställa in en funktion för att **avbryta**.

#### <a name="configure-the-submit-feature-setup"></a>Konfigurera inställningar för överföringsfunktionen

1. På sidan **e-faktureringsfunktioner** på fliken **Inställningar** i kolumnen **Funktionsinställningar** välj **Skicka**.
2. Välj **Redigera**.

    ![Redigera inställningar för e-faktureringsfunktioner](media/e-Invoicing-services-get-started-BRA-Edit-e-Invoicing-feature-setup.png)

3. På sidan **Inställning av funktionsversion** välj fliken **Åtgärder** för att hantera listan med åtgärder.

    ![Fliken åtgärder](media/e-Invoicing-services-get-started-BRA-Select-Actions.png)

4. Granska åtgärderna som krävs för att skicka NF-e för auktorisering.

    | Åtgärds-ID | Namn på åtgärd                  | Åtgärdsbeskrivning                                                |
    |-----------|------------------------------|-------------------------------------------------------------------|
    | 1         | Transformera dokument           | Skapa den NF-e XML-fil som ska skickas.                          |
    | 2         | Signera dokument                | Använd ett digitalt certifikat i XML-filen.                    |
    | 3         | Ring brasilianska SEFAZ-tjänsten | Skicka den signerade XML-filen till webbtjänsterna för auktorisering. |
    | 4         | Behandla svar             | Hämta webbtjänstsvaret.                                     |
    | 5         | Transformera dokument           | Tolka innehållet i den fil som tas emot som ett svar.     |
    | 6         | Transformera dokument           | Skapa XML-filen för att fråga om status för överföringen.    |
    | 7         | Ring brasilianska SEFAZ-tjänsten | Skicka XML-filen som begär status för överföringen.          |
    | 8         | Behandla svar             | Hämta webbtjänstsvaret.                                     |

#### <a name="set-up-the-url-for-sefaz-web-services"></a>Ställ in URL:en för SEFAZ-webbtjänster 

1. På fliken **Inställning av funktionsversion** på fliken **Åtgärder** på snabbfliken **Åtgärder** välj **Anropa brasilianska SEFAZ-tjänsten** (åtgärds-ID **3** ).
2. På snabbfliken **Parametrar** i fältet **Parametrar för URL-adress** anger du webbadressen till SEFAZ-webbtjänsten för NF-e-sändning.
3. På snabbfliken **åtgärder** väljer du **anropa brasilianska SEFAZ-tjänsten** (åtgärds-ID **7** ).
4. På snabbfliken **Parametrar** i fältet **Parametrar för URL-adress** anger du webbadressen till SEFAZ-webbtjänsten för NF-e-sändning.

#### <a name="configure-the-cancellation-feature-setup"></a>Konfigurera inställningar för annulleringsfunktionen

1. På sidan **e-faktureringsfunktioner** på fliken **Inställningar** i kolumnen **Funktionsinställningar** välj **Annullera**.
2. Välj **Redigera**.
3. På sidan **Inställning av funktionsversion** välj fliken **Åtgärder** för att hantera listan med åtgärder.
4. Granska åtgärderna som krävs för att begära annullering av en godkänd NF-e.

    | Åtgärds-ID | Namn på åtgärd                  | Åtgärdsbeskrivning                                               |
    |-----------|------------------------------|------------------------------------------------------------------|
    | 1         | Transformera dokument           | Skapa den NF-e XML-fil för annullering som ska skickas.            |
    | 2         | Signera dokument                | Använd ett digitalt certifikat i XML-filen.                   |
    | 3         | Ring brasilianska SEFAZ-tjänsten | Skicka den signerade XML-filen till webbtjänsterna för annullering. |
    | 4         | Behandla svar             | Hämta webbtjänstsvaret.                                    |

#### <a name="set-up-the-url-for-sefaz-web-services"></a>Ställ in URL:en för SEFAZ-webbtjänster

1. På fliken **Inställning av funktionsversion** på fliken **Åtgärder** på snabbfliken **Åtgärder** välj **Anropa brasilianska SEFAZ-tjänsten** (åtgärds-ID **3** ).
2. På snabbfliken **Parametrar** i fältet **Parametrar för URL-adress** anger du webbadressen till SEFAZ-webbtjänsten för annullering av godkänd NF-e.

### <a name="make-an-e-invoicing-environment-available-and-assign-a-draft-version"></a>Göra en e-faktureringsmiljö tillgänglig och tilldela en utkastversion

1. På sidan **e-faktureringsfunktioner** på fliken **Miljöer** välj Ändra status **Aktivera**.
2. I fältet **miljö** välj miljön.
3. I fältet **gäller från** väljer du det datum då miljön ska börja gälla.
4. Välj **Aktivera**.

![Aktivera en e-faktureringsmiljö](media/e-Invoicing-services-get-started-BRA-Enable-e-Invoicing-environment.png)

### <a name="change-the-status-to-completed"></a>Ändra status till slutförd

1. På sidan **e-faktureringsfunktion** på fliken **Versioner** , välj den version av e-faktureringsfunktionen som har status **Utkast**.
2. Välj **Ändra status \> Slutför**.

### <a name="change-the-status-to-publish"></a>Ändra status till publicera

1. På sidan **e-faktureringsfunktion** på fliken **Versioner** , välj den version av e-faktureringsfunktionen som har status **Slutförd**.
2. Välj **Ändra status \> Publicera**.

![Publicera e-faktureringsfunktion](media/e-Invoicing-services-get-started-BRA-Publish-e-Invoicing-feature.png)

## <a name="set-up-electronic-invoicing-add-on-integration-in-finance-or-supply-chain-management"></a>Ställa in integrering av tillägget elektronisk fakturering i Finance eller Supply Chain Management

Under inställningen ska du utföra följande uppgifter:

1. Sätt på den federala NF-e-funktionen för Brasilien.
2. Importera den specifika ER-datamodell, ER-datamodellmappning och de format som krävs för NF-e skattedokument.
3. Importera ER-konfiguration och ställ in de svarstyper som krävs för att uppdatera status för skattedokumenten efter överföringsprocessen returneras.

### <a name="turn-on-the-nf-e-federal-feature-for-brazil"></a>Sätt på den federala NF-e-funktionen för Brasilien

1. Gå till **organisationsadministration \> inställning \> parametrar för elektroniska dokument**.
2. På fliken **Funktioner** markerar du kryssrutan **Aktivera** i raden för funktionsreferens **BR00053**.

### <a name="import-the-er-data-model-mapping-required-for-nf-e-fiscal-documents"></a>Importera mappningen för ER-datamodell som krävs för NF-e-skattedokument

1. Logga in på Finance.
2. I arbetsytan **elektronisk rapportering** i avsnittet **konfigurationsprovider** väljer du panelen **Microsoft**. Kontrollera att konfigurationsprovidern är **aktiverad**. För information om hur du ställer in en leverantör på **Aktiv** , se [Skapa konfigurationsleverantörer och markera dem som aktiva](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11).
3. Välj **Databaser**.
4. Välj **Global resurs \> Öppna**.
5. Importera konfigurationer **Mappning av skattedokument**.

### <a name="import-er-configurations-and-set-up-the-response-types-for-fiscal-documents"></a>Importera ER-konfigurationer och ställ in svarstyperna för skattedokument

1. I arbetsytan **elektronisk rapportering** i avsnittet **konfigurationsprovider** väljer du panelen **Microsoft**.
2. Välj **Databaser**.
3. Välj **Global resurs \> Öppna**.
4. Importera **import av NF-e fellogg (BR)** , **importformat för NF-e svarsdata (BR)** och **import av NF-e svarsmeddelande (BR)**.
5. Gå till **organisationsadministration \> inställning \> parametrar för elektroniska dokument**.
6. På fliken **Elektroniska dokument** väljer du **Lägg till**.
6. I fältet **Registernamn** ange **skattedokumentets rubrik**.
7. I fältet **Dokumentkontext** väljer du **Kundfaktura kontextmodell - skattedokument kontext**.
8. Välj **svarstyper**.
9. Markera **Ny** och sedan, i fältet **Svarstyp** , markerar du **Svar**.
10. I fältet **Överföringsstatus** välj **Väntande**.
11. I fältet **Modellmappning** välj **Importformat för svarsmeddelande - Modellmappning från svarsmeddelande**.
12. Välj **Spara**.
13. Markera **Ny** och sedan, i fältet **Svarstyp** , markerar du **ResponseData**.
14. I fältet **Överföringsstatus** välj **Väntande**.
15. I fältet **modellmappning** väljer du **NFe importformat för svarsdata – import av svarsdata**.
16. Välj **Spara**.

## <a name="electronic-invoice-processing"></a>Elektronisk fakturabearbetning

Under bearbetningen i Finance ska du utföra följande uppgifter:

1. Skicka ett skattedokument via tillägget för elektronisk fakturering.
2. Visa körningsloggarna för överföring och granska resultaten av bearbetningen.
3. Skicka annullering av ett skattedokument via tillägget för elektronisk fakturering.

### <a name="submit-nf-e-fiscal-documents-for-sefaz-authorization"></a>Skicka NF-e-dokument för SEFAZ-auktorisering 

När du har aktiverat funktionen **Konfigurerbara integreringstillägg för elektronisk fakturering** kan den gamla processen för NF-e skattedokument för auktorisering ( **Exportera/importera NF-e-process** ) kan inte längre användas. Den ersätts med en ny process som kallas **skicka elektroniska dokument**.

> [!NOTE]
> Innan du fortsätter måste du kontrollera att du har ett eller flera kundskattedokument modell 55 som har utfärdats av kundens skattemyndighet. Riktningen för dessa skattedokument måste ställas in på **utgående** och status måste **skapad**. Mer information finns i avsnittet om att [utfärda kundskattedokument (Brasilien)](https://docs.microsoft.com/dynamics365/finance/localizations/tasks/br-00038-issuing-customer-fiscal-document).

1. Gå till **organisationsadministration \> periodisk \> elektroniska dokument \> skicka elektroniska dokument**.
2. Ställ alltid in alternativet **Skicka dokument igen** till **Nej** för första inlämningen av ett dokument. Om du måste skicka ett dokument på nytt via tjänsten ställer du in det här alternativet på **Ja**.
3. På snabbfliken **Poster att inkludera** välj **Filter** för att öppna dialogrutan **fråga** där du kan skapa en fråga för att välja dokument för överföring.
4. På fliken **Intervall** klickar du på **Lägg till**.
5. I fältet **Register** ange **skattedokumentets rubrik**.
6. I fältet **härlett register** ange **skattedokumentets rubrik**.
6. I fältet **Fält** , välj **Nummer**.
7. I fältet **Kriterier** anger du numret på det skattedokument som ska skickas.
8. Välj **OK** för att stänga dialogrutan **Förfrågning**.
8. Välj **OK** för att skicka de valda dokumenten.

> [!NOTE]
> Under ditt första försök att skicka ett dokument via tjänsten uppmanas du att bekräfta anslutningen med tillägget för elektronisk fakturering. Välj **Klicka här för att ansluta till tjänsten inlämning av elektroniska dokument**.

### <a name="view-all-submission-logs"></a>Visa alla överföringsloggar

När du har aktiverat funktionen **konfigurerbara integreringstillägg för elektronisk fakturering** finns en ny sida där du kan följa upp processen för att skicka dokument. Du kan använda den här sidan om du vill visa överföringsloggar för alla skickade dokument.

1. Gå till **organisationsadministration \> periodisk \> elektroniska dokument \> logg för inlämning av elektroniska dokument**.
2. I fältet **Dokumenttyp** väljer du **Skattedokumentets rubrik** att endast filtrera skattedokument.
3. I åtgärdsfönstret, välj **Förfrågningar \> Överföringsinformation** om du vill visa information om körningsloggar för överföring.

![Visa information om överföringsloggen](media/e-Invoicing-services-get-started-BRA-View-Submission-log-details.png)

> [!NOTE] 
> För NF-e skattedokument visar kolumnen **Felkod** den returkod som har returnerats av SEFAZ-webbtjänsten.

### <a name="view-submission-logs-through-the-fiscal-document-page"></a>Visa överföringsloggar via sidan för skattedokument

När du har aktiverat funktionen **konfigurerbara integreringstillägg för elektronisk fakturering** kan du även visa överföringsloggarna via sidan för skattedokument.

1. Gå till **Redovisning \> Förfrågningar och rapporter \> Skattedokument \> Alla skattedokument**.
2. Välj ett skattedokument som tidigare skickades via tillägget elektronisk fakturering.
3. I åtgärdsfönstret på fliken **NF-e federal** välj **Elektronisk dokumentlogg**.

![Visa överföringsloggar från sidan för skattedokument](media/e-Invoicing-services-get-started-BRA-View-Submission-log-from-Fiscal-document-viewer.png)

### <a name="submit-approved-nf-e-fiscal-documents-for-sefaz-cancellation"></a>Skicka godkända NF-e-dokument för SEFAZ-annullering

När du har aktiverat funktionen **konfigurerbara integreringstillägg för elektronisk fakturering** kan den gamla processen för att avbryta NF-e-skattedokument inte längre användas. Det ersätts med en ny annulleringsprocess som är inbäddad på sidan **Logg för inlämning av elektroniska dokument**.

> [!NOTE]
> Kontrollera att du har kört annulleringen av kundens skattedokument för ett godkänt NF-e-dokument. Mer information finns i avsnittet om att [Annullera kundskattedokument (Brasilien)](https://docs.microsoft.com/dynamics365/finance/localizations/latam-bra-cancel-customer-fiscal-documents).

1. Gå till **organisationsadministration \> periodisk \> elektroniska dokument \> logg för inlämning av elektroniska dokument**.
2. Välj skattedokument och välj sedan **Funktioner \> Skicka relaterade överföringar**.
3. Ange en beskrivning av den relaterade sändningen och klicka sedan på **OK**.

### <a name="view-cancellation-submission-logs"></a>Visa överföringsloggar för annullering

1. Gå till **organisationsadministration \> periodisk \> elektroniska dokument \> logg för inlämning av elektroniska dokument**.
2. I fältet **Dokumenttyp** väljer du **Skattedokumentets rubrik** att endast filtrera skattedokument.
3. Välj skattedokument och välj sedan åtgärdsfönstret **Förfrågningar \> Relaterade överföringar**.

    Tillhörande skickade inleveranser är relaterade till en huvudöverföring som först gjordes. Den överföring som tillåter en specifik NF-e är till exempel huvudöverföring. Överföringen som begär annullering av samma NF-e i SEFAZ är en relaterad överföring. Den finns bara eftersom den begär att jobbet ska annulleras som skedde genom en annan överföring.

    Sidan **relaterade överföringar** visas alla relaterade inskickade och deras inlämningsstatus för ett visst skattedokument. På följande bild representerar den första raden inskickad som begärt godkännande av skattedokumentet. Den andra raden representerar det inskickade som annullerade skattedokumentet.

    ![Visa överföringsloggar för annullering](media/e-Invoicing-services-get-started-BRA-View-Cancellation-Submission-log.png)

4. I åtgärdsfönstret, välj **Förfrågningar \> Överföringsinformation** om du vill visa information om körningsloggar för överföring.

    ![Visa information om överföringsloggar för annullering](media/e-Invoicing-services-get-started-BRA-View-Cancellation-Submission-log-details.png)

## <a name="privacy-notice"></a>Sekretesspolicy
Om du aktiverar funktionen BR-00053 (NF-e Federal) kan det krävas att begränsade data skickas, vilket inkluderar organisationens momsregistrerings-ID. Detta kommer att översändas till tredje parts byråer som har tillstånd av skattemyndigheten för att skicka elektroniska fakturor till denna skattemyndighet i det fördefinierade format som krävs för integrering med den offentliga sektorns webbtjänster. En administratör kan aktivera och inaktivera funktionen BR-00053 (NF-e Federal) genom att navigera till **Organisationsadministration \> Inställningar \> Parametrar för elektroniskt dokument**. Välj fliken **Funktioner** , markera den rad som innehåller funktionen BR-00053 och välj sedan lämpligt alternativ. Data som importeras från dessa externa system till denna Dynamics 365 onlinetjänst omfattas av vår [sekretesspolicy](https://go.microsoft.com/fwlink/?LinkId=512132). Mer information finns i sektionerna om sekretessmeddelanden i landsspecifik funktionsdokumentation.


## <a name="additional-resources"></a>Ytterligare resurser

- [Tillägg för elektronisk fakturering: översikt](e-invoicing-service-overview.md)
- [Kom igång med tillägget elektronisk fakturering](e-invoicing-get-started.md)
- [Ställ in tillägg för elektroniska fakturor](e-invoicing-setup.md)
