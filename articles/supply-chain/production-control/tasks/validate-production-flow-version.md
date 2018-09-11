--- 
title: "Validera produktionsflöde och version"
description: "Den här proceduren visar hur du skapar ett nytt produktionsflöde och en första version för lean manufacturing."
author: ChristianRytt
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LeanProductionFlow
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 32d71167fdad65cb1dec37671999a497759ca484
ms.openlocfilehash: 555a7564c3fc976bdf89d2295518ba9f687e258d
ms.contentlocale: sv-se
ms.lasthandoff: 09/11/2018

---
# <a name="validate-a-production-flow-and-version"></a><span data-ttu-id="95a57-103">Validera produktionsflöde och version</span><span class="sxs-lookup"><span data-stu-id="95a57-103">Validate a production flow and version</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="95a57-104">Den här proceduren visar hur du skapar ett nytt produktionsflöde och en första version för lean manufacturing.</span><span class="sxs-lookup"><span data-stu-id="95a57-104">This procedure shows how to create a new production flow and a first version for lean manufacturing.</span></span> <span data-ttu-id="95a57-105">Förutsättningar: Produktionsparametrarna för lean manufacturing och måttenheterna för klasstid måste definieras.</span><span class="sxs-lookup"><span data-stu-id="95a57-105">Prerequisites: The production parameters for Lean manufacturing and the units of measure for class time must be defined.</span></span> <span data-ttu-id="95a57-106">Du måste definiera en värdeström och en produktionsgrupp.</span><span class="sxs-lookup"><span data-stu-id="95a57-106">You need to define a Value stream and a Production group.</span></span> <span data-ttu-id="95a57-107">Läs vitböckerna om lean manufacturing och bekanta dig med begreppen i produktionsflöden och aktiviteter.</span><span class="sxs-lookup"><span data-stu-id="95a57-107">Refer to the white papers on Lean manufacturing to familiarize yourself with the concepts of production flows and activities.</span></span> <span data-ttu-id="95a57-108">Den här proceduren refererar till den juridiska personen USMF i demodata.</span><span class="sxs-lookup"><span data-stu-id="95a57-108">This procedure refers to the legal entity USMF in demo data.</span></span> <span data-ttu-id="95a57-109">Men, under antagandet att den juridiska personen har konfigurerats för lean manufacturing, kan andra juridiska personer användas.</span><span class="sxs-lookup"><span data-stu-id="95a57-109">However, assuming that the legal entity is configured for Lean manufacturing, other legal entities can be used.</span></span>


## <a name="create-a-production-flow"></a><span data-ttu-id="95a57-110">Skapa ett produktionsflöde</span><span class="sxs-lookup"><span data-stu-id="95a57-110">Create a production flow</span></span>
1. <span data-ttu-id="95a57-111">Gå till Produktionskontroll > Inställningar > Lean-produktionsflöde > Produktionsflöden.</span><span class="sxs-lookup"><span data-stu-id="95a57-111">Go to Production control > Setup > Lean production flow > Production flows.</span></span>
2. <span data-ttu-id="95a57-112">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="95a57-112">Click New.</span></span>
3. <span data-ttu-id="95a57-113">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="95a57-113">In the Name field, type a value.</span></span>
4. <span data-ttu-id="95a57-114">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="95a57-114">In the Description field, type a value.</span></span>
5. <span data-ttu-id="95a57-115">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="95a57-115">In the Name field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="95a57-116">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="95a57-116">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="95a57-117">En värdeström är en driftenhet som sträcker sig över alla aktiviteter och flöden för värdeströmmen.</span><span class="sxs-lookup"><span data-stu-id="95a57-117">A value stream is an operating unit that spans over all activities and flows of the value stream.</span></span>   <span data-ttu-id="95a57-118">I den här fasen är driftenheter begränsade till en juridisk person och har ingen ytterligare funktion.</span><span class="sxs-lookup"><span data-stu-id="95a57-118">At this stage, operating units are limited to a legal entity and have no further functionality.</span></span>  
7. <span data-ttu-id="95a57-119">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Produktionsgrupp.</span><span class="sxs-lookup"><span data-stu-id="95a57-119">In the Production group field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="95a57-120">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="95a57-120">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="95a57-121">Produktionsgrupper gör att du kan definiera material, arbete och PIA-konton för en produktionsprocess.</span><span class="sxs-lookup"><span data-stu-id="95a57-121">Production groups allow the definition of material, labor, and WIP accounts for a production process.</span></span> <span data-ttu-id="95a57-122">Om du vill koppla redovisningskontexten till ett produktionsflöde måste en produktionsgrupp har valts.</span><span class="sxs-lookup"><span data-stu-id="95a57-122">To associate the accounting context to a production flow, a production group must be selected.</span></span>  
9. <span data-ttu-id="95a57-123">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="95a57-123">Click Save.</span></span>

