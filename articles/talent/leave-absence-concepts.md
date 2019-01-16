---
title: "Begrepp för tjänstledighet och frånvaro"
description: "Det här avsnittet beskriver begrepp för tjänstledighet och frånvaro och hur ledighetssaldon fastställs."
author: jcart
manager: AnnBe
ms.date: 01/03/2019
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application user
ms.reviewer: josaw
ms.search.scope: Core, Operations, Talent
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2019-01-01
ms.dyn365.ops.version: 
ms.translationtype: HT
ms.sourcegitcommit: a388e0efe6c19a3aabe04e7fff039ce11ae023c4
ms.openlocfilehash: 563593d6c93b0488c681f5b43004f5c0d22cc004
ms.contentlocale: sv-se
ms.lasthandoff: 01/07/2019

---

# <a name="leave-and-absence-concepts"></a><span data-ttu-id="b4660-103">Begrepp för tjänstledighet och frånvaro</span><span class="sxs-lookup"><span data-stu-id="b4660-103">Leave and absence concepts</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="b4660-104">De begrepp och termer som beskrivs i det här avsnittet kan hjälpa dig att avgöra hur en medarbetare tilldelats ledighet och hur denna medarbetares tidssaldo beräknas.</span><span class="sxs-lookup"><span data-stu-id="b4660-104">The concepts and terms that are described in this topic can help you determine how an employee is awarded time off, and how that employee's time balances are calculated.</span></span> <span data-ttu-id="b4660-105">Läs mer om ledighet och frånvaro i [Hantering av tjänstledighet och frånvaro](https://docs.microsoft.com/dynamics365/unified-operations/talent/leave-absence-overview).</span><span class="sxs-lookup"><span data-stu-id="b4660-105">For more information about leave and absence management, see [Leave and absence management](https://docs.microsoft.com/dynamics365/unified-operations/talent/leave-absence-overview).</span></span>

## <a name="leave-plan-details"></a><span data-ttu-id="b4660-106">Detaljer om tjänstledighetsplan</span><span class="sxs-lookup"><span data-stu-id="b4660-106">Leave plan details</span></span>

### <a name="start-date"></a><span data-ttu-id="b4660-107">Startdatum</span><span class="sxs-lookup"><span data-stu-id="b4660-107">Start date</span></span>

<span data-ttu-id="b4660-108">Startdatumet är det datum då periodiseringsbehandling börjar.</span><span class="sxs-lookup"><span data-stu-id="b4660-108">The start date is the date when accrual processing begins.</span></span> <span data-ttu-id="b4660-109">Startdatumet används också som jubileumsdatum för att beräkna överföringsmängd.</span><span class="sxs-lookup"><span data-stu-id="b4660-109">The start date also serves as the anniversary date that is used to calculate carry-forward amounts.</span></span>

## <a name="accruals"></a><span data-ttu-id="b4660-110">Periodiseringar</span><span class="sxs-lookup"><span data-stu-id="b4660-110">Accruals</span></span>

<span data-ttu-id="b4660-111">Periodiseringar bestämmer när och hur ofta en medarbetaren belönas med ledighet.</span><span class="sxs-lookup"><span data-stu-id="b4660-111">Accruals determine when and how often an employee is awarded time off.</span></span> <span data-ttu-id="b4660-112">Policyer om när periodiseringar bör tilldelas och policyer om proportionell fördelning definieras i avsnittet **periodiseringar** när du ställer in planen för tjänstledighet och frånvaro.</span><span class="sxs-lookup"><span data-stu-id="b4660-112">Policies about when accruals should be awarded and policies about proration are defined in the **Accruals** section when setting up the leave and absence plan.</span></span>

### <a name="accrual-frequency"></a><span data-ttu-id="b4660-113">Periodiseringsfrekvens</span><span class="sxs-lookup"><span data-stu-id="b4660-113">Accrual frequency</span></span>

<span data-ttu-id="b4660-114">Periodiseringsfrekvensen definierar hur ofta ledighet periodiseras eller tilldelas.</span><span class="sxs-lookup"><span data-stu-id="b4660-114">The accrual frequency defines how often leave is accrued or awarded.</span></span> <span data-ttu-id="b4660-115">Följande alternativ är tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="b4660-115">The following options are available:</span></span>

- <span data-ttu-id="b4660-116">Dagligen</span><span class="sxs-lookup"><span data-stu-id="b4660-116">Daily</span></span>
- <span data-ttu-id="b4660-117">Varje vecka</span><span class="sxs-lookup"><span data-stu-id="b4660-117">Weekly</span></span>
- <span data-ttu-id="b4660-118">Varannan vecka</span><span class="sxs-lookup"><span data-stu-id="b4660-118">Biweekly</span></span>
- <span data-ttu-id="b4660-119">Halvmånadsvis</span><span class="sxs-lookup"><span data-stu-id="b4660-119">Semimonthly</span></span>
- <span data-ttu-id="b4660-120">Månatlig</span><span class="sxs-lookup"><span data-stu-id="b4660-120">Monthly</span></span>
- <span data-ttu-id="b4660-121">Kvartalsvis</span><span class="sxs-lookup"><span data-stu-id="b4660-121">Quarterly</span></span>
- <span data-ttu-id="b4660-122">Halvårsvis</span><span class="sxs-lookup"><span data-stu-id="b4660-122">Semiannually</span></span>
- <span data-ttu-id="b4660-123">Årligen</span><span class="sxs-lookup"><span data-stu-id="b4660-123">Annually</span></span>
- <span data-ttu-id="b4660-124">Ingen</span><span class="sxs-lookup"><span data-stu-id="b4660-124">None</span></span>

### <a name="accrual-period-basis"></a><span data-ttu-id="b4660-125">Periodiseringsperiodbas</span><span class="sxs-lookup"><span data-stu-id="b4660-125">Accrual period basis</span></span>

<span data-ttu-id="b4660-126">Periodiseringperiodunderlaget bestämmer datumet som används för att beräkna periodiseringsperioder.</span><span class="sxs-lookup"><span data-stu-id="b4660-126">The accrual period basis determines the date that is used to calculate accrual periods.</span></span> <span data-ttu-id="b4660-127">Följande alternativ är tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="b4660-127">The following options are available:</span></span>

- <span data-ttu-id="b4660-128">**Startdatum för planen**</span><span class="sxs-lookup"><span data-stu-id="b4660-128">**Plan start date**</span></span>
- <span data-ttu-id="b4660-129">**Datum för särskilda medarbetare** – när det här alternativet väljs bestäms källan för första datumvärdet som används för att beräkna periodiseringsperioder.</span><span class="sxs-lookup"><span data-stu-id="b4660-129">**Employee specific date** – When this option is selected, the value determines the source of the initial date value that is used to calculate accrual periods.</span></span> <span data-ttu-id="b4660-130">Följande alternativ är tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="b4660-130">The following options are available:</span></span>

    - <span data-ttu-id="b4660-131">Anpassa</span><span class="sxs-lookup"><span data-stu-id="b4660-131">Custom</span></span>
    - <span data-ttu-id="b4660-132">Jubileumsdatum</span><span class="sxs-lookup"><span data-stu-id="b4660-132">Anniversary date</span></span>
    - <span data-ttu-id="b4660-133">Ursprungligt anställningsdatum</span><span class="sxs-lookup"><span data-stu-id="b4660-133">Original hire date</span></span>
    - <span data-ttu-id="b4660-134">Datum för tjänsteålder</span><span class="sxs-lookup"><span data-stu-id="b4660-134">Seniority date</span></span>
    - <span data-ttu-id="b4660-135">Arbetarens justerade startdatum</span><span class="sxs-lookup"><span data-stu-id="b4660-135">Worker's adjusted start date</span></span>
    - <span data-ttu-id="b4660-136">Arbetarens startdatum</span><span class="sxs-lookup"><span data-stu-id="b4660-136">Worker's start date</span></span>

### <a name="accrual-award-date"></a><span data-ttu-id="b4660-137">Belöningsdatum för periodisering</span><span class="sxs-lookup"><span data-stu-id="b4660-137">Accrual award date</span></span>

