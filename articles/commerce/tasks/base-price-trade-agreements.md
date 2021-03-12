---
title: " Baspris och handelsavtal"
description: Den här proceduren går igenom hur du skapar kanalspecifika handelsavtal för försäljningspriset.
author: josaw1
manager: AnnBe
ms.date: 08/12/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PriceDiscGroup, RetailStoreTable, RetailChannelPriceGroup, EcoResProductDetailsExtended, PriceDiscAdmTable, PriceDiscAdm
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: db3a91807c0cfb51426c03eeaf7785168e6ad0de
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "5006068"
---
# <a name="base-price-and-trade-agreements"></a><span data-ttu-id="4fbd6-103"> Baspris och handelsavtal</span><span class="sxs-lookup"><span data-stu-id="4fbd6-103">Base price and trade agreements</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4fbd6-104">Den här proceduren går igenom hur du skapar kanalspecifika handelsavtal för försäljningspriset.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-104">This procedure walks through creating channel-specific sales price trade agreements.</span></span> <span data-ttu-id="4fbd6-105">I proceduren används demonstrationsföretaget USRT.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-105">This procedure uses the USRT demo data company.</span></span>

1. <span data-ttu-id="4fbd6-106">I **Navigeringsfönstret** går du till **Moduler > Butik och handel > Hantering av priser och rabatter > Prisgrupper > Alla prisgrupper**.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-106">In the **Navigation pane**, go to **Modules > Retail and Commerce > Pricing and discounts management > Price groups > All price groups**.</span></span> <span data-ttu-id="4fbd6-107">Prisgrupper hur handelsavtal tilldelas specifika kanaler.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-107">Price groups are how trade agreements are assigned to specific channels.</span></span> <span data-ttu-id="4fbd6-108">Användningen av prisgrupperna för att tilldela handelsavtal till en kanal aktiverar kanalspecifik prissättning.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-108">Using price groups to assign trade agreements to a channel enables channel-specific pricing.</span></span>  
2. <span data-ttu-id="4fbd6-109">Klicka på **Ny**.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-109">Click **New**.</span></span>
3. <span data-ttu-id="4fbd6-110">Ange ett värde i fältet **Prisgrupper**.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-110">In the **Price groups** field, type a value.</span></span>
4. <span data-ttu-id="4fbd6-111">Skriv ett värde i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-111">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="4fbd6-112">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-112">Click **Save**.</span></span>
6. <span data-ttu-id="4fbd6-113">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-113">Close the page.</span></span>
7. <span data-ttu-id="4fbd6-114">I **Navigeringsfönstret**, gå till **Moduler > Butik och handel > Kanaler > Butiker > Alla butiker**.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-114">In the **Navigation pane**, go to **Modules > Retail and Commerce > Channels > Stores > All stores**.</span></span>
8. <span data-ttu-id="4fbd6-115">Välj New York i listan.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-115">In the list, select 'New York'</span></span>
9. <span data-ttu-id="4fbd6-116">Klicka på **Butik** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-116">On the Action Pane, click **Store**.</span></span>
10. <span data-ttu-id="4fbd6-117">Klicka på **Prisgrupper**.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-117">Click **Price groups**.</span></span>
11. <span data-ttu-id="4fbd6-118">Klicka på **Ny**.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-118">Click **New**.</span></span>
12. <span data-ttu-id="4fbd6-119">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Prisgrupper**.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-119">In the **Price groups** field, click the drop-down button to open the lookup.</span></span>
13. <span data-ttu-id="4fbd6-120">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-120">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="4fbd6-121">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-121">Click **Save**.</span></span>
15. <span data-ttu-id="4fbd6-122">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-122">Close the page.</span></span>
16. <span data-ttu-id="4fbd6-123">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-123">Close the page.</span></span>
17. <span data-ttu-id="4fbd6-124">I **Navigeringsfönstret**, gå till **Moduler > Butik och handel > Produkter och kategorier > Frisläppta produkter per kategori**.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-124">In the **Navigation pane**, go to **Modules > Retail and Commerce > Products and categories > Released products by category**.</span></span>
18. <span data-ttu-id="4fbd6-125">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-125">In the list, click the link in the selected row.</span></span>
19. <span data-ttu-id="4fbd6-126">Klicka på **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-126">Click **Edit**.</span></span>
20. <span data-ttu-id="4fbd6-127">Expandera snabbfliken **Sälj**.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-127">Expand the **Sell** fastTab.</span></span>
21. <span data-ttu-id="4fbd6-128">Ange ett tal i fältet **Pris**.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-128">In the **Price** field, enter a number.</span></span> <span data-ttu-id="4fbd6-129">Detta pris används om inget tillämpligt handelsavtal hittas.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-129">This price is used if no applicable trade agreements are found.</span></span>  
22. <span data-ttu-id="4fbd6-130">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-130">Click **Save**.</span></span>
23. <span data-ttu-id="4fbd6-131">Klicka på **Sälj** i **åtgärdsfönstret**.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-131">On the **Action Pane**, click **Sell**.</span></span>
24. <span data-ttu-id="4fbd6-132">Klicka på **Skapa handelsavtal**.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-132">Click **Create trade agreements**.</span></span>
25. <span data-ttu-id="4fbd6-133">Klicka på **Ny**.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-133">Click **New**.</span></span>
26. <span data-ttu-id="4fbd6-134">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-134">In the **Name** field, click the drop-down button to open the lookup.</span></span>
27. <span data-ttu-id="4fbd6-135">I listan välj raden **Commerce**.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-135">In the list, select **Commerce**.</span></span> <span data-ttu-id="4fbd6-136">I demonstrationsdata har journalnamnet **Commerce** standardrelationen **Pris (Försäljning)**.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-136">In the demo data, the **Commerce** journal name has the default relation of **Price (sales)**.</span></span> <span data-ttu-id="4fbd6-137">Det innebär att alla skapade nya rader får standardinställningen handelsavtal för försäljningspriset.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-137">That means all new lines created will default to sales price trade agreements.</span></span>  
28. <span data-ttu-id="4fbd6-138">Klicka på **Rader** i **åtgärdsfönstret**.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-138">On the **Action pane**, click **Lines**.</span></span>
29. <span data-ttu-id="4fbd6-139">I fältet **Partkodtyp** välj Grupp.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-139">In the **Party code type** field, select 'Group'.</span></span>
30. <span data-ttu-id="4fbd6-140">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Kontomarkering**.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-140">In the **Account selection** field, click the drop-down button to open the lookup.</span></span>
31. <span data-ttu-id="4fbd6-141">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-141">In the list, find and select the desired record.</span></span> <span data-ttu-id="4fbd6-142">Detta slutför länken från Kanal till Prisgrupp till Commercesavtal.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-142">This will complete the link from Channel to Price group to Trade agreement.</span></span>  
32. <span data-ttu-id="4fbd6-143">Skriv ett värde i fältet **Artikelrelation**.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-143">In the **Item relation** field, type a value.</span></span>
33. <span data-ttu-id="4fbd6-144">Ange ett nummer i fältet **Belopp i valuta**.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-144">In the **Amount in currency** field, enter a number.</span></span>
34. <span data-ttu-id="4fbd6-145">På snabbfliken **Detaljer**, markera eller avmarkera kryssrutan **Sök nästa**.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-145">In the **Details** fastTab, check or uncheck the **Find next** checkbox.</span></span> <span data-ttu-id="4fbd6-146">När **Sök nästa** sedan anges till Ja, prissättningsmotorn ska fortsätta att söka efter tillämpliga handelsavtal med ett lägre försäljningspris.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-146">When **Find next** is set to 'Yes', the pricing engine will continue to search for applicable trade agreements with a lower sale price.</span></span> <span data-ttu-id="4fbd6-147">När **Sök nästa** anges till Nej slutar prismotorn söka och använder handelsavtalet.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-147">When **Find next** is set to 'No', the price engine stops searching and uses the trade agreement.</span></span>  
35. <span data-ttu-id="4fbd6-148">Klicka på **Bokför**.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-148">Click **Post**.</span></span>
36. <span data-ttu-id="4fbd6-149">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-149">Click **OK**.</span></span>
37. <span data-ttu-id="4fbd6-150">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-150">Close the page.</span></span>
38. <span data-ttu-id="4fbd6-151">Klicka på Sälj i **åtgärdsfönstret**.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-151">On the **Action Pane**, click Sell.</span></span>
39. <span data-ttu-id="4fbd6-152">Klicka på **Försäljningspris**.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-152">Click **Sales price**.</span></span>

