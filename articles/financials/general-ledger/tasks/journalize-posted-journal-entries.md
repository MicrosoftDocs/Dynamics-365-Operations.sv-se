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
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 490e9a4beda43f6e32b87792b11153c3e8e322d6
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="journalize-posted-journal-entries"></a>Journalföra bokförda poster i redovisningsjournal

[!include [task guide banner](../../includes/task-guide-banner.md)]

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


