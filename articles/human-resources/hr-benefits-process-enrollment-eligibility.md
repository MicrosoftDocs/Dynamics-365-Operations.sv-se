---
title: Bearbeta anmälningsberättigande
description: I detta ämne beskrivs hur du kör processen för bearbetning av registreringsberättigande.
author: twheeloc
ms.date: 08/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 78a7de6dbb8d8ed13392eb7eb9aa02b15db2e009
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/04/2022
ms.locfileid: "8693183"
---
# <a name="process-enrollment-eligibility"></a>Bearbeta anmälningsberättigande


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

I detta ämne beskrivs hur du kör processen för bearbetning av registreringsberättigande.

1. I arbetsytan **Förmånshantering** under **bearbetar**, välj **Bearbetning av berättigande för anmälan**.

2. I dialogrutan **Kör bearbetning av berättigande för förmånsanmälan** ange värden för följande fält:

   | Fält | Beskrivning |
   | --- | --- |
   | **Anmälningsperiod** | Anmälningsperiod för att bearbeta av berättigande för anmälan. |
   | **Juridisk person** | Juridisk person att bearbeta berättigande för anmälan för. |
   | **Arbetare** | Arbetare att bearbeta berättigande för anmälan för. Om du lämnar det här fältet tomt bearbetas en berättigande för anmälan för alla medarbetare. |
   | **Förmånsplan** | Förmånsplan att bearbeta berättigande för anmälan för.

3. Om du vill köra processen i bakgrunden väljer du **Kör i bakgrunden** och utför följande uppgifter:

   1. Ange information för processen.

   2. Om du vill ställa in ett återkommande jobb väljer du **återkommande**, anger upprepningsinformationen och klickar på **OK**.

   3. Ställ in en jobbsignal genom att välja **notifieringar**, välja de notifieringar som ska tas emot och sedan välja **OK**.

   4. Välj **OK**. Processen kommer att köras med de parametrar du angett.

4. Välj **OK**.

## <a name="view-process-results"></a>Visa processresultat

I detta ämne beskrivs hur du visar resultaten för berättigandeprocessen.

1.  I arbetsytan **Förmånshantering** under **bearbetar**, välj **processresultat**.

2.  På sidan **Processresultat** anges följande fält:

   | Fält | beskrivning |
   | --- | --- |
   | **Process-ID** | Unikt ID för kombinationen av medarbetare, juridisk person och processkörning. |
   | **Processtyp** | Detta anger vilken process som kördes. Till exempel: Anmälan. |
   | **Tidstämpel** | Den tidpunkt då berättigandeprocessen kördes. |
   | **Juridisk person** | Den juridiska person som anges under anmälningsprocessen. |
   | **Arbetare** | Arbetaren som bearbetades. |
   | **Plan | Den förmånsplan som anmälan gjordes för. |
   | **Berättiganderegel** | Den berättiganderegel som bearbetades. Om ett fel påträffades innan berättigandet kördes är detta tomt. Exempel: om kompensationen inte har definierats för en medarbetare körs inte berättigandeprocessen och detta fält lämnas tomt. |
   | **Resultatstatus** | Detta är berättigat eller inte berättigat. Resultatstatusen är inte giltig om medarbetaren inte uppfyller villkoren för berättiganderegler, om personen saknar nödvändig information, t.ex. lönefrekvens eller en fast kompensation, eller om det saknas information om förmånsplanen som förhindrar att medarbetare registreras. |
   | **Resultatmeddelande** | Anger varför en medarbetare är berättigad till en förmånsplan eller om berättiganderegler har överförts. |



[!INCLUDE[footer-include](../includes/footer-banner.md)]
