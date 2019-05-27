---
title: Använd säkerhetslagerjournalen för att uppdatera minimumdisponering
description: I den här proceduren visas hur du beräknar minsta disponeringsförslag som baseras på historiska transaktioner och uppdaterar sedan med artikeldisponeringen med förslagen.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqItemJournalName, ReqItemJournalSafetyStock, EcoResProductInformationDialog, EcoResProductDetailsExtended, ReqItemTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7a6e217d476cedc0318c382e12b7dc2036e557c3
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1571437"
---
# <a name="use-the-safety-stock-journal-to-update-minimum-coverage"></a><span data-ttu-id="70d5a-103">Använd säkerhetslagerjournalen för att uppdatera minimumdisponering</span><span class="sxs-lookup"><span data-stu-id="70d5a-103">Use the safety stock journal to update minimum coverage</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="70d5a-104">I den här proceduren visas hur du beräknar minsta disponeringsförslag som baseras på historiska transaktioner och uppdaterar sedan med artikeldisponeringen med förslagen.</span><span class="sxs-lookup"><span data-stu-id="70d5a-104">This procedure shows how to calculate minimum coverage proposals based on historical transactions and then update the item coverage with the proposals.</span></span> <span data-ttu-id="70d5a-105">Detta görs med hjälp av säkerhetslagerjournalen.</span><span class="sxs-lookup"><span data-stu-id="70d5a-105">This is done using the safety stock journal.</span></span> <span data-ttu-id="70d5a-106">Det demonstrationsdataföretag som används för att skapa den här uppgiften är USMF.</span><span class="sxs-lookup"><span data-stu-id="70d5a-106">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="70d5a-107">Denna uppgift är avsedd för produktionsplaneraren för att hjälpa till att bibehålla minsta disponering.</span><span class="sxs-lookup"><span data-stu-id="70d5a-107">This task is intended for the production planner, to help maintain minimum coverage.</span></span>


## <a name="create-a-new-safety-stock-journal-name"></a><span data-ttu-id="70d5a-108">Skapa ett nytt namn på säkerhetslagerjournal.</span><span class="sxs-lookup"><span data-stu-id="70d5a-108">Create a new safety stock journal name</span></span>
1. <span data-ttu-id="70d5a-109">Gå till Namn på säkerhetslagerjournal.</span><span class="sxs-lookup"><span data-stu-id="70d5a-109">Go to Safety stock journal names.</span></span>
2. <span data-ttu-id="70d5a-110">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="70d5a-110">Click New.</span></span>
3. <span data-ttu-id="70d5a-111">Ange "Material" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="70d5a-111">In the Name field, type 'Material'.</span></span>
4. <span data-ttu-id="70d5a-112">Ange "Material" i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="70d5a-112">In the Description field, type 'Material'.</span></span>
5. <span data-ttu-id="70d5a-113">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="70d5a-113">Close the page.</span></span>

## <a name="create-a-safety-stock-journal"></a><span data-ttu-id="70d5a-114">Skapa en säkerhetslagerjournal</span><span class="sxs-lookup"><span data-stu-id="70d5a-114">Create a safety stock journal</span></span>
1. <span data-ttu-id="70d5a-115">Gå till Beräkning av säkerhetslager.</span><span class="sxs-lookup"><span data-stu-id="70d5a-115">Go to Safety stock calculation.</span></span>
2. <span data-ttu-id="70d5a-116">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="70d5a-116">Click New.</span></span>
3. <span data-ttu-id="70d5a-117">Ange eller välj ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="70d5a-117">In the Name field, enter or select a value.</span></span>
    * <span data-ttu-id="70d5a-118">Välj det säkerhetslagerjournalnamn som du har skapaat, t.ex. Material.</span><span class="sxs-lookup"><span data-stu-id="70d5a-118">Select the safety stock journal name that you created, for example, Material.</span></span>  
4. <span data-ttu-id="70d5a-119">Klicka på Skapa rader.</span><span class="sxs-lookup"><span data-stu-id="70d5a-119">Click Create lines.</span></span>
5. <span data-ttu-id="70d5a-120">Ange ett datum i fältet Från datum.</span><span class="sxs-lookup"><span data-stu-id="70d5a-120">In the From date field, enter a date.</span></span>
    * <span data-ttu-id="70d5a-121">Ange datumet till "2015-01-02".</span><span class="sxs-lookup"><span data-stu-id="70d5a-121">Set the date to '2015-01-02'.</span></span>  
6. <span data-ttu-id="70d5a-122">Ange ett datum i fältet Till datum.</span><span class="sxs-lookup"><span data-stu-id="70d5a-122">In the To date field, enter a date.</span></span>
    * <span data-ttu-id="70d5a-123">Ange datumet till "2015-12-30".</span><span class="sxs-lookup"><span data-stu-id="70d5a-123">Set the date to '2015-12-30'.</span></span>  
7. <span data-ttu-id="70d5a-124">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="70d5a-124">Click OK.</span></span>
    * <span data-ttu-id="70d5a-125">Detta skapar rader för dimensionerna som har lagertransaktioner.</span><span class="sxs-lookup"><span data-stu-id="70d5a-125">This will create lines for the dimensions that have inventory transactions.</span></span>  

