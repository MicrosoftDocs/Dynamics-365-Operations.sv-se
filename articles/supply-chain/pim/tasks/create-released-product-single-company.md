--- 
title: "Skapa en frisläppt produkt för ett enskilt företag"
description: "I den här proceduren beskrivs hur du skapar en enskild frisläppt produkt i sammanhanget för en enskild juridisk enhet."
author: ShylaThompson
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResProductDetailsExtended, EcoResProductCreate, UnitOfMeasureLookup, DimensionLookup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 32d71167fdad65cb1dec37671999a497759ca484
ms.openlocfilehash: cca492bb1083f2520699dd8871a15b10ba3b4e1f
ms.contentlocale: sv-se
ms.lasthandoff: 09/11/2018

---
# <a name="create-a-released-product-for-a-single-company"></a><span data-ttu-id="2ac35-103">Skapa en frisläppt produkt för ett enskilt företag</span><span class="sxs-lookup"><span data-stu-id="2ac35-103">Create a released product for a single company</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="2ac35-104">I den här proceduren beskrivs hur du skapar en enskild frisläppt produkt i sammanhanget för en enskild juridisk enhet.</span><span class="sxs-lookup"><span data-stu-id="2ac35-104">This procedure walks through how to create a single released product in the context of a single legal unit.</span></span> <span data-ttu-id="2ac35-105">När en frisläppt den produkten har skapats, är den endast direkt tillgänglig i den här enheten.</span><span class="sxs-lookup"><span data-stu-id="2ac35-105">After the released product is created,  it's immediately available in this unit only.</span></span> <span data-ttu-id="2ac35-106">Du kan gå igenom den här proceduren i demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="2ac35-106">You can walk through this procedure in demo data company USMF.</span></span> <span data-ttu-id="2ac35-107">Denna uppgift utförs vanligtvis av en produktdesigner.</span><span class="sxs-lookup"><span data-stu-id="2ac35-107">This task is usually performed by a product designer.</span></span>


## <a name="create-a-released-product"></a><span data-ttu-id="2ac35-108">Skapa en frisläppt produkt</span><span class="sxs-lookup"><span data-stu-id="2ac35-108">Create a released product</span></span>
1. <span data-ttu-id="2ac35-109">Gå till Frisläppta produkter.</span><span class="sxs-lookup"><span data-stu-id="2ac35-109">Go to Released products.</span></span>
2. <span data-ttu-id="2ac35-110">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="2ac35-110">Click New.</span></span>
3. <span data-ttu-id="2ac35-111">Skriv ett värde i fältet Produktnummer.</span><span class="sxs-lookup"><span data-stu-id="2ac35-111">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="2ac35-112">Om ett produktnummer inte anges automatiskt i fältet Produktnummer skriver du ett unikt produktnummer.</span><span class="sxs-lookup"><span data-stu-id="2ac35-112">If a product number is not automatically entered in the Product number field, type a unique product number.</span></span> <span data-ttu-id="2ac35-113">Det här steget krävs endast om ingen nummerserie har ställts in för produktnummer.</span><span class="sxs-lookup"><span data-stu-id="2ac35-113">This step is only  required if no number sequence has been set up for product numbers.</span></span>  
4. <span data-ttu-id="2ac35-114">Skriv ett värde i fältet Produktnamn.</span><span class="sxs-lookup"><span data-stu-id="2ac35-114">In the Product name field, type a value.</span></span>
    * <span data-ttu-id="2ac35-115">Produktnamn anges som standard till söknamnet.</span><span class="sxs-lookup"><span data-stu-id="2ac35-115">The Product name is defaulted to the search name.</span></span> <span data-ttu-id="2ac35-116">Du kan välja att ändra söknamnet om det behövs.</span><span class="sxs-lookup"><span data-stu-id="2ac35-116">If needed, you can select to change the search name.</span></span>  
