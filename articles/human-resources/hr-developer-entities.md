---
title: Common Data Service-entiteter
description: Microsoft Dynamics 365 Human Resources använder Common Data Service för att aktivera scenarier för utökning och integration.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
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
ms.openlocfilehash: 988fa0b6d39a49b973626a8a0abe83c546f42297
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/17/2020
ms.locfileid: "4530016"
---
# <a name="common-data-service-entities"></a><span data-ttu-id="e3abc-103">Common Data Service-entiteter</span><span class="sxs-lookup"><span data-stu-id="e3abc-103">Common Data Service entities</span></span>

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="e3abc-104">Microsoft Dynamics 365 Human Resources använder Common Data Service för att aktivera scenarier för utökning och integration.</span><span class="sxs-lookup"><span data-stu-id="e3abc-104">Microsoft Dynamics 365 Human Resources uses Common Data Service to enable extensibility and integration scenarios.</span></span>

<span data-ttu-id="e3abc-105">Mer information om Common Data Service, se [Vad är Common Data Service](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro).</span><span class="sxs-lookup"><span data-stu-id="e3abc-105">For more information about Common Data Service, see [What is Common Data Service](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro).</span></span>

<span data-ttu-id="e3abc-106">Följande personalentiteter är tillgängliga i Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="e3abc-106">The following Human Resources entities are available in Common Data Service.</span></span>

## <a name="benefit-entities"></a><span data-ttu-id="e3abc-107">Förmånsentiteter</span><span class="sxs-lookup"><span data-stu-id="e3abc-107">Benefit entities</span></span>

| <span data-ttu-id="e3abc-108">Namn</span><span class="sxs-lookup"><span data-stu-id="e3abc-108">Name</span></span> | <span data-ttu-id="e3abc-109">Enhet</span><span class="sxs-lookup"><span data-stu-id="e3abc-109">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="e3abc-110">Frekvens i förmånsberäkning</span><span class="sxs-lookup"><span data-stu-id="e3abc-110">Benefit Calculation Frequency</span></span> | <span data-ttu-id="e3abc-111">cdm_benefitcalculationfrequency</span><span class="sxs-lookup"><span data-stu-id="e3abc-111">cdm_benefitcalculationfrequency</span></span> |
| <span data-ttu-id="e3abc-112">Löneperiod med frekvens i förmånsberäkning</span><span class="sxs-lookup"><span data-stu-id="e3abc-112">Benefit Calculation Frequency Pay Period</span></span> | <span data-ttu-id="e3abc-113">cdm_benefitcalculationfrequencypayperiod</span><span class="sxs-lookup"><span data-stu-id="e3abc-113">cdm_benefitcalculationfrequencypayperiod</span></span> |
| <span data-ttu-id="e3abc-114">Tariff för förmånsberäkning</span><span class="sxs-lookup"><span data-stu-id="e3abc-114">Benefit Calculation Rate</span></span> | <span data-ttu-id="e3abc-115">cdm_benefitcalculationrate</span><span class="sxs-lookup"><span data-stu-id="e3abc-115">cdm_benefitcalculationrate</span></span> |
| <span data-ttu-id="e3abc-116">Uppgift om tariff för förmånsberäkning</span><span class="sxs-lookup"><span data-stu-id="e3abc-116">Benefit Calculation Rate Detail</span></span> | <span data-ttu-id="e3abc-117">cdm_benefitcalculationratedetail</span><span class="sxs-lookup"><span data-stu-id="e3abc-117">cdm_benefitcalculationratedetail</span></span> |
| <span data-ttu-id="e3abc-118">Förmånsalternativ</span><span class="sxs-lookup"><span data-stu-id="e3abc-118">Benefit Option</span></span> | <span data-ttu-id="e3abc-119">cdm_benefitoption</span><span class="sxs-lookup"><span data-stu-id="e3abc-119">cdm_benefitoption</span></span> |
| <span data-ttu-id="e3abc-120">Förmånsplan</span><span class="sxs-lookup"><span data-stu-id="e3abc-120">Benefit Plan</span></span> | <span data-ttu-id="e3abc-121">cdm_benefitplan (inte aktiverat för stöd för anpassade fält)</span><span class="sxs-lookup"><span data-stu-id="e3abc-121">cdm_benefitplan (Not enabled for custom field support)</span></span> |
| <span data-ttu-id="e3abc-122">Förmånstyp</span><span class="sxs-lookup"><span data-stu-id="e3abc-122">Benefit Type</span></span> | <span data-ttu-id="e3abc-123">cdm_benefittype</span><span class="sxs-lookup"><span data-stu-id="e3abc-123">cdm_benefittype</span></span> |

