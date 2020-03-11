---
title: Utveckla en struktur för kompensation
description: Den här artikeln leder dig genom att skapa en fast kompensationsplan och registrera anställda i planen genom behörighetsregler.
author: andreabichsel
manager: AnnBe
ms.date: 02/10/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: DefaultDashboard, HcmCompensationWorkspace, HcmCompFixedPlansPart, HRMCompFixedPlanTable, HRMCompCreateGridDialog, HRCCompGridView, HRMCompEligibility,  HRCCompGrid
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 124d0f7f83feebabf622f00732c25bfa0f6eccdd
ms.sourcegitcommit: de715b7fda2f1548f2f443b9e0f6d09f5b881d61
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/10/2020
ms.locfileid: "3034273"
---
# <a name="develop-a-compensation-structure"></a><span data-ttu-id="29bb3-103">Utveckla en struktur för kompensation</span><span class="sxs-lookup"><span data-stu-id="29bb3-103">Develop a compensation structure</span></span>

<span data-ttu-id="29bb3-104">Den här artikeln leder dig genom att skapa en fast kompensationsplan och registrera anställda i planen genom behörighetsregler.</span><span class="sxs-lookup"><span data-stu-id="29bb3-104">This article walks you through creating a fixed compensation plan and enrolling employees in the plan through eligibility rules.</span></span> <span data-ttu-id="29bb3-105">I den här artikeln används USMF demodata och gäller kompensations- och förmånsansvariga.</span><span class="sxs-lookup"><span data-stu-id="29bb3-105">This article uses the USMF demo data and applies to Compensation and Benefits Managers.</span></span>

## <a name="create-a-fixed-compensation-plan"></a><span data-ttu-id="29bb3-106">Skapa en fast kompensationsplan</span><span class="sxs-lookup"><span data-stu-id="29bb3-106">Create a fixed compensation plan</span></span>

1. <span data-ttu-id="29bb3-107">Välj **Kompensationshantering**.</span><span class="sxs-lookup"><span data-stu-id="29bb3-107">Select **Compensation management**.</span></span>

2. <span data-ttu-id="29bb3-108">Välj **Planer för fast kompensation**.</span><span class="sxs-lookup"><span data-stu-id="29bb3-108">Select **Fixed compensation plans**.</span></span>

3. <span data-ttu-id="29bb3-109">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="29bb3-109">Select **New**.</span></span>

4. <span data-ttu-id="29bb3-110">I fältet **Plan** ange ett värde.</span><span class="sxs-lookup"><span data-stu-id="29bb3-110">In the **Plan** field, enter a value.</span></span>

5. <span data-ttu-id="29bb3-111">I fältet **Beskrivning** anger du ett värde.</span><span class="sxs-lookup"><span data-stu-id="29bb3-111">In the **Description** field, enter a value.</span></span>

6. <span data-ttu-id="29bb3-112">Ange ett datum i fältet **Giltighetsdatum**.</span><span class="sxs-lookup"><span data-stu-id="29bb3-112">In the **Effective date** field, enter a date.</span></span>

7. <span data-ttu-id="29bb3-113">I fältet **Typ** välj om den fasta kompensationsplanen är en **Band-**, **Grad-** eller **Steg**-plan.</span><span class="sxs-lookup"><span data-stu-id="29bb3-113">In the **Type** field, select whether the fixed compensation plan is a **Band**, **Grade**, or **Step** plan.</span></span>

8. <span data-ttu-id="29bb3-114">Kryssrutan **Rekommendation tillåts** fungerar som ett standardvärde för de åtgärder som läggs till i den här planen i en processhändelse.</span><span class="sxs-lookup"><span data-stu-id="29bb3-114">The **Recommendation allowed** checkbox acts as a default value for any actions added to this plan in a Process event.</span></span> <span data-ttu-id="29bb3-115">Om du tillåter rekommendationer kan du åsidosätta det beräknade riktlinjebeloppet när du bearbetar kompensation.</span><span class="sxs-lookup"><span data-stu-id="29bb3-115">Allowing recommendations enables you to override the calculated guideline amount when processing compensation.</span></span>

