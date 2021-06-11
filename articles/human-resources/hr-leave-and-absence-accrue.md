---
title: Periodisera planer för tjänstledighet och frånvaro
description: Du kan periodisera tjänstledighet och frånvaro i Dynamics 365 Human Resources för flera medarbetare eller för en person.
author: andreabichsel
ms.date: 05/04/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 86ca63b1703faa6f57ed2e5591c89a5e84363481
ms.sourcegitcommit: 318e406b84d43381d450272eb83c5eea9c5cf1c0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059483"
---
# <a name="accrue-leave-and-absence-plans"></a><span data-ttu-id="1f986-103">Periodisera planer för tjänstledighet och frånvaro</span><span class="sxs-lookup"><span data-stu-id="1f986-103">Accrue leave and absence plans</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="1f986-104">Du kan periodisera tjänstledighet och frånvaro i Dynamics 365 Human Resources för flera medarbetare eller för en person.</span><span class="sxs-lookup"><span data-stu-id="1f986-104">You can accrue leave and absence in Dynamics 365 Human Resources for multiple employees or for an individual.</span></span>

## <a name="accrue-leave-and-absence-for-multiple-employees"></a><span data-ttu-id="1f986-105">Periodisera tjänstledighet och frånvaro för flera medarbetare</span><span class="sxs-lookup"><span data-stu-id="1f986-105">Accrue leave and absence for multiple employees</span></span>

1. <span data-ttu-id="1f986-106">På sidan **tjänstledighet och frånvaro** välj fliken **Länkar**.</span><span class="sxs-lookup"><span data-stu-id="1f986-106">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="1f986-107">Under **Hantera tjänstledighet**, välj **tjänstledighet och frånvaroplaner**.</span><span class="sxs-lookup"><span data-stu-id="1f986-107">Under **Manage leave**, select **Accrue leave and absence plans**.</span></span>

3. <span data-ttu-id="1f986-108">Dialogrutan **Periodisera planer för tjänstledighet och frånvaro** visas.</span><span class="sxs-lookup"><span data-stu-id="1f986-108">The **Accrue leave and absence plans** dialog box appears.</span></span> <span data-ttu-id="1f986-109">I **Accrue as of**, either select **Samla ihop från och med** eller välj **Anpassat datum** och ange ett anpassat datum.</span><span class="sxs-lookup"><span data-stu-id="1f986-109">In **Accrue as of**, either select **Today's date** or select **Custom date** and enter a custom date.</span></span>

4. <span data-ttu-id="1f986-110">Om du vill köra periodiseringar för alla företag väljer du **alla företag**.</span><span class="sxs-lookup"><span data-stu-id="1f986-110">If you want to run accruals for all companies, select **All companies**.</span></span> <span data-ttu-id="1f986-111">Om du vill bearbeta periodiseringar för en enda tjänstledighetsplan väljer du **Nej** för **Alla planer** och väljer sedan en **Tjänstledighetsplan**.</span><span class="sxs-lookup"><span data-stu-id="1f986-111">If you want to process accruals for a single leave plan, select **No** for **All plans**, and then select a **Leave plan**.</span></span> <span data-ttu-id="1f986-112">Om du väljer alla företag kan du inte välja en enskild tjänstledighetsplan.</span><span class="sxs-lookup"><span data-stu-id="1f986-112">If you select all companies, you can't select an individual leave plan.</span></span>

5. <span data-ttu-id="1f986-113">Om du vill köra periodiseringsprocessen i bakgrunden väljer du **Kör i bakgrunden** och utför följande uppgifter:</span><span class="sxs-lookup"><span data-stu-id="1f986-113">If you want to run the accrual process in the background, select **Run in the background** and do the following tasks:</span></span>

    1. <span data-ttu-id="1f986-114">Ange information för periodiseringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="1f986-114">Enter information for the accrual process.</span></span>
    2. <span data-ttu-id="1f986-115">Om du vill ställa in ett återkommande jobb väljer du **återkommande**, anger upprepningsinformationen och klickar på **OK**.</span><span class="sxs-lookup"><span data-stu-id="1f986-115">To set up a recurring job, select **Recurrence**, enter the recurrence information, and then select **OK**.</span></span>
    3. <span data-ttu-id="1f986-116">Ställ in en jobbsignal genom att välja **notifieringar**, välja de notifieringar som ska tas emot och sedan välja **OK**.</span><span class="sxs-lookup"><span data-stu-id="1f986-116">To set up a job alert, select **Alerts**, select the alerts to receive, and then select **OK**.</span></span>
    4. <span data-ttu-id="1f986-117">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="1f986-117">Select **OK**.</span></span> <span data-ttu-id="1f986-118">Periodiseringsprocessen kommer att köras med de parametrar du angett.</span><span class="sxs-lookup"><span data-stu-id="1f986-118">The accrual process will run with the parameters you set.</span></span> 

