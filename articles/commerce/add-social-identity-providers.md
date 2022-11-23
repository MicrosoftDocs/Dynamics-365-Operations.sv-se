---
title: Lägg till sociala identitetsleverantör
description: I den här artikeln beskrivs hur du lägger till tillhandahållare av social identitet på Microsoft Azure-portalen.
author: BrianShook
ms.date: 11/15/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2020-02-13
ms.openlocfilehash: 5596097a5484acafda54adcfffa68fb59c8fbc65
ms.sourcegitcommit: 774f8f97a0b14cf1199bd1802178ccf536a25ade
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/17/2022
ms.locfileid: "9785277"
---
# <a name="add-social-identity-providers"></a>Lägg till sociala identitetsleverantör

[!include [banner](includes/banner.md)]

I den här artikeln beskrivs hur du lägger till tillhandahållare av social identitet på Microsoft Azure-portalen.

Med sociala identitetsleverantör kan användarna använda sina sociala konton för autentisering. Att lägga till sociala identitetsleverantör är valfritt i Dynamics 365 Commerce. 

Om autentiseringen av sociala identitetsleverantör inte läggs till blir Azure Active Directory (Azure AD) B2C-profiler huvudprofilerna för användarbasen. Användarna väljer sina egna användarnamn (deras standard-e-postadress) och anger ett lösenord. Azure AD B2C kommer att autentisera användare direkt. 

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

> [!NOTE]
> Att lägga till tillhandahållare av social identitet är ett valfritt steg när du ställer in en B2C-innehavare i Microsoft Dynamics 365 Commerce.

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
1. Om du vill koppla användarflödespolicyn för inloggning/registrering markerar du varje identitetsleverantör som du har skapat för ditt konto. Om du vill testa flöden väljer du **kör användarflöde** för varje identitetsleverantör. På en ny flik visas inloggningssidan med den nya valrutan för identitetsleverantörer.

Följande bild illustrerar exempel på skärmarna **lägga till identitetsleverantören** och **konfigurerar social identitetsleverantören** i Azure AD B2C.

![Lägga till en social identitetsleverantör i ditt program.](./media/B2CImage_14.png)

I följande bild visas ett exempel på hur du väljer identitetsleverantörer på sidan Azure AD B2C **identitetsleverantörer**.

![Välj varje social identitetsleverantör som ska aktiveras för din policy.](./media/B2CImage_16.png)

I bilden nedan visas ett exempel på en standard inloggningsskärm med knappen för inloggning med sociala identitetsleverantörer som visas.

> [!NOTE]
> Om du använder de anpassade sidorna som är inbyggda i Commerce för dina användarflöden måste knapparna för sociala identitetsleverantörer läggas till med hjälp av utökningsfunktionerna i Commerce-modulbiblioteket. När du konfigurerar program med en viss leverantör av social identitet, kan URL-adressen eller konfigurationssträngen i vissa fall vara ärendekänslig. Mer information finns i anslutningsinstruktioner för din personidentitetsprovider.
 
![Exempel på standardinloggningsskärm när inloggningsknappen för sociala identitetsleverantörer visas.](./media/B2CImage_17.png)

## <a name="next-steps"></a>Nästa steg

För att fortsätta processen med att skapa en B2C-innehavare i Commerce, fortsätt till [Uppdatera Commerce headquarters med den nya Azure AD B2C-informationen](update-hq-aad-b2c-info.md).

## <a name="additional-resources"></a>Ytterligare resurser

[Ställa in en B2C-innehavare i Commerce](set-up-b2c-tenant.md)

[Skapa eller länka till en befintlig Azure AD B2C-klientorganisation i Azure-portalen](create-link-aad-b2c-tenant.md)

[Skapa B2C-applikationen](create-b2c-app.md)

[Skapa policyer för användarflöden](create-user-flow-policies.md)

[Uppdatera Commerce headquarters med den nya Azure AD B2C-informationen](update-hq-aad-b2c-info.md)

[Konfigurera din B2C-innehavare i Commerce webbplatsskaparen](config-b2c-tenant-site-builder.md)

[Ytterligare B2C-information](additional-b2c-info.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
