--- 
title: Skapa en baslinjeprognos
description: "En produktionsplanerare kan skapa en baslinjeprognos, antingen genom att använda tidsserieprognosmodeller eller genom att kopiera den historiska efterfrågan."
author: YuyuScheller
manager: AnnBe
ms.date: 111/02/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: ef11f3779fc94fa95f082893f6863dde8d8c921e
ms.contentlocale: sv-se
ms.lasthandoff: 04/13/2018

---
# <a name="create-a-baseline-forecast"></a><span data-ttu-id="2ad95-103">Skapa en baslinjeprognos</span><span class="sxs-lookup"><span data-stu-id="2ad95-103">Create a baseline forecast</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="2ad95-104">En produktionsplanerare kan skapa en baslinjeprognos, antingen genom att använda tidsserieprognosmodeller eller genom att kopiera den historiska efterfrågan.</span><span class="sxs-lookup"><span data-stu-id="2ad95-104">A production planner can create a baseline forecast either by using time series forecast models or by copying the historical demand.</span></span> <span data-ttu-id="2ad95-105">Denna procedur visas hur du kopierar en historisk efterfrågan med syfte att skapa en baslinjeprognos för alla produkter med hjälp av en artikelallokeringsnyckel.</span><span class="sxs-lookup"><span data-stu-id="2ad95-105">This procedure shows how to copy the historical demand to create a baseline forecast for all products using one item allocation key.</span></span> 


## <a name="set-up-an-item-allocation-key"></a><span data-ttu-id="2ad95-106">Ställ in en nyckel för artikelallokering</span><span class="sxs-lookup"><span data-stu-id="2ad95-106">Set up an item allocation key</span></span>
1. <span data-ttu-id="2ad95-107">Gå till Huvudplanering > Inställningar > Koncerninterna planeringsgrupper.</span><span class="sxs-lookup"><span data-stu-id="2ad95-107">Go to Master planning > Setup > Intercompany planning groups.</span></span>
2. <span data-ttu-id="2ad95-108">Använd snabbfiltret för att söka efter poster.</span><span class="sxs-lookup"><span data-stu-id="2ad95-108">Use the Quick Filter to find records.</span></span> <span data-ttu-id="2ad95-109">Filtrera till exempel på värdet "10" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="2ad95-109">For example, filter on the Name field with a value of '10'.</span></span>
    * <span data-ttu-id="2ad95-110">Efterfrågeprognosticering körs över juridiska personer.</span><span class="sxs-lookup"><span data-stu-id="2ad95-110">Demand forecasting runs across legal entities.</span></span> <span data-ttu-id="2ad95-111">Det är därför du måste ställa in alla företag som du vill generera prognoser för i en koncernintern planeringsgrupp.</span><span class="sxs-lookup"><span data-stu-id="2ad95-111">That's why you need to set up all the companies for which you want to generate forecasts in one intercompany planning group.</span></span>  
3. <span data-ttu-id="2ad95-112">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="2ad95-112">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="2ad95-113">Klicka på Artikelallokeringsnycklar.</span><span class="sxs-lookup"><span data-stu-id="2ad95-113">Click Item allocation keys.</span></span>
    * <span data-ttu-id="2ad95-114">Markera alla artikelallokeringsnycklar som du vill skapa prognoser för.</span><span class="sxs-lookup"><span data-stu-id="2ad95-114">Select all the item allocation keys for which you want to create forecasts.</span></span>  
5. <span data-ttu-id="2ad95-115">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="2ad95-115">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="2ad95-116">Markera artikelallokeringsnyckeln D_Aloc.</span><span class="sxs-lookup"><span data-stu-id="2ad95-116">Select D_Aloc item allocation key.</span></span>  
6. <span data-ttu-id="2ad95-117">Klicka på >.</span><span class="sxs-lookup"><span data-stu-id="2ad95-117">Click >.</span></span>
7. <span data-ttu-id="2ad95-118">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="2ad95-118">Close the page.</span></span>
8. <span data-ttu-id="2ad95-119">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="2ad95-119">Close the page.</span></span>

