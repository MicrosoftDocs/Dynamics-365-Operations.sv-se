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
# <a name="define-benefit-eligibility-rules-and-policies"></a><span data-ttu-id="a6726-103">Definiera förmånsberättiganderegler och policyer</span><span class="sxs-lookup"><span data-stu-id="a6726-103">Define benefit eligibility rules and policies</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a6726-104">Den här registreringen visar hur du kan skapa förmånberättiganderegler och policyer och sedan tilldela regler till förmåner.</span><span class="sxs-lookup"><span data-stu-id="a6726-104">This recording will show you how you can create benefit eligibility rules and policies and then assign rules to Benefits.</span></span>  

<span data-ttu-id="a6726-105">Det demonstrationsdataföretag som används för att skapa den här registreringen är USMF.</span><span class="sxs-lookup"><span data-stu-id="a6726-105">The demo data company used to create this recording is USMF.</span></span>


## <a name="create-benefit-eligibility-policy-rule-type"></a><span data-ttu-id="a6726-106">Skapa policyregeltypen för förmånsberättigande</span><span class="sxs-lookup"><span data-stu-id="a6726-106">Create benefit eligibility policy rule type</span></span>
1. <span data-ttu-id="a6726-107">Gå till Personal > Förmåner > Berättigande > Policyregeltyper för förmånsberättigande.</span><span class="sxs-lookup"><span data-stu-id="a6726-107">Go to Human resources > Benefits > Eligibility > Benefit eligibility policy rule types.</span></span>
2. <span data-ttu-id="a6726-108">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="a6726-108">Click New.</span></span>
3. <span data-ttu-id="a6726-109">I fältet Regelnamn, skriv ett värde.</span><span class="sxs-lookup"><span data-stu-id="a6726-109">In the Rule name field, type a value.</span></span>
4. <span data-ttu-id="a6726-110">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="a6726-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="a6726-111">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Frågenamn.</span><span class="sxs-lookup"><span data-stu-id="a6726-111">In the Query name field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="a6726-112">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="a6726-112">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="a6726-113">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="a6726-113">Click Save.</span></span>
8. <span data-ttu-id="a6726-114">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="a6726-114">Close the page.</span></span>

## <a name="benefit-eligibility-policy"></a><span data-ttu-id="a6726-115">Policy för förmånsberättigande</span><span class="sxs-lookup"><span data-stu-id="a6726-115">Benefit eligibility policy</span></span>
1. <span data-ttu-id="a6726-116">Gå till Personal > Förmåner > Berättigande > Policyer för förmånsberättigande.</span><span class="sxs-lookup"><span data-stu-id="a6726-116">Go to Human resources > Benefits > Eligibility > Benefit eligibility policies.</span></span>
2. <span data-ttu-id="a6726-117">Välj en befintlig förmånspolicy.</span><span class="sxs-lookup"><span data-stu-id="a6726-117">Select an existing benefit policy.</span></span>
3. <span data-ttu-id="a6726-118">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="a6726-118">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="a6726-119">Växla expandering av policyorganisationsavsnitten.</span><span class="sxs-lookup"><span data-stu-id="a6726-119">Toggle the expansion of the Policy organizations sections.</span></span>  <span data-ttu-id="a6726-120">Här kan du lägga till eller ta bort organisationer som du vill inkludera i policyn.</span><span class="sxs-lookup"><span data-stu-id="a6726-120">Here you can add or remove any organizations you want to include in the policy.</span></span>
5. <span data-ttu-id="a6726-121">Expandera eller komprimera avsnittet Policyregler.</span><span class="sxs-lookup"><span data-stu-id="a6726-121">Expand or collapse the Policy rules section.</span></span>
6. <span data-ttu-id="a6726-122">I listan söker du efter den policyregel som tidigare har skapats.</span><span class="sxs-lookup"><span data-stu-id="a6726-122">In the list find the policy rule previously created.</span></span>
7. <span data-ttu-id="a6726-123">Klicka på Skapa policyregel.</span><span class="sxs-lookup"><span data-stu-id="a6726-123">Click Create policy rule.</span></span>
8. <span data-ttu-id="a6726-124">Ange det datum då du vill att den nya policyn ska börja gälla i fältet Giltighetsdatum.</span><span class="sxs-lookup"><span data-stu-id="a6726-124">In the Effective date field, enter the date in which you want the policy to become effective.</span></span>
    * <span data-ttu-id="a6726-125">Om du anger giltighetsdatum och slutdatum kan du göra framtida ändringar i policyregler och behöver inte gå tillbaka till policyn när du vill att dessa ändringar ska börja gälla.</span><span class="sxs-lookup"><span data-stu-id="a6726-125">Setting effective and end dates allows you to make future changes to policy rules and removing the need to come back to the policy when you want those changes to take effect.</span></span>  
9. 
    * <span data-ttu-id="a6726-126">Om du till exempel vill att regeln bara ska gälla för försäljningschefer kan du skapa en Where-sats för att säga: Där befattningen är lika med försäljningschef.</span><span class="sxs-lookup"><span data-stu-id="a6726-126">For example if you wanted the rule to only apply to Sales Managers you could create the Where clause to say: Where position description equals Sales Manager.</span></span>  <span data-ttu-id="a6726-127">Du kan samla Och eller Eller för flera Where-utdrag i regeln.</span><span class="sxs-lookup"><span data-stu-id="a6726-127">You can And or Or multiple Where statements together in the rule.</span></span>  
10. <span data-ttu-id="a6726-128">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="a6726-128">Click OK.</span></span>
11. <span data-ttu-id="a6726-129">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="a6726-129">Close the page.</span></span>
12. <span data-ttu-id="a6726-130">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="a6726-130">Close the page.</span></span>

## <a name="assign-rule-to-benefit"></a><span data-ttu-id="a6726-131">Tilldela regel till förmån</span><span class="sxs-lookup"><span data-stu-id="a6726-131">Assign rule to benefit</span></span>
1. <span data-ttu-id="a6726-132">Gå till Personal > Förmåner > Förmåner.</span><span class="sxs-lookup"><span data-stu-id="a6726-132">Go to Human resources > Benefits > Benefits.</span></span>
2. <span data-ttu-id="a6726-133">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="a6726-133">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="a6726-134">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="a6726-134">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="a6726-135">Visa eller dölj avsnittet Berättiganderegler.</span><span class="sxs-lookup"><span data-stu-id="a6726-135">Expand or collapse the Eligibility rules section.</span></span>
5. <span data-ttu-id="a6726-136">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="a6726-136">Click Edit.</span></span>
6. <span data-ttu-id="a6726-137">Välj Regelbaserad från listan i fältet Berättigande.</span><span class="sxs-lookup"><span data-stu-id="a6726-137">In the Eligibility field, select Rule based from the list.</span></span>
7. <span data-ttu-id="a6726-138">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Regeltyp.</span><span class="sxs-lookup"><span data-stu-id="a6726-138">In the Rule type field, click the drop down button to open the lookup.</span></span>
8. <span data-ttu-id="a6726-139">I listan söker du efter och väljer den policyregel som tidigare har skapats.</span><span class="sxs-lookup"><span data-stu-id="a6726-139">In the list find and select the rule you previously created.</span></span>
9. <span data-ttu-id="a6726-140">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="a6726-140">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="a6726-141">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="a6726-141">Click Save.</span></span>
11. <span data-ttu-id="a6726-142">Stäng formuläret.</span><span class="sxs-lookup"><span data-stu-id="a6726-142">Close the form.</span></span>

