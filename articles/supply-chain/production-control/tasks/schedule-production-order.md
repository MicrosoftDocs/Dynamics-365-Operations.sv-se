---
title: Tidsplanera en produktionsorder
description: I den här proceduren visas hur du tidsplanerar en produktionsorder.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ProdTableListPage, ProdSchedule, ProdRouteJob, WrkCtrCapResSum, ProdRouteJobSched, ProductionOrderScheduleDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 43d183764def1b1bea7bbe140c25e0eec0b692b1
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/29/2021
ms.locfileid: "7580586"
---
# <a name="schedule-a-production-order"></a>Tidsplanera en produktionsorder

[!include [banner](../../includes/banner.md)]

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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]