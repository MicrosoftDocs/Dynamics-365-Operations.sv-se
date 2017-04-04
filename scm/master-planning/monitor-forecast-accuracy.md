---
title: "Övervaka prognos noggrannhet"
description: "Den här artikeln beskrivs typer av prognostiserad noggrannhet som Microsoft Dynamics 365 för operationer beräknas och förklarar hur du kan visa korrekta värden."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
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
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: d3f88a4fa54217cea909c54955de05e2175db0cd
ms.lasthandoff: 03/29/2017


---

# <a name="monitor-forecast-accuracy"></a>Övervaka prognos noggrannhet

Den här artikeln beskrivs typer av prognostiserad noggrannhet som Microsoft Dynamics 365 för operationer beräknas och förklarar hur du kan visa korrekta värden.

Dynamics 365 för operationer beräknar följande typer av prognos är korrekt:

-   Historisk prognos exakthet, genom att jämföra den historiska prognosen att Huvudplanering använder med historisk efterfrågan. Om du vill visa värden (både i absoluta och procentuella värden) för Historisk prognos noggrannhet, klicka på **Visa noggrannheten** på **Demand forecast sidan detaljer** .
-   Den uppskattade noggrannheten hos den prognosmodell som används för att generera prediktioner. Du kan visa noggrannheten procentsats enligt **modellen detaljer – MAPE** på **Demand forecast sidan detaljer** . 

**Anmärkning:** om du använder Dynamics 365 för operationer på Microsoft Learning om datorn Azure service prognoser beräkningen av intern modell är korrekt utifrån test för datauppsättningen. För att ange storleken på datauppsättningen test i **testa\_ange\_storlek\_PROCENT** parameter på den **efterfrågan prognoser parametrar** sida. Till exempel, om du anger värdet till **20**, de sista 20 procent av historiska data används för att beräkna intern modell noggrannhet.


<a name="see-also"></a>Se även
--------

[Authorizing the adjusted forecast](authorize-adjusted-forecast.md)

[Remove outliers from historical transaction data when calculating a demand forecast](remove-historical-outliers-calculating-demand-forecast.md)


