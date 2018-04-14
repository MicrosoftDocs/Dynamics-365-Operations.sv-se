---
title: Allokeringsunderlag
description: "Det här ämnet innehåller information om allokeringsunderlag. Allokeringsunderlag används oftast för att fördela omkostnader är viktiga komponenter i kostnadsredovisning."
author: AndersGirke
manager: AnnBe
ms.date: 05/24/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CAMDimensionMember
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 223174
ms.assetid: 
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 63f39a6c06a0c6b5df901f7aa4235aab3c4ac06e
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="allocation-bases"></a>Allokeringsunderlag 

[!INCLUDE [banner](../includes/banner.md)]

Ett allokeringsunderlag är baseen som redovisning fördelar omkostnader på. Ett allokeringsunderlag kan vara en kvantitet som t.ex. maskintimmar som används, kilowattimmar (kWh) som förbrukas eller kvadratmeteryta som ockuperas. Allokeringsunderlag används oftast för att tilldela omkostnader till lager som produceras. Till exempel fördelar IT-avdelningen sina utgifter enligt antalet datorer som varje avdelning använder.

Det finns tre typer av allokeringsunderlag i kostnadsredovisning:

- Fördefinierad dimensionsmedlem för allokeringsunderlag
- Allokeringsunderlag för hierarki
- Formelallokeringsunderlag

## <a name="predefined-dimension-member-allocation-bases"></a>Fördefinierad dimensionsmedlem för allokeringsunderlag

De fördefinierade dimensionsmedlem för allokeringsunderlag skapas automatiskt när en dimensionsmedlem i en följande typer skapas:

- Statistikdimensionsmedlemmar
- Dimensionsmedlemmar för kostnadselement

> [!NOTE]
> Fördefinierad dimensionsmedlem för allokeringsunderlag som baseras på en dimensionsmedlem för kostnadselement beaktar endast värdena från datakällaprovidern som till exempel redovisnings- och budgettransaktionerna.

### <a name="example-1-use-a-cost-element-dimension-member-as-the-allocation-base"></a>Exempel 1: Använd en dimensionsmedlem för kostnadselement som allokeringsunderlag
Exemplet visar hur du skapar en kostnadsallokeringsregel för att allokera kostnaselement 10002 (försäkring för medarbetare) till det saldo som registreras på kostnadselement 10001 (löner). Allokeringsregeln definieras utifrån förhållandet mellan avdelningarnas löner till totala löner. (Granskning behövs!)

I redovisningen anges kontoplanen på följande sätt.

| Kontoplan | Huvudkonto | beskrivning        | Huvudkontotyp |
|------------------|--------------|--------------------|-------------------|
| Delade           | 10001        | Löner           | Utgift           |
| Delade           | 10002        | Försäkring för medarbetare | Utgift           |

Definiera en dimension för kostnadselement och konfigurera datakoppling. När data har importerats skapas följande poster i kostnadsredovisning.

**Dimensionsmedlemmar för kostnadselement**

| Namn på dimension för kostnadselement | Kostnadselement |  beskrivning       | Typ    |
|-----------------------------|--------------|--------------------|---------|
| Kostnadselement               | 10001        | Löner           | Primär |
| Kostnadselement               | 10002        | Försäkring för medarbetare | Primär |

**Fördefinierad dimensionsmedlem för allokeringsunderlag** 

| Namn  | beskrivning        | Dimension för kostnadselement |
|-------|--------------------|------------------------|
| 10001 | Löner           | Kostnadselement          |
| 10002 | Försäkring för medarbetare | Kostnadselement          |

Följande transaktioner har bokförts i redovisningen:

- Posterna som visar huvudkontot för löner hämtas från lönesystemet och bokförs till kostnadsställen.
- Utgiften för medarbetares försäkring bokförs manuellt på ett standardkostnadsställe.

| Räkenskapsdatum | Kostnadsställe |  beskrivning        | Huvudkonto |  beskrivning       | Belopp i redovisningsvaluta |
|-----------------|-------------|---------------------|--------------|--------------------|-------------------------------|
| 03-01-2017      | CC001       | Personal                  | 10001        | Löner           | 2 000,00                      |
| 03-01-2017      | CC002       | FI                  | 10001        | Löner           | 5 000,00                      |
| 03-01-2017      | CC003       | LÖ                  | 10001        | Löner           | 3 000,00                      |
| 03-01-2017      | CC099       | Standardkostnadscenter | 10002        | Försäkring för medarbetare | 1 000,00                      |

