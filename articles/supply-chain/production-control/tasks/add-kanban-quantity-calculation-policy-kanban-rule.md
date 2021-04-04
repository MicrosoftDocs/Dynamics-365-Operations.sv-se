---
title: Lägg till en beräkning av kanban-kvantitet i en kanban-regel
description: Den här proceduren fokuserar på att skapa en beräkningspolicy för kanban-kvantitet som läggs till den i en kanban-regel för att optimera kanban-storlek och kvantiteter.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanQuantityPolicy, KanbanRules, KanbanQuantityCalculation
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a32753701c9e06c46ed9b2a9c4b0329f62f15597
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5255479"
---
# <a name="add-a-kanban-quantity-calculation-policy-to-a-kanban-rule"></a>Lägg till en beräkning av kanban-kvantitet i en kanban-regel

[!include [banner](../../includes/banner.md)]

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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]