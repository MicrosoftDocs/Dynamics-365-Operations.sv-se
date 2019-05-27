---
title: Validera produktionsflöde och version
description: Den här proceduren visar hur du skapar ett nytt produktionsflöde och en första version för lean manufacturing.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LeanProductionFlow
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4ae4c5f55d317a99e23ba6e76fc50ddece1e55a1
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1571414"
---
# <a name="validate-a-production-flow-and-version"></a>Validera produktionsflöde och version

[!include [task guide banner](../../includes/task-guide-banner.md)]

Den här proceduren visar hur du skapar ett nytt produktionsflöde och en första version för lean manufacturing. Förutsättningar: Produktionsparametrarna för lean manufacturing och måttenheterna för klasstid måste definieras. Du måste definiera en värdeström och en produktionsgrupp. Läs vitböckerna om lean manufacturing och bekanta dig med begreppen i produktionsflöden och aktiviteter. Den här proceduren refererar till den juridiska personen USMF i demodata. Men, under antagandet att den juridiska personen har konfigurerats för lean manufacturing, kan andra juridiska personer användas.


## <a name="create-a-production-flow"></a>Skapa ett produktionsflöde
1. Gå till Produktionskontroll > Inställningar > Lean-produktionsflöde > Produktionsflöden.
2. Klicka på Ny.
3. Skriv ett värde i fältet Namn.
4. Ange ett värde i fältet Beskrivning.
5. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Namn.
6. Klicka på länken på den valda raden i listan.
    * En värdeström är en driftenhet som sträcker sig över alla aktiviteter och flöden för värdeströmmen.   I den här fasen är driftenheter begränsade till en juridisk person och har ingen ytterligare funktion.  
7. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Produktionsgrupp.
8. Klicka på länken på den valda raden i listan.
    * Produktionsgrupper gör att du kan definiera material, arbete och PIA-konton för en produktionsprocess. Om du vill koppla redovisningskontexten till ett produktionsflöde måste en produktionsgrupp har valts.  
9. Klicka på Spara.

## <a name="create-a-production-flow-version"></a>Skapa en produktionsflödesversion
1. Klicka på Lägg till.
2. I fältet Utgångsdatum anger du datum och tid.
    * Du kan uppdatera sista giltighetsdatumet för versionen när du vill, även för aktiva versioner. Använd förfallodatumet för versionen för att planera för utfasningen av en version.  
3. Klicka på OK.
4. Markera vald rad i listan.
5. Skriv ett värde i fältet Enhet.
6. Välj taktenheten.
7. Ange ett värde i fältet Genomsnittlig takttid.
    * Definiera en riktad genomsnittlig takttid för taktkontrollen för produktionsflödesversionen.   Takttiden definieras som kvantitet per tidsperiod.  I exemplet är takttiden 0,2 timmar per 10 enheter. För en arbetstid på 8 timmar motsvarar detta en daglig genomflödeskapacitet på 400 enheter.  
8. Ange ett värde i fältet Kvantitet per cykel.
9. Expandera eller dölj avsnittet Versionsdetaljer.
10. Ange ett värde i fältet Minimal takttid.
    * Den minsta takttiden måste vara mindre än eller lika med den genomsnittliga takttiden.  
11. Ange ett värde i fältet Maximal takttid.
    * Den högsta takttiden måste vara större än eller lika med den genomsnittliga takttiden.  
12. Ange antal dagar i Period för faktisk cykeltid
    * Perioden för faktisk cykeltid är antalet dagar då jobb läggs till från den faktiska tiden (minuter) bakåt för att beräkna den faktiska cykeltiden. Värdet kan när som helst ändras och används endast för beräkningen av de faktiska cykeltiderna.  
13. Klicka på Spara.

