---
title: "Providermallar för statistiska dimensionsmedlemmar och statistiska mätningar"
description: "Det här avsnittet innehåller information om statistikdimensionsmedlemmar och providermallar för statistisk mätning. Statistikdimensionsmedlemmar kan användas som en fördelningsbas i policyerna för bland annat kostnadsfördelning och kostnadsallokering. De kan också användas för att rapportera icke-monetär kostnadsförbrukning."
author: AndersGirke
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CAMCostAccountingLedgerSourceEntryProvider, CAMStatisticalDimension, CAMAXStatisticalMeasureProviderTemplate
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 2c0a00b6a1956f1f22a50951308c434c3f0eefc4
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="statistical-dimension-members-and-statistical-measure-provider-templates"></a>Providermallar för statistiska dimensionsmedlemmar och statistiska mätningar

[!include[banner](../includes/banner.md)]

En statistisk dimension och dess medlemmar används för att registrera och kontrollera icke-monetära poster i kostnadsredovisning. Statistiska dimensionsmedlemmar kan användas för två syften:

- Som en allokeringsbas i policyer såsom kostnadsdistribution eller kostnadsallokering
- För rapportering av icke-monetär förbrukning

## <a name="statistical-dimension"></a>Statistikdimension

En statistisk dimension har ett unikt namn och en uppsättning unika dimensionsmedlemmar. Den statistiska dimensionen tilldelas ett ID för huvudboken för kostnadsredovisning. Denna relation kopplar samman alla motsvarande statistiska dimensionsmedlemmar till huvudboken för kostnadsredovisning. Alla statistiska transaktioner kommer därför att skapas i kontexten av huvudboken för kostnadsredovisning.

> [!NOTE]
> En statistisk dimensionen kan tilldelas till fler än en huvudbok för kostnadsredovisning.

Här följer ett exempel på en statistisk dimension.

| Namn                        | Datakoppling för dimensionsmedlemmar |
|-----------------------------|--------------------------------------|
| Gemensamma statistiska element | Importerade dimensionsmedlemmar           |

Här följer ett exempel på en statistisk dimension som har tilldelats en huvudbok för kostnadsredovisning.

| Namn                  | Redovisningsvaluta | Valutakurstyp | Räkenskapskalender | Dimension för kostnadselement | Statistikdimension       |
|-----------------------|---------------------|--------------------|-----------------|------------------------|-----------------------------|
| Hanterbar redovisning | USD                 | Konstant valuta  | Räkenskapsperiod   | Gemensamma kostnadselement   | Gemensamma statistiska element |

## <a name="statistical-dimension-members"></a>Statistikdimensionsmedlemmar

En statistisk dimensionsmedlem representerar en enhet som du vill registrera icke-monetära åtgärder för. Dessa åtgärder kan användas som en fördelningsbas eller bara för att rapportera icke-monetära värden.

Statistiska dimensionsmedlemmar kan skapas manuellt. De kan också importeras från en fil med hjälp av datahanteringsverktyget importera och exportera.

En statistisk dimensionsmedlem blir automatiskt en fördefinierad fördelningsbas. Den kan användas som en fördelningsbas i policyer eller i andra typer av fördelningsbaser.

Här följer några exempel på vanliga statistiska dimensionsmedlemmar.

| Statistikdimensionsnamn  | Statistiska element | beskrivning             | Enhet |
|-----------------------------|----------------------|-------------------------|------|
| Gemensamma statistiska element | FTE                  | Heltidsmedarbetare     | Ea.  |
| Gemensamma statistiska element | Elektricitet          | Elförbrukning | kWh  |
| Gemensamma statistiska element | Packkopia              | Kostnadsställe för paketering   | Tim. |

## <a name="statistical-measure-provider-template"></a>Providermall för statistisk mätning

Statistiska mätningar kan ha sitt ursprung i många typer av källor. Microsoft Dynamics 365 for Finance and Operations, Enterprise edition är en stor källa för att extrahera statistiska mätningar från. Du kan använda en providermall för statistisk mätning för att enkelt konfigurera de statistiska mätningar du vill extrahera.

Definitionen av en providermall för statistisk mätning kan återanvändas i flera statistiska dimensionsmedlemmar.

> [!NOTE]
> Alla register som innehåller ekonomiska dimensioner kan användas som källa för statistiska mätningar.

**Exempel: Antalet medarbetare per kostnadsställe**

