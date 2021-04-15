---
title: Dataverse-register
description: Microsoft Dynamics 365 Human Resources använder Dataverse för att aktivera scenarier för utökning och integration.
author: andreabichsel
ms.date: 01/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e316cda9b9c5361c0a2837e7ed6c050e76cc39b9
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5793619"
---
# <a name="dataverse-tables"></a><span data-ttu-id="9b1bd-103">Dataverse-register</span><span class="sxs-lookup"><span data-stu-id="9b1bd-103">Dataverse tables</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="9b1bd-104">Microsoft Dynamics 365 Human Resources använder Dataverse för att aktivera scenarier för utökning och integration.</span><span class="sxs-lookup"><span data-stu-id="9b1bd-104">Microsoft Dynamics 365 Human Resources uses Dataverse to enable extensibility and integration scenarios.</span></span>

> [!NOTE]
> <span data-ttu-id="9b1bd-105">Personal-entiteter motsvarar Dataverse-register.</span><span class="sxs-lookup"><span data-stu-id="9b1bd-105">Human Resources entities correspond to Dataverse tables.</span></span> <span data-ttu-id="9b1bd-106">Mer information om Dataverse (tidigare Common Data Service) och terminologiuppdateringar finns i [Vad är Microsoft Dataverse?](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro)</span><span class="sxs-lookup"><span data-stu-id="9b1bd-106">For more information about Dataverse (formerly Common Data Service) and terminology updates, see [What is Microsoft Dataverse?](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro)</span></span>

<span data-ttu-id="9b1bd-107">Följande Dataverse-register baseras på Personal-entiteter.</span><span class="sxs-lookup"><span data-stu-id="9b1bd-107">The following Dataverse tables are available based on Human Resources entities.</span></span>

## <a name="benefit-tables"></a><span data-ttu-id="9b1bd-108">Förmånsregister</span><span class="sxs-lookup"><span data-stu-id="9b1bd-108">Benefit tables</span></span>

| <span data-ttu-id="9b1bd-109">Namn</span><span class="sxs-lookup"><span data-stu-id="9b1bd-109">Name</span></span> | <span data-ttu-id="9b1bd-110">Register</span><span class="sxs-lookup"><span data-stu-id="9b1bd-110">Table</span></span> |
| --- | --- |
| <span data-ttu-id="9b1bd-111">Frekvens i förmånsberäkning</span><span class="sxs-lookup"><span data-stu-id="9b1bd-111">Benefit Calculation Frequency</span></span> | <span data-ttu-id="9b1bd-112">cdm_benefitcalculationfrequency</span><span class="sxs-lookup"><span data-stu-id="9b1bd-112">cdm_benefitcalculationfrequency</span></span> |
| <span data-ttu-id="9b1bd-113">Löneperiod med frekvens i förmånsberäkning</span><span class="sxs-lookup"><span data-stu-id="9b1bd-113">Benefit Calculation Frequency Pay Period</span></span> | <span data-ttu-id="9b1bd-114">cdm_benefitcalculationfrequencypayperiod</span><span class="sxs-lookup"><span data-stu-id="9b1bd-114">cdm_benefitcalculationfrequencypayperiod</span></span> |
| <span data-ttu-id="9b1bd-115">Tariff för förmånsberäkning</span><span class="sxs-lookup"><span data-stu-id="9b1bd-115">Benefit Calculation Rate</span></span> | <span data-ttu-id="9b1bd-116">cdm_benefitcalculationrate</span><span class="sxs-lookup"><span data-stu-id="9b1bd-116">cdm_benefitcalculationrate</span></span> |
| <span data-ttu-id="9b1bd-117">Uppgift om tariff för förmånsberäkning</span><span class="sxs-lookup"><span data-stu-id="9b1bd-117">Benefit Calculation Rate Detail</span></span> | <span data-ttu-id="9b1bd-118">cdm_benefitcalculationratedetail</span><span class="sxs-lookup"><span data-stu-id="9b1bd-118">cdm_benefitcalculationratedetail</span></span> |
| <span data-ttu-id="9b1bd-119">Förmånsalternativ</span><span class="sxs-lookup"><span data-stu-id="9b1bd-119">Benefit Option</span></span> | <span data-ttu-id="9b1bd-120">cdm_benefitoption</span><span class="sxs-lookup"><span data-stu-id="9b1bd-120">cdm_benefitoption</span></span> |
| <span data-ttu-id="9b1bd-121">Förmånsplan</span><span class="sxs-lookup"><span data-stu-id="9b1bd-121">Benefit Plan</span></span> | <span data-ttu-id="9b1bd-122">cdm_benefitplan (inte aktiverat för stöd för anpassade fält)</span><span class="sxs-lookup"><span data-stu-id="9b1bd-122">cdm_benefitplan (Not enabled for custom field support)</span></span> |
| <span data-ttu-id="9b1bd-123">Förmånstyp</span><span class="sxs-lookup"><span data-stu-id="9b1bd-123">Benefit Type</span></span> | <span data-ttu-id="9b1bd-124">cdm_benefittype</span><span class="sxs-lookup"><span data-stu-id="9b1bd-124">cdm_benefittype</span></span> |

