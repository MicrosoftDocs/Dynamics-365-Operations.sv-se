--- 
title: " Använd ett kontinuitetsprogram"
description: "Denna procedur visar hur du säljer ett kontinuitetsprogram och behandlar relaterade försäljningsordrar."
author: scott-tucker
manager: AnnBe
ms.date: 11/14/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: d9b080ff46a0fbc73ed4f8fa3f03d71e9d758cc2
ms.openlocfilehash: 111aa3c653f7733031e7c43a52a33ad9219530c5
ms.contentlocale: sv-se
ms.lasthandoff: 01/18/2018

---
# <a name="use-a-continuity-program"></a><span data-ttu-id="542d8-103"> Använd ett kontinuitetsprogram</span><span class="sxs-lookup"><span data-stu-id="542d8-103">Use a continuity program</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="542d8-104">Denna procedur visar hur du säljer ett kontinuitetsprogram och behandlar relaterade försäljningsordrar.</span><span class="sxs-lookup"><span data-stu-id="542d8-104">This procedure walks through selling a continuity program and processing related sales orders.</span></span> <span data-ttu-id="542d8-105">För att slutföra denna procedur måste användaren konfigureras som en kundtjänstanvändare.</span><span class="sxs-lookup"><span data-stu-id="542d8-105">To complete this procedure, the user has to be set up as a call center user.</span></span> <span data-ttu-id="542d8-106">I proceduren används demonstrationsföretaget USRT.</span><span class="sxs-lookup"><span data-stu-id="542d8-106">This procedure uses the USRT demo data company.</span></span>

1. <span data-ttu-id="542d8-107">Gå till Butik och handel > Kunder > Kundtjänst.</span><span class="sxs-lookup"><span data-stu-id="542d8-107">Go to Retail and commerce > Customers > Customer service.</span></span>
2. <span data-ttu-id="542d8-108">I det fältet för söktext, ange "Karen" och tryck sedan på Tabb-tangenten.</span><span class="sxs-lookup"><span data-stu-id="542d8-108">In the SearchText field, type 'Karen' and then press the Tab key.</span></span>
    * <span data-ttu-id="542d8-109">Den avancerade sökningsdialogen bör dyka upp.</span><span class="sxs-lookup"><span data-stu-id="542d8-109">The advanced search dialog should pop up.</span></span> <span data-ttu-id="542d8-110">Om den inte gör det, klicka då på Search till höger om fältet.</span><span class="sxs-lookup"><span data-stu-id="542d8-110">If it doesn't, click Search to the right of this field.</span></span>  
3. <span data-ttu-id="542d8-111">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="542d8-111">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="542d8-112">Det bör bara finnas en rad som anger Karen Berg.</span><span class="sxs-lookup"><span data-stu-id="542d8-112">There should be only one row with Karen Berg showing.</span></span> <span data-ttu-id="542d8-113">Markera raden genom att klicka på kryssmarkeringskolumnen längst till höger på rutnätet.</span><span class="sxs-lookup"><span data-stu-id="542d8-113">Select the row by clicking on the checkmark column on the far left of the grid.</span></span>  
4. <span data-ttu-id="542d8-114">Klicka på Välj.</span><span class="sxs-lookup"><span data-stu-id="542d8-114">Click Select.</span></span>
5. <span data-ttu-id="542d8-115">Klicka på Ny försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="542d8-115">Click New sales order.</span></span>
    * <span data-ttu-id="542d8-116">Det är god bra idé att notera försäljningsorderns nummer.</span><span class="sxs-lookup"><span data-stu-id="542d8-116">It's a good idea to note the sales order number.</span></span> <span data-ttu-id="542d8-117">Du kommer att behöva det senare under denna procedur.</span><span class="sxs-lookup"><span data-stu-id="542d8-117">You'll need it later in this procedure.</span></span>  
6. <span data-ttu-id="542d8-118">I fältet för artikelnummer, ange "88000" och tryck sedan på Tabb-tangenten.</span><span class="sxs-lookup"><span data-stu-id="542d8-118">In the Item number field, type '88000' and then press the Tab key.</span></span>
    * <span data-ttu-id="542d8-119">Detta är en kontinuitetsartikel i USRT-demonstrationsdatan.</span><span class="sxs-lookup"><span data-stu-id="542d8-119">This is a continuity item in the USRT demo data.</span></span>  
