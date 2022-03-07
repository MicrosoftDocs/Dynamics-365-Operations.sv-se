---
title: Distribuera en ny klientorganisation för näthandel
description: I det här avsnittet beskrivs hur du distribuerar en ny Dynamics 365 Commerce-näthandelssajt med hjälp av Microsoft Dynamics Lifecycle Services (LCS).
author: psimolin
ms.date: 07/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: b4b54e10cb4bd897b4c0706a13eeaf32f8892a05f7a09f3b27dbdd3dcdad1606
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6750724"
---
# <a name="deploy-a-new-e-commerce-tenant"></a>Distribuera en ny klientorganisation för näthandel

[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs hur du distribuerar en ny Dynamics 365 Commerce-näthandelssajt med hjälp av Microsoft Dynamics Lifecycle Services (LCS).

Microsoft Dynamics Lifecycle Services (LCS) är en molnbaserad samarbetsyta som partners och kunder kan använda för att hantera sina projekt och miljöer, visa den senaste informationen om Microsoft Dynamics produkter och funktioner samt skapa, spåra och bläddra i supporthändelser. Administreringsfunktionerna för näthandel integreras i LCS.

Mer information om LCS finns i [användarhandboken för Lifecycle Services](/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide).
    
## <a name="get-started"></a>Kom i gång

Innan du kan initiera näthandel måste du initiera ett projekt, en miljö och en Retail Cloud Scale Unit (RCSU). Om du vill utföra initieringen i LCS måste du ha behörighet till rollen som projektägare eller som en miljöhanterare. Topologierna för tillverkning och begränsat läge stöds.

Mer information om miljöer finns i [miljöplanering](/dynamics365/unified-operations/fin-and-ops/imp-lifecycle/environment-planning). Mer information om RCSU finns i [Initiera Retail Cloud Scale Unit](/dynamics365/unified-operations/dev-itpro/deployment/initialize-retail-channels).

## <a name="initialize-e-commerce"></a>Initiera näthandel

Använd den här proceduren för att initiera funktionen för näthandel i en befintlig miljö.

Innan du börjar måste du se till att du har följande obligatoriska information:

- RCSU som ska användas.
- Den Microsoft Azure Active Directory-säkerhetsgrupp som ska användas för systemadministratörer för näthandel.
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

När du har samlat in den information som krävs följer du stegen nedan för att initiera näthandel.

1. Logga in på [LCS](https://lcs.dynamics.com).
1. Öppna det projekt som innehåller den miljö där du vill initiera näthandel.
1. Välj miljön avsnittet **miljöer**.
1. Under **miljöfunktioner**, välj länken **Butik – hantera**.
1. På fliken **näthandel** välj **inställningar**. En dialogruta visas där du måste ange den information som krävs för etableringen.
1. Fyll i den information som krävs och gå sedan till nästa sida.
1. Fyll i önskad information på nästa sida och skicka sedan in formuläret. Du kommer tillbaka till fliken **näthandel** där du bör se att initieringen har startats.
1. Om du vill visa initieringsstatusen **uppdatera** du eller återgår till fliken **näthandel** senare.
    
När näthandel initieras från LCS etablerar systemet flera komponenter som krävs för näthandel och kopplar dem till miljön. När etableringen har slutförts, på fliken **näthandel** på sidan **Butikshantering** uppdateras för att avspegla etableringen. På sidan visas de senaste anpassningsdistributionerna och status för alla andra pågående distributioner. Den innehåller också länkar till webbplatsen för näthandel och Commerce-webbplatsbyggaren där webbplatser har skapats.

## <a name="access-commerce-site-builder"></a>Få åtkomst till Commerce-webbplatsbyggaren

För att få åtkomst till Commerce-webbplatsbyggaren går du till fliken **näthandel** på sidan **Butikshantering** i LCS och väljer länken **Hanteringsverktyg för näthandelssajt**. Landningssidan för webbplatsskaparen visar en vy på klientorganisationsnivå. Från den här sidan kan du:

- Ändra inställningarna för klientorganisationsnivå.
- Navigera till en webbplats som du har skapat och ha behörighet att visa den. 
- Åtkomst till granskningsfunktioner, t.ex. av redigering och rapportering.
- Skapa en ny anläggning. Mer information om hur du skapar en ny webbplats finns i [Skapa en näthandelssajt](create-ecommerce-site.md). 

## <a name="additional-resources"></a>Ytterligare resurser

[Konfigurera ditt domännamn](configure-your-domain-name.md)

[Skapa en näthandelssajt](create-ecommerce-site.md)

[Associera en Dynamics 365 Commerce-webbplats med en onlinekanal](associate-site-online-store.md)

[Hantera robots.txt-filer](manage-robots-txt-files.md)

[Överför URL-omdirigeringar i bulk](upload-bulk-redirects.md)

[Ställa in en B2C-innehavare i Commerce](set-up-B2C-tenant.md)

[Ställa in anpassade sidor för användarinloggningar](custom-pages-user-logins.md)

[Konfigurera flera B2C-innehavare i en Commerce-miljö](configure-multi-B2C-tenants.md)

[Lägga till stöd för ett innehållsleveransnätverk (CDN)](add-cdn-support.md)

[Aktivera platsbaserad butiksdetektering](enable-store-detection.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]