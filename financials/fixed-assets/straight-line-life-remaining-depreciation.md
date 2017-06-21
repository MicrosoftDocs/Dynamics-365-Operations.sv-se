---
title: "Linjär avskrivning kvarstående livstid"
description: "Det här avsnittet ger en översikt över metoden för linjär återstående livstid för avskrivning."
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
ms.custom: 13851
ms.assetid: 0fa2f71a-596c-414c-a6e6-8f7405a0bf81
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 765825ba43cad44b076ea6628d2787011e97fc57
ms.contentlocale: sv-se
ms.lasthandoff: 05/25/2017


---

# <a name="straight-line-life-remaining-depreciation"></a>Linjär avskrivning kvarstående livstid

[!include[banner](../includes/banner.md)]


Det här avsnittet ger en översikt över metoden för linjär återstående livstid för avskrivning.

När du ställer in en avskrivningsprofil för anläggningstillgångar och väljer **Linjär återstående livstid** i fältet **Metod** i formuläret **Avskrivningsprofiler** baseras avskrivningen av anläggningstillgångar som är tilldelade till den här avskrivningsprofilen på tillgångens återstående tjänstelivstid. Avskrivningsbeloppet är vanligtvis samma i varje avskrivningsperiod. Om du vill ställa in linjär avskrivning kvarstående livstid måste du också markera alternativ i fältet **Avskrivningsår** och fältet **Periodfrekvens** på sidan **Avskrivningsprofiler**. De tillgängliga alternativen i fältet **Periodfrekvens** varierar beroende på vilket värde som valts i fältet **Avskrivningsår**.

## <a name="select-a-depreciation-year"></a>Välj ett avskrivningsår
Du kan välja **Kalender** eller **Räkenskapsår** i fältet **Avskrivningsår** på sidan **Avskrivningsprofiler**. Standardvärdet är **Kalender**. Valet avgör vilka alternativ som är tillgängliga i fältet **Periodfrekvens**. Det här fältet definierar bokföringsdatumen för periodisering av avskrivningen och beloppen under kalenderåret.

### <a name="calendar"></a>Kalender

Om du väljer **Kalender** i fältet ***Avskrivningsår*** kommer ett år från 1 januari till 31 december att antas, även om du har definierat räkenskapskalendern annorlunda. Alternativet **Kalender** uppdaterar avskrivningsbasen den 1 januari varje år. Generellt är avskrivningsbasen bokfört nettovärde minus skrotvärdet. I exemplen senare i det här ämnet utgör avskrivningsbasen täljaren i det första uttrycket i beräkningskolumnen. Om du väljer **Kalender** som avskrivningsår finns följande alternativ i fältet **Periodfrekvens**.

-   **Årlig** bokför ett belopp den 31 december.
-   **Månatlig** bokför ett månatligt belopp i slutet av varje kalendermånad.
-   **Kvartalsvis** bokför ett kvartalsbelopp i slutet av varje kvartal (31 mars, 30 juni, 30 september och 31 december).
-   **Halvårsvis** bokför ett halvårsbelopp i slutet av varje halvår (30 juni och 31 december).
-   **Dagligen** bokför avskrivningsbeloppet för den dagliga avskrivningsmetoden genom att använda en transaktion för varje dag.

Om du till exempel **Årligen** bokförs årets avskrivning alltså bara en gång, den 31 december varje år. Om du väljer **Månadsvis** bokförs månadens avskrivning som 1/12 av det årliga avskrivningsbeloppet.

### <a name="fiscal"></a>Skatt

Om du väljer **Räkenskapsår** i fältet **Avskrivningsår** används linjär avskrivning kvarstående livstid. Avskrivningen beräknas utifrån vad som är kvar av räkenskapsåret. För räkenskapsåret 1 juli 2015 - 30 juni 2016 startar alltså avskrivningsberäkningen alltså den 1 juli. Räkenskapsåret kan vara längre eller kortare än 12 månader. Avskrivningen justeras för varje räkenskapsperiod. Längden på nästa räkenskapsår bestäms av de räkenskapsperioder som är inställda på sidan **Räkenskapskalendrar**. Om du väljer **Räkenskapsår** som avskrivningsår finns följande alternativ i fältet **Periodfrekvens**:

-   **Årligen** bokför det totala avskrivningsbeloppet som beräknas för räkenskapsåret som ett belopp på räkenskapsårets sista dag.
-   **Räkenskapsperiod** beräknar det totala avskrivningsbeloppet för räkenskapsåret. Detta belopp periodiseras sedan till de räkenskapsperioder som har definierats på sidan **Räkenskapskalendrar** för den räkenskapskalender som angetts för boken.

## <a name="example-of-straight-line-depreciation-of-an-unchanged-fixed-asset"></a>Exempel på linjär avskrivning av en oförändrad anläggningstillgång
En anläggningstillgång har följande egenskaper.

|                     |        |
|---------------------|--------|
| Anskaffningskostnad    | 11 000 |
| Skrotvärde       | 1 000  |
| Avskrivningsbas   | 10 000 |
| Antal tjänsteår  | 5      |
| Årlig avskrivning | 2 000  |

Avskrivningsbeloppet är samma varje år: Innan ÷tjänstelivstid (om anskaffning kostnadsberäknad – skrotvärde år)

| Period | Beräkning av årligt avskrivningsbelopp | Bokfört nettovärde i slutet av året |
|--------|-----------------------------------------------|---------------------------------------|
| År 1 | (11 000 – 1 000) ÷ 5 = 2 000                  | 9 000                                 |
| År 2 | (9 000 – 1 000) ÷ 4 = 2 000                   | 7 000                                 |
| År 3 | (7 000 – 1 000) ÷ 3 = 2 000                   | 5 000                                 |
| År 4 | (5 000 – 1 000) ÷ 2 = 2 000                   | 3 000                                 |
| År 5 | (3 000 – 1 000) ÷ 1 = 2 000                   | 1 000                                 |






