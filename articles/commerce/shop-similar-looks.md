---
title: Aktivera rekommendationer för "köp liknande produkter"
description: I det här avsnittet beskrivs hur du aktiverar produktrekommendationerna "köp liknande produkter" i Microsoft Dynamics 365 Commerce.
author: bebeale
manager: AnnBe
ms.date: 08/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 95e4246d6c5f9ac5bc86b626be0d971f756c5130
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4985621"
---
# <a name="enable-shop-similar-looks-recommendations"></a><span data-ttu-id="83b4d-103">Aktivera rekommendationer för "köp liknande produkter"</span><span class="sxs-lookup"><span data-stu-id="83b4d-103">Enable "shop similar looks" recommendations</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="83b4d-104">I det här avsnittet beskrivs hur du aktiverar produktrekommendationerna "köp liknande produkter" i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="83b4d-104">This topic describes how to enable "shop similar looks" product recommendations in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="83b4d-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="83b4d-105">Overview</span></span>

<span data-ttu-id="83b4d-106">Med hjälp av rekommendationerna "köp liknande produkter" i Dynamics 365 Commerce används funktionerna hos artificiell intelligens och maskininlärning (AI-ML) för att leverera rekommendationer för visuellt likartade produkter till kunder.</span><span class="sxs-lookup"><span data-stu-id="83b4d-106">The "shop similar looks" recommendations feature in Dynamics 365 Commerce uses the power of artificial intelligence and machine learning (AI-ML) to deliver recommendations for visually similar products to customers.</span></span> <span data-ttu-id="83b4d-107">Genom att göra rekommendationer av typen "köp liknande produkter" tillgängliga för alla detaljhandelskanaler i Commerce kan återförsäljare öka kundtillfredsställelsen genom att hjälpa kunderna att enkelt hitta vad de vill ha.</span><span class="sxs-lookup"><span data-stu-id="83b4d-107">By making "shop similar looks" recommendations available for all retail channels in Commerce, retailers can increase customer satisfaction by helping customers easily find what they want.</span></span>

<span data-ttu-id="83b4d-108">Funktionerna för "köp liknande produkter" rekommendationer använder produktbilder av produktvarianter för att hitta och rekommendera visuellt likartade produkter i en återförsäljares produktkatalog.</span><span class="sxs-lookup"><span data-stu-id="83b4d-108">The functionality for "shop similar looks" recommendations uses product images of seed product variants to find and recommend visually similar products in a retailer's product catalog.</span></span> 

<span data-ttu-id="83b4d-109">Rekommendationerna för "köp liknande produkter" i både kassa- (POS) och näthandelsupplevelser.</span><span class="sxs-lookup"><span data-stu-id="83b4d-109">"Shop similar looks" recommendations are available in both the point of sale (POS) and e-Commerce experiences.</span></span>

### <a name="example-scenarios"></a><span data-ttu-id="83b4d-110">Exempelscenarier</span><span class="sxs-lookup"><span data-stu-id="83b4d-110">Example scenarios</span></span>

- <span data-ttu-id="83b4d-111">En kund visar en svartrandig tröja och får en rekommendation om liknande tröja i rött.</span><span class="sxs-lookup"><span data-stu-id="83b4d-111">A customer views a black striped sweater and receives a recommendation for a similar sweater in red.</span></span> <span data-ttu-id="83b4d-112">Kunden väljer den rekommenderade produkten i stället för den ursprungligen visade produkten och får rekommendationer för liknande produkter i rött.</span><span class="sxs-lookup"><span data-stu-id="83b4d-112">The customer selects the recommended product instead of the originally viewed product and then receives recommendations for similar products in red.</span></span> 
- <span data-ttu-id="83b4d-113">En kund använder rekommendationer om "köp liknande produkter" för att upptäcka matchande örhängen för en ring som kunden är intresserad av att köpa.</span><span class="sxs-lookup"><span data-stu-id="83b4d-113">A customer uses "shop similar looks" recommendations to discover matching earrings for a ring that the customer is interested in buying.</span></span>

