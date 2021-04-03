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
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f7aaa4e1fee12092be0389f0641e64712e869e6a
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5260369"
---
# <a name="mass-create-sales-quotations"></a><span data-ttu-id="a4a49-103">Masskapa försäljningsofferter</span><span class="sxs-lookup"><span data-stu-id="a4a49-103">Mass create sales quotations</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a4a49-104">I den här proceduren visas hur du skapar offerter med en uppsättning produkter eller tjänster som ska skickas till flera kunder.</span><span class="sxs-lookup"><span data-stu-id="a4a49-104">This procedure demonstrates how to efficiently create quotations offering a set of products or services that are to be sent to multiple customers.</span></span> <span data-ttu-id="a4a49-105">Den här genereringen av massofferter baseras på offertmallar.</span><span class="sxs-lookup"><span data-stu-id="a4a49-105">This mass quotation creation is based on quotation templates.</span></span> <span data-ttu-id="a4a49-106">Du kan köra den här proceduren med dina egna uppgifter i demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="a4a49-106">You can run this procedure on your own data or in demo data company USMF.</span></span>


## <a name="create-a-quotation-template"></a><span data-ttu-id="a4a49-107">Skapa en offertmall</span><span class="sxs-lookup"><span data-stu-id="a4a49-107">Create a quotation template</span></span>
1. <span data-ttu-id="a4a49-108">Gå till försäljning och marknadsföring > Installation > offerter > Template Groups.</span><span class="sxs-lookup"><span data-stu-id="a4a49-108">Go to Sales and marketing > Setup > Quotations > Template groups.</span></span>
2. <span data-ttu-id="a4a49-109">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="a4a49-109">Click New.</span></span>
3. <span data-ttu-id="a4a49-110">Ange ett id i fältet Grupp-ID.</span><span class="sxs-lookup"><span data-stu-id="a4a49-110">In the Group ID field, type an ID of your choice.</span></span>
4. <span data-ttu-id="a4a49-111">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="a4a49-111">In the Description field, type a value.</span></span>
5. <span data-ttu-id="a4a49-112">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="a4a49-112">Click Save.</span></span>
6. <span data-ttu-id="a4a49-113">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="a4a49-113">Close the page.</span></span>
7. <span data-ttu-id="a4a49-114">Gå till försäljning och marknadsföring > offerter > Alla offerter.</span><span class="sxs-lookup"><span data-stu-id="a4a49-114">Go to Sales and marketing > Sales quotations > All quotations.</span></span>
8. <span data-ttu-id="a4a49-115">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="a4a49-115">Click New.</span></span>
9. <span data-ttu-id="a4a49-116">I fältet Kontotyp väljer du "Kund".</span><span class="sxs-lookup"><span data-stu-id="a4a49-116">In the Account type field, select 'Customer'.</span></span>
10. <span data-ttu-id="a4a49-117">I fältet Kundkonto, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="a4a49-117">In the Customer account field, enter or select a value.</span></span>
11. <span data-ttu-id="a4a49-118">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="a4a49-118">Click OK.</span></span>
    * <span data-ttu-id="a4a49-119">För att en offert ska kunna bli en mall, måste du utföra inställningssteg i offerthuvudet.</span><span class="sxs-lookup"><span data-stu-id="a4a49-119">For a quotation to become a template you must carry out  setup steps on the quotation header.</span></span> <span data-ttu-id="a4a49-120">Detta måste göras innan du lägger till rader i offerten.</span><span class="sxs-lookup"><span data-stu-id="a4a49-120">This must be done before you add lines to the quotation.</span></span>   
12. <span data-ttu-id="a4a49-121">Klicka på Alternativ i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="a4a49-121">On the Action Pane, click Options.</span></span>
13. <span data-ttu-id="a4a49-122">Klicka på Ändra vy.</span><span class="sxs-lookup"><span data-stu-id="a4a49-122">Click Change view.</span></span>
14. <span data-ttu-id="a4a49-123">Klicka på Huvudvy.</span><span class="sxs-lookup"><span data-stu-id="a4a49-123">Click Header view.</span></span>
15. <span data-ttu-id="a4a49-124">Expandera avsnittet Inställningar.</span><span class="sxs-lookup"><span data-stu-id="a4a49-124">Expand the Setup section.</span></span>
16. <span data-ttu-id="a4a49-125">Ange eller välj ett värde i fältet Grupp-ID.</span><span class="sxs-lookup"><span data-stu-id="a4a49-125">In the Group ID field, enter or select a value.</span></span>
17. <span data-ttu-id="a4a49-126">I fältet Mallnamn, skriv ett värde.</span><span class="sxs-lookup"><span data-stu-id="a4a49-126">In the Template name field, type a value.</span></span>
18. <span data-ttu-id="a4a49-127">Välj Ja i fältet Aktivt.</span><span class="sxs-lookup"><span data-stu-id="a4a49-127">Select Yes in the Active field.</span></span>
    * <span data-ttu-id="a4a49-128">Endast aktiva mallar kan användas när du använder en mall till en ny försäljningsoffert.</span><span class="sxs-lookup"><span data-stu-id="a4a49-128">Only active templates can be used when you apply a template to a new sales quotation.</span></span>  
