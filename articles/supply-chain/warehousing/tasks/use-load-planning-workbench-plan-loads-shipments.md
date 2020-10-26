---
title: Planera laster och utleveranser med workbench för lastplanering
description: I det här avsnittet visas hur du använder workbench för lastplanering om för att skapa en beläggning för en försäljningsorder.
author: ShylaThompson
manager: tfehr
ms.date: 07/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7966c6e445e0e44cd4ff8518926aa6b410502e13
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/10/2020
ms.locfileid: "3980445"
---
# <a name="plan-loads-and-shipments-using-the-load-planning-workbench"></a><span data-ttu-id="ff71e-103">Planera laster och utleveranser med workbench för lastplanering</span><span class="sxs-lookup"><span data-stu-id="ff71e-103">Plan loads and shipments using the Load planning workbench</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ff71e-104">I det här avsnittet visas hur du använder workbench för lastplanering om för att skapa en beläggning för en försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="ff71e-104">This topic shows how to use the load planning workbench to create a load for a sales order.</span></span> <span data-ttu-id="ff71e-105">Som en förutsättning skapar vi försäljningsordern först.</span><span class="sxs-lookup"><span data-stu-id="ff71e-105">As a prerequisite we'll create the sales order first.</span></span> <span data-ttu-id="ff71e-106">Den här proceduren utgör en del av det dagliga arbetet för transportkoordinatorn.</span><span class="sxs-lookup"><span data-stu-id="ff71e-106">This procedure is part of the daily work for the transportation coordinator.</span></span> <span data-ttu-id="ff71e-107">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="ff71e-107">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-a-sales-order"></a><span data-ttu-id="ff71e-108">Skapa en försäljningsorder</span><span class="sxs-lookup"><span data-stu-id="ff71e-108">Create a sales order</span></span>
1. <span data-ttu-id="ff71e-109">Gå till **Navigeringsfönstret > Moduler > Kundreskontra > Order > Alla försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="ff71e-109">Go to the **Navigation pane > Modules > Accounts receivable > Orders > All sales orders**.</span></span>
2. <span data-ttu-id="ff71e-110">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="ff71e-110">Select **New**.</span></span>
3. <span data-ttu-id="ff71e-111">På fältet **Kundkonto** klicka på knappen för att öppna sökning.</span><span class="sxs-lookup"><span data-stu-id="ff71e-111">In the **Customer account** field, select the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="ff71e-112">Välj kontot **US-004**.</span><span class="sxs-lookup"><span data-stu-id="ff71e-112">Select account **US-004**.</span></span>
5. <span data-ttu-id="ff71e-113">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="ff71e-113">Select **OK**.</span></span>
6. <span data-ttu-id="ff71e-114">På fält **Artikelnummer** klicka på nedrullningsbara knappen för att öppna sökningen.</span><span class="sxs-lookup"><span data-stu-id="ff71e-114">In the **Item number** field, select the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="ff71e-115">Välj artikel **A0001**.</span><span class="sxs-lookup"><span data-stu-id="ff71e-115">Select item **A0001**.</span></span> <span data-ttu-id="ff71e-116">**A0001** har aktiverats för transporthantering.</span><span class="sxs-lookup"><span data-stu-id="ff71e-116">**A0001** is enabled for transportation management.</span></span>  
8. <span data-ttu-id="ff71e-117">I fältet **Plats** klicka på nedrullningsbara knappen för att öppna sökningen och välj sedan en artikel.</span><span class="sxs-lookup"><span data-stu-id="ff71e-117">In the **Site** field, select the drop-down button to open the lookup, then select an item.</span></span>
9. <span data-ttu-id="ff71e-118">Ange ett nummer i fältet **Kvantitet**.</span><span class="sxs-lookup"><span data-stu-id="ff71e-118">In the **Quantity** field, enter a number.</span></span>
10. <span data-ttu-id="ff71e-119">I fältet **Lagerställe** skriver du "24" för det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="ff71e-119">In the **Warehouse** field, type '24' for this example.</span></span> <span data-ttu-id="ff71e-120">Lagerstället aktiveras för transportledning och avancerad lagerstyrning.</span><span class="sxs-lookup"><span data-stu-id="ff71e-120">This warehouse is enabled for transportation management and advanced warehouse management.</span></span>  
11. <span data-ttu-id="ff71e-121">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="ff71e-121">Select **Save**.</span></span>
12. <span data-ttu-id="ff71e-122">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="ff71e-122">Close the page.</span></span>

