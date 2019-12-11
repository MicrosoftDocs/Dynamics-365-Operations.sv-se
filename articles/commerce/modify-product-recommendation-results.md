---
title: Hantera AI-ML-baserade produktrekommendationsresultat
description: I det här avsnittet beskrivs hur du skräddarsyr resultat för produktrekommendationer baserat på maskininlärning med artificiell intelligens (AI-ML) till ditt företag.
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
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 669b056c38614c8ac9be2d7b244a0ab0c73bc9f8
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770080"
---
# <a name="manage-ai-ml-based-product-recommendation-results"></a><span data-ttu-id="08678-103">Hantera AI-ML-baserade produktrekommendationsresultat</span><span class="sxs-lookup"><span data-stu-id="08678-103">Manage AI-ML-based product recommendation results</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="08678-104">I det här avsnittet beskrivs hur du skräddarsyr resultat för produktrekommendationer baserat på maskininlärning med artificiell intelligens (AI-ML) till ditt företag.</span><span class="sxs-lookup"><span data-stu-id="08678-104">This topic explains how to tailor product recommendation results based on artificial intelligence-machine learning (AI-ML) to your business.</span></span> 

<span data-ttu-id="08678-105">När du har aktiverat produktrekommendationer börjar standardinställningarna att gälla. Dessa parametrar fungerar kanske för många behov.</span><span class="sxs-lookup"><span data-stu-id="08678-105">After enabling product recommendations, the default settings will take effect; these parameters will work for may work for many needs.</span></span> <span data-ttu-id="08678-106">Det är bäst att planera att ägna en stund åt att bedöma om resultatet passar produkternas försäljningsrörelse.</span><span class="sxs-lookup"><span data-stu-id="08678-106">It is best to plan to spend some time evaluating whether the results fit the selling motion of products.</span></span> <span data-ttu-id="08678-107">Vi föreslår utvärdering av resultat under några dagar innan parametrarna ändras efter behov innan de testas igen.</span><span class="sxs-lookup"><span data-stu-id="08678-107">We suggest evaluating results for a few days before changing parameters as needed before testing again.</span></span> 

## <a name="understanding-recommendation-list-parameters"></a><span data-ttu-id="08678-108">Förstå parametrar för rekommendationslista</span><span class="sxs-lookup"><span data-stu-id="08678-108">Understanding recommendation list parameters</span></span>

<span data-ttu-id="08678-109">Innan du ändrar parametrarna ska du lära dig hur de påverkar resultaten nedan.</span><span class="sxs-lookup"><span data-stu-id="08678-109">Before changing the parameters, learn about how they will affect the results below.</span></span>

### <a name="trending-product-list"></a><span data-ttu-id="08678-110">Produktlista för trender</span><span class="sxs-lookup"><span data-stu-id="08678-110">Trending product list</span></span>

<span data-ttu-id="08678-111">Produktlistan **trender** har två parametrar som kan ändras: ![exempel på standardparametrar för trendlista](./media/exampletrendingparameters.png)</span><span class="sxs-lookup"><span data-stu-id="08678-111">The **Trending** product list has two parameters that can be changed: ![Example Trending list default parameters](./media/exampletrendingparameters.png)</span></span>
1. <span data-ttu-id="08678-112">**Inkludera nya produkter från de senaste X dagarna** – produkter som har lagts till inom det angivna antalet dagar innan det aktuella datumet kan användas för att välja produktkandidater.</span><span class="sxs-lookup"><span data-stu-id="08678-112">**Include new products from last X days** - Products that have been added within the specified number of days before the current date can be used to select product candidates.</span></span> <span data-ttu-id="08678-113">Standardvärdet i bilden föreslår att produkter som är så gamla som 180 dagar kan användas i produktlistan för trender.</span><span class="sxs-lookup"><span data-stu-id="08678-113">The default value in the picture suggests that products as old has 180 days can be used in the trending product list.</span></span>
1. <span data-ttu-id="08678-114">**Inkludera nya försäljningar från de senaste X dagarna** – Försäljningstransaktioner som har inträffat till inom det angivna antalet dagar innan det aktuella datumet kan användas för att beställa produkterna.</span><span class="sxs-lookup"><span data-stu-id="08678-114">**Include sales from last X days** - Sales transactions that have occurred within the specified number of days before the current date can be used to order the products.</span></span> <span data-ttu-id="08678-115">Standardvärdet ovan innebär att alla inköp av en produkt under de senaste 30 dagarna ska användas för att fastställa produktens placering i produktlistan för trenden.</span><span class="sxs-lookup"><span data-stu-id="08678-115">The default value above suggests that all purchases made of a product in the last 30 days would be used to determine the placement of the product in the trending product list.</span></span> 

### <a name="best-selling-product-list"></a><span data-ttu-id="08678-116">Produktlistan bästsäljare</span><span class="sxs-lookup"><span data-stu-id="08678-116">Best selling product list</span></span>

