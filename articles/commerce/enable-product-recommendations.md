---
title: Aktivera produktrekommendationer
description: I denna artikel beskrivs hur du gör produktrekommendationer som baseras på artificiell intelligens/maskininlärning (AI-ML) tillgänglig för Microsoft Dynamics 365 Commerce-kunder.
author: bebeale
ms.date: 09/08/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: fc1b43fa70e6652d38b1141e2d93cf323f70a756
ms.sourcegitcommit: f88273627ba105ede27f28fe67ccec2d7f78261c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/09/2022
ms.locfileid: "9460032"
---
# <a name="enable-product-recommendations"></a>Aktivera produktrekommendationer

[!include [banner](includes/banner.md)]

I denna artikel beskrivs hur du gör produktrekommendationer som baseras på artificiell intelligens/maskininlärning (AI-ML) tillgänglig för Microsoft Dynamics 365 Commerce-kunder. Mer information om produktrekommendationslistor finns i [produktrekommendationer – översikt](product-recommendations.md).

## <a name="recommendations-pre-check"></a>Förkontroll av rekommendationer

1. Se till att du har en giltig licens för Dynamics 365 Commerce-rekommendationer.
1. Se till att Enhetsarkivet är anslutet till ett kundägt Azure Data Lake Storage Gen2-konto. För mer information, se [Kontrollera att Azure Data Lake Storage har köpts och kontrollerats i miljön](enable-ADLS-environment.md).
1. Bekräfta att Azure AD identitetskonfigurationen innehåller en post för rekommendationer. Mer information om hur du utför den här åtgärden finns nedan.
1. Kontrollera att enhetsarkivet dagliga uppdatering till Azure Data Lake Storage Gen2 har tidsplanerats. Mer information finns i [kontrollera att uppdatering av enhetsarkivet har automatiserats](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md).
1. Aktivera RetailSale-mått för Enhetsarkiv. Mer information om den här inställningsprocessen finns i [Arbeta med mått](/dynamics365/ai/customer-insights/pm-measures).
1. Kontrollera att din miljö har konfigurerat serverings- och arbetsmiljöområdena i de aktuella regionerna som stöds, på följande sätt:

    - **Regioner som stöds:** EU/US/CA/AU.
    - **Serveringsregioner som stöds:** US/CA/AU. Om portionsområdet inte matchar något av de befintliga regioner som stöds, väljer rekommendationer från den region som stöds närmast.

När stegen ovan har slutförts är du redo att aktivera rekommendationer.

> [!NOTE]
> Det finns ett känt problem där rekommendationer inte visas när följande steg har slutförts. Det här problemet orsakas av dataflödesproblem i miljön. Om din miljö inte visar rekommendationsresultat kan du konfigurera alternativa data för rekommendationer genom att följa stegen i [Ställa in ett alternativt dataflöde för rekommendationer](set-up-alternate-data-flow.md). Du måste ha administratörsbehörighet från Azure för att kunna utföra de här stegen. Om du behöver hjälp kontaktar du din FastTrack-representant.

## <a name="azure-ad-identity-configuration"></a>Azure AD identitetskonfiguration

Det här steget krävs bara för kunder som kör infrastruktur som en tjänst (IaaS) konfiguration. Azure AD-identitetskonfiguration är automatisk för kunder som kör på Azure Service Fabric, men du rekommenderas att kontrollera att inställningen är konfigurerad som förväntat.

### <a name="setup"></a>Ställ in

1. I Commerce headquarters, sök efter sidan **Azure Active Directory-program**.
1. Kontrollera att det finns en post för **RecommendationSystemApplication-1**. Om det inte finns någon post skapar du en med följande information:

    - **Klient-ID**: d37b07e8-dd1c-4514-835d-8b918e6f9727
    - **Namn**: RecommendationSystemApplication-1
    - **Användar-ID**: RetailServiceAccount

1. Spara och stäng formuläret 

## <a name="turn-on-recommendations"></a>Aktivera rekommendationer

Så här aktiverar du produktrekommendationer.

