---
title: "Rapportera produktionsorder som färdiga"
description: "Rapportera som färdig är en produktionsfas. I detta skede rapporteras färdiga produkter och flyttas från produktionsordern till lagret."
author: johanhoffmann
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProdJournalTransJob, ProdJournalTransProd, ProdJournalTransRoute, ProdParmReportFinished, ProdRouteOprOverview
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 27061
ms.assetid: 1c2dfc54-a293-49f2-9b96-5a912ac5762c
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 52607d645c6eaf4ff97d2c4bf8abc6ec1374fd7e
ms.contentlocale: sv-se
ms.lasthandoff: 05/25/2017

---

# <a name="report-production-orders-as-finished"></a>Rapportera produktionsorder som färdiga

[!include[banner](../includes/banner.md)]


Rapportera som färdig är en produktionsfas. I detta skede rapporteras färdiga produkter och flyttas från produktionsordern till lagret.

När kvantiteten på de slutförda varorna rapporteras som färdig på en produktionsorder, uppdateras den som lagerbehållning. Delvisa kvantiteter av den ursprungligen planerade orderkvantiteten kan rapporteras som färdiga. Det går också att rapportera felkvantiteter med ett associerat fel när du rapporterar kvantiteter som färdiga. När produktionsordern når fasen Rapporterad som färdig innebär det att ingen mer kvantitet på tillverkningsordern ska rapporteras.
Följande egenskaper associeras också med processen **Rapportera som färdig**:
-   Det går att ställa in förbrukning av råmaterial och tid som är proportionerlig till den rapporterade kvantiteten (bakåtavräkning)
-   Inlagrat arbete kan skapas för artiklar som aktiveras för lagerställeprocesser.
-   Det planerade eller standardkostnadsvärdet för de färdiga varorna kan ställas in att rapporteras på huvudbokskonton.
-   En kvalitetsorder kan skapas för den rapporterade kvantiteten baserat på inställningarna för en kvalitetsassociation.

Kvantiteten rapporteras till utleveransplatsen. Lagerställearbete genereras sedan för att flytta kvantiteten från utleveransplatsen till dess slutmål som definieras av platsdirektivet för platsarbete.

-   En kvalitetsorder kan skapas när en produktionsorder rapporteras som färdig om en kvalitetsassociation har ställts in.

## <a name="set-a-production-order-to-reporting-as-finished"></a>Ställ in en produktionsorder till Rapportering som färdig
Du kan ställa in en produktionsorder som **Rapportera som färdig** genom uppdateringsfunktionen för produktionsorder eller via journalen **Rapportera som färdig**. Du kan även uppdatera fasen till **Rapportera som färdig** via sidorna för jobbkortterminal och jobbkortenhet när du rapporterar på det sista jobbet för produktionsordern. Slutligen kan du aktivera alternativet **Rapportera som färdig** som en process för lösningen för den handhållna lagerställeenheten.  



