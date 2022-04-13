---
title: Övervaka prognosens exakthet
description: Detta avsnitt beskriver de typer av prognosprecision som Dynamics 365 Supply Chain Management beräknar, och förklarar hur du kan visa spridningsvärden.
author: t-benebo
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
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 14d23ae800240ebb10ae085acf3ed981a22f1574
ms.sourcegitcommit: ad1afc6893a8dc32d1363395666b0fe1d50e983a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2022
ms.locfileid: "8470301"
---
# <a name="monitor-forecast-accuracy"></a>Övervaka prognosens exakthet

[!include [banner](../includes/banner.md)]

Detta avsnitt beskriver de typer av prognosprecision som Microsoft Dynamics 365 Supply Chain Management beräknar, och förklarar hur du kan visa spridningsvärden.

Supply Chain Management beräknar följande typer av prognosprecision:

-   Historisk prognos exakthet, genom att jämföra den historiska prognosen att Huvudplanering använder med historisk efterfrågan. Om du vill visa värden (både i absoluta och procentuella värden) för Historisk prognos noggrannhet, klicka på **Visa noggrannheten** på **Demand forecast sidan detaljer** .
-   Den uppskattade noggrannheten hos den prognosmodell som används för att generera prediktioner. Du kan visa noggrannheten procentsats enligt **modellen detaljer – MAPE** på **Demand forecast sidan detaljer** . 

> [!NOTE]
> Om du använder efterfrågeprognos för Microsoft Azure Machine Learning Learning baseras beräkningen av intern modellnoggrannhet på testdata. För att ange storleken på testdatauppsättningen, ställ in parametern **TEST\_SET\_SIZE\_PERCENT** på sidan **Parametrar för efterfrågeprognosticering**. Till exempel, om du anger värdet till **20**, de sista 20 procent av historiska data används för att beräkna intern modell noggrannhet.


## <a name="additional-resources"></a>Ytterligare resurser

[Auktorisera en justerad efterfrågeprognos](authorize-adjusted-forecast.md)

[Ta bort avskilda från historiska transaktionsdata när du beräknar en efterfrågeprognos](remove-historical-outliers-calculating-demand-forecast.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]