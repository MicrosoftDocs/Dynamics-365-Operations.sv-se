---
title: Fördela tid till jobb i en jobbunt
description: I tillverkningskörning kan du bunta jobb. Du kan sedan starta fler jobb på en gång på jobblistsidan.
author: johanhoffmann
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: JmgBundleSlize, JmgProdParameters, JmgRegistration
audience: Application User
ms.reviewer: kamaybac
ms.custom: 55591
ms.assetid: 358efce7-73c8-4d2a-a7f7-cb99b88ab6ee
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 86fbc81de8ba59f0782bd9af5b50bfcf45d5621a
ms.sourcegitcommit: 74e47075eab2b0b28f82b0d57f439719847ecb01
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/07/2021
ms.locfileid: "6193055"
---
# <a name="allocate-time-to-jobs-in-a-job-bundle"></a>Fördela tid till jobb i en jobbunt

[!include [banner](../includes/banner.md)]

I tillverkningskörning kan du bunta jobb. Du kan sedan starta fler jobb på en gång på jobblistsidan.

Om du buntar jobb, måste du definiera den totala registrerade tiden för alla jobb ska allokeras varje jobb. Du definierar allokeringen genom att välja ett av följande alternativ i fältet **Bunttyp** på sidan **Allokeringsnycklar**:

-   **Uppskattning** – Tiden delas mellan jobben baserat på den uppskattade tiden för jobben.
-   **Jobb** – Tiden delas upp efter det totala antalet buntade jobb och hur mycket tid som lades ned på att slutföra alla jobben.
-   **Nettotid** – Tiden delas lika mellan jobben som är i bunten vilken tid som helst.
-   **Realtid** - Den faktiska jobbtiden allokeras. Kostnaden kan beräknas baserat på den verkliga lönekostnaden. **Obs!** Allokeringsnyckeln **Realtid** är endast tillgänglig om ditt företag använder funktionen lönelista i Tid och närvaro.

Följande exempel visar de olika allokeringsnycklarna.

## <a name="example-scenario"></a>Exempelscenario
Tre jobb i jobbkön måste ha slutförts. Du startar det första jobbet och när detta jobb pågår startar du det andra och tredje jobbet. Därför finns det en bunt med tre jobb. Följande tabell visar den uppskattade produktionstiden för varje jobb.

| Jobb   | Produktionstid |
|-------|-----------------|
| Jobb 1 | 1 timma          |
| Jobb 2 | 3 timmar         |
| Jobb 3 | 4 timmar         |
| Summa | 8 timmar         |

Följande tabell visar faktiska antalet arbetstimmar som spenderas på varje jobb.

| Jobb    | Starttid | Sluttid | Bunttid |
|--------|------------|----------|-------------|
| Jobb 1  | 09:00:00      | 11:00:00    | 2 timmar     |
| Jobb 2  | 10:00:00      | 13:00:00    | 3 timmar     |
| Jobb 3  | 10:00:00      | 15:00:00    | 5 timmar     |
| Bunt | 09:00:00      | 15:00:00    | 6 timmar     |

Följande avsnitt beskriver resultaten av den beräknade tiden för varje allokeringsnyckel.

## <a name="estimation-allocation-key"></a>Allokeringsnyckeln Uppskattning
Följande tabell visar formeln för att beräkna allokerad tid. Formelnn är följande: Tid per jobb = Total bunttid x (Uppskattad jobbtid ÷ Total uppskattad tid)

| Jobb   | Formel           | Tilldelad tid |
|-------|-------------------|----------------|
| Jobb 1 | 6 × (1 ÷ 8) timmar | 0,75 timme      |
| Jobb 2 | 6 × (3 ÷ 8) timmar | 2,25 timmar     |
| Jobb 3 | 6 × (4 ÷ 8) timmar | 3,00 timmar     |

## <a name="jobs-allocation-key"></a>Allokeringsnyckeln Jobb
Följande tabell visar formeln för att beräkna allokerad tid. Formeln är följande: Tid per jobb = Total bunttid ÷ Antal jobb

