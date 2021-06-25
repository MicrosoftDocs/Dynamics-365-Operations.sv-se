---
title: Beräkningsmetod för moms i fältet Ursprung
description: Den här artikeln beskriver alternativen i fältet Ursprung på momskodsidan och hur moms beräknas utifrån det markerade alternativet för en momskod.
author: ShylaThompson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e57e97847c6aa7a775b0f2639dff93f1e3a9e7a2
ms.sourcegitcommit: ff09736563d3cd2bc74c7664edd1767b218401cb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "6189383"
---
# <a name="sales-tax-calculation-methods-in-the-origin-field"></a>Beräkningsmetod för moms i fältet Ursprung

[!include [banner](../includes/banner.md)]

Den här artikeln beskriver alternativen i fältet Ursprung på momskodsidan och hur moms beräknas utifrån det markerade alternativet för en momskod.

För varje momskod som du skapar på sidan Momskoder väljer du den beräkningsmetod som ska tillämpas på basbeloppet för skatten i fältet Ursprung.

## <a name="percentage-of-net-amount"></a>Procent av nettobelopp
Beräkningsmetoden för procentandel av nettobeloppet är det förvalda värdet i fältet Ursprung. Momsen beräknas som en procentandel av inköps- eller försäljningsbeloppet, exklusive annan eventuell moms.
### <a name="example"></a>Exempel

Momssatsen är 25%. Fakturaraden visar en kvantitet på 10 artiklar à 1,00 $ styck och kunden har rätt till en radrabatt på 10 %. Nettobelopp: (10 x 1,00) -10 % = 9,00 moms: 9,00 x 25 % = 2,25 totalbelopp: 9,00 + 2,25 = 11,25

## <a name="percentage-of-gross-amount"></a> Procent av bruttobelopp
Om du väljer metoden Procent av bruttobeloppet beräknas momsen som en procentandel av bruttoförsäljningsbeloppet. Bruttobeloppet är radnettobeloppet plus all skatt och tillägg för raden utom skatt med Ursprung = procentandel av bruttobeloppet.
### <a name="example"></a>Exempel

Skattemyndigheten har lagt särskilda avgifter på en artikel. Avgiftsbeloppen läggs till nettobeloppet innan momsen beräknas. Givet följande momskoder:
-   AVGIFT 1 = 10 % med beräkningsmetoden Procent av nettobelopp.
-   AVGIFT 2 = 20 % med beräkningsmetoden Procent av nettobelopp.
-   MOMS = 25 % med beräkningsmetoden Procent av bruttobelopp.

Om nettobeloppet är 10,00, är AVGIFT 1 1,00 (10,00 x 10 %) och AVGIFT 2 = 2,00 (10,00 x 20 %). Beloppen blir som följer: Bruttobelopp: Nettobelopp + AVGIFT 1 belopp + 2 AVGIFT belopp (10,00 + 1,00 + 2,00) = 13,00 MOMS = 13,00 × 25 % = 3,25 totala AVGIFTER och MOMS: 1,00 + 2,00 + 3,25 = 6,25 totalbelopp: 10,00 + 6,25 = 16,25

| **Obs!**                                                                                                                                                                                                                 |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Endast en momskod med Ursprung = procentandel av bruttobeloppet kan användas för en transaktion. Om mer än en sådan momskod bestäms av en transaktion, visas ett fel att moms inte kan beräknas. |


## <a name="percentage-of-sales-tax"></a>Procent av moms

När du väljer procentsats av moms i fältet Ursprung, beräknas momsen som en procentandel av momsen som har valts i fältet Moms på moms. Momsen som väljs i fältet Moms på moms beräknas först. Den andra momsen beräknas därefter baserat på det första momsbeloppet.
### <a name="example"></a>Exempel

Givet följande momskoder:
-   AVGIFT 1 = 10 % med metoden Procent av nettobelopp.
-   AVGIFT 2 = 20 %, med hjälp av metoden Procent av moms, med Avgift 1 i fältet Moms på moms
-   MOMS = 25 % med metoden Procent av bruttobelopp.

Nettobelopp: 10,00 AVGIFT 1: 10,00 x 10 % = 1,00 AVGIFT 2: 1,00 x 20 % = 0,20 Bruttobelopp: 10,00 + 1,00 + 0,20 = 11,20 MOMS: 11,20 x 25 % = 2,80 Totala AVGIFTER och MOMS: 1,00 + 0,20 + 2,80 = 4,00 Totalt belopp: 10,00 + 4,00 = 14,00

| **Obs!**                                                                                                                                                                                                                    |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Skatt på flera nivåer är inte möjlig. Skatt kan inte beräknas baserat på skatt som redan har beräknats på en annan skatt. Skatt på flera nivåer på momskoder kan beräknas för en transaktion. |

## <a name="amount-per-unit"></a> Belopp per enhet
När du väljer belopp per enhet i fältet Ursprung, beräknas momsen som ett fast belopp per enhet multiplicerat med den kvantitet som anges på dokumentraden. Enheten väljs i fältet Enhet. Pris per enhet anges på sidan för Momskodsvärden.
### <a name="example"></a>Exempel

