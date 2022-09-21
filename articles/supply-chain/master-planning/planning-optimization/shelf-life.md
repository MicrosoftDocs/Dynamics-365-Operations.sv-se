---
title: Huvudplanering för produkter med begränsad hållbarhetstid
description: I den här artikeln beskrivs hur du ställer in och använder planeringsfunktioner som tar hänsyn till hållbarhetstiden för förgängliga produkter.
author: t-benebo
ms.date: 08/10/2022
ms.topic: article
ms.search.form: ReqPlanSched, CustTable, EcoResProductDetailsExtended, InventModelGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-08-10
ms.dyn365.ops.version: 10.0.28
ms.openlocfilehash: 68a1ba2bfe90aaf0462917c405d483fa12bf8126
ms.sourcegitcommit: 3d7ae22401b376d2899840b561575e8d5c55658c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/08/2022
ms.locfileid: "9428232"
---
# <a name="master-planning-for-products-with-limited-shelf-life"></a>Huvudplanering för produkter med begränsad hållbarhetstid

[!include [banner](../../includes/banner.md)]

Hållbarhetstiden är den tid som en produkt kan lagras tills den inte längre kan användas eller säljas. För produkter som har en begränsad hållbarhetstid kommer du troligen att använda en strategi för först utgått, först ut (FEFO), som prioriterar förbrukningen och försäljningen av artiklar utifrån deras återstående hållbarhetstid. Den här lagerställestrategin är relevant för livsmedel, mediciner och andra varor som kännetecknas av kort lagringstid. Enligt FEFO lagras artiklar på lagerstället som varor på en hylla: produkter som har lång hållbarhetstid placeras djupare in på hyllorna så att produkter som har en kortare hållbarhetstid levereras först.

## <a name="using-shelf-life-in-master-planning"></a>Använda hållbarhetstid i huvudplanering

I det här avsnittet förklaras hur huvudplanering föreslår leverans för artiklar med hållbarhetstid.

När du kör en huvudplan genereras föreslagna planerade order (leverans) som uppfyller din efterfrågan och minimerar också förseningar. Om planen omfattar artiklar med begränsad hållbarhetstid blir planeringsberäkningarna mer komplexa, eftersom planen inte bara får minimera förseningar utan även använda befintlig leverans innan den upphör att gälla. Planen måste försöka använda leverans som ligger närmast utgångsdatumet innan leverans som upphör att gälla. Huvudplaneringen är därför ett sätt att uppnå följande mål i den här ordningen:

1. Minimera summan av förseningarna.
1. Maximera summan av FEFO-leveransen.
1. Minimera påfyllnaden av lagret.

I vissa fall kan det uppstår en konflikt mellan de två första målen och ett val måste göras: vill du försena en leverans eller vill du använda en leverans som förfaller senare i stället för leverans som förfaller tidigare? För att lösa denna konflikt under huvudplanering prioriterar systemet minsta möjliga fördröjningar över användningen av leverans som snart förfaller. I allmänhet uppstår den här typen av konflikt när det kan uppstå fördröjningar och disponering per period. Därför rekommenderar vi att du använder en disponeringsperiod som är kortare än artikelns hållbarhetstid. Andra typer av disponering (till exempel krav) är ett problem som uppstår vid en sådan här konflikt.

## <a name="set-up-shelf-life"></a>Ställ in hållbarhetstid

### <a name="configure-each-master-plan-to-consider-shelf-life"></a>Konfigurera varje huvudplan så att den tar hänsyn till hållbarhetstid

Som standard tar huvudplaner inte hänsyn till hållbarhetstid. Gör på följande sätt när du vill aktivera beräkningar av hållbarhetstid för varje huvudplan som kräver det.

1. Gå till **Huvudplanering \> Inställningar \> Planer \> Huvudplaner**.
1. Välj antingen en befintlig plan i listrutan eller skapa en ny.
1. På snabbfliken **allmänt** anger du alternativet **Använd datum för hållbarhetstid** till *Ja*.

### <a name="configure-tracking-dimension-groups-to-track-the-batch-dimension"></a>Konfigurera spårningsdimensionsgrupper för att spåra batchdimensionen

