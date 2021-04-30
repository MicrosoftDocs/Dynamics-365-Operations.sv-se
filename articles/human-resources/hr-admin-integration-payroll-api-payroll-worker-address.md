---
title: Lönearbetarens adress
description: Detta ämne tillhandahåller information och en exempelfrågeställning för entiteten för lönearbetaradresser i Dynamics 365 Human Resources.
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
ms.openlocfilehash: 6d93c38b21e953446142fc32cc2a0911616ac61d
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "5882078"
---
# <a name="payroll-worker-address"></a><span data-ttu-id="fce6e-103">Lönearbetarens adress</span><span class="sxs-lookup"><span data-stu-id="fce6e-103">Payroll worker address</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="fce6e-104">Detta ämne tillhandahåller information och en exempelfrågeställning för entiteten för lönearbetaradresser i Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="fce6e-104">This topic provides details and an example query for the Payroll worker address entity in Dynamics 365 Human Resources.</span></span>

## <a name="properties"></a><span data-ttu-id="fce6e-105">Egenskaper</span><span class="sxs-lookup"><span data-stu-id="fce6e-105">Properties</span></span>

| <span data-ttu-id="fce6e-106">Egenskap</span><span class="sxs-lookup"><span data-stu-id="fce6e-106">Property</span></span><br><span data-ttu-id="fce6e-107">**Fysiskt namn**</span><span class="sxs-lookup"><span data-stu-id="fce6e-107">**Physical name**</span></span><br><span data-ttu-id="fce6e-108">**_Typ_**</span><span class="sxs-lookup"><span data-stu-id="fce6e-108">**_Type_**</span></span> | <span data-ttu-id="fce6e-109">Använd</span><span class="sxs-lookup"><span data-stu-id="fce6e-109">Use</span></span> | <span data-ttu-id="fce6e-110">beskrivning</span><span class="sxs-lookup"><span data-stu-id="fce6e-110">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="fce6e-111">**Ort**</span><span class="sxs-lookup"><span data-stu-id="fce6e-111">**City**</span></span><br><span data-ttu-id="fce6e-112">mshr_city</span><span class="sxs-lookup"><span data-stu-id="fce6e-112">mshr_city</span></span><br><span data-ttu-id="fce6e-113">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="fce6e-113">*String*</span></span> | <span data-ttu-id="fce6e-114">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="fce6e-114">Read-only</span></span><br><span data-ttu-id="fce6e-115">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="fce6e-115">Required</span></span> | <span data-ttu-id="fce6e-116">Den ort som angetts för adressen.</span><span class="sxs-lookup"><span data-stu-id="fce6e-116">The city defined for the address.</span></span>   |
| <span data-ttu-id="fce6e-117">**Personalnummer**</span><span class="sxs-lookup"><span data-stu-id="fce6e-117">**Personnel number**</span></span><br><span data-ttu-id="fce6e-118">mshr_personnelnumber</span><span class="sxs-lookup"><span data-stu-id="fce6e-118">mshr_personnelnumber</span></span><br><span data-ttu-id="fce6e-119">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="fce6e-119">*String*</span></span> | <span data-ttu-id="fce6e-120">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="fce6e-120">Read-only</span></span><br><span data-ttu-id="fce6e-121">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="fce6e-121">Required</span></span> | <span data-ttu-id="fce6e-122">Medarbetarens unika personalnummer.</span><span class="sxs-lookup"><span data-stu-id="fce6e-122">The employee's unique personnel number.</span></span>  |
| <span data-ttu-id="fce6e-123">**Land/region**</span><span class="sxs-lookup"><span data-stu-id="fce6e-123">**Country region**</span></span><br><span data-ttu-id="fce6e-124">mshr_countryregionid</span><span class="sxs-lookup"><span data-stu-id="fce6e-124">mshr_countryregionid</span></span><br><span data-ttu-id="fce6e-125">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="fce6e-125">*String*</span></span> | <span data-ttu-id="fce6e-126">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="fce6e-126">Read-only</span></span><br><span data-ttu-id="fce6e-127">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="fce6e-127">Required</span></span> | <span data-ttu-id="fce6e-128">Land/region som angetts för adressen</span><span class="sxs-lookup"><span data-stu-id="fce6e-128">The country region defined for the address</span></span>  |
| <span data-ttu-id="fce6e-129">**Giltig från**</span><span class="sxs-lookup"><span data-stu-id="fce6e-129">**Valid from**</span></span><br><span data-ttu-id="fce6e-130">mshr_postaladdressvalidfrom</span><span class="sxs-lookup"><span data-stu-id="fce6e-130">mshr_postaladdressvalidfrom</span></span><br><span data-ttu-id="fce6e-131">*Datum Tid Offset*</span><span class="sxs-lookup"><span data-stu-id="fce6e-131">*Date Time Offset*</span></span> | <span data-ttu-id="fce6e-132">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="fce6e-132">Read-only</span></span> <br><span data-ttu-id="fce6e-133">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="fce6e-133">Required</span></span> | <span data-ttu-id="fce6e-134">Det datum då adressen börjar gälla.</span><span class="sxs-lookup"><span data-stu-id="fce6e-134">The date the address is valid from.</span></span> |
| <span data-ttu-id="fce6e-135">**Jobbadress**</span><span class="sxs-lookup"><span data-stu-id="fce6e-135">**Worked in address**</span></span><br><span data-ttu-id="fce6e-136">mshr_isworkedinaddressbr>*Int32*</span><span class="sxs-lookup"><span data-stu-id="fce6e-136">mshr_isworkedinaddressbr>*Int32*</span></span> | <span data-ttu-id="fce6e-137">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="fce6e-137">Read-only</span></span><br><span data-ttu-id="fce6e-138">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="fce6e-138">Required</span></span> | <span data-ttu-id="fce6e-139">Anger om adressen anger platsen där medarbetaren arbetar.</span><span class="sxs-lookup"><span data-stu-id="fce6e-139">Denotes if the address is where the employee works.</span></span> |
| <span data-ttu-id="fce6e-140">**Region**</span><span class="sxs-lookup"><span data-stu-id="fce6e-140">**County**</span></span><br><span data-ttu-id="fce6e-141">mshr_county</span><span class="sxs-lookup"><span data-stu-id="fce6e-141">mshr_county</span></span><br><span data-ttu-id="fce6e-142">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="fce6e-142">*String*</span></span> | <span data-ttu-id="fce6e-143">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="fce6e-143">Read-only</span></span><br><span data-ttu-id="fce6e-144">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="fce6e-144">Required</span></span> | <span data-ttu-id="fce6e-145">Den region som angetts för adressen.</span><span class="sxs-lookup"><span data-stu-id="fce6e-145">The county defined for the address.</span></span>  |
| <span data-ttu-id="fce6e-146">**ID för lönearbetarens adress**</span><span class="sxs-lookup"><span data-stu-id="fce6e-146">**Payroll worker address ID**</span></span><br><span data-ttu-id="fce6e-147">mshr_payrollworkeraddressentityid</span><span class="sxs-lookup"><span data-stu-id="fce6e-147">mshr_payrollworkeraddressentityid</span></span><br><span data-ttu-id="fce6e-148">*GUID*</span><span class="sxs-lookup"><span data-stu-id="fce6e-148">*GUID*</span></span> | <span data-ttu-id="fce6e-149">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="fce6e-149">Required</span></span><br><span data-ttu-id="fce6e-150">Systemgenererad</span><span class="sxs-lookup"><span data-stu-id="fce6e-150">System generated</span></span> | <span data-ttu-id="fce6e-151">Ett systemgenererat GUID-värde som unikt identifierar adressen.</span><span class="sxs-lookup"><span data-stu-id="fce6e-151">A system-generated GUID value to uniquely identify the address.</span></span>  |
| <span data-ttu-id="fce6e-152">**Primärt fält**</span><span class="sxs-lookup"><span data-stu-id="fce6e-152">**Primary field**</span></span><br><span data-ttu-id="fce6e-153">mshr_primaryfield</span><span class="sxs-lookup"><span data-stu-id="fce6e-153">mshr_primaryfield</span></span><br><span data-ttu-id="fce6e-154">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="fce6e-154">*String*</span></span> | <span data-ttu-id="fce6e-155">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="fce6e-155">Read-only</span></span><br><span data-ttu-id="fce6e-156">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="fce6e-156">Required</span></span> |  |
| <span data-ttu-id="fce6e-157">**Gata**</span><span class="sxs-lookup"><span data-stu-id="fce6e-157">**Street**</span></span><br><span data-ttu-id="fce6e-158">mshr_street</span><span class="sxs-lookup"><span data-stu-id="fce6e-158">mshr_street</span></span><br><span data-ttu-id="fce6e-159">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="fce6e-159">*String*</span></span> | <span data-ttu-id="fce6e-160">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="fce6e-160">Read-only</span></span><br><span data-ttu-id="fce6e-161">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="fce6e-161">Required</span></span> | <span data-ttu-id="fce6e-162">Den gata som angetts för adressen.</span><span class="sxs-lookup"><span data-stu-id="fce6e-162">The street defined for the address.</span></span> |
| <span data-ttu-id="fce6e-163">**Giltig till**</span><span class="sxs-lookup"><span data-stu-id="fce6e-163">**Valid to**</span></span><br><span data-ttu-id="fce6e-164">mshr_postaladdressvalidto</span><span class="sxs-lookup"><span data-stu-id="fce6e-164">mshr_postaladdressvalidto</span></span><br><span data-ttu-id="fce6e-165">*Datum Tid Offset*</span><span class="sxs-lookup"><span data-stu-id="fce6e-165">*Date Time Offset*</span></span> | <span data-ttu-id="fce6e-166">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="fce6e-166">Read-only</span></span> <br><span data-ttu-id="fce6e-167">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="fce6e-167">Required</span></span> | <span data-ttu-id="fce6e-168">Det datum då adressen slutar gälla.</span><span class="sxs-lookup"><span data-stu-id="fce6e-168">The date the address is valid to.</span></span>  |
| <span data-ttu-id="fce6e-169">**Plats-id**</span><span class="sxs-lookup"><span data-stu-id="fce6e-169">**Location ID**</span></span><br><span data-ttu-id="fce6e-170">mshr_locationidbr>*Sträng*</span><span class="sxs-lookup"><span data-stu-id="fce6e-170">mshr_locationidbr>*String*</span></span> | <span data-ttu-id="fce6e-171">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="fce6e-171">Read-only</span></span> <br><span data-ttu-id="fce6e-172">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="fce6e-172">Required</span></span> | <span data-ttu-id="fce6e-173">Adressens ID.</span><span class="sxs-lookup"><span data-stu-id="fce6e-173">The ID for the address.</span></span>  |
| <span data-ttu-id="fce6e-174">**Postnummer**</span><span class="sxs-lookup"><span data-stu-id="fce6e-174">**Postal code**</span></span><br><span data-ttu-id="fce6e-175">mshr_zipcode</span><span class="sxs-lookup"><span data-stu-id="fce6e-175">mshr_zipcode</span></span><br><span data-ttu-id="fce6e-176">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="fce6e-176">*String*</span></span> | <span data-ttu-id="fce6e-177">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="fce6e-177">Read-only</span></span> <br><span data-ttu-id="fce6e-178">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="fce6e-178">Required</span></span> |<span data-ttu-id="fce6e-179">Det identifieringsnummer som definierats för medarbetaren.</span><span class="sxs-lookup"><span data-stu-id="fce6e-179">The identification number defined for the employee.</span></span>  |
| <span data-ttu-id="fce6e-180">**Bostadsadress**</span><span class="sxs-lookup"><span data-stu-id="fce6e-180">**Lived in address**</span></span><br><span data-ttu-id="fce6e-181">mshr_islivedinaddressbr>*Sträng*</span><span class="sxs-lookup"><span data-stu-id="fce6e-181">mshr_islivedinaddressbr>*String*</span></span> | <span data-ttu-id="fce6e-182">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="fce6e-182">Read-only</span></span><br><span data-ttu-id="fce6e-183">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="fce6e-183">Required</span></span> | <span data-ttu-id="fce6e-184">Anger om adressen anger platsen där medarbetaren bor.</span><span class="sxs-lookup"><span data-stu-id="fce6e-184">Denotes if the address is where the employee lives.</span></span> |
| <span data-ttu-id="fce6e-185">**Delstat**</span><span class="sxs-lookup"><span data-stu-id="fce6e-185">**State**</span></span><br><span data-ttu-id="fce6e-186">mshr_state</span><span class="sxs-lookup"><span data-stu-id="fce6e-186">mshr_state</span></span><br><span data-ttu-id="fce6e-187">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="fce6e-187">*String*</span></span> | <span data-ttu-id="fce6e-188">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="fce6e-188">Read-only</span></span><br><span data-ttu-id="fce6e-189">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="fce6e-189">Required</span></span> | <span data-ttu-id="fce6e-190">Den delstat som angetts för adressen.</span><span class="sxs-lookup"><span data-stu-id="fce6e-190">The state defined for the address.</span></span>  |

## <a name="example-query"></a><span data-ttu-id="fce6e-191">Exempelfrågeställning</span><span class="sxs-lookup"><span data-stu-id="fce6e-191">Example query</span></span>

<span data-ttu-id="fce6e-192">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="fce6e-192">**Request**</span></span>

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollworkeraddressentities?$filter=mshr_personnelnumber eq @personnelnumber and mshr_postaladdressvalidfrom le @asofdate and mshr_postaladdressvalidto ge @asofdate&@personnelnumber='000041'&@asofdate=2021-04-01
```

<span data-ttu-id="fce6e-193">**Svar**</span><span class="sxs-lookup"><span data-stu-id="fce6e-193">**Response**</span></span>

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
