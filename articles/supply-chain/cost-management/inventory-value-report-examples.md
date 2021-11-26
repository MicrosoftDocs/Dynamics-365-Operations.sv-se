---
title: Exempel och logik rörande värderapport för lager
description: Detta ämne innehåller några exempel på resultat som visas för respektive typ av lagervärdesrapport. Rapporterna för lagervärde innehåller information om fysiska och ekonomiska kvantiteter och belopp.
author: banluo-ms
ms.date: 10/19/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: banluo
ms.search.validFrom: 2021-10-19
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 4ad85058c8743895185d3da2e8975711f1e3bc2c
ms.sourcegitcommit: ba10ba2cd4fb4267afb5aacae4f6a52aa2456e7e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/11/2021
ms.locfileid: "7798399"
---
# <a name="inventory-value-report-examples-and-logic"></a>Exempel och logik rörande värderapport för lager

[!include [banner](../includes/banner.md)]

Rapporterna för lagervärde innehåller information om fysiska och ekonomiska kvantiteter och belopp. Detta ämne innehåller några exempel på resultat som visas för respektive typ av lagervärdesrapport.

Mer information om hur du genererar och använder respektive typ av lagervärdesrapport finns i [Lagervärdesrapporter](inventory-value-report-storage.md).

## <a name="sample-data-that-is-used-in-these-examples"></a>Exempeldata som används i dessa exempel

Exemplen i det här avsnittet är baserade på transaktionsdata för exempellager som beskrivs i det här avsnittet.

### <a name="storage-dimension-setup"></a>Inställningar av lagringsdimension

Exempelsystemet innehåller följande inställning av lagringsdimensioner.

| Namn | Aktiva | Fysiskt lager | Ekonomiskt lager |
|---|---|---|---|
| Webbplats | Ja | Ja | Ja |
| Lagerställe | Ja | Ja | Nej |

### <a name="inventory-model"></a>Lagermodell

I exempelsystemet är lagermodellen för de frisläppta produkterna *FIFO* och fältet **Självkostnad** för lagermodellen är *Inkludera fysiskt värde*.

### <a name="inventory-transactions"></a>Lagertransaktioner

Exempelsystemet innehåller följande lagertransaktioner för en frisläppt produkt som har artikelnumret *B0001*.

| Referens | Webbplats | Lagerställe | Inleverans | Problem | Fysiskt datum | Ekonomiskt datum | Kvantitet | Kostnadsbelopp | Fysiskt kostnadsbelopp |
|---|---|---|---|---|---|---|---|---|---|
| Inköpsorder | 1 | 11 | Inköpt | | 15 mars | 15 mars | 10 | 1 000 | 1 000 |
| Inköpsorder | 2 | 21 | Inköpt | | 15 mars | 15 mars | 10 | 2,000 | 2,000 |
| Inköpsorder | 1 | 11 | Inlevererat | | 15 april | | 5 | | 375 |
| Överföringsorder | 1 | 11 | | Sålt | 2 maj | 2 maj | -5 | -458,33 | -458,33 |
| Överföringsorder | 1 | 12 | Inköpt | | 2 maj | 2 maj | 5 | 458.33 | 458.33 |
| Försäljningsorder | 1 | 12 | | Sålt | 3 maj | 3 maj | -1 | -91,67 | -91,67 |

### <a name="inventory-value-report-configuration"></a>Konfiguration av lagervärdesrapport

I exempelsystemet ingår en konfiguration av en lagervärdesrapport med följande inställningar:

- **Intervall:**  *Bokföringsdatum*
- **Lager:** *Ja*
- **Beräkna genomsnittlig enhetskostnad:** *Ja*
- **Total kvantitet och värde:** *Ja*
- **Plats, visa:** *Vald*
- **Resurs-ID, visa:** *Ja*
- **Nivå:** *Summor*

## <a name="inventory-value-report-example-1"></a>Lagervärdesrapport, exempel 1

I följande tabell och illustrationer visas resultaten när du använder den exempeldata och rapportkonfiguration som beskrevs tidigare i det här avsnittet.

| Resurstyp | Resurs | Webbplats | Referens | Lager: Ekonomisk kvantitet | Lager: Ekonomiskt belopp | Lager: Bokförd fysisk kvantitet | Lager: Bokfört fysiskt belopp | Lager: Kvantitet | Lager: Belopp | Genomsnittlig enhetskostnad |
|---|---|---|---|---|---|---|---|---|---|---|
| Material | B0001 | 1 | Utgående balans | 9.00 | 908.33 | 5.00 | 375.00 | 14,00 | 1,283.33 | 91.67 |
| Material | B0001 | 2 | Utgående balans | 10,00 | 2,000.00 | 0,00 | 0,00 | 10,00 | 2,000.00 | 200.00 |

### <a name="standard-inventory-value-report-for-example-1"></a>Standardlagervärdesrapport för exempel 1