## <a name="business-process-tasks-entities"></a><span data-ttu-id="e3abc-124">Entiteter för affärsprocessuppgifter</span><span class="sxs-lookup"><span data-stu-id="e3abc-124">Business process tasks entities</span></span>

| <span data-ttu-id="e3abc-125">Namn</span><span class="sxs-lookup"><span data-stu-id="e3abc-125">Name</span></span> | <span data-ttu-id="e3abc-126">Enhet</span><span class="sxs-lookup"><span data-stu-id="e3abc-126">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="e3abc-127">Affärsprocesskalender</span><span class="sxs-lookup"><span data-stu-id="e3abc-127">Business Process Calendar</span></span> | <span data-ttu-id="e3abc-128">cdm_businessprocesscalendar</span><span class="sxs-lookup"><span data-stu-id="e3abc-128">cdm_businessprocesscalendar</span></span> |
| <span data-ttu-id="e3abc-129">Tilldelning av affärsprocessgrupp</span><span class="sxs-lookup"><span data-stu-id="e3abc-129">Business Process Group Assignment</span></span> | <span data-ttu-id="e3abc-130">cdm_businessprocessgroupassignment</span><span class="sxs-lookup"><span data-stu-id="e3abc-130">cdm_businessprocessgroupassignment</span></span> |
| <span data-ttu-id="e3abc-131">Affärsprocessbibliotekets uppgiftsgrupp</span><span class="sxs-lookup"><span data-stu-id="e3abc-131">Business Process Library Task Group</span></span> | <span data-ttu-id="e3abc-132">cdm_businessprocesslibrarytaskgroup</span><span class="sxs-lookup"><span data-stu-id="e3abc-132">cdm_businessprocesslibrarytaskgroup</span></span> |
| <span data-ttu-id="e3abc-133">Affärsprocessfas</span><span class="sxs-lookup"><span data-stu-id="e3abc-133">Business Process Stage</span></span> | <span data-ttu-id="e3abc-134">cdm_businessprocessstage</span><span class="sxs-lookup"><span data-stu-id="e3abc-134">cdm_businessprocessstage</span></span> |
| <span data-ttu-id="e3abc-135">Checklistemallens rubrik</span><span class="sxs-lookup"><span data-stu-id="e3abc-135">Checklist Template Header</span></span> | <span data-ttu-id="e3abc-136">cdm_businessprocesstemplateheader</span><span class="sxs-lookup"><span data-stu-id="e3abc-136">cdm_businessprocesstemplateheader</span></span> |
| <span data-ttu-id="e3abc-137">Checklistemallens uppgift</span><span class="sxs-lookup"><span data-stu-id="e3abc-137">Checklist Template Task</span></span> | <span data-ttu-id="e3abc-138">cdm_businessprocesstemplatetask</span><span class="sxs-lookup"><span data-stu-id="e3abc-138">cdm_businessprocesstemplatetask</span></span> |

## <a name="compensation-entities"></a><span data-ttu-id="e3abc-139">Enheter för kompensation</span><span class="sxs-lookup"><span data-stu-id="e3abc-139">Compensation entities</span></span>

