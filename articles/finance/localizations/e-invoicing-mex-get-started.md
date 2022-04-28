---
title: Kom i gång med e-fakturering för Mexiko
description: Det här avsnittet innehåller information som hjälper dig att komma igång med e-fakturering för Mexiko.
author: gionoder
ms.date: 12/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom:
- "97423"
- intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 6fc8a9eaf6c6e4c82719e7c1ebccd4272548e73f
ms.sourcegitcommit: 23588e66e25c05e989f3212ac519d7016820430a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2022
ms.locfileid: "8566011"
---
# <a name="get-started-with-electronic-invoicing-for-mexico"></a>Kom i gång med e-fakturering för Mexiko

[!include [banner](../includes/banner.md)]

> [!IMPORTANT]
> E-fakturering för Mexiko stöder för närvarande inte alla funktioner som är tillgängliga i dokumentet Comprobante Fiscal Digital por Internet (CFDI) samt i den relaterade integrationen som är inbyggd i Microsoft Microsoft Dynamics 365 Finance eller Dynamics 365 Supply Chain Management.

Det här avsnittet innehåller information som hjälper dig att komma igång med e-fakturering för Mexiko. Den guidar dig genom de konfigurationssteg som är beroende av RCS (Regulatory Configuration Services) och Finance. Det vägleder dig genom de steg som du måste följa i ekonomin när du vill skicka CFDI-fakturor via tjänsten, och den innehåller även information om hur du granskar bearbetningsresultaten och status för CFDI-fakturor.

## <a name="prerequisites"></a>Förutsättningar

Innan du slutför stegen i det här avsnittet måste du slutföra stegen i [komma igång med tjänstadministration för e-fakturering](e-invoicing-get-started-service-administration.md) och [komma igång med e-fakturering](e-invoicing-get-started.md).

## <a name="set-up-the-cadena-xslt"></a>Konfigurera Cadena XSLT

Lägg till Cadena XSLT-schemat till globaliseringsfunktionen för CFDI-bearbetning genom att utföra följande steg.

