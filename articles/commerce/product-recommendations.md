---
title: Översikt av produktrekommendationer
description: Det här ämnet innehåller allmän information om produktrekommendationer. Med produktrekommendationer kan kunderna enkelt och snabbt hitta produkter som de vill ha och till och med produkter som de ursprungligen inte hade tänkt att köpa.
author: Moonma
manager: AnnBe
ms.date: 03/19/2020
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
ms.author: moonma
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: e61136ed296d673e14600762c6f6199093530546
ms.sourcegitcommit: de5af1912201dd70aa85fdcad0b184c42405802e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/21/2020
ms.locfileid: "3154236"
---
# <a name="product-recommendations-overview"></a><span data-ttu-id="61fe9-104">Översikt av produktrekommendationer</span><span class="sxs-lookup"><span data-stu-id="61fe9-104">Product recommendations overview</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="61fe9-105">Microsoft Dynamics 365 Commerce kan användas för att visa produktrekommendationer på webbplatsen för e-handel och kassaenheten (POS).</span><span class="sxs-lookup"><span data-stu-id="61fe9-105">Microsoft Dynamics 365 Commerce can be used to show product recommendations on the e-Commerce website and point of sale (POS) device.</span></span> <span data-ttu-id="61fe9-106">Produktrekommendationer är artiklar som en kund kan vara intresserad av.</span><span class="sxs-lookup"><span data-stu-id="61fe9-106">Product recommendations are items that a customer might be interested in.</span></span> <span data-ttu-id="61fe9-107">Rekommendationerna bygger på de övriga kundernas inköpstrender i online- och fysiska butiker.</span><span class="sxs-lookup"><span data-stu-id="61fe9-107">The recommendations are based on the purchase trends of other customers in online and brick-and-mortar stores.</span></span>

<span data-ttu-id="61fe9-108">Med produktrekommendationer kan kunderna enkelt och snabbt hitta produkter som de vill ha medan de får en upplevelse som tjänar dem väl.</span><span class="sxs-lookup"><span data-stu-id="61fe9-108">Product recommendations allow customers to easily and quickly find products that they want while they have an experience that serves them well.</span></span> <span data-ttu-id="61fe9-109">Korsförsäljning och merförsäljning kan användas för att hjälpa kunder att hitta fler produkter än vad de ursprungligen avsåg att köpa.</span><span class="sxs-lookup"><span data-stu-id="61fe9-109">Cross-selling and upselling can even be used to assist customers find additional products that they didn't originally intend to buy.</span></span> <span data-ttu-id="61fe9-110">När rekommendationer används för att hjälpa till med produktidentifiering kan de skapa fler konverteringsmöjligheter, hjälpa till att öka försäljningsintäkterna och till och med öka kundens tillfredsställelse och kvarhållande.</span><span class="sxs-lookup"><span data-stu-id="61fe9-110">When recommendations are used to enhance product discovery, they create more conversion opportunities, help increase sales revenue, and even amplify customer satisfaction and retention.</span></span>

<span data-ttu-id="61fe9-111">I e-handel drivs produktrekommendationerna av Microsoft maskininlärningsteknik för rekommendationer i en stor skala.</span><span class="sxs-lookup"><span data-stu-id="61fe9-111">In e-Commerce, product recommendations are powered by Microsoft Recommendations machine learning technologies on a large scale.</span></span>

## <a name="recommendation-service"></a><span data-ttu-id="61fe9-112">Rekommendationstjänst</span><span class="sxs-lookup"><span data-stu-id="61fe9-112">Recommendation service</span></span>

<span data-ttu-id="61fe9-113">Tjänsten produktrekommendationer använder funktioner för artificiell intelligens och AI-ML (AI-ML) på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="61fe9-113">The product recommendations service utilizes artificial intelligence and machine learning (AI-ML) technologies in the following way:</span></span>

- <span data-ttu-id="61fe9-114">Data i det format som krävs av rekommendationstjänster extraheras från e-handelns driftsdatabas och skickas till Azure Data Lake Storage (ADSL) eller enhetslagringen.</span><span class="sxs-lookup"><span data-stu-id="61fe9-114">Data in the format that the Recommendation service requires is extracted from the Commerce operational database and sent to Azure data lake storage (ADLS) or Entity store.</span></span>
- <span data-ttu-id="61fe9-115">Rekommendationstjänsten använder lagrade data för att träna rekommendationsmodeller för listan **människor gillar också**, **köps ofta ihop**, **ny**, **bästsäljare** och **trend**.</span><span class="sxs-lookup"><span data-stu-id="61fe9-115">The recommendations service uses the stored data to train recommendation models for the **People also like**, **Frequently bought together**, **New**, **Best selling**, and **Trending** lists.</span></span>

## <a name="scenarios"></a><span data-ttu-id="61fe9-116">Scenarier</span><span class="sxs-lookup"><span data-stu-id="61fe9-116">Scenarios</span></span>

