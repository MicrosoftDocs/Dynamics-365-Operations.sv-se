---
title: Huvudplanering för täckning av plats och lagerställe ej obligatoriskt
description: Denna artikel innehåller en beskrivning av hur en artikel som har webbplatsen som disponeringsdimension planeras.
author: t-benebo
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResStorageDimensionGroup, ReqItemTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2474
ms.assetid: 316da918-67ae-43c5-baea-00ae559e29b0
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 327bb259cc108f1fad068c847441229dcaee7ff1
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8859239"
---
# <a name="master-planning-for-site-coverage-warehouse-not-mandatory"></a>Huvudplanering för täckning av plats och lagerställe ej obligatoriskt

[!include [banner](../includes/banner.md)]

Denna artikel innehåller en beskrivning av hur en artikel som har webbplatsen som disponeringsdimension planeras.

Det här huvudplaneringsscenariot omfattar följande villkor:

-   Dimensionen på en site är obligatorisk och måste anges på efterfrågetransaktionen.
-   Lagerdimensionen har inte angetts vara obligatorisk. Lagret kan vara känt, men det används inte vid beräkningen av huvudplaneringen.
-   Sitedimensionen är aktiverad för disponeringsplanering.
-   Lagerställedimensionen är inte aktiverad för disponeringsplanering. Därför sammanställs tillgång och efterfrågan per site, och eventuellt, andra disponeringsplanerade dimensioner.

Följande figur illustrerar hur huvudplaneringen fortskrider. Parametrarna som refereras i bilden och deras siter är som följer:
-   Disponeringsplanering har definierats för artikeln. Klicka på **Hantering av produktinformation &gt; Produkter&gt; Frisläppta produkter**. Markera artikeln och klicka sedan på **Plan &gt; Artikeldisponering**.
-   Påfyllningsrelationer har definierats för lagret. Klick på **Lagerhantering &gt; Inställningar &gt; Lagerindelning &gt; Lagerställen**. Gå till fliken **Huvudplanering** och leta reda på fältgruppen **Huvudlagerställe**.
-   Standardordertypen anges som Produktion, Inköpsorder eller Kanban. Klicka på **Hantering av produktinformation &gt; Produkter&gt; Frisläppta produkter**. Välj artikeln och klicka sedan på **Plan &gt; Standardorderinställningar**. I formuläret **Standardorderinställningar**, se fältet **Standardordertyp** .

![Efterfrågan för täckning av plats, lagerställe ej obligatorisk.](./media/multisitedemandexplosionscenarioforsitecoveragewarehousenotmandatory.jpg)



## <a name="additional-resources"></a>Ytterligare resurser

[Huvudplanering och multisitefunktioner – översikt](master-plan-multisite-functionality.md)

[Huvudplanering för plats och lagerställe, lagerställe obligatoriskt](master-plan-site-coverage-warehouse-mandatory.md)

[Huvudplanering för täckning av plats, lagerställe obligatoriskt](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[Huvudplanering för täckning av plats, lagerställe inte obligatoriskt](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[Avgör strukturlisteversion](master-plan-bom-version-determined.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]