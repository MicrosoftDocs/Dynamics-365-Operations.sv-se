---
title: Produktionsplanering
description: Det här ämnet beskriver planering för produktion och förklarar hur du ändrar planerade tillverkningsorder genom att använda Planeringsoptimering.
author: t-benebo
ms.date: 06/01/2021
ms.topic: article
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-12-15
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 8f23cb62512dfd718fe199867a4b21aaa0eca3fd
ms.sourcegitcommit: ad1afc6893a8dc32d1363395666b0fe1d50e983a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2022
ms.locfileid: "8469070"
---
# <a name="production-planning"></a>Produktionsplanering

[!include [banner](../../includes/banner.md)]

Planeringsoptimering stöder flera produktionsscenarier. Om du migrerar från den befintliga, inbyggda huvudplaneringsmotorn är det viktigt att du känner till vissa ändrade beteenden.

Följande video ger en kort introduktion till några av de begrepp som diskuteras i detta ämne: [Dynamics 365 Supply Chain Management: Förbättringar av planeringsoptimering](https://youtu.be/u1pcmZuZBTw).

## <a name="turn-on-this-feature-for-your-system"></a>Aktivera funktionen i systemet

Om ditt system inte redan innehåller de funktioner som beskrivs i det här avsnittet, gå till [funktionshantering](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) och aktivera funktionen *Planerade produktionsorder för planeringsoptimering*.

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

Om du vill vara säker på att Planeringsoptimeringen har den information som den behöver för att beräkna rätt resultat, måste du inkludera alla produkter som har någon som helst relation till produkter i hela strukturlistestrukturen för den planerade ordern. Vid planering av scenarier där produktion ingår rekommenderar vi därför att du undviker filtrerade huvudplaneringskörningar.

Även om underordnade artiklar hittas automatiskt och inkluderas i huvudplaneringskörningar när den inbyggda huvudplaneringsmotorn används, utför i nuläget Planeringsoptimeringen inte denna åtgärd.

Om till exempel en enda blixt från strukturlistestrukturen för produkt A även används för att tillverka produkt B, måste alla produkter i strukturlistestrukturen för produkter A och B inkluderas i filtret. Eftersom det kan vara komplicerat att säkerställa att alla produkter ingår i filtret, rekommenderar vi att du undviker filtrerade huvudplaneringskörningar när produktionsorder används. I annat fall kommer huvudplaneringen att ge oönskade resultat.

### <a name="reasons-to-avoid-filtered-master-planning-runs"></a>Orsaker att undvika filtrerade huvudplaneringskörningar

När du kör filtrerad huvudplanering för en produkt detekterar Planeringsoptimeringen (till skillnad från den inbyggda huvudplaneringsmotorn) inte alla delprodukter och råmaterial i strukturlistestrukturen för den produkten och tar därför inte med dem i huvudplaneringskörningen. Även om Planeringsoptimering identifierar den första nivån i strukturlistestrukturen för produkten läses inga produktinställningar (till exempel standardordertyp eller artikeldisponering) in från databasen.

I Planeringsoptimeringen läses data in för körningen i förväg och filtret används. Detta innebär att om en delproduktion eller råmaterial som ingår i en viss produkt inte ingår i filtret, kommer inte information att registreras under körningen. Om delprodukten eller råmaterialet dessutom ingår i en annan produkt kommer en filtrerad körning som endast innehåller den ursprungliga produkten och dess komponenter ta bort befintlig planerad efterfrågan som skapats för den andra produkten.

Denna logik kan leda till att filtrerade huvudplaneringskörningar leder till oväntade resultat. Följande avsnitt innehåller exempel som illustrerar de oväntade resultat som kan inträffa.

### <a name="example-1"></a>Exempel 1

Färdig vara *FG* består av följande komponenter:

- Råmaterial *R*
- Delprodukt *S1*, som består av delprodukt *S2*

Det finns lagerbehållning för råmaterial *R*, medan delprodukt *S1* inte finns i lagret.

När du gör en filtrerad huvudplaneringskörning för färdig vara *FG* får du en planerad produktionsorder för färdig vara *FG*, en planerad inköpsorder för råmaterial *R*, samt en planerade inköpsorder för underprodukt *S1*. Detta är ett oönskat resultat eftersom Planeringsoptimeringen har ignorerat att befintliga lager råmaterial *R* och delprodukt *S1* skulle framställas med hjälp av *S2* snarare än beställas direkt. Detta händer eftersom planeringsoptimering bara har listat komponenter för det färdiga varan *FG* utan relaterad information, till exempel den befintliga tillförseln av komponenter eller dessas standardorderinställningar.

### <a name="example-2"></a>Exempel 2

Baserat på det tidigare exemplet använder en extra färdig vara, *FG2*, också delproduktion *S1*. En planerad order finns för färdig vara *FG2*, och planerat behov finns för samtliga dess komponenter, inklusive *S1*.

Du bestämmer dig för att kringgå oönskade resultat av den filtrerade huvudplaneringskörningen från det föregående exemplet genom att lägga till samtliga delprodukter och råmaterial från strukturlistan för färdig vara *FG* i filtret och sedan köra hela omgenereringen.

När du kör hela omgenereringen raderar systemet alla befintliga resultat för alla inkluderade produkter och återskapar sedan resultat baserat på de nya beräkningarna. Detta innebär att befintlig planerad efterfrågan för *S1* tas bort och sedan återskapas i beaktande av endast krav för färdig vara *FG*, medan kraven för färdig vara *FG2* ignoreras. Detta sker eftersom körd Planeringsoptimering inte omfattar den planerade efterfrågan för andra planerade produktionsorder &mdash; endast den planerade efterfrågan som genererats under körning används.

> [!NOTE]
> Om den befintliga planerade ordern för färdig vara *FG2* har statusen *Godkänd* inkluderas den godkända planerade efterfrågan även om den överordnade produkten inte läggs till i filtret.

Om du inte lägger till alla komponenter för den färdiga varan *FG*, färdig vara *FG2* och alla andra produkter som dessa komponenter ingår i (tillsammans med dessas komponenter), kommer den filtrerade huvudplaneringskörningen därför att generera oönskade resultat.

Eftersom det kan vara komplicerat att säkerställa att alla produkter ingår i filtret, rekommenderar vi att du undviker filtrerade huvudplaneringskörningar när produktionsorder används.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
