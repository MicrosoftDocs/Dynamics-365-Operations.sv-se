---
title: Scenarier för justeringsdatum
description: Det här avsnittet innehåller exempel som visar hur justeringsdatum fungerar vid prenumerationsfakturering.
author: JodiChristiansen
ms.date: 11/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: 91480fecd16cf8417722df73c28bbd81d029fb07
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/04/2022
ms.locfileid: "8690485"
---
# <a name="alignment-date-scenarios"></a>Scenarier för justeringsdatum

Det här avsnittet innehåller exempel som visar hur justeringsdatum fungerar vid prenumerationsfakturering.

I de här exemplen finns det ett faktureringsdetalj för ett faktureringsschema som har justeringsdatumet 31 oktober 2019. Den första faktureringsdetaljen för raden slutar den 31 oktober 2019 och delräknas enligt detta. Raden förnyas automatiskt genom att du använder ett startdatum för startdatumet 11 november.

> [!NOTE]
> Året är relevant eftersom det kan leda till att justeringsdatumet blir mer eller lägre än ett år. För dessa exempel är prorationsmetoden inställd på **Månatlig** på sidan **Faktureringsparametrar för återkommande kontrakt**. Om det ställs in på **Daglig** skiljer sig vissa delbelopp åt.

## <a name="scenario-1-no-alignment"></a>Scenario 1: Ingen justering

Faktureringsschemat ställs in med följande data:

- **Startdatum:** 1 maj 2019
- **Slutdatum:** 31 december, 2024
- **Belopp:** 1 000 $

| Faktureringsstartdatum | Faktureringsslutdatum | Föregående avläsning | Aktuell avläsning | Kvantitet har angetts | Fri kvantitet | Fakturerbar kvantitet | Pris per enhet |
|---|---|---|---|---|---|---|---|
| 5/1/2019 | 2020-04-30 | | | 1.00 | | 1.00 | 1,000.00 |
| 5/1/2020 | 4/30/2021 | | | 1.00 | | 1.00 | 1,000.00 |
| 5/1/2021 | 4/30/2022 | | | 1.00 | | 1.00 | 1,000.00 |
| 5/1/2022 | 4/30/2023 | | | 1.00 | | 1.00 | 1,000.00 |
| 5/1/2023 | 4/30/2024 | | | 1.00 | | 1.00 | 1,000.00 |
| 5/1/2024 | 12/31/2024 | | | 1.00 | | 1.00 | 666.67 |

## <a name="scenario-2-shortened-alignment"></a>Scenario 2: Förkortad justering

Faktureringsschemat ställs in med följande data:

- **Startdatum:** 1 maj 2019
- **Slutdatum:** 31 december, 2024
- **Belopp:** 1 000 $
- **Justeringsdatum:** 31 december 2019

Det första belopp som används är under ett år.

| Faktureringsstartdatum | Faktureringsslutdatum | Föregående avläsning | Aktuell avläsning | Kvantitet har angetts | Fri kvantitet | Fakturerbar kvantitet | Pris per enhet |
|---|---|---|---|---|---|---|---|
| 5/1/2019 | 12/31/2019 | | | 1.00 | | 1.00 | 666.67 |
| 1/1/2020 | 12/31/2020 | | | 1.00 | | 1.00 | 1,000.00 |
| 1/1/2021 | 12/31/2021 | | | 1.00 | | 1.00 | 1,000.00 |
| 2022-01-01 | 12/31/2022 | | | 1.00 | | 1.00 | 1,000.00 |
| 1/1/2023 | 12/31/2023 | | | 1.00 | | 1.00 | 1,000.00 |
| 1/1/2024 | 12/31/2024 | | | 1.00 | | 1.00 | 1,000.00 |

## <a name="scenario-3-extended-alignment"></a>Scenario 3: Utökad justering

Faktureringsschemat ställs in med följande data:

- **Startdatum:** 1 maj 2019
- **Slutdatum:** 31 december, 2024
- **Belopp:** 1 000 $
- **Justeringsdatum:** 31 december 2020

Det första belopp som används är mer än ett år.

| Faktureringsstartdatum | Faktureringsslutdatum | Föregående avläsning | Aktuell avläsning | Kvantitet har angetts | Fri kvantitet | Fakturerbar kvantitet | Pris per enhet |
|---|---|---|---|---|---|---|---|
| 5/1/2019 | 12/31/2020 | | | 1.00 | | 1.00 | 1,666.67 |
| 1/1/2021 | 12/31/2021 | | | 1.00 | | 1.00 | 1,000.00 |
| 2022-01-01 | 12/31/2022 | | | 1.00 | | 1.00 | 1,000.00 |
| 1/1/2023 | 12/31/2023 | | | 1.00 | | 1.00 | 1,000.00 |
| 1/1/2024 | 12/31/2024 | | | 1.00 | | 1.00 | 1,000.00 |

## <a name="scenario-4-alignment-with-a-different-end-month"></a>Scenario 4: Justering med en annan slutmånad

Faktureringsschemat ställs in med följande data:

- **Startdatum:** 1 maj 2019
- **Slutdatum:** 31 oktober 2024
- **Belopp:** 1 000 $
- **Justeringsdatum:** 31 december 2019

> [!NOTE]
> Detta scenario är inte vanligt.

| Faktureringsstartdatum | Faktureringsslutdatum | Föregående avläsning | Aktuell avläsning | Kvantitet har angetts | Fri kvantitet | Fakturerbar kvantitet | Pris per enhet |
|---|---|---|---|---|---|---|---|
| 5/1/2019 | 12/31/2019 | | | 1.00 | | 1.00 | 666.67 |
| 1/1/2020 | 12/31/2020 | | | 1.00 | | 1.00 | 1,000.00 |
| 1/1/2021 | 12/31/2021 | | | 1.00 | | 1.00 | 1,000.00 |
| 2022-01-01 | 12/31/2022 | | | 1.00 | | 1.00 | 1,000.00 |
| 1/1/2023 | 12/31/2023 | | | 1.00 | | 1.00 | 1,000.00 |
| 1/1/2024 | 10/31/2024 | | | 1.00 | | 1.00 | 833.33 |

## <a name="scenario-5-single-partial-year"></a>Scenario 5: Enstaka delår

Faktureringsschemat ställs in med följande data:

- **Startdatum:** 1 maj 2019
- **Slutdatum:** 31 december, 2019
- **Belopp:** 1 000 $
- **Justeringsdatum**: 31 december 2019

I det här scenariot behövs inte justeringsdatumet. Detta scenario är vanligt för automatiska misstag.

| Faktureringsstartdatum | Faktureringsslutdatum | Föregående avläsning | Aktuell avläsning | Kvantitet har angetts | Fri kvantitet | Fakturerbar kvantitet | Pris per enhet |
|---|---|---|---|---|---|---|---|
| 5/1/2019 | 12/31/2019 | | | 1.00 | | 1.00 | 666.67 |

## <a name="scenario-6-calculated-dates"></a>Scenario 6: Beräknade datum

Stöd och förnyelse ställs in med följande data:

- **Åsidosätt startdatum:** Nej
- **Startdatum för support och som inte kan förnyas:** Början på nästa månad
- **Fakturabokföringsdatum:** 22 juni 2019
- **Justeringsdatum:** 31 december 2020

| Faktureringsstartdatum | Faktureringsslutdatum | Föregående avläsning | Aktuell avläsning | Kvantitet har angetts | Fri kvantitet | Fakturerbar kvantitet | Pris per enhet |
|---|---|---|---|---|---|---|---|
| 7/1/2019 | 7/31/2019 | | | 1.00 | | 1.00 | 297.60 |
| 8/1/2019 | 12/31/2020 | | | 1.00 | | 1.00 | 6,936.00 |

