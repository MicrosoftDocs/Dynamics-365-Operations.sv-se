--- 
title: "Definiera resurssnåla schemagrupper"
description: "Resurssnåla schemagrupper definieras för att kunna gruppera och skilja grupper åt i kanban-planering."
author: cvocph
manager: AnnBe
ms.date: 11/03/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 3ce7185c68b6342c1eae9cc9568da4bf4cc72205
ms.contentlocale: sv-se
ms.lasthandoff: 08/07/2018

---
# <a name="define-lean-schedule-groups"></a><span data-ttu-id="e3e0d-103">Definiera resurssnåla schemagrupper</span><span class="sxs-lookup"><span data-stu-id="e3e0d-103">Define lean schedule groups</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e3e0d-104">Resurssnåla schemagrupper definieras för att kunna gruppera och skilja grupper åt i kanban-planering.</span><span class="sxs-lookup"><span data-stu-id="e3e0d-104">Lean schedule groups are defined to group and distinguish products in kanban scheduling.</span></span> <span data-ttu-id="e3e0d-105">Grupperingen kan göras som en allmän association per företag eller specifik för en arbetsgrupp.</span><span class="sxs-lookup"><span data-stu-id="e3e0d-105">The grouping can be done as generic association per company or specific to a work cell.</span></span> <span data-ttu-id="e3e0d-106">Varje grupp har en färgkod för visuell indikation på kanban-planeringssidan.</span><span class="sxs-lookup"><span data-stu-id="e3e0d-106">Each group has a color code assigned for visual indication in the kanban scheduling list page.</span></span> <span data-ttu-id="e3e0d-107">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="e3e0d-107">The demo data company used to create this procedure is USMF.</span></span>


## <a name="define-lean-scheduling-group"></a><span data-ttu-id="e3e0d-108">Definiera resurssnål schemagrupp</span><span class="sxs-lookup"><span data-stu-id="e3e0d-108">Define lean scheduling group</span></span>
1. <span data-ttu-id="e3e0d-109">Gå till Produktinformationshantering > Lean manufacturing > Resurssnåla schemagrupper.</span><span class="sxs-lookup"><span data-stu-id="e3e0d-109">Go to Product information management > Lean manufacturing > Lean schedule groups.</span></span>
2. <span data-ttu-id="e3e0d-110">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="e3e0d-110">Click New.</span></span>
3. <span data-ttu-id="e3e0d-111">Skriv ett värde i fältet Schemagrupp.</span><span class="sxs-lookup"><span data-stu-id="e3e0d-111">In the Schedule group field, type a value.</span></span>
    * <span data-ttu-id="e3e0d-112">En schemagrupp kan definieras som global grupp eller specifik för en arbetsgrupp.</span><span class="sxs-lookup"><span data-stu-id="e3e0d-112">A schedule group can be defined as global group or specific to a work cell.</span></span> <span data-ttu-id="e3e0d-113">I detta enkla exempel definierar vi en global grupp, och arbetsgruppen hålls tom.</span><span class="sxs-lookup"><span data-stu-id="e3e0d-113">In this simple example, we define a global group, and the work cell is kept empty.</span></span> <span data-ttu-id="e3e0d-114">Inställningarna för den här gruppen gäller alla arbetsgrupper som inte har specifika schemagrupper.</span><span class="sxs-lookup"><span data-stu-id="e3e0d-114">The settings of this group apply to all work cells that do not have specific schedule groups.</span></span>  
4. <span data-ttu-id="e3e0d-115">Välj en färg från färgvalet.</span><span class="sxs-lookup"><span data-stu-id="e3e0d-115">Select a color from the color selection.</span></span>
    * <span data-ttu-id="e3e0d-116">Färgerna används för att markera jobben på kanban-schemalistsidan eller kanban-processtavlan.</span><span class="sxs-lookup"><span data-stu-id="e3e0d-116">The colors are used to highlight the jobs on the kanban schedule list page or the kanban process board.</span></span>  
5. <span data-ttu-id="e3e0d-117">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="e3e0d-117">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="e3e0d-118">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="e3e0d-118">In the list, click the link in the selected row.</span></span>

