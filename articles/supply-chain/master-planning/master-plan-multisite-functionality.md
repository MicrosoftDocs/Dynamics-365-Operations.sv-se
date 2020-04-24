---
title: Huvudplanering och multisitefunktioner – översikt
description: Huvudplanering tar hänsyn till inställningarna för lagerdimensionerna för site och lagerställe.
author: roxanadiaconu
manager: tfehr
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventLocation, InventSite
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2434
ms.assetid: 7f05c031-a446-4168-8cce-03a6305f5c4d
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5b26ff5c2f580c30113b82302bbad744bbf285ff
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3213732"
---
# <a name="master-planning-and-multisite-functionality-overview"></a>Huvudplanering och multisitefunktioner – översikt

[!include [banner](../includes/banner.md)]

Huvudplanering tar hänsyn till inställningarna för lagerdimensionerna för site och lagerställe. 

Platsdimensionen är obligatorisk och du kan ange att lagerställedimensionen ska vara obligatorisk.

Om en dimension är obligatorisk måste ett dimensionsvärde anges för alla lagertransaktioner. Detta innebär att platsen och lagerstället för den ursprungliga efterfrågan är känd under huvudplaneringen. Sitedimensionen är också bestående, vilket innebär att sitevärdet inte ändras under nedbrytningen av efterfrågan på lägre nivåer.

Om lagerställedimensionen inte anges som obligatorisk kan det hända att lagerstället är okänt i den ursprungliga efterfrågan. Planeringsmotorn måste då identifiera vilket lagerställe som ska användas utifrån de inställningar som har definierats för artikeln, enskilda lagerställen och informationen på orderraden.

I följande avsnitt beskrivs hur planeringsmotorn används för att avgöra vilket lagerställe som ska användas när olika inställningar har angetts.

[Huvudplanering för plats och lagerställe, lagerställe obligatoriskt](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[Huvudplanering för täckning av plats, lagerställe obligatoriskt](master-plan-site-coverage-warehouse-mandatory.md)

[Huvudplanering för plats och lagerställe, lagerställe inte obligatoriskt](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[Huvudplanering för täckning av plats, lagerställe inte obligatoriskt](master-plan-site-coverage-warehouse-not-mandatory.md)

[Avgör strukturlisteversion](master-plan-bom-version-determined.md)



