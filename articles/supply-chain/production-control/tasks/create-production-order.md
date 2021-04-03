---
title: Skapa en produktionsorder
description: Den här proceduren visar hur du skapar en produktionsorder.
author: johanhoffmann
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdTableListPage, ProdTableCreate, ProdTable, ProdBOM, ProdRoute, ProdJournalCreate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: dec447302da3a3bbca7d9c3e783af54bc77dfe70
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5259828"
---
# <a name="create-a-production-order"></a><span data-ttu-id="8702e-103">Skapa en produktionsorder</span><span class="sxs-lookup"><span data-stu-id="8702e-103">Create a production order</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="8702e-104">Den här proceduren visar hur du skapar en produktionsorder.</span><span class="sxs-lookup"><span data-stu-id="8702e-104">This procedure shows how to create a production order.</span></span> <span data-ttu-id="8702e-105">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="8702e-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="8702e-106">Detta är den första proceduren av sju som förklarar produktionsorderns livscykel.</span><span class="sxs-lookup"><span data-stu-id="8702e-106">This is the first procedure out of seven which explains the production order lifecycle.</span></span>


## <a name="create-a-production-order"></a><span data-ttu-id="8702e-107">Skapa en produktionsorder</span><span class="sxs-lookup"><span data-stu-id="8702e-107">Create a production order</span></span>
1. <span data-ttu-id="8702e-108">Gå till Produktionskontroll > Produktionsorder > Alla produktionsorder.</span><span class="sxs-lookup"><span data-stu-id="8702e-108">Go to Production control > Production orders > All production orders.</span></span>
2. <span data-ttu-id="8702e-109">Klicka på Ny produktionsorder.</span><span class="sxs-lookup"><span data-stu-id="8702e-109">Click New production order.</span></span>
3. <span data-ttu-id="8702e-110">Skriv "D0001" i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="8702e-110">In the Item number field, type 'D0001'.</span></span>
4. <span data-ttu-id="8702e-111">Ange ett datum i fältet Leverans.</span><span class="sxs-lookup"><span data-stu-id="8702e-111">In the Delivery field, enter a date.</span></span>
    * <span data-ttu-id="8702e-112">Leveransdatumet anger när tillverkningsordern ska vara klar för att leverera i tid.</span><span class="sxs-lookup"><span data-stu-id="8702e-112">The delivery date indicates when the production order should end in order to deliver on time.</span></span> <span data-ttu-id="8702e-113">Det här datumet kan användas i planeringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="8702e-113">This date can be used in the scheduling process.</span></span> <span data-ttu-id="8702e-114">Till exempel tidsplanering av ordern bakåt från leveransdatumet.</span><span class="sxs-lookup"><span data-stu-id="8702e-114">For example, you can schedule the order backward from the delivery date.</span></span>  
5. <span data-ttu-id="8702e-115">Ställ in kvantiteten på 20.</span><span class="sxs-lookup"><span data-stu-id="8702e-115">Set Quantity to '20'.</span></span>
    * <span data-ttu-id="8702e-116">Notering: Strukturlistnummerfältet visar automatiskt numret på alla aktiva strukturlistor för den aktuella artikeln, men du kan ändra strukturlistan för tillverkningsordern genom att markera en aktiv strukturlista i listan över godkända strukturlistversioner.</span><span class="sxs-lookup"><span data-stu-id="8702e-116">Note: The BOM number field automatically displays the number of any active BOM for the current item, but you can change the BOM for the production order by selecting an active BOM from the list of approved BOM versions.</span></span>    <span data-ttu-id="8702e-117">Flödesnummerfältet visar automatiskt numret på alla aktiva flöden för den aktuella artikeln, men du kan ändra flödet för tillverkningsordern genom att markera ett aktivt flöde i listan över godkända flödesversioner.</span><span class="sxs-lookup"><span data-stu-id="8702e-117">The Route number field automatically displays the number of any active Route for the current item, but you can change the Route for the production order by selecting an active Route from the list of approved Route versions.</span></span>  
6. <span data-ttu-id="8702e-118">Klicka på Skapa.</span><span class="sxs-lookup"><span data-stu-id="8702e-118">Click Create.</span></span>

