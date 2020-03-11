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
ms.openlocfilehash: 6879a45dd1fcc1ba718747aaaf0d7936c2eac49f
ms.sourcegitcommit: 3cad15f8ecc257d3a45c1bc1fada7c094ff4bcec
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/26/2020
ms.locfileid: "3087356"
---
# <a name="common-data-service-entities"></a><span data-ttu-id="39792-103">Common Data Service-entiteter</span><span class="sxs-lookup"><span data-stu-id="39792-103">Common Data Service entities</span></span>

<span data-ttu-id="39792-104">Microsoft Dynamics 365 Human Resources använder Common Data Service för att aktivera scenarier för utökning och integration.</span><span class="sxs-lookup"><span data-stu-id="39792-104">Microsoft Dynamics 365 Human Resources uses Common Data Service to enable extensibility and integration scenarios.</span></span>

<span data-ttu-id="39792-105">Mer information om Common Data Service, se [Vad är Common Data Service](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro).</span><span class="sxs-lookup"><span data-stu-id="39792-105">For more information about Common Data Service, see [What is Common Data Service](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro).</span></span>

<span data-ttu-id="39792-106">Följande personalentiteter är tillgängliga i Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="39792-106">The following Human Resources entities are available in Common Data Service.</span></span>

## <a name="benefit-entities"></a><span data-ttu-id="39792-107">Förmånsentiteter</span><span class="sxs-lookup"><span data-stu-id="39792-107">Benefit entities</span></span>

| <span data-ttu-id="39792-108">Namn</span><span class="sxs-lookup"><span data-stu-id="39792-108">Name</span></span> | <span data-ttu-id="39792-109">Enhet</span><span class="sxs-lookup"><span data-stu-id="39792-109">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="39792-110">Frekvens i förmånsberäkning</span><span class="sxs-lookup"><span data-stu-id="39792-110">Benefit Calculation Frequency</span></span> | <span data-ttu-id="39792-111">cdm_benefitcalculationfrequency</span><span class="sxs-lookup"><span data-stu-id="39792-111">cdm_benefitcalculationfrequency</span></span> |
| <span data-ttu-id="39792-112">Löneperiod med frekvens i förmånsberäkning</span><span class="sxs-lookup"><span data-stu-id="39792-112">Benefit Calculation Frequency Pay Period</span></span> | <span data-ttu-id="39792-113">cdm_benefitcalculationfrequencypayperiod</span><span class="sxs-lookup"><span data-stu-id="39792-113">cdm_benefitcalculationfrequencypayperiod</span></span> |
| <span data-ttu-id="39792-114">Tariff för förmånsberäkning</span><span class="sxs-lookup"><span data-stu-id="39792-114">Benefit Calculation Rate</span></span> | <span data-ttu-id="39792-115">cdm_benefitcalculationrate</span><span class="sxs-lookup"><span data-stu-id="39792-115">cdm_benefitcalculationrate</span></span> |
| <span data-ttu-id="39792-116">Uppgift om tariff för förmånsberäkning</span><span class="sxs-lookup"><span data-stu-id="39792-116">Benefit Calculation Rate Detail</span></span> | <span data-ttu-id="39792-117">cdm_benefitcalculationratedetail</span><span class="sxs-lookup"><span data-stu-id="39792-117">cdm_benefitcalculationratedetail</span></span> |
| <span data-ttu-id="39792-118">Förmånsalternativ</span><span class="sxs-lookup"><span data-stu-id="39792-118">Benefit Option</span></span> | <span data-ttu-id="39792-119">cdm_benefitoption</span><span class="sxs-lookup"><span data-stu-id="39792-119">cdm_benefitoption</span></span> |
| <span data-ttu-id="39792-120">Förmånsplan</span><span class="sxs-lookup"><span data-stu-id="39792-120">Benefit Plan</span></span> | <span data-ttu-id="39792-121">cdm_benefitplan (inte aktiverat för stöd för anpassade fält)</span><span class="sxs-lookup"><span data-stu-id="39792-121">cdm_benefitplan (Not enabled for custom field support)</span></span> |
| <span data-ttu-id="39792-122">Förmånstyp</span><span class="sxs-lookup"><span data-stu-id="39792-122">Benefit Type</span></span> | <span data-ttu-id="39792-123">cdm_benefittype</span><span class="sxs-lookup"><span data-stu-id="39792-123">cdm_benefittype</span></span> |

