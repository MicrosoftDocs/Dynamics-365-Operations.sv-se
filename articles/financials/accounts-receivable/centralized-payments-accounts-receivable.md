---
title: "Centraliserade betalningar för kundreskontra"
description: "Organisationer som omfattar flera juridiska personer kan skapa och hantera betalningar genom att använda en enda juridisk person som hanterar alla betalningar. Därför måste samma transaktion inte finns med i flera juridiska personer. Den här artikeln ger exempel som visar hur bokföringen av centraliserade betalningar hanteras i olika scenarier."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerJournalTransCustPaym
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 7208acc35e656d12b3c4f88a090f36ecfdd4fdfb
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="centralized-payments-for-accounts-receivable"></a>Centraliserade betalningar för kundreskontra

[!include [banner](../includes/banner.md)]

Organisationer som omfattar flera juridiska personer kan skapa och hantera betalningar genom att använda en enda juridisk person som hanterar alla betalningar. Därför måste samma transaktion inte finns med i flera juridiska personer. Den här artikeln ger exempel som visar hur bokföringen av centraliserade betalningar hanteras i olika scenarier.

Organisationer som omfattar flera juridiska personer kan skapa och hantera betalningar genom att använda en enda juridisk person som hanterar alla betalningar. Därför måste samma transaktion inte finns med i flera juridiska personer. Dessutom sparar organisationen tid eftersom de processer för betalningsförslag, kvittningar och redigering av öppna och stängda transaktioner för centraliserade betalningar effektiviseras. 

I en organisation med centraliserade betalningar finns många juridiska personer för verksamheter, och varje verksam juridisk person hanterar sina egna leverantörsfakturor. Betalningar för alla verksamma juridiska personer tas emot av en enda juridisk person, som kallas betalningens juridiska person. Under kvittningsprocessen genereras de förfaller till- och förfaller från-transaktioner som behövs. Du kan ange vilken juridisk person i organisationen som får de realiserade vinst- eller förlusttransaktionerna, och hur kassarabattransaktioner som hör till en centraliserad betalning hanteras. 

I följande exempel visas hur bokföringen hanteras i olika scenarier. Följande konfiguration används i alla tre exempel:

-   De juridiska personerna är Fabrikam, Fabrikam East och Fabrikam West. Kundbetalningar anges i Fabrikam.
-   Fältet **Bokför kassarabatt** på sidan **Koncernintern redovisning** är inställd på **Juridisk person på fakturan**.
-   Fältet **Bokför valutakursvinst eller -förlust** på sidan **Koncernintern redovisning** är inställd på **Juridisk person för betalning**.
-   Kunden Northwind Traders är inställd som en kund i varje juridisk person. Kunderna från de olika juridiska personerna identifieras som samma kund eftersom de delar samma globala adressboks-ID.

| Adressboks-ID | Kundkonto | Namn              | Juridisk person  |
|-----------------|------------------|-------------------|---------------|
| 4050            | 4000             | Northwind Traders | Fabrikam      |
| 4050            | 4000             | Northwind Traders | Fabrikam öst |
| 4050            | 10000            | Northwind Traders | Fabrikam väst |

## <a name="example-1-customer-payment-of-invoice-from-another-legal-entity"></a>Exempel 1: Kundbetalning för faktura från en annan juridisk person
Fabrikam tar emot en betalning på 600,00 för Fabrikam-kundkonto 4000, Northwind Traders. Betalningen kvittas mot en öppen faktura för kundkonto 4000 i Fabrikam East.

### <a name="invoice-is-posted-in-fabrikam-east-for-customer-4000"></a>Faktura bokförs i Fabrikam East för kund 4000

| Konto                             | Debetbelopp | Kreditbelopp |
|-------------------------------------|--------------|---------------|
| Kundreskontra (Fabrikam East) | 600,00       |               |
| Försäljning (Fabrikam East)               |              | 600,00        |

