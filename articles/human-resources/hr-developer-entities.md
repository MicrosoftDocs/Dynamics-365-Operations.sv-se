---
title: Dataverse-register
description: Microsoft Dynamics 365 Human Resources använder Dataverse för att aktivera scenarier för utökning och integration.
author: andreabichsel
manager: tfehr
ms.date: 01/25/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
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
ms.openlocfilehash: caf8b0a5d0b24ef3619f45a6d236acae6d29c8ab
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/17/2021
ms.locfileid: "5465232"
---
# <a name="dataverse-tables"></a><span data-ttu-id="0ec0a-103">Dataverse-register</span><span class="sxs-lookup"><span data-stu-id="0ec0a-103">Dataverse tables</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="0ec0a-104">Microsoft Dynamics 365 Human Resources använder Dataverse för att aktivera scenarier för utökning och integration.</span><span class="sxs-lookup"><span data-stu-id="0ec0a-104">Microsoft Dynamics 365 Human Resources uses Dataverse to enable extensibility and integration scenarios.</span></span>

> [!NOTE]
> <span data-ttu-id="0ec0a-105">Personal-entiteter motsvarar Dataverse-register.</span><span class="sxs-lookup"><span data-stu-id="0ec0a-105">Human Resources entities correspond to Dataverse tables.</span></span> <span data-ttu-id="0ec0a-106">Mer information om Dataverse (tidigare Common Data Service) och terminologiuppdateringar finns i [Vad är Microsoft Dataverse?](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro)</span><span class="sxs-lookup"><span data-stu-id="0ec0a-106">For more information about Dataverse (formerly Common Data Service) and terminology updates, see [What is Microsoft Dataverse?](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro)</span></span>

<span data-ttu-id="0ec0a-107">Följande Dataverse-register baseras på Personal-entiteter.</span><span class="sxs-lookup"><span data-stu-id="0ec0a-107">The following Dataverse tables are available based on Human Resources entities.</span></span>

## <a name="benefit-tables"></a><span data-ttu-id="0ec0a-108">Förmånsregister</span><span class="sxs-lookup"><span data-stu-id="0ec0a-108">Benefit tables</span></span>

| <span data-ttu-id="0ec0a-109">Namn</span><span class="sxs-lookup"><span data-stu-id="0ec0a-109">Name</span></span> | <span data-ttu-id="0ec0a-110">Register</span><span class="sxs-lookup"><span data-stu-id="0ec0a-110">Table</span></span> |
| --- | --- |
| <span data-ttu-id="0ec0a-111">Frekvens i förmånsberäkning</span><span class="sxs-lookup"><span data-stu-id="0ec0a-111">Benefit Calculation Frequency</span></span> | <span data-ttu-id="0ec0a-112">cdm_benefitcalculationfrequency</span><span class="sxs-lookup"><span data-stu-id="0ec0a-112">cdm_benefitcalculationfrequency</span></span> |
| <span data-ttu-id="0ec0a-113">Löneperiod med frekvens i förmånsberäkning</span><span class="sxs-lookup"><span data-stu-id="0ec0a-113">Benefit Calculation Frequency Pay Period</span></span> | <span data-ttu-id="0ec0a-114">cdm_benefitcalculationfrequencypayperiod</span><span class="sxs-lookup"><span data-stu-id="0ec0a-114">cdm_benefitcalculationfrequencypayperiod</span></span> |
| <span data-ttu-id="0ec0a-115">Tariff för förmånsberäkning</span><span class="sxs-lookup"><span data-stu-id="0ec0a-115">Benefit Calculation Rate</span></span> | <span data-ttu-id="0ec0a-116">cdm_benefitcalculationrate</span><span class="sxs-lookup"><span data-stu-id="0ec0a-116">cdm_benefitcalculationrate</span></span> |
| <span data-ttu-id="0ec0a-117">Uppgift om tariff för förmånsberäkning</span><span class="sxs-lookup"><span data-stu-id="0ec0a-117">Benefit Calculation Rate Detail</span></span> | <span data-ttu-id="0ec0a-118">cdm_benefitcalculationratedetail</span><span class="sxs-lookup"><span data-stu-id="0ec0a-118">cdm_benefitcalculationratedetail</span></span> |
| <span data-ttu-id="0ec0a-119">Förmånsalternativ</span><span class="sxs-lookup"><span data-stu-id="0ec0a-119">Benefit Option</span></span> | <span data-ttu-id="0ec0a-120">cdm_benefitoption</span><span class="sxs-lookup"><span data-stu-id="0ec0a-120">cdm_benefitoption</span></span> |
| <span data-ttu-id="0ec0a-121">Förmånsplan</span><span class="sxs-lookup"><span data-stu-id="0ec0a-121">Benefit Plan</span></span> | <span data-ttu-id="0ec0a-122">cdm_benefitplan (inte aktiverat för stöd för anpassade fält)</span><span class="sxs-lookup"><span data-stu-id="0ec0a-122">cdm_benefitplan (Not enabled for custom field support)</span></span> |
| <span data-ttu-id="0ec0a-123">Förmånstyp</span><span class="sxs-lookup"><span data-stu-id="0ec0a-123">Benefit Type</span></span> | <span data-ttu-id="0ec0a-124">cdm_benefittype</span><span class="sxs-lookup"><span data-stu-id="0ec0a-124">cdm_benefittype</span></span> |