<span data-ttu-id="b4660-138">Belöningsdatum för periodisering bestämmer när och hur ofta en medarbetaren belönas med ledighet.</span><span class="sxs-lookup"><span data-stu-id="b4660-138">The accrual award date determines when an employee is awarded time off.</span></span> <span data-ttu-id="b4660-139">Följande alternativ är tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="b4660-139">The following options are available:</span></span>

- <span data-ttu-id="b4660-140">**Periodiseringens slutdatum** – medarbetaren kommer att tilldelas ledighet på den sista dagen av belöningsperioden.</span><span class="sxs-lookup"><span data-stu-id="b4660-140">**Accrual period end date** – The employee will be awarded time off on the last day of the award period.</span></span>

    <span data-ttu-id="b4660-141">Om du vill periodisera den korrekta mängden måste periodiseringsprocessen innehålla hela perioden.</span><span class="sxs-lookup"><span data-stu-id="b4660-141">To accrue the correct amount, the accrual process must include the whole period.</span></span> <span data-ttu-id="b4660-142">Exempelvis är 1 januari 2018 till och med 31 januari 2018 periodiseringsperioden.</span><span class="sxs-lookup"><span data-stu-id="b4660-142">For example, the accrual period is January 1, 2018, through January 31, 2018.</span></span> <span data-ttu-id="b4660-143">För januari att ingå måste då avskrivningen köras för 1 februari 2018.</span><span class="sxs-lookup"><span data-stu-id="b4660-143">In this case, for January to be included, the accrual must be run for February 1, 2018.</span></span>

- <span data-ttu-id="b4660-144">**Periodiseringens startdatum** – medarbetaren kommer att tilldelas ledighet på den första dagen av belöningsperioden.</span><span class="sxs-lookup"><span data-stu-id="b4660-144">**Accrual period start date** – The employee will be awarded time off on the first day of the award period.</span></span>

### <a name="accrual-policy-on-enrollment"></a><span data-ttu-id="b4660-145">Periodiseringspolicy vid registrering</span><span class="sxs-lookup"><span data-stu-id="b4660-145">Accrual policy on enrollment</span></span>

<span data-ttu-id="b4660-146">Periodiseringspolicyn vid registreringen definierar hur periodiseringen beräknas när medarbetaren har registrerats i mitten av en periodiseringsperiod.</span><span class="sxs-lookup"><span data-stu-id="b4660-146">The accrual policy on enrollment defines how accrual is calculated when an employee is enrolled in the middle of an accrual period.</span></span> <span data-ttu-id="b4660-147">Följande alternativ är tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="b4660-147">The following options are available:</span></span>

- <span data-ttu-id="b4660-148">**Proportionellt fördelad** – det datumintervall mellan registreringsdatum och startdatum används för att bestämma skillnaden i dagar.</span><span class="sxs-lookup"><span data-stu-id="b4660-148">**Prorated** – The date range between the enrollment date and the start date is used to determine the difference in days.</span></span> <span data-ttu-id="b4660-149">Denna skillnad tillämpas när periodiseringar bearbetas.</span><span class="sxs-lookup"><span data-stu-id="b4660-149">That difference is applied when accruals are processed.</span></span>
- <span data-ttu-id="b4660-150">**Fullständig periodisering** – Den fullständiga periodiseringsmängd, baserat på nivå, tilldelas under den första periodiseringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="b4660-150">**Full accrual** – The full accrual amount, based on the tier, is awarded during the first accrual processing.</span></span>
- <span data-ttu-id="b4660-151">**Ingen periodisering** – ingen periodisering tilldelas till nästa periodiseringsperiod.</span><span class="sxs-lookup"><span data-stu-id="b4660-151">**No accrual** – No accrual is awarded until the next accrual period.</span></span>

### <a name="accrual-policy-on-unenrollment"></a><span data-ttu-id="b4660-152">Periodiseringspolicy vid avregistrering</span><span class="sxs-lookup"><span data-stu-id="b4660-152">Accrual policy on unenrollment</span></span>

<span data-ttu-id="b4660-153">Periodiseringspolicyn vid avregistreringen definierar hur periodiseringen beräknas när medarbetaren har avregistrerats i mitten av en periodiseringsperiod.</span><span class="sxs-lookup"><span data-stu-id="b4660-153">The accrual policy on unenrollment defines how accrual is calculated when an employee is unenrolled in the middle of an accrual period.</span></span> <span data-ttu-id="b4660-154">Följande alternativ är tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="b4660-154">The following options are available:</span></span>

- <span data-ttu-id="b4660-155">**Proportionellt fördelad** – det datumintervall mellan registreringsdatum och startdatum används för att bestämma skillnaden i dagar.</span><span class="sxs-lookup"><span data-stu-id="b4660-155">**Prorated** – The date range between the enrollment date and the start date is used to determine the difference in days.</span></span> <span data-ttu-id="b4660-156">Denna skillnad tillämpas när periodiseringar bearbetas.</span><span class="sxs-lookup"><span data-stu-id="b4660-156">That difference is applied when accruals are processed.</span></span>
- <span data-ttu-id="b4660-157">**Fullständig periodisering** – Den fullständiga periodiseringsmängd, baserat på nivå, tilldelas under den första periodiseringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="b4660-157">**Full accrual** – The full accrual amount, based on the tier, is awarded during the first accrual processing.</span></span>
- <span data-ttu-id="b4660-158">**Ingen periodisering** – ingen periodisering tilldelas till nästa periodiseringsperiod.</span><span class="sxs-lookup"><span data-stu-id="b4660-158">**No accrual** – No accrual is awarded until the next accrual period.</span></span>

## <a name="accrual-schedule"></a><span data-ttu-id="b4660-159">Periodiseringsschema</span><span class="sxs-lookup"><span data-stu-id="b4660-159">Accrual schedule</span></span>

<span data-ttu-id="b4660-160">Periodiseringsschemat avgör hur en medarbetare periodiserar ledig tid och vilka mängder som den medarbetaren ska periodisera och överföra.</span><span class="sxs-lookup"><span data-stu-id="b4660-160">The accrual schedule determines how an employee will accrue time off, and what amounts that employee will accrue and carry forward.</span></span> <span data-ttu-id="b4660-161">Nivåerna kan skapas så att ledig tid beviljas baserat på olika nivåer.</span><span class="sxs-lookup"><span data-stu-id="b4660-161">Tiers can be created so that time off is awarded based on different levels.</span></span>

### <a name="months-of-service"></a><span data-ttu-id="b4660-162">Tjänstgöringsmånader</span><span class="sxs-lookup"><span data-stu-id="b4660-162">Months of service</span></span>

<span data-ttu-id="b4660-163">Värdet **månader** anger minsta antalet månader som medarbetare måste arbeta om du vill ha rätt till periodiseringar.</span><span class="sxs-lookup"><span data-stu-id="b4660-163">The **Months of service** value defines the minimum number of months that employees must work to be entitled to accruals.</span></span> <span data-ttu-id="b4660-164">Om inget lägsta krävs för medarbetare är värdet **0**.</span><span class="sxs-lookup"><span data-stu-id="b4660-164">If no minimum is required for employees, set the value to **0**.</span></span>

### <a name="hours-worked"></a><span data-ttu-id="b4660-165">Arbetade timmar</span><span class="sxs-lookup"><span data-stu-id="b4660-165">Hours worked</span></span>

<span data-ttu-id="b4660-166">Värdet **Arbetade timmar** anger minsta antalet timmar som medarbetare måste arbeta per periodiseringsperiod för att ha rätt till periodiseringar.</span><span class="sxs-lookup"><span data-stu-id="b4660-166">The **Hours worked** value defines the minimum number of hours that employees must work per accrual period to be entitled to accruals.</span></span> <span data-ttu-id="b4660-167">Om inget lägsta krävs för medarbetare är värdet **0**.</span><span class="sxs-lookup"><span data-stu-id="b4660-167">If no minimum is required for employees, set the value to **0**.</span></span>

