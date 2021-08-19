---
title: Funktion för sammanslagningsintervall
description: Det här ämnet innehåller information som hjälper dig att välja mellan månadsvis, kvartalsvis, halvårsvis och årliga sammanslagningsintervall.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeaseDetail
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 9d0f01748d370dfa5351ceb007a630564ca5d3a76c142830f32ce11951db9088
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6716703"
---
# <a name="compounding-interval-functionality"></a>Funktion för sammanslagningsintervall

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Det här ämnet innehåller information som hjälper dig att välja mellan månadsvis, kvartalsvis, halvårsvis och årliga sammanslagningsintervall. Funktionen för sammanslagningsintervall används för att fastställa antalet sammanslagningsperioder per år i ett leasingavtals betalningsplan. Vart och ett av de fyra exemplen i det här avsnittet visar hur ett leasingavtals betalningsplan kommer att se ut för ett annat intervall.

Du kan inte välja ett sammanslagningsintervall som är mindre vanligt än leasingens betalningsfrekvens. Ett kvartalsvis sammanslagningsintervall kan till exempel inte användas med en månatlig betalningsfrekvens, och ett årligt sammanslagningsintervall kan inte användas med en halvårsvis betalningsfrekvens. Om du försöker välja ett sammanslagningsintervall som är mindre vanligt än leasingens betalningsfrekvens får du ett felmeddelande.

> [!NOTE]
> I alla fyra exemplen i det här avsnittet matchar sammanslagningsintervallet betalningsfrekvensen.

## <a name="examples"></a>Exempel

### <a name="setup-for-all-four-leases"></a>Inställningar för alla fyra leasingavtal

I följande tabeller visas de värden som är inställda på flikarna **Allmänt** och **Betalningsplanrader** för de fyra leasingavtal som används i exemplen.

**Fliken Allmänt**

| Fält                      | Värde                        |
|----------------------------|------------------------------|
| Marginell låneränta | **5 %**                       |
| Typ av annuitet               | **Vanlig annuitet**         |
| Intervall för sammanslagning       | Se de enskilda exemplen. |
| Lönefrekvens          | **Månatlig**                  |
| Startdatum          | **2020-01-01**                 |

**Fliken Betalningsplanrader**

| Fält             | Värde                        |
|-------------------|------------------------------|
| Startdatum        | **2020-01-01**                 |
| Perioder           | **120**                      |
| Periodintervall   | **Månader**                   |
| Slutdatum          | **2029-12-31**               |
| Lönefrekvens | Se de enskilda exemplen. |
| Betalningsbelopp    | **50,000**                   |

### <a name="lease-1-monthly-compounding-interval-and-monthly-payment-frequency"></a>Leasing 1: Månadsvis sammanslagningsintervall och månadsvis betalningsfrekvens

Följande tabell visar de första tolv månaderna av betalningsplanen. Observera följande information:

- Värdet i kolumnen "Period" ökar med 1 varje månad, eftersom varje månad är ett nytt sammanslagningsintervall.
- I formeln i kolumnen "Nuvarande värde" delas kursen med 12, eftersom det finns 12 sammanslagningsperioder per år. Exponenten (dvs. den upphöjda siffran) är lika med värdet i kolumnen "Period".

| Period | Månad | Datum       | Betalningsbelopp | Aktuellt värde                                       |
|--------|-------|------------|----------------|-----------------------------------------------------|
| 1      | 1     | 2020-01-31  | 50,000.00      | 50 000 ÷ (1 + \[5 % ÷ 12\])<sup>1</sup> = 49 792,53  |
| 2      | 2     | 2020-02-29  | 50,000.00      | 50 000 ÷ (1 + \[5 % ÷ 12\])<sup>2</sup> = 49 585,92  |
| 3      | 3     | 2020-03-31  | 50,000.00      | 50 000 ÷ (1 + \[5 % ÷ 12\])<sup>3</sup> = 49 380,17  |
| 4      | 4     | 2020-04-30  | 50,000.00      | 50 000 ÷ (1 + \[5 % ÷ 12\])<sup>4</sup> = 49 175,28  |
| 5      | 5     | 2020-05-31  | 50,000.00      | 50 000 ÷ (1 + \[5 % ÷ 12\])<sup>5</sup> = 48 971,23  |
| 6      | 6     | 2020-06-30  | 50,000.00      | 50 000 ÷ (1 + \[5 % ÷ 12\])<sup>6</sup> = 48 768,03  |
| 7      | 7     | 2020-07-31  | 50,000.00      | 50 000 ÷ (1 + \[5 % ÷ 12\])<sup>7</sup> = 48 565,67  |
| 8      | 8     | 2020-08-31  | 50,000.00      | 50 000 ÷ (1 + \[5 % ÷ 12\])<sup>8</sup> = 48 364,15  |
| 9      | 9     | 2020-09-30  | 50,000.00      | 50 000 ÷ (1 + \[5 % ÷ 12\])<sup>9</sup> = 48 163,47  |
| 10     | 10    | 2020-10-31 | 50,000.00      | 50 000 ÷ (1 + \[5 % ÷ 12\])<sup>10</sup> = 47 963,62 |
| 11     | 11    | 2020-11-30 | 50,000.00      | 50 000 ÷ (1 + \[5 % ÷ 12\])<sup>11</sup> = 47 764,61 |
| 12     | 12    | 2020-12-31 | 50,000.00      | 50 000 ÷ (1 + \[5 % ÷ 12\])<sup>12</sup> = 47 566,41 |

