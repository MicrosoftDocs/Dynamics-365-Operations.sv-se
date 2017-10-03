---
title: Reduceringsnycklar
description: "Den här artikeln ger exempel som visar hur du ställer in en reduceringsnyckel. Den innehåller information om de olika reduceringsnyckelinställningarna och resultaten av varje nyckel. Du kan använda en reduceringsnyckel om du vill ange hur du ska minska prognosbehoven."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqPlanSched
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 19251
ms.assetid: aa9e0dfb-6052-4a2e-9378-89507c02fdf2
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: ce3ff2ac0a5bd9bd342baa05425d7d0957ab8a09
ms.contentlocale: sv-se
ms.lasthandoff: 05/25/2017

---

# <a name="reduction-keys"></a>Reduceringsnycklar

[!include[banner](../includes/banner.md)]


Den här artikeln ger exempel som visar hur du ställer in en reduceringsnyckel. Den innehåller information om de olika reduceringsnyckelinställningarna och resultaten av varje nyckel. Du kan använda en reduceringsnyckel om du vill ange hur du ska minska prognosbehoven.

<a name="example-1-percent---reduction-key-forecast-reduction-principle"></a>Exempel 1: Procent - reduceringsnyckel för prognosreduceringsprincip
---------------------------------------------------------------

Detta exempel visar hur en reduceringsnyckel reducerar behoven av efterfrågeprognos enligt procentsatserna och de perioder som definieras av reduceringsnyckeln.

1.  Ange följande rader på sidan **Reduceringsnycklar**.
    | Växel | Enhet  | Procent |
    |--------|-------|---------|
    | 1      | Månad | 100     |
    | 2      | Månad | 75      |
    | 3      | Månad | 50      |
    | 4      | Månad | 25      |

2.  Länka reduceringsnyckeln till artikelns täckningsgrupp.
3.  På sidan **Huvudplaner** i fältet **Reduceringsprincip** väljer du **Procent - reduceringsnyckel**.
4.  Skapa en efterfrågeprognos på 1 000 enheter per månad.

Om du kör prognosplanering den 1 januari förbrukas kraven på efterfrågeprognos enligt de procentsatser som du ställer in på sidan **Reduceringsnycklar**. Följande behovskvantiteter överförs till huvudplanen.

| Månad                | Obligatoriskt antal enheter |
|----------------------|---------------------------|
| Januari              | 0                         |
| Februari             | 250                       |
| Mars                | 500                       |
| april                | 750                       |
| Maj - december | 1 000                     |

## <a name="example-2-transactions--reduction-key-forecast-reduction-principle"></a>Exempel 2: Transaktioner - reduceringsnyckel för prognosreduceringsprincip
Detta exempel visar hur aktuella order som inträffar under de perioder som definieras av reduceringsnyckeln reducerar behoven av efterfrågeprognos.

-   På sidan **Huvudplaner** i fältet **Reduceringsprincip** väljer du **Transaktioner - reduceringsnyckel**.

Följande försäljningsorder finns den 1 januari.

| Månad    | Beställt antal enheter |
|----------|--------------------------|
| Januari  | 956                      |
| Februari | 1 176                    |
| Mars    | 451                      |
| april    | 119                      |

Med samma försäljningsprognos på 1 000 enheter per månad överförs följande behovskvantiteter till huvudplanen:

| Månad                | Obligatoriskt antal enheter |
|----------------------|---------------------------|
| Januari              | 44                        |
| Februari             | 0                         |
| Mars                | 549                       |
| april                | 881                       |
| Maj - december | 1 000                     |

## <a name="example-3-transactions--dynamic-period-forecast-reduction-principle"></a>Exempel 3: Transaktioner - dynamisk period för prognosreduceringsprincip
I de flesta fall ställs systemen in så att transaktioner minskar efterfrågeprognosen inom specifika detaljprognosperioder: veckor, månader och så vidare. Dessa perioder definieras i reduceringsnyckeln. Men tiden mellan två efterfrågeprognosrader kan också* antyda* en period.

1.  Skapa en efterfrågeprognos för följande datum och kvantiteter.
    | Datum       | Efterfrågeprognos |
    |------------|-----------------|
    | 1 januari  | 1 000           |
    | 5 januari  | 500             |
    | 12 januari | 1 000           |

    I denna prognos finns det inte en tydlig period mellan prognosdata: mellan de första och andra data finns det endast en tidsperiod på 4 dagar, och mellan de andra och tredje data finns det endast en tidsperiod på 1 dag. Dessa olika tidsperioder är de dynamiska perioderna.
2.  Skapa försäljningsorderrader enligt följande.
    | Datum                             | Försäljningsorderns kvantitet |
    |----------------------------------|----------------------|
    | 15 december föregående år | 500                  |
    | 3 januari                        | 100                  |
    | 10 januari                       | 200                  |

Prognosen reduceras enligt följande:

-   Den första försäljningsordern sker inte inom någon period, så den kommer inte att reducera prognosen.
-   Den andra försäljningsordern sker mellan 1 januari och 5 januari, så den ska reducera prognosen för 1 januari med 100.
-   Den tredje försäljningsordern sker mellan 5 januari och 12 januari, så den ska reducera prognosen för 5 januari med 200.

Följande planerade order skapas för att uppfylla prognosen.

| Efterfrågeprognosdatum | Reducerad kvantitet |
|----------------------|------------------|
| 1 januari            | 900              |
| 5 januari            | 300              |
| 12 januari           | 1 000            |

Här följer en sammanfattning av **Transaktioner - dynamisk period** för reducering:

-   Prognosbehoven reduceras med de verkliga ordertransaktionerna som inträffar under den dynamiska perioden. Den dynamiska perioden omfattar de aktuella prognosdatumen och slutar i början av nästa prognos.
-   Den här metoden använder inte eller kräver en reduceringsnyckel.
-   När det här alternativet används, sker följande beteende:
    -   Om prognosen reduceras fullständigt, blir prognosbehoven för den aktuella prognosen 0 (noll).
    -   Om det inte finns någon framtida prognos, kommer prognosbehov från sista prognosen att reduceras.
    -   Tidsgränser ingår i prognosförminskningsberäkningen.
    -   Positiva dagar ingår i beräkningen av prognosreducering.
    -   Om verkliga ordertransaktioner överskrider prognosbehoven, förs resten av transaktionerna inte framåt till nästa prognosperiod.


<a name="see-also"></a>Se även
--------

[Huvudplaner](master-plans.md)