## <a name="associate-product"></a><span data-ttu-id="e3e0d-119">Associera produkt</span><span class="sxs-lookup"><span data-stu-id="e3e0d-119">Associate product</span></span>
1. <span data-ttu-id="e3e0d-120">Koppla en specifik produkt</span><span class="sxs-lookup"><span data-stu-id="e3e0d-120">Associate a specific product</span></span>
    * <span data-ttu-id="e3e0d-121">Det går att associera produkter i resurssnåla schemagrupper på två sätt: antingen som en specifik produkt (artikelrelationtyp = artikel) eller som en del av en artikelallokeringsnyckel (artikelrelationtyp = grupp).</span><span class="sxs-lookup"><span data-stu-id="e3e0d-121">There are two ways to associate products to lean schedule groups, either as a specific product (Item relation type = Item) or as part of an item allocation key (item relation type = group).</span></span>    
2. <span data-ttu-id="e3e0d-122">Välj Artikel i fältet Artikelrelationstyp.</span><span class="sxs-lookup"><span data-stu-id="e3e0d-122">In the Item relation type field, select Item</span></span>
3. <span data-ttu-id="e3e0d-123">Skriv ett värde i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="e3e0d-123">In the Item number field, type a value.</span></span>
4. <span data-ttu-id="e3e0d-124">Ange ett värde i fältet Genomflödestakt.</span><span class="sxs-lookup"><span data-stu-id="e3e0d-124">In the Throughput ratio field, enter a number.</span></span>
    * <span data-ttu-id="e3e0d-125">Standardgenomflödestakten är 1, vilket innebär att de relaterade produkterna förbrukar exakt den kapacitet som anges i processaktiviteterna i produktionsflödet.</span><span class="sxs-lookup"><span data-stu-id="e3e0d-125">The default Throughput ratio is 1, which means that the related products consume exactly the capacity specified in the process activities of the production flows.</span></span> <span data-ttu-id="e3e0d-126">Genomflödestakt > 1 definierar en högre resursförbrukning och genomflödestakt > 1 en lägre förbrukning.</span><span class="sxs-lookup"><span data-stu-id="e3e0d-126">Throughput ratio > 1 defines a higher resource consumption, Throughput ratio < 1 defines a lower resource consumption.</span></span> <span data-ttu-id="e3e0d-127">Takten används i kostnadsberäkningen och i beräkningen av kanban-jobbförbrukningen.</span><span class="sxs-lookup"><span data-stu-id="e3e0d-127">The ratio is used in the cost calculation and in the calculation of the kanban job consumption.</span></span>  

## <a name="associate-item-allocation-key"></a><span data-ttu-id="e3e0d-128">Associera artikelallokeringsnyckel</span><span class="sxs-lookup"><span data-stu-id="e3e0d-128">Associate item allocation key</span></span>
1. <span data-ttu-id="e3e0d-129">Associera en artikelallokeringsnyckel</span><span class="sxs-lookup"><span data-stu-id="e3e0d-129">Associate an item allocation key</span></span>
    * <span data-ttu-id="e3e0d-130">Lägg till en association i en artikelallokeringsnyckel genom att använda artikelrelationtypgruppen.</span><span class="sxs-lookup"><span data-stu-id="e3e0d-130">Add an association to an item allocation key by using the Item relation type Group.</span></span>   <span data-ttu-id="e3e0d-131">Observera att en artikelallokeringsnyckel för prognoser måste vara definierad i dina data för den här processen.</span><span class="sxs-lookup"><span data-stu-id="e3e0d-131">Note that for this process, you need a forecast item allocation key defined in your data.</span></span>  
2. <span data-ttu-id="e3e0d-132">Välj Grupp i fältet Artikelrelationstyp.</span><span class="sxs-lookup"><span data-stu-id="e3e0d-132">In the Item relation type field, select Group</span></span>
3. <span data-ttu-id="e3e0d-133">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Artikelallokeringsnyckel.</span><span class="sxs-lookup"><span data-stu-id="e3e0d-133">In the Item allocation key field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="e3e0d-134">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="e3e0d-134">In the list, click the link in the selected row.</span></span>


