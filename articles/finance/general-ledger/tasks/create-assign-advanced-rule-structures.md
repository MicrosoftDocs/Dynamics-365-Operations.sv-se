---
title: Skapa och tilldela avancerade regelstrukturer
description: I det här avsnittet beskrivs hur du skapar och tilldelar en avancerad regelstruktur till en kontostruktur.
author: aprilolson
manager: AnnBe
ms.date: 07/19/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DimensionConfigureAccountRuleStructure, DimensionCreateAccountRuleStructure, DimensionHierarchyAddLevel, DimensionHierarchyConstraintActivate, DimensionConfigureAccountStructure, DimensionConfigureAccountRule, DimensionCreateAccountRule, DimensionSelectAccountRuleStructure
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9a7b9d0c20a49996b4c8d45b030d9e587818de3d
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5216555"
---
# <a name="create-and-assign-advanced-rule-structures"></a><span data-ttu-id="cd2eb-103">Skapa och tilldela avancerade regelstrukturer</span><span class="sxs-lookup"><span data-stu-id="cd2eb-103">Create and assign advanced rule structures</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="cd2eb-104">I det här avsnittet beskrivs hur du skapar och tilldelar en avancerad regelstruktur till en kontostruktur.</span><span class="sxs-lookup"><span data-stu-id="cd2eb-104">This topic explains how to create and assign an advanced rule structure to an account structure.</span></span> <span data-ttu-id="cd2eb-105">Den här guiden använder demoföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="cd2eb-105">This guide uses the USMF demo company.</span></span>

## <a name="create-an-advanced-rule-structure"></a><span data-ttu-id="cd2eb-106">Skapa en avancerad regelstruktur</span><span class="sxs-lookup"><span data-stu-id="cd2eb-106">Create an advanced rule structure</span></span>
1. <span data-ttu-id="cd2eb-107">Gå till **Navigeringsfönster > Moduler > General ledger > Chart of accounts > Structures > Advanced rule structures**.</span><span class="sxs-lookup"><span data-stu-id="cd2eb-107">Go to **Navigation pane > Modules > General ledger > Chart of accounts > Structures > Advanced rule structures**.</span></span>
2. <span data-ttu-id="cd2eb-108">Välj **Nytt** om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="cd2eb-108">Select **New** to open the drop dialog.</span></span>
3. <span data-ttu-id="cd2eb-109">Ange ett namn som beskriver regelstrukturen i fältet **Avancerad regelstruktur**.</span><span class="sxs-lookup"><span data-stu-id="cd2eb-109">In the **Advanced rule structure** field, type a name to describe the rule structure.</span></span>
4. <span data-ttu-id="cd2eb-110">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="cd2eb-110">Select **OK**.</span></span>
5. <span data-ttu-id="cd2eb-111">Välj **Lägg till segment**.</span><span class="sxs-lookup"><span data-stu-id="cd2eb-111">Select **Add segment**.</span></span>
6. <span data-ttu-id="cd2eb-112">Välj en ekonomisk dimension i listan med segment.</span><span class="sxs-lookup"><span data-stu-id="cd2eb-112">In the list of segments, select a financial dimension.</span></span> <span data-ttu-id="cd2eb-113">Till exempel **Butik**.</span><span class="sxs-lookup"><span data-stu-id="cd2eb-113">For example, **Store**.</span></span>  
7. <span data-ttu-id="cd2eb-114">Välj **Lägg till segment**.</span><span class="sxs-lookup"><span data-stu-id="cd2eb-114">Select **Add segment**.</span></span>
8. <span data-ttu-id="cd2eb-115">Välj **aktivera**.</span><span class="sxs-lookup"><span data-stu-id="cd2eb-115">Select **Activate**.</span></span>

