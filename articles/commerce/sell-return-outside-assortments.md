---
title: Sälj och returnera produkter som inte ingår i sortimentet för en butik
description: Med Dynamics 365 Commerce kan du sälja och returnera produkter utanför sortiment.
author: pdp1207
manager: AnnBe
ms.date: 05/24/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailAssortmentDetails
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.search.region: Global
ms.search.industry: retail
ms.author: prabhup
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 18d91287bfdcca272b5dd5e8dc8e04b1fd937a6d
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5254707"
---
# <a name="sell-and-return-products-that-arent-part-of-a-stores-assortment"></a><span data-ttu-id="bd0ee-103">Sälj och returnera produkter som inte ingår i sortimentet för en butik</span><span class="sxs-lookup"><span data-stu-id="bd0ee-103">Sell and return products that aren't part of a store's assortment</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="bd0ee-104">Ett vanligt scenario för alla återförsäljare är att sälja produkter till sina kunder eller acceptera returer från kunderna, även om de inte saluför specialprodukter i sin butik (d.v.s. produkter som inte är utvalda till butiken).</span><span class="sxs-lookup"><span data-stu-id="bd0ee-104">A common scenario for any retailer is to sell products to their customers or accept returns from their customers even if they don't carry the specific products in their store (in other words, the products are not assorted to the store).</span></span>

<span data-ttu-id="bd0ee-105">Här följer några vanliga scenarier:</span><span class="sxs-lookup"><span data-stu-id="bd0ee-105">Here are some typical scenarios:</span></span>

+ <span data-ttu-id="bd0ee-106">En återförsäljaren saluför inte alla sina produkter i en specifik butik.</span><span class="sxs-lookup"><span data-stu-id="bd0ee-106">A retailer doesn't carry all its products in a specific store.</span></span> <span data-ttu-id="bd0ee-107">De återstående produkterna lagras i lagerstället.</span><span class="sxs-lookup"><span data-stu-id="bd0ee-107">The remaining products are stored in the warehouse.</span></span> <span data-ttu-id="bd0ee-108">Butiksbiträdet kan hjälpa kunden genom att söka eller leta efter produkter på lagret, lägga dem i kundvagnen och slutföra kassan genom att välja en leveransmetod, till exempel levereras till en adress från lagret eller låta kunden hämta produkten från den aktuella butiken eller från en annan butik.</span><span class="sxs-lookup"><span data-stu-id="bd0ee-108">The store associate can assist the customer by searching or browsing for the products in the warehouse, add them to the cart, and complete the checkout by selecting a delivery method, such as shipping to an address from the warehouse or letting the customer pick up the product from the current store or from another store.</span></span>
+ <span data-ttu-id="bd0ee-109">En återförsäljare saluför inte specialprodukter i butiken eller har dem inte i lager i butiken som kunden besökte, men produkterna finns i andra butiker.</span><span class="sxs-lookup"><span data-stu-id="bd0ee-109">A retailer doesn't carry specific products in the store or doesn't have them in stock at the store the customer visited, but the products are available in other stores.</span></span> <span data-ttu-id="bd0ee-110">Butiksbiträdet kan hjälpa kunden genom att söka eller leta efter produkterna i andra butiker, lägga till dem i kundvagnen och slutföra kassan genom att välja en leveransmetod.</span><span class="sxs-lookup"><span data-stu-id="bd0ee-110">The store associate can assist the customer by searching or browsing the products in the other store, add them to the cart, and complete the checkout by selecting a delivery method.</span></span>
+ <span data-ttu-id="bd0ee-111">En återförsäljare har många butiker i och runt en viss ort eller ett visst postnummer och vill inte tvinga kunder att returnera produkter till samma butik som de köpts in i.</span><span class="sxs-lookup"><span data-stu-id="bd0ee-111">A retailer has many stores in and around a specific city or zip code and doesn't want to force the customers to return products to the same store they were purchased in.</span></span> <span data-ttu-id="bd0ee-112">I stället kan kunderna returnera sina produkter i valfri butik.</span><span class="sxs-lookup"><span data-stu-id="bd0ee-112">Instead, customers can return products to any store.</span></span>

<span data-ttu-id="bd0ee-113">Dessa vanliga scenarier är tillgängliga för återförsäljare som använder Commerce.</span><span class="sxs-lookup"><span data-stu-id="bd0ee-113">Those common scenarios are available for retailers using Commerce.</span></span> <span data-ttu-id="bd0ee-114">Med Commerce kan du:</span><span class="sxs-lookup"><span data-stu-id="bd0ee-114">With Commerce, you can:</span></span>

+ <span data-ttu-id="bd0ee-115">Söka eller bläddra bland produkter i andra butiker.</span><span class="sxs-lookup"><span data-stu-id="bd0ee-115">Search or browse products at other stores.</span></span>
+ <span data-ttu-id="bd0ee-116">Söka eller bläddra i alla frisläppta produkter.</span><span class="sxs-lookup"><span data-stu-id="bd0ee-116">Search or browse all released products.</span></span>
+ <span data-ttu-id="bd0ee-117">Skapa cash-and-carry-transaktioner eller kundorder.</span><span class="sxs-lookup"><span data-stu-id="bd0ee-117">Create cash-and-carry transactions or customer orders.</span></span>
+ <span data-ttu-id="bd0ee-118">Välj leveransalternativ för kundorder.</span><span class="sxs-lookup"><span data-stu-id="bd0ee-118">Select delivery options for customer orders.</span></span>
+ <span data-ttu-id="bd0ee-119">Hämta produkter i den aktuella butiken eller i en annan butik.</span><span class="sxs-lookup"><span data-stu-id="bd0ee-119">Pick up products at the current store or another store.</span></span>
+ <span data-ttu-id="bd0ee-120">Avbryt en order i den aktuella butiken eller i en annan butik.</span><span class="sxs-lookup"><span data-stu-id="bd0ee-120">Cancel an order at the current store or another store.</span></span>
+ <span data-ttu-id="bd0ee-121">Returnera en order med eller utan kvitt i den aktuella butiken eller i en annan butik.</span><span class="sxs-lookup"><span data-stu-id="bd0ee-121">Return an order with or without the receipt at the current store or another store.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]