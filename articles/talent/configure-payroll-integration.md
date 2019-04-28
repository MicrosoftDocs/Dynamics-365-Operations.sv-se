---
title: Konfigurera löneintegrering mellan Talent och Dayforce
description: Det här avsnittet förklarar hur du konfigurerar integrationen mellan Dynamics 365 for Talent och Ceridian Dayforce så att du kan bearbeta en betalning.
author: andreabichsel
manager: AnnBe
ms.date: 03/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 9a88bf61dbb12520b555ceb7363b1c646d95386e
ms.sourcegitcommit: 204e4554e409c39fbbf7b273ad138ce2809931a8
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/26/2019
ms.locfileid: "898454"
---
# <a name="configure-the-payroll-integration-between-talent-and-dayforce"></a><span data-ttu-id="24326-103">Konfigurera löneintegration mellan Talent och Dayforce</span><span class="sxs-lookup"><span data-stu-id="24326-103">Configure the payroll integration between Talent and Dayforce</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="24326-104">Integreringen mellan Microsoft Dynamics 365 for Talent och Ceridian Dayforce är beroende av flera konfigurationssteg som beskrivs i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="24326-104">The integration between Microsoft Dynamics 365 for Talent and Ceridian Dayforce relies on several configuration steps that are described in this topic.</span></span> <span data-ttu-id="24326-105">Du måste konfigurera integrationen i både Talent och Dayforce innan du kan bearbeta en betalning.</span><span class="sxs-lookup"><span data-stu-id="24326-105">You must configure the integration in both Talent and Dayforce before you can process a pay run.</span></span>

<span data-ttu-id="24326-106">När du använder tjänster som exempelvis Dayforce för att utföra betalningar måste du aktivera integration i Talent.</span><span class="sxs-lookup"><span data-stu-id="24326-106">When you use a service such as Dayforce to complete pay runs, you must enable the integration in Talent.</span></span> <span data-ttu-id="24326-107">Integrationen kräver specifika data från Talent.</span><span class="sxs-lookup"><span data-stu-id="24326-107">The integration requires specific data from Talent.</span></span> <span data-ttu-id="24326-108">Därför måste du kontrollera att data som är mappad till Dayforce konfigureras i Talent på ett sätt som stöder integrationen.</span><span class="sxs-lookup"><span data-stu-id="24326-108">Therefore, you must verify that data that is mapped to Dayforce is configured in Talent in a manner that supports the integration.</span></span> <span data-ttu-id="24326-109">Integrationen använder följande breda datakategorier:</span><span class="sxs-lookup"><span data-stu-id="24326-109">The integration uses the following broad categories of data:</span></span>

- <span data-ttu-id="24326-110">Personaldata</span><span class="sxs-lookup"><span data-stu-id="24326-110">Human resources data</span></span>
- <span data-ttu-id="24326-111">Kompensationsdata</span><span class="sxs-lookup"><span data-stu-id="24326-111">Compensation data</span></span>
- <span data-ttu-id="24326-112">Lönedata som till exempel lönecykler, betalningsperioder och inkomstkoder</span><span class="sxs-lookup"><span data-stu-id="24326-112">Payroll data, such as pay cycles, pay periods, and earning codes</span></span>
- <span data-ttu-id="24326-113">Medarbetardata</span><span class="sxs-lookup"><span data-stu-id="24326-113">Worker data</span></span>

<span data-ttu-id="24326-114">Det här avsnittet beskriver de steg som du måste följa för att aktivera integrationen.</span><span class="sxs-lookup"><span data-stu-id="24326-114">This topic describes the steps that you must follow to enable the integration.</span></span> <span data-ttu-id="24326-115">Här förklaras också de typer av data och den konfigurationsinformation som integrationen kräver.</span><span class="sxs-lookup"><span data-stu-id="24326-115">It also explains the types of data and the configuration details that the integration requires.</span></span>

## <a name="enable-the-integration"></a><span data-ttu-id="24326-116">Aktivera integrationen</span><span class="sxs-lookup"><span data-stu-id="24326-116">Enable the integration</span></span>

<span data-ttu-id="24326-117">Du måste aktivera integrationen i Talent och ange konfigurationsinformation för att ansluta till Dayforce.</span><span class="sxs-lookup"><span data-stu-id="24326-117">In Talent, you must turn on the integration and enter the configuration information to connect to Dayforce.</span></span> <span data-ttu-id="24326-118">Om du vill att den redovisningstransaktion som framställs ska importeras till Microsoft Dynamics 365 for Finance and Operations måste du också skapa ett lagringskonto för Microsoft Azure och ange anslutningssträngen för Azure-lagring i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="24326-118">If you want the general ledger transaction that is produced to be imported into Microsoft Dynamics 365 for Finance and Operations, you must also set up a Microsoft Azure storage account and enter the Azure Storage connection string in Finance and Operations.</span></span>

<span data-ttu-id="24326-119">Följ dessa steg om du vill aktivera integration i Talent.</span><span class="sxs-lookup"><span data-stu-id="24326-119">To turn on the integration in Talent, follow these steps.</span></span>

1. <span data-ttu-id="24326-120">På sidan **Systemadministration** väljer du **Integrationskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="24326-120">On the **System administration** page, select **Integration configuration**.</span></span>
2. <span data-ttu-id="24326-121">Ange slutpunkten för filöverföringsprotokollet (FTP) och den säkra FTP-sökvägen.</span><span class="sxs-lookup"><span data-stu-id="24326-121">Enter the secure File Transfer Protocol (FTP) endpoint and the secure FTP folder path.</span></span>
3. <span data-ttu-id="24326-122">Ange användarnamn och lösenord för den användare som kommer att använda den säkra FTP-slutpunkten och mappsökvägen.</span><span class="sxs-lookup"><span data-stu-id="24326-122">Enter the user name and password of the user who will access the secure FTP endpoint and folder path.</span></span>
4. <span data-ttu-id="24326-123">Testa anslutningen efter behov samt ange alternativet **Aktivera integrering av löner** som **Ja**.</span><span class="sxs-lookup"><span data-stu-id="24326-123">Test the connection, as required, and set the **Enable payroll integration** option to **Yes**.</span></span>

<span data-ttu-id="24326-124">När integreringen aktiveras skapas dataexportpaket och filer, och frekvensen anges.</span><span class="sxs-lookup"><span data-stu-id="24326-124">When the integration is turned on, the data export package and files are created, and the frequency is set.</span></span> <span data-ttu-id="24326-125">Du kan ändra frekvensen efter behov.</span><span class="sxs-lookup"><span data-stu-id="24326-125">You can change this frequency as you require.</span></span>

<span data-ttu-id="24326-126">Mer information om Azure-lagringskonton och anslutningssträngar för Azure-lagring, se följande Azure-avsnitt:</span><span class="sxs-lookup"><span data-stu-id="24326-126">For more information about Azure storage accounts and Azure Storage connection strings, see the following Azure topics:</span></span>