När redovisningens källdata har behandlats, skapas följande poster i kostnadsredovisning.

**Kostnadsposter**

| Kostnadsobjekt |  beskrivning        | Kostnadselement  |  beskrivning       | Kostnadsbeteende   |Belopp|Räkenskapsdatum|
|-------------|---------------------|---------------|--------------------|-----------------|------|---------------|
| CC001       | Personal                  | 10001         | Löner           | Oklassificerade    |2 000,00|  03-01-2017    |
| CC002       | FI                  | 10001         | Löner           | Oklassificerade    |5 000,00|     03-01-2017         |
| CC003       | LÖ                  | 10001         | Löner           | Oklassificerade    |3 000,00|      03-01-2017        |
| CC099       | Standardkostnadscenter | 10002         | Försäkring för medarbetare | Oklassificerade    |1 000,00|      03-01-2017       |

I detta förenklade exempel skapas en kostnadsallokeringsregel för att allokera kostnadselement 10002 (försäkring för medarbetare) relaterat till det saldo som registreras på kostnadselement 10001 (löner).

**Kostnadsfördelningsregel**

| Dimensionshierarkinod för kostnadsobjekt | Dimensionshierarkinod för kostnadselement | Kostnadsbeteende | Allokeringsunderlag |
|--------------------------------------|---------------------------------------|---------------|-----------------|
| CC099                                | 10002                                 | Oklassificerade  | 10001           |

**Utföra beräkning av indirekta kostnader**

När kostnadselement 10001 (löner) används som allokeringsunderlag, är resultatet av beräkning av indirekta kostnader följande.

| Kostnadsobjekt | beskrivning | Storlek |   Allokeringsfaktor         | Belopp |
|-------------|-------------|-----------|-----------------------------|--------|
| CC001       | Personal          | 2 000     | (2 000 ÷ 10 000) × 1 000,00 | 200,00 |
| CC002       | FI          | 5 000     | (5 000 ÷ 10 000) × 1 000,00 | 500.00 |
| CC003       | LÖ          | 3 000     | (3 000 ÷ 10 000) × 1 000,00 | 300,00 |

**Journal**

| Journal | Journaltyp                          | Räkenskapskalenderperiod | År | Period   | Version                                                                 |
|---------|---------------------------------------|------------------------|------|----------|-------------------------------------------------------------------------|
| 00001   | Beräkningsjournal för kostnadsfördelning | Skatt                 | 2017 | Period 1 | Beräkning av indirekta kostnader/2017-02-01 23:51:00/redovisning/2017/period 1 |

**Journalposter för kostnadsobjektsaldo**

| Räkenskapsdatum | Kostnadsobjekt | beskrivning         | Kostnadselement | beskrivning        | Kostnadsbeteende |  Belopp  |
|-----------------|-------------|---------------------|--------------|--------------------|---------------|----------|
| 31-01-2017      | CC099       | Standardkostnadscenter | 10002        | Försäkring för medarbetare | Oklassificerade  | 1 000,00 |

**Kostnadsposter**

| Kostnadsobjekt |  beskrivning        | Kostnadselement |    beskrivning     | Kostnadsbeteende | Belopp    | Räkenskapsdatum |
|-------------|---------------------|--------------|--------------------|---------------|-----------|-----------------|
| CC099       | Standardkostnadscenter | 10002        | Försäkring för medarbetare | Oklassificerade  | -1 000,00 | 31-01-2017      |
| CC001       | Personal                  | 10002        | Försäkring för medarbetare | Oklassificerade  | 200,00    | 31-01-2017      |
| CC002       | FI                  | 10002        | Försäkring för medarbetare | Oklassificerade  | 500.00    | 31-01-2017      |
| CC099       | LÖ                  | 10002        | Försäkring för medarbetare | Oklassificerade  | 300,00    | 31-01-2017      |

### <a name="example-2-use-a-statistical-dimension-member-as-the-allocation-base"></a>Exempel 2: Använd en statistisk dimensionsmedlem som allokeringsunderlag

Statistiska dimensionsmedlemmar kan användas som allokeringsunderlag för att definiera policyer eller rapportera icke-monetär förbrukning efter kostnadsobjekt. Du kan manuellt skapa statistiska dimensionsmedlemmar eller importera dem från en fil med hjälp av verktyget Importera/exportera för datahantering.

