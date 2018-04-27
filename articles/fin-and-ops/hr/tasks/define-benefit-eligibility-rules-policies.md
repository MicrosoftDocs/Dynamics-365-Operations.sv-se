--- 
title: "Definiera förmånsberättiganderegler och policyer"
description: "Den här registreringen visar hur du kan skapa förmånberättiganderegler och policyer och sedan tilldela regler till förmåner."
author: kherr75
manager: AnnBe
ms.date: 06/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Operations, Talent
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 807e6a41d603a5327d713d1ab742cc0d961a7784
ms.contentlocale: sv-se
ms.lasthandoff: 04/13/2018

---
# <a name="define-benefit-eligibility-rules-and-policies"></a><span data-ttu-id="1ecda-103">Definiera förmånsberättiganderegler och policyer</span><span class="sxs-lookup"><span data-stu-id="1ecda-103">Define benefit eligibility rules and policies</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="1ecda-104">Den här registreringen visar hur du kan skapa förmånberättiganderegler och policyer och sedan tilldela regler till förmåner.</span><span class="sxs-lookup"><span data-stu-id="1ecda-104">This recording will show you how you can create benefit eligibility rules and policies and then assign rules to Benefits.</span></span>  

<span data-ttu-id="1ecda-105">Det demonstrationsdataföretag som används för att skapa den här registreringen är USMF.</span><span class="sxs-lookup"><span data-stu-id="1ecda-105">The demo data company used to create this recording is USMF.</span></span>


## <a name="create-benefit-eligibility-policy-rule-type"></a><span data-ttu-id="1ecda-106">Skapa policyregeltypen för förmånsberättigande</span><span class="sxs-lookup"><span data-stu-id="1ecda-106">Create benefit eligibility policy rule type</span></span>
1. <span data-ttu-id="1ecda-107">Gå till Personal > Förmåner > Berättigande > Policyregeltyper för förmånsberättigande.</span><span class="sxs-lookup"><span data-stu-id="1ecda-107">Go to Human resources > Benefits > Eligibility > Benefit eligibility policy rule types.</span></span>
2. <span data-ttu-id="1ecda-108">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="1ecda-108">Click New.</span></span>
3. <span data-ttu-id="1ecda-109">I fältet Regelnamn, skriv ett värde.</span><span class="sxs-lookup"><span data-stu-id="1ecda-109">In the Rule name field, type a value.</span></span>
4. <span data-ttu-id="1ecda-110">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="1ecda-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="1ecda-111">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Frågenamn.</span><span class="sxs-lookup"><span data-stu-id="1ecda-111">In the Query name field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="1ecda-112">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="1ecda-112">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="1ecda-113">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="1ecda-113">Click Save.</span></span>
8. <span data-ttu-id="1ecda-114">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="1ecda-114">Close the page.</span></span>

## <a name="benefit-eligibility-policy"></a><span data-ttu-id="1ecda-115">Policy för förmånsberättigande</span><span class="sxs-lookup"><span data-stu-id="1ecda-115">Benefit eligibility policy</span></span>
1. <span data-ttu-id="1ecda-116">Gå till Personal > Förmåner > Berättigande > Policyer för förmånsberättigande.</span><span class="sxs-lookup"><span data-stu-id="1ecda-116">Go to Human resources > Benefits > Eligibility > Benefit eligibility policies.</span></span>
2. <span data-ttu-id="1ecda-117">Välj en befintlig förmånspolicy.</span><span class="sxs-lookup"><span data-stu-id="1ecda-117">Select an existing benefit policy.</span></span>
3. <span data-ttu-id="1ecda-118">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="1ecda-118">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="1ecda-119">Växla expandering av policyorganisationsavsnitten.</span><span class="sxs-lookup"><span data-stu-id="1ecda-119">Toggle the expansion of the Policy organizations sections.</span></span>  <span data-ttu-id="1ecda-120">Här kan du lägga till eller ta bort organisationer som du vill inkludera i policyn.</span><span class="sxs-lookup"><span data-stu-id="1ecda-120">Here you can add or remove any organizations you want to include in the policy.</span></span>
5. <span data-ttu-id="1ecda-121">Expandera eller komprimera avsnittet Policyregler.</span><span class="sxs-lookup"><span data-stu-id="1ecda-121">Expand or collapse the Policy rules section.</span></span>
6. <span data-ttu-id="1ecda-122">I listan söker du efter den policyregel som tidigare har skapats.</span><span class="sxs-lookup"><span data-stu-id="1ecda-122">In the list find the policy rule previously created.</span></span>
7. <span data-ttu-id="1ecda-123">Klicka på Skapa policyregel.</span><span class="sxs-lookup"><span data-stu-id="1ecda-123">Click Create policy rule.</span></span>
8. <span data-ttu-id="1ecda-124">Ange det datum då du vill att den nya policyn ska börja gälla i fältet Giltighetsdatum.</span><span class="sxs-lookup"><span data-stu-id="1ecda-124">In the Effective date field, enter the date in which you want the policy to become effective.</span></span>
    * <span data-ttu-id="1ecda-125">Om du anger giltighetsdatum och slutdatum kan du göra framtida ändringar i policyregler och behöver inte gå tillbaka till policyn när du vill att dessa ändringar ska börja gälla.</span><span class="sxs-lookup"><span data-stu-id="1ecda-125">Setting effective and end dates allows you to make future changes to policy rules and removing the need to come back to the policy when you want those changes to take effect.</span></span>  
