---
title: Prioritetsbaserad planering
description: I denna artikel beskrivs funktionen för prioritetsbaserad planering i Microsoft Dynamics 365 Supply Chain Management.
author: t-benebo
ms.date: 10/15/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-10-15
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: 8f46a4d4e087a99c00ab7b4eabc74f60043cbf21
ms.sourcegitcommit: 529fc10074b06f4c4dc52f2b4dc1f159c36e8dbc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/22/2022
ms.locfileid: "9186496"
---
# <a name="priority-based-planning"></a>Prioritetsbaserad planering

[!include [banner](../../includes/banner.md)]

I denna artikel beskrivs funktionen för prioritetsbaserad planering i Microsoft Dynamics 365 Supply Chain Management. Funktionen ger stöd för efterfrågestyrd planering, som är ett steg i DDMRP [(Demand Driven Material Requirements Planning)](ddmrp-overview.md). Med prioriterad planering kan Planeringsoptimering generera planerade order som baseras på planeringsprioritet istället för behovsdatum.

Med prioriterad planering kan du prioritera lagerpåfyllnadsorder för att säkerställa att brådskande efterfrågan prioriteras över mindre viktig efterfrågan. En lagerpåfyllnadsorder prioriteras till exempel över en standardpåfyllnadsorder. Systemet kan automatiskt dela större order i separata mindre order där orderrader grupperas efter prioritet. Därefter kan alla order med hög prioritet bearbetas först.

