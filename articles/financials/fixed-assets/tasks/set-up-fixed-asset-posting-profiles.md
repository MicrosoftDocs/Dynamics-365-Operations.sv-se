--- 
title: "Ställ in bokföringsprofiler för anläggningstillgångar"
description: "I den här uppgiftsguiden ställer vi in bokföringsprofiler för anläggningstillgångar."
author: saraschi2
manager: AnnBe
ms.date: 02/24/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 9bd8a506fc0bbf4d4d8127afa71fe371be10b55b
ms.contentlocale: sv-se
ms.lasthandoff: 04/13/2018

---
# <a name="set-up-fixed-asset-posting-profiles"></a><span data-ttu-id="e857c-103">Ställ in bokföringsprofiler för anläggningstillgångar</span><span class="sxs-lookup"><span data-stu-id="e857c-103">Set up fixed asset posting profiles</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e857c-104">I den här uppgiftsguiden ställer vi in bokföringsprofiler för anläggningstillgångar.</span><span class="sxs-lookup"><span data-stu-id="e857c-104">This task guide will set up Fixed asset posting profiles.</span></span>  <span data-ttu-id="e857c-105">Här används revisorrollen och demonstrationdata för den juridiska personen USMF.</span><span class="sxs-lookup"><span data-stu-id="e857c-105">It uses the Accountant role and demo data for the USMF legal entity.</span></span>  <span data-ttu-id="e857c-106">Exempel som angetts i uppgifthandboken, gäller en grundläggande bokföringsprofil, fast bokföringsprofiler måste skapas för dina specifika krav för kontoplanen och om den ekonomiska rapporteringen.</span><span class="sxs-lookup"><span data-stu-id="e857c-106">Examples given in the task guide are for a basic posting profile, though posting profiles must be created for your specific chart of accounts and financial reporting requirements.</span></span>

1. <span data-ttu-id="e857c-107">Gå till Anläggningstillgångar > Inställning > Bokföringsprofiler för anläggningstillgångar.</span><span class="sxs-lookup"><span data-stu-id="e857c-107">Go to Fixed assets > Setup > Fixed asset posting profiles.</span></span>
2. <span data-ttu-id="e857c-108">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="e857c-108">Click New.</span></span>
3. <span data-ttu-id="e857c-109">Skriv ett värde i fältet Bokföringsprofil.</span><span class="sxs-lookup"><span data-stu-id="e857c-109">In the Posting profile field, type a value.</span></span>
4. <span data-ttu-id="e857c-110">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="e857c-110">In the Description field, type a value.</span></span>
    * <span data-ttu-id="e857c-111">Du måste skapa en bokföringsprofil för varje en transaktionstyp som ska användas, när du arbetar med anläggningstillgångar.</span><span class="sxs-lookup"><span data-stu-id="e857c-111">You will need to create a posting profile for each fixed asset transaction type you will be using when working with fixed assets.</span></span>  <span data-ttu-id="e857c-112">Den här uppgifthandboken inleds med anskaffningstransaktionstypen.</span><span class="sxs-lookup"><span data-stu-id="e857c-112">This task guide will start with the Acquisition transaction type.</span></span>  
5. <span data-ttu-id="e857c-113">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="e857c-113">Click Add.</span></span>
6. <span data-ttu-id="e857c-114">Ange eller välj ett värde i fältet Book.</span><span class="sxs-lookup"><span data-stu-id="e857c-114">In the Book field, enter or select a value.</span></span>
    * <span data-ttu-id="e857c-115">I grupperingfältet kan du definiera bokföringsprofilen nedåt till registret (en kontoinställning för varje anläggningstillgång) eller Grupp (en kontoinställning för varje anläggningstillgångsgrupp).</span><span class="sxs-lookup"><span data-stu-id="e857c-115">The Groupings field allows you to define the posting profile down to the Table (one account set up for each fixed asset) or Group (one account set up for each fixed asset group).</span></span>  <span data-ttu-id="e857c-116">För den här uppgiftsguiden lämnas värdet inställt på "Alla" för att gälla för alla anläggningstillgångar med den angivna boken.</span><span class="sxs-lookup"><span data-stu-id="e857c-116">For this task guide I will leave the value set to “All” to apply to all fixed assets with the specified Book.</span></span>  
