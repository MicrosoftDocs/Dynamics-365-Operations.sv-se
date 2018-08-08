---
title: Dimensionsbaserad produktkonfiguration
description: "Dimensionsbaserad produktkonfigurering motsvarar en enda lösning för att skapa många produktvarianter från en enda produktmall och dess strukturlista."
author: cvocph
manager: AnnBe
ms.date: 11/03/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BOMConfigRule, BOMTable, ConfigChooseFromRoute, ConfigGroup, ConfigHierarchy, EcoResDimensionBasedConfiguration
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 19821
ms.assetid: 4db9890b-306b-4be7-ba98-3be2094d561f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: eb2690ec5296f65430268a211108551348a4a060
ms.contentlocale: sv-se
ms.lasthandoff: 08/07/2018

---

# <a name="dimension-based-product-configuration"></a><span data-ttu-id="d8508-103">Dimensionsbaserad produktkonfiguration</span><span class="sxs-lookup"><span data-stu-id="d8508-103">Dimension-based product configuration</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d8508-104">Dimensionsbaserad produktkonfigurering motsvarar en enda lösning för att skapa många produktvarianter från en enda produktmall och dess strukturlista.</span><span class="sxs-lookup"><span data-stu-id="d8508-104">Dimension-based product configuration represents a simple solution for creating many product variants from a single product master and its bill of materials.</span></span>

<span data-ttu-id="d8508-105">Dimensionsbaserad produktkonfiguration är en av de tre inbyggda teknikerna för produktkonfigurationer.</span><span class="sxs-lookup"><span data-stu-id="d8508-105">Dimension-based product configuration is one of the three built-in product configuration technologies.</span></span> <span data-ttu-id="d8508-106">De två andra teknikerna är fördefinierade varianter och begränsningsbaserad konfiguration.</span><span class="sxs-lookup"><span data-stu-id="d8508-106">The two other technologies are predefined variants and constraint-based configuration.</span></span> <span data-ttu-id="d8508-107">Alla tre teknikerna använder en produktmall som startpunkt och gör att användaren kan skapa många produktvarianter av en produktmall.</span><span class="sxs-lookup"><span data-stu-id="d8508-107">All three technologies use a product master as the starting point and allow the user to create many product variants for one product master.</span></span>

## <a name="key-concepts"></a><span data-ttu-id="d8508-108">Viktiga begrepp</span><span class="sxs-lookup"><span data-stu-id="d8508-108">Key concepts</span></span>
<span data-ttu-id="d8508-109">Dimensionsbaserad produktkonfiguration baseras på följande viktiga begrepp:</span><span class="sxs-lookup"><span data-stu-id="d8508-109">Dimension-based product configuration is based on the following key concepts:</span></span>

-   <span data-ttu-id="d8508-110">Produktmallar</span><span class="sxs-lookup"><span data-stu-id="d8508-110">Product masters</span></span>
-   <span data-ttu-id="d8508-111">Konfigurationsproduktdimension</span><span class="sxs-lookup"><span data-stu-id="d8508-111">Configuration product dimension</span></span>
-   <span data-ttu-id="d8508-112">Konfigurationsgrupper</span><span class="sxs-lookup"><span data-stu-id="d8508-112">Configuration groups</span></span>
-   <span data-ttu-id="d8508-113">Strukturlista</span><span class="sxs-lookup"><span data-stu-id="d8508-113">Bill of materials (BOM)</span></span>
-   <span data-ttu-id="d8508-114">Konfigurationsflöde</span><span class="sxs-lookup"><span data-stu-id="d8508-114">Configuration route</span></span>
-   <span data-ttu-id="d8508-115">Konfigurationsregler</span><span class="sxs-lookup"><span data-stu-id="d8508-115">Configuration rules</span></span>

### <a name="product-masters"></a><span data-ttu-id="d8508-116">Produktmallar</span><span class="sxs-lookup"><span data-stu-id="d8508-116">Product masters</span></span>

