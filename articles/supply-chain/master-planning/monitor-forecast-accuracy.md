---
title: Övervaka prognosens exakthet
description: Detta avsnitt beskriver de typer av prognosprecision som Dynamics 365 Supply Chain Management beräknar, och förklarar hur du kan visa spridningsvärden.
author: roxanadiaconu
ms.date: 01/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqDemPlanForecastDetails
audience: Application User
ms.reviewer: kamaybac
ms.custom: 72863
ms.assetid: 810a0d63-f4c6-4167-b2b3-a178b74ead89
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6ad41e002f6246311c3755df5baf4a010f9204ee
ms.sourcegitcommit: ff09736563d3cd2bc74c7664edd1767b218401cb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "6188920"
---
# <a name="monitor-forecast-accuracy"></a><span data-ttu-id="fcf50-103">Övervaka prognosens exakthet</span><span class="sxs-lookup"><span data-stu-id="fcf50-103">Monitor forecast accuracy</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fcf50-104">Detta avsnitt beskriver de typer av prognosprecision som Microsoft Dynamics 365 Supply Chain Management beräknar, och förklarar hur du kan visa spridningsvärden.</span><span class="sxs-lookup"><span data-stu-id="fcf50-104">This topic describes the types of forecast accuracy that Microsoft Dynamics 365 Supply Chain Management calculates, and explains how you can view the accuracy values.</span></span>

<span data-ttu-id="fcf50-105">Supply Chain Management beräknar följande typer av prognosprecision:</span><span class="sxs-lookup"><span data-stu-id="fcf50-105">Supply Chain Management calculates the following types of forecast accuracy:</span></span>

-   <span data-ttu-id="fcf50-106">Historisk prognos exakthet, genom att jämföra den historiska prognosen att Huvudplanering använder med historisk efterfrågan.</span><span class="sxs-lookup"><span data-stu-id="fcf50-106">Historical forecast accuracy, by comparing the historical forecast that Master Planning uses with the historical demand.</span></span> <span data-ttu-id="fcf50-107">Om du vill visa värden (både i absoluta och procentuella värden) för Historisk prognos noggrannhet, klicka på **Visa noggrannheten** på **Demand forecast sidan detaljer** .</span><span class="sxs-lookup"><span data-stu-id="fcf50-107">To view the values (both absolute values and percentage values) for historical forecast accuracy, click **Show accuracy** on the **Demand forecast details** page.</span></span>
-   <span data-ttu-id="fcf50-108">Den uppskattade noggrannheten hos den prognosmodell som används för att generera prediktioner.</span><span class="sxs-lookup"><span data-stu-id="fcf50-108">The estimated accuracy of the forecasting model that is used to generate the predictions.</span></span> <span data-ttu-id="fcf50-109">Du kan visa noggrannheten procentsats enligt **modellen detaljer – MAPE** på **Demand forecast sidan detaljer** .</span><span class="sxs-lookup"><span data-stu-id="fcf50-109">You can view the accuracy percentage under **Model details - MAPE** on the **Demand forecast details** page.</span></span> 

> [!NOTE]
> <span data-ttu-id="fcf50-110">Om du använder efterfrågeprognos för Microsoft Azure Machine Learning Learning baseras beräkningen av intern modellnoggrannhet på testdata.</span><span class="sxs-lookup"><span data-stu-id="fcf50-110">If you use the Demand forecasting Microsoft Azure Machine Learning, the calculation of internal model accuracy is based on the test data set.</span></span> <span data-ttu-id="fcf50-111">För att ange storleken på testdatauppsättningen, ställ in parametern **TEST\_SET\_SIZE\_PERCENT** på sidan **Parametrar för efterfrågeprognosticering**.</span><span class="sxs-lookup"><span data-stu-id="fcf50-111">To specify the size of the test data set, set the **TEST\_SET\_SIZE\_PERCENT** parameter on the **Demand forecasting parameters** page.</span></span> <span data-ttu-id="fcf50-112">Till exempel, om du anger värdet till **20**, de sista 20 procent av historiska data används för att beräkna intern modell noggrannhet.</span><span class="sxs-lookup"><span data-stu-id="fcf50-112">For example, if you set the value to **20**, the last 20 percent of the historical data will be used to calculate the internal model accuracy.</span></span>


## <a name="additional-resources"></a><span data-ttu-id="fcf50-113">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="fcf50-113">Additional resources</span></span>

[<span data-ttu-id="fcf50-114">Auktorisera en justerad efterfrågeprognos</span><span class="sxs-lookup"><span data-stu-id="fcf50-114">Authorize an adjusted forecast</span></span>](authorize-adjusted-forecast.md)

[<span data-ttu-id="fcf50-115">Ta bort avskilda från historiska transaktionsdata när du beräknar en efterfrågeprognos</span><span class="sxs-lookup"><span data-stu-id="fcf50-115">Remove outliers from historical transaction data when calculating a demand forecast</span></span>](remove-historical-outliers-calculating-demand-forecast.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]