### <a name="payment-is-received-and-posted-in-fabrikam-for-customer-4000"></a>Betalning tas emot och bokförs i Fabrikam för kund 4000

| Konto                        | Debetbelopp | Kreditbelopp |
|--------------------------------|--------------|---------------|
| Kontant (Fabrikam)                | 600,00       |               |
| Kundreskontra (Fabrikam) |              | 600,00        |

### <a name="fabrikam-payment-is-settled-with-fabrikam-east-invoice"></a>Fabrikam-betalning kvittas mot Fabrikam East-faktura

**Fabrikam-bokföring**

| Konto                         | Debetbelopp | Kreditbelopp |
|---------------------------------|--------------|---------------|
| Kundreskontra (Fabrikam)  | 600,00       |               |
| Förfaller till Fabrikam East (Fabrikam) |              | 600,00        |

**Fabrikam East-bokföring**

| Konto                             | Debetbelopp | Kreditbelopp |
|-------------------------------------|--------------|---------------|
| Förfaller från Fabrikam (Fabrikam East)   | 600,00       |               |
| Kundreskontra (Fabrikam East) |              | 600,00        |

## <a name="example-2-customer-payment-of-invoice-from-another-legal-entity-with-cash-discount"></a>Exempel 2: Kundbetalning för faktura från en annan juridisk person med kassarabatt
Fabrikam tar emot en betalning på 580,00 för Fabrikam-kundkonto 4000, Northwind Traders. Fabrikam East har en öppen faktura för leverantör 4000. Fakturan har en kassarabatt på 20,00. Betalningen kvittas mot de öppna Fabrikam East-fakturorna. Kassarabatten bokförs till den juridiska personen för fakturan, Fabrikam East.

### <a name="invoice-is-posted-in-fabrikam-east-for-fabrikam-east-customer-4000"></a>Faktura bokförs i Fabrikam East för Fabrikam East-kund 4000

| Konto                             | Debetbelopp | Kreditbelopp |
|-------------------------------------|--------------|---------------|
| Kundreskontra (Fabrikam East) | 600,00       |               |
| Försäljning (Fabrikam East)               |              | 600,00        |

### <a name="payment-is-received-and-posted-in-fabrikam-for-fabrikam-customer-4000"></a>Betalning tas emot och bokförs i Fabrikam för Fabrikam-kund 4000

| Konto                        | Debetbelopp | Kreditbelopp |
|--------------------------------|--------------|---------------|
| Kontant (Fabrikam)                | 600,00       |               |
| Kundreskontra (Fabrikam) |              | 600,00        |

### <a name="fabrikam-payment-is-settled-with-fabrikam-east-invoice"></a>Fabrikam-betalning kvittas mot Fabrikam East-faktura

**Fabrikam-bokföring**

| Konto                         | Debetbelopp | Kreditbelopp |
|---------------------------------|--------------|---------------|
| Kundreskontra (Fabrikam)  | 580,00       |               |
| Förfaller till Fabrikam East (Fabrikam) |              | 580,00        |

**Fabrikam East-bokföring**

| Konto                             | Debetbelopp | Kreditbelopp |
|-------------------------------------|--------------|---------------|
| Förfaller från Fabrikam (Fabrikam East)   | 580,00       |               |
| Kundreskontra (Fabrikam East) |              | 580,00        |
| Kassarabatt (Fabrikam East)       | 20,00        |               |
| Kundreskontra (Fabrikam East) |              | 20,00         |

## <a name="example-3-customer-payment-of-invoice-from-another-legal-entity-with-realized-exchange-rate-gain"></a>Exempel 3: Kundbetalning av faktura från en annan juridisk person med realiserad kursvinst
Fabrikam tar emot en betalning på 600,00 euro (EUR) för Fabrikam-kundkonto 4000, Northwind Traders. Betalningen kvittas mot en öppen faktura för kundkonto 4000 i Fabrikam East. En transaktion för kursvinst genereras under kvittningen.

