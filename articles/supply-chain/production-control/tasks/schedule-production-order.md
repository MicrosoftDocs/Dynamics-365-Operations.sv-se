--- 
title: Tidsplanera en produktionsorder
description: "I den här proceduren visas hur du tidsplanerar en produktionsorder."
author: johanhoffmann
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: c71192e93ca44efb69dea5622a48a3e462c54ec5
ms.contentlocale: sv-se
ms.lasthandoff: 07/27/2017

---
# <a name="schedule-a-production-order"></a>Tidsplanera en produktionsorder

[!include[task guide banner](../../includes/task-guide-banner.md)]

I den här proceduren visas hur du tidsplanerar en produktionsorder. Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF. Detta är den tredje proceduren av sju som förklarar produktionsorderns livscykel.


## <a name="schedule-a-production-order"></a>Tidsplanera en produktionsorder
1. Gå till Produktionskontroll > Produktionsorder > Alla produktionsorder.
    * Välj en produktionsorder som har statusen Uppskattad.  
2. Klicka på Tidsplanera i åtgärdsfönstret.
3. Klicka på Tidsplanera jobb.
    * Parametrarna för schemaläggning ställs in på den här sidan. Du kan ställa in parametrarna för vissa användare eller alla användare.  
4. Välj Framåt från idag i fältet Planeringsriktning.
5. Ange ett datum i fältet Planeringsdatum.
6. Markera eller avmarkera kryssrutan Begränsad kapacitet.
7. Markera eller avmarkera kryssrutan Begränsat material.
8. Klicka på OK.

## <a name="view-the-scheduling-results"></a>Visa resultaten av tidsplaneringen
1. Klicka på Produktionsorder i åtgärdsfönstret.
2. Klicka på Alla jobb.
    * På den här sidan visas schemalagda jobb som du precis har genererat.  
3. Utöka eller komprimera avsnittet Tidsplanering.
    * På snabbfliken Tidsplanering kan du visa det schemalagda datumet och tiden.  
4. Klicka på Förfrågningar.
5. Klicka på Kapacitetsbeläggning.
    * Sidan Kapacitetsbeläggning visar den kapacitet som reserverats genom finplanering, det totala antalet timmar som är reserverat för närvarande för resursen och antalet timmar som återstår för finplanering för resursen.  
6. Stäng sidan.
7. Stäng sidan.

