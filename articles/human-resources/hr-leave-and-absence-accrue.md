---
title: Periodisera planer för tjänstledighet och frånvaro
description: Du kan periodisera tjänstledighet och frånvaro i Dynamics 365 Human Resources för flera medarbetare eller för en person.
author: andreabichsel
manager: tfehr
ms.date: 06/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 348c8e5336854eb2a1c04a1f98a97a2c9dba7176
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/17/2021
ms.locfileid: "5464920"
---
# <a name="accrue-leave-and-absence-plans"></a><span data-ttu-id="aec13-103">Periodisera planer för tjänstledighet och frånvaro</span><span class="sxs-lookup"><span data-stu-id="aec13-103">Accrue leave and absence plans</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="aec13-104">Du kan periodisera tjänstledighet och frånvaro i Dynamics 365 Human Resources för flera medarbetare eller för en person.</span><span class="sxs-lookup"><span data-stu-id="aec13-104">You can accrue leave and absence in Dynamics 365 Human Resources for multiple employees or for an individual.</span></span>

## <a name="accrue-leave-and-absence-for-multiple-employees"></a><span data-ttu-id="aec13-105">Periodisera tjänstledighet och frånvaro för flera medarbetare</span><span class="sxs-lookup"><span data-stu-id="aec13-105">Accrue leave and absence for multiple employees</span></span>

1. <span data-ttu-id="aec13-106">På sidan **tjänstledighet och frånvaro** välj fliken **Länkar**.</span><span class="sxs-lookup"><span data-stu-id="aec13-106">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="aec13-107">Under **Hantera tjänstledighet**, välj **tjänstledighet och frånvaroplaner**.</span><span class="sxs-lookup"><span data-stu-id="aec13-107">Under **Manage leave**, select **Accrue leave and absence plans**.</span></span>

3. <span data-ttu-id="aec13-108">Dialogrutan **Periodisera planer för tjänstledighet och frånvaro** visas.</span><span class="sxs-lookup"><span data-stu-id="aec13-108">The **Accrue leave and absence plans** dialog box appears.</span></span> <span data-ttu-id="aec13-109">I **Accrue as of**, either select **Samla ihop från och med** eller välj **Anpassat datum** och ange ett anpassat datum.</span><span class="sxs-lookup"><span data-stu-id="aec13-109">In **Accrue as of**, either select **Today's date** or select **Custom date** and enter a custom date.</span></span>

4. <span data-ttu-id="aec13-110">Om du vill köra periodiseringar för alla företag väljer du **alla företag**.</span><span class="sxs-lookup"><span data-stu-id="aec13-110">If you want to run accruals for all companies, select **All companies**.</span></span> <span data-ttu-id="aec13-111">Om du vill bearbeta periodiseringar för en enda tjänstledighetsplan väljer du **Nej** för **Alla planer** och väljer sedan en **Tjänstledighetsplan**.</span><span class="sxs-lookup"><span data-stu-id="aec13-111">If you want to process accruals for a single leave plan, select **No** for **All plans**, and then select a **Leave plan**.</span></span> <span data-ttu-id="aec13-112">Om du väljer alla företag kan du inte välja en enskild tjänstledighetsplan.</span><span class="sxs-lookup"><span data-stu-id="aec13-112">If you select all companies, you can't select an individual leave plan.</span></span> 

5. <span data-ttu-id="aec13-113">Om du vill köra periodiseringsprocessen i bakgrunden väljer du **Kör i bakgrunden** och utför följande uppgifter:</span><span class="sxs-lookup"><span data-stu-id="aec13-113">If you want to run the accrual process in the background, select **Run in the background** and do the following tasks:</span></span>

   1. <span data-ttu-id="aec13-114">Ange information för periodiseringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="aec13-114">Enter information for the accrual process.</span></span>

   2. <span data-ttu-id="aec13-115">Om du vill ställa in ett återkommande jobb väljer du **återkommande**, anger upprepningsinformationen och klickar på **OK**.</span><span class="sxs-lookup"><span data-stu-id="aec13-115">To set up a recurring job, select **Recurrence**, enter the recurrence information, and the select **OK**.</span></span>

   3. <span data-ttu-id="aec13-116">Ställ in en jobbsignal genom att välja **notifieringar**, välja de notifieringar som ska tas emot och sedan välja **OK**.</span><span class="sxs-lookup"><span data-stu-id="aec13-116">To set up a job alert, select **Alerts**, select the alerts to receive, and then select **OK**.</span></span>

   4. <span data-ttu-id="aec13-117">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="aec13-117">Select **OK**.</span></span> <span data-ttu-id="aec13-118">Periodiseringsprocessen kommer att köras med de parametrar du angett.</span><span class="sxs-lookup"><span data-stu-id="aec13-118">The accrual process will run with the parameters you set.</span></span>

## <a name="accrue-leave-and-absence-for-an-employee"></a><span data-ttu-id="aec13-119">Periodisera tjänstledighet och frånvaro för en medarbetare</span><span class="sxs-lookup"><span data-stu-id="aec13-119">Accrue leave and absence for an employee</span></span>

