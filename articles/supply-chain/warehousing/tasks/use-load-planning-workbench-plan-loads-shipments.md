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
ms.search.form: WHSHistory, WHSLoadTable, WHSLoadPlanningListPage, WHSLoadPlanningWorkbench
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c37a98a3728cb1233a6e1207975a6b8f23f8120d
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/16/2020
ms.locfileid: "4438048"
---
# <a name="plan-loads-and-shipments-using-the-load-planning-workbench"></a><span data-ttu-id="9e33c-103">Planera laster och utleveranser med workbench för lastplanering</span><span class="sxs-lookup"><span data-stu-id="9e33c-103">Plan loads and shipments using the Load planning workbench</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="9e33c-104">I det här avsnittet visas hur du använder workbench för lastplanering om för att skapa en beläggning för en försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="9e33c-104">This topic shows how to use the load planning workbench to create a load for a sales order.</span></span> <span data-ttu-id="9e33c-105">Som en förutsättning skapar vi försäljningsordern först.</span><span class="sxs-lookup"><span data-stu-id="9e33c-105">As a prerequisite we'll create the sales order first.</span></span> <span data-ttu-id="9e33c-106">Den här proceduren utgör en del av det dagliga arbetet för transportkoordinatorn.</span><span class="sxs-lookup"><span data-stu-id="9e33c-106">This procedure is part of the daily work for the transportation coordinator.</span></span> <span data-ttu-id="9e33c-107">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="9e33c-107">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-a-sales-order"></a><span data-ttu-id="9e33c-108">Skapa en försäljningsorder</span><span class="sxs-lookup"><span data-stu-id="9e33c-108">Create a sales order</span></span>
1. <span data-ttu-id="9e33c-109">Gå till **Navigeringsfönstret > Moduler > Kundreskontra > Order > Alla försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="9e33c-109">Go to the **Navigation pane > Modules > Accounts receivable > Orders > All sales orders**.</span></span>
2. <span data-ttu-id="9e33c-110">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="9e33c-110">Select **New**.</span></span>
3. <span data-ttu-id="9e33c-111">På fältet **Kundkonto** klicka på knappen för att öppna sökning.</span><span class="sxs-lookup"><span data-stu-id="9e33c-111">In the **Customer account** field, select the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="9e33c-112">Välj kontot **US-004**.</span><span class="sxs-lookup"><span data-stu-id="9e33c-112">Select account **US-004**.</span></span>
5. <span data-ttu-id="9e33c-113">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="9e33c-113">Select **OK**.</span></span>
6. <span data-ttu-id="9e33c-114">På fält **Artikelnummer** klicka på nedrullningsbara knappen för att öppna sökningen.</span><span class="sxs-lookup"><span data-stu-id="9e33c-114">In the **Item number** field, select the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="9e33c-115">Välj artikel **A0001**.</span><span class="sxs-lookup"><span data-stu-id="9e33c-115">Select item **A0001**.</span></span> <span data-ttu-id="9e33c-116">**A0001** har aktiverats för transporthantering.</span><span class="sxs-lookup"><span data-stu-id="9e33c-116">**A0001** is enabled for transportation management.</span></span>  
8. <span data-ttu-id="9e33c-117">I fältet **Plats** klicka på nedrullningsbara knappen för att öppna sökningen och välj sedan en artikel.</span><span class="sxs-lookup"><span data-stu-id="9e33c-117">In the **Site** field, select the drop-down button to open the lookup, then select an item.</span></span>
9. <span data-ttu-id="9e33c-118">Ange ett nummer i fältet **Kvantitet**.</span><span class="sxs-lookup"><span data-stu-id="9e33c-118">In the **Quantity** field, enter a number.</span></span>
10. <span data-ttu-id="9e33c-119">I fältet **Lagerställe** skriver du "24" för det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="9e33c-119">In the **Warehouse** field, type '24' for this example.</span></span> <span data-ttu-id="9e33c-120">Lagerstället aktiveras för transportledning och avancerad lagerstyrning.</span><span class="sxs-lookup"><span data-stu-id="9e33c-120">This warehouse is enabled for transportation management and advanced warehouse management.</span></span>  
11. <span data-ttu-id="9e33c-121">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="9e33c-121">Select **Save**.</span></span>
12. <span data-ttu-id="9e33c-122">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="9e33c-122">Close the page.</span></span>

