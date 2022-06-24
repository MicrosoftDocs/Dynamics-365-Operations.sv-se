---
title: Ställa in en B2C-innehavare i Commerce
description: I denna artikel beskrivs hur du konfigurerar din Azure Active Directory (Azure AD) B2C-innehavare (Business-to-Consumer) för autentisering av användarplats i Dynamics 365 Commerce.
author: BrianShook
ms.date: 05/05/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: brshoo
ms.search.validFrom: 2020-02-13
ms.dyn365.ops.version: ''
ms.openlocfilehash: 4b1ee8999717d70dfe36baef95921962a1b7be65
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8853751"
---
# <a name="set-up-a-b2c-tenant-in-commerce"></a>Ställa in en B2C-innehavare i Commerce

[!include [banner](includes/banner.md)]

I denna artikel beskrivs hur du konfigurerar din Azure Active Directory (Azure AD) B2C-innehavare (Business-to-Consumer) för autentisering av användarplats i Dynamics 365 Commerce.

Dynamics 365 Commerce använder Azure AD B2C för att stödja autentiseringsuppgifter för användare och verifikationsflöden. En användare kan registrera sig, logga in och återställa sitt lösenord genom dessa flöden. Azure AD B2C lagrar känslig information om användarautentisering, t.ex. användarnamn och lösenord. Användarposten i B2C-innehavaren kommer att lagra antingen en B2C lokal kontopost eller en post för en B2C social identitetsleverantör. Dessa B2C-poster kommer att länkas tillbaka till kundposten i Commerce-miljön.

> [!WARNING] 
> Azure AD B2C drar tillbaka gamla (äldre) användarflöden senast den 1 augusti 2021. Därför bör du planera att flytta dina användarflöden till den nya rekommenderade versionen. Den nya versionen innehåller funktionen paritet och nya funktioner. Modulbiblioteket för Commerce version 10.0.15 eller högre ska användas med de rekommenderade B2C-användarflödena. Mer information finns i [Arbetsflöden i Azure Active Directory B2C](/azure/active-directory-b2c/user-flow-overview).
 
 > [!NOTE]
 > Utvärderingsmiljöer för Commerce kommer med en förinläst Azure AD B2C-innehavare för demonstration. Inläsning av din egen Azure AD B2C-innehavare med hjälp av stegen nedan krävs inte för utvärderingsmiljöer.

> [!TIP]
> Du kan skydda dina webbplatsanvändare ytterligare och förbättra säkerheten för dina Azure ADB2C-klientorganisationer idenhetsskydd och villkorlig åtkomst för Azure AD. Information om hur du granskar funktionerna för Azure AD B2C Premium P1- och Premium P2-innehavare finns i [Idenhetsskydd och villkorlig åtkomst för Azure AD B2C ](/azure/active-directory-b2c/conditional-access-identity-protection-overview).

## <a name="dynamics-environment-prerequisites"></a>Förutsättningar för Dynamics-miljö

Innan du börjar måste du se till att din Dynamics 365 Commerce-miljö och näthandelskanal är konfigurerad på rätt sätt genom att uppfylla följande förutsättningar.

- Ställ in kassaåtgärders värde **AllowAnonymousAccess** till "1" i Commerce headquarters:
    1. Gå till **Kassaåtgärder**.
    1. I åtgärdsrutnätet, högerklicka och välj **Personanpassa**.
    1. Välj **Lägg till ett fält**.
    1. I listan över tillgängliga kolumner väljer du kolumnen **AllowAnonyousAccess** för att lägga till den.
    1. Välj **Uppdatera**.
    1. För åtgärden **612** "Lägga till kund" ändrar du **AllowAnonymousAccess** till "1."
    1. Kör jobbet **1090 (register)**.
- Ställ in nummerseriekundkontots attribut **Manuellt** till **Nej** i Commerce Headquarters:
    1. Öppna **Retail och Commerce \> Administrationsinställning \> Parametrar \> Parametrar för kundreskontra**.
    1. Välj **Nummerserier**.
    1. Dubbelklicka på värdet för **Nummerseriekod** på raden **Kundkonto**.
    1. På snabbfliken **Allmänt** för nummerserien ställer du in **Manuellt** till **Nej**.

När du har distribuerat din Dynamics 365 Commerce-miljö bör du också [initiera startdata](enable-configure-retail-functionality.md) i miljön.

## <a name="create-or-link-to-an-existing-azure-ad-b2c-tenant-in-the-azure-portal"></a>Skapa eller länka till en befintlig Azure AD B2C-klientorganisation i Azure-portalen

