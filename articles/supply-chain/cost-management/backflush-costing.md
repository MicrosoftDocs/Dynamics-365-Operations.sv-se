---
title: Kostnadskalkylering med automatisk lageravräkning
description: Det här avsnittet förklarar kostnadsredovisning med bakåtavräkning som används för Lean manufacturing.
author: cvocph
ms.date: 04/10/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeanCosting, LeanCostingTimeBucket
audience: Application User
ms.reviewer: kamaybac
ms.custom: 272063
ms.assetid: 62a2a7da-ff79-49bf-a6e8-29460ba5252f
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: ef8241424d3f512378849f820202b842b6c61ac208edd1d1e8e6a7efa06e9615
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6725852"
---
# <a name="backflush-costing"></a>Kostnadskalkylering med automatisk lageravräkning

[!include [banner](../includes/banner.md)]

Det här avsnittet förklarar kostnadsredovisning med bakåtavräkning som används för Lean manufacturing. 

Kostnadsredovisning för Lean manufacturing tillåter att produktionsflödet använder den metod för kostnadsackumulering som kallas kostnadsredovisning med bakåtavräkning. I kostnadsredovisning med bakåtavräkning ackumuleras de direktmaterial som förbrukas i produktionsflödets kostnadskonto för pågående arbete (PIA). Lagermodellgruppen för standardkostnader används. Produkterna som inlevereras från produktionsflödet dras från PIA till deras standardkostnad. Den största skillnaden mellan bakåtavräkning och standardkostnad är att för bakåtavräkning beräknas inte avvikelser per kanban eller färdig produkt. I stället beräknas avvikelser per produktionsflöde under en period. Denna metod innebär ett riktigt resurssnålt koncept för rapportering av materialförbrukning. Dedikerade plockade kvantiteter rapporteras inte till en kanban eller tillverkningsorder. I stället mellanlagras hela batchar eller materialhanteringsenheter till produktionsflödet. När batchar eller materialhanteringsenheter registrerats som tomma, förklaras de som förbrukade. Avancerad förbrukning kan användas, beroende på [konfigurationen av produktionsflödet](../production-control/lean-manufacturing-modeling-lean-organization.md). Innan du kan använda avancerad förbrukning, måste organisationer tillåta att de låter material försvinna i PIA för produktionsflödet. Den periodiska bakåtavräkningen bestämmer det effektiva värdet för PIA i slutet av perioden. Beslutet baseras på kanban-materialhanteringsenheten och kanban-jobbstatus. Avvikelser mellan effektiva värden och faktiska PIA-värden per kostnadsgrupp och artikel bokförs och visas som avvikelser.

## <a name="configuring-backflush-costing"></a>Konfigurera kostnadsredovisning med bakåtavräkning
Om du vill aktivera kostnadsredovisning måste du slutföra stegen nedan:

-   **Ställa in PIA-konton för produktionsgruppen och produktionsflödet.** PIA-konton för produktionsflödet anges i produktionsgruppen. Bakåtavräkning för produktionsflödet beräknas som skillnaden i värdet för PIA-avvikelser före och efter bakåtavräkning körs för varje produktionsflöde. Därför rekommenderar vi att du skapar ett PIA-konto för varje produktionsflöde.
-   **Tilldela en kostnadskategori till en resursgrupp.** Du måste tilldela en kostnadskategori till arbetsgruppens körtidskategori. Om du vill bestämma avvikelser efter aktivitet bör du skapa en kostnadskategori för varje arbetsgrupp. Kostnadskategorier för inställning och kvantitet beaktas inte vid kostnadsredovisning för lean manufacturing. PIA-konton per resursgrupp ignoreras i kostnadsredovisning med bakåtavräkning. För legotillverkningsaktiviteter krävs ingen kostnadskategori. Den kostnadsgrupp som tilldelas den aktiva tjänsten används i stället.
-   **Tilldela kostnadsgrupper.** Om du vill aktivera segmentering av kostnadsbidrag i ett produktionsflöde måste du tilldela kostnadsgrupper per kostnadsgruppstyp:
    -   **Kostnadsgrupp för direktmaterial** - direkt material kräver en kostnadsgrupp som identifierar materialkategorin för kostnadsredovisning. Denna kostnadsgrupp tillåter en aggregerad vy över kostnader, PIA och avvikelser genom direkt material.
    -   **Kostnadsgrupp för direkttillverkning** - Kostnadsgruppen för direkttillverkning samlar in bidraget för direktkostnad för verksamhetsresurser till produktionsflödet. Denna kostnadsgrupp tillåter en aggregerad vy över kostnader, PIA och avvikelser genom direkttillverkningskostnad.
    -   **Indirekt kostnadsgrupp** - den indirekta kostnadsgruppen krävs för att beräkna bidraget för indirekta kostnader för produktionsflödet. Denna kostnadsgrupp tillåter en aggregerad vy över kostnader, PIA och avvikelser genom indirekt kostnad.
    -   **Kostnadsgrupp för direktutkontraktering** - kostnadsgruppen för direktutkontraktering tillåter en aggregerad vy över tilldelade kostnader och PIA och avgör kostnadsavvikelser för legotillverkningstjänster.
    -   **Kostnadsgrupp för en färdig produkt** - färdiga produkter kräver en kostnadsgrupp som identifierar produktkategori för kostnadsredovisning. Denna kostnadsgrupp tillåter en aggregerad vy över kostnader, PIA och avvikelser genom produktkategori. Standardkostnaden för produkter beräknas med hjälp av kostnadsberäkningen som baseras på en strukturlista (BOM) och antingen produktionsflödet och kanbanregler för produktion, eller flödet.

