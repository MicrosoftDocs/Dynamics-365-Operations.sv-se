---
title: Skapa policyer för användarflöden
description: I den här artikeln beskrivs hur du skapar användarflödesprinciper i Microsoft Azure-portalen.
author: BrianShook
ms.date: 11/15/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2020-02-13
ms.openlocfilehash: 91b9d99dfd8c3d100ca197aa499ca86799bbffc8
ms.sourcegitcommit: 774f8f97a0b14cf1199bd1802178ccf536a25ade
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/17/2022
ms.locfileid: "9785310"
---
# <a name="create-user-flow-policies"></a>Skapa policyer för användarflöden

[!include [banner](includes/banner.md)]

I den här artikeln beskrivs hur du skapar användarflödesprinciper i Microsoft Azure-portalen.

Användarflöden är de policyer Azure Active Directory (Azure AD) B2C använder för att tillhandahålla säker inloggning, registrera, redigera profil och glömma användarupplevelser för lösenord. Dynamics 365 Commerce använder dessa flöden för att utföra policyåtgärder för samverkan med Azure AD B2C-innehavaren. När en användare interagerar med dessa principer, omdirigeras de till Azure AD B2C-innehavaren för att utföra åtgärderna.

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

## <a name="next-steps"></a>Nästa steg

För att fortsätta processen att ställa in B2C-innehavare Commerce, gå till [Lägg till sociala identitetsleverantör](add-social-identity-providers.md).

## <a name="additional-resources"></a>Ytterligare resurser

[Ställa in en B2C-innehavare i Commerce](set-up-b2c-tenant.md)

[Skapa eller länka till en befintlig Azure AD B2C-klientorganisation i Azure-portalen](create-link-aad-b2c-tenant.md)

[Skapa B2C-applikationen](create-b2c-app.md)

[Lägg till sociala identitetsleverantör (valfritt)](add-social-identity-providers.md)

[Uppdatera Commerce headquarters med den nya Azure AD B2C-informationen](update-hq-aad-b2c-info.md)

[Konfigurera din B2C-innehavare i Commerce webbplatsskaparen](config-b2c-tenant-site-builder.md)

[Ytterligare B2C-information](additional-b2c-info.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