| <span data-ttu-id="e3abc-140">Namn</span><span class="sxs-lookup"><span data-stu-id="e3abc-140">Name</span></span> | <span data-ttu-id="e3abc-141">Enhet</span><span class="sxs-lookup"><span data-stu-id="e3abc-141">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="e3abc-142">Plan för fast kompensation</span><span class="sxs-lookup"><span data-stu-id="e3abc-142">Compensation Fixed Plan</span></span> | <span data-ttu-id="e3abc-143">cdm_compensationfixedplan</span><span class="sxs-lookup"><span data-stu-id="e3abc-143">cdm_compensationfixedplan</span></span> |
| <span data-ttu-id="e3abc-144">Kompensationsrutnät</span><span class="sxs-lookup"><span data-stu-id="e3abc-144">Compensation Grid</span></span> | <span data-ttu-id="e3abc-145">cdm_compensationgrid</span><span class="sxs-lookup"><span data-stu-id="e3abc-145">cdm_compensationgrid</span></span> |
| <span data-ttu-id="e3abc-146">Kompensationsnivå</span><span class="sxs-lookup"><span data-stu-id="e3abc-146">Compensation Level</span></span> | <span data-ttu-id="e3abc-147">cdm_compensationlevel</span><span class="sxs-lookup"><span data-stu-id="e3abc-147">cdm_compensationlevel</span></span> |
| <span data-ttu-id="e3abc-148">Lönefrekvens för kompensation</span><span class="sxs-lookup"><span data-stu-id="e3abc-148">Compensation Pay Frequency</span></span> | <span data-ttu-id="e3abc-149">cdm_compensationpayfrequency</span><span class="sxs-lookup"><span data-stu-id="e3abc-149">cdm_compensationpayfrequency</span></span> |
| <span data-ttu-id="e3abc-150">Kompensationsreferenspunkt</span><span class="sxs-lookup"><span data-stu-id="e3abc-150">Compensation Reference Point Setup</span></span> | <span data-ttu-id="e3abc-151">cdm_compensationreferencepointsetup</span><span class="sxs-lookup"><span data-stu-id="e3abc-151">cdm_compensationreferencepointsetup</span></span> |
| <span data-ttu-id="e3abc-152">Ställ in kompensationsreferenspunkt</span><span class="sxs-lookup"><span data-stu-id="e3abc-152">Compensation Reference Point Setup Line</span></span> | <span data-ttu-id="e3abc-153">cdm_compensationreferencepointsetupline</span><span class="sxs-lookup"><span data-stu-id="e3abc-153">cdm_compensationreferencepointsetupline</span></span> |
| <span data-ttu-id="e3abc-154">Kompensationsregion</span><span class="sxs-lookup"><span data-stu-id="e3abc-154">Compensation Region</span></span> | <span data-ttu-id="e3abc-155">cdm_compensationregion</span><span class="sxs-lookup"><span data-stu-id="e3abc-155">cdm_compensationregion</span></span> |
| <span data-ttu-id="e3abc-156">Kompensationsstruktur</span><span class="sxs-lookup"><span data-stu-id="e3abc-156">Compensation Structure</span></span> | <span data-ttu-id="e3abc-157">cdm_compensationstructure</span><span class="sxs-lookup"><span data-stu-id="e3abc-157">cdm_compensationstructure</span></span> |
| <span data-ttu-id="e3abc-158">Variabel kompensationsplan</span><span class="sxs-lookup"><span data-stu-id="e3abc-158">Compensation Variable Plan</span></span> | <span data-ttu-id="e3abc-159">cdm_compensationvariableplan</span><span class="sxs-lookup"><span data-stu-id="e3abc-159">cdm_compensationvariableplan</span></span> |
| <span data-ttu-id="e3abc-160">Variabel kompensationsplannivå</span><span class="sxs-lookup"><span data-stu-id="e3abc-160">Compensation Variable Plan Level</span></span> | <span data-ttu-id="e3abc-161">cdm_compensationvariableplanlevel</span><span class="sxs-lookup"><span data-stu-id="e3abc-161">cdm_compensationvariableplanlevel</span></span> |
| <span data-ttu-id="e3abc-162">Typ av variabel kompensationsplan</span><span class="sxs-lookup"><span data-stu-id="e3abc-162">Compensation Variable Plan Type</span></span> | <span data-ttu-id="e3abc-163">cdm_compensationvariableplantype</span><span class="sxs-lookup"><span data-stu-id="e3abc-163">cdm_compensationvariableplantype</span></span> |
| <span data-ttu-id="e3abc-164">Händelse för fast kompensation</span><span class="sxs-lookup"><span data-stu-id="e3abc-164">Fixed Compensation Event</span></span> | <span data-ttu-id="e3abc-165">cdm_fixedcompensationevent</span><span class="sxs-lookup"><span data-stu-id="e3abc-165">cdm_fixedcompensationevent</span></span> |
| <span data-ttu-id="e3abc-166">Överlåtelseregel</span><span class="sxs-lookup"><span data-stu-id="e3abc-166">Vesting Rule</span></span> | <span data-ttu-id="e3abc-167">cdm_vestingrule</span><span class="sxs-lookup"><span data-stu-id="e3abc-167">cdm_vestingrule</span></span> |
| <span data-ttu-id="e3abc-168">Fast arbetarkompensation</span><span class="sxs-lookup"><span data-stu-id="e3abc-168">Worker Fixed Compensation</span></span> | <span data-ttu-id="e3abc-169">cdm_workerfixedcompensation</span><span class="sxs-lookup"><span data-stu-id="e3abc-169">cdm_workerfixedcompensation</span></span> |

