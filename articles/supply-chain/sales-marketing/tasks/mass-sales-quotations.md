---
title: Masskapa försäljningsofferter
description: I den här proceduren visas hur du skapar offerter med en uppsättning produkter eller tjänster som ska skickas till flera kunder.
author: omulvad
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SalesQuotationTemplateGroup, SalesQuotationListPage, SalesCreateQuotation, SalesQuotationTable, SysQueryForm, SalesQuickQuote
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0422817576d9d93d0ec6bbfb5f3777013ee09ece
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5817711"
---
# <a name="mass-create-sales-quotations"></a><span data-ttu-id="2a80a-103">Masskapa försäljningsofferter</span><span class="sxs-lookup"><span data-stu-id="2a80a-103">Mass create sales quotations</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="2a80a-104">I den här proceduren visas hur du skapar offerter med en uppsättning produkter eller tjänster som ska skickas till flera kunder.</span><span class="sxs-lookup"><span data-stu-id="2a80a-104">This procedure demonstrates how to efficiently create quotations offering a set of products or services that are to be sent to multiple customers.</span></span> <span data-ttu-id="2a80a-105">Den här genereringen av massofferter baseras på offertmallar.</span><span class="sxs-lookup"><span data-stu-id="2a80a-105">This mass quotation creation is based on quotation templates.</span></span> <span data-ttu-id="2a80a-106">Du kan köra den här proceduren med dina egna uppgifter i demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="2a80a-106">You can run this procedure on your own data or in demo data company USMF.</span></span>


## <a name="create-a-quotation-template"></a><span data-ttu-id="2a80a-107">Skapa en offertmall</span><span class="sxs-lookup"><span data-stu-id="2a80a-107">Create a quotation template</span></span>
1. <span data-ttu-id="2a80a-108">Gå till försäljning och marknadsföring > Installation > offerter > Template Groups.</span><span class="sxs-lookup"><span data-stu-id="2a80a-108">Go to Sales and marketing > Setup > Quotations > Template groups.</span></span>
2. <span data-ttu-id="2a80a-109">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="2a80a-109">Click New.</span></span>
3. <span data-ttu-id="2a80a-110">Ange ett id i fältet Grupp-ID.</span><span class="sxs-lookup"><span data-stu-id="2a80a-110">In the Group ID field, type an ID of your choice.</span></span>
4. <span data-ttu-id="2a80a-111">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="2a80a-111">In the Description field, type a value.</span></span>
5. <span data-ttu-id="2a80a-112">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="2a80a-112">Click Save.</span></span>
6. <span data-ttu-id="2a80a-113">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="2a80a-113">Close the page.</span></span>
7. <span data-ttu-id="2a80a-114">Gå till försäljning och marknadsföring > offerter > Alla offerter.</span><span class="sxs-lookup"><span data-stu-id="2a80a-114">Go to Sales and marketing > Sales quotations > All quotations.</span></span>
8. <span data-ttu-id="2a80a-115">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="2a80a-115">Click New.</span></span>
9. <span data-ttu-id="2a80a-116">I fältet Kontotyp väljer du "Kund".</span><span class="sxs-lookup"><span data-stu-id="2a80a-116">In the Account type field, select 'Customer'.</span></span>
10. <span data-ttu-id="2a80a-117">I fältet Kundkonto, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="2a80a-117">In the Customer account field, enter or select a value.</span></span>
11. <span data-ttu-id="2a80a-118">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="2a80a-118">Click OK.</span></span>
    * <span data-ttu-id="2a80a-119">För att en offert ska kunna bli en mall, måste du utföra inställningssteg i offerthuvudet.</span><span class="sxs-lookup"><span data-stu-id="2a80a-119">For a quotation to become a template you must carry out  setup steps on the quotation header.</span></span> <span data-ttu-id="2a80a-120">Detta måste göras innan du lägger till rader i offerten.</span><span class="sxs-lookup"><span data-stu-id="2a80a-120">This must be done before you add lines to the quotation.</span></span>   
12. <span data-ttu-id="2a80a-121">Klicka på Alternativ i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="2a80a-121">On the Action Pane, click Options.</span></span>
13. <span data-ttu-id="2a80a-122">Klicka på Ändra vy.</span><span class="sxs-lookup"><span data-stu-id="2a80a-122">Click Change view.</span></span>
14. <span data-ttu-id="2a80a-123">Klicka på Huvudvy.</span><span class="sxs-lookup"><span data-stu-id="2a80a-123">Click Header view.</span></span>
15. <span data-ttu-id="2a80a-124">Expandera avsnittet Inställningar.</span><span class="sxs-lookup"><span data-stu-id="2a80a-124">Expand the Setup section.</span></span>
16. <span data-ttu-id="2a80a-125">Ange eller välj ett värde i fältet Grupp-ID.</span><span class="sxs-lookup"><span data-stu-id="2a80a-125">In the Group ID field, enter or select a value.</span></span>
17. <span data-ttu-id="2a80a-126">I fältet Mallnamn, skriv ett värde.</span><span class="sxs-lookup"><span data-stu-id="2a80a-126">In the Template name field, type a value.</span></span>
18. <span data-ttu-id="2a80a-127">Välj Ja i fältet Aktivt.</span><span class="sxs-lookup"><span data-stu-id="2a80a-127">Select Yes in the Active field.</span></span>
    * <span data-ttu-id="2a80a-128">Endast aktiva mallar kan användas när du använder en mall till en ny försäljningsoffert.</span><span class="sxs-lookup"><span data-stu-id="2a80a-128">Only active templates can be used when you apply a template to a new sales quotation.</span></span>  