En artikels hållbarhetstid kan endast spåras om den spåras i batchdimensionen. Med andra ord måste batchreferensen och de nödvändiga datumen registreras vid inleverans eller tillverkning, och genom varje lagertransaktion för artikeln. Du kan hantera det här alternativet genom att skapa en eller flera spårningsdimensionsgrupper för att spåra som behövs och sedan tilldela de relevanta artiklarna till dessa grupper efter behov.

Gör på följande sätt när du vill ställa in en spårningsdimensionsgrupp för spårning av batchdimensionen.

1. Gå till **Produktinformationshantering \> Inställning \> Dimensioner och variantgrupper \> Spårningsdimensionsgrupper**.
1. Gör något av följande:

    - I åtgärdsfönstret, välj **Ny** för att skapa en ny spårningsdimensionsgrupp. Ange ett namn och en beskrivning och välj sedan **Spara** i åtgärdsfönstret.
    - Välj i listfönstret den befintliga spårningsdimensionsgrupp som du vill ställa in för att spåra batchdimensionen.

1. På snabbfliken **Spårningsdimension** i rad **Batchnummer**, markera kryssrutorna i kolumnerna **Aktivt** och **Fysiskt lager**.

### <a name="set-up-shelf-life-for-a-product"></a>Ställ in hållbarhet för en produkt

Använd följande procedur när du ställer in hållbarhetstid för en produkt.

1. Gå till **Produktinformationshantering \> Produkter \> Frisläppta produkter**.
1. Skapa eller öppna produkt som ska ställas in.
1. För att använda inställningarna för hållbarhet, på snabbfliken **Allmän**, ange fältet **Spårningsdimensionsgrupp** till en spårningsdimensionsgrupp som är inställd för att spåra batchdimensionen. Du kan endast ställa in detta fält när du först skapar en produkt. Du kan inte ändra värdet för befintliga produkter.
1. På snabbfliken **Hantera lager** anger du följande fält:

    - **Datummärkningsperiod i dagar** – Ange den period (i dagar) som en batch av produkten ska ha för att säkerställa att den är lämplig för förbrukning eller återförsäljning. Värdet i det här fältet läggs till ett batchens *tillverkningsdatum* för att bestämma *datummärkning*. Du kan konfigurera systemet att generera kvalitetsorder när en batch närmar sig datummärkning.
    - **Hållbarhetstid i dagar** – Ange antalet dagar innan en batch av den här produkten upphör att gälla. Det här värdet läggs till *tillverkningsdatumet* för att bestämma *utgångsdatum*. Batchen betraktas som oanvändbar efter detta datum.
    - **Bästföretid i dagar** – Ange perioden (i dagar) efter vilken en batch av produkten bedöms som fortfarande säljbar men inte längre kan behålla vissa av sina ursprungliga egenskaper. Det här värdet läggs till *tillverkningsdatumet* för att bestämma *bäst-före-datum*. Du kan köra rapporter för att identifiera det lager som har förlöpt dess bäst-före-datum. 

### <a name="set-a-sellable-days-rule-for-each-customer"></a>Ange en regel för försäljningsbara dagar för varje kund

Funktionen *Möjliga försäljningsdagar* säkerställer att produkter från en batch som snart upphör att gälla inte skickas till kunder. Dessutom ser det till att ett tillräckligt antal säljbara dagar fortfarande finns kvar efter leveransen när produkter skickas till kunden.

Om du vill använda funktionen för säljbara dagar måste du definiera antalet säljbara dagar som gäller för varje produkt (eller grupp av produkter) för varje kund. Du måste slutföra den här processen manuellt eftersom det inte finns någon dataenhet för den.

Använd följande procedur när du ställer in säljbara dagar för varje produkt för varje kund.