### <a name="accrual-amount"></a><span data-ttu-id="b4660-168">Periodiseringstid</span><span class="sxs-lookup"><span data-stu-id="b4660-168">Accrual amount</span></span>

<span data-ttu-id="b4660-169">Den periodiserade mängden är antalet timmar eller dagar som medarbetare periodiserar per period.</span><span class="sxs-lookup"><span data-stu-id="b4660-169">The accrual amount is the number of hours or days that employees will accrue per period.</span></span> <span data-ttu-id="b4660-170">Perioden baseras på periodiseringsfrekvensen.</span><span class="sxs-lookup"><span data-stu-id="b4660-170">The period is based on the accrual frequency.</span></span>

### <a name="minimum-balance"></a><span data-ttu-id="b4660-171">Lägsta saldo</span><span class="sxs-lookup"><span data-stu-id="b4660-171">Minimum balance</span></span>

<span data-ttu-id="b4660-172">Ett negativt värde kan användas för minsta saldot om anställda kan begära mer ledighet än vad de har tillgängligt.</span><span class="sxs-lookup"><span data-stu-id="b4660-172">A negative value can be used for the minimum balance if employees can request more leave than they have available.</span></span>

### <a name="maximum-carry-forward"></a><span data-ttu-id="b4660-173">Maximal överföring</span><span class="sxs-lookup"><span data-stu-id="b4660-173">Maximum carry-forward</span></span>

<span data-ttu-id="b4660-174">Periodiseringsprocessen kommer att justera ledighetssaldon som överstiger det maximalt överförda saldot på startdatumet.</span><span class="sxs-lookup"><span data-stu-id="b4660-174">The accrual process will adjust leave balances that exceed the maximum carry-forward balance on the anniversary of the start date.</span></span>

### <a name="grant-amount"></a><span data-ttu-id="b4660-175">Bevilja mängd</span><span class="sxs-lookup"><span data-stu-id="b4660-175">Grant amount</span></span>

<span data-ttu-id="b4660-176">Beviljad mängd är initiala antalet timmar eller dagar som medarbetaren har beviljats när de först registrerar sig i ledighetsplanen.</span><span class="sxs-lookup"><span data-stu-id="b4660-176">The grant amount is the initial number of hours or days that employees are granted when they first enroll in the leave plan.</span></span> <span data-ttu-id="b4660-177">Mängden periodiseras inte för varje periodiseringsperiod.</span><span class="sxs-lookup"><span data-stu-id="b4660-177">The amount doesn't accrue for each accrual period.</span></span>

## <a name="enrollments-and-balances"></a><span data-ttu-id="b4660-178">Registrera och saldon</span><span class="sxs-lookup"><span data-stu-id="b4660-178">Enrollments and balances</span></span>

### <a name="enrollment-date"></a><span data-ttu-id="b4660-179">Datum för anmälan</span><span class="sxs-lookup"><span data-stu-id="b4660-179">Enrollment date</span></span>

<span data-ttu-id="b4660-180">Anmälningsdatumet bestämmer när medarbetaren kan börja periodisera ledig tid.</span><span class="sxs-lookup"><span data-stu-id="b4660-180">The enrollment date determines when an employee can start to accrue time off.</span></span> <span data-ttu-id="b4660-181">Om medarbetaren till exempel har registrerats på en plan för semester den 15 juni 2018 kan hon inte periodisera ledig tid före 15 juni 2018.</span><span class="sxs-lookup"><span data-stu-id="b4660-181">For example, if an employee is enrolled in a vacation plan on June 15, 2018, she can't accrue any time off before June 15, 2018.</span></span>

### <a name="current-balance"></a><span data-ttu-id="b4660-182">Aktuellt saldo</span><span class="sxs-lookup"><span data-stu-id="b4660-182">Current balance</span></span>

<span data-ttu-id="b4660-183">Aktuellt saldo är mängden ledighet som är tillgänglig för begäran om ledighet.</span><span class="sxs-lookup"><span data-stu-id="b4660-183">The current balance is the amount of leave that is available for time off requests.</span></span> <span data-ttu-id="b4660-184">Denna mängd inkluderar periodiseringar, godkända begäran och justeringar som aktuellt datum.</span><span class="sxs-lookup"><span data-stu-id="b4660-184">This amount includes accruals, approved requests, and adjustments through the current date.</span></span>

### <a name="current-balance-examples"></a><span data-ttu-id="b4660-185">Exempel på aktuellt saldo</span><span class="sxs-lookup"><span data-stu-id="b4660-185">Current balance examples</span></span>

#### <a name="annual-plan"></a><span data-ttu-id="b4660-186">Årlig plan</span><span class="sxs-lookup"><span data-stu-id="b4660-186">Annual plan</span></span>

<span data-ttu-id="b4660-187">**Planinställningar**</span><span class="sxs-lookup"><span data-stu-id="b4660-187">**Plan setup**</span></span>

| <span data-ttu-id="b4660-188">Startdatum för planen</span><span class="sxs-lookup"><span data-stu-id="b4660-188">Plan start date</span></span> | <span data-ttu-id="b4660-189">Datum för anmälan</span><span class="sxs-lookup"><span data-stu-id="b4660-189">Enrollment date</span></span> | <span data-ttu-id="b4660-190">Periodiseringsfrekvens</span><span class="sxs-lookup"><span data-stu-id="b4660-190">Accrual frequency</span></span> | <span data-ttu-id="b4660-191">Periodiseringsperiodbas</span><span class="sxs-lookup"><span data-stu-id="b4660-191">Accrual period basis</span></span> | <span data-ttu-id="b4660-192">Belöningsdatum för periodisering</span><span class="sxs-lookup"><span data-stu-id="b4660-192">Accrual award date</span></span>    |
|-----------------|-----------------|-------------------|----------------------|-----------------------|
| <span data-ttu-id="b4660-193">1/1/2018</span><span class="sxs-lookup"><span data-stu-id="b4660-193">1/1/2018</span></span>        | <span data-ttu-id="b4660-194">1/1/2018</span><span class="sxs-lookup"><span data-stu-id="b4660-194">1/1/2018</span></span>        | <span data-ttu-id="b4660-195">Årlig</span><span class="sxs-lookup"><span data-stu-id="b4660-195">Annual</span></span>            | <span data-ttu-id="b4660-196">Startdatum för planen</span><span class="sxs-lookup"><span data-stu-id="b4660-196">Plan start date</span></span>      | <span data-ttu-id="b4660-197">Slut på periodiseringsperiod</span><span class="sxs-lookup"><span data-stu-id="b4660-197">End of accrual period</span></span> |

<span data-ttu-id="b4660-198">Periodiseringar ska behandlas 1 januari 2019 (1/1/2019), så att hela den perioden inkluderas.</span><span class="sxs-lookup"><span data-stu-id="b4660-198">Accruals are processed on January 1, 2019 (1/1/2019), so that that whole period is included.</span></span>

<span data-ttu-id="b4660-199">**Resultat**</span><span class="sxs-lookup"><span data-stu-id="b4660-199">**Results**</span></span>

| <span data-ttu-id="b4660-200">Periodiseringstid</span><span class="sxs-lookup"><span data-stu-id="b4660-200">Accrual amount</span></span> | <span data-ttu-id="b4660-201">Lägsta saldo</span><span class="sxs-lookup"><span data-stu-id="b4660-201">Minimum balance</span></span> | <span data-ttu-id="b4660-202">Maximal överföring</span><span class="sxs-lookup"><span data-stu-id="b4660-202">Maximum carry-forward</span></span> | <span data-ttu-id="b4660-203">Begära mängd</span><span class="sxs-lookup"><span data-stu-id="b4660-203">Request amount</span></span> | <span data-ttu-id="b4660-204">Registrera saldo (den 1/1/2019)</span><span class="sxs-lookup"><span data-stu-id="b4660-204">Current balance (as of 1/1/2019)</span></span> |
|----------------|-----------------|-----------------------|----------------|----------------------------------|
| <span data-ttu-id="b4660-205">200</span><span class="sxs-lookup"><span data-stu-id="b4660-205">200</span></span>            | <span data-ttu-id="b4660-206">0</span><span class="sxs-lookup"><span data-stu-id="b4660-206">0</span></span>               | <span data-ttu-id="b4660-207">120</span><span class="sxs-lookup"><span data-stu-id="b4660-207">120</span></span>                   | <span data-ttu-id="b4660-208">40</span><span class="sxs-lookup"><span data-stu-id="b4660-208">40</span></span>             | <span data-ttu-id="b4660-209">160</span><span class="sxs-lookup"><span data-stu-id="b4660-209">160</span></span>                              |

