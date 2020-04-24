---
title: Ställ in bränsleindex för transportföretag
description: I den här handboken visas hur du skapar en bränsleindexregion, ett bränsleindex och ett transportföretags bränsleindex.
author: ShylaThompson
manager: tfehr
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 69bf6e3a896e560b1dbb96c8f997f6ee8dbb9ec1
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3214928"
---
# <a name="set-up-a-carrier-fuel-index"></a><span data-ttu-id="a2613-103">Ställ in bränsleindex för transportföretag</span><span class="sxs-lookup"><span data-stu-id="a2613-103">Set up a carrier fuel index</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a2613-104">I den här handboken visas hur du skapar en bränsleindexregion, ett bränsleindex och ett transportföretags bränsleindex.</span><span class="sxs-lookup"><span data-stu-id="a2613-104">This guide shows how to create a fuel index region, a fuel index and a carrier fuel index.</span></span> <span data-ttu-id="a2613-105">Bränsleindexregionen anger vilken region som bränsleindexet ska gälla för och bränsleindexet anger ett bränslepris för en viss tidsperiod.</span><span class="sxs-lookup"><span data-stu-id="a2613-105">The fuel index region specifies which region the fuel index should apply to, and the fuel index specifies a fuel price for a particular period of time.</span></span> <span data-ttu-id="a2613-106">För att återspegla ändringen i bränslepriser över tid kan du associera flera bränsleindex med en transportör.</span><span class="sxs-lookup"><span data-stu-id="a2613-106">To reflect the change in fuel prices over time, you can associate multiple fuel indexes with a carrier.</span></span>  <span data-ttu-id="a2613-107">Dessa uppgifter utförs normalt av en transportkoordinator.</span><span class="sxs-lookup"><span data-stu-id="a2613-107">These tasks are normally done by a transportation coordinator.</span></span> <span data-ttu-id="a2613-108">Du kan använda den här proceduren i demonstrationsdataföretaget USMF eller använda dina egna data.</span><span class="sxs-lookup"><span data-stu-id="a2613-108">You can use this procedure in demo data company USMF or using your own data.</span></span>


## <a name="create-a-fuel-index-region"></a><span data-ttu-id="a2613-109">Skapa en bränsleindexregion.</span><span class="sxs-lookup"><span data-stu-id="a2613-109">Create a fuel index region</span></span>
1. <span data-ttu-id="a2613-110">Gå till Transporthantering > Inställningar > Bränsleindex > Bränsleindexregioner.</span><span class="sxs-lookup"><span data-stu-id="a2613-110">Go to Transportation management > Setup > Fuel indexes > Fuel index regions.</span></span>
    * <span data-ttu-id="a2613-111">Först måste du skapa de olika regioner där du arbetar och beräkna olika bränsletillägg.</span><span class="sxs-lookup"><span data-stu-id="a2613-111">First you have to create the different regions, where you operate and calculate different fuel surcharges.</span></span>  
2. <span data-ttu-id="a2613-112">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="a2613-112">Click New.</span></span>
3. <span data-ttu-id="a2613-113">Skriv ett värde i fältet Region.</span><span class="sxs-lookup"><span data-stu-id="a2613-113">In the Region field, type a value.</span></span>
4. <span data-ttu-id="a2613-114">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="a2613-114">In the Name field, type a value.</span></span>
5. <span data-ttu-id="a2613-115">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="a2613-115">Click Save.</span></span>

## <a name="create-a-fuel-index"></a><span data-ttu-id="a2613-116">Skapa ett bränsleindex</span><span class="sxs-lookup"><span data-stu-id="a2613-116">Create a fuel index</span></span>
1. <span data-ttu-id="a2613-117">Gå till Transporthantering > Inställningar > Bränsleindex > Bränsleindex.</span><span class="sxs-lookup"><span data-stu-id="a2613-117">Go to Transportation management > Setup > Fuel indexes > Fuel indexes.</span></span>
    * <span data-ttu-id="a2613-118">Du måste ange aktuella priser för bränslet för de regioner som du har ställt in.</span><span class="sxs-lookup"><span data-stu-id="a2613-118">For the regions you have set up you need to enter the current prices for the fuel.</span></span>  
