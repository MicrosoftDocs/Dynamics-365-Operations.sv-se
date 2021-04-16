---
title: Konfigurera integration med Dayforce
description: Integreringen mellan Microsoft Dynamics 365 Human Resources och Ceridian Dayforce är beroende av flera konfigurationssteg som beskrivs i det här avsnittet. Du måste konfigurera integrationen i både Personal och Dayforce innan du kan bearbeta en betalning.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PersonnelIntegrationConfiguration
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: bcb57082a49fc07a4139aa37f9507890ca7ed620
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5805092"
---
# <a name="configure-integration-with-dayforce"></a><span data-ttu-id="fce19-104">Konfigurera integration med Dayforce</span><span class="sxs-lookup"><span data-stu-id="fce19-104">Configure integration with Dayforce</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="fce19-105">Integreringen mellan Microsoft Dynamics 365 Human Resources och Ceridian Dayforce är beroende av flera konfigurationssteg som beskrivs i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="fce19-105">The integration between Microsoft Dynamics 365 Human Resources and Ceridian Dayforce relies on several configuration steps that are described in this article.</span></span> <span data-ttu-id="fce19-106">Du måste konfigurera integrationen i både Personal och Dayforce innan du kan bearbeta en betalning.</span><span class="sxs-lookup"><span data-stu-id="fce19-106">You must configure the integration in both Human Resources and Dayforce before you can process a pay run.</span></span>

<span data-ttu-id="fce19-107">När du använder tjänster som exempelvis Dayforce för att utföra betalningar måste du aktivera integration i Personal.</span><span class="sxs-lookup"><span data-stu-id="fce19-107">When you use a service such as Dayforce to complete pay runs, you must enable the integration in Human Resources.</span></span> <span data-ttu-id="fce19-108">Integrationen kräver specifika data från Personal.</span><span class="sxs-lookup"><span data-stu-id="fce19-108">The integration requires specific data from Human Resources.</span></span> <span data-ttu-id="fce19-109">Därför måste du kontrollera att data som är mappad till Dayforce konfigureras i Personal på ett sätt som stöder integrationen.</span><span class="sxs-lookup"><span data-stu-id="fce19-109">Therefore, you must verify that data that is mapped to Dayforce is configured in Human Resources in a manner that supports the integration.</span></span> <span data-ttu-id="fce19-110">Integrationen använder följande breda datakategorier:</span><span class="sxs-lookup"><span data-stu-id="fce19-110">The integration uses the following broad categories of data:</span></span>

- <span data-ttu-id="fce19-111">Personaldata</span><span class="sxs-lookup"><span data-stu-id="fce19-111">Human resources data</span></span>
- <span data-ttu-id="fce19-112">Kompensationsdata</span><span class="sxs-lookup"><span data-stu-id="fce19-112">Compensation data</span></span>
- <span data-ttu-id="fce19-113">Lönedata som till exempel lönecykler, betalningsperioder och inkomstkoder</span><span class="sxs-lookup"><span data-stu-id="fce19-113">Payroll data, such as pay cycles, pay periods, and earning codes</span></span>
- <span data-ttu-id="fce19-114">Medarbetardata</span><span class="sxs-lookup"><span data-stu-id="fce19-114">Worker data</span></span>

<span data-ttu-id="fce19-115">Det här avsnittet beskriver de steg som du måste följa för att aktivera integrationen.</span><span class="sxs-lookup"><span data-stu-id="fce19-115">This article describes the steps that you must follow to enable the integration.</span></span> <span data-ttu-id="fce19-116">Här förklaras också de typer av data och den konfigurationsinformation som integrationen kräver.</span><span class="sxs-lookup"><span data-stu-id="fce19-116">It also explains the types of data and the configuration details that the integration requires.</span></span>

## <a name="enable-the-integration"></a><span data-ttu-id="fce19-117">Aktivera integrationen</span><span class="sxs-lookup"><span data-stu-id="fce19-117">Enable the integration</span></span>

<span data-ttu-id="fce19-118">Du måste aktivera integrationen i Personal och ange konfigurationsinformation för att ansluta till Dayforce.</span><span class="sxs-lookup"><span data-stu-id="fce19-118">In Human Resources, you must turn on the integration and enter the configuration information to connect to Dayforce.</span></span> <span data-ttu-id="fce19-119">Om du vill att den redovisningstransaktion som framställs ska importeras till Microsoft Dynamics 365 Finance måste du också skapa ett lagringskonto för Microsoft Azure och ange anslutningssträngen för Azure-lagring i Finance.</span><span class="sxs-lookup"><span data-stu-id="fce19-119">If you want the general ledger transaction that is produced to be imported into Microsoft Dynamics 365 Finance, you must also set up a Microsoft Azure storage account and enter the Azure Storage connection string in Finance.</span></span>

<span data-ttu-id="fce19-120">Följ dessa steg om du vill aktivera integration i Personal.</span><span class="sxs-lookup"><span data-stu-id="fce19-120">To turn on the integration in Human Resources, follow these steps.</span></span>

1. <span data-ttu-id="fce19-121">På sidan **Systemadministration** väljer du **Integrationskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="fce19-121">On the **System administration** page, select **Integration configuration**.</span></span>
2. <span data-ttu-id="fce19-122">Ange slutpunkten för filöverföringsprotokollet (FTP) och den säkra FTP-sökvägen.</span><span class="sxs-lookup"><span data-stu-id="fce19-122">Enter the secure File Transfer Protocol (FTP) endpoint and the secure FTP folder path.</span></span>
3. <span data-ttu-id="fce19-123">Ange användarnamn och lösenord för den användare som kommer att använda den säkra FTP-slutpunkten och mappsökvägen.</span><span class="sxs-lookup"><span data-stu-id="fce19-123">Enter the user name and password of the user who will access the secure FTP endpoint and folder path.</span></span>
4. <span data-ttu-id="fce19-124">Testa anslutningen efter behov samt ange alternativet **Aktivera integrering av löner** som **Ja**.</span><span class="sxs-lookup"><span data-stu-id="fce19-124">Test the connection, as required, and set the **Enable payroll integration** option to **Yes**.</span></span>

<span data-ttu-id="fce19-125">När integreringen aktiveras skapas dataexportpaket och filer, och frekvensen anges.</span><span class="sxs-lookup"><span data-stu-id="fce19-125">When the integration is turned on, the data export package and files are created, and the frequency is set.</span></span> <span data-ttu-id="fce19-126">Du kan ändra frekvensen efter behov.</span><span class="sxs-lookup"><span data-stu-id="fce19-126">You can change this frequency as you require.</span></span>

<span data-ttu-id="fce19-127">Mer information om Azure-lagringskonton och anslutningssträngar för Azure-lagring, se följande Azure-artiklar:</span><span class="sxs-lookup"><span data-stu-id="fce19-127">For more information about Azure storage accounts and Azure Storage connection strings, see the following Azure articles:</span></span>

