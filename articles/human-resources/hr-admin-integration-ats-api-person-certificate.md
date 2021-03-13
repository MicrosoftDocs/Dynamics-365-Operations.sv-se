---
title: Personcertifikat
description: I detta ämne beskrivs entiteten Personcertifikat för Dynamics 365 Human Resources.
author: jaredha
manager: tfehr
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: fa4582dc00341a647f1ea43ed16d9dce8bfcf688
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/05/2021
ms.locfileid: "5125363"
---
# <a name="person-certificate"></a><span data-ttu-id="f5497-103">Personcertifikat</span><span class="sxs-lookup"><span data-stu-id="f5497-103">Person certificate</span></span>

<span data-ttu-id="f5497-104">I detta ämne beskrivs entiteten Personcertifikat för Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="f5497-104">This topic describes the Person certificate entity for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="f5497-105">Fysiskt namn: mshr_hcmpersoncertificateentity</span><span class="sxs-lookup"><span data-stu-id="f5497-105">Physical name: mshr_hcmpersoncertificateentity</span></span>

## <a name="description"></a><span data-ttu-id="f5497-106">beskrivning</span><span class="sxs-lookup"><span data-stu-id="f5497-106">Description</span></span>

<span data-ttu-id="f5497-107">Denna entitet beskriver yrkescertifikaten för en kandidat.</span><span class="sxs-lookup"><span data-stu-id="f5497-107">This entity describes the professional certificates of a candidate.</span></span>

## <a name="json-representation"></a><span data-ttu-id="f5497-108">JSON-representation</span><span class="sxs-lookup"><span data-stu-id="f5497-108">JSON representation</span></span>

```json
{
    "mshr_certificatetypeid": "String",
    "mshr_startdate": "Date",
    "mshr_enddate": "Date",
    "mshr_notes": "String",
    "mshr_partynumber": "String",
    "mshr_primaryfield": "String",
    "_mshr_fk_certificatetype_id_value": "Guid",
    "_mshr_fk_person_id_value": "Guid",
    "mshr_hcmpersoncertificateentityid": "Guid"
}
```

## <a name="properties"></a><span data-ttu-id="f5497-109">Egenskaper</span><span class="sxs-lookup"><span data-stu-id="f5497-109">Properties</span></span>

