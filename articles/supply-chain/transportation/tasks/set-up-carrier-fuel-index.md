---
title: Ställ in bränsleindex för transportföretag
description: I den här handboken visas hur du skapar en bränsleindexregion, ett bränsleindex och ett transportföretags bränsleindex.
author: ShylaThompson
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b6f72de7ad54a2b2dc1bf40fd8cb86d8b055e2d1
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1552102"
---
# <a name="set-up-a-carrier-fuel-index"></a><span data-ttu-id="7ec01-103">Ställ in bränsleindex för transportföretag</span><span class="sxs-lookup"><span data-stu-id="7ec01-103">Set up a carrier fuel index</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="7ec01-104">I den här handboken visas hur du skapar en bränsleindexregion, ett bränsleindex och ett transportföretags bränsleindex.</span><span class="sxs-lookup"><span data-stu-id="7ec01-104">This guide shows how to create a fuel index region, a fuel index and a carrier fuel index.</span></span> <span data-ttu-id="7ec01-105">Bränsleindexregionen anger vilken region som bränsleindexet ska gälla för och bränsleindexet anger ett bränslepris för en viss tidsperiod.</span><span class="sxs-lookup"><span data-stu-id="7ec01-105">The fuel index region specifies which region the fuel index should apply to, and the fuel index specifies a fuel price for a particular period of time.</span></span> <span data-ttu-id="7ec01-106">För att återspegla ändringen i bränslepriser över tid kan du associera flera bränsleindex med en transportör.</span><span class="sxs-lookup"><span data-stu-id="7ec01-106">To reflect the change in fuel prices over time, you can associate multiple fuel indexes with a carrier.</span></span>  <span data-ttu-id="7ec01-107">Dessa uppgifter utförs normalt av en transportkoordinator.</span><span class="sxs-lookup"><span data-stu-id="7ec01-107">These tasks are normally done by a transportation coordinator.</span></span> <span data-ttu-id="7ec01-108">Du kan använda den här proceduren i demonstrationsdataföretaget USMF eller använda dina egna data.</span><span class="sxs-lookup"><span data-stu-id="7ec01-108">You can use this procedure in demo data company USMF or using your own data.</span></span>


## <a name="create-a-fuel-index-region"></a><span data-ttu-id="7ec01-109">Skapa en bränsleindexregion.</span><span class="sxs-lookup"><span data-stu-id="7ec01-109">Create a fuel index region</span></span>
1. <span data-ttu-id="7ec01-110">Gå till Transporthantering > Inställningar > Bränsleindex > Bränsleindexregioner.</span><span class="sxs-lookup"><span data-stu-id="7ec01-110">Go to Transportation management > Setup > Fuel indexes > Fuel index regions.</span></span>
    * <span data-ttu-id="7ec01-111">Först måste du skapa de olika regioner där du arbetar och beräkna olika bränsletillägg.</span><span class="sxs-lookup"><span data-stu-id="7ec01-111">First you have to create the different regions, where you operate and calculate different fuel surcharges.</span></span>  
2. <span data-ttu-id="7ec01-112">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="7ec01-112">Click New.</span></span>
3. <span data-ttu-id="7ec01-113">Skriv ett värde i fältet Region.</span><span class="sxs-lookup"><span data-stu-id="7ec01-113">In the Region field, type a value.</span></span>
4. <span data-ttu-id="7ec01-114">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="7ec01-114">In the Name field, type a value.</span></span>
5. <span data-ttu-id="7ec01-115">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="7ec01-115">Click Save.</span></span>

## <a name="create-a-fuel-index"></a><span data-ttu-id="7ec01-116">Skapa ett bränsleindex</span><span class="sxs-lookup"><span data-stu-id="7ec01-116">Create a fuel index</span></span>
1. <span data-ttu-id="7ec01-117">Gå till Transporthantering > Inställningar > Bränsleindex > Bränsleindex.</span><span class="sxs-lookup"><span data-stu-id="7ec01-117">Go to Transportation management > Setup > Fuel indexes > Fuel indexes.</span></span>
    * <span data-ttu-id="7ec01-118">Du måste ange aktuella priser för bränslet för de regioner som du har ställt in.</span><span class="sxs-lookup"><span data-stu-id="7ec01-118">For the regions you have set up you need to enter the current prices for the fuel.</span></span>  
