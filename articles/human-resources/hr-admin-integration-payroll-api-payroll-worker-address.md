---
title: Lönearbetarens adress
description: Detta ämne tillhandahåller information och en exempelfrågeställning för entiteten för lönearbetaradresser i Dynamics 365 Human Resources.
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
ms.openlocfilehash: 964f04261ea95ee6fa2880b0905a669855f6c58a
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020715"
---
# <a name="payroll-worker-address"></a><span data-ttu-id="7e438-103">Lönearbetarens adress</span><span class="sxs-lookup"><span data-stu-id="7e438-103">Payroll worker address</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="7e438-104">Detta ämne tillhandahåller information och en exempelfrågeställning för entiteten för lönearbetaradresser i Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="7e438-104">This topic provides details and an example query for the Payroll worker address entity in Dynamics 365 Human Resources.</span></span>

## <a name="properties"></a><span data-ttu-id="7e438-105">Egenskaper</span><span class="sxs-lookup"><span data-stu-id="7e438-105">Properties</span></span>

| <span data-ttu-id="7e438-106">Egenskap</span><span class="sxs-lookup"><span data-stu-id="7e438-106">Property</span></span><br><span data-ttu-id="7e438-107">**Fysiskt namn**</span><span class="sxs-lookup"><span data-stu-id="7e438-107">**Physical name**</span></span><br><span data-ttu-id="7e438-108">**_Typ_**</span><span class="sxs-lookup"><span data-stu-id="7e438-108">**_Type_**</span></span> | <span data-ttu-id="7e438-109">Använd</span><span class="sxs-lookup"><span data-stu-id="7e438-109">Use</span></span> | <span data-ttu-id="7e438-110">beskrivning</span><span class="sxs-lookup"><span data-stu-id="7e438-110">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="7e438-111">**Ort**</span><span class="sxs-lookup"><span data-stu-id="7e438-111">**City**</span></span><br><span data-ttu-id="7e438-112">mshr_city</span><span class="sxs-lookup"><span data-stu-id="7e438-112">mshr_city</span></span><br><span data-ttu-id="7e438-113">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="7e438-113">*String*</span></span> | <span data-ttu-id="7e438-114">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="7e438-114">Read-only</span></span><br><span data-ttu-id="7e438-115">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="7e438-115">Required</span></span> | <span data-ttu-id="7e438-116">Den ort som angetts för adressen.</span><span class="sxs-lookup"><span data-stu-id="7e438-116">The city defined for the address.</span></span>   |
| <span data-ttu-id="7e438-117">**Personalnummer**</span><span class="sxs-lookup"><span data-stu-id="7e438-117">**Personnel number**</span></span><br><span data-ttu-id="7e438-118">mshr_personnelnumber</span><span class="sxs-lookup"><span data-stu-id="7e438-118">mshr_personnelnumber</span></span><br><span data-ttu-id="7e438-119">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="7e438-119">*String*</span></span> | <span data-ttu-id="7e438-120">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="7e438-120">Read-only</span></span><br><span data-ttu-id="7e438-121">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="7e438-121">Required</span></span> | <span data-ttu-id="7e438-122">Medarbetarens unika personalnummer.</span><span class="sxs-lookup"><span data-stu-id="7e438-122">The employee's unique personnel number.</span></span>  |
| <span data-ttu-id="7e438-123">**Land/region**</span><span class="sxs-lookup"><span data-stu-id="7e438-123">**Country region**</span></span><br><span data-ttu-id="7e438-124">mshr_countryregionid</span><span class="sxs-lookup"><span data-stu-id="7e438-124">mshr_countryregionid</span></span><br><span data-ttu-id="7e438-125">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="7e438-125">*String*</span></span> | <span data-ttu-id="7e438-126">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="7e438-126">Read-only</span></span><br><span data-ttu-id="7e438-127">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="7e438-127">Required</span></span> | <span data-ttu-id="7e438-128">Land/region som angetts för adressen</span><span class="sxs-lookup"><span data-stu-id="7e438-128">The country region defined for the address</span></span>  |
| <span data-ttu-id="7e438-129">**Giltig från**</span><span class="sxs-lookup"><span data-stu-id="7e438-129">**Valid from**</span></span><br><span data-ttu-id="7e438-130">mshr_postaladdressvalidfrom</span><span class="sxs-lookup"><span data-stu-id="7e438-130">mshr_postaladdressvalidfrom</span></span><br><span data-ttu-id="7e438-131">*Datum Tid Offset*</span><span class="sxs-lookup"><span data-stu-id="7e438-131">*Date Time Offset*</span></span> | <span data-ttu-id="7e438-132">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="7e438-132">Read-only</span></span> <br><span data-ttu-id="7e438-133">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="7e438-133">Required</span></span> | <span data-ttu-id="7e438-134">Det datum då adressen börjar gälla.</span><span class="sxs-lookup"><span data-stu-id="7e438-134">The date the address is valid from.</span></span> |
| <span data-ttu-id="7e438-135">**Jobbadress**</span><span class="sxs-lookup"><span data-stu-id="7e438-135">**Worked in address**</span></span><br><span data-ttu-id="7e438-136">mshr_isworkedinaddressbr>*Int32*</span><span class="sxs-lookup"><span data-stu-id="7e438-136">mshr_isworkedinaddressbr>*Int32*</span></span> | <span data-ttu-id="7e438-137">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="7e438-137">Read-only</span></span><br><span data-ttu-id="7e438-138">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="7e438-138">Required</span></span> | <span data-ttu-id="7e438-139">Anger om adressen anger platsen där medarbetaren arbetar.</span><span class="sxs-lookup"><span data-stu-id="7e438-139">Denotes if the address is where the employee works.</span></span> |
| <span data-ttu-id="7e438-140">**Region**</span><span class="sxs-lookup"><span data-stu-id="7e438-140">**County**</span></span><br><span data-ttu-id="7e438-141">mshr_county</span><span class="sxs-lookup"><span data-stu-id="7e438-141">mshr_county</span></span><br><span data-ttu-id="7e438-142">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="7e438-142">*String*</span></span> | <span data-ttu-id="7e438-143">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="7e438-143">Read-only</span></span><br><span data-ttu-id="7e438-144">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="7e438-144">Required</span></span> | <span data-ttu-id="7e438-145">Den region som angetts för adressen.</span><span class="sxs-lookup"><span data-stu-id="7e438-145">The county defined for the address.</span></span>  |
| <span data-ttu-id="7e438-146">**ID för lönearbetarens adress**</span><span class="sxs-lookup"><span data-stu-id="7e438-146">**Payroll worker address ID**</span></span><br><span data-ttu-id="7e438-147">mshr_payrollworkeraddressentityid</span><span class="sxs-lookup"><span data-stu-id="7e438-147">mshr_payrollworkeraddressentityid</span></span><br><span data-ttu-id="7e438-148">*GUID*</span><span class="sxs-lookup"><span data-stu-id="7e438-148">*GUID*</span></span> | <span data-ttu-id="7e438-149">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="7e438-149">Required</span></span><br><span data-ttu-id="7e438-150">Systemgenererad</span><span class="sxs-lookup"><span data-stu-id="7e438-150">System generated</span></span> | <span data-ttu-id="7e438-151">Ett systemgenererat GUID-värde som unikt identifierar adressen.</span><span class="sxs-lookup"><span data-stu-id="7e438-151">A system-generated GUID value to uniquely identify the address.</span></span>  |
| <span data-ttu-id="7e438-152">**Primärt fält**</span><span class="sxs-lookup"><span data-stu-id="7e438-152">**Primary field**</span></span><br><span data-ttu-id="7e438-153">mshr_primaryfield</span><span class="sxs-lookup"><span data-stu-id="7e438-153">mshr_primaryfield</span></span><br><span data-ttu-id="7e438-154">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="7e438-154">*String*</span></span> | <span data-ttu-id="7e438-155">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="7e438-155">Read-only</span></span><br><span data-ttu-id="7e438-156">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="7e438-156">Required</span></span> |  |
| <span data-ttu-id="7e438-157">**Gata**</span><span class="sxs-lookup"><span data-stu-id="7e438-157">**Street**</span></span><br><span data-ttu-id="7e438-158">mshr_street</span><span class="sxs-lookup"><span data-stu-id="7e438-158">mshr_street</span></span><br><span data-ttu-id="7e438-159">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="7e438-159">*String*</span></span> | <span data-ttu-id="7e438-160">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="7e438-160">Read-only</span></span><br><span data-ttu-id="7e438-161">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="7e438-161">Required</span></span> | <span data-ttu-id="7e438-162">Den gata som angetts för adressen.</span><span class="sxs-lookup"><span data-stu-id="7e438-162">The street defined for the address.</span></span> |
| <span data-ttu-id="7e438-163">**Giltig till**</span><span class="sxs-lookup"><span data-stu-id="7e438-163">**Valid to**</span></span><br><span data-ttu-id="7e438-164">mshr_postaladdressvalidto</span><span class="sxs-lookup"><span data-stu-id="7e438-164">mshr_postaladdressvalidto</span></span><br><span data-ttu-id="7e438-165">*Datum Tid Offset*</span><span class="sxs-lookup"><span data-stu-id="7e438-165">*Date Time Offset*</span></span> | <span data-ttu-id="7e438-166">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="7e438-166">Read-only</span></span> <br><span data-ttu-id="7e438-167">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="7e438-167">Required</span></span> | <span data-ttu-id="7e438-168">Det datum då adressen slutar gälla.</span><span class="sxs-lookup"><span data-stu-id="7e438-168">The date the address is valid to.</span></span>  |
| <span data-ttu-id="7e438-169">**Plats-id**</span><span class="sxs-lookup"><span data-stu-id="7e438-169">**Location ID**</span></span><br><span data-ttu-id="7e438-170">mshr_locationidbr>*Sträng*</span><span class="sxs-lookup"><span data-stu-id="7e438-170">mshr_locationidbr>*String*</span></span> | <span data-ttu-id="7e438-171">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="7e438-171">Read-only</span></span> <br><span data-ttu-id="7e438-172">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="7e438-172">Required</span></span> | <span data-ttu-id="7e438-173">Adressens ID.</span><span class="sxs-lookup"><span data-stu-id="7e438-173">The ID for the address.</span></span>  |
| <span data-ttu-id="7e438-174">**Postnummer**</span><span class="sxs-lookup"><span data-stu-id="7e438-174">**Postal code**</span></span><br><span data-ttu-id="7e438-175">mshr_zipcode</span><span class="sxs-lookup"><span data-stu-id="7e438-175">mshr_zipcode</span></span><br><span data-ttu-id="7e438-176">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="7e438-176">*String*</span></span> | <span data-ttu-id="7e438-177">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="7e438-177">Read-only</span></span> <br><span data-ttu-id="7e438-178">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="7e438-178">Required</span></span> |<span data-ttu-id="7e438-179">Det identifieringsnummer som definierats för medarbetaren.</span><span class="sxs-lookup"><span data-stu-id="7e438-179">The identification number defined for the employee.</span></span>  |
| <span data-ttu-id="7e438-180">**Bostadsadress**</span><span class="sxs-lookup"><span data-stu-id="7e438-180">**Lived in address**</span></span><br><span data-ttu-id="7e438-181">mshr_islivedinaddressbr>*Sträng*</span><span class="sxs-lookup"><span data-stu-id="7e438-181">mshr_islivedinaddressbr>*String*</span></span> | <span data-ttu-id="7e438-182">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="7e438-182">Read-only</span></span><br><span data-ttu-id="7e438-183">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="7e438-183">Required</span></span> | <span data-ttu-id="7e438-184">Anger om adressen anger platsen där medarbetaren bor.</span><span class="sxs-lookup"><span data-stu-id="7e438-184">Denotes if the address is where the employee lives.</span></span> |
| <span data-ttu-id="7e438-185">**Delstat**</span><span class="sxs-lookup"><span data-stu-id="7e438-185">**State**</span></span><br><span data-ttu-id="7e438-186">mshr_state</span><span class="sxs-lookup"><span data-stu-id="7e438-186">mshr_state</span></span><br><span data-ttu-id="7e438-187">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="7e438-187">*String*</span></span> | <span data-ttu-id="7e438-188">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="7e438-188">Read-only</span></span><br><span data-ttu-id="7e438-189">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="7e438-189">Required</span></span> | <span data-ttu-id="7e438-190">Den delstat som angetts för adressen.</span><span class="sxs-lookup"><span data-stu-id="7e438-190">The state defined for the address.</span></span>  |

