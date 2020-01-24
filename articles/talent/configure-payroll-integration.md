---
title: Konfigurera löneintegrering mellan Talent och Dayforce
description: Det här avsnittet förklarar hur du konfigurerar integrationen mellan Dynamics 365 Talent och Ceridian Dayforce så att du kan bearbeta en betalning.
author: andreabichsel
manager: AnnBe
ms.date: 06/24/2019
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
ms.openlocfilehash: 075b2bdfa08bb190f66b6d60074e1263feedcf70
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/06/2019
ms.locfileid: "2898552"
---
# <a name="configure-payroll-integration-between-talent-and-dayforce"></a><span data-ttu-id="78965-103">Konfigurera löneintegration mellan Talent och Dayforce</span><span class="sxs-lookup"><span data-stu-id="78965-103">Configure payroll integration between Talent and Dayforce</span></span>

<span data-ttu-id="78965-104">Integreringen mellan Microsoft Dynamics 365 Talent och Ceridian Dayforce är beroende av flera konfigurationssteg som beskrivs i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="78965-104">The integration between Microsoft Dynamics 365 Talent and Ceridian Dayforce relies on several configuration steps that are described in this topic.</span></span> <span data-ttu-id="78965-105">Du måste konfigurera integrationen i både Talent och Dayforce innan du kan bearbeta en betalning.</span><span class="sxs-lookup"><span data-stu-id="78965-105">You must configure the integration in both Talent and Dayforce before you can process a pay run.</span></span>

<span data-ttu-id="78965-106">När du använder tjänster som exempelvis Dayforce för att utföra betalningar måste du aktivera integration i Talent.</span><span class="sxs-lookup"><span data-stu-id="78965-106">When you use a service such as Dayforce to complete pay runs, you must enable the integration in Talent.</span></span> <span data-ttu-id="78965-107">Integrationen kräver specifika data från Talent.</span><span class="sxs-lookup"><span data-stu-id="78965-107">The integration requires specific data from Talent.</span></span> <span data-ttu-id="78965-108">Därför måste du kontrollera att data som är mappad till Dayforce konfigureras i Talent på ett sätt som stöder integrationen.</span><span class="sxs-lookup"><span data-stu-id="78965-108">Therefore, you must verify that data that is mapped to Dayforce is configured in Talent in a manner that supports the integration.</span></span> <span data-ttu-id="78965-109">Integrationen använder följande breda datakategorier:</span><span class="sxs-lookup"><span data-stu-id="78965-109">The integration uses the following broad categories of data:</span></span>

- <span data-ttu-id="78965-110">Personaldata</span><span class="sxs-lookup"><span data-stu-id="78965-110">Human resources data</span></span>
- <span data-ttu-id="78965-111">Kompensationsdata</span><span class="sxs-lookup"><span data-stu-id="78965-111">Compensation data</span></span>
- <span data-ttu-id="78965-112">Lönedata som till exempel lönecykler, betalningsperioder och inkomstkoder</span><span class="sxs-lookup"><span data-stu-id="78965-112">Payroll data, such as pay cycles, pay periods, and earning codes</span></span>
- <span data-ttu-id="78965-113">Medarbetardata</span><span class="sxs-lookup"><span data-stu-id="78965-113">Worker data</span></span>

<span data-ttu-id="78965-114">Det här avsnittet beskriver de steg som du måste följa för att aktivera integrationen.</span><span class="sxs-lookup"><span data-stu-id="78965-114">This topic describes the steps that you must follow to enable the integration.</span></span> <span data-ttu-id="78965-115">Här förklaras också de typer av data och den konfigurationsinformation som integrationen kräver.</span><span class="sxs-lookup"><span data-stu-id="78965-115">It also explains the types of data and the configuration details that the integration requires.</span></span>

## <a name="enable-the-integration"></a><span data-ttu-id="78965-116">Aktivera integrationen</span><span class="sxs-lookup"><span data-stu-id="78965-116">Enable the integration</span></span>

<span data-ttu-id="78965-117">Du måste aktivera integrationen i Talent och ange konfigurationsinformation för att ansluta till Dayforce.</span><span class="sxs-lookup"><span data-stu-id="78965-117">In Talent, you must turn on the integration and enter the configuration information to connect to Dayforce.</span></span> <span data-ttu-id="78965-118">Om du vill att den redovisningstransaktion som framställs ska importeras till Microsoft Dynamics 365 Finance måste du också skapa ett lagringskonto för Microsoft Azure och ange anslutningssträngen för Azure-lagring i Finance.</span><span class="sxs-lookup"><span data-stu-id="78965-118">If you want the general ledger transaction that is produced to be imported into Microsoft Dynamics 365 Finance, you must also set up a Microsoft Azure storage account and enter the Azure Storage connection string in Finance.</span></span>

<span data-ttu-id="78965-119">Följ dessa steg om du vill aktivera integration i Talent.</span><span class="sxs-lookup"><span data-stu-id="78965-119">To turn on the integration in Talent, follow these steps.</span></span>

1. <span data-ttu-id="78965-120">På sidan **Systemadministration** väljer du **Integrationskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="78965-120">On the **System administration** page, select **Integration configuration**.</span></span>
2. <span data-ttu-id="78965-121">Ange slutpunkten för filöverföringsprotokollet (FTP) och den säkra FTP-sökvägen.</span><span class="sxs-lookup"><span data-stu-id="78965-121">Enter the secure File Transfer Protocol (FTP) endpoint and the secure FTP folder path.</span></span>
3. <span data-ttu-id="78965-122">Ange användarnamn och lösenord för den användare som kommer att använda den säkra FTP-slutpunkten och mappsökvägen.</span><span class="sxs-lookup"><span data-stu-id="78965-122">Enter the user name and password of the user who will access the secure FTP endpoint and folder path.</span></span>
4. <span data-ttu-id="78965-123">Testa anslutningen efter behov samt ange alternativet **Aktivera integrering av löner** som **Ja**.</span><span class="sxs-lookup"><span data-stu-id="78965-123">Test the connection, as required, and set the **Enable payroll integration** option to **Yes**.</span></span>

<span data-ttu-id="78965-124">När integreringen aktiveras skapas dataexportpaket och filer, och frekvensen anges.</span><span class="sxs-lookup"><span data-stu-id="78965-124">When the integration is turned on, the data export package and files are created, and the frequency is set.</span></span> <span data-ttu-id="78965-125">Du kan ändra frekvensen efter behov.</span><span class="sxs-lookup"><span data-stu-id="78965-125">You can change this frequency as you require.</span></span>

<span data-ttu-id="78965-126">Mer information om Azure-lagringskonton och anslutningssträngar för Azure-lagring, se följande Azure-avsnitt:</span><span class="sxs-lookup"><span data-stu-id="78965-126">For more information about Azure storage accounts and Azure Storage connection strings, see the following Azure topics:</span></span>

