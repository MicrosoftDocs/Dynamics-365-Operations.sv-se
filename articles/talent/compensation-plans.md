---
title: Kompensationsplaner
description: Kompensations- och förmånschefer kan använda kompensationshantering för att underhålla och bearbeta fasta och variabla kompensationsplaner för organisationens medarbetare.
author: andreabichsel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: HcmCompensationLevel, HRCCompGrid, HRMCompFixedAction, HRMCompFixedBudget, HRMCompFixedPlanTable
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.openlocfilehash: 8e7e41756c3be73937ef62523ff6bf41536405b0
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/06/2019
ms.locfileid: "2898860"
---
# <a name="compensation-plans"></a><span data-ttu-id="509fc-103">Kompensationsplaner</span><span class="sxs-lookup"><span data-stu-id="509fc-103">Compensation plans</span></span>

<span data-ttu-id="509fc-104">Kompensations- och förmånschefer kan använda kompensationshantering för att underhålla och bearbeta fasta och variabla kompensationsplaner för organisationens medarbetare.</span><span class="sxs-lookup"><span data-stu-id="509fc-104">Compensation and Benefits Managers can use Compensation management to maintain and process fixed and variable compensation plans for the organization's employees.</span></span>

### <a name="introduction"></a><span data-ttu-id="509fc-105">Introduktion</span><span class="sxs-lookup"><span data-stu-id="509fc-105">Introduction</span></span>

<span data-ttu-id="509fc-106">Kompensationshantering används för att styra du utbetalningen av grundlön och belöningar.</span><span class="sxs-lookup"><span data-stu-id="509fc-106">Compensation management is used to control the delivery of base pay and awards.</span></span> <span data-ttu-id="509fc-107">En medarbetares fasta grundlön och merithöjningar kontrolleras genom fasta kompensationsplaner.</span><span class="sxs-lookup"><span data-stu-id="509fc-107">An employee's fixed base pay and merit increases are controlled through fixed compensation plans.</span></span> <span data-ttu-id="509fc-108">Betalningen av incitament, till exempel bonusar, resultatbelöningar, aktieoptioner och anslag och även engångsbelöningar kontrolleras genom variabla kompensationsplaner.</span><span class="sxs-lookup"><span data-stu-id="509fc-108">The payment of incentive pay, such as bonus payments, performance awards, stock options, and grants, and also one-time awards, are controlled through variable compensation plans.</span></span> 

<span data-ttu-id="509fc-109">Medarbetare kan registreras i en eller flera planer av båda typerna.</span><span class="sxs-lookup"><span data-stu-id="509fc-109">Employees can be enrolled in one or more plans of both types.</span></span> <span data-ttu-id="509fc-110">En medarbetare måste uppfylla följande krav för att kunna registreras i en kompensationsplan:</span><span class="sxs-lookup"><span data-stu-id="509fc-110">An employee must meet the following requirements in order to be eligible for enrollment in a compensation plan:</span></span>
-   <span data-ttu-id="509fc-111">Medarbetaren måste ha en aktiv befattningstilldelning.</span><span class="sxs-lookup"><span data-stu-id="509fc-111">The employee must have an active position assignment.</span></span>
-   <span data-ttu-id="509fc-112">Medarbetaren måste uppfylla villkoren som definieras av berättiganderegler för en kompensationsplan.</span><span class="sxs-lookup"><span data-stu-id="509fc-112">The employee must meet the criteria that are defined by eligibility rules for a compensation plan.</span></span>

