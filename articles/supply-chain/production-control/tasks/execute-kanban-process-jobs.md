---
title: Kör kanban-processjobb
description: Den här proceduren är avsedd för att köra kanban-processjobb.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanBoardWorkCell, KanbanJobStatusUpdate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 10f8a464207fc3b1c34638a9f55df7b53a69b357
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5259804"
---
# <a name="execute-kanban-process-jobs"></a>Kör kanban-processjobb

[!include [banner](../../includes/banner.md)]

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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]