<span data-ttu-id="d8508-117">En produktmall är startpunkten för alla produktkonfigurationer.</span><span class="sxs-lookup"><span data-stu-id="d8508-117">A product master is the starting point for any product configuration process.</span></span> <span data-ttu-id="d8508-118">Till den dimensionsbaserade produktkonfigurationen behöver du en produktmall med denna specifika konfigurationsteknik och en produktdimensionsgrupp som omfattar konfigurationsproduktdimensionen.</span><span class="sxs-lookup"><span data-stu-id="d8508-118">For the dimension-based product configuration, you need a product master with this particular configuration technology and a product dimension group that includes the configuration product dimension.</span></span>

### <a name="configuration-product-dimension"></a><span data-ttu-id="d8508-119">Konfigurationsproduktdimension</span><span class="sxs-lookup"><span data-stu-id="d8508-119">Configuration product dimension</span></span>

<span data-ttu-id="d8508-120">Konfigurationsproduktdimensionen används för att identifiera produktvarianter för en produktmall med den dimensionsbaserade konfigurationstekniken.</span><span class="sxs-lookup"><span data-stu-id="d8508-120">The configuration product dimension is used to identify the product variants for a product master with the dimension-based configuration technology.</span></span> <span data-ttu-id="d8508-121">Konfigurationsdimensionsvärdet anges av användaren och kan identifiera enskilda produktvarianter.</span><span class="sxs-lookup"><span data-stu-id="d8508-121">The configuration dimension value is entered by the user and should help to identify the individual product variants.</span></span>

### <a name="configuration-groups"></a><span data-ttu-id="d8508-122">Konfigurationsgrupper</span><span class="sxs-lookup"><span data-stu-id="d8508-122">Configuration groups</span></span>

<span data-ttu-id="d8508-123">Konfigurationsgrupper definieras i en central databas och kan användas för alla dimensionsbaserade produktkonfigurationsmodeller.</span><span class="sxs-lookup"><span data-stu-id="d8508-123">Configuration groups are defined in a central repository and can be used for all dimension-based product configuration models.</span></span> <span data-ttu-id="d8508-124">Konfigurationsgrupper associeras till enskilda strukturlisterader och innehåller tillsammans en grupp med rader som är ömsesidigt uteslutande.</span><span class="sxs-lookup"><span data-stu-id="d8508-124">Configuration groups are associated to the individual BOM lines and hold together a group of lines that are mutually exclusive.</span></span> <span data-ttu-id="d8508-125">Det innebär att det bara är en rad i en grupp som kan väljas för en enskild produktvariant.</span><span class="sxs-lookup"><span data-stu-id="d8508-125">This means that only one line in a group can be selected for a single product variant.</span></span>

### <a name="bill-of-materials-bom"></a><span data-ttu-id="d8508-126">Strukturlista</span><span class="sxs-lookup"><span data-stu-id="d8508-126">Bill of materials (BOM)</span></span>

<span data-ttu-id="d8508-127">Strukturlistan visar byggstenarna för en dimensionsbaserad produktkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="d8508-127">The BOM represent the building blocks for a dimension-based product configuration.</span></span> <span data-ttu-id="d8508-128">Den måste inkludera alla olika produkter som kan användas i en produktvariant.</span><span class="sxs-lookup"><span data-stu-id="d8508-128">It must include all the different products that can be used in any product variant.</span></span> <span data-ttu-id="d8508-129">Varje rad i strukturlistan kan referera till en konfigurationsgrupp.</span><span class="sxs-lookup"><span data-stu-id="d8508-129">Each line in the BOM can reference a configuration group.</span></span> <span data-ttu-id="d8508-130">Om en rad inte refererar till en konfigurationsgrupp, inkluderas den i alla produktvarianter.</span><span class="sxs-lookup"><span data-stu-id="d8508-130">If a line doesn’t reference a configuration group, it will be included in all product variants.</span></span>

### <a name="configuration-route"></a><span data-ttu-id="d8508-131">Konfigurationsflöde</span><span class="sxs-lookup"><span data-stu-id="d8508-131">Configuration route</span></span>

