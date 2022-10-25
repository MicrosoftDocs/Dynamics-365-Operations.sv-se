---
title: Huvudplanering med inflödesprognoser
description: I den här artikeln beskrivs hur inflödesprognoser beaktas under huvudplaneringen.
author: t-benebo
ms.date: 09/21/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2022-09-21
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: dc83d10851958ec67166cb7e40cfd84dceae6651
ms.sourcegitcommit: 3e04f7e4bc0c29c936dc177d5fa11761a58e9a02
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/18/2022
ms.locfileid: "9690099"
---
# <a name="master-planning-with-supply-forecasts"></a>Huvudplanering med inflödesprognoser

[!include [banner](../../includes/banner.md)]

Med inflödesprognoser kan du ange det leverans som du förväntar dig att behöva under en del framtida period. Vanligtvis baserar du uppskattningen på föregående års försäljningshistorik och använder sedan prognosen för budgeteringsändamål. Du kan också ställa in huvudplaner så att prognoserna tar hänsyn till prognoser under planeringen.

## <a name="set-up-a-master-plan-to-consider-supply-forecasts"></a>Ställ in en huvudplan för att beakta inflödesprognoser

Du kan ange om respektive huvudplan ska beakta prognoser när den körs. Gör på följande sätt när du vill ställa in prognosalternativ för varje plan.

1. Gå till **Huvudplanering \> Inställningar \> Planer \> Huvudplaner**.
1. Välj antingen en befintlig huvudplan i listvyn eller **Ny** i åtgärdsfönstret för att skapa en ny.
1. På snabbfliken **Allmänt** ange följande fält:

    - **Prognosmodell** – Välj den modell som innehåller de leverans- och/eller efterfrågeprognoser som huvudplanen ska ta i beaktande.
    - **Inkludera inflödesprognos** – Ange detta alternativ till *Ja* om huvudplanen bör beakta inflödesprognos.
    - **Inkludera efterfrågeprognos** – Ange detta alternativ till *Ja* om huvudplanen bör beakta efterfrågeprognoser. Även om den här inställningen är oberoende av inställningen **Inkludera inflödesprognos** gäller vissa av de andra inställningarna på sidan både för inflödesprognoser och efterfrågeprognoser. Mer information om planering där efterfrågeprognoser beaktas finns i [huvudplanering med efterfrågeprognoser](demand-forecast.md).
    - **Metod som används för att minska prognosbehov** – Välj den metod som ska användas för att minska prognoskraven under huvudplanering:

        - *Ingen* – Prognosbehoven reduceras inte under huvudplaneringen.
        - Om du väljer *Procent – reduceringsnyckel* kommer kraven att reduceras enligt procentsatserna och de tidsperioder som definieras i reduceringsnyckeln.
        - Om du väljer *Transaktioner – reduceringsnyckel* prognosbehoven reduceras av de transaktioner som genomförs under de tidperioder som definieras av reduceringsnyckeln.
        - Om du väljer *transaktioner – dynamisk period* reduceras prognosbehoven av de ordertransaktioner som sker under en dynamisk period. Den dynamiska perioden omfattar de aktuella prognosdatumen och slutar när nästa prognos börjar. Metoden *Transaktioner – dynamisk period* använder eller kräver inte en reduceringsnyckel och när du använder den gäller följande villkor:

            - Om prognosen reduceras fullständigt, blir prognosbehoven för den aktuella prognosen 0 (noll).
            - Om det inte finns någon framtida prognos, kommer prognosbehov från sista prognosen att reduceras.
            - Tidsgränser ingår i prognosförminskningsberäkningen.
            - Positiva dagar ingår i beräkningen av prognosreducering.
            - Om verkliga ordertransaktioner överskrider prognosbehoven, förs resten av transaktionerna inte framåt till nästa prognosperiod.

        > [!NOTE]
        > Inställningen **Metod som används för att minska prognosbehov** gäller även efterfrågeprognoser om du har aktiverat dem för översiktsplanen och det påverkar dem på liknande sätt. För mer information, se [Huvudplanering med efterfrågeprognoser](demand-forecast.md).

