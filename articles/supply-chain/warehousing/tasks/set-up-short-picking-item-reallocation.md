---
title: Skapa omallokering av artiklar för kort plockning
description: I den här proceduren visas hur du auktoriserar lagerarbetare att snabbt söka efter alternativa platser om det inte finns tillräckligt med lagerutrymme på den plats som de har hänvisats till.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorkException, WHSWorker
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e860a54c2306f8140947b77cdcb538160a84e06f
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3216823"
---
# <a name="set-up-short-picking-item-reallocation"></a>Skapa omallokering av artiklar för kort plockning

[!include [banner](../../includes/banner.md)]

I den här proceduren visas hur du auktoriserar lagerarbetare att snabbt söka efter alternativa platser om det inte finns tillräckligt med lagerutrymme på den plats som de har hänvisats till. Det går att använda en automatisk omallokeringsprocess som använder platsdirektiv för att hämta varorna, om dessa är tillgängliga på en annan plats. Alternativt visas, när den manuella omallokeringen används, en lista över platserna med den tillgängliga kvantiteten på den mobila enheten, vilket gör det möjligt för lagerställearbetaren att välja vilken plats lagret ska användas från. Du kan köra den här proceduren i demonstrationsdataföretaget USMF. Denna procedur är avsedd för en funktion som lades till i Dynamics 365 for Operations version 1611.


## <a name="set-up-work-exceptions"></a>Konfigurera arbetsavvikelser
1. I **navigeringsfönstret**, gå till **Lagerstyrning > Inställningar > Arbete > Arbetsundantag**.
2. Klicka på **Ny**. Det går att definiera flera arbetsundantag med olika artikelomallokeringspolicyer om du vill göra det möjligt för lagerarbetare att välja en baserat på behoven hos den försändelse som de bearbetar.  
3. Ange ett värde i fältet **Kod för arbetsundantag.** Ge arbetsundantaget en rubrik för att ange vad den används för. Till exempel "Kortplockning manuellt".  
4. I fältet **Beskrivning** anger du ett värde.
5. Välj "Kort plockning" i fältet **Undantagstyp.**
6. Välj kryssrutan **Justera lager**. Detta alternativ innebär att lagret justeras automatiskt till 0 på en kort plockad plats.  
7. Ange eller välj ett värde i fältet **Kod för standardjusteringstyp**. I USMF kan du till exempel välja "Remove Res Adj Out".  
8. Välj "Manuelll" i fältet **Omallokering av artikel.** Om du väljer manuellt, eller automatiskt och manuellt, måste lagerställearbetaren auktoriseras för att använda manuell omallokering.  

## <a name="set-up-a-worker-to-use-manual-item-reallocation"></a>Ställ in en arbetare som ska använda manuell artikelomallokering
1. Stäng sidan.
2. I **navigeringsfönstret**, gå till **Lagerstyrning > Inställningar > Arbetare**.
3. Klicka på **Redigera**.
4. I listan väljer du worker 24.
5. Expandera snabbfliken **Arbete**.
6. Välj Ja i fältet **Tillåt manuell omallokering av artikel**.

