---
title: Konfigurera standardkostnader för arbetskraft och utgifter
description: Den här proceduren visar hur du ställer in standardkostnader för arbete och utgifter för ett projekt.
author: KimANelson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjCostPriceHour, ProjSalesPriceHour, ProjCostPriceExpense, ProjSalesPriceCost
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: knelson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f89590c87aec1a7200e95aeac6b2765fc64bb623
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "339405"
---
# <a name="configure-standard-costs-for-labor-and-expenses"></a><span data-ttu-id="51d77-103">Konfigurera standardkostnader för arbetskraft och utgifter</span><span class="sxs-lookup"><span data-stu-id="51d77-103">Configure standard costs for labor and expenses</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="51d77-104">Den här proceduren visar hur du ställer in standardkostnader för arbete och utgifter för ett projekt.</span><span class="sxs-lookup"><span data-stu-id="51d77-104">This procedure shows you how to set up standard costs for labor and expenses for a project.</span></span> <span data-ttu-id="51d77-105">I den här uppgiften används datauppsättningen USSI.</span><span class="sxs-lookup"><span data-stu-id="51d77-105">This task uses the USSI data set.</span></span>

1. <span data-ttu-id="51d77-106">Klicka på Projekthantering och redovisning > Inställningar > Priser > Självkostnadspris (timme).</span><span class="sxs-lookup"><span data-stu-id="51d77-106">Go to Project management and accounting > Setup > Prices > Cost price (hour).</span></span>
2. <span data-ttu-id="51d77-107">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="51d77-107">Click New.</span></span>
3. <span data-ttu-id="51d77-108">Ange ett datum i fältet Giltighetsdatum.</span><span class="sxs-lookup"><span data-stu-id="51d77-108">In the Effective date field, enter a date.</span></span>
4. <span data-ttu-id="51d77-109">Ange ett värde i fältet Cost price.</span><span class="sxs-lookup"><span data-stu-id="51d77-109">In the Cost price field, enter a number.</span></span>
    * <span data-ttu-id="51d77-110">Du kan ställa in ett standardsjälvkostnadspris för projektkategorin, eller också kan du ställa in ett självkostnadspris efter medarbetarnummer, projektnummer, kategori, datum eller någon kombination av dessa.</span><span class="sxs-lookup"><span data-stu-id="51d77-110">You can set up a standard cost price for the project category, or you can set up a cost price by worker number, project number, category, date, or any combination of these.</span></span> <span data-ttu-id="51d77-111">Det självkostnadspris som används är det mest detaljerade.</span><span class="sxs-lookup"><span data-stu-id="51d77-111">The cost price that is applied is the cost price with the highest level of detail.</span></span>  
5. <span data-ttu-id="51d77-112">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="51d77-112">Click Save.</span></span>
6. <span data-ttu-id="51d77-113">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="51d77-113">Close the page.</span></span>
7. <span data-ttu-id="51d77-114">Klicka på Projekthantering och redovisning > Inställningar > Priser > Försäljningspris (timme).</span><span class="sxs-lookup"><span data-stu-id="51d77-114">Go to Project management and accounting > Setup > Prices > Sales price (hour).</span></span>
8. <span data-ttu-id="51d77-115">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="51d77-115">Click New.</span></span>
9. <span data-ttu-id="51d77-116">Ange ett datum i fältet Giltighetsdatum.</span><span class="sxs-lookup"><span data-stu-id="51d77-116">In the Effective date field, enter a date.</span></span>
10. <span data-ttu-id="51d77-117">Välj ett alternativ i fältet Gäller för.</span><span class="sxs-lookup"><span data-stu-id="51d77-117">In the Valid for field, select an option.</span></span>
11. <span data-ttu-id="51d77-118">Ange ett nummer i fältet Pris.</span><span class="sxs-lookup"><span data-stu-id="51d77-118">In the Pricing field, enter a number.</span></span>
    * <span data-ttu-id="51d77-119">Du kan ställa in ett standardförsäljningspris för timtransaktioner eller för en projektkategori.</span><span class="sxs-lookup"><span data-stu-id="51d77-119">You can set up a standard sales price for hour transactions or for a project category.</span></span> <span data-ttu-id="51d77-120">Du kan också ställa in försäljningspriser efter medarbetarnummer, projektnummer, kategori, transaktionsdatum eller valfri kombination av dessa.</span><span class="sxs-lookup"><span data-stu-id="51d77-120">You can also set up sales prices by worker number, project number, category, transaction date, or any combination of these.</span></span> <span data-ttu-id="51d77-121">Det verkliga försäljningspriset, som används när en medarbetare registrerar en transaktion i timjournalen, är försäljningspriset med den högsta detaljnivån.</span><span class="sxs-lookup"><span data-stu-id="51d77-121">The actual sales price, which is applied when a worker enters a transaction in the Hour journal, is the sales price with the highest level of detail.</span></span> <span data-ttu-id="51d77-122">Om till exempel både ett allmänt försäljningspris och ett medarbetarspecifikt försäljningspris har angivits, används automatiskt det medarbetarspecifika försäljningspriset.</span><span class="sxs-lookup"><span data-stu-id="51d77-122">For example, if both a general sales price and a worker-specific sales price are set up, the worker-specific sales price is used.</span></span>  