## <a name="business-process-tasks-tables"></a><span data-ttu-id="9b1bd-125">Uppgiftsentiteter för affärsprocesser</span><span class="sxs-lookup"><span data-stu-id="9b1bd-125">Business process tasks tables</span></span>

| <span data-ttu-id="9b1bd-126">Namn</span><span class="sxs-lookup"><span data-stu-id="9b1bd-126">Name</span></span> | <span data-ttu-id="9b1bd-127">Register</span><span class="sxs-lookup"><span data-stu-id="9b1bd-127">Table</span></span> |
| --- | --- |
| <span data-ttu-id="9b1bd-128">Affärsprocesskalender</span><span class="sxs-lookup"><span data-stu-id="9b1bd-128">Business Process Calendar</span></span> | <span data-ttu-id="9b1bd-129">cdm_businessprocesscalendar</span><span class="sxs-lookup"><span data-stu-id="9b1bd-129">cdm_businessprocesscalendar</span></span> |
| <span data-ttu-id="9b1bd-130">Tilldelning av affärsprocessgrupp</span><span class="sxs-lookup"><span data-stu-id="9b1bd-130">Business Process Group Assignment</span></span> | <span data-ttu-id="9b1bd-131">cdm_businessprocessgroupassignment</span><span class="sxs-lookup"><span data-stu-id="9b1bd-131">cdm_businessprocessgroupassignment</span></span> |
| <span data-ttu-id="9b1bd-132">Affärsprocessbibliotekets uppgiftsgrupp</span><span class="sxs-lookup"><span data-stu-id="9b1bd-132">Business Process Library Task Group</span></span> | <span data-ttu-id="9b1bd-133">cdm_businessprocesslibrarytaskgroup</span><span class="sxs-lookup"><span data-stu-id="9b1bd-133">cdm_businessprocesslibrarytaskgroup</span></span> |
| <span data-ttu-id="9b1bd-134">Affärsprocessfas</span><span class="sxs-lookup"><span data-stu-id="9b1bd-134">Business Process Stage</span></span> | <span data-ttu-id="9b1bd-135">cdm_businessprocessstage</span><span class="sxs-lookup"><span data-stu-id="9b1bd-135">cdm_businessprocessstage</span></span> |
| <span data-ttu-id="9b1bd-136">Checklistemallens rubrik</span><span class="sxs-lookup"><span data-stu-id="9b1bd-136">Checklist Template Header</span></span> | <span data-ttu-id="9b1bd-137">cdm_businessprocesstemplateheader</span><span class="sxs-lookup"><span data-stu-id="9b1bd-137">cdm_businessprocesstemplateheader</span></span> |
| <span data-ttu-id="9b1bd-138">Checklistemallens uppgift</span><span class="sxs-lookup"><span data-stu-id="9b1bd-138">Checklist Template Task</span></span> | <span data-ttu-id="9b1bd-139">cdm_businessprocesstemplatetask</span><span class="sxs-lookup"><span data-stu-id="9b1bd-139">cdm_businessprocesstemplatetask</span></span> |

## <a name="compensation-tables"></a><span data-ttu-id="9b1bd-140">Kompensationsregister</span><span class="sxs-lookup"><span data-stu-id="9b1bd-140">Compensation tables</span></span>