## <a name="organization-entities"></a><span data-ttu-id="e3abc-170">Organisationsenheter</span><span class="sxs-lookup"><span data-stu-id="e3abc-170">Organization entities</span></span>

| <span data-ttu-id="e3abc-171">Namn</span><span class="sxs-lookup"><span data-stu-id="e3abc-171">Name</span></span> | <span data-ttu-id="e3abc-172">Enhet</span><span class="sxs-lookup"><span data-stu-id="e3abc-172">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="e3abc-173">Avdelning</span><span class="sxs-lookup"><span data-stu-id="e3abc-173">Department</span></span> | <span data-ttu-id="e3abc-174">cdm_department</span><span class="sxs-lookup"><span data-stu-id="e3abc-174">cdm_department</span></span> |
| <span data-ttu-id="e3abc-175">Anställning</span><span class="sxs-lookup"><span data-stu-id="e3abc-175">Employment</span></span> | <span data-ttu-id="e3abc-176">cdm_employment</span><span class="sxs-lookup"><span data-stu-id="e3abc-176">cdm_employment</span></span> |
| <span data-ttu-id="e3abc-177">Företag</span><span class="sxs-lookup"><span data-stu-id="e3abc-177">Company</span></span> | <span data-ttu-id="e3abc-178">cdm_company</span><span class="sxs-lookup"><span data-stu-id="e3abc-178">cdm_company</span></span> |
| <span data-ttu-id="e3abc-179">Befattning</span><span class="sxs-lookup"><span data-stu-id="e3abc-179">Job</span></span> | <span data-ttu-id="e3abc-180">cdm_job</span><span class="sxs-lookup"><span data-stu-id="e3abc-180">cdm_job</span></span> |
| <span data-ttu-id="e3abc-181">Jobbfunktion</span><span class="sxs-lookup"><span data-stu-id="e3abc-181">Job Function</span></span> | <span data-ttu-id="e3abc-182">cdm_jobfunction</span><span class="sxs-lookup"><span data-stu-id="e3abc-182">cdm_jobfunction</span></span> |
| <span data-ttu-id="e3abc-183">Befattning</span><span class="sxs-lookup"><span data-stu-id="e3abc-183">Job Position</span></span> | <span data-ttu-id="e3abc-184">cdm_jobposition</span><span class="sxs-lookup"><span data-stu-id="e3abc-184">cdm_jobposition</span></span> |
| <span data-ttu-id="e3abc-185">Befattningstyp</span><span class="sxs-lookup"><span data-stu-id="e3abc-185">Position Type</span></span> | <span data-ttu-id="e3abc-186">cdm_positiontype</span><span class="sxs-lookup"><span data-stu-id="e3abc-186">cdm_positiontype</span></span> |
| <span data-ttu-id="e3abc-187">Befattningstilldelning för arbetare</span><span class="sxs-lookup"><span data-stu-id="e3abc-187">Position Worker Assignment</span></span> | <span data-ttu-id="e3abc-188">cdm_positionworkerassignmentmap</span><span class="sxs-lookup"><span data-stu-id="e3abc-188">cdm_positionworkerassignmentmap</span></span> |
| <span data-ttu-id="e3abc-189">Befattningsdimension</span><span class="sxs-lookup"><span data-stu-id="e3abc-189">Job Position Dimension</span></span> | <span data-ttu-id="e3abc-190">cdm_jobpositiondimension</span><span class="sxs-lookup"><span data-stu-id="e3abc-190">cdm_jobpositiondimension</span></span>|
| <span data-ttu-id="e3abc-191">Jobbtyp</span><span class="sxs-lookup"><span data-stu-id="e3abc-191">Job Type</span></span> | <span data-ttu-id="e3abc-192">cdm_jobtype</span><span class="sxs-lookup"><span data-stu-id="e3abc-192">cdm_jobtype</span></span> |
| <span data-ttu-id="e3abc-193">Språk</span><span class="sxs-lookup"><span data-stu-id="e3abc-193">Language</span></span> | <span data-ttu-id="e3abc-194">cdm_language</span><span class="sxs-lookup"><span data-stu-id="e3abc-194">cdm_language</span></span> |
| <span data-ttu-id="e3abc-195">Namn</span><span class="sxs-lookup"><span data-stu-id="e3abc-195">Title</span></span> | <span data-ttu-id="e3abc-196">cdm_title</span><span class="sxs-lookup"><span data-stu-id="e3abc-196">cdm_title</span></span> |

