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
ms.openlocfilehash: 2d3f1bc2526eeacb4bd6338a0679eadd95a75989
ms.sourcegitcommit: b5ecde955a69f577de46e7db10e89caaedeb2b49
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/04/2020
ms.locfileid: "3024966"
---
# <a name="enable-product-recommendations"></a><span data-ttu-id="aaf5f-103">Aktivera produktrekommendationer</span><span class="sxs-lookup"><span data-stu-id="aaf5f-103">Enable product recommendations</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="aaf5f-104">I det här avsnittet beskrivs hur du gör produktrekommendationer som baseras på artificiell intelligens (AI-ML) tillgängligt för Microsoft Dynamics 365 Commerce-kunder.</span><span class="sxs-lookup"><span data-stu-id="aaf5f-104">This topic explains how to make product recommendations that are based on artificial intelligence-machine learning (AI-ML) available for Microsoft Dynamics 365 Commerce customers.</span></span> <span data-ttu-id="aaf5f-105">Mer information om produktrekommendationslistor finns i [produktrekommendationer - översikt](product-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="aaf5f-105">For more information about product recommendation lists, see [Product recommendations overview](product-recommendations.md).</span></span>

## <a name="recommendations-pre-check"></a><span data-ttu-id="aaf5f-106">Förkontroll av rekommendationer</span><span class="sxs-lookup"><span data-stu-id="aaf5f-106">Recommendations pre-check</span></span>

<span data-ttu-id="aaf5f-107">Innan du aktiverar produkten bör du notera att produktrekommendationer endast stöds för handelskunder som har migrerat deras lagring till att använda Azure Data Lake Storage (ADLS).</span><span class="sxs-lookup"><span data-stu-id="aaf5f-107">Before enabling, please note that product recommendations are only supported for Commerce customers who have migrated their storage to using Azure Data Lake Storage (ADLS).</span></span> 

<span data-ttu-id="aaf5f-108">Information om hur du aktiverar ADLS finns i [Så här aktiverar du ADLS i en Dynamics 365-miljö](enable-ADLS-environment.md).</span><span class="sxs-lookup"><span data-stu-id="aaf5f-108">For steps on enabling ADLS, see [How to enable ADLS in a Dynamics 365 environment](enable-ADLS-environment.md).</span></span>

