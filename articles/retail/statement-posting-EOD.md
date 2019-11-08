---
title: Förbättringar av funktionen för bokföring av utdrag
description: Det här avsnittet beskriver de förbättringar som har gjorts till funktionen för bokföring av utdrag.
author: josaw1
manager: AnnBe
ms.date: 05/14/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: Global
ms.search.industry: retail
ms.author: anpurush
ms.search.validFrom: 2018-04-30
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 1e3fc0e8cb5c9a6cc7729dfbddd5d918a1d6bdb5
ms.sourcegitcommit: 0099fb24f5f40ff442020b488ef4171836c35c48
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/23/2019
ms.locfileid: "2653381"
---
# <a name="improvements-to-statement-posting-functionality"></a>Förbättringar av funktionen för bokföring av utdrag

[!include [banner](includes/banner.md)]

Det här avsnittet beskriver den första uppsättningen förbättringar som har gjorts till funktionen för bokföring av utdrag. Dessa förbättringar är tillgängliga i Microsoft Dynamics 365 for Finance and Operations 7.3.2.

## <a name="activation"></a>Aktivering

Som standard ställs under distributionen av Finance and Operations 7.3.2 programmet in äldre funktionen för bokföring av utdrag. Om du vill aktivera funktionen för bokföring av utdrag måste du aktivera konfigurationsnyckeln för den.

- Gå till **Systemadministration**\>**Inställningar**\>**Licenskonfigurationen** och sedan under noden **Butik**, avmarkera kryssrutan **Butiksutdrag (äldre)** och markera kryssrutan **Butiksutdrag**.

När den nya **Butiksutdrag** konfigurationsnyckeln är aktiverad och ett nytt menyalternativ som heter **Butiksutdrag** är tillgänglig. Det här menyobjektet låter dig manuellt skapa, beräkna och bokföra utdrag. Alla utdrag som orsakar ett felmeddelande när batchbokföringsprocessen används blir också tillgängliga via det här menyalternativet. (När den nya **Butiksutdrag (äldre)** konfigurationsnyckeln är aktiverad och ett nytt menyalternativ som heter **Öppna utdrag**.)

Retail omfattar följande valideringar som hör till dessa konfigurationsnycklar

- Båda konfigurationsnycklar kan inte aktiveras samtidigt.
- Samma konfigurationsnycklarna måste användas för alla åtgärder som utförs på ett visst utdrag under dess livscykel (skapa, beräkna, radera, bokföra och så vidare). Exempelvis kan du inte skapa och beräkna ett utdrag när konfigurationsnyckeln **Butiksutdrag (äldre)** aktiveras och sedan försöker bokföra samma uttryck när konfigurationsnyckeln **Butiksutdrag**.

> [!NOTE]
> Vi rekommenderar att du använder konfigurationsnyckeln **Butiksutdrag** för förbättrad funktion för bokföring av utdrag om du inte måste använda konfigurationsnyckeln **Butiksutdrag (äldre)** istället. Microsoft fortsätter att investera i nya och förbättrade funktioner för bokföring av utdrag och det är viktigt att du växlar till det så snart som möjligt för att kunna utnyttja denna. Funktionen för bokföring av äldre utdrag kommer att tas bort från och med version 8.0.

## <a name="setup"></a>Konfigurera

Som del av förbättringarna av funktionerna för bokföring av utdrag har tre nya parametrar införts på snabbfliken **utdrag** på fliken **bokföring** på sidan **butiksparametrar**:

- **Inaktivera rensning av utdrag** – det här alternativet gäller endast för äldre funktioner för bokföring av utdrag. Vi rekommenderar att du ställer in detta alternativ till **Nej** att förhindra att användare rensar rapporter som har statusen delvis bokförda. Om utdrag som är delvis bokförda rensas kommer data att skadas. Du bör endast ange detta alternativ till **Ja** i undantagsfall.
- **Reservera lager vid beräkning** – Vi rekommenderar att du använder batchjobbet **Bokför lager** för reservation av lager och du ställer in detta alternativ till **Nej**. När det här alternativet är inställt på **Nej**, kommer funktionen för förbättrad bokföring av utdrag inte att försöka skapa lagerreservationstransaktioner vid tidpunkten för beräkningen (om transaktionerna inte redan har skapats via batchjobbet **Bokför lager**). Funktionen skapar i stället lagerreservationstransaktioner endast vid bokföringstidpunkten. Den här implementeringen var ett designval och är baserat på att tidsfönstret mellan beräkningsprocessen och bokföringsprocessen vanligtvis är litet. Om du vill reservera lager vid tidpunkten för beräkningen kan du ställa in detta alternativ till **Ja**.

    Den äldre funktionen för bokföring av utdrag reserverar alltid lager under beräkningsprocessen för utdrag (om du inte redan har gjort reservationen via batchjobbet **Bokför lager**), oavsett inställningen av detta alternativ.

- **Inaktivera att inventering krävs** – när det här alternativet ställs in på **Ja**, fortsätter bokföringsprocessen för ett utdrag, även om skillnaden mellan det beräknade beloppet och transaktionsbeloppet för utdraget är utanför det tröskelvärde som är definieras på snabbfliken **Utdrag** för butiker.

Dessutom har följande parametrar införts på snabbfliken **gruppbearbetning** på fliken **bokföring** på sidan för **butiksparametrar**: 

- **Maximalt antal parallella utdragsbokföringar** – det här fältet definierar antalet batchjobb som ska användas för att bokföra flera utdrag. 
- **Max. tråd för orderbearbetning per utdrag** - det här fältet representerar det högsta antalet trådar som används av batch-jobbet utdragsbokföring för att skapa och fakturera försäljningsorder för ett enda utdrag. Det totala antalet trådar som kommer att användas av utdragsbokföringsprocessen beräknas utifrån värdet i den här parametern multiplicerat med värdet i parametern **Maximalt antal parallella utdragsbokföringar**. Om du anger värdet för den här parametern för högt kan prestandan i bokföringsprocessen för utdraget påverkas negativt.
- **Max. transaktionsrader inkluderade i sammansättning** - det här fältet definierar antalet transaktionsrader som ska inkluderas i en samlad transaktion innan en ny skapas. Aggregerade transaktioner skapas utifrån olika sammansättningskriterier, t.ex. kund, affärsdatum eller ekonomiska dimensioner. Det är viktigt att notera att raderna från en enda butikstransaktion inte delas mellan olika sammansättningstransaktioner. Detta innebär att det finns en risk för att antalet rader i en sammansättningstransaktion är något högre eller lägre baserat på faktorer som antal specifika produkter.
- **Maximalt antal trådar för validering av butikstransaktioner** – det här fältet definierar antalet trådar som ska användas för att validera butikstransaktioner. Validering av butikstransaktioner är ett obligatoriskt steg som måste inträffa innan transaktionerna kan hämtas till kontoutdrag. Du måste definiera en **Presentkortsprodukt** på snabbfliken **presentkort** på fliken **bokföring** på sidan **butiksparametrar** Detta måste definieras även om inga presentkort används i organisationen.

> [!NOTE]
> Alla inställningar och parametrar som relateras till bokföring av utdrag och som definieras i butiker och på sidan **Butiksparametrar**, gäller för den förbättrade funktionen för bokföring av utdrag.

## <a name="processing"></a>Bearbetning

Utdrag kan beräknas och bokföras i en batch med hjälp av menyalternativeet **Beräkna utdrag i batch** och **Bokför utdrag i batch**. Alternativt kan utdrag beräknas och bokföras manuellt med hjälp av menyalternativet **Butiksutdrag** som innehåller den förbättrade funktionen för bokföring av utdrag.

Processen och stegen för beräkning och bokföring av utdrag i en batch är desamma som i den äldre funktionen för bokföring av utdrag. Dock har viktiga förbättringar gjorts i den huvudsakliga interna behandlingen av utdragen. Dessa förbättringar gör processen mer flexibel och ger bättre insyn i tillstånden och felinformation. Därför kan användarna adressera orsaken till fel och sedan fortsätta bokföringssprocessen utan att orsaka datakorruption och utan att det krävs datakorrigeringar.