### <a name="costing-sheet"></a>Kostnadsredovisning

Företagets kostnadsredovisningen och kostnadsstrukturmodeller skapas med kostnadsgrupper för att klassificera kostnaden. Kostnadsredovisningen har olika formulär. Den visar kostnadsinformation enligt strukturen som visas i den. I kostnadsredovisningen definierar du även formeln som används för beräkning av indirekta kostnader. Beräkningsformeln kan baseras på kvantitet, vikt, volym eller värde.

-   **Definiera en kostnadsredovisningsversion.** I kostnadsredovisningsversion definierar företaget hur kostnaden bör underhållas. En kostnadsversion kan innehålla en uppsättning standardkostnadsposter eller en uppsättning planerade kostnadsposter beroende på kostnadstypen som tilldelas kostnadsversionen. Den kostnadsversion som används för kostnadsredovisning för Lean manufacturing måste baseras på standardkostnader.
-   **Tilldela en lagermodellgrupp till frisläppt produkt.** Alla produkter som hör till produktionsflödet måste ha tilldelats en lagermodellgrupp som använder lagermodellgruppen **standardkostnad**. Standardkostnad underhålls per site och aktiveringsdatum. För produktmallar kan lagermodellgruppen väljas om kostnaden underhålls per variant eller produktmall.
-   **Legotillverkningstjänster är per definition icke-inventerade tjänster.** Legotillverkningsaktiviteter har ingen lagermodellgrupp. För att bokföra en kostnad till en legotillverkningsaktivitet korrekt måste du kontrollera att serviceaktiviteten tillhör en lagermodellgrupp där lagerprincipen är inställd på **Produkt i lager = falskt**.

För slutprodukter kräver kostnadsberäkning som baseras på produktionsflödet att standardkostnaden behålls för tjänster som rör legotillverkningsaktiviteter. Den kostnadsgrupp som tilldelas tjänster används för att bestämma kostnadsavvikelser för den legotillverkningsaktiviteten.

## <a name="cost-calculation-for-lean-manufacturing"></a>Kostnadsberäkning för Lean manufacturing
För produkter som tillhandahålls av ett produktionsflöde ska strukturlisteberäkningen baseras på ett produktionsflöde eller en flödesversion. Strukturlisteberäkningen beräknar kostnaden för en produkt och den relaterade fördelningen till resurser och material som krävs för att skapa produkten. Avdrag från PIA-kontot för produktionsflödet görs med hjälp av fördelningen av en produkt per artikel och kostnadsgrupp.

### <a name="calculation-that-is-based-on-the-production-flow"></a>Beräkning som baseras på produktionsflöde.

Lean manufacturing för Dynamics 365 Supply Chain Management är oberoende av flöden. Kostnadsberäkningen för produkter som tillhandahålls från ett produktionsflöde kan baseras på själva produktionsflödet. Innan beräkningen kan göras måste en kanban-regel skapas som levererar produkten utanför produktionsflödet. Om en produkt kan läsas in från flera produktionsflöden på samma plats på beräkningsdatumet, kan du välja produktionsflödet för strukturlisteberäkningen. På sidan **Standardproduktionsflöde** kan du konfigurera ett standardproduktionsflöde för varje artikel. Om det inte finns flera kanban-regler för samma produkt i samma produktionsflöde som är aktivt på beräkningsdatumet markerar beräkningen den första kanban-regeln som är aktiv för beräkningen.

