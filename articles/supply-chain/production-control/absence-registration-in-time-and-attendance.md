---
title: Frånvaroregistrering i Tid och närvaro
description: Det här avsnittet beskriver hur du hanterar frånvaroregistreringar i Tid och närvaro.
author: johanhoffmann
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JMGParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2017-09-20
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7ef244d5abf762bcaab426cf1cefb232383a8109
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "363049"
---
# <a name="absence-registration-in-time-and-attendance"></a><span data-ttu-id="bb637-103">Frånvaroregistrering i Tid och närvaro</span><span class="sxs-lookup"><span data-stu-id="bb637-103">Absence registration in Time and attendance</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="bb637-104">Det här avsnittet beskriver begreppen för frånvaro och hur du hanterar frånvaro i Tid och närvaro.</span><span class="sxs-lookup"><span data-stu-id="bb637-104">This topic describes the concepts for absence and explains how to handle absence in Time and attendance.</span></span>

## <a name="absence-that-is-based-on-regular-work-hours"></a><span data-ttu-id="bb637-105">Frånvaro som baseras på vanliga arbetstider</span><span class="sxs-lookup"><span data-stu-id="bb637-105">Absence that is based on regular work hours</span></span>

<span data-ttu-id="bb637-106">Arbetare anses vara frånvarande för det antal timmar som de inte arbetar under deras vanliga arbetstider.</span><span class="sxs-lookup"><span data-stu-id="bb637-106">Workers are considered absent for any hours that they don't work during their regular work hours.</span></span> <span data-ttu-id="bb637-107">Vanliga arbetstimmar anges i profilen för en arbetares standardtid.</span><span class="sxs-lookup"><span data-stu-id="bb637-107">Regular work hours are defined in a worker's standard time profile.</span></span>

<span data-ttu-id="bb637-108">Exempelvis arbetar en arbetare med en dagprofil som stämplar in klockan 7:00 och stämplar ut kl 15:00.</span><span class="sxs-lookup"><span data-stu-id="bb637-108">For example, a worker is working on a day profile that has clock-in at 7:00 AM and clock-out at 3:00 PM.</span></span> <span data-ttu-id="bb637-109">Om arbetaren stämplar in klockan 9:00 anses han frånvarande från 7:00 till 9:00 den dagen.</span><span class="sxs-lookup"><span data-stu-id="bb637-109">If the worker clocks in at 9:00 AM, he is considered absent from 7:00 AM to 9:00 AM on that day.</span></span>

<span data-ttu-id="bb637-110">I det här fallet uppmanas arbetare att ange en orsak till frånvaron.</span><span class="sxs-lookup"><span data-stu-id="bb637-110">In this case, workers are prompted to enter a reason for their absence.</span></span> <span data-ttu-id="bb637-111">De kan ange en orsak genom att välja en frånvarokod.</span><span class="sxs-lookup"><span data-stu-id="bb637-111">They can specify a reason by selecting an absence code.</span></span>

## <a name="absence-codes"></a><span data-ttu-id="bb637-112">Frånvarokoder</span><span class="sxs-lookup"><span data-stu-id="bb637-112">Absence codes</span></span>

<span data-ttu-id="bb637-113">Frånvarokoder definierar olika typer av frånvaro.</span><span class="sxs-lookup"><span data-stu-id="bb637-113">Absence codes define the various types of absence.</span></span> <span data-ttu-id="bb637-114">Frånvarokoder definieras av företaget.</span><span class="sxs-lookup"><span data-stu-id="bb637-114">Absence codes are defined by the company.</span></span>

<span data-ttu-id="bb637-115">Olika regler kan tillämpas på frånvarokoder.</span><span class="sxs-lookup"><span data-stu-id="bb637-115">Various rules can be applied to absence codes.</span></span> <span data-ttu-id="bb637-116">Exempelvis kan en frånvarokod konfigureras att dra av eller bevilja lön.</span><span class="sxs-lookup"><span data-stu-id="bb637-116">For example, an absence code can be configured to deduct or grant pay.</span></span>

