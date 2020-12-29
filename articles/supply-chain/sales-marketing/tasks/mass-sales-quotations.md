---
title: Masskapa försäljningsofferter
description: I den här proceduren visas hur du skapar offerter med en uppsättning produkter eller tjänster som ska skickas till flera kunder.
author: omulvad
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesQuotationTemplateGroup, SalesQuotationListPage, SalesCreateQuotation, SalesQuotationTable, SysQueryForm, SalesQuickQuote
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 227ff0dd03f8917f4551ce08067ef26c6204b059
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437468"
---
# <a name="mass-create-sales-quotations"></a><span data-ttu-id="63591-103">Masskapa försäljningsofferter</span><span class="sxs-lookup"><span data-stu-id="63591-103">Mass create sales quotations</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="63591-104">I den här proceduren visas hur du skapar offerter med en uppsättning produkter eller tjänster som ska skickas till flera kunder.</span><span class="sxs-lookup"><span data-stu-id="63591-104">This procedure demonstrates how to efficiently create quotations offering a set of products or services that are to be sent to multiple customers.</span></span> <span data-ttu-id="63591-105">Den här genereringen av massofferter baseras på offertmallar.</span><span class="sxs-lookup"><span data-stu-id="63591-105">This mass quotation creation is based on quotation templates.</span></span> <span data-ttu-id="63591-106">Du kan köra den här proceduren med dina egna uppgifter i demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="63591-106">You can run this procedure on your own data or in demo data company USMF.</span></span>


## <a name="create-a-quotation-template"></a><span data-ttu-id="63591-107">Skapa en offertmall</span><span class="sxs-lookup"><span data-stu-id="63591-107">Create a quotation template</span></span>
1. <span data-ttu-id="63591-108">Gå till försäljning och marknadsföring > Installation > offerter > Template Groups.</span><span class="sxs-lookup"><span data-stu-id="63591-108">Go to Sales and marketing > Setup > Quotations > Template groups.</span></span>
2. <span data-ttu-id="63591-109">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="63591-109">Click New.</span></span>
3. <span data-ttu-id="63591-110">Ange ett id i fältet Grupp-ID.</span><span class="sxs-lookup"><span data-stu-id="63591-110">In the Group ID field, type an ID of your choice.</span></span>
4. <span data-ttu-id="63591-111">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="63591-111">In the Description field, type a value.</span></span>
5. <span data-ttu-id="63591-112">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="63591-112">Click Save.</span></span>
6. <span data-ttu-id="63591-113">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="63591-113">Close the page.</span></span>
7. <span data-ttu-id="63591-114">Gå till försäljning och marknadsföring > offerter > Alla offerter.</span><span class="sxs-lookup"><span data-stu-id="63591-114">Go to Sales and marketing > Sales quotations > All quotations.</span></span>
8. <span data-ttu-id="63591-115">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="63591-115">Click New.</span></span>
9. <span data-ttu-id="63591-116">I fältet Kontotyp väljer du "Kund".</span><span class="sxs-lookup"><span data-stu-id="63591-116">In the Account type field, select 'Customer'.</span></span>
10. <span data-ttu-id="63591-117">I fältet Kundkonto, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="63591-117">In the Customer account field, enter or select a value.</span></span>
11. <span data-ttu-id="63591-118">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="63591-118">Click OK.</span></span>
    * <span data-ttu-id="63591-119">För att en offert ska kunna bli en mall, måste du utföra inställningssteg i offerthuvudet.</span><span class="sxs-lookup"><span data-stu-id="63591-119">For a quotation to become a template you must carry out  setup steps on the quotation header.</span></span> <span data-ttu-id="63591-120">Detta måste göras innan du lägger till rader i offerten.</span><span class="sxs-lookup"><span data-stu-id="63591-120">This must be done before you add lines to the quotation.</span></span>   
12. <span data-ttu-id="63591-121">Klicka på Alternativ i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="63591-121">On the Action Pane, click Options.</span></span>
13. <span data-ttu-id="63591-122">Klicka på Ändra vy.</span><span class="sxs-lookup"><span data-stu-id="63591-122">Click Change view.</span></span>
14. <span data-ttu-id="63591-123">Klicka på Huvudvy.</span><span class="sxs-lookup"><span data-stu-id="63591-123">Click Header view.</span></span>
15. <span data-ttu-id="63591-124">Expandera avsnittet Inställningar.</span><span class="sxs-lookup"><span data-stu-id="63591-124">Expand the Setup section.</span></span>
16. <span data-ttu-id="63591-125">Ange eller välj ett värde i fältet Grupp-ID.</span><span class="sxs-lookup"><span data-stu-id="63591-125">In the Group ID field, enter or select a value.</span></span>
17. <span data-ttu-id="63591-126">I fältet Mallnamn, skriv ett värde.</span><span class="sxs-lookup"><span data-stu-id="63591-126">In the Template name field, type a value.</span></span>
18. <span data-ttu-id="63591-127">Välj Ja i fältet Aktivt.</span><span class="sxs-lookup"><span data-stu-id="63591-127">Select Yes in the Active field.</span></span>
    * <span data-ttu-id="63591-128">Endast aktiva mallar kan användas när du använder en mall till en ny försäljningsoffert.</span><span class="sxs-lookup"><span data-stu-id="63591-128">Only active templates can be used when you apply a template to a new sales quotation.</span></span>  
