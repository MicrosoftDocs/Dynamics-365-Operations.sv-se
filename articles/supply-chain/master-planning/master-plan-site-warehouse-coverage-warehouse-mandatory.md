---
title: Huvudplanering för täckning av site och lagerställe, lagerställe obligatorisk
description: Det här avsnittet beskriver hur en artikel som har plats och lagerställe som disponeringsdimensioner planeras. Lagerdimensionen är obligatorisk.
author: t-benebo
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResStorageDimensionGroup, ReqItemTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2554
ms.assetid: 3211e95f-b91a-4d27-8d92-f328ae2bcf12
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9055969391f9aed3780de871cd34de80e367ff5e
ms.sourcegitcommit: ad1afc6893a8dc32d1363395666b0fe1d50e983a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2022
ms.locfileid: "8468816"
---
# <a name="master-planning-for-site-and-warehouse-coverage-warehouse-mandatory"></a>Huvudplanering för täckning av site och lagerställe, lagerställe obligatorisk

[!include [banner](../includes/banner.md)]

Det här avsnittet beskriver hur en artikel som har plats och lagerställe som disponeringsdimensioner planeras. Lagerdimensionen är obligatorisk.

Det här huvudplaneringsscenariot omfattar följande villkor:

-   Dimensionen på en site är obligatorisk och måste anges på efterfrågetransaktionen.
-   Lagerställedimensionen är obligatorisk och måste anges på efterfrågetransaktionen.
-   Site- och lagerställedimensionerna är inställda för disponeringsplanering. Andra dimensioner kan också ha valts för disponeringsplanering. De påverkas emellertid inte av multisitefunktionen.

Följande figur illustrerar hur huvudplaneringen fortskrider. Parametrarna som refereras i bilden och deras siter är som följer:
-   Lagret har inställningen **Manuellt**. Klick på **Lagerhantering &gt; Inställningar &gt; Lagerindelning &gt; Lagerställen**. Se fältet **Manuell** på snabbfliken **Huvudplanering**.
-   Disponeringsplanering har definierats för artikeln. Klicka på **Hantering av produktinformation &gt; Produkter&gt; Frisläppta produkter**. Markera artikeln innan du i åtgärdsfönstret, på fliken **Plan**, klickar på **Artikeldisponering**.
-   Påfyllningsrelationer har definierats för lagret. Klick på **Lagerhantering &gt; Inställningar &gt; Lagerindelning &gt; Lagerställen**. Gå till snabbfliken **Huvudplanering** och leta reda på fältgruppen **Huvudlagerställe**.
-   Standardordertypen anges som Produktion, Inköpsorder eller Kanban. Klicka på **Hantering av produktinformation &gt; Produkter&gt; Frisläppta produkter**. Markera artikeln innan du i åtgärdsfönstret, på fliken **Plan**, klickar på **Standardorderinställningar**. Se **Standardordertyp** i formuläret **Standardorderinställningar**.

![Efterfrågan för täckning av plats och lagerställe, lagerställe obligatoriskt.](./media/multisitedemandexplosionscenarioforsiteandwarehousecoveragewarehousemandatory.jpg)



## <a name="additional-resources"></a>Ytterligare resurser

[Huvudplanering och multisitefunktioner – översikt](master-plan-multisite-functionality.md)

[Huvudplanering för täckning av plats, lagerställe obligatoriskt](master-plan-site-coverage-warehouse-mandatory.md)

[Huvudplanering för täckning av plats, lagerställe inte obligatoriskt](master-plan-site-coverage-warehouse-not-mandatory.md)

[Huvudplanering för plats och lagerställe, lagerställe inte obligatoriskt](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[Avgör strukturlisteversion](master-plan-bom-version-determined.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]