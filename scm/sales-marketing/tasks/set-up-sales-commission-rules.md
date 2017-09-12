--- 
title: "Ställ in regler för försäljningsprovision"
description: "I den här proceduren visas om hur du ställer in och aktiverar försäljningsprovisionsberäkning och knipning."
author: omulvad
manager: AnnBe
ms.date: 11/10/2016
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
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 0ab5b3b5447e56eb8ed012a67454400cb2357af4
ms.contentlocale: sv-se
ms.lasthandoff: 07/27/2017

---
# <a name="set-up-sales-commission-rules"></a><span data-ttu-id="85d74-103">Ställ in regler för försäljningsprovision</span><span class="sxs-lookup"><span data-stu-id="85d74-103">Set up sales commission rules</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="85d74-104">I den här proceduren visas om hur du ställer in och aktiverar försäljningsprovisionsberäkning och knipning.</span><span class="sxs-lookup"><span data-stu-id="85d74-104">This procedure shows you how to set up and enable sales commission calculation and tracking.</span></span> <span data-ttu-id="85d74-105">Proceduren visas hur du skapar både kund- och artikelprovisionsgrupper, och hur du sedan kopplar en vald kund och produkt till respektive grupp.</span><span class="sxs-lookup"><span data-stu-id="85d74-105">The procedure shows how to create both customer and item commission groups, and then how to link a selected customer and product to the respective groups.</span></span> <span data-ttu-id="85d74-106">Grupperna används sedan i inställningarna för provisionsberäkningen för att skapa en kombination av kund, artikel och en säljare som måste matchas med försäljningsordern som berättigar säljaren till provision.</span><span class="sxs-lookup"><span data-stu-id="85d74-106">Those groups are then used in the commission calculation setup to create a customer, item, and sales representatives combination that must be matched by the sales order to entitle the sales people to a commission.</span></span> <span data-ttu-id="85d74-107">Det är valfritt att skapa kund- och artikelprovisionsgrupper, eftersom beräkningen av provision också kan göras för en enskild kund eller artikel.</span><span class="sxs-lookup"><span data-stu-id="85d74-107">Creating customer and item commission groups are optional, as the calculation of commission can also be done for an individual customer and/or item.</span></span> <span data-ttu-id="85d74-108">Du kan köra den här proceduren i demonstrationsföretaget USMF eller på dina egna data.</span><span class="sxs-lookup"><span data-stu-id="85d74-108">You can run this procedure in demo data company USMF or on your own data.</span></span>


## <a name="set-up-commission-groups-and-commission-rates"></a><span data-ttu-id="85d74-109">Ställ in provisionsgrupper och provisioner</span><span class="sxs-lookup"><span data-stu-id="85d74-109">Set up commission groups and commission rates</span></span>
1. <span data-ttu-id="85d74-110">Gå till Försäljning och marknadsföring > Provisioner > Kundgrupper för provision.</span><span class="sxs-lookup"><span data-stu-id="85d74-110">Go to Sales and marketing > Commissions > Customer groups for commission.</span></span>
2. <span data-ttu-id="85d74-111">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="85d74-111">Click New.</span></span>
3. <span data-ttu-id="85d74-112">Ange ett värde i fältet Grupp.</span><span class="sxs-lookup"><span data-stu-id="85d74-112">In the Group field, type a value.</span></span>
4. <span data-ttu-id="85d74-113">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="85d74-113">In the Name field, type a value.</span></span>
5. <span data-ttu-id="85d74-114">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="85d74-114">Click Save.</span></span>
6. <span data-ttu-id="85d74-115">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="85d74-115">Close the page.</span></span>
7. <span data-ttu-id="85d74-116">Gå till Försäljning och marknadsföring > Provisioner > Artikelgrupper.</span><span class="sxs-lookup"><span data-stu-id="85d74-116">Go to Sales and marketing > Commissions > Item groups.</span></span>
8. <span data-ttu-id="85d74-117">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="85d74-117">Click New.</span></span>
9. <span data-ttu-id="85d74-118">Ange ett värde i fältet Grupp.</span><span class="sxs-lookup"><span data-stu-id="85d74-118">In the Group field, type a value.</span></span>
10. <span data-ttu-id="85d74-119">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="85d74-119">In the Name field, type a value.</span></span>
11. <span data-ttu-id="85d74-120">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="85d74-120">Close the page.</span></span>
12. <span data-ttu-id="85d74-121">Gå till Försäljning och marknadsföring > Provisioner > Säljgrupper.</span><span class="sxs-lookup"><span data-stu-id="85d74-121">Go to Sales and marketing > Commissions > Sales groups.</span></span>
    * <span data-ttu-id="85d74-122">En provisionsförsäljningsgrupp anger medarbetarna i säljarrollerna som är berättigade till en provision när en kund som associeras med relevant försäljningsgrupp köper vissa artiklar.</span><span class="sxs-lookup"><span data-stu-id="85d74-122">A Commission sales group specifies the employees in sales representative roles who are eligible to receive a commission when a customer associated with the relevant sales group buys certain items.</span></span>  
    * <span data-ttu-id="85d74-123">I demonstrationsföretaget USMF finns det en försäljningsgrupp som kallas Säljare USA.</span><span class="sxs-lookup"><span data-stu-id="85d74-123">In the USMF demo data company, there is a sales group called "Sales reps US."</span></span>  
