---
title: Centraliserade betalningar för leverantörsreskontra
description: Organisationer som omfattar flera juridiska personer kan skapa och hantera betalningar genom att använda en enda juridisk person som hanterar alla betalningar. Därför måste inte samma betalningar anges i flera juridiska personer. Den här artikeln ger exempel som visar hur bokföringen av centraliserade betalningar hanteras i olika scenarier.
author: abruer
manager: AnnBe
ms.date: 02/12/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14341
ms.assetid: 7bd02e32-2416-4ac6-8a60-85525267fdb7
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2a4632056d6873cfeb748251c77becc410f5cf54
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2019
ms.locfileid: "1837430"
---
# <a name="centralized-payments-for-accounts-payable"></a>Centraliserade betalningar för leverantörsreskontra

[!include [banner](../includes/banner.md)]

Organisationer som omfattar flera juridiska personer kan skapa och hantera betalningar genom att använda en enda juridisk person som hanterar alla betalningar. Därför måste inte samma betalningar anges i flera juridiska personer. Den här artikeln ger exempel som visar hur bokföringen av centraliserade betalningar hanteras i olika scenarier.

Organisationer som omfattar flera juridiska personer kan skapa och hantera betalningar genom att använda en enda juridisk person som hanterar alla betalningar. Därför måste inte samma betalningar anges i flera juridiska personer. Dessutom sparar organisationen tid eftersom betalningsprocessen rationaliseras.

I en organisation med centraliserade betalningar finns det många juridiska personer för operationer, och varje fungerande juridisk person hanterar sina egna leverantörsfakturor. Betalningar för alla verksamma juridiska personer genereras från en enda juridisk person, som kallas betalningens juridiska person. Under kvittningsprocessen genereras de förfaller till- och förfaller från-transaktioner som behövs. Du kan ange vilken juridisk person i organisationen som får de realiserade vinst- eller förlusttransaktionerna, och hur kassarabattransaktioner som hör till en korsföretagsbetalning hanteras. Den centraliserade betalningsjournalraden **kontotyp** bör anges till Leverantör. **Motkontotypen** bör anges till Bank eller Huvudbok. Bakkontot bör vara i nuvarande företaget. 

I följande exempel visas hur bokföringen hanteras i olika scenarier. Följande konfiguration används i alla tre exempel:

-   De juridiska personerna är Fabrikam, Fabrikam East och Fabrikam West. Betalningar görs från Fabrikam.
-   Fältet **Bokför kassarabatt** på sidan **Koncernintern redovisning** är inställd på **Juridisk person på fakturan**.
-   Fältet **Bokför valutakursvinst eller -förlust** på sidan **Koncernintern redovisning** är inställd på **Juridisk person för betalning**.
-   Leverantören Fourth Coffee är inställd som en leverantör i varje juridisk person. Leverantör från de olika juridiska personerna identifieras som samma leverantör eftersom de delar samma globala adressboks-ID.

| Katalog-ID | Leverantörskonto | Namn          | Juridisk person  |
|--------------|----------------|---------------|---------------|
| 1050         | 3004           | Fourth Coffee | Fabrikam      |
| 1050         | 100            | Fourth Coffee | Fabrikam öst |
| 1050         | 3004           | Fourth Coffee | Fabrikam väst |

## <a name="example-1-vendor-payment-of-invoice-from-another-legal-entity"></a>Exempel 1: Leverantörsbetalning för faktura från en annan juridisk person
Fabrikam East har en öppen faktura för leverantörskontot 100, Fourth Coffee. Fabrikam registrerar och bokför en betalning till Fabrikams leverantörskonto 3004, Fourth Coffee. Betalningen kvittas mot den öppna fakturan.

### <a name="invoice-is-posted-in-fabrikam-east-for-vendor-100"></a>Faktura bokförs i Fabrikam East för leverantör 100

| Konto                          | Debetbelopp | Kreditbelopp |
|----------------------------------|--------------|---------------|
| Utgift (Fabrikam East)          | 600,00       |               |
| Leverantörsreskontra (Fabrikam East) |              | 600,00        |