> [!NOTE]
> <span data-ttu-id="e3abc-197">Ekonomiska dimensioner för **Befattningstyp**, **Befattningstilldelning för arbetare** och **Anställning** ger integration med Common Data Service i en riktning.</span><span class="sxs-lookup"><span data-stu-id="e3abc-197">Financial dimensions for **Position Type**, **Position Worker Assignment**, and **Employment** provide one-direction integration to Common Data Service.</span></span> <span data-ttu-id="e3abc-198">Uppdateringar av ekonomiska dimensioner kan för närvarande inte synkroniseras från Common Data Service till personal.</span><span class="sxs-lookup"><span data-stu-id="e3abc-198">Financial dimensions updates currently can't synchronize from Common Data Service to Human Resources.</span></span> 

## <a name="leave-and-absence-entities"></a><span data-ttu-id="e3abc-199">Enheter för tjänstledighet och frånvaro</span><span class="sxs-lookup"><span data-stu-id="e3abc-199">Leave and absence entities</span></span>

| <span data-ttu-id="e3abc-200">Namn</span><span class="sxs-lookup"><span data-stu-id="e3abc-200">Name</span></span> | <span data-ttu-id="e3abc-201">Enhet</span><span class="sxs-lookup"><span data-stu-id="e3abc-201">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="e3abc-202">Transaktion för tjänstledighetsbank</span><span class="sxs-lookup"><span data-stu-id="e3abc-202">Leave Bank Transaction</span></span> | <span data-ttu-id="e3abc-203">cdm_leavebanktransaction</span><span class="sxs-lookup"><span data-stu-id="e3abc-203">cdm_leavebanktransaction</span></span> |
| <span data-ttu-id="e3abc-204">Lämna anmälan</span><span class="sxs-lookup"><span data-stu-id="e3abc-204">Leave Enrollment</span></span> | <span data-ttu-id="e3abc-205">cdm_leaveenrollment</span><span class="sxs-lookup"><span data-stu-id="e3abc-205">cdm_leaveenrollment</span></span> |
| <span data-ttu-id="e3abc-206">Tjänstledighetsplan</span><span class="sxs-lookup"><span data-stu-id="e3abc-206">Leave Plan</span></span> | <span data-ttu-id="e3abc-207">cdm_leaveplan</span><span class="sxs-lookup"><span data-stu-id="e3abc-207">cdm_leaveplan</span></span> |
| <span data-ttu-id="e3abc-208">Begäran om tjänstledighet</span><span class="sxs-lookup"><span data-stu-id="e3abc-208">Leave Request</span></span> | <span data-ttu-id="e3abc-209">cdm_leaverequest</span><span class="sxs-lookup"><span data-stu-id="e3abc-209">cdm_leaverequest</span></span> |
| <span data-ttu-id="e3abc-210">Information om att lämna begäran</span><span class="sxs-lookup"><span data-stu-id="e3abc-210">Leave Request Detail</span></span> | <span data-ttu-id="e3abc-211">cdm_leaverequestdetail</span><span class="sxs-lookup"><span data-stu-id="e3abc-211">cdm_leaverequestdetail</span></span> |
| <span data-ttu-id="e3abc-212">Tjänstledighetstyp</span><span class="sxs-lookup"><span data-stu-id="e3abc-212">Leave Type</span></span> | <span data-ttu-id="e3abc-213">cdm_leavetype</span><span class="sxs-lookup"><span data-stu-id="e3abc-213">cdm_leavetype</span></span> |
| <span data-ttu-id="e3abc-214">Ledighetstypens orsakskod</span><span class="sxs-lookup"><span data-stu-id="e3abc-214">Leave Type Reason Code</span></span> | <span data-ttu-id="e3abc-215">cdm_leavetypereasoncode</span><span class="sxs-lookup"><span data-stu-id="e3abc-215">cdm_leavetypereasoncode</span></span> |

