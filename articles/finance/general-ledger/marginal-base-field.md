---
title: Momssatser baserade på fälten Bidragsunderlag och Beräkningsmetoder
description: Det här ämnet innehåller en beskrivning av hur värdena i fälten Bidragsunderlag och Beräkningsmetod fastställer momssats(er) i försäljnings- och inköpstransaktioner.
author: kailiang
ms.date: 10/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: kfend
ms.custom: 7171
ms.assetid: 381fc309-b32a-4927-b5b8-fa1c31b0bd72
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 00cdc470397cedfd951e4c3a05a32f048775a4b9
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8903143"
---
# <a name="sales-tax-rates-based-on-the-marginal-base-and-calculation-methods"></a>Momssatser baserade på fälten Bidragsunderlag och Beräkningsmetoder

[!include [banner](../includes/banner.md)]

Det här ämnet innehåller en beskrivning av hur värdena i fälten Bidragsunderlag och Beräkningsmetod fastställer momssats(er) i försäljnings- och inköpstransaktioner.

Bidragsunderlag på snabbfliken Beräkning på sidan Momskoder avgör vilket belopp som används för att plocka rätt momssatser från momssatserna på sidan Momskodvärden. Beloppstypen i fältet Bidragsunderlag i kombination med metoden i fältet Beräkningsmetod bestämmer logiken för att hitta rätt momssats för en transaktion. 

Olika kombinationer av värden i de här fälten kan ge mycket olika momsberäkningar, vilket demonstreras i följande exempel. I exemplen används samma momsintervallvärden – värden som har ställts in för varje momskod på sidan Momskodvärden. Klicka på Momskod &gt; Värden på sidan Momskoder för att öppna denna sida.

> [!Important]                                                                                                                  
> Om Bidragsunderlag för en eller flera av dina momskoder baseras på radbelopp eller enheter måste värdet i fältet Beräkningsmetod på sidan Allmänna huvudboksparametrar ha inställningen Rad. |

## <a name="net-amount-per-line"></a> Nettobelopp per rad
Välj det här alternativet för att bestämma momssatser baserat på nettobeloppet för fakturaraderna, exklusive andra skatter.

### <a name="example"></a>Exempel

Momssatserna ställs in med följande intervall.

| Beloppsintervall    | Skattesats |
|--------------------|----------|
| 0 – 50             | 30 %      |
| 50 – 100           | 20 %      |
| 100 – 0 (&gt; 100) | 10 %      |

> [!NOTE]                                                                                                             
> Den övre gränsen på noll (0) i det sista intervallet innebär att alla belopp över 100 inkluderas i intervallet.

Bidragsunderlaget: **Nettobelopp per rad** 

Beräkningsmetod: **Intervall** 

Du köper 8 lampor som kostar 25,00 styck. 

Nettobeloppet för fakturaraden är 200,00. 

Momsen beräknas på följande sätt: 

Total moms = 50 × 30 % + 50 × 20 % + 100 × 10 % = 15 + 10 + 10 = 35,00. 

Totalt fakturabelopp = 200,00 + 35,00 = 235,00. 

**Variant** 

Om fakturan har två rader med fyra artiklar på varje rad är nettobeloppet på respektive rad 100,00, och momsen beräknas på följande sätt: 

Moms för rad 1 = 50 × 30 % + 50 × 20 % = 15 + 10 = 25,00. 

Moms för rad 2 = 50 × 30 % + 50 × 20 % = 15 + 10 = 25,00. 

Total moms = 25,00 +25,00 = 50,00 

Totalt fakturabelopp = 200,00 + 50,00 = 250,00.

## <a name="net-amount-per-unit"></a> Nettobelopp per enhet
Välj det här alternativet för att bestämma momssatser baserat på värdet för varje enhet, exklusive andra skatter. När en enhet som baseras på Bidragsunderlag väljs måste även en enhet anges för momskoden.

### <a name="example"></a>Exempel

Momssatserna ställs in med följande intervall.

| Belopp             | Skattesats |
|--------------------|----------|
| 0 – 50             | 30 %      |
| 50 – 100           | 20 %      |
| 100 – 0 (&gt; 100) | 10 %      |

Bidragsunderlag: **Nettobelopp per enhet** 

Beräkningsmetod: **Hela beloppet** 

Du köper 8 lampor som kostar 25,00 styck. 

Nettobeloppet för fakturaraden är 200,00. 

Momsen beräknas på följande sätt: Moms per enhet = 25,00 × 30 % = 7,50 Total moms = 7,50 × 8 enheter = 60,00 Totalt fakturabelopp = 200,00 + 60,00 = 260,00

## <a name="net-amount-of-invoice-balance"></a> Nettobelopp av fakturasaldo

Välj det här alternativet för att bestämma momssatser baserat på fakturans totala värde, exklusive andra skatter.

### <a name="example"></a>Exempel

Momssatserna ställs in med följande intervall.

| Belopp            | Skattesats |
|-------------------|----------|
| 0 – 50            | 30 %      |
| 50 – 100          | 20 %      |
| 100 -0 (&gt; 100) | 10 %      |

Bidragsunderlag **Nettobelopp av fakturasaldo** 

