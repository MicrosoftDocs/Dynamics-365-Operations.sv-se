---
title: Aktivera rekommendationer för "sök efter liknande beskrivning"
description: I det här avsnittet beskrivs hur du aktiverar produktrekommendationerna för "leta efter liknande beskrivning" i Microsoft Dynamics 365 Commerce.
author: bsokolov
manager: AnnBe
ms.date: 01/13/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: b6b397b1f21e3dfcdb4a2b7fe67ddb541d090a97
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5234399"
---
# <a name="enable-shop-similar-description-recommendations"></a><span data-ttu-id="12838-103">Aktivera rekommendationer för "köp liknande beskrivning"</span><span class="sxs-lookup"><span data-stu-id="12838-103">Enable "shop similar description" recommendations</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="12838-104">I det här avsnittet beskrivs hur du aktiverar produktrekommendationerna för "leta efter liknande beskrivning" i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="12838-104">This topic describes how to enable "shop similar description" product recommendations in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="12838-105">Med hjälp av rekommendationsfunktionen för "sök liknande beskrivning" i Dynamics 365 Commerce används artificiell intelligens och maskininlärning (AI-ML) för att leverera rekommendationer för produkter med beskrivningar som liknar det som kunden söker.</span><span class="sxs-lookup"><span data-stu-id="12838-105">The "shop similar description" recommendations feature in Dynamics 365 Commerce uses artificial intelligence and machine learning (AI-ML) to deliver recommendations for products that have descriptions that are similar to what the customer is looking for.</span></span> <span data-ttu-id="12838-106">Genom att göra rekommendationer av typen "sök efter liknande beskrivning" tillgängliga för alla detaljhandelskanaler i Commerce kan återförsäljare göra det lättare för kunder att enkelt hitta vad de vill ha.</span><span class="sxs-lookup"><span data-stu-id="12838-106">By making "shop similar description" recommendations available for all retail channels in Commerce, retailers can help customers easily find what they want.</span></span>

<span data-ttu-id="12838-107">Rekommendationsfunktionerna för "sök efter liknande beskrivning" använder produktens namn och beskrivningen av sagda produkter för att hitta och rekommendera likartade produkter i en återförsäljares produktkatalog.</span><span class="sxs-lookup"><span data-stu-id="12838-107">The functionality for "shop similar description" recommendations uses the product name and description of seed products to find and recommend similar products in a retailer's product catalog.</span></span>

<span data-ttu-id="12838-108">Rekommendationerna för "köp liknande produkter" finns i såväl kassa- (POS) som näthandelsupplevelserna.</span><span class="sxs-lookup"><span data-stu-id="12838-108">"Shop similar description" recommendations are available in both the point of sale (POS) and e-commerce experiences.</span></span>

## <a name="example-scenarios"></a><span data-ttu-id="12838-109">Exempelscenarier</span><span class="sxs-lookup"><span data-stu-id="12838-109">Example scenarios</span></span>

<span data-ttu-id="12838-110">Följande exempelscenarier visar de typer av rekommendationer som funktionen "sök efter liknande beskrivning" kan ge:</span><span class="sxs-lookup"><span data-stu-id="12838-110">The following example scenarios show the types of recommendations that the "shop similar description" functionality can provide:</span></span>

- <span data-ttu-id="12838-111">En kund ser ett par hornbågade glasögon i retro-stil och får en uppsättning rekommendationer för andra glasögon med liknande design, inom återförsäljarens bransch.</span><span class="sxs-lookup"><span data-stu-id="12838-111">A customer views a pair of retro-style horn-rimmed glasses and receives a set of recommendations for other glasses that have a similar design, in the context of the retailer's industry.</span></span>
- <span data-ttu-id="12838-112">En kund använder rekommendationer för "sök efter liknande beskrivning" för att upptäcka kaffesmaker som liknar en han/hon nyligen inköpt från återförsäljaren.</span><span class="sxs-lookup"><span data-stu-id="12838-112">A customer uses "shop similar description" recommendations to discover coffee flavors that are similar to a flavor that they previously purchased from the retailer.</span></span>

## <a name="set-up-shop-similar-description-recommendations"></a><span data-ttu-id="12838-113">Konfigurera rekommendationer för "sök efter liknande beskrivning"</span><span class="sxs-lookup"><span data-stu-id="12838-113">Set up "shop similar description" recommendations</span></span>

