--- 
title: "Masstäng räkenskapsperiod"
description: "I den här proceduren visas hur du spärrar eller permanent stänger ner en period eller mer än en juridisk person åt gången."
author: aprilolson
manager: AnnBe
ms.date: 10/24/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: b176adc2cbd23647b98cf55e94829e1ea9637c95
ms.contentlocale: sv-se
ms.lasthandoff: 07/27/2017

---
# <a name="mass-financial-period-close"></a>Masstäng räkenskapsperiod

[!include[task guide banner](../../includes/task-guide-banner.md)]

I den här proceduren visas hur du spärrar eller permanent stänger ner en period eller mer än en juridisk person åt gången. Dessutom kommer uppgiften att visa hur du begränsar bokföring från användargrupper till specifika moduler.

1. Gå till General ledger > Period close > Ledger calendars.
    * Observera att listan med juridiska personer som visas är beroende av räkenskapskalendern som har valts på sidan. Endast juridiska personer som använder vald räkenskapskalender kommer att visas.  
2. Klicka på Redigera.
3. Välj den period som du vill ändra statusen för.
4. Välj den juridiska person som du vill uppdatera statusen för.
    * Du kan snabbt välja alla juridiska personer genom att välja bocken uppe på rutnätets vänstra sida.  
5. Välj Update module access för att definiera bokföringsåtkomsten för en vald modul.
    * Modulstatusen kan också uppdateras individuellt genom att redigera posterna i rutnätet. Knappen är praktisk när du snabbt vill uppdatera flera juridiska personposter.  
6. Markera den modul för vilken du vill uppdatera statusen i programmodulen. Klicka på Välj.
7. Markera All, None eller en specifik användargrupp i åtkomstnivån. Klicka på Välj.
    * Alla innebär att alla användare med redigeringsåtkomst till modulen kan bokföra om perioden är öppen. "None" innebär att användare inte kan bokföra i modulen om perioden är öppen. En specifik användargrupp anger att endast användare i gruppen får bokföra i modulen, om perioden är öppen.  
8. Klicka på Uppdatera.
9. Välj en annan period för att uppdatera statusen.
10. Välj de juridiska personer för vilka du vill uppdatera periodstatusen.
11. Välj Update period status och ange statusen som On hold, Open, eller Permanently closed.
    * Öppen visar att bokföring kan göras i perioden, förutsatt att användare har åtkomst. "On hold" innebär att inga bokföringar till perioden kan genomföras, men den kan öppnas igen. "Permanently closed" innebär att perioden är stängd och aldrig kan öppnas på nytt. Inga justeringar kan bokföra. Vi rekommenderar ingen att ställa in en period som "Permanently closed" förrän alla justeringar och revisioner har avslutats.  
12. Klicka på Uppdatera.

