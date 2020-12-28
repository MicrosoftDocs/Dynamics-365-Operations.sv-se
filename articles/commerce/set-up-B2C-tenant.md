---
title: Ställa in en B2C-innehavare i Commerce
description: I det här avsnittet beskrivs hur du ställer in din Azure Active Directory (Azure AD) B2C-innehavare (Business-to-Consumer) för autentisering av användarplats i Dynamics 365 Commerce.
author: BrianShook
manager: annbe
ms.date: 06/22/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: ''
ms.search.region: Global
ms.search.industry: retail
ms.author: brshoo
ms.search.validFrom: 2020-02-13
ms.dyn365.ops.version: ''
ms.openlocfilehash: af2ec75328b6377c5d92656d011d21576417a63f
ms.sourcegitcommit: 4bf5ae2f2f144a28e431ed574c7e8438dc5935de
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/13/2020
ms.locfileid: "4517390"
---
# <a name="set-up-a-b2c-tenant-in-commerce"></a>Ställa in en B2C-innehavare i Commerce

[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs hur du ställer in din Azure Active Directory (Azure AD) B2C-innehavare (Business-to-Consumer) för autentisering av användarplats i Dynamics 365 Commerce.

## <a name="overview"></a>Översikt

Dynamics 365 Commerce använder Azure AD B2C för att stödja autentiseringsuppgifter för användare och verifikationsflöden. En användare kan registrera sig, logga in och återställa sitt lösenord genom dessa flöden. Azure AD B2C lagrar känslig information om användarautentisering, t.ex. användarnamn och lösenord. Användarposten i B2C-innehavaren kommer att lagra antingen en B2C lokal kontopost eller en post för en B2C social identitetsleverantör. Dessa B2C-poster kommer att länkas tillbaka till kundposten i Commerce-miljön.

## <a name="create-or-link-to-an-existing-aad-b2c-tenant-in-the-azure-portal"></a>Skapa eller länka till en befintlig AAD B2C-klientorganisation i Azure-portalen

1. Logga in på [Azure-portal](https://portal.azure.com/).
1. Från Azure-portal menyn, välj **skapa en resurs**. Se till att använda den prenumeration och katalog som kommer att vara ansluten till din Commerce-miljö.

    ![Skapa en resurs i Azure-portalen](./media/B2CImage_1.png)

1. Gå till **identitet \>Azure Active Directory B2C**.
1. På sidan **Skapa ny B2C-klient eller länk till befintlig klient** använder du ett av alternativen nedan som bäst passar ditt företags behov:

    - **Skapa en ny Azure AD B2C-innehavare**: Använd det här alternativet om du vill skapa en ny AAD B2C-innehavare.
        1. Välj **Skapa ett nytt Azure AD B2C-innehavare**.
        1. Ange **organisationsnamnet** under organisationsnamn.
        1. Under **Initialt domännamn**, ange initialt domännamn.
        1. För **land eller region** välj land eller region.
        1. Välj **skapa** om du vill skapa innehavaren.

     ![Skapa en ny Azure AD innehavare](./media/B2CImage_2.png)

     - **Länka en befintlig Azure AD B2C-innehavare till min Azure-prenumeration**: Använd det här alternativet om du redan har en Azure AD B2C innehavare som du vill länka till.
        1. Välj **länka en befintlig Azure AD B2C-klient till mitt Azure-abonnemang**.
        1. Välj **Azure AD B2C innehavare** välj för B2C-innehavaren. Om meddelandet "inga bidragsberättigande B2C-innehavare hittades" visas i urvalsrutan har du inte en giltig B2C klientorganisation och behöver skapa en ny.
        1. För **Resursgrupp**, välj **Skapa nya**. Ange ett **namn** på den resursgrupp som ska innehålla innehavaren, välj **Välj resursgruppens plats** och välj **sedan skapa**.

    ![Länka en befintlig Azure AD B2C innehavare till Azure abonnemang](./media/B2CImage_3.png)

1. När den nya Azure AD B2C skapas (detta kan ta en stund) visas en länk till den nya katalogen på instrumentpanelen. Länken leder till sidan "Välkommen till Azure Active Directory B2C".

    ![Länk till ny AAD-katalog](./media/B2CImage_4.png)

> [!NOTE]
> Om du har flera prenumerationer inom ditt Azure-konto eller har ställt in B2C-klienten utan att länka till en aktiv **prenumeration**, kommer en felsökningsannons att leda till att du kopplar klienten till en prenumeration. Markera felsökningsmeddelandet och följ instruktionerna för att lösa prenumerationsproblemet.

Följande bild visar ett exempel på en Azure AD B2C **felsökning** banderoll.

![Varnings visar av katalog har ingen aktiv prenumeration](./media/B2CImage_5.png)

## <a name="create-the-b2c-application"></a>Skapa B2C-applikationen

När B2C-innehavaren har skapats kommer du att skapa ett B2C-program inom innehavaren för att samverka med Commerce-åtgärderna.

Gör så här om du vill skapa ett B2C-applikation.

1. Markera **Program (äldre)** och välj **Lägg till** i Azure-portalen.
1. Under **namn** anger du namnet på det önskade AAD B2C-programmet.
1. Under **Webbapp/Webb-API**, för **Inkludera webbapp/webb-API**, välj **Ja**.
1. För **Tillåt implicit flöde**, välj **Ja** (standardvärde).
1. Ange **Svars-URL** för svar under svars-URL. Se [besvara URL](#reply-urls) nedan för information om svars-URL:er och hur du formaterar dem.
1. För **Inkludera inhemsk klient**, välj **Nej** (standardvärdet).
1. Markera **Skapa**.

### <a name="reply-urls"></a>Svars-URL

Svars-URL är viktiga eftersom de ger en tillåten-lista med returdomänerna när platsen anropar Azure AD B2C för autentisering av en användare. På så sätt tillåts den autentiserade användaren returnera tillbaka till den domän som de loggar in på (din webbplatsdomän). 

I rutan **Svars-URL** på skärmen **Azure AD B2C - program \> Ny program** måste du lägga till separata rader för både din webbplatsdomän och (när din miljö har etablerats) den URL som genereras av Commerce. URL-adresserna får alltid använda ett giltigt URL-format och måste bara vara bas-URL:er (inga snedstreck eller sökvägar kan avslutas). Strängen ``/_msdyn365/authresp`` måste läggas till i bas-URL:erna, som i följande exempel.

- ``https://www.fabrikam.com/_msdyn365/authresp`` (Domänen ska matcha näthandelsdomänen helt. Om du har flera domäner måste du lägga till denna URL för varje domän.)
- ``https://fabrikam-prod.commerce.dynamics.com/_msdyn365/authresp``

## <a name="create-user-flow-policies"></a>Skapa policyer för användarflöden

Användarflöden är de policyer Azure AD B2C använder för att tillhandahålla säker inloggning, registrera, redigera profil och glömma användarupplevelser för lösenord. Dynamics 365 Commerce använder dessa flöden för att utföra policyåtgärder för samverkan med Azure AD B2C-innehavaren. När en användare interagerar med dessa principer, omdirigeras de till Azure AD B2C-innehavaren för att utföra åtgärderna.

Azure AD B2C har tre grundläggande användarflödestyper:
- Registrera dig och logga in
- Profilredigering
- Återställ lösenord

Du kan välja att använda standard användarflöden som tillhandahålls av Azure AD, vilket visar en sida som finns i AAD B2C. Du kan också skapa en HTML-sida för att kontrollera hur dessa användarflödesupplevelser ser ut och fungerar. 

Information om hur du anpassar sidorna för Dynamics 365 Commerce finns i [Konfigurera användarsidor för användarinloggningar](custom-pages-user-logins.md). Mer information finns i [Anpassa gränssnittet för användarupplevelser i Azure Active Directory B2C](https://docs.microsoft.com/azure/active-directory-b2c/tutorial-customize-ui).

### <a name="create-a-sign-up-and-sign-in-user-flow-policy"></a>Skapa en policy för användarflöde för registrering och inloggning

För att skapa en inloggning och policy för användarflöde följ stegen nedan.

1. I Azure-portalen väljer du **Användarflöden (policyer)** i det vänstra navigeringsfönstret.
1. På sidan **Azure AD B2C – användarflöden (policyer)** väljer du **Nytt användarflöde**.
1. På fliken **Rekommenderad** välj **registrera dig och logga in**.
1. Under **Namn**, ange ett policynamn. Det här namnet visas efteråt med ett prefix som portalen tilldelar (t.ex. "B2C_1_").
1. Under **identitetsleverantörer**, välj lämplig kryssruta.
1. Under **Flerfaktorautentisering** väljer du lämpligt val för ditt företag. 
1. Under **användarattribut och anspråk** väljer du alternativ för att samla in attribut eller returnera anspråk efter behov. Commerce kräver följande standardalternativ:

    | **Samla in attribut** | **Returnera anspråk** |
    | ---------------------- | ----------------- |
    | E-postadress          | E-postadresser   |
    | Angivet namn             | Angivet namn        |
    |                        | Identitetsprovider |
    | Efternamn                | Efternamn           |
    |                        | Användarens objekt-ID  |

1. Markera **Skapa**.

Följande bild är ett exempel på Azure AD B2C registrering och inloggning i användarflödet.

![Inställningar av policyn Registrera och logga in](./media/B2CImage_11.png)

I bilden nedan visas alternativet **kör användarflöde** i Azure AD B2C för att registrera och logga in i användarflödet.

![Kör användarflödesalternativ i policyflöde](./media/B2CImage_23.png)
   
### <a name="create-a-profile-editing-user-flow-policy"></a>Skapa en profil genom att redigera användarflödespolicy

För att en profilredigering för policy för användarflöde följ stegen nedan.

1. I Azure-portalen väljer du **Användarflöden (policyer)** i det vänstra navigeringsfönstret.
1. På sidan **Azure AD B2C – användarflöden (policyer)** väljer du **Nytt användarflöde**.
1. På fliken **Rekommenderad**, välj **Profilredigering**.
1. Under **namn** anger du användarflödet för profilredigering. Det här namnet visas efteråt med ett prefix som portalen tilldelar (t.ex. "B2C_1_").
1. Under **identitetsleverantörer**, välj **Inloggning på lokalt konto**.
1. Markera en eller flera av följande kryssrutor under **Användarattribut**:
    - **E-postadresser** (endast **returanspråk**)
    - **Angivet namn** (**Samla in attribut** och **returanspråk**)
    - **Identitetsleverantör** (endast **returanspråk**)
    - **Efternamn** (**Samla in attribut** och **returanspråk**)
    - **Användarens objekt-ID** (endast **returanspråk**)
1. Markera **Skapa**.

Följande bild visar ett exempel på Azure AD B2C-profil som redigerar användarflödet.

![Skapa en användarflödet profilredigering](./media/B2CImage_12.png)

### <a name="create-a-password-reset-user-flow-policy"></a>Skapa en lösenordsåterställning för användarflödespolicy

För att en lösenordsåterställning för policy för användarflöde följ stegen nedan.

1. I Azure-portalen väljer du **Användarflöden (policyer)** i det vänstra navigeringsfönstret.
1. På sidan **Azure AD B2C – användarflöden (policyer)** väljer du **Nytt användarflöde**.
1. På fliken **Rekommenderad**, välj **lösenordsåterställning**.
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

Innan du kan lägga till en social identitetsleverantör för autentisering måste du gå till identitetsleverantörens portal och ställa in ett program för identitetsleverantör enligt anvisningarna i Azure AD B2C-dokumentationen. Nedan finns en lista med länkar till dokumentationen.

- [Amazon](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-setup-amzn-app)
- [Azure AD (En innehavare)](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-setup-oidc-azure-active-directory)
- [Microsoft-konto](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-setup-msa-app)
- [Facebook](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-setup-fb-app)
- [GitHub](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-setup-github-app)
- [Google](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-setup-goog-app)
- [LinkedIn](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-setup-li-app)
- [OpenID Connect](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-setup-oidc-idp)
- [Twitter](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-setup-twitter-app)

### <a name="add-and-set-up-a-social-identity-provider"></a>Lägga till och ställa in en leverantör av sociala identiteter

Lägg till och ställ in en leverantör av sociala identiteter enligt följande instruktioner.  

1. I Azure-portal, navigera till **identitetsleverantörer**.
1. Markera **Lägg till**. Skärmen **Lägg till identitetsleverantör** visas.
1. Under **namn** anger du det namn som ska visas för användarna i inloggningsskärmen.
1. Under **Typ av identitetsleverantör**, välj en identitetsleverantör från listan.
1. Välj **OK**.
1. Välj **konfigurera den här identitetsleverantören** för åtkomst till skärmen **Ställ in till fönstret för social identitetsleverantör**.
1. Under **klient-ID**, ange det klient-ID som hämtas från programinställningar för identitetsleverantör.
1. Under **klienthemlighet**, ange den klienthemlighet som hämtas från programinställningar för identitetsleverantör.
1. Koppla användarflöde för inloggningsprinciper för inloggning:
1. Gå till **Azure AD B2C – användarflöden (principer)\> {din policy för registrering och inloggning} \> identitetsleverantörer**.
1. Om du vill koppla användarflödespolicyn för inloggning/registrering markerar du varje identitetsleverantör som du har skapat för ditt konto. Om du vill testa dessa väljer du **kör användarflöde** för varje identitetsleverantör. På en ny flik visas inloggningssidan med den nya valrutan för identitetsleverantörer.

Följande bild illustrerar exempel på skärmarna **lägga till identitetsleverantören** och **ställer in social identitetsleverantören** i Azure AD B2C.

![Lägga till en social identitetsleverantör i ditt program](./media/B2CImage_14.png)

I följande bild visas ett exempel på hur du väljer identitetsleverantörer på sidan Azure AD B2C **identitetsleverantörer**.

![Välj varje social identitetsleverantör som ska aktiveras för din policy](./media/B2CImage_16.png)

I bilden nedan visas ett exempel på en standard inloggningsskärm med knappen för inloggning med sociala identitetsleverantörer som visas.

![Exempel på standard inloggningsskärm när inloggningsknappen för sociala identitetsleverantörer visas](./media/B2CImage_17.png)

## <a name="update-commerce-headquarters-with-the-new-azure-ad-b2c-information"></a>Uppdatera Commerce-administration med den nya Azure AD B2C-informationen

När Azure AD B2C etableringsstegen ovan har slutförts måste Azure AD B2C-programmet vara registrerat i din Dynamics 365 Commerce-miljö.

Om du vill uppdatera huvud kontoret med den nya Azure AD B2C-informationen följer du stegen nedan.

1. I Commerce går du till **delade Commerce-parametrar** och väljer **identitetsleverantörer** på den vänstra menyn.
1. Under **identitetsleverantörer** gör du följande:
    1. I rutan **utfärdare** anger du URL för identitetsleverantörens utfärdare. Information om hur du hittar din utfärdar-URL, se [Hämta utfärdar-URL](#obtain-issuer-url) nedan.
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

### <a name="obtain-issuer-url"></a>Hämta utfärdar-URL

Om du vill ha en utfärdar-URL för identitetsleverantören följer du stegen nedan.

1. Skapa en URL för en metadataadress i följande format med hjälp av din B2C-klient och policy: ``https://<B2CTENANTNAME>.b2clogin.com/<B2CTENANTNAME>.onmicrosoft.com/v2.0/.well-known/openid-configuration?p=<B2CSIGN-INPOLICY>``
    - Exempel: ``https://d365plc.b2clogin.com/d365plc.onmicrosoft.com/v2.0/.well-known/openid-configuration?p=B2C_1_signinup``.
1. Ange URL-adressen för metadata i webbläsarens adressfält.
1. I metadata kopierar du URL:en för identitetsleverantören (värdet för **"utfärdare"**).
    - Exempel: ``https://login.fabrikam.com/073405c3-0113-4f43-b5e2-df01266e24ae/v2.0/``.

## <a name="configure-your-b2c-tenant-in-commerce-site-builder"></a>Konfigurera din B2C-innehavare i Commerce webbplatsskaparen

När installationen av din Azure AD B2C-innehavare har slutförts måste du konfigurera B2C-innehavaren i Commerce webbplatsskaparen. Konfigurationsstegen omfattar insamling av B2C programinformation från Azure-portalen, ange B2C programinformation till webbplatsskaparen och sedan associera B2C-programmet med din webbplats och kanal.

### <a name="collect-the-required-application-information"></a>Samla in nödvändig programinformation

Gör så här för att samla in den nödvändiga programinformationen.

1. I Azure-portal, gå till **Start \> Azure AD B2C - program**.
1. Markera programmet och välj sedan i vänstra navigeringsfönstret **Egenskaper** för att hämta programinformationen.
1. Från rutan **program-ID**, samla in program-ID för B2C-programmet som har skapats i B2C-innehavaren. Detta kommer senare att anges som **klient-GUID** i webbplatsskaparen.
1. Under **Svars-URL**, samla svars-URL.
1. Gå till **Start \> Azure AD B2C – användarflöden (policyer)** och samla sedan in namnen på varje användarflödespolicy.

Följande bild visar ett exempel på sidan **Azure AD B2C-program**.

![Navigera till B2C-programmet inom din klientorganisation](./media/B2CImage_19.png)

Följande bild visar ett exempel på en programsida **egenskaper** i Azure AD B2C. 

![Kopiera program-ID från B2C programegenskaper](./media/B2CImage_21.png)

Följande bild visar ett exempel på användarflödespolicyer på sidan **Azure AD B2C – användarflöden (policy)**.

![Samla in namnen på varje B2C policyflöde](./media/B2CImage_22.png)

### <a name="enter-your-aad-b2c-tenant-application-information-into-commerce"></a>Ange din AAD B2C-information för klientprogram i Commerce

Du måste ange information om Azure AD B2C-innehavaren i Commerce webbplatsskaparen innan du kopplar B2C-innehavaren till dina webbplatser.

Följ stegen nedan om du vill lägga till din AAD B2C-information till Commerce.

1. Logga in som administratör på Commerce webbplatsskaparen för din miljö.
1. I det vänstra navigeringsfönstret väljer du **innehavarinställningar** för att expandera den.
1. Under **innehavarinställningar** väljer du **B2C-inställningar**. 
1. I huvudfönstret bredvid **B2C-program**, välj **Hantera**. (Om din klientorganisation visas i listan B2C-program, har den redan lagts till av en administratör. Kontrollera att artiklarna i steg 6 nedan matchar ditt B2C-program.)
1. Välj **Lägg till B2C-program**.
1. Ange följande obligatoriska objekt i formuläret som visas med värden från din B2C-innehavare och programmet. Fält som inte är obligatoriska (sådana som saknar asterisk) kan lämnas tomma.

    - **Programnamn**: namnet på ditt B2C-program, t.ex. "Fabrikam B2C".
    - **Klientnamn**: Namnet på din B2C-klient (Använd till exempel "fabrikam" om domänen visas som "fabrikam.onmicrosoft.com" för B2C-klienten). 
    - **Glömt lösenordspolicy-ID**: glöm lösenord användarflödespolicy-ID, t.ex. "B2C_1_PasswordReset".
    - **Policy-ID för registrering och inloggning**: användarflödespolicy-ID för registrering och inloggning, t.ex. "B2C_1_signup_signin".
    - **Klient-GUID**: B2C program-ID, till exempel "22290eb2-c52e-42e9-8b35-a2b0a3bcb9e6".
    - **Redigera profilpolicy-ID-**: profil som redigerar användarflödespolicy-ID, till exempel "B2C_1A_ProfileEdit".

1. Välj **OK**. Nu ska nu se att namnet på ditt B2C-program visas i listan.
1. Spara ändringarna genom att klicka på **Spara**.

### <a name="associate-the-b2c-application-to-your-site-and-channel"></a>Associera B2C program till din webbplats och kanal

> [!WARNING]
> Om webbplatsen redan är associerad med ett B2C-program tas aktuella referenser för användare som redan registrerats i den här miljön bort när du byter till ett annat B2C-program. Om det ändras kommer inga autentiseringsuppgifter som associeras med det B2C programmet att vara tillgängliga för användarna. 
> 
> Uppdatera endast B2C-programmet om du ställer in kanalens B2C-program för första gången eller om du vill att användarna ska registrera dig igen med nya autentiseringsuppgifter för den här kanalen med det nya B2C-programmet. Var försiktig när du kopplar kanaler till B2C-program och namnge program tydligt. Om en kanal inte är associerad med ett B2C program i stegen nedan, kommer användare som loggar in på den kanalen för din webbplats att anges i B2C-program som visas **standard** i **innehavarinställningar \> B2C-inställningar** för B2C-program.

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

För ytterligare Azure AD B2C-dokumentation om kundmigrering, se [Migrera användare till Azure Active Directory B2C](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-user-migration).

### <a name="custom-policies"></a>Anpassade principer

Mer information om hur du anpassar Azure AD-interaktioner och policyflöden utöver vad som erbjuds av B2C, se [Anpassa policyer i Azure Active Directory B2C](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-overview-custom). 

### <a name="secondary-admin"></a>Sekundär administration

Ett valfritt, sekundärt administratörskonto kan läggas till i avsnittet **användare** på din B2C-innehavare. Det kan vara ett direkt konto eller ett allmänt konto. Om du behöver dela ett konto mellan teamresurser kan du även skapa ett gemensamt konto. På grund av känsligheten hos de data som lagras i Azure AD B2C, bör ett gemensamt konto övervakas i ett nära samarbete per ditt företags säkerhetspolicyer.

## <a name="additional-resources"></a>Ytterligare resurser

[Konfigurera ditt domännamn](configure-your-domain-name.md)

[Distribuera en ny klientorganisation för näthandel](deploy-ecommerce-site.md)

[Skapa en näthandelsplats](create-ecommerce-site.md)

[Associera en Dynamics 365 Commerce-webbplats med en onlinekanal](associate-site-online-store.md)

[Hantera robots.txt-filer](manage-robots-txt-files.md)

[Ladda upp URL-omdirigeringar i bulk](upload-bulk-redirects.md)Associera en Dynamics 365 Commerce-webbplats med en onlinekanal

[Ställa in anpassade sidor för användarinloggningar](custom-pages-user-logins.md)

[Konfigurera flera B2C-klientorganisationer i en Commerce-miljö](configure-multi-B2C-tenants.md)

[Lägga till stöd för ett innehållsleveransnätverk (CDN)](add-cdn-support.md)

[Aktivera platsbaserad butiksdetektering](enable-store-detection.md)