## <a name="business-process-tasks-entities"></a><span data-ttu-id="39792-124">Entiteter för affärsprocessuppgifter</span><span class="sxs-lookup"><span data-stu-id="39792-124">Business process tasks entities</span></span>

| <span data-ttu-id="39792-125">Namn</span><span class="sxs-lookup"><span data-stu-id="39792-125">Name</span></span> | <span data-ttu-id="39792-126">Enhet</span><span class="sxs-lookup"><span data-stu-id="39792-126">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="39792-127">Affärsprocesskalender</span><span class="sxs-lookup"><span data-stu-id="39792-127">Business Process Calendar</span></span> | <span data-ttu-id="39792-128">cdm_businessprocesscalendar</span><span class="sxs-lookup"><span data-stu-id="39792-128">cdm_businessprocesscalendar</span></span> |
| <span data-ttu-id="39792-129">Tilldelning av affärsprocessgrupp</span><span class="sxs-lookup"><span data-stu-id="39792-129">Business Process Group Assignment</span></span> | <span data-ttu-id="39792-130">cdm_businessprocessgroupassignment</span><span class="sxs-lookup"><span data-stu-id="39792-130">cdm_businessprocessgroupassignment</span></span> |
| <span data-ttu-id="39792-131">Affärsprocessbibliotekets uppgiftsgrupp</span><span class="sxs-lookup"><span data-stu-id="39792-131">Business Process Library Task Group</span></span> | <span data-ttu-id="39792-132">cdm_businessprocesslibrarytaskgroup</span><span class="sxs-lookup"><span data-stu-id="39792-132">cdm_businessprocesslibrarytaskgroup</span></span> |
| <span data-ttu-id="39792-133">Affärsprocessfas</span><span class="sxs-lookup"><span data-stu-id="39792-133">Business Process Stage</span></span> | <span data-ttu-id="39792-134">cdm_businessprocessstage</span><span class="sxs-lookup"><span data-stu-id="39792-134">cdm_businessprocessstage</span></span> |
| <span data-ttu-id="39792-135">Checklistemallens rubrik</span><span class="sxs-lookup"><span data-stu-id="39792-135">Checklist Template Header</span></span> | <span data-ttu-id="39792-136">cdm_businessprocesstemplateheader</span><span class="sxs-lookup"><span data-stu-id="39792-136">cdm_businessprocesstemplateheader</span></span> |
| <span data-ttu-id="39792-137">Checklistemallens uppgift</span><span class="sxs-lookup"><span data-stu-id="39792-137">Checklist Template Task</span></span> | <span data-ttu-id="39792-138">cdm_businessprocesstemplatetask</span><span class="sxs-lookup"><span data-stu-id="39792-138">cdm_businessprocesstemplatetask</span></span> |

## <a name="compensation-entities"></a><span data-ttu-id="39792-139">Enheter för kompensation</span><span class="sxs-lookup"><span data-stu-id="39792-139">Compensation entities</span></span>

