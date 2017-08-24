--- 
title: "Ställa in nummerserier med hjälp av en guide"
description: "Nummerserier används för att generera läsliga, unika identifierare för huvuddataposter och transaktionsposter och som kräver dem."
author: sericks007
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 5fe6e54b4ebcf6cd611af54e7066a3e39d0e677d
ms.contentlocale: sv-se
ms.lasthandoff: 07/27/2017

---
# <a name="set-up-number-sequences-by-using-a-wizard"></a>Ställa in nummerserier med hjälp av en guide

[!include[task guide banner](../../includes/task-guide-banner.md)]

Nummerserier används för att generera läsliga, unika identifierare för huvuddataposter och transaktionsposter och som kräver dem. En huvuddata eller en transaktionpost som kräver en identifierare, kallas för en referens. Innan du kan skapa nya poster för en referens, måste du ställa in en nummerserie och koppla den till referensen. I den här proceduren förklaras hur du ställer in alla nödvändiga nummerserier samtidigt, med hjälp av en guide. Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.

1. Gå till Organisationsadministration > Nummerserier > Nummerserier.
2. Klicka på Generera.
3. Klicka på Nästa.
    * På den här sidan kan du ändra identifieringskoden, det lägsta värdet och det högsta värdet. Dessutom kan du ange om nummerserien måste vara löpande.   
    * Välj inte alternativet Kontinuerlig om du måste förallokera nummer för nummerserien.     Om du vill lägga till ett omfångsegment till formatet för en nummerserie väljer du formatet i listan och klickar på Inkludera område i format.     Om du vill ta bort ett omfångsegment från formatet för en nummerserie väljer du formatet i listan och klickar på Ta bort område från format.     Om du vill utesluta en nummerserie i den automatiska genereringen väljer du nummerserien i listan och klickar på Ta bort.  
4. Klicka på Nästa.
5. Klicka på Avsluta.


