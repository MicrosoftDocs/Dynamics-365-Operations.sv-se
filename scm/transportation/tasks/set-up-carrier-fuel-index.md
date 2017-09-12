--- 
title: "Ställ in bränsleindex för transportföretag"
description: "I den här handboken visas hur du skapar en bränsleindexregion, ett bränsleindex och ett transportföretags bränsleindex."
author: BibiSp
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 81f3244ff42cf13cd93ac10656c47f8a9204ef99
ms.contentlocale: sv-se
ms.lasthandoff: 08/29/2017

---
# <a name="set-up-a-carrier-fuel-index"></a><span data-ttu-id="391ca-103">Ställ in bränsleindex för transportföretag</span><span class="sxs-lookup"><span data-stu-id="391ca-103">Set up a carrier fuel index</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="391ca-104">I den här handboken visas hur du skapar en bränsleindexregion, ett bränsleindex och ett transportföretags bränsleindex.</span><span class="sxs-lookup"><span data-stu-id="391ca-104">This guide shows how to create a fuel index region, a fuel index and a carrier fuel index.</span></span> <span data-ttu-id="391ca-105">Bränsleindexregionen anger vilken region som bränsleindexet ska gälla för och bränsleindexet anger ett bränslepris för en viss tidsperiod.</span><span class="sxs-lookup"><span data-stu-id="391ca-105">The fuel index region specifies which region the fuel index should apply to, and the fuel index specifies a fuel price for a particular period of time.</span></span> <span data-ttu-id="391ca-106">För att återspegla ändringen i bränslepriser över tid kan du associera flera bränsleindex med en transportör.</span><span class="sxs-lookup"><span data-stu-id="391ca-106">To reflect the change in fuel prices over time, you can associate multiple fuel indexes with a carrier.</span></span>  <span data-ttu-id="391ca-107">Dessa uppgifter utförs normalt av en transportkoordinator.</span><span class="sxs-lookup"><span data-stu-id="391ca-107">These tasks are normally done by a transportation coordinator.</span></span> <span data-ttu-id="391ca-108">Du kan använda den här proceduren i demonstrationsdataföretaget USMF eller använda dina egna data.</span><span class="sxs-lookup"><span data-stu-id="391ca-108">You can use this procedure in demo data company USMF or using your own data.</span></span>


## <a name="create-a-fuel-index-region"></a><span data-ttu-id="391ca-109">Skapa en bränsleindexregion.</span><span class="sxs-lookup"><span data-stu-id="391ca-109">Create a fuel index region</span></span>
1. <span data-ttu-id="391ca-110">Gå till Transporthantering > Inställningar > Bränsleindex > Bränsleindexregioner.</span><span class="sxs-lookup"><span data-stu-id="391ca-110">Go to Transportation management > Setup > Fuel indexes > Fuel index regions.</span></span>
    * <span data-ttu-id="391ca-111">Först måste du skapa de olika regioner där du arbetar och beräkna olika bränsletillägg.</span><span class="sxs-lookup"><span data-stu-id="391ca-111">First you have to create the different regions, where you operate and calculate different fuel surcharges.</span></span>  
2. <span data-ttu-id="391ca-112">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="391ca-112">Click New.</span></span>
3. <span data-ttu-id="391ca-113">Skriv ett värde i fältet Region.</span><span class="sxs-lookup"><span data-stu-id="391ca-113">In the Region field, type a value.</span></span>
4. <span data-ttu-id="391ca-114">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="391ca-114">In the Name field, type a value.</span></span>
5. <span data-ttu-id="391ca-115">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="391ca-115">Click Save.</span></span>

## <a name="create-a-fuel-index"></a><span data-ttu-id="391ca-116">Skapa ett bränsleindex</span><span class="sxs-lookup"><span data-stu-id="391ca-116">Create a fuel index</span></span>
1. <span data-ttu-id="391ca-117">Gå till Transporthantering > Inställningar > Bränsleindex > Bränsleindex.</span><span class="sxs-lookup"><span data-stu-id="391ca-117">Go to Transportation management > Setup > Fuel indexes > Fuel indexes.</span></span>
    * <span data-ttu-id="391ca-118">Du måste ange aktuella priser för bränslet för de regioner som du har ställt in.</span><span class="sxs-lookup"><span data-stu-id="391ca-118">For the regions you have set up you need to enter the current prices for the fuel.</span></span>  