| <span data-ttu-id="39792-140">Namn</span><span class="sxs-lookup"><span data-stu-id="39792-140">Name</span></span> | <span data-ttu-id="39792-141">Enhet</span><span class="sxs-lookup"><span data-stu-id="39792-141">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="39792-142">Plan för fast kompensation</span><span class="sxs-lookup"><span data-stu-id="39792-142">Compensation Fixed Plan</span></span> | <span data-ttu-id="39792-143">cdm_compensationfixedplan</span><span class="sxs-lookup"><span data-stu-id="39792-143">cdm_compensationfixedplan</span></span> |
| <span data-ttu-id="39792-144">Kompensationsrutnät</span><span class="sxs-lookup"><span data-stu-id="39792-144">Compensation Grid</span></span> | <span data-ttu-id="39792-145">cdm_compensationgrid</span><span class="sxs-lookup"><span data-stu-id="39792-145">cdm_compensationgrid</span></span> |
| <span data-ttu-id="39792-146">Kompensationsnivå</span><span class="sxs-lookup"><span data-stu-id="39792-146">Compensation Level</span></span> | <span data-ttu-id="39792-147">cdm_compensationlevel</span><span class="sxs-lookup"><span data-stu-id="39792-147">cdm_compensationlevel</span></span> |
| <span data-ttu-id="39792-148">Lönefrekvens för kompensation</span><span class="sxs-lookup"><span data-stu-id="39792-148">Compensation Pay Frequency</span></span> | <span data-ttu-id="39792-149">cdm_compensationpayfrequency</span><span class="sxs-lookup"><span data-stu-id="39792-149">cdm_compensationpayfrequency</span></span> |
| <span data-ttu-id="39792-150">Kompensationsreferenspunkt</span><span class="sxs-lookup"><span data-stu-id="39792-150">Compensation Reference Point Setup</span></span> | <span data-ttu-id="39792-151">cdm_compensationreferencepointsetup</span><span class="sxs-lookup"><span data-stu-id="39792-151">cdm_compensationreferencepointsetup</span></span> |
| <span data-ttu-id="39792-152">Ställ in kompensationsreferenspunkt</span><span class="sxs-lookup"><span data-stu-id="39792-152">Compensation Reference Point Setup Line</span></span> | <span data-ttu-id="39792-153">cdm_compensationreferencepointsetupline</span><span class="sxs-lookup"><span data-stu-id="39792-153">cdm_compensationreferencepointsetupline</span></span> |
| <span data-ttu-id="39792-154">Kompensationsregion</span><span class="sxs-lookup"><span data-stu-id="39792-154">Compensation Region</span></span> | <span data-ttu-id="39792-155">cdm_compensationregion</span><span class="sxs-lookup"><span data-stu-id="39792-155">cdm_compensationregion</span></span> |
| <span data-ttu-id="39792-156">Kompensationsstruktur</span><span class="sxs-lookup"><span data-stu-id="39792-156">Compensation Structure</span></span> | <span data-ttu-id="39792-157">cdm_compensationstructure</span><span class="sxs-lookup"><span data-stu-id="39792-157">cdm_compensationstructure</span></span> |
| <span data-ttu-id="39792-158">Variabel kompensationsplan</span><span class="sxs-lookup"><span data-stu-id="39792-158">Compensation Variable Plan</span></span> | <span data-ttu-id="39792-159">cdm_compensationvariableplan</span><span class="sxs-lookup"><span data-stu-id="39792-159">cdm_compensationvariableplan</span></span> |
| <span data-ttu-id="39792-160">Variabel kompensationsplannivå</span><span class="sxs-lookup"><span data-stu-id="39792-160">Compensation Variable Plan Level</span></span> | <span data-ttu-id="39792-161">cdm_compensationvariableplanlevel</span><span class="sxs-lookup"><span data-stu-id="39792-161">cdm_compensationvariableplanlevel</span></span> |
| <span data-ttu-id="39792-162">Typ av variabel kompensationsplan</span><span class="sxs-lookup"><span data-stu-id="39792-162">Compensation Variable Plan Type</span></span> | <span data-ttu-id="39792-163">cdm_compensationvariableplantype</span><span class="sxs-lookup"><span data-stu-id="39792-163">cdm_compensationvariableplantype</span></span> |
| <span data-ttu-id="39792-164">Händelse för fast kompensation</span><span class="sxs-lookup"><span data-stu-id="39792-164">Fixed Compensation Event</span></span> | <span data-ttu-id="39792-165">cdm_fixedcompensationevent</span><span class="sxs-lookup"><span data-stu-id="39792-165">cdm_fixedcompensationevent</span></span> |
| <span data-ttu-id="39792-166">Överlåtelseregel</span><span class="sxs-lookup"><span data-stu-id="39792-166">Vesting Rule</span></span> | <span data-ttu-id="39792-167">cdm_vestingrule</span><span class="sxs-lookup"><span data-stu-id="39792-167">cdm_vestingrule</span></span> |
| <span data-ttu-id="39792-168">Fast arbetarkompensation</span><span class="sxs-lookup"><span data-stu-id="39792-168">Worker Fixed Compensation</span></span> | <span data-ttu-id="39792-169">cdm_workerfixedcompensation</span><span class="sxs-lookup"><span data-stu-id="39792-169">cdm_workerfixedcompensation</span></span> |

## <a name="organization-entities"></a><span data-ttu-id="39792-170">Organisationsenheter</span><span class="sxs-lookup"><span data-stu-id="39792-170">Organization entities</span></span>