1. Hämta schema från [SAT-webbplatsen](http://www.sat.gob.mx/sitio_internet/cfd/3/cadenaoriginal_3_3/cadenaoriginal_3_3.xslt).
2. Komprimera schemat till en ZIP-fil.
3. Spara xslt-filen i ditt Azure Storage-konto som ställts in i din tjänstemiljö för den nya behållaren.

## <a name="rcs-setup"></a>Inställning av RCS

Under RCS-inställningar ska du utföra följande uppgifter:

1. Importera e-faktureringsfunktionen för att bearbeta CFDI-fakturor.
2. Granska de formatkonfigurationer som krävs för att generera, skicka och ta emot svar om CFDI-fakturor och för att skicka och ta emot svar om annullering.
3. Konfigurera de händelser som stöder CFDI för fakturaöverföringar.
4. Publicera e-faktureringsfunktionen för CFDI-fakturor.

> [!NOTE]
> "e-faktureringsfunktionen" är det allmänna namnet för resursen som är konfigurerad och publicerad för att använda servern för e-fakturering. I det här fallet är CFDI-fakturor (MX) e-faktureringsfunktion du vill ställa in.

## <a name="import-the-e-invoicing-feature"></a>Importera e-faktureringsfunktion

1. Logga in på RCS-kontot.
2. I arbetsytan **globaliseringsfunktioner** i avsnittet **Funktioner**, välj panelen **e-fakturering**.
3. På sidan **e-faktureringsfunktioner** väljer du **Importera** för att importera **CFDI-fakturor (MX)** från den globala databasen.

    > [!NOTE]
    > Om funktionen inte visas i listan väljer du **synkronisera** och upprepar sedan steg 3.

![Funktionen Importera CFDI-fakturor (MX).](media/e-Invoicing-services-get-started-MEX-Select-Import-CFDI-feature.png)

När du importerar **CFD-fakturor (MX)** från den globala databasen, importeras också alla funktionsinställningar, inklusive konfigurationer och åtgärder.

### <a name="create-a-new-version-of-the-cfdi-invoices-mx-feature"></a>Skapa en ny version av funktionen CFDI-fakturor (MX)

Du kan skapa en ny version om t.ex. URL:er måste uppdateras. Mer information finns i [E-fakturering CFDI](tasks/mx-00010-e-invoicing-cfdi.md).

- På sidan **e-faktureringsfunktioner** på fliken **Versioner** välj Ändra status **Ny**.

![Lägga till en ny version av e-faktureringsfunktionen.](media/e-Invoicing-services-get-started-MEX-Select-New-e-Invoicing-feature.png)

### <a name="update-the-configuration-version"></a>Uppdatera konfigurationsversionen

1. På sidan **e-faktureringsfunktioner** på fliken **Konfigurationer** välj **Lägg till** eller **Ta bort** för att hantera konfigurationsversioner (konfigurationer för ER-filformat).

    ![Hantera konfigurationer av e-faktureringsfunktioner.](media/e-Invoicing-services-get-started-MEX-Manage-e-Invoicing-feature-Configurations.png)

    När du skapar en ny version ärvs alla konfigurationer från den senast publicerade versionen. För att bearbeta CFDI-fakturor krävs följande konfigurationer:

    - CFDI-faktura (BusinessDocumentService)
    - CFDI import av svarsmeddelande
    - CFDI import av fellogg
    - CFDI annulleringsbegäran (MX) (BusinessDocumentService)
    - CFDI-faktura (BusinessDocumentService)

2. Välj en konfigurationsversion i listan och välj sedan **Redigera** eller **Visa** för att öppna sidan **Formatdesigner**, där du kan redigera eller visa konfigurationen.

    ![Öppna sidan Formatdesigner.](media/e-Invoicing-services-get-started-MEX-Configuration-ER-format-designer.png)

3. Använd sidan **Formatdesigner** för att redigera och visa filkonfigurationerna i ER-format. Mer information finns i [Skapa konfigurationer för elektroniska dokument](../../fin-ops-core/dev-itpro/analytics/electronic-reporting-configuration.md).

    ![Formatdesignersida.](media/e-Invoicing-services-get-started-MEX-ER-format-designer.png)

## <a name="manage-the-e-invoicing-feature-setups"></a>Hantera inställningen för e-faktureringsfunktionen

- på sidan **e-faktureringsfunktioner** på fliken **Inställningar** välj **Lägg till**, **Ta bort** eller **Redigera** för att hantera inställningsfunktionen för e-fakturering.

![Hantera konfigurationer för e-faktureringsfunktionen.](media/e-Invoicing-services-get-started-MEX-Manage-e-Invoicing-feature-Setup.png)

Om du vill skicka CFDI-fakturor för auktorisering (generera XML-filen, skicka XML-filen och svaret) måste du konfigurera funktionen för **försäljningsfaktura**.

Om du vill skicka annullering av CFDI-faktura krävs funktionsinställningarna **Annullering** och **Annullera**.

### <a name="configure-the-sales-invoice-feature-setup"></a>Konfigurera inställningen av funktionen Sales-faktura

1. På sidan **e-faktureringsfunktioner** på fliken **Inställningar** i kolumnen **Funktionsinställningar** välj **Försäljningsfaktura**.
2. Välj **Redigera** om du vill konfigurera åtgärder, tillämpningsreglerna och variabler.

    ![Redigera inställningen för e-faktureringsfunktionen.](media/e-Invoicing-services-get-started-MEX-Edit-e-Invoicing-feature-setup.png)

3. På sidan **Inställning av funktionsversion** välj fliken **Åtgärder** för att hantera listan med åtgärder. Åtgärder definierar en lista med operationer som måste köras i en sekventiell ordning för att händelsen ska kunna utföras.

    ![Fliken Åtgärder.](media/e-Invoicing-services-get-started-MEX-Select-Actions.png)

    | Åtgärds-ID | Åtgärd                   | Namn på åtgärd                                  | Åtgärdsbeskrivning                                          |
    |-----------|--------------------------|----------------------------------------------|-------------------------------------------------------------|
    | 1         | Omvandla dokument       | Generera CFDI E-faktura utan digital signering | Generera CFDI e-faktura.                                |
    | 2         | Signera dokument            | Digitalt tecken                                 | Signera e-postfakturan digitalt för överföring.                |
    | 3         | Anropa mexikanska PAC-tjänsten | Skicka CFDI e-faktura                        | WCF-klienten (Windows Communication Foundation) skickar CFDI e-faktura. |
    | 4         | Behandla svar         | Analysera webbtjänstsvar                 | Analysera webbtjänstens svar och returnera felloggen. |

### <a name="set-up-the-url-for-mexican-pac-web-services"></a>Ställ in URL:en för mexikanska PAC-webbtjänster 

1. På fliken **Inställning av funktionsversion** på fliken **Åtgärder** på snabbfliken **Åtgärder** välj **Anropa mexikanska PAC-tjänsten**.
2. På snabbfliken **Parametrar** i fältet **URL-adress** anger du webbadressen till webbtjänsten för CFDI fakturasändning.

> [!NOTE]
> Använd samma steg för att uppdatera URL:en för åtgärden **Anropa mexikanska PAC-tjänsten** för funktionsinställningarna **Annullera** och **Annulleringsbegäran**.

### <a name="set-up-the-path-for-the-cadena-xlst-schema"></a>Ställa in sökvägen för Cadena XLST-schemat

1. På sidan **inställning av funktionsversion** på fliken **variabler**, välj variabelnamn **DigitalSignatureXSLT**.
2. I fältet **Värden** ange: {"containerUrl":"https://&lt;AccountStorageName&gt;.blob.core.windows.net/&lt;ContainerName&gt;","path":"&lt;RelativePath&gt;"}
   
    där: \<RelativePath\> = mapp\\mapp\\filnamn med två omvända snedstreck, ContainerName måste ange den behållare som används för tjänsten.
   
    Exempel på variabeln är:
    
    {"path":"xxxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx\\dev\\cadena_xslt","containerUrl":https://yyyyyyyyyy.blob.core.windows.net/containername}

## <a name="assign-the-draft-version-to-an-e-invoicing-environment"></a>Tilldela utkastversionen till en e-faktureringsmiljö

1. På sidan **e-faktureringsfunktioner** på fliken **Miljöer** välj Ändra status **Aktivera**.
2. I fältet **miljö** välj miljön.
3. I fältet **gäller från** väljer du det datum då miljön ska börja gälla.
3. Välj **Aktivera**.

![Aktivera en e-faktureringsmiljö.](media/e-Invoicing-services-get-started-MEX-Enable-e-Invoicing-Environment.png)

## <a name="change-the-version-status-to-completed"></a>Ändra versionsstatus till slutförd

1. På sidan **e-faktureringsfunktion** på fliken **Versioner**, välj den version av e-faktureringsfunktionen som har status **Utkast**.
2. Välj **Ändra status \> Slutför**.

## <a name="change-the-version-status-to-published"></a>Ändra versionsstatus till publicerad

- På sidan **e-faktureringsfunktioner** på fliken **Versioner** välj **Ändra status \> Publicera**.

## <a name="publish-the-e-invoicing-feature"></a>Publicera e-faktureringsfunktionen

1. På sidan **e-faktureringsfunktioner** väljer du fliken **Versioner** för att hantera status för funktionen **CFDI-fakturor (MX)**.
2. Välj **ändra status** om du vill ändra funktionens status.

![Ändra status för e-faktureringsfunktionen.](media/e-Invoicing-services-get-started-MEX-Change-status-of-e-Invoicing-feature.png)

## <a name="set-up-electronic-invoicing--integration-in-finance"></a>Ställ in integrering av e-fakturering i Finance

Du ställer in e-fakturering i Finance genom att utföra följande uppgifter:

1. Importera ER-datamodell, ER-datamodellmappning och de format som krävs för CFDI-fakturor.
2. Konfigurera svarstyper för uppdatering av CFDI-fakturor. Dessa svarstyper används för svaret från den auktoriserade certifieringsserverns leverantör (PAC).

### <a name="import-the-er-data-model-er-data-model-mapping-and-context-configurations-for-cfdi-invoices"></a>Importera ER-datamodell, ER-datamodellmappning och kontextkonfigurationer för CFDI-fakturor

1. Logga in på Finance.
2. I arbetsytan **elektronisk rapportering** i avsnittet **konfigurationsleverantör** väljer du rubriken **Microsoft**. Kontrollera att konfigurationsprovidern är **aktiverad**. För information om hur du ställer in en leverantör på **Aktiv**, se [Skapa konfigurationsleverantörer och markera dem som aktiva](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).
3. Välj **Databaser**.
4. Välj **Global resurs \> Öppna**.
5. Importera **Fakturamodell**, **Mappning av fakturamodell**, **CFDI-fakturaformat (MX)**, **CFDI-format för begäran om annullering av faktura (MX)** och **CFDI-format för annullering av faktura (MX)**.

### <a name="turn-on-the-feature-for-processing-cfdi-invoices"></a>Aktivera funktionen för att bearbeta CFDI-fakturor

1. Gå till **organisationsadministration \> inställning \> parametrar för elektroniska dokument**.
2. På fliken **funktioner** markerar du kryssrutan **Aktivera** i raderna för funktionsreferenser till **MX-00010** och **MX-00016**.

![Aktivera funktioner för att bearbeta CFDI-fakturor.](media/e-Invoicing-services-get-started-MEX-Enable-CFDI-feature.png)

### <a name="import-er-configurations-and-set-up-the-response-types-for-updating-cfdi-invoices"></a>Importera ER-konfigurationer och ställ in svarstyperna för uppdatering av CFDI-fakturor

#### <a name="import-er-configurations"></a>Importera ER-konfigurationer

1. I arbetsytan **elektronisk rapportering** i avsnittet **konfigurationsleverantör** väljer du rubriken **Microsoft**.
3. Välj **Databaser**.
4. Välj **Global resurs \> Öppna**.
5. Importera **Svarsmeddelandemodell**, **CFDI import av fellogg (MX)** och **CFDI import av svarsmeddelande (MX)**.

#### <a name="set-up-the-response-types"></a>Ställ in svarstyper

1. Gå till **organisationsadministration \> inställning \> parametrar för elektroniska dokument**.
2. På fliken **Elektroniska dokument** väljer du **Lägg till**.
3. Ange kundfakturajournalen och välj sedan projektfakturan i fältet **Registernamn**.
4. Definiera ett relaterat dokumentsammanhang för varje register.

    - För **Kundfakturajournaler** anger du **Kundfakturakontext**.
    - För **Projektfaktura**, ange **Projektfaktura kontext**.

4. Välj **svarstyper** för att konfigurera de svarstyper som kan returneras från e-fakturering och inkluderas i en kundfakturajournal eller på en projektfaktura.
5. Markera **Ny** och sedan, i fältet **Svarstyp**, markerar du **Svar**.
6. I fältet **Överföringsstatus** välj **Väntande**.
7. I fältet **Modellmappning** välj **Importformat för svarsmeddelande – Modellmappning från svarsmeddelande**.
8. Välj **Spara**.
9. Markera **Ny** och sedan, i fältet **Svarstyp**, markerar du **ResponseData**.
10. I fältet **Överföringsstatus** välj **Väntande**.
11. I fältet **modellmappning** väljer du **CFDI importformat för svarsdata (information) – import av svarsdata**.
12. Välj **Spara**.

## <a name="process-electronic-invoices-in-finance"></a>Bearbeta e-fakturor i Finance 

Under bearbetningen av CFDI-fakturor i Finance genom E-fakturering kan du utföra följande uppgifter:

- Skicka CFDI-fakturor.
- Visa körningsloggar för överföring.
- Skicka annulleringen av en CFDI-faktura.

### <a name="submit-cfdi-invoices"></a>Skicka CFDI-fakturor

När du har aktiverat funktionen **Konfigurerbar integrering för e-fakturering** kan processen **Exportera/importera e-faktura** (**Kundreskontra \> Fakturor \> E-fakturor**) för att skicka CFDI-fakturor inte längre användas. Den ersätts med en ny process som kallas **skicka elektroniska dokument**.

> [!NOTE]
> Innan du använder processen för att **skicka elektroniska dokument** bör du kontrollera att inställningen som krävs för mexikanska e-fakturor har slutförts. För mer information, se [CFDI layout version 3.3](./latam-mex-cfdi-3-3.md).

1. Gå till **organisationsadministration \> periodisk \> elektroniska dokument \> skicka elektroniska dokument**.
2. Ställ alltid in alternativet **Skicka dokument igen** till **Nej** för första inlämningen av ett dokument. Om du måste skicka ett dokument på nytt via tjänsten ställer du in det här alternativet på **Ja**.
3. På snabbfliken **Poster att inkludera** välj **Filter** för att öppna dialogrutan **fråga** där du kan skapa en frågeställning för att välja dokument för överföring.

![Skicka ett CFDI-dokument.](media/e-Invoicing-services-get-started-MEX-Submit-CFDI-document.png)

> [!NOTE]
> Under ditt första försök att skicka ett dokument via tjänsten uppmanas du att bekräfta anslutningen med E-fakturering. Välj **Klicka här för att ansluta till tjänsten inlämning av elektroniska dokument**.

### <a name="view-submission-logs"></a>Visa överföringsloggar

Du kan visa överföringsloggar för alla skickade dokument eller för bara ett skickat dokument.

#### <a name="view-all-submission-logs"></a>Visa alla överföringsloggar

När du har aktiverat funktionen **konfigurerbar integrering för e-fakturering** finns en ny sida där du kan följa upp processen för att skicka dokument. Du kan använda den här sidan om du vill visa överföringsloggar för alla skickade dokument.

1. Gå till **organisationsadministration \> periodisk \> elektroniska dokument \> logg för inlämning av elektroniska dokument**.
2. I fältet **Dokumenttyp** väljer du **Kundfakturajournal** för att filtrera fram nödvändiga elektroniska dokument.

    ![Välja en dokumenttyp för att visa överföringsloggarna.](media/e-Invoicing-services-get-started-MEX-Select-document-type-for-viewing-submission-log.png)

3. I åtgärdsfönstret, välj **Förfrågningar \> Överföringsinformation** om du vill visa information om körningsloggar för överföring.

    ![Visa information om överföringsloggen.](media/e-Invoicing-services-get-started-MEX-View-submission-log-details.png)

Informationen i överföringsloggarna delas upp på tre snabbflikar:

- **Bearbeta åtgärder** – på den här snabbfliken visas körningsloggen för de åtgärder som är konfigurerade i funktionsversionen som ställdes in i RCS. Kolumnen **Status** visar om åtgärden har utförts utan fel.
- **Åtgärdsfiler** – på den här snabbfliken visas de mellanliggande filer som genererades under körningen av åtgärderna. Du kan välja **vy** om du vill hämta och visa filen.
- **Bearbeta åtgärdslogg** – på den här snabbfliken visas resultaten av kommunikationen mellan E-fakturering och målwebbtjänsten. Det visar också vad som har returnerats av bearbetningen från webbtjänst. I kolumnen **Felkod** visas den returkod som har returnerats av webbtjänsten för auktorisering.

När den skickade CFDI-fakturan godkänns uppdateras dess status till **godkänd**.

#### <a name="view-submission-logs-from-cfdi-invoices"></a>Visa överföringsloggar från CFDI-fakturor

När du har aktiverat funktionen **konfigurerbar integrering för e-fakturering** kan du även visa överföringsloggarna från CFDI-fakturor.

1. Gå till **Kundreskontra \> Förfrågningar och rapporter \> CFDI (e-fakturor)**.
2. Välj en CFDI-faktura som har skickats efter att funktionen **konfigurerbar integrering för e-fakturering** aktiverades.
3. I åtgärdsfönstret på fliken **Historik** välj **Elektronisk dokumentlogg**.

![Visa överföringsloggar från CFDI-fakturor.](media/e-Invoicing-services-get-started-MEX-View-submission-log-from-CFDI-invoice.png)

> [!NOTE]
> För CFDI-fakturor som har skickats innan den funktionen **konfigurerbar integrering för e-fakturering** aktiverades är knappen **Historik** tillgänglig. Knappen **Historik** är inte tillgänglig för CFDI-fakturor som har skickats innan den funktionen **konfigurerbar integrering för e-fakturering** aktiverades.

### <a name="submit-cancellation-of-cfdi-invoices"></a>Skicka annulleringen av en CFDI-fakturor

När du har aktiverat funktionen **konfigurerbar integrering för e-fakturering** kan den gamla processen för att avbryta CFDI-fakturor inte längre användas. Det ersätts med en ny annulleringsprocess som är inbäddad på sidan **Logg för inlämning av elektroniska dokument**.

1. Gå till **Kundreskontra \> Förfrågningar och rapporter \> CFDI (e-fakturor)**.
2. Om CFDI-faktura har statusen **Godkänd** väljer du **Funktioner \> Avbryt CFDI**.
3. Gå till **organisationsadministration \> periodisk \> elektroniska dokument \> logg för inlämning av elektroniska dokument**.
4. Välj den CFDI-fakturan och välj sedan **Funktioner \> Skicka relaterade överföringar**.
5. Ange en beskrivning av den relaterade sändningen och klicka sedan på **OK**.

#### <a name="view-cancellation-submission-logs"></a>Visa överföringsloggar för annullering

1. Gå till **organisationsadministration \> periodisk \> elektroniska dokument \> logg för inlämning av elektroniska dokument**.
2. I fältet **Dokumenttyp** väljer du **Kundfakturajournal** för att endast filtrera efter journaldokument för kundfaktura.
3. Välj CFDI-fakturan och välj sedan åtgärdsfönstret **Förfrågningar \> Relaterade överföringar**.

    Sidan **relaterade överföringar** visas alla relaterade inskickade och deras inlämningsstatus för en viss CFDI-faktura. På följande bild representerar den första raden inskickad som begärt godkännande av CFDI-fakturan. Den andra raden representerar det inskickade som annullerade den CFDI-fakturan.

    ![Visa överföringsloggar för annullering.](media/e-Invoicing-services-get-started-MEX-View-cancellation-submission-log.png)

4. I åtgärdsfönstret, välj **Förfrågningar \> Överföringsinformation** om du vill visa information om körningsloggar för överföring.

    ![Visa information om överföringsloggar för annullering.](media/e-Invoicing-services-get-started-MEX-View-cancellation-submission-log-details.png)

## <a name="privacy-notice"></a>Sekretesspolicy
Om du aktiverar funktionen **CFDI mexikansk e-faktura (MX)** kan det krävas att begränsade data skickas, vilket inkluderar organisationens skatteregistrerings-ID. Detta kommer att översändas till tredje parts byråer som har tillstånd av skattemyndigheten för att skicka e-fakturor till denna skattemyndighet i det fördefinierade format som krävs för integrering med den offentliga sektorns webbtjänster. En administratör kan aktivera och inaktivera funktionen **CFDI mexikansk e-faktura (MX)** genom att navigera till **Organisationsadministration \> Inställningar \> Parametrar för elektroniskt dokument**. Välj fliken **Funktioner**, markera de rader som innehåller funktionerna **CFDI mexikansk e-faktura (MX)** och välj sedan lämpligt alternativ. Data som importeras från dessa externa system till denna Dynamics 365 onlinetjänst omfattas av vår [sekretesspolicy](https://go.microsoft.com/fwlink/?LinkId=512132). Mer information finns i sektionerna om sekretessmeddelanden i landsspecifik funktionsdokumentation.

## <a name="additional-resources"></a>Ytterligare resurser

- [E-fakturering – översikt](e-invoicing-service-overview.md)
- [Kom i gång med e-fakturering](e-invoicing-get-started.md)
- [Ställ in e-fakturering](e-invoicing-setup.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
