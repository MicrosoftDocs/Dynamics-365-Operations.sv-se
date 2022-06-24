---
title: Bearbeta ändringar av sats
description: I denna artikel förklaras hur du bearbetar ändringar av förmånspriset i Microsoft Dynamics 365 Human Resources.
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
ms.openlocfilehash: 09714c70cb00b1a1b5dbd4613bbd70ff11d35cb2
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8882965"
---
# <a name="process-rate-changes"></a>Bearbeta ändringar av sats


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Detta ämne förklarar hur du bearbetar ändringar i förmånspris i Microsoft Dynamics 365 Human Resources när en ny eller befintlig förmånsplan får en ändring i inställningarna för berättiganderegler. Om en ny berättiganderegel skapas och tilldelas till planen uppmanas systemet att köra om medarbetarens berättigande för att kontrollera om medarbetaren kan bli berättigade till planen baserat på nya berättigandealternativ. 

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