<span data-ttu-id="b4660-210">Aktuellt saldo (160) = periodiserad mängd (200) - begärd mängd (40)</span><span class="sxs-lookup"><span data-stu-id="b4660-210">Current balance (160) = Accrual amount (200) – Request amount (40)</span></span>

#### <a name="semimonthly-plan"></a><span data-ttu-id="b4660-211">Halvmånadsvis plan</span><span class="sxs-lookup"><span data-stu-id="b4660-211">Semimonthly plan</span></span>

<span data-ttu-id="b4660-212">**Planinställningar**</span><span class="sxs-lookup"><span data-stu-id="b4660-212">**Plan setup**</span></span>

| <span data-ttu-id="b4660-213">Startdatum för planen</span><span class="sxs-lookup"><span data-stu-id="b4660-213">Plan start date</span></span> | <span data-ttu-id="b4660-214">Datum för anmälan</span><span class="sxs-lookup"><span data-stu-id="b4660-214">Enrollment date</span></span> | <span data-ttu-id="b4660-215">Periodiseringsfrekvens</span><span class="sxs-lookup"><span data-stu-id="b4660-215">Accrual frequency</span></span> | <span data-ttu-id="b4660-216">Periodiseringsperiodbas</span><span class="sxs-lookup"><span data-stu-id="b4660-216">Accrual period basis</span></span> | <span data-ttu-id="b4660-217">Belöningsdatum för periodisering</span><span class="sxs-lookup"><span data-stu-id="b4660-217">Accrual award date</span></span>    |
|-----------------|-----------------|-------------------|----------------------|-----------------------|
| <span data-ttu-id="b4660-218">1/1/2018</span><span class="sxs-lookup"><span data-stu-id="b4660-218">1/1/2018</span></span>        | <span data-ttu-id="b4660-219">2/1/2018</span><span class="sxs-lookup"><span data-stu-id="b4660-219">2/1/2018</span></span>        | <span data-ttu-id="b4660-220">Halvmånadsvis</span><span class="sxs-lookup"><span data-stu-id="b4660-220">Semimonthly</span></span>       | <span data-ttu-id="b4660-221">Startdatum för planen</span><span class="sxs-lookup"><span data-stu-id="b4660-221">Plan start date</span></span>      | <span data-ttu-id="b4660-222">Slut på periodiseringsperiod</span><span class="sxs-lookup"><span data-stu-id="b4660-222">End of accrual period</span></span> |

<span data-ttu-id="b4660-223">Periodiseringar ska behandlas 1 maj 2018 (5/1/2018), så att hela den perioden inkluderas.</span><span class="sxs-lookup"><span data-stu-id="b4660-223">Accruals are processed on May 1, 2018 (5/1/2018), so that that whole period is included.</span></span>

<span data-ttu-id="b4660-224">**Resultat**</span><span class="sxs-lookup"><span data-stu-id="b4660-224">**Results**</span></span>

| <span data-ttu-id="b4660-225">Periodiseringstid</span><span class="sxs-lookup"><span data-stu-id="b4660-225">Accrual amount</span></span> | <span data-ttu-id="b4660-226">Lägsta saldo</span><span class="sxs-lookup"><span data-stu-id="b4660-226">Minimum balance</span></span> | <span data-ttu-id="b4660-227">Maximal överföring</span><span class="sxs-lookup"><span data-stu-id="b4660-227">Maximum carry-forward</span></span> | <span data-ttu-id="b4660-228">Begära mängd</span><span class="sxs-lookup"><span data-stu-id="b4660-228">Request amount</span></span> | <span data-ttu-id="b4660-229">Registrera saldo (den 1/1/2019)</span><span class="sxs-lookup"><span data-stu-id="b4660-229">Current balance (as of 1/1/2019)</span></span> |
|----------------|-----------------|-----------------------|----------------|----------------------------------|
| <span data-ttu-id="b4660-230">5</span><span class="sxs-lookup"><span data-stu-id="b4660-230">5</span></span>              | <span data-ttu-id="b4660-231">0</span><span class="sxs-lookup"><span data-stu-id="b4660-231">0</span></span>               | <span data-ttu-id="b4660-232">120</span><span class="sxs-lookup"><span data-stu-id="b4660-232">120</span></span>                   | <span data-ttu-id="b4660-233">8</span><span class="sxs-lookup"><span data-stu-id="b4660-233">8</span></span>              | <span data-ttu-id="b4660-234">22</span><span class="sxs-lookup"><span data-stu-id="b4660-234">22</span></span>                               |

<span data-ttu-id="b4660-235">Aktuellt saldo (22) = periodiserad mängd (5x6) - begärd mängd (8)</span><span class="sxs-lookup"><span data-stu-id="b4660-235">Current balance (22) = Accrual amount (5 × 6) – Request amount (8)</span></span>

#### <a name="monthly-plan"></a><span data-ttu-id="b4660-236">Månadsvis plan</span><span class="sxs-lookup"><span data-stu-id="b4660-236">Monthly plan</span></span>

<span data-ttu-id="b4660-237">**Planinställningar**</span><span class="sxs-lookup"><span data-stu-id="b4660-237">**Plan setup**</span></span>

| <span data-ttu-id="b4660-238">Startdatum för planen</span><span class="sxs-lookup"><span data-stu-id="b4660-238">Plan start date</span></span> | <span data-ttu-id="b4660-239">Datum för anmälan</span><span class="sxs-lookup"><span data-stu-id="b4660-239">Enrollment date</span></span> | <span data-ttu-id="b4660-240">Periodiseringsfrekvens</span><span class="sxs-lookup"><span data-stu-id="b4660-240">Accrual frequency</span></span> | <span data-ttu-id="b4660-241">Periodiseringsperiodbas</span><span class="sxs-lookup"><span data-stu-id="b4660-241">Accrual period basis</span></span> | <span data-ttu-id="b4660-242">Belöningsdatum för periodisering</span><span class="sxs-lookup"><span data-stu-id="b4660-242">Accrual award date</span></span>    |
|-----------------|-----------------|-------------------|----------------------|-----------------------|
| <span data-ttu-id="b4660-243">1/1/2018</span><span class="sxs-lookup"><span data-stu-id="b4660-243">1/1/2018</span></span>        | <span data-ttu-id="b4660-244">2/1/2018</span><span class="sxs-lookup"><span data-stu-id="b4660-244">2/1/2018</span></span>        | <span data-ttu-id="b4660-245">Halvmånadsvis</span><span class="sxs-lookup"><span data-stu-id="b4660-245">Semimonthly</span></span>       | <span data-ttu-id="b4660-246">Startdatum för planen</span><span class="sxs-lookup"><span data-stu-id="b4660-246">Plan start date</span></span>      | <span data-ttu-id="b4660-247">Slut på periodiseringsperiod</span><span class="sxs-lookup"><span data-stu-id="b4660-247">End of accrual period</span></span> |

<span data-ttu-id="b4660-248">Periodiseringar ska behandlas 1 maj 2018 (5/1/2018), så att hela den perioden inkluderas.</span><span class="sxs-lookup"><span data-stu-id="b4660-248">Accruals are processed on May 1, 2018 (5/1/2018), so that that whole period is included.</span></span>

<span data-ttu-id="b4660-249">**Resultat**</span><span class="sxs-lookup"><span data-stu-id="b4660-249">**Results**</span></span>

