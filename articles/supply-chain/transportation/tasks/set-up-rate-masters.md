---
title: Ställ in tariffhuvuden
description: I den här proceduren visas hur du ställer in ett tariffhuvud.
author: ShylaThompson
manager: tfehr
ms.date: 10/16/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSBreakMaster,TMSRateMaster,TMSRateMasterBase,TMSRateBaseType, TMSRouteWorkbench
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 77629cbaec4c4d4608b8941e55ab23a106d38727
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5233617"
---
# <a name="set-up-rate-masters"></a><span data-ttu-id="810f0-103">Ställ in tariffhuvuden</span><span class="sxs-lookup"><span data-stu-id="810f0-103">Set up rate masters</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="810f0-104">I den här proceduren visas hur du ställer in ett tariffhuvud.</span><span class="sxs-lookup"><span data-stu-id="810f0-104">This procedure shows you how to set up a rate master.</span></span> <span data-ttu-id="810f0-105">Den logistikansvarige ställer vanligtvis in tariffhuvuden, beroende på vilka kontrakt som har signerats med transportföretagen.</span><span class="sxs-lookup"><span data-stu-id="810f0-105">The logistic manager usually sets up rate masters, depending on the contracts signed with the carriers.</span></span> <span data-ttu-id="810f0-106">I detta scenario ställer du in ett tariffhuvud för ett flygtransportföretag.</span><span class="sxs-lookup"><span data-stu-id="810f0-106">In this scenario you will set up a rate master for an air carrier.</span></span> <span data-ttu-id="810f0-107">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="810f0-107">The demo data company used to create this procedure is USMF.</span></span>

## <a name="set-up-break-master"></a><span data-ttu-id="810f0-108">Ställa in en avbrottsmall</span><span class="sxs-lookup"><span data-stu-id="810f0-108">Set up break master</span></span>

1. <span data-ttu-id="810f0-109">Gå till **Transporthantering > Inställningar > Klassificering > Rastmall**.</span><span class="sxs-lookup"><span data-stu-id="810f0-109">Go to **Transportation management > Setup > Rating > Break master**.</span></span> <span data-ttu-id="810f0-110">Avbrottsmallar används för att definiera prissättningsstrukturen och dess brytpunkter.</span><span class="sxs-lookup"><span data-stu-id="810f0-110">Break masters are used to define the pricing structure and its breakpoints.</span></span> <span data-ttu-id="810f0-111">Prissättningsstrukturen använder skiftindelad prissättning som baseras på fysiska dimensioner.</span><span class="sxs-lookup"><span data-stu-id="810f0-111">The pricing structure uses tiered pricing that is based on physical dimensions.</span></span>  
1. <span data-ttu-id="810f0-112">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="810f0-112">Select **New**.</span></span>
1. <span data-ttu-id="810f0-113">I fältet **Rastmall** anger du ett värde.</span><span class="sxs-lookup"><span data-stu-id="810f0-113">In the **Break master** field, enter a value.</span></span>
1. <span data-ttu-id="810f0-114">I fältet **Namn** anger du ett värde.</span><span class="sxs-lookup"><span data-stu-id="810f0-114">In the **Name** field, enter a value.</span></span>
1. <span data-ttu-id="810f0-115">I fältet **Datatyp** välj datatypen.</span><span class="sxs-lookup"><span data-stu-id="810f0-115">In the **Data type** field, select the data type.</span></span>
1. <span data-ttu-id="810f0-116">I fältet **Jämförelse** anger du den typ av jämförelse som begärs (med operatorer).</span><span class="sxs-lookup"><span data-stu-id="810f0-116">In the **Comparison** field, enter the kind of comparison requested (using operators).</span></span>
1. <span data-ttu-id="810f0-117">I fältet **Brytenhet** ange brytningsenheten.</span><span class="sxs-lookup"><span data-stu-id="810f0-117">In the **Break unit** field, enter the break unit.</span></span>
1. <span data-ttu-id="810f0-118">I avsnittet **Detaljer**, skapa så många raster som behövs för prisstrukturen.</span><span class="sxs-lookup"><span data-stu-id="810f0-118">In the **Details** section, create as many breaks as needed for the pricing structure.</span></span>
1. <span data-ttu-id="810f0-119">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="810f0-119">Select **Save**.</span></span>

