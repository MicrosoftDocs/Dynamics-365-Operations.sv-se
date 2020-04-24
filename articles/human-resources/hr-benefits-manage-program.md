---
title: Definiera och hantera ett förmånsprogram
description: Personal innehåller en uppsättning av verktyg som kan användas för att ställa in och underhålla förmåner, avdrag och arbetares kompensationsplaner som en organisation ger eller bearbetar för dess arbetare. Denna artikel innehåller information om hur du ställer in och hanterar förmåner.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
ms.search.form: HcmBenefitEligibilityDetail, HcmBenefitSelection, SysPolicyListPage, SysPolicySourceDocumentRuleType
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Human Resources
ms.custom: 15681
ms.assetid: 6aee97ac-29f7-4b3c-8aa1-c65810de3090
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: b976bccf7f5da4483ec8a015f464db764b82a2f1
ms.sourcegitcommit: 79f8aa2c0b166a423db9b8503da53e96e3fc43dc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2020
ms.locfileid: "3197899"
---
# <a name="define-and-manage-a-benefits-program"></a><span data-ttu-id="ceb50-104">Definiera och hantera ett förmånsprogram</span><span class="sxs-lookup"><span data-stu-id="ceb50-104">Define and manage a benefits program</span></span>

<span data-ttu-id="ceb50-105">Personal innehåller en uppsättning av verktyg som kan användas för att ställa in och underhålla förmåner, avdrag och arbetares kompensationsplaner som en organisation ger eller bearbetar för dess arbetare.</span><span class="sxs-lookup"><span data-stu-id="ceb50-105">Human Resources provides a set of tools that can be used to set up and maintain benefits, deductions, and workers' compensation plans that an organization offers or processes for its workers.</span></span> <span data-ttu-id="ceb50-106">Denna artikel innehåller information om hur du ställer in och hanterar förmåner.</span><span class="sxs-lookup"><span data-stu-id="ceb50-106">This article provides information about how to set up and manage benefits.</span></span>

## <a name="benefit-setup"></a><span data-ttu-id="ceb50-107">Förmånsinställning</span><span class="sxs-lookup"><span data-stu-id="ceb50-107">Benefit setup</span></span>

<span data-ttu-id="ceb50-108">Innan arbetare kan anmäla sig till förmåner, måste du skapa elementen för varje förmån.</span><span class="sxs-lookup"><span data-stu-id="ceb50-108">Before workers can be enrolled in benefits, you must create the elements of each benefit.</span></span> <span data-ttu-id="ceb50-109">Dessa element kombinerar liknande förmånplaner och definierar standardinställningen, till exempel avdragspriser och redovisningsinformation.</span><span class="sxs-lookup"><span data-stu-id="ceb50-109">These elements combine similar benefit plans and define default settings, such as deduction rates and accounting details.</span></span> <span data-ttu-id="ceb50-110">Många av de här inställningarna kan justeras när arbetare anmäler sig till förmånen vid ett senare tillfälle.</span><span class="sxs-lookup"><span data-stu-id="ceb50-110">Many of these settings can be adjusted when workers are later enrolled in the benefit.</span></span> <span data-ttu-id="ceb50-111">För varje förmånplan kan en organisation erbjuda flera anmälningsalternativ, eller så kan en arbetare anmäla sig till planen.</span><span class="sxs-lookup"><span data-stu-id="ceb50-111">For each benefit plan, an organization can offer several enrollment options, or a worker can waive enrollment in the plan.</span></span> 

<span data-ttu-id="ceb50-112">[![Processflöde för förmåner](./media/benefit-process-flow1.png)](./media/benefit-process-flow1.png)</span><span class="sxs-lookup"><span data-stu-id="ceb50-112">[![Benefit process flow](./media/benefit-process-flow1.png)](./media/benefit-process-flow1.png)</span></span>

## <a name="benefit-elements"></a><span data-ttu-id="ceb50-113">Förmånselement</span><span class="sxs-lookup"><span data-stu-id="ceb50-113">Benefit elements</span></span>

<span data-ttu-id="ceb50-114">Innan du börjar skapa förmåner och anmäla arbetare till dem, måste du definiera de element som utgör en förmån: typ, plan och alternativ.</span><span class="sxs-lookup"><span data-stu-id="ceb50-114">Before you begin to create benefits and enroll workers in them, you must define the elements that make up a benefit: the type, plan, and options.</span></span>

