---
title: Associera ett bränsleindex med ett transportföretag som ett tillägg
description: I den här guiden visas hur du skapar en tilldelning av tillägg, en tilläggsavgift för transportföretag, en tilläggsmall för bränsletillägg och associerar ett transportföretags bränsleindex med ett transportföretag.
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
ms.openlocfilehash: ae0aa90cfd673704bcd8e19f795499283ff01d44
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1560965"
---
# <a name="associate-a-fuel-index-with-a-carrier-as-an-accessorial-charge"></a><span data-ttu-id="99590-103">Associera ett bränsleindex med ett transportföretag som ett tillägg</span><span class="sxs-lookup"><span data-stu-id="99590-103">Associate a fuel index with a carrier as an accessorial charge</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="99590-104">I den här guiden visas hur du skapar en tilldelning av tillägg, en tilläggsavgift för transportföretag, en tilläggsmall för bränsletillägg och associerar ett transportföretags bränsleindex med ett transportföretag.</span><span class="sxs-lookup"><span data-stu-id="99590-104">This guide shows how to create an accessorial assignment, carrier accessorial charge, accessorial master for fuel surcharge, and associate a carrier fuel index with a carrier.</span></span> <span data-ttu-id="99590-105">Du måste ha ställt in ett transportföretags bränsleindex innan du kör den här guiden.</span><span class="sxs-lookup"><span data-stu-id="99590-105">You need to have set up a carrier fuel index before you run this guide.</span></span> <span data-ttu-id="99590-106">Du kan använda guiden "Ställa in bränsleindex för transportföretag" för att göra detta.</span><span class="sxs-lookup"><span data-stu-id="99590-106">You can use the “Set up a carrier fuel index” guide to do this.</span></span> <span data-ttu-id="99590-107">Dessa inställningsuppgifter utförs normalt av en logistikansvarig.</span><span class="sxs-lookup"><span data-stu-id="99590-107">These setup tasks are typically done by a Logistics manager.</span></span> <span data-ttu-id="99590-108">De demonstrationsdata som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="99590-108">The demo data used to create this procedure is USMF.</span></span>


## <a name="create-an-accessorial-master"></a><span data-ttu-id="99590-109">Skapa en tilläggsmall</span><span class="sxs-lookup"><span data-stu-id="99590-109">Create an accessorial master</span></span>
1. <span data-ttu-id="99590-110">Gå till Transporthantering > Inställningar > Klassificering > Tilläggsmallar.</span><span class="sxs-lookup"><span data-stu-id="99590-110">Go to Transportation management > Setup > Rating > Accessorial masters.</span></span>
2. <span data-ttu-id="99590-111">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="99590-111">Click New.</span></span>
3. <span data-ttu-id="99590-112">Skriv ett värde i fältet Tilläggsmall.</span><span class="sxs-lookup"><span data-stu-id="99590-112">In the Accessorial master field, type a value.</span></span>
4. <span data-ttu-id="99590-113">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="99590-113">In the Name field, type a value.</span></span>
5. <span data-ttu-id="99590-114">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="99590-114">Click Save.</span></span>

## <a name="create-a-carrier-accessorial-charge"></a><span data-ttu-id="99590-115">Skapa en tilläggsavgift för transportföretag</span><span class="sxs-lookup"><span data-stu-id="99590-115">Create a carrier accessorial charge</span></span>
1. <span data-ttu-id="99590-116">Gå till Transporthantering > Inställningar > Klassificering > Tilläggsavgifter för transportföretag.</span><span class="sxs-lookup"><span data-stu-id="99590-116">Go to Transportation management > Setup > Rating > Carrier accessorial charges.</span></span>
2. <span data-ttu-id="99590-117">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="99590-117">Click New.</span></span>
3. <span data-ttu-id="99590-118">Skriv ett värde i fältet Transportföretagets tilläggs-ID.</span><span class="sxs-lookup"><span data-stu-id="99590-118">In the Carrier accessorial ID field, type a value.</span></span>
4. <span data-ttu-id="99590-119">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Transportföretag.</span><span class="sxs-lookup"><span data-stu-id="99590-119">In the Shipping carrier field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="99590-120">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="99590-120">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="99590-121">Välj Lastbilstransportföretag i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="99590-121">In this example, choose Truck Carrier.</span></span>  
6. <span data-ttu-id="99590-122">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="99590-122">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="99590-123">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Transportföretagstjänst.</span><span class="sxs-lookup"><span data-stu-id="99590-123">In the Carrier service field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="99590-124">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="99590-124">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="99590-125">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Tilläggsmall.</span><span class="sxs-lookup"><span data-stu-id="99590-125">In the Accessorial master field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="99590-126">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="99590-126">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="99590-127">Välj den tilläggsmall som nyligen har skapats i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="99590-127">In this example, choose the newly created Accessorial master.</span></span>  
11. <span data-ttu-id="99590-128">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="99590-128">Click Save.</span></span>