<span data-ttu-id="08678-117">Beroende på din verksamhet kan bästsäljare få andra resultat än trender, även om de båda använder transaktionsdata för att beställa produkter.</span><span class="sxs-lookup"><span data-stu-id="08678-117">Depending on your business, Best selling can bring different results than trending, even though they both use transaction data to order products.</span></span> <span data-ttu-id="08678-118">Eftersom bästsäljare inte har något upphörande baserat på sortimentdatum, kan bästsäljare fortfarande markera mycket populära äldre produkter som har släppts från trendlistan.</span><span class="sxs-lookup"><span data-stu-id="08678-118">Because best selling has no cut off based on assortment date, Best selling can still highlight very popular, older products that might have been dropped from the trending list.</span></span> 

<span data-ttu-id="08678-119">Produktlistan **bästsäljande** har en parameter som kan ändras:</span><span class="sxs-lookup"><span data-stu-id="08678-119">The **Best selling** product list has one parameter that can be changed:</span></span>

![Exempel på standardparameter för bästsäljarlista](./media/examplebestsellingparameters.PNG)
1. <span data-ttu-id="08678-121">**Inkludera nya försäljningar från de senaste X dagarna** – Försäljningstransaktioner som har inträffat till inom det angivna antalet dagar innan det aktuella datumet kan användas för att beställa produkterna.</span><span class="sxs-lookup"><span data-stu-id="08678-121">**Include sales from last X days** - Sales transactions that have occurred within the specified number of days before the current date can be used to order the products.</span></span> <span data-ttu-id="08678-122">Standardvärdet ovan innebär att alla inköp av en produkt under de senaste 30 dagarna ska användas för att fastställa produktens placering i produktlistan för bästsäljare.</span><span class="sxs-lookup"><span data-stu-id="08678-122">The default value above suggests that all purchases made of a product in the last 30 days would be used to determine the placement of the product in the Best selling product list.</span></span> 

## <a name="manually-add-or-remove-products-from-recommendation-lists"></a><span data-ttu-id="08678-123">Lägga till eller ta bort produkter manuellt från rekommendationslistor</span><span class="sxs-lookup"><span data-stu-id="08678-123">Manually add or remove products from recommendation lists</span></span>

### <a name="for-new-trending-or-best-selling"></a><span data-ttu-id="08678-124">För ny, trend eller bästsäljare</span><span class="sxs-lookup"><span data-stu-id="08678-124">For New, Trending, or Best selling</span></span>

1.  <span data-ttu-id="08678-125">Gå till **Butik** > **Produktrekommendationer** > **Rekommendationsparametrar**.</span><span class="sxs-lookup"><span data-stu-id="08678-125">Go to **Retail** > **Product recommendations** > **Recommendation parameters**.</span></span>
1.  <span data-ttu-id="08678-126">I listan över delade butiksparametrar, välj **Rekommendationslistor**.</span><span class="sxs-lookup"><span data-stu-id="08678-126">In the list of retail shared parameters, select **Recommendation lists**.</span></span>
1.  <span data-ttu-id="08678-127">Välj listan att lägga till eller ta bort produkter från.</span><span class="sxs-lookup"><span data-stu-id="08678-127">Select the list add or remove products from.</span></span>
1.  <span data-ttu-id="08678-128">För att lägga till produkter i tabellen, välj **Lägg till rad**.</span><span class="sxs-lookup"><span data-stu-id="08678-128">To add products to the table, select **Add line.**</span></span> 
1.  <span data-ttu-id="08678-129">Under kolumnen produkt, sök efter en ny produkt efter **Namn** eller **Produktnummer.**
![Exempel på sökning efter en produkt i listan Ny produkt](./media/examplenewlistconfiguration1.png)</span><span class="sxs-lookup"><span data-stu-id="08678-129">Under the Product column, search for a product by **Name** or **Product number.**
![Example of searching for a product on the New product list](./media/examplenewlistconfiguration1.png)</span></span>
1.  <span data-ttu-id="08678-130">Välj ett av två alternativ under kolumnen Radtyp:</span><span class="sxs-lookup"><span data-stu-id="08678-130">Under the Line type column, select one of two options:</span></span>
    -   <span data-ttu-id="08678-131">**Inkludera** – framtvingar en produkt överst i listan</span><span class="sxs-lookup"><span data-stu-id="08678-131">**Include** – forces a product to the front of the list</span></span>
    -   <span data-ttu-id="08678-132">**Exkludera** – tar bort en produkt från att visas i listan ![exempel på inkludering av eller exkludering av en produkt från den nya produktlistan](./media/examplenewlistconfiguration2.png)</span><span class="sxs-lookup"><span data-stu-id="08678-132">**Exclude** – removes a product from appearing in the list ![Example of Including or Excluding a product from the New product list](./media/examplenewlistconfiguration2.png)</span></span>
