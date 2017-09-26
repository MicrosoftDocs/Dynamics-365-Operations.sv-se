--- 
title: "Skapa en kanban-regel för ersättning"
description: "Den här proceduren fokuserar på att ersätta en befintlig kanban-regel med en ny kanban-regel vid ett visst datum."
author: ChristianRytt
manager: AnnBe
ms.date: 06/20/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: 58b12edbbdcf77429c32193dfd850bc53f4c26a8
ms.contentlocale: sv-se
ms.lasthandoff: 07/27/2017

---
# <a name="create-a-replacement-kanban-rule"></a>Skapa en kanban-regel för ersättning

[!include[task guide banner](../../includes/task-guide-banner.md)]

Den här proceduren fokuserar på att ersätta en befintlig kanban-regel med en ny kanban-regel vid ett visst datum. Detta är användbart när ändringar i produktionsflödet eller påfyllnadsregler behöver koordineras och tidsplaneras. I proceduren används demonstrationsföretag USMF. Den här proceduren är avsedd för processingenjören eller värdeströmansvarig när de förbereder tillverkningen för ett modifierat produktionsflöde eller en ny återanskaffningsregel. Denna uppgift ersätter kanban-regel 000022 med en ny regel och ökar den högsta kvantiteten från 48 till 100 för den nya regeln.


## <a name="select-a-kanban-rule-to-replace"></a>Välj en kanban-regel att ersätta.
1. Gå till Kanban-regler.
2. Hitta och markera önskad post i listan.
    * Välj kanban-regel 000022.  

## <a name="create-a-replacement-kanban-rule"></a>Skapa en kanban-regel för ersättning
1. Klicka på Ersätt kanban-regel.
2. Ange datum och tid i fältet Giltighetsdatum.
    * Välj ett datum i framtiden, till exempel en vecka från och med nu. Detta är det datum och den tid då den nya kanban-regel blir aktiv och ersätter den gamla kanban-regeln.  
    * Om kanban-regeln ändrar sökvägen i produktionsflödet kan en annan aktivitet väljas.  I den här proceduren ska du hålla aktiviteten orörd.  
3. Klicka på OK.
    * Observera att en ny kanban-regel skapas för att ersätta kanban-regel 000022.  
    * Giltighetsdatumet anges enligt det valda datumet när du ersätter kanban-regeln.  
4. Hitta och markera önskad post i listan.
    * Välj den ersatta kanban-regel 000022.  
    * Observera att den ersatta kanban-regeln har samma datum som utgångsdatumet eftersom det är datumet när den upphör att gälla.  
5. Väl rad 1 i listan.
    * Välj den nya kanban-regel längst upp i listan. Detta är kanban-regeln med det högsta kanban-regelnumret.  
6. Klicka på länken på den valda raden i listan.
    * Klicka på kanban-regelnumret för att öppna kanban-regeln.  

## <a name="modify-maximum-quantity-for-the-replacement-kanban-rule"></a>Ändra den högsta kvantiteten för ersättningskanban-regeln
1. AngeHögsta kvantitet till "100".
    * Visa snabbfliken Kvantiteter om du vill visa fältet Högsta kvantitet. Om du ändrar den högsta kvantiteten till 100 kommer upp till 100 kanban att bearbetas.    Detta är det sista steget i den här uppgiften.  