<span data-ttu-id="d8508-132">Konfigurationsflödet bestämmer ordningen på konfigurationsgrupperna som de visas för användaren under produktkonfigureringen.</span><span class="sxs-lookup"><span data-stu-id="d8508-132">The configuration route determines the sequence of the configuration groups, as they will be displayed to the user during the product configuration process.</span></span>

### <a name="configuration-rules"></a><span data-ttu-id="d8508-133">Konfigurationsregler</span><span class="sxs-lookup"><span data-stu-id="d8508-133">Configuration rules</span></span>

<span data-ttu-id="d8508-134">Konfigurationsreglerna representerar en mekanism för säkerställande av att en produkt som ingår i en konfigurationsgrupp i en strukturlista använder antingen ett inkludering eller ett uteslutande en produkt i en annan konfigurationsgrupp i samma strukturlista.</span><span class="sxs-lookup"><span data-stu-id="d8508-134">The configuration rules represent a mechanism for ensuring that a product included in one configuration group in a BOM enforces either an inclusion or an exclusion of a product in a different configuration group in the same BOM.</span></span>

## <a name="product-modeling-process"></a><span data-ttu-id="d8508-135">Produktmodellering</span><span class="sxs-lookup"><span data-stu-id="d8508-135">Product modeling process</span></span>
<span data-ttu-id="d8508-136">Den naturliga sekvensen för uppbyggnad av en produktmodell för en dimensionsbaserad produkt börjar med att definiera de relevanta konfigurationsgrupperna.</span><span class="sxs-lookup"><span data-stu-id="d8508-136">The natural sequence for building a product model for a dimension-based product starts with defining the relevant configuration groups.</span></span> <span data-ttu-id="d8508-137">Det är viktigt att se till att alla produkter som ska användas i strukturlistan har släppts till det företag som produktmodellen skapas för.</span><span class="sxs-lookup"><span data-stu-id="d8508-137">It is important to ensure that all products which will be used in the BOM have been released to the company that the product model is built for.</span></span> <span data-ttu-id="d8508-138">Med de här byggblocken på plats kan användaren skapa strukturen och tilldela konfigurationsgrupper till alla relevanta strukturlisterader.</span><span class="sxs-lookup"><span data-stu-id="d8508-138">With these building blocks in place, the user can create the BOM and assign configuration groups to all relevant BOM lines.</span></span> <span data-ttu-id="d8508-139">Ett konfigurationsflöde kan definieras för att beställa konfigurationsgrupperna i rätt ordning när strukturlistan är klar.</span><span class="sxs-lookup"><span data-stu-id="d8508-139">When the BOM is complete, a configuration route can be defined for ordering the configuration groups in the proper sequence.</span></span> <span data-ttu-id="d8508-140">[![Process för dimensionsbaserad produktmodellering](./media/dimension-based-product-modeling-process-v1.png)](./media/dimension-based-product-modeling-process-v1.png) Om det finns specifika produkter från andra konfigurationsgrupper som antingen måste eller absolut inte får användas tillsammans, kan du skapa konfigurationsregler som stärker dessa produktrelationer.</span><span class="sxs-lookup"><span data-stu-id="d8508-140">[![Dimension-based product modeling process](./media/dimension-based-product-modeling-process-v1.png)](./media/dimension-based-product-modeling-process-v1.png) If there are certain products from different configuration groups that either must or must not be used together, you can create configuration rules that will enforce these product relationships.</span></span> <span data-ttu-id="d8508-141">När strukturlistan har bundits tillsammans med en dimensionsbaserad produktmall via en strukturlisteversion, och båda har godkänts och aktiverats, kan du skapa produktkonfigurationer och ett namn för varje konfiguration.</span><span class="sxs-lookup"><span data-stu-id="d8508-141">After the BOM has been tied together with a dimension-based product master through a BOM version and both have been approved and activated, you can create product configurations and enter a name for each configuration.</span></span> <span data-ttu-id="d8508-142">Konfigurationerna kan definieras innan några transaktioner skapas, eller utföras när behovet av en viss konfiguration uppstår.</span><span class="sxs-lookup"><span data-stu-id="d8508-142">The configurations can be defined before any transactions are generated or it can be done when the need for a certain configuration occurs.</span></span>

