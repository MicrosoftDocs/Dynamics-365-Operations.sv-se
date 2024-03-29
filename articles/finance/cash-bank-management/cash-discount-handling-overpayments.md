---
title: Kassarabatter för överbetalningar
description: Det här avsnittet tillhandahåller scenarier om hur en betalning hanteras när kunden får en kassarabatt, men även betalar för mycket.
author: angelad116
ms.date: 10/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustOpenTrans, CustParameters, LedgerJournalTransCustPaym, LedgerJournalTransVendPaym, VendOpenTrans, VendParameters
audience: Application User
ms.reviewer: kfend
ms.custom: 14171
ms.assetid: a94d0fd0-57ba-4054-93c8-519d01d50e19
ms.search.region: Global
ms.author: angelading
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d7c4e98481bc3607d3dce68a6b6cb0478524442f
ms.sourcegitcommit: 81bb8e51951395be3f18f45212e47e6c41656f6a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/23/2022
ms.locfileid: "9804166"
---
# <a name="cash-discounts-for-overpayments"></a>Kassarabatter för överbetalningar

[!include [banner](../includes/banner.md)]

Det här avsnittet tillhandahåller scenarier om hur en betalning hanteras när kunden får en kassarabatt, men även betalar för mycket. 

En faktura betraktas som överbetald när betalningsbeloppet överstiger fakturabeloppet minus kassarabatten. Om du vill ange hur en användbar kassarabattsskillnad ska hanteras när en faktura är överbetalad, använd fälten **Administration av kassarabatt** och **Maximal över – och underbetalning** på sidan **Parametrar för kundreskontra**. I följande exempel har kunden överbetalt fakturan med 0,50.

| Fakturatotal | Tillgänglig kassarabatt | Belopp som ska betalas inklusive kassarabatt | Belopp som kunden faktiskt betalar |
|---------------|-------------------------|-----------------------------------------------------|-----------------------------------|
| 105,00        | 10,50                   | 94,50                                               | 95,00                             |

## <a name="cash-discount-administration--specific"></a>Administration av kassarabatt = Specifikt
När **Specifikt** har valts i fältet **Administration av kassarabatt** på sidan **Konton för automatiska transaktioner**, hämtas den fullständiga kassarabatten. Överbetalningbeloppet bokförs antingen till ett redovisningskonto för kassarabattskillnad eller återstår som ett saldo på kundens konto. Beteendet beror på om överbetalningsbeloppet är mellan 0,00 och det belopp som angetts i fältet **Maximal över- och underbetalning**, eller om överbetalningsbeloppet är större än beloppet **Maximal över- och underbetalning** .

### <a name="scenario-1"></a>Scenario 1

I detta scenario ligger överbetalningsbeloppet mellan 0,00 och den maximala över- eller underbetalningen. En faktura anges för 105,00 och en kassarabatt är tillgänglig om fakturan betalas inom sju dagar.

| Fakturatotal | Tillgänglig kassarabatt | Belopp som ska betalas inklusive kassarabatt |
|---------------|-------------------------|-----------------------------------------------------|
| 105,00        | 10,50                   | 94,50                                               |

Kunden skickar in en betalning på för 95,00 inom kassarabattperioden. Betalningen kvittas mot fakturan för 105,00. Efter att fakturan och betalningen har kvittats skapas följande transaktioner i för kunden i Kundreskontra.

| Transaktion   | Belopp | Saldo |
|---------------|--------|---------|
| Faktura       | 105,00 | 0,00    |
| Betalning       | -95.00 | 0,00    |
| Kassarabatt | -10.50 | 0,00    |

Följande redovisningsposter genereras för betalningen och kvittningen.

**Betalning**

| Konto             | Debetbelopp | Kreditbelopp |
|---------------------|--------------|---------------|
| Kontanter                | 95,00        |               |
| Kundreskontra |              | 95,00         |

**Kvittning**

