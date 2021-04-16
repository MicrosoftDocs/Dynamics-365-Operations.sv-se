---
title: Personkontroller
description: I detta ämne beskrivs kontrollentiteten Person för Dynamics 365 Human Resources.
author: jaredha
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 4bc32eb948f4a4966a927b0907b8d499486e43dc
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5798043"
---
# <a name="person-screening"></a><span data-ttu-id="f88a9-103">Personkontroller</span><span class="sxs-lookup"><span data-stu-id="f88a9-103">Person screening</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="f88a9-104">I detta ämne beskrivs kontrollentiteten Person för Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="f88a9-104">This topic describes the Person screening entity for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="f88a9-105">Fysiskt namn: mshr_hcmpersonscreeningentity</span><span class="sxs-lookup"><span data-stu-id="f88a9-105">Physical name: mshr_hcmpersonscreeningentity</span></span>

## <a name="description"></a><span data-ttu-id="f88a9-106">beskrivning</span><span class="sxs-lookup"><span data-stu-id="f88a9-106">Description</span></span>

<span data-ttu-id="f88a9-107">Denna entitet beskriver gallringningar som en kandidat har klarat eller måste klara för anställning.</span><span class="sxs-lookup"><span data-stu-id="f88a9-107">This entity describes screenings a candidate has passed or must pass for employment.</span></span>

## <a name="json-representation"></a><span data-ttu-id="f88a9-108">JSON-representation</span><span class="sxs-lookup"><span data-stu-id="f88a9-108">JSON representation</span></span>

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

## <a name="properties"></a><span data-ttu-id="f88a9-109">Egenskaper</span><span class="sxs-lookup"><span data-stu-id="f88a9-109">Properties</span></span>

