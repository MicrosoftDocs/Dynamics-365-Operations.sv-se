---
title: Fiktiva artiklar
description: "Det här avsnittet beskriver i detalj, hur radtypen Fiktiv kan användas för rader i en strukturlista (BOM) och en formel i Microsoft Dynamics 365 for Finance and Operations."
author: ShylaThompson
manager: AnnBe
ms.date: 06/15/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SysOperationTemplateForm
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 1705903
ms.search.region: Global
ms.author: shylaw
ms.search.validfrom: 
ms.dyn365.ops.version: 8.1
ms.translationtype: HT
ms.sourcegitcommit: c5d4fb53939d88fcb1bd83d70bc361ed9879f298
ms.openlocfilehash: a92dd82f309867586f047e0dfc36e452a44a0f9c
ms.contentlocale: sv-se
ms.lasthandoff: 10/01/2018

---

# <a name="phantom-items"></a><span data-ttu-id="2faa5-103">Fiktiva artiklar</span><span class="sxs-lookup"><span data-stu-id="2faa5-103">Phantom items</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2faa5-104">Det här avsnittet beskrivs i detalj, hur radtypen fiktiv kan användas för rader i en strukturlista (BOM) och en formel.</span><span class="sxs-lookup"><span data-stu-id="2faa5-104">This topic describes, in detail, how the Phantom line type can be used for the lines of a bill of materials (BOM) and a formula.</span></span> <span data-ttu-id="2faa5-105">I bilden nedan (a) är strukturlistan för produkt H och delar F och G och (b) flödesbladet för produkter H och del F.</span><span class="sxs-lookup"><span data-stu-id="2faa5-105">In the following illustration, (a) is the BOM for product H and parts F and G, and (b) is the route sheet for products H and part F.</span></span>

![Produkt H och del F](media/product-H-part-F.png)


<span data-ttu-id="2faa5-107">Illustrationen visar ett exempel på en strukturlista på två nivåer.</span><span class="sxs-lookup"><span data-stu-id="2faa5-107">This illustration shows an example of a BOM structure in two levels.</span></span> <span data-ttu-id="2faa5-108">Slutprodukten H representerar en produkt för en maskinsammansättning.</span><span class="sxs-lookup"><span data-stu-id="2faa5-108">Finished product H represents a product for a machine assembly.</span></span> <span data-ttu-id="2faa5-109">Maskinsammansättningen består av två delar, en elektrisk enhet (F) med två material (A och B) och en uppsättning förpackningsmaterial (G) som också har två material (C och D).</span><span class="sxs-lookup"><span data-stu-id="2faa5-109">The machine assembly consists of two parts, an electrical unit (F) that has two materials (A and B) and a group of packaging materials (G) that also has two materials (C and D).</span></span> <span data-ttu-id="2faa5-110">Ett annat material (E) används vid allmän sammansättning av maskinen.</span><span class="sxs-lookup"><span data-stu-id="2faa5-110">Another material (E) is used during the general assembly of the machine.</span></span>

![Produkt H och del F](media/product-H-part-B.png)

<span data-ttu-id="2faa5-112">Bilden ovan representerar teknikstrukturlistan för produkt H. Den här strukturen ger en bra översikt över delarna och komponenterna i maskinens övergripande sammansättning.</span><span class="sxs-lookup"><span data-stu-id="2faa5-112">The preceding illustration represents the Engineering BOM for product H. This structure provides a good overview of the parts and components of the overall machine assembly.</span></span> <span data-ttu-id="2faa5-113">Men även om produktutvecklare kanske föredrar att visa strukturlistan på detta sätt, kanske strukturen inte korrekt återger hur maskinen byggs i fabriken.</span><span class="sxs-lookup"><span data-stu-id="2faa5-113">However, although product designers might prefer to see the BOM represented in this way, this structure might not correctly represent the way that the machine is built on the shop floor.</span></span> 

<span data-ttu-id="2faa5-114">T.ex. teknikstrukturen i föregående illustration anger till exempel att den elektriska enheten F sammansätts som en separat del på en separat arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="2faa5-114">For example, the Engineering BOM in the preceding illustration indicates that electrical unit F is assembled as a separate part on a separate work order.</span></span> <span data-ttu-id="2faa5-115">Men i verkstaden kanske det anses mer optimalt att sammansätta den elektriska enheten som en del av hela maskinsammansättningen och inte som en separat arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="2faa5-115">However, on the shop floor, it might be judged more optimal to assemble the electrical unit as part of the overall machine assembly, not as a separate work order.</span></span>

