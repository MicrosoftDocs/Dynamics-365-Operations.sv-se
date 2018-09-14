--- 
title: "Skapa en kanban-regel för strukturlistehändelse"
description: "Denna uppgift fokuserar på inställningen som krävs för att skapa en kanban-regel för händelse för att säkerställa leverans till produktionsstrukturlisterader i ett blandat resurssnål och klassisk produktionsmiljö."
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, InventItemIdLookupSimple, ProdTableListPage, ProdTableCreate, InventItemIdLookupPurchase, ProdTable, ProdBOM, ProdParmCostEstimation
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 82a4252548fd030f2a044436ff607da5125d2854
ms.contentlocale: sv-se
ms.lasthandoff: 09/14/2018

---
# <a name="create-a-bom-line-event-kanban-rule"></a><span data-ttu-id="7c967-103">Skapa en kanban-regel för strukturlistehändelse</span><span class="sxs-lookup"><span data-stu-id="7c967-103">Create a BOM line event kanban rule</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="7c967-104">Denna uppgift fokuserar på inställningen som krävs för att skapa en kanban-regel för händelse för att säkerställa leverans till produktionsstrukturlisterader i ett blandat resurssnål och klassisk produktionsmiljö.</span><span class="sxs-lookup"><span data-stu-id="7c967-104">This task focuses on the setup needed to create an event kanban rule to ensure supply for production BOM lines in a mixed lean and classic production environment.</span></span> <span data-ttu-id="7c967-105">Det demonstrationsdataföretag som används för att skapa den här uppgiften är USMF.</span><span class="sxs-lookup"><span data-stu-id="7c967-105">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="7c967-106">Den här uppgiften är avsedd för processingenjören eller värdeströmansvarig när de förbereder tillverkningen av en ny eller ändrad produkt.</span><span class="sxs-lookup"><span data-stu-id="7c967-106">This task is intended for the process engineer or the value stream manager, as they prepare production of a new or modified product.</span></span>


## <a name="create-a-new-kanban-rule"></a><span data-ttu-id="7c967-107">Skapa en ny kanban-regel</span><span class="sxs-lookup"><span data-stu-id="7c967-107">Create a new kanban rule</span></span>
1. <span data-ttu-id="7c967-108">Gå till Produktionskontroll > Periodiska uppgifter > Kanban-kvantitetsberäkning > Kanban-regler.</span><span class="sxs-lookup"><span data-stu-id="7c967-108">Go to Production control > Periodic tasks > Kanban quantity calculation > Kanban rules.</span></span>
2. <span data-ttu-id="7c967-109">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="7c967-109">Click New.</span></span>
3. <span data-ttu-id="7c967-110">Välj "Uttag" i fältet Typ.</span><span class="sxs-lookup"><span data-stu-id="7c967-110">In the Type field, select 'Withdrawal'.</span></span>
    * <span data-ttu-id="7c967-111">Uttagstypen används för att skapa överföringskanban.</span><span class="sxs-lookup"><span data-stu-id="7c967-111">The Withdrawal type is used to create transfer kanbans.</span></span>  
4. <span data-ttu-id="7c967-112">Välj Händelse i fältet för återanskaffningsstrategi.</span><span class="sxs-lookup"><span data-stu-id="7c967-112">In the Replenishment strategy field, select 'Event'.</span></span>
    * <span data-ttu-id="7c967-113">Händelsestrategin markeras om du vill skapa överföringen av kanban baserat på en händelse.</span><span class="sxs-lookup"><span data-stu-id="7c967-113">The Event strategy is selected to create the transfer of kanbans based on an event.</span></span> <span data-ttu-id="7c967-114">Senare i uppgiftsgudien, ska vi utlösa vi den genom att beräkna en tillverkningsorder.</span><span class="sxs-lookup"><span data-stu-id="7c967-114">Later in the task guide, we will trigger it by estimating a production order.</span></span>  
