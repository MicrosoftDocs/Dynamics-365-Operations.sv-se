---
title: Nyheter och ändringar i Dynamics 365 Talent - Core HR (10 september 2018)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Talent - Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 09/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-09-06
ms.dyn365.ops.version: Talent September 10, 2018 update
ms.openlocfilehash: 1340f17e57f49d6adb9dc0a7c769bafa655de56e
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/03/2019
ms.locfileid: "2551289"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent---core-hr-september-10-2018"></a><span data-ttu-id="89247-103">Nyheter och ändringar i Dynamics 365 Talent - Core HR (10 september 2018)</span><span class="sxs-lookup"><span data-stu-id="89247-103">What's new or changed in Dynamics 365 Talent - Core HR (September 10, 2018)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="89247-104">**Skapa 8.1.138.0**</span><span class="sxs-lookup"><span data-stu-id="89247-104">**Build 8.1.138.0**</span></span>

<span data-ttu-id="89247-105">Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Talent: Core HR.</span><span class="sxs-lookup"><span data-stu-id="89247-105">This topic describes features that are either new or changed in Microsoft Dynamics 365 Talent: Core HR.</span></span>

## <a name="allow-specific-time-of-day-on-time-off-requests-half-days"></a><span data-ttu-id="89247-106">Tillåta viss tid på ledighetsbegärande (halv dagar)</span><span class="sxs-lookup"><span data-stu-id="89247-106">Allow specific time of day on time-off requests (half days)</span></span>

<span data-ttu-id="89247-107">Om ledighet och frånvaro är inställd så att ledig tid lämnas in i dagar, kan du nu även aktivera en halvdagars definition.</span><span class="sxs-lookup"><span data-stu-id="89247-107">If leave and absence is set up so that time off is submitted in days, you can now also enable a half-day definition.</span></span> <span data-ttu-id="89247-108">Därefter när användaren skickar ledighetsbegäranden, kan de ange om de begär första halvan eller andra halvan av den lediga dagen.</span><span class="sxs-lookup"><span data-stu-id="89247-108">Then, when users submit time-off requests, they can specify whether they are requesting the first half or the second half of the day off.</span></span>

<span data-ttu-id="89247-109">Det här alternativet är inaktiverat som standard.</span><span class="sxs-lookup"><span data-stu-id="89247-109">By default, this option is turned off.</span></span> <span data-ttu-id="89247-110">För anställda att begära den första halvan eller andra halvan av dagen, måste du aktivera det här alternativet i området **Tjänstledighet och frånvaro** personalparametrar.</span><span class="sxs-lookup"><span data-stu-id="89247-110">For employees to request the first half or second half of the day off, you must turn on this option in the **Leave and absence** area of Human resources parameters.</span></span>

<span data-ttu-id="89247-111">Säkerhetsprivilegier för den här funktionen är Underhåll personalparametrar.</span><span class="sxs-lookup"><span data-stu-id="89247-111">The security privilege for this feature is Maintain Human Resources Parameters.</span></span>

## <a name="validation-of-leave-and-absence-entries"></a><span data-ttu-id="89247-112">Validering av tjänstledighets- och frånvaroposter</span><span class="sxs-lookup"><span data-stu-id="89247-112">Validation of leave and absence entries</span></span>

<span data-ttu-id="89247-113">Beroende på hur ledigheten är konfigurerad, får anställda som försöker skicka in en ledighetsbegäran som är längre än sin arbetsdag ett varningsmeddelande.</span><span class="sxs-lookup"><span data-stu-id="89247-113">Depending on how leave is configured, employees who try to submit a time-off request that is longer than their work day receive a warning message.</span></span> <span data-ttu-id="89247-114">Med andra ord varnas de om de försöker ta mer än en hel dag vid ett givet datum.</span><span class="sxs-lookup"><span data-stu-id="89247-114">In other words, they are warned if they try to take more than a full day off on any given date.</span></span>

<span data-ttu-id="89247-115">Verifieringen är alltid aktiverad.</span><span class="sxs-lookup"><span data-stu-id="89247-115">This validation is always turned on.</span></span> <span data-ttu-id="89247-116">När anställda överstiger tröskelvärdet som definieras får de en varning i sin ledighetsbegäran.</span><span class="sxs-lookup"><span data-stu-id="89247-116">Any time that employees exceed the day threshold that is defined, they receive a warning in their time-off request.</span></span>

