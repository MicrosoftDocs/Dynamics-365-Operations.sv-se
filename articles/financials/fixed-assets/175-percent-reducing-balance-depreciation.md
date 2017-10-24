---
title: 175 procent degressiv avskrivning
description: "Det här avsnittet ger en översikt över 175-procentsmetoden för degressiv avskrivning."
author: saraschi2
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 13911
ms.assetid: cc5d001f-bcfe-4602-9ec1-9e265e9fd188
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 318e111f784157666c2853bcd6d5b3af2c9ffdc5
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="175-percent-reducing-balance-depreciation"></a>175 procent degressiv avskrivning

[!include[banner](../includes/banner.md)]


Det här avsnittet ger en översikt över 175-procentsmetoden för degressiv avskrivning.

När du ställer in en avskrivningsprofil för anläggningstillgångar och väljer **175 % degressiv avskrivning** i fältet **Metod** på sidan **Avskrivningsprofiler** skrivs tillgångarna som tilldelas den här avskrivningsprofilen av med samma procentsats under varje avskrivningsperiod. 

Om du vill ställa in 175% degressiv avskrivning måste du också markera alternativ i fältet **Avskrivningsår** och fältet **Periodfrekvens** på sidan **Avskrivningsprofiler**. De tillgängliga alternativen i fältet **Periodfrekvens** varierar beroende på vilket värde som valts i fältet **Avskrivningsår**.

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

Om du väljer **Räkenskapsår** i fältet **Avskrivningsår**, beräknas 175 % degressiv avskrivning baserat på räkenskapsåret för räkenskapskalendern som angetts för boken, eller för den räkenskapskalender som har valts på sidan **Huvudbok**. Räkenskapskalendrar ställs in på sidan **Räkenskapskalendrar**. Mer information finns i [Räkenskapskalendrar, räkenskapsår och perioder.](..\budgeting\fiscal-calendars-fiscal-years-periods.md)

För räkenskapsåret 1 juli - 30 juni startar alltså avskrivningsberäkningen den 1 juli. Räkenskapsåret kan vara längre eller kortare än 12 månader. Avskrivningen justeras automatiskt för varje period och längden på nästa räkenskapsår bestäms av perioderna som ställs in på sidan **Räkenskapskalendrar**. 

Om du väljer **Räkenskapsår** som avskrivningsår finns följande alternativ i fältet **Periodfrekvens**:

-   **Årlig** bokför det totala avskrivningsbeloppet som beräknas för räkenskapsåret som ett belopp på räkenskapsårets sista dag.
-   **Räkenskapsperiod** beräknar det totala avskrivningsbeloppet för räkenskapsåret. Detta belopp periodiseras till de räkenskapsperioder som har definierats på **Räkenskapskalendrar**.

## <a name="example-of-175-reducing-balance-depreciation"></a>Exempel på en degressiv avskrivning på 175 %
|                                |        |
|--------------------------------|--------|
| Anskaffningskostnad               | 11 000 |
| Skrotvärde                  | 1 000  |
| Avskrivningsbas              | 10 000 |
| Antal tjänsteår             | 5      |
| Årlig avskrivningsprocent | 35 %    |

Den degressiva avskrivningsmetoden på 175 % delar 175 procent med tjänstelivstiden i år. Den procenten multipliceras med anläggningstillgångens bokförda nettovärde för att bestämma årets avskrivningsbelopp.

| Period | Beräkning av årligt avskrivningsbelopp | Bokfört värde                  | Bokfört nettovärde i slutet av året |
|--------|-----------------------------------------------|-----------------------------|---------------------------------------|
| År 1 | (11 000 - 1 000) × 35 % = 3 500                | 11 000 - 3 500 = 7 500      | 11 000 - 1 000 – 3 500 = 6 500        |
| År 2 | 6 500 × 35 % = 2 275                           | 7 500 - 2 275 = 5 225       | 6 500 - 2 275 = 4 225                 |
| År 3 | 4 225 × 35 % = 1 478,75                        | 5 225 - 1 478,75 = 3 746,25 | 4,225 - 1 478,75 = 2 746,25           |

> [!NOTE] 
> Om beloppet som beräknas med den degressiva avskrivningsmetoden 175 % blir lägre än beloppet som beräknas med den linjära metoden, sker vanligtvis en konvertering till den linjära metoden för resterande tjänstelivstid.




