---
title: "Ta en kassarabatt utanför kassarabattperioden"
description: "Den här artikeln tillhandahåller två scenarier som visar hur en kassarabatt kan utnyttjas även om betalningen görs utanför kassarabattperioden."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 14301
ms.assetid: bad10b7f-e550-4742-9261-8a094c9c624d
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 3ff83f0ab68f7a87921dc2b6c3dcad43e5d331b7
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="take-a-cash-discount-outside-the-cash-discount-period"></a>Ta en kassarabatt utanför kassarabattperioden

[!include[banner](../includes/banner.md)]


Den här artikeln tillhandahåller två scenarier som visar hur en kassarabatt kan utnyttjas även om betalningen görs utanför kassarabattperioden.

Den 28 juni skapar April en faktura för 1 000,00 för leverantör 3052. Fakturan har en kassarabatt på 1 procent om fakturan är betald inom 14 dagar.

## <a name="use-cash-discount-option--always"></a>Alternativet Utnyttja kassarabatt = Alltid
April skapar en betalning den 1 juli, vilket är efter rabattdatumet. April öppnar sidan **Kvitta transaktioner** för att visa transaktionerna som kan kvittas. 

April markerar fakturan för betalning. Ingen kassarabatt utnyttjas, eftersom betalningen görs efter båda rabattperioder. Leverantören har emellertid gett April godkännande att utnyttja kassarabatt ändå. Därför ändrar April värdet i fältet **Använd kassarabatt** till **Alltid**.

| Markera     | Använd kassarabatt | Verifikation   | Konto | Kassarabattdatum | Förfallodatum  | Faktura | Belopp i transaktionsvalutan | Valuta | Belopp att kvitta |
|----------|-------------------|-----------|---------|--------------------|-----------|---------|--------------------------------|----------|------------------|
| Markerad | Alltid            | Fakt- 10030 | 3052    | 2015/06/28          | 2015/07/12 | 10030   | - 2 000,00                      | USD      | - 1 980,00        |

Information om rabatten visas längst ned på sidan **Kvitta transaktioner**.

|                              |           |
|------------------------------|-----------|
| Kassarabattdatum           | 2015/07/12 |
| Kassarabattbelopp         | -20,00    |
| Använd kassarabatt            | Alltid    |
| Utnyttjad kassarabatt          | 0,00      |
| Kassarabattbelopp att utnyttja | -20,00    |

## <a name="date-to-use-for-calculating-discounts--selected-date"></a>Datum som ska användas för att beräkna rabatten = Valda datumet
Om både fakturan och betalningen har bokförts, kan fortfarande kassarabatten utnyttjas när transaktionen kvittas på sidan **Kvitta transaktioner**. April ändrar värdet i fältet **Datum som ska användas för att beräkna rabatter** till **Markerat datum**. Hon anger sedan datumet 28 juni, som infaller under fakturan kassarabattperiod. Det datumet används för att beräkna en kassarabatt för transaktionen. På sidan **Kvitta öppna transaktioner** ser April att hela rabatten på 20,00 visas som standard. Fakturaraden visar kvittningsbeloppet är 1 980,00.

| Markera                     | Använd kassarabatt | Verifikation   | Konto | Kassarabattdatum | Förfallodatum  | Faktura | Belopp i transaktionsvalutan | Valuta | Belopp att kvitta |
|--------------------------|-------------------|-----------|---------|--------------------|-----------|---------|--------------------------------|----------|------------------|
| Vald och markerad | Normal            | Fakt- 10030 | 3052    | 2015/06/28          | 2015/07/12 | 10030   | - 2000,00                      | USD      | - 1 980,00        |
| Markerad                 | Normal            | APP-10030 | 3052    | 2015/07/12          | 2015/07/15 |         | 500.00                         | USD      | 500.00           |

Information om rabatten visas längst ned på sidan **Kvitta öppna transaktioner**. Rabattbeloppet som har utnyttjats är 20,00 eftersom kvittningsbeloppet för fakturan är standardbeloppet på 1 980,00.

|                              |           |
|------------------------------|-----------|
| Kassarabattdatum           | 2015/07/12 |
| Kassarabattbelopp         | -20,00    |
| Använd kassarabatt            | Normal    |
| Utnyttjad kassarabatt          | 0,00      |
| Kassarabattbelopp att utnyttja | -20,00    |

Därför uppdaterar hon fakturan i fältet **Belopp att kvitta** till **500,00**. Värdet i fältet **Kassarabattbelopp att utnyttja** beräknas som **5,05**.

| Markera                     | Använd kassarabatt | Verifikation   | Konto | Datum      | Förfallodatum  | Faktura | Belopp i transaktionsvalutan | Valuta | Belopp att kvitta |
|--------------------------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Vald och markerad | Normal            | Fakt- 10030 | 3052    | 2015/06/28 | 2015/07/12 | 10030   | 2 000,00                       | USD      | -500,00          |
| Markerad                 | Normal            | APP-10030 | 3052    | 2015/07/15 | 2015/07/15 |         | 500.00                         | USD      | 500.00           |

Information om rabatten visas längst ned på sidan **Kvitta öppna transaktioner**. Värdet i fältet **Kassarabattbelopp att utnyttja** är **5,05**, eftersom kvittningsbeloppet för fakturan ändrades till betalningsbeloppet på 500,00.

|                              |           |
|------------------------------|-----------|
| Kassarabattdatum           | 2015/07/15 |
| Kassarabattbelopp         | -20,00    |
| Använd kassarabatt            | Normal    |
| Utnyttjad kassarabatt          | 0,00      |
| Kassarabattbelopp att utnyttja | -5,05     |