5. <span data-ttu-id="2ac35-117">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Artikelmodellgrupp.</span><span class="sxs-lookup"><span data-stu-id="2ac35-117">In the Item model group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="2ac35-118">Artikelmodellgrupper innehåller inställningar som bestämmer hur artiklar kontrolleras och hanteras för artikelinleveranser och artikelutleveranser.</span><span class="sxs-lookup"><span data-stu-id="2ac35-118">The item model groups contain settings that determine how items are controlled and handled on item receipts and issues.</span></span> <span data-ttu-id="2ac35-119">Inställningarna bestämmer även hur förbrukningen av artiklar beräknas.</span><span class="sxs-lookup"><span data-stu-id="2ac35-119">The settings also determine how the consumption of items are calculated.</span></span>  
6. <span data-ttu-id="2ac35-120">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="2ac35-120">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="2ac35-121">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="2ac35-121">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="2ac35-122">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Artikelgrupp.</span><span class="sxs-lookup"><span data-stu-id="2ac35-122">In the Item group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="2ac35-123">Artikelgrupper används för att hantera lager genom att dela upp lagerartiklar i grupper efter artikelegenskaper.</span><span class="sxs-lookup"><span data-stu-id="2ac35-123">Item groups are used to manage inventory by dividing inventory items into groups based on item characteristics.</span></span> <span data-ttu-id="2ac35-124">Om du till exempel vill hantera hur information bokförs på huvudkontona, kan du skapa en serie olika artikelgrupper som är associerade med specifika huvudkonton.</span><span class="sxs-lookup"><span data-stu-id="2ac35-124">For example, to manage how information is posted to main accounts, you can create a series of different item groups that are associated with specific main accounts.</span></span> <span data-ttu-id="2ac35-125">På så sätt kan du följa lagervärdet för artiklar vid olika faser.</span><span class="sxs-lookup"><span data-stu-id="2ac35-125">This lets you track the inventory value of items at different stages.</span></span>  
9. <span data-ttu-id="2ac35-126">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="2ac35-126">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="2ac35-127">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="2ac35-127">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="2ac35-128">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Lagringsdimensionsgrupp.</span><span class="sxs-lookup"><span data-stu-id="2ac35-128">In the Storage dimension group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="2ac35-129">Lagringsdimensioner bestämmer hur artiklar lagras och tas från lagret.</span><span class="sxs-lookup"><span data-stu-id="2ac35-129">The storage dimensions help you control how items are stored and taken from inventory.</span></span> <span data-ttu-id="2ac35-130">Till exempel kan en lagringsdimension vara webbplats och lagerställe.</span><span class="sxs-lookup"><span data-stu-id="2ac35-130">For example, a storage dimension can be Site and Warehouse.</span></span>  
12. <span data-ttu-id="2ac35-131">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="2ac35-131">In the list, find and select the desired record.</span></span>
13. <span data-ttu-id="2ac35-132">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="2ac35-132">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="2ac35-133">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Spårningsdimensionsgrupp.</span><span class="sxs-lookup"><span data-stu-id="2ac35-133">In the Tracking dimension group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="2ac35-134">Spårningsdimensionsgruppen avgör vilka spårningsdimensioner du kan lägga till för en produkt.</span><span class="sxs-lookup"><span data-stu-id="2ac35-134">The tracking dimension group determines which tracking dimensions you can add to a product.</span></span> <span data-ttu-id="2ac35-135">Batchnummer och serienummer används till exempel för att spåra lagerartiklar.</span><span class="sxs-lookup"><span data-stu-id="2ac35-135">For example, the batch number and serial number are used to track inventory items.</span></span>  
15. <span data-ttu-id="2ac35-136">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="2ac35-136">In the list, find and select the desired record.</span></span>
16. <span data-ttu-id="2ac35-137">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="2ac35-137">In the list, click the link in the selected row.</span></span>
17. <span data-ttu-id="2ac35-138">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Lagerenhet.</span><span class="sxs-lookup"><span data-stu-id="2ac35-138">In the Inventory unit field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="2ac35-139">Lagerenheten bestämmer hur produkten kvantifieras när den sparas i lagret.</span><span class="sxs-lookup"><span data-stu-id="2ac35-139">The inventory unit determines how the product is quantified when it's stored in inventory.</span></span>  
18. <span data-ttu-id="2ac35-140">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="2ac35-140">In the list, find and select the desired record.</span></span>
19. <span data-ttu-id="2ac35-141">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="2ac35-141">In the list, click the link in the selected row.</span></span>
20. <span data-ttu-id="2ac35-142">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Inköpsenhet.</span><span class="sxs-lookup"><span data-stu-id="2ac35-142">In the Purchase unit field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="2ac35-143">Inköpsenheten bestämmer hur produkten kvantifieras när den har köpts från en leverantör.</span><span class="sxs-lookup"><span data-stu-id="2ac35-143">The purchase unit determines how the product is quantified when it’s purchased from a vendor.</span></span>  
21. <span data-ttu-id="2ac35-144">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="2ac35-144">In the list, find and select the desired record.</span></span>
22. <span data-ttu-id="2ac35-145">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="2ac35-145">In the list, click the link in the selected row.</span></span>
23. <span data-ttu-id="2ac35-146">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Försäljningsenhet.</span><span class="sxs-lookup"><span data-stu-id="2ac35-146">In the Sales unit field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="2ac35-147">Försäljningsenheten bestämmer hur produkten kvantifieras när den säljs till en kund.</span><span class="sxs-lookup"><span data-stu-id="2ac35-147">The sales unit determines how the product is quantified when it’s sold to a customer.</span></span>  
24. <span data-ttu-id="2ac35-148">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="2ac35-148">In the list, find and select the desired record.</span></span>
25. <span data-ttu-id="2ac35-149">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="2ac35-149">In the list, click the link in the selected row.</span></span>
26. <span data-ttu-id="2ac35-150">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Strukturlisteenhet.</span><span class="sxs-lookup"><span data-stu-id="2ac35-150">In the BOM unit field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="2ac35-151">Strukturlisteenheten bestämmer hur produkten kvantifieras när du inkluderar den i en strukturlista (BOM).</span><span class="sxs-lookup"><span data-stu-id="2ac35-151">The BOM unit determines how the product is quantified when including it in a bill of materials (BOM).</span></span>  
27. <span data-ttu-id="2ac35-152">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="2ac35-152">In the list, find and select the desired record.</span></span>
28. <span data-ttu-id="2ac35-153">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="2ac35-153">In the list, click the link in the selected row.</span></span>
29. <span data-ttu-id="2ac35-154">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Artikelmomsgrupp.</span><span class="sxs-lookup"><span data-stu-id="2ac35-154">In the Item sales tax group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="2ac35-155">Artikelmomsgruppen i momsbeskattningsgruppen bestämmer hur moms beräknas för varje artikel.</span><span class="sxs-lookup"><span data-stu-id="2ac35-155">The item sales tax group in the Sales taxation group determines how sales tax is calculated for each item.</span></span>  
30. <span data-ttu-id="2ac35-156">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="2ac35-156">In the list, find and select the desired record.</span></span>
31. <span data-ttu-id="2ac35-157">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="2ac35-157">In the list, click the link in the selected row.</span></span>
32. <span data-ttu-id="2ac35-158">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Artikelmomsgrupp.</span><span class="sxs-lookup"><span data-stu-id="2ac35-158">In the Item sales tax group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="2ac35-159">Artikelmomsgruppen i inköpsbeskattningsgruppen bestämmer hur ingående moms beräknas för varje artikel.</span><span class="sxs-lookup"><span data-stu-id="2ac35-159">The item sales tax group in the Purchase taxation group determines how purchase tax is calculated for each item.</span></span>  
33. <span data-ttu-id="2ac35-160">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="2ac35-160">In the list, find and select the desired record.</span></span>
34. <span data-ttu-id="2ac35-161">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="2ac35-161">In the list, click the link in the selected row.</span></span>
35. <span data-ttu-id="2ac35-162">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="2ac35-162">Click OK.</span></span>

