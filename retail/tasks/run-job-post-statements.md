--- 
title: " Konfigurera och kör ett jobb för att bokföra utdrag"
description: "Den här proceduren går igenom konfigurationen och körning av regelbundet återkommande batchjobb för att bokföra utdrag för en vald butik eller grupp av butiker."
author: josaw1
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 55b22d246d6bfa9e8159fb844da95f61fcf07c62
ms.openlocfilehash: d111e914ef24b328d26fc88c059f51180fa02ee3
ms.contentlocale: sv-se
ms.lasthandoff: 07/28/2017

---
# <a name="configure-and-run-a-job-to-post-statements"></a> Konfigurera och kör ett jobb för att bokföra utdrag

[!include[task guide banner](../includes/task-guide-banner.md)]

Den här proceduren går igenom konfigurationen och körning av regelbundet återkommande batchjobb för att bokföra utdrag för en vald butik eller grupp av butiker. I proceduren används demonstrationsföretaget USRT.

1. Alla arbetsytor > .. > Butiksekonomi.
2. Klicka på Bokför utdrag.
    * Välj en organisationshierarki och sedan i organisationsnodträdet, välj antingen en enskild butik eller en nod. Välj en nod om du vill skapa batchjobbet för en grupp av butiker.  
    * Klicka på pilen om du vill lägga till ditt val.  
3. Klicka på fliken Kör i bakgrunden ...
4. Markera eller avmarkera kryssrutan Batchbearbetning.
5. Klicka på Upprepning.
6. Ange ett datum i fältet Startdatum.
7. Ange en tid i fältet Starttid.
    * Välj om du vill att slutföra återkommande efter ett visst antal körningar, vid ett visst datum eller aldrig. Välj sedan de olika alternativen för att definiera hur ofta du vill att jobbet ska köras.  
8. Klicka på OK.
9. Klicka på OK.