## <a name="validate-the-production-order"></a><span data-ttu-id="8702e-119">Validera produktionsordern</span><span class="sxs-lookup"><span data-stu-id="8702e-119">Validate the production order</span></span>
1. <span data-ttu-id="8702e-120">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="8702e-120">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="8702e-121">Klicka på länken till tillverkningsordernumret som du nyss skapat.</span><span class="sxs-lookup"><span data-stu-id="8702e-121">Click the link for the production order number that you have just created.</span></span> <span data-ttu-id="8702e-122">Då öppnas detaljsidan för ordern.</span><span class="sxs-lookup"><span data-stu-id="8702e-122">This will open the details page for the order.</span></span>  
2. <span data-ttu-id="8702e-123">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="8702e-123">Click Edit.</span></span>
3. <span data-ttu-id="8702e-124">Ange ett datum i fältet Leverans.</span><span class="sxs-lookup"><span data-stu-id="8702e-124">In the Delivery field, enter a date.</span></span>
    * <span data-ttu-id="8702e-125">Till exempel ändring av leveransdatumet för produktionsordern.</span><span class="sxs-lookup"><span data-stu-id="8702e-125">For example, you can change the delivery date for the production order.</span></span>  
4. <span data-ttu-id="8702e-126">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="8702e-126">Click Save.</span></span>
5. <span data-ttu-id="8702e-127">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="8702e-127">Close the page.</span></span>

## <a name="update-the-bom"></a><span data-ttu-id="8702e-128">Uppdatera strukturlistan</span><span class="sxs-lookup"><span data-stu-id="8702e-128">Update the BOM</span></span>
1. <span data-ttu-id="8702e-129">Klicka på Produktionsorder i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="8702e-129">On the Action Pane, click Production order.</span></span>
2. <span data-ttu-id="8702e-130">Klicka på Strukturlista.</span><span class="sxs-lookup"><span data-stu-id="8702e-130">Click BOM.</span></span>
    * <span data-ttu-id="8702e-131">Öppna strukturlistsidan för att validera strukturlistdata som har kopierats från standarddata när tillverkningsordern skapades.</span><span class="sxs-lookup"><span data-stu-id="8702e-131">Open the BOM page to validate the BOM data that was copied from the default data when the production order was created.</span></span> <span data-ttu-id="8702e-132">I den här proceduren måste du uppdatera kvantiteten för en strukturlista.</span><span class="sxs-lookup"><span data-stu-id="8702e-132">In this procedure, you need to update the quantity for a BOM.</span></span>  
3. <span data-ttu-id="8702e-133">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="8702e-133">Click Edit.</span></span>
4. <span data-ttu-id="8702e-134">Ange ett tal i fältet Kvantitet.</span><span class="sxs-lookup"><span data-stu-id="8702e-134">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="8702e-135">När du ändrar kvantiteten på strukturlistraden påverkar detta kostnadsuppskattningen av materialförbrukningen för tillverkningsordern.</span><span class="sxs-lookup"><span data-stu-id="8702e-135">Changing the quantity on the BOM line affects the cost estimate of material consumption for the production order.</span></span>  
5. <span data-ttu-id="8702e-136">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="8702e-136">Click Save.</span></span>
6. <span data-ttu-id="8702e-137">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="8702e-137">Close the page.</span></span>

## <a name="update-the-production-route"></a><span data-ttu-id="8702e-138">Uppdatera produktionsflödet</span><span class="sxs-lookup"><span data-stu-id="8702e-138">Update the production route</span></span>
1. <span data-ttu-id="8702e-139">Klicka på Produktionsorder i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="8702e-139">On the Action Pane, click Production order.</span></span>
2. <span data-ttu-id="8702e-140">Klicka på Flöde.</span><span class="sxs-lookup"><span data-stu-id="8702e-140">Click Route.</span></span>
    * <span data-ttu-id="8702e-141">Öppna flödessidan för att validera data i produktionsflödet som har kopierats från standarddata när ordern skapades.</span><span class="sxs-lookup"><span data-stu-id="8702e-141">Open the Route page to validate the data of the production route that was copied from the default data when the order was created.</span></span> <span data-ttu-id="8702e-142">I den här proceduren måste du uppdatera kvantiteten för en av operationerna i produktionsflödet.</span><span class="sxs-lookup"><span data-stu-id="8702e-142">In this procedure, you need to update the quantity for one of the operations in the production route.</span></span>  
3. <span data-ttu-id="8702e-143">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="8702e-143">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="8702e-144">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="8702e-144">Click Edit.</span></span>
5. <span data-ttu-id="8702e-145">I Processkvantitets- fältet anger du ett tal.</span><span class="sxs-lookup"><span data-stu-id="8702e-145">In the Process qty. field, enter a number.</span></span>
    * <span data-ttu-id="8702e-146">När du ändrar processtiden påverkas den beräknade flödesförbrukningen och kostnaden för tillverkningsordern.</span><span class="sxs-lookup"><span data-stu-id="8702e-146">Changing the process time affects the estimated route consumption and the cost of the production order.</span></span>  
6. <span data-ttu-id="8702e-147">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="8702e-147">Click Save.</span></span>
7. <span data-ttu-id="8702e-148">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="8702e-148">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]