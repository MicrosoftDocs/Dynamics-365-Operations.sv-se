---
title: Hantering av förmåner – översikt
description: Översikt över funktionen för förmånshantering i Dynamics 365 Human Resources. Erbjud dina medarbetare utökade förmånsalternativ med en lättanvänd onlineupplevelse.
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
ms.openlocfilehash: 4157cb1f83d686d435f3d04e47c578df455376c9
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2020
ms.locfileid: "3429276"
---
# <a name="benefits-management-overview"></a><span data-ttu-id="5a9e8-104">Förmånshantering – översikt</span><span class="sxs-lookup"><span data-stu-id="5a9e8-104">Benefits management overview</span></span>

<span data-ttu-id="5a9e8-105">För att vara konkurrenskraftig måste du erbjuda en stor mängd fördelar för att kunna locka till dig och behålla dina bästa anställda.</span><span class="sxs-lookup"><span data-stu-id="5a9e8-105">To remain competitive, you must offer a rich set of benefits to attract and retain your best employees.</span></span> <span data-ttu-id="5a9e8-106">Förutom standardförmåner som sjukvård och tandvård kanske du även vill erbjuda utökade tjänster som implementeringshjälp, rekreationsprogram och bidrag till kläder.</span><span class="sxs-lookup"><span data-stu-id="5a9e8-106">In addition to standard benefits like medical and dental coverage, you might also want to offer expanded services like adoption assistance, recreation programs, and clothing allowances.</span></span> <span data-ttu-id="5a9e8-107">Med förmånshantering i Microsoft Dynamics 365 Human Resources får du en flexibel lösning som stöder en mängd olika förmånsalternativ.</span><span class="sxs-lookup"><span data-stu-id="5a9e8-107">Benefits management in Microsoft Dynamics 365 Human Resources provides you with a flexible solution that supports a wide variety of benefit options.</span></span> <span data-ttu-id="5a9e8-108">Personal inkluderar också en lättanvänd medarbetarupplevelse som visar dina erbjudanden.</span><span class="sxs-lookup"><span data-stu-id="5a9e8-108">Human Resources also includes an easy-to-use employee experience that showcases your offerings.</span></span>

- <span data-ttu-id="5a9e8-109">Med hjälp av förbättrade förmånsplaner kan du skapa och hantera unika förmånsplaner och stödja komplexa förmånspristabeller och kapslade nivåer.</span><span class="sxs-lookup"><span data-stu-id="5a9e8-109">Enhanced benefits plans let you create and manage unique benefit plans and support complex benefit rate tables and nested tiers.</span></span> <span data-ttu-id="5a9e8-110">Du kan enkelt skapa förmånsprogram, buntar och automatiska registreringsregler för en enklare medarbetarupplevelse.</span><span class="sxs-lookup"><span data-stu-id="5a9e8-110">You can easily create benefit programs, bundles, and auto-enrollment rules for an easier employee experience.</span></span>

- <span data-ttu-id="5a9e8-111">Med flexkreditprogram kan du göra proportionell fördelning för att stödja pension och andra livhändelser.</span><span class="sxs-lookup"><span data-stu-id="5a9e8-111">Flex credit programs let you prorate to support retirement and other life events.</span></span>

- <span data-ttu-id="5a9e8-112">Omfattande berättiganderegler garanterar att du gör rätt förmåner tillgängliga för rätt medarbetare.</span><span class="sxs-lookup"><span data-stu-id="5a9e8-112">Extensive eligibility rules ensure you make the right benefits available to the right employees.</span></span>

- <span data-ttu-id="5a9e8-113">En anmälan online av förmåner är en enkel upplevelse för dina anställda.</span><span class="sxs-lookup"><span data-stu-id="5a9e8-113">Online benefits enrollment provides an easy experience for your employees.</span></span>

- <span data-ttu-id="5a9e8-114">Kvalificerad bearbetning av livshändelse stöder framtida livshändelser.</span><span class="sxs-lookup"><span data-stu-id="5a9e8-114">Qualified life event processing supports future life events.</span></span>

