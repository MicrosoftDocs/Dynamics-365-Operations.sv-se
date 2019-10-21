---
title: Degressiv avskrivning
description: Den här avsnittet ger en översikt över metoden för degressiv avskrivning.
author: ShylaThompson
manager: AnnBe
ms.date: 04/25/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 3281
ms.assetid: 1b86763d-d47c-4a6a-a9a6-d97a736750da
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2dd4a8726ca194de2e5d95128659f3b212eaace5
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2179946"
---
# <a name="reduce-balance-depreciation"></a>Degressiv avskrivning

[!include [banner](../includes/banner.md)]

Den här avsnittet ger en översikt över metoden för degressiv avskrivning.

När du ställer in en avskrivningsprofil för anläggningstillgångar och väljer Degressiv avskrivning i fältet Metod på sidan Avskrivningsprofiler skrivs tillgångarna som har tilldelats den här avskrivningsprofilen av med samma procentsats under varje avskrivningsperiod.

Om du vill ställa in degressiv avskrivning måste du också göra val i fält på Allmänt snabbfliken på sidan Avskrivningsprofiler. Först väljer du ett år i fältet Avskrivningsår. Beroende på valet visas olika alternativ i fältet Periodfrekvens, vilket beskrivs i följande avsnitt. 

Du måste också ange ett värde i fältet Procent för avskrivningsprofilen. Om du väljer alternativet Full avskrivning tas kvarstående avskrivningsunderlag i den sista avskrivningsperioden och kan vara ett stort belopp. Vissa länder/regioner använder inte en omställning till en linjär metod. Omställning sker när den alternativa avskrivningsmetodens mängd är större än eller lika med den primära avskrivningsprofilens mängd och den alternativa metodens mängd väljs som avskrivningsmängd. 

Eftersom en tillgång aldrig skrivs av helt med en procentberäkning måste du välja det alternativet Full avskrivning för att skriva av en tillgång helt.

## <a name="select-a-depreciation-year"></a>Välj ett avskrivningsår
Du kan välja Kalender eller Räkenskapsår i fältet Avskrivningår på sidan Avskrivningsprofiler. Valet avgör vilka alternativ som är tillgängliga i fältet Periodfrekvens. Standardalternativet är Kalender.

### <a name="calendar"></a>Kalender

Med alternativet Kalender uppdaterar du avskrivningsbasen som vanligtvis är bokfört nettovärde minus skrotvärde, den 1 januari varje år. I exemplet på degressiv avskrivning senare i det här avsnittet utgör avskrivningsbasen täljaren i det första uttrycket i beräkningen som görs i kolumnen Beräkning. 

Om du väljer Kalender är följande alternativ tillgängliga i fältet Periodfrekvens, som definierar bokföringsdatumen för periodisering av avskrivningen och beloppen under kalenderåret:

-   Årligen bokför den 31 december.
-   Månadsvis bokför ett månatligt belopp i slutet av varje månad.
-   Kvartalvis bokför ett kvartalsbelopp i slutet av varje kvartal (31 mars, 30 juni, 30 september och 31 december).
-   Halvårsvis bokför ett halvårsbelopp i slutet av varje halvår (30 juni och 31 december).
-   Dagligen bokför avskrivningsbeloppet för den dagliga avskrivningsmetoden genom att använda en transaktion för varje dag.

Om du till exempel väljer Årligen, bokförs årets avskrivning alltså bara en gång, den 31 december varje år. Om du väljer Månadsvis, bokförs månadens avskrivning som 1/12 av det årliga avskrivningsbeloppet.

### <a name="fiscal"></a>Skatt

Om du väljer Räkenskapsår i fältet Avskrivning används den linjära avskrivningsmetoden. Det beräknas utifrån räkenskapsåret, som ställs in på sidan Räkenskapskalendrar som väljs på sidan Redovisning. Exempelvis för räkenskapsåret 1 juli - 30 juni startar alltså avskrivningsberäkningen den 1 juli. Räkenskapsåret kan vara längre eller kortare än 12 månader. Avskrivningen justeras för varje räkenskapsperiod. Längden på nästa räkenskapsår baseras på de räkenskapsperioder som du ställer in när du skapar ett nytt räkenskapsår på sidan Räkenskapskalendrar.


Om du väljer Räkenskapsår har du följande alternativ i fältet Räkenskapsår.

-   Årligen bokför det totala avskrivningsbeloppet som beräknas för räkenskapsåret som ett belopp på räkenskapsårets sista dag.
-   Räkenskapsperioden bokför det totala avskrivningsbeloppet som beräknas för räkenskapsåret. Beloppet periodiseras till de räkenskapsperioder som definierats för räkenskapskalendern som väljs på redovisningssidan, eller för den räkenskapskalender som väljs för boken för en anläggningstillgång.

## <a name="example-of-reducing-balance-depreciation"></a>Exempel på en degressiv avskrivning

Anta att anskaffningspriset för anläggningstillgången är 11 000, kassationsvärdet är 1 000 och procentfaktorn för avskrivning är 30. 

Med metoden för degressiv avskrivning beräknas 30 procent av avskrivningsbasen (bokfört nettovärde minus kassationsvärde) i slutet av föregående avskrivningsperiod. Avskrivning för de första tre åren visas i följande tabell.

| Period | Beräkning av årligt avskrivningsbelopp | Bokfört nettovärde i slutet av året |
|--------|-------------------------------------------|---------------------------------------|
| År 1 | (11 000 - 1 000) \* 30% = 3 000           | (11 000 - 1 000) - 3 000 = 7 000      |
| År 2 | (7 000 - 1 000) \* 30% = 1 800            | (7 000 -1 800) = 5 200                |
| År 3 | (5 200 - 1 000) \* 30% = 1 260            | (5 200 - 1 260) = 3 940               |


-





