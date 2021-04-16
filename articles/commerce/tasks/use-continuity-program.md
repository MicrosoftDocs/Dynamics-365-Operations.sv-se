---
title: Använda kontinuitetsprogram
description: Denna procedur visar hur du säljer ett kontinuitetsprogram och behandlar relaterade försäljningsordrar.
author: scott-tucker
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: MCRCustomerService, MCRCustSearch, SalesTable, MCRContinuityCustInfo, MCRCustPaymLookup, CreditCardTokenization, CreditCardLookup, MCRSalesOrderRecap
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 58eca42634ad995f174350bc3a1996ddc4c449b9
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5804099"
---
# <a name="using-continuity-program"></a><span data-ttu-id="a5f9d-103">Använda kontinuitetsprogram</span><span class="sxs-lookup"><span data-stu-id="a5f9d-103">Using continuity program</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a5f9d-104">Denna procedur visar hur du säljer ett kontinuitetsprogram och behandlar relaterade försäljningsordrar.</span><span class="sxs-lookup"><span data-stu-id="a5f9d-104">This procedure walks through selling a continuity program and processing related sales orders.</span></span> <span data-ttu-id="a5f9d-105">För att slutföra denna procedur måste användaren konfigureras som en kundtjänstanvändare.</span><span class="sxs-lookup"><span data-stu-id="a5f9d-105">To complete this procedure, the user has to be set up as a call center user.</span></span> <span data-ttu-id="a5f9d-106">I proceduren används demonstrationsföretaget USRT.</span><span class="sxs-lookup"><span data-stu-id="a5f9d-106">This procedure uses the USRT demo data company.</span></span>

1. <span data-ttu-id="a5f9d-107">Gå till Butik och handel > Kunder > Kundtjänst.</span><span class="sxs-lookup"><span data-stu-id="a5f9d-107">Go to Retail and Commerce > Customers > Customer service.</span></span>
2. <span data-ttu-id="a5f9d-108">I det fältet för söktext, ange "Karen" och tryck sedan på Tabb-tangenten.</span><span class="sxs-lookup"><span data-stu-id="a5f9d-108">In the SearchText field, type 'Karen' and then press the Tab key.</span></span>
    * <span data-ttu-id="a5f9d-109">Den avancerade sökningsdialogen bör dyka upp.</span><span class="sxs-lookup"><span data-stu-id="a5f9d-109">The advanced search dialog should pop up.</span></span> <span data-ttu-id="a5f9d-110">Om den inte gör det, klicka då på Search till höger om fältet.</span><span class="sxs-lookup"><span data-stu-id="a5f9d-110">If it doesn't, click Search to the right of this field.</span></span>  
3. <span data-ttu-id="a5f9d-111">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="a5f9d-111">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="a5f9d-112">Det bör bara finnas en rad som anger Karen Berg.</span><span class="sxs-lookup"><span data-stu-id="a5f9d-112">There should be only one row with Karen Berg showing.</span></span> <span data-ttu-id="a5f9d-113">Markera raden genom att klicka på kryssmarkeringskolumnen längst till höger på rutnätet.</span><span class="sxs-lookup"><span data-stu-id="a5f9d-113">Select the row by clicking on the checkmark column on the far left of the grid.</span></span>  
4. <span data-ttu-id="a5f9d-114">Klicka på Välj.</span><span class="sxs-lookup"><span data-stu-id="a5f9d-114">Click Select.</span></span>
5. <span data-ttu-id="a5f9d-115">Klicka på Ny försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="a5f9d-115">Click New sales order.</span></span>
    * <span data-ttu-id="a5f9d-116">Det är god bra idé att notera försäljningsorderns nummer.</span><span class="sxs-lookup"><span data-stu-id="a5f9d-116">It's a good idea to note the sales order number.</span></span> <span data-ttu-id="a5f9d-117">Du kommer att behöva det senare under denna procedur.</span><span class="sxs-lookup"><span data-stu-id="a5f9d-117">You'll need it later in this procedure.</span></span>  
6. <span data-ttu-id="a5f9d-118">I fältet för artikelnummer, ange "88000" och tryck sedan på Tabb-tangenten.</span><span class="sxs-lookup"><span data-stu-id="a5f9d-118">In the Item number field, type '88000' and then press the Tab key.</span></span>
    * <span data-ttu-id="a5f9d-119">Detta är en kontinuitetsartikel i USRT-demonstrationsdatan.</span><span class="sxs-lookup"><span data-stu-id="a5f9d-119">This is a continuity item in the USRT demo data.</span></span>  
