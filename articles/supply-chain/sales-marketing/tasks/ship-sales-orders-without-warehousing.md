---
title: Leverera försäljningsorder utan lagerstyrning
description: I den här handboken visas hur du uppdaterar en försäljningsorder när produkter skickas till kunden.
author: omulvad
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesTable, SalesEditLines,  SrsReportViewerForm, SalesTableLineQuantity, CustPackingSlipJournal
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 62bbd65e2d80dca5a07b761e1aa76f1894b667c1
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2019
ms.locfileid: "1843326"
---
# <a name="ship-sales-orders-without-warehousing"></a><span data-ttu-id="a232b-103">Leverera försäljningsorder utan lagerstyrning</span><span class="sxs-lookup"><span data-stu-id="a232b-103">Ship sales orders without warehousing</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a232b-104">I den här handboken visas hur du uppdaterar en försäljningsorder när produkter skickas till kunden.</span><span class="sxs-lookup"><span data-stu-id="a232b-104">This guide demonstrates how to update a sales order when products are shipped to the customer.</span></span> <span data-ttu-id="a232b-105">Guiden gäller uppfyllelseflödet som inte ställs in för lagerstyrning (varken grundläggande eller avancerad lagerstyrning) och därför inte kräver att produktplockningen ska registreras före leverans.</span><span class="sxs-lookup"><span data-stu-id="a232b-105">The guide is applicable to the fulfillment flow that is not set up for warehouse management (neither basic or advanced warehousing), and therefore does not require product picking to be registered before shipment.</span></span> <span data-ttu-id="a232b-106">Du kan köra den här proceduren med dina egna uppgifter i demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="a232b-106">You can run this procedure on your own data or in demo data company USMF.</span></span> <span data-ttu-id="a232b-107">I båda fallen innan du startar den här uppgiften, skapa en försäljningsorder för inventerad produkt med samma mängd större än 1.</span><span class="sxs-lookup"><span data-stu-id="a232b-107">In both cases, before you start this task, create a sales order for an inventoried product with a quantity of greater than 1.</span></span> <span data-ttu-id="a232b-108">För att undvika bokföringsfelt måste du kontrollera att produktens lagerbehållning på plats och lagerställe som du har valt på ordern omfattar orderkvantiteten.</span><span class="sxs-lookup"><span data-stu-id="a232b-108">To avoid a posting error, you need to check that the product's on-hand quantity in the site and warehouse that you’ve selected on the order covers the order quantity.</span></span>


## <a name="post-packing-slip-for-an-order"></a><span data-ttu-id="a232b-109">Bokför följesedel för en order</span><span class="sxs-lookup"><span data-stu-id="a232b-109">Post packing slip for an order</span></span>
1. <span data-ttu-id="a232b-110">Gå till försäljning och marknadsföring > beställningar > Alla beställningar.</span><span class="sxs-lookup"><span data-stu-id="a232b-110">Go to Sales and marketing > Sales orders > All sales orders.</span></span>
2. <span data-ttu-id="a232b-111">I listan söker du och väljer den order som du har skapat för uppgiften.</span><span class="sxs-lookup"><span data-stu-id="a232b-111">In the list, find and select the order you have created for this task.</span></span>
3. <span data-ttu-id="a232b-112">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="a232b-112">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="a232b-113">Klicka på Plocka och packa i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="a232b-113">On the Action Pane, click Pick and pack.</span></span>
5. <span data-ttu-id="a232b-114">Klicka på Bokför följesedel.</span><span class="sxs-lookup"><span data-stu-id="a232b-114">Click Post packing slip.</span></span>
6. <span data-ttu-id="a232b-115">Utöka eller komprimera avsnittet Parametrar.</span><span class="sxs-lookup"><span data-stu-id="a232b-115">Expand or collapse the Parameters section.</span></span>
7. <span data-ttu-id="a232b-116">Välj Alla i fältet Kvantitet.</span><span class="sxs-lookup"><span data-stu-id="a232b-116">In the Quantity field, select 'All'.</span></span>
    * <span data-ttu-id="a232b-117">Andra alternativ inkluderar Leverera nu och Plockat.</span><span class="sxs-lookup"><span data-stu-id="a232b-117">Other options include Deliver now and Picked.</span></span> <span data-ttu-id="a232b-118">Om orderraden ska levereras delvis och fältet Leverera nu på orderraden innehållen en kvantitet ska du välja Leverera nu.</span><span class="sxs-lookup"><span data-stu-id="a232b-118">If the order line is to be shipped partially and the Deliver now field on the order line contains a quantity, you would select Deliver now.</span></span> <span data-ttu-id="a232b-119">Om organisationens uppfyllelseflöde inkluderar plockning som en separat process som administreras av och registreras med en plocklista, ska du välja Plockat.</span><span class="sxs-lookup"><span data-stu-id="a232b-119">If your organization's fulfillment flow includes picking as a separate process that is managed by and registered with a picking list, you would select Picked.</span></span>  
    * <span data-ttu-id="a232b-120">Kontrollera att alternativet Bokför har värdet Ja.</span><span class="sxs-lookup"><span data-stu-id="a232b-120">Check that the Posting option is set to Yes.</span></span>  
