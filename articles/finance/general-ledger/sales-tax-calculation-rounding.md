---
title: Momsberäkning och avrundning
description: Den här artikeln innehåller en översikt över momsberäkning och avrundning, och förklarar parametrarna för momsberäkningen och avrundningsinställningen.
author: wangchen
ms.date: 06/01/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: kfend
ms.custom:
- "13111"
- intro-internal
ms.assetid: fe5fdc7f-9834-49fb-a611-1dd9c289619d
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2022-05-31
ms.dyn365.ops.version: AX 10.0.28
ms.openlocfilehash: aa3564f0fcf4a958637ba4a5cdcc497bffc50000
ms.sourcegitcommit: 8b716849707ec96d1cb4cac85b9e782dc25f5a70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/07/2022
ms.locfileid: "8939245"
---
# <a name="sales-tax-calculation-and-rounding"></a>Momsberäkning och avrundning

[!include [banner](../includes/banner.md)]

Den här artikeln ger en översikt över momsberäkning och avrundning i Microsoft Dynamics 365 Finance. Det förklarar även de parametrar som används i inställningarna för momsberäkning och avrundning, och hur dessa parametrar fungerar tillsammans.

## <a name="parameters"></a>Parametrar

Flera parametrar styr momsberäkning och avrundning:

- **Beräkningsmetod** – Den här parametern ställs in på sidan **Allmänna redovisningsparametrar** och definierar om skattebasbeloppet beräknas per dokument eller per rad. Om **marginalbas** parametern för momskoden har ställts in på **Nettobelopp för fakturasaldo**, beräknas skattebasbeloppet alltid per dokument, oavsett vilken inställning den här parametern har ställts in.
- **Avrundning med** – Den här parametern ställs in för momsgruppen och anger om momsbeloppet avrundas per momskod eller per momskodskombination.
- **Ursprung** – den här parametern är inställd för momskoden och definierar hur momsbeloppet beräknas. Mer information finns i [Momsberäkningsmetoder i fältet Ursprung](sales-tax-calculation-methods-origin-field.md)
- **Bidragsunderlag** – Denna parameter ställs in för momskoden och bestämmer vilket belopp som används för att välja lämpliga momssatser på **Momskodvärden**. Mer information finns i [Momssatser baserat på fälten Marginalbas och Beräkningsmetod](marginal-base-field.md)
- **Momsavrundningsregel** – Den här parametern ställs in för momskoden och definierar hur det bestäms momsbeloppet avrundas, inklusive avrundningsprecision och avrundningsmetoden.

I resten av den här artikeln visas några typiska exempel på momsberäkning och avrundning som använder en kombination av föregående parametrar.

## <a name="scenario-for-the-examples"></a>Scenario för exempel

- Det finns två rader i den skattepliktiga handlingen och skattebasbeloppet för varje rad är 42,42.
- Två momskoder är definierade för varje rad: momskod 1 och momskod 2.
- Momssatsen för både momskod 1 och momskod 2 är 10 procent.
- Priset är exklusive skatt.
- Avrundningsprecisionen är 0,01.
- Avrundningsmetoden ställs in på **Avrunda uppåt**.

## <a name="example-1"></a>Exempel 1

### <a name="parameter-values"></a>Parametervärden

| Beräkningsmetod | Avrundning efter    | Ursprung                   | Bidragsunderlag       |
| ------------------ | -------------- | ------------------------ | ------------------- |
| Rad               | Momskod | Procent av nettobelopp | Nettobelopp per rad |

### <a name="calculation-and-rounding-behavior"></a>Beräknings- och avrundningsbeteende

| Radnummer | Momskod | Beloppsunderlag | Momsbelopp |
| ------------| ---------------| --------------| -----------------|
| 1           | Kod 1         | 42.42         | 4.25             |
| 1           | Kod 2         | 42.42         | 4.25             |
| 2           | Kod 1         | 42.42         | 4.25             |
| 2           | Kod 2         | 42.42         | 4.25             |

Skattebasbeloppet beräknas per rad:

- **Rad 1:** 42,42
- **Rad 2:** 42,42

Momsbeloppet beräknas per momskod:

- **Rad 1:**

    - Momsbelopp för momskod 1 = 42,42 &times; 10 procent = 4,242
    - Momsbelopp för momskod 2 = 42,42 &times; 10 procent = 4,242

- **Rad 2:**

    - Momsbelopp för momskod 1 = 42,42 &times; 10 procent = 4,242
    - Momsbelopp för momskod 2 = 42,42 &times; 10 procent = 4,242

Momsbeloppet avrundas per momskod:

- **Rad 1:**

    - Avrundat momsbelopp för momskod 1 = 4,25
    - Avrundat momsbelopp för momskod 2 = 4,25

