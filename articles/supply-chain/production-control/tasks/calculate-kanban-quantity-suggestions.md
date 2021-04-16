---
title: Beräkna förslag till kanban-kvantitet
description: Den här proceduren fokuserar på att optimera kanban-storleken och kvantiteterna för en specifik kanban-regel med hjälp av kanban-kvantitetsberäkningen.
author: ChristianRytt
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 93845129e057b8729e676123967efefb6bca66f2
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5829340"
---
# <a name="calculate-kanban-quantity-suggestions"></a><span data-ttu-id="53ba0-103">Beräkna förslag till kanban-kvantitet</span><span class="sxs-lookup"><span data-stu-id="53ba0-103">Calculate kanban quantity suggestions</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="53ba0-104">Den här proceduren fokuserar på att optimera kanban-storleken och kvantiteterna för en specifik kanban-regel med hjälp av kanban-kvantitetsberäkningen.</span><span class="sxs-lookup"><span data-stu-id="53ba0-104">This procedure focuses on optimizing the kanban size and quantities for a specific kanban rule by using the kanban quantity calculation.</span></span> <span data-ttu-id="53ba0-105">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="53ba0-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="53ba0-106">Den här proceduren är avsedd för den värdeströmsansvarige.</span><span class="sxs-lookup"><span data-stu-id="53ba0-106">This procedure is intended for the value stream manager.</span></span> <span data-ttu-id="53ba0-107">Det är en förutsättning att du har slutfört proceduren Lägg till en beräkningspolicy för kanban-kvantitet till en kanban-regel.</span><span class="sxs-lookup"><span data-stu-id="53ba0-107">It is a prerequisite that you have completed the procedure Add a new kanban quantity calculation policy to a kanban rule.</span></span>


## <a name="create-a-kanban-quantity-calculation"></a><span data-ttu-id="53ba0-108">Skapa en beräkning av kanban-kvantitet</span><span class="sxs-lookup"><span data-stu-id="53ba0-108">Create a kanban quantity calculation</span></span>
1. <span data-ttu-id="53ba0-109">Gå till Produktionskontroll > Periodiska uppgifter > Kanban-kvantitetsberäkning > Beräkna kanban-kvantitet.</span><span class="sxs-lookup"><span data-stu-id="53ba0-109">Go to Production control > Periodic tasks > Kanban quantity calculation > Calculate kanban quantity.</span></span>
2. <span data-ttu-id="53ba0-110">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="53ba0-110">Click New.</span></span>
3. <span data-ttu-id="53ba0-111">Skriv "Speaker2016" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="53ba0-111">In the Name field, type 'Speaker2016'.</span></span>
4. <span data-ttu-id="53ba0-112">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="53ba0-112">In the Name field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="53ba0-113">Välj den policy som du har skapat i proceduren Lägg till en beräkningspolicy för kanban-kvantitet till en kanban-regel.</span><span class="sxs-lookup"><span data-stu-id="53ba0-113">Select the policy that you have created in the procedure Add a new kanban quantity calculation policy to a kanban rule.</span></span> <span data-ttu-id="53ba0-114">Till exempel Speaker2016.</span><span class="sxs-lookup"><span data-stu-id="53ba0-114">For example, Speaker2016.</span></span>  
5. <span data-ttu-id="53ba0-115">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="53ba0-115">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="53ba0-116">Ange datum och tid till "2012-12-17T08:00:00" i fältet Regel aktiv från och med datum.</span><span class="sxs-lookup"><span data-stu-id="53ba0-116">In the Rule active as of date field, set the date and time to '2012-12-17T08:00:00'.</span></span>
    * <span data-ttu-id="53ba0-117">Det här datumet används som bas för att bestämma vilka fasta kanban-regler som inkluderas i kanban-kvantitetsberäkningen.</span><span class="sxs-lookup"><span data-stu-id="53ba0-117">This date serves as the basis for determining which fixed kanban rules are included in the kanban quantity calculation.</span></span>  
7. <span data-ttu-id="53ba0-118">Ange datum och tid till "2012-11-17T09:00:00" i fältet Startdatum för den uppfyllda efterfrågeperioden.</span><span class="sxs-lookup"><span data-stu-id="53ba0-118">In the Fulfilled demand period start date field, set the date and time to '2012-11-17T09:00:00'.</span></span>
    * <span data-ttu-id="53ba0-119">Det datum från vilket tidigare efterfrågetransaktioner inkluderas för att beräkna kanban-kvantiteten.</span><span class="sxs-lookup"><span data-stu-id="53ba0-119">The date from when past demand transactions are included to calculate the kanban quantity.</span></span>  
