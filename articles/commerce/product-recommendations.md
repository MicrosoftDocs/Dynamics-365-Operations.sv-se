---
title: Översikt av produktrekommendationer
description: Det här ämnet innehåller allmän information om produktrekommendationer. Med produktrekommendationer kan kunderna enkelt och snabbt hitta produkter som de vill ha och till och med produkter som de ursprungligen inte hade tänkt att köpa.
author: Moonma
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
ms.author: moonma
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: e249c7d450510a3a9a33158e9e1c33f832a1f91c
ms.sourcegitcommit: b5ecde955a69f577de46e7db10e89caaedeb2b49
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/04/2020
ms.locfileid: "3024989"
---
# <a name="product-recommendations-overview"></a><span data-ttu-id="d47ec-104">Översikt av produktrekommendationer</span><span class="sxs-lookup"><span data-stu-id="d47ec-104">Product recommendations overview</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="d47ec-105">Microsoft Dynamics 365 Commerce kan användas för att visa produktrekommendationer på webbplatsen för e-handel och kassaenheten (POS).</span><span class="sxs-lookup"><span data-stu-id="d47ec-105">Microsoft Dynamics 365 Commerce can be used to show product recommendations on the e-Commerce website and point of sale (POS) device.</span></span> <span data-ttu-id="d47ec-106">Produktrekommendationer är artiklar som en kund kan vara intresserad av.</span><span class="sxs-lookup"><span data-stu-id="d47ec-106">Product recommendations are items that a customer might be interested in.</span></span> <span data-ttu-id="d47ec-107">Rekommendationerna bygger på de övriga kundernas inköpstrender i online- och fysiska butiker.</span><span class="sxs-lookup"><span data-stu-id="d47ec-107">The recommendations are based on the purchase trends of other customers in online and brick-and-mortar stores.</span></span>

<span data-ttu-id="d47ec-108">Med produktrekommendationer kan kunderna enkelt och snabbt hitta produkter som de vill ha medan de får en upplevelse som tjänar dem väl.</span><span class="sxs-lookup"><span data-stu-id="d47ec-108">Product recommendations let customers easily and quickly find products that they want while they have an experience that serves them well.</span></span> <span data-ttu-id="d47ec-109">Korsförsäljning och merförsäljning kan användas för att hjälpa kunder att hitta fler produkter än vad de ursprungligen avsåg att köpa.</span><span class="sxs-lookup"><span data-stu-id="d47ec-109">Cross-selling and upselling can even be used to help customers find additional products than they didn't originally intend to buy.</span></span> <span data-ttu-id="d47ec-110">När rekommendationer används för att hjälpa till med produktidentifiering kan de skapa fler konverteringsmöjligheter, hjälpa till att öka försäljningsintäkterna och till och med öka kundens tillfredsställelse och kvarhållande.</span><span class="sxs-lookup"><span data-stu-id="d47ec-110">When recommendations are used to help with product discovery, they can create more conversion opportunities, help increase sales revenue, and even help enhance customer satisfaction and retention.</span></span>

<span data-ttu-id="d47ec-111">I handel drivs produktrekommendationerna av Microsoft maskininlärningsteknik för rekommendationer i en stor skala.</span><span class="sxs-lookup"><span data-stu-id="d47ec-111">In Commerce, product recommendations are powered by Microsoft Recommendations machine learning technologies on a large scale.</span></span>


## <a name="scenarios"></a><span data-ttu-id="d47ec-112">Scenarier</span><span class="sxs-lookup"><span data-stu-id="d47ec-112">Scenarios</span></span>

<span data-ttu-id="d47ec-113">Produktrekommendationer är tillgängliga för följande scenarier:</span><span class="sxs-lookup"><span data-stu-id="d47ec-113">Product recommendations are available for the following scenarios:</span></span>

