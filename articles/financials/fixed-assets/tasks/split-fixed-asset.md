---
title: Dela en anläggningstillgång
description: Den här uppgiftsguiden delar en procentsats för en tillgångsförteckning till en ny tillgångsförteckning.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTable, AssetBook, AssetSplit, AssetBookLookup, LedgerJournalTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6be9de64265a4d7b5c91af3ee8acfce80c78e0f1
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1566902"
---
# <a name="split-a-fixed-asset"></a>Dela en anläggningstillgång

[!include [task guide banner](../../includes/task-guide-banner.md)]

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

