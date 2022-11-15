---
title: Konfigurera CPOS för att använda ett eget Azure AD program
description: I den här artikeln förklaras hur du konfigurerar Cloud POS (CPOS) för att använda ett anpassat Azure Active Directory (Azure AD) program.
author: boycez
ms.date: 11/04/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.search.region: global
ms.author: boycez
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: 5e4ff797410e1e94869cc37684e7622ec0d97842
ms.sourcegitcommit: 9e2e54ff7d15aa51e58309da3eb52366328e199d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/04/2022
ms.locfileid: "9746271"
---
# <a name="configure-cpos-to-use-a-custom-azure-ad-app"></a>Konfigurera CPOS för att använda ett eget Azure AD program

[!include [banner](includes/banner.md)]

Som standard pekar Cloud POS (CPOS) i Microsoft Dynamics 365 Commerce på en registrerad förstaparts Microsoft-app i Azure Active Directory (Azure AD). Därför kan du använda CPOS utan att behöva göra några ändringar i .Azure AD. Du kanske däremot vill peka ut instansen av CPOS till ett anpassat Azure AD program som du styr. I den här artikeln förklaras hur du konfigurerar CPOS för att använda ett anpassat Azure AD-program.

## <a name="set-up-a-custom-retail-server-app-in-azure-ad"></a>Ställa in ett anpassat Retail Server-program i Azure AD

Följ de här stegen om du vill skapa och konfigurera ett anpassat Retail Server-program i Azure AD.

