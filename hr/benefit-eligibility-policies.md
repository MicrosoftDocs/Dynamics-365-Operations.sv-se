---
title: "Policyer för förmånsberättigande"
description: "Det här avsnittet innehåller information om policyer för förmånsberättigande som underlättar vid definition av vem som är berättigad till specifika förmåner."
author: rschloma
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: HcmBenefitEligibilityDetail, SysPolicyListPage, SysPolicySourceDocumentRuleType
audience: Application User
ms.reviewer: rschloma
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 16441
ms.assetid: 4ad0106f-5b07-4fd5-bc1a-5834fa9b198e
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 076b4f14a09698b6a0e2f5f3dd4f74ef5b673a8d
ms.contentlocale: sv-se
ms.lasthandoff: 04/25/2017


---

# <a name="benefit-eligibility-policies"></a>Policyer för förmånsberättigande

[!include[banner](includes/banner.md)]


Det här avsnittet innehåller information om policyer för förmånsberättigande som underlättar vid definition av vem som är berättigad till specifika förmåner.

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

Du definierar regelns omfång inom policyn. Om du till exempel skapar en policyregeltyp för förmånsberättigande med namnet **Chef** kan du ange vad regeln är inom den policyn. I det här exemplet kan regeln ange att en jobbtitel som innehåller ordet chef inkluderas i regeln. När du har definierat parametrar för regeln eller regler som är inkluderade i policyn, kan du koppla en viss regel till förmånen.

<a name="see-also"></a>Se även
--------

[Definiera och hantera ett förmånsprogram](manage-benefit-program.md)