5. <span data-ttu-id="7c967-115">Ange eller välj ett värde i fältet Första planaktivitet.</span><span class="sxs-lookup"><span data-stu-id="7c967-115">In the First plan activity field, enter or select a value.</span></span>
    * <span data-ttu-id="7c967-116">Ange eller välj ReplenishSpeakerComponents.</span><span class="sxs-lookup"><span data-stu-id="7c967-116">Enter or select ReplenishSpeakerComponents.</span></span> <span data-ttu-id="7c967-117">Den här överföringsaktiviteten har mottagande lagerställe (utleverans) och plats 12, vilket innebär att material ska flyttas till plats 12 på lagerställe 12.</span><span class="sxs-lookup"><span data-stu-id="7c967-117">This transfer activity has receipt (output) warehouse and location 12, which means that material will be moved to location 12 in warehouse 12.</span></span>  
6. <span data-ttu-id="7c967-118">Expandera avsnittet Detaljer.</span><span class="sxs-lookup"><span data-stu-id="7c967-118">Expand the Details section.</span></span>
7. <span data-ttu-id="7c967-119">Ange eller välj M0001 värde i fältet Produkt.</span><span class="sxs-lookup"><span data-stu-id="7c967-119">In the Product field, enter or select M0001.</span></span>
8. <span data-ttu-id="7c967-120">Expandera avsnittet Händelser.</span><span class="sxs-lookup"><span data-stu-id="7c967-120">Expand the Events section.</span></span>
9. <span data-ttu-id="7c967-121">Välj Automatisk i fältet Strukturlistehändelse.</span><span class="sxs-lookup"><span data-stu-id="7c967-121">In the BOM line event field, select 'Automatic'.</span></span>
    * <span data-ttu-id="7c967-122">Med fältet Strukturlisteradhändelse inställt på Automatisk kommer kanban att skapas för att uppfylla materialbehoven för tillverkningsorderns strukturlisterader.</span><span class="sxs-lookup"><span data-stu-id="7c967-122">With the BOM line event field set to Automatic, kanban will be created to fulfill material needs for production order BOM lines.</span></span>  
10. <span data-ttu-id="7c967-123">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="7c967-123">Close the page.</span></span>

## <a name="create-and-modify-a-new-production-order"></a><span data-ttu-id="7c967-124">Skapa och ändra en ny tillverkningsorder</span><span class="sxs-lookup"><span data-stu-id="7c967-124">Create and modify a new production order</span></span>
1. <span data-ttu-id="7c967-125">Gå till Produktionskontroll > Produktionsorder > Alla produktionsorder.</span><span class="sxs-lookup"><span data-stu-id="7c967-125">Go to Production control > Production orders > All production orders.</span></span>
2. <span data-ttu-id="7c967-126">Klicka på Ny produktionsorder.</span><span class="sxs-lookup"><span data-stu-id="7c967-126">Click New production order.</span></span>
3. <span data-ttu-id="7c967-127">Ange eller välj ett värde i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="7c967-127">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="7c967-128">Ange eller välj "'L0001".</span><span class="sxs-lookup"><span data-stu-id="7c967-128">Enter or select 'L0001'.</span></span> <span data-ttu-id="7c967-129">Vi använder artikel L0001, eftersom artikel M0001 ingår i strukturlistan för artikel L0001.</span><span class="sxs-lookup"><span data-stu-id="7c967-129">We use item L0001 because item M0001 is included in the BOM for item L0001.</span></span>  
4. <span data-ttu-id="7c967-130">Klicka på Skapa.</span><span class="sxs-lookup"><span data-stu-id="7c967-130">Click Create.</span></span>
5. <span data-ttu-id="7c967-131">Klicka på länken på raden för L0001</span><span class="sxs-lookup"><span data-stu-id="7c967-131">In the list, click the link in the row for L0001</span></span>
6. <span data-ttu-id="7c967-132">Klicka på Strukturlista.</span><span class="sxs-lookup"><span data-stu-id="7c967-132">Click BOM.</span></span>
7. <span data-ttu-id="7c967-133">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="7c967-133">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="7c967-134">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="7c967-134">Click Edit.</span></span>
9. <span data-ttu-id="7c967-135">Välj "Peggad leverans" i fältet Radtyp.</span><span class="sxs-lookup"><span data-stu-id="7c967-135">In the Line type field, select 'Pegged supply'.</span></span>
    * <span data-ttu-id="7c967-136">Peggad leverans väljs för att utlösa leveransskapelse av en kanban.</span><span class="sxs-lookup"><span data-stu-id="7c967-136">Pegged supply is selected to trigger the supply creation of a kanban.</span></span>  
