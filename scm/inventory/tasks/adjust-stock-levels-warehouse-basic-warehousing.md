--- 
title: "Justera lagernivåer i lagerstället (grundläggande lagerstyrning)"
description: "Den här proceduren beskriver hur du kan skapa och bokför en lagerjusteringsjournal för att justera lagernivåer för produkter på lagerstället."
author: MarkusFogelberg
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: f96db79bcb6ec26daaeb66d29edb18486daafab0
ms.contentlocale: sv-se
ms.lasthandoff: 07/27/2017

---
# Justera lagernivåer i lagerstället (grundläggande lagerstyrning)

[!include[task guide banner](../../includes/task-guide-banner.md)]

Den här proceduren beskriver hur du kan skapa och bokför en lagerjusteringsjournal för att justera lagernivåer för produkter på lagerstället. Du måste ha ett lagerjournalnamn konfigurerat för lagerjusteringarna innan du sätter igång. Du kan gå igenom den här proceduren i demonstrationsdataföretaget USMF eller använda dina egna data. Dessa uppgifter utförs vanligtvis av en lagerarbetare.


## Skapa en lagerjusteringsjournal
1. Gå till Lagerhantering > Journalposter > Artiklar > Lagerjustering.
2. Klicka på Ny.
3. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Namn.
4. Klicka på lagerjusteringsjournalnamnet som du vill använda i listan.
    * Vissa fält kommer att fyllas i baserat på inställningarna för journalnamnet för lagerjustering som du väljer.  
5. Klicka på OK.

## Skapa journalrader
1. Klicka på Ny.
2. Markera fältet för artikelnummer i listan.
3. Välj en artikel i fältet Artikelnummer. Om du använder demonstrationsdataföretaget USMF skriver du "D0001".
4. Öppna sökningen genom att klicka på listruteknappen i fältet Plats.
5. Välj en plats i listan.
6. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Lagerställe.
7. Välj ett lagerställe i listan.
    * Om du har valt en artikel med Plats som en obligatorisk dimension måste du ange platsen här.  
8. Ange ett tal i fältet Kvantitet.
    * Fältet Självkostnad anger kostnaden per enhet för lagerinleveranser. Om kostnaden inte har angetts för artikelnumret eller om du vill ändra det manuellt gör du det här.  

## Validera och bokför lagerjusteringsjournalen
1. Klicka på Validera.
2. Klicka på OK.
3. Klicka på Bokför.
    * När du bokför den här typen av journal bokförs en lagerinleverans eller -utleverans, lagernivån och värdet ändras och redovisningstransaktioner skapas.  
4. Klicka på OK.
5. Stäng formuläret.
6. Stäng sidan.

