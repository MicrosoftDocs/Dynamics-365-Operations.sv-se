---
title: Konfigurera din B2C-innehavare i Commerce webbplatsskaparen
description: I denna artikel beskrivs hur du konfigurerar din B2C-innehavare i Microsoft Dynamics 365 Commerce webbplatsskaparen.
author: BrianShook
ms.date: 11/15/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2020-02-13
ms.openlocfilehash: 181edf1570f1a9d071a7fae38ff9d73ff3c068fa
ms.sourcegitcommit: 774f8f97a0b14cf1199bd1802178ccf536a25ade
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/17/2022
ms.locfileid: "9785313"
---
# <a name="configure-your-b2c-tenant-in-commerce-site-builder"></a>Konfigurera din B2C-innehavare i Commerce webbplatsskaparen

[!include [banner](includes/banner.md)]

I denna artikel beskrivs hur du konfigurerar din B2C-innehavare i Microsoft Dynamics 365 Commerce webbplatsskaparen.

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

Det valfria fältet **Anpassad domän för inloggning** ska endast användas om du konfigurerar en anpassad domän för Azure AD B2C-klientorganisationen. Mer information och beaktanden om hur du använder fältet **Anpassad domän för inloggning** finns i [Ytterligare B2C-information](additional-b2c-info.md).

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

## <a name="next-steps"></a>Nästa steg

För att fortsätta processen att ställa in B2C-innehavare Commerce, gå till [Ytterligare B2C-information](additional-b2c-info.md).

## <a name="additional-resources"></a>Ytterligare resurser

[Ställa in en B2C-innehavare i Commerce](set-up-b2c-tenant.md)

[Skapa eller länka till en befintlig Azure AD B2C-klientorganisation i Azure-portalen](create-link-aad-b2c-tenant.md)

[Skapa B2C-applikationen](create-b2c-app.md)

[Skapa policyer för användarflöden](create-user-flow-policies.md)

[Lägg till sociala identitetsleverantör (valfritt)](add-social-identity-providers.md)

[Uppdatera Commerce headquarters med den nya Azure AD B2C-informationen](update-hq-aad-b2c-info.md)

[Ytterligare B2C-information](additional-b2c-info.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