## <a name="compensation-setup"></a><span data-ttu-id="509fc-113"> Kompensationskonfiguration</span><span class="sxs-lookup"><span data-stu-id="509fc-113">Compensation setup</span></span>
<span data-ttu-id="509fc-114">Följande register visar komponenter i kompensationsprocessen som kan vara väsentliga i konfigurationen av ditt företags kompensationsplaner.</span><span class="sxs-lookup"><span data-stu-id="509fc-114">The following table lists components of the compensation process that can be integral in setting up your company's compensation plans.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="509fc-115">Komponent</span><span class="sxs-lookup"><span data-stu-id="509fc-115">Component</span></span></th>
<th><span data-ttu-id="509fc-116">Mer information …</span><span class="sxs-lookup"><span data-stu-id="509fc-116">More information…</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="509fc-117">Åtgärder för fast kompensation</span><span class="sxs-lookup"><span data-stu-id="509fc-117">Fixed compensation actions</span></span></td>
<td><span data-ttu-id="509fc-118">Fasta kompensationsåtgärder åstadkommer två syften:</span><span class="sxs-lookup"><span data-stu-id="509fc-118">Fixed compensation actions accomplish two purposes:</span></span>
<ul>
<li><span data-ttu-id="509fc-119">Åtgärder kan ange den typ av information som måste registreras när en medarbetares kompensation ändras.</span><span class="sxs-lookup"><span data-stu-id="509fc-119">Actions can specify the kind of information that must be recorded when an employee’s compensation changes.</span></span> <span data-ttu-id="509fc-120">Du kan till exempel kräva att orsaken till en ändring, till exempel en kampanj eller en degradering registreras.</span><span class="sxs-lookup"><span data-stu-id="509fc-120">For example, you can require that the reason a change, such as a promotion or a demotion be recorded.</span></span></li>
<li><span data-ttu-id="509fc-121">Åtgärder kan se till att en beräkning används när fasta kompensationsplaner bearbetas.</span><span class="sxs-lookup"><span data-stu-id="509fc-121">Actions can ensure that a calculation is applied when fixed compensation plans are processed.</span></span>  <span data-ttu-id="509fc-122">Exempelvis jämför åtgärder av typen Eget kapital medarbetarens lön med den minsta referenspunkten för medarbetarens nivå och ser till att medarbetaren får minst minimibeloppet betalt.</span><span class="sxs-lookup"><span data-stu-id="509fc-122">For example, actions of type Equity will compare the employees pay to the minimum reference point for the level on the employee&#39;s and ensure the employee is getting paid at least the minimum.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="509fc-123">Nivåer</span><span class="sxs-lookup"><span data-stu-id="509fc-123">Levels</span></span></td>
<td><span data-ttu-id="509fc-124">Nivåerna är associerade med olika jobb, och eventuella befattningar som är relaterade till en jobbreferens.</span><span class="sxs-lookup"><span data-stu-id="509fc-124">Levels are associated with jobs and any positions that are related to a job reference.</span></span> <span data-ttu-id="509fc-125">Du kan skapa diskreta nivåer för de tre typerna av kompensationsplaner: Grad, Band och Steg.</span><span class="sxs-lookup"><span data-stu-id="509fc-125">You can create discrete levels for the three types of compensation plans: Grade, Band, and Step.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="509fc-126">Matris för utnyttjande inom löneintervall</span><span class="sxs-lookup"><span data-stu-id="509fc-126">Range utilization matrix</span></span></td>
<td><span data-ttu-id="509fc-127">En intervallutnyttjandematris hjälper dig att migrera medarbetare till kontrollpunkten för deras jobb.</span><span class="sxs-lookup"><span data-stu-id="509fc-127">A range utilization matrix helps you transition employees to the control point for their jobs.</span></span> <span data-ttu-id="509fc-128">Du kan också använda intervallutnyttjandematrisen om du vill styra lönekapitalet inom företaget utan hänsyn till en enskild medarbetares prestanda eller företagets generella prestanda.</span><span class="sxs-lookup"><span data-stu-id="509fc-128">You can also use range utilization to control pay rate equity in the company without regard to an individual employee&#39;s performance or the overall performance of the company.</span></span> <span data-ttu-id="509fc-129">Lägre betalda medarbetare i intervallet får exempelvis procentuellt större ökningar än de som har en högre lön inom intervallet.</span><span class="sxs-lookup"><span data-stu-id="509fc-129">For example, employees who are paid lower in their range get higher percentage increases than employees who are paid higher in the range.</span></span> <span data-ttu-id="509fc-130">På så sätt kan du systematiskt motboka skillnader i eget kapital.</span><span class="sxs-lookup"><span data-stu-id="509fc-130">In this manner, you can systematically offset equity differences.</span></span> <span data-ttu-id="509fc-131">Intervallutnyttjandet beräknas på följande sätt: (Fast lönesats - Minsta intervallvärde) ÷ (Högsta intervallvärde - Minsta intervallvärde).</span><span class="sxs-lookup"><span data-stu-id="509fc-131">The range utilization is calculated as follows: (Fixed Pay Rate - Range Minimum) ÷ (Range Maximum - Range Minimum).</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="509fc-132">Referenspunktsinställningar</span><span class="sxs-lookup"><span data-stu-id="509fc-132">Reference point setups</span></span></td>
<td><span data-ttu-id="509fc-133">Referenspunktsinställningar omfattar ett antal referenspunkter som motsvarar intervallen i en lönesatsmatris.</span><span class="sxs-lookup"><span data-stu-id="509fc-133">A reference point setup includes a set of reference points that represent ranges in a matrix.</span></span> <span data-ttu-id="509fc-134">Varje intervall kan associeras med en lönesats.</span><span class="sxs-lookup"><span data-stu-id="509fc-134">Each range can be associated with a pay rate.</span></span> <span data-ttu-id="509fc-135">Till exempel har gradplaner ofta referenspunkter för minimum, mittpunkt och maximum.</span><span class="sxs-lookup"><span data-stu-id="509fc-135">For example, grade plans will often have reference points of Minimum, Midpoint, and Maximum.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="509fc-136">Kompensationsmatris</span><span class="sxs-lookup"><span data-stu-id="509fc-136">Compensation matrix</span></span></td>
<td><span data-ttu-id="509fc-137">En kompensationsmatris är en uppsättning referenspunkter och nivåer som du använder för att skapa en kompensationsstruktur.</span><span class="sxs-lookup"><span data-stu-id="509fc-137">A compensation matrix is the set of reference points and levels that you use to create a compensation structure.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="509fc-138">Kompensationsstruktur</span><span class="sxs-lookup"><span data-stu-id="509fc-138">Compensation structure</span></span></td>
<td><span data-ttu-id="509fc-139">En kompensationsstruktur är en kompensationsmatris som har lönesatser kopplade till referenspunkterna för varje nivå.</span><span class="sxs-lookup"><span data-stu-id="509fc-139">A compensation structure is a compensation matrix that has pay rates associated with the reference points for each level.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="509fc-140">Berättiganderegler</span><span class="sxs-lookup"><span data-stu-id="509fc-140">Eligibility rules</span></span></td>
<td><span data-ttu-id="509fc-141">Berättiganderegler används för att identifiera medarbetare i specifika jobb, jobbfunktioner, jobbtyper, avdelningar, fackföreningar eller kompensationsområden som täcks av specifika kompensationsplaner.</span><span class="sxs-lookup"><span data-stu-id="509fc-141">Eligibility rules are used to identify employees in specific jobs, job functions, job types, departments, labor unions, or compensation regions that are covered by specific compensation plans.</span></span> <span data-ttu-id="509fc-142">Du måste skapa berättiganderegler för både fasta och variabla kompensationsplaner när du vill anmäla medarbetare till planen.</span><span class="sxs-lookup"><span data-stu-id="509fc-142">You must create eligibility rules for both variable and fixed compensation plans in order to enroll employees in the plan.</span></span> <span data-ttu-id="509fc-143">När du har angett berättiganderegler för en kompensationsplan kan du definiera vilka nivåer som ska tillämpas på jobben som omfattas av planen.</span><span class="sxs-lookup"><span data-stu-id="509fc-143">After eligibility rules are specified for a compensation plan, you can define the levels that should apply to the jobs that are covered by the plan.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="509fc-144">Lönefrekvenser</span><span class="sxs-lookup"><span data-stu-id="509fc-144">Pay frequencies</span></span></td>
<td><span data-ttu-id="509fc-145">Lönefrekvenser används för att definiera den tidsperiod för vilken kompensationen anges.</span><span class="sxs-lookup"><span data-stu-id="509fc-145">Pay frequencies are used to define the time period for which the compensation is specified.</span></span>  <span data-ttu-id="509fc-146">Till exempel hjälper lönefrekvensen dig att förstå huruvida kompensationsbeloppet anges som en årslön kontra en timlön.</span><span class="sxs-lookup"><span data-stu-id="509fc-146">For example, the pay frequency helps you understand if the compensation amount is specified as an annual salary versus an hourly pay rate.</span></span> <span data-ttu-id="509fc-147">Lönefrekvenser används också för att ställa in konverteringsfaktorer om du vill konvertera kompensationsbelopp från månadslön, veckolön, varannanveckaslön och timlön till en årlig lönefrekvens.</span><span class="sxs-lookup"><span data-stu-id="509fc-147">Pay frequencies are also used to set up conversion factors to convert compensation amounts from monthly, weekly, biweekly and hourly pay frequencies to an annual pay frequency.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="509fc-148">Kompensationsregioner</span><span class="sxs-lookup"><span data-stu-id="509fc-148">Compensation regions</span></span></td>
<td><span data-ttu-id="509fc-149">Kompensationsområden används för att ange medarbetarkompensation baserat på var arbetsplatsen ligger.</span><span class="sxs-lookup"><span data-stu-id="509fc-149">Compensation regions are used to specify employee compensation based on the location of the workplace.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="509fc-150">Kontrollpunkt</span><span class="sxs-lookup"><span data-stu-id="509fc-150">Control point</span></span></td>
<td><span data-ttu-id="509fc-151">Kontrollpunkten anger vad du anser vara den ideala lönesatsen för alla medarbetare på en viss kompensationsnivå.</span><span class="sxs-lookup"><span data-stu-id="509fc-151">The control point defines what you consider to be the ideal pay rate for all employees at a compensation level.</span></span> <span data-ttu-id="509fc-152">För gradplansstrukturer utgörs kontrollpunkterna vanligtvis av intervallernas mittpunkt.</span><span class="sxs-lookup"><span data-stu-id="509fc-152">For grade plan structures, control points are typically the midpoint of the ranges.</span></span> <span data-ttu-id="509fc-153">Bandstrukturer använder sällan kontrollpunkter.</span><span class="sxs-lookup"><span data-stu-id="509fc-153">Band structures rarely use control points.</span></span> <span data-ttu-id="509fc-154">Du kan ange kontrollpunkten för en fast kompensationsplan i formuläret Planer för fast kompensation.</span><span class="sxs-lookup"><span data-stu-id="509fc-154">You can specify the control point for a fixed compensation plan in the Fixed compensation plans form.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="509fc-155">Jobbfunktioner</span><span class="sxs-lookup"><span data-stu-id="509fc-155">Job functions</span></span></td>
<td><span data-ttu-id="509fc-156">Jobbfunktioner används för att klassificera och filtrera kompensationsplaner till specifika jobb.</span><span class="sxs-lookup"><span data-stu-id="509fc-156">Job functions are used to classify and filter compensation plans to specific jobs.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="509fc-157">Jobbtyper</span><span class="sxs-lookup"><span data-stu-id="509fc-157">Job types</span></span></td>
<td><span data-ttu-id="509fc-158">Jobbtyper används för att klassificera och filtrera kompensationsplaner till specifika jobb.</span><span class="sxs-lookup"><span data-stu-id="509fc-158">Job types are used to classify and filter compensation plans to specific jobs.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="509fc-159">Typer av variabel kompensation</span><span class="sxs-lookup"><span data-stu-id="509fc-159">Variable compensation types</span></span></td>
<td><span data-ttu-id="509fc-160">Variabla kompensationstyper, till exempel ersättning i aktier eller kontantbonusar, ställs in i variabla kompensationsplaner.</span><span class="sxs-lookup"><span data-stu-id="509fc-160">Variable compensation types, such as stock awards or cash award bonuses, are set up in variable compensation plans.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="509fc-161">Kompensationsrutnät</span><span class="sxs-lookup"><span data-stu-id="509fc-161">Compensation grids</span></span></td>
<td><span data-ttu-id="509fc-162">Kompensationsrutnät innehåller kompensationsstrukturen.</span><span class="sxs-lookup"><span data-stu-id="509fc-162">Compensation grids contain the compensation structure.</span></span>  <span data-ttu-id="509fc-163">Kompensationsrutnät kan användas av en eller flera kompensationsplaner.</span><span class="sxs-lookup"><span data-stu-id="509fc-163">Compensation grids can be used by one or more compensation plans.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="509fc-164">Resultatplaner</span><span class="sxs-lookup"><span data-stu-id="509fc-164">Performance plans</span></span></td>
<td><span data-ttu-id="509fc-165">Resultatplaner används för att associera resultat med en allokeringsmatris så att du kan använda planen i en resultatlönestrategi.</span><span class="sxs-lookup"><span data-stu-id="509fc-165">Performance plans are used to associate performance with an allocation matrix, so that you can use the plan in a pay-for-performance strategy.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="509fc-166">Resultatvärderingar</span><span class="sxs-lookup"><span data-stu-id="509fc-166">Performance ratings</span></span></td>
<td><span data-ttu-id="509fc-167">Resultatvärderingar används i resultatplaner när du vill fastställa beloppet för en meritbelöning eller resultatbelöning.</span><span class="sxs-lookup"><span data-stu-id="509fc-167">Performance ratings are used in performance plans to determine the amount of a merit award or performance award.</span></span></td>
</tr>
</tbody>
</table>

