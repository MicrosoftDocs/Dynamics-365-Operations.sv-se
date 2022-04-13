---
title: Fördröjningar
description: Det här ämnet innehåller information om fördröjda data i huvudplaneringen. Ett fördröjt datum är ett realistiskt förfallodatum som en transaktion får om det tidigaste uppfyllelsedatumet som huvudplaneringen beräknar infaller efter begärt datum.
author: t-benebo
ms.date: 03/31/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqTransFuturesListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19311
ms.assetid: 5ffb1486-2e08-4cdc-bd34-b47ae795ef0f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6896e2d73fa634f6d528ff4b1da8eb73b6708837
ms.sourcegitcommit: ad1afc6893a8dc32d1363395666b0fe1d50e983a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2022
ms.locfileid: "8469965"
---
# <a name="delays"></a>Fördröjningar

[!include [banner](../includes/banner.md)]

Det här ämnet innehåller information om fördröjda data i huvudplaneringen. Ett fördröjt datum är ett realistiskt förfallodatum som en transaktion får om det tidigaste uppfyllelsedatumet som huvudplaneringen beräknar infaller efter begärt datum.

Huvudplaneringen kan beräkna det tidigaste uppfyllelsedatumet för en transaktion baserat på produktionstiderna, materialtillgänglighet, kapacitettillgänglighet och olika planläggningsparametrar. 

Om en huvudplanering beräknar ett orderdatum som infaller före det aktuella datumet, kan inte ordern expedieras i tid. Därför är ordern försenad. I det här fallet inkluderar huvudplaneringen framåtplaner för ordern från aktuellt datum och som inkluderar ledtider. Dessa ledtider startar komponentartiklar på lägre nivå. Ordern får sedan ett försenat datum. Ett försenat datum är ett realistiskt förfallodatum baserat på aktuella uppgifter. I huvudplaneringen beräknas också antalet fördröjningsdagar. 

I vissa fall kan du välja att inte att beräkna fördröjningar, till exempel när användare vet att de kan påskynda ledtider genom att välja alternativa leveranssätt. 

Du kan konfigurera hur förseningar beräknas för en disponeringsgrupp. Du kan sedan koppla disponeringsgruppen till en artikel vid ett senare tillfälle. 

På sidan **Huvudplaneringsparametrar** kan du ange starttiden för beräkningen av förseningar. Om en order expedieras efter den här tiden läggs en försening på en dag till i orderns förseningsdatum. 

> [!NOTE]
> I tidigare versioner kallades beräknade förseningar *leveransplansmeddelanden*, förseningsdatumet kallades *leveransplansdatum* och en försenad transaktion kallades *en transaktion som är inställd på ett datum i framtiden*.

## <a name="limited-delays-in-production-setup-with-multiple-bom-levels"></a>Begränsade förseningar i produktionsinställningarna med flera strukturlistenivåer
När du arbetar med förseningar i en produktionsinställning som har flera strukturlistenivåer, är det viktigt att observera att endast artiklarna direkt ovanför artikeln (i strukturlistan) som orsakar fördröjningen uppdateras med en fördröjning som en del av huvudplaneringskörningen. Andra artiklar i strukturlistan får inte den fördröjning som används fram till den första huvudplaneringskörningen, när den planerade ordern för den översta nivån har godkänts eller bekräftats. 

För att undvika den här kända begränsningen kan tillverkningsorder högst upp i strukturlistan med förseningar godkännas (eller bekräftas) före nästa huvudplaneringskörning. På så sätt behålls förseningen från den fördröjda godkända planerade tillverkningsordern och alla underliggande komponenter uppdateras enligt detta.
Åtgärdsmeddelanden kan också användas för att identifiera planerade order som kan flyttas till ett senare datum, på grund av andra förseningar i strukturlistan.

## <a name="desired-date"></a>Önskat datum

På sidan **planerad order** under fliken **Förseningar** är **önskat datum** för den planerade ordern. Önskat datum för en planerad order är grunddata för förseningar, vilket är ett beräknat datum som är lika med **begärt datum** beräknat från **nettobehovet**. Om den planerade ordern är en strukturlisterad, produktionsrad eller kanban-rad, baseras önskat datum på **Behovsdatum** och det önskade datumet visas på sidan **Planerad order**.

## <a name="additional-resources"></a>Ytterligare resurser

[Disponeringsinställningar](coverage-settings.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]