## <a name="business-process-tasks-tables"></a><span data-ttu-id="0ec0a-125">Uppgiftsentiteter för affärsprocesser</span><span class="sxs-lookup"><span data-stu-id="0ec0a-125">Business process tasks tables</span></span>

| <span data-ttu-id="0ec0a-126">Namn</span><span class="sxs-lookup"><span data-stu-id="0ec0a-126">Name</span></span> | <span data-ttu-id="0ec0a-127">Register</span><span class="sxs-lookup"><span data-stu-id="0ec0a-127">Table</span></span> |
| --- | --- |
| <span data-ttu-id="0ec0a-128">Affärsprocesskalender</span><span class="sxs-lookup"><span data-stu-id="0ec0a-128">Business Process Calendar</span></span> | <span data-ttu-id="0ec0a-129">cdm_businessprocesscalendar</span><span class="sxs-lookup"><span data-stu-id="0ec0a-129">cdm_businessprocesscalendar</span></span> |
| <span data-ttu-id="0ec0a-130">Tilldelning av affärsprocessgrupp</span><span class="sxs-lookup"><span data-stu-id="0ec0a-130">Business Process Group Assignment</span></span> | <span data-ttu-id="0ec0a-131">cdm_businessprocessgroupassignment</span><span class="sxs-lookup"><span data-stu-id="0ec0a-131">cdm_businessprocessgroupassignment</span></span> |
| <span data-ttu-id="0ec0a-132">Affärsprocessbibliotekets uppgiftsgrupp</span><span class="sxs-lookup"><span data-stu-id="0ec0a-132">Business Process Library Task Group</span></span> | <span data-ttu-id="0ec0a-133">cdm_businessprocesslibrarytaskgroup</span><span class="sxs-lookup"><span data-stu-id="0ec0a-133">cdm_businessprocesslibrarytaskgroup</span></span> |
| <span data-ttu-id="0ec0a-134">Affärsprocessfas</span><span class="sxs-lookup"><span data-stu-id="0ec0a-134">Business Process Stage</span></span> | <span data-ttu-id="0ec0a-135">cdm_businessprocessstage</span><span class="sxs-lookup"><span data-stu-id="0ec0a-135">cdm_businessprocessstage</span></span> |
| <span data-ttu-id="0ec0a-136">Checklistemallens rubrik</span><span class="sxs-lookup"><span data-stu-id="0ec0a-136">Checklist Template Header</span></span> | <span data-ttu-id="0ec0a-137">cdm_businessprocesstemplateheader</span><span class="sxs-lookup"><span data-stu-id="0ec0a-137">cdm_businessprocesstemplateheader</span></span> |
| <span data-ttu-id="0ec0a-138">Checklistemallens uppgift</span><span class="sxs-lookup"><span data-stu-id="0ec0a-138">Checklist Template Task</span></span> | <span data-ttu-id="0ec0a-139">cdm_businessprocesstemplatetask</span><span class="sxs-lookup"><span data-stu-id="0ec0a-139">cdm_businessprocesstemplatetask</span></span> |

## <a name="compensation-tables"></a><span data-ttu-id="0ec0a-140">Kompensationsregister</span><span class="sxs-lookup"><span data-stu-id="0ec0a-140">Compensation tables</span></span>

