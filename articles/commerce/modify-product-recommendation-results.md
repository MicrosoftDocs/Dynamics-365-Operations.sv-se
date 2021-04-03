---
title: Justera AI-ML-baserade produktrekommendationsresultat
description: I det här avsnittet beskrivs hur du skräddarsyr resultat för produktrekommendationer baserat på maskininlärning med artificiell intelligens (AI-ML) till ditt företag.
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
ms.search.industry: Retail
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: b9e370faed7feb0640959a9fcc4b608f18f9ffc1
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5263956"
---
# <a name="adjust-ai-ml-based-product-recommendation-results"></a><span data-ttu-id="62fee-103">Justera AI-ML-baserade produktrekommendationsresultat</span><span class="sxs-lookup"><span data-stu-id="62fee-103">Adjust AI-ML-based product recommendation results</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="62fee-104">I det här avsnittet beskrivs hur du skräddarsyr resultat för produktrekommendationer baserat på maskininlärning med artificiell intelligens (AI-ML) till ditt företag.</span><span class="sxs-lookup"><span data-stu-id="62fee-104">This topic explains how to adjust product recommendation results based on artificial intelligence-machine learning (AI-ML) to your business.</span></span> 

<span data-ttu-id="62fee-105">När du har aktiverat produktrekommendationer börjar standardinställningarna att gälla. Dessa parametrar fungerar kanske för många behov.</span><span class="sxs-lookup"><span data-stu-id="62fee-105">After enabling product recommendations, the default settings will take effect; these parameters will work for may work for many needs.</span></span> <span data-ttu-id="62fee-106">Det är bäst att planera att ägna en stund åt att bedöma om resultatet passar produkternas försäljningsrörelse.</span><span class="sxs-lookup"><span data-stu-id="62fee-106">It is best to plan to spend some time evaluating whether the results fit the selling motion of products.</span></span> <span data-ttu-id="62fee-107">Vi föreslår utvärdering av resultat under några dagar innan parametrarna ändras efter behov innan de testas igen.</span><span class="sxs-lookup"><span data-stu-id="62fee-107">We suggest evaluating results for a few days before changing parameters as needed before testing again.</span></span> 

## <a name="understanding-recommendation-list-parameters"></a><span data-ttu-id="62fee-108">Förstå parametrar för rekommendationslista</span><span class="sxs-lookup"><span data-stu-id="62fee-108">Understanding recommendation list parameters</span></span>

<span data-ttu-id="62fee-109">Innan du ändrar parametrarna ska du lära dig hur de påverkar resultaten nedan.</span><span class="sxs-lookup"><span data-stu-id="62fee-109">Before changing the parameters, learn about how they will affect the results below.</span></span>

### <a name="trending-product-list"></a><span data-ttu-id="62fee-110">Produktlista för trender</span><span class="sxs-lookup"><span data-stu-id="62fee-110">"Trending" product list</span></span>

<span data-ttu-id="62fee-111">Produktlistan för trender har två parametrar som kan ändras:</span><span class="sxs-lookup"><span data-stu-id="62fee-111">The "Trending" product list has two parameters that can be changed:</span></span>

![Exempel på standardparameter för listan med trender](./media/exampletrendingparameters.png)

1. <span data-ttu-id="62fee-113">**Inkludera nya produkter från de senaste X dagarna** – produkter som har lagts till inom det angivna antalet dagar innan det aktuella datumet kan användas för att välja produktkandidater.</span><span class="sxs-lookup"><span data-stu-id="62fee-113">**Include new products from last X days** - Products that have been added within the specified number of days before the current date can be used to select product candidates.</span></span> <span data-ttu-id="62fee-114">Standardvärdet i bilden föreslår att produkter som är så gamla som 180 dagar kan användas i produktlistan för trender.</span><span class="sxs-lookup"><span data-stu-id="62fee-114">The default value in the picture suggests that products as old has 180 days can be used in the trending product list.</span></span>
1. <span data-ttu-id="62fee-115">**Inkludera nya försäljningar från de senaste X dagarna** – Försäljningstransaktioner som har inträffat till inom det angivna antalet dagar innan det aktuella datumet kan användas för att beställa produkterna.</span><span class="sxs-lookup"><span data-stu-id="62fee-115">**Include sales from last X days** - Sales transactions that have occurred within the specified number of days before the current date can be used to order the products.</span></span> <span data-ttu-id="62fee-116">Standardvärdet ovan innebär att alla inköp av en produkt under de senaste 30 dagarna ska användas för att fastställa produktens placering i produktlistan för trenden.</span><span class="sxs-lookup"><span data-stu-id="62fee-116">The default value above suggests that all purchases made of a product in the last 30 days would be used to determine the placement of the product in the trending product list.</span></span> 

