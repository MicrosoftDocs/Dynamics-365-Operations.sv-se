---
title: Koncernintern huvudplanering
description: Det här ämnet innehåller information om koncernintern huvudplanering
author: GalynaFedorova
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: e28051097905503e291e0c15a50e9363b39b2daa
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/23/2021
ms.locfileid: "7548539"
---
# <a name="intercompany-master-scheduling"></a>Koncernintern huvudplanering

[!include [banner](../../includes/banner.md)]

Koncernintern huvudplanering är ett sätt att beräkna behov och generera planerade koncerninterna order mellan flera interna företag. Koncernintern huvudplanering genomförs så många gånger som du anger. Om du vill att Microsoft Dynamics 365 Supply Chain Management ska genomföra koncernintern huvudplanering måste du ställa in huvudplanering i alla koncerninterna företag. Det innefattar ett antal upprepningar då Microsoft Dynamics 365 Supply Chain Management automatiskt skapar en koncernintern inköpsorder, vilket leder till att en koncernintern försäljningsorder skapas, vilket i sin tur leder till nya krav.

Du ställer in den koncerninterna huvudplanen och den koncerninterna planeringsordningen i parametrarna för **Huvudplanering** i alla koncerninterna företag.

För att sprida kravet genom den koncerninterna kedjan måste du ställa in parametrar för att se till att planerade inköpsorder inköpsorder bekräftas automatiskt, det vill säga tid eller kvantitet i order kan inte ändras. Ställ in den **Bekräfta tidsgräns** i disponeringsgruppen eller **Bekräfta tidsgräns** i huvudplanen. Om ingen **Bekräfta tidsgräns** ställs in skapas inga koncerninterna inköpsorder automatiskt. Endast den första körningen av huvudplaneringen leder till planerade order. Eftersom ingen koncernintern inköpsorder skapas skapas ingen koncernintern försäljningsorder och därmed skapas inga fler koncerninterna inköpsorder, och så vidare.

När du startar den koncerninterna huvudplaneringen utför Microsoft Dynamics 365 Supply Chain Management en huvudplanering i varje koncerninternt företag, och utför sedan en andra huvudplanering i varje koncerninternt företag, och så vidare tills det angivna antalet upprepningar har uppnåtts. Maximalt 30 upprepningar är möjligt men ju fler upprepningar du väljer, desto längre tid tar planeringen.

Du kan starta den koncerninterna huvudplaneringen från alla koncerninterna företag eftersom huvudplaneringen i företagen styrs av den koncerninterna planeringsordningen, det vill säga den ordning i vilken programmet prioriterar huvudplaneringarna mellan alla koncerninterna företag. Eftersom den koncerninterna planeringsordningen avgör i vilken ordning huvudplaneringen utförs i företagen, spelar det ingen roll var den koncerninterna huvudplaneringen startas. Under varje upprepning körs det aktuella företaget sist.

> [!NOTE]
> Det är lämpligast att låta den koncerninterna huvudplaneringen initieras från ett företag i Microsoft Dynamics 365 Supply Chain Management.

På sidan **Koncernintern huvudplanering** kan du starta en ordning för huvudplaneringen, som utför en huvudplanering första gången med principen för att uppdatera behovsberäkningen som du har valt för den första upprepningen för alla koncerninterna företag. Följande upprepningar använder den sekundära principen som du har valt för den andra upprepningen, och den här principen används tills antalet upprepningar som du har angivit uppnås.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
