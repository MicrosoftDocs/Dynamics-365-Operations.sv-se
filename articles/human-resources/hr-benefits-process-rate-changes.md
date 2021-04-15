---
title: Behandla prisändringar
description: Bearbeta förmånens prisändringar i Microsoft Dynamics 365 Human Resources när en ny eller befintlig förmånsplan har en ändring i inställningarna för berättiganderegler.
author: andreabichsel
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart, BenefitRate, BenefitEligibilityProcessResultViewer
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: c841f5d5d409c7e73cdc38988f8233747a11f837
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5803835"
---
# <a name="process-rate-changes"></a>Behandla prisändringar

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Bearbeta förmånens prisändringar i Microsoft Dynamics 365 Human Resources när en ny eller befintlig förmånsplan har en ändring i inställningarna för berättiganderegler. Om en ny berättiganderegel skapas och tilldelas till planen uppmanas systemet att köra om arbetarens berättigande för att kontrollera om medarbetaren kan bli berättigade till planen baserat på nya berättigandealternativ. 

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