---
title: Konfigurera standardkostnader för arbetskraft och utgifter
description: Det här avsnittet visar hur du ställer in standardkostnader för arbete och utgifter för ett projekt.
author: KimANelson
manager: AnnBe
ms.date: 08/02/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjCostPriceHour, ProjSalesPriceHour, ProjCostPriceExpense, ProjSalesPriceCost
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: knelson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 51bbe52d70bae11cb0c95e9544f951f0fcc605f5
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "3140103"
---
# <a name="configure-standard-costs-for-labor-and-expenses"></a><span data-ttu-id="90730-103">Konfigurera standardkostnader för arbetskraft och utgifter</span><span class="sxs-lookup"><span data-stu-id="90730-103">Configure standard costs for labor and expenses</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="90730-104">Det här avsnittet visar hur du ställer in standardkostnader för arbete och utgifter för ett projekt.</span><span class="sxs-lookup"><span data-stu-id="90730-104">This topic explains how to set up standard costs for labor and expenses for a project.</span></span> <span data-ttu-id="90730-105">I den här uppgiften används datauppsättningen USSI.</span><span class="sxs-lookup"><span data-stu-id="90730-105">This task uses the USSI data set.</span></span>

1. <span data-ttu-id="90730-106">I navigeringsfönstret, gå till **Moduler > Projekthantering och redovisning > Inställningar > Priser > Självkostnad (timme)**.</span><span class="sxs-lookup"><span data-stu-id="90730-106">In the navigation pane, go to **Modules > Project management and accounting > Setup > Prices > Cost price (hour)**.</span></span>
2. <span data-ttu-id="90730-107">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="90730-107">Select **New**.</span></span>
3. <span data-ttu-id="90730-108">Ange ett datum i fältet **Giltighetsdatum**.</span><span class="sxs-lookup"><span data-stu-id="90730-108">In the **Effective date** field, enter a date.</span></span>
4. <span data-ttu-id="90730-109">Ange ett värde i fältet **Självkostnad**.</span><span class="sxs-lookup"><span data-stu-id="90730-109">In the **Cost price** field, enter a number.</span></span> <span data-ttu-id="90730-110">Du kan ställa in ett standardsjälvkostnadspris för projektkategorin, eller också kan du ställa in ett självkostnadspris efter medarbetarnummer, projektnummer, kategori, datum eller någon kombination av dessa.</span><span class="sxs-lookup"><span data-stu-id="90730-110">You can set up a standard cost price for the project category, or you can set up a cost price by worker number, project number, category, date, or any combination of these.</span></span> <span data-ttu-id="90730-111">Det självkostnadspris som används är det mest detaljerade.</span><span class="sxs-lookup"><span data-stu-id="90730-111">The cost price that is applied is the cost price with the highest level of detail.</span></span>  
5. <span data-ttu-id="90730-112">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="90730-112">Select **Save**.</span></span>
6. <span data-ttu-id="90730-113">I navigeringsfönstret, gå till **Moduler > Projekthantering och redovisning > Inställningar > Priser > Försäljningspris (timme)**.</span><span class="sxs-lookup"><span data-stu-id="90730-113">In the navigation pane, go to **Modules > Project management and accounting > Setup > Prices > Sales price (hour)**.</span></span>
7. <span data-ttu-id="90730-114">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="90730-114">Select **New**.</span></span>
8. <span data-ttu-id="90730-115">Ange ett datum i fältet **Giltighetsdatum**.</span><span class="sxs-lookup"><span data-stu-id="90730-115">In the **Effective date** field, enter a date.</span></span>
9. <span data-ttu-id="90730-116">Välj ett alternativ i fältet **Gäller för**.</span><span class="sxs-lookup"><span data-stu-id="90730-116">In the **Valid for** field, select an option.</span></span>
10. <span data-ttu-id="90730-117">Ange ett nummer i fältet **Pris**.</span><span class="sxs-lookup"><span data-stu-id="90730-117">In the **Pricing** field, enter a number.</span></span> <span data-ttu-id="90730-118">Du kan ställa in ett standardförsäljningspris för timtransaktioner eller för en projektkategori.</span><span class="sxs-lookup"><span data-stu-id="90730-118">You can set up a standard sales price for hour transactions or for a project category.</span></span> <span data-ttu-id="90730-119">Du kan också ställa in försäljningspriser efter medarbetarnummer, projektnummer, kategori, transaktionsdatum eller valfri kombination av dessa.</span><span class="sxs-lookup"><span data-stu-id="90730-119">You can also set up sales prices by worker number, project number, category, transaction date, or any combination of these.</span></span> <span data-ttu-id="90730-120">Det verkliga försäljningspriset, som används när en medarbetare registrerar en transaktion i timjournalen, är försäljningspriset med den högsta detaljnivån.</span><span class="sxs-lookup"><span data-stu-id="90730-120">The actual sales price, which is applied when a worker enters a transaction in the Hour journal, is the sales price with the highest level of detail.</span></span> <span data-ttu-id="90730-121">Om till exempel både ett allmänt försäljningspris och ett medarbetarspecifikt försäljningspris har angivits, används automatiskt det medarbetarspecifika försäljningspriset.</span><span class="sxs-lookup"><span data-stu-id="90730-121">For example, if both a general sales price and a worker-specific sales price are set up, the worker-specific sales price is used.</span></span>  
11. <span data-ttu-id="90730-122">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="90730-122">Select **Save**.</span></span>
12. <span data-ttu-id="90730-123">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="90730-123">Close the page.</span></span>
13. <span data-ttu-id="90730-124">I navigeringsfönstret, gå till **Moduler > Projekthantering och redovisning > Inställningar > Priser > Självkostnad (utgift)**.</span><span class="sxs-lookup"><span data-stu-id="90730-124">In the navigation pane, go to **Modules > Project management and accounting > Setup > Prices > Cost price (expense)**.</span></span>
14. <span data-ttu-id="90730-125">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="90730-125">Select **New**.</span></span>
15. <span data-ttu-id="90730-126">Ange ett datum i fältet **Giltighetsdatum**.</span><span class="sxs-lookup"><span data-stu-id="90730-126">In the **Effective date** field, enter a date.</span></span>
16. <span data-ttu-id="90730-127">Ange ett värde i fältet **Självkostnad**.</span><span class="sxs-lookup"><span data-stu-id="90730-127">In the **Cost price** field, enter a number.</span></span> <span data-ttu-id="90730-128">Flera fält kan fyllas i, men detta är det som krävs för att spara posten.</span><span class="sxs-lookup"><span data-stu-id="90730-128">Multiple fields can be filled in, but this is the minimum needed to save the record.</span></span>  
17. <span data-ttu-id="90730-129">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="90730-129">Select **Save**.</span></span>
18. <span data-ttu-id="90730-130">I navigeringsfönstret, gå till **Moduler > Projekthantering och redovisning > Inställningar > Priser > Försäljningspris (utgift)**.</span><span class="sxs-lookup"><span data-stu-id="90730-130">In the navigation pane, go to **Modules > Project management and accounting > Setup > Prices > Sales price (expense)**.</span></span>
19. <span data-ttu-id="90730-131">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="90730-131">Select **New**.</span></span>
20. <span data-ttu-id="90730-132">Ange ett datum i fältet **Giltighetsdatum**.</span><span class="sxs-lookup"><span data-stu-id="90730-132">In the **Effective date** field, enter a date.</span></span>
21. <span data-ttu-id="90730-133">Välj ett alternativ i fältet **Gäller för**.</span><span class="sxs-lookup"><span data-stu-id="90730-133">In the **Valid for** field, select an option.</span></span>
22. <span data-ttu-id="90730-134">Ange ett nummer i fältet **Pris**.</span><span class="sxs-lookup"><span data-stu-id="90730-134">In the **Pricing** field, enter a number.</span></span> <span data-ttu-id="90730-135">Det verkliga försäljningspriset, som används när en medarbetare registrerar transaktionerna i en utgiftsjournal, är försäljningspriset med den högsta detaljnivån.</span><span class="sxs-lookup"><span data-stu-id="90730-135">The actual sales price, which is applied when a worker enters transactions in an expense journal, is the sales price with the highest level of detail.</span></span> <span data-ttu-id="90730-136">Om till exempel både ett allmänt försäljningspris och ett medarbetarspecifikt försäljningspris har angivits, används det medarbetarspecifika försäljningspriset.</span><span class="sxs-lookup"><span data-stu-id="90730-136">For example, if both a general and a worker-specific sales price are set up, the worker-specific sales price is used.</span></span>  
23. <span data-ttu-id="90730-137">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="90730-137">Select **Save**.</span></span>

