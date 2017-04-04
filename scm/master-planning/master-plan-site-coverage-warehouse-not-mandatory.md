---
title: "Huvudplanering för täckning av site, lagerställe ej obligatoriskt"
description: "Det här avsnittet innehåller en beskrivning av hur en artikel som har webbplatsen som disponeringsdimension planeras."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: EcoResStorageDimensionGroup, ReqItemTable
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 2474
ms.assetid: 316da918-67ae-43c5-baea-00ae559e29b0
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 28607f0fc8db99c9fc8e96b4514763b8cf589dd8
ms.lasthandoff: 03/31/2017


---

# <a name="master-planning-for-site-coverage-warehouse-not-mandatory"></a>Huvudplanering för täckning av site, lagerställe ej obligatoriskt

Det här avsnittet innehåller en beskrivning av hur en artikel som har webbplatsen som disponeringsdimension planeras.

Det här huvudplaneringsscenariot omfattar följande villkor:

-   Dimensionen på en site är obligatorisk och måste anges på efterfrågetransaktionen.
-   Lagerdimensionen har inte angetts vara obligatorisk. Lagret kan vara känt, men det används inte vid beräkningen av huvudplaneringen.
-   Sitedimensionen är aktiverad för disponeringsplanering.
-   Lagerställedimensionen är inte aktiverad för disponeringsplanering. Därför sammanställs tillgång och efterfrågan per site, och eventuellt, andra disponeringsplanerade dimensioner.

Följande figur illustrerar hur huvudplaneringen fortskrider. Parametrarna som refereras i bilden och deras siter är som följer:
-   Disponeringsplanering har definierats för artikeln. Klicka på **produktinformationshantering &gt;produkter&gt; frisläppta produkter**. Markera artikeln och klicka sedan på **planera &gt;artikeldisponering**.
-   Påfyllningsrelationer har definierats för lagret. Klicka på **lagerhantering &gt;inställningar &gt;Lagerindelning &gt;lagerställen**. Gå till fliken **Huvudplanering** och leta reda på fältgruppen **Huvudlagerställe**.
-   Standardordertypen anges som Produktion, Inköpsorder eller Kanban. Klicka på **produktinformationshantering &gt;produkter&gt; frisläppta produkter**. Markera artikeln och klicka sedan på **planera &gt;standardorderinställningar**. I formuläret **Standardorderinställningar**, se fältet **Standardordertyp** .

![Efterfrågenedbrytning för täckning av site, lagerställe ej obligatoriskt    ](./media/multisitedemandexplosionscenarioforsitecoveragewarehousenotmandatory.jpg)



<a name="see-also"></a>Se även
--------

[Master planning and multisite functionality](master-plan-multisite-functionality.md)

[Huvudplanering - platstäckning, lagerställe obligatoriskt](master-plan-site-coverage-warehouse-mandatory.md)

[Huvudplanering - täckning av plats och lagerställe, lagerstället är inte obligatoriskt](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[Huvudplanering - täckning av site och lagerställe, lagerställe obligatorisk](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[Huvudplanering - hur strukturlisteversionen avgörs](master-plan-bom-version-determined.md)