I följande bild visas standardrapporten **Lagervärde** fär exempel 1. (Välj illustrationen om du vill öppna en större version.)

[![Standardlagervärdesrapport för exempel 1.](media/inventory-value-report-ex1-small.png "Lagervärdesrapport för exempel 1")](media/inventory-value-report-ex1.png)

### <a name="inventory-value-report-storage-report-for-example-1"></a>Lagring av lagervärdesrapport för exempel 1

I följande bild visas rapporten **Lagring av lagervärdesrapport** för exempel 1. (Välj illustrationen om du vill öppna en större version.)

[![Lagring av lagervärdesrapport för exempel 1.](media/inventory-value-report-storage-ex1-small.png "Lagring av lagervärdesrapport för exempel 1")](media/inventory-value-report-storage-ex1.png)

## <a name="inventory-value-report-example-2"></a>Lagervärdesrapport, exempel 2

I följande tabell och illustrationer visas resultaten när du använder exempeldata som beskrivs tidigare i det här avsnittet, men du ändrar värdet i fältet **Nivå** till *Transaktioner* i rapportkonfigurationen, och du anger fältet **Från datum** som *15 mars* när du kör rapporten.

| Resurstyp | Resurs | Webbplats | Datum | Nummer | Referens | Lager: Ekonomisk kvantitet | Lager: Ekonomiskt belopp | Lager: Bokförd fysisk kvantitet | Lager: Bokfört fysiskt belopp | Lager: Kvantitet | Lager: Belopp |
|---|---|---|---|---|---|---|---|---|---|---|---|
| Material | B0001 | 1 | 2021-03-15 | 00000126 | Inköpsorder | 0,00 | 0,00 | 10,00 | 1,000.00 | **10.00** | **1,000.00** |
| Material | B0001 | 1 | 2021-03-15 | 00000126 | Inköpsorder | 10,00 | 1,000.00 | -10.00 | -1 000,00 | **0.00** | **0.00** |
| Material | B0001 | 1 | 2021-04-15 | 00000128 | Inköpsorder | 0,00 | 0,00 | 5.00 | 375.00 | **5.00** | **375.00** |
| Material | B0001 | 1 | 2021-05-02 | 000003 | Överföringsorderförsändelse | -5,00 | -458,33 | 0,00 | 0,00 | **-5,00** | **-458,33** |
| Material | B0001 | 1 | 2021-05-02 | 000003 | Överföringsorderinleverans | 5.00 | 458.33 | 0,00 | 0,00 | **5.00** | **458.33** |
| Material | B0001 | 1 | 2021-05-03 | 000835 | Försäljningsorder | 0,00 | 0,00 | -1,00 | -91,67 | **-1,00** | **-91,67** |
| Material | B0001 | 1 | 2021-05-03 | 000835 | Försäljningsorder | -1,00 | -91,67 | 1.00 | 91.67 | **0.00** | **0.00** |
| Material | B0001 | 2 | 2021-03-15 | 00000127 | Inköpsorder | 0,00 | 0,00 | 10,00 | 2,000.00 | **10.00** | **2,000.00** |
| Material | B0001 | 2 | 2021-03-15 | 00000127 | Inköpsorder | 10,00 | 2,000.00 | -10.00 | - 2 000,00 | **0.00** | **0.00** |
| Material | B0001 | 2 | 2021-05-02 | 000003 | Överföringsorderförsändelse | 5.00 | 458.33 | 0,00 | 0,00 | **5.00** | **458.33** |
| Material | B0001 | 2 | 2021-05-02 | 000003 | Överföringsorderinleverans | -5,00 | -458,33 | 0,00 | 0,00 | **-5,00** | **-458,33** |

### <a name="standard-inventory-value-report-for-example-2"></a>Standardlagervärdesrapport för exempel 2

I följande bild visas standardrapporten **Lagervärde** för exempel 2. (Välj illustrationen om du vill öppna en större version.)

[![Standardlagervärdesrapport för exempel 2.](media/inventory-value-report-ex2-small.png "Lagervärdesrapport för exempel 2")](media/inventory-value-report-ex2.png)

### <a name="inventory-value-report-storage-report-for-example-2"></a>Lagring av lagervärdesrapport för exempel 2

I följande bild visas rapporten **Lagring av lagervärdesrapport** för exempel 2. (Välj illustrationen om du vill öppna en större version.)

[![Lagring av lagervärdesrapport för exempel 2.](media/inventory-value-report-storage-ex2-small.png "Lagring av lagervärdesrapport för exempel 2")](media/inventory-value-report-storage-ex2.png)

## <a name="inventory-value-report-example-3"></a>Lagervärdesrapport, exempel 3

Vi rekommenderar att du kör lagervärdesrapporter efter omberäkning eller lagerstängning, så att du har de transaktioner och belopp som påverkas av omberäkningen eller lagerstängningen.