| <span data-ttu-id="0ec0a-141">Namn</span><span class="sxs-lookup"><span data-stu-id="0ec0a-141">Name</span></span> | <span data-ttu-id="0ec0a-142">Register</span><span class="sxs-lookup"><span data-stu-id="0ec0a-142">Table</span></span> |
| --- | --- |
| <span data-ttu-id="0ec0a-143">Fast kompensationsplan</span><span class="sxs-lookup"><span data-stu-id="0ec0a-143">Compensation Fixed Plan</span></span> | <span data-ttu-id="0ec0a-144">cdm_compensationfixedplan</span><span class="sxs-lookup"><span data-stu-id="0ec0a-144">cdm_compensationfixedplan</span></span> |
| <span data-ttu-id="0ec0a-145">Kompensationsrutnät</span><span class="sxs-lookup"><span data-stu-id="0ec0a-145">Compensation Grid</span></span> | <span data-ttu-id="0ec0a-146">cdm_compensationgrid</span><span class="sxs-lookup"><span data-stu-id="0ec0a-146">cdm_compensationgrid</span></span> |
| <span data-ttu-id="0ec0a-147">Kompensationsnivå</span><span class="sxs-lookup"><span data-stu-id="0ec0a-147">Compensation Level</span></span> | <span data-ttu-id="0ec0a-148">cdm_compensationlevel</span><span class="sxs-lookup"><span data-stu-id="0ec0a-148">cdm_compensationlevel</span></span> |
| <span data-ttu-id="0ec0a-149">Lönefrekvens för kompensation</span><span class="sxs-lookup"><span data-stu-id="0ec0a-149">Compensation Pay Frequency</span></span> | <span data-ttu-id="0ec0a-150">cdm_compensationpayfrequency</span><span class="sxs-lookup"><span data-stu-id="0ec0a-150">cdm_compensationpayfrequency</span></span> |
| <span data-ttu-id="0ec0a-151">Kompensationsreferenspunkt</span><span class="sxs-lookup"><span data-stu-id="0ec0a-151">Compensation Reference Point Setup</span></span> | <span data-ttu-id="0ec0a-152">cdm_compensationreferencepointsetup</span><span class="sxs-lookup"><span data-stu-id="0ec0a-152">cdm_compensationreferencepointsetup</span></span> |
| <span data-ttu-id="0ec0a-153">Ställ in kompensationsreferenspunkt</span><span class="sxs-lookup"><span data-stu-id="0ec0a-153">Compensation Reference Point Setup Line</span></span> | <span data-ttu-id="0ec0a-154">cdm_compensationreferencepointsetupline</span><span class="sxs-lookup"><span data-stu-id="0ec0a-154">cdm_compensationreferencepointsetupline</span></span> |
| <span data-ttu-id="0ec0a-155">Kompensationsregion</span><span class="sxs-lookup"><span data-stu-id="0ec0a-155">Compensation Region</span></span> | <span data-ttu-id="0ec0a-156">cdm_compensationregion</span><span class="sxs-lookup"><span data-stu-id="0ec0a-156">cdm_compensationregion</span></span> |
| <span data-ttu-id="0ec0a-157">Kompensationsstruktur</span><span class="sxs-lookup"><span data-stu-id="0ec0a-157">Compensation Structure</span></span> | <span data-ttu-id="0ec0a-158">cdm_compensationstructure</span><span class="sxs-lookup"><span data-stu-id="0ec0a-158">cdm_compensationstructure</span></span> |
| <span data-ttu-id="0ec0a-159">Variabel kompensationsplan</span><span class="sxs-lookup"><span data-stu-id="0ec0a-159">Compensation Variable Plan</span></span> | <span data-ttu-id="0ec0a-160">cdm_compensationvariableplan</span><span class="sxs-lookup"><span data-stu-id="0ec0a-160">cdm_compensationvariableplan</span></span> |
| <span data-ttu-id="0ec0a-161">Variabel kompensationsplannivå</span><span class="sxs-lookup"><span data-stu-id="0ec0a-161">Compensation Variable Plan Level</span></span> | <span data-ttu-id="0ec0a-162">cdm_compensationvariableplanlevel</span><span class="sxs-lookup"><span data-stu-id="0ec0a-162">cdm_compensationvariableplanlevel</span></span> |
| <span data-ttu-id="0ec0a-163">Typ av variabel kompensationsplan</span><span class="sxs-lookup"><span data-stu-id="0ec0a-163">Compensation Variable Plan Type</span></span> | <span data-ttu-id="0ec0a-164">cdm_compensationvariableplantype</span><span class="sxs-lookup"><span data-stu-id="0ec0a-164">cdm_compensationvariableplantype</span></span> |
| <span data-ttu-id="0ec0a-165">Händelse för fast kompensation</span><span class="sxs-lookup"><span data-stu-id="0ec0a-165">Fixed Compensation Event</span></span> | <span data-ttu-id="0ec0a-166">cdm_fixedcompensationevent</span><span class="sxs-lookup"><span data-stu-id="0ec0a-166">cdm_fixedcompensationevent</span></span> |
| <span data-ttu-id="0ec0a-167">Överlåtelseregel</span><span class="sxs-lookup"><span data-stu-id="0ec0a-167">Vesting Rule</span></span> | <span data-ttu-id="0ec0a-168">cdm_vestingrule</span><span class="sxs-lookup"><span data-stu-id="0ec0a-168">cdm_vestingrule</span></span> |
| <span data-ttu-id="0ec0a-169">Arbetarens fasta kompensation</span><span class="sxs-lookup"><span data-stu-id="0ec0a-169">Worker Fixed Compensation</span></span> | <span data-ttu-id="0ec0a-170">cdm_workerfixedcompensation</span><span class="sxs-lookup"><span data-stu-id="0ec0a-170">cdm_workerfixedcompensation</span></span> |