### <a name="best-selling-product-list"></a><span data-ttu-id="62fee-117">Produktlistan bästsäljare</span><span class="sxs-lookup"><span data-stu-id="62fee-117">"Best selling" product list</span></span>

<span data-ttu-id="62fee-118">Beroende på din verksamhet kan listan bästsäljare få andra resultat än trender, även om de båda använder transaktionsdata för att beställa produkter.</span><span class="sxs-lookup"><span data-stu-id="62fee-118">Depending on your business, the "Best selling" list can bring different results than trending, even though they both use transaction data to order products.</span></span> <span data-ttu-id="62fee-119">Eftersom bästsäljare inte har något upphörande baserat på sortimentdatum, kan bästsäljare fortfarande markera mycket populära äldre produkter som har släppts från trendlistan.</span><span class="sxs-lookup"><span data-stu-id="62fee-119">Because best selling has no cut off based on assortment date, Best selling can still highlight very popular, older products that might have been dropped from the trending list.</span></span> 

<span data-ttu-id="62fee-120">Produktlistan bästsäljande har en parameter som kan ändras:</span><span class="sxs-lookup"><span data-stu-id="62fee-120">The "Best selling" product list has one parameter that can be changed:</span></span>

![Exempel på standardparameter för bästsäljarlista](./media/examplebestsellingparameters.PNG)

1. <span data-ttu-id="62fee-122">**Inkludera nya försäljningar från de senaste X dagarna** – Försäljningstransaktioner som har inträffat till inom det angivna antalet dagar innan det aktuella datumet kan användas för att beställa produkterna.</span><span class="sxs-lookup"><span data-stu-id="62fee-122">**Include sales from last X days** - Sales transactions that have occurred within the specified number of days before the current date can be used to order the products.</span></span> <span data-ttu-id="62fee-123">Standardvärdet ovan innebär att alla inköp av en produkt under de senaste 30 dagarna ska användas för att fastställa produktens placering i produktlistan för bästsäljare.</span><span class="sxs-lookup"><span data-stu-id="62fee-123">The default value above suggests that all purchases made of a product in the last 30 days would be used to determine the placement of the product in the Best selling product list.</span></span> 

## <a name="manually-add-or-remove-products-from-recommendation-lists"></a><span data-ttu-id="62fee-124">Lägga till eller ta bort produkter manuellt från rekommendationslistor</span><span class="sxs-lookup"><span data-stu-id="62fee-124">Manually add or remove products from recommendation lists</span></span>

### <a name="for-new-trending-or-best-selling-lists"></a><span data-ttu-id="62fee-125">För listorna ny, trend eller bästsäljare</span><span class="sxs-lookup"><span data-stu-id="62fee-125">For "New," "Trending," or "Best selling" lists</span></span>