- <span data-ttu-id="d47ec-114">**På valfri butikssida för bläddring eller landnings sida i e-handel:** Om kunder eller butikspartner besöker en butikssida kan rekommendationsmotorn föreslå produkter i listorna **Ny**. **Bästsäljande** och **Trend**.</span><span class="sxs-lookup"><span data-stu-id="d47ec-114">**On any store page for browsing or landing page in e-Commerce:** If customers or store associates visit a store page, the recommendation engine can suggest products in the **New**, **Best Selling**, and **Trending** lists.</span></span>
- <span data-ttu-id="d47ec-115">**På sidan produktinformation:** om kunder eller säljare besöker en sida med **produktinformation** föreslår rekommendationsmotorn ytterligare artiklar som troligen kommer att köpas.</span><span class="sxs-lookup"><span data-stu-id="d47ec-115">**On the Product details page:** If customers or store associates visit a **Product details** page, the recommendation engine suggests additional items that are also likely to be purchased.</span></span> <span data-ttu-id="d47ec-116">Dessa objekt visas i listan **människor gillar också**.</span><span class="sxs-lookup"><span data-stu-id="d47ec-116">These items appear in the **People also like** list.</span></span>
- <span data-ttu-id="d47ec-117">**På transaktionssidan eller på utcheckningssidan:** rekommendationsmotorn föreslår artiklar, baserat på den fullständiga listan med artiklar i varukorgen.</span><span class="sxs-lookup"><span data-stu-id="d47ec-117">**On the Transaction page or the checkout page:** The recommendation engine suggests items, based on the whole list of items in the basket.</span></span> <span data-ttu-id="d47ec-118">Dessa objekt visas i listan över **Köps ofta ihop**.</span><span class="sxs-lookup"><span data-stu-id="d47ec-118">These items appear in the **Frequently bought together** list.</span></span>
- <span data-ttu-id="d47ec-119">**Personliga rekommendationer:** inköpare kan ge de inloggade kunderna en anpassad **plockning för dig**, förutom nya funktioner som gör att befintliga listscenarier kan anpassas baserat på den kunden.</span><span class="sxs-lookup"><span data-stu-id="d47ec-119">**Personalized recommendations:** Merchandizers can provide signed-in customers a personalized **picks for you** list, in addition to new functionality that allows for existing list scenarios to be personalized based on that customer.</span></span> <span data-ttu-id="d47ec-120">Mer information finns i funktionen dokumentation: [aktivera personligt anpassade rekommendationer.](personalized-recommendations.md)</span><span class="sxs-lookup"><span data-stu-id="d47ec-120">To learn more, please see the feature documenation: [enable personalized recommedations.](personalized-recommendations.md)</span></span>

## <a name="recommendation-service"></a><span data-ttu-id="d47ec-121">Rekommendationstjänst</span><span class="sxs-lookup"><span data-stu-id="d47ec-121">Recommendation service</span></span>

<span data-ttu-id="d47ec-122">Produktrekommendationer använder rekommendationerna för maskininlärningstekniker på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="d47ec-122">Product recommendations use the Recommendations machine learning technologies in the following way:</span></span>

- <span data-ttu-id="d47ec-123">Data i det format som krävs av rekommendationstjänster extraheras från e-handelns driftsdatabas och skickas till enhetslagringen.</span><span class="sxs-lookup"><span data-stu-id="d47ec-123">Data in the format that the Recommendation service requires is extracted from the Commerce operational database and sent to the Entity store.</span></span>
- <span data-ttu-id="d47ec-124">Rekommendationstjänsten använder data för att träna rekommendationsmodeller för listan **människor gillar också**, **köps ofta ihop**, **ny**, **bästsäljare** och **trend**.</span><span class="sxs-lookup"><span data-stu-id="d47ec-124">The Recommendation service uses the data to train recommendation models for the **People also like**, **Frequently bought together**, **New**, **Best selling**, and **Trending** lists.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d47ec-125">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="d47ec-125">Additional resources</span></span>

[<span data-ttu-id="d47ec-126">Aktivera produktrekommendationer</span><span class="sxs-lookup"><span data-stu-id="d47ec-126">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="d47ec-127">Aktivera anpassade rekommendationer</span><span class="sxs-lookup"><span data-stu-id="d47ec-127">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="d47ec-128">Översikt över produktsamlingsmodul</span><span class="sxs-lookup"><span data-stu-id="d47ec-128">Product collection module overview</span></span>](product-collection-module-overview.md)

[<span data-ttu-id="d47ec-129">Skapa granskade listor över produktrekommendationer</span><span class="sxs-lookup"><span data-stu-id="d47ec-129">Create curated product recommendation lists</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="d47ec-130">Hantera AI-ML-baserade produktrekommendationsresultat</span><span class="sxs-lookup"><span data-stu-id="d47ec-130">Manage AI-ML-based product recommendation results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="d47ec-131">Lägg till produktrekommendationer på sidor</span><span class="sxs-lookup"><span data-stu-id="d47ec-131">Add product recommendation lists to pages</span></span>](add-reco-list-to-page.md)
