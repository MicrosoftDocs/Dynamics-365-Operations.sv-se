---
title: Godkänn leverantörer för specifika produkter
description: I den här proceduren visas hur du godkänner leverantörer för specifika produkter.
author: RichardLuan
manager: tfehr
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, PdsApprovedVendorList, VendTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d08791caba34908903ce330df0f91e44fbdfcaea
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5237285"
---
# <a name="approve-vendors-for-specific-products"></a><span data-ttu-id="74b55-103">Godkänn leverantörer för specifika produkter</span><span class="sxs-lookup"><span data-stu-id="74b55-103">Approve vendors for specific products</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="74b55-104">I den här proceduren visas hur du godkänner leverantörer för specifika produkter.</span><span class="sxs-lookup"><span data-stu-id="74b55-104">This procedure shows you how to approve vendors for specific products.</span></span> <span data-ttu-id="74b55-105">På så sätt kan du kontrollera vilka leverantörer som kan användas när produkten läggs till en inköpsorder.</span><span class="sxs-lookup"><span data-stu-id="74b55-105">This allows you to control which vendors can be used when the product is added to a purchase order.</span></span> <span data-ttu-id="74b55-106">Du kan använda den här proceduren i demonstrationsföretaget USMF eller med dina egna data.</span><span class="sxs-lookup"><span data-stu-id="74b55-106">You can use this procedure in demo data company USMF, or on your own data.</span></span> <span data-ttu-id="74b55-107">Uppgiften utförs vanligtvis av en inköpschef.</span><span class="sxs-lookup"><span data-stu-id="74b55-107">This task would typically be carried out by a Purchasing manager.</span></span>

