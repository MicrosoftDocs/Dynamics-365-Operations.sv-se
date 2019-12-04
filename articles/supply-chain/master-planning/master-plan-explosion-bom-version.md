---
title: Nedbrytning av en strukturlisteversion
description: Den här artikeln förklarar ett övergripande planeringsscenario som omfattar nedbrytning av en strukturlista (BOM).
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqTransExplosion
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 19211
ms.assetid: fe08c2e6-9cc5-4e34-bbb2-cd07843403b5
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dbdfc169365cb73e13383b11efcd8983aef4bbca
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/18/2019
ms.locfileid: "2815328"
---
# <a name="explosion-of-a-bom-version"></a>Nedbrytning av en strukturlisteversion

[!include [banner](../includes/banner.md)]

Den här artikeln förklarar ett övergripande planeringsscenario som omfattar nedbrytning av en strukturlista (BOM).

En efterfrågenedbrytning av en strukturlisteversion skapar en efterfrågan för varje artikelrad i strukturlistan på en viss site och kanske ett särskilt lager. I en sitespecifik strukturlista kan ett visst lager definieras för varje strukturlisterad. Dessutom bestämmer artikeldimensionens inställningar huruvida lagret krävs för varje strukturlisterad. Den resulterande efterfrågan för varje strukturlisterad blir i sin tur utgångspunkten för en vidare efterfrågenedbrytning. Det här huvudplaneringsscenariot omfattar följande villkor:

-   Sitedimensionen är obligatorisk och måste anges på efterfrågetransaktionen.
-   Sitedimensionen är konsekvent. Därför är siten för efterfrågan på lägre nivåer densamma som siten för den ursprungliga efterfrågetransaktionen.

Följande bild visar hur processen för efterfrågenedbrytningen i huvudplaneringen fortskrider. ![Efterfrågenedbrytning med hjälp av strukturlisteversion](./media/multisitedemandexplosionscenariousingbomversion.gif)

<a name="additional-resources"></a>Ytterligare resurser
--------

[Avgör strukturlisteversion](master-plan-bom-version-determined.md)

[Huvudplanering och multisitefunktioner – översikt](master-plan-multisite-functionality.md)



