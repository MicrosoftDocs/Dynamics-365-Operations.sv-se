---
title: " Definiera bonusprogram"
description: Den här proceduren visar hur du ställer in ett bonusprogram med två lojalitetnivåer.
author: jashanno
manager: AnnBe
ms.date: 11/14/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4a853287c0795057b09c429ea1c9ad5231e39a33
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4972315"
---
# <a name="define-loyalty-programs"></a><span data-ttu-id="629c1-103"> Definiera bonusprogram</span><span class="sxs-lookup"><span data-stu-id="629c1-103">Define loyalty programs</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="629c1-104">Den här proceduren visar hur du ställer in ett bonusprogram med två lojalitetnivåer.</span><span class="sxs-lookup"><span data-stu-id="629c1-104">This procedure shows how to set up a loyalty program with two loyalty tiers.</span></span> <span data-ttu-id="629c1-105">I proceduren används demonstrationsföretaget USRT.</span><span class="sxs-lookup"><span data-stu-id="629c1-105">This procedure uses the USRT demo data company.</span></span>

1. <span data-ttu-id="629c1-106">Gå till Butik och handel > ..</span><span class="sxs-lookup"><span data-stu-id="629c1-106">Go to Retail and Commerce > ..</span></span> <span data-ttu-id="629c1-107">> Bonusprogram.</span><span class="sxs-lookup"><span data-stu-id="629c1-107">> Loyalty programs.</span></span>
2. <span data-ttu-id="629c1-108">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="629c1-108">Click New.</span></span>
3. <span data-ttu-id="629c1-109">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="629c1-109">In the Name field, type a value.</span></span>
4. <span data-ttu-id="629c1-110">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="629c1-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="629c1-111">Klicka på Lägg till rad.</span><span class="sxs-lookup"><span data-stu-id="629c1-111">Click Add line.</span></span>
6. <span data-ttu-id="629c1-112">Välj ett tal i fältet Nivå.</span><span class="sxs-lookup"><span data-stu-id="629c1-112">In the Level field, enter a number.</span></span>
7. <span data-ttu-id="629c1-113">Ange ett namn för bonusnivån i fältet nivå.</span><span class="sxs-lookup"><span data-stu-id="629c1-113">In the Tier field, enter a name for the loyalty tier.</span></span>
8. <span data-ttu-id="629c1-114">Skriv ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="629c1-114">In the Description field, type a value.</span></span>
9. <span data-ttu-id="629c1-115">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Datumintervall.</span><span class="sxs-lookup"><span data-stu-id="629c1-115">In the Date interval field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="629c1-116">Detta datumintervall bör utvidgas i framtiden.</span><span class="sxs-lookup"><span data-stu-id="629c1-116">This date interval should extend into the future.</span></span> <span data-ttu-id="629c1-117">Om till exempel det tidsintervall som valts för gold-nivån är en ettårsperiod, någon kund som kvalificerar sig för gold-nivån kan få belöningar som tilldelats gold-nivån för ett år.</span><span class="sxs-lookup"><span data-stu-id="629c1-117">For example, if the date interval that is selected for gold tier is a one-year period, any customer who qualifies for the gold tier can receive the rewards that are assigned to the gold tier for one year.</span></span> <span data-ttu-id="629c1-118">Om kunden kvalificerar sig igen för Guld-nivån medan de är på den nivån, utökas utgångsdatumet för denna status med ett år med start från det datum när de kvalificerar sig igen.</span><span class="sxs-lookup"><span data-stu-id="629c1-118">If the customer re-qualifies for the gold tier while they are in the tier, the date that the tier expires is extended by another year from the date when they re-qualify.</span></span>  
10. <span data-ttu-id="629c1-119">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="629c1-119">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="629c1-120">Klicka på Lägg till rad.</span><span class="sxs-lookup"><span data-stu-id="629c1-120">Click Add line.</span></span>
12. <span data-ttu-id="629c1-121">Välj ett tal i fältet Nivå.</span><span class="sxs-lookup"><span data-stu-id="629c1-121">In the Level field, enter a number.</span></span>
13. <span data-ttu-id="629c1-122">Ange ett namn för bonusnivån i fältet nivå.</span><span class="sxs-lookup"><span data-stu-id="629c1-122">In the Tier field, enter a name for the loyalty tier.</span></span>
14. <span data-ttu-id="629c1-123">Skriv ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="629c1-123">In the Description field, type a value.</span></span>
15. <span data-ttu-id="629c1-124">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Datumintervall.</span><span class="sxs-lookup"><span data-stu-id="629c1-124">In the Date interval field, click the drop-down button to open the lookup.</span></span>
16. <span data-ttu-id="629c1-125">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="629c1-125">In the list, click the link in the selected row.</span></span>
17. <span data-ttu-id="629c1-126">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="629c1-126">Click Save.</span></span>
18. <span data-ttu-id="629c1-127">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="629c1-127">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="629c1-128">Nivåregler definierar minsta antalet belöningspoäng som måste tjänas in under en tidsperiod när du vill kvalificera dig för nivån.</span><span class="sxs-lookup"><span data-stu-id="629c1-128">Tier rules define the minimum number of a reward point needed to be earned during a time period to qualify for the tier.</span></span>  
19. <span data-ttu-id="629c1-129">Växla expanderingen av avsnittet Skiktregler.</span><span class="sxs-lookup"><span data-stu-id="629c1-129">Toggle the expansion of the Tier rules section.</span></span>
20. <span data-ttu-id="629c1-130">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="629c1-130">Click New.</span></span>
    * <span data-ttu-id="629c1-131">Du kan använda flera nivåregler för varje nivå.</span><span class="sxs-lookup"><span data-stu-id="629c1-131">You can have more than one tier rule per tier.</span></span> <span data-ttu-id="629c1-132">Du vill kanske ha tre olika kriterier för att tjäna in en nivå – genom att spendera 500 USD under en månad, genom att spendera 1 000 USD under ett år och genom att göra 20 transaktioner under ett år.</span><span class="sxs-lookup"><span data-stu-id="629c1-132">For example, you could have three different criteria to earn a tier; by spending $500 in one month, by spending $1000 over one year, and by having 20 transactions in one year.</span></span> <span data-ttu-id="629c1-133">Om du vill kunna genomföra detta måste du skapa tre nivåregler.</span><span class="sxs-lookup"><span data-stu-id="629c1-133">To do this, you would need to create three tier rules.</span></span>  
