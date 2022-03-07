---
title: Produktionsplanering
description: Det här ämnet beskriver planering för produktion och förklarar hur du ändrar planerade tillverkningsorder genom att använda Planeringsoptimering.
author: ChristianRytt
manager: tfehr
ms.date: 12/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-12-15
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: eda22aa6f1e8d665d8ef390f24b247a76d4c2956
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4992405"
---
# <a name="production-planning"></a>Produktionsplanering

Planeringsoptimering stöder flera produktionsscenarier. Om du migrerar från den befintliga, inbyggda huvudplaneringsmotorn, är det viktigt att du känner till vissa ändrade beteende.

<!-- The following video gives a short introduction to some of the current capabilities. 
KFM: Link to video for production functionality, coming soon... -->

## <a name="planned-production-orders"></a>Planerade produktionsorder

När huvudplaneringen skapar planerade order för att uppfylla behov, bestäms ordertypen av värdet i fältet **Typ av planerad order**. Om fältet **Typ av planerad order** anges till *Produktion*, skapas planerade produktionsorder. Dessa planerade tillverkningsorder innehåller information om den aktiva strukturlistan och flödes-ID från de relaterade produktionsinställningarna.

## <a name="requirements-from-boms"></a>Krav från strukturlistor

Strukturlisteinformationen används vid huvudplaneringen. Planutleveransen omfattar materialleveranser för att täcka relaterad materialbehov för produktion.

Under huvudplaneringen används den aktuella aktiva strukturlistan för att avgöra vilket material som krävs för produktionen. Detta steg görs genom alla nivåer i strukturlistestrukturen som hör till den tillverkningsorder som krävs. Materialbehov uppfylls genom att använda tillgänglig lagerbehållning, befintlig lagerbehållning och godkända planerade order. Om mer material krävs någonstans skapas en planerad order för att täcka efterfrågan.

## <a name="scheduling-during-firming"></a>Planering vid bekräftelse

Planerade tillverkningsorder innehåller det flödes-ID som krävs för produktionsplanering. Det pågår dock planeringssupport under planeringskörningen för planerade order. Flödes-ID:t används för att tidsplanera planerade tillverkningsorder under bekräftad. Därför kan produktionstiden för planerade tillverkningsorder skilja sig från produktionstiden för relaterade tidsplanerade, bekräftade tillverkningsorder som genereras från dem, enligt beskrivningen här:

- **Planerad produktionsorder** – Produktionstiden baseras på den statiska produktionstiden från den frisläppta produkten.
- **Bekräftad tillverkningsorder** – Produktionstiden baseras på tidsplanering där flödesinformation och relaterade resursbegränsningar används.

Mer information om förväntad tillgänglighet för funktioner finns i [planeringsoptimeringsanalys](planning-optimization-fit-analysis.md).

Om du är beroende av produktionsfunktionerna som inte är tillgängliga för Planeringsoptimering ännu kan du fortsätta att använda den inbyggda huvudplaneringsmotorn. Inget undantag behövs.

## <a name="delays"></a>Fördröjningar

Om produktionstiden för det material som krävs är längre än perioden mellan dagens datum och materialbehovsdatumet försenas den planerade ordern för det begärda materialet och den relaterade tillverkningsordern. För planerade order beräknas förseningen (i dagar) baserat på produktionstiden från den frisläppta produkten. Fördröjningsinformationen sprids sedan genom alla nivåer i strukturlistestrukturen. Därför kan du följa inverkan från försenad råmaterial hela vägen till kundens försäljningsorder.

## <a name="modifying-planned-orders"></a>Ändra planerade order

När du ändrar information om en planerad order visas följande meddelande: "Observera att effekten från manuella ändringar på planerade order inte kommer att återspeglas i resten av planen förrän nästa huvudplaneringskörning."

Följ de här stegen om du vill ändra informationen i en planerad order och se effekten på de relaterade materialbehoven.

1. Uppdatera planerade ordern.
2. Godkänna planerade order.
3. Kör Huvudplanering.

När du kör huvudplanering bör du inte använda filter om planerade tillverkningsorder inkluderas. Mer information finns i avsnittet [Filter](#filters) senare i det här avsnittet.

> [!NOTE]
> Om leveransdatumet för den planerade ordern ändras till ett senare datum kan efterfrågan pegged mot en ny planerad order. Detta beteende inträffar när det nya leveransdatumet orsakar en fördröjning för den pegged efterfrågan, men enligt inställningarna för ledtid kan förseningen undviks.

## <a name="explosion-page"></a>Nedbrytningssida

På sidan **Nedbrytning** kan du analysera behovet av en viss tillverkningsorder eller planerad tillverkningsorder, tillhörande disponering och pegging-information. Informationen på sidan **Nedbrytning** uppdateras under huvudplaneringen. Du kan inte uppdatera informationen direkt från sidan **Nedbrytning**.

## <a name="filters"></a><a name="filters"></a>Filter

Vid planering av scenarier där produktion ingår bör du undvika filtrerade huvudplaneringskörningar. Om du vill vara säker på att Planeringsoptimering har den information som krävs för att beräkna rätt resultat, måste du inkludera alla produkter som har alla relationer till produkter i hela strukturlistestrukturen för den planerade ordern.

Underordnade artiklar som är beroende hittas automatiskt och inkluderas i huvudplaneringskörningar när den inbyggda huvudplaneringsmotorn används, men den här åtgärden utförs inte under Planeringsoptimering.

Om till exempel en enda blixt från strukturlistestrukturen för produkt A även används för att tillverka produkt B, måste alla produkter i strukturlistestrukturen för produkter A och B inkluderas i filtret. Eftersom det kan vara mycket komplicerat att säkerställa att alla produkter ingår i filtret rekommenderar vi att du undviker filtrerade huvudplaneringskörningar när tillverkningsorder används.