-   Valutakursen för EUR till USD vid fakturadatumet: 1,2062
-   Växelkurs för EUR till USD vid betalningsdatumet: 1,2277

### <a name="invoice-is-posted-in-fabrikam-east-for-fabrikam-east-customer-4000"></a>Faktura bokförs i Fabrikam East för Fabrikam East-kund 4000

| Konto                             | Debetbelopp            | Kreditbelopp           |
|-------------------------------------|-------------------------|-------------------------|
| Kundreskontra (Fabrikam East) | 600,00 EUR / 723,72 USD |                         |
| Försäljning (Fabrikam East)               |                         | 600,00 EUR / 723,72 USD |

### <a name="payment-is-received-and-posted-in-fabrikam-for-fabrikam-customer-4000"></a>Betalning tas emot och bokförs i Fabrikam för Fabrikam-kund 4000

| Konto                        | Debetbelopp            | Kreditbelopp           |
|--------------------------------|-------------------------|-------------------------|
| Kontant (Fabrikam)                | 600,00 EUR / 736,62 USD |                         |
| Kundreskontra (Fabrikam) |                         | 600,00 EUR / 736,62 USD |

### <a name="fabrikam-payment-is-settled-with-fabrikam-east-invoice"></a>Fabrikam-betalning kvittas mot Fabrikam East-faktura

**Fabrikam-bokföring**

| Konto                         | Debetbelopp            | Kreditbelopp           |
|---------------------------------|-------------------------|-------------------------|
| Kundreskontra (Fabrikam)  | 600,00 EUR / 736,62 USD |                         |
| Förfaller till Fabrikam East (Fabrikam) |                         | 600,00 EUR / 736,62 USD |
| Förfaller till Fabrikam East (Fabrikam) | 0,00 EUR / 12,90 USD    |                         |
| Realiserad vinst (Fabrikam)        |                         | 0,00 EUR / 12,90 USD    |

**Fabrikam East-bokföring**

| Konto                             | Debetbelopp            | Kreditbelopp           |
|-------------------------------------|-------------------------|-------------------------|
| Förfaller från Fabrikam (Fabrikam East)   | 600,00 EUR / 736,62 USD |                         |
| Kundreskontra (Fabrikam East) |                         | 600,00 EUR / 736,62 USD |
| Kundreskontra (Fabrikam East) | 0,00 EUR / 12,90 USD    |                         |
| Förfaller från Fabrikam (Fabrikam East)   |                         | 0,00 EUR / 12,90 USD    |

## <a name="example-4-customer-payment-of-invoice-from-another-legal-entity-with-cash-discount-and-realized-exchange-rate-gain"></a>Exempel 4: Kundbetalning av faktura från en annan juridisk person med kassarabatt och realiserad kursvinst
Fabrikam bokför en betalning för Fabrikam-kund 4000, Northwind Traders, för en öppen faktura i Fabrikam East. Fakturan har en kassarabatt och en momstransaktion skapas. Betalningen kvittas mot den öppna Fabrikam East-fakturan. En transaktion för kursvinst genereras under kvittningen. Kassarabatten bokförs till den juridiska personen för fakturan (Fabrikam East) och kursvinsten bokförs till den juridiska personen för betalningen (Fabrikam).

-   Växelkurs för EUR till USD vid fakturadatumet: 1,2062
-   Växelkurs för EUR till USD vid betalningsdatumet: 1,2277

### <a name="free-text-invoice-is-posted-and-a-tax-transaction-is-generated-in-fabrikam-east-for-customer-4000"></a>Fritextfaktura bokförs och en momstransaktion skapas i Fabrikam East för kund 4000

| Konto                             | Debetbelopp            | Kreditbelopp           |
|-------------------------------------|-------------------------|-------------------------|
| Kundreskontra (Fabrikam East) | 638,22 EUR / 769,82 USD |                         |
| Försäljning (Fabrikam East)               |                         | 600,00 EUR / 723,72 USD |
| Moms (Fabrikam East)           |                         | 38,22 EUR / 46,10 USD   |

