---
title: Korrekt information om lagerspårning
description: Den här proceduren går igenom processen med att skapa och bokföra en lageröverföringsjournal för att korrigera information om lagerspårning.
author: yufeihuang
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventJournalTransfer, InventJournalCreate, InventItemIdLookupSimple, InventBatchIdLookup, InventLocationIdLookup, InventDimTracking, InventTrans
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 69921651ecd0969e9cdd3cdd3740db212a1953e1
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/29/2021
ms.locfileid: "7573811"
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