<span data-ttu-id="5a9e8-115">Om du vill ha tillgång till demonstrationsdata måste du omdistribuera miljön i begränsat läge.</span><span class="sxs-lookup"><span data-stu-id="5a9e8-115">If you would like to access the demo data, you'll need to redeploy your sandbox environment.</span></span>

## <a name="benefits-management-known-issues"></a><span data-ttu-id="5a9e8-116">Kända problem med förmånshantering</span><span class="sxs-lookup"><span data-stu-id="5a9e8-116">Benefits management known issues</span></span>

### <a name="flex-credit-programs"></a><span data-ttu-id="5a9e8-117">Flexkreditprogram</span><span class="sxs-lookup"><span data-stu-id="5a9e8-117">Flex credit programs</span></span>

<span data-ttu-id="5a9e8-118">Det totala kreditvärde som har definierats för ett flexkreditprogram visas i formuläret **Förmånsplaner för arbetare**.</span><span class="sxs-lookup"><span data-stu-id="5a9e8-118">The total credit value defined for a flex credit program doesn't display in the **Worker benefit plans** form.</span></span> <span data-ttu-id="5a9e8-119">Om du anger att ett flexkreditprogram ska ha en proportionell fördelningsregel som **ingen**, får du också ett felmeddelande i formuläret **arbetarens förmånsplan** när du väljer och bekräftar planer.</span><span class="sxs-lookup"><span data-stu-id="5a9e8-119">Also, if you set a flex credit program to have a proration rule of **None**, you get an error in the **Worker benefit plan** form when selecting and confirming plans.</span></span>

## <a name="enable-benefits-management"></a><span data-ttu-id="5a9e8-120">Aktivera hantering av förmåner</span><span class="sxs-lookup"><span data-stu-id="5a9e8-120">Enable Benefits management</span></span>

<span data-ttu-id="5a9e8-121">Den här artikeln beskriver hur du aktiverar funktionerna i personal.</span><span class="sxs-lookup"><span data-stu-id="5a9e8-121">This article describes how to turn on features in Human Resources.</span></span> <span data-ttu-id="5a9e8-122">Den talar också om vilka befintliga funktioner i personal som hantering av förmåner ersätter eller inaktiveras när du har aktiverat hantering av förmåner.</span><span class="sxs-lookup"><span data-stu-id="5a9e8-122">It also tells which existing features in Human Resources that Benefits management replaces or are disabled once you turn on Benefits management.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5a9e8-123">När du har aktiverat hantering av förmåner i miljön **produktion** kan du inte inaktivera den.</span><span class="sxs-lookup"><span data-stu-id="5a9e8-123">After you enable Benefits management in a **Production** environment, you can't disable it.</span></span> <span data-ttu-id="5a9e8-124">Vi rekommenderar att du aktiverar och testar förmånshantering i en miljö med **begränsat läge** innan du aktiverar den i en miljö för **produktion**.</span><span class="sxs-lookup"><span data-stu-id="5a9e8-124">We recommend enabling and testing Benefits management in a **Sandbox** environment before enabling it in a **Production** environment.</span></span> <span data-ttu-id="5a9e8-125">Det finns betydande skillnader mellan den tidigare förmånsfunktionen och nya fördelar för hanteringsfunktioner som kräver ytterligare inställningar och bör testas innan de kan placeras i produktionen.</span><span class="sxs-lookup"><span data-stu-id="5a9e8-125">There are significant differences between the legacy Benefit functionality and new Benefits management functionality that require additional setup and should be tested prior to being placed into production.</span></span>

- [<span data-ttu-id="5a9e8-126">Hantera funktioner</span><span class="sxs-lookup"><span data-stu-id="5a9e8-126">Manage features</span></span>](hr-admin-manage-features.md)

## <a name="configure-employee-information"></a><span data-ttu-id="5a9e8-127">Konfigurera information om medarbetare</span><span class="sxs-lookup"><span data-stu-id="5a9e8-127">Configure employee information</span></span>