| <span data-ttu-id="b4660-250">Periodiseringstid</span><span class="sxs-lookup"><span data-stu-id="b4660-250">Accrual amount</span></span> | <span data-ttu-id="b4660-251">Lägsta saldo</span><span class="sxs-lookup"><span data-stu-id="b4660-251">Minimum balance</span></span> | <span data-ttu-id="b4660-252">Maximal överföring</span><span class="sxs-lookup"><span data-stu-id="b4660-252">Maximum carry-forward</span></span> | <span data-ttu-id="b4660-253">Begära mängd</span><span class="sxs-lookup"><span data-stu-id="b4660-253">Request amount</span></span> | <span data-ttu-id="b4660-254">Registrera saldo (den 1/1/2019)</span><span class="sxs-lookup"><span data-stu-id="b4660-254">Current balance (as of 1/1/2019)</span></span> |
|----------------|-----------------|-----------------------|----------------|----------------------------------|
| <span data-ttu-id="b4660-255">5</span><span class="sxs-lookup"><span data-stu-id="b4660-255">5</span></span>              | <span data-ttu-id="b4660-256">0</span><span class="sxs-lookup"><span data-stu-id="b4660-256">0</span></span>               | <span data-ttu-id="b4660-257">120</span><span class="sxs-lookup"><span data-stu-id="b4660-257">120</span></span>                   | <span data-ttu-id="b4660-258">8</span><span class="sxs-lookup"><span data-stu-id="b4660-258">8</span></span>              | <span data-ttu-id="b4660-259">7</span><span class="sxs-lookup"><span data-stu-id="b4660-259">7</span></span>                                |

<span data-ttu-id="b4660-260">Aktuellt saldo (7) = periodiserad mängd (5x3) - begärd mängd (8)</span><span class="sxs-lookup"><span data-stu-id="b4660-260">Current balance (7) = Accrual amount (5 × 3) – Request amount (8)</span></span>

### <a name="forecasted-balance"></a><span data-ttu-id="b4660-261">Prognossaldo</span><span class="sxs-lookup"><span data-stu-id="b4660-261">Forecasted balance</span></span>

<span data-ttu-id="b4660-262">*Prognossaldot* är mängden ledighet som är tillgängligt ett framtida datum.</span><span class="sxs-lookup"><span data-stu-id="b4660-262">The *forecasted balance* is the amount of leave that is available on a future date.</span></span> <span data-ttu-id="b4660-263">Periodiseringar och överförda justeringar prognostiseras fram till detta datum.</span><span class="sxs-lookup"><span data-stu-id="b4660-263">Accruals and carry-forward adjustments are forecasted up to that date.</span></span>

<span data-ttu-id="b4660-264">Följande formel används:</span><span class="sxs-lookup"><span data-stu-id="b4660-264">The following formula is used:</span></span>

<span data-ttu-id="b4660-265">Måndag prognostiserat saldo = aktuellt saldo – begäran + periodiseringar – överför justering</span><span class="sxs-lookup"><span data-stu-id="b4660-265">Monday forecasted balance = Current balance – Requests + Accruals – Carry-forward adjustment</span></span>

### <a name="forecasted-balance-examples"></a><span data-ttu-id="b4660-266">Exempel på prognostiserat saldo</span><span class="sxs-lookup"><span data-stu-id="b4660-266">Forecasted balance examples</span></span>

#### <a name="annual-plan"></a><span data-ttu-id="b4660-267">Årlig plan</span><span class="sxs-lookup"><span data-stu-id="b4660-267">Annual plan</span></span>

<span data-ttu-id="b4660-268">**Planinställningar**</span><span class="sxs-lookup"><span data-stu-id="b4660-268">**Plan setup**</span></span>

| <span data-ttu-id="b4660-269">Startdatum för planen</span><span class="sxs-lookup"><span data-stu-id="b4660-269">Plan start date</span></span> | <span data-ttu-id="b4660-270">Datum för anmälan</span><span class="sxs-lookup"><span data-stu-id="b4660-270">Enrollment date</span></span> | <span data-ttu-id="b4660-271">Periodiseringsfrekvens</span><span class="sxs-lookup"><span data-stu-id="b4660-271">Accrual frequency</span></span> | <span data-ttu-id="b4660-272">Periodiseringsperiodbas</span><span class="sxs-lookup"><span data-stu-id="b4660-272">Accrual period basis</span></span> | <span data-ttu-id="b4660-273">Belöningsdatum för periodisering</span><span class="sxs-lookup"><span data-stu-id="b4660-273">Accrual award date</span></span>    |
|-----------------|-----------------|-------------------|----------------------|-----------------------|
| <span data-ttu-id="b4660-274">1/1/2018</span><span class="sxs-lookup"><span data-stu-id="b4660-274">1/1/2018</span></span>        | <span data-ttu-id="b4660-275">1/1/2018</span><span class="sxs-lookup"><span data-stu-id="b4660-275">1/1/2018</span></span>        | <span data-ttu-id="b4660-276">Årlig</span><span class="sxs-lookup"><span data-stu-id="b4660-276">Annual</span></span>            | <span data-ttu-id="b4660-277">Startdatum för planen</span><span class="sxs-lookup"><span data-stu-id="b4660-277">Plan start date</span></span>      | <span data-ttu-id="b4660-278">Slut på periodiseringsperiod</span><span class="sxs-lookup"><span data-stu-id="b4660-278">End of accrual period</span></span> |

<span data-ttu-id="b4660-279">Periodiseringar ska behandlas 15 februari 2019 (2/15/2019), så att hela den perioden inkluderas.</span><span class="sxs-lookup"><span data-stu-id="b4660-279">Accruals are processed on February 15, 2019 (2/15/2019), so that that whole period is included.</span></span>

<span data-ttu-id="b4660-280">**Resultat**</span><span class="sxs-lookup"><span data-stu-id="b4660-280">**Results**</span></span>

| <span data-ttu-id="b4660-281">Periodiseringstid</span><span class="sxs-lookup"><span data-stu-id="b4660-281">Accrual amount</span></span> | <span data-ttu-id="b4660-282">Lägsta saldo</span><span class="sxs-lookup"><span data-stu-id="b4660-282">Minimum balance</span></span> | <span data-ttu-id="b4660-283">Maximal överföring</span><span class="sxs-lookup"><span data-stu-id="b4660-283">Maximum carry-forward</span></span> | <span data-ttu-id="b4660-284">Aktuellt saldo</span><span class="sxs-lookup"><span data-stu-id="b4660-284">Current balance</span></span> | <span data-ttu-id="b4660-285">Prognostiserat saldo (den 2/15/2019)</span><span class="sxs-lookup"><span data-stu-id="b4660-285">Forecasted balance (as of 2/15/2019)</span></span> |
|----------------|-----------------|-----------------------|-----------------|--------------------------------------|
| <span data-ttu-id="b4660-286">20</span><span class="sxs-lookup"><span data-stu-id="b4660-286">20</span></span>             | <span data-ttu-id="b4660-287">0</span><span class="sxs-lookup"><span data-stu-id="b4660-287">0</span></span>               | <span data-ttu-id="b4660-288">20</span><span class="sxs-lookup"><span data-stu-id="b4660-288">20</span></span>                    | <span data-ttu-id="b4660-289">40</span><span class="sxs-lookup"><span data-stu-id="b4660-289">40</span></span>              | <span data-ttu-id="b4660-290">40</span><span class="sxs-lookup"><span data-stu-id="b4660-290">40</span></span>                                   |

<span data-ttu-id="b4660-291">Prognostiserat saldo (40) = periodiserad mängd (20) + aktuellt saldo (40) – överför justering (20)</span><span class="sxs-lookup"><span data-stu-id="b4660-291">Forecasted balance (40) = Accrual amount (20) + Current balance (40) – Carry-forward adjustment (20)</span></span>

#### <a name="semimonthly-plan"></a><span data-ttu-id="b4660-292">Halvmånadsvis plan</span><span class="sxs-lookup"><span data-stu-id="b4660-292">Semimonthly plan</span></span>

