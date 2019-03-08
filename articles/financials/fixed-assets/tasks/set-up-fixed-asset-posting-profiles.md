---
title: Ställ in bokföringsprofiler för anläggningstillgångar
description: I den här uppgiftsguiden ställer vi in bokföringsprofiler för anläggningstillgångar.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetPosting
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 286c8732c1f2c92d0f16582b0b9de41990280e5a
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "351112"
---
# <a name="set-up-fixed-asset-posting-profiles"></a><span data-ttu-id="42d44-103">Ställ in bokföringsprofiler för anläggningstillgångar</span><span class="sxs-lookup"><span data-stu-id="42d44-103">Set up fixed asset posting profiles</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="42d44-104">I den här uppgiftsguiden ställer vi in bokföringsprofiler för anläggningstillgångar.</span><span class="sxs-lookup"><span data-stu-id="42d44-104">This task guide will set up Fixed asset posting profiles.</span></span>  <span data-ttu-id="42d44-105">Här används revisorrollen och demonstrationdata för den juridiska personen USMF.</span><span class="sxs-lookup"><span data-stu-id="42d44-105">It uses the Accountant role and demo data for the USMF legal entity.</span></span>  <span data-ttu-id="42d44-106">Exempel som angetts i uppgifthandboken, gäller en grundläggande bokföringsprofil, fast bokföringsprofiler måste skapas för dina specifika krav för kontoplanen och om den ekonomiska rapporteringen.</span><span class="sxs-lookup"><span data-stu-id="42d44-106">Examples given in the task guide are for a basic posting profile, though posting profiles must be created for your specific chart of accounts and financial reporting requirements.</span></span>

1. <span data-ttu-id="42d44-107">Gå till Anläggningstillgångar > Inställning > Bokföringsprofiler för anläggningstillgångar.</span><span class="sxs-lookup"><span data-stu-id="42d44-107">Go to Fixed assets > Setup > Fixed asset posting profiles.</span></span>
2. <span data-ttu-id="42d44-108">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="42d44-108">Click New.</span></span>
3. <span data-ttu-id="42d44-109">Skriv ett värde i fältet Bokföringsprofil.</span><span class="sxs-lookup"><span data-stu-id="42d44-109">In the Posting profile field, type a value.</span></span>
4. <span data-ttu-id="42d44-110">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="42d44-110">In the Description field, type a value.</span></span>
    * <span data-ttu-id="42d44-111">Du måste skapa en bokföringsprofil för varje en transaktionstyp som ska användas, när du arbetar med anläggningstillgångar.</span><span class="sxs-lookup"><span data-stu-id="42d44-111">You will need to create a posting profile for each fixed asset transaction type you will be using when working with fixed assets.</span></span>  <span data-ttu-id="42d44-112">Den här uppgifthandboken inleds med anskaffningstransaktionstypen.</span><span class="sxs-lookup"><span data-stu-id="42d44-112">This task guide will start with the Acquisition transaction type.</span></span>  
5. <span data-ttu-id="42d44-113">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="42d44-113">Click Add.</span></span>
6. <span data-ttu-id="42d44-114">Ange eller välj ett värde i fältet Book.</span><span class="sxs-lookup"><span data-stu-id="42d44-114">In the Book field, enter or select a value.</span></span>
    * <span data-ttu-id="42d44-115">I grupperingfältet kan du definiera bokföringsprofilen nedåt till registret (en kontoinställning för varje anläggningstillgång) eller Grupp (en kontoinställning för varje anläggningstillgångsgrupp).</span><span class="sxs-lookup"><span data-stu-id="42d44-115">The Groupings field allows you to define the posting profile down to the Table (one account set up for each fixed asset) or Group (one account set up for each fixed asset group).</span></span>  <span data-ttu-id="42d44-116">För den här uppgiftsguiden lämnas värdet inställt på "Alla" för att gälla för alla anläggningstillgångar med den angivna boken.</span><span class="sxs-lookup"><span data-stu-id="42d44-116">For this task guide I will leave the value set to “All” to apply to all fixed assets with the specified Book.</span></span>  
