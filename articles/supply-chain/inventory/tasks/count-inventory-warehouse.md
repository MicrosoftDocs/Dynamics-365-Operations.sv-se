---
title: Inventering i ett lagerställe
description: I denna artikel beskrivs hur du kan skapa och bokföra en lagerinventeringsjournal för att kunna räkna en viss artikel på en plats på lagerstället.
author: yufeihuang
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventJournalCount, InventJournalCreate, HcmWorkerLookUp, InventItemIdLookupSimple, InventLocationIdLookup, WMSLocationIdLookup, InventTrans
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7c8712b88867dc4be48bbdb4b905993e3ccbc73f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8870649"
---
# <a name="count-inventory-in-a-warehouse"></a>Inventering i ett lagerställe

[!include [banner](../../includes/banner.md)]

I denna artikel beskrivs hur du kan skapa och bokföra en lagerinventeringsjournal för att kunna räkna en viss artikel på en plats på lagerstället. Proceduren gäller grundläggande lagerstyrningsfunktioner som är tillgängliga i lagerhanteringmodulen, inte de lagerfunktioner som finns i lagerstyrningsmodulen. Du kan gå igenom den här proceduren i demonstrationsdataföretaget USMF eller använda dina egna data. Om du använder dina egna data, kontrollera att du har konfigurerat produkter och platser och att du har skapat ett lagerjournalnamn för inventeringsjournaler. Lagerinventering utförs normalt av en lagerarbetare.


## <a name="create-an-inventory-counting-journal"></a>Skapa en lagerinventeringsjournal
1. Gå till **Navigeringsfönster > Moduler > Lagerhantering > Journalposter > Artikelräkning > Inventering**.
2. Välj **Ny**.
3. I fältet **namn** väljer du det journalnamn för lagerinventering som du vill använda från listrutan. Vissa fält kommer att fyllas i baserat på inställningarna för journalnamnet för lagerinventering som du väljer.  
4. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Arbetare**.
5. **Välj** den arbetare som du vill ha i listan.
6. Välj **OK**.

## <a name="create-journal-lines"></a>Skapa journalrader
1. Välj **Ny**.
2. På fält **Artikelnummer** klicka på önskad post från listrutan. Om du använder demonstrationsföretaget USMF kan du välja **A0001**.  
3. På fält **site** klicka på önskad post från listrutan. Om du använder demonstrationsföretaget USMF kan du välja plats **2**.
4. På fält **Lagerställe** klicka på önskad post från listrutan. Om du använder demonstrationsföretaget USMF kan du välja lagerställe **24**.  
5. På fält **Plats** klicka på önskad post från listrutan. Om du använder demonstrationsföretaget USMF kan du välja platsen **BULK-001**.  
6. Ange ett värde i fältet Räknat. Om du anger ett nummer som skiljer sig till antalet i fältet **I lager**, uppdateras fältet **Kvantitet** med diskrepansen.  
7. Välj **Spara**.

## <a name="post-the-inventory-counting-journal"></a>Bokför lagerinventeringsjournalen
1. Välj **bokföring** När du bokför en lagerinventeringsjournal och om det räknade antalet skiljer sig från antalet som rapporteras i fältet **I lager** där en lagerinleverans eller ett lageruttag bokförs, ändras lagernivån och värdet och redovisningstransaktioner genereras.
2. Välj **OK**.

## <a name="view-inventory-transactions"></a>Visa lagertransaktioner
1. Välj **Lager**.
2. Markera **transaktioner** Här kan du se alla relaterade transaktioner som skapas när du bokför en lagerinventeringsjournal.   



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]