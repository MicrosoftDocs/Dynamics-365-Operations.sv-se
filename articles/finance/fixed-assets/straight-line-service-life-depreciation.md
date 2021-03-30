---
title: Linjär avskrivning av tjänstelivstid
description: Det här avsnittet ger en översikt över metoden för linjär tjänstelivstid för avskrivning.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: roschlom
ms.custom: 3341
ms.assetid: ae5ceaeb-aeb7-45cd-b835-23cf9c5cf95a
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5853265492edc88acbbd297bc5cb639b46fa0b41
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5210081"
---
# <a name="straight-line-service-life-depreciation"></a>Linjär avskrivning av tjänstelivstid

[!include [banner](../includes/banner.md)]

Det här avsnittet ger en översikt över metoden för linjär tjänstelivstid för avskrivning.

När du ställer in en avskrivningsprofil för anläggningstillgångar och väljer Linjär återstående tjänstelivstid i fältet Metod på sidan Avskrivningsprofiler baseras avskrivningen av anläggningstillgångar som är tilldelade till den här avskrivningsprofilen på tillgångens totala tjänstelivstid. Det är vanligtvis samma avskrivningsbelopp i varje avskrivningsperiod. 

Avskrivningsbelopp som beräknas mellan återstående linjär tjänstelivstid och linjär tjänstelivstid skiljer sig endast då en justering har bokförts för tillgången. 

Om du vill ställa in linjär avskrivning kvarstående tjänstelivstid måste du också markera alternativ i fältet Avskrivningsår och fältet Periodfrekvens på sidan Avskrivningsprofiler.

## <a name="select-a-depreciation-year"></a>Välj ett avskrivningsår
Du kan välja Kalender eller Räkenskapsår i fältet Avskrivningår på sidan Avskrivningsprofiler. Valet avgör vilka alternativ som är tillgängliga i fältet Periodfrekvens. Standardalternativet är Kalender.

### <a name="calendar"></a>Kalender

När du väljer Kalender blir kalenderåret 1 januari till 31 december, även om du har gjort andra inställningar för räkenskapskalender. 

Med alternativet Kalender uppdaterar du avskrivningsbasen som vanligtvis är bokfört nettovärde minus skrotvärde, den 1 januari varje år. I exemplen senare i det här ämnet utgör avskrivningsbasen täljaren i det första uttrycket i beräkningskolumnen. 

Om du väljer Kalender är följande alternativ tillgängliga i fältet Periodfrekvens, som definierar bokföringsdatumen för periodisering av avskrivningen och beloppen under kalenderåret:
-   Årlig bokför ett belopp den 31 december.
-   Månadsvis bokför ett månatligt belopp i slutet av varje månad.
-   Kvartalvis bokför ett kvartalsbelopp i slutet av varje kvartal (31 mars, 30 juni, 30 september och 31 december).
-   Halvårsvis bokför ett halvårsbelopp i slutet av varje halvår (30 juni och 31 december).
-   Dagligen bokför avskrivningsbeloppet för den dagliga avskrivningsmetoden genom att använda en transaktion för varje dag.

Om du till exempel väljer Årligen, bokförs årets avskrivning alltså bara en gång, den 31 december varje år. Om du väljer Månadsvis, bokförs månadens avskrivning som 1/12 av det årliga avskrivningsbeloppet.

### <a name="fiscal"></a>Skatt

Om du väljer Räkenskapsår i fältet Avskrivningsår används linjär avskrivning av tjänstelivstid. Den beräknas utifrån räkenskapsåret, som definieras av den räkenskapskalender som anges för boken, eller utifrån räkenskapskalendern som valts på sidan Redovisning. Räkenskapskalendrar ställs in på sidan Räkenskapskalendrar.

Exempelvis för räkenskapsåret 1 juli – 30 juni startar alltså avskrivningsberäkningen den 1 juli. Räkenskapsåret kan vara längre eller kortare än 12 månader. Avskrivningen justeras automatiskt för varje räkenskapsperiod. Längden på nästa räkenskapsår baseras på de räkenskapsperioder som du ställer in när du skapar ett nytt räkenskapsår i formuläret Räkenskapskalendrar. 

Om du väljer Räkenskapsår har du följande alternativ i fältet Räkenskapsår.
-   Årligen bokför det totala avskrivningsbeloppet som beräknas för räkenskapsåret som ett belopp på räkenskapsårets sista dag.
-   Räkenskapsperiod beräknar det totala avskrivningsbeloppet för räkenskapsåret, som periodiseras till de räkenskapsperioder som har definierats i formuläret Räkenskapsperiod för räkenskapskalendern.

## <a name="example-straight-line-depreciation-of-an-unchanged-fixed-asset"></a>Exempel: Linjär avskrivning av en oförändrad anläggningstillgång
Anta att anläggningstillgången har följande egenskaper.

|                     |        |
|---------------------|--------|
| Anskaffningskostnad    | 11 000 |
| Skrotvärde       | 1 000  |
| Avskrivningsbas   | 10 000 |
| Antal tjänsteår  | 5      |
| Årlig avskrivning | 2 000  |

Samma avskrivningsbelopp varje år. (Anskaffningskostnad – skrotvärde)/tjänstelivstidsår

| Period | Beräkning av årligt avskrivningsbelopp | Bokfört nettovärde i slutet av året |
|--------|-------------------------------------------|---------------------------------------|
| År 1 | (11 000 – 1 000) / 5 = 2 000              | 9 000                                 |
| År 2 | (11 000 – 1 000) / 5 = 2 000              | 7 000                                 |
| År 3 | (11 000 – 1 000) / 5 = 2 000              | 5 000                                 |
| År 4 | (11 000 – 1 000) / 5 = 2 000              | 3 000                                 |
| År 5 | (11 000 – 1 000) / 5 = 2 000              | 1 000                                 |

## <a name="example-straight-line-depreciation-of-a-modified-fixed-asset"></a>Exempel: Linjär avskrivning av en förändrad anläggningstillgång

Antag att du lägger till en anskaffningsjustering på 4 000 under år 2 till samma anläggningstillgång. 

Anskaffningsjusteringens tjänstelivstid är samma som anläggningstillgångens och påbörjas vid anskaffning. Vid slutet av år 5 återstår ett bokfört nettovärde som motsvarar anskaffningsjusteringens bokförda nettovärde. Följande tabell visar hur avskrivning per period beräknas.

| Period | Beräkning av årligt avskrivningsbelopp | Bokfört nettovärde i slutet av året |
|--------|-------------------------------------------|---------------------------------------|
| År 1 | 10 000 / 5 = 2 000                        | 11 000 – 2 000 = 9 000                |
| År 2 | 4 000 (anskaffningsjustering)            | 9 000 + 4 000 =13 000                 |
| År 2 | 14 000 / 5 = 2 800                        | 13 000 – 2 800 = 10 200               |
| År 3 | 14 000 / 5 = 2 800                        | 10 200 – 2 800 = 7 400                |
| År 4 | 14 000 / 5 = 2 800                        | 7 400 – 2 800 = 4 600                 |
| År 5 | 14 000 / 5 = 2 800                        | 4 600 – 2 800 = 1 800                 |
| År 6 | Resterande 800\*                           | 1 800 – 800 = 1 000                   |

\*Eftersom det resterande beloppet är mindre än avskrivningsbeloppet hämtas endast det resterande beloppet minus skrotvärdet.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]