### <a name="payment-is-generated-and-posted-in-fabrikam-for-vendor-3004"></a>Betalning skapas och bokförs i Fabrikam för leverantör 3004

| Konto                     | Debetbelopp | Kreditbelopp |
|-----------------------------|--------------|---------------|
| Leverantörsreskontra (Fabrikam) | 600,00       |               |
| Kontant (Fabrikam)             |              | 600,00        |

### <a name="fabrikam-payment-is-settled-with-fabrikam-east-invoice"></a>Fabrikam-betalning kvittas mot Fabrikam East-faktura

**Fabrikam-bokföring**

| Konto                           | Debetbelopp | Kreditbelopp |
|-----------------------------------|--------------|---------------|
| Förfaller från Fabrikam East (Fabrikam) | 600,00       |               |
| Leverantörsreskontra (Fabrikam)       |              | 600,00        |

**Fabrikam East-bokföring**

| Konto                          | Debetbelopp | Kreditbelopp |
|----------------------------------|--------------|---------------|
| Leverantörsreskontra (Fabrikam East) | 600,00       |               |
| Förfaller till Fabrikam (Fabrikam East)  |              | 600,00        |

## <a name="example-2-vendor-payment-of-invoice-from-another-legal-entity-with-cash-discount"></a>Exempel 2: Leverantörsbetalning för faktura från annan juridisk person med kassarabatt
Fabrikam East har en öppen faktura för leverantör 100, Fourth Coffee. Fakturan har en kassarabatt på 20,00. Fabrikam registrerar och bokför en betalning på 580,00 till Fabrikams leverantör 3004, Fourth Coffee. Betalningen kvittas mot de öppna Fabrikam East-fakturorna. Kassarabatten bokförs till den juridiska personen för fakturan, Fabrikam East.

### <a name="invoice-is-posted-in-fabrikam-east-for-fabrikam-east-vendor-100"></a>Faktura bokförs i Fabrikam East för Fabrikam East-leverantör 100

| Konto                          | Debetbelopp | Kreditbelopp |
|----------------------------------|--------------|---------------|
| Utgift (Fabrikam East)          | 600,00       |               |
| Leverantörsreskontra (Fabrikam East) |              | 600,00        |

### <a name="payment-is-generated-and-posted-in-fabrikam-for-fabrikam-vendor-3004"></a>Betalning skapas och bokförs i Fabrikam för Fabrikam-leverantör 3004

| Konto                     | Debetbelopp | Kreditbelopp |
|-----------------------------|--------------|---------------|
| Leverantörsreskontra (Fabrikam) | 580,00       |               |
| Kontant (Fabrikam)             |              | 580,00        |

### <a name="fabrikam-payment-is-settled-with-fabrikam-east-invoice"></a>Fabrikam-betalning kvittas mot Fabrikam East-faktura

**Fabrikam-bokföring**

| Konto                           | Debetbelopp | Kreditbelopp |
|-----------------------------------|--------------|---------------|
| Förfaller från Fabrikam East (Fabrikam) | 580,00       |               |
| Leverantörsreskontra (Fabrikam)       |              | 580,00        |

**Fabrikam East-bokföring**

| Konto                          | Debetbelopp | Kreditbelopp |
|----------------------------------|--------------|---------------|
| Leverantörsreskontra (Fabrikam East) | 580,00       |               |
| Förfaller till Fabrikam (Fabrikam East)  |              | 580,00        |
| Leverantörsreskontra (Fabrikam East) | 20,00        |               |
| Kassarabatt (Fabrikam East)    |              | 20,00         |

## <a name="example-3-vendor-payment-of-invoice-from-another-legal-entity-with-realized-exchange-rate-loss"></a>Exempel 3: Leverantörsbetalning av faktura från annan juridisk person med realiserad kursförlust
Fabrikam East har en öppen faktura för leverantör 100, Fourth Coffee. Fabrikam registrerar och bokför en betalning för Fabrikams leverantör 3004, Fourth Coffee. Betalningen kvittas mot de öppna Fabrikam East-fakturorna. En transaktion för kursförlust genereras under kvittningen.