<span data-ttu-id="bb637-117">Ett företag definierar till exempel frånvarokoden **sen** som arbetare kan använda om de kommer in sent och inte har en bra orsak.</span><span class="sxs-lookup"><span data-stu-id="bb637-117">For example, a company defines a **Late** absence code that workers use if they come in late and don't have a good reason.</span></span> <span data-ttu-id="bb637-118">Företaget definierar också frånvarokoden **intern kurs** som arbetare använder för tid som de tillbringar med att delta i interna kurser.</span><span class="sxs-lookup"><span data-stu-id="bb637-118">The company also defines an **Internal course** absence code that workers use for time that they spend attending internal courses.</span></span> <span data-ttu-id="bb637-119">Dessa koder kan ställas in så att **sen** dras av från en arbetares lön men **intern kurs** inte dras av från en arbetares lön.</span><span class="sxs-lookup"><span data-stu-id="bb637-119">These absence codes can be set up so that **Late** deducts from a worker's pay but **Internal course** doesn't deduct from a worker's pay.</span></span>

<span data-ttu-id="bb637-120">Du kan ange automatiska orsakskoder.</span><span class="sxs-lookup"><span data-stu-id="bb637-120">You can set up automatic absence codes.</span></span> <span data-ttu-id="bb637-121">Dessa frånvarokoder kan användas för att beräkna en arbetare tid när ingen frånvaro har registrerats.</span><span class="sxs-lookup"><span data-stu-id="bb637-121">These absence codes can be used to calculate a worker's time when no absence is registered.</span></span> <span data-ttu-id="bb637-122">Arbetarens tidsprofil avgör om frånvarokoden för standardtid eller flextid används.</span><span class="sxs-lookup"><span data-stu-id="bb637-122">The worker's time profile determines whether the absence code for standard time or flex time is used.</span></span>

### <a name="set-up-standard-time-and-flex-time"></a><span data-ttu-id="bb637-123">Ställa in standardtid och flextid</span><span class="sxs-lookup"><span data-stu-id="bb637-123">Set up standard time and flex time</span></span>

- <span data-ttu-id="bb637-124">Konfigurera parametrar för standardtid och flextid med hjälp av alternativen **Infoga frånvaro automatiskt** och **Infoga flextid automatiskt** på sidan **parametrar för tid och närvaro**.</span><span class="sxs-lookup"><span data-stu-id="bb637-124">Configure the parameters for standard time and flex time by using the **Auto insert absence** and **Auto insert Flex-** options on the **Time and attendance parameters** page.</span></span>

## <a name="absence-groups"></a><span data-ttu-id="bb637-125">Frånvarogrupper</span><span class="sxs-lookup"><span data-stu-id="bb637-125">Absence groups</span></span>

<span data-ttu-id="bb637-126">Frånvarokoder grupperas i frånvarogrupper.</span><span class="sxs-lookup"><span data-stu-id="bb637-126">Absence codes are grouped into absence groups.</span></span> <span data-ttu-id="bb637-127">Du kan använda frånvarogrupper för att gruppera frånvarokoder som har gemensamma egenskaper.</span><span class="sxs-lookup"><span data-stu-id="bb637-127">You use absence groups to group absence codes that have common characteristics.</span></span> <span data-ttu-id="bb637-128">Exempel omfattar frånvarokoder för en giltig frånvaro, eller frånvaro på grund av en avtalad tid hos läkare, jurytjänst eller sjukt barn.</span><span class="sxs-lookup"><span data-stu-id="bb637-128">Examples include absence codes for a legal absence, or absence because of a doctor's appointment, jury duty, or a sick child.</span></span>

## <a name="planned-absence"></a><span data-ttu-id="bb637-129">Planerad frånvaro</span><span class="sxs-lookup"><span data-stu-id="bb637-129">Planned absence</span></span>

<span data-ttu-id="bb637-130">Om du vet att arbetaren kommer att vara frånvarande under en period, till exempel en kommande semester, kan du använda planerad frånvaro.</span><span class="sxs-lookup"><span data-stu-id="bb637-130">If you know that a worker will be absent for a period, such as an upcoming vacation, you can use planned absence.</span></span> <span data-ttu-id="bb637-131">Du kan ställa in planerad frånvarokod genom att konfigurera frånvarokoden så att den anser att den tar hänsyn tilll den planerade frånvaron.</span><span class="sxs-lookup"><span data-stu-id="bb637-131">You set up planned absence by configuring the absence code so that it considers the planned absence.</span></span> <span data-ttu-id="bb637-132">När du ställer in en planerad frånvaro blir du inte tillfrågad om en frånvarokod under frånvaroperioden när användarens tidsregistreringar beräknas.</span><span class="sxs-lookup"><span data-stu-id="bb637-132">When you set up a planned absence, you aren't prompted for an absence code during the absence period when user time registrations are calculated.</span></span> <span data-ttu-id="bb637-133">Planerad frånvaro kan definieras för en enskild arbetare eller så kan du definiera ett batchjobb för att massuppdatera planerad frånvaro för arbetare.</span><span class="sxs-lookup"><span data-stu-id="bb637-133">Planned absence can be defined for a single worker, or you can define a batch job to bulk update the planned absence for workers.</span></span>

