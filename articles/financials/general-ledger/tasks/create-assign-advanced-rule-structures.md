---
title: Skapa och tilldela avancerade regelstrukturer
description: Den här uppgiften beskriver steg för steg hur du skapar och tilldelar en avancerad regelstruktur till en kontostruktur.
author: aprilolson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DimensionConfigureAccountRuleStructure, DimensionCreateAccountRuleStructure, DimensionHierarchyAddLevel, DimensionHierarchyConstraintActivate, DimensionConfigureAccountStructure, DimensionConfigureAccountRule, DimensionCreateAccountRule, DimensionSelectAccountRuleStructure
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: dd62254c20cf5d77677d03c7d7335fb793d7f5f2
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "367051"
---
# <a name="create-and-assign-advanced-rule-structures"></a><span data-ttu-id="83c00-103">Skapa och tilldela avancerade regelstrukturer</span><span class="sxs-lookup"><span data-stu-id="83c00-103">Create and assign advanced rule structures</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="83c00-104">Den här uppgiften beskriver steg för steg hur du skapar och tilldelar en avancerad regelstruktur till en kontostruktur.</span><span class="sxs-lookup"><span data-stu-id="83c00-104">This task guide steps through creating and assigning an advanced rule structure to an account structure.</span></span> <span data-ttu-id="83c00-105">Den här guiden använder demoföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="83c00-105">This guide uses the USMF demo company.</span></span>


## <a name="create-an-advanced-rule-structure"></a><span data-ttu-id="83c00-106">Skapa en avancerad regelstruktur</span><span class="sxs-lookup"><span data-stu-id="83c00-106">Create an advanced rule structure</span></span>
1. <span data-ttu-id="83c00-107">Gå till Redovisning > Kontoplan > Strukturerar > Avancerade regelstrukturer.</span><span class="sxs-lookup"><span data-stu-id="83c00-107">Go to General ledger > Chart of accounts > Structures > Advanced rule structures.</span></span>
2. <span data-ttu-id="83c00-108">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="83c00-108">Click New to open the drop dialog.</span></span>
3. <span data-ttu-id="83c00-109">Ange ett namn som beskriver regelstrukturen i fältet Avancerad regelstruktur.</span><span class="sxs-lookup"><span data-stu-id="83c00-109">In the Advanced rule structure field, type a name to descritbe the rule structure.</span></span>
4. <span data-ttu-id="83c00-110">Ange ett värde som beskriver strukturen i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="83c00-110">In the Description field, type a value to describe the structure.</span></span>
5. <span data-ttu-id="83c00-111">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="83c00-111">Click OK.</span></span>
6. <span data-ttu-id="83c00-112">Klicka på Lägg till segment.</span><span class="sxs-lookup"><span data-stu-id="83c00-112">Click Add segment.</span></span>
7. <span data-ttu-id="83c00-113">Välj en ekonomisk dimension i listan med segment.</span><span class="sxs-lookup"><span data-stu-id="83c00-113">In the list of segments, select a financial dimension.</span></span>
    * <span data-ttu-id="83c00-114">Till exempel Butik.</span><span class="sxs-lookup"><span data-stu-id="83c00-114">For example, Store.</span></span>  
8. <span data-ttu-id="83c00-115">Klicka på Lägg till segment.</span><span class="sxs-lookup"><span data-stu-id="83c00-115">Click Add segment.</span></span>
9. <span data-ttu-id="83c00-116">I listan klickar du på länken för den avancerade regelstrukturen för att visa den.</span><span class="sxs-lookup"><span data-stu-id="83c00-116">In the list, click the link of the advanced rule structure to view it.</span></span>
10. <span data-ttu-id="83c00-117">Klicka på Aktivera.</span><span class="sxs-lookup"><span data-stu-id="83c00-117">Click Activate.</span></span>
11. <span data-ttu-id="83c00-118">Klicka på Aktivera.</span><span class="sxs-lookup"><span data-stu-id="83c00-118">Click Activate.</span></span>