1. Sök efter **funktionshantering** i Commerce Headquarters.
1. Välj **alla** om du vill visa en lista över tillgängliga funktioner. 
1. Ange **rekommendationer** i sökrutan.
1. Välj funktionen **produktrekommendationer**.
1. I egenskapsfönstret **produktrekommendationer** välj **Aktivera nu**.

![Aktivera rekommendationer.](./media/FeatureManagement_Recommendations.PNG)

> [!NOTE]
> - Med proceduren ovan inleds processen med att generera listor över produktrekommendationer. Det kan ta flera timmar innan listorna är tillgängliga och kan visas i POS eller i Dynamics 365 Commerce.
> - Denna konfiguration aktiverar inte alla rekommendationsfunktioner. Avancerade funktioner som anpassade rekommendationer, "köp liknande produkter" och "köp liknande beskrivning" kontrolleras av dedikerade funktionshanteringsposter. Mer information om hur du aktiverar dessa funktioner i Commerce Headquarters finns i [Aktivera anpassade rekommendationer](personalized-recommendations.md), [Aktivera rekommendationer för "köp liknande produkter"](shop-similar-looks.md) och [Aktivera rekommendationer för "köp liknande beskrivning"](shop-similar-description.md).

## <a name="configure-recommendation-list-parameters"></a>Konfigurera parametrar för rekommendationslista

Som standard innehåller listan AI-ML-baserad produktrekommendation förslagna värden. Du kan ändra de föreslagna standardvärdena så att de passar affärsflödet. Om du vill veta mer om hur du ändrar standardparametrarna kan du gå till [Hantera AI-ML-baserade produktrekommendationsresultat](modify-product-recommendation-results.md).

## <a name="include-recommendations-in-e-commerce-experiences"></a>Ta med rekommendationer i näthandelsupplevelser

När du har aktiverat rekommendationer i Commerce Headquarters är de Commerce-moduler som används för att visa rekommendationer för näthandelsupplevelser klara att konfigureras. Mer information finns i [Produktsamlingsmoduler](product-collection-module-overview.md).

## <a name="show-recommendations-on-pos-devices"></a>Visa rekommendationer på kassaenheter

När du har aktiverat rekommendationer i Commerce headquarters måste rekommendationspanelen läggas till i kassans kontrollskärm via layoutverktyget. Mer information om den här processen finns i [Lägga till en rekommendationskontroll till transaktionsskärmen på kassaenheter](add-recommendations-control-pos-screen.md). 

## <a name="enable-personalized-recommendations"></a>Aktivera anpassade rekommendationer

I Dynamics 365 Commerce kan återförsäljare göra anpassade produktrekommendationer (även kallade anpassningar) tillgängliga. På detta sätt kan personliga rekommendationer införlivas i kundupplevelsen online och i POS. När anpassningsfunktionen är aktiverad kan systemet associera en användares inköps- och produktinformation för att skapa enskilda produktrekommendationer.

Mer information om anpassade rekommendationer finns i [aktivera anpassade rekommendationer](personalized-recommendations.md).

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt av produktrekommendationer](product-recommendations.md)

[Aktivera Azure Data Lake Storage i en Dynamics 365 Commerce-miljö](enable-adls-environment.md)

[Ställa in alternativt dataflöde för rekommendationer](set-up-alternate-data-flow.md)

[Aktivera anpassade rekommendationer](personalized-recommendations.md)

[Aktivera rekommendationer för "köp liknande produkter"](shop-similar-looks.md)

[Avanmäl anpassade rekommendationer](personalization-gdpr.md)

[Lägg till produktrekommendationer i POS](product.md)

[Lägg till rekommendationer på transaktionsskärmen](add-recommendations-control-pos-screen.md)

[Justera rekommendationsresultat från AI-ML](modify-product-recommendation-results.md)

[Skapa granskade rekommendationer manuellt](create-editorial-recommendation-lists.md)

[Skapa rekommendationer med demodata](product-recommendations-demo-data.md)

[Vanliga frågor om produktrekommendationer](faq-recommendations.md)




[!INCLUDE[footer-include](../includes/footer-banner.md)]