**Statistikdimensionsmedlemmar**

| Statistikdimensionsnamn | Statistiskt element | beskrivning               | Enhet |
|----------------------------|---------------------|---------------------------|------|
| Statistiska element       | FTE                 | Heltidsmedarbetare       | Ea   |
| Statistiska element       | Elektricitet         | Elförbrukning   | Kwh  |

När en statistikdimensionsmedlem sparas skapas en motsvarande post i fördefinierade allokeringsunderlag för dimensionsmedlem.

**Fördefinierad dimensionsmedlem för allokeringsunderlag**

| Namn        | beskrivning             | Dimensioner för statistika element |
|-------------|-------------------------|-------------------------------|
| FTE         | Heltidsmedarbetare     | Statistiska element          |
| Elektricitet | Elförbrukning | Statistiska element          |

Statistiskt mått kan komma från olika källor:

- Elförbrukningen kan mätas med kvadratmeter som installeras i olika områden i företaget.
- Register innehåller statistiska mätningar. T.ex. registret HcmEmployment innehåller en lista över alla medarbetare och de kostnadsställen de arbetar på.

| Namn       | Kostnadsställe |  beskrivning  | Typ av arbetare |
|------------|-------------|----|-------------|
| Medarbetare A | CC001       | Personal | Medarbetare    |
| Medarbetare B | CC002       | FI | Medarbetare    |
| Medarbetare C | CC002       | FI | Medarbetare    |
| Medarbetare D | CC003       | LÖ | Medarbetare    |
| Medarbetare F | CC003       | LÖ | Medarbetare    |

> [!NOTE]
> Alla register som innehåller ekonomiska dimensioner kan användas som källa för statistikändamål.

Kostnadsredovisning stöder en uppsättning statistikändamål genom att använda följande dataanslutningar:

- Datahanteringsverktyget Importera och exportera
- Statistiska mätningar

Om du vill göra statistiska mätningarna från systemet krävs en providermall för statistiska mätningar. Mer information finns i providermallar för statistisk mätning (Lägger till en länk när det här avsnittet skrivs.)

**Providermallar för statistiska mätningar**

| Namn  | Funktion | Källregister  | Summafält      | Datumfält     |
|-------|----------|---------------|----------------|----------------|
| FTE:s | Antal    | HcmEmployment | Inte tillämpligt | Inte tillämpligt |

När källdata för statistiska mätningar har behandlats, skapas följande poster i kostnadsredovisning.

**Statistikposter**

| Kostnadsobjekt | beskrivning      | Räkenskapsdatum | Statistikdimensionsmedlem | beskrivning         | Storlek |
|-------------|------------------|-----------------|------------------------------|---------------------|-----------|
| CC001       | Personal               | 31-01-2017      | FTE:s                        | Heltidsmedarbetare | 1,00      |
| CC002       | FI               | 31-01-2017      | FTE:s                        | Heltidsmedarbetare | 2.00      |
| CC003       | LÖ               | 31-01-2017      | FTE:s                        | Heltidsmedarbetare | 2.00      |

Här är ett exempel på en kostnadsfördelningsregel om FT:s fördefinierade dimensionsmedlem för allokeringsunderlag tilldelas som fördelningsbasen där.

| Kostnadsobjekt | beskrivning  | Storlek | Allokeringsfaktor |
|-------------|------|-----------|-------------------|
| CC001       | Personal   | 1,00      | (1/5) × belopp    |
| CC002       | FI   | 2.00      | (2/5) × belopp    |
| CC003       | LÖ   | 2.00      | (2/5) × belopp    |

Du kan använda dataentiteten importerade statistiska mätningar för att importera statistiska mätningar i kostnadsredovisning. Du kan också använda Datahanteringsverktyget Importera och exportera I Excel registreras elförbrukningen på följande sätt.

| Räkenskapsdatum | Dimensionsmedlem | Storlek | Identifierare för källa |
|-----------------|------------------|-----------|-------------------|
| 31-01-2017      | CC001            | 2,450.00  | Elektricitet       |
| 2017-01-31      | CC002            | 4,100.00  | Elektricitet       |
| 31-01-2017      | CC003            | 15,000.00 | Elektricitet       |

När källdata för statistiska mätningar har behandlats, skapas följande poster i kostnadsredovisning.

**Statistikposter**

