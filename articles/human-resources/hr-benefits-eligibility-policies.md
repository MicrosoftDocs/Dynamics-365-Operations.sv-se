---
title: Policyer för förmånsberättigande
description: Detta avsnitt innehåller information om policyer för förmånsberättigande som definierar vem som är berättigad till specifika förmåner.
author: twheeloc
ms.date: 08/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmBenefitEligibilityDetail, SysPolicyListPage, SysPolicySourceDocumentRuleType, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.custom: 16441
ms.assetid: 4ad0106f-5b07-4fd5-bc1a-5834fa9b198e
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: e36235e089fef70bc0d33815cd855628836f58db
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/04/2022
ms.locfileid: "8689562"
---
# <a name="benefit-eligibility-policies"></a>Policyer för förmånsberättigande


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Detta avsnitt innehåller information om policyer för förmånsberättigande som definierar vem som är berättigad till specifika förmåner.

När du skapar förmåner, väljer du vilka förmåner ska vara tillgängliga för vilka medarbetare. Följande tabell visar exempel på förmåner som du kan göra tillgängliga för specifika medarbetare.

| Förmån          | Vem förmånen är tillgängliga för |
|------------------|---------------------------------|
| Sjukförsäkring | Alla medarbetare                   |
| Mobiltelefon     | Försäljningspersonal, chefer         |
| Parkeringskort   | Chefer                      |

Följande komponenter används för att skapa valbarhetpolicyer:

-   Policyregeltyper
-   Policyer för förmånsberättigande

Policyregeltyper definierar frågeparametrar som används när du utvecklar specifika policyregler. När du har skapat policyregeltyper, kan du skapa förmånvalbarhetpolicyer. Policyerna gör att du kan skapa en grupp av regler som gäller en eller flera juridiska personer. Inom varje policy kan du visa någon av policyregeltyperna för förmånsberättigande som du skapade tidigare. 

Du definierar regelns omfång inom policyn. Om du till exempel skapar en policyregeltyp för förmånsberättigande med namnet **Chef** kan du ange vad regeln är inom den policyn. I det här exemplet kan regeln ange att en jobbrubrik som innehåller ordet chef inkluderas i regeln. När du har definierat parametrar för regeln eller regler som är inkluderade i policyn, kan du koppla en viss regel till förmånen.






[!INCLUDE[footer-include](../includes/footer-banner.md)]