## <a name="organization-tables"></a><span data-ttu-id="0ec0a-171">Organisationsregister</span><span class="sxs-lookup"><span data-stu-id="0ec0a-171">Organization tables</span></span>

| <span data-ttu-id="0ec0a-172">Namn</span><span class="sxs-lookup"><span data-stu-id="0ec0a-172">Name</span></span> | <span data-ttu-id="0ec0a-173">Register</span><span class="sxs-lookup"><span data-stu-id="0ec0a-173">Table</span></span> |
| --- | --- |
| <span data-ttu-id="0ec0a-174">Avdelning</span><span class="sxs-lookup"><span data-stu-id="0ec0a-174">Department</span></span> | <span data-ttu-id="0ec0a-175">cdm_department</span><span class="sxs-lookup"><span data-stu-id="0ec0a-175">cdm_department</span></span> |
| <span data-ttu-id="0ec0a-176">Anställning</span><span class="sxs-lookup"><span data-stu-id="0ec0a-176">Employment</span></span> | <span data-ttu-id="0ec0a-177">cdm_employment</span><span class="sxs-lookup"><span data-stu-id="0ec0a-177">cdm_employment</span></span> |
| <span data-ttu-id="0ec0a-178">Företag</span><span class="sxs-lookup"><span data-stu-id="0ec0a-178">Company</span></span> | <span data-ttu-id="0ec0a-179">cdm_company</span><span class="sxs-lookup"><span data-stu-id="0ec0a-179">cdm_company</span></span> |
| <span data-ttu-id="0ec0a-180">Befattning</span><span class="sxs-lookup"><span data-stu-id="0ec0a-180">Job</span></span> | <span data-ttu-id="0ec0a-181">cdm_job</span><span class="sxs-lookup"><span data-stu-id="0ec0a-181">cdm_job</span></span> |
| <span data-ttu-id="0ec0a-182">Jobbfunktion</span><span class="sxs-lookup"><span data-stu-id="0ec0a-182">Job Function</span></span> | <span data-ttu-id="0ec0a-183">cdm_jobfunction</span><span class="sxs-lookup"><span data-stu-id="0ec0a-183">cdm_jobfunction</span></span> |
| <span data-ttu-id="0ec0a-184">Befattning</span><span class="sxs-lookup"><span data-stu-id="0ec0a-184">Job Position</span></span> | <span data-ttu-id="0ec0a-185">cdm_jobposition</span><span class="sxs-lookup"><span data-stu-id="0ec0a-185">cdm_jobposition</span></span> |
| <span data-ttu-id="0ec0a-186">Befattningstyp</span><span class="sxs-lookup"><span data-stu-id="0ec0a-186">Position Type</span></span> | <span data-ttu-id="0ec0a-187">cdm_positiontype</span><span class="sxs-lookup"><span data-stu-id="0ec0a-187">cdm_positiontype</span></span> |
| <span data-ttu-id="0ec0a-188">Befattningstilldelning för arbetare</span><span class="sxs-lookup"><span data-stu-id="0ec0a-188">Position Worker Assignment</span></span> | <span data-ttu-id="0ec0a-189">cdm_positionworkerassignmentmap</span><span class="sxs-lookup"><span data-stu-id="0ec0a-189">cdm_positionworkerassignmentmap</span></span> |
| <span data-ttu-id="0ec0a-190">Befattningsdimension</span><span class="sxs-lookup"><span data-stu-id="0ec0a-190">Job Position Dimension</span></span> | <span data-ttu-id="0ec0a-191">cdm_jobpositiondimension</span><span class="sxs-lookup"><span data-stu-id="0ec0a-191">cdm_jobpositiondimension</span></span>|
| <span data-ttu-id="0ec0a-192">Jobbtyp</span><span class="sxs-lookup"><span data-stu-id="0ec0a-192">Job Type</span></span> | <span data-ttu-id="0ec0a-193">cdm_jobtype</span><span class="sxs-lookup"><span data-stu-id="0ec0a-193">cdm_jobtype</span></span> |
| <span data-ttu-id="0ec0a-194">Språk</span><span class="sxs-lookup"><span data-stu-id="0ec0a-194">Language</span></span> | <span data-ttu-id="0ec0a-195">cdm_language</span><span class="sxs-lookup"><span data-stu-id="0ec0a-195">cdm_language</span></span> |
| <span data-ttu-id="0ec0a-196">Namn</span><span class="sxs-lookup"><span data-stu-id="0ec0a-196">Title</span></span> | <span data-ttu-id="0ec0a-197">cdm_title</span><span class="sxs-lookup"><span data-stu-id="0ec0a-197">cdm_title</span></span> |

