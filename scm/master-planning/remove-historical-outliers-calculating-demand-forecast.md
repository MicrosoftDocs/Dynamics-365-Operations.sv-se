---
title: "Ta bort avskilda från historiska transaktionsdata när du beräknar en efterfrågeprognos"
description: "Den här artikeln beskriver hur du utesluter avskilda från historiska data som används för att beräkna en efterfrågeprognos. Genom att exkludera avskilda kan du förbättra prognosexaktheten."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ReqDemPlanForecastParameters, ReqDemPlanOutlierQuerySetup
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 72621
ms.assetid: 88a964af-14eb-4c5c-945b-388e5908362c
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 6f44e1ce566781f1586203528d55b13b28001a2c
ms.lasthandoff: 03/31/2017


---

# <a name="remove-outliers-from-historical-transaction-data-when-calculating-a-demand-forecast"></a>Ta bort avskilda från historiska transaktionsdata när du beräknar en efterfrågeprognos

Den här artikeln beskriver hur du utesluter avskilda från historiska data som används för att beräkna en efterfrågeprognos. Genom att exkludera avskilda kan du förbättra prognosexaktheten.

Du kan utesluta avvikare förbättra precisionen prognos. Den här uppgiften är valfri. Här finns en översikt av processen:

1.  Klickar du på **huvudplanering**&gt;**inställningar**&gt;**efterfrågeprognosticering**&gt;**avvikare borttagning** så att den **avvikare borttagning** sida där du kan använda en fråga för att välja vilka transaktioner som ska undantas.
2.  Välj vilket företag som frågan gäller och ange sedan ett namn och en beskrivning. Fältet **Frågedatum** ställs automatiskt in på aktuellt datum.
3.  Markera kryssrutan **Aktiv** om du vill exkludera transaktionerna som hittas av frågan från historiska data. Den här inställningen ska börja gälla när du skapar en baslinjeprognos.
4.  På sidan **Fråga för borttagning av avskild** kan du lägga till, ta bort och välja kriterier som definierar vilka transaktioner som ska utelämnas när baslinjeprognosen beräknas. Välj till exempel en viss artikel eller ordertransaktion som du vill utesluta.
5.  Klicka på **Visa transaktioner**. Sidan **Avskilda transaktioner** visar en lista över de transaktioner som uppfyller de kriterier som definierats i frågan och som ska uteslutas ur historiska data när efterfrågeprognosen beräknas.

**Anm.:** Du kan också skapa en fråga som baseras på en befintlig fråga. Välj den frågan som du vill kopiera från och klicka sedan på **Duplicera**. Fältet **Frågedatum** identifierar versionen. Du kan använda frågan som är den är eller klicka på **Redigera fråga** om du vill ändra kriterierna. Du kan även ändra namn och beskrivning för den nya frågan.

<a name="see-also"></a>Se även
--------

[Introduction to demand forecasting](introduction-demand-forecasting.md)

[Monitoring forecast accuracy](monitor-forecast-accuracy.md)