## <a name="accrue-leave-and-absence-for-an-employee"></a><span data-ttu-id="1f986-119">Periodisera tjänstledighet och frånvaro för en medarbetare</span><span class="sxs-lookup"><span data-stu-id="1f986-119">Accrue leave and absence for an employee</span></span>

1. <span data-ttu-id="1f986-120">Välj **tjänstledighet** för medarbetarens post.</span><span class="sxs-lookup"><span data-stu-id="1f986-120">On the employee's record, select **Leave**.</span></span>

2. <span data-ttu-id="1f986-121">Välj **Periodisera för tjänstledighet och frånvaro**.</span><span class="sxs-lookup"><span data-stu-id="1f986-121">Select **Accrue leave and absence**.</span></span>

3. <span data-ttu-id="1f986-122">Dialogrutan **Periodisera planer för tjänstledighet och frånvaro** visas.</span><span class="sxs-lookup"><span data-stu-id="1f986-122">The **Accrue leave and absence plans** dialog box appears.</span></span> <span data-ttu-id="1f986-123">I **Accrue as of**, either select **Samla ihop från och med** eller välj **Anpassat datum** och ange ett anpassat datum.</span><span class="sxs-lookup"><span data-stu-id="1f986-123">In **Accrue as of**, either select **Today's date** or select **Custom date** and enter a custom date.</span></span>

4. <span data-ttu-id="1f986-124">Om du vill köra periodiseringar för alla företag väljer du **alla företag**.</span><span class="sxs-lookup"><span data-stu-id="1f986-124">If you want to run accruals for all companies, select **All companies**.</span></span> <span data-ttu-id="1f986-125">Om du vill bearbeta periodiseringar för en enda tjänstledighetsplan väljer du **Nej** för **Alla planer** och väljer sedan en **Tjänstledighetsplan**.</span><span class="sxs-lookup"><span data-stu-id="1f986-125">If you want to process accruals for a single leave plan, select **No** for **All plans**, and then select a **Leave plan**.</span></span> <span data-ttu-id="1f986-126">Om du väljer alla företag kan du inte välja en enskild tjänstledighetsplan.</span><span class="sxs-lookup"><span data-stu-id="1f986-126">If you select all companies, you can't select an individual leave plan.</span></span>

5. <span data-ttu-id="1f986-127">Om du vill köra periodiseringsprocessen i bakgrunden väljer du **Kör i bakgrunden** och utför följande uppgifter:</span><span class="sxs-lookup"><span data-stu-id="1f986-127">If you want to run the accrual process in the background, select **Run in the background** and do the following tasks:</span></span>

   1. <span data-ttu-id="1f986-128">Ange information för periodiseringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="1f986-128">Enter information for the accrual process.</span></span>

   2. <span data-ttu-id="1f986-129">Om du vill ställa in ett återkommande jobb väljer du **återkommande**, anger upprepningsinformationen och klickar på **OK**.</span><span class="sxs-lookup"><span data-stu-id="1f986-129">To set up a recurring job, select **Recurrence**, enter the recurrence information, and the select **OK**.</span></span>

   3. <span data-ttu-id="1f986-130">Ställ in en jobbsignal genom att välja **notifieringar**, välja de notifieringar som ska tas emot och sedan välja **OK**.</span><span class="sxs-lookup"><span data-stu-id="1f986-130">To set up a job alert, select **Alerts**, select the alerts to receive, and then select **OK**.</span></span>

   4. <span data-ttu-id="1f986-131">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="1f986-131">Select **OK**.</span></span> <span data-ttu-id="1f986-132">Periodiseringsprocessen kommer att köras med de parametrar du angett.</span><span class="sxs-lookup"><span data-stu-id="1f986-132">The accrual process will run with the parameters you set.</span></span>

## <a name="delete-leave-and-absence-accruals-for-multiple-employees"></a><span data-ttu-id="1f986-133">Ta bort periodiseringar av tjänstledighet och frånvaro för flera medarbetare</span><span class="sxs-lookup"><span data-stu-id="1f986-133">Delete leave and absence accruals for multiple employees</span></span>

<span data-ttu-id="1f986-134">Ta bort periodiseringsposter för ett specifikt plan- och datumintervall.</span><span class="sxs-lookup"><span data-stu-id="1f986-134">Delete accrual records for a specific plan and date range.</span></span> <span data-ttu-id="1f986-135">Periodiseringsdatum måste vara daterade i dag eller i framtiden.</span><span class="sxs-lookup"><span data-stu-id="1f986-135">Accrual dates must be dated today or in the future.</span></span>