> [!NOTE]
> <span data-ttu-id="0ec0a-198">Ekonomiska dimensioner för **Befattningstyp**, **Befattningstilldelning för arbetare** och **Anställning** ger integration med Dataverse i en riktning.</span><span class="sxs-lookup"><span data-stu-id="0ec0a-198">Financial dimensions for **Position Type**, **Position Worker Assignment**, and **Employment** provide one-direction integration to Dataverse.</span></span> <span data-ttu-id="0ec0a-199">Uppdateringar av ekonomiska dimensioner kan för närvarande inte synkroniseras från Dataverse till personal.</span><span class="sxs-lookup"><span data-stu-id="0ec0a-199">Financial dimensions updates currently can't synchronize from Dataverse to Human Resources.</span></span> 

## <a name="leave-and-absence-tables"></a><span data-ttu-id="0ec0a-200">Tjänstledighets- och frånvaroregister</span><span class="sxs-lookup"><span data-stu-id="0ec0a-200">Leave and absence tables</span></span>

| <span data-ttu-id="0ec0a-201">Namn</span><span class="sxs-lookup"><span data-stu-id="0ec0a-201">Name</span></span> | <span data-ttu-id="0ec0a-202">Register</span><span class="sxs-lookup"><span data-stu-id="0ec0a-202">Table</span></span> |
| --- | --- |
| <span data-ttu-id="0ec0a-203">Transaktion för tjänstledighetsbank</span><span class="sxs-lookup"><span data-stu-id="0ec0a-203">Leave Bank Transaction</span></span> | <span data-ttu-id="0ec0a-204">cdm_leavebanktransaction</span><span class="sxs-lookup"><span data-stu-id="0ec0a-204">cdm_leavebanktransaction</span></span> |
| <span data-ttu-id="0ec0a-205">Anmälning om tjänstledighet</span><span class="sxs-lookup"><span data-stu-id="0ec0a-205">Leave Enrollment</span></span> | <span data-ttu-id="0ec0a-206">cdm_leaveenrollment</span><span class="sxs-lookup"><span data-stu-id="0ec0a-206">cdm_leaveenrollment</span></span> |
| <span data-ttu-id="0ec0a-207">Tjänstledighetsplan</span><span class="sxs-lookup"><span data-stu-id="0ec0a-207">Leave Plan</span></span> | <span data-ttu-id="0ec0a-208">cdm_leaveplan</span><span class="sxs-lookup"><span data-stu-id="0ec0a-208">cdm_leaveplan</span></span> |
| <span data-ttu-id="0ec0a-209">Begäran om tjänstledighet</span><span class="sxs-lookup"><span data-stu-id="0ec0a-209">Leave Request</span></span> | <span data-ttu-id="0ec0a-210">cdm_leaverequest</span><span class="sxs-lookup"><span data-stu-id="0ec0a-210">cdm_leaverequest</span></span> |
| <span data-ttu-id="0ec0a-211">Information om att lämna begäran</span><span class="sxs-lookup"><span data-stu-id="0ec0a-211">Leave Request Detail</span></span> | <span data-ttu-id="0ec0a-212">cdm_leaverequestdetail</span><span class="sxs-lookup"><span data-stu-id="0ec0a-212">cdm_leaverequestdetail</span></span> |
| <span data-ttu-id="0ec0a-213">Tjänstledighetstyp</span><span class="sxs-lookup"><span data-stu-id="0ec0a-213">Leave Type</span></span> | <span data-ttu-id="0ec0a-214">cdm_leavetype</span><span class="sxs-lookup"><span data-stu-id="0ec0a-214">cdm_leavetype</span></span> |
| <span data-ttu-id="0ec0a-215">Ledighetstypens orsakskod</span><span class="sxs-lookup"><span data-stu-id="0ec0a-215">Leave Type Reason Code</span></span> | <span data-ttu-id="0ec0a-216">cdm_leavetypereasoncode</span><span class="sxs-lookup"><span data-stu-id="0ec0a-216">cdm_leavetypereasoncode</span></span> |

