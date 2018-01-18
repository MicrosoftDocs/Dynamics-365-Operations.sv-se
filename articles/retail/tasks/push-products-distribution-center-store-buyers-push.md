--- 
title: " Skjut produkter från distributionscenter till butik med centraliserad distribution"
description: "Den här proceduren går igenom stegen för att skapa och bearbeta en centraliserad distribution för att distribuera produkter från en plats till en eller flera butiker."
author: rubencdelgado
manager: AnnBe
ms.date: 02/17/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: d9b080ff46a0fbc73ed4f8fa3f03d71e9d758cc2
ms.openlocfilehash: fc14a4e013eadaa5b4b1df357f0c646ab68b6072
ms.contentlocale: sv-se
ms.lasthandoff: 01/18/2018

---
# <a name="push-products-from-distribution-center-to-store-using-buyers-push"></a><span data-ttu-id="9d9eb-103"> Skjut produkter från distributionscenter till butik med centraliserad distribution</span><span class="sxs-lookup"><span data-stu-id="9d9eb-103">Push products from distribution center to store using buyer's push</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="9d9eb-104">Den här proceduren går igenom stegen för att skapa och bearbeta en centraliserad distribution för att distribuera produkter från en plats till en eller flera butiker.</span><span class="sxs-lookup"><span data-stu-id="9d9eb-104">This procedure walks through the steps to create and process a Buyer´s push to distribute products from one location to one or many stores.</span></span> <span data-ttu-id="9d9eb-105">Användaren kan definiera flera konfigurationer och låta systemet att föreslå hur du fördelar produkterna, eller ange manuellt var produkterna fördelas till och hur mycket som distribueras till varje butik.</span><span class="sxs-lookup"><span data-stu-id="9d9eb-105">The user can define multiple configurations and have the system suggest how to distribute the products, or manually enter where the products are distributed to and how much gets distributed to each store.</span></span> <span data-ttu-id="9d9eb-106">Den här proceduren inkluderar inte inställningen av data som kan användas i centraliserad distribution, till exempel påfyllnadsregler, organisationshierarkier och butikvikter.</span><span class="sxs-lookup"><span data-stu-id="9d9eb-106">This procedure doesn't include setup of data that can be used in the Buyer´s push, such as replenishment rules, organizational hierarchies, and store weights.</span></span> <span data-ttu-id="9d9eb-107">I den här proceduren används demonstrationsföretaget USRT.</span><span class="sxs-lookup"><span data-stu-id="9d9eb-107">This procedure uses the USRT demo company.</span></span>

1. <span data-ttu-id="9d9eb-108">Gå till Centraliserad distribution.</span><span class="sxs-lookup"><span data-stu-id="9d9eb-108">Go to Buyer's push.</span></span>
2. <span data-ttu-id="9d9eb-109">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="9d9eb-109">Click New.</span></span>
3. <span data-ttu-id="9d9eb-110">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="9d9eb-110">In the Description field, type a value.</span></span>
4. <span data-ttu-id="9d9eb-111">Ange eller välj ett värde i fältet Plats.</span><span class="sxs-lookup"><span data-stu-id="9d9eb-111">In the Site field, enter or select a value.</span></span>
5. <span data-ttu-id="9d9eb-112">I fältet Lagerställe, ange eller välj ett lagerställe som har produkter med lagerbehållning.</span><span class="sxs-lookup"><span data-stu-id="9d9eb-112">In the Warehouse field, enter or select a warehouse that has products with on-hand quantities.</span></span>
6. <span data-ttu-id="9d9eb-113">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="9d9eb-113">Click Add.</span></span>
7. <span data-ttu-id="9d9eb-114">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="9d9eb-114">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="9d9eb-115">I fältet Artikelnummer, ange eller välj en produkt.</span><span class="sxs-lookup"><span data-stu-id="9d9eb-115">In the Item number field, enter or select a product.</span></span>
9. <span data-ttu-id="9d9eb-116">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="9d9eb-116">Click Add.</span></span>
10. <span data-ttu-id="9d9eb-117">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="9d9eb-117">In the list, mark the selected row.</span></span>
11. <span data-ttu-id="9d9eb-118">I fältet Artikelnummer, ange eller välj en variantprodukt.</span><span class="sxs-lookup"><span data-stu-id="9d9eb-118">In the Item number field, enter or select a variant product.</span></span>
    * <span data-ttu-id="9d9eb-119">När du anger en variantprodukt, rader skapas för varje variant.</span><span class="sxs-lookup"><span data-stu-id="9d9eb-119">When entering a variant product, lines will be created for each variant.</span></span>  
12. <span data-ttu-id="9d9eb-120">Markera en rad i listan.</span><span class="sxs-lookup"><span data-stu-id="9d9eb-120">In the list, mark a row.</span></span>
13. <span data-ttu-id="9d9eb-121">I fältet Distribuerad kvantitet, ange hur många av den valda produkten du vill distribuera.</span><span class="sxs-lookup"><span data-stu-id="9d9eb-121">In the Pushed quantity field, type how many of the selected product you want to distribute.</span></span>
14. <span data-ttu-id="9d9eb-122">I fältet Ytterligare kvantitet att distribuera, ange kvantiteten för de produkter som har tillgänglig kvantitet att distribuera.</span><span class="sxs-lookup"><span data-stu-id="9d9eb-122">In the Additional quantity to push field, enter the quantity of the products that have available quantity to distribute.</span></span>
15. <span data-ttu-id="9d9eb-123">I fältet Fördelning, ange Platsvikt.</span><span class="sxs-lookup"><span data-stu-id="9d9eb-123">In the Distribution field, enter 'Location weight'.</span></span>
    * <span data-ttu-id="9d9eb-124">Du kan välja de andra typerna om du vill använda andra regler för fördelningen.</span><span class="sxs-lookup"><span data-stu-id="9d9eb-124">You can select the other types to use other rules for the distribution.</span></span>  
16. <span data-ttu-id="9d9eb-125">I fältet Påfyllnadshierarki, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="9d9eb-125">In the Replenishment hierarchy field, select a value.</span></span>
17. <span data-ttu-id="9d9eb-126">Välj Ja i fältet Respektera sortiment.</span><span class="sxs-lookup"><span data-stu-id="9d9eb-126">Select Yes in the Respect assortments field.</span></span>
18. <span data-ttu-id="9d9eb-127">Klicka på Beräkna kvantiteter och granska de kvantiteter som läggs till för raderna i lagerställeavsnittet.</span><span class="sxs-lookup"><span data-stu-id="9d9eb-127">Click Calculate quantities and review the quantities that are added to the rows in the Warehouse section.</span></span>
19. <span data-ttu-id="9d9eb-128">Klicka på Skapa order.</span><span class="sxs-lookup"><span data-stu-id="9d9eb-128">Click Create order.</span></span>
20. <span data-ttu-id="9d9eb-129">Klicka på Ja.</span><span class="sxs-lookup"><span data-stu-id="9d9eb-129">Click Yes.</span></span>