| Kostnadsobjekt |    | Räkenskapsdatum | Statistikdimensionsmedlem |    beskrivning          | Storlek |
|-------------|----|-----------------|------------------------------|-------------------------|-----------|
| CC001       | Personal | 31-01-2017      | Elektricitet                  | Elförbrukning | 2,450.00  |
| CC002       | FI | 31-01-2017      | Elektricitet                  | Elförbrukning | 4,100.00  |
| CC003       | LÖ | 31-01-2017      | Elektricitet                  | Elförbrukning | 15,000.00 |

Här är ett exempel på en kostnadsfördelningsregel om electricitetens fördefinierade dimensionsmedlem för allokeringsunderlag tilldelas som fördelningsbasen där.

| Kostnadsobjekt | beskrivning  | Storlek | Allokeringsfaktor          |
|-------------|------|-----------|----------------------------|
| CC001       | Personal   | 2,450.00  | (2 450 ÷ 21 550) × belopp  |
| CC002       | FI   | 4,100.00  | (4 100 ÷ 21 550) × belopp  |
| CC003       | LÖ   | 15,000.00 | (15 000 ÷ 21 550) × belopp |

## <a name="hierarchy-allocation-bases"></a>Allokeringsunderlag för hierarki

Kostnadsrevisorer kan manuellt skapa allokeringsunderlag för hierarki genom att använda en befintlig dimensionshierarkinod för kostnadsobjekt till ett befintligt allokeringsunderlag. På så sätt kan du begränsa intervallet för den ursprungliga fördefinierade dimensionsmedlem för allokeringsunderlag. En fördefinierad dimensionsmedlem för allokeringsunderlag kan användas för att skapa flera allokeringsunderlag för hierarki. Intervallen kan hållas i den dimensionshierarki för kostnadsobjekt som associeras med allokeringsunderlaget för hierarki.

### <a name="example-hierarchy-allocation-bases-that-are-based-on-full-time-employees-in-the-organization"></a>Exempel: Allokeringsunderlag för hierarki som baseras på heltidsanställda medarbetare i organisationen
Här följer ett exempel på en dimensionshierarki för kostnadsobjekt som kan skapas för att beskriva en förenklad organisation.

| Hierarkinamn | Nodnivå 0 | Nodnivå 1 | Nodnivå 2 | Dimensionsmedlemmar |
|----------------|--------------|--------------|--------------|-------------------|
| Organisation   | VD          | CFO          | FICO         | CC001             |
| Organisation   | VD          | CFO          | Personal           | CC002             |
| Organisation   | VD          | CIO          | LÖ           | CC003             |

FTE:s fördefinierade dimensionsmedlem för allokeringsunderlag som skapades i tidigare avsnitt innefattar följande poster.

**Statistikposter**

| Kostnadsobjekt | beskrivning  | Räkenskapsdatum | Statistikdimensionsmedlem | beskrivning | Storlek |
|-------------|------|-----------------|------------------------------|---------------------|-----------|
| CC001       | Personal   | 31-01-2017      | FTE:s                        | Heltidsmedarbetare | 1,00      |
| CC002       | FI   | 31-01-2017      | FTE:s                        | Heltidsmedarbetare | 2.00      |
| CC003       | LÖ   | 31-01-2017      | FTE:s                        | Heltidsmedarbetare | 2.00      |

En kostnad måste fördelas mellan kostnadsställen som rapporteras till företagets ekonomichef (CFO). Det bekräftas att rätt fördelningskvot är antalet heltidsanställda (FTS) per kostnadsställe.

**Allokeringsunderlag för hierarki**

| Namn                  | Allokeringsunderlag | Dimensionshierarki för kostnadsobjekt | Dimensionshierarkinod för kostnadsobjekt |
|-----------------------|-----------------|---------------------------------|--------------------------------------|
| Antal heltidsanställda inom ekonomi | FTE:s           | Organisation                    | CFO                                  |

En funktion för förhandsgranskning låter dig validera allokeringsbasen för hierarki som skapas utifrån statistiska transaktioner i systemet.

**Information om allokeringsunderlag**

| Kostnadsobjekt | beskrivning  |  Storlek |
|-------------|------|------------|
| CC001       | Personal   | 1,00       |
| CC002       | FI   | 2.00       |

Här är ett exempel på en kostnadsfördelningsregel om antal FTE:s i CFO:s allokeringsunderlag för hierarki som tilldelas som allokeringsunderlaget där.

