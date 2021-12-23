---
title: Budgetmedel är tillgängliga
description: Det här ämnet presenterar funktionen för tillgängliga budgetmedel och innehåller information som hjälper dig att konfigurera budgetkontroll för att optimera hanteringen av organisationens ekonomiska resurser.
author: rcarlson
ms.date: 11/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BudgetControlConfiguration
audience: Application User
ms.reviewer: roschlom
ms.custom:
- "60493"
- intro-internal
ms.assetid: be964167-43bc-431d-9adb-48bff32d68d5
ms.search.region: Global
ms.author: rcarlson
ms.search.validFrom: 2021-11-28
ms.dyn365.ops.version: AX 10.0.24
ms.openlocfilehash: a8279ae9b08c7537548c1c8b71e6e978fee2b8a1
ms.sourcegitcommit: c85eac17fbfbd311288b50664f9e2bae101c1fe6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/03/2021
ms.locfileid: "7891328"
---
# <a name="budget-funds-available"></a>Budgetmedel är tillgängliga

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Det här ämnet presenterar funktionen för tillgängliga budgetmedel och innehåller information som hjälper dig att konfigurera budgetkontroll för att optimera hanteringen av organisationens ekonomiska resurser.

## <a name="enhanced-calculation-feature-for-budget-funds-available"></a>Förbättrad beräkningsfunktion för tillgängliga budgetmedel

Med funktionen **Spåra endast belopp i beräkningen av tillgängliga budgetmedel** feature låter dig spåra de underliggande budgetkontrolltabellerna för dokumenttyper och tillstånd, baserat på inställningarna på **Definiera parametrar för budgetkontroll**.

Vissa konfigurationsalternativ för budgetkontroll måste ha specifika inställningar för att funktionen ska fungera korrekt. Dessa alternativ markeras eller avmarkeras på fliken **Tillgängliga budgetmedel** på sidan **Definiera parametrar för budgetkontroll**. Följande tabell visar de inställningar som krävs för funktionen Tillgängliga budgetmedel.

| Om detta alternativ är valt | Det här alternativet måste också väljas. |
| ------------------------- | -------------------------------- |
| Budgetreservationer för förinteckningar | Budgetreservationer för inteckningar *och* faktiska utgifter |
| Budgetreservationer för inteckningar | Faktiska omkostnader |
| Budgetreservationer för inteckningar med dokument av typen inköpsrekvisitioner | Budgetreservationer för förinteckningar |

Den här funktionen påverkar endast nya dokument. Belopp för befintliga dokument spåras även fortsättningsvis och visas i statistikförfrågan för budgetkontroll tills en inställning för tillgängliga budgetmedel ändras och den nya budgetkontrollkonfigurationen aktiveras. Då tas budgetspårningsdata bort för dokument som tagits bort från de tillgängliga budgetmedelsberäkningarna.

Vi rekommenderar att du låter alternativet **Ej bokförda faktiska utgifter** vara avmarkerat. Om den är markerad utförs en beräkning av en tidskrävande budgetkontroll på icke-bokförda dokument, till exempel väntande leverantörsfakturor.
