---
title: "Alternativ för hela belopp och intervallberäkning för momskoder"
description: "Den här artikeln beskriver alternativen för fältet Beräkningsmetod för momskoder och hur moms beräknas för intervall och hela belopp."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: TaxData, TaxTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 5624
ms.assetid: 96166db4-b7ca-470b-aeb7-0a66fe0554c4
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: ecd32549b6067ed4c1211996e846e210f77f5013
ms.openlocfilehash: d417019ab7e47a180d45d45abbde4e358a904721
ms.lasthandoff: 03/31/2017


---

# <a name="whole-amount-and-interval-calculation-options-for-sales-tax-codes"></a>Alternativ för hela belopp och intervallberäkning för momskoder

Den här artikeln beskriver alternativen för fältet Beräkningsmetod för momskoder och hur moms beräknas för intervall och hela belopp.

Du kan ställa in en momskod som ska beräknas baserat på ett helt belopp eller ett intervallbelopp. På sidan Momskoder använder du fältet Beräkningsmetod på snabbfliken Beräkning för att välja hur du beräknar en momskod.
-   Hela belopp – Momssatsen tillämpas för hela det momspliktiga beloppet.
-   Intervall – Det momspliktiga beloppet delas upp i delar, och varje del ligger inom ett intervall som har en specifik momssats. Den del av beloppet som ligger inom ett angivet intervall beläggs med moms i enlighet med momssatsen för intervallet. Momsen är summan av de momsbelopp som beräknas för varje beloppsintervall.
> [!NOTE]                                                                                                                              
> Alternativet Intervall är bara tillgängliga när du väljer i fältet Rad i fältet Beräkningsmetod i området Moms på sidan Redovisningparameter. 

Intervall ställs in på sidan Momskodvärden, genom att ange gränsbelopp för minimum och maximum per momssats. För att moms ska beräknas på alla momspliktiga belopp, oavsett vilken beräkningsmetod som har valts, måste intervallen vara utformade i enlighet med följande regler:
-   Det första intervallet måste ha en minimigräns på noll.
-   Det sista intervallet måste ha en maximal gräns på noll, vilket anger oändlighet.
-   Den maximala gränsen i ett intervall måste vara minimumgränsen i nästa intervall.

Om ett belopp är den maximala gränsen för föregående intervall och den minimala gränsen i nästa intervall används momssatsen från det första intervallet för beloppet. Om ett belopp ligger utanför de intervall som har definierats av övre och nedre gränser används momssatsen noll.

## <a name="example-whole-amount-method-of-calculation"></a>Exempel: Beräkningsmetoden för hela beloppet
På sidan för momskodvärden ställs momssatser in med följande intervall:
|                   |                   |              |
|-------------------|-------------------|--------------|
| **Minimigräns** | **Maximigräns** | **Momssats** |
| 0,00              | 50,00             | 30 %          |
| 50,00             | 100,00            | 20 %          |
| 100,00            | 0,00              | 10 %          |

Momsen beräknas till hela momspliktiga beloppet.

| Momspliktigt belopp (pris) | Beräkning    | Moms |
|------------------------|----------------|-----------|
| 35,00                  | 35.00 \* 0.30  | 10,50     |
| 50,00                  | 50.00 \* 0.30  | 15,00     |
| 85,00                  | 85.00 \* 0.20  | 17,00     |
| 305,00                 | 305.00 \* 0.10 | 30,50     |

## <a name="example-interval-method-of-calculation"></a> Exempel: Beräkningsmetoden Intervall
PÅ sidan Värden ställs momssatserna in med följande intervall:

|                   |                   |              |
|-------------------|-------------------|--------------|
| **Minimigräns** | **Maximigräns** | **Momssats** |
| 0,00              | 50,00             | 30 %          |
| 50,00             | 100,00            | 20 %          |
| 100,00            | 0,00              | 10 %          |

Momsen är summan av de momsbelopp som beräknas för varje beloppsintervall.

| Momspliktigt belopp (pris) | Beräkning                                                               | Moms |
|------------------------|---------------------------------------------------------------------------|-----------|
| 35,00                  | 35.00 \* 0.30                                                             | 10,50     |
| 50,00                  | 50.00 \* 0.30                                                             | 15,00     |
| 85,00                  | (50.00 \* 0.30 = 15.00) + (35.00 \* 0.20 = 7.00)                          | 22,00     |
| 305,00                 | (50.00 \* 0.30 = 15.00) + (50.00 \* 0.20 = 10.00) + (205 \* 0.10 = 20.50) | 45,50     |

 

Mer information finns i [fastställa skattesatser försäljning utifrån bidragsunderlaget och beräkningen metoden fält](marginal-base-field.md).



