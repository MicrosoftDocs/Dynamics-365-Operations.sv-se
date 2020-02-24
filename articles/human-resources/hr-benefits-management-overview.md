---
title: Förmånshantering – översikt
description: Översikt över funktionen för förmånshantering i Dynamics 365 Human Resources. Erbjud dina medarbetare utökade förmånsalternativ med en lättanvänd onlineupplevelse.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 63db1b55bae9150dd87d9981136b96d72ffd0c59
ms.sourcegitcommit: 523049c363a999050c58d20695f1c7d151b3fd3e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/06/2020
ms.locfileid: "3029473"
---
# <a name="benefits-management-overview"></a><span data-ttu-id="bf29b-104">Förmånshantering – översikt</span><span class="sxs-lookup"><span data-stu-id="bf29b-104">Benefits management overview</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="bf29b-105">För att vara konkurrenskraftig måste du erbjuda en stor mängd fördelar för att kunna locka till dig och behålla dina bästa anställda.</span><span class="sxs-lookup"><span data-stu-id="bf29b-105">To remain competitive, you must offer a rich set of benefits to attract and retain your best employees.</span></span> <span data-ttu-id="bf29b-106">Förutom standardförmåner som sjukvård och tandvård kanske du även vill erbjuda utökade tjänster som implementeringshjälp, rekreationsprogram och bidrag till kläder.</span><span class="sxs-lookup"><span data-stu-id="bf29b-106">In addition to standard benefits like medical and dental coverage, you might also want to offer expanded services like adoption assistance, recreation programs, and clothing allowances.</span></span> <span data-ttu-id="bf29b-107">Med funktionen för förhandsgranskning av förmånshantering i Microsoft Dynamics 365 Human Resources får du en flexibel lösning som stöder en mängd olika förmånsalternativ.</span><span class="sxs-lookup"><span data-stu-id="bf29b-107">The Benefits management preview feature in Microsoft Dynamics 365 Human Resources provides you with a flexible solution that supports a wide variety of benefit options.</span></span> <span data-ttu-id="bf29b-108">Personal inkluderar också en lättanvänd medarbetarupplevelse som visar dina erbjudanden.</span><span class="sxs-lookup"><span data-stu-id="bf29b-108">Human Resources also includes an easy-to-use employee experience that showcases your offerings.</span></span>

- <span data-ttu-id="bf29b-109">Med hjälp av förbättrade förmånsplaner kan du skapa och hantera unika förmånsplaner och stödja komplexa förmånspristabeller och kapslade nivåer.</span><span class="sxs-lookup"><span data-stu-id="bf29b-109">Enhanced benefits plans let you create and manage unique benefit plans and support complex benefit rate tables and nested tiers.</span></span> <span data-ttu-id="bf29b-110">Du kan enkelt skapa förmånsprogram, buntar och automatiska registreringsregler för en enklare medarbetarupplevelse.</span><span class="sxs-lookup"><span data-stu-id="bf29b-110">You can easily create benefit programs, bundles, and auto-enrollment rules for an easier employee experience.</span></span>

- <span data-ttu-id="bf29b-111">Med flexkreditprogram kan du göra proportionell fördelning för att stödja pension och andra livhändelser.</span><span class="sxs-lookup"><span data-stu-id="bf29b-111">Flex credit programs let you prorate to support retirement and other life events.</span></span>

- <span data-ttu-id="bf29b-112">Omfattande berättiganderegler garanterar att du gör rätt förmåner tillgängliga för rätt medarbetare.</span><span class="sxs-lookup"><span data-stu-id="bf29b-112">Extensive eligibility rules ensure you make the right benefits available to the right employees.</span></span>

- <span data-ttu-id="bf29b-113">En anmälan online av förmåner är en enkel upplevelse för dina anställda.</span><span class="sxs-lookup"><span data-stu-id="bf29b-113">Online benefits enrollment provides an easy experience for your employees.</span></span>

