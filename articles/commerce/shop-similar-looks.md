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
ms.openlocfilehash: d0b3585ce326e47b119b3f6c41436b9e6494ec87
ms.sourcegitcommit: c88b54ba13a4dfe39b844ffaced4dc435560c47d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/19/2021
ms.locfileid: "5478102"
---
# <a name="enable-shop-similar-looks-recommendations"></a><span data-ttu-id="75ec8-103">Aktivera rekommendationer för "köp liknande produkter"</span><span class="sxs-lookup"><span data-stu-id="75ec8-103">Enable "shop similar looks" recommendations</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="75ec8-104">I det här avsnittet beskrivs hur du aktiverar produktrekommendationerna "köp liknande produkter" i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="75ec8-104">This topic describes how to enable "shop similar looks" product recommendations in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="75ec8-105">Med hjälp av rekommendationerna "köp liknande produkter" i Dynamics 365 Commerce används funktionerna hos artificiell intelligens och maskininlärning (AI-ML) för att leverera rekommendationer för visuellt likartade produkter till kunder.</span><span class="sxs-lookup"><span data-stu-id="75ec8-105">The "shop similar looks" recommendations feature in Dynamics 365 Commerce uses the power of artificial intelligence and machine learning (AI-ML) to deliver recommendations for visually similar products to customers.</span></span> <span data-ttu-id="75ec8-106">Genom att göra rekommendationer av typen "köp liknande produkter" tillgängliga för alla detaljhandelskanaler i Commerce kan återförsäljare öka kundtillfredsställelsen genom att hjälpa kunderna att enkelt hitta vad de vill ha.</span><span class="sxs-lookup"><span data-stu-id="75ec8-106">By making "shop similar looks" recommendations available for all retail channels in Commerce, retailers can increase customer satisfaction by helping customers easily find what they want.</span></span>

<span data-ttu-id="75ec8-107">Funktionerna för "köp liknande produkter" rekommendationer använder produktbilder av produktvarianter för att hitta och rekommendera visuellt likartade produkter i en återförsäljares produktkatalog.</span><span class="sxs-lookup"><span data-stu-id="75ec8-107">The functionality for "shop similar looks" recommendations uses product images of seed product variants to find and recommend visually similar products in a retailer's product catalog.</span></span> 

<span data-ttu-id="75ec8-108">Rekommendationerna för "köp liknande produkter" i både kassa- (POS) och näthandelsupplevelser.</span><span class="sxs-lookup"><span data-stu-id="75ec8-108">"Shop similar looks" recommendations are available in both the point of sale (POS) and e-Commerce experiences.</span></span>

### <a name="example-scenarios"></a><span data-ttu-id="75ec8-109">Exempelscenarier</span><span class="sxs-lookup"><span data-stu-id="75ec8-109">Example scenarios</span></span>

- <span data-ttu-id="75ec8-110">En kund visar en svartrandig tröja och får en rekommendation om liknande tröja i rött.</span><span class="sxs-lookup"><span data-stu-id="75ec8-110">A customer views a black striped sweater and receives a recommendation for a similar sweater in red.</span></span> <span data-ttu-id="75ec8-111">Kunden väljer den rekommenderade produkten i stället för den ursprungligen visade produkten och får rekommendationer för liknande produkter i rött.</span><span class="sxs-lookup"><span data-stu-id="75ec8-111">The customer selects the recommended product instead of the originally viewed product and then receives recommendations for similar products in red.</span></span> 
- <span data-ttu-id="75ec8-112">En kund använder rekommendationer om "köp liknande produkter" för att upptäcka matchande örhängen för en ring som kunden är intresserad av att köpa.</span><span class="sxs-lookup"><span data-stu-id="75ec8-112">A customer uses "shop similar looks" recommendations to discover matching earrings for a ring that the customer is interested in buying.</span></span>

