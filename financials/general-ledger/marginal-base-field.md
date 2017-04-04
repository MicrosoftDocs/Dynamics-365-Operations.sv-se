---
title: "Momssatser utifrån Bidragsunderlag och beräkningsmetod"
description: "Det här avsnittet innehåller en beskrivning av hur värdena i fälten Bidragsunderlag och Beräkningsmetod fastställer momssats(er) i försäljnings- och inköpstransaktioner."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: TaxTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 7171
ms.assetid: 381fc309-b32a-4927-b5b8-fa1c31b0bd72
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 114dee90b0fe525f0b3efabbf651d2804a22dd7d
ms.openlocfilehash: ad731401fe553cdc50665cc87aaac64dc48813f2
ms.lasthandoff: 03/31/2017


---

# <a name="sales-tax-rates-based-on-the-marginal-base-and-calculation-methods"></a>Momssatser utifrån Bidragsunderlag och beräkningsmetod

Det här avsnittet innehåller en beskrivning av hur värdena i fälten Bidragsunderlag och Beräkningsmetod fastställer momssats(er) i försäljnings- och inköpstransaktioner.

Bidragsunderlag på snabbfliken Beräkning på sidan Momskoder avgör vilket belopp som används för att plocka rätt momssatser från momssatserna på sidan Momskodvärden. Beloppstypen i fältet Bidragsunderlag i kombination med metoden i fältet Beräkningsmetod bestämmer logiken för att hitta rätt momssats för en transaktion. 

Olika kombinationer av värden i de här fälten kan ge mycket olika momsberäkningar, vilket demonstreras i följande exempel. I exemplen används samma momsintervallvärden – värden som har ställts in för varje momskod på sidan Momskodvärden. Klicka för att öppna den här sidan momskod &gt;värden på sidan koder för moms.

> [!Important]                                                                                                                  
> Om Bidragsunderlag för en eller flera av dina momskoder baseras på radbelopp eller enheter måste värdet i fältet Beräkningsmetod på sidan Allmänna huvudboksparametrar ha inställningen Rad. |

## <a name="net-amount-per-line"></a>Nettobelopp per rad
Välj det här alternativet för att bestämma momssatser baserat på nettobeloppet för fakturaraderna, exklusive andra skatter.

### <a name="example"></a>Exempel

Momssatserna ställs in med följande intervall.

| Beloppsintervall    | Skattesats |
|--------------------|----------|
| 0 – 50             | 30 %      |
| 50 – 100           | 20 %      |
| 100 - 0 (&gt; 100) | 10 %      |

> [!NOTE]                                                                                                             
> Den övre gränsen på noll (0) i det sista intervallet innebär att alla belopp över 100 inkluderas i intervallet.

Bidragsunderlaget: **Nettobelopp per rad** 

Beräkningsmetoden: **intervall** 

Du köper 8 lampor som kostar 25,00 styck. 

Nettobeloppet för fakturaraden är 200,00. 

Momsen beräknas på följande sätt: 

Total moms = 50 × 30 % + 50 × 20 % + 100 × 10 % = 15 + 10 + 10 = 35,00 

Totalt fakturabelopp = 200,00 + 35,00 = 235,00 

**Variation** 

Om fakturan har två rader med fyra artiklar på varje rad visas nettobeloppet på varje rad är 100,00 och momsen beräknas på följande sätt: 

Moms för rad 1 = 50 × 30 % + 50 x 20 % = 15 + 10 = 25,00 

Moms för rad 2 = 50 × 30 % + 50 x 20 % = 15 + 10 = 25,00 

Total moms = 25,00 + 25,00 = 50,00. 

Totalt fakturabelopp = 200,00 + 50,00 = 250,00

## <a name="net-amount-per-unit"></a> Nettobelopp per enhet
Välj det här alternativet för att bestämma momssatser baserat på värdet för varje enhet, exklusive andra skatter. När en enhet som baseras på Bidragsunderlag väljs måste även en enhet anges för momskoden.

### <a name="example"></a>Exempel

Momssatserna ställs in med följande intervall.

| Belopp             | Skattesats |
|--------------------|----------|
| 0 – 50             | 30 %      |
| 50 – 100           | 20 %      |
| 100 - 0 (&gt; 100) | 10 %      |

Bidragsunderlaget: **Nettobelopp per enhet** 

Beräkningsmetoden: **hela beloppet** 

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

Bidragsunderlaget: **nettobelopp av fakturasaldo** 

