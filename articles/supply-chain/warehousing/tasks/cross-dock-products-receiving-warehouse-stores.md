---
title: Direktleverera produkter från det mottagande lagerstället till butiker
description: Den här proceduren går igenom stegen för att skapa och bearbeta en direktutleverans om du vill fördela produkter från inleveransplatsen för en inköpsorder till en eller flera butiker.
author: ShylaThompson
ms.date: 02/17/2016
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: RetailBuyersPushPerPackage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a7caec5329774baaa03c72f9236f8e3192399089
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5810400"
---
# <a name="cross-dock-products-from-receiving-warehouse-to-stores"></a><span data-ttu-id="13ac1-103">Direktleverera produkter från det mottagande lagerstället till butiker</span><span class="sxs-lookup"><span data-stu-id="13ac1-103">Cross-dock products from receiving warehouse to stores</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="13ac1-104">Den här proceduren går igenom stegen för att skapa och bearbeta en direktutleverans om du vill fördela produkter från inleveransplatsen för en inköpsorder till en eller flera butiker.</span><span class="sxs-lookup"><span data-stu-id="13ac1-104">This procedure walks through the steps to create and process a Cross-dock to distribute products from the receiving location of a purchase order to one or many stores.</span></span> <span data-ttu-id="13ac1-105">Användaren kan definiera flera konfigurationer och låta systemet att föreslå hur du fördelar produkterna, eller ange manuellt var produkterna fördelas till och hur mycket som distribueras till varje butik.</span><span class="sxs-lookup"><span data-stu-id="13ac1-105">The user can define multiple configurations and have the system suggest how to distribute the products, or manually enter where the products are distributed to and how much gets distributed to each store.</span></span> <span data-ttu-id="13ac1-106">Proceduren inkluderar inte inställningen av data som kan användas i direktutleveransen, till exempel påfyllnadsregler, organisationshierarkier och butikvikter.</span><span class="sxs-lookup"><span data-stu-id="13ac1-106">The procedure doesn't include setup of data that can be used in the Cross-dock, such as replenishment rules, organizational hierarchies, and store weights.</span></span> <span data-ttu-id="13ac1-107">Den här proceduren använder demonstrationsföretaget USRT.</span><span class="sxs-lookup"><span data-stu-id="13ac1-107">The procedure uses the USRT demo company.</span></span>

1. <span data-ttu-id="13ac1-108">Gå till Alla inköpsorder.</span><span class="sxs-lookup"><span data-stu-id="13ac1-108">Go to All purchase orders.</span></span>
2. <span data-ttu-id="13ac1-109">Välj en inköpsorder i listan och klicka på länken för att öppna ordern.</span><span class="sxs-lookup"><span data-stu-id="13ac1-109">Select a purchase order in the list and click the link to open the order.</span></span>
3. <span data-ttu-id="13ac1-110">Klicka på Butik och handel i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="13ac1-110">On the Action Pane, click Retail and Commerce.</span></span>
4. <span data-ttu-id="13ac1-111">Klicka på Direktleverans.</span><span class="sxs-lookup"><span data-stu-id="13ac1-111">Click Cross docking.</span></span>
5. <span data-ttu-id="13ac1-112">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="13ac1-112">Click Edit.</span></span>
    * <span data-ttu-id="13ac1-113">Kategorin kan användas för att filtrera artiklarna i avsnittet Rader.</span><span class="sxs-lookup"><span data-stu-id="13ac1-113">The category can be used to filter the items in the Lines section.</span></span>  
6. <span data-ttu-id="13ac1-114">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="13ac1-114">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="13ac1-115">I fältet Kvantitet för direktleverans, ange ett värde för att ange hur mycket av kvantiteten för inköpet av den valda produkten som ska fördelas.</span><span class="sxs-lookup"><span data-stu-id="13ac1-115">In the Cross docking quantity field, type a value to specify how much of the quantity being purchased of the selected product should be distributed.</span></span>
8. <span data-ttu-id="13ac1-116">I fältet Ytterligare direktleveranskvantitet, ange ett värde för att ange kvantiteterna att fördela för de tillgängliga produkterna som köps.</span><span class="sxs-lookup"><span data-stu-id="13ac1-116">In the Additional cross docking quantity field, enter a value to specify the quantities to distribute for the available products being purchased</span></span>
9. <span data-ttu-id="13ac1-117">I fältet Fördelning, ange Platsvikt.</span><span class="sxs-lookup"><span data-stu-id="13ac1-117">In the Distribution field, enter 'Location weight'.</span></span>
    * <span data-ttu-id="13ac1-118">Du kan välja de andra typerna om du vill använda andra regler för fördelningen.</span><span class="sxs-lookup"><span data-stu-id="13ac1-118">You can select the other types to use different rules for the distribution.</span></span>  
10. <span data-ttu-id="13ac1-119">I fältet Påfyllnadshierarki, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="13ac1-119">In the Replenishment hierarchy field, select a value.</span></span>
11. <span data-ttu-id="13ac1-120">Välj Ja i fältet Respektera sortiment.</span><span class="sxs-lookup"><span data-stu-id="13ac1-120">Select Yes in the Respect assortments field.</span></span>
12. <span data-ttu-id="13ac1-121">Klicka på Beräkna kvantiteter.</span><span class="sxs-lookup"><span data-stu-id="13ac1-121">Click Calculate quantities.</span></span>
13. <span data-ttu-id="13ac1-122">Klicka på Skapa order.</span><span class="sxs-lookup"><span data-stu-id="13ac1-122">Click Create order.</span></span>
14. <span data-ttu-id="13ac1-123">Klicka på Ja.</span><span class="sxs-lookup"><span data-stu-id="13ac1-123">Click Yes.</span></span>
15. <span data-ttu-id="13ac1-124">I listan, sök efter och välj ett lagerställe som har tagit emot produkter.</span><span class="sxs-lookup"><span data-stu-id="13ac1-124">In the list, find and select a warehouse that received products</span></span>
16. <span data-ttu-id="13ac1-125">Klicka på order för att visa de order som skapades för det valda lagerstället</span><span class="sxs-lookup"><span data-stu-id="13ac1-125">Click Order to view the orders that got created for the selected warehouse</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]