## <a name="apply-an-advanced-rule-structure-to-an-account-structure"></a><span data-ttu-id="cd2eb-116">Använd en avancerad regelstruktur för en kontostruktur</span><span class="sxs-lookup"><span data-stu-id="cd2eb-116">Apply an advanced rule structure to an account structure</span></span>
1. <span data-ttu-id="cd2eb-117">Gå till **Navigeringsfönster > Moduler > General ledger > Chart of accounts > Structures > Konfigurera kontostrukturer**.</span><span class="sxs-lookup"><span data-stu-id="cd2eb-117">Go to **navigation pane > Modules > General ledger > Chart of accounts > Structures > Configure account structures**.</span></span>
2. <span data-ttu-id="cd2eb-118">I listan letar du upp och väljer den kontostruktur som du vill tillämpa den avancerade regeln på.</span><span class="sxs-lookup"><span data-stu-id="cd2eb-118">In the list, find and select the account structure you want to apply the advanced rule to.</span></span>
3. <span data-ttu-id="cd2eb-119">Välj **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="cd2eb-119">Select **Edit**.</span></span> <span data-ttu-id="cd2eb-120">Du kan också klicka på **Avancerade regler** så uppmanas du att placera kontostrukturen i **utkastläge**.</span><span class="sxs-lookup"><span data-stu-id="cd2eb-120">You can also select **Advanced rules** and you will be prompted to put the account structure in **Draft mode**.</span></span>  
4. <span data-ttu-id="cd2eb-121">Visa **avancerade regler**.</span><span class="sxs-lookup"><span data-stu-id="cd2eb-121">Select **Advanced rules**.</span></span>
5. <span data-ttu-id="cd2eb-122">Välj **Nytt** om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="cd2eb-122">Select **New** to open the drop dialog.</span></span>
6. <span data-ttu-id="cd2eb-123">Ange ett värde i fältet **Avancerad regel**.</span><span class="sxs-lookup"><span data-stu-id="cd2eb-123">In the **Advanced rule** field, type a value.</span></span>
7. <span data-ttu-id="cd2eb-124">Skriv ett värde i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="cd2eb-124">In the **Name** field, type a value.</span></span>
8. <span data-ttu-id="cd2eb-125">Markera **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="cd2eb-125">Select **Create**.</span></span>
9. <span data-ttu-id="cd2eb-126">Välj **Lägg till nya kriterier**.</span><span class="sxs-lookup"><span data-stu-id="cd2eb-126">Select **Add new criteria**.</span></span>
10. <span data-ttu-id="cd2eb-127">Välj huvudkonto eller en ekonomisk dimension i fältet **Där**.</span><span class="sxs-lookup"><span data-stu-id="cd2eb-127">In the **Where** field, select main account or a financial dimension.</span></span>
11. <span data-ttu-id="cd2eb-128">Välj ett alternativ i fältet **Operator**, t.ex. **är mellan** och **inkluderar**.</span><span class="sxs-lookup"><span data-stu-id="cd2eb-128">In the **Operator** field, select an option, such as **is between** and **includes**.</span></span>
12. <span data-ttu-id="cd2eb-129">Ange ett värde i fältet **Värde**.</span><span class="sxs-lookup"><span data-stu-id="cd2eb-129">In the **Value** field, type a value.</span></span>
13. <span data-ttu-id="cd2eb-130">Skriv ett värde i fältet **via**.</span><span class="sxs-lookup"><span data-stu-id="cd2eb-130">In the **through** field, type a value.</span></span>
14. <span data-ttu-id="cd2eb-131">Välj **Lägg till** för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="cd2eb-131">Select **Add** to open the drop dialog.</span></span>
15. <span data-ttu-id="cd2eb-132">I listan letar du upp den avancerade regelstruktur som du vill använda när de villkor som du angett uppfylls.</span><span class="sxs-lookup"><span data-stu-id="cd2eb-132">In the list, find the advanced rule structure you want to use when the criteria you entered is met.</span></span>
16. <span data-ttu-id="cd2eb-133">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="cd2eb-133">Select **Add**.</span></span>
17. <span data-ttu-id="cd2eb-134">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="cd2eb-134">Close the page.</span></span>
18. <span data-ttu-id="cd2eb-135">Välj **aktivera**.</span><span class="sxs-lookup"><span data-stu-id="cd2eb-135">Select **Activate**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]