## <a name="payroll-tables"></a><span data-ttu-id="0ec0a-217">Löneregister</span><span class="sxs-lookup"><span data-stu-id="0ec0a-217">Payroll tables</span></span>

| <span data-ttu-id="0ec0a-218">Namn</span><span class="sxs-lookup"><span data-stu-id="0ec0a-218">Name</span></span> | <span data-ttu-id="0ec0a-219">Register</span><span class="sxs-lookup"><span data-stu-id="0ec0a-219">Table</span></span> |
| --- | --- |
| <span data-ttu-id="0ec0a-220">Lönecykel</span><span class="sxs-lookup"><span data-stu-id="0ec0a-220">Pay Cycle</span></span> | <span data-ttu-id="0ec0a-221">cdm_paycycle</span><span class="sxs-lookup"><span data-stu-id="0ec0a-221">cdm_paycycle</span></span> |
| <span data-ttu-id="0ec0a-222">Löneperiod</span><span class="sxs-lookup"><span data-stu-id="0ec0a-222">Pay Period</span></span> | <span data-ttu-id="0ec0a-223">cdm_payperiod</span><span class="sxs-lookup"><span data-stu-id="0ec0a-223">cdm_payperiod</span></span> |
| <span data-ttu-id="0ec0a-224">Inkomstkod</span><span class="sxs-lookup"><span data-stu-id="0ec0a-224">Payroll Earning Code</span></span> | <span data-ttu-id="0ec0a-225">cdm_payrollearningcode</span><span class="sxs-lookup"><span data-stu-id="0ec0a-225">cdm_payrollearningcode</span></span> |
| <span data-ttu-id="0ec0a-226">Bankkontoutbetalningar</span><span class="sxs-lookup"><span data-stu-id="0ec0a-226">Bank Account Disbursement</span></span> | <span data-ttu-id="0ec0a-227">cdm_bankaccountdisbursement</span><span class="sxs-lookup"><span data-stu-id="0ec0a-227">cdm_bankaccountdisbursement</span></span> |
| <span data-ttu-id="0ec0a-228">Skatteregion</span><span class="sxs-lookup"><span data-stu-id="0ec0a-228">Tax Region</span></span> | <span data-ttu-id="0ec0a-229">cdm_taxregion</span><span class="sxs-lookup"><span data-stu-id="0ec0a-229">cdm_taxregion</span></span> |

## <a name="worker-tables"></a><span data-ttu-id="0ec0a-230">Medarbetarregister</span><span class="sxs-lookup"><span data-stu-id="0ec0a-230">Worker tables</span></span>