9. 
    * <span data-ttu-id="1ecda-126">Om du till exempel vill att regeln bara ska gälla för försäljningschefer kan du skapa en Where-sats för att säga: Där befattningen är lika med försäljningschef.</span><span class="sxs-lookup"><span data-stu-id="1ecda-126">For example if you wanted the rule to only apply to Sales Managers you could create the Where clause to say: Where position description equals Sales Manager.</span></span>  <span data-ttu-id="1ecda-127">Du kan samla Och eller Eller för flera Where-utdrag i regeln.</span><span class="sxs-lookup"><span data-stu-id="1ecda-127">You can And or Or multiple Where statements together in the rule.</span></span>  
10. <span data-ttu-id="1ecda-128">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="1ecda-128">Click OK.</span></span>
11. <span data-ttu-id="1ecda-129">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="1ecda-129">Close the page.</span></span>
12. <span data-ttu-id="1ecda-130">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="1ecda-130">Close the page.</span></span>

## <a name="assign-rule-to-benefit"></a><span data-ttu-id="1ecda-131">Tilldela regel till förmån</span><span class="sxs-lookup"><span data-stu-id="1ecda-131">Assign rule to benefit</span></span>
1. <span data-ttu-id="1ecda-132">Gå till Personal > Förmåner > Förmåner.</span><span class="sxs-lookup"><span data-stu-id="1ecda-132">Go to Human resources > Benefits > Benefits.</span></span>
2. <span data-ttu-id="1ecda-133">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="1ecda-133">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="1ecda-134">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="1ecda-134">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="1ecda-135">Visa eller dölj avsnittet Berättiganderegler.</span><span class="sxs-lookup"><span data-stu-id="1ecda-135">Expand or collapse the Eligibility rules section.</span></span>
5. <span data-ttu-id="1ecda-136">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="1ecda-136">Click Edit.</span></span>
6. <span data-ttu-id="1ecda-137">Välj Regelbaserad från listan i fältet Berättigande.</span><span class="sxs-lookup"><span data-stu-id="1ecda-137">In the Eligibility field, select Rule based from the list.</span></span>
7. <span data-ttu-id="1ecda-138">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Regeltyp.</span><span class="sxs-lookup"><span data-stu-id="1ecda-138">In the Rule type field, click the drop down button to open the lookup.</span></span>
8. <span data-ttu-id="1ecda-139">I listan söker du efter och väljer den policyregel som tidigare har skapats.</span><span class="sxs-lookup"><span data-stu-id="1ecda-139">In the list find and select the rule you previously created.</span></span>
9. <span data-ttu-id="1ecda-140">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="1ecda-140">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="1ecda-141">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="1ecda-141">Click Save.</span></span>
11. <span data-ttu-id="1ecda-142">Stäng formuläret.</span><span class="sxs-lookup"><span data-stu-id="1ecda-142">Close the form.</span></span>


