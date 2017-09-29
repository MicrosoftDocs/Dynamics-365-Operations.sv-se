--- 
title: Skapa ett nytt handelsavtal
description: "I den här proceduren visas hur du skapar ett handelsavtal där du registrerar ett nytt produktförsäljningspris som du har avtalat med en viss kund."
author: omulvad
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 1eb7a945243387f85ec5f38cc3b969d8d030ff25
ms.contentlocale: sv-se
ms.lasthandoff: 08/29/2017

---
# <a name="create-a-new-trade-agreement"></a><span data-ttu-id="a708f-103">Skapa ett nytt handelsavtal</span><span class="sxs-lookup"><span data-stu-id="a708f-103">Create a new trade agreement</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a708f-104">I den här proceduren visas hur du skapar ett handelsavtal där du registrerar ett nytt produktförsäljningspris som du har avtalat med en viss kund.</span><span class="sxs-lookup"><span data-stu-id="a708f-104">This procedure shows you how to create a trade agreement where you register a new product sales price that you've agreed with a specific customer.</span></span> <span data-ttu-id="a708f-105">Du kan köra den här proceduren i demonstrationsföretaget USMF eller på dina egna data.</span><span class="sxs-lookup"><span data-stu-id="a708f-105">You can run this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="a708f-106">Om du använder dina egna data måste du se till att det finns ett namn på handelsavtalsjournalen där standardrelationen har angetts till "Pris (försäljning)" innan du startar den här guiden.</span><span class="sxs-lookup"><span data-stu-id="a708f-106">If you’re using your own data, before you start this guide you need to make sure that a Trade agreement journal name exists where the Default relation is set to “Price (sales)”.</span></span>


## <a name="create-and-post-a-new-trade-agreement-journal"></a><span data-ttu-id="a708f-107">Skapa och bokför en ny handelsavtalsjournal.</span><span class="sxs-lookup"><span data-stu-id="a708f-107">Create and post a new trade agreement journal</span></span>
1. <span data-ttu-id="a708f-108">Gå till försäljning och marknadsföring > Priser och rabatter > Handel journaler.</span><span class="sxs-lookup"><span data-stu-id="a708f-108">Go to Sales and marketing > Prices and discounts > Trade agreement journals.</span></span>
2. <span data-ttu-id="a708f-109">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="a708f-109">Click New.</span></span>
3. <span data-ttu-id="a708f-110">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="a708f-110">In the Name field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="a708f-111">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="a708f-111">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="a708f-112">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="a708f-112">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="a708f-113">Klicka på Rader.</span><span class="sxs-lookup"><span data-stu-id="a708f-113">Click Lines.</span></span>
7. <span data-ttu-id="a708f-114">Välj "Tabell" i fältet Kontokod.</span><span class="sxs-lookup"><span data-stu-id="a708f-114">In the Account code field, select 'Table'.</span></span>
    * <span data-ttu-id="a708f-115">I det här exemplet uppdaterar du priset för en viss kund, vilket innebär att du måste välja Tabell.</span><span class="sxs-lookup"><span data-stu-id="a708f-115">In this example, you're updating the price for a specific customer, which means you need to choose Table.</span></span> <span data-ttu-id="a708f-116">Om du har uppdaterat produktens listpris, du vill markera alla, så att det nya priset är giltigt för alla kunder.</span><span class="sxs-lookup"><span data-stu-id="a708f-116">If you were updating the product's list price, you would select All, so that the new price is valid for all customers.</span></span> <span data-ttu-id="a708f-117">Om du differentiera priser mellan olika kundsegment, då skulle du välja grupp.</span><span class="sxs-lookup"><span data-stu-id="a708f-117">If you were differentiating prices among different customer segments, then you would select Group.</span></span> <span data-ttu-id="a708f-118">Du måste ha ställt in Kundprisgrupper för att välja Grupp.</span><span class="sxs-lookup"><span data-stu-id="a708f-118">To select Group, you must have set up Customer price groups.</span></span>  
8. <span data-ttu-id="a708f-119">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Kontomarkering.</span><span class="sxs-lookup"><span data-stu-id="a708f-119">In the Account selection field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="a708f-120">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="a708f-120">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="a708f-121">Välj "Tabell" i fältet Artikelkod.</span><span class="sxs-lookup"><span data-stu-id="a708f-121">In the Item code field, select 'Table'.</span></span>
    * <span data-ttu-id="a708f-122">När du anger ett handelsavtal av typen "Pris (försäljning)" behöver du bara välja "Tabell" i fältet Artikelkod.</span><span class="sxs-lookup"><span data-stu-id="a708f-122">When you are entering a trade agreement of type 'Price (sales)', you must only select 'Table' in the Item code field.</span></span> <span data-ttu-id="a708f-123">Detta beror på att ett pris är ett absolut värde och kan inte vara samma för alla produkter eller en grupp av produkter.</span><span class="sxs-lookup"><span data-stu-id="a708f-123">This is because a price is an absolute value and cannot be same for all products or a group of products.</span></span>  
