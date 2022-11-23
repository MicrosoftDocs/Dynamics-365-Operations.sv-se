---
title: Ta en kassarabatt utanför kassarabattperioden
description: Den här artikeln tillhandahåller två scenarier som visar hur en kassarabatt kan utnyttjas även om betalningen görs utanför kassarabattperioden.
author: angelad116
ms.date: 10/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: twheeloc
ms.custom: 14301
ms.assetid: bad10b7f-e550-4742-9261-8a094c9c624d
ms.search.region: Global
ms.author: angelading
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 26b1eb5e542acf7496d1a0cf7196716a5de75e4e
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/16/2022
ms.locfileid: "9780593"
---
# <a name="take-a-cash-discount-outside-the-cash-discount-period"></a>Ta en kassarabatt utanför kassarabattperioden

[!include [banner](../includes/banner.md)]

Den här artikeln tillhandahåller två scenarier som visar hur en kassarabatt kan utnyttjas även om betalningen görs utanför kassarabattperioden.

Den 28 juni skapar April en faktura för 1 000,00 för leverantör 3052. Fakturan har en kassarabatt på 1 procent om fakturan är betald inom 14 dagar.

## <a name="use-cash-discount-option--always"></a>Alternativet Utnyttja kassarabatt = Alltid
April skapar en betalning den 1 juli, vilket är efter rabattdatumet. April öppnar sidan **Kvitta transaktioner** för att visa transaktionerna som kan kvittas. 

April markerar fakturan för betalning. Ingen kassarabatt utnyttjas, eftersom betalningen görs efter båda rabattperioder. Leverantören har emellertid gett April godkännande att utnyttja kassarabatt ändå. Därför ändrar April värdet i fältet **Använd kassarabatt** till **Alltid**.

| Markera     | Använd kassarabatt | Verifikation   | Konto | Kassarabattdatum | Förfallodatum  | Faktura | Belopp i transaktionsvalutan | Valuta | Belopp att kvitta |
|----------|-------------------|-----------|---------|--------------------|-----------|---------|--------------------------------|----------|------------------|
| Markerad | Alltid            | Fakt- 10030 | 3052    | 6/28/2020          | 7/12/2020 | 10030   | - 2 000,00                      | USD      | - 1 980,00        |

Information om rabatten visas längst ned på sidan **Kvitta transaktioner**.

| Fält                        | Värde     |
|------------------------------|-----------|
| Kassarabattdatum           | 7/12/2020 |
| Kassarabattbelopp         | -20,00    |
| Använd kassarabatt            | Alltid    |
| Utnyttjad kassarabatt          | 0,00      |
| Kassarabattbelopp att utnyttja | -20,00    |

## <a name="date-to-use-for-calculating-discounts--selected-date"></a>Datum som ska användas för att beräkna rabatten = Valda datumet
Om både fakturan och betalningen har bokförts, kan fortfarande kassarabatten utnyttjas när transaktionen kvittas på sidan **Kvitta transaktioner**. April ändrar värdet i fältet **Datum som ska användas för att beräkna rabatter** till **Markerat datum**. Hon anger sedan datumet 28 juni, som infaller under fakturan kassarabattperiod. Det datumet används för att beräkna en kassarabatt för transaktionen. På sidan **Kvitta öppna transaktioner** ser April att hela rabatten på 20,00 visas som standard. Fakturaraden visar kvittningsbeloppet är 1 980,00.

| Markera          | Använd kassarabatt | Verifikation   | Konto | Kassarabattdatum | Förfallodatum  | Faktura | Belopp i transaktionsvalutan | Valuta | Belopp att kvitta |
|--------------|-------------------|-----------|---------|--------------------|-----------|---------|--------------------------------|----------|------------------|
| Vald och markerad | Normal    | Fakt- 10030 | 3052    | 6/28/2020         | 7/12/2020 | 10030   | - 2 000,00                      | USD      | - 1 980,00        |
| Markerad                 | Normal    | APP-10030 | 3052    | 7/15/2020          | 7/15/2020 |         | 500.00                         | USD      | 500.00           |

Information om rabatten visas längst ned på sidan **Kvitta öppna transaktioner**. Rabattbeloppet som har utnyttjats är 20,00 eftersom kvittningsbeloppet för fakturan är standardbeloppet på 1 980,00.

| Fält                        | Värde     |
|------------------------------|-----------|
| Kassarabattdatum           | 7/12/2020 |
| Kassarabattbelopp         | -20,00    |
| Använd kassarabatt            | Normal    |
| Utnyttjad kassarabatt          | 0,00      |
| Kassarabattbelopp att utnyttja | -20,00    |

Därför uppdaterar hon fakturan i fältet **Belopp att kvitta** till **500,00**. Värdet i fältet **Kassarabattbelopp att utnyttja** beräknas som **5,05**.

| Markera                     | Använd kassarabatt | Verifikation   | Konto | Datum      | Förfallodatum  | Faktura | Belopp i transaktionsvalutan | Valuta | Belopp att kvitta |
|--------------------------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Vald och markerad | Normal            | Fakt- 10030 | 3052    | 6/28/2020 | 7/12/2020 | 10030   | 2,000.00                       | USD      | -500,00          |
| Markerad                 | Normal            | APP-10030 | 3052    | 7/15/2020 | 7/15/2020 |         | 500.00                         | USD      | 500.00           |

Information om rabatten visas längst ned på sidan **Kvitta öppna transaktioner**. Värdet i fältet **Kassarabattbelopp att utnyttja** är **5,05**, eftersom kvittningsbeloppet för fakturan ändrades till betalningsbeloppet på 500,00.

| Fält                        | Värde     |
|------------------------------|-----------|
| Kassarabattdatum           | 7/12/2020 |
| Kassarabattbelopp         | -20,00    |
| Använd kassarabatt            | Normal    |
| Utnyttjad kassarabatt          | 0,00      |
| Kassarabattbelopp att utnyttja | -5,05     |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
