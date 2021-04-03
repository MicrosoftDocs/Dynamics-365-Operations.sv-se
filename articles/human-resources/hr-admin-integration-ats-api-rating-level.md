---
title: Bedömningsnivå
description: Detta ämne beskriver entiteten Bedömningsnivå för Dynamics 365 Human Resources.
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
ms.openlocfilehash: 2dbdbea7087d8bca8563da10d1bf9a97df24e8b3
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/17/2021
ms.locfileid: "5464752"
---
# <a name="rating-level"></a><span data-ttu-id="7e136-103">Bedömningsnivå</span><span class="sxs-lookup"><span data-stu-id="7e136-103">Rating level</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="7e136-104">Detta ämne beskriver entiteten Bedömningsnivå för Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="7e136-104">This topic describes the Rating level entity for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="7e136-105">Fysiskt namn: mshr_hcmratinglevelentity</span><span class="sxs-lookup"><span data-stu-id="7e136-105">Physical name: mshr_hcmratinglevelentity</span></span>

## <a name="description"></a><span data-ttu-id="7e136-106">beskrivning</span><span class="sxs-lookup"><span data-stu-id="7e136-106">Description</span></span>

<span data-ttu-id="7e136-107">Denna entitet tillhandahåller tillgängliga bedömningsnivåer för färdigheter.</span><span class="sxs-lookup"><span data-stu-id="7e136-107">This entity provides the available rating levels for skills.</span></span> <span data-ttu-id="7e136-108">Bedömningsnivåerna gäller för alla juridiska personer.</span><span class="sxs-lookup"><span data-stu-id="7e136-108">Rating levels apply across all legal entities.</span></span>

## <a name="json-representation"></a><span data-ttu-id="7e136-109">JSON-representation</span><span class="sxs-lookup"><span data-stu-id="7e136-109">JSON representation</span></span>

```json
{
    "mshr_description": "String",
    "mshr_factor": Int,
    "mshr_note": "String",
    "mshr_ratinglevelid": "String",
    "mshr_ratingmodelid": "String",
    "mshr_primaryfield": "String",
    "_mshr_fk_ratingmodelentity_id_value": "Guid",
    "mshr_hcmratinglevelentityid": "Guid"
}
```

## <a name="properties"></a><span data-ttu-id="7e136-110">Egenskaper</span><span class="sxs-lookup"><span data-stu-id="7e136-110">Properties</span></span>

