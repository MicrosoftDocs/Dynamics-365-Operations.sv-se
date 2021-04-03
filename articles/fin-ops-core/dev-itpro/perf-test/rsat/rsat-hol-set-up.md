---
title: Självstudie för att ställa in och installera Regression Suite Automation Tool
description: Det här avsnittet innehåller en vägledning om hur du ställer in och installerar RSAT (Regression Suite Automation Tool).
author: robinarh
manager: AnnBe
ms.date: 09/20/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ROBOTS: NOINDEX, NOFOLLOW
audience: Application User, Developer, IT Pro
ms.reviewer: rhaertle
ms.custom: 21761, NotInToc
ms.search.region: Global
ms.author: rhaertle
ms.search.validFrom: 2019-05-30
ms.dyn365.ops.version: AX 7.0.0, Operations
ms.openlocfilehash: ca1e0d61263ed19e7eab18f6ba6aec628b0295a8
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5568422"
---
# <a name="set-up-and-install-regression-suite-automation-tool-tutorial"></a>Självstudie för att ställa in och installera Regression Suite Automation Tool

Det här avsnittet är en vägledning som hjälper dig att få installationsprogrammet och komma igång med RSAT och verktygen för att använda RSAT.

[!include [banner](../../includes/banner.md)]

> [!NOTE]
> Använd webbläsarverktygen för att hämta och spara sidan i PDF-format.

## <a name="key-concepts"></a>Viktiga begrepp

- Förstå installationen och nödvändiga inställningar som krävs för de olika programmen som stöder RSAT (Regression Suite Automation Tool).
- Förstå hur funktionen uppgiftsinspelare tillsammans med Microsoft Dynamics Lifecycle Services (LCS) och Microsoft Azure DevOps, gör det möjligt att skapa, konfigurera, köra, undersöka och rapportera om testfall.
- Ge funktionella användare möjlighet att registrera affärsuppgifter med hjälp av uppgiftsregistrering och sedan konvertera inspelningsuppgifterna till en uppsättning automatiserade tester utan att källkoden behöver skrivas.

## <a name="before-you-begin"></a>Innan du börjar

### <a name="prerequisites"></a>Förutsättningar

- En miljö som kör Microsoft Dynamics 365 for Finance and Operations version 10.0 (april 2019) eller senare krävs för den här självstudien. För kunder som använder Microsoft Dynamics 365 for Finance and Operations Enterprise Edition 7.3, plattformsuppdatering 20 (PU20) eller senare stöds också.
- Användaren måste ha administratörsbehörighet till den här miljön.
- Du måste ha tillgång till kundens LCS-klientorganisation och Azure DevOps (kallades tidigare Microsoft Visual Studio Team Services \[VSTS\]).
- Användaren som skapar och hanterar testpaket måste ha en licens för Azure DevOps testplan eller testansvarig. Följande licenser kommer också att ge dig åtkomst till testplaner:
    - Visual Studio Enterprise-licens
    - Visual Studio Test Professional-licens
    - Prenumerationslicens för MSDN-plattformar
- RSAT måste ha åtkomst till testmiljön via en webbläsare.
- För att kunna generera och redigera testparametrar måste du ha Microsoft Excel installerat.

## <a name="configure-azure-devops"></a>Konfigurera Azure DevOps

### <a name="user-eligibility"></a>Användarberättigande

