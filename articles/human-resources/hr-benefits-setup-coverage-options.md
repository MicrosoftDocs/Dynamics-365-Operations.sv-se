---
title: Skapa disponeringsalternativ
description: Täckningsalternativ i Microsoft Dynamics 365 Human Resources är täckningsgrad för en deltagares val i en förmånsplan eller ett program.
author: andreabichsel
manager: AnnBe
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 8690dbe00c2316ccf745f5222c3cbaa9c3379f85
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4420636"
---
# <a name="create-coverage-options"></a><span data-ttu-id="db484-103">Skapa disponeringsalternativ</span><span class="sxs-lookup"><span data-stu-id="db484-103">Create coverage options</span></span>

<span data-ttu-id="db484-104">Täckningsalternativ i Microsoft Dynamics 365 Human Resources är täckningsgrad för en deltagares val i en förmånsplan eller ett program.</span><span class="sxs-lookup"><span data-stu-id="db484-104">Coverage options in Microsoft Dynamics 365 Human Resources are levels of coverage for a participant's election in a benefit plan or program.</span></span> <span data-ttu-id="db484-105">Täckningsalternativ kan t.ex. inkludera **endast medarbetare** för en sjukvårdsplan eller **2x lön** för en livförsäkringsplan.</span><span class="sxs-lookup"><span data-stu-id="db484-105">For example, coverage options could include **Employee Only** for a medical plan, or **2x Salary** for a life insurance plan.</span></span> <span data-ttu-id="db484-106">När du har definierat den kan du återanvända alternativ för förmånens omfattning.</span><span class="sxs-lookup"><span data-stu-id="db484-106">Once defined, you can reuse benefit coverage options.</span></span> <span data-ttu-id="db484-107">Du kan associera ett alternativ med en eller flera planer.</span><span class="sxs-lookup"><span data-stu-id="db484-107">You can associate an option with one or more plans.</span></span>

<span data-ttu-id="db484-108">När du definierar omfattningsalternativ kopplar du omfattningsalternativen till en förmånsplantyp.</span><span class="sxs-lookup"><span data-stu-id="db484-108">After you define coverage options, attach the coverage options to a benefit plan type.</span></span> <span data-ttu-id="db484-109">Plantypen associeras sedan med en förmånsplan eller ett program.</span><span class="sxs-lookup"><span data-stu-id="db484-109">The plan type is then associated with a benefit plan or program.</span></span> <span data-ttu-id="db484-110">Omfattningsalternativ som är kopplade till en plantyp blir tillgängligt för alla planer som skapas med den aktuella plantypen.</span><span class="sxs-lookup"><span data-stu-id="db484-110">Coverage options that are associated with a plan type are available to all plans that are created with that plan type.</span></span> 

1. <span data-ttu-id="db484-111">I arbetsytan **Förmånshantering** under **inställningar**, välj **Omfattningsalternativ**.</span><span class="sxs-lookup"><span data-stu-id="db484-111">In the **Benefits management** workspace, under **Setup**, select **Coverage options**.</span></span>

2. <span data-ttu-id="db484-112">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="db484-112">Select **New**.</span></span>