1. <span data-ttu-id="74b55-108">I navigeringsfönstret, gå till **Moduler > Produktinformationshantering > Produkter > Frisläppta produkter**.</span><span class="sxs-lookup"><span data-stu-id="74b55-108">In Navigation Pane, go to **Modules > Product information management > Products > Released products**.</span></span>
2. <span data-ttu-id="74b55-109">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="74b55-109">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="74b55-110">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="74b55-110">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="74b55-111">Expandera snabbfliken **Inköp**.</span><span class="sxs-lookup"><span data-stu-id="74b55-111">Expand the **Purchase** fastTab.</span></span> <span data-ttu-id="74b55-112">Om det visas en primär leverantör som i fältet **Leverantör** måste du lägga till den här leverantören som en godkänd leverantör på följande sätt.</span><span class="sxs-lookup"><span data-stu-id="74b55-112">If there is a primary vendor shown in the **Vendor** field, then you need to add this vendor as an approved vendor in the following steps.</span></span> <span data-ttu-id="74b55-113">Gör en notering av leverantörnumret om ett sådant visas.</span><span class="sxs-lookup"><span data-stu-id="74b55-113">Make a note of the vendor number, if one is shown.</span></span>  
5. <span data-ttu-id="74b55-114">I åtgärdsrutan, klicka på **Köp**.</span><span class="sxs-lookup"><span data-stu-id="74b55-114">On the Action Pane, click **Purchase**.</span></span>
6. <span data-ttu-id="74b55-115">Klicka på **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="74b55-115">Click **Setup**.</span></span>
7. <span data-ttu-id="74b55-116">Klicka på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="74b55-116">Click **Add**.</span></span>
8. <span data-ttu-id="74b55-117">Ange eller välj ett värde i fältet Leverantör.</span><span class="sxs-lookup"><span data-stu-id="74b55-117">In the Vendor field, enter or select a value.</span></span> <span data-ttu-id="74b55-118">Välj godkänd leverantör.</span><span class="sxs-lookup"><span data-stu-id="74b55-118">Select the approved vendor.</span></span> <span data-ttu-id="74b55-119">Minst en av raderna måste vara primär leverantör, om det finns en i produktposten.</span><span class="sxs-lookup"><span data-stu-id="74b55-119">At least one of the lines has to be the primary vendor if there was one in the product record.</span></span> <span data-ttu-id="74b55-120">Om du gjorde en notering av leverantörsnumret tidigare, väljer du den här.</span><span class="sxs-lookup"><span data-stu-id="74b55-120">If you made a note of the vendor number earlier, select it here.</span></span>  
9. <span data-ttu-id="74b55-121">I fältet **Utgång** anger du ett datum.</span><span class="sxs-lookup"><span data-stu-id="74b55-121">In the **Expiration** field, enter a date.</span></span> <span data-ttu-id="74b55-122">Välj ett datum som infaller alla månader framåt.</span><span class="sxs-lookup"><span data-stu-id="74b55-122">Choose a date a that is a few months ahead.</span></span>  
10. <span data-ttu-id="74b55-123">Klicka på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="74b55-123">Click **Add**.</span></span>
11. <span data-ttu-id="74b55-124">Ange eller välj ett värde i fältet **Leverantör**.</span><span class="sxs-lookup"><span data-stu-id="74b55-124">In the **Vendor** field, enter or select a value.</span></span>
12. <span data-ttu-id="74b55-125">I fältet **Utgång** anger du ett datum.</span><span class="sxs-lookup"><span data-stu-id="74b55-125">In the **Expiration** field, enter a date.</span></span> <span data-ttu-id="74b55-126">Välj ett datum som är annorlunda än det föregående utgångsdatumet.</span><span class="sxs-lookup"><span data-stu-id="74b55-126">Choose a date that is different than the previous expiration date.</span></span>  
13. <span data-ttu-id="74b55-127">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="74b55-127">Close the page.</span></span>
14. <span data-ttu-id="74b55-128">Klicka på **Godkända leverantörer** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="74b55-128">On the Action Pane, click **Approved vendors**.</span></span>
15. <span data-ttu-id="74b55-129">I fältet **Utgång** anger du ett datum.</span><span class="sxs-lookup"><span data-stu-id="74b55-129">In the **Expiration** field, enter a date.</span></span> <span data-ttu-id="74b55-130">Detta datum fungerar som ett filter så att du kan se vilka som är godkända leverantörer, fram till ett visst datum.</span><span class="sxs-lookup"><span data-stu-id="74b55-130">This date acts as a filter so you can see who the approved vendors are, up to a certain date.</span></span>  
16. <span data-ttu-id="74b55-131">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="74b55-131">Close the page.</span></span>
17. <span data-ttu-id="74b55-132">Klicka på **Giltighetstid** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="74b55-132">On the Action Pane, click **Effective period**.</span></span>
18. <span data-ttu-id="74b55-133">Ange ett datum i fältet **Visa leverantörer som upphör den**.</span><span class="sxs-lookup"><span data-stu-id="74b55-133">In the **Show vendors expired by** field, enter a date.</span></span> <span data-ttu-id="74b55-134">Du kan använda den här sidan för att identifiera leverantörer där godkännande upphör att gälla efter ett visst datum.</span><span class="sxs-lookup"><span data-stu-id="74b55-134">You can use this page to identify vendors where the approval status will expire after a certain date.</span></span>  
19. <span data-ttu-id="74b55-135">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="74b55-135">Close the page.</span></span>
20. <span data-ttu-id="74b55-136">Klicka på **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="74b55-136">Click **Edit**.</span></span>
21. <span data-ttu-id="74b55-137">Välj ett alternativ i fältet **Kontrollmetod för godkänd leverantör**.</span><span class="sxs-lookup"><span data-stu-id="74b55-137">In the **Approved vendor check method** field, select an option.</span></span> <span data-ttu-id="74b55-138">I det här fältet kan du välja policyn för vad som ska hända om produkten läggs till i en inköpsorderrad där leverantören inte är en godkänd leverantör.</span><span class="sxs-lookup"><span data-stu-id="74b55-138">This field allows you to select the policy for what should happen if the product is added to a purchase order line where the vendor is not an approved vendor.</span></span>  
22. <span data-ttu-id="74b55-139">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="74b55-139">Click **Save**.</span></span>
23. <span data-ttu-id="74b55-140">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="74b55-140">Close the page.</span></span>
24. <span data-ttu-id="74b55-141">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="74b55-141">Close the page.</span></span>
25. <span data-ttu-id="74b55-142">I navigeringsfönstret, gå till **Moduler > Leverantörer > Leverantör/artikelrelationer > Godkänd leverantörslista per artikel**.</span><span class="sxs-lookup"><span data-stu-id="74b55-142">In Navigation Pane, go to **Modules > Procurement and sourcing > Vendors > Vendor/item relations > Approved vendor list by item**.</span></span> <span data-ttu-id="74b55-143">På den här sidan finns en översikt över alla produkter och godkända leverantörer.</span><span class="sxs-lookup"><span data-stu-id="74b55-143">This page gives you an overview of all products and the approved vendors.</span></span>  
26. <span data-ttu-id="74b55-144">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="74b55-144">Close the page.</span></span>
27. <span data-ttu-id="74b55-145">I navigeringsfönstret, gå till **Moduler > Anskaffning och källa > Leverantörer > Alla leverantörer**.</span><span class="sxs-lookup"><span data-stu-id="74b55-145">In Navigation Pane, go to **Modules > Procurement and sourcing > Vendors > All vendors**.</span></span> <span data-ttu-id="74b55-146">Du kan också starta från en leverantör och sedan gå till listan över godkända produkter för det leverantörskontot.</span><span class="sxs-lookup"><span data-stu-id="74b55-146">You can also start from a vendor and then go to the list of approved products for that vendor account.</span></span>  
28. <span data-ttu-id="74b55-147">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="74b55-147">In the list, find and select the desired record.</span></span>
29. <span data-ttu-id="74b55-148">Klicka på **Anskaffning** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="74b55-148">On the Action Pane, click **Procurement**.</span></span>
30. <span data-ttu-id="74b55-149">Klicka på **Godkänd leverantörslista per leverantör**.</span><span class="sxs-lookup"><span data-stu-id="74b55-149">Click **Approved vendor list by vendor**.</span></span>
31. <span data-ttu-id="74b55-150">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="74b55-150">Close the page.</span></span>
32. <span data-ttu-id="74b55-151">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="74b55-151">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]