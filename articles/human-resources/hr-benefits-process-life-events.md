---
title: Bearbeta livshändelse
description: Under medarbetarens livscykel i Microsoft Dynamics 365 Human Resources kan varje medarbetare stöta på olika ändringar av livshändelser.
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
ms.openlocfilehash: ef160af483f81b8c1e60a274029b77c3cd34f924
ms.sourcegitcommit: 66d129874635d34a8b29c57762ecf1564e4dc233
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/23/2022
ms.locfileid: "9324801"
---
# <a name="process-life-events"></a>Bearbeta livshändelse

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Under medarbetarens livscykel i Microsoft Dynamics 365 Human Resources kan varje medarbetare stöta på olika ändringar av livshändelser. Till exempel, äktenskap, nytt jobb eller beroendeändringar. Om du vill använda livshändelser måste du aktivera livshändelser på sidan **Förmånsparametrar**, ställa in livhändelsetyper samt ställa in livshändelsealternativ för plantyper.

Innan du kan bearbeta livshändelser måste du redan ha kört öppna registreringar minst en gång under en anställningstidsram. I USA är det vanligt att öppna anmälningen en gång per år. Utanför USA kan öppen registrering utföras vid anställningstiden. En arbetstagare behöver inte välja en förmånsplan för att livshändelser ska bearbetas, men de måste ha inkluderats i öppen registreringsbearbetning. 

Använd bearbetning av livhändelse när du har medarbetare med livhändelser som inträffar på ett framtida datum. Den här händelsen bearbetar alla livshändelser som inte har bearbetats (som framtida livshändelser eller livshändelser som inte är specifika för någon arbetstagare – ett exempel är en ny förmån). Livshändelser i realtid döljs.

Om till exempel dagens datum är 1 februari och den 14 februari är medarbetare Johan Svensson schemalagd att ändra juridiska personer, bearbetas alla livshändelser fram till 15 februari i systemet. 

1. I arbetsytan **Förmånshantering** under **bearbetar**, välj **bearbeta livshändelser**.

2. I dialogrutan **Kör process för livshändelse** ange värden för följande fält:

   | Fält | Beskrivning |
   | --- | --- |
   | **Anmälningsperiod** | Anmälningsperiod för bearbeta livshändelse. |
   | **Juridisk person** | Juridisk person för bearbeta livshändelse. |
   | **Datum för livshändelse** | Systemet bearbetar alla händelser under anmälningsperioden som inträffar fram till detta datum. |
   | **Arbetare** | Arbetare för bearbeta livshändelse. Om du lämnar det här fältet livshändelser bearbetas för alla medarbetare. |

3. Om du vill köra processen i bakgrunden väljer du **Kör i bakgrunden** och utför följande uppgifter:

   1. Ange information för processen.

   2. Om du vill ställa in ett återkommande jobb väljer du **återkommande**, anger upprepningsinformationen och klickar på **OK**.

   3. Ställ in en jobbsignal genom att välja **notifieringar**, välja de notifieringar som ska tas emot och sedan välja **OK**.

   4. Välj **OK**. Processen kommer att köras med de parametrar du angett.

4. Välj **OK**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