## <a name="enable-shop-similar-looks-recommendations-in-commerce-headquarters"></a><span data-ttu-id="83b4d-114">Aktivera rekommendationerna "köp liknande produkter" i Commerce-administration</span><span class="sxs-lookup"><span data-stu-id="83b4d-114">Enable "shop similar looks" recommendations in Commerce headquarters</span></span>

<span data-ttu-id="83b4d-115">Produktrekommendationer stöds endast för Commerce-användare som har migrerat sin lagring till Azure Data Lake Gen2.</span><span class="sxs-lookup"><span data-stu-id="83b4d-115">Product recommendations are supported only for Commerce users who have migrated their storage to Azure Data Lake Gen2.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="83b4d-116">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="83b4d-116">Prerequisites</span></span>

<span data-ttu-id="83b4d-117">Innan återförsäljare kan börja visa rekommendationer från "köp liknande produkter", finns det två steg:</span><span class="sxs-lookup"><span data-stu-id="83b4d-117">Before retailers can begin to show "shop similar looks" recommendations to customers, there are two prerequisite steps:</span></span>

- <span data-ttu-id="83b4d-118">[Aktivera produktrekommendationer](enable-product-recommendations.md) i Commerce-administration.</span><span class="sxs-lookup"><span data-stu-id="83b4d-118">[Enable product recommendations](enable-product-recommendations.md) in Commerce headquarters.</span></span>
- <span data-ttu-id="83b4d-119">Kontrollera att mediaservern stöder HTTPS-anrop.</span><span class="sxs-lookup"><span data-stu-id="83b4d-119">Confirm that the media server supports HTTPS calls.</span></span>

<span data-ttu-id="83b4d-120">För att rekommendationsmotorn ska få åtkomst till produktbilderna måste återförsäljare generera produktens URL:er.</span><span class="sxs-lookup"><span data-stu-id="83b4d-120">For the recommendations engine to access the product images, retailers must generate the product URLs.</span></span> <span data-ttu-id="83b4d-121">För att generera URL:er i Commerce-administration, följ de här stegen.</span><span class="sxs-lookup"><span data-stu-id="83b4d-121">To generate product URLs in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="83b4d-122">Gå till **Produktbilder**.</span><span class="sxs-lookup"><span data-stu-id="83b4d-122">Go to **Product images**.</span></span>
1. <span data-ttu-id="83b4d-123">I åtgärdsfönstret, välj **Definiera mediemall**.</span><span class="sxs-lookup"><span data-stu-id="83b4d-123">On the Action Pane, select **Define media template**.</span></span>
1. <span data-ttu-id="83b4d-124">I egenskaper **Definiera mediemall** under **Media-URL:er**, välj **Generera URL:er**.</span><span class="sxs-lookup"><span data-stu-id="83b4d-124">In the **Define media template** properties pane, under **Media URLs**, select **Generate URLs**.</span></span>

> [!NOTE]
> <span data-ttu-id="83b4d-125">När du aktiverar rekommendationsfunktionen "köp liknande produkter", börjar processen att generera listor över produktrekommendationer.</span><span class="sxs-lookup"><span data-stu-id="83b4d-125">When you enable the "shop similar looks" recommendations feature, the process of generating product recommendation lists begins.</span></span> <span data-ttu-id="83b4d-126">Det kan krävas upp till en dag innan dessa listor är tillgängliga och kan visas online och i POS.</span><span class="sxs-lookup"><span data-stu-id="83b4d-126">Up to a day might be required before those lists are available and visible online and on POS terminals.</span></span>

