---
title: Löneuppgifter för Positioner
description: Detta ämne tillhandahåller information och en exempelfrågeställning för entiteten för löneuppgifter för positioner i Dynamics 365 Human Resources.
author: jcart
ms.date: 04/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2021-04-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 8918044dbf84e79015dc3bca904f204123a37db8
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/18/2021
ms.locfileid: "6056790"
---
# <a name="payroll-position"></a><span data-ttu-id="cc57a-103">Lönebefattning</span><span class="sxs-lookup"><span data-stu-id="cc57a-103">Payroll position</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="cc57a-104">Detta ämne tillhandahåller information och en exempelfrågeställning för entiteten för löneuppgifter för positioner i Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="cc57a-104">This topic provides details and an example query for the Payroll details for the Positions entity in Dynamics 365 Human Resources.</span></span>

## <a name="properties"></a><span data-ttu-id="cc57a-105">Egenskaper</span><span class="sxs-lookup"><span data-stu-id="cc57a-105">Properties</span></span>

| <span data-ttu-id="cc57a-106">Egenskap</span><span class="sxs-lookup"><span data-stu-id="cc57a-106">Property</span></span><br><span data-ttu-id="cc57a-107">**Fysiskt namn**</span><span class="sxs-lookup"><span data-stu-id="cc57a-107">**Physical name**</span></span><br><span data-ttu-id="cc57a-108">**_Typ_**</span><span class="sxs-lookup"><span data-stu-id="cc57a-108">**_Type_**</span></span> | <span data-ttu-id="cc57a-109">Använd</span><span class="sxs-lookup"><span data-stu-id="cc57a-109">Use</span></span> | <span data-ttu-id="cc57a-110">beskrivning</span><span class="sxs-lookup"><span data-stu-id="cc57a-110">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="cc57a-111">**Ordinarie timmar per år**</span><span class="sxs-lookup"><span data-stu-id="cc57a-111">**Annual regular hours**</span></span><br><span data-ttu-id="cc57a-112">annualregularhours</span><span class="sxs-lookup"><span data-stu-id="cc57a-112">annualregularhours</span></span><br><span data-ttu-id="cc57a-113">*Decimal*</span><span class="sxs-lookup"><span data-stu-id="cc57a-113">*Decimal*</span></span> | <span data-ttu-id="cc57a-114">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="cc57a-114">Read-only</span></span><br><span data-ttu-id="cc57a-115">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="cc57a-115">Required</span></span> | <span data-ttu-id="cc57a-116">Årligt antal regelbundna timmar som definierats för befattningen.</span><span class="sxs-lookup"><span data-stu-id="cc57a-116">Annual regular hours defined on the position.</span></span>  |
| <span data-ttu-id="cc57a-117">**Entitets-ID för information om löneposition**</span><span class="sxs-lookup"><span data-stu-id="cc57a-117">**Payroll position details entity ID**</span></span><br><span data-ttu-id="cc57a-118">payrollpositiondetailsentityid</span><span class="sxs-lookup"><span data-stu-id="cc57a-118">payrollpositiondetailsentityid</span></span><br><span data-ttu-id="cc57a-119">*Guid*</span><span class="sxs-lookup"><span data-stu-id="cc57a-119">*Guid*</span></span> | <span data-ttu-id="cc57a-120">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="cc57a-120">Required</span></span><br><span data-ttu-id="cc57a-121">Systemgenererat.</span><span class="sxs-lookup"><span data-stu-id="cc57a-121">System generated.</span></span> | <span data-ttu-id="cc57a-122">Ett systemgenererat GUID-värde som unikt identifierar positionen.</span><span class="sxs-lookup"><span data-stu-id="cc57a-122">A system-generated GUID value to uniquely identify the position.</span></span>  |
| <span data-ttu-id="cc57a-123">**Primärt fält**</span><span class="sxs-lookup"><span data-stu-id="cc57a-123">**Primary field**</span></span><br><span data-ttu-id="cc57a-124">mshr_primaryfield</span><span class="sxs-lookup"><span data-stu-id="cc57a-124">mshr_primaryfield</span></span><br><span data-ttu-id="cc57a-125">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="cc57a-125">*String*</span></span> | <span data-ttu-id="cc57a-126">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="cc57a-126">Required</span></span><br><span data-ttu-id="cc57a-127">Systemgenererad</span><span class="sxs-lookup"><span data-stu-id="cc57a-127">System generated</span></span> |  |
| <span data-ttu-id="cc57a-128">**ID-värde för befattningsjobb**</span><span class="sxs-lookup"><span data-stu-id="cc57a-128">**Position job ID value**</span></span><br><span data-ttu-id="cc57a-129">_mshr_fk_positionjob_id_value</span><span class="sxs-lookup"><span data-stu-id="cc57a-129">_mshr_fk_positionjob_id_value</span></span><br><span data-ttu-id="cc57a-130">*GUID*</span><span class="sxs-lookup"><span data-stu-id="cc57a-130">*GUID*</span></span> | <span data-ttu-id="cc57a-131">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="cc57a-131">Read-only</span></span><br><span data-ttu-id="cc57a-132">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="cc57a-132">Required</span></span><br><span data-ttu-id="cc57a-133">Sekundärnyckel:mshr_PayrollPositionJobEntity för mshr_payrollpositionjobentity</span><span class="sxs-lookup"><span data-stu-id="cc57a-133">Foreign key:mshr_PayrollPositionJobEntity of the mshr_payrollpositionjobentity</span></span> |<span data-ttu-id="cc57a-134">ID för det jobb som är kopplat till befattningen.</span><span class="sxs-lookup"><span data-stu-id="cc57a-134">The ID of the job associated with the position.</span></span>|
| <span data-ttu-id="cc57a-135">**ID-värde för fast kompensationsplan**</span><span class="sxs-lookup"><span data-stu-id="cc57a-135">**Fixed compensation plan ID value**</span></span><br><span data-ttu-id="cc57a-136">_mshr_fk_fixedcompplan_id_value</span><span class="sxs-lookup"><span data-stu-id="cc57a-136">_mshr_fk_fixedcompplan_id_value</span></span><br><span data-ttu-id="cc57a-137">*GUID*</span><span class="sxs-lookup"><span data-stu-id="cc57a-137">*GUID*</span></span> | <span data-ttu-id="cc57a-138">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="cc57a-138">Read-only</span></span><br><span data-ttu-id="cc57a-139">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="cc57a-139">Required</span></span><br><span data-ttu-id="cc57a-140">Sekundärnyckel: mshr_FixedCompPlan_id för mshr_payrollfixedcompensationplanentity</span><span class="sxs-lookup"><span data-stu-id="cc57a-140">Foreign key: mshr_FixedCompPlan_id of mshr_payrollfixedcompensationplanentity</span></span>  | <span data-ttu-id="cc57a-141">ID för den fasta kompensationsplan som är kopplad till befattningen.</span><span class="sxs-lookup"><span data-stu-id="cc57a-141">The ID of the fixed compensation plan associated with the position.</span></span> |
| <span data-ttu-id="cc57a-142">**ID för lönecykel**</span><span class="sxs-lookup"><span data-stu-id="cc57a-142">**Pay cycle ID**</span></span><br><span data-ttu-id="cc57a-143">mshr_primaryfield</span><span class="sxs-lookup"><span data-stu-id="cc57a-143">mshr_primaryfield</span></span><br><span data-ttu-id="cc57a-144">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="cc57a-144">*String*</span></span> | <span data-ttu-id="cc57a-145">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="cc57a-145">Read-only</span></span><br><span data-ttu-id="cc57a-146">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="cc57a-146">Required</span></span> | <span data-ttu-id="cc57a-147">Lönecykeln som definieras för befattningen.</span><span class="sxs-lookup"><span data-stu-id="cc57a-147">The pay cycle defined on the position.</span></span> |
| <span data-ttu-id="cc57a-148">**Betalas av den juridiska personen**</span><span class="sxs-lookup"><span data-stu-id="cc57a-148">**Paid by legal entity**</span></span><br><span data-ttu-id="cc57a-149">paidbylegalentity</span><span class="sxs-lookup"><span data-stu-id="cc57a-149">paidbylegalentity</span></span><br><span data-ttu-id="cc57a-150">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="cc57a-150">*String*</span></span> | <span data-ttu-id="cc57a-151">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="cc57a-151">Read-only</span></span><br><span data-ttu-id="cc57a-152">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="cc57a-152">Required</span></span> | <span data-ttu-id="cc57a-153">Den juridiska person som definieras i befattningen som ansvarar för utfärdande av betalning.</span><span class="sxs-lookup"><span data-stu-id="cc57a-153">The legal entity defined on the positoin responsible for issuing payment.</span></span> |
| <span data-ttu-id="cc57a-154">**Befattnings-ID**</span><span class="sxs-lookup"><span data-stu-id="cc57a-154">**Position ID**</span></span><br><span data-ttu-id="cc57a-155">mshr_positionid</span><span class="sxs-lookup"><span data-stu-id="cc57a-155">mshr_positionid</span></span><br><span data-ttu-id="cc57a-156">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="cc57a-156">*String*</span></span> | <span data-ttu-id="cc57a-157">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="cc57a-157">Read-only</span></span><br><span data-ttu-id="cc57a-158">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="cc57a-158">Required</span></span> | <span data-ttu-id="cc57a-159">Befattningens ID.</span><span class="sxs-lookup"><span data-stu-id="cc57a-159">The ID of the position.</span></span> |
| <span data-ttu-id="cc57a-160">**Giltig till**</span><span class="sxs-lookup"><span data-stu-id="cc57a-160">**Valid to**</span></span><br><span data-ttu-id="cc57a-161">validto</span><span class="sxs-lookup"><span data-stu-id="cc57a-161">validto</span></span><br><span data-ttu-id="cc57a-162">*Datum Tid Offset*</span><span class="sxs-lookup"><span data-stu-id="cc57a-162">*Date Time Offset*</span></span> | <span data-ttu-id="cc57a-163">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="cc57a-163">Read-only</span></span><br><span data-ttu-id="cc57a-164">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="cc57a-164">Required</span></span> |<span data-ttu-id="cc57a-165">Det datum befattningsinformationen gäller från.</span><span class="sxs-lookup"><span data-stu-id="cc57a-165">The date the position details are valid from.</span></span>  |
| <span data-ttu-id="cc57a-166">**Giltig från**</span><span class="sxs-lookup"><span data-stu-id="cc57a-166">**Valid from**</span></span><br><span data-ttu-id="cc57a-167">validfrom</span><span class="sxs-lookup"><span data-stu-id="cc57a-167">validfrom</span></span><br><span data-ttu-id="cc57a-168">*Datum Tid Offset*</span><span class="sxs-lookup"><span data-stu-id="cc57a-168">*Date Time Offset*</span></span> | <span data-ttu-id="cc57a-169">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="cc57a-169">Read-only</span></span><br><span data-ttu-id="cc57a-170">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="cc57a-170">Required</span></span> |<span data-ttu-id="cc57a-171">Det datum befattningsinformationen gäller till.</span><span class="sxs-lookup"><span data-stu-id="cc57a-171">The date the position details are valid to.</span></span>  |

<span data-ttu-id="cc57a-172">**Fråga**</span><span class="sxs-lookup"><span data-stu-id="cc57a-172">**Query**</span></span>

<span data-ttu-id="cc57a-173">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="cc57a-173">**Request**</span></span>

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollpositionentities?$filter=mshr_positionid eq @positionid and mshr_validfrom le @asofdate and mshr_validto ge @asofdate&@positionid='000276'&@asofdate=2021-04-01
```

<span data-ttu-id="cc57a-174">**Svar**</span><span class="sxs-lookup"><span data-stu-id="cc57a-174">**Response**</span></span>

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