19. <span data-ttu-id="2a80a-129">Klicka på Alternativ i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="2a80a-129">On the Action Pane, click Options.</span></span>
20. <span data-ttu-id="2a80a-130">Klicka på Ändra vy.</span><span class="sxs-lookup"><span data-stu-id="2a80a-130">Click Change view.</span></span>
21. <span data-ttu-id="2a80a-131">Klicka på Radvy.</span><span class="sxs-lookup"><span data-stu-id="2a80a-131">Click Line view.</span></span>
22. <span data-ttu-id="2a80a-132">Ange eller välj ett värde i fältet Artikel.</span><span class="sxs-lookup"><span data-stu-id="2a80a-132">In the Item field, enter or select a value.</span></span>
23. <span data-ttu-id="2a80a-133">Ange ett värde i fältet Artikel.</span><span class="sxs-lookup"><span data-stu-id="2a80a-133">In the Item field, type a value.</span></span>
24. <span data-ttu-id="2a80a-134">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="2a80a-134">Close the page.</span></span>
25. <span data-ttu-id="2a80a-135">Ange ett värde i fältet Rabatt i procent.</span><span class="sxs-lookup"><span data-stu-id="2a80a-135">In the Discount percent field, enter a number.</span></span>
26. <span data-ttu-id="2a80a-136">Klicka på Lägg till rad.</span><span class="sxs-lookup"><span data-stu-id="2a80a-136">Click Add line.</span></span>
27. <span data-ttu-id="2a80a-137">Ange eller välj ett värde i fältet Artikel.</span><span class="sxs-lookup"><span data-stu-id="2a80a-137">In the Item field, enter or select a value.</span></span>
28. <span data-ttu-id="2a80a-138">Ange ett värde i fältet Artikel.</span><span class="sxs-lookup"><span data-stu-id="2a80a-138">In the Item field, type a value.</span></span>
29. <span data-ttu-id="2a80a-139">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="2a80a-139">Close the page.</span></span>
30. <span data-ttu-id="2a80a-140">Ange ett nytt pris eller ändra det aktuella i fältet Enhetspris.</span><span class="sxs-lookup"><span data-stu-id="2a80a-140">In the Unit price field, enter a new price or change the current one.</span></span>
31. <span data-ttu-id="2a80a-141">Klicka på Lägg till rad.</span><span class="sxs-lookup"><span data-stu-id="2a80a-141">Click Add line.</span></span>
32. <span data-ttu-id="2a80a-142">Ange eller välj ett värde i fältet Artikel.</span><span class="sxs-lookup"><span data-stu-id="2a80a-142">In the Item field, enter or select a value.</span></span>
33. <span data-ttu-id="2a80a-143">Ange ett värde i fältet Artikel.</span><span class="sxs-lookup"><span data-stu-id="2a80a-143">In the Item field, type a value.</span></span>
34. <span data-ttu-id="2a80a-144">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="2a80a-144">Close the page.</span></span>
35. <span data-ttu-id="2a80a-145">Ange ett tal i fältet Kvantitet.</span><span class="sxs-lookup"><span data-stu-id="2a80a-145">In the Quantity field, enter a number.</span></span>
36. <span data-ttu-id="2a80a-146">Ange ett värde i fältet Rabatt.</span><span class="sxs-lookup"><span data-stu-id="2a80a-146">In the Discount field, enter a number.</span></span>
37. <span data-ttu-id="2a80a-147">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="2a80a-147">Click Save.</span></span>

## <a name="apply-the-template-to-create-a-single-quotation"></a><span data-ttu-id="2a80a-148">Använd mallen för att skapa en offert</span><span class="sxs-lookup"><span data-stu-id="2a80a-148">Apply the template to create a single quotation</span></span>
1. <span data-ttu-id="2a80a-149">Gå till försäljning och marknadsföring > offerter > Alla offerter.</span><span class="sxs-lookup"><span data-stu-id="2a80a-149">Go to Sales and marketing > Sales quotations > All quotations.</span></span>
    * <span data-ttu-id="2a80a-150">Observera att offerten som du nyss skapade markeras som mall.</span><span class="sxs-lookup"><span data-stu-id="2a80a-150">Note that the quotation you have just created is marked as template.</span></span>  