## <a name="apply-an-advanced-rule-structure-to-an-account-structure"></a><span data-ttu-id="83c00-119">Använd en avancerad regelstruktur för en kontostruktur</span><span class="sxs-lookup"><span data-stu-id="83c00-119">Apply an advanced rule structure to an account structure</span></span>
1. <span data-ttu-id="83c00-120">Stäng formuläret.</span><span class="sxs-lookup"><span data-stu-id="83c00-120">Close the form.</span></span>
2. <span data-ttu-id="83c00-121">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="83c00-121">Close the page.</span></span>
3. <span data-ttu-id="83c00-122">Gå till Redovisning > Kontoplan > Strukturer > Konfigurera kontostrukturer.</span><span class="sxs-lookup"><span data-stu-id="83c00-122">Go to General ledger > Chart of accounts > Structures > Configure account structures.</span></span>
4. <span data-ttu-id="83c00-123">I listan letar du upp och väljer den kontostruktur som du vill tillämpa den avancerade regeln på.</span><span class="sxs-lookup"><span data-stu-id="83c00-123">In the list, find and select the account structure you want to apply the advanced rule to.</span></span>
5. <span data-ttu-id="83c00-124">Klicka på namnet på kontostrukturen för att öppna den.</span><span class="sxs-lookup"><span data-stu-id="83c00-124">Click the name of the account structure to open it.</span></span>
6. <span data-ttu-id="83c00-125">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="83c00-125">Click Edit.</span></span>
    * <span data-ttu-id="83c00-126">Du kan också klicka på Avancerade regler så uppmanas du att placera kontostrukturen i utkastläge.</span><span class="sxs-lookup"><span data-stu-id="83c00-126">You can also click Advanced rules and you will be prompted to put the account structure in Draft mode.</span></span>  
7. <span data-ttu-id="83c00-127">Klicka på Avancerade regler.</span><span class="sxs-lookup"><span data-stu-id="83c00-127">Click Advanced rules.</span></span>
8. <span data-ttu-id="83c00-128">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="83c00-128">Click New to open the drop dialog.</span></span>
9. <span data-ttu-id="83c00-129">Ange ett värde i fältet Avancerad regel.</span><span class="sxs-lookup"><span data-stu-id="83c00-129">In the Advanced rule field, type a value.</span></span>
10. <span data-ttu-id="83c00-130">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="83c00-130">In the Name field, type a value.</span></span>
11. <span data-ttu-id="83c00-131">Klicka på Skapa.</span><span class="sxs-lookup"><span data-stu-id="83c00-131">Click Create.</span></span>
12. <span data-ttu-id="83c00-132">Klicka på Lägg till nya kriterier.</span><span class="sxs-lookup"><span data-stu-id="83c00-132">Click Add new criteria.</span></span>
13. <span data-ttu-id="83c00-133">Välj huvudkonto eller en ekonomisk dimension i fältet Där.</span><span class="sxs-lookup"><span data-stu-id="83c00-133">In the Where field, select main account or a financial dimension.</span></span>
14. <span data-ttu-id="83c00-134">Välj ett alternativ i fältet Operator, t.ex. är mellan och inkluderar.</span><span class="sxs-lookup"><span data-stu-id="83c00-134">In the Operator field, select an option, such as is between and includes.</span></span>
15. <span data-ttu-id="83c00-135">Ange ett värde i fältet Värde.</span><span class="sxs-lookup"><span data-stu-id="83c00-135">In the Value field, type a value.</span></span>
16. <span data-ttu-id="83c00-136">Skriv ett värde i fältet via.</span><span class="sxs-lookup"><span data-stu-id="83c00-136">In the through field, type a value.</span></span>
17. <span data-ttu-id="83c00-137">Klicka på Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="83c00-137">Click Add to open the drop dialog.</span></span>
18. <span data-ttu-id="83c00-138">I listan letar du upp den avancerade regelstruktur som du vill använda när de villkor som du angett uppfylls.</span><span class="sxs-lookup"><span data-stu-id="83c00-138">In the list, find the advanced rule structure you want to use when the criteria you entered is met.</span></span>
19. <span data-ttu-id="83c00-139">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="83c00-139">Click Add.</span></span>
20. <span data-ttu-id="83c00-140">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="83c00-140">Close the page.</span></span>
21. <span data-ttu-id="83c00-141">Klicka på Aktivera.</span><span class="sxs-lookup"><span data-stu-id="83c00-141">Click Activate.</span></span>
22. <span data-ttu-id="83c00-142">Klicka på Aktivera.</span><span class="sxs-lookup"><span data-stu-id="83c00-142">Click Activate.</span></span>