## <a name="enable-shop-similar-looks-recommendations-in-commerce-headquarters"></a><span data-ttu-id="75ec8-113">Aktivera rekommendationerna "köp liknande produkter" i Commerce-administration</span><span class="sxs-lookup"><span data-stu-id="75ec8-113">Enable "shop similar looks" recommendations in Commerce headquarters</span></span>

<span data-ttu-id="75ec8-114">Produktrekommendationer stöds endast för Commerce-användare som har migrerat sin lagring till Azure Data Lake Gen2.</span><span class="sxs-lookup"><span data-stu-id="75ec8-114">Product recommendations are supported only for Commerce users who have migrated their storage to Azure Data Lake Gen2.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="75ec8-115">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="75ec8-115">Prerequisites</span></span>

<span data-ttu-id="75ec8-116">Innan återförsäljare kan börja visa rekommendationer från "köp liknande produkter", finns det två steg:</span><span class="sxs-lookup"><span data-stu-id="75ec8-116">Before retailers can begin to show "shop similar looks" recommendations to customers, there are two prerequisite steps:</span></span>

- <span data-ttu-id="75ec8-117">[Aktivera produktrekommendationer](enable-product-recommendations.md) i Commerce-administration.</span><span class="sxs-lookup"><span data-stu-id="75ec8-117">[Enable product recommendations](enable-product-recommendations.md) in Commerce headquarters.</span></span>
- <span data-ttu-id="75ec8-118">Kontrollera att mediaservern stöder HTTPS-anrop.</span><span class="sxs-lookup"><span data-stu-id="75ec8-118">Confirm that the media server supports HTTPS calls.</span></span>

<span data-ttu-id="75ec8-119">För att rekommendationsmotorn ska få åtkomst till produktbilderna måste återförsäljare generera produktens URL:er.</span><span class="sxs-lookup"><span data-stu-id="75ec8-119">For the recommendations engine to access the product images, retailers must generate the product URLs.</span></span> <span data-ttu-id="75ec8-120">För att generera URL:er i Commerce-administration, följ de här stegen.</span><span class="sxs-lookup"><span data-stu-id="75ec8-120">To generate product URLs in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="75ec8-121">Gå till **Produktbilder**.</span><span class="sxs-lookup"><span data-stu-id="75ec8-121">Go to **Product images**.</span></span>
1. <span data-ttu-id="75ec8-122">I åtgärdsfönstret, välj **Definiera mediemall**.</span><span class="sxs-lookup"><span data-stu-id="75ec8-122">On the Action Pane, select **Define media template**.</span></span>
1. <span data-ttu-id="75ec8-123">I egenskaper **Definiera mediemall** under **Media-URL:er**, välj **Generera URL:er**.</span><span class="sxs-lookup"><span data-stu-id="75ec8-123">In the **Define media template** properties pane, under **Media URLs**, select **Generate URLs**.</span></span>

> [!NOTE]
> <span data-ttu-id="75ec8-124">När du aktiverar rekommendationsfunktionen "köp liknande produkter", börjar processen att generera listor över produktrekommendationer.</span><span class="sxs-lookup"><span data-stu-id="75ec8-124">When you enable the "shop similar looks" recommendations feature, the process of generating product recommendation lists begins.</span></span> <span data-ttu-id="75ec8-125">Det kan krävas upp till en dag innan dessa listor är tillgängliga och kan visas online och i POS.</span><span class="sxs-lookup"><span data-stu-id="75ec8-125">Up to a day might be required before those lists are available and visible online and on POS terminals.</span></span>

