---
title: Generera en begränsad plan
description: I den här proceduren visas hur du skapar en plan som tar hänsyn till både material- och kapacitetsbegränsningar.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, ReqPlanSched
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0e2265f7788fd2a4a37f6fb96d7562649dbc5b1c
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1556033"
---
# <a name="generate-a-constrained-plan"></a>Generera en begränsad plan

[!include [task guide banner](../../includes/task-guide-banner.md)]

I den här proceduren visas hur du skapar en plan som tar hänsyn till både material- och kapacitetsbegränsningar. Planen garanterar att produktionen inte startas innan det finns tillgängligt material och resurserna inte är överbokade. 

Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF. Den här proceduren är avsedd för produktionsplaneraren.


## <a name="set-up-a-constrained-plan"></a>Ställ in en begränsad plan
1. Klcka på Huvudplanering.
2. Klcka på Huvudplaner.
3. Hitta och markera önskad post i listan.
    * Exempel: StaticPlan  
4. Välj Ja i fältet Begränsad kapacitet.
5. Ange "30 "i fältet Tidsgräns för begränsad kapacitet.
6. Expandera avsnittet Tidsgräns i dagar.
7. Välj Ja i fältet Kapacitet.
8. Ange ett tal i fältet Tidsgräns för kapacitetsplanering (dagar).
    * Exempel: 60  
9. Välj Ja i fältet Beräknade fördröjningar.
10. Ange ett tal i fältet Beräkna fördröjningstidsgräns (dagar).
    * Exempel: 60  
11. Expandera avsnittet Beräknade fördröjningar.
12. Välj Ja i fältet Lägg till den beräknade fördröjningen för behovsdatumet.
13. Välj Ja i fältet Lägg till den beräknade fördröjningen för behovsdatumet.
14. Välj Ja i fältet Lägg till den beräknade fördröjningen för behovsdatumet.
15. Stäng sidan.

## <a name="create-a-constrained-plan"></a>Skapa en begränsad plan
1. Klicka på Kör.
2. Ange eller välj ett värde i fältet Huvudplan.
    * Välj den plan som du har ställt in begränsningar för.  
3. Klicka på OK.
    * Detta kan ta ett tag.  
4. Klicka på Planerade order.

