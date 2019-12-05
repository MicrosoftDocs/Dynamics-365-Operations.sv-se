---
title: Rådgivning om optimering – översikt
description: Det här avsnittet innehåller en översikt över funktionen för rådgivning om optimering.
author: ChristianRytt
manager: AnnBe
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: aae9ea56fc2174df56274776993c68b11c0521d0
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/06/2019
ms.locfileid: "2774052"
---
[!include [banner](../../includes/banner.md)]
[!include [banner](../../includes/preview-banner.md)]

# <a name="planning-optimization-overview"></a>Rådgivning om optimering – översikt

Tillägget planerings optimering för Microsoft Dynamics 365 Supply Chain Management gör det möjligt att utföra en beräkning av huvudplanering utanför Dynamics 365 Supply Chain Management och den relaterade SQL-databasen. De fördelar som är kopplade till funktionerna för planeringsoptimering omfattar förbättrad prestanda och minimal inverkan på SQL-databasen under huvudplaneringskörningen. Snabba planeringskörningar kan göras även under kontorstid, så att planerare omedelbart kan reagera på efterfrågan eller parameterändringar.

Om du vill använda planeringsoptimering måste du installera tillägget planeringsoptimering från ditt projekt i Microsoft Dynamics Lifecycle Services (LCS) och aktivera planeringsoptimeringsfunktionen i Supply Chain Management. Mer information finns i [komma igång med planeringsoptimering](get-started.md).

Följande illustration visar fördelen med att använda planeringsoptimering under kontorstid.

![Fördelar med att använda planeringsoptimering under kontorstid](media/PlanningOptimization1.png)

## <a name="improved-performance"></a>Förbättrad prestanda

Planeringsoptimering kan användas i scenarier som innefattar huvudplaner som körs länge. Den är särskilt utformad för mycket snabba beräkningar som innebär mycket stora datavolymer. Eftersom den är byggd som en hyperskalbar tjänst för flera innehavare kan flera instanser samarbeta samtidigt för att beräkna planen. Dessutom tar planeringstjänsten bort belastningen på huvudplaneringen från systemet och fungerar med en dataström som minimerar serverbelastningen.

Planeringsoptimeringen hjälper dig att uppnå följande mål:

- Förbättra planeringsprestandan genom en kortare körningstid.
- Minska påverkan på andra processer under körningen av huvudplaneringen.
- Utför mer frekventa planeringskörningar. (Du är inte begränsad till daglig körning.)
- Var säker på att framtida affärstillväxt inte överbelastar planeringssystemet.

## <a name="architecture-and-data-flow"></a>Arkitektur och dataflöde

När tillägget för planeringsoptimering installeras från LCS, upprättas en säker anslutning till planeringsoptimeringstjänsten. Tjänsten finns i samma datacenterland eller -region som den relaterade instansen för Supply Chain Management. När planeringsoptimeringen har ställts in, när huvudplaneringen körs, skickas huvuddata och transaktionsdata från Supply Chain Management till planeringsoptimeringstjänsten.

Om tillägget för planeringsoptimering avinstalleras tas alla relaterade data i planeringsoptimeringstjänsten bort.

### <a name="high-level-data-flow-for-regeneration-runs"></a>Dataflöde på hög nivå för återskapande körs

1. Klienten för Supply Chain Management skickar en signal för att begära en planeringskörning från planeringsoptimering.
2. Planeringsoptimering begär nödvändiga data via den integrerade anslutaren.
3. SQL-databasen skickar den begärda informationen om installations-, huvud- och transaktionsdata för planeringsoptimering via anslutningen. Anslutningen översätter information mellan Supply Chain Management och planeringsoptimeringstjänsten.
4. Planeringsoptimeringstjänsten innehåller planeringsrelaterade data i minnet och de beräkningar som krävs.
5. Planeringsresultatet skickas till Supply Chain Management-databasen via anslutaren. Resultaten innehåller information som t.ex. planerade order och pegging-information. Planeringsoptimering skickar en signal till Supply Chain Management som visar att planeringskörningen har slutförts. Alla relevanta meddelanden och varningar skickas också.

Illustrationen som följer visar dataflöde.

![Dataflöde för återskapande körs](media/PlanningOptimization2.png)

## <a name="related-resources"></a>Relaterade resurser

[Kom igång med planeringsoptimering](get-started.md)

[Planera analys av optimeringsanpassning](planning-optimization-fit-analysis.md)

[Visa planhistorik och planeringsloggar](plan-history-logs.md)

[Använda filter på en plan](plan-filters.md)

[Annullera ett planeringsjobb](cancel-planning-job.md)