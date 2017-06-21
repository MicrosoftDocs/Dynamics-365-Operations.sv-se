---
title: 125 procent degressiv avskrivning
description: "Den här avsnittet ger en översikt över 125-procentsmetoden för degressiv avskrivning."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 13871
ms.assetid: 3abc263e-59d6-4f1a-986d-1be388948bd3
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 6e9a50c9cc03a7f561a3c23987538c0285c542e8
ms.contentlocale: sv-se
ms.lasthandoff: 05/25/2017


---

# <a name="125-percent-reducing-balance-depreciation"></a>125 procent degressiv avskrivning

[!include[banner](../includes/banner.md)]


Den här avsnittet ger en översikt över 125-procentsmetoden för degressiv avskrivning.

När du ställer in en avskrivningsprofil för anläggningstillgångar och väljer **125 % degressiv avskrivning** i fältet **Metod** på sidan **Avskrivningsprofiler** skrivs tillgångarna som tilldelas den här avskrivningsprofilen av med samma procentsats under varje avskrivningsperiod. Denna procentsats beräknas baserat på tillgångens tjänstelivstid. Om till exempel en tillgång har en tjänstelivstid på fem år, beräknas procentsatsen som 25 procent (125 % ÷ 5).

Om du vill ställa in 125 % degressiv avskrivning måste du också markera alternativ i fältet **Avskrivningsår** och fältet **Periodfrekvens** på sidan **Avskrivningsprofiler**. De tillgängliga alternativen i fältet **Periodfrekvens** varierar beroende på vilket värde som valts i fältet **Avskrivningsår**.

## <a name="select-a-depreciation-year"></a>Välj ett avskrivningsår
Du kan välja **Kalender** eller **Räkenskapsår** i fältet **Avskrivningsår** på sidan **Avskrivningsprofiler**. Standardvärdet är **Kalender**. 

Valet avgör vilka alternativ som är tillgängliga i fältet **Periodfrekvens**. Det här fältet definierar bokföringsdatumen för periodisering av avskrivningen och beloppen under kalenderåret.

### <a name="calendar"></a>Kalender

Du kan välja att behålla standardvärdet i fältet **Avskrivningsår**, **Kalender**. 

Alternativet **Kalender** uppdaterar avskrivningsbasen den 1 januari varje år. Generellt är avskrivningsbasen bokfört nettovärde minus skrotvärdet. I exemplen senare i det här ämnet utgör avskrivningsbasen täljaren i det första uttrycket i beräkningskolumnen. 

Om du väljer **Kalender** som avskrivningsår finns följande alternativ i fältet **Periodfrekvens**.

-   **Årlig** bokför ett belopp den 31 december.
-   **Månatlig** bokför ett månatligt belopp i slutet av varje kalendermånad.
-   **Kvartalsvis** bokför ett kvartalsbelopp i slutet av varje kvartal (31 mars, 30 juni, 30 september och 31 december).
-   **Halvårsvis** bokför ett halvårsbelopp i slutet av varje halvår (30 juni och 31 december).
-   **Dagligen** bokför avskrivningsbeloppet för den dagliga avskrivningsmetoden genom att använda en transaktion för varje dag.

### <a name="fiscal"></a>Skatt

Om du väljer **Räkenskapsår** i fältet **Avskrivningsår**, beräknas 125 % degressiv avskrivning baserat på räkenskapsåret för räkenskapskalendern som angetts för boken, eller för den räkenskapskalender som har valts på sidan **Huvudbok**. Räkenskapskalendrar ställs in på sidan **Räkenskapskalendrar**. 

För räkenskapsåret 1 juli - 30 juni startar alltså avskrivningsberäkningen den 1 juli. Räkenskapsåret kan vara längre eller kortare än 12 månader. Avskrivningen justeras automatiskt för varje period och längden på nästa räkenskapsår bestäms av perioderna som ställs in på sidan **Räkenskapskalendrar**. 

Om du väljer **Räkenskapsår** som avskrivningsår finns följande alternativ i fältet **Periodfrekvens**:

-   **Årligen** bokför det totala avskrivningsbeloppet som beräknas för räkenskapsåret som ett belopp på räkenskapsårets sista dag.
-   **Räkenskapsperiod** bokför det totala avskrivningsbeloppet som beräknas för räkenskapsåret. Detta belopp periodiseras till de räkenskapsperioder som har definierats på **Räkenskapskalendrar**.

## <a name="example-of-125-reducing-balance-depreciation"></a>Exempel på en degressiv avskrivning på 125 %
|                                |        |
|--------------------------------|--------|
| Anskaffningskostnad               | 11 000 |
| Skrotvärde                  | 1 000  |
| Avskrivningsbas              | 10 000 |
| Antal tjänsteår             | 5      |
| Årlig avskrivningsprocent | 25 %    |

Den degressiva avskrivningsmetoden på 125 % delar 125 procent med tjänstelivstiden i år. Den procenten multipliceras med anläggningstillgångens bokförda nettovärde för att bestämma årets avskrivningsbelopp.

| Period | Beräkning av årligt avskrivningsbelopp | Bokfört värde                    | Bokfört nettovärde i slutet av året |
|--------|-----------------------------------------------|-------------------------------|---------------------------------------|
| År 1 | (11 000 – 1 000) × 25 % = 2 500                | (11 000 – 2 500) = 8 500      | (11 000 – 1 000 – 2 500) = 7 500      |
| År 2 | 7 500 × 25 % = 1 875                           | (8 500 – 1 875) = 6 625       | (7 500 – 1 875) = 5 625               |
| År 3 | 5 625 × 25 % = 1 406,25                        | (6 625 – 1 406,25) = 5 218,75 | (5 625 – 1 406,25) = 4 218,75         |

> [!NOTE] 
> Om beloppet som beräknas med den degressiva avskrivningsmetoden 125 % blir lägre än beloppet som beräknas med den linjära metoden, sker vanligtvis en konvertering till den linjära metoden för resterande tjänstelivstid.




