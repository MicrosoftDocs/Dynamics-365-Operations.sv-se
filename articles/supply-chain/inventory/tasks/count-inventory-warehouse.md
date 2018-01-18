---
title: "Inventering i ett lagerställe"
description: "I den här proceduren beskrivs hur du kan skapa och bokföra en lagerinventeringsjournal för att kunna räkna en viss artikel på en plats på lagerstället."
author: MarkusFogelberg
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: fa72cb0d651f5e60797fa41f6e2b2cf1891730b5
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="count-inventory-in-a-warehouse"></a>Inventering i ett lagerställe

[!include[task guide banner](../../includes/task-guide-banner.md)]

I den här proceduren beskrivs hur du kan skapa och bokföra en lagerinventeringsjournal för att kunna räkna en viss artikel på en plats på lagerstället. Proceduren gäller grundläggande lagerstyrningsfunktioner som är tillgängliga i lagerhanteringmodulen, inte de lagerfunktioner som finns i lagerstyrningsmodulen. Du kan gå igenom den här proceduren i demonstrationsdataföretaget USMF eller använda dina egna data. Om du använder dina egna data, kontrollera att du har konfigurerat produkter och platser och att du har skapat ett lagerjournalnamn för inventeringsjournaler. Lagerinventering utförs normalt av en lagerarbetare.


## <a name="create-an-inventory-counting-journal"></a>Skapa en lagerinventeringsjournal
1. Gå till Lagerhantering > Journalposter > Artikelräkning > Inventering.
2. Klicka på Ny.
3. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Namn.
4. Klicka på lagerinventeringsjournalnamnet som du vill använda i listan
    * Vissa fält kommer att fyllas i baserat på inställningarna för journalnamnet för lagerinventering som du väljer.  
5. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Arbetare.
6. Välj den arbetare som du vill ha i listan.
7. Klicka på Välj.
8. Klicka på OK.

## <a name="create-journal-lines"></a>Skapa journalrader
1. Klicka på Ny.
2. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Artikelnummer.
3. Hitta och markera önskad post i listan.
    * Om du använder demonstrationsföretaget USMF kan du välja A0001.  
4. Öppna sökningen genom att klicka på listruteknappen i fältet Plats.
5. Hitta och markera önskad post i listan.
    * Om du använder demonstrationsföretaget USMF kan du välja site 2.  
6. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Lagerställe.
7. Hitta och markera önskad post i listan.
    * Om du använder demonstrationsföretaget USMF kan du välja lagerställe 24.  
8. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Plats.
9. Hitta och markera önskad post i listan.
    * Om du använder demonstrationsföretaget USMF kan du välja platsen BULK-001.  
10. Ange ett värde i fältet Räknat.
    * Om du anger ett nummer som skiljer sig till antalet i fältet I lager, uppdateras fältet Kvantitet med diskrepansen.  
11. Klicka på Spara.

## <a name="post-the-inventory-counting-journal"></a>Bokför lagerinventeringsjournalen
1. Klicka på Bokför.
    * När du bokför en lagerinventeringsjournal och om det räknade antalet skiljer sig från antalet som rapporteras i fältet I lager där en lagerinleverans eller ett lageruttag bokförs, ändras lagernivån och värdet och redovisningstransaktioner genereras.  
2. Klicka på OK.

## <a name="view-inventory-transactions"></a>Visa lagertransaktioner
1. Klicka på Lager.
2. Klicka på Transaktioner.
    * Här kan du se alla relaterade transaktioner som skapas när du bokför en lagerinventeringsjournal.   