| Jobb   | Formel | Tilldelad tid |
|-------|---------|----------------|
| Jobb 1 | 6 ÷ 3   | 2 timmar        |
| Jobb 2 | 6 ÷ 3   | 2 timmar        |
| Jobb 3 | 6 ÷ 3   | 2 timmar        |

## <a name="net-time-allocation-key"></a>Allokeringsnyckeln Nettotid
Följande tabell visar formeln för att beräkna allokerad tid. Formeln är följande: Beräknad tid per rapport = Bunttid ÷ Antal jobb

| Exempel                       | 09:00–10:00 (1 timme) | 10:00–11:00 (1 timme) | 11:00–13:00 (2 timmar) | 13:00–15:00 (2 timmar) | Tilldelad tid |
|------------------------------|----------------------|----------------------|-----------------------|-----------------------|----------------|
| Antalet jobb i bunten. | 1                    | 3                    | 2                     | 1                     | Inte tillämpligt |
| Jobb 1                        | 1 ÷ 1 = 1 timme       | 1 ÷ 3 = 0,33 timme    | Inte tillämpligt        | Inte tillämpligt        | 1,33 timmar     |
| Jobb 2                        | Inte tillämpligt       | 1 ÷ 3 = 0,33 timme    | 2 ÷ 2 = 1 timme        | Inte tillämpligt        | 1,33 timmar     |
| Jobb 3                        | Inte tillämpligt       | 1 ÷ 3 = 0,33 timme    | 2 ÷ 2 = 1 timme        | 2 ÷ 1 = 2 timmar       | 3,33 timmar     |

## <a name="real-time-allocation-key"></a>Allokeringsnyckeln Realtid
Om du vill att produktionskostnader ska beräknas baserat på verkliga kostnader, måste avmarkera alternativet **Kostnadskategori** på sidan **Standarder för produktionsorder**. Följande tabell visar formeln för att beräkna allokerad tid. Formeln är följande: Faktisk tid per jobb = Faktisk tid i bunt

| Jobb   | Faktisk tid |
|-------|-------------|
| Jobb 1 | 2 timmar     |
| Jobb 2 | 3 timmar     |
| Jobb 3 | 5 timmar     |

Tänk dig att de tre jobben utförs av en anställd, som har en timlön på 120,00 kronor. Ingen övertidsbonus eller premier erhålls för tiden som lagts ner på jobben. Medarbetaren har arbetat med dessa tre buntade jobb i totalt sex timmar. Därför är lönkostnaden 6 × 12,00 USD = 72,00 USD. När realtidsallokering används omberäknas kostnaden per timme med faktorn från formeln Nettotid. Den faktiska tid som lagts ner på varje jobb överförs då, men med den korrigerade självkostnaden per timme. I exemplet lägger man ner 6 timmar fastän 10 timmar är tilldelade. Följande tabell visar formeln för att beräkna kostnad. Formeln är följande: Kostnad per timme = (Total bunttid per jobb (Nettotid) ÷ Faktisk tid per jobb) x Standardsjälvkostnad per timme

| Jobb   | Beräkning av korrigerad kostnad per timme | Korrigerad kostnad per timme | Tilldelad tid | Total kostnad för jobbet |
|-------|----------------------------------------|-------------------------|----------------|-------------------|
| Jobb 1 | (1,33 ÷ 2) × 12,00 USD                 | 8,00 USD                | 2 timmar        | 16,00 USD         |
| Jobb 2 | (1,33 ÷ 3) × 12,00 USD                 | 5,33 USD                | 3 timmar        | 16,00 USD         |
| Jobb 3 | (3,33 ÷ 5) × 12,00 USD                 | 8,00 USD                | 5 timmar        | 40,00 USD         |

Den korrigerade kostnaden per timme samt jobbtiden bokförs i produktionsjournalen. **Obs!** Om du väljer alternativet **Kostnadskategori** på fliken **Allmän** på sidan **Standarder för produktionsorder**, överförs den verkliga tiden för varje jobb till en produktionsjournal, där kostnaden används för det specifika jobbets kostnadskategori.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]