## <a name="set-up-the-demand-forecasting-parameters"></a><span data-ttu-id="2ad95-120">Ställ in parametrar för efterfrågeprognosticering</span><span class="sxs-lookup"><span data-stu-id="2ad95-120">Set up the demand forecasting parameters</span></span>
1. <span data-ttu-id="2ad95-121">Gå till Huvudplanering > Inställningar > Efterfrågeprognosticering > Parametrar för efterfrågeprognosticering.</span><span class="sxs-lookup"><span data-stu-id="2ad95-121">Go to Master planning > Setup > Demand forecasting > Demand forecasting parameters.</span></span>
2. <span data-ttu-id="2ad95-122">Expandera avsnittet Forecast algorithm parameters.</span><span class="sxs-lookup"><span data-stu-id="2ad95-122">Expand the Forecast algorithm parameters section.</span></span>
3. <span data-ttu-id="2ad95-123">Välj "Kopiera över historisk efterfrågan" i fältet Strategi för prognosgenerering.</span><span class="sxs-lookup"><span data-stu-id="2ad95-123">In the Forecast generation strategy field, select 'Copy over historical demand'.</span></span>
4. <span data-ttu-id="2ad95-124">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="2ad95-124">Click Save.</span></span>

## <a name="create-a-baseline-forecast"></a><span data-ttu-id="2ad95-125">Skapa en baslinjeprognos</span><span class="sxs-lookup"><span data-stu-id="2ad95-125">Create a baseline forecast</span></span>
1. <span data-ttu-id="2ad95-126">Gå till Huvudplanering > Prognosticering > Efterfrågeprognosticering > Generera statistisk baslinjeprognos.</span><span class="sxs-lookup"><span data-stu-id="2ad95-126">Go to Master planning > Forecasting > Demand forecasting > Generate statistical baseline forecast.</span></span>
2. <span data-ttu-id="2ad95-127">Ange ett datum i fältet Från datum.</span><span class="sxs-lookup"><span data-stu-id="2ad95-127">In the From date field, enter a date.</span></span>
    * <span data-ttu-id="2ad95-128">Ange detta datum om du har försäljningsorder som startar från 1 januari 2015.</span><span class="sxs-lookup"><span data-stu-id="2ad95-128">If you have sales orders starting from January 1, 2015, enter this date.</span></span> <span data-ttu-id="2ad95-129">Om du inte har det anger du det tidigaste datumet för dina försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="2ad95-129">If you don't, enter the earliest date of your sales orders.</span></span>  
3. <span data-ttu-id="2ad95-130">Ange ett datum i fältet Till datum.</span><span class="sxs-lookup"><span data-stu-id="2ad95-130">In the To date field, enter a date.</span></span>
    * <span data-ttu-id="2ad95-131">Ange det sista datumet för dina försäljningsorder, t.ex. "2015-03-31".</span><span class="sxs-lookup"><span data-stu-id="2ad95-131">Enter the last date of your sales orders, for example '2015-03-31'.</span></span>  
4. <span data-ttu-id="2ad95-132">Ange ett datum i fältet Från datum.</span><span class="sxs-lookup"><span data-stu-id="2ad95-132">In the From date field, enter a date.</span></span>
    * <span data-ttu-id="2ad95-133">Ange "2015-04-01".</span><span class="sxs-lookup"><span data-stu-id="2ad95-133">Enter '2015-04-01'.</span></span> <span data-ttu-id="2ad95-134">Det här datumet beräknas automatiskt som startdatumet för nästa prognosgrupp.</span><span class="sxs-lookup"><span data-stu-id="2ad95-134">This date will be automatically calculated as the start date of the next forecasting bucket.</span></span>  
5. <span data-ttu-id="2ad95-135">Expandera avsnittet Poster som ska ingå.</span><span class="sxs-lookup"><span data-stu-id="2ad95-135">Expand the Records to include section.</span></span>
6. <span data-ttu-id="2ad95-136">Klicka på Filter.</span><span class="sxs-lookup"><span data-stu-id="2ad95-136">Click Filter.</span></span>
7. <span data-ttu-id="2ad95-137">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="2ad95-137">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="2ad95-138">Markera raden där Fält = Koncernintern planeringsgrupp.</span><span class="sxs-lookup"><span data-stu-id="2ad95-138">Mark the row where Field = Intercompany planning group.</span></span>  
8. <span data-ttu-id="2ad95-139">Ange ett värde i fältet Kriterier.</span><span class="sxs-lookup"><span data-stu-id="2ad95-139">In the Criteria field, type a value.</span></span>
    * <span data-ttu-id="2ad95-140">Skriv den koncerninterna planeringsgruppen, till exempel 10, som du använde i den första uppgiften.</span><span class="sxs-lookup"><span data-stu-id="2ad95-140">Type the intercompany planning group, for example, 10, that you used in the first task.</span></span>  