I följande avsnitt beskrivs några viktiga förbättringar för utdragsbokföring som visas i användargränssnittet för butiksutdrag och bokförda utdrag.

### <a name="status-details"></a>Statusinformation

En ny tillståndsmodell har introducerats i metoden för bokföring av utdrag genom beräknings- och bokföringsprocesser.

I följande tabell beskrivs de olika tillstånden och deras ordning under beräkningsprocessen.

| Tillstånd order | Stat      | beskrivning |
|-------------|------------|-------------|
| 1           | Startat    | Utdraget har skapats och är redo att beräknas. |
| 2           | Markerade     | De transaktioner som finns inom räckvidd för utdraget identifieras baserat på utdragsparametrarna och de är märkta med utdrags-ID. |
| 3           | Beräknat | Utdragsraderna beräknas och visas. |

I följande tabell beskrivs de olika tillstånden och deras ordning under bokföringsprocessen.

| Tillstånd order | Stat                   | beskrivning |
|-------------|-------------------------|-------------|
| 1           | Kontrollerad                 | Flera valideringar görs som hör till parametrar (till exempel dispositionsavgift) och till utdraget och utdragsraderna (till exempel skillnaden mellan det beräknade beloppet och transaktionsbeloppet). |
| 2           | Sammansatt              | Försäljningstransaktioner för namngivna och icke namngivna kunder sammanställs baserat på konfigurationen. Varje aggregerad transaktion konverteras slutligen till en försäljningsorder. |
| 3           | Kundorder skapas  | Utifrån den sammanlagda transaktionen skapas försäljningsorder i systemet. |
| 4           | Fakturerad kundorder | Försäljningsorder faktureras |
| 5           | Bokförda rabatter        | Tidsbegränsade rabattjournaler bokförs utifrån konfigurationen. |
| 6           | Bokförd intäkt/utgift   | Intäkts-/utgiftstransaktioner bokförs som verifikationer. |
| 7           | Länkade verifikationer         | Betalningsjournaler skapas och kopplas till motsvarande faktura. |
| 8           | Bokförda betalningar         | Betalningsjournaler bokförs. |
| 9           | Bokförda presentkort       | Presentkortstransaktioner bokförs som verifikationer. |
| 10          | Publicerat                  | Utdraget markeras som bokfört. |

Alla tillstånden i föregående tabell är av oberoende karaktär och hierarkiska beroenden skapas mellan tillstånden. Detta beroende flödas uppifrån och ned. Om systemet stöter på ett fel när det bearbetar ett tillstånd, återställs status för utdraget till föregående tillstånd. Alla efterföljande återförsök i processen fortsätter från det tillstånd som har misslyckats och fortsätter att gå vidare. Den här metoden har följande fördelar:

- Användaren har fullständig överblick över det tillstånd där felet uppstod.
- Datafel undviks. Exempelvis i funktionen för bokföring av äldre utdrag fanns exempel där vissa försäljningsorder fakturerades, men andra utelämnades. Det fanns även vissa exempel där en del betalningsjournaler inte hade en motsvarande faktura att betalas, eftersom bokföringen av fakturan hade ett fel.
- Visar aktuell status för ett utdrag med knappen **statusinformation** i gruppen **Information om körning** för utdraget. Informationssidan om tillstånd har tre avsnitt:

    - Det första avsnittet visat aktuellt tillstånd för kontoutdrag, tillsammans med felkoden och ett felmeddelande om ett fel uppstod.
    - Den andra delen visar de olika lägena i beräkningen. Visuella hjälpmedel kan ange tillstånd som har utförts, som inte kunde köras på grund av ett fel, och tillstånd som ännu inte har körts.
    - Det tredje avsnittet visar de olika tillstånden i bokföringen. Visuella hjälpmedel kan ange tillstånd som har utförts, som inte kunde köras på grund av ett fel, och tillstånd som ännu inte har körts.

Dessutom visas rubriken i andra och tredje avsnitten övergripande tillstånd för den aktuella processen.

### <a name="event-logs"></a>Händelseloggar

