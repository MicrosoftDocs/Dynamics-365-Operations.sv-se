---
title: Ställa in anpassade sidor för användarinloggningar
description: I det här avsnittet beskrivs hur du skapar anpassade sidor i Microsoft Dynamics 365 Commerce som hanterar anpassade inloggningsuppgifter för användare av Azure Active Directory (Azure AD) B2C-innehavare (Business-to-Consumer).
author: brianshook
manager: annbe
ms.date: 12/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 20bfacbc2374003814e12e7737644d118d404cc0
ms.sourcegitcommit: ef3a1d7527311d00b69a1072ae5eb021ce68034c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/09/2020
ms.locfileid: "2945569"
---
# <a name="set-up-custom-pages-for-user-logins"></a>Ställa in anpassade sidor för användarinloggningar

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs hur du skapar anpassade sidor i Microsoft Dynamics 365 Commerce som hanterar anpassade inloggningsuppgifter för användare av Azure Active Directory (Azure AD) B2C-innehavare (Business-to-Consumer).

## <a name="overview"></a>Översikt

Om du vill använda anpassade sidor som har skapats i Dynamics 365 Commerce för att hantera användarinloggningsflöden måste du ställa in de Azure AD-policyer som kommer att refereras till i handelsmiljön. Du kan konfigurera B2C-policyer "Registrera och logga in", "profilredigering" och "lösenordsåterställning" Azure AD B2C-policyer med hjälp av Azure AD B2C-programmet. Azure AD B2C-innehavare och policynamn kan sedan refereras under etableringsprocessen som utförs för handelsmiljön med hjälp av Microsoft Dynamics Lifecycle Services (LCS).

De anpassade handelssidorna kan skapas med hjälp av modulen logga in, registrera, kontoprofil eller återställ lösenord. De sid-URL:er som publiceras för dessa anpassade sidor bör sedan refereras i Azure AD B2C policykonfigurationer i Azure-portalen.

## <a name="set-up-b2c-policies"></a>Ställ in B2C-policyer

När du har ställt in Azure AD B2C-innehavare och associerar den med din handelsmiljö, går du till sidan **Azure AD B2C** i Azure-portalen och väljer i menyn **Policyer** och sedan **Användarflöden (policyer)**.

![Kommandot användarflöden (policyer) på menyn](./media/B2C_CustomPage_PoliciesMenu.png)

Du kan nu konfigurera användarinloggningsflöden "registrera och logga in", "profilredigering" och "lösenordsåterställning".

### <a name="configure-the-sign-up-and-sign-in-policy"></a>Konfigurera policyn "Registrera och logga in"

För att konfigurera policyn "Registrera och logga in" följ stegen nedan.

1. Välj **nytt användarflöde** och välj sedan fliken **rekommenderad**, välj policyn **Logga in**.
1. Ange ett namn på policyn (till exempel **B2C\_1\_SignInSignUp**).
1. I avsnittet **identitetsleverantörer** väljer du vilka identitetsleverantörer som ska användas för policyn. Åtminstone måste du **välja e-postregistrering**.
1. I kolumnen **Samla in attribut** välj kryssrutorna för **e-postadress**, **förnamn** och **efternamn**.
1. I kolumnen **returanspråk** markerar du kryssrutorna för **e-postadresser**, **förnamn**, **identitetsleverantör**, **efternamn** och **användarens objekt-ID**.

    ![Valda attribut och anspråk](./media/B2C_SignInSignUp_Attributes.png)

1. Skapa policyn genom att välja **OK**.
1. Dubbelklicka på det nya policynamnet och välj sedan **Egenskaper**i navigeringsfönstret.
1. Ange alternativet **aktivera JavaScript med tvingad sidlayout (förhandsgranskning)** till **På**.

    ![Egenskapssida för den nya policyn](./media/B2C_SignInSignUp_EnableJavascript.png)

> [!NOTE]
> Policynamnet kommer att refereras till i handelsmiljön. (Prefixet **B2C\_1\_** kommer att inkluderas i referensen.) Det går inte att byta namn på policyer när de har skapats. Om du ersätter en befintlig policy för din handelsmiljö, kan du ta bort den ursprungliga policyn och bygga en ny policy som har samma namn. Om miljön redan har etablerats kan du skicka det nya policynamnet via en tjänstbegäran.

Du kommer tillbaka till den här policyn för att slutföra installationen när du har byggt de anpassade sidorna. Stäng nu policyn för att återgå till sidan **användarflöden (policyer)** i Azure-portalen.

### <a name="configure-the-profile-editing-policy"></a>Konfigurera policyn för "profilredigering"

Gör på följande vis för att konfigurera policyn "profilredigering".