2. <span data-ttu-id="a2613-119">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="a2613-119">Click New.</span></span>
3. <span data-ttu-id="a2613-120">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Region.</span><span class="sxs-lookup"><span data-stu-id="a2613-120">In the Region field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="a2613-121">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="a2613-121">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="a2613-122">Ange ett nummer i fältet Pris per liter.</span><span class="sxs-lookup"><span data-stu-id="a2613-122">In the Price per gallon field, enter a number.</span></span>
6. <span data-ttu-id="a2613-123">Ange datum och tid i fältet Giltighetsdatum och giltighetstid.</span><span class="sxs-lookup"><span data-stu-id="a2613-123">In the Effective start date and time field, enter a date and time.</span></span>
7. <span data-ttu-id="a2613-124">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="a2613-124">Click Save.</span></span>

## <a name="create-a-carrier-fuel-index"></a><span data-ttu-id="a2613-125">Skapa ett bränsleindex för transportföretag</span><span class="sxs-lookup"><span data-stu-id="a2613-125">Create a Carrier fuel index</span></span>
1. <span data-ttu-id="a2613-126">Gå till Transporthantering > Inställningar > Bränsleindex > Transportföretagets bränsleindex.</span><span class="sxs-lookup"><span data-stu-id="a2613-126">Go to Transportation management > Setup > Fuel indexes > Carrier fuel indexes.</span></span>
2. <span data-ttu-id="a2613-127">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="a2613-127">Click New.</span></span>
3. <span data-ttu-id="a2613-128">Skriv ett värde i fältet Transportföretagets bränsleindex.</span><span class="sxs-lookup"><span data-stu-id="a2613-128">In the Carrier fuel index field, type a value.</span></span>
4. <span data-ttu-id="a2613-129">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="a2613-129">In the Description field, type a value.</span></span>
5. <span data-ttu-id="a2613-130">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="a2613-130">Click New.</span></span>
6. <span data-ttu-id="a2613-131">Ange datum och tid i fältet Giltighetsdatum och giltighetstid.</span><span class="sxs-lookup"><span data-stu-id="a2613-131">In the Effective start date and time field, enter a date and time.</span></span>
7. <span data-ttu-id="a2613-132">Ange ett nummer i fältet Pris/l från.</span><span class="sxs-lookup"><span data-stu-id="a2613-132">In the PPG From field, enter a number.</span></span>
    * <span data-ttu-id="a2613-133">I det här exemplet kan du ange 1,95 i fältet Pris/l från.</span><span class="sxs-lookup"><span data-stu-id="a2613-133">In this example, you can set PPG From field to 1.95.</span></span>  
8. <span data-ttu-id="a2613-134">Ange ett nummer i fältet Pris/l till.</span><span class="sxs-lookup"><span data-stu-id="a2613-134">In the PPG To field, enter a number.</span></span>
    * <span data-ttu-id="a2613-135">I det här exemplet kan du ange 2 i fältet Pris/l till.</span><span class="sxs-lookup"><span data-stu-id="a2613-135">In this example you can set the PPG To field to 2.</span></span>  
9. <span data-ttu-id="a2613-136">Välj ett tal i fältet Procent.</span><span class="sxs-lookup"><span data-stu-id="a2613-136">In the Percentage field, enter a number.</span></span>
    * <span data-ttu-id="a2613-137">I det här exemplet kan du ange procentsatsen till 3.</span><span class="sxs-lookup"><span data-stu-id="a2613-137">In this example you can set the percentage to 3.</span></span>  
10. <span data-ttu-id="a2613-138">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Valuta.</span><span class="sxs-lookup"><span data-stu-id="a2613-138">In the Currency field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="a2613-139">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="a2613-139">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="a2613-140">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="a2613-140">In the list, click the link in the selected row.</span></span>
13. <span data-ttu-id="a2613-141">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="a2613-141">Click Save.</span></span>

