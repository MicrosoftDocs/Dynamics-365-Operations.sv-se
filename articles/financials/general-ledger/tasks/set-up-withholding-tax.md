---
title: Ställ in källskatt
description: Källskatt är en skatt på leverantörer som inte skapar momstransaktioner.
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxWithholdTable, TaxWithholdData, TaxWithholdGroup
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 382b6332665af2491563960a75d498a4f007aba8
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1562798"
---
# <a name="set-up-withholding-tax"></a>Ställ in källskatt

[!include [task guide banner](../../includes/task-guide-banner.md)]

Källskatt är en skatt på leverantörer som inte skapar momstransaktioner. Källskatt som beräknats på leverantörsbetalningar är en skuld. Därför är endast balansräkningskonton eller skuldkonton giltiga konton för bokföring av källskatt. Den här uppgifthandboken visar hur du ställer in källskatt.

1. Gå till Skatt > Indirekta skatter > Källskatt > Källskattekoder.
2. Klicka på Ny.
3. I fältet Källskattekod, skriv ett värde.
4. Ange namnet på källskattekoden i fältet Källskattenamn.
5. Välj huvudkontot för bokföring av källskatteskulder i huvudkontofältet.
6. Klicka på Spara.
7. Klicka på Värden.
8. Markera vald rad i listan.
9. Ange en procentsats som används för beräkning av källskatten i fältet Värde.
10. Klicka på Spara.
11. Stäng sidan.
12. Klicka på Spara.
13. Stäng sidan.
14. Gå till Skatt > Indirekta skatter > Källskatt > Källskattegrupper.
15. Klicka på Ny.
16. Ange ID på källskattegruppen i fältet Källskattegrupp.
17. Ange namn på källskattegruppen i fältet Beskrivning.
18. Markera vald rad i listan.
19. Välj källskattekoden i fältet Källskattekod.
20. Klicka på länken på den valda raden i listan.
21. Klicka på Spara.

