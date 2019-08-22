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
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b923b215528ecceaed9b5057ddb736ec959f1d65
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2019
ms.locfileid: "1845124"
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