12. <span data-ttu-id="51d77-123">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="51d77-123">Click Save.</span></span>
13. <span data-ttu-id="51d77-124">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="51d77-124">Close the page.</span></span>
14. <span data-ttu-id="51d77-125">Klicka på Projekthantering och redovisning > Inställningar > Priser > Självkostnadspris (utgift).</span><span class="sxs-lookup"><span data-stu-id="51d77-125">Go to Project management and accounting > Setup > Prices > Cost price (expense).</span></span>
15. <span data-ttu-id="51d77-126">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="51d77-126">Click New.</span></span>
16. <span data-ttu-id="51d77-127">Ange ett datum i fältet Giltighetsdatum.</span><span class="sxs-lookup"><span data-stu-id="51d77-127">In the Effective date field, enter a date.</span></span>
17. <span data-ttu-id="51d77-128">Ange ett värde i fältet Cost price.</span><span class="sxs-lookup"><span data-stu-id="51d77-128">In the Cost price field, enter a number.</span></span>
    * <span data-ttu-id="51d77-129">Flera fält kan fyllas i, men detta är det som krävs för att spara posten.</span><span class="sxs-lookup"><span data-stu-id="51d77-129">Multiple fields can be filled in, but this is the minimum needed to save the record.</span></span>  
18. <span data-ttu-id="51d77-130">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="51d77-130">Click Save.</span></span>
19. <span data-ttu-id="51d77-131">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="51d77-131">Close the page.</span></span>
20. <span data-ttu-id="51d77-132">Gå till Projekthantering och redovisning > Inställningar > Priser > Försäljningspris (utgift).</span><span class="sxs-lookup"><span data-stu-id="51d77-132">Go to Project management and accounting > Setup > Prices > Sales price (expense).</span></span>
21. <span data-ttu-id="51d77-133">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="51d77-133">Click New.</span></span>
22. <span data-ttu-id="51d77-134">Ange ett datum i fältet Giltighetsdatum.</span><span class="sxs-lookup"><span data-stu-id="51d77-134">In the Effective date field, enter a date.</span></span>
23. <span data-ttu-id="51d77-135">Välj ett alternativ i fältet Gäller för.</span><span class="sxs-lookup"><span data-stu-id="51d77-135">In the Valid for field, select an option.</span></span>
24. <span data-ttu-id="51d77-136">Ange ett nummer i fältet Pris.</span><span class="sxs-lookup"><span data-stu-id="51d77-136">In the Pricing field, enter a number.</span></span>
    * <span data-ttu-id="51d77-137">Det verkliga försäljningspriset, som används när en medarbetare registrerar transaktionerna i en utgiftsjournal, är försäljningspriset med den högsta detaljnivån.</span><span class="sxs-lookup"><span data-stu-id="51d77-137">The actual sales price, which is applied when a worker enters transactions in an expense journal, is the sales price with the highest level of detail.</span></span> <span data-ttu-id="51d77-138">Om till exempel både ett allmänt försäljningspris och ett medarbetarspecifikt försäljningspris har angivits, används det medarbetarspecifika försäljningspriset.</span><span class="sxs-lookup"><span data-stu-id="51d77-138">For example, if both a general and a worker-specific sales price are set up, the worker-specific sales price is used.</span></span>  
25. <span data-ttu-id="51d77-139">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="51d77-139">Click Save.</span></span>