## <a name="payroll-entities"></a><span data-ttu-id="e3abc-216">Löneenheter</span><span class="sxs-lookup"><span data-stu-id="e3abc-216">Payroll entities</span></span>

| <span data-ttu-id="e3abc-217">Namn</span><span class="sxs-lookup"><span data-stu-id="e3abc-217">Name</span></span> | <span data-ttu-id="e3abc-218">Enhet</span><span class="sxs-lookup"><span data-stu-id="e3abc-218">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="e3abc-219">Lönecykel</span><span class="sxs-lookup"><span data-stu-id="e3abc-219">Pay Cycle</span></span> | <span data-ttu-id="e3abc-220">cdm_paycycle</span><span class="sxs-lookup"><span data-stu-id="e3abc-220">cdm_paycycle</span></span> |
| <span data-ttu-id="e3abc-221">Löneperiod</span><span class="sxs-lookup"><span data-stu-id="e3abc-221">Pay Period</span></span> | <span data-ttu-id="e3abc-222">cdm_payperiod</span><span class="sxs-lookup"><span data-stu-id="e3abc-222">cdm_payperiod</span></span> |
| <span data-ttu-id="e3abc-223">Inkomstkod för lön</span><span class="sxs-lookup"><span data-stu-id="e3abc-223">Payroll Earning Code</span></span> | <span data-ttu-id="e3abc-224">cdm_payrollearningcode</span><span class="sxs-lookup"><span data-stu-id="e3abc-224">cdm_payrollearningcode</span></span> |
| <span data-ttu-id="e3abc-225">Bankkontoutbetalningar</span><span class="sxs-lookup"><span data-stu-id="e3abc-225">Bank Account Disbursement</span></span> | <span data-ttu-id="e3abc-226">cdm_bankaccountdisbursement</span><span class="sxs-lookup"><span data-stu-id="e3abc-226">cdm_bankaccountdisbursement</span></span> |
| <span data-ttu-id="e3abc-227">Skatteregion</span><span class="sxs-lookup"><span data-stu-id="e3abc-227">Tax Region</span></span> | <span data-ttu-id="e3abc-228">cdm_taxregion</span><span class="sxs-lookup"><span data-stu-id="e3abc-228">cdm_taxregion</span></span> |

## <a name="worker-entities"></a><span data-ttu-id="e3abc-229">Entiteter för arbetare</span><span class="sxs-lookup"><span data-stu-id="e3abc-229">Worker entities</span></span>

