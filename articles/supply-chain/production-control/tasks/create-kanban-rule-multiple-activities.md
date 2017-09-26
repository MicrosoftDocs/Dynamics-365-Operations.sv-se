--- 
title: "Skapa en kanban-regel för flera aktiviteter"
description: "Den här proceduren visar hur du skapar en kanban-regel som omfattar flera aktiviteter från ett produktionsflöde."
author: ChristianRytt
manager: AnnBe
ms.date: 08/24/2016
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
ms.openlocfilehash: 5b4c6f919072dd6497b0eab548077f68fc46dbf5
ms.contentlocale: sv-se
ms.lasthandoff: 07/27/2017

---
# <a name="create-a-kanban-rule-for-multiple-activities"></a>Skapa en kanban-regel för flera aktiviteter

[!include[task guide banner](../../includes/task-guide-banner.md)]

Den här proceduren visar hur du skapar en kanban-regel som omfattar flera aktiviteter från ett produktionsflöde. Det demonstrationsdataföretag som används för att skapa den här uppgiften är USMF. Den här uppgiften är avsedd för processingenjören eller värdeströmansvarig när de förbereder tillverkningen av en ny eller ändrad produkt i en resurssnål miljö.


## <a name="create-a-new-kanban-rule"></a>Skapa en ny kanban-regel
1. Gå till Produktinformationshantering > Lean manufacturing > Kanban-regler.
2. Klicka på Ny.
3. Välj Tidsplanerat i fältet Återanskaffningsstrategi.
4. Ange eller välj ett värde i fältet Första planaktivitet.
    * Välj SpeakerAssemblyAndPolish.  
5. Markera kryssrutan Flera aktiviteter.
    * Syftet är att inkludera mer än en aktivitet i kanban-regeln. Du kan välja en sökväg i produktionsflödet när du väljer den senaste planaktiviteten.  
6. Ange eller välj ett värde i fältet Sista planaktivitet.
    * Välj SpeakerTestAndPackaging. När du har valt värdet öppnas en sida automatiskt. Markera kanban-flödet SpeakerAssemblyAndPolish > SpeakerTestAndPackaging. Klicka på OK.  
7. Expandera avsnittet Detaljer.
8. Ange eller välj ett värde i fältet Produkt.
    * Välj artikel L0006.  

## <a name="create-kanban-and-view-jobs"></a>Skapa kanban och visa jobb
1. Expandera avsnittet Kanbans.
2. Klicka på Lägg till.
3. Ange "1" i fältet Antal nya kanban.
    * Detta skapar en kanban.  
4. Ange produktkvantiteten till "3".
    * Kanban kommer att bearbeta 3 produkter.  
5. Ange datum och tid i fältet Förfallodatum- och tid.
    * Du kan ange Idag.  
6. Klicka på Skapa.
7. Klicka på Detaljer.
    * Observera att kanban har två processjobb från produktionsflödet. Det första är SpeakerAssemblyAndPolish och det andra är SpeakerTestAndPackaging.  
    * Detta är det sista steget!  