Beräkningsmetod: **Intervall** En försäljningsfaktura har 2 rader med 4 lampor på respektive rad för 25,00 per styck. Nettobeloppet för fakturasaldo är 4 × 25,00 + 4 × 25,00 = 200,00. Momsen beräknas på följande sätt: Total moms = 50 × 0,30 + 50 × 0,20 + 100 × 0,10 = 15 + 10 + 10 = 35,00 Totalt fakturabelopp = 200,00 + 35,00 = 235,00

## <a name="gross-amount-per-line"></a> Bruttobelopp per rad

Välj det här alternativet för att bestämma momssatser baserat på radens värde, inklusive alla andra skatter för raden.

> [!NOTE]
> I en momsgrupp kan det bara finnas en momskod med det här valet i fältet Bidragsunderlag.

### <a name="example"></a>Exempel

Momssatserna ställs in med följande intervall.

| Belopp             | Skattesats |
|--------------------|----------|
| 0 – 50             | 30 %      |
| 50 – 100           | 20 %      |
| 100 – 0 (&gt; 100) | 10 %      |

Bidragsunderlag: **Bruttobelopp per rad** Beräkningsmetod: **Intervall** Det finns också en annan momskod som beräknas för en särskild avgift på 5,00 för varje lampa. Avgiften läggs till nettobeloppet innan momsen beräknas. Du köper 8 lampor som kostar 25,00 styck. Nettobeloppet för fakturaraden är 200,00. Bruttobeloppet för fakturaraden är 8 × 25,00 + 8 × 5,00 = 240,00. Momsen beräknas på följande sätt: Total moms = 50 × 0,30 + 50 × 0,20 + 140 × 0,10 = 15 + 20 + 14 = 39,00 Total avgift = 5,00 × 8 = 40,00 Totalt fakturabelopp = 200,00 + 39,00 + 40,00 = 279,00

**Variant** 

Om fakturan skapas med två fakturarader med fyra artiklar på respektive rad, är nettobeloppet per fakturarad 100,00. Bruttobeloppet (inklusive avgiften på 4 × 5,00) per fakturarad blir då 120,00 och momsen skapas på följande sätt: Moms för fakturarad 1 = 50 × 0,30 + 50 × 0,20 + 20 × 0,10 = 15 + 10 + 2 = 27,00 Moms för fakturarad 2 = 50 × 0,30 + 50 × 0,20 + 20 × 0,10 = 15 + 10 + 2 = 27,00 Total moms = 27,00 + 27,00 = 54,00 Total avgift = 5,00 × 8 = 40,00 Totalt fakturabelopp = 200,00 + 54,00 + 40,00 = 294,00

## <a name="gross-amount-per-unit"></a> Bruttobelopp per enhet

Välj det här alternativet för att bestämma momssatser baserat på värdet för enheten inklusive andra skatter.

> [!NOTE]
> I en momsgrupp kan det bara finnas en momskod med det här valet i fältet Bidragsunderlag.

### <a name="example"></a>Exempel

Momssatserna ställs in med följande intervall.

| Belopp             | Skattesats |
|--------------------|----------|
| 0 – 50             | 30 %      |
| 50 – 100           | 20 %      |
| 100 – 0 (&gt; 100) | 10 %      |

Bidragsunderlag: **Bruttobelopp per enhet** Det finns en särskild avgift på 5,00 för varje lampa. Avgiften läggs till nettobeloppet innan momsen beräknas. Du köper 8 lampor som kostar 25,00 styck. Bruttobeloppet per enhet är 30,00. Momsen beräknas på följande sätt: Moms per enhet = 30 × 30% = 9,00 Total moms = 9,00 × 8 = 72,00 Total avgift = 5,00 × 8 = 40,00 Totalt fakturabelopp = 200,00 + 72,00 + 40,00 = 312,00

## <a name="invoice-total-incl-other-sales-tax-amounts"></a> Fakturatotal inkl. andra momsbelopp

Välj det här alternativet för att bestämma momssatser baserat på fakturans totala värde, inklusive andra skatter.
> [!NOTE]
> I en momsgrupp kan det bara finnas en momskod med det här valet i fältet Bidragsunderlag.

### <a name="example"></a>Exempel

Momssatserna ställs in med följande intervall.

| Belopp             | Skattesats |
|--------------------|----------|
| 0 – 50             | 30 %      |
| 50 – 100           | 20 %      |
| 100 – 0 (&gt; 100) | 10 %      |

Bidragsunderlag: **Fakturasumma inklusive andra momsbelopp** Beräkningsmetod: **Intervall**   
Det finns en särskild avgift på 5, 00 för varje lampa. Avgiften läggs till nettobeloppet innan momsen beräknas. Du köper 8 lampor som kostar 25,00 styck. Nettobeloppet för fakturan är 200,00. Bruttobeloppet för fakturan är 200,00 + (8 × 5,00) = 240,00. Momsen beräknas på följande sätt: Total moms = 50 × 0,30 + 50 × 0,20 + 140 × 0,10 = 15 + 10 + 14 = 39,00 Total avgift = 5,00 × 8 = 40,00 Totalt fakturabelopp = 200,00 + 39,00 + 40,00 = 279,00

Mer information finns i [Alternativ för hela belopp och intervallberäkning för momskoder](whole-amount-interval-options-sales-tax-codes.md) samt i [Beräkning av momskoder i fältet Ursprung](sales-tax-calculation-methods-origin-field.md).





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