2. <span data-ttu-id="2a80a-151">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="2a80a-151">Click New.</span></span>
3. <span data-ttu-id="2a80a-152">I fältet Kontotyp väljer du "Kund".</span><span class="sxs-lookup"><span data-stu-id="2a80a-152">In the Account type field, select 'Customer'.</span></span>
4. <span data-ttu-id="2a80a-153">I fältet Kundkonto, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="2a80a-153">In the Customer account field, enter or select a value.</span></span>
5. <span data-ttu-id="2a80a-154">Expandera alternativet Mall.</span><span class="sxs-lookup"><span data-stu-id="2a80a-154">Expand the Template section.</span></span>
6. <span data-ttu-id="2a80a-155">Ange eller välj ett värde i fältet Grupp-ID.</span><span class="sxs-lookup"><span data-stu-id="2a80a-155">In the Group ID field, enter or select a value.</span></span>
7. <span data-ttu-id="2a80a-156">Ange eller välj ett värde i fältet Mallnamn.</span><span class="sxs-lookup"><span data-stu-id="2a80a-156">In the Template name field, enter or select a value.</span></span>
8. <span data-ttu-id="2a80a-157">Välj Baserat på mallvärden i fältet Beräkningsmetod.</span><span class="sxs-lookup"><span data-stu-id="2a80a-157">In the Calculation method field, select 'Based on template values'.</span></span>
9. <span data-ttu-id="2a80a-158">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="2a80a-158">Click OK.</span></span>
    * <span data-ttu-id="2a80a-159">Den nya offerten har nu skapats, baserat på data och villkoren i mallen.</span><span class="sxs-lookup"><span data-stu-id="2a80a-159">The new quotation has now been created, based on the data and terms of the template.</span></span>  
10. <span data-ttu-id="2a80a-160">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="2a80a-160">Close the page.</span></span>
11. <span data-ttu-id="2a80a-161">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="2a80a-161">Close the page.</span></span>

## <a name="apply-the-template-to-mass-create-quotations"></a><span data-ttu-id="2a80a-162">Använd mallen för att skapa flera offerter</span><span class="sxs-lookup"><span data-stu-id="2a80a-162">Apply the template to mass create quotations</span></span>
1. <span data-ttu-id="2a80a-163">Gå till försäljning och marknadsföring > offerter > Offert update > massa skapa offerter.</span><span class="sxs-lookup"><span data-stu-id="2a80a-163">Go to Sales and marketing > Sales quotations > Quotation update > Mass create quotations.</span></span>
2. <span data-ttu-id="2a80a-164">I fältet Kontotyp väljer du "Kund".</span><span class="sxs-lookup"><span data-stu-id="2a80a-164">In the Account type field, select 'Customer'.</span></span>
3. <span data-ttu-id="2a80a-165">Ange eller välj ett värde i fältet Grupp-ID.</span><span class="sxs-lookup"><span data-stu-id="2a80a-165">In the Group ID field, enter or select a value.</span></span>
4. <span data-ttu-id="2a80a-166">Ange eller välj ett värde i fältet Mallnamn.</span><span class="sxs-lookup"><span data-stu-id="2a80a-166">In the Template name field, enter or select a value.</span></span>
5. <span data-ttu-id="2a80a-167">Välj Baserat på mallvärden i fältet Beräkningsmetod.</span><span class="sxs-lookup"><span data-stu-id="2a80a-167">In the Calculation method field, select 'Based on template values'.</span></span>
6. <span data-ttu-id="2a80a-168">Expandera avsnittet Poster som ska ingå.</span><span class="sxs-lookup"><span data-stu-id="2a80a-168">Expand the Records to include section.</span></span>
7. <span data-ttu-id="2a80a-169">Klicka på Filter.</span><span class="sxs-lookup"><span data-stu-id="2a80a-169">Click Filter.</span></span>
8. <span data-ttu-id="2a80a-170">Gå till fältet Kriterier och ställ in ett filter som omfattar kunder du vill ta med i massofferten.</span><span class="sxs-lookup"><span data-stu-id="2a80a-170">In the Criteria field, set the filter to cover a range of customers you want to include in this mass quotation creation.</span></span> <span data-ttu-id="2a80a-171">Använd format Kund1..KundN.</span><span class="sxs-lookup"><span data-stu-id="2a80a-171">Use the following format "Customer1..CustomerN.</span></span>
    * <span data-ttu-id="2a80a-172">Du kan till exempel ställa in filtret på US-001..US-004</span><span class="sxs-lookup"><span data-stu-id="2a80a-172">For example, you could set the filter to: US-001..US-004</span></span>  
9. <span data-ttu-id="2a80a-173">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="2a80a-173">Click OK.</span></span>
10. <span data-ttu-id="2a80a-174">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="2a80a-174">Click OK.</span></span>
11. <span data-ttu-id="2a80a-175">Gå till försäljning och marknadsföring > offerter > Alla offerter.</span><span class="sxs-lookup"><span data-stu-id="2a80a-175">Go to Sales and marketing > Sales quotations > All quotations.</span></span>
    * <span data-ttu-id="2a80a-176">Kontrollera att offerter har skapats för alla angivna kunder i massuppdateringrutinen som baserat på den valda mallen.</span><span class="sxs-lookup"><span data-stu-id="2a80a-176">Verify that quotations have been created for all the customers specified in the mass update routine, as based on the selected template.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]