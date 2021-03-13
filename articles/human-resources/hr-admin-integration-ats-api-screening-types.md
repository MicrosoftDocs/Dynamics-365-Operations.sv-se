---
title: Kontrolltyper
description: I detta ämne beskrivs entiteten Gallringstyper för Dynamics 365 Human Resources.
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
ms.openlocfilehash: 227c15acb44e020ea9858961e45c11ad07e18a74
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/05/2021
ms.locfileid: "5126180"
---
# <a name="screening-types"></a><span data-ttu-id="d0f21-103">Kontrolltyper</span><span class="sxs-lookup"><span data-stu-id="d0f21-103">Screening types</span></span>

<span data-ttu-id="d0f21-104">I detta ämne beskrivs entiteten Gallringstyper för Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="d0f21-104">This topic describes the Screening types entity for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="d0f21-105">Fysiskt namn: mshr_hcmscreeningtypeentity</span><span class="sxs-lookup"><span data-stu-id="d0f21-105">Physical name: mshr_hcmscreeningtypeentity</span></span>

## <a name="description"></a><span data-ttu-id="d0f21-106">beskrivning</span><span class="sxs-lookup"><span data-stu-id="d0f21-106">Description</span></span>

<span data-ttu-id="d0f21-107">I den här enheten beskrivs de gallringstyper som företaget har ställt in för gallringsprocesser av medarbetare såväl före som under anställning.</span><span class="sxs-lookup"><span data-stu-id="d0f21-107">This entity describes the screening types set up by the company for pre-employment and ongoing employee screening processes.</span></span>

## <a name="json-representation"></a><span data-ttu-id="d0f21-108">JSON-representation</span><span class="sxs-lookup"><span data-stu-id="d0f21-108">JSON representation</span></span>

```json
{
    "mshr_description": "String",
    "mshr_frequencyunit": Int,
    "mshr_generatefrom": Int,
    "mshr_frequencyinterval": Int,
    "mshr_screeningtypeid": "String",
    "mshr_hcmscreeningtypeentityid": "Guid"
}
```

## <a name="properties"></a><span data-ttu-id="d0f21-109">Egenskaper</span><span class="sxs-lookup"><span data-stu-id="d0f21-109">Properties</span></span>

