---
title: Skapa disponeringsalternativ
description: Omfattningsalternativ i Microsoft Dynamics 365 Human Resources är täckningsgrad för en deltagares val i en förmånsplan eller ett program, t.ex. endast medarbetare för en sjukförsäkringsplan eller 2x lön för en livförsäkringsplan.
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
ms.openlocfilehash: 0af2b6ae0853b4c7f64c4d4f04299c87089d622b
ms.sourcegitcommit: f38302b9430f2ab3efe91d0a7beff946bc610e8f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/28/2020
ms.locfileid: "3092716"
---
# <a name="create-coverage-options"></a><span data-ttu-id="056ba-103">Skapa disponeringsalternativ</span><span class="sxs-lookup"><span data-stu-id="056ba-103">Create coverage options</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="056ba-104">Omfattningsalternativ i Microsoft Dynamics 365 Human Resources är täckningsgrad för en deltagares val i en förmånsplan eller ett program, t.ex. endast medarbetare för en sjukförsäkringsplan eller 2x lön för en livförsäkringsplan.</span><span class="sxs-lookup"><span data-stu-id="056ba-104">Coverage options in Microsoft Dynamics 365 Human Resources are levels of coverage for a participant's election in a benefit plan or program, such as Employee Only for a medical plan, or 2x Salary for a life insurance plan.</span></span> <span data-ttu-id="056ba-105">När du har definierat alternativen för förmånsdisponeringen kan du använda dem igen och du kan associera ett alternativ till en eller flera planer.</span><span class="sxs-lookup"><span data-stu-id="056ba-105">Once defined, benefit coverage options are re-usable and you can associate an option with one or more plans.</span></span>

<span data-ttu-id="056ba-106">När omfattningsalternativ har definierats kopplar du omfattningsalternativen till en förmånsplantyp.</span><span class="sxs-lookup"><span data-stu-id="056ba-106">Once the coverage options are defined, attach the coverage options to a benefit plan type.</span></span> <span data-ttu-id="056ba-107">Plantypen associeras sedan med en förmånsplan eller ett program.</span><span class="sxs-lookup"><span data-stu-id="056ba-107">The plan type is then associated with a benefit plan or program.</span></span> <span data-ttu-id="056ba-108">Omfattningsalternativ som är kopplade till en plantyp blir tillgängligt för alla planer som skapas med den aktuella plantypen.</span><span class="sxs-lookup"><span data-stu-id="056ba-108">Coverage options that are associated with a plan type will be available to all plans that are created with that plan type.</span></span> 

1. <span data-ttu-id="056ba-109">I arbetsytan **Förmånshantering** under **inställningar**, välj **Omfattningsalternativ**.</span><span class="sxs-lookup"><span data-stu-id="056ba-109">In the **Benefits management** workspace, under **Setup**, select **Coverage options**.</span></span>

2. <span data-ttu-id="056ba-110">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="056ba-110">Select **New**.</span></span>

