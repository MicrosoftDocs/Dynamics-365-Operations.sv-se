---
title: "Frisläpp tillverkningsorder"
description: "En frisläppt produktionsorder är en order som har auktoriserats för tillverkning. Termen frisläppt används för att beskriva ett tillstånd i produktionsorderlivscykeln, där produktionsordern är tillgänglig för körning i produktionsarbete och för lagerställeprocesser."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ProdParmRelease
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 2414
ms.assetid: 50c2257b-2924-44f5-b7c1-11f498092053
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: c4ebedab6d7de62479d3bc80583afadbe780aac4
ms.lasthandoff: 03/31/2017


---

# <a name="release-production-orders"></a>Frisläpp tillverkningsorder

En frisläppt produktionsorder är en order som har auktoriserats för tillverkning. Termen frisläppt används för att beskriva ett tillstånd i produktionsorderlivscykeln, där produktionsordern är tillgänglig för körning i produktionsarbete och för lagerställeprocesser. 

<a name="characteristics-of-the-released-state"></a>Egenskaper för det frisläppta tillståndet
-------------------------------------

**Frisläppt** tillstånd är ett tillstånd i produktionsorderns livscykel. Produktionsorder som är i **Frisläppt** tillstånd är tillgängliga för körning på produktionsarbete och lagerställeprocesser. **Frisläppt** tillstånd har följande egenskaper:

-   En produktionsorder kan ändras till **Frisläppt** tillstånd antingen från produktionsordern eller genom att använda en batchprocess. Produktionsordern kan också uppdateras automatiskt från planerade produktionsorder som bekräftas med hjälp av fältet **Bekräfta tidsgräns** på sidan **Huvudplan**.
-   **Frisläppt** tillstånd är signalen för fabriksoperatörerna att börja köra produktionsjobben i fabriken.
-   Produktionsdokument som t.ex. flödeskort, flödesjobb och jobbkort innehåller information om produktionsjobb och kan utfärdas.
-   För material som reserverats fysiskt genereras lagerställearbete för att plocka material för produktionsordern.

## <a name="releasing-jobs-to-the-shop-floor"></a>Frisläppning av jobb för fabriken
När en produktionsorder har frisläppts visas produktionsjobb som hör till ordern och är redo att registreras. Operatorerna kan göra jobbregistreringar, t ex Start och stopp skall antingen den **jobbet kortet terminal** sida eller **card-kortenheter jobbet** sida. Registrerad tid och kvantitet överförs automatiskt från registreringssidorna till produktionsjournaler för att hålla reda på förbrukad tid och kvantitet.

## <a name="route-cards"></a>Flödeskort
Ett flödeskort omfattar en översikt över informationen som kommer från flödet och operationsinställningarna samt från operations- och finplaneringsmetoderna.

## <a name="route-jobs"></a>Flödesjobb
Ett flödesjobb anger alla jobb i en operation i detalj och omfattar inställnings-, process-, kö- och transporttider. En operation som att måla kan till exempel kräva olika jobb som inställningstid, körtid för målningsprocessen och kötid för torkning.

## <a name="job-cards"></a>Jobbkort
Ett jobbkort anger de enskilda jobbnumren för en viss operation. Ett jobb visas på varje sida. De jobb som finns på ett jobbkort, och deras uppskattade tider, kommer från flödet och operationens inställningsinformation. Från ett jobbkort kan du öppna sidan **Produktionsjournalrader**, **jobbkort **. De som driver operationsresurser kan återrapportera om produktionsprocessen. Det finns fält där du kan ange förbrukningsstatistik och information som felkvantitet.

## <a name="warehouse-work-for-raw-material-picking"></a>Lagerställearbete för plockning av råmaterial.
Produkter för råvaraplockning genereras under leverans. Arbete genereras endast för mängden av material som fysiskt reserverats för tillverkningsordern innan ordern släpptes. Följande inställningar krävs för att generera arbete lagerstället för plockning råmaterial:

-   Ett platsdirektiv för plockning för råmaterial som bestämmer vilket lagerställen som materialet ska plockas i
-   En vågmall för råmaterial, där policyer för utförande av lagerställearbete konfigureras
-   En produktionsinleverans som bestämmer var materialet ska placeras