### <a name="suggested-use"></a><span data-ttu-id="d8508-143">Möjliga användningsområden</span><span class="sxs-lookup"><span data-stu-id="d8508-143">Suggested use</span></span>

<span data-ttu-id="d8508-144">Dimensionsbaserad konfigurationsteknik används främst till produkter med begränsade varianter och där kombinationer av produktdimensionerna storlek, färg, utförande och konfiguration inte passar till att identifiera en viss produktvariant.</span><span class="sxs-lookup"><span data-stu-id="d8508-144">The dimension-based configuration technology is best used for products with limited variability and the combination of the standard product dimensions size, color, style, and configuration is unsuitable for identifying a specific product variant.</span></span> <span data-ttu-id="d8508-145">Ett exempel kan vara en cykel med ramhöjd, hjulstorlek, bromstyper och olika växlar.</span><span class="sxs-lookup"><span data-stu-id="d8508-145">An example could be bicycle with frame height, wheel size, brake types, and different gears.</span></span>

### <a name="next-step"></a><span data-ttu-id="d8508-146">Gå vidare</span><span class="sxs-lookup"><span data-stu-id="d8508-146">Next step</span></span> 

<span data-ttu-id="d8508-147">Följande åtta uppgiftsguider listas i den ordning som du bör slutföra dem i.</span><span class="sxs-lookup"><span data-stu-id="d8508-147">The following eight task guides are listed in the order in which you should complete them.</span></span> 

1.  [<span data-ttu-id="d8508-148">Skapa en dimensionsbaserad produktmall (uppgiftsguide)</span><span class="sxs-lookup"><span data-stu-id="d8508-148">Create a dimension-based product master (Task guide)</span></span>](tasks/create-dimension-based-product-master.md)
2.  [<span data-ttu-id="d8508-149">Frisläpp en dimensionsbaserad produktmall (uppgiftsguide)</span><span class="sxs-lookup"><span data-stu-id="d8508-149">Release a dimension-based product master (Task guide)</span></span>](tasks/release-dimension-based-product-master.md)
3.  [<span data-ttu-id="d8508-150">Slutför grundläggande inställningar för en frisläppt produktmall (uppgiftsguide)</span><span class="sxs-lookup"><span data-stu-id="d8508-150">Complete basic setup of a released product master (Task guide)</span></span>](tasks/complete-basic-setup-released-product-master.md)
4.  [<span data-ttu-id="d8508-151">Definiera konfigurationsgrupper (uppgiftsguide)</span><span class="sxs-lookup"><span data-stu-id="d8508-151">Define configuration groups (Task guide)</span></span>](tasks/define-configuration-groups.md)
5.  [<span data-ttu-id="d8508-152">Skapa en strukturlista för en dimensionsbaserad produktmall (uppgiftsguide)</span><span class="sxs-lookup"><span data-stu-id="d8508-152">Create a bill of materials for a dimension-based product master (Task guide)</span></span>](tasks/create-bill-materials-dimension-based-product-master.md)
6.  [<span data-ttu-id="d8508-153">Definiera konfigurationsflöden (uppgiftsguide)</span><span class="sxs-lookup"><span data-stu-id="d8508-153">Define configuration routes (Task guide)</span></span>](tasks/define-configuration-route.md)
7.  [<span data-ttu-id="d8508-154">Skapa konfigurationsregler (uppgiftsguide)</span><span class="sxs-lookup"><span data-stu-id="d8508-154">Create configuration rules (Task guide)</span></span>](tasks/create-configuration-rules.md)
8.  [<span data-ttu-id="d8508-155">Skapa dimensionsbaserade konfigurationer (uppgiftsguide)</span><span class="sxs-lookup"><span data-stu-id="d8508-155">Create dimension-based configurations (Task guide)</span></span>](tasks/create-dimension-based-configurations.md)


