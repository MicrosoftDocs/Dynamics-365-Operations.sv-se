---
title: Bearbetning av berättigande för anmälan
description: I den här artikeln beskrivs hur du kör bearbetning av berättigande för anmälan.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0344c48460a7d1540481e09ba106526e119de72b
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010545"
---
# <a name="process-enrollment-eligibility"></a>Bearbetning av berättigande för anmälan

[!include [banner](includes/preview-feature.md)]

I den här artikeln beskrivs hur du kör bearbetning av berättigande för anmälan.

1. I arbetsytan **Förmånshantering** under **bearbetar**, välj **Bearbetning av berättigande för anmälan**.

2. I dialogrutan **Kör bearbetning av berättigande för förmånsanmälan** ange värden för följande fält:

   | Fält | Beskrivning |
   | --- | --- |
   | Anmälningsperiod | Anmälningsperiod för att bearbeta av berättigande för anmälan. |
   | Juridisk person | Juridisk person att bearbeta berättigande för anmälan för. |
   | Arbetare | Arbetare att bearbeta berättigande för anmälan för. Om du lämnar det här fältet tomt bearbetas en berättigande för anmälan för alla arbetare. |
   | Förmånsplan | Förmånsplan att bearbeta berättigande för anmälan för.

3. Om du vill köra processen i bakgrunden väljer du **Kör i bakgrunden** och utför följande uppgifter:

   1. Ange information för processen.

   2. Om du vill ställa in ett återkommande jobb väljer du **återkommande**, anger upprepningsinformationen och klickar på **OK**.

   3. Ställ in en jobbsignal genom att välja **notifieringar**, välja de notifieringar som ska tas emot och sedan välja **OK**.

   4. Välj **OK**. Processen kommer att köras med de parametrar du angett.

4. Välj **OK**.
