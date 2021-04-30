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
ms.openlocfilehash: 1647b7fbf84a78051e745e918954df32a2e7e1dd
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "5890014"
---
# <a name="configure-integration-with-dayforce"></a><span data-ttu-id="330a2-104">Konfigurera integration med Dayforce</span><span class="sxs-lookup"><span data-stu-id="330a2-104">Configure integration with Dayforce</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="330a2-105">Integreringen mellan Microsoft Dynamics 365 Human Resources och Ceridian Dayforce är beroende av flera konfigurationssteg som beskrivs i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="330a2-105">The integration between Microsoft Dynamics 365 Human Resources and Ceridian Dayforce relies on several configuration steps that are described in this article.</span></span> <span data-ttu-id="330a2-106">Du måste konfigurera integrationen i både Personal och Dayforce innan du kan bearbeta en betalning.</span><span class="sxs-lookup"><span data-stu-id="330a2-106">You must configure the integration in both Human Resources and Dayforce before you can process a pay run.</span></span>

<span data-ttu-id="330a2-107">När du använder tjänster som exempelvis Dayforce för att utföra betalningar måste du aktivera integration i Personal.</span><span class="sxs-lookup"><span data-stu-id="330a2-107">When you use a service such as Dayforce to complete pay runs, you must enable the integration in Human Resources.</span></span> <span data-ttu-id="330a2-108">Integrationen kräver specifika data från Personal.</span><span class="sxs-lookup"><span data-stu-id="330a2-108">The integration requires specific data from Human Resources.</span></span> <span data-ttu-id="330a2-109">Därför måste du kontrollera att data som är mappad till Dayforce konfigureras i Personal på ett sätt som stöder integrationen.</span><span class="sxs-lookup"><span data-stu-id="330a2-109">Therefore, you must verify that data that is mapped to Dayforce is configured in Human Resources in a manner that supports the integration.</span></span> <span data-ttu-id="330a2-110">Integrationen använder följande breda datakategorier:</span><span class="sxs-lookup"><span data-stu-id="330a2-110">The integration uses the following broad categories of data:</span></span>

- <span data-ttu-id="330a2-111">Personaldata</span><span class="sxs-lookup"><span data-stu-id="330a2-111">Human resources data</span></span>
- <span data-ttu-id="330a2-112">Kompensationsdata</span><span class="sxs-lookup"><span data-stu-id="330a2-112">Compensation data</span></span>
- <span data-ttu-id="330a2-113">Lönedata som till exempel lönecykler, betalningsperioder och inkomstkoder</span><span class="sxs-lookup"><span data-stu-id="330a2-113">Payroll data, such as pay cycles, pay periods, and earning codes</span></span>
- <span data-ttu-id="330a2-114">Medarbetardata</span><span class="sxs-lookup"><span data-stu-id="330a2-114">Worker data</span></span>

<span data-ttu-id="330a2-115">Det här avsnittet beskriver de steg som du måste följa för att aktivera integrationen.</span><span class="sxs-lookup"><span data-stu-id="330a2-115">This article describes the steps that you must follow to enable the integration.</span></span> <span data-ttu-id="330a2-116">Här förklaras också de typer av data och den konfigurationsinformation som integrationen kräver.</span><span class="sxs-lookup"><span data-stu-id="330a2-116">It also explains the types of data and the configuration details that the integration requires.</span></span>

## <a name="enable-the-integration"></a><span data-ttu-id="330a2-117">Aktivera integrationen</span><span class="sxs-lookup"><span data-stu-id="330a2-117">Enable the integration</span></span>

<span data-ttu-id="330a2-118">Du måste aktivera integrationen i Personal och ange konfigurationsinformation för att ansluta till Dayforce.</span><span class="sxs-lookup"><span data-stu-id="330a2-118">In Human Resources, you must turn on the integration and enter the configuration information to connect to Dayforce.</span></span> <span data-ttu-id="330a2-119">Om du vill att den redovisningstransaktion som framställs ska importeras till Microsoft Dynamics 365 Finance måste du också skapa ett lagringskonto för Microsoft Azure och ange anslutningssträngen för Azure-lagring i Finance.</span><span class="sxs-lookup"><span data-stu-id="330a2-119">If you want the general ledger transaction that is produced to be imported into Microsoft Dynamics 365 Finance, you must also set up a Microsoft Azure storage account and enter the Azure Storage connection string in Finance.</span></span>

<span data-ttu-id="330a2-120">Följ dessa steg om du vill aktivera integration i Personal.</span><span class="sxs-lookup"><span data-stu-id="330a2-120">To turn on the integration in Human Resources, follow these steps.</span></span>

1. <span data-ttu-id="330a2-121">På sidan **Systemadministration** väljer du **Integrationskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="330a2-121">On the **System administration** page, select **Integration configuration**.</span></span>
2. <span data-ttu-id="330a2-122">Ange slutpunkten för filöverföringsprotokollet (FTP) och den säkra FTP-sökvägen.</span><span class="sxs-lookup"><span data-stu-id="330a2-122">Enter the secure File Transfer Protocol (FTP) endpoint and the secure FTP folder path.</span></span>
3. <span data-ttu-id="330a2-123">Ange användarnamn och lösenord för den användare som kommer att använda den säkra FTP-slutpunkten och mappsökvägen.</span><span class="sxs-lookup"><span data-stu-id="330a2-123">Enter the user name and password of the user who will access the secure FTP endpoint and folder path.</span></span>
4. <span data-ttu-id="330a2-124">Testa anslutningen efter behov samt ange alternativet **Aktivera integrering av löner** som **Ja**.</span><span class="sxs-lookup"><span data-stu-id="330a2-124">Test the connection, as required, and set the **Enable payroll integration** option to **Yes**.</span></span>

<span data-ttu-id="330a2-125">När integreringen aktiveras skapas dataexportpaket och filer, och frekvensen anges.</span><span class="sxs-lookup"><span data-stu-id="330a2-125">When the integration is turned on, the data export package and files are created, and the frequency is set.</span></span> <span data-ttu-id="330a2-126">Du kan ändra frekvensen efter behov.</span><span class="sxs-lookup"><span data-stu-id="330a2-126">You can change this frequency as you require.</span></span>

<span data-ttu-id="330a2-127">Mer information om Azure-lagringskonton och anslutningssträngar för Azure-lagring, se följande Azure-artiklar:</span><span class="sxs-lookup"><span data-stu-id="330a2-127">For more information about Azure storage accounts and Azure Storage connection strings, see the following Azure articles:</span></span>

- [<span data-ttu-id="330a2-128">Om Azure-lagringskonton</span><span class="sxs-lookup"><span data-stu-id="330a2-128">About Azure storage accounts</span></span>](/azure/storage/common/storage-create-storage-account?toc=%2fazure%2fstorage%2ffiles%2ftoc.json)
- [<span data-ttu-id="330a2-129">Konfigurera anslutningssträngar för Azure-lagring</span><span class="sxs-lookup"><span data-stu-id="330a2-129">Configure Azure Storage connection strings</span></span>](/azure/storage/common/storage-configure-connection-string)

### <a name="technical-details-when-payroll-integration-is-enabled"></a><span data-ttu-id="330a2-130">Teknisk information när löneintegration har aktiverats</span><span class="sxs-lookup"><span data-stu-id="330a2-130">Technical details when payroll integration is enabled</span></span>

<span data-ttu-id="330a2-131">Att slå på löneintegration har två primära effekter:</span><span class="sxs-lookup"><span data-stu-id="330a2-131">Turning on the payroll integration has two primary effects:</span></span>

- <span data-ttu-id="330a2-132">Ett dataexportprojekt med namnet "Löneintegrationexport" skapas.</span><span class="sxs-lookup"><span data-stu-id="330a2-132">A data export project named "Payroll integration export" is created.</span></span> <span data-ttu-id="330a2-133">Det här projektet innehåller de entiteter och fält som krävs för löneintegration.</span><span class="sxs-lookup"><span data-stu-id="330a2-133">This project contains the entities and fields required for the payroll integration.</span></span> <span data-ttu-id="330a2-134">För att undersöka projekt, gå till **Systemadministration**, välj **Datahantering** och öppna dataprojekt från lista över projekt.</span><span class="sxs-lookup"><span data-stu-id="330a2-134">To examine the project, go to **System administration**, select the **Data management** tile, and then open the data project from the list of projects.</span></span>
- <span data-ttu-id="330a2-135">Det här batchjobbet kör dataexportprojektet, krypterar det resulterande datapaketet och överför datapaketfilen till den SFTP-slutpunkt som konfigurerats på skärmen **integrationskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="330a2-135">This batch job executes the data export project, encrypts the resulting data package, and transfers the data package file to the SFTP endpoint configured on the **Integration configuration** screen.</span></span>

> [!NOTE]
> <span data-ttu-id="330a2-136">Det datapaket som överförs till SFTP-slutpunkten krypteras med en nyckel som är unik för paketet.</span><span class="sxs-lookup"><span data-stu-id="330a2-136">The data package transferred to the SFTP endpoint is encrypted using a key that is unique to the package.</span></span> <span data-ttu-id="330a2-137">Nyckeln finns i ett Azure Key Vault som bara kan nås av Ceridian.</span><span class="sxs-lookup"><span data-stu-id="330a2-137">The key is in an Azure Key Vault that is accessible only by Ceridian.</span></span> <span data-ttu-id="330a2-138">Det går inte att dekryptera och undersöka innehållet i datapaketet.</span><span class="sxs-lookup"><span data-stu-id="330a2-138">It is not possible to decrypt and examine the data package contents.</span></span> <span data-ttu-id="330a2-139">Om du behöver undersöka innehållet i datapaketet, måste du exportera dataprojektet "Löneintegrationexport" manuellt, hämta det och sedan öppna det.</span><span class="sxs-lookup"><span data-stu-id="330a2-139">If you need to examine the contents of the data package, you need to export the "Payroll integration export" data project manually, download it, and then open it.</span></span> <span data-ttu-id="330a2-140">Manuell export använder inte kryptering eller överföring av paketet.</span><span class="sxs-lookup"><span data-stu-id="330a2-140">Manual export will not apply encryption or transfer the package.</span></span>
> <span data-ttu-id="330a2-141">Om integrationsfilerna till exempel skickas från en UAT- eller sandbox-miljö för Dynamics 365 Human Resources till en Ceridian Dayforce-testmiljö kan du använda följande URL för nyckelvalv: https://payrollintegrationprod.vault.azure.net.</span><span class="sxs-lookup"><span data-stu-id="330a2-141">For instances where the integration files are sent from a Dynamics 365 Human Resources UAT or Sandbox environment to a Ceridian Dayforce Test environment, you can use the following key vault URL: https://payrollintegrationprod.vault.azure.net.</span></span>

## <a name="configure-your-data"></a><span data-ttu-id="330a2-142">Konfigurera dina data</span><span class="sxs-lookup"><span data-stu-id="330a2-142">Configure your data</span></span> 

<span data-ttu-id="330a2-143">Du måste konfigurera personaldata för att bearbeta löner i Personal.</span><span class="sxs-lookup"><span data-stu-id="330a2-143">To process payroll, you must configure human resource data in Human Resources.</span></span> <span data-ttu-id="330a2-144">Du måste ställa in organisationsinformation, t.ex. jobb och befattningar samt förmåner och kompensationsinformation.</span><span class="sxs-lookup"><span data-stu-id="330a2-144">You must set up organizational data, such as jobs and positions, together with benefits and compensation information.</span></span> <span data-ttu-id="330a2-145">Denna information utgör den anställnings-, lön- och avdragsinformationen som krävs för att generera lön för medarbetare.</span><span class="sxs-lookup"><span data-stu-id="330a2-145">This information provides the employment, pay, and deduction information that is required in order to generate employee pay.</span></span>

### <a name="human-resource-data"></a><span data-ttu-id="330a2-146">Personaldata</span><span class="sxs-lookup"><span data-stu-id="330a2-146">Human resource data</span></span>

#### <a name="benefits"></a><span data-ttu-id="330a2-147">Förmåner</span><span class="sxs-lookup"><span data-stu-id="330a2-147">Benefits</span></span> 

<span data-ttu-id="330a2-148">Personal tillhandahåller verktyg som kan användas för att ställa in och underhålla förmåner, avdrag och kompensationsplaner för medarbetare som en organisation erbjuder eller bearbetar för sin personal.</span><span class="sxs-lookup"><span data-stu-id="330a2-148">Human resources provides tools for the setup and maintenance of the benefits, deductions, and worker compensation plans that an organization offers or processes for its workers.</span></span>

<span data-ttu-id="330a2-149">När du skapar förmåner, kom då ihåg följande data och konfigurationer som används i Dayforce.</span><span class="sxs-lookup"><span data-stu-id="330a2-149">When you create benefits, keep in mind the following data and configurations that are used in Dayforce.</span></span>

##### <a name="benefit-plans"></a><span data-ttu-id="330a2-150">Förmånsplaner</span><span class="sxs-lookup"><span data-stu-id="330a2-150">Benefit plans</span></span>

