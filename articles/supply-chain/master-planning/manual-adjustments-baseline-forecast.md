---
title: Gör manuella justeringar på baslinjeprognosen
description: Detta ämne beskriver hur du kan göra manuella justeringar till en baslinje prognos och visa information om prognosen.
author: roxanadiaconu
manager: AnnBe
ms.date: 11/02/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqDemPlanForecastViewer
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 72704
ms.assetid: e7c5d44e-07bc-40b1-a4b3-8ba46483ef9e
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: df9692dc168e9efb653b20c677cd6e3bb0bd8756
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/30/2019
ms.locfileid: "2250724"
---
# <a name="make-manual-adjustments-to-the-baseline-forecast"></a><span data-ttu-id="4db55-103">Gör manuella justeringar på baslinjeprognosen</span><span class="sxs-lookup"><span data-stu-id="4db55-103">Make manual adjustments to the baseline forecast</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4db55-104">Detta ämne beskriver hur du kan göra manuella justeringar till en baslinje prognos och visa information om prognosen.</span><span class="sxs-lookup"><span data-stu-id="4db55-104">This topic explains how you can make manual adjustments to a baseline forecast and view details of the forecast.</span></span> 

<span data-ttu-id="4db55-105">Innan du gör manuella justeringar, det är viktigt att du förstår några begrepp på olika sidor.</span><span class="sxs-lookup"><span data-stu-id="4db55-105">Before you make manual adjustments, it's important that you understand a few concepts on various pages.</span></span>

## <a name="grid-on-the-adjusted-demand-forecast-page"></a><span data-ttu-id="4db55-106">Raster på det justerade behovet prognos sida</span><span class="sxs-lookup"><span data-stu-id="4db55-106">Grid on the Adjusted demand forecast page</span></span>
<span data-ttu-id="4db55-107">Det **justerade behovet prognos** sidan innehåller ett rutnät som har följande struktur:</span><span class="sxs-lookup"><span data-stu-id="4db55-107">The **Adjusted demand forecast** page includes a grid that has the following structure:</span></span>

-   <span data-ttu-id="4db55-108">Den första kolumnen visar element, fördelningsnycklar, företag och så vidare, att prognosen har genererats för.</span><span class="sxs-lookup"><span data-stu-id="4db55-108">The first column shows the items, item allocation keys, companies, and so on, that the forecast has been generated for.</span></span> <span data-ttu-id="4db55-109">Undertiteln på sidan ger en beskrivning av den aktuella prognosen mått som visas i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="4db55-109">The subtitle of the page provides a description of the current forecast dimensions that are shown in the grid.</span></span> <span data-ttu-id="4db55-110">Om undertexten på sidan exempelvis är **Företag / Plats / Allokeringsnyckel för artikel** och en av radrubrikerna i rutnätet är **USMF / 1 / D\_Alloc**, visar den raden prognosen för företaget USMF, plats 1 , samt artikelallokeringsnyckeln **D\_Alloc**.</span><span class="sxs-lookup"><span data-stu-id="4db55-110">For example, if the subtitle of the page is **Company / Site / Item allocation key**, and one of the row headers in the grid is **USMF / 1 / D\_Alloc**, that row shows the forecast for the USMF company, site 1, and the **D\_Alloc** item allocation key.</span></span>
-   <span data-ttu-id="4db55-111">Följande kolumnerna representerar prognos hinkar att prognosen har genererats för.</span><span class="sxs-lookup"><span data-stu-id="4db55-111">Subsequent columns represent the forecast buckets that the forecast has been generated for.</span></span> <span data-ttu-id="4db55-112">Varje kolumnrubrik är den första dagen av den prognostiserade kostnadsslag som visas.</span><span class="sxs-lookup"><span data-stu-id="4db55-112">Each column header is the first date of the forecast bucket that the column shows.</span></span>
-   <span data-ttu-id="4db55-113">Värdena i cellerna utgör prognosen för ett objekt, objekt fördelningsnyckel, och så vidare, för att särskilda prognostiserade hink.</span><span class="sxs-lookup"><span data-stu-id="4db55-113">The values in the cells represent the forecast for one item, item allocation key, and so on, for that specific forecast bucket.</span></span>

## <a name="forecast-aggregation-and-de-aggregation"></a><span data-ttu-id="4db55-114">Prognossummeringen och aggregering</span><span class="sxs-lookup"><span data-stu-id="4db55-114">Forecast aggregation and de-aggregation</span></span>
<span data-ttu-id="4db55-115">Undertiteln på sidan visar prognossummeringen.</span><span class="sxs-lookup"><span data-stu-id="4db55-115">The subtitle of the page shows the level of forecast aggregation.</span></span> 