| <span data-ttu-id="9b1bd-141">Namn</span><span class="sxs-lookup"><span data-stu-id="9b1bd-141">Name</span></span> | <span data-ttu-id="9b1bd-142">Register</span><span class="sxs-lookup"><span data-stu-id="9b1bd-142">Table</span></span> |
| --- | --- |
| <span data-ttu-id="9b1bd-143">Fast kompensationsplan</span><span class="sxs-lookup"><span data-stu-id="9b1bd-143">Compensation Fixed Plan</span></span> | <span data-ttu-id="9b1bd-144">cdm_compensationfixedplan</span><span class="sxs-lookup"><span data-stu-id="9b1bd-144">cdm_compensationfixedplan</span></span> |
| <span data-ttu-id="9b1bd-145">Kompensationsrutnät</span><span class="sxs-lookup"><span data-stu-id="9b1bd-145">Compensation Grid</span></span> | <span data-ttu-id="9b1bd-146">cdm_compensationgrid</span><span class="sxs-lookup"><span data-stu-id="9b1bd-146">cdm_compensationgrid</span></span> |
| <span data-ttu-id="9b1bd-147">Kompensationsnivå</span><span class="sxs-lookup"><span data-stu-id="9b1bd-147">Compensation Level</span></span> | <span data-ttu-id="9b1bd-148">cdm_compensationlevel</span><span class="sxs-lookup"><span data-stu-id="9b1bd-148">cdm_compensationlevel</span></span> |
| <span data-ttu-id="9b1bd-149">Lönefrekvens för kompensation</span><span class="sxs-lookup"><span data-stu-id="9b1bd-149">Compensation Pay Frequency</span></span> | <span data-ttu-id="9b1bd-150">cdm_compensationpayfrequency</span><span class="sxs-lookup"><span data-stu-id="9b1bd-150">cdm_compensationpayfrequency</span></span> |
| <span data-ttu-id="9b1bd-151">Kompensationsreferenspunkt</span><span class="sxs-lookup"><span data-stu-id="9b1bd-151">Compensation Reference Point Setup</span></span> | <span data-ttu-id="9b1bd-152">cdm_compensationreferencepointsetup</span><span class="sxs-lookup"><span data-stu-id="9b1bd-152">cdm_compensationreferencepointsetup</span></span> |
| <span data-ttu-id="9b1bd-153">Ställ in kompensationsreferenspunkt</span><span class="sxs-lookup"><span data-stu-id="9b1bd-153">Compensation Reference Point Setup Line</span></span> | <span data-ttu-id="9b1bd-154">cdm_compensationreferencepointsetupline</span><span class="sxs-lookup"><span data-stu-id="9b1bd-154">cdm_compensationreferencepointsetupline</span></span> |
| <span data-ttu-id="9b1bd-155">Kompensationsregion</span><span class="sxs-lookup"><span data-stu-id="9b1bd-155">Compensation Region</span></span> | <span data-ttu-id="9b1bd-156">cdm_compensationregion</span><span class="sxs-lookup"><span data-stu-id="9b1bd-156">cdm_compensationregion</span></span> |
| <span data-ttu-id="9b1bd-157">Kompensationsstruktur</span><span class="sxs-lookup"><span data-stu-id="9b1bd-157">Compensation Structure</span></span> | <span data-ttu-id="9b1bd-158">cdm_compensationstructure</span><span class="sxs-lookup"><span data-stu-id="9b1bd-158">cdm_compensationstructure</span></span> |
| <span data-ttu-id="9b1bd-159">Variabel kompensationsplan</span><span class="sxs-lookup"><span data-stu-id="9b1bd-159">Compensation Variable Plan</span></span> | <span data-ttu-id="9b1bd-160">cdm_compensationvariableplan</span><span class="sxs-lookup"><span data-stu-id="9b1bd-160">cdm_compensationvariableplan</span></span> |
| <span data-ttu-id="9b1bd-161">Variabel kompensationsplannivå</span><span class="sxs-lookup"><span data-stu-id="9b1bd-161">Compensation Variable Plan Level</span></span> | <span data-ttu-id="9b1bd-162">cdm_compensationvariableplanlevel</span><span class="sxs-lookup"><span data-stu-id="9b1bd-162">cdm_compensationvariableplanlevel</span></span> |
| <span data-ttu-id="9b1bd-163">Typ av variabel kompensationsplan</span><span class="sxs-lookup"><span data-stu-id="9b1bd-163">Compensation Variable Plan Type</span></span> | <span data-ttu-id="9b1bd-164">cdm_compensationvariableplantype</span><span class="sxs-lookup"><span data-stu-id="9b1bd-164">cdm_compensationvariableplantype</span></span> |
| <span data-ttu-id="9b1bd-165">Händelse för fast kompensation</span><span class="sxs-lookup"><span data-stu-id="9b1bd-165">Fixed Compensation Event</span></span> | <span data-ttu-id="9b1bd-166">cdm_fixedcompensationevent</span><span class="sxs-lookup"><span data-stu-id="9b1bd-166">cdm_fixedcompensationevent</span></span> |
| <span data-ttu-id="9b1bd-167">Överlåtelseregel</span><span class="sxs-lookup"><span data-stu-id="9b1bd-167">Vesting Rule</span></span> | <span data-ttu-id="9b1bd-168">cdm_vestingrule</span><span class="sxs-lookup"><span data-stu-id="9b1bd-168">cdm_vestingrule</span></span> |
| <span data-ttu-id="9b1bd-169">Arbetarens fasta kompensation</span><span class="sxs-lookup"><span data-stu-id="9b1bd-169">Worker Fixed Compensation</span></span> | <span data-ttu-id="9b1bd-170">cdm_workerfixedcompensation</span><span class="sxs-lookup"><span data-stu-id="9b1bd-170">cdm_workerfixedcompensation</span></span> |