### <a name="calculation-that-is-based-on-the-route"></a>Beräkningen baseras på flödet.

Beräkning som baseras på ett flöde är en giltig beräkning som baseras på ett produktionsflöde. Däremot en beräkning som baseras på ett flöde använder inte funktionerna kostnadsredovisning för Lean manufacturing. Flödet bör använda resursbehov för resursgrupper. För att undvika systematiska avvikelser bör det också använda samma arbetsgrupper eller åtminstone samma kostnadskategorier. Återigen bör du undvika kostnadskategorier för inställning och kvantitet. De hjälper inte till att beräkna kostnaden i en mer detaljerad uppdelning än för bakåtavräkning av kostnad i Lean manufacturing. För att avgöra vilket alternativ (produktionsflöde eller flöde) som bör användas för att beräkna kostnaden bör kostnadsuppdelningens resultat beaktas. Versionen som kommer närmast utgångspunkten och ger generellt färre avvikelser är ett bra alternativ. I en Lean manufacturing-miljö där en produkt levereras av ett enda produktionsflöde och en enda kanban-regel, är förmodligen beräkningen som baseras på produktionsflödet mer exakt. För en produkt som levereras av en Lean manufacturing och produktionsorder på samma plats och kan ha flera produktionsflöden eller flera kanban-regler i samma flöde kan vara mer exakt om den är baserad på en flödesversion som skapats speciellt för kostnadsberäkningen, inte för produktionen. Beräkningen av produktionsflödet måste användas för att beräkna produkter som innefattar legotillverkning. Kostnadsmodeller för legotillverkning via tillverkningsorder och underleverantörer i Lean manufacturing använder två olika sätt. Lean manufacturing introducerar en ny typ av kostnadsgrupp, **direktutkontraktering**, för att beräkna legotillverkningstjänster.

## <a name="material-consumption"></a>Materialförbrukning
När material förbrukas från lagret till PIA läggs kostnaden för material till i PIA enligt dess faktiska standardkostnad för en kostnadsgrupp. Den här åtgärden uppstår under följande förutsättningar:

-   Kanban-utleveranser bokförs för kanban-plockrader som uppdaterar lagret.
-   Överföringsjobb slutförs som uppdaterar lagret vid plockning men inte för inleverans (överföring av material från lager till PIA).

## <a name="receiving-products-from-the-production-flow"></a>Mottagning av produkter från produktionsflödet
Produkterna inlevereras från produktionsflödet under följande förhållanden:

-   Processjobb slutförs som har **uppdatering av lager vid inleverans** inställt på **Ja**.
-   Överföringsjobb är klara att uppdatera lagret vid inleverans men har **uppdatering av lager vid plockning** inställt på **nej** (Överför från pågående arbete till lagret). Det här alternativet låter dig inleverera produkter utanför ett produktionsflöde oberoende av strukturliste- och flödeskonfigurationen. Bara följ de fysiska flödena. Detta alternativ är särskilt lämpligt för att ta emot biprodukter, samprodukter eller kassation från produktionsflödet och för att korrigera kostnadssaldo för produktionsflödet i PIA i enlighet med detta.

Produkterna som inlevereras från produktionsflödet dras från PIA.

## <a name="products-in-wip"></a>Produkter i PIA 
PIA-modellen för Lean manufacturing låter dig använda den enhetsstatus för kanban-hantering för att hantera material, halvfabrikat och färdiga produkter som ingår i PIA.

-   **Tilldelad** - kanban kan ha förbrukat materialet som redovisas i PIA.
-   **Mottagna** - om kanban refererar till senaste aktiviteten där **uppdatering av lager vid inleverans** anges till **nej**, representerar det en fullständig materialhanteringsenhet av en produkt eller en halvfärdig produkt som inte är registrerad till lagret.

Observera att material från PIA inte syns i lagerbehållningsvyn. Men den syns i kanban-kvantitetsvyn.

## <a name="consuming-products-in-wip"></a>Förbrukade produkter i PIA
Produkter i PIA förbrukas när motsvarande kanban-materialhanteringsenheter är tomma. En tom kanban-signal ger inte en aktiv kostnadsredovisningstransaktionen men börjar gälla efter att nästa kostnadsredovisning med bakåtavräkning körs. Tomma kanban-materialhanteringsenheter redovisas inte längre som behållna därför beräknas de som förbrukade inom perioden