### <a name="set-up-planned-absence"></a><span data-ttu-id="bb637-134">Ställ in planerad frånvaro</span><span class="sxs-lookup"><span data-stu-id="bb637-134">Set up planned absence</span></span>

1. <span data-ttu-id="bb637-135">Välj **personal**&gt;**arbetare**&gt;**medarbetare** och välj en medarbetare.</span><span class="sxs-lookup"><span data-stu-id="bb637-135">Select **Human resources** &gt; **Workers** &gt; **Employees**, and select an employee.</span></span>
2. <span data-ttu-id="bb637-136">Välj **tid**&gt;**tidstilldelningar**&gt;**tidsfrånvaroregistrering** och ställ in den planerade frånvaron.</span><span class="sxs-lookup"><span data-stu-id="bb637-136">Select **Time** &gt; **Time assignments** &gt; **Time Absence registration**, and set up the planned absence.</span></span>

## <a name="interrupted-planned-absence"></a><span data-ttu-id="bb637-137">Avbruten planerad frånvaro</span><span class="sxs-lookup"><span data-stu-id="bb637-137">Interrupted planned absence</span></span>

<span data-ttu-id="bb637-138">Om du använder alternativet **avbryta** när du ställer in en planerad frånvaro, kommer den planerade frånvaron att avbrytas om arbetaren loggar in under den planerade frånvaroperioden.</span><span class="sxs-lookup"><span data-stu-id="bb637-138">If you apply the **Interrupt** option when you set up a planned absence, the planned absence will be interrupted if the worker signs in during the planned absence period.</span></span> <span data-ttu-id="bb637-139">Den planerade frånvaron markeras som **avbruten** och har någon inverkan på framtida beräkningar.</span><span class="sxs-lookup"><span data-stu-id="bb637-139">The planned absence will be marked as **Interrupted** and won't have any effect on future calculations.</span></span>

### <a name="set-up-a-planned-absence-for-interruption"></a><span data-ttu-id="bb637-140">Skapa en planerad frånvaro för avbrott</span><span class="sxs-lookup"><span data-stu-id="bb637-140">Set up a planned absence for interruption</span></span>

1. <span data-ttu-id="bb637-141">Öppna sidan **tidsfrånvaroregistrering** enligt proceduren för att skapa planerad frånvaro.</span><span class="sxs-lookup"><span data-stu-id="bb637-141">Open the **Time Absence registration** page as described in the procedure for setting up planned absence.</span></span>
2. <span data-ttu-id="bb637-142">Välj **avbryta**.</span><span class="sxs-lookup"><span data-stu-id="bb637-142">Select **Interrupt**.</span></span>

<span data-ttu-id="bb637-143">Alternativet **avbryta** används när tiden registreras via terminalen Arbetsstyrning eller enheten Arbetsstyrning.</span><span class="sxs-lookup"><span data-stu-id="bb637-143">The **Interrupt** option applies when time is registered through the shop floor terminal or the shop floor device.</span></span> <span data-ttu-id="bb637-144">Alternativet kan inte användas om registreringarna anges på sidorna för beräkning och godkännande eller på sidan **elektroniskt tidkort**.</span><span class="sxs-lookup"><span data-stu-id="bb637-144">The option doesn't apply if the registrations are entered on the calculation and approval pages, or on the **Electronic timecard** page.</span></span>

## <a name="examples-of-the-use-of-absence-in-a-flex-profile"></a><span data-ttu-id="bb637-145">Exempel på användning av frånvaro i en flexprofil</span><span class="sxs-lookup"><span data-stu-id="bb637-145">Examples of the use of absence in a flex profile</span></span>

<span data-ttu-id="bb637-146">Följande tre exempel visar hur frånvaro beräknas i en profil med flextidperioder.</span><span class="sxs-lookup"><span data-stu-id="bb637-146">The following three examples show how absence is calculated in a profile that has flex periods.</span></span>

<span data-ttu-id="bb637-147">Exemplen använder följande profiler.</span><span class="sxs-lookup"><span data-stu-id="bb637-147">The examples use the following profile.</span></span>