1.  <span data-ttu-id="08678-133">Att ändra **Visningsorder** ändrar ordningen där produkter som markerats **inkludera** visas i listan.</span><span class="sxs-lookup"><span data-stu-id="08678-133">Changing the **Display order** will change the order that products marked **include** will appear in the list.</span></span>
    - <span data-ttu-id="08678-134">Om två produkter har samma **visningsordningsvärde** kan den slutgiltiga ordningen på dessa två resultat skilja sig från backoffice.</span><span class="sxs-lookup"><span data-stu-id="08678-134">If two products have the same **display order** value, then the final order of those two results may differ from the back office.</span></span>
1.  <span data-ttu-id="08678-135">Så här tar du bort produkter från registret: Markera raden som du vill ta bort och välj **ta bort**.</span><span class="sxs-lookup"><span data-stu-id="08678-135">To remove products from the table: select the line to remove and select **Remove**.</span></span>


### <a name="for-people-also-like-or-frequently-bought-together-lists"></a><span data-ttu-id="08678-136">För listorna Människor gillar också eller Ofta köpt tillsammans</span><span class="sxs-lookup"><span data-stu-id="08678-136">For People also like or Frequently bought together lists</span></span>

<span data-ttu-id="08678-137">I samband med **Ofta köpt tillsammans** eller **Människor gillar också** används maskininlärning för att analysera konsumenternas inköpsmönster för att rekommendera relaterade produkter som vanligtvis köps tillsammans för en unik startprodukt.</span><span class="sxs-lookup"><span data-stu-id="08678-137">In the context of **Frequently bought together** or **People also like** lists, machine learning is used to analyze consumer purchase patterns to recommend related products commonly purchased together for a unique seed product.</span></span> 
 
<span data-ttu-id="08678-138">En **startprodukt** är den produkt som du vill generera resultat för.</span><span class="sxs-lookup"><span data-stu-id="08678-138">A **seed product** is the product you want to generate results for.</span></span> <span data-ttu-id="08678-139">I samband med att du manuellt justerar rekommendationslistor lägger du till eller tar bort resultat för den här produkten.</span><span class="sxs-lookup"><span data-stu-id="08678-139">In the context of manually adjusting recommendation lists, you are adding or removing results for this product.</span></span> 

<span data-ttu-id="08678-140">Följ dessa steg för att lägga till eller ta bort resultat för en startprodukt manuellt:</span><span class="sxs-lookup"><span data-stu-id="08678-140">Follow these steps to manually add or remove results for a seed product:</span></span>
1.  <span data-ttu-id="08678-141">Välj **startprodukt**.</span><span class="sxs-lookup"><span data-stu-id="08678-141">Select the **Seed product**.</span></span> 
1.  <span data-ttu-id="08678-142">Under kolumnen **produkt** sök efter en ny produkt efter **Namn** eller **Produktnummer.**
![Exempel på sökning efter en produkt i listan Ofta köpt tillsammans](./media/exampleFBTlistconfiguration1.png)</span><span class="sxs-lookup"><span data-stu-id="08678-142">Under the **Product** column, search for a product by **Name** or **Product number.**
![Example of searching for a product on the Frequently bought together list](./media/exampleFBTlistconfiguration1.png)</span></span>
1. <span data-ttu-id="08678-143">Välj ett av två alternativ under kolumnen **Radtyp**:</span><span class="sxs-lookup"><span data-stu-id="08678-143">Under the **Line type** column, select one of two options:</span></span>
    - <span data-ttu-id="08678-144">**Inkludera** – framtvingar en produkt överst i listan</span><span class="sxs-lookup"><span data-stu-id="08678-144">**Include** – forces a product to the front of the list</span></span>
    - <span data-ttu-id="08678-145">**Exkludera** – tar bort en produkt från listan</span><span class="sxs-lookup"><span data-stu-id="08678-145">**Exclude** – removes a product from appearing in the list</span></span>     
<span data-ttu-id="08678-146">![Exempel på inkludering eller exkludering av en produkt i listan som ofta köps ihop](./media/exampleFBTlistconfiguration2.png)</span><span class="sxs-lookup"><span data-stu-id="08678-146">![Example of Including or Excluding a product on the Frequently bought together list](./media/exampleFBTlistconfiguration2.png)</span></span>
1.  <span data-ttu-id="08678-147">Så här tar du bort produkter från registret: Markera raden som du vill ta bort och välj ta bort.</span><span class="sxs-lookup"><span data-stu-id="08678-147">To remove products from the table: select the line to remove and select Remove.</span></span>


## <a name="additional-resources"></a><span data-ttu-id="08678-148">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="08678-148">Additional resources</span></span>

[<span data-ttu-id="08678-149">Översikt av produktrekommendationer</span><span class="sxs-lookup"><span data-stu-id="08678-149">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="08678-150">Aktivera produktrekommendationer</span><span class="sxs-lookup"><span data-stu-id="08678-150">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="08678-151">Lägg till produktrekommendationer på sidor</span><span class="sxs-lookup"><span data-stu-id="08678-151">Add product recommendation lists to pages</span></span>](add-reco-list-to-page.md)
