---
title: Konfigurera flera B2C-innehavare i en Commerce-miljö
description: Det här avsnittet beskriver när och hur du ställer in flera Microsoft Azure Active Directory (Azure AD) B2C-innehavare för användarautentisering i en dedikerad Dynamics 365 Commerce-miljö.
author: BrianShook
manager: annbe
ms.date: 03/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: brshoo
ms.search.validFrom: 2020-02-12
ms.dyn365.ops.version: ''
ms.openlocfilehash: 9a1af453349d69ef94d725e138a898c73ea052fa
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4997610"
---
# <a name="configure-multiple-b2c-tenants-in-a-commerce-environment"></a>Konfigurera flera B2C-innehavare i en Commerce-miljö

[!include [banner](includes/banner.md)]

Det här avsnittet beskriver när och hur du ställer in flera Microsoft Azure Active Directory (Azure AD) B2C-innehavare per kanal för användarautentisering i en dedikerad Dynamics 365 Commerce-miljö.

## <a name="overview"></a>Översikt

Dynamics 365 Commerce använder Azure AD B2C molnidentitetstjänst för att stödja autentiseringsuppgifter och verifikationsflöden. Användare kan använda verifikationsflöden för att registrera, logga in och återställa sitt lösenord. Azure AD B2C lagrar känslig en användares känsliga autentiseringsinformation, t.ex. hans eller hennes namn och lösenord. Användarposten är unik för varje B2C-innehavare och använder antingen användarnamn (e-postadress) autentiseringsuppgifter eller autentiseringsuppgifter för social identitet.

I de flesta fall används en enda Azure AD B2C-innehavare i en Commerce-miljö. Commerce-kunder kan sedan skapa och publicera flera webbplatser i samma Commerce-miljö och samma kundautentiseringsuppgifter kommer att användas på dessa webbplatser. Om webbplatserna i miljön ska behandlas som olika varumärken och visas för användarna som separata företag, kan en B2C-innehavare konfigureras för den kanal som används för webbplatsens/varumärkets separation.

## <a name="considerations-when-multiple-b2c-tenants-are-set-up-per-channel"></a>Att tänka på när flera B2C-innehavare ställs in per kanal

När varje kanal eller webbplats behandlas som ett separat företag är det bästa alternativet med avseende på användarverifieringsflöden i Commerce att använda separata juridiska enheter. Om du däremot vill behålla varje kanal/plats i samma miljö och juridisk person, men vill ha separata användarautentisering för varje webbplats, är det viktigt att du tänker på följande saker innan du går vidare:

- Användarna får sina egna unika autentiseringsuppgifter för varje kanal/webbplats.

    Samma person kan ha två separata konton per kanal/webbplats, eftersom varje konto är en unik post i en separat B2C-innehavare.

- I Microsoft Dynamics-miljön kommer separata kundposter att returneras för globala postsökningar.

    Om en användare använder samma e-postadress för kanaler/webbplatser returnerar globala kundsökningar resultat för varje kanal/webbplats. (En kanalindikator visas.)

- Adressboken kan användas för att hjälpa till att gruppera användare, så att de kan spåras per kanal.
- Antalet kundposter per kanal kan öka och denna ökning kan påverka prestandan hos globala kundsökningar.
- B2C-innehavare måste mappas omsorgsfullt till en kanal, för att förhindra situationer där kunder registrerar sig för fel innehavare. I annat fall kan förvirring och spårningsproblem uppstå.

I bilden nedan visas flera B2C-innehavare i en Commerce-miljö.

![Flera B2C-innehavare i en Commerce-miljö](media/MultiB2C_In_Environment.png)

Om du bestämmer dig för att ditt företag kräver distinkta B2C-innehavare per kanal i samma Commerce-miljö, måste du utföra procedurerna i följande avsnitt för att kunna begära den här funktionen.

## <a name="request-that-b2c-per-channel-be-enabled-in-your-environment"></a>Begär att B2C per kanal aktiveras i din miljö

För närvarande, om du vill att olika B2C-innehavare per kanal ska vara tillgängliga i samma Commerce-miljö, måste du skicka en begäran till Dynamics 365 Commerce. Mer information finns i [få support för Lifecycle Services (LCS)](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md) eller diskutera det här problemet med din kontakt för Commerce-lösningen.

## <a name="configure-b2c-tenants-in-your-environment"></a>Konfigurera B2C-innehavare i miljön

Om du vill konfigurera B2C-innehavare i miljön ska du slutföra de relevanta procedurerna i det här avsnittet.

### <a name="add-an-azure-ad-b2c-tenant"></a>Lägg till en Azure AD B2C-innehavare

Följ stegen nedan för att lägga till en Azure AD B2C-innehavare i din miljö.