Ett utdrag genomgår olika operationer (till exempel skapa, beräkna, radera och bokföra) och flera instanser av samma operation kan anropas under utdragets livscykel. Exempelvis när ett utdrag skapas och beräknas kan användaren avmarkera utdraget och beräkna det igen. Knappen **händelseloggar** i gruppen **Information om körning** för utdraget ger en fullständig redovisningsspårning av olika åtgärder som kallas på utdraget sats, tillsammans med information om när dessa åtgärder kallades.

### <a name="aggregated-transactions"></a>Sammansatta transaktioner

Under bokföringsprocessen sammanställs försäljningstransaktionerna baserat på konfigurationen. Dessa sammanlagda transaktioner lagras i systemet och används till att skapa försäljningsorder. Varje sammanlagd transaktion skapar en motsvarande försäljningsorder i systemet. Du kan visa sammanlagd transaktion med knappen **sammanlagda transaktioner** i gruppen **Information om körning** för utdraget.

Fliken **detaljer för försäljningsorder** för en sammanlagd transaktionen visar följande information:

- **Post-ID** – ID för sammanlagda transaktionen.
- **Utdragsnummer** – utdraget som den sammanlagda transaktionen tillhör.
- **Datum** – Datumet när den sammanlagda transaktionen skapades.
- **Försäljnings-ID** – när en försäljningsorder skapas från den sammanlagda transaktionen , försäljningsorder-ID. Om fältet är tomt kommer har motsvarande försäljningsorder inte ha skapats.
- **Antal sammanlagda rader** – det totala antalet rader för försäljningsordern och sammanlagda transaktionen.
- **Status** – sista status för sammanlagda transaktionen.
- **Faktura-ID** – när försäljningsordern för sammanlagda transaktionen faktureras, försäljningsfaktura ID. Om fältet är tomt kommer har fakturan för försäljningsorder inte bokförts.

Fliken **transaktionsdetaljer** på en sammanlagd transaktion visar alla butikstransaktioner som tagits emot i sammanlagda transaktionen. De sammanlagda raderna på den sammanlagda transaktionen visar alla sammanlagda posterna från butikstransaktioner. De sammanlagda raderna visar också information om artikel, variant, kvantitet, pris, nettobelopp, enhet och lagerställe. I princip motsvarar varje sammanlagd rad en försäljningsorderrad.

Från sidan **sammanlagda transaktioner** kan du hämta XML för en viss sammanlagd transaktion med knappen **exportera försäljningsorder-XLM**. Du kan använda XML för att felsöka problem som rör upprättande av försäljningsorder och bokföring. Bara hämta XML, överför den till en testmiljö och felsök problem i testmiljön. Funktionen för att hämta XML för sammanlagda transaktioner är inte tillgänglig för utdrag som har bokförts.

Vyn sammanlagd transaktion ger följande fördelar:

- Användaren har insyn i sammanlagda transaktioner som misslyckades vid upprättande av försäljningsorder och försäljningsorder som misslyckades vid fakturering.
- Användaren har insyn i hur transaktioner slås samman.
- Användaren har en fullständig redovisningsspårning från butikstransaktioner, försäljningsorder till försäljningsfakturor. Den här redovisningsspårningen är inte tillgänglig i funktionen för bokföring av äldre utdrag.
- Sammanlagd XML-filen gör det enklare att identifiera problem vid upprättande av försäljningsorder och fakturering.

### <a name="journal-vouchers"></a>Bokföringsorder

Knappen **journalverifikationer** i gruppen **Information om körning** för utdraget visar alla de olika verifikationstransaktioner som skapas för ett utdrag och som rör rabatter, intäkter/kostnader-konton, presentkort kort, osv.

Programmet visar för närvarande endast data för bokförda utdrag.

### <a name="payment-journals"></a>Betalningsjournaler

Knappen **betalningsjournaler** i gruppen **Information om körning** för utdraget visar alla de olika betalningsjournaler som har skapats för ett utdrag.

Programmet visar för närvarande endast data för bokförda utdrag.

## <a name="other-improvements"></a>Andra förbättringar

Andra interna förbättringar som användarna kan se att de har gjorts till funktionen för bokföring av utdrag. Nedan följer några exempel:

- Sammansättning tar inte hänsyn till personal, terminal och skiftenheter. Eftersom det finns färre sammanslagningsparametrar måste färre försäljningsorderrader bearbetas.
- Förekomst av dödläge i butikstransaktionstabeller minskas genom att införa ytterligare tilläggstabeller och genom att göra detta sätta in åtgärder istället för att uppdatera åtgärder i detaljhandelstransaktionstabellerna.
- Antal batchuppgifter som kör är parameterstyrda och begränsade. Detta nummer kan därför vara anpassat till en kunds miljö. Ett obegränsat antal batchuppgifter skapades i funktionen för bokföring av äldre utdrag samtidigt. Resultatet var svårhanterligt belastning, overhead och flaskhalsar i batchservern.
- Rapporterna köas effektivt för bearbetning genom att prioritera utdrag som har det maximala antalet transaktioner.
- Batchprocesser såsom **beräkna utdrag i batch** och **Bokför utdrag i batch** körs bara i batchläge. I funktionen för bokföring av äldre utdrag kan du välja att dessa batchprocesser körs i interaktivt läge som är enkeltrådig till skillnad från batchprocesser som är flertrådade.
- I funktionen för bokföring av äldre utdrag ger ett fel i en batchuppgift feltillstånd i hela batchjobbet. I den förbättrade funktionen gör inte ett fel i en batchuppgift att hela batchjobbet hamnar i feltillstånd om andra batchuppgifter har slutförts. Du bör ta reda på bokföringsstatus för en batchkörning som körs med hjälp av sidan **Butiksutdrag** där du kan visa alla utdrag som inte bokförts på grund av fel.
- I funktionen för bokföring av äldre utdrag gör den första förekomsten av ett fel att hela batchen misslyckas. De återstående utdragen bearbetas inte. I den förbättrade funktionen fortsätter batchprocessen att bearbeta alla utdrag, även om en del av utdraget misslyckas. En fördel är att användare får insyn i hur många utdrag som innehåller fel. Därför behöver användare inte fastna i en kontinuerlig slinga med att rätta till fel och köra processen för bokföring av utdrag tills alla utdrag bokförs.

## <a name="general-guidance-about-the-statement-posting-process"></a>Allmänna riktlinjer om utdragsbokföringsprocessen

- Vi rekommenderar att du kör utdragsbokföringsprocessen i en batch eftersom batchen utnyttjar kapaciteten hos batchramverket i flertrådsteknik. Flertrådsteknik krävs för att hantera stora mängder transaktioner som normalt visas i utdragsbokföring.
- Vi rekommenderar att du aktiverar negativt fysiskt lager i artikelmodellgrupp, så att du får en sömlös bokföring. I vissa fall kan negativ utdrag inte bokföras om inte finns negativt fysiskt lager. Exempelvis ska det i teorin om det bara finns en enhet av en artikel i lager och det har skett en försäljningstransaktion och en returtransaktion för artikeln, ska transaktionen kunna bokföras även om negativt lager inte är aktiverad. Men eftersom utdragsbokföringsprocessen hämtar både försäljningstransaktionen och returtransaktionen i en enda kundorder, finns det ingen garanti för att försäljningsraden bokförs först, följt av returraden. Därför kan det uppstå fel. Om negativt lager är aktiverat i det här scenariot påverkas inte transaktionsbokföringen negativt och systemet avspeglar korrekt lagret.
- Vi rekommenderar att du använder sammanslagning när du beräknar och bokför utdrag. Följande inställningar rekommenderas därför för vissa sammanslagningsparametrar.

    - Gå till **Butiker** \> **Inställningar för huvudkontor** \> **Parametrar** \> **Detaljhandelsparametrar**. Klicka sedan på fliken **bokföring** på snabbfliken **lageruppdatering** på fältet **Detaljnivå** och välj **sammanfattning**.
    - Gå till **Butiker** \> **Inställningar för huvudkontor** \> **Parametrar** \> **Detaljhandelsparametrar**. Klicka sedan på fliken **bokföring** på snabbfliken **Sammanslagning** och ställ in alternativet **Verifikationstransaktioner** till **Ja**.
