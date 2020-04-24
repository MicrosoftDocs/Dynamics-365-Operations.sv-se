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
ms.openlocfilehash: 021fea7604af2fff833ddc6868d55a316ef70aae
ms.sourcegitcommit: a9461650d11d6845e1942865ebf7e35f75f61ad3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/06/2020
ms.locfileid: "3230187"
---
# <a name="create-coverage-options"></a><span data-ttu-id="2257f-103">Skapa disponeringsalternativ</span><span class="sxs-lookup"><span data-stu-id="2257f-103">Create coverage options</span></span>

<span data-ttu-id="2257f-104">Täckningsalternativ i Microsoft Dynamics 365 Human Resources är täckningsgrad för en deltagares val i en förmånsplan eller ett program.</span><span class="sxs-lookup"><span data-stu-id="2257f-104">Coverage options in Microsoft Dynamics 365 Human Resources are levels of coverage for a participant's election in a benefit plan or program.</span></span> <span data-ttu-id="2257f-105">Täckningsalternativ kan t.ex. inkludera **endast medarbetare** för en sjukvårdsplan eller **2x lön** för en livförsäkringsplan.</span><span class="sxs-lookup"><span data-stu-id="2257f-105">For example, coverage options could include **Employee Only** for a medical plan, or **2x Salary** for a life insurance plan.</span></span> <span data-ttu-id="2257f-106">När du har definierat den kan du återanvända alternativ för förmånens omfattning.</span><span class="sxs-lookup"><span data-stu-id="2257f-106">Once defined, you can reuse benefit coverage options.</span></span> <span data-ttu-id="2257f-107">Du kan associera ett alternativ med en eller flera planer.</span><span class="sxs-lookup"><span data-stu-id="2257f-107">You can associate an option with one or more plans.</span></span>

<span data-ttu-id="2257f-108">När du definierar omfattningsalternativ kopplar du omfattningsalternativen till en förmånsplantyp.</span><span class="sxs-lookup"><span data-stu-id="2257f-108">After you define coverage options, attach the coverage options to a benefit plan type.</span></span> <span data-ttu-id="2257f-109">Plantypen associeras sedan med en förmånsplan eller ett program.</span><span class="sxs-lookup"><span data-stu-id="2257f-109">The plan type is then associated with a benefit plan or program.</span></span> <span data-ttu-id="2257f-110">Omfattningsalternativ som är kopplade till en plantyp blir tillgängligt för alla planer som skapas med den aktuella plantypen.</span><span class="sxs-lookup"><span data-stu-id="2257f-110">Coverage options that are associated with a plan type are available to all plans that are created with that plan type.</span></span> 

1. <span data-ttu-id="2257f-111">I arbetsytan **Förmånshantering** under **inställningar**, välj **Omfattningsalternativ**.</span><span class="sxs-lookup"><span data-stu-id="2257f-111">In the **Benefits management** workspace, under **Setup**, select **Coverage options**.</span></span>

2. <span data-ttu-id="2257f-112">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="2257f-112">Select **New**.</span></span>