1. Gå till **Försäljning och marknadsföring \> Kunder \> Alla kunder**.
1. Sök efter och välj den kund som du vill ställa in.
1. I åtgärdsfönstret, på fliken **Sälja** i gruppen **Konfigurering** markerar du **Sälja \> Säljbara dagar**.
1. På sidan **Säljbara dagar för kund** visar rutnätet befintliga regler för försäljningsbara dagar för varje produkt eller grupp av produkter. Använd knapparna i åtgärdsfönstret för att lägga till eller redigera rader i rutnätet efter behov. Ett **filter** finns med som hjälp för att hitta befintliga rader.
1. För varje rad anger du följande fält:

    - **Artikelkod** – Välj ett av följande värden för att ange omfattningen av artiklar som påverkas:

        - *Register* – Raden gäller för en viss artikel.
        - *Grupp* – Raden gäller en specifik artikelgrupp.
        - *Alla* – Raden gäller för alla artiklar.

    - **Artikelrelation** – Om du anger fältet **Artikelkod** till *Tabell* väljer du en specifik artikel. Om du anger fältet **Artikelkod** till *Grupp*, väljer du en artikelgrupp. Om du anger fältet **Artikelkod** till *Alla*, är det här fältet inte tillgängligt.
    - **Möjliga försäljningsdagar** – Ange det lägsta antal dagar som kunden måste sälja matchande produkter innan batchen upphör att gälla. Värdet för de försäljningsbara dagarna baseras på det begärda inleveransdatumet (eller det bekräftade inleveransdatumet, om det har definierats) för matchande produkter på försäljningsordern.
    - *(Övriga produktdimensioner)* – Om du vill begränsa radens omfattning ytterligare anger du andra dimensionsvärden (t.ex. **Storlek** och **Färg**) efter behov. Välj **Visa dimensioner** i åtgärdsfönstret om du vill kontrollera vilka dimensioner som visas i rutnätet.

### <a name="set-up-all-relevant-products-so-that-they-are-fefo-date-controlled"></a>Ställ in alla relevanta produkter så att de är FEFO-datumkontrollerade

För att försäljningsdagar ska fungera måste varje relevant artikel tillhöra en artikelmodellgrupp där kryssrutan **FEFO-datumkontrollerad** är markerad.

Använd följande procedur när du vill ställa in en artikelmodellgrupp så att den stöder funktionen för försäljningsdagar.

1. Gå till **Lagerhantering \> Inställningar \> Lager \> Modellgrupper för artiklar**.
1. Välj antingen en befintlig grupp i listrutan eller skapa en ny genom att välja **Ny** i åtgärdsfönstret.
1. På snabbfliken **Lagerpolicyer** väljer du kryssrutan **FEFO-datumkontrollerad**.
1. Ställ in övriga fält för gruppen efter behov.

Använd följande procedur om du vill visa eller ställa in artikelmodellgruppen som en produkt tillhör.

1. Gå till **Produktinformationshantering \> Produkter \> Frisläppta produkter**.
1. Öppna produkten som du vill inspektera eller redigera.
1. På snabbfliken **Allmänt** ange fältet **Artikelmodellgrupp** till en grupp där kryssrutan **FEFO-datumkontrollerad** har markerats.

## <a name="example-1-simple-fefo-10-day-period-zero-days-of-lead-time"></a>Exempel 1: Enkel FEFO, 10-dagarsperiod, noll dagar med produktionstid

Det här exemplet visar ett grundläggande exempel på hållbarhetstid där pegging mellan leveransorder och efterfrågan görs för att uppfylla följande mål i systemet:

- Minimera summan av förseningarna.
- Maximera summan av FEFO-leveransen.
- Minimera påfyllnaden av lagret.

Systemet har följande inställningar för artikel- och huvudplan:

- **Disponeringskod (påfyllnadsstrategi):** period 
- **Disponeringsperiod:** 10 dagar (lika med hållbarhetstid)
- **Hållbarhetstid:** 10 dagar
- **Försäljningsdagar:** 0 dagar
- **Produktionstid:** 0 dagar
- **Negativa dagar:** 0 dagar
- **Typ för planerad order (standardorderinställningar för artikeln):** Inköpsorder

Följande försäljningsorder för artikeln finns i systemet:

- **SO1:** Kvantitet (kvt) = 2, begärt leveransdatum = idag + 1 dag
- **SO2:** Kvt = 1, begärt leveransdatum = idag + 4 dagar
- **SO3:** Kvt = 1, begärt leveransdatum = idag + 5 dagar

Alla dessa försäljningsorder skapar efterfrågan för artikeln.

Följande leverans finns för artikeln:

- **Lagerbehållning:** Kvt = 1, utgångsdatum = idag + 5 dagar
- **Inköpsorder 1 (IO1):** Inleveransdatum = idag + 2 dagar, kvt = 1, utgångsdatum = idag + 4 dagar

Systemet skapar en lista med leverans som kan täcka denna efterfrågan och sorterar listan efter utgångsdatum (genom att använda FEFO).

I huvudplaneringen skapas ett behov av pegging mellan tillgång och efterfrågan. Det skapar också all nödvändig efterfrågan baserat på leveranslistan (genom att använda FEFO) och tar hänsyn till tillgänglighetsdatum.

- SO1 kan uppfyllas med lagerhållningskvantiteten, men kan inte uppfyllas av IO1, eftersom tillgänglighetsdatum för IO1 in en dag senare än SO1 kräver. Därför genererar SO1 efterfrågan på en enhet varor.
- SO2 kan täckas av IO1, eftersom IO1 kommer fram vid den begärda tiden och utgångsdatumet gäller fortfarande. Därför omfattas SO2-kravet helt av IO1.
- SO3 täcks inte, eftersom resurser inte är tillgängliga. Därför genererar SO3 efterfrågan på en enhet varor.

För att du ska kunna täcka alla återstående behov måste systemet skapa följande planerade inköpsorder:

- **PPO1:** Inleveransdatum = idag, kvt = 2, utgångsdatum = idag + 10 dagar

I följande tabell sammanfattas resultatet.

| Efterfrågan | Pegging |
|---|---|
| **SO1:** Leveransdatum = idag + 1 dag, kvt = 2 | <p>**Behållning:** Kvt = 1, utgångsdatum = idag + 5 dagar</p><p>**PPO1:** Inleveransdatum = idag, kvt = 1, utgångsdatum = idag + 10 dagar</p> |
| **SO2:** Leveransdatum = idag + 4 dagar, kvt = 1 | **PO1:** Inleveransdatum = idag + 2 dagar, 1 kvt, utgångsdatum = idag + 4 dagar |
| **SO3:** Leveransdatum = idag + 5 dagar, kvt = 1 | **PPO1:** Inleveransdatum = idag, kvt = 2, utgångsdatum = idag + 10 dagar |

Följande bild visar tidslinjen för detta exempel.

![Exempel 1: Enkel FEFO, 10-dagarsperiod, noll dagar med produktionstid.](media/fefo-example-1.png "Exempel 1: Enkel FEFO, 10-dagarsperiod, noll dagar med produktionstid")

## <a name="example-2-simple-fefo-requirement-three-days-of-lead-time"></a>Exempel 2: Enkel FEFO, krav, tre dagar med produktionstid

I det här exemplet visas hur systemets försök att minimera förseningar ibland kan leda till att överorder inträffar.

Systemet har följande inställningar för artikel- och huvudplan:

- **Disponeringskod (påfyllnadsstrategi):** krav
- **Hållbarhetstid:** 10 dagar
- **Försäljningsdagar:** 0 dagar
- **Produktionstid:** Upprättats av följande handelsavtal för leverantörer:

    - **Handelsavtal 1:** Om kvt = 1, produktionstid = 4
    - **Handelsavtal 2:** Om kvt = 2, produktionstid = 3

- **Negativa dagar:** 0 dagar
- **Typ för planerad order (standardorderinställningar för artikeln):** Inköpsorder

Följande försäljningsorderrader finns i systemet:

- **SO1:** Kvt = 2, begärt leveransdatum = idag + 3 dagar

Denna efterfrågan täcks av den befintliga tillgången och en bekräftad inköpsorder:

- **Lagerbehållning:** Tillgänglig = idag, kvt = 1, utgångsdatum = idag + 2 dagar
- **PO1:** Inleveransdatum = idag + 3 dagar, kvt = 1, utgångsdatum = idag + 4 dagar

