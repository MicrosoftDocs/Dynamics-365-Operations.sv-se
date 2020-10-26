---
title: Generera en begränsad plan
description: I det här avsnittet visas hur du skapar en plan som tar hänsyn till både material- och kapacitetsbegränsningar.
author: ShylaThompson
manager: tfehr
ms.date: 08/02/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, ReqPlanSched
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d8b9d5712dd1b4f9958de775e1a2224b64485d05
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/10/2020
ms.locfileid: "3987224"
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

