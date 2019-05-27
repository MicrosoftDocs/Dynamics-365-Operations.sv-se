---
title: Övervaka prognosprecision
description: Denna artikel beskriver de typer av prognosprecision som Microsoft Dynamics 365 for Finance and Operations beräknar, och förklarar hur du kan visa spridningsvärden.
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqDemPlanForecastDetails
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 72863
ms.assetid: 810a0d63-f4c6-4167-b2b3-a178b74ead89
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d7070c15f9ee23cfdba871af68d1fc5954735651
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1556816"
---
# <a name="monitor-forecast-accuracy"></a><span data-ttu-id="6b5af-103">Övervaka prognosprecision</span><span class="sxs-lookup"><span data-stu-id="6b5af-103">Monitor forecast accuracy</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6b5af-104">Denna artikel beskriver de typer av prognosprecision som Microsoft Dynamics 365 for Finance and Operations beräknar, och förklarar hur du kan visa spridningsvärden.</span><span class="sxs-lookup"><span data-stu-id="6b5af-104">This article describes the types of forecast accuracy that Microsoft Dynamics 365 for Finance and Operations calculates, and explains how you can view the accuracy values.</span></span>

<span data-ttu-id="6b5af-105">Finance and Operations beräknar följande typer av prognosprecision:</span><span class="sxs-lookup"><span data-stu-id="6b5af-105">Finance and Operations calculates the following types of forecast accuracy:</span></span>

-   <span data-ttu-id="6b5af-106">Historisk prognos exakthet, genom att jämföra den historiska prognosen att Huvudplanering använder med historisk efterfrågan.</span><span class="sxs-lookup"><span data-stu-id="6b5af-106">Historical forecast accuracy, by comparing the historical forecast that Master Planning uses with the historical demand.</span></span> <span data-ttu-id="6b5af-107">Om du vill visa värden (både i absoluta och procentuella värden) för Historisk prognos noggrannhet, klicka på **Visa noggrannheten** på **Demand forecast sidan detaljer** .</span><span class="sxs-lookup"><span data-stu-id="6b5af-107">To view the values (both absolute values and percentage values) for historical forecast accuracy, click **Show accuracy** on the **Demand forecast details** page.</span></span>
-   <span data-ttu-id="6b5af-108">Den uppskattade noggrannheten hos den prognosmodell som används för att generera prediktioner.</span><span class="sxs-lookup"><span data-stu-id="6b5af-108">The estimated accuracy of the forecasting model that is used to generate the predictions.</span></span> <span data-ttu-id="6b5af-109">Du kan visa noggrannheten procentsats enligt **modellen detaljer – MAPE** på **Demand forecast sidan detaljer** .</span><span class="sxs-lookup"><span data-stu-id="6b5af-109">You can view the accuracy percentage under **Model details - MAPE** on the **Demand forecast details** page.</span></span> 

<span data-ttu-id="6b5af-110">**Obs!** Om du använder tjänsten Finance and Operations Demand-efterfrågeprognoser Microsoft Azure Machine Learning baseras beräkningen av intern modellnoggrannhet på testdata.</span><span class="sxs-lookup"><span data-stu-id="6b5af-110">**Note:** If you use the Finance and Operations Demand forecasting Microsoft Azure Machine Learning service, the calculation of internal model accuracy is based on the test data set.</span></span> <span data-ttu-id="6b5af-111">För att ange storleken på testdatauppsättningen, ställ in parametern **TEST\_SET\_SIZE\_PERCENT** på sidan **Parametrar för efterfrågeprognosticering**.</span><span class="sxs-lookup"><span data-stu-id="6b5af-111">To specify the size of the test data set, set the **TEST\_SET\_SIZE\_PERCENT** parameter on the **Demand forecasting parameters** page.</span></span> <span data-ttu-id="6b5af-112">Till exempel, om du anger värdet till **20**, de sista 20 procent av historiska data används för att beräkna intern modell noggrannhet.</span><span class="sxs-lookup"><span data-stu-id="6b5af-112">For example, if you set the value to **20**, the last 20 percent of the historical data will be used to calculate the internal model accuracy.</span></span>


<a name="additional-resources"></a><span data-ttu-id="6b5af-113">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="6b5af-113">Additional resources</span></span>
--------

[<span data-ttu-id="6b5af-114">Auktorisering av den justerade prognosen</span><span class="sxs-lookup"><span data-stu-id="6b5af-114">Authorizing the adjusted forecast</span></span>](authorize-adjusted-forecast.md)

[<span data-ttu-id="6b5af-115">Ta bort avskilda från historiska transaktionsdata när du beräknar en efterfrågeprognos</span><span class="sxs-lookup"><span data-stu-id="6b5af-115">Remove outliers from historical transaction data when calculating a demand forecast</span></span>](remove-historical-outliers-calculating-demand-forecast.md)



