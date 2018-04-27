---
title: "Överför fysiskt lager i lagerstället"
description: "I den här proceduren beskrivs hur du kan skapa och bokföra en lageröverföringsjournal för att kunna lagret registrera förflyttningen av en artikel från en plats till en annan på samma lagerställe."
author: MarkusFogelberg
manager: AnnBe
ms.date: 03/02/2016
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
ms.openlocfilehash: bfba69731a4897906d08ff9fb9ce69e79121efeb
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="transfer-physical-inventory-within-the-warehouse"></a>Överför fysiskt lager i lagerstället

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

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