## <a name="process-events"></a><span data-ttu-id="509fc-168">Processhändelser</span><span class="sxs-lookup"><span data-stu-id="509fc-168">Process events</span></span>
<span data-ttu-id="509fc-169">En processhändelse beräknar kompensationsinformation för en angiven period för alla medarbetare som har anmälts till minst en fast eller variabel kompensationsplan.</span><span class="sxs-lookup"><span data-stu-id="509fc-169">A process event calculates compensation information for a specific period for all employees who are enrolled in one or more fixed or variable compensation plans.</span></span> <span data-ttu-id="509fc-170">Du kan köra en processhändelse flera gånger för att testa eller uppdatera beräknade kompensationsresultat.</span><span class="sxs-lookup"><span data-stu-id="509fc-170">You can run a process event repeatedly to test or update calculated compensation results.</span></span>

<a name="compensation-events"></a><span data-ttu-id="509fc-171">Kompensationshändelser</span><span class="sxs-lookup"><span data-stu-id="509fc-171">Compensation events</span></span>
-------------------

<span data-ttu-id="509fc-172">Varje gång en processhändelse körs skapas en kompensationshändelse.</span><span class="sxs-lookup"><span data-stu-id="509fc-172">Each time a process event is run, a compensation event is created.</span></span>  <span data-ttu-id="509fc-173">Händelser för medarbetarkompensation innehåller resultaten av kompensationsprocessen för varje anställd som omfattas av den processhändelsen.</span><span class="sxs-lookup"><span data-stu-id="509fc-173">Compensation events contain the results of the compensation process for each employee included in that process event.</span></span>  <span data-ttu-id="509fc-174">När beräkningarna är korrekta kan du ladda kompensationshändelsen för att uppdatera kompensationsposterna för de medarbetare som påverkas av processhändelsen.</span><span class="sxs-lookup"><span data-stu-id="509fc-174">When the calculations are correct, you can load the compensation event to update the compensation records for the employees who are affected by the process event.</span></span>

## <a name="recommendations"></a><span data-ttu-id="509fc-175"> Rekommendationer</span><span class="sxs-lookup"><span data-stu-id="509fc-175">Recommendations</span></span>
<span data-ttu-id="509fc-176">När du har kört en processhändelse kan du rekommendera justeringar av en medarbetares meritökning eller belöningsbelopp baserat på de beräknade riktlinjerna för processhändelsen.</span><span class="sxs-lookup"><span data-stu-id="509fc-176">After you run a process event, you can recommend adjustments to an employee’s merit increase or award amount, based on the calculated guidelines of the process event.</span></span> <span data-ttu-id="509fc-177">Om du vill göra rekommendationer för medarbetare måste du aktivera rekommendationer när du ställer in kompensationsplaner eller när du ställer in processhändelsen.</span><span class="sxs-lookup"><span data-stu-id="509fc-177">To make recommendations for employees, you must enable recommendations when you set up compensation plans or when you set up the process event.</span></span>