SO1 kan inte uppfyllas med lagerbehållningen eftersom lagrets utgångsdatum infaller före leveransdatumet. IO1 kan täcka SO1-kravet med en kvantitet på endast 1. Därför genererar SO1 efterfrågan på en enhet varor. För att täcka detta behov skapar systemet en planerad inköpsorder (PPO1).

Systemet har två handelsavtal (ett för kvt = 1, produktionstid = 4 dagar och ett för kvt = 2, produktionstid = 3 dagar). Därför görs ett försök att minimera förseningar genom att skapa en planerad inköpsorder (PPO1) som uppfyller det andra handelsavtalet. Resultatet är en överleverans (kvt = 2, utgångsdatum = idag + 10 dagar).

I följande tabell sammanfattas resultatet.

| Efterfrågan | Pegging |
|---|---|
| **SO1:** Leveransdatum = idag + 3 dagar, kvt = 2 | <p>**PO1:** Inleveransdatum = idag + 3 dagar, kvt = 1, utgångsdatum = idag + 4 dagar</p><p>**PPO1:** Inleveransdatum = idag + 3 dagar, kvt = 1, utgångsdatum = idag + 10 dagar</p> |

Följande bild visar tidslinjen för detta exempel.

![Exempel 2: Enkel FEFO, krav, tre dagar med produktionstid.](media/fefo-example-2.png "Exempel 2: Enkel FEFO, krav, tre dagar med produktionstid")

## <a name="example-3-simple-fefo-requirement-three-days-of-lead-time-five-sellable-days"></a>Exempel 3: Enkel FEFO, krav, tre dagar med produktionstid, fem säljbara dagar

Det här exemplet visar hur hållbarhetstiden fungerar när säljbara dagar läggs till för en artikel.

Systemet har följande inställningar för artikel- och huvudplan:

- **Disponeringskod (påfyllnadsstrategi):** krav
- **Hållbarhetstid:** 10 dagar
- **Försäljningsdagar:** 5 dagar
- **Produktionstid:** 5 dagar
- **Negativa dagar:** 0 dagar
- **Typ för planerad order (standardorderinställningar för artikeln):** Inköpsorder

Följande försäljningsorder finns i systemet:

- **SO1:** Kvt = 2, begärt leveransdatum = idag + 2 dagar
- **SO2:** Kvt = 1, begärt leveransdatum = idag + 3 dagar
- **SO3:** Kvt = 1, begärt leveransdatum = idag + 5 dagar

Denna efterfrågan kan täckas av den befintliga tillgången och en bekräftad inköpsorder:

- **Lagerbehållning:** Tillgänglig = idag, kvt = 1, utgångsdatum = idag + 6 dagar
- **PO1:** Inleveransdatum = idag + 2 dagar, kvt = 3, utgångsdatum = idag + 10 dagar

En lista skapas med pegging-kandidater, baserad på FEFO-listan (supply list and availability dates). Därför kan SO1 inte uppfyllas med lagerbehållningen eftersom lagret förfaller före slutet på de säljbara dagar som kunden kräver (begärt inleveransdatum + 5 dagar). PO1 kan täcka SO1-behovet med två enheter och SO2-kravet med en enhet. Därför är det bara SO3 som fortfarande har ej täckt efterfrågan på en enhet varor. För att täcka detta behov skapar systemet följande planerade inköpsorder:

- **PP01:** Inleveransdatum = idag + 5 dagar, kvt = 1, utgångsdatum = idag + 10 dagar

I följande tabell sammanfattas resultatet.

| Efterfrågan | Pegging |
|---|---|
| **SO1:** Leveransdatum = idag + 2 dagar, kvt = 2 | **PO1:** Inleveransdatum = idag + 2 dagar, kvt = 2, utgångsdatum = idag + 10 dagar |
| **SO2:** Leveransdatum = idag + 3 dagar, kvt = 1 | **PO1:** Inleveransdatum = idag + 2 dagar, kvt = 1, utgångsdatum = idag + 10 dagar |
| **SO3:** Leveransdatum = idag + 5 dagar, kvt = 1 | **PPO1:** Inleveransdatum = idag + 5 dagar, kvt = 1, utgångsdatum = idag + 10 dagar |

