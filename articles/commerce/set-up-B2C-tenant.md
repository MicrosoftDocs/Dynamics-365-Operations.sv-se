---
title: Ställa in en B2C-innehavare i Commerce
description: I denna artikel beskrivs hur du konfigurerar din Azure Active Directory (Azure AD) B2C-innehavare (Business-to-Consumer) för autentisering av användarplats i Microsoft Dynamics 365 Commerce.
author: BrianShook
ms.date: 11/15/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2020-02-13
ms.openlocfilehash: 3421dd3d67198a99ac236a56cbb4f300cb591a03
ms.sourcegitcommit: 774f8f97a0b14cf1199bd1802178ccf536a25ade
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/17/2022
ms.locfileid: "9785155"
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

## <a name="next-steps"></a>Nästa steg

För att fortsätta processen med att skapa en B2C-innehavare i Commerce, fortsätt till [Skapa eller länka till en befintlig Azure AD B2C-innehavare i Azure-portal](create-link-aad-b2c-tenant.md).

## <a name="additional-resources"></a>Ytterligare resurser

[Skapa eller länka till en befintlig Azure AD B2C-klientorganisation i Azure-portalen](create-link-aad-b2c-tenant.md)

[Skapa B2C-applikationen](create-b2c-app.md)

[Skapa policyer för användarflöden](create-user-flow-policies.md)

[Lägg till sociala identitetsleverantör (valfritt)](add-social-identity-providers.md)

[Uppdatera Commerce headquarters med den nya Azure AD B2C-informationen](update-hq-aad-b2c-info.md)

[Konfigurera din B2C-innehavare i Commerce webbplatsskaparen](config-b2c-tenant-site-builder.md)

[Ytterligare B2C-information](additional-b2c-info.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