<span data-ttu-id="b4660-293">**Planinställningar**</span><span class="sxs-lookup"><span data-stu-id="b4660-293">**Plan setup**</span></span>

| <span data-ttu-id="b4660-294">Startdatum för planen</span><span class="sxs-lookup"><span data-stu-id="b4660-294">Plan start date</span></span> | <span data-ttu-id="b4660-295">Datum för anmälan</span><span class="sxs-lookup"><span data-stu-id="b4660-295">Enrollment date</span></span> | <span data-ttu-id="b4660-296">Periodiseringsfrekvens</span><span class="sxs-lookup"><span data-stu-id="b4660-296">Accrual frequency</span></span> | <span data-ttu-id="b4660-297">Periodiseringsperiodbas</span><span class="sxs-lookup"><span data-stu-id="b4660-297">Accrual period basis</span></span> | <span data-ttu-id="b4660-298">Belöningsdatum för periodisering</span><span class="sxs-lookup"><span data-stu-id="b4660-298">Accrual award date</span></span>    |
|-----------------|-----------------|-------------------|----------------------|-----------------------|
| <span data-ttu-id="b4660-299">1/1/2018</span><span class="sxs-lookup"><span data-stu-id="b4660-299">1/1/2018</span></span>        | <span data-ttu-id="b4660-300">2/1/2018</span><span class="sxs-lookup"><span data-stu-id="b4660-300">2/1/2018</span></span>        | <span data-ttu-id="b4660-301">Halvmånadsvis</span><span class="sxs-lookup"><span data-stu-id="b4660-301">Semimonthly</span></span>       | <span data-ttu-id="b4660-302">Startdatum för planen</span><span class="sxs-lookup"><span data-stu-id="b4660-302">Plan start date</span></span>      | <span data-ttu-id="b4660-303">Slut på periodiseringsperiod</span><span class="sxs-lookup"><span data-stu-id="b4660-303">End of accrual period</span></span> |

<span data-ttu-id="b4660-304">Periodiseringar ska behandlas 15 februari 2019 (2/15/2019), så att hela den perioden inkluderas.</span><span class="sxs-lookup"><span data-stu-id="b4660-304">Accruals are processed on February 15, 2019 (2/15/2019), so that that whole period is included.</span></span>

<span data-ttu-id="b4660-305">**Resultat**</span><span class="sxs-lookup"><span data-stu-id="b4660-305">**Results**</span></span>

| <span data-ttu-id="b4660-306">Periodiseringstid</span><span class="sxs-lookup"><span data-stu-id="b4660-306">Accrual amount</span></span> | <span data-ttu-id="b4660-307">Lägsta saldo</span><span class="sxs-lookup"><span data-stu-id="b4660-307">Minimum balance</span></span> | <span data-ttu-id="b4660-308">Maximal överföring</span><span class="sxs-lookup"><span data-stu-id="b4660-308">Maximum carry-forward</span></span> | <span data-ttu-id="b4660-309">Aktuellt saldo</span><span class="sxs-lookup"><span data-stu-id="b4660-309">Current balance</span></span> | <span data-ttu-id="b4660-310">Prognostiserat saldo (den 2/15/2019)</span><span class="sxs-lookup"><span data-stu-id="b4660-310">Forecasted balance (as of 2/15/2019)</span></span> |
|----------------|-----------------|-----------------------|-----------------|--------------------------------------|
| <span data-ttu-id="b4660-311">5</span><span class="sxs-lookup"><span data-stu-id="b4660-311">5</span></span>              | <span data-ttu-id="b4660-312">0</span><span class="sxs-lookup"><span data-stu-id="b4660-312">0</span></span>               | <span data-ttu-id="b4660-313">20</span><span class="sxs-lookup"><span data-stu-id="b4660-313">20</span></span>                    | <span data-ttu-id="b4660-314">40</span><span class="sxs-lookup"><span data-stu-id="b4660-314">40</span></span>              | <span data-ttu-id="b4660-315">35</span><span class="sxs-lookup"><span data-stu-id="b4660-315">35</span></span>                                   |

<span data-ttu-id="b4660-316">Prognostiserat saldo (35) = periodiserad mängd (5x3) + aktuellt saldo (40) – överför justering (20)</span><span class="sxs-lookup"><span data-stu-id="b4660-316">Forecasted balance (35) = Accrual amount (5 × 3) + Current balance (40) – Carry-forward adjustment (20)</span></span>

#### <a name="monthly-plan"></a><span data-ttu-id="b4660-317">Månadsvis plan</span><span class="sxs-lookup"><span data-stu-id="b4660-317">Monthly plan</span></span>

<span data-ttu-id="b4660-318">**Planinställningar**</span><span class="sxs-lookup"><span data-stu-id="b4660-318">**Plan setup**</span></span>

| <span data-ttu-id="b4660-319">Startdatum för planen</span><span class="sxs-lookup"><span data-stu-id="b4660-319">Plan start date</span></span> | <span data-ttu-id="b4660-320">Datum för anmälan</span><span class="sxs-lookup"><span data-stu-id="b4660-320">Enrollment date</span></span> | <span data-ttu-id="b4660-321">Periodiseringsfrekvens</span><span class="sxs-lookup"><span data-stu-id="b4660-321">Accrual frequency</span></span> | <span data-ttu-id="b4660-322">Periodiseringsperiodbas</span><span class="sxs-lookup"><span data-stu-id="b4660-322">Accrual period basis</span></span> | <span data-ttu-id="b4660-323">Belöningsdatum för periodisering</span><span class="sxs-lookup"><span data-stu-id="b4660-323">Accrual award date</span></span>    |
|-----------------|-----------------|-------------------|----------------------|-----------------------|
| <span data-ttu-id="b4660-324">1/1/2018</span><span class="sxs-lookup"><span data-stu-id="b4660-324">1/1/2018</span></span>        | <span data-ttu-id="b4660-325">2/1/2018</span><span class="sxs-lookup"><span data-stu-id="b4660-325">2/1/2018</span></span>        | <span data-ttu-id="b4660-326">Halvmånadsvis</span><span class="sxs-lookup"><span data-stu-id="b4660-326">Semimonthly</span></span>       | <span data-ttu-id="b4660-327">Startdatum för planen</span><span class="sxs-lookup"><span data-stu-id="b4660-327">Plan start date</span></span>      | <span data-ttu-id="b4660-328">Slut på periodiseringsperiod</span><span class="sxs-lookup"><span data-stu-id="b4660-328">End of accrual period</span></span> |

<span data-ttu-id="b4660-329">Periodiseringar ska behandlas 15 februari 2019 (2/15/2019), så att hela den perioden inkluderas.</span><span class="sxs-lookup"><span data-stu-id="b4660-329">Accruals are processed on February 15, 2019 (2/15/2019), so that that whole period is included.</span></span>

<span data-ttu-id="b4660-330">**Resultat**</span><span class="sxs-lookup"><span data-stu-id="b4660-330">**Results**</span></span>

| <span data-ttu-id="b4660-331">Periodiseringstid</span><span class="sxs-lookup"><span data-stu-id="b4660-331">Accrual amount</span></span> | <span data-ttu-id="b4660-332">Lägsta saldo</span><span class="sxs-lookup"><span data-stu-id="b4660-332">Minimum balance</span></span> | <span data-ttu-id="b4660-333">Maximal överföring</span><span class="sxs-lookup"><span data-stu-id="b4660-333">Maximum carry-forward</span></span> | <span data-ttu-id="b4660-334">Aktuellt saldo</span><span class="sxs-lookup"><span data-stu-id="b4660-334">Current balance</span></span> | <span data-ttu-id="b4660-335">Prognostiserat saldo (den 2/15/2019)</span><span class="sxs-lookup"><span data-stu-id="b4660-335">Forecasted balance (as of 2/15/2019)</span></span> |
|----------------|-----------------|-----------------------|-----------------|--------------------------------------|
| <span data-ttu-id="b4660-336">10</span><span class="sxs-lookup"><span data-stu-id="b4660-336">10</span></span>             | <span data-ttu-id="b4660-337">0</span><span class="sxs-lookup"><span data-stu-id="b4660-337">0</span></span>               | <span data-ttu-id="b4660-338">20</span><span class="sxs-lookup"><span data-stu-id="b4660-338">20</span></span>                    | <span data-ttu-id="b4660-339">40</span><span class="sxs-lookup"><span data-stu-id="b4660-339">40</span></span>              | <span data-ttu-id="b4660-340">30</span><span class="sxs-lookup"><span data-stu-id="b4660-340">30</span></span>                                   |