- **Rad 2:**

    - Avrundat momsbelopp för momskod 1 = 4,25
    - Avrundat momsbelopp för momskod 2 = 4,25

## <a name="example-2"></a>Exempel 2

### <a name="parameter-values"></a>Parametervärden

| Beräkningsmetod | Avrundning efter    | Ursprung                   | Bidragsunderlag                 |
| ------------------ | -------------- | ------------------------ | ----------------------------- |
| Rad/total         | Momskod | Procent av nettobelopp | Nettobelopp av fakturasaldo |

### <a name="calculation-and-rounding-behavior"></a>Beräknings- och avrundningsbeteende

| Radnummer | Momskod | Beloppsunderlag | Momsbelopp |
| ----------- | -------------- | ------------- | ---------------- |
| 1           | Kod 1         | 42.42         | 4.25             |
| 1           | Kod 2         | 42.42         | 4.25             |
| 2           | Kod 1         | 42.42         | 4.24             |
| 2           | Kod 2         | 42.42         | 4.24             |

Skattebasbeloppet beräknas per dokument:

- Momsbasbelopp = 42,42 + 42,42 = 84,84

Momsbeloppet beräknas per momskod:

- Momsbelopp för momskod 1 = 84,84 &times; 10 procent = 8,484
- Momsbelopp för momskod 2 = 84,84 &times; 10 procent = 8,484

Momsbeloppet avrundas per momskod:

- Avrundat momsbelopp för momskod 1 = 8,49
- Avrundat momsbelopp för momskod 2 = 8,49

Det avrundade momsbeloppet tilldelas varje rad per momskod:

- Fördela det avrundade momsbeloppet för momskod 1 (8,49) till rad 1 (4,25) och rad 2 (4,24).
- Fördela det avrundade momsbeloppet för momskod 2 (8,49) till rad 1 (4,25) och rad 2 (4,24).

## <a name="example-3"></a>Exempel 3

### <a name="parameter-values"></a>Parametervärden

| Beräkningsmetod | Avrundning efter    | Ursprung                              | Bidragsunderlag       |
| ------------------ | -------------- | ----------------------------------- | ------------------- |
| Rad               | Momskod | Beräknad procent av nettobeloppet | Nettobelopp per rad |

### <a name="calculation-and-rounding-behavior"></a>Beräknings- och avrundningsbeteende

| Radnummer | Momskod | Beloppsunderlag | Momsbelopp |
| ----------- | -------------- | ------------- | ---------------- |
| 1           | Kod 1         | 42.42         | 4.72             |
| 1           | Kod 2         | 42.42         | 4.72             |
| 2           | Kod 1         | 42.42         | 4.72             |
| 2           | Kod 2         | 42.42         | 4.72             |

Skattebasbeloppet beräknas per rad:

- **Rad 1:** 42,42
- **Rad 2:** 42,42

Momsbeloppet beräknas per momskod:

- **Rad 1:**

    - Momsbelopp för momskod 1 = 42,42 &times; 10 procent &divide; (1 – 10 procent) = 4,7133
    - Momsbelopp för momskod 2 = 42,42 &times; 10 procent &divide; (1 – 10 procent) = 4,7133

- **Rad 2:**

    - Momsbelopp för momskod 1 = 42,42 &times; 10 procent &divide; (1 – 10 procent) = 4,7133
    - Momsbelopp för momskod 2 = 42,42 &times; 10 procent &divide; (1 – 10 procent) = 4,7133

Momsbeloppet avrundas per momskod:

- **Rad 1:**

    - Avrundat momsbelopp för momskod 1 = 4,72
    - Avrundat momsbelopp för momskod 2 = 4,72

- **Rad 2:**

    - Avrundat momsbelopp för momskod 1 = 4,72
    - Avrundat momsbelopp för momskod 2 = 4,72

## <a name="example-4"></a>Exempel 4

### <a name="parameter-values"></a>Parametervärden

| Beräkningsmetod | Avrundning efter    | Ursprung                              | Bidragsunderlag                 |
| ------------------ | -------------- | ----------------------------------- | ----------------------------- |
| Rad/total         | Momskod | Beräknad procent av nettobeloppet | Nettobelopp av fakturasaldo |

### <a name="calculation-and-rounding-behavior"></a>Beräknings- och avrundningsbeteende

| Radnummer | Momskod | Beloppsunderlag | Momsbelopp |
| ----------- | -------------- | ------------- | ---------------- |
| 1           | Kod 1         | 42.42         | 4.72             |
| 1           | Kod 2         | 42.42         | 4.72             |
| 2           | Kod 1         | 42.42         | 4.71             |
| 2           | Kod 2         | 42.42         | 4.71             |

