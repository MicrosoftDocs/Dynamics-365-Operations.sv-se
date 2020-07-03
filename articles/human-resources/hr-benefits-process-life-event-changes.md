---
title: Bearbeta ändring av livshändelse
description: Bearbeta ändring av livshändelse i Microsoft Dynamics 365 Human Resources för ändringar i livshändelser.
author: andreabichsel
manager: AnnBe
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
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
ms.openlocfilehash: 11809bcf631316a064a3c917926f486ff22cb35a
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2020
ms.locfileid: "3429138"
---
# <a name="process-life-event-changes"></a>Bearbeta ändring av livshändelse

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
