---
title: Personkontroller
description: I detta ämne beskrivs kontrollentiteten Person för Dynamics 365 Human Resources.
author: jaredha
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 9d29b26094e307c3f68d57f297ab3614f3a5ccae
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059290"
---
# <a name="person-screening"></a><span data-ttu-id="a60f7-103">Personkontroller</span><span class="sxs-lookup"><span data-stu-id="a60f7-103">Person screening</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="a60f7-104">I detta ämne beskrivs kontrollentiteten Person för Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="a60f7-104">This topic describes the Person screening entity for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="a60f7-105">Fysiskt namn: mshr_hcmpersonscreeningentity</span><span class="sxs-lookup"><span data-stu-id="a60f7-105">Physical name: mshr_hcmpersonscreeningentity</span></span>

## <a name="description"></a><span data-ttu-id="a60f7-106">beskrivning</span><span class="sxs-lookup"><span data-stu-id="a60f7-106">Description</span></span>

<span data-ttu-id="a60f7-107">Denna entitet beskriver gallringningar som en kandidat har klarat eller måste klara för anställning.</span><span class="sxs-lookup"><span data-stu-id="a60f7-107">This entity describes screenings a candidate has passed or must pass for employment.</span></span>

## <a name="json-representation"></a><span data-ttu-id="a60f7-108">JSON-representation</span><span class="sxs-lookup"><span data-stu-id="a60f7-108">JSON representation</span></span>

```json
{
    "mshr_note": "String",
    "mshr_requiredby": "Date",
    "mshr_status": Int,
    "mshr_partynumber": "String",
    "mshr_screeningtypeid": "String",
    "mshr_primaryfield": "String",
    "_mshr_fk_person_id_value": "Guid",
    "mshr_hcmpersonscreeningentityid": "Guid",
    "mshr_completeddate": "Date"
}
```

## <a name="properties"></a><span data-ttu-id="a60f7-109">Egenskaper</span><span class="sxs-lookup"><span data-stu-id="a60f7-109">Properties</span></span>

