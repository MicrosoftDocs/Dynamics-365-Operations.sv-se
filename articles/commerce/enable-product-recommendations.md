---
title: Aktivera produktrekommendationer
description: I det här avsnittet beskrivs hur du gör produktrekommendationer som baseras på artificiell intelligens (AI-ML) tillgängligt för Microsoft Dynamics 365 Commerce-kunder.
author: bebeale
manager: AnnBe
ms.date: 03/19/2020
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
ms.openlocfilehash: d8a579be5df3c5e7718a6fb4720341f3bd01a64c
ms.sourcegitcommit: de5af1912201dd70aa85fdcad0b184c42405802e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/21/2020
ms.locfileid: "3154423"
---
# <a name="enable-product-recommendations"></a>Aktivera produktrekommendationer

[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs hur du gör produktrekommendationer som baseras på artificiell intelligens (AI-ML) tillgängligt för Microsoft Dynamics 365 Commerce-kunder. Mer information om produktrekommendationslistor finns i [produktrekommendationer - översikt](product-recommendations.md).

## <a name="recommendations-pre-check"></a>Förkontroll av rekommendationer

Innan du aktiverar produkten bör du notera att produktrekommendationer endast stöds för handelskunder som har migrerat deras lagring till att använda Azure Data Lake Storage (ADLS). 

Information om hur du aktiverar ADLS finns i [Så här aktiverar du ADLS i en Dynamics 365-miljö](enable-ADLS-environment.md).

Kontrollera också att RetailSale-mätningar har aktiverats. Du får mer information om den här inställningsprocessen [här.](https://docs.microsoft.com/dynamics365/ai/customer-insights/pm-measures)


## <a name="turn-on-recommendations"></a>Aktivera rekommendationer

Så här aktiverar du produktrekommendationer.

1. Gå till **Butik och handel &gt; Produktrekommendationer &gt; Rekommendationsparametrar**.
1. I listan över delade parametrar, välj **Rekommendationslistor**.
1. Ge alternativet **Aktivera rekommendationer** värdet **Ja**.

![aktivera produktrekommendationer](./media/enableproductrecommendations.png)

> [!NOTE]
> I den här proceduren inleds processen med att generera listor över produktrekommendationer. Det kan krävas upp till flera timmar innan listorna är tillgängliga och kan visas i kassan (POS) eller i Dynamics 365 Commerce.

## <a name="configure-recommendation-list-parameters"></a>Konfigurera parametrar för rekommendationslista

Som standard innehåller listan AI-ML-baserad produktrekommendation förslagna värden. Du kan ändra de föreslagna standardvärdena så att de passar affärsflödet. Om du vill veta mer om hur du ändrar standardparametrarna kan du gå till [Hantera AI-ML-baserade produktrekommendationsresultat](modify-product-recommendation-results.md).

## <a name="show-recommendations-on-pos-devices"></a>Visa rekommendationer på kassaenheter

När du har aktiverat rekommendationer i backoffice för Handel måste rekommendationspanelen läggas till i kassans kontrollskärm via layoutverktyget. Mer information om den här processen finns i [Lägga till en rekommendationskontroll till transaktionsskärmen på kassaenheter](add-recommendations-control-pos-screen.md). 

## <a name="enable-personalized-recommendations"></a>Aktivera anpassade rekommendationer

Mer information om hur du tar emot anpassade rekommendationer finns i [aktivera anpassade rekommendationer](personalized-recommendations.md).

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

