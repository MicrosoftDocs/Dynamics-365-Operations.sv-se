---
title: Policyer för förmånsberättigande
description: Det här avsnittet innehåller information om policyer för förmånsberättigande som underlättar vid definition av vem som är berättigad till specifika förmåner.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
ms.search.form: HcmBenefitEligibilityDetail, SysPolicyListPage, SysPolicySourceDocumentRuleType
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Human Resources
ms.custom: 16441
ms.assetid: 4ad0106f-5b07-4fd5-bc1a-5834fa9b198e
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 7b35d3f9a8afd3be44b648f6e138afd5f143ba55
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010673"
---
# <a name="benefit-eligibility-policies"></a><span data-ttu-id="13d12-103">Policyer för förmånsberättigande</span><span class="sxs-lookup"><span data-stu-id="13d12-103">Benefit eligibility policies</span></span>

<span data-ttu-id="13d12-104">Det här avsnittet innehåller information om policyer för förmånsberättigande som underlättar vid definition av vem som är berättigad till specifika förmåner.</span><span class="sxs-lookup"><span data-stu-id="13d12-104">This article provides information about benefit eligibility policies, which help you define who is eligible for specific benefits.</span></span>

<span data-ttu-id="13d12-105">När du skapar förmåner, väljer du vilka förmåner ska vara tillgängliga för vilka medarbetare.</span><span class="sxs-lookup"><span data-stu-id="13d12-105">When you create benefits, you decide which benefits will be available to which employees.</span></span> <span data-ttu-id="13d12-106">Följande tabell visar exempel på förmåner som du kan göra tillgängliga för specifika medarbetare.</span><span class="sxs-lookup"><span data-stu-id="13d12-106">The following table shows examples of benefits that you might make available to specific employees.</span></span>

| <span data-ttu-id="13d12-107">Förmån</span><span class="sxs-lookup"><span data-stu-id="13d12-107">Benefit</span></span>          | <span data-ttu-id="13d12-108">Vem förmånen är tillgängliga för</span><span class="sxs-lookup"><span data-stu-id="13d12-108">Who the benefit is available to</span></span> |
|------------------|---------------------------------|
| <span data-ttu-id="13d12-109">Sjukförsäkring</span><span class="sxs-lookup"><span data-stu-id="13d12-109">Health insurance</span></span> | <span data-ttu-id="13d12-110">Alla medarbetare</span><span class="sxs-lookup"><span data-stu-id="13d12-110">All employees</span></span>                   |
| <span data-ttu-id="13d12-111">Mobiltelefon</span><span class="sxs-lookup"><span data-stu-id="13d12-111">Mobile phone</span></span>     | <span data-ttu-id="13d12-112">Försäljningspersonal, chefer</span><span class="sxs-lookup"><span data-stu-id="13d12-112">Sales staff, executives</span></span>         |
| <span data-ttu-id="13d12-113">Parkeringskort</span><span class="sxs-lookup"><span data-stu-id="13d12-113">Parking passes</span></span>   | <span data-ttu-id="13d12-114">Chefer</span><span class="sxs-lookup"><span data-stu-id="13d12-114">Executives</span></span>                      |

<span data-ttu-id="13d12-115">Följande komponenter används för att skapa valbarhetpolicyer:</span><span class="sxs-lookup"><span data-stu-id="13d12-115">The following components in are used to create eligibility policies:</span></span>

-   <span data-ttu-id="13d12-116">Policyregeltyper</span><span class="sxs-lookup"><span data-stu-id="13d12-116">Policy rule types</span></span>
-   <span data-ttu-id="13d12-117">Policyer för förmånsberättigande</span><span class="sxs-lookup"><span data-stu-id="13d12-117">Benefit eligibility policies</span></span>

<span data-ttu-id="13d12-118">Policyregeltyper definierar frågeparametrar som används när du utvecklar specifika policyregler.</span><span class="sxs-lookup"><span data-stu-id="13d12-118">Policy rule types define the query parameters that are used when you develop specific policy rules.</span></span> <span data-ttu-id="13d12-119">När du har skapat policyregeltyper, kan du skapa förmånvalbarhetpolicyer.</span><span class="sxs-lookup"><span data-stu-id="13d12-119">After you create policy rule types, you can create benefit eligibility policies.</span></span> <span data-ttu-id="13d12-120">Policyerna gör att du kan skapa en grupp av regler som gäller en eller flera juridiska personer.</span><span class="sxs-lookup"><span data-stu-id="13d12-120">The policies let you create a collection of rules that apply to one or more legal entities.</span></span> <span data-ttu-id="13d12-121">Inom varje policy kan du visa någon av policyregeltyperna för förmånsberättigande som du skapade tidigare.</span><span class="sxs-lookup"><span data-stu-id="13d12-121">Within each policy, you can view any of the benefit eligibility policy rule types that you created earlier.</span></span> 

<span data-ttu-id="13d12-122">Du definierar regelns omfång inom policyn.</span><span class="sxs-lookup"><span data-stu-id="13d12-122">You define the scope of the rule within the policy.</span></span> <span data-ttu-id="13d12-123">Om du till exempel skapar en policyregeltyp för förmånsberättigande med namnet **Chef** kan du ange vad regeln är inom den policyn.</span><span class="sxs-lookup"><span data-stu-id="13d12-123">For example, if you create a benefit eligibility policy rule type that is named **Executive**, you can specify what the rule is within that policy.</span></span> <span data-ttu-id="13d12-124">I det här exemplet kan regeln ange att en jobbtitel som innehåller ordet chef inkluderas i regeln.</span><span class="sxs-lookup"><span data-stu-id="13d12-124">In this example, the rule might state that any job title that contains the word "executive" should be included in the rule.</span></span> <span data-ttu-id="13d12-125">När du har definierat parametrar för regeln eller regler som är inkluderade i policyn, kan du koppla en viss regel till förmånen.</span><span class="sxs-lookup"><span data-stu-id="13d12-125">After you've defined the parameters of the rule or rules that are included in the policy, you can assign a specific rule to the benefit.</span></span>