<span data-ttu-id="5a9e8-128">Innan du kan registrera medarbetare i förmåner måste du ange den information som krävs.</span><span class="sxs-lookup"><span data-stu-id="5a9e8-128">Before you can enroll employees in benefits, you must provide required information.</span></span> <span data-ttu-id="5a9e8-129">Du måste registrera en medarbetare i en **fast kompensationsplan** på deras startdatum och du måste välja en **förmånslönefrekvens** i **medarbetarinformation** i formuläret **medarbetare**.</span><span class="sxs-lookup"><span data-stu-id="5a9e8-129">You must enroll an employee in a **Fixed compensation plan** on their start date, and you must select a **Benefit pay frequency** in **Employment details** on the **Worker** form.</span></span>

<span data-ttu-id="5a9e8-130">När du skapar en förmånsplan som bygger på kön eller ålder måste du ange ett födelsedatum och kön för medarbetaren för att beräkna förmånskostnaden.</span><span class="sxs-lookup"><span data-stu-id="5a9e8-130">When you create a benefit plan that uses rates that are based on gender or age, you must enter a birth date and gender for the employee to calculate the benefit cost.</span></span>

## <a name="configure-benefits-management"></a><span data-ttu-id="5a9e8-131">Konfigurera förmånshantering</span><span class="sxs-lookup"><span data-stu-id="5a9e8-131">Configure Benefits management</span></span>

<span data-ttu-id="5a9e8-132">Innan du kan skapa förmånsplaner för dina medarbetare måste du konfigurera alternativen för planerna.</span><span class="sxs-lookup"><span data-stu-id="5a9e8-132">Before you can create benefit plans for your employees, you need to configure options for the plans.</span></span>

- [<span data-ttu-id="5a9e8-133">Ställ in parametrar för hantering av förmåner</span><span class="sxs-lookup"><span data-stu-id="5a9e8-133">Set Benefits management parameters</span></span>](hr-benefits-setup-parameters.md)
- [<span data-ttu-id="5a9e8-134">Konfigurera berättiganderegler och alternativ</span><span class="sxs-lookup"><span data-stu-id="5a9e8-134">Configure eligibility rules and options</span></span>](hr-benefits-setup-eligibility-rules.md)
- [<span data-ttu-id="5a9e8-135">Konfigurera berättigandealternativ för personlig kontakt</span><span class="sxs-lookup"><span data-stu-id="5a9e8-135">Configure personal contact eligibility options</span></span>](hr-benefits-setup-contact-eligibility-options.md)
- [<span data-ttu-id="5a9e8-136">Skapa disponeringsalternativ</span><span class="sxs-lookup"><span data-stu-id="5a9e8-136">Create coverage options</span></span>](hr-benefits-setup-coverage-options.md)
- [<span data-ttu-id="5a9e8-137">Ställa in betalningsfrekvenser</span><span class="sxs-lookup"><span data-stu-id="5a9e8-137">Set up payment frequencies</span></span>](hr-benefits-setup-payment-frequencies.md)
- [<span data-ttu-id="5a9e8-138">Konfigurera livshändelsetyper</span><span class="sxs-lookup"><span data-stu-id="5a9e8-138">Configure life event types</span></span>](hr-benefits-setup-life-event-types.md)
- [<span data-ttu-id="5a9e8-139">Skapa plantyper</span><span class="sxs-lookup"><span data-stu-id="5a9e8-139">Create plan types</span></span>](hr-benefits-setup-plan-types.md)
- [<span data-ttu-id="5a9e8-140">Ställa in orsakskoder</span><span class="sxs-lookup"><span data-stu-id="5a9e8-140">Set up reason codes</span></span>](hr-benefits-setup-reason-codes.md)
- [<span data-ttu-id="5a9e8-141">Ställa in skiktkoder</span><span class="sxs-lookup"><span data-stu-id="5a9e8-141">Set up tier codes</span></span>](hr-benefits-setup-tier-codes.md)
- [<span data-ttu-id="5a9e8-142">Konfigurera satser</span><span class="sxs-lookup"><span data-stu-id="5a9e8-142">Configure rates</span></span>](hr-benefits-setup-rates.md)
- [<span data-ttu-id="5a9e8-143">Konfigurera avdrag</span><span class="sxs-lookup"><span data-stu-id="5a9e8-143">Configure deductions</span></span>](hr-benefits-setup-deductions.md)
- [<span data-ttu-id="5a9e8-144">Konfigurera väntedagar</span><span class="sxs-lookup"><span data-stu-id="5a9e8-144">Configure waiting days</span></span>](hr-benefits-setup-waiting-days.md)
- [<span data-ttu-id="5a9e8-145">Konfigurera vänteperioder</span><span class="sxs-lookup"><span data-stu-id="5a9e8-145">Configure waiting periods</span></span>](hr-benefits-setup-waiting-periods.md)
- [<span data-ttu-id="5a9e8-146">Ställa in avrundningsregler</span><span class="sxs-lookup"><span data-stu-id="5a9e8-146">Set up rounding rules</span></span>](hr-benefits-setup-rounding-rules.md)
- [<span data-ttu-id="5a9e8-147">Skapa anställningskategorier</span><span class="sxs-lookup"><span data-stu-id="5a9e8-147">Create employment categories</span></span>](hr-benefits-setup-employment-categories.md)
- [<span data-ttu-id="5a9e8-148">Ställ in anställningstyper</span><span class="sxs-lookup"><span data-stu-id="5a9e8-148">Set up employment types</span></span>](hr-benefits-setup-employment-types.md)
- [<span data-ttu-id="5a9e8-149">Konfigurera självbetjäning för medarbetare</span><span class="sxs-lookup"><span data-stu-id="5a9e8-149">Configure employee self service</span></span>](hr-benefits-setup-employee-self-service.md)

