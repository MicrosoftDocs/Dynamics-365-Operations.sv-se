---
title: Visa planhistorik och planeringsloggar
description: I den här artikeln förklaras hur du visar historiken för planeringsjobb.
author: t-benebo
ms.date: 06/01/2020
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
ms.author: benebotg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: ab469686a009364bf53cb963506fd2107075a283
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2022
ms.locfileid: "9740942"
---
# <a name="view-plan-history-and-planning-logs"></a>Visa planhistorik och planeringsloggar

[!include [banner](../../includes/banner.md)]

I den här artikeln förklaras hur du visar historiken för planeringsjobb i Microsoft Dynamics 365 Supply Chain Management.

Om du vill visa historiken för en plan öppnar du planen genom att gå till **huvudplanering** \> **inställningar** \> **planer** \> **huvudplaner** och väljer **historik**. I historiken visas alla jobb för den valda planen. Listan innehåller slutförda och aktiva jobb.

Systemet behåller maximalt 60 historikposter per huvudplan och tar bort poster som är äldre än 30 dagar. Varje gång du kör en ny huvudplaneringsberäkning lägger systemet till en ny historikpost och rensar sedan de äldsta posterna efter behov.

Förutom att visa starttid och status för jobb kan du visa loggen för ett specifikt jobb. Loggen innehåller ytterligare information och varningar. Alla jobb har inte en logg. Om du vill visa loggen för ett jobb väljer du **logg**. Loggposter lagras bara i 30 dagar efter det datum då jobbet avslutades, efter det att de raderas automatiskt.

Om alternativet **batchbearbetning** på snabbfliken **Kör i bakgrunden** var aktiverat när huvudplaneringsbearbetningen skapades, visar batchjobbloggen mer information om eventuella varningar och fel som genererades under huvudplaneringskörningen. Till exempel fångas automatiskt bekräftande fel bara i batchjobbloggen. De visas inte i loggar på sidan **historik**.

Gör på följande sätt om du vill visa automatiskt bekräftande fel och andra varningar eller fel som uppstod under en huvudplaneringskörning.

1. Gå till **Systemadministration \> Förfrågningar \> Batchjobb**.
1. Sök och välj den post som representerar den huvudplaneringskörning som du är intresserad av. (Exempelvis värdet av fältet **Jobbeskrivning** kan börja med *Huvudplanering*.)
1. Följ ett av dessa steg, beroende på om du använder *förbättrat formulär* eller *äldre (ej förbättrat) formulär* för sidorna **Batch-jobb**:

    - Om du använder det förbättrade formuläret: Välj **batchjobbhistorik** i åtgärdsfönstret. På sidan **Batchjobbhistorik** i åtgärdsfönstret, välj **Logg**.
    - Om du använder det äldre formuläret i åtgärdsfönstret, på fliken **Batch-jobb**, välj **Logg**.

1. Välj **Meddelandeinformation** om du vill öppna fönstret **Meddelandeinformation** där du kan visa alla varningar och fel som har samlats in under bearbetningen.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
