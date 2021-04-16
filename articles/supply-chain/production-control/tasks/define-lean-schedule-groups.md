---
title: Definiera resurssnåla schemagrupper
description: Resurssnåla schemagrupper definieras för att kunna gruppera och skilja grupper åt i kanban-planering.
author: cvocph
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LeanScheduleGroup, GanttColorTableLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 647e721a0616ceae387322517f2955d75c06bfd2
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5828764"
---
# <a name="define-lean-schedule-groups"></a><span data-ttu-id="0fd5c-103">Definiera resurssnåla schemagrupper</span><span class="sxs-lookup"><span data-stu-id="0fd5c-103">Define lean schedule groups</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="0fd5c-104">Resurssnåla schemagrupper definieras för att kunna gruppera och skilja grupper åt i kanban-planering.</span><span class="sxs-lookup"><span data-stu-id="0fd5c-104">Lean schedule groups are defined to group and distinguish products in kanban scheduling.</span></span> <span data-ttu-id="0fd5c-105">Grupperingen kan göras som en allmän association per företag eller specifik för en arbetsgrupp.</span><span class="sxs-lookup"><span data-stu-id="0fd5c-105">The grouping can be done as generic association per company or specific to a work cell.</span></span> <span data-ttu-id="0fd5c-106">Varje grupp har en färgkod för visuell indikation på kanban-planeringssidan.</span><span class="sxs-lookup"><span data-stu-id="0fd5c-106">Each group has a color code assigned for visual indication in the kanban scheduling listpage.</span></span> <span data-ttu-id="0fd5c-107">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="0fd5c-107">The demo data company used to create this procedure is USMF.</span></span>


## <a name="define-lean-scheduling-group"></a><span data-ttu-id="0fd5c-108">Definiera resurssnål schemagrupp</span><span class="sxs-lookup"><span data-stu-id="0fd5c-108">Define lean scheduling group</span></span>
1. <span data-ttu-id="0fd5c-109">Gå till Produktinformationshantering > Lean manufacturing > Resurssnåla schemagrupper.</span><span class="sxs-lookup"><span data-stu-id="0fd5c-109">Go to Product information management > Lean manufacturing > Lean schedule groups.</span></span>
2. <span data-ttu-id="0fd5c-110">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="0fd5c-110">Click New.</span></span>
3. <span data-ttu-id="0fd5c-111">Skriv ett värde i fältet Schemagrupp.</span><span class="sxs-lookup"><span data-stu-id="0fd5c-111">In the Schedule group field, type a value.</span></span>
    * <span data-ttu-id="0fd5c-112">En schemagrupp kan definieras som global grupp eller specifik för en arbetsgrupp.</span><span class="sxs-lookup"><span data-stu-id="0fd5c-112">A schedule group can be defined as global group or specific to a work cell.</span></span> <span data-ttu-id="0fd5c-113">I detta enkla exempel definierar vi en global grupp, och arbetsgruppen hålls tom.</span><span class="sxs-lookup"><span data-stu-id="0fd5c-113">In this simple example, we define a global group, and the work cell is kept empty.</span></span> <span data-ttu-id="0fd5c-114">Inställningarna för den här gruppen gäller alla arbetsgrupper som inte har specifika schemagrupper.</span><span class="sxs-lookup"><span data-stu-id="0fd5c-114">The settings of this group apply to all work cells that do not have specific schedule groups.</span></span>  
4. <span data-ttu-id="0fd5c-115">Välj en färg från färgvalet.</span><span class="sxs-lookup"><span data-stu-id="0fd5c-115">Select a color from the color selection.</span></span>
    * <span data-ttu-id="0fd5c-116">Färgerna används för att markera jobben på kanban-schemalistsidan eller kanban-processtavlan.</span><span class="sxs-lookup"><span data-stu-id="0fd5c-116">The colors are used to highlight the jobs on the kanban schedule list page or the kanban process board.</span></span>  
5. <span data-ttu-id="0fd5c-117">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="0fd5c-117">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="0fd5c-118">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="0fd5c-118">In the list, click the link in the selected row.</span></span>