9. <span data-ttu-id="29bb3-116">Med **Tolerans utanför intervallet** kan du ange hur du vill hantera kompensationsbelopp som ligger utanför det angivna kompensationsstrukturintervallet för den angivna nivån.</span><span class="sxs-lookup"><span data-stu-id="29bb3-116">The **Out of range tolerance** field allows you to specify how you want to handle compensation amounts that fall outside of the specified compensation structure range for the given level.</span></span> <span data-ttu-id="29bb3-117">Om du ställer in fälten **Tolerans utanför intervallet** till **Ingen** kan du använda ett kompensationsbelopp.</span><span class="sxs-lookup"><span data-stu-id="29bb3-117">Setting the **Out of range tolerance** field to **None** allows you to use any compensation amount.</span></span> <span data-ttu-id="29bb3-118">**Mjuk tolerans** varnar användarna om kompensationsbeloppet är lägre än minimum eller högre än de maximala referenspunktsbeloppen för den nivån.</span><span class="sxs-lookup"><span data-stu-id="29bb3-118">**Soft tolerance** warns users if the compensation amount is less than the minimum or greater than the maximum reference point amounts for that level.</span></span> <span data-ttu-id="29bb3-119">Användare kan ignorera varningen och fortsätta.</span><span class="sxs-lookup"><span data-stu-id="29bb3-119">Users can ignore the warning and continue.</span></span> <span data-ttu-id="29bb3-120">En **Hård tolerans** skapar ett fel om en medarbetares kompensation anges utanför den minsta och högsta nivån för referenspunkten och justerar automatiskt en medarbetares kompensation så att den är inom intervallet.</span><span class="sxs-lookup"><span data-stu-id="29bb3-120">**Hard tolerance** generates an error if an employee's compensation is outside the minimum and maximum reference points for the level and will automatically adjust the employee's compensation to fall within the range.</span></span>

10. <span data-ttu-id="29bb3-121">Fältet **anställningsregel** beräknas en medarbetares kompensation under en processhändelse.</span><span class="sxs-lookup"><span data-stu-id="29bb3-121">The **Hire rule** field calculates an employee's compensation during a process event.</span></span> <span data-ttu-id="29bb3-122">En **Anställningsregel** av **Procent** beräknas en ökning som är proportionell mot tidslängden som arbetaren har varit anställd i cykeln.</span><span class="sxs-lookup"><span data-stu-id="29bb3-122">A **Hire rule** of **Percent** calculates an increase that's prorated for the length of the time the worker has been employed in the cycle.</span></span>

11. <span data-ttu-id="29bb3-123">Ange ett värde i fältet **Valuta**.</span><span class="sxs-lookup"><span data-stu-id="29bb3-123">In the **Currency** field, type a value.</span></span>

12. <span data-ttu-id="29bb3-124">Ange eller välj ett värde i fältet **Lönesatskonvertering**.</span><span class="sxs-lookup"><span data-stu-id="29bb3-124">In the **Pay rate conversion** field, enter or select a value.</span></span>

13. <span data-ttu-id="29bb3-125">Visa avsnittet **Matris för utnyttjande inom löneintervall**.</span><span class="sxs-lookup"><span data-stu-id="29bb3-125">Expand the **Range utilization matrix** section.</span></span> <span data-ttu-id="29bb3-126">Lägg eventuellt till poster med intervallutnyttjande för att få medarbetare att komma snabbare till mittpunkten och långsammare till maxvärdet i ett intervall.</span><span class="sxs-lookup"><span data-stu-id="29bb3-126">Optionally, add range utilization records to get employees to their midpoint faster and slow them from reaching the maximum of their range.</span></span>

14. <span data-ttu-id="29bb3-127">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="29bb3-127">Select **Save**.</span></span> <span data-ttu-id="29bb3-128">Då aktiveras knappen **Ställ in kompensation** och fortsätter definiera din kompensationsstruktur för planen.</span><span class="sxs-lookup"><span data-stu-id="29bb3-128">This enables the **Set up compensation** button and continue defining your compensation structure for the plan.</span></span>

15. <span data-ttu-id="29bb3-129">Välj **Ställ in kompensationsplaner**.</span><span class="sxs-lookup"><span data-stu-id="29bb3-129">Select **Set up compensation**.</span></span> <span data-ttu-id="29bb3-130">Du kan skapa en kompensationsstruktur genom att använda en av dessa tre metoder:</span><span class="sxs-lookup"><span data-stu-id="29bb3-130">You can create a compensation structure by using one of these three methods:</span></span>

    - <span data-ttu-id="29bb3-131">Skapa en helt ny struktur genom att välja en uppsättning referenspunkter och lägga till nivåer om du vill skapa dina egna strukturer.</span><span class="sxs-lookup"><span data-stu-id="29bb3-131">Create a completely new structure by selecting a set of reference points and adding the levels to create your own structure.</span></span>
    - <span data-ttu-id="29bb3-132">Kopiera en kompensationsstruktur från en befintlig plan som utgångspunkt och ändra den för den nya planen.</span><span class="sxs-lookup"><span data-stu-id="29bb3-132">Copy a compensation structure from an existing plan as a starting point and modify it for the new plan.</span></span>
    - <span data-ttu-id="29bb3-133">Välj ett befintligt kompensationsrutnät.</span><span class="sxs-lookup"><span data-stu-id="29bb3-133">Select an existing compensation grid.</span></span> <span data-ttu-id="29bb3-134">Om en annan plan redan använder kompensationsnätet återspeglar den andra planen alla ändringar du gör i nätet.</span><span class="sxs-lookup"><span data-stu-id="29bb3-134">If another plan already uses the compensation grid, the other plan also reflects any changes you make to the grid.</span></span>