## <a name="example-query"></a><span data-ttu-id="7e438-191">Exempelfrågeställning</span><span class="sxs-lookup"><span data-stu-id="7e438-191">Example query</span></span>

<span data-ttu-id="7e438-192">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="7e438-192">**Request**</span></span>

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollworkeraddressentities?$filter=mshr_personnelnumber eq @personnelnumber and mshr_postaladdressvalidfrom le @asofdate and mshr_postaladdressvalidto ge @asofdate&@personnelnumber='000041'&@asofdate=2021-04-01
```

<span data-ttu-id="7e438-193">**Svar**</span><span class="sxs-lookup"><span data-stu-id="7e438-193">**Response**</span></span>

```json
{
            "mshr_personnelnumber": "000041",
            "mshr_locationid": "000000538",
            "mshr_islivedinaddress": 200000001,
            "mshr_isworkedinaddress": 200000000,
            "mshr_countryregionid": "USA",
            "mshr_zipcode": "99025",
            "mshr_street": "6543 Cypress Ave",
            "mshr_city": "Tacoma",
            "mshr_state": "WA",
            "mshr_county": "KING",
            "mshr_postaladdressvalidfrom": "2012-09-20T20:14:27Z",
            "mshr_postaladdressvalidto": "2154-12-31T23:59:59Z",
            "mshr_primaryfield": "000041 | 000000538 | 9/20/2012 08:14:27 pm",
            "_mshr_fk_worker_id_value": "00000d3c-0000-0000-d5ff-004105000000",
            "mshr_payrollworkeraddressentityid": "000006f0-0000-0000-f90f-014105000000"

}
```