| <span data-ttu-id="d0f21-110">Egenskap</span><span class="sxs-lookup"><span data-stu-id="d0f21-110">Property</span></span><br><span data-ttu-id="d0f21-111">**Fysiskt namn**</span><span class="sxs-lookup"><span data-stu-id="d0f21-111">**Physical name**</span></span><br><span data-ttu-id="d0f21-112">**_Typ_**</span><span class="sxs-lookup"><span data-stu-id="d0f21-112">**_Type_**</span></span> | <span data-ttu-id="d0f21-113">Använd</span><span class="sxs-lookup"><span data-stu-id="d0f21-113">Use</span></span> | <span data-ttu-id="d0f21-114">beskrivning</span><span class="sxs-lookup"><span data-stu-id="d0f21-114">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="d0f21-115">**Entitets-ID för gallringstyp**</span><span class="sxs-lookup"><span data-stu-id="d0f21-115">**Screening Type Entity ID**</span></span><br><span data-ttu-id="d0f21-116">mshr_hcmscreeningtypeentityid</span><span class="sxs-lookup"><span data-stu-id="d0f21-116">mshr_hcmscreeningtypeentityid</span></span><br><span data-ttu-id="d0f21-117">*GUID*</span><span class="sxs-lookup"><span data-stu-id="d0f21-117">*GUID*</span></span> | <span data-ttu-id="d0f21-118">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="d0f21-118">Read-only</span></span><br><span data-ttu-id="d0f21-119">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="d0f21-119">Required</span></span><br><span data-ttu-id="d0f21-120">Systemgenererad</span><span class="sxs-lookup"><span data-stu-id="d0f21-120">System-generated</span></span> | <span data-ttu-id="d0f21-121">Unik, primär identifierare för posten för gallringstyp.</span><span class="sxs-lookup"><span data-stu-id="d0f21-121">Unique primary identifier for the screening type record.</span></span> |
| <span data-ttu-id="d0f21-122">**ID för gallringstyp**</span><span class="sxs-lookup"><span data-stu-id="d0f21-122">**Screening Type ID**</span></span><br><span data-ttu-id="d0f21-123">mshr_screeningtypeid</span><span class="sxs-lookup"><span data-stu-id="d0f21-123">mshr_screeningtypeid</span></span><br><span data-ttu-id="d0f21-124">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="d0f21-124">*String*</span></span> | <span data-ttu-id="d0f21-125">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="d0f21-125">Read/write</span></span><br><span data-ttu-id="d0f21-126">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="d0f21-126">Required</span></span> | <span data-ttu-id="d0f21-127">Användardefinierad, unik identifierare för gallringstyp.</span><span class="sxs-lookup"><span data-stu-id="d0f21-127">User-defined unique identifier for the screening type.</span></span> |
| <span data-ttu-id="d0f21-128">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="d0f21-128">**Description**</span></span><br><span data-ttu-id="d0f21-129">mshr_description</span><span class="sxs-lookup"><span data-stu-id="d0f21-129">mshr_description</span></span><br><span data-ttu-id="d0f21-130">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="d0f21-130">*String*</span></span> | <span data-ttu-id="d0f21-131">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="d0f21-131">Read/write</span></span><br><span data-ttu-id="d0f21-132">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="d0f21-132">Required</span></span> | <span data-ttu-id="d0f21-133">Beskrivningen av gallringstypen.</span><span class="sxs-lookup"><span data-stu-id="d0f21-133">The description of the screening type.</span></span> |
| <span data-ttu-id="d0f21-134">**Frekvensenhet**</span><span class="sxs-lookup"><span data-stu-id="d0f21-134">**Frequency Unit**</span></span><br><span data-ttu-id="d0f21-135">mshr_frequencyunit</span><span class="sxs-lookup"><span data-stu-id="d0f21-135">mshr_frequencyunit</span></span><br><span data-ttu-id="d0f21-136">*alternativuppsättningen mshr_hcmfrequencyunit*</span><span class="sxs-lookup"><span data-stu-id="d0f21-136">*mshr_hcmfrequencyunit option set*</span></span> | <span data-ttu-id="d0f21-137">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="d0f21-137">Read/write</span></span><br><span data-ttu-id="d0f21-138">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="d0f21-138">Required</span></span> | <span data-ttu-id="d0f21-139">Beskriver hur ofta gallring måste utföras för den tilldelade personen.</span><span class="sxs-lookup"><span data-stu-id="d0f21-139">Describes the frequency with which the screening must be completed for the assigned person.</span></span> |
| <span data-ttu-id="d0f21-140">**Generera från**</span><span class="sxs-lookup"><span data-stu-id="d0f21-140">**Generate From**</span></span><br><span data-ttu-id="d0f21-141">mshr_generatefrom</span><span class="sxs-lookup"><span data-stu-id="d0f21-141">mshr_generatefrom</span></span><br><span data-ttu-id="d0f21-142">*alternativuppsättningen mshr_hcmfrequencygeneratefrom*</span><span class="sxs-lookup"><span data-stu-id="d0f21-142">*mshr_hcmfrequencygeneratefrom option set*</span></span> | <span data-ttu-id="d0f21-143">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="d0f21-143">Read-write</span></span><br><span data-ttu-id="d0f21-144">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="d0f21-144">Required</span></span> | <span data-ttu-id="d0f21-145">Om värdet Frekvens är något annat än "Endast vid en tidpunkt" avgör värdet GenerateFrom det datum från vilket nästa gallringshändelse ska beräknas.</span><span class="sxs-lookup"><span data-stu-id="d0f21-145">If the Frequency value is any value other than “One-time only”, the GenerateFrom value determines the date from which to calculate the next screening event.</span></span> |
| <span data-ttu-id="d0f21-146">**Frekvensintervall**</span><span class="sxs-lookup"><span data-stu-id="d0f21-146">**Frequency Interval**</span></span><br><span data-ttu-id="d0f21-147">mshr_frequencyinterval</span><span class="sxs-lookup"><span data-stu-id="d0f21-147">mshr_frequencyinterval</span></span><br><span data-ttu-id="d0f21-148">*Heltal*</span><span class="sxs-lookup"><span data-stu-id="d0f21-148">*Integer*</span></span> | <span data-ttu-id="d0f21-149">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="d0f21-149">Read-write</span></span><br><span data-ttu-id="d0f21-150">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="d0f21-150">Required</span></span> | <span data-ttu-id="d0f21-151">Om värdet Frekvens är något annat än "Endast vid en tidpunkt" måste du definiera ett intervall för tidsenheterna mellan varje gallringshändelse.</span><span class="sxs-lookup"><span data-stu-id="d0f21-151">If the Frequency value is any value other than “One-time only”, you must define an interval for the units of time between each screening event.</span></span> |

## <a name="see-also"></a><span data-ttu-id="d0f21-152">Se även</span><span class="sxs-lookup"><span data-stu-id="d0f21-152">See also</span></span>

[<span data-ttu-id="d0f21-153">Introduktion av API för integrering av system för sökandespårning</span><span class="sxs-lookup"><span data-stu-id="d0f21-153">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="d0f21-154">Exempelfråga för kandidat att anställa</span><span class="sxs-lookup"><span data-stu-id="d0f21-154">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)
