---
title: Skapa omfattningsalternativ
description: ''
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
ms.openlocfilehash: 27b43d858a92beac526ac0fc40b544649ef658b0
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010544"
---
# <a name="create-coverage-options"></a><span data-ttu-id="efede-102">Skapa omfattningsalternativ</span><span class="sxs-lookup"><span data-stu-id="efede-102">Create coverage options</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="efede-103">Omfattningsalternativ i Microsoft Dynamics 365 Human Resources är täckningsgrad för en deltagares val i en förmånsplan eller ett program, t.ex. endast medarbetare för en sjukförsäkringsplan eller 2x lön för en livförsäkringsplan.</span><span class="sxs-lookup"><span data-stu-id="efede-103">Coverage options in Microsoft Dynamics 365 Human Resources are levels of coverage for a participant's election in a benefit plan or program, such as Employee Only for a medical plan, or 2x Salary for a life insurance plan.</span></span> <span data-ttu-id="efede-104">När du har definierat alternativen för förmånsdisponeringen kan du använda dem igen och du kan associera ett alternativ till en eller flera planer.</span><span class="sxs-lookup"><span data-stu-id="efede-104">Once defined, benefit coverage options are re-usable and you can associate an option with one or more plans.</span></span>

<span data-ttu-id="efede-105">När omfattningsalternativ har definierats kopplar du omfattningsalternativen till en förmånsplantyp.</span><span class="sxs-lookup"><span data-stu-id="efede-105">Once the coverage options are defined, attach the coverage options to a benefit plan type.</span></span> <span data-ttu-id="efede-106">Plantypen associeras sedan med en förmånsplan eller ett program.</span><span class="sxs-lookup"><span data-stu-id="efede-106">The plan type is then associated with a benefit plan or program.</span></span> <span data-ttu-id="efede-107">Omfattningsalternativ som är kopplade till en plantyp blir tillgängligt för alla planer som skapas med den aktuella plantypen.</span><span class="sxs-lookup"><span data-stu-id="efede-107">Coverage options that are associated with a plan type will be available to all plans that are created with that plan type.</span></span> 

1. <span data-ttu-id="efede-108">I arbetsytan **Förmånshantering** under **inställningar**, välj **Omfattningsalternativ**.</span><span class="sxs-lookup"><span data-stu-id="efede-108">In the **Benefits management** workspace, under **Setup**, select **Coverage options**.</span></span>

2. <span data-ttu-id="efede-109">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="efede-109">Select **New**.</span></span>

3. <span data-ttu-id="efede-110">Ange värden för de följande fälten:</span><span class="sxs-lookup"><span data-stu-id="efede-110">Specify values for the following fields:</span></span>

   | <span data-ttu-id="efede-111">Fält</span><span class="sxs-lookup"><span data-stu-id="efede-111">Field</span></span> | <span data-ttu-id="efede-112">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="efede-112">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="efede-113">**Omfattningsalternativ**</span><span class="sxs-lookup"><span data-stu-id="efede-113">**Coverage option**</span></span> | <span data-ttu-id="efede-114">Ett unikt namn på omfattningsalternativ.</span><span class="sxs-lookup"><span data-stu-id="efede-114">A unique coverage option name.</span></span> |
   | <span data-ttu-id="efede-115">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="efede-115">**Description**</span></span> | <span data-ttu-id="efede-116">Ange en beskrivning av omfattningsalternativet.</span><span class="sxs-lookup"><span data-stu-id="efede-116">A description of the coverage option.</span></span> |
   | <span data-ttu-id="efede-117">**Omfattningskod**</span><span class="sxs-lookup"><span data-stu-id="efede-117">**Coverage code**</span></span> | <span data-ttu-id="efede-118">Täckningskoder tilldelar minimi- och maximibelopp för varje stödberättigad persontyp.</span><span class="sxs-lookup"><span data-stu-id="efede-118">Coverage codes assign minimum and maximum amounts for each eligible covered person type.</span></span> <span data-ttu-id="efede-119">En variantkod anger vem som täcks av eller hur mycket täckningsbelopp som tillåts för en plantyp.</span><span class="sxs-lookup"><span data-stu-id="efede-119">A coverage code indicates who is covered or the amount of coverage allowed for a plan type.</span></span> <span data-ttu-id="efede-120">Du kan uttrycka beloppet för täckningen som ett dollarbelopp eller en procentsats.</span><span class="sxs-lookup"><span data-stu-id="efede-120">You can express the amount of coverage as a dollar amount or a percentage.</span></span> <span data-ttu-id="efede-121">Exempel:</span><span class="sxs-lookup"><span data-stu-id="efede-121">For example:</span></span></br></br><span data-ttu-id="efede-122">- **Emp+ 1** – för att kvalificeras måste medarbetaren ha ett beroende valt (om fler än en har valts, de är inte längre kvalificerade).</span><span class="sxs-lookup"><span data-stu-id="efede-122">- **Emp+1** – to be qualified, the employee must have one dependent selected (if more than one is selected, they no longer qualify).</span></span></br></br><span data-ttu-id="efede-123">- **Emp+familj** – som ska kvalificeras måste medarbetaren ha minst två beroenden valda.</span><span class="sxs-lookup"><span data-stu-id="efede-123">- **Emp+family** – to be qualified, the employee must have at least two dependents selected.</span></span> |
   | <span data-ttu-id="efede-124">**Maximalt antal**</span><span class="sxs-lookup"><span data-stu-id="efede-124">**Maximum number**</span></span> | <span data-ttu-id="efede-125">Det högsta antalet beroenden.</span><span class="sxs-lookup"><span data-stu-id="efede-125">The maximum number of dependents.</span></span> |
   | <span data-ttu-id="efede-126">**Status**</span><span class="sxs-lookup"><span data-stu-id="efede-126">**Status**</span></span> | <span data-ttu-id="efede-127">Status för omfattningsalternativ.</span><span class="sxs-lookup"><span data-stu-id="efede-127">The status of the coverage option.</span></span> <span data-ttu-id="efede-128">Om omfattningsalternativets status är inaktiverat kan omfattningsalternativet inte väljas på plantyper.</span><span class="sxs-lookup"><span data-stu-id="efede-128">If the Coverage option status is set to Inactive, the Coverage option can’t be selected on plan types.</span></span> |
   | <span data-ttu-id="efede-129">**Procent**</span><span class="sxs-lookup"><span data-stu-id="efede-129">**Percent**</span></span> | <span data-ttu-id="efede-130">Procentbeloppet.</span><span class="sxs-lookup"><span data-stu-id="efede-130">The percent amount.</span></span> <span data-ttu-id="efede-131">Det här fältet är bara aktivt om % x lön har valts i fältet Disponeringskod.</span><span class="sxs-lookup"><span data-stu-id="efede-131">This field is only active if % x Salary was selected in the Coverage code field.</span></span> |
   | <span data-ttu-id="efede-132">**Divisor**</span><span class="sxs-lookup"><span data-stu-id="efede-132">**Divisor**</span></span> | <span data-ttu-id="efede-133">Divisorn som ska användas i beräkningen när du väljer disponeringskoden % x lön.</span><span class="sxs-lookup"><span data-stu-id="efede-133">The divisor to use in the calculation when you select the coverage code % x salary.</span></span> |
   | <span data-ttu-id="efede-134">**Lägsta procentandel**</span><span class="sxs-lookup"><span data-stu-id="efede-134">**Percent minimum**</span></span> | <span data-ttu-id="efede-135">Den lägsta procentsatsen när du väljer koden för procent disponeringskoden.</span><span class="sxs-lookup"><span data-stu-id="efede-135">The minimum percentage when you select the Percentage coverage code.</span></span> |
   | <span data-ttu-id="efede-136">**Högsta procentandel**</span><span class="sxs-lookup"><span data-stu-id="efede-136">**Percent maximum**</span></span> | <span data-ttu-id="efede-137">Den högsta procentsatsen när du väljer koden för procent disponeringskoden.</span><span class="sxs-lookup"><span data-stu-id="efede-137">The maximum percentage when you select the Percentage coverage code.</span></span> |