Antalet medarbetare per kostnadsställe är ett statistiskt mått som kan användas för olika ändamål som ger ledarskapsinsikter:

- En statistisk rapportåtgärd per kostnadsställe
- En allokeringsbas för olika typer av utgifter
- Interna kostnadstariffer per kostnadsställe:

    - Kostnad per medarbetare
    - Intäkt per medarbetare

Registret HcmEmployment innehåller en lista över alla medarbetare i förekomsten. Det här är ett globalt register. Posterna är därför inte kopplade till ett visst dataområdes-ID.

Här följer ett exempel på medarbetare i HcmEmployment-registret.

| Namn       | Kostnadsställe | beskrivning   | Typ av arbetare |
|------------|-------------|----|-------------|
| Medarbetare 1 | CC001       | Personal | Medarbetare    |
| Medarbetare 2 | CC002       | FI | Medarbetare    |
| Medarbetare 3 | CC002       | FI | Medarbetare    |
| Medarbetare 4 | CC003       | LÖ | Medarbetare    |
| Medarbetare 5 | CC003       | LÖ | Medarbetare    |
| Medarbetare 6 | CC002       | FI | Leverantör  |

När du skapar posten **Providermall för statistisk mätning** måste du bestämma vilken funktion som ska användas:

- **Antal** – Ett antal poster per kostnadsbärare överförs.
- **Summa** – En summa poster per kostnadsbärare överförs. (Fältet **Summa** och fältet **Datum** krävs.)

## <a name="using-the-count-function"></a>Använda funktionen Antal

Till exempel kan en providermallar för statistisk mätning ställas in på följande sätt.

| Namn  | Funktion | Källregister  | Summafält      | Datumfält     |
|-------|----------|---------------|----------------|----------------|
| Heltidsanställda  | Antal    | HcmEmployment | Inte tillämpligt | Inte tillämpligt |

Du kan även lägga till ett eller flera områden för att begränsa mätningarna från källregistret.

I det här exemplet, om du vill räkna alla heltidsanställda, kan du lägga till ett område i fältet **Typ av arbetare**. I fältet **Kriterier**, välj **Medarbetare** för att begränsa utdataintervallet på följande sätt.

**Intervall**

| Källregister  | Fält       | Kriterier |
|---------------|-------------|----------|
| HcmEmployment | Typ av arbetare | Medarbetare |

Innan du kan hämta statistiska mätningar till kostnadsredovisningen måste du upprätta en relation mellan providermallen för statistiska mätningar och den statistiska dimensionsmedlemmen. Den här relationen skapas per huvudbok för kostnadsredovisning och version. Relationen består av en datakoppling och en dataprovider. Du kan ha flera datakopplingar och dataprovider per statistisk dimensionsmedlem.

> [!NOTE]
> I det här exemplet skapar vi en relation för en **Faktisk version**.

Gå till **Huvudbok för kostnadsredovisning** \> **Faktisk version** \> **Hantera** \> **Statistiska mätningar** för att upprätta relationen. I det här scenariot markerar du datakopplingen **Dynamics 365 for Finance and Operations, Enterprise edition – statistiska mätningar**, eftersom vi vill hämta data från Finance and Operations.

**Datakälla**

| Namn        | Datakoppling                                                                     | Statistikdimensionsmedlem |
|-------------|------------------------------------------------------------------------------------|------------------------------|
| Heltidsanställda D365FO | Dynamics 365 for Finance and Operations, Enterprise edition – statistiska mätningar | Heltidsanställda                         |

**Dataproviderkonfiguration**

| Namn på statistisk mall |
|---------------------------|
| Heltidsanställda                      |

När källdata för statistiska mätningar har behandlats, skapas följande poster i kostnadsredovisning.

**Journal**

| Journal | Journaltyp                       | Räkenskapskalenderperiod | År   |  Period  |  Version | Datakoppling för källposter|
|---------|------------------------------------|------------------------|--------|----------|----------|------------------------------|
| 00001   | Överföringsjournal för statistisk post | Skatt                 | 2017   | Period 1 | CA-huvudbok USMF | Heltidsanställda                   |

**Överföringsjournalposter för statistisk post**

| Räkenskapsdatum | Storlek | Statistiskt element |   beskrivning       | Kostnadsställe |
|-----------------|-----------|---------------------|---------------------|-------------|
| 2017-01-31      | 1,00      | Heltidsanställda                | Heltidsanställda | CC001       |
| 2017-01-31      | 2.00      | Heltidsanställda                | Heltidsanställda | CC002       |
| 2017-01-31      | 2.00      | Heltidsanställda                | Heltidsanställda | CC003       |

