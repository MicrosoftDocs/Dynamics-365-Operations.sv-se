---
title: Skapa en produktionsflödesversion
description: Den här proceduren fokuserar på att skapa en ny produktionsflödesversion.
author: cvocph
manager: AnnBe
ms.date: 11/03/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5512c30be586c75d2571d60588a1179c0d47570b
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "3147007"
---
# <a name="create-a-production-flow-version"></a><span data-ttu-id="c71c4-103">Skapa en produktionsflödesversion</span><span class="sxs-lookup"><span data-stu-id="c71c4-103">Create a production flow version</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c71c4-104">Den här proceduren fokuserar på att skapa en ny produktionsflödesversion.</span><span class="sxs-lookup"><span data-stu-id="c71c4-104">This procedure focuses on creating a new production flow version.</span></span> <span data-ttu-id="c71c4-105">För den här proceduren måste produktionsparametrarna för lean manufacturing och måttenheterna för klasstid definieras.</span><span class="sxs-lookup"><span data-stu-id="c71c4-105">For this procedure, the production parameters for lean manufacturing and the units of measurement for class time must be defined.</span></span> <span data-ttu-id="c71c4-106">Du måste också definiera en värdeström och en produktionsgrupp.</span><span class="sxs-lookup"><span data-stu-id="c71c4-106">You also need to define a value stream and a production group.</span></span> <span data-ttu-id="c71c4-107">Mer information om produktionsflöden och aktiviteter i lean manufacturing finns i dokumentationen om lean manufacturing för Microsoft Dynamics AX.</span><span class="sxs-lookup"><span data-stu-id="c71c4-107">To learn more about production flows and activities in lean manufacturing, see the white papers on Lean manufacturing for Microsoft Dynamics AX.</span></span> <span data-ttu-id="c71c4-108">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="c71c4-108">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-a-production-flow"></a><span data-ttu-id="c71c4-109">Skapa ett produktionsflöde</span><span class="sxs-lookup"><span data-stu-id="c71c4-109">Create a production flow</span></span>
1. <span data-ttu-id="c71c4-110">Gå till Produktionskontroll > Inställningar > Lean-produktionsflöde > Produktionsflöden.</span><span class="sxs-lookup"><span data-stu-id="c71c4-110">Go to Production control > Setup > Lean production flow > Production flows.</span></span>
2. <span data-ttu-id="c71c4-111">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="c71c4-111">Click New.</span></span>
3. <span data-ttu-id="c71c4-112">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="c71c4-112">In the Name field, type a value.</span></span>
4. <span data-ttu-id="c71c4-113">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="c71c4-113">In the Description field, type a value.</span></span>
5. <span data-ttu-id="c71c4-114">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="c71c4-114">In the Name field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="c71c4-115">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="c71c4-115">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="c71c4-116">Välj en driftenhet av typen Värdeström.</span><span class="sxs-lookup"><span data-stu-id="c71c4-116">Select an operating unit of type value stream.</span></span> <span data-ttu-id="c71c4-117">En värdeström är en driftenhet som sträcker sig över alla aktiviteter och flöden för värdeströmmen.</span><span class="sxs-lookup"><span data-stu-id="c71c4-117">A value stream is an operating unit that spans all activities and flows of the value stream.</span></span> <span data-ttu-id="c71c4-118">I den här fasen är driftenheter begränsade till en juridisk person och har ingen ytterligare funktion.</span><span class="sxs-lookup"><span data-stu-id="c71c4-118">At this stage, operating units are limited to a legal entity and have no further functionality.</span></span>  
7. <span data-ttu-id="c71c4-119">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Produktionsgrupp.</span><span class="sxs-lookup"><span data-stu-id="c71c4-119">In the Production group field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="c71c4-120">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="c71c4-120">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="c71c4-121">Välj en produktionsgrupp för produktionsflödet.</span><span class="sxs-lookup"><span data-stu-id="c71c4-121">Select a production group for the production flow.</span></span> <span data-ttu-id="c71c4-122">Produktionsgrupper gör att du kan definiera material, arbete och PIA-konton för en produktionsprocess.</span><span class="sxs-lookup"><span data-stu-id="c71c4-122">Production groups allow the definition of material, labor, and WIP accounts for a production process.</span></span> <span data-ttu-id="c71c4-123">Om du vill koppla redovisningskontexten till ett produktionsflöde måste en produktionsgrupp har valts.</span><span class="sxs-lookup"><span data-stu-id="c71c4-123">To associate the accounting context to a production flow, a production group must be selected.</span></span>  
9. <span data-ttu-id="c71c4-124">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="c71c4-124">Click Save.</span></span>

## <a name="create-a-production-flow-version"></a><span data-ttu-id="c71c4-125">Skapa en produktionsflödesversion</span><span class="sxs-lookup"><span data-stu-id="c71c4-125">Create a production flow version</span></span>
1. <span data-ttu-id="c71c4-126">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="c71c4-126">Click Add.</span></span>
2. <span data-ttu-id="c71c4-127">I fältet Utgångsdatum anger du datum och tid.</span><span class="sxs-lookup"><span data-stu-id="c71c4-127">In the Expiration date field, enter a date and time.</span></span>
    * <span data-ttu-id="c71c4-128">Definiera ett utgångsdatum för versionen om det behövs.</span><span class="sxs-lookup"><span data-stu-id="c71c4-128">If required, define an Expiration date for the version.</span></span> <span data-ttu-id="c71c4-129">Du kan uppdatera det när du vill, även för aktiva versioner.</span><span class="sxs-lookup"><span data-stu-id="c71c4-129">You can update it at any given time, even for active versions.</span></span> <span data-ttu-id="c71c4-130">Du kan använda det för att planera utfasningen av en version.</span><span class="sxs-lookup"><span data-stu-id="c71c4-130">You can use it to plan to phase out a version.</span></span>  