## <a name="create-an-accessorial-assignment"></a><span data-ttu-id="99590-129">Skapa en tilldelning av tillägg</span><span class="sxs-lookup"><span data-stu-id="99590-129">Create an accessorial assignment</span></span>
1. <span data-ttu-id="99590-130">Visa Tilldelningar av tillägg.</span><span class="sxs-lookup"><span data-stu-id="99590-130">Click Accessorial assignments.</span></span>
2. <span data-ttu-id="99590-131">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="99590-131">Click New.</span></span>
3. <span data-ttu-id="99590-132">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="99590-132">In the Name field, type a value.</span></span>
4. <span data-ttu-id="99590-133">Växla expanderingen av avsnittet Kriterier.</span><span class="sxs-lookup"><span data-stu-id="99590-133">Toggle the expansion of the Criteria section.</span></span>
    * <span data-ttu-id="99590-134">I villkoren kan du välja alltid att tillämpa bränsletillägget, eller för det här exemplet välja att det gäller bara inom en viss region.</span><span class="sxs-lookup"><span data-stu-id="99590-134">In the criteria, you can choose to always apply the fuel surcharge or for this example choose that it only applies within a certain region.</span></span>  
5. <span data-ttu-id="99590-135">Skriv ett värde i fältet Postnummer från.</span><span class="sxs-lookup"><span data-stu-id="99590-135">In the ZIP/postal code from field, type a value.</span></span>
6. <span data-ttu-id="99590-136">Skriv ett värde i fältet Postnummer till.</span><span class="sxs-lookup"><span data-stu-id="99590-136">In the ZIP/postal code to field, type a value.</span></span>
7. <span data-ttu-id="99590-137">Växla expanderingen av avsnittet Beräkning.</span><span class="sxs-lookup"><span data-stu-id="99590-137">Toggle the expansion of the Calculation section.</span></span>
    * <span data-ttu-id="99590-138">I beräkningsavsnittet kan du ange hur du beräknar bränsletillägget.</span><span class="sxs-lookup"><span data-stu-id="99590-138">In the calculation section you can specify how to calculate the fuel surcharge.</span></span> <span data-ttu-id="99590-139">Beräkningen beror på den tilläggsenhet som du valde som bas för beräkningen.</span><span class="sxs-lookup"><span data-stu-id="99590-139">This calculation depends on the Accessorial unit that you chose as the base for your calculation.</span></span>  
8. <span data-ttu-id="99590-140">Välj "Bränsletillägg" i fältet Typ av tilläggsavgift.</span><span class="sxs-lookup"><span data-stu-id="99590-140">In the Accessorial fee type field, select 'Fuel surcharge'.</span></span>
9. <span data-ttu-id="99590-141">Välj "Körsträcka" i fältet Tilläggsenhet.</span><span class="sxs-lookup"><span data-stu-id="99590-141">In the Accessorial unit field, select 'Mileage'.</span></span>
10. <span data-ttu-id="99590-142">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Region.</span><span class="sxs-lookup"><span data-stu-id="99590-142">In the Region field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="99590-143">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="99590-143">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="99590-144">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="99590-144">Click Save.</span></span>

## <a name="update-the-carrier-rating-profile"></a><span data-ttu-id="99590-145">Uppdatera bedömningsprofilen för transportföretag</span><span class="sxs-lookup"><span data-stu-id="99590-145">Update the carrier rating profile</span></span>
1. <span data-ttu-id="99590-146">Gå till Transporthantering > Inställningar > Transportföretag > Transportföretag.</span><span class="sxs-lookup"><span data-stu-id="99590-146">Go to Transportation management > Setup > Carriers > Shipping carriers.</span></span>
2. <span data-ttu-id="99590-147">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="99590-147">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="99590-148">Växla expanderingen av avsnittet Bedömningsprofiler.</span><span class="sxs-lookup"><span data-stu-id="99590-148">Toggle the expansion of the Rating profiles section.</span></span>
4. <span data-ttu-id="99590-149">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="99590-149">Click Edit.</span></span>
5. <span data-ttu-id="99590-150">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Transportföretagets bränsleindex.</span><span class="sxs-lookup"><span data-stu-id="99590-150">In the Carrier fuel index field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="99590-151">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="99590-151">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="99590-152">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="99590-152">Click Save.</span></span>

