---
title: "Skapa avskrivningsförslag"
description: "Den här proceduren beskriver hur avskrivningsbatchförslag fungerar och förklarar hur man föreslår avskrivning för anläggningstillgångar."
author: abruer
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerJournalTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: d11554ee5f26ef5a85e799194d2f75757a31c254
ms.contentlocale: sv-se
ms.lasthandoff: 09/14/2018

---

# <a name="create-depreciation-proposal"></a>Skapa avskrivningsförslag

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