-   Valutakursen för euro (EUR) till dollar (USD) vid fakturadatumet: 1,2062
-   Växelkurs för EUR till USD vid betalningsdatumet: 1,2277

### <a name="invoice-is-posted-in-fabrikam-east-for-fabrikam-east-vendor-100"></a>Faktura bokförs i Fabrikam East för Fabrikam East-leverantör 100

| Konto                          | Debetbelopp            | Kreditbelopp           |
|----------------------------------|-------------------------|-------------------------|
| Utgift (Fabrikam East)          | 600,00 EUR / 723,72 USD |                         |
| Leverantörsreskontra (Fabrikam East) |                         | 600,00 EUR / 723,72 USD |

### <a name="payment-is-generated-and-posted-in-fabrikam-for-fabrikam-vendor-3004"></a>Betalning skapas och bokförs i Fabrikam för Fabrikam-leverantör 3004

| Konto                     | Debetbelopp            | Kreditbelopp           |
|-----------------------------|-------------------------|-------------------------|
| Leverantörsreskontra (Fabrikam) | 600,00 EUR / 736,62 USD |                         |
| Kontant (Fabrikam)             |                         | 600,00 EUR / 736,62 USD |

### <a name="fabrikam-payment-is-settled-with-fabrikam-east-invoice"></a>Fabrikam-betalning kvittas mot Fabrikam East-faktura

**Fabrikam-bokföring**

| Konto                           | Debetbelopp            | Kreditbelopp           |
|-----------------------------------|-------------------------|-------------------------|
| Förfaller från Fabrikam East (Fabrikam) | 600,00 EUR / 736,62 USD |                         |
| Leverantörsreskontra (Fabrikam)       |                         | 600,00 EUR / 736,62 USD |
| Realiserad förlust (Fabrikam)          | 0,00 EUR / 12,90 USD    |                         |
| Förfaller från Fabrikam East (Fabrikam) |                         | 0,00 EUR / 12,90 USD    |

**Fabrikam East-bokföring**

| Konto                          | Debetbelopp            | Kreditbelopp           |
|----------------------------------|-------------------------|-------------------------|
| Leverantörsreskontra (Fabrikam East) | 600,00 EUR / 736,62 USD |                         |
| Förfaller till Fabrikam (Fabrikam East)  |                         | 600,00 EUR / 736,62 USD |
| Förfaller till Fabrikam (Fabrikam East)  | 0,00 EUR / 12,90 USD    |                         |
| Leverantörsreskontra (Fabrikam East) |                         | 0,00 EUR / 12,90 USD    |

## <a name="example-4-vendor-payment-of-invoice-from-another-legal-entity-with-cash-discount-and-realized-exchange-rate-loss"></a>Exempel 4: Leverantörsbetalning av faktura från annan juridisk person med kassarabatt och realiserad kursförlust
Fabrikam East har en öppen faktura för leverantör 100, Fourth Coffee. Fakturan har en kassarabatt och en momstransaktion skapas. Fabrikam bokför en betalning för Fabrikams leverantör 3004, Fourth Coffee. Betalningen kvittas mot de öppna Fabrikam East-fakturorna. En transaktion för kursförlust genereras under kvittningen. Kassarabatten bokförs till den juridiska personen för fakturan (Fabrikam East) och kursförlusten bokförs till den juridiska personen för betalningen (Fabrikam).

-   Växelkurs för EUR till USD vid fakturadatumet: 1,2062
-   Växelkurs för EUR till USD vid betalningsdatumet: 1,2277

### <a name="invoice-is-posted-and-a-tax-transaction-is-generated-in-fabrikam-east-for-vendor-100"></a>Faktura bokförs och en momstransaktion skapas i Fabrikam East för leverantör 100

| Konto                          | Debetbelopp            | Kreditbelopp           |
|----------------------------------|-------------------------|-------------------------|
| Utgift (Fabrikam East)          | 564,07 EUR / 680,38 USD |                         |
| Moms (Fabrikam East)        | 35,93 EUR / 43,34 USD   |                         |
| Leverantörsreskontra (Fabrikam East) |                         | 600,00 EUR / 723,72 USD |

