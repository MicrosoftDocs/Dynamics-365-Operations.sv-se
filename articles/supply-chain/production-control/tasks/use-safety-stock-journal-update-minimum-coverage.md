---
title: Använd säkerhetslagerjournalen för att uppdatera minimumdisponering
description: I den här proceduren visas hur du beräknar minsta disponeringsförslag som baseras på historiska transaktioner och uppdaterar sedan med artikeldisponeringen med förslagen.
author: ChristianRytt
manager: AnnBe
ms.date: 08/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqItemJournalName, ReqItemJournalSafetyStock, EcoResProductInformationDialog, EcoResProductDetailsExtended, ReqItemTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1624f84db10ea7cc80bb94757f19484b8c403c5c
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "3148791"
---
# <a name="use-the-safety-stock-journal-to-update-minimum-coverage"></a><span data-ttu-id="3f358-103">Använd säkerhetslagerjournalen för att uppdatera minimumdisponering</span><span class="sxs-lookup"><span data-stu-id="3f358-103">Use the safety stock journal to update minimum coverage</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3f358-104">I den här proceduren visas hur du beräknar minsta disponeringsförslag som baseras på historiska transaktioner och uppdaterar sedan med artikeldisponeringen med förslagen.</span><span class="sxs-lookup"><span data-stu-id="3f358-104">This procedure shows how to calculate minimum coverage proposals based on historical transactions and then update the item coverage with the proposals.</span></span> <span data-ttu-id="3f358-105">Detta görs med hjälp av säkerhetslagerjournalen.</span><span class="sxs-lookup"><span data-stu-id="3f358-105">This is done using the safety stock journal.</span></span> <span data-ttu-id="3f358-106">Det demonstrationsdataföretag som används för att skapa den här uppgiften är USMF.</span><span class="sxs-lookup"><span data-stu-id="3f358-106">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="3f358-107">Denna uppgift är avsedd för produktionsplaneraren för att hjälpa till att bibehålla minsta disponering.</span><span class="sxs-lookup"><span data-stu-id="3f358-107">This task is intended for the production planner, to help maintain minimum coverage.</span></span>


## <a name="create-a-new-safety-stock-journal-name"></a><span data-ttu-id="3f358-108">Skapa ett nytt namn på säkerhetslagerjournal.</span><span class="sxs-lookup"><span data-stu-id="3f358-108">Create a new safety stock journal name</span></span>
1. <span data-ttu-id="3f358-109">I **navigeringfönstret**, gå till **Huvudplanering > Inställningar > Namn på säkerhetslagerjournal**.</span><span class="sxs-lookup"><span data-stu-id="3f358-109">In the **Navigation pane**, go to **Master planning > Setup > Safety stock journal names**.</span></span>
2. <span data-ttu-id="3f358-110">Klicka på **Ny**.</span><span class="sxs-lookup"><span data-stu-id="3f358-110">Click **New**.</span></span>
3. <span data-ttu-id="3f358-111">Ange "Material" i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="3f358-111">In the **Name** field, type 'Material'.</span></span>
4. <span data-ttu-id="3f358-112">Ange "Material" i fältet **Beskrivning**.</span><span class="sxs-lookup"><span data-stu-id="3f358-112">In the **Description** field, type 'Material'.</span></span>
5. <span data-ttu-id="3f358-113">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="3f358-113">Close the page.</span></span>