Följande bild visar tidslinjen för detta exempel.

![Exempel 3: Enkel FEFO, krav, tre dagar med produktionstid, fem säljbara dagar.](media/fefo-example-3.png "Exempel 3: Enkel FEFO, krav, tre dagar med produktionstid, fem säljbara dagar")

## <a name="example-4-simple-fefo-period-lead-time-depends-on-the-quantity"></a>Exempel 4: Enkel FEFO, period, produktionstid beror på kvantiteten

I det här exemplet visas hur systemets försök att minimera förseningar ibland kan leda till att överorder inträffar.

Systemet har följande inställningar för artikel- och huvudplan:

- **Disponeringskod (påfyllnadsstrategi):** period
- **Disponeringsperiod:** 10 dagar (lika med hållbarhetstid)
- **Hållbarhetstid:** 10 dagar
- **Försäljningsdagar:** 0 dagar
- **Produktionstid:** Upprättats av följande handelsavtal för leverantörer:

    - **Handelsavtal 1:** Om kvt = 1, produktionstid = 5
    - **Handelsavtal 2:** Om kvt = 2, produktionstid = 0

- **Negativa dagar:** 0 dagar
- **Typ för planerad order (standardorderinställningar för artikeln):** Inköpsorder

Följande försäljningsorder finns i systemet:

- **SO1:** Kvt = 1, begärt leveransdatum = idag
- **SO2:** Kvt = 1, begärt leveransdatum = idag + 6 dagar

Denna efterfrågan kan delvis täckas av den befintliga tillgången från följande bekräftade inköpsorder:

- **PO1:** Inleveransdatum = idag + 1 dagar, kvt = 1, utgångsdatum = idag + 2 dagar
- **PO2:** Inleveransdatum = idag + 3 dagar, kvt = 1, utgångsdatum = idag + 7 dagar

Systemet har två handelsavtal (ett för kvt = 1, produktionstid = 5 dagar och ett för kvt = 2, produktionstid = 0 dagar). Därför görs ett försök att minimera förseningar genom att skapa följande planerade inköpsorder som uppfyller det andra handelsavtalet:

- **PP01:** Inleveransdatum = idag, kvt = 2, utgångsdatum = idag + 10 dagar

SO1 kommer att täckas av en enhet från PPO1. IO2 omfattas av IO2 eftersom IO2 upphör att gälla tidigare än PPO1.

I följande tabell sammanfattas resultatet.

| Efterfrågan | Pegging |
|---|---|
| **SO1:** Leveransdatum = idag, kvt = 1 | **PPO1:** Inleveransdatum = idag, kvt = 1, utgångsdatum = idag + 10 dagar |
| **SO2:** Leveransdatum = idag + 6 dagar, kvt = 1 | **PO2:** Inleveransdatum = idag + 3 dagar, kvt = 1, utgångsdatum = idag + 7 dagar |

> [!NOTE]
> PO1 används inte, eftersom den kommer för sent för S01 och upphör att gälla innan S02 levereras. PPO1 har beställts över med en enhet så att produktionstid kan vara 0 (noll) per handelsavtal 2.

Följande bild visar tidslinjen för detta exempel.

![Exempel 4: Enkel FEFO, period, produktionstid beror på kvantiteten.](media/fefo-example-4.png "Exempel 4: Enkel FEFO, period, produktionstid beror på kvantiteten")

## <a name="example-5-simple-fefo-requirement-10-negative-days"></a>Exempel 5: Enkel FEFO, behov, 10 negativa dagar

Det här exemplet visar hur hållbarhetstiden fungerar när ett stort antal negativa dagar läggs till för en artikel. Negativa dagar är antalet dagar som du är villig att vänta innan du beställer ny påfyllnad av en artikel som har negativt lager. Systemet skapar inte leverans om inte antalet negativa dagar överskrids.

