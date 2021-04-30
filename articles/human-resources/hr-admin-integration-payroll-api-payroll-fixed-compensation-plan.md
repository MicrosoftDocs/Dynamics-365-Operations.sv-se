---
title: Kompensationsplan med fast lön
description: Detta ämne tillhandahåller information och en exempelfrågeställning för lönelistaentiteten för fast kompensationsplan i Dynamics 365 Human Resources.
author: jcart
manager: tfehr
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
ms.openlocfilehash: 78a274cc491041d3d917a50bfb433f667cd8c255
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "5882081"
---
# <a name="payroll-fixed-compensation-plan"></a><span data-ttu-id="bdaaa-103">Kompensationsplan med fast lön</span><span class="sxs-lookup"><span data-stu-id="bdaaa-103">Payroll fixed compensation plan</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="bdaaa-104">Detta ämne tillhandahåller information och en exempelfrågeställning för lönelistaentiteten för fast kompensationsplan i Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="bdaaa-104">This topic provides details and an example query for the Payroll fixed compensation plan entity in Dynamics 365 Human Resources.</span></span>

## <a name="properties"></a><span data-ttu-id="bdaaa-105">Egenskaper</span><span class="sxs-lookup"><span data-stu-id="bdaaa-105">Properties</span></span>

| <span data-ttu-id="bdaaa-106">Egenskap</span><span class="sxs-lookup"><span data-stu-id="bdaaa-106">Property</span></span><br><span data-ttu-id="bdaaa-107">**Fysiskt namn**</span><span class="sxs-lookup"><span data-stu-id="bdaaa-107">**Physical name**</span></span><br><span data-ttu-id="bdaaa-108">**_Typ_**</span><span class="sxs-lookup"><span data-stu-id="bdaaa-108">**_Type_**</span></span> | <span data-ttu-id="bdaaa-109">Använd</span><span class="sxs-lookup"><span data-stu-id="bdaaa-109">Use</span></span> | <span data-ttu-id="bdaaa-110">beskrivning</span><span class="sxs-lookup"><span data-stu-id="bdaaa-110">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="bdaaa-111">**Medarbetarens ID**</span><span class="sxs-lookup"><span data-stu-id="bdaaa-111">**Employee ID**</span></span><br><span data-ttu-id="bdaaa-112">mshr_fk_employee_id_value</span><span class="sxs-lookup"><span data-stu-id="bdaaa-112">mshr_fk_employee_id_value</span></span><br><span data-ttu-id="bdaaa-113">*GUID*</span><span class="sxs-lookup"><span data-stu-id="bdaaa-113">*GUID*</span></span> | <span data-ttu-id="bdaaa-114">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="bdaaa-114">Read-only</span></span><br><span data-ttu-id="bdaaa-115">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="bdaaa-115">Required</span></span><br><span data-ttu-id="bdaaa-116">Sekundärnyckel: mshr_Employee_id för entiteten mshr_payrollemployeeentity</span><span class="sxs-lookup"><span data-stu-id="bdaaa-116">Foreign key:mshr_Employee_id of mshr_payrollemployeeentity entity</span></span>  | <span data-ttu-id="bdaaa-117">Medarbetarens ID</span><span class="sxs-lookup"><span data-stu-id="bdaaa-117">Employee ID</span></span> |
| <span data-ttu-id="bdaaa-118">**Lönesats**</span><span class="sxs-lookup"><span data-stu-id="bdaaa-118">**Pay rate**</span></span><br><span data-ttu-id="bdaaa-119">mshr_payrate</span><span class="sxs-lookup"><span data-stu-id="bdaaa-119">mshr_payrate</span></span><br><span data-ttu-id="bdaaa-120">*Decimal*</span><span class="sxs-lookup"><span data-stu-id="bdaaa-120">*Decimal*</span></span> | <span data-ttu-id="bdaaa-121">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="bdaaa-121">Read-only</span></span><br><span data-ttu-id="bdaaa-122">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="bdaaa-122">Required</span></span> | <span data-ttu-id="bdaaa-123">Lönesats som definieras i den fasta kompensationsplanen.</span><span class="sxs-lookup"><span data-stu-id="bdaaa-123">Pay rate defined in fixed compensation plan.</span></span> |
| <span data-ttu-id="bdaaa-124">**Plan-ID**</span><span class="sxs-lookup"><span data-stu-id="bdaaa-124">**Plan ID**</span></span><br><span data-ttu-id="bdaaa-125">mshr_planid</span><span class="sxs-lookup"><span data-stu-id="bdaaa-125">mshr_planid</span></span><br><span data-ttu-id="bdaaa-126">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="bdaaa-126">*String*</span></span> | <span data-ttu-id="bdaaa-127">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="bdaaa-127">Read-only</span></span><br><span data-ttu-id="bdaaa-128">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="bdaaa-128">Required</span></span> |<span data-ttu-id="bdaaa-129">Anger kompensationsplanen.</span><span class="sxs-lookup"><span data-stu-id="bdaaa-129">Specifies the compensation plan.</span></span>  |
| <span data-ttu-id="bdaaa-130">**Giltig från**</span><span class="sxs-lookup"><span data-stu-id="bdaaa-130">**Valid from**</span></span><br><span data-ttu-id="bdaaa-131">mshr_validfrom</span><span class="sxs-lookup"><span data-stu-id="bdaaa-131">mshr_validfrom</span></span><br><span data-ttu-id="bdaaa-132">*Datum Tid Offset*</span><span class="sxs-lookup"><span data-stu-id="bdaaa-132">*Date Time Offset*</span></span> |  <span data-ttu-id="bdaaa-133">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="bdaaa-133">Read-only</span></span><br><span data-ttu-id="bdaaa-134">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="bdaaa-134">Required</span></span> |<span data-ttu-id="bdaaa-135">Det datum då medarbetarens fasta kompensation börjar gälla.</span><span class="sxs-lookup"><span data-stu-id="bdaaa-135">Date the employee fixed compensation is valid from.</span></span>  |
| <span data-ttu-id="bdaaa-136">**Lönelisteentiteten för fast kompensation**</span><span class="sxs-lookup"><span data-stu-id="bdaaa-136">**Payroll Fixed Compensation Plan entity**</span></span><br><span data-ttu-id="bdaaa-137">mshr_payrollfixedcompensationplanentityid</span><span class="sxs-lookup"><span data-stu-id="bdaaa-137">mshr_payrollfixedcompensationplanentityid</span></span><br><span data-ttu-id="bdaaa-138">*GUID*</span><span class="sxs-lookup"><span data-stu-id="bdaaa-138">*GUID*</span></span> | <span data-ttu-id="bdaaa-139">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="bdaaa-139">Required</span></span><br><span data-ttu-id="bdaaa-140">Systemgenererad</span><span class="sxs-lookup"><span data-stu-id="bdaaa-140">Sytem generated</span></span> | <span data-ttu-id="bdaaa-141">Ett systemgenererat GUID-värde som ger kompensationsplanen ett unikt ID.</span><span class="sxs-lookup"><span data-stu-id="bdaaa-141">A system-generated GUID value to uniquely identify the compensation plan.</span></span> |
| <span data-ttu-id="bdaaa-142">**Lönefrekvens**</span><span class="sxs-lookup"><span data-stu-id="bdaaa-142">**Pay frequency**</span></span><br><span data-ttu-id="bdaaa-143">mshr_payfrequency</span><span class="sxs-lookup"><span data-stu-id="bdaaa-143">mshr_payfrequency</span></span><br><span data-ttu-id="bdaaa-144">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="bdaaa-144">*String*</span></span> | <span data-ttu-id="bdaaa-145">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="bdaaa-145">Read-only</span></span><br><span data-ttu-id="bdaaa-146">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="bdaaa-146">Required</span></span> |<span data-ttu-id="bdaaa-147">Den frekvens som medarbetaren ska betalas.</span><span class="sxs-lookup"><span data-stu-id="bdaaa-147">The frequency the employee will be paid.</span></span>  |
| <span data-ttu-id="bdaaa-148">**Giltig till**</span><span class="sxs-lookup"><span data-stu-id="bdaaa-148">**Valid to**</span></span><br><span data-ttu-id="bdaaa-149">mshr_validto</span><span class="sxs-lookup"><span data-stu-id="bdaaa-149">mshr_validto</span></span><br><span data-ttu-id="bdaaa-150">*Datum Tid Offset*</span><span class="sxs-lookup"><span data-stu-id="bdaaa-150">*Date Time Offset*</span></span> | <span data-ttu-id="bdaaa-151">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="bdaaa-151">Read-only</span></span> <br><span data-ttu-id="bdaaa-152">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="bdaaa-152">Required</span></span> | <span data-ttu-id="bdaaa-153">Det datum då medarbetarens fasta kompensation slutar gälla.</span><span class="sxs-lookup"><span data-stu-id="bdaaa-153">Date the employee fixed compensation is valid to.</span></span> |
| <span data-ttu-id="bdaaa-154">**Befattnings-ID**</span><span class="sxs-lookup"><span data-stu-id="bdaaa-154">**Position ID**</span></span><br><span data-ttu-id="bdaaa-155">mshr_positionid</span><span class="sxs-lookup"><span data-stu-id="bdaaa-155">mshr_positionid</span></span><br><span data-ttu-id="bdaaa-156">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="bdaaa-156">*String*</span></span> | <span data-ttu-id="bdaaa-157">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="bdaaa-157">Read-only</span></span> <br><span data-ttu-id="bdaaa-158">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="bdaaa-158">Required</span></span> | <span data-ttu-id="bdaaa-159">Positions-ID som är kopplat till medarbetaren samt registrering för fast kompensationsplan.</span><span class="sxs-lookup"><span data-stu-id="bdaaa-159">Postion ID associated with the employee and fixed compensation plan enrollment.</span></span> |
| <span data-ttu-id="bdaaa-160">**Valuta**</span><span class="sxs-lookup"><span data-stu-id="bdaaa-160">**Currency**</span></span><br><span data-ttu-id="bdaaa-161">mshr_currency</span><span class="sxs-lookup"><span data-stu-id="bdaaa-161">mshr_currency</span></span><br><span data-ttu-id="bdaaa-162">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="bdaaa-162">*String*</span></span> | <span data-ttu-id="bdaaa-163">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="bdaaa-163">Read-only</span></span> <br><span data-ttu-id="bdaaa-164">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="bdaaa-164">Required</span></span> |<span data-ttu-id="bdaaa-165">Den valuta som har definierats för den fasta kompensationsplanen</span><span class="sxs-lookup"><span data-stu-id="bdaaa-165">The currency defined for the fixed compensation plan</span></span>   |
| <span data-ttu-id="bdaaa-166">**Personalnummer**</span><span class="sxs-lookup"><span data-stu-id="bdaaa-166">**Personnel number**</span></span><br><span data-ttu-id="bdaaa-167">mshr_personnelnumber</span><span class="sxs-lookup"><span data-stu-id="bdaaa-167">mshr_personnelnumber</span></span><br><span data-ttu-id="bdaaa-168">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="bdaaa-168">*String*</span></span> | <span data-ttu-id="bdaaa-169">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="bdaaa-169">Read-only</span></span><br><span data-ttu-id="bdaaa-170">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="bdaaa-170">Required</span></span> |<span data-ttu-id="bdaaa-171">Medarbetarens unika personalnummer.</span><span class="sxs-lookup"><span data-stu-id="bdaaa-171">The employee's unique personnel number.</span></span>  |

