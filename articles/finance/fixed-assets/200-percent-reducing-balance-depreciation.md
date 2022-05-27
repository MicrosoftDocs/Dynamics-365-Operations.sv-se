---
title: 200 procent degressiv avskrivning
description: Det här ämnet ger en översikt över 200-procentsmetoden för degressiv avskrivning.
author: moaamer
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: kfend
ms.custom: 13951
ms.assetid: 69b4e010-7683-4dc2-8a06-6d572f37e903
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 831a99246f0a2d5f223e3624aace1c218c3c4ff4
ms.sourcegitcommit: 04e6c1c9400e1b582180cf3e0e4767434e736c26
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/05/2022
ms.locfileid: "8710958"
---
# <a name="200-percent-reducing-balance-depreciation"></a>200 procent degressiv avskrivning

[!include [banner](../includes/banner.md)]

Det här ämnet ger en översikt över 200-procentsmetoden för degressiv avskrivning.

När du ställer in en avskrivningsprofil för anläggningstillgångar och väljer **200 % degressiv avskrivning** i fältet **Metod** på sidan **Avskrivningsprofiler** skrivs tillgångarna som tilldelas den här avskrivningsprofilen av med samma procentsats under varje avskrivningsperiod. Denna procentsats beräknas baserat på tillgångens tjänstelivstid. Om till exempel en tillgång har en tjänstelivstid på fem år, beräknas procentsatsen som 40 procent (200% ÷ 5). 

Denna metod kallas också för dubbel degressiv avskrivning.

Om du vill ställa in 200 % degressiv avskrivning måste du också markera alternativ i fältet **Avskrivningsår** och fältet **Periodfrekvens** på sidan **Avskrivningsprofiler**. De tillgängliga alternativen i fältet **Periodfrekvens** varierar beroende på vilket värde som valts i fältet **Avskrivningsår**.

## <a name="select-a-depreciation-year"></a>Välj ett avskrivningsår
Du kan välja **Kalender** eller **Räkenskapsår** i fältet **Avskrivningsår** på sidan **Avskrivningsprofiler**. Standardvärdet är **Kalender**. 

Valet avgör vilka alternativ som är tillgängliga i fältet **Periodfrekvens**. Det här fältet definierar bokföringsdatumen för periodisering av avskrivningen och beloppen under kalenderåret.

### <a name="calendar"></a>Kalender

Du kan välja att behålla standardvärdet i fältet **Avskrivningsår**, **Kalender**. 

Alternativet **Kalender** uppdaterar avskrivningsbasen den 1 januari varje år. Generellt är avskrivningen bokfört nettovärde minus kassationsvärdet. I exemplen senare i det här ämnet utgör avskrivningsbasen täljaren i det första uttrycket i beräkningskolumnen. 

Om du väljer **Kalender** som avskrivningsår finns följande alternativ i fältet **Periodfrekvens**.

-   **Årlig** bokför ett belopp den 31 december.
-   **Månatlig** bokför ett månatligt belopp i slutet av varje kalendermånad.
-   **Kvartalsvis** bokför ett kvartalsbelopp i slutet av varje kvartal (31 mars, 30 juni, 30 september och 31 december).
-   **Halvårsvis** bokför ett halvårsbelopp i slutet av varje halvår (30 juni och 31 december).
-   **Dagligen** bokför avskrivningsbeloppet för den dagliga avskrivningsmetoden genom att använda en transaktion för varje dag.

### <a name="fiscal"></a>Skatt

Om du väljer **Räkenskapsår** i fältet **Avskrivningsår**, beräknas 200 % degressiv avskrivning baserat på räkenskapsåret för räkenskapskalendern som angetts för boken, eller för den räkenskapskalender som har valts på sidan **Huvudbok**. Räkenskapskalendrar ställs in på sidan **Räkenskapskalendrar**. 

För räkenskapsåret 1 juli – 30 juni startar alltså avskrivningsberäkningen den 1 juli. Räkenskapsåret kan vara längre eller kortare än 12 månader. Avskrivningen justeras för varje period. Längden på nästa räkenskapsår bestäms av inställningen för perioder på sidan **Räkenskapskalendrar**. 

Om du väljer **Skatt** som avskrivningsår finns följande alternativ i fältet **Periodfrekvens**:

-   **Årligen** bokför det totala avskrivningsbeloppet som beräknas för räkenskapsåret som ett belopp på räkenskapsårets sista dag.
-   **Räkenskapsperiod** bokför det totala avskrivningsbeloppet som beräknas för räkenskapsåret. Detta belopp periodiseras till de räkenskapsperioder som har definierats på **Räkenskapskalendrar**.

## <a name="example-of-200-reducing-balance-depreciation"></a>Exempel på en degressiv avskrivning på 200 %

| &nbsp;                         | &nbsp; |
|--------------------------------|--------|
| Anskaffningskostnad               | 11 000 |
| Skrotvärde                  | 1 000 |
| Avskrivningsbas              | 10 000 |
| Antal tjänsteår             | 5      |
| Årlig avskrivningsprocent | 40 %    |

Den degressiva avskrivningsmetoden på 200 % delar 200 procent med tjänstelivstiden i år. Den procenten multipliceras med anläggningstillgångens bokförda nettovärde för att bestämma årets avskrivningsbelopp.

| Period | Beräkning av årligt avskrivningsbelopp | Bokfört värde             | Bokfört nettovärde i slutet av året |
|--------|-----------------------------------------------|------------------------|---------------------------------------|
| År 1 | (11 000 – 1 000) × 40 % = 4 000                | 11 000 – 4 000 = 7 000 | 11 000 – 1 000 – 4 000 = 6 000        |
| År 2 | 6 000 × 40 % = 2 400                           | 7 000 – 2 400 = 4 600  | 6 000 – 2 400 = 3 600                 |
| År 3 | 3 600 × 40 % = 1 440                           | 4 600 – 1 440 = 3 160  | 3 600 – 1 440 = 2 160                 |

> [!NOTE] 
> Om beloppet som beräknas med den degressiva avskrivningsmetoden 200 % blir lägre än beloppet som beräknas med den linjära metoden, sker vanligtvis en konvertering till den linjära metoden för resterande tjänstelivstid.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