<span data-ttu-id="b4660-341">Prognostiserat saldo (30) = periodiserad mängd (10x1) + aktuellt saldo (40) – överför justering (20)</span><span class="sxs-lookup"><span data-stu-id="b4660-341">Forecasted balance (30) = Accrual amount (10 × 1) + Current balance (40) – Carry-forward adjustment (20)</span></span>

### <a name="proration-balance-examples"></a><span data-ttu-id="b4660-342">Exempel på proportionell fördelning av saldo</span><span class="sxs-lookup"><span data-stu-id="b4660-342">Proration balance examples</span></span>

#### <a name="prorated-monthly-plan"></a><span data-ttu-id="b4660-343">Månatlig plan med proportionell fördelning</span><span class="sxs-lookup"><span data-stu-id="b4660-343">Prorated monthly plan</span></span>

<span data-ttu-id="b4660-344">**Planinställningar**</span><span class="sxs-lookup"><span data-stu-id="b4660-344">**Plan setup**</span></span>

| <span data-ttu-id="b4660-345">Startdatum för planen</span><span class="sxs-lookup"><span data-stu-id="b4660-345">Plan start date</span></span> | <span data-ttu-id="b4660-346">Periodiseringsfrekvens</span><span class="sxs-lookup"><span data-stu-id="b4660-346">Accrual frequency</span></span> | <span data-ttu-id="b4660-347">Periodiseringsperiodbas</span><span class="sxs-lookup"><span data-stu-id="b4660-347">Accrual period basis</span></span> |
|-----------------|-------------------|----------------------|
| <span data-ttu-id="b4660-348">1/1/2018</span><span class="sxs-lookup"><span data-stu-id="b4660-348">1/1/2018</span></span>        | <span data-ttu-id="b4660-349">Månatlig</span><span class="sxs-lookup"><span data-stu-id="b4660-349">Monthly</span></span>           | <span data-ttu-id="b4660-350">Startdatum för planen</span><span class="sxs-lookup"><span data-stu-id="b4660-350">Plan start date</span></span>      |

<span data-ttu-id="b4660-351">**Resultat**</span><span class="sxs-lookup"><span data-stu-id="b4660-351">**Results**</span></span>

| <span data-ttu-id="b4660-352">Medarbetare</span><span class="sxs-lookup"><span data-stu-id="b4660-352">Employee</span></span>            | <span data-ttu-id="b4660-353">Tjänstgöringsmånader</span><span class="sxs-lookup"><span data-stu-id="b4660-353">Months of service</span></span> | <span data-ttu-id="b4660-354">Datum för anmälan</span><span class="sxs-lookup"><span data-stu-id="b4660-354">Enrollment date</span></span> | <span data-ttu-id="b4660-355">Startdatum</span><span class="sxs-lookup"><span data-stu-id="b4660-355">Start date</span></span> | <span data-ttu-id="b4660-356">Periodiseringstid</span><span class="sxs-lookup"><span data-stu-id="b4660-356">Accrual amount</span></span> | <span data-ttu-id="b4660-357">Bearbeta periodisering</span><span class="sxs-lookup"><span data-stu-id="b4660-357">Process accrual</span></span> | <span data-ttu-id="b4660-358">Balans</span><span class="sxs-lookup"><span data-stu-id="b4660-358">Balance</span></span> |
|---------------------|-------------------|-----------------|------------|----------------|-----------------|---------|
| <span data-ttu-id="b4660-359">Jeannette Nicholson</span><span class="sxs-lookup"><span data-stu-id="b4660-359">Jeannette Nicholson</span></span> | <span data-ttu-id="b4660-360">0,00</span><span class="sxs-lookup"><span data-stu-id="b4660-360">0.00</span></span>              | <span data-ttu-id="b4660-361">6/1/2018</span><span class="sxs-lookup"><span data-stu-id="b4660-361">6/1/2018</span></span>        | <span data-ttu-id="b4660-362">6/1/2018</span><span class="sxs-lookup"><span data-stu-id="b4660-362">6/1/2018</span></span>   | <span data-ttu-id="b4660-363">1,00</span><span class="sxs-lookup"><span data-stu-id="b4660-363">1.00</span></span>           | <span data-ttu-id="b4660-364">9/1/2018</span><span class="sxs-lookup"><span data-stu-id="b4660-364">9/1/2018</span></span>        | <span data-ttu-id="b4660-365">3,00</span><span class="sxs-lookup"><span data-stu-id="b4660-365">3.00</span></span>    |
| <span data-ttu-id="b4660-366">Jay Norman</span><span class="sxs-lookup"><span data-stu-id="b4660-366">Jay Norman</span></span>          | <span data-ttu-id="b4660-367">0,00</span><span class="sxs-lookup"><span data-stu-id="b4660-367">0.00</span></span>              | <span data-ttu-id="b4660-368">6/15/2018</span><span class="sxs-lookup"><span data-stu-id="b4660-368">6/15/2018</span></span>       | <span data-ttu-id="b4660-369">6/15/2018</span><span class="sxs-lookup"><span data-stu-id="b4660-369">6/15/2018</span></span>  | <span data-ttu-id="b4660-370">1,00</span><span class="sxs-lookup"><span data-stu-id="b4660-370">1.00</span></span>           | <span data-ttu-id="b4660-371">9/1/2018</span><span class="sxs-lookup"><span data-stu-id="b4660-371">9/1/2018</span></span>        | <span data-ttu-id="b4660-372">2,53</span><span class="sxs-lookup"><span data-stu-id="b4660-372">2.53</span></span>    |

#### <a name="full-accrual-monthly-plan"></a><span data-ttu-id="b4660-373">Fullständig månatlig plan för periodisering</span><span class="sxs-lookup"><span data-stu-id="b4660-373">Full accrual monthly plan</span></span>

<span data-ttu-id="b4660-374">**Planinställningar**</span><span class="sxs-lookup"><span data-stu-id="b4660-374">**Plan setup**</span></span>

| <span data-ttu-id="b4660-375">Startdatum för planen</span><span class="sxs-lookup"><span data-stu-id="b4660-375">Plan start date</span></span> | <span data-ttu-id="b4660-376">Periodiseringsfrekvens</span><span class="sxs-lookup"><span data-stu-id="b4660-376">Accrual frequency</span></span> | <span data-ttu-id="b4660-377">Periodiseringsperiodbas</span><span class="sxs-lookup"><span data-stu-id="b4660-377">Accrual period basis</span></span> |
|-----------------|-------------------|----------------------|
| <span data-ttu-id="b4660-378">1/1/2018</span><span class="sxs-lookup"><span data-stu-id="b4660-378">1/1/2018</span></span>        | <span data-ttu-id="b4660-379">Månatlig</span><span class="sxs-lookup"><span data-stu-id="b4660-379">Monthly</span></span>           | <span data-ttu-id="b4660-380">Startdatum för planen</span><span class="sxs-lookup"><span data-stu-id="b4660-380">Plan start date</span></span>      |

<span data-ttu-id="b4660-381">**Resultat**</span><span class="sxs-lookup"><span data-stu-id="b4660-381">**Results**</span></span>

