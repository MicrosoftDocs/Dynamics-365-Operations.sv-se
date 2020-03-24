---
title: Aktivera produktrekommendationer
description: I det här avsnittet beskrivs hur du gör produktrekommendationer som baseras på artificiell intelligens (AI-ML) tillgängligt för Microsoft Dynamics 365 Commerce-kunder.
author: bebeale
manager: AnnBe
ms.date: 03/12/2020
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
ms.openlocfilehash: 879fccb063ca0b74e0f022a9edf6a15f7d1311ae
ms.sourcegitcommit: 1e7e7c4bc197b0a42e4d53d2a54600a2fb125b69
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/13/2020
ms.locfileid: "3127892"
---
# <a name="enable-product-recommendations"></a><span data-ttu-id="80670-103">Aktivera produktrekommendationer</span><span class="sxs-lookup"><span data-stu-id="80670-103">Enable product recommendations</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="80670-104">I det här avsnittet beskrivs hur du gör produktrekommendationer som baseras på artificiell intelligens (AI-ML) tillgängligt för Microsoft Dynamics 365 Commerce-kunder.</span><span class="sxs-lookup"><span data-stu-id="80670-104">This topic explains how to make product recommendations that are based on artificial intelligence-machine learning (AI-ML) available for Microsoft Dynamics 365 Commerce customers.</span></span> <span data-ttu-id="80670-105">Mer information om produktrekommendationslistor finns i [produktrekommendationer - översikt](product-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="80670-105">For more information about product recommendation lists, see [Product recommendations overview](product-recommendations.md).</span></span>

## <a name="recommendations-pre-check"></a><span data-ttu-id="80670-106">Förkontroll av rekommendationer</span><span class="sxs-lookup"><span data-stu-id="80670-106">Recommendations pre-check</span></span>

<span data-ttu-id="80670-107">Innan du aktiverar produkten bör du notera att produktrekommendationer endast stöds för handelskunder som har migrerat deras lagring till att använda Azure Data Lake Storage (ADLS).</span><span class="sxs-lookup"><span data-stu-id="80670-107">Before enabling, please note that product recommendations are only supported for Commerce customers who have migrated their storage to using Azure Data Lake Storage (ADLS).</span></span> 

<span data-ttu-id="80670-108">Information om hur du aktiverar ADLS finns i [Så här aktiverar du ADLS i en Dynamics 365-miljö](enable-ADLS-environment.md).</span><span class="sxs-lookup"><span data-stu-id="80670-108">For steps on enabling ADLS, see [How to enable ADLS in a Dynamics 365 environment](enable-ADLS-environment.md).</span></span>

