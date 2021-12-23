---
title: 150 procent degressiv avskrivning
description: Det här ämnet ger en översikt över 150-procentsmetoden för degressiv avskrivning.
author: moaamer
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: roschlom
ms.custom: 13891
ms.assetid: 36d1112d-921c-4fff-abe0-0ff2429848d3
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fe8a794e9d5f01e4cd8844b5388b37970607d0be
ms.sourcegitcommit: 62ca651c94e61aaa69cfa59e861f263f89d01c4a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/03/2021
ms.locfileid: "7883322"
---
# <a name="150-percent-reducing-balance-depreciation"></a>150 procent degressiv avskrivning

[!include [banner](../includes/banner.md)]

Det här ämnet ger en översikt över 150-procentsmetoden för degressiv avskrivning.

När du ställer in en avskrivningsprofil för anläggningstillgångar och väljer **150 % degressiv avskrivning** i fältet **Metod** på sidan **Avskrivningsprofiler** skrivs tillgångarna som tilldelas den här avskrivningsprofilen av med samma procentsats under varje avskrivningsperiod. Denna procentsats beräknas baserat på tillgångens tjänstelivstid. Om till exempel en tillgång har en tjänstelivstid på fem år, beräknas procentsatsen som 30 procent (150 % ÷ 5). 

Om du vill ställa in 150 % degressiv avskrivning måste du också markera alternativ i fältet **Avskrivningsår** och fältet **Periodfrekvens** på sidan **Avskrivningsprofiler**. De tillgängliga alternativen i fältet **Periodfrekvens** varierar beroende på vilket värde som valts i fältet **Avskrivningsår**.

## <a name="selection-of-depreciation-year"></a>Val av avskrivningsår
Du kan välja **Kalender** eller **Räkenskapsår** i fältet **Avskrivningsår** på sidan **Avskrivningsprofiler**. 

Standardvärdet är **Kalender**. Valet avgör vilka alternativ som är tillgängliga i fältet **Periodfrekvens**. Det här fältet definierar bokföringsdatumen för periodisering av avskrivningen och beloppen under kalenderåret.

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

Om du väljer **Räkenskapsår** i fältet **Avskrivningsår**, beräknas 150 % degressiv avskrivning baserat på räkenskapsåret för räkenskapskalendern som angetts för boken, eller för den räkenskapskalender som har valts på sidan **Huvudbok**. Räkenskapskalendrar ställs in på sidan **Räkenskapskalendrar**. 

För räkenskapsåret 1 juli – 30 juni startar alltså avskrivningsberäkningen den 1 juli. Räkenskapsåret kan vara längre eller kortare än 12 månader. Avskrivningen justeras för varje period. Längden på nästa räkenskapsår bestäms av inställningen för perioder på sidan **Räkenskapskalendrar**. 

Om du väljer **Räkenskapsår** som avskrivningsår finns följande alternativ i fältet **Periodfrekvens**:

-   **Årlig** bokför det totala avskrivningsbeloppet som beräknas för räkenskapsåret som ett belopp på räkenskapsårets sista dag.
-   **Räkenskapsperiod** bokför det totala avskrivningsbeloppet som beräknas för räkenskapsåret. Detta belopp periodiseras till de räkenskapsperioder som har definierats på **Räkenskapskalendrar**.

## <a name="example-of-150-reducing-balance-depreciation"></a>Exempel på 150 % degressiv avskrivning

| &nbsp;                         | &nbsp; |
|--------------------------------|--------|
| Anskaffningskostnad               | 11 000 |
| Skrotvärde                  | 1 000  |
| Avskrivningsbas              | 10 000 |
| Antal tjänsteår             | 5      |
| Årlig avskrivningsprocent | 30 %    |

Den degressiva avskrivningsmetoden på 150 % delar 150 procent med tjänstelivstiden i år. Den procenten multipliceras med anläggningstillgångens bokförda nettovärde för att bestämma årets avskrivningsbelopp.

| Period | Beräkning av årligt avskrivningsbelopp | Bokfört värde             | Bokfört nettovärde i slutet av året |
|--------|-----------------------------------------------|------------------------|---------------------------------------|
| År 1 | (11 000 – 1 000) × 30 % = 3 000                | 11 000 – 3 000 = 8 000 | 11 000 – 1 000 – 3 000 = 7 000        |
| År 2 | 7 000 × 30 % = 2 100                           | 8 000 – 2 100 = 5 900  | 7 000 – 2 100 = 4 900                 |
| År 3 | 4 900 × 30 % = 1 470                           | 5 900 – 1 470 = 4 430  | 4 900 – 1 470 = 3 430                 |

> [!NOTE]
> Om beloppet som beräknas med den degressiva avskrivningsmetoden 150 % blir lägre än beloppet som beräknas med den linjära metoden, sker vanligtvis en konvertering till den linjära metoden för resterande tjänstelivstid.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