## <a name="add-product-characteristics"></a><span data-ttu-id="2ac35-163">Lägga till produktegenskaper</span><span class="sxs-lookup"><span data-stu-id="2ac35-163">Add product characteristics</span></span>
1. <span data-ttu-id="2ac35-164">Visa eller dölj avsnittet Hantera lager.</span><span class="sxs-lookup"><span data-stu-id="2ac35-164">Expand or collapse the Manage inventory section.</span></span>
2. <span data-ttu-id="2ac35-165">Ange ett nummer i fältet Nettovikt.</span><span class="sxs-lookup"><span data-stu-id="2ac35-165">In the Net weight field, enter a number.</span></span>
3. <span data-ttu-id="2ac35-166">Ange ett nummer i fältet Taravikt.</span><span class="sxs-lookup"><span data-stu-id="2ac35-166">In the Tare weight field, enter a number.</span></span>
4. <span data-ttu-id="2ac35-167">Välj ett nummer i fältet Bruttodjup.</span><span class="sxs-lookup"><span data-stu-id="2ac35-167">In the Gross depth field, enter a number.</span></span>
5. <span data-ttu-id="2ac35-168">Välj ett nummer i fältet Bruttobredd.</span><span class="sxs-lookup"><span data-stu-id="2ac35-168">In the Gross width field, enter a number.</span></span>
6. <span data-ttu-id="2ac35-169">Välj ett nummer i fältet Bruttohöjd.</span><span class="sxs-lookup"><span data-stu-id="2ac35-169">In the Gross height field, enter a number.</span></span>
7. <span data-ttu-id="2ac35-170">Välj ett nummer i fältet Volym.</span><span class="sxs-lookup"><span data-stu-id="2ac35-170">In the Volume field, enter a number.</span></span>

## <a name="add-financial-dimensions"></a><span data-ttu-id="2ac35-171">Lägga till ekonomiska dimensioner</span><span class="sxs-lookup"><span data-stu-id="2ac35-171">Add financial dimensions</span></span>
1. <span data-ttu-id="2ac35-172">Expandera eller komprimera avsnittet Ekonomiska dimensioner.</span><span class="sxs-lookup"><span data-stu-id="2ac35-172">Expand or collapse the Financial dimensions section.</span></span>
2. <span data-ttu-id="2ac35-173">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet BusinessUnit.</span><span class="sxs-lookup"><span data-stu-id="2ac35-173">In the BusinessUnit field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="2ac35-174">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="2ac35-174">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="2ac35-175">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="2ac35-175">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="2ac35-176">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet CostCenter.</span><span class="sxs-lookup"><span data-stu-id="2ac35-176">In the CostCenter field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="2ac35-177">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="2ac35-177">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="2ac35-178">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="2ac35-178">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="2ac35-179">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Avdelning.</span><span class="sxs-lookup"><span data-stu-id="2ac35-179">In the Department field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="2ac35-180">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="2ac35-180">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="2ac35-181">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="2ac35-181">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="2ac35-182">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet ItemGroup.</span><span class="sxs-lookup"><span data-stu-id="2ac35-182">In the ItemGroup field, click the drop-down button to open the lookup.</span></span>
12. <span data-ttu-id="2ac35-183">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="2ac35-183">In the list, find and select the desired record.</span></span>
13. <span data-ttu-id="2ac35-184">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="2ac35-184">In the list, click the link in the selected row.</span></span>


