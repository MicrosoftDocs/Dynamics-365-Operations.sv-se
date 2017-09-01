--- 
title: "Ställ in dispositionskoder"
description: "I den här proceduren läggs fokus på inställningen av en dispositionskod som kan användas på en mobil enhet för inleveransprocessen för returorder."
author: BibiSp
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: cefa614ed68d6f6f72b31b3b55fba77f0f02e889
ms.contentlocale: sv-se
ms.lasthandoff: 07/27/2017

---
# <a name="set-up-dispositions-codes"></a>Ställ in dispositionskoder

[!include[task guide banner](../../includes/task-guide-banner.md)]

I den här proceduren läggs fokus på inställningen av en dispositionskod som kan användas på en mobil enhet för inleveransprocessen för returorder. Dispositionskoder är en grupp regler som kan användas när artiklar tas emot. När till exempel en arbetare använder en mobil enhet för att ta emot artiklar som är skadade, måste användaren skanna en dispositionskod för skadade artiklar. Lagerstatusen för de mottagna varorna, arbetsmallen och platsdirektivet kan fastställas från den skannade dispositionskoden. För inleveransprocessen för inköpsorder och produktionsorderrapporten som slutförd process är användningen av en dispositionskod valfritt. För inleveransprocessen för försäljningsorder där artiklarna registreras med hjälp av en mobil enhet, är användning av dispositionskoden obligatorisk.  Guiden har skapats med demodataföretaget USMF. Den här proceduren är avsedd för lagerchefen. 

1. Gå till Lagerstyrning > Inställningar > Mobil enhet > Dispositionskoder.
2. Klicka på Ny.
    * Skapa en ny dispositionskod som ska användas för kundreturer.  
3. Skriv ett värde i fältet Dispositionskod.
4. Välj en lagerstatus där det finns lagerspärr i fältet Lagerstatus.
    * Välj "Spärr" om du använder USMF. Du kan lägga till en lagerstatus till dispositionskoden för att åsidosätta standardstatusen på orderraderna.  
5. Skriv ett värde i fältet Arbetsmall.
    * Valfritt: Välj en arbetsmallkod som associeras med en returorder. Om inget värde anges, anges arbetsmallen med hjälp av de konfigurerade standardreglerna i systemet. Om du väljer en arbetsmall begränsas de processer som dispositionskoden kan användas med. Om en dispositionskod till exempel har en arbetsmall med en arbetsorder av typen inköpsorder, kan den inte användas för att registrera artiklar som returneras av kunder.  
6. Skriv ett värde i fältet Returdispositionskod.
    * Returdispositionskoden bestämmer resten av returorderprocessen för de registrerade artiklarna. I det här exemplet ska kunden få en kreditfaktura. Lägg till en returdispositionskod som innehåller en åtgärdskredit.  

