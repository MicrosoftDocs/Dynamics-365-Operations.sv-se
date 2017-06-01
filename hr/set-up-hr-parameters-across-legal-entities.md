---
title: "Ställa in HR parametrar över juridiska personer"
description: "Du måste ställa in delade parametrar för poster som delas av flera företag, till exempel befattningsposter. Den här artikeln innehåller information om hur du ställer in personalparametrar för juridiska personer."
author: rschloma
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: HcmSharedParameters
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 51891
ms.assetid: c7d8f58c-d78a-4035-abbf-2b0ce16109fe
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: f93d548adc4ae81eb89ac7c01cdae79d20b763aa
ms.contentlocale: sv-se
ms.lasthandoff: 05/25/2017


---

# <a name="set-up-hr-parameters-across-legal-entities"></a>Ställa in HR parametrar över juridiska personer

[!include[banner](includes/banner.md)]


Du måste ställa in delade parametrar för poster som delas av flera företag, till exempel befattningsposter. Den här artikeln innehåller information om hur du ställer in personalparametrar för juridiska personer.

Vissa typer av poster, såsom läge, delas mellan företag. För dessa poster måste du ställa in delad parametrar. Du kan till exempel använda **mänskliga resurser delade parametrar** för att ställa in mänskliga resurser parametrar över juridiska personer. 

På **mänskliga resurser delade parametrar sidan** , parametrar är indelade i områden, baserade på deras funktionsduglighet. 

På **fliken identifiering** , måste du välja id typer som representerar ID-nummer som finns på sidan. Du måste ställa in identifieringtyper innan du kan ange identifieringsinformation för anställd. Information om personnummer, försäkringsnummer, Alien-ID-nummer och personliga ID-kod bibehålls på **identifiering typ** page. För att definiera en ny typ av identifiering eller granska listan över befintliga typer, klicka på **Mänskliga resurser** &gt; **Inställningar** &gt; **Identifieringstyper**. Du kan ange en enkel kod och beskrivning. 

På fliken **Nummersekvenser** kan du välja antalet sekvenser som används för följande poster: Anställningsnummer, befattning, användarens begärande-ID, 1-9 dokument, sökande, diskussion, förmåns-ID och personalåtgärd (om detta är aktiverat). För att bibehålla nummersekvens referenser och koder, använd **nummersekvens** listsidan. För att hitta denna sida, använd sidan sökfunktionen. 

På **fliken positioner** , ange om nya positioner som är tillgängliga för tilldelning som standard:

-   **Alltid** – Du kan tilldela arbetstagare till nya positioner när positioner skapas. När befattningar skapas kommer datum och tid för **Tillgänglig för tilldelningar** på fliken **Allmänt** på sidan **Position** anges automatiskt till skapandedatum och -tid.
-   **Aldrig** – Du kan inte tilldela arbetstagare till nya positioner när positioner skapas. Om du väljer det här alternativet, måste du öppna **läge** sida för varje ny position när den blir tillgänglig, och sedan på **fliken Allmänt** anger du är **tillgängliga för tilldelning**datum att arbetstagaren uppdrag.


<a name="see-also"></a>Se även
--------

[Ställa in företagsspecifika HR parametrar](set-up-company-specific-hr-parameters.md)