## <a name="associate-product"></a><span data-ttu-id="0fd5c-119">Associera produkt</span><span class="sxs-lookup"><span data-stu-id="0fd5c-119">Associate product</span></span>
1. <span data-ttu-id="0fd5c-120">Koppla en specifik produkt</span><span class="sxs-lookup"><span data-stu-id="0fd5c-120">Associate a specific product</span></span>
    * <span data-ttu-id="0fd5c-121">Det går att associera produkter i resurssnåla schemagrupper på två sätt: antingen som en specifik produkt (artikelrelationtyp = artikel) eller som en del av en artikelallokeringsnyckel (artikelrelationtyp = grupp).</span><span class="sxs-lookup"><span data-stu-id="0fd5c-121">There are two ways to associate products to lean schedule groups, either as a specific product (Item relation type = Item) or as part of an item allocation key (item relation type = group).</span></span>    
2. <span data-ttu-id="0fd5c-122">Välj Artikel i fältet Artikelrelationstyp.</span><span class="sxs-lookup"><span data-stu-id="0fd5c-122">In the Item relation type field, select Item</span></span>
3. <span data-ttu-id="0fd5c-123">Skriv ett värde i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="0fd5c-123">In the Item number field, type a value.</span></span>
4. <span data-ttu-id="0fd5c-124">Ange ett värde i fältet Genomflödestakt.</span><span class="sxs-lookup"><span data-stu-id="0fd5c-124">In the Throughput ratio field, enter a number.</span></span>
    * <span data-ttu-id="0fd5c-125">Standardgenomflödestakten är 1, vilket innebär att de relaterade produkterna förbrukar exakt den kapacitet som anges i processaktiviteterna i produktionsflödet.</span><span class="sxs-lookup"><span data-stu-id="0fd5c-125">The default Throughput ratio is 1, which means that the related products consume exactly the capacity specified in the process activites of the production flows.</span></span> <span data-ttu-id="0fd5c-126">Genomflödestakt > 1 definierar en högre resursförbrukning och genomflödestakt > 1 en lägre förbrukning.</span><span class="sxs-lookup"><span data-stu-id="0fd5c-126">Throughput ratio > 1 defines a higher resource consumption, Throughput ratio < 1 defines a lower resource consumption.</span></span> <span data-ttu-id="0fd5c-127">Takten används i kostnadsberäkningen och i beräkningen av kanban-jobbförbrukningen.</span><span class="sxs-lookup"><span data-stu-id="0fd5c-127">The ratio is used in the cost calculation and in the calculation of the kanban job consumption.</span></span>  

## <a name="associate-item-allocation-key"></a><span data-ttu-id="0fd5c-128">Associera artikelallokeringsnyckel</span><span class="sxs-lookup"><span data-stu-id="0fd5c-128">Associate item allocation key</span></span>
1. <span data-ttu-id="0fd5c-129">Associera en artikelallokeringsnyckel</span><span class="sxs-lookup"><span data-stu-id="0fd5c-129">Associate an item allocation key</span></span>
    * <span data-ttu-id="0fd5c-130">Lägg till en association i en artikelallokeringsnyckel genom att använda artikelrelationtypgruppen.</span><span class="sxs-lookup"><span data-stu-id="0fd5c-130">Add an association to an item allocation key by using the Item relation type Group.</span></span>   <span data-ttu-id="0fd5c-131">Observera att en artikelallokeringsnyckel för prognoser måste vara definierad i dina data för den här processen.</span><span class="sxs-lookup"><span data-stu-id="0fd5c-131">Note that for this process, you need a forecast item alllocation key defined in your data.</span></span>  
2. <span data-ttu-id="0fd5c-132">Välj Grupp i fältet Artikelrelationstyp.</span><span class="sxs-lookup"><span data-stu-id="0fd5c-132">In the Item relation type field, select Group</span></span>
3. <span data-ttu-id="0fd5c-133">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Artikelallokeringsnyckel.</span><span class="sxs-lookup"><span data-stu-id="0fd5c-133">In the Item allocation key field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="0fd5c-134">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="0fd5c-134">In the list, click the link in the selected row.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]