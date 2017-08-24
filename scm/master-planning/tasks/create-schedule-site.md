--- 
title: "Skapa en tidsplan för en plats"
description: "I den här proceduren visas hur du tidsplanerar tillverkningsorder som ännu inte har startat för en site."
author: YuyuScheller
manager: AnnBe
ms.date: 06/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: a611cb773919284b2bbe55395a7ec2b947d5c0b4
ms.contentlocale: sv-se
ms.lasthandoff: 07/27/2017

---
# <a name="create-a-schedule-for-a-site"></a>Skapa en tidsplan för en plats

[!include[task guide banner](../../includes/task-guide-banner.md)]

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