### <a name="payment-is-received-and-posted-in-fabrikam-for-customer-4000"></a>Betalning tas emot och bokförs i Fabrikam för kund 4000

| Konto                        | Debetbelopp            | Kreditbelopp           |
|--------------------------------|-------------------------|-------------------------|
| Kontant (Fabrikam)                | 626,22 EUR / 768,81 USD |                         |
| Kundreskontra (Fabrikam) |                         | 626,22 EUR / 768,81 USD |

### <a name="fabrikam-payment-is-settled-with-fabrikam-east-invoice"></a>Fabrikam-betalning kvittas mot Fabrikam East-faktura

**Fabrikam-bokföring**

| Konto                         | Debetbelopp            | Kreditbelopp           |
|---------------------------------|-------------------------|-------------------------|
| Kundreskontra (Fabrikam)  | 626,22 EUR / 768,81 USD |                         |
| Förfaller till Fabrikam East (Fabrikam) |                         | 626,22 EUR / 768,81 USD |
| Förfaller till Fabrikam East (Fabrikam) | 0,00 EUR / 13,46 USD    |                         |
| Realiserad vinst (Fabrikam)        |                         | 0,00 EUR / 13,46 USD    |

**Fabrikam East-bokföring**

| Konto                             | Debetbelopp            | Kreditbelopp           |
|-------------------------------------|-------------------------|-------------------------|
| Förfaller från Fabrikam (Fabrikam East)   | 626,22 EUR / 768,81 USD |                         |
| Kundreskontra (Fabrikam East) |                         | 626,22 EUR / 768,81 USD |
| Kundreskontra (Fabrikam East)  | 0,00 EUR / 13,46 USD    |                         |
| Förfaller från Fabrikam (Fabrikam East)   |                         | 0,00 EUR / 13,46 USD    |
| Kassarabatt (Fabrikam East)       | 12,00 EUR / 14,47 USD   |                         |
| Kundreskontra (Fabrikam East) |                         | 12,00 EUR / 14,47 USD   |

## <a name="example-5-customer-credit-note-with-primary-payment"></a>Exempel 5: Kundkreditfaktura med primär betalning
Fabrikam tar emot en betalning på 75,00 från kund 4000, Northwind Traders. Betalningen kvittas mot en öppen faktura för Fabrikam West-kund 10000 och en öppen kreditfaktura för Fabrikam East-kund 4000. Betalningen väljs som primär betalning på sidan **Kvitta transaktioner**.

### <a name="invoice-is-posted-to-fabrikam-west-for-customer-10000"></a>Faktura bokförs på Fabrikam West för kund 10000

| Konto                             | Debetbelopp | Kreditbelopp |
|-------------------------------------|--------------|---------------|
| Kundreskontra (Fabrikam West) | 100,00       |               |
| Försäljning (Fabrikam West)               |              | 100,00        |

### <a name="credit-note-is-posted-to-fabrikam-east-for-customer-4000"></a>Kreditfaktura bokförs på Fabrikam East för kund 4000

| Konto                             | Debetbelopp | Kreditbelopp |
|-------------------------------------|--------------|---------------|
| Försäljningsreturer (Fabrikam East)       | 25,00        |               |
| Kundreskontra (Fabrikam East) |              | 25,00         |

### <a name="payment-is-posted-to-fabrikam-for-customer-4000"></a>Betalning bokförs på Fabrikam för kund 4000

| Konto                        | Debetbelopp | Kreditbelopp |
|--------------------------------|--------------|---------------|
| Kontant (Fabrikam)                | 75,00        |               |
| Kundreskontra (Fabrikam) |              | 75,00         |

### <a name="fabrikam-payment-is-settled-with-fabrikam-west-invoice-and-fabrikam-east-credit-note"></a>Fabrikam-betalning kvittas mot Fabrikam West-faktura och Fabrikam East-kreditfaktura

