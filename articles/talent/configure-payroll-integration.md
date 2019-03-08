---
title: Konfigurera löneintegrering mellan Talent och Dayforce
description: Det här avsnittet förklarar hur du konfigurerar integrationen mellan Dynamics 365 for Talent och Ceridian Dayforce så att du kan bearbeta en betalning.
author: jcart1106
manager: AnnBe
ms.date: 07/10/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations, Talent
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: fcddf82cffb9f0ba94b83eb21809b810585ebc9e
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "306237"
---
# <a name="configure-the-payroll-integration-between-talent-and-dayforce"></a><span data-ttu-id="195ba-103">Konfigurera löneintegration mellan Talent och Dayforce</span><span class="sxs-lookup"><span data-stu-id="195ba-103">Configure the payroll integration between Talent and Dayforce</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="195ba-104">Integreringen mellan Microsoft Dynamics 365 for Talent och Ceridian Dayforce är beroende av flera konfigurationssteg som beskrivs i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="195ba-104">The integration between Microsoft Dynamics 365 for Talent and Ceridian Dayforce relies on several configuration steps that are described in this topic.</span></span> <span data-ttu-id="195ba-105">Du måste konfigurera integrationen i både Talent och Dayforce innan du kan bearbeta en betalning.</span><span class="sxs-lookup"><span data-stu-id="195ba-105">You must configure the integration in both Talent and Dayforce before you can process a pay run.</span></span>

<span data-ttu-id="195ba-106">När du använder tjänster som exempelvis Dayforce för att utföra betalningar måste du aktivera integration i Talent.</span><span class="sxs-lookup"><span data-stu-id="195ba-106">When you use a service such as Dayforce to complete pay runs, you must enable the integration in Talent.</span></span> <span data-ttu-id="195ba-107">Integrationen kräver specifika data från Talent.</span><span class="sxs-lookup"><span data-stu-id="195ba-107">The integration requires specific data from Talent.</span></span> <span data-ttu-id="195ba-108">Därför måste du kontrollera att data som är mappad till Dayforce konfigureras i Talent på ett sätt som stöder integrationen.</span><span class="sxs-lookup"><span data-stu-id="195ba-108">Therefore, you must verify that data that is mapped to Dayforce is configured in Talent in a manner that supports the integration.</span></span> <span data-ttu-id="195ba-109">Integrationen använder följande breda datakategorier:</span><span class="sxs-lookup"><span data-stu-id="195ba-109">The integration uses the following broad categories of data:</span></span>

- <span data-ttu-id="195ba-110">Personaldata</span><span class="sxs-lookup"><span data-stu-id="195ba-110">Human resources data</span></span>
- <span data-ttu-id="195ba-111">Kompensationsdata</span><span class="sxs-lookup"><span data-stu-id="195ba-111">Compensation data</span></span>
- <span data-ttu-id="195ba-112">Lönedata som till exempel lönecykler, betalningsperioder och inkomstkoder</span><span class="sxs-lookup"><span data-stu-id="195ba-112">Payroll data, such as pay cycles, pay periods, and earning codes</span></span>
- <span data-ttu-id="195ba-113">Medarbetardata</span><span class="sxs-lookup"><span data-stu-id="195ba-113">Worker data</span></span>

<span data-ttu-id="195ba-114">Det här avsnittet beskriver de steg som du måste följa för att aktivera integrationen.</span><span class="sxs-lookup"><span data-stu-id="195ba-114">This topic describes the steps that you must follow to enable the integration.</span></span> <span data-ttu-id="195ba-115">Här förklaras också de typer av data och den konfigurationsinformation som integrationen kräver.</span><span class="sxs-lookup"><span data-stu-id="195ba-115">It also explains the types of data and the configuration details that the integration requires.</span></span>

## <a name="enable-the-integration"></a><span data-ttu-id="195ba-116">Aktivera integrationen</span><span class="sxs-lookup"><span data-stu-id="195ba-116">Enable the integration</span></span>

<span data-ttu-id="195ba-117">Du måste aktivera integrationen i Talent och ange konfigurationsinformation för att ansluta till Dayforce.</span><span class="sxs-lookup"><span data-stu-id="195ba-117">In Talent, you must turn on the integration and enter the configuration information to connect to Dayforce.</span></span> <span data-ttu-id="195ba-118">Om du vill att den redovisningstransaktion som framställs ska importeras till Microsoft Dynamics 365 for Finance and Operations måste du också skapa ett lagringskonto för Microsoft Azure och ange anslutningssträngen för Azure-lagring i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="195ba-118">If you want the general ledger transaction that is produced to be imported into Microsoft Dynamics 365 for Finance and Operations, you must also set up a Microsoft Azure storage account and enter the Azure Storage connection string in Finance and Operations.</span></span>

<span data-ttu-id="195ba-119">Följ dessa steg om du vill aktivera integration i Talent.</span><span class="sxs-lookup"><span data-stu-id="195ba-119">To turn on the integration in Talent, follow these steps.</span></span>

1. <span data-ttu-id="195ba-120">På sidan **Systemadministration** väljer du **Integrationskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="195ba-120">On the **System administration** page, select **Integration configuration**.</span></span>
2. <span data-ttu-id="195ba-121">Ange slutpunkten för filöverföringsprotokollet (FTP) och den säkra FTP-sökvägen.</span><span class="sxs-lookup"><span data-stu-id="195ba-121">Enter the secure File Transfer Protocol (FTP) endpoint and the secure FTP folder path.</span></span>
3. <span data-ttu-id="195ba-122">Ange användarnamn och lösenord för den användare som kommer att använda den säkra FTP-slutpunkten och mappsökvägen.</span><span class="sxs-lookup"><span data-stu-id="195ba-122">Enter the user name and password of the user who will access the secure FTP endpoint and folder path.</span></span>
4. <span data-ttu-id="195ba-123">Testa anslutningen efter behov samt ange alternativet **Aktivera integrering av löner** som **Ja**.</span><span class="sxs-lookup"><span data-stu-id="195ba-123">Test the connection, as required, and set the **Enable payroll integration** option to **Yes**.</span></span>

<span data-ttu-id="195ba-124">När integreringen aktiveras skapas dataexportpaket och filer, och frekvensen anges.</span><span class="sxs-lookup"><span data-stu-id="195ba-124">When the integration is turned on, the data export package and files are created, and the frequency is set.</span></span> <span data-ttu-id="195ba-125">Du kan ändra frekvensen efter behov.</span><span class="sxs-lookup"><span data-stu-id="195ba-125">You can change this frequency as you require.</span></span>

<span data-ttu-id="195ba-126">Mer information om Azure-lagringskonton och anslutningssträngar för Azure-lagring, se följande Azure-avsnitt:</span><span class="sxs-lookup"><span data-stu-id="195ba-126">For more information about Azure storage accounts and Azure Storage connection strings, see the following Azure topics:</span></span>