## <a name="create-benefit-plans"></a><span data-ttu-id="5a9e8-150">Skapa förmånsplaner</span><span class="sxs-lookup"><span data-stu-id="5a9e8-150">Create benefit plans</span></span>

<span data-ttu-id="5a9e8-151">Dessa artiklar visar hur du skapar förmånsplaner, inklusive buntar och flexkreditprogram.</span><span class="sxs-lookup"><span data-stu-id="5a9e8-151">These articles show how to create benefit plans, including bundles and flex credit programs.</span></span>

- [<span data-ttu-id="5a9e8-152">Ställa in förmånsplaner</span><span class="sxs-lookup"><span data-stu-id="5a9e8-152">Set up benefit plans</span></span>](hr-benefits-plans-setup.md)
- [<span data-ttu-id="5a9e8-153">Ställa in flexkreditprogram</span><span class="sxs-lookup"><span data-stu-id="5a9e8-153">Set up flex credit programs</span></span>](hr-benefits-plans-flex-credit-programs.md)

## <a name="process-benefit-plans"></a><span data-ttu-id="5a9e8-154">Bearbeta förmånsplaner</span><span class="sxs-lookup"><span data-stu-id="5a9e8-154">Process benefit plans</span></span>

<span data-ttu-id="5a9e8-155">Du måste bearbeta några av dina ändringar för att göra dem aktiva.</span><span class="sxs-lookup"><span data-stu-id="5a9e8-155">You need to process some of your changes to make them active.</span></span>

- [<span data-ttu-id="5a9e8-156">Bearbetning av berättigande för anmälan</span><span class="sxs-lookup"><span data-stu-id="5a9e8-156">Process enrollment eligibility</span></span>](hr-benefits-process-enrollment-eligibility.md)
- [<span data-ttu-id="5a9e8-157">Bearbeta livshändelse</span><span class="sxs-lookup"><span data-stu-id="5a9e8-157">Process life events</span></span>](hr-benefits-process-life-events.md)
- [<span data-ttu-id="5a9e8-158">Bearbeta ändring av livshändelse</span><span class="sxs-lookup"><span data-stu-id="5a9e8-158">Process life event changes</span></span>](hr-benefits-process-life-event-changes.md)
- [<span data-ttu-id="5a9e8-159">Bearbetning av berättigande för livshändelse</span><span class="sxs-lookup"><span data-stu-id="5a9e8-159">Process life event eligibility</span></span>](hr-benefits-process-life-event-eligibility.md)
- [<span data-ttu-id="5a9e8-160">Behandla prisändringar</span><span class="sxs-lookup"><span data-stu-id="5a9e8-160">Process rate changes</span></span>](hr-benefits-process-rate-changes.md)

