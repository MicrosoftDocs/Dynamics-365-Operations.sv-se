--- 
title: "Konfigurera standardkostnader för arbetskraft och utgifter"
description: "Den här proceduren visar hur du ställer in standardkostnader för arbete och utgifter för ett projekt."
author: KimANelson
manager: AnnBe
ms.date: 02/13/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: knelson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: e4f1981bb35f7740bda6f662fd13f3505d1f8fda
ms.contentlocale: sv-se
ms.lasthandoff: 05/08/2018

---
# <a name="configure-standard-costs-for-labor-and-expenses"></a><span data-ttu-id="c67c6-103">Konfigurera standardkostnader för arbetskraft och utgifter</span><span class="sxs-lookup"><span data-stu-id="c67c6-103">Configure standard costs for labor and expenses</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c67c6-104">Den här proceduren visar hur du ställer in standardkostnader för arbete och utgifter för ett projekt.</span><span class="sxs-lookup"><span data-stu-id="c67c6-104">This procedure shows you how to set up standard costs for labor and expenses for a project.</span></span> <span data-ttu-id="c67c6-105">I den här uppgiften används datauppsättningen USSI.</span><span class="sxs-lookup"><span data-stu-id="c67c6-105">This task uses the USSI data set.</span></span>

1. <span data-ttu-id="c67c6-106">Klicka på Projekthantering och redovisning > Inställningar > Priser > Självkostnadspris (timme).</span><span class="sxs-lookup"><span data-stu-id="c67c6-106">Go to Project management and accounting > Setup > Prices > Cost price (hour).</span></span>
2. <span data-ttu-id="c67c6-107">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="c67c6-107">Click New.</span></span>
3. <span data-ttu-id="c67c6-108">Ange ett datum i fältet Giltighetsdatum.</span><span class="sxs-lookup"><span data-stu-id="c67c6-108">In the Effective date field, enter a date.</span></span>
4. <span data-ttu-id="c67c6-109">Ange ett värde i fältet Cost price.</span><span class="sxs-lookup"><span data-stu-id="c67c6-109">In the Cost price field, enter a number.</span></span>
    * <span data-ttu-id="c67c6-110">Du kan ställa in ett standardsjälvkostnadspris för projektkategorin, eller också kan du ställa in ett självkostnadspris efter medarbetarnummer, projektnummer, kategori, datum eller någon kombination av dessa.</span><span class="sxs-lookup"><span data-stu-id="c67c6-110">You can set up a standard cost price for the project category, or you can set up a cost price by worker number, project number, category, date, or any combination of these.</span></span> <span data-ttu-id="c67c6-111">Det självkostnadspris som används är det mest detaljerade.</span><span class="sxs-lookup"><span data-stu-id="c67c6-111">The cost price that is applied is the cost price with the highest level of detail.</span></span>  
5. <span data-ttu-id="c67c6-112">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="c67c6-112">Click Save.</span></span>
6. <span data-ttu-id="c67c6-113">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="c67c6-113">Close the page.</span></span>
7. <span data-ttu-id="c67c6-114">Klicka på Projekthantering och redovisning > Inställningar > Priser > Försäljningspris (timme).</span><span class="sxs-lookup"><span data-stu-id="c67c6-114">Go to Project management and accounting > Setup > Prices > Sales price (hour).</span></span>
8. <span data-ttu-id="c67c6-115">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="c67c6-115">Click New.</span></span>
9. <span data-ttu-id="c67c6-116">Ange ett datum i fältet Giltighetsdatum.</span><span class="sxs-lookup"><span data-stu-id="c67c6-116">In the Effective date field, enter a date.</span></span>
10. <span data-ttu-id="c67c6-117">Välj ett alternativ i fältet Gäller för.</span><span class="sxs-lookup"><span data-stu-id="c67c6-117">In the Valid for field, select an option.</span></span>
11. <span data-ttu-id="c67c6-118">Ange ett nummer i fältet Pris.</span><span class="sxs-lookup"><span data-stu-id="c67c6-118">In the Pricing field, enter a number.</span></span>
    * <span data-ttu-id="c67c6-119">Du kan ställa in ett standardförsäljningspris för timtransaktioner eller för en projektkategori.</span><span class="sxs-lookup"><span data-stu-id="c67c6-119">You can set up a standard sales price for hour transactions or for a project category.</span></span> <span data-ttu-id="c67c6-120">Du kan också ställa in försäljningspriser efter medarbetarnummer, projektnummer, kategori, transaktionsdatum eller valfri kombination av dessa.</span><span class="sxs-lookup"><span data-stu-id="c67c6-120">You can also set up sales prices by worker number, project number, category, transaction date, or any combination of these.</span></span> <span data-ttu-id="c67c6-121">Det verkliga försäljningspriset, som används när en medarbetare registrerar en transaktion i timjournalen, är försäljningspriset med den högsta detaljnivån.</span><span class="sxs-lookup"><span data-stu-id="c67c6-121">The actual sales price, which is applied when a worker enters a transaction in the Hour journal, is the sales price with the highest level of detail.</span></span> <span data-ttu-id="c67c6-122">Om till exempel både ett allmänt försäljningspris och ett medarbetarspecifikt försäljningspris har angivits, används automatiskt det medarbetarspecifika försäljningspriset.</span><span class="sxs-lookup"><span data-stu-id="c67c6-122">For example, if both a general sales price and a worker-specific sales price are set up, the worker-specific sales price is used.</span></span>  
