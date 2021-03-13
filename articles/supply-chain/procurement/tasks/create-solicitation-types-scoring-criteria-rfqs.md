---
title: Skapa begäranstyper och göra poängvillkor för anbudsförfrågan
description: I den här handboken visas hur du skapar en typ av begäran och associerar med en poängmetod.
author: RichardLuan
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchRFQSolicitationType, PurchRFQCaseTableListPage, PurchCreateRFQCase, PurchRFQCaseTable, PurchRFQScoringRFQCaseCriteria, PurchRFQScoringCriteriaCopy
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 40625152a579bb269411d026d77d449902c8d4bc
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/16/2021
ms.locfileid: "5016816"
---
# <a name="create-solicitation-types-and-scoring-criteria-for-rfqs"></a>Skapa begäranstyper och göra poängvillkor för anbudsförfrågan

[!include [banner](../../includes/banner.md)]

I den här handboken visas hur du skapar en typ av begäran och associerar med en poängmetod. Den visar även hur du använder typen av begäran på en anbudsförfrågan som sedan anger standardpoängmetoden. Dessa uppgifter utförs vanligtvis av en inköpschef. Du kan använda den här proceduren i demonstrationsföretaget USMF eller på dina egna data. Du behöver ha en tillgänglig poängmetod innan du börjar.


## <a name="create-a-solicitation-type"></a>Skapa en typ av begäran
1. Gå till Anskaffning och källa > Inställning > Anbudsförfrågan > Begärantyp.
2. Klicka på Ny.
3. Skriv ett värde i fältet Namn.
4. Ange ett värde i fältet Beskrivning.
5. Välj den poängmetod du vill använda för den här typen av begäran i fältet Poängmetod.
6. Klicka på Spara.
7. Stäng sidan.

## <a name="use-the-solicitation-type"></a>Använd typen av begäran
1. Gå till Anskaffning och källa > Anbudsförfrågningar > Alla anbudsförfrågningar.
2. Klicka på Ny.
3. Välj typen av begäran som du nyss skapat i fältet Typ av begäran. 
    *   
4. Klicka på OK.
5. Klicka på Poängkriterier.
    * Poängkriterierna som visas är de från den poängmetod som du har associerat med typen av begäran. Du kan välja att lägga till eller ta bort kriterier på den här sidan. Det går också att lägga till nya kriterier, genom att kopiera dem från andra poängmetoder.  
6. Klicka på Kopiera kriterier.
7. Ange eller välj ett värde i fältet Poängmetod.
8. Klicka på OK.
9. Stäng sidan.