**Statistikposter**

| Kostnadsobjekt |    | Räkenskapsdatum | Statistikdimensionsmedlem |  beskrivning        | Storlek |
|-------------|----|-----------------|------------------------------|---------------------|-----------|
| CC001       | Personal | 2017-01-31      | Heltidsanställda                         | Heltidsanställda | 1,00      |
| CC002       | FI | 2017-01-31      | Heltidsanställda                         | Heltidsanställda | 2.00      |
| CC003       | LÖ | 2017-01-31      | Heltidsanställda                         | Heltidsanställda | 2.00      |

Om den fördefinierad dimensionsmedlemsallokeringsbasen för heltidsanställda tilldelas som en allokeringsbas i en distributionsregel kommer kostnaden att fördelas med följande allokeringsfaktor.

| Kostnadsobjekt | beskrivning    | Storlek | Allokeringsfaktor |
|-------------|----|-----------|-------------------|
| CC001       | Personal | 1,00      | (1/5) × belopp    |
| CC002       | FI | 2.00      | (2/5) × belopp    |
| CC003       | LÖ | 2.00      | (2/5) × belopp    |

## <a name="using-the-sum-function"></a>Använda funktionen Summa

Ett produktionskostnadsställe CC010 (förpackning) ansvarar för förpackning av produkterna innan de levereras till kunder. Direkt arbetskostnad läggs till produkter via strukturlistor och flöden. Den indirekta kostnaden för kostnadsstället måste också tilldelas till de tillverkade produkterna. Ofta är den bästa statistiska mätningen för en sådan fördelning antalet registrerade produktionstimmar per produkt inom den angivna perioden.

Registret ProdRouteTrans innehåller alla transaktioner för arbete per juridisk person DataAreadID.

Här följer ett exempel på registret ProdRouteTrans.

| Referens        | Nummer | Åtgärd | Typ | Tid  | Fysiskt datum | Produktgrupp (ekonomisk dimension) | Juridisk person |
|------------------|--------|-----------|------|-------|---------------|-------------------------------------|--------------|
| Produktionsorder | P0001  | Paketering | Tid | 8,00  | 2017-01-01    | Apelsinjuice B2B                    | USMF         |
| Produktionsorder | P0001  | Paketering | Tid | 8,00  | 2017-01-02    | Apelsinjuice B2B                    | USMF         |
| Produktionsorder | P0002  | Paketering | Tid | 4,00  | 2017-01-03    | Apelsinjuicekonsument               | USMF         |
| Produktionsorder | P0003  | Paketering | Tid | 4,00  | 2017-01-03    | Apelsinjuicekonsument               | USMF         |
| Produktionsorder | P0004  | Rekonstr.  | Tid | 10,00 | 2017-01-03    | Apelsinjuicekonsument               | USMF         |

När du skapar posten **Providermall för statistisk mätning** måste du bestämma vilken funktion som ska användas:

- **Antal** – Ett antal poster per kostnadsbärare överförs.
- **Summa** – En summa poster per kostnadsbärare överförs. (Fältet **Summa** och fältet **Datum** krävs.)

Providermallen för statistisk mätning kan ställas in på följande sätt.

| Namn    | Funktion | Källregister   | Summafält | Datumfält    |
|---------|----------|----------------|-----------|---------------|
| Packkopia | Summa      | ProdRouteTrans | Timmar     | Fysiskt datum |

Du kan även lägga till intervall för att begränsa mätningarna från källregistret.

I det här exemplet, om du bara vill ha summan av de timmar som rör CC010-packningskostnadsstället, kan du lägga till ett intervall i fältet **Åtgärd**. I fältet **Kriterium**, välj **Paketering** för att begränsa utdataintervallet.

**Intervall**

| Källregister   | Fält     | Kriterier  |
|----------------|-----------|-----------|
| ProdRouteTrans | Åtgärd | Paketering |

Innan du kan hämta statistiska mätningar till kostnadsredovisningen måste du upprätta en relation mellan providermallen för statistiska mätningar och den statistiska dimensionsmedlemmen. Den här relationen skapas per huvudbok för kostnadsredovisning och version. Relationen består av en datakoppling och en dataprovider. Du kan ha flera datakopplingar och dataprovider per statistisk dimensionsmedlem.

