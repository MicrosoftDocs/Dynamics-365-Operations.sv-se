---
title: Nedbrytning av en strukturlisteversion
description: Den här artikeln förklarar ett övergripande planeringsscenario som omfattar nedbrytning av en strukturlista (BOM).
author: roxanadiaconu
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqTransExplosion
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19211
ms.assetid: fe08c2e6-9cc5-4e34-bbb2-cd07843403b5
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1f50d9f2f7249ecb4090983e245d4700020e0886
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "5005187"
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



