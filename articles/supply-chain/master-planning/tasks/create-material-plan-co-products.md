--- 
title: "Skapa en materialplan för samprodukter"
description: "Produktionsplaneraren planerar materialbehoven för de artiklar som är samprodukter för formeln."
author: YuyuScheller
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: f3a411e8fc773957b5ce3f24749242d9d0c6ffd0
ms.contentlocale: sv-se
ms.lasthandoff: 05/08/2018

---
# <a name="create-a-material-plan-for-co-products"></a><span data-ttu-id="2cf18-103">Skapa en materialplan för samprodukter</span><span class="sxs-lookup"><span data-stu-id="2cf18-103">Create a material plan for co-products</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="2cf18-104">Produktionsplaneraren planerar materialbehoven för de artiklar som är samprodukter för formeln.</span><span class="sxs-lookup"><span data-stu-id="2cf18-104">The production planner plans the material requirements for items that are formula co-products.</span></span> <span data-ttu-id="2cf18-105">Det demonstrationsdataföretag som används för att skapa den här proceduren är USP2.</span><span class="sxs-lookup"><span data-stu-id="2cf18-105">The demo data company used to create this procedure is USP2.</span></span>


## <a name="create-requirement-for-a-co-product"></a><span data-ttu-id="2cf18-106">Skapa behov för en samprodukt</span><span class="sxs-lookup"><span data-stu-id="2cf18-106">Create requirement for a co-product</span></span>
1. <span data-ttu-id="2cf18-107">Gå till standardinstrumentpanelen.</span><span class="sxs-lookup"><span data-stu-id="2cf18-107">Go to Default dashboard.</span></span>
2. <span data-ttu-id="2cf18-108">Klicka på Bearbetning och förfrågan om försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="2cf18-108">Click Sales order processing and inquiry.</span></span>
3. <span data-ttu-id="2cf18-109">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="2cf18-109">Click New.</span></span>
4. <span data-ttu-id="2cf18-110">Klicka på Försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="2cf18-110">Click Sales order.</span></span>
5. <span data-ttu-id="2cf18-111">Ange ett värde i fältet Kundkonto.</span><span class="sxs-lookup"><span data-stu-id="2cf18-111">In the Customer account field, type a value.</span></span>
    * <span data-ttu-id="2cf18-112">Exempel: US-001</span><span class="sxs-lookup"><span data-stu-id="2cf18-112">Example: US-001</span></span>  
6. <span data-ttu-id="2cf18-113">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="2cf18-113">Click OK.</span></span>
7. <span data-ttu-id="2cf18-114">Skriv ett värde i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="2cf18-114">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="2cf18-115">Exempel: P6003</span><span class="sxs-lookup"><span data-stu-id="2cf18-115">Example: P6003</span></span>  
8. <span data-ttu-id="2cf18-116">Ange ett tal i fältet Kvantitet.</span><span class="sxs-lookup"><span data-stu-id="2cf18-116">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="2cf18-117">Exempel: 50 000</span><span class="sxs-lookup"><span data-stu-id="2cf18-117">Example: 50000</span></span>  
9. <span data-ttu-id="2cf18-118">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="2cf18-118">Click Save.</span></span>

## <a name="create-a-material-plan-for-co-products"></a><span data-ttu-id="2cf18-119">Skapa en materialplan för samprodukter</span><span class="sxs-lookup"><span data-stu-id="2cf18-119">Create a material plan for co-products</span></span>
1. <span data-ttu-id="2cf18-120">Klcka på Huvudplanering.</span><span class="sxs-lookup"><span data-stu-id="2cf18-120">Click Master planning.</span></span>
2. <span data-ttu-id="2cf18-121">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Plan.</span><span class="sxs-lookup"><span data-stu-id="2cf18-121">In the Plan field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="2cf18-122">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="2cf18-122">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="2cf18-123">Exempel: MasterPlan</span><span class="sxs-lookup"><span data-stu-id="2cf18-123">Example: MasterPlan</span></span>  
4. <span data-ttu-id="2cf18-124">Klicka på Kör.</span><span class="sxs-lookup"><span data-stu-id="2cf18-124">Click Run.</span></span>
5. <span data-ttu-id="2cf18-125">Utöka eller komprimera avsnittet Poster som ska ingå.</span><span class="sxs-lookup"><span data-stu-id="2cf18-125">Expand or collapse the Records to include section.</span></span>
6. <span data-ttu-id="2cf18-126">Klicka på Filter.</span><span class="sxs-lookup"><span data-stu-id="2cf18-126">Click Filter.</span></span>
7. <span data-ttu-id="2cf18-127">Välj raden för fält = artikelnummer i listan.</span><span class="sxs-lookup"><span data-stu-id="2cf18-127">In the list, select the row for Field = Item number.</span></span>
8. <span data-ttu-id="2cf18-128">Ange ett värde i fältet Kriterier.</span><span class="sxs-lookup"><span data-stu-id="2cf18-128">In the Criteria field, type a value.</span></span>
    * <span data-ttu-id="2cf18-129">Exempel: P6003</span><span class="sxs-lookup"><span data-stu-id="2cf18-129">Example: P6003</span></span>  
9. <span data-ttu-id="2cf18-130">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="2cf18-130">Click OK.</span></span>
10. <span data-ttu-id="2cf18-131">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="2cf18-131">Click OK.</span></span>
11. <span data-ttu-id="2cf18-132">Klicka på Planerade order.</span><span class="sxs-lookup"><span data-stu-id="2cf18-132">Click Planned orders.</span></span>
12. <span data-ttu-id="2cf18-133">Använd snabbfiltret för att söka efter poster.</span><span class="sxs-lookup"><span data-stu-id="2cf18-133">Use the Quick Filter to find records.</span></span> <span data-ttu-id="2cf18-134">Filtrera till exempel i fältet Artikelnummer med värdet "P6000".</span><span class="sxs-lookup"><span data-stu-id="2cf18-134">For example, filter on the Item number field with a value of 'P6000'.</span></span>
    * <span data-ttu-id="2cf18-135">Filtrera efter den receptartikel som har en samprodukt för den artikel som du har skapat en försäljningsorder för.</span><span class="sxs-lookup"><span data-stu-id="2cf18-135">Filter by the formula item that has as co-product of the item that you created a sales order for.</span></span>  
13. <span data-ttu-id="2cf18-136">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="2cf18-136">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="2cf18-137">Välj någon av de rader som returneras av filtret.</span><span class="sxs-lookup"><span data-stu-id="2cf18-137">Select any of the rows returned by the filter.</span></span>  
14. <span data-ttu-id="2cf18-138">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="2cf18-138">In the list, click the link in the selected row.</span></span>
15. <span data-ttu-id="2cf18-139">Expandera eller komprimera avsnittet Pegging.</span><span class="sxs-lookup"><span data-stu-id="2cf18-139">Expand or collapse the Pegging section.</span></span>
16. <span data-ttu-id="2cf18-140">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="2cf18-140">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="2cf18-141">Den planerade ordern peggas till försäljningsordern för samprodukten.</span><span class="sxs-lookup"><span data-stu-id="2cf18-141">The planned order is pegged to the sales order for the co-product.</span></span>  
17. <span data-ttu-id="2cf18-142">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="2cf18-142">Close the page.</span></span>