## <a name="set-reduction-options-for-coverage-groups"></a>Ställ in reduceringsalternativ för disponeringsgrupper

Följ de här stegen om du vill ställa in alternativ som styr hur disponeringsgruppen ska minska sina prognosbehov för huvudplaner som använder transaktionsbaserad reducering.

1. Gå till **huvudplanering \> inställningar \> planer \> disponeringsgrupper**.
1. Välj antingen en befintlig disponeringsgrupp i listvyn eller **Ny** i åtgärdsfönstret för att skapa en ny.
1. På snabbfliken **Övriga** i fältet **Reducera prognos med** specificera hur utbudsprognoskraven ska minskas för artiklar i täckningsgruppen, för huvudplaner där fältet **Metod som används för att minska prognosbehov** anges till *Transaktioner – reduceringsnyckel* eller *Transaktioner – dynamisk period*. Välj ett av följande värden:

    - *Alla transaktioner* – alla transaktioner ska reducera prognosen.
    - *Order* – endast order av samma typ ska minska prognosen.

    Till exempel anger inställningarna för standardbeställning för en vara att den ska produceras. Det finns en leveransprognosrad för kvantiteten 50 och det finns en befintlig inköpsorder med kvantiteten 20. Om fältet **Reducera prognos med** anges till *Order*, en planerad produktionsorder kommer att skapas för en mängd av 50. Om det är inställt på *Alla transaktioner*, reduceras den planerade tillverkningsordern till kvantiteten 30.

    Inställningen gäller även för reducering av efterfrågeprognoser. För mer information, se [Huvudplanering med efterfrågeprognoser](demand-forecast.md).

## <a name="enter-a-supply-forecast-for-a-product"></a>Ange en inflödesprognos för en produkt

Om du vill ange en inflödesprognos för en produkt följer du dessa steg.

1. Gå till **Produktinformationshantering \> Produkter \> Frisläppta produkter**.
1. Välj den produkt som du vill ange en prognos för.
1. I åtgärdsfönstret, på fliken **Plan**, väljer du **Inflödesprognos**.
1. På sidan **Inflödesprognos** i åtgärdsfönstret, välj **Ny** för att lägga till en prognosrad i rutnätet.
1. Ange den nya raden information som behövs för att ange prognosen.

## <a name="plan-for-an-item-with-supply-forecast-lines"></a>Planera för en artikel med inflödesprognosrader

När du kör en huvudplan som omfattar en artikel som det finns en inflödesprognos för, skapas en inköpsorder för leveransraderna som har angetts. Inställningar för standardorder för artikeln iakttas. Om dessa standardordningsinställningar anger ett värde **Standardordertyp** för *Inköpsorder* och inget leverantörskonto anges på inflödesprognosraden, kommer systemet att använda standardleverantören för artikeln.

## <a name="check-whether-a-planned-order-is-a-supply-forecast-order"></a>Kontrollera om en planerad order är en inflödesprognosorder

Använd följande procedur när du vill ta reda på om en planerad order skapades till följd av en inflödesprognos.

1. Gå till **Huvudplanering \> Huvudplanering \> Planerade order**.
1. Öppna den planerade beställningen som du vill inspektera.
1. I snabbfliken **Allmänt** tittar du på värdet i fältet **Inflödesprognos**. Om ordern skapades för att täcka en inflödesprognos sätts det här fältet till *Ja*.

## <a name="examples-of-master-planning-with-supply-forecasts"></a>Exempel på huvudplanering med inflödesprognoser

Det här avsnittet innehåller flera exempel som visar hur inflödesprognoser påverkar huvudplaneringen.

### <a name="example-1-supply-forecast-for-an-item"></a>Exempel 1: Inflödesprognos för en vara

Du har en artikel med standardordertypen *Inköpsorder* och standardleverantören är *US-002*. Den har följande rad för inflödesprognos.

| Modell    | Datum     | Leverantörskonto | Leverantörsgrupp | Antal | Enhet | Webbplats | Lagerställe |
|----------|----------|----------------|--------------|----------|------|------|-----------|
| CurrentF | 10/10/22 |                |              | 35       | st   | 1    | 11        |

