---
title: Arbetsyta för förmånshantering
description: I detta avsnitt beskrivs funktionen arbetsyta för förmånshantering i Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 02/24/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-24
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 49393ab65c2f0020af5b246f7c18a152d613725f5b31be89cb57f244b28003f3
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6719102"
---
# <a name="benefits-management-workspace"></a>Arbetsyta för förmånshantering

[!include [applies to](../includes/applies-to-hr.md)]

[!include [preview feature](./includes/preview-feature.md)]

I detta avsnitt beskrivs funktionen arbetsyta för **förmånshantering** i Dynamics 365 Human Resources.

> [!NOTE]
> Om du vill visa arbetsytan **förmånshantering** måste du först aktivera funktionen för **(förhandsgranska) förmånshantering** i funktionshantering. Mer information om hur du aktiverar förhandsfunktioner finns i [Hantera funktioner](hr-admin-manage-features.md).<br><br>![Aktivera arbetsyta för hantering av förmåner.](./media/hr-benefits-management-workspace-enable.png)

Arbetsytan **förmånshantering** ger dig en snabb översikt över fördelar som kräver din uppmärksamhet. På denna sida kan du se:

- Summor för artiklar som väntar på åtgärd
- Arbetare med obekräftade val
- Arbetare som nyligen registrerade sig till förmåner
- Arbetare med framtida livshändelser
- Nyanställningar som inte är registrerade
- Arbetare med aktiva livshändelser
- Arbetare med öppna anmälningar som inte har valt några planer

![Arbetsyta för förmånshantering.](./media/hr-benefits-management-workspace.png)

## <a name="view-action-items"></a>Visa åtgärdsobjekt

Du kan visa åtgärdsobjekten genom att välja en panel eller en flik. Om du väljer en flik kan du visa och välja arbetare direkt på arbetsytan.

![Åtgärdsobjekt.](./media/hr-benefits-management-workspace-action-items.png)

Om du väljer en panel går du till sidan för det området. Om du till exempel väljer någon av dessa visas sidan **Arbetares förmånsplaner** filtrerat för medarbetare som du behöver vidta åtgärder för:

- **Obekräftade val**
- **Öppna registreringar utan utcheckade planer**
- **Registrerad för förmåner**
- **Nyanställd som inte registrerats**

![Förmånsplaner för medarbetare.](./media/hr-benefits-management-workspace-plans.png)

Om du väljer panelen **Aktiva livshändelser** eller **Framtida livshändelser** kommer du till en lista över aktiva eller framtida händelser.

![Livshändelser.](./media/hr-benefits-management-workspace-life-events.png)

## <a name="processing"></a>Bearbetas

När du vill bearbeta anmälan, livscykelhändelser eller kursändringsuppdateringar markerar du lämpligt objekt i navigeringsfältet.

![Bearbetas.](./media/hr-benefits-management-workspace-processing.png)

Om du vill visa processresultaten, välj **Processresultat** på sidan.

![Processresultat.](./media/hr-benefits-management-workspace-process-results.png)

Mer information om förmånsbearbetning finns i:.

- [Bearbeta anmälningsberättigande](hr-benefits-process-enrollment-eligibility.md)
- [Bearbeta ändringar av livshändelser](hr-benefits-process-life-event-changes.md)
- [Bearbeta livshändelseberättigande](hr-benefits-process-life-event-eligibility.md)
- [Bearbeta livshändelser](hr-benefits-process-life-events.md)
- [Bearbeta ändringar av sats](hr-benefits-process-rate-changes.md)

## <a name="change-period"></a>Ändringsperiod

Om du vill visa en annan förmånsperiod väljer du den från listrutan **Period**.

![Ändringsperiod.](./media/hr-benefits-management-workspace-period.png)

## <a name="view-more-options"></a>Visa fler alternativ

Om du vill visa mer information och åtgärder som du kan vidta väljer du **Länkar**.

![Länkar.](./media/hr-benefits-management-workspace-links.png)

## <a name="see-also"></a>Se även

[Hantering av förmåner – översikt](hr-benefits-management-overview.md)