## <a name="organization-tables"></a><span data-ttu-id="9b1bd-171">Organisationsregister</span><span class="sxs-lookup"><span data-stu-id="9b1bd-171">Organization tables</span></span>

| <span data-ttu-id="9b1bd-172">Namn</span><span class="sxs-lookup"><span data-stu-id="9b1bd-172">Name</span></span> | <span data-ttu-id="9b1bd-173">Register</span><span class="sxs-lookup"><span data-stu-id="9b1bd-173">Table</span></span> |
| --- | --- |
| <span data-ttu-id="9b1bd-174">Avdelning</span><span class="sxs-lookup"><span data-stu-id="9b1bd-174">Department</span></span> | <span data-ttu-id="9b1bd-175">cdm_department</span><span class="sxs-lookup"><span data-stu-id="9b1bd-175">cdm_department</span></span> |
| <span data-ttu-id="9b1bd-176">Anställning</span><span class="sxs-lookup"><span data-stu-id="9b1bd-176">Employment</span></span> | <span data-ttu-id="9b1bd-177">cdm_employment</span><span class="sxs-lookup"><span data-stu-id="9b1bd-177">cdm_employment</span></span> |
| <span data-ttu-id="9b1bd-178">Företag</span><span class="sxs-lookup"><span data-stu-id="9b1bd-178">Company</span></span> | <span data-ttu-id="9b1bd-179">cdm_company</span><span class="sxs-lookup"><span data-stu-id="9b1bd-179">cdm_company</span></span> |
| <span data-ttu-id="9b1bd-180">Befattning</span><span class="sxs-lookup"><span data-stu-id="9b1bd-180">Job</span></span> | <span data-ttu-id="9b1bd-181">cdm_job</span><span class="sxs-lookup"><span data-stu-id="9b1bd-181">cdm_job</span></span> |
| <span data-ttu-id="9b1bd-182">Jobbfunktion</span><span class="sxs-lookup"><span data-stu-id="9b1bd-182">Job Function</span></span> | <span data-ttu-id="9b1bd-183">cdm_jobfunction</span><span class="sxs-lookup"><span data-stu-id="9b1bd-183">cdm_jobfunction</span></span> |
| <span data-ttu-id="9b1bd-184">Befattning</span><span class="sxs-lookup"><span data-stu-id="9b1bd-184">Job Position</span></span> | <span data-ttu-id="9b1bd-185">cdm_jobposition</span><span class="sxs-lookup"><span data-stu-id="9b1bd-185">cdm_jobposition</span></span> |
| <span data-ttu-id="9b1bd-186">Befattningstyp</span><span class="sxs-lookup"><span data-stu-id="9b1bd-186">Position Type</span></span> | <span data-ttu-id="9b1bd-187">cdm_positiontype</span><span class="sxs-lookup"><span data-stu-id="9b1bd-187">cdm_positiontype</span></span> |
| <span data-ttu-id="9b1bd-188">Befattningstilldelning för arbetare</span><span class="sxs-lookup"><span data-stu-id="9b1bd-188">Position Worker Assignment</span></span> | <span data-ttu-id="9b1bd-189">cdm_positionworkerassignmentmap</span><span class="sxs-lookup"><span data-stu-id="9b1bd-189">cdm_positionworkerassignmentmap</span></span> |
| <span data-ttu-id="9b1bd-190">Befattningsdimension</span><span class="sxs-lookup"><span data-stu-id="9b1bd-190">Job Position Dimension</span></span> | <span data-ttu-id="9b1bd-191">cdm_jobpositiondimension</span><span class="sxs-lookup"><span data-stu-id="9b1bd-191">cdm_jobpositiondimension</span></span>|
| <span data-ttu-id="9b1bd-192">Jobbtyp</span><span class="sxs-lookup"><span data-stu-id="9b1bd-192">Job Type</span></span> | <span data-ttu-id="9b1bd-193">cdm_jobtype</span><span class="sxs-lookup"><span data-stu-id="9b1bd-193">cdm_jobtype</span></span> |
| <span data-ttu-id="9b1bd-194">Språk</span><span class="sxs-lookup"><span data-stu-id="9b1bd-194">Language</span></span> | <span data-ttu-id="9b1bd-195">cdm_language</span><span class="sxs-lookup"><span data-stu-id="9b1bd-195">cdm_language</span></span> |
| <span data-ttu-id="9b1bd-196">Namn</span><span class="sxs-lookup"><span data-stu-id="9b1bd-196">Title</span></span> | <span data-ttu-id="9b1bd-197">cdm_title</span><span class="sxs-lookup"><span data-stu-id="9b1bd-197">cdm_title</span></span> |

