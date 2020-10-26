---
title: Leverera försäljningsorder utan lagerhållning
description: I det här avsnittet handboken visas hur du uppdaterar en försäljningsorder när produkter levereras till kunden.
author: omulvad
manager: tfehr
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesTable, SalesEditLines,  SrsReportViewerForm, SalesTableLineQuantity, CustPackingSlipJournal
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b6b1dbb4d53785c226f7c9d40339d9dd19f47152
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/10/2020
ms.locfileid: "3984164"
---
# <a name="ship-sales-orders-without-warehousing"></a><span data-ttu-id="bae62-103">Leverera försäljningsorder utan lagerhållning</span><span class="sxs-lookup"><span data-stu-id="bae62-103">Ship sales orders without warehousing</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="bae62-104">I det här avsnittet handboken visas hur du uppdaterar en försäljningsorder när produkter levereras till kunden.</span><span class="sxs-lookup"><span data-stu-id="bae62-104">This topic explains how to update a sales order when products are shipped to the customer.</span></span> <span data-ttu-id="bae62-105">Guiden gäller uppfyllelseflödet som inte ställs in för lagerstyrning (varken grundläggande eller avancerad lagerstyrning) och därför inte kräver att produktplockningen ska registreras före leverans.</span><span class="sxs-lookup"><span data-stu-id="bae62-105">The guide is applicable to the fulfillment flow that is not set up for warehouse management (neither basic or advanced warehousing), and therefore does not require product picking to be registered before shipment.</span></span> <span data-ttu-id="bae62-106">Du kan köra den här proceduren med dina egna uppgifter i demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="bae62-106">You can run this procedure on your own data or in demo data company USMF.</span></span> <span data-ttu-id="bae62-107">I båda fallen innan du startar den här uppgiften, skapa en försäljningsorder för inventerad produkt med samma mängd större än 1.</span><span class="sxs-lookup"><span data-stu-id="bae62-107">In both cases, before you start this task, create a sales order for an inventoried product with a quantity of greater than 1.</span></span> <span data-ttu-id="bae62-108">För att undvika bokföringsfelt måste du kontrollera att produktens lagerbehållning på plats och lagerställe som du har valt på ordern omfattar orderkvantiteten.</span><span class="sxs-lookup"><span data-stu-id="bae62-108">To avoid a posting error, you need to check that the product's on-hand quantity in the site and warehouse that you've selected on the order covers the order quantity.</span></span>

## <a name="post-packing-slip-for-an-order"></a><span data-ttu-id="bae62-109">Bokför följesedel för en order</span><span class="sxs-lookup"><span data-stu-id="bae62-109">Post packing slip for an order</span></span>
1. <span data-ttu-id="bae62-110">I navigeringsfönstret, gå till **Moduler > Försäljning och marknadsföring > Försäljningsorder > Alla försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="bae62-110">In the navigation pane, go to **Modules > Sales and marketing > Sales orders > All sales orders**.</span></span>
2. <span data-ttu-id="bae62-111">I listan söker du och väljer den order som du har skapat för uppgiften.</span><span class="sxs-lookup"><span data-stu-id="bae62-111">In the list, find and select the order you have created for this task.</span></span>
3. <span data-ttu-id="bae62-112">I åtgärdsfönstret, klicka **Plocka och packa.**</span><span class="sxs-lookup"><span data-stu-id="bae62-112">On the Action Pane, select **Pick and pack**.</span></span>
4. <span data-ttu-id="bae62-113">Välj **Bokför följesedel**.</span><span class="sxs-lookup"><span data-stu-id="bae62-113">Select **Post packing slip**.</span></span>
5. <span data-ttu-id="bae62-114">Expandera eller komprimera avsnittet **Parametrar.**</span><span class="sxs-lookup"><span data-stu-id="bae62-114">Expand or collapse the **Parameters** section.</span></span>
6. <span data-ttu-id="bae62-115">I fältet **Kvantitet**, välj **Alla**.</span><span class="sxs-lookup"><span data-stu-id="bae62-115">In the **Quantity** field, select **All**.</span></span>
    - <span data-ttu-id="bae62-116">Andra alternativ inkluderar **Leverera nu** och **Plockat**.</span><span class="sxs-lookup"><span data-stu-id="bae62-116">Other options include **Deliver now** and **Picked**.</span></span> <span data-ttu-id="bae62-117">Om orderraden ska levereras delvis och fältet **Leverera nu** på orderraden innehåller en kvantitet ska du välja **Leverera nu**.</span><span class="sxs-lookup"><span data-stu-id="bae62-117">If the order line is to be shipped partially and the **Deliver now** field on the order line contains a quantity, you would select **Deliver now**.</span></span> <span data-ttu-id="bae62-118">Om organisationens uppfyllelseflöde inkluderar plockning som en separat process som administreras av och registreras med en plocklista, ska du välja **Plockat**.</span><span class="sxs-lookup"><span data-stu-id="bae62-118">If your organization's fulfillment flow includes picking as a separate process that is managed by and registered with a picking list, you would select **Picked**.</span></span>  
    - <span data-ttu-id="bae62-119">Kontrollera att alternativet **Bokför** har värdet **Ja**.</span><span class="sxs-lookup"><span data-stu-id="bae62-119">Check that the **Posting** option is set to **Yes**.</span></span>  