## <a name="calculate-proposal"></a><span data-ttu-id="70d5a-126">Beräkna förslag</span><span class="sxs-lookup"><span data-stu-id="70d5a-126">Calculate proposal</span></span>
1. <span data-ttu-id="70d5a-127">Klicka på Beräkna förslag.</span><span class="sxs-lookup"><span data-stu-id="70d5a-127">Click Calculate proposal.</span></span>
2. <span data-ttu-id="70d5a-128">Välj alternativet Use average issue during lead time.</span><span class="sxs-lookup"><span data-stu-id="70d5a-128">Select the Use average issue during lead time option.</span></span>
3. <span data-ttu-id="70d5a-129">Ange Multiplikationsfaktorn till "10".</span><span class="sxs-lookup"><span data-stu-id="70d5a-129">Set Multiplication factor to '10'.</span></span>
    * <span data-ttu-id="70d5a-130">Multiplikationsfaktorn används för att justera förslaget.</span><span class="sxs-lookup"><span data-stu-id="70d5a-130">The Multiply factor is used to adjust the proposal.</span></span> <span data-ttu-id="70d5a-131">Eftersom demodata bara har några transaktioner, måste du ange faktorn för att få ett realistiskt förslag.</span><span class="sxs-lookup"><span data-stu-id="70d5a-131">Because demo data only has a few transactions, you will need to set the factor to get a realistic proposal.</span></span>  
4. <span data-ttu-id="70d5a-132">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="70d5a-132">Click OK.</span></span>
    * <span data-ttu-id="70d5a-133">Bläddra ned för att hitta M0002 och M0003.</span><span class="sxs-lookup"><span data-stu-id="70d5a-133">Scroll down to find M0002 and M0003.</span></span> <span data-ttu-id="70d5a-134">Visa kolumnen Beräknad minsta kvantitet.</span><span class="sxs-lookup"><span data-stu-id="70d5a-134">View the Calculated minimum quantity column.</span></span>   

## <a name="update-minimum-quantity"></a><span data-ttu-id="70d5a-135">Uppdatera minsta kvantitet</span><span class="sxs-lookup"><span data-stu-id="70d5a-135">Update minimum quantity</span></span>
1. <span data-ttu-id="70d5a-136">Ange ett nummer i fältet Ny minsta kvantitet.</span><span class="sxs-lookup"><span data-stu-id="70d5a-136">In the New minimum quantity field, enter a number.</span></span>
    * <span data-ttu-id="70d5a-137">Uppdatera den Nya minsta kvantiteten till att matcha värdet i Beräknad minsta kvantitet.</span><span class="sxs-lookup"><span data-stu-id="70d5a-137">Update the New minimum quantity to match the value in the Calculated minimum quantity.</span></span> <span data-ttu-id="70d5a-138">Om det beräknade minimivärdet är noll, kan du ange önskat framtida värde.</span><span class="sxs-lookup"><span data-stu-id="70d5a-138">If the Calculated minimum is zero,  you can enter the desired future value.</span></span> <span data-ttu-id="70d5a-139">Du kan till exempel ange den beräknade minimikvantiteten i det här fältet för M0002 som har lagerställe 12.</span><span class="sxs-lookup"><span data-stu-id="70d5a-139">For example, you can enter the Calculated minimum quantity in this field for M0002 that has warehouse 12.</span></span>  
2. <span data-ttu-id="70d5a-140">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="70d5a-140">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="70d5a-141">Du kan till exempel välja M0002 som har lagerstället 12.</span><span class="sxs-lookup"><span data-stu-id="70d5a-141">For example, you can select M0002 that has warehouse 12.</span></span>  
3. <span data-ttu-id="70d5a-142">Ange ett nummer i fältet Ny minsta kvantitet.</span><span class="sxs-lookup"><span data-stu-id="70d5a-142">In the New minimum quantity field, enter a number.</span></span>
    * <span data-ttu-id="70d5a-143">Uppdatera den Nya minsta kvantiteten till att matcha värdet i Beräknad minsta kvantitet.</span><span class="sxs-lookup"><span data-stu-id="70d5a-143">Update the New minimum quantity to match the value in the Calculated minimum quantity.</span></span> <span data-ttu-id="70d5a-144">Om det beräknade minimivärdet är noll, kan du ange önskat framtida värde.</span><span class="sxs-lookup"><span data-stu-id="70d5a-144">If the Calculated minimum is zero you can enter the desired future value.</span></span>  

## <a name="post-the-new-minimum-quantity-and-validate-the-result"></a><span data-ttu-id="70d5a-145">Bokför den nya minsta kvantiteten och verifiera resultatet</span><span class="sxs-lookup"><span data-stu-id="70d5a-145">Post the new minimum quantity and validate the result</span></span>
1. <span data-ttu-id="70d5a-146">Klicka på Bokför.</span><span class="sxs-lookup"><span data-stu-id="70d5a-146">Click Post.</span></span>
2. <span data-ttu-id="70d5a-147">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="70d5a-147">Click OK.</span></span>
3. <span data-ttu-id="70d5a-148">Klicka för att följa länken i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="70d5a-148">Click to follow the link in the Item number field.</span></span>
4. <span data-ttu-id="70d5a-149">Klicka för att följa länken i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="70d5a-149">Click to follow the link in the Item number field.</span></span>
5. <span data-ttu-id="70d5a-150">Klicka på Plan i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="70d5a-150">On the Action Pane, click Plan.</span></span>
6. <span data-ttu-id="70d5a-151">Klicka på Artikeldisponering.</span><span class="sxs-lookup"><span data-stu-id="70d5a-151">Click Item coverage.</span></span>
    * <span data-ttu-id="70d5a-152">Observera att den minsta kvantiteten har uppdaterats med den nya minsta kvantiteten från säkerhetslagerjournalen.</span><span class="sxs-lookup"><span data-stu-id="70d5a-152">Notice that the Minimum quantity has been updated with the new minimum quantity from the safety stock journal.</span></span>  