> [!NOTE]
> <span data-ttu-id="9b1bd-198">Ekonomiska dimensioner för **Befattningstyp**, **Befattningstilldelning för arbetare** och **Anställning** ger integration med Dataverse i en riktning.</span><span class="sxs-lookup"><span data-stu-id="9b1bd-198">Financial dimensions for **Position Type**, **Position Worker Assignment**, and **Employment** provide one-direction integration to Dataverse.</span></span> <span data-ttu-id="9b1bd-199">Uppdateringar av ekonomiska dimensioner kan för närvarande inte synkroniseras från Dataverse till personal.</span><span class="sxs-lookup"><span data-stu-id="9b1bd-199">Financial dimensions updates currently can't synchronize from Dataverse to Human Resources.</span></span> 

## <a name="leave-and-absence-tables"></a><span data-ttu-id="9b1bd-200">Tjänstledighets- och frånvaroregister</span><span class="sxs-lookup"><span data-stu-id="9b1bd-200">Leave and absence tables</span></span>

| <span data-ttu-id="9b1bd-201">Namn</span><span class="sxs-lookup"><span data-stu-id="9b1bd-201">Name</span></span> | <span data-ttu-id="9b1bd-202">Register</span><span class="sxs-lookup"><span data-stu-id="9b1bd-202">Table</span></span> |
| --- | --- |
| <span data-ttu-id="9b1bd-203">Transaktion för tjänstledighetsbank</span><span class="sxs-lookup"><span data-stu-id="9b1bd-203">Leave Bank Transaction</span></span> | <span data-ttu-id="9b1bd-204">cdm_leavebanktransaction</span><span class="sxs-lookup"><span data-stu-id="9b1bd-204">cdm_leavebanktransaction</span></span> |
| <span data-ttu-id="9b1bd-205">Anmälning om tjänstledighet</span><span class="sxs-lookup"><span data-stu-id="9b1bd-205">Leave Enrollment</span></span> | <span data-ttu-id="9b1bd-206">cdm_leaveenrollment</span><span class="sxs-lookup"><span data-stu-id="9b1bd-206">cdm_leaveenrollment</span></span> |
| <span data-ttu-id="9b1bd-207">Tjänstledighetsplan</span><span class="sxs-lookup"><span data-stu-id="9b1bd-207">Leave Plan</span></span> | <span data-ttu-id="9b1bd-208">cdm_leaveplan</span><span class="sxs-lookup"><span data-stu-id="9b1bd-208">cdm_leaveplan</span></span> |
| <span data-ttu-id="9b1bd-209">Begäran om tjänstledighet</span><span class="sxs-lookup"><span data-stu-id="9b1bd-209">Leave Request</span></span> | <span data-ttu-id="9b1bd-210">cdm_leaverequest</span><span class="sxs-lookup"><span data-stu-id="9b1bd-210">cdm_leaverequest</span></span> |
| <span data-ttu-id="9b1bd-211">Information om att lämna begäran</span><span class="sxs-lookup"><span data-stu-id="9b1bd-211">Leave Request Detail</span></span> | <span data-ttu-id="9b1bd-212">cdm_leaverequestdetail</span><span class="sxs-lookup"><span data-stu-id="9b1bd-212">cdm_leaverequestdetail</span></span> |
| <span data-ttu-id="9b1bd-213">Tjänstledighetstyp</span><span class="sxs-lookup"><span data-stu-id="9b1bd-213">Leave Type</span></span> | <span data-ttu-id="9b1bd-214">cdm_leavetype</span><span class="sxs-lookup"><span data-stu-id="9b1bd-214">cdm_leavetype</span></span> |
| <span data-ttu-id="9b1bd-215">Ledighetstypens orsakskod</span><span class="sxs-lookup"><span data-stu-id="9b1bd-215">Leave Type Reason Code</span></span> | <span data-ttu-id="9b1bd-216">cdm_leavetypereasoncode</span><span class="sxs-lookup"><span data-stu-id="9b1bd-216">cdm_leavetypereasoncode</span></span> |