### <a name="automatic-empty-registration"></a>Automatisk registrering av tömning

Schemalagda eller händelse-kanban som kan ställas in för automatisk registrering av tömning i kanban-regeln:

-   **När materialhanteringsenheter inlevereras** - som standard för tidsplanerade kanbans deklareras materialet som förbrukatnär det sista jobbet för kanban har slutförts. För kanban med fast kvantitet rekommenderas detta alternativ endast för single-bin kanban eftersom det returnerar kortet till efterfrågekällan när en kanban erhålls vid den slutliga användningen.
-   **När källbehovet är registrerat** - det här alternativet är bara tillgängligt för händelse-kanban och är standardalternativet för dessa. Detta alternativ är användbart för att hålla PIA ren, eftersom kanbans för komponenter i PIA töms automatiskt, och därför förbrukas från PIA, när den överordnade kanban förbereds i anslutning till Pågående arbete.

Sammanfattningsvis  kan kanban-hantering av enheter kan tilldelas (= pågår) tas emot (= komplett), eller tömts. Det finns ingen del tömma. För att aktivera korrekt registrering av förbrukning är det viktigt att du begränsar produktkvantiteter för en kanbans så att de är mindre än förbrukning per period. Produkter som flyttas till verkstaden i stora grupper som täcker dagar eller veckor av efterfrågan ska inte förbrukas till PIA. I stället bör produkterna finnas i lager.

## <a name="backflush-costing"></a>Kostnadskalkylering med automatisk lageravräkning
Kör ostnadsredovisning med bakåtavräkning till periodiskt värdet för PIA och producera en slutstatus som beräknar varians av material, arbete och omkostnader. Beräknade avvikelser bokförs på avvikelsekontona. I kostnadsredovisning med bakåtavräkning används alla produktionsflöden för den juridiska personen i samma batchkörning. Vid kostnadsredovisning med bakåtavräkning i en batch kan bearbetning vara flertrådad i produktionsmiljön. Bakåtavräkningsperioden definieras av ett slutdatum. Du kan inte bokföra nya transaktioner till ett datum när kostnadsredovisning med bakåtavräkning har körts. Kör aldrig kostnadsredovisning med bakåtavräkning för det aktuella datumet innan dagen är slut. Utför följande steg för kostnadsredovisning med bakåtavräkning.

1.  Bestäm de outnyttjade kvantiteterna i produktionsflödet vid periodens slutdatum. När kostnadsredovisning med bakåtavräkning körs kan du visa de outnyttjade kvantiteterna på datumet för kostnadsredovisningen körs i dialogrutan **Outnyttjade kvantiteter**.
2.  Beräkna produktionsflöde nettorealiserade förbrukning under perioden.
3.  Avmarkera PIA från realiserade resursförbrukning och produkter.
4.  Beräkna standardkostnader produktionsavvikelser för perioden. **För förbrukade komponenter för perioden:**
    -   Uppdatera de realiserade nettokvantiteter av material som har förbrukats under produktionsflödet. Systemet bearbetar i ordningen först in, först ut (FIFO) på enskilda lagertransaktioner för att uppdatera de fysiskt uppdaterade transaktionerna för produktionsflödet, tills nettorealiserade kvantiteterna för perioden har uppnåtts.
    -   Ekonomiskt dela upp transaktioner om du vill mappa de exakta förbrukade antalen.
    -   Outnyttjade kvantiteter i produktionsflödet PIA finns kvar i fysiskt uppdaterad status.

    **För att slutföra produktionskvantiteter i perioden:**
    -   Uppdatera ekonomiskt lagertransaktionerna för slutförda kvantiteterna för perioden.

    **För konverteringskostnad:**
    -   Använd konverteringskostnadstransaktioner (flödestransaktioner) som registrerades för perioden uppdaterats ekonomiskt.
    -   Alla direkta produktionskostnaden uppdateras ekonomiskt. Kanban-processjobb som utförs under perioden samlas.
    -   Alla indirekta kostnader beräknas för det förbrukade materialet inom perioden och dras av från PIA. Återstående indirekta kostnaden bokförs som en avvikelse.

5.  Beräkna standardkostnader produktionsavvikelser. Avvikelsen beräknas per kostnadsgrupp.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]