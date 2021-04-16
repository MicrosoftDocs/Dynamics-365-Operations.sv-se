---
title: Generera en begränsad plan
description: I det här avsnittet visas hur du skapar en plan som tar hänsyn till både material- och kapacitetsbegränsningar.
author: ShylaThompson
ms.date: 08/02/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, ReqPlanSched
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c35d5a7465cc6cfe0bc12cb00796eff2aeed1ece
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5808026"
---
# <a name="generate-a-constrained-plan"></a>Generera en begränsad plan

[!include [banner](../../includes/banner.md)]

I det här avsnittet visas hur du skapar en plan som tar hänsyn till både material- och kapacitetsbegränsningar. Planen garanterar att produktionen inte startas innan det finns tillgängligt material och resurserna inte är överbokade. 

Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF. Den här proceduren är avsedd för produktionsplaneraren.


## <a name="set-up-a-constrained-plan"></a>Ställ in en begränsad plan
1. På startsidan väljer du arbetsytan **Huvudplanering**.
2. Välj **Huvudplaner** i listan med länkar längst till höger på arbetsytan.
3. Hitta och markera önskad post i listan. Exempel: **StaticPlan**  
4. Välj **Ja** i fältet **Begränsad kapacitet**.
5. Ange `30` i fältet **Tidsgräns för begränsad kapacitet**.
6. Expandera avsnittet **Tidsgräns i dagar**.
7. Välj **Ja** i fältet **Kapacitet**.
8. Ange en siffra i fältet **Tidsgräns för kapacitetsplanering (dagar)**. Exempel: `60`  
9. Välj **Ja** i fältet **Beräknade fördröjningar**.
10. Ange en siffra i fältet **Beräkna fördröjningstidsgräns (dagar)**. Exempel: `60` 
11. Expandera avsnittet **Beräknade fördröjningar**.
12. Välj **Ja** i alla fält **Lägg till den beräknade fördröjningen för behovsdatumet**.
13. Stäng sidan.

## <a name="create-a-constrained-plan"></a>Skapa en begränsad plan
1. Välj **kör**.
2. Ange eller välj den plan som du har ställt in begränsningar för i fältet **Huvudplan** .  
3. Välj **OK**.
4. Välj **Planerade order**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]