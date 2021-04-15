---
title: " Ställ in regler och parametrar för direktleverans och centraliserad distribution"
description: I den här proceduren visas stegen för att skapa Påfyllnadsregler.
author: josaw1
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: RetailReplenishmentRuleTable, RetailReplenishmentTreeLookup
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a2d8e561273c2a573182259c2ceb45cebc072eca
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5804171"
---
# <a name="set-up-rules-and-parameters-for-cross-docking-and-buyers-push"></a><span data-ttu-id="9c7de-103"> Ställ in regler och parametrar för direktleverans och centraliserad distribution</span><span class="sxs-lookup"><span data-stu-id="9c7de-103">Set up rules and parameters for cross docking and buyer's push</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9c7de-104">I den här proceduren visas stegen för att skapa Påfyllnadsregler.</span><span class="sxs-lookup"><span data-stu-id="9c7de-104">This procedure demonstrates the steps to create Replenishment rules.</span></span> <span data-ttu-id="9c7de-105">Påfyllnadsregler kan användas för att styra hur produkter fördelas till butikerna när du använder direktleverans och centraliserad distribution.</span><span class="sxs-lookup"><span data-stu-id="9c7de-105">Replenishment rules can be used to control how products are distributed to stores when using Cross-docking and Buyer´s push.</span></span> <span data-ttu-id="9c7de-106">Påfyllnadsregler kan ställas in för butiker eller butiksgrupper.</span><span class="sxs-lookup"><span data-stu-id="9c7de-106">Replenishment rules can be set up for stores or store groups.</span></span> <span data-ttu-id="9c7de-107">Vikten som definieras för varje rad i en regel ska kontrollera kvantiteterna av hur produkter ska bli distribuerade mellan butiker när de använder påfyllnadsregler som fördelningsmetoden i direktleverans eller centraliserad distribution.</span><span class="sxs-lookup"><span data-stu-id="9c7de-107">The weight defined for each line in a rule will control how the quantities of products will get distributed between the stores when using Replenishment rules as the distribution method in Cross-docking or Buyer´s push.</span></span> <span data-ttu-id="9c7de-108">I den här proceduren används demonstrationsföretaget USRT.</span><span class="sxs-lookup"><span data-stu-id="9c7de-108">This procedure uses the USRT demo company.</span></span>

1. <span data-ttu-id="9c7de-109">Gå till Påfyllnadsregler.</span><span class="sxs-lookup"><span data-stu-id="9c7de-109">Go to Replenishment rules.</span></span>
2. <span data-ttu-id="9c7de-110">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="9c7de-110">Click New.</span></span>
3. <span data-ttu-id="9c7de-111">Ange ett värde i fältet Påfyllnadsregel.</span><span class="sxs-lookup"><span data-stu-id="9c7de-111">In the Replenishment rule field, type a value.</span></span>
4. <span data-ttu-id="9c7de-112">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="9c7de-112">In the Description field, type a value.</span></span>
5. <span data-ttu-id="9c7de-113">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="9c7de-113">Click Save.</span></span>
6. <span data-ttu-id="9c7de-114">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="9c7de-114">Click Add.</span></span>
7. <span data-ttu-id="9c7de-115">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="9c7de-115">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="9c7de-116">Du kan välja påfyllnadshierarki eller kanal för typen.</span><span class="sxs-lookup"><span data-stu-id="9c7de-116">You can choose Replenishment hierarchy or Channel for the type.</span></span> <span data-ttu-id="9c7de-117">Värdena styr om urvalet i Namn kommer att bli en hierarki med kanaler eller en specifik kanal.</span><span class="sxs-lookup"><span data-stu-id="9c7de-117">The value controls whether the selection in Name will be a hierarchy of channels or a specific channel.</span></span>  <span data-ttu-id="9c7de-118">Låt inställningen vara Återanskaffningshierarki i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="9c7de-118">For this example, leave it set as Replenishment hierarchy.</span></span>  
8. <span data-ttu-id="9c7de-119">Välj ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="9c7de-119">In the Name field, select a value.</span></span>
    * <span data-ttu-id="9c7de-120">Standardviktvärdet fylls i från den vikt som definieras på lagerstället.</span><span class="sxs-lookup"><span data-stu-id="9c7de-120">The default weight value is populated from the weight defined on the warehouse.</span></span>  <span data-ttu-id="9c7de-121">Vikten kan användas för en lagerpåfyllnadsregel eller så kan du ange en ny vikt i fältet Vikt.</span><span class="sxs-lookup"><span data-stu-id="9c7de-121">This weight can be used for the Replenishment rule or you can enter a new weight in the Weight field.</span></span>  
9. <span data-ttu-id="9c7de-122">Ange ett nummer i fältet Vikt.</span><span class="sxs-lookup"><span data-stu-id="9c7de-122">In the Weight field, enter a number.</span></span>
10. <span data-ttu-id="9c7de-123">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="9c7de-123">Click Add.</span></span>
11. <span data-ttu-id="9c7de-124">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="9c7de-124">In the list, mark the selected row.</span></span>
12. <span data-ttu-id="9c7de-125">Välj Kanal i fältet Typ.</span><span class="sxs-lookup"><span data-stu-id="9c7de-125">In the Type field, select 'Channel'.</span></span>
13. <span data-ttu-id="9c7de-126">Ange eller välj ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="9c7de-126">In the Name field, enter or select a value.</span></span>
14. <span data-ttu-id="9c7de-127">Ange ett nummer i fältet Vikt.</span><span class="sxs-lookup"><span data-stu-id="9c7de-127">In the Weight field, enter a number.</span></span>
15. <span data-ttu-id="9c7de-128">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="9c7de-128">Click Save.</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]