10. <span data-ttu-id="7c967-137">Välj Nej i fältet Resursförbrukning.</span><span class="sxs-lookup"><span data-stu-id="7c967-137">Select No in the Resource consumption field.</span></span>
    * <span data-ttu-id="7c967-138">Om du avmarkerar kryssrutan för Resursförbrukning kan du ändra lagerstället.</span><span class="sxs-lookup"><span data-stu-id="7c967-138">Clearing the check box of Resource consumption lets us change the warehouse.</span></span>  
11. <span data-ttu-id="7c967-139">Visa avsnittet Lagerdimensioner.</span><span class="sxs-lookup"><span data-stu-id="7c967-139">Expand the Inventory dimensions section.</span></span>
12. <span data-ttu-id="7c967-140">Skriv "12" i fältet Lagerställe.</span><span class="sxs-lookup"><span data-stu-id="7c967-140">In the Warehouse field, type '12'.</span></span>
    * <span data-ttu-id="7c967-141">Lagret har är inställd på 12 eftersom det är utleveranslagerstället för uttagsaktiviteten.</span><span class="sxs-lookup"><span data-stu-id="7c967-141">Warehouse is set to 12 because this is the output warehouse for the withdrawal activity.</span></span>  
13. <span data-ttu-id="7c967-142">Skriv "12" i fältet Plats.</span><span class="sxs-lookup"><span data-stu-id="7c967-142">In the Location field, type '12'.</span></span>
    * <span data-ttu-id="7c967-143">Åöatsen är inställd på 12 eftersom det är utleveransplatsen för uttagsaktiviteten.</span><span class="sxs-lookup"><span data-stu-id="7c967-143">Location is set to 12 because this is the output location of the withdrawal activity.</span></span>  
14. <span data-ttu-id="7c967-144">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="7c967-144">Close the page.</span></span>
15. <span data-ttu-id="7c967-145">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="7c967-145">Close the page.</span></span>

## <a name="estimate-the-production-order-and-view-the-kanban-created"></a><span data-ttu-id="7c967-146">Beräkna tillverkningsordern och visa den skapade kanban</span><span class="sxs-lookup"><span data-stu-id="7c967-146">Estimate the production order and view the kanban created</span></span>
1. <span data-ttu-id="7c967-147">Klicka på Uppskattning.</span><span class="sxs-lookup"><span data-stu-id="7c967-147">Click Estimate.</span></span>
    * <span data-ttu-id="7c967-148">Beräkning av tillverkningsordern kommer att utlösa skapandet av associerade kanban för att leverera artikel M0001.</span><span class="sxs-lookup"><span data-stu-id="7c967-148">Estimating the production order will trigger the creation of the associated kanban to supply item M0001.</span></span>  
2. <span data-ttu-id="7c967-149">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="7c967-149">Click OK.</span></span>
3. <span data-ttu-id="7c967-150">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="7c967-150">Close the page.</span></span>
4. <span data-ttu-id="7c967-151">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="7c967-151">Close the page.</span></span>
5. <span data-ttu-id="7c967-152">Gå till Produktinformationshantering > Lean manufacturing > Kanban-regler.</span><span class="sxs-lookup"><span data-stu-id="7c967-152">Go to Product information management > Lean manufacturing > Kanban rules.</span></span>
6. <span data-ttu-id="7c967-153">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="7c967-153">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="7c967-154">Välj den kanban-regel för händelse som skapades för artikel M0001.</span><span class="sxs-lookup"><span data-stu-id="7c967-154">Select the event kanban rule created for item M0001.</span></span>  
7. <span data-ttu-id="7c967-155">Expandera avsnittet Kanbans.</span><span class="sxs-lookup"><span data-stu-id="7c967-155">Expand the Kanbans section.</span></span>
8. <span data-ttu-id="7c967-156">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="7c967-156">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="7c967-157">Observera de kanban som skapats för att leverera M0001 för den uppskattade tillverkningsordern.</span><span class="sxs-lookup"><span data-stu-id="7c967-157">Notice the kanban created to supply M0001 for the estimated production order.</span></span>  
    * <span data-ttu-id="7c967-158">Detta är det sista steget!</span><span class="sxs-lookup"><span data-stu-id="7c967-158">This is the last step!</span></span>  


