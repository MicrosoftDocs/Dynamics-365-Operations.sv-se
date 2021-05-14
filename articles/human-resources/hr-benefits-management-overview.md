---
title: Hantering av förmåner – översikt
description: Översikt över funktionen för förmånshantering i Dynamics 365 Human Resources. Erbjud dina medarbetare utökade förmånsalternativ med en lättanvänd onlineupplevelse.
author: andreabichsel
ms.date: 04/21/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 4ad94d81d7e8bedd3622b3e073e431bc4abaafff
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924240"
---
# <a name="benefits-management-overview"></a><span data-ttu-id="20589-104">Förmånshantering – översikt</span><span class="sxs-lookup"><span data-stu-id="20589-104">Benefits management overview</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="20589-105">För att vara konkurrenskraftig måste du erbjuda en stor mängd fördelar för att kunna locka till dig och behålla dina bästa anställda.</span><span class="sxs-lookup"><span data-stu-id="20589-105">To remain competitive, you must offer a rich set of benefits to attract and retain your best employees.</span></span> <span data-ttu-id="20589-106">Förutom standardförmåner som sjukvård och tandvård kanske du även vill erbjuda utökade tjänster som implementeringshjälp, rekreationsprogram och bidrag till kläder.</span><span class="sxs-lookup"><span data-stu-id="20589-106">In addition to standard benefits like medical and dental coverage, you might also want to offer expanded services like adoption assistance, recreation programs, and clothing allowances.</span></span> <span data-ttu-id="20589-107">Med förmånshantering i Microsoft Dynamics 365 Human Resources får du en flexibel lösning som stöder en mängd olika förmånsalternativ.</span><span class="sxs-lookup"><span data-stu-id="20589-107">Benefits management in Microsoft Dynamics 365 Human Resources provides you with a flexible solution that supports a wide variety of benefit options.</span></span> <span data-ttu-id="20589-108">Personal inkluderar också en lättanvänd medarbetarupplevelse som visar dina erbjudanden.</span><span class="sxs-lookup"><span data-stu-id="20589-108">Human Resources also includes an easy-to-use employee experience that showcases your offerings.</span></span>

- <span data-ttu-id="20589-109">Med hjälp av förbättrade förmånsplaner kan du skapa och hantera unika förmånsplaner och stödja komplexa förmånspristabeller och kapslade nivåer.</span><span class="sxs-lookup"><span data-stu-id="20589-109">Enhanced benefits plans let you create and manage unique benefit plans and support complex benefit rate tables and nested tiers.</span></span> <span data-ttu-id="20589-110">Du kan enkelt skapa förmånsprogram, buntar och automatiska registreringsregler för en enklare medarbetarupplevelse.</span><span class="sxs-lookup"><span data-stu-id="20589-110">You can easily create benefit programs, bundles, and auto-enrollment rules for an easier employee experience.</span></span>

- <span data-ttu-id="20589-111">Med flexkreditprogram kan du göra proportionell fördelning för att stödja pension och andra livhändelser.</span><span class="sxs-lookup"><span data-stu-id="20589-111">Flex credit programs let you prorate to support retirement and other life events.</span></span>

- <span data-ttu-id="20589-112">Omfattande berättiganderegler garanterar att du gör rätt förmåner tillgängliga för rätt medarbetare.</span><span class="sxs-lookup"><span data-stu-id="20589-112">Extensive eligibility rules ensure you make the right benefits available to the right employees.</span></span>

- <span data-ttu-id="20589-113">En anmälan online av förmåner är en enkel upplevelse för dina anställda.</span><span class="sxs-lookup"><span data-stu-id="20589-113">Online benefits enrollment provides an easy experience for your employees.</span></span>

- <span data-ttu-id="20589-114">Kvalificerad bearbetning av livshändelse stöder framtida livshändelser.</span><span class="sxs-lookup"><span data-stu-id="20589-114">Qualified life event processing supports future life events.</span></span>

<span data-ttu-id="20589-115">Om du vill ha tillgång till demonstrationsdata måste du omdistribuera miljön i begränsat läge.</span><span class="sxs-lookup"><span data-stu-id="20589-115">If you would like to access the demo data, you'll need to redeploy your sandbox environment.</span></span>