1. <span data-ttu-id="aec13-120">Välj **tjänstledighet** för medarbetarens post.</span><span class="sxs-lookup"><span data-stu-id="aec13-120">On the employee's record, select **Leave**.</span></span>

2. <span data-ttu-id="aec13-121">Välj **Periodisera för tjänstledighet och frånvaro**.</span><span class="sxs-lookup"><span data-stu-id="aec13-121">Select **Accrue leave and absence**.</span></span>

3. <span data-ttu-id="aec13-122">Dialogrutan **Periodisera planer för tjänstledighet och frånvaro** visas.</span><span class="sxs-lookup"><span data-stu-id="aec13-122">The **Accrue leave and absence plans** dialog box appears.</span></span> <span data-ttu-id="aec13-123">I **Accrue as of**, either select **Samla ihop från och med** eller välj **Anpassat datum** och ange ett anpassat datum.</span><span class="sxs-lookup"><span data-stu-id="aec13-123">In **Accrue as of**, either select **Today's date** or select **Custom date** and enter a custom date.</span></span>

4. <span data-ttu-id="aec13-124">Om du vill köra periodiseringar för alla företag väljer du **alla företag**.</span><span class="sxs-lookup"><span data-stu-id="aec13-124">If you want to run accruals for all companies, select **All companies**.</span></span> <span data-ttu-id="aec13-125">Om du vill bearbeta periodiseringar för en enda tjänstledighetsplan väljer du **Nej** för **Alla planer** och väljer sedan en **Tjänstledighetsplan**.</span><span class="sxs-lookup"><span data-stu-id="aec13-125">If you want to process accruals for a single leave plan, select **No** for **All plans**, and then select a **Leave plan**.</span></span> <span data-ttu-id="aec13-126">Om du väljer alla företag kan du inte välja en enskild tjänstledighetsplan.</span><span class="sxs-lookup"><span data-stu-id="aec13-126">If you select all companies, you can't select an individual leave plan.</span></span> 

5. <span data-ttu-id="aec13-127">Om du vill köra periodiseringsprocessen i bakgrunden väljer du **Kör i bakgrunden** och utför följande uppgifter:</span><span class="sxs-lookup"><span data-stu-id="aec13-127">If you want to run the accrual process in the background, select **Run in the background** and do the following tasks:</span></span>

   1. <span data-ttu-id="aec13-128">Ange information för periodiseringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="aec13-128">Enter information for the accrual process.</span></span>

   2. <span data-ttu-id="aec13-129">Om du vill ställa in ett återkommande jobb väljer du **återkommande**, anger upprepningsinformationen och klickar på **OK**.</span><span class="sxs-lookup"><span data-stu-id="aec13-129">To set up a recurring job, select **Recurrence**, enter the recurrence information, and the select **OK**.</span></span>

   3. <span data-ttu-id="aec13-130">Ställ in en jobbsignal genom att välja **notifieringar**, välja de notifieringar som ska tas emot och sedan välja **OK**.</span><span class="sxs-lookup"><span data-stu-id="aec13-130">To set up a job alert, select **Alerts**, select the alerts to receive, and then select **OK**.</span></span>

   4. <span data-ttu-id="aec13-131">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="aec13-131">Select **OK**.</span></span> <span data-ttu-id="aec13-132">Periodiseringsprocessen kommer att köras med de parametrar du angett.</span><span class="sxs-lookup"><span data-stu-id="aec13-132">The accrual process will run with the parameters you set.</span></span>

## <a name="delete-leave-and-absence-accruals-for-multiple-employees"></a><span data-ttu-id="aec13-133">Ta bort periodiseringar av tjänstledighet och frånvaro för flera medarbetare</span><span class="sxs-lookup"><span data-stu-id="aec13-133">Delete leave and absence accruals for multiple employees</span></span>

<span data-ttu-id="aec13-134">Ta bort periodiseringsposter för ett specifikt plan- och datumintervall.</span><span class="sxs-lookup"><span data-stu-id="aec13-134">Delete accrual records for a specific plan and date range.</span></span> <span data-ttu-id="aec13-135">Periodiseringsdatum måste vara daterade i dag eller i framtiden.</span><span class="sxs-lookup"><span data-stu-id="aec13-135">Accrual dates must be dated today or in the future.</span></span>

1. <span data-ttu-id="aec13-136">På sidan **tjänstledighet och frånvaro** välj fliken **Länkar**.</span><span class="sxs-lookup"><span data-stu-id="aec13-136">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="aec13-137">Under **Hantera tjänstledighet**, välj **Ta bort periodiseringar av plan för tjänstledighet och frånvaro**.</span><span class="sxs-lookup"><span data-stu-id="aec13-137">Under **Manage leave**, select **Delete leave and absence plan accruals**.</span></span>

3. <span data-ttu-id="aec13-138">I dialogrutan **Ta bort periodiseringar av plan för tjänstledighet och frånvaro** och välj **Tjänstledighetsplan**.</span><span class="sxs-lookup"><span data-stu-id="aec13-138">In the **Delete leave and absence plan accruals** dialog box, select the **Leave plan**.</span></span> 