<span data-ttu-id="4db55-116">Till exempel, om undertexten på sidan **Företag / Ort / fördelningsnyckel / artikelnummer / Färg / Storlek / Konfiguration / Stil**, det finns ingen prognos aggregering och prognosen visas på objektet och dess dimensioner.</span><span class="sxs-lookup"><span data-stu-id="4db55-116">For example, if the subtitle of the page is **Company / Site / Allocation key / Item number / Color / Size / Configuration / Style**, there is no forecast aggregation, and the forecast is shown at the level of the item and its dimensions.</span></span> <span data-ttu-id="4db55-117">För att ändra aggregering, använd **ändra prognosen mått** sida som du kan öppna från programmenyn.</span><span class="sxs-lookup"><span data-stu-id="4db55-117">To change the aggregation, use the **Change forecast dimensions** page, which you can open from the application menu.</span></span> 

<span data-ttu-id="4db55-118">För att ändra prognosen, klicka på någon av de celler som är tillgängliga, och den justerade prognosen.</span><span class="sxs-lookup"><span data-stu-id="4db55-118">To modify the forecast, click in any of the cells that are available, and type the adjusted forecast value.</span></span> <span data-ttu-id="4db55-119">Den redigerade cell omedelbart blir fet för att indikera att prognosen att det visar inte prognosen att behovsprognoser service skapats, men har justerats manuellt.</span><span class="sxs-lookup"><span data-stu-id="4db55-119">The edited cell immediately becomes bold to indicate that the forecast that it shows isn't the forecast that the demand forecasting service created, but has been manually adjusted.</span></span> 

<span data-ttu-id="4db55-120">Om du ändrar aggregering för att göra sidan mer aggregerade data, kan du använda **efterfrågan prognosrader** sidan för att se de enskilda prognosrader som sminkar den aggregerade prognosen.</span><span class="sxs-lookup"><span data-stu-id="4db55-120">If you change the aggregation to make the page show more aggregated data, you can use the **Demand forecast lines** page to see the individual forecast lines that make up the aggregated forecast.</span></span> 

<span data-ttu-id="4db55-121">Exempelvis du har genererat den prognos på artikelnivå, men du vet att efterfrågan på denna punkt kommer att öka mellan alla platser på grund av en kampanj eller annan liknande händelse.</span><span class="sxs-lookup"><span data-stu-id="4db55-121">For example, you've generated the forecast at the item level, but you know that the demand for this item will increase across all sites because of a promotion or another similar event.</span></span> <span data-ttu-id="4db55-122">I detta fall kan du ange den aggregering till **företag / Post fördelningsnyckel / Objekt** på **ändra prognosen mått** sida.</span><span class="sxs-lookup"><span data-stu-id="4db55-122">In this case, you can set the aggregation to **Company / Item allocation key / Item** on the **Change forecast dimensions** page.</span></span> <span data-ttu-id="4db55-123">Du kan justera den globala prognos för posten över alla orter i **Justerat behov prognos** raster.</span><span class="sxs-lookup"><span data-stu-id="4db55-123">You can adjust the global forecast for the item across all sites in the **Adjusted demand forecast** grid.</span></span> <span data-ttu-id="4db55-124">För att se effekten av din förändring på alla orter, öppna **efterfrågan prognosrader** sida.</span><span class="sxs-lookup"><span data-stu-id="4db55-124">To see the effect of your change across all sites, open the **Demand forecast lines** page.</span></span> <span data-ttu-id="4db55-125">På den här sidan kommer du att se en rad för posten för varje ort, den justerade prognosen och den ursprungliga prognosen.</span><span class="sxs-lookup"><span data-stu-id="4db55-125">On this page, you will see one line for the item for each site, the adjusted forecast quantity, and the original forecast quantity.</span></span> 

<span data-ttu-id="4db55-126">När justeringen av den prognosticerade kvantiteten görs på aggregerad nivå, använder systemet viktad tilldelning för att distribuera förändringen bland de rader som skapar sammansättningen.</span><span class="sxs-lookup"><span data-stu-id="4db55-126">When the adjustment of the forecasted quantity is made at an aggregated level, the system uses weighted allocation to distribute the change among the lines that create the aggregation.</span></span> 

<span data-ttu-id="4db55-127">Du kan också göra manuella justeringar på **efterfrågan prognosrader** sida, genom att modifiera antingen den **totala kvantitet** värde eller **kvantitet** celler i de-aggregering raster.</span><span class="sxs-lookup"><span data-stu-id="4db55-127">You can also make manual adjustments on the **Demand forecast lines** page, by modifying either the **Total quantity** value or the **Quantity** cells in the de-aggregation grid.</span></span>

## <a name="viewing-details-of-the-forecast"></a><span data-ttu-id="4db55-128">Visa detaljer för prognos</span><span class="sxs-lookup"><span data-stu-id="4db55-128">Viewing details of the forecast</span></span>
<span data-ttu-id="4db55-129">Du kan öppna **Demand forecast sidan detaljer för** att se mer information om prognosen.</span><span class="sxs-lookup"><span data-stu-id="4db55-129">You can open the **Demand forecast details** page to view more information about the forecast.</span></span> 

<span data-ttu-id="4db55-130">**Efterfrågan sidan Detaljer** visar följande information i grafisk och i tabellform format:</span><span class="sxs-lookup"><span data-stu-id="4db55-130">The **Demand forecast details** page shows the following information in graphical and tabular formats:</span></span>

