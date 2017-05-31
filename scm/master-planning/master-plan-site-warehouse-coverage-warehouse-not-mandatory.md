---
title: "Huvudplanering för täckning av site och lagerställe, lagerställe inte obligatorisk"
description: "Det här avsnittet beskriver hur en artikel som har plats och lagerställe som disponeringsdimensioner planeras. Lagerdimensionen är inte obligatorisk."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResStorageDimensionGroup, ReqItemTable
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 2514
ms.assetid: 92d47bdd-df68-4f60-ac9a-96aa08236c26
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: ec5150abd297a7c00ac180db581adb30bef65b3f
ms.contentlocale: sv-se
ms.lasthandoff: 05/25/2017


---

# <a name="master-planning-for-site-and-warehouse-coverage-warehouse-not-mandatory"></a>Huvudplanering för täckning av site och lagerställe, lagerställe inte obligatorisk

[!include[banner](../includes/banner.md)]


Det här avsnittet beskriver hur en artikel som har plats och lagerställe som disponeringsdimensioner planeras. Lagerdimensionen är inte obligatorisk.

Det här huvudplaneringsscenariot omfattar följande villkor:

-   Dimensionen på en site är obligatorisk och måste anges på efterfrågetransaktionen. Den här inställningen går inte att ändra.
-   Lagerdimensionen har inte angetts vara obligatorisk. Lagret kan vara känt, men det används inte vid beräkningen av huvudplaneringen.
-   Plats- och lagerdimensionerna är inställda på disponeringsplanering. Andra dimensioner kan också ha valts för disponeringsplanering. De påverkas emellertid inte av multisitefunktionen.

Följande figur illustrerar hur huvudplaneringen fortskrider. Parametrarna som refereras i bilden och deras siter är som följer:
-   Lagret har inställningen Manuellt. Klick på **Lagerhantering &gt; Inställningar &gt; Lagerindelning &gt; Lagerställen**. Se fältet **Manuell** på snabbfliken **Huvudplanering**.
-   Disponeringsplanering har definierats för artikeln. Klicka på **Hantering av produktinformation &gt; Produkter&gt; Frisläppta produkter**. Markera artikeln och sedan, i åtgärdsfönstret, på fliken **Plan**, klickar du på **Artikeldisponering**.
-   Påfyllningsrelationer har definierats för lagret. Klick på **Lagerhantering &gt; Inställningar &gt; Lagerindelning &gt; Lagerställen**. Gå till snabbfliken **Huvudplanering** och leta reda på fältgruppen **Huvudlagerställe**.
-   Standardordertypen anges som Produktion, Inköpsorder eller Kanban. Klicka på **Hantering av produktinformation &gt; Produkter&gt; Frisläppta produkter**. Markera artikeln och sedan, i åtgärdsfönstret, på fliken **Plan**, klickar du på **Standardorderinställningar**. Se **Standardordertyp** i formuläret **Standardorderinställningar**.

![Efterfrågenedbrytning för site och lagerställe, lagerställe ej obligatoriskt](./media/multisitedemandexplosionscenarioforsiteandwarehousecoveragewarehousenotmandatory.jpg)

 
-



<a name="see-also"></a>Se även
--------

[Huvudplanering och multiplatsfunktioner](master-plan-multisite-functionality.md)

[Huvudplanering - täckning av site och lagerställe, lagerställe obligatorisk](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[Huvudplanering - platstäckning, lagerställe obligatoriskt](master-plan-site-coverage-warehouse-mandatory.md)

[Huvudplanering - täckning av site, lagerställe ej obligatoriskt](master-plan-site-coverage-warehouse-not-mandatory.md)

[Huvudplanering - hur strukturlisteversionen bestäms](master-plan-bom-version-determined.md)