8. <span data-ttu-id="53ba0-120">Ange datum och tid till "2012-12-17T07:59:59" i fältet Slutdatum för den uppfyllda efterfrågeperioden.</span><span class="sxs-lookup"><span data-stu-id="53ba0-120">In the Fulfilled demand period end date field, set the date and time to '2012-12-17T07:59:59'.</span></span>
    * <span data-ttu-id="53ba0-121">Det datum fram till vilket tidigare efterfrågetransaktioner inkluderas för att beräkna kanban-kvantiteten.</span><span class="sxs-lookup"><span data-stu-id="53ba0-121">The date until when past demand transactions are included to calculate the kanban quantity.</span></span>  
9. <span data-ttu-id="53ba0-122">Ange datum och tid till "2012-12-17T08:00:00" i fältet Startdatum för efterfrågeperioden.</span><span class="sxs-lookup"><span data-stu-id="53ba0-122">In the Demand period start date field, set the date and time to '2012-12-17T08:00:00'.</span></span>
    * <span data-ttu-id="53ba0-123">Det datum från vilket aktuella efterfrågetransaktioner inkluderas för att beräkna kanban-kvantiteten.</span><span class="sxs-lookup"><span data-stu-id="53ba0-123">The date from when current demand transactions are included to calculate the kanban quantity.</span></span>  
10. <span data-ttu-id="53ba0-124">Ange datum och tid till "2013-01-16T07:59:59" i fältet Slutdatum för efterfrågeperioden.</span><span class="sxs-lookup"><span data-stu-id="53ba0-124">In the Demand period end date field, set the date and time to '2013-01-16T07:59:59'.</span></span>
    * <span data-ttu-id="53ba0-125">Det datum fram till vilket aktuella efterfrågetransaktioner inkluderas för att beräkna kanban-kvantiteten.</span><span class="sxs-lookup"><span data-stu-id="53ba0-125">The date until when current demand transactions are included to calculate the kanban quantity.</span></span>  

## <a name="generate-kanban-quantity-proposal"></a><span data-ttu-id="53ba0-126">Generera förslag på kanban-kvantitet</span><span class="sxs-lookup"><span data-stu-id="53ba0-126">Generate kanban quantity proposal</span></span>
1. <span data-ttu-id="53ba0-127">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="53ba0-127">Click Save.</span></span>
2. <span data-ttu-id="53ba0-128">Klicka på Generera.</span><span class="sxs-lookup"><span data-stu-id="53ba0-128">Click Generate.</span></span>
    * <span data-ttu-id="53ba0-129">Då skapas en förslagsrad för kanban-kvantitet för kanban-regeln 000020.</span><span class="sxs-lookup"><span data-stu-id="53ba0-129">This generates a kanban quantity proposal line for the kanban rule 000020.</span></span>  

## <a name="run-kanban-quantity-calculation"></a><span data-ttu-id="53ba0-130">Kör beräkning av kanban-kvantitet</span><span class="sxs-lookup"><span data-stu-id="53ba0-130">Run kanban quantity calculation</span></span>
1. <span data-ttu-id="53ba0-131">Klicka på Beräkna.</span><span class="sxs-lookup"><span data-stu-id="53ba0-131">Click Calculate.</span></span>
    * <span data-ttu-id="53ba0-132">Då beräknas kanban-kvantitetsförslaget.</span><span class="sxs-lookup"><span data-stu-id="53ba0-132">This calculates the kanban quantity proposal.</span></span>  
2. <span data-ttu-id="53ba0-133">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="53ba0-133">Click OK.</span></span>
3. <span data-ttu-id="53ba0-134">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="53ba0-134">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="53ba0-135">Observera att den föreslagna kanban-kvantiteten är 2.</span><span class="sxs-lookup"><span data-stu-id="53ba0-135">Notice the suggested kanban quantity is 2.</span></span>  

## <a name="change-product-quantity-and-calculate-again"></a><span data-ttu-id="53ba0-136">Ändra produktkvantiteten och beräkna igen</span><span class="sxs-lookup"><span data-stu-id="53ba0-136">Change product quantity and calculate again</span></span>
1. <span data-ttu-id="53ba0-137">Ange produktkvantiteten till "5".</span><span class="sxs-lookup"><span data-stu-id="53ba0-137">Set Product quantity to '5'.</span></span>
2. <span data-ttu-id="53ba0-138">Klicka på Beräkna.</span><span class="sxs-lookup"><span data-stu-id="53ba0-138">Click Calculate.</span></span>
3. <span data-ttu-id="53ba0-139">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="53ba0-139">Click OK.</span></span>
    * <span data-ttu-id="53ba0-140">Observera att med en kanban-kvantitet på 5 så ändras förslaget till en kanban-kvantitet på 4.</span><span class="sxs-lookup"><span data-stu-id="53ba0-140">Notice that with a kanban quantity of 5, the suggestion is changed to a kanban quantity of 4.</span></span>  
    * <span data-ttu-id="53ba0-141">Detta orsakas av att med en lägre produktkvantitet så behöver vi fler kanbans för att uppfylla efterfrågan.</span><span class="sxs-lookup"><span data-stu-id="53ba0-141">This is caused by the fact that with a lower product quantity, we need more kanbans to fulfill the demand.</span></span>  