## <a name="payroll-tables"></a><span data-ttu-id="9b1bd-217">Löneregister</span><span class="sxs-lookup"><span data-stu-id="9b1bd-217">Payroll tables</span></span>

| <span data-ttu-id="9b1bd-218">Namn</span><span class="sxs-lookup"><span data-stu-id="9b1bd-218">Name</span></span> | <span data-ttu-id="9b1bd-219">Register</span><span class="sxs-lookup"><span data-stu-id="9b1bd-219">Table</span></span> |
| --- | --- |
| <span data-ttu-id="9b1bd-220">Lönecykel</span><span class="sxs-lookup"><span data-stu-id="9b1bd-220">Pay Cycle</span></span> | <span data-ttu-id="9b1bd-221">cdm_paycycle</span><span class="sxs-lookup"><span data-stu-id="9b1bd-221">cdm_paycycle</span></span> |
| <span data-ttu-id="9b1bd-222">Löneperiod</span><span class="sxs-lookup"><span data-stu-id="9b1bd-222">Pay Period</span></span> | <span data-ttu-id="9b1bd-223">cdm_payperiod</span><span class="sxs-lookup"><span data-stu-id="9b1bd-223">cdm_payperiod</span></span> |
| <span data-ttu-id="9b1bd-224">Inkomstkod</span><span class="sxs-lookup"><span data-stu-id="9b1bd-224">Payroll Earning Code</span></span> | <span data-ttu-id="9b1bd-225">cdm_payrollearningcode</span><span class="sxs-lookup"><span data-stu-id="9b1bd-225">cdm_payrollearningcode</span></span> |
| <span data-ttu-id="9b1bd-226">Bankkontoutbetalningar</span><span class="sxs-lookup"><span data-stu-id="9b1bd-226">Bank Account Disbursement</span></span> | <span data-ttu-id="9b1bd-227">cdm_bankaccountdisbursement</span><span class="sxs-lookup"><span data-stu-id="9b1bd-227">cdm_bankaccountdisbursement</span></span> |
| <span data-ttu-id="9b1bd-228">Skatteregion</span><span class="sxs-lookup"><span data-stu-id="9b1bd-228">Tax Region</span></span> | <span data-ttu-id="9b1bd-229">cdm_taxregion</span><span class="sxs-lookup"><span data-stu-id="9b1bd-229">cdm_taxregion</span></span> |

## <a name="worker-tables"></a><span data-ttu-id="9b1bd-230">Medarbetarregister</span><span class="sxs-lookup"><span data-stu-id="9b1bd-230">Worker tables</span></span>