19. <span data-ttu-id="63591-129">Klicka på Alternativ i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="63591-129">On the Action Pane, click Options.</span></span>
20. <span data-ttu-id="63591-130">Klicka på Ändra vy.</span><span class="sxs-lookup"><span data-stu-id="63591-130">Click Change view.</span></span>
21. <span data-ttu-id="63591-131">Klicka på Radvy.</span><span class="sxs-lookup"><span data-stu-id="63591-131">Click Line view.</span></span>
22. <span data-ttu-id="63591-132">Ange eller välj ett värde i fältet Artikel.</span><span class="sxs-lookup"><span data-stu-id="63591-132">In the Item field, enter or select a value.</span></span>
23. <span data-ttu-id="63591-133">Ange ett värde i fältet Artikel.</span><span class="sxs-lookup"><span data-stu-id="63591-133">In the Item field, type a value.</span></span>
24. <span data-ttu-id="63591-134">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="63591-134">Close the page.</span></span>
25. <span data-ttu-id="63591-135">Ange ett värde i fältet Rabatt i procent.</span><span class="sxs-lookup"><span data-stu-id="63591-135">In the Discount percent field, enter a number.</span></span>
26. <span data-ttu-id="63591-136">Klicka på Lägg till rad.</span><span class="sxs-lookup"><span data-stu-id="63591-136">Click Add line.</span></span>
27. <span data-ttu-id="63591-137">Ange eller välj ett värde i fältet Artikel.</span><span class="sxs-lookup"><span data-stu-id="63591-137">In the Item field, enter or select a value.</span></span>
28. <span data-ttu-id="63591-138">Ange ett värde i fältet Artikel.</span><span class="sxs-lookup"><span data-stu-id="63591-138">In the Item field, type a value.</span></span>
29. <span data-ttu-id="63591-139">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="63591-139">Close the page.</span></span>
30. <span data-ttu-id="63591-140">Ange ett nytt pris eller ändra det aktuella i fältet Enhetspris.</span><span class="sxs-lookup"><span data-stu-id="63591-140">In the Unit price field, enter a new price or change the current one.</span></span>
31. <span data-ttu-id="63591-141">Klicka på Lägg till rad.</span><span class="sxs-lookup"><span data-stu-id="63591-141">Click Add line.</span></span>
32. <span data-ttu-id="63591-142">Ange eller välj ett värde i fältet Artikel.</span><span class="sxs-lookup"><span data-stu-id="63591-142">In the Item field, enter or select a value.</span></span>
33. <span data-ttu-id="63591-143">Ange ett värde i fältet Artikel.</span><span class="sxs-lookup"><span data-stu-id="63591-143">In the Item field, type a value.</span></span>
34. <span data-ttu-id="63591-144">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="63591-144">Close the page.</span></span>
35. <span data-ttu-id="63591-145">Ange ett tal i fältet Kvantitet.</span><span class="sxs-lookup"><span data-stu-id="63591-145">In the Quantity field, enter a number.</span></span>
36. <span data-ttu-id="63591-146">Ange ett värde i fältet Rabatt.</span><span class="sxs-lookup"><span data-stu-id="63591-146">In the Discount field, enter a number.</span></span>
37. <span data-ttu-id="63591-147">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="63591-147">Click Save.</span></span>

## <a name="apply-the-template-to-create-a-single-quotation"></a><span data-ttu-id="63591-148">Använd mallen för att skapa en offert</span><span class="sxs-lookup"><span data-stu-id="63591-148">Apply the template to create a single quotation</span></span>
1. <span data-ttu-id="63591-149">Gå till försäljning och marknadsföring > offerter > Alla offerter.</span><span class="sxs-lookup"><span data-stu-id="63591-149">Go to Sales and marketing > Sales quotations > All quotations.</span></span>
    * <span data-ttu-id="63591-150">Observera att offerten som du nyss skapade markeras som mall.</span><span class="sxs-lookup"><span data-stu-id="63591-150">Note that the quotation you have just created is marked as template.</span></span>  
