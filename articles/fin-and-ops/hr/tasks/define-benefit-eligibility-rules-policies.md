---
title: Definiera förmånsberättiganderegler och policyer
description: Den här registreringen visar hur du kan skapa förmånberättiganderegler och policyer och sedan tilldela regler till förmåner.
author: kherr75
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysPolicySourceDocumentRuleType, SysPolicyListPage, SysPolicy, HcmBenefitEligibilityPolicy, HcmBenefit
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d346c3277e8f19020d6aa96cf6961c4c52ac28fb
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "341682"
---
# <a name="define-benefit-eligibility-rules-and-policies"></a>Definiera förmånsberättiganderegler och policyer

[!include [task guide banner](../../includes/task-guide-banner.md)]

Den här registreringen visar hur du kan skapa förmånberättiganderegler och policyer och sedan tilldela regler till förmåner.  

Det demonstrationsdataföretag som används för att skapa den här registreringen är USMF.


## <a name="create-benefit-eligibility-policy-rule-type"></a>Skapa policyregeltypen för förmånsberättigande
1. Gå till Personal > Förmåner > Berättigande > Policyregeltyper för förmånsberättigande.
2. Klicka på Ny.
3. I fältet Regelnamn, skriv ett värde.
4. Ange ett värde i fältet Beskrivning.
5. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Frågenamn.
6. Klicka på länken på den valda raden i listan.
7. Klicka på Spara.
8. Stäng sidan.

## <a name="benefit-eligibility-policy"></a>Policy för förmånsberättigande
1. Gå till Personal > Förmåner > Berättigande > Policyer för förmånsberättigande.
2. Välj en befintlig förmånspolicy.
3. Klicka på länken på den valda raden i listan.
4. Växla expandering av policyorganisationsavsnitten.  Här kan du lägga till eller ta bort organisationer som du vill inkludera i policyn.
5. Expandera eller komprimera avsnittet Policyregler.
6. I listan söker du efter den policyregel som tidigare har skapats.
7. Klicka på Skapa policyregel.
8. Ange det datum då du vill att den nya policyn ska börja gälla i fältet Giltighetsdatum.
    * Om du anger giltighetsdatum och slutdatum kan du göra framtida ändringar i policyregler och behöver inte gå tillbaka till policyn när du vill att dessa ändringar ska börja gälla.  
9. 
    * Om du till exempel vill att regeln bara ska gälla för försäljningschefer kan du skapa en Where-sats för att säga: Där befattningen är lika med försäljningschef.  Du kan samla Och eller Eller för flera Where-utdrag i regeln.  
10. Klicka på OK.
11. Stäng sidan.
12. Stäng sidan.

## <a name="assign-rule-to-benefit"></a>Tilldela regel till förmån
1. Gå till Personal > Förmåner > Förmåner.
2. Hitta och markera önskad post i listan.
3. Klicka på länken på den valda raden i listan.
4. Visa eller dölj avsnittet Berättiganderegler.
5. Klicka på Redigera.
6. Välj Regelbaserad från listan i fältet Berättigande.
7. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Regeltyp.
8. I listan söker du efter och väljer den policyregel som tidigare har skapats.
9. Klicka på länken på den valda raden i listan.
10. Klicka på Spara.
11. Stäng formuläret.

