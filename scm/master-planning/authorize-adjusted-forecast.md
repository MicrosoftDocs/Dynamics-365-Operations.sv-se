---
title: Auktorisera en justerad prognos
description: "Inte alla prognosdata måste godkännas omedelbart. Denna artikel beskriver hur du kan ange den period som en prognos är godkända för. Det förklarar också hur du kan attestera prognos för specifika företag och prognosmodeller."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ReqDemPlanImportForecastDialog
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 72734
ms.assetid: cb8fd809-605a-4a8b-a390-636edfec21f9
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 7ff7891e9a12be75b9171a23f0a9288b3c723730
ms.contentlocale: sv-se
ms.lasthandoff: 04/25/2017


---

# <a name="authorize-an-adjusted-forecast"></a>Auktorisera en justerad prognos

[!include[banner](../includes/banner.md)]


Inte alla prognosdata måste godkännas omedelbart. Denna artikel beskriver hur du kan ange den period som en prognos är godkända för. Det förklarar också hur du kan attestera prognos för specifika företag och prognosmodeller.

Inte alla prognosdata måste godkännas omedelbart. Du kan ange start- och slutdatum för den period som prognosen är godkända för. Med denna funktion kan du frysa specifikt kostnadsslag. 

Start- och slutdatumen som du anger måste överensstämma med start- och slutdatumen på gruppen som prognosen skapas i. Systemet använder denna begränsning och justerar datumen automatiskt om justeringar krävs. 

På **fliken Detaljer** i fönstret **Attest** kan du visa information om den prognos som var mest nyligen genererade. 

Du kan välja företag och prognosmodeller för att godkänna prognosen för användning. Som standard är rutnätet omfattar alla företag som prognostiserad efterfrågan har skapats för. För varje företag, den prognosmodell som motsvarar aktuell prognos plan som sätts upp i huvudplanering parametrar är fyllt. Du kan dock ändra den här prognosmodellen till någon prognosmodell som tillhör företaget. Om ingen förväntad efterfrågan data har skapats för ett valt företag, får du ett varningsmeddelande vid importen. 

Det är mycket viktigt att du förstår hur **spara den manuella justeringar av baslinjen demand forecast** kryssruta fungerar. Om du har gjort manuella justeringar av den statistisk baslinjeprognosen, kommer de justerade värdena att godkännas för användning även om denna kryssruta är avmarkerad. Ändringarna kan emellertid kasseras efter tillstånd. Därför nästa gång en prognos genereras, att prognosen är bara en statistisk prognos och inte har någon handmanöver, även om **överlåtelsen manuella justeringar för att efterfrågan** är markerad. Därför kan du överväga att **spara den manuella justeringar av baslinjen demand forecast** kryssrutan en mekanism som låter dig att förvara eller kasta alla manuella ändringar.

<a name="see-also"></a>Se även
--------

[Gör manuella justeringar till den ursprungliga prognosen](manual-adjustments-baseline-forecast.md)

[Övervaka prognosprecisionen](monitor-forecast-accuracy.md)




