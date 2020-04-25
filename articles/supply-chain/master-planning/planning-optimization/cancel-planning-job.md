---
title: Annullera ett planeringsjobb
description: I det här avsnittet beskrivs hur du avbryter ett aktivt planeringsjobb där funktionerna för planeringsoptimering används.
author: ChristianRytt
manager: tfehr
ms.date: 02/18/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: b731aa4573b438e594ede702e6556c1be2daa549
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3213482"
---
# <a name="cancel-a-planning-job"></a>Avbryta ett planeringsjobb

[!include [banner](../../includes/banner.md)]
[!include [banner](../../includes/preview-banner.md)]

I Microsoft Dynamics 365 Supply Chain Management kan du avbryta ett aktivt planeringsjobb där funktionerna för planeringsoptimering används. När du väljer **Avbryt** i dialogrutan när ett planeringsoptimeringsjobb utlöses direkt från användargränssnittet (inte i bakgrunden) avbryts inte jobbet planeringsoptimering. Även om du får en varning om att "åtgärden har avbrutits", måste du ändå använda följande steg för att avbryta ett planeringsjobb med planeringsoptimering.


Om du vill avbryta ett aktivt planeringsjobb följer du stegen nedan. 

> [!NOTE]
> Endast aktiva jobb kan annulleras.

1. Gå till **huvudplanering \> inställning \> planer**.
2. Välj en lämplig plan för planeringskörningen.
3. Välj **historik**.
4. Markera planeringsjobbet som ska annulleras.
5. Välj **Avbryt**.

Jobbstatus kommer att vara **annullerar** tills planeringsoptimeringstjänsten bekräftar att jobbet har avbrutits. Status kommer sedan att ändras till **annullerad**.

> [!NOTE]
> Om du vill se statusändringar måste du uppdatera sidan genom att välja **uppdatera**.

## <a name="additional-resources"></a>Ytterligare resurser

[Planeringsoptimering – översikt](planning-optimization-overview.md)

[Kom igång med planeringsoptimering](get-started.md)

[Planera analys av optimeringsanpassning](planning-optimization-fit-analysis.md)

[Visa planhistorik och planeringsloggar](plan-history-logs.md)

[Använda filter på en plan](plan-filters.md)
