--- 
title: Skapa en koncernintern plan
description: "I den här proceduren visas hur du skapar en koncernintern plan."
author: ShylaThompson
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqIntercompanyPlanningGroupSetup,  ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: da186f7ad74bb607fd6e7220d77c2f414789f29c
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="create-an-intercompany-plan"></a>Skapa en koncernintern plan

[!include [task guide banner](../../includes/task-guide-banner.md)]

I den här proceduren visas hur du skapar en koncernintern plan. Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.


## <a name="set-up-an-intercompany-planning-group"></a>Skapa en koncernintern planeringsgrupp 
1. Gå till koncerninterna planeringsgrupper.
    * Huvudplanering > Inställningar > Koncerninterna planeringsgrupper  
2. Använd snabbfiltret för att söka efter poster. Filtrera till exempel på värdet "10" i fältet Namn.
3. Markera vald rad i listan.
4. Klicka på Ta bort.
    * Det här steget är nödvändigt för att förkorta den koncerninterna planläggningskörningen.   Den koncerninterna planeringen kör huvudplaneringen i samtliga företag i en planläggningsgrupp, med början från den lägsta schemaläggningssekvensen.  
5. Klicka på Ja.
6. Stäng sidan.

## <a name="create-an-intercompany-plan"></a>Skapa en koncernintern plan
1. Klicka på Intercompany master planning.
    * Detta ligger på arbetsytan Master planning.  
2. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Intercompany planning group.
3. Klicka på länken på den valda raden i listan.
    * Välj koncernintern planeringsgrupp 10.  
4. Ange "2" i fältet "Number of intercompany planning iterations".
    * Koncernintern planeringsgrupp 10 har två medlemmar. Om du vill sprida förskjutningarna från källföretaget (USMF) till kundföretaget (DEMF ) måste du köra koncerninternt i båda företag två gånger. Den första upprepningen sprider begäran och identifierar förskjutningarna i källföretaget (USMF). Den andra upprepningen sprider förskjutningarna från USMF till DEMF.  
5. Välj ett alternativ i fältet First iteration.
6. Välj "Regeneration" i fältet First iteration.
7. I fältet Subsequent iterations väljer du "Regeneration".
8. Ange ett nummer i fältet Antal trådar.
    * Detta representerar antalet parallella trådar som används för planering.  
9. Klicka på OK.

## <a name="view-the-result-of-the-plan"></a>Visa resultatet av planen
1. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Plan.
2. Klicka på länken på den valda raden i listan.
    * Klicka på länken för StaticPlan. Du måste vara i företaget USMF.  
3. Klicka på Planerade order.