### <a name="lease-2-quarterly-compounding-interval-and-quarterly-payment-frequency"></a>Leasing 2: Kvartalsvis sammanslagningsintervall och kvartalsvis betalningsfrekvens

Följande tabell visar de första tolv månaderna av betalningsplanen. Observera följande information:

- Värdet i kolumnen "Period" ökar med 1 var tredje månad (dvs. varje kvartal), eftersom varje kvartal är ett nytt sammanslagningsintervall.
- I formeln i kolumnen "Nuvarande värde" delas kursen med 4, eftersom det finns 4 sammanslagningsperioder per år. Exponenten är lika med värdet i kolumnen "Period".

| Period | Månad | Datum       | Betalningsbelopp | Aktuellt värde                                     |
|--------|-------|------------|----------------|---------------------------------------------------|
| 1      | 1     | 2020-01-31  | 0,00           | 0,00 ÷ (1 + \[5 % ÷ 4\])<sup>1</sup> = 0           |
| 1      | 2     | 2020-02-29  | 0,00           | 0,00 ÷ (1 + \[5 % ÷ 4\])<sup>1</sup> = 0           |
| 1      | 3     | 2020-03-31  | 50,000.00      | 50 000 ÷ (1 + \[5 % ÷ 4\])<sup>1</sup> = 49 382,72 |
| 2      | 4     | 2020-04-30  | 0,00           | 0,00 ÷ (1 + \[5 % ÷ 4\])<sup>2</sup> = 0           |
| 2      | 5     | 2020-05-31  | 0,00           | 0,00 ÷ (1 + \[5 % ÷ 4\])<sup>2</sup> = 0           |
| 2      | 6     | 2020-06-30  | 50,000.00      | 50 000 ÷ (1 + \[5 % ÷ 4\])<sup>2</sup> = 48 773,05 |
| 3      | 7     | 2020-07-31  | 0,00           | 0,00 ÷ (1 + \[5 % ÷ 4\])<sup>3</sup> = 0           |
| 3      | 8     | 2020-08-31  | 0,00           | 0,00 ÷ (1 + \[5 % ÷ 4\])<sup>3</sup> = 0           |
| 3      | 9     | 2020-09-30  | 50,000.00      | 50 000 ÷ (1 + \[5 % ÷ 4\])<sup>3</sup> = 48 170,92 |
| 4      | 10    | 2020-10-31 | 0,00           | 0,00 ÷ (1 + \[5 % ÷ 4\])<sup>4</sup> = 0           |
| 4      | 11    | 2020-11-30 | 0,00           | 0,00 ÷ (1 + \[5 % ÷ 4\])<sup>4</sup> = 0           |
| 4      | 12    | 2020-12-31 | 50,000.00      | 50 000 ÷ (1 + \[5 % ÷ 4\])<sup>4</sup> = 47 576,21 |

> [!NOTE]
> Om annuitetstypen ändras till **Annuitet förfaller** kommer betalningen att ske i början av kvartalet i stället för kvartalets slut.

### <a name="lease-3-semiannual-compounding-interval-and-semiannual-payment-frequency"></a>Leasing 3: Halvårsvis sammanslagningsintervall och halvårsvis betalningsfrekvens

Följande tabell visar de första tolv månaderna av betalningsplanen. Observera följande information:

- Värdet i kolumnen "Period" ökar med 1 var sjätte månad (dvs. varje halvår), eftersom varje halvår är ett nytt sammanslagningsintervall.
- I formeln i kolumnen "Nuvarande värde" delas kursen med 2, eftersom det finns 2 sammanslagningsperioder per år. Exponenten är lika med värdet i kolumnen "Period".

