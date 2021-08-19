---
title: Återställ kanban-jobbstatus
description: Den här proceduren är avsedd för att återställa en felaktig kanban-jobbstatus.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanBoardWorkCell, KanbanJobStatusUpdate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ef6d77aae52dc81bb1b34acc74d4174a7dfe0482f3af5123f93688244cf50f9f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6728541"
---
# <a name="revert-kanban-job-status"></a>Återställ kanban-jobbstatus

[!include [banner](../../includes/banner.md)]

Den här proceduren är avsedd för att återställa en felaktig kanban-jobbstatus. Detta är användbart om maskinoperatören uppdaterar fel jobb eller ställer in fel status av misstag. I den här proceduren registreras ett kanban-jobb som förberett av misstag och statusvärdet återställas. Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF. Den här proceduren är avsedd för den arbetsansvarige eller maskinoperatören som arbetar i ett lean manufacturing-företag.


## <a name="open-process-board-for-the-work-cell"></a>Öppna processtavlan för arbetsgruppen
1. Gå till Kanban-tavla för processjobb.
2. I fältet Arbetsgrupp, ange eller välj ett värde.
    * Välj arbetsgrupp 1260.  

## <a name="prepare-kanban-job"></a>Förbereda kanban-jobb
1. Klicka på Förbered.
    * Om du inte kan klicka på Förbered eftersom den gråas ut, se till att det valda kanban-jobbet har statusen Planerad som anges med en tom kanban-ikon. Om Förbered misslyckas, se till att allt material i plocklistan är tillgängligt.  
2. I listan, välj det förberedda jobbet.
    * Välj det första jobbet du precis har förberett.  
    * Observera att jobbstatusen förbereds, vilket anges med en triangel i kanban-ikonen.  

## <a name="revert-the-status-of-the-prepared-kanban-job"></a>Återställa statusen för det förberedda kanban-jobbet
1. Markera vald rad i listan.
    * Välj det första jobbet som har förberetts.  
2. I åtgärdsfönstret, klicka på Tillverka.
3. Klicka på Återställ status.
    * Du kan använda en alternativ kanban-regel när följande villkor är sant: återanskaffningsstrategin är densamma för båda reglerna.  - Den version av produktionsflödet är densamma för båda regler.  - Produkten som levereras är densamma för båda regler.  - Vissa nedströmsaktiviteter som konfigurerats för den senaste aktiviteten för kanban-reglerna måste vara samma för båda regler.  - Samma levererade lagerdimensioner måste ha konfigurerats för båda reglerna.  - Statusen för materialhanteringsenheten måste vara Inte tilldelat.  - Konfigurationen för händelse-kanbans måste vara samma.  
    * Kontrollera att den nya statusen är Planerat.  
4. Klicka på OK.
5. Avmarkera vald rad i listan.
    * Välj samma jobb.  
    * Observera att jobbstatusen för kanban-jobbet återställs till Planerat, vilket anges med en tom kanban-ikon.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]