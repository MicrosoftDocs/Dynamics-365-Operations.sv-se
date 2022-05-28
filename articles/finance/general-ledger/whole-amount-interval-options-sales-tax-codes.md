---
title: Beräkningsalternativ för hela beloppet och intervall för momskoder
description: Den här artikeln beskriver alternativen för fältet Beräkningsmetod för momskoder och hur moms beräknas för intervall och hela belopp.
author: kailiang
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxData, TaxTable
audience: Application User
ms.reviewer: kfend
ms.custom: 5624
ms.assetid: 96166db4-b7ca-470b-aeb7-0a66fe0554c4
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6f06c92f2151f54a7d9b684b9687b786d1e4cd7a
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2022
ms.locfileid: "8727466"
---
# <a name="whole-amount-and-interval-calculation-options-for-sales-tax-codes"></a>Beräkningsalternativ för hela beloppet och intervall för momskoder

[!include [banner](../includes/banner.md)]

Den här artikeln beskriver alternativen för fältet **Beräkningsmetod** för momskoder och hur moms beräknas för intervall och hela belopp.

Du kan ställa in en momskod som ska beräknas baserat på ett helt belopp eller ett intervallbelopp. På sidan **Momskoder** använder du fältet **Beräkningsmetod** på snabbfliken **Beräkning** för att välja hur du beräknar en momskod.
- Hela belopp – Momssatsen tillämpas för hela det momspliktiga beloppet.
- Intervall – Det momspliktiga beloppet delas upp i delar, och varje del ligger inom ett intervall som har en specifik momssats. Den del av beloppet som ligger inom ett angivet intervall beläggs med moms i enlighet med momssatsen för intervallet. Momsen är summan av de momsbelopp som beräknas för varje beloppsintervall.
  > [!NOTE]                                                                                                                              
  > Alternativet Intervall är bara tillgängliga när du väljer i fältet Rad i fältet Beräkningsmetod i området Moms på sidan Redovisningparameter. 

Intervall ställs in på sidan Momskodvärden, genom att ange gränsbelopp för minimum och maximum per momssats. För att moms ska beräknas på alla momspliktiga belopp, oavsett vilken beräkningsmetod som har valts, måste intervallen vara utformade i enlighet med följande regler:
-   Det första intervallet måste ha en minimigräns på noll.
-   Det sista intervallet måste ha en maximal gräns på noll, vilket anger oändlighet.
-   Den maximala gränsen i ett intervall måste vara minimumgränsen i nästa intervall.

Om ett belopp är den maximala gränsen för föregående intervall och den minimala gränsen i nästa intervall används momssatsen från det första intervallet för beloppet. Om ett belopp ligger utanför de intervall som har definierats av övre och nedre gränser används momssatsen noll.

## <a name="example-whole-amount-method-of-calculation"></a>Exempel: Beräkningsmetoden för hela beloppet
På sidan för momskodvärden ställs momssatser in med följande intervall:

| Minimigräns     | Maximigräns     | Momssats     |
|-------------------|-------------------|--------------|
| 0,00              | 50,00             | 30 %          |
| 50,00             | 100,00            | 20 %          |
| 100,00            | 0,00              | 10 %          |

Momsen beräknas till hela momspliktiga beloppet.

| Momspliktigt belopp (pris) | Beräkning    | Moms |
|------------------------|----------------|-----------|
| 35,00                  | 35,00 \* 0,30  | 10,50     |
| 50,00                  | 50,00 \* 0,30  | 15,00     |
| 85,00                  | 85,00 \* 0,20  | 17,00     |
| 305,00                 | 305,00 \* 0,10 | 30,50     |

## <a name="example-interval-method-of-calculation"></a> Exempel: Beräkningsmetoden Intervall
PÅ sidan Värden ställs momssatserna in med följande intervall:

| Minimigräns     | Maximigräns     | Momssats     |
|-------------------|-------------------|--------------|
| 0,00              | 50,00             | 30 %          |
| 50,00             | 100,00            | 20 %          |
| 100,00            | 0,00              | 10 %          |

Momsen är summan av de momsbelopp som beräknas för varje beloppsintervall.

| Momspliktigt belopp (pris) | Beräkning                                                               | Moms |
|------------------------|---------------------------------------------------------------------------|-----------|
| 35,00                  | 35,00 \* 0,30                                                             | 10,50     |
| 50,00                  | 50,00 \* 0,30                                                             | 15,00     |
| 85,00                  | (50,00 \* 0,30 = 15,00) + (35,00 \* 0,20 = 7,00)                          | 22,00     |
| 305,00                 | (50,00 \* 0,30 = 15,00) + (50,00 \* 0,20 = 10,00) + (205 \* 0,10 = 20,50) | 45.50     |



Mer information finns i [Momssatser baserat på fälten Marginalbas och Beräkningsmetod](marginal-base-field.md)







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
