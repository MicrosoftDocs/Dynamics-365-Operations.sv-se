---
title: Certifikattyp
description: I detta ämne beskrivs entiteten Certifikatstyp för Dynamics 365 Human Resources.
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
ms.openlocfilehash: b8e979f242eb689b730b7f8a8684b3e697adbee6
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/18/2021
ms.locfileid: "6054702"
---
# <a name="certificate-type"></a><span data-ttu-id="aeac4-103">Certifikattyp</span><span class="sxs-lookup"><span data-stu-id="aeac4-103">Certificate type</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="aeac4-104">I detta ämne beskrivs entiteten Certifikatstyp för Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="aeac4-104">This topic describes the Certificate type entity for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="aeac4-105">Fysiskt namn: mshr_hcmcertificatetypeentity</span><span class="sxs-lookup"><span data-stu-id="aeac4-105">Physical name: mshr_hcmcertificatetypeentity</span></span>

## <a name="description"></a><span data-ttu-id="aeac4-106">beskrivning</span><span class="sxs-lookup"><span data-stu-id="aeac4-106">Description</span></span>

<span data-ttu-id="aeac4-107">Denna entitet definierar listan över yrkesintygstyper som skapas i Personal.</span><span class="sxs-lookup"><span data-stu-id="aeac4-107">This entity defines the list of professional certificate types set up in Human Resources.</span></span> <span data-ttu-id="aeac4-108">Entiteten är inte specifik för en juridisk person (företag).</span><span class="sxs-lookup"><span data-stu-id="aeac4-108">The entity isn't specific to a legal entity (company).</span></span>

## <a name="json-representation"></a><span data-ttu-id="aeac4-109">JSON-representation</span><span class="sxs-lookup"><span data-stu-id="aeac4-109">JSON representation</span></span>

```json
{
    "mshr_certificatetype": "String",
    "mshr_description": "String",
    "mshr_requirerenewal": Int,
    "mshr_hcmcertificatetypeentityid": "Guid"
}
```

## <a name="properties"></a><span data-ttu-id="aeac4-110">Egenskaper</span><span class="sxs-lookup"><span data-stu-id="aeac4-110">Properties</span></span>

| <span data-ttu-id="aeac4-111">Egenskap</span><span class="sxs-lookup"><span data-stu-id="aeac4-111">Property</span></span><br><span data-ttu-id="aeac4-112">**Fysiskt namn**</span><span class="sxs-lookup"><span data-stu-id="aeac4-112">**Physical name**</span></span><br><span data-ttu-id="aeac4-113">**_Typ_**</span><span class="sxs-lookup"><span data-stu-id="aeac4-113">**_Type_**</span></span> | <span data-ttu-id="aeac4-114">Använd</span><span class="sxs-lookup"><span data-stu-id="aeac4-114">Use</span></span> | <span data-ttu-id="aeac4-115">beskrivning</span><span class="sxs-lookup"><span data-stu-id="aeac4-115">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="aeac4-116">**ID för typ av certifikatsentitet**</span><span class="sxs-lookup"><span data-stu-id="aeac4-116">**Certificate Type Entity ID**</span></span><br><span data-ttu-id="aeac4-117">mshr_hcmcertificatetypeentityid</span><span class="sxs-lookup"><span data-stu-id="aeac4-117">mshr_hcmcertificatetypeentityid</span></span><br><span data-ttu-id="aeac4-118">*GUID*</span><span class="sxs-lookup"><span data-stu-id="aeac4-118">*GUID*</span></span> | <span data-ttu-id="aeac4-119">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="aeac4-119">Read-only</span></span><br><span data-ttu-id="aeac4-120">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="aeac4-120">Required</span></span> 
<span data-ttu-id="aeac4-121">Systemgenererad</span><span class="sxs-lookup"><span data-stu-id="aeac4-121">System-generated</span></span> | <span data-ttu-id="aeac4-122">Unik,primär identifierare för certifikatstypen.</span><span class="sxs-lookup"><span data-stu-id="aeac4-122">Unique primary identifier for the certificate type.</span></span> |
| <span data-ttu-id="aeac4-123">**Certifikatstyp**</span><span class="sxs-lookup"><span data-stu-id="aeac4-123">**Certificate Type**</span></span><br><span data-ttu-id="aeac4-124">mshr_certificatetype</span><span class="sxs-lookup"><span data-stu-id="aeac4-124">mshr_certificatetype</span></span><br><span data-ttu-id="aeac4-125">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="aeac4-125">*String*</span></span> | <span data-ttu-id="aeac4-126">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="aeac4-126">Read/write</span></span><br><span data-ttu-id="aeac4-127">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="aeac4-127">Required</span></span> | <span data-ttu-id="aeac4-128">Unik, användarläsbar identifierare för certifikatstypen.</span><span class="sxs-lookup"><span data-stu-id="aeac4-128">Unique user-readable identifier for the certificate type.</span></span> |
| <span data-ttu-id="aeac4-129">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="aeac4-129">**Description**</span></span><br><span data-ttu-id="aeac4-130">mshr_description</span><span class="sxs-lookup"><span data-stu-id="aeac4-130">mshr_description</span></span><br><span data-ttu-id="aeac4-131">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="aeac4-131">*String*</span></span> | <span data-ttu-id="aeac4-132">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="aeac4-132">Read/write</span></span><br><span data-ttu-id="aeac4-133">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="aeac4-133">Required</span></span> | <span data-ttu-id="aeac4-134">Beskrivning av certifikatstypen.</span><span class="sxs-lookup"><span data-stu-id="aeac4-134">Description of the certificate type.</span></span> |
| <span data-ttu-id="aeac4-135">**Kräv förnyelse**</span><span class="sxs-lookup"><span data-stu-id="aeac4-135">**Require Renewal**</span></span><br><span data-ttu-id="aeac4-136">mshr_requirerenewal</span><span class="sxs-lookup"><span data-stu-id="aeac4-136">mshr_requirerenewal</span></span><br><span data-ttu-id="aeac4-137">*alternativuppsättningen mshr_noyes*</span><span class="sxs-lookup"><span data-stu-id="aeac4-137">*mshr_noyes option set*</span></span> | <span data-ttu-id="aeac4-138">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="aeac4-138">Read/write</span></span><br><span data-ttu-id="aeac4-139">Valfritt</span><span class="sxs-lookup"><span data-stu-id="aeac4-139">Optional</span></span> | <span data-ttu-id="aeac4-140">Anger om förnyelse krävs för certifikatet.</span><span class="sxs-lookup"><span data-stu-id="aeac4-140">Indicates whether renewal is required for the certificate.</span></span> |

## <a name="see-also"></a><span data-ttu-id="aeac4-141">Se även</span><span class="sxs-lookup"><span data-stu-id="aeac4-141">See also</span></span>

[<span data-ttu-id="aeac4-142">Introduktion av API för integrering av system för sökandespårning</span><span class="sxs-lookup"><span data-stu-id="aeac4-142">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="aeac4-143">Exempelfråga för kandidat att anställa</span><span class="sxs-lookup"><span data-stu-id="aeac4-143">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]