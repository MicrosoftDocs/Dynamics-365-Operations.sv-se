---
title: Bearbeta ändringar av sats
description: I detta ämne förklaras hur du bearbetar ändringar av förmånspriset i Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart, BenefitRate, BenefitEligibilityProcessResultViewer
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: c1eea61df6dd5fbe0b52a21944deba69928b5125
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/04/2022
ms.locfileid: "8696138"
---
# <a name="process-rate-changes"></a>Bearbeta ändringar av sats


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Detta ämne förkalrar hur du bearbetar ändringar i förmånspris i Microsoft Dynamics 365 Human Resources när en ny eller befintlig förmånsplan får en ändring i inställningarna för berättiganderegler. Om en ny berättiganderegel skapas och tilldelas till planen uppmanas systemet att köra om medarbetarens berättigande för att kontrollera om medarbetaren kan bli berättigade till planen baserat på nya berättigandealternativ. 

1. I arbetsytan **Förmånshantering** under **bearbetar**, välj **bearbeta uppdateringar i prisändringar**.

2. I dialogrutan **Kör uppdateringsprocess av förmånspris** ange värden för följande fält:

   | Fält | Beskrivning |
   | --- | --- |
   | **Anmälningsperiod** | Anmälningsperiod för bearbeta prisändring. |

3. Om du vill köra processen i bakgrunden väljer du **Kör i bakgrunden** och utför följande uppgifter:

   1. Ange information för processen.

   2. Om du vill ställa in ett återkommande jobb väljer du **återkommande**, anger upprepningsinformationen och klickar på **OK**.

   3. Ställ in en jobbsignal genom att välja **notifieringar**, välja de notifieringar som ska tas emot och sedan välja **OK**.

   4. Välj **OK**. Processen kommer att köras med de parametrar du angett.

4. Välj **OK**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
