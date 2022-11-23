---
title: Skapa B2C-app
description: I den här artikeln beskrivs hur du skapar ett B2C-app i Microsoft Azure-portal.
author: BrianShook
ms.date: 11/15/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2020-02-13
ms.openlocfilehash: d8956d51bac7bf2a162a370ae5ef1c7e7cdc1e2f
ms.sourcegitcommit: 774f8f97a0b14cf1199bd1802178ccf536a25ade
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/17/2022
ms.locfileid: "9785292"
---
# <a name="create-a-b2c-application"></a>Skapa B2C-app

[!include [banner](includes/banner.md)]

I den här artikeln beskrivs hur du skapar ett B2C-app i Microsoft Azure-portal.

När B2C-innehavaren har skapats kommer du att skapa ett B2C-program inom din nya Azure Active Directory (Azure AD)-innehavare för att samverka med Commerce.

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

## <a name="next-steps"></a>Nästa steg

För att fortsätta processen att ställa in B2C-innehavare Commerce, gå till [Skapa användarflödespolicyer](create-user-flow-policies.md).

## <a name="additional-resources"></a>Ytterligare resurser

[Ställa in en B2C-innehavare i Commerce](set-up-b2c-tenant.md)

[Skapa eller länka till en befintlig Azure AD B2C-klientorganisation i Azure-portalen](create-link-aad-b2c-tenant.md)

[Skapa policyer för användarflöden](create-user-flow-policies.md)

[Lägg till sociala identitetsleverantör (valfritt)](add-social-identity-providers.md)

[Uppdatera Commerce headquarters med den nya Azure AD B2C-informationen](update-hq-aad-b2c-info.md)

[Konfigurera din B2C-innehavare i Commerce webbplatsskaparen](config-b2c-tenant-site-builder.md)

[Ytterligare B2C-information](additional-b2c-info.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