| <span data-ttu-id="9b1bd-231">Namn</span><span class="sxs-lookup"><span data-stu-id="9b1bd-231">Name</span></span> | <span data-ttu-id="9b1bd-232">Register</span><span class="sxs-lookup"><span data-stu-id="9b1bd-232">Table</span></span> |
| --- | --- |
| <span data-ttu-id="9b1bd-233">Arbetare</span><span class="sxs-lookup"><span data-stu-id="9b1bd-233">Worker</span></span> | <span data-ttu-id="9b1bd-234">cdm_worker</span><span class="sxs-lookup"><span data-stu-id="9b1bd-234">cdm_worker</span></span> |
| <span data-ttu-id="9b1bd-235">Adress för arbetare</span><span class="sxs-lookup"><span data-stu-id="9b1bd-235">Worker Address</span></span> | <span data-ttu-id="9b1bd-236">cdm_workeraddress</span><span class="sxs-lookup"><span data-stu-id="9b1bd-236">cdm_workeraddress</span></span> |
| <span data-ttu-id="9b1bd-237">Arbetarens personuppgift</span><span class="sxs-lookup"><span data-stu-id="9b1bd-237">Worker Personal Detail</span></span> | <span data-ttu-id="9b1bd-238">cdm_workerpersonaldetail</span><span class="sxs-lookup"><span data-stu-id="9b1bd-238">cdm_workerpersonaldetail</span></span> |
| <span data-ttu-id="9b1bd-239">Arbetsidentifieringsnummer</span><span class="sxs-lookup"><span data-stu-id="9b1bd-239">Worker Person Identification Number</span></span> | <span data-ttu-id="9b1bd-240">cdm_workerpersonidentificationnumber</span><span class="sxs-lookup"><span data-stu-id="9b1bd-240">cdm_workerpersonidentificationnumber</span></span> |
| <span data-ttu-id="9b1bd-241">Arbetsidentifieringstyp</span><span class="sxs-lookup"><span data-stu-id="9b1bd-241">Worker Person Identification Type</span></span> | <span data-ttu-id="9b1bd-242">cdm_workerpersonidentificationtype</span><span class="sxs-lookup"><span data-stu-id="9b1bd-242">cdm_workerpersonidentificationtype</span></span> |
| <span data-ttu-id="9b1bd-243">Arbetskalender</span><span class="sxs-lookup"><span data-stu-id="9b1bd-243">Work Calendar</span></span> | <span data-ttu-id="9b1bd-244">cdm_workcalendar</span><span class="sxs-lookup"><span data-stu-id="9b1bd-244">cdm_workcalendar</span></span> |
| <span data-ttu-id="9b1bd-245">Arbetsdagar i kalendern</span><span class="sxs-lookup"><span data-stu-id="9b1bd-245">Work Calendar Day</span></span> | <span data-ttu-id="9b1bd-246">cdm_workcalendarday</span><span class="sxs-lookup"><span data-stu-id="9b1bd-246">cdm_workcalendarday</span></span> |
| <span data-ttu-id="9b1bd-247">Helgdag i arbetskalender</span><span class="sxs-lookup"><span data-stu-id="9b1bd-247">Work Calendar Holiday</span></span> |<span data-ttu-id="9b1bd-248">cdm_workcalendarholiday</span><span class="sxs-lookup"><span data-stu-id="9b1bd-248">cdm_workcalendarholiday</span></span> |
| <span data-ttu-id="9b1bd-249">Arbetskalenderns datumrad</span><span class="sxs-lookup"><span data-stu-id="9b1bd-249">Work Calendar Holiday Line</span></span> | <span data-ttu-id="9b1bd-250">cdm_workcalendarholidayline</span><span class="sxs-lookup"><span data-stu-id="9b1bd-250">cdm_workcalendarholidayline</span></span> |
| <span data-ttu-id="9b1bd-251">Tidsintervall till arbetskalendern</span><span class="sxs-lookup"><span data-stu-id="9b1bd-251">Work Calendar Time Interval</span></span> | <span data-ttu-id="9b1bd-252">cdm_workcalendartimeinterval (inte aktiverat för stöd för anpassade fält)</span><span class="sxs-lookup"><span data-stu-id="9b1bd-252">cdm_workcalendartimeinterval (Not enabled for custom field support)</span></span> |
| <span data-ttu-id="9b1bd-253">Bankkonto för arbetare</span><span class="sxs-lookup"><span data-stu-id="9b1bd-253">Worker Bank Account</span></span> | <span data-ttu-id="9b1bd-254">cdm_workerbankaccount</span><span class="sxs-lookup"><span data-stu-id="9b1bd-254">cdm_workerbankaccount</span></span> |

## <a name="worker-setup-tables"></a><span data-ttu-id="9b1bd-255">Inställningsregister för medarbetare</span><span class="sxs-lookup"><span data-stu-id="9b1bd-255">Worker setup tables</span></span>

| <span data-ttu-id="9b1bd-256">Namn</span><span class="sxs-lookup"><span data-stu-id="9b1bd-256">Name</span></span> | <span data-ttu-id="9b1bd-257">Register</span><span class="sxs-lookup"><span data-stu-id="9b1bd-257">Table</span></span> |
| --- | --- |
| <span data-ttu-id="9b1bd-258">Veteranstatus</span><span class="sxs-lookup"><span data-stu-id="9b1bd-258">Veteran Status</span></span> | <span data-ttu-id="9b1bd-259">cdm_veteranstatus</span><span class="sxs-lookup"><span data-stu-id="9b1bd-259">cdm_veteranstatus</span></span> |
| <span data-ttu-id="9b1bd-260">Etniskt ursprung</span><span class="sxs-lookup"><span data-stu-id="9b1bd-260">Ethnic Origin</span></span> | <span data-ttu-id="9b1bd-261">cdm_ethnicorigin</span><span class="sxs-lookup"><span data-stu-id="9b1bd-261">cdm_ethnicorigin</span></span> |
| <span data-ttu-id="9b1bd-262">Orsakskod</span><span class="sxs-lookup"><span data-stu-id="9b1bd-262">Reason Code</span></span> | <span data-ttu-id="9b1bd-263">cdm_reasoncode</span><span class="sxs-lookup"><span data-stu-id="9b1bd-263">cdm_reasoncode</span></span> |
| <span data-ttu-id="9b1bd-264">Utfärdande organ för personidentifiering</span><span class="sxs-lookup"><span data-stu-id="9b1bd-264">Person Identification Issuing Agency</span></span> | <span data-ttu-id="9b1bd-265">cdm_personidentificationissuingagency</span><span class="sxs-lookup"><span data-stu-id="9b1bd-265">cdm_personidentificationissuingagency</span></span> |