12. <span data-ttu-id="c67c6-123">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="c67c6-123">Click Save.</span></span>
13. <span data-ttu-id="c67c6-124">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="c67c6-124">Close the page.</span></span>
14. <span data-ttu-id="c67c6-125">Klicka på Projekthantering och redovisning > Inställningar > Priser > Självkostnadspris (utgift).</span><span class="sxs-lookup"><span data-stu-id="c67c6-125">Go to Project management and accounting > Setup > Prices > Cost price (expense).</span></span>
15. <span data-ttu-id="c67c6-126">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="c67c6-126">Click New.</span></span>
16. <span data-ttu-id="c67c6-127">Ange ett datum i fältet Giltighetsdatum.</span><span class="sxs-lookup"><span data-stu-id="c67c6-127">In the Effective date field, enter a date.</span></span>
17. <span data-ttu-id="c67c6-128">Ange ett värde i fältet Cost price.</span><span class="sxs-lookup"><span data-stu-id="c67c6-128">In the Cost price field, enter a number.</span></span>
    * <span data-ttu-id="c67c6-129">Flera fält kan fyllas i, men detta är det som krävs för att spara posten.</span><span class="sxs-lookup"><span data-stu-id="c67c6-129">Multiple fields can be filled in, but this is the minimum needed to save the record.</span></span>  
18. <span data-ttu-id="c67c6-130">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="c67c6-130">Click Save.</span></span>
19. <span data-ttu-id="c67c6-131">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="c67c6-131">Close the page.</span></span>
20. <span data-ttu-id="c67c6-132">Gå till Projekthantering och redovisning > Inställningar > Priser > Försäljningspris (utgift).</span><span class="sxs-lookup"><span data-stu-id="c67c6-132">Go to Project management and accounting > Setup > Prices > Sales price (expense).</span></span>
21. <span data-ttu-id="c67c6-133">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="c67c6-133">Click New.</span></span>
22. <span data-ttu-id="c67c6-134">Ange ett datum i fältet Giltighetsdatum.</span><span class="sxs-lookup"><span data-stu-id="c67c6-134">In the Effective date field, enter a date.</span></span>
23. <span data-ttu-id="c67c6-135">Välj ett alternativ i fältet Gäller för.</span><span class="sxs-lookup"><span data-stu-id="c67c6-135">In the Valid for field, select an option.</span></span>
24. <span data-ttu-id="c67c6-136">Ange ett nummer i fältet Pris.</span><span class="sxs-lookup"><span data-stu-id="c67c6-136">In the Pricing field, enter a number.</span></span>
    * <span data-ttu-id="c67c6-137">Det verkliga försäljningspriset, som används när en medarbetare registrerar transaktionerna i en utgiftsjournal, är försäljningspriset med den högsta detaljnivån.</span><span class="sxs-lookup"><span data-stu-id="c67c6-137">The actual sales price, which is applied when a worker enters transactions in an expense journal, is the sales price with the highest level of detail.</span></span> <span data-ttu-id="c67c6-138">Om till exempel både ett allmänt försäljningspris och ett medarbetarspecifikt försäljningspris har angivits, används det medarbetarspecifika försäljningspriset.</span><span class="sxs-lookup"><span data-stu-id="c67c6-138">For example, if both a general and a worker-specific sales price are set up, the worker-specific sales price is used.</span></span>  
25. <span data-ttu-id="c67c6-139">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="c67c6-139">Click Save.</span></span>


