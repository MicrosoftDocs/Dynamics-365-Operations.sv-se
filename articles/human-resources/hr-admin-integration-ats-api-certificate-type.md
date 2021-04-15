---
title: Certifikattyp
description: I detta ämne beskrivs entiteten Certifikatstyp för Dynamics 365 Human Resources.
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
ms.openlocfilehash: fe5713b6b5f38ad7f6857b36c6b2f63a1dc0c320
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5798403"
---
# <a name="certificate-type"></a><span data-ttu-id="0ede8-103">Certifikattyp</span><span class="sxs-lookup"><span data-stu-id="0ede8-103">Certificate type</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="0ede8-104">I detta ämne beskrivs entiteten Certifikatstyp för Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="0ede8-104">This topic describes the Certificate type entity for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="0ede8-105">Fysiskt namn: mshr_hcmcertificatetypeentity</span><span class="sxs-lookup"><span data-stu-id="0ede8-105">Physical name: mshr_hcmcertificatetypeentity</span></span>

## <a name="description"></a><span data-ttu-id="0ede8-106">beskrivning</span><span class="sxs-lookup"><span data-stu-id="0ede8-106">Description</span></span>

<span data-ttu-id="0ede8-107">Denna entitet definierar listan över yrkesintygstyper som skapas i Personal.</span><span class="sxs-lookup"><span data-stu-id="0ede8-107">This entity defines the list of professional certificate types set up in Human Resources.</span></span> <span data-ttu-id="0ede8-108">Entiteten är inte specifik för en juridisk person (företag).</span><span class="sxs-lookup"><span data-stu-id="0ede8-108">The entity isn't specific to a legal entity (company).</span></span>

## <a name="json-representation"></a><span data-ttu-id="0ede8-109">JSON-representation</span><span class="sxs-lookup"><span data-stu-id="0ede8-109">JSON representation</span></span>

```json
{
    "mshr_certificatetype": "String",
    "mshr_description": "String",
    "mshr_requirerenewal": Int,
    "mshr_hcmcertificatetypeentityid": "Guid"
}
```

## <a name="properties"></a><span data-ttu-id="0ede8-110">Egenskaper</span><span class="sxs-lookup"><span data-stu-id="0ede8-110">Properties</span></span>

| <span data-ttu-id="0ede8-111">Egenskap</span><span class="sxs-lookup"><span data-stu-id="0ede8-111">Property</span></span><br><span data-ttu-id="0ede8-112">**Fysiskt namn**</span><span class="sxs-lookup"><span data-stu-id="0ede8-112">**Physical name**</span></span><br><span data-ttu-id="0ede8-113">**_Typ_**</span><span class="sxs-lookup"><span data-stu-id="0ede8-113">**_Type_**</span></span> | <span data-ttu-id="0ede8-114">Använd</span><span class="sxs-lookup"><span data-stu-id="0ede8-114">Use</span></span> | <span data-ttu-id="0ede8-115">beskrivning</span><span class="sxs-lookup"><span data-stu-id="0ede8-115">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="0ede8-116">**ID för typ av certifikatsentitet**</span><span class="sxs-lookup"><span data-stu-id="0ede8-116">**Certificate Type Entity ID**</span></span><br><span data-ttu-id="0ede8-117">mshr_hcmcertificatetypeentityid</span><span class="sxs-lookup"><span data-stu-id="0ede8-117">mshr_hcmcertificatetypeentityid</span></span><br><span data-ttu-id="0ede8-118">*GUID*</span><span class="sxs-lookup"><span data-stu-id="0ede8-118">*GUID*</span></span> | <span data-ttu-id="0ede8-119">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="0ede8-119">Read-only</span></span><br><span data-ttu-id="0ede8-120">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="0ede8-120">Required</span></span> 
<span data-ttu-id="0ede8-121">Systemgenererad</span><span class="sxs-lookup"><span data-stu-id="0ede8-121">System-generated</span></span> | <span data-ttu-id="0ede8-122">Unik,primär identifierare för certifikatstypen.</span><span class="sxs-lookup"><span data-stu-id="0ede8-122">Unique primary identifier for the certificate type.</span></span> |
| <span data-ttu-id="0ede8-123">**Certifikatstyp**</span><span class="sxs-lookup"><span data-stu-id="0ede8-123">**Certificate Type**</span></span><br><span data-ttu-id="0ede8-124">mshr_certificatetype</span><span class="sxs-lookup"><span data-stu-id="0ede8-124">mshr_certificatetype</span></span><br><span data-ttu-id="0ede8-125">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="0ede8-125">*String*</span></span> | <span data-ttu-id="0ede8-126">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="0ede8-126">Read/write</span></span><br><span data-ttu-id="0ede8-127">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="0ede8-127">Required</span></span> | <span data-ttu-id="0ede8-128">Unik, användarläsbar identifierare för certifikatstypen.</span><span class="sxs-lookup"><span data-stu-id="0ede8-128">Unique user-readable identifier for the certificate type.</span></span> |
| <span data-ttu-id="0ede8-129">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="0ede8-129">**Description**</span></span><br><span data-ttu-id="0ede8-130">mshr_description</span><span class="sxs-lookup"><span data-stu-id="0ede8-130">mshr_description</span></span><br><span data-ttu-id="0ede8-131">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="0ede8-131">*String*</span></span> | <span data-ttu-id="0ede8-132">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="0ede8-132">Read/write</span></span><br><span data-ttu-id="0ede8-133">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="0ede8-133">Required</span></span> | <span data-ttu-id="0ede8-134">Beskrivning av certifikatstypen.</span><span class="sxs-lookup"><span data-stu-id="0ede8-134">Description of the certificate type.</span></span> |
| <span data-ttu-id="0ede8-135">**Kräv förnyelse**</span><span class="sxs-lookup"><span data-stu-id="0ede8-135">**Require Renewal**</span></span><br><span data-ttu-id="0ede8-136">mshr_requirerenewal</span><span class="sxs-lookup"><span data-stu-id="0ede8-136">mshr_requirerenewal</span></span><br><span data-ttu-id="0ede8-137">*alternativuppsättningen mshr_noyes*</span><span class="sxs-lookup"><span data-stu-id="0ede8-137">*mshr_noyes option set*</span></span> | <span data-ttu-id="0ede8-138">Skrivskydd</span><span class="sxs-lookup"><span data-stu-id="0ede8-138">Read/write</span></span><br><span data-ttu-id="0ede8-139">Valfritt</span><span class="sxs-lookup"><span data-stu-id="0ede8-139">Optional</span></span> | <span data-ttu-id="0ede8-140">Anger om förnyelse krävs för certifikatet.</span><span class="sxs-lookup"><span data-stu-id="0ede8-140">Indicates whether renewal is required for the certificate.</span></span> |

## <a name="see-also"></a><span data-ttu-id="0ede8-141">Se även</span><span class="sxs-lookup"><span data-stu-id="0ede8-141">See also</span></span>

[<span data-ttu-id="0ede8-142">Introduktion av API för integrering av system för sökandespårning</span><span class="sxs-lookup"><span data-stu-id="0ede8-142">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="0ede8-143">Exempelfråga för kandidat att anställa</span><span class="sxs-lookup"><span data-stu-id="0ede8-143">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]