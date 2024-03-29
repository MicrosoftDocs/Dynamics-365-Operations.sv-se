---
title: Huvudplanering för täckning av site och lagerställe, lagerställe inte obligatorisk
description: Denna artikel beskriver hur en artikel som har webbplats och lagerställe som disponeringsdimensioner planeras. Lagerdimensionen är inte obligatorisk.
author: t-benebo
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResStorageDimensionGroup, ReqItemTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2514
ms.assetid: 92d47bdd-df68-4f60-ac9a-96aa08236c26
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b4989a05f4647ac836b78692da7f63396dbef788
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2022
ms.locfileid: "9741023"
---
# <a name="master-planning-for-site-and-warehouse-coverage-warehouse-not-mandatory"></a>Huvudplanering för täckning av site och lagerställe, lagerställe inte obligatorisk

[!include [banner](../includes/banner.md)]

Denna artikel beskriver hur en artikel som har webbplats och lagerställe som disponeringsdimensioner planeras. Lagerdimensionen är inte obligatorisk.

Det här huvudplaneringsscenariot omfattar följande villkor:

-   Dimensionen på en site är obligatorisk och måste anges på efterfrågetransaktionen. Den här inställningen går inte att ändra.
-   Lagerdimensionen har inte angetts vara obligatorisk. Lagret kan vara känt, men det används inte vid beräkningen av huvudplaneringen.
-   Plats- och lagerdimensionerna är inställda på disponeringsplanering. Andra dimensioner kan också ha valts för disponeringsplanering. De påverkas emellertid inte av multisitefunktionen.

Följande figur illustrerar hur huvudplaneringen fortskrider. Parametrarna som refereras i bilden och deras siter är som följer:
-   Lagret har inställningen Manuellt. Klick på **Lagerhantering &gt; Inställningar &gt; Lagerindelning &gt; Lagerställen**. Se fältet **Manuell** på snabbfliken **Huvudplanering**.
-   Disponeringsplanering har definierats för artikeln. Klicka på **Hantering av produktinformation &gt; Produkter&gt; Frisläppta produkter**. Markera artikeln innan du i åtgärdsfönstret, på fliken **Plan**, klickar på **Artikeldisponering**.
-   Påfyllningsrelationer har definierats för lagret. Klick på **Lagerhantering &gt; Inställningar &gt; Lagerindelning &gt; Lagerställen**. Gå till snabbfliken **Huvudplanering** och leta reda på fältgruppen **Huvudlagerställe**.
-   Standardordertypen anges som Produktion, Inköpsorder eller Kanban. Klicka på **Hantering av produktinformation &gt; Produkter&gt; Frisläppta produkter**. Markera artikeln innan du i åtgärdsfönstret, på fliken **Plan**, klickar på **Standardorderinställningar**. Se **Standardordertyp** i formuläret **Standardorderinställningar**.

![Efterfrågan för plats och lagerställe, lagerställe ej.](./media/multisitedemandexplosionscenarioforsiteandwarehousecoveragewarehousenotmandatory.jpg)



## <a name="additional-resources"></a>Ytterligare resurser

- [Huvudplanering och multisitefunktioner – översikt](master-plan-multisite-functionality.md)
- [Huvudplanering för täckning av plats, lagerställe obligatoriskt](master-plan-site-warehouse-coverage-warehouse-mandatory.md)
- [Huvudplanering för plats och lagerställe, lagerställe obligatoriskt](master-plan-site-coverage-warehouse-mandatory.md)
- [Huvudplanering för plats och lagerställe, lagerställe inte obligatoriskt](master-plan-site-coverage-warehouse-not-mandatory.md)
- [Avgör strukturlisteversion](master-plan-bom-version-determined.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]