11. <span data-ttu-id="a708f-124">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Artikelrelation.</span><span class="sxs-lookup"><span data-stu-id="a708f-124">In the Item relation field, click the drop-down button to open the lookup.</span></span>
12. <span data-ttu-id="a708f-125">I listan väljer du vilken produkt som du vill inkludera i avtalet.</span><span class="sxs-lookup"><span data-stu-id="a708f-125">In the list, select the product you want to include in the agreement.</span></span>
    * <span data-ttu-id="a708f-126">Gör en notering för vilken produkt du har valt.</span><span class="sxs-lookup"><span data-stu-id="a708f-126">Make a note of which product you've selected.</span></span>  
13. <span data-ttu-id="a708f-127">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="a708f-127">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="a708f-128">Ange en minsta kvantitet i fältet Från.</span><span class="sxs-lookup"><span data-stu-id="a708f-128">In the From field, enter a minimum quantity.</span></span>
    * <span data-ttu-id="a708f-129">Om kunden måste beställa en minimikvantitet innan de är berättigade till det nya priset, så måste du ange den kvantiteten här.</span><span class="sxs-lookup"><span data-stu-id="a708f-129">If the customer has to order a minimum quantity  before they can qualify for the new price, then you need to specify that quantity here.</span></span>  
    * <span data-ttu-id="a708f-130">Ange ett värde i fältet Till för att ange den högsta kvantitet över vilken avtalets pris inte kommer att gälla.</span><span class="sxs-lookup"><span data-stu-id="a708f-130">Enter a value in the To field to specify the maximum quantity above which the agreement's price will not be valid.</span></span> <span data-ttu-id="a708f-131">Om du erbjuder priser och rabatter baserat på flera kvantitetsavbrott anger du sedan varje kvantitetshakparentes som ett par av minsta och högsta kvantitet i fälten "Från" respektive "Till".</span><span class="sxs-lookup"><span data-stu-id="a708f-131">If you offer prices and discounts based on multiple quantity breaks, then specify each quantity bracket as a pair of minimum and maximum quantity in the 'From' and 'To' fields respectively.</span></span>  
15. <span data-ttu-id="a708f-132">Ange ett pris i fältet Belopp i valuta.</span><span class="sxs-lookup"><span data-stu-id="a708f-132">In the Amount in currency field, enter a price.</span></span>
16. <span data-ttu-id="a708f-133">Ange ett datum från vilket det här avtalet kommer att gälla i fältet Från.</span><span class="sxs-lookup"><span data-stu-id="a708f-133">In the From date field, enter a date from which this agreement will be valid.</span></span>
17. <span data-ttu-id="a708f-134">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="a708f-134">Click Save.</span></span>
18. <span data-ttu-id="a708f-135">Klicka på Validera.</span><span class="sxs-lookup"><span data-stu-id="a708f-135">Click Validate.</span></span>
19. <span data-ttu-id="a708f-136">Klicka på Validera markerade rader.</span><span class="sxs-lookup"><span data-stu-id="a708f-136">Click Validate selected lines.</span></span>
20. <span data-ttu-id="a708f-137">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="a708f-137">Click OK.</span></span>
21. <span data-ttu-id="a708f-138">Klicka på Bokför.</span><span class="sxs-lookup"><span data-stu-id="a708f-138">Click Post.</span></span>
22. <span data-ttu-id="a708f-139">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="a708f-139">Click OK.</span></span>

## <a name="view-trade-agreements-for-a-product"></a><span data-ttu-id="a708f-140">Visa handelsavtal för en produkt.</span><span class="sxs-lookup"><span data-stu-id="a708f-140">View trade agreements for a product</span></span>
1. <span data-ttu-id="a708f-141">Gå till Produktinformationshantering > Produkter > Frisläppta produkter.</span><span class="sxs-lookup"><span data-stu-id="a708f-141">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="a708f-142">Hitta och markera den produkt vars pris du precis har uppdaterat.</span><span class="sxs-lookup"><span data-stu-id="a708f-142">In the list, find and select the product whose price you have just updated.</span></span>
3. <span data-ttu-id="a708f-143">Klicka på Sälj i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="a708f-143">On the Action Pane, click Sell.</span></span>
4. <span data-ttu-id="a708f-144">Klicka på Visa handelsavtal.</span><span class="sxs-lookup"><span data-stu-id="a708f-144">Click View trade agreements.</span></span>
    * <span data-ttu-id="a708f-145">Granska informationen i prishandelsavtalet som du precis har skapat.</span><span class="sxs-lookup"><span data-stu-id="a708f-145">Review the details of the price trade agreement you have just created.</span></span>    
5. <span data-ttu-id="a708f-146">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="a708f-146">Close the page.</span></span>