7. <span data-ttu-id="542d8-120">Klicka på Slutför.</span><span class="sxs-lookup"><span data-stu-id="542d8-120">Click Complete.</span></span>
8. <span data-ttu-id="542d8-121">I fältet för betalsätt anger du "Visa".</span><span class="sxs-lookup"><span data-stu-id="542d8-121">In the Payment method field, enter 'Visa'.</span></span>
9. <span data-ttu-id="542d8-122">Klicka på Add credit card.</span><span class="sxs-lookup"><span data-stu-id="542d8-122">Click Add credit card.</span></span>
    * <span data-ttu-id="542d8-123">Ange den obligatoriska kreditkortsinformationen på denna sida.</span><span class="sxs-lookup"><span data-stu-id="542d8-123">Enter the required credit card information on this page.</span></span>  
10. <span data-ttu-id="542d8-124">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="542d8-124">Click OK.</span></span>
11. <span data-ttu-id="542d8-125">Expandera avsnittet Betalning.</span><span class="sxs-lookup"><span data-stu-id="542d8-125">Expand the Payment section.</span></span>
    * <span data-ttu-id="542d8-126">Om du vill skicka in en kundcenterorder måste betalningar anges för ordern.</span><span class="sxs-lookup"><span data-stu-id="542d8-126">To submit a call center order, payments have to be entered for the order.</span></span>  
12. <span data-ttu-id="542d8-127">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="542d8-127">Click OK.</span></span>
13. <span data-ttu-id="542d8-128">Klicka på Skicka.</span><span class="sxs-lookup"><span data-stu-id="542d8-128">Click Submit.</span></span>
    * <span data-ttu-id="542d8-129">Du har nu skapat en ny kontinuitetsorder.</span><span class="sxs-lookup"><span data-stu-id="542d8-129">You're done creating a new continuity order.</span></span> <span data-ttu-id="542d8-130">Sedan ska du köra två batchprocesser som används för att processa kontinuitetsordrarna.</span><span class="sxs-lookup"><span data-stu-id="542d8-130">Next, you'll run two batch processes that are used to process the continuity orders.</span></span>  
14. <span data-ttu-id="542d8-131">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="542d8-131">Close the page.</span></span>
15. <span data-ttu-id="542d8-132">Gå till Retail and commerce > Continuity > Process continuity payments.</span><span class="sxs-lookup"><span data-stu-id="542d8-132">Go to Retail and commerce > Continuity > Process continuity payments.</span></span>
16. <span data-ttu-id="542d8-133">Ange "88000 "och tryck sedan på Tabb-tangenten i kontinuitetsartikelfältet.</span><span class="sxs-lookup"><span data-stu-id="542d8-133">In the Continuity item field, type '88000' and then press the Tab key.</span></span>
17. <span data-ttu-id="542d8-134">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="542d8-134">Click OK.</span></span>
18. <span data-ttu-id="542d8-135">Gå till Retail and commerce > Continuity > Create continuity child orders.</span><span class="sxs-lookup"><span data-stu-id="542d8-135">Go to Retail and commerce > Continuity > Create continuity child orders.</span></span>
    * <span data-ttu-id="542d8-136">Denna process skapar nya försäljningsordrar som baseras på inställningarna för dina kontinuitetsprogram.</span><span class="sxs-lookup"><span data-stu-id="542d8-136">This process will create new sales orders based on the settings of your continuity programs.</span></span>  
19. <span data-ttu-id="542d8-137">Ange "88000 "och tryck sedan på Tabb-tangenten i kontinuitetsartikelfältet.</span><span class="sxs-lookup"><span data-stu-id="542d8-137">In the Continuity item field, type '88000' and then press the Tab key.</span></span>
    * <span data-ttu-id="542d8-138">Artikel "88000" är en kontinuitetsartikel i USRT-demonstrationsdatan.</span><span class="sxs-lookup"><span data-stu-id="542d8-138">Item '88000' is a continuity item in the USRT demo data.</span></span>  
20. <span data-ttu-id="542d8-139">I fältet Sales order anger eller väljer du ett värde.</span><span class="sxs-lookup"><span data-stu-id="542d8-139">In the Sales order field, enter or select a value.</span></span>
    * <span data-ttu-id="542d8-140">Ange försäljningsordernummer som du noterade tidigare i proceduren.</span><span class="sxs-lookup"><span data-stu-id="542d8-140">Enter the sales order number that you noted earlier in the procedure.</span></span> <span data-ttu-id="542d8-141">Detta håller bearbetningstiden till ett minimum för denna procedur.</span><span class="sxs-lookup"><span data-stu-id="542d8-141">This will keep the processing time to a minimal for this procedure.</span></span> <span data-ttu-id="542d8-142">Fältet för försäljningsorder valfritt ‒ du kan processa alla ordrar för valfritt program.</span><span class="sxs-lookup"><span data-stu-id="542d8-142">The Sales order field is optional--you could process all orders for any one program.</span></span>  
21. <span data-ttu-id="542d8-143">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="542d8-143">Click OK.</span></span>