19. <span data-ttu-id="a4a49-129">Klicka på Alternativ i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="a4a49-129">On the Action Pane, click Options.</span></span>
20. <span data-ttu-id="a4a49-130">Klicka på Ändra vy.</span><span class="sxs-lookup"><span data-stu-id="a4a49-130">Click Change view.</span></span>
21. <span data-ttu-id="a4a49-131">Klicka på Radvy.</span><span class="sxs-lookup"><span data-stu-id="a4a49-131">Click Line view.</span></span>
22. <span data-ttu-id="a4a49-132">Ange eller välj ett värde i fältet Artikel.</span><span class="sxs-lookup"><span data-stu-id="a4a49-132">In the Item field, enter or select a value.</span></span>
23. <span data-ttu-id="a4a49-133">Ange ett värde i fältet Artikel.</span><span class="sxs-lookup"><span data-stu-id="a4a49-133">In the Item field, type a value.</span></span>
24. <span data-ttu-id="a4a49-134">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="a4a49-134">Close the page.</span></span>
25. <span data-ttu-id="a4a49-135">Ange ett värde i fältet Rabatt i procent.</span><span class="sxs-lookup"><span data-stu-id="a4a49-135">In the Discount percent field, enter a number.</span></span>
26. <span data-ttu-id="a4a49-136">Klicka på Lägg till rad.</span><span class="sxs-lookup"><span data-stu-id="a4a49-136">Click Add line.</span></span>
27. <span data-ttu-id="a4a49-137">Ange eller välj ett värde i fältet Artikel.</span><span class="sxs-lookup"><span data-stu-id="a4a49-137">In the Item field, enter or select a value.</span></span>
28. <span data-ttu-id="a4a49-138">Ange ett värde i fältet Artikel.</span><span class="sxs-lookup"><span data-stu-id="a4a49-138">In the Item field, type a value.</span></span>
29. <span data-ttu-id="a4a49-139">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="a4a49-139">Close the page.</span></span>
30. <span data-ttu-id="a4a49-140">Ange ett nytt pris eller ändra det aktuella i fältet Enhetspris.</span><span class="sxs-lookup"><span data-stu-id="a4a49-140">In the Unit price field, enter a new price or change the current one.</span></span>
31. <span data-ttu-id="a4a49-141">Klicka på Lägg till rad.</span><span class="sxs-lookup"><span data-stu-id="a4a49-141">Click Add line.</span></span>
32. <span data-ttu-id="a4a49-142">Ange eller välj ett värde i fältet Artikel.</span><span class="sxs-lookup"><span data-stu-id="a4a49-142">In the Item field, enter or select a value.</span></span>
33. <span data-ttu-id="a4a49-143">Ange ett värde i fältet Artikel.</span><span class="sxs-lookup"><span data-stu-id="a4a49-143">In the Item field, type a value.</span></span>
34. <span data-ttu-id="a4a49-144">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="a4a49-144">Close the page.</span></span>
35. <span data-ttu-id="a4a49-145">Ange ett tal i fältet Kvantitet.</span><span class="sxs-lookup"><span data-stu-id="a4a49-145">In the Quantity field, enter a number.</span></span>
36. <span data-ttu-id="a4a49-146">Ange ett värde i fältet Rabatt.</span><span class="sxs-lookup"><span data-stu-id="a4a49-146">In the Discount field, enter a number.</span></span>
37. <span data-ttu-id="a4a49-147">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="a4a49-147">Click Save.</span></span>

## <a name="apply-the-template-to-create-a-single-quotation"></a><span data-ttu-id="a4a49-148">Använd mallen för att skapa en offert</span><span class="sxs-lookup"><span data-stu-id="a4a49-148">Apply the template to create a single quotation</span></span>
1. <span data-ttu-id="a4a49-149">Gå till försäljning och marknadsföring > offerter > Alla offerter.</span><span class="sxs-lookup"><span data-stu-id="a4a49-149">Go to Sales and marketing > Sales quotations > All quotations.</span></span>
    * <span data-ttu-id="a4a49-150">Observera att offerten som du nyss skapade markeras som mall.</span><span class="sxs-lookup"><span data-stu-id="a4a49-150">Note that the quotation you have just created is marked as template.</span></span>  
