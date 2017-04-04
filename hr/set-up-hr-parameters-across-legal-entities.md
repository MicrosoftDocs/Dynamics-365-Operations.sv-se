---
title: "Ställa in HR parametrar över juridiska personer"
description: "Du måste ställa in delade parametrar för poster som delas av flera företag, till exempel befattningsposter. Den här artikeln innehåller information om hur du ställer in personalparametrar för juridiska personer."
author: rschloma
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
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
translationtype: Human Translation
ms.sourcegitcommit: 9397e84f03ee5b340fa2aa0a64e582fc0078526e
ms.openlocfilehash: 5df6079605d2d8d320c38d302e8e5e2cba51a3f1
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-hr-parameters-across-legal-entities"></a>Ställa in HR parametrar över juridiska personer

Du måste ställa in delade parametrar för poster som delas av flera företag, till exempel befattningsposter. Den här artikeln innehåller information om hur du ställer in personalparametrar för juridiska personer.

Vissa typer av poster, såsom läge, delas mellan företag. För dessa poster måste du ställa in delad parametrar. Du kan till exempel använda **mänskliga resurser delade parametrar** för att ställa in mänskliga resurser parametrar över juridiska personer. 

På **mänskliga resurser delade parametrar sidan** , parametrar är indelade i områden, baserade på deras funktionsduglighet. 

På **fliken identifiering** , måste du välja id typer som representerar ID-nummer som finns på sidan. Du måste ställa in identifieringtyper innan du kan ange identifieringsinformation för anställd. Information om personnummer, försäkringsnummer, Alien-ID-nummer och personliga ID-kod bibehålls på **identifiering typ** page. Klicka på om du vill definiera en ny identifieringstyp eller granska listan över befintliga typerna **personal**&gt;**inställningar**&gt;**identifieringstyper**. Du kan ange en enkel kod och beskrivning. 

På fliken **Nummersekvenser** kan du välja antalet sekvenser som används för följande poster: Anställningsnummer, befattning, användarens begärande-ID, 1-9 dokument, sökande, diskussion, förmåns-ID och personalåtgärd (om detta är aktiverat). För att bibehålla nummersekvens referenser och koder, använd **nummersekvens** listsidan. För att hitta denna sida, använd sidan sökfunktionen. 

På **fliken positioner** , ange om nya positioner som är tillgängliga för tilldelning som standard:

-   **Alltid** – tilldela arbetare till nya positioner när befattningar skapas. När befattningar skapas den **tillgänglig för tilldelningar** datum och tid på den **allmänna** fliken i den **Position** sidan anges automatiskt till datum och tid.
-   **Aldrig** – Du kan inte tilldela arbetstagare till nya positioner när positioner skapas. Om du väljer det här alternativet, måste du öppna **läge** sida för varje ny position när den blir tillgänglig, och sedan på **fliken Allmänt** anger du är **tillgängliga för tilldelning **datum att arbetstagaren uppdrag.


<a name="see-also"></a>Se även
--------

[Ställa in företagets specifika parametrar för personal](set-up-company-specific-hr-parameters.md)


