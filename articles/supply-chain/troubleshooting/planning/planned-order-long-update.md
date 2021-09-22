---
title: Planerade order tar lång tid att uppdatera
description: Vid uppdatering av kravkvantitet och/eller leveransdatum på en planerad order tar det vanligtvis minst 30 sekunder per order för att spara uppdateringen
author: ChristianRytt
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: ccf3305cc18ea0ccf2ac3e9ca0dd507fd12a9da7
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477645"
---
# <a name="planned-orders-take-a-long-time-to-update"></a>Planerade order tar lång tid att uppdatera

## <a name="symptoms"></a>Symtom

Vid uppdatering av kravkvantitet och/eller leveransdatum på en planerad order tar det vanligtvis minst 30 sekunder per order för att spara uppdateringen.

## <a name="resolution"></a>Lösning

Detta är ett känt problem med den inbyggda huvudplaneringsmotorn. Det beror på den underliggande automatiska nedbrytningen genom strukturlistan under redigeringar. Det här problemet åtgärdas i planeringsoptimering, där en planering kan uppdatera och godkänna relevanta order och, när så önskas, utlösa en planeringskörning för att uppdatera planerade order för den underliggande strukturlistan.

Ett sätt att förbättra prestanda med den inbyggda huvudplaneringsmotorn är att utföra följande steg:

1. Gå till **Huvudplanering \> Inställningar \> Planer \> Huvudplaner**.
1. Välj en plan.
1. Expandera snabbfliken **Tidsgräns i dagar**.
1. Ställ in **Nedbrytning** till *Ja* och ange fältet under den här inställningen till 0 (noll).

> [!NOTE]
> Detta begränsar tidsperioden för nedbrytningar som utförs för denna huvudplan till en enda dag.