## <a name="create-a-safety-stock-journal"></a><span data-ttu-id="3f358-114">Skapa en säkerhetslagerjournal</span><span class="sxs-lookup"><span data-stu-id="3f358-114">Create a safety stock journal</span></span>
1. <span data-ttu-id="3f358-115">I **navigeringfönstret**, gå till **Huvudplanering > Huvudplanering > Kör > Beräkning av säkerhetslager**.</span><span class="sxs-lookup"><span data-stu-id="3f358-115">In the **Navigation pane**, go to **Master planning > Master planning > Run > Safety stock calculation**.</span></span>
2. <span data-ttu-id="3f358-116">Klicka på **Ny**.</span><span class="sxs-lookup"><span data-stu-id="3f358-116">Click **New**.</span></span>
3. <span data-ttu-id="3f358-117">I fältet **Namn**anger eller väljer du ett värde.</span><span class="sxs-lookup"><span data-stu-id="3f358-117">In the **Name** field, enter or select a value.</span></span> <span data-ttu-id="3f358-118">Välj det säkerhetslagerjournalnamn som du har skapaat, t.ex. Material.</span><span class="sxs-lookup"><span data-stu-id="3f358-118">Select the safety stock journal name that you created, for example, Material.</span></span>  
4. <span data-ttu-id="3f358-119">Klicka på **Skapa rader.**</span><span class="sxs-lookup"><span data-stu-id="3f358-119">Click **Create lines**.</span></span>
5. <span data-ttu-id="3f358-120">I fältet **Från datum** anger du ett datum.</span><span class="sxs-lookup"><span data-stu-id="3f358-120">In the **From date** field, enter a date.</span></span>  
6. <span data-ttu-id="3f358-121">I fältet **Till-datum**, anger du ett datum.</span><span class="sxs-lookup"><span data-stu-id="3f358-121">In the **To date** field, enter a date.</span></span>
7. <span data-ttu-id="3f358-122">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="3f358-122">Click **OK**.</span></span> <span data-ttu-id="3f358-123">Detta skapar rader för dimensionerna som har lagertransaktioner.</span><span class="sxs-lookup"><span data-stu-id="3f358-123">This will create lines for the dimensions that have inventory transactions.</span></span>  

## <a name="calculate-proposal"></a><span data-ttu-id="3f358-124">Beräkna förslag</span><span class="sxs-lookup"><span data-stu-id="3f358-124">Calculate proposal</span></span>
1. <span data-ttu-id="3f358-125">Klicka på **Beräkna förslag**.</span><span class="sxs-lookup"><span data-stu-id="3f358-125">Click **Calculate proposal**.</span></span>
2. <span data-ttu-id="3f358-126">Välj alternativet **Använd genomsnittlig utleverans under produktionstid**.</span><span class="sxs-lookup"><span data-stu-id="3f358-126">Select the **Use average issue during lead time** option.</span></span>
3. <span data-ttu-id="3f358-127">Ange **Multiplikationsfaktor** till 10.</span><span class="sxs-lookup"><span data-stu-id="3f358-127">Set **Multiplication factor** to '10'.</span></span> <span data-ttu-id="3f358-128">Multiplikationsfaktorn används för att justera förslaget.</span><span class="sxs-lookup"><span data-stu-id="3f358-128">The Multiply factor is used to adjust the proposal.</span></span> <span data-ttu-id="3f358-129">Eftersom demodata bara har några transaktioner, måste du ange faktorn för att få ett realistiskt förslag.</span><span class="sxs-lookup"><span data-stu-id="3f358-129">Because demo data only has a few transactions, you will need to set the factor to get a realistic proposal.</span></span>  
4. <span data-ttu-id="3f358-130">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="3f358-130">Click **OK**.</span></span> <span data-ttu-id="3f358-131">Bläddra ned för att hitta M0002 och M0003.</span><span class="sxs-lookup"><span data-stu-id="3f358-131">Scroll down to find M0002 and M0003.</span></span> <span data-ttu-id="3f358-132">Visa kolumnen **Beräknad minst kvantitet**.</span><span class="sxs-lookup"><span data-stu-id="3f358-132">View the **Calculated minimum** quantity column.</span></span>   