13. <span data-ttu-id="85d74-124">Klicka på Allmänt i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="85d74-124">On the Action Pane, click General.</span></span>
14. <span data-ttu-id="85d74-125">Klicka på Säljare.</span><span class="sxs-lookup"><span data-stu-id="85d74-125">Click Sales rep..</span></span>
    * <span data-ttu-id="85d74-126">Sidan Säljare</span><span class="sxs-lookup"><span data-stu-id="85d74-126">The Sales rep.</span></span> <span data-ttu-id="85d74-127">visar en lista över företagets säljare som har associerats med en specifik provisionsgrupp.</span><span class="sxs-lookup"><span data-stu-id="85d74-127">page displays a list of the company's sales people who are associated with a specific commission group.</span></span> <span data-ttu-id="85d74-128">Du kan tilldela flera säljare till samma grupp och definiera deras respektive andel av det totala värdet för provisionstillägget som en procentsats.</span><span class="sxs-lookup"><span data-stu-id="85d74-128">You can assign multiple sales representatives to the same group and define their respective share of the total commission fee as a percentage value.</span></span> <span data-ttu-id="85d74-129">Den totala provisionsandelen för alla medarbetare får inte överstiga 100.</span><span class="sxs-lookup"><span data-stu-id="85d74-129">The total commission share across all employees must not exceed 100.</span></span>  
15. <span data-ttu-id="85d74-130">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="85d74-130">In the list, mark the selected row.</span></span>
16. <span data-ttu-id="85d74-131">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="85d74-131">Click Edit.</span></span>
17. <span data-ttu-id="85d74-132">Ställ in provisionsandel på 50.</span><span class="sxs-lookup"><span data-stu-id="85d74-132">Set Commission share to '50'.</span></span>
18. <span data-ttu-id="85d74-133">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="85d74-133">Click New.</span></span>
19. <span data-ttu-id="85d74-134">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="85d74-134">In the Name field, click the drop-down button to open the lookup.</span></span>
20. <span data-ttu-id="85d74-135">Använd snabbfiltret för att söka efter poster.</span><span class="sxs-lookup"><span data-stu-id="85d74-135">Use the Quick Filter to find records.</span></span> <span data-ttu-id="85d74-136">Filtrera till exempel fältet Namn på värdet Susan Burk.</span><span class="sxs-lookup"><span data-stu-id="85d74-136">For example, filter on the Name field with a value of 'Susan Burk'.</span></span>
21. <span data-ttu-id="85d74-137">Klicka på Välj.</span><span class="sxs-lookup"><span data-stu-id="85d74-137">Click Select.</span></span>
22. <span data-ttu-id="85d74-138">Ställ in provisionsandel på 50.</span><span class="sxs-lookup"><span data-stu-id="85d74-138">Set Commission share to '50'.</span></span>
23. <span data-ttu-id="85d74-139">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="85d74-139">Click Save.</span></span>
24. <span data-ttu-id="85d74-140">Gå till Försäljning och marknadsföring > Provisioner > Beräkna provision.</span><span class="sxs-lookup"><span data-stu-id="85d74-140">Go to Sales and marketing > Commissions > Commission calculation.</span></span>
    * <span data-ttu-id="85d74-141">På sidan för beräkning av provision definierar du provisionen som medarbetaren ska få för en försäljningstransaktion, när den innehåller den förinställda kombinationen av kund och produkt.</span><span class="sxs-lookup"><span data-stu-id="85d74-141">In the Commission calculation page you define the commission rate that the employee is to receive for a sales transaction when it contains the pre-set combination of customer and product.</span></span> <span data-ttu-id="85d74-142">Som en del av inställningen av provisionen måste du ange grunden för provisionsberäkningen och om den ska inkludera eller exkludera rabatter.</span><span class="sxs-lookup"><span data-stu-id="85d74-142">As part of the commission rate setup, you must specify the commission calculation basis and whether it should include or exclude discounts.</span></span> <span data-ttu-id="85d74-143">Du kan även ange en för giltighetsperiod då provisionen ska vara aktiv.</span><span class="sxs-lookup"><span data-stu-id="85d74-143">You can also enter a validity period for when the commission rate is active.</span></span>  
