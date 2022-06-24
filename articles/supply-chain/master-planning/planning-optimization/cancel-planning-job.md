---
title: Avbryta ett planeringsjobb
description: I denna artikel beskrivs hur du avbryter ett aktivt planeringsjobb där funktionerna för Planeringsoptimering används.
author: t-benebo
ms.date: 02/18/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 0474c50157295d9ecd2341b700c07f4fbf1ed51f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8900953"
---
# <a name="cancel-a-planning-job"></a>Avbryta ett planeringsjobb

[!include [banner](../../includes/banner.md)]

I Microsoft Dynamics 365 Supply Chain Management kan du avbryta ett aktivt planeringsjobb där funktionerna för Planeringsoptimering används. När du väljer **Avbryt** i dialogrutan när ett Planeringsoptimerinsjobb utlöses direkt från användargränssnittet (inte i bakgrunden) avbryts inte jobbet Planeringsoptimering. Även om du får en varning om att "åtgärden har avbrutits", måste du ändå använda följande steg för att avbryta ett planeringsjobb med Planeringsoptimering.


Om du vill avbryta ett aktivt planeringsjobb följer du stegen nedan. 

> [!NOTE]
> Endast aktiva jobb kan annulleras.

1. Gå till **huvudplanering \> inställning \> planer**.
2. Välj en lämplig plan för planeringskörningen.
3. Välj **historik**.
4. Markera planeringsjobbet som ska annulleras.
5. Välj **Avbryt**.

Jobbstatus kommer att vara **annullerar** tills Planeringsoptimerinstjänsten bekräftar att jobbet har avbrutits. Status kommer sedan att ändras till **annullerad**.

> [!NOTE]
> Om du vill se statusändringar måste du uppdatera sidan genom att välja **uppdatera**.

## <a name="additional-resources"></a>Ytterligare resurser

[Planeringsoptimering – översikt](planning-optimization-overview.md)

[Kom igång med Planeringsoptimering](get-started.md)

[Planera analys av optimeringsanpassning](planning-optimization-fit-analysis.md)

[Visa planhistorik och planeringsloggar](plan-history-logs.md)

[Använda filter på en plan](plan-filters.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]