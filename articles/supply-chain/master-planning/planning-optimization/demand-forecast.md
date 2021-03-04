---
title: Huvudplanering med efterfrågeprognoser
description: I det här avsnittet beskrivs hur du inkluderar efterfrågeprognoser vid huvudplanering med planeringsoptimering.
author: ChristianRytt
manager: tfehr
ms.date: 12/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: MpsIntegrationParameters, MpsFitAnalysis
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-12-02
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 8b47aee41494394a32ffc0ea0c42a512e5051532
ms.sourcegitcommit: b86576e1114e4125eba8c144d40c068025f670fc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/03/2020
ms.locfileid: "4666732"
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

Om du väljer **Transaktioner - reduceringsnyckel** prognosbehoven reduceras av de transaktioner som genomförs under de perioder som definieras av reduceringsnyckeln.

##### <a name="example-transactions--reduction-key"></a>Exempel: Transaktioner - reduceringsnyckel

Detta exempel visar hur aktuella order som inträffar under de perioder som definieras av reduceringsnyckeln reducerar behoven av efterfrågeprognos.

I det här exemplet väljer du **Transaktionsplaner - reduceringsnyckel** i fältet **Metod som används för att minska prognosbehov** på sidan **Huvudplaner**.

Följande försäljningsorder finns den 1 januari.

| Månad    | Beställt antal enheter |
|----------|--------------------------|
| Januari  | 956                      |
| Februari | 1 176                    |
| Mars    | 451                      |
| april    | 119                      |

Med samma försäljningsprognos på 1 000 enheter per månad som användes i det föregående exemplet överförs följande behovskvantiteter till huvudplanen:

| Månad                | Obligatoriskt antal enheter |
|----------------------|---------------------------|
| Januari              | 44                        |
| Februari             | 0                         |
| Mars                | 549                       |
| april                | 881                       |
| Maj - december | 1 000                     |

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
2. Välj **ny** eller tryck på **Ctrl+N** för att skapa en reduceringsnyckel.
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

    - Huvudplanering \> Inställning \> Planer \> Prognosplaner
    - Huvudplanering \> Inställningar \> Planer \> Huvudplaner

4. På sidan **Prognosplaner** eller **Huvudplaner** på snabbfliken **Allmänt** i fältet **Metod som används för att minska prognosbehov** väljer du antingen **Procent - reduceringsnyckel** eller **transaktioner - reduceringsnyckel**.

### <a name="reduce-a-forecast-by-transactions"></a>Minska en prognos med transaktioner

När du väljer **transaktioner - reduceringsnyckel** eller **transaktioner - dynamisk period** som metod för att minska prognosbehoven kan du ange vilka transaktioner som reducerar prognosen. På sidan **Disponeringsgrupper** på transaktioner **Övrigt** i fältet **reducera prognos efter** väljer du **alla transaktioner** om alla transaktioner ska reducera prognosen eller **order** om bara försäljningsorder ska reducera prognosen.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]