---
title: Justera lagernivåer i lagerstället (grundläggande lagerstyrning)
description: Den här proceduren beskriver hur du kan skapa och bokför en lagerjusteringsjournal för att justera lagernivåer för produkter på lagerstället.
author: MarkusFogelberg
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalLossProfit, InventJournalCreate, InventLocationIdLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8b397dd7efdfcd8874bc5bb44aaa12ab1dc8cb66
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "5011581"
---
# <a name="adjust-stock-levels-in-the-warehouse-basic-warehousing"></a>Justera lagernivåer i lagerstället (grundläggande lagerstyrning)

[!include [banner](../../includes/banner.md)]

Den här proceduren beskriver hur du kan skapa och bokför en lagerjusteringsjournal för att justera lagernivåer för produkter på lagerstället. Du måste ha ett lagerjournalnamn konfigurerat för lagerjusteringarna innan du sätter igång. Du kan gå igenom den här proceduren i demonstrationsdataföretaget USMF eller använda dina egna data. Dessa uppgifter utförs vanligtvis av en lagerarbetare.


## <a name="create-an-inventory-adjustment-journal"></a>Skapa en lagerjusteringsjournal
1. Gå till Lagerhantering > Journalposter > Artiklar > Lagerjustering.
2. Klicka på Ny.
3. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Namn.
4. Klicka på lagerjusteringsjournalnamnet som du vill använda i listan.
    * Vissa fält kommer att fyllas i baserat på inställningarna för journalnamnet för lagerjustering som du väljer.  
5. Klicka på OK.

## <a name="create-journal-lines"></a>Skapa journalrader
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

## <a name="validate-and-post-the-inventory-adjustment-journal"></a>Validera och bokför lagerjusteringsjournalen
1. Klicka på Validera.
2. Klicka på OK.
3. Klicka på Bokför.
    * När du bokför den här typen av journal bokförs en lagerinleverans eller -utleverans, lagernivån och värdet ändras och redovisningstransaktioner skapas.  
4. Klicka på OK.
5. Stäng formuläret.
6. Stäng sidan.

