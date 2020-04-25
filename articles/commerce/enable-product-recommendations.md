---
title: Aktivera produktrekommendationer
description: I det här avsnittet beskrivs hur du gör produktrekommendationer som baseras på artificiell intelligens (AI-ML) tillgängligt för Microsoft Dynamics 365 Commerce-kunder.
author: bebeale
manager: AnnBe
ms.date: 04/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: ''
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: d38d7b0e98d84e23d7a51c5d8ee65df4a3b9e4a7
ms.sourcegitcommit: dbff1c6bb371a443a0cd2a310f5a48d5c21b08ca
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2020
ms.locfileid: "3259804"
---
# <a name="enable-product-recommendations"></a>Aktivera produktrekommendationer

[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs hur du gör produktrekommendationer som baseras på artificiell intelligens (AI-ML) tillgängligt för Microsoft Dynamics 365 Commerce-kunder. Mer information om produktrekommendationslistor finns i [produktrekommendationer - översikt](product-recommendations.md).

## <a name="recommendations-pre-check"></a>Förkontroll av rekommendationer

Innan du aktiverar produkten bör du notera att produktrekommendationer endast stöds för handelskunder som har migrerat deras lagring till att använda Azure Data Lake Storage (ADLS). 

Följande konfigurationer måste aktiveras på baksidan innan rekommendationer aktiveras:

1. Kontrollera att ADLS har köpts och kontrollerats i miljön. För mer information, se [Kontrollera att ADLS har köpts och kontrollerats i miljön](enable-ADLS-environment.md).
2. Kontrollera att uppdatering av enhetslagring är automatiserat. Mer information finns i [kontrollera att uppdatering av enhetsarkivet har automatiserats](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md).
3. Bekräfta att Azure AD identitetskonfigurationen innehåller en post för rekommendationer. Mer information om hur du utför den här åtgärden finns nedan.

Kontrollera också att RetailSale-mätningar har aktiverats. Mer information om den här inställningsprocessen finns i [arbeta med mått](https://docs.microsoft.com/dynamics365/ai/customer-insights/pm-measures).

## <a name="azure-ad-identity-configuration"></a>Azure AD identitetskonfiguration

Det här steget krävs för alla kunder som kör infrastruktur som en tjänst (IaaS) konfiguration. För kunder som kör on Service Fabric (SF) ska det här steget vara automatiskt och vi rekommenderar att du bekräftar att inställningen är konfigurerad som förväntat.

### <a name="setup"></a>Konfigurera

1. Från backoffice sök efter sidan **Azure Active Directory-program**.
2. Kontrollera om det finns en post för "RecommendationSystemApplication-1".

Om posten inte finns lägger du till en ny post med följande information:

- **Klient-ID** - d37b07e8-dd1c-4514-835d-8b918e6f9727
- **Namn** - RecommendationSystemApplication-1
- **Användar-ID** - RetailServiceAccount

Spara och stäng formuläret 

## <a name="turn-on-recommendations"></a>Aktivera rekommendationer

Så här aktiverar du produktrekommendationer.

1. Gå till **Butik och handel &gt; Produktrekommendationer &gt; Rekommendationsparametrar**.
1. I listan över delade parametrar, välj **Rekommendationslistor**.
1. Ge alternativet **Aktivera rekommendationer** värdet **Ja**.

![Aktivera rekommendationer](./media/enablepersonalization.png)

> [!NOTE]
> I den här proceduren inleds processen med att generera listor över produktrekommendationer. Det kan ta flera timmar innan listorna är tillgängliga och kan visas i kassan (POS) eller i Dynamics 365 Commerce.

## <a name="configure-recommendation-list-parameters"></a>Konfigurera parametrar för rekommendationslista

Som standard innehåller listan AI-ML-baserad produktrekommendation förslagna värden. Du kan ändra de föreslagna standardvärdena så att de passar affärsflödet. Om du vill veta mer om hur du ändrar standardparametrarna kan du gå till [Hantera AI-ML-baserade produktrekommendationsresultat](modify-product-recommendation-results.md).

## <a name="show-recommendations-on-pos-devices"></a>Visa rekommendationer på kassaenheter

När du har aktiverat rekommendationer i backoffice för Handel måste rekommendationspanelen läggas till i kassans kontrollskärm via layoutverktyget. Mer information om den här processen finns i [Lägga till en rekommendationskontroll till transaktionsskärmen på kassaenheter](add-recommendations-control-pos-screen.md). 

## <a name="enable-personalized-recommendations"></a>Aktivera anpassade rekommendationer

I Dynamics 365 Commerce kan återförsäljare göra anpassade produktrekommendationer (även kallade anpassningar) tillgängliga. På detta sätt kan personliga rekommendationer införlivas i kundupplevelsen online och i kassan. När anpassningsfunktionen är aktiverad kan systemet associera en användares inköps- och produktinformation för att skapa enskilda produktrekommendationer.

Mer information om anpassade rekommendationer finns i [aktivera anpassade rekommendationer](personalized-recommendations.md).

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt av produktrekommendationer](product-recommendations.md)

[Aktivera ADLS i en Dynamics 365 Commerce-miljö](enable-adls-environment.md)

[Aktivera anpassade rekommendationer](personalized-recommendations.md)

[Avanmäl anpassade rekommendationer](personalization-gdpr.md)

[Lägg till produktrekommendationer i kassan](product.md)

[Lägg till rekommendationer på transaktionsskärmen](add-recommendations-control-pos-screen.md)

[Justera rekommendationsresultat från AI-ML](modify-product-recommendation-results.md)

[Skapa granskade rekommendationer manuellt](create-editorial-recommendation-lists.md)

[Skapa rekommendationer med demodata](product-recommendations-demo-data.md)

[Vanliga frågor om produktrekommendationer](faq-recommendations.md)