> [!NOTE]
> I det här exemplet skapar vi en relation för en **Faktisk version**.

Gå till **Huvudbok för kostnadsredovisning** \> **Faktisk version** \> **Hantera** \> **Statistiska mätningar** för att upprätta relationen. I det här scenariot markerar du datakopplingen **Dynamics 365 for Finance and Operations, Enterprise edition – statistiska mätningar**, eftersom vi vill hämta data från Finance and Operations.

**Datakälla**

| Namn           | Datakoppling                                                                     | Statistikdimensionsmedlem |
|----------------|------------------------------------------------------------------------------------|------------------------------|
| Packkopia D365FO | Dynamics 365 for Finance and Operations, Enterprise edition – statistiska mätningar | Packkopia                      |

Systemet känner igen att ProdRouteTrans är ett register där varje post tillhör en separat juridisk person. Därför uppmanas du att välja den juridiska person som transaktionerna ska importeras från.

**Dataproviderkonfiguration**

| Namn på statistisk mall | Juridisk person |
|---------------------------|--------------|
| Packkopia                   | USMF         |

När källdata för statistiska mätningar har behandlats, skapas följande poster i kostnadsredovisning.

**Journal**

| Journal | Journaltyp                     | Räkenskapskalenderperiod | År   | Period | Version   |   Datakoppling för källposter  |
|---------|----------------------------------|------------------------|--------|---------|----------------|---------|
| 00002   | Överföringsjournal för statistisk post | Skatt               | 2017    | Period 1  | CA-huvudbok USMF | Packkopia |

**Överföringsjournalposter för statistisk post**

| Räkenskapsdatum | Storlek | Statistiskt element |  beskrivning          | Produktgrupp         |
|-----------------|-----------|---------------------|-----------------------|-----------------------|
| 2017-01-31      | 16,00     | Packkopia             | Kostnadsställe för paketering | Apelsinjuice B2B      |
| 2017-01-31      | 8,00      | Packkopia             | Kostnadsställe för paketering | Apelsinjuicekonsument |

**Statistikposter**

| Kostnadsobjekt           | Räkenskapsdatum | Statistikdimensionsmedlem |    beskrivning        | Storlek |
|-----------------------|-----------------|------------------------------|-----------------------|-----------|
| Apelsinjuice B2B      | 2017-01-31      | Packkopia                      | Kostnadsställe för paketering | 16,00     |
| Apelsinjuicekonsument | 2017-01-31      | Packkopia                      | Kostnadsställe för paketering | 8,00      |

Om den fördefinierad dimensionsmedlemsallokeringsbasen för packkopian tilldelas som en allokeringsbas i en kostnadsdistributionsregel kommer kostnaden att fördelas med följande allokeringsfaktor.

| Kostnadsobjekt           | Storlek | Allokeringsfaktor  |
|-----------------------|-----------|--------------------|
| Apelsinjuice B2B      | 16,00     | (16 ÷ 24) × belopp |
| Apelsinjuicekonsument | 8,00      | (8 ÷ 24) × belopp  |

## <a name="imported-statistical-measures"></a>Importerade statistiska mätningar

Du kan importera statistiska mätningar till kostnadsredovisningen med hjälp av datahanteringsverktyget importera och exportera.

Dataenheten som används för importen kallas Importerad statistisk mätning.

> [!NOTE]
> Dataenheten är utformat för att tillåta högst fem unika dimensionsvärden per post.

Användningen av el registreras med fördefinierade format för dataenheten i Microsoft Excel. Här är ett exempel:

| Räkenskapsdatum | Namn 1 på dimensionsmedlemmen | Namn 2 på dimensionsmedlemmen | Namn 5 på dimensionsmedlemmen | Storlek  | Identifierare för källa |
|-----------------|------------------------|------------------------|------------------------|------------|-------------------|
| 2017-01-31      | CC001                  |                        |                        | 2,450.00   | Elektricitet       |
| 2017-01-31      | CC002                  |                        |                        | 4,100.00   | Elektricitet       |
| 2017-01-31      | CC003                  |                        |                        | 15,000.00  | Elektricitet       |

När du har importerat dina data via Datahantering lagras data i en tabell för mellanlagring av kostnadsredovisning. Importerade data kan därför användas i flera huvudböcker för kostnadsredovisning. Du behöver inte ladda om data.

