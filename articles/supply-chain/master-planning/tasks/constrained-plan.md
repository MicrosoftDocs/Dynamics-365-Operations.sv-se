--- 
title: "Generera en begränsad plan"
description: "I den här proceduren visas hur du skapar en plan som tar hänsyn till både material- och kapacitetsbegränsningar."
author: YuyuScheller
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 59c6a4a2b239b3fd6b6ddc8f06bfd007f0191f0a
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="generate-a-constrained-plan"></a>Generera en begränsad plan

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

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


