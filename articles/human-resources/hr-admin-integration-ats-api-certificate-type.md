---
title: Certifikattyp
description: I detta ämne beskrivs entiteten Certifikatstyp för Dynamics 365 Human Resources.
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
ms.openlocfilehash: 1d2d53a628ef43d50bd83fd6b62807f44eddd653
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/05/2021
ms.locfileid: "5125723"
---
# <a name="certificate-type"></a><span data-ttu-id="c6c56-103">Certifikattyp</span><span class="sxs-lookup"><span data-stu-id="c6c56-103">Certificate type</span></span>

<span data-ttu-id="c6c56-104">I detta ämne beskrivs entiteten Certifikatstyp för Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="c6c56-104">This topic describes the Certificate type entity for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="c6c56-105">Fysiskt namn: mshr_hcmcertificatetypeentity</span><span class="sxs-lookup"><span data-stu-id="c6c56-105">Physical name: mshr_hcmcertificatetypeentity</span></span>

## <a name="description"></a><span data-ttu-id="c6c56-106">beskrivning</span><span class="sxs-lookup"><span data-stu-id="c6c56-106">Description</span></span>

<span data-ttu-id="c6c56-107">Denna entitet definierar listan över yrkesintygstyper som skapas i Personal.</span><span class="sxs-lookup"><span data-stu-id="c6c56-107">This entity defines the list of professional certificate types set up in Human Resources.</span></span> <span data-ttu-id="c6c56-108">Entiteten är inte specifik för en juridisk person (företag).</span><span class="sxs-lookup"><span data-stu-id="c6c56-108">The entity isn't specific to a legal entity (company).</span></span>

## <a name="json-representation"></a><span data-ttu-id="c6c56-109">JSON-representation</span><span class="sxs-lookup"><span data-stu-id="c6c56-109">JSON representation</span></span>

```json
{
    "mshr_certificatetype": "String",
    "mshr_description": "String",
    "mshr_requirerenewal": Int,
    "mshr_hcmcertificatetypeentityid": "Guid"
}
```

## <a name="properties"></a><span data-ttu-id="c6c56-110">Egenskaper</span><span class="sxs-lookup"><span data-stu-id="c6c56-110">Properties</span></span>

| <span data-ttu-id="c6c56-111">Egenskap</span><span class="sxs-lookup"><span data-stu-id="c6c56-111">Property</span></span><br><span data-ttu-id="c6c56-112">**Fysiskt namn**</span><span class="sxs-lookup"><span data-stu-id="c6c56-112">**Physical name**</span></span><br><span data-ttu-id="c6c56-113">**_Typ_**</span><span class="sxs-lookup"><span data-stu-id="c6c56-113">**_Type_**</span></span> | <span data-ttu-id="c6c56-114">Använd</span><span class="sxs-lookup"><span data-stu-id="c6c56-114">Use</span></span> | <span data-ttu-id="c6c56-115">beskrivning</span><span class="sxs-lookup"><span data-stu-id="c6c56-115">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="c6c56-116">**ID för typ av certifikatsentitet**</span><span class="sxs-lookup"><span data-stu-id="c6c56-116">**Certificate Type Entity ID**</span></span><br><span data-ttu-id="c6c56-117">mshr_hcmcertificatetypeentityid</span><span class="sxs-lookup"><span data-stu-id="c6c56-117">mshr_hcmcertificatetypeentityid</span></span><br><span data-ttu-id="c6c56-118">*GUID*</span><span class="sxs-lookup"><span data-stu-id="c6c56-118">*GUID*</span></span> | <span data-ttu-id="c6c56-119">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="c6c56-119">Read-only</span></span><br><span data-ttu-id="c6c56-120">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="c6c56-120">Required</span></span> 
<span data-ttu-id="c6c56-121">Systemgenererad</span><span class="sxs-lookup"><span data-stu-id="c6c56-121">System-generated</span></span> | <span data-ttu-id="c6c56-122">Unik,primär identifierare för certifikatstypen.</span><span class="sxs-lookup"><span data-stu-id="c6c56-122">Unique primary identifier for the certificate type.</span></span> |
| <span data-ttu-id="c6c56-123">**Certifikatstyp**</span><span class="sxs-lookup"><span data-stu-id="c6c56-123">**Certificate Type**</span></span><br><span data-ttu-id="c6c56-124">mshr_certificatetype</span><span class="sxs-lookup"><span data-stu-id="c6c56-124">mshr_certificatetype</span></span><br><span data-ttu-id="c6c56-125">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="c6c56-125">*String*</span></span> | <span data-ttu-id="c6c56-126">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="c6c56-126">Read/write</span></span><br><span data-ttu-id="c6c56-127">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="c6c56-127">Required</span></span> | <span data-ttu-id="c6c56-128">Unik, användarläsbar identifierare för certifikatstypen.</span><span class="sxs-lookup"><span data-stu-id="c6c56-128">Unique user-readable identifier for the certificate type.</span></span> |
| <span data-ttu-id="c6c56-129">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="c6c56-129">**Description**</span></span><br><span data-ttu-id="c6c56-130">mshr_description</span><span class="sxs-lookup"><span data-stu-id="c6c56-130">mshr_description</span></span><br><span data-ttu-id="c6c56-131">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="c6c56-131">*String*</span></span> | <span data-ttu-id="c6c56-132">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="c6c56-132">Read/write</span></span><br><span data-ttu-id="c6c56-133">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="c6c56-133">Required</span></span> | <span data-ttu-id="c6c56-134">Beskrivning av certifikatstypen.</span><span class="sxs-lookup"><span data-stu-id="c6c56-134">Description of the certificate type.</span></span> |
| <span data-ttu-id="c6c56-135">**Kräv förnyelse**</span><span class="sxs-lookup"><span data-stu-id="c6c56-135">**Require Renewal**</span></span><br><span data-ttu-id="c6c56-136">mshr_requirerenewal</span><span class="sxs-lookup"><span data-stu-id="c6c56-136">mshr_requirerenewal</span></span><br><span data-ttu-id="c6c56-137">*alternativuppsättningen mshr_noyes*</span><span class="sxs-lookup"><span data-stu-id="c6c56-137">*mshr_noyes option set*</span></span> | <span data-ttu-id="c6c56-138">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="c6c56-138">Read/write</span></span><br><span data-ttu-id="c6c56-139">Valfritt</span><span class="sxs-lookup"><span data-stu-id="c6c56-139">Optional</span></span> | <span data-ttu-id="c6c56-140">Anger om förnyelse krävs för certifikatet.</span><span class="sxs-lookup"><span data-stu-id="c6c56-140">Indicates whether renewal is required for the certificate.</span></span> |

## <a name="see-also"></a><span data-ttu-id="c6c56-141">Se även</span><span class="sxs-lookup"><span data-stu-id="c6c56-141">See also</span></span>

[<span data-ttu-id="c6c56-142">Introduktion av API för integrering av system för sökandespårning</span><span class="sxs-lookup"><span data-stu-id="c6c56-142">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="c6c56-143">Exempelfråga för kandidat att anställa</span><span class="sxs-lookup"><span data-stu-id="c6c56-143">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)

