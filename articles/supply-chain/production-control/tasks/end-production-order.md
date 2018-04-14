---
title: Avsluta en produktionsorder
description: "Den här proceduren visar hur du avslutar en produktionsorder."
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
ms.openlocfilehash: 1cc586f804a072ca5499c73ecdf7d37778cbf067
ms.contentlocale: sv-se
ms.lasthandoff: 02/06/2018

---
# <a name="end-a-production-order"></a>Avsluta en produktionsorder

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Den här proceduren visar hur du avslutar en produktionsorder. Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF. Detta är den sista proceduren av sju som förklarar produktionsorderns livscykel.


## <a name="end-a-production-order"></a>Avsluta en produktionsorder
1. Gå till Produktionskontroll > Produktionsorder > Alla produktionsorder.
    * Välj en produktionsorder som har statusen Rapporterat som färdigt.  
2. Klicka på Produktionsorder i åtgärdsfönstret.
3. Klicka på Slut.
    * På den här sidan kan du bekräfta att du vill avsluta produktionsordern.  
4. Klicka på fliken Allmänt.
5. Ange ett datum i fältet Datum.
6. Välj ”Allokering” i fältet Kassationsmetod.
    * När du väljer allokeringsmetod läggs kostnaderna från de kasserade materialen till för de färdiga varorna.  
7. Klicka på OK.

## <a name="validate-calculation-results"></a>Validera beräkningsresultatet
1. Klicka på Hantera kostnader i åtgärdsfönstret.
2. Klicka på Visa kostnadsjämförelse.
    * När du har avslutat produktionsordern kan du jämföra den uppskattade självkostnaden med den verkliga självkostnaden för att få en överblick över produktionsavvikelserna.  

