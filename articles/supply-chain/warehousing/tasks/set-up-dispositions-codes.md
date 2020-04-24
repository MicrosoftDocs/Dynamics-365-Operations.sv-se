---
title: Ställ in dispositionskoder
description: I den här proceduren läggs fokus på inställningen av en dispositionskod som kan användas på en mobil enhet för inleveransprocessen för returorder.
author: ShylaThompson
manager: tfehr
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 56117445df82a8f8a69287ed1cdfca04de7abf5b
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3216929"
---
# <a name="set-up-dispositions-codes"></a>Ställ in dispositionskoder

[!include [banner](../../includes/banner.md)]

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

