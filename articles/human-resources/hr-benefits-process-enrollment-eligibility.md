---
title: Bearbetning av berättigande för anmälan
description: I den här artikeln beskrivs hur du kör bearbetning av berättigande för anmälan.
author: andreabichsel
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f9b1febe2690fab17586033994b10ebf260630af
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5805716"
---
# <a name="process-enrollment-eligibility"></a>Bearbetning av berättigande för anmälan

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

I den här artikeln beskrivs hur du kör bearbetning av berättigande för anmälan.

1. I arbetsytan **Förmånshantering** under **bearbetar**, välj **Bearbetning av berättigande för anmälan**.

2. I dialogrutan **Kör bearbetning av berättigande för förmånsanmälan** ange värden för följande fält:

   | Fält | Beskrivning |
   | --- | --- |
   | **Anmälningsperiod** | Anmälningsperiod för att bearbeta av berättigande för anmälan. |
   | **Juridisk person** | Juridisk person att bearbeta berättigande för anmälan för. |
   | **Arbetare** | Arbetare att bearbeta berättigande för anmälan för. Om du lämnar det här fältet tomt bearbetas en berättigande för anmälan för alla arbetare. |
   | **Förmånsplan** | Förmånsplan att bearbeta berättigande för anmälan för.

3. Om du vill köra processen i bakgrunden väljer du **Kör i bakgrunden** och utför följande uppgifter:

   1. Ange information för processen.

   2. Om du vill ställa in ett återkommande jobb väljer du **återkommande**, anger upprepningsinformationen och klickar på **OK**.

   3. Ställ in en jobbsignal genom att välja **notifieringar**, välja de notifieringar som ska tas emot och sedan välja **OK**.

   4. Välj **OK**. Processen kommer att köras med de parametrar du angett.

4. Välj **OK**.

## <a name="view-process-results"></a>Visa processresultat

I den här artikeln beskrivs hur du visar berättigande processresultat.

1.  I arbetsytan **Förmånshantering** under **bearbetar**, välj **processresultat**.

2.  I formuläret **processresultat** anges följande fält:

   | Fält | beskrivning |
   | --- | --- |
   | **Process-ID** | Unikt ID för kombinationen av arbetare, juridisk person och processkörning. |
   | **Processtyp** | Detta anger vilken process som kördes. Till exempel: Anmälan. |
   | **Tidstämpel** | Den tidpunkt då berättigandeprocessen kördes. |
   | **Juridisk person** | Den juridiska person som anges under anmälningsprocessen. |
   | **Arbetare** | Arbetaren som bearbetades. |
   | **Plan | Den förmånsplan som anmälan gjordes för. |
   | **Berättiganderegel** | Den berättiganderegel som bearbetades. Om ett fel påträffades innan berättigandet kördes är detta tomt. Exempel: om kompensationen inte har definierats för en arbetare körs inte berättigandeprocessen och detta fält lämnas tomt. |
   | **Resultatstatus** | Detta är berättigat eller inte berättigat. Resultatstatusen är inte giltig om medarbetaren inte uppfyller villkoren för berättiganderegler, om personen saknar nödvändig information, t.ex. lönefrekvens eller en fast kompensation, eller om det saknas information om förmånsplanen som förhindrar att arbetare registreras. |
   | **Resultatmeddelande** | Anger varför en arbetare är berättigad till en förmånsplan eller om berättiganderegler har överförts. |



[!INCLUDE[footer-include](../includes/footer-banner.md)]