När du kör huvudplanering skapas en planerad inköpsorder på *35 ea* leverantören *US-002*.

### <a name="example-2-several-supply-forecast-lines-with-and-without-a-vendor"></a>Exempel 2: Flera rader för inflödesprognos, med och utan en leverantör

Du har en artikel med standardordertypen *Inköpsorder* och standardleverantören är *US-002*. Den har följande rader för inflödesprognos.

| Modell    | Datum     | Leverantörskonto | Leverantörsgrupp | Antal | Enhet | Webbplats | Lagerställe |
|----------|----------|----------------|--------------|----------|------|------|-----------|
| CurrentF | 10/10/22 |                |              | 35       | st   | 1    | 11        |
| CurrentF | 10/10/22 | US-101         |              | 25       | st   | 1    | 11        |

I det här fallet behandlas raden som inte anger en leverantör som en allmän prognos och det förutsätter att raden som anger en leverantör ska dras från den allmänna prognosen. Huvudplaneringen skapar därför följande planerade inköpsorder för artikeln:

- En planerad inköpsorder med kvantiteten *25 ea* från leverantören *US-101* (Leverantören och kvantiteten som anges på prognosraden används.)
- En planerad inköpsorder med kvantiteten *10 ea* från leverantören *US-002* (Eftersom ingen leverantör angavs på den andra prognosraden används standardleverantören och kvantiteten på denna prognosrad minskas med kvantiteten för den leverantörsspecifika prognosraden.)

### <a name="example-3-plans-that-use-the-transactions---dynamic-period-reduction-method-in-a-single-forecast-period"></a>Exempel 3: Planer där transaktionerna används – dynamisk periodreduceringsmetod i en enda prognosperiod

För huvudplaner där *Transaktioner – dynamisk period* som prognosreduceringsmetod kommer huvudplanering att minska prognostiserade kvantiteter om det finns befintliga transaktioner som matchar dessa utbudsegenskaper.

Du har till exempel en artikel där standardordertypen är *Inköpsorder*. Den har följande rad för inflödesprognos.

| Modell    | Datum     | Leverantörskonto | Leverantörsgrupp | Antal | Enhet | Webbplats | Lagerställe |
|----------|----------|----------------|--------------|----------|------|------|-----------|
| CurrentF | 10/10/22 | US-101         |              | 25       | st   | 1    | 11        |

Eftersom det bara finns en inflödesprognosrad finns det bara en prognosperiod.

När du kör en huvudplan som är inställd på att använda *Transaktioner – dynamisk period* som reduceringsmetod kan något av följande resultat inträffa:

- Om det finns en inköpsorder för leverantören *US-101* och kvantiteten *10 ea* och **Inflödesprognos** anges till *Ja*, huvudplaneringen skapar en ny planerad inköpsorder för den återstående kvantiteten av *10 ea*. Prognosraden minskas eftersom leverantören matchar den befintliga inköpsordern.
- Om det finns en inköpsorder för leverantören *US-102*, webbplats *1*, lagerställe *11* och kvantiteten *10 ea* och fältet **Inflödesprognos** anges till *Ja*, huvudplanering skapar en ny planerad inköpsorder för hela kvantiteten av *25 ea*. Prognosraden kan inte reduceras eftersom den har en annan leverantör än den befintliga inköpsordern.

> [!NOTE]
> Det kan inträffa för planerade inköpsorder eftersom en leverantör är kopplad till dem. För överföringsorder och produktionsorder kommer dock inflödesprognosbeloppen alltid att reduceras med befintliga order, eftersom ingen leverantör är angiven för dessa typer av order.

### <a name="example-4-plans-that-use-the-transactions---dynamic-period-reduction-method-over-several-forecast-periods"></a>Exempel 4: Planer där transaktionerna används – dynamisk periodreduceringsmetod över flera prognosperioder

Du har artikel där standardordertypen är *Inköpsorder*. Den har följande rader för inflödesprognos.

