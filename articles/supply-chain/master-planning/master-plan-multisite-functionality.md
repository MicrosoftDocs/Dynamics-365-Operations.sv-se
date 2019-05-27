---
title: Huvudplanering och multisitefunktioner
description: Huvudplanering tar hänsyn till inställningarna för lagerdimensionerna för site och lagerställe.
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventLocation, InventSite
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2434
ms.assetid: 7f05c031-a446-4168-8cce-03a6305f5c4d
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 10981e0fe201566c83fd28c792000865bc533cd3
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1573101"
---
# <a name="master-planning-and-multisite-functionality"></a>Huvudplanering och multisitefunktioner

[!include [banner](../includes/banner.md)]

Huvudplanering tar hänsyn till inställningarna för lagerdimensionerna för site och lagerställe. 

Platsdimensionen är obligatorisk och du kan ange att lagerställedimensionen ska vara obligatorisk.

Om en dimension är obligatorisk måste ett dimensionsvärde anges för alla lagertransaktioner. Detta innebär att platsen och lagerstället för den ursprungliga efterfrågan är känd under huvudplaneringen. Sitedimensionen är också bestående, vilket innebär att sitevärdet inte ändras under nedbrytningen av efterfrågan på lägre nivåer.

Om lagerställedimensionen inte anges som obligatorisk kan det hända att lagerstället är okänt i den ursprungliga efterfrågan. Planeringsmotorn måste då identifiera vilket lagerställe som ska användas utifrån de inställningar som har definierats för artikeln, enskilda lagerställen och informationen på orderraden.

I följande avsnitt beskrivs hur planeringsmotorn används för att avgöra vilket lagerställe som ska användas när olika inställningar har angetts.

[Huvudplanering - täckning av site och lagerställe, lagerställe obligatorisk](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[Huvudplanering - platstäckning, lagerställe obligatoriskt](master-plan-site-coverage-warehouse-mandatory.md)

[Huvudplanering - täckning av plats och lagerställe, lagerstället är inte obligatoriskt](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[Huvudplanering - täckning av site, lagerställe ej obligatoriskt](master-plan-site-coverage-warehouse-not-mandatory.md)

[Huvudplanering - hur strukturlisteversionen bestäms](master-plan-bom-version-determined.md)