Skattebasbeloppet beräknas per dokument:

- Momsbasbelopp = 42,42 + 42,42 = 84,84

Momsbeloppet beräknas per momskod:

- Momsbelopp för momskod 1 = 84,84 &times; 10 procent &divide; (1 – 10 procent) = 9,4267
- Momsbelopp för momskod 2 = 84,84 &times; 10 procent &divide; (1 – 10 procent) = 9,4267

Momsbeloppet avrundas per momskod:

- Avrundat momsbelopp för momskod 1 = 9,43
- Avrundat momsbelopp för momskod 2 = 9,43

Det avrundade momsbeloppet tilldelas varje rad per momskod:

- Fördela momsbeloppet för momskod 1 (9,43) till rad 1 (4,72) och rad 2 (4,71).
- Fördela momsbeloppet för momskod 2 (9,43) till rad 1 (4,72) och rad 2 (4,71).

## <a name="example-5"></a>Exempel 5

### <a name="parameter-values"></a>Parametervärden

| Beräkningsmetod | Avrundning efter                | Ursprung                   | Bidragsunderlag       |
| ------------------ | -------------------------- | ------------------------ | ------------------- |
| Rad               | Momskodkombination | Procent av nettobelopp | Nettobelopp per rad |

### <a name="calculation-and-rounding-behavior"></a>Beräknings- och avrundningsbeteende

| Radnummer | Momskod | Beloppsunderlag | Momsbelopp |
| ----------- | -------------- | ------------- | ---------------- |
| 1           | Kod 1         | 42.42         | 4.25             |
| 1           | Kod 2         | 42.42         | 4.24             |
| 2           | Kod 1         | 42.42         | 4.24             |
| 2           | Kod 2         | 42.42         | 4.24             |

Skattebasbeloppet beräknas per rad:

- **Rad 1:** 42,42
- **Rad 2:** 42,42

Momsbeloppet beräknas per momskod:

- **Rad 1:**

    - Momsbelopp för momskod 1 = 42,42 &times; 10 procent = 4,242
    - momsbelopp för momskod 2 = 42,42 &times; 10 procent = 4,242

- **Rad 2:**

    - Momsbelopp för momskod 1 = 42,42 &times; 10 procent = 4,242
    - Momsbelopp för momskod 2 = 42,42 &times; 10 procent = 4,242

Momsbeloppet avrundas per momskod kombinationer:

- Totalt momsbelopp = 4,242 + 4,242 + 4,242 + 4,242 = 16,968, som rundas av upp till 16,97

Det avrundade momsbeloppet tilldelas varje rad per momskod:

- Fördela momsbeloppet (16,97) till rad 1 och rad 2:

    - **Rad 1:**

        - Momsbelopp för momskod 1 = 4,25
        - Momsbelopp för momskod 2 = 4,24

    - **Rad 2:**

        - Momsbelopp för momskod 1 = 4,24
        - Momsbelopp för momskod 2 = 4,24

## <a name="example-6"></a>Exempel 6

### <a name="parameter-values"></a>Parametervärden

| Beräkningsmetod | Avrundning efter                | Ursprung                   | Bidragsunderlag                 |
| ------------------ | -------------------------- | ------------------------ | ----------------------------- |
| Rad/total         | Momskodkombination | Procent av nettobelopp | Nettobelopp av fakturasaldo |

### <a name="calculation-and-rounding-behavior"></a>Beräknings- och avrundningsbeteende

| Radnummer | Momskod | Beloppsunderlag | Momsbelopp |
| ----------- | -------------- | ------------- | ---------------- |
| 1           | Kod 1         | 42.42         | 4.25             |
| 1           | Kod 2         | 42.42         | 4.24             |
| 2           | Kod 1         | 42.42         | 4.24             |
| 2           | Kod 2         | 42.42         | 4.24             |

Skattebasbeloppet beräknas per dokument:

- Momsbasbelopp = 42,42 + 42,42 = 84,84

Momsbeloppet beräknas per momskod:

- Momsbelopp för momskod 1 = 84,84 &times; 10 procent = 8,484
- Momsbelopp för momskod 2 = 84,84 &times; 10 procent = 8,484

Momsbeloppet avrundas per momskod kombinationer:

- Totalt momsbelopp = 8,484 + 8,484 = 16,968, som rundas av upp till 16,97

Det avrundade momsbeloppet tilldelas varje rad per momskod:

- Fördela momsbeloppet (16,97) till rad 1 och rad 2:

    - **Rad 1:**

        - Momsbelopp för momskod 1 = 4,25
        - Momsbelopp för momskod 2 = 4,24

    - **Rad 2:**

        - Momsbelopp för momskod 1 = 4,24
        - Momsbelopp för momskod 2 = 4,24