| <span data-ttu-id="b4660-382">Medarbetare</span><span class="sxs-lookup"><span data-stu-id="b4660-382">Employee</span></span>            | <span data-ttu-id="b4660-383">Tjänstgöringsmånader</span><span class="sxs-lookup"><span data-stu-id="b4660-383">Months of service</span></span> | <span data-ttu-id="b4660-384">Datum för anmälan</span><span class="sxs-lookup"><span data-stu-id="b4660-384">Enrollment date</span></span> | <span data-ttu-id="b4660-385">Startdatum</span><span class="sxs-lookup"><span data-stu-id="b4660-385">Start date</span></span> | <span data-ttu-id="b4660-386">Periodiseringstid</span><span class="sxs-lookup"><span data-stu-id="b4660-386">Accrual amount</span></span> | <span data-ttu-id="b4660-387">Bearbeta periodisering</span><span class="sxs-lookup"><span data-stu-id="b4660-387">Process accrual</span></span> | <span data-ttu-id="b4660-388">Balans</span><span class="sxs-lookup"><span data-stu-id="b4660-388">Balance</span></span> |
|---------------------|-------------------|-----------------|------------|----------------|-----------------|---------|
| <span data-ttu-id="b4660-389">Jeannette Nicholson</span><span class="sxs-lookup"><span data-stu-id="b4660-389">Jeannette Nicholson</span></span> | <span data-ttu-id="b4660-390">0,00</span><span class="sxs-lookup"><span data-stu-id="b4660-390">0.00</span></span>              | <span data-ttu-id="b4660-391">6/1/2018</span><span class="sxs-lookup"><span data-stu-id="b4660-391">6/1/2018</span></span>        | <span data-ttu-id="b4660-392">6/1/2018</span><span class="sxs-lookup"><span data-stu-id="b4660-392">6/1/2018</span></span>   | <span data-ttu-id="b4660-393">1,00</span><span class="sxs-lookup"><span data-stu-id="b4660-393">1.00</span></span>           | <span data-ttu-id="b4660-394">9/1/2018</span><span class="sxs-lookup"><span data-stu-id="b4660-394">9/1/2018</span></span>        | <span data-ttu-id="b4660-395">3,00</span><span class="sxs-lookup"><span data-stu-id="b4660-395">3.00</span></span>    |
| <span data-ttu-id="b4660-396">Jay Norman</span><span class="sxs-lookup"><span data-stu-id="b4660-396">Jay Norman</span></span>          | <span data-ttu-id="b4660-397">0,00</span><span class="sxs-lookup"><span data-stu-id="b4660-397">0.00</span></span>              | <span data-ttu-id="b4660-398">6/15/2018</span><span class="sxs-lookup"><span data-stu-id="b4660-398">6/15/2018</span></span>       | <span data-ttu-id="b4660-399">6/15/2018</span><span class="sxs-lookup"><span data-stu-id="b4660-399">6/15/2018</span></span>  | <span data-ttu-id="b4660-400">1,00</span><span class="sxs-lookup"><span data-stu-id="b4660-400">1.00</span></span>           | <span data-ttu-id="b4660-401">9/1/2018</span><span class="sxs-lookup"><span data-stu-id="b4660-401">9/1/2018</span></span>        | <span data-ttu-id="b4660-402">3,00</span><span class="sxs-lookup"><span data-stu-id="b4660-402">3.00</span></span>    |

#### <a name="no-accrual-monthly-plan"></a><span data-ttu-id="b4660-403">Ingen månatlig plan för periodisering</span><span class="sxs-lookup"><span data-stu-id="b4660-403">No accrual monthly plan</span></span>

<span data-ttu-id="b4660-404">**Planinställningar**</span><span class="sxs-lookup"><span data-stu-id="b4660-404">**Plan setup**</span></span>

| <span data-ttu-id="b4660-405">Startdatum för planen</span><span class="sxs-lookup"><span data-stu-id="b4660-405">Plan start date</span></span> | <span data-ttu-id="b4660-406">Periodiseringsfrekvens</span><span class="sxs-lookup"><span data-stu-id="b4660-406">Accrual frequency</span></span> | <span data-ttu-id="b4660-407">Periodiseringsperiodbas</span><span class="sxs-lookup"><span data-stu-id="b4660-407">Accrual period basis</span></span> |
|-----------------|-------------------|----------------------|
| <span data-ttu-id="b4660-408">1/1/2018</span><span class="sxs-lookup"><span data-stu-id="b4660-408">1/1/2018</span></span>        | <span data-ttu-id="b4660-409">Månatlig</span><span class="sxs-lookup"><span data-stu-id="b4660-409">Monthly</span></span>           | <span data-ttu-id="b4660-410">Startdatum för planen</span><span class="sxs-lookup"><span data-stu-id="b4660-410">Plan start date</span></span>      |

<span data-ttu-id="b4660-411">**Resultat**</span><span class="sxs-lookup"><span data-stu-id="b4660-411">**Results**</span></span>

| <span data-ttu-id="b4660-412">Medarbetare</span><span class="sxs-lookup"><span data-stu-id="b4660-412">Employee</span></span>            | <span data-ttu-id="b4660-413">Tjänstgöringsmånader</span><span class="sxs-lookup"><span data-stu-id="b4660-413">Months of service</span></span> | <span data-ttu-id="b4660-414">Datum för anmälan</span><span class="sxs-lookup"><span data-stu-id="b4660-414">Enrollment date</span></span> | <span data-ttu-id="b4660-415">Startdatum</span><span class="sxs-lookup"><span data-stu-id="b4660-415">Start date</span></span> | <span data-ttu-id="b4660-416">Periodiseringstid</span><span class="sxs-lookup"><span data-stu-id="b4660-416">Accrual amount</span></span> | <span data-ttu-id="b4660-417">Bearbeta periodisering</span><span class="sxs-lookup"><span data-stu-id="b4660-417">Process accrual</span></span> | <span data-ttu-id="b4660-418">Balans</span><span class="sxs-lookup"><span data-stu-id="b4660-418">Balance</span></span> |
|---------------------|-------------------|-----------------|------------|----------------|-----------------|---------|
| <span data-ttu-id="b4660-419">Jeannette Nicholson</span><span class="sxs-lookup"><span data-stu-id="b4660-419">Jeannette Nicholson</span></span> | <span data-ttu-id="b4660-420">0,00</span><span class="sxs-lookup"><span data-stu-id="b4660-420">0.00</span></span>              | <span data-ttu-id="b4660-421">6/1/2018</span><span class="sxs-lookup"><span data-stu-id="b4660-421">6/1/2018</span></span>        | <span data-ttu-id="b4660-422">6/1/2018</span><span class="sxs-lookup"><span data-stu-id="b4660-422">6/1/2018</span></span>   | <span data-ttu-id="b4660-423">1,00</span><span class="sxs-lookup"><span data-stu-id="b4660-423">1.00</span></span>           | <span data-ttu-id="b4660-424">9/1/2018</span><span class="sxs-lookup"><span data-stu-id="b4660-424">9/1/2018</span></span>        | <span data-ttu-id="b4660-425">3,00</span><span class="sxs-lookup"><span data-stu-id="b4660-425">3.00</span></span>    |
| <span data-ttu-id="b4660-426">Jay Norman</span><span class="sxs-lookup"><span data-stu-id="b4660-426">Jay Norman</span></span>          | <span data-ttu-id="b4660-427">0,00</span><span class="sxs-lookup"><span data-stu-id="b4660-427">0.00</span></span>              | <span data-ttu-id="b4660-428">6/15/2018</span><span class="sxs-lookup"><span data-stu-id="b4660-428">6/15/2018</span></span>       | <span data-ttu-id="b4660-429">6/15/2018</span><span class="sxs-lookup"><span data-stu-id="b4660-429">6/15/2018</span></span>  | <span data-ttu-id="b4660-430">1,00</span><span class="sxs-lookup"><span data-stu-id="b4660-430">1.00</span></span>           | <span data-ttu-id="b4660-431">9/1/2018</span><span class="sxs-lookup"><span data-stu-id="b4660-431">9/1/2018</span></span>        | <span data-ttu-id="b4660-432">2.00</span><span class="sxs-lookup"><span data-stu-id="b4660-432">2.00</span></span>    |