## <a name="create-a-new-load"></a><span data-ttu-id="9e33c-123">Skapa en ny beläggning.</span><span class="sxs-lookup"><span data-stu-id="9e33c-123">Create a new load</span></span>
1. <span data-ttu-id="9e33c-124">Gå till **Navigeringsfönstret > Moduler > Transporthantering > Planering > Workbench för lastplanering**.</span><span class="sxs-lookup"><span data-stu-id="9e33c-124">Go to the **Navigation pane > Modules > Transportation management > Planning > Load planning workbench**.</span></span>
2. <span data-ttu-id="9e33c-125">Välj fliken **Försäljningsrader**. Nu skapar du beläggningen för den försäljningsorder som du precis skapade.</span><span class="sxs-lookup"><span data-stu-id="9e33c-125">Select the **Sales lines** tab. Now you'll build the load for the sales order that you just created.</span></span> <span data-ttu-id="9e33c-126">Beläggningar kan skapas med utgångspunkt i tillgång och efterfrågan från inköpsorder, överföringsorder och försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="9e33c-126">Loads can be built based on supply and demand from purchase orders, transfer orders, and sales orders.</span></span>  
3. <span data-ttu-id="9e33c-127">I åtgärdsfönstret väljer du **Tillgång och efterfrågan**.</span><span class="sxs-lookup"><span data-stu-id="9e33c-127">On the Action Pane, select **Supply and demand**.</span></span>
4. <span data-ttu-id="9e33c-128">Välj **Till ny last**.</span><span class="sxs-lookup"><span data-stu-id="9e33c-128">Select **To new load**.</span></span>
5. <span data-ttu-id="9e33c-129">I fältet **Lastmall-ID** väljer du den nedrullningsbara knappen för att öppna sökningen.</span><span class="sxs-lookup"><span data-stu-id="9e33c-129">In the **Load template ID** field, select the drop-down button to open the lookup.</span></span> <span data-ttu-id="9e33c-130">Beläggningsmallen definierar maximala mått för vikt och volym för hela beläggningen.</span><span class="sxs-lookup"><span data-stu-id="9e33c-130">The Load template defines maximum measurements for weight and volume of the entire load.</span></span> <span data-ttu-id="9e33c-131">Beläggningsmallen kan till exempel representera storleken på en behållare eller en lastbil.</span><span class="sxs-lookup"><span data-stu-id="9e33c-131">For example, the load template might represent the size of a container or truck.</span></span> <span data-ttu-id="9e33c-132">Markera en artikel.</span><span class="sxs-lookup"><span data-stu-id="9e33c-132">Select an item.</span></span>
6. <span data-ttu-id="9e33c-133">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="9e33c-133">Select **OK**.</span></span>

## <a name="rate-and-route-the-load"></a><span data-ttu-id="9e33c-134">Tariff och rutt för beläggningen</span><span class="sxs-lookup"><span data-stu-id="9e33c-134">Rate and route the load</span></span>
1. <span data-ttu-id="9e33c-135">Välj **värdering och flöde**.</span><span class="sxs-lookup"><span data-stu-id="9e33c-135">Select **Rating and routing**.</span></span>
2. <span data-ttu-id="9e33c-136">Välj **workbench för tariff/rutt**.</span><span class="sxs-lookup"><span data-stu-id="9e33c-136">Select **Rate route workbench**.</span></span>
3. <span data-ttu-id="9e33c-137">Välj **Tariffbutik**.</span><span class="sxs-lookup"><span data-stu-id="9e33c-137">Select **Rate shop**.</span></span>
4. <span data-ttu-id="9e33c-138">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="9e33c-138">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="9e33c-139">Välj **Tilldela**.</span><span class="sxs-lookup"><span data-stu-id="9e33c-139">Select **Assign**.</span></span>
6. <span data-ttu-id="9e33c-140">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="9e33c-140">Close the page.</span></span>

