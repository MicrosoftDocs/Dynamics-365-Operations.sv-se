---
title: Ställ in direkt integration av italiensk FatturaPA med SDI
description: Det här ämnet ger information som hjälper dig att komma igång med elektronisk fakturering för Italien och ställa in direkt integration av italiensk FatturaPA med Exchange-systemet (SDI).
author: abaryshnikov
ms.date: 07/27/2022
ms.topic: article
audience: Application User, Developer
ms.reviewer: kfend
ms.search.region: Global
ms.author: abaryshnikov
ms.search.validFrom: 2021-10-18
ms.dyn365.ops.version: AX 10.0.20
ms.openlocfilehash: 363b7b5e3d5abbb990fea8f8ad4d0c1bebf80102
ms.sourcegitcommit: 6d9fcb52d723ac5022a3002e0ced8e7b56e9bc2a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9203182"
---
# <a name="set-up-direct-integration-of-italian-fatturapa-with-sdi"></a>Ställ in direkt integration av italiensk FatturaPA med SDI

[!include [banner](../includes/banner.md)]

> [!IMPORTANT]
> E-fakturering för Italien kanske för närvarande inte stöder alla funktioner som är tillgängliga för elektroniska fakturor i Microsoft Dynamics 365 Finance och Dynamics 365 Supply Chain Management.

Den här artikeln innehåller information som hjälper dig att komma igång med elektronisk fakturering för Italien i Finance och Supply Chain Management. Den guidar dig genom de konfigurationssteg som är beroende av land/region i RCS (Regulatory Configuration Services). De här stegen kompletterar stegen som beskrivs i [Kom igång med elektronisk fakturering](e-invoicing-get-started.md).

## <a name="prerequisites"></a>Förutsättningar

Innan du slutför stegen i detta ämne måste följande förutsättningar vara slutförda:

- Slutför stegen i [Kom i gång med elektronisk fakturering](e-invoicing-get-started.md).
- Importera elektroniska faktureringsfunktionen för **Italiensk FatturaPA (IT)** i RCS från den globala databasen. Mer information finns i avsnittet [Importera en elektronisk faktureringsfunktion från leverantörsavsnittet för Microsoft-konfiguration](e-invoicing-get-started.md#import-an-electronic-invoicing-feature-from-the-microsoft-configuration-provider) i det ovan nämnda avsnittet "Kom igång med elektronisk fakturering".
- Lägga till länkar från de certifikat som krävs till tjänstemiljön. De obligatoriska certifikaten inkluderar certifikatet för digital signatur, certifikat från certifikatutfärdare (CA) och klientcertifikat. För mer information, se avsnittet [Skapa digitalt certifikatshemlighet](e-invoicing-get-started-service-administration.md#create-a-digital-certificate-secret) i ämnet "Kom igång med administration av elektronisk fakturering".

## <a name="country-specific-configuration-for-the-italian-fatturapa-it-electronic-invoicing-feature"></a>Landsspecifik konfiguration för italiensk FatturaPA (IT) Elektronisk faktureringsfunktion

Genomför de här procedurerna innan du distribuerar programinställningarna till det anslutna programmet Finance eller Supply Chain Management.

Denna artikel kompletterar avsnittet [Landsspecifik konfiguration för programkonfiguration](e-invoicing-get-started.md#country-specific-configuration-of-application-setup) i ämnet "Kom igång med Elektronisk fakturering".

### <a name="create-a-new-feature"></a>Skapa en ny funktion

1. Logga in på RCS.
2. I arbetsytan **Elektronisk rapportering** i avsnittet **Konfigurationsleverantör** markera ditt företags konfigurationsleverantör som aktiv.
3. I arbetsytan **globaliseringsfunktion** i avsnittet **Funktioner**, välj panelen **Elektronisk faktura**.
4. På sidan **Funktioner för elektronisk fakturering**, välj **Lägg till** \> **Baserat på den befintliga funktionen**.
5. Under **Microsoft konfigurationsleverantör**, välj **Italiensk FatturaPA (IT)** som basfunktion anger du ett namn och väljer sedan **Skapa funktion**.

### <a name="set-up-application-specific-parameters"></a>Ställa in appspecifika parametrar

1. På sidan **Funktioner för elektronisk fakturering**, funktion att redigera.
2. I fliken **Versioner** bekräftar du att versionen **Utkast** har valts.
3. På fliken **konfigurationer**, välj en konfiguration och välj sedan **Appspecifika parametrar**.
4. I **Uppslag**, se till att uppslaget **Lista över underkategorier för återförda tillägg in natura** har valts.
5. I avsnittet **Villkor** välj **Lägg till**.
6. Lägg till särskilda villkor för varje underkategori som definieras i systemet och spara ändringarna.

    > [!NOTE]
    > I kolumnen **Namn** kan du välja värdet **\*Tom\*** eller **\*Inte tom\*** platshållarvärde istället för ett specifikt värde.

### <a name="configure-a-processing-pipeline-for-export"></a>Konfigurera ett bearbetningsförlopp för export

1. På sidan **Funktioner för elektronisk fakturering**, funktion att redigera.
2. På fliken **Inställningar**, välj **Försäljningsfakturor** och välj **Redigera**.
3. Gå igenom åtgärderna i området **Bearbetning av försäljningsförlopp** och ställ in alla fält som behövs:

    - Fö åtgärden **Logga in dokument**, i fältet **Certifikatnamn**, ange certifikatet för digital signatur.
    - För åtgärden **Skicka** ange fälten **URL-adress** och **Certifikat**. Värdet för fältet **Certifikat** är en kedja av certifikat, varav det första är rot-CA-certifikatet (caentrate.cer), och det andra är klientens certifikat.

4. I avsnittet **Tillämpningsregler** går du igenom klausulerna och granskar eller ställer in de obligatoriska fälten:
    - Granska klausulen **LegalEntityID** och uppdatera den med korrekt värde från din juridiska person.

5. Välj **Validera** om du vill vara säker på att alla obligatoriska fält har ställts in.
6. Spara ändringarna och stäng sidan.
7. På fliken **Inställningar**, välj **Projektfakturor** och välj **Redigera**.
8. Upprepa steg 3 till 6 för projektfakturor.

### <a name="configure-the-processing-pipeline-for-import"></a>Konfigurera ett bearbetningsförlopp för import

1. På sidan **Funktioner för elektronisk fakturering**, funktion att redigera.
2. På fliken **Inställningar**, välj **Importfakturor** och välj **Redigera**.
3. I avsnittet **Datakanalen**, på fliken **Parameter** i fältet **Datakanal**, ange ett strängvärde.
4. Ställ in fälten för inställningen på fliken **Tillämplighetsregler**. Du kan använda standard klausul **Kanal** genom att ange det värde du angett för fältet **Datakanal** i föregående steg till **Värde**.

    ![Ställa in tillämplighetsregler.](media/e-invoicing-ita-fatturapa-get-started-apprules-setup.png)

5. Välj **Validera** om du vill vara säker på att alla obligatoriska fält har ställts in.

### <a name="deploy-the-feature"></a>Distribuera funktionen

1. Komplettera, publicera och distribuera funktionen i tjänstemiljön. Mer information finns i avsnittet [Distribuera en elektronisk faktureringsfunktion till Servicemiljö](e-invoicing-get-started.md#deploy-the-electronic-invoicing-feature-to-service-environment) i det ovan nämnda avsnittet "Kom igång med elektronisk fakturering".
2. Distribuera funktionen till den anslutna appen. Mer information finns i avsnittet [Distribuera en elektronisk faktureringsfunktion till Ansluten app](e-invoicing-get-started.md#deploy-the-electronic-invoicing-feature-to-connected-application) i det ovan nämnda avsnittet "Kom igång med elektronisk fakturering".

### <a name="set-up-finance"></a>Ställa in Finance

1. Logga in på Finance-miljön.
2. I arbetsytan **elektronisk rapportering** i avsnittet **konfigurationsprovider** väljer du panelen **Microsoft**.
3. Välj **Databaser** \> **Global** \> **Öppen**.
4. Välj och importera konfigurationer **kontextmodellen för kundfaktura** och **Importera leverantörsfakturor (IT)**.
5. Gå till **Organisationsadministration** \> **Inställningar** \> **Parametrar för elektroniskt dokument**.
6. På fliken **Funktioner**, hitta och välj funktionen **Italiensk elektronisk faktura** och välj sedan kryssrutan **Aktivera**.
7. Kontrollera på fliken **Elektroniskt dokument**, se till att fälten **Kundfakturajournal** och **Projektfaktura** är inställda enligt informationen i [Konfigurera appinställningarna](e-invoicing-get-started.md#configure-the-application-setup).

### <a name="set-up-vendor-invoice-import"></a>Konfigurera leverantörsfakturaimport 

1. I Finance arbetsytan **Elektronisk rapportering** i avsnittet **Konfigurationsleverantör** markera ditt företags konfigurationsleverantör som aktiv.
2. Välj **rapporteringskonfigurationer**.
3. Välj **Kontextmodell för kundfaktura** och välj **Skapa konfiguration**.
4. Välj **Härleds från Namn: Kundfaktura sammanhang, Microsoft** och skapa en härledd konfiguration.
5. På versionen **Utkast** välj **Designer**.
6. I trädet **Datamodell**, välj **Mappa modell till datakälla**.
7. I trädet **Definitioner**, välj **DataChannel** och välj **Designer**.
8. I trädet **Datakällor**, visa containern **\$Context\_kanal**.
9. I fältet **Värde**, välj **Redigera**. 
10. Ange namnet på datakanalen. Namnet ska ha maximalt 10 tecken. Den bör matcha värdet på parametern **datakanal** för datakanal för den elektroniska faktureringsfunktionen i RCS.
11. Spara ändringarna och gå sedan till **Rapporteringskonfigurationer** \> **Slutför konfigurationsversion**.
12. På fliken **Externa kanaler**, i avsnittet **Kanaler**, välj **Lägg till**.
13. I fältet **Kanal** ange värdet **\$Kontextkanal**.
14. Ange värden i fälten **Beskrivning** och **Företag**.
15. I fältet **Dokumentkontext** väljer du den nya härledda konfigurationen från **Kontextmodell för kundfaktura**. Mappningsbeskrivningen ska vara **Datakanalkontext**.
16. Välj **Importera källor** välj **Lägg till** och ange sedan följande värden:

    - **Namn:** OutputFile
    - **Dataenhetsnamn:** Leverantörsfakturahuvud (**Dataenhet:** VendorInvoiceHeaderEntity)
    - **Modellmappning:** Import av leverantörsfaktura (IT)

> [!NOTE]
> Om du har importera leverantörsfakturor från olika källor kan du skapa flera externa kanaler och flera härledda konfigurationer som har olika värden **\$Kontextkanal**. Du kanske till exempel vill importera leverantörsfakturor för olika juridiska personer.

## <a name="proxy-server-setup"></a>Proxyserverinställning

Det här avsnittet innehåller information som hjälper dig att ställa in och konfigurera proxytjänsten för kommunikation mellan Exchange-systemet (SDI) och den elektroniska faktureringstjänsten.

### <a name="create-an-app-registration"></a>Skapa en appregistrering

1. Använd följande Windows PowerShell-skript när du vill skapa ett själv signerat certifikat för S2S-autentisering (Service-to-service).

    ```powershell
    $certOutputLocation = "C:\certs\proxytest"
    $certName = "sdiProxyClientS2SCert"
    $certPassword = "123"

    $certCerFile = Join-Path $certOutputLocation "$certName.cer"
    $certPfxFile = Join-Path $certOutputLocation "$certName.pfx"

    $securePassword = ConvertTo-SecureString $certPassword -AsPlainText -Force

    $cert = New-SelfSignedCertificate -KeyLength 2048 -KeyExportPolicy Exportable -FriendlyName "CN=$certName" -CertStoreLocation Cert:\CurrentUser\My -Subject $certName -Provider "Microsoft Enhanced RSA and AES Cryptographic Provider"

    Export-Certificate -Cert $cert -FilePath $certCerFile -type CERT | Out-Null
    Export-PfxCertificate -Cert $cert -FilePath $certPfxFile -Password $securePassword | Out-Null
    ```

2. Spara .pfx-certifikatfilen i nyckelarkivet och ta sedan bort den lokala kopian.
3. Logga in på [Azure-portalen](https://portal.azure.com) som administratör.
4. Skapa en appregistrering för SDI-proxytjänsten.

    1. Gå till **Appregistreringar**, skapa en registrering och ställ sedan in följande värden för den:

        - **Namn:** SDI-proxyklient
        - **Kontotyper som stöds:** Konton endast i den här organisationskatalogen (Enstaka innehavare)

    2. Välj **Registrera** och välj sedan den appregistrering som du just skapade.
    3. Gå till **API-behörigheter** och välj **Bevilja administratörsmedgivande**.
    4. Gå till **Certifikat och hemligheter**, välj **Ladda upp certifikat** och ladda upp .cer-certifikatfilen för S2S-autentisering.
    5. Gå till **Företagsprogram** och välj det program som du har skapat.
    6. Spara värden för **program-ID** (klient-ID) och **objekt-ID** för appen.
    7. Faktureringstjänsten-teamet måste bevilja appen åtkomst till tjänsten. Skicka värdena för följande parametrar till <D365EInvoiceSupport@microsoft.com>:

        - Klientorganisations-ID för AAD
        - LCS miljö-ID
        - Sökande-ID
        - Objekt-ID

5. I RCS lägger du till appen i applistan för din tjänstemiljö.

    1. Gå till **Globaliseringsfunktionerna** \> **Miljöer** \> **Elektroniska fakturering** \> **Servicemiljö** och välj din miljö.
    2. I avsnittet **Appar**, lägg till en rad i rutnätet och ange namn och objekt-ID för appen.

        ![Lägga till programmet i tjänstemiljön.](media/e-invoicing-ita-fatturapa-get-started-add-app-to-env.png)

    3. Välj **spara** och välj sedan **publicera**.

### <a name="create-an-azure-virtual-machine"></a>Skapa en virtuell maskin i Azure

1. I [Azure-portalen](https://portal.azure.com), gå till **Virtuella maskiner** och **Skapa ny**.
2. På fliken **Grundläggande**, välj din prenumeration och resursgrupp. Värdena ska vara den abonnemangs- och resursgrupp där nyckellager och Lagring av nycklar finns.
3. Välj region. Det här värdet ska vara den region där din Finance-miljö distribueras.
4. Lägg till administratörens användarnamn och lösenord och spara dem i nyckelarkivet.
5. I fältet **Välj inkommande portar**, välj **HTTPS (443)** och **RPD (3389)**.

    > [!NOTE]
    > Vi rekommenderar att du inaktiverar **RDP (3389)** porten när systemet går till produktion. Du kan aktivera det igen om du måste ansluta till den virtuella datorn (VM) för felsökningsändamål.

    ![Ställa in fälten på fliken Grundläggande om du vill skapa en Azure VM.](media/e-invoicing-ita-fatturapa-get-started-create-vm-1.png)

6. På fliken **Diskar** på snabbfliken **Avancerad**, markera kryssrutan **Använd hanterade diskar**. Lämna kryssrutan **efemär operativsystemdisk** avmarkerad.

    ![Ställa in fälten på fliken Grundläggande om du vill skapa en Azure VM.](media/e-invoicing-ita-fatturapa-get-started-create-vm-2.png)

7. På fliken **Nätverk** under fältet **Offentlig IP**, välj **Skapa nu**.

    ![Ställa in fälten på fliken Nätverk om du vill skapa en Azure VM.](media/e-invoicing-ita-fatturapa-get-started-create-vm-3.png)

8. I dialogrutan **Skapa offentlig IP-adress** i fältgruppen **SKU**, välj alternativet **Standard**. I fältgruppen **Tilldelning** välj alternativet **Statisk**.

    ![Skapa en offentlig IP-adress.](media/e-invoicing-ita-fatturapa-get-started-create-vm-4.png)

9. På fliken **hantering**, avmarkera kryssrutan **Autostängning** för att inaktivera automatisk avstängning.
10. Ställ in fältet **gäst-OS-uppdateringar** till **Manuell** och ställ sedan in andra principer.
11. Välj Granska och skapa VM.
12. I den nya virtuella datorn, gå till **Identitet** \> **System tilldelat** och ange alternativet **Status** till **På**.
13. Bevilja VM-åtkomst till nyckelvalv.

    1. I nyckelvalvet, gå till **Åtkomstkontroll (IAM)** \> **Rolltilldelningar**.
    2. Välj **Lägg till rolltilldelning** och ange följande fält:

        1. I fältet **Roll** ange **Användare av Key Vault-hemlighet**.
        2. I fältet **Tilldela åtkomst till** ange **Virtuell maskin**.
        3. I fältet **abonnemang**, ange ditt abonnemang.
        4. I fältet **Välj**, ange din VM.

    3. Gå till **Åtkomstpolicyer**.
    4. Välj **Lägg till åtkomstpolicy** och ange följande fält:

        1. I fältet **Valt huvudkonto** välj din virtuella dator.
        2. I behörigheter **Certifikat**, välj **List** och **Hämta**.

14. I [Azure-portalen](https://portal.azure.com), gå till **Offentlig IP adress** och välj IP-adressen som skapades i den virtuella datorn.
15. Gå till **Konfiguration** och ställ in DNS-namnet (Domain Name System).

### <a name="prepare-the-proxy-service-environment"></a>Förbered proxytjänstmiljön

Följ de här stegen på datorn där proxytjänsten finns.

1. Anslut till den virtuella datorn genom att använda anslutning till fjärrdator.
2. Öppna det lokala maskinintyget. Mer information finns i [Så här visar du intyg med MMC-instickskort](/dotnet/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in).
3. Importera **caentrate.cer**-certifikatet för produktion och **CAEntratetest.cer** för att testa in [betrodda rotcertifikatutfärdare](/dotnet/framework/wcf/feature-details/working-with-certificates#certificate-stores). (**CAEntratetest.cer** är rot-CA-certifikatet som tillhandahölls av myndigheten.)
4. Öppna Kontrollpanelen **Slå av eller på funktioner i Windows**, eller gå till **Serverhanteraren** \> **Lägg roller och funktioner** för serveroperativsystemet (OS) och aktivera funktionerna för Internet Information Services (IIS):

    - Webbhanteringsverktyg
        - IIS-hanteringskonsol
    - Webbtjänster
        - Programutvecklingsfunktioner
            - .NET Extensibility 4.7 (eller 4.8)
            - ASP
            - ASP.NET 4.7 (eller 4.8)
            - CGI
            - ISAPI-tillägg
            - ISAPI-filter
        - Vanliga HTTP-funktioner
            - Standarddokument
            - Katalogbläddring
            - HTTP-fel
            - Statiskt innehåll
        - Hälsa och diagnostik
            - HTTP-loggning
            - Spårning
        - Prestandafunktioner
            - Komprimering av statiskt innehåll
        - Säkerhet
            - Begär filtrering

    ![Slå på IIS-funktioner.](media/e-invoicing-ita-fatturapa-get-started-turnon-features.png)

### <a name="set-up-the-sdi-proxy-service-in-iis"></a>Ställa in SDI-proxytjänsten i IIS

1. I Microsoft Dynamics Lifecycle Services (LCS), gå till biblioteket delade tillgångar och välj **Datapaket** som tillgångstyp.
2. Sök efter **Elektronisk faktureringstjänst Sdi Proxy** och hämta den till VM.
3. Konfigurera tjänsten.

    1. Avmarkera mappen **Elektronisk faktureringstjänst Sdi Proxy** som du hämtat.
    2. I mappen **src\\FattureService** öppna filen **appsettings.json** och ställ in följande parametrar:

        - **KeyVaultUri** – Ange adressen till nyckelarkivet som lagrar klientcertifikatet för faktureringstjänsten.
        - **TenantId** – Ange den globala unika identifieraren (GUID) för kundens innehavare.
        - **EnvironmentId** – Ange ID för LCS-miljön.
        - **ClientId** – Anger app-ID för mellanliggande tjänsteprogramregistrering i kundens innehavare.
        - **ClientCertificateName** – Ange namnet på S2S-certifikatet i nyckelarkivet.
        - **SecurityServiceClientOptions.Endpoint** – Ange URL för säkerhetstjänsten.
        - **SecurityServiceClientOptions.Resource** – Ange vilket område som token ska erhållas för.
        - **InvoicingServiceClientOptions.Endpoint** – Ange slutpunkten för faktureringstjänsten. Det här värdet ska vara samma slutpunkt som används för RCS och Finance.
        - **InvoicingServiceClientOptions.ServiceEnvironmentId** – Ange namnet på servicemiljön. Det här värdet ska vara namnet på din Finance-miljö.
        - **NotificationsFolder** – Ange mappen där inkommande meddelandefiler ska sparas.

    3. I filen **web.config** hitta följande rad och lägg till tumavtrycket för proxyservercertifikatet.

        `<serviceCertificate findValue="[certificate thumbprint]" storeLocation="LocalMachine" storeName="My" x509FindType="FindByThumbprint">`

        > [!TIP]
        > När systemet går till produktion kan du ändra vissa värden i filen web.config för att minska mängden logginformation som samlas in och hjälpa till att spara diskutrymme. I noden **\<system.diagnostics\>\<source\>** ändra värdet **switchValue** till **Critical,Error**. Mer information finns i [MS Service spårningsvisare](/dotnet/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe).

4. Öppna IIS-hanteraren. Ligga kvar i rotnoden i trädet till vänster. Till höger väljer du **servercertifikat**.

    ![Välja servicecertifikat i IIS-hanteraren.](media/e-invoicing-ita-fatturapa-get-started-proxy-cert-1.png)

5. Öppna menyn och välj **Importera**.
6. I dialogrutan **Importera certifikat** i fältet **Certifikatfil (.pfx)** ange sökvägen till .pfx-filen för proxyservercertifikatet.

    ![Ange proxytjänstens certifikatfil.](media/e-invoicing-ita-fatturapa-get-started-proxy-cert-2.png)

7. Markera och håll inne (eller högerklicka på) **Webbplatser** och välj sedan **Lägg till webbplats**.
8. I dialogrutan **Lägg till webbplats** i fältet **Webbplatsnamn** anger du ett namn för webbplatsen.
9. I fält **Fysisk sökväg**, punkt mappen **src\\FattureService**.
10. Välj **Bindningstyp** i fältet **https**.
11. I fältet **värddatornamn** anger du värddatornamn.
12. Låt **IP-adressen** och **Port** fälten vara inställda på standardvärdena.
13. Kontrollera att kryssrutan **Kräv servernamns indikation** är avmarkerad, eftersom SDI inte stöder den tekniken.
14. Välj det proxyservercertifikat som du importerat i **SSL-certifikat** fältet.
15. I fältet **App-pool** ange en pool för webbplatsen och anteckna dess namn (t.ex. **SdiAppPool**).

    ![Lägga till en webbplats.](media/e-invoicing-ita-fatturapa-get-started-proxy-iis-setup-1.png)

16. När du är klar med att skapa webbplatsen öppnar du menyn för **SSL-inställningar**.

    ![Öppna menyn för SSL-inställningar.](media/e-invoicing-ita-fatturapa-get-started-proxy-iis-setup-2.png)

17. Markera kryssrutan **Kräver SSL** och sedan i fältgruppen **Klientcertifikat** välj alternativet **Kräv**.

    ![Konfigurera SSL-inställningar.](media/e-invoicing-ita-fatturapa-get-started-proxy-iis-setup-3.png)

18. Öppna **Katalog bläddring** och välj **Aktivera**.
19. I vilken webbläsare som helst, gå till **serverDNS/TrasmissioneFatture.svc**. En standardsida om tjänsten måste visas.

    ![Kontrollera tjänsten i en webbläsare.](media/e-invoicing-ita-fatturapa-get-started-proxy-open-browser.png)

20. Skapa följande mappar där du lagrar loggar och filer:

    - **C: \\Loggar\\** – Butiksloggfiler här. De här filerna kan visas i [MS Tjänst spårningsvisare](/dotnet/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe).
    - **C:\\Filer\\** – Lagra alla svarsfiler här.

21. I Filutforskaren, bevilja **NÄTVERKSTJÄNST** och **IIS AppPool\\SdiAppPool** (eller **IIS AppPool\\DefaultAppPool** Jag om du använder standardpoolen) har tillgång till mappar **Loggar** och **Filer**.

    1. Markera och håll inne (eller högerklicka på) mapparna, och välj sedan **Egenskaper**.
    2. I dialogrutan **Egenskaper** på fliken **Säkerhet**, välj **Redigera**.
    3. Lägg till användarna om de inte finns med i listan.
    4. Upprepa steg 1 till och med 3 för alla andra mappar.

    ![Lägga till behörigheter för tjänsteanvändaren.](media/e-invoicing-ita-fatturapa-get-started-proxy-add-user.png)

## <a name="privacy-notice"></a>Sekretesspolicy 

Om du vill aktivera funktionen för **elektronisk faktura i Italien** måste begränsade data skickas. Dessa data inkluderar företagets momsregistrerings-ID. En administratör kan aktivera och inaktivera funktionen för elektronisk italiensk faktura. Följ dessa steg om du vill inaktivera en funktion.

1. Gå till **Organisationsadministration** \> **Inställningar** \> **Parametrar för elektroniskt dokument**.
2. På fliken **Funktioner**, hitta raderna som innehåller funktionen **Italiensk elektronisk faktura** och välj sedan kryssrutan **Inaktivera nu**.

Data som importeras från dessa externa system till denna Dynamics 365 onlinetjänst omfattas av vår [sekretesspolicy](https://go.microsoft.com/fwlink/?LinkId=512132). Mer information finns i sektionerna om sekretessmeddelanden i lands-/regionspecifik funktionsdokumentation.

## <a name="additional-resources"></a>Ytterligare resurser

- [E-fakturering – översikt](e-invoicing-service-overview.md)
- [Kom i gång med tjänstadministration för elektronisk fakturering](e-invoicing-get-started-service-administration.md)
- [Kom i gång med elektronisk fakturering](e-invoicing-get-started.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