>[!NOTE]
><span data-ttu-id="20589-116">Du kan nu formulären för hantering av förmåner.</span><span class="sxs-lookup"><span data-stu-id="20589-116">You can now customize Benefits management forms.</span></span> <span data-ttu-id="20589-117">Du kan nu lägga till anpassade fält som hör till disponeringssatser i formuläret **Disponeringsalternativ** för förmånsplaner.</span><span class="sxs-lookup"><span data-stu-id="20589-117">You can now add custom fields related to coverage rates to the **Coverage option** form for benefit plans.</span></span> <span data-ttu-id="20589-118">Mer information om arbete med anpassade fält finns i [Anpassade fält](hr-developer-custom-fields.md).</span><span class="sxs-lookup"><span data-stu-id="20589-118">For more information about working with custom fields, see [Custom fields](hr-developer-custom-fields.md).</span></span>
><span data-ttu-id="20589-119">![Anpassade fält för förmånshantering](media/hr-benefits-management-custom-fields.png)</span><span class="sxs-lookup"><span data-stu-id="20589-119">![Benefits management custom fields](media/hr-benefits-management-custom-fields.png)</span></span>

## <a name="enable-benefits-management"></a><span data-ttu-id="20589-120">Aktivera hantering av förmåner</span><span class="sxs-lookup"><span data-stu-id="20589-120">Enable Benefits management</span></span>

<span data-ttu-id="20589-121">Det här ämnet beskriver hur du aktiverar funktionerna i personal.</span><span class="sxs-lookup"><span data-stu-id="20589-121">This topic describes how to turn on features in Human Resources.</span></span> <span data-ttu-id="20589-122">Den talar också om vilka befintliga funktioner i personal som hantering av förmåner ersätter eller inaktiveras när du har aktiverat hantering av förmåner.</span><span class="sxs-lookup"><span data-stu-id="20589-122">It also tells which existing features in Human Resources that Benefits management replaces or are disabled once you turn on Benefits management.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="20589-123">När du har aktiverat hantering av förmåner i miljön **produktion** kan du inte inaktivera den.</span><span class="sxs-lookup"><span data-stu-id="20589-123">After you enable Benefits management in a **Production** environment, you can't disable it.</span></span> <span data-ttu-id="20589-124">Vi rekommenderar att du aktiverar och testar förmånshantering i en miljö med **begränsat läge** innan du aktiverar den i en miljö för **produktion**.</span><span class="sxs-lookup"><span data-stu-id="20589-124">We recommend enabling and testing Benefits management in a **Sandbox** environment before enabling it in a **Production** environment.</span></span> <span data-ttu-id="20589-125">Det finns betydande skillnader mellan den tidigare förmånsfunktionen och nya fördelar för hanteringsfunktioner som kräver ytterligare inställningar och bör testas innan de kan placeras i produktionen.</span><span class="sxs-lookup"><span data-stu-id="20589-125">There are significant differences between the legacy Benefit functionality and new Benefits management functionality that require additional setup and should be tested prior to being placed into production.</span></span>

- [<span data-ttu-id="20589-126">Hantera funktioner</span><span class="sxs-lookup"><span data-stu-id="20589-126">Manage features</span></span>](hr-admin-manage-features.md)

## <a name="configure-employee-information"></a><span data-ttu-id="20589-127">Konfigurera information om medarbetare</span><span class="sxs-lookup"><span data-stu-id="20589-127">Configure employee information</span></span>

<span data-ttu-id="20589-128">Innan du kan registrera medarbetare i förmåner måste du ange den information som krävs.</span><span class="sxs-lookup"><span data-stu-id="20589-128">Before you can enroll employees in benefits, you must provide required information.</span></span> <span data-ttu-id="20589-129">Du måste registrera en medarbetare i en **fast kompensationsplan** på deras startdatum och du måste välja en **förmånslönefrekvens** i **medarbetarinformation** i formuläret **medarbetare**.</span><span class="sxs-lookup"><span data-stu-id="20589-129">You must enroll an employee in a **Fixed compensation plan** on their start date, and you must select a **Benefit pay frequency** in **Employment details** on the **Worker** form.</span></span>

