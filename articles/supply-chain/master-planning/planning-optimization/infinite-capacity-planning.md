---
title: Tidsplanering med obegränsad kapacitet
description: Denna artikel innehåller information om oändlig kapacitetsplanering för Planeringsoptimering. Det beskriver även aktuella funktionsbegränsningar.
author: t-benebo
ms.date: 09/21/2021
ms.topic: article
ms.search.form: RouteInventProd
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-06-09
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 3646a7ca1f9a3a87a2f130783dc4961a61335f1d
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8873881"
---
# <a name="scheduling-with-infinite-capacity"></a>Tidsplanering med obegränsad kapacitet

[!include [banner](../../includes/banner.md)]

Med funktionen *Oändlig kapacitetsplanering för Planeringsoptimering* introduceras tidsplanering som baseras på flödesinformation. Med den kan du tidsplanera jobb utifrån ett stort antal flödeskonfigurationer. Tidsplanering för Planeringsoptimering omfattar ofta använda flödesinställningar, inklusive flödesdriftsordning eller krav för flödesdriftsresurser.

## <a name="turn-on-the-infinite-capacity-scheduling-feature"></a>Aktivera funktionen för tidsplanering av obegränsad kapacitet

Innan du kan använda den här funktionen den aktiveras i ditt system. Administratörer kan använda inställningarna [funktionshantering](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den. I arbetsytan **utgiftshantering** anges den här funktionen på följande sätt:

- **Modul:** *huvudplanering*
- **Funktionsnamn:** *Planering med obegränsad kapacitet för Planeringsoptimering*

Mer information om den här funktionen finns i [Tidsplanering med resursurval som baseras på kapaciteten](capability-based-scheduling.md).

## <a name="added-functionality"></a>Tillagda funktioner

Med funktionen *Oändlig kapacitetsplanering för Planeringsoptimering* möjliggörs introduceras tidsplanering för jobb som baseras på flödesinformation. Därför kan en flödeskonfiguration användas för att tidsplanera produktionsprocesser. Även om denna funktion har vissa begränsningar som den inbyggda huvudplaneringen inte har, så har den stöd för de vanligaste funktionerna som krävs för tillverkningsscenarier.

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

Sammanfattningsvis stöder tidsplaneringen för Planeringsoptimering de vanligast använda scenarierna. Du kan skapa flödet, lägga till primära och sekundära åtgärder, definiera kommande åtgärder, lägga till resursbehov och lägga till konfigurationstid och körningstid. Systemet beaktar sedan denna information under tidsplaneringen.

## <a name="limitations"></a>Begränsningar

Följande begränsningar gäller när du använder tidsplanering för Planeringsoptimeringen:

- Funktionen har bara stöd för obegränsad kapacitet.
- Funktionen stöder inte funktionen för resursbelastning.
- Funktionen tar inte hänsyn till flödeskassation.
- Funktionen stöder endast *Varaktighet* som primärt resursval.

Observera att funktionen *Oändlig kapacitetsplanering för Planeringsoptimering* konstant förbättras. Microsoft förväntar sig att kunna införa stöd för ytterligare tidsplaneringsinställningar i framtida versioner.