<span data-ttu-id="12838-114">Produktrekommendationer stöds endast för Commerce-användare som har migrerat sin lagring till Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="12838-114">Product recommendations are supported only for Commerce users who have migrated their storage to Azure Data Lake Storage Gen2.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="12838-115">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="12838-115">Prerequisites</span></span>

<span data-ttu-id="12838-116">Innan rekommendationer för "sök efter liknande beskrivning" kan visas för kunderna måste du uppfylla följande förutsättningar:</span><span class="sxs-lookup"><span data-stu-id="12838-116">Before "shop similar description" recommendations can be shown to customers, you must complete the following prerequisites:</span></span>

- <span data-ttu-id="12838-117">[Aktivera produktrekommendationer](enable-product-recommendations.md) i Commerce-administration.</span><span class="sxs-lookup"><span data-stu-id="12838-117">[Enable product recommendations](enable-product-recommendations.md) in Commerce headquarters.</span></span>
- <span data-ttu-id="12838-118">Kontrollera att mediaservern stöder HTTPS-anrop.</span><span class="sxs-lookup"><span data-stu-id="12838-118">Confirm that the media server supports HTTPS calls.</span></span>

### <a name="turn-on-the-shop-similar-description-recommendations-feature"></a><span data-ttu-id="12838-119">Aktivera rekommendationsfunktionen för "sök efter liknande beskrivning"</span><span class="sxs-lookup"><span data-stu-id="12838-119">Turn on the "shop similar description" recommendations feature</span></span>

<span data-ttu-id="12838-120">Gör så här om du vill aktivera rekommendationsfunktionen "sök efter liknande beskrivning" i Commerce-administrationen.</span><span class="sxs-lookup"><span data-stu-id="12838-120">To turn on the "shop similar description" recommendations feature in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="12838-121">I arbetsytan **Funktionshantering**, i listan över tillgängliga funktioner, söker du efter och väljer **Sök efter liknande beskrivning**.</span><span class="sxs-lookup"><span data-stu-id="12838-121">In the **Feature management** workspace, in the list of available features, search for and select **Shop similar description**.</span></span>
1. <span data-ttu-id="12838-122">Välj **Aktivera** i höger fönster.</span><span class="sxs-lookup"><span data-stu-id="12838-122">In the right pane, select **Enable**.</span></span>

> [!NOTE]
> <span data-ttu-id="12838-123">När du aktiverar funktionen börjar systemet att generera listor med produktrekommendationer.</span><span class="sxs-lookup"><span data-stu-id="12838-123">When you turn on the feature, the system starts to generate product recommendation lists.</span></span> <span data-ttu-id="12838-124">Det kan krävas upp till en dag för att dessa listor ska bli tillgängliga och synliga online och i kassan.</span><span class="sxs-lookup"><span data-stu-id="12838-124">It might take up to a day for those lists to become available and visible online and on POS terminals.</span></span>
>
> <span data-ttu-id="12838-125">Om du inaktiverar funktionen påverkas inte andra typer av produktrekommendationer.</span><span class="sxs-lookup"><span data-stu-id="12838-125">If you turn off the feature, other types of product recommendations aren't affected.</span></span> <span data-ttu-id="12838-126">Mer information om produktrekommendationslistor finns i [produktrekommendationer – översikt](product-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="12838-126">For more information about product recommendations, see [Product recommendations overview](product-recommendations.md).</span></span>

## <a name="add-a-shop-similar-description-button-to-product-details-pages"></a><span data-ttu-id="12838-127">Lägg till en Sök efter liknande beskrivning-knapp på produktinformationssidor</span><span class="sxs-lookup"><span data-stu-id="12838-127">Add a Shop similar description button to product details pages</span></span>