| Period | Månad | Datum       | Betalningsbelopp | Aktuellt värde                                     |
|--------|-------|------------|----------------|---------------------------------------------------|
| 1      | 1     | 2020-01-31  | 0,00           | 0,00 ÷ (1 + \[5 % ÷ 2\])<sup>1</sup> = 0           |
| 1      | 2     | 2020-02-29  | 0,00           | 0,00 ÷ (1 + \[5 % ÷ 2\])<sup>1</sup> = 0           |
| 1      | 3     | 2020-03-31  | 0,00           | 0,00 ÷ (1 + \[5 % ÷ 2\])<sup>1</sup> = 0           |
| 1      | 4     | 2020-04-30  | 0,00           | 0,00 ÷ (1 + \[5 % ÷ 2\])<sup>1</sup> = 0           |
| 1      | 5     | 2020-05-31  | 0,00           | 0,00 ÷ (1 + \[5 % ÷ 2\])<sup>1</sup> = 0           |
| 1      | 6     | 2020-06-30  | 50,000.00      | 50 000 ÷ (1 + \[5 % ÷ 2\])<sup>1</sup> = 48 780,49 |
| 2      | 7     | 2020-07-31  | 0,00           | 0,00 ÷ (1 + \[5 % ÷ 2\])<sup>2</sup> = 0           |
| 2      | 8     | 2020-08-31  | 0,00           | 0,00 ÷ (1 + \[5 % ÷ 2\])<sup>2</sup> = 0           |
| 2      | 9     | 2020-09-30  | 0,00           | 0,00 ÷ (1 + \[5 % ÷ 2\])<sup>2</sup> = 0           |
| 2      | 10    | 2020-10-31 | 0,00           | 0,00 ÷ (1 + \[5 % ÷ 2\])<sup>2</sup> = 0           |
| 2      | 11    | 2020-11-30 | 0,00           | 0,00 ÷ (1 + \[5 % ÷ 2\])<sup>2</sup> = 0           |
| 2      | 12    | 2020-12-31 | 50,000.00      | 50 000 ÷ (1 + \[5 % ÷ 2\])<sup>2</sup> = 47 590,72 |

> [!NOTE]
> Om annuitetstypen ändras till **Annuitet förfaller**, kommer betalningen att vara i januari och juli i stället för juni och december.

### <a name="lease-4-annual-compounding-interval-and-annual-payment-frequency"></a>Leasing 4: Årsvis sammanslagningsintervall och årsvis betalningsfrekvens

Följande tabell visar de första tolv månaderna av betalningsplanen. Observera följande information:

- Värdet i kolumnen "Period" ökar med 1 var tolfte månad (dvs. varje år), eftersom varje år är ett nytt sammanslagningsintervall.
- I formeln i kolumnen "Nuvarande värde" delas kursen med 1, eftersom det finns 1 sammanslagningsperiod per år. Exponenten är lika med värdet i kolumnen "Period".

| Period | Månad | Datum       | Betalningsbelopp | Aktuellt värde                                     |
|--------|-------|------------|----------------|---------------------------------------------------|
| 1      | 1     | 2020-01-31  | 0,00           | 0,00 ÷ (1 + \[5 % ÷ 1\])<sup>1</sup> = 0           |
| 1      | 2     | 2020-02-29  | 0,00           | 0,00 ÷ (1 + \[5 % ÷ 1\])<sup>1</sup> = 0           |
| 1      | 3     | 2020-03-31  | 0,00           | 0,00 ÷ (1 + \[5 % ÷ 1\])<sup>1</sup> = 0           |
| 1      | 4     | 2020-04-30  | 0,00           | 0,00 ÷ (1 + \[5 % ÷ 1\])<sup>1</sup> = 0           |
| 1      | 5     | 2020-05-31  | 0,00           | 0,00 ÷ (1 + \[5 % ÷ 1\])<sup>1</sup> = 0           |
| 1      | 6     | 2020-06-30  | 0,00           | 0,00 ÷ (1 + \[5 % ÷ 1\])<sup>1</sup> = 0           |
| 1      | 7     | 2020-07-31  | 0,00           | 0,00 ÷ (1 + \[5 % ÷ 1\])<sup>1</sup> = 0           |
| 1      | 8     | 2020-08-31  | 0,00           | 0,00 ÷ (1 + \[5 % ÷ 1\])<sup>1</sup> = 0           |
| 1      | 9     | 2020-09-30  | 0,00           | 0,00 ÷ (1 + \[5 % ÷ 1\])<sup>1</sup> = 0           |
| 1      | 10    | 2020-10-31 | 0,00           | 0,00 ÷ (1 + \[5 % ÷ 1\])<sup>1</sup> = 0           |
| 1      | 11    | 2020-11-30 | 0,00           | 0,00 ÷ (1 + \[5 % ÷ 1\])<sup>1</sup> = 0           |
| 1      | 12    | 2020-12-31 | 50,000.00      | 50 000 ÷ (1 + \[5 % ÷ 1\])<sup>1</sup> = 47 619,05 |

> [!NOTE]
> Om annuitetstypen ändras till **Annuitet förfaller**, kommer betalningen att vara i januari i stället för december.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