<span data-ttu-id="aaf5f-109">Kontrollera också att RetailSale-mätningar har aktiverats.</span><span class="sxs-lookup"><span data-stu-id="aaf5f-109">Additionally, ensure that RetailSale measurements have been enabled.</span></span> <span data-ttu-id="aaf5f-110">Du får mer information om den här inställningsprocessen [här.](https://docs.microsoft.com/en-us/dynamics365/ai/customer-insights/pm-measures)</span><span class="sxs-lookup"><span data-stu-id="aaf5f-110">To learn more about this set up process, go [here.](https://docs.microsoft.com/en-us/dynamics365/ai/customer-insights/pm-measures)</span></span>


## <a name="turn-on-recommendations"></a><span data-ttu-id="aaf5f-111">Aktivera rekommendationer</span><span class="sxs-lookup"><span data-stu-id="aaf5f-111">Turn on recommendations</span></span>

<span data-ttu-id="aaf5f-112">Så här aktiverar du produktrekommendationer.</span><span class="sxs-lookup"><span data-stu-id="aaf5f-112">To turn on product recommendations, follow these steps.</span></span>

1. <span data-ttu-id="aaf5f-113">Gå till **Butik och handel &gt; Produktrekommendationer &gt; Rekommendationsparametrar**.</span><span class="sxs-lookup"><span data-stu-id="aaf5f-113">Go to **Retail and Commerce &gt; Product recommendations &gt; Recommendation parameters**.</span></span>
1. <span data-ttu-id="aaf5f-114">I listan över delade parametrar, välj **Rekommendationslistor**.</span><span class="sxs-lookup"><span data-stu-id="aaf5f-114">In the list of shared parameters, select **Recommendation Lists**.</span></span>
1. <span data-ttu-id="aaf5f-115">Ge alternativet **Aktivera rekommendationer** värdet **Ja**.</span><span class="sxs-lookup"><span data-stu-id="aaf5f-115">Set the **Enable recommendations** option to **Yes**.</span></span>

![aktivera produktrekommendationer](./media/enableproductrecommendations.png)

> [!NOTE]
> <span data-ttu-id="aaf5f-117">I den här proceduren inleds processen med att generera listor över produktrekommendationer.</span><span class="sxs-lookup"><span data-stu-id="aaf5f-117">This procedure starts the process of generating product recommendation lists.</span></span> <span data-ttu-id="aaf5f-118">Det kan krävas upp till flera timmar innan listorna är tillgängliga och kan visas i kassan (POS) eller i Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="aaf5f-118">Up to several hours might be required before the lists are available and can be seen at the point of sale (POS) or in Dynamics 365 Commerce.</span></span>

## <a name="configure-recommendation-list-parameters"></a><span data-ttu-id="aaf5f-119">Konfigurera parametrar för rekommendationslista</span><span class="sxs-lookup"><span data-stu-id="aaf5f-119">Configure recommendation list parameters</span></span>

<span data-ttu-id="aaf5f-120">Som standard innehåller listan AI-ML-baserad produktrekommendation förslagna värden.</span><span class="sxs-lookup"><span data-stu-id="aaf5f-120">By default, the AI-ML-based product recommendation list provides suggested values.</span></span> <span data-ttu-id="aaf5f-121">Du kan ändra de föreslagna standardvärdena så att de passar affärsflödet.</span><span class="sxs-lookup"><span data-stu-id="aaf5f-121">You can change the default suggested values to suit the flow of your business.</span></span> <span data-ttu-id="aaf5f-122">Om du vill veta mer om hur du ändrar standardparametrarna kan du gå till [Hantera AI-ML-baserade produktrekommendationsresultat](modify-product-recommendation-results.md).</span><span class="sxs-lookup"><span data-stu-id="aaf5f-122">To learn more about how to change the default parameters, go to [Manage AI-ML-based product recommendation results](modify-product-recommendation-results.md).</span></span>

## <a name="show-recommendations-on-pos-devices"></a><span data-ttu-id="aaf5f-123">Visa rekommendationer på kassaenheter</span><span class="sxs-lookup"><span data-stu-id="aaf5f-123">Show recommendations on POS devices</span></span>

<span data-ttu-id="aaf5f-124">När du har aktiverat rekommendationer i backoffice för Handel måste rekommendationspanelen läggas till i kassans kontrollskärm via layoutverktyget.</span><span class="sxs-lookup"><span data-stu-id="aaf5f-124">After enabling recommendations in Commerce back office, the recommendations panel must be added to the control POS screen using the layout tool.</span></span> <span data-ttu-id="aaf5f-125">Mer information om den här processen finns i [Lägga till en rekommendationskontroll till transaktionsskärmen på kassaenheter](add-recommendations-control-pos-screen.md).</span><span class="sxs-lookup"><span data-stu-id="aaf5f-125">To learn about this process, see [Add a recommendations control to the transaction screen on POS devices](add-recommendations-control-pos-screen.md).</span></span> 

## <a name="enable-personalized-recommendations"></a><span data-ttu-id="aaf5f-126">Aktivera anpassade rekommendationer</span><span class="sxs-lookup"><span data-stu-id="aaf5f-126">Enable personalized recommendations</span></span>

<span data-ttu-id="aaf5f-127">Mer information om hur du tar emot anpassade rekommendationer finns i [aktivera anpassade rekommendationer](personalized-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="aaf5f-127">To learn more about how to receive personalized recommendations, see [Enable personalized recommendations](personalized-recommendations.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="aaf5f-128">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="aaf5f-128">Additional resources</span></span>

[<span data-ttu-id="aaf5f-129">Översikt av produktrekommendationer</span><span class="sxs-lookup"><span data-stu-id="aaf5f-129">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="aaf5f-130">Aktivera anpassade rekommendationer</span><span class="sxs-lookup"><span data-stu-id="aaf5f-130">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="aaf5f-131">Lägg till produktrekommendationer på sidor</span><span class="sxs-lookup"><span data-stu-id="aaf5f-131">Add product recommendation lists to pages</span></span>](add-reco-list-to-page.md)

[<span data-ttu-id="aaf5f-132">Lägg till rekommendationspanelen i kassaenheter</span><span class="sxs-lookup"><span data-stu-id="aaf5f-132">Add recommendations panel to POS devices</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="aaf5f-133">Översikt över produktsamlingsmodul</span><span class="sxs-lookup"><span data-stu-id="aaf5f-133">Product collection module overview</span></span>](product-collection-module-overview.md)

[<span data-ttu-id="aaf5f-134">Aktivera ADLS i Dynamics 365-miljön</span><span class="sxs-lookup"><span data-stu-id="aaf5f-134">Enable ADLS in Dynamics 365 environment</span></span>](enable-ADLS-environment.md)