| <span data-ttu-id="f88a9-110">Egenskap</span><span class="sxs-lookup"><span data-stu-id="f88a9-110">Property</span></span><br><span data-ttu-id="f88a9-111">**Fysiskt namn**</span><span class="sxs-lookup"><span data-stu-id="f88a9-111">**Physical name**</span></span><br><span data-ttu-id="f88a9-112">**_Typ_**</span><span class="sxs-lookup"><span data-stu-id="f88a9-112">**_Type_**</span></span> | <span data-ttu-id="f88a9-113">Använd</span><span class="sxs-lookup"><span data-stu-id="f88a9-113">Use</span></span> | <span data-ttu-id="f88a9-114">beskrivning</span><span class="sxs-lookup"><span data-stu-id="f88a9-114">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="f88a9-115">**Entitets-ID för persongallring**</span><span class="sxs-lookup"><span data-stu-id="f88a9-115">**Person Screening Entity ID**</span></span><br><span data-ttu-id="f88a9-116">mshr_hcmpersonscreeningentityid</span><span class="sxs-lookup"><span data-stu-id="f88a9-116">mshr_hcmpersonscreeningentityid</span></span><br><span data-ttu-id="f88a9-117">*GUID*</span><span class="sxs-lookup"><span data-stu-id="f88a9-117">*GUID*</span></span> | <span data-ttu-id="f88a9-118">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="f88a9-118">Read-only</span></span><br><span data-ttu-id="f88a9-119">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="f88a9-119">Required</span></span><br><span data-ttu-id="f88a9-120">Systemgenererad</span><span class="sxs-lookup"><span data-stu-id="f88a9-120">System-generated</span></span> | <span data-ttu-id="f88a9-121">Unik, primär identifierare för posten för persongallring.</span><span class="sxs-lookup"><span data-stu-id="f88a9-121">Unique primary identifier for the person screening record.</span></span> |
| <span data-ttu-id="f88a9-122">**Partnummer**</span><span class="sxs-lookup"><span data-stu-id="f88a9-122">**Party Number**</span></span><br><span data-ttu-id="f88a9-123">mshr_partynumber</span><span class="sxs-lookup"><span data-stu-id="f88a9-123">mshr_partynumber</span></span><br><span data-ttu-id="f88a9-124">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="f88a9-124">*String*</span></span> | <span data-ttu-id="f88a9-125">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="f88a9-125">Read/write</span></span><br><span data-ttu-id="f88a9-126">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="f88a9-126">Required</span></span> | <span data-ttu-id="f88a9-127">Det partnummer (personnummer) som är kopplat till kandidaten.</span><span class="sxs-lookup"><span data-stu-id="f88a9-127">The party (person) number associated with the candidate.</span></span> |
| <span data-ttu-id="f88a9-128">**Värde för personligt ID**</span><span class="sxs-lookup"><span data-stu-id="f88a9-128">**Person ID Value**</span></span><br><span data-ttu-id="f88a9-129">_mshr_fk_person_id_value</span><span class="sxs-lookup"><span data-stu-id="f88a9-129">_mshr_fk_person_id_value</span></span><br><span data-ttu-id="f88a9-130">*GUID*</span><span class="sxs-lookup"><span data-stu-id="f88a9-130">*GUID*</span></span> | <span data-ttu-id="f88a9-131">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="f88a9-131">Read-only</span></span><br><span data-ttu-id="f88a9-132">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="f88a9-132">Required</span></span><br><span data-ttu-id="f88a9-133">Sekundärnyckel: mshr_dirpersonentityid för mshr_dirpersonentity</span><span class="sxs-lookup"><span data-stu-id="f88a9-133">Foreign key: mshr_dirpersonentityid of mshr_dirpersonentity</span></span> | <span data-ttu-id="f88a9-134">Den systemgenererade, unika identifieraren för entitetsposten för parten (personen).</span><span class="sxs-lookup"><span data-stu-id="f88a9-134">The system-generated identifier of the party (person) entity record.</span></span> |
| <span data-ttu-id="f88a9-135">**ID för gallringstyp**</span><span class="sxs-lookup"><span data-stu-id="f88a9-135">**Screening Type ID**</span></span><br><span data-ttu-id="f88a9-136">mshr_screeningtypeid</span><span class="sxs-lookup"><span data-stu-id="f88a9-136">mshr_screeningtypeid</span></span><br><span data-ttu-id="f88a9-137">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="f88a9-137">*String*</span></span> | <span data-ttu-id="f88a9-138">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="f88a9-138">Read/write</span></span><br><span data-ttu-id="f88a9-139">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="f88a9-139">Required</span></span><br><span data-ttu-id="f88a9-140">Sekundärnyckel: Gallringstyp</span><span class="sxs-lookup"><span data-stu-id="f88a9-140">Foreign key: ScreeningType</span></span> | <span data-ttu-id="f88a9-141">Identifieraren för den gallringstyp som angetts i Personal.</span><span class="sxs-lookup"><span data-stu-id="f88a9-141">The identifier of the screening type defined in Human Resources.</span></span> |
| <span data-ttu-id="f88a9-142">**ID-värde för gallringstyp**</span><span class="sxs-lookup"><span data-stu-id="f88a9-142">**Screening Type ID Value**</span></span><br><span data-ttu-id="f88a9-143">_mshr_fk_screeningtype_id_value</span><span class="sxs-lookup"><span data-stu-id="f88a9-143">_mshr_fk_screeningtype_id_value</span></span><br><span data-ttu-id="f88a9-144">*GUID*</span><span class="sxs-lookup"><span data-stu-id="f88a9-144">*GUID*</span></span> | <span data-ttu-id="f88a9-145">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="f88a9-145">Read-only</span></span><br><span data-ttu-id="f88a9-146">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="f88a9-146">Required</span></span><br><span data-ttu-id="f88a9-147">Sekundärnyckel: mshr_hcmscreeningtypeentityid för mshr_hcmscreeningtypeentity</span><span class="sxs-lookup"><span data-stu-id="f88a9-147">Foreign key: mshr_hcmscreeningtypeentityid of mshr_hcmscreeningtypeentity</span></span> | <span data-ttu-id="f88a9-148">Systemgenererad identifierare för gallringstypposten i den associerade entiteten.</span><span class="sxs-lookup"><span data-stu-id="f88a9-148">System-generated identifier for the screening type record in the associated entity.</span></span> |
| <span data-ttu-id="f88a9-149">**Krävs senast**</span><span class="sxs-lookup"><span data-stu-id="f88a9-149">**Required By**</span></span><br><span data-ttu-id="f88a9-150">mshr_requiredby</span><span class="sxs-lookup"><span data-stu-id="f88a9-150">mshr_requiredby</span></span><br><span data-ttu-id="f88a9-151">*Datum/tid*</span><span class="sxs-lookup"><span data-stu-id="f88a9-151">*Datetime*</span></span> | <span data-ttu-id="f88a9-152">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="f88a9-152">Read/write</span></span><br><span data-ttu-id="f88a9-153">Valfritt</span><span class="sxs-lookup"><span data-stu-id="f88a9-153">Optional</span></span> | <span data-ttu-id="f88a9-154">Det datum då gallringen måste ha genomförts.</span><span class="sxs-lookup"><span data-stu-id="f88a9-154">The date by which the screening is required to be completed.</span></span> |
| <span data-ttu-id="f88a9-155">**Status**</span><span class="sxs-lookup"><span data-stu-id="f88a9-155">**Status**</span></span><br><span data-ttu-id="f88a9-156">mshr_status</span><span class="sxs-lookup"><span data-stu-id="f88a9-156">mshr_status</span></span><br><span data-ttu-id="f88a9-157">*alternativuppsättningen mshr_hcmcompletionstatus*</span><span class="sxs-lookup"><span data-stu-id="f88a9-157">*mshr_hcmcompletionstatus option set*</span></span><br><span data-ttu-id="f88a9-158">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="f88a9-158">Read/write</span></span><br><span data-ttu-id="f88a9-159">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="f88a9-159">Required</span></span> | <span data-ttu-id="f88a9-160">Anger kandidatens status för gallring.</span><span class="sxs-lookup"><span data-stu-id="f88a9-160">Provides the candidate’s status for the screening.</span></span> |
| <span data-ttu-id="f88a9-161">**Slutfört den**</span><span class="sxs-lookup"><span data-stu-id="f88a9-161">**Completed Date**</span></span><br><span data-ttu-id="f88a9-162">mshr_completeddate</span><span class="sxs-lookup"><span data-stu-id="f88a9-162">mshr_completeddate</span></span><br><span data-ttu-id="f88a9-163">*Datum/tid*</span><span class="sxs-lookup"><span data-stu-id="f88a9-163">*Datetime*</span></span> | <span data-ttu-id="f88a9-164">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="f88a9-164">Read/write</span></span><br><span data-ttu-id="f88a9-165">Valfritt</span><span class="sxs-lookup"><span data-stu-id="f88a9-165">Optional</span></span> | <span data-ttu-id="f88a9-166">Det datum då gallringningen slutfördes.</span><span class="sxs-lookup"><span data-stu-id="f88a9-166">The date the screening was completed.</span></span> |
| <span data-ttu-id="f88a9-167">**Anteckningar**</span><span class="sxs-lookup"><span data-stu-id="f88a9-167">**Notes**</span></span><br><span data-ttu-id="f88a9-168">mshr_note</span><span class="sxs-lookup"><span data-stu-id="f88a9-168">mshr_note</span></span><br><span data-ttu-id="f88a9-169">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="f88a9-169">*String*</span></span> | <span data-ttu-id="f88a9-170">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="f88a9-170">Read/write</span></span><br><span data-ttu-id="f88a9-171">Valfritt</span><span class="sxs-lookup"><span data-stu-id="f88a9-171">Optional</span></span> | <span data-ttu-id="f88a9-172">Anteckningar att användas av anställande chefer och rekryterare.</span><span class="sxs-lookup"><span data-stu-id="f88a9-172">Notes for use by hiring managers and recruiters.</span></span> |

## <a name="see-also"></a><span data-ttu-id="f88a9-173">Se även</span><span class="sxs-lookup"><span data-stu-id="f88a9-173">See also</span></span>

[<span data-ttu-id="f88a9-174">Introduktion av API för integrering av system för sökandespårning</span><span class="sxs-lookup"><span data-stu-id="f88a9-174">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="f88a9-175">Exempelfråga för kandidat att anställa</span><span class="sxs-lookup"><span data-stu-id="f88a9-175">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]