## <a name="update-minimum-quantity"></a><span data-ttu-id="3f358-133">Uppdatera minsta kvantitet</span><span class="sxs-lookup"><span data-stu-id="3f358-133">Update minimum quantity</span></span>
1. <span data-ttu-id="3f358-134">Ange ett nummer i fältet **Ny minsta kvantitet**.</span><span class="sxs-lookup"><span data-stu-id="3f358-134">In the **New minimum quantity** field, enter a number.</span></span> <span data-ttu-id="3f358-135">Uppdatera den Nya minsta kvantiteten till att matcha värdet i Beräknad minsta kvantitet.</span><span class="sxs-lookup"><span data-stu-id="3f358-135">Update the New minimum quantity to match the value in the Calculated minimum quantity.</span></span> <span data-ttu-id="3f358-136">Om det beräknade minimivärdet är noll, kan du ange önskat framtida värde.</span><span class="sxs-lookup"><span data-stu-id="3f358-136">If the Calculated minimum is zero,  you can enter the desired future value.</span></span> <span data-ttu-id="3f358-137">Du kan till exempel ange den beräknade minimikvantiteten i det här fältet för M0002 som har lagerställe 12.</span><span class="sxs-lookup"><span data-stu-id="3f358-137">For example, you can enter the Calculated minimum quantity in this field for M0002 that has warehouse 12.</span></span>  
2. <span data-ttu-id="3f358-138">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="3f358-138">In the list, find and select the desired record.</span></span> <span data-ttu-id="3f358-139">Du kan till exempel välja M0002 som har lagerstället 12.</span><span class="sxs-lookup"><span data-stu-id="3f358-139">For example, you can select M0002 that has warehouse 12.</span></span>  
3. <span data-ttu-id="3f358-140">Ange ett nummer i fältet **Ny minsta kvantitet**.</span><span class="sxs-lookup"><span data-stu-id="3f358-140">In the **New minimum quantity** field, enter a number.</span></span> <span data-ttu-id="3f358-141">Uppdatera den Nya minsta kvantiteten till att matcha värdet i Beräknad minsta kvantitet.</span><span class="sxs-lookup"><span data-stu-id="3f358-141">Update the New minimum quantity to match the value in the Calculated minimum quantity.</span></span> <span data-ttu-id="3f358-142">Om det beräknade minimivärdet är noll, kan du ange önskat framtida värde.</span><span class="sxs-lookup"><span data-stu-id="3f358-142">If the Calculated minimum is zero you can enter the desired future value.</span></span>  

## <a name="post-the-new-minimum-quantity-and-validate-the-result"></a><span data-ttu-id="3f358-143">Bokför den nya minsta kvantiteten och verifiera resultatet</span><span class="sxs-lookup"><span data-stu-id="3f358-143">Post the new minimum quantity and validate the result</span></span>
1. <span data-ttu-id="3f358-144">Klicka på **Bokför**.</span><span class="sxs-lookup"><span data-stu-id="3f358-144">Click **Post**.</span></span>
2. <span data-ttu-id="3f358-145">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="3f358-145">Click **OK**.</span></span>
3. <span data-ttu-id="3f358-146">Klicka för att följa länken i fältet **Artikelnummer**.</span><span class="sxs-lookup"><span data-stu-id="3f358-146">Click to follow the link in the **Item number** field.</span></span>
4. <span data-ttu-id="3f358-147">Klicka för att följa länken i fältet **Artikelnummer**.</span><span class="sxs-lookup"><span data-stu-id="3f358-147">Click to follow the link in the **Item number** field.</span></span>
5. <span data-ttu-id="3f358-148">Klicka på Plan i **åtgärdsfönstret**.</span><span class="sxs-lookup"><span data-stu-id="3f358-148">On the **Action Pane**, click Plan.</span></span>
6. <span data-ttu-id="3f358-149">Klicka på **Artikeldisponering**.</span><span class="sxs-lookup"><span data-stu-id="3f358-149">Click **Item coverage**.</span></span> <span data-ttu-id="3f358-150">Observera att den **minsta kvantiteten** har uppdaterats med den nya minsta kvantiteten från säkerhetslagerjournalen.</span><span class="sxs-lookup"><span data-stu-id="3f358-150">Notice that the **Minimum quantity** has been updated with the new minimum quantity from the safety stock journal.</span></span>  