2. <span data-ttu-id="391ca-119">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="391ca-119">Click New.</span></span>
3. <span data-ttu-id="391ca-120">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Region.</span><span class="sxs-lookup"><span data-stu-id="391ca-120">In the Region field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="391ca-121">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="391ca-121">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="391ca-122">Ange ett nummer i fältet Pris per liter.</span><span class="sxs-lookup"><span data-stu-id="391ca-122">In the Price per gallon field, enter a number.</span></span>
6. <span data-ttu-id="391ca-123">Ange datum och tid i fältet Giltighetsdatum och giltighetstid.</span><span class="sxs-lookup"><span data-stu-id="391ca-123">In the Effective start date and time field, enter a date and time.</span></span>
7. <span data-ttu-id="391ca-124">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="391ca-124">Click Save.</span></span>

## <a name="create-a-carrier-fuel-index"></a><span data-ttu-id="391ca-125">Skapa ett bränsleindex för transportföretag</span><span class="sxs-lookup"><span data-stu-id="391ca-125">Create a Carrier fuel index</span></span>
1. <span data-ttu-id="391ca-126">Gå till Transporthantering > Inställningar > Bränsleindex > Transportföretagets bränsleindex.</span><span class="sxs-lookup"><span data-stu-id="391ca-126">Go to Transportation management > Setup > Fuel indexes > Carrier fuel indexes.</span></span>
2. <span data-ttu-id="391ca-127">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="391ca-127">Click New.</span></span>
3. <span data-ttu-id="391ca-128">Skriv ett värde i fältet Transportföretagets bränsleindex.</span><span class="sxs-lookup"><span data-stu-id="391ca-128">In the Carrier fuel index field, type a value.</span></span>
4. <span data-ttu-id="391ca-129">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="391ca-129">In the Description field, type a value.</span></span>
5. <span data-ttu-id="391ca-130">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="391ca-130">Click New.</span></span>
6. <span data-ttu-id="391ca-131">Ange datum och tid i fältet Giltighetsdatum och giltighetstid.</span><span class="sxs-lookup"><span data-stu-id="391ca-131">In the Effective start date and time field, enter a date and time.</span></span>
7. <span data-ttu-id="391ca-132">Ange ett nummer i fältet Pris/l från.</span><span class="sxs-lookup"><span data-stu-id="391ca-132">In the PPG From field, enter a number.</span></span>
    * <span data-ttu-id="391ca-133">I det här exemplet kan du ange 1,95 i fältet Pris/l från.</span><span class="sxs-lookup"><span data-stu-id="391ca-133">In this example, you can set PPG From field to 1.95.</span></span>  
8. <span data-ttu-id="391ca-134">Ange ett nummer i fältet Pris/l till.</span><span class="sxs-lookup"><span data-stu-id="391ca-134">In the PPG To field, enter a number.</span></span>
    * <span data-ttu-id="391ca-135">I det här exemplet kan du ange 2 i fältet Pris/l till.</span><span class="sxs-lookup"><span data-stu-id="391ca-135">In this example you can set the PPG To field to 2.</span></span>  
9. <span data-ttu-id="391ca-136">Välj ett tal i fältet Procent.</span><span class="sxs-lookup"><span data-stu-id="391ca-136">In the Percentage field, enter a number.</span></span>
    * <span data-ttu-id="391ca-137">I det här exemplet kan du ange procentsatsen till 3.</span><span class="sxs-lookup"><span data-stu-id="391ca-137">In this example you can set the percentage to 3.</span></span>  
10. <span data-ttu-id="391ca-138">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Valuta.</span><span class="sxs-lookup"><span data-stu-id="391ca-138">In the Currency field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="391ca-139">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="391ca-139">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="391ca-140">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="391ca-140">In the list, click the link in the selected row.</span></span>
13. <span data-ttu-id="391ca-141">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="391ca-141">Click Save.</span></span>


