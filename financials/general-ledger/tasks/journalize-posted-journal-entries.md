--- 
title: "Journalföra bokförda poster i redovisningsjournal"
description: "Den här proceduren visar dig hur du journalför bokförda journalposter."
author: aprilolson
manager: AnnBe
ms.date: 10/24/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 450bb7fdcc866f45c2fd3357a5ee25e6c6f929c1
ms.contentlocale: sv-se
ms.lasthandoff: 07/27/2017

---
# <a name="journalize-posted-journal-entries"></a>Journalföra bokförda poster i redovisningsjournal

[!include[task guide banner](../../includes/task-guide-banner.md)]

Den här proceduren visar dig hur du journalför bokförda journalposter. I proceduren används demonstrationsföretag USMF.

1. Validera inställningarna för journalföring under General ledger > Ledger setup > General ledger parameters.
2. Fältet Extended ledger journal kan anges som Yes eller No. Om "Yes" kommer rapportutdatan att skilja sig åt.
3. Välj om perioden kan stängas även om journalföringsprocessen inte har körts.
    * Om detta alternativ är inställt på "Yes" kan inte perioden stängas förrän journalföringsprocessen har slutförts för den perioden.  
4. Stäng sidan.
5. Gå till Redovisning > Periodiska uppgifter > Journalföring.
6. Klicka på Filter.
7. Markera raden med filtervillkoret som du vill definiera.
8. Ange eller välj filterkriterier i fältet Criteria.
9. Klicka på OK för att stänga filtersidan.
10. Starta journalföringsprocessen genom att klicka på OK.
    * En rapport skapas när processen är slutförd.  