Se till att användaren har skapats i Azure DevOps och har en prenumerationsnivå som ger åtkomst till Azure testplaner. En Azure DevOps Test Plans-licens krävs endast om användaren ska skapa och hantera testfall (dvs. inte alla RSAT-användare behöver denna licens). Mer information om licens kraven finns i [licenskrav](https://docs.microsoft.com/azure/devops/test/manual-test-permissions#license-requirements).

### <a name="create-a-new-azure-devops-project"></a>Skapa ett nytt Azure DevOps-projekt

I RSAT använder Azure DevOps för testfall och testpaket hantering, rapportering och undersöka testkörningsresultat.

> [!NOTE]
> Du kan använda ett befintligt Azure DevOps-projekt. Om ditt befintliga Azure DevOps-projekt har konfigurerats så att det har en anpassad mall visas dock felmeddelandet "Fel vid VSTS-synkronisering" när du synkroniserar testfall från BPM (Affärsprocessmodelleraren) till Azure DevOps (se avsnittet [Testa synkroniseringen från BPM till Azure DevOps](#test-the-synchronization-from-bpm-to-azure-devops)). Om följande metodtips har följts för den anpassade mallen kommer du att kunna synkronisera test fallen med Azure DevOps. (De här metodtipsen finns i felmeddelandet.)

- Ta inte bort några arbetsuppgiftstyper eller färdigkonfigurerade fält
- Ta inte bort något tillstånd för en arbetsuppgiftstyp
- Lägg inte till några obligatoriska fält i en arbetsuppgiftstyp

![Felmeddelande med en lista över metodtips](./media/setup_rsa_tool_02.png)

I den här självstudien rekommenderar vi annars att du skapar ett nytt Azure DevOps-projekt. Mer information finns i [frågor vid synkronisering till BPM med hjälp av en anpassad Azure DevOps (VSTS) processmall](https://blogs.msdn.microsoft.com/lcs/2018/11/28/issues-when-syncing-to-bpm-using-a-custom-azure-devops-vsts-process-template/).

1. Öppna Azure DevOps-URL (`https://dev.azure.com/<Azure DevOps Name>`).
2. Klicka på knappen **Skapa projekt** längst upp till höger på Azure DevOps-sidan.

    ![Knappen Skapa projekt](./media/setup_rsa_tool_03.png)

3. Fyll i följande fält och välj sedan **skapa**:

    - **Projektnamn**
    - **Versionskontroll**  – Välj **Versionskontroll för Team Foundation**. Observera att standardalternativet **Git** inte stöds.
    - **Arbetsuppgiftprocess**

    ![Dialogrutan skapa nytt projekt](./media/setup_rsa_tool_04.png)

### <a name="create-a-personal-access-token"></a>Skapa ett token för personlig åtkomst

I den här självstudien ska du använda LCS affärsprocessmodelleraren (BPM) för att skapa ett testfallsbibliotek och synkronisera dina testfall med Azure DevOps. Du måste ha en personlig åtkomsttoken för att kunna synkronisera BPM med Azure DevOps.

1. Välj en profilikon i det övre högra hörnet på sidan för Azure DevOps-projektet och välj sedan **säkerhet**.

    ![Säkerhetskommando](./media/setup_rsa_tool_05.png)

2. Markera **personliga åtkomsttoken** i det vänstra fönstret under **säkerhet**. Välj sedan **ny token**.

    ![Knappen Ny token på fliken för personliga åtkomsttoken i användarinställningar](./media/setup_rsa_tool_06.png)

3. Fyll i följande fält och välj sedan **skapa**:

    - **Namn**
    - **Förfallodatum (UTC**) – Välj **anpassad definierad och använd sedan datumväljaren för att välja det sista tillgängliga datumet**.
    - **Oområde** – Markera alternativet **fullständig åtkomst**.

    ![Dialogrutan skapa en ny personlig åtkomsttoken](./media/setup_rsa_tool_07.png)

    > [!NOTE]
    > Anteckna vilken personlig åtkomsttoken som skapas. Du kommer att behöva det senare när du ställer in konfigurationen för RSAT.

    ![Token för personlig åtkomst](./media/setup_rsa_tool_08.png)

## <a name="configure-the-lcs-project"></a>Konfigurera LCS-projekt

Du behöver ett LCS-projekt (Lifecycle Services) för ditt huvudtestbibliotek. LCS affärsprocessmodelleraren (BPM) används som huvudbibliotek för testfallen. BPM används för att hantera och distribuera testbibliotek över LCS-projekt. En Microsoft-partner eller en oberoende programleverantör (ISV) för att skapa testbibliotek frigörs till exempel testfall i form av BPM-bibliotek. I BPM är testfall organiserade efter affärsprocess. BPM definierar inte körningsordningen eller frekvensen för testpass. Dessa detaljer hanteras i Azure DevOps vilket beskrivs mer utförligt i detta ämne.  

För det LCS-projektet kan du använda ett befintligt implementerings- eller partnerprojekt för kund.

### <a name="update-the-lcs-language"></a>Uppdatera LCS-språk

> [!NOTE]
> För användargränssnittet (UI) för att visa affärsprocesser korrekt måste LCS föredraget språk vara **engelska (USA)**.

1. Gå till själva LCS-implementeringsprojektet.
2. Välj knappen **inställningar** (växelsymbol) i det övre högra hörnet och välj sedan **Språkinställning**.

    ![Uppdatera språkinställning](./media/setup_rsa_tool_09.png)

3. I fältet **Föredraget språk**, välj **engelska (USA)** och välj sedan **Spara**.

    ![Fliken språkinställningar i användarinställningar](./media/setup_rsa_tool_10.png)

### <a name="configure-lcs-to-connect-to-the-azure-devops-project"></a>Konfigurera LCS för att ansluta till Azure DevOps-projektet

Om du skapade ett nytt Azure DevOps-projekt tidigare konfigurerar du LCS-projektet så att du kan ansluta till det. Om LCS-projektet redan är anslutet till ditt Azure DevOps-projekt kan du fortsätta till nästa avsnitt.

1. Gå till själva LCS-implementeringsprojektet.
2. Välj knappen **meny** och välj sedan **projektinställningar**.

    ![Projektinställningskommando](./media/setup_rsa_tool_11.png)

3. Markera **Visual Studio Team Services** i det vänstra fönstret och välj sedan **konfigurera Visual Studio Team Services**.

    ![Fliken Visual Studio Team Services i projektinställningar](./media/setup_rsa_tool_12.png)

4. Ange **Azure DevOps webbplatsens URL** i fältet Azure DevOps webbplats-URL. I fältet **personlig åtkomsttoken** anger du den personliga åtkomsttoken som skapades tidigare.

    > [!NOTE]
    > Ãven om VSTS nu kallas Azure DevOps kan du använda den gamla URL för att ansluta LCS till Azure DevOps-projektet. Till exempel den Azure DevOps-URL som används i den här självstudien är `https://dev.azure.com/D365FOFastTrack/`. I följande illustration är det dock angivet som `https://D365FOFastTrack.visualstudio.com/`.

    ![Steg 1 i Konfigurera Visual Studio Team Services](./media/setup_rsa_tool_13.png)

5. Välj **Fortsätt**.
6. I fältet **Visual Studio Team Services-projekt** väljer du det VSTS-projekt på den valda webbplatsen för att koppla med LCS-projekt. Som standard anges fältet **processmall** till **Agile**. Om du vill ha en anpassad mall ska du läsa metodtipsen i avsnittet [Skapa ett nytt Azure DevOps-projekt](#create-a-new-azure-devops-project). Välj sedan **Fortsätt**.

    ![Steg 2 i Konfigurera Visual Studio Team Services](./media/setup_rsa_tool_14.png)

7. Granska inställningarna och välj sedan **Spara**.

    ![Steg 3 i Konfigurera Visual Studio Team Services](./media/setup_rsa_tool_15.png)

8. Välj **Auktorisera** för att auktorisera LCS för åtkomst till den konfigurerade Azure DevOps-platsen för din räkning och aktivera funktioner som är integrerade med VSTS.

    ![Knappen auktorisera](./media/setup_rsa_tool_16.png)

9. En meddelanderutan visas som anger: Du omdirigeras till en extern webbplats för en att ge LCS behörighet att ansluta till Visual Studio Team Services för din räkning. Villl du fortsätta? Välj **Ja**.

    ![Meddelanderuta](./media/setup_rsa_tool_17.png)

10. Välj **Godkänn**.

    ![Auktorisera åtkomst](./media/setup_rsa_tool_18.png)

11. Om du är auktoriserad som användare ska du gå tillbaka till sidan LCS-projektinställningar.

    ![Behöriga användare](./media/setup_rsa_tool_19.png)

### <a name="create-a-new-bpm-library"></a>Skapa ett nytt BPM-bibliotek

1. Gå till själva LCS-implementeringsprojektet.
2. Välj knappen **meny** och välj sedan **affärsprocessmodelleraren**.

    ![Kommandot Affärsprocessmodelleraren](./media/setup_rsa_tool_20.png)

3. Välj ett **Nytt bibliotek**.

    ![Knappen Nytt bibliotek](./media/setup_rsa_tool_21.png)

4. I fältet **biblioteksnamn** anger du ett namn och väljer sedan **skapa**. I den här självstudien namnger du BPM-biblioteket **RSAT**.

    ![Dialogrutan skapa nytt bibliotek](./media/setup_rsa_tool_22.png)

5. Öppna det nya BMP-biblioteket för **BPM**.
6. Välj affärsprocessen **Sample Core Business Process** och välj **redigeringsläge** till höger.

    ![Knappen Redigeringsläge](./media/setup_rsa_tool_23.png)

7. Ändra värdet för både fältet **Namn** och fältet **Beskrivning** för att **skapa en produkt**. Välj sedan **Spara**.

    ![Fälten namn och beskrivning](./media/setup_rsa_tool_24.png)

## <a name="environment"></a>Miljö

### <a name="version-requirement"></a>Versionskrav

Ett test- eller begränsat läge-miljö som kör version 10 krävs. För kunder som använder version 7.3, plattformsuppdatering 20 eller senare stöds också.

> [!NOTE]
> RSAT måste ha åtkomst till testmiljön via en webbläsare.

### <a name="user-criteria"></a>Användarkriterier

Användaren måste ha administratörsbehörighet till den här miljön.

### <a name="set-up-help-settings-to-connect-with-lcs"></a>Konfigurera hjälpinställningar för anslutning med LCS

Det här steget krävs för att ansluta med LCS så att uppgiftsregistreringar kan sparas i lämpligt BPM-bibliotek i LCS via klienten.

1. Öppna klienten.
2. Navigera till **Systemadministration \> Inställningar \> Systemparametrar**.
3. På fliken **Hjälp** i fältet **Hjälpkonfiguration för Lifecycle Services**, välj relevant LCS-projekt (**RSAT** för denna självstudie).

    ![Lifecycle Services hjälper konfigurationsfält på fliken Hjälp](./media/setup_rsa_tool_25.png)

    BPM-bibliotek fylls i under lämpligt LCS-projekt.

4. Välj **Spara**.
5. Du kanske måste uppdatera webbläsaren för att kunna se det uppdaterade hjälpinnehållet.

    ![Meddelande om uppdatering av webbläsaren](./media/setup_rsa_tool_26.png)

## <a name="task-recordings"></a>Uppgiftsinspelningar

> [!NOTE]
> Kontrollera att alla uppgiftsinspelningar startar på huvudinstrumentpanelen. Hålla enskilda inspelningar korta och fokusera på en affärsuppgift, t.ex. skapa en försäljningsorder.

### <a name="create-a-task-recording-and-save-it-to-the-bpm-library"></a>Skapa en uppgiftsinspelning och spara den i BPM-biblioteket

Skapa en motsvarande uppgiftsinspelning som du kan koppla till den enkla affärsprocess som skapades i det nya BPM-biblioteket.

1. Öppna klienten.
2. Välj knappen **inställningar** (växelsymbolen) och sedan **Uppgiftsinspelare**.

    ![Välj Uppgiftsinspelare på Menyn Inställningar](./media/setup_rsa_tool_27.png)

3. Välj **Skapa registrering**.

    ![Knappen Skapa registrering](./media/setup_rsa_tool_28.png)

4. Fyll i fälten **inspelningsnamn** och **inspelningsbeskrivning** och välj sedan **starta**.

    ![Fälten Inspelningens namn och Inspelningens beskrivning.](./media/setup_rsa_tool_29.png)

5. Registrera stegen för att skapa en produkt. När du är klar väljer du **stoppa** om du vill stoppa inspelningen.

    ![Steg för att skapa en produkt](./media/setup_rsa_tool_30.png)

6. Välj **Spara till Lifecycle Services**.

    ![Spara uppgiftsregistrering i Lifecycle Services](./media/setup_rsa_tool_31.png)

    Biblioteksinformationen läses in från LCS.

    ![Läsa in biblioteksinformation](./media/setup_rsa_tool_32.png)

7. Välj BPM-bibliotek som ska associeras med uppgiftsinspelningen. För den här självstudien väljer du **RSAT** BPM-biblioteket, som skapades tidigare och affärsprocessen **Skapa en produkt** under det. Välj sedan **OK**.

    ![Associera en uppgiftsinspelning med ett BPM-bibliotek och en affärsprocess](./media/setup_rsa_tool_33.png)

    Meddelandet Spara till Lifecycle Services slutfördes visas.

    ![Meddelande om lyckad sparning till LCS](./media/setup_rsa_tool_34.png)

8. Gör så här om du vill spara uppgiftsinspelningen lokalt och sedan överföra den till BPM via LCS:

    1. När inspelningen har slutförts väljer su **Spara på den här datorn**.

        ![Spara på datorn](./media/setup_rsa_tool_35.png)

    2. I webbläsarens meddelandefält väljer du **Spara** eller **Spara som** om du vill spara filen på den lokala datorn.

        ![Meddelandefält](./media/setup_rsa_tool_36.png)

    3. Gå till **RSAT** BPM-biblioteket och välj den affärsprocess som du vill spara uppgiftsinspelningen mot.
    4. På fliken **översikt** väljer du **överför**.

        ![Knappen Överför](./media/setup_rsa_tool_37.png)

    5. Välj **bläddra** och markera den .axtr-fil som du sparade tidigare. Välj sedan **överför**.

        ![Välja vilken .axtr-fil som ska överföras](./media/setup_rsa_tool_38.png)

### <a name="test-the-synchronization-from-bpm-to-azure-devops"></a>Testa synkroniseringen från BPM till Azure DevOps

Nu när en uppgiftsinspelning är kopplad till affärsprocessen måste du validera att affärsprocessen och den tillhör ande uppgiftsinspelningen kan synkroniseras till Azure DevOps som en funktion och ett testfall med hjälp av VSTS-synkroniseringsfunktionen i LCS.

> [!NOTE]
> Motsvarande arbetsuppgiftstyp som skapades i Azure DevOpsvarierar beroende på vilken procesmall du valde när du konfigurerade LCS-projektet med Azure DevOps, som beskrivs i avsnittet [skapa ett nytt Azure DevOps-projekt](#create-a-new-azure-devops-project).

1. Gå till BPM-biblioteket och öppna det **RSAT**-bibliotek som du skapade tidigare.
2. Markera ellips-knappen (**...**) och välj **VSTS-synkronsiering**.

    ![Kommandot VSTS-synkronsiering på ellips-menyn](./media/setup_rsa_tool_39.png)

    När VSTS-synkroniseringen är slutförd visas fliken **krav** på vänster sida och innehåller motsvarande Azure DevOps-arbetsuppgift.

    > [!NOTE]
    > Arbetsuppgiften som skapas i Azure DevOps kommer att ha BPM-biblioteksnamnet som rubrikprefix.

    ![Fliken Krav](./media/setup_rsa_tool_40.png)

3. Uppdatera sidan.
4. Markera ellips-knappen (**...**). Du kommer att se ett ytterligare alternativ **Synkronisera testfall**. Välj det här alternativet .

    ![Kommandot synkronisera testfall på ellips-menyn](./media/setup_rsa_tool_41.png)

    > [!NOTE]
    > Om alternativet **synkronisera testfall** inte är tillgängligt när du har uppdaterat sidan går du till huvudsidan för BPM och väljer **synkronisera testfall** för hela biblioteket. På så sätt framtvingar du effektivt en synkronisering av hela biblioteket.
    >
    > ![Välja synkronisering av testfall för hela biblioteket](./media/setup_rsa_tool_42.png)

    När synkroniseringen av testfall hargjorts skapas ett nytt testfall på fliken **krav**.

    ![Nytt testfall på fliken Krav](./media/setup_rsa_tool_43.png)

5. Gå till Azure DevOps-projektet och välj **Tavlor \> Arbetsuppgifter**.

    ![Kommandot arbetsuppgifter under tavlor](./media/setup_rsa_tool_44.png)

6. Validera att arbetsuppgiften och testfallet som du skapade genom BPM-synkronisering finns.

    ![Arbetsuppgift och testfall](./media/setup_rsa_tool_45.png)

## <a name="install-and-configure-rsat"></a>Installera och konfigurera RSAT

RSAT kan installeras på alla datorer som kör Windows 10 och som kan ansluta till miljö via en webbläsare (Internet Explorer eller Google Chrome).

> [!NOTE]
> Innan du installerar en ny version av verktyget rekommenderar vi att du avinstallerar den tidigare versionen.

### <a name="install-an-authentication-certificate"></a>Installera ett autentiseringscertifikat

Om du vill aktivera autentisering måste du generera och installera ett certifikat på samma dator som RSAT körs på.

#### <a name="generate-a-certificate"></a>Generera ett certifikat

1. Om du vill generera en certifikatfil öppnar du Microsoft Windows PowerShell-fönster som administratör och kör följande kommando.

    ```powershell
    $certificate = New-SelfSignedCertificate -dnsname 127.0.0.1 -CertStoreLocation cert:\LocalMachine\My -FriendlyName "D365 Automated testing certificate" -Provider "Microsoft Strong Cryptographic Provider"
    ```

2. Öppna certifikathanterare genom att ange **certlm.msc** i dialogrutan **Kör** och bekräfta attcertifikatet **D365-automatiserad testning** har skapats under **personliga \> certifikat**.

    > [!NOTE]
    > Glöm inte att ange **certlm.msc**, inte **certmgr.msc**, eftersom certifikaten lagras på den lokala datorn.

    ![D365 för automatisk testning av certifikat](./media/setup_rsa_tool_46.png)

3. Högerklicka i certifikatet och välj sedan **Kopiera**.
4. Gå till **certifikat till betrodda rotcertifikatutfärdare \> certifikat**.

    ![Mappen Certifikat under mappen Betrodda rotcertifikatutfärdare](./media/setup_rsa_tool_47.png)

5. På menyn **Åtgärd**, välj **Klistra in** om du vill kopiera certifikatet till platsen **certifikat till betrodda rotcertifikatutfärdare**.

    ![Kommandot Klistra in på Åtgärd-menyn](./media/setup_rsa_tool_48.png)

6. Om du vill hämta tumavtrycket för det installerade certifikatet, men utan blanksteg eller specialtecken, öppnar du ett Windows PowerShell-fönster som administratör och kör följande kommandon.

    ```powershell
    cd Cert:\LocalMachine\My

    Get-ChildItem | Where-Object { $_.Subject -like "CN=127.0.0.1" }
    ```

    > [!NOTE]
    > Spara tumavtrycket eftersom du kommer att behöva det senare när du uppdaterar .wif-filerna för programobjektserver (AOS) och ställ in RSAT-konfigurationen.

#### <a name="configure-the-aos-computer-to-trust-the-connection"></a>Konfigurera AOS-datorn så att den betror anslutningen

> [!NOTE]
> Om miljön är en Nivå 2+-miljö, måste tumavtrycket för certifikatet uppdateras i filen wif.config för **alla** AOS-datorer för miljön.

1. Upprätta en RDP-anslutning (Remote Desktop Protocol) till AOS-datorn. Inloggningsinformation finns på miljöns informationssida i LCS.
2. Öppna Microsoft Internet Information Services (IIS) och sök efter **AOSService** i listan över webbplatser.

    ![AOSService i listan över webbplatser](./media/setup_rsa_tool_49.png)

3. Högerklicka på **Utforska** för att öppna mappen **\<Drive\>: \\AosService\\WebRoot**. Leta upp filen **wif.config**.

    ![Filen wif.config i mappen WebRoot](./media/setup_rsa_tool_50.png)

4. Uppdatera filen **wif.config** genom att lägga till en ny auktoritetspost för ditt certifikat och auktoritetsnamn, som i följande exempel.

    ```Xml
    <issuerNameRegistry type="Microsoft.Dynamics.AX.Security.SharedUtility.AxIssuerNameRegistry,Microsoft.Dynamics.AX.Security.SharedUtility">
        <authority name="CN=127.0.0.1">
            <keys>
                <add thumbprint="xxxxxxxxxxxxxxxxxxxx" />
                <add thumbprint="xxxxxxxxxxxxxxxxxxxx" />
            </keys>
            <validIssuers>
                <add name="CN=127.0.0.1" />
            </validIssuers>
        </authority>
    ```

    > [!NOTE]
    > Om flera användare använder samma program, måste alla användare generera separata tumavtryck och alla dessa tumavtryck måste läggas till i avsnittet **\<keys\>**.

5. Om det finns fler än en AOS-dator upprepar du steg 3 till och med 4 för varje ytterligare dator.

    > [!NOTE]
    > Till skillnad från äldre miljöer med nivå 2 distribueras nya miljöer med nivå 2 med två AOS-instanser.

6. Kör **iisreset** på alla AOS-datorer.

    > [!NOTE]
    > Om du inte har administratörsbehörighet för att köra **iisreset** på en dator på nivå 1 väljer du Underhåll > Starta om tjänster på sidan Miljödetaljer i LCS.

#### <a name="tier-2-environment"></a>Nivå 2+-miljö

Om en nivå 2+ (sandbox med standardacceptanstest eller högre) miljö används, kontrollerar eller anger du följande registerinställning på datorn där RSAT har installerats. Det här steget är obligatoriskt eftersom det hjälper dig att undvika anslutningsfel för autentisering eller RSAT.

```PowerShell
if ((Test-Path HKLM:\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v4.0.30319))
{
    Set-ItemProperty HKLM:\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v4.0.30319 -Name SchUseStrongCrypto -Value 1 -Type dword -Force -Confirm:$false
}
```

### <a name="install-rsat"></a>Installera RSAT

1. Gå till <https://www.microsoft.com/download/details.aspx?id=57357> och välj **Hämta**.
2. Markera alla filer och välj **nästa**.

    ![Markera alla filer](./media/setup_rsa_tool_51.png)

3. Dubbelklicka på .msi-paketet för att köra installationsprogrammet. Sedan när installationen är slutförd väljer du **Slutför**.

    ![Installationsfil för RSAT](./media/setup_rsa_tool_52.png)

### <a name="install-selenium-and-browser-drivers"></a>Installera drivrutiner för Selenium och webbläsare

I tidigare versioner av RSAT var du tvungen att installera drivrutiner för Selenium och webbläsare. Du behöver inte längre installera dessa drivrutiner eftersom de installeras automatiskt.

1. Första gången du öppnar RSAT uppmanas du att automatiskt hämta och installera Selenium. Mer information finns i avsnittet [ Konfigurera RSAT](#configure-rsat).
2. Innan du kan köra ett testfall uppmanas du att automatiskt hämta och installera drivrutinen för webbläsaren som motsvarar standardwebbläsaren som väljs i konfigurationen för RSAT. Mer information finns i avsnittet [Läsa in och köra testfall](#load-and-run-test-cases).

## <a name="get-started-with-rsat"></a>Kom igång med RSAT

### <a name="create-a-test-plan-and-test-suites"></a>Skapa en testplan och testpaket

1. Gå till Azure DevOps-projektet och välj **testplaner**.

    ![Testplaner, kommando](./media/setup_rsa_tool_53.png)

2. Välj **ny testplan**.

    ![Knappen Ny testplan](./media/setup_rsa_tool_54.png)

3. Fyll i fältet **Namn** och välj sedan **Skapa**. I den här självstudien namnger du **RSAT-testplan**.

    ![Dialogrutan ny testplan](./media/setup_rsa_tool_55.png)

4. Välj plustecknet (**+**) och välj sedan **statiskt paket** för att skapa en statiskt paket under den nya testplanen. Ange ett namn på det nya testpaketet **T01 – Tillverka mot lager**.

    > [!NOTE]
    > Du kan också skapa ett frågebaserat paket om du vill att de nya testfallen från BPM ska hämtas automatiskt till testpaketet för RSAT.

    ![Skapa en statiskt paket](./media/setup_rsa_tool_56.png)

### <a name="attach-test-cases-to-test-suites"></a>Bifoga testfall till testpaket

1. Välj **Lägg till befintlig** på höger sida om du vill lägga till befintliga testfall i testprogrammet.

    ![Knappen Lägg till befintlig](./media/setup_rsa_tool_57.png)

2. På sidan **Lägg till testfall till paket** väljer du **Kör fråga** och väljer sedan det testfall som ska läggas till i testpaketet. För den här självstudien väljer du testfallet **Skapa enny produkt**. Välj sedan **Lägg till testfall** i det nedre högra hörnet på sidan (den här knappen visas inte på följande bild).

    ![Knappen Kör fråga](./media/setup_rsa_tool_58.png)

    Testfall som läggs till i testfallet **T01 - Tillverka mot lager**.

    ![Testfall tillagt i testpaketet](./media/setup_rsa_tool_59.png)

### <a name="configure-rsat"></a>Konfigurera RSAT

1. Öppna RSAT

    ![RSAT-ikon](./media/setup_rsa_tool_60.png)

2. Du får ett varningsmeddelande om att "Regression Suite Automation Tool kräver Selenium, vill du att det automatiskt ska hämtas och installeras nu?" Välj **Ja**.

    ![Varningsmeddelande som Regression Suite Automation Tool kräver Selenium](./media/setup_rsa_tool_61.png)

3. Välj knappen **inställningar** (kugghjulssymbolen) i det övre högra hörnet och fyll sedan i följande fält i dialogrutan som visas:

    - **Azure DevOps Url** – Anger URL för ditt Azure DevOps-projekt, t.ex. `https://yourAzureDevOpsUrlHere.visualStudio.com`.
    - **Åtkomsttoken** – ange den åtkomsttoken som gör att verktyget kan ansluta till Azure DevOps. Använd den personliga åtkomsttoken som du skapade tidigare i den här självstudien. Mer information finns i autentisera [åtkomst med privata åtkomsttoken](https://www.visualstudio.com/docs/setup-admin/team-services/use-personal-access-tokens-to-authenticate).
    - **Projektnamn** – Välj namnet på Azure DevOps-projektet.
    - **Testplan** – Välj Azure DevOps testplanen som innehåller testfallen. Mer information finns i [skapa testplaner och testpaket](https://www.visualstudio.com/docs/test/manual-exploratory-testing/getting-started/create-a-test-plan). När du har valt en testplan väljer du **testa anslutning** för att testa anslutningen till Azure DevOps.
    - **Värdnamn** – Ange värdnamnet på testmiljön, som **\<myaos\>.cloudax.dynamics.com**. Ta inte med prefixet **https://** eller **http://**.
    - **SOAP-värdnamn** – ange SOAP-värdnamnet för testmiljön. Vanligt vis är SOAP-värdnamnet detsamma som värdnamnet, men det har ett **soap**-suffix. Här följer ett exempel: **\<myaos\>soap.cloudax.dynamics.com**. Ta inte med prefixet **https://** eller **http://**.

        > [!NOTE]
        > Om du vill hitta värdnamnet och namnet på SOAP-värddatorn, öppna IIS-hanterare, högerklicka på **Webbplatser \> AOSService** och välj sedan **redigera bindningar**. Värdena i kolumnen **värdnamn** ger värdnamnet och namnet på SOAP-värddatorn (SOAP-värdnamnet har suffixet **soap** i URL).

        ![Värdnamnet och SOAP-värdnamnet i kolumnen värdnamn](./media/setup_rsa_tool_63.png)

    - **Användarnamn för administratören** – Ange e-postadressen för en administratörsanvändare i testmiljön.
    - **Tumavtryck** – Ange certifikatets tumavtryck, enligt beskrivningen ovan i den här självstudien.
    - **Arbetskatalog** – ange mappens plats där du vill lagra testautomatiseringsfiler, t.ex. Excel-testdatafiler. Skriv t.ex. eller välj **C:\\Temp\\RegressionTool**.

        > [!NOTE]
        > Om namnet på mappen innehåller blanksteg misslyckas körningen eftersom mappen inte kan hittas. Det här problemet är ett känt problem och bör korrigeras i den senaste versionen av verktyget.

    - **Standardwebbläsare** – Välj antingen **Internet Explorer** eller **Google Chrome**. Kontrollera att rätt drivrutiner för webbläsarfilen har installerats.
    - **Tidsgräns för testkörning** – ange tidsgränsen i minuter för testkörningarna. När tidsgränsen går ut stängs alla aktiva fönster och väntande testfall misslyckas.
    - **Teståtgärdens tidsgräns** – det här fältet styr tidsgränsen, i minuter, för Finance and Operation-miljöns serverbegäran. Normalt bör standardvärdet (2 minuter) vara tillräckligt. För långsammare miljöer kan det dock vara bra att öka värdet om fel som rör tidsgränden uppstår.
    - **Företagsnamn** – ange vilket företagsnamn som ska användas som standardföretag när Excel-parameterfiler skapas. Du kan ändra företaget senare genom att redigera Excel-parameterfilen.

    ![Dialogrutan Inställningar](./media/setup_rsa_tool_62.png)

4. Välj **tillämpa** om du vill tillämpa och spara inställningarna.

    Om du vill spara de aktuella inställningarna i en konfigurationsfil på din dator väljer du **Spara som**. Om du vill återställa dina inställningarna från en konfigurationsfil på din dator väljer du **Öppna**.

5. Välj **Stäng** för att stänga dialogrutan.

### <a name="load-and-run-test-cases"></a>Läs in och kör testfall

1. Välj **Läs in** föratt läsa in testplanen **RSAT-testplan** från Azure DevOps-projektet.

    ![Knappen Läs in](./media/setup_rsa_tool_64.png)

2. Välj **skapa en ny produkt** testfall från testpaketet och välj sedan **ny \> generera testkörning och parameterfil**.

    ![Generera kommandon Testkörning och Parameterfiler på menyn Ny](./media/setup_rsa_tool_65.png)

    Excel-parameterfilen skapas i den lokala mapp som du har angett i RSAT-konfigurationen (t.ex. **C:\\Temp\\RegressionTool**).

    ![Excel-parameterfilen skapas](./media/setup_rsa_tool_66.png)

3. Om du vill spara parametervärdena väljer du **överför**. Testautomatiseringsfiler för alla valda testfall överförs till Azure DevOps för framtida användning. (Dessa filer inkluderar även Excel-testparameterfiler.)

    På så sätt kan du välja **Läs in** för att läsa in parametervärdena (och automatiseringsfiler) från testfall direkt från Azure DevOps. Du behöver inte generera om parameterfilerna. Den här metoden kommer att bli viktig senare när du vill behålla ändringarna i parameterfilen och inte vill att de ska skrivas över.

4. Om du vill kontrollera att automatiseringsfiler och parameterfilerna sparas i Azure DevOps, gå till Azure DevOps-projektet och välj **Tavlor \> Arbetsuppgifter** och välj sedan testfallet **Skapa en ny produkt**. På fliken **bifogade filer** ska du se fyra filer:

    - **.cs** – C\# automatiseringsfil
    - **.dll** – kompilerad automatiseringsfil som en sammansättning
    - **.xlsx** – Excel-parameterfil
    - **.xml** – Inspelningsfil

    ![Filer på fliken Bifogade filer](./media/setup_rsa_tool_67.png)

5. Välj det testfall som ska köras och välj sedan **kör**.

    > [!NOTE]
    > Innan du kör testfall, om du använder Internet Explorer som webbläsare kontrollerar du att din skrivbordsupplösning är inställd på **100 %** på **Inställningar för Windows-display \> Skala och layout**. Om du inte kan ändra den här inställningen på en virtuell dator (VM) ändrar du den på klienten (den bärbara datorn) som du försöker komma åt den virtuella datorn från. Inställningarna för upplösning kommer sedan att ärvas av inställningarna för den virtuella datorns bildskärm.

    ![Skärmupplösningen är inställd på 100 %](./media/setup_rsa_tool_68.png)

6. Om drivrutinerna för webbläsaren inte är installerade i systemet visas ett varningsmeddelande om "Den här åtgärden kräver drivrutin för \<browser name\>. Vill du att den automatiskt ska hämtas och installeras nu?" Välj **Ja**.

    ![Varningsmeddelande för Internet Explorer](./media/setup_rsa_tool_69.png)

    ![Varningsmeddelande för Chrome](./media/setup_rsa_tool_70.png)

    > [!NOTE]
    > Om du använder Chrome som webbläsare och får ett felmeddelande om att sessionen inte skapades eftersom den inte är korrekt, hämtar du den senaste Chrome-drivrutinen från <http://chromedriver.chromium.org/downloads> till mappen **C:\\Programfiler (x86)\\Regression Suite Automation Tool\\Vanliga\\Externa\\Selenium**.

    ![Felmeddelande för Chrome](./media/setup_rsa_tool_71.png)

    Testfall körs och fältet **resultat** uppdateras.

    ![Uppdaterat resultatfält](./media/setup_rsa_tool_72.png)

    Om du har följt den här vägledningen som den är skriven kommer testfallet **Skapa en ny produkt** att misslyckas eftersom uppgiftsinspelningen för att skapa en produkt har sparade produktnamnet som ett hårdkodat värde. Om du kör samma testfall igen bör du få ett felmeddelande, eftersom produkten redan finns.

    ![Fältet Resultat angavs till misslyckat](./media/setup_rsa_tool_72.png)

### <a name="view-the-test-results"></a>Visa testresultaten

1. Dubbelklicka på det misslyckade testfallet.

    Du får ett felmeddelande.

    ![Felmeddelande](./media/setup_rsa_tool_73.png)

2. Välj **Detaljer** om du vill visa hela felmeddelandet.

    ![Hela felmeddelande](./media/setup_rsa_tool_74.png)

3. Om du vill visa en detaljerad version av felmeddelandet i Azure DevOps väljer **Öppna i Azure DevOps**. I Azure DevOps kan du visa status för testfallet och det detaljerade felmeddelandet.

    ![Detaljerat felmeddelande i Azure DevOps](./media/setup_rsa_tool_75.png)

4. Om du vill visa testresultaten direkt i Azure DevOps-projektet går du till **testplaner \> testplaner \> körs**. Dubbelklicka på testkörningen som du vill ha mer information om.

    ![Lista över testkörningar i Azure DevOps](./media/setup_rsa_tool_76.png)

5. Fliken **Kör sammanfattning** anger att testfallet misslyckades, men det inte ger det faktiska felmeddelandet. Om du vill visa det detaljerade felmeddelandet väljer du fliken **testresultat**.

    ![Kör fliken Sammanfattning](./media/setup_rsa_tool_77.png)

    På fliken **Testresultat** finns information om testfall tillsammans med resultatet och felmeddelandet.

    ![Fliken Testresultat](./media/setup_rsa_tool_78.png)

6. Dubbelklicka på den relevanta posten så visas ett detaljerat felmeddelande.

    ![Detaljerat felmeddelande](./media/setup_rsa_tool_79.png)

    > [!NOTE]
    > Alla felmeddelanden finns också lokalt i **C:\\Användare\\\$YourUserName\\AppData\\Roaming\\regressionTool\\errormsg-.txt**.

7. Du kan också exportera testresultaten från testplannivån genom att välja **exportera**.

    ![Exportera en testplan](./media/setup_rsa_tool_80.png)

### <a name="modify-the-excel-parameter-file"></a>Modifiera Excel-parameterfil

1. Öppna RSAT
2. Markera testfallen och välj sedan **redigera** för att öppna Excel-parameterfil.

    På arket **EcoResProductCreate**, observera att värdetpå fältet **produktnummer** är hårdkodat. Du måste uppdatera det här fältet till ett nytt produktnummer innan du kör testfallet igen.

3. Om du vill skapa ett unikt produktnummer för varje körning utan att behöva öppna Excel-parameterfilen på nytt och uppdatera produktnumret manuellt varje gång, använder du följande Excel-formel.

    ```vba
    ="RSAT_"&TEXT(NOW(),"yyymmddhhmm")
    ```

    > [!NOTE]
    > Förutom fliken **allmänt** innehåller Excel-parameterfilen en dataflik för varje formulärsida som testfallet besöker.

    ![Fältet Produktnummer](./media/setup_rsa_tool_81.png)

4. Markera **Spara** och stäng sedan Excel-arbetsboken.
5. Välj **överför** om du vill spara Excel-parameterfilen på Azure DevOps.

    ![Meddelandet Uppladdning klar](./media/setup_rsa_tool_82.png)

    > [!NOTE]
    > Om du vill köra testfall i en specifik användarkontext anger du användarens e-post-ID **testanvändare** på fliken **Allmänt** i Excel-parameterfilen. I den senaste versionen av RSAT har layouten för fälten i Excel-parameterfilen uppdaterats, men konceptet förblir oförändrat.
    >
    > ![Fältet Testanvändare](./media/setup_rsa_tool_83.png)

### <a name="validate-the-results"></a>Validera resultaten

- Välj **kör** för att köra testfallet igen och kontrollera att testfallet har godkänts. Du kan visa testresultaten enligt beskrivningen i avsnittet [Visa testresultat](#view-the-test-results).

    ![Fältet Resultat angavs till Godkänt](./media/setup_rsa_tool_84.png)

### <a name="chaining-of-test-cases"></a>Kedja av testfall

En nyckelegenskap i RSAT är en kedja av testfall (det vill säga förmågan hos ett test för att överföra värden till andra tester). Testfall körs enligt deras definierade ordning i Azure DevOps-testplan. (Den här ordningen kan också uppdateras i själva testverktyget.) Om du vill överföra variabler från ett testfall till ett annat, är det därför mycket viktigt att testen finns i rätt ordning.

I det här avsnittet skapar du en sparad variabel i det första testfallet, skapar ett andra testfall och skickar den sparade variabeln från det första testfallet till det andra testfallet. Sedan kör du testfallen som ett kedjetestfall i RSAT.

#### <a name="modify-an-existing-task-recording-to-create-a-saved-variable"></a>Ändra en befintlig uppgiftsinspelning för att skapa en sparad variabel

1. Öppna klienten.
2. Välj knappen **inställningar** (växelsymbolen) och sedan **Uppgiftsinspelare**.
3. Välj **redigera inspelning**.

    ![Knappen Redigera inspelning](./media/setup_rsa_tool_85.png)

4. Välj **Öppna från Lifecycle Services**.

    ![Knappen Öppna från Lifecycle Services](./media/setup_rsa_tool_86.png)

5. Välj **Lifecycle Services-bibliotek**

    ![Knappen Välj Lifecycle Services-bibliotek](./media/setup_rsa_tool_87.png)

    BPM-bibliotek läses in från LCS.

    ![Läser in BPM-bibliotek](./media/setup_rsa_tool_88.png)

6. När du har läst in BPM-biblioteken från LCS väljer du **RSAT** BPM-biblioteket och affärsprocessen **Skapa enny produkt** som uppgiftsinspelningen var associerad med. Välj sedan **OK**.

    ![Välj ett BPM-bibliotek och en affärsprocess](./media/setup_rsa_tool_89.png)

7. Namnet på lämplig uppgiftsinspelning anges i fältet **inspelningsnamn**. Välj **start**.

    ![Namn på uppgiftsinspelningen i fältet Inspelningsnamn](./media/setup_rsa_tool_90.png)

8. Gå till **produktinformationshantering \> produkter** och välj **Ny** om du vill öppna sidan med den ursprungliga uppgiftsinspelningen, **Skapa en produkt** spelades in.
9. Välj **infoga steg**.

    > [!NOTE]
    > Det nya steget infogas **efter** steget som du valde i fönstret.

    ![Knappen Infoga steg](./media/setup_rsa_tool_91.png)

10. Högerklicka i fältet **produktnummer** och välj sedan **uppgiftsinspelning \> Kopia**.

    ![Kopiera kommando](./media/setup_rsa_tool_92.png)

11. Ett nytt steg läggs till i fönstret. Anteckna värdet i fältet **produktnummer** eftersom det senare kommer att bli nödvändigt.

    ![Nya steg har lagts till](./media/setup_rsa_tool_93.png)

12. Välj **Redigeringen är slutförd**.
13. Välj **Spara till Lifecycle Services** och koppla den nya uppgiftsinspelningen till samma BPM-bibliotek och affärsprocess som den ursprungliga uppgiftsinspelningen var kopplad till. Mer information finns i avsnittet [skapa en uppgiftsinspelning och spara den i BPM-biblioteket](#create-a-task-recording-and-save-it-to-the-bpm-library).
14. Gå till BPM-biblioteket och välj **Synkronisera testärenden** om du vill skriva över den uppgiftsinspelning som är kopplad till testfallet i Azure DevOps, enligt beskrivningen i avsnittet [testa synkronisering från BPM till Azure DevOps](#test-the-synchronization-from-bpm-to-azure-devops).
15. Öppna RSAT och välj **Läs in** om du vill läsa in alla testfall i testpaketet på nytt. Du måste generera om automatiserings- och parameterfiler genom att välja testfall och sedan välja **Ny \> Generera testkörnings- och parameterfiler**, enligt beskrivningen i avsnittet [Läs in och kör testfall](#load-and-run-test-cases).

    > [!NOTE]
    > Om Excel-parametern har lämnats öppen kommer omgenereringen att misslyckas. Kontrollera därför att Excel-parametern för testfall är stängd innan du genererar den nya parameterfilen för Excel.

16. Välj **redigera** om du vill öppna den nya Excel-parametern. Du kommer att se en ny post för **Sparad variabel** på rad 9. Den här variabeln, **{{EcoResProductCreate\_Identification\_ProductNumber\_Copy}}** sparas i uppgiftsinspelningens XML-fil och kan användas i efterföljande tester.

    ![Sparad variabelpost](./media/setup_rsa_tool_94.png)

#### <a name="create-a-new-test-case"></a>Skapa ett nytt testfall

1. Gå till **RSAT** BPM-biblioteket.
2. Välj processen **Sample Support Business Process** och välj **redigeringsläge** till höger.
3. Ändra värdet för både fältet **Namn** och fältet **Beskrivning** för att **Frisläpp en produkt**. Välj sedan **Spara**.

    ![Namn och beskrivning har ändrats till Frisläpp en produkt](./media/setup_rsa_tool_95.png)

#### <a name="create-a-new-task-recording-that-has-a-validate-function"></a>Skapa en ny uppgiftsinspelning som har en valideringsfunktion

- Skapa en uppgiftsinspelning om du vill frisläppa den produkt som skapades tidigare till den USRT juridiska personen. Mer information finns i avsnittet [skapa en uppgiftsinspelning och spara den i BPM-biblioteket](#create-a-task-recording-and-save-it-to-the-bpm-library).

    > [!NOTE]
    > För sammankopplade testfall rekommenderar vi alltid att du söker efter eller filtrerar posten som du behöver genom att *manuellt skriva värdet i fältet*. På så sätt kan du i verktyget bestämma vilken post som åtgärden måste vidtas mot i det efterföljande testfallet.

    ![Ny uppgiftsinspelning som har en valideringsfunktion](./media/setup_rsa_tool_96.png)

    Som den föregående visar,efter att produkten hittas genom att använda snabbfiltret, men efter att du har valt **Frisläpp produkter**, måste du validera värdet av fältet **Produktnummer** för att se till att produkt-ID:t är det produkt-ID som skapades tidigare. Om du vill validera värdet högerklickar du på fältet **produktnummer** och väljer sedan **uppgiftsinspelning \> validera \> aktuellt värde**.

    ![Valider det aktuella värdet](./media/setup_rsa_tool_97.png)

#### <a name="save-the-task-recording-to-bpm"></a>Spara uppgiftsinspelning till BPM

1. När uppgiftsinspelningen har slutförts väljer du **Spara till Lifecycle Services**.

    ![Spara slutförd uppgiftsregistrering i Lifecycle Services](./media/setup_rsa_tool_98.png)

2. Biblioteksinformationen läses in från LCS.

    ![Läsa in biblioteksinformation från LCS](./media/setup_rsa_tool_99.png)

3. Välj BPM-bibliotek som ska associeras med uppgiftsinspelningen. För den här självstudien väljer du **RSAT** BPM-biblioteket, som skapades tidigare och affärsprocessen **Frisläpp en produkt** under det. Välj sedan **OK**.

#### <a name="sync-bpm-to-azure-devops"></a>Synkronisera BPM till Azure DevOps

1. Gå till BPM-biblioteket och öppna biblioteket för **RSAT**.
2. Välj **VSTS-synkronisering** och **synkronisera testfall**. Mer information finns i avsnittet [testa synkroniseringen från BPM till Azure DevOps](#test-the-synchronization-from-bpm-to-azure-devops).

    När synkroniseringen är slutförd visas den nya arbetsuppgiften och motsvarande testfall för affärsprocessen **frisläppa en produkt** som visas i Azure DevOps på **Tavlor \> Arbetsartiklar**.

#### <a name="add-the-new-test-case-to-the-existing-test-suite"></a>Lägg till det nya testfallet i det befintliga testpaketet

1. Gå till **testplaner \> testplaner** och markera planen **RSAT-testplan**.
2. Välj **Lägg till befintlig**.
3. På sidan **Lägg till testfall i paket** väljer du **Kör fråga**.
4. Välj det nya testfallet som har skapats för **Frisläppa en produkt** och välj sedan **Lägg testfall** i det nedre högra hörnet på sidan (den här knappen visas inte i bilden nedan).

    ![Lägg till testfall på sidan Paket](./media/setup_rsa_tool_100.png)

    Testpaketet har nu två testfall.

    ![Två testfall i testpaketet.](./media/setup_rsa_tool_101.png)

#### <a name="load-test-cases-into-rsat"></a>Läs in testfall i RSAT

1. Öppna RSAT och välj **Läs in**.
2. Testfallen läses in och du får en varning om att "den här åtgärden skriver över Excel-testdatafilerna, lokala ändringar går förlorade. Vill du fortsätta?" Välj **ja** om du vill uppdatera Excel-parametervärdena i det lokala systemet, men inte de Excel-parametervärden som överförts till Azure DevOps.

    ![Den här åtgärden skriver över Excel-testdatafiler](./media/setup_rsa_tool_102.png)

    Båda testfallen läses in, tillsammans med Excel-parametern för det första testfallet. Eftersom du valde **överför** i den senaste körningen hämtas parametervärdena från Azure DevOps.

    ![Testfall har lästs in](./media/setup_rsa_tool_103.png)

3. Markera bara det andra testfallet och välj sedan **ny \> generera testkörning och parameterstyrda filer**.

#### <a name="edit-the-excel-parameter-file"></a>Redigera Excel-parameterfilen.

1. Markera endast det andra testfallet och välj sedan **redigera** för att öppna motsvarande Excel-parameterfil.
2. Kopiera **{{EcoResProductCreate\_Identification\_ProductNumber\_Copy}}** sparad variabel (se avsnittet [Ändra en befintlig uppgiftsinspelning för att skapa en sparad variabel](#modify-an-existing-task-recording-to-create-a-saved-variable)) från det första testfallet till alla fält där produktnumret används. I det här fallet kopierar du variabeln till fälten **produktnummer** och **validera produktnummer** på arket **EcoResProductListPage**.

    ![Fält för produktnummer och validera produktnummer](./media/setup_rsa_tool_104.png)

    > [!NOTE]
    > Variabler kan bara skickas mellan tester under samma testkörning. Namnen på variablerna måste matcha exakt.

3. Markera **Spara** och stäng sedan Excel-arbetsboken.
4. Välj **överför** om du vill spara ändringarna som du gjorde i Excel-parameterfilen.

#### <a name="run-the-chained-test-cases"></a>Kör kedjetestfallen

1. Välj båda testfallen och välj sedan **kör**.
2. Kontrollera att båda testfallen har godkänts.

    ![Resultatfältet har godkänts för båda testfallen](./media/setup_rsa_tool_105.png)


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]