<span data-ttu-id="83b4d-127">Gör så här om du vill aktivera rekommendationer funktionen "köp liknande produkter" i Commerce-administration.</span><span class="sxs-lookup"><span data-stu-id="83b4d-127">To enable the "shop similar looks" recommendations feature in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="83b4d-128">Gå till **Funktionshantering**.</span><span class="sxs-lookup"><span data-stu-id="83b4d-128">Go to **Feature management**.</span></span>
1. <span data-ttu-id="83b4d-129">I listan över tillgängliga funktioner söker du efter och väljer **köp liknande produkter**.</span><span class="sxs-lookup"><span data-stu-id="83b4d-129">In the list of available features, search for and select **Shop similar looks**.</span></span>
1. <span data-ttu-id="83b4d-130">I det högra fönstret väljer du **Aktivera** för att aktivera tjänsten.</span><span class="sxs-lookup"><span data-stu-id="83b4d-130">In the right pane, select **Enable** to turn on the service.</span></span>

<span data-ttu-id="83b4d-131">I följande bild visas funktionen **köp liknande produkter** på sidan **Funktionshantering** i Commerce-administration.</span><span class="sxs-lookup"><span data-stu-id="83b4d-131">The following illustration shows the **Shop similar looks** feature on the **Feature management** page in Commerce headquarters.</span></span>

![Funktionen handla liknande utseende på sidan funktionshantering i Commerce-administration](./media/enableshopsimilarlooks.png)

<span data-ttu-id="83b4d-133">När föregående uppgifter har slutförts förbättras kassaterminaler automatiskt med en panel för **köp liknande produkter**.</span><span class="sxs-lookup"><span data-stu-id="83b4d-133">After the preceding tasks been completed, POS terminals are automatically enhanced with a contextual **Shop similar products** panel.</span></span> <span data-ttu-id="83b4d-134">Genom att välja **Se mer** användare av kassaterminal kan tas till en dedikerad sida för "köp liknande produkter" som kan filtreras ytterligare.</span><span class="sxs-lookup"><span data-stu-id="83b4d-134">By selecting **See more**, POS terminal users can be taken to a dedicated "shop similar looks" page that can be filtered further.</span></span>

