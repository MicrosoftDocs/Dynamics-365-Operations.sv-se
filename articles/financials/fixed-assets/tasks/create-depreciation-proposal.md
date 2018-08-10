--- 
title: "Skapa ett avskrivningsförslag"
description: "Den här proceduren beskriver hur avskrivningsbatchförslag fungerar och förklarar hur man föreslår avskrivning för anläggningstillgångar."
author: saraschi2
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 07d8cf2f1c46b99dfcd1d7c3419fe835f37c5a02
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-depreciation-proposal"></a>Skapa ett avskrivningsförslag

[!include [task guide banner](../../includes/task-guide-banner.md)]

Den här proceduren beskriver hur avskrivningsbatchförslag fungerar och förklarar hur man föreslår avskrivning för anläggningstillgångar. I denna uppgift används USMF-demonstrationföretaget och revisorrollen.


## <a name="create-depreciation-proposal"></a>Skapa avskrivningsförslag
1. Gå till Anläggningstillgångar > Journalposter > Skapa avskrivningsförslag.
2. I fältet Journalnamn, öppna sökningen genom att klicka på den nedrullningsbara knappen.
3. Klicka på länken på den valda raden i listan.
4. Ange ett datum i fältet Till datum.
    * Markera alternativet Summera avskrivning för att summera månadsvisa avskrivningar till en journalrad.  
    * Till exempel om värdet för Till-datum är 31 mars 2015 skapas följande beskrivning: ”avskrivning sedan 31 januari 31 2015”. Datumfältet på de föreslagna journalraderna ställs sedan in till 31:a mars 2015.  
    * Avskrivningsförslaget kan filtreras per tillgång, tillgångsgrupp eller andra kriterier med hjälp av filteralternativet.  
    * När du använder formuläret Skapa förvärvs- eller avskrivningsförslag för anläggningstillgångar, kan du ange avskrivning i batchar. Detta rekommenderas för större förslag som kräver mer systemresurser. Om du väljer batchalternativet, kan du fortfarande använda slutföra andra uppgifter under den tidsperioden. När du föreslår avskrivning på detta sätt, beräknas avskrivningen för värdemodeller för anläggningstillgångar.  
5. Kicka på Skapa journal.

## <a name="review-depreciation-entries"></a>Granska avskrivningposter
1. Gå till Anläggningstillgångar > Journalposter > Journal för anläggningstillgångar.
2. Hitta och markera önskad post i listan.
3. Klicka på Rader.
4. Klicka på Bokför.