- <span data-ttu-id="bf29b-114">Kvalificerad bearbetning av livshändelse integreras med självbetjäning för medarbetare och stöder även framtida livshändelser.</span><span class="sxs-lookup"><span data-stu-id="bf29b-114">Qualified life event processing integrates with Employee self service, and also supports future life events.</span></span>

<span data-ttu-id="bf29b-115">Om du vill ha tillgång till demonstrationsdata måste du omdistribuera miljön i begränsat läge.</span><span class="sxs-lookup"><span data-stu-id="bf29b-115">If you would like to access the demo data, you'll need to redeploy your sandbox environment.</span></span>

<span data-ttu-id="bf29b-116">Du kan tillhandahålla direkt återrapportering eller rapportera problem till: D365BenefitsPreview@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="bf29b-116">You can provide direct feedback or report issues to:  D365BenefitsPreview@microsoft.com.</span></span>

## <a name="benefits-management-known-issues"></a><span data-ttu-id="bf29b-117">Kända problem med förmånshantering</span><span class="sxs-lookup"><span data-stu-id="bf29b-117">Benefits management known issues</span></span>

### <a name="eligibility-processing"></a><span data-ttu-id="bf29b-118">Bearbetning av berättigande</span><span class="sxs-lookup"><span data-stu-id="bf29b-118">Eligibility processing</span></span>

<span data-ttu-id="bf29b-119">När du kör berättigande till förmåner som använder en 1-5X lön, % av lönen och fast belopp för försäkringsbeloppet, måste du ställa in datum för **förmånsinformation** till **medarbetarens startdatum** i **anställningshistoriken**.</span><span class="sxs-lookup"><span data-stu-id="bf29b-119">When running eligibility for benefits that use a 1-5X Salary, % of Salary, and Flat Amount coverage amount, you must set the **Benefit details** date to the **Employee start date** in **Employment history**.</span></span> <span data-ttu-id="bf29b-120">Du måste också inkludera **arbetade timmar**, **lönefrekvens** och **årlig inkomst av förmånen**.</span><span class="sxs-lookup"><span data-stu-id="bf29b-120">You must also include **Hours worked**, **Payment frequency**, and **Annual benefits salary amount**.</span></span> <span data-ttu-id="bf29b-121">Om arbetaren har fast kompensation, ange **arbetade timmar** och **lönefrekvens**.</span><span class="sxs-lookup"><span data-stu-id="bf29b-121">If the worker has fixed compensation, enter **Hours worked** and **Payment frequency**.</span></span> <span data-ttu-id="bf29b-122">Den årliga inkomsten kommer att beräknas.</span><span class="sxs-lookup"><span data-stu-id="bf29b-122">The annual salary amount will calculate.</span></span> <span data-ttu-id="bf29b-123">Om medarbetaren har län behöver du inte ange **arbetade timmar**.</span><span class="sxs-lookup"><span data-stu-id="bf29b-123">If the employee is salaried, you don't need to enter **Hours worked**.</span></span> <span data-ttu-id="bf29b-124">Vi rekommenderar att du först anger fast kompensation när du skapar nya medarbetare.</span><span class="sxs-lookup"><span data-stu-id="bf29b-124">We recommend that when creating new workers, enter fixed compensation first.</span></span> <span data-ttu-id="bf29b-125">Om du vill uppdatera informationen om förmånsposter, gå till **Arbetare > Arbetarhistorik > Information om anställning**.</span><span class="sxs-lookup"><span data-stu-id="bf29b-125">To update the benefit details record, navigate to **Worker > Worker history > Employment details**.</span></span> <span data-ttu-id="bf29b-126">Justera datumet till arbetarens startdatum.</span><span class="sxs-lookup"><span data-stu-id="bf29b-126">Adjust the date to the worker's start date.</span></span>