7. <span data-ttu-id="a5f9d-120">Klicka på Slutför.</span><span class="sxs-lookup"><span data-stu-id="a5f9d-120">Click Complete.</span></span>
8. <span data-ttu-id="a5f9d-121">I fältet för betalsätt anger du "Visa".</span><span class="sxs-lookup"><span data-stu-id="a5f9d-121">In the Payment method field, enter 'Visa'.</span></span>
9. <span data-ttu-id="a5f9d-122">Klicka på Add credit card.</span><span class="sxs-lookup"><span data-stu-id="a5f9d-122">Click Add credit card.</span></span>
    * <span data-ttu-id="a5f9d-123">Ange den obligatoriska kreditkortsinformationen på denna sida.</span><span class="sxs-lookup"><span data-stu-id="a5f9d-123">Enter the required credit card information on this page.</span></span>  
10. <span data-ttu-id="a5f9d-124">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="a5f9d-124">Click OK.</span></span>
11. <span data-ttu-id="a5f9d-125">Expandera avsnittet Betalning.</span><span class="sxs-lookup"><span data-stu-id="a5f9d-125">Expand the Payment section.</span></span>
    * <span data-ttu-id="a5f9d-126">Om du vill skicka in en kundcenterorder måste betalningar anges för ordern.</span><span class="sxs-lookup"><span data-stu-id="a5f9d-126">To submit a call center order, payments have to be entered for the order.</span></span>  
12. <span data-ttu-id="a5f9d-127">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="a5f9d-127">Click OK.</span></span>
13. <span data-ttu-id="a5f9d-128">Klicka på Skicka.</span><span class="sxs-lookup"><span data-stu-id="a5f9d-128">Click Submit.</span></span>
    * <span data-ttu-id="a5f9d-129">Du har nu skapat en ny kontinuitetsorder.</span><span class="sxs-lookup"><span data-stu-id="a5f9d-129">You're done creating a new continuity order.</span></span> <span data-ttu-id="a5f9d-130">Sedan ska du köra två batchprocesser som används för att processa kontinuitetsordrarna.</span><span class="sxs-lookup"><span data-stu-id="a5f9d-130">Next, you'll run two batch processes that are used to process the continuity orders.</span></span>  
14. <span data-ttu-id="a5f9d-131">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="a5f9d-131">Close the page.</span></span>
15. <span data-ttu-id="a5f9d-132">Gå till Butik och handel > Kontinuitet > Butik och handel.</span><span class="sxs-lookup"><span data-stu-id="a5f9d-132">Go to Retail and Commerce > Continuity > Process continuity payments.</span></span>
16. <span data-ttu-id="a5f9d-133">Ange "88000 "och tryck sedan på Tabb-tangenten i kontinuitetsartikelfältet.</span><span class="sxs-lookup"><span data-stu-id="a5f9d-133">In the Continuity item field, type '88000' and then press the Tab key.</span></span>
17. <span data-ttu-id="a5f9d-134">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="a5f9d-134">Click OK.</span></span>
18. <span data-ttu-id="a5f9d-135">Gå till Butik och handel > Kontinuitet > Skapa underordnade kontinuitetsorder.</span><span class="sxs-lookup"><span data-stu-id="a5f9d-135">Go to Retail and Commerce > Continuity > Create continuity child orders.</span></span>
    * <span data-ttu-id="a5f9d-136">Denna process skapar nya försäljningsordrar som baseras på inställningarna för dina kontinuitetsprogram.</span><span class="sxs-lookup"><span data-stu-id="a5f9d-136">This process will create new sales orders based on the settings of your continuity programs.</span></span>  
19. <span data-ttu-id="a5f9d-137">Ange "88000 "och tryck sedan på Tabb-tangenten i kontinuitetsartikelfältet.</span><span class="sxs-lookup"><span data-stu-id="a5f9d-137">In the Continuity item field, type '88000' and then press the Tab key.</span></span>
    * <span data-ttu-id="a5f9d-138">Artikel "88000" är en kontinuitetsartikel i USRT-demonstrationsdatan.</span><span class="sxs-lookup"><span data-stu-id="a5f9d-138">Item '88000' is a continuity item in the USRT demo data.</span></span>  
20. <span data-ttu-id="a5f9d-139">I fältet Sales order anger eller väljer du ett värde.</span><span class="sxs-lookup"><span data-stu-id="a5f9d-139">In the Sales order field, enter or select a value.</span></span>
    * <span data-ttu-id="a5f9d-140">Ange försäljningsordernummer som du noterade tidigare i proceduren.</span><span class="sxs-lookup"><span data-stu-id="a5f9d-140">Enter the sales order number that you noted earlier in the procedure.</span></span> <span data-ttu-id="a5f9d-141">Detta håller bearbetningstiden till ett minimum för denna procedur.</span><span class="sxs-lookup"><span data-stu-id="a5f9d-141">This will keep the processing time to a minimal for this procedure.</span></span> <span data-ttu-id="a5f9d-142">Fältet för försäljningsorder valfritt ‒ du kan processa alla ordrar för valfritt program.</span><span class="sxs-lookup"><span data-stu-id="a5f9d-142">The Sales order field field is optional--you could process all orders for any one program.</span></span>  
21. <span data-ttu-id="a5f9d-143">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="a5f9d-143">Click OK.</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]