- [<span data-ttu-id="fce19-128">Om Azure-lagringskonton</span><span class="sxs-lookup"><span data-stu-id="fce19-128">About Azure storage accounts</span></span>](https://docs.microsoft.com/azure/storage/common/storage-create-storage-account?toc=%2fazure%2fstorage%2ffiles%2ftoc.json)
- [<span data-ttu-id="fce19-129">Konfigurera anslutningssträngar för Azure-lagring</span><span class="sxs-lookup"><span data-stu-id="fce19-129">Configure Azure Storage connection strings</span></span>](https://docs.microsoft.com/azure/storage/common/storage-configure-connection-string)

### <a name="technical-details-when-payroll-integration-is-enabled"></a><span data-ttu-id="fce19-130">Teknisk information när löneintegration har aktiverats</span><span class="sxs-lookup"><span data-stu-id="fce19-130">Technical details when payroll integration is enabled</span></span>

<span data-ttu-id="fce19-131">Att slå på löneintegration har två primära effekter:</span><span class="sxs-lookup"><span data-stu-id="fce19-131">Turning on the payroll integration has two primary effects:</span></span>

- <span data-ttu-id="fce19-132">Ett dataexportprojekt med namnet "Löneintegrationexport" skapas.</span><span class="sxs-lookup"><span data-stu-id="fce19-132">A data export project named "Payroll integration export" is created.</span></span> <span data-ttu-id="fce19-133">Det här projektet innehåller de entiteter och fält som krävs för löneintegration.</span><span class="sxs-lookup"><span data-stu-id="fce19-133">This project contains the entities and fields required for the payroll integration.</span></span> <span data-ttu-id="fce19-134">För att undersöka projekt, gå till **Systemadministration**, välj **Datahantering** och öppna dataprojekt från lista över projekt.</span><span class="sxs-lookup"><span data-stu-id="fce19-134">To examine the project, go to **System administration**, select the **Data management** tile, and then open the data project from the list of projects.</span></span>
- <span data-ttu-id="fce19-135">Det här batchjobbet kör dataexportprojektet, krypterar det resulterande datapaketet och överför datapaketfilen till den SFTP-slutpunkt som konfigurerats på skärmen **integrationskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="fce19-135">This batch job executes the data export project, encrypts the resulting data package, and transfers the data package file to the SFTP endpoint configured on the **Integration configuration** screen.</span></span>

> [!NOTE]
> <span data-ttu-id="fce19-136">Det datapaket som överförs till SFTP-slutpunkten krypteras med en nyckel som är unik för paketet.</span><span class="sxs-lookup"><span data-stu-id="fce19-136">The data package transferred to the SFTP endpoint is encrypted using a key that is unique to the package.</span></span> <span data-ttu-id="fce19-137">Nyckeln finns i ett Azure Key Vault som bara kan nås av Ceridian.</span><span class="sxs-lookup"><span data-stu-id="fce19-137">The key is in an Azure Key Vault that is accessible only by Ceridian.</span></span> <span data-ttu-id="fce19-138">Det går inte att dekryptera och undersöka innehållet i datapaketet.</span><span class="sxs-lookup"><span data-stu-id="fce19-138">It is not possible to decrypt and examine the data package contents.</span></span> <span data-ttu-id="fce19-139">Om du behöver undersöka innehållet i datapaketet, måste du exportera dataprojektet "Löneintegrationexport" manuellt, hämta det och sedan öppna det.</span><span class="sxs-lookup"><span data-stu-id="fce19-139">If you need to examine the contents of the data package, you need to export the "Payroll integration export" data project manually, download it, and then open it.</span></span> <span data-ttu-id="fce19-140">Manuell export använder inte kryptering eller överföring av paketet.</span><span class="sxs-lookup"><span data-stu-id="fce19-140">Manual export will not apply encryption or transfer the package.</span></span>

## <a name="configure-your-data"></a><span data-ttu-id="fce19-141">Konfigurera dina data</span><span class="sxs-lookup"><span data-stu-id="fce19-141">Configure your data</span></span> 

<span data-ttu-id="fce19-142">Du måste konfigurera personaldata för att bearbeta löner i Personal.</span><span class="sxs-lookup"><span data-stu-id="fce19-142">To process payroll, you must configure human resource data in Human Resources.</span></span> <span data-ttu-id="fce19-143">Du måste ställa in organisationsinformation, t.ex. jobb och befattningar samt förmåner och kompensationsinformation.</span><span class="sxs-lookup"><span data-stu-id="fce19-143">You must set up organizational data, such as jobs and positions, together with benefits and compensation information.</span></span> <span data-ttu-id="fce19-144">Denna information utgör den anställnings-, lön- och avdragsinformationen som krävs för att generera lön för medarbetare.</span><span class="sxs-lookup"><span data-stu-id="fce19-144">This information provides the employment, pay, and deduction information that is required in order to generate employee pay.</span></span>

### <a name="human-resource-data"></a><span data-ttu-id="fce19-145">Personaldata</span><span class="sxs-lookup"><span data-stu-id="fce19-145">Human resource data</span></span>

#### <a name="benefits"></a><span data-ttu-id="fce19-146">Förmåner</span><span class="sxs-lookup"><span data-stu-id="fce19-146">Benefits</span></span> 

<span data-ttu-id="fce19-147">Personal tillhandahåller verktyg som kan användas för att ställa in och underhålla förmåner, avdrag och kompensationsplaner för medarbetare som en organisation erbjuder eller bearbetar för sin personal.</span><span class="sxs-lookup"><span data-stu-id="fce19-147">Human resources provides tools for the setup and maintenance of the benefits, deductions, and worker compensation plans that an organization offers or processes for its workers.</span></span>

<span data-ttu-id="fce19-148">När du skapar förmåner, kom då ihåg följande data och konfigurationer som används i Dayforce.</span><span class="sxs-lookup"><span data-stu-id="fce19-148">When you create benefits, keep in mind the following data and configurations that are used in Dayforce.</span></span>

##### <a name="benefit-plans"></a><span data-ttu-id="fce19-149">Förmånsplaner</span><span class="sxs-lookup"><span data-stu-id="fce19-149">Benefit plans</span></span>

- <span data-ttu-id="fce19-150">Plan (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="fce19-150">Plan (required)</span></span>
- <span data-ttu-id="fce19-151">Typ (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="fce19-151">Type (required)</span></span>
- <span data-ttu-id="fce19-152">Effekt på lön (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="fce19-152">Payroll impact (required)</span></span>
- <span data-ttu-id="fce19-153">Återvinn restbetalningar</span><span class="sxs-lookup"><span data-stu-id="fce19-153">Recover arrears</span></span>
- <span data-ttu-id="fce19-154">Avdragsmetod</span><span class="sxs-lookup"><span data-stu-id="fce19-154">Deduction method</span></span>
- <span data-ttu-id="fce19-155">Avdragsprioritet</span><span class="sxs-lookup"><span data-stu-id="fce19-155">Deduction priority</span></span>
- <span data-ttu-id="fce19-156">Gränsperiod</span><span class="sxs-lookup"><span data-stu-id="fce19-156">Limit period</span></span>
- <span data-ttu-id="fce19-157">Begränsa belopp</span><span class="sxs-lookup"><span data-stu-id="fce19-157">Limit amount</span></span>

##### <a name="benefits"></a><span data-ttu-id="fce19-158">Förmåner</span><span class="sxs-lookup"><span data-stu-id="fce19-158">Benefits</span></span>

- <span data-ttu-id="fce19-159">Plan (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="fce19-159">Plan (required)</span></span>
- <span data-ttu-id="fce19-160">Typ (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="fce19-160">Type (required)</span></span>
- <span data-ttu-id="fce19-161">Tillval (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="fce19-161">Option (required)</span></span>
- <span data-ttu-id="fce19-162">Förmåns-ID (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="fce19-162">Benefit ID (required)</span></span>
- <span data-ttu-id="fce19-163">Frekvens</span><span class="sxs-lookup"><span data-stu-id="fce19-163">Frequency</span></span>
- <span data-ttu-id="fce19-164">Bas</span><span class="sxs-lookup"><span data-stu-id="fce19-164">Basis</span></span>
- <span data-ttu-id="fce19-165">Belopp eller tariff</span><span class="sxs-lookup"><span data-stu-id="fce19-165">Amount or rate</span></span>
- <span data-ttu-id="fce19-166">Inkomstkod</span><span class="sxs-lookup"><span data-stu-id="fce19-166">Earning code</span></span>

##### <a name="supported-frequencies"></a><span data-ttu-id="fce19-167">Frekvenser som stöds</span><span class="sxs-lookup"><span data-stu-id="fce19-167">Supported frequencies</span></span> 

- <span data-ttu-id="fce19-168">Varje vecka</span><span class="sxs-lookup"><span data-stu-id="fce19-168">Weekly</span></span>
- <span data-ttu-id="fce19-169">Varannan vecka</span><span class="sxs-lookup"><span data-stu-id="fce19-169">Bi-weekly</span></span>
- <span data-ttu-id="fce19-170">Var fjortonde dag</span><span class="sxs-lookup"><span data-stu-id="fce19-170">Semi-monthly</span></span>
- <span data-ttu-id="fce19-171">Månatlig</span><span class="sxs-lookup"><span data-stu-id="fce19-171">Monthly</span></span>

##### <a name="supported-bases"></a><span data-ttu-id="fce19-172">Databaser som stöds</span><span class="sxs-lookup"><span data-stu-id="fce19-172">Supported bases</span></span> 

- <span data-ttu-id="fce19-173">Fast belopp</span><span class="sxs-lookup"><span data-stu-id="fce19-173">Fixed amount</span></span>
- <span data-ttu-id="fce19-174">Procent av inkomst</span><span class="sxs-lookup"><span data-stu-id="fce19-174">Percent of earnings</span></span>
- <span data-ttu-id="fce19-175">Produktiva timmar</span><span class="sxs-lookup"><span data-stu-id="fce19-175">Productive hours</span></span>

<span data-ttu-id="fce19-176">Dayforce skapar följande avdrag baserat på den löneeffekt som definieras i förmånsplanen.</span><span class="sxs-lookup"><span data-stu-id="fce19-176">Dayforce creates the following deductions, based on the payroll impact that is defined on the benefit plan.</span></span>

| <span data-ttu-id="fce19-177">Val i Personal</span><span class="sxs-lookup"><span data-stu-id="fce19-177">Selection in Human Resources</span></span>        | <span data-ttu-id="fce19-178">Resultat i Dayforce</span><span class="sxs-lookup"><span data-stu-id="fce19-178">Result in Dayforce</span></span>                            |
|----------------------------|-----------------------------------------------|
| <span data-ttu-id="fce19-179">Ingen</span><span class="sxs-lookup"><span data-stu-id="fce19-179">None</span></span>                       | <span data-ttu-id="fce19-180">Inget avdrag skapas.</span><span class="sxs-lookup"><span data-stu-id="fce19-180">No deduction is created.</span></span>                      |
| <span data-ttu-id="fce19-181">Endast avdrag</span><span class="sxs-lookup"><span data-stu-id="fce19-181">Deduction only</span></span>             | <span data-ttu-id="fce19-182">Löneavdrag för en medarbetare skapas.</span><span class="sxs-lookup"><span data-stu-id="fce19-182">An employee deduction is created.</span></span>             |
| <span data-ttu-id="fce19-183">Endast lönetillägg</span><span class="sxs-lookup"><span data-stu-id="fce19-183">Contribution only</span></span>          | <span data-ttu-id="fce19-184">Löneavdrag för en arbetsgivare skapas.</span><span class="sxs-lookup"><span data-stu-id="fce19-184">An employer deduction is created.</span></span>             |
| <span data-ttu-id="fce19-185">Avdrag och tillägg</span><span class="sxs-lookup"><span data-stu-id="fce19-185">Deduction and contribution</span></span> | <span data-ttu-id="fce19-186">Avdrag för medarbetare och arbetsgivare skapas.</span><span class="sxs-lookup"><span data-stu-id="fce19-186">Employee and employer deductions are created.</span></span> |

<span data-ttu-id="fce19-187">Mer information om hur du definierar och hanterar ett förmånsprogram finns i följande artiklar:</span><span class="sxs-lookup"><span data-stu-id="fce19-187">For more information about how to define and manage a benefits program, see the following articles:</span></span>

- [<span data-ttu-id="fce19-188">Utveckla ett förmånsprogram för medarbetare</span><span class="sxs-lookup"><span data-stu-id="fce19-188">Deliver an employee benefits program</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/deliver-employee-benefits-program)
- [<span data-ttu-id="fce19-189">Skapa en ny förmån</span><span class="sxs-lookup"><span data-stu-id="fce19-189">Create a new benefit</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/create-new-benefit)
- [<span data-ttu-id="fce19-190">Definiera förmånsberättiganderegler och policyer</span><span class="sxs-lookup"><span data-stu-id="fce19-190">Define benefit eligibility rules and policies</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-benefit-eligibility-rules-policies)
- [<span data-ttu-id="fce19-191">Registrera och ta bort förmåner för arbetare</span><span class="sxs-lookup"><span data-stu-id="fce19-191">Enroll and remove benefits from workers</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-remove-benefits-workers)

#### <a name="compensation"></a><span data-ttu-id="fce19-192">Kompensation</span><span class="sxs-lookup"><span data-stu-id="fce19-192">Compensation</span></span> 

<span data-ttu-id="fce19-193">Kompensationshantering används för att styra du utbetalningen av grundlön och belöningar.</span><span class="sxs-lookup"><span data-stu-id="fce19-193">Compensation management is used to control the delivery of base pay and awards.</span></span> <span data-ttu-id="fce19-194">En medarbetares fasta grundlön och merithöjningar kontrolleras genom fasta kompensationsplaner.</span><span class="sxs-lookup"><span data-stu-id="fce19-194">An employee's fixed base pay and merit increases are controlled through fixed compensation plans.</span></span> <span data-ttu-id="fce19-195">Betalningen av incitament, till exempel bonusar, resultatbelöningar, aktieoptioner och anslag och även engångsbelöningar kontrolleras genom variabla kompensationsplaner.</span><span class="sxs-lookup"><span data-stu-id="fce19-195">The payment of incentive pay, such as bonus payments, performance awards, stock options, and grants, and also one-time awards, are controlled through variable compensation plans.</span></span>

<span data-ttu-id="fce19-196">Dayforce använder kompensationsinformation för att beräkna en medarbetares tim- eller årliga betalning.</span><span class="sxs-lookup"><span data-stu-id="fce19-196">Dayforce uses compensation information to calculate an employee's hourly or annual rate.</span></span> <span data-ttu-id="fce19-197">Fasta kompensationsplaner och lönekonverteringar är obligatoriska.</span><span class="sxs-lookup"><span data-stu-id="fce19-197">Fixed compensation plans and pay rate conversions are required.</span></span> <span data-ttu-id="fce19-198">Medarbetarna måste vara anslutna till en fast kompensationsplan.</span><span class="sxs-lookup"><span data-stu-id="fce19-198">Employees must be associated with a fixed compensation plan.</span></span>

<span data-ttu-id="fce19-199">Mer information om att kompensationsplaner finns i följande artiklar:</span><span class="sxs-lookup"><span data-stu-id="fce19-199">For more information about compensation plans, see the following articles:</span></span>

- [<span data-ttu-id="fce19-200">Skapa planer för fast kompensation</span><span class="sxs-lookup"><span data-stu-id="fce19-200">Create fixed compensation plans</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/create-fixed-compensation-plans)
- [<span data-ttu-id="fce19-201">Skapa planer för variabel kompensation</span><span class="sxs-lookup"><span data-stu-id="fce19-201">Create variable compensation plans</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/create-variable-compensation-plans)
- [<span data-ttu-id="fce19-202">Utveckla struktur och planer för lön/kompensation</span><span class="sxs-lookup"><span data-stu-id="fce19-202">Develop salary/compensation structure and plans</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/develop-salary-compensation-structure-plan)
- [<span data-ttu-id="fce19-203">Bearbeta kompensation</span><span class="sxs-lookup"><span data-stu-id="fce19-203">Process compensation</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/process-compensation)
- [<span data-ttu-id="fce19-204">Definiera kompensationsprocessen och beräkna resultat</span><span class="sxs-lookup"><span data-stu-id="fce19-204">Define compensation process and calculate results</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-compensation-process-calculate-results)
- [<span data-ttu-id="fce19-205">Registrera en medarbetare i en fast kompensationsplan</span><span class="sxs-lookup"><span data-stu-id="fce19-205">Enroll an employee in a fixed compensation plan</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-fixed-compensation-plan)
- [<span data-ttu-id="fce19-206">Registrera en medarbetare i en variabel kompensationsplan</span><span class="sxs-lookup"><span data-stu-id="fce19-206">Enroll an employee in a variable compensation plan</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-variable-compensation-plan)

#### <a name="jobs"></a><span data-ttu-id="fce19-207">Jobb</span><span class="sxs-lookup"><span data-stu-id="fce19-207">Jobs</span></span> 

<span data-ttu-id="fce19-208">Ett jobb är den samling uppgifter och ansvarsområden som avkrävs en person som utför ett jobb.</span><span class="sxs-lookup"><span data-stu-id="fce19-208">A job is a collection of the tasks and responsibilities that are required of a person who performs a job.</span></span> <span data-ttu-id="fce19-209">Mer information finns i följande artiklar:</span><span class="sxs-lookup"><span data-stu-id="fce19-209">For more information, see the following articles:</span></span>

- [<span data-ttu-id="fce19-210">Installera komponenter för ett jobb</span><span class="sxs-lookup"><span data-stu-id="fce19-210">Setting up the components of a job</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/create-job)
- [<span data-ttu-id="fce19-211">Definiera nya jobb</span><span class="sxs-lookup"><span data-stu-id="fce19-211">Define new jobs</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-jobs)

##### <a name="positions"></a><span data-ttu-id="fce19-212">Befattningar</span><span class="sxs-lookup"><span data-stu-id="fce19-212">Positions</span></span>

<span data-ttu-id="fce19-213">En befattning är ett exempel på ett enskilt jobb.</span><span class="sxs-lookup"><span data-stu-id="fce19-213">A position is an individual instance of a job.</span></span> <span data-ttu-id="fce19-214">Befattningen "Försäljningschef (öst)" är exempelvis en av de befattningar som associeras med jobbet "Försäljningschef."</span><span class="sxs-lookup"><span data-stu-id="fce19-214">For example, the "Sales manager (East)" position is one of the positions that are associated with the "Sales manager" job.</span></span> <span data-ttu-id="fce19-215">En befattning finns på en avdelning.</span><span class="sxs-lookup"><span data-stu-id="fce19-215">A position exists in a department.</span></span> <span data-ttu-id="fce19-216">Endast en enda medarbetare kan vara associerad med respektive befattning.</span><span class="sxs-lookup"><span data-stu-id="fce19-216">Only one worker can be associated with each position.</span></span>

<span data-ttu-id="fce19-217">Tänk på följande uppgifter och konfigurationsinformation när du ställer in befattningar:</span><span class="sxs-lookup"><span data-stu-id="fce19-217">Keep the following data and configuration in mind when you set up positions:</span></span>

- <span data-ttu-id="fce19-218">Befattning (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="fce19-218">Position (required)</span></span>
- <span data-ttu-id="fce19-219">Beskrivning (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="fce19-219">Description (required)</span></span>
- <span data-ttu-id="fce19-220">Jobb (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="fce19-220">Job (required)</span></span>
- <span data-ttu-id="fce19-221">Avdelning (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="fce19-221">Department (required)</span></span>
- <span data-ttu-id="fce19-222">Befattningstyp (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="fce19-222">Position type (required)</span></span>
- <span data-ttu-id="fce19-223">Heltidslön</span><span class="sxs-lookup"><span data-stu-id="fce19-223">Full-time equivalent</span></span>
- <span data-ttu-id="fce19-224">Ordinarie timmar per år (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="fce19-224">Annual regular hours (required)</span></span>
- <span data-ttu-id="fce19-225">Betalas av den juridiska personen (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="fce19-225">Paid by legal entity (required)</span></span>
- <span data-ttu-id="fce19-226">Lönecykel (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="fce19-226">Pay cycle (required)</span></span>
- <span data-ttu-id="fce19-227">Standardekonomisk dimension – kostnadsställe (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="fce19-227">Default financial dimension – Cost center (required)</span></span>
- <span data-ttu-id="fce19-228">Medarbetartilldelning – medarbetare, tilldelningsstart, tilldelningsslut, orsakskod</span><span class="sxs-lookup"><span data-stu-id="fce19-228">Worker assignment – Worker, assignment start, assignment end, reason code</span></span>

<span data-ttu-id="fce19-229">Om flera befattningar på samma avdelning är associerade med samma jobb konsolideras de till en enda befattning i Dayforce.</span><span class="sxs-lookup"><span data-stu-id="fce19-229">If multiple positions in the same department are associated with the same job, they are consolidated into a single position in Dayforce.</span></span>

<span data-ttu-id="fce19-230">Mer information finns i följande artiklar:</span><span class="sxs-lookup"><span data-stu-id="fce19-230">For more information, see the following articles:</span></span>

- [<span data-ttu-id="fce19-231">Organisera arbetsstyrkan med avdelningar, jobb och befattningar</span><span class="sxs-lookup"><span data-stu-id="fce19-231">Organize your workforce using departments, jobs, and positions</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/departments-jobs-positions#positions)
- [<span data-ttu-id="fce19-232">Ställ in befattningar</span><span class="sxs-lookup"><span data-stu-id="fce19-232">Set up positions</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/set-up-positions)

#### <a name="departments"></a><span data-ttu-id="fce19-233">Avdelningar</span><span class="sxs-lookup"><span data-stu-id="fce19-233">Departments</span></span>

<span data-ttu-id="fce19-234">En avdelning är en driftenhet som representerar en kategori eller verksamhetsområde inom en organisation.</span><span class="sxs-lookup"><span data-stu-id="fce19-234">A department is an operating unit that represents a category or functional area of an organization.</span></span> <span data-ttu-id="fce19-235">En avdelning är ansvarig för en viss del av organisationen, såsom försäljning, bokföring eller mänskliga resurser.</span><span class="sxs-lookup"><span data-stu-id="fce19-235">A department is responsible for a specific area of the organization, such as sales, accounting, or human resources.</span></span> <span data-ttu-id="fce19-236">Du kan använda avdelningar att rapportera om funktionella områden.</span><span class="sxs-lookup"><span data-stu-id="fce19-236">You can use departments to report on functional areas.</span></span> <span data-ttu-id="fce19-237">Avdelningar kan ha vinst och förlust.</span><span class="sxs-lookup"><span data-stu-id="fce19-237">Departments might have profit and loss responsibility.</span></span>

<span data-ttu-id="fce19-238">Mer information finns i följande artiklar:</span><span class="sxs-lookup"><span data-stu-id="fce19-238">For more information, see the following articles:</span></span>

- [<span data-ttu-id="fce19-239">Skapa en avdelning och associera den med avdelningshierarkin</span><span class="sxs-lookup"><span data-stu-id="fce19-239">Create a department and associate it with the department hierarchy</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/create-department-add-department-hierarchy)
- [<span data-ttu-id="fce19-240">Definiera nya avdelningar</span><span class="sxs-lookup"><span data-stu-id="fce19-240">Define new departments</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-departments)

#### <a name="pay-cycles-and-pay-periods"></a><span data-ttu-id="fce19-241">Lönecykler och löneperioder</span><span class="sxs-lookup"><span data-stu-id="fce19-241">Pay cycles and pay periods</span></span>

<span data-ttu-id="fce19-242">En lönecykel avgör hur ofta lönelistan körs, samt vilka specifika dagar som medarbetarna får betalt.</span><span class="sxs-lookup"><span data-stu-id="fce19-242">A pay cycle determines how often payroll is run and the specific days when workers are paid.</span></span> <span data-ttu-id="fce19-243">En lönecykel kan exempelvis vara månadsvis och medarbetarna få sin lön den sista dagen i månaden.</span><span class="sxs-lookup"><span data-stu-id="fce19-243">For example, a pay cycle might be monthly, and employees might be paid on the last day of the month.</span></span> <span data-ttu-id="fce19-244">Alternativt kan en lönecykel vara veckovis och medarbetarna få sin lön på tisdagen efter betalningsperiodens utgång.</span><span class="sxs-lookup"><span data-stu-id="fce19-244">Alternatively, a pay cycle might be weekly, and employees might be paid on the Tuesday after the end of the pay period.</span></span> <span data-ttu-id="fce19-245">Lönecykler tilldelas befattningar i syfte att styra när arbetare på dessa befattningar får sin lön.</span><span class="sxs-lookup"><span data-stu-id="fce19-245">Pay cycles are assigned to positions to control when workers in those positions are paid.</span></span>

<span data-ttu-id="fce19-246">När du har skapat lönecykler kan du generera betalningsperioder för respektive cykel.</span><span class="sxs-lookup"><span data-stu-id="fce19-246">After you create pay cycles, you can generate pay periods for each cycle.</span></span> <span data-ttu-id="fce19-247">Varje betalningsperiod innehåller ett standardbetalningsdatum som baseras på den information du anger.</span><span class="sxs-lookup"><span data-stu-id="fce19-247">Each pay period includes a default payment date that is based on information that you provide.</span></span> <span data-ttu-id="fce19-248">Du kan emellertid ändra standarddatumet för betalning i en löneperiod i syfte att tillåta undantag, till exempel när betalningsdatumet infaller på en allmän helgdag.</span><span class="sxs-lookup"><span data-stu-id="fce19-248">However, you can modify the default payment date in a pay period to allow for exceptions, such as when the payment date falls on a holiday.</span></span>

<span data-ttu-id="fce19-249">Följande information används i Dayforce:</span><span class="sxs-lookup"><span data-stu-id="fce19-249">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="fce19-250">Lönecykel (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="fce19-250">Pay cycle (required)</span></span>
- <span data-ttu-id="fce19-251">Lönecykelfrekvens (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="fce19-251">Pay cycle frequency (required)</span></span>
- <span data-ttu-id="fce19-252">Periodens startdatum (första löneperiod obligatorisk)</span><span class="sxs-lookup"><span data-stu-id="fce19-252">Period start date (first pay period required)</span></span>
- <span data-ttu-id="fce19-253">Standarddatum för betalning (första löneperiod obligatorisk)</span><span class="sxs-lookup"><span data-stu-id="fce19-253">Default payment date (first pay period required)</span></span>

<span data-ttu-id="fce19-254">Denna information är integrerad i Dayforce som lönegrupper och delas upp efter land eller region för respektive lönecykel.</span><span class="sxs-lookup"><span data-stu-id="fce19-254">This information is integrated with Dayforce as pay groups, and is separated by country or region for each pay cycle.</span></span> <span data-ttu-id="fce19-255">Minst en löneperiod måste genereras före integration.</span><span class="sxs-lookup"><span data-stu-id="fce19-255">At least one pay period must be generated before integration.</span></span> <span data-ttu-id="fce19-256">Dayforce genererar gruppkalendrar för lön och betalningsdatum utifrån startdatumet för den första löneperioden och det standarddatum för betalning som anges i Personal.</span><span class="sxs-lookup"><span data-stu-id="fce19-256">Dayforce generates pay group calendars and payment dates, based on the start date of the first pay period and the default payment date that is set up in Human Resources.</span></span>

#### <a name="earning-codes"></a><span data-ttu-id="fce19-257">Inkomstkoder</span><span class="sxs-lookup"><span data-stu-id="fce19-257">Earning codes</span></span>

<span data-ttu-id="fce19-258">Inkomstkoder identifierar individuellt alla typer av arbetstagarintäkter.</span><span class="sxs-lookup"><span data-stu-id="fce19-258">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="fce19-259">Koderna har olika parametrar som rör inkomster, till exempel redovisningsbestämmelser, skattelagar, rapporteringskrav, och gross up-kapacitet.</span><span class="sxs-lookup"><span data-stu-id="fce19-259">The codes have various parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span>

<span data-ttu-id="fce19-260">Följande information används i Dayforce:</span><span class="sxs-lookup"><span data-stu-id="fce19-260">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="fce19-261">Inkomstkod (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="fce19-261">Earning Code (required)</span></span>
- <span data-ttu-id="fce19-262">beskrivning</span><span class="sxs-lookup"><span data-stu-id="fce19-262">Description</span></span>
- <span data-ttu-id="fce19-263">Enhet</span><span class="sxs-lookup"><span data-stu-id="fce19-263">Unit of measure</span></span>
- <span data-ttu-id="fce19-264">Produktiv</span><span class="sxs-lookup"><span data-stu-id="fce19-264">Productive</span></span>

### <a name="worker-data"></a><span data-ttu-id="fce19-265">Medarbetardata</span><span class="sxs-lookup"><span data-stu-id="fce19-265">Worker data</span></span>

<span data-ttu-id="fce19-266">Poster för de olika typer av medarbetare som du har är viktiga för dina personal- och lönesystem.</span><span class="sxs-lookup"><span data-stu-id="fce19-266">Records for the various types of workers that you have are important to your human resources and payroll systems.</span></span> <span data-ttu-id="fce19-267">Den information du anger kan användas för att spåra medarbetare och personuppgifter.</span><span class="sxs-lookup"><span data-stu-id="fce19-267">The information that you enter can be used to track workers and personal information.</span></span>

<span data-ttu-id="fce19-268">För medarbetare kan du behålla följande information:</span><span class="sxs-lookup"><span data-stu-id="fce19-268">You can maintain the following information for workers:</span></span>

- <span data-ttu-id="fce19-269">**Grundläggande** – Grundläggande information om en medarbetare, till exempel kontaktinformation, demografisk information, identifikationsinformation, familjeinformation, status för militärtjänst, exilstatusinformation samt personliga och nödkontakter.</span><span class="sxs-lookup"><span data-stu-id="fce19-269">**Basic** – Maintain basic information about a worker, such as contact information, demographic information, identification information, family information, military service status, expatriate information, and personal and emergency contacts.</span></span>
- <span data-ttu-id="fce19-270">**Anställning** – Information om en medarbetares anställning, exempelvis företags- eller organisationstillhörighet, befattningstilldelning, start- och slutdatum, jobbtillgänglighet, anställningsvillkor, pension, semester- samt omplaceringsinformation.</span><span class="sxs-lookup"><span data-stu-id="fce19-270">**Employment** – Maintain information about a worker's employment, such as company or organization affiliation, position assignment, start and end dates, work eligibility, terms of employment, pension, vacation, and relocation information.</span></span>
- <span data-ttu-id="fce19-271">**Tjänstledighet och frånvaro** – Information om en medarbetares frånvaro, exempelvis jobbkalendrar, frånvarotransaktioner samt frånvaroinställningar.</span><span class="sxs-lookup"><span data-stu-id="fce19-271">**Leave and absence** – Maintain information about a worker's absences, such as working calendars, absence transactions, and absence setup.</span></span>
- <span data-ttu-id="fce19-272">**Ersättning och lön** – Information om en medarbetares ersättningsplaner och löneinformation, exempelvis plananmälan, utmärkelser, resultat, provision, skatteinformation, pensionering samt löneavdrag.</span><span class="sxs-lookup"><span data-stu-id="fce19-272">**Compensation and payroll** – Maintain information about a worker's compensation plans and payroll information, such as plan enrollment, awards, performance, commission, tax information, retirement, and salary deductions.</span></span>

<span data-ttu-id="fce19-273">När du anger medarbetarinformation, kom då ihåg följande uppgifter och konfigurationer som används i Dayforce.</span><span class="sxs-lookup"><span data-stu-id="fce19-273">When you enter worker information, keep in mind the following data and configurations that are used in Dayforce.</span></span>

#### <a name="general-information"></a><span data-ttu-id="fce19-274">Allmän information</span><span class="sxs-lookup"><span data-stu-id="fce19-274">General information</span></span>

- <span data-ttu-id="fce19-275">Anställningsnummer (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="fce19-275">Personnel number (required)</span></span>
- <span data-ttu-id="fce19-276">Förnamn (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="fce19-276">First name (required)</span></span>
- <span data-ttu-id="fce19-277">Efternamn (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="fce19-277">Last name (required)</span></span>
- <span data-ttu-id="fce19-278">Mellannamn</span><span class="sxs-lookup"><span data-stu-id="fce19-278">Middle name</span></span>
- <span data-ttu-id="fce19-279">Datum för tjänsteålder</span><span class="sxs-lookup"><span data-stu-id="fce19-279">Seniority date</span></span>
- <span data-ttu-id="fce19-280">Känt som</span><span class="sxs-lookup"><span data-stu-id="fce19-280">Known as</span></span>

#### <a name="personal-information"></a><span data-ttu-id="fce19-281">Personlig information</span><span class="sxs-lookup"><span data-stu-id="fce19-281">Personal information</span></span>

- <span data-ttu-id="fce19-282">Civilstånd (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="fce19-282">Marital status (required)</span></span>
- <span data-ttu-id="fce19-283">Födelsedatum (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="fce19-283">Birth date (required)</span></span>
- <span data-ttu-id="fce19-284">Könstillhörighet (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="fce19-284">Gender (required)</span></span>
- <span data-ttu-id="fce19-285">Person med funktionsnedsättningar</span><span class="sxs-lookup"><span data-stu-id="fce19-285">Person with disabilities</span></span>
- <span data-ttu-id="fce19-286">Medborgarskap, land, region (endast för Mexiko)</span><span class="sxs-lookup"><span data-stu-id="fce19-286">Nationality country region (only for Mexico)</span></span>

#### <a name="address-information"></a><span data-ttu-id="fce19-287">Adressinformation</span><span class="sxs-lookup"><span data-stu-id="fce19-287">Address information</span></span>

- <span data-ttu-id="fce19-288">Primär adress (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="fce19-288">Primary (required)</span></span>
- <span data-ttu-id="fce19-289">Land/region (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="fce19-289">Country/region (required)</span></span>
- <span data-ttu-id="fce19-290">Postnummer (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="fce19-290">Postal code (required)</span></span>
- <span data-ttu-id="fce19-291">Nummer (obligatoriskt) (endast för Mexiko)</span><span class="sxs-lookup"><span data-stu-id="fce19-291">Street Number (required) (Only for Mexico)</span></span>
- <span data-ttu-id="fce19-292">Byggnadskomplement (endast för Mexiko)</span><span class="sxs-lookup"><span data-stu-id="fce19-292">Building Complement (Only for Mexico)</span></span>
- <span data-ttu-id="fce19-293">Stad (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="fce19-293">City (required)</span></span>
- <span data-ttu-id="fce19-294">Delstat (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="fce19-294">State (required)</span></span>
- <span data-ttu-id="fce19-295">Region (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="fce19-295">County (required)</span></span>

#### <a name="contact-information"></a><span data-ttu-id="fce19-296">Kontaktinformation</span><span class="sxs-lookup"><span data-stu-id="fce19-296">Contact information</span></span> 

- <span data-ttu-id="fce19-297">Primär adress (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="fce19-297">Primary (required)</span></span>
- <span data-ttu-id="fce19-298">Kontaktnummer (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="fce19-298">Contact number (required)</span></span>
- <span data-ttu-id="fce19-299">Anknytning</span><span class="sxs-lookup"><span data-stu-id="fce19-299">Extension</span></span>

#### <a name="payroll-information-and-earning-codes"></a><span data-ttu-id="fce19-300">Löneinformation och inkomstkoder</span><span class="sxs-lookup"><span data-stu-id="fce19-300">Payroll information and earning codes</span></span>

<span data-ttu-id="fce19-301">Medarbetare kan tilldelas en viss inkomst till en viss betalningsfrekvens och ha en prioriterad betalningsmetod.</span><span class="sxs-lookup"><span data-stu-id="fce19-301">Employees may be assigned specific earnings at a given frequency of payment and have a preferred payment method.</span></span> <span data-ttu-id="fce19-302">Följande fält används i Dayforce för att garantera att dessa prioriteringar och inställningar används.</span><span class="sxs-lookup"><span data-stu-id="fce19-302">The following fields are used in Dayforce to help guarantee that those preferences and settings are used.</span></span>

##### <a name="earning-codes"></a><span data-ttu-id="fce19-303">Inkomstkoder</span><span class="sxs-lookup"><span data-stu-id="fce19-303">Earning codes</span></span>

- <span data-ttu-id="fce19-304">Befattning (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="fce19-304">Position (required)</span></span>
- <span data-ttu-id="fce19-305">Inkomstkod (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="fce19-305">Earning Code (required)</span></span>
- <span data-ttu-id="fce19-306">Frekvens (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="fce19-306">Frequency (required)</span></span>
- <span data-ttu-id="fce19-307">Belopp (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="fce19-307">Amount (required)</span></span>

##### <a name="payroll-information"></a><span data-ttu-id="fce19-308">Löneinformation</span><span class="sxs-lookup"><span data-stu-id="fce19-308">Payroll information</span></span>

- <span data-ttu-id="fce19-309">Betalningsmetod</span><span class="sxs-lookup"><span data-stu-id="fce19-309">Payment Method</span></span>
- <span data-ttu-id="fce19-310">Ekonomisk region (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="fce19-310">Economic Region (required)</span></span>
- <span data-ttu-id="fce19-311">ID för anställningsförmåner</span><span class="sxs-lookup"><span data-stu-id="fce19-311">Employee Benefits ID</span></span>
- <span data-ttu-id="fce19-312">Nationellt ID-nummer (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="fce19-312">National ID Number (required)</span></span>
- <span data-ttu-id="fce19-313">Militärtjänstgöring, nummer</span><span class="sxs-lookup"><span data-stu-id="fce19-313">Military Service Number</span></span>
- <span data-ttu-id="fce19-314">Skiftes-ID (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="fce19-314">Shift ID (required)</span></span>
- <span data-ttu-id="fce19-315">Skattenummer (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="fce19-315">Tax Number (required)</span></span>
- <span data-ttu-id="fce19-316">Fack-ID (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="fce19-316">Union ID (required)</span></span>
- <span data-ttu-id="fce19-317">Arbetsdags-ID (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="fce19-317">Work Day ID (required)</span></span>
- <span data-ttu-id="fce19-318">Arbetstillståndsnummer</span><span class="sxs-lookup"><span data-stu-id="fce19-318">Work Permit Number</span></span>

> [!NOTE]
> <span data-ttu-id="fce19-319">För betalsättet stöder Mexiko **Kontant**, **Check** (företagets fysiska check), samt **Elektronisk betalning**.</span><span class="sxs-lookup"><span data-stu-id="fce19-319">For the payment method, Mexico supports **Cash**, **Check** (the company's physical check), and **Electronic Payment**.</span></span> <span data-ttu-id="fce19-320">Om betalsättet np anges används **Check** som standard.</span><span class="sxs-lookup"><span data-stu-id="fce19-320">If np payment method is specified, **Check** is used by default.</span></span>

#### <a name="employment-details"></a><span data-ttu-id="fce19-321">Anställningsinformation</span><span class="sxs-lookup"><span data-stu-id="fce19-321">Employment details</span></span>

<span data-ttu-id="fce19-322">Detaljerad anställningshistorik används som viktig information i syfte att hämta en medarbetares anställnings-, uppsägnings- och återanställningsstatus i Dayforce.</span><span class="sxs-lookup"><span data-stu-id="fce19-322">Employment detail history is used as key information to derive an employee's hire, termination, and rehire statuses in Dayforce.</span></span> <span data-ttu-id="fce19-323">Dayforce stöder endast en aktiv anställningspost åt gången.</span><span class="sxs-lookup"><span data-stu-id="fce19-323">Dayforce supports only one active employment record at a time.</span></span>

- <span data-ttu-id="fce19-324">Startdatum för anställning (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="fce19-324">Employment start date (required)</span></span>
- <span data-ttu-id="fce19-325">Slutdatum för anställning</span><span class="sxs-lookup"><span data-stu-id="fce19-325">Employment end date</span></span>
- <span data-ttu-id="fce19-326">Startdatum</span><span class="sxs-lookup"><span data-stu-id="fce19-326">Start date</span></span>
- <span data-ttu-id="fce19-327">Justerat startdatum</span><span class="sxs-lookup"><span data-stu-id="fce19-327">Adjusted start date</span></span>
- <span data-ttu-id="fce19-328">Uppsägningsdatum (obligatoriskt vid uppsägning)</span><span class="sxs-lookup"><span data-stu-id="fce19-328">Termination date (required upon termination)</span></span>
- <span data-ttu-id="fce19-329">Uppsägningsorsak (obligatoriskt vid uppsägning)</span><span class="sxs-lookup"><span data-stu-id="fce19-329">Termination reason (required upon termination)</span></span>

<span data-ttu-id="fce19-330">Medarbetarens viktiga datum beräknas med hjälp av följande information.</span><span class="sxs-lookup"><span data-stu-id="fce19-330">An employee's key dates are derived by using the following information.</span></span>

| <span data-ttu-id="fce19-331">Personal</span><span class="sxs-lookup"><span data-stu-id="fce19-331">Human Resources</span></span>                | <span data-ttu-id="fce19-332">Dayforce</span><span class="sxs-lookup"><span data-stu-id="fce19-332">Dayforce</span></span>                                                                                             |
|-----------------------|------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="fce19-333">Senaste anställningsdatum</span><span class="sxs-lookup"><span data-stu-id="fce19-333">Most recent hire date</span></span> | <span data-ttu-id="fce19-334">Anställningsstart för aktuell, icke-uppsagd post för anställningshistorik</span><span class="sxs-lookup"><span data-stu-id="fce19-334">Employment start of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="fce19-335">Uppsägningsdatum</span><span class="sxs-lookup"><span data-stu-id="fce19-335">Termination date</span></span>      | <span data-ttu-id="fce19-336">Uppsägningsdatum för aktuell, icke-uppsagd post för anställningshistorik</span><span class="sxs-lookup"><span data-stu-id="fce19-336">Termination date of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="fce19-337">Startdatum</span><span class="sxs-lookup"><span data-stu-id="fce19-337">Start date</span></span>            | <span data-ttu-id="fce19-338">Justerat startdatum, startdatum eller anställningsstart för aktuell, inaktiv post för anställningshistorik</span><span class="sxs-lookup"><span data-stu-id="fce19-338">Adjusted start date, start date, or employment start of current non-active employment history record</span></span> |
| <span data-ttu-id="fce19-339">Ursprungligt anställningsdatum</span><span class="sxs-lookup"><span data-stu-id="fce19-339">Original hire date</span></span>    | <span data-ttu-id="fce19-340">Anställningsstart för tidigaste anställningshistorikpost</span><span class="sxs-lookup"><span data-stu-id="fce19-340">Employment start of earliest employment history record</span></span>                                               |

#### <a name="compensation"></a><span data-ttu-id="fce19-341">Kompensation</span><span class="sxs-lookup"><span data-stu-id="fce19-341">Compensation</span></span>

<span data-ttu-id="fce19-342">En fast kompensationsplan måste kopplas till varje medarbetares primära befattning under hela anställningsperioden.</span><span class="sxs-lookup"><span data-stu-id="fce19-342">A fixed compensation plan must be associated with every employee's primary position throughout an employment period.</span></span> <span data-ttu-id="fce19-343">Perioden inleds det datum då medarbetaren anställts (eller på anställningens startdatum) och fortsätter till och med uppsägningen.</span><span class="sxs-lookup"><span data-stu-id="fce19-343">This period starts on the date that the employee was hired (or the employment start date) and continues until termination.</span></span>

- <span data-ttu-id="fce19-344">Giltighetsdatum (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="fce19-344">Effective Date (required)</span></span>
- <span data-ttu-id="fce19-345">Utgångsdatum</span><span class="sxs-lookup"><span data-stu-id="fce19-345">Expiration date</span></span>
- <span data-ttu-id="fce19-346">Lönesats (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="fce19-346">Pay Rate (required)</span></span>
- <span data-ttu-id="fce19-347">Lönesatskonverteringar (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="fce19-347">Pay Rate Conversions (required)</span></span>
- <span data-ttu-id="fce19-348">Årlig motsvarighet (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="fce19-348">Annual equivalent (required)</span></span>
- <span data-ttu-id="fce19-349">Motsvarighet per timme (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="fce19-349">Hourly equivalent (required)</span></span>

<span data-ttu-id="fce19-350">Om en timanställd har flera befattningar importeras den fasta kompensationen för den primära befattningen till Dayforce som bastariff/-lön för medarbetaren.</span><span class="sxs-lookup"><span data-stu-id="fce19-350">If an hourly employee has multiple positions, the fixed compensation of the primary position is imported into Dayforce as the employee-level base rate/salary.</span></span> <span data-ttu-id="fce19-351">För icke-primära befattningar sparas timtariffen i motsvarande befattning i Dayforce.</span><span class="sxs-lookup"><span data-stu-id="fce19-351">For non-primary positions, the hourly rate is saved to the corresponding position in Dayforce.</span></span>

<span data-ttu-id="fce19-352">Om en fast anställd tjänsteman har flera befattningar hämtas den ackumulerade timtariffen och årslönen för samtliga aktiva befattningar och används som bastariff/-lön för medarbetarnivån.</span><span class="sxs-lookup"><span data-stu-id="fce19-352">If a salaried employee has multiple positions, the cumulative hour rate and annual salary across all active positions are derived and used as the employee-level base rate/salary.</span></span>

#### <a name="identification-numbers"></a><span data-ttu-id="fce19-353">Identifieringsnummer</span><span class="sxs-lookup"><span data-stu-id="fce19-353">Identification numbers</span></span>

##### <a name="social-security-identifier"></a><span data-ttu-id="fce19-354">Socialförsäkrings-identifierare</span><span class="sxs-lookup"><span data-stu-id="fce19-354">Social Security identifier</span></span> 

<span data-ttu-id="fce19-355">Alla medarbetare måste ha en primär identifierare.</span><span class="sxs-lookup"><span data-stu-id="fce19-355">Every employee must have one primary identifier.</span></span> <span data-ttu-id="fce19-356">Denna identifierare måste vara av identifieringstypen **SSN**.</span><span class="sxs-lookup"><span data-stu-id="fce19-356">This identifier must be of **SSN** identification type.</span></span> <span data-ttu-id="fce19-357">I Dayforce hämtas den automatiskt som den socialförsäkringsidentifierare för anställd som krävs för anställning.</span><span class="sxs-lookup"><span data-stu-id="fce19-357">In Dayforce, it's automatically derived as the employee's Social Security identifier that is required for hire.</span></span>

- <span data-ttu-id="fce19-358">Primär adress (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="fce19-358">Primary (required)</span></span>
- <span data-ttu-id="fce19-359">Identifieringstyp = "SSN"</span><span class="sxs-lookup"><span data-stu-id="fce19-359">Identification Type = "SSN"</span></span>
- <span data-ttu-id="fce19-360">Utfärdat den</span><span class="sxs-lookup"><span data-stu-id="fce19-360">Issued Date</span></span>
- <span data-ttu-id="fce19-361">Utgångsdatum</span><span class="sxs-lookup"><span data-stu-id="fce19-361">Expiration Date</span></span>

<span data-ttu-id="fce19-362">Medarbetare kan deklarera flera ID-nummer med ID-typen **SSN**.</span><span class="sxs-lookup"><span data-stu-id="fce19-362">Employees can declare multiple identification numbers of the **SSN** identification type.</span></span> <span data-ttu-id="fce19-363">Endast posten som är markerad som **Primär** integreras emellertid i Dayforce, oavsett om numret är aktivt eller har upphört att gälla.</span><span class="sxs-lookup"><span data-stu-id="fce19-363">However, only the record that is marked as **Primary** is integrated into Dayforce, regardless of whether the number is active or expired.</span></span>

#### <a name="bank-accounts-and-disbursements"></a><span data-ttu-id="fce19-364">Bankkonton och utbetalningar</span><span class="sxs-lookup"><span data-stu-id="fce19-364">Bank accounts and disbursements</span></span>

<span data-ttu-id="fce19-365">Giltig bankkontoinformation måste anges för varje medarbetare som väljer att få sin lön via bankkontoöverföringar.</span><span class="sxs-lookup"><span data-stu-id="fce19-365">Valid bank account information must be entered for any employee who chooses to be paid via bank account transfers.</span></span>

| <span data-ttu-id="fce19-366">Personal</span><span class="sxs-lookup"><span data-stu-id="fce19-366">Human Resources</span></span>                         | <span data-ttu-id="fce19-367">Dayforce</span><span class="sxs-lookup"><span data-stu-id="fce19-367">Dayforce</span></span>                                                                                                    |
|--------------------------------|-------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="fce19-368">Bankkontonummer (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="fce19-368">Bank account number (required)</span></span> |                                                                                                             |
| <span data-ttu-id="fce19-369">SWIFT-kod (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="fce19-369">SWIFT code (required)</span></span>          | <span data-ttu-id="fce19-370">Fältet **Bank-ID** används när löner bearbetas i Mexiko.</span><span class="sxs-lookup"><span data-stu-id="fce19-370">**Bank ID** field used when processing payroll in Mexico.</span></span>                                                             |
| <span data-ttu-id="fce19-371">Filialnummer (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="fce19-371">Branch number (required)</span></span>       |                                                                                                             |
| <span data-ttu-id="fce19-372">Bankkontotyp (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="fce19-372">Bank account type (required)</span></span>   | <span data-ttu-id="fce19-373">Fältet **Kontotyp** används när löner bearbetas i Mexiko.</span><span class="sxs-lookup"><span data-stu-id="fce19-373">**Account type** field used when processing payroll in Mexico.</span></span> <span data-ttu-id="fce19-374">Värden som stöds inkluderar **Check** och **Lönelista**.</span><span class="sxs-lookup"><span data-stu-id="fce19-374">Supported values include **Checking** and **Payroll**.</span></span> |

> [!NOTE]
> <span data-ttu-id="fce19-375">Medarbetare som väljer att få lön via bankkontoöverföring måste ange en länk till ett restkonto tillhörande en juridisk person med primär adress i Mexiko och som är associerad med ett giltigt bankkonto från en mexikansk bank.</span><span class="sxs-lookup"><span data-stu-id="fce19-375">Employees who choose to be paid via bank account transfers must provide a link to a remainder account that is under a legal entity that has its primary address in Mexico and associated with a valid bank account from a Mexican bank.</span></span> <span data-ttu-id="fce19-376">Alla övriga restkonton ignoreras.</span><span class="sxs-lookup"><span data-stu-id="fce19-376">All other non-remainder accounts are ignored.</span></span>

#### <a name="address-information"></a><span data-ttu-id="fce19-377">Adressinformation</span><span class="sxs-lookup"><span data-stu-id="fce19-377">Address information</span></span>

<span data-ttu-id="fce19-378">Alla medarbetare måste ha en primär plats.</span><span class="sxs-lookup"><span data-stu-id="fce19-378">Every employee must have one primary location.</span></span> <span data-ttu-id="fce19-379">Den här platsen används i Dayforce i syfte att fastställa medarbetarens primära hemort i skattesyfte.</span><span class="sxs-lookup"><span data-stu-id="fce19-379">In Dayforce, this location is used to determine the employee's primary residence for tax purposes.</span></span>

- <span data-ttu-id="fce19-380">Primär adress (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="fce19-380">Primary (required)</span></span>
- <span data-ttu-id="fce19-381">Land/region (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="fce19-381">Country/region (required)</span></span>
- <span data-ttu-id="fce19-382">Postnummer (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="fce19-382">Zip/postal code (required)</span></span>
- <span data-ttu-id="fce19-383">Gata (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="fce19-383">Street (required)</span></span>
- <span data-ttu-id="fce19-384">Nummer (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="fce19-384">Street Number (required)</span></span>
- <span data-ttu-id="fce19-385">Byggnadskomplement</span><span class="sxs-lookup"><span data-stu-id="fce19-385">Building Complement</span></span>
- <span data-ttu-id="fce19-386">Stad (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="fce19-386">City (required)</span></span>
- <span data-ttu-id="fce19-387">Delstat (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="fce19-387">State (required)</span></span>
- <span data-ttu-id="fce19-388">Region (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="fce19-388">County (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-united-states-and-canada"></a><span data-ttu-id="fce19-389">Konfigurera dina data för att generera lön i USA och Kanada</span><span class="sxs-lookup"><span data-stu-id="fce19-389">Configure your data to generate payroll in United States and Canada</span></span>

<span data-ttu-id="fce19-390">Om du genererar lön för medarbetare i USA och Kanada måste följande element konfigureras:</span><span class="sxs-lookup"><span data-stu-id="fce19-390">If you're generating pay for employees in the United States and Canada, the following elements must be configured:</span></span>

- <span data-ttu-id="fce19-391">Avdelningar är obligatoriska vid befattningarna:</span><span class="sxs-lookup"><span data-stu-id="fce19-391">Departments are required on positions.</span></span>
- <span data-ttu-id="fce19-392">Kostnadsställen måste ställas in som ekonomiska dimensioner och måste vara det första elementet i standardsträngen för ekonomisk dimension.</span><span class="sxs-lookup"><span data-stu-id="fce19-392">Cost centers must be set as financial dimensions and must be the first element in the default financial dimension string.</span></span>

> [!NOTE] 
> <span data-ttu-id="fce19-393">Du kan konfigurera Personal att kräva att befattningar anger en avdelning.</span><span class="sxs-lookup"><span data-stu-id="fce19-393">You can configure Human Resources to require that Positions specify a Department.</span></span> <span data-ttu-id="fce19-394">Gör detta genom att gå till **delade befattningar i Personal > befattningar > kräver avdelningar för befattningar**.</span><span class="sxs-lookup"><span data-stu-id="fce19-394">To do this, go to **Human Resources Shared Positions > Positions > Require departments on positions**.</span></span> <span data-ttu-id="fce19-395">Vi rekommenderar att den här inställningen tillämpas för integration.</span><span class="sxs-lookup"><span data-stu-id="fce19-395">We recommend that this setting be enforced for the integration.</span></span>

### <a name="job-types"></a><span data-ttu-id="fce19-396">Jobbtyper</span><span class="sxs-lookup"><span data-stu-id="fce19-396">Job types</span></span>

<span data-ttu-id="fce19-397">Jobbtyper används för att gruppera liknande jobb i kategorier.</span><span class="sxs-lookup"><span data-stu-id="fce19-397">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="fce19-398">Jobbtyper krävs för att bearbeta lön i USA och Kanada.</span><span class="sxs-lookup"><span data-stu-id="fce19-398">Job types are required in order to process payroll in the United States and Canada.</span></span> <span data-ttu-id="fce19-399">Några exempel på jobbtyper är heltid och deltid, eller fast lön och timpenning.</span><span class="sxs-lookup"><span data-stu-id="fce19-399">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="fce19-400">Jobbtyper mappas till Dayforce som lönetyper som anger huruvida en anställd arbetar per timme eller har fast lön.</span><span class="sxs-lookup"><span data-stu-id="fce19-400">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="fce19-401">Följande jobbtyper och beskrivningar krävs.</span><span class="sxs-lookup"><span data-stu-id="fce19-401">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="fce19-402">Jobbtyp</span><span class="sxs-lookup"><span data-stu-id="fce19-402">Job type</span></span>   | <span data-ttu-id="fce19-403">beskrivning</span><span class="sxs-lookup"><span data-stu-id="fce19-403">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="fce19-404">Varje timme</span><span class="sxs-lookup"><span data-stu-id="fce19-404">Hourly</span></span>     | <span data-ttu-id="fce19-405">Varje timme</span><span class="sxs-lookup"><span data-stu-id="fce19-405">Hourly</span></span>      |
| <span data-ttu-id="fce19-406">Fast lön</span><span class="sxs-lookup"><span data-stu-id="fce19-406">Salaried</span></span>   | <span data-ttu-id="fce19-407">Fast lön</span><span class="sxs-lookup"><span data-stu-id="fce19-407">Salaried</span></span>    |

### <a name="position-types"></a><span data-ttu-id="fce19-408">Befattningstyper</span><span class="sxs-lookup"><span data-stu-id="fce19-408">Position types</span></span> 

<span data-ttu-id="fce19-409">Du kan använda befattningstyper för att beskriva huruvida befattningen är på heltid, deltid eller annat.</span><span class="sxs-lookup"><span data-stu-id="fce19-409">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="fce19-410">Befattningstyper mappas till Dayforce som löneklasser som anger huruvida en anställd arbetar heltid eller deltid.</span><span class="sxs-lookup"><span data-stu-id="fce19-410">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="fce19-411">Följande befattningstyper och beskrivningar krävs.</span><span class="sxs-lookup"><span data-stu-id="fce19-411">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="fce19-412">Befattningstyp</span><span class="sxs-lookup"><span data-stu-id="fce19-412">Position type</span></span>   | <span data-ttu-id="fce19-413">beskrivning</span><span class="sxs-lookup"><span data-stu-id="fce19-413">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="fce19-414">Heltid</span><span class="sxs-lookup"><span data-stu-id="fce19-414">Full-time</span></span>       | <span data-ttu-id="fce19-415">Heltidsanställd</span><span class="sxs-lookup"><span data-stu-id="fce19-415">Full time employee</span></span> |
| <span data-ttu-id="fce19-416">Deltid</span><span class="sxs-lookup"><span data-stu-id="fce19-416">Part-time</span></span>       | <span data-ttu-id="fce19-417">Deltidsanställd</span><span class="sxs-lookup"><span data-stu-id="fce19-417">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="fce19-418">Orsakskoder</span><span class="sxs-lookup"><span data-stu-id="fce19-418">Reason codes</span></span>

<span data-ttu-id="fce19-419">Orsakskoder innehåller information om statusen för en medarbetare.</span><span class="sxs-lookup"><span data-stu-id="fce19-419">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="fce19-420">Orsakskoder mappas till Dayforce som statusanledningar som anger orsaken till ändringar i en medarbetares befattning eller anställningsstatus.</span><span class="sxs-lookup"><span data-stu-id="fce19-420">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="fce19-421">Följande orsakskoder och -beskrivningar krävs.</span><span class="sxs-lookup"><span data-stu-id="fce19-421">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="fce19-422">Orsakskod</span><span class="sxs-lookup"><span data-stu-id="fce19-422">Reason code</span></span>    | <span data-ttu-id="fce19-423">beskrivning</span><span class="sxs-lookup"><span data-stu-id="fce19-423">Description</span></span>      | <span data-ttu-id="fce19-424">Tillämpliga scenarier</span><span class="sxs-lookup"><span data-stu-id="fce19-424">Applicable scenarios</span></span> |
|----------------|------------------|----------------------|
| <span data-ttu-id="fce19-425">EGEN UPPSÄGNING</span><span class="sxs-lookup"><span data-stu-id="fce19-425">RESIGNATION</span></span>    | <span data-ttu-id="fce19-426">Egen uppsägning</span><span class="sxs-lookup"><span data-stu-id="fce19-426">Resignation</span></span>      | <span data-ttu-id="fce19-427">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="fce19-427">Terminate worker</span></span>     |
| <span data-ttu-id="fce19-428">UPPSÄGNING</span><span class="sxs-lookup"><span data-stu-id="fce19-428">TERMINATION</span></span>    | <span data-ttu-id="fce19-429">Uppsägning</span><span class="sxs-lookup"><span data-stu-id="fce19-429">Termination</span></span>      | <span data-ttu-id="fce19-430">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="fce19-430">Terminate worker</span></span>     |
| <span data-ttu-id="fce19-431">PENSION</span><span class="sxs-lookup"><span data-stu-id="fce19-431">RETIREMENT</span></span>     | <span data-ttu-id="fce19-432">Pension</span><span class="sxs-lookup"><span data-stu-id="fce19-432">Retirement</span></span>       | <span data-ttu-id="fce19-433">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="fce19-433">Terminate worker</span></span>     |
| <span data-ttu-id="fce19-434">ÖVRIGT</span><span class="sxs-lookup"><span data-stu-id="fce19-434">OTHER</span></span>          | <span data-ttu-id="fce19-435">Andra orsaker</span><span class="sxs-lookup"><span data-stu-id="fce19-435">Other Reasons</span></span>    | <span data-ttu-id="fce19-436">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="fce19-436">Terminate worker</span></span>     |
| <span data-ttu-id="fce19-437">DÖDSFALL</span><span class="sxs-lookup"><span data-stu-id="fce19-437">DEATH</span></span>          | <span data-ttu-id="fce19-438">Dödsfall</span><span class="sxs-lookup"><span data-stu-id="fce19-438">Death</span></span>            | <span data-ttu-id="fce19-439">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="fce19-439">Terminate worker</span></span>     |
| <span data-ttu-id="fce19-440">TJÄNSTLEDIGHET</span><span class="sxs-lookup"><span data-stu-id="fce19-440">LEAVEOFABSENCE</span></span> | <span data-ttu-id="fce19-441">Tjänstledighet</span><span class="sxs-lookup"><span data-stu-id="fce19-441">Leave of Absence</span></span> | <span data-ttu-id="fce19-442">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="fce19-442">Terminate worker</span></span>     |
| <span data-ttu-id="fce19-443">KONTRAKTSLUT</span><span class="sxs-lookup"><span data-stu-id="fce19-443">CONTRACTEND</span></span>    | <span data-ttu-id="fce19-444">Kontraktslut</span><span class="sxs-lookup"><span data-stu-id="fce19-444">End of Contract</span></span>  | <span data-ttu-id="fce19-445">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="fce19-445">Terminate worker</span></span>     |
| <span data-ttu-id="fce19-446">LÖNEÄNDRING</span><span class="sxs-lookup"><span data-stu-id="fce19-446">SALARYCHANGE</span></span>   | <span data-ttu-id="fce19-447">Löneändring</span><span class="sxs-lookup"><span data-stu-id="fce19-447">Change of Salary</span></span> | <span data-ttu-id="fce19-448">Kompensation</span><span class="sxs-lookup"><span data-stu-id="fce19-448">Compensation</span></span>         |

### <a name="marital-status"></a><span data-ttu-id="fce19-449">Civilstånd</span><span class="sxs-lookup"><span data-stu-id="fce19-449">Marital status</span></span>

<span data-ttu-id="fce19-450">Civilståndsvärden mappas till Dayforce och översätts på lämpligt sätt till giltiga värden i samband med integrering.</span><span class="sxs-lookup"><span data-stu-id="fce19-450">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="fce19-451">Följande tabell visar hur civilståndsvärden mappas till Dayforce.</span><span class="sxs-lookup"><span data-stu-id="fce19-451">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="fce19-452">Personal</span><span class="sxs-lookup"><span data-stu-id="fce19-452">Human Resources</span></span>                 | <span data-ttu-id="fce19-453">Dayforce</span><span class="sxs-lookup"><span data-stu-id="fce19-453">Dayforce</span></span>             |
|------------------------|----------------------|
| <span data-ttu-id="fce19-454">Gift</span><span class="sxs-lookup"><span data-stu-id="fce19-454">Married</span></span>                | <span data-ttu-id="fce19-455">Gift</span><span class="sxs-lookup"><span data-stu-id="fce19-455">Married</span></span>              |
| <span data-ttu-id="fce19-456">Ett</span><span class="sxs-lookup"><span data-stu-id="fce19-456">Single</span></span>                 | <span data-ttu-id="fce19-457">Ett</span><span class="sxs-lookup"><span data-stu-id="fce19-457">Single</span></span>               |
| <span data-ttu-id="fce19-458">Änka/Änkeman</span><span class="sxs-lookup"><span data-stu-id="fce19-458">Widowed</span></span>                | <span data-ttu-id="fce19-459">Änka/Änkeman</span><span class="sxs-lookup"><span data-stu-id="fce19-459">Widowed</span></span>              |
| <span data-ttu-id="fce19-460">Skild</span><span class="sxs-lookup"><span data-stu-id="fce19-460">Divorced</span></span>               | <span data-ttu-id="fce19-461">Frånskild</span><span class="sxs-lookup"><span data-stu-id="fce19-461">Divorced</span></span>             |
| <span data-ttu-id="fce19-462">Registrerat partnerskap</span><span class="sxs-lookup"><span data-stu-id="fce19-462">Registered Partnership</span></span> | <span data-ttu-id="fce19-463">Samboförhållande</span><span class="sxs-lookup"><span data-stu-id="fce19-463">Domestic Partnership</span></span> |
| <span data-ttu-id="fce19-464">Inga</span><span class="sxs-lookup"><span data-stu-id="fce19-464">None</span></span>                   | <span data-ttu-id="fce19-465">Inga</span><span class="sxs-lookup"><span data-stu-id="fce19-465">None</span></span>                 |
| <span data-ttu-id="fce19-466">Sambo</span><span class="sxs-lookup"><span data-stu-id="fce19-466">Cohabiting</span></span>             | <span data-ttu-id="fce19-467">Sambo</span><span class="sxs-lookup"><span data-stu-id="fce19-467">Cohabiting</span></span>           |

### <a name="gender"></a><span data-ttu-id="fce19-468">Kön</span><span class="sxs-lookup"><span data-stu-id="fce19-468">Gender</span></span>

<span data-ttu-id="fce19-469">Könsbeteckningar mappas till Dayforce och översätts på lämpligt sätt till giltiga värden i samband med integrering.</span><span class="sxs-lookup"><span data-stu-id="fce19-469">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="fce19-470">Följande tabell visar hur könsbeteckningar mappas till Dayforce.</span><span class="sxs-lookup"><span data-stu-id="fce19-470">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="fce19-471">Personal</span><span class="sxs-lookup"><span data-stu-id="fce19-471">Human Resources</span></span>       | <span data-ttu-id="fce19-472">Dayforce</span><span class="sxs-lookup"><span data-stu-id="fce19-472">Dayforce</span></span>        |
|--------------|-----------------|
| <span data-ttu-id="fce19-473">Man</span><span class="sxs-lookup"><span data-stu-id="fce19-473">Male</span></span>         | <span data-ttu-id="fce19-474">Man</span><span class="sxs-lookup"><span data-stu-id="fce19-474">Male</span></span>            |
| <span data-ttu-id="fce19-475">Kvinna</span><span class="sxs-lookup"><span data-stu-id="fce19-475">Female</span></span>       | <span data-ttu-id="fce19-476">Kvinna</span><span class="sxs-lookup"><span data-stu-id="fce19-476">Female</span></span>          |
| <span data-ttu-id="fce19-477">Icke-specifik</span><span class="sxs-lookup"><span data-stu-id="fce19-477">Non-specific</span></span> | <span data-ttu-id="fce19-478">*Stöds ej*</span><span class="sxs-lookup"><span data-stu-id="fce19-478">*Not supported*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="fce19-479">Inkomstkoder</span><span class="sxs-lookup"><span data-stu-id="fce19-479">Earning codes</span></span>

<span data-ttu-id="fce19-480">Inkomstkoder identifierar individuellt alla typer av arbetstagarintäkter.</span><span class="sxs-lookup"><span data-stu-id="fce19-480">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="fce19-481">Koderna omfattar flera olika parametrar som rör inkomster, till exempel redovisningsbestämmelser, skattelagar, rapporteringskrav och gross up-kapacitet.</span><span class="sxs-lookup"><span data-stu-id="fce19-481">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="fce19-482">Om en frekvens som inte stöds används tillämpas frekvensen **Varje lön** som standard för beräkningen.</span><span class="sxs-lookup"><span data-stu-id="fce19-482">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="fce19-483">Frekvenser som stöds</span><span class="sxs-lookup"><span data-stu-id="fce19-483">Supported frequencies</span></span>

- <span data-ttu-id="fce19-484">Allt</span><span class="sxs-lookup"><span data-stu-id="fce19-484">All</span></span>
- <span data-ttu-id="fce19-485">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="fce19-485">EVERYPAY</span></span>
- <span data-ttu-id="fce19-486">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="fce19-486">EACHPAYPERIOD</span></span>
- <span data-ttu-id="fce19-487">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="fce19-487">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="fce19-488">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="fce19-488">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="fce19-489">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="fce19-489">1OFMTH</span></span>
- <span data-ttu-id="fce19-490">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="fce19-490">LASTOFMTH</span></span>
- <span data-ttu-id="fce19-491">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="fce19-491">2OFMTH</span></span>
- <span data-ttu-id="fce19-492">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="fce19-492">3OFMTH</span></span>
- <span data-ttu-id="fce19-493">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="fce19-493">4OFMTH</span></span>
- <span data-ttu-id="fce19-494">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="fce19-494">5OFMTH</span></span>
- <span data-ttu-id="fce19-495">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="fce19-495">1N2OFMTH</span></span>
- <span data-ttu-id="fce19-496">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="fce19-496">3N4OFMTH</span></span>
- <span data-ttu-id="fce19-497">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="fce19-497">1N3OFMTH</span></span>
- <span data-ttu-id="fce19-498">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="fce19-498">1N4OFMTH</span></span>
- <span data-ttu-id="fce19-499">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="fce19-499">2N3OFMTH</span></span>
- <span data-ttu-id="fce19-500">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="fce19-500">2N4OFMTH</span></span>
- <span data-ttu-id="fce19-501">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="fce19-501">1N2N3OFMTH</span></span>
- <span data-ttu-id="fce19-502">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="fce19-502">1N2N4OFMTH</span></span>
- <span data-ttu-id="fce19-503">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="fce19-503">1N3N4OFMTH</span></span>
- <span data-ttu-id="fce19-504">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="fce19-504">2N3N4OFMTH</span></span>
- <span data-ttu-id="fce19-505">1N2N3N4OFMTH – 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="fce19-505">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="fce19-506">2N3N4N5OFMth – 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="fce19-506">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="fce19-507">1OFQTR – 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="fce19-507">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="fce19-508">LASTOFQTR – LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="fce19-508">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="fce19-509">LASTMTHOFQTR – LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="fce19-509">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="fce19-510">1OFYEAR – 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="fce19-510">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="fce19-511">LASTOFYEAR – LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="fce19-511">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="fce19-512">NOVNDECOFYEAR – NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="fce19-512">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="fce19-513">Adresser</span><span class="sxs-lookup"><span data-stu-id="fce19-513">Addresses</span></span>

<span data-ttu-id="fce19-514">Identifiering av specifika lands-/region-, delstats- och region(kommun)-koder kräver särskilda format som Dayforce och leverantörer i respektive land/region kan känna igen.</span><span class="sxs-lookup"><span data-stu-id="fce19-514">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="fce19-515">Även om formatet för städer är flexibelt måste varje stad associeras med en delstat.</span><span class="sxs-lookup"><span data-stu-id="fce19-515">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="fce19-516">Personal</span><span class="sxs-lookup"><span data-stu-id="fce19-516">Human Resources</span></span>          | <span data-ttu-id="fce19-517">Dayforce</span><span class="sxs-lookup"><span data-stu-id="fce19-517">Dayforce</span></span>              |
|-----------------|-----------------------|
| <span data-ttu-id="fce19-518">Land/region</span><span class="sxs-lookup"><span data-stu-id="fce19-518">Country/Region</span></span>  | <span data-ttu-id="fce19-519">Landskod</span><span class="sxs-lookup"><span data-stu-id="fce19-519">Country Code</span></span>          |
| <span data-ttu-id="fce19-520">Postnummer</span><span class="sxs-lookup"><span data-stu-id="fce19-520">Zip/Postal Code</span></span> | <span data-ttu-id="fce19-521">Postnummer</span><span class="sxs-lookup"><span data-stu-id="fce19-521">Postal Code</span></span>           |
| <span data-ttu-id="fce19-522">Stat</span><span class="sxs-lookup"><span data-stu-id="fce19-522">State</span></span>           | <span data-ttu-id="fce19-523">Delstatskod</span><span class="sxs-lookup"><span data-stu-id="fce19-523">State Code</span></span>            |
| <span data-ttu-id="fce19-524">Ort</span><span class="sxs-lookup"><span data-stu-id="fce19-524">City</span></span>            | <span data-ttu-id="fce19-525">Ort</span><span class="sxs-lookup"><span data-stu-id="fce19-525">City</span></span>                  |
| <span data-ttu-id="fce19-526">Län</span><span class="sxs-lookup"><span data-stu-id="fce19-526">County</span></span>          | <span data-ttu-id="fce19-527">Region (kommun)</span><span class="sxs-lookup"><span data-stu-id="fce19-527">County (Municipality)</span></span> |
| <span data-ttu-id="fce19-528">Gata</span><span class="sxs-lookup"><span data-stu-id="fce19-528">Street</span></span>          | <span data-ttu-id="fce19-529">Adressrad 1</span><span class="sxs-lookup"><span data-stu-id="fce19-529">Address Line 1</span></span>        |

### <a name="tax-regions"></a><span data-ttu-id="fce19-530">Skatteregioner</span><span class="sxs-lookup"><span data-stu-id="fce19-530">Tax regions</span></span>

<span data-ttu-id="fce19-531">Skatteregioner används för att bestämma vilken skattesats som ska användas vid lönegenerering.</span><span class="sxs-lookup"><span data-stu-id="fce19-531">Tax regions are used to determine the appropriate tax that should be applied during payroll generation.</span></span> <span data-ttu-id="fce19-532">Skatteregioner mappas till Dayforce som platsadresser.</span><span class="sxs-lookup"><span data-stu-id="fce19-532">Tax regions are mapped to Dayforce as location addresses.</span></span> <span data-ttu-id="fce19-533">Förvald skatteregion måste associeras med medarbetarens aktiva befattning.</span><span class="sxs-lookup"><span data-stu-id="fce19-533">The default tax region must be associated with the worker's active position.</span></span> 

- <span data-ttu-id="fce19-534">Skatteregion (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="fce19-534">Tax region (required)</span></span>
- <span data-ttu-id="fce19-535">Land/region (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="fce19-535">Country/Region (required)</span></span>
- <span data-ttu-id="fce19-536">Delstat (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="fce19-536">State (required)</span></span>
- <span data-ttu-id="fce19-537">Län</span><span class="sxs-lookup"><span data-stu-id="fce19-537">County</span></span> 
- <span data-ttu-id="fce19-538">Stad (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="fce19-538">City (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-mexico"></a><span data-ttu-id="fce19-539">Konfigurera dina data för att generera lön i Mexiko</span><span class="sxs-lookup"><span data-stu-id="fce19-539">Configure your data to generate payroll in Mexico</span></span>

<span data-ttu-id="fce19-540">Om du genererar lön för medarbetare i Mexiko måste följande element konfigureras:</span><span class="sxs-lookup"><span data-stu-id="fce19-540">If you're generating pay for employees in Mexico, the following elements must be configured:</span></span>

- <span data-ttu-id="fce19-541">Avdelningar är obligatoriska vid befattningarna:</span><span class="sxs-lookup"><span data-stu-id="fce19-541">Departments are required on positions.</span></span>
- <span data-ttu-id="fce19-542">Kostnadsställen måste ställas in som ekonomiska dimensioner och måste vara det första elementet i standardsträngen för ekonomisk dimension.</span><span class="sxs-lookup"><span data-stu-id="fce19-542">Cost centers must be set as financial dimensions and must be the first element in the Default Financial Dimension string.</span></span>

### <a name="job-types"></a><span data-ttu-id="fce19-543">Jobbtyper</span><span class="sxs-lookup"><span data-stu-id="fce19-543">Job types</span></span>

<span data-ttu-id="fce19-544">Jobbtyper används för att gruppera liknande jobb i kategorier.</span><span class="sxs-lookup"><span data-stu-id="fce19-544">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="fce19-545">Jobbtyper krävs för att bearbeta löner i Mexiko.</span><span class="sxs-lookup"><span data-stu-id="fce19-545">Job types are required in order to process payroll in Mexico.</span></span> <span data-ttu-id="fce19-546">Några exempel på jobbtyper är heltid och deltid, eller fast lön och timpenning.</span><span class="sxs-lookup"><span data-stu-id="fce19-546">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="fce19-547">Jobbtyper mappas till Dayforce som lönetyper som anger huruvida en anställd arbetar per timme eller har fast lön.</span><span class="sxs-lookup"><span data-stu-id="fce19-547">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="fce19-548">Följande jobbtyper och beskrivningar krävs.</span><span class="sxs-lookup"><span data-stu-id="fce19-548">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="fce19-549">Jobbtyp</span><span class="sxs-lookup"><span data-stu-id="fce19-549">Job type</span></span>   | <span data-ttu-id="fce19-550">beskrivning</span><span class="sxs-lookup"><span data-stu-id="fce19-550">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="fce19-551">Varje timme</span><span class="sxs-lookup"><span data-stu-id="fce19-551">Hourly</span></span>     | <span data-ttu-id="fce19-552">MX Varje timme</span><span class="sxs-lookup"><span data-stu-id="fce19-552">MX Hourly</span></span>   |
| <span data-ttu-id="fce19-553">Fast lön</span><span class="sxs-lookup"><span data-stu-id="fce19-553">Salaried</span></span>   | <span data-ttu-id="fce19-554">MX Fast lön</span><span class="sxs-lookup"><span data-stu-id="fce19-554">MX Salaried</span></span> |

### <a name="position-types"></a><span data-ttu-id="fce19-555">Befattningstyper</span><span class="sxs-lookup"><span data-stu-id="fce19-555">Position types</span></span> 

<span data-ttu-id="fce19-556">Du kan använda befattningstyper för att beskriva huruvida befattningen är på heltid, deltid eller annat.</span><span class="sxs-lookup"><span data-stu-id="fce19-556">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="fce19-557">Befattningstyper mappas till Dayforce som löneklasser som anger huruvida en anställd arbetar heltid eller deltid.</span><span class="sxs-lookup"><span data-stu-id="fce19-557">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="fce19-558">Följande befattningstyper och beskrivningar krävs.</span><span class="sxs-lookup"><span data-stu-id="fce19-558">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="fce19-559">Befattningstyp</span><span class="sxs-lookup"><span data-stu-id="fce19-559">Position type</span></span>   | <span data-ttu-id="fce19-560">beskrivning</span><span class="sxs-lookup"><span data-stu-id="fce19-560">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="fce19-561">Heltid</span><span class="sxs-lookup"><span data-stu-id="fce19-561">Full-time</span></span>       | <span data-ttu-id="fce19-562">Heltidsanställd</span><span class="sxs-lookup"><span data-stu-id="fce19-562">Full time employee</span></span> |
| <span data-ttu-id="fce19-563">Deltid</span><span class="sxs-lookup"><span data-stu-id="fce19-563">Part-time</span></span>       | <span data-ttu-id="fce19-564">Deltidsanställd</span><span class="sxs-lookup"><span data-stu-id="fce19-564">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="fce19-565">Orsakskoder</span><span class="sxs-lookup"><span data-stu-id="fce19-565">Reason codes</span></span>

<span data-ttu-id="fce19-566">Orsakskoder innehåller information om statusen för en medarbetare.</span><span class="sxs-lookup"><span data-stu-id="fce19-566">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="fce19-567">Orsakskoder mappas till Dayforce som statusanledningar som anger orsaken till ändringar i en medarbetares befattning eller anställningsstatus.</span><span class="sxs-lookup"><span data-stu-id="fce19-567">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="fce19-568">Följande orsakskoder och -beskrivningar krävs.</span><span class="sxs-lookup"><span data-stu-id="fce19-568">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="fce19-569">Orsakskod</span><span class="sxs-lookup"><span data-stu-id="fce19-569">Reason code</span></span>            | <span data-ttu-id="fce19-570">beskrivning</span><span class="sxs-lookup"><span data-stu-id="fce19-570">Description</span></span>                    | <span data-ttu-id="fce19-571">Tillämpliga scenarier</span><span class="sxs-lookup"><span data-stu-id="fce19-571">Applicable scenarios</span></span> |
|------------------------|--------------------------------|----------------------|
| <span data-ttu-id="fce19-572">DEPARTUREBEFOREPAYMENT</span><span class="sxs-lookup"><span data-stu-id="fce19-572">DEPARTUREBEFOREPAYMENT</span></span> | <span data-ttu-id="fce19-573">Avgick före första lön</span><span class="sxs-lookup"><span data-stu-id="fce19-573">Departure before first payroll</span></span> | <span data-ttu-id="fce19-574">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="fce19-574">Terminate worker</span></span>     |
| <span data-ttu-id="fce19-575">EGEN UPPSÄGNING</span><span class="sxs-lookup"><span data-stu-id="fce19-575">RESIGNATION</span></span>            | <span data-ttu-id="fce19-576">Egen uppsägning</span><span class="sxs-lookup"><span data-stu-id="fce19-576">Resignation</span></span>                    | <span data-ttu-id="fce19-577">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="fce19-577">Terminate worker</span></span>     |
| <span data-ttu-id="fce19-578">PENSION</span><span class="sxs-lookup"><span data-stu-id="fce19-578">PENSION</span></span>                | <span data-ttu-id="fce19-579">Pension</span><span class="sxs-lookup"><span data-stu-id="fce19-579">Pension</span></span>                        | <span data-ttu-id="fce19-580">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="fce19-580">Terminate worker</span></span>     |
| <span data-ttu-id="fce19-581">UPPSÄGNING</span><span class="sxs-lookup"><span data-stu-id="fce19-581">TERMINATION</span></span>            | <span data-ttu-id="fce19-582">Uppsägning</span><span class="sxs-lookup"><span data-stu-id="fce19-582">Termination</span></span>                    | <span data-ttu-id="fce19-583">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="fce19-583">Terminate worker</span></span>     |
| <span data-ttu-id="fce19-584">PENSION</span><span class="sxs-lookup"><span data-stu-id="fce19-584">RETIREMENT</span></span>             | <span data-ttu-id="fce19-585">Pension</span><span class="sxs-lookup"><span data-stu-id="fce19-585">Retirement</span></span>                     | <span data-ttu-id="fce19-586">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="fce19-586">Terminate worker</span></span>     |
| <span data-ttu-id="fce19-587">FRÅNVARANDE</span><span class="sxs-lookup"><span data-stu-id="fce19-587">ABSENTEE</span></span>               | <span data-ttu-id="fce19-588">Frånvarande</span><span class="sxs-lookup"><span data-stu-id="fce19-588">Absentee</span></span>                       | <span data-ttu-id="fce19-589">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="fce19-589">Terminate worker</span></span>     |
| <span data-ttu-id="fce19-590">ÖVRIGT</span><span class="sxs-lookup"><span data-stu-id="fce19-590">OTHER</span></span>                  | <span data-ttu-id="fce19-591">Andra orsaker</span><span class="sxs-lookup"><span data-stu-id="fce19-591">Other Reasons</span></span>                  | <span data-ttu-id="fce19-592">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="fce19-592">Terminate worker</span></span>     |
| <span data-ttu-id="fce19-593">AVSLUT</span><span class="sxs-lookup"><span data-stu-id="fce19-593">CLOSURE</span></span>                | <span data-ttu-id="fce19-594">Verksamheten nedlagd</span><span class="sxs-lookup"><span data-stu-id="fce19-594">Business Closure</span></span>               | <span data-ttu-id="fce19-595">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="fce19-595">Terminate worker</span></span>     |
| <span data-ttu-id="fce19-596">DÖDSFALL</span><span class="sxs-lookup"><span data-stu-id="fce19-596">DEATH</span></span>                  | <span data-ttu-id="fce19-597">Dödsfall</span><span class="sxs-lookup"><span data-stu-id="fce19-597">Death</span></span>                          | <span data-ttu-id="fce19-598">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="fce19-598">Terminate worker</span></span>     |
| <span data-ttu-id="fce19-599">TJÄNSTLEDIGHET</span><span class="sxs-lookup"><span data-stu-id="fce19-599">LEAVEOFABSENCE</span></span>         | <span data-ttu-id="fce19-600">Tjänstledighet</span><span class="sxs-lookup"><span data-stu-id="fce19-600">Leave of Absence</span></span>               | <span data-ttu-id="fce19-601">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="fce19-601">Terminate worker</span></span>     |
| <span data-ttu-id="fce19-602">KONTRAKTSLUT</span><span class="sxs-lookup"><span data-stu-id="fce19-602">CONTRACTEND</span></span>            | <span data-ttu-id="fce19-603">Kontraktslut</span><span class="sxs-lookup"><span data-stu-id="fce19-603">End of Contract</span></span>                | <span data-ttu-id="fce19-604">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="fce19-604">Terminate worker</span></span>     |
| <span data-ttu-id="fce19-605">LÖNEÄNDRING</span><span class="sxs-lookup"><span data-stu-id="fce19-605">SALARYCHANGE</span></span>           | <span data-ttu-id="fce19-606">Löneändring</span><span class="sxs-lookup"><span data-stu-id="fce19-606">Change of Salary</span></span>               | <span data-ttu-id="fce19-607">Kompensation</span><span class="sxs-lookup"><span data-stu-id="fce19-607">Compensation</span></span>         |

### <a name="terms-of-employment"></a><span data-ttu-id="fce19-608">Anställningsvillkor</span><span class="sxs-lookup"><span data-stu-id="fce19-608">Terms of employment</span></span>

<span data-ttu-id="fce19-609">Anställningsvillkor används för att skapa kategorier av anställningsvillkor.</span><span class="sxs-lookup"><span data-stu-id="fce19-609">Terms of employment are used to create categories of employment terms.</span></span> <span data-ttu-id="fce19-610">Villkoren mappas till Dayforce som indikatorvärden för anställning.</span><span class="sxs-lookup"><span data-stu-id="fce19-610">The terms are mapped to Dayforce as employment indicator values.</span></span>

<span data-ttu-id="fce19-611">Följande anställningsvillkor samt beskrivningar krävs.</span><span class="sxs-lookup"><span data-stu-id="fce19-611">The following terms of employment and descriptions are required.</span></span>

| <span data-ttu-id="fce19-612">Anställningsvillkor</span><span class="sxs-lookup"><span data-stu-id="fce19-612">Terms of employment</span></span>   | <span data-ttu-id="fce19-613">beskrivning</span><span class="sxs-lookup"><span data-stu-id="fce19-613">Description</span></span> |
|-----------------------|-------------|
| <span data-ttu-id="fce19-614">Vanligt</span><span class="sxs-lookup"><span data-stu-id="fce19-614">Regular</span></span>               | <span data-ttu-id="fce19-615">Vanligt</span><span class="sxs-lookup"><span data-stu-id="fce19-615">Regular</span></span>     |
| <span data-ttu-id="fce19-616">Direkt</span><span class="sxs-lookup"><span data-stu-id="fce19-616">Direct</span></span>                | <span data-ttu-id="fce19-617">Direkt</span><span class="sxs-lookup"><span data-stu-id="fce19-617">Direct</span></span>      |
| <span data-ttu-id="fce19-618">Praktik</span><span class="sxs-lookup"><span data-stu-id="fce19-618">Internship</span></span>            | <span data-ttu-id="fce19-619">Praktik</span><span class="sxs-lookup"><span data-stu-id="fce19-619">Internship</span></span>  |
| <span data-ttu-id="fce19-620">Permanent</span><span class="sxs-lookup"><span data-stu-id="fce19-620">Permanent</span></span>             | <span data-ttu-id="fce19-621">Permanent</span><span class="sxs-lookup"><span data-stu-id="fce19-621">Permanent</span></span>   |

### <a name="marital-status"></a><span data-ttu-id="fce19-622">Civilstånd</span><span class="sxs-lookup"><span data-stu-id="fce19-622">Marital status</span></span>

<span data-ttu-id="fce19-623">Civilståndsvärden mappas till Dayforce och översätts på lämpligt sätt till giltiga värden i samband med integrering.</span><span class="sxs-lookup"><span data-stu-id="fce19-623">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="fce19-624">Följande tabell visar hur civilståndsvärden mappas till Dayforce.</span><span class="sxs-lookup"><span data-stu-id="fce19-624">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="fce19-625">Personal</span><span class="sxs-lookup"><span data-stu-id="fce19-625">Human Resources</span></span>                 | <span data-ttu-id="fce19-626">Dayforce</span><span class="sxs-lookup"><span data-stu-id="fce19-626">Dayforce</span></span>                  |
|------------------------|---------------------------|
| <span data-ttu-id="fce19-627">Gift</span><span class="sxs-lookup"><span data-stu-id="fce19-627">Married</span></span>                | <span data-ttu-id="fce19-628">Gift</span><span class="sxs-lookup"><span data-stu-id="fce19-628">Married</span></span>                   |
| <span data-ttu-id="fce19-629">Ett</span><span class="sxs-lookup"><span data-stu-id="fce19-629">Single</span></span>                 | <span data-ttu-id="fce19-630">Ett</span><span class="sxs-lookup"><span data-stu-id="fce19-630">Single</span></span>                    |
| <span data-ttu-id="fce19-631">Änka/Änkeman</span><span class="sxs-lookup"><span data-stu-id="fce19-631">Widowed</span></span>                | <span data-ttu-id="fce19-632">Änka/Änkeman</span><span class="sxs-lookup"><span data-stu-id="fce19-632">Widowed</span></span>                   |
| <span data-ttu-id="fce19-633">Skild</span><span class="sxs-lookup"><span data-stu-id="fce19-633">Divorced</span></span>               | <span data-ttu-id="fce19-634">Frånskild</span><span class="sxs-lookup"><span data-stu-id="fce19-634">Divorced</span></span>                  |
| <span data-ttu-id="fce19-635">Registrerat partnerskap</span><span class="sxs-lookup"><span data-stu-id="fce19-635">Registered Partnership</span></span> | <span data-ttu-id="fce19-636">Samboförhållande</span><span class="sxs-lookup"><span data-stu-id="fce19-636">Domestic Partnership</span></span>      |
| <span data-ttu-id="fce19-637">Inga</span><span class="sxs-lookup"><span data-stu-id="fce19-637">None</span></span>                   | <span data-ttu-id="fce19-638">*Stöds inte i Mexiko*</span><span class="sxs-lookup"><span data-stu-id="fce19-638">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="fce19-639">Sambo</span><span class="sxs-lookup"><span data-stu-id="fce19-639">Cohabiting</span></span>             | <span data-ttu-id="fce19-640">*Stöds inte i Mexiko*</span><span class="sxs-lookup"><span data-stu-id="fce19-640">*Not supported by Mexico*</span></span> |

### <a name="gender"></a><span data-ttu-id="fce19-641">Kön</span><span class="sxs-lookup"><span data-stu-id="fce19-641">Gender</span></span>

<span data-ttu-id="fce19-642">Könsbeteckningar mappas till Dayforce och översätts på lämpligt sätt till giltiga värden i samband med integrering.</span><span class="sxs-lookup"><span data-stu-id="fce19-642">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="fce19-643">Följande tabell visar hur könsbeteckningar mappas till Dayforce.</span><span class="sxs-lookup"><span data-stu-id="fce19-643">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="fce19-644">Personal</span><span class="sxs-lookup"><span data-stu-id="fce19-644">Human Resources</span></span>       | <span data-ttu-id="fce19-645">Dayforce</span><span class="sxs-lookup"><span data-stu-id="fce19-645">Dayforce</span></span>                  |
|--------------|---------------------------|
| <span data-ttu-id="fce19-646">Man</span><span class="sxs-lookup"><span data-stu-id="fce19-646">Male</span></span>         | <span data-ttu-id="fce19-647">Man</span><span class="sxs-lookup"><span data-stu-id="fce19-647">Male</span></span>                      |
| <span data-ttu-id="fce19-648">Kvinna</span><span class="sxs-lookup"><span data-stu-id="fce19-648">Female</span></span>       | <span data-ttu-id="fce19-649">Kvinna</span><span class="sxs-lookup"><span data-stu-id="fce19-649">Female</span></span>                    |
| <span data-ttu-id="fce19-650">Icke-specifik</span><span class="sxs-lookup"><span data-stu-id="fce19-650">Non-specific</span></span> | <span data-ttu-id="fce19-651">*Stöds inte i Mexiko*</span><span class="sxs-lookup"><span data-stu-id="fce19-651">*Not supported by Mexico*</span></span> |

### <a name="payment-method"></a><span data-ttu-id="fce19-652">Betalningsmetod</span><span class="sxs-lookup"><span data-stu-id="fce19-652">Payment method</span></span>

<span data-ttu-id="fce19-653">Betalsätt ger medarbetare och företag ett sätt att beskriva hur medarbetaren ska betalas.</span><span class="sxs-lookup"><span data-stu-id="fce19-653">Payment methods give the employee and the company a way to describe how employees will be paid.</span></span> <span data-ttu-id="fce19-654">Betalsätt mappas till Dayforce och översätts på lämpligt sätt till giltiga värden i samband med integrering.</span><span class="sxs-lookup"><span data-stu-id="fce19-654">Payment methods are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="fce19-655">Följande tabell visar hur betalsätt mappas till Dayforce.</span><span class="sxs-lookup"><span data-stu-id="fce19-655">The following table shows how payment methods are mapped to Dayforce.</span></span>

| <span data-ttu-id="fce19-656">Personal</span><span class="sxs-lookup"><span data-stu-id="fce19-656">Human Resources</span></span>             | <span data-ttu-id="fce19-657">Dayforce</span><span class="sxs-lookup"><span data-stu-id="fce19-657">Dayforce</span></span>                  |
|--------------------|---------------------------|
| <span data-ttu-id="fce19-658">Kontant</span><span class="sxs-lookup"><span data-stu-id="fce19-658">Cash</span></span>               | <span data-ttu-id="fce19-659">Kontant</span><span class="sxs-lookup"><span data-stu-id="fce19-659">Cash</span></span>                      |
| <span data-ttu-id="fce19-660">Elektronisk betalning</span><span class="sxs-lookup"><span data-stu-id="fce19-660">Electronic Payment</span></span> | <span data-ttu-id="fce19-661">Överför</span><span class="sxs-lookup"><span data-stu-id="fce19-661">Transfer</span></span>                  |
| <span data-ttu-id="fce19-662">Check</span><span class="sxs-lookup"><span data-stu-id="fce19-662">Check</span></span>              | <span data-ttu-id="fce19-663">Check</span><span class="sxs-lookup"><span data-stu-id="fce19-663">Cheque</span></span>                    |
| <span data-ttu-id="fce19-664">Bankutdrag</span><span class="sxs-lookup"><span data-stu-id="fce19-664">Bank Draft</span></span>         | <span data-ttu-id="fce19-665">*Stöds inte i Mexiko*</span><span class="sxs-lookup"><span data-stu-id="fce19-665">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="fce19-666">Annat</span><span class="sxs-lookup"><span data-stu-id="fce19-666">Other</span></span>              | <span data-ttu-id="fce19-667">*Stöds inte i Mexiko*</span><span class="sxs-lookup"><span data-stu-id="fce19-667">*Not supported by Mexico*</span></span> |

### <a name="bank-account-type"></a><span data-ttu-id="fce19-668">Bankkontotyp</span><span class="sxs-lookup"><span data-stu-id="fce19-668">Bank account type</span></span>

<span data-ttu-id="fce19-669">Bankkontotyper används för elektroniska betalningar till medarbetare.</span><span class="sxs-lookup"><span data-stu-id="fce19-669">Bank account types are used for electronic payments to employees.</span></span> <span data-ttu-id="fce19-670">Bankkontotyper mappas till Dayforce som kontoinformation för överföringar.</span><span class="sxs-lookup"><span data-stu-id="fce19-670">Bank account types are mapped to Dayforce as transfer account information.</span></span> <span data-ttu-id="fce19-671">Bankkontotyper översätts på lämpligt till giltiga värden i samband med integrering.</span><span class="sxs-lookup"><span data-stu-id="fce19-671">The bank account types are translated, as appropriate, to the accepted values upon integration.</span></span>

| <span data-ttu-id="fce19-672">Personal</span><span class="sxs-lookup"><span data-stu-id="fce19-672">Human Resources</span></span>            | <span data-ttu-id="fce19-673">Dayforce</span><span class="sxs-lookup"><span data-stu-id="fce19-673">Dayforce</span></span>                  |
|-------------------|---------------------------|
| <span data-ttu-id="fce19-674">Checkkonto</span><span class="sxs-lookup"><span data-stu-id="fce19-674">Checking Account</span></span>  | <span data-ttu-id="fce19-675">Checkkonto</span><span class="sxs-lookup"><span data-stu-id="fce19-675">CheckingAccount</span></span>           |
| <span data-ttu-id="fce19-676">Lönekonto</span><span class="sxs-lookup"><span data-stu-id="fce19-676">Payroll Account</span></span>   | <span data-ttu-id="fce19-677">Lönekonto</span><span class="sxs-lookup"><span data-stu-id="fce19-677">PayrollAccount</span></span>            |
| <span data-ttu-id="fce19-678">Sparkonto</span><span class="sxs-lookup"><span data-stu-id="fce19-678">Savings Account</span></span>   | <span data-ttu-id="fce19-679">*Stöds inte i Mexiko*</span><span class="sxs-lookup"><span data-stu-id="fce19-679">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="fce19-680">BankGirot-konto</span><span class="sxs-lookup"><span data-stu-id="fce19-680">BankGirot account</span></span> | <span data-ttu-id="fce19-681">*Stöds inte i Mexiko*</span><span class="sxs-lookup"><span data-stu-id="fce19-681">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="fce19-682">PlusGirot-konto</span><span class="sxs-lookup"><span data-stu-id="fce19-682">PlusGirot account</span></span> | <span data-ttu-id="fce19-683">*Stöds inte i Mexiko*</span><span class="sxs-lookup"><span data-stu-id="fce19-683">*Not supported by Mexico*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="fce19-684">Inkomstkoder</span><span class="sxs-lookup"><span data-stu-id="fce19-684">Earning codes</span></span>

<span data-ttu-id="fce19-685">Inkomstkoder identifierar individuellt alla typer av arbetstagarintäkter.</span><span class="sxs-lookup"><span data-stu-id="fce19-685">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="fce19-686">Koderna omfattar flera olika parametrar som rör inkomster, till exempel redovisningsbestämmelser, skattelagar, rapporteringskrav och gross up-kapacitet.</span><span class="sxs-lookup"><span data-stu-id="fce19-686">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="fce19-687">Om en frekvens som inte stöds används tillämpas frekvensen **Varje lön** som standard för beräkningen.</span><span class="sxs-lookup"><span data-stu-id="fce19-687">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="fce19-688">Frekvenser som stöds</span><span class="sxs-lookup"><span data-stu-id="fce19-688">Supported frequencies</span></span>

- <span data-ttu-id="fce19-689">Allt</span><span class="sxs-lookup"><span data-stu-id="fce19-689">All</span></span>
- <span data-ttu-id="fce19-690">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="fce19-690">EVERYPAY</span></span>
- <span data-ttu-id="fce19-691">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="fce19-691">EACHPAYPERIOD</span></span>
- <span data-ttu-id="fce19-692">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="fce19-692">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="fce19-693">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="fce19-693">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="fce19-694">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="fce19-694">1OFMTH</span></span>
- <span data-ttu-id="fce19-695">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="fce19-695">LASTOFMTH</span></span>
- <span data-ttu-id="fce19-696">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="fce19-696">2OFMTH</span></span>
- <span data-ttu-id="fce19-697">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="fce19-697">3OFMTH</span></span>
- <span data-ttu-id="fce19-698">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="fce19-698">4OFMTH</span></span>
- <span data-ttu-id="fce19-699">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="fce19-699">5OFMTH</span></span>
- <span data-ttu-id="fce19-700">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="fce19-700">1N2OFMTH</span></span>
- <span data-ttu-id="fce19-701">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="fce19-701">3N4OFMTH</span></span>
- <span data-ttu-id="fce19-702">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="fce19-702">1N3OFMTH</span></span>
- <span data-ttu-id="fce19-703">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="fce19-703">1N4OFMTH</span></span>
- <span data-ttu-id="fce19-704">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="fce19-704">2N3OFMTH</span></span>
- <span data-ttu-id="fce19-705">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="fce19-705">2N4OFMTH</span></span>
- <span data-ttu-id="fce19-706">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="fce19-706">1N2N3OFMTH</span></span>
- <span data-ttu-id="fce19-707">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="fce19-707">1N2N4OFMTH</span></span>
- <span data-ttu-id="fce19-708">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="fce19-708">1N3N4OFMTH</span></span>
- <span data-ttu-id="fce19-709">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="fce19-709">2N3N4OFMTH</span></span>
- <span data-ttu-id="fce19-710">1N2N3N4OFMTH – 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="fce19-710">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="fce19-711">2N3N4N5OFMth – 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="fce19-711">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="fce19-712">1OFQTR – 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="fce19-712">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="fce19-713">LASTOFQTR – LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="fce19-713">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="fce19-714">LASTMTHOFQTR – LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="fce19-714">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="fce19-715">1OFYEAR – 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="fce19-715">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="fce19-716">LASTOFYEAR – LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="fce19-716">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="fce19-717">NOVNDECOFYEAR – NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="fce19-717">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="fce19-718">Adresser</span><span class="sxs-lookup"><span data-stu-id="fce19-718">Addresses</span></span>

<span data-ttu-id="fce19-719">Identifiering av specifika lands-/region-, delstats- och region(kommun)-koder kräver särskilda format som Dayforce och leverantörer i respektive land/region kan känna igen.</span><span class="sxs-lookup"><span data-stu-id="fce19-719">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="fce19-720">Även om formatet för städer är flexibelt måste varje stad associeras med en delstat.</span><span class="sxs-lookup"><span data-stu-id="fce19-720">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="fce19-721">Personal</span><span class="sxs-lookup"><span data-stu-id="fce19-721">Human Resources</span></span>              | <span data-ttu-id="fce19-722">Dayforce</span><span class="sxs-lookup"><span data-stu-id="fce19-722">Dayforce</span></span>              |
|---------------------|-----------------------|
| <span data-ttu-id="fce19-723">Land/region</span><span class="sxs-lookup"><span data-stu-id="fce19-723">Country/Region</span></span>      | <span data-ttu-id="fce19-724">Landskod</span><span class="sxs-lookup"><span data-stu-id="fce19-724">Country Code</span></span>          |
| <span data-ttu-id="fce19-725">Postnummer</span><span class="sxs-lookup"><span data-stu-id="fce19-725">Zip/Postal Code</span></span>     | <span data-ttu-id="fce19-726">Postnummer</span><span class="sxs-lookup"><span data-stu-id="fce19-726">Postal Code</span></span>           |
| <span data-ttu-id="fce19-727">Stat</span><span class="sxs-lookup"><span data-stu-id="fce19-727">State</span></span>               | <span data-ttu-id="fce19-728">Delstatskod</span><span class="sxs-lookup"><span data-stu-id="fce19-728">State Code</span></span>            |
| <span data-ttu-id="fce19-729">Ort</span><span class="sxs-lookup"><span data-stu-id="fce19-729">City</span></span>                | <span data-ttu-id="fce19-730">Ort</span><span class="sxs-lookup"><span data-stu-id="fce19-730">City</span></span>                  |
| <span data-ttu-id="fce19-731">Län</span><span class="sxs-lookup"><span data-stu-id="fce19-731">County</span></span>              | <span data-ttu-id="fce19-732">Region (kommun)</span><span class="sxs-lookup"><span data-stu-id="fce19-732">County (Municipality)</span></span> |
| <span data-ttu-id="fce19-733">Gata</span><span class="sxs-lookup"><span data-stu-id="fce19-733">Street</span></span>              | <span data-ttu-id="fce19-734">Adressrad 1</span><span class="sxs-lookup"><span data-stu-id="fce19-734">Address Line 1</span></span>        |
| <span data-ttu-id="fce19-735">Gatunummer</span><span class="sxs-lookup"><span data-stu-id="fce19-735">Street Number</span></span>       | <span data-ttu-id="fce19-736">Adressrad 2</span><span class="sxs-lookup"><span data-stu-id="fce19-736">Address Line 2</span></span>        |
| <span data-ttu-id="fce19-737">Byggnadskomplement</span><span class="sxs-lookup"><span data-stu-id="fce19-737">Building Complement</span></span> | <span data-ttu-id="fce19-738">Adressrad 5</span><span class="sxs-lookup"><span data-stu-id="fce19-738">Address Line 5</span></span>        |

### <a name="passport-number"></a><span data-ttu-id="fce19-739">Passnummer</span><span class="sxs-lookup"><span data-stu-id="fce19-739">Passport number</span></span>

<span data-ttu-id="fce19-740">Medarbetare kan deklarera passinformation.</span><span class="sxs-lookup"><span data-stu-id="fce19-740">Employees can declare passport information.</span></span> <span data-ttu-id="fce19-741">Denna information bär ID-typen **Pass** och integreras i Dayforce som en del av medarbetarens Mexikospecifika information.</span><span class="sxs-lookup"><span data-stu-id="fce19-741">This information is of the **Passport** identification type and is integrated into Dayforce as part of an employee's Mexico-specific information.</span></span>

- <span data-ttu-id="fce19-742">Identifieringstyp = "Pass"</span><span class="sxs-lookup"><span data-stu-id="fce19-742">Identification Type = "Passport"</span></span>
- <span data-ttu-id="fce19-743">Utfärdat den</span><span class="sxs-lookup"><span data-stu-id="fce19-743">Issued Date</span></span>
- <span data-ttu-id="fce19-744">Utgångsdatum</span><span class="sxs-lookup"><span data-stu-id="fce19-744">Expiration Date</span></span>

<span data-ttu-id="fce19-745">Medarbetare kan deklarera flera ID-nummer med ID-typen **Pass**.</span><span class="sxs-lookup"><span data-stu-id="fce19-745">Employees can declare multiple identification numbers of the **Passport** identification type.</span></span> <span data-ttu-id="fce19-746">Endast den aktuella passposten integreras emellertid i Dayforce.</span><span class="sxs-lookup"><span data-stu-id="fce19-746">However, only the current active passport entry is integrated into Dayforce.</span></span> <span data-ttu-id="fce19-747">Om alla passposter har upphört att gälla kommer det pass som är utfärdat senast att integreras i Dayforce.</span><span class="sxs-lookup"><span data-stu-id="fce19-747">If all passport entries are expired, the passport that was most recently issued is integrated into Dayforce.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]