<span data-ttu-id="2faa5-116">Teknikstrukturen indikerar också att del G är en separat del.</span><span class="sxs-lookup"><span data-stu-id="2faa5-116">This Engineering BOM also indicates that part G is a separate part.</span></span> <span data-ttu-id="2faa5-117">Men i den här strukturen representerar del G inte en fysisk del utan en samling av förpackningsmaterial.</span><span class="sxs-lookup"><span data-stu-id="2faa5-117">However, in this structure, part G doesn’t represent a physical part but a collection of packaging materials.</span></span> 

<span data-ttu-id="2faa5-118">Därför, även om en teknikstrukturlista ger bra värde för designen av en produkt och underhåll av den designen, den behöver inte vara det mest logiska sättet att stödja produktens tillverkningskörningsprocess.</span><span class="sxs-lookup"><span data-stu-id="2faa5-118">Therefore, although an Engineering BOM provides great value for the design of a product and maintenance of that design, it might not be the most logical way to support the manufacturing execution process of the product.</span></span> <span data-ttu-id="2faa5-119">Däremot representerar en tillverkningsstrukturlista det bästa sättet att skapa en produkt.</span><span class="sxs-lookup"><span data-stu-id="2faa5-119">By contrast, a Manufacturing BOM represents the best way to build a product.</span></span>

<span data-ttu-id="2faa5-120">Följande bild visar hur föregående teknikstrukturlista övergår till en tillverkningsstrukturlista.</span><span class="sxs-lookup"><span data-stu-id="2faa5-120">The following illustration shows how the preceding Engineering BOM is transitioned into a Manufacturing BOM.</span></span> <span data-ttu-id="2faa5-121">I den här illustrationen (a) är strukturlistan för produkt H och b flödesbladet för produkt H.</span><span class="sxs-lookup"><span data-stu-id="2faa5-121">In this illustration, (a) is the BOM for product H, and b is the route sheet for product H.</span></span>

<span data-ttu-id="2faa5-122">I den här strukturen kan du se att det inte finns några delar F och G och de material som dessa delar består av har upphöjts till nästa strukturlistenivå.</span><span class="sxs-lookup"><span data-stu-id="2faa5-122">In this structure, you can see that there is no notion of parts F and G, and the materials that these parts consist of have been elevated to the next BOM level.</span></span> 

<span data-ttu-id="2faa5-123">Till skillnad från teknikstrukturlistan som hade två operationsblad har tillverkningsstrukturlistan endast ett operationsblad.</span><span class="sxs-lookup"><span data-stu-id="2faa5-123">Unlike the Engineering BOM, which had two operations sheets, the Manufacturing BOM has only one operations sheet.</span></span> <span data-ttu-id="2faa5-124">Förpackningsoperationen som var kopplad till del G har också utökats och ingår nu i operationsbladet för produkt H. Sammansättningen av den elektriska enheten är den första operationen.</span><span class="sxs-lookup"><span data-stu-id="2faa5-124">The packaging operation that was linked to part G has also been elevated and is now part of the operations sheet for product H. The assembly of the electrical unit is the first operation.</span></span> <span data-ttu-id="2faa5-125">Denna order passar bra, eftersom enheten används i nästa operation som är maskinsammansättningen.</span><span class="sxs-lookup"><span data-stu-id="2faa5-125">This order makes good sense, because this unit is used in the next operation, which is the machine assembly.</span></span> <span data-ttu-id="2faa5-126">Den sista operationen är förpackningsoperationen som förbrukar två förpackningsmaterial (C och D).</span><span class="sxs-lookup"><span data-stu-id="2faa5-126">The last operation is the packaging operation, which consumes two packing materials (C and D).</span></span>

<span data-ttu-id="2faa5-127">I Microsoft Dynamics 365 for Finance and Operations aktiveras övergången mellan teknikstrukturlistan och tillverkningsstrukturlistan genom strukturlistans radtyp Fiktiv.</span><span class="sxs-lookup"><span data-stu-id="2faa5-127">In Microsoft Dynamics 365 for Finance and Operations, the transition between the Engineering BOM and the Manufacturing BOM is enabled through the Phantom BOM line type.</span></span> <span data-ttu-id="2faa5-128">Såsom begreppet ”fiktiv” anger, har delar F och G försvunnit under övergångsperioden mellan de två typerna av strukturlista.</span><span class="sxs-lookup"><span data-stu-id="2faa5-128">As the term “phantom” indicates, parts F and G have disappeared during the transition between the two BOM types.</span></span> <span data-ttu-id="2faa5-129">I det här exemplet används radtypen Fiktiv till strukturlisteraderna för delar F och G i teknikstrukturlistan.</span><span class="sxs-lookup"><span data-stu-id="2faa5-129">In this example, the Phantom line type is applied to the BOM lines for parts F and G in the Engineering BOM.</span></span> <span data-ttu-id="2faa5-130">När en produktions- eller batchorder skapas kopieras teknikstrukturlista till produktions- eller batchordern.</span><span class="sxs-lookup"><span data-stu-id="2faa5-130">When a production or batch order is created, the Engineering BOM is copied to the production or batch order.</span></span> <span data-ttu-id="2faa5-131">Sedan när ordern beräknas, sker övergången från teknikstrukturlistan till tillverkningsstrukturlistan enligt föregående illustrationer.</span><span class="sxs-lookup"><span data-stu-id="2faa5-131">Then, when the order is estimated, the transition from the Engineering BOM to the Manufacturing BOM occurs, as shown in the preceding illustrations.</span></span> <span data-ttu-id="2faa5-132">Från operationsbladet i den andra bilden inmatas förpackningsmaterialen C och D för operationen.</span><span class="sxs-lookup"><span data-stu-id="2faa5-132">From the operations sheet in the second illustration, packaging materials C and D are input for the operation.</span></span> 

