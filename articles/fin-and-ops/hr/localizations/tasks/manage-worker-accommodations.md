--- 
title: Hantera arbetstagarnas logi
description: "Den här proceduren går igenom stegen för att ställa in logityper för arbetsmiljön, till exempel ergonomiska stolar eller periodiska raster."
author: ShielaSogge
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Operations, Talent
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 10d34d0b2eca95034d1f67931ff72a035be9a6b8
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="manage-worker-accommodations"></a>Hantera arbetstagarnas logi

[!include[task guide banner](../../../includes/task-guide-banner.md)]

Den här proceduren går igenom stegen för att ställa in logityper för arbetsmiljön, till exempel ergonomiska stolar eller periodiska raster. Här visas även hur du tilldelar dessa logityper till en arbetare och antingen godkänner eller avslår logitypen. Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.


## <a name="setup-accommodations"></a>Ställ in logi
1. Gå till Personal > Inställningar > Boendetyper.
2. Klicka på Ny.
3. Ange ett namn för boendet i fältet Logityp. Exempel: Tangentbord.
4. Ange en beskrivning av logitypen i fältet Beskrivning. Exempel: Ergonomiskt tangentbord.
5. Ange eventuell information som hjälper till att klargöra login i fältet Anmärkning.
6. Klicka på Spara.
7. Stäng sidan.

## <a name="assign-accommodations"></a>Tilldela logi
1. Gå till Personal > Arbetare > Medarbetare.
2. Välj en medarbetare från listan.
3. Klicka på medarbetarens namn för att visa information om den medarbetare som begär login.
4. Expandera snabbfliken Personlig information.
5. Klicka på Logi.
6. Klicka på Ny.
7. Välj lämplig logi i fältet Logityp. Exempel: Tangentbord
8. Välj den arbetsuppgift som kräver login i fältet Arbetsuppgift.
9. Ställ in lämplig status i fältet Status. Exempel: Rimligt
    * Följande statusalternativ finns tillgängliga. Begärt anger att login har skapats men ännu inte har granskats. Rimligt anger att login är rimlig och används och kommer att godkännas. Oskälig anger att login kommer att innebära en orimlig börda för arbetsgivaren och har avslagits. I det här exemplet godkändes begäran direkt eftersom logibegäran var minimal.  
10. Välj den person som godkände logibegäran i fältet Godkänt.
11. Klicka på Välj.
12. Ange datum och tid när logibegäran godkändes i fältet Godkännandedatum.
13. Expandera avsnittet Anmärkning.
14. Ange de informations- eller resurskostnader som gör det lättare att klargöra påverkan av login i fältet Ekonomisk.
    * Om login har nekats kan svarsfältet användas för att ange varför begäran avslogs.  
15. Klicka på Spara.