<span data-ttu-id="bdaaa-172">**Fråga**</span><span class="sxs-lookup"><span data-stu-id="bdaaa-172">**Query**</span></span>

<span data-ttu-id="bdaaa-173">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="bdaaa-173">**Request**</span></span>

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollfixedcompensationplanentities?$filter=mshr_personnelnumber eq @personnelnumber and mshr_validfrom le @asofdate and mshr_validto ge @asofdate&@personnelnumber='000041'&@asofdate=2021-04-01
```

<span data-ttu-id="bdaaa-174">**Svar**</span><span class="sxs-lookup"><span data-stu-id="bdaaa-174">**Response**</span></span>

```json
{
            "mshr_planid": "GradeC",
            "mshr_personnelnumber": "000041",
            "mshr_payrate": 75200,
            "mshr_positionid": "000276",
            "mshr_validfrom": "2011-04-05T00:00:00Z",
            "mshr_validto": "2154-12-31T00:00:00Z",
            "mshr_payfrequency": "Annual",
            "mshr_currency": "USD",
            "_mshr_fk_employee_id_value": "00000d3c-0000-0000-d5ff-004105000000",
            "_mshr_fk_plan_id_value": "0000070c-0000-0000-b328-fef003000000",
            "_mshr_fk_job_id_value": "00010094-0000-0000-df00-014105000000",
            "mshr_payrollfixedcompensationplanentityid": "0000029f-0000-0000-d5ff-004105000000",
            "_mshr_fk_payroll_id_value": null
}
```
