--- 
title: "Skapa en produktionsflödesversion"
description: "Den här proceduren fokuserar på att skapa en ny produktionsflödesversion."
author: cvocph
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: 3cd2ff6f410e3817f3e23a651b7a2febf38b072b
ms.contentlocale: sv-se
ms.lasthandoff: 07/27/2017

---
# <a name="create-a-production-flow-version"></a>Skapa en produktionsflödesversion

[!include[task guide banner](../../includes/task-guide-banner.md)]

Den här proceduren fokuserar på att skapa en ny produktionsflödesversion. För den här proceduren måste produktionsparametrarna för lean manufacturing och måttenheterna för klasstid definieras. Du måste också definiera en värdeström och en produktionsgrupp. Mer information om produktionsflöden och aktiviteter i lean manufacturing finns i dokumentationen om lean manufacturing för Microsoft Dynamics AX. Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.


## <a name="create-a-production-flow"></a>Skapa ett produktionsflöde
1. Gå till Produktionskontroll > Inställningar > Lean-produktionsflöde > Produktionsflöden.
2. Klicka på Ny.
3. Skriv ett värde i fältet Namn.
4. Ange ett värde i fältet Beskrivning.
5. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Namn.
6. Klicka på länken på den valda raden i listan.
    * Välj en driftenhet av typen Värdeström. En värdeström är en driftenhet som sträcker sig över alla aktiviteter och flöden för värdeströmmen. I den här fasen är driftenheter begränsade till en juridisk person och har ingen ytterligare funktion.  
7. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Produktionsgrupp.
8. Klicka på länken på den valda raden i listan.
    * Välj en produktionsgrupp för produktionsflödet. Produktionsgrupper gör att du kan definiera material, arbete och PIA-konton för en produktionsprocess. Om du vill koppla redovisningskontexten till ett produktionsflöde måste en produktionsgrupp har valts.  
9. Klicka på Spara.

## <a name="create-a-production-flow-version"></a>Skapa en produktionsflödesversion
1. Klicka på Lägg till.
2. I fältet Utgångsdatum anger du datum och tid.
    * Definiera ett utgångsdatum för versionen om det behövs. Du kan uppdatera det när du vill, även för aktiva versioner. Du kan använda det för att planera utfasningen av en version.  
3. Klicka på OK.
4. Markera vald rad i listan.
5. Skriv ett värde i fältet Enhet.
6. ResolveChanges taktenheten.
7. Ange ett värde i fältet Genomsnittlig takttid.
    * Definiera den genomsnittliga takttiden för versionen. Definiera en riktad genomsnittlig takttid för taktkontrollen för produktionsflödesversionen. Takttiden definieras som kvantitet per tidsperiod. I exemplet är takttiden 0,2 timmar per 10 enheter. För en arbetstid på 8 timmar motsvarar detta en daglig genomflödeskapacitet på 400 enheter.  
8. Ange ett värde i fältet Kvantitet per cykel.
    * Definiera kvantiteten per cykel relaterat till den genomsnittliga takttiden.  
9. Växla utökningen av avsnittet Versionsdetaljer.
10. Ange ett värde i fältet Minimal takttid.
    * Definiera den lägsta takttiden. Den minsta takttiden måste vara mindre än eller lika med den genomsnittliga takttiden.  
11. Ange ett värde i fältet Maximal takttid.
    * Den högsta takttiden måste vara större än eller lika med den genomsnittliga takttiden.  
12. Ange ett värde i fältet Period för faktisk cykeltid (dagar).
    * Ange antalet dagar i Period för faktisk cykeltid. Perioden för faktisk cykeltid är antalet dagar då jobb läggs till från den faktiska tiden (minuter) bakåt för att beräkna den faktiska cykeltiden. Värdet kan när som helst ändras och används endast för beräkningen av de faktiska cykeltiderna.  
13. Klicka på Spara.