| <span data-ttu-id="0ec0a-231">Namn</span><span class="sxs-lookup"><span data-stu-id="0ec0a-231">Name</span></span> | <span data-ttu-id="0ec0a-232">Register</span><span class="sxs-lookup"><span data-stu-id="0ec0a-232">Table</span></span> |
| --- | --- |
| <span data-ttu-id="0ec0a-233">Arbetare</span><span class="sxs-lookup"><span data-stu-id="0ec0a-233">Worker</span></span> | <span data-ttu-id="0ec0a-234">cdm_worker</span><span class="sxs-lookup"><span data-stu-id="0ec0a-234">cdm_worker</span></span> |
| <span data-ttu-id="0ec0a-235">Adress för arbetare</span><span class="sxs-lookup"><span data-stu-id="0ec0a-235">Worker Address</span></span> | <span data-ttu-id="0ec0a-236">cdm_workeraddress</span><span class="sxs-lookup"><span data-stu-id="0ec0a-236">cdm_workeraddress</span></span> |
| <span data-ttu-id="0ec0a-237">Arbetarens personuppgift</span><span class="sxs-lookup"><span data-stu-id="0ec0a-237">Worker Personal Detail</span></span> | <span data-ttu-id="0ec0a-238">cdm_workerpersonaldetail</span><span class="sxs-lookup"><span data-stu-id="0ec0a-238">cdm_workerpersonaldetail</span></span> |
| <span data-ttu-id="0ec0a-239">Arbetsidentifieringsnummer</span><span class="sxs-lookup"><span data-stu-id="0ec0a-239">Worker Person Identification Number</span></span> | <span data-ttu-id="0ec0a-240">cdm_workerpersonidentificationnumber</span><span class="sxs-lookup"><span data-stu-id="0ec0a-240">cdm_workerpersonidentificationnumber</span></span> |
| <span data-ttu-id="0ec0a-241">Arbetsidentifieringstyp</span><span class="sxs-lookup"><span data-stu-id="0ec0a-241">Worker Person Identification Type</span></span> | <span data-ttu-id="0ec0a-242">cdm_workerpersonidentificationtype</span><span class="sxs-lookup"><span data-stu-id="0ec0a-242">cdm_workerpersonidentificationtype</span></span> |
| <span data-ttu-id="0ec0a-243">Arbetskalender</span><span class="sxs-lookup"><span data-stu-id="0ec0a-243">Work Calendar</span></span> | <span data-ttu-id="0ec0a-244">cdm_workcalendar</span><span class="sxs-lookup"><span data-stu-id="0ec0a-244">cdm_workcalendar</span></span> |
| <span data-ttu-id="0ec0a-245">Arbetsdagar i kalendern</span><span class="sxs-lookup"><span data-stu-id="0ec0a-245">Work Calendar Day</span></span> | <span data-ttu-id="0ec0a-246">cdm_workcalendarday</span><span class="sxs-lookup"><span data-stu-id="0ec0a-246">cdm_workcalendarday</span></span> |
| <span data-ttu-id="0ec0a-247">Helgdag i arbetskalender</span><span class="sxs-lookup"><span data-stu-id="0ec0a-247">Work Calendar Holiday</span></span> |<span data-ttu-id="0ec0a-248">cdm_workcalendarholiday</span><span class="sxs-lookup"><span data-stu-id="0ec0a-248">cdm_workcalendarholiday</span></span> |
| <span data-ttu-id="0ec0a-249">Arbetskalenderns datumrad</span><span class="sxs-lookup"><span data-stu-id="0ec0a-249">Work Calendar Holiday Line</span></span> | <span data-ttu-id="0ec0a-250">cdm_workcalendarholidayline</span><span class="sxs-lookup"><span data-stu-id="0ec0a-250">cdm_workcalendarholidayline</span></span> |
| <span data-ttu-id="0ec0a-251">Tidsintervall till arbetskalendern</span><span class="sxs-lookup"><span data-stu-id="0ec0a-251">Work Calendar Time Interval</span></span> | <span data-ttu-id="0ec0a-252">cdm_workcalendartimeinterval (inte aktiverat för stöd för anpassade fält)</span><span class="sxs-lookup"><span data-stu-id="0ec0a-252">cdm_workcalendartimeinterval (Not enabled for custom field support)</span></span> |
| <span data-ttu-id="0ec0a-253">Bankkonto för arbetare</span><span class="sxs-lookup"><span data-stu-id="0ec0a-253">Worker Bank Account</span></span> | <span data-ttu-id="0ec0a-254">cdm_workerbankaccount</span><span class="sxs-lookup"><span data-stu-id="0ec0a-254">cdm_workerbankaccount</span></span> |

## <a name="worker-setup-tables"></a><span data-ttu-id="0ec0a-255">Inställningsregister för medarbetare</span><span class="sxs-lookup"><span data-stu-id="0ec0a-255">Worker setup tables</span></span>

| <span data-ttu-id="0ec0a-256">Namn</span><span class="sxs-lookup"><span data-stu-id="0ec0a-256">Name</span></span> | <span data-ttu-id="0ec0a-257">Register</span><span class="sxs-lookup"><span data-stu-id="0ec0a-257">Table</span></span> |
| --- | --- |
| <span data-ttu-id="0ec0a-258">Veteranstatus</span><span class="sxs-lookup"><span data-stu-id="0ec0a-258">Veteran Status</span></span> | <span data-ttu-id="0ec0a-259">cdm_veteranstatus</span><span class="sxs-lookup"><span data-stu-id="0ec0a-259">cdm_veteranstatus</span></span> |
| <span data-ttu-id="0ec0a-260">Etniskt ursprung</span><span class="sxs-lookup"><span data-stu-id="0ec0a-260">Ethnic Origin</span></span> | <span data-ttu-id="0ec0a-261">cdm_ethnicorigin</span><span class="sxs-lookup"><span data-stu-id="0ec0a-261">cdm_ethnicorigin</span></span> |
| <span data-ttu-id="0ec0a-262">Orsakskod</span><span class="sxs-lookup"><span data-stu-id="0ec0a-262">Reason Code</span></span> | <span data-ttu-id="0ec0a-263">cdm_reasoncode</span><span class="sxs-lookup"><span data-stu-id="0ec0a-263">cdm_reasoncode</span></span> |
| <span data-ttu-id="0ec0a-264">Utfärdande organ för personidentifiering</span><span class="sxs-lookup"><span data-stu-id="0ec0a-264">Person Identification Issuing Agency</span></span> | <span data-ttu-id="0ec0a-265">cdm_personidentificationissuingagency</span><span class="sxs-lookup"><span data-stu-id="0ec0a-265">cdm_personidentificationissuingagency</span></span> |

