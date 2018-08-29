--- 
title: Skapa kanalspecifika handelsavtal
description: "Den här proceduren går igenom hur du skapar kanalspecifika handelsavtal för försäljningspriset."
author: josaw1
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 5098fb3339403b6f2779dfe3bb7ef5c4ca78051f
ms.openlocfilehash: 4cc797d2e23f0c7b14564415de6153ac0894c727
ms.contentlocale: sv-se
ms.lasthandoff: 08/09/2018

---
# <a name="create-channel-specific-trade-agreements"></a><span data-ttu-id="5b0b4-103">Skapa kanalspecifika handelsavtal</span><span class="sxs-lookup"><span data-stu-id="5b0b4-103">Create channel-specific trade agreements</span></span>

[!include [task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="5b0b4-104">Den här proceduren går igenom hur du skapar kanalspecifika handelsavtal för försäljningspriset.</span><span class="sxs-lookup"><span data-stu-id="5b0b4-104">This procedure walks through creating channel-specific sales price trade agreements.</span></span> <span data-ttu-id="5b0b4-105">I proceduren används demonstrationsföretaget USRT.</span><span class="sxs-lookup"><span data-stu-id="5b0b4-105">This procedure uses the USRT demo data company.</span></span>

1. <span data-ttu-id="5b0b4-106">Gå till butik och handel > prissättning och rabatter > prisgrupper > alla prisgrupper.</span><span class="sxs-lookup"><span data-stu-id="5b0b4-106">Go to Retail and commerce > Pricing and discounts > Price groups > All price groups.</span></span>
    * <span data-ttu-id="5b0b4-107">Prisgrupper hur handelsavtal tilldelas specifika kanaler.</span><span class="sxs-lookup"><span data-stu-id="5b0b4-107">Price groups are how trade agreements are assigned to specific channels.</span></span> <span data-ttu-id="5b0b4-108">Användningen av prisgrupperna för att tilldela handelsavtal till en kanal aktiverar kanalspecifik prissättning.</span><span class="sxs-lookup"><span data-stu-id="5b0b4-108">Using price groups to assign trade agreements to a channel enables channel-specific pricing.</span></span>  
2. <span data-ttu-id="5b0b4-109">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="5b0b4-109">Click New.</span></span>
3. <span data-ttu-id="5b0b4-110">Ange ett värde i fältet Prisgrupper.</span><span class="sxs-lookup"><span data-stu-id="5b0b4-110">In the Price groups field, type a value.</span></span>
4. <span data-ttu-id="5b0b4-111">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="5b0b4-111">In the Name field, type a value.</span></span>
5. <span data-ttu-id="5b0b4-112">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="5b0b4-112">Click Save.</span></span>
6. <span data-ttu-id="5b0b4-113">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="5b0b4-113">Close the page.</span></span>
7. <span data-ttu-id="5b0b4-114">Gå till butik och handel > Kanaler > butiker > Alla butiker.</span><span class="sxs-lookup"><span data-stu-id="5b0b4-114">Go to Retail and commerce > Channels > Retail stores > All retail stores.</span></span>
8. <span data-ttu-id="5b0b4-115">Välj New York i listan.</span><span class="sxs-lookup"><span data-stu-id="5b0b4-115">In the list, select 'New York'</span></span>
9. <span data-ttu-id="5b0b4-116">Klicka på Butik i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="5b0b4-116">On the Action Pane, click Store.</span></span>
10. <span data-ttu-id="5b0b4-117">Klicka på Prisgrupper.</span><span class="sxs-lookup"><span data-stu-id="5b0b4-117">Click Price groups.</span></span>
11. <span data-ttu-id="5b0b4-118">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="5b0b4-118">Click New.</span></span>
12. <span data-ttu-id="5b0b4-119">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Prisgrupper.</span><span class="sxs-lookup"><span data-stu-id="5b0b4-119">In the Price groups field, click the drop-down button to open the lookup.</span></span>
13. <span data-ttu-id="5b0b4-120">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="5b0b4-120">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="5b0b4-121">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="5b0b4-121">Click Save.</span></span>
15. <span data-ttu-id="5b0b4-122">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="5b0b4-122">Close the page.</span></span>
16. <span data-ttu-id="5b0b4-123">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="5b0b4-123">Close the page.</span></span>
17. <span data-ttu-id="5b0b4-124">Gå till butik och handel > Produkter och kategorier > Frisläppta produkter per kategori.</span><span class="sxs-lookup"><span data-stu-id="5b0b4-124">Go to Retail and commerce > Products and categories > Released products by category.</span></span>
18. <span data-ttu-id="5b0b4-125">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="5b0b4-125">In the list, click the link in the selected row.</span></span>
19. <span data-ttu-id="5b0b4-126">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="5b0b4-126">Click Edit.</span></span>
20. <span data-ttu-id="5b0b4-127">Växla utökningen av avsnittet Sälj.</span><span class="sxs-lookup"><span data-stu-id="5b0b4-127">Toggle the expansion of the Sell section.</span></span>
21. <span data-ttu-id="5b0b4-128">Ange ett tal i fältet Pris.</span><span class="sxs-lookup"><span data-stu-id="5b0b4-128">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="5b0b4-129">Detta pris används om inget tillämpligt handelsavtal hittas.</span><span class="sxs-lookup"><span data-stu-id="5b0b4-129">This price is used if no applicable trade agreements are found.</span></span>  
22. <span data-ttu-id="5b0b4-130">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="5b0b4-130">Click Save.</span></span>
23. <span data-ttu-id="5b0b4-131">Klicka på Sälj i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="5b0b4-131">On the Action Pane, click Sell.</span></span>
24. <span data-ttu-id="5b0b4-132">Klicka på Skapa handelsavtal.</span><span class="sxs-lookup"><span data-stu-id="5b0b4-132">Click Create trade agreements.</span></span>
25. <span data-ttu-id="5b0b4-133">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="5b0b4-133">Click New.</span></span>
26. <span data-ttu-id="5b0b4-134">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="5b0b4-134">In the Name field, click the drop-down button to open the lookup.</span></span>
27. <span data-ttu-id="5b0b4-135">I listan väljer du Butik .</span><span class="sxs-lookup"><span data-stu-id="5b0b4-135">In the list, select 'Retail'.</span></span>
    * <span data-ttu-id="5b0b4-136">I demonstrationsdata har journalnamnet Butik standardrelationen Pris (Försäljning).</span><span class="sxs-lookup"><span data-stu-id="5b0b4-136">In the demo data, the 'Retail' journal name has the default relation of 'Price (sales)'.</span></span> <span data-ttu-id="5b0b4-137">Det innebär att alla skapade nya rader får standardinställningen handelsavtal för försäljningspriset.</span><span class="sxs-lookup"><span data-stu-id="5b0b4-137">That means all new lines created will default to sales price trade agreements.</span></span>  
28. <span data-ttu-id="5b0b4-138">Klicka på Rader.</span><span class="sxs-lookup"><span data-stu-id="5b0b4-138">Click Lines.</span></span>
29. <span data-ttu-id="5b0b4-139">Välj Grupp i fältet Konto.</span><span class="sxs-lookup"><span data-stu-id="5b0b4-139">In the Account code field, select 'Group'.</span></span>
30. <span data-ttu-id="5b0b4-140">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Kontomarkering.</span><span class="sxs-lookup"><span data-stu-id="5b0b4-140">In the Account selection field, click the drop-down button to open the lookup.</span></span>
31. <span data-ttu-id="5b0b4-141">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="5b0b4-141">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="5b0b4-142">Detta slutför länken från Kanal till Prisgrupp till Handelsavtal.</span><span class="sxs-lookup"><span data-stu-id="5b0b4-142">This will complete the link from Channel to Price group to Trade agreement.</span></span>  
32. <span data-ttu-id="5b0b4-143">Skriv ett värde i fältet Artikelrelation.</span><span class="sxs-lookup"><span data-stu-id="5b0b4-143">In the Item relation field, type a value.</span></span>
33. <span data-ttu-id="5b0b4-144">Ange ett nummer i fältet Belopp i valuta.</span><span class="sxs-lookup"><span data-stu-id="5b0b4-144">In the Amount in currency field, enter a number.</span></span>
34. <span data-ttu-id="5b0b4-145">Markera eller avmarkera kryssrutan Sök nästa.</span><span class="sxs-lookup"><span data-stu-id="5b0b4-145">Check or uncheck the Find next checkbox.</span></span>
    * <span data-ttu-id="5b0b4-146">När Sök nästa sedan anges till Ja, prissättningsmotorn ska fortsätta att söka efter tillämpliga handelsavtal med ett lägre försäljningspris.</span><span class="sxs-lookup"><span data-stu-id="5b0b4-146">When Find next is set to 'Yes', the pricing engine will continue to search for applicable trade agreements with a lower sale price.</span></span> <span data-ttu-id="5b0b4-147">När Sök nästa anges till Nej slutar prismotorn söka och använder handelsavtalet.</span><span class="sxs-lookup"><span data-stu-id="5b0b4-147">When Find next is set to 'No', the price engine stops searching and uses the trade agreement.</span></span>  
35. <span data-ttu-id="5b0b4-148">Klicka på Bokför.</span><span class="sxs-lookup"><span data-stu-id="5b0b4-148">Click Post.</span></span>
36. <span data-ttu-id="5b0b4-149">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="5b0b4-149">Click OK.</span></span>
37. <span data-ttu-id="5b0b4-150">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="5b0b4-150">Close the page.</span></span>
38. <span data-ttu-id="5b0b4-151">Klicka på Sälj i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="5b0b4-151">On the Action Pane, click Sell.</span></span>
39. <span data-ttu-id="5b0b4-152">Klicka på Försäljningspris.</span><span class="sxs-lookup"><span data-stu-id="5b0b4-152">Click Sales price.</span></span>


