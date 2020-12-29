---
title: Ta bort avskilda från historiska transaktionsdata när du beräknar en efterfrågeprognos
description: Den här artikeln beskriver hur du utesluter avskilda från historiska data som används för att beräkna en efterfrågeprognos. Genom att exkludera avskilda kan du förbättra prognosexaktheten.
author: roxanadiaconu
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqDemPlanForecastParameters, ReqDemPlanOutlierQuerySetup, ReqDemPlanOutlierQueryPreview
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 72621
ms.assetid: 88a964af-14eb-4c5c-945b-388e5908362c
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9dec963ed5abd6f77e82029a3ea5ba1a69d44e36
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437539"
---
# <a name="remove-outliers-from-historical-transaction-data-when-calculating-a-demand-forecast"></a>Ta bort avskilda från historiska transaktionsdata när du beräknar en efterfrågeprognos

[!include [banner](../includes/banner.md)]

Den här artikeln beskriver hur du utesluter avskilda från historiska data som används för att beräkna en efterfrågeprognos. Genom att exkludera avskilda kan du förbättra prognosexaktheten.

Du kan exkludera avvikare för att förbättra prognosexaktheten. Den här uppgiften är valfri. Här finns en översikt av processen:

1.  Klicka på **Huvudplanering** &gt; **Inställningar** &gt; **Efterfrågeprognosticering** &gt; **Borttagning av avskild** för att öppna sidan **Borttagning av avskild** där du kan använda en fråga för att välja transaktionerna som ska undantas.
2.  Välj vilket företag som frågan gäller och ange sedan ett namn och en beskrivning. Fältet **Frågedatum** ställs automatiskt in på aktuellt datum.
3.  Markera kryssrutan **Aktiv** om du vill exkludera transaktionerna som hittas av frågan från historiska data. Den här inställningen ska börja gälla när du skapar en baslinjeprognos.
4.  På sidan **Fråga för borttagning av avskild** kan du lägga till, ta bort och välja kriterier som definierar vilka transaktioner som ska utelämnas när baslinjeprognosen beräknas. Välj till exempel en viss artikel eller ordertransaktion som du vill utesluta.
5.  Klicka på **Visa transaktioner**. Sidan **Avskilda transaktioner** visar en lista över de transaktioner som uppfyller de kriterier som definierats i frågan och som ska uteslutas ur historiska data när efterfrågeprognosen beräknas.

**Anm.:** Du kan också skapa en fråga som baseras på en befintlig fråga. Välj den frågan som du vill kopiera från och klicka sedan på **Duplicera**. Fältet **Frågedatum** identifierar versionen. Du kan använda frågan som är den är eller klicka på **Redigera fråga** om du vill ändra kriterierna. Du kan även ändra namn och beskrivning för den nya frågan.

<a name="additional-resources"></a>Ytterligare resurser
--------

[Efterfrågeprognosticering – översikt](introduction-demand-forecasting.md)

[Övervaka prognosens exakthet](monitor-forecast-accuracy.md)