4. <span data-ttu-id="efede-138">Under **Berättigandealternativ för personlig kontakt**, bifoga lämpligt alternativ för personliga kontakters valbarhet till varje täckningsalternativ.</span><span class="sxs-lookup"><span data-stu-id="efede-138">Under **Personal contact eligibility options**, attach the appropriate personal contacts eligibility option to each coverage option.</span></span>

5. <span data-ttu-id="efede-139">Under **Självbetjäning**, ange värden för följande fält:</span><span class="sxs-lookup"><span data-stu-id="efede-139">Under **Self service**, specify values for the following fields:</span></span>

   | <span data-ttu-id="efede-140">Fält</span><span class="sxs-lookup"><span data-stu-id="efede-140">Field</span></span> | <span data-ttu-id="efede-141">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="efede-141">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="efede-142">**Tillåt medarbetartilläggsbelopp**</span><span class="sxs-lookup"><span data-stu-id="efede-142">**Allow employee contribution amount**</span></span> | <span data-ttu-id="efede-143">Anger om medarbetare ska kunna ändra bidragsbeloppet för självbetjäning för förmåner när de väljer förmåner.</span><span class="sxs-lookup"><span data-stu-id="efede-143">Specifies whether to allow employees to modify the contribution amount on benefits self-service when they select benefits.</span></span> <span data-ttu-id="efede-144">Om du markerar den här kryssrutan kommer systemet att beräkna förmånplanparametrar baserat på det bidragsbelopp som medarbetaren registrerar sig på självbetjäning för förmåner.</span><span class="sxs-lookup"><span data-stu-id="efede-144">If you select this check box, the system will calculate benefit plan parameters based on the contribution amount the employee enters on benefits self-service.</span></span> |
   | <span data-ttu-id="efede-145">**Tillåt medarbetarförsäkringsbelopp**</span><span class="sxs-lookup"><span data-stu-id="efede-145">**Allow employee coverage amount**</span></span> | <span data-ttu-id="efede-146">Anger om medarbetare ska kunna ändra försäkringsbeloppet för självbetjäning för förmåner när de väljer förmåner.</span><span class="sxs-lookup"><span data-stu-id="efede-146">Specifies whether to allow employees to modify the coverage amount on benefits self-service when they select benefits.</span></span> <span data-ttu-id="efede-147">Om du markerar den här kryssrutan kommer systemet att beräkna förmånplanparametrar baserat på det försäkringsbelopp som medarbetaren registrerar sig på i Självbetjäning för medarbetare.</span><span class="sxs-lookup"><span data-stu-id="efede-147">If you select this check box, the system will calculate benefit plan parameters based on the coverage amount the employee enters in Employee self service.</span></span> |

6. <span data-ttu-id="efede-148">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="efede-148">Select **Save**.</span></span> 