| Kostnadsobjekt | beskrivning  | Storlek | Allokeringsfaktor |
|-------------|------|-----------|-------------------|
| CC001       | Personal   | 1,00      | (1/3) × belopp    |
| CC002       | FI   | 2.00      | (2/3) × belopp    |

## <a name="formula-allocation-bases"></a>Formelallokeringsunderlag

Formelallokeringsunderlag låter dig definiera avancerade formler för att uppnå rätt allokeringsbas. Du kan manuellt skapa formelallokeringsunderlag.

När du skapar ett formelallokeringsunderlag väljer du den statistiska dimension och kostnadselementdimension som ska vara grunden för formeln. Alla allokeringsunderlag som kommer från tidigare valda dimensioner kan användas i ett formelallokeringsunderlag.

> [!NOTE]
> Tidigare definierade formelallokeringsunderlag kan användas för att definiera ett nytt formelallokeringsunderlag.

I faktorer om formelallokeringsunderlag skapar du ett alias och associerar det med antingen ett allokeringsunderlag eller en konstant. Alias används sedan för att ange formeln.

Du kan använda följande operatorer för att ange formeln.

| Symboler | Text           |
|---------|----------------|
| ( )     | Parenteser    |
| \<      | Mindre än   |
| \>      | Större än    |
| +       | Tillägg       |
| –       | Subtraktion    |
| \*      | Multiplikation |

Traditionella **IF**-rapporter stöds inte. Du kan emellertid skapa rapporter och kontrollera om de är sanna.

| Kontoutdrag | Validering | Resultat |
|-----------|------------|--------|
| a \> b    | Sant       | 1      |
| a \> b    | Falskt      | 0      |

### <a name="example-1-a-simple-formula"></a>Exempel 1: En enkel formel

Elräkningar består ofta av två delar:

- En fast avgift för att vara ansluten till nätet
- En kostnad som är kopplad till förbrukning per kWh

Den fördefinierade dimensionsmedlemmen för allokeringsunderlag El har redan definierats och innehåller dessa värden.

**Statistikposter**

| Kostnadsobjekt | Namn | Räkenskapsdatum | Statistikdimensionsmedlem | beskrivning             | Storlek |
|-------------|------|-----------------|------------------------------|-------------------------|-----------|
| CC001       | Personal   | 31-01-2017      | Elektricitet                  | Elförbrukning | 2,450.00  |
| CC002       | FI   | 31-01-2017      | Elektricitet                  | Elförbrukning | 4,100.00  |
| CC003       | LÖ   | 31-01-2017      | Elektricitet                  | Elförbrukning | 15,000.00 |

Om den fasta avgiften nu måste spridas jämnt över kostnadsobjekt som förbrukar el, har du två alternativ för att allokera kostnaderna:

- Skapa ett nytt fördefinierat allokeringsunderlag, fast el, och tillämpa ett statistiskt mått på 1,00 för varje kostnadsobjekt som förbrukat el.
- Skapa en formelallokeringsunderlag, fast el, som utnyttjar den fördefinierade dimensionsmedlemmen för allokeringsunderlag El som redan har definierats i systemet. Fördelen med det här alternativet är att data måste läsas in i kostnadsredovisning för endast en statistikdimensionsmedlem för El.

**Formelallokeringsunderlag** 

| Namn              | Dimension för kostnadselement | Statistikdimension | Formel |
|-------------------|------------------------|-----------------------|---------|
| Fast el |                        | Statistiska element  |         |

Innan fältet **formel** kan fyllas i måste du ange det alias som ska användas i formeln.

**Formelfaktorer för allokeringsunderlag**

| Alias | Konstant | Allokeringsunderlag |
|-------|----------|-----------------|
| a     |          | Elektricitet     |
| b     | 0,01     |                 |

Observera att 0 (noll) inte stöds som en konstant.

**Formelallokeringsunderlag**

| Namn              | Dimension för kostnadselement | Statistikdimension | Formel |
|-------------------|------------------------|-----------------------|---------|
| Fast el |                        | Statistiska element  | a \> b  |

En funktion för förhandsgranskning låter dig validera formelallokeringsbasen för hierarki som skapas utifrån statistiska transaktioner i systemet.

**Information om allokeringsunderlag**

| Kostnadsobjekt | beskrivning  | Formel           | Storlek |
|-------------|------|-------------------|-----------|
| CC001       | Personal   | 2.450,00 \> 0,01  | 1,00      |
| CC002       | FI   | 4.100,00 \> 0,01  | 1,00      |
| CC003       | LÖ   | 15.000,00 \> 0,01 | 1,00      |