3. <span data-ttu-id="db484-113">Ange värden för de följande fälten:</span><span class="sxs-lookup"><span data-stu-id="db484-113">Specify values for the following fields:</span></span>

   | <span data-ttu-id="db484-114">Fält</span><span class="sxs-lookup"><span data-stu-id="db484-114">Field</span></span> | <span data-ttu-id="db484-115">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="db484-115">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="db484-116">**Omfattningsalternativ**</span><span class="sxs-lookup"><span data-stu-id="db484-116">**Coverage option**</span></span> | <span data-ttu-id="db484-117">Ett unikt namn på omfattningsalternativ.</span><span class="sxs-lookup"><span data-stu-id="db484-117">A unique coverage option name.</span></span> |
   | <span data-ttu-id="db484-118">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="db484-118">**Description**</span></span> | <span data-ttu-id="db484-119">Ange en beskrivning av omfattningsalternativet.</span><span class="sxs-lookup"><span data-stu-id="db484-119">A description of the coverage option.</span></span> |
   | <span data-ttu-id="db484-120">**Omfattningskod**</span><span class="sxs-lookup"><span data-stu-id="db484-120">**Coverage code**</span></span> | <span data-ttu-id="db484-121">Täckningskoder tilldelar minimi- och maximibelopp för varje stödberättigad persontyp.</span><span class="sxs-lookup"><span data-stu-id="db484-121">Coverage codes assign minimum and maximum amounts for each eligible covered person type.</span></span> <span data-ttu-id="db484-122">En variantkod anger vem som täcks av eller hur mycket täckningsbelopp som tillåts för en plantyp.</span><span class="sxs-lookup"><span data-stu-id="db484-122">A coverage code indicates who is covered or the amount of coverage allowed for a plan type.</span></span> <span data-ttu-id="db484-123">Du kan uttrycka beloppet för täckningen som ett dollarbelopp eller en procentsats.</span><span class="sxs-lookup"><span data-stu-id="db484-123">You can express the amount of coverage as a dollar amount or a percentage.</span></span> <span data-ttu-id="db484-124">Exempel:</span><span class="sxs-lookup"><span data-stu-id="db484-124">For example:</span></span></br></br><span data-ttu-id="db484-125">- **Emp+ 1** – för att kvalificeras måste medarbetaren ha ett beroende valt (om fler än en har valts, de är inte längre kvalificerade).</span><span class="sxs-lookup"><span data-stu-id="db484-125">- **Emp+1** – to be qualified, the employee must have one dependent selected (if more than one is selected, they no longer qualify).</span></span></br></br><span data-ttu-id="db484-126">- **Emp+familj** – som ska kvalificeras måste medarbetaren ha minst två beroenden valda.</span><span class="sxs-lookup"><span data-stu-id="db484-126">- **Emp+family** – to be qualified, the employee must have at least two dependents selected.</span></span> |
   | <span data-ttu-id="db484-127">**Maximalt antal**</span><span class="sxs-lookup"><span data-stu-id="db484-127">**Maximum number**</span></span> | <span data-ttu-id="db484-128">Det högsta antalet beroenden.</span><span class="sxs-lookup"><span data-stu-id="db484-128">The maximum number of dependents.</span></span> |
   | <span data-ttu-id="db484-129">**Status**</span><span class="sxs-lookup"><span data-stu-id="db484-129">**Status**</span></span> | <span data-ttu-id="db484-130">Status för omfattningsalternativ.</span><span class="sxs-lookup"><span data-stu-id="db484-130">The status of the coverage option.</span></span> <span data-ttu-id="db484-131">Om omfattningsalternativets status är inaktiverat kan omfattningsalternativet inte väljas på plantyper.</span><span class="sxs-lookup"><span data-stu-id="db484-131">If the Coverage option status is set to Inactive, the Coverage option can’t be selected on plan types.</span></span> |
   | <span data-ttu-id="db484-132">**Procent**</span><span class="sxs-lookup"><span data-stu-id="db484-132">**Percent**</span></span> | <span data-ttu-id="db484-133">Procentbeloppet.</span><span class="sxs-lookup"><span data-stu-id="db484-133">The percent amount.</span></span> <span data-ttu-id="db484-134">Det här fältet är bara aktivt om % x lön har valts i fältet Disponeringskod.</span><span class="sxs-lookup"><span data-stu-id="db484-134">This field is only active if % x Salary was selected in the Coverage code field.</span></span> |
   | <span data-ttu-id="db484-135">**Divisor**</span><span class="sxs-lookup"><span data-stu-id="db484-135">**Divisor**</span></span> | <span data-ttu-id="db484-136">Divisorn som ska användas i beräkningen när du väljer disponeringskoden % x lön.</span><span class="sxs-lookup"><span data-stu-id="db484-136">The divisor to use in the calculation when you select the coverage code % x salary.</span></span> |
   | <span data-ttu-id="db484-137">**Lägsta procentandel**</span><span class="sxs-lookup"><span data-stu-id="db484-137">**Percent minimum**</span></span> | <span data-ttu-id="db484-138">Den lägsta procentsatsen när du väljer koden för procent disponeringskoden.</span><span class="sxs-lookup"><span data-stu-id="db484-138">The minimum percentage when you select the Percentage coverage code.</span></span> |
   | <span data-ttu-id="db484-139">**Högsta procentandel**</span><span class="sxs-lookup"><span data-stu-id="db484-139">**Percent maximum**</span></span> | <span data-ttu-id="db484-140">Den högsta procentsatsen när du väljer koden för procent disponeringskoden.</span><span class="sxs-lookup"><span data-stu-id="db484-140">The maximum percentage when you select the Percentage coverage code.</span></span> |