7. <span data-ttu-id="42d44-117">Ange önskade värden i fältet Huvudkonto.</span><span class="sxs-lookup"><span data-stu-id="42d44-117">In the Main account field, specify the desired values.</span></span>
    * <span data-ttu-id="42d44-118">För anskaffningar kan du ange ett motkonto eller lämna tomt om du vill åsidosätta för att fyllas i för den aktuella transaktionen.</span><span class="sxs-lookup"><span data-stu-id="42d44-118">For Acquisitions, you can enter an offset account or leave it blank to be filled in for the specific transaction.</span></span>    
8. <span data-ttu-id="42d44-119">Välj Anskaffningsjustering i fältet Transaktionstyp.</span><span class="sxs-lookup"><span data-stu-id="42d44-119">In the Transaction type field, select 'Acquisition adjustment'.</span></span>
    * <span data-ttu-id="42d44-120">För anskaffningsjusteringstransaktioner ska du använda samma konton som använda för anskaffningstransaktioner.</span><span class="sxs-lookup"><span data-stu-id="42d44-120">For Acquisition adjustment transactions, we will use the same accounts as used for Acquisition transactions.</span></span>  
9. <span data-ttu-id="42d44-121">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="42d44-121">Click Add.</span></span>
10. <span data-ttu-id="42d44-122">Ange eller välj ett värde i fältet Book.</span><span class="sxs-lookup"><span data-stu-id="42d44-122">In the Book field, enter or select a value.</span></span>
11. <span data-ttu-id="42d44-123">Ange önskade värden i fältet Huvudkonto.</span><span class="sxs-lookup"><span data-stu-id="42d44-123">In the Main account field, specify the desired values.</span></span>
    * <span data-ttu-id="42d44-124">För anskaffningsjusteringar kan du ange ett motkonto eller lämna tomt om du vill åsidosätta för att fyllas i för den aktuella transaktionen.</span><span class="sxs-lookup"><span data-stu-id="42d44-124">For Acquisition adjustments, you can enter an offset account or leave it blank to be filled in for the specific transaction.</span></span>    
12. <span data-ttu-id="42d44-125">Välj Avskrivning i fältet Transaktionstyp.</span><span class="sxs-lookup"><span data-stu-id="42d44-125">In the Transaction type field, select 'Depreciation'.</span></span>
13. <span data-ttu-id="42d44-126">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="42d44-126">Click Add.</span></span>
14. <span data-ttu-id="42d44-127">Ange eller välj ett värde i fältet Book.</span><span class="sxs-lookup"><span data-stu-id="42d44-127">In the Book field, enter or select a value.</span></span>
15. <span data-ttu-id="42d44-128">Ange önskade värden i fältet Huvudkonto.</span><span class="sxs-lookup"><span data-stu-id="42d44-128">In the Main account field, specify the desired values.</span></span>
16. <span data-ttu-id="42d44-129">Ange önskade värden i fältet Motkonto.</span><span class="sxs-lookup"><span data-stu-id="42d44-129">In the Offset account field, specify the desired values.</span></span>
17. <span data-ttu-id="42d44-130">Välj Avskrivningsjustering i fältet Transaktionstyp.</span><span class="sxs-lookup"><span data-stu-id="42d44-130">In the Transaction type field, select 'Depreciation adjustment'.</span></span>
    * <span data-ttu-id="42d44-131">För avskrivningsjusteringstransaktioner ska du använda samma konton som använda för avskrivningstransaktioner.</span><span class="sxs-lookup"><span data-stu-id="42d44-131">For Depreciation adjustment transactions, we will use the same accounts as used for Depreciation transactions.</span></span>  
