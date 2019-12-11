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
# <a name="enable-product-recommendations"></a><span data-ttu-id="fb790-103">Aktivera produktrekommendationer</span><span class="sxs-lookup"><span data-stu-id="fb790-103">Enable product recommendations</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="fb790-104">I det här avsnittet beskrivs hur du gör produktrekommendationer som baseras på artificiell intelligens (AI-ML) tillgängligt för Microsoft Dynamics 365 Commerce-kunder.</span><span class="sxs-lookup"><span data-stu-id="fb790-104">This topic explains how to make product recommendations that are based on artificial intelligence-machine learning (AI-ML) available for Microsoft Dynamics 365 Commerce customers.</span></span> <span data-ttu-id="fb790-105">Mer information om produktrekommendationslistor finns i [produktrekommendationer - översikt](product-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="fb790-105">For more information about product recommendation lists, see [Product recommendations overview](product-recommendations.md).</span></span>

## <a name="recommendations-pre-check"></a><span data-ttu-id="fb790-106">Förkontroll av rekommendationer</span><span class="sxs-lookup"><span data-stu-id="fb790-106">Recommendations pre-check</span></span>
<span data-ttu-id="fb790-107">Innan du aktiverar produkten bör du notera att produktrekommendationer endast stöds för F&O-kunder som stöder version 10.0.6 och har migrerat deras lagring till att använda BDL.</span><span class="sxs-lookup"><span data-stu-id="fb790-107">Before enabling, please note that product recommendations are only supported for F&O customers supporting build 10.0.6 and have migrated their storage to using BDL.</span></span> 

<span data-ttu-id="fb790-108">Kontrollera också att RetailSale-mätningar har aktiverats.</span><span class="sxs-lookup"><span data-stu-id="fb790-108">Additionally, ensure that RetailSale measurements have been enabled.</span></span> <span data-ttu-id="fb790-109">Du får mer information om den här inställningsprocessen [här.](https://docs.microsoft.com/en-us/dynamics365/ai/customer-insights/pm-measures)</span><span class="sxs-lookup"><span data-stu-id="fb790-109">To Learn more about this set up process, go [here.](https://docs.microsoft.com/en-us/dynamics365/ai/customer-insights/pm-measures)</span></span>


## <a name="turn-on-recommendations"></a><span data-ttu-id="fb790-110">Aktivera rekommendationer</span><span class="sxs-lookup"><span data-stu-id="fb790-110">Turn on recommendations</span></span>

<span data-ttu-id="fb790-111">Så här aktiverar du produktrekommendationer.</span><span class="sxs-lookup"><span data-stu-id="fb790-111">To turn on product recommendations, follow these steps.</span></span>

1. <span data-ttu-id="fb790-112">Gå till **Butik** &gt; **Produktrekommendationer** &gt; **Rekommendationsparametrar**.</span><span class="sxs-lookup"><span data-stu-id="fb790-112">Go to **Retail** &gt; **Product recommendations** &gt; **Recommendation parameters**.</span></span>
1. <span data-ttu-id="fb790-113">I listan över delade butiksparametrar, välj **Rekommendationslistor**.</span><span class="sxs-lookup"><span data-stu-id="fb790-113">In the list of retail shared parameters, select **Recommendation Lists**.</span></span>
1. <span data-ttu-id="fb790-114">Ge alternativet **Aktivera rekommendationer** värdet **Ja**.</span><span class="sxs-lookup"><span data-stu-id="fb790-114">Set the **Enable recommendations** option to **Yes**.</span></span>

![aktivera produktrekommendationer](./media/enableproductrecommendations.png)

> [!NOTE]
> <span data-ttu-id="fb790-116">I den här proceduren inleds processen med att generera listor över produktrekommendationer.</span><span class="sxs-lookup"><span data-stu-id="fb790-116">This procedure starts the process of generating product recommendation lists.</span></span> <span data-ttu-id="fb790-117">Det kan krävas upp till flera timmar innan listorna är tillgängliga och kan visas i kassan (POS) eller i Dynamics 365 for Commerce.</span><span class="sxs-lookup"><span data-stu-id="fb790-117">Up to several hours might be required before the lists are available and can be seen at the point of sale (POS) or in Dynamics 365 for Commerce.</span></span>

## <a name="configure-recommendation-list-parameters"></a><span data-ttu-id="fb790-118">Konfigurera parametrar för rekommendationslista</span><span class="sxs-lookup"><span data-stu-id="fb790-118">Configure recommendation list parameters</span></span>
<span data-ttu-id="fb790-119">Som standard innehåller listan AI-ML-baserad produktrekommendation förslagna värden.</span><span class="sxs-lookup"><span data-stu-id="fb790-119">By default, the AI-ML-based product recommendation list provides suggested values.</span></span> <span data-ttu-id="fb790-120">Du kan ändra de föreslagna standardvärdena så att de passar affärsflödet.</span><span class="sxs-lookup"><span data-stu-id="fb790-120">You can change the default suggested values to suit the flow of your business.</span></span> <span data-ttu-id="fb790-121">Om du vill veta mer om hur du ändrar standardparametrarna kan du gå till [Hantera AI-ML-baserade produktrekommendationsresultat](modify-product-recommendation-results.md).</span><span class="sxs-lookup"><span data-stu-id="fb790-121">To learn more about how to change the default parameters, go to [Manage AI-ML-based product recommendation results](modify-product-recommendation-results.md).</span></span>

## <a name="show-recommendations-on-pos-devices"></a><span data-ttu-id="fb790-122">Visa rekommendationer på kassaenheter</span><span class="sxs-lookup"><span data-stu-id="fb790-122">Show recommendations on POS devices</span></span>
<span data-ttu-id="fb790-123">När du har aktiverat rekommendationer i backoffice måste rekommendationspanelen läggas till i kassans kontrollskärm via layoutverktyget.</span><span class="sxs-lookup"><span data-stu-id="fb790-123">After enabling recommendations in the back office, the recommendations pannel must be added to the control POS screen via the layout tool.</span></span> <span data-ttu-id="fb790-124">Du får mer information om den här processen [här.](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/add-recommendations-control-pos-screen)</span><span class="sxs-lookup"><span data-stu-id="fb790-124">To learn about this process, go [here.](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/add-recommendations-control-pos-screen)</span></span>


## <a name="additional-resources"></a><span data-ttu-id="fb790-125">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="fb790-125">Additional resources</span></span>

[<span data-ttu-id="fb790-126">Översikt av produktrekommendationer</span><span class="sxs-lookup"><span data-stu-id="fb790-126">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="fb790-127">Lägg till produktrekommendationer på sidor</span><span class="sxs-lookup"><span data-stu-id="fb790-127">Add product recommendation lists to pages</span></span>](add-reco-list-to-page.md)

[<span data-ttu-id="fb790-128">Lägg till rekommendationspanelen i kassaenheter</span><span class="sxs-lookup"><span data-stu-id="fb790-128">Add recommendations panel to POS devices</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/add-recommendations-control-pos-screen)


