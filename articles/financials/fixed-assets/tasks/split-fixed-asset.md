--- 
title: "Dela en anläggningstillgång"
description: "Den här uppgiftsguiden delar en procentsats för en tillgångsförteckning till en ny tillgångsförteckning."
author: saraschi2
manager: AnnBe
ms.date: 10/19/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: b4c1b39bcae1fa3830f3a217d1ad89e84cd72134
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="split-a-fixed-asset"></a>Dela en anläggningstillgång

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Den här uppgiftsguiden delar en procentsats för en tillgångsförteckning till en ny tillgångsförteckning.  Här används revisorrollen och USMF-demonstrationdata.


## <a name="create-a-new-fixed-asset"></a>Skapa en ny anläggningstillgång
1. Gå till anläggningstillgångar > anläggningstillgångar > Fasta tillgångar.
2. Klicka på Ny.
3. I fältet Anläggningstillgångsgrupp, ange eller välj ett värde.
4. Observera numret på anläggningstillgången som ska användas i delningsprocessen senare.
5. Skriv ett värde i fältet Namn.
6. Stäng formuläret.

## <a name="split-a-fixed-asset"></a>Dela en anläggningstillgång
1. Hitta och välj den anläggningstillgång som ska delas i listan.
2. Klicka på länken på den valda raden i listan.
3. Klicka på Books.
    * Välj räkenskapsboken för att dela till den nya tillgången.  
4. Klicka på Funktioner.
5. Klicka på Dela anläggningstillgång.
6. Ange eller välj ett värde i fältet To fixed asset.
7. I fältet To book klickar du på den nedrullningsbara knappen för att öppna sökningen.
8. I fältet Transaktionsdatum, ange ett datum.
9. Ange ett tal i fältet Procent.
10. Ange eller välj ett värde i fältet Journal name.
11. Klicka på OK.

## <a name="post-the-journal-transaction"></a>Bokför journaltransaktionen
1. Gå till Anläggningstillgångar > Journalposter > Journal för anläggningstillgångar.
2. Välj den journal som skapats med delningsprocessen i listan.
3. Klicka på Rader.
    * Kontrollera de skapade journalraderna.  En anskaffningsjusteringstransaktion skapas för den ursprungliga tillgången för att minska värdet med procenten som angetts under delningsprocessen.  En anskaffningstransaktion skapas för den nya tillgången för samma belopp.  
4. Klicka på Bokför.