4. <span data-ttu-id="aec13-139">Om tillämpligt, välj **Ta bort saldojusteringar**.</span><span class="sxs-lookup"><span data-stu-id="aec13-139">If applicable, choose **Delete balance adjustments**.</span></span>

5. <span data-ttu-id="aec13-140">Ange eller välj ett **periodiseringsdatum för tjänstledighet**.</span><span class="sxs-lookup"><span data-stu-id="aec13-140">Enter or select a **Leave accrual date**.</span></span> <span data-ttu-id="aec13-141">Detta datum måste vara antingen idag eller senare.</span><span class="sxs-lookup"><span data-stu-id="aec13-141">This date has to be either today or in the future.</span></span> 

6. <span data-ttu-id="aec13-142">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="aec13-142">Select **OK**.</span></span> <span data-ttu-id="aec13-143">Periodiseringsprocessen kommer att ta bort periodiseringar med de parametrar du angett.</span><span class="sxs-lookup"><span data-stu-id="aec13-143">The accrual process will delete accruals with the parameters you set.</span></span> 

## <a name="delete-leave-and-absence-accruals-for-a-single-employee"></a><span data-ttu-id="aec13-144">Ta bort periodiseringar av tjänstledighet och frånvaro för en medarbetare</span><span class="sxs-lookup"><span data-stu-id="aec13-144">Delete leave and absence accruals for a single employee</span></span>

1. <span data-ttu-id="aec13-145">Välj **tjänstledighet** för medarbetarens post.</span><span class="sxs-lookup"><span data-stu-id="aec13-145">On the employee's record, select **Leave**.</span></span>

2. <span data-ttu-id="aec13-146">Välj **Ta bort periodiseringar av plan för tjänstledighet och frånvaro**.</span><span class="sxs-lookup"><span data-stu-id="aec13-146">Select **Delete leave and absence plan accruals**.</span></span>

3. <span data-ttu-id="aec13-147">I dialogrutan **Ta bort periodiseringar av plan för tjänstledighet och frånvaro** och välj **Tjänstledighetsplan**.</span><span class="sxs-lookup"><span data-stu-id="aec13-147">In the **Delete leave and absence plan accruals** dialog box, select **Leave plan**.</span></span> 

4. <span data-ttu-id="aec13-148">Om tillämpligt, välj **Ta bort saldojusteringar**.</span><span class="sxs-lookup"><span data-stu-id="aec13-148">If applicable, choose **Delete balance adjustments**.</span></span>

5. <span data-ttu-id="aec13-149">Ange eller välj ett **periodiseringsdatum för tjänstledighet**.</span><span class="sxs-lookup"><span data-stu-id="aec13-149">Enter or select a **Leave accrual date**.</span></span> <span data-ttu-id="aec13-150">Detta datum måste vara antingen idag eller senare.</span><span class="sxs-lookup"><span data-stu-id="aec13-150">This date must be either today or in the future.</span></span> 

6. <span data-ttu-id="aec13-151">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="aec13-151">Select **OK**.</span></span> <span data-ttu-id="aec13-152">Periodiseringsprocessen kommer att ta bort periodiseringar med de parametrar du angett.</span><span class="sxs-lookup"><span data-stu-id="aec13-152">The accrual process will delete accruals with the parameters you set.</span></span> 

## <a name="review-leave-accrual-and-deletion-processes"></a><span data-ttu-id="aec13-153">Granska processer för periodisering av tjänstledighet och borttagning</span><span class="sxs-lookup"><span data-stu-id="aec13-153">Review leave accrual and deletion processes</span></span>

<span data-ttu-id="aec13-154">**Granskning av periodisering av tjänstledighet** visas varje gång du kör eller tar bort en periodisering för en eller alla medarbetare.</span><span class="sxs-lookup"><span data-stu-id="aec13-154">**Leave accrual audit** displays each time you run or delete an accrual for one or all employees.</span></span> <span data-ttu-id="aec13-155">Datumet och personen som utförde åtgärden visas också.</span><span class="sxs-lookup"><span data-stu-id="aec13-155">The date and person who performed the action also displays.</span></span>

1. <span data-ttu-id="aec13-156">På sidan **tjänstledighet och frånvaro** välj fliken **Länkar**.</span><span class="sxs-lookup"><span data-stu-id="aec13-156">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="aec13-157">Under **Hantera tjänstledighet**, välj **Ta bort granskning av periodisering av tjänstledighet**.</span><span class="sxs-lookup"><span data-stu-id="aec13-157">Under **Manage leave**, select **Delete leave accrual audit**.</span></span>

## <a name="see-also"></a><span data-ttu-id="aec13-158">Se även</span><span class="sxs-lookup"><span data-stu-id="aec13-158">See also</span></span>

[<span data-ttu-id="aec13-159">Översikt över tjänstledighet och frånvaro</span><span class="sxs-lookup"><span data-stu-id="aec13-159">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)</br>
[<span data-ttu-id="aec13-160">Skapa en plan för tjänstledighet och frånvaro</span><span class="sxs-lookup"><span data-stu-id="aec13-160">Create a leave and absence plan</span></span>](hr-leave-and-absence-plans.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]