### <a name="employee-self-service"></a><span data-ttu-id="bf29b-127">Självbetjäning för medarbetare</span><span class="sxs-lookup"><span data-stu-id="bf29b-127">Employee self-service</span></span>

<span data-ttu-id="bf29b-128">Medarbetarbelopp beräknas inte när täckningsbeloppet uppdateras för livförsäkring.</span><span class="sxs-lookup"><span data-stu-id="bf29b-128">Employee amount doesn't calculate when updating the coverage amount for life insurance.</span></span> <span data-ttu-id="bf29b-129">När en medarbetare till exempel erbjuds en livförsäkringsplan kan han eller hon välja upp för att $ 50 000 för täckning till en kostnad av $ 0,36 per $ 1 000 av täckning.</span><span class="sxs-lookup"><span data-stu-id="bf29b-129">For example, when an employee is offered a life insurance plan, they can select up to $50,000 in coverage at a cost of $.36 per $1,000 of coverage.</span></span>  <span data-ttu-id="bf29b-130">När medarbetaren uppdaterar täckningsbeloppet finns medarbetarens kopplade kostnad kvar på noll.</span><span class="sxs-lookup"><span data-stu-id="bf29b-130">When the employee updates the coverage amount, the employee’s associated cost remains at zero.</span></span>

<span data-ttu-id="bf29b-131">För en förmånsplan som bara tillåter ett enda urval av den aktuella plantypen får användaren ett fel om de försöker att avstå från en plan efter att ha valt en plan.</span><span class="sxs-lookup"><span data-stu-id="bf29b-131">For a benefit plan that only allows a single selection of that plan type, the user receives an error if they attempt to waive a plan after selecting a plan.</span></span> <span data-ttu-id="bf29b-132">En användare väljer till exempel en sjukvårdsplan och placerar den i vagnen.</span><span class="sxs-lookup"><span data-stu-id="bf29b-132">For example, a user selects a medical plan and places it in their cart.</span></span> <span data-ttu-id="bf29b-133">Användaren väljer sedan **Avstå** för en annan sjukvårdsplan.</span><span class="sxs-lookup"><span data-stu-id="bf29b-133">The user then selects **Waive** for another medical plan.</span></span> <span data-ttu-id="bf29b-134">Användaren får ett felmeddelande.</span><span class="sxs-lookup"><span data-stu-id="bf29b-134">The user will receive an error.</span></span>

## <a name="enable-benefits-management"></a><span data-ttu-id="bf29b-135">Aktivera hantering av förmåner</span><span class="sxs-lookup"><span data-stu-id="bf29b-135">Enable Benefits management</span></span>

<span data-ttu-id="bf29b-136">Hantering av förmåner är en förhandsgranskningsfunktion som bara är tillgänglig i miljöer med **begränsat läge**.</span><span class="sxs-lookup"><span data-stu-id="bf29b-136">Benefits management is a preview feature, and is only available in **Sandbox** environments.</span></span> <span data-ttu-id="bf29b-137">I dessa artiklar beskrivs hur du aktiverar förhandsgranskningsfunktionerna i personal.</span><span class="sxs-lookup"><span data-stu-id="bf29b-137">These articles describe how to turn on preview features in Human Resources.</span></span> <span data-ttu-id="bf29b-138">De talar också om vilka befintliga funktioner i personal som hantering av förmåner ersätter eller inaktiveras när du har aktiverat hantering av förmåner.</span><span class="sxs-lookup"><span data-stu-id="bf29b-138">They also tell which existing features in Human Resources that Benefits management replaces or are disabled once you turn on Benefits management.</span></span>

- [<span data-ttu-id="bf29b-139">Hantera funktioner</span><span class="sxs-lookup"><span data-stu-id="bf29b-139">Manage features</span></span>](hr-admin-manage-features.md)
- [<span data-ttu-id="bf29b-140">Förhandsgranskningsfunktion: Hantering av förmåner</span><span class="sxs-lookup"><span data-stu-id="bf29b-140">Preview feature: Benefits management</span></span>](hr-admin-manage-features.md?preview-feature-benefits-management)

