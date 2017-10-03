--- 
title: "Lägg till en beräkning av kanban-kvantitet i en kanban-regel"
description: "Den här proceduren fokuserar på att skapa en beräkningspolicy för kanban-kvantitet som läggs till den i en kanban-regel för att optimera kanban-storlek och kvantiteter."
author: ChristianRytt
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
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: f9e0ccf25a346d54e48f51b0866f0c11e98bf0a0
ms.contentlocale: sv-se
ms.lasthandoff: 07/27/2017

---
# <a name="add-a-kanban-quantity-calculation-policy-to-a-kanban-rule"></a>Lägg till en beräkning av kanban-kvantitet i en kanban-regel

[!include[task guide banner](../../includes/task-guide-banner.md)]

Den här proceduren fokuserar på att skapa en beräkningspolicy för kanban-kvantitet som läggs till den i en kanban-regel för att optimera kanban-storlek och kvantiteter. Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF. Den här proceduren är avsedd för den värdeströmsansvarige. Den här proceduren är en förutsättning när du skapar proceduren Beräkna förslag till kanban-kvantitet. 


## <a name="create-a-kanban-quantity-calculation-policy"></a>Skapa en beräkningspolicy för kanban-kvantitet
1. Gå till Produktionskontroll > Periodiska uppgifter > Beräkning av kanban-kvantitet > Beräkningspolicyer för kanban-kvantitet.
2. Klicka på Ny.
3. Skriv ett värde i fältet Namn.
    * Skriv till exempel Speaker2016.  
4. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Huvudplan.
5. Hitta och markera önskad post i listan.
    * Välj StaticPlan för att beräkna behov.  
6. Klicka på länken på den valda raden i listan.
7. Klicka på Spara.
8. Ange "1" i fältet Minsta kanban-kvantitet.
    * Detta är det extra antal kanbans som ingår i beräkningen av kanban-kvantitet.  
9. Ange säkerhetsfaktorn till "1".
    * Detta är den faktor som används för att beräkna ytterligare kvantitet för säkerhetslager.  
10. Ange "30" i fältet Dagar före.
    * Detta är det antal dagar före beräkningsdatumet för kanban-kvantitet som ingår i efterfrågeberäkningen.  
11. Ange "30" i fältet Dagar efter.
    * Detta är det antal dagar framåt från beräkningsdatumet för kanban-kvantitet som ingår i efterfrågeberäkningen.  Den formel som används för beräkning visas med de faktiska värdena. Till exempel, Kanban-kvantitet = ((Genomsnittlig daglig efterfrågan x ledtid x 2,00) / produktkvantitet per materialhanteringsenhet) + 1  
12. Stäng sidan.

## <a name="add-the-kanban-quantity-calculation-policy-to-a-kanban-rule"></a>Lägg till beräkningspolicyn för kanban-kvantitet till en kanban-regel
1. Gå till Produktinformationshantering > Lean manufacturing > Kanban-regler.
2. Hitta och markera önskad post i listan.
    * Välj kanban-regel 000020 för den här proceduren.  
3. Klicka på länken på den valda raden i listan.
4. Växla expanderingen av avsnittet Beräkningspolicyer för kanban-kvantitet.
5. Klicka på Lägg till.
    * Lägg till beräkningspolicyn för kanban-kvantitet som du precis har skapat i föregående underuppgift.  
6. Markera vald rad i listan.
7. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Namn.
8. Klicka på länken på den valda raden i listan.
    * Välj policyn Speaker2016 som du precis har skapat i föregående underuppgift.  