| <span data-ttu-id="e3abc-230">Namn</span><span class="sxs-lookup"><span data-stu-id="e3abc-230">Name</span></span> | <span data-ttu-id="e3abc-231">Enhet</span><span class="sxs-lookup"><span data-stu-id="e3abc-231">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="e3abc-232">Arbetare</span><span class="sxs-lookup"><span data-stu-id="e3abc-232">Worker</span></span> | <span data-ttu-id="e3abc-233">cdm_worker</span><span class="sxs-lookup"><span data-stu-id="e3abc-233">cdm_worker</span></span> |
| <span data-ttu-id="e3abc-234">Arbetarens adress</span><span class="sxs-lookup"><span data-stu-id="e3abc-234">Worker Address</span></span> | <span data-ttu-id="e3abc-235">cdm_workeraddress</span><span class="sxs-lookup"><span data-stu-id="e3abc-235">cdm_workeraddress</span></span> |
| <span data-ttu-id="e3abc-236">Arbetarens personuppgift</span><span class="sxs-lookup"><span data-stu-id="e3abc-236">Worker Personal Detail</span></span> | <span data-ttu-id="e3abc-237">cdm_workerpersonaldetail</span><span class="sxs-lookup"><span data-stu-id="e3abc-237">cdm_workerpersonaldetail</span></span> |
| <span data-ttu-id="e3abc-238">Arbetsidentifieringsnummer</span><span class="sxs-lookup"><span data-stu-id="e3abc-238">Worker Person Identification Number</span></span> | <span data-ttu-id="e3abc-239">cdm_workerpersonidentificationnumber</span><span class="sxs-lookup"><span data-stu-id="e3abc-239">cdm_workerpersonidentificationnumber</span></span> |
| <span data-ttu-id="e3abc-240">Arbetsidentifieringstyp</span><span class="sxs-lookup"><span data-stu-id="e3abc-240">Worker Person Identification Type</span></span> | <span data-ttu-id="e3abc-241">cdm_workerpersonidentificationtype</span><span class="sxs-lookup"><span data-stu-id="e3abc-241">cdm_workerpersonidentificationtype</span></span> |
| <span data-ttu-id="e3abc-242">Arbetskalender</span><span class="sxs-lookup"><span data-stu-id="e3abc-242">Work Calendar</span></span> | <span data-ttu-id="e3abc-243">cdm_workcalendar</span><span class="sxs-lookup"><span data-stu-id="e3abc-243">cdm_workcalendar</span></span> |
| <span data-ttu-id="e3abc-244">Arbetsdagar i kalendern</span><span class="sxs-lookup"><span data-stu-id="e3abc-244">Work Calendar Day</span></span> | <span data-ttu-id="e3abc-245">cdm_workcalendarday</span><span class="sxs-lookup"><span data-stu-id="e3abc-245">cdm_workcalendarday</span></span> |
| <span data-ttu-id="e3abc-246">Helgdag i arbetskalender</span><span class="sxs-lookup"><span data-stu-id="e3abc-246">Work Calendar Holiday</span></span> |<span data-ttu-id="e3abc-247">cdm_workcalendarholiday</span><span class="sxs-lookup"><span data-stu-id="e3abc-247">cdm_workcalendarholiday</span></span> |
| <span data-ttu-id="e3abc-248">Arbetskalenderns datumrad</span><span class="sxs-lookup"><span data-stu-id="e3abc-248">Work Calendar Holiday Line</span></span> | <span data-ttu-id="e3abc-249">cdm_workcalendarholidayline</span><span class="sxs-lookup"><span data-stu-id="e3abc-249">cdm_workcalendarholidayline</span></span> |
| <span data-ttu-id="e3abc-250">Tidsintervall till arbetskalendern</span><span class="sxs-lookup"><span data-stu-id="e3abc-250">Work Calendar Time Interval</span></span> | <span data-ttu-id="e3abc-251">cdm_workcalendartimeinterval (inte aktiverat för stöd för anpassade fält)</span><span class="sxs-lookup"><span data-stu-id="e3abc-251">cdm_workcalendartimeinterval (Not enabled for custom field support)</span></span> |
| <span data-ttu-id="e3abc-252">Bankkonto för arbetare</span><span class="sxs-lookup"><span data-stu-id="e3abc-252">Worker Bank Account</span></span> | <span data-ttu-id="e3abc-253">cdm_workerbankaccount</span><span class="sxs-lookup"><span data-stu-id="e3abc-253">cdm_workerbankaccount</span></span> |

## <a name="worker-setup-entities"></a><span data-ttu-id="e3abc-254">Enheter för arbetarkonfiguration</span><span class="sxs-lookup"><span data-stu-id="e3abc-254">Worker setup entities</span></span>

