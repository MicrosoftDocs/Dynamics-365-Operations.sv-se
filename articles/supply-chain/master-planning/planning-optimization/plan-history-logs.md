---
title: Visa planhistorik och planeringsloggar
description: I det här avsnittet beskrivs hur du visar historiken för planeringsjobb som löses av funktionen för planeringsoptimering.
author: ChristianRytt
ms.date: 10/30/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: MPSPlanRegenerationJobList, MPSPlanRegenerationJobLogs
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: d7bba084b03f8698c8bf31d171d5e4e486ed06ad
ms.sourcegitcommit: a7649b361ec54b49c0e9ee1c1c63a8815f320225
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "6187257"
---
# <a name="view-plan-history-and-planning-logs"></a>Visa planhistorik och planeringsloggar

[!include [banner](../../includes/banner.md)]

I det här avsnittet beskrivs hur du visar historiken för planeringsjobb som löses av funktionen för planeringsoptimering i Microsoft Dynamics 365 Supply Chain Management.

Om du vill visa historiken för en plan öppnar du planen genom att gå till **huvudplanering** \> **inställningar** \> **planer** \> **huvudplaner** och väljer **historik**. I historiken visas alla jobb för den valda planen. Listan innehåller slutförda och aktiva jobb.

Jobbhistoriken i huvudplaneringskörningarna för planeringsoptimeraren innehåller bara upp till 60 poster per huvudplan. När du kör en ny huvudplaneringsberäkning tas den planens tidigaste historikpost bort.

Förutom att visa starttid och status för jobb kan du visa loggen för ett specifikt jobb. Loggen innehåller ytterligare information och varningar. Alla jobb har inte en logg. Om du vill visa loggen för ett jobb väljer du **logg**. Loggposter lagras bara i 30 dagar efter det datum då jobbet avslutades, efter det att de raderas automatiskt.

## <a name="related-resources"></a>Relaterade resurser

- [Planeringsoptimering – översikt](planning-optimization-overview.md)
- [Kom i gång med planeringsoptimering](get-started.md)
- [Planera analys av optimeringsanpassning](planning-optimization-fit-analysis.md)
- [Använda filter på en plan](plan-filters.md)
- [Annullera ett planeringsjobb](cancel-planning-job.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]