### <a name="payment-is-generated-and-posted-in-fabrikam-for-vendor-3004"></a>Betalning skapas och bokförs i Fabrikam för leverantör 3004

| Konto                     | Debetbelopp            | Kreditbelopp           |
|-----------------------------|-------------------------|-------------------------|
| Leverantörsreskontra (Fabrikam) | 588,72 EUR / 722,77 USD |                         |
| Kontant (Fabrikam)        |                         | 588,72 EUR / 722,77 USD |

### <a name="fabrikam-payment-is-settled-with-fabrikam-east-invoice"></a>Fabrikam-betalning kvittas mot Fabrikam East-faktura

**Fabrikam-bokföring**

| Konto                           | Debetbelopp            | Kreditbelopp           |
|-----------------------------------|-------------------------|-------------------------|
| Förfaller från Fabrikam East (Fabrikam) | 588,72 EUR / 722,77 USD |                         |
| Leverantörsreskontra (Fabrikam)       |                         | 588,72 EUR / 722,77 USD |
| Realiserad förlust (Fabrikam)          | 0,00 EUR / 12,66 USD    |                         |
| Förfaller från Fabrikam East (Fabrikam) |                         | 0,00 EUR / 12,66 USD    |

**Fabrikam East-bokföring**

| Konto                          | Debetbelopp            | Kreditbelopp           |
|----------------------------------|-------------------------|-------------------------|
| Leverantörsreskontra (Fabrikam East) | 588,72 EUR / 722,77 USD |                         |
| Förfaller till Fabrikam (Fabrikam East)  |                         | 588,72 EUR / 722,77 USD |
| Förfaller till Fabrikam (Fabrikam East)   | 0,00 EUR / 12,66 USD    |                         |
| Leverantörsreskontra (Fabrikam East) |                         | 0,00 EUR / 12,66 USD    |
| Leverantörsreskontra (Fabrikam East) | 11,28 EUR / 13,61 USD   |                         |
| Kassarabatt (Fabrikam East)    |                         | 11,28 EUR / 13,61 USD   |

## <a name="example-5-vendor-credit-note-with-primary-payment"></a>Exempel 5: Leverantörskreditfaktura med primär betalning
Fabrikam skapar en betalning på 75,00 för leverantör 3004, Fourth Coffee. Betalningen kvittas mot en öppen faktura för Fabrikam West-leverantör 3004 och en öppen kreditfaktura för Fabrikam East-leverantör 100. Betalningen väljs som primär betalning på sidan **Kvitta transaktioner**.

### <a name="invoice-is-posted-to-fabrikam-west-for-vendor-3004"></a>Faktura bokförs på Fabrikam West för leverantör 3004

| Konto                          | Debetbelopp | Kreditbelopp |
|----------------------------------|--------------|---------------|
| Utgift (Fabrikam West)          | 100,00       |               |
| Leverantörsreskontra (Fabrikam West) |              | 100,00        |

### <a name="credit-note-is-posted-to-fabrikam-east-for-vendor-100"></a>Kreditnota bokförs på Fabrikam East för leverantör 100

| Konto                          | Debetbelopp | Kreditbelopp |
|----------------------------------|--------------|---------------|
| Leverantörsreskontra (Fabrikam East) | 25,00        |               |
| Inköpsreturer (Fabrikam East) |              | 25,00         |

### <a name="payment-is-posted-to-fabrikam-for-vendor-3004"></a>Betalning bokförs på Fabrikam för leverantör 3004

| Konto                     | Debetbelopp | Kreditbelopp |
|-----------------------------|--------------|---------------|
| Leverantörsreskontra (Fabrikam) | 75,00        |               |
| Kontant (Fabrikam)             |              | 75,00         |

### <a name="fabrikam-payment-is-settled-with-fabrikam-west-invoice-and-fabrikam-east-credit-note"></a>Fabrikam-betalning kvittas mot Fabrikam West-faktura och Fabrikam East-kreditfaktura