## <a name="additional-fields-for-conditional-statements-in-workflows"></a><span data-ttu-id="89247-117">Ytterligare fält för villkorssatser i arbetsflöden</span><span class="sxs-lookup"><span data-stu-id="89247-117">Additional fields for conditional statements in workflows</span></span>

<span data-ttu-id="89247-118">Ytterligare fält har lagts till villkorssatser och platshållare för flera arbetsflöden i Core HR.</span><span class="sxs-lookup"><span data-stu-id="89247-118">Additional fields have been added to conditional statements and placeholders for several workflows in Core HR.</span></span>

<span data-ttu-id="89247-119">Följande fält har lagts till kompensation, avslutning och överföra arbetsflöden:</span><span class="sxs-lookup"><span data-stu-id="89247-119">The following fields have been added to the compensation, termination, and transfer workflows:</span></span>

- <span data-ttu-id="89247-120">EmploymentType</span><span class="sxs-lookup"><span data-stu-id="89247-120">EmploymentType</span></span>
- <span data-ttu-id="89247-121">LegalEntity</span><span class="sxs-lookup"><span data-stu-id="89247-121">LegalEntity</span></span>
- <span data-ttu-id="89247-122">AdjustedWorkerStartDate</span><span class="sxs-lookup"><span data-stu-id="89247-122">AdjustedWorkerStartDate</span></span>
- <span data-ttu-id="89247-123">EmployerNoticeAmount</span><span class="sxs-lookup"><span data-stu-id="89247-123">EmployerNoticeAmount</span></span>
- <span data-ttu-id="89247-124">EmployerUnitOfNotice</span><span class="sxs-lookup"><span data-stu-id="89247-124">EmployerUnitOfNotice</span></span>
- <span data-ttu-id="89247-125">TransitionDate</span><span class="sxs-lookup"><span data-stu-id="89247-125">TransitionDate</span></span>
- <span data-ttu-id="89247-126">WorkerNoticeAmount</span><span class="sxs-lookup"><span data-stu-id="89247-126">WorkerNoticeAmount</span></span>
- <span data-ttu-id="89247-127">WorkerStartDate</span><span class="sxs-lookup"><span data-stu-id="89247-127">WorkerStartDate</span></span>
- <span data-ttu-id="89247-128">WorkerUnitOfNotice</span><span class="sxs-lookup"><span data-stu-id="89247-128">WorkerUnitOfNotice</span></span>
- <span data-ttu-id="89247-129">ProbationEndDate</span><span class="sxs-lookup"><span data-stu-id="89247-129">ProbationEndDate</span></span>
- <span data-ttu-id="89247-130">Befattning</span><span class="sxs-lookup"><span data-stu-id="89247-130">Position</span></span>
- <span data-ttu-id="89247-131">Fackförening</span><span class="sxs-lookup"><span data-stu-id="89247-131">Union</span></span>
- <span data-ttu-id="89247-132">Avdelning</span><span class="sxs-lookup"><span data-stu-id="89247-132">Department</span></span>
- <span data-ttu-id="89247-133">PositionType</span><span class="sxs-lookup"><span data-stu-id="89247-133">PositionType</span></span>
- <span data-ttu-id="89247-134">CompLocation</span><span class="sxs-lookup"><span data-stu-id="89247-134">CompLocation</span></span>
- <span data-ttu-id="89247-135">Namn</span><span class="sxs-lookup"><span data-stu-id="89247-135">Title</span></span>
- <span data-ttu-id="89247-136">Jobb</span><span class="sxs-lookup"><span data-stu-id="89247-136">Job</span></span>
- <span data-ttu-id="89247-137">JobType</span><span class="sxs-lookup"><span data-stu-id="89247-137">JobType</span></span>
- <span data-ttu-id="89247-138">JobFamily</span><span class="sxs-lookup"><span data-stu-id="89247-138">JobFamily</span></span>
- <span data-ttu-id="89247-139">JobFunction</span><span class="sxs-lookup"><span data-stu-id="89247-139">JobFunction</span></span>