18. <span data-ttu-id="42d44-132">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="42d44-132">Click Add.</span></span>
19. <span data-ttu-id="42d44-133">Ange eller välj ett värde i fältet Book.</span><span class="sxs-lookup"><span data-stu-id="42d44-133">In the Book field, enter or select a value.</span></span>
20. <span data-ttu-id="42d44-134">Ange önskade värden i fältet Huvudkonto.</span><span class="sxs-lookup"><span data-stu-id="42d44-134">In the Main account field, specify the desired values.</span></span>
21. <span data-ttu-id="42d44-135">Ange önskade värden i fältet Motkonto.</span><span class="sxs-lookup"><span data-stu-id="42d44-135">In the Offset account field, specify the desired values.</span></span>
22. <span data-ttu-id="42d44-136">Välj Avyttrande försäljning i fältet Transaktionstyp.</span><span class="sxs-lookup"><span data-stu-id="42d44-136">In the Transaction type field, select 'Disposal - sale'.</span></span>
23. <span data-ttu-id="42d44-137">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="42d44-137">Click Add.</span></span>
24. <span data-ttu-id="42d44-138">Ange eller välj ett värde i fältet Book.</span><span class="sxs-lookup"><span data-stu-id="42d44-138">In the Book field, enter or select a value.</span></span>
25. <span data-ttu-id="42d44-139">Ange önskade värden i fältet Huvudkonto.</span><span class="sxs-lookup"><span data-stu-id="42d44-139">In the Main account field, specify the desired values.</span></span>
    * <span data-ttu-id="42d44-140">För avyttringar kan du ange ett motkonto eller lämna tomt om du vill åsidosätta för att fyllas i för den aktuella transaktionen.</span><span class="sxs-lookup"><span data-stu-id="42d44-140">For Disposals, you can enter an offset account or leave it blank to be filled in for the specific transaction.</span></span>  
26. <span data-ttu-id="42d44-141">Välj Avyttrande kassation i fältet Transaktionstyp.</span><span class="sxs-lookup"><span data-stu-id="42d44-141">In the Transaction type field, select 'Disposal - scrap'.</span></span>
    * <span data-ttu-id="42d44-142">Vi använder samma konton för Avyttrande försäljning och Avyttrande kassation.</span><span class="sxs-lookup"><span data-stu-id="42d44-142">We will use the same accounts for Disposal sale and Disposal scrap.</span></span>  
27. <span data-ttu-id="42d44-143">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="42d44-143">Click Add.</span></span>
28. <span data-ttu-id="42d44-144">Ange eller välj ett värde i fältet Book.</span><span class="sxs-lookup"><span data-stu-id="42d44-144">In the Book field, enter or select a value.</span></span>
29. <span data-ttu-id="42d44-145">Ange önskade värden i fältet Huvudkonto.</span><span class="sxs-lookup"><span data-stu-id="42d44-145">In the Main account field, specify the desired values.</span></span>
    * <span data-ttu-id="42d44-146">För avyttringar kan du ange ett motkonto eller lämna tomt om du vill åsidosätta för att fyllas i för den aktuella transaktionen.</span><span class="sxs-lookup"><span data-stu-id="42d44-146">For Disposals, you can enter an offset account or leave it blank to be filled in for the specific transaction.</span></span>  
30. <span data-ttu-id="42d44-147">Expandera valet Avyttra.</span><span class="sxs-lookup"><span data-stu-id="42d44-147">Expand the Disposal section.</span></span>
    * <span data-ttu-id="42d44-148">Du måste ställa in förfogandebokföringsprofiler för både försäljning och kassation.</span><span class="sxs-lookup"><span data-stu-id="42d44-148">You must set up disposal posting profiles for both sale and scrap.</span></span>  <span data-ttu-id="42d44-149">Vi inleder med avyttringsförsäljningtransaktioner.</span><span class="sxs-lookup"><span data-stu-id="42d44-149">We will start with disposal sale transactions.</span></span>  
31. <span data-ttu-id="42d44-150">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="42d44-150">Click Add.</span></span>
32. <span data-ttu-id="42d44-151">Ange eller välj ett värde i fältet Book.</span><span class="sxs-lookup"><span data-stu-id="42d44-151">In the Book field, enter or select a value.</span></span>
33. <span data-ttu-id="42d44-152">Välj ”Anskaffningsvärde " i fältet Bokför värde.</span><span class="sxs-lookup"><span data-stu-id="42d44-152">In the Post value field, select 'Acquisition value'.</span></span>
    * <span data-ttu-id="42d44-153">Anskaffningsvärdet används för anskaffnings- och anskaffningsjusteringsvärden för alla år.</span><span class="sxs-lookup"><span data-stu-id="42d44-153">Acquisition value will address Acquisition and Acquisition adjustment values for all years.</span></span>  <span data-ttu-id="42d44-154">Du kan också definiera konton för de transaktionstyperna separat.</span><span class="sxs-lookup"><span data-stu-id="42d44-154">You can also define accounts for these transaction types separately.</span></span>  
    * <span data-ttu-id="42d44-155">Du kan ange avyttringsprocessen om du vill använda andra konton, beroende på om avyttringen leder till en vinst eller en förlust.</span><span class="sxs-lookup"><span data-stu-id="42d44-155">You can set the disposal process to use different accounts depending upon if the disposal results in a gain or loss.</span></span>  <span data-ttu-id="42d44-156">Jag ska ange försäljningvärdetypen till ”Alla” för användning av samma konton för alla typer av avyttringar.</span><span class="sxs-lookup"><span data-stu-id="42d44-156">I will set the Sales value type to “All” to use the same accounts for all types of disposals.</span></span>  
