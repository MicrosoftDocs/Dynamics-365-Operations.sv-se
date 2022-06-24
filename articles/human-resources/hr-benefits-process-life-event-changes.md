---
title: Bearbeta ändringar av livshändelser
description: I denna artikel beskrivs hur du bearbetar ändringar av livshändelser i Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart, BenefitLifeEventTypes, BenefitEligibilityProcessResultViewer
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 38b36f2165c9794091321c193f10dd37cc92b866
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8858197"
---
# <a name="process-life-event-changes"></a>Bearbeta ändringar av livshändelser


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Bearbeta ändring av livshändelse i Microsoft Dynamics 365 Human Resources för två ändringar i livshändelser:

- Födelsedagsändringar
- Ändringar av berättiganderegelns giltighet 

1. I arbetsytan **Förmånshantering** under **bearbetar**, välj **bearbeta ändringar i livshändelser**.

2. I dialogrutan **Kör ändringsprocess för livshändelse** ange värden för följande fält:

   | Fält | Beskrivning |
   | --- | --- |
   | Anmälningsperiod | Anmälningsperiod för bearbeta ändring av livshändelse. |
   | Juridisk person | Juridisk person för bearbeta ändring av livshändelse. |

3. Om du vill köra processen i bakgrunden väljer du **Kör i bakgrunden** och utför följande uppgifter:

   1. Ange information för processen.

   2. Om du vill ställa in ett återkommande jobb väljer du **återkommande**, anger upprepningsinformationen och klickar på **OK**.

   3. Ställ in en jobbsignal genom att välja **notifieringar**, välja de notifieringar som ska tas emot och sedan välja **OK**.

   4. Välj **OK**. Processen kommer att köras med de parametrar du angett.

4. Välj **OK**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