1.  <span data-ttu-id="62fee-126">Gå till **Butik och handel** > **Produktrekommendationer** > **Rekommendationsparametrar**.</span><span class="sxs-lookup"><span data-stu-id="62fee-126">Go to **Retail and Commerce** > **Product recommendations** > **Recommendation parameters**.</span></span>
1.  <span data-ttu-id="62fee-127">I listan över delade parametrar, välj **Rekommendationslistor**.</span><span class="sxs-lookup"><span data-stu-id="62fee-127">In the list of shared parameters, select **Recommendation lists**.</span></span>
1.  <span data-ttu-id="62fee-128">Välj listan att lägga till eller ta bort produkter från.</span><span class="sxs-lookup"><span data-stu-id="62fee-128">Select the list add or remove products from.</span></span>
1.  <span data-ttu-id="62fee-129">För att lägga till produkter i tabellen, välj **Lägg till rad**.</span><span class="sxs-lookup"><span data-stu-id="62fee-129">To add products to the table, select **Add line.**</span></span> 
1.  <span data-ttu-id="62fee-130">Under kolumnen produkt, sök efter en produkt via **Namn** eller **Produktnummer.**</span><span class="sxs-lookup"><span data-stu-id="62fee-130">Under the Product column, search for a product by **Name** or **Product number.**</span></span>

    ![Exempel på sökning efter en produkt i den nya produktlistan](./media/examplenewlistconfiguration1.png)

1.  <span data-ttu-id="62fee-132">Välj ett av två alternativ under kolumnen Radtyp:</span><span class="sxs-lookup"><span data-stu-id="62fee-132">Under the Line type column, select one of two options:</span></span>
    -   <span data-ttu-id="62fee-133">**Inkludera** – framtvingar en produkt överst i listan</span><span class="sxs-lookup"><span data-stu-id="62fee-133">**Include** – forces a product to the front of the list</span></span>
    -   <span data-ttu-id="62fee-134">**Exkludera** – tar bort en produkt från listan</span><span class="sxs-lookup"><span data-stu-id="62fee-134">**Exclude** – removes a product from appearing in the list</span></span>
    
    ![Exempel på inkludering eller uteslutning av en produkt från den nya produktlistan](./media/examplenewlistconfiguration2.png)

1.  <span data-ttu-id="62fee-136">Att ändra **Visningsorder** ändrar ordningen där produkter som markerats **inkludera** visas i listan.</span><span class="sxs-lookup"><span data-stu-id="62fee-136">Changing the **Display order** will change the order that products marked **include** will appear in the list.</span></span>
    - <span data-ttu-id="62fee-137">Om två produkter har samma **visningsordningsvärde** kan den slutgiltiga ordningen på dessa två resultat skilja sig från backoffice.</span><span class="sxs-lookup"><span data-stu-id="62fee-137">If two products have the same **display order** value, then the final order of those two results may differ from the back office.</span></span>
1.  <span data-ttu-id="62fee-138">Så här tar du bort produkter från registret: Markera raden som du vill ta bort och välj **ta bort**.</span><span class="sxs-lookup"><span data-stu-id="62fee-138">To remove products from the table: select the line to remove and select **Remove**.</span></span>


### <a name="for-people-also-like-or-frequently-bought-together-lists"></a><span data-ttu-id="62fee-139">För listorna Människor gillar också eller Ofta köpt tillsammans</span><span class="sxs-lookup"><span data-stu-id="62fee-139">For "People also like" or "Frequently bought together" lists</span></span>

<span data-ttu-id="62fee-140">I samband med Ofta köpt tillsammans eller Människor gillar också används maskininlärning för att analysera konsumenternas inköpsmönster för att rekommendera relaterade produkter som vanligtvis köps tillsammans för en unik startprodukt.</span><span class="sxs-lookup"><span data-stu-id="62fee-140">In the context of "Frequently bought together" or "People also like" lists, machine learning is used to analyze consumer purchase patterns to recommend related products commonly purchased together for a unique seed product.</span></span> 
 
<span data-ttu-id="62fee-141">En *startprodukt* är den produkt som du vill generera resultat för.</span><span class="sxs-lookup"><span data-stu-id="62fee-141">A *seed product* is the product you want to generate results for.</span></span> <span data-ttu-id="62fee-142">I samband med att du manuellt justerar rekommendationslistor lägger du till eller tar bort resultat för den här produkten.</span><span class="sxs-lookup"><span data-stu-id="62fee-142">In the context of manually adjusting recommendation lists, you are adding or removing results for this product.</span></span> 