7. <span data-ttu-id="e857c-117">Ange önskade värden i fältet Huvudkonto.</span><span class="sxs-lookup"><span data-stu-id="e857c-117">In the Main account field, specify the desired values.</span></span>
    * <span data-ttu-id="e857c-118">För anskaffningar kan du ange ett motkonto eller lämna tomt om du vill åsidosätta för att fyllas i för den aktuella transaktionen.</span><span class="sxs-lookup"><span data-stu-id="e857c-118">For Acquisitions, you can enter an offset account or leave it blank to be filled in for the specific transaction.</span></span>    
8. <span data-ttu-id="e857c-119">Välj Anskaffningsjustering i fältet Transaktionstyp.</span><span class="sxs-lookup"><span data-stu-id="e857c-119">In the Transaction type field, select 'Acquisition adjustment'.</span></span>
    * <span data-ttu-id="e857c-120">För anskaffningsjusteringstransaktioner ska du använda samma konton som använda för anskaffningstransaktioner.</span><span class="sxs-lookup"><span data-stu-id="e857c-120">For Acquisition adjustment transactions, we will use the same accounts as used for Acquisition transactions.</span></span>  
9. <span data-ttu-id="e857c-121">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="e857c-121">Click Add.</span></span>
10. <span data-ttu-id="e857c-122">Ange eller välj ett värde i fältet Book.</span><span class="sxs-lookup"><span data-stu-id="e857c-122">In the Book field, enter or select a value.</span></span>
11. <span data-ttu-id="e857c-123">Ange önskade värden i fältet Huvudkonto.</span><span class="sxs-lookup"><span data-stu-id="e857c-123">In the Main account field, specify the desired values.</span></span>
    * <span data-ttu-id="e857c-124">För anskaffningsjusteringar kan du ange ett motkonto eller lämna tomt om du vill åsidosätta för att fyllas i för den aktuella transaktionen.</span><span class="sxs-lookup"><span data-stu-id="e857c-124">For Acquisition adjustments, you can enter an offset account or leave it blank to be filled in for the specific transaction.</span></span>    
12. <span data-ttu-id="e857c-125">Välj Avskrivning i fältet Transaktionstyp.</span><span class="sxs-lookup"><span data-stu-id="e857c-125">In the Transaction type field, select 'Depreciation'.</span></span>
13. <span data-ttu-id="e857c-126">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="e857c-126">Click Add.</span></span>
14. <span data-ttu-id="e857c-127">Ange eller välj ett värde i fältet Book.</span><span class="sxs-lookup"><span data-stu-id="e857c-127">In the Book field, enter or select a value.</span></span>
15. <span data-ttu-id="e857c-128">Ange önskade värden i fältet Huvudkonto.</span><span class="sxs-lookup"><span data-stu-id="e857c-128">In the Main account field, specify the desired values.</span></span>
16. <span data-ttu-id="e857c-129">Ange önskade värden i fältet Motkonto.</span><span class="sxs-lookup"><span data-stu-id="e857c-129">In the Offset account field, specify the desired values.</span></span>
17. <span data-ttu-id="e857c-130">Välj Avskrivningsjustering i fältet Transaktionstyp.</span><span class="sxs-lookup"><span data-stu-id="e857c-130">In the Transaction type field, select 'Depreciation adjustment'.</span></span>
    * <span data-ttu-id="e857c-131">För avskrivningsjusteringstransaktioner ska du använda samma konton som använda för avskrivningstransaktioner.</span><span class="sxs-lookup"><span data-stu-id="e857c-131">For Depreciation adjustment transactions, we will use the same accounts as used for Depreciation transactions.</span></span>  