Det här avsnittet innehåller information om hur du skapar eller länkar en Azure AD B2C-innehavare som ska användas på din handelsplats. Mer information finns i [Självstudie: Skapa en Azure Active Directory B2C klientorganisation](/azure/active-directory-b2c/tutorial-create-tenant).

1. Logga in på [Azure-portal](https://portal.azure.com/).
1. Från Azure-portal menyn, välj **skapa en resurs**. Se till att använda den prenumeration och katalog som kommer att vara ansluten till din Commerce-miljö.

    ![Skapa en resurs i Azure-portalen.](./media/B2CImage_1.png)

1. Gå till **identitet \>Azure Active Directory B2C**.
1. På sidan **Skapa ny B2C-klient eller länk till befintlig klient** använder du ett av alternativen nedan som bäst passar ditt företags behov:

    - **Skapa en ny Azure AD B2C innehavare**: Använd det här alternativet om du vill skapa en ny Azure AD B2C innehavare.
        1. Välj **Skapa ett nytt Azure AD B2C-innehavare**.
        1. Ange **organisationsnamnet** under organisationsnamn.
        1. Under **Initialt domännamn**, ange initialt domännamn.
        1. För **land eller region** välj land eller region.
        1. Välj **skapa** om du vill skapa innehavaren.

     ![Skapa en ny Azure AD-klientorganisation.](./media/B2CImage_2.png)

     - **Länka en befintlig Azure AD B2C-innehavare till min Azure-prenumeration**: Använd det här alternativet om du redan har en Azure AD B2C innehavare som du vill länka till.
        1. Välj **länka en befintlig Azure AD B2C-klient till mitt Azure-abonnemang**.
        1. Välj **Azure AD B2C innehavare** välj för B2C-innehavaren. Om meddelandet "inga bidragsberättigande B2C-innehavare hittades" visas i urvalsrutan har du inte en giltig B2C klientorganisation och behöver skapa en ny.
        1. För **Resursgrupp**, välj **Skapa nya**. Ange ett **namn** på den resursgrupp som ska innehålla innehavaren, välj **Välj resursgruppens plats** och välj **sedan skapa**.

    ![Länka en befintlig Azure AD B2C-klientorganisation till ett Azure-abonnemang.](./media/B2CImage_3.png)

1. När den nya Azure AD B2C skapas (detta kan ta en stund) visas en länk till den nya katalogen på instrumentpanelen. Länken leder till sidan "Välkommen till Azure Active Directory B2C".

    ![Länk till ny Azure AD-katalog](./media/B2CImage_4.png)

> [!NOTE]
> Om du har flera prenumerationer inom ditt Azure-konto eller har ställt in B2C-klienten utan att länka till en aktiv **prenumeration**, kommer en felsökningsannons att leda till att du kopplar klienten till en prenumeration. Markera felsökningsmeddelandet och följ instruktionerna för att lösa prenumerationsproblemet.

Följande bild visar ett exempel på en Azure AD B2C **felsökning** banderoll.

![Varnings som anger att katalogen inte har någon aktiv prenumeration.](./media/B2CImage_5.png)

## <a name="create-the-b2c-application"></a>Skapa B2C-applikationen

När B2C-innehavaren har skapats kommer du att skapa ett B2C-program inom din nya Azure AD B2C-innehavare för att samverka med Commerce.

Gör så här om du vill skapa ett B2C-applikation.

1. I Azure-portalen, gå till **Appregistreringar** och välj **Ny registrering**.
1. Under **Namn** anger du det namn som ska ge den här Azure AD B2C-applikationen.
1. Under **Kontotyper som stöds**, välj **Konton i valfri identitetsleverantör eller organisationskatalog (för autentisering av användare med användarflöden)**.
1. För **Omdirigerings-URI** anger du de dedikerade svars-URL av typen **Webb**. För information på svar-URL och hur du formaterar dem, se [Svars-URL](#reply-urls) nedan. En URL för omdirigerad URI/svar måste anges för att det ska gå att omdirigera från Azure AD B2C tillbaka till webbplatsen när en användare autentiserar. Svars-URL kan läggas till under registreringsprocessen eller läggas till senare genom att du väljer länken **Lägg till en omdirigerad URI** från menyn **Översikt** i avsnittet **Översikt** för B2C-programmets översikt.
1. För **Behörigheter**, välj **Bevilja administratörens samtycke till openid och offline_access behörigheter**.
1. Välj **Registrera**.
1. Välj det nyskapade programmet och navigera till menyn **Autentisering**. 
1. Om en svars-URL anges, under **Implicita bidrag och hybridflöden** välj både alternativet **Åtkomsttoken** och **ID-token** för att aktivera dem för programmet och välj sedan **Spara**. Om ingen svars-URL har angetts under registreringen kan den också läggas till på den här sidan genom att välja **Lägg till en plattform**, välja **webb** och sedan ange program- och omdirigerar-URI. Avsnitten **Implicita bidrag och hybridflöden** är tillgänglig för att välja både **Åtkomsttoken** och **ID-token**.
1. Gå till menyn **Översikt** i Azure-portal och kopiera **Program-ID (klient)**. Notera detta ID för senare installationssteg (refereras senare till som **Klient GUID**).

För ytterligare referens om appregistreringar i Azure AD B2C, se [Den nya appregistreringsupplevelsen för Azure Active Directory B2C](/azure/active-directory-b2c/app-registrations-training-guide)

### <a name="reply-urls"></a>Svars-URL

Svars-URL är viktiga eftersom de ger en tillåten-lista med returdomänerna när platsen anropar Azure AD B2C för autentisering av en användare. På så sätt tillåts den autentiserade användaren returnera tillbaka till den domän som de loggar in på (din webbplatsdomän). 

I rutan **Svars-URL** på skärmen **Azure AD B2C – program \> Ny program** måste du lägga till separata rader för både din webbplatsdomän och (när din miljö har etablerats) den URL som genereras av Commerce. URL-adresserna får alltid använda ett giltigt URL-format och måste bara vara bas-URL:er (inga snedstreck eller sökvägar kan avslutas). Strängen ``/_msdyn365/authresp`` måste läggas till i bas-URL:erna, som i följande exempel.

- ``https://www.fabrikam.com/_msdyn365/authresp`` (Domänen ska matcha näthandelsdomänen helt. Om du har flera domäner måste du lägga till denna URL för varje domän.)
- ``https://fabrikam-prod.commerce.dynamics.com/_msdyn365/authresp``

## <a name="create-user-flow-policies"></a>Skapa policyer för användarflöden

Användarflöden är de policyer Azure AD B2C använder för att tillhandahålla säker inloggning, registrera, redigera profil och glömma användarupplevelser för lösenord. Dynamics 365 Commerce använder dessa flöden för att utföra policyåtgärder för samverkan med Azure AD B2C-innehavaren. När en användare interagerar med dessa principer, omdirigeras de till Azure AD B2C-innehavaren för att utföra åtgärderna.

Azure AD B2C har tre grundläggande användarflödestyper:
- Registrera dig och logga in
- Profilredigering
- Återställ lösenord

Du kan välja att använda standard användarflöden som tillhandahålls av Azure AD, vilket visar en sida som finns i Azure AD B2C. Du kan också skapa en HTML-sida för att kontrollera hur dessa användarflödesupplevelser ser ut och fungerar. 

Information om hur du anpassar sidorna med sidorna inbyggda i Dynamics 365 Commerce finns i [Konfigurera användarsidor för användarinloggningar](custom-pages-user-logins.md). Mer information finns i [Anpassa gränssnittet för användarupplevelser i Azure Active Directory B2C](/azure/active-directory-b2c/tutorial-customize-ui).

### <a name="create-a-sign-up-and-sign-in-user-flow-policy"></a>Skapa en policy för användarflöde för registrering och inloggning

För att skapa en inloggning och policy för användarflöde följ stegen nedan.

1. I Azure-portalen väljer du **Användarflöden (policyer)** i det vänstra navigeringsfönstret.
1. På sidan **Azure AD B2C – användarflöden (policyer)** väljer du **Nytt användarflöde**.
1. Välj policyn **Registrera och logga in** och välj sedan versionen **Rekommenderad**.
1. Under **Namn**, ange ett policynamn. Det här namnet visas efteråt med ett prefix som portalen tilldelar (t.ex. "B2C_1_").
1. Under **Identitetsleverantörer**, i avsnittet **Lokala konton**, välj **E-postregistrering**. E-postautentisering används i de vanligaste scenarierna för Commerce. Om du även använder autentisering för personidentitetsprovider, kan du även välja dessa vid den här tidpunkten.
1. Under **Flerfaktorautentisering** väljer du lämpligt val för ditt företag. 
1. Under **användarattribut och anspråk** väljer du alternativ för att samla in attribut eller returnera anspråk efter behov. Välj **Visa mer...** om du vill få den fullständiga listan över attribut- och anspråksalternativ. Commerce kräver följande standardalternativ:

    | **Samla in attribut** | **Returnera anspråk** |
    | ---------------------- | ----------------- |
    | E-postadress          | E-postadresser   |
    | Angivet namn             | Angivet namn        |
    |                        | Identitetsprovider |
    | Efternamn                | Efternamn           |
    |                        | Användarens objekt-ID  |

1. Markera **Skapa**.

Följande bild är ett exempel på Azure AD B2C registrering och inloggning i användarflödet.

![Policyinställningar för Registrera och Logga in.](./media/B2CImage_11.png)

   
### <a name="create-a-profile-editing-user-flow-policy"></a>Skapa en profil genom att redigera användarflödespolicy

För att en profilredigering för policy för användarflöde följ stegen nedan.

1. I Azure-portalen väljer du **Användarflöden (policyer)** i det vänstra navigeringsfönstret.
1. På sidan **Azure AD B2C – användarflöden (policyer)** väljer du **Nytt användarflöde**.
1. Välj **Profilredigering** och välj sedan den **rekommenderade** versionen.
1. Under **namn** anger du användarflödet för profilredigering. Det här namnet visas efteråt med ett prefix som portalen tilldelar (t.ex. "B2C_1_").
1. Under **Identitetsleverantörer**, i avsnittet **Lokala konton**, välj **E-post SignIn**.
1. Markera en eller flera av följande kryssrutor under **Användarattribut**:
    
    | **Samla in attribut** | **Returnera anspråk** |
    | ---------------------- | ----------------- |
    |                        | E-postadresser   |
    | Angivet namn             | Angivet namn        |
    |                        | Identitetsprovider |
    | Efternamn                | Efternamn           |
    |                        | Användarens objekt-ID  |
    
1. Markera **Skapa**.

Följande bild visar ett exempel på Azure AD B2C-profil som redigerar användarflödet.

![Exempel på användarflödet Azure AD B2C profilredigering](./media/B2CImage_12.png)

### <a name="create-a-password-reset-user-flow-policy"></a>Skapa en lösenordsåterställning för användarflödespolicy

För att en lösenordsåterställning för policy för användarflöde följ stegen nedan.

1. I Azure-portalen väljer du **Användarflöden (policyer)** i det vänstra navigeringsfönstret.
1. På sidan **Azure AD B2C – användarflöden (policyer)** väljer du **Nytt användarflöde**.
1. Välj **Lösenordsåterställning** och välj sedan den **rekommenderade** versionen.
1. Under **namn** anger du ett namn på användarflödet för återställning av lösenord.
1. Under **identitetsleverantörer** väljer du **Återställ lösenord med e-postadress**.
1. Markera **Skapa**.
1. Markera en eller flera av följande kryssrutor under **Programanspråk**:
    - **E-postadresser**
    - **Angivet namn**
    - **Efternamn**
    - **Användarens objekt-ID**
1. Markera **Skapa**.

I följande bild visas var du ska ange **Återställ lösenord med e-postadress** i Azure AD B2C lösenordsåterställning för användarflöde.

![Ange "Återställ lösenord med e-postadress" i policyn för lösenordsåterställning](./media/B2CImage_13.png)

## <a name="add-social-identity-providers-optional"></a>Lägg till sociala identitetsleverantör (valfritt)

Med sociala identitetsleverantör kan användarna använda sina sociala konton för autentisering. Att lägga till sociala identitetsleverantör är valfritt i Dynamics 365 Commerce. 

Om autentiseringen av sociala identitetsleverantör inte läggs till blir Azure AD B2C standard-profiler huvudprofilerna för användarbasen. Användarna väljer sina egna användarnamn (deras standard-e-postadress) och anger ett lösenord. Azure AD B2C kommer att autentisera användare direkt. 

Om autentisering av sociala identitetsleverantörer läggs till och en användare väljer en av de tillgängliga leverantörerna av sociala identiteter, skapas en entitet fortfarande i Azure AD B2C-innehavaren. Azure AD B2C kommer sedan att autentisera användarens uppgifter hos den sociala identitetsleverantören.

> [!NOTE]
> Identitetsleverantörens inloggning skapar en post i B2C-innehavaren, men i ett annat format än lokala konton eftersom den ska anropa den externa referensen för social identitetsleverantör för autentisering. Användaren kan använda samma e-postadress för sociala identitetsleverantör, vilket innebär att e-postnamnet som används för autentisering kanske inte är unikt för innehavaren. Azure AD B2C kommer bara att säkerställa att användarna har en unik e-postadress på lokala B2C-konton.

Innan du kan lägga till en social identitetsleverantör för autentisering måste du gå till identitetsleverantörens portal och konfigurera ett program för identitetsleverantör enligt anvisningarna i Azure AD B2C-dokumentationen. Nedan finns en lista med länkar till dokumentationen.

- [Amazon](/azure/active-directory-b2c/active-directory-b2c-setup-amzn-app)
- [Azure AD (En innehavare)](/azure/active-directory-b2c/active-directory-b2c-setup-oidc-azure-active-directory)
- [Microsoft-konto](/azure/active-directory-b2c/active-directory-b2c-setup-msa-app)
- [Facebook](/azure/active-directory-b2c/active-directory-b2c-setup-fb-app)
- [GitHub](/azure/active-directory-b2c/active-directory-b2c-setup-github-app)
- [Google](/azure/active-directory-b2c/active-directory-b2c-setup-goog-app)
- [LinkedIn](/azure/active-directory-b2c/active-directory-b2c-setup-li-app)
- [OpenID Connect](/azure/active-directory-b2c/active-directory-b2c-setup-oidc-idp)
- [Twitter](/azure/active-directory-b2c/active-directory-b2c-setup-twitter-app)

### <a name="add-and-set-up-a-social-identity-provider"></a>Lägga till och konfigurera en leverantör av sociala identiteter

Lägg till och ställ in en leverantör av sociala identiteter enligt följande instruktioner.  

1. I Azure-portal, navigera till **identitetsleverantörer**.
1. Markera **Lägg till**. Skärmen **Lägg till identitetsleverantör** visas.
1. Under **Namn** anger du det namn som ska visas för användarna i inloggningsskärmen.
1. Under **Typ av identitetsleverantör**, välj en identitetsleverantör från listan.
1. Välj **OK**.
1. Välj **konfigurera den här identitetsleverantören** för åtkomst till skärmen **Ställ in till fönstret för social identitetsleverantör**.
1. Under **klient-ID**, ange det klient-ID som hämtas från programinställningar för identitetsleverantör.
1. Under **klienthemlighet**, ange den klienthemlighet som hämtas från programinställningar för identitetsleverantör.
1. Koppla användarflöde för inloggningsprinciper för inloggning:
1. Gå till **Azure AD B2C – användarflöden (principer)\> {din policy för registrering och inloggning} \> identitetsleverantörer**.
1. Om du vill koppla användarflödespolicyn för inloggning/registrering markerar du varje identitetsleverantör som du har skapat för ditt konto. Om du vill testa dessa väljer du **kör användarflöde** för varje identitetsleverantör. På en ny flik visas inloggningssidan med den nya valrutan för identitetsleverantörer.

Följande bild illustrerar exempel på skärmarna **lägga till identitetsleverantören** och **konfigurerar social identitetsleverantören** i Azure AD B2C.

![Lägga till en social identitetsleverantör i ditt program.](./media/B2CImage_14.png)

I följande bild visas ett exempel på hur du väljer identitetsleverantörer på sidan Azure AD B2C **identitetsleverantörer**.

![Välj varje social identitetsleverantör som ska aktiveras för din policy.](./media/B2CImage_16.png)

I bilden nedan visas ett exempel på en standard inloggningsskärm med knappen för inloggning med sociala identitetsleverantörer som visas.

> [!NOTE]
> Om du använder de anpassade sidorna som är inbyggda i Commerce för dina användarflöden måste knapparna för sociala identitetsleverantörer läggas till med hjälp av utökningsfunktionerna i Commerce-modulbiblioteket. När du konfigurerar program med en viss leverantör av social identitet, kan URL-adressen eller konfigurationssträngen i vissa fall vara ärendekänslig. Mer information finns i anslutningsinstruktioner för din personidentitetsprovider.
 
![Exempel på standardinloggningsskärm när inloggningsknappen för sociala identitetsleverantörer visas.](./media/B2CImage_17.png)

## <a name="update-commerce-headquarters-with-the-new-azure-ad-b2c-information"></a>Uppdatera Commerce headquarters med den nya Azure AD B2C-informationen

När Azure AD B2C etableringsstegen ovan har slutförts måste Azure AD B2C-programmet vara registrerat i din Dynamics 365 Commerce-miljö.

Om du vill uppdatera huvud kontoret med den nya Azure AD B2C-informationen följer du stegen nedan.

1. I Commerce går du till **delade Commerce-parametrar** och väljer **identitetsleverantörer** på den vänstra menyn.
1. Under **identitetsleverantörer** gör du följande:
    1. I rutan **utfärdare** anger du sträng för identitetsleverantörens utfärdare. För att hitta din utfärdarsträng, se [Skaffa utfärdarsträng för inställning av huvudkontoret](#obtain-issuer-string-for-headquarters-setup) nedan.
    1. I rutan **Namn**, ange ett namn för din utfärdarpost.
    1. I rutan **Typ**, ange **Azure AD B2C (id_token)**.
1. Under **Förlitande parter**, med ovanstående B2C för identitetsleverantör:
    1. I rutan **ClientID**, ange ditt B2C program-ID. Du hittar detta i rutan **Program-ID** på egenskapssida B2C-program.
    1. I rutan **Typ** ange **Offentlig**.
    1. I rutan **Användartyp** ange **Kund**.
1. Klicka på **Spara** i åtgärdsfönstret.
1. I Commerce-sökrutan, sök efter **Distributionsschema**
1. I den vänstra navigeringsmenyn på sidan **distributionsscheman** väljer du **1110 Global konfiguration**.
1. I åtgärdsfönstret, klicka på **Kör nu**.

### <a name="obtain-issuer-string-for-headquarters-setup"></a>Hämta utfärdarsträng för inställning av huvudkontor

Om du vill ha en utfärdar-sträng för identitetsleverantören följer du stegen nedan.

1. På Azure AD B2C-sidan i Azure-portal navigerar du till ditt användarflöde **Registrera dig och logga in**.
1. Välj **Sidlayouter** i den vänstra navigeringsmenyn, under **Layoutnamn** välj **Enhetlig registrering eller inloggning på sidan** och välj sedan **Kör användarflöde**.
1. Kontrollera att ditt program är inställt på din avsedda Azure AD B2C-app som skapats ovan och välj sedan användarflödeslänken som visas under rubriken **Kör användarflöde** som innehåller ``.../.well-known/openid-configuration?p=<B2CSIGN-INPOLICY>``. (Välj inte **Kör användarflöde**.) En ny flik öppnas med metadata för policyn som utfärdarsträngen ska samlas in för.
1. På den metadatasida som visas i webbläsaren kopierar du utfärdarsträngen för ID-utfärdaren (värdet för **utfärdaren** som börjar med "https://" och slutar med "/v2.0/" ) som liknar följande exempel.
   - ``https://login.fabrikam.com/011115c3-0113-4f43-b5e2-df01266e24ae/v2.0/``.
 
**ELLER**: Om du vill skapa samma metadata-URL manuellt gör du på följande sätt.

1. Skapa en URL för en metadataadress i följande format med hjälp av din B2C-klient och policy: ``https://<B2CTENANTNAME>.b2clogin.com/<B2CTENANTNAME>.onmicrosoft.com/v2.0/.well-known/openid-configuration?p=<B2CSIGN-INPOLICY>``
    - Exempel: ``https://d365plc.b2clogin.com/d365plc.onmicrosoft.com/v2.0/.well-known/openid-configuration?p=B2C_1_signinup``.
1. Ange URL-adressen för metadata i webbläsarens adressfält.
1. I metadata kopierar du URL:en för identitetsleverantören (värdet för **"utfärdare"**).
    - Exempel: ``https://login.fabrikam.com/011115c3-0113-4f43-b5e2-df01266e24ae/v2.0/``.

## <a name="configure-your-b2c-tenant-in-commerce-site-builder"></a>Konfigurera din B2C-innehavare i Commerce webbplatsskaparen

När installationen av din Azure AD B2C-innehavare har slutförts måste du konfigurera B2C-innehavaren i Commerce webbplatsskaparen. Konfigurationsstegen omfattar insamling av B2C programinformation från Azure-portalen, ange B2C programinformation till webbplatsskaparen och sedan associera B2C-programmet med din webbplats och kanal.

### <a name="collect-the-required-application-information"></a>Samla in nödvändig programinformation

Gör så här för att samla in den nödvändiga programinformationen.

1. I Azure-portal, gå till **Start \> Azure AD B2C – programregistrering**.
1. Markera programmet och välj sedan i vänstra navigeringsfönstret **Översikt** för att hämta programinformationen.
1. Från **program-ID (klient)**, samla in program-ID för B2C-programmet som har skapats i B2C-innehavaren. Detta kommer senare att anges som **klient-GUID** i webbplatsskaparen.
1. Välj **Omdirigera URI** och samla in den svars-URL som visas för din webbplats (svars-URL:en som angavs vid inställningen).
1. Gå till **Start \> Azure AD B2C – användarflöden** och samla sedan in full namnen på varje användarflödespolicy.

Följande bild visar ett exempel på översiktssidan **Azure AD B2C-program - App-registreringar**.

![Azure AD B2C – Översiktssida för programregistreringar, där program-ID (klient) markerats](./media/ClientGUID_Application_AzurePortal.png)

Följande bild visar ett exempel på användarflödespolicyer på sidan **Azure AD B2C – användarflöden (policy)**.

![Samla in namnen på respektive B2C-policyflöde.](./media/B2CImage_22.png)

### <a name="enter-your-azure-ad-b2c-tenant-application-information-into-commerce"></a>Ange din Azure AD B2C-information för klientprogram i Commerce

Du måste ange information om Azure AD B2C-innehavaren i Commerce webbplatsskaparen innan du kopplar B2C-innehavaren till dina webbplatser.

Följ stegen nedan om du vill lägga till din Azure AD B2C-information till Commerce.

1. Logga in som administratör på Commerce webbplatsskaparen för din miljö.
1. I det vänstra navigeringsfönstret väljer du **innehavarinställningar** för att expandera den.
1. Under **Inställningar för klientorganisation**, välj **Inställning av webbplatsautentisering**. 
1. I huvudfönstret, bredvid **Webbplatsautentiseringsprofiler**, välj **Hantera**. (Om din klientorganisation visas i listan med webbplatsautentiseringsprofiler har den redan lagts till av en administratör. Kontrollera att artiklarna i steg 6 nedan matchar artiklarna för din avsedda B2C-konfiguration. En ny profil kan också skapas med hjälp av liknande Azure AD B2C-innehavare eller program som tar hänsyn till mindre skillnader, t.ex. olika användarpolicy-ID).
1. Välj **Lägg till webbplatsautentiseringsprofil**.
1. Ange följande obligatoriska objekt i formuläret som visas med värden från din B2C-innehavare och programmet. Fält som inte är obligatoriska (sådana som saknar asterisk) kan lämnas tomma.

    - **Programnamn**: namnet på ditt B2C-program, t.ex. "Fabrikam B2C".
    - **Klientnamn**: Namnet på din B2C-klient (Använd till exempel "fabrikam" om domänen visas som "fabrikam.onmicrosoft.com" för B2C-klienten). 
    - **Glömt lösenordspolicy-ID**: glöm lösenord användarflödespolicy-ID, t.ex. "B2C_1_PasswordReset".
    - **Policy-ID för registrering och inloggning**: användarflödespolicy-ID för registrering och inloggning, t.ex. "B2C_1_signup_signin".
    - **Klient-GUID**: B2C program-ID, till exempel "22290eb2-c52e-42e9-8b35-a2b0a3bcb9e6".
    - **Redigera profilpolicy-ID-**: profil som redigerar användarflödespolicy-ID, till exempel "B2C_1A_ProfileEdit".

1. Välj **OK**. Nu ska nu se att namnet på ditt B2C-program visas i listan.
1. Spara ändringarna genom att klicka på **Spara**.

Det valfria fältet **Anpassad domän för inloggning** ska endast användas om du konfigurerar en anpassad domän för Azure AD B2C-klientorganisationen. Mer information och beaktanden om hur du använder fältet **Anpassad domän för inloggning** finns i [Ytterligare B2C-information](#additional-b2c-information) nedan.

### <a name="associate-the-b2c-application-to-your-site-and-channel"></a>Associera B2C program till din webbplats och kanal

> [!WARNING]
> - Om webbplatsen redan är associerad med ett B2C-program tas aktuella referenser för användare som redan registrerats i den här miljön bort när du byter till ett annat B2C-program. Om det ändras kommer inga autentiseringsuppgifter som associeras med det B2C programmet att vara tillgängliga för användarna. 
> - Uppdatera endast B2C-programmet om du konfigurerar kanalens B2C-program för första gången eller om du vill att användarna ska registrera dig igen med nya autentiseringsuppgifter för den här kanalen med det nya B2C-programmet. Var försiktig när du kopplar kanaler till B2C-program och namnge program tydligt. Om en kanal inte är associerad med ett B2C program i stegen nedan, kommer användare som loggar in på den kanalen för din webbplats att anges i B2C-program som visas **standard** i **innehavarinställningar \> B2C-inställningar** för B2C-program.

För att associera B2C-program till din webbplats och kanal, följ dessa steg.

1. Navigera till webbplatsen i Commerce webbplatsskaparen.
1. I det vänstra navigeringsfönstret väljer du **Webbplatsinställningar** för att expandera den.
1. Under **webbplatsinställningar**, välj **kanaler**.
1. I huvudfönstret under **kanaler**, välj din kanal.
1. I rutan kanal egenskaper till höger väljer du B2C-programnamnet från nedrullningsbara menyn **Välj B2C-program**.
1. Välj **Stäng** och välj sedan **Spara och publicera**.

## <a name="additional-b2c-information"></a>Ytterligare B2C-information

### <a name="customer-migration"></a>Kundmigrering

Om du funderar på att flytta kundposter från en tidigare plattform för identitetsleverantörer, arbeta med Dynamics 365 Commerce för att granska behovet av kundmigrering.

För ytterligare Azure AD B2C-dokumentation om kundmigrering, se [Migrera användare till Azure Active Directory B2C](/azure/active-directory-b2c/active-directory-b2c-user-migration).

### <a name="custom-policies"></a>Anpassade principer

Mer information om hur du anpassar Azure AD-interaktioner och policyflöden utöver vad som erbjuds av B2C, se [Anpassa policyer i Azure Active Directory B2C](/azure/active-directory-b2c/active-directory-b2c-overview-custom). 

### <a name="secondary-admin"></a>Sekundär administration

Ett valfritt, sekundärt administratörskonto kan läggas till i avsnittet **användare** på din B2C-innehavare. Det kan vara ett direkt konto eller ett allmänt konto. Om du behöver dela ett konto mellan teamresurser kan du även skapa ett gemensamt konto. På grund av känsligheten hos de data som lagras i Azure AD B2C, bör ett gemensamt konto övervakas i ett nära samarbete per ditt företags säkerhetspolicyer.

### <a name="set-up-a-custom-sign-in-domain"></a>Ställa in en anpassad inloggningsdomän

Med Azure AD B2C kan du konfigurera en anpassad inloggningsdomän för Azure AD B2C-klientorganisationer. Instruktioner finns i [Aktivera anpassade domäner för Azure Active Directory B2C](/azure/active-directory-b2c/custom-domain). 

Om du använder en anpassad inloggningsdomän måste domänen anges i Commerce-webbplatsbyggaren.

För att ange en anpassad inloggningsdomän i webbplatsskaparen följer du stegen nedan.

1. I övre högra hörnet på webbplatsbyggaren väljer du webbplatsväxlaren och väljer **Hantera webbplatser**.
1. I det vänstra navigeringsfönstret väljer du **Inställningar för klientorganisation \> Inställning av webbplatsautentisering**.
1. I avsnittet **Webbplatsautentiseringsprofiler**, välj **Hantera**.
1. Klicka på knappen **Redigera** (pennsymbol) i den utfällbara menyn till höger som finns bredvid den webbplatsautentiseringsprofil som du vill ange en anpassad domän för.
1. I dialogrutan **Redigera webbplatsautentiseringsprofil**, under **Anpassad domän för inloggning**, anger du din anpassade inloggningsdomän (t.ex. login.fabrikam.com).

> [!WARNING]
> När du uppdaterar till en anpassad domän för Azure AD B2C-klientorganisationer påverkar ändringen klientorganisationens utfärdarinformation för den token som genereras. Utfärdardetaljerna omfattar sedan den anpassade domänen i stället för den standarddomän som tillhandahålls av Azure AD B2C. En annorlunda **Utfärdare**-konfiguration i Commerce headquarters (**Butik och handel \> Administrationsinställning \> Parametrar \> Gemensamma handelsparametrar \> Identitetsproviders**) ändrar systemets interaktion med webbplatsanvändare, och skapar potentiellt en ny kundpost om en användare autentiserar mot den nya utfärdaren. Alla ändringar av anpassade domän bör testas noggrant innan du växlar till den anpassade domänen i en live Azure AD B2C-miljö.

## <a name="additional-resources"></a>Ytterligare resurser

[Konfigurera ditt domännamn](configure-your-domain-name.md)

[Distribuera en ny klientorganisation för näthandel](deploy-ecommerce-site.md)

[Skapa en näthandelssajt](create-ecommerce-site.md)

[Associera en Dynamics 365 Commerce-webbplats med en onlinekanal](associate-site-online-store.md)

[Hantera robots.txt-filer](manage-robots-txt-files.md)

[Massöverföra URL-omdirigeringar](upload-bulk-redirects.md)

[Ställa in anpassade sidor för användarinloggningar](custom-pages-user-logins.md)

[Konfigurera flera B2C-innehavare i en Commerce-miljö](configure-multi-B2C-tenants.md)

[Lägga till stöd för ett innehållsleveransnätverk (CDN)](add-cdn-support.md)

[Aktivera platsbaserad butiksdetektering](enable-store-detection.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