**Fabrikam-bokföring**

| Konto                           | Debetbelopp | Kreditbelopp |
|-----------------------------------|--------------|---------------|
| Leverantörsreskontra (Fabrikam)       | 25,00        |               |
| Förfaller till Fabrikam East (Fabrikam)   |              | 25,00         |
| Förfaller från Fabrikam West (Fabrikam) | 100,00       |               |
| Leverantörsreskontra (Fabrikam)       |              | 100,00        |

**Fabrikam East-bokföring**

| Konto                           | Debetbelopp | Kreditbelopp |
|-----------------------------------|--------------|---------------|
| Förfaller från Fabrikam (Fabrikam East) | 25,00        |               |
| Leverantörsreskontra (Fabrikam East)  |              | 25,00         |

**Fabrikam West-bokföring**

| Konto                          | Debetbelopp | Kreditbelopp |
|----------------------------------|--------------|---------------|
| Leverantörsreskontra (Fabrikam West) | 100,00       |               |
| Förfaller till Fabrikam (Fabrikam West)  |              | 100,00        |

## <a name="example-6-vendor-credit-note-without-primary-payment"></a>Exempel 6: Leverantörskreditfaktura utan primär betalning
Fabrikam skapar en betalning på 75,00 för leverantör 3004, Fourth Coffee. Betalningen kvittas mot en öppen faktura för Fabrikam West-leverantör 3004 och en öppen kreditfaktura för Fabrikam East-leverantör 100. Betalningen väljs inte som primär betalning på sidan **Kvitta transaktioner**.

### <a name="invoice-is-posted-to-fabrikam-west-for-vendor-3004"></a>Faktura bokförs på Fabrikam West för leverantör 3004

| Konto                          | Debetbelopp | Kreditbelopp |
|----------------------------------|--------------|---------------|
| Utgift (Fabrikam West)          | 100,00       |               |
| Leverantörsreskontra (Fabrikam West) |              | 100,00        |

### <a name="credit-note-is-posted-to-fabrikam-east-for-vendor-100"></a>Kreditnota bokförs på Fabrikam East för leverantör 100

| Konto                          | Debetbelopp | Kreditbelopp |
|----------------------------------|--------------|---------------|
| Leverantörsreskontra (Fabrikam East) | 25,00        |               |
| Inköpsreturer (Fabrikam East) |              | 25,00         |

### <a name="payment-is-posted-to-fabrikam-for-vendor-3004"></a>Betalning bokförs på Fabrikam för leverantör 3004

| Konto                     | Debetbelopp | Kreditbelopp |
|-----------------------------|--------------|---------------|
| Leverantörsreskontra (Fabrikam) | 75,00        |               |
| Kontant (Fabrikam)             |              | 75,00         |

### <a name="fabrikam-payment-is-settled-with-fabrikam-west-invoice-and-fabrikam-east-credit-note"></a>Fabrikam-betalning kvittas mot Fabrikam West-faktura och Fabrikam East-kreditfaktura

**Fabrikam-bokföring**

| Konto                           | Debetbelopp | Kreditbelopp |
|-----------------------------------|--------------|---------------|
| Förfaller från Fabrikam West (Fabrikam) | 75,00        |               |
| Leverantörsreskontra (Fabrikam)       |              | 75,00         |

**Fabrikam East-bokföring**

| Konto                                | Debetbelopp | Kreditbelopp |
|----------------------------------------|--------------|---------------|
| Förfaller från Fabrikam West (Fabrikam East) | 25,00        |               |
| Leverantörsreskontra (Fabrikam East)       |              | 25,00         |

**Fabrikam West-bokföring**

| Konto                              | Debetbelopp | Kreditbelopp |
|--------------------------------------|--------------|---------------|
| Leverantörsreskontra (Fabrikam West)     | 75,00        |               |
| Förfaller till Fabrikam (Fabrikam West)      |              | 75,00         |
| Leverantörsreskontra (Fabrikam West)     | 25,00        |               |
| Förfaller till Fabrikam East (Fabrikam West) |              | 25,00         |





