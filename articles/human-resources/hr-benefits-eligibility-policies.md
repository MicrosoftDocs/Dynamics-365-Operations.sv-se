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
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 16441
ms.assetid: 4ad0106f-5b07-4fd5-bc1a-5834fa9b198e
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: a5046f1d32fb965c7cb3793daf1ba40b9c2a1d10
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5805908"
---
# <a name="benefit-eligibility-policies"></a><span data-ttu-id="3f479-103">Policyer för förmånsberättigande</span><span class="sxs-lookup"><span data-stu-id="3f479-103">Benefit eligibility policies</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="3f479-104">Det här avsnittet innehåller information om policyer för förmånsberättigande som underlättar vid definition av vem som är berättigad till specifika förmåner.</span><span class="sxs-lookup"><span data-stu-id="3f479-104">This article provides information about benefit eligibility policies, which help you define who is eligible for specific benefits.</span></span>

<span data-ttu-id="3f479-105">När du skapar förmåner, väljer du vilka förmåner ska vara tillgängliga för vilka medarbetare.</span><span class="sxs-lookup"><span data-stu-id="3f479-105">When you create benefits, you decide which benefits will be available to which employees.</span></span> <span data-ttu-id="3f479-106">Följande tabell visar exempel på förmåner som du kan göra tillgängliga för specifika medarbetare.</span><span class="sxs-lookup"><span data-stu-id="3f479-106">The following table shows examples of benefits that you might make available to specific employees.</span></span>

| <span data-ttu-id="3f479-107">Förmån</span><span class="sxs-lookup"><span data-stu-id="3f479-107">Benefit</span></span>          | <span data-ttu-id="3f479-108">Vem förmånen är tillgängliga för</span><span class="sxs-lookup"><span data-stu-id="3f479-108">Who the benefit is available to</span></span> |
|------------------|---------------------------------|
| <span data-ttu-id="3f479-109">Sjukförsäkring</span><span class="sxs-lookup"><span data-stu-id="3f479-109">Health insurance</span></span> | <span data-ttu-id="3f479-110">Alla medarbetare</span><span class="sxs-lookup"><span data-stu-id="3f479-110">All employees</span></span>                   |
| <span data-ttu-id="3f479-111">Mobiltelefon</span><span class="sxs-lookup"><span data-stu-id="3f479-111">Mobile phone</span></span>     | <span data-ttu-id="3f479-112">Försäljningspersonal, chefer</span><span class="sxs-lookup"><span data-stu-id="3f479-112">Sales staff, executives</span></span>         |
| <span data-ttu-id="3f479-113">Parkeringskort</span><span class="sxs-lookup"><span data-stu-id="3f479-113">Parking passes</span></span>   | <span data-ttu-id="3f479-114">Chefer</span><span class="sxs-lookup"><span data-stu-id="3f479-114">Executives</span></span>                      |

<span data-ttu-id="3f479-115">Följande komponenter används för att skapa valbarhetpolicyer:</span><span class="sxs-lookup"><span data-stu-id="3f479-115">The following components in are used to create eligibility policies:</span></span>

-   <span data-ttu-id="3f479-116">Policyregeltyper</span><span class="sxs-lookup"><span data-stu-id="3f479-116">Policy rule types</span></span>
-   <span data-ttu-id="3f479-117">Policyer för förmånsberättigande</span><span class="sxs-lookup"><span data-stu-id="3f479-117">Benefit eligibility policies</span></span>

<span data-ttu-id="3f479-118">Policyregeltyper definierar frågeparametrar som används när du utvecklar specifika policyregler.</span><span class="sxs-lookup"><span data-stu-id="3f479-118">Policy rule types define the query parameters that are used when you develop specific policy rules.</span></span> <span data-ttu-id="3f479-119">När du har skapat policyregeltyper, kan du skapa förmånvalbarhetpolicyer.</span><span class="sxs-lookup"><span data-stu-id="3f479-119">After you create policy rule types, you can create benefit eligibility policies.</span></span> <span data-ttu-id="3f479-120">Policyerna gör att du kan skapa en grupp av regler som gäller en eller flera juridiska personer.</span><span class="sxs-lookup"><span data-stu-id="3f479-120">The policies let you create a collection of rules that apply to one or more legal entities.</span></span> <span data-ttu-id="3f479-121">Inom varje policy kan du visa någon av policyregeltyperna för förmånsberättigande som du skapade tidigare.</span><span class="sxs-lookup"><span data-stu-id="3f479-121">Within each policy, you can view any of the benefit eligibility policy rule types that you created earlier.</span></span> 

<span data-ttu-id="3f479-122">Du definierar regelns omfång inom policyn.</span><span class="sxs-lookup"><span data-stu-id="3f479-122">You define the scope of the rule within the policy.</span></span> <span data-ttu-id="3f479-123">Om du till exempel skapar en policyregeltyp för förmånsberättigande med namnet **Chef** kan du ange vad regeln är inom den policyn.</span><span class="sxs-lookup"><span data-stu-id="3f479-123">For example, if you create a benefit eligibility policy rule type that is named **Executive**, you can specify what the rule is within that policy.</span></span> <span data-ttu-id="3f479-124">I det här exemplet kan regeln ange att en jobbtitel som innehåller ordet chef inkluderas i regeln.</span><span class="sxs-lookup"><span data-stu-id="3f479-124">In this example, the rule might state that any job title that contains the word "executive" should be included in the rule.</span></span> <span data-ttu-id="3f479-125">När du har definierat parametrar för regeln eller regler som är inkluderade i policyn, kan du koppla en viss regel till förmånen.</span><span class="sxs-lookup"><span data-stu-id="3f479-125">After you've defined the parameters of the rule or rules that are included in the policy, you can assign a specific rule to the benefit.</span></span>






[!INCLUDE[footer-include](../includes/footer-banner.md)]