---
title: Tidsplanering med obegränsad kapacitet
description: Detta ämne innehåller information om oändlig kapacitetsplanering för planeringsoptimering. Det beskriver även aktuella funktionsbegränsningar.
author: crytt
ms.date: 6/9/2021
ms.topic: article
ms.search.form: RouteInventProd
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-06-09
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fc40dc2bcf1969e4c566b624a9425638e69ab2a17892f035aeabb74068aadd14
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6718982"
---
# <a name="scheduling-with-infinite-capacity"></a>Tidsplanering med obegränsad kapacitet

[!include [banner](../../includes/banner.md)]
[!INCLUDE [preview-banner](../../includes/preview-banner.md)]

Med funktionen *Oändlig kapacitetsplanering för planeringsoptimering* introduceras tidsplanering som baseras på flödesinformation. Med den kan du tidsplanera jobb utifrån ett stort antal flödeskonfigurationer. Tidsplanering för planeringsoptimering omfattar ofta använda flödesinställningar, inklusive flödesdriftsordning eller krav för flödesdriftsresurser.

## <a name="turn-on-the-infinite-capacity-scheduling-feature"></a>Aktivera funktionen för tidsplanering av obegränsad kapacitet

Om ditt system inte redan innehåller den funktion som beskrivs i det här avsnittet öppnar du arbetsytan [Funktionshantering](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) och aktiverar funktionen *Tidsplanering av obegränsad kapacitet för planeringsoptimering*.

## <a name="added-functionality"></a>Tillagda funktioner

Med funktionen *Oändlig kapacitetsplanering för planeringsoptimering* möjliggörs introduceras tidsplanering för jobb som baseras på flödesinformation. Därför kan en flödeskonfiguration användas för att tidsplanera produktionsprocesser. Även om denna funktion har vissa begränsningar som den inbyggda huvudplaneringen inte har, så har den stöd för de vanligaste funktionerna som krävs för tillverkningsscenarier.

Funktionen tar hänsyn till både *enkla flöden* och *flödesnätverk*. Genom att använda fältet **Nästa** i en flödesåtgärd kan du konfigurera komplexa flöden som har flera startpunkter och flera åtgärder som körs parallellt. I systemet kommer komplexa flödesstrukturer av den här typen att beaktas under tidsplaneringen.

Dessutom stöder funktionen *parallella åtgärder* i flöden. Genom att använda alternativen *Primär* och *Sekundär* i fältet **Prioritet** i flödesåtgärder kan du definiera en flödesstruktur där en flödesåtgärd är den primära åtgärden och en annan är sekundär. I detta fall kommer systemet att beakta flödesstrukturen i samband med tidsplaneringen.

Under tidsplaneringsprocessen tar systemet även hänsyn till de *resursbehov* som har angetts för en åtgärd. Systemet använder resursbehov för att avgöra vilka resurser som krävs för att utföra åtgärden. Funktionen *Oändlig kapacitetsplanering för planeringsoptimering* stöder för närvarande följande typer av resursbehov:

- Resurstyp
- Resurs
- Resursgrupp
- Funktion

> [!NOTE]
> Krav som rör personal, som kompetenser eller certifikatkrav, stöds ännu inte.

Funktionen stöder även åtgärdsegenskaper för **Inställning av tid** och **Körningstid**. När du anger dessa egenskaper för en flödesoperation skapar tidsplaneringsprocessen lämpliga inställnings- och processjobb.

Sammanfattningsvis stöder tidsplaneringen för planeringsoptimering de vanligast använda scenarierna. Du kan skapa flödet, lägga till primära och sekundära åtgärder, definiera kommande åtgärder, lägga till resursbehov och lägga till konfigurationstid och körningstid. Systemet beaktar sedan denna information under tidsplaneringen.

## <a name="limitations"></a>Begränsningar

Följande begränsningar gäller när du använder tidsplanering för planeringsoptimeringen:

- Funktionen stöder endast tidsplanering för jobb. Inställningar som är relaterade till grovplanering beaktas inte under tidsplaneringen, oavsett planeringsmetod i huvudplaner.
- Funktionen har bara stöd för obegränsad kapacitet.
- Funktionen stöder inte funktionen för resursbelastning.
- Funktionen tar inte hänsyn till flödeskassation.
- Funktionen stöder endast *Varaktighet* som primärt resursval.

Observera att funktionen *Oändlig kapacitetsplanering för Planeringsoptimering* konstant förbättras. Microsoft förväntar sig att kunna införa stöd för ytterligare tidsplaneringsinställningar i framtida versioner.