<span data-ttu-id="20589-130">Om du har en medarbetare som tar emot kompletterande kompensation som provisioner kan du lägga till ett belopp för **årslön** från medarbetarposten.</span><span class="sxs-lookup"><span data-stu-id="20589-130">If you have an employee who receives supplemental compensation like commissions, you can add a **Benefits annual salary** amount from the employee record.</span></span> <span data-ttu-id="20589-131">Personal kommer att använda beloppet **Årslön** vid fastställande av täckningsbelopp, istället för det årliga beloppet för fast ersättning.</span><span class="sxs-lookup"><span data-stu-id="20589-131">Human Resources will use the **Benefits annual salary** amount when determining coverage amounts, instead of the fixed compensation annual amount.</span></span> <span data-ttu-id="20589-132">Den **Årslönen** måste vara giltig för medarbetarens startdatum eller början av förmånsperioden, beroende på vilket som är senaste.</span><span class="sxs-lookup"><span data-stu-id="20589-132">The **Benefits annual salary** must be valid as of the employee’s start date or the beginning of the benefit period, whichever is latest.</span></span> <span data-ttu-id="20589-133">Om både en fast kompensation och bestämda årslönsbelopp registreras för en medarbetare, kommer den bestämda årslönen att användas vid fast ställande av täckningsbelopp.</span><span class="sxs-lookup"><span data-stu-id="20589-133">If both a fixed compensation and benefits annual salary amount is recorded for an employee, the benefits annual salary will be used in determining coverage amounts.</span></span>

<span data-ttu-id="20589-134">När du skapar en förmånsplan som bygger på kön eller ålder måste du ange ett födelsedatum och kön för medarbetaren för att beräkna förmånskostnaden.</span><span class="sxs-lookup"><span data-stu-id="20589-134">When you create a benefit plan that uses rates that are based on gender or age, you must enter a birth date and gender for the employee to calculate the benefit cost.</span></span>

## <a name="configure-benefits-management"></a><span data-ttu-id="20589-135">Konfigurera förmånshantering</span><span class="sxs-lookup"><span data-stu-id="20589-135">Configure Benefits management</span></span>

<span data-ttu-id="20589-136">Innan du kan skapa förmånsplaner för dina medarbetare måste du konfigurera alternativen för planerna.</span><span class="sxs-lookup"><span data-stu-id="20589-136">Before you can create benefit plans for your employees, you need to configure options for the plans.</span></span>

- [<span data-ttu-id="20589-137">Ställ in parametrar för hantering av förmåner</span><span class="sxs-lookup"><span data-stu-id="20589-137">Set Benefits management parameters</span></span>](hr-benefits-setup-parameters.md)
- [<span data-ttu-id="20589-138">Konfigurera berättiganderegler och alternativ</span><span class="sxs-lookup"><span data-stu-id="20589-138">Configure eligibility rules and options</span></span>](hr-benefits-setup-eligibility-rules.md)
- [<span data-ttu-id="20589-139">Konfigurera berättigandealternativ för personlig kontakt</span><span class="sxs-lookup"><span data-stu-id="20589-139">Configure personal contact eligibility options</span></span>](hr-benefits-setup-contact-eligibility-options.md)
- [<span data-ttu-id="20589-140">Skapa disponeringsalternativ</span><span class="sxs-lookup"><span data-stu-id="20589-140">Create coverage options</span></span>](hr-benefits-setup-coverage-options.md)
- [<span data-ttu-id="20589-141">Ställa in betalningsfrekvenser</span><span class="sxs-lookup"><span data-stu-id="20589-141">Set up payment frequencies</span></span>](hr-benefits-setup-payment-frequencies.md)
- [<span data-ttu-id="20589-142">Konfigurera livshändelsetyper</span><span class="sxs-lookup"><span data-stu-id="20589-142">Configure life event types</span></span>](hr-benefits-setup-life-event-types.md)
- [<span data-ttu-id="20589-143">Skapa plantyper</span><span class="sxs-lookup"><span data-stu-id="20589-143">Create plan types</span></span>](hr-benefits-setup-plan-types.md)
- [<span data-ttu-id="20589-144">Ställa in orsakskoder</span><span class="sxs-lookup"><span data-stu-id="20589-144">Set up reason codes</span></span>](hr-benefits-setup-reason-codes.md)
- [<span data-ttu-id="20589-145">Ställa in skiktkoder</span><span class="sxs-lookup"><span data-stu-id="20589-145">Set up tier codes</span></span>](hr-benefits-setup-tier-codes.md)
- [<span data-ttu-id="20589-146">Konfigurera satser</span><span class="sxs-lookup"><span data-stu-id="20589-146">Configure rates</span></span>](hr-benefits-setup-rates.md)
- [<span data-ttu-id="20589-147">Konfigurera avdrag</span><span class="sxs-lookup"><span data-stu-id="20589-147">Configure deductions</span></span>](hr-benefits-setup-deductions.md)
- [<span data-ttu-id="20589-148">Konfigurera väntedagar</span><span class="sxs-lookup"><span data-stu-id="20589-148">Configure waiting days</span></span>](hr-benefits-setup-waiting-days.md)
- [<span data-ttu-id="20589-149">Konfigurera vänteperioder</span><span class="sxs-lookup"><span data-stu-id="20589-149">Configure waiting periods</span></span>](hr-benefits-setup-waiting-periods.md)
- [<span data-ttu-id="20589-150">Ställa in avrundningsregler</span><span class="sxs-lookup"><span data-stu-id="20589-150">Set up rounding rules</span></span>](hr-benefits-setup-rounding-rules.md)
- [<span data-ttu-id="20589-151">Skapa anställningskategorier</span><span class="sxs-lookup"><span data-stu-id="20589-151">Create employment categories</span></span>](hr-benefits-setup-employment-categories.md)
- [<span data-ttu-id="20589-152">Ställ in anställningstyper</span><span class="sxs-lookup"><span data-stu-id="20589-152">Set up employment types</span></span>](hr-benefits-setup-employment-types.md)
- [<span data-ttu-id="20589-153">Konfigurera självbetjäning för medarbetare</span><span class="sxs-lookup"><span data-stu-id="20589-153">Configure employee self service</span></span>](hr-benefits-setup-employee-self-service.md)