| <span data-ttu-id="bb637-148">Instämpling</span><span class="sxs-lookup"><span data-stu-id="bb637-148">Clock-in</span></span> | <span data-ttu-id="bb637-149">Standardtid</span><span class="sxs-lookup"><span data-stu-id="bb637-149">Standard time</span></span>    | <span data-ttu-id="bb637-150">Rast</span><span class="sxs-lookup"><span data-stu-id="bb637-150">Break</span></span>             | <span data-ttu-id="bb637-151">Standardtid</span><span class="sxs-lookup"><span data-stu-id="bb637-151">Standard time</span></span> | <span data-ttu-id="bb637-152">Flex-</span><span class="sxs-lookup"><span data-stu-id="bb637-152">Flex-</span></span>        | <span data-ttu-id="bb637-153">Utstämpling</span><span class="sxs-lookup"><span data-stu-id="bb637-153">Clock-out</span></span> | <span data-ttu-id="bb637-154">Flex+</span><span class="sxs-lookup"><span data-stu-id="bb637-154">Flex+</span></span>        |
|----------|------------------|-------------------|---------------|--------------|-----------|--------------|
| <span data-ttu-id="bb637-155">08:00</span><span class="sxs-lookup"><span data-stu-id="bb637-155">8 AM</span></span>     | <span data-ttu-id="bb637-156">09:00 till 11:30</span><span class="sxs-lookup"><span data-stu-id="bb637-156">9 AM to 11:30 AM</span></span> | <span data-ttu-id="bb637-157">11:30 till 12:00</span><span class="sxs-lookup"><span data-stu-id="bb637-157">11:30 AM to 12 PM</span></span> | <span data-ttu-id="bb637-158">12:00 till 15:00</span><span class="sxs-lookup"><span data-stu-id="bb637-158">12 PM to 3 PM</span></span> | <span data-ttu-id="bb637-159">15:00 till 16:00</span><span class="sxs-lookup"><span data-stu-id="bb637-159">3 PM to 4 PM</span></span> | <span data-ttu-id="bb637-160">16:00</span><span class="sxs-lookup"><span data-stu-id="bb637-160">4 PM</span></span>      | <span data-ttu-id="bb637-161">16:00 till 18:00</span><span class="sxs-lookup"><span data-stu-id="bb637-161">4 PM to 6 PM</span></span> |

### <a name="example-1-signing-out-during-a-flex--period"></a><span data-ttu-id="bb637-162">Exempel 1: Loggar ut under en flex- period</span><span class="sxs-lookup"><span data-stu-id="bb637-162">Example 1: Signing out during a Flex- period</span></span>

<span data-ttu-id="bb637-163">Arbetaren stämplar in klockan 8:00 och stämplar ut 15:30.</span><span class="sxs-lookup"><span data-stu-id="bb637-163">The worker clocks in at 8:00 AM and clocks out at 3:30 PM.</span></span> <span data-ttu-id="bb637-164">I detta fall, eftersom arbetaren stämplar ut under en flex- period, beräknas ingen frånvaro och en halvtimme dras av från arbetarens flexsaldo.</span><span class="sxs-lookup"><span data-stu-id="bb637-164">In this case, because the worker clocks out during a Flex- period, no absence is calculated, and half an hour is deducted from the worker's flex balance.</span></span>

### <a name="example-2-signing-out-in-during-standard-time-period"></a><span data-ttu-id="bb637-165">Exempel 2: Loggar ut under standardtiden</span><span class="sxs-lookup"><span data-stu-id="bb637-165">Example 2: Signing out in during Standard time period</span></span>

<span data-ttu-id="bb637-166">Arbetaren stämplar in klockan 8:00 och stämplar ut 14:30.</span><span class="sxs-lookup"><span data-stu-id="bb637-166">The worker clocks in at 8:00 AM and clocks out at 2:30 PM.</span></span> <span data-ttu-id="bb637-167">I detta fall, eftersom medarbetaren stämplar ut under standardtidsperioden, beräknas frånvaro från 14:30 till 16:00 och en frånvaroperiod på 1,5 timmar registreras.</span><span class="sxs-lookup"><span data-stu-id="bb637-167">In this case, because the worker clocks out during the Standard time period, absence is calculated from 2:30 PM to 4 PM, and an absence period of 1.5 hours is registered.</span></span> <span data-ttu-id="bb637-168">Det krävs en frånvarokod för den perioden.</span><span class="sxs-lookup"><span data-stu-id="bb637-168">An absence code for that period is required.</span></span>