21. <span data-ttu-id="629c1-134">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Belöningspoäng.</span><span class="sxs-lookup"><span data-stu-id="629c1-134">In the Reward point field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="629c1-135">Det ska vara en ej inlösbar förmånsbelöningspoäng.</span><span class="sxs-lookup"><span data-stu-id="629c1-135">This should be a non-redeemable loyalty reward point.</span></span>  
22. <span data-ttu-id="629c1-136">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="629c1-136">In the list, click the link in the selected row.</span></span>
23. <span data-ttu-id="629c1-137">Ange ett värde i fältet Lägsta antal utfärdade poäng.</span><span class="sxs-lookup"><span data-stu-id="629c1-137">In the Minimum issued points field, enter a number.</span></span>
    * <span data-ttu-id="629c1-138">Om du vill att alla kunder ska kunna bli medlemmar på den lägsta nivån anger du 0 (noll).</span><span class="sxs-lookup"><span data-stu-id="629c1-138">For the lowest level tier, if all customers qualify simply by participating in the program, enter '0'.</span></span>  
24. <span data-ttu-id="629c1-139">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Intervall för bedömningsdatum.</span><span class="sxs-lookup"><span data-stu-id="629c1-139">In the Evaluation date interval field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="629c1-140">Detta datumintervall bör utvidgas till det förgångna.</span><span class="sxs-lookup"><span data-stu-id="629c1-140">This date interval should extend into the past.</span></span> <span data-ttu-id="629c1-141">Endast poäng som erhållits under detta datumintervall ska göra det möjligt att tillgodoräkna sig lägsta möjliga utlevererade poängvärde.</span><span class="sxs-lookup"><span data-stu-id="629c1-141">Only points earned during this date interval will be counted towards reaching the minimum issued points value.</span></span>  
25. <span data-ttu-id="629c1-142">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="629c1-142">In the list, click the link in the selected row.</span></span>
26. <span data-ttu-id="629c1-143">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="629c1-143">Click Save.</span></span>
27. <span data-ttu-id="629c1-144">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="629c1-144">In the list, find and select the desired record.</span></span>
28. <span data-ttu-id="629c1-145">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="629c1-145">Click New.</span></span>
29. <span data-ttu-id="629c1-146">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Belöningspoäng.</span><span class="sxs-lookup"><span data-stu-id="629c1-146">In the Reward point field, click the drop-down button to open the lookup.</span></span>
30. <span data-ttu-id="629c1-147">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="629c1-147">In the list, click the link in the selected row.</span></span>
31. <span data-ttu-id="629c1-148">Ange ett värde i fältet Lägsta antal utfärdade poäng.</span><span class="sxs-lookup"><span data-stu-id="629c1-148">In the Minimum issued points field, enter a number.</span></span>
32. <span data-ttu-id="629c1-149">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Intervall för bedömningsdatum.</span><span class="sxs-lookup"><span data-stu-id="629c1-149">In the Evaluation date interval field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="629c1-150">Det här datumintervallet bör utökas bakåt i tiden.</span><span class="sxs-lookup"><span data-stu-id="629c1-150">This date interval should extend into the past.</span></span>  
33. <span data-ttu-id="629c1-151">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="629c1-151">In the list, click the link in the selected row.</span></span>
34. <span data-ttu-id="629c1-152">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="629c1-152">Click Save.</span></span>
35. <span data-ttu-id="629c1-153">Klicka på prisgrupper.</span><span class="sxs-lookup"><span data-stu-id="629c1-153">Click Price groups.</span></span>
    * <span data-ttu-id="629c1-154">Om du vill ge förmånskunder rabatter.</span><span class="sxs-lookup"><span data-stu-id="629c1-154">If you want to give loyalty customers discounts.</span></span> <span data-ttu-id="629c1-155">måste du tilldela en eller flera prisgrupper till bonusprogrammet och tilldela prisgrupperna till rabatter.</span><span class="sxs-lookup"><span data-stu-id="629c1-155">you'll need to assign one or more price groups to the loyalty program and assign the price groups to discounts.</span></span> <span data-ttu-id="629c1-156">Det är bästa praxis att inte blanda prisgrupper på olika typer av diskontering av enheter.</span><span class="sxs-lookup"><span data-stu-id="629c1-156">It is a best practice to not mix price groups across different types of discounting entities.</span></span>  <span data-ttu-id="629c1-157">Använd till exempel inte samma prisgrupp för en lojalitetsrabatt och en kanalrabatt.</span><span class="sxs-lookup"><span data-stu-id="629c1-157">For example, don't use the same price group for a loyalty discount and a channel discount.</span></span>  
36. <span data-ttu-id="629c1-158">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Prisgrupp.</span><span class="sxs-lookup"><span data-stu-id="629c1-158">In the Price group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="629c1-159">Prisgrupperna länk överst på sidan är för lojalitetsprogram.</span><span class="sxs-lookup"><span data-stu-id="629c1-159">The Price groups link at the top of the page is for the loyalty program.</span></span> <span data-ttu-id="629c1-160">Länken Prisgrupper på programnivåernas snabbflikar används endast för en specifik lojalitetsnivå.</span><span class="sxs-lookup"><span data-stu-id="629c1-160">The Price groups link in the Program tiers FastTab is for a specific loyalty tier only.</span></span>  
37. <span data-ttu-id="629c1-161">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="629c1-161">In the list, click the link in the selected row.</span></span>
38. <span data-ttu-id="629c1-162">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="629c1-162">Click Save.</span></span>
39. <span data-ttu-id="629c1-163">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="629c1-163">Close the page.</span></span>
40. <span data-ttu-id="629c1-164">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="629c1-164">Click Save.</span></span>