- [<span data-ttu-id="195ba-127">Om Azure-lagringskonton</span><span class="sxs-lookup"><span data-stu-id="195ba-127">About Azure storage accounts</span></span>](https://docs.microsoft.com/en-us/azure/storage/common/storage-create-storage-account?toc=%2fazure%2fstorage%2ffiles%2ftoc.json)
- [<span data-ttu-id="195ba-128">Konfigurera anslutningssträngar för Azure-lagring</span><span class="sxs-lookup"><span data-stu-id="195ba-128">Configure Azure Storage connection strings</span></span>](https://docs.microsoft.com/en-us/azure/storage/common/storage-configure-connection-string)

## <a name="configure-your-data"></a><span data-ttu-id="195ba-129">Konfigurera dina data</span><span class="sxs-lookup"><span data-stu-id="195ba-129">Configure your data</span></span> 

<span data-ttu-id="195ba-130">Du måste konfigurera personaldata för att bearbeta löner i Talent.</span><span class="sxs-lookup"><span data-stu-id="195ba-130">To process payroll, you must configure human resource data in Talent.</span></span> <span data-ttu-id="195ba-131">Du måste ställa in organisationsinformation, t.ex. jobb och befattningar samt förmåner och kompensationsinformation.</span><span class="sxs-lookup"><span data-stu-id="195ba-131">You must set up organizational data, such as jobs and positions, together with benefits and compensation information.</span></span> <span data-ttu-id="195ba-132">Denna information utgör den anställnings-, lön- och avdragsinformationen som krävs för att generera lön för medarbetare.</span><span class="sxs-lookup"><span data-stu-id="195ba-132">This information provides the employment, pay, and deduction information that is required in order to generate employee pay.</span></span>

### <a name="human-resource-data"></a><span data-ttu-id="195ba-133">Personaldata</span><span class="sxs-lookup"><span data-stu-id="195ba-133">Human resource data</span></span>

#### <a name="benefits"></a><span data-ttu-id="195ba-134">Förmåner</span><span class="sxs-lookup"><span data-stu-id="195ba-134">Benefits</span></span> 

<span data-ttu-id="195ba-135">Personal tillhandahåller verktyg som kan användas för att ställa in och underhålla förmåner, avdrag och kompensationsplaner för medarbetare som en organisation erbjuder eller bearbetar för sin personal.</span><span class="sxs-lookup"><span data-stu-id="195ba-135">Human resources provides tools for the setup and maintenance of the benefits, deductions, and worker compensation plans that an organization offers or processes for its workers.</span></span>

<span data-ttu-id="195ba-136">När du skapar förmåner, kom då ihåg följande data och konfigurationer som används i Dayforce.</span><span class="sxs-lookup"><span data-stu-id="195ba-136">When you create benefits, keep in mind the following data and configurations that are used in Dayforce.</span></span>

##### <a name="benefit-plans"></a><span data-ttu-id="195ba-137">Förmånsplaner</span><span class="sxs-lookup"><span data-stu-id="195ba-137">Benefit plans</span></span>

- <span data-ttu-id="195ba-138">Plan (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="195ba-138">Plan (required)</span></span>
- <span data-ttu-id="195ba-139">Typ (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="195ba-139">Type (required)</span></span>
- <span data-ttu-id="195ba-140">Effekt på lön (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="195ba-140">Payroll impact (required)</span></span>
- <span data-ttu-id="195ba-141">Återvinn restbetalningar</span><span class="sxs-lookup"><span data-stu-id="195ba-141">Recover arrears</span></span>
- <span data-ttu-id="195ba-142">Avdragsmetod</span><span class="sxs-lookup"><span data-stu-id="195ba-142">Deduction method</span></span>
- <span data-ttu-id="195ba-143">Avdragsprioritet</span><span class="sxs-lookup"><span data-stu-id="195ba-143">Deduction priority</span></span>
- <span data-ttu-id="195ba-144">Gränsperiod</span><span class="sxs-lookup"><span data-stu-id="195ba-144">Limit period</span></span>
- <span data-ttu-id="195ba-145">Begränsa belopp</span><span class="sxs-lookup"><span data-stu-id="195ba-145">Limit amount</span></span>

##### <a name="benefits"></a><span data-ttu-id="195ba-146">Förmåner</span><span class="sxs-lookup"><span data-stu-id="195ba-146">Benefits</span></span>

- <span data-ttu-id="195ba-147">Plan (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="195ba-147">Plan (required)</span></span>
- <span data-ttu-id="195ba-148">Typ (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="195ba-148">Type (required)</span></span>
- <span data-ttu-id="195ba-149">Tillval (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="195ba-149">Option (required)</span></span>
- <span data-ttu-id="195ba-150">Förmåns-ID (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="195ba-150">Benefit ID (required)</span></span>
- <span data-ttu-id="195ba-151">Frekvens</span><span class="sxs-lookup"><span data-stu-id="195ba-151">Frequency</span></span>
- <span data-ttu-id="195ba-152">Bas</span><span class="sxs-lookup"><span data-stu-id="195ba-152">Basis</span></span>
- <span data-ttu-id="195ba-153">Belopp eller tariff</span><span class="sxs-lookup"><span data-stu-id="195ba-153">Amount or rate</span></span>
- <span data-ttu-id="195ba-154">Inkomstkod</span><span class="sxs-lookup"><span data-stu-id="195ba-154">Earning code</span></span>

##### <a name="supported-frequencies"></a><span data-ttu-id="195ba-155">Frekvenser som stöds</span><span class="sxs-lookup"><span data-stu-id="195ba-155">Supported frequencies</span></span> 

- <span data-ttu-id="195ba-156">Varje vecka</span><span class="sxs-lookup"><span data-stu-id="195ba-156">Weekly</span></span>
- <span data-ttu-id="195ba-157">Varannan vecka</span><span class="sxs-lookup"><span data-stu-id="195ba-157">Bi-weekly</span></span>
- <span data-ttu-id="195ba-158">Var fjortonde dag</span><span class="sxs-lookup"><span data-stu-id="195ba-158">Semi-monthly</span></span>
- <span data-ttu-id="195ba-159">Månatlig</span><span class="sxs-lookup"><span data-stu-id="195ba-159">Monthly</span></span>

##### <a name="supported-bases"></a><span data-ttu-id="195ba-160">Databaser som stöds</span><span class="sxs-lookup"><span data-stu-id="195ba-160">Supported bases</span></span> 

- <span data-ttu-id="195ba-161">Fast belopp</span><span class="sxs-lookup"><span data-stu-id="195ba-161">Fixed amount</span></span>
- <span data-ttu-id="195ba-162">Procent av inkomst</span><span class="sxs-lookup"><span data-stu-id="195ba-162">Percent of earnings</span></span>
- <span data-ttu-id="195ba-163">Produktiva timmar</span><span class="sxs-lookup"><span data-stu-id="195ba-163">Productive hours</span></span>

<span data-ttu-id="195ba-164">Dayforce skapar följande avdrag baserat på den löneeffekt som definieras i förmånsplanen.</span><span class="sxs-lookup"><span data-stu-id="195ba-164">Dayforce creates the following deductions, based on the payroll impact that is defined on the benefit plan.</span></span>

| <span data-ttu-id="195ba-165">Val i Talent</span><span class="sxs-lookup"><span data-stu-id="195ba-165">Selection in Talent</span></span>        | <span data-ttu-id="195ba-166">Resultat i Dayforce</span><span class="sxs-lookup"><span data-stu-id="195ba-166">Result in Dayforce</span></span>                            |
|----------------------------|-----------------------------------------------|
| <span data-ttu-id="195ba-167">Inga</span><span class="sxs-lookup"><span data-stu-id="195ba-167">None</span></span>                       | <span data-ttu-id="195ba-168">Inget avdrag skapas.</span><span class="sxs-lookup"><span data-stu-id="195ba-168">No deduction is created.</span></span>                      |
| <span data-ttu-id="195ba-169">Endast avdrag</span><span class="sxs-lookup"><span data-stu-id="195ba-169">Deduction only</span></span>             | <span data-ttu-id="195ba-170">Löneavdrag för en medarbetare skapas.</span><span class="sxs-lookup"><span data-stu-id="195ba-170">An employee deduction is created.</span></span>             |
| <span data-ttu-id="195ba-171">Endast lönetillägg</span><span class="sxs-lookup"><span data-stu-id="195ba-171">Contribution only</span></span>          | <span data-ttu-id="195ba-172">Löneavdrag för en arbetsgivare skapas.</span><span class="sxs-lookup"><span data-stu-id="195ba-172">An employer deduction is created.</span></span>             |
| <span data-ttu-id="195ba-173">Avdrag och tillägg</span><span class="sxs-lookup"><span data-stu-id="195ba-173">Deduction and contribution</span></span> | <span data-ttu-id="195ba-174">Avdrag för medarbetare och arbetsgivare skapas.</span><span class="sxs-lookup"><span data-stu-id="195ba-174">Employee and employer deductions are created.</span></span> |

<span data-ttu-id="195ba-175">Mer information om hur du definierar och hanterar ett förmånsprogram finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="195ba-175">For more information about how to define and manage a benefits program, see the following topics:</span></span>

- [<span data-ttu-id="195ba-176">Utveckla ett förmånsprogram för medarbetare</span><span class="sxs-lookup"><span data-stu-id="195ba-176">Deliver an employee benefits program</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/deliver-employee-benefits-program)
- [<span data-ttu-id="195ba-177">Skapa en ny förmån</span><span class="sxs-lookup"><span data-stu-id="195ba-177">Create a new benefit</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/create-new-benefit)
- [<span data-ttu-id="195ba-178">Definiera förmånsberättiganderegler och policyer</span><span class="sxs-lookup"><span data-stu-id="195ba-178">Define benefit eligibility rules and policies</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-benefit-eligibility-rules-policies)
- [<span data-ttu-id="195ba-179">Registrera och ta bort förmåner för arbetare</span><span class="sxs-lookup"><span data-stu-id="195ba-179">Enroll and remove benefits from workers</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-remove-benefits-workers)

#### <a name="compensation"></a><span data-ttu-id="195ba-180">Kompensation</span><span class="sxs-lookup"><span data-stu-id="195ba-180">Compensation</span></span> 

<span data-ttu-id="195ba-181">Kompensationshantering används för att styra du utbetalningen av grundlön och belöningar.</span><span class="sxs-lookup"><span data-stu-id="195ba-181">Compensation management is used to control the delivery of base pay and awards.</span></span> <span data-ttu-id="195ba-182">En medarbetares fasta grundlön och merithöjningar kontrolleras genom fasta kompensationsplaner.</span><span class="sxs-lookup"><span data-stu-id="195ba-182">An employee's fixed base pay and merit increases are controlled through fixed compensation plans.</span></span> <span data-ttu-id="195ba-183">Betalningen av incitament, till exempel bonusar, resultatbelöningar, aktieoptioner och anslag och även engångsbelöningar kontrolleras genom variabla kompensationsplaner.</span><span class="sxs-lookup"><span data-stu-id="195ba-183">The payment of incentive pay, such as bonus payments, performance awards, stock options, and grants, and also one-time awards, are controlled through variable compensation plans.</span></span>

<span data-ttu-id="195ba-184">Dayforce använder kompensationsinformation för att beräkna en medarbetares tim- eller årliga betalning.</span><span class="sxs-lookup"><span data-stu-id="195ba-184">Dayforce uses compensation information to calculate an employee's hourly or annual rate.</span></span> <span data-ttu-id="195ba-185">Fasta kompensationsplaner och lönekonverteringar är obligatoriska.</span><span class="sxs-lookup"><span data-stu-id="195ba-185">Fixed compensation plans and pay rate conversions are required.</span></span> <span data-ttu-id="195ba-186">Medarbetarna måste vara anslutna till en fast kompensationsplan.</span><span class="sxs-lookup"><span data-stu-id="195ba-186">Employees must be associated with a fixed compensation plan.</span></span>

<span data-ttu-id="195ba-187">Mer information om att kompensationsplaner finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="195ba-187">For more information about compensation plans, see the following topics:</span></span>

- [<span data-ttu-id="195ba-188">Skapa planer för fast kompensation</span><span class="sxs-lookup"><span data-stu-id="195ba-188">Create fixed compensation plans</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/create-fixed-compensation-plans)
- [<span data-ttu-id="195ba-189">Skapa planer för variabel kompensation</span><span class="sxs-lookup"><span data-stu-id="195ba-189">Create variable compensation plans</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/create-variable-compensation-plans)
- [<span data-ttu-id="195ba-190">Utveckla struktur och planer för lön/kompensation</span><span class="sxs-lookup"><span data-stu-id="195ba-190">Develop salary/compensation structure and plans</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/develop-salary-compensation-structure-plan)
- [<span data-ttu-id="195ba-191">Bearbeta kompensation</span><span class="sxs-lookup"><span data-stu-id="195ba-191">Process compensation</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/process-compensation)
- [<span data-ttu-id="195ba-192">Definiera kompensationsprocessen och beräkna resultat</span><span class="sxs-lookup"><span data-stu-id="195ba-192">Define compensation process and calculate results</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-compensation-process-calculate-results)
- [<span data-ttu-id="195ba-193">Registrera en medarbetare i en fast kompensationsplan</span><span class="sxs-lookup"><span data-stu-id="195ba-193">Enroll an employee in a fixed compensation plan</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-fixed-compensation-plan)
- [<span data-ttu-id="195ba-194">Registrera en medarbetare i en variabel kompensationsplan</span><span class="sxs-lookup"><span data-stu-id="195ba-194">Enroll an employee in a variable compensation plan</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-variable-compensation-plan)

#### <a name="jobs"></a><span data-ttu-id="195ba-195">Jobb</span><span class="sxs-lookup"><span data-stu-id="195ba-195">Jobs</span></span> 

<span data-ttu-id="195ba-196">Ett jobb är den samling uppgifter och ansvarsområden som avkrävs en person som utför ett jobb.</span><span class="sxs-lookup"><span data-stu-id="195ba-196">A job is a collection of the tasks and responsibilities that are required of a person who performs a job.</span></span> <span data-ttu-id="195ba-197">Mer information finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="195ba-197">For more information, see the following topics:</span></span>

- [<span data-ttu-id="195ba-198">Installera komponenter för ett jobb</span><span class="sxs-lookup"><span data-stu-id="195ba-198">Setting up the components of a job</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/create-job)
- [<span data-ttu-id="195ba-199">Definiera nya jobb</span><span class="sxs-lookup"><span data-stu-id="195ba-199">Define new jobs</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-jobs)

##### <a name="positions"></a><span data-ttu-id="195ba-200">Befattningar</span><span class="sxs-lookup"><span data-stu-id="195ba-200">Positions</span></span>

<span data-ttu-id="195ba-201">En befattning är ett exempel på ett enskilt jobb.</span><span class="sxs-lookup"><span data-stu-id="195ba-201">A position is an individual instance of a job.</span></span> <span data-ttu-id="195ba-202">Befattningen "Försäljningschef (öst)" är exempelvis en av de befattningar som associeras med jobbet "Försäljningschef."</span><span class="sxs-lookup"><span data-stu-id="195ba-202">For example, the "Sales manager (East)" position is one of the positions that are associated with the "Sales manager" job.</span></span> <span data-ttu-id="195ba-203">En befattning finns på en avdelning.</span><span class="sxs-lookup"><span data-stu-id="195ba-203">A position exists in a department.</span></span> <span data-ttu-id="195ba-204">Endast en enda medarbetare kan vara associerad med respektive befattning.</span><span class="sxs-lookup"><span data-stu-id="195ba-204">Only one worker can be associated with each position.</span></span>

<span data-ttu-id="195ba-205">Tänk på följande uppgifter och konfigurationsinformation när du ställer in befattningar:</span><span class="sxs-lookup"><span data-stu-id="195ba-205">Keep the following data and configuration in mind when you set up positions:</span></span>

- <span data-ttu-id="195ba-206">Befattning (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="195ba-206">Position (required)</span></span>
- <span data-ttu-id="195ba-207">Beskrivning (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="195ba-207">Description (required)</span></span>
- <span data-ttu-id="195ba-208">Jobb (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="195ba-208">Job (required)</span></span>
- <span data-ttu-id="195ba-209">Avdelning (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="195ba-209">Department (required)</span></span>
- <span data-ttu-id="195ba-210">Befattningstyp (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="195ba-210">Position type (required)</span></span>
- <span data-ttu-id="195ba-211">Heltidslön</span><span class="sxs-lookup"><span data-stu-id="195ba-211">Full-time equivalent</span></span>
- <span data-ttu-id="195ba-212">Ordinarie timmar per år (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="195ba-212">Annual regular hours (required)</span></span>
- <span data-ttu-id="195ba-213">Betalas av den juridiska personen (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="195ba-213">Paid by legal entity (required)</span></span>
- <span data-ttu-id="195ba-214">Lönecykel (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="195ba-214">Pay cycle (required)</span></span>
- <span data-ttu-id="195ba-215">Standardekonomisk dimension – kostnadsställe (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="195ba-215">Default financial dimension – Cost center (required)</span></span>
- <span data-ttu-id="195ba-216">Medarbetartilldelning – medarbetare, tilldelningsstart, tilldelningsslut, orsakskod</span><span class="sxs-lookup"><span data-stu-id="195ba-216">Worker assignment – Worker, assignment start, assignment end, reason code</span></span>

<span data-ttu-id="195ba-217">Om flera befattningar på samma avdelning är associerade med samma jobb konsolideras de till en enda befattning i Dayforce.</span><span class="sxs-lookup"><span data-stu-id="195ba-217">If multiple positions in the same department are associated with the same job, they are consolidated into a single position in Dayforce.</span></span>

<span data-ttu-id="195ba-218">Mer information finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="195ba-218">For more information, see the following topics:</span></span>

- [<span data-ttu-id="195ba-219">Organisera arbetsstyrkan med avdelningar, jobb och befattningar</span><span class="sxs-lookup"><span data-stu-id="195ba-219">Organize your workforce using departments, jobs, and positions</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/departments-jobs-positions#positions)
- [<span data-ttu-id="195ba-220">Ställ in befattningar</span><span class="sxs-lookup"><span data-stu-id="195ba-220">Set up positions</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/set-up-positions)

#### <a name="departments"></a><span data-ttu-id="195ba-221">Avdelningar</span><span class="sxs-lookup"><span data-stu-id="195ba-221">Departments</span></span>

<span data-ttu-id="195ba-222">En avdelning är en driftenhet som representerar en kategori eller verksamhetsområde inom en organisation.</span><span class="sxs-lookup"><span data-stu-id="195ba-222">A department is an operating unit that represents a category or functional area of an organization.</span></span> <span data-ttu-id="195ba-223">En avdelning är ansvarig för en viss del av organisationen, såsom försäljning, bokföring eller mänskliga resurser.</span><span class="sxs-lookup"><span data-stu-id="195ba-223">A department is responsible for a specific area of the organization, such as sales, accounting, or human resources.</span></span> <span data-ttu-id="195ba-224">Du kan använda avdelningar att rapportera om funktionella områden.</span><span class="sxs-lookup"><span data-stu-id="195ba-224">You can use departments to report on functional areas.</span></span> <span data-ttu-id="195ba-225">Avdelningar kan ha vinst och förlust.</span><span class="sxs-lookup"><span data-stu-id="195ba-225">Departments might have profit and loss responsibility.</span></span>

<span data-ttu-id="195ba-226">Mer information finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="195ba-226">For more information, see the following topics:</span></span>

- [<span data-ttu-id="195ba-227">Skapa en avdelning och associera den med avdelningshierarkin</span><span class="sxs-lookup"><span data-stu-id="195ba-227">Create a department and associate it with the department hierarchy</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/create-department-add-department-hierarchy)
- [<span data-ttu-id="195ba-228">Definiera nya avdelningar</span><span class="sxs-lookup"><span data-stu-id="195ba-228">Define new departments</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-departments)

#### <a name="pay-cycles-and-pay-periods"></a><span data-ttu-id="195ba-229">Lönecykler och löneperioder</span><span class="sxs-lookup"><span data-stu-id="195ba-229">Pay cycles and pay periods</span></span>

<span data-ttu-id="195ba-230">En lönecykel avgör hur ofta lönelistan körs, samt vilka specifika dagar som medarbetarna får betalt.</span><span class="sxs-lookup"><span data-stu-id="195ba-230">A pay cycle determines how often payroll is run and the specific days when workers are paid.</span></span> <span data-ttu-id="195ba-231">En lönecykel kan exempelvis vara månadsvis och medarbetarna få sin lön den sista dagen i månaden.</span><span class="sxs-lookup"><span data-stu-id="195ba-231">For example, a pay cycle might be monthly, and employees might be paid on the last day of the month.</span></span> <span data-ttu-id="195ba-232">Alternativt kan en lönecykel vara veckovis och medarbetarna få sin lön på tisdagen efter betalningsperiodens utgång.</span><span class="sxs-lookup"><span data-stu-id="195ba-232">Alternatively, a pay cycle might be weekly, and employees might be paid on the Tuesday after the end of the pay period.</span></span> <span data-ttu-id="195ba-233">Lönecykler tilldelas befattningar i syfte att styra när arbetare på dessa befattningar får sin lön.</span><span class="sxs-lookup"><span data-stu-id="195ba-233">Pay cycles are assigned to positions to control when workers in those positions are paid.</span></span>

<span data-ttu-id="195ba-234">När du har skapat lönecykler kan du generera betalningsperioder för respektive cykel.</span><span class="sxs-lookup"><span data-stu-id="195ba-234">After you create pay cycles, you can generate pay periods for each cycle.</span></span> <span data-ttu-id="195ba-235">Varje betalningsperiod innehåller ett standardbetalningsdatum som baseras på den information du anger.</span><span class="sxs-lookup"><span data-stu-id="195ba-235">Each pay period includes a default payment date that is based on information that you provide.</span></span> <span data-ttu-id="195ba-236">Du kan emellertid ändra standarddatumet för betalning i en löneperiod i syfte att tillåta undantag, till exempel när betalningsdatumet infaller på en allmän helgdag.</span><span class="sxs-lookup"><span data-stu-id="195ba-236">However, you can modify the default payment date in a pay period to allow for exceptions, such as when the payment date falls on a holiday.</span></span>

<span data-ttu-id="195ba-237">Följande information används i Dayforce:</span><span class="sxs-lookup"><span data-stu-id="195ba-237">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="195ba-238">Lönecykel (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="195ba-238">Pay cycle (required)</span></span>
- <span data-ttu-id="195ba-239">Lönecykelfrekvens (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="195ba-239">Pay cycle frequency (required)</span></span>
- <span data-ttu-id="195ba-240">Periodens startdatum (första löneperiod obligatorisk)</span><span class="sxs-lookup"><span data-stu-id="195ba-240">Period start date (first pay period required)</span></span>
- <span data-ttu-id="195ba-241">Standarddatum för betalning (första löneperiod obligatorisk)</span><span class="sxs-lookup"><span data-stu-id="195ba-241">Default payment date (first pay period required)</span></span>

<span data-ttu-id="195ba-242">Denna information är integrerad i Dayforce som lönegrupper och delas upp efter land eller region för respektive lönecykel.</span><span class="sxs-lookup"><span data-stu-id="195ba-242">This information is integrated with Dayforce as pay groups, and is separated by country or region for each pay cycle.</span></span> <span data-ttu-id="195ba-243">Minst en löneperiod måste genereras före integration.</span><span class="sxs-lookup"><span data-stu-id="195ba-243">At least one pay period must be generated before integration.</span></span> <span data-ttu-id="195ba-244">Dayforce genererar gruppkalendrar för lön och betalningsdatum utifrån startdatumet för den första löneperioden och det standarddatum för betalning som anges i Talent.</span><span class="sxs-lookup"><span data-stu-id="195ba-244">Dayforce generates pay group calendars and payment dates, based on the start date of the first pay period and the default payment date that is set up in Talent.</span></span>

#### <a name="earning-codes"></a><span data-ttu-id="195ba-245">Inkomstkoder</span><span class="sxs-lookup"><span data-stu-id="195ba-245">Earning codes</span></span>

<span data-ttu-id="195ba-246">Inkomstkoder identifierar individuellt alla typer av arbetstagarintäkter.</span><span class="sxs-lookup"><span data-stu-id="195ba-246">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="195ba-247">Koderna har olika parametrar som rör inkomster, till exempel redovisningsbestämmelser, skattelagar, rapporteringskrav, och gross up-kapacitet.</span><span class="sxs-lookup"><span data-stu-id="195ba-247">The codes have various parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span>

<span data-ttu-id="195ba-248">Följande information används i Dayforce:</span><span class="sxs-lookup"><span data-stu-id="195ba-248">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="195ba-249">Inkomstkod (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="195ba-249">Earning Code (required)</span></span>
- <span data-ttu-id="195ba-250">beskrivning</span><span class="sxs-lookup"><span data-stu-id="195ba-250">Description</span></span>
- <span data-ttu-id="195ba-251">Enhet</span><span class="sxs-lookup"><span data-stu-id="195ba-251">Unit of measure</span></span>
- <span data-ttu-id="195ba-252">Produktiv</span><span class="sxs-lookup"><span data-stu-id="195ba-252">Productive</span></span>

### <a name="worker-data"></a><span data-ttu-id="195ba-253">Medarbetardata</span><span class="sxs-lookup"><span data-stu-id="195ba-253">Worker data</span></span>

<span data-ttu-id="195ba-254">Poster för de olika typer av medarbetare som du har är viktiga för dina personal- och lönesystem.</span><span class="sxs-lookup"><span data-stu-id="195ba-254">Records for the various types of workers that you have are important to your human resources and payroll systems.</span></span> <span data-ttu-id="195ba-255">Den information du anger kan användas för att spåra medarbetare och personuppgifter.</span><span class="sxs-lookup"><span data-stu-id="195ba-255">The information that you enter can be used to track workers and personal information.</span></span>

<span data-ttu-id="195ba-256">För medarbetare kan du behålla följande information:</span><span class="sxs-lookup"><span data-stu-id="195ba-256">You can maintain the following information for workers:</span></span>

- <span data-ttu-id="195ba-257">**Grundläggande** – Grundläggande information om en medarbetare, till exempel kontaktinformation, demografisk information, identifikationsinformation, familjeinformation, status för militärtjänst, exilstatusinformation samt personliga och nödkontakter.</span><span class="sxs-lookup"><span data-stu-id="195ba-257">**Basic** – Maintain basic information about a worker, such as contact information, demographic information, identification information, family information, military service status, expatriate information, and personal and emergency contacts.</span></span>
- <span data-ttu-id="195ba-258">**Anställning** – Information om en medarbetares anställning, exempelvis företags- eller organisationstillhörighet, befattningstilldelning, start- och slutdatum, jobbtillgänglighet, anställningsvillkor, pension, semester- samt omplaceringsinformation.</span><span class="sxs-lookup"><span data-stu-id="195ba-258">**Employment** – Maintain information about a worker's employment, such as company or organization affiliation, position assignment, start and end dates, work eligibility, terms of employment, pension, vacation, and relocation information.</span></span>
- <span data-ttu-id="195ba-259">**Tjänstledighet och frånvaro** – Information om en medarbetares frånvaro, exempelvis jobbkalendrar, frånvarotransaktioner samt frånvaroinställningar.</span><span class="sxs-lookup"><span data-stu-id="195ba-259">**Leave and absence** – Maintain information about a worker's absences, such as working calendars, absence transactions, and absence setup.</span></span>
- <span data-ttu-id="195ba-260">**Ersättning och lön** – Information om en medarbetares ersättningsplaner och löneinformation, exempelvis plananmälan, utmärkelser, resultat, provision, skatteinformation, pensionering samt löneavdrag.</span><span class="sxs-lookup"><span data-stu-id="195ba-260">**Compensation and payroll** – Maintain information about a worker's compensation plans and payroll information, such as plan enrollment, awards, performance, commission, tax information, retirement, and salary deductions.</span></span>

<span data-ttu-id="195ba-261">När du anger medarbetarinformation, kom då ihåg följande uppgifter och konfigurationer som används i Dayforce.</span><span class="sxs-lookup"><span data-stu-id="195ba-261">When you enter worker information, keep in mind the following data and configurations that are used in Dayforce.</span></span>

#### <a name="general-information"></a><span data-ttu-id="195ba-262">Allmän information</span><span class="sxs-lookup"><span data-stu-id="195ba-262">General information</span></span>

- <span data-ttu-id="195ba-263">Anställningsnummer (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="195ba-263">Personnel number (required)</span></span>
- <span data-ttu-id="195ba-264">Förnamn (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="195ba-264">First name (required)</span></span>
- <span data-ttu-id="195ba-265">Efternamn (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="195ba-265">Last name (required)</span></span>
- <span data-ttu-id="195ba-266">Mellannamn</span><span class="sxs-lookup"><span data-stu-id="195ba-266">Middle name</span></span>
- <span data-ttu-id="195ba-267">Datum för tjänsteålder</span><span class="sxs-lookup"><span data-stu-id="195ba-267">Seniority date</span></span>
- <span data-ttu-id="195ba-268">Känt som</span><span class="sxs-lookup"><span data-stu-id="195ba-268">Known as</span></span>

#### <a name="personal-information"></a><span data-ttu-id="195ba-269">Personlig information</span><span class="sxs-lookup"><span data-stu-id="195ba-269">Personal information</span></span>

- <span data-ttu-id="195ba-270">Civilstånd (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="195ba-270">Marital status (required)</span></span>
- <span data-ttu-id="195ba-271">Födelsedatum (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="195ba-271">Birth date (required)</span></span>
- <span data-ttu-id="195ba-272">Könstillhörighet (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="195ba-272">Gender (required)</span></span>
- <span data-ttu-id="195ba-273">Person med funktionsnedsättningar</span><span class="sxs-lookup"><span data-stu-id="195ba-273">Person with disabilities</span></span>
- <span data-ttu-id="195ba-274">Medborgarskap, land, region (endast för Mexiko)</span><span class="sxs-lookup"><span data-stu-id="195ba-274">Nationality country region (only for Mexico)</span></span>

#### <a name="address-information"></a><span data-ttu-id="195ba-275">Adressinformation</span><span class="sxs-lookup"><span data-stu-id="195ba-275">Address information</span></span>

- <span data-ttu-id="195ba-276">Primär adress (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="195ba-276">Primary (required)</span></span>
- <span data-ttu-id="195ba-277">Land/region (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="195ba-277">Country/region (required)</span></span>
- <span data-ttu-id="195ba-278">Postnummer (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="195ba-278">Postal code (required)</span></span>
- <span data-ttu-id="195ba-279">Nummer (obligatoriskt) (endast för Mexiko)</span><span class="sxs-lookup"><span data-stu-id="195ba-279">Street Number (required) (Only for Mexico)</span></span>
- <span data-ttu-id="195ba-280">Byggnadskomplement (endast för Mexiko)</span><span class="sxs-lookup"><span data-stu-id="195ba-280">Building Complement (Only for Mexico)</span></span>
- <span data-ttu-id="195ba-281">Stad (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="195ba-281">City (required)</span></span>
- <span data-ttu-id="195ba-282">Delstat (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="195ba-282">State (required)</span></span>
- <span data-ttu-id="195ba-283">Region (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="195ba-283">County (required)</span></span>

#### <a name="contact-information"></a><span data-ttu-id="195ba-284">Kontaktinformation</span><span class="sxs-lookup"><span data-stu-id="195ba-284">Contact information</span></span> 

- <span data-ttu-id="195ba-285">Primär adress (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="195ba-285">Primary (required)</span></span>
- <span data-ttu-id="195ba-286">Kontaktnummer (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="195ba-286">Contact number (required)</span></span>
- <span data-ttu-id="195ba-287">Anknytning</span><span class="sxs-lookup"><span data-stu-id="195ba-287">Extension</span></span>

#### <a name="payroll-information-and-earning-codes"></a><span data-ttu-id="195ba-288">Löneinformation och inkomstkoder</span><span class="sxs-lookup"><span data-stu-id="195ba-288">Payroll information and earning codes</span></span>

<span data-ttu-id="195ba-289">Medarbetare kan tilldelas en viss inkomst till en viss betalningsfrekvens och ha en prioriterad betalningsmetod.</span><span class="sxs-lookup"><span data-stu-id="195ba-289">Employees may be assigned specific earnings at a given frequency of payment and have a preferred payment method.</span></span> <span data-ttu-id="195ba-290">Följande fält används i Dayforce för att garantera att dessa prioriteringar och inställningar används.</span><span class="sxs-lookup"><span data-stu-id="195ba-290">The following fields are used in Dayforce to help guarantee that those preferences and settings are used.</span></span>

##### <a name="earning-codes"></a><span data-ttu-id="195ba-291">Inkomstkoder</span><span class="sxs-lookup"><span data-stu-id="195ba-291">Earning codes</span></span>

- <span data-ttu-id="195ba-292">Befattning (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="195ba-292">Position (required)</span></span>
- <span data-ttu-id="195ba-293">Inkomstkod (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="195ba-293">Earning Code (required)</span></span>
- <span data-ttu-id="195ba-294">Frekvens (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="195ba-294">Frequency (required)</span></span>
- <span data-ttu-id="195ba-295">Belopp (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="195ba-295">Amount (required)</span></span>

##### <a name="payroll-information"></a><span data-ttu-id="195ba-296">Löneinformation</span><span class="sxs-lookup"><span data-stu-id="195ba-296">Payroll information</span></span>

- <span data-ttu-id="195ba-297">Betalningsmetod</span><span class="sxs-lookup"><span data-stu-id="195ba-297">Payment Method</span></span>
- <span data-ttu-id="195ba-298">Ekonomisk region (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="195ba-298">Economic Region (required)</span></span>
- <span data-ttu-id="195ba-299">ID för anställningsförmåner</span><span class="sxs-lookup"><span data-stu-id="195ba-299">Employee Benefits ID</span></span>
- <span data-ttu-id="195ba-300">Nationellt ID-nummer (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="195ba-300">National ID Number (required)</span></span>
- <span data-ttu-id="195ba-301">Militärtjänstgöring, nummer</span><span class="sxs-lookup"><span data-stu-id="195ba-301">Military Service Number</span></span>
- <span data-ttu-id="195ba-302">Skiftes-ID (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="195ba-302">Shift ID (required)</span></span>
- <span data-ttu-id="195ba-303">Skattenummer (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="195ba-303">Tax Number (required)</span></span>
- <span data-ttu-id="195ba-304">Fack-ID (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="195ba-304">Union ID (required)</span></span>
- <span data-ttu-id="195ba-305">Arbetsdags-ID (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="195ba-305">Work Day ID (required)</span></span>
- <span data-ttu-id="195ba-306">Arbetstillståndsnummer</span><span class="sxs-lookup"><span data-stu-id="195ba-306">Work Permit Number</span></span>

> [!NOTE]
> <span data-ttu-id="195ba-307">För betalningsmetoden stöder Mexiko **Kontant**, **Check** (företagets fysiska check), samt **Elektronisk betalning**.</span><span class="sxs-lookup"><span data-stu-id="195ba-307">For the payment method, Mexico supports **Cash**, **Check** (the company's physical check), and **Electronic Payment**.</span></span> <span data-ttu-id="195ba-308">Om betalningsmetoden np anges används **Check** som standard.</span><span class="sxs-lookup"><span data-stu-id="195ba-308">If np payment method is specified, **Check** is used by default.</span></span>

#### <a name="employment-details"></a><span data-ttu-id="195ba-309">Anställningsinformation</span><span class="sxs-lookup"><span data-stu-id="195ba-309">Employment details</span></span>

<span data-ttu-id="195ba-310">Detaljerad anställningshistorik används som viktig information i syfte att hämta en medarbetares anställnings-, uppsägnings- och återanställningsstatus i Dayforce.</span><span class="sxs-lookup"><span data-stu-id="195ba-310">Employment detail history is used as key information to derive an employee's hire, termination, and rehire statuses in Dayforce.</span></span> <span data-ttu-id="195ba-311">Dayforce stöder endast en aktiv anställningspost åt gången.</span><span class="sxs-lookup"><span data-stu-id="195ba-311">Dayforce supports only one active employment record at a time.</span></span>

- <span data-ttu-id="195ba-312">Startdatum för anställning (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="195ba-312">Employment start date (required)</span></span>
- <span data-ttu-id="195ba-313">Slutdatum för anställning</span><span class="sxs-lookup"><span data-stu-id="195ba-313">Employment end date</span></span>
- <span data-ttu-id="195ba-314">Startdatum</span><span class="sxs-lookup"><span data-stu-id="195ba-314">Start date</span></span>
- <span data-ttu-id="195ba-315">Justerat startdatum</span><span class="sxs-lookup"><span data-stu-id="195ba-315">Adjusted start date</span></span>
- <span data-ttu-id="195ba-316">Uppsägningsdatum (obligatoriskt vid uppsägning)</span><span class="sxs-lookup"><span data-stu-id="195ba-316">Termination date (required upon termination)</span></span>
- <span data-ttu-id="195ba-317">Uppsägningsorsak (obligatoriskt vid uppsägning)</span><span class="sxs-lookup"><span data-stu-id="195ba-317">Termination reason (required upon termination)</span></span>

<span data-ttu-id="195ba-318">Medarbetarens viktiga datum beräknas med hjälp av följande information.</span><span class="sxs-lookup"><span data-stu-id="195ba-318">An employee's key dates are derived by using the following information.</span></span>

| <span data-ttu-id="195ba-319">Talent</span><span class="sxs-lookup"><span data-stu-id="195ba-319">Talent</span></span>                | <span data-ttu-id="195ba-320">Dayforce</span><span class="sxs-lookup"><span data-stu-id="195ba-320">Dayforce</span></span>                                                                                             |
|-----------------------|------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="195ba-321">Senaste anställningsdatum</span><span class="sxs-lookup"><span data-stu-id="195ba-321">Most recent hire date</span></span> | <span data-ttu-id="195ba-322">Anställningsstart för aktuell, icke-uppsagd post för anställningshistorik</span><span class="sxs-lookup"><span data-stu-id="195ba-322">Employment start of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="195ba-323">Uppsägningsdatum</span><span class="sxs-lookup"><span data-stu-id="195ba-323">Termination date</span></span>      | <span data-ttu-id="195ba-324">Uppsägningsdatum för aktuell, icke-uppsagd post för anställningshistorik</span><span class="sxs-lookup"><span data-stu-id="195ba-324">Termination date of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="195ba-325">Startdatum</span><span class="sxs-lookup"><span data-stu-id="195ba-325">Start date</span></span>            | <span data-ttu-id="195ba-326">Justerat startdatum, startdatum eller anställningsstart för aktuell, inaktiv post för anställningshistorik</span><span class="sxs-lookup"><span data-stu-id="195ba-326">Adjusted start date, start date, or employment start of current non-active employment history record</span></span> |
| <span data-ttu-id="195ba-327">Ursprungligt anställningsdatum</span><span class="sxs-lookup"><span data-stu-id="195ba-327">Original hire date</span></span>    | <span data-ttu-id="195ba-328">Anställningsstart för tidigaste anställningshistorikpost</span><span class="sxs-lookup"><span data-stu-id="195ba-328">Employment start of earliest employment history record</span></span>                                               |

#### <a name="compensation"></a><span data-ttu-id="195ba-329">Kompensation</span><span class="sxs-lookup"><span data-stu-id="195ba-329">Compensation</span></span>

<span data-ttu-id="195ba-330">En fast kompensationsplan måste kopplas till varje medarbetares primära befattning under hela anställningsperioden.</span><span class="sxs-lookup"><span data-stu-id="195ba-330">A fixed compensation plan must be associated with every employee's primary position throughout an employment period.</span></span> <span data-ttu-id="195ba-331">Perioden inleds det datum då medarbetaren anställts (eller på anställningens startdatum) och fortsätter till och med uppsägningen.</span><span class="sxs-lookup"><span data-stu-id="195ba-331">This period starts on the date that the employee was hired (or the employment start date) and continues until termination.</span></span>

- <span data-ttu-id="195ba-332">Giltighetsdatum (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="195ba-332">Effective Date (required)</span></span>
- <span data-ttu-id="195ba-333">Utgångsdatum</span><span class="sxs-lookup"><span data-stu-id="195ba-333">Expiration date</span></span>
- <span data-ttu-id="195ba-334">Lönesats (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="195ba-334">Pay Rate (required)</span></span>
- <span data-ttu-id="195ba-335">Lönesatskonverteringar (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="195ba-335">Pay Rate Conversions (required)</span></span>
- <span data-ttu-id="195ba-336">Årlig motsvarighet (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="195ba-336">Annual equivalent (required)</span></span>
- <span data-ttu-id="195ba-337">Motsvarighet per timme (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="195ba-337">Hourly equivalent (required)</span></span>

<span data-ttu-id="195ba-338">Om en timanställd har flera befattningar importeras den fasta kompensationen för den primära befattningen till Dayforce som bastariff/-lön för medarbetaren.</span><span class="sxs-lookup"><span data-stu-id="195ba-338">If an hourly employee has multiple positions, the fixed compensation of the primary position is imported into Dayforce as the employee-level base rate/salary.</span></span> <span data-ttu-id="195ba-339">För icke-primära befattningar sparas timtariffen i motsvarande befattning i Dayforce.</span><span class="sxs-lookup"><span data-stu-id="195ba-339">For non-primary positions, the hourly rate is saved to the corresponding position in Dayforce.</span></span>

<span data-ttu-id="195ba-340">Om en fast anställd tjänsteman har flera befattningar hämtas den ackumulerade timtariffen och årslönen för samtliga aktiva befattningar och används som bastariff/-lön för medarbetarnivån.</span><span class="sxs-lookup"><span data-stu-id="195ba-340">If a salaried employee has multiple positions, the cumulative hour rate and annual salary across all active positions are derived and used as the employee-level base rate/salary.</span></span>

#### <a name="identification-numbers"></a><span data-ttu-id="195ba-341">Identifieringsnummer</span><span class="sxs-lookup"><span data-stu-id="195ba-341">Identification numbers</span></span>

##### <a name="social-security-identifier"></a><span data-ttu-id="195ba-342">Socialförsäkrings-identifierare</span><span class="sxs-lookup"><span data-stu-id="195ba-342">Social Security identifier</span></span> 

<span data-ttu-id="195ba-343">Alla medarbetare måste ha en primär identifierare.</span><span class="sxs-lookup"><span data-stu-id="195ba-343">Every employee must have one primary identifier.</span></span> <span data-ttu-id="195ba-344">Denna identifierare måste vara av identifieringstypen **SSN**.</span><span class="sxs-lookup"><span data-stu-id="195ba-344">This identifier must be of **SSN** identification type.</span></span> <span data-ttu-id="195ba-345">I Dayforce hämtas den automatiskt som den socialförsäkringsidentifierare för anställd som krävs för anställning.</span><span class="sxs-lookup"><span data-stu-id="195ba-345">In Dayforce, it's automatically derived as the employee's Social Security identifier that is required for hire.</span></span>

- <span data-ttu-id="195ba-346">Primär adress (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="195ba-346">Primary (required)</span></span>
- <span data-ttu-id="195ba-347">Identifieringstyp = "SSN"</span><span class="sxs-lookup"><span data-stu-id="195ba-347">Identification Type = "SSN"</span></span>
- <span data-ttu-id="195ba-348">Utfärdat den</span><span class="sxs-lookup"><span data-stu-id="195ba-348">Issued Date</span></span>
- <span data-ttu-id="195ba-349">Utgångsdatum</span><span class="sxs-lookup"><span data-stu-id="195ba-349">Expiration Date</span></span>

<span data-ttu-id="195ba-350">Medarbetare kan deklarera flera ID-nummer med ID-typen **SSN**.</span><span class="sxs-lookup"><span data-stu-id="195ba-350">Employees can declare multiple identification numbers of the **SSN** identification type.</span></span> <span data-ttu-id="195ba-351">Endast posten som är markerad som **Primär** integreras emellertid i Dayforce, oavsett om numret är aktivt eller har upphört att gälla.</span><span class="sxs-lookup"><span data-stu-id="195ba-351">However, only the record that is marked as **Primary** is integrated into Dayforce, regardless of whether the number is active or expired.</span></span>

#### <a name="bank-accounts-and-disbursements"></a><span data-ttu-id="195ba-352">Bankkonton och utbetalningar</span><span class="sxs-lookup"><span data-stu-id="195ba-352">Bank accounts and disbursements</span></span>

<span data-ttu-id="195ba-353">Giltig bankkontoinformation måste anges för varje medarbetare som väljer att få sin lön via bankkontoöverföringar.</span><span class="sxs-lookup"><span data-stu-id="195ba-353">Valid bank account information must be entered for any employee who chooses to be paid via bank account transfers.</span></span>

| <span data-ttu-id="195ba-354">Talent</span><span class="sxs-lookup"><span data-stu-id="195ba-354">Talent</span></span>                         | <span data-ttu-id="195ba-355">Dayforce</span><span class="sxs-lookup"><span data-stu-id="195ba-355">Dayforce</span></span>                                                                                                    |
|--------------------------------|-------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="195ba-356">Bankkontonummer (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="195ba-356">Bank account number (required)</span></span> |                                                                                                             |
| <span data-ttu-id="195ba-357">SWIFT-kod (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="195ba-357">SWIFT code (required)</span></span>          | <span data-ttu-id="195ba-358">Fältet **Bank-ID** används när löner bearbetas i Mexiko.</span><span class="sxs-lookup"><span data-stu-id="195ba-358">**Bank ID** field used when processing payroll in Mexico.</span></span>                                                             |
| <span data-ttu-id="195ba-359">Filialnummer (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="195ba-359">Branch number (required)</span></span>       |                                                                                                             |
| <span data-ttu-id="195ba-360">Bankkontotyp (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="195ba-360">Bank account type (required)</span></span>   | <span data-ttu-id="195ba-361">Fältet **Kontotyp** används när löner bearbetas i Mexiko.</span><span class="sxs-lookup"><span data-stu-id="195ba-361">**Account type** field used when processing payroll in Mexico.</span></span> <span data-ttu-id="195ba-362">Värden som stöds inkluderar **Check** och **Lönelista**.</span><span class="sxs-lookup"><span data-stu-id="195ba-362">Supported values include **Checking** and **Payroll**.</span></span> |

> [!NOTE]
> <span data-ttu-id="195ba-363">Medarbetare som väljer att få lön via bankkontoöverföring måste ange en länk till ett restkonto tillhörande en juridisk person med primär adress i Mexiko och som är associerad med ett giltigt bankkonto från en mexikansk bank.</span><span class="sxs-lookup"><span data-stu-id="195ba-363">Employees who choose to be paid via bank account transfers must provide a link to a remainder account that is under a legal entity that has its primary address in Mexico and associated with a valid bank account from a Mexican bank.</span></span> <span data-ttu-id="195ba-364">Alla övriga restkonton ignoreras.</span><span class="sxs-lookup"><span data-stu-id="195ba-364">All other non-remainder accounts are ignored.</span></span>

#### <a name="address-information"></a><span data-ttu-id="195ba-365">Adressinformation</span><span class="sxs-lookup"><span data-stu-id="195ba-365">Address information</span></span>

<span data-ttu-id="195ba-366">Alla medarbetare måste ha en primär plats.</span><span class="sxs-lookup"><span data-stu-id="195ba-366">Every employee must have one primary location.</span></span> <span data-ttu-id="195ba-367">Den här platsen används i Dayforce i syfte att fastställa medarbetarens primära hemort i skattesyfte.</span><span class="sxs-lookup"><span data-stu-id="195ba-367">In Dayforce, this location is used to determine the employee's primary residence for tax purposes.</span></span>

- <span data-ttu-id="195ba-368">Primär adress (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="195ba-368">Primary (required)</span></span>
- <span data-ttu-id="195ba-369">Land/region (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="195ba-369">Country/region (required)</span></span>
- <span data-ttu-id="195ba-370">Postnummer (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="195ba-370">Zip/postal code (required)</span></span>
- <span data-ttu-id="195ba-371">Gata (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="195ba-371">Street (required)</span></span>
- <span data-ttu-id="195ba-372">Nummer (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="195ba-372">Street Number (required)</span></span>
- <span data-ttu-id="195ba-373">Byggnadskomplement</span><span class="sxs-lookup"><span data-stu-id="195ba-373">Building Complement</span></span>
- <span data-ttu-id="195ba-374">Stad (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="195ba-374">City (required)</span></span>
- <span data-ttu-id="195ba-375">Delstat (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="195ba-375">State (required)</span></span>
- <span data-ttu-id="195ba-376">Region (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="195ba-376">County (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-united-states-and-canada"></a><span data-ttu-id="195ba-377">Konfigurera dina data för att generera lön i USA och Kanada</span><span class="sxs-lookup"><span data-stu-id="195ba-377">Configure your data to generate payroll in United States and Canada</span></span>

<span data-ttu-id="195ba-378">Om du genererar lön för medarbetare i USA och Kanada måste följande element konfigureras:</span><span class="sxs-lookup"><span data-stu-id="195ba-378">If you're generating pay for employees in the United States and Canada, the following elements must be configured:</span></span>

- <span data-ttu-id="195ba-379">Avdelningar är obligatoriska vid befattningarna:</span><span class="sxs-lookup"><span data-stu-id="195ba-379">Departments are required on positions.</span></span>
- <span data-ttu-id="195ba-380">Kostnadsställen måste ställas in som ekonomiska dimensioner och måste vara det första elementet i standardsträngen för ekonomisk dimension.</span><span class="sxs-lookup"><span data-stu-id="195ba-380">Cost centers must be set as financial dimensions and must be the first element in the default financial dimension string.</span></span>

### <a name="job-types"></a><span data-ttu-id="195ba-381">Jobbtyper</span><span class="sxs-lookup"><span data-stu-id="195ba-381">Job types</span></span>

<span data-ttu-id="195ba-382">Jobbtyper används för att gruppera liknande jobb i kategorier.</span><span class="sxs-lookup"><span data-stu-id="195ba-382">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="195ba-383">Jobbtyper krävs för att bearbeta lön i USA och Kanada.</span><span class="sxs-lookup"><span data-stu-id="195ba-383">Job types are required in order to process payroll in the United States and Canada.</span></span> <span data-ttu-id="195ba-384">Några exempel på jobbtyper är heltid och deltid, eller fast lön och timpenning.</span><span class="sxs-lookup"><span data-stu-id="195ba-384">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="195ba-385">Jobbtyper mappas till Dayforce som lönetyper som anger huruvida en anställd arbetar per timme eller har fast lön.</span><span class="sxs-lookup"><span data-stu-id="195ba-385">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="195ba-386">Följande jobbtyper och beskrivningar krävs.</span><span class="sxs-lookup"><span data-stu-id="195ba-386">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="195ba-387">Jobbtyp</span><span class="sxs-lookup"><span data-stu-id="195ba-387">Job type</span></span>   | <span data-ttu-id="195ba-388">beskrivning</span><span class="sxs-lookup"><span data-stu-id="195ba-388">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="195ba-389">Varje timme</span><span class="sxs-lookup"><span data-stu-id="195ba-389">Hourly</span></span>     | <span data-ttu-id="195ba-390">Varje timme</span><span class="sxs-lookup"><span data-stu-id="195ba-390">Hourly</span></span>      |
| <span data-ttu-id="195ba-391">Fast lön</span><span class="sxs-lookup"><span data-stu-id="195ba-391">Salaried</span></span>   | <span data-ttu-id="195ba-392">Fast lön</span><span class="sxs-lookup"><span data-stu-id="195ba-392">Salaried</span></span>    |

### <a name="position-types"></a><span data-ttu-id="195ba-393">Befattningstyper</span><span class="sxs-lookup"><span data-stu-id="195ba-393">Position types</span></span> 

<span data-ttu-id="195ba-394">Du kan använda befattningstyper för att beskriva huruvida befattningen är på heltid, deltid eller annat.</span><span class="sxs-lookup"><span data-stu-id="195ba-394">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="195ba-395">Befattningstyper mappas till Dayforce som löneklasser som anger huruvida en anställd arbetar heltid eller deltid.</span><span class="sxs-lookup"><span data-stu-id="195ba-395">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="195ba-396">Följande befattningstyper och beskrivningar krävs.</span><span class="sxs-lookup"><span data-stu-id="195ba-396">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="195ba-397">Befattningstyp</span><span class="sxs-lookup"><span data-stu-id="195ba-397">Position type</span></span>   | <span data-ttu-id="195ba-398">beskrivning</span><span class="sxs-lookup"><span data-stu-id="195ba-398">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="195ba-399">Heltid</span><span class="sxs-lookup"><span data-stu-id="195ba-399">Full-time</span></span>       | <span data-ttu-id="195ba-400">Heltidsanställd</span><span class="sxs-lookup"><span data-stu-id="195ba-400">Full time employee</span></span> |
| <span data-ttu-id="195ba-401">Deltid</span><span class="sxs-lookup"><span data-stu-id="195ba-401">Part-time</span></span>       | <span data-ttu-id="195ba-402">Deltidsanställd</span><span class="sxs-lookup"><span data-stu-id="195ba-402">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="195ba-403">Orsakskoder</span><span class="sxs-lookup"><span data-stu-id="195ba-403">Reason codes</span></span>

<span data-ttu-id="195ba-404">Orsakskoder innehåller information om statusen för en medarbetare.</span><span class="sxs-lookup"><span data-stu-id="195ba-404">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="195ba-405">Orsakskoder mappas till Dayforce som statusanledningar som anger orsaken till ändringar i en medarbetares befattning eller anställningsstatus.</span><span class="sxs-lookup"><span data-stu-id="195ba-405">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="195ba-406">Följande orsakskoder och -beskrivningar krävs.</span><span class="sxs-lookup"><span data-stu-id="195ba-406">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="195ba-407">Orsakskod</span><span class="sxs-lookup"><span data-stu-id="195ba-407">Reason code</span></span>    | <span data-ttu-id="195ba-408">beskrivning</span><span class="sxs-lookup"><span data-stu-id="195ba-408">Description</span></span>      | <span data-ttu-id="195ba-409">Tillämpliga scenarier</span><span class="sxs-lookup"><span data-stu-id="195ba-409">Applicable scenarios</span></span> |
|----------------|------------------|----------------------|
| <span data-ttu-id="195ba-410">EGEN UPPSÄGNING</span><span class="sxs-lookup"><span data-stu-id="195ba-410">RESIGNATION</span></span>    | <span data-ttu-id="195ba-411">Egen uppsägning</span><span class="sxs-lookup"><span data-stu-id="195ba-411">Resignation</span></span>      | <span data-ttu-id="195ba-412">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="195ba-412">Terminate worker</span></span>     |
| <span data-ttu-id="195ba-413">UPPSÄGNING</span><span class="sxs-lookup"><span data-stu-id="195ba-413">TERMINATION</span></span>    | <span data-ttu-id="195ba-414">Uppsägning</span><span class="sxs-lookup"><span data-stu-id="195ba-414">Termination</span></span>      | <span data-ttu-id="195ba-415">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="195ba-415">Terminate worker</span></span>     |
| <span data-ttu-id="195ba-416">PENSION</span><span class="sxs-lookup"><span data-stu-id="195ba-416">RETIREMENT</span></span>     | <span data-ttu-id="195ba-417">Pension</span><span class="sxs-lookup"><span data-stu-id="195ba-417">Retirement</span></span>       | <span data-ttu-id="195ba-418">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="195ba-418">Terminate worker</span></span>     |
| <span data-ttu-id="195ba-419">ÖVRIGT</span><span class="sxs-lookup"><span data-stu-id="195ba-419">OTHER</span></span>          | <span data-ttu-id="195ba-420">Andra orsaker</span><span class="sxs-lookup"><span data-stu-id="195ba-420">Other Reasons</span></span>    | <span data-ttu-id="195ba-421">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="195ba-421">Terminate worker</span></span>     |
| <span data-ttu-id="195ba-422">DÖDSFALL</span><span class="sxs-lookup"><span data-stu-id="195ba-422">DEATH</span></span>          | <span data-ttu-id="195ba-423">Dödsfall</span><span class="sxs-lookup"><span data-stu-id="195ba-423">Death</span></span>            | <span data-ttu-id="195ba-424">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="195ba-424">Terminate worker</span></span>     |
| <span data-ttu-id="195ba-425">TJÄNSTLEDIGHET</span><span class="sxs-lookup"><span data-stu-id="195ba-425">LEAVEOFABSENCE</span></span> | <span data-ttu-id="195ba-426">Tjänstledighet</span><span class="sxs-lookup"><span data-stu-id="195ba-426">Leave of Absence</span></span> | <span data-ttu-id="195ba-427">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="195ba-427">Terminate worker</span></span>     |
| <span data-ttu-id="195ba-428">KONTRAKTSLUT</span><span class="sxs-lookup"><span data-stu-id="195ba-428">CONTRACTEND</span></span>    | <span data-ttu-id="195ba-429">Kontraktslut</span><span class="sxs-lookup"><span data-stu-id="195ba-429">End of Contract</span></span>  | <span data-ttu-id="195ba-430">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="195ba-430">Terminate worker</span></span>     |
| <span data-ttu-id="195ba-431">LÖNEÄNDRING</span><span class="sxs-lookup"><span data-stu-id="195ba-431">SALARYCHANGE</span></span>   | <span data-ttu-id="195ba-432">Löneändring</span><span class="sxs-lookup"><span data-stu-id="195ba-432">Change of Salary</span></span> | <span data-ttu-id="195ba-433">Kompensation</span><span class="sxs-lookup"><span data-stu-id="195ba-433">Compensation</span></span>         |

### <a name="marital-status"></a><span data-ttu-id="195ba-434">Civilstånd</span><span class="sxs-lookup"><span data-stu-id="195ba-434">Marital status</span></span>

<span data-ttu-id="195ba-435">Civilståndsvärden mappas till Dayforce och översätts på lämpligt sätt till giltiga värden i samband med integrering.</span><span class="sxs-lookup"><span data-stu-id="195ba-435">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="195ba-436">Följande tabell visar hur civilståndsvärden mappas till Dayforce.</span><span class="sxs-lookup"><span data-stu-id="195ba-436">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="195ba-437">Talent</span><span class="sxs-lookup"><span data-stu-id="195ba-437">Talent</span></span>                 | <span data-ttu-id="195ba-438">Dayforce</span><span class="sxs-lookup"><span data-stu-id="195ba-438">Dayforce</span></span>             |
|------------------------|----------------------|
| <span data-ttu-id="195ba-439">Gift</span><span class="sxs-lookup"><span data-stu-id="195ba-439">Married</span></span>                | <span data-ttu-id="195ba-440">Gift</span><span class="sxs-lookup"><span data-stu-id="195ba-440">Married</span></span>              |
| <span data-ttu-id="195ba-441">Ett</span><span class="sxs-lookup"><span data-stu-id="195ba-441">Single</span></span>                 | <span data-ttu-id="195ba-442">Ett</span><span class="sxs-lookup"><span data-stu-id="195ba-442">Single</span></span>               |
| <span data-ttu-id="195ba-443">Änka/änkling</span><span class="sxs-lookup"><span data-stu-id="195ba-443">Widowed</span></span>                | <span data-ttu-id="195ba-444">Änka/änkling</span><span class="sxs-lookup"><span data-stu-id="195ba-444">Widowed</span></span>              |
| <span data-ttu-id="195ba-445">Frånskild</span><span class="sxs-lookup"><span data-stu-id="195ba-445">Divorced</span></span>               | <span data-ttu-id="195ba-446">Frånskild</span><span class="sxs-lookup"><span data-stu-id="195ba-446">Divorced</span></span>             |
| <span data-ttu-id="195ba-447">Registrerat partnerskap</span><span class="sxs-lookup"><span data-stu-id="195ba-447">Registered Partnership</span></span> | <span data-ttu-id="195ba-448">Samboförhållande</span><span class="sxs-lookup"><span data-stu-id="195ba-448">Domestic Partnership</span></span> |
| <span data-ttu-id="195ba-449">Inga</span><span class="sxs-lookup"><span data-stu-id="195ba-449">None</span></span>                   | <span data-ttu-id="195ba-450">Inga</span><span class="sxs-lookup"><span data-stu-id="195ba-450">None</span></span>                 |
| <span data-ttu-id="195ba-451">Sambo</span><span class="sxs-lookup"><span data-stu-id="195ba-451">Cohabiting</span></span>             | <span data-ttu-id="195ba-452">Sambo</span><span class="sxs-lookup"><span data-stu-id="195ba-452">Cohabiting</span></span>           |

### <a name="gender"></a><span data-ttu-id="195ba-453">Kön</span><span class="sxs-lookup"><span data-stu-id="195ba-453">Gender</span></span>

<span data-ttu-id="195ba-454">Könsbeteckningar mappas till Dayforce och översätts på lämpligt sätt till giltiga värden i samband med integrering.</span><span class="sxs-lookup"><span data-stu-id="195ba-454">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="195ba-455">Följande tabell visar hur könsbeteckningar mappas till Dayforce.</span><span class="sxs-lookup"><span data-stu-id="195ba-455">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="195ba-456">Talent</span><span class="sxs-lookup"><span data-stu-id="195ba-456">Talent</span></span>       | <span data-ttu-id="195ba-457">Dayforce</span><span class="sxs-lookup"><span data-stu-id="195ba-457">Dayforce</span></span>        |
|--------------|-----------------|
| <span data-ttu-id="195ba-458">Man</span><span class="sxs-lookup"><span data-stu-id="195ba-458">Male</span></span>         | <span data-ttu-id="195ba-459">Man</span><span class="sxs-lookup"><span data-stu-id="195ba-459">Male</span></span>            |
| <span data-ttu-id="195ba-460">Kvinna</span><span class="sxs-lookup"><span data-stu-id="195ba-460">Female</span></span>       | <span data-ttu-id="195ba-461">Kvinna</span><span class="sxs-lookup"><span data-stu-id="195ba-461">Female</span></span>          |
| <span data-ttu-id="195ba-462">Icke-specifik</span><span class="sxs-lookup"><span data-stu-id="195ba-462">Non-specific</span></span> | <span data-ttu-id="195ba-463">*Stöds ej*</span><span class="sxs-lookup"><span data-stu-id="195ba-463">*Not supported*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="195ba-464">Inkomstkoder</span><span class="sxs-lookup"><span data-stu-id="195ba-464">Earning codes</span></span>

<span data-ttu-id="195ba-465">Inkomstkoder identifierar individuellt alla typer av arbetstagarintäkter.</span><span class="sxs-lookup"><span data-stu-id="195ba-465">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="195ba-466">Koderna omfattar flera olika parametrar som rör inkomster, till exempel redovisningsbestämmelser, skattelagar, rapporteringskrav och gross up-kapacitet.</span><span class="sxs-lookup"><span data-stu-id="195ba-466">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="195ba-467">Om en frekvens som inte stöds används tillämpas frekvensen **Varje lön** som standard för beräkningen.</span><span class="sxs-lookup"><span data-stu-id="195ba-467">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="195ba-468">Frekvenser som stöds</span><span class="sxs-lookup"><span data-stu-id="195ba-468">Supported frequencies</span></span>

- <span data-ttu-id="195ba-469">Allt</span><span class="sxs-lookup"><span data-stu-id="195ba-469">All</span></span>
- <span data-ttu-id="195ba-470">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="195ba-470">EVERYPAY</span></span>
- <span data-ttu-id="195ba-471">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="195ba-471">EACHPAYPERIOD</span></span>
- <span data-ttu-id="195ba-472">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="195ba-472">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="195ba-473">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="195ba-473">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="195ba-474">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="195ba-474">1OFMTH</span></span>
- <span data-ttu-id="195ba-475">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="195ba-475">LASTOFMTH</span></span>
- <span data-ttu-id="195ba-476">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="195ba-476">2OFMTH</span></span>
- <span data-ttu-id="195ba-477">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="195ba-477">3OFMTH</span></span>
- <span data-ttu-id="195ba-478">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="195ba-478">4OFMTH</span></span>
- <span data-ttu-id="195ba-479">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="195ba-479">5OFMTH</span></span>
- <span data-ttu-id="195ba-480">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="195ba-480">1N2OFMTH</span></span>
- <span data-ttu-id="195ba-481">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="195ba-481">3N4OFMTH</span></span>
- <span data-ttu-id="195ba-482">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="195ba-482">1N3OFMTH</span></span>
- <span data-ttu-id="195ba-483">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="195ba-483">1N4OFMTH</span></span>
- <span data-ttu-id="195ba-484">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="195ba-484">2N3OFMTH</span></span>
- <span data-ttu-id="195ba-485">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="195ba-485">2N4OFMTH</span></span>
- <span data-ttu-id="195ba-486">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="195ba-486">1N2N3OFMTH</span></span>
- <span data-ttu-id="195ba-487">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="195ba-487">1N2N4OFMTH</span></span>
- <span data-ttu-id="195ba-488">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="195ba-488">1N3N4OFMTH</span></span>
- <span data-ttu-id="195ba-489">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="195ba-489">2N3N4OFMTH</span></span>
- <span data-ttu-id="195ba-490">1N2N3N4OFMTH - 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="195ba-490">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="195ba-491">2N3N4N5OFMth - 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="195ba-491">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="195ba-492">1OFQTR - 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="195ba-492">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="195ba-493">LASTOFQTR – LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="195ba-493">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="195ba-494">LASTMTHOFQTR – LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="195ba-494">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="195ba-495">1OFYEAR - 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="195ba-495">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="195ba-496">LASTOFYEAR – LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="195ba-496">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="195ba-497">NOVNDECOFYEAR - NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="195ba-497">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="195ba-498">Adresser</span><span class="sxs-lookup"><span data-stu-id="195ba-498">Addresses</span></span>

<span data-ttu-id="195ba-499">Identifiering av specifika lands-/region-, delstats- och region(kommun)-koder kräver särskilda format som Dayforce och leverantörer i respektive land/region kan känna igen.</span><span class="sxs-lookup"><span data-stu-id="195ba-499">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="195ba-500">Även om formatet för städer är flexibelt måste varje stad associeras med en delstat.</span><span class="sxs-lookup"><span data-stu-id="195ba-500">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="195ba-501">Talent</span><span class="sxs-lookup"><span data-stu-id="195ba-501">Talent</span></span>          | <span data-ttu-id="195ba-502">Dayforce</span><span class="sxs-lookup"><span data-stu-id="195ba-502">Dayforce</span></span>              |
|-----------------|-----------------------|
| <span data-ttu-id="195ba-503">Land/region</span><span class="sxs-lookup"><span data-stu-id="195ba-503">Country/Region</span></span>  | <span data-ttu-id="195ba-504">Landskod</span><span class="sxs-lookup"><span data-stu-id="195ba-504">Country Code</span></span>          |
| <span data-ttu-id="195ba-505">Postnummer</span><span class="sxs-lookup"><span data-stu-id="195ba-505">Zip/Postal Code</span></span> | <span data-ttu-id="195ba-506">Postnummer</span><span class="sxs-lookup"><span data-stu-id="195ba-506">Postal Code</span></span>           |
| <span data-ttu-id="195ba-507">Stat</span><span class="sxs-lookup"><span data-stu-id="195ba-507">State</span></span>           | <span data-ttu-id="195ba-508">Delstatskod</span><span class="sxs-lookup"><span data-stu-id="195ba-508">State Code</span></span>            |
| <span data-ttu-id="195ba-509">Ort</span><span class="sxs-lookup"><span data-stu-id="195ba-509">City</span></span>            | <span data-ttu-id="195ba-510">Ort</span><span class="sxs-lookup"><span data-stu-id="195ba-510">City</span></span>                  |
| <span data-ttu-id="195ba-511">Län</span><span class="sxs-lookup"><span data-stu-id="195ba-511">County</span></span>          | <span data-ttu-id="195ba-512">Region (kommun)</span><span class="sxs-lookup"><span data-stu-id="195ba-512">County (Municipality)</span></span> |
| <span data-ttu-id="195ba-513">Gata</span><span class="sxs-lookup"><span data-stu-id="195ba-513">Street</span></span>          | <span data-ttu-id="195ba-514">Adressrad 1</span><span class="sxs-lookup"><span data-stu-id="195ba-514">Address Line 1</span></span>        |

### <a name="tax-regions"></a><span data-ttu-id="195ba-515">Skatteregioner</span><span class="sxs-lookup"><span data-stu-id="195ba-515">Tax regions</span></span>

<span data-ttu-id="195ba-516">Skatteregioner används för att bestämma vilken skattesats som ska användas vid lönegenerering.</span><span class="sxs-lookup"><span data-stu-id="195ba-516">Tax regions are used to determine the appropriate tax that should be applied during payroll generation.</span></span> <span data-ttu-id="195ba-517">Skatteregioner mappas till Dayforce som platsadresser.</span><span class="sxs-lookup"><span data-stu-id="195ba-517">Tax regions are mapped to Dayforce as location addresses.</span></span> <span data-ttu-id="195ba-518">Förvald skatteregion måste associeras med medarbetarens aktiva befattning.</span><span class="sxs-lookup"><span data-stu-id="195ba-518">The default tax region must be associated with the worker's active position.</span></span> 

- <span data-ttu-id="195ba-519">Skatteregion (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="195ba-519">Tax region (required)</span></span>
- <span data-ttu-id="195ba-520">Land/region (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="195ba-520">Country/Region (required)</span></span>
- <span data-ttu-id="195ba-521">Delstat (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="195ba-521">State (required)</span></span>
- <span data-ttu-id="195ba-522">Län</span><span class="sxs-lookup"><span data-stu-id="195ba-522">County</span></span> 
- <span data-ttu-id="195ba-523">Stad (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="195ba-523">City (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-mexico"></a><span data-ttu-id="195ba-524">Konfigurera dina data för att generera lön i Mexiko</span><span class="sxs-lookup"><span data-stu-id="195ba-524">Configure your data to generate payroll in Mexico</span></span>

<span data-ttu-id="195ba-525">Om du genererar lön för medarbetare i Mexiko måste följande element konfigureras:</span><span class="sxs-lookup"><span data-stu-id="195ba-525">If you're generating pay for employees in Mexico, the following elements must be configured:</span></span>

- <span data-ttu-id="195ba-526">Avdelningar är obligatoriska vid befattningarna:</span><span class="sxs-lookup"><span data-stu-id="195ba-526">Departments are required on positions.</span></span>
- <span data-ttu-id="195ba-527">Kostnadsställen måste ställas in som ekonomiska dimensioner och måste vara det första elementet i standardsträngen för ekonomisk dimension.</span><span class="sxs-lookup"><span data-stu-id="195ba-527">Cost centers must be set as financial dimensions and must be the first element in the Default Financial Dimension string.</span></span>

### <a name="job-types"></a><span data-ttu-id="195ba-528">Jobbtyper</span><span class="sxs-lookup"><span data-stu-id="195ba-528">Job types</span></span>

<span data-ttu-id="195ba-529">Jobbtyper används för att gruppera liknande jobb i kategorier.</span><span class="sxs-lookup"><span data-stu-id="195ba-529">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="195ba-530">Jobbtyper krävs för att bearbeta löner i Mexiko.</span><span class="sxs-lookup"><span data-stu-id="195ba-530">Job types are required in order to process payroll in Mexico.</span></span> <span data-ttu-id="195ba-531">Några exempel på jobbtyper är heltid och deltid, eller fast lön och timpenning.</span><span class="sxs-lookup"><span data-stu-id="195ba-531">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="195ba-532">Jobbtyper mappas till Dayforce som lönetyper som anger huruvida en anställd arbetar per timme eller har fast lön.</span><span class="sxs-lookup"><span data-stu-id="195ba-532">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="195ba-533">Följande jobbtyper och beskrivningar krävs.</span><span class="sxs-lookup"><span data-stu-id="195ba-533">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="195ba-534">Jobbtyp</span><span class="sxs-lookup"><span data-stu-id="195ba-534">Job type</span></span>   | <span data-ttu-id="195ba-535">beskrivning</span><span class="sxs-lookup"><span data-stu-id="195ba-535">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="195ba-536">Varje timme</span><span class="sxs-lookup"><span data-stu-id="195ba-536">Hourly</span></span>     | <span data-ttu-id="195ba-537">MX Varje timme</span><span class="sxs-lookup"><span data-stu-id="195ba-537">MX Hourly</span></span>   |
| <span data-ttu-id="195ba-538">Fast lön</span><span class="sxs-lookup"><span data-stu-id="195ba-538">Salaried</span></span>   | <span data-ttu-id="195ba-539">MX Fast lön</span><span class="sxs-lookup"><span data-stu-id="195ba-539">MX Salaried</span></span> |

### <a name="position-types"></a><span data-ttu-id="195ba-540">Befattningstyper</span><span class="sxs-lookup"><span data-stu-id="195ba-540">Position types</span></span> 

<span data-ttu-id="195ba-541">Du kan använda befattningstyper för att beskriva huruvida befattningen är på heltid, deltid eller annat.</span><span class="sxs-lookup"><span data-stu-id="195ba-541">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="195ba-542">Befattningstyper mappas till Dayforce som löneklasser som anger huruvida en anställd arbetar heltid eller deltid.</span><span class="sxs-lookup"><span data-stu-id="195ba-542">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="195ba-543">Följande befattningstyper och beskrivningar krävs.</span><span class="sxs-lookup"><span data-stu-id="195ba-543">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="195ba-544">Befattningstyp</span><span class="sxs-lookup"><span data-stu-id="195ba-544">Position type</span></span>   | <span data-ttu-id="195ba-545">beskrivning</span><span class="sxs-lookup"><span data-stu-id="195ba-545">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="195ba-546">Heltid</span><span class="sxs-lookup"><span data-stu-id="195ba-546">Full-time</span></span>       | <span data-ttu-id="195ba-547">Heltidsanställd</span><span class="sxs-lookup"><span data-stu-id="195ba-547">Full time employee</span></span> |
| <span data-ttu-id="195ba-548">Deltid</span><span class="sxs-lookup"><span data-stu-id="195ba-548">Part-time</span></span>       | <span data-ttu-id="195ba-549">Deltidsanställd</span><span class="sxs-lookup"><span data-stu-id="195ba-549">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="195ba-550">Orsakskoder</span><span class="sxs-lookup"><span data-stu-id="195ba-550">Reason codes</span></span>

<span data-ttu-id="195ba-551">Orsakskoder innehåller information om statusen för en medarbetare.</span><span class="sxs-lookup"><span data-stu-id="195ba-551">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="195ba-552">Orsakskoder mappas till Dayforce som statusanledningar som anger orsaken till ändringar i en medarbetares befattning eller anställningsstatus.</span><span class="sxs-lookup"><span data-stu-id="195ba-552">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="195ba-553">Följande orsakskoder och -beskrivningar krävs.</span><span class="sxs-lookup"><span data-stu-id="195ba-553">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="195ba-554">Orsakskod</span><span class="sxs-lookup"><span data-stu-id="195ba-554">Reason code</span></span>            | <span data-ttu-id="195ba-555">beskrivning</span><span class="sxs-lookup"><span data-stu-id="195ba-555">Description</span></span>                    | <span data-ttu-id="195ba-556">Tillämpliga scenarier</span><span class="sxs-lookup"><span data-stu-id="195ba-556">Applicable scenarios</span></span> |
|------------------------|--------------------------------|----------------------|
| <span data-ttu-id="195ba-557">DEPARTUREBEFOREPAYMENT</span><span class="sxs-lookup"><span data-stu-id="195ba-557">DEPARTUREBEFOREPAYMENT</span></span> | <span data-ttu-id="195ba-558">Avgick före första lön</span><span class="sxs-lookup"><span data-stu-id="195ba-558">Departure before first payroll</span></span> | <span data-ttu-id="195ba-559">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="195ba-559">Terminate worker</span></span>     |
| <span data-ttu-id="195ba-560">EGEN UPPSÄGNING</span><span class="sxs-lookup"><span data-stu-id="195ba-560">RESIGNATION</span></span>            | <span data-ttu-id="195ba-561">Egen uppsägning</span><span class="sxs-lookup"><span data-stu-id="195ba-561">Resignation</span></span>                    | <span data-ttu-id="195ba-562">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="195ba-562">Terminate worker</span></span>     |
| <span data-ttu-id="195ba-563">PENSION</span><span class="sxs-lookup"><span data-stu-id="195ba-563">PENSION</span></span>                | <span data-ttu-id="195ba-564">Pension</span><span class="sxs-lookup"><span data-stu-id="195ba-564">Pension</span></span>                        | <span data-ttu-id="195ba-565">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="195ba-565">Terminate worker</span></span>     |
| <span data-ttu-id="195ba-566">UPPSÄGNING</span><span class="sxs-lookup"><span data-stu-id="195ba-566">TERMINATION</span></span>            | <span data-ttu-id="195ba-567">Uppsägning</span><span class="sxs-lookup"><span data-stu-id="195ba-567">Termination</span></span>                    | <span data-ttu-id="195ba-568">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="195ba-568">Terminate worker</span></span>     |
| <span data-ttu-id="195ba-569">PENSION</span><span class="sxs-lookup"><span data-stu-id="195ba-569">RETIREMENT</span></span>             | <span data-ttu-id="195ba-570">Pension</span><span class="sxs-lookup"><span data-stu-id="195ba-570">Retirement</span></span>                     | <span data-ttu-id="195ba-571">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="195ba-571">Terminate worker</span></span>     |
| <span data-ttu-id="195ba-572">FRÅNVARANDE</span><span class="sxs-lookup"><span data-stu-id="195ba-572">ABSENTEE</span></span>               | <span data-ttu-id="195ba-573">Frånvarande</span><span class="sxs-lookup"><span data-stu-id="195ba-573">Absentee</span></span>                       | <span data-ttu-id="195ba-574">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="195ba-574">Terminate worker</span></span>     |
| <span data-ttu-id="195ba-575">ÖVRIGT</span><span class="sxs-lookup"><span data-stu-id="195ba-575">OTHER</span></span>                  | <span data-ttu-id="195ba-576">Andra orsaker</span><span class="sxs-lookup"><span data-stu-id="195ba-576">Other Reasons</span></span>                  | <span data-ttu-id="195ba-577">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="195ba-577">Terminate worker</span></span>     |
| <span data-ttu-id="195ba-578">AVSLUT</span><span class="sxs-lookup"><span data-stu-id="195ba-578">CLOSURE</span></span>                | <span data-ttu-id="195ba-579">Verksamheten nedlagd</span><span class="sxs-lookup"><span data-stu-id="195ba-579">Business Closure</span></span>               | <span data-ttu-id="195ba-580">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="195ba-580">Terminate worker</span></span>     |
| <span data-ttu-id="195ba-581">DÖDSFALL</span><span class="sxs-lookup"><span data-stu-id="195ba-581">DEATH</span></span>                  | <span data-ttu-id="195ba-582">Dödsfall</span><span class="sxs-lookup"><span data-stu-id="195ba-582">Death</span></span>                          | <span data-ttu-id="195ba-583">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="195ba-583">Terminate worker</span></span>     |
| <span data-ttu-id="195ba-584">TJÄNSTLEDIGHET</span><span class="sxs-lookup"><span data-stu-id="195ba-584">LEAVEOFABSENCE</span></span>         | <span data-ttu-id="195ba-585">Tjänstledighet</span><span class="sxs-lookup"><span data-stu-id="195ba-585">Leave of Absence</span></span>               | <span data-ttu-id="195ba-586">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="195ba-586">Terminate worker</span></span>     |
| <span data-ttu-id="195ba-587">KONTRAKTSLUT</span><span class="sxs-lookup"><span data-stu-id="195ba-587">CONTRACTEND</span></span>            | <span data-ttu-id="195ba-588">Kontraktslut</span><span class="sxs-lookup"><span data-stu-id="195ba-588">End of Contract</span></span>                | <span data-ttu-id="195ba-589">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="195ba-589">Terminate worker</span></span>     |
| <span data-ttu-id="195ba-590">LÖNEÄNDRING</span><span class="sxs-lookup"><span data-stu-id="195ba-590">SALARYCHANGE</span></span>           | <span data-ttu-id="195ba-591">Löneändring</span><span class="sxs-lookup"><span data-stu-id="195ba-591">Change of Salary</span></span>               | <span data-ttu-id="195ba-592">Kompensation</span><span class="sxs-lookup"><span data-stu-id="195ba-592">Compensation</span></span>         |

### <a name="terms-of-employment"></a><span data-ttu-id="195ba-593">Anställningsvillkor</span><span class="sxs-lookup"><span data-stu-id="195ba-593">Terms of employment</span></span>

<span data-ttu-id="195ba-594">Anställningsvillkor används för att skapa kategorier av anställningsvillkor.</span><span class="sxs-lookup"><span data-stu-id="195ba-594">Terms of employment are used to create categories of employment terms.</span></span> <span data-ttu-id="195ba-595">Villkoren mappas till Dayforce som indikatorvärden för anställning.</span><span class="sxs-lookup"><span data-stu-id="195ba-595">The terms are mapped to Dayforce as employment indicator values.</span></span>

<span data-ttu-id="195ba-596">Följande anställningsvillkor samt beskrivningar krävs.</span><span class="sxs-lookup"><span data-stu-id="195ba-596">The following terms of employment and descriptions are required.</span></span>

| <span data-ttu-id="195ba-597">Anställningsvillkor</span><span class="sxs-lookup"><span data-stu-id="195ba-597">Terms of employment</span></span>   | <span data-ttu-id="195ba-598">beskrivning</span><span class="sxs-lookup"><span data-stu-id="195ba-598">Description</span></span> |
|-----------------------|-------------|
| <span data-ttu-id="195ba-599">Vanligt</span><span class="sxs-lookup"><span data-stu-id="195ba-599">Regular</span></span>               | <span data-ttu-id="195ba-600">Vanligt</span><span class="sxs-lookup"><span data-stu-id="195ba-600">Regular</span></span>     |
| <span data-ttu-id="195ba-601">Direkt</span><span class="sxs-lookup"><span data-stu-id="195ba-601">Direct</span></span>                | <span data-ttu-id="195ba-602">Direkt</span><span class="sxs-lookup"><span data-stu-id="195ba-602">Direct</span></span>      |
| <span data-ttu-id="195ba-603">Praktik</span><span class="sxs-lookup"><span data-stu-id="195ba-603">Internship</span></span>            | <span data-ttu-id="195ba-604">Praktik</span><span class="sxs-lookup"><span data-stu-id="195ba-604">Internship</span></span>  |
| <span data-ttu-id="195ba-605">Permanent</span><span class="sxs-lookup"><span data-stu-id="195ba-605">Permanent</span></span>             | <span data-ttu-id="195ba-606">Permanent</span><span class="sxs-lookup"><span data-stu-id="195ba-606">Permanent</span></span>   |

### <a name="marital-status"></a><span data-ttu-id="195ba-607">Civilstånd</span><span class="sxs-lookup"><span data-stu-id="195ba-607">Marital status</span></span>

<span data-ttu-id="195ba-608">Civilståndsvärden mappas till Dayforce och översätts på lämpligt sätt till giltiga värden i samband med integrering.</span><span class="sxs-lookup"><span data-stu-id="195ba-608">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="195ba-609">Följande tabell visar hur civilståndsvärden mappas till Dayforce.</span><span class="sxs-lookup"><span data-stu-id="195ba-609">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="195ba-610">Talent</span><span class="sxs-lookup"><span data-stu-id="195ba-610">Talent</span></span>                 | <span data-ttu-id="195ba-611">Dayforce</span><span class="sxs-lookup"><span data-stu-id="195ba-611">Dayforce</span></span>                  |
|------------------------|---------------------------|
| <span data-ttu-id="195ba-612">Gift</span><span class="sxs-lookup"><span data-stu-id="195ba-612">Married</span></span>                | <span data-ttu-id="195ba-613">Gift</span><span class="sxs-lookup"><span data-stu-id="195ba-613">Married</span></span>                   |
| <span data-ttu-id="195ba-614">Ett</span><span class="sxs-lookup"><span data-stu-id="195ba-614">Single</span></span>                 | <span data-ttu-id="195ba-615">Ett</span><span class="sxs-lookup"><span data-stu-id="195ba-615">Single</span></span>                    |
| <span data-ttu-id="195ba-616">Änka/änkling</span><span class="sxs-lookup"><span data-stu-id="195ba-616">Widowed</span></span>                | <span data-ttu-id="195ba-617">Änka/änkling</span><span class="sxs-lookup"><span data-stu-id="195ba-617">Widowed</span></span>                   |
| <span data-ttu-id="195ba-618">Frånskild</span><span class="sxs-lookup"><span data-stu-id="195ba-618">Divorced</span></span>               | <span data-ttu-id="195ba-619">Frånskild</span><span class="sxs-lookup"><span data-stu-id="195ba-619">Divorced</span></span>                  |
| <span data-ttu-id="195ba-620">Registrerat partnerskap</span><span class="sxs-lookup"><span data-stu-id="195ba-620">Registered Partnership</span></span> | <span data-ttu-id="195ba-621">Samboförhållande</span><span class="sxs-lookup"><span data-stu-id="195ba-621">Domestic Partnership</span></span>      |
| <span data-ttu-id="195ba-622">Inga</span><span class="sxs-lookup"><span data-stu-id="195ba-622">None</span></span>                   | <span data-ttu-id="195ba-623">*Stöds inte i Mexiko*</span><span class="sxs-lookup"><span data-stu-id="195ba-623">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="195ba-624">Sambo</span><span class="sxs-lookup"><span data-stu-id="195ba-624">Cohabiting</span></span>             | <span data-ttu-id="195ba-625">*Stöds inte i Mexiko*</span><span class="sxs-lookup"><span data-stu-id="195ba-625">*Not supported by Mexico*</span></span> |

### <a name="gender"></a><span data-ttu-id="195ba-626">Kön</span><span class="sxs-lookup"><span data-stu-id="195ba-626">Gender</span></span>

<span data-ttu-id="195ba-627">Könsbeteckningar mappas till Dayforce och översätts på lämpligt sätt till giltiga värden i samband med integrering.</span><span class="sxs-lookup"><span data-stu-id="195ba-627">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="195ba-628">Följande tabell visar hur könsbeteckningar mappas till Dayforce.</span><span class="sxs-lookup"><span data-stu-id="195ba-628">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="195ba-629">Talent</span><span class="sxs-lookup"><span data-stu-id="195ba-629">Talent</span></span>       | <span data-ttu-id="195ba-630">Dayforce</span><span class="sxs-lookup"><span data-stu-id="195ba-630">Dayforce</span></span>                  |
|--------------|---------------------------|
| <span data-ttu-id="195ba-631">Man</span><span class="sxs-lookup"><span data-stu-id="195ba-631">Male</span></span>         | <span data-ttu-id="195ba-632">Man</span><span class="sxs-lookup"><span data-stu-id="195ba-632">Male</span></span>                      |
| <span data-ttu-id="195ba-633">Kvinna</span><span class="sxs-lookup"><span data-stu-id="195ba-633">Female</span></span>       | <span data-ttu-id="195ba-634">Kvinna</span><span class="sxs-lookup"><span data-stu-id="195ba-634">Female</span></span>                    |
| <span data-ttu-id="195ba-635">Icke-specifik</span><span class="sxs-lookup"><span data-stu-id="195ba-635">Non-specific</span></span> | <span data-ttu-id="195ba-636">*Stöds inte i Mexiko*</span><span class="sxs-lookup"><span data-stu-id="195ba-636">*Not supported by Mexico*</span></span> |

### <a name="payment-method"></a><span data-ttu-id="195ba-637">Betalningsmetod</span><span class="sxs-lookup"><span data-stu-id="195ba-637">Payment method</span></span>

<span data-ttu-id="195ba-638">Betalningsmetoder ger medarbetare och företag ett sätt att beskriva hur medarbetaren ska betalas.</span><span class="sxs-lookup"><span data-stu-id="195ba-638">Payment methods give the employee and the company a way to describe how employees will be paid.</span></span> <span data-ttu-id="195ba-639">Betalningsmetoder mappas till Dayforce och översätts på lämpligt sätt till giltiga värden i samband med integrering.</span><span class="sxs-lookup"><span data-stu-id="195ba-639">Payment methods are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="195ba-640">Följande tabell visar hur betalningsmetoder mappas till Dayforce.</span><span class="sxs-lookup"><span data-stu-id="195ba-640">The following table shows how payment methods are mapped to Dayforce.</span></span>

| <span data-ttu-id="195ba-641">Talent</span><span class="sxs-lookup"><span data-stu-id="195ba-641">Talent</span></span>             | <span data-ttu-id="195ba-642">Dayforce</span><span class="sxs-lookup"><span data-stu-id="195ba-642">Dayforce</span></span>                  |
|--------------------|---------------------------|
| <span data-ttu-id="195ba-643">Kontant</span><span class="sxs-lookup"><span data-stu-id="195ba-643">Cash</span></span>               | <span data-ttu-id="195ba-644">Kontant</span><span class="sxs-lookup"><span data-stu-id="195ba-644">Cash</span></span>                      |
| <span data-ttu-id="195ba-645">Elektronisk betalning</span><span class="sxs-lookup"><span data-stu-id="195ba-645">Electronic Payment</span></span> | <span data-ttu-id="195ba-646">Överför</span><span class="sxs-lookup"><span data-stu-id="195ba-646">Transfer</span></span>                  |
| <span data-ttu-id="195ba-647">Check</span><span class="sxs-lookup"><span data-stu-id="195ba-647">Check</span></span>              | <span data-ttu-id="195ba-648">Check</span><span class="sxs-lookup"><span data-stu-id="195ba-648">Cheque</span></span>                    |
| <span data-ttu-id="195ba-649">Bankutdrag</span><span class="sxs-lookup"><span data-stu-id="195ba-649">Bank Draft</span></span>         | <span data-ttu-id="195ba-650">*Stöds inte i Mexiko*</span><span class="sxs-lookup"><span data-stu-id="195ba-650">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="195ba-651">Annat</span><span class="sxs-lookup"><span data-stu-id="195ba-651">Other</span></span>              | <span data-ttu-id="195ba-652">*Stöds inte i Mexiko*</span><span class="sxs-lookup"><span data-stu-id="195ba-652">*Not supported by Mexico*</span></span> |

### <a name="bank-account-type"></a><span data-ttu-id="195ba-653">Bankkontotyp</span><span class="sxs-lookup"><span data-stu-id="195ba-653">Bank account type</span></span>

<span data-ttu-id="195ba-654">Bankkontotyper används för elektroniska betalningar till medarbetare.</span><span class="sxs-lookup"><span data-stu-id="195ba-654">Bank account types are used for electronic payments to employees.</span></span> <span data-ttu-id="195ba-655">Bankkontotyper mappas till Dayforce som kontoinformation för överföringar.</span><span class="sxs-lookup"><span data-stu-id="195ba-655">Bank account types are mapped to Dayforce as transfer account information.</span></span> <span data-ttu-id="195ba-656">Bankkontotyper översätts på lämpligt till giltiga värden i samband med integrering.</span><span class="sxs-lookup"><span data-stu-id="195ba-656">The bank account types are translated, as appropriate, to the accepted values upon integration.</span></span>

| <span data-ttu-id="195ba-657">Talent</span><span class="sxs-lookup"><span data-stu-id="195ba-657">Talent</span></span>            | <span data-ttu-id="195ba-658">Dayforce</span><span class="sxs-lookup"><span data-stu-id="195ba-658">Dayforce</span></span>                  |
|-------------------|---------------------------|
| <span data-ttu-id="195ba-659">Checkkonto</span><span class="sxs-lookup"><span data-stu-id="195ba-659">Checking Account</span></span>  | <span data-ttu-id="195ba-660">Checkkonto</span><span class="sxs-lookup"><span data-stu-id="195ba-660">CheckingAccount</span></span>           |
| <span data-ttu-id="195ba-661">Lönekonto</span><span class="sxs-lookup"><span data-stu-id="195ba-661">Payroll Account</span></span>   | <span data-ttu-id="195ba-662">Lönekonto</span><span class="sxs-lookup"><span data-stu-id="195ba-662">PayrollAccount</span></span>            |
| <span data-ttu-id="195ba-663">Sparkonto</span><span class="sxs-lookup"><span data-stu-id="195ba-663">Savings Account</span></span>   | <span data-ttu-id="195ba-664">*Stöds inte i Mexiko*</span><span class="sxs-lookup"><span data-stu-id="195ba-664">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="195ba-665">BankGirot-konto</span><span class="sxs-lookup"><span data-stu-id="195ba-665">BankGirot account</span></span> | <span data-ttu-id="195ba-666">*Stöds inte i Mexiko*</span><span class="sxs-lookup"><span data-stu-id="195ba-666">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="195ba-667">PlusGirot-konto</span><span class="sxs-lookup"><span data-stu-id="195ba-667">PlusGirot account</span></span> | <span data-ttu-id="195ba-668">*Stöds inte i Mexiko*</span><span class="sxs-lookup"><span data-stu-id="195ba-668">*Not supported by Mexico*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="195ba-669">Inkomstkoder</span><span class="sxs-lookup"><span data-stu-id="195ba-669">Earning codes</span></span>

<span data-ttu-id="195ba-670">Inkomstkoder identifierar individuellt alla typer av arbetstagarintäkter.</span><span class="sxs-lookup"><span data-stu-id="195ba-670">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="195ba-671">Koderna omfattar flera olika parametrar som rör inkomster, till exempel redovisningsbestämmelser, skattelagar, rapporteringskrav och gross up-kapacitet.</span><span class="sxs-lookup"><span data-stu-id="195ba-671">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="195ba-672">Om en frekvens som inte stöds används tillämpas frekvensen **Varje lön** som standard för beräkningen.</span><span class="sxs-lookup"><span data-stu-id="195ba-672">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="195ba-673">Frekvenser som stöds</span><span class="sxs-lookup"><span data-stu-id="195ba-673">Supported frequencies</span></span>

- <span data-ttu-id="195ba-674">Allt</span><span class="sxs-lookup"><span data-stu-id="195ba-674">All</span></span>
- <span data-ttu-id="195ba-675">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="195ba-675">EVERYPAY</span></span>
- <span data-ttu-id="195ba-676">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="195ba-676">EACHPAYPERIOD</span></span>
- <span data-ttu-id="195ba-677">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="195ba-677">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="195ba-678">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="195ba-678">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="195ba-679">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="195ba-679">1OFMTH</span></span>
- <span data-ttu-id="195ba-680">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="195ba-680">LASTOFMTH</span></span>
- <span data-ttu-id="195ba-681">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="195ba-681">2OFMTH</span></span>
- <span data-ttu-id="195ba-682">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="195ba-682">3OFMTH</span></span>
- <span data-ttu-id="195ba-683">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="195ba-683">4OFMTH</span></span>
- <span data-ttu-id="195ba-684">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="195ba-684">5OFMTH</span></span>
- <span data-ttu-id="195ba-685">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="195ba-685">1N2OFMTH</span></span>
- <span data-ttu-id="195ba-686">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="195ba-686">3N4OFMTH</span></span>
- <span data-ttu-id="195ba-687">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="195ba-687">1N3OFMTH</span></span>
- <span data-ttu-id="195ba-688">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="195ba-688">1N4OFMTH</span></span>
- <span data-ttu-id="195ba-689">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="195ba-689">2N3OFMTH</span></span>
- <span data-ttu-id="195ba-690">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="195ba-690">2N4OFMTH</span></span>
- <span data-ttu-id="195ba-691">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="195ba-691">1N2N3OFMTH</span></span>
- <span data-ttu-id="195ba-692">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="195ba-692">1N2N4OFMTH</span></span>
- <span data-ttu-id="195ba-693">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="195ba-693">1N3N4OFMTH</span></span>
- <span data-ttu-id="195ba-694">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="195ba-694">2N3N4OFMTH</span></span>
- <span data-ttu-id="195ba-695">1N2N3N4OFMTH - 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="195ba-695">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="195ba-696">2N3N4N5OFMth - 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="195ba-696">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="195ba-697">1OFQTR - 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="195ba-697">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="195ba-698">LASTOFQTR – LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="195ba-698">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="195ba-699">LASTMTHOFQTR – LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="195ba-699">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="195ba-700">1OFYEAR - 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="195ba-700">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="195ba-701">LASTOFYEAR – LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="195ba-701">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="195ba-702">NOVNDECOFYEAR - NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="195ba-702">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="195ba-703">Adresser</span><span class="sxs-lookup"><span data-stu-id="195ba-703">Addresses</span></span>

<span data-ttu-id="195ba-704">Identifiering av specifika lands-/region-, delstats- och region(kommun)-koder kräver särskilda format som Dayforce och leverantörer i respektive land/region kan känna igen.</span><span class="sxs-lookup"><span data-stu-id="195ba-704">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="195ba-705">Även om formatet för städer är flexibelt måste varje stad associeras med en delstat.</span><span class="sxs-lookup"><span data-stu-id="195ba-705">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="195ba-706">Talent</span><span class="sxs-lookup"><span data-stu-id="195ba-706">Talent</span></span>              | <span data-ttu-id="195ba-707">Dayforce</span><span class="sxs-lookup"><span data-stu-id="195ba-707">Dayforce</span></span>              |
|---------------------|-----------------------|
| <span data-ttu-id="195ba-708">Land/region</span><span class="sxs-lookup"><span data-stu-id="195ba-708">Country/Region</span></span>      | <span data-ttu-id="195ba-709">Landskod</span><span class="sxs-lookup"><span data-stu-id="195ba-709">Country Code</span></span>          |
| <span data-ttu-id="195ba-710">Postnummer</span><span class="sxs-lookup"><span data-stu-id="195ba-710">Zip/Postal Code</span></span>     | <span data-ttu-id="195ba-711">Postnummer</span><span class="sxs-lookup"><span data-stu-id="195ba-711">Postal Code</span></span>           |
| <span data-ttu-id="195ba-712">Stat</span><span class="sxs-lookup"><span data-stu-id="195ba-712">State</span></span>               | <span data-ttu-id="195ba-713">Delstatskod</span><span class="sxs-lookup"><span data-stu-id="195ba-713">State Code</span></span>            |
| <span data-ttu-id="195ba-714">Ort</span><span class="sxs-lookup"><span data-stu-id="195ba-714">City</span></span>                | <span data-ttu-id="195ba-715">Ort</span><span class="sxs-lookup"><span data-stu-id="195ba-715">City</span></span>                  |
| <span data-ttu-id="195ba-716">Län</span><span class="sxs-lookup"><span data-stu-id="195ba-716">County</span></span>              | <span data-ttu-id="195ba-717">Region (kommun)</span><span class="sxs-lookup"><span data-stu-id="195ba-717">County (Municipality)</span></span> |
| <span data-ttu-id="195ba-718">Gata</span><span class="sxs-lookup"><span data-stu-id="195ba-718">Street</span></span>              | <span data-ttu-id="195ba-719">Adressrad 1</span><span class="sxs-lookup"><span data-stu-id="195ba-719">Address Line 1</span></span>        |
| <span data-ttu-id="195ba-720">Gatunummer</span><span class="sxs-lookup"><span data-stu-id="195ba-720">Street Number</span></span>       | <span data-ttu-id="195ba-721">Adressrad 2</span><span class="sxs-lookup"><span data-stu-id="195ba-721">Address Line 2</span></span>        |
| <span data-ttu-id="195ba-722">Byggnadskomplement</span><span class="sxs-lookup"><span data-stu-id="195ba-722">Building Complement</span></span> | <span data-ttu-id="195ba-723">Adressrad 5</span><span class="sxs-lookup"><span data-stu-id="195ba-723">Address Line 5</span></span>        |

### <a name="passport-number"></a><span data-ttu-id="195ba-724">Passnummer</span><span class="sxs-lookup"><span data-stu-id="195ba-724">Passport number</span></span>

<span data-ttu-id="195ba-725">Medarbetare kan deklarera passinformation.</span><span class="sxs-lookup"><span data-stu-id="195ba-725">Employees can declare passport information.</span></span> <span data-ttu-id="195ba-726">Denna information bär ID-typen **Pass** och integreras i Dayforce som en del av medarbetarens Mexikospecifika information.</span><span class="sxs-lookup"><span data-stu-id="195ba-726">This information is of the **Passport** identification type and is integrated into Dayforce as part of an employee's Mexico-specific information.</span></span>

- <span data-ttu-id="195ba-727">Identifieringstyp = "Pass"</span><span class="sxs-lookup"><span data-stu-id="195ba-727">Identification Type = "Passport"</span></span>
- <span data-ttu-id="195ba-728">Utfärdat den</span><span class="sxs-lookup"><span data-stu-id="195ba-728">Issued Date</span></span>
- <span data-ttu-id="195ba-729">Utgångsdatum</span><span class="sxs-lookup"><span data-stu-id="195ba-729">Expiration Date</span></span>

<span data-ttu-id="195ba-730">Medarbetare kan deklarera flera ID-nummer med ID-typen **Pass**.</span><span class="sxs-lookup"><span data-stu-id="195ba-730">Employees can declare multiple identification numbers of the **Passport** identification type.</span></span> <span data-ttu-id="195ba-731">Endast den aktuella passposten integreras emellertid i Dayforce.</span><span class="sxs-lookup"><span data-stu-id="195ba-731">However, only the current active passport entry is integrated into Dayforce.</span></span> <span data-ttu-id="195ba-732">Om alla passposter har upphört att gälla kommer det pass som är utfärdat senast att integreras i Dayforce.</span><span class="sxs-lookup"><span data-stu-id="195ba-732">If all passport entries are expired, the passport that was most recently issued is integrated into Dayforce.</span></span>