2. <span data-ttu-id="a4a49-151">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="a4a49-151">Click New.</span></span>
3. <span data-ttu-id="a4a49-152">I fältet Kontotyp väljer du "Kund".</span><span class="sxs-lookup"><span data-stu-id="a4a49-152">In the Account type field, select 'Customer'.</span></span>
4. <span data-ttu-id="a4a49-153">I fältet Kundkonto, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="a4a49-153">In the Customer account field, enter or select a value.</span></span>
5. <span data-ttu-id="a4a49-154">Expandera alternativet Mall.</span><span class="sxs-lookup"><span data-stu-id="a4a49-154">Expand the Template section.</span></span>
6. <span data-ttu-id="a4a49-155">Ange eller välj ett värde i fältet Grupp-ID.</span><span class="sxs-lookup"><span data-stu-id="a4a49-155">In the Group ID field, enter or select a value.</span></span>
7. <span data-ttu-id="a4a49-156">Ange eller välj ett värde i fältet Mallnamn.</span><span class="sxs-lookup"><span data-stu-id="a4a49-156">In the Template name field, enter or select a value.</span></span>
8. <span data-ttu-id="a4a49-157">Välj Baserat på mallvärden i fältet Beräkningsmetod.</span><span class="sxs-lookup"><span data-stu-id="a4a49-157">In the Calculation method field, select 'Based on template values'.</span></span>
9. <span data-ttu-id="a4a49-158">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="a4a49-158">Click OK.</span></span>
    * <span data-ttu-id="a4a49-159">Den nya offerten har nu skapats, baserat på data och villkoren i mallen.</span><span class="sxs-lookup"><span data-stu-id="a4a49-159">The new quotation has now been created, based on the data and terms of the template.</span></span>  
10. <span data-ttu-id="a4a49-160">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="a4a49-160">Close the page.</span></span>
11. <span data-ttu-id="a4a49-161">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="a4a49-161">Close the page.</span></span>

## <a name="apply-the-template-to-mass-create-quotations"></a><span data-ttu-id="a4a49-162">Använd mallen för att skapa flera offerter</span><span class="sxs-lookup"><span data-stu-id="a4a49-162">Apply the template to mass create quotations</span></span>
1. <span data-ttu-id="a4a49-163">Gå till försäljning och marknadsföring > offerter > Offert update > massa skapa offerter.</span><span class="sxs-lookup"><span data-stu-id="a4a49-163">Go to Sales and marketing > Sales quotations > Quotation update > Mass create quotations.</span></span>
2. <span data-ttu-id="a4a49-164">I fältet Kontotyp väljer du "Kund".</span><span class="sxs-lookup"><span data-stu-id="a4a49-164">In the Account type field, select 'Customer'.</span></span>
3. <span data-ttu-id="a4a49-165">Ange eller välj ett värde i fältet Grupp-ID.</span><span class="sxs-lookup"><span data-stu-id="a4a49-165">In the Group ID field, enter or select a value.</span></span>
4. <span data-ttu-id="a4a49-166">Ange eller välj ett värde i fältet Mallnamn.</span><span class="sxs-lookup"><span data-stu-id="a4a49-166">In the Template name field, enter or select a value.</span></span>
5. <span data-ttu-id="a4a49-167">Välj Baserat på mallvärden i fältet Beräkningsmetod.</span><span class="sxs-lookup"><span data-stu-id="a4a49-167">In the Calculation method field, select 'Based on template values'.</span></span>
6. <span data-ttu-id="a4a49-168">Expandera avsnittet Poster som ska ingå.</span><span class="sxs-lookup"><span data-stu-id="a4a49-168">Expand the Records to include section.</span></span>
7. <span data-ttu-id="a4a49-169">Klicka på Filter.</span><span class="sxs-lookup"><span data-stu-id="a4a49-169">Click Filter.</span></span>
8. <span data-ttu-id="a4a49-170">Gå till fältet Kriterier och ställ in ett filter som omfattar kunder du vill ta med i massofferten.</span><span class="sxs-lookup"><span data-stu-id="a4a49-170">In the Criteria field, set the filter to cover a range of customers you want to include in this mass quotation creation.</span></span> <span data-ttu-id="a4a49-171">Använd format Kund1..KundN.</span><span class="sxs-lookup"><span data-stu-id="a4a49-171">Use the following format "Customer1..CustomerN.</span></span>
    * <span data-ttu-id="a4a49-172">Du kan till exempel ställa in filtret på US-001..US-004</span><span class="sxs-lookup"><span data-stu-id="a4a49-172">For example, you could set the filter to: US-001..US-004</span></span>  
9. <span data-ttu-id="a4a49-173">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="a4a49-173">Click OK.</span></span>
10. <span data-ttu-id="a4a49-174">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="a4a49-174">Click OK.</span></span>
11. <span data-ttu-id="a4a49-175">Gå till försäljning och marknadsföring > offerter > Alla offerter.</span><span class="sxs-lookup"><span data-stu-id="a4a49-175">Go to Sales and marketing > Sales quotations > All quotations.</span></span>
    * <span data-ttu-id="a4a49-176">Kontrollera att offerter har skapats för alla angivna kunder i massuppdateringrutinen som baserat på den valda mallen.</span><span class="sxs-lookup"><span data-stu-id="a4a49-176">Verify that quotations have been created for all the customers specified in the mass update routine, as based on the selected template.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]