## <a name="competency-tables"></a><span data-ttu-id="0ec0a-266">Kompetensregister</span><span class="sxs-lookup"><span data-stu-id="0ec0a-266">Competency tables</span></span>

| <span data-ttu-id="0ec0a-267">Namn</span><span class="sxs-lookup"><span data-stu-id="0ec0a-267">Name</span></span> | <span data-ttu-id="0ec0a-268">Register</span><span class="sxs-lookup"><span data-stu-id="0ec0a-268">Table</span></span> |
| --- | --- |
| <span data-ttu-id="0ec0a-269">Kompetenstyp</span><span class="sxs-lookup"><span data-stu-id="0ec0a-269">Skill Type</span></span> | <span data-ttu-id="0ec0a-270">cdm_skilltype</span><span class="sxs-lookup"><span data-stu-id="0ec0a-270">cdm_skilltype</span></span> |

## <a name="table-relationship-models"></a><span data-ttu-id="0ec0a-271">Relationsmodeller för register</span><span class="sxs-lookup"><span data-stu-id="0ec0a-271">Table relationship models</span></span>

### <a name="worker"></a><span data-ttu-id="0ec0a-272">Arbetare</span><span class="sxs-lookup"><span data-stu-id="0ec0a-272">Worker</span></span>

![Arbetare](./media/HCMCommon-worker-entity-diagram.png)

### <a name="job-and-job-position"></a><span data-ttu-id="0ec0a-274">Jobb och jobbefattning</span><span class="sxs-lookup"><span data-stu-id="0ec0a-274">Job and Job Position</span></span>

![Jobb och jobbefattning](./media/HCMCommon-job-and-job-position-entity-diagram.png)

### <a name="benefits"></a><span data-ttu-id="0ec0a-276">Fördelar</span><span class="sxs-lookup"><span data-stu-id="0ec0a-276">Benefits</span></span>

![Fördelar](./media/HCMCommon-benefits-entity-diagram.png)

### <a name="compensation"></a><span data-ttu-id="0ec0a-278">Kompensation</span><span class="sxs-lookup"><span data-stu-id="0ec0a-278">Compensation</span></span>

![Kompensation](./media/HCMCommon-compensation-entity-diagram.png)

### <a name="leave"></a><span data-ttu-id="0ec0a-280">Lämna</span><span class="sxs-lookup"><span data-stu-id="0ec0a-280">Leave</span></span>

![Lämna](./media/HCMCommon-leave-entity-diagram.png)

### <a name="work-calendar"></a><span data-ttu-id="0ec0a-282">Arbetskalender</span><span class="sxs-lookup"><span data-stu-id="0ec0a-282">Work Calendar</span></span>

![Arbetskalender](./media/HCMCommon-work-calendar-entity-diagram.png)

## <a name="see-also"></a><span data-ttu-id="0ec0a-284">Se även</span><span class="sxs-lookup"><span data-stu-id="0ec0a-284">See also</span></span>

[<span data-ttu-id="0ec0a-285">Välja en dataintegreringsteknik</span><span class="sxs-lookup"><span data-stu-id="0ec0a-285">Choose a data integration technology</span></span>](hr-admin-integration-choose-technology.md)<br>
[<span data-ttu-id="0ec0a-286">Konfigurera Dataverse-integrering</span><span class="sxs-lookup"><span data-stu-id="0ec0a-286">Configure Dataverse integration</span></span>](hr-admin-integration-common-data-service.md)<br>
[<span data-ttu-id="0ec0a-287">Konfigurera virtuella Dataverse-register</span><span class="sxs-lookup"><span data-stu-id="0ec0a-287">Configure Dataverse virtual tables</span></span>](hr-admin-integration-common-data-service-virtual-entities.md)<br>
[<span data-ttu-id="0ec0a-288">Vanliga frågor och svar om virtuella register i Personal</span><span class="sxs-lookup"><span data-stu-id="0ec0a-288">Human Resources virtual tables FAQ</span></span>](hr-admin-virtual-entity-faq.md)<br>
[<span data-ttu-id="0ec0a-289">Vad är Microsoft Dataverse?</span><span class="sxs-lookup"><span data-stu-id="0ec0a-289">What is Microsoft Dataverse?</span></span>](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro)<br>
[<span data-ttu-id="0ec0a-290">Terminologiuppdateringar</span><span class="sxs-lookup"><span data-stu-id="0ec0a-290">Terminology updates</span></span>](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro#terminology-updates)


[!INCLUDE[footer-include](../includes/footer-banner.md)]