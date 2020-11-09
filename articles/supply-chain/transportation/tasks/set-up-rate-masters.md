---
title: Ställ in tariffhuvuden
description: I den här proceduren visas hur du ställer in ett tariffhuvud.
author: ShylaThompson
manager: tfehr
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSRouteWorkbench, TMSRateMaster, TMSRateBaseType
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 72d71aa15f8cec532980f412ff1cb48e142c4cb1
ms.sourcegitcommit: a36a4f9915ae3eb36bf8220111cf1486387713d9
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/16/2020
ms.locfileid: "4016480"
---
# <a name="set-up-rate-masters"></a><span data-ttu-id="8376f-103">Ställ in tariffhuvuden</span><span class="sxs-lookup"><span data-stu-id="8376f-103">Set up rate masters</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="8376f-104">I den här proceduren visas hur du ställer in ett tariffhuvud.</span><span class="sxs-lookup"><span data-stu-id="8376f-104">This procedure shows you how to set up a rate master.</span></span> <span data-ttu-id="8376f-105">Den logistikansvarige ställer vanligtvis in tariffhuvuden, beroende på vilka kontrakt som har signerats med transportföretagen.</span><span class="sxs-lookup"><span data-stu-id="8376f-105">The logistic manager usually sets up rate masters, depending on the contracts signed with the carriers.</span></span> <span data-ttu-id="8376f-106">I detta scenario ställer du in ett tariffhuvud för ett flygtransportföretag.</span><span class="sxs-lookup"><span data-stu-id="8376f-106">In this scenario you will set up a rate master for an air carrier.</span></span> <span data-ttu-id="8376f-107">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="8376f-107">The demo data company used to create this procedure is USMF.</span></span>


## <a name="set-up-rate-master"></a><span data-ttu-id="8376f-108">Ställa in tariffhuvud</span><span class="sxs-lookup"><span data-stu-id="8376f-108">Set up rate master</span></span>
1. <span data-ttu-id="8376f-109">Gå till Transporthantering > Inställningar > Klassificering > Tariffmall.</span><span class="sxs-lookup"><span data-stu-id="8376f-109">Go to Transportation management > Setup > Rating > Rate master.</span></span>
2. <span data-ttu-id="8376f-110">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="8376f-110">Click New.</span></span>
3. <span data-ttu-id="8376f-111">Skriv ett värde i fältet Tariffmall.</span><span class="sxs-lookup"><span data-stu-id="8376f-111">In the Rate master field, type a value.</span></span>
4. <span data-ttu-id="8376f-112">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="8376f-112">In the Name field, type a value.</span></span>
5. <span data-ttu-id="8376f-113">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet ID på metadata för bedömning.</span><span class="sxs-lookup"><span data-stu-id="8376f-113">In the Rating metadata ID field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="8376f-114">ID på metadata för bedömning bestämmer vilka data som behövs för tariffhuvudet, eftersom det definierar de metadata som förväntas av TMS-motorn där det här tariffhuvudet används.</span><span class="sxs-lookup"><span data-stu-id="8376f-114">The rating metadata ID will determine the data needed for the rate master, as it defines the metadata expected by the TMS engine using this rate master.</span></span>  
6. <span data-ttu-id="8376f-115">Välj alternativet P2P i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="8376f-115">For this example, select the P2P option</span></span>
7. <span data-ttu-id="8376f-116">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="8376f-116">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="8376f-117">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="8376f-117">Click Save.</span></span>

## <a name="set-up-rate-base"></a><span data-ttu-id="8376f-118">Ställa in tariffbas</span><span class="sxs-lookup"><span data-stu-id="8376f-118">Set up rate base</span></span>
1. <span data-ttu-id="8376f-119">Klicka på Tariffbas.</span><span class="sxs-lookup"><span data-stu-id="8376f-119">Click Rate base.</span></span>
    * <span data-ttu-id="8376f-120">Tariffbasen bestämmer tariffen för transportföretaget och kan användas för att ställa in en tariffstruktur, eftersom detta strukturerar upp tarifferna i de brytpunkter som definieras i avbrottsmallen.</span><span class="sxs-lookup"><span data-stu-id="8376f-120">The rate base determines the rate of the carrier, and can be used to set up a tariff structure as it structures the rates in the breakpoints defined in the break master.</span></span>  
