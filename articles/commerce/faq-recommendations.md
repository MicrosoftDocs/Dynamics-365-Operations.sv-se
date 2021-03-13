---
title: Vanliga frågor om produktrekommendationer
description: Det här avsnittet innehåller information om processer och verktyg som du kan använda för att felsöka problem som hör till produktrekommendationer eller deras resultat.
author: bebeale
manager: AnnBe
ms.date: 05/26/2020
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
ms.search.industry: Retail, Core, Operations
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 8eaebaf605cd53ce6848624169c3bbbd2a4281a5
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "5009909"
---
# <a name="product-recommendations-faq"></a><span data-ttu-id="86ac8-103">Vanliga frågor om produktrekommendationer</span><span class="sxs-lookup"><span data-stu-id="86ac8-103">Product recommendations FAQ</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="86ac8-104">Det här avsnittet innehåller information om processer och verktyg som du kan använda för att felsöka problem som hör till [produktrekommendationer](product-recommendations.md) eller deras resultat.</span><span class="sxs-lookup"><span data-stu-id="86ac8-104">This topic provides information about processes and tools that you can use to troubleshoot issues that are related to [product recommendations](product-recommendations.md) or their results.</span></span>

## <a name="best-practices"></a><span data-ttu-id="86ac8-105">Regelverk</span><span class="sxs-lookup"><span data-stu-id="86ac8-105">Best practices</span></span>
<span data-ttu-id="86ac8-106">Det är mycket viktigt att du använder begreppet produktmallar och varianter.</span><span class="sxs-lookup"><span data-stu-id="86ac8-106">It's very important to utilize the concept of product masters and variants.</span></span> <span data-ttu-id="86ac8-107">Vettig gruppering av varianter till en överordnad produktmall gör att listan över algoritmer och tjänster skapar bättre modeller.</span><span class="sxs-lookup"><span data-stu-id="86ac8-107">The sensible grouping of variants to a parent product master helps the list algorithms and service create better models.</span></span> <span data-ttu-id="86ac8-108">Dessutom kan tjänsten bara hantera en enda instans av en produkt i stället för att placera alla nära relaterade varianter i en lista.</span><span class="sxs-lookup"><span data-stu-id="86ac8-108">Additionally, the service can serve just one instance of a product instead of putting all closely related variants in a list.</span></span> <span data-ttu-id="86ac8-109">När alla nära relaterade varianter placeras i en lista, kan felaktiga eller dubbla resultat inträffa.</span><span class="sxs-lookup"><span data-stu-id="86ac8-109">When all closely related variants are put in a list, erroneous or duplicate results can occur.</span></span>

## <a name="why-are-products-missing-from-my-recommendation-lists"></a><span data-ttu-id="86ac8-110">Varför saknas produkter i mina rekommendationslistor?</span><span class="sxs-lookup"><span data-stu-id="86ac8-110">Why are products missing from my recommendation lists?</span></span>

<span data-ttu-id="86ac8-111">Om en artikel saknas i en lista över produktrekommendationer kan det finnas ett problem med produktkonfigurationen.</span><span class="sxs-lookup"><span data-stu-id="86ac8-111">Typically, if an item is missing from a product recommendation list, there might be a product configuration issue.</span></span> <span data-ttu-id="86ac8-112">Det kan till exempel vara fel på produktens startdatum eller slutdatum, en dimension kan vara felkonfigurerad eller produkten kanske inte är i rätt kanalsortiment, osv.</span><span class="sxs-lookup"><span data-stu-id="86ac8-112">For example, there might be an incorrect product start date or end date, a dimension might be misconfigured, or the product might not be in the correct channel assortment, etc.</span></span>

<span data-ttu-id="86ac8-113">Om en artikel saknas i en rekommendationslista som är baserad på artificiell intelligens (AI-ML), kanske objektet inte passar kriteriet i listan över rekommendationer eller så har det inte tillräckligt många inköpstransaktioner för att listan över rekommendationer ska visas filen.</span><span class="sxs-lookup"><span data-stu-id="86ac8-113">If an item is missing from a recommendation list that is based on artificial intelligence-machine learning (AI-ML), the item might not fit the criteria of the recommendation list, or it might not have enough purchase transactions for the recommendation list to show it.</span></span>