<span data-ttu-id="80670-109">Kontrollera också att RetailSale-mätningar har aktiverats.</span><span class="sxs-lookup"><span data-stu-id="80670-109">Additionally, ensure that RetailSale measurements have been enabled.</span></span> <span data-ttu-id="80670-110">Du får mer information om den här inställningsprocessen [här.](https://docs.microsoft.com/dynamics365/ai/customer-insights/pm-measures)</span><span class="sxs-lookup"><span data-stu-id="80670-110">To learn more about this set up process, go [here.](https://docs.microsoft.com/dynamics365/ai/customer-insights/pm-measures)</span></span>


## <a name="turn-on-recommendations"></a><span data-ttu-id="80670-111">Aktivera rekommendationer</span><span class="sxs-lookup"><span data-stu-id="80670-111">Turn on recommendations</span></span>

<span data-ttu-id="80670-112">Så här aktiverar du produktrekommendationer.</span><span class="sxs-lookup"><span data-stu-id="80670-112">To turn on product recommendations, follow these steps.</span></span>

1. <span data-ttu-id="80670-113">Gå till **Butik och handel &gt; Produktrekommendationer &gt; Rekommendationsparametrar**.</span><span class="sxs-lookup"><span data-stu-id="80670-113">Go to **Retail and Commerce &gt; Product recommendations &gt; Recommendation parameters**.</span></span>
1. <span data-ttu-id="80670-114">I listan över delade parametrar, välj **Rekommendationslistor**.</span><span class="sxs-lookup"><span data-stu-id="80670-114">In the list of shared parameters, select **Recommendation Lists**.</span></span>
1. <span data-ttu-id="80670-115">Ge alternativet **Aktivera rekommendationer** värdet **Ja**.</span><span class="sxs-lookup"><span data-stu-id="80670-115">Set the **Enable recommendations** option to **Yes**.</span></span>

![aktivera produktrekommendationer](./media/enableproductrecommendations.png)

> [!NOTE]
> <span data-ttu-id="80670-117">I den här proceduren inleds processen med att generera listor över produktrekommendationer.</span><span class="sxs-lookup"><span data-stu-id="80670-117">This procedure starts the process of generating product recommendation lists.</span></span> <span data-ttu-id="80670-118">Det kan krävas upp till flera timmar innan listorna är tillgängliga och kan visas i kassan (POS) eller i Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="80670-118">Up to several hours might be required before the lists are available and can be seen at the point of sale (POS) or in Dynamics 365 Commerce.</span></span>

## <a name="configure-recommendation-list-parameters"></a><span data-ttu-id="80670-119">Konfigurera parametrar för rekommendationslista</span><span class="sxs-lookup"><span data-stu-id="80670-119">Configure recommendation list parameters</span></span>

<span data-ttu-id="80670-120">Som standard innehåller listan AI-ML-baserad produktrekommendation förslagna värden.</span><span class="sxs-lookup"><span data-stu-id="80670-120">By default, the AI-ML-based product recommendation list provides suggested values.</span></span> <span data-ttu-id="80670-121">Du kan ändra de föreslagna standardvärdena så att de passar affärsflödet.</span><span class="sxs-lookup"><span data-stu-id="80670-121">You can change the default suggested values to suit the flow of your business.</span></span> <span data-ttu-id="80670-122">Om du vill veta mer om hur du ändrar standardparametrarna kan du gå till [Hantera AI-ML-baserade produktrekommendationsresultat](modify-product-recommendation-results.md).</span><span class="sxs-lookup"><span data-stu-id="80670-122">To learn more about how to change the default parameters, go to [Manage AI-ML-based product recommendation results](modify-product-recommendation-results.md).</span></span>

## <a name="show-recommendations-on-pos-devices"></a><span data-ttu-id="80670-123">Visa rekommendationer på kassaenheter</span><span class="sxs-lookup"><span data-stu-id="80670-123">Show recommendations on POS devices</span></span>

<span data-ttu-id="80670-124">När du har aktiverat rekommendationer i backoffice för Handel måste rekommendationspanelen läggas till i kassans kontrollskärm via layoutverktyget.</span><span class="sxs-lookup"><span data-stu-id="80670-124">After enabling recommendations in Commerce back office, the recommendations panel must be added to the control POS screen using the layout tool.</span></span> <span data-ttu-id="80670-125">Mer information om den här processen finns i [Lägga till en rekommendationskontroll till transaktionsskärmen på kassaenheter](add-recommendations-control-pos-screen.md).</span><span class="sxs-lookup"><span data-stu-id="80670-125">To learn about this process, see [Add a recommendations control to the transaction screen on POS devices](add-recommendations-control-pos-screen.md).</span></span> 

## <a name="enable-personalized-recommendations"></a><span data-ttu-id="80670-126">Aktivera anpassade rekommendationer</span><span class="sxs-lookup"><span data-stu-id="80670-126">Enable personalized recommendations</span></span>

<span data-ttu-id="80670-127">Mer information om hur du tar emot anpassade rekommendationer finns i [aktivera anpassade rekommendationer](personalized-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="80670-127">To learn more about how to receive personalized recommendations, see [Enable personalized recommendations](personalized-recommendations.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="80670-128">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="80670-128">Additional resources</span></span>

[<span data-ttu-id="80670-129">Översikt av produktrekommendationer</span><span class="sxs-lookup"><span data-stu-id="80670-129">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="80670-130">Aktivera ADLS i en Dynamics 365 Commerce-miljö</span><span class="sxs-lookup"><span data-stu-id="80670-130">Enable ADLS in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="80670-131">Aktivera anpassade rekommendationer</span><span class="sxs-lookup"><span data-stu-id="80670-131">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="80670-132">Avanmäl anpassade rekommendationer</span><span class="sxs-lookup"><span data-stu-id="80670-132">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="80670-133">Lägga till rekommendationslistor på en näthandelsplats</span><span class="sxs-lookup"><span data-stu-id="80670-133">Add recommendation lists to an e-Commerce site</span></span>](add-reco-list-to-page.md)

[<span data-ttu-id="80670-134">Lägg till produktrekommendationer i kassan</span><span class="sxs-lookup"><span data-stu-id="80670-134">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="80670-135">Lägg till rekommendationer på transaktionsskärmen</span><span class="sxs-lookup"><span data-stu-id="80670-135">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="80670-136">Justera rekommendationsresultat från AI-ML</span><span class="sxs-lookup"><span data-stu-id="80670-136">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="80670-137">Skapa granskade rekommendationer manuellt</span><span class="sxs-lookup"><span data-stu-id="80670-137">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="80670-138">Skapa rekommendationer med demodata</span><span class="sxs-lookup"><span data-stu-id="80670-138">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="80670-139">Vanliga frågor om produktrekommendationer</span><span class="sxs-lookup"><span data-stu-id="80670-139">Product recommendations FAQ</span></span>](faq-recommendations.md)

