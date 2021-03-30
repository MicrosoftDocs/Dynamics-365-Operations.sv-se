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
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 12137c0d82109a8b757df6f6990922994d49c71a
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5208665"
---
# <a name="process-and-trace-source-data"></a>Bearbeta och spåra källdata

[!include [banner](../../includes/banner.md)]

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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]