<span data-ttu-id="61fe9-117">Produktrekommendationer är tillgängliga för följande scenarier:</span><span class="sxs-lookup"><span data-stu-id="61fe9-117">Product recommendations are available for the following scenarios:</span></span>

- <span data-ttu-id="61fe9-118">**På valfri butikssida för bläddring eller landnings sida i e-handel:** Om kunder eller butikspartner besöker en butikssida kan rekommendationsmotorn föreslå produkter i listorna **Ny**. **Bästsäljande** och **Trend**.</span><span class="sxs-lookup"><span data-stu-id="61fe9-118">**On any store page for browsing or landing page in e-Commerce:** If customers or store associates visit a store page, the recommendation engine can suggest products in the **New**, **Best Selling**, and **Trending** lists.</span></span>
- <span data-ttu-id="61fe9-119">**På sidan produktinformation:** om kunder eller säljare besöker en sida med **produktinformation** föreslår rekommendationsmotorn ytterligare artiklar som troligen kommer att köpas.</span><span class="sxs-lookup"><span data-stu-id="61fe9-119">**On the Product details page:** If customers or store associates visit a **Product details** page, the recommendation engine suggests additional items that are also likely to be purchased.</span></span> <span data-ttu-id="61fe9-120">Dessa objekt visas i listan **människor gillar också**.</span><span class="sxs-lookup"><span data-stu-id="61fe9-120">These items appear in the **People also like** list.</span></span>
- <span data-ttu-id="61fe9-121">**På transaktionssidan eller på utcheckningssidan:** rekommendationsmotorn föreslår artiklar, baserat på den fullständiga listan med artiklar i varukorgen.</span><span class="sxs-lookup"><span data-stu-id="61fe9-121">**On the Transaction page or the checkout page:** The recommendation engine suggests items, based on the whole list of items in the basket.</span></span> <span data-ttu-id="61fe9-122">Dessa objekt visas i listan över **Köps ofta ihop**.</span><span class="sxs-lookup"><span data-stu-id="61fe9-122">These items appear in the **Frequently bought together** list.</span></span>
- <span data-ttu-id="61fe9-123">**Personliga rekommendationer:** inköpare kan ge de inloggade kunderna en anpassad **plockning för dig**, förutom nya funktioner som gör att befintliga listscenarier kan anpassas baserat på den kunden.</span><span class="sxs-lookup"><span data-stu-id="61fe9-123">**Personalized recommendations:** Merchandizers can provide signed-in customers a personalized **picks for you** list, in addition to new functionality that allows for existing list scenarios to be personalized based on that customer.</span></span> <span data-ttu-id="61fe9-124">Mer information finns i [Aktivera anpassade rekommendationer.](personalized-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="61fe9-124">To learn more, see [Enable personalized recommendations.](personalized-recommendations.md).</span></span>

### <a name="types-of-product-recommendations"></a><span data-ttu-id="61fe9-125">Typer av produktrekommendationer</span><span class="sxs-lookup"><span data-stu-id="61fe9-125">Types of product recommendations</span></span>

<span data-ttu-id="61fe9-126">I följande tabell beskrivs olika typer av automatiska produktrekommendationer som är tillgängliga för återförsäljare att implementera i deras Dynamics 365 Commerce-lösning via [modulen för produktinsamling](product-collection-module-overview.md).</span><span class="sxs-lookup"><span data-stu-id="61fe9-126">The following table describes various types of automated product recommendations available for retailers to implement in their Dynamics 365 Commerce solution via the [product collection module](product-collection-module-overview.md).</span></span> <span data-ttu-id="61fe9-127">Återförsäljare kan också visa anpassade resultat för en inloggad användare om webbplatsförfattaren väljer det alternativet.</span><span class="sxs-lookup"><span data-stu-id="61fe9-127">Retailers can also show personalized results for a signed-in user if the site author chooses that option.</span></span>

| <span data-ttu-id="61fe9-128">Produktsamlingsmodul</span><span class="sxs-lookup"><span data-stu-id="61fe9-128">Product collection module</span></span>  | <span data-ttu-id="61fe9-129">Typ</span><span class="sxs-lookup"><span data-stu-id="61fe9-129">Type</span></span> | <span data-ttu-id="61fe9-130">beskrivning</span><span class="sxs-lookup"><span data-stu-id="61fe9-130">Description</span></span> |
|----------------------------|------|-------------|
| <span data-ttu-id="61fe9-131">Nytt</span><span class="sxs-lookup"><span data-stu-id="61fe9-131">New</span></span>                        | <span data-ttu-id="61fe9-132">Algoritmiska</span><span class="sxs-lookup"><span data-stu-id="61fe9-132">Algorithmic</span></span> | <span data-ttu-id="61fe9-133">Den här modulen visar en lista över de senaste produkterna som har varit utvalda för kanaler och kataloger.</span><span class="sxs-lookup"><span data-stu-id="61fe9-133">This module shows a list of the newest products that have been recently assorted to channels and catalogs.</span></span> |
| <span data-ttu-id="61fe9-134">Bästsäljare</span><span class="sxs-lookup"><span data-stu-id="61fe9-134">Best selling</span></span>               | <span data-ttu-id="61fe9-135">Algoritmiska</span><span class="sxs-lookup"><span data-stu-id="61fe9-135">Algorithmic</span></span> | <span data-ttu-id="61fe9-136">Den här modulen visar en lista över produkter som rangordnas med det högsta antalet försäljningar.</span><span class="sxs-lookup"><span data-stu-id="61fe9-136">This module shows a list of products that are ranked by the highest number of sales.</span></span> |
| <span data-ttu-id="61fe9-137">Trend</span><span class="sxs-lookup"><span data-stu-id="61fe9-137">Trending</span></span>                   | <span data-ttu-id="61fe9-138">Algoritmiska</span><span class="sxs-lookup"><span data-stu-id="61fe9-138">Algorithmic</span></span> | <span data-ttu-id="61fe9-139">Den här modulen visar en lista över de produkter som har bäst prestanda för en viss period, rangordnade efter högsta antalet försäljningar.</span><span class="sxs-lookup"><span data-stu-id="61fe9-139">This module shows a list of the highest-performing products for a given period, ranked by highest number of sales.</span></span>  |
| <span data-ttu-id="61fe9-140">Ofta köpta tillsammans</span><span class="sxs-lookup"><span data-stu-id="61fe9-140">Frequently bought together</span></span> | <span data-ttu-id="61fe9-141">AI-ML</span><span class="sxs-lookup"><span data-stu-id="61fe9-141">AI-ML</span></span> | <span data-ttu-id="61fe9-142">Den här modulen rekommenderar en lista över produkter som vanligtvis köps tillsammans med innehållet i konsumenten aktuell kundvagn.</span><span class="sxs-lookup"><span data-stu-id="61fe9-142">This module recommends a list of products that are commonly purchased together with the contents of the consumers current cart.</span></span> |
| <span data-ttu-id="61fe9-143">Andra gillar också</span><span class="sxs-lookup"><span data-stu-id="61fe9-143">People also like</span></span>           | <span data-ttu-id="61fe9-144">AI-ML</span><span class="sxs-lookup"><span data-stu-id="61fe9-144">AI-ML</span></span> | <span data-ttu-id="61fe9-145">Den här modulen rekommenderar produkter för en given fröprodukt som baseras på konsument inköpsmönster.</span><span class="sxs-lookup"><span data-stu-id="61fe9-145">This module recommends products for a given seed product based on consumer purchase patterns.</span></span> |
| <span data-ttu-id="61fe9-146">Val för dig</span><span class="sxs-lookup"><span data-stu-id="61fe9-146">Picks for you</span></span>              | <span data-ttu-id="61fe9-147">AI-ML</span><span class="sxs-lookup"><span data-stu-id="61fe9-147">AI-ML</span></span> | <span data-ttu-id="61fe9-148">Den här modulen rekommenderar en anpassad lista över produkter som baseras på inköpsmönster för den inloggade användaren.</span><span class="sxs-lookup"><span data-stu-id="61fe9-148">This module recommends a personalized list of products based on purchase patterns of the signed-in user.</span></span> <span data-ttu-id="61fe9-149">För en gästanvändare kommer den här listan att döljas.</span><span class="sxs-lookup"><span data-stu-id="61fe9-149">For a guest user, this list will be collapsed.</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="61fe9-150">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="61fe9-150">Additional resources</span></span>

[<span data-ttu-id="61fe9-151">Aktivera ADLS i en Dynamics 365 Commerce-miljö</span><span class="sxs-lookup"><span data-stu-id="61fe9-151">Enable ADLS in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="61fe9-152">Aktivera produktrekommendationer</span><span class="sxs-lookup"><span data-stu-id="61fe9-152">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="61fe9-153">Aktivera anpassade rekommendationer</span><span class="sxs-lookup"><span data-stu-id="61fe9-153">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="61fe9-154">Avanmäl anpassade rekommendationer</span><span class="sxs-lookup"><span data-stu-id="61fe9-154">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="61fe9-155">Lägg till produktrekommendationer i kassan</span><span class="sxs-lookup"><span data-stu-id="61fe9-155">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="61fe9-156">Lägg till rekommendationer på transaktionsskärmen</span><span class="sxs-lookup"><span data-stu-id="61fe9-156">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="61fe9-157">Justera rekommendationsresultat från AI-ML</span><span class="sxs-lookup"><span data-stu-id="61fe9-157">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="61fe9-158">Skapa granskade rekommendationer manuellt</span><span class="sxs-lookup"><span data-stu-id="61fe9-158">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="61fe9-159">Skapa rekommendationer med demodata</span><span class="sxs-lookup"><span data-stu-id="61fe9-159">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="61fe9-160">Vanliga frågor om produktrekommendationer</span><span class="sxs-lookup"><span data-stu-id="61fe9-160">Product recommendations FAQ</span></span>](faq-recommendations.md)
