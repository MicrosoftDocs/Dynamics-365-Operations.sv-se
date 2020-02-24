---
title: Konfigurera berättigandealternativ för personlig kontakt
description: Konfigurera berättigande alternativ för personliga kontakter i Microsoft Dynamics 365 Human Resources. Personliga kontakter kan vara mottagare eller beroende.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: a50c5e54d224a2f8607284eb105381ffb6ef7ad9
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010621"
---
# <a name="configure-personal-contact-eligibility-options"></a><span data-ttu-id="51d0f-104">Konfigurera berättigandealternativ för personlig kontakt</span><span class="sxs-lookup"><span data-stu-id="51d0f-104">Configure personal contact eligibility options</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="51d0f-105">I den här artikeln beskrivs hur du konfigurerar olika typer av personliga kontakter att använda i förmåner i Microsoft Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="51d0f-105">This article shows you how to configure types of personal contacts to use in benefits in Microsoft Dynamics 365 Human Resources.</span></span> <span data-ttu-id="51d0f-106">Personliga kontakter kan vara mottagare eller beroende.</span><span class="sxs-lookup"><span data-stu-id="51d0f-106">Personal contacts can be beneficiaries or dependents.</span></span> 

1. <span data-ttu-id="51d0f-107">I arbetsytan **olämplig** under **inställningar**, välj **Berättigandealternativ för personlig kontakt**.</span><span class="sxs-lookup"><span data-stu-id="51d0f-107">In the **Benefits management** workspace, under **Setup**, select **Personal contact eligibility options**.</span></span>

2. <span data-ttu-id="51d0f-108">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="51d0f-108">Select **New**.</span></span>

3. <span data-ttu-id="51d0f-109">Ange värden för de följande fälten:</span><span class="sxs-lookup"><span data-stu-id="51d0f-109">Specify values for the following fields:</span></span>

   | <span data-ttu-id="51d0f-110">Fält</span><span class="sxs-lookup"><span data-stu-id="51d0f-110">Field</span></span> | <span data-ttu-id="51d0f-111">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="51d0f-111">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="51d0f-112">**Berättigandealternativ**</span><span class="sxs-lookup"><span data-stu-id="51d0f-112">**Eligibility option**</span></span> | <span data-ttu-id="51d0f-113">Ett unikt namn eller en kod som identifierar alternativet för berättigande.</span><span class="sxs-lookup"><span data-stu-id="51d0f-113">A unique eligibility option name or code to identify the eligibility option.</span></span> |
   | <span data-ttu-id="51d0f-114">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="51d0f-114">**Description**</span></span> | <span data-ttu-id="51d0f-115">En kort beskrivning av berättigandealternativet.</span><span class="sxs-lookup"><span data-stu-id="51d0f-115">A brief description of the eligibility option.</span></span> |
   | <span data-ttu-id="51d0f-116">**Berättigandekod för kontakt**</span><span class="sxs-lookup"><span data-stu-id="51d0f-116">**Contact eligibility code**</span></span> | <span data-ttu-id="51d0f-117">Den systemkod som bäst beskriver det personliga berättigandealternativet.</span><span class="sxs-lookup"><span data-stu-id="51d0f-117">The system code that best describes the personal eligibility option.</span></span> <span data-ttu-id="51d0f-118">Du kan välja mellan:</span><span class="sxs-lookup"><span data-stu-id="51d0f-118">You can choose from:</span></span> <ul><li><span data-ttu-id="51d0f-119">Relation</span><span class="sxs-lookup"><span data-stu-id="51d0f-119">Relationship</span></span></li><li><span data-ttu-id="51d0f-120">Student</span><span class="sxs-lookup"><span data-stu-id="51d0f-120">Student</span></span></li><li><span data-ttu-id="51d0f-121">Överårig beroende</span><span class="sxs-lookup"><span data-stu-id="51d0f-121">Overage dependent</span></span></li><li><span data-ttu-id="51d0f-122">Överårig funktionshindrad beroende</span><span class="sxs-lookup"><span data-stu-id="51d0f-122">Over-aged disabled dependent</span></span></li></ul> |
   | <span data-ttu-id="51d0f-123">**Status**</span><span class="sxs-lookup"><span data-stu-id="51d0f-123">**Status**</span></span> | <span data-ttu-id="51d0f-124">Status för berättigandealternativet.</span><span class="sxs-lookup"><span data-stu-id="51d0f-124">The status of the eligibility option.</span></span> <span data-ttu-id="51d0f-125">Om status för ett alternativ är inaktiverad kan du inte välja det personliga kontaktalternativet för personliga kontakter.</span><span class="sxs-lookup"><span data-stu-id="51d0f-125">If the status for an eligibility option is set to inactive, then you can’t select that personal contact eligibility option for personal contacts.</span></span> |
   | <span data-ttu-id="51d0f-126">**Relation**</span><span class="sxs-lookup"><span data-stu-id="51d0f-126">**Relationship**</span></span> | <span data-ttu-id="51d0f-127">Anger relationen mellan den personliga kontakten och medarbetaren.</span><span class="sxs-lookup"><span data-stu-id="51d0f-127">Specifies the relationship between the personal contact and the employee.</span></span> <span data-ttu-id="51d0f-128">Det här fältet är endast aktivt om kontakt villkorskoden är inställd på relation.</span><span class="sxs-lookup"><span data-stu-id="51d0f-128">This field is only active if the contact eligibility code is set to Relationship.</span></span> |
   | <span data-ttu-id="51d0f-129">**Ålder**</span><span class="sxs-lookup"><span data-stu-id="51d0f-129">**Age**</span></span> | <span data-ttu-id="51d0f-130">Maximal ålder för en berättigad personlig kontakt för förmånsplanen.</span><span class="sxs-lookup"><span data-stu-id="51d0f-130">The maximum age of an eligible personal contact for the benefit plan.</span></span> <span data-ttu-id="51d0f-131">Det här fältet är bara aktivt om du väljer en relation.</span><span class="sxs-lookup"><span data-stu-id="51d0f-131">This field is only active if you select a relationship.</span></span> <span data-ttu-id="51d0f-132">Denna ålder jämförs med den beräknade åldern för den personliga kontakten.</span><span class="sxs-lookup"><span data-stu-id="51d0f-132">This age is compared with the calculated age of the personal contact.</span></span> <span data-ttu-id="51d0f-133">Beräknad ålder är: (täckningsdatum – personliga kontaktens födelsedatum/365).</span><span class="sxs-lookup"><span data-stu-id="51d0f-133">Calculated age is: (Coverage date – personal contact birth date / 365).</span></span> <span data-ttu-id="51d0f-134">Det här talet är alltid ett heltal.</span><span class="sxs-lookup"><span data-stu-id="51d0f-134">This number is always an integer.</span></span> |

4. <span data-ttu-id="51d0f-135">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="51d0f-135">Select **Save**.</span></span> 