## <a name="create-a-new-load"></a><span data-ttu-id="ff71e-123">Skapa en ny beläggning.</span><span class="sxs-lookup"><span data-stu-id="ff71e-123">Create a new load</span></span>
1. <span data-ttu-id="ff71e-124">Gå till **Navigeringsfönstret > Moduler > Transporthantering > Planering > Workbench för lastplanering**.</span><span class="sxs-lookup"><span data-stu-id="ff71e-124">Go to the **Navigation pane > Modules > Transportation management > Planning > Load planning workbench**.</span></span>
2. <span data-ttu-id="ff71e-125">Välj fliken **Försäljningsrader**. Nu skapar du beläggningen för den försäljningsorder som du precis skapade.</span><span class="sxs-lookup"><span data-stu-id="ff71e-125">Select the **Sales lines** tab. Now you'll build the load for the sales order that you just created.</span></span> <span data-ttu-id="ff71e-126">Beläggningar kan skapas med utgångspunkt i tillgång och efterfrågan från inköpsorder, överföringsorder och försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="ff71e-126">Loads can be built based on supply and demand from purchase orders, transfer orders, and sales orders.</span></span>  
3. <span data-ttu-id="ff71e-127">I åtgärdsfönstret väljer du **Tillgång och efterfrågan**.</span><span class="sxs-lookup"><span data-stu-id="ff71e-127">On the Action Pane, select **Supply and demand**.</span></span>
4. <span data-ttu-id="ff71e-128">Välj **Till ny last**.</span><span class="sxs-lookup"><span data-stu-id="ff71e-128">Select **To new load**.</span></span>
5. <span data-ttu-id="ff71e-129">I fältet **Lastmall-ID** väljer du den nedrullningsbara knappen för att öppna sökningen.</span><span class="sxs-lookup"><span data-stu-id="ff71e-129">In the **Load template ID** field, select the drop-down button to open the lookup.</span></span> <span data-ttu-id="ff71e-130">Beläggningsmallen definierar maximala mått för vikt och volym för hela beläggningen.</span><span class="sxs-lookup"><span data-stu-id="ff71e-130">The Load template defines maximum measurements for weight and volume of the entire load.</span></span> <span data-ttu-id="ff71e-131">Beläggningsmallen kan till exempel representera storleken på en behållare eller en lastbil.</span><span class="sxs-lookup"><span data-stu-id="ff71e-131">For example, the load template might represent the size of a container or truck.</span></span> <span data-ttu-id="ff71e-132">Markera en artikel.</span><span class="sxs-lookup"><span data-stu-id="ff71e-132">Select an item.</span></span>
6. <span data-ttu-id="ff71e-133">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="ff71e-133">Select **OK**.</span></span>

## <a name="rate-and-route-the-load"></a><span data-ttu-id="ff71e-134">Tariff och rutt för beläggningen</span><span class="sxs-lookup"><span data-stu-id="ff71e-134">Rate and route the load</span></span>
1. <span data-ttu-id="ff71e-135">Välj **värdering och flöde**.</span><span class="sxs-lookup"><span data-stu-id="ff71e-135">Select **Rating and routing**.</span></span>
2. <span data-ttu-id="ff71e-136">Välj **workbench för tariff/rutt**.</span><span class="sxs-lookup"><span data-stu-id="ff71e-136">Select **Rate route workbench**.</span></span>
3. <span data-ttu-id="ff71e-137">Välj **Tariffbutik**.</span><span class="sxs-lookup"><span data-stu-id="ff71e-137">Select **Rate shop**.</span></span>
4. <span data-ttu-id="ff71e-138">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="ff71e-138">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="ff71e-139">Välj **Tilldela**.</span><span class="sxs-lookup"><span data-stu-id="ff71e-139">Select **Assign**.</span></span>
6. <span data-ttu-id="ff71e-140">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="ff71e-140">Close the page.</span></span>