## <a name="create-a-production-flow-version"></a><span data-ttu-id="95a57-124">Skapa en produktionsflödesversion</span><span class="sxs-lookup"><span data-stu-id="95a57-124">Create a production flow version</span></span>
1. <span data-ttu-id="95a57-125">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="95a57-125">Click Add.</span></span>
2. <span data-ttu-id="95a57-126">I fältet Utgångsdatum anger du datum och tid.</span><span class="sxs-lookup"><span data-stu-id="95a57-126">In the Expiration date field, enter a date and time.</span></span>
    * <span data-ttu-id="95a57-127">Du kan uppdatera sista giltighetsdatumet för versionen när du vill, även för aktiva versioner.</span><span class="sxs-lookup"><span data-stu-id="95a57-127">You can update the Expiration date of the version at any given time, even for active versions.</span></span> <span data-ttu-id="95a57-128">Använd förfallodatumet för versionen för att planera för utfasningen av en version.</span><span class="sxs-lookup"><span data-stu-id="95a57-128">Use the expiration of the version to plan for a phase out of a version.</span></span>  
3. <span data-ttu-id="95a57-129">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="95a57-129">Click OK.</span></span>
4. <span data-ttu-id="95a57-130">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="95a57-130">In the list, mark the selected row.</span></span>
5. <span data-ttu-id="95a57-131">Skriv ett värde i fältet Enhet.</span><span class="sxs-lookup"><span data-stu-id="95a57-131">In the Unit field, type a value.</span></span>
6. <span data-ttu-id="95a57-132">Välj taktenheten.</span><span class="sxs-lookup"><span data-stu-id="95a57-132">Select the Takt unit.</span></span>
7. <span data-ttu-id="95a57-133">Ange ett värde i fältet Genomsnittlig takttid.</span><span class="sxs-lookup"><span data-stu-id="95a57-133">In the Average takt time field, enter a number.</span></span>
    * <span data-ttu-id="95a57-134">Definiera en riktad genomsnittlig takttid för taktkontrollen för produktionsflödesversionen.</span><span class="sxs-lookup"><span data-stu-id="95a57-134">For the takt control of the production flow version, define a targeted average takt time.</span></span>   <span data-ttu-id="95a57-135">Takttiden definieras som kvantitet per tidsperiod.</span><span class="sxs-lookup"><span data-stu-id="95a57-135">The takt is defined as quantity  per time period.</span></span>  <span data-ttu-id="95a57-136">I exemplet är takttiden 0,2 timmar per 10 enheter.</span><span class="sxs-lookup"><span data-stu-id="95a57-136">In the given example, the takt time is 0.2 hours per 10 pieces.</span></span> <span data-ttu-id="95a57-137">För en arbetstid på 8 timmar motsvarar detta en daglig genomflödeskapacitet på 400 enheter.</span><span class="sxs-lookup"><span data-stu-id="95a57-137">For a working time of 8 hours, this corresponds to a daily throughput capacity of 400 pieces.</span></span>  
8. <span data-ttu-id="95a57-138">Ange ett värde i fältet Kvantitet per cykel.</span><span class="sxs-lookup"><span data-stu-id="95a57-138">In the Quantity per cycle field, enter a number.</span></span>
9. <span data-ttu-id="95a57-139">Expandera eller dölj avsnittet Versionsdetaljer.</span><span class="sxs-lookup"><span data-stu-id="95a57-139">Expand or collapse the Version details section.</span></span>
10. <span data-ttu-id="95a57-140">Ange ett värde i fältet Minimal takttid.</span><span class="sxs-lookup"><span data-stu-id="95a57-140">In the Minimum takt time field, enter a number.</span></span>
    * <span data-ttu-id="95a57-141">Den minsta takttiden måste vara mindre än eller lika med den genomsnittliga takttiden.</span><span class="sxs-lookup"><span data-stu-id="95a57-141">The minimum takt time must be less than or equal to the average takt time.</span></span>  
11. <span data-ttu-id="95a57-142">Ange ett värde i fältet Maximal takttid.</span><span class="sxs-lookup"><span data-stu-id="95a57-142">In the Maximum takt time field, enter a number.</span></span>
    * <span data-ttu-id="95a57-143">Den högsta takttiden måste vara större än eller lika med den genomsnittliga takttiden.</span><span class="sxs-lookup"><span data-stu-id="95a57-143">The maximum takt time must be higher than or equal to the Average takt time.</span></span>  
12. <span data-ttu-id="95a57-144">Ange antal dagar i Period för faktisk cykeltid</span><span class="sxs-lookup"><span data-stu-id="95a57-144">Enter a number of days in the Period for actual cycle time</span></span>
    * <span data-ttu-id="95a57-145">Perioden för faktisk cykeltid är antalet dagar då jobb läggs till från den faktiska tiden (minuter) bakåt för att beräkna den faktiska cykeltiden.</span><span class="sxs-lookup"><span data-stu-id="95a57-145">The period for actual cycle time is the number of days that jobs are aggregated from the actual minute backwards to calculate the actual cycle time.</span></span> <span data-ttu-id="95a57-146">Värdet kan när som helst ändras och används endast för beräkningen av de faktiska cykeltiderna.</span><span class="sxs-lookup"><span data-stu-id="95a57-146">The value can be changed at any time and is only used for the calculation of the actual cycle times.</span></span>  
13. <span data-ttu-id="95a57-147">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="95a57-147">Click Save.</span></span>


