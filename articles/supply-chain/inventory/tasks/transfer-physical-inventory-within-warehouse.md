---
title: Överför fysiskt lager i lagerstället
description: I den här proceduren beskrivs hur du kan skapa och bokföra en lageröverföringsjournal för att kunna lagret registrera förflyttningen av en artikel från en plats till en annan på samma lagerställe.
author: MarkusFogelberg
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalTransfer, InventJournalCreate, InventItemIdLookupSimple, InventLocationIdLookup, WMSLocationIdLookup, InventTrans
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7344bfa3be0d7345d3ac68202c7bc26bcac8ebb9
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2019
ms.locfileid: "1845267"
---
# <a name="transfer-physical-inventory-within-the-warehouse"></a>Överför fysiskt lager i lagerstället

[!include [task guide banner](../../includes/task-guide-banner.md)]

I den här proceduren beskrivs hur du kan skapa och bokföra en lageröverföringsjournal för att kunna lagret registrera förflyttningen av en artikel från en plats till en annan på samma lagerställe. Du måste ha ett lagerjournalnamn för lageröverföringar innan du sätter igång. Du kan gå igenom den här proceduren i demonstrationsföretaget USMF med hjälp av exempelvärdena som visas, eller också kan du använda dina egna uppgifter om du har konfigurerat produkter och platser. Dessa uppgifter utförs vanligtvis av en lagerarbetare.


## <a name="create-an-inventory-transfer-journal"></a>Skapa en lageröverföringsjournal
1. Gå till Överför.
2. Klicka på Ny.
3. Ange eller välj ett värde i fältet Namn.
4. Klicka på OK.
    * Det finns alternativ för att ange från- och tilldimensioner för varje journalrad. Dessa är nödvändiga för den här journaltypen. Du kan överföra artiklar till platser med olika regler. I det här exemplet överför vi en artikel inom samma lagerställe, från en id-nummerstyrd plats till en plats som inte är id-nummerstyrd.   

## <a name="create-journal-lines"></a>Skapa journalrader
1. Klicka på Ny.
2. Ange eller välj ett värde i fältet Artikelnummer.
    * Om du använder USMF kan du välja A0001.  
3. Ange eller välj ett värde i fältet Från site.
    * Om du använder USMF kan du välja 2.  
4. Ange eller välj ett värde i fältet Till site.
    * Om du använder USMF kan du välja 2.  
5. Ange eller välj ett värde i fältet Från lagerställe.
    * Om du använder USMF kan du välja 24.  
6. Ange eller välj ett värde i fältet Till lagerställe.
    * Om du använder USMF kan du välja 24.  
7. Ange eller välj ett värde i fältet för Från plats.
    * Om du använder USMF kan du välja FL-001.  
8. Ange eller välj ett värde i fältet Till plats.
    * Om du använder USMF kan du välja BULK-001.  
9. Ange ett tal i fältet Kvantitet.
10. Klicka på fliken Lagerdimensioner.
11. Ange eller välj ett värde i fältet ID-nummer.
    * Om du använder USMF kan du välja 24.  
12. Klicka på Spara.

## <a name="post-the-inventory-transfer-journal"></a>Bokföra lageröverföringsjournalen
1. Klicka på Bokför.
2. Klicka på OK.

## <a name="view-inventory-transactions"></a>Visa lagertransaktioner
1. Klicka på Lager.
2. Klicka på Transaktioner.
    * Här kan du se de transaktioner som skapades när du bokförde din journal.  

