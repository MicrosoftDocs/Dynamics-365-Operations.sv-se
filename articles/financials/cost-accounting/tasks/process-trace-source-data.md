---
title: Bearbeta och spåra källdata
description: All databearbetning körs med jobb.
author: ShylaThompson
manager: AnnBe
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e476416420875ba0f2401cf251d34977ae84b8f5
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "322615"
---
# <a name="process-and-trace-source-data"></a>Bearbeta och spåra källdata

[!include [task guide banner](../../includes/task-guide-banner.md)]

All databearbetning körs med jobb. För varje jobb och dataprovider skapas en journal för att dokumentera processen som körs, och att transaktionerna har bearbetats i det aktuella jobbet. Använd den här proceduren för att skapa en datakälla och sedan spåra ursprunget till en viss kostnadstransaktion. I den här inspelningen används demonstrationsföretaget USP2. Innan du utför den här uppgiften måste du spela upp följande uppgiftsguider: "Skapa en huvudbok för kostnadsredovisning", "Definiera kostnadsstyrenheter" och "Hantera datakälla för huvudbok för kostnadsredovisning".

1. Gå till Kostnadsredovisning > Redovisningsinställningar > Huvudböcker för kostnadsredovisning.
2. Hitta och markera önskad post i listan.
    * Välj den huvudbok för kostnadsredovisning som du skapade tidigare.  
3. Klicka på Faktiska versioner.
4. Klicka på Källdatabehandling i åtgärdsfönstret.
5. Klicka på Överföringsjournaler för redovisningsposter.
6. Hitta och markera önskad post i listan.
7. Klicka på Journalposter.
8. Markera vald rad i listan.
9. Klicka på Kostnadsposter.
10. Klicka på Källpost.
11. Klicka på Källdatabehandling i åtgärdsfönstret.
12. Klicka på Redovisning.
13. Ange eller välj ett värde i fältet Räkenskapskalenderperiod.
    * Välj Fiscal 2017 Period 9 i det här exemplet.  
14. Klicka på OK.

