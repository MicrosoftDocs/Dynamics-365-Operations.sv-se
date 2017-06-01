---
title: "Övervaka prognosprecision"
description: "Denna artikel beskriver de typer av prognosprecision som Microsoft Dynamics 365 for Operations beräknar, och förklarar hur du kan visa precisionsvärdena."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 72863
ms.assetid: 810a0d63-f4c6-4167-b2b3-a178b74ead89
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 580b45263b45e6ef730b0fac32575fcdd9c358b6
ms.contentlocale: sv-se
ms.lasthandoff: 05/25/2017


---

# <a name="monitor-forecast-accuracy"></a>Övervaka prognosprecision

[!include[banner](../includes/banner.md)]


Denna artikel beskriver de typer av prognosprecision som Microsoft Dynamics 365 for Operations beräknar, och förklarar hur du kan visa precisionsvärdena.

Dynamics 365 for Operations beräknar följande typer av prognosprecision:

-   Historisk prognos exakthet, genom att jämföra den historiska prognosen att Huvudplanering använder med historisk efterfrågan. Om du vill visa värden (både i absoluta och procentuella värden) för Historisk prognos noggrannhet, klicka på **Visa noggrannheten** på **Demand forecast sidan detaljer** .
-   Den uppskattade noggrannheten hos den prognosmodell som används för att generera prediktioner. Du kan visa noggrannheten procentsats enligt **modellen detaljer – MAPE** på **Demand forecast sidan detaljer** . 

**Obs!** Om du använder Dynamics 365 for Operations efterfrågeprognos Microsoft Azure Machine Learning-tjänsten baseras beräkningen av intern modellnoggrannhet på testdata. För att ange storleken på testdatauppsättningen, ställ in parametern **TEST\_SET\_SIZE\_PERCENT** på sidan **Parametrar för efterfrågeprognosticering**. Till exempel, om du anger värdet till **20**, de sista 20 procent av historiska data används för att beräkna intern modell noggrannhet.


<a name="see-also"></a>Se även
--------

[Auktorisering av den justerade prognosen](authorize-adjusted-forecast.md)

[Ta bort avskilda från historiska transaktionsdata vid beräkning av en efterfrågeprognos](remove-historical-outliers-calculating-demand-forecast.md)