<span data-ttu-id="12838-128">När du har aktiverat rekommendationsfunktionen "sök efter liknande beskrivning" i Commerce-administrationen kan du lägga till en **Sök efter liknande beskrivning**-knapp i köprutan på valfri produktinformationssida (PDP).</span><span class="sxs-lookup"><span data-stu-id="12838-128">After you turn on the "shop similar description" recommendations feature in Commerce headquarters, you can add a **Shop similar description** button to the buy box on any product details page (PDP).</span></span> <span data-ttu-id="12838-129">En kund som väljer den här knappen tas till en särskild **Sök efter liknande beskrivning**-sida som visar visuellt likartade produkter.</span><span class="sxs-lookup"><span data-stu-id="12838-129">A customer who selects this button is taken to a dedicated **Shop similar description** page that shows visually similar products.</span></span> <span data-ttu-id="12838-130">Kunden kan därefter använda väljare för att filtrera produkterna ytterligare.</span><span class="sxs-lookup"><span data-stu-id="12838-130">The customer can then use selectors to further filter the products.</span></span>

<span data-ttu-id="12838-131">Lägg till en **Sök efter liknande beskrivning**-knapp på en PDP med hjälp av Commerce-webbplatsbyggaren genom att följa följande steg.</span><span class="sxs-lookup"><span data-stu-id="12838-131">To add a **Shop similar description** button to a PDP by using Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="12838-132">Öppna en befintlig sida i webbplatsskaparen som innehåller en modul för köpruta.</span><span class="sxs-lookup"><span data-stu-id="12838-132">Open an existing site builder page that contains a buy box module.</span></span>
1. <span data-ttu-id="12838-133">I vänster navigeringsfönstret, välj modul för köpruta.</span><span class="sxs-lookup"><span data-stu-id="12838-133">In the left navigation pane, select the buy box module.</span></span>
1. <span data-ttu-id="12838-134">I det högra fönstret väljer du kryssrutan **Aktivera länken Sök efter liknande beskrivning**.</span><span class="sxs-lookup"><span data-stu-id="12838-134">In the right pane, select the **Enable Shop Similar description Link** check box.</span></span>
1. <span data-ttu-id="12838-135">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="12838-135">Select **Save**.</span></span>
1. <span data-ttu-id="12838-136">Välj **Slutför redigering** för att checka in sidan och välj sedan **publicera** för att publicera den.</span><span class="sxs-lookup"><span data-stu-id="12838-136">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span> <span data-ttu-id="12838-137">När sidan har publicerats innehåller PDP en knapp för **Sök efter liknande beskrivning**.</span><span class="sxs-lookup"><span data-stu-id="12838-137">After the page is published, the PDP will include a **Shop similar description** button.</span></span>

<span data-ttu-id="12838-138">Bilden nedan visar kryssrutan **Aktivera länken Sök efter liknande beskrivning** och knappen **Sök efter liknande beskrivning** på en exempel-PDP i webbplatsbyggaren.</span><span class="sxs-lookup"><span data-stu-id="12838-138">The following illustration shows the **Enable shop similar description Link** check box and the **Shop similar description** button on an example PDP in site builder.</span></span>

![Aktivera kryssrutan Sök efter liknande beskrivningslänk och knappen Sök efter liknande beskrivning på en PDP i webbplatsbyggaren](./media/ter_site_builder_buybox_button.png)

## <a name="additional-resources"></a><span data-ttu-id="12838-140">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="12838-140">Additional resources</span></span>

[<span data-ttu-id="12838-141">Översikt av produktrekommendationer</span><span class="sxs-lookup"><span data-stu-id="12838-141">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="12838-142">Aktivera Azure Data Lake Storage i en Dynamics 365 Commerce-miljö</span><span class="sxs-lookup"><span data-stu-id="12838-142">Enable Azure Data Lake Storage in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="12838-143">Aktivera produktrekommendationer</span><span class="sxs-lookup"><span data-stu-id="12838-143">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="12838-144">Aktivera rekommendationer för "köp liknande produkter"</span><span class="sxs-lookup"><span data-stu-id="12838-144">Enable "shop similar looks" recommendations</span></span>](shop-similar-looks.md)

[<span data-ttu-id="12838-145">Justera rekommendationsresultat från AI-ML</span><span class="sxs-lookup"><span data-stu-id="12838-145">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="12838-146">Skapa granskade rekommendationer manuellt</span><span class="sxs-lookup"><span data-stu-id="12838-146">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="12838-147">Vanliga frågor om produktrekommendationer</span><span class="sxs-lookup"><span data-stu-id="12838-147">Product recommendations FAQ</span></span>](faq-recommendations.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]