## <a name="set-up-rate-master"></a><span data-ttu-id="810f0-120">Ställa in tariffhuvud</span><span class="sxs-lookup"><span data-stu-id="810f0-120">Set up rate master</span></span>

1. <span data-ttu-id="810f0-121">Gå till **Transporthantering > Inställningar > Klassificering > Tariffmall**.</span><span class="sxs-lookup"><span data-stu-id="810f0-121">Go to **Transportation management > Setup > Rating > Rate master**.</span></span>
1. <span data-ttu-id="810f0-122">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="810f0-122">Select **New**.</span></span>
1. <span data-ttu-id="810f0-123">Skriv ett värde i fältet **Tariffmall**.</span><span class="sxs-lookup"><span data-stu-id="810f0-123">In the **Rate master** field, type a value.</span></span>
1. <span data-ttu-id="810f0-124">Skriv ett värde i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="810f0-124">In the **Name** field, type a value.</span></span>
1. <span data-ttu-id="810f0-125">I fältet **ID på metadata för bedömning** välj rullgardinsmenyn för att öppna sökningen.</span><span class="sxs-lookup"><span data-stu-id="810f0-125">In the **Rating metadata ID** field, select the drop-down button to open the lookup.</span></span> <span data-ttu-id="810f0-126">ID på metadata för bedömning bestämmer vilka data som behövs för tariffhuvudet, eftersom det definierar de metadata som förväntas av transporthantering där det här tariffhuvudet används.</span><span class="sxs-lookup"><span data-stu-id="810f0-126">The rating metadata ID will determine the data needed for the rate master, as it defines the metadata expected by the transportation management engine using this rate master.</span></span>  
1. <span data-ttu-id="810f0-127">Välj alternativet P2P i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="810f0-127">For this example, select the P2P option.</span></span> <span data-ttu-id="810f0-128">Detta är redan definierat i demonstrationsdata.</span><span class="sxs-lookup"><span data-stu-id="810f0-128">This is already defined in the demo data.</span></span>
1. <span data-ttu-id="810f0-129">Klicka på länken på önskad rad i valda listan.</span><span class="sxs-lookup"><span data-stu-id="810f0-129">In the list, select the link in the selected row.</span></span>
1. <span data-ttu-id="810f0-130">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="810f0-130">Select **Save**.</span></span>

## <a name="set-up-rate-base"></a><span data-ttu-id="810f0-131">Ställa in tariffbas</span><span class="sxs-lookup"><span data-stu-id="810f0-131">Set up rate base</span></span>

1. <span data-ttu-id="810f0-132">Välj **tariffbasen**.</span><span class="sxs-lookup"><span data-stu-id="810f0-132">Select **Rate base**.</span></span>
    * <span data-ttu-id="810f0-133">Tariffbasen bestämmer tariffen för transportföretaget och kan användas för att ställa in en tariffstruktur, eftersom detta strukturerar upp tarifferna i de brytpunkter som definieras i avbrottsmallen.</span><span class="sxs-lookup"><span data-stu-id="810f0-133">The rate base determines the rate of the carrier, and can be used to set up a tariff structure as it structures the rates in the breakpoints defined in the break master.</span></span>  
