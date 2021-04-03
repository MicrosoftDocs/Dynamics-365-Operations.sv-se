---
title: Definiera förmånsberättiganderegler och policyer
description: Den här artikeln visar hur du kan skapa förmånberättiganderegler och policyer och sedan tilldela regler till förmåner.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysPolicySourceDocumentRuleType, SysPolicyListPage, SysPolicy, HcmBenefitEligibilityPolicy, HcmBenefit, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Version 7.0.0, Human Resources
ms.openlocfilehash: 39a9a1c96ae2a12a32b3c5fbc67571bcf983c898
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/17/2021
ms.locfileid: "5467997"
---
# <a name="define-benefit-eligibility-rules-and-policies"></a><span data-ttu-id="2f778-103">Definiera förmånsberättiganderegler och policyer</span><span class="sxs-lookup"><span data-stu-id="2f778-103">Define benefit eligibility rules and policies</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="2f778-104">Detta ämne visar hur du kan skapa förmånsberättigande regler och policyer och sedan tilldela regler till förmåner.</span><span class="sxs-lookup"><span data-stu-id="2f778-104">This topic shows you how you can create benefit eligibility rules and policies and then assign rules to benefits.</span></span>  

## <a name="create-benefit-eligibility-policy-rule-type"></a><span data-ttu-id="2f778-105">Skapa policyregeltypen för förmånsberättigande</span><span class="sxs-lookup"><span data-stu-id="2f778-105">Create benefit eligibility policy rule type</span></span>

1. <span data-ttu-id="2f778-106">Gå till **Personal > Förmåner > Berättigande > Regeltyper för förmånsberättigande policyer**.</span><span class="sxs-lookup"><span data-stu-id="2f778-106">Go to **Human resources > Benefits > Eligibility > Benefit eligibility policy rule types**.</span></span>
2. <span data-ttu-id="2f778-107">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="2f778-107">Select **New**.</span></span>
3. <span data-ttu-id="2f778-108">I fältet **Regelnamn** anger du ett värde.</span><span class="sxs-lookup"><span data-stu-id="2f778-108">In the **Rule name** field, enter a value.</span></span>
4. <span data-ttu-id="2f778-109">I fältet **Beskrivning** anger du ett värde.</span><span class="sxs-lookup"><span data-stu-id="2f778-109">In the **Description** field, enter a value.</span></span>
5. <span data-ttu-id="2f778-110">I fältet **Frågenamn** väljer du listruteknappen för att öppna sökningen.</span><span class="sxs-lookup"><span data-stu-id="2f778-110">In the **Query name** field, select the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="2f778-111">Klicka på länken på önskad rad i valda listan.</span><span class="sxs-lookup"><span data-stu-id="2f778-111">In the list, select the link in the selected row.</span></span>
7. <span data-ttu-id="2f778-112">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="2f778-112">Select **Save**.</span></span>
8. <span data-ttu-id="2f778-113">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="2f778-113">Close the page.</span></span>

## <a name="benefit-eligibility-policy"></a><span data-ttu-id="2f778-114">Policy för förmånsberättigande</span><span class="sxs-lookup"><span data-stu-id="2f778-114">Benefit eligibility policy</span></span>