**Fabrikam-bokföring**

| Konto                           | Debetbelopp | Kreditbelopp |
|-----------------------------------|--------------|---------------|
| Förfaller från Fabrikam East (Fabrikam) | 25,00        |               |
| Kundreskontra (Fabrikam)    |              | 25,00         |
| Kundreskontra (Fabrikam)    | 100,00       |               |
| Förfaller till Fabrikam West (Fabrikam)   |              | 100,00        |

**Fabrikam East-bokföring**

| Konto                             | Debetbelopp | Kreditbelopp |
|-------------------------------------|--------------|---------------|
| Kundreskontra (Fabrikam East) | 25,00        |               |
| Förfaller till Fabrikam (Fabrikam East)     |              | 25,00         |

**Fabrikam West-bokföring**

| Konto                             | Debetbelopp | Kreditbelopp |
|-------------------------------------|--------------|---------------|
| Förfaller från Fabrikam (Fabrikam West)   | 100,00       |               |
| Kundreskontra (Fabrikam West) |              | 100,00        |

## <a name="example-6-customer-credit-note-without-primary-payment"></a>Exempel 6: Kundkreditfaktura utan primär betalning
Fabrikam tar emot en betalning på 75,00 från kund 4000, Northwind Traders. Betalningen kvittas mot en öppen faktura för Fabrikam West-kund 10000 och en öppen kreditfaktura för Fabrikam East-kund 4000. Betalningen väljs inte som primär betalning på sidan **Kvitta transaktioner**.

### <a name="invoice-is-posted-to-fabrikam-west-for-customer-10000"></a>Faktura bokförs på Fabrikam West för kund 10000

| Konto                             | Debetbelopp | Kreditbelopp |
|-------------------------------------|--------------|---------------|
| Kundreskontra (Fabrikam West) | 100,00       |               |
| Försäljning (Fabrikam West)               |              | 100,00        |

### <a name="credit-note-is-posted-to-fabrikam-east-for-customer-4000"></a>Kreditfaktura bokförs på Fabrikam East för kund 4000

| Konto                             | Debetbelopp | Kreditbelopp |
|-------------------------------------|--------------|---------------|
| Försäljningsreturer (Fabrikam East)       | 25,00        |               |
| Kundreskontra (Fabrikam East) |              | 25,00         |

### <a name="payment-is-posted-to-fabrikam-for-customer-4000"></a>Betalning bokförs på Fabrikam för kund 4000

| Konto                        | Debetbelopp | Kreditbelopp |
|--------------------------------|--------------|---------------|
| Kontant (Fabrikam)                | 75,00        |               |
| Kundreskontra (Fabrikam) |              | 75,00         |

### <a name="fabrikam-payment-is-settled-with-fabrikam-west-invoice-and-fabrikam-east-credit-note"></a>Fabrikam-betalning kvittas mot Fabrikam West-faktura och Fabrikam East-kreditfaktura

**Fabrikam-bokföring**

| Konto                         | Debetbelopp | Kreditbelopp |
|---------------------------------|--------------|---------------|
| Kundreskontra (Fabrikam)  | 75,00        |               |
| Förfaller till Fabrikam West (Fabrikam) |              | 75,00         |

**Fabrikam East-bokföring**

| Konto                              | Debetbelopp | Kreditbelopp |
|--------------------------------------|--------------|---------------|
| Kundreskontra (Fabrikam East)  | 25,00        |               |
| Förfaller till Fabrikam West (Fabrikam East) |              | 25,00         |

**Fabrikam West-bokföring**

| Konto                                | Debetbelopp | Kreditbelopp |
|----------------------------------------|--------------|---------------|
| Förfaller från Fabrikam (Fabrikam West)      | 75,00        |               |
| Kundreskontra (Fabrikam West)    |              | 75,00         |
| Förfaller från Fabrikam East (Fabrikam West) | 25,00        |               |
| Kundreskontra (Fabrikam West)    |              | 25,00         |