| Modell    | Datum     | Leverantörskonto | Leverantörsgrupp | Antal | Enhet | Webbplats | Lagerställe |
|----------|----------|----------------|--------------|----------|------|------|-----------|
| CurrentF | 10/10/22 | US-101         |              | 25       | st   | 1    | 11        |
| CurrentF | 10/15/22 | US-101         |              | 25       | st   | 1    | 11        |

I det här exemplet finns det två prognosrader, som alla har ett annat datum. Därför skapar datumen gränserna för prognosperioderna. Den första perioden är från 10 oktober till 14 oktober 2022 (10/10/22 – 10/14/22). Den andra är från den 15 oktober 2022 (10/15/22) och framåt.

Det finns en befintlig inköpsorder för leverantören *US-101*, kvantiteten *10 ea* och datumet *10/12/22* (12 oktober 2022). När du kör en huvudplan som är inställd på att använda *Transaktioner – dynamisk period* som reduceringsmetod kommer det att skapa följande order:

- En planerad order på kvantiteten *15 ea* och datumet *10/10/22* (Kvantiteten reduceras med den befintliga inköpsorder som är daterad under samma prognosperiod.)
- En planerad order på kvantiteten *25 ea* och datumet *10/15/22* (Kvantiteten är hela kvantiteten i prognosen.)

### <a name="example-5-plans-that-use-no-reduction"></a>Exempel 5: Planer där ingen reducering används

När du kör en plan där prognosreduceringsmetoden är *Ingen*, skapar huvudplanering alltid planerad leverans för alla inflödesprognosrader. När den planerade leveransen har godkänts kommer den att minska framtida planerade order. Inköpsorder minskar emellertid inte inflödesprognosraderna.

Du har till exempel en artikel där standardordertypen är *Inköpsorder*. Den har följande rad för inflödesprognos.

| Modell    | Datum     | Leverantörskonto | Leverantörsgrupp | Antal | Enhet | Webbplats | Lagerställe |
|----------|----------|----------------|--------------|----------|------|------|-----------|
| CurrentF | 10/10/22 | US-101         |              | 25       | st   | 1    | 11        |

Det finns en befintlig inköpsorder för leverantören *US-101*, webbplats *1*, lagerställe *11*, en kvantitet av *25 ea* och datumet *10/10/22*. 

När du kör en huvudplan som är inställd på att använda *Ingen* som reduceringsmetod, skapar den en planerad inköpsorder för leverantören *US-101*, webbplats *1*, lagerställe *11*, en kvantitet på *25 ea* och datumet *10/10/22*. Med andra ord minskas inte den befintliga inköpsordern eftersom prognosreduceringsmetoden är *Ingen*.

Du redigerar nu den planerade inköpsordern som skapades efter den senaste planeringskörningen och ändrar kvantiteten till *15 ea*. Du godkänner då beställningen. Nästa gång du kör huvudplanen kommer det att skapa en planerad inköpsorder för leverantören *US-101*, webbplats *1*, lagerställe *11*, en kvantitet på *10 ea* och datumet *10/10/22*. Denna tidpunkt reduceras kvantiteten så att den återspeglar kvantiteten för den befintliga godkända ordern från föregående planeringskörning.

## <a name="differences-between-planning-optimization-and-the-built-in-planning-engine"></a>Skillnader mellan planeringsoptimering och den inbyggda planeringsmotorn

Inflödesprognoser fungerar lite olika, beroende på vilken planeringsmotor du använder (inbyggd huvudplanering eller planeringsoptimering). Det här avsnittet beskriver skillnaderna.

### <a name="vendor-groups"></a>Leverantörsgrupper

När du lägger till en prognosrad kan du ange en leverantör och en leverantörsgrupp. I den inbyggda planeringsmotorn grupperas planerade order efter kombinationen av leverantörs- och leverantörsgruppvärden. I Planeringsoptimering grupperas planerade order per leverantör.

Följande tabell innehåller några exempel på leveransprognosrader för en artikel.

| Modell    | Datum     | Leverantörskonto | Leverantörsgrupp | Antal | Enhet | Webbplats | Lagerställe |
|----------|----------|----------------|--------------|----------|------|------|-----------|
| CurrentF | 10/10/22 |                | VendorGroupA | 5        | st   | 1    | 11        |
| CurrentF | 10/10/22 |                | VendorGroupA | 6        | st   | 1    | 11        |
| CurrentF | 10/10/22 |                |              | 7        | st   | 1    | 11        |

