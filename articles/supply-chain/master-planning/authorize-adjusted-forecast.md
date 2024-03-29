---
title: Auktorisera en justerad prognos
description: Inte alla prognosdata måste godkännas omedelbart. Denna artikel beskriver hur du kan ange den period som en prognos är godkända för. Det förklarar också hur du kan attestera prognos för specifika företag och prognosmodeller.
author: t-benebo
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqDemPlanImportForecastDialog
audience: Application User
ms.reviewer: kamaybac
ms.custom: 72734
ms.assetid: cb8fd809-605a-4a8b-a390-636edfec21f9
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4954b70e56482e419d81485b544cb5d0b4e4a3ce
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2022
ms.locfileid: "9740722"
---
# <a name="authorize-an-adjusted-forecast"></a>Auktorisera en justerad prognos

[!include [banner](../includes/banner.md)]

Inte alla prognosdata måste godkännas omedelbart. Denna artikel beskriver hur du kan ange den period som en prognos är godkända för. Det förklarar också hur du kan attestera prognos för specifika företag och prognosmodeller.

Inte alla prognosdata måste godkännas omedelbart. Du kan ange start- och slutdatum för den period som prognosen är godkända för. Med denna funktion kan du frysa specifikt kostnadsslag. 

Start- och slutdatumen som du anger måste överensstämma med start- och slutdatumen på gruppen som prognosen skapas i. Systemet använder denna begränsning och justerar datumen automatiskt om justeringar krävs. 

På **fliken Detaljer** i fönstret **Attest** kan du visa information om den prognos som var mest nyligen genererade. 

Du kan välja företag och prognosmodeller för att godkänna prognosen för användning. Som standard är rutnätet omfattar alla företag som prognostiserad efterfrågan har skapats för. För varje företag, den prognosmodell som motsvarar aktuell prognos plan som sätts upp i huvudplanering parametrar är fyllt. Du kan dock ändra den här prognosmodellen till någon prognosmodell som tillhör företaget. Om ingen förväntad efterfrågan data har skapats för ett valt företag, får du ett varningsmeddelande vid importen. 

Det är mycket viktigt att du förstår hur **spara den manuella justeringar av baslinjen demand forecast** kryssruta fungerar. Om du har gjort manuella justeringar av den statistisk baslinjeprognosen, kommer de justerade värdena att godkännas för användning även om denna kryssruta är avmarkerad. Ändringarna kan emellertid kasseras efter tillstånd. Därför nästa gång en prognos genereras, att prognosen är bara en statistisk prognos och inte har någon handmanöver, även om **överlåtelsen manuella justeringar för att efterfrågan** är markerad. Därför kan du överväga att **spara den manuella justeringar av baslinjen demand forecast** kryssrutan en mekanism som låter dig att förvara eller kasta alla manuella ändringar.

## <a name="additional-resources"></a>Ytterligare resurser

- [Gör manuella justeringar på baslinjeprognosen](manual-adjustments-baseline-forecast.md)
- [Övervaka prognosens exakthet](monitor-forecast-accuracy.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]