Här är ett exempel på en kostnadsfördelningsregel om formelallokeringsunderlaget för El tilldelas som allokeringsunderlage i det.

**Allokeringsfaktor för kostnadsobjektstorlek**

| Kostnadsobjekt | Namn | Storlek |  Allokeringsfaktor |
|-------------|------|-----------|--------------------|
| CC001       | Personal   | 1,00      | (1/3) × belopp     |
| CC002       | FI   | 1,00      | (1/3) × belopp     |
| CC003       | LÖ   | 1,00      | (1/3) × belopp     |

### <a name="example-2-an-advanced-formula"></a>Exempel 2: En avancerad formel
I det här exemplet bör elkostnaderna inte bara följa den faktiska elen som förbrukas i kWh. Ledningen vill inkludera incitament för att minska elförbrukningen. 

| Regel              | Kurs | 
|-------------------|------|
| a <= 10 000,00 kWh | 0.75 |
| a >10 000,00 kWh  | 1.15 |

Ett nytt formelallokeringsunderlag, Elförbrukning, skapas.

**Formelallokeringsunderlag**

| Namn              | Dimension för kostnadselement | Statistikdimension | Formel |
|-------------------|------------------------|-----------------------|---------|
| Elförbrukning |                        | Statistiska element  |         |

Innan fältet **formel** kan fyllas i måste du ange det alias som ska användas i formeln.

**Formelfaktorer för allokeringsunderlag**

| Alias | Konstant  | Allokeringsunderlag |
|-------|-----------|-----------------|
| a     |           | Elektricitet     |
| b     | 10 000,00 |                 |
| c     | 0.75      |                 |
| d     | 1.15      |                 |

**Formelallokeringsunderlag**

| Namn              | Dimension för kostnadselement | Statistikdimension | Formel                                                    |
|-------------------|------------------------|-----------------------|------------------------------------------------------------|
| Fast el |                        | Statistiska element  | ((a \> b) × ((b × c) + (a – b) × d)) + ((a \<= b] × a × c) |

En funktion för förhandsgranskning låter dig validera formelallokeringsbasen för hierarki som skapas utifrån statistiska transaktioner i systemet.

**Information om allokeringsunderlag**

| Kostnadsobjekt |    | Formel                                                                                                                             | Storlek |
|-------------|----|-------------------------------------------------------------------------------------------------------------------------------------|-----------|
| CC001       | Personal | ((2 450,00 \> 10 000,00) × ((10 000,00 × 0,75) + (2 450,00 – 10 000,00) × 1,15)) + ((2 450,00 \<= 10 000,00) × 2 450,00 × 0,75)     | 1,837.50  |
| CC002       | FI | ((2 450,00 \> 10 000,00) × ((10 000,00 × 0,75) + (2 450,00 – 10 000,00) × 1,15)) + ((2 450,00 \<= 10 000,00) × 2 450,00 × 0,75)     | 3,075.00  |
| CC003       | LÖ | ((2 450,00 \> 10 000,00) × ((10 000,00 × 0,75) + (2 450,00 – 10 000,00) × 1,15)) + ((2 450,00 \<= 10 000,00) × 2 450,00 × 0,75) | 1,3250.00 |

Det är en nrmare titt på formeln CC003 (IT):

((15 000,00 \> 10 000,00) × ((10 000,00 × 0,75) + (15 000,00 – 10 000,00) × 1,15)) + ((15 000,00 \<= 10 000,00) × 15 000,00 × 0,75) = 13 250,00

(1 × (7 500,00 + 5 000,00 × 1,15)) + (0 × 15 000,00 × 0,75)            

1 × 7 500,00 + 5 750,00 + 0 

Här är ett exempel på en kostnadsfördelningsregel om formelallokeringsunderlaget för Fast el tilldelas som allokeringsunderlage i det.


| Kostnadsobjekt | beskrivning | Storlek |        Allokeringsfaktor         |
|-------------|-------------|-----------|----------------------------------|
|    CC001    |     Personal      | 1,837.50  | (1 837,50 ÷ 18 162,50) × belopp  |
|    CC002    |     FI      | 3,075.00  | (3 075,00 ÷ 18 162,50) × belopp  |
|    CC003    |     LÖ      | 13,250.00 | (13 250,00 ÷ 18 162,50) × belopp |