När du importerar data, gå till **Importerade data** \> **Dataenhet** \> **Importerade statistiska mätningar**.

| Identifierare för källa | Räkenskapsdatum | Storlek  | Namn 1 på dimensionsmedlemmen | Namn 2 på dimensionsmedlemmen | Namn 5 på dimensionsmedlemmen |
|-------------------|-----------------|------------|------------------------|------------------------|------------------------|
| Elektricitet       | 2017-01-31      | 2,450.00   | CC001                  |                        |                        |
| Elektricitet       | 2017-01-31      | 4,100.00   | CC002                  |                        |                        |
| Elektricitet       | 2017-01-31      | 15,000.00  | CC003                  |                        |                        |

Innan du kan hämta statistiska mätningar till kostnadsredovisningen måste du upprätta en relation mellan källidentifieraren och den statistiska dimensionsmedlemmen. Den här relationen skapas per huvudbok för kostnadsredovisning och version. Relationen består av en datakoppling och en dataprovider. Du kan ha flera datakopplingar och dataprovider per statistisk dimensionsmedlem.

> [!NOTE]
> I det här exemplet skapar vi en relation för en **Faktisk version**.

Gå till **Huvudbok för kostnadsredovisning** \> **Faktisk version** \> **Hantera** \> **Statistiska mätningar** för att upprätta relationen. I det här scenariot markerar du datakopplingen **Importerade statistiska mätningar**, eftersom data har importerats från tredje partssystem till kostnadsredovisning via Excel.

**Datakälla**

| Namn        | Datakoppling                | Statistikdimensionsmedlem |
|-------------|-------------------------------|------------------------------|
| Elektricitet | Importerade statistiska mätningar | Elektricitet                  |

**Dataproviderkonfiguration**

| Identifierare för importkälla | Funktion | Dimension 1   | Dimension 2 | Dimension 5 |
|--------------------------|----------|--------------|------------|------------|
| Elektricitet              | Summa      | Kostnadsställen |            |            |

> [!NOTE]
> När du definierar dataproviderkonfigurationen måste du ange vilken kostnadsbärardimension som ska matchas mot de importerade transaktionerna. När källdata för statistiska mätningar har behandlats, skapas följande poster i kostnadsredovisning.

**Journal**

| Journal | Journaltyp                       | Räkenskapskalenderperiod | År  | Period  |Version      |Datakoppling för källposter |
|---------|------------------------------------|------------------------|-------|--------|---------------|-------------|
| 00002   | Överföringsjournal för statistisk post | Skatt                 | 2017  | Period 1 | CA-huvudbok USMF | Elektricitet |

**Överföringsjournalposter för statistisk post**

| Räkenskapsdatum | Storlek  | Kostnadselement |   beskrivning           | Kostnadsställe |
|-----------------|------------|--------------|-------------------------|-------------|
| 2017-01-31      | 2,450.00   | Elektricitet  | Elförbrukning | CC001       |
| 2017-01-31      | 4,100.00   | Elektricitet  | Elförbrukning | CC002       |
| 2017-01-31      | 15,000.00  | Elektricitet  | Elförbrukning | CC003       |

**Statistikposter**

| Kostnadsobjekt |    | Räkenskapsdatum | Statistikdimensionsmedlem |      beskrivning                   | Storlek  |
|-------------|----|-----------------|------------------------------|-------------------------|------------|
| CC001       | Personal | 31-01-2017      | Elektricitet                  | Elförbrukning | 2,450.00   |
| CC002       | FI | 31-01-2017      | Elektricitet                  | Elförbrukning | 4,100.00   |
| CC003       | LÖ | 2017-01-31      | Elektricitet                  | Elförbrukning | 15,000.00  |

Om den fördefinierad dimensionsmedlemsallokeringsbasen för el tilldelas som en allokeringsbas i en kostnadsdistributionsregel kommer kostnaden att fördelas med följande allokeringsfaktor.

| Kostnadsobjekt |    | Storlek | Allokeringsfaktor          |
|-------------|----|-----------|----------------------------|
| CC001       | Personal | 2,450.00  | (2 450 ÷ 21 550) × belopp  |
| CC002       | FI | 4,100.00  | (4 100 ÷ 21 550) × belopp  |
| CC003       | LÖ | 15,000.00 | (15 000 ÷ 21 550) × belopp |

## <a name="see-also"></a>Se även

[Allokeringsunderlag](allocation-bases.md)

