---
title: "Ställa in räntesatser för en räntekod"
description: "Räntekoder innehåller inställningar som bestämmer när ränta debiteras och hur den beräknas på förfallna konton."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: Interest
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 59402
ms.assetid: 3b945333-1eaf-4658-ab5a-1a7791a7eb40
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 7ae0bfdc157a7e2e5b9f871dae487a6f85e889b9
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="set-up-interest-rates-for-an-interest-code"></a>Ställa in räntesatser för en räntekod

[!include[banner](../includes/banner.md)]


Räntekoder innehåller inställningar som bestämmer när ränta debiteras och hur den beräknas på förfallna konton.

Du kan ställa in en enskild räntekod och använda den till flera bokföringsprofiler för kunder och faktureringskoder eller för specifika fakturarader. När räntekoddetaljerna ändras kommer alla funktioner som använder koden att införa ändringarna automatiskt i nya transaktioner. För varje räntekod kan du ställa in två typer av satser:
-   Satser för ränteintäkter − dessa representerar intäkt som erhållits genom att debitera ränta på fakturor, eller räntefakturor.
-   Satser för räntebetalningar − dessa representerar en kostnad som betalas för ränta på kreditfakturor.

Båda av följande satstyper kan finnas samtidigt och med samma räntekod. Räntesatser kan baseras på tre beräkningstyper:
-   Ränta i procent.
-   Ränta i belopp.
-   Ränta per intervall, vilket resulterar i en enskild procentandel eller belopp.

När en räntekod används för beräkning av räntan skapas en separat räntefaktura för varje räntesats som gäller under den tid som betalningen har överskridit transaktionens förfallodatum. Du använder fliken **Resultaten** på sidan **Räntekod** för att ställa in räntesatser för ränta som du till exempel tjänar genom att debitera ränta. Använd fliken **Betalningar** om du vill ställa in räntesatser för ränta som du betalar.

## <a name="interest-rates-based-on-a-percentage"></a>Räntesatser baserat på procentsats
Du kan ställa in räntesatser för att beräkna en viss procent.

-   Räntebeloppet gäller för alla valutor.
-   Valfria räntebeloppsgränser kan anges.
-   **Procent** väljs** **i fältet **Beräkna ränta baserat på** på sidan **Ställ in räntekoder**.

Om du till exempel vill ställa in en räntekod som värderas med 5 procent ränta för varje tvåmånadersperiod som överskrider fakturans förfallodatum för transaktionen, ska du ange 2 i fältet **Beräkna ränta var** och välja **Månad**.

## <a name="interest-rates-based-on-amounts"></a>Räntesatser baserade på belopp
Du kan ställa in räntesatser för att beräkna ett angivet belopp per valuta.
-   Ett räntebelopp anges för varje valuta i räntekoden.
-   Valfria räntebeloppsgränser kan anges.
-   **Belopp **väljs i fältet **Beräkna ränta baserat på** på sidan **Ställ in räntekoder**.

Om du till exempel vill ställa in en räntekod som värderas med 25,00 ränta för varje 20-dagarsperiod som överskrider fakturans förfallodatum för transaktionen, ska du ange 20 i fältet **Beräkna ränta var** och välj **Dag**.

## <a name="interest-rates-based-on-ranges"></a>Räntesatser baserade på perioder
Du kan ställa in räntesatser som varierar beroende på det förfallna beloppet, antalet dagar som beloppet är försenat eller antalet månader som beloppet är försenat.
-   Du kan använda fliken **Resultaten per valuta** för att ange särskilda ränteinställningar för varje valuta. Det är också där du definierar intervallet.
-   Använd knappen **Intervall** om du vill lägga till rader som motsvarar intervall som du vill ställa in. Värdet **Från** representerar starttiden för intervallet och talet **Räntevärde** representerar antingen ett procenttal eller ett belopp, beroende på valet i fältet **Beräkna ränta baserat på** på sidan **Ställ in räntekoder**.

## <a name="example-1-interest-by-range--amount"></a>Exempel 1: Ränta efter period = Belopp
Du kan ställa in en räntekod som beräknar ränta en gång var tredje månad som överskrider fakturans förfallodatum för transaktionen. Du ska basera beräkningen på ett procentuellt räntevärde, efter stegvisa beloppsintervall. Räntevärdet ska vara 1 procent för fakturabelopp upp till 1.000,00, 2 procent för belopp från 1.001,00 till 5.000,00 och 3 procent för större än 5.000,00. Du ställer in räntekodfältvärdena på följande sätt.

| **Fältnamn**                  | **Fältvärde** |
|---------------------------------|-----------------|
| **Räntekod**               | 3M%ByAmt        |
| **Beräkna ränta var**    | 3/månad         |
| **Ränta per intervall**           | Belopp          |
| **Beräkna ränta baserat på** | Procent      |

Du ställer in information om intervall så här.

| **Från-värde** | **Räntevärde** |
|----------------|--------------------|
| 0              | 1                  |
| 1,001          | 2                  |
| 5,001          | 3                  |

 
## <a name="example-2-interest-by-range--days"></a>Exempel 2: Ränta efter period = Dagar
--------------------------------------------------

Du kan ställa in en räntekod som beräknar ränta en gång för varje 15 dagar som överskrider fakturans förfallodatum för transaktionen. Du ska basera beräkningen på ett räntevärde för ett belopp, efter stegvisa dagsintervall. Räntavärdet blir 10,00 per 15 dagar under de första 60 dagar, 15,00 dagar per 15 dagar under 61 till 90 och 20,00 per 15 dagar från dag 91 och ska. Du ställer in räntekodfältvärdena på följande sätt.

| **Fältnamn**                  | **Fältvärde** |
|---------------------------------|-----------------|
| **Räntekod**               | 15DAmtXDay      |
| **Beräkna ränta var**    | 15/dag          |
| **Ränta per intervall**           | Dagar            |
| **Beräkna ränta baserat på** | Belopp          |

Du ställer in information om intervall så här.

| **Från-värde** | **Räntevärde** |
|----------------|--------------------|
| 0              | 10                 |
| 61             | 15                 |
| 91             | 20                 |

 
## <a name="example-3-interest-by-range--months"></a>Exempel 3: Ränta efter period = Månader
----------------------------------------------------

Du kan ställa in en räntekod som beräknar ränta en gång för varje månad som överskrider fakturans förfallodatum för transaktionen. Du ska basera beräkningen på ett procentuellt räntevärde, efter stegvisa månadsintervall. Räntevärdet ska vara 1,5 procent per månad för de första tre förfallna månaderna, 2,0 procent per månad för nästa tre månader och 2,5 procent per månad för varje månad efter det första halvåret. Du ställer in räntekodfältvärdena på följande sätt.

| **Fältnamn**                  | **Fältvärde** |
|---------------------------------|-----------------|
| **Räntekod**               | 1M%ByMth        |
| **Beräkna ränta var**    | 1/månad         |
| **Ränta per intervall**           | Månader          |
| **Beräkna ränta baserat på** | Procent      |

Du ställer in information om intervall så här.

| **Från-värde** | **Räntevärde** |
|----------------|--------------------|
| 0              | 1.5                |
| 4              | 2                  |
| 7              | 2,5                |

## <a name="new-versions"></a>Nya versioner
Räntekoder har giltighetsdatum. Om du vill ändra räntesatsen kan du skapa en **ny version** som gäller för ett framtida datum.

Om du vill visa andra versioner kan du använda menyvalet **Från och med (datum)** för att välja slutdatumet. Du kan också markera **Visa alla poster** för att visa alla räntekoder på sidan.