2. <span data-ttu-id="7ec01-119">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="7ec01-119">Click New.</span></span>
3. <span data-ttu-id="7ec01-120">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Region.</span><span class="sxs-lookup"><span data-stu-id="7ec01-120">In the Region field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="7ec01-121">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="7ec01-121">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="7ec01-122">Ange ett nummer i fältet Pris per liter.</span><span class="sxs-lookup"><span data-stu-id="7ec01-122">In the Price per gallon field, enter a number.</span></span>
6. <span data-ttu-id="7ec01-123">Ange datum och tid i fältet Giltighetsdatum och giltighetstid.</span><span class="sxs-lookup"><span data-stu-id="7ec01-123">In the Effective start date and time field, enter a date and time.</span></span>
7. <span data-ttu-id="7ec01-124">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="7ec01-124">Click Save.</span></span>

## <a name="create-a-carrier-fuel-index"></a><span data-ttu-id="7ec01-125">Skapa ett bränsleindex för transportföretag</span><span class="sxs-lookup"><span data-stu-id="7ec01-125">Create a Carrier fuel index</span></span>
1. <span data-ttu-id="7ec01-126">Gå till Transporthantering > Inställningar > Bränsleindex > Transportföretagets bränsleindex.</span><span class="sxs-lookup"><span data-stu-id="7ec01-126">Go to Transportation management > Setup > Fuel indexes > Carrier fuel indexes.</span></span>
2. <span data-ttu-id="7ec01-127">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="7ec01-127">Click New.</span></span>
3. <span data-ttu-id="7ec01-128">Skriv ett värde i fältet Transportföretagets bränsleindex.</span><span class="sxs-lookup"><span data-stu-id="7ec01-128">In the Carrier fuel index field, type a value.</span></span>
4. <span data-ttu-id="7ec01-129">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="7ec01-129">In the Description field, type a value.</span></span>
5. <span data-ttu-id="7ec01-130">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="7ec01-130">Click New.</span></span>
6. <span data-ttu-id="7ec01-131">Ange datum och tid i fältet Giltighetsdatum och giltighetstid.</span><span class="sxs-lookup"><span data-stu-id="7ec01-131">In the Effective start date and time field, enter a date and time.</span></span>
7. <span data-ttu-id="7ec01-132">Ange ett nummer i fältet Pris/l från.</span><span class="sxs-lookup"><span data-stu-id="7ec01-132">In the PPG From field, enter a number.</span></span>
    * <span data-ttu-id="7ec01-133">I det här exemplet kan du ange 1,95 i fältet Pris/l från.</span><span class="sxs-lookup"><span data-stu-id="7ec01-133">In this example, you can set PPG From field to 1.95.</span></span>  
8. <span data-ttu-id="7ec01-134">Ange ett nummer i fältet Pris/l till.</span><span class="sxs-lookup"><span data-stu-id="7ec01-134">In the PPG To field, enter a number.</span></span>
    * <span data-ttu-id="7ec01-135">I det här exemplet kan du ange 2 i fältet Pris/l till.</span><span class="sxs-lookup"><span data-stu-id="7ec01-135">In this example you can set the PPG To field to 2.</span></span>  
9. <span data-ttu-id="7ec01-136">Välj ett tal i fältet Procent.</span><span class="sxs-lookup"><span data-stu-id="7ec01-136">In the Percentage field, enter a number.</span></span>
    * <span data-ttu-id="7ec01-137">I det här exemplet kan du ange procentsatsen till 3.</span><span class="sxs-lookup"><span data-stu-id="7ec01-137">In this example you can set the percentage to 3.</span></span>  
10. <span data-ttu-id="7ec01-138">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Valuta.</span><span class="sxs-lookup"><span data-stu-id="7ec01-138">In the Currency field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="7ec01-139">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="7ec01-139">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="7ec01-140">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="7ec01-140">In the list, click the link in the selected row.</span></span>
13. <span data-ttu-id="7ec01-141">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="7ec01-141">Click Save.</span></span>

