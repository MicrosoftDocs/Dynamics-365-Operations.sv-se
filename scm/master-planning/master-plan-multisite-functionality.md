---
title: Huvudplanering och multisitefunktioner
description: "Huvudplanering tar hänsyn till inställningarna för lagerdimensionerna för site och lagerställe."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: InventLocation, InventSite
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 2434
ms.assetid: 7f05c031-a446-4168-8cce-03a6305f5c4d
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 19eeee753c15cf2670948ce2c615a112813c16ad
ms.lasthandoff: 03/31/2017


---

# <a name="master-planning-and-multisite-functionality"></a>Huvudplanering och multisitefunktioner

Huvudplanering tar hänsyn till inställningarna för lagerdimensionerna för site och lagerställe. 

Platsdimensionen är obligatorisk och du kan ange att lagerställedimensionen ska vara obligatorisk.

Om en dimension är obligatorisk måste ett dimensionsvärde anges för alla lagertransaktioner. Detta innebär att platsen och lagerstället för den ursprungliga efterfrågan är känd under huvudplaneringen. Sitedimensionen är också bestående, vilket innebär att sitevärdet inte ändras under nedbrytningen av efterfrågan på lägre nivåer.

Om lagerställedimensionen inte anges som obligatorisk kan det hända att lagerstället är okänt i den ursprungliga efterfrågan. Planeringsmotorn måste då identifiera vilket lagerställe som ska användas utifrån de inställningar som har definierats för artikeln, enskilda lagerställen och informationen på orderraden.

I följande wiki-artiklar beskrivs hur planeringsmotorn används för att avgöra vilket lagerställe som ska användas när olika inställningar har angetts.

[Huvudplanering - täckning av site och lagerställe, lagerställe obligatorisk](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[Huvudplanering - platstäckning, lagerställe obligatoriskt](master-plan-site-coverage-warehouse-mandatory.md)

[Huvudplanering - täckning av plats och lagerställe, lagerstället är inte obligatoriskt](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[Huvudplanering - täckning av site, lagerställe ej obligatoriskt](master-plan-site-coverage-warehouse-not-mandatory.md)

[Huvudplanering - hur strukturlisteversionen bestäms](master-plan-bom-version-determined.md)