3. <span data-ttu-id="2257f-113">Ange värden för de följande fälten:</span><span class="sxs-lookup"><span data-stu-id="2257f-113">Specify values for the following fields:</span></span>

   | <span data-ttu-id="2257f-114">Fält</span><span class="sxs-lookup"><span data-stu-id="2257f-114">Field</span></span> | <span data-ttu-id="2257f-115">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="2257f-115">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="2257f-116">**Omfattningsalternativ**</span><span class="sxs-lookup"><span data-stu-id="2257f-116">**Coverage option**</span></span> | <span data-ttu-id="2257f-117">Ett unikt namn på omfattningsalternativ.</span><span class="sxs-lookup"><span data-stu-id="2257f-117">A unique coverage option name.</span></span> |
   | <span data-ttu-id="2257f-118">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="2257f-118">**Description**</span></span> | <span data-ttu-id="2257f-119">Ange en beskrivning av omfattningsalternativet.</span><span class="sxs-lookup"><span data-stu-id="2257f-119">A description of the coverage option.</span></span> |
   | <span data-ttu-id="2257f-120">**Omfattningskod**</span><span class="sxs-lookup"><span data-stu-id="2257f-120">**Coverage code**</span></span> | <span data-ttu-id="2257f-121">Täckningskoder tilldelar minimi- och maximibelopp för varje stödberättigad persontyp.</span><span class="sxs-lookup"><span data-stu-id="2257f-121">Coverage codes assign minimum and maximum amounts for each eligible covered person type.</span></span> <span data-ttu-id="2257f-122">En variantkod anger vem som täcks av eller hur mycket täckningsbelopp som tillåts för en plantyp.</span><span class="sxs-lookup"><span data-stu-id="2257f-122">A coverage code indicates who is covered or the amount of coverage allowed for a plan type.</span></span> <span data-ttu-id="2257f-123">Du kan uttrycka beloppet för täckningen som ett dollarbelopp eller en procentsats.</span><span class="sxs-lookup"><span data-stu-id="2257f-123">You can express the amount of coverage as a dollar amount or a percentage.</span></span> <span data-ttu-id="2257f-124">Exempel:</span><span class="sxs-lookup"><span data-stu-id="2257f-124">For example:</span></span></br></br><span data-ttu-id="2257f-125">- **Emp+ 1** – för att kvalificeras måste medarbetaren ha ett beroende valt (om fler än en har valts, de är inte längre kvalificerade).</span><span class="sxs-lookup"><span data-stu-id="2257f-125">- **Emp+1** – to be qualified, the employee must have one dependent selected (if more than one is selected, they no longer qualify).</span></span></br></br><span data-ttu-id="2257f-126">- **Emp+familj** – som ska kvalificeras måste medarbetaren ha minst två beroenden valda.</span><span class="sxs-lookup"><span data-stu-id="2257f-126">- **Emp+family** – to be qualified, the employee must have at least two dependents selected.</span></span> |
   | <span data-ttu-id="2257f-127">**Maximalt antal**</span><span class="sxs-lookup"><span data-stu-id="2257f-127">**Maximum number**</span></span> | <span data-ttu-id="2257f-128">Det högsta antalet beroenden.</span><span class="sxs-lookup"><span data-stu-id="2257f-128">The maximum number of dependents.</span></span> |
   | <span data-ttu-id="2257f-129">**Status**</span><span class="sxs-lookup"><span data-stu-id="2257f-129">**Status**</span></span> | <span data-ttu-id="2257f-130">Status för omfattningsalternativ.</span><span class="sxs-lookup"><span data-stu-id="2257f-130">The status of the coverage option.</span></span> <span data-ttu-id="2257f-131">Om omfattningsalternativets status är inaktiverat kan omfattningsalternativet inte väljas på plantyper.</span><span class="sxs-lookup"><span data-stu-id="2257f-131">If the Coverage option status is set to Inactive, the Coverage option can’t be selected on plan types.</span></span> |
   | <span data-ttu-id="2257f-132">**Procent**</span><span class="sxs-lookup"><span data-stu-id="2257f-132">**Percent**</span></span> | <span data-ttu-id="2257f-133">Procentbeloppet.</span><span class="sxs-lookup"><span data-stu-id="2257f-133">The percent amount.</span></span> <span data-ttu-id="2257f-134">Det här fältet är bara aktivt om % x lön har valts i fältet Disponeringskod.</span><span class="sxs-lookup"><span data-stu-id="2257f-134">This field is only active if % x Salary was selected in the Coverage code field.</span></span> |
   | <span data-ttu-id="2257f-135">**Divisor**</span><span class="sxs-lookup"><span data-stu-id="2257f-135">**Divisor**</span></span> | <span data-ttu-id="2257f-136">Divisorn som ska användas i beräkningen när du väljer disponeringskoden % x lön.</span><span class="sxs-lookup"><span data-stu-id="2257f-136">The divisor to use in the calculation when you select the coverage code % x salary.</span></span> |
   | <span data-ttu-id="2257f-137">**Lägsta procentandel**</span><span class="sxs-lookup"><span data-stu-id="2257f-137">**Percent minimum**</span></span> | <span data-ttu-id="2257f-138">Den lägsta procentsatsen när du väljer koden för procent disponeringskoden.</span><span class="sxs-lookup"><span data-stu-id="2257f-138">The minimum percentage when you select the Percentage coverage code.</span></span> |
   | <span data-ttu-id="2257f-139">**Högsta procentandel**</span><span class="sxs-lookup"><span data-stu-id="2257f-139">**Percent maximum**</span></span> | <span data-ttu-id="2257f-140">Den högsta procentsatsen när du väljer koden för procent disponeringskoden.</span><span class="sxs-lookup"><span data-stu-id="2257f-140">The maximum percentage when you select the Percentage coverage code.</span></span> |

