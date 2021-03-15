---
title: Konfigurera och köra jobb för att bokföra utdrag
description: Den här proceduren går igenom konfigurationen och körning av regelbundet återkommande batchjobb för att bokföra utdrag för en vald butik eller grupp av butiker.
author: josaw1
manager: AnnBe
ms.date: 07/29/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailChannelOperationsWorkspace, RetailOperatingUnitPicker, SysRecurrence
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bed4cfb4875231d11ad76e4403c7995519d56e73
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "5003688"
---
# <a name="configure-and-run-job-to-post-statements"></a>Konfigurera och köra jobb för att bokföra utdrag

[!include [banner](../includes/banner.md)]

Den här proceduren går igenom konfigurationen och körning av regelbundet återkommande batchjobb för att bokföra utdrag för en vald butik eller grupp av butiker. I proceduren används demonstrationsföretaget USRT.

1. Alla arbetsytor > .. > Butiksekonomi.
2. Klicka på Bokför utdrag i batch.
    * Välj en organisationshierarki och sedan i organisationsnodträdet, välj antingen en enskild butik eller en nod. Välj en nod om du vill skapa batchjobbet för en grupp av butiker.  
    * Klicka på pilen om du vill lägga till ditt val.  
3. Klicka på fliken Kör i bakgrunden. ![Kör i bakgrunden](../dev-itpro/media/runbackground.png "Kör i bakgrunden") 
4. Markera eller avmarkera kryssrutan Batchbearbetning.
![Batchbearbetning](../dev-itpro/media/batchprocessing.png "Batchbearbetning och upprepning") 
5. Klicka på Upprepning.
6. Ange ett datum i fältet Startdatum.
7. Ange en tid i fältet Starttid.
    * Välj om du vill att slutföra återkommande efter ett visst antal körningar, vid ett visst datum eller aldrig. Välj sedan de olika alternativen för att definiera hur ofta du vill att jobbet ska köras.  
8. Klicka på OK.
9. Klicka på OK.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]