### <a name="example-3-signing-out-during-a-flex-period"></a><span data-ttu-id="bb637-169">Exempel 3: Loggar ut under en flex+ period</span><span class="sxs-lookup"><span data-stu-id="bb637-169">Example 3: Signing out during a Flex+ period</span></span>

<span data-ttu-id="bb637-170">Arbetaren stämplar in klockan 8:00 och stämplar ut 16:30.</span><span class="sxs-lookup"><span data-stu-id="bb637-170">The worker clocks in at 8:00 AM and clocks out at 4:30 PM.</span></span> <span data-ttu-id="bb637-171">I detta fall, eftersom arbetaren stämplar ut under en flex+ period, beräknas ingen frånvaro och en halvtimme läggs till arbetarens flexsaldo.</span><span class="sxs-lookup"><span data-stu-id="bb637-171">In this case, because the worker clocks out during a Flex+ period, no absence is calculated, and half an hour is added to the worker's flex balance.</span></span>

## <a name="absence-in-the-calculation-and-approval-process"></a><span data-ttu-id="bb637-172">Frånvaro i beräknings- och godkännandeprocessen</span><span class="sxs-lookup"><span data-stu-id="bb637-172">Absence in the calculation and approval process</span></span>

<span data-ttu-id="bb637-173">Tidsregistreringar för arbetare måste beräknas och godkännas innan de kan överföras till ett lönesystem som löneposter.</span><span class="sxs-lookup"><span data-stu-id="bb637-173">Worker time registrations must be calculated and approved before they can be transferred to a payroll system as pay items.</span></span>

<span data-ttu-id="bb637-174">En godkännare kan ändra tidsregistreringar för en arbetare.</span><span class="sxs-lookup"><span data-stu-id="bb637-174">An approver can change a worker's time registrations.</span></span> <span data-ttu-id="bb637-175">Godkännaren kan även ändra eventuell frånvaro som arbetaren har registrerat.</span><span class="sxs-lookup"><span data-stu-id="bb637-175">The approver can even change any absence that the worker has registered.</span></span> <span data-ttu-id="bb637-176">Om godkännaren manuellt anger en tidsperiod som har en frånvarokod, åsidosätts frånvarokoden för den perioden inte av standardfrånvarokoden från parametrarna Tid och närvaro.</span><span class="sxs-lookup"><span data-stu-id="bb637-176">If the approver manually enters a time period that has an absence code, the absence code for that period isn't overridden by the default absence code from the Time and attendance parameters.</span></span>

<span data-ttu-id="bb637-177">En arbetare stämplar t.ex. in klockan 10:00 och väljer en frånvarokod som indikerar att hon är sen.</span><span class="sxs-lookup"><span data-stu-id="bb637-177">For example, a worker clocks in at 10 AM and selects an absence code that indicates that she is late.</span></span> <span data-ttu-id="bb637-178">Arbetaren informerar senare sin arbetsledare att hon hade ett läkarbesök mellan 08:00 till 10:00.</span><span class="sxs-lookup"><span data-stu-id="bb637-178">Later, the worker informs her supervisor that she had a doctor's appointment from 8 AM to 10 AM.</span></span> <span data-ttu-id="bb637-179">Ett läkarbesök bör inte medföra avdrag på arbetarens lön.</span><span class="sxs-lookup"><span data-stu-id="bb637-179">A doctor's appointment should not cause a deduction in the worker's pay.</span></span> <span data-ttu-id="bb637-180">Därför kan i detta fall chefen justera två timmar av frånvaro mellan 08:00 till 10:00 manuellt genom att ange en frånvarokod som anger sjukdom under de två timmar.</span><span class="sxs-lookup"><span data-stu-id="bb637-180">Therefore, in this case, the supervisor can adjust the two hours of absence from 8 AM to 10 AM by manually entering an absence code that indicates illness for those two hours.</span></span>

### <a name="calculate-and-approve-absence"></a><span data-ttu-id="bb637-181">Beräkna och godkänn frånvaro</span><span class="sxs-lookup"><span data-stu-id="bb637-181">Calculate and approve absence</span></span>

- <span data-ttu-id="bb637-182">Välj **Tid och närvaro**&gt;**Granska och godkänn**&gt;**Godkänn eller beräkna**.</span><span class="sxs-lookup"><span data-stu-id="bb637-182">Select **Time attendance** &gt; **Review and approve** &gt; **Approve or Calculate**.</span></span>
