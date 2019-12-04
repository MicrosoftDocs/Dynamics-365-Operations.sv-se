---
title: Policyer för förmånsberättigande
description: Det här avsnittet innehåller information om policyer för förmånsberättigande som underlättar vid definition av vem som är berättigad till specifika förmåner.
author: andreabichsel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: HcmBenefitEligibilityDetail, SysPolicyListPage, SysPolicySourceDocumentRuleType
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.custom: 16441
ms.assetid: 4ad0106f-5b07-4fd5-bc1a-5834fa9b198e
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.openlocfilehash: b44287bf22f0b6c4e33a29b4b86aaae934505a43
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/18/2019
ms.locfileid: "2814707"
---
# <a name="benefit-eligibility-policies"></a>Policyer för förmånsberättigande

[!include [banner](includes/banner.md)]

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

<a name="additional-resources"></a>Ytterligare resurser
--------

[Definiera och hantera ett förmånsprogram](manage-benefit-program.md)