## <a name="multilevel-phantom-bom-structures"></a><span data-ttu-id="2faa5-133">Fiktiva artikelstrukturlistor på flera nivåer</span><span class="sxs-lookup"><span data-stu-id="2faa5-133">Multilevel phantom BOM structures</span></span>
<span data-ttu-id="2faa5-134">Radtypen Fiktiv kan användas i strukturlistor på flera nivåer, vilket visas i följande illustration.</span><span class="sxs-lookup"><span data-stu-id="2faa5-134">The Phantom line type can be used in multilevel BOM structures, as shown in the following illustration.</span></span> <span data-ttu-id="2faa5-135">I den här illustrationen (a) är strukturlistan för produkt G och (b) flödesbladet för delar E och produkt G.</span><span class="sxs-lookup"><span data-stu-id="2faa5-135">In this illustration, (a) is the BOM for product G, and (b) is the route sheet for parts E and F and product G.</span></span> 

![Produkt G och del F med bladflöde](media/product-G-route-sheet-G.png)


<span data-ttu-id="2faa5-137">Följande bild visar den resulterande tillverkningsstrukturlistan och flödesbladet och strukturlisteraderna för delar E och F konfigureras så att radtypen är Fiktiv.</span><span class="sxs-lookup"><span data-stu-id="2faa5-137">The following illustration shows the resulting Manufacturing BOM and route sheet if the BOM lines for parts E and F are configured so that the line type is Phantom.</span></span> <span data-ttu-id="2faa5-138">I den här illustrationen (a) är strukturlistan för produkt G och (b) flödesbladet för produkt G.</span><span class="sxs-lookup"><span data-stu-id="2faa5-138">In this illustration, (a) is the BOM for product G, and (b) is the route sheet for product G.</span></span>

![Produkt G](media/product-G.png)


## <a name="phantom-and-route-network"></a><span data-ttu-id="2faa5-140">Fiktiv och flödesnätverk</span><span class="sxs-lookup"><span data-stu-id="2faa5-140">Phantom and route network</span></span>
<span data-ttu-id="2faa5-141">Fiktiva strukturlistor kan också användas för en strukturlista som har ett flödesnätverk.</span><span class="sxs-lookup"><span data-stu-id="2faa5-141">Phantom BOMs can also be used for a BOM that has a route network.</span></span> <span data-ttu-id="2faa5-142">I ett flödesnätverk körs en eller flera åtgärder parallellt.</span><span class="sxs-lookup"><span data-stu-id="2faa5-142">In a route network, one or more operations run in parallel.</span></span> <span data-ttu-id="2faa5-143">Nedan visas ett exempel på ett flödesnätverk som används i en strukturlista med flera nivåer.</span><span class="sxs-lookup"><span data-stu-id="2faa5-143">The following illustration shows an example of a route network that is used in a multilevel BOM.</span></span> <span data-ttu-id="2faa5-144">I den här illustrationen (a) är strukturlistan för produkt G och F och (b) flödesbladet för produkt G och del F som har flödesnätverk.</span><span class="sxs-lookup"><span data-stu-id="2faa5-144">In this illustration, (a) is the BOM for product G and part F, and (b) is the route sheet for product G and part F, which has a route network.</span></span>

![Produkt G och del F](media/product-G-part-F.png)


<span data-ttu-id="2faa5-146">I bilden nedan (a) är strukturlistan för produkt G och del F och (b) flödesbladet för produkt G och del F.</span><span class="sxs-lookup"><span data-stu-id="2faa5-146">In the following illustration, (a) is the BOM for product G and part F, and (b) is the route sheet for product G and part F.</span></span>

![Produkt G och del F med bladflöde](media/product-G-part-F-with-route-sheet.png)

