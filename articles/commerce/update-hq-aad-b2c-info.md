---
title: Uppdatera Commerce headquarters med den nya Azure AD B2C-informationen
description: I den här artikeln beskrivs hur du uppdaterar Microsoft Dynamics 365 Commerce headquarters med ny Azure Active Directory (Azure AD) B2C-information.
author: BrianShook
ms.date: 11/15/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2020-02-13
ms.openlocfilehash: c65949ff97182d2692319ac2af00e3ef35a79580
ms.sourcegitcommit: 774f8f97a0b14cf1199bd1802178ccf536a25ade
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/17/2022
ms.locfileid: "9785328"
---
# <a name="update-commerce-headquarters-with-the-new-azure-ad-b2c-information"></a>Uppdatera Commerce headquarters med den nya Azure AD B2C-informationen

[!include [banner](includes/banner.md)]

I den här artikeln beskrivs hur du uppdaterar Microsoft Dynamics 365 Commerce headquarters med ny Azure Active Directory (Azure AD) B2C-information.

När Azure AD B2C etableringsstegen ovan har slutförts måste Azure AD B2C-programmet vara registrerat i din Dynamics 365 Commerce-miljö.

Om du vill uppdatera huvud kontoret med den nya Azure AD B2C-informationen följer du stegen nedan.

1. I Commerce går du till **delade Commerce-parametrar** och väljer **identitetsleverantörer** på den vänstra menyn.
1. Under **identitetsleverantörer** gör du följande:
    1. I rutan **utfärdare** anger du sträng för identitetsleverantörens utfärdare. För att hitta din utfärdarsträng, se [Skaffa utfärdarsträng för inställning av huvudkontoret](#obtain-issuer-string-for-headquarters-setup) nedan.
    1. I rutan **Namn**, ange ett namn för din utfärdarpost.
    1. I rutan **Typ**, ange **Azure AD B2C (id_token)**.
1. Under **Förlitande parter**, med ovanstående B2C för identitetsleverantör:
    1. I rutan **ClientID** ange din B2C-app ID, som du hittar i rutan **App-ID** i B2C-appens egenskapssida.
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

## <a name="next-steps"></a>Nästa steg

Fortsätt processen med att ställa in en B2C-innehavare i Commerce genom att gå vidare till [Konfigurera B2C-innehavare i Commerce webbplatsskaparen](config-b2c-tenant-site-builder.md).

## <a name="additional-resources"></a>Ytterligare resurser

[Ställa in en B2C-innehavare i Commerce](set-up-b2c-tenant.md)

[Skapa eller länka till en befintlig Azure AD B2C-klientorganisation i Azure-portalen](create-link-aad-b2c-tenant.md)

[Skapa B2C-applikationen](create-b2c-app.md)

[Skapa policyer för användarflöden](create-user-flow-policies.md)

[Lägg till sociala identitetsleverantör (valfritt)](add-social-identity-providers.md)

[Konfigurera din B2C-innehavare i Commerce webbplatsskaparen](config-b2c-tenant-site-builder.md)

[Ytterligare B2C-information](additional-b2c-info.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