1. Välj **nytt användarflöde** och välj sedan fliken **rekommenderad**, välj policyn **profilredigering**.
1. Ange ett namn på policyn (till exempel **B2C\_1\_EditProfile**).
1. I avsnittet **identitetsleverantörer** väljer du vilka identitetsleverantörer som ska användas för policyn. Åtminstone **Local Account SignIn** måste väljas.
1. I kolumnen **Samla in attribut** välj kryssrutorna för **e-postadresser** och **efternamn**.
1. I kolumnen **returanspråk** markerar du kryssrutorna för **e-postadresser**, **förnamn**, **identitetsleverantör**, **efternamn** och **användarens objekt-ID**.
1. Skapa policyn genom att välja **OK**.
1. Dubbelklicka på det nya policynamnet och välj sedan **Egenskaper**i navigeringsfönstret.
1. Ange alternativet **aktivera JavaScript med tvingad sidlayout (förhandsgranskning)** till **På**.

Du kommer tillbaka till den här policyn för att slutföra installationen när du har byggt de anpassade sidorna. Stäng nu policyn för att återgå till sidan **användarflöden (policyer)** i Azure-portalen.

### <a name="configure-the-password-reset-policy"></a>Konfigurera policyn "Återställ lösenord"

Gör på följande vis för att konfigurera policyn "Lösenordsåterställning".

1. Välj **nytt användarflöde** och välj sedan fliken **Förhandsgranska**, välj policyn **lösenordsåterställning v1.1**.

    ![Policyn lösenordsåterställning v1.1 har valts på fliken förhandsgranskning](./media/B2C_ForgetPassword_Menu.png)

1. Ange ett namn på policyn (till exempel **B2C\_1\_ForgetPassword**).
1. I avsnittet **identitetsleverantörer** väljer du **Återställ lösenord med e-postadress**.
1. I kolumnen **returanspråk** markerar du kryssrutorna för **e-postadresser**, **förnamn**, **efternamn** och **användarens objekt-ID**.

    ![Valda anspråk](./media/B2C_ForgetPassword_Attributes.png)

1. Skapa policyn genom att välja **OK**.
1. Dubbelklicka på det nya policynamnet och välj sedan **Egenskaper**i navigeringsfönstret.
1. Ange alternativet **aktivera JavaScript med tvingad sidlayout (förhandsgranskning)** till **På**.

Du kommer tillbaka till den här policyn för att slutföra installationen när du har byggt de anpassade sidorna. Stäng nu policyn för att återgå till sidan **användarflöden (policyer)** i Azure-portalen.

## <a name="build-the-custom-pages"></a>Skapa anpassade sidor

Om du vill skapa de anpassade sidorna för att hantera användarinloggningar följer du stegen nedan.

1. I handelsredigeringsverktyg, gå till din webbplats.
1. Skapa följande fem mallar och fem sidor:

    - Mallen **Logga in** och sida där inloggningsmodulen används.
    - Mallen **Registrera dig** och sida där registreringsmodulen används.
    - Mallen **lösenordsåterställning** och sidan med modulen lösenordsåterställning.
    - Mallen **verifiering av lösenordsåterställning** och sidan med modulen verifiering av lösenordsåterställning.
    - Mallen **profilredigering** och sidor som använder redigeringsmodulen för kontoprofilen

Följ de här riktlinjerna när du skapar sidorna:

- För varje sida eller modul använder du layouten och formatet som bäst passar dina affärsbehov.
- Publicera alla sidor och URL som måste användas i Azure AD B2C-inställningar.
- När sidorna och adresserna har publicerats samlar du in de URL-adresser som måste användas för konfigurationer av Azure AD B2C-policy. Suffixet **?preloadscripts=true** kommer att läggas till varje URL när det används.

> [!IMPORTANT]
> Återanvänd inte universella sidhuvuden och sidfötter med relativa länkar. Eftersom dessa sidor kommer att finnas i Azure AD B2C-domänen när de används, ska endast absoluta URL:er användas för alla länkar.

## <a name="configure-azure-ad-b2c-policies-with-custom-page-information"></a>Konfigurera Azure AD B2C policyer med anpassad sidinformation 

I Azure-portalen, gå tillbaka till sidan **Azure AD B2C** och sedan på menyn under **Policyer**, välj **Användarflöden (policyer)**.

### <a name="update-the-sign-up-and-sign-in-policy-with-custom-page-information"></a>Uppdatera policyn "Registrera och logga in" med anpassad sidinformation

För att uppdatera policyn "Registrera och logga in" med anpassad sidinformation, följ dessa steg.

