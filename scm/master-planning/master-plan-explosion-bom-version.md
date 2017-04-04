---
title: Nedbrytning av en strukturlisteversion
description: "Den här artikeln scenario som omfattar nedbrytning av en strukturlistan (BOM) för huvudplanering."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ReqTransExplosion
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 19211
ms.assetid: fe08c2e6-9cc5-4e34-bbb2-cd07843403b5
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 6461a07f8c8f02f584e5ef70b21ebaf04f29b57b
ms.lasthandoff: 03/31/2017


---

# <a name="explosion-of-a-bom-version"></a>Nedbrytning av en strukturlisteversion

Den här artikeln scenario som omfattar nedbrytning av en strukturlistan (BOM) för huvudplanering.

En efterfrågenedbrytning av en strukturlisteversion skapar en efterfrågan för varje artikelrad i strukturlistan på en viss site och kanske ett särskilt lager. I en sitespecifik strukturlista kan ett visst lager definieras för varje strukturlisterad. Dessutom bestämmer artikeldimensionens inställningar huruvida lagret krävs för varje strukturlisterad. Den resulterande efterfrågan för varje strukturlisterad blir i sin tur utgångspunkten för en vidare efterfrågenedbrytning. Det här huvudplaneringsscenariot omfattar följande villkor:

-   Sitedimensionen är obligatorisk och måste anges på efterfrågetransaktionen.
-   Sitedimensionen är konsekvent. Därför är siten för efterfrågan på lägre nivåer densamma som siten för den ursprungliga efterfrågetransaktionen.

Följande bild visar hur processen för efterfrågenedbrytningen i huvudplaneringen fortskrider. ![Efterfrågenedbrytning med hjälp av strukturlisteversion](./media/multisitedemandexplosionscenariousingbomversion.gif)

<a name="see-also"></a>Se även
--------

[Huvudplanering - hur strukturlisteversionen avgörs](master-plan-bom-version-determined.md)

[Master planning and multisite functionality](master-plan-multisite-functionality.md)