34. <span data-ttu-id="42d44-157">Ange önskade värden i fältet Huvudkonto.</span><span class="sxs-lookup"><span data-stu-id="42d44-157">In the Main account field, specify the desired values.</span></span>
35. <span data-ttu-id="42d44-158">Ange önskade värden i fältet Motkonto.</span><span class="sxs-lookup"><span data-stu-id="42d44-158">In the Offset account field, specify the desired values.</span></span>
36. <span data-ttu-id="42d44-159">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="42d44-159">Click Add.</span></span>
37. <span data-ttu-id="42d44-160">Ange eller välj ett värde i fältet Book.</span><span class="sxs-lookup"><span data-stu-id="42d44-160">In the Book field, enter or select a value.</span></span>
    * <span data-ttu-id="42d44-161">Välj ”Avskrivning (tidigare år)” i fältet Bokför värde.</span><span class="sxs-lookup"><span data-stu-id="42d44-161">In the Post value field, select 'Depreciation (prior years)'.</span></span>  
38. <span data-ttu-id="42d44-162">Ange önskade värden i fältet Huvudkonto.</span><span class="sxs-lookup"><span data-stu-id="42d44-162">In the Main account field, specify the desired values.</span></span>
39. <span data-ttu-id="42d44-163">Ange önskade värden i fältet Motkonto.</span><span class="sxs-lookup"><span data-stu-id="42d44-163">In the Offset account field, specify the desired values.</span></span>
40. <span data-ttu-id="42d44-164">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="42d44-164">Click Add.</span></span>
41. <span data-ttu-id="42d44-165">Ange eller välj ett värde i fältet Book.</span><span class="sxs-lookup"><span data-stu-id="42d44-165">In the Book field, enter or select a value.</span></span>
42. <span data-ttu-id="42d44-166">Välj ”Avskrivning (detta år)” i fältet Bokför värde.</span><span class="sxs-lookup"><span data-stu-id="42d44-166">In the Post value field, select 'Depreciation (this year)'.</span></span>
43. <span data-ttu-id="42d44-167">Ange önskade värden i fältet Huvudkonto.</span><span class="sxs-lookup"><span data-stu-id="42d44-167">In the Main account field, specify the desired values.</span></span>
44. <span data-ttu-id="42d44-168">Ange önskade värden i fältet Motkonto.</span><span class="sxs-lookup"><span data-stu-id="42d44-168">In the Offset account field, specify the desired values.</span></span>
45. <span data-ttu-id="42d44-169">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="42d44-169">Click Add.</span></span>
46. <span data-ttu-id="42d44-170">Ange eller välj ett värde i fältet Book.</span><span class="sxs-lookup"><span data-stu-id="42d44-170">In the Book field, enter or select a value.</span></span>
47. <span data-ttu-id="42d44-171">Välj ”Avskrivningsjusteringar (tidigare år)” i fältet Bokför värde.</span><span class="sxs-lookup"><span data-stu-id="42d44-171">In the Post value field, select 'Depreciation adjustments (prior years)'.</span></span>
48. <span data-ttu-id="42d44-172">Ange önskade värden i fältet Huvudkonto.</span><span class="sxs-lookup"><span data-stu-id="42d44-172">In the Main account field, specify the desired values.</span></span>
49. <span data-ttu-id="42d44-173">Ange önskade värden i fältet Motkonto.</span><span class="sxs-lookup"><span data-stu-id="42d44-173">In the Offset account field, specify the desired values.</span></span>
50. <span data-ttu-id="42d44-174">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="42d44-174">Click Add.</span></span>
51. <span data-ttu-id="42d44-175">Ange eller välj ett värde i fältet Book.</span><span class="sxs-lookup"><span data-stu-id="42d44-175">In the Book field, enter or select a value.</span></span>
52. <span data-ttu-id="42d44-176">Välj ”Avskrivningsjusteringar (detta år)” i fältet Bokför värde.</span><span class="sxs-lookup"><span data-stu-id="42d44-176">In the Post value field, select 'Depreciation adjustments (this year)'.</span></span>
53. <span data-ttu-id="42d44-177">Ange önskade värden i fältet Huvudkonto.</span><span class="sxs-lookup"><span data-stu-id="42d44-177">In the Main account field, specify the desired values.</span></span>
54. <span data-ttu-id="42d44-178">Ange önskade värden i fältet Motkonto.</span><span class="sxs-lookup"><span data-stu-id="42d44-178">In the Offset account field, specify the desired values.</span></span>
55. <span data-ttu-id="42d44-179">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="42d44-179">Click Add.</span></span>
56. <span data-ttu-id="42d44-180">Ange eller välj ett värde i fältet Book.</span><span class="sxs-lookup"><span data-stu-id="42d44-180">In the Book field, enter or select a value.</span></span>
57. <span data-ttu-id="42d44-181">Välj ”Bokfört nettovärde " i fältet Bokför värde.</span><span class="sxs-lookup"><span data-stu-id="42d44-181">In the Post value field, select 'Net book value'.</span></span>
58. <span data-ttu-id="42d44-182">Ange önskade värden i fältet Huvudkonto.</span><span class="sxs-lookup"><span data-stu-id="42d44-182">In the Main account field, specify the desired values.</span></span>
59. <span data-ttu-id="42d44-183">Ange önskade värden i fältet Motkonto.</span><span class="sxs-lookup"><span data-stu-id="42d44-183">In the Offset account field, specify the desired values.</span></span>
60. <span data-ttu-id="42d44-184">Välj ”Kassation” i fältet Försäljning eller kassation.</span><span class="sxs-lookup"><span data-stu-id="42d44-184">In the Sale or scrap field, select 'Scrap'.</span></span>
61. <span data-ttu-id="42d44-185">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="42d44-185">Click Add.</span></span>
62. <span data-ttu-id="42d44-186">Ange eller välj ett värde i fältet Book.</span><span class="sxs-lookup"><span data-stu-id="42d44-186">In the Book field, enter or select a value.</span></span>
63. <span data-ttu-id="42d44-187">Välj ”Anskaffningsvärde " i fältet Bokför värde.</span><span class="sxs-lookup"><span data-stu-id="42d44-187">In the Post value field, select 'Acquisition value'.</span></span>
64. <span data-ttu-id="42d44-188">Ange önskade värden i fältet Huvudkonto.</span><span class="sxs-lookup"><span data-stu-id="42d44-188">In the Main account field, specify the desired values.</span></span>
65. <span data-ttu-id="42d44-189">Ange önskade värden i fältet Motkonto.</span><span class="sxs-lookup"><span data-stu-id="42d44-189">In the Offset account field, specify the desired values.</span></span>
66. <span data-ttu-id="42d44-190">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="42d44-190">Click Add.</span></span>
67. <span data-ttu-id="42d44-191">Ange eller välj ett värde i fältet Book.</span><span class="sxs-lookup"><span data-stu-id="42d44-191">In the Book field, enter or select a value.</span></span>
    * <span data-ttu-id="42d44-192">Välj ”Avskrivning (tidigare år)” i fältet Bokför värde.</span><span class="sxs-lookup"><span data-stu-id="42d44-192">In Post value field, select 'Depreciation (prior years)'.</span></span>  
