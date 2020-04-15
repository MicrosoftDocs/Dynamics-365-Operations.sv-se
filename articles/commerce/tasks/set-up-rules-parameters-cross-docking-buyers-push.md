---
title: " Ställ in regler och parametrar för direktleverans och centraliserad distribution"
description: I den här proceduren visas stegen för att skapa Påfyllnadsregler.
author: josaw1
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailReplenishmentRuleTable, RetailReplenishmentTreeLookup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9bccd92946783628dce37c3fd018e4dd927efd49
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "3141149"
---
# <a name="set-up-rules-and-parameters-for-cross-docking-and-buyers-push"></a><span data-ttu-id="46da4-103"> Ställ in regler och parametrar för direktleverans och centraliserad distribution</span><span class="sxs-lookup"><span data-stu-id="46da4-103">Set up rules and parameters for cross docking and buyer's push</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="46da4-104">I den här proceduren visas stegen för att skapa Påfyllnadsregler.</span><span class="sxs-lookup"><span data-stu-id="46da4-104">This procedure demonstrates the steps to create Replenishment rules.</span></span> <span data-ttu-id="46da4-105">Påfyllnadsregler kan användas för att styra hur produkter fördelas till butikerna när du använder direktleverans och centraliserad distribution.</span><span class="sxs-lookup"><span data-stu-id="46da4-105">Replenishment rules can be used to control how products are distributed to stores when using Cross-docking and Buyer´s push.</span></span> <span data-ttu-id="46da4-106">Påfyllnadsregler kan ställas in för butiker eller butiksgrupper.</span><span class="sxs-lookup"><span data-stu-id="46da4-106">Replenishment rules can be set up for stores or store groups.</span></span> <span data-ttu-id="46da4-107">Vikten som definieras för varje rad i en regel ska kontrollera kvantiteterna av hur produkter ska bli distribuerade mellan butiker när de använder påfyllnadsregler som fördelningsmetoden i direktleverans eller centraliserad distribution.</span><span class="sxs-lookup"><span data-stu-id="46da4-107">The weight defined for each line in a rule will control how the quantities of products will get distributed between the stores when using Replenishment rules as the distribution method in Cross-docking or Buyer´s push.</span></span> <span data-ttu-id="46da4-108">I den här proceduren används demonstrationsföretaget USRT.</span><span class="sxs-lookup"><span data-stu-id="46da4-108">This procedure uses the USRT demo company.</span></span>

1. <span data-ttu-id="46da4-109">Gå till Påfyllnadsregler.</span><span class="sxs-lookup"><span data-stu-id="46da4-109">Go to Replenishment rules.</span></span>
2. <span data-ttu-id="46da4-110">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="46da4-110">Click New.</span></span>
3. <span data-ttu-id="46da4-111">Ange ett värde i fältet Påfyllnadsregel.</span><span class="sxs-lookup"><span data-stu-id="46da4-111">In the Replenishment rule field, type a value.</span></span>
4. <span data-ttu-id="46da4-112">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="46da4-112">In the Description field, type a value.</span></span>
5. <span data-ttu-id="46da4-113">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="46da4-113">Click Save.</span></span>
6. <span data-ttu-id="46da4-114">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="46da4-114">Click Add.</span></span>
7. <span data-ttu-id="46da4-115">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="46da4-115">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="46da4-116">Du kan välja påfyllnadshierarki eller kanal för typen.</span><span class="sxs-lookup"><span data-stu-id="46da4-116">You can choose Replenishment hierarchy or Channel for the type.</span></span> <span data-ttu-id="46da4-117">Värdena styr om urvalet i Namn kommer att bli en hierarki med kanaler eller en specifik kanal.</span><span class="sxs-lookup"><span data-stu-id="46da4-117">The value controls whether the selection in Name will be a hierarchy of channels or a specific channel.</span></span>  <span data-ttu-id="46da4-118">Låt inställningen vara Återanskaffningshierarki i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="46da4-118">For this example, leave it set as Replenishment hierarchy.</span></span>  
8. <span data-ttu-id="46da4-119">Välj ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="46da4-119">In the Name field, select a value.</span></span>
    * <span data-ttu-id="46da4-120">Standardviktvärdet fylls i från den vikt som definieras på lagerstället.</span><span class="sxs-lookup"><span data-stu-id="46da4-120">The default weight value is populated from the weight defined on the warehouse.</span></span>  <span data-ttu-id="46da4-121">Vikten kan användas för en lagerpåfyllnadsregel eller så kan du ange en ny vikt i fältet Vikt.</span><span class="sxs-lookup"><span data-stu-id="46da4-121">This weight can be used for the Replenishment rule or you can enter a new weight in the Weight field.</span></span>  
9. <span data-ttu-id="46da4-122">Ange ett nummer i fältet Vikt.</span><span class="sxs-lookup"><span data-stu-id="46da4-122">In the Weight field, enter a number.</span></span>
10. <span data-ttu-id="46da4-123">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="46da4-123">Click Add.</span></span>
11. <span data-ttu-id="46da4-124">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="46da4-124">In the list, mark the selected row.</span></span>
12. <span data-ttu-id="46da4-125">Välj Kanal i fältet Typ.</span><span class="sxs-lookup"><span data-stu-id="46da4-125">In the Type field, select 'Channel'.</span></span>
13. <span data-ttu-id="46da4-126">Ange eller välj ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="46da4-126">In the Name field, enter or select a value.</span></span>
14. <span data-ttu-id="46da4-127">Ange ett nummer i fältet Vikt.</span><span class="sxs-lookup"><span data-stu-id="46da4-127">In the Weight field, enter a number.</span></span>
15. <span data-ttu-id="46da4-128">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="46da4-128">Click Save.</span></span>