2. <span data-ttu-id="810f0-134">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="810f0-134">Select **New**.</span></span>
3. <span data-ttu-id="810f0-135">Skriv ett värde i fältet **Tariffbas**.</span><span class="sxs-lookup"><span data-stu-id="810f0-135">In the **Rate base** field, type a value.</span></span>
4. <span data-ttu-id="810f0-136">Skriv ett värde i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="810f0-136">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="810f0-137">I fältet **Avbrottsmall**, välj rullgardinsmenyn för att öppna sökningen.</span><span class="sxs-lookup"><span data-stu-id="810f0-137">In the **Break master** field, select the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="810f0-138">Avbrottsmallar används för att definiera prissättningsstrukturen och dess brytpunkter.</span><span class="sxs-lookup"><span data-stu-id="810f0-138">Break masters are used to define the pricing structure and its breakpoints.</span></span> <span data-ttu-id="810f0-139">Prissättningsstrukturen använder skiftindelad prissättning som baseras på fysiska dimensioner.</span><span class="sxs-lookup"><span data-stu-id="810f0-139">The pricing structure uses tiered pricing that is based on physical dimensions.</span></span>  
6. <span data-ttu-id="810f0-140">Använd vikt i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="810f0-140">For this example, use weight.</span></span> <span data-ttu-id="810f0-141">Detta är redan definierat i demonstrationsdata.</span><span class="sxs-lookup"><span data-stu-id="810f0-141">This is already defined in the demo data.</span></span>
7. <span data-ttu-id="810f0-142">Klicka på länken på markerad rad i den listan.</span><span class="sxs-lookup"><span data-stu-id="810f0-142">In the list, select the link in the highlighted row.</span></span>
8. <span data-ttu-id="810f0-143">Expandera avsnittet **Detaljer**.</span><span class="sxs-lookup"><span data-stu-id="810f0-143">Expand the **Details** section.</span></span>
9. <span data-ttu-id="810f0-144">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="810f0-144">Select **New**.</span></span>
10. <span data-ttu-id="810f0-145">Ange "30301" i fältet **Postnummer för avlämning från**.</span><span class="sxs-lookup"><span data-stu-id="810f0-145">In the **Drop-off Postal Code From** field, type "30301".</span></span>
11. <span data-ttu-id="810f0-146">Skriv "30318" i fältet **Postnummer för avlämning till**.</span><span class="sxs-lookup"><span data-stu-id="810f0-146">In the **Drop-off Postal Code To** field, type "30318".</span></span>
12. <span data-ttu-id="810f0-147">Skriv "USA" i fältet **Avlämningsland/region**.</span><span class="sxs-lookup"><span data-stu-id="810f0-147">In the **Drop-off Country Region** field, type "USA".</span></span>
13. <span data-ttu-id="810f0-148">I fältet **<1,00 kg** skriv "100".</span><span class="sxs-lookup"><span data-stu-id="810f0-148">In the **<1.00 Lbs** field, type "100".</span></span>
    * <span data-ttu-id="810f0-149">Infoga tariffen per kilo om den totala vikten på beläggningen är mindre än 1 kilo.</span><span class="sxs-lookup"><span data-stu-id="810f0-149">Insert the rate per pounds if the total weight of the load is less than 1 pound.</span></span>  
14. <span data-ttu-id="810f0-150">I fältet **<5,00 kg** skriv "300".</span><span class="sxs-lookup"><span data-stu-id="810f0-150">In the **<5.00 Lbs** field, type "300".</span></span>
    * <span data-ttu-id="810f0-151">Infoga tariffen per kilo om den totala vikten på beläggningen är mindre än 5 kilo.</span><span class="sxs-lookup"><span data-stu-id="810f0-151">Insert the rate per pounds if the total weight of the load is less than 5 pounds.</span></span>  
15. <span data-ttu-id="810f0-152">I fältet **<20,00 kg** skriv "500".</span><span class="sxs-lookup"><span data-stu-id="810f0-152">In the **<20.00 Lbs** field, type "500".</span></span>
    * <span data-ttu-id="810f0-153">Infoga tariffen per kilo om den totala vikten på beläggningen är mindre än 20 kilo.</span><span class="sxs-lookup"><span data-stu-id="810f0-153">Insert the rate per pounds if the total weight of the load is less than 20 pounds.</span></span>  
16. <span data-ttu-id="810f0-154">I fältet **<100,00 kg** skriv "1000".</span><span class="sxs-lookup"><span data-stu-id="810f0-154">In the **<100.00 Lbs** field, type "1000".</span></span>
    * <span data-ttu-id="810f0-155">Infoga tariffen per kilo om den totala vikten på beläggningen är mindre än 100 kilo.</span><span class="sxs-lookup"><span data-stu-id="810f0-155">Insert the rate per pounds if the total weight of the load is less than 100 pounds.</span></span>  