<span data-ttu-id="62fee-143">Följ dessa steg för att lägga till eller ta bort resultat för en startprodukt manuellt:</span><span class="sxs-lookup"><span data-stu-id="62fee-143">Follow these steps to manually add or remove results for a seed product:</span></span>
1.  <span data-ttu-id="62fee-144">Välj **startprodukt**.</span><span class="sxs-lookup"><span data-stu-id="62fee-144">Select the **Seed product**.</span></span> 
1.  <span data-ttu-id="62fee-145">Under kolumnen **produkt** sök efter en ny produkt efter **Namn** eller **Produktnummer.**
![Exempel på sökning efter en produkt i listan Ofta köpt tillsammans](./media/exampleFBTlistconfiguration1.png)</span><span class="sxs-lookup"><span data-stu-id="62fee-145">Under the **Product** column, search for a product by **Name** or **Product number.**
![Example of searching for a product on the Frequently bought together list](./media/exampleFBTlistconfiguration1.png)</span></span>
1. <span data-ttu-id="62fee-146">Välj ett av två alternativ under kolumnen **Radtyp**:</span><span class="sxs-lookup"><span data-stu-id="62fee-146">Under the **Line type** column, select one of two options:</span></span>
    - <span data-ttu-id="62fee-147">**Inkludera** – framtvingar en produkt överst i listan</span><span class="sxs-lookup"><span data-stu-id="62fee-147">**Include** – forces a product to the front of the list</span></span>
    - <span data-ttu-id="62fee-148">**Exkludera** – tar bort en produkt från listan</span><span class="sxs-lookup"><span data-stu-id="62fee-148">**Exclude** – removes a product from appearing in the list</span></span>     
<span data-ttu-id="62fee-149">![Exempel på inkludering eller exkludering av en produkt i listan som ofta köps ihop](./media/exampleFBTlistconfiguration2.png)</span><span class="sxs-lookup"><span data-stu-id="62fee-149">![Example of Including or Excluding a product on the Frequently bought together list](./media/exampleFBTlistconfiguration2.png)</span></span>
1.  <span data-ttu-id="62fee-150">Så här tar du bort produkter från registret: Markera raden som du vill ta bort och välj ta bort.</span><span class="sxs-lookup"><span data-stu-id="62fee-150">To remove products from the table: select the line to remove and select Remove.</span></span>


## <a name="additional-resources"></a><span data-ttu-id="62fee-151">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="62fee-151">Additional resources</span></span>

[<span data-ttu-id="62fee-152">Översikt av produktrekommendationer</span><span class="sxs-lookup"><span data-stu-id="62fee-152">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="62fee-153">Aktivera Azure Data Lake Storage i en Dynamics 365 Commerce-miljö</span><span class="sxs-lookup"><span data-stu-id="62fee-153">Enable Azure Data Lake Storage in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="62fee-154">Aktivera produktrekommendationer</span><span class="sxs-lookup"><span data-stu-id="62fee-154">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="62fee-155">Aktivera anpassade rekommendationer</span><span class="sxs-lookup"><span data-stu-id="62fee-155">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="62fee-156">Avanmäl anpassade rekommendationer</span><span class="sxs-lookup"><span data-stu-id="62fee-156">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="62fee-157">Aktivera rekommendationer för "köp liknande produkter"</span><span class="sxs-lookup"><span data-stu-id="62fee-157">Enable "shop similar looks" recommendations</span></span>](shop-similar-looks.md)

[<span data-ttu-id="62fee-158">Lägga till produktrekommendationer i POS</span><span class="sxs-lookup"><span data-stu-id="62fee-158">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="62fee-159">Lägg till rekommendationer på transaktionsskärmen</span><span class="sxs-lookup"><span data-stu-id="62fee-159">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="62fee-160">Skapa granskade rekommendationer manuellt</span><span class="sxs-lookup"><span data-stu-id="62fee-160">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="62fee-161">Skapa rekommendationer med demodata</span><span class="sxs-lookup"><span data-stu-id="62fee-161">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="62fee-162">Vanliga frågor om produktrekommendationer</span><span class="sxs-lookup"><span data-stu-id="62fee-162">Product recommendations FAQ</span></span>](faq-recommendations.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]