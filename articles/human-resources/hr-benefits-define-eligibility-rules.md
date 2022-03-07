---
title: Definiera förmånsberättiganderegler och policyer
description: Detta ämne förklarar hur du kan skapa förmånsberättigande regler och policyer och sedan tilldela regler till förmåner.
author: twheeloc
ms.date: 08/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysPolicySourceDocumentRuleType, SysPolicyListPage, SysPolicy, HcmBenefitEligibilityPolicy, HcmBenefit, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Version 7.0.0, Human Resources
ms.openlocfilehash: c2595e40f6f9d1f75a94a3339735cc06bdabd14a
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/31/2022
ms.locfileid: "8067664"
---
# <a name="define-benefit-eligibility-rules-and-policies"></a>Definiera förmånsberättiganderegler och policyer


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Detta ämne förklarar hur du kan skapa förmånsberättigande regler och policyer och sedan tilldela regler till förmåner.  

## <a name="create-benefit-eligibility-policy-rule-type"></a>Skapa policyregeltypen för förmånsberättigande

1. Gå till **Personal > Förmåner > Berättigande > Regeltyper för förmånsberättigande policyer**.
2. Välj **Ny**.
3. I fältet **Regelnamn** anger du ett värde.
4. I fältet **Beskrivning** anger du ett värde.
5. I fältet **Frågenamn** väljer du listruteknappen för att öppna sökningen.
6. Klicka på länken på önskad rad i valda listan.
7. Välj **Spara**.
8. Stäng sidan.

## <a name="benefit-eligibility-policy"></a>Policy för förmånsberättigande

1. Gå till **Personal > Förmåner > Berättigande > Olicyer för förmånsberättigande**.
2. Välj en befintlig förmånspolicy.
3. Klicka på länken på önskad rad i valda listan.
4. Växla expandering av avsnitten **Policyorganisationer**. Du kan lägga till eller ta bort organisationer som du vill inkludera i policyn.
5. Expandera eller komprimera avsnittet **Policyregler**.
6. I listan söker du efter den policyregel som tidigare har skapats.
7. Välj **Skapa policyregel**.
8. I fältet **Giltighetsdatum** anger du datum då du vill att policyn ska träda i kraft.
    * Om du anger giltighetsdatum och slutdatum kan du göra framtida ändringar i policyregler, detta så att du inte behöver inte gå tillbaka till policyn när du vill att dessa ändringar ska börja gälla.  
9. Lägg vid behov till en where-klausul i fältet **Lägg till villkor**.
    * Om du till exempel vill att regeln bara ska gälla för säljchefer kan du skapa en Where-sats för att säga: "Där befattningsbeskrivningen är lika med säljchef". Du kan lägga till flera where-instruktioner i regeln.  
10. Välj **OK**.
11. Stäng sidan.

## <a name="assign-rule-to-benefit"></a>Tilldela regel till förmån

1. Gå till **Personal > Förmåner > Förmåner**.
2. Hitta och markera önskad post i listan.
3. Klicka på länken på önskad rad i valda listan.
4. Visa eller dölj avsnittet **Berättiganderegler**.
5. Välj **Redigera**.
6. I fältet **Berättigande** väljer du regeln.
7. I fältet **Regeltyp** väljer du den regel du tidigare skapat.
9. Klicka på länken på önskad rad i valda listan.
10. Välj **Spara**.
11. Stäng formuläret.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