| Konto                                                                                                          | Debetbelopp | Kreditbelopp |
|------------------------------------------------------------------------------------------------------------------|--------------|---------------|
| Kassarabatt (**fältet Huvudkonto för kundrabatter** på sidan **Kassarabatter**)                 | 10,50        |               |
| Kundreskontra                                                                                              |              | 10,50         |
| Kundkassarabatt (**fältet Kundkassarabatt** på sidan **Konton för automatiska transaktioner**) |              | 0.50          |
| Kundreskontra                                                                                              | 0.50         |               |

### <a name="scenario-2"></a>Scenario 2

I det här scenariot överstiger överbetalningsbeloppet det maximala över- eller underbetalningsbeloppet. En faktura anges för 105,00 och en kassarabatt är tillgänglig om fakturan betalas inom sju dagar.

| Fakturatotal | Tillgänglig kassarabatt | Belopp som ska betalas inklusive kassarabatt |
|---------------|-------------------------|-----------------------------------------------------|
| 105,00        | 10,50                   | 94,50                                               |

Kunden skickar in en betalning på för 95,00 inom kassarabattperioden. Betalningen kvittas mot fakturan för 105,00. Efter att fakturan och betalningen har kvittats skapas följande transaktioner i för kunden i Kundreskontra.

| Transaktion   | Belopp | Saldo |
|---------------|--------|---------|
| Faktura       | 105,00 | 0,00    |
| Betalning       | -95.00 | -0.50   |
| Kassarabatt | -10.50 | 0,00    |

Överbetalningsbeloppet på 0,50 kommer att återstå som ett öppet saldot på betalningen och kan kvittas mot en annan faktura. Följande redovisningsposter genereras för betalningen och kvittningen. 

**Betalning**

| Konto             | Debetbelopp | Kreditbelopp |
|---------------------|--------------|---------------|
| Kontanter                | 95,00        |               |
| Kundreskontra |              | 95,00         |

**Kvittning**

| Konto                                                                                          | Debetbelopp | Kreditbelopp |
|--------------------------------------------------------------------------------------------------|--------------|---------------|
| Kassarabatt (**fältet Huvudkonto för kundrabatter** på sidan **Kassarabatter**) | 10,50        |               |
| Kundreskontra                                                                              |              | 10,50         |

## <a name="cash-discount-administration--unspecific"></a>Administration av kassarabatt = Ospecifikt
När **Ospecifikt** har valts i fältet **Administration av kassarabatt** på sidan **Konton för automatiska transaktioner**, reduceras kassarabattsbeloppet med överbetalningsbeloppet. Det här beteendet används alltid oavsett om överbetalningsbeloppet är större än eller mindre än det belopp som angetts i fältet **Maximal över- och underbetalning** .

### <a name="scenario-3"></a>Scenario 3

I det här scenariot anges en faktura för 105,00 och en kassarabatt är tillgänglig om fakturan betalas inom sju dagar.

| Fakturatotal | Tillgänglig kassarabatt | Belopp som ska betalas inklusive kassarabatt |
|---------------|-------------------------|-----------------------------------------------------|
| 105,00        | 10,50                   | 94,50                                               |

Kunden skickar in en betalning på för 95,00 inom kassarabattdatumet. Betalningen kvittas mot fakturan för 105,00. Efter att fakturan och betalningen har kvittats skapas följande transaktioner i för kunden i Kundreskontra.

| Transaktion   | Belopp | Saldo |
|---------------|--------|---------|
| Faktura       | 105,00 | 0,00    |
| Betalning       | -95.00 | -0.00   |
| Kassarabatt | -10.00 | 0,00    |

Kassarabattbeloppet reduceras från 10,50 till 10,00. Betalningen och fakturan anses kvittade. 

**Betalning**

| Konto             | Debetbelopp | Kreditbelopp |
|---------------------|--------------|---------------|
| Kontanter                | 95,00        |               |
| Kundreskontra |              | 95,00         |

**Kvittning**

| Konto                                                                                          | Debetbelopp | Kreditbelopp |
|--------------------------------------------------------------------------------------------------|--------------|---------------|
| Kassarabatt (**fältet Huvudkonto för kundrabatter** på sidan **Kassarabatter**) | 10,50        |               |
| Kundreskontra                                                                              |              | 10,50         |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
