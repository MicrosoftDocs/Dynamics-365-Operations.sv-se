---
title: Installera och ansluta mobilappen Hantering av distributionslager
description: I det här avsnittet beskrivs hur du installerar mobilappen Hantering av distributionslager på alla dina mobila enheter och konfigurerar den för anslutning till din Microsoft Dynamics 365 Supply Chain Management-miljö.
author: MarkusFogelberg
ms.date: 02/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysAADClientTable, WHSMobileAppField, WHSMobileAppFieldPriority, WHSRFMenu, WHSRFMenuItem, WHSWorker
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: 267694
ms.assetid: d95d43b2-13ff-4189-a71a-3a1fb57d55ed
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mafoge
ms.search.validFrom: 2021-02-28
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 810592bcbe11b03753c12ab7bfe6160d3e9233ee
ms.sourcegitcommit: c53de2c09b9296b41653e739178edf29f79e0679
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/17/2021
ms.locfileid: "6049326"
---
# <a name="install-and-connect-the-warehouse-management-mobile-app"></a>Installera och ansluta mobilappen Hantering av distributionslager

[!include [banner](../includes/banner.md)]

> [!NOTE]
> Det här ämnet beskriver hur man konfigurerar mobilappen för distributionslagerhantering. Mer information om hur du konfigurerar en gamla distributionslagerappen (nu inaktuell) finns i [Installera och koppla in distributionslagerappen](../../supply-chain/warehousing/install-configure-warehousing-app.md).

I det här avsnittet beskrivs hur du laddar ner och installerar mobilappen Hantering av distributionslager på alla dina mobila enheter och konfigurerar appen den för anslutning till din Supply Chain Management-miljö. Du kan konfigurera varje enhet manuellt eller också kan du importera anslutningsinställningar via en fil eller genom att skanna en QR-kod.

## <a name="system-requirements"></a>Systemkrav

Mobilappen Hantering av distributionslager är tillgänglig för både operativsystemet Google Android och operativsystemet Windows. Om du vill använda det här programmet måste du ha något av följande operativsystem som stöds installerade på dina mobila enheter:

- Windows 10 (Universal Windows Platform \[UWP\]) oktober 2018 uppdatering 1809 (version 10.0.17763) eller senare
- Android 4.4 eller senare

## <a name="turn-on-the-feature"></a>Aktivera en funktion