## <a name="scenario-7-calculated-dates-and-future-posting"></a>Scenario 7: Beräknade datum och framtida bokföring

Stöd och förnyelse ställs in med följande data:

- **Åsidosätt startdatum:** Nej
- **Startdatum för support och som inte kan förnyas:** Början på nästa månad
- **Fakturabokföringsdatum:** 22 juni 2019
- **Justeringsdatum:** 31 december 2020

Justeringsdatumet ändras till 31 december 2021 i det här scenariot.

| Faktureringsstartdatum | Faktureringsslutdatum | Föregående avläsning | Aktuell avläsning | Kvantitet har angetts | Fri kvantitet | Fakturerbar kvantitet | Pris per enhet |
|---|---|---|---|---|---|---|---|
| 6/22/2019 | 6/22/2019 | | | 1.00 | | 1.00 | 0,00 |
| 8/1/2019 | 12/31/2020 | | | 1.00 | | 1.00 | 4,250.00 |

## <a name="scenario-8-manual-dates-and-multiple-years"></a>Scenario 8: Manuella datum och flera år

Stöd och förnyelse ställs in med följande data:

- **Åsidosätt startdatum:** Ja
- **Startdatum för förnyelse:** 1 juli 2020
- **Slutdatum för förnyelse:** 31 december 2024
- **Justeringsdatum:** 31 december 2021

| Faktureringsstartdatum | Faktureringsslutdatum | Föregående avläsning | Aktuell avläsning | Kvantitet har angetts | Fri kvantitet | Fakturerbar kvantitet | Pris per enhet |
|---|---|---|---|---|---|---|---|
| 6/22/2019 | 6/22/2019 | | | 1.00 | | 1.00 | 0,00 |
| 7/1/2020 | 12/31/2021 | | | 1.00 | | 1.00 | 375.00 |
| 2022-01-01 | 12/31/2022 | | | 1.00 | | 1.00 | 250.00 |
| 1/1/2023 | 12/31/2023 | | | 1.00 | | 1.00 | 250.00 |
| 1/1/2024 | 12/31/2024 | | | 1.00 | | 1.00 | 250.00 |

## <a name="scenario-9-manual-dates-multiple-years-and-a-different-end-month"></a>Scenario 9: Manuella datum, flera år och en annan slutmånad

Stöd och förnyelse ställs in med följande data:

- **Åsidosätt startdatum:** Ja
- **Startdatum för förnyelse:** 1 juli 2020
- **Slutdatum för förnyelse:** 31 oktober 2024
- **Justeringsdatum:** 31 december 2021

| Faktureringsstartdatum | Faktureringsslutdatum | Föregående avläsning | Aktuell avläsning | Kvantitet har angetts | Fri kvantitet | Fakturerbar kvantitet | Pris per enhet |
|---|---|---|---|---|---|---|---|
| 6/22/2019 | 6/22/2019 | | | 1.00 | | 1.00 | 0,00 |
| 7/1/2020 | 12/31/2021 | | | 1.00 | | 1.00 | 375.00 |
| 2022-01-01 | 12/31/2022 | | | 1.00 | | 1.00 | 250.00 |
| 1/1/2023 | 12/31/2023 | | | 1.00 | | 1.00 | 250.00 |
| 1/1/2024 | 10/31/2024 | | | 1.00 | | 1.00 | 208.33 |

## <a name="scenario-10-alignment-without-proration"></a>Scenario 10: Justering utan proportionell fördelning

Stöd och förnyelse ställs in med följande data:

- **Åsidosätt startdatum:** Nej
- **Fakturabokföringsdatum:** 22 juni 2019
- **Justeringsdatum:** 31 december 2019

Startdatumet och justeringsdatumen justeras så att båda startdatumen inträffar efter bokföringsdatumet.

- **Startdatum för förnyelse:** 1 januari 2020
- **Slutdatum för förnyelse:** 31 december 2020