## <a name="configure-benefits-management"></a><span data-ttu-id="bf29b-141">Konfigurera hantering av förmåner</span><span class="sxs-lookup"><span data-stu-id="bf29b-141">Configure Benefits management</span></span>

<span data-ttu-id="bf29b-142">Innan du kan skapa förmånsplaner för dina medarbetare måste du konfigurera alternativen för planerna.</span><span class="sxs-lookup"><span data-stu-id="bf29b-142">Before you can create benefit plans for your employees, you need to configure options for the plans.</span></span>

- [<span data-ttu-id="bf29b-143">Ställ in parametrar för hantering av förmåner</span><span class="sxs-lookup"><span data-stu-id="bf29b-143">Set Benefits management parameters</span></span>](hr-benefits-setup-parameters.md)
- [<span data-ttu-id="bf29b-144">Konfigurera berättiganderegler och alternativ</span><span class="sxs-lookup"><span data-stu-id="bf29b-144">Configure eligibility rules and options</span></span>](hr-benefits-setup-eligibility-rules.md)
- [<span data-ttu-id="bf29b-145">Konfigurera berättigandealternativ för personlig kontakt</span><span class="sxs-lookup"><span data-stu-id="bf29b-145">Configure personal contact eligibility options</span></span>](hr-benefits-setup-contact-eligibility-options.md)
- [<span data-ttu-id="bf29b-146">Skapa omfattningsalternativ</span><span class="sxs-lookup"><span data-stu-id="bf29b-146">Create coverage options</span></span>](hr-benefits-setup-coverage-options.md)
- [<span data-ttu-id="bf29b-147">Ställ in lönefrekvenser</span><span class="sxs-lookup"><span data-stu-id="bf29b-147">Set up payment frequencies</span></span>](hr-benefits-setup-payment-frequencies.md)
- [<span data-ttu-id="bf29b-148">Konfigurera livshändelsetyper</span><span class="sxs-lookup"><span data-stu-id="bf29b-148">Configure life event types</span></span>](hr-benefits-setup-life-event-types.md)
- [<span data-ttu-id="bf29b-149">Skapa plantyper</span><span class="sxs-lookup"><span data-stu-id="bf29b-149">Create plan types</span></span>](hr-benefits-setup-plan-types.md)
- [<span data-ttu-id="bf29b-150">Ställ in orsakskoder</span><span class="sxs-lookup"><span data-stu-id="bf29b-150">Set up reason codes</span></span>](hr-benefits-setup-reason-codes.md)
- [<span data-ttu-id="bf29b-151">Ställa in nivåkoder</span><span class="sxs-lookup"><span data-stu-id="bf29b-151">Set up tier codes</span></span>](hr-benefits-setup-tier-codes.md)
- [<span data-ttu-id="bf29b-152">Konfigurera tariffer</span><span class="sxs-lookup"><span data-stu-id="bf29b-152">Configure rates</span></span>](hr-benefits-setup-rates.md)
- [<span data-ttu-id="bf29b-153">Konfigurera avdrag</span><span class="sxs-lookup"><span data-stu-id="bf29b-153">Configure deductions</span></span>](hr-benefits-setup-deductions.md)
- [<span data-ttu-id="bf29b-154">Konfigurera väntedagar</span><span class="sxs-lookup"><span data-stu-id="bf29b-154">Configure waiting days</span></span>](hr-benefits-setup-waiting-days.md)
- [<span data-ttu-id="bf29b-155">Konfigurera vänteperioder</span><span class="sxs-lookup"><span data-stu-id="bf29b-155">Configure waiting periods</span></span>](hr-benefits-setup-waiting-periods.md)
- [<span data-ttu-id="bf29b-156">Ställ in avrundningsregler</span><span class="sxs-lookup"><span data-stu-id="bf29b-156">Set up rounding rules</span></span>](hr-benefits-setup-rounding-rules.md)
- [<span data-ttu-id="bf29b-157">Skapa anställningskategorier</span><span class="sxs-lookup"><span data-stu-id="bf29b-157">Create employment categories</span></span>](hr-benefits-setup-employment-categories.md)
- [<span data-ttu-id="bf29b-158">Ställ in anställningstyper</span><span class="sxs-lookup"><span data-stu-id="bf29b-158">Set up employment types</span></span>](hr-benefits-setup-employment-types.md)
- [<span data-ttu-id="bf29b-159">Konfigurera självbetjäning för medarbetare</span><span class="sxs-lookup"><span data-stu-id="bf29b-159">Configure employee self service</span></span>](hr-benefits-setup-employee-self-service.md)

