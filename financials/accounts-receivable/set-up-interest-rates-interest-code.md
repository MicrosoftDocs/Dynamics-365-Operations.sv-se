---
title: "Ställa in räntesatser för en räntekod"
description: "Räntekoder innehåller inställningar som bestämmer när ränta debiteras och hur den beräknas på förfallna konton."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 59402
ms.assetid: 3b945333-1eaf-4658-ab5a-1a7791a7eb40
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 2cb439e871d57f74c296697cfc42705fb0121bb7
ms.openlocfilehash: 9656718d7afbcc6d89e650ab9379900c083507fe
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-interest-rates-for-an-interest-code"></a>Ställa in räntesatser för en räntekod

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
-   **Procent** har markerats ** ** i den **beräkna ränta baserat på** på den **Ställ in räntekoder** sida.

Exempelvis ställa in en räntekod som utvärderar 5 procents ränta för varannan månad att transaktionen överskrider för fakturans förfallodatum, skriver du 2 i den **beräkna ränta var** och välj **månad**.

## <a name="interest-rates-based-on-amounts"></a>Räntesatser baserade på belopp
Du kan ställa in räntesatser för att beräkna ett angivet belopp per valuta.
-   Ett räntebelopp anges för varje valuta i räntekoden.
-   Valfria räntebeloppsgränser kan anges.
-   ** Belopp ** väljs i den **beräkna ränta baserat på** på de **Ställ in räntekoder** sida.

Exempelvis ställa in en räntekod som utvärderar 25,00 intresse för varje 20 dagar att transaktionen överskrider för fakturans förfallodatum, skriver du 20 i den **beräkna ränta var** och välj **dag**.

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

| **From value** | **Interest value** |
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

| **From value** | **Interest value** |
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

| **From value** | **Interest value** |
|----------------|--------------------|
| 0              | 1.5                |
| 4              | 2                  |
| 7              | 2,5                |

## <a name="new-versions"></a>Nya versioner
Räntekoder har giltighetsdatum. Om du vill ändra räntesatsen kan du skapa en **ny version** som gäller för ett framtida datum.

Om du vill visa andra versioner kan du använda menyvalet **Från och med (datum)** för att välja slutdatumet. Du kan också markera **Visa alla poster** för att visa alla räntekoder på sidan.


