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
ms.openlocfilehash: 973236acca0cb8c0d57171e4bb9d4daaa7faaf38
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "3141210"
---
# <a name="configure-and-run-job-to-calculate-statements"></a>Konfigurera och köra jobb för att beräkna utdrag

[!include [banner](../includes/banner.md)]

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