16. <span data-ttu-id="29bb3-135">Välj **Skapa ny från befintlig kompensationsmatris**.</span><span class="sxs-lookup"><span data-stu-id="29bb3-135">Select **Create new from existing compensation matrix**.</span></span>

17. <span data-ttu-id="29bb3-136">Ange eller välj ett värde i fältet **Kopiera från rutnät**.</span><span class="sxs-lookup"><span data-stu-id="29bb3-136">In the **Copy from grid** field, enter or select a value.</span></span> <span data-ttu-id="29bb3-137">Du kan även ändra namnet på det nya kompensationsrutnätet, som skapas som en kopia av det valda rutnätet.</span><span class="sxs-lookup"><span data-stu-id="29bb3-137">Optionally, you can change the name of the new compensation grid that you create by copying the selected grid.</span></span>

18. <span data-ttu-id="29bb3-138">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="29bb3-138">Select **OK**.</span></span>

19. <span data-ttu-id="29bb3-139">Välj **Massförändring**.</span><span class="sxs-lookup"><span data-stu-id="29bb3-139">Select **Mass change**.</span></span> <span data-ttu-id="29bb3-140">**Massändringar** låter dig underhålla kompensationsmatrisbeloppen genom att du anger procent eller ett fast belopp som ökning för en eller flera nivåer eller referenspunkter.</span><span class="sxs-lookup"><span data-stu-id="29bb3-140">**Mass change** allows you to maintain the compensation matrix amounts by applying a percent or flat amount increase to one or more levels or reference points.</span></span>

20. <span data-ttu-id="29bb3-141">Ange ett tal i fältet **Justeringsbelopp**.</span><span class="sxs-lookup"><span data-stu-id="29bb3-141">In the **Adjustment amount** field, enter a number.</span></span>

21. <span data-ttu-id="29bb3-142">Markera eller avmarkera alla rader i listan.</span><span class="sxs-lookup"><span data-stu-id="29bb3-142">In the list, mark or unmark all rows.</span></span>

22. <span data-ttu-id="29bb3-143">Klicka på **Använd i rutnät**.</span><span class="sxs-lookup"><span data-stu-id="29bb3-143">Click **Apply to grid**.</span></span>

23. <span data-ttu-id="29bb3-144">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="29bb3-144">Close the page.</span></span> <span data-ttu-id="29bb3-145">När du har skapat kompensationsstrukturen kan du välja vilka av referenspunkterna som ska användas som kontrollpunkt för den fasta kompensationsplanen.</span><span class="sxs-lookup"><span data-stu-id="29bb3-145">After you create the compensation structure, you can select which of the reference points to use as the control point for the fixed compensation plan.</span></span> <span data-ttu-id="29bb3-146">Kontrollpunkten används för att beräkna en medarbetares jämförelsekvot för löneberäkning.</span><span class="sxs-lookup"><span data-stu-id="29bb3-146">The control point is used to calculate an employee's Compa Ratio.</span></span>

24. <span data-ttu-id="29bb3-147">Ange eller välj ett värde i fältet **Kontrollpunkt**.</span><span class="sxs-lookup"><span data-stu-id="29bb3-147">In the **Control point** field, enter or select a value.</span></span>

25. <span data-ttu-id="29bb3-148">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="29bb3-148">Close the page.</span></span>

## <a name="create-an-eligibility-rule-for-the-fixed-compensation-plan"></a><span data-ttu-id="29bb3-149">Skapa en berättiganderegel för den fasta kompensationsplanen</span><span class="sxs-lookup"><span data-stu-id="29bb3-149">Create an eligibility rule for the fixed compensation plan</span></span>

<span data-ttu-id="29bb3-150">Du kan inte tilldela en fast kompensationsplan till en anställd förrän du definierar behörighetsregler för planen.</span><span class="sxs-lookup"><span data-stu-id="29bb3-150">You can't assign a fixed compensation plan to an employee until you define eligibility rules for the plan.</span></span>  

