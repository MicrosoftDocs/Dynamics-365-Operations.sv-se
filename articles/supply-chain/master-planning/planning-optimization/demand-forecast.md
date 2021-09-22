---
title: Huvudplanering med efterfrågeprognoser
description: I det här avsnittet beskrivs hur du inkluderar efterfrågeprognoser vid huvudplanering med planeringsoptimering.
author: ChristianRytt
ms.date: 12/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqPlanSched, ReqGroup, ReqReduceKey, ForecastModel
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-12-02
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 0f322dd63cb2dee6a9048e6ed086dc075cc0e1b9
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7474854"
---
# <a name="master-planning-with-demand-forecasts"></a>Huvudplanering med efterfrågeprognoser

[!include [banner](../../includes/banner.md)]

Du kan använda en efterfrågeprognos tillsammans med planeringsoptimering för att redovisa förväntad efter frågan i huvudplaneringen. Du kan manuellt skapa en efterfrågeprognos, importera den eller generera den med hjälp av funktionen för efterfrågeprognos i Microsoft Dynamics 365 Supply Chain Management. Mer information om efterfrågeprognoser finns i [Översikt över efterfrågeprognoser](../introduction-demand-forecasting.md).

> [!NOTE]
> Planeringsoptimering stöder inte separat prognosplanering. Därför har inställningen för **aktuell prognosplan** på sidan **parametrar för huvudplanering** när du använder planeringsoptimering.

## <a name="set-up-a-master-plan-to-include-a-demand-forecast"></a>Ställ in en huvudplan för att inkludera en efterfrågeprognos

Följ dessa steg för att konfigurera en huvudplan så att den innehåller en efterfråganprognos.