18. <span data-ttu-id="e857c-132">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="e857c-132">Click Add.</span></span>
19. <span data-ttu-id="e857c-133">Ange eller välj ett värde i fältet Book.</span><span class="sxs-lookup"><span data-stu-id="e857c-133">In the Book field, enter or select a value.</span></span>
20. <span data-ttu-id="e857c-134">Ange önskade värden i fältet Huvudkonto.</span><span class="sxs-lookup"><span data-stu-id="e857c-134">In the Main account field, specify the desired values.</span></span>
21. <span data-ttu-id="e857c-135">Ange önskade värden i fältet Motkonto.</span><span class="sxs-lookup"><span data-stu-id="e857c-135">In the Offset account field, specify the desired values.</span></span>
22. <span data-ttu-id="e857c-136">Välj Avyttrande försäljning i fältet Transaktionstyp.</span><span class="sxs-lookup"><span data-stu-id="e857c-136">In the Transaction type field, select 'Disposal - sale'.</span></span>
23. <span data-ttu-id="e857c-137">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="e857c-137">Click Add.</span></span>
24. <span data-ttu-id="e857c-138">Ange eller välj ett värde i fältet Book.</span><span class="sxs-lookup"><span data-stu-id="e857c-138">In the Book field, enter or select a value.</span></span>
25. <span data-ttu-id="e857c-139">Ange önskade värden i fältet Huvudkonto.</span><span class="sxs-lookup"><span data-stu-id="e857c-139">In the Main account field, specify the desired values.</span></span>
    * <span data-ttu-id="e857c-140">För avyttringar kan du ange ett motkonto eller lämna tomt om du vill åsidosätta för att fyllas i för den aktuella transaktionen.</span><span class="sxs-lookup"><span data-stu-id="e857c-140">For Disposals, you can enter an offset account or leave it blank to be filled in for the specific transaction.</span></span>  
26. <span data-ttu-id="e857c-141">Välj Avyttrande kassation i fältet Transaktionstyp.</span><span class="sxs-lookup"><span data-stu-id="e857c-141">In the Transaction type field, select 'Disposal - scrap'.</span></span>
    * <span data-ttu-id="e857c-142">Vi använder samma konton för Avyttrande försäljning och Avyttrande kassation.</span><span class="sxs-lookup"><span data-stu-id="e857c-142">We will use the same accounts for Disposal sale and Disposal scrap.</span></span>  
27. <span data-ttu-id="e857c-143">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="e857c-143">Click Add.</span></span>
28. <span data-ttu-id="e857c-144">Ange eller välj ett värde i fältet Book.</span><span class="sxs-lookup"><span data-stu-id="e857c-144">In the Book field, enter or select a value.</span></span>
29. <span data-ttu-id="e857c-145">Ange önskade värden i fältet Huvudkonto.</span><span class="sxs-lookup"><span data-stu-id="e857c-145">In the Main account field, specify the desired values.</span></span>
    * <span data-ttu-id="e857c-146">För avyttringar kan du ange ett motkonto eller lämna tomt om du vill åsidosätta för att fyllas i för den aktuella transaktionen.</span><span class="sxs-lookup"><span data-stu-id="e857c-146">For Disposals, you can enter an offset account or leave it blank to be filled in for the specific transaction.</span></span>  
30. <span data-ttu-id="e857c-147">Expandera valet Avyttra.</span><span class="sxs-lookup"><span data-stu-id="e857c-147">Expand the Disposal section.</span></span>
    * <span data-ttu-id="e857c-148">Du måste ställa in förfogandebokföringsprofiler för både försäljning och kassation.</span><span class="sxs-lookup"><span data-stu-id="e857c-148">You must set up disposal posting profiles for both sale and scrap.</span></span>  <span data-ttu-id="e857c-149">Vi inleder med avyttringsförsäljningtransaktioner.</span><span class="sxs-lookup"><span data-stu-id="e857c-149">We will start with disposal sale transactions.</span></span>  