En snabb överblick över funktionen finns i följande video: [Planering av optimeringssupport för prioriterad planering i Dynamics 365 Supply Chain Management](https://youtu.be/GmMHzFETTQc).

## <a name="turn-on-priority-based-planning-in-your-system"></a>Aktivera prioriterad planering i systemet

Innan du kan använda den här funktionen den aktiveras i ditt system. Administratörer kan använda inställningarna [funktionshantering](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den. I arbetsytan **utgiftshantering** anges den här funktionen på följande sätt:

- **Modul:** *huvudplanering*
- **Funktionsnamn:** *Prioritetsstyrt MRP-stöd för Planeringsoptimering*

## <a name="where-and-how-planning-priorities-are-assigned"></a>Var och hur planeringsprioriteringar tilldelas

*Planeringsprioritetsinformation* om leverans och efterfrågan utgör den viktigaste delen i den prioritetsbaserade planeringen. Planeringsprioritet definierar hur viktig en efterfråge- eller leveransrad är. Planeringsoptimering används när fältet **Disponeringskod** anges som *Prioritet*.

Planeringsprioritet är vanligtvis ett värde mellan 0 (noll) och 100, där 0 har högst betydelse. Detta värde visas och anges i fältet **Planeringsprioritet**. Fältet finns på följande sidor: **Rader för efterfrågeprognos**, **Information om försäljningsorder**, **Information om inköpsorder**, **Information om överförignsorder** samt **Information om planerad order**.

När fältet **Disponeringskod** för relevant artikel eller disponeringsgrupp angetts som *Prioritet* kommer Planeringsoptimeringen att balansera tillgång och efterfrågan med hjälp av en behovsdriven metod när den beräknar planeringsprioriteten, samt – för respektive frisläppt produkt – beakta värdena som angetts för fälten **Minimum**, **Punkt för ombeställning** och **Maximum** på sidan **Artikeldisponering**.

> [!NOTE]
> Värdet *Prioritet* är endast tillgängligt för fältet **Disponeringskod** när Planeringsoptimering har aktiverats.

De relaterade *modellerna för planeringsprioritet* styr planeringsprioritet och delar upp planerade order efter prioritetsintervall. De låter dig även ange standardvärden för planeringsprioritet för varje enskild tillgångs- eller efterfrågetyp, samt definiera prioritetsberäkningsmetod.

## <a name="types-of-priority-calculation-methods"></a>Metodtyper för prioritetsberäkning

Varje modell för planeringsprioritet har en inställning för **Metod för prioritetsberäkning** som styr hur huvudplaneringen prioriterar planerade order. Tillgängliga värden är *Procent av största lagerkvantitet* och *Prioritetsintervall*. *Prioritetsintervall* representerar en mer avancerad version av metoden *Procent av maximal lagerkvantitet*.

### <a name="percent-of-maximum-inventory-quantity"></a>Procent av maximal lagerkvantitet

I beräkningsmetoden *Procent av maximal lagerkvantitet* hittar leveransprioritetsberäkningen det aktuella *totala tillgängliga lagret* (nettoflöde) som en procentsats av värdet **Maximal lagerkvantitet** som angetts för en artikel. En enda planerad order skapas sedan per artikel och leverantör (såvida inte den maximala orderkvantiteten används för att framtvinga en uppdelning). Planeringsprioritet för ordern beräknas som en procentsats av maximum.

Följande formel används:

*Procentsats av maximum* = (*Nettoflödesposition* × 100) ÷ *Maximalt lagerkvantitetsvärde från artikeldisponeringen*

I den här formeln beräknas *nettoflödespositionen* på följande sätt:

*Nettoflödesposition* = *Behållning* + *På beställning* – *Kvalificerad efterfrågan*

- *På beställning* är förväntad tillgång.
- *Kvalificerad efterfrågan* representerar nettobehoven som har behovsdatum inom planeringstidsgränsen.

Under huvudplaneringen skapas nya planerade order när nettoflödespositionen är mindre än beställningspunktkvantiteten för en artikel. Den planerade orderkvantiteten är skillnaden mellan värdet för **maximilagerkvantitet** som anges på artikelnivån och nettoflödespositionen. Den planerade orderprioritet som beräknas som en procentandel av *nettoflödespositionen* för värdet för **Maximal lagerkvantitet**.

> [!NOTE]
> Den beräknade prioriteten kan inte vara negativ, även om efterfrågan överstiger den totala tillgången. Om efterfrågan överskrider total tillgång sätts den beräknade prioriteten till 0 (noll).

### <a name="priority-ranges"></a>Prioritetsintervall

Beräkningsmetoden *Prioritetsintervall* är mer avancerad än metoden *Procent av maximal lagerkvantitet* och konfigureras på nivån för planeringsprioritetsmodell. Flera nya planerade leveransorder kan skapas för att uppfylla efterfrågan per artikel. Prioriteringarna för den planerade leveransen följer värdena som har definierats i rutnätet **Planeringsprioritetsintervall** på sidan **Planeringsprioritetsmodeller**.

Följande tillkommande regler träder i kraft när fältet **Prioritetsberäkningsmetod** anges som *Prioritetsintervall*:

- Om alternativet **Beakta efterfrågeprioritet** har angetts som *Ja* kommer den prioritet som angetts för respektive efterfrågerad att begränsa prioritetsintervallsgruppen. Prioriteten för alla nya planerade order för tillgång kommer inte att vara lägre än efterfrågans prioritet. Intervallets övre värde betraktas som ett tröskelvärde som efterfrågans prioritetsvärde jämförs med. Om efterfrågans prioritet ligger exakt i mitten mellan de övre tröskelvärdena för två intervall, väljs det intervall som har den högsta prioriteten (det vill säga det lägsta prioritetsvärdet).
- Om fältet **Skapa planerad order** för planerad prioritetsmodell har angetts som *Enstaka leverans med viktigast prioritet* kommer en enda leverans att skapas i syfte att motsvara maximum. Prioriteten anges till prioriteten för det första intervall som utlöser en leverans.
- Om det inte finns någon lagerbehållning, ingen leverans och ingen efterfrågan, används raden i rutnätet **Planera prioriteringsintervall** där fältet **Från kvantitet** angivits som *Noll*.
- Om det finns en efterfrågan men ingen lagerbehållning eller förväntad tillgång kommer raden i rutnätet **Planera prioriteringsintervall** där fältet **Från kvantitet** angivits som *Noll eller mindre* att användas.
- När intervallet som efterfrågan ingår i utvärderas påverkas inte inställningen för alternativet **Överväg efterfrågeprioritet**.

## <a name="differences-between-traditional-timeline-calculations-and-priority-based-planning"></a>Skillnader mellan beräkningar av traditionella tidslinjer och prioriterad planering

Prioriterad planering skiljer sig från beräkningar av traditionella tidslinjer på följande sätt:

- Alla vanliga förplaneringsprocessorer gäller fortfarande. Dessa förprocessorer omfattar såkallad pegging av godkända planerade order mot försäljningsbehov, mappning av inköpsrekvisitioner samt reservationslogik. Endast begäran som inte uppfylls av dessa förprocessorer behandlas.
- Vid "pegging" beaktas all leverans, oavsett prioritet. Denna leverans omfattar lagerbehållning, frisläppt leverans och icke-pegged del av godkända planerade order.
- Ingen "negativ dag"-efterfrågan kan vara "pegged" mot tillgången under hela disponeringstiden.
- När tillgången är pegged mot efterfrågan används den tillgång som har högst prioritet (dvs. det lägsta prioritetsvärdet) först. Leverans av lagerbehållning anses ha ett prioritetsvärde på 0 (noll). Därför kommer den att förbrukas som den första källan.
- Nya planerade leveransrader skapas enligt de vanliga reglerna för minsta orderstorlek, största orderstorlek, kvantitetsmultipel och så vidare.

## <a name="planning-priority-models"></a>Planeringsprioritetsmodeller

*Planeringsprioritetsmodeller* tilldelas disponeringsgrupper och kontrollerar planeringsprioritet för planerade order. De definierar den logik som bestämmer hur värdet för planeringsprioritet beräknas för varje planerad order, samt hur prioritet tilldelas planerade order, leveransrader och efterfrågerader.

Om du vill arbeta med modellerna för planeringsprioritet går du till **Huvudplanering \> Inställningar \> Prioriteringsmodeller för planering**. Som tidigare nämnts är en av en modells viktigaste inställningar värdet för **prioritetsberäkningsmetod**. Den här inställningen styr den beräkningsmetod som används när huvudplaneringen tilldelar planerade order ett prioritetsvärde.

> [!NOTE]
> Planeringsprioritetsmodeller gäller för hela organisationen samt för alla juridiska personer.

### <a name="coverage-group"></a>Disponeringsgrupp

Konfigurera en ny disponeringsgrupp som du tänker använda för prioriterad planering enligt beskrivningen i [Definiera disponeringsregler för artiklar](../tasks/define-coverage-rules-items.md). När du har skapat disponeringsgruppen ställer du in följande ytterligare fält:

- **Disponeringskod** – Välj *Prioritet* om disponeringsgruppen ska använda prioritetsbaserad planering.
- **Planeringsprioritetsmodell** – Välj en prioritetsmodell för planering som gäller för hela organisationen.

### <a name="item-coverage"></a>Artikeldisponering

Konfigurera artikeldisponeringsinställningar enligt beskrivningen i [Disponeringsinställningar](../coverage-settings.md). Som standard kopieras värdet för **Disponeringskod** som valts för disponeringsgruppen till inställningarna för artikeldisponering. Du kan emellertid åsidosätta standardvärdet som du vill. I vissa fall anges fältet **Disponeringskod** för en artikeldisponeringspost som *Planering*, men ingen modell för planeringsprioritet definieras för relaterad disponeringsgrupp. I dessa ärenden kommer alla modeller där fältet **Prioritetsberäkningsmetod** har ställts in på *Procent av maximilagerkvantiteten* och fältet **Skapa planerad order** angetts som *Enstaka leverans med den viktigaste prioriteten* att appliceras som standard.

Ställ in fältet **Disponeringskod** på *Prioritet* om du vill göra fältet **Beställningspunkt** i inställningarna för artikeldisponering tillgängligt. I det här fältet anger du den kvantitet för beställningspunkt som systemet ska använda när det avgör när planerade order med ett värde för **Disponeringskod** som är *Prioritet* ska placeras.

Kvantiteten för beställningspunkt beräknas ofta som efterfrågan under ledtiden plus ett minimivärde (säkerhetslager). Detta måste vara ett värde mellan värden för **Minimum** och **Maximum**.

Du kan till exempel konfigurera fälten på följande sätt:

- **Minimum:** *10*
- **Beställningspunkt:** *45*
- **Maximum:** *60*

I det här exemplet baseras kvantiteten för beställningspunkt på en ledtid på sju dagar och en genomsnittlig daglig användning på 5. Därför är efterfrågan under ledtiden 35. Minimivärdet på 10 (säkerhetslager) läggs sedan till för att få en beställningspunkt på 45. När de här inställningarna används kommer leverans att föreslås när den projekterade behållningsnivån är under 45. Orderprioritet baseras på inställningarna för planeringsprioritet.

### <a name="manage-planning-priority-models"></a>Hantera modeller för planeringsprioritet

Arbeta med dina modeller för planeringsprioritet. följ dessa steg:

1. Gå till **Huvudplanering \> Inställningar \> Planera prioritetsmodeller**.
1. Välj antingen en befintlig modell i listvyn eller **Ny** i åtgärdsfönstret för att skapa en ny modell.
1. Ange följande fält i den nya postrubriken:

    - **Namn** – Ange ett namn för modellen. Namnet måste vara unikt för alla juridiska personer i organisationen.
    - **Beskrivning** – Ange en beskrivning av modellen.
    - **Beräkningsmetod för prioritet** – Välj ett av följande värden:

        - *Prioritetsintervall* – När du väljer det här värdet blir rutnätet **Planeringsprioritetsintervall** tillgängligt. Där måste du skapa flera prioritetsintervall för att definiera värdet för planeringsprioritet.
        - *Procent av maximilagerkvantitet* – Beräkna värdet för planeringsprioritet som en procentsats, baserat på den projekterade lagernivån över den maximala lagerkvantiteten.

    - **Skapa planerade order** – Detta fältet är tillgängligt när fältet **Prioritetsberäkningsmetod** är inställt på *Prioritetsintervall*. Välj ett av följande värden:

        - *Enstaka leverans med den viktigaste prioriteten* – Dela inte upp planerade order baserat på prioritetsintervallet. Planeringsprioritet för en planerad order baseras på det viktigaste prioritetsintervallet (det vill säga det lägsta värdet för planeringsprioritet).
        - *Dela upp enligt prioritetsintervall* – Dela upp efterfrågan i flera planerade order baserat på intervallen för planeringsprioritet. Planeringsprioritet för enskilda planerade order definieras av planeringsprioritet i det relaterade planeringsprioritetsintervallet.

    - **Överväg efterfrågeprioritet** – Ange det här alternativet som *Ja* om du vill begränsa prioriteten för en ny planerad order som skapas för leverans. (Prioriteten blir inte lägre än den relaterade efterfrågans prioritet.) Om du anger detta alternativ som *Nej* beaktas inte efterfrågeorderns prioritet när leveransorderns prioritet beräknas.

1. Om du anger fältet **Prioritetsberäkningsmetod** som *Prioritetsintervall* använder du knapparna **Lägg till** och **Ta bort** i verktygsfältet på snabbfliken **Planera prioritetsintervall** om du vill lägga till eller ta bort prioritetsintervaller efter behov. Om det finns flera rader och du infogar en ny rad sätts planeringsprioriteten automatiskt till medelvärdet för den markerade raden och raden ovanför denna. För varje rad anger du följande fält:

    - **Planeringsprioritet** – Ange alla värden mellan 0,00 och 100,00. Detta värde representerar den planeringsprioritet som används för raden. Det lägsta prioritetsvärdet står för högsta prioritet. Ett standardvärde anges automatiskt, men du kan ändra det efter behov. Samma värde för **Planeringsprioritet** kan inte användas för mer än ett intervall för planeringsprioritet i samma modell för planeringsprioritet.
    - **Beskrivning** – Ange en beskrivning av intervallet för planeringsprioritet (t.ex. *Beställningspunkt till maximum*).
    - **Från kvantitet** – Den lägre gränsen för intervallet för planeringsprioritet. Detta värde är skrivskyddat och baserat på värdena **Till kvantitet** och **Procentsats av Till kvantitet** för föregående prioritetsintervall för planering.
    - **Till kvantitet** – Välj fältet från den artikeldisponering som ska användas för att definiera intervallets övre gräns. Följande värden stöds och påverkar värdet **Från kvantitet** för nästa intervall:

        - *Noll* – Detta värde motsvarar ett intervall negativt till noll (*Noll eller mindre* till *Noll*). För rader där det här värdet har valts är fältet **Procent av Till kvantitet** alltid skrivskyddat och alltid satt till *100* procent.
        - *Minimilagerkvantitet* – Detta värde representerar värdet **Minimum** för en artikel på sidan **Artikeldisponering**. För rader där det här värdet väljs är fältet **Procent av Till kvantitet** redigerbart och används för att ange värdet **Från kvantitet** för nästa intervall (exempelvis till *80 % av minimikvantitet för lager*).
        - *Beställningspunkt* – Detta värde representerar värdet **Beställningspunkt** för en artikel på sidan **Artikeldisponering**. För rader där det här värdet väljs är fältet **Procent av Till kvantitet** redigerbart och används för att ange värdet **Från kvantitet** för nästa intervall (exempelvis till *80 % av beställningspunkt*).
        - *Maximal lagerkvantitet* – Detta värde representerar värdet **Maximum** för en artikel på sidan **Artikeldisponering**. För rader där det här värdet väljs är fältet **Procent av Till kvantitet** redigerbart och används för att ange värdet **Från kvantitet** för nästa intervall (exempelvis till *80 % av minimikvantitet för lager*).
        - *Obegränsat* – Detta värde representerar en oändlig övre nivå i intervallet (*Oändligt eller mindre* till *Oändligt*). För rader där det här värdet har valts är fältet **Procent av Till kvantitet** alltid skrivskyddat och alltid satt till *100* procent.

    - **Procent av Till kvantitet** – Ange ett procentvärde som används för att beräkna den övre gränsen för planeringsprioritetsintervallet, baserat på det värde som har valts i fältet **Till kvantitet**. Om till exempel fältet **Till kvantitet** har angetts som *Minimilagerkvantitet* och fältet **Procentsats av Till kvantitet** har angetts som *50* kommer den övre gränsen att vara 50 procent av minimilagerkvantiteten från relaterad artikeldisponering.

1. På snabbfliken **Standardvärden för planeringsprioritet** konfigurerar du erforderliga fält i syfte att definiera standardprioriteringar för planering för respektive leveranstyp eller efterfrågerad (försäljningsorder, inköpsorder, överföringsorder eller efterfrågeprognos). Du kan endast ange positiva värden.

## <a name="view-and-maintain-planning-priority"></a>Visa och underhåll planeringsprioritet

Planeringsprioriteten visas och anges i fältet **Planeringsprioritet**. Fältet finns på sidorna som visas i följande tabell. Planeringsprioriteten anges som ett värde mellan 0 (noll) och 100, där 0 har högst betydelse.

| Sida | Fältplats | Värdekälla |
|---|---|---|
| Rader i efterfrågeprognos | <p>Fliken **Artikel**</p><p>(Markera en rad i det övre avsnittet och välj sedan panelen **Artikel**.)</p> | Standardvärde eller värde som ställs in manuellt |
| Försäljningsorderinformation | <p>Fliken **Leverans** på snabbfliken **Raddetaljer**</p><p>(Välj en rad på snabbfliken **Försäljningsorderrader** innan du på snabbfliken **Raddetaljer** väljer fliken **Leverans**.)</p> | Standardvärde, koncerninternt värde, eller värde som ställs in manuellt |
| Inköpsorderdetaljer | <p>Fliken **Leverans** på snabbfliken **Raddetaljer**</p><p>(Välj en rad på snabbfliken **Försäljningsorderrader** innan du på snabbfliken **Raddetaljer** väljer fliken **Leverans**.)</p> | Värde som ställs in under bekräftelse från planerade order, värde från koncernintern eller värde som ställs in manuellt |
| Information om överföringsorder | <p>Fliken **Leverans** på snabbfliken **Raddetaljer**</p><p>(Välj en rad på snabbfliken **Överföringsorderrader** innan du på snabbfliken **Raddetaljer** väljer fliken **Leverans**.)</p> | Värde som ställs in under bekräftelse från planerade order eller värde som ställs in manuellt |
| Information om planerade order | Snabbfliken **Allmänt** | Värde som beräknas under huvudplaneringen eller värde som ställs in manuellt |

### <a name="intercompany-trade"></a>Koncernintern handel

Värdet för **Planeringsprioritet** på koncerninterna rader för leverans och efterfrågan delas mellan de länkade entiteterna. Ändringar på någon av dem återspeglas på den länkade orderraden.

Nedan följer några exempel:

- En användare ändrar planeringsprioritet för en koncernintern försäljningsorderrad från 20 till 30. Ändringen reflekterar den länkade koncerninterna inköpsorderraden.
- En användare ändrar planeringsprioritet för en koncernintern inköpsorderrad från 40 till 50. Ändringen reflekterar den länkade koncerninterna försäljningsorderraden.
