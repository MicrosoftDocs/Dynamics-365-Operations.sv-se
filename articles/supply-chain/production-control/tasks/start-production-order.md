---
title: Starta en produktionsorder
description: "Den här proceduren visar hur du startar en produktionsorder i fabriken."
author: johanhoffmann
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: dadf0e87eac8522f61bb094c146e37f46a21fc09
ms.openlocfilehash: 3b5657e5eb2719702eae3a3c5178b3a04f7545e3
ms.contentlocale: sv-se
ms.lasthandoff: 02/06/2018

---
# <a name="start-a-production-order"></a>Starta en produktionsorder

[!include [task guide banner](../../includes/task-guide-banner.md)]

Den här proceduren visar hur du startar en produktionsorder i fabriken. Tids- och materialförbrukning rapporteras i den här processen. Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF. Detta är den femte proceduren av sju som förklarar produktionsorderns livscykel.


## <a name="start-a-production-order"></a>Starta en produktionsorder
1. Gå till Produktionskontroll > Produktionsorder > Alla produktionsorder.
    * Välj en produktionsorder som har statusen Frisläppt.  
2. Klicka på Produktionsorder i åtgärdsfönstret.
3. Klicka på Start.
    * På den här sidan kan du bekräfta produktionsorderns start.  
4. Klicka på fliken Allmänt.
5. I Från Oper. Nr. fältet, ange"10".
6. Välj "Alltid" i fältet Automatisk flödesförbrukning.
7. Klicka på kryssrutan Bokför ruttkort nu.
8. Välj "Alltid" i fältet Automatisk strukturlisteförbrukning.
9. Klicka på kryssrutan Bokför plocklista nu.
10. Klicka på kryssrutan Skriv ut plocklista.
11. Klicka på OK.
    * Det här är den utskrivna plocklistan som visar det material som används för produktionsordern.  
12. Stäng sidan.

## <a name="validate-the-picking-list"></a>Validera plocklistan
1. Klicka på Visa i åtgärdsfönstret.
2. Klicka på Plocklista.
3. Hitta och markera önskad post i listan.
4. Klicka på länken på den valda raden i listan.
5. Klicka på Redigera.
6. Ange ett värde i fältet Förbrukning.
7. Klicka på Bokför.
8. Klicka på OK.
    * I plocklistejournalen bokförs materialet som förbrukas av produktionsordern. Innan du bokför journalen kan du göra justeringar om det finns en skillnad mellan den beräknade kvantiteten och den verkliga förbrukade kvantiteten.  
9. Klicka på fliken GridPanel.
10. Stäng sidan.

## <a name="verify-the-route-card-journal"></a>Verifiera flödeskortjournalen
1. Klicka på Visa i åtgärdsfönstret.
2. Klicka på Flödeskort.
3. Hitta och markera önskad post i listan.
4. Klicka på länken på den valda raden i listan.
5. Klicka på Redigera.
6. Ange ett värde i fältet Timmar.
7. Klicka på Bokför.
8. Klicka på OK.
    * I flödeskortjournalen registreras tidsåtgången för enskilda åtgärder. Varu- och felkvantiteten kan också rapporteras.  

