---
title: Ställ in källskatt
description: Den här artikeln innehåller information om hur du ställer in källskatt.
author: twheeloc
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxWithholdTable, TaxWithholdData, TaxWithholdGroup
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0cc080df587904568796a9d6794987326be3ad26
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8907963"
---
# <a name="set-up-withholding-tax"></a>Ställ in källskatt

[!include [banner](../../includes/banner.md)]

Den här artikeln innehåller information om hur du ställer in källskatt. *Källskatt* är en skatt på leverantörer som inte skapar momstransaktioner. Källskatt som beräknats på leverantörsbetalningar är en skuld. Därför är endast balansräkningskonton eller skuldkonton giltiga konton för bokföring av källskatt. Den här uppgifthandboken visar hur du ställer in källskatt.

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