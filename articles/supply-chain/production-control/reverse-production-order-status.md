---
title: Återföra produktionsorderstatus
description: I denna artikel beskrivs hur du återför produktionsorderstatus.
author: johanhoffmann
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ProdParmStatusDecrease, ProdSetupStatusDecrease
audience: Application User
ms.reviewer: kamaybac
ms.custom: 70131
ms.assetid: b1e0df43-b388-4326-8fb7-501f30c89776
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1d50cbcb4031d5c9f2c814883afd1fb38777d2ba
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8903968"
---
# <a name="reverse-the-production-order-status"></a>Återföra produktionsorderstatus

[!include [banner](../includes/banner.md)]

I denna artikel beskrivs hur du återför produktionsorderstatus. 

Om du återför statusen för en produktionsorder tar själva ordern och alla åtgärder som är kopplade till flödena tillbaka till ett tidigare steg i produktionscykeln. Till exempel har en produktionsorder statusen **Tidsplanerad** och du ändrar tillbaka status till **Skapad**. I detta fall måste systemet först ändra statusvärdet till **Estimated**, som är den status som omedelbart föregår **Scheduled**. Den kan sedan ändra statusvärdet till den status som du vill **Skapad**. **Obs!** Om ordern har uppnått statusen **Rapportera som färdigt** kan du fortfarande vända det till en tidigare status. Du måste dock köra om uppskattning och grovplanering, finplanering eller båda typerna av planering om du vill uppdatera informationen på ordern. Detta steg krävs för att eventuella reservationer av återstående artikelförbrukning och åtgärdsresursförbrukning också måste återställas. Resten av denna artikel förklarar vad som sker när du återför statusen för en produktionsorder på följande sätt:

-   Från **Uppskattad** till **Skapad**
-   Från **Planerad** till **Uppskattad**
-   Från **frisläppt** till **tidsplanerad**
-   Från **startad** till **frisläppt**

## <a name="from-estimated-to-created"></a>Från Uppskattad till Skapad
När du återför statusen för en produktionsorder från **Uppskattat** till **Skapad** tas artikelförbrukningen som beräknades för artiklarna i strukturlistan bort. Lagertransaktioner på produktionsraden tas bort och fältet **Reststatus** på produktionsorderns strukturlisterader återställs till **Avslutad**. När alternativen **Härledda inköp** och **Härledd produktion** markeras, tas alla underliggande inköpsorder eller produktionsorder bort. Om du beräknade kostnaderna för produktionsordern, eller om du reserverade artiklar manuellt så att de kan användas i produktionen, tas dessa transaktioner bort.

## <a name="from-scheduled-to-estimated"></a>Från Planerad till Uppskattad
När du återför statusen från **Tidsplanerad** till **Uppskattad**, tas de tidsplanerade start- och slutdatumen bort. Kapacitetsreservationer som gjorts under planeringen tas bort och jobb som skapats under finplaneringen raderas. All information som är registrerad om grovplanering och finplanering på sidan **Produktionsorderdetaljer** återställs.

## <a name="from-released-to-scheduled"></a>Från frisläppt till tidsplanerad
När du återför statusen för en produktionsorder från **Frisläppt** till **Tidsplanerad**, leder det bara till en ändring i värdet i statusfältet.

## <a name="from-started-to-released"></a>Från startad till frisläppt
När du återför statusen för en produktionsorder från **Startad** till **Frisläpp**, återställs alla artiklar som rapporterats som färdiga. Om material har plockats eller inkommande och utgående leveranser har gått till produktion återställs även dessa inställningar. Fältet **Reststatus** på produktionsorderns strukturlisterader ändras från **Avslutad** till **Materialförbrukning**. Om tid har registrerats, eller om kvantiteter har rapporterats som färdiga för åtgärder i produktionsflödet, återförs dessa inställningar. Fältet **Reststatus** på produktionsorderns strukturlisterader ändras från **Avslutad** till **Flädesförbrukning** i produktionsflödet. Inställningarna för alla artiklar som bokförs som pågående eller som pågående arbete återförs. På sidan **Produktionsorderdetaljer** återställs de fält som visar en kvantitet som startades, eller rapporterades som avslutad. Data för dessa transaktioner återställs också.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]