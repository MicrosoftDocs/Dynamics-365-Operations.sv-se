---
title: Bearbeta livshändelseberättigande
description: I detta ämne beskrivs hur du bearbetar ändringar av livshändelser.
author: twheeloc
ms.date: 08/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart, BenefitLifeEventTypes, BenefitEligibilityProcessResultViewer
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: b6cb4a8b815db561785ee56a0cd21376f1079cbd
ms.sourcegitcommit: 4f9c889e5cf72f34dd9746a322f8c0d6b983037b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/25/2021
ms.locfileid: "7417465"
---
# <a name="process-life-event-eligibility"></a>Bearbeta livshändelseberättigande

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

I detta ämne beskrivs hur du bearbetar tillgänglighet för livshändelser.

1. I arbetsytan **Förmånshantering** under **bearbetar**, välj **bearbetning av berättigande för livshändelse**.

2. I dialogrutan **Kör bearbetning av berättigande för livshändelse** ange värden för följande fält:

   | Fält | Beskrivning |
   | --- | --- |
   | **Anmälningsperiod** | Anmälningsperiod för bearbetning av berättigande för livshändelse. |

3. Om du vill köra processen i bakgrunden väljer du **Kör i bakgrunden** och utför följande uppgifter:

   1. Ange information för processen.

   2. Om du vill ställa in ett återkommande jobb väljer du **återkommande**, anger upprepningsinformationen och klickar på **OK**.

   3. Ställ in en jobbsignal genom att välja **notifieringar**, välja de notifieringar som ska tas emot och sedan välja **OK**.

   4. Välj **OK**. Processen kommer att köras med de parametrar du angett.

4. Välj **OK**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