| <span data-ttu-id="f5497-110">Egenskap</span><span class="sxs-lookup"><span data-stu-id="f5497-110">Property</span></span><br><span data-ttu-id="f5497-111">**Fysiskt namn**</span><span class="sxs-lookup"><span data-stu-id="f5497-111">**Physical name**</span></span><br><span data-ttu-id="f5497-112">**_Typ_**</span><span class="sxs-lookup"><span data-stu-id="f5497-112">**_Type_**</span></span> | <span data-ttu-id="f5497-113">Använd</span><span class="sxs-lookup"><span data-stu-id="f5497-113">Use</span></span> | <span data-ttu-id="f5497-114">beskrivning</span><span class="sxs-lookup"><span data-stu-id="f5497-114">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="f5497-115">**Entitets-ID för personcertifikat**</span><span class="sxs-lookup"><span data-stu-id="f5497-115">**Person Certificate Entity ID**</span></span><br><span data-ttu-id="f5497-116">mshr_hcmpersoncertificateentityid</span><span class="sxs-lookup"><span data-stu-id="f5497-116">mshr_hcmpersoncertificateentityid</span></span><br><span data-ttu-id="f5497-117">*GUID*</span><span class="sxs-lookup"><span data-stu-id="f5497-117">*GUID*</span></span> | <span data-ttu-id="f5497-118">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="f5497-118">Read-only</span></span><br><span data-ttu-id="f5497-119">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="f5497-119">Required</span></span> | <span data-ttu-id="f5497-120">Systemgenererad, unik identifierare för entitetsposten för personcertifikat.</span><span class="sxs-lookup"><span data-stu-id="f5497-120">System-generated unique identifier for the person certificate entity record.</span></span> |
| <span data-ttu-id="f5497-121">**Partnummer**</span><span class="sxs-lookup"><span data-stu-id="f5497-121">**Party Number**</span></span><br><span data-ttu-id="f5497-122">mshr_partynumber</span><span class="sxs-lookup"><span data-stu-id="f5497-122">mshr_partynumber</span></span><br><span data-ttu-id="f5497-123">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="f5497-123">*String*</span></span> | <span data-ttu-id="f5497-124">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="f5497-124">Read/write</span></span><br><span data-ttu-id="f5497-125">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="f5497-125">Required</span></span> | <span data-ttu-id="f5497-126">Part-/person-ID för kandidaten.</span><span class="sxs-lookup"><span data-stu-id="f5497-126">The party (person) ID of the candidate.</span></span> |
| <span data-ttu-id="f5497-127">**Värde för personligt ID**</span><span class="sxs-lookup"><span data-stu-id="f5497-127">**Person ID Value**</span></span><br><span data-ttu-id="f5497-128">_mshr_fk_person_id_value</span><span class="sxs-lookup"><span data-stu-id="f5497-128">_mshr_fk_person_id_value</span></span><br><span data-ttu-id="f5497-129">*GUID*</span><span class="sxs-lookup"><span data-stu-id="f5497-129">*GUID*</span></span> | <span data-ttu-id="f5497-130">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="f5497-130">Read-only</span></span><br><span data-ttu-id="f5497-131">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="f5497-131">Required</span></span><br><span data-ttu-id="f5497-132">Sekundärnyckel: mshr_dirpersonentityid för mshr_dirpersonentity</span><span class="sxs-lookup"><span data-stu-id="f5497-132">Foreign key: mshr_dirpersonentityid of mshr_dirpersonentity</span></span> | <span data-ttu-id="f5497-133">Den systemgenererade, unika identifieraren för entitetsposten för parten (personen).</span><span class="sxs-lookup"><span data-stu-id="f5497-133">The system-generated identifier of the party (person) entity record.</span></span> |
| <span data-ttu-id="f5497-134">**ID för certifikattyp**</span><span class="sxs-lookup"><span data-stu-id="f5497-134">**Certificate Type ID**</span></span><br><span data-ttu-id="f5497-135">mshr_certificatetypeid</span><span class="sxs-lookup"><span data-stu-id="f5497-135">mshr_certificatetypeid</span></span><br><span data-ttu-id="f5497-136">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="f5497-136">*String*</span></span> | <span data-ttu-id="f5497-137">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="f5497-137">Read/write</span></span><br><span data-ttu-id="f5497-138">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="f5497-138">Required</span></span> |  <span data-ttu-id="f5497-139">Identifieraren för den certifikattyp som angetts i Personal.</span><span class="sxs-lookup"><span data-stu-id="f5497-139">The identifier of the certificate type defined in Human Resources.</span></span> |
| <span data-ttu-id="f5497-140">**ID-värde för certifikattyp**</span><span class="sxs-lookup"><span data-stu-id="f5497-140">**Certificate Type ID Value**</span></span><br><span data-ttu-id="f5497-141">_mshr_fk_certificatetype_id_value</span><span class="sxs-lookup"><span data-stu-id="f5497-141">_mshr_fk_certificatetype_id_value</span></span><br><span data-ttu-id="f5497-142">*GUID*</span><span class="sxs-lookup"><span data-stu-id="f5497-142">*GUID*</span></span> | <span data-ttu-id="f5497-143">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="f5497-143">Read-only</span></span><br><span data-ttu-id="f5497-144">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="f5497-144">Required</span></span><br><span data-ttu-id="f5497-145">Sekundärnyckel mshr_hcmcertificatetypeentityid för mshr_hcmcertificatetypeentity</span><span class="sxs-lookup"><span data-stu-id="f5497-145">Foreign key: mshr_hcmcertificatetypeentityid of mshr_hcmcertificatetypeentity</span></span> | <span data-ttu-id="f5497-146">Systemgenererad, unik identifierare för certifikattypen i den associerade entiteten.</span><span class="sxs-lookup"><span data-stu-id="f5497-146">System-generated unique identifier of the certificate type in the associated entity.</span></span> |
| <span data-ttu-id="f5497-147">**Startdatum**</span><span class="sxs-lookup"><span data-stu-id="f5497-147">**Start Date**</span></span><br><span data-ttu-id="f5497-148">mshr_startdate</span><span class="sxs-lookup"><span data-stu-id="f5497-148">mshr_startdate</span></span><br><span data-ttu-id="f5497-149">*Datum/tid*</span><span class="sxs-lookup"><span data-stu-id="f5497-149">*Datetime*</span></span> | <span data-ttu-id="f5497-150">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="f5497-150">Read/write</span></span><br><span data-ttu-id="f5497-151">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="f5497-151">Required</span></span> | <span data-ttu-id="f5497-152">Det datum då certifikatet utfärdades.</span><span class="sxs-lookup"><span data-stu-id="f5497-152">The date at which the certificate was issued.</span></span> |
| <span data-ttu-id="f5497-153">**Slutdatum**</span><span class="sxs-lookup"><span data-stu-id="f5497-153">**End Date**</span></span><br><span data-ttu-id="f5497-154">mshr_enddate</span><span class="sxs-lookup"><span data-stu-id="f5497-154">mshr_enddate</span></span><br><span data-ttu-id="f5497-155">*Datum/tid*</span><span class="sxs-lookup"><span data-stu-id="f5497-155">*Datetime*</span></span> | <span data-ttu-id="f5497-156">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="f5497-156">Read/write</span></span><br><span data-ttu-id="f5497-157">Valfritt</span><span class="sxs-lookup"><span data-stu-id="f5497-157">Optional</span></span> | <span data-ttu-id="f5497-158">Det datum då certifikatet löper ut.</span><span class="sxs-lookup"><span data-stu-id="f5497-158">The date at which the certificate will expire.</span></span> |
| <span data-ttu-id="f5497-159">**Anteckningar**</span><span class="sxs-lookup"><span data-stu-id="f5497-159">**Notes**</span></span><br><span data-ttu-id="f5497-160">mshr_notes</span><span class="sxs-lookup"><span data-stu-id="f5497-160">mshr_notes</span></span><br><span data-ttu-id="f5497-161">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="f5497-161">*String*</span></span> | <span data-ttu-id="f5497-162">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="f5497-162">Read/write</span></span><br><span data-ttu-id="f5497-163">Valfritt</span><span class="sxs-lookup"><span data-stu-id="f5497-163">Optional</span></span> | <span data-ttu-id="f5497-164">Anteckningar att användas av anställande chefer och rekryterare.</span><span class="sxs-lookup"><span data-stu-id="f5497-164">Notes for use by hiring managers and recruiters.</span></span> |
| <span data-ttu-id="f5497-165">**Primärt fält**</span><span class="sxs-lookup"><span data-stu-id="f5497-165">**Primary Field**</span></span><br><span data-ttu-id="f5497-166">mshr_primaryfield</span><span class="sxs-lookup"><span data-stu-id="f5497-166">mshr_primaryfield</span></span><br><span data-ttu-id="f5497-167">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="f5497-167">*String*</span></span> | <span data-ttu-id="f5497-168">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="f5497-168">Read-only</span></span><br><span data-ttu-id="f5497-169">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="f5497-169">Required</span></span> |  <span data-ttu-id="f5497-170">Fält som används som identifierare för entitetsposten.</span><span class="sxs-lookup"><span data-stu-id="f5497-170">Field to be used as an identifier of the entity record.</span></span> <span data-ttu-id="f5497-171">Kombination av partnummer, ID för certifikattyp samt startdatum.</span><span class="sxs-lookup"><span data-stu-id="f5497-171">Combination of party number, certificate type ID, and start date.</span></span> |

## <a name="see-also"></a><span data-ttu-id="f5497-172">Se även</span><span class="sxs-lookup"><span data-stu-id="f5497-172">See also</span></span>

[<span data-ttu-id="f5497-173">Introduktion av API för integrering av system för sökandespårning</span><span class="sxs-lookup"><span data-stu-id="f5497-173">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="f5497-174">Exempelfråga för kandidat att anställa</span><span class="sxs-lookup"><span data-stu-id="f5497-174">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)