| <span data-ttu-id="39792-171">Namn</span><span class="sxs-lookup"><span data-stu-id="39792-171">Name</span></span> | <span data-ttu-id="39792-172">Enhet</span><span class="sxs-lookup"><span data-stu-id="39792-172">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="39792-173">Avdelning</span><span class="sxs-lookup"><span data-stu-id="39792-173">Department</span></span> | <span data-ttu-id="39792-174">cdm_department</span><span class="sxs-lookup"><span data-stu-id="39792-174">cdm_department</span></span> |
| <span data-ttu-id="39792-175">Anställning</span><span class="sxs-lookup"><span data-stu-id="39792-175">Employment</span></span> | <span data-ttu-id="39792-176">cdm_employment</span><span class="sxs-lookup"><span data-stu-id="39792-176">cdm_employment</span></span> |
| <span data-ttu-id="39792-177">Företag</span><span class="sxs-lookup"><span data-stu-id="39792-177">Company</span></span> | <span data-ttu-id="39792-178">cdm_company</span><span class="sxs-lookup"><span data-stu-id="39792-178">cdm_company</span></span> |
| <span data-ttu-id="39792-179">Befattning</span><span class="sxs-lookup"><span data-stu-id="39792-179">Job</span></span> | <span data-ttu-id="39792-180">cdm_job</span><span class="sxs-lookup"><span data-stu-id="39792-180">cdm_job</span></span> |
| <span data-ttu-id="39792-181">Jobbfunktion</span><span class="sxs-lookup"><span data-stu-id="39792-181">Job Function</span></span> | <span data-ttu-id="39792-182">cdm_jobfunction</span><span class="sxs-lookup"><span data-stu-id="39792-182">cdm_jobfunction</span></span> |
| <span data-ttu-id="39792-183">Befattning</span><span class="sxs-lookup"><span data-stu-id="39792-183">Job Position</span></span> | <span data-ttu-id="39792-184">cdm_jobposition</span><span class="sxs-lookup"><span data-stu-id="39792-184">cdm_jobposition</span></span> |
| <span data-ttu-id="39792-185">Befattningstyp</span><span class="sxs-lookup"><span data-stu-id="39792-185">Position Type</span></span> | <span data-ttu-id="39792-186">cdm_positiontype</span><span class="sxs-lookup"><span data-stu-id="39792-186">cdm_positiontype</span></span> |
| <span data-ttu-id="39792-187">Befattningstilldelning för arbetare</span><span class="sxs-lookup"><span data-stu-id="39792-187">Position Worker Assignment</span></span> | <span data-ttu-id="39792-188">cdm_positionworkerassignmentmap</span><span class="sxs-lookup"><span data-stu-id="39792-188">cdm_positionworkerassignmentmap</span></span> |
| <span data-ttu-id="39792-189">Jobbtyp</span><span class="sxs-lookup"><span data-stu-id="39792-189">Job Type</span></span> | <span data-ttu-id="39792-190">cdm_jobtype</span><span class="sxs-lookup"><span data-stu-id="39792-190">cdm_jobtype</span></span> |
| <span data-ttu-id="39792-191">Språk</span><span class="sxs-lookup"><span data-stu-id="39792-191">Language</span></span> | <span data-ttu-id="39792-192">cdm_language</span><span class="sxs-lookup"><span data-stu-id="39792-192">cdm_language</span></span> |

## <a name="leave-and-absence-entities"></a><span data-ttu-id="39792-193">Enheter för tjänstledighet och frånvaro</span><span class="sxs-lookup"><span data-stu-id="39792-193">Leave and absence entities</span></span>

