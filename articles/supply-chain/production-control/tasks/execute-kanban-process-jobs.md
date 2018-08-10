--- 
title: "Kör kanban-processjobb"
description: "Den här proceduren är avsedd för att köra kanban-processjobb."
author: ChristianRytt
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 752eab976f740606154d416678ba2381641697df
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="execute-kanban-process-jobs"></a>Kör kanban-processjobb

[!include [task guide banner](../../includes/task-guide-banner.md)]

Den här proceduren är avsedd för att köra kanban-processjobb. Det första jobbet är slutfört med den förväntade kvantiteten och har inga fel. Det andra jobbet slutförs med fel. Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF. Den här proceduren är avsedd för maskinoperatören.


## <a name="select-a-kanban-job"></a>Välj ett kanban-jobb.
1. Gå till Produktionskontroll > Kanban > Kanban-tavla för processjobb.
2. Klicka på den nedrullningsbara knappen för att öppna uppslaget i fältet Arbetsgrupp.
3. Klicka på raden med resursgrupp 1250. Detta filtrerar jobblistan så att endast jobben för arbetsgrupp 1250 visas.
    * Markera raden som har jobbstatusen Planerad.  

## <a name="complete-a-job-with-expected-quantity"></a>Slutför ett jobb med förväntad kvantitet
1. Visa eller dölj avsnittet Detaljer.
    * Det här avsnittet visar viktig information om kortnummer, artikelnummer, beställd kvantitet och aktivitetsnamn.  
2. Visa eller dölj avsnittet Produktionsinstruktioner.
    * Det här avsnittet visar produktioninstruktioner för aktiviteten. Instruktionerna kan vara text, bilder, ritningar och andra dokument.  
3. Klicka på Start.
    * Välj ett jobb som inte har slutförts. Använd statusikoner i fältet Jobbstatus för att visa jobbstatus.      
4. Klicka på Slutför.
    * Jobbet är slutfört med den förväntade kvaliteten.  

## <a name="complete-a-job-with-errors"></a>Slutför ett jobb med fel
1. Klicka på Start.
    * När ett jobb utförs, markeras nästa jobb i listan automatiskt. Detta beror på att du inte behöver välja ett jobb innan du klickar på Start.  
2. I åtgärdsfönstret, klicka på Tillverka.
3. Klicka på Slutfört (detaljer).
4. Markera vald rad i listan.
5. Ange ett nummer i fältet Felkvantitet.
6. Ange ett värde i fältet Godkänd kvantitet.
7. Klicka på OK.


