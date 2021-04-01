---
title: Avskrivningsmetoder och praxis
description: Den här artikeln ger en översikt över avskrivningspraxis och avskrivningsmetoder som stöds av Microsoft Dynamics 365 Finance.
author: ShylaThompson
manager: AnnBe
ms.date: 04/25/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetDepreciationProfile, AssetGroupBookSetup, AssetGroupDepBookSetup
audience: Application User
ms.reviewer: roschlom
ms.custom: 3441
ms.assetid: 1d8267b1-86a8-44bf-8814-f56b5d45a0ae
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1aacc57051f21b992d9f7feb44c99511fc2a65bb
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5241300"
---
# <a name="depreciation-methods-and-conventions"></a>Avskrivningsmetoder och praxis

[!include [banner](../includes/banner.md)]

Den här artikeln ger en översikt över avskrivningspraxis och avskrivningsmetoder som stöds.

Du kan välja olika avskrivningsmetoder och -praxis. Syftet med metoderna är att fördela anläggningstillgångens avskrivbara värde i räkenskapsperioder. Anläggningstillgångens avskrivbara värde är anskaffningspriset minus eventuellt kassationsvärde. 

Om du använder avskrivningspraxis och ändrar senaste körningsdatum för avskrivning för en tillgång, som orsakar att vissa avskrivningar hoppas över, kan avskrivningen för förra året bli högre eller lägre än förväntat. Avskrivningen justeras med antalet avskrivningsperioder som påverkas av ändringen av senaste körningsdatum för avskrivning.

Om du till exempel använder praxis för halvårsavskrivning över tre år sker avskrivning normalt över 3 1/2 år. Om du ändrar senaste körningsdatum för avskrivning under de 3 1/2 åren, flyttar det senaste avskrivningsåret ut antalet perioder som påverkas. Om du flyttar datumet tre månader har förra året nio månaders avskrivning, medan det normalt skulle vara sex månaders avskrivning.

Du kan välja bland följande avskrivningspraxis.


-   Halvår
-   Hel månad
-   Mellankvartal
-   Mitt i månaden (första i månaden)
-   Mitt i månaden (15:e i månaden)
-   Halvår (start på året)
-   Halvår (nästa år)

Du kan välja mellan följande avskrivningsmetoder.
-   Linjär tjänstelivstid
-   Degressiv avskrivning
-   Manuell
-   Faktor
-   Förbrukning
-   Linjär återstående livstid
-   200 % degressiv avskrivning
-   175 % degressiv avskrivning
-   150 % degressiv avskrivning
-   125 % degressiv avskrivning





<a name="additional-resources"></a>Ytterligare resurser
--------

[Avskrivning av anläggningstillgång](fixed-asset-depreciation.md)

[Linjär avskrivning av tjänstelivstid](Straight-line-service-life-depreciation.md)

[Minska balans för avskrivning](reduce-balance-depreciation.md)

[Manuell avskrivning](manual-depreciation.md)

[Faktoravskrivning](factor-depreciation.md)

[Förbrukningsavskrivning](consumption-depreciation.md)

[Linjär avskrivning kvarstående livstid](straight-line-life-remaining-depreciation.md)

[125 procent degressiv avskrivning](125-percent-reducing-balance-depreciation.md)

[150 procent degressiv avskrivning](150-percent-reducing-balance-depreciation.md)

[175 procent degressiv avskrivning](175-percent-reducing-balance-depreciation.md)

[200 procent degressiv avskrivning](200-percent-reducing-balance-depreciation.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]