---
title: Konfigurera och köra jobb för att beräkna utdrag
description: Den här proceduren går igenom konfigurationen och körning av regelbundet återkommande batchjobb om du vill skapa och beräkna utdrag för en vald butik eller grupp av butiker.
author: josaw1
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailChannelOperationsWorkspace, RetailOperatingUnitPicker, SysRecurrence
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f52603672e95d0ae4973844851c4ed260484e5f0
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1550172"
---
# <a name="configure-and-run-job-to-calculate-statements"></a>Konfigurera och köra jobb för att beräkna utdrag

[!include[task guide banner](../includes/task-guide-banner.md)]

Den här proceduren går igenom konfigurationen och körning av regelbundet återkommande batchjobb om du vill skapa och beräkna utdrag för en vald butik eller grupp av butiker. I proceduren används demonstrationsföretaget USRT.

1. Gå till alla arbetsytor > butiksekonomi.
2. Klicka på Beräkna utdrag.
    * Välj antingen en specifik butik eller en nod om du vill skapa batchjobbet för en grupp av butiker.  
    * Klicka på pilen om du vill lägga till ditt val.  
3. Klicka på fliken Kör i bakgrunden ...
4. Välj Ja under Batchbearbetning.
5. Klicka på Upprepning.
6. Ange ett datum i fältet Startdatum.
7. Ange en tid i fältet Starttid.
8. Välj alternativet Slutdatum saknas.
9. Ange Dagar i fältet PatternUnit.
10. Ange ett tal i fältet Per.
11. Klicka på OK.
12. Klicka på OK.