25. <span data-ttu-id="85d74-144">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="85d74-144">Click New.</span></span>
26. <span data-ttu-id="85d74-145">Välj Grupp i fältet Artikelkod.</span><span class="sxs-lookup"><span data-stu-id="85d74-145">In the Item code field, select 'Group'.</span></span>
27. <span data-ttu-id="85d74-146">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Artikelrelation.</span><span class="sxs-lookup"><span data-stu-id="85d74-146">In the Item relation field, click the drop-down button to open the lookup.</span></span>
28. <span data-ttu-id="85d74-147">I listan söker du efter och väljer den grupp som du skapade tidigare.</span><span class="sxs-lookup"><span data-stu-id="85d74-147">In the list, find and select the group that you created earlier.</span></span>
29. <span data-ttu-id="85d74-148">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="85d74-148">In the list, click the link in the selected row.</span></span>
30. <span data-ttu-id="85d74-149">Välj Grupp i fältet Kundkod.</span><span class="sxs-lookup"><span data-stu-id="85d74-149">In the Customer code field, select 'Group'.</span></span>
31. <span data-ttu-id="85d74-150">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Kundrelation.</span><span class="sxs-lookup"><span data-stu-id="85d74-150">In the Customer relation field, click the drop-down button to open the lookup.</span></span>
32. <span data-ttu-id="85d74-151">I listan väljer du den grupp som du ställde in tidigare.</span><span class="sxs-lookup"><span data-stu-id="85d74-151">In the list, select the group that you set up earlier.</span></span>
33. <span data-ttu-id="85d74-152">I fältet</span><span class="sxs-lookup"><span data-stu-id="85d74-152">In the Sales rep.</span></span> <span data-ttu-id="85d74-153">säljarrelation, klicka på den nedrullningsbara knappen för att öppna sökningen.</span><span class="sxs-lookup"><span data-stu-id="85d74-153">relation field, click the drop-down button to open the lookup.</span></span>
34. <span data-ttu-id="85d74-154">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="85d74-154">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="85d74-155">Behåll alternativet Före radrabatt.</span><span class="sxs-lookup"><span data-stu-id="85d74-155">Keep the "Before line discount" option.</span></span>  
    * <span data-ttu-id="85d74-156">Behåll alternativet Intäkt som grund för beräkningen av provisionen.</span><span class="sxs-lookup"><span data-stu-id="85d74-156">Keep the "Revenue" option as the basis for commission value calculation.</span></span>    
35. <span data-ttu-id="85d74-157">Ange ett nummer i fältet Provisionsprocent.</span><span class="sxs-lookup"><span data-stu-id="85d74-157">In the Commission percentage field, enter a number.</span></span>
36. <span data-ttu-id="85d74-158">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="85d74-158">Click Save.</span></span>