3. <span data-ttu-id="056ba-111">Ange värden för de följande fälten:</span><span class="sxs-lookup"><span data-stu-id="056ba-111">Specify values for the following fields:</span></span>

   | <span data-ttu-id="056ba-112">Fält</span><span class="sxs-lookup"><span data-stu-id="056ba-112">Field</span></span> | <span data-ttu-id="056ba-113">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="056ba-113">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="056ba-114">**Omfattningsalternativ**</span><span class="sxs-lookup"><span data-stu-id="056ba-114">**Coverage option**</span></span> | <span data-ttu-id="056ba-115">Ett unikt namn på omfattningsalternativ.</span><span class="sxs-lookup"><span data-stu-id="056ba-115">A unique coverage option name.</span></span> |
   | <span data-ttu-id="056ba-116">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="056ba-116">**Description**</span></span> | <span data-ttu-id="056ba-117">Ange en beskrivning av omfattningsalternativet.</span><span class="sxs-lookup"><span data-stu-id="056ba-117">A description of the coverage option.</span></span> |
   | <span data-ttu-id="056ba-118">**Omfattningskod**</span><span class="sxs-lookup"><span data-stu-id="056ba-118">**Coverage code**</span></span> | <span data-ttu-id="056ba-119">Täckningskoder tilldelar minimi- och maximibelopp för varje stödberättigad persontyp.</span><span class="sxs-lookup"><span data-stu-id="056ba-119">Coverage codes assign minimum and maximum amounts for each eligible covered person type.</span></span> <span data-ttu-id="056ba-120">En variantkod anger vem som täcks av eller hur mycket täckningsbelopp som tillåts för en plantyp.</span><span class="sxs-lookup"><span data-stu-id="056ba-120">A coverage code indicates who is covered or the amount of coverage allowed for a plan type.</span></span> <span data-ttu-id="056ba-121">Du kan uttrycka beloppet för täckningen som ett dollarbelopp eller en procentsats.</span><span class="sxs-lookup"><span data-stu-id="056ba-121">You can express the amount of coverage as a dollar amount or a percentage.</span></span> <span data-ttu-id="056ba-122">Exempel:</span><span class="sxs-lookup"><span data-stu-id="056ba-122">For example:</span></span></br></br><span data-ttu-id="056ba-123">- **Emp+ 1** – för att kvalificeras måste medarbetaren ha ett beroende valt (om fler än en har valts, de är inte längre kvalificerade).</span><span class="sxs-lookup"><span data-stu-id="056ba-123">- **Emp+1** – to be qualified, the employee must have one dependent selected (if more than one is selected, they no longer qualify).</span></span></br></br><span data-ttu-id="056ba-124">- **Emp+familj** – som ska kvalificeras måste medarbetaren ha minst två beroenden valda.</span><span class="sxs-lookup"><span data-stu-id="056ba-124">- **Emp+family** – to be qualified, the employee must have at least two dependents selected.</span></span> |
   | <span data-ttu-id="056ba-125">**Maximalt antal**</span><span class="sxs-lookup"><span data-stu-id="056ba-125">**Maximum number**</span></span> | <span data-ttu-id="056ba-126">Det högsta antalet beroenden.</span><span class="sxs-lookup"><span data-stu-id="056ba-126">The maximum number of dependents.</span></span> |
   | <span data-ttu-id="056ba-127">**Status**</span><span class="sxs-lookup"><span data-stu-id="056ba-127">**Status**</span></span> | <span data-ttu-id="056ba-128">Status för omfattningsalternativ.</span><span class="sxs-lookup"><span data-stu-id="056ba-128">The status of the coverage option.</span></span> <span data-ttu-id="056ba-129">Om omfattningsalternativets status är inaktiverat kan omfattningsalternativet inte väljas på plantyper.</span><span class="sxs-lookup"><span data-stu-id="056ba-129">If the Coverage option status is set to Inactive, the Coverage option can’t be selected on plan types.</span></span> |
   | <span data-ttu-id="056ba-130">**Procent**</span><span class="sxs-lookup"><span data-stu-id="056ba-130">**Percent**</span></span> | <span data-ttu-id="056ba-131">Procentbeloppet.</span><span class="sxs-lookup"><span data-stu-id="056ba-131">The percent amount.</span></span> <span data-ttu-id="056ba-132">Det här fältet är bara aktivt om % x lön har valts i fältet Disponeringskod.</span><span class="sxs-lookup"><span data-stu-id="056ba-132">This field is only active if % x Salary was selected in the Coverage code field.</span></span> |
   | <span data-ttu-id="056ba-133">**Divisor**</span><span class="sxs-lookup"><span data-stu-id="056ba-133">**Divisor**</span></span> | <span data-ttu-id="056ba-134">Divisorn som ska användas i beräkningen när du väljer disponeringskoden % x lön.</span><span class="sxs-lookup"><span data-stu-id="056ba-134">The divisor to use in the calculation when you select the coverage code % x salary.</span></span> |
   | <span data-ttu-id="056ba-135">**Lägsta procentandel**</span><span class="sxs-lookup"><span data-stu-id="056ba-135">**Percent minimum**</span></span> | <span data-ttu-id="056ba-136">Den lägsta procentsatsen när du väljer koden för procent disponeringskoden.</span><span class="sxs-lookup"><span data-stu-id="056ba-136">The minimum percentage when you select the Percentage coverage code.</span></span> |
   | <span data-ttu-id="056ba-137">**Högsta procentandel**</span><span class="sxs-lookup"><span data-stu-id="056ba-137">**Percent maximum**</span></span> | <span data-ttu-id="056ba-138">Den högsta procentsatsen när du väljer koden för procent disponeringskoden.</span><span class="sxs-lookup"><span data-stu-id="056ba-138">The maximum percentage when you select the Percentage coverage code.</span></span> |

