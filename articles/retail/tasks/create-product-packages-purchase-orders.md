--- 
title: " Skapa produktförpackningar för inköpsorder"
description: "Den här proceduren går igenom hur du skapar ett produktpaket och använder det i en inköpsorder."
author: josaw1
manager: AnnBe
ms.date: 11/14/2017
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
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: d89744a4dbe52d201dc370b5cde151cc579508ea
ms.contentlocale: sv-se
ms.lasthandoff: 02/07/2018

---
# <a name="create-product-packages-for-purchase-orders"></a><span data-ttu-id="90037-103"> Skapa produktförpackningar för inköpsorder</span><span class="sxs-lookup"><span data-stu-id="90037-103">Create product packages for purchase orders</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="90037-104">Den här proceduren går igenom hur du skapar ett produktpaket och använder det i en inköpsorder.</span><span class="sxs-lookup"><span data-stu-id="90037-104">This procedure walks through creating a product package and using it on a purchase order.</span></span> <span data-ttu-id="90037-105">Inköpsordern ska användas för att skapa en order för en fördefinierad uppsättning av produkter.</span><span class="sxs-lookup"><span data-stu-id="90037-105">The purchase order will be used to create an order for a pre-defined set of products.</span></span> <span data-ttu-id="90037-106">I proceduren används demonstrationsföretaget USRT.</span><span class="sxs-lookup"><span data-stu-id="90037-106">This procedure uses the USRT demo data company.</span></span>


## <a name="create-a-product-package"></a><span data-ttu-id="90037-107">Skapa ett produktpaket</span><span class="sxs-lookup"><span data-stu-id="90037-107">Create a product package</span></span>
1. <span data-ttu-id="90037-108">Gå till butik och handel > lagerhantering > återfyllnad > produktpaket.</span><span class="sxs-lookup"><span data-stu-id="90037-108">Go to Retail and commerce > Inventory management > Replenishment > Product packages.</span></span>
2. <span data-ttu-id="90037-109">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="90037-109">Click New.</span></span>
3. <span data-ttu-id="90037-110">Skriv ett värde i fältet Paketnummer.</span><span class="sxs-lookup"><span data-stu-id="90037-110">In the Package number field, type a value.</span></span>
4. <span data-ttu-id="90037-111">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="90037-111">In the Description field, type a value.</span></span>
5. <span data-ttu-id="90037-112">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Leverantörskonto.</span><span class="sxs-lookup"><span data-stu-id="90037-112">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="90037-113">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="90037-113">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="90037-114">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="90037-114">Click Add.</span></span>
8. <span data-ttu-id="90037-115">Skriv 0160 i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="90037-115">In the Item number field, type '0160'.</span></span>
9. <span data-ttu-id="90037-116">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Storlek.</span><span class="sxs-lookup"><span data-stu-id="90037-116">In the Size field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="90037-117">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="90037-117">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="90037-118">Ange ett tal i fältet Kvantitet.</span><span class="sxs-lookup"><span data-stu-id="90037-118">In the Quantity field, enter a number.</span></span>
12. <span data-ttu-id="90037-119">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="90037-119">Click Add.</span></span>
13. <span data-ttu-id="90037-120">Skriv 0160 i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="90037-120">In the Item number field, type '0160'.</span></span>
14. <span data-ttu-id="90037-121">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Variant number.</span><span class="sxs-lookup"><span data-stu-id="90037-121">In the Variant number field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="90037-122">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="90037-122">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="90037-123">Ange ett tal i fältet Kvantitet.</span><span class="sxs-lookup"><span data-stu-id="90037-123">In the Quantity field, enter a number.</span></span>
17. <span data-ttu-id="90037-124">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="90037-124">Click Add.</span></span>
18. <span data-ttu-id="90037-125">Skriv 0175 i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="90037-125">In the Item number field, type '0175'.</span></span>
19. <span data-ttu-id="90037-126">Ange ett tal i fältet Kvantitet.</span><span class="sxs-lookup"><span data-stu-id="90037-126">In the Quantity field, enter a number.</span></span>
20. <span data-ttu-id="90037-127">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="90037-127">Click Save.</span></span>
21. <span data-ttu-id="90037-128">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="90037-128">Close the page.</span></span>

## <a name="add-package-to-purchase-order"></a><span data-ttu-id="90037-129">Lägg till paket i inköpsorder</span><span class="sxs-lookup"><span data-stu-id="90037-129">Add package to purchase order</span></span>
1. <span data-ttu-id="90037-130">Gå till leverantörsskulder > inköpsorder > Alla inköpsorder.</span><span class="sxs-lookup"><span data-stu-id="90037-130">Go to Accounts payable > Purchase orders > All purchase orders.</span></span>
2. <span data-ttu-id="90037-131">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="90037-131">Click New.</span></span>
3. <span data-ttu-id="90037-132">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Leverantörskonto.</span><span class="sxs-lookup"><span data-stu-id="90037-132">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="90037-133">I listan, välj samma leverantör som produktpaketet har skapats tidigare för om en leverantör valdes.</span><span class="sxs-lookup"><span data-stu-id="90037-133">In the list, select the same vendor that the product package was previously created for, if a vendor was selected.</span></span>
5. <span data-ttu-id="90037-134">Växla utökningen av avsnittet Allmänt.</span><span class="sxs-lookup"><span data-stu-id="90037-134">Toggle the expansion of the General section.</span></span>
6. <span data-ttu-id="90037-135">Öppna sökningen genom att klicka på listruteknappen i fältet Plats.</span><span class="sxs-lookup"><span data-stu-id="90037-135">In the Site field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="90037-136">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="90037-136">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="90037-137">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Lagerställe.</span><span class="sxs-lookup"><span data-stu-id="90037-137">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="90037-138">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="90037-138">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="90037-139">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="90037-139">Click OK.</span></span>
11. <span data-ttu-id="90037-140">Växla expanderingen av avsnittet Raddetaljer.</span><span class="sxs-lookup"><span data-stu-id="90037-140">Toggle the expansion of the Line details section.</span></span>
12. <span data-ttu-id="90037-141">Klicka på fliken Produktpaket.</span><span class="sxs-lookup"><span data-stu-id="90037-141">Click the Product packages tab.</span></span>
13. <span data-ttu-id="90037-142">Klicka på Inköpsorderrad.</span><span class="sxs-lookup"><span data-stu-id="90037-142">Click Purchase order line.</span></span>
14. <span data-ttu-id="90037-143">Klicka på Skapa rader från paket.</span><span class="sxs-lookup"><span data-stu-id="90037-143">Click Create lines from package.</span></span>
15. <span data-ttu-id="90037-144">I listan, sök efter och välj produktpaketet som skapas i föregående steg.</span><span class="sxs-lookup"><span data-stu-id="90037-144">In the list, find and select the product package created in previous step.</span></span>
16. <span data-ttu-id="90037-145">Ange ett nummer i fältet Kvantitet.</span><span class="sxs-lookup"><span data-stu-id="90037-145">In the Quantity field, enter a number.</span></span>
17. <span data-ttu-id="90037-146">Klicka på Skapa.</span><span class="sxs-lookup"><span data-stu-id="90037-146">Click Create.</span></span>
18. <span data-ttu-id="90037-147">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="90037-147">Click Save.</span></span>