17. <span data-ttu-id="810f0-156">I fältet **<1 000,00 kg** skriv "3000".</span><span class="sxs-lookup"><span data-stu-id="810f0-156">In the **<1,000.00 Lbs** field, type "3000".</span></span>
    * <span data-ttu-id="810f0-157">Infoga tariffen per kilo om den totala vikten på beläggningen är mindre än 1 000 kilo.</span><span class="sxs-lookup"><span data-stu-id="810f0-157">Insert the rate per pounds if the total weight of the load is less than 1000 pounds.</span></span>  
18. <span data-ttu-id="810f0-158">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="810f0-158">Select **Save**.</span></span>
19. <span data-ttu-id="810f0-159">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="810f0-159">Close the page.</span></span>

## <a name="assign-rate-base"></a><span data-ttu-id="810f0-160">Tilldela tariffbas</span><span class="sxs-lookup"><span data-stu-id="810f0-160">Assign rate base</span></span>

1. <span data-ttu-id="810f0-161">Visa avsnittet **Tilldelningar av tariffbas**.</span><span class="sxs-lookup"><span data-stu-id="810f0-161">Expand the **Rate base assignments** section.</span></span>
2. <span data-ttu-id="810f0-162">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="810f0-162">Select **New**.</span></span>
    * <span data-ttu-id="810f0-163">Du kan ha flera tilldelningar av tariffbas för varje tariffhuvud.</span><span class="sxs-lookup"><span data-stu-id="810f0-163">You can have several rate base assignments for each rate master.</span></span> <span data-ttu-id="810f0-164">På så sätt kan du skapa flera olika prispunkter för varje transportföretag beroende på mål, tjänster eller olika tariffbaser.</span><span class="sxs-lookup"><span data-stu-id="810f0-164">This makes it possible to create several different price points for each carrier depending on destinations, services, or different rate bases.</span></span> <span data-ttu-id="810f0-165">I den här proceduren kommer du endast att skapa en tariffbastilldelning.</span><span class="sxs-lookup"><span data-stu-id="810f0-165">In this procedure you will only create one rate base assignment.</span></span>  
3. <span data-ttu-id="810f0-166">Skriv ett värde i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="810f0-166">In the **Name** field, type a value.</span></span>
4. <span data-ttu-id="810f0-167">I fältet **Tariffbas**, välj rullgardinsmenyn för att öppna sökningen.</span><span class="sxs-lookup"><span data-stu-id="810f0-167">In the **Rate base** field, select the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="810f0-168">Klicka på länken på markerad rad i den listan.</span><span class="sxs-lookup"><span data-stu-id="810f0-168">In the list, select the link in the highlighted row.</span></span>
6. <span data-ttu-id="810f0-169">I fältet **Tjänst** väljer du den nedrullningsbara knappen för att öppna sökningen.</span><span class="sxs-lookup"><span data-stu-id="810f0-169">In the **Service** field, select the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="810f0-170">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="810f0-170">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="810f0-171">Klicka på länken på markerad rad i den listan.</span><span class="sxs-lookup"><span data-stu-id="810f0-171">In the list, select the link in the highlighted row.</span></span>
9. <span data-ttu-id="810f0-172">Ange "98052" i fältet **Postnummer för upphämtning**.</span><span class="sxs-lookup"><span data-stu-id="810f0-172">In the **Pick-up Postal Code** field, type "98052".</span></span>
    * <span data-ttu-id="810f0-173">Ange vilket postnummer som den här tariffbastilldelningen ska gälla från.</span><span class="sxs-lookup"><span data-stu-id="810f0-173">Specify which postal code this rate base assignment should be valid from.</span></span>
10. <span data-ttu-id="810f0-174">Skriv "USA" i fältet **Upphämtningsland/region**.</span><span class="sxs-lookup"><span data-stu-id="810f0-174">In the **Pick-up Country Region** field, type "USA".</span></span>
11. <span data-ttu-id="810f0-175">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="810f0-175">Select **Save**.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]