1. Logga in på [Azure Active Directory administratörscentret](https://aad.portal.azure.com) med något Azure AD användarkonto. Användarkontot behöver inte ha administratörsbehörighet.
1. Markera **Azure Active Directory**.
1. Välj **Appregistreringar** och välj sedan **Ny registrering** för att öppna dialogrutan **Registrera ett program**.
1. Ange följande fält.

    - **Namn** – Ange ett anpassat namn för appen. Ange till exempel **Anpassad Retail Server**.
    - **Kontotyper som stöds** – Välj standardalternativet, **Konton endast i denna organisationskatalog (Endast Microsoft – en innehavare)**.
    - **Omdirigerings-URI** – Det här fältet är valfritt. Lämna tomt.
    - **Tjänst träd-ID** – Det här fältet är valfritt. Lämna tomt.
    
1. Välj **Registrera**. Konfigurationssidan för den nyregistrerade appen visas.
1. I avsnittet **Översikt \> Grundläggande** välj **Lägg till en app-ID-URI** och välj **Ställ in** bredvid **App-ID URI**. Notera det föreslagna värdet och välj **Spara** om du vill acceptera det värdet. 
1. Välj **Lägg till omfattning** och ange följande fält:

    - **Omfattningens namn** – Ange ett anpassat namn för omfattningen. Ange till exempel **Legacy.Access.Full**.
    - **Vem kan samtycka** – Ange om både administratörer och användare eller bara administratörer kan ge samtycke, baserat på din organisations säkerhetspolicyer.
    - **Visningsnamn för administratörsmedgivande** – Ange ett visningsnamn. Ange till exempel **Åtkomst till Retail Server**.
    - **Beskrivning av administratörsmedgivande** – Ange en beskrivning. Ange till exempel **Ger åtkomst till Retail Server API:er**.

1. Välj **Lägg till omfattning** för att slutföra genereringsprocessen för omfattning.

## <a name="set-up-a-custom-cpos-app-in-azure-ad"></a>Ställa in en anpassad CPOS-app i Azure AD

> [!IMPORTANT]
> Om du uppgraderar ett befintligt anpassat CPOS Azure AD app som skapades före Commerce version 10.0.21 följer du stegen i [Uppgradera en befintligt anpassad CPOS Azure AD app skapad före Commerce version 10.0.21](#upgrade-an-existing-custom-cpos-azure-ad-app-created-before-commerce-version-10021).

Följ de här stegen om du vill skapa och konfigurera ett anpassat CPOS-program i Azure AD.

1. Logga in på [Azure Active Directory administratörscentret](https://aad.portal.azure.com) med något Azure AD användarkonto. Användarkontot behöver inte ha administratörsbehörighet.
1. Markera **Azure Active Directory**.
1. Välj **Appregistreringar** och välj sedan **Ny registrering** för att öppna dialogrutan **Registrera ett program**.
1. Ange följande fält.

    - **Namn** – Ange ett namn för appen. Ange till exempel **Anpassad Cloud POS**.
    - **Kontotyper som stöds** – Välj standardalternativet, **Konton endast i denna organisationskatalog (Endast Microsoft – en innehavare)**.
    - **Omdirigerings-URI** – Välj **Ensidig app (SPA)** i listrutan och ange sedan CPOS-URI.
    - **Tjänst träd-ID** – Det här fältet är valfritt. Lämna tomt.

1. Välj **Registrera**. Konfigurationssidan för den nyregistrerade appen visas.
1. I avsnittet **Manifest** ange parametrarna **oauth2AllowIdTokenImplicitFlow** och **oauth2AllowImplicitFlow** till **true** och sedan **Spara**.
1. I avsnittet **Tokenkonfiguration** om du vill lägga till två anspråk:

    1. Välj **Lägg till ytterligare anspråk**. Ange fältet **Tokentyp** till **ID** och välj sedan **sid** anspråk. Markera **Lägg till**.
    1. Välj **Lägg till ytterligare anspråk**. Ange fältet **Tokentyp** till **Åtkomst** och välj sedan **sid** anspråk. Markera **Lägg till**.

1. I avsnittet **API-behörigheter** väljer du **Lägg till behörighet**.
1. På fliken **API:er min organisation använder** sök efter den Retail Server-app du skapade i avsnittet [Ställa in ett anpassat Retail Server-program i Azure AD](#set-up-a-custom-retail-server-app-in-azure-ad). Välj **Lägg till behörigheter**.
1. I avsnittet **Översikt** notera värdet i **App (klient) ID**.

### <a name="upgrade-an-existing-custom-cpos-azure-ad-app-created-before-commerce-version-10021"></a>Uppgradera en befintlig anpassad CPOS Azure AD-app som skapats före Commerce version 10.0.21

För att uppgradera en befintlig anpassad CPOS Azure AD-app som skapats före Commerce version 10.0.21, följ stegen nedan. 

1. Öppna din anpassade CPOS Azure AD-app i Azure-portalen.
1. Markera fliken **autentisering**.
1. Kopiera och spara den ursprungliga omdirigerade URI-filen från typen **webb** så att du kan använda den senare och ta sedan bort den.
1. Välj **Lägg till en plattform** och välj sedan **Ensidig app (SPA)**.
1. Lägg till den ursprungliga webb- och omdirigerings-URI som kopieras ovan till SPA-plattform.
1. I avsnittet **Tokenkonfiguration** om du vill lägga till två anspråk:
    1. Välj **Lägg till ytterligare anspråk**. Ange fältet **Tokentyp** till **ID** och välj sedan **sid** anspråk. Markera **Lägg till**.
    1. Välj **Lägg till ytterligare anspråk**. Ange fältet **Tokentyp** till **Åtkomst** och välj sedan **sid** anspråk. Markera **Lägg till**.

## <a name="update-the-cpos-configuration-file"></a>Uppdatera konfigurationsfilen för CPOS

Öppna filen CPOS config.json och gör följande uppdateringar i den.

1. Ersätt nyckelvärdet **AADClientId** med värdet **App (klient) ID** för den anpassade CPOS-appen som du skapade i avsnittet [Ange en anpassad CPOS app i Azure AD](#set-up-a-custom-cpos-app-in-azure-ad).
1. Ersätt nyckelvärdet **AADRetailServerResourceId** med värdet **App-ID URI** av anpassade Retail Server-app som du skapade i avsnittet [Konfigurera en anpassad Retail Server-app i Azure AD](#set-up-a-custom-retail-server-app-in-azure-ad).

CPOS använder båda parametrarna när den skickar förfrågningar om Azure AD för att hämta en säkerhetstoken.

## <a name="update-identity-providers-settings-in-commerce-headquarters"></a>Uppdatera inställningar för tillhandahållare av ID i Commerce headquarters

Därefter måste du uppdatera inställningar för tillhandahållare av ID i Commerce headquarters.

1. I Commerce headquarters, öppna sidan **Gemensamma Commerce-parametrar**.
1. På fliken **Identitetsutfärdare** i avsnittet **identitetsprovider** välj radeb där fältet **Skriv** anges till **Azure Active Directory** och fältet **utfärdare** pekar på din Azure AD klientorganisation. Den här inställningen anger att du ska arbeta med underordnade rutnät som innehåller data som är relaterade till den ID-leverantör som motsvarar din innehavare Azure AD.
1. I avsnittet **Beroende parter** välj **Lägg till** för att lägga till en rad.
1. Ange följande fält.

    - **ClientId** – Ange värdet **App (klient) ID** för den anpassade CPOS-app du skapade i avsnittet [Ställa in en anpassad CPOS-app i Azure AD](#set-up-a-custom-cpos-app-in-azure-ad).
    - **Typ** – Välj **Offentlig**.
    - **UserType** – Välj **Arbetare**.

1. Välj den rad som du lade till. Avsnittet **Serverresurs-ID** under avsnittet **beroende parter** visar de Retail Server-app-ID som du kan komma åt via appen du valde i rutnätet **beroende parter**.
1. I avsnittet **Serverresurs-ID** välj **Lägg till** för att lägga till en rad.
1. I fältet **Serverresurs-ID** ange värdet **App-ID URI** för den anpassade Retail Server-app som du skapade i avsnittet [Konfigurera en anpassad Retail Server-app i Azure AD](#set-up-a-custom-retail-server-app-in-azure-ad).

    > [!IMPORTANT]
    > Alla fält som nämns i föregående steg är skiftlägeskänsliga. Värdena du anger måste exakt matcha värdena som konfigureras i Azure AD administrationscenter.

1. Gå till **IT för butik och handel \> Distributionsschema** och kör jobbet **1110** (**Global konfiguration**).

Nu kan du aktivera CPOS-enheter med hjälp av ditt eget Azure AD program.

## <a name="additional-resources"></a>Ytterligare resurser

[Aktivering av kassaenehet (POS)](dev-itpro/retail-device-activation.md)

[Hantera aktiveringskonton och validera enheter](set-up-activation-accounts-validate-devices-hq.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
