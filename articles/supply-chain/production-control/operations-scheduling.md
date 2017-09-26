---
title: Grovplanering
description: "Det här avsnittet innehåller information om grovplanering. Du kan använda grovplaneringen för att ange en allmän uppskattning av produktionsprocessen över en viss tid."
author: ChristianRytt
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProdSchedule
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 198073
ms.assetid: 12c28b11-80aa-4668-b15b-724cb24890bd
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: eb9a9aa3fa0d1928101204e7c902a6777bbbef5b
ms.contentlocale: sv-se
ms.lasthandoff: 05/25/2017

---

# <a name="operations-scheduling"></a>Grovplanering

[!include[banner](../includes/banner.md)]


Det här avsnittet innehåller information om grovplanering. Du kan använda grovplaneringen för att ange en allmän uppskattning av produktionsprocessen över en viss tid.

Du kan tidsplanera produktionen på grov- och finplaneringsnivå. Till skillnad från finplanering bryter grovplanering inte ned verksamheten för produktionsflödet till jobb. Om du vill inkludera fler detaljer i planeringen, till exempel information om aktuell kapacitet, kan du köra finplaneringen efter det att du har kört grovplaneringen. Du kan även välja att endast köra finplaneringen. Finplanering används som regel för att planera enskilda jobb för en omedelbar eller kortsiktig tidsram.

## <a name="components-of-operations-scheduling"></a>Komponenter i grovplanering
Huvudkomponenterna i grovplaneringen är planeringsriktning, resurskapacitet och materialoptimering. Genom att använda grovplanering kan du uppnå följande mål:

-   Styra planeringsmetoden genom att planera framåt eller bakåt i tiden från ett visst datum.
-   Optimera användningen av resurser genom att schemalägga produktion som baseras på resursernas kapacitet. Denna inställning kan också hjälpa till att identifiera när alternativa resurser bör användas.
-   Optimera användningen av material genom att schemalägga produktion baserat på tillgängligheten på erforderliga material.
-   Tidsplanera och synkronisera referensproduktioner. Datum för referensproduktioner justeras när tidsplanen för produktionsorder ändras.

Du måste uppskatta kostnaden för en produktionsorder innan du kan köra grovplaneringen. Om du inte har kört en uppskattning kommer denna att köras automatiskt innan grovplaneringsprocessen påbörjas. En grovplan anger följande information:

-   Den produkt som planeras för tillverkning
-   Produktens konfiguration
-   De kvantiteter som ingår i produktionen
-   Start- och slutdatum för produktionen
-   Kapacitetsreservationerna för de resurser som utför produktionsaktiviteterna

Ställtiden, processtiden och körtiden anges för verksamheter i produktionen. När du kör grovplanering anges statusen för produktionsorder som **Scheduled**, och all verksamhet planeras i den ordning som anges av produktionsflödet. Det är emellertid endast verksamhetens tidsläng som beaktas. Start- och sluttider planeras inte.

## <a name="scheduling-direction-and-date"></a>Planeringsriktning och datum
Planeringsriktningen är avgörande för planeringsprocessen. Produktion kan planeras framåt eller bakåt från valfritt datum, beroende på tids- och planeringskrav.

-   **Framåt från planeringsdatum** – Du kan tidsplanera en produktion så att denna startar så tidigt som möjligt. Produktionen kan påbörjas idag, imorgon eller på valfritt datum i framtiden. Produktionen schemaläggs längre fram i tiden, till närmast möjliga slutdatum.
-   **Bakåt från planeringsdatum** – Du kan tidsplanera en produktion så att denna startar så tidigt som möjligt. Bakåtplanering baseras på det datum då produktionen senast måste slutföras. Tidsplanen räknar bakåt från detta datum till det senast möjliga datum då produktionen kan påbörjas och fortfarande avslutas i tid.

## <a name="resource-scheduling"></a>Resursplanering
När du kör en grovplanering är alla verksamheter i produktionsflödet datumplanerade för den resurs som specificerats för verksamheten. Dessutom är längden för varje verksamhet angiven i produktionsflödet. Om en resursgrupp anges för en verksamhet, reserverar planeringen kapacitet för gruppen. Men till skillnad från finplanering väljer grovplanering inte de specifika resurserna i gruppen. Om du arbetar med begränsad kapacitet vilar tidsplanen på tillgängligheten för de resurser som krävs för att genomföra produktionen. Grovplanering följer den verksamhetsordning som anges i produktionsflödet. Planeringen reserverar kapacitet i resursgrupperna baserat på de verksamhetstider som anges i produktionsflödet. Den sammanlagda, tillgängliga och inblandade resurskapaciteten avgör kapaciteten för resursgruppen. Kapacitetsreservationer som redan finns för resurserna beaktas som otillgänglig kapacitet. Om det inte finns tillräcklig kapacitet för produktionen, kan produktionsorder senareläggas eller till och med stoppas. Du kan även ange den effektivitet som du förväntar dig från de resurser som ingår i produktionen. Du anger effektiviteten som en procentsats i resursen. Effektivitetsprocentsatsen justerar genomflödet av resursen. Denna justering påverkar den tid som reserveras för resursen. Produktionstiderna för verksamheter som använder resursen justeras även därefter.

## <a name="operations-scheduling-and-master-planning"></a>Grovplanering och huvudplanering
Grovplaneringens tidsplan ligger även till grund för huvudplaneringen och avgör beräkningarna för materialbehoven. Grovplaneringen beaktas följande information:

-   **Eftersläpande produktion** – Artiklar som är planerade, frisläppta eller startade
-   **Materialtillgänglighet** – Lager, delproduktion och leverantörer
-   **Tillgänglig kapacitet** – Resurser som krävs för produktionen

## <a name="cancellations"></a>Annulleringar
När du kör grovplanering kan du avbryta specifika delar av rutten. Dessa inkluderar kötid, ställtid, processtid, överlappningstid och transporttider.

## <a name="finite-materials"></a>Begränsat material
Om du arbetar med begränsade material vilar planeringen dessutom på tillgängligheten för de material som krävs för produktionen. Om det inte finns tillräckligt med tillgängliga komponenter för tillverkning, kan produktionen senareläggas. Du kan basera tidsplaneringen på användning av material genom att ange de material som måste vara tillgängliga för produktion. När optimeringen sker både för resurskapaciteten och materialtillgängligheten, beräknas produktionen efter dessa begränsningar. En produktionsorder kan inte planeras att inledas förrän kapacitet och material är tillgängliga samtidigt och i erforderliga kvantiteter.

<a name="see-also"></a>Se även
--------

[Alternativ för grovplanering](operation-scheduling-options.md)