1. Gå till **Huvudplanering \> Inställningar \> Planer \> Huvudplaner**.
1. Välj en befintlig plan eller skapa en ny plan.
1. På snabbfliken **Allmänt** ange följande fält:

    - **Prognosmodell** – Välj den prognosmodell som ska tillämpas. Den här modellen kommer att beaktas när ett leveransförslag skapas för den aktuella huvudplanen.
    - **Inkludera efterfrågeprognos** – Ange detta alternativ till *Ja* om du vill inkludera efterfrågeprognosen i den aktuella huvudplanen. Om du ställer in den på *Nej*, tas inte efterfrågeprognos transaktioner med i huvudplanen.
    - **Metod som används för att minska prognosbehov** – Välj den metod som ska användas för att minska prognosbehoven. Mer information finns i avsnittet [Prognosreduceringnycklar](#reduction-keys) senare i det här avsnittet.

1. På snabbfliken **Tidsgräns i dagar** du kan ställa in följande fält för att ange den period som efterfrågan förutses inkluderas under:

    - **Prognosplan** – Ställ in det här alternativet på *Ja* för att åsidosätta tidsgränsen för en prognosplan som kommer från de enskilda disponeringsgrupper. Ställ in den på *Nej* om du vill använda värdena från de enskilda disponeringsgrupper för den aktuella huvudplanen.
    - **Prognostidsperiod** – om du ställer in alternativet **prognosplan** till *Ja* anger du antalet dagar (från dagens datum) som efterfrågeprognos ska användas.

    > [!IMPORTANT]
    > Inställningen **Prognosplan** stöder inte separat prognosplanering.

## <a name="set-up-a-coverage-group-to-include-a-demand-forecast"></a>Ställ in en disponeringsgrupp för att inkludera en efterfrågeprognos

Följ dessa steg för att konfigurera en disponeringsgrupp så att den innehåller en efterfråganprognos.

1. Gå till **huvudplanering \> inställningar \> planer \> disponeringsgrupper**.
1. Välj en befintlig disponeringsgrupp eller skapa en ny grupp.
1. På snabbfliken **Andra** ange följande fält:

    - **Tidsgräns för prognosplan** – Ange antalet dagar (från dagens datum) som efterfrågeprognos ska användas för. Det här värdet kan åsidosättas med hjälp av alternativet **prognosplan** i huvudplanen, enligt beskrivningen i föregående avsnitt.
    - **Reduceringsnyckel** – Välj den reduceringsnyckel som ska användas. Mer information finns i avsnitt [skapa och ställa in en prognosreduceringsnyckel](#create-reduction-key) och [använda ett reduceringsnyckel](#use-reduction-key) senare i det här avsnittet.
    - **Reducera prognos med** – för huvudplaner där fältet **Metod som används för att minska prognosbehoven** är inställt på *transaktioner - reduceringsnycklar* eller *transaktioner-dynamisk period* anger du vilka transaktioner som ska reducera prognosen. Välj ett av följande värden:

        - **Alla transaktioner** – alla transaktioner ska reducera prognosen.
        - **Order** – endast försäljningsorder ska minska prognosen.

        > [!NOTE]
        > Om du väljer *alla transaktioner* betraktas transaktioner som har både efterfrågan och tillgång i samma lagerdimensioner neutrala och ignoreras under prognosminskningen. Om t.ex. planeringsdimensionen är inställd på endast webbplats, inte lagerställe, en överföringsorder mellan webbplats 1, lagerställe 11 och webbplats 1, lagerställe 13, ignoreras den återstående efterfrågeprognosen.

    - **Inkludera koncerninterna order** – Ange det här alternativet till *Ja* om koncerninterna order ska inkluderas när prognosen minskas. Annars ställer du in den på *Nej*.
    - **Inkludera kundprognos i efterfrågeprognosen** – Ange om en kundprognos ska inkluderas i den övergripande prognosen. Det här alternativet bestämmer hur faktisk efterfrågan minskar den prognostiserade efterfrågan. Du kan använda den här inställningen för att säkerställa att huvudplaneringen omfattar tillförseln av artiklar som köps av vissa kunder.

        - Ställ in det här alternativet på *Ja* om du vill inkludera en kundprognos i den övergripande prognosen. I det här fallet minskar den faktiska kundens efter frågan både kundprognosen och den övergripande prognosen. Huvudplaneringen genererar planerade ordrar som endast täcker den övergripande prognoskvantiteten.
        - Ställ in det här alternativet på *Nej* om du inte vill inkludera en kundprognos i den övergripande prognosen. I det här fallet minskar faktiskt kund efterfrågan endast kundprognosen. Huvudplaneringen genererar planerade order för att täcka både den totala prognoskvantiteten och prognosen för varje kundkvantitet.

## <a name="forecast-reduction-keys"></a><a name="reduction-keys"></a>Prognosreduceringnycklar

Det här avsnittet innehåller information om de olika metoder som används för att minska prognosbehov. Det inkluderar exempel på resultatet av varje metod. Det förklarar även hur du skapar, konfigurerar och använder en prognosreduceringnyckel. Vissa metoder använder en prognosreduceringnyckel för att ange hur du ska minska prognosbehoven.

### <a name="methods-that-are-used-to-reduce-forecast-requirements"></a>Metoder som används för att minska prognosbehov

När du inkluderar en prognos i en huvudplan kan du välja hur prognosbehoven reduceras när faktisk efterfrågan inkluderas. Observera att huvudplaneringen exkluderar prognoskrav från det förflutna, vilket innebär alla prognoskrav före dagens datum.

Om du vill ta med en prognos i en huvudplan och välja den metod som används för att minska prognosbehoven, gå till **huvudplanering \> inställningar \> planer \> huvudplaner**. I fältet **prognosmodell** väljer du en prognosmodell. I fältet **Metod som används för att minska prognosbehov** väljer du en metod. Följande alternativ är tillgängliga:

- None
- Procent - reduceringsnyckel
- Transaktioner – reduceringsnyckel (ännu ej stöd för planeringsoptimering)
- Transaktions - dynamisk period

Följande avsnitt innehåller mer information om varje alternativ.

#### <a name="none"></a>Ingen

Om du väljer **Inga** minskas prognosbehoven inte under huvudplaneringen. I detta fall skapar huvudplaneringen planerade order för att tillhandahålla prognostiserade efterfrågan (prognosbehov). Dessa planerade order behåller det föreslagna antalet oavsett andra typer av efterfrågan. Om till exempel försäljningsorder placeras skapar huvudplanen ytterligare planerade order för att tillhandahålla försäljningsorder. Antalet prognosbehov reduceras inte.

#### <a name="percent--reduction-key"></a>Procent - reduceringsnyckel

Om du väljer **Procent - reduceringsnyckel** prognosbehoven reduceras enligt procentsatserna och de perioder som definieras av reduceringsnyckeln. I detta fall skapar huvudplaneringen planerade order där kvantiteten beräknas som det prognostiserade antalet × reduceringsnyckel i varje period. Om det finns andra typer av efterfrågan, skapar huvudplanering planerade order för att tillgodose den efterfrågan.

##### <a name="example-percent--reduction-key"></a>Exempel: Procent - reduceringsnyckel

Detta exempel visar hur en reduceringsnyckel reducerar behoven av efterfrågeprognos enligt procentsatserna och de perioder som definieras av reduceringsnyckeln.

I det här exemplet inkluderar du följande efterfrågeprognos i en huvudplan.

| Månad    | Efterfrågeprognos |
|----------|-----------------|
| Januari  | 1 000           |
| Februari | 1 000           |
| Mars    | 1 000           |
| april    | 1 000           |

Ange följande rader på sidan **Reduceringsnycklar**.

| Växel | Enhet  | Procent |
|--------|-------|---------|
| 1      | Månad | 100     |
| 2      | Månad | 75      |
| 3      | Månad | 50      |
| 4      | Månad | 25      |

Du tilldelar reduceringsnyckeln till artikelns täckningsgrupp. Sedan på sidan **huvudplaner** i fältet **Metod som används för att minska prognosbehov** väljer du **procent - reduceringsnyckel**.

I det här fallet om du kör prognosplanering den 1 januari förbrukas kraven på efterfrågeprognos enligt de procentsatser som du ställer in på sidan **Reduceringsnycklar**. Följande behovskvantiteter överförs till huvudplanen.

| Månad                | Planerad orderkvantitet | Beräkning    |
|----------------------|------------------------|----------------|
| Januari              | 0                      | = 0 % × 1 000   |
| Februari             | 250                    | = 25 % × 1 000  |
| Mars                | 500                    | = 50 % × 1 000  |
| april                | 750                    | = 75 % × 1 000  |
| Maj - december | 1 000                  | = 100 % × 1 000 |

#### <a name="transactions--reduction-key"></a>Transaktioner - reduceringsnyckel

Om du ställer in fältet **Metod som används för att minska prognosbehov** till *Transaktioner - reduceringsnyckel* reduceras prognosbehoven med de kvalificerade efterfrågetransaktioner som inträffar under de perioder som definieras av reduceringsnyckeln.

Det kvalificerade behovet definieras i fältet **Minska prognos med** på sidan **Disponeringsgrupper**. Om du ställer in fältet **Minska prognos med** till *Order* beaktas endast försäljningsordertransaktioner som kvalificerade efterfrågan. Om du ställer in det till *Alla transaktioner* beaktas alla icke-koncerninterna lagertransaktioner som kvalificerade efterfrågan. Om koncerninterna order ska inkluderas när prognosen minskas ställer du in alternativet **Inkludera koncerninterna order** till *Ja*.

Prognosreducering startar med den första (tidigaste) efterfrågeprognosposten i perioden för reduceringsnyckeln. Om kvantiteten för kvalificerade lagertransaktioner är större än kvantiteten på efterfrågeprognosraderna i samma reduceringsnyckelperiod, används saldot för lagertransaktionskvantiteten för att minska efterfrågeprognoskvantiteten under den föregående perioden (om det finns en oförbrukad prognos).

Om ingen oförbrukad prognos finns kvar i den föregående perioden för reduceringsnyckeln används saldot för lagertransaktionerna för att minska prognoskvantiteten under nästa månad (om det finns en oförbrukad prognos).

Värdet i fältet **Procent** på reduceringsnyckelns rader används inte när fältet **Metod som används för att minska prognosbehov** är inställt *Transaktioner - reduceringsnyckel*. Endast datumen används för att definiera perioden för reduceringsnyckeln.

> [!NOTE]
> Prognoser som bokförs på eller före dagens datum ignoreras och används inte för att skapa planerade order. Om till exempel din efterfrågeprognos för månaden genereras den 1 januari och du kör huvudplanering som inkluderar efterfrågeprognoser den 2 januari ignorerar beräkningen efterfrågeprognosraden som är daterad den 1 januari.

##### <a name="example-transactions--reduction-key"></a>Exempel: Transaktioner - reduceringsnyckel

Detta exempel visar hur aktuella order som inträffar under de perioder som definieras av reduceringsnyckeln reducerar behoven av efterfrågeprognos.

[![Faktiska order och prognoser innan huvudplaneringen körs.](media/forecast-reduction-keys-1-small.png)](media/forecast-reduction-keys-1.png)

I det här exemplet väljer du *Transaktionsplaner - reduceringsnyckel* i fältet **Metod som används för att minska prognosbehov** på sidan **Huvudplaner**.

Följande rader för efterfrågeprognoser finns den 1 april.

| Datum     | Prognostiserat antal enheter |
|----------|-----------------------------|
| 5 april  | 100                         |
| 12 april | 100                         |
| 19 april | 100                         |
| 26 april | 100                         |
| 3 maj    | 100                         |
| 10 maj   | 100                         |
| 17 maj   | 100                         |

Följande försäljningsorderrader finns i april.

| Datum     | Begärt antal enheter |
|----------|----------------------------|
| 27 april | 240                        |

[![Planerad leverans genererad baserat på aprilorder.](media/forecast-reduction-keys-2-small.png)](media/forecast-reduction-keys-2.png)

Följande behovskvantiteter överförs till huvudplanen när huvudplaneringen körs den 1 april. Som du ser har prognostransaktionerna i april minskats med efterfrågekvantiteten 240 i en sekvens, med början från den första av dessa transaktioner.

| Datum     | Obligatoriskt antal enheter |
|----------|---------------------------|
| 5 april  | 0                         |
| 12 april | 0                         |
| 19 april | 60                        |
| 26 april | 100                       |
| 27 april | 240                       |
| 3 maj    | 100                       |
| 10 maj   | 100                       |
| 17 maj   | 100                       |

Anta nu att nya order importerades för maj.

Följande försäljningsorderrader finns i maj.

| Datum   | Begärt antal enheter |
|--------|----------------------------|
| 4 maj  | 80                         |
| 11 maj | 130                        |

[![Planerad leverans genererad baserat på april- och majorder.](media/forecast-reduction-keys-3-small.png)](media/forecast-reduction-keys-3.png)

Följande behovskvantiteter överförs till huvudplanen när huvudplaneringen körs den 1 april. Som du ser har prognostransaktionerna i april minskats med efterfrågekvantiteten 240 i en sekvens, med början från den första av dessa transaktioner. Prognostransaktionerna för maj minskades med sammanlagt 210, från den första efterfrågeprognostransaktionen i maj. Summorna per period bevaras (400 i april och 300 i maj).

| Datum     | Obligatoriskt antal enheter |
|----------|---------------------------|
| 5 april  | 0                         |
| 12 april | 0                         |
| 19 april | 60                        |
| 26 april | 100                       |
| 27 april | 240                       |
| 3 maj    | 0                         |
| 4 maj    | 80                        |
| 10 maj   | 0                         |
| 11 maj   | 130                       |
| 17 maj   | 90                        |

#### <a name="transactions--dynamic-period"></a>Transaktions - dynamisk period

Om du väljer **transaktioner - dynamisk period** reduceras prognosbehoven av de faktiska ordertransaktioner som sker under en dynamisk period. Den dynamiska perioden omfattar de aktuella prognosdatumen och slutar i början av nästa prognos. I detta fall skapar huvudplaneringen planerade order för att tillhandahålla prognostiserade efterfrågan (prognosbehov). När de faktiska ordertransaktionerna placeras reduceras prognosbehoven. De faktiska transaktionerna förbrukar en del av det prognostiserade behovet.

När det här alternativet används, sker följande beteende:

- Reduceringsnycklar krävs eller används inte. 
- Om prognosen reduceras fullständigt, blir prognosbehoven för den aktuella prognosen 0 (noll).
- Om det inte finns någon framtida prognos, kommer prognosbehov från sista prognosen att reduceras.
- Tidsgränser ingår i prognosförminskningsberäkningen.
- Positiva dagar ingår i beräkningen av prognosreducering.
- Om verkliga ordertransaktioner överskrider prognosbehoven, förs resten av transaktionerna inte framåt till nästa prognosperiod.

##### <a name="example-1-transactions--dynamic-period"></a>Exempel 1: Transaktions - dynamisk period

Här ett enkelt exempel som visar hur metoden **transaktioner - dynamisk period** fungerar.

I det här exemplet inkluderar du följande efterfrågeprognos i en huvudplan.

| Datum       | Efterfrågeprognos |
|------------|-----------------|
| 1 januari  | 1 000           |
| 1 februari | 1 000             |

Du kan också skapa följande försäljningsorder.

| Datum        | Försäljningsorderns kvantitet |
|-------------|----------------------|
| 15 januari  | 200                  |
| 15 februari | 400                  |

I det här fallet skapas följande planerade order.

| Efterfrågeprognosdatum | Kvantitet | Förklaring                           |
|--------------------- |----------|---------------------------------------|
| 1 januari            | 800      | Prognosbehoven (= 1 000 - 200) |
| 15 januari           | 200      | Krav på försäljningsorder             |
| 1 februari           | 600      | Prognosbehoven (= 1 000 - 400) |
| 15 februari          | 400      | Krav på försäljningsorder             |

##### <a name="example-2-transactions--dynamic-period"></a>Exempel 2: Transaktions - dynamisk period

I de flesta fall ställs systemen in så att transaktioner minskar efterfrågeprognosen inom specifika detaljprognosperioder: veckor, månader och så vidare. Dessa perioder definieras i reduceringsnyckeln. Men tiden mellan två efterfrågeprognosrader kan också *antyda* en period.

I det här exemplet skapar du en efterfrågeprognos för följande datum och kvantiteter.

| Datum       | Efterfrågeprognos |
|------------|-----------------|
| 1 januari  | 1 000           |
| 5 januari  | 500             |
| 12 januari | 1 000           |

Observera att i den här prognosen finns det inte en tydlig period mellan prognosdatumen. Mellan de första och andra datumen är ett intervall med en tidsperiod på fyra dagar och mellan de andra och tredje datumet är ett intervall med sju dagar. Dessa tidsperioder är de dynamiska perioderna.

Du kan också skapa följande försäljningsorderrader.

| Datum                             | Försäljningsorderns kvantitet |
|----------------------------------|----------------------|
| 15 december föregående år | 500                  |
| 3 januari                        | 100                  |
| 10 januari                       | 200                  |

I det här fallet minskas prognosen på följande sätt:

- Eftersom den första försäljningsordern inte sker inom någon period, så den kommer inte att reducera prognosen.
- Eftersom den andra försäljningsordern sker mellan 1 januari och 5 januari, reducerar den prognosen för 1 januari med 100.
- Eftersom den tredje försäljningsordern sker mellan 5 januari och 12 januari, reducerar den prognosen för 5 januari med 200.

Därför skapas följande planerade order.

| Efterfrågeprognosdatum             | Kvantitet | Förklaring                                                         |
|----------------------------------|----------|---------------------------------------------------------------------|
| 15 december föregående år | 500      | Krav på försäljningsorder                                            |
| 1 januari                        | 900      | Prognosbehovperioden 1 januari till 5 januari (= 1 000 – 100) |
| 3 januari                        | 100      | Krav på försäljningsorder                                            |
| 5 januari                        | 300      | Prognosbehovperioden 5 januari till 10 januari (= 500 – 200)  |
| 12 januari                       | 1 000    | Prognosbehovperioden 12 januari till slutet                      |

### <a name="create-and-set-up-a-forecast-reduction-key"></a><a name="create-reduction-key"></a>Skapa och ställa in en prognosreduceringsnyckel

En prognosreduceringsnyckel används i metoderna **transaktioner - reduceringsnyckel** och **procent - reduceringsnyckel** för att minska prognosbehoven. Följ dessa steg om du vill skapa och ställa in en reduceringsnyckel.

1. Gå till **huvudplanering \> inställningar \> täckning \> reduceringsnycklar**.
2. Skapa en reduceringsnyckel genom att välja **Nytt**.
3. I fältet **reduceringsnyckeln** anger ett unikt ID för prognosreduceringsnyckeln. Ange sedan ett namn i fältet **Namn**. 
4. Definiera perioder och procentandel av reduktionsnyckel i varje period:

    - Fältet **giltighetsdatum** visar datumet då skapande av perioderna börjar. När alternativet **Använd giltighetsdatum** anges till **Ja** startar perioderna från giltighetsdatumet. När det anges till **Nej** startar perioderna på datumet då huvudplaneringen körs.
    - Definiera perioder då prognosreducering ska ske.
    - För en viss period anger du de procentsatser som prognosbehoven bör minskas med. Du kan ange positiva värden för att minska behov eller negativa värden att öka behov.

### <a name="use-a-reduction-key"></a><a name="use-reduction-key"></a>Använd en reduceringsnyckel

En prognosreduceringsnyckel måste tilldelas artikelns disponeringsgrupp. Följ dessa steg om du vill tilldela en reduceringsnyckel till artikelns disponeringsgrupp.

1. Gå till **huvudplanering \> inställningar \> täckning \> disponeringsgrupper**.
2. På snabbfliken **Övrigt** i fältet **reduceringsnyckel** väljer du reduceringsnyckeln som ska tilldelas disponeringsgruppen. Reduceringsnyckeln gäller för alla objekt som hör till disponeringsgruppen.
3. Om du vill använda en reduceringsnyckel för att beräkna prognosreducering under huvudplaneringen måste du definiera inställningen av prognosplanen eller huvudplanen. Gå till en av följande platser:

    - **Huvudplanering \> Inställning \> Planer \> Prognosplaner**
    - **Huvudplanering \> Inställningar \> Planer \> Huvudplaner**

4. På sidan **Prognosplaner** eller **Huvudplaner** på snabbfliken **Allmänt** i fältet **Metod som används för att minska prognosbehov** väljer du antingen **Procent - reduceringsnyckel** eller **transaktioner - reduceringsnyckel**.

### <a name="reduce-a-forecast-by-transactions"></a>Minska en prognos med transaktioner

När du väljer **transaktioner - reduceringsnyckel** eller **transaktioner - dynamisk period** som metod för att minska prognosbehoven kan du ange vilka transaktioner som reducerar prognosen. På sidan **Disponeringsgrupper** på transaktioner **Övrigt** i fältet **reducera prognos efter** väljer du **alla transaktioner** om alla transaktioner ska reducera prognosen eller **order** om bara försäljningsorder ska reducera prognosen.

## <a name="forecast-models-and-submodels"></a>Prognosmodeller med undermodeller

I det här avsnittet beskrivs hur du skapar prognosmodeller och hur du kombinerar flera prognosmodeller genom att ställa in delmodeller.

En *prognosmodell* namnger och identifierar en viss prognos. När du har skapat prognosmodellen kan du lägga till prognosrader i den. Om du vill lägga till prognosrader för flera artiklar använder du sidan **Efterfrågeprognosrader**. Om du vill lägga till prognosrader för en specifik vald artikel använder du sidan **Frisläppta produkter**.

En prognosmodell kan innehålla prognoser från andra prognosmodeller. För att uppnå detta resultat lägger du till andra prognosmodeller som *delmodeller* till en överordnad prognosmodell. Du måste skapa varje relevant modell innan du kan lägga till den som en delmodell till en överordnad prognosmodell.

Den resulterande strukturen ger dig ett kraftfullt sätt att kontrollera prognoser, eftersom du kan kombinera (aggregera) indata från flera enskilda prognoser. Från planeringssynpunkt är det därför enkelt att kombinera prognoser för simuleringar. Du kan till exempel ställa in en simulering som baseras på kombinationen av en vanlig prognos och prognosen för ett återkommande erbjudande.

### <a name="submodel-levels"></a>Delmodellnivåer

Det finns ingen gräns för hur många delmodeller som kan läggas till i en överordnad prognosmodell. Strukturen kan dock bara vara en nivå djup. Med andra ord kan en prognosmodell som är en delmodell till en annan prognosmodell inte ha sina egna delmodeller. När du lägger till delmodeller till en prognosmodell kontrollerar systemet om denna prognosmodell redan är en delmodell till en annan prognosmodell.

Om en delmodell med sina egna delmodeller påträffas i huvudplaneringen får du ett felmeddelande.

#### <a name="submodel-levels-example"></a>Exempel på delmodellnivåer

Prognosmodell A har prognosmodell B som delmodell. Därför kan prognosmodellen B inte ha sina egna delmodeller. Om du försöker lägga till en delmodell till prognosmodell B visas följande felmeddelande: "Prognosmodell B är en delmodell för modell A."

### <a name="aggregating-forecasts-across-forecast-models"></a>Sammanställa prognoser för flera prognosmodeller

Prognosrader som inträffar samma dag aggregeras över prognosmodellen och dess delmodeller.

#### <a name="aggregation-example"></a>Aggregering, exempel

Prognosmodell A har prognosmodeller B och C som delmodeller.

- Prognosmodell A innehåller en efterfrågeprognos för 2 enheter (delar) den 15 juni.
- Prognosmodell B innehåller en efterfrågeprognos för 3 enheter den 15 juni.
- Prognosmodell C innehåller en efterfrågeprognos för 4 enheter den 15 juni.

Den resulterande efterfrågeprognosen blir ett enda behov på 9 procent (2 + 3 + 4) den 15 juni.

> [!NOTE]
> Varje delmodell har egna parametrar och använder inte parameter av den överordnade prognosmodellen.

### <a name="create-a-forecast-model"></a>Skapa en prognosmodell

Gör så här om du vill skapa en prognosmodell.

1. Gå till **Huvudplanering \> Inställningar \> Efterfrågeprognosticering \> Prognosmodeller**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. Ställ in följande fält för den nya prognosmodellen:

    - **Modell** – Ange en unik identifierare för värderingsmodellen.
    - **Namn** – Ange ett beskrivande namn för modell.
    - **Stoppat** – Vanligtvis ska du ställa in detta alternativ till *Nej*. Ställ in *Ja* bara om du vill förhindra redigering av alla prognosrader som tilldelas modellen.

    > [!NOTE]
    > Fältet **Inkludera i kassaflödesprognoser** och fälten på **Projekt** hör inte till huvudplaneringen. Därför kan du ignorera dem i det här sammanhanget. Du måste endast ta hänsyn till dem när du arbetar med prognoser för modulen **Projekthantering och redovisning**.

### <a name="assign-submodels-to-a-forecast-model"></a>Tilldela undermodeller till en prognosmodell

Följ dessa steg för att tilldela undermodeller till en prognosmodell.

1. Gå till **Lagerhantering \> Inställningar \> Prognos \> Prognosmodeller**.
1. Välj den prognosmodell som du vill ställa in en undermodell för i listfönstret.
1. På snabbfliken **Delmodeller**, välj **Lägg till** om du vill lägga till rutnätet.
1. I den nya raden anger du följande fält:

    - **Delmodell** – Välj prognosmodellen som ska läggas till som delmodell. Prognosmodellen måste redan finnas och får inte ha några egna delmodeller.
    - **Namn** – Ange ett beskrivande namn för delmodell. Det här namnet kan till exempel indikera delmodellens relation till den överordnade prognosmodellen.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