Innan du kan använda appen måste relaterad funktion aktiveras i ditt system. Administratörer kan använda arbetsytan [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den om det behövs. Funktionen visas på följande sätt:

- **Modul:** *Lagerstyrning*
- **Funktionsnamn:** *användarinställningar, ikoner och stegrubriker för den nya distributionslagerappen*

## <a name="get-the-warehouse-management-mobile-app"></a>Skaffa mobilappen Hantering av distributionslager

För mindre distributioner kanske du vill installera appen från den relevanta butiken på respektive enhet och sedan manuellt konfigurera anslutningen till de miljöer du använder.

Vid större distributioner kan du automatisera appdistributionen och/eller konfigurationen, vilket kan vara bättre om du hanterar många enheter. Du kan till exempel använda en mobil enhetshantering och en lösning för mobilapphantering som [Microsoft Intune](/mem/intune/fundamentals/what-is-intune). Information om hur du använder Intune för att lägga till program finns i [Lägga till appar i Microsoft Intune](/mem/intune/apps/apps-add).

### <a name="install-the-app-from-an-app-store"></a>Installera programmet från en appbutik

Det enklaste sättet att installera programmet på en enskild enhet är att installera det från en appbutik, som alltid innehåller den senaste, generellt tillgängliga versionen. Microsoft Intune kan också hämta program från appbutikerna. Använd någon av följande länkar när du installerar programmet från en appbutik:

- **Windows (UWP):** [Lagerstyrning i Microsoft Store](https://www.microsoft.com/store/apps/9pd35cdqcmg3)

- **Android:** [Lagerstyrning på Google Play Store](https://play.google.com/store/apps/details?id=com.Microsoft.WarehouseManagement)

### <a name="download-the-app-from-microsoft-app-center"></a>Hämta programmet från Microsoft App Center

Ett alternativ till att installera från en appbutik är att hämta programmet från Microsoft App Center. App Center innehåller avinstallationsbara paket som du kan separat inläsning. Utöver den aktuella versionen kan du även hämta tidigare versioner med App Center, och du kan förse förhandsgranskningsversioner med kommande funktioner som du kan prova. Om du vill hämta aktuella, tidigare eller förhandsgranskningsversioner av mobilapplikationen Lagerstyrning från Microsoft App Center använder du någon av följande länkar:

- **Windows (UWP):** [Lagerstyrning (Windows)](https://go.microsoft.com/fwlink/?linkid=2154406)  
    För instruktioner om hur du installerar ett nedladdat paket på en Windows-enhet och sedan ställer in nödvändiga certifikat, se [Installera en version från App Center](/appcenter/distribution/installation).

- **Android:** [distributionslagerhantering (Android)](https://go.microsoft.com/fwlink/?linkid=2154613)  
    Om du laddar ner en förhandsgranskningsversion krävs några extra steg för att installera den. Mer information finns i [Testa Android-appar](/appcenter/distribution/testers/testing-android).

## <a name="create-a-web-service-application-in-azure-active-directory"></a><a name="create-service"></a>Skapa ett webbtjänstprogram i Azure Active Directory

Om du vill att mobilappen Hantering av distributionslager ska interagera med en viss Supply Chain Management-server måste du registrera ett webbtjänstprogram i en klientorganisation för Supply Chain Management i Azure Active Directory (Azure AD). Följande procedur anger ett sätt att skapa slutföra denna uppgift. Mer information och alternativ finns bland länkarna efter proceduren.

1. I en webbläsare går du till [https://portal.azure.com](https://portal.azure.com/).
1. Ange namn och lösenord för den användare som har tillgång till Azure-abonnemanget.
1. I Azure-portalen väljer du i det vänstra navigeringsfönstret **Azure Active Directory**.

    ![Azure Active Directory](media/app-connect-azure-aad.png "Azure Active Directory")

1. Se till att du arbetar med den instans av Azure AD som används av Supply Chain Management.
1. I listan **Hantera** väljer du **App-registreringar**.

    ![App-registreringar](media/app-connect-azure-register.png "App-registreringar")

1. I verktygsfältet väljer du **Ny registrering** för att öppna guiden **Registrera ett program**.
1. Ange ett namn på programmet, välj alternativet **Endast konton i denna organisationskatalo** och sedan **Registrera**.

    ![Guiden Registrera ett program](media/app-connect-azure-register-wizard.png "Guiden Registrera ett program")

1. Din nya programregistrering öppnas. Anteckna värdet för **Program-ID (klient)** eftersom du kommer att behöva detta senare. Detta ID benämns *klient-ID* längre fram i detta avsnitt.

    ![Program-ID (klient)](media/app-connect-azure-app-id.png "Program-ID (klient)")

1. I listan **Hantera** väljer du **Certifikat och hemligheter**. Välj sedan någon av följande knappar, beroende på hur du vill konfigurera appen för autentisering. (Mer information finns under [Autentisera med hjälp av ett certifikat eller en klienthemlighet](#authenticate) senare i det här avsnittet.)

    - **Ladda upp certifikat** – Ladda upp ett certifikat som ska användas som hemlighet. Vi rekommenderar detta tillvägagångssätt eftersom det är säkrare och även kan automatiseras helt. Om du kör mobilappen Hantering av distributionslager på Windows-enheter ska du anteckna det värde för **tumavtryck** som visas när du har laddat upp certifikatet. Du kommer att behöva detta värde när du konfigurerar certifikatet på Windows-enheter.
    - **Ny klienthemlighet** – Skapa en nyckel genom att ange en nyckelbeskrivning och en varaktighet i avsnittet **Lösenord**, och välj sedan **Lägg till**. Skapa en kopia av nyckeln och spara den på ett säkert sätt.

    ![Certifikat & hemligheter](media/app-connect-azure-authentication.png "Certifikat & hemligheter")

Mer information om hur du ställer in webbtjänstprogram i Azure AD finns i följande resurser:

- Instruktioner som visar hur du använder Windows PowerShell för att skapa webbtjänstprogram i Azure AD finns i [Så här använder du Azure PowerShell för att skapa ett tjänstekonto med ett certifikat](/azure/active-directory/develop/howto-authenticate-service-principal-powershell).
- Mer information om hur du manuellt skapar ett webbtjänstprogram i Azure AD finns i följande avsnitt:

    - [Snabbstart: Registrera ett program med Microsofts identitetsplattform](/azure/active-directory/develop/quickstart-register-app)
    - [Så här använder du portalen för att skapa ett Azure AD-program och ett tjänstekonto som har åtkomst till resurser](/azure/active-directory/develop/howto-create-service-principal-portal)

## <a name="create-and-configure-a-user-account-in-supply-chain-management"></a>Skapa och konfigurera ett användarkonto i Supply Chain Management

Gör så här om du vill låta Supply Chain Management använda ditt Azure AD-program.

1. Skapa en användare som motsvarar autentiseringsuppgifterna för mobilappen Hantering av distributionslager:

    1. I Supply Chain Management går du till **Systemadministration \> Användare \> Användare**.
    1. Skapa en användare.
    1. Tilldela användaren av den mobila enheten för lagerstyrningsenheten.

    ![Tilldela användaren av den mobila enheten för lagerstyrningsenheten](media/app-connect-app-users.png "Tilldela användaren av den mobila enheten för lagerstyrningsenheten")

1. Koppla ditt Azure AD-program till användaren av mobilappen Hantering av distributionslager:

    1. Gå till **Systemadministration \> Konfiguration \> Azure Active Directory-program**.
    1. Skapa en rad.
    1. Ange det klient-ID som du noterade i föregående avsnitt, ge det ett namn och välj sedan den användare du just skapat. Vi rekommenderar att du taggar alla enheter. Om en enhet går förlorad kan du enkelt ta bort åtkomsten till Supply Chain Management från den här sidan.

    ![Azure Active Directory-program](media/app-connect-aad-apps.png "Azure Active Directory-program")

## <a name="authenticate-by-using-a-certificate-or-client-secret"></a><a name="authenticate"></a>Autentisera med hjälp av ett certifikat eller en klienthemlighet

Autentisering med Azure AD är ett säkert sätt att ansluta en mobil enhet till Supply Chain Management. Du kan autentisera med hjälp av antingen en klienthemlighet eller ett certifikat. Om du vill importera anslutningsinställningar rekommenderar vi att du använder ett certifikat istället för en klienthemlighet. Eftersom klienthemligheten alltid måste lagras på ett säkert sätt kan du inte importera den från en anslutningsinställningsfil eller en QR-kod, enligt beskrivningen längre fram i det här avsnittet.

Certifikat kan användas som hemligheter för att bevisa programmets identitet när en token begärs. Den offentliga delen av certifikatet överförs till app-registreringen i Azure-portalen, medan det fullständiga certifikatet måste distribueras på varje enskild enhet där mobilappen Hantering av distributionslager installeras. Organisationen ansvarar för att hantera certifikatet i fråga om rotation osv.. Du kan använda självsignerade certifikat, men du bör alltid använda icke-exporterbara certifikat.

Du måste göra certifikatet tillgängligt lokalt på varje enskild enhet där du kör mobilappen Hantering av distributionslager. Information om hur du hanterar certifikat för Intune-styrda enheter om du använder Intune finns i [Använda certifikat för autentisering i Microsoft Intune](/mem/intune/protect/certificates-configure).

## <a name="configure-the-application-by-importing-connection-settings"></a>Konfigurera programmet genom att importera anslutningsinställningar

För att göra det enklare att underhålla och distribuera programmet på många mobila enheter kan du importera anslutningsinställningarna istället för att ange dem manuellt på varje enskild enhet. Detta avsnitt innehåller information om hur du skapar och importerar inställningar.

### <a name="create-a-connection-settings-file-or-qr-code"></a>Skapa en inställningsfil eller QR-kod för anslutning

Du kan importera anslutningsinställningar från antingen en fil eller en QR-kod. För båda metoder måste du först skapa en inställningsfil som använder format och syntax för JSON (JavaScript Object Notation). Filen måste innehålla en anslutningslista som innehåller de enskilda anslutningar som måste läggas till. I följande register sammanfattas de parametrar som du måste ange i filen med anslutningsinställningar.

| Parameter | beskrivning |
|---|---|
| Anslutningsnamn | Ange namnet på anslutningsinställningen. Du kan använda upp till 20 tecken. Eftersom detta värde är den unika identifieraren för en anslutningsinställning måste du se till att den är unik i listan. Om en anslutning med samma namn redan finns på enheten åsidosätts den av inställningarna från den importerade filen. |
| ActiveDirectoryClientAppId | Ange det klient-ID som du har angivit under installationen av Azure AD i avsnittet [Skapa ett webbtjänstprogram i Azure Active Directory](#create-service). |
| ActiveDirectoryResource | Ange rot-URL för Supply Chain Management. |
| ActiveDirectoryTenant | Ange den Azure AD-klientorganisation som du använder med Supply Chain Management-servern. Detta värde har formuläret `https://login.windows.net/<your-Azure-AD-tenant-ID>`. Här är ett exempel: `https://login.windows.net/contosooperations.onmicrosoft.com`. |
| Företag | Ange den juridiska person i Supply Chain Management som du vill att programmet ansluter till. |
| ConnectionType | (Valfritt) Ange om anslutningsinställningen ska använda ett certifikat eller en klienthemlighet för att ansluta till en miljö. Giltiga värden är *"certificate"* och *"clientsecret"*. Standardvärdet är *"certificate"*.<p>**Obs!** Det går inte att importera klienthemligheter.</p> |
| IsEditable | (Valfritt) Ange om programanvändaren ska kunna redigera anslutningsinställningen. Giltiga värden är *"true"* och *"false"*. Standardvärdet är *"true"*. |
| IsDefault | (Valfritt) Ange om anslutningen är standardanslutningen. En anslutning som är angiven som standardanslutning markeras automatiskt när appen öppnas. Endast en anslutning kan anges som standaranslutning. Giltiga värden är *"true"* och *"false"*. Standardvärdet är *"false"*. |
| CertificateThumbprint | (Valfritt) För Windows-enheter kan du ange certifikatets tumavtryck för anslutningen. För Android-enheter måste app-användaren välja certifikatet första gången en anslutning används. |

Följande exempel visar en giltig fil med anslutningsinställningar som innehåller två anslutningar. Som du ser är anslutningslistan (kallad *"ConnectionList"* i filen) ett objekt som har en matris som lagrar varje anslutning som ett objekt. Varje objekt måste stå inom klamrar ({}) och avgränsas med kommatecken, och matrisen måste omges av hakparenteser (\[\]).

```json
{
    "ConnectionList": [
        {
            "ActiveDirectoryClientAppId":"aaaaaaaa-bbbb-ccccc-dddd-eeeeeeeeeeee",
            "ConnectionName": "Connection1",
            "ActiveDirectoryResource": "https://yourenvironment.cloudax.dynamics.com",
            "ActiveDirectoryTenant": "https://login.windows.net/contosooperations.onmicrosoft.com",
            "Company": "USMF",
            "IsEditable": false,
            "IsDefaultConnection": true,
            "CertificateThumbprint": "aaaabbbbcccccdddddeeeeefffffggggghhhhiiiii",
            "ConnectionType": "certificate"
        },
        {
            "ActiveDirectoryClientAppId":"aaaaaaaa-bbbb-ccccc-dddd-eeeeeeeeeeee",
            "ConnectionName": "Connection2",
            "ActiveDirectoryResource": "https://yourenvironment2.cloudax.dynamics.com",
            "ActiveDirectoryTenant": "https://login.windows.net/contosooperations.onmicrosoft.com",
            "Company": "USMF",
            "IsEditable": true,
            "IsDefaultConnection": false,
            "ConnectionType": "clientsecret"
        }
    ]
}
```

Du kan antingen spara informationen som en JSON-fil eller generera en QR-kod med samma innehåll. Om du sparar informationen som en fil rekommenderar vi att du sparar den med standardnamnet *connections.json*, särskilt om du kommer att lagra den på standardplatsen på respektive mobila enhet.

### <a name="save-the-connection-settings-file-on-each-device"></a>Spara filen med anslutningsinställningar på varje enskild enhet

Vanligtvis använder du ett verktyg för enhetshantering eller ett skript för att distribuera filerna med anslutningsinställningar till alla enheter som du hanterar. Om du använder standardnamn och -plats när du sparar filen med anslutningsinställningar på varje enhet importerar mobilappen Hantering av distributionslager den automatiskt, även under den första körningen efter det att appen har installerats. Om du använder ett anpassat namn eller en anpassad plats för filen måste programanvändaren ange värdena under den första körningen. Appen fortsätter dock att använda angivet namn och angiven plats efteråt.

Varje gång appen startas återimporterar den anslutningsinställningarna från dessas tidigare plats för att avgöra om några ändringar har gjorts. Appen uppdaterar bara anslutningar som har samma namn som anslutningarna i filen med anslutningsinställningar. Användarskapade anslutningar som använder andra namn uppdateras inte.

Du kan inte ta bort en anslutning med hjälp av filen med anslutningsinställningar.

Som har nämnts är standardfilnamnet *connections.json*. Standardfilens plats beror på om du använder en Windows-enhet eller en Android-enhet:

- **Windows:** `C:\Users\<User>\AppData\Local\Packages\Microsoft.WarehouseManagement_8wekyb3d8bbwe\LocalState`
- **Android:** `Android\data\com.Microsoft.WarehouseManagement\files`

Normalt skapas sökvägarna automatiskt när appen har körts för första gången. Du kan dock skapa dem manuellt om du måste överföra filen med anslutningsinställningar till enheten före installationen.

> [!NOTE]
> Om programmet avinstalleras tas standardsökvägen och dess innehåll bort.

### <a name="import-the-connection-settings"></a>Importera anslutningsinställningar

Följ dessa steg om du vill importera anslutningsinställningar från antingen en fil eller en QR-kod.

1. Starta mobilappen Hantering av distributionslager på din mobila enhet. Första gången du startar programmet visas ett välkomstmeddelande. Välj **Välj en anslutning**.

    ![Välkomstmeddelande](media/app-configure-welcome-screen.png "Välkomstmeddelande")

1. Om du importerar anslutningsinställningar från en fil kan det hända att appen redan har hittat filen om standardnamnet och standardplatsen användes när den sparades. I det här fallet går du vidare till steg 4. Annars väljer du **Ställ in anslutning** och fortsätter sedan till steg 3.

    ![Konfigurera anslutning](media/app-configure-set-up-connection.png "Konfigurera anslutning")

1. I dialogrutan **Konfiguration av anslutning** välj **Lägg till från fil** eller **Lägg till från QR-kod**, beroende på hur du vill importera inställningarna:

    - Om du importerar anslutningsinställningarna från en fil väljer du **Lägg till från fil**, bläddrar till filen på den lokala enheten och väljer den. Om du väljer en anpassad plats kommer appen att lagra den och använda den automatiskt nästa gång.
    - Om du importerar anslutningsinställningar genom att skanna en QR-kod väljer du **Lägg till från QR-kod**. I appen uppmanas du att ange din behörighet att använda enhetens kamera. När du har gett ditt tillstånd startar kameran så att du kan använda den för skanning. Beroende på kvaliteten på enhetens kamera och hur pass komplex QR-koden är, kan det vara svårt att få en korrekt genomsökning. I så fall kan du försöka minska komplexiteten i QR-koden genom att bara skapa en anslutning per QR-kod. (För närvarande kan du endast använda enhetens kamera för att skanna QR-koden.)

    ![Meny för konfiguration av anslutning](media/app-configure-connection-setup-flyout.png "Meny för konfiguration av anslutning")

1. När anslutningsinställningarna har lästs in visas den valda anslutningen.

    ![Inlästa anslutningsinställningar](media/app-configure-select-connection.png "Inlästa anslutningsinställningar")

1. Om du använder en Android-enhet och ett certifikat för autentisering uppmanas du av enheten att välja certifikatet.

    ![Välj certifikatuppmaning på en Android-enhet](media/app-configure-select-certificate.png "Välj certifikatuppmaning på en Android-enhet")

1. Appen ansluter till din Supply Chain Management-server och visar inloggningssidan.

    ![Inloggningssida](media/app-configure-sign-in-page.png "Inloggningssida")

## <a name="manually-configure-the-application"></a><a name="config-manually"></a>Konfigurera programmet manuellt

Om du inte har en fil eller en QR-kod kan du konfigurera programmet manuellt på enheten så att den ansluter till Supply Chain Management-servern via Azure AD-programmet.

1. Starta mobilappen Hantering av distributionslager på din mobila enhet.
1. Om programmet har startat i **Demoläget**, välj **Anslutningsinställningar**. Om **inloggningssidan** visas när programmet startas väljer du **Ändra anslutning**.
1. Välj **Ange anslutning**.

    ![Konfigurera anslutning](media/app-configure-set-up-connection.png "Konfigurera anslutning")

1. Välj **Inmatning manuellt**.

    ![Meny för konfiguration av anslutning](media/app-configure-connection-setup-flyout.png "Meny för konfiguration av anslutning")

    Sidan **Ny anslutning** visas för att expandera de inställningar som krävs för att ange anslutningsinformationen manuellt.

    ![Manuella anslutningsfält](media/app-configure-input-manually.png "Manuella anslutningsfält")

1. Ange följande information:

    - **Använd klienthemlighet** – Ställ in det här alternativet på _Ja_ om du vill använda en klienthemlighet för att autentisera med Supply Chain Management. Ställ in det på _Nej_ om du vill använda ett certifikat för autentisering. (Mer information finns i [Skapa ett webbtjänstprogram i avsnittet Azure Active Directory](#create-service) tidigare i det här avsnittet.)
    - **Anslutningsnamn** – Ange ett namn på den nya anslutningen. Det här namnet kommer att visas i fältet **Välj anslutning** nästa gång du öppnar anslutningsinställningarna. Det namn du anger måste vara unikt. (Med andra ord måste det skilja sig från alla andra anslutningsnamn som lagras på enheten, om det finns andra anslutningsnamn där).
    - **Klient-ID för Azure-katalog** – Ange det klient-ID som du noterade när du konfigurerade Azure AD i avsnittet [Skapa ett webbtjänstprogram i Azure Active Directory](#create-service).
    - **Klient-hemlighet för Active-katalog** – Det här fältet är endast tillgängligt när alternativet **Använd klienthemlighet** är inställt på _Ja_. Ange den klient-hemlighet som du har angivit under konfigurationen av Azure AD i avsnittet [Skapa ett webbtjänstprogram i Azure Active Directory](#create-service).
    - **Tumavtryck för certifikat för Active-katalog** – Det här fältet är endast tillgängligt för Windows-enheter när alternativet **Använd klienthemlighet** är inställt på _Nej_. Ange det tumavtryck för certifikat som du noterade när du konfigurerade Azure AD i avsnittet [Skapa ett webbtjänstprogram i Azure Active Directory](#create-service).
    - **Active-katalogresurs** – Ange rot-URL för Supply Chain Management.

        > [!IMPORTANT]
        > Avsluta inte det här värdet med ett snedstreck (/).

    - **Klientorganisation i Active-katalog** – Ange den Azure AD-klientorganisation som du använder med Supply Chain Management-servern. Detta värde har formuläret `https://login.windows.net/<your-Azure-AD-tenant-ID>`. Här är ett exempel: `https://login.windows.net/contosooperations.onmicrosoft.com`.

        > [!IMPORTANT]
        > Avsluta inte det här värdet med ett snedstreck (/).

    - **Företag** – Ange den juridiska person i Supply Chain Management som du vill att programmet ansluter till.

1. Klicka på knappen **Spara** längst upp till höger på sidan.
1. Om du använder en Android-enhet och ett certifikat för autentisering uppmanas du av enheten att välja certifikatet.
1. Appen ansluter till din Supply Chain Management-server och visar inloggningssidan.

## <a name="remove-access-for-a-device"></a>Ta bort åtkomsten för en enhet

Om en enhet går förlorad eller drabbas av fel, måste du ta bort åtkomsten till Supply Chain Management för enheten. Följande steg beskriver den rekommenderade processen för att ta bort åtkomst.

1. Gå till **Systemadministration \> Konfiguration \> Azure Active Directory-program**.
1. Ta bort den rad som motsvarar den enhet för vilken du vill ta bort åtkomsten. Anteckna vilket klient-ID som ska användas för enheten, eftersom du behöver det senare.

    Om du bara har registrerat ett klient-ID och flera enheter använder samma klient-ID, måste du distribuera nya anslutningsinställningar till dessa enheter. Annars kommer de att förlora åtkomsten.

1. Logga in på Azure-portalen på [https://portal.azure.com](https://portal.azure.com/).
1. I det vänstra navigeringsfönstret väljer du **Active Directory** och ser till att du befinner dig i rätt katalog.
1. I listan **Hantera** väljer du **App-registreringar** och sedan den app du vill konfigurera. Sidan **Inställningar** visas och anger konfigurationsinformation.
1. Kontrollera att klient-ID:t för programmet matchar det klient-ID som du noterade i steg 2.
1. Välj **Ta bort** i verktygsfältet.
1. Markera **Ja** i bekräftelsemeddelandet som visas.

## <a name="additional-resources"></a>Ytterligare resurser

- [Användarinställningar för mobil enhet](mobile-device-user-settings.md)
- [Tilldela stegikoner och titlar för mobilappen för Warehouse Management](step-icons-titles.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]