1. Logga in på Commerce webbplatsskapare för din miljö som systemadministratör. Om du vill konfigurera Azure AD B2C-innehavare måste du vara systemadministratör för Commerce-miljön.
1. I det vänstra navigeringsfönstret väljer du **innehavarinställningar** för att expandera den.
1. Välj **B2C-inställningar**, och välj sedan **Hantera**.
1. Välj **Lägg till B2C-program** och ange sedan följande information:

    - **Programnamn**: Ange namnet som ska användas för programmet i samband med hantering av det i Commerce. Vi rekommenderar att du använder det programnamn som du väljer när du ställer in Azure AD B2C-programmet i Azure-portalen. På det här sättet kan du minska förvirring när du hanterar B2C-innehavare i Commerce.
    - **Klientnamn**: Ange det B2C-innehavare som det visas i Azure-portalen.
    - **Glömt lösenordspolicy-ID**: Ange policy-ID (namnet på principen i Azure-portalen).
    - **Policy-ID för registrering och inloggning**: Ange policy-ID (namnet på principen i Azure-portalen).
    - **Klient-GUID**: Ange Azure AD B2C innehavar-ID så som det visas i Azure-portalen (inte program-ID för B2C-innehavare).
    - **Redigera profil för policy-ID**: Ange policy-ID (namnet på principen i Azure-portalen).

1. När du har angett den här informationen väljer du **OK** för att spara ändringarna.

> [!NOTE]
> Du bör lämna fält som **Omfattning**, **Icke-interaktivt policy-ID**, **Icke-interaktivt klient-ID**, **Anpassad domän för inloggning** och **Policy-ID för registrering** tomma om inte teamet för Dynamics 365 Commerce uppmanar dig att ställa in dem.
Den nya Azure AD B2C-innehavaren ska nu visas i listan under **hantera B2C-program**.

### <a name="manage-or-delete-an-azure-ad-b2c-tenant"></a>Hantera eller ta bort Azure AD B2C-innehavare

1. Logga in på Commerce webbplatsskapare för din miljö som systemadministratör. Om du vill konfigurera Azure AD B2C-innehavare måste du vara systemadministratör för Commerce-miljön.
1. I det vänstra navigeringsfönstret väljer du **innehavarinställningar** för att expandera den.
1. Välj **B2C-inställningar**, och välj sedan **Hantera**.
1. Om du vill redigera en B2C-innehavare väljer du pennsymbolen bredvid. Om du vill ta bort en B2C-innehavare väljer du symbolen bredvid papperskorgen.
1. Välj **spara** och välj sedan **publicera** för att aktivera ändringarna.

> [!WARNING]
> När en B2C-innehavare har konfigurerats för en pågående/publicerad plats, kan användare ha registrerat sig genom att använda konton som finns på innehavaren. Om du tar bort en konfigurerad innehavare på menyn **innehavarinställningar \> B2C-innehavare** tar du bort kopplingen till den B2C-innehavare från webbplatser som är associerade med eventuella kanaler hos innehavaren. I det här fallet kanske användarna inte längre kan logga in på sina konton. Använd därför yttersta försiktighet när du tar bort en konfigurerad innehavare.
>
> När en konfigurerad innehavare tas bort kommer B2C-innehavaren och posterna att fortsätta underhållas, men systemkonfigurationen för den innehavaren kommer att ändras eller tas bort. Användare som försöker registrera sig eller logga in på webbplatsen skapar en ny kontopost i den standard- eller B2C-innehavare som har konfigurerats för webbplatsens kanal.
## <a name="configure-your-channel-with-a-b2c-tenant"></a>Konfigurera kanalen med en B2C-innehavare

1. Logga in på Commerce webbplatsskapare för din miljö som systemadministratör. Om du vill konfigurera Azure AD B2C-innehavare måste du vara systemadministratör för Commerce-miljön.
1. I det vänstra navigeringsfönstret väljer du **Webbplatsinställningar** för att expandera den.
1. Välj **kanaler** och välj sedan vilken kanal som ska konfigureras.
1. I egenskapsfönstret till höger i fältet **Välj B2C-program**, välj konfigurerad Azure AD B2C-innehavare som ska användas för denna kanal.
1. I kommandofältet väljer du **spara och publicera** för att bekräfta den nya eller uppdaterade konfigurationen.

> [!WARNING]
> Om du ändrar det B2C-program som har tilldelats till kanalen, tar du bort aktuella referenser som har upprättats för användare som redan har registrerat dig i miljön. I detta fall kommer eventuella autentiseringsuppgifter som associeras med det B2C programmet inte att vara tillgängliga för användarna. Ändra därför bara en kanal Azure AD B2C konfiguration om du ställer in kanalen för första gången och inga användare har kunnat registrera sig. Annars kan användarna behöva registrera sig igen för att upprätta en post i den nya Azure AD B2C-innehavaren.
## <a name="additional-resources"></a>Ytterligare resurser

[Konfigurera ditt domännamn](configure-your-domain-name.md)

[Distribuera en ny klientorganisation för näthandel](deploy-ecommerce-site.md)

[Skapa en näthandelssajt](create-ecommerce-site.md)

[Associera en Dynamics 365 Commerce-webbplats med en onlinekanal](associate-site-online-store.md)

[Hantera robots.txt-filer](manage-robots-txt-files.md)

[Överför URL-omdirigeringar i bulk](upload-bulk-redirects.md)

[Ställa in en B2C-innehavare i Commerce](set-up-B2C-tenant.md)

[Ställa in anpassade sidor för användarinloggningar](custom-pages-user-logins.md)

[Lägga till stöd för ett innehållsleveransnätverk (CDN)](add-cdn-support.md)

[Aktivera platsbaserad butiksdetektering](enable-store-detection.md)