| <span data-ttu-id="e3abc-255">Namn</span><span class="sxs-lookup"><span data-stu-id="e3abc-255">Name</span></span> | <span data-ttu-id="e3abc-256">Enhet</span><span class="sxs-lookup"><span data-stu-id="e3abc-256">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="e3abc-257">Veteranstatus</span><span class="sxs-lookup"><span data-stu-id="e3abc-257">Veteran Status</span></span> | <span data-ttu-id="e3abc-258">cdm_veteranstatus</span><span class="sxs-lookup"><span data-stu-id="e3abc-258">cdm_veteranstatus</span></span> |
| <span data-ttu-id="e3abc-259">Etniskt ursprung</span><span class="sxs-lookup"><span data-stu-id="e3abc-259">Ethnic Origin</span></span> | <span data-ttu-id="e3abc-260">cdm_ethnicorigin</span><span class="sxs-lookup"><span data-stu-id="e3abc-260">cdm_ethnicorigin</span></span> |
| <span data-ttu-id="e3abc-261">Orsakskod</span><span class="sxs-lookup"><span data-stu-id="e3abc-261">Reason Code</span></span> | <span data-ttu-id="e3abc-262">cdm_reasoncode</span><span class="sxs-lookup"><span data-stu-id="e3abc-262">cdm_reasoncode</span></span> |
| <span data-ttu-id="e3abc-263">Utfärdande organ personidentifiering</span><span class="sxs-lookup"><span data-stu-id="e3abc-263">Person Identification Issuing Agency</span></span> | <span data-ttu-id="e3abc-264">cdm_personidentificationissuingagency</span><span class="sxs-lookup"><span data-stu-id="e3abc-264">cdm_personidentificationissuingagency</span></span> |

## <a name="competency-entities"></a><span data-ttu-id="e3abc-265">Kompetensenheter</span><span class="sxs-lookup"><span data-stu-id="e3abc-265">Competency entities</span></span>

| <span data-ttu-id="e3abc-266">Namn</span><span class="sxs-lookup"><span data-stu-id="e3abc-266">Name</span></span> | <span data-ttu-id="e3abc-267">Enhet</span><span class="sxs-lookup"><span data-stu-id="e3abc-267">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="e3abc-268">Kompetenstyp</span><span class="sxs-lookup"><span data-stu-id="e3abc-268">Skill Type</span></span> | <span data-ttu-id="e3abc-269">cdm_skilltype</span><span class="sxs-lookup"><span data-stu-id="e3abc-269">cdm_skilltype</span></span> |

## <a name="entity-relationship-models"></a><span data-ttu-id="e3abc-270">Modeller för enhetsrelation</span><span class="sxs-lookup"><span data-stu-id="e3abc-270">Entity relationship models</span></span>

### <a name="worker"></a><span data-ttu-id="e3abc-271">Arbetare</span><span class="sxs-lookup"><span data-stu-id="e3abc-271">Worker</span></span>

![Arbetare](./media/HCMCommon-worker-entity-diagram.png)

### <a name="job-and-job-position"></a><span data-ttu-id="e3abc-273">Jobb och jobbefattning</span><span class="sxs-lookup"><span data-stu-id="e3abc-273">Job and Job Position</span></span>

![Jobb och jobbefattning](./media/HCMCommon-job-and-job-position-entity-diagram.png)

### <a name="benefits"></a><span data-ttu-id="e3abc-275">Fördelar</span><span class="sxs-lookup"><span data-stu-id="e3abc-275">Benefits</span></span>

![Fördelar](./media/HCMCommon-benefits-entity-diagram.png)

### <a name="compensation"></a><span data-ttu-id="e3abc-277">Kompensation</span><span class="sxs-lookup"><span data-stu-id="e3abc-277">Compensation</span></span>

![Kompensation](./media/HCMCommon-compensation-entity-diagram.png)

### <a name="leave"></a><span data-ttu-id="e3abc-279">Lämna</span><span class="sxs-lookup"><span data-stu-id="e3abc-279">Leave</span></span>

![Lämna](./media/HCMCommon-leave-entity-diagram.png)

### <a name="work-calendar"></a><span data-ttu-id="e3abc-281">Arbetskalender</span><span class="sxs-lookup"><span data-stu-id="e3abc-281">Work Calendar</span></span>

![Arbetskalender](./media/HCMCommon-work-calendar-entity-diagram.png)

## <a name="see-also"></a><span data-ttu-id="e3abc-283">Se även</span><span class="sxs-lookup"><span data-stu-id="e3abc-283">See also</span></span>

[<span data-ttu-id="e3abc-284">Välja en dataintegreringsteknik</span><span class="sxs-lookup"><span data-stu-id="e3abc-284">Choose a data integration technology</span></span>](hr-admin-integration-choose-technology.md)</br>
[<span data-ttu-id="e3abc-285">Konfigurera Common Data Service-integrering</span><span class="sxs-lookup"><span data-stu-id="e3abc-285">Configure Common Data Service integration</span></span>](hr-admin-integration-common-data-service.md)