-   <span data-ttu-id="ceb50-115">**Typ** – en samling planer för en viss förmån, till exempel medicin eller parkering.</span><span class="sxs-lookup"><span data-stu-id="ceb50-115">**Type** – A collection of plans for a specific benefit, such as medical or parking.</span></span>
-   <span data-ttu-id="ceb50-116">**Plan** – en viss förmån som avtalats från en leverantör.</span><span class="sxs-lookup"><span data-stu-id="ceb50-116">**Plan** – A specific benefit that is contracted from a provider.</span></span>
-   <span data-ttu-id="ceb50-117">**Alternativ** – omfattningsnivån, exempelvis endast medarbetare eller endast medarbetare och make/maka/partner.</span><span class="sxs-lookup"><span data-stu-id="ceb50-117">**Option** – The coverage level, such as employee only, or employee and spouse/partner.</span></span>

<span data-ttu-id="ceb50-118">För varje typ av förmån som till exempel syn- eller tandvård kan en organisation erbjuda en eller flera planer till dess arbetare.</span><span class="sxs-lookup"><span data-stu-id="ceb50-118">For each type of benefit, such as vision or dental, an organization can offer one or more plans to its workers.</span></span> <span data-ttu-id="ceb50-119">För varje plan kan organisationen erbjuda olika alternativ.</span><span class="sxs-lookup"><span data-stu-id="ceb50-119">For each plan, the organization can offer different options.</span></span> <span data-ttu-id="ceb50-120">T.ex. kan arbetare köpa ytterligare livförsäkringsplaner på ett, två eller tre gånger deras årliga lön.</span><span class="sxs-lookup"><span data-stu-id="ceb50-120">For example, workers can buy additional term life insurance coverage at one, two, or three times their yearly salary.</span></span> <span data-ttu-id="ceb50-121">Varje kombination av en plan och alternativ blir en förmån som arbetare kan anmäla sig till.</span><span class="sxs-lookup"><span data-stu-id="ceb50-121">Each combination of a plan and options becomes a benefit that workers can enroll in.</span></span> 

<span data-ttu-id="ceb50-122">[![förmånsbild](./media/benefit-pic.png)](./media/benefit-pic.png)</span><span class="sxs-lookup"><span data-stu-id="ceb50-122">[![benefit pic](./media/benefit-pic.png)](./media/benefit-pic.png)</span></span>

## <a name="eligibility"></a><span data-ttu-id="ceb50-123">Berättigande</span><span class="sxs-lookup"><span data-stu-id="ceb50-123">Eligibility</span></span>
<span data-ttu-id="ceb50-124">Många faktorer bestämmer berättigande för arbetaren för olika typer av förmåner som en arbetsgivare erbjuder.</span><span class="sxs-lookup"><span data-stu-id="ceb50-124">Many factors determine worker eligibility for the various types of benefits that an employer offers.</span></span> <span data-ttu-id="ceb50-125">När du skapar en förmån i Dynamics 365 Human Resources kan du ange den typ av berättigande som gäller för den förmånen.</span><span class="sxs-lookup"><span data-stu-id="ceb50-125">When you create a benefit in Dynamics 365 Human Resources, you can set the type of eligibility that applies to that benefit.</span></span> 

<span data-ttu-id="ceb50-126">Du kan göra en förmån tillgänglig för alla arbetare.</span><span class="sxs-lookup"><span data-stu-id="ceb50-126">You can make a benefit available to all workers.</span></span> <span data-ttu-id="ceb50-127">Vissa företag erbjuder till exempel parkeringstillstånd för alla medarbetare som en löneförmån.</span><span class="sxs-lookup"><span data-stu-id="ceb50-127">For example, some companies offer parking passes to all employees as a fringe benefit.</span></span> <span data-ttu-id="ceb50-128">När du skapar den här förmånen, förmån du ställer in berättigande till **Alla arbetare är berättigade**.</span><span class="sxs-lookup"><span data-stu-id="ceb50-128">When you create this benefit, you set the eligibility to **All workers are eligible**.</span></span> 

