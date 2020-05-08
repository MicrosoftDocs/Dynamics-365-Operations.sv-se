---
title: Distribuera en ny klientorganisation för e-handel
description: I det här avsnittet beskrivs hur du distribuerar en ny näthandelsinnehavare med hjälp av Microsoft Dynamics Lifecycle Services (LCS).
author: psimolin
manager: annbe
ms.date: 03/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 3febd3ca36f4d517033e910c4087ad3a6ffff35a
ms.sourcegitcommit: 7a1d01122790b904e2d96a7ea9f1d003392358a6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/17/2020
ms.locfileid: "3269945"
---
# <a name="deploy-a-new-e-commerce-tenant"></a>Distribuera en ny klientorganisation för e-handel


[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs hur du distribuerar en ny näthandelsplats med hjälp av Microsoft Dynamics Lifecycle Services (LCS).

## <a name="overview"></a>Översikt

Microsoft Dynamics Lifecycle Services (LCS) är en molnbaserad samarbetsyta som partners och kunder kan använda för att hantera sina projekt och miljöer, visa den senaste informationen om Microsoft Dynamics produkter och funktioner samt skapa, spåra och bläddra i supporthändelser. Funktionerna för hantering av e-handel integreras i LCS.

Mer information om LCS finns i [användarhandboken för Lifecycle Services](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide).
    
## <a name="get-started"></a>Kom igång

Innan du kan initiera e-handel måste du initiera ett projekt, en miljö och en Retail Cloud Scale Unit (RCSU). Om du vill utföra initieringen i LCS måste du ha behörighet till rollen som projektägare eller som en miljöhanterare. Topologierna för tillverkning och begränsat läge stöds.

Mer information om miljöer finns i [miljöplanering](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/imp-lifecycle/environment-planning). Mer information om RCSU finns i [Initiera Retail Cloud Scale Unit](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/deployment/initialize-retail-channels).

## <a name="initialize-e-commerce"></a>Initiera e-handelsplattform

Använd den här proceduren för att initiera funktionen för e-handel i en befintlig miljö.

Innan du börjar måste du se till att du har följande obligatoriska information:

- RCSU som ska användas.
- Den Microsoft Azure Active Directory-säkerhetsgrupp som ska användas för e-handelssystemadministratörer.
- Den Microsoft Azure Active Directory-säkerhetsgrupp som ska användas för moderatorer för omdömen och recensioner.
- Domänerna som ska associeras med miljön.

Dessutom kan du samla in följande valfria information:

- Azure AD information om B2C (business-to-consumer):

    - Innehavarens namn.
    - Klient-ID.
    - Anpassad domän för inloggning.
    - Svars-URL.
    - Policy-ID för SignUp SignIn.
    - Policy-ID för återställning av lösenord
    - Redigera ID för profilpolicy.

> [!NOTE]
> Denna information kan läggas till senare, genom en tjänstbegäran.

När du har samlat in den information som krävs följer du stegen nedan för att initiera e-handel.

1. Logga in på [LCS](https://lcs.dynamics.com).
1. Öppna det projekt som innehåller den miljö där du vill initiera e-handel.
1. Välj miljön avsnittet **miljöer**.
1. Under **miljöfunktioner**, välj länken **Butik – hantera**.
1. På fliken **e-handel** välj **inställningar**. En dialogruta visas där du måste ange den information som krävs för etableringen.
1. Fyll i den information som krävs och gå sedan till nästa sida.
1. Fyll i önskad information på nästa sida och skicka sedan in formuläret. Du kommer tillbaka till fliken **e-handel** där du bör se att initieringen har startats.
1. Om du vill visa initieringsstatusen **uppdatera** du eller återgår till fliken **e-handel** senare.
    
När e-handel initieras från LCS, etablerar systemet flera komponenter som krävs för e-handel och kopplar dem till miljön. När etableringen har slutförts, på fliken **e-handel** på sidan **Butikshantering** uppdateras för att avspegla etableringen. På sidan visas de senaste anpassningsdistributionerna och status för alla andra pågående distributioner. Den innehåller också länkar till webbplatsen för e-handel och webbplatsskaparen för e-handel där webbplatser har redigerats.

## <a name="access-site-builder"></a>Få åtkomst till webbplatsskaparen

Du öppnar webbplatsskaparen genom att gå till fliken **e-handel** på sidan **butikshantering** i LCS och väljer länken **Hanteringsverktyg för näthandelsplats**. Landningssidan för webbplatsskaparen visar en vy på klientorganisationsnivå. Från den här sidan kan du:

- Ändra inställningarna för klientorganisationsnivå.
- Navigera till en webbplats som du har skapat och ha behörighet att visa den. 
- Åtkomst till granskningsfunktioner, t.ex. av redigering och rapportering.
- Skapa en ny anläggning. Mer information om hur du skapar en ny webbplats finns i [Skapa en e-handelsplats](create-ecommerce-site.md). 

## <a name="additional-resources"></a>Ytterligare resurser

[Konfigurera ditt domännamn](configure-your-domain-name.md)

[Skapa en e-handelsplats](create-ecommerce-site.md)

[Ställ in en kanal för onlinebutik](online-stores.md)

[Associera en online-webbplats med en kanal](associate-site-online-store.md)

[Hantera robots.txt-filer](manage-robots-txt-files.md)

[Överföring av URL-omdirigeringar i bulk](upload-bulk-redirects.md)

[Ställa in en B2C-innehavare i Commerce](set-up-B2C-tenant.md)

[Ställa in anpassade sidor för användarinloggningar](custom-pages-user-logins.md)

[Konfigurera flera B2C-innehavare i en Commerce-miljö](configure-multi-B2C-tenants.md)

[Lägga till stöd för ett innehållsleveransnätverk (CDN)](add-cdn-support.md)

[Aktivera platsbaserad butiksdetektering](enable-store-detection.md)