2. <span data-ttu-id="8376f-121">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="8376f-121">Click New.</span></span>
3. <span data-ttu-id="8376f-122">Skriv ett värde i fältet Tariffbas.</span><span class="sxs-lookup"><span data-stu-id="8376f-122">In the Rate base field, type a value.</span></span>
4. <span data-ttu-id="8376f-123">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="8376f-123">In the Name field, type a value.</span></span>
5. <span data-ttu-id="8376f-124">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Avbrottsmall.</span><span class="sxs-lookup"><span data-stu-id="8376f-124">In the Break master field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="8376f-125">Avbrottsmallar används för att definiera prissättningsstrukturen och dess brytpunkter.</span><span class="sxs-lookup"><span data-stu-id="8376f-125">Break masters are used to define the pricing structure and its breakpoints.</span></span> <span data-ttu-id="8376f-126">Prissättningsstrukturen använder skiftindelad prissättning som baseras på fysiska dimensioner.</span><span class="sxs-lookup"><span data-stu-id="8376f-126">The pricing structure uses tiered pricing that is based on physical dimensions.</span></span>  
6. <span data-ttu-id="8376f-127">Använd vikt i det här exemplet</span><span class="sxs-lookup"><span data-stu-id="8376f-127">For this example, use weight</span></span>
7. <span data-ttu-id="8376f-128">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="8376f-128">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="8376f-129">Växla expanderingen av avsnittet Detaljer.</span><span class="sxs-lookup"><span data-stu-id="8376f-129">Toggle the expansion of the Details section.</span></span>
9. <span data-ttu-id="8376f-130">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="8376f-130">Click New.</span></span>
10. <span data-ttu-id="8376f-131">Ange "30301" i fältet Postnummer för avlämning från.</span><span class="sxs-lookup"><span data-stu-id="8376f-131">In the Drop-off Postal Code From field, type '30301'.</span></span>
11. <span data-ttu-id="8376f-132">Skriv "30318" i fältet Postnummer för avlämning till.</span><span class="sxs-lookup"><span data-stu-id="8376f-132">In the Drop-off Postal Code To field, type '30318'.</span></span>
12. <span data-ttu-id="8376f-133">Skriv "USA" i fältet Avlämningsland/region.</span><span class="sxs-lookup"><span data-stu-id="8376f-133">In the Drop-off Country Region field, type 'USA'.</span></span>
13. <span data-ttu-id="8376f-134">Skriv "100" i fältet <1,00 kg.</span><span class="sxs-lookup"><span data-stu-id="8376f-134">In the <1.00 Lbs field, type '100'.</span></span>
    * <span data-ttu-id="8376f-135">Infoga tariffen per kilo om den totala vikten på beläggningen är mindre än 1 kilo.</span><span class="sxs-lookup"><span data-stu-id="8376f-135">Insert the rate per lbs if the total weight of the load is less than 1 pound.</span></span>  
14. <span data-ttu-id="8376f-136">I fältet <5,00 Lbs, typ "300".</span><span class="sxs-lookup"><span data-stu-id="8376f-136">In the <5.00 Lbs field, type '300'.</span></span>
    * <span data-ttu-id="8376f-137">Infoga tariffen per kilo om den totala vikten på beläggningen är mindre än 5 kilo.</span><span class="sxs-lookup"><span data-stu-id="8376f-137">Insert the rate per lbs if the total weight of the load is less than 5 pounds.</span></span>  
15. <span data-ttu-id="8376f-138">I fältet <20,00 Lbs, typ "500".</span><span class="sxs-lookup"><span data-stu-id="8376f-138">In the <20.00 Lbs field, type '500'.</span></span>
    * <span data-ttu-id="8376f-139">Infoga tariffen per kilo om den totala vikten på beläggningen är mindre än 20 kilo.</span><span class="sxs-lookup"><span data-stu-id="8376f-139">Insert the rate per lbs if the total weight of the load is less than 20 pounds.</span></span>  
