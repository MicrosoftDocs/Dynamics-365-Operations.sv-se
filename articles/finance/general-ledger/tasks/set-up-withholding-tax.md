---
title: Ställ in källskatt
description: Det här avsnittet innehåller information om hur du ställer in källskatt.
author: twheeloc
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxWithholdTable, TaxWithholdData, TaxWithholdGroup
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 592afb7542fa44dcb1bf3f7354937d3c21fb1a87
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5813478"
---
# <a name="set-up-withholding-tax"></a>Ställ in källskatt

[!include [banner](../../includes/banner.md)]

Det här avsnittet innehåller information om hur du ställer in källskatt. *Källskatt* är en skatt på leverantörer som inte skapar momstransaktioner. Källskatt som beräknats på leverantörsbetalningar är en skuld. Därför är endast balansräkningskonton eller skuldkonton giltiga konton för bokföring av källskatt. Den här uppgifthandboken visar hur du ställer in källskatt.

1. Gå till **Navigeringsfönster > Moduler > Skatt > Indirekt moms > Källskatt > Källskattekoder**.
2. Välj **Ny**.
3. I fältet **Källskattekod** anger du ett värde.
4. Ange namnet på källskattekoden i fältet **Källskattenamn**.
5. Välj **huvudkontot** för bokföring av källskatteskulder i huvudkontofältet.
6. Välj **Spara**.
7. Välj **Värden** och markera önskad post i listan.
8. Ange en procentsats som används för beräkning av källskatten i fältet **Värde**.
9. Välj **Spara**.
10. Stäng sidan.
11. Välj **Spara**.
12. Stäng sidan.
13. Gå till **Navigeringsfönster > Moduler > Skatt > Indirekt moms > Källskatt > Källskattegrupper**.
14. Välj **Ny**.
15. Ange ID på källskattegruppen i fältet **Källskattegrupp**.
16. Ange namn på källskattegruppen i fältet **Beskrivning**.
17. Välj källskattekoden i fältet **Källskattekod**.
18. Välj **Spara**.
19. Stäng sidan.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]