## <a name="setting-up-commission-posting"></a><span data-ttu-id="85d74-159">Ställ in provisionsbokföring</span><span class="sxs-lookup"><span data-stu-id="85d74-159">Setting up commission posting</span></span>
1. <span data-ttu-id="85d74-160">Gå till Försäljning och marknadsföring > Provisioner > Provisionsbokföring.</span><span class="sxs-lookup"><span data-stu-id="85d74-160">Go to Sales and marketing > Commissions > Commission posting.</span></span>
    * <span data-ttu-id="85d74-161">Provisionser är betalning till medarbetarna och därför måste de ställas in för att säkerställa korrekt redovisning på rätt konton.</span><span class="sxs-lookup"><span data-stu-id="85d74-161">Commission fees are payable to the employees and must therefore be set up to ensure correct financial posting to the appropriate accounts in the General ledger.</span></span> <span data-ttu-id="85d74-162">Du gör detta på sidan Provisionsbokföring.</span><span class="sxs-lookup"><span data-stu-id="85d74-162">This is done in the Commission posting page.</span></span> <span data-ttu-id="85d74-163">Granska upplägget för det aktuella företaget.</span><span class="sxs-lookup"><span data-stu-id="85d74-163">Review the setup that is available for the current company.</span></span> <span data-ttu-id="85d74-164">Vanligtvis bokförs provisionsbeloppen på ett dedicerad utgiftskonto och avräknas mot ett dedicerat dedikerat skuldkonto.</span><span class="sxs-lookup"><span data-stu-id="85d74-164">Typically, the commission amounts are posted to a dedicated expense account and are offset to a dedicated payable account.</span></span> <span data-ttu-id="85d74-165">Om du inte har lagt upp bokföringsreglerna för provision kan inte systemet slutföra faktureringen av en försäljningsorder som har provisioner.</span><span class="sxs-lookup"><span data-stu-id="85d74-165">If you don't have the commission posting rules set up, the system will fail to complete invoicing of a sales order which has eligible commissions.</span></span>  
2. <span data-ttu-id="85d74-166">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="85d74-166">Close the page.</span></span>

## <a name="assign-a-commission-group-to-a-customer-and-a-product"></a><span data-ttu-id="85d74-167">Koppla en provisionssäljgrupp till en kund och en produkt</span><span class="sxs-lookup"><span data-stu-id="85d74-167">Assign a commission group to a customer and a product</span></span>
1. <span data-ttu-id="85d74-168">Gå till Försäljning och marknadsföring > Kunder > Alla kunder.</span><span class="sxs-lookup"><span data-stu-id="85d74-168">Go to Sales and marketing > Customers > All customers.</span></span>
2. <span data-ttu-id="85d74-169">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="85d74-169">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="85d74-170">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="85d74-170">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="85d74-171">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="85d74-171">Click Edit.</span></span>
5. <span data-ttu-id="85d74-172">Expandera avsnittet med försäljningsorderstandarder.</span><span class="sxs-lookup"><span data-stu-id="85d74-172">Expand the Sales order defaults section.</span></span>
6. <span data-ttu-id="85d74-173">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Provisionsgrupp.</span><span class="sxs-lookup"><span data-stu-id="85d74-173">In the Commission group field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="85d74-174">I listan väljer du den grupp som du skapade tidigare.</span><span class="sxs-lookup"><span data-stu-id="85d74-174">In the list, select the group that you created earlier.</span></span>
8. <span data-ttu-id="85d74-175">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Säljgrupp.</span><span class="sxs-lookup"><span data-stu-id="85d74-175">In the Sales group field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="85d74-176">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="85d74-176">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="85d74-177">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="85d74-177">Click Save.</span></span>
11. <span data-ttu-id="85d74-178">Gå till Produktinformationshantering > Produkter > Frisläppta produkter.</span><span class="sxs-lookup"><span data-stu-id="85d74-178">Go to Product information management > Products > Released products.</span></span>
12. <span data-ttu-id="85d74-179">Använd snabbfiltret för att söka efter poster.</span><span class="sxs-lookup"><span data-stu-id="85d74-179">Use the Quick Filter to find records.</span></span> <span data-ttu-id="85d74-180">Filtrera till exempel i fältet Artikelnummer med värdet T0020.</span><span class="sxs-lookup"><span data-stu-id="85d74-180">For example, filter on the Item number field with a value of 'T0020 '.</span></span>
13. <span data-ttu-id="85d74-181">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="85d74-181">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="85d74-182">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="85d74-182">Click Edit.</span></span>
15. <span data-ttu-id="85d74-183">Expandera avsnittet Sälj.</span><span class="sxs-lookup"><span data-stu-id="85d74-183">Expand the Sell section.</span></span>
16. <span data-ttu-id="85d74-184">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Provisionsgrupp.</span><span class="sxs-lookup"><span data-stu-id="85d74-184">In the Commission group field, click the drop-down button to open the lookup.</span></span>
17. <span data-ttu-id="85d74-185">I listan väljer du den provisionsgrupp som du skapade tidigare.</span><span class="sxs-lookup"><span data-stu-id="85d74-185">In the list, select the commission group that you created earlier.</span></span>