7. <span data-ttu-id="bae62-120">Ställ in alternativet **Skriv ut följesedel** på **Ja**.</span><span class="sxs-lookup"><span data-stu-id="bae62-120">Set the **Print packing slip** option to **Yes**.</span></span> <span data-ttu-id="bae62-121">Fliken **Översikt** innehåller en lista med följesedlar som ska genereras i den här bokföringen.</span><span class="sxs-lookup"><span data-stu-id="bae62-121">The **Overview** tab contains a list of packing slips to be generated in this posting.</span></span> <span data-ttu-id="bae62-122">Om du skickar en enskild order, finns det vanligtvis en följesedel.</span><span class="sxs-lookup"><span data-stu-id="bae62-122">If you are shipping an individual order, there will typically be one packing slip.</span></span> <span data-ttu-id="bae62-123">Men om orderns rader ska levereras från olika platser, delas bokföringen automatiskt upp i flera dokument.</span><span class="sxs-lookup"><span data-stu-id="bae62-123">However, if that order's lines are to be shipped from different sites, posting will automatically be split into the appropriate number of documents.</span></span> <span data-ttu-id="bae62-124">Detta är ett obligatoriskt och det går inte att ändra.</span><span class="sxs-lookup"><span data-stu-id="bae62-124">This is a mandatory condition that cannot be changed.</span></span> <span data-ttu-id="bae62-125">På liknande sätt kommer bokföringen också att delas upp i flera dokument om orderns rader ska skickas till olika leveransadresser, och leveransregeln är inställd på att kräva en delning.</span><span class="sxs-lookup"><span data-stu-id="bae62-125">Similarly, the posting will also be split into multiple documents if the order's lines are to be shipped to different delivery addresses, and the shipping policy is set up to require a split.</span></span>  
8. <span data-ttu-id="bae62-126">Markera raden för att orderraden ska skickas på fliken **Rader**.</span><span class="sxs-lookup"><span data-stu-id="bae62-126">On the **Lines** tab, select the row for the order line to be shipped.</span></span>
9. <span data-ttu-id="bae62-127">Ange ett värde som är lägre än den ursprungliga kvantiteten i fältet **Uppdatera**.</span><span class="sxs-lookup"><span data-stu-id="bae62-127">In the **Update** field, enter a number lower than the original quantity.</span></span>
10. <span data-ttu-id="bae62-128">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="bae62-128">Select **OK**.</span></span>
11. <span data-ttu-id="bae62-129">Välj **Ja**.</span><span class="sxs-lookup"><span data-stu-id="bae62-129">Select **Yes**.</span></span>
12. <span data-ttu-id="bae62-130">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="bae62-130">Close the page.</span></span>
13. <span data-ttu-id="bae62-131">Välj **Alternativ** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="bae62-131">On the Action Pane, select **Options**.</span></span>
14. <span data-ttu-id="bae62-132">Välj **Byt visning**.</span><span class="sxs-lookup"><span data-stu-id="bae62-132">Select **Change view**.</span></span>
15. <span data-ttu-id="bae62-133">Välj **Huvudvy**.</span><span class="sxs-lookup"><span data-stu-id="bae62-133">Select **Header view**.</span></span>
    - <span data-ttu-id="bae62-134">Om alla rader på ordern har skickats ändras orderstatusen från Öppen till Levererat.</span><span class="sxs-lookup"><span data-stu-id="bae62-134">If all of the lines on the order have been fully shipped, the order status changes from Open to Delivered.</span></span>  
    - <span data-ttu-id="bae62-135">I det här exemplet har orderraden skickats delvis.</span><span class="sxs-lookup"><span data-stu-id="bae62-135">In this example, the order line has been shipped partially.</span></span> <span data-ttu-id="bae62-136">Därför är orderstatusen fortfarande Öppen.</span><span class="sxs-lookup"><span data-stu-id="bae62-136">This is why the the order status remains Open.</span></span>     
    - <span data-ttu-id="bae62-137">Fältet **Dokumentstatus** har värdet Följesedel eftersom minst en orderrad har skickats.</span><span class="sxs-lookup"><span data-stu-id="bae62-137">The **Document status** field is set to Packing slip because at least one of the order lines have been shipped.</span></span>  
16. <span data-ttu-id="bae62-138">Välj **Allmänt** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="bae62-138">On the Action Pane, select **General**.</span></span>
17. <span data-ttu-id="bae62-139">Välj **Radkvantitet**.</span><span class="sxs-lookup"><span data-stu-id="bae62-139">Select **Line quantity**.</span></span>
18. <span data-ttu-id="bae62-140">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="bae62-140">Close the page.</span></span>
19. <span data-ttu-id="bae62-141">I åtgärdsfönstret, klicka **Plocka och packa.**</span><span class="sxs-lookup"><span data-stu-id="bae62-141">On the Action Pane, select **Pick and pack**.</span></span>
20. <span data-ttu-id="bae62-142">Välj **Följesedel**.</span><span class="sxs-lookup"><span data-stu-id="bae62-142">Select **Packing slip**.</span></span> <span data-ttu-id="bae62-143">Sidan **Följesedelsjournal** innehåller alla följesedlar som har skapats för ordern.</span><span class="sxs-lookup"><span data-stu-id="bae62-143">The **Packing slip journal** page contains all the packing slip documents that were generated for your order.</span></span> <span data-ttu-id="bae62-144">Du kan granska informationen i varje dokument och skriva ut dem om du vill.</span><span class="sxs-lookup"><span data-stu-id="bae62-144">You can review details of each document and print them, if you wish.</span></span>  