- [<span data-ttu-id="78965-127">Om Azure-lagringskonton</span><span class="sxs-lookup"><span data-stu-id="78965-127">About Azure storage accounts</span></span>](https://docs.microsoft.com/azure/storage/common/storage-create-storage-account?toc=%2fazure%2fstorage%2ffiles%2ftoc.json)
- [<span data-ttu-id="78965-128">Konfigurera anslutningssträngar för Azure-lagring</span><span class="sxs-lookup"><span data-stu-id="78965-128">Configure Azure Storage connection strings</span></span>](https://docs.microsoft.com/azure/storage/common/storage-configure-connection-string)

### <a name="technical-details-when-payroll-integration-is-enabled"></a><span data-ttu-id="78965-129">Teknisk information när löneintegration har aktiverats</span><span class="sxs-lookup"><span data-stu-id="78965-129">Technical details when payroll integration is enabled</span></span>

<span data-ttu-id="78965-130">Att slå på löneintegration har två primära effekter:</span><span class="sxs-lookup"><span data-stu-id="78965-130">Turning on the payroll integration has two primary effects:</span></span>

- <span data-ttu-id="78965-131">Ett dataexportprojekt med namnet "Löneintegrationexport" skapas.</span><span class="sxs-lookup"><span data-stu-id="78965-131">A data export project named "Payroll integration export" is created.</span></span> <span data-ttu-id="78965-132">Det här projektet innehåller de entiteter och fält som krävs för löneintegration.</span><span class="sxs-lookup"><span data-stu-id="78965-132">This project contains the entities and fields required for the payroll integration.</span></span> <span data-ttu-id="78965-133">För att undersöka projekt, gå till **Systemadministration**, välj **Datahantering** och öppna dataprojekt från lista över projekt.</span><span class="sxs-lookup"><span data-stu-id="78965-133">To examine the project, go to **System administration**, select the **Data management** tile, and then open the data project from the list of projects.</span></span>
- <span data-ttu-id="78965-134">Det här batchjobbet kör dataexportprojektet, krypterar det resulterande datapaketet och överför datapaketfilen till den SFTP-slutpunkt som konfigurerats på skärmen **integrationskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="78965-134">This batch job executes the data export project, encrypts the resulting data package, and transfers the data package file to the SFTP endpoint configured on the **Integration configuration** screen.</span></span>

> [!NOTE]
> <span data-ttu-id="78965-135">Det datapaket som överförs till SFTP-slutpunkten krypteras med en nyckel som är unik för paketet.</span><span class="sxs-lookup"><span data-stu-id="78965-135">The data package transferred to the SFTP endpoint is encrypted using a key that is unique to the package.</span></span> <span data-ttu-id="78965-136">Nyckeln finns i ett Azure Key Vault som bara kan nås av Ceridian.</span><span class="sxs-lookup"><span data-stu-id="78965-136">The key is in an Azure Key Vault that is accessible only by Ceridian.</span></span> <span data-ttu-id="78965-137">Det går inte att dekryptera och undersöka innehållet i datapaketet.</span><span class="sxs-lookup"><span data-stu-id="78965-137">It is not possible to decrypt and examine the data package contents.</span></span> <span data-ttu-id="78965-138">Om du behöver undersöka innehållet i datapaketet, måste du exportera dataprojektet "Löneintegrationexport" manuellt, hämta det och sedan öppna det.</span><span class="sxs-lookup"><span data-stu-id="78965-138">If you need to examine the contents of the data package, you need to export the "Payroll integration export" data project manually, download it, and then open it.</span></span> <span data-ttu-id="78965-139">Manuell export använder inte kryptering eller överföring av paketet.</span><span class="sxs-lookup"><span data-stu-id="78965-139">Manual export will not apply encryption or transfer the package.</span></span>

## <a name="configure-your-data"></a><span data-ttu-id="78965-140">Konfigurera dina data</span><span class="sxs-lookup"><span data-stu-id="78965-140">Configure your data</span></span> 

<span data-ttu-id="78965-141">Du måste konfigurera personaldata för att bearbeta löner i Talent.</span><span class="sxs-lookup"><span data-stu-id="78965-141">To process payroll, you must configure human resource data in Talent.</span></span> <span data-ttu-id="78965-142">Du måste ställa in organisationsinformation, t.ex. jobb och befattningar samt förmåner och kompensationsinformation.</span><span class="sxs-lookup"><span data-stu-id="78965-142">You must set up organizational data, such as jobs and positions, together with benefits and compensation information.</span></span> <span data-ttu-id="78965-143">Denna information utgör den anställnings-, lön- och avdragsinformationen som krävs för att generera lön för medarbetare.</span><span class="sxs-lookup"><span data-stu-id="78965-143">This information provides the employment, pay, and deduction information that is required in order to generate employee pay.</span></span>

### <a name="human-resource-data"></a><span data-ttu-id="78965-144">Personaldata</span><span class="sxs-lookup"><span data-stu-id="78965-144">Human resource data</span></span>

#### <a name="benefits"></a><span data-ttu-id="78965-145">Förmåner</span><span class="sxs-lookup"><span data-stu-id="78965-145">Benefits</span></span> 

<span data-ttu-id="78965-146">Personal tillhandahåller verktyg som kan användas för att ställa in och underhålla förmåner, avdrag och kompensationsplaner för medarbetare som en organisation erbjuder eller bearbetar för sin personal.</span><span class="sxs-lookup"><span data-stu-id="78965-146">Human resources provides tools for the setup and maintenance of the benefits, deductions, and worker compensation plans that an organization offers or processes for its workers.</span></span>

<span data-ttu-id="78965-147">När du skapar förmåner, kom då ihåg följande data och konfigurationer som används i Dayforce.</span><span class="sxs-lookup"><span data-stu-id="78965-147">When you create benefits, keep in mind the following data and configurations that are used in Dayforce.</span></span>

##### <a name="benefit-plans"></a><span data-ttu-id="78965-148">Förmånsplaner</span><span class="sxs-lookup"><span data-stu-id="78965-148">Benefit plans</span></span>

- <span data-ttu-id="78965-149">Plan (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="78965-149">Plan (required)</span></span>
- <span data-ttu-id="78965-150">Typ (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="78965-150">Type (required)</span></span>
- <span data-ttu-id="78965-151">Effekt på lön (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="78965-151">Payroll impact (required)</span></span>
- <span data-ttu-id="78965-152">Återvinn restbetalningar</span><span class="sxs-lookup"><span data-stu-id="78965-152">Recover arrears</span></span>
- <span data-ttu-id="78965-153">Avdragsmetod</span><span class="sxs-lookup"><span data-stu-id="78965-153">Deduction method</span></span>
- <span data-ttu-id="78965-154">Avdragsprioritet</span><span class="sxs-lookup"><span data-stu-id="78965-154">Deduction priority</span></span>
- <span data-ttu-id="78965-155">Gränsperiod</span><span class="sxs-lookup"><span data-stu-id="78965-155">Limit period</span></span>
- <span data-ttu-id="78965-156">Begränsa belopp</span><span class="sxs-lookup"><span data-stu-id="78965-156">Limit amount</span></span>

##### <a name="benefits"></a><span data-ttu-id="78965-157">Förmåner</span><span class="sxs-lookup"><span data-stu-id="78965-157">Benefits</span></span>

- <span data-ttu-id="78965-158">Plan (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="78965-158">Plan (required)</span></span>
- <span data-ttu-id="78965-159">Typ (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="78965-159">Type (required)</span></span>
- <span data-ttu-id="78965-160">Tillval (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="78965-160">Option (required)</span></span>
- <span data-ttu-id="78965-161">Förmåns-ID (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="78965-161">Benefit ID (required)</span></span>
- <span data-ttu-id="78965-162">Frekvens</span><span class="sxs-lookup"><span data-stu-id="78965-162">Frequency</span></span>
- <span data-ttu-id="78965-163">Bas</span><span class="sxs-lookup"><span data-stu-id="78965-163">Basis</span></span>
- <span data-ttu-id="78965-164">Belopp eller tariff</span><span class="sxs-lookup"><span data-stu-id="78965-164">Amount or rate</span></span>
- <span data-ttu-id="78965-165">Inkomstkod</span><span class="sxs-lookup"><span data-stu-id="78965-165">Earning code</span></span>

##### <a name="supported-frequencies"></a><span data-ttu-id="78965-166">Frekvenser som stöds</span><span class="sxs-lookup"><span data-stu-id="78965-166">Supported frequencies</span></span> 

- <span data-ttu-id="78965-167">Varje vecka</span><span class="sxs-lookup"><span data-stu-id="78965-167">Weekly</span></span>
- <span data-ttu-id="78965-168">Varannan vecka</span><span class="sxs-lookup"><span data-stu-id="78965-168">Bi-weekly</span></span>
- <span data-ttu-id="78965-169">Var fjortonde dag</span><span class="sxs-lookup"><span data-stu-id="78965-169">Semi-monthly</span></span>
- <span data-ttu-id="78965-170">Månatlig</span><span class="sxs-lookup"><span data-stu-id="78965-170">Monthly</span></span>

##### <a name="supported-bases"></a><span data-ttu-id="78965-171">Databaser som stöds</span><span class="sxs-lookup"><span data-stu-id="78965-171">Supported bases</span></span> 

- <span data-ttu-id="78965-172">Fast belopp</span><span class="sxs-lookup"><span data-stu-id="78965-172">Fixed amount</span></span>
- <span data-ttu-id="78965-173">Procent av inkomst</span><span class="sxs-lookup"><span data-stu-id="78965-173">Percent of earnings</span></span>
- <span data-ttu-id="78965-174">Produktiva timmar</span><span class="sxs-lookup"><span data-stu-id="78965-174">Productive hours</span></span>

<span data-ttu-id="78965-175">Dayforce skapar följande avdrag baserat på den löneeffekt som definieras i förmånsplanen.</span><span class="sxs-lookup"><span data-stu-id="78965-175">Dayforce creates the following deductions, based on the payroll impact that is defined on the benefit plan.</span></span>

| <span data-ttu-id="78965-176">Val i Talent</span><span class="sxs-lookup"><span data-stu-id="78965-176">Selection in Talent</span></span>        | <span data-ttu-id="78965-177">Resultat i Dayforce</span><span class="sxs-lookup"><span data-stu-id="78965-177">Result in Dayforce</span></span>                            |
|----------------------------|-----------------------------------------------|
| <span data-ttu-id="78965-178">Inga</span><span class="sxs-lookup"><span data-stu-id="78965-178">None</span></span>                       | <span data-ttu-id="78965-179">Inget avdrag skapas.</span><span class="sxs-lookup"><span data-stu-id="78965-179">No deduction is created.</span></span>                      |
| <span data-ttu-id="78965-180">Endast avdrag</span><span class="sxs-lookup"><span data-stu-id="78965-180">Deduction only</span></span>             | <span data-ttu-id="78965-181">Löneavdrag för en medarbetare skapas.</span><span class="sxs-lookup"><span data-stu-id="78965-181">An employee deduction is created.</span></span>             |
| <span data-ttu-id="78965-182">Endast lönetillägg</span><span class="sxs-lookup"><span data-stu-id="78965-182">Contribution only</span></span>          | <span data-ttu-id="78965-183">Löneavdrag för en arbetsgivare skapas.</span><span class="sxs-lookup"><span data-stu-id="78965-183">An employer deduction is created.</span></span>             |
| <span data-ttu-id="78965-184">Avdrag och tillägg</span><span class="sxs-lookup"><span data-stu-id="78965-184">Deduction and contribution</span></span> | <span data-ttu-id="78965-185">Avdrag för medarbetare och arbetsgivare skapas.</span><span class="sxs-lookup"><span data-stu-id="78965-185">Employee and employer deductions are created.</span></span> |

<span data-ttu-id="78965-186">Mer information om hur du definierar och hanterar ett förmånsprogram finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="78965-186">For more information about how to define and manage a benefits program, see the following topics:</span></span>

- [<span data-ttu-id="78965-187">Utveckla ett förmånsprogram för medarbetare</span><span class="sxs-lookup"><span data-stu-id="78965-187">Deliver an employee benefits program</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/deliver-employee-benefits-program)
- [<span data-ttu-id="78965-188">Skapa en ny förmån</span><span class="sxs-lookup"><span data-stu-id="78965-188">Create a new benefit</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/create-new-benefit)
- [<span data-ttu-id="78965-189">Definiera förmånsberättiganderegler och policyer</span><span class="sxs-lookup"><span data-stu-id="78965-189">Define benefit eligibility rules and policies</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-benefit-eligibility-rules-policies)
- [<span data-ttu-id="78965-190">Registrera och ta bort förmåner för arbetare</span><span class="sxs-lookup"><span data-stu-id="78965-190">Enroll and remove benefits from workers</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-remove-benefits-workers)

#### <a name="compensation"></a><span data-ttu-id="78965-191">Kompensation</span><span class="sxs-lookup"><span data-stu-id="78965-191">Compensation</span></span> 

<span data-ttu-id="78965-192">Kompensationshantering används för att styra du utbetalningen av grundlön och belöningar.</span><span class="sxs-lookup"><span data-stu-id="78965-192">Compensation management is used to control the delivery of base pay and awards.</span></span> <span data-ttu-id="78965-193">En medarbetares fasta grundlön och merithöjningar kontrolleras genom fasta kompensationsplaner.</span><span class="sxs-lookup"><span data-stu-id="78965-193">An employee's fixed base pay and merit increases are controlled through fixed compensation plans.</span></span> <span data-ttu-id="78965-194">Betalningen av incitament, till exempel bonusar, resultatbelöningar, aktieoptioner och anslag och även engångsbelöningar kontrolleras genom variabla kompensationsplaner.</span><span class="sxs-lookup"><span data-stu-id="78965-194">The payment of incentive pay, such as bonus payments, performance awards, stock options, and grants, and also one-time awards, are controlled through variable compensation plans.</span></span>

<span data-ttu-id="78965-195">Dayforce använder kompensationsinformation för att beräkna en medarbetares tim- eller årliga betalning.</span><span class="sxs-lookup"><span data-stu-id="78965-195">Dayforce uses compensation information to calculate an employee's hourly or annual rate.</span></span> <span data-ttu-id="78965-196">Fasta kompensationsplaner och lönekonverteringar är obligatoriska.</span><span class="sxs-lookup"><span data-stu-id="78965-196">Fixed compensation plans and pay rate conversions are required.</span></span> <span data-ttu-id="78965-197">Medarbetarna måste vara anslutna till en fast kompensationsplan.</span><span class="sxs-lookup"><span data-stu-id="78965-197">Employees must be associated with a fixed compensation plan.</span></span>

<span data-ttu-id="78965-198">Mer information om att kompensationsplaner finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="78965-198">For more information about compensation plans, see the following topics:</span></span>

- [<span data-ttu-id="78965-199">Skapa planer för fast kompensation</span><span class="sxs-lookup"><span data-stu-id="78965-199">Create fixed compensation plans</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/create-fixed-compensation-plans)
- [<span data-ttu-id="78965-200">Skapa planer för variabel kompensation</span><span class="sxs-lookup"><span data-stu-id="78965-200">Create variable compensation plans</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/create-variable-compensation-plans)
- [<span data-ttu-id="78965-201">Utveckla struktur och planer för lön/kompensation</span><span class="sxs-lookup"><span data-stu-id="78965-201">Develop salary/compensation structure and plans</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/develop-salary-compensation-structure-plan)
- [<span data-ttu-id="78965-202">Bearbeta kompensation</span><span class="sxs-lookup"><span data-stu-id="78965-202">Process compensation</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/process-compensation)
- [<span data-ttu-id="78965-203">Definiera kompensationsprocessen och beräkna resultat</span><span class="sxs-lookup"><span data-stu-id="78965-203">Define compensation process and calculate results</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-compensation-process-calculate-results)
- [<span data-ttu-id="78965-204">Registrera en medarbetare i en fast kompensationsplan</span><span class="sxs-lookup"><span data-stu-id="78965-204">Enroll an employee in a fixed compensation plan</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-fixed-compensation-plan)
- [<span data-ttu-id="78965-205">Registrera en medarbetare i en variabel kompensationsplan</span><span class="sxs-lookup"><span data-stu-id="78965-205">Enroll an employee in a variable compensation plan</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-variable-compensation-plan)

#### <a name="jobs"></a><span data-ttu-id="78965-206">Jobb</span><span class="sxs-lookup"><span data-stu-id="78965-206">Jobs</span></span> 

<span data-ttu-id="78965-207">Ett jobb är den samling uppgifter och ansvarsområden som avkrävs en person som utför ett jobb.</span><span class="sxs-lookup"><span data-stu-id="78965-207">A job is a collection of the tasks and responsibilities that are required of a person who performs a job.</span></span> <span data-ttu-id="78965-208">Mer information finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="78965-208">For more information, see the following topics:</span></span>

- [<span data-ttu-id="78965-209">Installera komponenter för ett jobb</span><span class="sxs-lookup"><span data-stu-id="78965-209">Setting up the components of a job</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/create-job)
- [<span data-ttu-id="78965-210">Definiera nya jobb</span><span class="sxs-lookup"><span data-stu-id="78965-210">Define new jobs</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-jobs)

##### <a name="positions"></a><span data-ttu-id="78965-211">Befattningar</span><span class="sxs-lookup"><span data-stu-id="78965-211">Positions</span></span>

<span data-ttu-id="78965-212">En befattning är ett exempel på ett enskilt jobb.</span><span class="sxs-lookup"><span data-stu-id="78965-212">A position is an individual instance of a job.</span></span> <span data-ttu-id="78965-213">Befattningen "Försäljningschef (öst)" är exempelvis en av de befattningar som associeras med jobbet "Försäljningschef."</span><span class="sxs-lookup"><span data-stu-id="78965-213">For example, the "Sales manager (East)" position is one of the positions that are associated with the "Sales manager" job.</span></span> <span data-ttu-id="78965-214">En befattning finns på en avdelning.</span><span class="sxs-lookup"><span data-stu-id="78965-214">A position exists in a department.</span></span> <span data-ttu-id="78965-215">Endast en enda medarbetare kan vara associerad med respektive befattning.</span><span class="sxs-lookup"><span data-stu-id="78965-215">Only one worker can be associated with each position.</span></span>

<span data-ttu-id="78965-216">Tänk på följande uppgifter och konfigurationsinformation när du ställer in befattningar:</span><span class="sxs-lookup"><span data-stu-id="78965-216">Keep the following data and configuration in mind when you set up positions:</span></span>

- <span data-ttu-id="78965-217">Befattning (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="78965-217">Position (required)</span></span>
- <span data-ttu-id="78965-218">Beskrivning (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="78965-218">Description (required)</span></span>
- <span data-ttu-id="78965-219">Jobb (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="78965-219">Job (required)</span></span>
- <span data-ttu-id="78965-220">Avdelning (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="78965-220">Department (required)</span></span>
- <span data-ttu-id="78965-221">Befattningstyp (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="78965-221">Position type (required)</span></span>
- <span data-ttu-id="78965-222">Heltidslön</span><span class="sxs-lookup"><span data-stu-id="78965-222">Full-time equivalent</span></span>
- <span data-ttu-id="78965-223">Ordinarie timmar per år (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="78965-223">Annual regular hours (required)</span></span>
- <span data-ttu-id="78965-224">Betalas av den juridiska personen (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="78965-224">Paid by legal entity (required)</span></span>
- <span data-ttu-id="78965-225">Lönecykel (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="78965-225">Pay cycle (required)</span></span>
- <span data-ttu-id="78965-226">Standardekonomisk dimension – kostnadsställe (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="78965-226">Default financial dimension – Cost center (required)</span></span>
- <span data-ttu-id="78965-227">Medarbetartilldelning – medarbetare, tilldelningsstart, tilldelningsslut, orsakskod</span><span class="sxs-lookup"><span data-stu-id="78965-227">Worker assignment – Worker, assignment start, assignment end, reason code</span></span>

<span data-ttu-id="78965-228">Om flera befattningar på samma avdelning är associerade med samma jobb konsolideras de till en enda befattning i Dayforce.</span><span class="sxs-lookup"><span data-stu-id="78965-228">If multiple positions in the same department are associated with the same job, they are consolidated into a single position in Dayforce.</span></span>

<span data-ttu-id="78965-229">Mer information finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="78965-229">For more information, see the following topics:</span></span>

- [<span data-ttu-id="78965-230">Organisera arbetsstyrkan med avdelningar, jobb och befattningar</span><span class="sxs-lookup"><span data-stu-id="78965-230">Organize your workforce using departments, jobs, and positions</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/departments-jobs-positions#positions)
- [<span data-ttu-id="78965-231">Ställ in befattningar</span><span class="sxs-lookup"><span data-stu-id="78965-231">Set up positions</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/set-up-positions)

#### <a name="departments"></a><span data-ttu-id="78965-232">Avdelningar</span><span class="sxs-lookup"><span data-stu-id="78965-232">Departments</span></span>

<span data-ttu-id="78965-233">En avdelning är en driftenhet som representerar en kategori eller verksamhetsområde inom en organisation.</span><span class="sxs-lookup"><span data-stu-id="78965-233">A department is an operating unit that represents a category or functional area of an organization.</span></span> <span data-ttu-id="78965-234">En avdelning är ansvarig för en viss del av organisationen, såsom försäljning, bokföring eller mänskliga resurser.</span><span class="sxs-lookup"><span data-stu-id="78965-234">A department is responsible for a specific area of the organization, such as sales, accounting, or human resources.</span></span> <span data-ttu-id="78965-235">Du kan använda avdelningar att rapportera om funktionella områden.</span><span class="sxs-lookup"><span data-stu-id="78965-235">You can use departments to report on functional areas.</span></span> <span data-ttu-id="78965-236">Avdelningar kan ha vinst och förlust.</span><span class="sxs-lookup"><span data-stu-id="78965-236">Departments might have profit and loss responsibility.</span></span>

<span data-ttu-id="78965-237">Mer information finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="78965-237">For more information, see the following topics:</span></span>

- [<span data-ttu-id="78965-238">Skapa en avdelning och associera den med avdelningshierarkin</span><span class="sxs-lookup"><span data-stu-id="78965-238">Create a department and associate it with the department hierarchy</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/create-department-add-department-hierarchy)
- [<span data-ttu-id="78965-239">Definiera nya avdelningar</span><span class="sxs-lookup"><span data-stu-id="78965-239">Define new departments</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-departments)

#### <a name="pay-cycles-and-pay-periods"></a><span data-ttu-id="78965-240">Lönecykler och löneperioder</span><span class="sxs-lookup"><span data-stu-id="78965-240">Pay cycles and pay periods</span></span>

<span data-ttu-id="78965-241">En lönecykel avgör hur ofta lönelistan körs, samt vilka specifika dagar som medarbetarna får betalt.</span><span class="sxs-lookup"><span data-stu-id="78965-241">A pay cycle determines how often payroll is run and the specific days when workers are paid.</span></span> <span data-ttu-id="78965-242">En lönecykel kan exempelvis vara månadsvis och medarbetarna få sin lön den sista dagen i månaden.</span><span class="sxs-lookup"><span data-stu-id="78965-242">For example, a pay cycle might be monthly, and employees might be paid on the last day of the month.</span></span> <span data-ttu-id="78965-243">Alternativt kan en lönecykel vara veckovis och medarbetarna få sin lön på tisdagen efter betalningsperiodens utgång.</span><span class="sxs-lookup"><span data-stu-id="78965-243">Alternatively, a pay cycle might be weekly, and employees might be paid on the Tuesday after the end of the pay period.</span></span> <span data-ttu-id="78965-244">Lönecykler tilldelas befattningar i syfte att styra när arbetare på dessa befattningar får sin lön.</span><span class="sxs-lookup"><span data-stu-id="78965-244">Pay cycles are assigned to positions to control when workers in those positions are paid.</span></span>

<span data-ttu-id="78965-245">När du har skapat lönecykler kan du generera betalningsperioder för respektive cykel.</span><span class="sxs-lookup"><span data-stu-id="78965-245">After you create pay cycles, you can generate pay periods for each cycle.</span></span> <span data-ttu-id="78965-246">Varje betalningsperiod innehåller ett standardbetalningsdatum som baseras på den information du anger.</span><span class="sxs-lookup"><span data-stu-id="78965-246">Each pay period includes a default payment date that is based on information that you provide.</span></span> <span data-ttu-id="78965-247">Du kan emellertid ändra standarddatumet för betalning i en löneperiod i syfte att tillåta undantag, till exempel när betalningsdatumet infaller på en allmän helgdag.</span><span class="sxs-lookup"><span data-stu-id="78965-247">However, you can modify the default payment date in a pay period to allow for exceptions, such as when the payment date falls on a holiday.</span></span>

<span data-ttu-id="78965-248">Följande information används i Dayforce:</span><span class="sxs-lookup"><span data-stu-id="78965-248">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="78965-249">Lönecykel (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="78965-249">Pay cycle (required)</span></span>
- <span data-ttu-id="78965-250">Lönecykelfrekvens (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="78965-250">Pay cycle frequency (required)</span></span>
- <span data-ttu-id="78965-251">Periodens startdatum (första löneperiod obligatorisk)</span><span class="sxs-lookup"><span data-stu-id="78965-251">Period start date (first pay period required)</span></span>
- <span data-ttu-id="78965-252">Standarddatum för betalning (första löneperiod obligatorisk)</span><span class="sxs-lookup"><span data-stu-id="78965-252">Default payment date (first pay period required)</span></span>

<span data-ttu-id="78965-253">Denna information är integrerad i Dayforce som lönegrupper och delas upp efter land eller region för respektive lönecykel.</span><span class="sxs-lookup"><span data-stu-id="78965-253">This information is integrated with Dayforce as pay groups, and is separated by country or region for each pay cycle.</span></span> <span data-ttu-id="78965-254">Minst en löneperiod måste genereras före integration.</span><span class="sxs-lookup"><span data-stu-id="78965-254">At least one pay period must be generated before integration.</span></span> <span data-ttu-id="78965-255">Dayforce genererar gruppkalendrar för lön och betalningsdatum utifrån startdatumet för den första löneperioden och det standarddatum för betalning som anges i Talent.</span><span class="sxs-lookup"><span data-stu-id="78965-255">Dayforce generates pay group calendars and payment dates, based on the start date of the first pay period and the default payment date that is set up in Talent.</span></span>

#### <a name="earning-codes"></a><span data-ttu-id="78965-256">Inkomstkoder</span><span class="sxs-lookup"><span data-stu-id="78965-256">Earning codes</span></span>

<span data-ttu-id="78965-257">Inkomstkoder identifierar individuellt alla typer av arbetstagarintäkter.</span><span class="sxs-lookup"><span data-stu-id="78965-257">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="78965-258">Koderna har olika parametrar som rör inkomster, till exempel redovisningsbestämmelser, skattelagar, rapporteringskrav, och gross up-kapacitet.</span><span class="sxs-lookup"><span data-stu-id="78965-258">The codes have various parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span>

<span data-ttu-id="78965-259">Följande information används i Dayforce:</span><span class="sxs-lookup"><span data-stu-id="78965-259">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="78965-260">Inkomstkod (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="78965-260">Earning Code (required)</span></span>
- <span data-ttu-id="78965-261">beskrivning</span><span class="sxs-lookup"><span data-stu-id="78965-261">Description</span></span>
- <span data-ttu-id="78965-262">Enhet</span><span class="sxs-lookup"><span data-stu-id="78965-262">Unit of measure</span></span>
- <span data-ttu-id="78965-263">Produktiv</span><span class="sxs-lookup"><span data-stu-id="78965-263">Productive</span></span>

### <a name="worker-data"></a><span data-ttu-id="78965-264">Medarbetardata</span><span class="sxs-lookup"><span data-stu-id="78965-264">Worker data</span></span>

<span data-ttu-id="78965-265">Poster för de olika typer av medarbetare som du har är viktiga för dina personal- och lönesystem.</span><span class="sxs-lookup"><span data-stu-id="78965-265">Records for the various types of workers that you have are important to your human resources and payroll systems.</span></span> <span data-ttu-id="78965-266">Den information du anger kan användas för att spåra medarbetare och personuppgifter.</span><span class="sxs-lookup"><span data-stu-id="78965-266">The information that you enter can be used to track workers and personal information.</span></span>

<span data-ttu-id="78965-267">För medarbetare kan du behålla följande information:</span><span class="sxs-lookup"><span data-stu-id="78965-267">You can maintain the following information for workers:</span></span>

- <span data-ttu-id="78965-268">**Grundläggande** – Grundläggande information om en medarbetare, till exempel kontaktinformation, demografisk information, identifikationsinformation, familjeinformation, status för militärtjänst, exilstatusinformation samt personliga och nödkontakter.</span><span class="sxs-lookup"><span data-stu-id="78965-268">**Basic** – Maintain basic information about a worker, such as contact information, demographic information, identification information, family information, military service status, expatriate information, and personal and emergency contacts.</span></span>
- <span data-ttu-id="78965-269">**Anställning** – Information om en medarbetares anställning, exempelvis företags- eller organisationstillhörighet, befattningstilldelning, start- och slutdatum, jobbtillgänglighet, anställningsvillkor, pension, semester- samt omplaceringsinformation.</span><span class="sxs-lookup"><span data-stu-id="78965-269">**Employment** – Maintain information about a worker's employment, such as company or organization affiliation, position assignment, start and end dates, work eligibility, terms of employment, pension, vacation, and relocation information.</span></span>
- <span data-ttu-id="78965-270">**Tjänstledighet och frånvaro** – Information om en medarbetares frånvaro, exempelvis jobbkalendrar, frånvarotransaktioner samt frånvaroinställningar.</span><span class="sxs-lookup"><span data-stu-id="78965-270">**Leave and absence** – Maintain information about a worker's absences, such as working calendars, absence transactions, and absence setup.</span></span>
- <span data-ttu-id="78965-271">**Ersättning och lön** – Information om en medarbetares ersättningsplaner och löneinformation, exempelvis plananmälan, utmärkelser, resultat, provision, skatteinformation, pensionering samt löneavdrag.</span><span class="sxs-lookup"><span data-stu-id="78965-271">**Compensation and payroll** – Maintain information about a worker's compensation plans and payroll information, such as plan enrollment, awards, performance, commission, tax information, retirement, and salary deductions.</span></span>

<span data-ttu-id="78965-272">När du anger medarbetarinformation, kom då ihåg följande uppgifter och konfigurationer som används i Dayforce.</span><span class="sxs-lookup"><span data-stu-id="78965-272">When you enter worker information, keep in mind the following data and configurations that are used in Dayforce.</span></span>

#### <a name="general-information"></a><span data-ttu-id="78965-273">Allmän information</span><span class="sxs-lookup"><span data-stu-id="78965-273">General information</span></span>

- <span data-ttu-id="78965-274">Anställningsnummer (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="78965-274">Personnel number (required)</span></span>
- <span data-ttu-id="78965-275">Förnamn (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="78965-275">First name (required)</span></span>
- <span data-ttu-id="78965-276">Efternamn (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="78965-276">Last name (required)</span></span>
- <span data-ttu-id="78965-277">Mellannamn</span><span class="sxs-lookup"><span data-stu-id="78965-277">Middle name</span></span>
- <span data-ttu-id="78965-278">Datum för tjänsteålder</span><span class="sxs-lookup"><span data-stu-id="78965-278">Seniority date</span></span>
- <span data-ttu-id="78965-279">Känt som</span><span class="sxs-lookup"><span data-stu-id="78965-279">Known as</span></span>

#### <a name="personal-information"></a><span data-ttu-id="78965-280">Personlig information</span><span class="sxs-lookup"><span data-stu-id="78965-280">Personal information</span></span>

- <span data-ttu-id="78965-281">Civilstånd (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="78965-281">Marital status (required)</span></span>
- <span data-ttu-id="78965-282">Födelsedatum (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="78965-282">Birth date (required)</span></span>
- <span data-ttu-id="78965-283">Könstillhörighet (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="78965-283">Gender (required)</span></span>
- <span data-ttu-id="78965-284">Person med funktionsnedsättningar</span><span class="sxs-lookup"><span data-stu-id="78965-284">Person with disabilities</span></span>
- <span data-ttu-id="78965-285">Medborgarskap, land, region (endast för Mexiko)</span><span class="sxs-lookup"><span data-stu-id="78965-285">Nationality country region (only for Mexico)</span></span>

#### <a name="address-information"></a><span data-ttu-id="78965-286">Adressinformation</span><span class="sxs-lookup"><span data-stu-id="78965-286">Address information</span></span>

- <span data-ttu-id="78965-287">Primär adress (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="78965-287">Primary (required)</span></span>
- <span data-ttu-id="78965-288">Land/region (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="78965-288">Country/region (required)</span></span>
- <span data-ttu-id="78965-289">Postnummer (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="78965-289">Postal code (required)</span></span>
- <span data-ttu-id="78965-290">Nummer (obligatoriskt) (endast för Mexiko)</span><span class="sxs-lookup"><span data-stu-id="78965-290">Street Number (required) (Only for Mexico)</span></span>
- <span data-ttu-id="78965-291">Byggnadskomplement (endast för Mexiko)</span><span class="sxs-lookup"><span data-stu-id="78965-291">Building Complement (Only for Mexico)</span></span>
- <span data-ttu-id="78965-292">Stad (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="78965-292">City (required)</span></span>
- <span data-ttu-id="78965-293">Delstat (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="78965-293">State (required)</span></span>
- <span data-ttu-id="78965-294">Region (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="78965-294">County (required)</span></span>

#### <a name="contact-information"></a><span data-ttu-id="78965-295">Kontaktinformation</span><span class="sxs-lookup"><span data-stu-id="78965-295">Contact information</span></span> 

- <span data-ttu-id="78965-296">Primär adress (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="78965-296">Primary (required)</span></span>
- <span data-ttu-id="78965-297">Kontaktnummer (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="78965-297">Contact number (required)</span></span>
- <span data-ttu-id="78965-298">Anknytning</span><span class="sxs-lookup"><span data-stu-id="78965-298">Extension</span></span>

#### <a name="payroll-information-and-earning-codes"></a><span data-ttu-id="78965-299">Löneinformation och inkomstkoder</span><span class="sxs-lookup"><span data-stu-id="78965-299">Payroll information and earning codes</span></span>

<span data-ttu-id="78965-300">Medarbetare kan tilldelas en viss inkomst till en viss betalningsfrekvens och ha en prioriterad betalningsmetod.</span><span class="sxs-lookup"><span data-stu-id="78965-300">Employees may be assigned specific earnings at a given frequency of payment and have a preferred payment method.</span></span> <span data-ttu-id="78965-301">Följande fält används i Dayforce för att garantera att dessa prioriteringar och inställningar används.</span><span class="sxs-lookup"><span data-stu-id="78965-301">The following fields are used in Dayforce to help guarantee that those preferences and settings are used.</span></span>

##### <a name="earning-codes"></a><span data-ttu-id="78965-302">Inkomstkoder</span><span class="sxs-lookup"><span data-stu-id="78965-302">Earning codes</span></span>

- <span data-ttu-id="78965-303">Befattning (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="78965-303">Position (required)</span></span>
- <span data-ttu-id="78965-304">Inkomstkod (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="78965-304">Earning Code (required)</span></span>
- <span data-ttu-id="78965-305">Frekvens (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="78965-305">Frequency (required)</span></span>
- <span data-ttu-id="78965-306">Belopp (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="78965-306">Amount (required)</span></span>

##### <a name="payroll-information"></a><span data-ttu-id="78965-307">Löneinformation</span><span class="sxs-lookup"><span data-stu-id="78965-307">Payroll information</span></span>

- <span data-ttu-id="78965-308">Betalningsmetod</span><span class="sxs-lookup"><span data-stu-id="78965-308">Payment Method</span></span>
- <span data-ttu-id="78965-309">Ekonomisk region (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="78965-309">Economic Region (required)</span></span>
- <span data-ttu-id="78965-310">ID för anställningsförmåner</span><span class="sxs-lookup"><span data-stu-id="78965-310">Employee Benefits ID</span></span>
- <span data-ttu-id="78965-311">Nationellt ID-nummer (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="78965-311">National ID Number (required)</span></span>
- <span data-ttu-id="78965-312">Militärtjänstgöring, nummer</span><span class="sxs-lookup"><span data-stu-id="78965-312">Military Service Number</span></span>
- <span data-ttu-id="78965-313">Skiftes-ID (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="78965-313">Shift ID (required)</span></span>
- <span data-ttu-id="78965-314">Skattenummer (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="78965-314">Tax Number (required)</span></span>
- <span data-ttu-id="78965-315">Fack-ID (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="78965-315">Union ID (required)</span></span>
- <span data-ttu-id="78965-316">Arbetsdags-ID (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="78965-316">Work Day ID (required)</span></span>
- <span data-ttu-id="78965-317">Arbetstillståndsnummer</span><span class="sxs-lookup"><span data-stu-id="78965-317">Work Permit Number</span></span>

> [!NOTE]
> <span data-ttu-id="78965-318">För betalningsmetoden stöder Mexiko **Kontant**, **Check** (företagets fysiska check), samt **Elektronisk betalning**.</span><span class="sxs-lookup"><span data-stu-id="78965-318">For the payment method, Mexico supports **Cash**, **Check** (the company's physical check), and **Electronic Payment**.</span></span> <span data-ttu-id="78965-319">Om betalningsmetoden np anges används **Check** som standard.</span><span class="sxs-lookup"><span data-stu-id="78965-319">If np payment method is specified, **Check** is used by default.</span></span>

#### <a name="employment-details"></a><span data-ttu-id="78965-320">Anställningsinformation</span><span class="sxs-lookup"><span data-stu-id="78965-320">Employment details</span></span>

<span data-ttu-id="78965-321">Detaljerad anställningshistorik används som viktig information i syfte att hämta en medarbetares anställnings-, uppsägnings- och återanställningsstatus i Dayforce.</span><span class="sxs-lookup"><span data-stu-id="78965-321">Employment detail history is used as key information to derive an employee's hire, termination, and rehire statuses in Dayforce.</span></span> <span data-ttu-id="78965-322">Dayforce stöder endast en aktiv anställningspost åt gången.</span><span class="sxs-lookup"><span data-stu-id="78965-322">Dayforce supports only one active employment record at a time.</span></span>

- <span data-ttu-id="78965-323">Startdatum för anställning (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="78965-323">Employment start date (required)</span></span>
- <span data-ttu-id="78965-324">Slutdatum för anställning</span><span class="sxs-lookup"><span data-stu-id="78965-324">Employment end date</span></span>
- <span data-ttu-id="78965-325">Startdatum</span><span class="sxs-lookup"><span data-stu-id="78965-325">Start date</span></span>
- <span data-ttu-id="78965-326">Justerat startdatum</span><span class="sxs-lookup"><span data-stu-id="78965-326">Adjusted start date</span></span>
- <span data-ttu-id="78965-327">Uppsägningsdatum (obligatoriskt vid uppsägning)</span><span class="sxs-lookup"><span data-stu-id="78965-327">Termination date (required upon termination)</span></span>
- <span data-ttu-id="78965-328">Uppsägningsorsak (obligatoriskt vid uppsägning)</span><span class="sxs-lookup"><span data-stu-id="78965-328">Termination reason (required upon termination)</span></span>

<span data-ttu-id="78965-329">Medarbetarens viktiga datum beräknas med hjälp av följande information.</span><span class="sxs-lookup"><span data-stu-id="78965-329">An employee's key dates are derived by using the following information.</span></span>

| <span data-ttu-id="78965-330">Talent</span><span class="sxs-lookup"><span data-stu-id="78965-330">Talent</span></span>                | <span data-ttu-id="78965-331">Dayforce</span><span class="sxs-lookup"><span data-stu-id="78965-331">Dayforce</span></span>                                                                                             |
|-----------------------|------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="78965-332">Senaste anställningsdatum</span><span class="sxs-lookup"><span data-stu-id="78965-332">Most recent hire date</span></span> | <span data-ttu-id="78965-333">Anställningsstart för aktuell, icke-uppsagd post för anställningshistorik</span><span class="sxs-lookup"><span data-stu-id="78965-333">Employment start of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="78965-334">Uppsägningsdatum</span><span class="sxs-lookup"><span data-stu-id="78965-334">Termination date</span></span>      | <span data-ttu-id="78965-335">Uppsägningsdatum för aktuell, icke-uppsagd post för anställningshistorik</span><span class="sxs-lookup"><span data-stu-id="78965-335">Termination date of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="78965-336">Startdatum</span><span class="sxs-lookup"><span data-stu-id="78965-336">Start date</span></span>            | <span data-ttu-id="78965-337">Justerat startdatum, startdatum eller anställningsstart för aktuell, inaktiv post för anställningshistorik</span><span class="sxs-lookup"><span data-stu-id="78965-337">Adjusted start date, start date, or employment start of current non-active employment history record</span></span> |
| <span data-ttu-id="78965-338">Ursprungligt anställningsdatum</span><span class="sxs-lookup"><span data-stu-id="78965-338">Original hire date</span></span>    | <span data-ttu-id="78965-339">Anställningsstart för tidigaste anställningshistorikpost</span><span class="sxs-lookup"><span data-stu-id="78965-339">Employment start of earliest employment history record</span></span>                                               |

#### <a name="compensation"></a><span data-ttu-id="78965-340">Kompensation</span><span class="sxs-lookup"><span data-stu-id="78965-340">Compensation</span></span>

<span data-ttu-id="78965-341">En fast kompensationsplan måste kopplas till varje medarbetares primära befattning under hela anställningsperioden.</span><span class="sxs-lookup"><span data-stu-id="78965-341">A fixed compensation plan must be associated with every employee's primary position throughout an employment period.</span></span> <span data-ttu-id="78965-342">Perioden inleds det datum då medarbetaren anställts (eller på anställningens startdatum) och fortsätter till och med uppsägningen.</span><span class="sxs-lookup"><span data-stu-id="78965-342">This period starts on the date that the employee was hired (or the employment start date) and continues until termination.</span></span>

- <span data-ttu-id="78965-343">Giltighetsdatum (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="78965-343">Effective Date (required)</span></span>
- <span data-ttu-id="78965-344">Utgångsdatum</span><span class="sxs-lookup"><span data-stu-id="78965-344">Expiration date</span></span>
- <span data-ttu-id="78965-345">Lönesats (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="78965-345">Pay Rate (required)</span></span>
- <span data-ttu-id="78965-346">Lönesatskonverteringar (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="78965-346">Pay Rate Conversions (required)</span></span>
- <span data-ttu-id="78965-347">Årlig motsvarighet (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="78965-347">Annual equivalent (required)</span></span>
- <span data-ttu-id="78965-348">Motsvarighet per timme (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="78965-348">Hourly equivalent (required)</span></span>

<span data-ttu-id="78965-349">Om en timanställd har flera befattningar importeras den fasta kompensationen för den primära befattningen till Dayforce som bastariff/-lön för medarbetaren.</span><span class="sxs-lookup"><span data-stu-id="78965-349">If an hourly employee has multiple positions, the fixed compensation of the primary position is imported into Dayforce as the employee-level base rate/salary.</span></span> <span data-ttu-id="78965-350">För icke-primära befattningar sparas timtariffen i motsvarande befattning i Dayforce.</span><span class="sxs-lookup"><span data-stu-id="78965-350">For non-primary positions, the hourly rate is saved to the corresponding position in Dayforce.</span></span>

<span data-ttu-id="78965-351">Om en fast anställd tjänsteman har flera befattningar hämtas den ackumulerade timtariffen och årslönen för samtliga aktiva befattningar och används som bastariff/-lön för medarbetarnivån.</span><span class="sxs-lookup"><span data-stu-id="78965-351">If a salaried employee has multiple positions, the cumulative hour rate and annual salary across all active positions are derived and used as the employee-level base rate/salary.</span></span>

#### <a name="identification-numbers"></a><span data-ttu-id="78965-352">Identifieringsnummer</span><span class="sxs-lookup"><span data-stu-id="78965-352">Identification numbers</span></span>

##### <a name="social-security-identifier"></a><span data-ttu-id="78965-353">Socialförsäkrings-identifierare</span><span class="sxs-lookup"><span data-stu-id="78965-353">Social Security identifier</span></span> 

<span data-ttu-id="78965-354">Alla medarbetare måste ha en primär identifierare.</span><span class="sxs-lookup"><span data-stu-id="78965-354">Every employee must have one primary identifier.</span></span> <span data-ttu-id="78965-355">Denna identifierare måste vara av identifieringstypen **SSN**.</span><span class="sxs-lookup"><span data-stu-id="78965-355">This identifier must be of **SSN** identification type.</span></span> <span data-ttu-id="78965-356">I Dayforce hämtas den automatiskt som den socialförsäkringsidentifierare för anställd som krävs för anställning.</span><span class="sxs-lookup"><span data-stu-id="78965-356">In Dayforce, it's automatically derived as the employee's Social Security identifier that is required for hire.</span></span>

- <span data-ttu-id="78965-357">Primär adress (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="78965-357">Primary (required)</span></span>
- <span data-ttu-id="78965-358">Identifieringstyp = "SSN"</span><span class="sxs-lookup"><span data-stu-id="78965-358">Identification Type = "SSN"</span></span>
- <span data-ttu-id="78965-359">Utfärdat den</span><span class="sxs-lookup"><span data-stu-id="78965-359">Issued Date</span></span>
- <span data-ttu-id="78965-360">Utgångsdatum</span><span class="sxs-lookup"><span data-stu-id="78965-360">Expiration Date</span></span>

<span data-ttu-id="78965-361">Medarbetare kan deklarera flera ID-nummer med ID-typen **SSN**.</span><span class="sxs-lookup"><span data-stu-id="78965-361">Employees can declare multiple identification numbers of the **SSN** identification type.</span></span> <span data-ttu-id="78965-362">Endast posten som är markerad som **Primär** integreras emellertid i Dayforce, oavsett om numret är aktivt eller har upphört att gälla.</span><span class="sxs-lookup"><span data-stu-id="78965-362">However, only the record that is marked as **Primary** is integrated into Dayforce, regardless of whether the number is active or expired.</span></span>

#### <a name="bank-accounts-and-disbursements"></a><span data-ttu-id="78965-363">Bankkonton och utbetalningar</span><span class="sxs-lookup"><span data-stu-id="78965-363">Bank accounts and disbursements</span></span>

<span data-ttu-id="78965-364">Giltig bankkontoinformation måste anges för varje medarbetare som väljer att få sin lön via bankkontoöverföringar.</span><span class="sxs-lookup"><span data-stu-id="78965-364">Valid bank account information must be entered for any employee who chooses to be paid via bank account transfers.</span></span>

| <span data-ttu-id="78965-365">Talent</span><span class="sxs-lookup"><span data-stu-id="78965-365">Talent</span></span>                         | <span data-ttu-id="78965-366">Dayforce</span><span class="sxs-lookup"><span data-stu-id="78965-366">Dayforce</span></span>                                                                                                    |
|--------------------------------|-------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="78965-367">Bankkontonummer (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="78965-367">Bank account number (required)</span></span> |                                                                                                             |
| <span data-ttu-id="78965-368">SWIFT-kod (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="78965-368">SWIFT code (required)</span></span>          | <span data-ttu-id="78965-369">Fältet **Bank-ID** används när löner bearbetas i Mexiko.</span><span class="sxs-lookup"><span data-stu-id="78965-369">**Bank ID** field used when processing payroll in Mexico.</span></span>                                                             |
| <span data-ttu-id="78965-370">Filialnummer (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="78965-370">Branch number (required)</span></span>       |                                                                                                             |
| <span data-ttu-id="78965-371">Bankkontotyp (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="78965-371">Bank account type (required)</span></span>   | <span data-ttu-id="78965-372">Fältet **Kontotyp** används när löner bearbetas i Mexiko.</span><span class="sxs-lookup"><span data-stu-id="78965-372">**Account type** field used when processing payroll in Mexico.</span></span> <span data-ttu-id="78965-373">Värden som stöds inkluderar **Check** och **Lönelista**.</span><span class="sxs-lookup"><span data-stu-id="78965-373">Supported values include **Checking** and **Payroll**.</span></span> |

> [!NOTE]
> <span data-ttu-id="78965-374">Medarbetare som väljer att få lön via bankkontoöverföring måste ange en länk till ett restkonto tillhörande en juridisk person med primär adress i Mexiko och som är associerad med ett giltigt bankkonto från en mexikansk bank.</span><span class="sxs-lookup"><span data-stu-id="78965-374">Employees who choose to be paid via bank account transfers must provide a link to a remainder account that is under a legal entity that has its primary address in Mexico and associated with a valid bank account from a Mexican bank.</span></span> <span data-ttu-id="78965-375">Alla övriga restkonton ignoreras.</span><span class="sxs-lookup"><span data-stu-id="78965-375">All other non-remainder accounts are ignored.</span></span>

#### <a name="address-information"></a><span data-ttu-id="78965-376">Adressinformation</span><span class="sxs-lookup"><span data-stu-id="78965-376">Address information</span></span>

<span data-ttu-id="78965-377">Alla medarbetare måste ha en primär plats.</span><span class="sxs-lookup"><span data-stu-id="78965-377">Every employee must have one primary location.</span></span> <span data-ttu-id="78965-378">Den här platsen används i Dayforce i syfte att fastställa medarbetarens primära hemort i skattesyfte.</span><span class="sxs-lookup"><span data-stu-id="78965-378">In Dayforce, this location is used to determine the employee's primary residence for tax purposes.</span></span>

- <span data-ttu-id="78965-379">Primär adress (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="78965-379">Primary (required)</span></span>
- <span data-ttu-id="78965-380">Land/region (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="78965-380">Country/region (required)</span></span>
- <span data-ttu-id="78965-381">Postnummer (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="78965-381">Zip/postal code (required)</span></span>
- <span data-ttu-id="78965-382">Gata (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="78965-382">Street (required)</span></span>
- <span data-ttu-id="78965-383">Nummer (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="78965-383">Street Number (required)</span></span>
- <span data-ttu-id="78965-384">Byggnadskomplement</span><span class="sxs-lookup"><span data-stu-id="78965-384">Building Complement</span></span>
- <span data-ttu-id="78965-385">Stad (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="78965-385">City (required)</span></span>
- <span data-ttu-id="78965-386">Delstat (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="78965-386">State (required)</span></span>
- <span data-ttu-id="78965-387">Region (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="78965-387">County (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-united-states-and-canada"></a><span data-ttu-id="78965-388">Konfigurera dina data för att generera lön i USA och Kanada</span><span class="sxs-lookup"><span data-stu-id="78965-388">Configure your data to generate payroll in United States and Canada</span></span>

<span data-ttu-id="78965-389">Om du genererar lön för medarbetare i USA och Kanada måste följande element konfigureras:</span><span class="sxs-lookup"><span data-stu-id="78965-389">If you're generating pay for employees in the United States and Canada, the following elements must be configured:</span></span>

- <span data-ttu-id="78965-390">Avdelningar är obligatoriska vid befattningarna:</span><span class="sxs-lookup"><span data-stu-id="78965-390">Departments are required on positions.</span></span>
- <span data-ttu-id="78965-391">Kostnadsställen måste ställas in som ekonomiska dimensioner och måste vara det första elementet i standardsträngen för ekonomisk dimension.</span><span class="sxs-lookup"><span data-stu-id="78965-391">Cost centers must be set as financial dimensions and must be the first element in the default financial dimension string.</span></span>

> [!NOTE] 
> <span data-ttu-id="78965-392">Du kan konfigurera Talent att kräva att befattningar anger en avdelning.</span><span class="sxs-lookup"><span data-stu-id="78965-392">You can configure Talent to require that Positions specify a Department.</span></span> <span data-ttu-id="78965-393">Gör detta genom att gå till **delade befattningar i Personal > befattningar > kräver avdelningar för befattningar**.</span><span class="sxs-lookup"><span data-stu-id="78965-393">To do this, go to **Human Resources Shared Positions > Positions > Require departments on positions**.</span></span> <span data-ttu-id="78965-394">Vi rekommenderar att den här inställningen tillämpas för integration.</span><span class="sxs-lookup"><span data-stu-id="78965-394">We recommend that this setting be enforced for the integration.</span></span>

### <a name="job-types"></a><span data-ttu-id="78965-395">Jobbtyper</span><span class="sxs-lookup"><span data-stu-id="78965-395">Job types</span></span>

<span data-ttu-id="78965-396">Jobbtyper används för att gruppera liknande jobb i kategorier.</span><span class="sxs-lookup"><span data-stu-id="78965-396">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="78965-397">Jobbtyper krävs för att bearbeta lön i USA och Kanada.</span><span class="sxs-lookup"><span data-stu-id="78965-397">Job types are required in order to process payroll in the United States and Canada.</span></span> <span data-ttu-id="78965-398">Några exempel på jobbtyper är heltid och deltid, eller fast lön och timpenning.</span><span class="sxs-lookup"><span data-stu-id="78965-398">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="78965-399">Jobbtyper mappas till Dayforce som lönetyper som anger huruvida en anställd arbetar per timme eller har fast lön.</span><span class="sxs-lookup"><span data-stu-id="78965-399">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="78965-400">Följande jobbtyper och beskrivningar krävs.</span><span class="sxs-lookup"><span data-stu-id="78965-400">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="78965-401">Jobbtyp</span><span class="sxs-lookup"><span data-stu-id="78965-401">Job type</span></span>   | <span data-ttu-id="78965-402">beskrivning</span><span class="sxs-lookup"><span data-stu-id="78965-402">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="78965-403">Varje timme</span><span class="sxs-lookup"><span data-stu-id="78965-403">Hourly</span></span>     | <span data-ttu-id="78965-404">Varje timme</span><span class="sxs-lookup"><span data-stu-id="78965-404">Hourly</span></span>      |
| <span data-ttu-id="78965-405">Fast lön</span><span class="sxs-lookup"><span data-stu-id="78965-405">Salaried</span></span>   | <span data-ttu-id="78965-406">Fast lön</span><span class="sxs-lookup"><span data-stu-id="78965-406">Salaried</span></span>    |

### <a name="position-types"></a><span data-ttu-id="78965-407">Befattningstyper</span><span class="sxs-lookup"><span data-stu-id="78965-407">Position types</span></span> 

<span data-ttu-id="78965-408">Du kan använda befattningstyper för att beskriva huruvida befattningen är på heltid, deltid eller annat.</span><span class="sxs-lookup"><span data-stu-id="78965-408">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="78965-409">Befattningstyper mappas till Dayforce som löneklasser som anger huruvida en anställd arbetar heltid eller deltid.</span><span class="sxs-lookup"><span data-stu-id="78965-409">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="78965-410">Följande befattningstyper och beskrivningar krävs.</span><span class="sxs-lookup"><span data-stu-id="78965-410">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="78965-411">Befattningstyp</span><span class="sxs-lookup"><span data-stu-id="78965-411">Position type</span></span>   | <span data-ttu-id="78965-412">beskrivning</span><span class="sxs-lookup"><span data-stu-id="78965-412">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="78965-413">Heltid</span><span class="sxs-lookup"><span data-stu-id="78965-413">Full-time</span></span>       | <span data-ttu-id="78965-414">Heltidsanställd</span><span class="sxs-lookup"><span data-stu-id="78965-414">Full time employee</span></span> |
| <span data-ttu-id="78965-415">Deltid</span><span class="sxs-lookup"><span data-stu-id="78965-415">Part-time</span></span>       | <span data-ttu-id="78965-416">Deltidsanställd</span><span class="sxs-lookup"><span data-stu-id="78965-416">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="78965-417">Orsakskoder</span><span class="sxs-lookup"><span data-stu-id="78965-417">Reason codes</span></span>

<span data-ttu-id="78965-418">Orsakskoder innehåller information om statusen för en medarbetare.</span><span class="sxs-lookup"><span data-stu-id="78965-418">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="78965-419">Orsakskoder mappas till Dayforce som statusanledningar som anger orsaken till ändringar i en medarbetares befattning eller anställningsstatus.</span><span class="sxs-lookup"><span data-stu-id="78965-419">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="78965-420">Följande orsakskoder och -beskrivningar krävs.</span><span class="sxs-lookup"><span data-stu-id="78965-420">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="78965-421">Orsakskod</span><span class="sxs-lookup"><span data-stu-id="78965-421">Reason code</span></span>    | <span data-ttu-id="78965-422">beskrivning</span><span class="sxs-lookup"><span data-stu-id="78965-422">Description</span></span>      | <span data-ttu-id="78965-423">Tillämpliga scenarier</span><span class="sxs-lookup"><span data-stu-id="78965-423">Applicable scenarios</span></span> |
|----------------|------------------|----------------------|
| <span data-ttu-id="78965-424">EGEN UPPSÄGNING</span><span class="sxs-lookup"><span data-stu-id="78965-424">RESIGNATION</span></span>    | <span data-ttu-id="78965-425">Egen uppsägning</span><span class="sxs-lookup"><span data-stu-id="78965-425">Resignation</span></span>      | <span data-ttu-id="78965-426">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="78965-426">Terminate worker</span></span>     |
| <span data-ttu-id="78965-427">UPPSÄGNING</span><span class="sxs-lookup"><span data-stu-id="78965-427">TERMINATION</span></span>    | <span data-ttu-id="78965-428">Uppsägning</span><span class="sxs-lookup"><span data-stu-id="78965-428">Termination</span></span>      | <span data-ttu-id="78965-429">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="78965-429">Terminate worker</span></span>     |
| <span data-ttu-id="78965-430">PENSION</span><span class="sxs-lookup"><span data-stu-id="78965-430">RETIREMENT</span></span>     | <span data-ttu-id="78965-431">Pension</span><span class="sxs-lookup"><span data-stu-id="78965-431">Retirement</span></span>       | <span data-ttu-id="78965-432">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="78965-432">Terminate worker</span></span>     |
| <span data-ttu-id="78965-433">ÖVRIGT</span><span class="sxs-lookup"><span data-stu-id="78965-433">OTHER</span></span>          | <span data-ttu-id="78965-434">Andra orsaker</span><span class="sxs-lookup"><span data-stu-id="78965-434">Other Reasons</span></span>    | <span data-ttu-id="78965-435">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="78965-435">Terminate worker</span></span>     |
| <span data-ttu-id="78965-436">DÖDSFALL</span><span class="sxs-lookup"><span data-stu-id="78965-436">DEATH</span></span>          | <span data-ttu-id="78965-437">Dödsfall</span><span class="sxs-lookup"><span data-stu-id="78965-437">Death</span></span>            | <span data-ttu-id="78965-438">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="78965-438">Terminate worker</span></span>     |
| <span data-ttu-id="78965-439">TJÄNSTLEDIGHET</span><span class="sxs-lookup"><span data-stu-id="78965-439">LEAVEOFABSENCE</span></span> | <span data-ttu-id="78965-440">Tjänstledighet</span><span class="sxs-lookup"><span data-stu-id="78965-440">Leave of Absence</span></span> | <span data-ttu-id="78965-441">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="78965-441">Terminate worker</span></span>     |
| <span data-ttu-id="78965-442">KONTRAKTSLUT</span><span class="sxs-lookup"><span data-stu-id="78965-442">CONTRACTEND</span></span>    | <span data-ttu-id="78965-443">Kontraktslut</span><span class="sxs-lookup"><span data-stu-id="78965-443">End of Contract</span></span>  | <span data-ttu-id="78965-444">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="78965-444">Terminate worker</span></span>     |
| <span data-ttu-id="78965-445">LÖNEÄNDRING</span><span class="sxs-lookup"><span data-stu-id="78965-445">SALARYCHANGE</span></span>   | <span data-ttu-id="78965-446">Löneändring</span><span class="sxs-lookup"><span data-stu-id="78965-446">Change of Salary</span></span> | <span data-ttu-id="78965-447">Kompensation</span><span class="sxs-lookup"><span data-stu-id="78965-447">Compensation</span></span>         |

### <a name="marital-status"></a><span data-ttu-id="78965-448">Civilstånd</span><span class="sxs-lookup"><span data-stu-id="78965-448">Marital status</span></span>

<span data-ttu-id="78965-449">Civilståndsvärden mappas till Dayforce och översätts på lämpligt sätt till giltiga värden i samband med integrering.</span><span class="sxs-lookup"><span data-stu-id="78965-449">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="78965-450">Följande tabell visar hur civilståndsvärden mappas till Dayforce.</span><span class="sxs-lookup"><span data-stu-id="78965-450">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="78965-451">Talent</span><span class="sxs-lookup"><span data-stu-id="78965-451">Talent</span></span>                 | <span data-ttu-id="78965-452">Dayforce</span><span class="sxs-lookup"><span data-stu-id="78965-452">Dayforce</span></span>             |
|------------------------|----------------------|
| <span data-ttu-id="78965-453">Gift</span><span class="sxs-lookup"><span data-stu-id="78965-453">Married</span></span>                | <span data-ttu-id="78965-454">Gift</span><span class="sxs-lookup"><span data-stu-id="78965-454">Married</span></span>              |
| <span data-ttu-id="78965-455">Ett</span><span class="sxs-lookup"><span data-stu-id="78965-455">Single</span></span>                 | <span data-ttu-id="78965-456">Ett</span><span class="sxs-lookup"><span data-stu-id="78965-456">Single</span></span>               |
| <span data-ttu-id="78965-457">Änka/änkling</span><span class="sxs-lookup"><span data-stu-id="78965-457">Widowed</span></span>                | <span data-ttu-id="78965-458">Änka/änkling</span><span class="sxs-lookup"><span data-stu-id="78965-458">Widowed</span></span>              |
| <span data-ttu-id="78965-459">Frånskild</span><span class="sxs-lookup"><span data-stu-id="78965-459">Divorced</span></span>               | <span data-ttu-id="78965-460">Frånskild</span><span class="sxs-lookup"><span data-stu-id="78965-460">Divorced</span></span>             |
| <span data-ttu-id="78965-461">Registrerat partnerskap</span><span class="sxs-lookup"><span data-stu-id="78965-461">Registered Partnership</span></span> | <span data-ttu-id="78965-462">Samboförhållande</span><span class="sxs-lookup"><span data-stu-id="78965-462">Domestic Partnership</span></span> |
| <span data-ttu-id="78965-463">Inga</span><span class="sxs-lookup"><span data-stu-id="78965-463">None</span></span>                   | <span data-ttu-id="78965-464">Inga</span><span class="sxs-lookup"><span data-stu-id="78965-464">None</span></span>                 |
| <span data-ttu-id="78965-465">Sambo</span><span class="sxs-lookup"><span data-stu-id="78965-465">Cohabiting</span></span>             | <span data-ttu-id="78965-466">Sambo</span><span class="sxs-lookup"><span data-stu-id="78965-466">Cohabiting</span></span>           |

### <a name="gender"></a><span data-ttu-id="78965-467">Kön</span><span class="sxs-lookup"><span data-stu-id="78965-467">Gender</span></span>

<span data-ttu-id="78965-468">Könsbeteckningar mappas till Dayforce och översätts på lämpligt sätt till giltiga värden i samband med integrering.</span><span class="sxs-lookup"><span data-stu-id="78965-468">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="78965-469">Följande tabell visar hur könsbeteckningar mappas till Dayforce.</span><span class="sxs-lookup"><span data-stu-id="78965-469">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="78965-470">Talent</span><span class="sxs-lookup"><span data-stu-id="78965-470">Talent</span></span>       | <span data-ttu-id="78965-471">Dayforce</span><span class="sxs-lookup"><span data-stu-id="78965-471">Dayforce</span></span>        |
|--------------|-----------------|
| <span data-ttu-id="78965-472">Man</span><span class="sxs-lookup"><span data-stu-id="78965-472">Male</span></span>         | <span data-ttu-id="78965-473">Man</span><span class="sxs-lookup"><span data-stu-id="78965-473">Male</span></span>            |
| <span data-ttu-id="78965-474">Kvinna</span><span class="sxs-lookup"><span data-stu-id="78965-474">Female</span></span>       | <span data-ttu-id="78965-475">Kvinna</span><span class="sxs-lookup"><span data-stu-id="78965-475">Female</span></span>          |
| <span data-ttu-id="78965-476">Icke-specifik</span><span class="sxs-lookup"><span data-stu-id="78965-476">Non-specific</span></span> | <span data-ttu-id="78965-477">*Stöds ej*</span><span class="sxs-lookup"><span data-stu-id="78965-477">*Not supported*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="78965-478">Inkomstkoder</span><span class="sxs-lookup"><span data-stu-id="78965-478">Earning codes</span></span>

<span data-ttu-id="78965-479">Inkomstkoder identifierar individuellt alla typer av arbetstagarintäkter.</span><span class="sxs-lookup"><span data-stu-id="78965-479">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="78965-480">Koderna omfattar flera olika parametrar som rör inkomster, till exempel redovisningsbestämmelser, skattelagar, rapporteringskrav och gross up-kapacitet.</span><span class="sxs-lookup"><span data-stu-id="78965-480">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="78965-481">Om en frekvens som inte stöds används tillämpas frekvensen **Varje lön** som standard för beräkningen.</span><span class="sxs-lookup"><span data-stu-id="78965-481">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="78965-482">Frekvenser som stöds</span><span class="sxs-lookup"><span data-stu-id="78965-482">Supported frequencies</span></span>

- <span data-ttu-id="78965-483">Allt</span><span class="sxs-lookup"><span data-stu-id="78965-483">All</span></span>
- <span data-ttu-id="78965-484">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="78965-484">EVERYPAY</span></span>
- <span data-ttu-id="78965-485">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="78965-485">EACHPAYPERIOD</span></span>
- <span data-ttu-id="78965-486">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="78965-486">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="78965-487">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="78965-487">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="78965-488">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="78965-488">1OFMTH</span></span>
- <span data-ttu-id="78965-489">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="78965-489">LASTOFMTH</span></span>
- <span data-ttu-id="78965-490">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="78965-490">2OFMTH</span></span>
- <span data-ttu-id="78965-491">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="78965-491">3OFMTH</span></span>
- <span data-ttu-id="78965-492">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="78965-492">4OFMTH</span></span>
- <span data-ttu-id="78965-493">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="78965-493">5OFMTH</span></span>
- <span data-ttu-id="78965-494">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="78965-494">1N2OFMTH</span></span>
- <span data-ttu-id="78965-495">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="78965-495">3N4OFMTH</span></span>
- <span data-ttu-id="78965-496">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="78965-496">1N3OFMTH</span></span>
- <span data-ttu-id="78965-497">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="78965-497">1N4OFMTH</span></span>
- <span data-ttu-id="78965-498">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="78965-498">2N3OFMTH</span></span>
- <span data-ttu-id="78965-499">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="78965-499">2N4OFMTH</span></span>
- <span data-ttu-id="78965-500">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="78965-500">1N2N3OFMTH</span></span>
- <span data-ttu-id="78965-501">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="78965-501">1N2N4OFMTH</span></span>
- <span data-ttu-id="78965-502">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="78965-502">1N3N4OFMTH</span></span>
- <span data-ttu-id="78965-503">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="78965-503">2N3N4OFMTH</span></span>
- <span data-ttu-id="78965-504">1N2N3N4OFMTH - 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="78965-504">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="78965-505">2N3N4N5OFMth - 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="78965-505">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="78965-506">1OFQTR - 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="78965-506">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="78965-507">LASTOFQTR – LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="78965-507">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="78965-508">LASTMTHOFQTR – LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="78965-508">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="78965-509">1OFYEAR - 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="78965-509">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="78965-510">LASTOFYEAR – LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="78965-510">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="78965-511">NOVNDECOFYEAR - NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="78965-511">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="78965-512">Adresser</span><span class="sxs-lookup"><span data-stu-id="78965-512">Addresses</span></span>

<span data-ttu-id="78965-513">Identifiering av specifika lands-/region-, delstats- och region(kommun)-koder kräver särskilda format som Dayforce och leverantörer i respektive land/region kan känna igen.</span><span class="sxs-lookup"><span data-stu-id="78965-513">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="78965-514">Även om formatet för städer är flexibelt måste varje stad associeras med en delstat.</span><span class="sxs-lookup"><span data-stu-id="78965-514">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="78965-515">Talent</span><span class="sxs-lookup"><span data-stu-id="78965-515">Talent</span></span>          | <span data-ttu-id="78965-516">Dayforce</span><span class="sxs-lookup"><span data-stu-id="78965-516">Dayforce</span></span>              |
|-----------------|-----------------------|
| <span data-ttu-id="78965-517">Land/region</span><span class="sxs-lookup"><span data-stu-id="78965-517">Country/Region</span></span>  | <span data-ttu-id="78965-518">Landskod</span><span class="sxs-lookup"><span data-stu-id="78965-518">Country Code</span></span>          |
| <span data-ttu-id="78965-519">Postnummer</span><span class="sxs-lookup"><span data-stu-id="78965-519">Zip/Postal Code</span></span> | <span data-ttu-id="78965-520">Postnummer</span><span class="sxs-lookup"><span data-stu-id="78965-520">Postal Code</span></span>           |
| <span data-ttu-id="78965-521">Stat</span><span class="sxs-lookup"><span data-stu-id="78965-521">State</span></span>           | <span data-ttu-id="78965-522">Delstatskod</span><span class="sxs-lookup"><span data-stu-id="78965-522">State Code</span></span>            |
| <span data-ttu-id="78965-523">Ort</span><span class="sxs-lookup"><span data-stu-id="78965-523">City</span></span>            | <span data-ttu-id="78965-524">Ort</span><span class="sxs-lookup"><span data-stu-id="78965-524">City</span></span>                  |
| <span data-ttu-id="78965-525">Län</span><span class="sxs-lookup"><span data-stu-id="78965-525">County</span></span>          | <span data-ttu-id="78965-526">Region (kommun)</span><span class="sxs-lookup"><span data-stu-id="78965-526">County (Municipality)</span></span> |
| <span data-ttu-id="78965-527">Gata</span><span class="sxs-lookup"><span data-stu-id="78965-527">Street</span></span>          | <span data-ttu-id="78965-528">Adressrad 1</span><span class="sxs-lookup"><span data-stu-id="78965-528">Address Line 1</span></span>        |

### <a name="tax-regions"></a><span data-ttu-id="78965-529">Skatteregioner</span><span class="sxs-lookup"><span data-stu-id="78965-529">Tax regions</span></span>

<span data-ttu-id="78965-530">Skatteregioner används för att bestämma vilken skattesats som ska användas vid lönegenerering.</span><span class="sxs-lookup"><span data-stu-id="78965-530">Tax regions are used to determine the appropriate tax that should be applied during payroll generation.</span></span> <span data-ttu-id="78965-531">Skatteregioner mappas till Dayforce som platsadresser.</span><span class="sxs-lookup"><span data-stu-id="78965-531">Tax regions are mapped to Dayforce as location addresses.</span></span> <span data-ttu-id="78965-532">Förvald skatteregion måste associeras med medarbetarens aktiva befattning.</span><span class="sxs-lookup"><span data-stu-id="78965-532">The default tax region must be associated with the worker's active position.</span></span> 

- <span data-ttu-id="78965-533">Skatteregion (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="78965-533">Tax region (required)</span></span>
- <span data-ttu-id="78965-534">Land/region (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="78965-534">Country/Region (required)</span></span>
- <span data-ttu-id="78965-535">Delstat (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="78965-535">State (required)</span></span>
- <span data-ttu-id="78965-536">Län</span><span class="sxs-lookup"><span data-stu-id="78965-536">County</span></span> 
- <span data-ttu-id="78965-537">Stad (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="78965-537">City (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-mexico"></a><span data-ttu-id="78965-538">Konfigurera dina data för att generera lön i Mexiko</span><span class="sxs-lookup"><span data-stu-id="78965-538">Configure your data to generate payroll in Mexico</span></span>

<span data-ttu-id="78965-539">Om du genererar lön för medarbetare i Mexiko måste följande element konfigureras:</span><span class="sxs-lookup"><span data-stu-id="78965-539">If you're generating pay for employees in Mexico, the following elements must be configured:</span></span>

- <span data-ttu-id="78965-540">Avdelningar är obligatoriska vid befattningarna:</span><span class="sxs-lookup"><span data-stu-id="78965-540">Departments are required on positions.</span></span>
- <span data-ttu-id="78965-541">Kostnadsställen måste ställas in som ekonomiska dimensioner och måste vara det första elementet i standardsträngen för ekonomisk dimension.</span><span class="sxs-lookup"><span data-stu-id="78965-541">Cost centers must be set as financial dimensions and must be the first element in the Default Financial Dimension string.</span></span>

### <a name="job-types"></a><span data-ttu-id="78965-542">Jobbtyper</span><span class="sxs-lookup"><span data-stu-id="78965-542">Job types</span></span>

<span data-ttu-id="78965-543">Jobbtyper används för att gruppera liknande jobb i kategorier.</span><span class="sxs-lookup"><span data-stu-id="78965-543">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="78965-544">Jobbtyper krävs för att bearbeta löner i Mexiko.</span><span class="sxs-lookup"><span data-stu-id="78965-544">Job types are required in order to process payroll in Mexico.</span></span> <span data-ttu-id="78965-545">Några exempel på jobbtyper är heltid och deltid, eller fast lön och timpenning.</span><span class="sxs-lookup"><span data-stu-id="78965-545">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="78965-546">Jobbtyper mappas till Dayforce som lönetyper som anger huruvida en anställd arbetar per timme eller har fast lön.</span><span class="sxs-lookup"><span data-stu-id="78965-546">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="78965-547">Följande jobbtyper och beskrivningar krävs.</span><span class="sxs-lookup"><span data-stu-id="78965-547">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="78965-548">Jobbtyp</span><span class="sxs-lookup"><span data-stu-id="78965-548">Job type</span></span>   | <span data-ttu-id="78965-549">beskrivning</span><span class="sxs-lookup"><span data-stu-id="78965-549">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="78965-550">Varje timme</span><span class="sxs-lookup"><span data-stu-id="78965-550">Hourly</span></span>     | <span data-ttu-id="78965-551">MX Varje timme</span><span class="sxs-lookup"><span data-stu-id="78965-551">MX Hourly</span></span>   |
| <span data-ttu-id="78965-552">Fast lön</span><span class="sxs-lookup"><span data-stu-id="78965-552">Salaried</span></span>   | <span data-ttu-id="78965-553">MX Fast lön</span><span class="sxs-lookup"><span data-stu-id="78965-553">MX Salaried</span></span> |

### <a name="position-types"></a><span data-ttu-id="78965-554">Befattningstyper</span><span class="sxs-lookup"><span data-stu-id="78965-554">Position types</span></span> 

<span data-ttu-id="78965-555">Du kan använda befattningstyper för att beskriva huruvida befattningen är på heltid, deltid eller annat.</span><span class="sxs-lookup"><span data-stu-id="78965-555">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="78965-556">Befattningstyper mappas till Dayforce som löneklasser som anger huruvida en anställd arbetar heltid eller deltid.</span><span class="sxs-lookup"><span data-stu-id="78965-556">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="78965-557">Följande befattningstyper och beskrivningar krävs.</span><span class="sxs-lookup"><span data-stu-id="78965-557">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="78965-558">Befattningstyp</span><span class="sxs-lookup"><span data-stu-id="78965-558">Position type</span></span>   | <span data-ttu-id="78965-559">beskrivning</span><span class="sxs-lookup"><span data-stu-id="78965-559">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="78965-560">Heltid</span><span class="sxs-lookup"><span data-stu-id="78965-560">Full-time</span></span>       | <span data-ttu-id="78965-561">Heltidsanställd</span><span class="sxs-lookup"><span data-stu-id="78965-561">Full time employee</span></span> |
| <span data-ttu-id="78965-562">Deltid</span><span class="sxs-lookup"><span data-stu-id="78965-562">Part-time</span></span>       | <span data-ttu-id="78965-563">Deltidsanställd</span><span class="sxs-lookup"><span data-stu-id="78965-563">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="78965-564">Orsakskoder</span><span class="sxs-lookup"><span data-stu-id="78965-564">Reason codes</span></span>

<span data-ttu-id="78965-565">Orsakskoder innehåller information om statusen för en medarbetare.</span><span class="sxs-lookup"><span data-stu-id="78965-565">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="78965-566">Orsakskoder mappas till Dayforce som statusanledningar som anger orsaken till ändringar i en medarbetares befattning eller anställningsstatus.</span><span class="sxs-lookup"><span data-stu-id="78965-566">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="78965-567">Följande orsakskoder och -beskrivningar krävs.</span><span class="sxs-lookup"><span data-stu-id="78965-567">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="78965-568">Orsakskod</span><span class="sxs-lookup"><span data-stu-id="78965-568">Reason code</span></span>            | <span data-ttu-id="78965-569">beskrivning</span><span class="sxs-lookup"><span data-stu-id="78965-569">Description</span></span>                    | <span data-ttu-id="78965-570">Tillämpliga scenarier</span><span class="sxs-lookup"><span data-stu-id="78965-570">Applicable scenarios</span></span> |
|------------------------|--------------------------------|----------------------|
| <span data-ttu-id="78965-571">DEPARTUREBEFOREPAYMENT</span><span class="sxs-lookup"><span data-stu-id="78965-571">DEPARTUREBEFOREPAYMENT</span></span> | <span data-ttu-id="78965-572">Avgick före första lön</span><span class="sxs-lookup"><span data-stu-id="78965-572">Departure before first payroll</span></span> | <span data-ttu-id="78965-573">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="78965-573">Terminate worker</span></span>     |
| <span data-ttu-id="78965-574">EGEN UPPSÄGNING</span><span class="sxs-lookup"><span data-stu-id="78965-574">RESIGNATION</span></span>            | <span data-ttu-id="78965-575">Egen uppsägning</span><span class="sxs-lookup"><span data-stu-id="78965-575">Resignation</span></span>                    | <span data-ttu-id="78965-576">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="78965-576">Terminate worker</span></span>     |
| <span data-ttu-id="78965-577">PENSION</span><span class="sxs-lookup"><span data-stu-id="78965-577">PENSION</span></span>                | <span data-ttu-id="78965-578">Pension</span><span class="sxs-lookup"><span data-stu-id="78965-578">Pension</span></span>                        | <span data-ttu-id="78965-579">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="78965-579">Terminate worker</span></span>     |
| <span data-ttu-id="78965-580">UPPSÄGNING</span><span class="sxs-lookup"><span data-stu-id="78965-580">TERMINATION</span></span>            | <span data-ttu-id="78965-581">Uppsägning</span><span class="sxs-lookup"><span data-stu-id="78965-581">Termination</span></span>                    | <span data-ttu-id="78965-582">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="78965-582">Terminate worker</span></span>     |
| <span data-ttu-id="78965-583">PENSION</span><span class="sxs-lookup"><span data-stu-id="78965-583">RETIREMENT</span></span>             | <span data-ttu-id="78965-584">Pension</span><span class="sxs-lookup"><span data-stu-id="78965-584">Retirement</span></span>                     | <span data-ttu-id="78965-585">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="78965-585">Terminate worker</span></span>     |
| <span data-ttu-id="78965-586">FRÅNVARANDE</span><span class="sxs-lookup"><span data-stu-id="78965-586">ABSENTEE</span></span>               | <span data-ttu-id="78965-587">Frånvarande</span><span class="sxs-lookup"><span data-stu-id="78965-587">Absentee</span></span>                       | <span data-ttu-id="78965-588">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="78965-588">Terminate worker</span></span>     |
| <span data-ttu-id="78965-589">ÖVRIGT</span><span class="sxs-lookup"><span data-stu-id="78965-589">OTHER</span></span>                  | <span data-ttu-id="78965-590">Andra orsaker</span><span class="sxs-lookup"><span data-stu-id="78965-590">Other Reasons</span></span>                  | <span data-ttu-id="78965-591">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="78965-591">Terminate worker</span></span>     |
| <span data-ttu-id="78965-592">AVSLUT</span><span class="sxs-lookup"><span data-stu-id="78965-592">CLOSURE</span></span>                | <span data-ttu-id="78965-593">Verksamheten nedlagd</span><span class="sxs-lookup"><span data-stu-id="78965-593">Business Closure</span></span>               | <span data-ttu-id="78965-594">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="78965-594">Terminate worker</span></span>     |
| <span data-ttu-id="78965-595">DÖDSFALL</span><span class="sxs-lookup"><span data-stu-id="78965-595">DEATH</span></span>                  | <span data-ttu-id="78965-596">Dödsfall</span><span class="sxs-lookup"><span data-stu-id="78965-596">Death</span></span>                          | <span data-ttu-id="78965-597">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="78965-597">Terminate worker</span></span>     |
| <span data-ttu-id="78965-598">TJÄNSTLEDIGHET</span><span class="sxs-lookup"><span data-stu-id="78965-598">LEAVEOFABSENCE</span></span>         | <span data-ttu-id="78965-599">Tjänstledighet</span><span class="sxs-lookup"><span data-stu-id="78965-599">Leave of Absence</span></span>               | <span data-ttu-id="78965-600">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="78965-600">Terminate worker</span></span>     |
| <span data-ttu-id="78965-601">KONTRAKTSLUT</span><span class="sxs-lookup"><span data-stu-id="78965-601">CONTRACTEND</span></span>            | <span data-ttu-id="78965-602">Kontraktslut</span><span class="sxs-lookup"><span data-stu-id="78965-602">End of Contract</span></span>                | <span data-ttu-id="78965-603">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="78965-603">Terminate worker</span></span>     |
| <span data-ttu-id="78965-604">LÖNEÄNDRING</span><span class="sxs-lookup"><span data-stu-id="78965-604">SALARYCHANGE</span></span>           | <span data-ttu-id="78965-605">Löneändring</span><span class="sxs-lookup"><span data-stu-id="78965-605">Change of Salary</span></span>               | <span data-ttu-id="78965-606">Kompensation</span><span class="sxs-lookup"><span data-stu-id="78965-606">Compensation</span></span>         |

### <a name="terms-of-employment"></a><span data-ttu-id="78965-607">Anställningsvillkor</span><span class="sxs-lookup"><span data-stu-id="78965-607">Terms of employment</span></span>

<span data-ttu-id="78965-608">Anställningsvillkor används för att skapa kategorier av anställningsvillkor.</span><span class="sxs-lookup"><span data-stu-id="78965-608">Terms of employment are used to create categories of employment terms.</span></span> <span data-ttu-id="78965-609">Villkoren mappas till Dayforce som indikatorvärden för anställning.</span><span class="sxs-lookup"><span data-stu-id="78965-609">The terms are mapped to Dayforce as employment indicator values.</span></span>

<span data-ttu-id="78965-610">Följande anställningsvillkor samt beskrivningar krävs.</span><span class="sxs-lookup"><span data-stu-id="78965-610">The following terms of employment and descriptions are required.</span></span>

| <span data-ttu-id="78965-611">Anställningsvillkor</span><span class="sxs-lookup"><span data-stu-id="78965-611">Terms of employment</span></span>   | <span data-ttu-id="78965-612">beskrivning</span><span class="sxs-lookup"><span data-stu-id="78965-612">Description</span></span> |
|-----------------------|-------------|
| <span data-ttu-id="78965-613">Vanligt</span><span class="sxs-lookup"><span data-stu-id="78965-613">Regular</span></span>               | <span data-ttu-id="78965-614">Vanligt</span><span class="sxs-lookup"><span data-stu-id="78965-614">Regular</span></span>     |
| <span data-ttu-id="78965-615">Direkt</span><span class="sxs-lookup"><span data-stu-id="78965-615">Direct</span></span>                | <span data-ttu-id="78965-616">Direkt</span><span class="sxs-lookup"><span data-stu-id="78965-616">Direct</span></span>      |
| <span data-ttu-id="78965-617">Praktik</span><span class="sxs-lookup"><span data-stu-id="78965-617">Internship</span></span>            | <span data-ttu-id="78965-618">Praktik</span><span class="sxs-lookup"><span data-stu-id="78965-618">Internship</span></span>  |
| <span data-ttu-id="78965-619">Permanent</span><span class="sxs-lookup"><span data-stu-id="78965-619">Permanent</span></span>             | <span data-ttu-id="78965-620">Permanent</span><span class="sxs-lookup"><span data-stu-id="78965-620">Permanent</span></span>   |

### <a name="marital-status"></a><span data-ttu-id="78965-621">Civilstånd</span><span class="sxs-lookup"><span data-stu-id="78965-621">Marital status</span></span>

<span data-ttu-id="78965-622">Civilståndsvärden mappas till Dayforce och översätts på lämpligt sätt till giltiga värden i samband med integrering.</span><span class="sxs-lookup"><span data-stu-id="78965-622">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="78965-623">Följande tabell visar hur civilståndsvärden mappas till Dayforce.</span><span class="sxs-lookup"><span data-stu-id="78965-623">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="78965-624">Talent</span><span class="sxs-lookup"><span data-stu-id="78965-624">Talent</span></span>                 | <span data-ttu-id="78965-625">Dayforce</span><span class="sxs-lookup"><span data-stu-id="78965-625">Dayforce</span></span>                  |
|------------------------|---------------------------|
| <span data-ttu-id="78965-626">Gift</span><span class="sxs-lookup"><span data-stu-id="78965-626">Married</span></span>                | <span data-ttu-id="78965-627">Gift</span><span class="sxs-lookup"><span data-stu-id="78965-627">Married</span></span>                   |
| <span data-ttu-id="78965-628">Ett</span><span class="sxs-lookup"><span data-stu-id="78965-628">Single</span></span>                 | <span data-ttu-id="78965-629">Ett</span><span class="sxs-lookup"><span data-stu-id="78965-629">Single</span></span>                    |
| <span data-ttu-id="78965-630">Änka/änkling</span><span class="sxs-lookup"><span data-stu-id="78965-630">Widowed</span></span>                | <span data-ttu-id="78965-631">Änka/änkling</span><span class="sxs-lookup"><span data-stu-id="78965-631">Widowed</span></span>                   |
| <span data-ttu-id="78965-632">Frånskild</span><span class="sxs-lookup"><span data-stu-id="78965-632">Divorced</span></span>               | <span data-ttu-id="78965-633">Frånskild</span><span class="sxs-lookup"><span data-stu-id="78965-633">Divorced</span></span>                  |
| <span data-ttu-id="78965-634">Registrerat partnerskap</span><span class="sxs-lookup"><span data-stu-id="78965-634">Registered Partnership</span></span> | <span data-ttu-id="78965-635">Samboförhållande</span><span class="sxs-lookup"><span data-stu-id="78965-635">Domestic Partnership</span></span>      |
| <span data-ttu-id="78965-636">Inga</span><span class="sxs-lookup"><span data-stu-id="78965-636">None</span></span>                   | <span data-ttu-id="78965-637">*Stöds inte i Mexiko*</span><span class="sxs-lookup"><span data-stu-id="78965-637">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="78965-638">Sambo</span><span class="sxs-lookup"><span data-stu-id="78965-638">Cohabiting</span></span>             | <span data-ttu-id="78965-639">*Stöds inte i Mexiko*</span><span class="sxs-lookup"><span data-stu-id="78965-639">*Not supported by Mexico*</span></span> |

### <a name="gender"></a><span data-ttu-id="78965-640">Kön</span><span class="sxs-lookup"><span data-stu-id="78965-640">Gender</span></span>

<span data-ttu-id="78965-641">Könsbeteckningar mappas till Dayforce och översätts på lämpligt sätt till giltiga värden i samband med integrering.</span><span class="sxs-lookup"><span data-stu-id="78965-641">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="78965-642">Följande tabell visar hur könsbeteckningar mappas till Dayforce.</span><span class="sxs-lookup"><span data-stu-id="78965-642">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="78965-643">Talent</span><span class="sxs-lookup"><span data-stu-id="78965-643">Talent</span></span>       | <span data-ttu-id="78965-644">Dayforce</span><span class="sxs-lookup"><span data-stu-id="78965-644">Dayforce</span></span>                  |
|--------------|---------------------------|
| <span data-ttu-id="78965-645">Man</span><span class="sxs-lookup"><span data-stu-id="78965-645">Male</span></span>         | <span data-ttu-id="78965-646">Man</span><span class="sxs-lookup"><span data-stu-id="78965-646">Male</span></span>                      |
| <span data-ttu-id="78965-647">Kvinna</span><span class="sxs-lookup"><span data-stu-id="78965-647">Female</span></span>       | <span data-ttu-id="78965-648">Kvinna</span><span class="sxs-lookup"><span data-stu-id="78965-648">Female</span></span>                    |
| <span data-ttu-id="78965-649">Icke-specifik</span><span class="sxs-lookup"><span data-stu-id="78965-649">Non-specific</span></span> | <span data-ttu-id="78965-650">*Stöds inte i Mexiko*</span><span class="sxs-lookup"><span data-stu-id="78965-650">*Not supported by Mexico*</span></span> |

### <a name="payment-method"></a><span data-ttu-id="78965-651">Betalningsmetod</span><span class="sxs-lookup"><span data-stu-id="78965-651">Payment method</span></span>

<span data-ttu-id="78965-652">Betalningsmetoder ger medarbetare och företag ett sätt att beskriva hur medarbetaren ska betalas.</span><span class="sxs-lookup"><span data-stu-id="78965-652">Payment methods give the employee and the company a way to describe how employees will be paid.</span></span> <span data-ttu-id="78965-653">Betalningsmetoder mappas till Dayforce och översätts på lämpligt sätt till giltiga värden i samband med integrering.</span><span class="sxs-lookup"><span data-stu-id="78965-653">Payment methods are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="78965-654">Följande tabell visar hur betalningsmetoder mappas till Dayforce.</span><span class="sxs-lookup"><span data-stu-id="78965-654">The following table shows how payment methods are mapped to Dayforce.</span></span>

| <span data-ttu-id="78965-655">Talent</span><span class="sxs-lookup"><span data-stu-id="78965-655">Talent</span></span>             | <span data-ttu-id="78965-656">Dayforce</span><span class="sxs-lookup"><span data-stu-id="78965-656">Dayforce</span></span>                  |
|--------------------|---------------------------|
| <span data-ttu-id="78965-657">Kontant</span><span class="sxs-lookup"><span data-stu-id="78965-657">Cash</span></span>               | <span data-ttu-id="78965-658">Kontant</span><span class="sxs-lookup"><span data-stu-id="78965-658">Cash</span></span>                      |
| <span data-ttu-id="78965-659">Elektronisk betalning</span><span class="sxs-lookup"><span data-stu-id="78965-659">Electronic Payment</span></span> | <span data-ttu-id="78965-660">Överför</span><span class="sxs-lookup"><span data-stu-id="78965-660">Transfer</span></span>                  |
| <span data-ttu-id="78965-661">Check</span><span class="sxs-lookup"><span data-stu-id="78965-661">Check</span></span>              | <span data-ttu-id="78965-662">Check</span><span class="sxs-lookup"><span data-stu-id="78965-662">Cheque</span></span>                    |
| <span data-ttu-id="78965-663">Bankutdrag</span><span class="sxs-lookup"><span data-stu-id="78965-663">Bank Draft</span></span>         | <span data-ttu-id="78965-664">*Stöds inte i Mexiko*</span><span class="sxs-lookup"><span data-stu-id="78965-664">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="78965-665">Annat</span><span class="sxs-lookup"><span data-stu-id="78965-665">Other</span></span>              | <span data-ttu-id="78965-666">*Stöds inte i Mexiko*</span><span class="sxs-lookup"><span data-stu-id="78965-666">*Not supported by Mexico*</span></span> |

### <a name="bank-account-type"></a><span data-ttu-id="78965-667">Bankkontotyp</span><span class="sxs-lookup"><span data-stu-id="78965-667">Bank account type</span></span>

<span data-ttu-id="78965-668">Bankkontotyper används för elektroniska betalningar till medarbetare.</span><span class="sxs-lookup"><span data-stu-id="78965-668">Bank account types are used for electronic payments to employees.</span></span> <span data-ttu-id="78965-669">Bankkontotyper mappas till Dayforce som kontoinformation för överföringar.</span><span class="sxs-lookup"><span data-stu-id="78965-669">Bank account types are mapped to Dayforce as transfer account information.</span></span> <span data-ttu-id="78965-670">Bankkontotyper översätts på lämpligt till giltiga värden i samband med integrering.</span><span class="sxs-lookup"><span data-stu-id="78965-670">The bank account types are translated, as appropriate, to the accepted values upon integration.</span></span>

| <span data-ttu-id="78965-671">Talent</span><span class="sxs-lookup"><span data-stu-id="78965-671">Talent</span></span>            | <span data-ttu-id="78965-672">Dayforce</span><span class="sxs-lookup"><span data-stu-id="78965-672">Dayforce</span></span>                  |
|-------------------|---------------------------|
| <span data-ttu-id="78965-673">Checkkonto</span><span class="sxs-lookup"><span data-stu-id="78965-673">Checking Account</span></span>  | <span data-ttu-id="78965-674">Checkkonto</span><span class="sxs-lookup"><span data-stu-id="78965-674">CheckingAccount</span></span>           |
| <span data-ttu-id="78965-675">Lönekonto</span><span class="sxs-lookup"><span data-stu-id="78965-675">Payroll Account</span></span>   | <span data-ttu-id="78965-676">Lönekonto</span><span class="sxs-lookup"><span data-stu-id="78965-676">PayrollAccount</span></span>            |
| <span data-ttu-id="78965-677">Sparkonto</span><span class="sxs-lookup"><span data-stu-id="78965-677">Savings Account</span></span>   | <span data-ttu-id="78965-678">*Stöds inte i Mexiko*</span><span class="sxs-lookup"><span data-stu-id="78965-678">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="78965-679">BankGirot-konto</span><span class="sxs-lookup"><span data-stu-id="78965-679">BankGirot account</span></span> | <span data-ttu-id="78965-680">*Stöds inte i Mexiko*</span><span class="sxs-lookup"><span data-stu-id="78965-680">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="78965-681">PlusGirot-konto</span><span class="sxs-lookup"><span data-stu-id="78965-681">PlusGirot account</span></span> | <span data-ttu-id="78965-682">*Stöds inte i Mexiko*</span><span class="sxs-lookup"><span data-stu-id="78965-682">*Not supported by Mexico*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="78965-683">Inkomstkoder</span><span class="sxs-lookup"><span data-stu-id="78965-683">Earning codes</span></span>

<span data-ttu-id="78965-684">Inkomstkoder identifierar individuellt alla typer av arbetstagarintäkter.</span><span class="sxs-lookup"><span data-stu-id="78965-684">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="78965-685">Koderna omfattar flera olika parametrar som rör inkomster, till exempel redovisningsbestämmelser, skattelagar, rapporteringskrav och gross up-kapacitet.</span><span class="sxs-lookup"><span data-stu-id="78965-685">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="78965-686">Om en frekvens som inte stöds används tillämpas frekvensen **Varje lön** som standard för beräkningen.</span><span class="sxs-lookup"><span data-stu-id="78965-686">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="78965-687">Frekvenser som stöds</span><span class="sxs-lookup"><span data-stu-id="78965-687">Supported frequencies</span></span>

- <span data-ttu-id="78965-688">Allt</span><span class="sxs-lookup"><span data-stu-id="78965-688">All</span></span>
- <span data-ttu-id="78965-689">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="78965-689">EVERYPAY</span></span>
- <span data-ttu-id="78965-690">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="78965-690">EACHPAYPERIOD</span></span>
- <span data-ttu-id="78965-691">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="78965-691">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="78965-692">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="78965-692">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="78965-693">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="78965-693">1OFMTH</span></span>
- <span data-ttu-id="78965-694">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="78965-694">LASTOFMTH</span></span>
- <span data-ttu-id="78965-695">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="78965-695">2OFMTH</span></span>
- <span data-ttu-id="78965-696">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="78965-696">3OFMTH</span></span>
- <span data-ttu-id="78965-697">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="78965-697">4OFMTH</span></span>
- <span data-ttu-id="78965-698">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="78965-698">5OFMTH</span></span>
- <span data-ttu-id="78965-699">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="78965-699">1N2OFMTH</span></span>
- <span data-ttu-id="78965-700">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="78965-700">3N4OFMTH</span></span>
- <span data-ttu-id="78965-701">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="78965-701">1N3OFMTH</span></span>
- <span data-ttu-id="78965-702">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="78965-702">1N4OFMTH</span></span>
- <span data-ttu-id="78965-703">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="78965-703">2N3OFMTH</span></span>
- <span data-ttu-id="78965-704">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="78965-704">2N4OFMTH</span></span>
- <span data-ttu-id="78965-705">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="78965-705">1N2N3OFMTH</span></span>
- <span data-ttu-id="78965-706">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="78965-706">1N2N4OFMTH</span></span>
- <span data-ttu-id="78965-707">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="78965-707">1N3N4OFMTH</span></span>
- <span data-ttu-id="78965-708">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="78965-708">2N3N4OFMTH</span></span>
- <span data-ttu-id="78965-709">1N2N3N4OFMTH - 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="78965-709">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="78965-710">2N3N4N5OFMth - 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="78965-710">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="78965-711">1OFQTR - 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="78965-711">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="78965-712">LASTOFQTR – LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="78965-712">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="78965-713">LASTMTHOFQTR – LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="78965-713">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="78965-714">1OFYEAR - 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="78965-714">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="78965-715">LASTOFYEAR – LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="78965-715">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="78965-716">NOVNDECOFYEAR - NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="78965-716">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="78965-717">Adresser</span><span class="sxs-lookup"><span data-stu-id="78965-717">Addresses</span></span>

<span data-ttu-id="78965-718">Identifiering av specifika lands-/region-, delstats- och region(kommun)-koder kräver särskilda format som Dayforce och leverantörer i respektive land/region kan känna igen.</span><span class="sxs-lookup"><span data-stu-id="78965-718">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="78965-719">Även om formatet för städer är flexibelt måste varje stad associeras med en delstat.</span><span class="sxs-lookup"><span data-stu-id="78965-719">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="78965-720">Talent</span><span class="sxs-lookup"><span data-stu-id="78965-720">Talent</span></span>              | <span data-ttu-id="78965-721">Dayforce</span><span class="sxs-lookup"><span data-stu-id="78965-721">Dayforce</span></span>              |
|---------------------|-----------------------|
| <span data-ttu-id="78965-722">Land/region</span><span class="sxs-lookup"><span data-stu-id="78965-722">Country/Region</span></span>      | <span data-ttu-id="78965-723">Landskod</span><span class="sxs-lookup"><span data-stu-id="78965-723">Country Code</span></span>          |
| <span data-ttu-id="78965-724">Postnummer</span><span class="sxs-lookup"><span data-stu-id="78965-724">Zip/Postal Code</span></span>     | <span data-ttu-id="78965-725">Postnummer</span><span class="sxs-lookup"><span data-stu-id="78965-725">Postal Code</span></span>           |
| <span data-ttu-id="78965-726">Stat</span><span class="sxs-lookup"><span data-stu-id="78965-726">State</span></span>               | <span data-ttu-id="78965-727">Delstatskod</span><span class="sxs-lookup"><span data-stu-id="78965-727">State Code</span></span>            |
| <span data-ttu-id="78965-728">Ort</span><span class="sxs-lookup"><span data-stu-id="78965-728">City</span></span>                | <span data-ttu-id="78965-729">Ort</span><span class="sxs-lookup"><span data-stu-id="78965-729">City</span></span>                  |
| <span data-ttu-id="78965-730">Län</span><span class="sxs-lookup"><span data-stu-id="78965-730">County</span></span>              | <span data-ttu-id="78965-731">Region (kommun)</span><span class="sxs-lookup"><span data-stu-id="78965-731">County (Municipality)</span></span> |
| <span data-ttu-id="78965-732">Gata</span><span class="sxs-lookup"><span data-stu-id="78965-732">Street</span></span>              | <span data-ttu-id="78965-733">Adressrad 1</span><span class="sxs-lookup"><span data-stu-id="78965-733">Address Line 1</span></span>        |
| <span data-ttu-id="78965-734">Gatunummer</span><span class="sxs-lookup"><span data-stu-id="78965-734">Street Number</span></span>       | <span data-ttu-id="78965-735">Adressrad 2</span><span class="sxs-lookup"><span data-stu-id="78965-735">Address Line 2</span></span>        |
| <span data-ttu-id="78965-736">Byggnadskomplement</span><span class="sxs-lookup"><span data-stu-id="78965-736">Building Complement</span></span> | <span data-ttu-id="78965-737">Adressrad 5</span><span class="sxs-lookup"><span data-stu-id="78965-737">Address Line 5</span></span>        |

### <a name="passport-number"></a><span data-ttu-id="78965-738">Passnummer</span><span class="sxs-lookup"><span data-stu-id="78965-738">Passport number</span></span>

<span data-ttu-id="78965-739">Medarbetare kan deklarera passinformation.</span><span class="sxs-lookup"><span data-stu-id="78965-739">Employees can declare passport information.</span></span> <span data-ttu-id="78965-740">Denna information bär ID-typen **Pass** och integreras i Dayforce som en del av medarbetarens Mexikospecifika information.</span><span class="sxs-lookup"><span data-stu-id="78965-740">This information is of the **Passport** identification type and is integrated into Dayforce as part of an employee's Mexico-specific information.</span></span>

- <span data-ttu-id="78965-741">Identifieringstyp = "Pass"</span><span class="sxs-lookup"><span data-stu-id="78965-741">Identification Type = "Passport"</span></span>
- <span data-ttu-id="78965-742">Utfärdat den</span><span class="sxs-lookup"><span data-stu-id="78965-742">Issued Date</span></span>
- <span data-ttu-id="78965-743">Utgångsdatum</span><span class="sxs-lookup"><span data-stu-id="78965-743">Expiration Date</span></span>

<span data-ttu-id="78965-744">Medarbetare kan deklarera flera ID-nummer med ID-typen **Pass**.</span><span class="sxs-lookup"><span data-stu-id="78965-744">Employees can declare multiple identification numbers of the **Passport** identification type.</span></span> <span data-ttu-id="78965-745">Endast den aktuella passposten integreras emellertid i Dayforce.</span><span class="sxs-lookup"><span data-stu-id="78965-745">However, only the current active passport entry is integrated into Dayforce.</span></span> <span data-ttu-id="78965-746">Om alla passposter har upphört att gälla kommer det pass som är utfärdat senast att integreras i Dayforce.</span><span class="sxs-lookup"><span data-stu-id="78965-746">If all passport entries are expired, the passport that was most recently issued is integrated into Dayforce.</span></span>
