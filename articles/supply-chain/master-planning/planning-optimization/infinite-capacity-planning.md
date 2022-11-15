---
title: Tidsplanering med obegränsad kapacitet
description: Denna artikel innehåller information om planläggning av obegränsad kapacitet. Det beskriver även aktuella funktionsbegränsningar.
author: t-benebo
ms.date: 08/09/2022
ms.topic: article
ms.search.form: RouteInventProd
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-06-09
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 7249734e5d2644145a36276dbc818a40b5962805
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2022
ms.locfileid: "9740016"
---
# <a name="scheduling-with-infinite-capacity"></a>Tidsplanering med obegränsad kapacitet

[!include [banner](../../includes/banner.md)]

Med funktionen *Oändlig kapacitetsplanering för Planeringsoptimering* introduceras tidsplanering som baseras på flödesinformation. Med den kan du tidsplanera jobb utifrån ett stort antal flödeskonfigurationer. Tidsplanering omfattar ofta använda flödesinställningar, inklusive flödesdriftsordning eller krav för flödesdriftsresurser.

## <a name="turn-the-infinite-capacity-scheduling-feature-on-or-off"></a>Aktivera eller inaktivera funktionen för tidsplanering av obegränsad kapacitet

Innan du kan använda funktionen måste den aktiveras i ditt system. Från och med version 10.0.29 av Supply Chain Management är denna funktion aktiverad som standard. Administratörer kan aktivera eller inaktivera den här funktionen genom att söka efter funktionen *Planering av oändlig kapacitet för Planeringsoptimering* i arbetsytan [Funktionshantering](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

Mer information om den här funktionen finns i [Tidsplanering med resursurval som baseras på kapaciteten](capability-based-scheduling.md).

## <a name="added-functionality"></a>Tillagda funktioner

Med funktionen *Oändlig kapacitetsplanering för Planeringsoptimering* möjliggörs introduceras tidsplanering för jobb som baseras på flödesinformation. Därför kan en flödeskonfiguration användas för att tidsplanera produktionsprocesser. Även om denna funktion har vissa begränsningar som den inaktuella huvudplaneringsmotorn inte har, så har den stöd för de vanligaste funktionerna som krävs för tillverkningsscenarier.

Funktionen tar hänsyn till både *enkla flöden* och *flödesnätverk*. Genom att använda fältet **Nästa** i en flödesåtgärd kan du konfigurera komplexa flöden som har flera startpunkter och flera åtgärder som körs parallellt. I systemet kommer komplexa flödesstrukturer av den här typen att beaktas under tidsplaneringen.

Dessutom stöder funktionen *parallella åtgärder* i flöden. Genom att använda alternativen *Primär* och *Sekundär* i fältet **Prioritet** i flödesåtgärder kan du definiera en flödesstruktur där en flödesåtgärd är den primära åtgärden och en annan är sekundär. I detta fall kommer systemet att beakta flödesstrukturen i samband med tidsplaneringen.

Under tidsplaneringsprocessen tar systemet även hänsyn till de *resursbehov* som har angetts för en åtgärd. Systemet använder resursbehov för att avgöra vilka resurser som krävs för att utföra åtgärden. Funktionen *Oändlig kapacitetsplanering för Planeringsoptimering* stöder för närvarande följande typer av resursbehov:

- Resurstyp
- Resurs
- Resursgrupp
- Kapacitet (För mer information, se [Tidsplanering med resursurval som baseras på kapaciteten](capability-based-scheduling.md).)

> [!NOTE]
>
> - Om resursen och/eller resursgruppen är inställda på obegränsad kapacitet kommer dessa att betrakta som obegränsad kapacitet i huvudplaneringen.
> - Krav som rör personal, som kompetenser eller certifikatkrav, stöds ännu inte.

Funktionen stöder även åtgärdsegenskaper för **Inställning av tid** och **Körningstid**. När du anger dessa egenskaper för en flödesåtgärd skapar tidsplaneringsprocessen lämpliga inställnings- och processjobb.

Sammanfattningsvis stöder tidsplaneringen de vanligast använda scenarierna. Du kan skapa flödet, lägga till primära och sekundära åtgärder, definiera kommande åtgärder, lägga till resursbehov och lägga till konfigurationstid och körningstid. Systemet beaktar sedan denna information under tidsplaneringen.

## <a name="limitations"></a>Begränsningar

Följande begränsningar gäller när du använder funktionen *Planering av oändlig kapacitet för Planeringsoptimering*:

- Funktionen har bara stöd för obegränsad kapacitet.
- Funktionen stöder inte funktionen för resursbelastning.
- Funktionen tar inte hänsyn till flödeskassation.
- Funktionen stöder endast *Varaktighet* som primärt resursval.
