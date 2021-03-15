---
title: Korrekt information om lagerspårning
description: Den här proceduren går igenom processen med att skapa och bokföra en lageröverföringsjournal för att korrigera information om lagerspårning.
author: MarkusFogelberg
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalTransfer, InventJournalCreate, InventItemIdLookupSimple, InventBatchIdLookup, InventLocationIdLookup, InventDimTracking, InventTrans
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7c70dba7d21eab372cec235efa5a4be19587a409
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "5000144"
---
# <a name="correct-inventory-tracking-information"></a>Korrekt information om lagerspårning

[!include [banner](../../includes/banner.md)]

Den här proceduren går igenom processen med att skapa och bokföra en lageröverföringsjournal för att korrigera information om lagerspårning. I det här exemplet ska du uppdatera informationen för en batchkontrollerad artikel genom att ändra en felaktigt bokförd batch till en annan batch. Du kan gå igenom den här proceduren i demonstrationsdataföretaget USPI eller använda dina egna data. Om du använder dina egna data måste du ha en artikel som är batchaktiverad och den få inte vara platskontrollerad. Du måste även ha ett lagerjournalnamn inställt för lageröverföringar. Dessa uppgifter utförs vanligtvis av en lagerarbetare.


## <a name="create-an-inventory-transfer-journal"></a>Skapa en lageröverföringsjournal
1. Gå till Överför.
2. Klicka på Ny.
3. Ange eller välj ett värde i fältet Namn.
4. Klicka på OK.

## <a name="create-journal-lines"></a>Skapa journalrader
1. Klicka på Ny.
2. Ange eller välj ett värde i fältet Artikelnummer.
    * Om du använder USPI kan du välja artikeln M5003.  
3. Ange ett tal i fältet Kvantitet.
4. Klicka på fliken Lagerdimensioner.
5. I fältet Batchnummer, ange eller välj ett värde.
6. Ange eller välj ett värde i fältet Plats.
7. Ange eller välj ett värde i fältet Lagerställe.
8. I fältet Batchnummer, ange eller välj ett värde.

## <a name="post-the-journal"></a>Bokför journalen
1. Klicka på Bokför.
2. Klicka på OK.

## <a name="check-tracing-information"></a>Kontrollera spårningsinformation
1. Klicka på Lager.
2. Klicka på Spåra.
3. Klicka på OK.
    * Med denna information om spårning kan du bakåtspåra den batch du korrigeraden lagret från.  Du kan också använda artikelspårningssidan om du vill se den här informationen.  
4. Stäng sidan.

## <a name="check-inventory-transactions"></a>Kontrollera lagertransaktioner
1. Klicka på Lager.
2. Klicka på Transaktioner.
    * Här kan du se de transaktioner som skapades när du bokförde din journal.   



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]