Momskoden är inställt som: 1,20 Kronor per enhet = rutan på en försäljningsfakturarad 25 rutor av en artikel är såld Moms beräknas som 25 x 1,20 = 30,00

| **Obs!**                                                                                                                                                                                                 |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Om transaktionen anges i en annan enhet än de enheter som anges på momskoden, konverteras den automatiskt baserat på enhetskonverteringarna som ställs in i enhetskonverteringsidan. |

###  <a name="amount-per-unit-additional-option"></a> Belopp per enhet, extra alternativ

I fliken Beräkning kan du välja om ett belopp per enhet för beräknad skatt ska beräknas före andra momskoder och läggas till nettobeloppet med ursprunget = procent av nettobeloppet beräknas.

### <a name="examples"></a>Exempel

Anta att du beräknar 2 momskoder på en transaktion:

-   AVGIFT: Ursprung = belopp per enhet och moms, värdet är 5,00 per enhet = stk
-   MOMS: Ursprung = enligt exemplen nedan, värdet är 25 %

Vi säljer 1 del av en artikel till enhetspriset på 10,00
#### <a name="example-1"></a>Exempel 1

MOMS: Ursprung = procentandel av bruttobeloppet, alternativet Beräknat före moms påverkar inte, eftersom MOMS beräknas som en procentandel av bruttobeloppet. AVGIFT: 1 × 5,00 = 5,00 bruttobelopp: 10,00 + 5,00 = 15,00 MOMS: 15,00 x 25 % = 3,75 Total moms: 5,00 + 3,75 = 8,75 Totalt belopp: 10,00 + 8,75 = 18,75

#### <a name="example-2"></a>Exempel 2

MOMS: Ursprung = procentandelen av nettobeloppet, alternativet Beräknat före moms markeras inte för beräkningen av AVGIFT. Nettobelopp: 10,00 AVGIFT: 1 x 5,00 = 5,00 MOMS: 10,00 x 25 % = 2,50 Total moms: 5,00 + 2,50 = 7,50 Totalt belopp: 10,00 + 7,50 = 17,50

#### <a name="example-3"></a>Exempel 3

MOMS: Ursprung = procentandelen av nettobeloppet, alternativet Beräknat före moms markeras för beräkningen av AVGIFT. Nettobelopp: 10,00 AVGIFT: 1 x 5,00 = 5,00 MOMS: (10,00 + 5,00) x 25 % = 3,75 Total moms: 5,00 + 3,75 = 8,75 Totalt belopp: 10,00 + 8,75 = 18, 75

#### <a name="example-4"></a>Exempel 4

Resultatet av exempel 3 och exempel 1 är samma, eftersom det bara fanns en avgift. Anta att du har två AVGIFTER, och endast en av dem är inkluderad i nettobeloppet för momsberäkningen: AVGIFT 1: 5,00 med hjälp av metoden Belopp per enhet och alternativet Beräkna före moms är markerade AVGIFT 2: 2,50 med hjälp av metoden Belopp per enhet och alternativet Beräkna före moms är inte markerat Moms: 25 % med hjälp av metoden Procent av nettobelopp: 10,00 AVGIFT 1: 1 x 5,00 = 5,00 AVGIFT 2: 1 x 2,50 = 2,50 Nettobelopp som omfattas av moms: 10,00 + 5,00 = 15,00 MOMS: 15,00 x 2 5% = 3,75 Total moms, inklusive tullavgifter: 5,00 + 2,50 + 3,75 = 11,25 Totalt belopp: 10,00 + 11,25 = 21,25, 25 % MOMS beräknas för summan av nettobeloppet (10,00) + AVGIFT 1 (5,00) = 15,00. AVGIFT 2 läggs till skattebeloppet efter att momsen beräknats.

## <a name="calculated-percentage-of-net-amount"></a> Beräknad procent av nettobeloppet
Den beräknade procentandelen av nettobeloppet hanterar momsberäkningen annorlunda beroende på inställningen av parametern Moms ingår i beloppen för dokumentet eller journalen.
### <a name="example-1"></a>Exempel 1

Dokumentet/journalen ställs in på Moms ingår i beloppen = Ja, Transaktionens radbelopp: 10,00 Momssats 25 % Skatt: Transaktionens radbelopp * (10,00 × 25 %) = 2,50 basbelopp för skatt (ursprungsbelopp): Transaktionens radbelopp – moms (10,00 – 2,50) = 7,50

### <a name="example-2"></a>Exempel 2

Dokumentet/journalen ställs in på Moms ingår i beloppen = Nej, Transaktionens radbelopp: 10,00 Momssats: 25 % (Transaktionens radbelopp x Momssats) / (100 – Momssats) (10,00 x 25 %) / (100 % – 25 %) = 3,33 Basbelopp för moms (ursprungsbelopp): Transaktionens radbelopp = 10,00



## <a name="additional-resources"></a>Ytterligare resurser

[Momssatser baserade på fälten Bidragsunderlag och Beräkningsmetoder](marginal-base-field.md)

[Beräkningsalternativ för hela beloppet och intervall för momskoder](whole-amount-interval-options-sales-tax-codes.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]