8. <span data-ttu-id="a232b-121">Ställ in alternativet Skriv ut följesedel på Ja.</span><span class="sxs-lookup"><span data-stu-id="a232b-121">Set the Print packing slip option to Yes.</span></span>
    * <span data-ttu-id="a232b-122">Fliken Översikt innehåller en lista med följesedlar som ska genereras i den här bokföringen.</span><span class="sxs-lookup"><span data-stu-id="a232b-122">The Overview tab contains a list of packing slips to be generated in this posting.</span></span> <span data-ttu-id="a232b-123">Om du skickar en enskild order, finns det vanligtvis en följesedel.</span><span class="sxs-lookup"><span data-stu-id="a232b-123">If you are shipping an individual order, there will typically be one packing slip.</span></span> <span data-ttu-id="a232b-124">Men om orderns rader ska levereras från olika platser, delas bokföringen automatiskt upp i flera dokument.</span><span class="sxs-lookup"><span data-stu-id="a232b-124">However, if that order's lines are to be shipped from different sites, posting will automatically be split into the appropriate number of documents.</span></span> <span data-ttu-id="a232b-125">Detta är ett obligatoriskt och det går inte att ändra.</span><span class="sxs-lookup"><span data-stu-id="a232b-125">This is a mandatory condition that cannot be changed.</span></span> <span data-ttu-id="a232b-126">På liknande sätt kommer bokföringen också att delas upp i flera dokument om orderns rader ska skickas till olika leveransadresser, och leveransregeln är inställd på att kräva en delning.</span><span class="sxs-lookup"><span data-stu-id="a232b-126">Similarly, the posting will also be split into multiple documents if the order’s lines are to be shipped to different delivery addresses, and the shipping policy is set up to require a split.</span></span>  
9. <span data-ttu-id="a232b-127">Markera raden för att orderraden ska skickas på fliken Rader.</span><span class="sxs-lookup"><span data-stu-id="a232b-127">On the Lines tab, select the row for the order line to be shipped.</span></span>
10. <span data-ttu-id="a232b-128">Ange ett värde som är lägre än den ursprungliga kvantiteten i fältet Uppdatera.</span><span class="sxs-lookup"><span data-stu-id="a232b-128">In the Update field, enter a number lower than the original quantity.</span></span>
11. <span data-ttu-id="a232b-129">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="a232b-129">Click OK.</span></span>
12. <span data-ttu-id="a232b-130">Klicka på Ja.</span><span class="sxs-lookup"><span data-stu-id="a232b-130">Click Yes.</span></span>
13. <span data-ttu-id="a232b-131">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="a232b-131">Close the page.</span></span>
14. <span data-ttu-id="a232b-132">Klicka på Alternativ i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="a232b-132">On the Action Pane, click Options.</span></span>
15. <span data-ttu-id="a232b-133">Klicka på Ändra vy.</span><span class="sxs-lookup"><span data-stu-id="a232b-133">Click Change view.</span></span>
16. <span data-ttu-id="a232b-134">Klicka på Huvudvy.</span><span class="sxs-lookup"><span data-stu-id="a232b-134">Click Header view.</span></span>
    * <span data-ttu-id="a232b-135">Om alla rader på ordern har skickats ändras orderstatusen från Öppen till Levererat.</span><span class="sxs-lookup"><span data-stu-id="a232b-135">If all of the lines on the order have been fully shipped, the order status changes from Open to Delivered.</span></span>  
    * <span data-ttu-id="a232b-136">I det här exemplet har orderraden skickats delvis.</span><span class="sxs-lookup"><span data-stu-id="a232b-136">In this example, the order line has been shipped partially.</span></span> <span data-ttu-id="a232b-137">Därför är orderstatusen fortfarande Öppen.</span><span class="sxs-lookup"><span data-stu-id="a232b-137">This is why the the order status remains Open.</span></span>     
    * <span data-ttu-id="a232b-138">Dokumentstatusfältet har värdet Följesedel eftersom minst en orderrad har skickats.</span><span class="sxs-lookup"><span data-stu-id="a232b-138">The Document status field is set to Packing slip because at least one of the order lines have been shipped.</span></span>  
17. <span data-ttu-id="a232b-139">Klicka på Allmänt i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="a232b-139">On the Action Pane, click General.</span></span>
18. <span data-ttu-id="a232b-140">Klicka på Radkvantitet.</span><span class="sxs-lookup"><span data-stu-id="a232b-140">Click Line quantity.</span></span>
19. <span data-ttu-id="a232b-141">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="a232b-141">Close the page.</span></span>
20. <span data-ttu-id="a232b-142">Klicka på Plocka och packa i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="a232b-142">On the Action Pane, click Pick and pack.</span></span>
21. <span data-ttu-id="a232b-143">Klicka på Följesedel.</span><span class="sxs-lookup"><span data-stu-id="a232b-143">Click Packing slip.</span></span>
    * <span data-ttu-id="a232b-144">Sidan Följesedelsjournal innehåller alla följesedlar som har skapats för ordern.</span><span class="sxs-lookup"><span data-stu-id="a232b-144">The Packing slip journal page contains all the packing slip documents that were generated for your order.</span></span> <span data-ttu-id="a232b-145">Du kan granska informationen i varje dokument och skriva ut dem om du vill.</span><span class="sxs-lookup"><span data-stu-id="a232b-145">You can review details of each document and print them, if you wish.</span></span>  