| <span data-ttu-id="a60f7-110">Egenskap</span><span class="sxs-lookup"><span data-stu-id="a60f7-110">Property</span></span><br><span data-ttu-id="a60f7-111">**Fysiskt namn**</span><span class="sxs-lookup"><span data-stu-id="a60f7-111">**Physical name**</span></span><br><span data-ttu-id="a60f7-112">**_Typ_**</span><span class="sxs-lookup"><span data-stu-id="a60f7-112">**_Type_**</span></span> | <span data-ttu-id="a60f7-113">Använd</span><span class="sxs-lookup"><span data-stu-id="a60f7-113">Use</span></span> | <span data-ttu-id="a60f7-114">beskrivning</span><span class="sxs-lookup"><span data-stu-id="a60f7-114">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="a60f7-115">**Entitets-ID för persongallring**</span><span class="sxs-lookup"><span data-stu-id="a60f7-115">**Person Screening Entity ID**</span></span><br><span data-ttu-id="a60f7-116">mshr_hcmpersonscreeningentityid</span><span class="sxs-lookup"><span data-stu-id="a60f7-116">mshr_hcmpersonscreeningentityid</span></span><br><span data-ttu-id="a60f7-117">*GUID*</span><span class="sxs-lookup"><span data-stu-id="a60f7-117">*GUID*</span></span> | <span data-ttu-id="a60f7-118">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="a60f7-118">Read-only</span></span><br><span data-ttu-id="a60f7-119">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="a60f7-119">Required</span></span><br><span data-ttu-id="a60f7-120">Systemgenererad</span><span class="sxs-lookup"><span data-stu-id="a60f7-120">System-generated</span></span> | <span data-ttu-id="a60f7-121">Unik, primär identifierare för posten för persongallring.</span><span class="sxs-lookup"><span data-stu-id="a60f7-121">Unique primary identifier for the person screening record.</span></span> |
| <span data-ttu-id="a60f7-122">**Partnummer**</span><span class="sxs-lookup"><span data-stu-id="a60f7-122">**Party Number**</span></span><br><span data-ttu-id="a60f7-123">mshr_partynumber</span><span class="sxs-lookup"><span data-stu-id="a60f7-123">mshr_partynumber</span></span><br><span data-ttu-id="a60f7-124">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="a60f7-124">*String*</span></span> | <span data-ttu-id="a60f7-125">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="a60f7-125">Read/write</span></span><br><span data-ttu-id="a60f7-126">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="a60f7-126">Required</span></span> | <span data-ttu-id="a60f7-127">Det partnummer (personnummer) som är kopplat till kandidaten.</span><span class="sxs-lookup"><span data-stu-id="a60f7-127">The party (person) number associated with the candidate.</span></span> |
| <span data-ttu-id="a60f7-128">**Värde för personligt ID**</span><span class="sxs-lookup"><span data-stu-id="a60f7-128">**Person ID Value**</span></span><br><span data-ttu-id="a60f7-129">_mshr_fk_person_id_value</span><span class="sxs-lookup"><span data-stu-id="a60f7-129">_mshr_fk_person_id_value</span></span><br><span data-ttu-id="a60f7-130">*GUID*</span><span class="sxs-lookup"><span data-stu-id="a60f7-130">*GUID*</span></span> | <span data-ttu-id="a60f7-131">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="a60f7-131">Read-only</span></span><br><span data-ttu-id="a60f7-132">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="a60f7-132">Required</span></span><br><span data-ttu-id="a60f7-133">Sekundärnyckel: mshr_dirpersonentityid för mshr_dirpersonentity</span><span class="sxs-lookup"><span data-stu-id="a60f7-133">Foreign key: mshr_dirpersonentityid of mshr_dirpersonentity</span></span> | <span data-ttu-id="a60f7-134">Den systemgenererade, unika identifieraren för entitetsposten för parten (personen).</span><span class="sxs-lookup"><span data-stu-id="a60f7-134">The system-generated identifier of the party (person) entity record.</span></span> |
| <span data-ttu-id="a60f7-135">**ID för gallringstyp**</span><span class="sxs-lookup"><span data-stu-id="a60f7-135">**Screening Type ID**</span></span><br><span data-ttu-id="a60f7-136">mshr_screeningtypeid</span><span class="sxs-lookup"><span data-stu-id="a60f7-136">mshr_screeningtypeid</span></span><br><span data-ttu-id="a60f7-137">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="a60f7-137">*String*</span></span> | <span data-ttu-id="a60f7-138">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="a60f7-138">Read/write</span></span><br><span data-ttu-id="a60f7-139">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="a60f7-139">Required</span></span><br><span data-ttu-id="a60f7-140">Sekundärnyckel: Gallringstyp</span><span class="sxs-lookup"><span data-stu-id="a60f7-140">Foreign key: ScreeningType</span></span> | <span data-ttu-id="a60f7-141">Identifieraren för den gallringstyp som angetts i Personal.</span><span class="sxs-lookup"><span data-stu-id="a60f7-141">The identifier of the screening type defined in Human Resources.</span></span> |
| <span data-ttu-id="a60f7-142">**ID-värde för gallringstyp**</span><span class="sxs-lookup"><span data-stu-id="a60f7-142">**Screening Type ID Value**</span></span><br><span data-ttu-id="a60f7-143">_mshr_fk_screeningtype_id_value</span><span class="sxs-lookup"><span data-stu-id="a60f7-143">_mshr_fk_screeningtype_id_value</span></span><br><span data-ttu-id="a60f7-144">*GUID*</span><span class="sxs-lookup"><span data-stu-id="a60f7-144">*GUID*</span></span> | <span data-ttu-id="a60f7-145">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="a60f7-145">Read-only</span></span><br><span data-ttu-id="a60f7-146">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="a60f7-146">Required</span></span><br><span data-ttu-id="a60f7-147">Sekundärnyckel: mshr_hcmscreeningtypeentityid för mshr_hcmscreeningtypeentity</span><span class="sxs-lookup"><span data-stu-id="a60f7-147">Foreign key: mshr_hcmscreeningtypeentityid of mshr_hcmscreeningtypeentity</span></span> | <span data-ttu-id="a60f7-148">Systemgenererad identifierare för gallringstypposten i den associerade entiteten.</span><span class="sxs-lookup"><span data-stu-id="a60f7-148">System-generated identifier for the screening type record in the associated entity.</span></span> |
| <span data-ttu-id="a60f7-149">**Krävs senast**</span><span class="sxs-lookup"><span data-stu-id="a60f7-149">**Required By**</span></span><br><span data-ttu-id="a60f7-150">mshr_requiredby</span><span class="sxs-lookup"><span data-stu-id="a60f7-150">mshr_requiredby</span></span><br><span data-ttu-id="a60f7-151">*Datum/tid*</span><span class="sxs-lookup"><span data-stu-id="a60f7-151">*Datetime*</span></span> | <span data-ttu-id="a60f7-152">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="a60f7-152">Read/write</span></span><br><span data-ttu-id="a60f7-153">Valfritt</span><span class="sxs-lookup"><span data-stu-id="a60f7-153">Optional</span></span> | <span data-ttu-id="a60f7-154">Det datum då gallringen måste ha genomförts.</span><span class="sxs-lookup"><span data-stu-id="a60f7-154">The date by which the screening is required to be completed.</span></span> |
| <span data-ttu-id="a60f7-155">**Status**</span><span class="sxs-lookup"><span data-stu-id="a60f7-155">**Status**</span></span><br><span data-ttu-id="a60f7-156">mshr_status</span><span class="sxs-lookup"><span data-stu-id="a60f7-156">mshr_status</span></span><br><span data-ttu-id="a60f7-157">*alternativuppsättningen mshr_hcmcompletionstatus*</span><span class="sxs-lookup"><span data-stu-id="a60f7-157">*mshr_hcmcompletionstatus option set*</span></span><br><span data-ttu-id="a60f7-158">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="a60f7-158">Read/write</span></span><br><span data-ttu-id="a60f7-159">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="a60f7-159">Required</span></span> | <span data-ttu-id="a60f7-160">Anger kandidatens status för gallring.</span><span class="sxs-lookup"><span data-stu-id="a60f7-160">Provides the candidate’s status for the screening.</span></span> |
| <span data-ttu-id="a60f7-161">**Slutfört den**</span><span class="sxs-lookup"><span data-stu-id="a60f7-161">**Completed Date**</span></span><br><span data-ttu-id="a60f7-162">mshr_completeddate</span><span class="sxs-lookup"><span data-stu-id="a60f7-162">mshr_completeddate</span></span><br><span data-ttu-id="a60f7-163">*Datum/tid*</span><span class="sxs-lookup"><span data-stu-id="a60f7-163">*Datetime*</span></span> | <span data-ttu-id="a60f7-164">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="a60f7-164">Read/write</span></span><br><span data-ttu-id="a60f7-165">Valfritt</span><span class="sxs-lookup"><span data-stu-id="a60f7-165">Optional</span></span> | <span data-ttu-id="a60f7-166">Det datum då gallringningen slutfördes.</span><span class="sxs-lookup"><span data-stu-id="a60f7-166">The date the screening was completed.</span></span> |
| <span data-ttu-id="a60f7-167">**Anteckningar**</span><span class="sxs-lookup"><span data-stu-id="a60f7-167">**Notes**</span></span><br><span data-ttu-id="a60f7-168">mshr_note</span><span class="sxs-lookup"><span data-stu-id="a60f7-168">mshr_note</span></span><br><span data-ttu-id="a60f7-169">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="a60f7-169">*String*</span></span> | <span data-ttu-id="a60f7-170">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="a60f7-170">Read/write</span></span><br><span data-ttu-id="a60f7-171">Valfritt</span><span class="sxs-lookup"><span data-stu-id="a60f7-171">Optional</span></span> | <span data-ttu-id="a60f7-172">Anteckningar att användas av anställande chefer och rekryterare.</span><span class="sxs-lookup"><span data-stu-id="a60f7-172">Notes for use by hiring managers and recruiters.</span></span> |

## <a name="see-also"></a><span data-ttu-id="a60f7-173">Se även</span><span class="sxs-lookup"><span data-stu-id="a60f7-173">See also</span></span>

[<span data-ttu-id="a60f7-174">Introduktion av API för integrering av system för sökandespårning</span><span class="sxs-lookup"><span data-stu-id="a60f7-174">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="a60f7-175">Exempelfråga för kandidat att anställa</span><span class="sxs-lookup"><span data-stu-id="a60f7-175">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]