Följande delgrupper visar de lagervärdesrapporter som genereras efter att du stänger lagret till den 30 maj.

### <a name="example-3-when-the-totals-level-is-used"></a>Exempel 3 när nivån Summor används

I följande tabell visas resultaten när du använder den exempeldata och rapportkonfiguration som beskrevs tidigare i det här ämnet. (I den rapportkonfigurationen måste fältet **Nivå** anges till *Summor*.)

| Resurstyp | Resurs | Webbplats | Referens | Lager: Ekonomisk kvantitet | Lager: Ekonomiskt belopp | Lager: Bokförd fysisk kvantitet | Lager: Bokfört fysiskt belopp | Lager: Kvantitet | Lager: Belopp | Genomsnittlig enhetskostnad |
|---|---|---|---|---|---|---|---|---|---|---|
| Material | B0001 | 1 | Utgående balans | 9.00 | 900.00 | 5.00 | 375.00 | 14,00 | 1,275.00 | 91.07 |
| Material | B0001 | 2 | Utgående balans | 10,00 | 2,000.00 | 0,00 | 0,00 | 10,00 | 2,000.00 | 200.00 |

### <a name="example-3-when-the-transactions-level-is-used"></a>Exempel 3 när nivån Transaktioner används

Följande tabell visar resultaten när du använder exempeldata som beskrivs tidigare i det här avsnittet, men du ändrar värdet i fältet **Nivå** till *Transaktioner* i rapportkonfigurationen.

| Resurstyp | Resurs | Webbplats | Datum | Nummer | Referens | Lager: Ekonomisk kvantitet | Lager: Ekonomiskt belopp | Lager: Bokförd fysisk kvantitet | Lager: Bokfört fysiskt belopp | Lager: Kvantitet | Lager: Belopp |
|---|---|---|---|---|---|---|---|---|---|---|---|
| Material | B0001 | 1 | 2021-03-15 | 00000126 | Inköpsorder | 0,00 | 0,00 | 10,00 | 1,000.00 | 10,00 | 1,000.00 |
| Material | B0001 | 1 | 2021-03-15 | 00000126 | Inköpsorder | 10,00 | 1,000.00 | -10.00 | -1 000,00 | 0,00 | 0,00 |
| Material | B0001 | 1 | 2021-04-15 | 00000128 | Inköpsorder | 0,00 | 0,00 | 5.00 | 375.00 | 5.00 | 375.00 |
| Material | B0001 | 1 | 2021-05-02 | 000003 | Överföringsorderförsändelse | -5,00 | -458,33 | 0,00 | 0,00 | -5,00 | -458,33 |
| Material | B0001 | 1 | 2021-05-02 | 000003 | Överföringsorderinleverans | 5.00 | 458.33 | 0,00 | 0,00 | 5.00 | 458.33 |
| Material | B0001 | 1 | 2021-05-03 | 000835 | Försäljningsorder | 0,00 | 0,00 | -1,00 | -91,67 | -1,00 | -91,67 |
| Material | B0001 | 1 | 2021-05-03 | 000835 | Försäljningsorder | -1,00 | -91,67 | 1.00 | 91.67 | 0,00 | 0,00 |
| Material | B0001 | 1 | 2021-05-31 | 000835 | Försäljningsorder | 0,00 | -8,33 | 0,00 | 0,00 | 0,00 | -8,33 |
| Material | B0001 | 1 | 2021-05-31 | 000003 | Överföringsorderförsändelse | 0,00 | -41,67 | 0,00 | 0,00 | 0,00 | -41,67 |
| Material | B0001 | 1 | 2021-05-31 | 000003 | Överföringsorderinleverans | 0,00 | 41.67 | 0,00 | 0,00 | 0,00 | 41.67 |
| Material | B0001 | 2 | 2021-03-15 | 00000127 | Inköpsorder | 0,00 | 0,00 | 10,00 | 2,000.00 | 10,00 | 2,000.00 |
| Material | B0001 | 2 | 2021-03-15 | 00000127 | Inköpsorder | 10,00 | 2,000.00 | -10.00 | - 2 000,00 | 0,00 | 0,00 |
| Material | B0001 | 2 | 2021-05-02 | 000003 | Överföringsorderförsändelse | 5.00 | 458.33 | 0,00 | 0,00 | 5.00 | 458.33 |
| Material | B0001 | 2 | 2021-05-02 | 000003 | Överföringsorderinleverans | -5,00 | -458,33 | 0,00 | 0,00 | -5,00 | -458,33 |
| Material | B0001 | 2 | 2021-05-31 | 000003 | Överföringsorderförsändelse | 0,00 | 41.67 | 0,00 | 0,00 | 0,00 | 41.67 |
| Material | B0001 | 2 | 2021-05-31 | 000003 | Överföringsorderinleverans | 0,00 | -41,67 | 0,00 | 0,00 | 0,00 | -41,67 |