<span data-ttu-id="75ec8-126">Gör så här om du vill aktivera rekommendationer funktionen "köp liknande produkter" i Commerce-administration.</span><span class="sxs-lookup"><span data-stu-id="75ec8-126">To enable the "shop similar looks" recommendations feature in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="75ec8-127">Gå till **Funktionshantering**.</span><span class="sxs-lookup"><span data-stu-id="75ec8-127">Go to **Feature management**.</span></span>
1. <span data-ttu-id="75ec8-128">I listan över tillgängliga funktioner söker du efter och väljer **köp liknande produkter**.</span><span class="sxs-lookup"><span data-stu-id="75ec8-128">In the list of available features, search for and select **Shop similar looks**.</span></span>
1. <span data-ttu-id="75ec8-129">I det högra fönstret väljer du **Aktivera** för att aktivera tjänsten.</span><span class="sxs-lookup"><span data-stu-id="75ec8-129">In the right pane, select **Enable** to turn on the service.</span></span>

<span data-ttu-id="75ec8-130">I följande bild visas funktionen **köp liknande produkter** på sidan **Funktionshantering** i Commerce-administration.</span><span class="sxs-lookup"><span data-stu-id="75ec8-130">The following illustration shows the **Shop similar looks** feature on the **Feature management** page in Commerce headquarters.</span></span>

![Funktionen handla liknande utseende på sidan funktionshantering i Commerce-administration](./media/enableshopsimilarlooks.png)

<span data-ttu-id="75ec8-132">När föregående uppgifter har slutförts förbättras kassaterminaler automatiskt med en panel för **köp liknande produkter**.</span><span class="sxs-lookup"><span data-stu-id="75ec8-132">After the preceding tasks been completed, POS terminals are automatically enhanced with a contextual **Shop similar products** panel.</span></span> <span data-ttu-id="75ec8-133">Genom att välja **Se mer** användare av kassaterminal kan tas till en dedikerad sida för "köp liknande produkter" som kan filtreras ytterligare.</span><span class="sxs-lookup"><span data-stu-id="75ec8-133">By selecting **See more**, POS terminal users can be taken to a dedicated "shop similar looks" page that can be filtered further.</span></span>

