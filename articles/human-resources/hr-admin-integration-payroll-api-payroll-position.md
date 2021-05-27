---
title: Löneuppgifter för Positioner
description: Detta ämne tillhandahåller information och en exempelfrågeställning för entiteten för löneuppgifter för positioner i Dynamics 365 Human Resources.
author: jcart
ms.date: 04/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2021-04-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 7b23ac5d11b18c77109be21afe1570755dccba20
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6019332"
---
# <a name="payroll-position"></a><span data-ttu-id="b2ac1-103">Lönebefattning</span><span class="sxs-lookup"><span data-stu-id="b2ac1-103">Payroll position</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="b2ac1-104">Detta ämne tillhandahåller information och en exempelfrågeställning för entiteten för löneuppgifter för positioner i Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="b2ac1-104">This topic provides details and an example query for the Payroll details for the Positions entity in Dynamics 365 Human Resources.</span></span>

## <a name="properties"></a><span data-ttu-id="b2ac1-105">Egenskaper</span><span class="sxs-lookup"><span data-stu-id="b2ac1-105">Properties</span></span>

| <span data-ttu-id="b2ac1-106">Egenskap</span><span class="sxs-lookup"><span data-stu-id="b2ac1-106">Property</span></span><br><span data-ttu-id="b2ac1-107">**Fysiskt namn**</span><span class="sxs-lookup"><span data-stu-id="b2ac1-107">**Physical name**</span></span><br><span data-ttu-id="b2ac1-108">**_Typ_**</span><span class="sxs-lookup"><span data-stu-id="b2ac1-108">**_Type_**</span></span> | <span data-ttu-id="b2ac1-109">Använd</span><span class="sxs-lookup"><span data-stu-id="b2ac1-109">Use</span></span> | <span data-ttu-id="b2ac1-110">beskrivning</span><span class="sxs-lookup"><span data-stu-id="b2ac1-110">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="b2ac1-111">**Ordinarie timmar per år**</span><span class="sxs-lookup"><span data-stu-id="b2ac1-111">**Annual regular hours**</span></span><br><span data-ttu-id="b2ac1-112">annualregularhours</span><span class="sxs-lookup"><span data-stu-id="b2ac1-112">annualregularhours</span></span><br><span data-ttu-id="b2ac1-113">*Decimal*</span><span class="sxs-lookup"><span data-stu-id="b2ac1-113">*Decimal*</span></span> | <span data-ttu-id="b2ac1-114">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="b2ac1-114">Read-only</span></span><br><span data-ttu-id="b2ac1-115">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="b2ac1-115">Required</span></span> | <span data-ttu-id="b2ac1-116">Årligt antal regelbundna timmar som definierats för befattningen.</span><span class="sxs-lookup"><span data-stu-id="b2ac1-116">Annual regular hours defined on the position.</span></span>  |
| <span data-ttu-id="b2ac1-117">**Entitets-ID för information om löneposition**</span><span class="sxs-lookup"><span data-stu-id="b2ac1-117">**Payroll position details entity ID**</span></span><br><span data-ttu-id="b2ac1-118">payrollpositiondetailsentityid</span><span class="sxs-lookup"><span data-stu-id="b2ac1-118">payrollpositiondetailsentityid</span></span><br><span data-ttu-id="b2ac1-119">*Guid*</span><span class="sxs-lookup"><span data-stu-id="b2ac1-119">*Guid*</span></span> | <span data-ttu-id="b2ac1-120">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="b2ac1-120">Required</span></span><br><span data-ttu-id="b2ac1-121">Systemgenererat.</span><span class="sxs-lookup"><span data-stu-id="b2ac1-121">System generated.</span></span> | <span data-ttu-id="b2ac1-122">Ett systemgenererat GUID-värde som unikt identifierar positionen.</span><span class="sxs-lookup"><span data-stu-id="b2ac1-122">A system-generated GUID value to uniquely identify the position.</span></span>  |
| <span data-ttu-id="b2ac1-123">**Primärt fält**</span><span class="sxs-lookup"><span data-stu-id="b2ac1-123">**Primary field**</span></span><br><span data-ttu-id="b2ac1-124">mshr_primaryfield</span><span class="sxs-lookup"><span data-stu-id="b2ac1-124">mshr_primaryfield</span></span><br><span data-ttu-id="b2ac1-125">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="b2ac1-125">*String*</span></span> | <span data-ttu-id="b2ac1-126">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="b2ac1-126">Required</span></span><br><span data-ttu-id="b2ac1-127">Systemgenererad</span><span class="sxs-lookup"><span data-stu-id="b2ac1-127">System generated</span></span> |  |
| <span data-ttu-id="b2ac1-128">**ID-värde för befattningsjobb**</span><span class="sxs-lookup"><span data-stu-id="b2ac1-128">**Position job ID value**</span></span><br><span data-ttu-id="b2ac1-129">_mshr_fk_positionjob_id_value</span><span class="sxs-lookup"><span data-stu-id="b2ac1-129">_mshr_fk_positionjob_id_value</span></span><br><span data-ttu-id="b2ac1-130">*GUID*</span><span class="sxs-lookup"><span data-stu-id="b2ac1-130">*GUID*</span></span> | <span data-ttu-id="b2ac1-131">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="b2ac1-131">Read-only</span></span><br><span data-ttu-id="b2ac1-132">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="b2ac1-132">Required</span></span><br><span data-ttu-id="b2ac1-133">Sekundärnyckel:mshr_PayrollPositionJobEntity för mshr_payrollpositionjobentity</span><span class="sxs-lookup"><span data-stu-id="b2ac1-133">Foreign key:mshr_PayrollPositionJobEntity of the mshr_payrollpositionjobentity</span></span> |<span data-ttu-id="b2ac1-134">ID för det jobb som är kopplat till befattningen.</span><span class="sxs-lookup"><span data-stu-id="b2ac1-134">The ID of the job associated with the position.</span></span>|
| <span data-ttu-id="b2ac1-135">**ID-värde för fast kompensationsplan**</span><span class="sxs-lookup"><span data-stu-id="b2ac1-135">**Fixed compensation plan ID value**</span></span><br><span data-ttu-id="b2ac1-136">_mshr_fk_fixedcompplan_id_value</span><span class="sxs-lookup"><span data-stu-id="b2ac1-136">_mshr_fk_fixedcompplan_id_value</span></span><br><span data-ttu-id="b2ac1-137">*GUID*</span><span class="sxs-lookup"><span data-stu-id="b2ac1-137">*GUID*</span></span> | <span data-ttu-id="b2ac1-138">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="b2ac1-138">Read-only</span></span><br><span data-ttu-id="b2ac1-139">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="b2ac1-139">Required</span></span><br><span data-ttu-id="b2ac1-140">Sekundärnyckel: mshr_FixedCompPlan_id för mshr_payrollfixedcompensationplanentity</span><span class="sxs-lookup"><span data-stu-id="b2ac1-140">Foreign key: mshr_FixedCompPlan_id of mshr_payrollfixedcompensationplanentity</span></span>  | <span data-ttu-id="b2ac1-141">ID för den fasta kompensationsplan som är kopplad till befattningen.</span><span class="sxs-lookup"><span data-stu-id="b2ac1-141">The ID of the fixed compensation plan associated with the position.</span></span> |
| <span data-ttu-id="b2ac1-142">**ID för lönecykel**</span><span class="sxs-lookup"><span data-stu-id="b2ac1-142">**Pay cycle ID**</span></span><br><span data-ttu-id="b2ac1-143">mshr_primaryfield</span><span class="sxs-lookup"><span data-stu-id="b2ac1-143">mshr_primaryfield</span></span><br><span data-ttu-id="b2ac1-144">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="b2ac1-144">*String*</span></span> | <span data-ttu-id="b2ac1-145">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="b2ac1-145">Read-only</span></span><br><span data-ttu-id="b2ac1-146">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="b2ac1-146">Required</span></span> | <span data-ttu-id="b2ac1-147">Lönecykeln som definieras för befattningen.</span><span class="sxs-lookup"><span data-stu-id="b2ac1-147">The pay cycle defined on the position.</span></span> |
| <span data-ttu-id="b2ac1-148">**Betalas av den juridiska personen**</span><span class="sxs-lookup"><span data-stu-id="b2ac1-148">**Paid by legal entity**</span></span><br><span data-ttu-id="b2ac1-149">paidbylegalentity</span><span class="sxs-lookup"><span data-stu-id="b2ac1-149">paidbylegalentity</span></span><br><span data-ttu-id="b2ac1-150">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="b2ac1-150">*String*</span></span> | <span data-ttu-id="b2ac1-151">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="b2ac1-151">Read-only</span></span><br><span data-ttu-id="b2ac1-152">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="b2ac1-152">Required</span></span> | <span data-ttu-id="b2ac1-153">Den juridiska person som definieras i befattningen som ansvarar för utfärdande av betalning.</span><span class="sxs-lookup"><span data-stu-id="b2ac1-153">The legal entity defined on the positoin responsible for issuing payment.</span></span> |
| <span data-ttu-id="b2ac1-154">**Befattnings-ID**</span><span class="sxs-lookup"><span data-stu-id="b2ac1-154">**Position ID**</span></span><br><span data-ttu-id="b2ac1-155">mshr_positionid</span><span class="sxs-lookup"><span data-stu-id="b2ac1-155">mshr_positionid</span></span><br><span data-ttu-id="b2ac1-156">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="b2ac1-156">*String*</span></span> | <span data-ttu-id="b2ac1-157">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="b2ac1-157">Read-only</span></span><br><span data-ttu-id="b2ac1-158">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="b2ac1-158">Required</span></span> | <span data-ttu-id="b2ac1-159">Befattningens ID.</span><span class="sxs-lookup"><span data-stu-id="b2ac1-159">The ID of the position.</span></span> |
| <span data-ttu-id="b2ac1-160">**Giltig till**</span><span class="sxs-lookup"><span data-stu-id="b2ac1-160">**Valid to**</span></span><br><span data-ttu-id="b2ac1-161">validto</span><span class="sxs-lookup"><span data-stu-id="b2ac1-161">validto</span></span><br><span data-ttu-id="b2ac1-162">*Datum Tid Offset*</span><span class="sxs-lookup"><span data-stu-id="b2ac1-162">*Date Time Offset*</span></span> | <span data-ttu-id="b2ac1-163">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="b2ac1-163">Read-only</span></span><br><span data-ttu-id="b2ac1-164">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="b2ac1-164">Required</span></span> |<span data-ttu-id="b2ac1-165">Det datum befattningsinformationen gäller från.</span><span class="sxs-lookup"><span data-stu-id="b2ac1-165">The date the position details are valid from.</span></span>  |
| <span data-ttu-id="b2ac1-166">**Giltig från**</span><span class="sxs-lookup"><span data-stu-id="b2ac1-166">**Valid from**</span></span><br><span data-ttu-id="b2ac1-167">validfrom</span><span class="sxs-lookup"><span data-stu-id="b2ac1-167">validfrom</span></span><br><span data-ttu-id="b2ac1-168">*Datum Tid Offset*</span><span class="sxs-lookup"><span data-stu-id="b2ac1-168">*Date Time Offset*</span></span> | <span data-ttu-id="b2ac1-169">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="b2ac1-169">Read-only</span></span><br><span data-ttu-id="b2ac1-170">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="b2ac1-170">Required</span></span> |<span data-ttu-id="b2ac1-171">Det datum befattningsinformationen gäller till.</span><span class="sxs-lookup"><span data-stu-id="b2ac1-171">The date the position details are valid to.</span></span>  |