1. I policyn **Registrera och logga in** som du konfigurerade tidigare, i navigeringsfönstret, välj **Sidlayouter**.
1. Välj layouten **Enhetlig sida för registrera och logga in**.
1. Ställ in alternativet **Använd anpassat sidinnehåll** till **ja**.
1. I fältet **Anpassad sid-URI** ange fullständig inloggnings-URL. Inkludera suffixet **?preloadscripts=true**. Ange exempelvis ``www.<my domain>.com/sign-in?preloadscripts=true``.
1. I fältet **Version av sidlayout (förhandsgranskning)**, välj **1.2.0**.
1. Välj layouten **sida för registrering av lokalt konto**.
1. Ställ in alternativet **Använd anpassat sidinnehåll** till **ja**.
1. I fältet **Anpassad sid-URI** ange fullständig inloggnings-URL. Inkludera suffixet **?preloadscripts=true**. Ange exempelvis ``www.<my domain>.com/sign-up?preloadscripts=true``.
1. I fältet **Version av sidlayout (förhandsgranskning)**, välj **1.2.0**.
1. I avsnittet **Användarattribut** följ dessa steg:

    1. För attributen **e-postadress**, **förnamn** och **efternamn** väljer du **nej** i fältet **kräver verifiering**.
    1. För attributen **förnamn** och **efternamn** välj **nej** i fältet **valfritt**.

    ![Konfiguration av policyn sida för registrering av lokalt konto](./media/B2C_SignUp_PageURLConfig.png)

### <a name="update-the-profile-editing-policy-with-custom-page-information"></a>Uppdatera policyn "Profilredigering" med anpassad sidinformation

För att uppdatera policyn "Profilredigering" med anpassad sidinformation, följ dessa steg.

1. I policyn **Profilredigering** som du konfigurerade tidigare, i navigeringsfönstret, välj **Sidlayouter**.
1. Välj layouten **Profilredigeringssida**.
1. Ställ in alternativet **Använd anpassat sidinnehåll** till **ja**.
1. I fältet **Anpassad sid-URI** ange fullständig profil redigerings-URL. Inkludera suffixet **?preloadscripts=true**. Ange exempelvis ``www.<my domain>.com/profile-edit?preloadscripts=true``.
1. I fältet **Version av sidlayout (förhandsgranskning)**, välj **1.2.0**.
1. I avsnittet **Användarattribut** följ dessa steg:

    1. För attributen **e-postadress**, **förnamn** väljer du **nej** i fältet **kräver verifiering**.
    1. För attributen **förnamn** och **efternamn** välj **nej** i fältet **valfritt**.

### <a name="update-the-password-reset-policy-with-custom-page-information"></a>Uppdatera policyn "Lösenordsåterställning" med anpassad sidinformation

För att uppdatera policyn "Lösenordsåterställning" med anpassad sidinformation, följ dessa steg.

1. I policyn **Lösenordsåterställning** som du konfigurerade tidigare, i navigeringsfönstret, välj **Sidlayouter**.
1. Välj layouten **Ny lösenordssida**.
1. Ställ in alternativet **Använd anpassat sidinnehåll** till **ja**.
1. I fältet **Anpassad sid-URI** ange fullständig lösenordsåterställnings-URL. Inkludera suffixet **?preloadscripts=true**. Ange exempelvis ``www.<my domain>.com/passwordreset?preloadscripts=true``.
1. I fältet **Version av sidlayout (förhandsgranskning)**, välj **1.2.0**.
1. Välj layouten **sida för kontoverifiering**.
1. Ställ in alternativet **Använd anpassat sidinnehåll** till **ja**.
1. I fältet **Anpassad sid-URI** ange fullständig lösenordsåterställning verifierings-URL. Inkludera suffixet **?preloadscripts=true**. Ange exempelvis ``www.<my domain>.com/passwordreset-verification?preloadscripts=true``.
1. I fältet **Version av sidlayout (förhandsgranskning)**, välj **1.2.0**.



## <a name="customize-default-text-strings-for-labels-and-descriptions"></a>Anpassa standardtextsträngar för etiketter och beskrivningar

I startpaketet är inloggningsmoduler förifyllda med standardtextsträngar för etiketterna och beskrivningarna. Du kan anpassa dessa strängar i SDK (Software Development Kit) genom att uppdatera värdena i global.json-filen för inloggningsmodulen.

Standardtexten för länken Glömt lösenordet är **glömt lösenord?**. Nedan visas den här standardtexten på inloggningssidan.

![Standardtext för länken Glömt lösenordet på inloggningssidan](./media/B2C_SignUp_ModuleFace.png)

I global.json-filen för loggen i startpaket kan du emellertid redigera texten till **glömt lösenordet?**, som du ser i bilden nedan.

![Länktexten uppdaterades i loggen i modulens global.json-fil](./media/B2C_CustomizingStringsForModule.png)

När du har uppdaterat global.json-filen och publicerat ändringarna, visas den nya länktexten i modulen logga in både i handel och på live-inloggningssidan.

## <a name="additional-resources"></a>Ytterligare resurser

[Konfigurera ditt domännamn](configure-your-domain-name.md)

[Distribuera en ny näthandelsplats](deploy-ecommerce-site.md)

[Skapa en e-handelsplats](create-ecommerce-site.md)

[Associera en online-webbplats med en kanal](associate-site-online-store.md)

[Hantera robots.txt-filer](manage-robots-txt-files.md)

[Lägga till stöd för ett innehållsleveransnätverk (CDN)](add-cdn-support.md)

[Aktivera platsbaserad butiksdetektering](enable-store-detection.md)