> [!NOTE]
> <span data-ttu-id="75ec8-134">Om du inaktiverar funktionen "köp liknande produkter" rekommenderar vi att inga andra typer av produktrekommendationer påverkas.</span><span class="sxs-lookup"><span data-stu-id="75ec8-134">If you turn off the "shop similar looks" recommendations feature, no other types of product recommendations are affected.</span></span> <span data-ttu-id="75ec8-135">Mer information om produktrekommendationslistor finns i [produktrekommendationer – översikt](product-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="75ec8-135">For more information about product recommendations, see [Product recommendations overview](product-recommendations.md).</span></span>

## <a name="add-a-shop-similar-looks-button-to-product-details-pages-by-using-commerce-site-builder"></a><span data-ttu-id="75ec8-136">Lägga till en knapp för köp liknande produkter på sidan med produktinformation genom att använda Commerce-webbplatsbyggaren</span><span class="sxs-lookup"><span data-stu-id="75ec8-136">Add a Shop similar looks button to product details pages by using Commerce site builder</span></span>

<span data-ttu-id="75ec8-137">När du har aktiverat rekommendationerna "köp liknande produkter" i Commerce-administration kan du välja ett alternativ i Commerce-webbplatsbyggaren för att lägga till knappar **köp liknande produkter** i köprutan på valfri produktinformationssida (PDP).</span><span class="sxs-lookup"><span data-stu-id="75ec8-137">After you enable the "shop similar looks" recommendations feature in Commerce headquarters, an option in Commerce site builder lets retailers to add a **Shop similar looks** button to the buy box on any product details page (PDP).</span></span> <span data-ttu-id="75ec8-138">En kund som väljer den här knappen tas till en särskild sida "köp liknande produkter" som returnerar visuellt likartade produkter.</span><span class="sxs-lookup"><span data-stu-id="75ec8-138">A customer who selects this button is taken to a dedicated "shop similar looks" page that returns visually similar products.</span></span> <span data-ttu-id="75ec8-139">Kunden kan använda väljare för att filtrera produkterna ytterligare.</span><span class="sxs-lookup"><span data-stu-id="75ec8-139">There, the customer can use selectors to further filter the products.</span></span>

<span data-ttu-id="75ec8-140">Lägg till en knapp för **Köp liknande produkter** till en PDP genom att använda Commerce-webbplatsbyggaren, följ dessa steg.</span><span class="sxs-lookup"><span data-stu-id="75ec8-140">To add a **Shop similar looks** button to a PDP by using Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="75ec8-141">Öppna en befintlig sida i webbplatsskaparen som innehåller en modul för köpruta.</span><span class="sxs-lookup"><span data-stu-id="75ec8-141">Open an existing site builder page that contains a buy box module.</span></span>
1. <span data-ttu-id="75ec8-142">I vänster navigeringsfönstret, välj modul för köpruta.</span><span class="sxs-lookup"><span data-stu-id="75ec8-142">In the left navigation pane, select the buy box module.</span></span>
1. <span data-ttu-id="75ec8-143">I det högra navigeringsfönstret markerar du kryssrutan **Aktivera länken köp liknande produkter**.</span><span class="sxs-lookup"><span data-stu-id="75ec8-143">In the right navigation pane, select the **Enable Shop Similar Looks Link** check box.</span></span>
1. <span data-ttu-id="75ec8-144">Välj **Spara**, välj **Slutför redigering** för att checka in sidan och välj sedan **publicera** för att publicera den.</span><span class="sxs-lookup"><span data-stu-id="75ec8-144">Select **Save**, select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span> <span data-ttu-id="75ec8-145">När sidan har publicerats innehåller PDP en knapp för **köp liknande produkter**.</span><span class="sxs-lookup"><span data-stu-id="75ec8-145">After the page is published, the PDP will include a **Shop similar looks** button.</span></span>

<span data-ttu-id="75ec8-146">Bilden nedan visar kryssrutan **Aktivera länken köp liknande produkter** och knappen **köp liknande produkter** på en exempel PDP i webbplatsskaparen.</span><span class="sxs-lookup"><span data-stu-id="75ec8-146">The following illustration shows the **Enable Shop Similar Looks Link** check box and **Shop similar looks** button on an example PDP in site builder.</span></span>

![Aktivera länken köp liknande produkter och knappen köp liknande produkter på en PDP i webbplatsskaparen.](./media/SSLecomtooling.png)

## <a name="additional-resources"></a><span data-ttu-id="75ec8-148">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="75ec8-148">Additional resources</span></span>

[<span data-ttu-id="75ec8-149">Översikt av produktrekommendationer</span><span class="sxs-lookup"><span data-stu-id="75ec8-149">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="75ec8-150">Aktivera Azure Data Lake Storage i en Dynamics 365 Commerce-miljö</span><span class="sxs-lookup"><span data-stu-id="75ec8-150">Enable Azure Data Lake Storage in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="75ec8-151">Aktivera produktrekommendationer</span><span class="sxs-lookup"><span data-stu-id="75ec8-151">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="75ec8-152">Avanmäl anpassade rekommendationer</span><span class="sxs-lookup"><span data-stu-id="75ec8-152">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="75ec8-153">Lägg till produktrekommendationer i POS</span><span class="sxs-lookup"><span data-stu-id="75ec8-153">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="75ec8-154">Lägg till rekommendationer på transaktionsskärmen</span><span class="sxs-lookup"><span data-stu-id="75ec8-154">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="75ec8-155">Justera rekommendationsresultat från AI-ML</span><span class="sxs-lookup"><span data-stu-id="75ec8-155">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="75ec8-156">Skapa granskade rekommendationer manuellt</span><span class="sxs-lookup"><span data-stu-id="75ec8-156">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="75ec8-157">Skapa rekommendationer med demodata</span><span class="sxs-lookup"><span data-stu-id="75ec8-157">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="75ec8-158">Vanliga frågor om produktrekommendationer</span><span class="sxs-lookup"><span data-stu-id="75ec8-158">Product recommendations FAQ</span></span>](faq-recommendations.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