1. <span data-ttu-id="2f778-115">Gå till **Personal > Förmåner > Berättigande > Olicyer för förmånsberättigande**.</span><span class="sxs-lookup"><span data-stu-id="2f778-115">Go to **Human resources > Benefits > Eligibility > Benefit eligibility policies**.</span></span>
2. <span data-ttu-id="2f778-116">Välj en befintlig förmånspolicy.</span><span class="sxs-lookup"><span data-stu-id="2f778-116">Select an existing benefit policy.</span></span>
3. <span data-ttu-id="2f778-117">Klicka på länken på önskad rad i valda listan.</span><span class="sxs-lookup"><span data-stu-id="2f778-117">In the list, select the link in the selected row.</span></span>
4. <span data-ttu-id="2f778-118">Växla expandering av avsnitten **Policyorganisationer**.</span><span class="sxs-lookup"><span data-stu-id="2f778-118">Toggle the expansion of the **Policy organizations** sections.</span></span> <span data-ttu-id="2f778-119">Du kan lägga till eller ta bort organisationer som du vill inkludera i policyn.</span><span class="sxs-lookup"><span data-stu-id="2f778-119">You can add or remove any organizations you want to include in the policy.</span></span>
5. <span data-ttu-id="2f778-120">Expandera eller komprimera avsnittet **Policyregler**.</span><span class="sxs-lookup"><span data-stu-id="2f778-120">Expand or collapse the **Policy rules** section.</span></span>
6. <span data-ttu-id="2f778-121">I listan söker du efter den policyregel som tidigare har skapats.</span><span class="sxs-lookup"><span data-stu-id="2f778-121">In the list, find the policy rule previously created.</span></span>
7. <span data-ttu-id="2f778-122">Välj **Skapa policyregel**.</span><span class="sxs-lookup"><span data-stu-id="2f778-122">Select **Create policy rule**.</span></span>
8. <span data-ttu-id="2f778-123">I fältet **Giltighetsdatum** anger du datum då du vill att policyn ska träda i kraft.</span><span class="sxs-lookup"><span data-stu-id="2f778-123">In the **Effective date** field, enter the date in which you want the policy to become effective.</span></span>
    * <span data-ttu-id="2f778-124">Om du anger giltighetsdatum och slutdatum kan du göra framtida ändringar i policyregler, detta så att du inte behöver inte gå tillbaka till policyn när du vill att dessa ändringar ska börja gälla.</span><span class="sxs-lookup"><span data-stu-id="2f778-124">Setting effective end dates allows you to make future changes to policy rules so you don't need to come back to the policy when you want those changes to take effect.</span></span>  
9. <span data-ttu-id="2f778-125">Lägg vid behov till en where-klausul i fältet **Lägg till villkor**.</span><span class="sxs-lookup"><span data-stu-id="2f778-125">If needed, add a where clause to the **Add condition** field.</span></span>
    * <span data-ttu-id="2f778-126">Om du till exempel vill att regeln bara ska gälla för säljchefer kan du skapa en Where-sats för att säga: "Där befattningsbeskrivningen är lika med säljchef".</span><span class="sxs-lookup"><span data-stu-id="2f778-126">For example if you wanted the rule to only apply to Sales Managers you could create the where clause to say: Where position description equals Sales Manager.</span></span> <span data-ttu-id="2f778-127">Du kan lägga till flera where-instruktioner i regeln.</span><span class="sxs-lookup"><span data-stu-id="2f778-127">You can add multiple where statements together in the rule.</span></span>  
10. <span data-ttu-id="2f778-128">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="2f778-128">Select **OK**.</span></span>
11. <span data-ttu-id="2f778-129">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="2f778-129">Close the page.</span></span>

## <a name="assign-rule-to-benefit"></a><span data-ttu-id="2f778-130">Tilldela regel till förmån</span><span class="sxs-lookup"><span data-stu-id="2f778-130">Assign rule to benefit</span></span>

1. <span data-ttu-id="2f778-131">Gå till **Personal > Förmåner > Förmåner**.</span><span class="sxs-lookup"><span data-stu-id="2f778-131">Go to **Human resources > Benefits > Benefits**.</span></span>
2. <span data-ttu-id="2f778-132">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="2f778-132">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="2f778-133">Klicka på länken på önskad rad i valda listan.</span><span class="sxs-lookup"><span data-stu-id="2f778-133">In the list, select the link in the selected row.</span></span>
4. <span data-ttu-id="2f778-134">Visa eller dölj avsnittet **Berättiganderegler**.</span><span class="sxs-lookup"><span data-stu-id="2f778-134">Expand or collapse the **Eligibility rules** section.</span></span>
5. <span data-ttu-id="2f778-135">Välj **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="2f778-135">Select **Edit**.</span></span>
6. <span data-ttu-id="2f778-136">I fältet **Berättigande** väljer du regeln.</span><span class="sxs-lookup"><span data-stu-id="2f778-136">In the **Eligibility** field, select the rule.</span></span>
7. <span data-ttu-id="2f778-137">I fältet **Regeltyp** väljer du den regel du tidigare skapat.</span><span class="sxs-lookup"><span data-stu-id="2f778-137">In the **Rule type** field, select the rule you previously created.</span></span>
9. <span data-ttu-id="2f778-138">Klicka på länken på önskad rad i valda listan.</span><span class="sxs-lookup"><span data-stu-id="2f778-138">In the list, select the link in the selected row.</span></span>
10. <span data-ttu-id="2f778-139">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="2f778-139">Select **Save**.</span></span>
11. <span data-ttu-id="2f778-140">Stäng formuläret.</span><span class="sxs-lookup"><span data-stu-id="2f778-140">Close the form.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]