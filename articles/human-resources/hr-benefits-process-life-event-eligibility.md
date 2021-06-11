---
title: Bearbetning av berättigande för livshändelse
description: I den här artikeln beskrivs hur du kör bearbetning av berättigande för livshändelse.
author: andreabichsel
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart, BenefitLifeEventTypes, BenefitEligibilityProcessResultViewer
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 20b458e67b6504ca1c3efce6b40d1cea4faa7193
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/18/2021
ms.locfileid: "6058522"
---
# <a name="process-life-event-eligibility"></a>Bearbetning av berättigande för livshändelse

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

I den här artikeln beskrivs hur du kör bearbetning av berättigande för livshändelse.

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