- [<span data-ttu-id="24326-127">Om Azure-lagringskonton</span><span class="sxs-lookup"><span data-stu-id="24326-127">About Azure storage accounts</span></span>](https://docs.microsoft.com/en-us/azure/storage/common/storage-create-storage-account?toc=%2fazure%2fstorage%2ffiles%2ftoc.json)
- [<span data-ttu-id="24326-128">Konfigurera anslutningssträngar för Azure-lagring</span><span class="sxs-lookup"><span data-stu-id="24326-128">Configure Azure Storage connection strings</span></span>](https://docs.microsoft.com/en-us/azure/storage/common/storage-configure-connection-string)

## <a name="configure-your-data"></a><span data-ttu-id="24326-129">Konfigurera dina data</span><span class="sxs-lookup"><span data-stu-id="24326-129">Configure your data</span></span> 

<span data-ttu-id="24326-130">Du måste konfigurera personaldata för att bearbeta löner i Talent.</span><span class="sxs-lookup"><span data-stu-id="24326-130">To process payroll, you must configure human resource data in Talent.</span></span> <span data-ttu-id="24326-131">Du måste ställa in organisationsinformation, t.ex. jobb och befattningar samt förmåner och kompensationsinformation.</span><span class="sxs-lookup"><span data-stu-id="24326-131">You must set up organizational data, such as jobs and positions, together with benefits and compensation information.</span></span> <span data-ttu-id="24326-132">Denna information utgör den anställnings-, lön- och avdragsinformationen som krävs för att generera lön för medarbetare.</span><span class="sxs-lookup"><span data-stu-id="24326-132">This information provides the employment, pay, and deduction information that is required in order to generate employee pay.</span></span>

### <a name="human-resource-data"></a><span data-ttu-id="24326-133">Personaldata</span><span class="sxs-lookup"><span data-stu-id="24326-133">Human resource data</span></span>

#### <a name="benefits"></a><span data-ttu-id="24326-134">Förmåner</span><span class="sxs-lookup"><span data-stu-id="24326-134">Benefits</span></span> 

<span data-ttu-id="24326-135">Personal tillhandahåller verktyg som kan användas för att ställa in och underhålla förmåner, avdrag och kompensationsplaner för medarbetare som en organisation erbjuder eller bearbetar för sin personal.</span><span class="sxs-lookup"><span data-stu-id="24326-135">Human resources provides tools for the setup and maintenance of the benefits, deductions, and worker compensation plans that an organization offers or processes for its workers.</span></span>

<span data-ttu-id="24326-136">När du skapar förmåner, kom då ihåg följande data och konfigurationer som används i Dayforce.</span><span class="sxs-lookup"><span data-stu-id="24326-136">When you create benefits, keep in mind the following data and configurations that are used in Dayforce.</span></span>

##### <a name="benefit-plans"></a><span data-ttu-id="24326-137">Förmånsplaner</span><span class="sxs-lookup"><span data-stu-id="24326-137">Benefit plans</span></span>

- <span data-ttu-id="24326-138">Plan (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="24326-138">Plan (required)</span></span>
- <span data-ttu-id="24326-139">Typ (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="24326-139">Type (required)</span></span>
- <span data-ttu-id="24326-140">Effekt på lön (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="24326-140">Payroll impact (required)</span></span>
- <span data-ttu-id="24326-141">Återvinn restbetalningar</span><span class="sxs-lookup"><span data-stu-id="24326-141">Recover arrears</span></span>
- <span data-ttu-id="24326-142">Avdragsmetod</span><span class="sxs-lookup"><span data-stu-id="24326-142">Deduction method</span></span>
- <span data-ttu-id="24326-143">Avdragsprioritet</span><span class="sxs-lookup"><span data-stu-id="24326-143">Deduction priority</span></span>
- <span data-ttu-id="24326-144">Gränsperiod</span><span class="sxs-lookup"><span data-stu-id="24326-144">Limit period</span></span>
- <span data-ttu-id="24326-145">Begränsa belopp</span><span class="sxs-lookup"><span data-stu-id="24326-145">Limit amount</span></span>

##### <a name="benefits"></a><span data-ttu-id="24326-146">Förmåner</span><span class="sxs-lookup"><span data-stu-id="24326-146">Benefits</span></span>

- <span data-ttu-id="24326-147">Plan (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="24326-147">Plan (required)</span></span>
- <span data-ttu-id="24326-148">Typ (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="24326-148">Type (required)</span></span>
- <span data-ttu-id="24326-149">Tillval (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="24326-149">Option (required)</span></span>
- <span data-ttu-id="24326-150">Förmåns-ID (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="24326-150">Benefit ID (required)</span></span>
- <span data-ttu-id="24326-151">Frekvens</span><span class="sxs-lookup"><span data-stu-id="24326-151">Frequency</span></span>
- <span data-ttu-id="24326-152">Bas</span><span class="sxs-lookup"><span data-stu-id="24326-152">Basis</span></span>
- <span data-ttu-id="24326-153">Belopp eller tariff</span><span class="sxs-lookup"><span data-stu-id="24326-153">Amount or rate</span></span>
- <span data-ttu-id="24326-154">Inkomstkod</span><span class="sxs-lookup"><span data-stu-id="24326-154">Earning code</span></span>

##### <a name="supported-frequencies"></a><span data-ttu-id="24326-155">Frekvenser som stöds</span><span class="sxs-lookup"><span data-stu-id="24326-155">Supported frequencies</span></span> 

- <span data-ttu-id="24326-156">Varje vecka</span><span class="sxs-lookup"><span data-stu-id="24326-156">Weekly</span></span>
- <span data-ttu-id="24326-157">Varannan vecka</span><span class="sxs-lookup"><span data-stu-id="24326-157">Bi-weekly</span></span>
- <span data-ttu-id="24326-158">Var fjortonde dag</span><span class="sxs-lookup"><span data-stu-id="24326-158">Semi-monthly</span></span>
- <span data-ttu-id="24326-159">Månatlig</span><span class="sxs-lookup"><span data-stu-id="24326-159">Monthly</span></span>

##### <a name="supported-bases"></a><span data-ttu-id="24326-160">Databaser som stöds</span><span class="sxs-lookup"><span data-stu-id="24326-160">Supported bases</span></span> 

- <span data-ttu-id="24326-161">Fast belopp</span><span class="sxs-lookup"><span data-stu-id="24326-161">Fixed amount</span></span>
- <span data-ttu-id="24326-162">Procent av inkomst</span><span class="sxs-lookup"><span data-stu-id="24326-162">Percent of earnings</span></span>
- <span data-ttu-id="24326-163">Produktiva timmar</span><span class="sxs-lookup"><span data-stu-id="24326-163">Productive hours</span></span>

<span data-ttu-id="24326-164">Dayforce skapar följande avdrag baserat på den löneeffekt som definieras i förmånsplanen.</span><span class="sxs-lookup"><span data-stu-id="24326-164">Dayforce creates the following deductions, based on the payroll impact that is defined on the benefit plan.</span></span>

| <span data-ttu-id="24326-165">Val i Talent</span><span class="sxs-lookup"><span data-stu-id="24326-165">Selection in Talent</span></span>        | <span data-ttu-id="24326-166">Resultat i Dayforce</span><span class="sxs-lookup"><span data-stu-id="24326-166">Result in Dayforce</span></span>                            |
|----------------------------|-----------------------------------------------|
| <span data-ttu-id="24326-167">Inga</span><span class="sxs-lookup"><span data-stu-id="24326-167">None</span></span>                       | <span data-ttu-id="24326-168">Inget avdrag skapas.</span><span class="sxs-lookup"><span data-stu-id="24326-168">No deduction is created.</span></span>                      |
| <span data-ttu-id="24326-169">Endast avdrag</span><span class="sxs-lookup"><span data-stu-id="24326-169">Deduction only</span></span>             | <span data-ttu-id="24326-170">Löneavdrag för en medarbetare skapas.</span><span class="sxs-lookup"><span data-stu-id="24326-170">An employee deduction is created.</span></span>             |
| <span data-ttu-id="24326-171">Endast lönetillägg</span><span class="sxs-lookup"><span data-stu-id="24326-171">Contribution only</span></span>          | <span data-ttu-id="24326-172">Löneavdrag för en arbetsgivare skapas.</span><span class="sxs-lookup"><span data-stu-id="24326-172">An employer deduction is created.</span></span>             |
| <span data-ttu-id="24326-173">Avdrag och tillägg</span><span class="sxs-lookup"><span data-stu-id="24326-173">Deduction and contribution</span></span> | <span data-ttu-id="24326-174">Avdrag för medarbetare och arbetsgivare skapas.</span><span class="sxs-lookup"><span data-stu-id="24326-174">Employee and employer deductions are created.</span></span> |

<span data-ttu-id="24326-175">Mer information om hur du definierar och hanterar ett förmånsprogram finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="24326-175">For more information about how to define and manage a benefits program, see the following topics:</span></span>

- [<span data-ttu-id="24326-176">Utveckla ett förmånsprogram för medarbetare</span><span class="sxs-lookup"><span data-stu-id="24326-176">Deliver an employee benefits program</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/deliver-employee-benefits-program)
- [<span data-ttu-id="24326-177">Skapa en ny förmån</span><span class="sxs-lookup"><span data-stu-id="24326-177">Create a new benefit</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/create-new-benefit)
- [<span data-ttu-id="24326-178">Definiera förmånsberättiganderegler och policyer</span><span class="sxs-lookup"><span data-stu-id="24326-178">Define benefit eligibility rules and policies</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-benefit-eligibility-rules-policies)
- [<span data-ttu-id="24326-179">Registrera och ta bort förmåner för arbetare</span><span class="sxs-lookup"><span data-stu-id="24326-179">Enroll and remove benefits from workers</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-remove-benefits-workers)

#### <a name="compensation"></a><span data-ttu-id="24326-180">Kompensation</span><span class="sxs-lookup"><span data-stu-id="24326-180">Compensation</span></span> 

<span data-ttu-id="24326-181">Kompensationshantering används för att styra du utbetalningen av grundlön och belöningar.</span><span class="sxs-lookup"><span data-stu-id="24326-181">Compensation management is used to control the delivery of base pay and awards.</span></span> <span data-ttu-id="24326-182">En medarbetares fasta grundlön och merithöjningar kontrolleras genom fasta kompensationsplaner.</span><span class="sxs-lookup"><span data-stu-id="24326-182">An employee's fixed base pay and merit increases are controlled through fixed compensation plans.</span></span> <span data-ttu-id="24326-183">Betalningen av incitament, till exempel bonusar, resultatbelöningar, aktieoptioner och anslag och även engångsbelöningar kontrolleras genom variabla kompensationsplaner.</span><span class="sxs-lookup"><span data-stu-id="24326-183">The payment of incentive pay, such as bonus payments, performance awards, stock options, and grants, and also one-time awards, are controlled through variable compensation plans.</span></span>

<span data-ttu-id="24326-184">Dayforce använder kompensationsinformation för att beräkna en medarbetares tim- eller årliga betalning.</span><span class="sxs-lookup"><span data-stu-id="24326-184">Dayforce uses compensation information to calculate an employee's hourly or annual rate.</span></span> <span data-ttu-id="24326-185">Fasta kompensationsplaner och lönekonverteringar är obligatoriska.</span><span class="sxs-lookup"><span data-stu-id="24326-185">Fixed compensation plans and pay rate conversions are required.</span></span> <span data-ttu-id="24326-186">Medarbetarna måste vara anslutna till en fast kompensationsplan.</span><span class="sxs-lookup"><span data-stu-id="24326-186">Employees must be associated with a fixed compensation plan.</span></span>

<span data-ttu-id="24326-187">Mer information om att kompensationsplaner finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="24326-187">For more information about compensation plans, see the following topics:</span></span>

- [<span data-ttu-id="24326-188">Skapa planer för fast kompensation</span><span class="sxs-lookup"><span data-stu-id="24326-188">Create fixed compensation plans</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/create-fixed-compensation-plans)
- [<span data-ttu-id="24326-189">Skapa planer för variabel kompensation</span><span class="sxs-lookup"><span data-stu-id="24326-189">Create variable compensation plans</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/create-variable-compensation-plans)
- [<span data-ttu-id="24326-190">Utveckla struktur och planer för lön/kompensation</span><span class="sxs-lookup"><span data-stu-id="24326-190">Develop salary/compensation structure and plans</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/develop-salary-compensation-structure-plan)
- [<span data-ttu-id="24326-191">Bearbeta kompensation</span><span class="sxs-lookup"><span data-stu-id="24326-191">Process compensation</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/process-compensation)
- [<span data-ttu-id="24326-192">Definiera kompensationsprocessen och beräkna resultat</span><span class="sxs-lookup"><span data-stu-id="24326-192">Define compensation process and calculate results</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-compensation-process-calculate-results)
- [<span data-ttu-id="24326-193">Registrera en medarbetare i en fast kompensationsplan</span><span class="sxs-lookup"><span data-stu-id="24326-193">Enroll an employee in a fixed compensation plan</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-fixed-compensation-plan)
- [<span data-ttu-id="24326-194">Registrera en medarbetare i en variabel kompensationsplan</span><span class="sxs-lookup"><span data-stu-id="24326-194">Enroll an employee in a variable compensation plan</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-variable-compensation-plan)

#### <a name="jobs"></a><span data-ttu-id="24326-195">Jobb</span><span class="sxs-lookup"><span data-stu-id="24326-195">Jobs</span></span> 

<span data-ttu-id="24326-196">Ett jobb är den samling uppgifter och ansvarsområden som avkrävs en person som utför ett jobb.</span><span class="sxs-lookup"><span data-stu-id="24326-196">A job is a collection of the tasks and responsibilities that are required of a person who performs a job.</span></span> <span data-ttu-id="24326-197">Mer information finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="24326-197">For more information, see the following topics:</span></span>

- [<span data-ttu-id="24326-198">Installera komponenter för ett jobb</span><span class="sxs-lookup"><span data-stu-id="24326-198">Setting up the components of a job</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/create-job)
- [<span data-ttu-id="24326-199">Definiera nya jobb</span><span class="sxs-lookup"><span data-stu-id="24326-199">Define new jobs</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-jobs)

##### <a name="positions"></a><span data-ttu-id="24326-200">Befattningar</span><span class="sxs-lookup"><span data-stu-id="24326-200">Positions</span></span>

<span data-ttu-id="24326-201">En befattning är ett exempel på ett enskilt jobb.</span><span class="sxs-lookup"><span data-stu-id="24326-201">A position is an individual instance of a job.</span></span> <span data-ttu-id="24326-202">Befattningen "Försäljningschef (öst)" är exempelvis en av de befattningar som associeras med jobbet "Försäljningschef."</span><span class="sxs-lookup"><span data-stu-id="24326-202">For example, the "Sales manager (East)" position is one of the positions that are associated with the "Sales manager" job.</span></span> <span data-ttu-id="24326-203">En befattning finns på en avdelning.</span><span class="sxs-lookup"><span data-stu-id="24326-203">A position exists in a department.</span></span> <span data-ttu-id="24326-204">Endast en enda medarbetare kan vara associerad med respektive befattning.</span><span class="sxs-lookup"><span data-stu-id="24326-204">Only one worker can be associated with each position.</span></span>

<span data-ttu-id="24326-205">Tänk på följande uppgifter och konfigurationsinformation när du ställer in befattningar:</span><span class="sxs-lookup"><span data-stu-id="24326-205">Keep the following data and configuration in mind when you set up positions:</span></span>

- <span data-ttu-id="24326-206">Befattning (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="24326-206">Position (required)</span></span>
- <span data-ttu-id="24326-207">Beskrivning (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="24326-207">Description (required)</span></span>
- <span data-ttu-id="24326-208">Jobb (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="24326-208">Job (required)</span></span>
- <span data-ttu-id="24326-209">Avdelning (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="24326-209">Department (required)</span></span>
- <span data-ttu-id="24326-210">Befattningstyp (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="24326-210">Position type (required)</span></span>
- <span data-ttu-id="24326-211">Heltidslön</span><span class="sxs-lookup"><span data-stu-id="24326-211">Full-time equivalent</span></span>
- <span data-ttu-id="24326-212">Ordinarie timmar per år (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="24326-212">Annual regular hours (required)</span></span>
- <span data-ttu-id="24326-213">Betalas av den juridiska personen (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="24326-213">Paid by legal entity (required)</span></span>
- <span data-ttu-id="24326-214">Lönecykel (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="24326-214">Pay cycle (required)</span></span>
- <span data-ttu-id="24326-215">Standardekonomisk dimension – kostnadsställe (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="24326-215">Default financial dimension – Cost center (required)</span></span>
- <span data-ttu-id="24326-216">Medarbetartilldelning – medarbetare, tilldelningsstart, tilldelningsslut, orsakskod</span><span class="sxs-lookup"><span data-stu-id="24326-216">Worker assignment – Worker, assignment start, assignment end, reason code</span></span>

<span data-ttu-id="24326-217">Om flera befattningar på samma avdelning är associerade med samma jobb konsolideras de till en enda befattning i Dayforce.</span><span class="sxs-lookup"><span data-stu-id="24326-217">If multiple positions in the same department are associated with the same job, they are consolidated into a single position in Dayforce.</span></span>

<span data-ttu-id="24326-218">Mer information finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="24326-218">For more information, see the following topics:</span></span>

- [<span data-ttu-id="24326-219">Organisera arbetsstyrkan med avdelningar, jobb och befattningar</span><span class="sxs-lookup"><span data-stu-id="24326-219">Organize your workforce using departments, jobs, and positions</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/departments-jobs-positions#positions)
- [<span data-ttu-id="24326-220">Ställ in befattningar</span><span class="sxs-lookup"><span data-stu-id="24326-220">Set up positions</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/set-up-positions)

#### <a name="departments"></a><span data-ttu-id="24326-221">Avdelningar</span><span class="sxs-lookup"><span data-stu-id="24326-221">Departments</span></span>

<span data-ttu-id="24326-222">En avdelning är en driftenhet som representerar en kategori eller verksamhetsområde inom en organisation.</span><span class="sxs-lookup"><span data-stu-id="24326-222">A department is an operating unit that represents a category or functional area of an organization.</span></span> <span data-ttu-id="24326-223">En avdelning är ansvarig för en viss del av organisationen, såsom försäljning, bokföring eller mänskliga resurser.</span><span class="sxs-lookup"><span data-stu-id="24326-223">A department is responsible for a specific area of the organization, such as sales, accounting, or human resources.</span></span> <span data-ttu-id="24326-224">Du kan använda avdelningar att rapportera om funktionella områden.</span><span class="sxs-lookup"><span data-stu-id="24326-224">You can use departments to report on functional areas.</span></span> <span data-ttu-id="24326-225">Avdelningar kan ha vinst och förlust.</span><span class="sxs-lookup"><span data-stu-id="24326-225">Departments might have profit and loss responsibility.</span></span>

<span data-ttu-id="24326-226">Mer information finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="24326-226">For more information, see the following topics:</span></span>

- [<span data-ttu-id="24326-227">Skapa en avdelning och associera den med avdelningshierarkin</span><span class="sxs-lookup"><span data-stu-id="24326-227">Create a department and associate it with the department hierarchy</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/create-department-add-department-hierarchy)
- [<span data-ttu-id="24326-228">Definiera nya avdelningar</span><span class="sxs-lookup"><span data-stu-id="24326-228">Define new departments</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-departments)

#### <a name="pay-cycles-and-pay-periods"></a><span data-ttu-id="24326-229">Lönecykler och löneperioder</span><span class="sxs-lookup"><span data-stu-id="24326-229">Pay cycles and pay periods</span></span>

<span data-ttu-id="24326-230">En lönecykel avgör hur ofta lönelistan körs, samt vilka specifika dagar som medarbetarna får betalt.</span><span class="sxs-lookup"><span data-stu-id="24326-230">A pay cycle determines how often payroll is run and the specific days when workers are paid.</span></span> <span data-ttu-id="24326-231">En lönecykel kan exempelvis vara månadsvis och medarbetarna få sin lön den sista dagen i månaden.</span><span class="sxs-lookup"><span data-stu-id="24326-231">For example, a pay cycle might be monthly, and employees might be paid on the last day of the month.</span></span> <span data-ttu-id="24326-232">Alternativt kan en lönecykel vara veckovis och medarbetarna få sin lön på tisdagen efter betalningsperiodens utgång.</span><span class="sxs-lookup"><span data-stu-id="24326-232">Alternatively, a pay cycle might be weekly, and employees might be paid on the Tuesday after the end of the pay period.</span></span> <span data-ttu-id="24326-233">Lönecykler tilldelas befattningar i syfte att styra när arbetare på dessa befattningar får sin lön.</span><span class="sxs-lookup"><span data-stu-id="24326-233">Pay cycles are assigned to positions to control when workers in those positions are paid.</span></span>

<span data-ttu-id="24326-234">När du har skapat lönecykler kan du generera betalningsperioder för respektive cykel.</span><span class="sxs-lookup"><span data-stu-id="24326-234">After you create pay cycles, you can generate pay periods for each cycle.</span></span> <span data-ttu-id="24326-235">Varje betalningsperiod innehåller ett standardbetalningsdatum som baseras på den information du anger.</span><span class="sxs-lookup"><span data-stu-id="24326-235">Each pay period includes a default payment date that is based on information that you provide.</span></span> <span data-ttu-id="24326-236">Du kan emellertid ändra standarddatumet för betalning i en löneperiod i syfte att tillåta undantag, till exempel när betalningsdatumet infaller på en allmän helgdag.</span><span class="sxs-lookup"><span data-stu-id="24326-236">However, you can modify the default payment date in a pay period to allow for exceptions, such as when the payment date falls on a holiday.</span></span>

<span data-ttu-id="24326-237">Följande information används i Dayforce:</span><span class="sxs-lookup"><span data-stu-id="24326-237">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="24326-238">Lönecykel (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="24326-238">Pay cycle (required)</span></span>
- <span data-ttu-id="24326-239">Lönecykelfrekvens (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="24326-239">Pay cycle frequency (required)</span></span>
- <span data-ttu-id="24326-240">Periodens startdatum (första löneperiod obligatorisk)</span><span class="sxs-lookup"><span data-stu-id="24326-240">Period start date (first pay period required)</span></span>
- <span data-ttu-id="24326-241">Standarddatum för betalning (första löneperiod obligatorisk)</span><span class="sxs-lookup"><span data-stu-id="24326-241">Default payment date (first pay period required)</span></span>

<span data-ttu-id="24326-242">Denna information är integrerad i Dayforce som lönegrupper och delas upp efter land eller region för respektive lönecykel.</span><span class="sxs-lookup"><span data-stu-id="24326-242">This information is integrated with Dayforce as pay groups, and is separated by country or region for each pay cycle.</span></span> <span data-ttu-id="24326-243">Minst en löneperiod måste genereras före integration.</span><span class="sxs-lookup"><span data-stu-id="24326-243">At least one pay period must be generated before integration.</span></span> <span data-ttu-id="24326-244">Dayforce genererar gruppkalendrar för lön och betalningsdatum utifrån startdatumet för den första löneperioden och det standarddatum för betalning som anges i Talent.</span><span class="sxs-lookup"><span data-stu-id="24326-244">Dayforce generates pay group calendars and payment dates, based on the start date of the first pay period and the default payment date that is set up in Talent.</span></span>

#### <a name="earning-codes"></a><span data-ttu-id="24326-245">Inkomstkoder</span><span class="sxs-lookup"><span data-stu-id="24326-245">Earning codes</span></span>

<span data-ttu-id="24326-246">Inkomstkoder identifierar individuellt alla typer av arbetstagarintäkter.</span><span class="sxs-lookup"><span data-stu-id="24326-246">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="24326-247">Koderna har olika parametrar som rör inkomster, till exempel redovisningsbestämmelser, skattelagar, rapporteringskrav, och gross up-kapacitet.</span><span class="sxs-lookup"><span data-stu-id="24326-247">The codes have various parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span>

<span data-ttu-id="24326-248">Följande information används i Dayforce:</span><span class="sxs-lookup"><span data-stu-id="24326-248">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="24326-249">Inkomstkod (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="24326-249">Earning Code (required)</span></span>
- <span data-ttu-id="24326-250">beskrivning</span><span class="sxs-lookup"><span data-stu-id="24326-250">Description</span></span>
- <span data-ttu-id="24326-251">Enhet</span><span class="sxs-lookup"><span data-stu-id="24326-251">Unit of measure</span></span>
- <span data-ttu-id="24326-252">Produktiv</span><span class="sxs-lookup"><span data-stu-id="24326-252">Productive</span></span>

### <a name="worker-data"></a><span data-ttu-id="24326-253">Medarbetardata</span><span class="sxs-lookup"><span data-stu-id="24326-253">Worker data</span></span>

<span data-ttu-id="24326-254">Poster för de olika typer av medarbetare som du har är viktiga för dina personal- och lönesystem.</span><span class="sxs-lookup"><span data-stu-id="24326-254">Records for the various types of workers that you have are important to your human resources and payroll systems.</span></span> <span data-ttu-id="24326-255">Den information du anger kan användas för att spåra medarbetare och personuppgifter.</span><span class="sxs-lookup"><span data-stu-id="24326-255">The information that you enter can be used to track workers and personal information.</span></span>

<span data-ttu-id="24326-256">För medarbetare kan du behålla följande information:</span><span class="sxs-lookup"><span data-stu-id="24326-256">You can maintain the following information for workers:</span></span>

- <span data-ttu-id="24326-257">**Grundläggande** – Grundläggande information om en medarbetare, till exempel kontaktinformation, demografisk information, identifikationsinformation, familjeinformation, status för militärtjänst, exilstatusinformation samt personliga och nödkontakter.</span><span class="sxs-lookup"><span data-stu-id="24326-257">**Basic** – Maintain basic information about a worker, such as contact information, demographic information, identification information, family information, military service status, expatriate information, and personal and emergency contacts.</span></span>
- <span data-ttu-id="24326-258">**Anställning** – Information om en medarbetares anställning, exempelvis företags- eller organisationstillhörighet, befattningstilldelning, start- och slutdatum, jobbtillgänglighet, anställningsvillkor, pension, semester- samt omplaceringsinformation.</span><span class="sxs-lookup"><span data-stu-id="24326-258">**Employment** – Maintain information about a worker's employment, such as company or organization affiliation, position assignment, start and end dates, work eligibility, terms of employment, pension, vacation, and relocation information.</span></span>
- <span data-ttu-id="24326-259">**Tjänstledighet och frånvaro** – Information om en medarbetares frånvaro, exempelvis jobbkalendrar, frånvarotransaktioner samt frånvaroinställningar.</span><span class="sxs-lookup"><span data-stu-id="24326-259">**Leave and absence** – Maintain information about a worker's absences, such as working calendars, absence transactions, and absence setup.</span></span>
- <span data-ttu-id="24326-260">**Ersättning och lön** – Information om en medarbetares ersättningsplaner och löneinformation, exempelvis plananmälan, utmärkelser, resultat, provision, skatteinformation, pensionering samt löneavdrag.</span><span class="sxs-lookup"><span data-stu-id="24326-260">**Compensation and payroll** – Maintain information about a worker's compensation plans and payroll information, such as plan enrollment, awards, performance, commission, tax information, retirement, and salary deductions.</span></span>

<span data-ttu-id="24326-261">När du anger medarbetarinformation, kom då ihåg följande uppgifter och konfigurationer som används i Dayforce.</span><span class="sxs-lookup"><span data-stu-id="24326-261">When you enter worker information, keep in mind the following data and configurations that are used in Dayforce.</span></span>

#### <a name="general-information"></a><span data-ttu-id="24326-262">Allmän information</span><span class="sxs-lookup"><span data-stu-id="24326-262">General information</span></span>

- <span data-ttu-id="24326-263">Anställningsnummer (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="24326-263">Personnel number (required)</span></span>
- <span data-ttu-id="24326-264">Förnamn (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="24326-264">First name (required)</span></span>
- <span data-ttu-id="24326-265">Efternamn (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="24326-265">Last name (required)</span></span>
- <span data-ttu-id="24326-266">Mellannamn</span><span class="sxs-lookup"><span data-stu-id="24326-266">Middle name</span></span>
- <span data-ttu-id="24326-267">Datum för tjänsteålder</span><span class="sxs-lookup"><span data-stu-id="24326-267">Seniority date</span></span>
- <span data-ttu-id="24326-268">Känt som</span><span class="sxs-lookup"><span data-stu-id="24326-268">Known as</span></span>

#### <a name="personal-information"></a><span data-ttu-id="24326-269">Personlig information</span><span class="sxs-lookup"><span data-stu-id="24326-269">Personal information</span></span>

- <span data-ttu-id="24326-270">Civilstånd (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="24326-270">Marital status (required)</span></span>
- <span data-ttu-id="24326-271">Födelsedatum (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="24326-271">Birth date (required)</span></span>
- <span data-ttu-id="24326-272">Könstillhörighet (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="24326-272">Gender (required)</span></span>
- <span data-ttu-id="24326-273">Person med funktionsnedsättningar</span><span class="sxs-lookup"><span data-stu-id="24326-273">Person with disabilities</span></span>
- <span data-ttu-id="24326-274">Medborgarskap, land, region (endast för Mexiko)</span><span class="sxs-lookup"><span data-stu-id="24326-274">Nationality country region (only for Mexico)</span></span>

#### <a name="address-information"></a><span data-ttu-id="24326-275">Adressinformation</span><span class="sxs-lookup"><span data-stu-id="24326-275">Address information</span></span>

- <span data-ttu-id="24326-276">Primär adress (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="24326-276">Primary (required)</span></span>
- <span data-ttu-id="24326-277">Land/region (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="24326-277">Country/region (required)</span></span>
- <span data-ttu-id="24326-278">Postnummer (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="24326-278">Postal code (required)</span></span>
- <span data-ttu-id="24326-279">Nummer (obligatoriskt) (endast för Mexiko)</span><span class="sxs-lookup"><span data-stu-id="24326-279">Street Number (required) (Only for Mexico)</span></span>
- <span data-ttu-id="24326-280">Byggnadskomplement (endast för Mexiko)</span><span class="sxs-lookup"><span data-stu-id="24326-280">Building Complement (Only for Mexico)</span></span>
- <span data-ttu-id="24326-281">Stad (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="24326-281">City (required)</span></span>
- <span data-ttu-id="24326-282">Delstat (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="24326-282">State (required)</span></span>
- <span data-ttu-id="24326-283">Region (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="24326-283">County (required)</span></span>

#### <a name="contact-information"></a><span data-ttu-id="24326-284">Kontaktinformation</span><span class="sxs-lookup"><span data-stu-id="24326-284">Contact information</span></span> 

- <span data-ttu-id="24326-285">Primär adress (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="24326-285">Primary (required)</span></span>
- <span data-ttu-id="24326-286">Kontaktnummer (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="24326-286">Contact number (required)</span></span>
- <span data-ttu-id="24326-287">Anknytning</span><span class="sxs-lookup"><span data-stu-id="24326-287">Extension</span></span>

#### <a name="payroll-information-and-earning-codes"></a><span data-ttu-id="24326-288">Löneinformation och inkomstkoder</span><span class="sxs-lookup"><span data-stu-id="24326-288">Payroll information and earning codes</span></span>

<span data-ttu-id="24326-289">Medarbetare kan tilldelas en viss inkomst till en viss betalningsfrekvens och ha en prioriterad betalningsmetod.</span><span class="sxs-lookup"><span data-stu-id="24326-289">Employees may be assigned specific earnings at a given frequency of payment and have a preferred payment method.</span></span> <span data-ttu-id="24326-290">Följande fält används i Dayforce för att garantera att dessa prioriteringar och inställningar används.</span><span class="sxs-lookup"><span data-stu-id="24326-290">The following fields are used in Dayforce to help guarantee that those preferences and settings are used.</span></span>

##### <a name="earning-codes"></a><span data-ttu-id="24326-291">Inkomstkoder</span><span class="sxs-lookup"><span data-stu-id="24326-291">Earning codes</span></span>

- <span data-ttu-id="24326-292">Befattning (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="24326-292">Position (required)</span></span>
- <span data-ttu-id="24326-293">Inkomstkod (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="24326-293">Earning Code (required)</span></span>
- <span data-ttu-id="24326-294">Frekvens (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="24326-294">Frequency (required)</span></span>
- <span data-ttu-id="24326-295">Belopp (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="24326-295">Amount (required)</span></span>

##### <a name="payroll-information"></a><span data-ttu-id="24326-296">Löneinformation</span><span class="sxs-lookup"><span data-stu-id="24326-296">Payroll information</span></span>

- <span data-ttu-id="24326-297">Betalningsmetod</span><span class="sxs-lookup"><span data-stu-id="24326-297">Payment Method</span></span>
- <span data-ttu-id="24326-298">Ekonomisk region (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="24326-298">Economic Region (required)</span></span>
- <span data-ttu-id="24326-299">ID för anställningsförmåner</span><span class="sxs-lookup"><span data-stu-id="24326-299">Employee Benefits ID</span></span>
- <span data-ttu-id="24326-300">Nationellt ID-nummer (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="24326-300">National ID Number (required)</span></span>
- <span data-ttu-id="24326-301">Militärtjänstgöring, nummer</span><span class="sxs-lookup"><span data-stu-id="24326-301">Military Service Number</span></span>
- <span data-ttu-id="24326-302">Skiftes-ID (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="24326-302">Shift ID (required)</span></span>
- <span data-ttu-id="24326-303">Skattenummer (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="24326-303">Tax Number (required)</span></span>
- <span data-ttu-id="24326-304">Fack-ID (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="24326-304">Union ID (required)</span></span>
- <span data-ttu-id="24326-305">Arbetsdags-ID (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="24326-305">Work Day ID (required)</span></span>
- <span data-ttu-id="24326-306">Arbetstillståndsnummer</span><span class="sxs-lookup"><span data-stu-id="24326-306">Work Permit Number</span></span>

> [!NOTE]
> <span data-ttu-id="24326-307">För betalningsmetoden stöder Mexiko **Kontant**, **Check** (företagets fysiska check), samt **Elektronisk betalning**.</span><span class="sxs-lookup"><span data-stu-id="24326-307">For the payment method, Mexico supports **Cash**, **Check** (the company's physical check), and **Electronic Payment**.</span></span> <span data-ttu-id="24326-308">Om betalningsmetoden np anges används **Check** som standard.</span><span class="sxs-lookup"><span data-stu-id="24326-308">If np payment method is specified, **Check** is used by default.</span></span>

#### <a name="employment-details"></a><span data-ttu-id="24326-309">Anställningsinformation</span><span class="sxs-lookup"><span data-stu-id="24326-309">Employment details</span></span>

<span data-ttu-id="24326-310">Detaljerad anställningshistorik används som viktig information i syfte att hämta en medarbetares anställnings-, uppsägnings- och återanställningsstatus i Dayforce.</span><span class="sxs-lookup"><span data-stu-id="24326-310">Employment detail history is used as key information to derive an employee's hire, termination, and rehire statuses in Dayforce.</span></span> <span data-ttu-id="24326-311">Dayforce stöder endast en aktiv anställningspost åt gången.</span><span class="sxs-lookup"><span data-stu-id="24326-311">Dayforce supports only one active employment record at a time.</span></span>

- <span data-ttu-id="24326-312">Startdatum för anställning (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="24326-312">Employment start date (required)</span></span>
- <span data-ttu-id="24326-313">Slutdatum för anställning</span><span class="sxs-lookup"><span data-stu-id="24326-313">Employment end date</span></span>
- <span data-ttu-id="24326-314">Startdatum</span><span class="sxs-lookup"><span data-stu-id="24326-314">Start date</span></span>
- <span data-ttu-id="24326-315">Justerat startdatum</span><span class="sxs-lookup"><span data-stu-id="24326-315">Adjusted start date</span></span>
- <span data-ttu-id="24326-316">Uppsägningsdatum (obligatoriskt vid uppsägning)</span><span class="sxs-lookup"><span data-stu-id="24326-316">Termination date (required upon termination)</span></span>
- <span data-ttu-id="24326-317">Uppsägningsorsak (obligatoriskt vid uppsägning)</span><span class="sxs-lookup"><span data-stu-id="24326-317">Termination reason (required upon termination)</span></span>

<span data-ttu-id="24326-318">Medarbetarens viktiga datum beräknas med hjälp av följande information.</span><span class="sxs-lookup"><span data-stu-id="24326-318">An employee's key dates are derived by using the following information.</span></span>

| <span data-ttu-id="24326-319">Talent</span><span class="sxs-lookup"><span data-stu-id="24326-319">Talent</span></span>                | <span data-ttu-id="24326-320">Dayforce</span><span class="sxs-lookup"><span data-stu-id="24326-320">Dayforce</span></span>                                                                                             |
|-----------------------|------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="24326-321">Senaste anställningsdatum</span><span class="sxs-lookup"><span data-stu-id="24326-321">Most recent hire date</span></span> | <span data-ttu-id="24326-322">Anställningsstart för aktuell, icke-uppsagd post för anställningshistorik</span><span class="sxs-lookup"><span data-stu-id="24326-322">Employment start of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="24326-323">Uppsägningsdatum</span><span class="sxs-lookup"><span data-stu-id="24326-323">Termination date</span></span>      | <span data-ttu-id="24326-324">Uppsägningsdatum för aktuell, icke-uppsagd post för anställningshistorik</span><span class="sxs-lookup"><span data-stu-id="24326-324">Termination date of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="24326-325">Startdatum</span><span class="sxs-lookup"><span data-stu-id="24326-325">Start date</span></span>            | <span data-ttu-id="24326-326">Justerat startdatum, startdatum eller anställningsstart för aktuell, inaktiv post för anställningshistorik</span><span class="sxs-lookup"><span data-stu-id="24326-326">Adjusted start date, start date, or employment start of current non-active employment history record</span></span> |
| <span data-ttu-id="24326-327">Ursprungligt anställningsdatum</span><span class="sxs-lookup"><span data-stu-id="24326-327">Original hire date</span></span>    | <span data-ttu-id="24326-328">Anställningsstart för tidigaste anställningshistorikpost</span><span class="sxs-lookup"><span data-stu-id="24326-328">Employment start of earliest employment history record</span></span>                                               |

#### <a name="compensation"></a><span data-ttu-id="24326-329">Kompensation</span><span class="sxs-lookup"><span data-stu-id="24326-329">Compensation</span></span>

<span data-ttu-id="24326-330">En fast kompensationsplan måste kopplas till varje medarbetares primära befattning under hela anställningsperioden.</span><span class="sxs-lookup"><span data-stu-id="24326-330">A fixed compensation plan must be associated with every employee's primary position throughout an employment period.</span></span> <span data-ttu-id="24326-331">Perioden inleds det datum då medarbetaren anställts (eller på anställningens startdatum) och fortsätter till och med uppsägningen.</span><span class="sxs-lookup"><span data-stu-id="24326-331">This period starts on the date that the employee was hired (or the employment start date) and continues until termination.</span></span>

- <span data-ttu-id="24326-332">Giltighetsdatum (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="24326-332">Effective Date (required)</span></span>
- <span data-ttu-id="24326-333">Utgångsdatum</span><span class="sxs-lookup"><span data-stu-id="24326-333">Expiration date</span></span>
- <span data-ttu-id="24326-334">Lönesats (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="24326-334">Pay Rate (required)</span></span>
- <span data-ttu-id="24326-335">Lönesatskonverteringar (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="24326-335">Pay Rate Conversions (required)</span></span>
- <span data-ttu-id="24326-336">Årlig motsvarighet (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="24326-336">Annual equivalent (required)</span></span>
- <span data-ttu-id="24326-337">Motsvarighet per timme (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="24326-337">Hourly equivalent (required)</span></span>

<span data-ttu-id="24326-338">Om en timanställd har flera befattningar importeras den fasta kompensationen för den primära befattningen till Dayforce som bastariff/-lön för medarbetaren.</span><span class="sxs-lookup"><span data-stu-id="24326-338">If an hourly employee has multiple positions, the fixed compensation of the primary position is imported into Dayforce as the employee-level base rate/salary.</span></span> <span data-ttu-id="24326-339">För icke-primära befattningar sparas timtariffen i motsvarande befattning i Dayforce.</span><span class="sxs-lookup"><span data-stu-id="24326-339">For non-primary positions, the hourly rate is saved to the corresponding position in Dayforce.</span></span>

<span data-ttu-id="24326-340">Om en fast anställd tjänsteman har flera befattningar hämtas den ackumulerade timtariffen och årslönen för samtliga aktiva befattningar och används som bastariff/-lön för medarbetarnivån.</span><span class="sxs-lookup"><span data-stu-id="24326-340">If a salaried employee has multiple positions, the cumulative hour rate and annual salary across all active positions are derived and used as the employee-level base rate/salary.</span></span>

#### <a name="identification-numbers"></a><span data-ttu-id="24326-341">Identifieringsnummer</span><span class="sxs-lookup"><span data-stu-id="24326-341">Identification numbers</span></span>

##### <a name="social-security-identifier"></a><span data-ttu-id="24326-342">Socialförsäkrings-identifierare</span><span class="sxs-lookup"><span data-stu-id="24326-342">Social Security identifier</span></span> 

<span data-ttu-id="24326-343">Alla medarbetare måste ha en primär identifierare.</span><span class="sxs-lookup"><span data-stu-id="24326-343">Every employee must have one primary identifier.</span></span> <span data-ttu-id="24326-344">Denna identifierare måste vara av identifieringstypen **SSN**.</span><span class="sxs-lookup"><span data-stu-id="24326-344">This identifier must be of **SSN** identification type.</span></span> <span data-ttu-id="24326-345">I Dayforce hämtas den automatiskt som den socialförsäkringsidentifierare för anställd som krävs för anställning.</span><span class="sxs-lookup"><span data-stu-id="24326-345">In Dayforce, it's automatically derived as the employee's Social Security identifier that is required for hire.</span></span>

- <span data-ttu-id="24326-346">Primär adress (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="24326-346">Primary (required)</span></span>
- <span data-ttu-id="24326-347">Identifieringstyp = "SSN"</span><span class="sxs-lookup"><span data-stu-id="24326-347">Identification Type = "SSN"</span></span>
- <span data-ttu-id="24326-348">Utfärdat den</span><span class="sxs-lookup"><span data-stu-id="24326-348">Issued Date</span></span>
- <span data-ttu-id="24326-349">Utgångsdatum</span><span class="sxs-lookup"><span data-stu-id="24326-349">Expiration Date</span></span>

<span data-ttu-id="24326-350">Medarbetare kan deklarera flera ID-nummer med ID-typen **SSN**.</span><span class="sxs-lookup"><span data-stu-id="24326-350">Employees can declare multiple identification numbers of the **SSN** identification type.</span></span> <span data-ttu-id="24326-351">Endast posten som är markerad som **Primär** integreras emellertid i Dayforce, oavsett om numret är aktivt eller har upphört att gälla.</span><span class="sxs-lookup"><span data-stu-id="24326-351">However, only the record that is marked as **Primary** is integrated into Dayforce, regardless of whether the number is active or expired.</span></span>

#### <a name="bank-accounts-and-disbursements"></a><span data-ttu-id="24326-352">Bankkonton och utbetalningar</span><span class="sxs-lookup"><span data-stu-id="24326-352">Bank accounts and disbursements</span></span>

<span data-ttu-id="24326-353">Giltig bankkontoinformation måste anges för varje medarbetare som väljer att få sin lön via bankkontoöverföringar.</span><span class="sxs-lookup"><span data-stu-id="24326-353">Valid bank account information must be entered for any employee who chooses to be paid via bank account transfers.</span></span>

| <span data-ttu-id="24326-354">Talent</span><span class="sxs-lookup"><span data-stu-id="24326-354">Talent</span></span>                         | <span data-ttu-id="24326-355">Dayforce</span><span class="sxs-lookup"><span data-stu-id="24326-355">Dayforce</span></span>                                                                                                    |
|--------------------------------|-------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="24326-356">Bankkontonummer (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="24326-356">Bank account number (required)</span></span> |                                                                                                             |
| <span data-ttu-id="24326-357">SWIFT-kod (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="24326-357">SWIFT code (required)</span></span>          | <span data-ttu-id="24326-358">Fältet **Bank-ID** används när löner bearbetas i Mexiko.</span><span class="sxs-lookup"><span data-stu-id="24326-358">**Bank ID** field used when processing payroll in Mexico.</span></span>                                                             |
| <span data-ttu-id="24326-359">Filialnummer (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="24326-359">Branch number (required)</span></span>       |                                                                                                             |
| <span data-ttu-id="24326-360">Bankkontotyp (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="24326-360">Bank account type (required)</span></span>   | <span data-ttu-id="24326-361">Fältet **Kontotyp** används när löner bearbetas i Mexiko.</span><span class="sxs-lookup"><span data-stu-id="24326-361">**Account type** field used when processing payroll in Mexico.</span></span> <span data-ttu-id="24326-362">Värden som stöds inkluderar **Check** och **Lönelista**.</span><span class="sxs-lookup"><span data-stu-id="24326-362">Supported values include **Checking** and **Payroll**.</span></span> |

> [!NOTE]
> <span data-ttu-id="24326-363">Medarbetare som väljer att få lön via bankkontoöverföring måste ange en länk till ett restkonto tillhörande en juridisk person med primär adress i Mexiko och som är associerad med ett giltigt bankkonto från en mexikansk bank.</span><span class="sxs-lookup"><span data-stu-id="24326-363">Employees who choose to be paid via bank account transfers must provide a link to a remainder account that is under a legal entity that has its primary address in Mexico and associated with a valid bank account from a Mexican bank.</span></span> <span data-ttu-id="24326-364">Alla övriga restkonton ignoreras.</span><span class="sxs-lookup"><span data-stu-id="24326-364">All other non-remainder accounts are ignored.</span></span>

#### <a name="address-information"></a><span data-ttu-id="24326-365">Adressinformation</span><span class="sxs-lookup"><span data-stu-id="24326-365">Address information</span></span>

<span data-ttu-id="24326-366">Alla medarbetare måste ha en primär plats.</span><span class="sxs-lookup"><span data-stu-id="24326-366">Every employee must have one primary location.</span></span> <span data-ttu-id="24326-367">Den här platsen används i Dayforce i syfte att fastställa medarbetarens primära hemort i skattesyfte.</span><span class="sxs-lookup"><span data-stu-id="24326-367">In Dayforce, this location is used to determine the employee's primary residence for tax purposes.</span></span>

- <span data-ttu-id="24326-368">Primär adress (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="24326-368">Primary (required)</span></span>
- <span data-ttu-id="24326-369">Land/region (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="24326-369">Country/region (required)</span></span>
- <span data-ttu-id="24326-370">Postnummer (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="24326-370">Zip/postal code (required)</span></span>
- <span data-ttu-id="24326-371">Gata (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="24326-371">Street (required)</span></span>
- <span data-ttu-id="24326-372">Nummer (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="24326-372">Street Number (required)</span></span>
- <span data-ttu-id="24326-373">Byggnadskomplement</span><span class="sxs-lookup"><span data-stu-id="24326-373">Building Complement</span></span>
- <span data-ttu-id="24326-374">Stad (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="24326-374">City (required)</span></span>
- <span data-ttu-id="24326-375">Delstat (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="24326-375">State (required)</span></span>
- <span data-ttu-id="24326-376">Region (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="24326-376">County (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-united-states-and-canada"></a><span data-ttu-id="24326-377">Konfigurera dina data för att generera lön i USA och Kanada</span><span class="sxs-lookup"><span data-stu-id="24326-377">Configure your data to generate payroll in United States and Canada</span></span>

<span data-ttu-id="24326-378">Om du genererar lön för medarbetare i USA och Kanada måste följande element konfigureras:</span><span class="sxs-lookup"><span data-stu-id="24326-378">If you're generating pay for employees in the United States and Canada, the following elements must be configured:</span></span>

- <span data-ttu-id="24326-379">Avdelningar är obligatoriska vid befattningarna:</span><span class="sxs-lookup"><span data-stu-id="24326-379">Departments are required on positions.</span></span>
- <span data-ttu-id="24326-380">Kostnadsställen måste ställas in som ekonomiska dimensioner och måste vara det första elementet i standardsträngen för ekonomisk dimension.</span><span class="sxs-lookup"><span data-stu-id="24326-380">Cost centers must be set as financial dimensions and must be the first element in the default financial dimension string.</span></span>

> [!NOTE] 
> <span data-ttu-id="24326-381">Du kan konfigurera Talent att kräva att befattningar anger en avdelning.</span><span class="sxs-lookup"><span data-stu-id="24326-381">You can configure Talent to require that Positions specify a Department.</span></span> <span data-ttu-id="24326-382">Gör detta genom att gå till **delade befattningar i Personal > befattningar > kräver avdelningar för befattningar**.</span><span class="sxs-lookup"><span data-stu-id="24326-382">To do this, go to **Human Resources Shared Positions > Positions > Require departments on positions**.</span></span> <span data-ttu-id="24326-383">Vi rekommenderar att den här inställningen tillämpas för integration.</span><span class="sxs-lookup"><span data-stu-id="24326-383">We recommend that this setting be enforced for the integration.</span></span>

### <a name="job-types"></a><span data-ttu-id="24326-384">Jobbtyper</span><span class="sxs-lookup"><span data-stu-id="24326-384">Job types</span></span>

<span data-ttu-id="24326-385">Jobbtyper används för att gruppera liknande jobb i kategorier.</span><span class="sxs-lookup"><span data-stu-id="24326-385">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="24326-386">Jobbtyper krävs för att bearbeta lön i USA och Kanada.</span><span class="sxs-lookup"><span data-stu-id="24326-386">Job types are required in order to process payroll in the United States and Canada.</span></span> <span data-ttu-id="24326-387">Några exempel på jobbtyper är heltid och deltid, eller fast lön och timpenning.</span><span class="sxs-lookup"><span data-stu-id="24326-387">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="24326-388">Jobbtyper mappas till Dayforce som lönetyper som anger huruvida en anställd arbetar per timme eller har fast lön.</span><span class="sxs-lookup"><span data-stu-id="24326-388">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="24326-389">Följande jobbtyper och beskrivningar krävs.</span><span class="sxs-lookup"><span data-stu-id="24326-389">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="24326-390">Jobbtyp</span><span class="sxs-lookup"><span data-stu-id="24326-390">Job type</span></span>   | <span data-ttu-id="24326-391">beskrivning</span><span class="sxs-lookup"><span data-stu-id="24326-391">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="24326-392">Varje timme</span><span class="sxs-lookup"><span data-stu-id="24326-392">Hourly</span></span>     | <span data-ttu-id="24326-393">Varje timme</span><span class="sxs-lookup"><span data-stu-id="24326-393">Hourly</span></span>      |
| <span data-ttu-id="24326-394">Fast lön</span><span class="sxs-lookup"><span data-stu-id="24326-394">Salaried</span></span>   | <span data-ttu-id="24326-395">Fast lön</span><span class="sxs-lookup"><span data-stu-id="24326-395">Salaried</span></span>    |

### <a name="position-types"></a><span data-ttu-id="24326-396">Befattningstyper</span><span class="sxs-lookup"><span data-stu-id="24326-396">Position types</span></span> 

<span data-ttu-id="24326-397">Du kan använda befattningstyper för att beskriva huruvida befattningen är på heltid, deltid eller annat.</span><span class="sxs-lookup"><span data-stu-id="24326-397">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="24326-398">Befattningstyper mappas till Dayforce som löneklasser som anger huruvida en anställd arbetar heltid eller deltid.</span><span class="sxs-lookup"><span data-stu-id="24326-398">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="24326-399">Följande befattningstyper och beskrivningar krävs.</span><span class="sxs-lookup"><span data-stu-id="24326-399">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="24326-400">Befattningstyp</span><span class="sxs-lookup"><span data-stu-id="24326-400">Position type</span></span>   | <span data-ttu-id="24326-401">beskrivning</span><span class="sxs-lookup"><span data-stu-id="24326-401">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="24326-402">Heltid</span><span class="sxs-lookup"><span data-stu-id="24326-402">Full-time</span></span>       | <span data-ttu-id="24326-403">Heltidsanställd</span><span class="sxs-lookup"><span data-stu-id="24326-403">Full time employee</span></span> |
| <span data-ttu-id="24326-404">Deltid</span><span class="sxs-lookup"><span data-stu-id="24326-404">Part-time</span></span>       | <span data-ttu-id="24326-405">Deltidsanställd</span><span class="sxs-lookup"><span data-stu-id="24326-405">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="24326-406">Orsakskoder</span><span class="sxs-lookup"><span data-stu-id="24326-406">Reason codes</span></span>

<span data-ttu-id="24326-407">Orsakskoder innehåller information om statusen för en medarbetare.</span><span class="sxs-lookup"><span data-stu-id="24326-407">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="24326-408">Orsakskoder mappas till Dayforce som statusanledningar som anger orsaken till ändringar i en medarbetares befattning eller anställningsstatus.</span><span class="sxs-lookup"><span data-stu-id="24326-408">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="24326-409">Följande orsakskoder och -beskrivningar krävs.</span><span class="sxs-lookup"><span data-stu-id="24326-409">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="24326-410">Orsakskod</span><span class="sxs-lookup"><span data-stu-id="24326-410">Reason code</span></span>    | <span data-ttu-id="24326-411">beskrivning</span><span class="sxs-lookup"><span data-stu-id="24326-411">Description</span></span>      | <span data-ttu-id="24326-412">Tillämpliga scenarier</span><span class="sxs-lookup"><span data-stu-id="24326-412">Applicable scenarios</span></span> |
|----------------|------------------|----------------------|
| <span data-ttu-id="24326-413">EGEN UPPSÄGNING</span><span class="sxs-lookup"><span data-stu-id="24326-413">RESIGNATION</span></span>    | <span data-ttu-id="24326-414">Egen uppsägning</span><span class="sxs-lookup"><span data-stu-id="24326-414">Resignation</span></span>      | <span data-ttu-id="24326-415">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="24326-415">Terminate worker</span></span>     |
| <span data-ttu-id="24326-416">UPPSÄGNING</span><span class="sxs-lookup"><span data-stu-id="24326-416">TERMINATION</span></span>    | <span data-ttu-id="24326-417">Uppsägning</span><span class="sxs-lookup"><span data-stu-id="24326-417">Termination</span></span>      | <span data-ttu-id="24326-418">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="24326-418">Terminate worker</span></span>     |
| <span data-ttu-id="24326-419">PENSION</span><span class="sxs-lookup"><span data-stu-id="24326-419">RETIREMENT</span></span>     | <span data-ttu-id="24326-420">Pension</span><span class="sxs-lookup"><span data-stu-id="24326-420">Retirement</span></span>       | <span data-ttu-id="24326-421">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="24326-421">Terminate worker</span></span>     |
| <span data-ttu-id="24326-422">ÖVRIGT</span><span class="sxs-lookup"><span data-stu-id="24326-422">OTHER</span></span>          | <span data-ttu-id="24326-423">Andra orsaker</span><span class="sxs-lookup"><span data-stu-id="24326-423">Other Reasons</span></span>    | <span data-ttu-id="24326-424">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="24326-424">Terminate worker</span></span>     |
| <span data-ttu-id="24326-425">DÖDSFALL</span><span class="sxs-lookup"><span data-stu-id="24326-425">DEATH</span></span>          | <span data-ttu-id="24326-426">Dödsfall</span><span class="sxs-lookup"><span data-stu-id="24326-426">Death</span></span>            | <span data-ttu-id="24326-427">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="24326-427">Terminate worker</span></span>     |
| <span data-ttu-id="24326-428">TJÄNSTLEDIGHET</span><span class="sxs-lookup"><span data-stu-id="24326-428">LEAVEOFABSENCE</span></span> | <span data-ttu-id="24326-429">Tjänstledighet</span><span class="sxs-lookup"><span data-stu-id="24326-429">Leave of Absence</span></span> | <span data-ttu-id="24326-430">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="24326-430">Terminate worker</span></span>     |
| <span data-ttu-id="24326-431">KONTRAKTSLUT</span><span class="sxs-lookup"><span data-stu-id="24326-431">CONTRACTEND</span></span>    | <span data-ttu-id="24326-432">Kontraktslut</span><span class="sxs-lookup"><span data-stu-id="24326-432">End of Contract</span></span>  | <span data-ttu-id="24326-433">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="24326-433">Terminate worker</span></span>     |
| <span data-ttu-id="24326-434">LÖNEÄNDRING</span><span class="sxs-lookup"><span data-stu-id="24326-434">SALARYCHANGE</span></span>   | <span data-ttu-id="24326-435">Löneändring</span><span class="sxs-lookup"><span data-stu-id="24326-435">Change of Salary</span></span> | <span data-ttu-id="24326-436">Kompensation</span><span class="sxs-lookup"><span data-stu-id="24326-436">Compensation</span></span>         |

### <a name="marital-status"></a><span data-ttu-id="24326-437">Civilstånd</span><span class="sxs-lookup"><span data-stu-id="24326-437">Marital status</span></span>

<span data-ttu-id="24326-438">Civilståndsvärden mappas till Dayforce och översätts på lämpligt sätt till giltiga värden i samband med integrering.</span><span class="sxs-lookup"><span data-stu-id="24326-438">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="24326-439">Följande tabell visar hur civilståndsvärden mappas till Dayforce.</span><span class="sxs-lookup"><span data-stu-id="24326-439">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="24326-440">Talent</span><span class="sxs-lookup"><span data-stu-id="24326-440">Talent</span></span>                 | <span data-ttu-id="24326-441">Dayforce</span><span class="sxs-lookup"><span data-stu-id="24326-441">Dayforce</span></span>             |
|------------------------|----------------------|
| <span data-ttu-id="24326-442">Gift</span><span class="sxs-lookup"><span data-stu-id="24326-442">Married</span></span>                | <span data-ttu-id="24326-443">Gift</span><span class="sxs-lookup"><span data-stu-id="24326-443">Married</span></span>              |
| <span data-ttu-id="24326-444">Ett</span><span class="sxs-lookup"><span data-stu-id="24326-444">Single</span></span>                 | <span data-ttu-id="24326-445">Ett</span><span class="sxs-lookup"><span data-stu-id="24326-445">Single</span></span>               |
| <span data-ttu-id="24326-446">Änka/änkling</span><span class="sxs-lookup"><span data-stu-id="24326-446">Widowed</span></span>                | <span data-ttu-id="24326-447">Änka/änkling</span><span class="sxs-lookup"><span data-stu-id="24326-447">Widowed</span></span>              |
| <span data-ttu-id="24326-448">Frånskild</span><span class="sxs-lookup"><span data-stu-id="24326-448">Divorced</span></span>               | <span data-ttu-id="24326-449">Frånskild</span><span class="sxs-lookup"><span data-stu-id="24326-449">Divorced</span></span>             |
| <span data-ttu-id="24326-450">Registrerat partnerskap</span><span class="sxs-lookup"><span data-stu-id="24326-450">Registered Partnership</span></span> | <span data-ttu-id="24326-451">Samboförhållande</span><span class="sxs-lookup"><span data-stu-id="24326-451">Domestic Partnership</span></span> |
| <span data-ttu-id="24326-452">Inga</span><span class="sxs-lookup"><span data-stu-id="24326-452">None</span></span>                   | <span data-ttu-id="24326-453">Inga</span><span class="sxs-lookup"><span data-stu-id="24326-453">None</span></span>                 |
| <span data-ttu-id="24326-454">Sambo</span><span class="sxs-lookup"><span data-stu-id="24326-454">Cohabiting</span></span>             | <span data-ttu-id="24326-455">Sambo</span><span class="sxs-lookup"><span data-stu-id="24326-455">Cohabiting</span></span>           |

### <a name="gender"></a><span data-ttu-id="24326-456">Kön</span><span class="sxs-lookup"><span data-stu-id="24326-456">Gender</span></span>

<span data-ttu-id="24326-457">Könsbeteckningar mappas till Dayforce och översätts på lämpligt sätt till giltiga värden i samband med integrering.</span><span class="sxs-lookup"><span data-stu-id="24326-457">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="24326-458">Följande tabell visar hur könsbeteckningar mappas till Dayforce.</span><span class="sxs-lookup"><span data-stu-id="24326-458">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="24326-459">Talent</span><span class="sxs-lookup"><span data-stu-id="24326-459">Talent</span></span>       | <span data-ttu-id="24326-460">Dayforce</span><span class="sxs-lookup"><span data-stu-id="24326-460">Dayforce</span></span>        |
|--------------|-----------------|
| <span data-ttu-id="24326-461">Man</span><span class="sxs-lookup"><span data-stu-id="24326-461">Male</span></span>         | <span data-ttu-id="24326-462">Man</span><span class="sxs-lookup"><span data-stu-id="24326-462">Male</span></span>            |
| <span data-ttu-id="24326-463">Kvinna</span><span class="sxs-lookup"><span data-stu-id="24326-463">Female</span></span>       | <span data-ttu-id="24326-464">Kvinna</span><span class="sxs-lookup"><span data-stu-id="24326-464">Female</span></span>          |
| <span data-ttu-id="24326-465">Icke-specifik</span><span class="sxs-lookup"><span data-stu-id="24326-465">Non-specific</span></span> | <span data-ttu-id="24326-466">*Stöds ej*</span><span class="sxs-lookup"><span data-stu-id="24326-466">*Not supported*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="24326-467">Inkomstkoder</span><span class="sxs-lookup"><span data-stu-id="24326-467">Earning codes</span></span>

<span data-ttu-id="24326-468">Inkomstkoder identifierar individuellt alla typer av arbetstagarintäkter.</span><span class="sxs-lookup"><span data-stu-id="24326-468">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="24326-469">Koderna omfattar flera olika parametrar som rör inkomster, till exempel redovisningsbestämmelser, skattelagar, rapporteringskrav och gross up-kapacitet.</span><span class="sxs-lookup"><span data-stu-id="24326-469">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="24326-470">Om en frekvens som inte stöds används tillämpas frekvensen **Varje lön** som standard för beräkningen.</span><span class="sxs-lookup"><span data-stu-id="24326-470">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="24326-471">Frekvenser som stöds</span><span class="sxs-lookup"><span data-stu-id="24326-471">Supported frequencies</span></span>

- <span data-ttu-id="24326-472">Allt</span><span class="sxs-lookup"><span data-stu-id="24326-472">All</span></span>
- <span data-ttu-id="24326-473">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="24326-473">EVERYPAY</span></span>
- <span data-ttu-id="24326-474">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="24326-474">EACHPAYPERIOD</span></span>
- <span data-ttu-id="24326-475">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="24326-475">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="24326-476">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="24326-476">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="24326-477">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="24326-477">1OFMTH</span></span>
- <span data-ttu-id="24326-478">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="24326-478">LASTOFMTH</span></span>
- <span data-ttu-id="24326-479">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="24326-479">2OFMTH</span></span>
- <span data-ttu-id="24326-480">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="24326-480">3OFMTH</span></span>
- <span data-ttu-id="24326-481">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="24326-481">4OFMTH</span></span>
- <span data-ttu-id="24326-482">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="24326-482">5OFMTH</span></span>
- <span data-ttu-id="24326-483">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="24326-483">1N2OFMTH</span></span>
- <span data-ttu-id="24326-484">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="24326-484">3N4OFMTH</span></span>
- <span data-ttu-id="24326-485">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="24326-485">1N3OFMTH</span></span>
- <span data-ttu-id="24326-486">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="24326-486">1N4OFMTH</span></span>
- <span data-ttu-id="24326-487">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="24326-487">2N3OFMTH</span></span>
- <span data-ttu-id="24326-488">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="24326-488">2N4OFMTH</span></span>
- <span data-ttu-id="24326-489">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="24326-489">1N2N3OFMTH</span></span>
- <span data-ttu-id="24326-490">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="24326-490">1N2N4OFMTH</span></span>
- <span data-ttu-id="24326-491">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="24326-491">1N3N4OFMTH</span></span>
- <span data-ttu-id="24326-492">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="24326-492">2N3N4OFMTH</span></span>
- <span data-ttu-id="24326-493">1N2N3N4OFMTH - 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="24326-493">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="24326-494">2N3N4N5OFMth - 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="24326-494">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="24326-495">1OFQTR - 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="24326-495">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="24326-496">LASTOFQTR – LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="24326-496">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="24326-497">LASTMTHOFQTR – LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="24326-497">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="24326-498">1OFYEAR - 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="24326-498">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="24326-499">LASTOFYEAR – LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="24326-499">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="24326-500">NOVNDECOFYEAR - NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="24326-500">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="24326-501">Adresser</span><span class="sxs-lookup"><span data-stu-id="24326-501">Addresses</span></span>

<span data-ttu-id="24326-502">Identifiering av specifika lands-/region-, delstats- och region(kommun)-koder kräver särskilda format som Dayforce och leverantörer i respektive land/region kan känna igen.</span><span class="sxs-lookup"><span data-stu-id="24326-502">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="24326-503">Även om formatet för städer är flexibelt måste varje stad associeras med en delstat.</span><span class="sxs-lookup"><span data-stu-id="24326-503">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="24326-504">Talent</span><span class="sxs-lookup"><span data-stu-id="24326-504">Talent</span></span>          | <span data-ttu-id="24326-505">Dayforce</span><span class="sxs-lookup"><span data-stu-id="24326-505">Dayforce</span></span>              |
|-----------------|-----------------------|
| <span data-ttu-id="24326-506">Land/region</span><span class="sxs-lookup"><span data-stu-id="24326-506">Country/Region</span></span>  | <span data-ttu-id="24326-507">Landskod</span><span class="sxs-lookup"><span data-stu-id="24326-507">Country Code</span></span>          |
| <span data-ttu-id="24326-508">Postnummer</span><span class="sxs-lookup"><span data-stu-id="24326-508">Zip/Postal Code</span></span> | <span data-ttu-id="24326-509">Postnummer</span><span class="sxs-lookup"><span data-stu-id="24326-509">Postal Code</span></span>           |
| <span data-ttu-id="24326-510">Stat</span><span class="sxs-lookup"><span data-stu-id="24326-510">State</span></span>           | <span data-ttu-id="24326-511">Delstatskod</span><span class="sxs-lookup"><span data-stu-id="24326-511">State Code</span></span>            |
| <span data-ttu-id="24326-512">Ort</span><span class="sxs-lookup"><span data-stu-id="24326-512">City</span></span>            | <span data-ttu-id="24326-513">Ort</span><span class="sxs-lookup"><span data-stu-id="24326-513">City</span></span>                  |
| <span data-ttu-id="24326-514">Län</span><span class="sxs-lookup"><span data-stu-id="24326-514">County</span></span>          | <span data-ttu-id="24326-515">Region (kommun)</span><span class="sxs-lookup"><span data-stu-id="24326-515">County (Municipality)</span></span> |
| <span data-ttu-id="24326-516">Gata</span><span class="sxs-lookup"><span data-stu-id="24326-516">Street</span></span>          | <span data-ttu-id="24326-517">Adressrad 1</span><span class="sxs-lookup"><span data-stu-id="24326-517">Address Line 1</span></span>        |

### <a name="tax-regions"></a><span data-ttu-id="24326-518">Skatteregioner</span><span class="sxs-lookup"><span data-stu-id="24326-518">Tax regions</span></span>

<span data-ttu-id="24326-519">Skatteregioner används för att bestämma vilken skattesats som ska användas vid lönegenerering.</span><span class="sxs-lookup"><span data-stu-id="24326-519">Tax regions are used to determine the appropriate tax that should be applied during payroll generation.</span></span> <span data-ttu-id="24326-520">Skatteregioner mappas till Dayforce som platsadresser.</span><span class="sxs-lookup"><span data-stu-id="24326-520">Tax regions are mapped to Dayforce as location addresses.</span></span> <span data-ttu-id="24326-521">Förvald skatteregion måste associeras med medarbetarens aktiva befattning.</span><span class="sxs-lookup"><span data-stu-id="24326-521">The default tax region must be associated with the worker's active position.</span></span> 

- <span data-ttu-id="24326-522">Skatteregion (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="24326-522">Tax region (required)</span></span>
- <span data-ttu-id="24326-523">Land/region (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="24326-523">Country/Region (required)</span></span>
- <span data-ttu-id="24326-524">Delstat (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="24326-524">State (required)</span></span>
- <span data-ttu-id="24326-525">Län</span><span class="sxs-lookup"><span data-stu-id="24326-525">County</span></span> 
- <span data-ttu-id="24326-526">Stad (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="24326-526">City (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-mexico"></a><span data-ttu-id="24326-527">Konfigurera dina data för att generera lön i Mexiko</span><span class="sxs-lookup"><span data-stu-id="24326-527">Configure your data to generate payroll in Mexico</span></span>

<span data-ttu-id="24326-528">Om du genererar lön för medarbetare i Mexiko måste följande element konfigureras:</span><span class="sxs-lookup"><span data-stu-id="24326-528">If you're generating pay for employees in Mexico, the following elements must be configured:</span></span>

- <span data-ttu-id="24326-529">Avdelningar är obligatoriska vid befattningarna:</span><span class="sxs-lookup"><span data-stu-id="24326-529">Departments are required on positions.</span></span>
- <span data-ttu-id="24326-530">Kostnadsställen måste ställas in som ekonomiska dimensioner och måste vara det första elementet i standardsträngen för ekonomisk dimension.</span><span class="sxs-lookup"><span data-stu-id="24326-530">Cost centers must be set as financial dimensions and must be the first element in the Default Financial Dimension string.</span></span>

### <a name="job-types"></a><span data-ttu-id="24326-531">Jobbtyper</span><span class="sxs-lookup"><span data-stu-id="24326-531">Job types</span></span>

<span data-ttu-id="24326-532">Jobbtyper används för att gruppera liknande jobb i kategorier.</span><span class="sxs-lookup"><span data-stu-id="24326-532">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="24326-533">Jobbtyper krävs för att bearbeta löner i Mexiko.</span><span class="sxs-lookup"><span data-stu-id="24326-533">Job types are required in order to process payroll in Mexico.</span></span> <span data-ttu-id="24326-534">Några exempel på jobbtyper är heltid och deltid, eller fast lön och timpenning.</span><span class="sxs-lookup"><span data-stu-id="24326-534">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="24326-535">Jobbtyper mappas till Dayforce som lönetyper som anger huruvida en anställd arbetar per timme eller har fast lön.</span><span class="sxs-lookup"><span data-stu-id="24326-535">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="24326-536">Följande jobbtyper och beskrivningar krävs.</span><span class="sxs-lookup"><span data-stu-id="24326-536">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="24326-537">Jobbtyp</span><span class="sxs-lookup"><span data-stu-id="24326-537">Job type</span></span>   | <span data-ttu-id="24326-538">beskrivning</span><span class="sxs-lookup"><span data-stu-id="24326-538">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="24326-539">Varje timme</span><span class="sxs-lookup"><span data-stu-id="24326-539">Hourly</span></span>     | <span data-ttu-id="24326-540">MX Varje timme</span><span class="sxs-lookup"><span data-stu-id="24326-540">MX Hourly</span></span>   |
| <span data-ttu-id="24326-541">Fast lön</span><span class="sxs-lookup"><span data-stu-id="24326-541">Salaried</span></span>   | <span data-ttu-id="24326-542">MX Fast lön</span><span class="sxs-lookup"><span data-stu-id="24326-542">MX Salaried</span></span> |

### <a name="position-types"></a><span data-ttu-id="24326-543">Befattningstyper</span><span class="sxs-lookup"><span data-stu-id="24326-543">Position types</span></span> 

<span data-ttu-id="24326-544">Du kan använda befattningstyper för att beskriva huruvida befattningen är på heltid, deltid eller annat.</span><span class="sxs-lookup"><span data-stu-id="24326-544">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="24326-545">Befattningstyper mappas till Dayforce som löneklasser som anger huruvida en anställd arbetar heltid eller deltid.</span><span class="sxs-lookup"><span data-stu-id="24326-545">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="24326-546">Följande befattningstyper och beskrivningar krävs.</span><span class="sxs-lookup"><span data-stu-id="24326-546">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="24326-547">Befattningstyp</span><span class="sxs-lookup"><span data-stu-id="24326-547">Position type</span></span>   | <span data-ttu-id="24326-548">beskrivning</span><span class="sxs-lookup"><span data-stu-id="24326-548">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="24326-549">Heltid</span><span class="sxs-lookup"><span data-stu-id="24326-549">Full-time</span></span>       | <span data-ttu-id="24326-550">Heltidsanställd</span><span class="sxs-lookup"><span data-stu-id="24326-550">Full time employee</span></span> |
| <span data-ttu-id="24326-551">Deltid</span><span class="sxs-lookup"><span data-stu-id="24326-551">Part-time</span></span>       | <span data-ttu-id="24326-552">Deltidsanställd</span><span class="sxs-lookup"><span data-stu-id="24326-552">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="24326-553">Orsakskoder</span><span class="sxs-lookup"><span data-stu-id="24326-553">Reason codes</span></span>

<span data-ttu-id="24326-554">Orsakskoder innehåller information om statusen för en medarbetare.</span><span class="sxs-lookup"><span data-stu-id="24326-554">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="24326-555">Orsakskoder mappas till Dayforce som statusanledningar som anger orsaken till ändringar i en medarbetares befattning eller anställningsstatus.</span><span class="sxs-lookup"><span data-stu-id="24326-555">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="24326-556">Följande orsakskoder och -beskrivningar krävs.</span><span class="sxs-lookup"><span data-stu-id="24326-556">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="24326-557">Orsakskod</span><span class="sxs-lookup"><span data-stu-id="24326-557">Reason code</span></span>            | <span data-ttu-id="24326-558">beskrivning</span><span class="sxs-lookup"><span data-stu-id="24326-558">Description</span></span>                    | <span data-ttu-id="24326-559">Tillämpliga scenarier</span><span class="sxs-lookup"><span data-stu-id="24326-559">Applicable scenarios</span></span> |
|------------------------|--------------------------------|----------------------|
| <span data-ttu-id="24326-560">DEPARTUREBEFOREPAYMENT</span><span class="sxs-lookup"><span data-stu-id="24326-560">DEPARTUREBEFOREPAYMENT</span></span> | <span data-ttu-id="24326-561">Avgick före första lön</span><span class="sxs-lookup"><span data-stu-id="24326-561">Departure before first payroll</span></span> | <span data-ttu-id="24326-562">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="24326-562">Terminate worker</span></span>     |
| <span data-ttu-id="24326-563">EGEN UPPSÄGNING</span><span class="sxs-lookup"><span data-stu-id="24326-563">RESIGNATION</span></span>            | <span data-ttu-id="24326-564">Egen uppsägning</span><span class="sxs-lookup"><span data-stu-id="24326-564">Resignation</span></span>                    | <span data-ttu-id="24326-565">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="24326-565">Terminate worker</span></span>     |
| <span data-ttu-id="24326-566">PENSION</span><span class="sxs-lookup"><span data-stu-id="24326-566">PENSION</span></span>                | <span data-ttu-id="24326-567">Pension</span><span class="sxs-lookup"><span data-stu-id="24326-567">Pension</span></span>                        | <span data-ttu-id="24326-568">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="24326-568">Terminate worker</span></span>     |
| <span data-ttu-id="24326-569">UPPSÄGNING</span><span class="sxs-lookup"><span data-stu-id="24326-569">TERMINATION</span></span>            | <span data-ttu-id="24326-570">Uppsägning</span><span class="sxs-lookup"><span data-stu-id="24326-570">Termination</span></span>                    | <span data-ttu-id="24326-571">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="24326-571">Terminate worker</span></span>     |
| <span data-ttu-id="24326-572">PENSION</span><span class="sxs-lookup"><span data-stu-id="24326-572">RETIREMENT</span></span>             | <span data-ttu-id="24326-573">Pension</span><span class="sxs-lookup"><span data-stu-id="24326-573">Retirement</span></span>                     | <span data-ttu-id="24326-574">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="24326-574">Terminate worker</span></span>     |
| <span data-ttu-id="24326-575">FRÅNVARANDE</span><span class="sxs-lookup"><span data-stu-id="24326-575">ABSENTEE</span></span>               | <span data-ttu-id="24326-576">Frånvarande</span><span class="sxs-lookup"><span data-stu-id="24326-576">Absentee</span></span>                       | <span data-ttu-id="24326-577">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="24326-577">Terminate worker</span></span>     |
| <span data-ttu-id="24326-578">ÖVRIGT</span><span class="sxs-lookup"><span data-stu-id="24326-578">OTHER</span></span>                  | <span data-ttu-id="24326-579">Andra orsaker</span><span class="sxs-lookup"><span data-stu-id="24326-579">Other Reasons</span></span>                  | <span data-ttu-id="24326-580">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="24326-580">Terminate worker</span></span>     |
| <span data-ttu-id="24326-581">AVSLUT</span><span class="sxs-lookup"><span data-stu-id="24326-581">CLOSURE</span></span>                | <span data-ttu-id="24326-582">Verksamheten nedlagd</span><span class="sxs-lookup"><span data-stu-id="24326-582">Business Closure</span></span>               | <span data-ttu-id="24326-583">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="24326-583">Terminate worker</span></span>     |
| <span data-ttu-id="24326-584">DÖDSFALL</span><span class="sxs-lookup"><span data-stu-id="24326-584">DEATH</span></span>                  | <span data-ttu-id="24326-585">Dödsfall</span><span class="sxs-lookup"><span data-stu-id="24326-585">Death</span></span>                          | <span data-ttu-id="24326-586">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="24326-586">Terminate worker</span></span>     |
| <span data-ttu-id="24326-587">TJÄNSTLEDIGHET</span><span class="sxs-lookup"><span data-stu-id="24326-587">LEAVEOFABSENCE</span></span>         | <span data-ttu-id="24326-588">Tjänstledighet</span><span class="sxs-lookup"><span data-stu-id="24326-588">Leave of Absence</span></span>               | <span data-ttu-id="24326-589">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="24326-589">Terminate worker</span></span>     |
| <span data-ttu-id="24326-590">KONTRAKTSLUT</span><span class="sxs-lookup"><span data-stu-id="24326-590">CONTRACTEND</span></span>            | <span data-ttu-id="24326-591">Kontraktslut</span><span class="sxs-lookup"><span data-stu-id="24326-591">End of Contract</span></span>                | <span data-ttu-id="24326-592">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="24326-592">Terminate worker</span></span>     |
| <span data-ttu-id="24326-593">LÖNEÄNDRING</span><span class="sxs-lookup"><span data-stu-id="24326-593">SALARYCHANGE</span></span>           | <span data-ttu-id="24326-594">Löneändring</span><span class="sxs-lookup"><span data-stu-id="24326-594">Change of Salary</span></span>               | <span data-ttu-id="24326-595">Kompensation</span><span class="sxs-lookup"><span data-stu-id="24326-595">Compensation</span></span>         |

### <a name="terms-of-employment"></a><span data-ttu-id="24326-596">Anställningsvillkor</span><span class="sxs-lookup"><span data-stu-id="24326-596">Terms of employment</span></span>

<span data-ttu-id="24326-597">Anställningsvillkor används för att skapa kategorier av anställningsvillkor.</span><span class="sxs-lookup"><span data-stu-id="24326-597">Terms of employment are used to create categories of employment terms.</span></span> <span data-ttu-id="24326-598">Villkoren mappas till Dayforce som indikatorvärden för anställning.</span><span class="sxs-lookup"><span data-stu-id="24326-598">The terms are mapped to Dayforce as employment indicator values.</span></span>

<span data-ttu-id="24326-599">Följande anställningsvillkor samt beskrivningar krävs.</span><span class="sxs-lookup"><span data-stu-id="24326-599">The following terms of employment and descriptions are required.</span></span>

| <span data-ttu-id="24326-600">Anställningsvillkor</span><span class="sxs-lookup"><span data-stu-id="24326-600">Terms of employment</span></span>   | <span data-ttu-id="24326-601">beskrivning</span><span class="sxs-lookup"><span data-stu-id="24326-601">Description</span></span> |
|-----------------------|-------------|
| <span data-ttu-id="24326-602">Vanligt</span><span class="sxs-lookup"><span data-stu-id="24326-602">Regular</span></span>               | <span data-ttu-id="24326-603">Vanligt</span><span class="sxs-lookup"><span data-stu-id="24326-603">Regular</span></span>     |
| <span data-ttu-id="24326-604">Direkt</span><span class="sxs-lookup"><span data-stu-id="24326-604">Direct</span></span>                | <span data-ttu-id="24326-605">Direkt</span><span class="sxs-lookup"><span data-stu-id="24326-605">Direct</span></span>      |
| <span data-ttu-id="24326-606">Praktik</span><span class="sxs-lookup"><span data-stu-id="24326-606">Internship</span></span>            | <span data-ttu-id="24326-607">Praktik</span><span class="sxs-lookup"><span data-stu-id="24326-607">Internship</span></span>  |
| <span data-ttu-id="24326-608">Permanent</span><span class="sxs-lookup"><span data-stu-id="24326-608">Permanent</span></span>             | <span data-ttu-id="24326-609">Permanent</span><span class="sxs-lookup"><span data-stu-id="24326-609">Permanent</span></span>   |

### <a name="marital-status"></a><span data-ttu-id="24326-610">Civilstånd</span><span class="sxs-lookup"><span data-stu-id="24326-610">Marital status</span></span>

<span data-ttu-id="24326-611">Civilståndsvärden mappas till Dayforce och översätts på lämpligt sätt till giltiga värden i samband med integrering.</span><span class="sxs-lookup"><span data-stu-id="24326-611">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="24326-612">Följande tabell visar hur civilståndsvärden mappas till Dayforce.</span><span class="sxs-lookup"><span data-stu-id="24326-612">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="24326-613">Talent</span><span class="sxs-lookup"><span data-stu-id="24326-613">Talent</span></span>                 | <span data-ttu-id="24326-614">Dayforce</span><span class="sxs-lookup"><span data-stu-id="24326-614">Dayforce</span></span>                  |
|------------------------|---------------------------|
| <span data-ttu-id="24326-615">Gift</span><span class="sxs-lookup"><span data-stu-id="24326-615">Married</span></span>                | <span data-ttu-id="24326-616">Gift</span><span class="sxs-lookup"><span data-stu-id="24326-616">Married</span></span>                   |
| <span data-ttu-id="24326-617">Ett</span><span class="sxs-lookup"><span data-stu-id="24326-617">Single</span></span>                 | <span data-ttu-id="24326-618">Ett</span><span class="sxs-lookup"><span data-stu-id="24326-618">Single</span></span>                    |
| <span data-ttu-id="24326-619">Änka/änkling</span><span class="sxs-lookup"><span data-stu-id="24326-619">Widowed</span></span>                | <span data-ttu-id="24326-620">Änka/änkling</span><span class="sxs-lookup"><span data-stu-id="24326-620">Widowed</span></span>                   |
| <span data-ttu-id="24326-621">Frånskild</span><span class="sxs-lookup"><span data-stu-id="24326-621">Divorced</span></span>               | <span data-ttu-id="24326-622">Frånskild</span><span class="sxs-lookup"><span data-stu-id="24326-622">Divorced</span></span>                  |
| <span data-ttu-id="24326-623">Registrerat partnerskap</span><span class="sxs-lookup"><span data-stu-id="24326-623">Registered Partnership</span></span> | <span data-ttu-id="24326-624">Samboförhållande</span><span class="sxs-lookup"><span data-stu-id="24326-624">Domestic Partnership</span></span>      |
| <span data-ttu-id="24326-625">Inga</span><span class="sxs-lookup"><span data-stu-id="24326-625">None</span></span>                   | <span data-ttu-id="24326-626">*Stöds inte i Mexiko*</span><span class="sxs-lookup"><span data-stu-id="24326-626">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="24326-627">Sambo</span><span class="sxs-lookup"><span data-stu-id="24326-627">Cohabiting</span></span>             | <span data-ttu-id="24326-628">*Stöds inte i Mexiko*</span><span class="sxs-lookup"><span data-stu-id="24326-628">*Not supported by Mexico*</span></span> |

### <a name="gender"></a><span data-ttu-id="24326-629">Kön</span><span class="sxs-lookup"><span data-stu-id="24326-629">Gender</span></span>

<span data-ttu-id="24326-630">Könsbeteckningar mappas till Dayforce och översätts på lämpligt sätt till giltiga värden i samband med integrering.</span><span class="sxs-lookup"><span data-stu-id="24326-630">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="24326-631">Följande tabell visar hur könsbeteckningar mappas till Dayforce.</span><span class="sxs-lookup"><span data-stu-id="24326-631">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="24326-632">Talent</span><span class="sxs-lookup"><span data-stu-id="24326-632">Talent</span></span>       | <span data-ttu-id="24326-633">Dayforce</span><span class="sxs-lookup"><span data-stu-id="24326-633">Dayforce</span></span>                  |
|--------------|---------------------------|
| <span data-ttu-id="24326-634">Man</span><span class="sxs-lookup"><span data-stu-id="24326-634">Male</span></span>         | <span data-ttu-id="24326-635">Man</span><span class="sxs-lookup"><span data-stu-id="24326-635">Male</span></span>                      |
| <span data-ttu-id="24326-636">Kvinna</span><span class="sxs-lookup"><span data-stu-id="24326-636">Female</span></span>       | <span data-ttu-id="24326-637">Kvinna</span><span class="sxs-lookup"><span data-stu-id="24326-637">Female</span></span>                    |
| <span data-ttu-id="24326-638">Icke-specifik</span><span class="sxs-lookup"><span data-stu-id="24326-638">Non-specific</span></span> | <span data-ttu-id="24326-639">*Stöds inte i Mexiko*</span><span class="sxs-lookup"><span data-stu-id="24326-639">*Not supported by Mexico*</span></span> |

### <a name="payment-method"></a><span data-ttu-id="24326-640">Betalningsmetod</span><span class="sxs-lookup"><span data-stu-id="24326-640">Payment method</span></span>

<span data-ttu-id="24326-641">Betalningsmetoder ger medarbetare och företag ett sätt att beskriva hur medarbetaren ska betalas.</span><span class="sxs-lookup"><span data-stu-id="24326-641">Payment methods give the employee and the company a way to describe how employees will be paid.</span></span> <span data-ttu-id="24326-642">Betalningsmetoder mappas till Dayforce och översätts på lämpligt sätt till giltiga värden i samband med integrering.</span><span class="sxs-lookup"><span data-stu-id="24326-642">Payment methods are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="24326-643">Följande tabell visar hur betalningsmetoder mappas till Dayforce.</span><span class="sxs-lookup"><span data-stu-id="24326-643">The following table shows how payment methods are mapped to Dayforce.</span></span>

| <span data-ttu-id="24326-644">Talent</span><span class="sxs-lookup"><span data-stu-id="24326-644">Talent</span></span>             | <span data-ttu-id="24326-645">Dayforce</span><span class="sxs-lookup"><span data-stu-id="24326-645">Dayforce</span></span>                  |
|--------------------|---------------------------|
| <span data-ttu-id="24326-646">Kontant</span><span class="sxs-lookup"><span data-stu-id="24326-646">Cash</span></span>               | <span data-ttu-id="24326-647">Kontant</span><span class="sxs-lookup"><span data-stu-id="24326-647">Cash</span></span>                      |
| <span data-ttu-id="24326-648">Elektronisk betalning</span><span class="sxs-lookup"><span data-stu-id="24326-648">Electronic Payment</span></span> | <span data-ttu-id="24326-649">Överför</span><span class="sxs-lookup"><span data-stu-id="24326-649">Transfer</span></span>                  |
| <span data-ttu-id="24326-650">Check</span><span class="sxs-lookup"><span data-stu-id="24326-650">Check</span></span>              | <span data-ttu-id="24326-651">Check</span><span class="sxs-lookup"><span data-stu-id="24326-651">Cheque</span></span>                    |
| <span data-ttu-id="24326-652">Bankutdrag</span><span class="sxs-lookup"><span data-stu-id="24326-652">Bank Draft</span></span>         | <span data-ttu-id="24326-653">*Stöds inte i Mexiko*</span><span class="sxs-lookup"><span data-stu-id="24326-653">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="24326-654">Annat</span><span class="sxs-lookup"><span data-stu-id="24326-654">Other</span></span>              | <span data-ttu-id="24326-655">*Stöds inte i Mexiko*</span><span class="sxs-lookup"><span data-stu-id="24326-655">*Not supported by Mexico*</span></span> |

### <a name="bank-account-type"></a><span data-ttu-id="24326-656">Bankkontotyp</span><span class="sxs-lookup"><span data-stu-id="24326-656">Bank account type</span></span>

<span data-ttu-id="24326-657">Bankkontotyper används för elektroniska betalningar till medarbetare.</span><span class="sxs-lookup"><span data-stu-id="24326-657">Bank account types are used for electronic payments to employees.</span></span> <span data-ttu-id="24326-658">Bankkontotyper mappas till Dayforce som kontoinformation för överföringar.</span><span class="sxs-lookup"><span data-stu-id="24326-658">Bank account types are mapped to Dayforce as transfer account information.</span></span> <span data-ttu-id="24326-659">Bankkontotyper översätts på lämpligt till giltiga värden i samband med integrering.</span><span class="sxs-lookup"><span data-stu-id="24326-659">The bank account types are translated, as appropriate, to the accepted values upon integration.</span></span>

| <span data-ttu-id="24326-660">Talent</span><span class="sxs-lookup"><span data-stu-id="24326-660">Talent</span></span>            | <span data-ttu-id="24326-661">Dayforce</span><span class="sxs-lookup"><span data-stu-id="24326-661">Dayforce</span></span>                  |
|-------------------|---------------------------|
| <span data-ttu-id="24326-662">Checkkonto</span><span class="sxs-lookup"><span data-stu-id="24326-662">Checking Account</span></span>  | <span data-ttu-id="24326-663">Checkkonto</span><span class="sxs-lookup"><span data-stu-id="24326-663">CheckingAccount</span></span>           |
| <span data-ttu-id="24326-664">Lönekonto</span><span class="sxs-lookup"><span data-stu-id="24326-664">Payroll Account</span></span>   | <span data-ttu-id="24326-665">Lönekonto</span><span class="sxs-lookup"><span data-stu-id="24326-665">PayrollAccount</span></span>            |
| <span data-ttu-id="24326-666">Sparkonto</span><span class="sxs-lookup"><span data-stu-id="24326-666">Savings Account</span></span>   | <span data-ttu-id="24326-667">*Stöds inte i Mexiko*</span><span class="sxs-lookup"><span data-stu-id="24326-667">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="24326-668">BankGirot-konto</span><span class="sxs-lookup"><span data-stu-id="24326-668">BankGirot account</span></span> | <span data-ttu-id="24326-669">*Stöds inte i Mexiko*</span><span class="sxs-lookup"><span data-stu-id="24326-669">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="24326-670">PlusGirot-konto</span><span class="sxs-lookup"><span data-stu-id="24326-670">PlusGirot account</span></span> | <span data-ttu-id="24326-671">*Stöds inte i Mexiko*</span><span class="sxs-lookup"><span data-stu-id="24326-671">*Not supported by Mexico*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="24326-672">Inkomstkoder</span><span class="sxs-lookup"><span data-stu-id="24326-672">Earning codes</span></span>

<span data-ttu-id="24326-673">Inkomstkoder identifierar individuellt alla typer av arbetstagarintäkter.</span><span class="sxs-lookup"><span data-stu-id="24326-673">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="24326-674">Koderna omfattar flera olika parametrar som rör inkomster, till exempel redovisningsbestämmelser, skattelagar, rapporteringskrav och gross up-kapacitet.</span><span class="sxs-lookup"><span data-stu-id="24326-674">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="24326-675">Om en frekvens som inte stöds används tillämpas frekvensen **Varje lön** som standard för beräkningen.</span><span class="sxs-lookup"><span data-stu-id="24326-675">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="24326-676">Frekvenser som stöds</span><span class="sxs-lookup"><span data-stu-id="24326-676">Supported frequencies</span></span>

- <span data-ttu-id="24326-677">Allt</span><span class="sxs-lookup"><span data-stu-id="24326-677">All</span></span>
- <span data-ttu-id="24326-678">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="24326-678">EVERYPAY</span></span>
- <span data-ttu-id="24326-679">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="24326-679">EACHPAYPERIOD</span></span>
- <span data-ttu-id="24326-680">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="24326-680">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="24326-681">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="24326-681">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="24326-682">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="24326-682">1OFMTH</span></span>
- <span data-ttu-id="24326-683">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="24326-683">LASTOFMTH</span></span>
- <span data-ttu-id="24326-684">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="24326-684">2OFMTH</span></span>
- <span data-ttu-id="24326-685">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="24326-685">3OFMTH</span></span>
- <span data-ttu-id="24326-686">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="24326-686">4OFMTH</span></span>
- <span data-ttu-id="24326-687">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="24326-687">5OFMTH</span></span>
- <span data-ttu-id="24326-688">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="24326-688">1N2OFMTH</span></span>
- <span data-ttu-id="24326-689">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="24326-689">3N4OFMTH</span></span>
- <span data-ttu-id="24326-690">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="24326-690">1N3OFMTH</span></span>
- <span data-ttu-id="24326-691">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="24326-691">1N4OFMTH</span></span>
- <span data-ttu-id="24326-692">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="24326-692">2N3OFMTH</span></span>
- <span data-ttu-id="24326-693">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="24326-693">2N4OFMTH</span></span>
- <span data-ttu-id="24326-694">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="24326-694">1N2N3OFMTH</span></span>
- <span data-ttu-id="24326-695">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="24326-695">1N2N4OFMTH</span></span>
- <span data-ttu-id="24326-696">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="24326-696">1N3N4OFMTH</span></span>
- <span data-ttu-id="24326-697">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="24326-697">2N3N4OFMTH</span></span>
- <span data-ttu-id="24326-698">1N2N3N4OFMTH - 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="24326-698">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="24326-699">2N3N4N5OFMth - 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="24326-699">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="24326-700">1OFQTR - 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="24326-700">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="24326-701">LASTOFQTR – LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="24326-701">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="24326-702">LASTMTHOFQTR – LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="24326-702">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="24326-703">1OFYEAR - 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="24326-703">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="24326-704">LASTOFYEAR – LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="24326-704">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="24326-705">NOVNDECOFYEAR - NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="24326-705">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="24326-706">Adresser</span><span class="sxs-lookup"><span data-stu-id="24326-706">Addresses</span></span>

<span data-ttu-id="24326-707">Identifiering av specifika lands-/region-, delstats- och region(kommun)-koder kräver särskilda format som Dayforce och leverantörer i respektive land/region kan känna igen.</span><span class="sxs-lookup"><span data-stu-id="24326-707">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="24326-708">Även om formatet för städer är flexibelt måste varje stad associeras med en delstat.</span><span class="sxs-lookup"><span data-stu-id="24326-708">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="24326-709">Talent</span><span class="sxs-lookup"><span data-stu-id="24326-709">Talent</span></span>              | <span data-ttu-id="24326-710">Dayforce</span><span class="sxs-lookup"><span data-stu-id="24326-710">Dayforce</span></span>              |
|---------------------|-----------------------|
| <span data-ttu-id="24326-711">Land/region</span><span class="sxs-lookup"><span data-stu-id="24326-711">Country/Region</span></span>      | <span data-ttu-id="24326-712">Landskod</span><span class="sxs-lookup"><span data-stu-id="24326-712">Country Code</span></span>          |
| <span data-ttu-id="24326-713">Postnummer</span><span class="sxs-lookup"><span data-stu-id="24326-713">Zip/Postal Code</span></span>     | <span data-ttu-id="24326-714">Postnummer</span><span class="sxs-lookup"><span data-stu-id="24326-714">Postal Code</span></span>           |
| <span data-ttu-id="24326-715">Stat</span><span class="sxs-lookup"><span data-stu-id="24326-715">State</span></span>               | <span data-ttu-id="24326-716">Delstatskod</span><span class="sxs-lookup"><span data-stu-id="24326-716">State Code</span></span>            |
| <span data-ttu-id="24326-717">Ort</span><span class="sxs-lookup"><span data-stu-id="24326-717">City</span></span>                | <span data-ttu-id="24326-718">Ort</span><span class="sxs-lookup"><span data-stu-id="24326-718">City</span></span>                  |
| <span data-ttu-id="24326-719">Län</span><span class="sxs-lookup"><span data-stu-id="24326-719">County</span></span>              | <span data-ttu-id="24326-720">Region (kommun)</span><span class="sxs-lookup"><span data-stu-id="24326-720">County (Municipality)</span></span> |
| <span data-ttu-id="24326-721">Gata</span><span class="sxs-lookup"><span data-stu-id="24326-721">Street</span></span>              | <span data-ttu-id="24326-722">Adressrad 1</span><span class="sxs-lookup"><span data-stu-id="24326-722">Address Line 1</span></span>        |
| <span data-ttu-id="24326-723">Gatunummer</span><span class="sxs-lookup"><span data-stu-id="24326-723">Street Number</span></span>       | <span data-ttu-id="24326-724">Adressrad 2</span><span class="sxs-lookup"><span data-stu-id="24326-724">Address Line 2</span></span>        |
| <span data-ttu-id="24326-725">Byggnadskomplement</span><span class="sxs-lookup"><span data-stu-id="24326-725">Building Complement</span></span> | <span data-ttu-id="24326-726">Adressrad 5</span><span class="sxs-lookup"><span data-stu-id="24326-726">Address Line 5</span></span>        |

### <a name="passport-number"></a><span data-ttu-id="24326-727">Passnummer</span><span class="sxs-lookup"><span data-stu-id="24326-727">Passport number</span></span>

<span data-ttu-id="24326-728">Medarbetare kan deklarera passinformation.</span><span class="sxs-lookup"><span data-stu-id="24326-728">Employees can declare passport information.</span></span> <span data-ttu-id="24326-729">Denna information bär ID-typen **Pass** och integreras i Dayforce som en del av medarbetarens Mexikospecifika information.</span><span class="sxs-lookup"><span data-stu-id="24326-729">This information is of the **Passport** identification type and is integrated into Dayforce as part of an employee's Mexico-specific information.</span></span>

- <span data-ttu-id="24326-730">Identifieringstyp = "Pass"</span><span class="sxs-lookup"><span data-stu-id="24326-730">Identification Type = "Passport"</span></span>
- <span data-ttu-id="24326-731">Utfärdat den</span><span class="sxs-lookup"><span data-stu-id="24326-731">Issued Date</span></span>
- <span data-ttu-id="24326-732">Utgångsdatum</span><span class="sxs-lookup"><span data-stu-id="24326-732">Expiration Date</span></span>

<span data-ttu-id="24326-733">Medarbetare kan deklarera flera ID-nummer med ID-typen **Pass**.</span><span class="sxs-lookup"><span data-stu-id="24326-733">Employees can declare multiple identification numbers of the **Passport** identification type.</span></span> <span data-ttu-id="24326-734">Endast den aktuella passposten integreras emellertid i Dayforce.</span><span class="sxs-lookup"><span data-stu-id="24326-734">However, only the current active passport entry is integrated into Dayforce.</span></span> <span data-ttu-id="24326-735">Om alla passposter har upphört att gälla kommer det pass som är utfärdat senast att integreras i Dayforce.</span><span class="sxs-lookup"><span data-stu-id="24326-735">If all passport entries are expired, the passport that was most recently issued is integrated into Dayforce.</span></span>