| <span data-ttu-id="39792-194">Namn</span><span class="sxs-lookup"><span data-stu-id="39792-194">Name</span></span> | <span data-ttu-id="39792-195">Enhet</span><span class="sxs-lookup"><span data-stu-id="39792-195">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="39792-196">Lämna banktransaktion</span><span class="sxs-lookup"><span data-stu-id="39792-196">Leave Bank Transaction</span></span> | <span data-ttu-id="39792-197">cdm_leavebanktransaction</span><span class="sxs-lookup"><span data-stu-id="39792-197">cdm_leavebanktransaction</span></span> |
| <span data-ttu-id="39792-198">Lämna anmälan</span><span class="sxs-lookup"><span data-stu-id="39792-198">Leave Enrollment</span></span> | <span data-ttu-id="39792-199">cdm_leaveenrollment</span><span class="sxs-lookup"><span data-stu-id="39792-199">cdm_leaveenrollment</span></span> |
| <span data-ttu-id="39792-200">Tjänstledighetsplan</span><span class="sxs-lookup"><span data-stu-id="39792-200">Leave Plan</span></span> | <span data-ttu-id="39792-201">cdm_leaveplan</span><span class="sxs-lookup"><span data-stu-id="39792-201">cdm_leaveplan</span></span> |
| <span data-ttu-id="39792-202">Begäran om tjänstledighet</span><span class="sxs-lookup"><span data-stu-id="39792-202">Leave Request</span></span> | <span data-ttu-id="39792-203">cdm_leaverequest</span><span class="sxs-lookup"><span data-stu-id="39792-203">cdm_leaverequest</span></span> |
| <span data-ttu-id="39792-204">Information om att lämna begäran</span><span class="sxs-lookup"><span data-stu-id="39792-204">Leave Request Detail</span></span> | <span data-ttu-id="39792-205">cdm_leaverequestdetail</span><span class="sxs-lookup"><span data-stu-id="39792-205">cdm_leaverequestdetail</span></span> |
| <span data-ttu-id="39792-206">Tjänstledighetstyp</span><span class="sxs-lookup"><span data-stu-id="39792-206">Leave Type</span></span> | <span data-ttu-id="39792-207">cdm_leavetype</span><span class="sxs-lookup"><span data-stu-id="39792-207">cdm_leavetype</span></span> |
| <span data-ttu-id="39792-208">Ledighetstypens orsakskod</span><span class="sxs-lookup"><span data-stu-id="39792-208">Leave Type Reason Code</span></span> | <span data-ttu-id="39792-209">cdm_leavetypereasoncode</span><span class="sxs-lookup"><span data-stu-id="39792-209">cdm_leavetypereasoncode</span></span> |

## <a name="payroll-entities"></a><span data-ttu-id="39792-210">Löneenheter</span><span class="sxs-lookup"><span data-stu-id="39792-210">Payroll entities</span></span>

| <span data-ttu-id="39792-211">Namn</span><span class="sxs-lookup"><span data-stu-id="39792-211">Name</span></span> | <span data-ttu-id="39792-212">Enhet</span><span class="sxs-lookup"><span data-stu-id="39792-212">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="39792-213">Lönecykel</span><span class="sxs-lookup"><span data-stu-id="39792-213">Pay Cycle</span></span> | <span data-ttu-id="39792-214">cdm_paycycle</span><span class="sxs-lookup"><span data-stu-id="39792-214">cdm_paycycle</span></span> |
| <span data-ttu-id="39792-215">Löneperiod</span><span class="sxs-lookup"><span data-stu-id="39792-215">Pay Period</span></span> | <span data-ttu-id="39792-216">cdm_payperiod</span><span class="sxs-lookup"><span data-stu-id="39792-216">cdm_payperiod</span></span> |
| <span data-ttu-id="39792-217">Inkomstkod för lön</span><span class="sxs-lookup"><span data-stu-id="39792-217">Payroll Earning Code</span></span> | <span data-ttu-id="39792-218">cdm_payrollearningcode</span><span class="sxs-lookup"><span data-stu-id="39792-218">cdm_payrollearningcode</span></span> |
| <span data-ttu-id="39792-219">Bankkontoutbetalningar</span><span class="sxs-lookup"><span data-stu-id="39792-219">Bank Account Disbursement</span></span> | <span data-ttu-id="39792-220">cdm_bankaccountdisbursement</span><span class="sxs-lookup"><span data-stu-id="39792-220">cdm_bankaccountdisbursement</span></span> |
| <span data-ttu-id="39792-221">Skatteregion</span><span class="sxs-lookup"><span data-stu-id="39792-221">Tax Region</span></span> | <span data-ttu-id="39792-222">cdm_taxregion</span><span class="sxs-lookup"><span data-stu-id="39792-222">cdm_taxregion</span></span> |

## <a name="worker-entities"></a><span data-ttu-id="39792-223">Entiteter för arbetare</span><span class="sxs-lookup"><span data-stu-id="39792-223">Worker entities</span></span>