4. <span data-ttu-id="056ba-139">Under **Berättigandealternativ för personlig kontakt**, bifoga lämpligt alternativ för personliga kontakters valbarhet till varje täckningsalternativ.</span><span class="sxs-lookup"><span data-stu-id="056ba-139">Under **Personal contact eligibility options**, attach the appropriate personal contacts eligibility option to each coverage option.</span></span>

5. <span data-ttu-id="056ba-140">Under **Självbetjäning**, ange värden för följande fält:</span><span class="sxs-lookup"><span data-stu-id="056ba-140">Under **Self service**, specify values for the following fields:</span></span>

   | <span data-ttu-id="056ba-141">Fält</span><span class="sxs-lookup"><span data-stu-id="056ba-141">Field</span></span> | <span data-ttu-id="056ba-142">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="056ba-142">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="056ba-143">**Tillåt medarbetartilläggsbelopp**</span><span class="sxs-lookup"><span data-stu-id="056ba-143">**Allow employee contribution amount**</span></span> | <span data-ttu-id="056ba-144">Anger om medarbetare ska kunna ändra bidragsbeloppet för självbetjäning för förmåner när de väljer förmåner.</span><span class="sxs-lookup"><span data-stu-id="056ba-144">Specifies whether to allow employees to modify the contribution amount on benefits self-service when they select benefits.</span></span> <span data-ttu-id="056ba-145">Om du markerar den här kryssrutan kommer systemet att beräkna förmånplanparametrar baserat på det bidragsbelopp som medarbetaren registrerar sig på självbetjäning för förmåner.</span><span class="sxs-lookup"><span data-stu-id="056ba-145">If you select this check box, the system will calculate benefit plan parameters based on the contribution amount the employee enters on benefits self-service.</span></span> |
   | <span data-ttu-id="056ba-146">**Tillåt medarbetarförsäkringsbelopp**</span><span class="sxs-lookup"><span data-stu-id="056ba-146">**Allow employee coverage amount**</span></span> | <span data-ttu-id="056ba-147">Anger om medarbetare ska kunna ändra försäkringsbeloppet för självbetjäning för förmåner när de väljer förmåner.</span><span class="sxs-lookup"><span data-stu-id="056ba-147">Specifies whether to allow employees to modify the coverage amount on benefits self-service when they select benefits.</span></span> <span data-ttu-id="056ba-148">Om du markerar den här kryssrutan kommer systemet att beräkna förmånplanparametrar baserat på det försäkringsbelopp som medarbetaren registrerar sig på i Självbetjäning för medarbetare.</span><span class="sxs-lookup"><span data-stu-id="056ba-148">If you select this check box, the system will calculate benefit plan parameters based on the coverage amount the employee enters in Employee self service.</span></span> |

6. <span data-ttu-id="056ba-149">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="056ba-149">Select **Save**.</span></span> 