## <a name="create-benefit-plans"></a><span data-ttu-id="bf29b-160">Skapa förmånsplaner</span><span class="sxs-lookup"><span data-stu-id="bf29b-160">Create benefit plans</span></span>

<span data-ttu-id="bf29b-161">Dessa artiklar visar hur du skapar förmånsplaner, inklusive buntar och flexkreditprogram.</span><span class="sxs-lookup"><span data-stu-id="bf29b-161">These articles show how to create benefit plans, including bundles and flex credit programs.</span></span>

- [<span data-ttu-id="bf29b-162">Ställa in förmånsplaner</span><span class="sxs-lookup"><span data-stu-id="bf29b-162">Set up benefit plans</span></span>](hr-benefits-plans-setup.md)
- [<span data-ttu-id="bf29b-163">Skapa förmånsplaner för arbetare</span><span class="sxs-lookup"><span data-stu-id="bf29b-163">Create worker benefit plans</span></span>](hr-benefits-plans-worker.md)
- [<span data-ttu-id="bf29b-164">Ställ in flexkreditprogram</span><span class="sxs-lookup"><span data-stu-id="bf29b-164">Set up flex credit programs</span></span>](hr-benefits-plans-flex-credit-programs.md)
- [<span data-ttu-id="bf29b-165">Konfigurera kommande livshändelser</span><span class="sxs-lookup"><span data-stu-id="bf29b-165">Configure future life events</span></span>](hr-benefits-plans-future-life-events.md)

## <a name="process-benefit-plans"></a><span data-ttu-id="bf29b-166">Bearbeta förmånsplaner</span><span class="sxs-lookup"><span data-stu-id="bf29b-166">Process benefit plans</span></span>

<span data-ttu-id="bf29b-167">Du måste bearbeta några av dina ändringar för att göra dem aktiva.</span><span class="sxs-lookup"><span data-stu-id="bf29b-167">You need to process some of your changes to make them active.</span></span>

- [<span data-ttu-id="bf29b-168">Bearbetning av berättigande för anmälan</span><span class="sxs-lookup"><span data-stu-id="bf29b-168">Process enrollment eligibility</span></span>](hr-benefits-process-enrollment-eligibility.md)
- [<span data-ttu-id="bf29b-169">Bearbeta livshändelse</span><span class="sxs-lookup"><span data-stu-id="bf29b-169">Process life events</span></span>](hr-benefits-process-life-events.md)
- [<span data-ttu-id="bf29b-170">Bearbeta ändring av livshändelse</span><span class="sxs-lookup"><span data-stu-id="bf29b-170">Process life event changes</span></span>](hr-benefits-process-life-event-changes.md)
- [<span data-ttu-id="bf29b-171">Bearbetning av berättigande för livshändelse</span><span class="sxs-lookup"><span data-stu-id="bf29b-171">Process life event eligibility</span></span>](hr-benefits-process-life-event-eligibility.md)
- [<span data-ttu-id="bf29b-172">Behandla prisändringar</span><span class="sxs-lookup"><span data-stu-id="bf29b-172">Process rate changes</span></span>](hr-benefits-process-rate-changes.md)