> [!NOTE]
> <span data-ttu-id="83b4d-135">Om du inaktiverar funktionen "köp liknande produkter" rekommenderar vi att inga andra typer av produktrekommendationer påverkas.</span><span class="sxs-lookup"><span data-stu-id="83b4d-135">If you turn off the "shop similar looks" recommendations feature, no other types of product recommendations are affected.</span></span> <span data-ttu-id="83b4d-136">Mer information om produktrekommendationslistor finns i [produktrekommendationer – översikt](product-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="83b4d-136">For more information about product recommendations, see [Product recommendations overview](product-recommendations.md).</span></span>

## <a name="add-a-shop-similar-looks-button-to-product-details-pages-by-using-commerce-site-builder"></a><span data-ttu-id="83b4d-137">Lägga till en knapp för köp liknande produkter på sidan med produktinformation genom att använda Commerce-webbplatsbyggaren</span><span class="sxs-lookup"><span data-stu-id="83b4d-137">Add a Shop similar looks button to product details pages by using Commerce site builder</span></span>

<span data-ttu-id="83b4d-138">När du har aktiverat rekommendationerna "köp liknande produkter" i Commerce-administration kan du välja ett alternativ i Commerce-webbplatsbyggaren för att lägga till knappar **köp liknande produkter** i köprutan på valfri produktinformationssida (PDP).</span><span class="sxs-lookup"><span data-stu-id="83b4d-138">After you enable the "shop similar looks" recommendations feature in Commerce headquarters, an option in Commerce site builder lets retailers to add a **Shop similar looks** button to the buy box on any product details page (PDP).</span></span> <span data-ttu-id="83b4d-139">En kund som väljer den här knappen tas till en särskild sida "köp liknande produkter" som returnerar visuellt likartade produkter.</span><span class="sxs-lookup"><span data-stu-id="83b4d-139">A customer who selects this button is taken to a dedicated "shop similar looks" page that returns visually similar products.</span></span> <span data-ttu-id="83b4d-140">Kunden kan använda väljare för att filtrera produkterna ytterligare.</span><span class="sxs-lookup"><span data-stu-id="83b4d-140">There, the customer can use selectors to further filter the products.</span></span>

<span data-ttu-id="83b4d-141">Lägg till en knapp för **Köp liknande produkter** till en PDP genom att använda Commerce-webbplatsbyggaren, följ dessa steg.</span><span class="sxs-lookup"><span data-stu-id="83b4d-141">To add a **Shop similar looks** button to a PDP by using Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="83b4d-142">Öppna en befintlig sida i webbplatsskaparen som innehåller en modul för köpruta.</span><span class="sxs-lookup"><span data-stu-id="83b4d-142">Open an existing site builder page that contains a buy box module.</span></span>
1. <span data-ttu-id="83b4d-143">I vänster navigeringsfönstret, välj modul för köpruta.</span><span class="sxs-lookup"><span data-stu-id="83b4d-143">In the left navigation pane, select the buy box module.</span></span>
1. <span data-ttu-id="83b4d-144">I det högra navigeringsfönstret markerar du kryssrutan **Aktivera länken köp liknande produkter**.</span><span class="sxs-lookup"><span data-stu-id="83b4d-144">In the right navigation pane, select the **Enable Shop Similar Looks Link** check box.</span></span>
1. <span data-ttu-id="83b4d-145">Välj **Spara**, välj **Slutför redigering** för att checka in sidan och välj sedan **publicera** för att publicera den.</span><span class="sxs-lookup"><span data-stu-id="83b4d-145">Select **Save**, select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span> <span data-ttu-id="83b4d-146">När sidan har publicerats innehåller PDP en knapp för **köp liknande produkter**.</span><span class="sxs-lookup"><span data-stu-id="83b4d-146">After the page is published, the PDP will include a **Shop similar looks** button.</span></span>

<span data-ttu-id="83b4d-147">Bilden nedan visar kryssrutan **Aktivera länken köp liknande produkter** och knappen **köp liknande produkter** på en exempel PDP i webbplatsskaparen.</span><span class="sxs-lookup"><span data-stu-id="83b4d-147">The following illustration shows the **Enable Shop Similar Looks Link** check box and **Shop similar looks** button on an example PDP in site builder.</span></span>

![Aktivera länken köp liknande produkter och knappen köp liknande produkter på en PDP i webbplatsskaparen.](./media/SSLecomtooling.png)

## <a name="additional-resources"></a><span data-ttu-id="83b4d-149">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="83b4d-149">Additional resources</span></span>

[<span data-ttu-id="83b4d-150">Översikt av produktrekommendationer</span><span class="sxs-lookup"><span data-stu-id="83b4d-150">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="83b4d-151">Aktivera Azure Data Lake Storage i en Dynamics 365 Commerce-miljö</span><span class="sxs-lookup"><span data-stu-id="83b4d-151">Enable Azure Data Lake Storage in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="83b4d-152">Aktivera produktrekommendationer</span><span class="sxs-lookup"><span data-stu-id="83b4d-152">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="83b4d-153">Avanmäl anpassade rekommendationer</span><span class="sxs-lookup"><span data-stu-id="83b4d-153">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="83b4d-154">Lägg till produktrekommendationer i POS</span><span class="sxs-lookup"><span data-stu-id="83b4d-154">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="83b4d-155">Lägg till rekommendationer på transaktionsskärmen</span><span class="sxs-lookup"><span data-stu-id="83b4d-155">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="83b4d-156">Justera rekommendationsresultat från AI-ML</span><span class="sxs-lookup"><span data-stu-id="83b4d-156">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="83b4d-157">Skapa granskade rekommendationer manuellt</span><span class="sxs-lookup"><span data-stu-id="83b4d-157">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="83b4d-158">Skapa rekommendationer med demodata</span><span class="sxs-lookup"><span data-stu-id="83b4d-158">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="83b4d-159">Vanliga frågor om produktrekommendationer</span><span class="sxs-lookup"><span data-stu-id="83b4d-159">Product recommendations FAQ</span></span>](faq-recommendations.md)
