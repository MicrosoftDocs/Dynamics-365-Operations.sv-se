---
title: Skapa en tidsplan för en plats
description: I den här proceduren visas hur du tidsplanerar tillverkningsorder som ännu inte har startat för en site.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ProdTableListPage, ProdSchedule, ProdRouteJob
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 070d8441700cd0051d421ea7e2210bcb668e8c22
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5820380"
---
# <a name="create-a-schedule-for-a-site"></a>Skapa en tidsplan för en plats

[!include [banner](../../includes/banner.md)]

I den här proceduren visas hur du tidsplanerar tillverkningsorder som ännu inte har startat för en site.  Demonstrationsdataföretaget USMF används för att utföra den här proceduren.


## <a name="identify-production-orders-that-are-not-started"></a>Identifiera tillverkningsorder som inte har startats
1. Gå till Produktionskontroll > Produktionsorder > Alla produktionsorder.
2. Använd snabbfiltret för att söka efter poster. Filtrera till exempel på värdet "1" i fältet Site.
    * 1 representerar en site i USMF. Om du inte använder USMF väler du en site från ditt eget företag.  
3. Öppna kolumnfiltret Status.
4. Använd ett filter på fältet "Status", med värdet "Tidsplanerad", med hjälp av filteroperatorn "är exakt".

## <a name="create-a-schedule"></a>Skapa en tidsplan
1. Markera eller avmarkera alla rader i listan.
2. Klicka på Tidsplanera i åtgärdsfönstret.
3. Klicka på Tidsplanera jobb.
4. Välj ”bakåt från leveransdatum " i fältetPlaneringsriktning.
5. Välj Nej i fältet Begränsad kapacitet.
6. Välj Nej i fältet Begränsat material.
7. Klicka på OK.
    * Detta kan ta ett tag.  

## <a name="view-the-result-of-scheduled-production-orders"></a>Visa resultatet av tidsplanerade tillverkningsorder.
1. Markera vald rad i listan.
    * Du kan markera någon rad rad.  
2. Klicka på Produktionsorder i åtgärdsfönstret.
3. Klicka på Alla jobb.
    * På den här sidan kan du se en lista med jobb. På fliken Tidsplanering kan du se Startdatum och Slutdatum för ett jobb.  
4. Klicka på Material.
    * På den här sidan kan du se den uppskattade materialförbrukningen för operationerna i produktionsordern och det aktuella tillgängliga lagret.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]