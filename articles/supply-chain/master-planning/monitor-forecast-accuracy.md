---
title: "Övervaka prognosprecision"
description: "Denna artikel beskriver de typer av prognosprecision som Microsoft Dynamics 365 for Finance and Operations beräknar, och förklarar hur du kan visa precisionsvärdena."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 72863
ms.assetid: 810a0d63-f4c6-4167-b2b3-a178b74ead89
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: bd84dde353972d2d259706dd9f8f3621cef04472
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="monitor-forecast-accuracy"></a><span data-ttu-id="40244-103">Övervaka prognosprecision</span><span class="sxs-lookup"><span data-stu-id="40244-103">Monitor forecast accuracy</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="40244-104">Denna artikel beskriver de typer av prognosprecision som Microsoft Dynamics 365 for Finance and Operations beräknar, och förklarar hur du kan visa precisionsvärdena.</span><span class="sxs-lookup"><span data-stu-id="40244-104">This article describes the types of forecast accuracy that Microsoft Dynamics 365 for Finance and Operations calculates, and explains how you can view the accuracy values.</span></span>

<span data-ttu-id="40244-105">Finance and Operations beräknar följande typer av prognosprecision:</span><span class="sxs-lookup"><span data-stu-id="40244-105">Finance and Operations calculates the following types of forecast accuracy:</span></span>

-   <span data-ttu-id="40244-106">Historisk prognos exakthet, genom att jämföra den historiska prognosen att Huvudplanering använder med historisk efterfrågan.</span><span class="sxs-lookup"><span data-stu-id="40244-106">Historical forecast accuracy, by comparing the historical forecast that Master Planning uses with the historical demand.</span></span> <span data-ttu-id="40244-107">Om du vill visa värden (både i absoluta och procentuella värden) för Historisk prognos noggrannhet, klicka på **Visa noggrannheten** på **Demand forecast sidan detaljer** .</span><span class="sxs-lookup"><span data-stu-id="40244-107">To view the values (both absolute values and percentage values) for historical forecast accuracy, click **Show accuracy** on the **Demand forecast details** page.</span></span>
-   <span data-ttu-id="40244-108">Den uppskattade noggrannheten hos den prognosmodell som används för att generera prediktioner.</span><span class="sxs-lookup"><span data-stu-id="40244-108">The estimated accuracy of the forecasting model that is used to generate the predictions.</span></span> <span data-ttu-id="40244-109">Du kan visa noggrannheten procentsats enligt **modellen detaljer – MAPE** på **Demand forecast sidan detaljer** .</span><span class="sxs-lookup"><span data-stu-id="40244-109">You can view the accuracy percentage under **Model details - MAPE** on the **Demand forecast details** page.</span></span> 

<span data-ttu-id="40244-110">**Obs!** Om du använder tjänsten Microsoft Azure Machine Learning för Finance and Operations-efterfrågeprognoser, baseras beräkningen av intern modellnoggrannhet på testdata.</span><span class="sxs-lookup"><span data-stu-id="40244-110">**Note:** If you use the Finance and Operations Demand forecasting Microsoft Azure Machine Learning service, the calculation of internal model accuracy is based on the test data set.</span></span> <span data-ttu-id="40244-111">För att ange storleken på testdatauppsättningen, ställ in parametern **TEST\_SET\_SIZE\_PERCENT** på sidan **Parametrar för efterfrågeprognosticering**.</span><span class="sxs-lookup"><span data-stu-id="40244-111">To specify the size of the test data set, set the **TEST\_SET\_SIZE\_PERCENT** parameter on the **Demand forecasting parameters** page.</span></span> <span data-ttu-id="40244-112">Till exempel, om du anger värdet till **20**, de sista 20 procent av historiska data används för att beräkna intern modell noggrannhet.</span><span class="sxs-lookup"><span data-stu-id="40244-112">For example, if you set the value to **20**, the last 20 percent of the historical data will be used to calculate the internal model accuracy.</span></span>


<a name="see-also"></a><span data-ttu-id="40244-113">Se även</span><span class="sxs-lookup"><span data-stu-id="40244-113">See also</span></span>
--------

[<span data-ttu-id="40244-114">Auktorisering av den justerade prognosen</span><span class="sxs-lookup"><span data-stu-id="40244-114">Authorizing the adjusted forecast</span></span>](authorize-adjusted-forecast.md)

[<span data-ttu-id="40244-115">Ta bort avskilda från historiska transaktionsdata vid beräkning av en efterfrågeprognos</span><span class="sxs-lookup"><span data-stu-id="40244-115">Remove outliers from historical transaction data when calculating a demand forecast</span></span>](remove-historical-outliers-calculating-demand-forecast.md)