| <span data-ttu-id="39792-224">Namn</span><span class="sxs-lookup"><span data-stu-id="39792-224">Name</span></span> | <span data-ttu-id="39792-225">Enhet</span><span class="sxs-lookup"><span data-stu-id="39792-225">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="39792-226">Arbetare</span><span class="sxs-lookup"><span data-stu-id="39792-226">Worker</span></span> | <span data-ttu-id="39792-227">cdm_worker</span><span class="sxs-lookup"><span data-stu-id="39792-227">cdm_worker</span></span> |
| <span data-ttu-id="39792-228">Arbetarens adress</span><span class="sxs-lookup"><span data-stu-id="39792-228">Worker Address</span></span> | <span data-ttu-id="39792-229">cdm_workeraddress</span><span class="sxs-lookup"><span data-stu-id="39792-229">cdm_workeraddress</span></span> |
| <span data-ttu-id="39792-230">Arbetarens personuppgift</span><span class="sxs-lookup"><span data-stu-id="39792-230">Worker Personal Detail</span></span> | <span data-ttu-id="39792-231">cdm_workerpersonaldetail</span><span class="sxs-lookup"><span data-stu-id="39792-231">cdm_workerpersonaldetail</span></span> |
| <span data-ttu-id="39792-232">Arbetsidentifieringsnummer</span><span class="sxs-lookup"><span data-stu-id="39792-232">Worker Person Identification Number</span></span> | <span data-ttu-id="39792-233">cdm_workerpersonidentificationnumber</span><span class="sxs-lookup"><span data-stu-id="39792-233">cdm_workerpersonidentificationnumber</span></span> |
| <span data-ttu-id="39792-234">Arbetsidentifieringstyp</span><span class="sxs-lookup"><span data-stu-id="39792-234">Worker Person Identification Type</span></span> | <span data-ttu-id="39792-235">cdm_workerpersonidentificationtype</span><span class="sxs-lookup"><span data-stu-id="39792-235">cdm_workerpersonidentificationtype</span></span> |
| <span data-ttu-id="39792-236">Arbetskalender</span><span class="sxs-lookup"><span data-stu-id="39792-236">Work Calendar</span></span> | <span data-ttu-id="39792-237">cdm_workcalendar</span><span class="sxs-lookup"><span data-stu-id="39792-237">cdm_workcalendar</span></span> |
| <span data-ttu-id="39792-238">Arbetsdagar i kalendern</span><span class="sxs-lookup"><span data-stu-id="39792-238">Work Calendar Day</span></span> | <span data-ttu-id="39792-239">cdm_workcalendarday</span><span class="sxs-lookup"><span data-stu-id="39792-239">cdm_workcalendarday</span></span> |
| <span data-ttu-id="39792-240">Helgdag i arbetskalender</span><span class="sxs-lookup"><span data-stu-id="39792-240">Work Calendar Holiday</span></span> |<span data-ttu-id="39792-241">cdm_workcalendarholiday</span><span class="sxs-lookup"><span data-stu-id="39792-241">cdm_workcalendarholiday</span></span> |
| <span data-ttu-id="39792-242">Arbetskalenderns datumrad</span><span class="sxs-lookup"><span data-stu-id="39792-242">Work Calendar Holiday Line</span></span> | <span data-ttu-id="39792-243">cdm_workcalendarholidayline</span><span class="sxs-lookup"><span data-stu-id="39792-243">cdm_workcalendarholidayline</span></span> |
| <span data-ttu-id="39792-244">Tidsintervall till arbetskalendern</span><span class="sxs-lookup"><span data-stu-id="39792-244">Work Calendar Time Interval</span></span> | <span data-ttu-id="39792-245">cdm_workcalendartimeinterval (inte aktiverat för stöd för anpassade fält)</span><span class="sxs-lookup"><span data-stu-id="39792-245">cdm_workcalendartimeinterval (Not enabled for custom field support)</span></span> |
| <span data-ttu-id="39792-246">Bankkonto för arbetare</span><span class="sxs-lookup"><span data-stu-id="39792-246">Worker Bank Account</span></span> | <span data-ttu-id="39792-247">cdm_workerbankaccount</span><span class="sxs-lookup"><span data-stu-id="39792-247">cdm_workerbankaccount</span></span> |

## <a name="worker-setup-entities"></a><span data-ttu-id="39792-248">Enheter för arbetarkonfiguration</span><span class="sxs-lookup"><span data-stu-id="39792-248">Worker setup entities</span></span>

