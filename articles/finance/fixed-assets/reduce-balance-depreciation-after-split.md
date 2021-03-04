---
title: Degressiv avskrivning efter en delning
description: I det här avsnittet beskrivs den metod som används i Anläggningstillgångar för att beräkna avskrivning efter att en tillgång har delats med metoden Degressiv avskrivning.
author: moaamer
manager: Ann Beebe
ms.date: 11/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-11-17
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 615d17c71b904d426081d4c57492ba7e95c2c749
ms.sourcegitcommit: 65f9e2584c0530b1a71655aae09101691726b47f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/01/2020
ms.locfileid: "4650685"
---
# <a name="reduce-balance-depreciation-after-a-split"></a>Degressiv avskrivning efter en delning

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs den metod som används i Anläggningstillgångar för att beräkna avskrivning efter att en tillgång har delats till en annan tillgång med metoden Degressiv avskrivning. Det avskrivningsår som är konfigurerat i tillgångsboken är räkenskapsåret. Mer information finns i [Degressiv avskrivning](reduce-balance-depreciation.md) och [Dela en anläggningstillgång](tasks/split-fixed-asset.md).

Om du delar en anläggningstillgång under en räkenskapsperiod som infaller senare än perioden då tillgången förvärvades, kommer den degressiva avskrivningen att redovisas mot tillgångens bokförda nettovärde (BNV) för föregående år. Det tar också hänsyn till de anskaffnings- och avskrivningsjusteringstransaktioner som genererades från transaktionen som delade upp tillgången. Detta förutsätter att tillgången förvärvades under ett räkenskapsår och delas upp i ett senare räkenskapsår. Det belopp som måste skrivas av för den ursprungliga tillgången efter delningen reflekterar tillgångens BNV innan tillgången delades, och anskaffnings- och avskrivningsjusteringstransaktionen som bokfördes för delningen.

Följande villkor gäller till exempel:

- Räkenskapsperioden är från den 30 juni till den 1 juli.
- Den degressiva avskrivningen i procent är 18 procent, och en tillgång förvärvas i juni 2019 till ett anskaffningspris på 10 000 USD.
- Avskrivningen för det första räkenskapsåret är lika med 18 000 USD, månadsavskrivningen är lika med 150 USD och tillgången avskrivs sedan tills 2019 november, till beloppet 738,75 USD.
- I november 2019 delas 80 procent av tillgången till en annan anläggningstillgång.

[![Degressiv avskrivning efter en delning](./media/reduce-balance-depreciation-after-split.png)](./media/reduce-balance-depreciation-after-split.png)

Det belopp som ska skrivas av för den ursprungliga till gången är 1 822,25 USD. Det här beloppet är lika med BNV innan delningstransaktionen bokförs (9 111,25 USD) plus den anskaffningsjustering som genereras vid bokföringen av den uppdelade transaktionen (-8 000 USD) plus den avskrivningsjustering som genererades under delningstransaktionen (711 USD). Därför är avskrivningen för det andra året (1 822,25 × 18 procent) ÷ 12 = 27,33 USD.

Beloppet som ska skrivas av för den nya anläggningstillgången under det första året är (8 000 × 18 procent) ÷ 12 = 120 USD.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]