Beräkningsmetoden: **intervallet** en försäljningsfaktura har 2 linjer med 4 lampor på alla rader för varje 25,00. Nettobeloppet för fakturasaldo är 4 × 25,00 + 4 × 25,00 = 200,00. Momsen beräknas på följande sätt: Total moms = 50 × 0,30 + 50 × 0,20 + 100 × 0,10 = 15 + 10 + 10 = 35,00 Totalt fakturabelopp = 200,00 + 35,00 = 235,00

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
| 100 - 0 (&gt; 100) | 10 %      |

Bidragsunderlag: **Bruttobelopp per rad** Beräkningsmetod: **Intervall** Det finns också en annan momskod som beräknas för en särskild avgift på 5,00 för varje lampa. Avgiften läggs till nettobeloppet innan momsen beräknas. Du köper 8 lampor som kostar 25,00 styck. Nettobeloppet för fakturaraden är 200,00. Bruttobeloppet för fakturaraden är 8 × 25,00 + 8 × 5,00 = 240,00. Momsen beräknas på följande sätt: Total moms = 50 × 0,30 + 50 × 0,20 + 140 × 0,10 = 15 + 20 + 14 = 39,00 Total avgift = 5,00 × 8 = 40,00 Totalt fakturabelopp = 200,00 + 39,00 + 40,00 = 279,00

**Variation** 

Om fakturan skapas med 2 rader med 4 artiklar på varje rad är nettobeloppet per fakturarad 100,00. Bruttobeloppet (inklusive avgiften på 4 × 5,00) per fakturarad blir då 120,00 och momsen skapas på följande sätt: Moms för fakturarad 1 = 50 × 0,30 + 50 × 0,20 + 20 × 0,10 = 15 + 10 + 2 = 27,00 Moms för fakturarad 2 = 50 × 0,30 + 50 × 0,20 + 20 × 0,10 = 15 + 10 + 2 = 27,00 Total moms = 27,00 + 27,00 = 54,00 Total avgift = 5,00 × 8 = 40,00 Totalt fakturabelopp = 200,00 + 54,00 + 40,00 = 294,00

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
| 100 - 0 (&gt; 100) | 10 %      |

Bidragsunderlag: **Bruttobelopp per enhet** Det finns en särskild avgift på 5,00 för varje lampa. Avgiften läggs till nettobeloppet innan momsen beräknas. Du köper 8 lampor som kostar 25,00 styck. Bruttobeloppet per enhet är 30,00. Momsen beräknas på följande sätt: Moms per enhet = 30 × 30% = 9,00 Total moms = 9,00 × 8 = 72,00 Total avgift = 5,00 × 8 = 40,00 Totalt fakturabelopp = 200,00 + 72,00 + 40,00 = 312,00

## <a name="invoice-total-incl-other-sales-tax-amounts"></a> Fakturatotal inkl. andra momsbelopp

Välj det här alternativet för att bestämma momssatser baserat på fakturans totala värde, inklusive andra skatter.
> [!NOTE]
> I momsgruppen, kan du bara ha en momskod med det här alternativet i fältet Bidragsunderlag

### <a name="example"></a>Exempel

Momssatserna ställs in med följande intervall.

| Belopp             | Skattesats |
|--------------------|----------|
| 0 – 50             | 30 %      |
| 50 – 100           | 20 %      |
| 100 - 0 (&gt; 100) | 10 %      |

Bidragsunderlaget: **fakturan Totalt inklusive andra momsbelopp** beräkningsmetoden: **intervall**   
Det finns en särskild avgift för alla lampor 5,00. Avgiften läggs till nettobeloppet innan momsen beräknas. Du köper 8 lampor som kostar 25,00 styck. Nettobeloppet för fakturan är 200,00. Bruttobeloppet för fakturan är 200,00 + (8 × 5,00) = 240,00. Momsen beräknas på följande sätt: Total moms = 50 × 0,30 + 50 × 0,20 + 140 × 0,10 = 15 + 10 + 14 = 39,00 Total avgift = 5,00 × 8 = 40,00 Totalt fakturabelopp = 200,00 + 39,00 + 40,00 = 279,00

Mer information finns i [hela beloppet och intervallet beräkningsalternativ för momskoder](whole-amount-interval-options-sales-tax-codes.md) och [metoder för beräkning av moms i fältet ursprung](sales-tax-calculation-methods-origin-field.md).


