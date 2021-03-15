---
title: Överför fysiskt lager i lagerstället
description: I den här proceduren beskrivs hur du kan skapa och bokföra en lageröverföringsjournal för att kunna lagret registrera förflyttningen av en artikel från en plats till en annan på samma lagerställe.
author: MarkusFogelberg
manager: tfehr
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalTransfer, InventJournalCreate, InventItemIdLookupSimple, InventLocationIdLookup, WMSLocationIdLookup, InventTrans
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c00b6d18b036482cd96e2287119ddb7fd80bfa2d
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "5011457"
---
# <a name="transfer-physical-inventory-within-the-warehouse"></a>Överför fysiskt lager i lagerstället

[!include [banner](../../includes/banner.md)]

I den här proceduren beskrivs hur du kan skapa och bokföra en lageröverföringsjournal för att kunna lagret registrera förflyttningen av en artikel från en plats till en annan på samma lagerställe. Du måste ha ett lagerjournalnamn för lageröverföringar innan du sätter igång. Du kan gå igenom den här proceduren i demonstrationsföretaget USMF med hjälp av exempelvärdena som visas, eller också kan du använda dina egna uppgifter om du har konfigurerat produkter och platser. Dessa uppgifter utförs vanligtvis av en lagerarbetare.


## <a name="create-an-inventory-transfer-journal"></a>Skapa en lageröverföringsjournal
1. I **navigeringsfönstret**, gå till **Lagerhantering > Journalposter > Artiklar > Överför**.
2. Klicka på **Ny**.
3. I fältet **Namn** anger eller väljer du ett värde.
4. Klicka på **OK**. Det finns alternativ för att ange från- och tilldimensioner för varje journalrad. Dessa är nödvändiga för den här journaltypen. Du kan överföra artiklar till platser med olika regler. I det här exemplet överför vi en artikel inom samma lagerställe, från en ID-nummerstyrd plats till en plats som inte är id-nummerstyrd.   

## <a name="create-journal-lines"></a>Skapa journalrader
1. På snabbfliken **Journalrader** klickar du på **Ny**.
2. I fältet **artikelnummer** anger du eller väljer ett värde. Om du använder USMF kan du välja A0001.  
3. Ange eller välj ett värde i fältet **Från site.** Om du använder USMF kan du välja 2.  
4. Ange eller välj ett värde i fältet **Till site.** Om du använder USMF kan du välja 2.  
5. Ange eller välj ett värde i fältet **Från lagerställe.** Om du använder USMF kan du välja 24.  
6. Ange eller välj ett värde i fältet **Till lagerställe.** Om du använder USMF kan du välja 24.  
7. Ange eller välj ett värde i fältet **Från plats.** Om du använder USMF kan du välja FL-001.  
8. Ange eller välj ett värde i fältet **Till plats.** Om du använder USMF kan du välja BULK-001.  
9. Ange ett nummer i fältet **Kvantitet**.
10. På snabbfliken **Radinformation**, klicka på fliken **Lagerdimensioner**.
11. Ange eller välj ett värde i **Från lagerdimensioner**, i fältet **ID-nummer**. Om du använder USMF kan du välja 24.  
12. Klicka på **Spara**.

## <a name="post-the-inventory-transfer-journal"></a>Bokföra lageröverföringsjournalen
1. Klicka på **Inlägg** i **åtgärdsfönstret**.
2. Klicka på **OK**.

## <a name="view-inventory-transactions"></a>Visa lagertransaktioner
1. Klicka på **Lager**.
2. Klicka på **Transaktioner.** Här kan du se de transaktioner som skapades när du bokförde din journal.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]