-   <span data-ttu-id="4db55-131">Det historiska behovet att prognosen prognosen är baserad på.</span><span class="sxs-lookup"><span data-stu-id="4db55-131">The historical demand that the forecast predictions are based on.</span></span>
-   <span data-ttu-id="4db55-132">Den aktuella prognosen som används av huvudplanering.</span><span class="sxs-lookup"><span data-stu-id="4db55-132">The current forecast that is used by Master planning.</span></span>
-   <span data-ttu-id="4db55-133">Den nya efterfrågan prognostiserade värden och de belopp de har justerats manuellt.</span><span class="sxs-lookup"><span data-stu-id="4db55-133">The new demand forecast values and the amounts they have been manually adjusted by.</span></span>
-   <span data-ttu-id="4db55-134">Konfidensintervallet för prognostiserade värden.</span><span class="sxs-lookup"><span data-stu-id="4db55-134">The confidence interval for the forecasted values.</span></span>
-   <span data-ttu-id="4db55-135">Den prognosmodell som använts för att generera prognos.</span><span class="sxs-lookup"><span data-stu-id="4db55-135">The forecast model that was used to generate the forecast.</span></span> <span data-ttu-id="4db55-136">Om du tittar på aggregerade data, du skar ser en förteckning av alla de metoder som användes för samtliga aggregerade tidsserier.</span><span class="sxs-lookup"><span data-stu-id="4db55-136">If you're viewing aggregated data, you will see the list of all the methods that were used for all the aggregated time series.</span></span>
-   <span data-ttu-id="4db55-137">Den inre modellen noggrannhet (MAPE).</span><span class="sxs-lookup"><span data-stu-id="4db55-137">The internal model accuracy (MAPE).</span></span> <span data-ttu-id="4db55-138">För mer information om prognosprecision, se [övervakning prognosprecision](monitor-forecast-accuracy.md).</span><span class="sxs-lookup"><span data-stu-id="4db55-138">For more information about forecast accuracy, see [Monitoring forecast accuracy](monitor-forecast-accuracy.md).</span></span>

<span data-ttu-id="4db55-139">**Anteckningar:**</span><span class="sxs-lookup"><span data-stu-id="4db55-139">**Notes:**</span></span>

-   <span data-ttu-id="4db55-140">De konfidensintervall som visas i **Prognosdelen** av sidan representerar skillnaden mellan konfidensintervall övre gräns och konfidensintervallet undre gräns.</span><span class="sxs-lookup"><span data-stu-id="4db55-140">The confidence interval that appears in the **Forecast** section of the page represents the difference between the confidence interval upper limit and the confidence interval lower limit.</span></span> <span data-ttu-id="4db55-141">För att se värdena för de övre och nedre gränserna, hovra över diagrammet i den **historiska efterfrågan och prognos grafiskt** .</span><span class="sxs-lookup"><span data-stu-id="4db55-141">To see the values for the upper and lower limits, hover over the chart in the **Historical demand and forecast graphically** section.</span></span>
-   <span data-ttu-id="4db55-142">Om du använder tjänsten Microsoft Azure Machine Learning-efterfrågeprognoser, kan du ange vilken förtroendenivå som den genererade prognosen ska ha.</span><span class="sxs-lookup"><span data-stu-id="4db55-142">If you use the Demand forecasting Microsoft Azure Machine Learning service, you can specify the confidence level percentage that the forecast that is generated should have.</span></span> <span data-ttu-id="4db55-143">Ett konfidensintervall består av ett antal värden som fungerar som goda prognoser för efterfrågan.</span><span class="sxs-lookup"><span data-stu-id="4db55-143">A confidence interval consists of a range of values that act as good estimates for the demand forecast.</span></span> <span data-ttu-id="4db55-144">En 95-procentig konfidensnivå procenttal indikerar att det finns en 5-procentig risk att efterfrågan faller utanför konfidensintervallet.</span><span class="sxs-lookup"><span data-stu-id="4db55-144">A 95-percent confidence level percentage indicates that there is a 5-percent risk that the demand forecast falls outside the confidence interval range.</span></span>

<span data-ttu-id="4db55-145">Du kan också göra manuella justeringar av prognosen på **efterfrågan sidan detaljer** genom att ändra värdena i **prognosen** raden i **prognos** .</span><span class="sxs-lookup"><span data-stu-id="4db55-145">You can also make manual adjustments to the forecast on the **Demand forecast details** page, by modifying the values in the **Forecast** row in the **Forecast** section.</span></span>

<a name="additional-resources"></a><span data-ttu-id="4db55-146">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="4db55-146">Additional resources</span></span>
--------

[<span data-ttu-id="4db55-147">Övervaka prognosprecision</span><span class="sxs-lookup"><span data-stu-id="4db55-147">Monitoring forecast accuracy</span></span>](monitor-forecast-accuracy.md)

[<span data-ttu-id="4db55-148">Generera en statistisk baslinjeprognos</span><span class="sxs-lookup"><span data-stu-id="4db55-148">Generating a statistical baseline forecast</span></span>](generate-statistical-baseline-forecast.md)