| <span data-ttu-id="7e136-111">Egenskap</span><span class="sxs-lookup"><span data-stu-id="7e136-111">Property</span></span><br><span data-ttu-id="7e136-112">**Fysiskt namn**</span><span class="sxs-lookup"><span data-stu-id="7e136-112">**Physical name**</span></span><br><span data-ttu-id="7e136-113">**_Typ_**</span><span class="sxs-lookup"><span data-stu-id="7e136-113">**_Type_**</span></span> | <span data-ttu-id="7e136-114">Använd</span><span class="sxs-lookup"><span data-stu-id="7e136-114">Use</span></span> | <span data-ttu-id="7e136-115">beskrivning</span><span class="sxs-lookup"><span data-stu-id="7e136-115">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="7e136-116">**Entitets-ID för bedömningsnivå**</span><span class="sxs-lookup"><span data-stu-id="7e136-116">**Rating Level Entity ID**</span></span><br><span data-ttu-id="7e136-117">mshr_hcmratinglevelentityid</span><span class="sxs-lookup"><span data-stu-id="7e136-117">mshr_hcmratinglevelentityid</span></span><br><span data-ttu-id="7e136-118">*GUID*</span><span class="sxs-lookup"><span data-stu-id="7e136-118">*GUID*</span></span> | <span data-ttu-id="7e136-119">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="7e136-119">Read-only</span></span><br><span data-ttu-id="7e136-120">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="7e136-120">Required</span></span><br><span data-ttu-id="7e136-121">Systemgenererad</span><span class="sxs-lookup"><span data-stu-id="7e136-121">System-generated</span></span> | <span data-ttu-id="7e136-122">Systemgenererad, unik identifierare för nivån.</span><span class="sxs-lookup"><span data-stu-id="7e136-122">The system-generated unique identifier for the level.</span></span> |
| <span data-ttu-id="7e136-123">**ID för bedömningsnivå**</span><span class="sxs-lookup"><span data-stu-id="7e136-123">**Rating Level ID**</span></span><br><span data-ttu-id="7e136-124">mshr_ratinglevelid</span><span class="sxs-lookup"><span data-stu-id="7e136-124">mshr_ratinglevelid</span></span><br><span data-ttu-id="7e136-125">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="7e136-125">*String*</span></span> | <span data-ttu-id="7e136-126">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="7e136-126">Read/write</span></span><br><span data-ttu-id="7e136-127">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="7e136-127">Required</span></span> | <span data-ttu-id="7e136-128">Användarläsbar, unik identifierare för nivån.</span><span class="sxs-lookup"><span data-stu-id="7e136-128">User-readable unique identifier for the level.</span></span> |
| <span data-ttu-id="7e136-129">**ID för bedömningsmodell**</span><span class="sxs-lookup"><span data-stu-id="7e136-129">**Rating Model ID**</span></span><br><span data-ttu-id="7e136-130">mshr_ratingmodelid</span><span class="sxs-lookup"><span data-stu-id="7e136-130">mshr_ratingmodelid</span></span><br><span data-ttu-id="7e136-131">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="7e136-131">*String*</span></span> | <span data-ttu-id="7e136-132">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="7e136-132">Read/write</span></span><br><span data-ttu-id="7e136-133">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="7e136-133">Required</span></span> | <span data-ttu-id="7e136-134">Bedömningsmodellen som bedömningsnivån tillhör.</span><span class="sxs-lookup"><span data-stu-id="7e136-134">The rating model to which the rating level belongs.</span></span> |
| <span data-ttu-id="7e136-135">**Entitets-ID för bedömningsmodell**</span><span class="sxs-lookup"><span data-stu-id="7e136-135">**Rating Model Entity ID**</span></span><br><span data-ttu-id="7e136-136">_mshr_fk_ratingmodelentity_id_value</span><span class="sxs-lookup"><span data-stu-id="7e136-136">_mshr_fk_ratingmodelentity_id_value</span></span><br><span data-ttu-id="7e136-137">*GUID*</span><span class="sxs-lookup"><span data-stu-id="7e136-137">*GUID*</span></span> | <span data-ttu-id="7e136-138">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="7e136-138">Read-only</span></span><br><span data-ttu-id="7e136-139">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="7e136-139">Required</span></span><br><span data-ttu-id="7e136-140">Sekundärnyckel: mshr_hcmratingmodelentityid för mshr_hcmratingmodelentity</span><span class="sxs-lookup"><span data-stu-id="7e136-140">Foreign key: mshr_hcmratingmodelentityid of mshr_hcmratingmodelentity</span></span> | <span data-ttu-id="7e136-141">Den systemgenererade identifieraren för den bedömningsmodell som bedömningsnivån tillhör.</span><span class="sxs-lookup"><span data-stu-id="7e136-141">The system-generated identifier for the rating model to which the rating level belongs.</span></span> |
| <span data-ttu-id="7e136-142">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="7e136-142">**Description**</span></span><br><span data-ttu-id="7e136-143">mshr_description</span><span class="sxs-lookup"><span data-stu-id="7e136-143">mshr_description</span></span><br><span data-ttu-id="7e136-144">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="7e136-144">*String*</span></span> | <span data-ttu-id="7e136-145">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="7e136-145">Read/write</span></span><br><span data-ttu-id="7e136-146">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="7e136-146">Required</span></span> | <span data-ttu-id="7e136-147">Beskrivningen av bedömningsnivån.</span><span class="sxs-lookup"><span data-stu-id="7e136-147">The description of the rating level.</span></span> |
| <span data-ttu-id="7e136-148">**Faktor**</span><span class="sxs-lookup"><span data-stu-id="7e136-148">**Factor**</span></span><br><span data-ttu-id="7e136-149">mshr_factor</span><span class="sxs-lookup"><span data-stu-id="7e136-149">mshr_factor</span></span><br><span data-ttu-id="7e136-150">*Heltal*</span><span class="sxs-lookup"><span data-stu-id="7e136-150">*Integer*</span></span> | <span data-ttu-id="7e136-151">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="7e136-151">Read/write</span></span><br><span data-ttu-id="7e136-152">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="7e136-152">Required</span></span> | <span data-ttu-id="7e136-153">Faktorn för bedömningsnivån.</span><span class="sxs-lookup"><span data-stu-id="7e136-153">The factor for the rating level.</span></span> <span data-ttu-id="7e136-154">När du jämför artiklar med olika bedömningsnivåer används faktorn till att normalisera poängen.</span><span class="sxs-lookup"><span data-stu-id="7e136-154">When you compare items with a different number of rating levels, the factor is used to normalize the scores.</span></span> <span data-ttu-id="7e136-155">Värdet måste vara ett heltal mellan 0 och 9.</span><span class="sxs-lookup"><span data-stu-id="7e136-155">The value must be an integer between 0 and 9.</span></span> |
| <span data-ttu-id="7e136-156">**Obs!**</span><span class="sxs-lookup"><span data-stu-id="7e136-156">**Note**</span></span><br><span data-ttu-id="7e136-157">mshr_note</span><span class="sxs-lookup"><span data-stu-id="7e136-157">mshr_note</span></span><br><span data-ttu-id="7e136-158">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="7e136-158">*String*</span></span> | <span data-ttu-id="7e136-159">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="7e136-159">Read/write</span></span><br><span data-ttu-id="7e136-160">Valfritt</span><span class="sxs-lookup"><span data-stu-id="7e136-160">Optional</span></span> | <span data-ttu-id="7e136-161">Eventuella anteckningar som är kopplade till bedömningsnivån.</span><span class="sxs-lookup"><span data-stu-id="7e136-161">Any notes associated with the rating level.</span></span> |
| <span data-ttu-id="7e136-162">**Primärt fält**</span><span class="sxs-lookup"><span data-stu-id="7e136-162">**Primary Field**</span></span><br><span data-ttu-id="7e136-163">mshr_primaryfield</span><span class="sxs-lookup"><span data-stu-id="7e136-163">mshr_primaryfield</span></span><br><span data-ttu-id="7e136-164">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="7e136-164">*String*</span></span> | <span data-ttu-id="7e136-165">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="7e136-165">Read-only</span></span><br><span data-ttu-id="7e136-166">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="7e136-166">Required</span></span> | <span data-ttu-id="7e136-167">Fält som används som identifierare för entitetsposten.</span><span class="sxs-lookup"><span data-stu-id="7e136-167">Field to be used as an identifier of the entity record.</span></span> <span data-ttu-id="7e136-168">Kombination av bedömningsnivå-ID och bedömningsmodell-ID.</span><span class="sxs-lookup"><span data-stu-id="7e136-168">Combination of rating level ID and rating model ID.</span></span> |

## <a name="see-also"></a><span data-ttu-id="7e136-169">Se även</span><span class="sxs-lookup"><span data-stu-id="7e136-169">See also</span></span>

[<span data-ttu-id="7e136-170">Introduktion av API för integrering av system för sökandespårning</span><span class="sxs-lookup"><span data-stu-id="7e136-170">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="7e136-171">Exempelfråga för kandidat att anställa</span><span class="sxs-lookup"><span data-stu-id="7e136-171">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]