1. <span data-ttu-id="29bb3-151">Visa **berättiganderegler**.</span><span class="sxs-lookup"><span data-stu-id="29bb3-151">Select **Eligibility rules**.</span></span>

2. <span data-ttu-id="29bb3-152">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="29bb3-152">Select **New**.</span></span>

3. <span data-ttu-id="29bb3-153">I fältet **Berättigande** anger ett värde.</span><span class="sxs-lookup"><span data-stu-id="29bb3-153">In the **Eligibility** field, enter a value.</span></span>

4. <span data-ttu-id="29bb3-154">I fältet **Beskrivning** anger du ett värde.</span><span class="sxs-lookup"><span data-stu-id="29bb3-154">In the **Description** field, enter a value.</span></span>

5. <span data-ttu-id="29bb3-155">Ange ett datum i fältet **Giltighetsdatum**.</span><span class="sxs-lookup"><span data-stu-id="29bb3-155">In the **Effective date** field, enter a date.</span></span> <span data-ttu-id="29bb3-156">Både fasta och rörliga kompensationsplaner använder behörighetsregler.</span><span class="sxs-lookup"><span data-stu-id="29bb3-156">Both fixed and variable compensation plans use eligibility rules.</span></span> <span data-ttu-id="29bb3-157">Välj typ av plan i fältet **Typ**.</span><span class="sxs-lookup"><span data-stu-id="29bb3-157">In the **Type** field, select the type of plan.</span></span>

6. <span data-ttu-id="29bb3-158">I fältet **Plan**, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="29bb3-158">In the **Plan** field, enter or select a value.</span></span> <span data-ttu-id="29bb3-159">Markera det villkor som en medarbetare måste uppfylla för att kunna berättigas till kompensationsplanen.</span><span class="sxs-lookup"><span data-stu-id="29bb3-159">Select the criteria an employee must meet in order to be eligible for the compensation plan.</span></span> <span data-ttu-id="29bb3-160">Kriterier kan vara:</span><span class="sxs-lookup"><span data-stu-id="29bb3-160">Criteria can include:</span></span>

    - <span data-ttu-id="29bb3-161">**Avdelning**</span><span class="sxs-lookup"><span data-stu-id="29bb3-161">**Department**</span></span>
    - <span data-ttu-id="29bb3-162">**Fackförening**</span><span class="sxs-lookup"><span data-stu-id="29bb3-162">**Labor union**</span></span>
    - <span data-ttu-id="29bb3-163">**Plats** (**kompensationsregion**)</span><span class="sxs-lookup"><span data-stu-id="29bb3-163">**Location** (**Compensation region**)</span></span>
    - <span data-ttu-id="29bb3-164">**Jobb**</span><span class="sxs-lookup"><span data-stu-id="29bb3-164">**Job**</span></span>
    - <span data-ttu-id="29bb3-165">**Funktion**</span><span class="sxs-lookup"><span data-stu-id="29bb3-165">**Function**</span></span>
    - <span data-ttu-id="29bb3-166">**Jobbtyp**</span><span class="sxs-lookup"><span data-stu-id="29bb3-166">**Job type**</span></span>
    - <span data-ttu-id="29bb3-167">**Kompensationsnivå**</span><span class="sxs-lookup"><span data-stu-id="29bb3-167">**Compensation level**</span></span>
    
    <span data-ttu-id="29bb3-168">En medarbetare måste uppfylla alla angivna villkor för att kunna berättigas till kompensationsplanen.</span><span class="sxs-lookup"><span data-stu-id="29bb3-168">The employee must meet all specified criteria to be eligible for the compensation plan.</span></span> <span data-ttu-id="29bb3-169">Om du inte anger några kriterier är alla medarbetare berättigade till kompensationsplanen.</span><span class="sxs-lookup"><span data-stu-id="29bb3-169">If you don't specify any criteria, all employees are eligible for the compensation plan.</span></span> <span data-ttu-id="29bb3-170">Om en medarbetare inte uppfyller kriteriet som ställts in i berättiganderegeln, eller en berättiganderegel inte har ställts in för en kompensationsplan, kommer kompensationsplanen inte att visas i sökningen när du skapar en post med fast kompensation för en medarbetare.</span><span class="sxs-lookup"><span data-stu-id="29bb3-170">If an employee doesn't meet the criteria specified in the eligibility rule, or an eligibility rule has not been specified for a compensation plan, the compensation plan won't appear in the lookup when you create a fixed compensation record for an employee.</span></span>

7. <span data-ttu-id="29bb3-171">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="29bb3-171">Close the page.</span></span>

8. <span data-ttu-id="29bb3-172">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="29bb3-172">Close the page.</span></span>

