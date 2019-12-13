---
title: Aktivera produktrekommendationer
description: I det här avsnittet beskrivs hur du gör produktrekommendationer som baseras på artificiell intelligens (AI-ML) tillgängligt för Microsoft Dynamics 365 Commerce-kunder.
author: bebeale
manager: AnnBe
ms.date: 10/1/2019
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
ms.openlocfilehash: ecda571a356c6968196d09cc19923105cf4544ab
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770149"
---
# <a name="enable-product-recommendations"></a>Aktivera produktrekommendationer

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs hur du gör produktrekommendationer som baseras på artificiell intelligens (AI-ML) tillgängligt för Microsoft Dynamics 365 Commerce-kunder. Mer information om produktrekommendationslistor finns i [produktrekommendationer - översikt](product-recommendations.md).

## <a name="recommendations-pre-check"></a>Förkontroll av rekommendationer
Innan du aktiverar produkten bör du notera att produktrekommendationer endast stöds för F&O-kunder som stöder version 10.0.6 och har migrerat deras lagring till att använda BDL. 

Kontrollera också att RetailSale-mätningar har aktiverats. Du får mer information om den här inställningsprocessen [här.](https://docs.microsoft.com/en-us/dynamics365/ai/customer-insights/pm-measures)


## <a name="turn-on-recommendations"></a>Aktivera rekommendationer

Så här aktiverar du produktrekommendationer.

1. Gå till **Butik** &gt; **Produktrekommendationer** &gt; **Rekommendationsparametrar**.
1. I listan över delade butiksparametrar, välj **Rekommendationslistor**.
1. Ge alternativet **Aktivera rekommendationer** värdet **Ja**.

![aktivera produktrekommendationer](./media/enableproductrecommendations.png)

> [!NOTE]
> I den här proceduren inleds processen med att generera listor över produktrekommendationer. Det kan krävas upp till flera timmar innan listorna är tillgängliga och kan visas i kassan (POS) eller i Dynamics 365 for Commerce.

## <a name="configure-recommendation-list-parameters"></a>Konfigurera parametrar för rekommendationslista
Som standard innehåller listan AI-ML-baserad produktrekommendation förslagna värden. Du kan ändra de föreslagna standardvärdena så att de passar affärsflödet. Om du vill veta mer om hur du ändrar standardparametrarna kan du gå till [Hantera AI-ML-baserade produktrekommendationsresultat](modify-product-recommendation-results.md).

## <a name="show-recommendations-on-pos-devices"></a>Visa rekommendationer på kassaenheter
När du har aktiverat rekommendationer i backoffice måste rekommendationspanelen läggas till i kassans kontrollskärm via layoutverktyget. Du får mer information om den här processen [här.](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/add-recommendations-control-pos-screen)


## <a name="additional-resources"></a>Ytterligare resurser

[Översikt av produktrekommendationer](product-recommendations.md)

[Lägg till produktrekommendationer på sidor](add-reco-list-to-page.md)

[Lägg till rekommendationspanelen i kassaenheter](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/add-recommendations-control-pos-screen)


