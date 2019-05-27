---
title: Övervaka en huvudplaneringskörning
description: Produktionsplaneraren vill visa om en huvudplaneringskörning pågår.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, SysQueryForm, InventItemIdLookupSimple, ReqLog, ReqProcessTaskTrace
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7c2e158d8cbad1f5d4f377f6a8eb43487b34ffdc
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1565629"
---
# <a name="monitor-a-master-planning-run"></a>Övervaka en huvudplaneringskörning

[!include [task guide banner](../../includes/task-guide-banner.md)]

Produktionsplaneraren vill visa om en huvudplaneringskörning pågår. Använd demonstrationsdataföretaget USMF för att utföra den här proceduren.


## <a name="run-master-planning"></a>Kör Huvudplanering
1. Klcka på Huvudplanering.
    * Du hittar denna på standardinstrumentpanelen.  
2. I fältet Plan, ange eller välj ett värde.
    * Exempel: StaticPlan  
3. Klicka på Kör.
4. Välj Ja i fältet Spåra bearbetningstid.
    * Om detta fält är markerat hoppar du över detta steg.  
5. Ange ett nummer i fältet Antal trådar.
6. Expandera avsnittet Poster som ska ingå.
7. Klicka på Filter.
8. Markera vald rad i listan.
    * Markera raden där Fält = artikelnumret.  
9. Ange eller välj ett värde i fältet Kriterier.
    * Exempel: T0001  
10. Klicka på OK.
11. Klicka på OK.

## <a name="monitor-the-master-planning-run"></a>Övervaka en huvudplaneringskörning
1. Klicka på historik.
2. Klicka på Förfrågningar.
3. Klicka på Processuppgiftens tidslängd.
4. Hitta och markera önskad post i listan.
    * För varje artikel kan du få en översikt över hur länge det tog att använda alla planeringssteg.  