<span data-ttu-id="b2ac1-172">**Fråga**</span><span class="sxs-lookup"><span data-stu-id="b2ac1-172">**Query**</span></span>

<span data-ttu-id="b2ac1-173">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="b2ac1-173">**Request**</span></span>

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollpositionentities?$filter=mshr_positionid eq @positionid and mshr_validfrom le @asofdate and mshr_validto ge @asofdate&@positionid='000276'&@asofdate=2021-04-01
```

<span data-ttu-id="b2ac1-174">**Svar**</span><span class="sxs-lookup"><span data-stu-id="b2ac1-174">**Response**</span></span>

```json
{
            "mshr_positionid": "000276",
            "mshr_paycycleid": "w",
            "mshr_annualregularhours": 3000,
            "mshr_paidbylegalentity": "USMF",
            "mshr_validfrom": "2021-03-14T00:00:00Z",
            "mshr_validto": "2154-12-31T00:00:00Z",
            "mshr_primaryfield": "000276 | 3/14/2021",
            "_mshr_fk_job_id_value": "00010094-0000-0000-df00-014105000000",
            "_mshr_fk_fixedcompplan_id_value": "0000029f-0000-0000-d5ff-004105000000",
            "mshr_payrollpositionentityid": "00010097-0000-0000-df00-014105000000"
}
```
