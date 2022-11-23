---
title: Ytterligare B2C-information
description: Den här artikeln innehåller mer information om hur du anger din B2C-innehavare i Microsoft Dynamics 365 Commerce.
author: BrianShook
ms.date: 11/14/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2020-02-13
ms.openlocfilehash: b60ef15544cd30c44968ee7a588a8a9fb08e8223
ms.sourcegitcommit: 774f8f97a0b14cf1199bd1802178ccf536a25ade
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/17/2022
ms.locfileid: "9785274"
---
# <a name="additional-b2c-information"></a>Ytterligare B2C-information

[!include [banner](includes/banner.md)]

Den här artikeln innehåller mer information om hur du anger din B2C-innehavare i Microsoft Dynamics 365 Commerce.

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

[Ställa in en B2C-innehavare i Commerce](set-up-b2c-tenant.md)

[Skapa eller länka till en befintlig Azure AD B2C-klientorganisation i Azure-portalen](create-link-aad-b2c-tenant.md)

[Skapa B2C-applikationen](create-b2c-app.md)

[Skapa policyer för användarflöden](create-user-flow-policies.md)

[Lägg till sociala identitetsleverantör (valfritt)](add-social-identity-providers.md)

[Uppdatera Commerce headquarters med den nya Azure AD B2C-informationen](update-hq-aad-b2c-info.md)

[Konfigurera din B2C-innehavare i Commerce webbplatsskaparen](config-b2c-tenant-site-builder.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
