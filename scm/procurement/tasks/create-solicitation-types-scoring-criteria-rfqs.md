--- 
title: "Skapa begäranstyper och göra poängvillkor för anbudsförfrågan"
description: "I den här handboken visas hur du skapar en typ av begäran och associerar med en poängmetod."
author: mkirknel
manager: AnnBe
ms.date: 08/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 04f8cb1a6375be9371bca2af7e4044392ce7322b
ms.openlocfilehash: c77173c5dd9f0513de5d794f7453715ceff550da
ms.contentlocale: sv-se
ms.lasthandoff: 08/02/2017

---
# <a name="create-solicitation-types-and-scoring-criteria-for-rfqs"></a>Skapa begäranstyper och göra poängvillkor för anbudsförfrågan

[!include[task guide banner](../../includes/task-guide-banner.md)]

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
4. Klicka på OK.
5. Klicka på Poängkriterier.
    * Poängkriterierna som visas är de från den poängmetod som du har associerat med typen av begäran. Du kan välja att lägga till eller ta bort kriterier på den här sidan. Det går också att lägga till nya kriterier, genom att kopiera dem från andra poängmetoder.  
6. Klicka på Kopiera kriterier.
7. Ange eller välj ett värde i fältet Poängmetod.
8. Klicka på OK.
9. Stäng sidan.