## <a name="competency-tables"></a><span data-ttu-id="9b1bd-266">Kompetensregister</span><span class="sxs-lookup"><span data-stu-id="9b1bd-266">Competency tables</span></span>

| <span data-ttu-id="9b1bd-267">Namn</span><span class="sxs-lookup"><span data-stu-id="9b1bd-267">Name</span></span> | <span data-ttu-id="9b1bd-268">Register</span><span class="sxs-lookup"><span data-stu-id="9b1bd-268">Table</span></span> |
| --- | --- |
| <span data-ttu-id="9b1bd-269">Kompetenstyp</span><span class="sxs-lookup"><span data-stu-id="9b1bd-269">Skill Type</span></span> | <span data-ttu-id="9b1bd-270">cdm_skilltype</span><span class="sxs-lookup"><span data-stu-id="9b1bd-270">cdm_skilltype</span></span> |

## <a name="table-relationship-models"></a><span data-ttu-id="9b1bd-271">Relationsmodeller för register</span><span class="sxs-lookup"><span data-stu-id="9b1bd-271">Table relationship models</span></span>

### <a name="worker"></a><span data-ttu-id="9b1bd-272">Arbetare</span><span class="sxs-lookup"><span data-stu-id="9b1bd-272">Worker</span></span>

![Arbetare](./media/HCMCommon-worker-entity-diagram.png)

### <a name="job-and-job-position"></a><span data-ttu-id="9b1bd-274">Jobb och jobbefattning</span><span class="sxs-lookup"><span data-stu-id="9b1bd-274">Job and Job Position</span></span>

![Jobb och jobbefattning](./media/HCMCommon-job-and-job-position-entity-diagram.png)

### <a name="benefits"></a><span data-ttu-id="9b1bd-276">Fördelar</span><span class="sxs-lookup"><span data-stu-id="9b1bd-276">Benefits</span></span>

![Fördelar](./media/HCMCommon-benefits-entity-diagram.png)

### <a name="compensation"></a><span data-ttu-id="9b1bd-278">Kompensation</span><span class="sxs-lookup"><span data-stu-id="9b1bd-278">Compensation</span></span>

![Kompensation](./media/HCMCommon-compensation-entity-diagram.png)

### <a name="leave"></a><span data-ttu-id="9b1bd-280">Lämna</span><span class="sxs-lookup"><span data-stu-id="9b1bd-280">Leave</span></span>

![Lämna](./media/HCMCommon-leave-entity-diagram.png)

### <a name="work-calendar"></a><span data-ttu-id="9b1bd-282">Arbetskalender</span><span class="sxs-lookup"><span data-stu-id="9b1bd-282">Work Calendar</span></span>

![Arbetskalender](./media/HCMCommon-work-calendar-entity-diagram.png)

## <a name="see-also"></a><span data-ttu-id="9b1bd-284">Se även</span><span class="sxs-lookup"><span data-stu-id="9b1bd-284">See also</span></span>

[<span data-ttu-id="9b1bd-285">Välja en dataintegreringsteknik</span><span class="sxs-lookup"><span data-stu-id="9b1bd-285">Choose a data integration technology</span></span>](hr-admin-integration-choose-technology.md)<br>
[<span data-ttu-id="9b1bd-286">Konfigurera Dataverse-integrering</span><span class="sxs-lookup"><span data-stu-id="9b1bd-286">Configure Dataverse integration</span></span>](hr-admin-integration-common-data-service.md)<br>
[<span data-ttu-id="9b1bd-287">Konfigurera virtuella Dataverse-register</span><span class="sxs-lookup"><span data-stu-id="9b1bd-287">Configure Dataverse virtual tables</span></span>](hr-admin-integration-common-data-service-virtual-entities.md)<br>
[<span data-ttu-id="9b1bd-288">Vanliga frågor och svar om virtuella register i Personal</span><span class="sxs-lookup"><span data-stu-id="9b1bd-288">Human Resources virtual tables FAQ</span></span>](hr-admin-virtual-entity-faq.md)<br>
[<span data-ttu-id="9b1bd-289">Vad är Microsoft Dataverse?</span><span class="sxs-lookup"><span data-stu-id="9b1bd-289">What is Microsoft Dataverse?</span></span>](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro)<br>
[<span data-ttu-id="9b1bd-290">Terminologiuppdateringar</span><span class="sxs-lookup"><span data-stu-id="9b1bd-290">Terminology updates</span></span>](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro#terminology-updates)


[!INCLUDE[footer-include](../includes/footer-banner.md)]