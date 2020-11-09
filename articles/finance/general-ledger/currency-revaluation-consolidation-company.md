---
title: Valutaomvärdering i ett konsolideringsföretag
description: Detta avsnitt beskriver hur du omvärderar valuta i ett konsolideringsföretag.
author: roschlom
manager: AnnBe
ms.date: 10/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerExchAdjHist
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 62183
ms.assetid: 2762baaf-0c10-4ff7-8713-c506d6c29b98
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 33db12388c969b8dadb38bfacf4d9df333b78bd4
ms.sourcegitcommit: 49f3011b8a6d8cdd038e153d8cb3cf773be25ae4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/16/2020
ms.locfileid: "4014993"
---
# <a name="currency-revaluation-in-a-consolidation-company"></a>Valutaomvärdering i ett konsolideringsföretag

[!include [banner](../includes/banner.md)]

När du konsolidera data från en redovisningsvaluta till en annan måste du fortfarande köra valutaomvärdering om det sker en förändring i valutakurser, så att ditt konto saldo är korrekt omvärderas. När du ursprungligen konsolidera data, använd **valutakursdifferens** flik för att välja den första växelkurser för översättning under konsolideringsprocessen. Efter en ny valutakurs registreras (t.ex. i nästa månad), du måste omvärdera den kontosaldon. Den orealiserade vinster eller förluster som sedan uppdateras baserat på den nya växelkursen och datum. Följande exempel illustrerar bokföringsposter som skapas under processen.

## <a name="company-setup"></a>Företagsinställningar
-   **Källa/driftbolaget (USMF)** – US dollar (USD) används som redovisning och rapportering valuta.
-   **Koncernens bolag (CON)** – EURO (EUR) används som redovisning och rapportering valuta.
    -   **Vinsten** – reskontra 801500
    -   **Förlusten** – reskontra 801600
    -   **Orealiserad vinst** – reskontra 801600
    -   **Orealiserad förlust** – reskontra 801400

## <a name="original-transactions"></a>Ursprungliga transaktioner
### <a name="cash-receipt-transactions-in-usmf"></a>Kontantkvitto transaktioner i USMF

| Datum       | Redovisningskonto               | Valuta | Belopp |
|------------|------------------------------|----------|--------|
| 10/11/2015 | 110110 – Kassa                | USD      | 500    |
| 10/11/2015 | 130100 – Kundfordringar | USD      | -500   |

## <a name="exchange-rates"></a>Valutakurser

| Från valuta | Till valuta | Startdatum | Valutakurs |
|---------------|-------------|------------|---------------|
| Euro           | USD         | 10/1/2015  | 200           |
| Euro           | USD         | 11-01 2015  | 150           |
| Euro           | USD         | 12/1/2012  | 100           |

## <a name="perform-the-consolidation-for-october-2015"></a>Utföra konsolideringen för oktober 2015
### <a name="balances-in-the-consolidation-company"></a>Saldon i fältet konsolideringsföretag

| Redovisningskonto | Valuta | Belopp | Beräkning    |
|----------------|----------|--------|----------------|
| 110110         | Euro      | 250    | 500 USD × 50 %  |
| 130100         | Euro      | -250   | -500 USD × 50% |

## <a name="perform-currency-revaluation-for-the-accounts-from-october-1-2015-through-november-30-2015"></a>Utföra valutaomvärdering för räkenskaper från den 1 oktober 2015, genom den 30 November, 2015
### <a name="balances-in-the-consolidation-company"></a>Saldon i fältet konsolideringsföretag

| Redovisningskonto | Valuta | Belopp  | Beräkning                        |
|----------------|----------|---------|------------------------------------|
| 110110         | Euro      | 333,33  | Ursprungligt belopp av 500 × 66,6667 %  |
| 130100         | Euro      | -333,33 | Ursprungligt belopp -500 × 66,6667 % |
| 801400         | Euro      | 83,33   | 333,33 – 250                       |
| 801600         | Euro      | -83,33  | -333,33 – (-250)                   |

Du kommer att se ytterligare transaktioner för rapportering valuta.

## <a name="perform-currency-revaluation-for-the-accounts-from-october-1-2015-through-december-31-2015"></a>Utföra valutaomvärdering för räkenskaper från 1 oktober 2015 till 31 December 2015
### <a name="balances-in-the-consolidation-company"></a>Saldon i fältet konsolideringsföretag

| Redovisningskonto | Valuta | Belopp  | Beräkning                                          |
|----------------|----------|---------|------------------------------------------------------|
| 110110         | Euro      | 500.00  | Ursprungligt belopp av 500 × 1                           |
| 130100         | Euro      | -500,00 | Ursprungligt belopp -500 × 1                          |
| 801400         | Euro      | 250     | 500 – 333,33 = 166,67 166,67 83,33 + = 250           |
| 801600         | Euro      | -250    | -500 – (-333,33) = -166,67 -166,67 + (-83,33) = -250 |