1. <span data-ttu-id="1f986-136">På sidan **tjänstledighet och frånvaro** välj fliken **Länkar**.</span><span class="sxs-lookup"><span data-stu-id="1f986-136">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="1f986-137">Under **Hantera tjänstledighet**, välj **Ta bort periodiseringar av plan för tjänstledighet och frånvaro**.</span><span class="sxs-lookup"><span data-stu-id="1f986-137">Under **Manage leave**, select **Delete leave and absence plan accruals**.</span></span>

3. <span data-ttu-id="1f986-138">I dialogrutan **Ta bort periodiseringar av plan för tjänstledighet och frånvaro** och välj **Tjänstledighetsplan**.</span><span class="sxs-lookup"><span data-stu-id="1f986-138">In the **Delete leave and absence plan accruals** dialog box, select the **Leave plan**.</span></span>

4. <span data-ttu-id="1f986-139">Om tillämpligt, välj **Ta bort saldojusteringar**.</span><span class="sxs-lookup"><span data-stu-id="1f986-139">If applicable, choose **Delete balance adjustments**.</span></span>

5. <span data-ttu-id="1f986-140">Ange eller välj ett **periodiseringsdatum för tjänstledighet**.</span><span class="sxs-lookup"><span data-stu-id="1f986-140">Enter or select a **Leave accrual date**.</span></span> <span data-ttu-id="1f986-141">Detta datum måste vara antingen idag eller senare.</span><span class="sxs-lookup"><span data-stu-id="1f986-141">This date has to be either today or in the future.</span></span>

6. <span data-ttu-id="1f986-142">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="1f986-142">Select **OK**.</span></span> <span data-ttu-id="1f986-143">Periodiseringsprocessen kommer att ta bort periodiseringar med de parametrar du angett.</span><span class="sxs-lookup"><span data-stu-id="1f986-143">The accrual process will delete accruals with the parameters you set.</span></span>

## <a name="delete-leave-and-absence-accruals-for-a-single-employee"></a><span data-ttu-id="1f986-144">Ta bort periodiseringar av tjänstledighet och frånvaro för en medarbetare</span><span class="sxs-lookup"><span data-stu-id="1f986-144">Delete leave and absence accruals for a single employee</span></span>

1. <span data-ttu-id="1f986-145">Välj **tjänstledighet** för medarbetarens post.</span><span class="sxs-lookup"><span data-stu-id="1f986-145">On the employee's record, select **Leave**.</span></span>

2. <span data-ttu-id="1f986-146">Välj **Ta bort periodiseringar av plan för tjänstledighet och frånvaro**.</span><span class="sxs-lookup"><span data-stu-id="1f986-146">Select **Delete leave and absence plan accruals**.</span></span>

3. <span data-ttu-id="1f986-147">I dialogrutan **Ta bort periodiseringar av plan för tjänstledighet och frånvaro** och välj **Tjänstledighetsplan**.</span><span class="sxs-lookup"><span data-stu-id="1f986-147">In the **Delete leave and absence plan accruals** dialog box, select **Leave plan**.</span></span>

4. <span data-ttu-id="1f986-148">Om tillämpligt, välj **Ta bort saldojusteringar**.</span><span class="sxs-lookup"><span data-stu-id="1f986-148">If applicable, choose **Delete balance adjustments**.</span></span>

5. <span data-ttu-id="1f986-149">Ange eller välj ett **periodiseringsdatum för tjänstledighet**.</span><span class="sxs-lookup"><span data-stu-id="1f986-149">Enter or select a **Leave accrual date**.</span></span> <span data-ttu-id="1f986-150">Detta datum måste vara antingen idag eller senare.</span><span class="sxs-lookup"><span data-stu-id="1f986-150">This date must be either today or in the future.</span></span>

6. <span data-ttu-id="1f986-151">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="1f986-151">Select **OK**.</span></span> <span data-ttu-id="1f986-152">Periodiseringsprocessen kommer att ta bort periodiseringar med de parametrar du angett.</span><span class="sxs-lookup"><span data-stu-id="1f986-152">The accrual process will delete accruals with the parameters you set.</span></span>

## <a name="review-leave-accrual-and-deletion-processes"></a><span data-ttu-id="1f986-153">Granska processer för periodisering av tjänstledighet och borttagning</span><span class="sxs-lookup"><span data-stu-id="1f986-153">Review leave accrual and deletion processes</span></span>

<span data-ttu-id="1f986-154">**Granskning av periodisering av tjänstledighet** visas varje gång du kör eller tar bort en periodisering för en eller alla medarbetare.</span><span class="sxs-lookup"><span data-stu-id="1f986-154">**Leave accrual audit** displays each time you run or delete an accrual for one or all employees.</span></span> <span data-ttu-id="1f986-155">Datumet och personen som utförde åtgärden visas också.</span><span class="sxs-lookup"><span data-stu-id="1f986-155">The date and person who performed the action also displays.</span></span>

