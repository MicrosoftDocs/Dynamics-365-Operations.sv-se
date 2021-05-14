---
title: Ställa in anpassade sidor för användarinloggningar
description: I det här avsnittet beskrivs hur du skapar anpassade sidor i Microsoft Dynamics 365 Commerce som hanterar anpassade inloggningsuppgifter för användare av Azure Active Directory (Azure AD) B2C-innehavare (Business-to-Consumer).
author: brianshook
ms.date: 03/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: d4a1c2f45d77c3ff9a7bb4dffaf12d877dc04e69
ms.sourcegitcommit: 9eadc7ca08e2db3fd208f5fc835551abe9d06dc8
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/22/2021
ms.locfileid: "5936790"
---
# <a name="set-up-custom-pages-for-user-sign-ins"></a>Ställa in anpassade sidor för användarinloggningar

[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs hur du skapar anpassade sidor i Microsoft Dynamics 365 Commerce som hanterar anpassade inloggningsuppgifter för användare av Azure Active Directory (Azure AD) B2C-innehavare (Business-to-Consumer).

Om du vill använda anpassade sidor som har skapats i Dynamics 365 Commerce för att hantera användarinloggningsflöden måste du ställa in de Azure AD-policyer som kommer att refereras till i handelsmiljön. Du kan konfigurera B2C-policyer "Registrera och logga in", "profilredigering" och "lösenordsåterställning" Azure AD B2C-policyer med hjälp av Azure AD B2C-programmet. Azure AD B2C-innehavare och policynamn kan sedan refereras under etableringsprocessen som utförs för handelsmiljön med hjälp av Microsoft Dynamics Lifecycle Services (LCS).

De anpassade handelssidorna kan skapas med hjälp av modulen logga in, registrera, kontoprofil eller återställ lösenord eller generiska AAD-moduler. De sid-URL:er som publiceras för dessa anpassade sidor bör sedan refereras i Azure AD B2C policykonfigurationer i Azure-portalen.

> [!WARNING] 
> Azure AD B2C drar tillbaka gamla (äldre) användarflöden senast den 1 augusti 2021. Därför bör du planera att flytta dina användarflöden till den nya rekommenderade versionen. Den nya versionen innehåller funktionen paritet och nya funktioner. Mer information finns i [Arbetsflöden i Azure Active Directory B2C](/azure/active-directory-b2c/user-flow-overview).

>Modulbiblioteket för Commerce version 10.0.15 eller högre ska användas med de rekommenderade B2C-användarflödena. De standardanvändarpolicysidor som finns i Azure AD B2C kan också användas, och tillåta tillagda bakgrundsbild, logotyp och bakgrundsfärgändringar relaterade till företagets märke. De mer begränsade designfunktionerna gör att standardanvändarpolicysidorna tillhandahåller Azure AD B2C-policyfunktioner utan att de dedikerade anpassade sidorna skapas och konfigureras. 

## <a name="set-up-b2c-policies"></a>Ställ in B2C-policyer

När du har ställt in Azure AD B2C-innehavare och associerar den med din handelsmiljö, går du till sidan **Azure AD B2C** i Azure-portalen och väljer i menyn **Policyer** och sedan **Användarflöden (policyer)**.

![Kommandot användarflöden (policyer) på menyn](./media/B2C_CustomPage_PoliciesMenu.png)

Du kan nu konfigurera användarinloggningsflöden "registrera och logga in", "profilredigering" och "lösenordsåterställning".

### <a name="configure-the-sign-up-and-sign-in-policy"></a>Konfigurera policyn "Registrera och logga in"

För att konfigurera policyn "Registrera och logga in" följ stegen nedan.

1. Välj **Nytt användarflöde**, välj **Registrera dig och logga in**, välj **Rekommenderad** och välj **Skapa**.
1. Ange ett namn på policyn (till exempel **B2C\_1\_SignInSignUp**).
1. I avsnittet **identitetsleverantörer** väljer du vilka identitetsleverantörer som ska användas för policyn. Åtminstone måste du **välja e-postregistrering**.
1. I kolumnen **Samla in attribut** välj kryssrutorna för **e-postadress**, **förnamn** och **efternamn**.
1. I kolumnen **returanspråk** markerar du kryssrutorna för **e-postadresser**, **förnamn**, **identitetsleverantör**, **efternamn** och **användarens objekt-ID**.

    ![Valda attribut och anspråk](./media/B2C_SignInSignUp_Attributes.png)

1. Skapa policyn genom att välja **OK**.
1. Dubbelklicka på det nya policynamnet och välj sedan **Egenskaper** i navigeringsfönstret.
1. Ange alternativet **aktivera JavaScript med tvingad sidlayout (förhandsgranskning)** till **På**.

    ![Egenskapssida för den nya policyn](./media/B2C_SignInSignUp_EnableJavascript.png)

> [!NOTE]
> Policynamnet kommer att refereras till i handelsmiljön. (Prefixet **B2C\_1\_** kommer att inkluderas i referensen.) Det går inte att byta namn på policyer när de har skapats. Om du ersätter en befintlig policy för din handelsmiljö, kan du ta bort den ursprungliga policyn och bygga en ny policy som har samma namn. Om miljön redan har etablerats kan du skicka det nya policynamnet via en tjänstbegäran.

Du kommer tillbaka till den här policyn för att slutföra installationen när du har byggt de anpassade sidorna. Stäng nu policyn för att återgå till sidan **användarflöden (policyer)** i Azure-portalen.

### <a name="configure-the-profile-editing-policy"></a>Konfigurera policyn för "profilredigering"

Gör på följande vis för att konfigurera policyn "profilredigering".

1. Välj **Nytt användarflöde**, välj **Profilredigering**, välj **Rekommenderad** och välj **Skapa**.
1. Ange ett namn på policyn (till exempel **B2C\_1\_EditProfile**).
1. I avsnittet **identitetsleverantörer** väljer du vilka identitetsleverantörer som ska användas för policyn. Åtminstone **Local Account SignIn** måste väljas.
1. I kolumnen **Samla in attribut** välj kryssrutorna för **förnamn** och **efternamn**.
1. I kolumnen **returanspråk** markerar du kryssrutorna för **e-postadresser**, **förnamn**, **identitetsleverantör**, **efternamn** och **användarens objekt-ID**.
1. Skapa policyn genom att välja **OK**.
1. Dubbelklicka på det nya policynamnet och välj sedan **Egenskaper** i navigeringsfönstret.
1. Ange alternativet **aktivera JavaScript med tvingad sidlayout (förhandsgranskning)** till **På**.

Du kommer tillbaka till den här policyn för att slutföra installationen när du har byggt de anpassade sidorna. Stäng nu policyn för att återgå till sidan **användarflöden (policyer)** i Azure-portalen.

### <a name="configure-the-password-reset-policy"></a>Konfigurera policyn "Återställ lösenord"

Gör på följande vis för att konfigurera policyn "Lösenordsåterställning".

1. Välj **Nytt användarflöde**, välj sedan alternativet **Återställ lösenord** och välj **Rekommenderad** och klicka på **Skapa**.
1. Ange ett namn på policyn (till exempel **B2C\_1\_ForgetPassword**).
1. I avsnittet **identitetsleverantörer** väljer du **Återställ lösenord med e-postadress**.
1. I kolumnen **returanspråk** markerar du kryssrutorna för **e-postadresser**, **förnamn**, **efternamn** och **användarens objekt-ID**.
1. Skapa policyn genom att välja **OK**.
1. Dubbelklicka på det nya policynamnet och välj sedan **Egenskaper** i navigeringsfönstret.
1. Ange alternativet **aktivera JavaScript med tvingad sidlayout (förhandsgranskning)** till **På**.

Du kommer tillbaka till den här policyn för att slutföra installationen när du har byggt de anpassade sidorna. Stäng nu policyn för att återgå till sidan **användarflöden (policyer)** i Azure-portalen.

## <a name="build-the-custom-pages"></a>Skapa anpassade sidor

Dedikerade Azure AD-moduler ingår i Commerce för att skapa anpassade sidor för Azure AD B2C-användarpolicyer. Sidor kan byggas specifikt för varje användarpolicysidas layout med hjälp av de Azure AD B2C huvudmoduler som beskrivs nedan. Du kan även använda modulen **AAD generisk** för alla sidlayouter och policyer i Azure AD B2C (även för sidlayoutalternativ inom de policyer som inte anges nedan). 

- Sidspecifika Azure AD-moduler är bundna till datainmatningsartiklar som återges av Azure AD B2C. Dessa moduler ger dig större kontroll över positionen för elementen på dina sidor. Det kan dock vara nödvändigt att skapa fler sidor och modultillägg som tar hänsyn till avvikelser utöver de standardinställningar som beskrivs nedan.
- Modulen **AAD generisk** skapa "div" element för Azure AD B2C att återge alla element i sidlayouten för användarpolicyn, vilket ger mer flexibilitet till sidans B2C-funktioner, men mindre kontroll över positionering och styling (dock CSS kan användas för att matcha utseendet på din webbplats).

Du kan skapa en enda sida med modulen **AAD generisk** och använda den för alla dina användarpolicy-sidor, eller så kan du bygga ut specifika sidor med individen Azure AD moduler för inloggning, registrering, profilredigering, återställning av lösenord och verifiering av lösenord. Du kan också använda en blandning av båda, med hjälp av det specifika Azure AD-sidor för de sidlayouter som anges nedan och den generella AAD-modulssidan för återstående sidlayouter på dessa eller andra sidor för användarpolicyer.

Om du vill veta mer om Azure AD moduler som levereras med modulbiblioteket kan du läsa mer på [identitetshanteringssidorna och modulerna](identity-mgmt-modules.md).

Att bygga anpassade sidor med specifika identitetsmoduler för att hantera användarinloggningar följer du stegen nedan.

1. I Commerce webbplatsskaparen, gå till din webbplats.
1. Bygg följande fem mallar och sidor (om de inte redan finns på webbplatsen):
    - Mallen **Logga in** och sida där inloggningsmodulen används.
    - Mallen **Registrera dig** och sida där registreringsmodulen används.
    - Mallen **lösenordsåterställning** och sidan med modulen lösenordsåterställning.
    - Mallen **verifiering av lösenordsåterställning** och sidan med modulen verifiering av lösenordsåterställning.
    - Mallen **profilredigering** och sidor som använder redigeringsmodulen för kontoprofilen.

Följ de här riktlinjerna när du skapar sidorna:

- För varje sida eller modul använder du layouten och formatet som bäst passar dina affärsbehov.
- Publicera alla sidor och URL som måste användas i Azure AD B2C-inställningar.
- När sidorna och adresserna har publicerats samlar du in de URL-adresser som måste användas för konfigurationer av Azure AD B2C-policy. Suffixet **?preloadscripts=true** kommer att läggas till varje URL när det används.

> [!IMPORTANT]
> Sidor som byggts i Azure AD B2C visas direkt från Azure AD B2C-innehavares domän. Återanvänd inte universella sidhuvuden och sidfötter med relativa länkar. Eftersom dessa sidor kommer att finnas i Azure AD B2C-domänen när de används, ska endast absoluta URL:er användas för alla länkar. Det rekommenderas att skapa en specifik sidhuvud och sidfot med absoluta webbadresser för din Azure AD-relaterade anpassade sidor, med alla Commerce-specifika moduler som kräver anslutning till Retail Server borttagen. Exempelvis ska inte modulerna för favoriter, sökfält, inloggning och kundvagn inkluderas på några sidor som används i Azure AD B2C-användarflöden.

## <a name="configure-azure-ad-b2c-policies-with-custom-page-information"></a>Konfigurera Azure AD B2C policyer med anpassad sidinformation 

I Azure-portalen, gå tillbaka till sidan **Azure AD B2C** och sedan på menyn under **Policyer**, välj **Användarflöden (policyer)**.

### <a name="update-the-sign-up-and-sign-in-policy-with-custom-page-information"></a>Uppdatera policyn "Registrera och logga in" med anpassad sidinformation

För att uppdatera policyn "Registrera och logga in" med anpassad sidinformation, följ dessa steg.

1. I policyn **Registrera och logga in** som du konfigurerade tidigare, i navigeringsfönstret, välj **Sidlayouter**.
1. Välj layouten **Enhetlig sida för registrera och logga in**.
1. Ställ in alternativet **Använd anpassat sidinnehåll** till **ja**.
1. I fältet **Anpassad sid-URI** ange fullständig inloggnings-URL. Inkludera suffixet **?preloadscripts=true**. Ange exempelvis ``www.<my domain>.com/sign-in?preloadscripts=true``.
1. I fältet **Version av sidlayout** väljer version **2.1.0** eller senare (kräver modulbibliotek för Commerce version 10.0.15 eller högre).
1. Välj **Spara**.
1. Välj layouten **sida för registrering av lokalt konto**.
1. Ställ in alternativet **Använd anpassat sidinnehåll** till **ja**.
1. I fältet **Anpassad sid-URI** ange fullständig inloggnings-URL. Inkludera suffixet **?preloadscripts=true**. Ange exempelvis ``www.<my domain>.com/sign-up?preloadscripts=true``.
1. I fältet **Version av sidlayout** väljer version **2.1.0** eller senare (kräver modulbibliotek för Commerce version 10.0.15 eller högre).
1. I avsnittet **Användarattribut** följ dessa steg:
    1. För attributen **förnamn** och **efternamn**, välj **Nej** i kolumnen **Kräver verifiering**.
    1. För **E-postadress**, det rekommenderas att lämna standardvärdet **Ja** som väljs i kolumnen **Kräver verifiering**. Det här alternativet garanterar att användarna registrerar sig med en viss e-postadress och verifierar att de har e-postadressen.
    1. För attributen **e-postadress**, **förnamn** och **efternamn** väljer du **nej** i kolumnen **Valfritt**.
1. Välj **Spara**.

    ![Konfiguration av policyn sida för registrering av lokalt konto](./media/B2C_SignInSignUp_Recommended_PageLayoutExample.png)

### <a name="update-the-profile-editing-policy-with-custom-page-information"></a>Uppdatera policyn "Profilredigering" med anpassad sidinformation

För att uppdatera policyn "Profilredigering" med anpassad sidinformation, följ dessa steg.

1. I policyn **Profilredigering** som du konfigurerade tidigare, i navigeringsfönstret, välj **Sidlayouter**.
1. Välj layout **Profilredigeringssida** (kan kräva att du rullar nedför andra layoutalternativ, beroende på skärm).
1. Ställ in alternativet **Använd anpassat sidinnehåll** till **ja**.
1. I fältet **Anpassad sid-URI** ange fullständig profil redigerings-URL. Inkludera suffixet **?preloadscripts=true**. Ange exempelvis ``www.<my domain>.com/profile-edit?preloadscripts=true``.
1. För **Version av sidlayout** väljer version **2.1.0** eller högre (kräver modulbibliotek för Commerce version 10.0.15 eller högre).
1. I avsnittet **Användarattribut** följ dessa steg:
    1. För attributen **förnamn** och **efternamn** välj **nej** i kolumnen **valfritt**.
    1. För attributen **förnamn** och **efternamn**, välj **Nej** i kolumnen **Kräver verifiering**.
1. Välj **Spara**.

### <a name="update-the-password-reset-policy-with-custom-page-information"></a>Uppdatera policyn "Lösenordsåterställning" med anpassad sidinformation

För att uppdatera policyn "Lösenordsåterställning" med anpassad sidinformation, följ dessa steg.

1. I policyn **Lösenordsåterställning** som du konfigurerade tidigare, i navigeringsfönstret, välj **Sidlayouter**.
1. Välj layouten **Glömt lösenordssida**.
1. Ställ in alternativet **Använd anpassat sidinnehåll** till **ja**.
1. I fältet **Anpassad sid-URI** ange fullständig lösenordsåterställning verifierings-URL. Inkludera suffixet **?preloadscripts=true**. Ange exempelvis ``www.<my domain>.com/password-reset-verification?preloadscripts=true``.
1. I fältet **Version av sidlayout** väljer version **2.1.0** eller senare (kräver modulbibliotek för Commerce version 10.0.15 eller högre).
2. Välj **Spara**.
3. Välj layouten **Ändra lösenordssida**.
4. Ställ in alternativet **Använd anpassat sidinnehåll** till **ja**.
5. I fältet **Anpassad sid-URI** ange fullständig lösenordsåterställnings-URL. Inkludera suffixet **?preloadscripts=true**. Ange exempelvis ``www.<my domain>.com/password-reset?preloadscripts=true``.
6. I fältet **Version av sidlayout** väljer version **2.1.0** eller senare (kräver modulbibliotek för Commerce version 10.0.15 eller högre).
7. Välj **Spara**.

## <a name="customize-default-text-strings-for-labels-and-descriptions"></a>Anpassa standardtextsträngar för etiketter och beskrivningar

I modulbiblioteket är inloggningsmoduler förifyllda med standardtextsträngar för etiketterna och beskrivningarna. Du kan anpassa strängerna i egenskapsfönstret i den modul du arbetar på. Ytterligare strängar på sidan, (t.ex. länktexten **Glömt lösenord?** eller åtgärdstexten **Skapa ett konto**) kräver att du använder Commerce programutvecklingskit (SDK) och uppdaterar värdena i filen global.json för inloggningsmodulen.

Standardtexten för länken Glömt lösenordet är **glömt lösenord?**. Nedan visas den här standardtexten på inloggningssidan.

![Standardtext för länken Glömt lösenordet på inloggningssidan](./media/B2C_SignUp_ModuleFace.png)

I global.json-filen för modulen modulbibliotek kan du emellertid redigera texten till **glömt lösenordet?**, som du ser i bilden nedan.

![Länktexten uppdaterades i loggen i modulens global.json-fil](./media/B2C_CustomizingStringsForModule.png)

När du har uppdaterat global.json-filen och publicerat ändringarna, visas den nya länktexten i modulen logga in både i handel och på live-inloggningssidan.

## <a name="additional-resources"></a>Ytterligare resurser

[Konfigurera ditt domännamn](configure-your-domain-name.md)

[Distribuera en ny klientorganisation för näthandel](deploy-ecommerce-site.md)

[Skapa en näthandelssajt](create-ecommerce-site.md)

[Associera en Dynamics 365 Commerce-webbplats med en onlinekanal](associate-site-online-store.md)

[Hantera robots.txt-filer](manage-robots-txt-files.md)

[Överför URL-omdirigeringar i bulk](upload-bulk-redirects.md)

[Ställa in en B2C-innehavare i Commerce](set-up-B2C-tenant.md)

[Konfigurera flera B2C-innehavare i en Commerce-miljö](configure-multi-B2C-tenants.md)

[Lägga till stöd för ett innehållsleveransnätverk (CDN)](add-cdn-support.md)

[Aktivera platsbaserad butiksdetektering](enable-store-detection.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]