31. <span data-ttu-id="e857c-150">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="e857c-150">Click Add.</span></span>
32. <span data-ttu-id="e857c-151">Ange eller välj ett värde i fältet Book.</span><span class="sxs-lookup"><span data-stu-id="e857c-151">In the Book field, enter or select a value.</span></span>
33. <span data-ttu-id="e857c-152">Välj ”Anskaffningsvärde " i fältet Bokför värde.</span><span class="sxs-lookup"><span data-stu-id="e857c-152">In the Post value field, select 'Acquisition value'.</span></span>
    * <span data-ttu-id="e857c-153">Anskaffningsvärdet används för anskaffnings- och anskaffningsjusteringsvärden för alla år.</span><span class="sxs-lookup"><span data-stu-id="e857c-153">Acquisition value will address Acquisition and Acquisition adjustment values for all years.</span></span>  <span data-ttu-id="e857c-154">Du kan också definiera konton för de transaktionstyperna separat.</span><span class="sxs-lookup"><span data-stu-id="e857c-154">You can also define accounts for these transaction types separately.</span></span>  
    * <span data-ttu-id="e857c-155">Du kan ange avyttringsprocessen om du vill använda andra konton, beroende på om avyttringen leder till en vinst eller en förlust.</span><span class="sxs-lookup"><span data-stu-id="e857c-155">You can set the disposal process to use different accounts depending upon if the disposal results in a gain or loss.</span></span>  <span data-ttu-id="e857c-156">Jag ska ange försäljningvärdetypen till ”Alla” för användning av samma konton för alla typer av avyttringar.</span><span class="sxs-lookup"><span data-stu-id="e857c-156">I will set the Sales value type to “All” to use the same accounts for all types of disposals.</span></span>  
34. <span data-ttu-id="e857c-157">Ange önskade värden i fältet Huvudkonto.</span><span class="sxs-lookup"><span data-stu-id="e857c-157">In the Main account field, specify the desired values.</span></span>
35. <span data-ttu-id="e857c-158">Ange önskade värden i fältet Motkonto.</span><span class="sxs-lookup"><span data-stu-id="e857c-158">In the Offset account field, specify the desired values.</span></span>
36. <span data-ttu-id="e857c-159">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="e857c-159">Click Add.</span></span>
37. <span data-ttu-id="e857c-160">Ange eller välj ett värde i fältet Book.</span><span class="sxs-lookup"><span data-stu-id="e857c-160">In the Book field, enter or select a value.</span></span>
    * <span data-ttu-id="e857c-161">Välj ”Avskrivning (tidigare år)” i fältet Bokför värde.</span><span class="sxs-lookup"><span data-stu-id="e857c-161">In the Post value field, select 'Depreciation (prior years)'.</span></span>  
