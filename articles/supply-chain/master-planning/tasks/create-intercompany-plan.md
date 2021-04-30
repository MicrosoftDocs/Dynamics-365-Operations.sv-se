---
title: Skapa en koncernintern plan
description: I den här proceduren visas hur du skapar en koncernintern plan.
author: ChristianRytt
ms.date: 08/13/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ReqIntercompanyPlanningGroupSetup,  ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f8cf4ed879b6b2202d0b0f1f45052f5e21452967
ms.sourcegitcommit: 9b07d536b4bd8addfbdba42d2429c9fedb664635
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/07/2021
ms.locfileid: "5867360"
---
# <a name="create-an-intercompany-plan"></a>Skapa en koncernintern plan

[!include [banner](../../includes/banner.md)]

I den här proceduren visas hur du skapar en koncernintern plan. Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.

## <a name="set-up-an-intercompany-planning-group"></a>Skapa en koncernintern planeringsgrupp

1. I **navigeringfönstret**, gå till **Moduler > Huvudplanering > Inställningar > Koncerninterna planeringsgrupper**.
2. Använd snabbfiltret för att söka efter poster. Filtrera till exempel på värdet "10" i fältet Namn.
3. Markera vald rad i listan.
4. Välj **Ta bort**. Det här steget är nödvändigt för att förkorta den koncerninterna planläggningskörningen.   Den koncerninterna planeringen kör huvudplaneringen i samtliga företag i en planläggningsgrupp, med början från den lägsta schemaläggningssekvensen.  
5. Välj **Ja**.
6. Stäng sidan.

## <a name="create-an-intercompany-master-plan"></a>Skapa en koncernintern huvudplan

1. I **navigeringfönstret**, gå till **Moduler > Huvudplanering > Arbetsytor > Huvudplanering**.
2. Välj **Koncernintern huvudplanering**.  
3. Öppna sökningen genom att välja listrutan i fältet **Koncernintern planeringsgrupp**.
4. Klicka på länken på önskad rad i valda listan. Välj koncernintern planeringsgrupp 10.  
5. Ange "2" i fältet **Antal upprepningar av koncernintern planering**. Koncernintern planeringsgrupp 10 har två medlemmar. Om du vill sprida förskjutningarna från källföretaget (USMF) till kundföretaget (DEMF ) måste du köra koncerninternt i båda företag två gånger. Den första upprepningen sprider begäran och identifierar förskjutningarna i källföretaget (USMF). Den andra upprepningen sprider förskjutningarna från USMF till DEMF.  
6. Välj "Omgenerering" i fältet **Första upprepning**.
7. Välj Omgenerering i fältet **Efterföljande upprepningar**.
8. Ange ett nummer i fältet **Antal trådar.** Detta representerar antalet parallella trådar som används för planering.  
9. Välj **OK**.

## <a name="view-the-result-of-the-plan"></a>Visa resultatet av planen

1. Öppna sökningen genom att välja listrutan i fältet **Planera**.
2. Klicka på länken på önskad rad i valda listan. Välj länken för StaticPlan. Du måste vara i företaget USMF.  
3. Välj **Planerade order**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]