68. <span data-ttu-id="42d44-193">Ange önskade värden i fältet Huvudkonto.</span><span class="sxs-lookup"><span data-stu-id="42d44-193">In the Main account field, specify the desired values.</span></span>
69. <span data-ttu-id="42d44-194">Ange önskade värden i fältet Motkonto.</span><span class="sxs-lookup"><span data-stu-id="42d44-194">In the Offset account field, specify the desired values.</span></span>
70. <span data-ttu-id="42d44-195">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="42d44-195">Click Add.</span></span>
71. <span data-ttu-id="42d44-196">Ange eller välj ett värde i fältet Book.</span><span class="sxs-lookup"><span data-stu-id="42d44-196">In the Book field, enter or select a value.</span></span>
72. <span data-ttu-id="42d44-197">Välj ”Avskrivning (detta år)” i fältet Bokför värde.</span><span class="sxs-lookup"><span data-stu-id="42d44-197">In the Post value field, select 'Depreciation (this year)'.</span></span>
73. <span data-ttu-id="42d44-198">Ange önskade värden i fältet Huvudkonto.</span><span class="sxs-lookup"><span data-stu-id="42d44-198">In the Main account field, specify the desired values.</span></span>
74. <span data-ttu-id="42d44-199">Ange önskade värden i fältet Motkonto.</span><span class="sxs-lookup"><span data-stu-id="42d44-199">In the Offset account field, specify the desired values.</span></span>
75. <span data-ttu-id="42d44-200">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="42d44-200">Click Add.</span></span>
76. <span data-ttu-id="42d44-201">Ange eller välj ett värde i fältet Book.</span><span class="sxs-lookup"><span data-stu-id="42d44-201">In the Book field, enter or select a value.</span></span>
77. <span data-ttu-id="42d44-202">Välj ”Avskrivningsjusteringar (tidigare år)” i fältet Bokför värde.</span><span class="sxs-lookup"><span data-stu-id="42d44-202">In the Post value field, select 'Depreciation adjustments (prior years)'.</span></span>
78. <span data-ttu-id="42d44-203">Ange önskade värden i fältet Huvudkonto.</span><span class="sxs-lookup"><span data-stu-id="42d44-203">In the Main account field, specify the desired values.</span></span>
79. <span data-ttu-id="42d44-204">Ange önskade värden i fältet Motkonto.</span><span class="sxs-lookup"><span data-stu-id="42d44-204">In the Offset account field, specify the desired values.</span></span>
80. <span data-ttu-id="42d44-205">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="42d44-205">Click Add.</span></span>
81. <span data-ttu-id="42d44-206">Ange eller välj ett värde i fältet Book.</span><span class="sxs-lookup"><span data-stu-id="42d44-206">In the Book field, enter or select a value.</span></span>
82. <span data-ttu-id="42d44-207">Välj ”Avskrivningsjusteringar (detta år)” i fältet Bokför värde.</span><span class="sxs-lookup"><span data-stu-id="42d44-207">In the Post value field, select 'Depreciation adjustments (this year)'.</span></span>
83. <span data-ttu-id="42d44-208">Ange önskade värden i fältet Huvudkonto.</span><span class="sxs-lookup"><span data-stu-id="42d44-208">In the Main account field, specify the desired values.</span></span>
84. <span data-ttu-id="42d44-209">Ange önskade värden i fältet Motkonto.</span><span class="sxs-lookup"><span data-stu-id="42d44-209">In the Offset account field, specify the desired values.</span></span>
85. <span data-ttu-id="42d44-210">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="42d44-210">Click Add.</span></span>
86. <span data-ttu-id="42d44-211">Ange eller välj ett värde i fältet Book.</span><span class="sxs-lookup"><span data-stu-id="42d44-211">In the Book field, enter or select a value.</span></span>
87. <span data-ttu-id="42d44-212">Välj ”Bokfört nettovärde " i fältet Bokför värde.</span><span class="sxs-lookup"><span data-stu-id="42d44-212">In the Post value field, select 'Net book value'.</span></span>
88. <span data-ttu-id="42d44-213">Ange önskade värden i fältet Huvudkonto.</span><span class="sxs-lookup"><span data-stu-id="42d44-213">In the Main account field, specify the desired values.</span></span>
89. <span data-ttu-id="42d44-214">Ange önskade värden i fältet Motkonto.</span><span class="sxs-lookup"><span data-stu-id="42d44-214">In the Offset account field, specify the desired values.</span></span>

