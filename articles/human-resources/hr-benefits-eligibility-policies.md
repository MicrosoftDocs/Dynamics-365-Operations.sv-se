---
title: Policyer för förmånsberättigande
description: Det här avsnittet innehåller information om policyer för förmånsberättigande som underlättar vid definition av vem som är berättigad till specifika förmåner.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmBenefitEligibilityDetail, SysPolicyListPage, SysPolicySourceDocumentRuleType, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 16441
ms.assetid: 4ad0106f-5b07-4fd5-bc1a-5834fa9b198e
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 8f0f51bc701af3f5dec2d393a87f589729af147bf44a56c4995991631f0d6379
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6727171"
---
# <a name="benefit-eligibility-policies"></a>Policyer för förmånsberättigande

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

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






[!INCLUDE[footer-include](../includes/footer-banner.md)]