4. <span data-ttu-id="db484-141">Under **Berättigandealternativ för personlig kontakt**, bifoga lämpligt alternativ för personliga kontakters valbarhet till varje täckningsalternativ.</span><span class="sxs-lookup"><span data-stu-id="db484-141">Under **Personal contact eligibility options**, attach the appropriate personal contacts eligibility option to each coverage option.</span></span>

5. <span data-ttu-id="db484-142">Under **Självbetjäning**, ange värden för följande fält:</span><span class="sxs-lookup"><span data-stu-id="db484-142">Under **Self service**, specify values for the following fields:</span></span>

   | <span data-ttu-id="db484-143">Fält</span><span class="sxs-lookup"><span data-stu-id="db484-143">Field</span></span> | <span data-ttu-id="db484-144">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="db484-144">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="db484-145">**Tillåt medarbetartilläggsbelopp**</span><span class="sxs-lookup"><span data-stu-id="db484-145">**Allow employee contribution amount**</span></span> | <span data-ttu-id="db484-146">Anger om medarbetare ska kunna ändra bidragsbeloppet för självbetjäning för förmåner när de väljer förmåner.</span><span class="sxs-lookup"><span data-stu-id="db484-146">Specifies whether to allow employees to modify the contribution amount on benefits self-service when they select benefits.</span></span> <span data-ttu-id="db484-147">Om du markerar den här kryssrutan kommer systemet att beräkna förmånplanparametrar baserat på det bidragsbelopp som medarbetaren registrerar sig på självbetjäning för förmåner.</span><span class="sxs-lookup"><span data-stu-id="db484-147">If you select this check box, the system will calculate benefit plan parameters based on the contribution amount the employee enters on benefits self-service.</span></span> |
   | <span data-ttu-id="db484-148">**Tillåt medarbetarförsäkringsbelopp**</span><span class="sxs-lookup"><span data-stu-id="db484-148">**Allow employee coverage amount**</span></span> | <span data-ttu-id="db484-149">Anger om medarbetare ska kunna ändra försäkringsbeloppet för självbetjäning för förmåner när de väljer förmåner.</span><span class="sxs-lookup"><span data-stu-id="db484-149">Specifies whether to allow employees to modify the coverage amount on benefits self-service when they select benefits.</span></span> <span data-ttu-id="db484-150">Om du markerar den här kryssrutan kommer systemet att beräkna förmånplanparametrar baserat på det försäkringsbelopp som medarbetaren registrerar sig på i Självbetjäning för medarbetare.</span><span class="sxs-lookup"><span data-stu-id="db484-150">If you select this check box, the system will calculate benefit plan parameters based on the coverage amount the employee enters in Employee self service.</span></span> |

6. <span data-ttu-id="db484-151">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="db484-151">Select **Save**.</span></span> 