Systemet har följande inställningar för artikel- och huvudplan:

- **Disponeringskod (påfyllnadsstrategi):** krav
- **Produktionstid:** 0 dagar
- **Negativa dagar:** 10 dagar
- **Typ för planerad order (standardorderinställningar för artikeln):** Inköpsorder

Följande försäljningsorderrader finns i systemet:

- **SO1:** Kvt = 1, begärt leveransdatum = idag

Denna efterfrågan kan täckas av den befintliga tillgången från följande bekräftade inköpsorder:

- **PO1:** Inleveransdatum = idag + 3 dagar, kvt = 1, utgångsdatum = idag + 5 dagar

Eftersom systemet är konfigurerat för att tillåta 10 negativa dagar, omfattar det efterfrågan på SO1 genom att använda IO1, även om resultatet blir en fördröjning på tre dagar eftersom SO1 skapar negativt lager tills IO1 anländer. Ingen planerad inköpsorder skapas, även om produktionstiden är 0 (noll) och skapandet av en planerad inköpsorder minskar fördröjningarna.

I följande tabell sammanfattas resultatet.

| Efterfrågan | Pegging |
|---|---|
| **SO1:** Leveransdatum = idag, kvt = 1 | **PO1:** Inleveransdatum = idag + 3 dagar, kvt = 1, utgångsdatum = idag + 5 dagar |

Följande bild visar tidslinjen för detta exempel.

![Exempel 5: Enkel FEFO, behov, 10 negativa dagar.](media/fefo-example-5.png "Exempel 5: Enkel FEFO, behov, 10 negativa dagar")

## <a name="example-6-simple-fefo-requirement-five-negative-days"></a>Exempel 6: Enkel FEFO, behov, fem negativa dagar

Det här exemplet visar hur hållbarhetstiden fungerar när ett stort antal negativa dagar är mindre än dess hållbarhetsperiod.

Systemet har följande inställningar för artikel- och huvudplan:

- **Disponeringskod (påfyllnadsstrategi):** krav
- **Försäljningsdagar:** 0 dagar
- **Produktionstid:** 0 dagar
- **Negativa dagar:** 5 dagar
- **Typ för planerad order (standardorderinställningar för artikeln):** Inköpsorder

Följande försäljningsorderrader finns i systemet:

- **SO1:** Kvt = 2, begärt leveransdatum = idag

Denna efterfrågan kan täckas av den befintliga tillgången från följande bekräftade inköpsorder:

- **PO1:** Inleveransdatum = idag, kvt = 1, utgångsdatum = idag + 1 dag
- **PO2:** Inleveransdatum = idag + 2 dagar, kvt = 1, utgångsdatum = idag + 3 dagar

Systemet måste dock följa begränsningen som levereras artiklar inte kan förfalla vid tidpunkten för försändelsen. Därför kan IO2 och IO1 inte båda användas för SO1, eftersom IO1 upphör att gälla innan IO2 ankommer. Systemet skapar följande planerade inköpsorder för att avsluta efterfrågan på SO1:

- **PPO1:** Inleveransdatum = idag, kvt = 1, utgångsdatum = idag + 10 dagar

Systemet kan utnyttja de fem negativa dagarna och använda IO2 och PPO1 för att täcka SO1. Det här innebär dock att leveransen försenas tills IO2 kommer, och IO1 upphör att gälla under tiden. Därför omfattar systemet SO1 genom användning av PPO1 och PO1.

I följande tabell sammanfattas resultatet.

| Efterfrågan | Pegging |
|---|---|
| **SO1:** Leveransdatum = idag, kvt = 2 | <p>**PO1:** Inleveransdatum = idag, kvt = 1, utgångsdatum = idag + 1 dag</p><p>**PPO1:** Inleveransdatum = idag, kvt = 1, utgångsdatum = idag + 10 dagar</p> |

Följande bild visar tidslinjen för detta exempel.

![Exempel 6: Enkel FEFO, behov, fem negativa dagar.](media/fefo-example-6.png "Exempel 6: Enkel FEFO, behov, fem negativa dagar")