<span data-ttu-id="89247-140">Följande fält har lagts till i befattningsarbetsflöden:</span><span class="sxs-lookup"><span data-stu-id="89247-140">The following fields have been added to the position workflow:</span></span>

- <span data-ttu-id="89247-141">Befattning</span><span class="sxs-lookup"><span data-stu-id="89247-141">Position</span></span>
- <span data-ttu-id="89247-142">Fackförening</span><span class="sxs-lookup"><span data-stu-id="89247-142">Union</span></span>
- <span data-ttu-id="89247-143">Avdelning</span><span class="sxs-lookup"><span data-stu-id="89247-143">Department</span></span>
- <span data-ttu-id="89247-144">PositionType</span><span class="sxs-lookup"><span data-stu-id="89247-144">PositionType</span></span>
- <span data-ttu-id="89247-145">CompLocation</span><span class="sxs-lookup"><span data-stu-id="89247-145">CompLocation</span></span>
- <span data-ttu-id="89247-146">Namn</span><span class="sxs-lookup"><span data-stu-id="89247-146">Title</span></span>
- <span data-ttu-id="89247-147">Jobb</span><span class="sxs-lookup"><span data-stu-id="89247-147">Job</span></span>
- <span data-ttu-id="89247-148">JobType</span><span class="sxs-lookup"><span data-stu-id="89247-148">JobType</span></span>
- <span data-ttu-id="89247-149">JobFamily</span><span class="sxs-lookup"><span data-stu-id="89247-149">JobFamily</span></span>
- <span data-ttu-id="89247-150">JobFunction</span><span class="sxs-lookup"><span data-stu-id="89247-150">JobFunction</span></span>

<span data-ttu-id="89247-151">Fält i villkorssatser och platshållare är tillgängliga för alla användare som har tillgång till konfiguration av tidigare nämnda arbetsflöden.</span><span class="sxs-lookup"><span data-stu-id="89247-151">Fields in conditional statements and placeholders are available to all users who have access to configure the previously mentioned workflows.</span></span>

## <a name="navigation-to-attract-from-personnel-management"></a><span data-ttu-id="89247-152">Navigera till Attract från personalhantering</span><span class="sxs-lookup"><span data-stu-id="89247-152">Navigation to Attract from personnel management</span></span>

<span data-ttu-id="89247-153">I personalhantering, om Attract inte har konfigurerats, hjälper avsnittet **Kandidater att anställa** användare att komma igång med Attract i stället för att visa meddelandet, ”Vi hittade ingenting att visa här”.</span><span class="sxs-lookup"><span data-stu-id="89247-153">In personnel management, if Attract hasn't been set up, the **Candidates to hire** section directs users to get started with Attract instead of showing the message, "We didn't find anything to show here."</span></span>

## <a name="other-changes"></a><span data-ttu-id="89247-154">Andra ändringar</span><span class="sxs-lookup"><span data-stu-id="89247-154">Other changes</span></span>

<span data-ttu-id="89247-155">Den här versionen innehåller flera ytterligare felkorrigeringar:</span><span class="sxs-lookup"><span data-stu-id="89247-155">This release includes several additional bug fixes:</span></span>

- <span data-ttu-id="89247-156">När en entreprenör anställs bör fliken **kompensation** inte vara tillgänglig på sidan förfrågan/åtgärd.</span><span class="sxs-lookup"><span data-stu-id="89247-156">When a contractor is hired, the **Compensation** tab should not be available on the request/action page.</span></span>
- <span data-ttu-id="89247-157">Under processen om begäran om uppsägning kan du inte fortsätta förrän alla obligatoriska fält innehåller data.</span><span class="sxs-lookup"><span data-stu-id="89247-157">During the request termination process, you can't continue until all required fields contain data.</span></span>
- <span data-ttu-id="89247-158">Problem med sorteringsordning och datumvisning i analysen för Personalhantering har hanterats.</span><span class="sxs-lookup"><span data-stu-id="89247-158">Sort order and date display issues on the Personnel management analytics have been addressed.</span></span>
