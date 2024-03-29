---
title: Huvudplanering för täckning av plats, obligatoriskt lagerställe
description: Denna artikel innehåller en beskrivning av hur en artikel som har webbplatsen som disponeringsdimension planeras. Lagerställe är en obligatorisk dimension.
author: t-benebo
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResStorageDimensionGroup, ReqItemTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2454
ms.assetid: aa135030-f98c-48bf-902c-e52f680dc247
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: df58017c25737cc946d09bf86ff7ad8bd33f4176
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2022
ms.locfileid: "9741051"
---
# <a name="master-planning-for-site-coverage-mandatory-warehouse"></a>Huvudplanering för täckning av plats, obligatoriskt lagerställe

[!include [banner](../includes/banner.md)]

Denna artikel innehåller en beskrivning av hur en artikel som har webbplatsen som disponeringsdimension planeras. Lagerställe är en obligatorisk dimension.

Det här huvudplaneringsscenariot omfattar följande villkor:

-   Dimensionen på en site är obligatorisk och måste anges på efterfrågetransaktionen. Den här inställningen går inte att ändra.
-   Lagerställedimensionen är obligatorisk och måste anges på efterfrågetransaktionen.
-   Sitedimensionen är aktiverad för disponeringsplanering. Även andra dimensioner kan ställas in för disponeringsplanering. De påverkas dock inte av multisitefunktionen.
-   Lagerställedimensionen är inte aktiverad för disponeringsplanering. Därför sammanställs tillgång och efterfrågan per site, och eventuellt, andra disponeringsplanerade dimensioner.

Följande figur illustrerar hur huvudplaneringen fortskrider. Parametrarna som refereras i bilden och deras siter är som följer:
-   Disponeringsplanering har definierats för artikeln. Klicka på **Hantering av produktinformation &gt; Produkter&gt; Frisläppta produkter**. Markera artikeln och klicka sedan på **Plan &gt; Artikeldisponering**.
-   Påfyllningsrelationer har definierats för lagret. Klick på **Lagerhantering &gt; Inställningar &gt; Lagerindelning &gt; Lagerställen**. Gå till fliken **Huvudplanering** och leta reda på fältgruppen **Huvudlagerställe**.
-   Standardordertypen anges som Produktion, Inköpsorder eller Kanban. Klicka på **Hantering av produktinformation &gt; Produkter&gt; Frisläppta produkter**. Välj artikeln och klicka sedan på **Plan &gt; Standardorderinställningar**. Se **Standardordertyp** i formuläret **Standardorderinställningar**.

![Efterfrågan för täckning av plats, lagerställe obligatorisk.](./media/multisitedemandexplosionscenarioforsitecoveragewarehousemandatory.jpg)



## <a name="additional-resources"></a>Ytterligare resurser

- [Huvudplanering och multisitefunktioner – översikt](master-plan-multisite-functionality.md)
- [Huvudplanering för plats och lagerställe, lagerställe obligatoriskt](master-plan-site-warehouse-coverage-warehouse-mandatory.md)
- [Huvudplanering för täckning av plats, lagerställe obligatoriskt](master-plan-site-coverage-warehouse-mandatory.md)
- [Huvudplanering för plats och lagerställe, lagerställe inte obligatoriskt](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)
- [Avgör strukturlisteversion](master-plan-bom-version-determined.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]