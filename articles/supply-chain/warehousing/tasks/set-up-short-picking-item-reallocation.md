--- 
title: "Skapa omallokering av artiklar för kort plockning"
description: "I den här proceduren visas hur du auktoriserar lagerarbetare att snabbt söka efter alternativa platser om det inte finns tillräckligt med lagerutrymme på den plats som de har hänvisats till."
author: YuyuScheller
manager: AnnBe
ms.date: 10/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: b67965b6c8641b5d91ab3c5b0a7a7fd28a07cba6
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-short-picking-item-reallocation"></a>Skapa omallokering av artiklar för kort plockning

[!include [task guide banner](../../includes/task-guide-banner.md)]

I den här proceduren visas hur du auktoriserar lagerarbetare att snabbt söka efter alternativa platser om det inte finns tillräckligt med lagerutrymme på den plats som de har hänvisats till. Det går att använda en automatisk omallokeringsprocess som använder platsdirektiv för att hämta varorna, om dessa är tillgängliga på en annan plats. Alternativt visas, när den manuella omallokeringen används, en lista över platserna med den tillgängliga kvantiteten på den mobila enheten, vilket gör det möjligt för lagerställearbetaren att välja vilken plats lagret ska användas från. Du kan köra den här proceduren i demonstrationsdataföretaget USMF. Denna procedur är avsedd för en funktion som lades till i Dynamics 365 for Operations version 1611.


## <a name="set-up-work-exceptions"></a>Konfigurera arbetsavvikelser
1. Gå till Lagerstyrning > Inställningar > Arbete > Arbetsavvikelser.
2. Klicka på Ny.
    * Det går att definiera flera arbetsundantag med olika artikelomallokeringspolicyer om du vill göra det möjligt för lagerarbetare att välja en baserat på behoven hos den försändelse som de bearbetar.  
3. Ange ett värde i fältet Work exception code.
    * Ge arbetsundantaget en rubrik för att ange vad den används för. Till exempel "Kortplockning manuellt".  
4. Ange ett värde i fältet Beskrivning.
5. Välj "Short pick" i fältet Exception type.
6. Välj kryssrutan Adjust inventory.
    * Detta alternativ innebär att lagret justeras automatiskt till 0 på en kort plockad plats.  
7. Ange eller välj ett värde i fältet Default adjustment type code.
    * I USMF kan du till exempel välja "Remove Res Adj Out".  
8. Välj "Manual" i fältet Item reallocation.
    * Om du väljer manuellt, eller automatiskt och manuellt, måste lagerställearbetaren auktoriseras för att använda manuell omallokering.  

## <a name="set-up-a-worker-to-use-manual-item-reallocation"></a>Ställ in en arbetare som ska använda manuell artikelomallokering
1. Stäng sidan.
2. Gå till Lagerstyrning > Inställningar > Arbetare.
3. Klicka på Redigera.
4. I listan väljer du worker 24.
5. Expandera avsnittet Work.
6. Välj Yes i fältet Allow manual item reallocation.