## <a name="create-benefit-plans"></a><span data-ttu-id="20589-154">Skapa förmånsplaner</span><span class="sxs-lookup"><span data-stu-id="20589-154">Create benefit plans</span></span>

<span data-ttu-id="20589-155">Dessa artiklar visar hur du skapar förmånsplaner, inklusive buntar och flexkreditprogram.</span><span class="sxs-lookup"><span data-stu-id="20589-155">These articles show how to create benefit plans, including bundles and flex credit programs.</span></span>

- [<span data-ttu-id="20589-156">Ställa in förmånsplaner</span><span class="sxs-lookup"><span data-stu-id="20589-156">Set up benefit plans</span></span>](hr-benefits-plans-setup.md)
- [<span data-ttu-id="20589-157">Ställa in flexkreditprogram</span><span class="sxs-lookup"><span data-stu-id="20589-157">Set up flex credit programs</span></span>](hr-benefits-plans-flex-credit-programs.md)

## <a name="process-benefit-plans"></a><span data-ttu-id="20589-158">Bearbeta förmånsplaner</span><span class="sxs-lookup"><span data-stu-id="20589-158">Process benefit plans</span></span>

<span data-ttu-id="20589-159">Du måste bearbeta några av dina ändringar för att göra dem aktiva.</span><span class="sxs-lookup"><span data-stu-id="20589-159">You need to process some of your changes to make them active.</span></span>

- [<span data-ttu-id="20589-160">Bearbetning av berättigande för anmälan</span><span class="sxs-lookup"><span data-stu-id="20589-160">Process enrollment eligibility</span></span>](hr-benefits-process-enrollment-eligibility.md)
- [<span data-ttu-id="20589-161">Bearbeta livshändelse</span><span class="sxs-lookup"><span data-stu-id="20589-161">Process life events</span></span>](hr-benefits-process-life-events.md)
- [<span data-ttu-id="20589-162">Bearbeta ändring av livshändelse</span><span class="sxs-lookup"><span data-stu-id="20589-162">Process life event changes</span></span>](hr-benefits-process-life-event-changes.md)
- [<span data-ttu-id="20589-163">Bearbetning av berättigande för livshändelse</span><span class="sxs-lookup"><span data-stu-id="20589-163">Process life event eligibility</span></span>](hr-benefits-process-life-event-eligibility.md)
- [<span data-ttu-id="20589-164">Behandla prisändringar</span><span class="sxs-lookup"><span data-stu-id="20589-164">Process rate changes</span></span>](hr-benefits-process-rate-changes.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]