<span data-ttu-id="86ac8-114">Vi rekommenderar att du kontrollerar följande steg:</span><span class="sxs-lookup"><span data-stu-id="86ac8-114">We recommend that you check these steps:</span></span>
1. <span data-ttu-id="86ac8-115">**Kontrollera att produktrekommendationerna har aktiverats i huvudkontor.**</span><span class="sxs-lookup"><span data-stu-id="86ac8-115">**Make sure that product recommendations have been enabled in HQ.**</span></span> <span data-ttu-id="86ac8-116">Mer information om hur du aktiverar den här tjänsten finns i [Aktivera produktrekommendationer](enable-product-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="86ac8-116">For more information about how to enable this service, see [Enable product recommendations](enable-product-recommendations.md).</span></span>
1. <span data-ttu-id="86ac8-117">**Kontrollera att egenskaperna för nyckelprodukter är inställda.**</span><span class="sxs-lookup"><span data-stu-id="86ac8-117">**Make sure that key product properties are set.**</span></span> <span data-ttu-id="86ac8-118">Produktsortimenten måste till exempel vara inställda på **inkludera**.</span><span class="sxs-lookup"><span data-stu-id="86ac8-118">For example, product assortments must be set to **Include**.</span></span>
1. <span data-ttu-id="86ac8-119">**För nya, utvalda produkter kan det ta upp till 3 timmar innan produkten börjar visas i den nya listan.**</span><span class="sxs-lookup"><span data-stu-id="86ac8-119">**For newly assorted products, it might take up to 3 hours before the product will start appearing in the new list.**</span></span>
1. <span data-ttu-id="86ac8-120">**Om en produkt fortfarande inte visas i trenden, bästsäljare, människor gillar också eller ofta köpt tillsammans kan det hända att produkten inte har tillräckligt med transaktioner.**</span><span class="sxs-lookup"><span data-stu-id="86ac8-120">**If a product is still not appearing in Trending, Best selling, People also like, or Frequently bought together, then that product might not have enough transactions.**</span></span> <span data-ttu-id="86ac8-121">I detta fall kan du antingen vänta på att fler transaktioner ska uppträda, uppdatera standardparametrarna för rekommendationslistan eller använda manuella åtgärder för att ändra resultaten av en lista över produktrekommendationer.</span><span class="sxs-lookup"><span data-stu-id="86ac8-121">In this case, you can either wait for more transactions to occur, update the default recommendation list parameters, or use manual intervention to modify the recommendation product list results.</span></span> <span data-ttu-id="86ac8-122">Mer information om parametrar för rekommendationer finns i [hantera AI-ML-baserade resultat för produktrekommendationer](modify-product-recommendation-results.md).</span><span class="sxs-lookup"><span data-stu-id="86ac8-122">For more information about recommendation parameters, see [Manage AI-ML-based product recommendation results](modify-product-recommendation-results.md).</span></span>
1. <span data-ttu-id="86ac8-123">**Kontrollera att produkten uppfyller rekommendationskriterierna för listan.**</span><span class="sxs-lookup"><span data-stu-id="86ac8-123">**Make sure that the product meets the recommendation criteria for the list.**</span></span> <span data-ttu-id="86ac8-124">Mer information om parametrar för produktrekommendationer finns i [hantera AI-ML-baserade resultat för produktrekommendationer](modify-product-recommendation-results.md).</span><span class="sxs-lookup"><span data-stu-id="86ac8-124">For more information about product recommendation parameters, see [Manage AI-ML-based product recommendation results](modify-product-recommendation-results.md).</span></span>

## <a name="how-can-i-prevent-poor-recommendation-results-from-being-returned"></a><span data-ttu-id="86ac8-125">Hur kan jag förhindra att dåliga rekommendationsresultat returneras?</span><span class="sxs-lookup"><span data-stu-id="86ac8-125">How can I prevent poor recommendation results from being returned?</span></span>

<span data-ttu-id="86ac8-126">I rekommendationslistor krävs en stor mängd transaktioner för att ge resultaten.</span><span class="sxs-lookup"><span data-stu-id="86ac8-126">Recommendation lists require a large volume of transactions to produce results.</span></span> <span data-ttu-id="86ac8-127">Därför är det viktigt att användarna ger fullständiga historiska transaktionsdata.</span><span class="sxs-lookup"><span data-stu-id="86ac8-127">Therefore, it's important that users provide full historical transaction data.</span></span>

<span data-ttu-id="86ac8-128">Dessutom har produkter som inte har några transaktioner eller få transaktioner vanligtvis inte resultaten **Människor gillar också** eller **Ofta köpt tillsammans** och visas inte i rekommendationslistorna **Trender** eller **Bästsäljande**.</span><span class="sxs-lookup"><span data-stu-id="86ac8-128">Additionally, products that have no transactions or few transactions typically don't have **People also like** or **Frequently bought together** results, and don't appear in **Trending** or **Best selling** recommendation lists.</span></span> <span data-ttu-id="86ac8-129">Den här situationen kan ofta inträffa för mycket nya produkter eller för gamla produkter som har ett litet antal inköp.</span><span class="sxs-lookup"><span data-stu-id="86ac8-129">This situation can often occur for very new products, or for old products that have a small number of purchases.</span></span> <span data-ttu-id="86ac8-130">Populära nya objekt kan lätt lösa det här problemet.</span><span class="sxs-lookup"><span data-stu-id="86ac8-130">Popular new items will easily overcome this issue.</span></span>

<span data-ttu-id="86ac8-131">Vi rekommenderar att du följer dessa steg:</span><span class="sxs-lookup"><span data-stu-id="86ac8-131">We recommend that you follow these steps:</span></span>
1. <span data-ttu-id="86ac8-132">**Kontrollera att produkten uppfyller rekommendationskriterierna för listan.**</span><span class="sxs-lookup"><span data-stu-id="86ac8-132">**Make sure that the product meets the recommendation criteria for that list.**</span></span> <span data-ttu-id="86ac8-133">Mer information om parametrar för produktrekommendationer finns i ändra AI-ML-baserade resultat för produktrekommendationer.</span><span class="sxs-lookup"><span data-stu-id="86ac8-133">For more information about product recommendation parameters, see Modify AI-ML-based product recommendation results.</span></span>
1. <span data-ttu-id="86ac8-134">**Om produkten är ny bör du överväga att ändra en rekommendationslista tills produkten har fler transaktioner.**</span><span class="sxs-lookup"><span data-stu-id="86ac8-134">**If the product is new, consider modifying a recommendation list until the product has more transactions.**</span></span> <span data-ttu-id="86ac8-135">Mer information om hur du ändrar rekommendationslistans resultat finns i [hantera AI-ML-baserade resultat för produktrekommendationer](modify-product-recommendation-results.md).</span><span class="sxs-lookup"><span data-stu-id="86ac8-135">For more information about how to modify recommendation list results, see [Manage AI-ML-based product recommendation results](modify-product-recommendation-results.md).</span></span>


- <span data-ttu-id="86ac8-136">**Kontrollera att produkten uppfyller rekommendationskriterierna för listan.**</span><span class="sxs-lookup"><span data-stu-id="86ac8-136">**Make sure that the product meets the recommendation criteria for that list.**</span></span> <span data-ttu-id="86ac8-137">Mer information om parametrar för produktrekommendationer finns i [hantera AI-ML-baserade resultat för produktrekommendationer](modify-product-recommendation-results.md).</span><span class="sxs-lookup"><span data-stu-id="86ac8-137">For more information about product recommendation parameters, see [Manage AI-ML-based product recommendation results](modify-product-recommendation-results.md).</span></span>
- <span data-ttu-id="86ac8-138">**Om produkten är ny bör du överväga att ändra en rekommendationslista tills produkten har fler transaktioner**.</span><span class="sxs-lookup"><span data-stu-id="86ac8-138">**If the product is new, consider modifying a recommendation list until the product has more transactions**.</span></span> <span data-ttu-id="86ac8-139">Mer information om hur du ändrar rekommendationslistans resultat finns i [hantera AI-ML-baserade resultat för produktrekommendationer](modify-product-recommendation-results.md).</span><span class="sxs-lookup"><span data-stu-id="86ac8-139">For more information about how to modify recommendation list results, see [Manage AI-ML-based product recommendation results](modify-product-recommendation-results.md).</span></span>

## <a name="can-i-remove-a-product-but-still-see-it-in-the-store"></a><span data-ttu-id="86ac8-140">Kan jag ta bort en produkt men ändå se den i butiken?</span><span class="sxs-lookup"><span data-stu-id="86ac8-140">Can I remove a product but still see it in the store?</span></span>

<span data-ttu-id="86ac8-141">Du kan justera listor som kan genereras med algoritm om en verksamhet behöver uppstå.</span><span class="sxs-lookup"><span data-stu-id="86ac8-141">You can adjust lists that are algorithmically generated if a business need arises.</span></span> <span data-ttu-id="86ac8-142">Om en produkt tas bort från en rekommendationslista kommer produkten att fortsätta vara synlig i butiken.</span><span class="sxs-lookup"><span data-stu-id="86ac8-142">However, if a product is removed from a recommendation list, the product will remain discoverable in the store.</span></span> <span data-ttu-id="86ac8-143">Mer information om hur du ändrar produktrekommendationernas resultat finns i [hantera AI-ML-baserade resultat för produktrekommendationer](modify-product-recommendation-results.md).</span><span class="sxs-lookup"><span data-stu-id="86ac8-143">For more information about how to modify product recommendation results, see [Manage AI-ML-based product recommendation results](modify-product-recommendation-results.md).</span></span>

<span data-ttu-id="86ac8-144">Om du måste spärra en artikel från att upptäckas i butiken måste du ändra värdet **Artikelsortiment** till **Exkludera**.</span><span class="sxs-lookup"><span data-stu-id="86ac8-144">If you must block an item from being discovered in the store, you must change the **Item assortments** value to **Exclude**.</span></span>

## <a name="how-do-i-add-a-list-to-an-e-commerce-page"></a><span data-ttu-id="86ac8-145">Hur lägger jag till en lista på en näthandelssida?</span><span class="sxs-lookup"><span data-stu-id="86ac8-145">How do I add a list to an e-Commerce page?</span></span>

<span data-ttu-id="86ac8-146">Information om hur du lägger till produktrekommendationssidor på din näthandelssajt finns i [Lägga till listor över produktrekommendationer till sidor](add-reco-list-to-page.md).</span><span class="sxs-lookup"><span data-stu-id="86ac8-146">For information about how to add product recommendation pages to your e-Commerce website, see [Add product recommendation lists to pages](add-reco-list-to-page.md).</span></span>

## <a name="how-do-i-enable-recommendations-on-pos"></a><span data-ttu-id="86ac8-147">Hur aktiverar jag rekommendationer i POS?</span><span class="sxs-lookup"><span data-stu-id="86ac8-147">How do I enable recommendations on POS?</span></span>

<span data-ttu-id="86ac8-148">Efter att ha aktiverat produktrekommendationer måste du lägga till rekommendationspanelen till kassans kontrollskärm.</span><span class="sxs-lookup"><span data-stu-id="86ac8-148">After enabling product recommendations, you will need to add the recommendations panel to the control POS screen.</span></span> <span data-ttu-id="86ac8-149">För mer information, se [Lägg till en rekommendationskontroll på transaktionsskärmen på kassaenheter](add-recommendations-control-pos-screen.md).</span><span class="sxs-lookup"><span data-stu-id="86ac8-149">For more information, see [Add a recommendations control to the transaction screen on POS devices](add-recommendations-control-pos-screen.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="86ac8-150">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="86ac8-150">Additional resources</span></span>

[<span data-ttu-id="86ac8-151">Översikt av produktrekommendationer</span><span class="sxs-lookup"><span data-stu-id="86ac8-151">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="86ac8-152">Aktivera Azure Data Lake Storage i en Dynamics 365 Commerce-miljö</span><span class="sxs-lookup"><span data-stu-id="86ac8-152">Enable Azure Data Lake Storage in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="86ac8-153">Aktivera produktrekommendationer</span><span class="sxs-lookup"><span data-stu-id="86ac8-153">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="86ac8-154">Aktivera anpassade rekommendationer</span><span class="sxs-lookup"><span data-stu-id="86ac8-154">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="86ac8-155">Avanmäl anpassade rekommendationer</span><span class="sxs-lookup"><span data-stu-id="86ac8-155">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="86ac8-156">Aktivera rekommendationer för "köp liknande produkter"</span><span class="sxs-lookup"><span data-stu-id="86ac8-156">Enable "shop similar looks" recommendations</span></span>](shop-similar-looks.md)

[<span data-ttu-id="86ac8-157">Lägga till produktrekommendationer i POS</span><span class="sxs-lookup"><span data-stu-id="86ac8-157">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="86ac8-158">Lägg till rekommendationer på transaktionsskärmen</span><span class="sxs-lookup"><span data-stu-id="86ac8-158">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="86ac8-159">Justera rekommendationsresultat från AI-ML</span><span class="sxs-lookup"><span data-stu-id="86ac8-159">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="86ac8-160">Skapa granskade rekommendationer manuellt</span><span class="sxs-lookup"><span data-stu-id="86ac8-160">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="86ac8-161">Skapa rekommendationer med demodata</span><span class="sxs-lookup"><span data-stu-id="86ac8-161">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)