16. <span data-ttu-id="8376f-140">I fältet <100,00 Lbs, typ "1000".</span><span class="sxs-lookup"><span data-stu-id="8376f-140">In the <100.00 Lbs field, type '1000'.</span></span>
    * <span data-ttu-id="8376f-141">Infoga tariffen per kilo om den totala vikten på beläggningen är mindre än 100 kilo.</span><span class="sxs-lookup"><span data-stu-id="8376f-141">Insert the rate per lbs if the total weight of the load is less than 100 pounds.</span></span>  
17. <span data-ttu-id="8376f-142">I fältet <1000,00 Lbs, typ "3000".</span><span class="sxs-lookup"><span data-stu-id="8376f-142">In the <1,000.00 Lbs field, type '3000'.</span></span>
    * <span data-ttu-id="8376f-143">Infoga tariffen per kilo om den totala vikten på beläggningen är mindre än 1 000 kilo.</span><span class="sxs-lookup"><span data-stu-id="8376f-143">Insert the rate per lbs if the total weight of the load is less than 1000 pounds.</span></span>  
18. <span data-ttu-id="8376f-144">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="8376f-144">Click Save.</span></span>
19. <span data-ttu-id="8376f-145">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="8376f-145">Close the page.</span></span>

## <a name="assign-rate-base"></a><span data-ttu-id="8376f-146">Tilldela tariffbas</span><span class="sxs-lookup"><span data-stu-id="8376f-146">Assign rate base</span></span>
1. <span data-ttu-id="8376f-147">Växla expanderingen av avsnittet Tilldelningar av tariffbas.</span><span class="sxs-lookup"><span data-stu-id="8376f-147">Toggle the expansion of the Rate base assignments section.</span></span>
2. <span data-ttu-id="8376f-148">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="8376f-148">Click New.</span></span>
    * <span data-ttu-id="8376f-149">Du kan ha flera tilldelningar av tariffbas för varje tariffhuvud.</span><span class="sxs-lookup"><span data-stu-id="8376f-149">You can have several rate base assignments for each rate master.</span></span> <span data-ttu-id="8376f-150">På så sätt kan du skapa flera olika prispunkter för varje transportföretag beroende på mål, tjänster eller olika tariffbaser.</span><span class="sxs-lookup"><span data-stu-id="8376f-150">This makes it possible to create several different price points for each carrier depending on destinations, services, or different rate bases.</span></span> <span data-ttu-id="8376f-151">I den här proceduren kommer du endast att skapa en tariffbastilldelning.</span><span class="sxs-lookup"><span data-stu-id="8376f-151">In this procedure you will only create one rate base assignment.</span></span>  
3. <span data-ttu-id="8376f-152">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="8376f-152">In the Name field, type a value.</span></span>
4. <span data-ttu-id="8376f-153">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Tariffbas.</span><span class="sxs-lookup"><span data-stu-id="8376f-153">In the Rate base field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="8376f-154">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="8376f-154">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="8376f-155">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Tjänst.</span><span class="sxs-lookup"><span data-stu-id="8376f-155">In the Service field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="8376f-156">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="8376f-156">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="8376f-157">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="8376f-157">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="8376f-158">Ange "98052" i fältet Postnummer för upphämtning.</span><span class="sxs-lookup"><span data-stu-id="8376f-158">In the Pick-up Postal Code field, type '98052'.</span></span>
    * <span data-ttu-id="8376f-159">Ange vilket postnummer som den här tariffbastilldelningen ska gälla från.</span><span class="sxs-lookup"><span data-stu-id="8376f-159">Specify which postal code this rate base assignment should be valid from.</span></span>    
10. <span data-ttu-id="8376f-160">Skriv "USA" i fältet Upphämtningsland/region.</span><span class="sxs-lookup"><span data-stu-id="8376f-160">In the Pick-up Country Region field, type 'USA'.</span></span>
11. <span data-ttu-id="8376f-161">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="8376f-161">Click Save.</span></span>