## <a name="example-7"></a>Exempel 7

### <a name="parameter-values"></a>Parametervärden

| Beräkningsmetod | Avrundning efter                | Ursprung                              | Bidragsunderlag       |
| ------------------ | -------------------------- | ----------------------------------- | ------------------- |
| Rad               | Momskodkombination | Beräknad procent av nettobeloppet | Nettobelopp per rad |

### <a name="calculation-and-rounding-behavior"></a>Beräknings- och avrundningsbeteende

| Radnummer | Momskod | Beloppsunderlag | Momsbelopp |
| ----------- | -------------- | ------------- | ---------------- |
| 1           | Kod 1         | 42.42         | 4.72             |
| 1           | Kod 2         | 42.42         | 4.71             |
| 2           | Kod 1         | 42.42         | 4.71             |
| 2           | Kod 2         | 42.42         | 4.72             |

Skattebasbeloppet beräknas per rad:

- **Rad 1:** 42,42
- **Rad 2:** 42,42

Momsbeloppet beräknas per momskod:

- **Rad 1:**

    - Momsbelopp för momskod 1 = 42,42 &times; 10 procent &divide; (1 – 10 procent) = 4,7133
    - Momsbelopp för momskod 2 = 42,42 &times; 10 procent &divide; (1 – 10 procent) = 4,7133

- **Rad 2:**

    - Momsbelopp för momskod 1 = 42,42 &times; 10 procent &divide; (1 – 10 procent) = 4,7133
    - Momsbelopp för momskod 2 = 42,42 &times; 10 procent &divide; (1 – 10 procent) = 4,7133

Momsbeloppet avrundas per momskod kombinationer:

- Totalt momsbelopp = 4,7133 + 4,7133 + 4,7133 + 4,7133 = 18,8532, som rundas av upp till 18,86

Det avrundade momsbeloppet tilldelas varje rad per momskod:

- Fördela momsbeloppet (18,86) till rad 1 och rad 2:

    - **Rad 1:**

        - Momsbelopp för momskod 1 = 4,72
        - Momsbelopp för momskod 2 = 4,71

    - **Rad 2:**

        - Momsbelopp för momskod 1 = 4,71
        - Momsbelopp för momskod 2 = 4,72

## <a name="example-8"></a>Exempel 8

### <a name="parameter-values"></a>Parametervärden

| Beräkningsmetod | Avrundning efter                | Ursprung                              | Bidragsunderlag                 |
| ------------------ | -------------------------- | ----------------------------------- | ----------------------------- |
| Rad/total         | Momskodkombination | Beräknad procent av nettobeloppet | Nettobelopp av fakturasaldo |

### <a name="calculation-and-rounding-behavior"></a>Beräknings- och avrundningsbeteende

| Radnummer | Momskod | Beloppsunderlag | Momsbelopp |
| ----------- | -------------- | ------------- | ---------------- |
| 1           | Kod 1         | 42.42         | 4.72             |
| 1           | Kod 2         | 42.42         | 4.71             |
| 2           | Kod 1         | 42.42         | 4.71             |
| 2           | Kod 2         | 42.42         | 4.72             |

Skattebasbeloppet beräknas per dokument:

- Momsbasbelopp = 42,42 + 42,42 = 84,84

Momsbeloppet beräknas per momskod:

- Momsbelopp för momskod 1 = 84,84 &times; 10 procent &divide; (1 – 10 procent) = 9,4267
- Momsbelopp för momskod 2 = 84,84 &times; 10 procent &divide; (1 – 10 procent) = 9,4267

Momsbeloppet avrundas per momskod kombinationer:

- Totalt momsbelopp = 9,4267 + 9,4267 = 18,8534, som rundas av upp till 18,86

Det avrundade momsbeloppet tilldelas varje rad per momskod:

- Fördela momsbeloppet (18,86) till rad 1 och rad 2:

    - **Rad 1:**

        - Momsbelopp för momskod 1 = 4,72
        - Momsbelopp för momskod 2 = 4,71

    - **Rad 2:**

        - Momsbelopp för momskod 1 = 4,71
        - Momsbelopp för momskod 2 = 4,72

## <a name="additional-resources"></a>Ytterligare resurser

- [Momsberäkningsmetoder i fältet Ursprung](sales-tax-calculation-methods-origin-field.md)
- [Momssatser baserade på fälten Bidragsunderlag och Beräkningsmetoder](marginal-base-field.md)
- [Beräkningsalternativ för hela beloppet och intervall för momskoder](whole-amount-interval-options-sales-tax-codes.md)