<span data-ttu-id="ceb50-129">För andra förmåner, exempelvis införsel i lån och skatteavgifter, gäller inte behörigheten.</span><span class="sxs-lookup"><span data-stu-id="ceb50-129">For other benefits, such as garnishments and tax levies, eligibility doesn't apply.</span></span> <span data-ttu-id="ceb50-130">När du skapar dessa typer av förmåner anger du berättigandet som **Kringgå berättigandeprocessen**.</span><span class="sxs-lookup"><span data-stu-id="ceb50-130">Whey you create these types of benefits, you set the eligibility to **Bypass eligibility process**.</span></span> 

<span data-ttu-id="ceb50-131">Slutligen kan förmånsberättigandet vara regelbaserat.</span><span class="sxs-lookup"><span data-stu-id="ceb50-131">Finally, benefit eligibility can be rule-based.</span></span> <span data-ttu-id="ceb50-132">Ett företag erbjuder exempelvis två typer av livförsäkringsförmåner för medarbetare.</span><span class="sxs-lookup"><span data-stu-id="ceb50-132">For example, a company offers two types of life insurance benefit to employees.</span></span> <span data-ttu-id="ceb50-133">Anställda i ledande befattningar är berättigade till en livförsäkringsplan, medan alla andra heltidsanställda är berättigade till den andra livförsäkringsplanen.</span><span class="sxs-lookup"><span data-stu-id="ceb50-133">Executive employees are eligible for one life insurance plan, whereas all other full-time employees are eligible for the other life insurance plan.</span></span> <span data-ttu-id="ceb50-134">I Personal kan du skapa en förmånsberättiganderegel för att hitta alla anställda i ledande befattningar och en annan regel för att hitta alla andra heltidsanställda, och sedan tillämpa dessa regler på lämplig förmån.</span><span class="sxs-lookup"><span data-stu-id="ceb50-134">In Human Resources, you can create a benefit eligibility rule to find all executive employees and another rule to find all other full-time employees, and then apply those rules to the appropriate benefit.</span></span>

## <a name="enrollment"></a><span data-ttu-id="ceb50-135">Anmälning</span><span class="sxs-lookup"><span data-stu-id="ceb50-135">Enrollment</span></span>
<span data-ttu-id="ceb50-136">När du har skapat de förmåner som din organisation erbjuder och har fastställt berättigande, kan du registrera dina anställda på förmåner.</span><span class="sxs-lookup"><span data-stu-id="ceb50-136">After you've created the benefits that your organization offers and determined eligibility, you can enroll your workers in benefits.</span></span> <span data-ttu-id="ceb50-137">Du kan skriva in som ett enda anställd i förmåner, eller så kan du anmäla sig många anställd i en eller flera förmåner under en enskild process.</span><span class="sxs-lookup"><span data-stu-id="ceb50-137">You can enroll a single worker in benefits, or you can enroll many workers in one or more benefits during a single process.</span></span> 

<span data-ttu-id="ceb50-138">Ibland stoppar en organisation att erbjuda vissa förmåner.</span><span class="sxs-lookup"><span data-stu-id="ceb50-138">Sometimes, an organization stops offering certain benefits.</span></span> <span data-ttu-id="ceb50-139">I det här fallet måste du uppdatera förmånen och den personal som registrerats för den.</span><span class="sxs-lookup"><span data-stu-id="ceb50-139">In this case, you must update the benefit and the workers who are enrolled in.</span></span> <span data-ttu-id="ceb50-140">Med massutgångsdatum kan du ändra utgångsdatumet för både en förmån och medarbetarregistreringarna för denna förmån samtidigt.</span><span class="sxs-lookup"><span data-stu-id="ceb50-140">Mass benefit expiration lets you change the expiration date of both a benefit and the worker enrollments for that benefit at the same time.</span></span> <span data-ttu-id="ceb50-141">Du kan också markera flera anställd, som är anmäld till en förmån, och ändra slutdatumet för deras disponering.</span><span class="sxs-lookup"><span data-stu-id="ceb50-141">You can also select multiple workers who are enrolled in a benefit and change the ending date of their coverage.</span></span> 

<span data-ttu-id="ceb50-142">På liknande sätt låter dig förlängning av massförmån dig förlänga sista giltighetsdatum för både en förmån och för medarbetarregistreringar för den förmånen om du väljer att erbjuda en förmån längre än vad du ursprungligen planerade.</span><span class="sxs-lookup"><span data-stu-id="ceb50-142">Similarly, mass benefit extension lets you extend the expiration date of both a benefit and the worker enrollments for that benefit if you decide to offer a benefit longer than you originally planned.</span></span>