- <span data-ttu-id="330a2-151">Plan (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="330a2-151">Plan (required)</span></span>
- <span data-ttu-id="330a2-152">Typ (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="330a2-152">Type (required)</span></span>
- <span data-ttu-id="330a2-153">Effekt på lön (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="330a2-153">Payroll impact (required)</span></span>
- <span data-ttu-id="330a2-154">Återvinn restbetalningar</span><span class="sxs-lookup"><span data-stu-id="330a2-154">Recover arrears</span></span>
- <span data-ttu-id="330a2-155">Avdragsmetod</span><span class="sxs-lookup"><span data-stu-id="330a2-155">Deduction method</span></span>
- <span data-ttu-id="330a2-156">Avdragsprioritet</span><span class="sxs-lookup"><span data-stu-id="330a2-156">Deduction priority</span></span>
- <span data-ttu-id="330a2-157">Gränsperiod</span><span class="sxs-lookup"><span data-stu-id="330a2-157">Limit period</span></span>
- <span data-ttu-id="330a2-158">Begränsa belopp</span><span class="sxs-lookup"><span data-stu-id="330a2-158">Limit amount</span></span>

##### <a name="benefits"></a><span data-ttu-id="330a2-159">Förmåner</span><span class="sxs-lookup"><span data-stu-id="330a2-159">Benefits</span></span>

- <span data-ttu-id="330a2-160">Plan (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="330a2-160">Plan (required)</span></span>
- <span data-ttu-id="330a2-161">Typ (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="330a2-161">Type (required)</span></span>
- <span data-ttu-id="330a2-162">Tillval (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="330a2-162">Option (required)</span></span>
- <span data-ttu-id="330a2-163">Förmåns-ID (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="330a2-163">Benefit ID (required)</span></span>
- <span data-ttu-id="330a2-164">Frekvens</span><span class="sxs-lookup"><span data-stu-id="330a2-164">Frequency</span></span>
- <span data-ttu-id="330a2-165">Bas</span><span class="sxs-lookup"><span data-stu-id="330a2-165">Basis</span></span>
- <span data-ttu-id="330a2-166">Belopp eller tariff</span><span class="sxs-lookup"><span data-stu-id="330a2-166">Amount or rate</span></span>
- <span data-ttu-id="330a2-167">Inkomstkod</span><span class="sxs-lookup"><span data-stu-id="330a2-167">Earning code</span></span>

##### <a name="supported-frequencies"></a><span data-ttu-id="330a2-168">Frekvenser som stöds</span><span class="sxs-lookup"><span data-stu-id="330a2-168">Supported frequencies</span></span> 

- <span data-ttu-id="330a2-169">Varje vecka</span><span class="sxs-lookup"><span data-stu-id="330a2-169">Weekly</span></span>
- <span data-ttu-id="330a2-170">Varannan vecka</span><span class="sxs-lookup"><span data-stu-id="330a2-170">Bi-weekly</span></span>
- <span data-ttu-id="330a2-171">Var fjortonde dag</span><span class="sxs-lookup"><span data-stu-id="330a2-171">Semi-monthly</span></span>
- <span data-ttu-id="330a2-172">Månatlig</span><span class="sxs-lookup"><span data-stu-id="330a2-172">Monthly</span></span>

##### <a name="supported-bases"></a><span data-ttu-id="330a2-173">Databaser som stöds</span><span class="sxs-lookup"><span data-stu-id="330a2-173">Supported bases</span></span> 

- <span data-ttu-id="330a2-174">Fast belopp</span><span class="sxs-lookup"><span data-stu-id="330a2-174">Fixed amount</span></span>
- <span data-ttu-id="330a2-175">Procent av inkomst</span><span class="sxs-lookup"><span data-stu-id="330a2-175">Percent of earnings</span></span>
- <span data-ttu-id="330a2-176">Produktiva timmar</span><span class="sxs-lookup"><span data-stu-id="330a2-176">Productive hours</span></span>

<span data-ttu-id="330a2-177">Dayforce skapar följande avdrag baserat på den löneeffekt som definieras i förmånsplanen.</span><span class="sxs-lookup"><span data-stu-id="330a2-177">Dayforce creates the following deductions, based on the payroll impact that is defined on the benefit plan.</span></span>

| <span data-ttu-id="330a2-178">Val i Personal</span><span class="sxs-lookup"><span data-stu-id="330a2-178">Selection in Human Resources</span></span>        | <span data-ttu-id="330a2-179">Resultat i Dayforce</span><span class="sxs-lookup"><span data-stu-id="330a2-179">Result in Dayforce</span></span>                            |
|----------------------------|-----------------------------------------------|
| <span data-ttu-id="330a2-180">Ingen</span><span class="sxs-lookup"><span data-stu-id="330a2-180">None</span></span>                       | <span data-ttu-id="330a2-181">Inget avdrag skapas.</span><span class="sxs-lookup"><span data-stu-id="330a2-181">No deduction is created.</span></span>                      |
| <span data-ttu-id="330a2-182">Endast avdrag</span><span class="sxs-lookup"><span data-stu-id="330a2-182">Deduction only</span></span>             | <span data-ttu-id="330a2-183">Löneavdrag för en medarbetare skapas.</span><span class="sxs-lookup"><span data-stu-id="330a2-183">An employee deduction is created.</span></span>             |
| <span data-ttu-id="330a2-184">Endast lönetillägg</span><span class="sxs-lookup"><span data-stu-id="330a2-184">Contribution only</span></span>          | <span data-ttu-id="330a2-185">Löneavdrag för en arbetsgivare skapas.</span><span class="sxs-lookup"><span data-stu-id="330a2-185">An employer deduction is created.</span></span>             |
| <span data-ttu-id="330a2-186">Avdrag och tillägg</span><span class="sxs-lookup"><span data-stu-id="330a2-186">Deduction and contribution</span></span> | <span data-ttu-id="330a2-187">Avdrag för medarbetare och arbetsgivare skapas.</span><span class="sxs-lookup"><span data-stu-id="330a2-187">Employee and employer deductions are created.</span></span> |

<span data-ttu-id="330a2-188">Mer information om hur du definierar och hanterar ett förmånsprogram finns i följande artiklar:</span><span class="sxs-lookup"><span data-stu-id="330a2-188">For more information about how to define and manage a benefits program, see the following articles:</span></span>

- [<span data-ttu-id="330a2-189">Utveckla ett förmånsprogram för medarbetare</span><span class="sxs-lookup"><span data-stu-id="330a2-189">Deliver an employee benefits program</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/deliver-employee-benefits-program)
- [<span data-ttu-id="330a2-190">Skapa en ny förmån</span><span class="sxs-lookup"><span data-stu-id="330a2-190">Create a new benefit</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/create-new-benefit)
- [<span data-ttu-id="330a2-191">Definiera förmånsberättiganderegler och policyer</span><span class="sxs-lookup"><span data-stu-id="330a2-191">Define benefit eligibility rules and policies</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-benefit-eligibility-rules-policies)
- [<span data-ttu-id="330a2-192">Registrera och ta bort förmåner för arbetare</span><span class="sxs-lookup"><span data-stu-id="330a2-192">Enroll and remove benefits from workers</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-remove-benefits-workers)

#### <a name="compensation"></a><span data-ttu-id="330a2-193">Kompensation</span><span class="sxs-lookup"><span data-stu-id="330a2-193">Compensation</span></span> 

<span data-ttu-id="330a2-194">Kompensationshantering används för att styra du utbetalningen av grundlön och belöningar.</span><span class="sxs-lookup"><span data-stu-id="330a2-194">Compensation management is used to control the delivery of base pay and awards.</span></span> <span data-ttu-id="330a2-195">En medarbetares fasta grundlön och merithöjningar kontrolleras genom fasta kompensationsplaner.</span><span class="sxs-lookup"><span data-stu-id="330a2-195">An employee's fixed base pay and merit increases are controlled through fixed compensation plans.</span></span> <span data-ttu-id="330a2-196">Betalningen av incitament, till exempel bonusar, resultatbelöningar, aktieoptioner och anslag och även engångsbelöningar kontrolleras genom variabla kompensationsplaner.</span><span class="sxs-lookup"><span data-stu-id="330a2-196">The payment of incentive pay, such as bonus payments, performance awards, stock options, and grants, and also one-time awards, are controlled through variable compensation plans.</span></span>

<span data-ttu-id="330a2-197">Dayforce använder kompensationsinformation för att beräkna en medarbetares tim- eller årliga betalning.</span><span class="sxs-lookup"><span data-stu-id="330a2-197">Dayforce uses compensation information to calculate an employee's hourly or annual rate.</span></span> <span data-ttu-id="330a2-198">Fasta kompensationsplaner och lönekonverteringar är obligatoriska.</span><span class="sxs-lookup"><span data-stu-id="330a2-198">Fixed compensation plans and pay rate conversions are required.</span></span> <span data-ttu-id="330a2-199">Medarbetarna måste vara anslutna till en fast kompensationsplan.</span><span class="sxs-lookup"><span data-stu-id="330a2-199">Employees must be associated with a fixed compensation plan.</span></span>

<span data-ttu-id="330a2-200">Mer information om att kompensationsplaner finns i följande artiklar:</span><span class="sxs-lookup"><span data-stu-id="330a2-200">For more information about compensation plans, see the following articles:</span></span>

- [<span data-ttu-id="330a2-201">Skapa planer för fast kompensation</span><span class="sxs-lookup"><span data-stu-id="330a2-201">Create fixed compensation plans</span></span>](/dynamics365/unified-operations/talent/create-fixed-compensation-plans)
- [<span data-ttu-id="330a2-202">Skapa planer för variabel kompensation</span><span class="sxs-lookup"><span data-stu-id="330a2-202">Create variable compensation plans</span></span>](/dynamics365/unified-operations/talent/create-variable-compensation-plans)
- [<span data-ttu-id="330a2-203">Utveckla struktur och planer för lön/kompensation</span><span class="sxs-lookup"><span data-stu-id="330a2-203">Develop salary/compensation structure and plans</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/develop-salary-compensation-structure-plan)
- [<span data-ttu-id="330a2-204">Bearbeta kompensation</span><span class="sxs-lookup"><span data-stu-id="330a2-204">Process compensation</span></span>](/dynamics365/unified-operations/talent/process-compensation)
- [<span data-ttu-id="330a2-205">Definiera kompensationsprocessen och beräkna resultat</span><span class="sxs-lookup"><span data-stu-id="330a2-205">Define compensation process and calculate results</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-compensation-process-calculate-results)
- [<span data-ttu-id="330a2-206">Registrera en medarbetare i en fast kompensationsplan</span><span class="sxs-lookup"><span data-stu-id="330a2-206">Enroll an employee in a fixed compensation plan</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-fixed-compensation-plan)
- [<span data-ttu-id="330a2-207">Registrera en medarbetare i en variabel kompensationsplan</span><span class="sxs-lookup"><span data-stu-id="330a2-207">Enroll an employee in a variable compensation plan</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-variable-compensation-plan)

#### <a name="jobs"></a><span data-ttu-id="330a2-208">Jobb</span><span class="sxs-lookup"><span data-stu-id="330a2-208">Jobs</span></span> 

<span data-ttu-id="330a2-209">Ett jobb är den samling uppgifter och ansvarsområden som avkrävs en person som utför ett jobb.</span><span class="sxs-lookup"><span data-stu-id="330a2-209">A job is a collection of the tasks and responsibilities that are required of a person who performs a job.</span></span> <span data-ttu-id="330a2-210">Mer information finns i följande artiklar:</span><span class="sxs-lookup"><span data-stu-id="330a2-210">For more information, see the following articles:</span></span>

- [<span data-ttu-id="330a2-211">Installera komponenter för ett jobb</span><span class="sxs-lookup"><span data-stu-id="330a2-211">Setting up the components of a job</span></span>](/dynamics365/unified-operations/talent/create-job)
- [<span data-ttu-id="330a2-212">Definiera nya jobb</span><span class="sxs-lookup"><span data-stu-id="330a2-212">Define new jobs</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-jobs)

##### <a name="positions"></a><span data-ttu-id="330a2-213">Befattningar</span><span class="sxs-lookup"><span data-stu-id="330a2-213">Positions</span></span>

<span data-ttu-id="330a2-214">En befattning är ett exempel på ett enskilt jobb.</span><span class="sxs-lookup"><span data-stu-id="330a2-214">A position is an individual instance of a job.</span></span> <span data-ttu-id="330a2-215">Befattningen "Försäljningschef (öst)" är exempelvis en av de befattningar som associeras med jobbet "Försäljningschef."</span><span class="sxs-lookup"><span data-stu-id="330a2-215">For example, the "Sales manager (East)" position is one of the positions that are associated with the "Sales manager" job.</span></span> <span data-ttu-id="330a2-216">En befattning finns på en avdelning.</span><span class="sxs-lookup"><span data-stu-id="330a2-216">A position exists in a department.</span></span> <span data-ttu-id="330a2-217">Endast en enda medarbetare kan vara associerad med respektive befattning.</span><span class="sxs-lookup"><span data-stu-id="330a2-217">Only one worker can be associated with each position.</span></span>

<span data-ttu-id="330a2-218">Tänk på följande uppgifter och konfigurationsinformation när du ställer in befattningar:</span><span class="sxs-lookup"><span data-stu-id="330a2-218">Keep the following data and configuration in mind when you set up positions:</span></span>

- <span data-ttu-id="330a2-219">Befattning (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="330a2-219">Position (required)</span></span>
- <span data-ttu-id="330a2-220">Beskrivning (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="330a2-220">Description (required)</span></span>
- <span data-ttu-id="330a2-221">Jobb (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="330a2-221">Job (required)</span></span>
- <span data-ttu-id="330a2-222">Avdelning (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="330a2-222">Department (required)</span></span>
- <span data-ttu-id="330a2-223">Befattningstyp (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="330a2-223">Position type (required)</span></span>
- <span data-ttu-id="330a2-224">Heltidslön</span><span class="sxs-lookup"><span data-stu-id="330a2-224">Full-time equivalent</span></span>
- <span data-ttu-id="330a2-225">Ordinarie timmar per år (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="330a2-225">Annual regular hours (required)</span></span>
- <span data-ttu-id="330a2-226">Betalas av den juridiska personen (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="330a2-226">Paid by legal entity (required)</span></span>
- <span data-ttu-id="330a2-227">Lönecykel (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="330a2-227">Pay cycle (required)</span></span>
- <span data-ttu-id="330a2-228">Standardekonomisk dimension – kostnadsställe (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="330a2-228">Default financial dimension – Cost center (required)</span></span>
- <span data-ttu-id="330a2-229">Medarbetartilldelning – medarbetare, tilldelningsstart, tilldelningsslut, orsakskod</span><span class="sxs-lookup"><span data-stu-id="330a2-229">Worker assignment – Worker, assignment start, assignment end, reason code</span></span>

<span data-ttu-id="330a2-230">Om flera befattningar på samma avdelning är associerade med samma jobb konsolideras de till en enda befattning i Dayforce.</span><span class="sxs-lookup"><span data-stu-id="330a2-230">If multiple positions in the same department are associated with the same job, they are consolidated into a single position in Dayforce.</span></span>

<span data-ttu-id="330a2-231">Mer information finns i följande artiklar:</span><span class="sxs-lookup"><span data-stu-id="330a2-231">For more information, see the following articles:</span></span>

- [<span data-ttu-id="330a2-232">Organisera arbetsstyrkan med avdelningar, jobb och befattningar</span><span class="sxs-lookup"><span data-stu-id="330a2-232">Organize your workforce using departments, jobs, and positions</span></span>](/dynamics365/unified-operations/talent/departments-jobs-positions#positions)
- [<span data-ttu-id="330a2-233">Ställ in befattningar</span><span class="sxs-lookup"><span data-stu-id="330a2-233">Set up positions</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/set-up-positions)

#### <a name="departments"></a><span data-ttu-id="330a2-234">Avdelningar</span><span class="sxs-lookup"><span data-stu-id="330a2-234">Departments</span></span>

<span data-ttu-id="330a2-235">En avdelning är en driftenhet som representerar en kategori eller verksamhetsområde inom en organisation.</span><span class="sxs-lookup"><span data-stu-id="330a2-235">A department is an operating unit that represents a category or functional area of an organization.</span></span> <span data-ttu-id="330a2-236">En avdelning är ansvarig för en viss del av organisationen, såsom försäljning, bokföring eller mänskliga resurser.</span><span class="sxs-lookup"><span data-stu-id="330a2-236">A department is responsible for a specific area of the organization, such as sales, accounting, or human resources.</span></span> <span data-ttu-id="330a2-237">Du kan använda avdelningar att rapportera om funktionella områden.</span><span class="sxs-lookup"><span data-stu-id="330a2-237">You can use departments to report on functional areas.</span></span> <span data-ttu-id="330a2-238">Avdelningar kan ha vinst och förlust.</span><span class="sxs-lookup"><span data-stu-id="330a2-238">Departments might have profit and loss responsibility.</span></span>

<span data-ttu-id="330a2-239">Mer information finns i följande artiklar:</span><span class="sxs-lookup"><span data-stu-id="330a2-239">For more information, see the following articles:</span></span>

- [<span data-ttu-id="330a2-240">Skapa en avdelning och associera den med avdelningshierarkin</span><span class="sxs-lookup"><span data-stu-id="330a2-240">Create a department and associate it with the department hierarchy</span></span>](/dynamics365/unified-operations/talent/create-department-add-department-hierarchy)
- [<span data-ttu-id="330a2-241">Definiera nya avdelningar</span><span class="sxs-lookup"><span data-stu-id="330a2-241">Define new departments</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-departments)

#### <a name="pay-cycles-and-pay-periods"></a><span data-ttu-id="330a2-242">Lönecykler och löneperioder</span><span class="sxs-lookup"><span data-stu-id="330a2-242">Pay cycles and pay periods</span></span>

<span data-ttu-id="330a2-243">En lönecykel avgör hur ofta lönelistan körs, samt vilka specifika dagar som medarbetarna får betalt.</span><span class="sxs-lookup"><span data-stu-id="330a2-243">A pay cycle determines how often payroll is run and the specific days when workers are paid.</span></span> <span data-ttu-id="330a2-244">En lönecykel kan exempelvis vara månadsvis och medarbetarna få sin lön den sista dagen i månaden.</span><span class="sxs-lookup"><span data-stu-id="330a2-244">For example, a pay cycle might be monthly, and employees might be paid on the last day of the month.</span></span> <span data-ttu-id="330a2-245">Alternativt kan en lönecykel vara veckovis och medarbetarna få sin lön på tisdagen efter betalningsperiodens utgång.</span><span class="sxs-lookup"><span data-stu-id="330a2-245">Alternatively, a pay cycle might be weekly, and employees might be paid on the Tuesday after the end of the pay period.</span></span> <span data-ttu-id="330a2-246">Lönecykler tilldelas befattningar i syfte att styra när arbetare på dessa befattningar får sin lön.</span><span class="sxs-lookup"><span data-stu-id="330a2-246">Pay cycles are assigned to positions to control when workers in those positions are paid.</span></span>

<span data-ttu-id="330a2-247">När du har skapat lönecykler kan du generera betalningsperioder för respektive cykel.</span><span class="sxs-lookup"><span data-stu-id="330a2-247">After you create pay cycles, you can generate pay periods for each cycle.</span></span> <span data-ttu-id="330a2-248">Varje betalningsperiod innehåller ett standardbetalningsdatum som baseras på den information du anger.</span><span class="sxs-lookup"><span data-stu-id="330a2-248">Each pay period includes a default payment date that is based on information that you provide.</span></span> <span data-ttu-id="330a2-249">Du kan emellertid ändra standarddatumet för betalning i en löneperiod i syfte att tillåta undantag, till exempel när betalningsdatumet infaller på en allmän helgdag.</span><span class="sxs-lookup"><span data-stu-id="330a2-249">However, you can modify the default payment date in a pay period to allow for exceptions, such as when the payment date falls on a holiday.</span></span>

<span data-ttu-id="330a2-250">Följande information används i Dayforce:</span><span class="sxs-lookup"><span data-stu-id="330a2-250">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="330a2-251">Lönecykel (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="330a2-251">Pay cycle (required)</span></span>
- <span data-ttu-id="330a2-252">Lönecykelfrekvens (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="330a2-252">Pay cycle frequency (required)</span></span>
- <span data-ttu-id="330a2-253">Periodens startdatum (första löneperiod obligatorisk)</span><span class="sxs-lookup"><span data-stu-id="330a2-253">Period start date (first pay period required)</span></span>
- <span data-ttu-id="330a2-254">Standarddatum för betalning (första löneperiod obligatorisk)</span><span class="sxs-lookup"><span data-stu-id="330a2-254">Default payment date (first pay period required)</span></span>

<span data-ttu-id="330a2-255">Denna information är integrerad i Dayforce som lönegrupper och delas upp efter land eller region för respektive lönecykel.</span><span class="sxs-lookup"><span data-stu-id="330a2-255">This information is integrated with Dayforce as pay groups, and is separated by country or region for each pay cycle.</span></span> <span data-ttu-id="330a2-256">Minst en löneperiod måste genereras före integration.</span><span class="sxs-lookup"><span data-stu-id="330a2-256">At least one pay period must be generated before integration.</span></span> <span data-ttu-id="330a2-257">Dayforce genererar gruppkalendrar för lön och betalningsdatum utifrån startdatumet för den första löneperioden och det standarddatum för betalning som anges i Personal.</span><span class="sxs-lookup"><span data-stu-id="330a2-257">Dayforce generates pay group calendars and payment dates, based on the start date of the first pay period and the default payment date that is set up in Human Resources.</span></span>

#### <a name="earning-codes"></a><span data-ttu-id="330a2-258">Inkomstkoder</span><span class="sxs-lookup"><span data-stu-id="330a2-258">Earning codes</span></span>

<span data-ttu-id="330a2-259">Inkomstkoder identifierar individuellt alla typer av arbetstagarintäkter.</span><span class="sxs-lookup"><span data-stu-id="330a2-259">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="330a2-260">Koderna har olika parametrar som rör inkomster, till exempel redovisningsbestämmelser, skattelagar, rapporteringskrav, och gross up-kapacitet.</span><span class="sxs-lookup"><span data-stu-id="330a2-260">The codes have various parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span>

<span data-ttu-id="330a2-261">Följande information används i Dayforce:</span><span class="sxs-lookup"><span data-stu-id="330a2-261">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="330a2-262">Inkomstkod (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="330a2-262">Earning Code (required)</span></span>
- <span data-ttu-id="330a2-263">beskrivning</span><span class="sxs-lookup"><span data-stu-id="330a2-263">Description</span></span>
- <span data-ttu-id="330a2-264">Enhet</span><span class="sxs-lookup"><span data-stu-id="330a2-264">Unit of measure</span></span>
- <span data-ttu-id="330a2-265">Produktiv</span><span class="sxs-lookup"><span data-stu-id="330a2-265">Productive</span></span>

### <a name="worker-data"></a><span data-ttu-id="330a2-266">Medarbetardata</span><span class="sxs-lookup"><span data-stu-id="330a2-266">Worker data</span></span>

<span data-ttu-id="330a2-267">Poster för de olika typer av medarbetare som du har är viktiga för dina personal- och lönesystem.</span><span class="sxs-lookup"><span data-stu-id="330a2-267">Records for the various types of workers that you have are important to your human resources and payroll systems.</span></span> <span data-ttu-id="330a2-268">Den information du anger kan användas för att spåra medarbetare och personuppgifter.</span><span class="sxs-lookup"><span data-stu-id="330a2-268">The information that you enter can be used to track workers and personal information.</span></span>

<span data-ttu-id="330a2-269">För medarbetare kan du behålla följande information:</span><span class="sxs-lookup"><span data-stu-id="330a2-269">You can maintain the following information for workers:</span></span>

- <span data-ttu-id="330a2-270">**Grundläggande** – Grundläggande information om en medarbetare, till exempel kontaktinformation, demografisk information, identifikationsinformation, familjeinformation, status för militärtjänst, exilstatusinformation samt personliga och nödkontakter.</span><span class="sxs-lookup"><span data-stu-id="330a2-270">**Basic** – Maintain basic information about a worker, such as contact information, demographic information, identification information, family information, military service status, expatriate information, and personal and emergency contacts.</span></span>
- <span data-ttu-id="330a2-271">**Anställning** – Information om en medarbetares anställning, exempelvis företags- eller organisationstillhörighet, befattningstilldelning, start- och slutdatum, jobbtillgänglighet, anställningsvillkor, pension, semester- samt omplaceringsinformation.</span><span class="sxs-lookup"><span data-stu-id="330a2-271">**Employment** – Maintain information about a worker's employment, such as company or organization affiliation, position assignment, start and end dates, work eligibility, terms of employment, pension, vacation, and relocation information.</span></span>
- <span data-ttu-id="330a2-272">**Tjänstledighet och frånvaro** – Information om en medarbetares frånvaro, exempelvis jobbkalendrar, frånvarotransaktioner samt frånvaroinställningar.</span><span class="sxs-lookup"><span data-stu-id="330a2-272">**Leave and absence** – Maintain information about a worker's absences, such as working calendars, absence transactions, and absence setup.</span></span>
- <span data-ttu-id="330a2-273">**Ersättning och lön** – Information om en medarbetares ersättningsplaner och löneinformation, exempelvis plananmälan, utmärkelser, resultat, provision, skatteinformation, pensionering samt löneavdrag.</span><span class="sxs-lookup"><span data-stu-id="330a2-273">**Compensation and payroll** – Maintain information about a worker's compensation plans and payroll information, such as plan enrollment, awards, performance, commission, tax information, retirement, and salary deductions.</span></span>

<span data-ttu-id="330a2-274">När du anger medarbetarinformation, kom då ihåg följande uppgifter och konfigurationer som används i Dayforce.</span><span class="sxs-lookup"><span data-stu-id="330a2-274">When you enter worker information, keep in mind the following data and configurations that are used in Dayforce.</span></span>

#### <a name="general-information"></a><span data-ttu-id="330a2-275">Allmän information</span><span class="sxs-lookup"><span data-stu-id="330a2-275">General information</span></span>

- <span data-ttu-id="330a2-276">Anställningsnummer (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="330a2-276">Personnel number (required)</span></span>
- <span data-ttu-id="330a2-277">Förnamn (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="330a2-277">First name (required)</span></span>
- <span data-ttu-id="330a2-278">Efternamn (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="330a2-278">Last name (required)</span></span>
- <span data-ttu-id="330a2-279">Mellannamn</span><span class="sxs-lookup"><span data-stu-id="330a2-279">Middle name</span></span>
- <span data-ttu-id="330a2-280">Datum för tjänsteålder</span><span class="sxs-lookup"><span data-stu-id="330a2-280">Seniority date</span></span>
- <span data-ttu-id="330a2-281">Känt som</span><span class="sxs-lookup"><span data-stu-id="330a2-281">Known as</span></span>

#### <a name="personal-information"></a><span data-ttu-id="330a2-282">Personlig information</span><span class="sxs-lookup"><span data-stu-id="330a2-282">Personal information</span></span>

- <span data-ttu-id="330a2-283">Civilstånd (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="330a2-283">Marital status (required)</span></span>
- <span data-ttu-id="330a2-284">Födelsedatum (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="330a2-284">Birth date (required)</span></span>
- <span data-ttu-id="330a2-285">Könstillhörighet (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="330a2-285">Gender (required)</span></span>
- <span data-ttu-id="330a2-286">Person med funktionsnedsättningar</span><span class="sxs-lookup"><span data-stu-id="330a2-286">Person with disabilities</span></span>
- <span data-ttu-id="330a2-287">Medborgarskap, land, region (endast för Mexiko)</span><span class="sxs-lookup"><span data-stu-id="330a2-287">Nationality country region (only for Mexico)</span></span>

#### <a name="address-information"></a><span data-ttu-id="330a2-288">Adressinformation</span><span class="sxs-lookup"><span data-stu-id="330a2-288">Address information</span></span>

- <span data-ttu-id="330a2-289">Primär adress (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="330a2-289">Primary (required)</span></span>
- <span data-ttu-id="330a2-290">Land/region (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="330a2-290">Country/region (required)</span></span>
- <span data-ttu-id="330a2-291">Postnummer (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="330a2-291">Postal code (required)</span></span>
- <span data-ttu-id="330a2-292">Nummer (obligatoriskt) (endast för Mexiko)</span><span class="sxs-lookup"><span data-stu-id="330a2-292">Street Number (required) (Only for Mexico)</span></span>
- <span data-ttu-id="330a2-293">Byggnadskomplement (endast för Mexiko)</span><span class="sxs-lookup"><span data-stu-id="330a2-293">Building Complement (Only for Mexico)</span></span>
- <span data-ttu-id="330a2-294">Stad (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="330a2-294">City (required)</span></span>
- <span data-ttu-id="330a2-295">Delstat (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="330a2-295">State (required)</span></span>
- <span data-ttu-id="330a2-296">Region (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="330a2-296">County (required)</span></span>

#### <a name="contact-information"></a><span data-ttu-id="330a2-297">Kontaktinformation</span><span class="sxs-lookup"><span data-stu-id="330a2-297">Contact information</span></span> 

- <span data-ttu-id="330a2-298">Primär adress (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="330a2-298">Primary (required)</span></span>
- <span data-ttu-id="330a2-299">Kontaktnummer (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="330a2-299">Contact number (required)</span></span>
- <span data-ttu-id="330a2-300">Anknytning</span><span class="sxs-lookup"><span data-stu-id="330a2-300">Extension</span></span>

#### <a name="payroll-information-and-earning-codes"></a><span data-ttu-id="330a2-301">Löneinformation och inkomstkoder</span><span class="sxs-lookup"><span data-stu-id="330a2-301">Payroll information and earning codes</span></span>

<span data-ttu-id="330a2-302">Medarbetare kan tilldelas en viss inkomst till en viss betalningsfrekvens och ha en prioriterad betalningsmetod.</span><span class="sxs-lookup"><span data-stu-id="330a2-302">Employees may be assigned specific earnings at a given frequency of payment and have a preferred payment method.</span></span> <span data-ttu-id="330a2-303">Följande fält används i Dayforce för att garantera att dessa prioriteringar och inställningar används.</span><span class="sxs-lookup"><span data-stu-id="330a2-303">The following fields are used in Dayforce to help guarantee that those preferences and settings are used.</span></span>

##### <a name="earning-codes"></a><span data-ttu-id="330a2-304">Inkomstkoder</span><span class="sxs-lookup"><span data-stu-id="330a2-304">Earning codes</span></span>

- <span data-ttu-id="330a2-305">Befattning (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="330a2-305">Position (required)</span></span>
- <span data-ttu-id="330a2-306">Inkomstkod (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="330a2-306">Earning Code (required)</span></span>
- <span data-ttu-id="330a2-307">Frekvens (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="330a2-307">Frequency (required)</span></span>
- <span data-ttu-id="330a2-308">Belopp (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="330a2-308">Amount (required)</span></span>

##### <a name="payroll-information"></a><span data-ttu-id="330a2-309">Löneinformation</span><span class="sxs-lookup"><span data-stu-id="330a2-309">Payroll information</span></span>

- <span data-ttu-id="330a2-310">Betalningsmetod</span><span class="sxs-lookup"><span data-stu-id="330a2-310">Payment Method</span></span>
- <span data-ttu-id="330a2-311">Ekonomisk region (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="330a2-311">Economic Region (required)</span></span>
- <span data-ttu-id="330a2-312">ID för anställningsförmåner</span><span class="sxs-lookup"><span data-stu-id="330a2-312">Employee Benefits ID</span></span>
- <span data-ttu-id="330a2-313">Nationellt ID-nummer (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="330a2-313">National ID Number (required)</span></span>
- <span data-ttu-id="330a2-314">Militärtjänstgöring, nummer</span><span class="sxs-lookup"><span data-stu-id="330a2-314">Military Service Number</span></span>
- <span data-ttu-id="330a2-315">Skiftes-ID (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="330a2-315">Shift ID (required)</span></span>
- <span data-ttu-id="330a2-316">Skattenummer (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="330a2-316">Tax Number (required)</span></span>
- <span data-ttu-id="330a2-317">Fack-ID (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="330a2-317">Union ID (required)</span></span>
- <span data-ttu-id="330a2-318">Arbetsdags-ID (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="330a2-318">Work Day ID (required)</span></span>
- <span data-ttu-id="330a2-319">Arbetstillståndsnummer</span><span class="sxs-lookup"><span data-stu-id="330a2-319">Work Permit Number</span></span>

> [!NOTE]
> <span data-ttu-id="330a2-320">För betalsättet stöder Mexiko **Kontant**, **Check** (företagets fysiska check), samt **Elektronisk betalning**.</span><span class="sxs-lookup"><span data-stu-id="330a2-320">For the payment method, Mexico supports **Cash**, **Check** (the company's physical check), and **Electronic Payment**.</span></span> <span data-ttu-id="330a2-321">Om betalsättet np anges används **Check** som standard.</span><span class="sxs-lookup"><span data-stu-id="330a2-321">If np payment method is specified, **Check** is used by default.</span></span>

#### <a name="employment-details"></a><span data-ttu-id="330a2-322">Anställningsinformation</span><span class="sxs-lookup"><span data-stu-id="330a2-322">Employment details</span></span>

<span data-ttu-id="330a2-323">Detaljerad anställningshistorik används som viktig information i syfte att hämta en medarbetares anställnings-, uppsägnings- och återanställningsstatus i Dayforce.</span><span class="sxs-lookup"><span data-stu-id="330a2-323">Employment detail history is used as key information to derive an employee's hire, termination, and rehire statuses in Dayforce.</span></span> <span data-ttu-id="330a2-324">Dayforce stöder endast en aktiv anställningspost åt gången.</span><span class="sxs-lookup"><span data-stu-id="330a2-324">Dayforce supports only one active employment record at a time.</span></span>

- <span data-ttu-id="330a2-325">Startdatum för anställning (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="330a2-325">Employment start date (required)</span></span>
- <span data-ttu-id="330a2-326">Slutdatum för anställning</span><span class="sxs-lookup"><span data-stu-id="330a2-326">Employment end date</span></span>
- <span data-ttu-id="330a2-327">Startdatum</span><span class="sxs-lookup"><span data-stu-id="330a2-327">Start date</span></span>
- <span data-ttu-id="330a2-328">Justerat startdatum</span><span class="sxs-lookup"><span data-stu-id="330a2-328">Adjusted start date</span></span>
- <span data-ttu-id="330a2-329">Uppsägningsdatum (obligatoriskt vid uppsägning)</span><span class="sxs-lookup"><span data-stu-id="330a2-329">Termination date (required upon termination)</span></span>
- <span data-ttu-id="330a2-330">Uppsägningsorsak (obligatoriskt vid uppsägning)</span><span class="sxs-lookup"><span data-stu-id="330a2-330">Termination reason (required upon termination)</span></span>

<span data-ttu-id="330a2-331">Medarbetarens viktiga datum beräknas med hjälp av följande information.</span><span class="sxs-lookup"><span data-stu-id="330a2-331">An employee's key dates are derived by using the following information.</span></span>

| <span data-ttu-id="330a2-332">Personal</span><span class="sxs-lookup"><span data-stu-id="330a2-332">Human Resources</span></span>                | <span data-ttu-id="330a2-333">Dayforce</span><span class="sxs-lookup"><span data-stu-id="330a2-333">Dayforce</span></span>                                                                                             |
|-----------------------|------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="330a2-334">Senaste anställningsdatum</span><span class="sxs-lookup"><span data-stu-id="330a2-334">Most recent hire date</span></span> | <span data-ttu-id="330a2-335">Anställningsstart för aktuell, icke-uppsagd post för anställningshistorik</span><span class="sxs-lookup"><span data-stu-id="330a2-335">Employment start of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="330a2-336">Uppsägningsdatum</span><span class="sxs-lookup"><span data-stu-id="330a2-336">Termination date</span></span>      | <span data-ttu-id="330a2-337">Uppsägningsdatum för aktuell, icke-uppsagd post för anställningshistorik</span><span class="sxs-lookup"><span data-stu-id="330a2-337">Termination date of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="330a2-338">Startdatum</span><span class="sxs-lookup"><span data-stu-id="330a2-338">Start date</span></span>            | <span data-ttu-id="330a2-339">Justerat startdatum, startdatum eller anställningsstart för aktuell, inaktiv post för anställningshistorik</span><span class="sxs-lookup"><span data-stu-id="330a2-339">Adjusted start date, start date, or employment start of current non-active employment history record</span></span> |
| <span data-ttu-id="330a2-340">Ursprungligt anställningsdatum</span><span class="sxs-lookup"><span data-stu-id="330a2-340">Original hire date</span></span>    | <span data-ttu-id="330a2-341">Anställningsstart för tidigaste anställningshistorikpost</span><span class="sxs-lookup"><span data-stu-id="330a2-341">Employment start of earliest employment history record</span></span>                                               |

#### <a name="compensation"></a><span data-ttu-id="330a2-342">Kompensation</span><span class="sxs-lookup"><span data-stu-id="330a2-342">Compensation</span></span>

<span data-ttu-id="330a2-343">En fast kompensationsplan måste kopplas till varje medarbetares primära befattning under hela anställningsperioden.</span><span class="sxs-lookup"><span data-stu-id="330a2-343">A fixed compensation plan must be associated with every employee's primary position throughout an employment period.</span></span> <span data-ttu-id="330a2-344">Perioden inleds det datum då medarbetaren anställts (eller på anställningens startdatum) och fortsätter till och med uppsägningen.</span><span class="sxs-lookup"><span data-stu-id="330a2-344">This period starts on the date that the employee was hired (or the employment start date) and continues until termination.</span></span>

- <span data-ttu-id="330a2-345">Giltighetsdatum (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="330a2-345">Effective Date (required)</span></span>
- <span data-ttu-id="330a2-346">Utgångsdatum</span><span class="sxs-lookup"><span data-stu-id="330a2-346">Expiration date</span></span>
- <span data-ttu-id="330a2-347">Lönesats (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="330a2-347">Pay Rate (required)</span></span>
- <span data-ttu-id="330a2-348">Lönesatskonverteringar (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="330a2-348">Pay Rate Conversions (required)</span></span>
- <span data-ttu-id="330a2-349">Årlig motsvarighet (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="330a2-349">Annual equivalent (required)</span></span>
- <span data-ttu-id="330a2-350">Motsvarighet per timme (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="330a2-350">Hourly equivalent (required)</span></span>

<span data-ttu-id="330a2-351">Om en timanställd har flera befattningar importeras den fasta kompensationen för den primära befattningen till Dayforce som bastariff/-lön för medarbetaren.</span><span class="sxs-lookup"><span data-stu-id="330a2-351">If an hourly employee has multiple positions, the fixed compensation of the primary position is imported into Dayforce as the employee-level base rate/salary.</span></span> <span data-ttu-id="330a2-352">För icke-primära befattningar sparas timtariffen i motsvarande befattning i Dayforce.</span><span class="sxs-lookup"><span data-stu-id="330a2-352">For non-primary positions, the hourly rate is saved to the corresponding position in Dayforce.</span></span>

<span data-ttu-id="330a2-353">Om en fast anställd tjänsteman har flera befattningar hämtas den ackumulerade timtariffen och årslönen för samtliga aktiva befattningar och används som bastariff/-lön för medarbetarnivån.</span><span class="sxs-lookup"><span data-stu-id="330a2-353">If a salaried employee has multiple positions, the cumulative hour rate and annual salary across all active positions are derived and used as the employee-level base rate/salary.</span></span>

#### <a name="identification-numbers"></a><span data-ttu-id="330a2-354">Identifieringsnummer</span><span class="sxs-lookup"><span data-stu-id="330a2-354">Identification numbers</span></span>

##### <a name="social-security-identifier"></a><span data-ttu-id="330a2-355">Socialförsäkrings-identifierare</span><span class="sxs-lookup"><span data-stu-id="330a2-355">Social Security identifier</span></span> 

<span data-ttu-id="330a2-356">Alla medarbetare måste ha en primär identifierare.</span><span class="sxs-lookup"><span data-stu-id="330a2-356">Every employee must have one primary identifier.</span></span> <span data-ttu-id="330a2-357">Denna identifierare måste vara av identifieringstypen **SSN**.</span><span class="sxs-lookup"><span data-stu-id="330a2-357">This identifier must be of **SSN** identification type.</span></span> <span data-ttu-id="330a2-358">I Dayforce hämtas den automatiskt som den socialförsäkringsidentifierare för anställd som krävs för anställning.</span><span class="sxs-lookup"><span data-stu-id="330a2-358">In Dayforce, it's automatically derived as the employee's Social Security identifier that is required for hire.</span></span>

- <span data-ttu-id="330a2-359">Primär adress (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="330a2-359">Primary (required)</span></span>
- <span data-ttu-id="330a2-360">Identifieringstyp = "SSN"</span><span class="sxs-lookup"><span data-stu-id="330a2-360">Identification Type = "SSN"</span></span>
- <span data-ttu-id="330a2-361">Utfärdat den</span><span class="sxs-lookup"><span data-stu-id="330a2-361">Issued Date</span></span>
- <span data-ttu-id="330a2-362">Utgångsdatum</span><span class="sxs-lookup"><span data-stu-id="330a2-362">Expiration Date</span></span>

<span data-ttu-id="330a2-363">Medarbetare kan deklarera flera ID-nummer med ID-typen **SSN**.</span><span class="sxs-lookup"><span data-stu-id="330a2-363">Employees can declare multiple identification numbers of the **SSN** identification type.</span></span> <span data-ttu-id="330a2-364">Endast posten som är markerad som **Primär** integreras emellertid i Dayforce, oavsett om numret är aktivt eller har upphört att gälla.</span><span class="sxs-lookup"><span data-stu-id="330a2-364">However, only the record that is marked as **Primary** is integrated into Dayforce, regardless of whether the number is active or expired.</span></span>

#### <a name="bank-accounts-and-disbursements"></a><span data-ttu-id="330a2-365">Bankkonton och utbetalningar</span><span class="sxs-lookup"><span data-stu-id="330a2-365">Bank accounts and disbursements</span></span>

<span data-ttu-id="330a2-366">Giltig bankkontoinformation måste anges för varje medarbetare som väljer att få sin lön via bankkontoöverföringar.</span><span class="sxs-lookup"><span data-stu-id="330a2-366">Valid bank account information must be entered for any employee who chooses to be paid via bank account transfers.</span></span>

| <span data-ttu-id="330a2-367">Personal</span><span class="sxs-lookup"><span data-stu-id="330a2-367">Human Resources</span></span>                         | <span data-ttu-id="330a2-368">Dayforce</span><span class="sxs-lookup"><span data-stu-id="330a2-368">Dayforce</span></span>                                                                                                    |
|--------------------------------|-------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="330a2-369">Bankkontonummer (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="330a2-369">Bank account number (required)</span></span> |                                                                                                             |
| <span data-ttu-id="330a2-370">SWIFT-kod (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="330a2-370">SWIFT code (required)</span></span>          | <span data-ttu-id="330a2-371">Fältet **Bank-ID** används när löner bearbetas i Mexiko.</span><span class="sxs-lookup"><span data-stu-id="330a2-371">**Bank ID** field used when processing payroll in Mexico.</span></span>                                                             |
| <span data-ttu-id="330a2-372">Filialnummer (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="330a2-372">Branch number (required)</span></span>       |                                                                                                             |
| <span data-ttu-id="330a2-373">Bankkontotyp (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="330a2-373">Bank account type (required)</span></span>   | <span data-ttu-id="330a2-374">Fältet **Kontotyp** används när löner bearbetas i Mexiko.</span><span class="sxs-lookup"><span data-stu-id="330a2-374">**Account type** field used when processing payroll in Mexico.</span></span> <span data-ttu-id="330a2-375">Värden som stöds inkluderar **Check** och **Lönelista**.</span><span class="sxs-lookup"><span data-stu-id="330a2-375">Supported values include **Checking** and **Payroll**.</span></span> |

> [!NOTE]
> <span data-ttu-id="330a2-376">Medarbetare som väljer att få lön via bankkontoöverföring måste ange en länk till ett restkonto tillhörande en juridisk person med primär adress i Mexiko och som är associerad med ett giltigt bankkonto från en mexikansk bank.</span><span class="sxs-lookup"><span data-stu-id="330a2-376">Employees who choose to be paid via bank account transfers must provide a link to a remainder account that is under a legal entity that has its primary address in Mexico and associated with a valid bank account from a Mexican bank.</span></span> <span data-ttu-id="330a2-377">Alla övriga restkonton ignoreras.</span><span class="sxs-lookup"><span data-stu-id="330a2-377">All other non-remainder accounts are ignored.</span></span>

#### <a name="address-information"></a><span data-ttu-id="330a2-378">Adressinformation</span><span class="sxs-lookup"><span data-stu-id="330a2-378">Address information</span></span>

<span data-ttu-id="330a2-379">Alla medarbetare måste ha en primär plats.</span><span class="sxs-lookup"><span data-stu-id="330a2-379">Every employee must have one primary location.</span></span> <span data-ttu-id="330a2-380">Den här platsen används i Dayforce i syfte att fastställa medarbetarens primära hemort i skattesyfte.</span><span class="sxs-lookup"><span data-stu-id="330a2-380">In Dayforce, this location is used to determine the employee's primary residence for tax purposes.</span></span>

- <span data-ttu-id="330a2-381">Primär adress (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="330a2-381">Primary (required)</span></span>
- <span data-ttu-id="330a2-382">Land/region (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="330a2-382">Country/region (required)</span></span>
- <span data-ttu-id="330a2-383">Postnummer (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="330a2-383">Zip/postal code (required)</span></span>
- <span data-ttu-id="330a2-384">Gata (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="330a2-384">Street (required)</span></span>
- <span data-ttu-id="330a2-385">Nummer (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="330a2-385">Street Number (required)</span></span>
- <span data-ttu-id="330a2-386">Byggnadskomplement</span><span class="sxs-lookup"><span data-stu-id="330a2-386">Building Complement</span></span>
- <span data-ttu-id="330a2-387">Stad (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="330a2-387">City (required)</span></span>
- <span data-ttu-id="330a2-388">Delstat (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="330a2-388">State (required)</span></span>
- <span data-ttu-id="330a2-389">Region (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="330a2-389">County (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-united-states-and-canada"></a><span data-ttu-id="330a2-390">Konfigurera dina data för att generera lön i USA och Kanada</span><span class="sxs-lookup"><span data-stu-id="330a2-390">Configure your data to generate payroll in United States and Canada</span></span>

<span data-ttu-id="330a2-391">Om du genererar lön för medarbetare i USA och Kanada måste följande element konfigureras:</span><span class="sxs-lookup"><span data-stu-id="330a2-391">If you're generating pay for employees in the United States and Canada, the following elements must be configured:</span></span>

- <span data-ttu-id="330a2-392">Avdelningar är obligatoriska vid befattningarna:</span><span class="sxs-lookup"><span data-stu-id="330a2-392">Departments are required on positions.</span></span>
- <span data-ttu-id="330a2-393">Kostnadsställen måste ställas in som ekonomiska dimensioner och måste vara det första elementet i standardsträngen för ekonomisk dimension.</span><span class="sxs-lookup"><span data-stu-id="330a2-393">Cost centers must be set as financial dimensions and must be the first element in the default financial dimension string.</span></span>

> [!NOTE] 
> <span data-ttu-id="330a2-394">Du kan konfigurera Personal att kräva att befattningar anger en avdelning.</span><span class="sxs-lookup"><span data-stu-id="330a2-394">You can configure Human Resources to require that Positions specify a Department.</span></span> <span data-ttu-id="330a2-395">Gör detta genom att gå till **delade befattningar i Personal > befattningar > kräver avdelningar för befattningar**.</span><span class="sxs-lookup"><span data-stu-id="330a2-395">To do this, go to **Human Resources Shared Positions > Positions > Require departments on positions**.</span></span> <span data-ttu-id="330a2-396">Vi rekommenderar att den här inställningen tillämpas för integration.</span><span class="sxs-lookup"><span data-stu-id="330a2-396">We recommend that this setting be enforced for the integration.</span></span>

### <a name="job-types"></a><span data-ttu-id="330a2-397">Jobbtyper</span><span class="sxs-lookup"><span data-stu-id="330a2-397">Job types</span></span>

<span data-ttu-id="330a2-398">Jobbtyper används för att gruppera liknande jobb i kategorier.</span><span class="sxs-lookup"><span data-stu-id="330a2-398">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="330a2-399">Jobbtyper krävs för att bearbeta lön i USA och Kanada.</span><span class="sxs-lookup"><span data-stu-id="330a2-399">Job types are required in order to process payroll in the United States and Canada.</span></span> <span data-ttu-id="330a2-400">Några exempel på jobbtyper är heltid och deltid, eller fast lön och timpenning.</span><span class="sxs-lookup"><span data-stu-id="330a2-400">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="330a2-401">Jobbtyper mappas till Dayforce som lönetyper som anger huruvida en anställd arbetar per timme eller har fast lön.</span><span class="sxs-lookup"><span data-stu-id="330a2-401">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="330a2-402">Följande jobbtyper och beskrivningar krävs.</span><span class="sxs-lookup"><span data-stu-id="330a2-402">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="330a2-403">Jobbtyp</span><span class="sxs-lookup"><span data-stu-id="330a2-403">Job type</span></span>   | <span data-ttu-id="330a2-404">beskrivning</span><span class="sxs-lookup"><span data-stu-id="330a2-404">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="330a2-405">Varje timme</span><span class="sxs-lookup"><span data-stu-id="330a2-405">Hourly</span></span>     | <span data-ttu-id="330a2-406">Varje timme</span><span class="sxs-lookup"><span data-stu-id="330a2-406">Hourly</span></span>      |
| <span data-ttu-id="330a2-407">Fast lön</span><span class="sxs-lookup"><span data-stu-id="330a2-407">Salaried</span></span>   | <span data-ttu-id="330a2-408">Fast lön</span><span class="sxs-lookup"><span data-stu-id="330a2-408">Salaried</span></span>    |

### <a name="position-types"></a><span data-ttu-id="330a2-409">Befattningstyper</span><span class="sxs-lookup"><span data-stu-id="330a2-409">Position types</span></span> 

<span data-ttu-id="330a2-410">Du kan använda befattningstyper för att beskriva huruvida befattningen är på heltid, deltid eller annat.</span><span class="sxs-lookup"><span data-stu-id="330a2-410">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="330a2-411">Befattningstyper mappas till Dayforce som löneklasser som anger huruvida en anställd arbetar heltid eller deltid.</span><span class="sxs-lookup"><span data-stu-id="330a2-411">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="330a2-412">Följande befattningstyper och beskrivningar krävs.</span><span class="sxs-lookup"><span data-stu-id="330a2-412">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="330a2-413">Befattningstyp</span><span class="sxs-lookup"><span data-stu-id="330a2-413">Position type</span></span>   | <span data-ttu-id="330a2-414">beskrivning</span><span class="sxs-lookup"><span data-stu-id="330a2-414">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="330a2-415">Heltid</span><span class="sxs-lookup"><span data-stu-id="330a2-415">Full-time</span></span>       | <span data-ttu-id="330a2-416">Heltidsanställd</span><span class="sxs-lookup"><span data-stu-id="330a2-416">Full time employee</span></span> |
| <span data-ttu-id="330a2-417">Deltid</span><span class="sxs-lookup"><span data-stu-id="330a2-417">Part-time</span></span>       | <span data-ttu-id="330a2-418">Deltidsanställd</span><span class="sxs-lookup"><span data-stu-id="330a2-418">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="330a2-419">Orsakskoder</span><span class="sxs-lookup"><span data-stu-id="330a2-419">Reason codes</span></span>

<span data-ttu-id="330a2-420">Orsakskoder innehåller information om statusen för en medarbetare.</span><span class="sxs-lookup"><span data-stu-id="330a2-420">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="330a2-421">Orsakskoder mappas till Dayforce som statusanledningar som anger orsaken till ändringar i en medarbetares befattning eller anställningsstatus.</span><span class="sxs-lookup"><span data-stu-id="330a2-421">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="330a2-422">Följande orsakskoder och -beskrivningar krävs.</span><span class="sxs-lookup"><span data-stu-id="330a2-422">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="330a2-423">Orsakskod</span><span class="sxs-lookup"><span data-stu-id="330a2-423">Reason code</span></span>    | <span data-ttu-id="330a2-424">beskrivning</span><span class="sxs-lookup"><span data-stu-id="330a2-424">Description</span></span>      | <span data-ttu-id="330a2-425">Tillämpliga scenarier</span><span class="sxs-lookup"><span data-stu-id="330a2-425">Applicable scenarios</span></span> |
|----------------|------------------|----------------------|
| <span data-ttu-id="330a2-426">EGEN UPPSÄGNING</span><span class="sxs-lookup"><span data-stu-id="330a2-426">RESIGNATION</span></span>    | <span data-ttu-id="330a2-427">Egen uppsägning</span><span class="sxs-lookup"><span data-stu-id="330a2-427">Resignation</span></span>      | <span data-ttu-id="330a2-428">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="330a2-428">Terminate worker</span></span>     |
| <span data-ttu-id="330a2-429">UPPSÄGNING</span><span class="sxs-lookup"><span data-stu-id="330a2-429">TERMINATION</span></span>    | <span data-ttu-id="330a2-430">Uppsägning</span><span class="sxs-lookup"><span data-stu-id="330a2-430">Termination</span></span>      | <span data-ttu-id="330a2-431">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="330a2-431">Terminate worker</span></span>     |
| <span data-ttu-id="330a2-432">PENSION</span><span class="sxs-lookup"><span data-stu-id="330a2-432">RETIREMENT</span></span>     | <span data-ttu-id="330a2-433">Pension</span><span class="sxs-lookup"><span data-stu-id="330a2-433">Retirement</span></span>       | <span data-ttu-id="330a2-434">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="330a2-434">Terminate worker</span></span>     |
| <span data-ttu-id="330a2-435">ÖVRIGT</span><span class="sxs-lookup"><span data-stu-id="330a2-435">OTHER</span></span>          | <span data-ttu-id="330a2-436">Andra orsaker</span><span class="sxs-lookup"><span data-stu-id="330a2-436">Other Reasons</span></span>    | <span data-ttu-id="330a2-437">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="330a2-437">Terminate worker</span></span>     |
| <span data-ttu-id="330a2-438">DÖDSFALL</span><span class="sxs-lookup"><span data-stu-id="330a2-438">DEATH</span></span>          | <span data-ttu-id="330a2-439">Dödsfall</span><span class="sxs-lookup"><span data-stu-id="330a2-439">Death</span></span>            | <span data-ttu-id="330a2-440">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="330a2-440">Terminate worker</span></span>     |
| <span data-ttu-id="330a2-441">TJÄNSTLEDIGHET</span><span class="sxs-lookup"><span data-stu-id="330a2-441">LEAVEOFABSENCE</span></span> | <span data-ttu-id="330a2-442">Tjänstledighet</span><span class="sxs-lookup"><span data-stu-id="330a2-442">Leave of Absence</span></span> | <span data-ttu-id="330a2-443">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="330a2-443">Terminate worker</span></span>     |
| <span data-ttu-id="330a2-444">KONTRAKTSLUT</span><span class="sxs-lookup"><span data-stu-id="330a2-444">CONTRACTEND</span></span>    | <span data-ttu-id="330a2-445">Kontraktslut</span><span class="sxs-lookup"><span data-stu-id="330a2-445">End of Contract</span></span>  | <span data-ttu-id="330a2-446">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="330a2-446">Terminate worker</span></span>     |
| <span data-ttu-id="330a2-447">LÖNEÄNDRING</span><span class="sxs-lookup"><span data-stu-id="330a2-447">SALARYCHANGE</span></span>   | <span data-ttu-id="330a2-448">Löneändring</span><span class="sxs-lookup"><span data-stu-id="330a2-448">Change of Salary</span></span> | <span data-ttu-id="330a2-449">Kompensation</span><span class="sxs-lookup"><span data-stu-id="330a2-449">Compensation</span></span>         |

### <a name="marital-status"></a><span data-ttu-id="330a2-450">Civilstånd</span><span class="sxs-lookup"><span data-stu-id="330a2-450">Marital status</span></span>

<span data-ttu-id="330a2-451">Civilståndsvärden mappas till Dayforce och översätts på lämpligt sätt till giltiga värden i samband med integrering.</span><span class="sxs-lookup"><span data-stu-id="330a2-451">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="330a2-452">Följande tabell visar hur civilståndsvärden mappas till Dayforce.</span><span class="sxs-lookup"><span data-stu-id="330a2-452">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="330a2-453">Personal</span><span class="sxs-lookup"><span data-stu-id="330a2-453">Human Resources</span></span>                 | <span data-ttu-id="330a2-454">Dayforce</span><span class="sxs-lookup"><span data-stu-id="330a2-454">Dayforce</span></span>             |
|------------------------|----------------------|
| <span data-ttu-id="330a2-455">Gift</span><span class="sxs-lookup"><span data-stu-id="330a2-455">Married</span></span>                | <span data-ttu-id="330a2-456">Gift</span><span class="sxs-lookup"><span data-stu-id="330a2-456">Married</span></span>              |
| <span data-ttu-id="330a2-457">Ett</span><span class="sxs-lookup"><span data-stu-id="330a2-457">Single</span></span>                 | <span data-ttu-id="330a2-458">Ett</span><span class="sxs-lookup"><span data-stu-id="330a2-458">Single</span></span>               |
| <span data-ttu-id="330a2-459">Änka/Änkeman</span><span class="sxs-lookup"><span data-stu-id="330a2-459">Widowed</span></span>                | <span data-ttu-id="330a2-460">Änka/Änkeman</span><span class="sxs-lookup"><span data-stu-id="330a2-460">Widowed</span></span>              |
| <span data-ttu-id="330a2-461">Skild</span><span class="sxs-lookup"><span data-stu-id="330a2-461">Divorced</span></span>               | <span data-ttu-id="330a2-462">Frånskild</span><span class="sxs-lookup"><span data-stu-id="330a2-462">Divorced</span></span>             |
| <span data-ttu-id="330a2-463">Registrerat partnerskap</span><span class="sxs-lookup"><span data-stu-id="330a2-463">Registered Partnership</span></span> | <span data-ttu-id="330a2-464">Samboförhållande</span><span class="sxs-lookup"><span data-stu-id="330a2-464">Domestic Partnership</span></span> |
| <span data-ttu-id="330a2-465">Inga</span><span class="sxs-lookup"><span data-stu-id="330a2-465">None</span></span>                   | <span data-ttu-id="330a2-466">Inga</span><span class="sxs-lookup"><span data-stu-id="330a2-466">None</span></span>                 |
| <span data-ttu-id="330a2-467">Sambo</span><span class="sxs-lookup"><span data-stu-id="330a2-467">Cohabiting</span></span>             | <span data-ttu-id="330a2-468">Sambo</span><span class="sxs-lookup"><span data-stu-id="330a2-468">Cohabiting</span></span>           |

### <a name="gender"></a><span data-ttu-id="330a2-469">Kön</span><span class="sxs-lookup"><span data-stu-id="330a2-469">Gender</span></span>

<span data-ttu-id="330a2-470">Könsbeteckningar mappas till Dayforce och översätts på lämpligt sätt till giltiga värden i samband med integrering.</span><span class="sxs-lookup"><span data-stu-id="330a2-470">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="330a2-471">Följande tabell visar hur könsbeteckningar mappas till Dayforce.</span><span class="sxs-lookup"><span data-stu-id="330a2-471">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="330a2-472">Personal</span><span class="sxs-lookup"><span data-stu-id="330a2-472">Human Resources</span></span>       | <span data-ttu-id="330a2-473">Dayforce</span><span class="sxs-lookup"><span data-stu-id="330a2-473">Dayforce</span></span>        |
|--------------|-----------------|
| <span data-ttu-id="330a2-474">Man</span><span class="sxs-lookup"><span data-stu-id="330a2-474">Male</span></span>         | <span data-ttu-id="330a2-475">Man</span><span class="sxs-lookup"><span data-stu-id="330a2-475">Male</span></span>            |
| <span data-ttu-id="330a2-476">Kvinna</span><span class="sxs-lookup"><span data-stu-id="330a2-476">Female</span></span>       | <span data-ttu-id="330a2-477">Kvinna</span><span class="sxs-lookup"><span data-stu-id="330a2-477">Female</span></span>          |
| <span data-ttu-id="330a2-478">Icke-specifik</span><span class="sxs-lookup"><span data-stu-id="330a2-478">Non-specific</span></span> | <span data-ttu-id="330a2-479">*Stöds ej*</span><span class="sxs-lookup"><span data-stu-id="330a2-479">*Not supported*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="330a2-480">Inkomstkoder</span><span class="sxs-lookup"><span data-stu-id="330a2-480">Earning codes</span></span>

<span data-ttu-id="330a2-481">Inkomstkoder identifierar individuellt alla typer av arbetstagarintäkter.</span><span class="sxs-lookup"><span data-stu-id="330a2-481">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="330a2-482">Koderna omfattar flera olika parametrar som rör inkomster, till exempel redovisningsbestämmelser, skattelagar, rapporteringskrav och gross up-kapacitet.</span><span class="sxs-lookup"><span data-stu-id="330a2-482">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="330a2-483">Om en frekvens som inte stöds används tillämpas frekvensen **Varje lön** som standard för beräkningen.</span><span class="sxs-lookup"><span data-stu-id="330a2-483">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="330a2-484">Frekvenser som stöds</span><span class="sxs-lookup"><span data-stu-id="330a2-484">Supported frequencies</span></span>

- <span data-ttu-id="330a2-485">Allt</span><span class="sxs-lookup"><span data-stu-id="330a2-485">All</span></span>
- <span data-ttu-id="330a2-486">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="330a2-486">EVERYPAY</span></span>
- <span data-ttu-id="330a2-487">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="330a2-487">EACHPAYPERIOD</span></span>
- <span data-ttu-id="330a2-488">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="330a2-488">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="330a2-489">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="330a2-489">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="330a2-490">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="330a2-490">1OFMTH</span></span>
- <span data-ttu-id="330a2-491">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="330a2-491">LASTOFMTH</span></span>
- <span data-ttu-id="330a2-492">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="330a2-492">2OFMTH</span></span>
- <span data-ttu-id="330a2-493">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="330a2-493">3OFMTH</span></span>
- <span data-ttu-id="330a2-494">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="330a2-494">4OFMTH</span></span>
- <span data-ttu-id="330a2-495">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="330a2-495">5OFMTH</span></span>
- <span data-ttu-id="330a2-496">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="330a2-496">1N2OFMTH</span></span>
- <span data-ttu-id="330a2-497">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="330a2-497">3N4OFMTH</span></span>
- <span data-ttu-id="330a2-498">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="330a2-498">1N3OFMTH</span></span>
- <span data-ttu-id="330a2-499">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="330a2-499">1N4OFMTH</span></span>
- <span data-ttu-id="330a2-500">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="330a2-500">2N3OFMTH</span></span>
- <span data-ttu-id="330a2-501">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="330a2-501">2N4OFMTH</span></span>
- <span data-ttu-id="330a2-502">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="330a2-502">1N2N3OFMTH</span></span>
- <span data-ttu-id="330a2-503">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="330a2-503">1N2N4OFMTH</span></span>
- <span data-ttu-id="330a2-504">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="330a2-504">1N3N4OFMTH</span></span>
- <span data-ttu-id="330a2-505">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="330a2-505">2N3N4OFMTH</span></span>
- <span data-ttu-id="330a2-506">1N2N3N4OFMTH – 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="330a2-506">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="330a2-507">2N3N4N5OFMth – 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="330a2-507">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="330a2-508">1OFQTR – 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="330a2-508">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="330a2-509">LASTOFQTR – LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="330a2-509">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="330a2-510">LASTMTHOFQTR – LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="330a2-510">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="330a2-511">1OFYEAR – 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="330a2-511">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="330a2-512">LASTOFYEAR – LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="330a2-512">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="330a2-513">NOVNDECOFYEAR – NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="330a2-513">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="330a2-514">Adresser</span><span class="sxs-lookup"><span data-stu-id="330a2-514">Addresses</span></span>

<span data-ttu-id="330a2-515">Identifiering av specifika lands-/region-, delstats- och region(kommun)-koder kräver särskilda format som Dayforce och leverantörer i respektive land/region kan känna igen.</span><span class="sxs-lookup"><span data-stu-id="330a2-515">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="330a2-516">Även om formatet för städer är flexibelt måste varje stad associeras med en delstat.</span><span class="sxs-lookup"><span data-stu-id="330a2-516">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="330a2-517">Personal</span><span class="sxs-lookup"><span data-stu-id="330a2-517">Human Resources</span></span>          | <span data-ttu-id="330a2-518">Dayforce</span><span class="sxs-lookup"><span data-stu-id="330a2-518">Dayforce</span></span>              |
|-----------------|-----------------------|
| <span data-ttu-id="330a2-519">Land/region</span><span class="sxs-lookup"><span data-stu-id="330a2-519">Country/Region</span></span>  | <span data-ttu-id="330a2-520">Landskod</span><span class="sxs-lookup"><span data-stu-id="330a2-520">Country Code</span></span>          |
| <span data-ttu-id="330a2-521">Postnummer</span><span class="sxs-lookup"><span data-stu-id="330a2-521">Zip/Postal Code</span></span> | <span data-ttu-id="330a2-522">Postnummer</span><span class="sxs-lookup"><span data-stu-id="330a2-522">Postal Code</span></span>           |
| <span data-ttu-id="330a2-523">Stat</span><span class="sxs-lookup"><span data-stu-id="330a2-523">State</span></span>           | <span data-ttu-id="330a2-524">Delstatskod</span><span class="sxs-lookup"><span data-stu-id="330a2-524">State Code</span></span>            |
| <span data-ttu-id="330a2-525">Ort</span><span class="sxs-lookup"><span data-stu-id="330a2-525">City</span></span>            | <span data-ttu-id="330a2-526">Ort</span><span class="sxs-lookup"><span data-stu-id="330a2-526">City</span></span>                  |
| <span data-ttu-id="330a2-527">Län</span><span class="sxs-lookup"><span data-stu-id="330a2-527">County</span></span>          | <span data-ttu-id="330a2-528">Region (kommun)</span><span class="sxs-lookup"><span data-stu-id="330a2-528">County (Municipality)</span></span> |
| <span data-ttu-id="330a2-529">Gata</span><span class="sxs-lookup"><span data-stu-id="330a2-529">Street</span></span>          | <span data-ttu-id="330a2-530">Adressrad 1</span><span class="sxs-lookup"><span data-stu-id="330a2-530">Address Line 1</span></span>        |

### <a name="tax-regions"></a><span data-ttu-id="330a2-531">Skatteregioner</span><span class="sxs-lookup"><span data-stu-id="330a2-531">Tax regions</span></span>

<span data-ttu-id="330a2-532">Skatteregioner används för att bestämma vilken skattesats som ska användas vid lönegenerering.</span><span class="sxs-lookup"><span data-stu-id="330a2-532">Tax regions are used to determine the appropriate tax that should be applied during payroll generation.</span></span> <span data-ttu-id="330a2-533">Skatteregioner mappas till Dayforce som platsadresser.</span><span class="sxs-lookup"><span data-stu-id="330a2-533">Tax regions are mapped to Dayforce as location addresses.</span></span> <span data-ttu-id="330a2-534">Förvald skatteregion måste associeras med medarbetarens aktiva befattning.</span><span class="sxs-lookup"><span data-stu-id="330a2-534">The default tax region must be associated with the worker's active position.</span></span> 

- <span data-ttu-id="330a2-535">Skatteregion (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="330a2-535">Tax region (required)</span></span>
- <span data-ttu-id="330a2-536">Land/region (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="330a2-536">Country/Region (required)</span></span>
- <span data-ttu-id="330a2-537">Delstat (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="330a2-537">State (required)</span></span>
- <span data-ttu-id="330a2-538">Län</span><span class="sxs-lookup"><span data-stu-id="330a2-538">County</span></span> 
- <span data-ttu-id="330a2-539">Stad (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="330a2-539">City (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-mexico"></a><span data-ttu-id="330a2-540">Konfigurera dina data för att generera lön i Mexiko</span><span class="sxs-lookup"><span data-stu-id="330a2-540">Configure your data to generate payroll in Mexico</span></span>

<span data-ttu-id="330a2-541">Om du genererar lön för medarbetare i Mexiko måste följande element konfigureras:</span><span class="sxs-lookup"><span data-stu-id="330a2-541">If you're generating pay for employees in Mexico, the following elements must be configured:</span></span>

- <span data-ttu-id="330a2-542">Avdelningar är obligatoriska vid befattningarna:</span><span class="sxs-lookup"><span data-stu-id="330a2-542">Departments are required on positions.</span></span>
- <span data-ttu-id="330a2-543">Kostnadsställen måste ställas in som ekonomiska dimensioner och måste vara det första elementet i standardsträngen för ekonomisk dimension.</span><span class="sxs-lookup"><span data-stu-id="330a2-543">Cost centers must be set as financial dimensions and must be the first element in the Default Financial Dimension string.</span></span>

### <a name="job-types"></a><span data-ttu-id="330a2-544">Jobbtyper</span><span class="sxs-lookup"><span data-stu-id="330a2-544">Job types</span></span>

<span data-ttu-id="330a2-545">Jobbtyper används för att gruppera liknande jobb i kategorier.</span><span class="sxs-lookup"><span data-stu-id="330a2-545">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="330a2-546">Jobbtyper krävs för att bearbeta löner i Mexiko.</span><span class="sxs-lookup"><span data-stu-id="330a2-546">Job types are required in order to process payroll in Mexico.</span></span> <span data-ttu-id="330a2-547">Några exempel på jobbtyper är heltid och deltid, eller fast lön och timpenning.</span><span class="sxs-lookup"><span data-stu-id="330a2-547">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="330a2-548">Jobbtyper mappas till Dayforce som lönetyper som anger huruvida en anställd arbetar per timme eller har fast lön.</span><span class="sxs-lookup"><span data-stu-id="330a2-548">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="330a2-549">Följande jobbtyper och beskrivningar krävs.</span><span class="sxs-lookup"><span data-stu-id="330a2-549">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="330a2-550">Jobbtyp</span><span class="sxs-lookup"><span data-stu-id="330a2-550">Job type</span></span>   | <span data-ttu-id="330a2-551">beskrivning</span><span class="sxs-lookup"><span data-stu-id="330a2-551">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="330a2-552">Varje timme</span><span class="sxs-lookup"><span data-stu-id="330a2-552">Hourly</span></span>     | <span data-ttu-id="330a2-553">MX Varje timme</span><span class="sxs-lookup"><span data-stu-id="330a2-553">MX Hourly</span></span>   |
| <span data-ttu-id="330a2-554">Fast lön</span><span class="sxs-lookup"><span data-stu-id="330a2-554">Salaried</span></span>   | <span data-ttu-id="330a2-555">MX Fast lön</span><span class="sxs-lookup"><span data-stu-id="330a2-555">MX Salaried</span></span> |

### <a name="position-types"></a><span data-ttu-id="330a2-556">Befattningstyper</span><span class="sxs-lookup"><span data-stu-id="330a2-556">Position types</span></span> 

<span data-ttu-id="330a2-557">Du kan använda befattningstyper för att beskriva huruvida befattningen är på heltid, deltid eller annat.</span><span class="sxs-lookup"><span data-stu-id="330a2-557">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="330a2-558">Befattningstyper mappas till Dayforce som löneklasser som anger huruvida en anställd arbetar heltid eller deltid.</span><span class="sxs-lookup"><span data-stu-id="330a2-558">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="330a2-559">Följande befattningstyper och beskrivningar krävs.</span><span class="sxs-lookup"><span data-stu-id="330a2-559">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="330a2-560">Befattningstyp</span><span class="sxs-lookup"><span data-stu-id="330a2-560">Position type</span></span>   | <span data-ttu-id="330a2-561">beskrivning</span><span class="sxs-lookup"><span data-stu-id="330a2-561">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="330a2-562">Heltid</span><span class="sxs-lookup"><span data-stu-id="330a2-562">Full-time</span></span>       | <span data-ttu-id="330a2-563">Heltidsanställd</span><span class="sxs-lookup"><span data-stu-id="330a2-563">Full time employee</span></span> |
| <span data-ttu-id="330a2-564">Deltid</span><span class="sxs-lookup"><span data-stu-id="330a2-564">Part-time</span></span>       | <span data-ttu-id="330a2-565">Deltidsanställd</span><span class="sxs-lookup"><span data-stu-id="330a2-565">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="330a2-566">Orsakskoder</span><span class="sxs-lookup"><span data-stu-id="330a2-566">Reason codes</span></span>

<span data-ttu-id="330a2-567">Orsakskoder innehåller information om statusen för en medarbetare.</span><span class="sxs-lookup"><span data-stu-id="330a2-567">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="330a2-568">Orsakskoder mappas till Dayforce som statusanledningar som anger orsaken till ändringar i en medarbetares befattning eller anställningsstatus.</span><span class="sxs-lookup"><span data-stu-id="330a2-568">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="330a2-569">Följande orsakskoder och -beskrivningar krävs.</span><span class="sxs-lookup"><span data-stu-id="330a2-569">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="330a2-570">Orsakskod</span><span class="sxs-lookup"><span data-stu-id="330a2-570">Reason code</span></span>            | <span data-ttu-id="330a2-571">beskrivning</span><span class="sxs-lookup"><span data-stu-id="330a2-571">Description</span></span>                    | <span data-ttu-id="330a2-572">Tillämpliga scenarier</span><span class="sxs-lookup"><span data-stu-id="330a2-572">Applicable scenarios</span></span> |
|------------------------|--------------------------------|----------------------|
| <span data-ttu-id="330a2-573">DEPARTUREBEFOREPAYMENT</span><span class="sxs-lookup"><span data-stu-id="330a2-573">DEPARTUREBEFOREPAYMENT</span></span> | <span data-ttu-id="330a2-574">Avgick före första lön</span><span class="sxs-lookup"><span data-stu-id="330a2-574">Departure before first payroll</span></span> | <span data-ttu-id="330a2-575">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="330a2-575">Terminate worker</span></span>     |
| <span data-ttu-id="330a2-576">EGEN UPPSÄGNING</span><span class="sxs-lookup"><span data-stu-id="330a2-576">RESIGNATION</span></span>            | <span data-ttu-id="330a2-577">Egen uppsägning</span><span class="sxs-lookup"><span data-stu-id="330a2-577">Resignation</span></span>                    | <span data-ttu-id="330a2-578">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="330a2-578">Terminate worker</span></span>     |
| <span data-ttu-id="330a2-579">PENSION</span><span class="sxs-lookup"><span data-stu-id="330a2-579">PENSION</span></span>                | <span data-ttu-id="330a2-580">Pension</span><span class="sxs-lookup"><span data-stu-id="330a2-580">Pension</span></span>                        | <span data-ttu-id="330a2-581">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="330a2-581">Terminate worker</span></span>     |
| <span data-ttu-id="330a2-582">UPPSÄGNING</span><span class="sxs-lookup"><span data-stu-id="330a2-582">TERMINATION</span></span>            | <span data-ttu-id="330a2-583">Uppsägning</span><span class="sxs-lookup"><span data-stu-id="330a2-583">Termination</span></span>                    | <span data-ttu-id="330a2-584">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="330a2-584">Terminate worker</span></span>     |
| <span data-ttu-id="330a2-585">PENSION</span><span class="sxs-lookup"><span data-stu-id="330a2-585">RETIREMENT</span></span>             | <span data-ttu-id="330a2-586">Pension</span><span class="sxs-lookup"><span data-stu-id="330a2-586">Retirement</span></span>                     | <span data-ttu-id="330a2-587">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="330a2-587">Terminate worker</span></span>     |
| <span data-ttu-id="330a2-588">FRÅNVARANDE</span><span class="sxs-lookup"><span data-stu-id="330a2-588">ABSENTEE</span></span>               | <span data-ttu-id="330a2-589">Frånvarande</span><span class="sxs-lookup"><span data-stu-id="330a2-589">Absentee</span></span>                       | <span data-ttu-id="330a2-590">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="330a2-590">Terminate worker</span></span>     |
| <span data-ttu-id="330a2-591">ÖVRIGT</span><span class="sxs-lookup"><span data-stu-id="330a2-591">OTHER</span></span>                  | <span data-ttu-id="330a2-592">Andra orsaker</span><span class="sxs-lookup"><span data-stu-id="330a2-592">Other Reasons</span></span>                  | <span data-ttu-id="330a2-593">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="330a2-593">Terminate worker</span></span>     |
| <span data-ttu-id="330a2-594">AVSLUT</span><span class="sxs-lookup"><span data-stu-id="330a2-594">CLOSURE</span></span>                | <span data-ttu-id="330a2-595">Verksamheten nedlagd</span><span class="sxs-lookup"><span data-stu-id="330a2-595">Business Closure</span></span>               | <span data-ttu-id="330a2-596">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="330a2-596">Terminate worker</span></span>     |
| <span data-ttu-id="330a2-597">DÖDSFALL</span><span class="sxs-lookup"><span data-stu-id="330a2-597">DEATH</span></span>                  | <span data-ttu-id="330a2-598">Dödsfall</span><span class="sxs-lookup"><span data-stu-id="330a2-598">Death</span></span>                          | <span data-ttu-id="330a2-599">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="330a2-599">Terminate worker</span></span>     |
| <span data-ttu-id="330a2-600">TJÄNSTLEDIGHET</span><span class="sxs-lookup"><span data-stu-id="330a2-600">LEAVEOFABSENCE</span></span>         | <span data-ttu-id="330a2-601">Tjänstledighet</span><span class="sxs-lookup"><span data-stu-id="330a2-601">Leave of Absence</span></span>               | <span data-ttu-id="330a2-602">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="330a2-602">Terminate worker</span></span>     |
| <span data-ttu-id="330a2-603">KONTRAKTSLUT</span><span class="sxs-lookup"><span data-stu-id="330a2-603">CONTRACTEND</span></span>            | <span data-ttu-id="330a2-604">Kontraktslut</span><span class="sxs-lookup"><span data-stu-id="330a2-604">End of Contract</span></span>                | <span data-ttu-id="330a2-605">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="330a2-605">Terminate worker</span></span>     |
| <span data-ttu-id="330a2-606">LÖNEÄNDRING</span><span class="sxs-lookup"><span data-stu-id="330a2-606">SALARYCHANGE</span></span>           | <span data-ttu-id="330a2-607">Löneändring</span><span class="sxs-lookup"><span data-stu-id="330a2-607">Change of Salary</span></span>               | <span data-ttu-id="330a2-608">Kompensation</span><span class="sxs-lookup"><span data-stu-id="330a2-608">Compensation</span></span>         |

### <a name="terms-of-employment"></a><span data-ttu-id="330a2-609">Anställningsvillkor</span><span class="sxs-lookup"><span data-stu-id="330a2-609">Terms of employment</span></span>

<span data-ttu-id="330a2-610">Anställningsvillkor används för att skapa kategorier av anställningsvillkor.</span><span class="sxs-lookup"><span data-stu-id="330a2-610">Terms of employment are used to create categories of employment terms.</span></span> <span data-ttu-id="330a2-611">Villkoren mappas till Dayforce som indikatorvärden för anställning.</span><span class="sxs-lookup"><span data-stu-id="330a2-611">The terms are mapped to Dayforce as employment indicator values.</span></span>

<span data-ttu-id="330a2-612">Följande anställningsvillkor samt beskrivningar krävs.</span><span class="sxs-lookup"><span data-stu-id="330a2-612">The following terms of employment and descriptions are required.</span></span>

| <span data-ttu-id="330a2-613">Anställningsvillkor</span><span class="sxs-lookup"><span data-stu-id="330a2-613">Terms of employment</span></span>   | <span data-ttu-id="330a2-614">beskrivning</span><span class="sxs-lookup"><span data-stu-id="330a2-614">Description</span></span> |
|-----------------------|-------------|
| <span data-ttu-id="330a2-615">Vanligt</span><span class="sxs-lookup"><span data-stu-id="330a2-615">Regular</span></span>               | <span data-ttu-id="330a2-616">Vanligt</span><span class="sxs-lookup"><span data-stu-id="330a2-616">Regular</span></span>     |
| <span data-ttu-id="330a2-617">Direkt</span><span class="sxs-lookup"><span data-stu-id="330a2-617">Direct</span></span>                | <span data-ttu-id="330a2-618">Direkt</span><span class="sxs-lookup"><span data-stu-id="330a2-618">Direct</span></span>      |
| <span data-ttu-id="330a2-619">Praktik</span><span class="sxs-lookup"><span data-stu-id="330a2-619">Internship</span></span>            | <span data-ttu-id="330a2-620">Praktik</span><span class="sxs-lookup"><span data-stu-id="330a2-620">Internship</span></span>  |
| <span data-ttu-id="330a2-621">Permanent</span><span class="sxs-lookup"><span data-stu-id="330a2-621">Permanent</span></span>             | <span data-ttu-id="330a2-622">Permanent</span><span class="sxs-lookup"><span data-stu-id="330a2-622">Permanent</span></span>   |

### <a name="marital-status"></a><span data-ttu-id="330a2-623">Civilstånd</span><span class="sxs-lookup"><span data-stu-id="330a2-623">Marital status</span></span>

<span data-ttu-id="330a2-624">Civilståndsvärden mappas till Dayforce och översätts på lämpligt sätt till giltiga värden i samband med integrering.</span><span class="sxs-lookup"><span data-stu-id="330a2-624">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="330a2-625">Följande tabell visar hur civilståndsvärden mappas till Dayforce.</span><span class="sxs-lookup"><span data-stu-id="330a2-625">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="330a2-626">Personal</span><span class="sxs-lookup"><span data-stu-id="330a2-626">Human Resources</span></span>                 | <span data-ttu-id="330a2-627">Dayforce</span><span class="sxs-lookup"><span data-stu-id="330a2-627">Dayforce</span></span>                  |
|------------------------|---------------------------|
| <span data-ttu-id="330a2-628">Gift</span><span class="sxs-lookup"><span data-stu-id="330a2-628">Married</span></span>                | <span data-ttu-id="330a2-629">Gift</span><span class="sxs-lookup"><span data-stu-id="330a2-629">Married</span></span>                   |
| <span data-ttu-id="330a2-630">Ett</span><span class="sxs-lookup"><span data-stu-id="330a2-630">Single</span></span>                 | <span data-ttu-id="330a2-631">Ett</span><span class="sxs-lookup"><span data-stu-id="330a2-631">Single</span></span>                    |
| <span data-ttu-id="330a2-632">Änka/Änkeman</span><span class="sxs-lookup"><span data-stu-id="330a2-632">Widowed</span></span>                | <span data-ttu-id="330a2-633">Änka/Änkeman</span><span class="sxs-lookup"><span data-stu-id="330a2-633">Widowed</span></span>                   |
| <span data-ttu-id="330a2-634">Skild</span><span class="sxs-lookup"><span data-stu-id="330a2-634">Divorced</span></span>               | <span data-ttu-id="330a2-635">Frånskild</span><span class="sxs-lookup"><span data-stu-id="330a2-635">Divorced</span></span>                  |
| <span data-ttu-id="330a2-636">Registrerat partnerskap</span><span class="sxs-lookup"><span data-stu-id="330a2-636">Registered Partnership</span></span> | <span data-ttu-id="330a2-637">Samboförhållande</span><span class="sxs-lookup"><span data-stu-id="330a2-637">Domestic Partnership</span></span>      |
| <span data-ttu-id="330a2-638">Inga</span><span class="sxs-lookup"><span data-stu-id="330a2-638">None</span></span>                   | <span data-ttu-id="330a2-639">*Stöds inte i Mexiko*</span><span class="sxs-lookup"><span data-stu-id="330a2-639">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="330a2-640">Sambo</span><span class="sxs-lookup"><span data-stu-id="330a2-640">Cohabiting</span></span>             | <span data-ttu-id="330a2-641">*Stöds inte i Mexiko*</span><span class="sxs-lookup"><span data-stu-id="330a2-641">*Not supported by Mexico*</span></span> |

### <a name="gender"></a><span data-ttu-id="330a2-642">Kön</span><span class="sxs-lookup"><span data-stu-id="330a2-642">Gender</span></span>

<span data-ttu-id="330a2-643">Könsbeteckningar mappas till Dayforce och översätts på lämpligt sätt till giltiga värden i samband med integrering.</span><span class="sxs-lookup"><span data-stu-id="330a2-643">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="330a2-644">Följande tabell visar hur könsbeteckningar mappas till Dayforce.</span><span class="sxs-lookup"><span data-stu-id="330a2-644">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="330a2-645">Personal</span><span class="sxs-lookup"><span data-stu-id="330a2-645">Human Resources</span></span>       | <span data-ttu-id="330a2-646">Dayforce</span><span class="sxs-lookup"><span data-stu-id="330a2-646">Dayforce</span></span>                  |
|--------------|---------------------------|
| <span data-ttu-id="330a2-647">Man</span><span class="sxs-lookup"><span data-stu-id="330a2-647">Male</span></span>         | <span data-ttu-id="330a2-648">Man</span><span class="sxs-lookup"><span data-stu-id="330a2-648">Male</span></span>                      |
| <span data-ttu-id="330a2-649">Kvinna</span><span class="sxs-lookup"><span data-stu-id="330a2-649">Female</span></span>       | <span data-ttu-id="330a2-650">Kvinna</span><span class="sxs-lookup"><span data-stu-id="330a2-650">Female</span></span>                    |
| <span data-ttu-id="330a2-651">Icke-specifik</span><span class="sxs-lookup"><span data-stu-id="330a2-651">Non-specific</span></span> | <span data-ttu-id="330a2-652">*Stöds inte i Mexiko*</span><span class="sxs-lookup"><span data-stu-id="330a2-652">*Not supported by Mexico*</span></span> |

### <a name="payment-method"></a><span data-ttu-id="330a2-653">Betalningsmetod</span><span class="sxs-lookup"><span data-stu-id="330a2-653">Payment method</span></span>

<span data-ttu-id="330a2-654">Betalsätt ger medarbetare och företag ett sätt att beskriva hur medarbetaren ska betalas.</span><span class="sxs-lookup"><span data-stu-id="330a2-654">Payment methods give the employee and the company a way to describe how employees will be paid.</span></span> <span data-ttu-id="330a2-655">Betalsätt mappas till Dayforce och översätts på lämpligt sätt till giltiga värden i samband med integrering.</span><span class="sxs-lookup"><span data-stu-id="330a2-655">Payment methods are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="330a2-656">Följande tabell visar hur betalsätt mappas till Dayforce.</span><span class="sxs-lookup"><span data-stu-id="330a2-656">The following table shows how payment methods are mapped to Dayforce.</span></span>

| <span data-ttu-id="330a2-657">Personal</span><span class="sxs-lookup"><span data-stu-id="330a2-657">Human Resources</span></span>             | <span data-ttu-id="330a2-658">Dayforce</span><span class="sxs-lookup"><span data-stu-id="330a2-658">Dayforce</span></span>                  |
|--------------------|---------------------------|
| <span data-ttu-id="330a2-659">Kontant</span><span class="sxs-lookup"><span data-stu-id="330a2-659">Cash</span></span>               | <span data-ttu-id="330a2-660">Kontant</span><span class="sxs-lookup"><span data-stu-id="330a2-660">Cash</span></span>                      |
| <span data-ttu-id="330a2-661">Elektronisk betalning</span><span class="sxs-lookup"><span data-stu-id="330a2-661">Electronic Payment</span></span> | <span data-ttu-id="330a2-662">Överför</span><span class="sxs-lookup"><span data-stu-id="330a2-662">Transfer</span></span>                  |
| <span data-ttu-id="330a2-663">Check</span><span class="sxs-lookup"><span data-stu-id="330a2-663">Check</span></span>              | <span data-ttu-id="330a2-664">Check</span><span class="sxs-lookup"><span data-stu-id="330a2-664">Cheque</span></span>                    |
| <span data-ttu-id="330a2-665">Bankutdrag</span><span class="sxs-lookup"><span data-stu-id="330a2-665">Bank Draft</span></span>         | <span data-ttu-id="330a2-666">*Stöds inte i Mexiko*</span><span class="sxs-lookup"><span data-stu-id="330a2-666">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="330a2-667">Annat</span><span class="sxs-lookup"><span data-stu-id="330a2-667">Other</span></span>              | <span data-ttu-id="330a2-668">*Stöds inte i Mexiko*</span><span class="sxs-lookup"><span data-stu-id="330a2-668">*Not supported by Mexico*</span></span> |

### <a name="bank-account-type"></a><span data-ttu-id="330a2-669">Bankkontotyp</span><span class="sxs-lookup"><span data-stu-id="330a2-669">Bank account type</span></span>

<span data-ttu-id="330a2-670">Bankkontotyper används för elektroniska betalningar till medarbetare.</span><span class="sxs-lookup"><span data-stu-id="330a2-670">Bank account types are used for electronic payments to employees.</span></span> <span data-ttu-id="330a2-671">Bankkontotyper mappas till Dayforce som kontoinformation för överföringar.</span><span class="sxs-lookup"><span data-stu-id="330a2-671">Bank account types are mapped to Dayforce as transfer account information.</span></span> <span data-ttu-id="330a2-672">Bankkontotyper översätts på lämpligt till giltiga värden i samband med integrering.</span><span class="sxs-lookup"><span data-stu-id="330a2-672">The bank account types are translated, as appropriate, to the accepted values upon integration.</span></span>

| <span data-ttu-id="330a2-673">Personal</span><span class="sxs-lookup"><span data-stu-id="330a2-673">Human Resources</span></span>            | <span data-ttu-id="330a2-674">Dayforce</span><span class="sxs-lookup"><span data-stu-id="330a2-674">Dayforce</span></span>                  |
|-------------------|---------------------------|
| <span data-ttu-id="330a2-675">Checkkonto</span><span class="sxs-lookup"><span data-stu-id="330a2-675">Checking Account</span></span>  | <span data-ttu-id="330a2-676">Checkkonto</span><span class="sxs-lookup"><span data-stu-id="330a2-676">CheckingAccount</span></span>           |
| <span data-ttu-id="330a2-677">Lönekonto</span><span class="sxs-lookup"><span data-stu-id="330a2-677">Payroll Account</span></span>   | <span data-ttu-id="330a2-678">Lönekonto</span><span class="sxs-lookup"><span data-stu-id="330a2-678">PayrollAccount</span></span>            |
| <span data-ttu-id="330a2-679">Sparkonto</span><span class="sxs-lookup"><span data-stu-id="330a2-679">Savings Account</span></span>   | <span data-ttu-id="330a2-680">*Stöds inte i Mexiko*</span><span class="sxs-lookup"><span data-stu-id="330a2-680">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="330a2-681">BankGirot-konto</span><span class="sxs-lookup"><span data-stu-id="330a2-681">BankGirot account</span></span> | <span data-ttu-id="330a2-682">*Stöds inte i Mexiko*</span><span class="sxs-lookup"><span data-stu-id="330a2-682">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="330a2-683">PlusGirot-konto</span><span class="sxs-lookup"><span data-stu-id="330a2-683">PlusGirot account</span></span> | <span data-ttu-id="330a2-684">*Stöds inte i Mexiko*</span><span class="sxs-lookup"><span data-stu-id="330a2-684">*Not supported by Mexico*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="330a2-685">Inkomstkoder</span><span class="sxs-lookup"><span data-stu-id="330a2-685">Earning codes</span></span>

<span data-ttu-id="330a2-686">Inkomstkoder identifierar individuellt alla typer av arbetstagarintäkter.</span><span class="sxs-lookup"><span data-stu-id="330a2-686">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="330a2-687">Koderna omfattar flera olika parametrar som rör inkomster, till exempel redovisningsbestämmelser, skattelagar, rapporteringskrav och gross up-kapacitet.</span><span class="sxs-lookup"><span data-stu-id="330a2-687">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="330a2-688">Om en frekvens som inte stöds används tillämpas frekvensen **Varje lön** som standard för beräkningen.</span><span class="sxs-lookup"><span data-stu-id="330a2-688">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="330a2-689">Frekvenser som stöds</span><span class="sxs-lookup"><span data-stu-id="330a2-689">Supported frequencies</span></span>

- <span data-ttu-id="330a2-690">Allt</span><span class="sxs-lookup"><span data-stu-id="330a2-690">All</span></span>
- <span data-ttu-id="330a2-691">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="330a2-691">EVERYPAY</span></span>
- <span data-ttu-id="330a2-692">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="330a2-692">EACHPAYPERIOD</span></span>
- <span data-ttu-id="330a2-693">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="330a2-693">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="330a2-694">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="330a2-694">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="330a2-695">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="330a2-695">1OFMTH</span></span>
- <span data-ttu-id="330a2-696">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="330a2-696">LASTOFMTH</span></span>
- <span data-ttu-id="330a2-697">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="330a2-697">2OFMTH</span></span>
- <span data-ttu-id="330a2-698">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="330a2-698">3OFMTH</span></span>
- <span data-ttu-id="330a2-699">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="330a2-699">4OFMTH</span></span>
- <span data-ttu-id="330a2-700">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="330a2-700">5OFMTH</span></span>
- <span data-ttu-id="330a2-701">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="330a2-701">1N2OFMTH</span></span>
- <span data-ttu-id="330a2-702">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="330a2-702">3N4OFMTH</span></span>
- <span data-ttu-id="330a2-703">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="330a2-703">1N3OFMTH</span></span>
- <span data-ttu-id="330a2-704">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="330a2-704">1N4OFMTH</span></span>
- <span data-ttu-id="330a2-705">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="330a2-705">2N3OFMTH</span></span>
- <span data-ttu-id="330a2-706">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="330a2-706">2N4OFMTH</span></span>
- <span data-ttu-id="330a2-707">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="330a2-707">1N2N3OFMTH</span></span>
- <span data-ttu-id="330a2-708">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="330a2-708">1N2N4OFMTH</span></span>
- <span data-ttu-id="330a2-709">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="330a2-709">1N3N4OFMTH</span></span>
- <span data-ttu-id="330a2-710">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="330a2-710">2N3N4OFMTH</span></span>
- <span data-ttu-id="330a2-711">1N2N3N4OFMTH – 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="330a2-711">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="330a2-712">2N3N4N5OFMth – 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="330a2-712">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="330a2-713">1OFQTR – 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="330a2-713">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="330a2-714">LASTOFQTR – LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="330a2-714">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="330a2-715">LASTMTHOFQTR – LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="330a2-715">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="330a2-716">1OFYEAR – 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="330a2-716">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="330a2-717">LASTOFYEAR – LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="330a2-717">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="330a2-718">NOVNDECOFYEAR – NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="330a2-718">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="330a2-719">Adresser</span><span class="sxs-lookup"><span data-stu-id="330a2-719">Addresses</span></span>

<span data-ttu-id="330a2-720">Identifiering av specifika lands-/region-, delstats- och region(kommun)-koder kräver särskilda format som Dayforce och leverantörer i respektive land/region kan känna igen.</span><span class="sxs-lookup"><span data-stu-id="330a2-720">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="330a2-721">Även om formatet för städer är flexibelt måste varje stad associeras med en delstat.</span><span class="sxs-lookup"><span data-stu-id="330a2-721">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="330a2-722">Personal</span><span class="sxs-lookup"><span data-stu-id="330a2-722">Human Resources</span></span>              | <span data-ttu-id="330a2-723">Dayforce</span><span class="sxs-lookup"><span data-stu-id="330a2-723">Dayforce</span></span>              |
|---------------------|-----------------------|
| <span data-ttu-id="330a2-724">Land/region</span><span class="sxs-lookup"><span data-stu-id="330a2-724">Country/Region</span></span>      | <span data-ttu-id="330a2-725">Landskod</span><span class="sxs-lookup"><span data-stu-id="330a2-725">Country Code</span></span>          |
| <span data-ttu-id="330a2-726">Postnummer</span><span class="sxs-lookup"><span data-stu-id="330a2-726">Zip/Postal Code</span></span>     | <span data-ttu-id="330a2-727">Postnummer</span><span class="sxs-lookup"><span data-stu-id="330a2-727">Postal Code</span></span>           |
| <span data-ttu-id="330a2-728">Stat</span><span class="sxs-lookup"><span data-stu-id="330a2-728">State</span></span>               | <span data-ttu-id="330a2-729">Delstatskod</span><span class="sxs-lookup"><span data-stu-id="330a2-729">State Code</span></span>            |
| <span data-ttu-id="330a2-730">Ort</span><span class="sxs-lookup"><span data-stu-id="330a2-730">City</span></span>                | <span data-ttu-id="330a2-731">Ort</span><span class="sxs-lookup"><span data-stu-id="330a2-731">City</span></span>                  |
| <span data-ttu-id="330a2-732">Län</span><span class="sxs-lookup"><span data-stu-id="330a2-732">County</span></span>              | <span data-ttu-id="330a2-733">Region (kommun)</span><span class="sxs-lookup"><span data-stu-id="330a2-733">County (Municipality)</span></span> |
| <span data-ttu-id="330a2-734">Gata</span><span class="sxs-lookup"><span data-stu-id="330a2-734">Street</span></span>              | <span data-ttu-id="330a2-735">Adressrad 1</span><span class="sxs-lookup"><span data-stu-id="330a2-735">Address Line 1</span></span>        |
| <span data-ttu-id="330a2-736">Gatunummer</span><span class="sxs-lookup"><span data-stu-id="330a2-736">Street Number</span></span>       | <span data-ttu-id="330a2-737">Adressrad 2</span><span class="sxs-lookup"><span data-stu-id="330a2-737">Address Line 2</span></span>        |
| <span data-ttu-id="330a2-738">Byggnadskomplement</span><span class="sxs-lookup"><span data-stu-id="330a2-738">Building Complement</span></span> | <span data-ttu-id="330a2-739">Adressrad 5</span><span class="sxs-lookup"><span data-stu-id="330a2-739">Address Line 5</span></span>        |

### <a name="passport-number"></a><span data-ttu-id="330a2-740">Passnummer</span><span class="sxs-lookup"><span data-stu-id="330a2-740">Passport number</span></span>

<span data-ttu-id="330a2-741">Medarbetare kan deklarera passinformation.</span><span class="sxs-lookup"><span data-stu-id="330a2-741">Employees can declare passport information.</span></span> <span data-ttu-id="330a2-742">Denna information bär ID-typen **Pass** och integreras i Dayforce som en del av medarbetarens Mexikospecifika information.</span><span class="sxs-lookup"><span data-stu-id="330a2-742">This information is of the **Passport** identification type and is integrated into Dayforce as part of an employee's Mexico-specific information.</span></span>

- <span data-ttu-id="330a2-743">Identifieringstyp = "Pass"</span><span class="sxs-lookup"><span data-stu-id="330a2-743">Identification Type = "Passport"</span></span>
- <span data-ttu-id="330a2-744">Utfärdat den</span><span class="sxs-lookup"><span data-stu-id="330a2-744">Issued Date</span></span>
- <span data-ttu-id="330a2-745">Utgångsdatum</span><span class="sxs-lookup"><span data-stu-id="330a2-745">Expiration Date</span></span>

<span data-ttu-id="330a2-746">Medarbetare kan deklarera flera ID-nummer med ID-typen **Pass**.</span><span class="sxs-lookup"><span data-stu-id="330a2-746">Employees can declare multiple identification numbers of the **Passport** identification type.</span></span> <span data-ttu-id="330a2-747">Endast den aktuella passposten integreras emellertid i Dayforce.</span><span class="sxs-lookup"><span data-stu-id="330a2-747">However, only the current active passport entry is integrated into Dayforce.</span></span> <span data-ttu-id="330a2-748">Om alla passposter har upphört att gälla kommer det pass som är utfärdat senast att integreras i Dayforce.</span><span class="sxs-lookup"><span data-stu-id="330a2-748">If all passport entries are expired, the passport that was most recently issued is integrated into Dayforce.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]