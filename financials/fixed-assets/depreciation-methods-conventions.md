---
title: Avskrivningsmetoder och praxis
description: "Den här artikeln ger en översikt över avskrivningspraxis och avskrivningsmetoder som stöds av Microsoft Dynamics AX."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: AssetDepreciationProfile, AssetGroupBookSetup, AssetGroupDepBookSetup
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 3441
ms.assetid: 1d8267b1-86a8-44bf-8814-f56b5d45a0ae
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 8e89a57dda8f2d392483ed13c686ea97b74926b0
ms.openlocfilehash: 51c053e6c130d20258e02284d097431a18bb38cb
ms.lasthandoff: 03/31/2017


---

# <a name="depreciation-methods-and-conventions"></a>Avskrivningsmetoder och praxis

Den här artikeln ger en översikt över avskrivningspraxis och avskrivningsmetoder som stöds av Microsoft Dynamics AX.

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

 



<a name="see-also"></a>Se även
--------

[Fixed asset depreciation](fixed-asset-depreciation.md)

[Straight line service life depreciation](Straight-line-service-life-depreciation.md)

[Reducing balance depreciation](reduce-balance-depreciation.md)

[Manual depreciation](manual-depreciation.md)

[Factor depreciation](factor-depreciation.md)

[Consumption depreciation](consumption-depreciation.md)

[Straight line life remaining depreciation](straight-line-life-remaining-depreciation.md)

[125 % degressiv avskrivning](125-percent-reducing-balance-depreciation.md)

[150 % degressiv avskrivning](150-percent-reducing-balance-depreciation.md)

[175 % degressiv avskrivning](175-percent-reducing-balance-depreciation.md)

[200 % degressiv avskrivning](200-percent-reducing-balance-depreciation.md)