3. <span data-ttu-id="c71c4-131">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="c71c4-131">Click OK.</span></span>
4. <span data-ttu-id="c71c4-132">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="c71c4-132">In the list, mark the selected row.</span></span>
5. <span data-ttu-id="c71c4-133">Skriv ett värde i fältet Enhet.</span><span class="sxs-lookup"><span data-stu-id="c71c4-133">In the Unit field, type a value.</span></span>
6. <span data-ttu-id="c71c4-134">ResolveChanges taktenheten.</span><span class="sxs-lookup"><span data-stu-id="c71c4-134">ResolveChanges the Takt unit.</span></span>
7. <span data-ttu-id="c71c4-135">Ange ett värde i fältet Genomsnittlig takttid.</span><span class="sxs-lookup"><span data-stu-id="c71c4-135">In the Average takt time field, enter a number.</span></span>
    * <span data-ttu-id="c71c4-136">Definiera den genomsnittliga takttiden för versionen.</span><span class="sxs-lookup"><span data-stu-id="c71c4-136">Define the Average takt time of the version.</span></span> <span data-ttu-id="c71c4-137">Definiera en riktad genomsnittlig takttid för taktkontrollen för produktionsflödesversionen.</span><span class="sxs-lookup"><span data-stu-id="c71c4-137">For the takt control of the production flow version, define a targeted average takt time.</span></span> <span data-ttu-id="c71c4-138">Takttiden definieras som kvantitet per tidsperiod.</span><span class="sxs-lookup"><span data-stu-id="c71c4-138">The takt is defined as quantity per time period.</span></span> <span data-ttu-id="c71c4-139">I exemplet är takttiden 0,2 timmar per 10 enheter.</span><span class="sxs-lookup"><span data-stu-id="c71c4-139">In the example, the takt time is 0.2 hours per 10 pieces.</span></span> <span data-ttu-id="c71c4-140">För en arbetstid på 8 timmar motsvarar detta en daglig genomflödeskapacitet på 400 enheter.</span><span class="sxs-lookup"><span data-stu-id="c71c4-140">For a working time of 8 hours, this corresponds to a daily throughput capacity of 400 pieces.</span></span>  
8. <span data-ttu-id="c71c4-141">Ange ett värde i fältet Kvantitet per cykel.</span><span class="sxs-lookup"><span data-stu-id="c71c4-141">In the Quantity per cycle field, enter a number.</span></span>
    * <span data-ttu-id="c71c4-142">Definiera kvantiteten per cykel relaterat till den genomsnittliga takttiden.</span><span class="sxs-lookup"><span data-stu-id="c71c4-142">Define the quantity per cycle related to the Average takt time.</span></span>  
9. <span data-ttu-id="c71c4-143">Växla utökningen av avsnittet Versionsdetaljer.</span><span class="sxs-lookup"><span data-stu-id="c71c4-143">Toggle the expansion of the Version details section.</span></span>
10. <span data-ttu-id="c71c4-144">Ange ett värde i fältet Minimal takttid.</span><span class="sxs-lookup"><span data-stu-id="c71c4-144">In the Minimum takt time field, enter a number.</span></span>
    * <span data-ttu-id="c71c4-145">Definiera den lägsta takttiden.</span><span class="sxs-lookup"><span data-stu-id="c71c4-145">Define the minimum takt time.</span></span> <span data-ttu-id="c71c4-146">Den minsta takttiden måste vara mindre än eller lika med den genomsnittliga takttiden.</span><span class="sxs-lookup"><span data-stu-id="c71c4-146">The minimum takt time must be less than or equal to the average takt time.</span></span>  
11. <span data-ttu-id="c71c4-147">Ange ett värde i fältet Maximal takttid.</span><span class="sxs-lookup"><span data-stu-id="c71c4-147">In the Maximum takt time field, enter a number.</span></span>
    * <span data-ttu-id="c71c4-148">Den högsta takttiden måste vara större än eller lika med den genomsnittliga takttiden.</span><span class="sxs-lookup"><span data-stu-id="c71c4-148">The maximum takt time must be higher than or equal to the Average takt time.</span></span>  
12. <span data-ttu-id="c71c4-149">Ange ett värde i fältet Period för faktisk cykeltid (dagar).</span><span class="sxs-lookup"><span data-stu-id="c71c4-149">In the Period for actual cycle time (days) field, enter a number.</span></span>
    * <span data-ttu-id="c71c4-150">Ange antalet dagar i Period för faktisk cykeltid.</span><span class="sxs-lookup"><span data-stu-id="c71c4-150">Enter the number of days in the Period for actual cycle time.</span></span> <span data-ttu-id="c71c4-151">Perioden för faktisk cykeltid är antalet dagar då jobb läggs till från den faktiska tiden (minuter) bakåt för att beräkna den faktiska cykeltiden.</span><span class="sxs-lookup"><span data-stu-id="c71c4-151">The period for actual cycle time is the number of days that jobs are aggregated from the actual minute backwards to calculate the actual cycle time.</span></span> <span data-ttu-id="c71c4-152">Värdet kan när som helst ändras och används endast för beräkningen av de faktiska cykeltiderna.</span><span class="sxs-lookup"><span data-stu-id="c71c4-152">The value can be changed at any time and is only used for the calculation of the actual cycle times.</span></span>  
13. <span data-ttu-id="c71c4-153">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="c71c4-153">Click Save.</span></span>