| <span data-ttu-id="39792-249">Namn</span><span class="sxs-lookup"><span data-stu-id="39792-249">Name</span></span> | <span data-ttu-id="39792-250">Enhet</span><span class="sxs-lookup"><span data-stu-id="39792-250">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="39792-251">Veteranstatus</span><span class="sxs-lookup"><span data-stu-id="39792-251">Veteran Status</span></span> | <span data-ttu-id="39792-252">cdm_veteranstatus</span><span class="sxs-lookup"><span data-stu-id="39792-252">cdm_veteranstatus</span></span> |
| <span data-ttu-id="39792-253">Etniskt ursprung</span><span class="sxs-lookup"><span data-stu-id="39792-253">Ethnic Origin</span></span> | <span data-ttu-id="39792-254">cdm_ethnicorigin</span><span class="sxs-lookup"><span data-stu-id="39792-254">cdm_ethnicorigin</span></span> |
| <span data-ttu-id="39792-255">Orsakskod</span><span class="sxs-lookup"><span data-stu-id="39792-255">Reason Code</span></span> | <span data-ttu-id="39792-256">cdm_reasoncode</span><span class="sxs-lookup"><span data-stu-id="39792-256">cdm_reasoncode</span></span> |
| <span data-ttu-id="39792-257">Utfärdande organ personidentifiering</span><span class="sxs-lookup"><span data-stu-id="39792-257">Person Identification Issuing Agency</span></span> | <span data-ttu-id="39792-258">cdm_personidentificationissuingagency</span><span class="sxs-lookup"><span data-stu-id="39792-258">cdm_personidentificationissuingagency</span></span> |

## <a name="competency-entities"></a><span data-ttu-id="39792-259">Kompetensenheter</span><span class="sxs-lookup"><span data-stu-id="39792-259">Competency entities</span></span>

| <span data-ttu-id="39792-260">Namn</span><span class="sxs-lookup"><span data-stu-id="39792-260">Name</span></span> | <span data-ttu-id="39792-261">Enhet</span><span class="sxs-lookup"><span data-stu-id="39792-261">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="39792-262">Kompetenstyp</span><span class="sxs-lookup"><span data-stu-id="39792-262">Skill Type</span></span> | <span data-ttu-id="39792-263">cdm_skilltype</span><span class="sxs-lookup"><span data-stu-id="39792-263">cdm_skilltype</span></span> |

## <a name="entity-relationship-models"></a><span data-ttu-id="39792-264">Modeller för enhetsrelation</span><span class="sxs-lookup"><span data-stu-id="39792-264">Entity relationship models</span></span>

### <a name="worker"></a><span data-ttu-id="39792-265">Arbetare</span><span class="sxs-lookup"><span data-stu-id="39792-265">Worker</span></span>

![Arbetare](./media/HCMCommon-worker-entity-diagram.png)

### <a name="job-and-job-position"></a><span data-ttu-id="39792-267">Jobb och jobbefattning</span><span class="sxs-lookup"><span data-stu-id="39792-267">Job and Job Position</span></span>

![Jobb och jobbefattning](./media/HCMCommon-job-and-job-position-entity-diagram.png)

### <a name="benefits"></a><span data-ttu-id="39792-269">Fördelar</span><span class="sxs-lookup"><span data-stu-id="39792-269">Benefits</span></span>

![Fördelar](./media/HCMCommon-benefits-entity-diagram.png)

### <a name="compensation"></a><span data-ttu-id="39792-271">Kompensation</span><span class="sxs-lookup"><span data-stu-id="39792-271">Compensation</span></span>

![Kompensation](./media/HCMCommon-compensation-entity-diagram.png)

### <a name="leave"></a><span data-ttu-id="39792-273">Lämna</span><span class="sxs-lookup"><span data-stu-id="39792-273">Leave</span></span>

![Lämna](./media/HCMCommon-leave-entity-diagram.png)

### <a name="work-calendar"></a><span data-ttu-id="39792-275">Arbetskalender</span><span class="sxs-lookup"><span data-stu-id="39792-275">Work Calendar</span></span>

![Arbetskalender](./media/HCMCommon-work-calendar-entity-diagram.png)

## <a name="see-also"></a><span data-ttu-id="39792-277">Se även</span><span class="sxs-lookup"><span data-stu-id="39792-277">See also</span></span>

[<span data-ttu-id="39792-278">Välja en dataintegreringsteknik</span><span class="sxs-lookup"><span data-stu-id="39792-278">Choose a data integration technology</span></span>](hr-admin-integration-choose-technology.md)</br>
[<span data-ttu-id="39792-279">Konfigurera Common Data Service-integrering</span><span class="sxs-lookup"><span data-stu-id="39792-279">Configure Common Data Service integration</span></span>](hr-admin-integration-common-data-service.md)