9. <span data-ttu-id="2ad95-141">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="2ad95-141">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="2ad95-142">Markera raden där Fält = Artikelallokeringsnyckel.</span><span class="sxs-lookup"><span data-stu-id="2ad95-142">Select the row where Field = Item allocation key.</span></span>  
10. <span data-ttu-id="2ad95-143">Ange ett värde i fältet Kriterier.</span><span class="sxs-lookup"><span data-stu-id="2ad95-143">In the Criteria field, type a value.</span></span>
11. <span data-ttu-id="2ad95-144">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="2ad95-144">Click OK.</span></span>
12. <span data-ttu-id="2ad95-145">Expandera avsnittet Avancerade parametrar.</span><span class="sxs-lookup"><span data-stu-id="2ad95-145">Expand the Advanced parameters section.</span></span>
13. <span data-ttu-id="2ad95-146">Välj "Månad" i fältet Prognosgrupp.</span><span class="sxs-lookup"><span data-stu-id="2ad95-146">In the Forecast bucket field, select 'Month'.</span></span>
14. <span data-ttu-id="2ad95-147">Ange "3" i fältet Prognoshorisont.</span><span class="sxs-lookup"><span data-stu-id="2ad95-147">In the Forecast horizon field, enter '3'.</span></span>
15. <span data-ttu-id="2ad95-148">Ange "1" i fältet Frystidsgräns.</span><span class="sxs-lookup"><span data-stu-id="2ad95-148">In the Freeze time fence field, enter '1'.</span></span>
16. <span data-ttu-id="2ad95-149">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="2ad95-149">Click OK.</span></span>

## <a name="visualize-the-demand-forecast"></a><span data-ttu-id="2ad95-150">Visualisera efterfrågeprognosen</span><span class="sxs-lookup"><span data-stu-id="2ad95-150">Visualize the demand forecast</span></span>
1. <span data-ttu-id="2ad95-151">Gå till Huvudplanering > Prognosticering > Efterfrågeprognosticering > Parametrar för efterfrågeprognosticering.</span><span class="sxs-lookup"><span data-stu-id="2ad95-151">Go to Master planning > Forecasting > Demand forecasting > Adjusted demand forecast.</span></span>
2. <span data-ttu-id="2ad95-152">Välj cellen i rad 1, kolumn 2 i tabellen AggregatedViewTable.</span><span class="sxs-lookup"><span data-stu-id="2ad95-152">In the aggregated view table, select the cell in row 1, column 2.</span></span> <span data-ttu-id="2ad95-153">Detta är den andra månaden som du har skapat prognos för.</span><span class="sxs-lookup"><span data-stu-id="2ad95-153">This is the second month for which you have created forecast.</span></span>
3. <span data-ttu-id="2ad95-154">Ange QtyCell till "400".</span><span class="sxs-lookup"><span data-stu-id="2ad95-154">Set QtyCell to '400'.</span></span>
    * <span data-ttu-id="2ad95-155">I cellen anger du ett annat nummer än det som har prognosticerats, till exempel 400.</span><span class="sxs-lookup"><span data-stu-id="2ad95-155">In the cell, enter a different number than the one that was forecasted, for example, 400.</span></span>  
4. <span data-ttu-id="2ad95-156">Du har gjort en manuell justering av prognosen.</span><span class="sxs-lookup"><span data-stu-id="2ad95-156">You have made a manual adjustment to the forecast.</span></span> <span data-ttu-id="2ad95-157">Observera den grafiska indikeringen i nästa steg.</span><span class="sxs-lookup"><span data-stu-id="2ad95-157">Notice the graphical indication in the next step.</span></span>
5. <span data-ttu-id="2ad95-158">Klicka på Raddetaljer för prognos.</span><span class="sxs-lookup"><span data-stu-id="2ad95-158">Click Forecast line details.</span></span>
    * <span data-ttu-id="2ad95-159">På den här sidan kan du se precisionsvärdena, den historiska efterfrågan och prognosen.</span><span class="sxs-lookup"><span data-stu-id="2ad95-159">On this page, you can see the accuracy values, historical demand, and forecast.</span></span> <span data-ttu-id="2ad95-160">Du kan fortfarande göra ändringar även i prognosen.</span><span class="sxs-lookup"><span data-stu-id="2ad95-160">You can make changes to the forecast as well.</span></span>  