38. <span data-ttu-id="e857c-162">Ange önskade värden i fältet Huvudkonto.</span><span class="sxs-lookup"><span data-stu-id="e857c-162">In the Main account field, specify the desired values.</span></span>
39. <span data-ttu-id="e857c-163">Ange önskade värden i fältet Motkonto.</span><span class="sxs-lookup"><span data-stu-id="e857c-163">In the Offset account field, specify the desired values.</span></span>
40. <span data-ttu-id="e857c-164">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="e857c-164">Click Add.</span></span>
41. <span data-ttu-id="e857c-165">Ange eller välj ett värde i fältet Book.</span><span class="sxs-lookup"><span data-stu-id="e857c-165">In the Book field, enter or select a value.</span></span>
42. <span data-ttu-id="e857c-166">Välj ”Avskrivning (detta år)” i fältet Bokför värde.</span><span class="sxs-lookup"><span data-stu-id="e857c-166">In the Post value field, select 'Depreciation (this year)'.</span></span>
43. <span data-ttu-id="e857c-167">Ange önskade värden i fältet Huvudkonto.</span><span class="sxs-lookup"><span data-stu-id="e857c-167">In the Main account field, specify the desired values.</span></span>
44. <span data-ttu-id="e857c-168">Ange önskade värden i fältet Motkonto.</span><span class="sxs-lookup"><span data-stu-id="e857c-168">In the Offset account field, specify the desired values.</span></span>
45. <span data-ttu-id="e857c-169">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="e857c-169">Click Add.</span></span>
46. <span data-ttu-id="e857c-170">Ange eller välj ett värde i fältet Book.</span><span class="sxs-lookup"><span data-stu-id="e857c-170">In the Book field, enter or select a value.</span></span>
47. <span data-ttu-id="e857c-171">Välj ”Avskrivningsjusteringar (tidigare år)” i fältet Bokför värde.</span><span class="sxs-lookup"><span data-stu-id="e857c-171">In the Post value field, select 'Depreciation adjustments (prior years)'.</span></span>
48. <span data-ttu-id="e857c-172">Ange önskade värden i fältet Huvudkonto.</span><span class="sxs-lookup"><span data-stu-id="e857c-172">In the Main account field, specify the desired values.</span></span>
49. <span data-ttu-id="e857c-173">Ange önskade värden i fältet Motkonto.</span><span class="sxs-lookup"><span data-stu-id="e857c-173">In the Offset account field, specify the desired values.</span></span>
50. <span data-ttu-id="e857c-174">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="e857c-174">Click Add.</span></span>
51. <span data-ttu-id="e857c-175">Ange eller välj ett värde i fältet Book.</span><span class="sxs-lookup"><span data-stu-id="e857c-175">In the Book field, enter or select a value.</span></span>
52. <span data-ttu-id="e857c-176">Välj ”Avskrivningsjusteringar (detta år)” i fältet Bokför värde.</span><span class="sxs-lookup"><span data-stu-id="e857c-176">In the Post value field, select 'Depreciation adjustments (this year)'.</span></span>
53. <span data-ttu-id="e857c-177">Ange önskade värden i fältet Huvudkonto.</span><span class="sxs-lookup"><span data-stu-id="e857c-177">In the Main account field, specify the desired values.</span></span>
54. <span data-ttu-id="e857c-178">Ange önskade värden i fältet Motkonto.</span><span class="sxs-lookup"><span data-stu-id="e857c-178">In the Offset account field, specify the desired values.</span></span>
55. <span data-ttu-id="e857c-179">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="e857c-179">Click Add.</span></span>
56. <span data-ttu-id="e857c-180">Ange eller välj ett värde i fältet Book.</span><span class="sxs-lookup"><span data-stu-id="e857c-180">In the Book field, enter or select a value.</span></span>
57. <span data-ttu-id="e857c-181">Välj ”Bokfört nettovärde " i fältet Bokför värde.</span><span class="sxs-lookup"><span data-stu-id="e857c-181">In the Post value field, select 'Net book value'.</span></span>
58. <span data-ttu-id="e857c-182">Ange önskade värden i fältet Huvudkonto.</span><span class="sxs-lookup"><span data-stu-id="e857c-182">In the Main account field, specify the desired values.</span></span>
59. <span data-ttu-id="e857c-183">Ange önskade värden i fältet Motkonto.</span><span class="sxs-lookup"><span data-stu-id="e857c-183">In the Offset account field, specify the desired values.</span></span>
60. <span data-ttu-id="e857c-184">Välj ”Kassation” i fältet Försäljning eller kassation.</span><span class="sxs-lookup"><span data-stu-id="e857c-184">In the Sale or scrap field, select 'Scrap'.</span></span>
61. <span data-ttu-id="e857c-185">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="e857c-185">Click Add.</span></span>
62. <span data-ttu-id="e857c-186">Ange eller välj ett värde i fältet Book.</span><span class="sxs-lookup"><span data-stu-id="e857c-186">In the Book field, enter or select a value.</span></span>
63. <span data-ttu-id="e857c-187">Välj ”Anskaffningsvärde " i fältet Bokför värde.</span><span class="sxs-lookup"><span data-stu-id="e857c-187">In the Post value field, select 'Acquisition value'.</span></span>
64. <span data-ttu-id="e857c-188">Ange önskade värden i fältet Huvudkonto.</span><span class="sxs-lookup"><span data-stu-id="e857c-188">In the Main account field, specify the desired values.</span></span>
65. <span data-ttu-id="e857c-189">Ange önskade värden i fältet Motkonto.</span><span class="sxs-lookup"><span data-stu-id="e857c-189">In the Offset account field, specify the desired values.</span></span>
66. <span data-ttu-id="e857c-190">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="e857c-190">Click Add.</span></span>
67. <span data-ttu-id="e857c-191">Ange eller välj ett värde i fältet Book.</span><span class="sxs-lookup"><span data-stu-id="e857c-191">In the Book field, enter or select a value.</span></span>
    * <span data-ttu-id="e857c-192">Välj ”Avskrivning (tidigare år)” i fältet Bokför värde.</span><span class="sxs-lookup"><span data-stu-id="e857c-192">In Post value field, select 'Depreciation (prior years)'.</span></span>  