4. <span data-ttu-id="2257f-141">Under **Berättigandealternativ för personlig kontakt**, bifoga lämpligt alternativ för personliga kontakters valbarhet till varje täckningsalternativ.</span><span class="sxs-lookup"><span data-stu-id="2257f-141">Under **Personal contact eligibility options**, attach the appropriate personal contacts eligibility option to each coverage option.</span></span>

5. <span data-ttu-id="2257f-142">Under **Självbetjäning**, ange värden för följande fält:</span><span class="sxs-lookup"><span data-stu-id="2257f-142">Under **Self service**, specify values for the following fields:</span></span>

   | <span data-ttu-id="2257f-143">Fält</span><span class="sxs-lookup"><span data-stu-id="2257f-143">Field</span></span> | <span data-ttu-id="2257f-144">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="2257f-144">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="2257f-145">**Tillåt medarbetartilläggsbelopp**</span><span class="sxs-lookup"><span data-stu-id="2257f-145">**Allow employee contribution amount**</span></span> | <span data-ttu-id="2257f-146">Anger om medarbetare ska kunna ändra bidragsbeloppet för självbetjäning för förmåner när de väljer förmåner.</span><span class="sxs-lookup"><span data-stu-id="2257f-146">Specifies whether to allow employees to modify the contribution amount on benefits self-service when they select benefits.</span></span> <span data-ttu-id="2257f-147">Om du markerar den här kryssrutan kommer systemet att beräkna förmånplanparametrar baserat på det bidragsbelopp som medarbetaren registrerar sig på självbetjäning för förmåner.</span><span class="sxs-lookup"><span data-stu-id="2257f-147">If you select this check box, the system will calculate benefit plan parameters based on the contribution amount the employee enters on benefits self-service.</span></span> |
   | <span data-ttu-id="2257f-148">**Tillåt medarbetarförsäkringsbelopp**</span><span class="sxs-lookup"><span data-stu-id="2257f-148">**Allow employee coverage amount**</span></span> | <span data-ttu-id="2257f-149">Anger om medarbetare ska kunna ändra försäkringsbeloppet för självbetjäning för förmåner när de väljer förmåner.</span><span class="sxs-lookup"><span data-stu-id="2257f-149">Specifies whether to allow employees to modify the coverage amount on benefits self-service when they select benefits.</span></span> <span data-ttu-id="2257f-150">Om du markerar den här kryssrutan kommer systemet att beräkna förmånplanparametrar baserat på det försäkringsbelopp som medarbetaren registrerar sig på i Självbetjäning för medarbetare.</span><span class="sxs-lookup"><span data-stu-id="2257f-150">If you select this check box, the system will calculate benefit plan parameters based on the coverage amount the employee enters in Employee self service.</span></span> |

6. <span data-ttu-id="2257f-151">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="2257f-151">Select **Save**.</span></span> 
