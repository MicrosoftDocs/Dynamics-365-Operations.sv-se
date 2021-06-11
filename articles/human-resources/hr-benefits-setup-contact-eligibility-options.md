---
title: Konfigurera berättigandealternativ för personlig kontakt
description: Konfigurera berättigande alternativ för personliga kontakter i Microsoft Dynamics 365 Human Resources. Personliga kontakter kan vara mottagare eller beroende.
author: andreabichsel
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d85677973f67f0c68de6c5ede62c142524939833
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/18/2021
ms.locfileid: "6054414"
---
# <a name="configure-personal-contact-eligibility-options"></a><span data-ttu-id="bd8bb-104">Konfigurera berättigandealternativ för personlig kontakt</span><span class="sxs-lookup"><span data-stu-id="bd8bb-104">Configure personal contact eligibility options</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="bd8bb-105">I den här artikeln beskrivs hur du konfigurerar olika typer av personliga kontakter att använda i förmåner i Microsoft Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="bd8bb-105">This article shows you how to configure types of personal contacts to use in benefits in Microsoft Dynamics 365 Human Resources.</span></span> <span data-ttu-id="bd8bb-106">Personliga kontakter kan vara mottagare eller beroende.</span><span class="sxs-lookup"><span data-stu-id="bd8bb-106">Personal contacts can be beneficiaries or dependents.</span></span> 

1. <span data-ttu-id="bd8bb-107">I arbetsytan **olämplig** under **inställningar**, välj **Berättigandealternativ för personlig kontakt**.</span><span class="sxs-lookup"><span data-stu-id="bd8bb-107">In the **Benefits management** workspace, under **Setup**, select **Personal contact eligibility options**.</span></span>

2. <span data-ttu-id="bd8bb-108">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="bd8bb-108">Select **New**.</span></span>

3. <span data-ttu-id="bd8bb-109">Ange värden för de följande fälten:</span><span class="sxs-lookup"><span data-stu-id="bd8bb-109">Specify values for the following fields:</span></span>

   | <span data-ttu-id="bd8bb-110">Fält</span><span class="sxs-lookup"><span data-stu-id="bd8bb-110">Field</span></span> | <span data-ttu-id="bd8bb-111">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="bd8bb-111">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="bd8bb-112">**Berättigandealternativ**</span><span class="sxs-lookup"><span data-stu-id="bd8bb-112">**Eligibility option**</span></span> | <span data-ttu-id="bd8bb-113">Ett unikt namn eller en kod som identifierar alternativet för berättigande.</span><span class="sxs-lookup"><span data-stu-id="bd8bb-113">A unique eligibility option name or code to identify the eligibility option.</span></span> |
   | <span data-ttu-id="bd8bb-114">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="bd8bb-114">**Description**</span></span> | <span data-ttu-id="bd8bb-115">En kort beskrivning av berättigandealternativet.</span><span class="sxs-lookup"><span data-stu-id="bd8bb-115">A brief description of the eligibility option.</span></span> |
   | <span data-ttu-id="bd8bb-116">**Berättigandekod för kontakt**</span><span class="sxs-lookup"><span data-stu-id="bd8bb-116">**Contact eligibility code**</span></span> | <span data-ttu-id="bd8bb-117">Den systemkod som bäst beskriver det personliga berättigandealternativet.</span><span class="sxs-lookup"><span data-stu-id="bd8bb-117">The system code that best describes the personal eligibility option.</span></span> <span data-ttu-id="bd8bb-118">Du kan välja mellan:</span><span class="sxs-lookup"><span data-stu-id="bd8bb-118">You can choose from:</span></span> <ul><li><span data-ttu-id="bd8bb-119">Relation</span><span class="sxs-lookup"><span data-stu-id="bd8bb-119">Relationship</span></span></li><li><span data-ttu-id="bd8bb-120">Student</span><span class="sxs-lookup"><span data-stu-id="bd8bb-120">Student</span></span></li><li><span data-ttu-id="bd8bb-121">Överårig beroende</span><span class="sxs-lookup"><span data-stu-id="bd8bb-121">Overage dependent</span></span></li><li><span data-ttu-id="bd8bb-122">Överårig funktionshindrad beroende</span><span class="sxs-lookup"><span data-stu-id="bd8bb-122">Over-aged disabled dependent</span></span></li></ul> |
   | <span data-ttu-id="bd8bb-123">**Status**</span><span class="sxs-lookup"><span data-stu-id="bd8bb-123">**Status**</span></span> | <span data-ttu-id="bd8bb-124">Status för berättigandealternativet.</span><span class="sxs-lookup"><span data-stu-id="bd8bb-124">The status of the eligibility option.</span></span> <span data-ttu-id="bd8bb-125">Om status för ett alternativ är inaktiverad kan du inte välja det personliga kontaktalternativet för personliga kontakter.</span><span class="sxs-lookup"><span data-stu-id="bd8bb-125">If the status for an eligibility option is set to inactive, then you can’t select that personal contact eligibility option for personal contacts.</span></span> |
   | <span data-ttu-id="bd8bb-126">**Relation**</span><span class="sxs-lookup"><span data-stu-id="bd8bb-126">**Relationship**</span></span> | <span data-ttu-id="bd8bb-127">Anger relationen mellan den personliga kontakten och medarbetaren.</span><span class="sxs-lookup"><span data-stu-id="bd8bb-127">Specifies the relationship between the personal contact and the employee.</span></span> <span data-ttu-id="bd8bb-128">Det här fältet är endast aktivt om kontakt villkorskoden är inställd på relation.</span><span class="sxs-lookup"><span data-stu-id="bd8bb-128">This field is only active if the contact eligibility code is set to Relationship.</span></span> |
   | <span data-ttu-id="bd8bb-129">**Ålder**</span><span class="sxs-lookup"><span data-stu-id="bd8bb-129">**Age**</span></span> | <span data-ttu-id="bd8bb-130">Maximal ålder för en berättigad personlig kontakt för förmånsplanen.</span><span class="sxs-lookup"><span data-stu-id="bd8bb-130">The maximum age of an eligible personal contact for the benefit plan.</span></span> <span data-ttu-id="bd8bb-131">Det här fältet är bara aktivt om du väljer en relation.</span><span class="sxs-lookup"><span data-stu-id="bd8bb-131">This field is only active if you select a relationship.</span></span> <span data-ttu-id="bd8bb-132">Denna ålder jämförs med den beräknade åldern för den personliga kontakten.</span><span class="sxs-lookup"><span data-stu-id="bd8bb-132">This age is compared with the calculated age of the personal contact.</span></span> <span data-ttu-id="bd8bb-133">Beräknad ålder är: (täckningsdatum – personliga kontaktens födelsedatum/365).</span><span class="sxs-lookup"><span data-stu-id="bd8bb-133">Calculated age is: (Coverage date – personal contact birth date / 365).</span></span> <span data-ttu-id="bd8bb-134">Det här talet är alltid ett heltal.</span><span class="sxs-lookup"><span data-stu-id="bd8bb-134">This number is always an integer.</span></span> |

4. <span data-ttu-id="bd8bb-135">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="bd8bb-135">Select **Save**.</span></span> 


[!INCLUDE[footer-include](../includes/footer-banner.md)]