## <a name="update-kanban-rule"></a><span data-ttu-id="53ba0-142">Uppdatera kanban-regel</span><span class="sxs-lookup"><span data-stu-id="53ba0-142">Update kanban rule</span></span>
1. <span data-ttu-id="53ba0-143">Ange datum och tid i fältet Giltighetsdatum för regel.</span><span class="sxs-lookup"><span data-stu-id="53ba0-143">In the Rule effective date field, enter a date and time.</span></span>
    * <span data-ttu-id="53ba0-144">Ange ”Regel aktiv från och med datum" till ett datum i framtiden.</span><span class="sxs-lookup"><span data-stu-id="53ba0-144">Set the 'Rule active as of date' to a date in the future.</span></span> <span data-ttu-id="53ba0-145">Till exempel i dag + ett år.</span><span class="sxs-lookup"><span data-stu-id="53ba0-145">For example, today + one year.</span></span>  
2. <span data-ttu-id="53ba0-146">Klicka på Uppdatera.</span><span class="sxs-lookup"><span data-stu-id="53ba0-146">Click Update.</span></span>
3. <span data-ttu-id="53ba0-147">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="53ba0-147">Click OK.</span></span>
4. <span data-ttu-id="53ba0-148">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="53ba0-148">Close the page.</span></span>

## <a name="validate-change-on-kanban-rule"></a><span data-ttu-id="53ba0-149">Validera ändringar i kanban-regel</span><span class="sxs-lookup"><span data-stu-id="53ba0-149">Validate change on kanban rule</span></span>
1. <span data-ttu-id="53ba0-150">Gå till Produktinformationshantering > Lean manufacturing > Kanban-regler.</span><span class="sxs-lookup"><span data-stu-id="53ba0-150">Go to Product information management > Lean manufacturing > Kanban rules.</span></span>
2. <span data-ttu-id="53ba0-151">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="53ba0-151">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="53ba0-152">Välj den kanban-regel som har skapats i den föregående underuppgiften.</span><span class="sxs-lookup"><span data-stu-id="53ba0-152">Select the kanban rule that was created in the previous sub-task.</span></span> <span data-ttu-id="53ba0-153">Detta ska vara den första kanban-regeln i listan sorterad efter nummer.</span><span class="sxs-lookup"><span data-stu-id="53ba0-153">This should be the first kanban rule in the list sorted by number.</span></span>  
3. <span data-ttu-id="53ba0-154">Växla expanderingen av avsnittet Detaljer.</span><span class="sxs-lookup"><span data-stu-id="53ba0-154">Toggle the expansion of the Details section.</span></span>
    * <span data-ttu-id="53ba0-155">Observera giltighetsdatumet, vilket innebär att regeln inte har aktiverats förrän detta datum.</span><span class="sxs-lookup"><span data-stu-id="53ba0-155">Notice the effective date, which means that this rule is not activated until this date.</span></span>  
4. <span data-ttu-id="53ba0-156">Växla expanderingen av avsnittet Kvantiteter.</span><span class="sxs-lookup"><span data-stu-id="53ba0-156">Toggle the expansion of the Quantities section.</span></span>
    * <span data-ttu-id="53ba0-157">Observera att detta är den standardkvantitet som du angett på kanban-kvantitetsberäkningen.</span><span class="sxs-lookup"><span data-stu-id="53ba0-157">Notice this is the default quantity that you entered on the kanban quantity calculation.</span></span>  
    * <span data-ttu-id="53ba0-158">Observera att detta är den fasta kanban-kvantiteten på 4 från den kanban-kvantitetsberäkningen.</span><span class="sxs-lookup"><span data-stu-id="53ba0-158">Notice this is the fixed kanban quantity of 4 from the kanban quantity calculation.</span></span>  
5. <span data-ttu-id="53ba0-159">Klicka på fliken ListPanel.</span><span class="sxs-lookup"><span data-stu-id="53ba0-159">Click the ListPanel tab.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]