68. <span data-ttu-id="e857c-193">Ange önskade värden i fältet Huvudkonto.</span><span class="sxs-lookup"><span data-stu-id="e857c-193">In the Main account field, specify the desired values.</span></span>
69. <span data-ttu-id="e857c-194">Ange önskade värden i fältet Motkonto.</span><span class="sxs-lookup"><span data-stu-id="e857c-194">In the Offset account field, specify the desired values.</span></span>
70. <span data-ttu-id="e857c-195">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="e857c-195">Click Add.</span></span>
71. <span data-ttu-id="e857c-196">Ange eller välj ett värde i fältet Book.</span><span class="sxs-lookup"><span data-stu-id="e857c-196">In the Book field, enter or select a value.</span></span>
72. <span data-ttu-id="e857c-197">Välj ”Avskrivning (detta år)” i fältet Bokför värde.</span><span class="sxs-lookup"><span data-stu-id="e857c-197">In the Post value field, select 'Depreciation (this year)'.</span></span>
73. <span data-ttu-id="e857c-198">Ange önskade värden i fältet Huvudkonto.</span><span class="sxs-lookup"><span data-stu-id="e857c-198">In the Main account field, specify the desired values.</span></span>
74. <span data-ttu-id="e857c-199">Ange önskade värden i fältet Motkonto.</span><span class="sxs-lookup"><span data-stu-id="e857c-199">In the Offset account field, specify the desired values.</span></span>
75. <span data-ttu-id="e857c-200">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="e857c-200">Click Add.</span></span>
76. <span data-ttu-id="e857c-201">Ange eller välj ett värde i fältet Book.</span><span class="sxs-lookup"><span data-stu-id="e857c-201">In the Book field, enter or select a value.</span></span>
77. <span data-ttu-id="e857c-202">Välj ”Avskrivningsjusteringar (tidigare år)” i fältet Bokför värde.</span><span class="sxs-lookup"><span data-stu-id="e857c-202">In the Post value field, select 'Depreciation adjustments (prior years)'.</span></span>
78. <span data-ttu-id="e857c-203">Ange önskade värden i fältet Huvudkonto.</span><span class="sxs-lookup"><span data-stu-id="e857c-203">In the Main account field, specify the desired values.</span></span>
79. <span data-ttu-id="e857c-204">Ange önskade värden i fältet Motkonto.</span><span class="sxs-lookup"><span data-stu-id="e857c-204">In the Offset account field, specify the desired values.</span></span>
80. <span data-ttu-id="e857c-205">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="e857c-205">Click Add.</span></span>
81. <span data-ttu-id="e857c-206">Ange eller välj ett värde i fältet Book.</span><span class="sxs-lookup"><span data-stu-id="e857c-206">In the Book field, enter or select a value.</span></span>
82. <span data-ttu-id="e857c-207">Välj ”Avskrivningsjusteringar (detta år)” i fältet Bokför värde.</span><span class="sxs-lookup"><span data-stu-id="e857c-207">In the Post value field, select 'Depreciation adjustments (this year)'.</span></span>
83. <span data-ttu-id="e857c-208">Ange önskade värden i fältet Huvudkonto.</span><span class="sxs-lookup"><span data-stu-id="e857c-208">In the Main account field, specify the desired values.</span></span>
84. <span data-ttu-id="e857c-209">Ange önskade värden i fältet Motkonto.</span><span class="sxs-lookup"><span data-stu-id="e857c-209">In the Offset account field, specify the desired values.</span></span>
85. <span data-ttu-id="e857c-210">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="e857c-210">Click Add.</span></span>
86. <span data-ttu-id="e857c-211">Ange eller välj ett värde i fältet Book.</span><span class="sxs-lookup"><span data-stu-id="e857c-211">In the Book field, enter or select a value.</span></span>
87. <span data-ttu-id="e857c-212">Välj ”Bokfört nettovärde " i fältet Bokför värde.</span><span class="sxs-lookup"><span data-stu-id="e857c-212">In the Post value field, select 'Net book value'.</span></span>
88. <span data-ttu-id="e857c-213">Ange önskade värden i fältet Huvudkonto.</span><span class="sxs-lookup"><span data-stu-id="e857c-213">In the Main account field, specify the desired values.</span></span>
89. <span data-ttu-id="e857c-214">Ange önskade värden i fältet Motkonto.</span><span class="sxs-lookup"><span data-stu-id="e857c-214">In the Offset account field, specify the desired values.</span></span>