Leverantör *VendorA* är standardleverantör för leverantörsgruppen *VendorGroupA*. Det är också standardleverantören för artikeln.

Den inbyggda planeringsmotorn skapar följande order:

- En planerad inköpsorder för leverantör *VendorA*, leverantörsgrupp *VendorGroupA* och kvantiteten *11*
- En planerad inköpsorder för leverantör *VendorA* och kvantiteten *7*

Planeringsoptimering skapar bara en order:

- En planerad inköpsorder för leverantör *VendorA*, leverantörsgrupp *VendorGroupA* och kvantiteten *18*

### <a name="reduction-of-general-forecasts-by-more-specific-forecasts"></a>Reducering av allmänna prognoser med mer specifika prognoser

I den inbyggda huvudplaneringsmotorn blir resultatet oförutsägbart om vissa prognoser har en leverantör men andra inte.

Vid planeringsoptimering minskas allmänna prognoser alltid med mer specifika prognoser, vilket visas i följande exempel.

Följande tabell innehåller några exempel på leveransprognosrader för en artikel.

| Datum       | Antal | Leverantör   | Leverantörsgrupp  |
|------------|----------|----------|---------------|
| 02/11/2022 | 5.00     | Vendor-A | VendorGroup-A |
| 02/11/2022 | 6,00     | Vendor-A | VendorGroup-A |
| 02/11/2022 | 15.00    |          |               |

Den allmänna prognosen (för 15,00 enheter) minskas med de mer specifika prognoserna (för 5,00 + 6,00 = 11,00 enheter). Resten tilldelas standardleverantören. Följande tabell visar planerade order.

| Datum       | Antal | Leverantör   | Leverantörsgrupp  |
|------------|----------|----------|---------------|
| 02/11/2022 | 11.00    | Vendor-A | VendorGroup-A |
| 02/11/2022 | 4.00     | Vendor-A | VendorGroup-A |

### <a name="respect-for-default-order-settings-when-planned-orders-are-generated"></a>Följa standardorderinställningar när planerade order genereras

Varje artikel kan ha standardorderinställningar, till exempel en minsta inköpsorderkvantitet. Den inbyggda planeringsmotorn ignorerar inställningarna och översätter därför prognoser till planerade order som har samma kvantitet. Planeringsoptimering följer inställningarna när planerade order genereras från leveransprognoser. 

### <a name="aggregation-of-planned-orders-as-a-result-of-reduction-by-approved-orders"></a>Aggregering av planerade order till följd av reducering av godkända order

Den inbyggda huvudplaneringsmotorn förutsätter att endast en order minskar den befintliga leveransprognosen. Om flera order matchar en inflödesprognosrad är det därför endast den första ordern som minskar den. I Planeringsoptimering minskar alla order som matchar inflödesprognosraden den.

### <a name="reduction-of-forecasts-by-matching-vendors-only"></a>Reducera prognoser genom att endast matcha leverantörer

När den inbyggda huvudplaneringsmotorn minskar en prognos från befintliga frisläppta inköpsorder, ser den inte till att leverantören på inköpsordern matchar leverantören från prognosen. Vid planeringsoptimering minskas prognoserna bara genom inköpsorder som har ett matchande värde i leverantörsfältet.

För överförings- och produktionsorder ignoreras alltid leverantörsfältet, eftersom det inte är relevant för dessa ordertyper.

### <a name="reduction-of-forecasts-by-transfer-orders"></a>Reducering av prognoser genom överföringsorder

Om standardordertypen för en artikel är *Överföring* kan prognoser endast reduceras med befintliga planerade överföringsorder. För tillverkningsorder och inköpsorder är det dock bara frisläppta order som minskar leveransprognosen.

Den inbyggda planeringsmotorn minskar för alla överföringsorderläge, medan planeringsoptimering bara minskar prognoserna genom att överföringsorder som har statusen *Frisläppt* minskar.