1. <span data-ttu-id="1f986-156">På sidan **tjänstledighet och frånvaro** välj fliken **Länkar**.</span><span class="sxs-lookup"><span data-stu-id="1f986-156">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="1f986-157">Under **Hantera tjänstledighet**, välj **Ta bort granskning av periodisering av tjänstledighet**.</span><span class="sxs-lookup"><span data-stu-id="1f986-157">Under **Manage leave**, select **Delete leave accrual audit**.</span></span>

## <a name="preview-leave-accrual-transaction-auditing"></a><span data-ttu-id="1f986-158">(Förhandsversion) Granskning av periodiseringstransaktion för tjänstledighet</span><span class="sxs-lookup"><span data-stu-id="1f986-158">(Preview) Leave accrual transaction auditing</span></span>

[!include [Preview feature](includes/preview-feature.md)]

<span data-ttu-id="1f986-159">Den här förhandsgranskningsfunktionen hjälper lediga och frånvaroansvariga att förstå transaktioner för periodiseringar för frånvaro och transaktioner relaterade till en anställds lediga saldon för en specifik semester.</span><span class="sxs-lookup"><span data-stu-id="1f986-159">This preview feature helps leave and absence managers understand the leave and absence accrual transactions related to an employee’s time off balances for a specific leave type.</span></span>

<span data-ttu-id="1f986-160">För att visa transaktionsdetaljer:</span><span class="sxs-lookup"><span data-stu-id="1f986-160">To view transaction details:</span></span>

1. <span data-ttu-id="1f986-161">Välj **tjänstledighet** för medarbetarens post.</span><span class="sxs-lookup"><span data-stu-id="1f986-161">On the employee's record, select **Leave**.</span></span>

2. <span data-ttu-id="1f986-162">Välj **Visa ledighet** och välj fliken **Saldon**.</span><span class="sxs-lookup"><span data-stu-id="1f986-162">Select **View time off**, and then select the **Balances** tab.</span></span>

<span data-ttu-id="1f986-163">Om du vill visa periodiseringstransaktionerna för en viss tjänstledighetstyp väljer du numeriskt värde i kolumnen **Aktuell balans**.</span><span class="sxs-lookup"><span data-stu-id="1f986-163">To view the accrual transactions related to a specific leave type, select the numerical value in the **Current balance** column.</span></span>

<span data-ttu-id="1f986-164">Om du vill visa transaktionsdetaljer för ett visst periodiseringsbelopp markerar du en periodiseringsrad, öppnar panelen **Relaterad information** till höger och öppnar sedan avsnittet **Transaktionsinformation**.</span><span class="sxs-lookup"><span data-stu-id="1f986-164">To view the transaction details for a specific accrual amount, select an accrual row, open the **Related information** panel on the right, and then open the **Transaction details** section.</span></span> <span data-ttu-id="1f986-165">Avsnittet Transaktionsdetaljer visar:</span><span class="sxs-lookup"><span data-stu-id="1f986-165">The Transaction details section displays:</span></span>

- <span data-ttu-id="1f986-166">Ändringar av medarbetarens saldo för tjänstledighetstyp</span><span class="sxs-lookup"><span data-stu-id="1f986-166">Changes to the employee’s leave type balance</span></span>
- <span data-ttu-id="1f986-167">Anställningsdetaljer för den angivna periodiseringsperioden</span><span class="sxs-lookup"><span data-stu-id="1f986-167">Employment details for that specified accrual period</span></span>
- <span data-ttu-id="1f986-168">Detaljer om periodiseringsperiod och periodiseringssatser</span><span class="sxs-lookup"><span data-stu-id="1f986-168">Details about the accrual period and rates</span></span>
- <span data-ttu-id="1f986-169">Ändringar som gjorts för att lämna plankonfigurationer</span><span class="sxs-lookup"><span data-stu-id="1f986-169">Any changes made to leave plan configurations</span></span>

![Visa granskning av periodiseringstransaktion för tjänstledighet](media/hr-leave-and-absence-accrue-audit.png)

## <a name="see-also"></a><span data-ttu-id="1f986-171">Se även</span><span class="sxs-lookup"><span data-stu-id="1f986-171">See also</span></span>

[<span data-ttu-id="1f986-172">Översikt över tjänstledighet och frånvaro</span><span class="sxs-lookup"><span data-stu-id="1f986-172">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)</br>
[<span data-ttu-id="1f986-173">Skapa en plan för tjänstledighet och frånvaro</span><span class="sxs-lookup"><span data-stu-id="1f986-173">Create a leave and absence plan</span></span>](hr-leave-and-absence-plans.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