2. <span data-ttu-id="63591-151">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="63591-151">Click New.</span></span>
3. <span data-ttu-id="63591-152">I fältet Kontotyp väljer du "Kund".</span><span class="sxs-lookup"><span data-stu-id="63591-152">In the Account type field, select 'Customer'.</span></span>
4. <span data-ttu-id="63591-153">I fältet Kundkonto, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="63591-153">In the Customer account field, enter or select a value.</span></span>
5. <span data-ttu-id="63591-154">Expandera alternativet Mall.</span><span class="sxs-lookup"><span data-stu-id="63591-154">Expand the Template section.</span></span>
6. <span data-ttu-id="63591-155">Ange eller välj ett värde i fältet Grupp-ID.</span><span class="sxs-lookup"><span data-stu-id="63591-155">In the Group ID field, enter or select a value.</span></span>
7. <span data-ttu-id="63591-156">Ange eller välj ett värde i fältet Mallnamn.</span><span class="sxs-lookup"><span data-stu-id="63591-156">In the Template name field, enter or select a value.</span></span>
8. <span data-ttu-id="63591-157">Välj Baserat på mallvärden i fältet Beräkningsmetod.</span><span class="sxs-lookup"><span data-stu-id="63591-157">In the Calculation method field, select 'Based on template values'.</span></span>
9. <span data-ttu-id="63591-158">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="63591-158">Click OK.</span></span>
    * <span data-ttu-id="63591-159">Den nya offerten har nu skapats, baserat på data och villkoren i mallen.</span><span class="sxs-lookup"><span data-stu-id="63591-159">The new quotation has now been created, based on the data and terms of the template.</span></span>  
10. <span data-ttu-id="63591-160">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="63591-160">Close the page.</span></span>
11. <span data-ttu-id="63591-161">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="63591-161">Close the page.</span></span>

## <a name="apply-the-template-to-mass-create-quotations"></a><span data-ttu-id="63591-162">Använd mallen för att skapa flera offerter</span><span class="sxs-lookup"><span data-stu-id="63591-162">Apply the template to mass create quotations</span></span>
1. <span data-ttu-id="63591-163">Gå till försäljning och marknadsföring > offerter > Offert update > massa skapa offerter.</span><span class="sxs-lookup"><span data-stu-id="63591-163">Go to Sales and marketing > Sales quotations > Quotation update > Mass create quotations.</span></span>
2. <span data-ttu-id="63591-164">I fältet Kontotyp väljer du "Kund".</span><span class="sxs-lookup"><span data-stu-id="63591-164">In the Account type field, select 'Customer'.</span></span>
3. <span data-ttu-id="63591-165">Ange eller välj ett värde i fältet Grupp-ID.</span><span class="sxs-lookup"><span data-stu-id="63591-165">In the Group ID field, enter or select a value.</span></span>
4. <span data-ttu-id="63591-166">Ange eller välj ett värde i fältet Mallnamn.</span><span class="sxs-lookup"><span data-stu-id="63591-166">In the Template name field, enter or select a value.</span></span>
5. <span data-ttu-id="63591-167">Välj Baserat på mallvärden i fältet Beräkningsmetod.</span><span class="sxs-lookup"><span data-stu-id="63591-167">In the Calculation method field, select 'Based on template values'.</span></span>
6. <span data-ttu-id="63591-168">Expandera avsnittet Poster som ska ingå.</span><span class="sxs-lookup"><span data-stu-id="63591-168">Expand the Records to include section.</span></span>
7. <span data-ttu-id="63591-169">Klicka på Filter.</span><span class="sxs-lookup"><span data-stu-id="63591-169">Click Filter.</span></span>
8. <span data-ttu-id="63591-170">Gå till fältet Kriterier och ställ in ett filter som omfattar kunder du vill ta med i massofferten.</span><span class="sxs-lookup"><span data-stu-id="63591-170">In the Criteria field, set the filter to cover a range of customers you want to include in this mass quotation creation.</span></span> <span data-ttu-id="63591-171">Använd format Kund1..KundN.</span><span class="sxs-lookup"><span data-stu-id="63591-171">Use the following format "Customer1..CustomerN.</span></span>
    * <span data-ttu-id="63591-172">Du kan till exempel ställa in filtret på US-001..US-004</span><span class="sxs-lookup"><span data-stu-id="63591-172">For example, you could set the filter to: US-001..US-004</span></span>  
9. <span data-ttu-id="63591-173">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="63591-173">Click OK.</span></span>
10. <span data-ttu-id="63591-174">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="63591-174">Click OK.</span></span>
11. <span data-ttu-id="63591-175">Gå till försäljning och marknadsföring > offerter > Alla offerter.</span><span class="sxs-lookup"><span data-stu-id="63591-175">Go to Sales and marketing > Sales quotations > All quotations.</span></span>
    * <span data-ttu-id="63591-176">Kontrollera att offerter har skapats för alla angivna kunder i massuppdateringrutinen som baserat på den valda mallen.</span><span class="sxs-lookup"><span data-stu-id="63591-176">Verify that quotations have been created for all the customers specified in the mass update routine, as based on the selected template.</span></span>  

