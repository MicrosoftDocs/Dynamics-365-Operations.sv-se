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
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 6d150daa92fe79cf6620ce5ddf1a01f369c64053
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/18/2021
ms.locfileid: "6051507"
---
# <a name="configure-integration-with-dayforce"></a><span data-ttu-id="92aaa-104">Konfigurera integration med Dayforce</span><span class="sxs-lookup"><span data-stu-id="92aaa-104">Configure integration with Dayforce</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="92aaa-105">Integreringen mellan Microsoft Dynamics 365 Human Resources och Ceridian Dayforce är beroende av flera konfigurationssteg som beskrivs i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="92aaa-105">The integration between Microsoft Dynamics 365 Human Resources and Ceridian Dayforce relies on several configuration steps that are described in this article.</span></span> <span data-ttu-id="92aaa-106">Du måste konfigurera integrationen i både Personal och Dayforce innan du kan bearbeta en betalning.</span><span class="sxs-lookup"><span data-stu-id="92aaa-106">You must configure the integration in both Human Resources and Dayforce before you can process a pay run.</span></span>

<span data-ttu-id="92aaa-107">När du använder tjänster som exempelvis Dayforce för att utföra betalningar måste du aktivera integration i Personal.</span><span class="sxs-lookup"><span data-stu-id="92aaa-107">When you use a service such as Dayforce to complete pay runs, you must enable the integration in Human Resources.</span></span> <span data-ttu-id="92aaa-108">Integrationen kräver specifika data från Personal.</span><span class="sxs-lookup"><span data-stu-id="92aaa-108">The integration requires specific data from Human Resources.</span></span> <span data-ttu-id="92aaa-109">Därför måste du kontrollera att data som är mappad till Dayforce konfigureras i Personal på ett sätt som stöder integrationen.</span><span class="sxs-lookup"><span data-stu-id="92aaa-109">Therefore, you must verify that data that is mapped to Dayforce is configured in Human Resources in a manner that supports the integration.</span></span> <span data-ttu-id="92aaa-110">Integrationen använder följande breda datakategorier:</span><span class="sxs-lookup"><span data-stu-id="92aaa-110">The integration uses the following broad categories of data:</span></span>

- <span data-ttu-id="92aaa-111">Personaldata</span><span class="sxs-lookup"><span data-stu-id="92aaa-111">Human resources data</span></span>
- <span data-ttu-id="92aaa-112">Kompensationsdata</span><span class="sxs-lookup"><span data-stu-id="92aaa-112">Compensation data</span></span>
- <span data-ttu-id="92aaa-113">Lönedata som till exempel lönecykler, betalningsperioder och inkomstkoder</span><span class="sxs-lookup"><span data-stu-id="92aaa-113">Payroll data, such as pay cycles, pay periods, and earning codes</span></span>
- <span data-ttu-id="92aaa-114">Medarbetardata</span><span class="sxs-lookup"><span data-stu-id="92aaa-114">Worker data</span></span>

<span data-ttu-id="92aaa-115">Det här avsnittet beskriver de steg som du måste följa för att aktivera integrationen.</span><span class="sxs-lookup"><span data-stu-id="92aaa-115">This article describes the steps that you must follow to enable the integration.</span></span> <span data-ttu-id="92aaa-116">Här förklaras också de typer av data och den konfigurationsinformation som integrationen kräver.</span><span class="sxs-lookup"><span data-stu-id="92aaa-116">It also explains the types of data and the configuration details that the integration requires.</span></span>

## <a name="enable-the-integration"></a><span data-ttu-id="92aaa-117">Aktivera integrationen</span><span class="sxs-lookup"><span data-stu-id="92aaa-117">Enable the integration</span></span>

<span data-ttu-id="92aaa-118">Du måste aktivera integrationen i Personal och ange konfigurationsinformation för att ansluta till Dayforce.</span><span class="sxs-lookup"><span data-stu-id="92aaa-118">In Human Resources, you must turn on the integration and enter the configuration information to connect to Dayforce.</span></span> <span data-ttu-id="92aaa-119">Om du vill att den redovisningstransaktion som framställs ska importeras till Microsoft Dynamics 365 Finance måste du också skapa ett lagringskonto för Microsoft Azure och ange anslutningssträngen för Azure-lagring i Finance.</span><span class="sxs-lookup"><span data-stu-id="92aaa-119">If you want the general ledger transaction that is produced to be imported into Microsoft Dynamics 365 Finance, you must also set up a Microsoft Azure storage account and enter the Azure Storage connection string in Finance.</span></span>

<span data-ttu-id="92aaa-120">Följ dessa steg om du vill aktivera integration i Personal.</span><span class="sxs-lookup"><span data-stu-id="92aaa-120">To turn on the integration in Human Resources, follow these steps.</span></span>

1. <span data-ttu-id="92aaa-121">På sidan **Systemadministration** väljer du **Integrationskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="92aaa-121">On the **System administration** page, select **Integration configuration**.</span></span>
2. <span data-ttu-id="92aaa-122">Ange slutpunkten för filöverföringsprotokollet (FTP) och den säkra FTP-sökvägen.</span><span class="sxs-lookup"><span data-stu-id="92aaa-122">Enter the secure File Transfer Protocol (FTP) endpoint and the secure FTP folder path.</span></span>
3. <span data-ttu-id="92aaa-123">Ange användarnamn och lösenord för den användare som kommer att använda den säkra FTP-slutpunkten och mappsökvägen.</span><span class="sxs-lookup"><span data-stu-id="92aaa-123">Enter the user name and password of the user who will access the secure FTP endpoint and folder path.</span></span>
4. <span data-ttu-id="92aaa-124">Testa anslutningen efter behov samt ange alternativet **Aktivera integrering av löner** som **Ja**.</span><span class="sxs-lookup"><span data-stu-id="92aaa-124">Test the connection, as required, and set the **Enable payroll integration** option to **Yes**.</span></span>

<span data-ttu-id="92aaa-125">När integreringen aktiveras skapas dataexportpaket och filer, och frekvensen anges.</span><span class="sxs-lookup"><span data-stu-id="92aaa-125">When the integration is turned on, the data export package and files are created, and the frequency is set.</span></span> <span data-ttu-id="92aaa-126">Du kan ändra frekvensen efter behov.</span><span class="sxs-lookup"><span data-stu-id="92aaa-126">You can change this frequency as you require.</span></span>

<span data-ttu-id="92aaa-127">Mer information om Azure-lagringskonton och anslutningssträngar för Azure-lagring, se följande Azure-artiklar:</span><span class="sxs-lookup"><span data-stu-id="92aaa-127">For more information about Azure storage accounts and Azure Storage connection strings, see the following Azure articles:</span></span>

- [<span data-ttu-id="92aaa-128">Om Azure-lagringskonton</span><span class="sxs-lookup"><span data-stu-id="92aaa-128">About Azure storage accounts</span></span>](/azure/storage/common/storage-create-storage-account?toc=%2fazure%2fstorage%2ffiles%2ftoc.json)
- [<span data-ttu-id="92aaa-129">Konfigurera anslutningssträngar för Azure-lagring</span><span class="sxs-lookup"><span data-stu-id="92aaa-129">Configure Azure Storage connection strings</span></span>](/azure/storage/common/storage-configure-connection-string)

### <a name="technical-details-when-payroll-integration-is-enabled"></a><span data-ttu-id="92aaa-130">Teknisk information när löneintegration har aktiverats</span><span class="sxs-lookup"><span data-stu-id="92aaa-130">Technical details when payroll integration is enabled</span></span>

<span data-ttu-id="92aaa-131">Att slå på löneintegration har två primära effekter:</span><span class="sxs-lookup"><span data-stu-id="92aaa-131">Turning on the payroll integration has two primary effects:</span></span>

- <span data-ttu-id="92aaa-132">Ett dataexportprojekt med namnet "Löneintegrationexport" skapas.</span><span class="sxs-lookup"><span data-stu-id="92aaa-132">A data export project named "Payroll integration export" is created.</span></span> <span data-ttu-id="92aaa-133">Det här projektet innehåller de entiteter och fält som krävs för löneintegration.</span><span class="sxs-lookup"><span data-stu-id="92aaa-133">This project contains the entities and fields required for the payroll integration.</span></span> <span data-ttu-id="92aaa-134">För att undersöka projekt, gå till **Systemadministration**, välj **Datahantering** och öppna dataprojekt från lista över projekt.</span><span class="sxs-lookup"><span data-stu-id="92aaa-134">To examine the project, go to **System administration**, select the **Data management** tile, and then open the data project from the list of projects.</span></span>
- <span data-ttu-id="92aaa-135">Det här batchjobbet kör dataexportprojektet, krypterar det resulterande datapaketet och överför datapaketfilen till den SFTP-slutpunkt som konfigurerats på skärmen **integrationskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="92aaa-135">This batch job executes the data export project, encrypts the resulting data package, and transfers the data package file to the SFTP endpoint configured on the **Integration configuration** screen.</span></span>

> [!NOTE]
> <span data-ttu-id="92aaa-136">Det datapaket som överförs till SFTP-slutpunkten krypteras med en nyckel som är unik för paketet.</span><span class="sxs-lookup"><span data-stu-id="92aaa-136">The data package transferred to the SFTP endpoint is encrypted using a key that is unique to the package.</span></span> <span data-ttu-id="92aaa-137">Nyckeln finns i ett Azure Key Vault som bara kan nås av Ceridian.</span><span class="sxs-lookup"><span data-stu-id="92aaa-137">The key is in an Azure Key Vault that is accessible only by Ceridian.</span></span> <span data-ttu-id="92aaa-138">Det går inte att dekryptera och undersöka innehållet i datapaketet.</span><span class="sxs-lookup"><span data-stu-id="92aaa-138">It is not possible to decrypt and examine the data package contents.</span></span> <span data-ttu-id="92aaa-139">Om du behöver undersöka innehållet i datapaketet, måste du exportera dataprojektet "Löneintegrationexport" manuellt, hämta det och sedan öppna det.</span><span class="sxs-lookup"><span data-stu-id="92aaa-139">If you need to examine the contents of the data package, you need to export the "Payroll integration export" data project manually, download it, and then open it.</span></span> <span data-ttu-id="92aaa-140">Manuell export använder inte kryptering eller överföring av paketet.</span><span class="sxs-lookup"><span data-stu-id="92aaa-140">Manual export will not apply encryption or transfer the package.</span></span>
> <span data-ttu-id="92aaa-141">Om integrationsfilerna till exempel skickas från en UAT- eller sandbox-miljö för Dynamics 365 Human Resources till en Ceridian Dayforce-testmiljö kan du använda följande URL för nyckelvalv: https://payrollintegrationprod.vault.azure.net.</span><span class="sxs-lookup"><span data-stu-id="92aaa-141">For instances where the integration files are sent from a Dynamics 365 Human Resources UAT or Sandbox environment to a Ceridian Dayforce Test environment, you can use the following key vault URL: https://payrollintegrationprod.vault.azure.net.</span></span>

## <a name="configure-your-data"></a><span data-ttu-id="92aaa-142">Konfigurera dina data</span><span class="sxs-lookup"><span data-stu-id="92aaa-142">Configure your data</span></span> 

<span data-ttu-id="92aaa-143">Du måste konfigurera personaldata för att bearbeta löner i Personal.</span><span class="sxs-lookup"><span data-stu-id="92aaa-143">To process payroll, you must configure human resource data in Human Resources.</span></span> <span data-ttu-id="92aaa-144">Du måste ställa in organisationsinformation, t.ex. jobb och befattningar samt förmåner och kompensationsinformation.</span><span class="sxs-lookup"><span data-stu-id="92aaa-144">You must set up organizational data, such as jobs and positions, together with benefits and compensation information.</span></span> <span data-ttu-id="92aaa-145">Denna information utgör den anställnings-, lön- och avdragsinformationen som krävs för att generera lön för medarbetare.</span><span class="sxs-lookup"><span data-stu-id="92aaa-145">This information provides the employment, pay, and deduction information that is required in order to generate employee pay.</span></span>

### <a name="human-resource-data"></a><span data-ttu-id="92aaa-146">Personaldata</span><span class="sxs-lookup"><span data-stu-id="92aaa-146">Human resource data</span></span>

#### <a name="benefits"></a><span data-ttu-id="92aaa-147">Förmåner</span><span class="sxs-lookup"><span data-stu-id="92aaa-147">Benefits</span></span> 

<span data-ttu-id="92aaa-148">Personal tillhandahåller verktyg som kan användas för att ställa in och underhålla förmåner, avdrag och kompensationsplaner för medarbetare som en organisation erbjuder eller bearbetar för sin personal.</span><span class="sxs-lookup"><span data-stu-id="92aaa-148">Human resources provides tools for the setup and maintenance of the benefits, deductions, and worker compensation plans that an organization offers or processes for its workers.</span></span>

<span data-ttu-id="92aaa-149">När du skapar förmåner, kom då ihåg följande data och konfigurationer som används i Dayforce.</span><span class="sxs-lookup"><span data-stu-id="92aaa-149">When you create benefits, keep in mind the following data and configurations that are used in Dayforce.</span></span>

##### <a name="benefit-plans"></a><span data-ttu-id="92aaa-150">Förmånsplaner</span><span class="sxs-lookup"><span data-stu-id="92aaa-150">Benefit plans</span></span>

- <span data-ttu-id="92aaa-151">Plan (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="92aaa-151">Plan (required)</span></span>
- <span data-ttu-id="92aaa-152">Typ (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="92aaa-152">Type (required)</span></span>
- <span data-ttu-id="92aaa-153">Effekt på lön (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="92aaa-153">Payroll impact (required)</span></span>
- <span data-ttu-id="92aaa-154">Återvinn restbetalningar</span><span class="sxs-lookup"><span data-stu-id="92aaa-154">Recover arrears</span></span>
- <span data-ttu-id="92aaa-155">Avdragsmetod</span><span class="sxs-lookup"><span data-stu-id="92aaa-155">Deduction method</span></span>
- <span data-ttu-id="92aaa-156">Avdragsprioritet</span><span class="sxs-lookup"><span data-stu-id="92aaa-156">Deduction priority</span></span>
- <span data-ttu-id="92aaa-157">Gränsperiod</span><span class="sxs-lookup"><span data-stu-id="92aaa-157">Limit period</span></span>
- <span data-ttu-id="92aaa-158">Begränsa belopp</span><span class="sxs-lookup"><span data-stu-id="92aaa-158">Limit amount</span></span>

##### <a name="benefits"></a><span data-ttu-id="92aaa-159">Förmåner</span><span class="sxs-lookup"><span data-stu-id="92aaa-159">Benefits</span></span>

- <span data-ttu-id="92aaa-160">Plan (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="92aaa-160">Plan (required)</span></span>
- <span data-ttu-id="92aaa-161">Typ (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="92aaa-161">Type (required)</span></span>
- <span data-ttu-id="92aaa-162">Tillval (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="92aaa-162">Option (required)</span></span>
- <span data-ttu-id="92aaa-163">Förmåns-ID (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="92aaa-163">Benefit ID (required)</span></span>
- <span data-ttu-id="92aaa-164">Frekvens</span><span class="sxs-lookup"><span data-stu-id="92aaa-164">Frequency</span></span>
- <span data-ttu-id="92aaa-165">Bas</span><span class="sxs-lookup"><span data-stu-id="92aaa-165">Basis</span></span>
- <span data-ttu-id="92aaa-166">Belopp eller tariff</span><span class="sxs-lookup"><span data-stu-id="92aaa-166">Amount or rate</span></span>
- <span data-ttu-id="92aaa-167">Inkomstkod</span><span class="sxs-lookup"><span data-stu-id="92aaa-167">Earning code</span></span>

##### <a name="supported-frequencies"></a><span data-ttu-id="92aaa-168">Frekvenser som stöds</span><span class="sxs-lookup"><span data-stu-id="92aaa-168">Supported frequencies</span></span> 

- <span data-ttu-id="92aaa-169">Varje vecka</span><span class="sxs-lookup"><span data-stu-id="92aaa-169">Weekly</span></span>
- <span data-ttu-id="92aaa-170">Varannan vecka</span><span class="sxs-lookup"><span data-stu-id="92aaa-170">Bi-weekly</span></span>
- <span data-ttu-id="92aaa-171">Var fjortonde dag</span><span class="sxs-lookup"><span data-stu-id="92aaa-171">Semi-monthly</span></span>
- <span data-ttu-id="92aaa-172">Månatlig</span><span class="sxs-lookup"><span data-stu-id="92aaa-172">Monthly</span></span>

##### <a name="supported-bases"></a><span data-ttu-id="92aaa-173">Databaser som stöds</span><span class="sxs-lookup"><span data-stu-id="92aaa-173">Supported bases</span></span> 

- <span data-ttu-id="92aaa-174">Fast belopp</span><span class="sxs-lookup"><span data-stu-id="92aaa-174">Fixed amount</span></span>
- <span data-ttu-id="92aaa-175">Procent av inkomst</span><span class="sxs-lookup"><span data-stu-id="92aaa-175">Percent of earnings</span></span>
- <span data-ttu-id="92aaa-176">Produktiva timmar</span><span class="sxs-lookup"><span data-stu-id="92aaa-176">Productive hours</span></span>

<span data-ttu-id="92aaa-177">Dayforce skapar följande avdrag baserat på den löneeffekt som definieras i förmånsplanen.</span><span class="sxs-lookup"><span data-stu-id="92aaa-177">Dayforce creates the following deductions, based on the payroll impact that is defined on the benefit plan.</span></span>

| <span data-ttu-id="92aaa-178">Val i Personal</span><span class="sxs-lookup"><span data-stu-id="92aaa-178">Selection in Human Resources</span></span>        | <span data-ttu-id="92aaa-179">Resultat i Dayforce</span><span class="sxs-lookup"><span data-stu-id="92aaa-179">Result in Dayforce</span></span>                            |
|----------------------------|-----------------------------------------------|
| <span data-ttu-id="92aaa-180">Ingen</span><span class="sxs-lookup"><span data-stu-id="92aaa-180">None</span></span>                       | <span data-ttu-id="92aaa-181">Inget avdrag skapas.</span><span class="sxs-lookup"><span data-stu-id="92aaa-181">No deduction is created.</span></span>                      |
| <span data-ttu-id="92aaa-182">Endast avdrag</span><span class="sxs-lookup"><span data-stu-id="92aaa-182">Deduction only</span></span>             | <span data-ttu-id="92aaa-183">Löneavdrag för en medarbetare skapas.</span><span class="sxs-lookup"><span data-stu-id="92aaa-183">An employee deduction is created.</span></span>             |
| <span data-ttu-id="92aaa-184">Endast lönetillägg</span><span class="sxs-lookup"><span data-stu-id="92aaa-184">Contribution only</span></span>          | <span data-ttu-id="92aaa-185">Löneavdrag för en arbetsgivare skapas.</span><span class="sxs-lookup"><span data-stu-id="92aaa-185">An employer deduction is created.</span></span>             |
| <span data-ttu-id="92aaa-186">Avdrag och tillägg</span><span class="sxs-lookup"><span data-stu-id="92aaa-186">Deduction and contribution</span></span> | <span data-ttu-id="92aaa-187">Avdrag för medarbetare och arbetsgivare skapas.</span><span class="sxs-lookup"><span data-stu-id="92aaa-187">Employee and employer deductions are created.</span></span> |

<span data-ttu-id="92aaa-188">Mer information om hur du definierar och hanterar ett förmånsprogram finns i följande artiklar:</span><span class="sxs-lookup"><span data-stu-id="92aaa-188">For more information about how to define and manage a benefits program, see the following articles:</span></span>

- [<span data-ttu-id="92aaa-189">Utveckla ett förmånsprogram för medarbetare</span><span class="sxs-lookup"><span data-stu-id="92aaa-189">Deliver an employee benefits program</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/deliver-employee-benefits-program)
- [<span data-ttu-id="92aaa-190">Skapa en ny förmån</span><span class="sxs-lookup"><span data-stu-id="92aaa-190">Create a new benefit</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/create-new-benefit)
- [<span data-ttu-id="92aaa-191">Definiera förmånsberättiganderegler och policyer</span><span class="sxs-lookup"><span data-stu-id="92aaa-191">Define benefit eligibility rules and policies</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-benefit-eligibility-rules-policies)
- [<span data-ttu-id="92aaa-192">Registrera och ta bort förmåner för arbetare</span><span class="sxs-lookup"><span data-stu-id="92aaa-192">Enroll and remove benefits from workers</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-remove-benefits-workers)

#### <a name="compensation"></a><span data-ttu-id="92aaa-193">Kompensation</span><span class="sxs-lookup"><span data-stu-id="92aaa-193">Compensation</span></span> 

<span data-ttu-id="92aaa-194">Kompensationshantering används för att styra du utbetalningen av grundlön och belöningar.</span><span class="sxs-lookup"><span data-stu-id="92aaa-194">Compensation management is used to control the delivery of base pay and awards.</span></span> <span data-ttu-id="92aaa-195">En medarbetares fasta grundlön och merithöjningar kontrolleras genom fasta kompensationsplaner.</span><span class="sxs-lookup"><span data-stu-id="92aaa-195">An employee's fixed base pay and merit increases are controlled through fixed compensation plans.</span></span> <span data-ttu-id="92aaa-196">Betalningen av incitament, till exempel bonusar, resultatbelöningar, aktieoptioner och anslag och även engångsbelöningar kontrolleras genom variabla kompensationsplaner.</span><span class="sxs-lookup"><span data-stu-id="92aaa-196">The payment of incentive pay, such as bonus payments, performance awards, stock options, and grants, and also one-time awards, are controlled through variable compensation plans.</span></span>

<span data-ttu-id="92aaa-197">Dayforce använder kompensationsinformation för att beräkna en medarbetares tim- eller årliga betalning.</span><span class="sxs-lookup"><span data-stu-id="92aaa-197">Dayforce uses compensation information to calculate an employee's hourly or annual rate.</span></span> <span data-ttu-id="92aaa-198">Fasta kompensationsplaner och lönekonverteringar är obligatoriska.</span><span class="sxs-lookup"><span data-stu-id="92aaa-198">Fixed compensation plans and pay rate conversions are required.</span></span> <span data-ttu-id="92aaa-199">Medarbetarna måste vara anslutna till en fast kompensationsplan.</span><span class="sxs-lookup"><span data-stu-id="92aaa-199">Employees must be associated with a fixed compensation plan.</span></span>

<span data-ttu-id="92aaa-200">Mer information om att kompensationsplaner finns i följande artiklar:</span><span class="sxs-lookup"><span data-stu-id="92aaa-200">For more information about compensation plans, see the following articles:</span></span>

- [<span data-ttu-id="92aaa-201">Skapa planer för fast kompensation</span><span class="sxs-lookup"><span data-stu-id="92aaa-201">Create fixed compensation plans</span></span>](/dynamics365/unified-operations/talent/create-fixed-compensation-plans)
- [<span data-ttu-id="92aaa-202">Skapa planer för variabel kompensation</span><span class="sxs-lookup"><span data-stu-id="92aaa-202">Create variable compensation plans</span></span>](/dynamics365/unified-operations/talent/create-variable-compensation-plans)
- [<span data-ttu-id="92aaa-203">Utveckla struktur och planer för lön/kompensation</span><span class="sxs-lookup"><span data-stu-id="92aaa-203">Develop salary/compensation structure and plans</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/develop-salary-compensation-structure-plan)
- [<span data-ttu-id="92aaa-204">Bearbeta kompensation</span><span class="sxs-lookup"><span data-stu-id="92aaa-204">Process compensation</span></span>](/dynamics365/unified-operations/talent/process-compensation)
- [<span data-ttu-id="92aaa-205">Definiera kompensationsprocessen och beräkna resultat</span><span class="sxs-lookup"><span data-stu-id="92aaa-205">Define compensation process and calculate results</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-compensation-process-calculate-results)
- [<span data-ttu-id="92aaa-206">Registrera en medarbetare i en fast kompensationsplan</span><span class="sxs-lookup"><span data-stu-id="92aaa-206">Enroll an employee in a fixed compensation plan</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-fixed-compensation-plan)
- [<span data-ttu-id="92aaa-207">Registrera en medarbetare i en variabel kompensationsplan</span><span class="sxs-lookup"><span data-stu-id="92aaa-207">Enroll an employee in a variable compensation plan</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-variable-compensation-plan)

#### <a name="jobs"></a><span data-ttu-id="92aaa-208">Jobb</span><span class="sxs-lookup"><span data-stu-id="92aaa-208">Jobs</span></span> 

<span data-ttu-id="92aaa-209">Ett jobb är den samling uppgifter och ansvarsområden som avkrävs en person som utför ett jobb.</span><span class="sxs-lookup"><span data-stu-id="92aaa-209">A job is a collection of the tasks and responsibilities that are required of a person who performs a job.</span></span> <span data-ttu-id="92aaa-210">Mer information finns i följande artiklar:</span><span class="sxs-lookup"><span data-stu-id="92aaa-210">For more information, see the following articles:</span></span>

- [<span data-ttu-id="92aaa-211">Installera komponenter för ett jobb</span><span class="sxs-lookup"><span data-stu-id="92aaa-211">Setting up the components of a job</span></span>](/dynamics365/unified-operations/talent/create-job)
- [<span data-ttu-id="92aaa-212">Definiera nya jobb</span><span class="sxs-lookup"><span data-stu-id="92aaa-212">Define new jobs</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-jobs)

##### <a name="positions"></a><span data-ttu-id="92aaa-213">Befattningar</span><span class="sxs-lookup"><span data-stu-id="92aaa-213">Positions</span></span>

<span data-ttu-id="92aaa-214">En befattning är ett exempel på ett enskilt jobb.</span><span class="sxs-lookup"><span data-stu-id="92aaa-214">A position is an individual instance of a job.</span></span> <span data-ttu-id="92aaa-215">Befattningen "Försäljningschef (öst)" är exempelvis en av de befattningar som associeras med jobbet "Försäljningschef."</span><span class="sxs-lookup"><span data-stu-id="92aaa-215">For example, the "Sales manager (East)" position is one of the positions that are associated with the "Sales manager" job.</span></span> <span data-ttu-id="92aaa-216">En befattning finns på en avdelning.</span><span class="sxs-lookup"><span data-stu-id="92aaa-216">A position exists in a department.</span></span> <span data-ttu-id="92aaa-217">Endast en enda medarbetare kan vara associerad med respektive befattning.</span><span class="sxs-lookup"><span data-stu-id="92aaa-217">Only one worker can be associated with each position.</span></span>

<span data-ttu-id="92aaa-218">Tänk på följande uppgifter och konfigurationsinformation när du ställer in befattningar:</span><span class="sxs-lookup"><span data-stu-id="92aaa-218">Keep the following data and configuration in mind when you set up positions:</span></span>

- <span data-ttu-id="92aaa-219">Befattning (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="92aaa-219">Position (required)</span></span>
- <span data-ttu-id="92aaa-220">Beskrivning (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="92aaa-220">Description (required)</span></span>
- <span data-ttu-id="92aaa-221">Jobb (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="92aaa-221">Job (required)</span></span>
- <span data-ttu-id="92aaa-222">Avdelning (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="92aaa-222">Department (required)</span></span>
- <span data-ttu-id="92aaa-223">Befattningstyp (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="92aaa-223">Position type (required)</span></span>
- <span data-ttu-id="92aaa-224">Heltidslön</span><span class="sxs-lookup"><span data-stu-id="92aaa-224">Full-time equivalent</span></span>
- <span data-ttu-id="92aaa-225">Ordinarie timmar per år (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="92aaa-225">Annual regular hours (required)</span></span>
- <span data-ttu-id="92aaa-226">Betalas av den juridiska personen (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="92aaa-226">Paid by legal entity (required)</span></span>
- <span data-ttu-id="92aaa-227">Lönecykel (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="92aaa-227">Pay cycle (required)</span></span>
- <span data-ttu-id="92aaa-228">Standardekonomisk dimension – kostnadsställe (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="92aaa-228">Default financial dimension – Cost center (required)</span></span>
- <span data-ttu-id="92aaa-229">Medarbetartilldelning – medarbetare, tilldelningsstart, tilldelningsslut, orsakskod</span><span class="sxs-lookup"><span data-stu-id="92aaa-229">Worker assignment – Worker, assignment start, assignment end, reason code</span></span>

<span data-ttu-id="92aaa-230">Om flera befattningar på samma avdelning är associerade med samma jobb konsolideras de till en enda befattning i Dayforce.</span><span class="sxs-lookup"><span data-stu-id="92aaa-230">If multiple positions in the same department are associated with the same job, they are consolidated into a single position in Dayforce.</span></span>

<span data-ttu-id="92aaa-231">Mer information finns i följande artiklar:</span><span class="sxs-lookup"><span data-stu-id="92aaa-231">For more information, see the following articles:</span></span>

- [<span data-ttu-id="92aaa-232">Organisera arbetsstyrkan med avdelningar, jobb och befattningar</span><span class="sxs-lookup"><span data-stu-id="92aaa-232">Organize your workforce using departments, jobs, and positions</span></span>](/dynamics365/unified-operations/talent/departments-jobs-positions#positions)
- [<span data-ttu-id="92aaa-233">Ställ in befattningar</span><span class="sxs-lookup"><span data-stu-id="92aaa-233">Set up positions</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/set-up-positions)

#### <a name="departments"></a><span data-ttu-id="92aaa-234">Avdelningar</span><span class="sxs-lookup"><span data-stu-id="92aaa-234">Departments</span></span>

<span data-ttu-id="92aaa-235">En avdelning är en driftenhet som representerar en kategori eller verksamhetsområde inom en organisation.</span><span class="sxs-lookup"><span data-stu-id="92aaa-235">A department is an operating unit that represents a category or functional area of an organization.</span></span> <span data-ttu-id="92aaa-236">En avdelning är ansvarig för en viss del av organisationen, såsom försäljning, bokföring eller mänskliga resurser.</span><span class="sxs-lookup"><span data-stu-id="92aaa-236">A department is responsible for a specific area of the organization, such as sales, accounting, or human resources.</span></span> <span data-ttu-id="92aaa-237">Du kan använda avdelningar att rapportera om funktionella områden.</span><span class="sxs-lookup"><span data-stu-id="92aaa-237">You can use departments to report on functional areas.</span></span> <span data-ttu-id="92aaa-238">Avdelningar kan ha vinst och förlust.</span><span class="sxs-lookup"><span data-stu-id="92aaa-238">Departments might have profit and loss responsibility.</span></span>

<span data-ttu-id="92aaa-239">Mer information finns i följande artiklar:</span><span class="sxs-lookup"><span data-stu-id="92aaa-239">For more information, see the following articles:</span></span>

- [<span data-ttu-id="92aaa-240">Skapa en avdelning och associera den med avdelningshierarkin</span><span class="sxs-lookup"><span data-stu-id="92aaa-240">Create a department and associate it with the department hierarchy</span></span>](/dynamics365/unified-operations/talent/create-department-add-department-hierarchy)
- [<span data-ttu-id="92aaa-241">Definiera nya avdelningar</span><span class="sxs-lookup"><span data-stu-id="92aaa-241">Define new departments</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-departments)

#### <a name="pay-cycles-and-pay-periods"></a><span data-ttu-id="92aaa-242">Lönecykler och löneperioder</span><span class="sxs-lookup"><span data-stu-id="92aaa-242">Pay cycles and pay periods</span></span>

<span data-ttu-id="92aaa-243">En lönecykel avgör hur ofta lönelistan körs, samt vilka specifika dagar som medarbetarna får betalt.</span><span class="sxs-lookup"><span data-stu-id="92aaa-243">A pay cycle determines how often payroll is run and the specific days when workers are paid.</span></span> <span data-ttu-id="92aaa-244">En lönecykel kan exempelvis vara månadsvis och medarbetarna få sin lön den sista dagen i månaden.</span><span class="sxs-lookup"><span data-stu-id="92aaa-244">For example, a pay cycle might be monthly, and employees might be paid on the last day of the month.</span></span> <span data-ttu-id="92aaa-245">Alternativt kan en lönecykel vara veckovis och medarbetarna få sin lön på tisdagen efter betalningsperiodens utgång.</span><span class="sxs-lookup"><span data-stu-id="92aaa-245">Alternatively, a pay cycle might be weekly, and employees might be paid on the Tuesday after the end of the pay period.</span></span> <span data-ttu-id="92aaa-246">Lönecykler tilldelas befattningar i syfte att styra när arbetare på dessa befattningar får sin lön.</span><span class="sxs-lookup"><span data-stu-id="92aaa-246">Pay cycles are assigned to positions to control when workers in those positions are paid.</span></span>

<span data-ttu-id="92aaa-247">När du har skapat lönecykler kan du generera betalningsperioder för respektive cykel.</span><span class="sxs-lookup"><span data-stu-id="92aaa-247">After you create pay cycles, you can generate pay periods for each cycle.</span></span> <span data-ttu-id="92aaa-248">Varje betalningsperiod innehåller ett standardbetalningsdatum som baseras på den information du anger.</span><span class="sxs-lookup"><span data-stu-id="92aaa-248">Each pay period includes a default payment date that is based on information that you provide.</span></span> <span data-ttu-id="92aaa-249">Du kan emellertid ändra standarddatumet för betalning i en löneperiod i syfte att tillåta undantag, till exempel när betalningsdatumet infaller på en allmän helgdag.</span><span class="sxs-lookup"><span data-stu-id="92aaa-249">However, you can modify the default payment date in a pay period to allow for exceptions, such as when the payment date falls on a holiday.</span></span>

<span data-ttu-id="92aaa-250">Följande information används i Dayforce:</span><span class="sxs-lookup"><span data-stu-id="92aaa-250">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="92aaa-251">Lönecykel (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="92aaa-251">Pay cycle (required)</span></span>
- <span data-ttu-id="92aaa-252">Lönecykelfrekvens (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="92aaa-252">Pay cycle frequency (required)</span></span>
- <span data-ttu-id="92aaa-253">Periodens startdatum (första löneperiod obligatorisk)</span><span class="sxs-lookup"><span data-stu-id="92aaa-253">Period start date (first pay period required)</span></span>
- <span data-ttu-id="92aaa-254">Standarddatum för betalning (första löneperiod obligatorisk)</span><span class="sxs-lookup"><span data-stu-id="92aaa-254">Default payment date (first pay period required)</span></span>

<span data-ttu-id="92aaa-255">Denna information är integrerad i Dayforce som lönegrupper och delas upp efter land eller region för respektive lönecykel.</span><span class="sxs-lookup"><span data-stu-id="92aaa-255">This information is integrated with Dayforce as pay groups, and is separated by country or region for each pay cycle.</span></span> <span data-ttu-id="92aaa-256">Minst en löneperiod måste genereras före integration.</span><span class="sxs-lookup"><span data-stu-id="92aaa-256">At least one pay period must be generated before integration.</span></span> <span data-ttu-id="92aaa-257">Dayforce genererar gruppkalendrar för lön och betalningsdatum utifrån startdatumet för den första löneperioden och det standarddatum för betalning som anges i Personal.</span><span class="sxs-lookup"><span data-stu-id="92aaa-257">Dayforce generates pay group calendars and payment dates, based on the start date of the first pay period and the default payment date that is set up in Human Resources.</span></span>

#### <a name="earning-codes"></a><span data-ttu-id="92aaa-258">Inkomstkoder</span><span class="sxs-lookup"><span data-stu-id="92aaa-258">Earning codes</span></span>

<span data-ttu-id="92aaa-259">Inkomstkoder identifierar individuellt alla typer av arbetstagarintäkter.</span><span class="sxs-lookup"><span data-stu-id="92aaa-259">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="92aaa-260">Koderna har olika parametrar som rör inkomster, till exempel redovisningsbestämmelser, skattelagar, rapporteringskrav, och gross up-kapacitet.</span><span class="sxs-lookup"><span data-stu-id="92aaa-260">The codes have various parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span>

<span data-ttu-id="92aaa-261">Följande information används i Dayforce:</span><span class="sxs-lookup"><span data-stu-id="92aaa-261">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="92aaa-262">Inkomstkod (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="92aaa-262">Earning Code (required)</span></span>
- <span data-ttu-id="92aaa-263">beskrivning</span><span class="sxs-lookup"><span data-stu-id="92aaa-263">Description</span></span>
- <span data-ttu-id="92aaa-264">Enhet</span><span class="sxs-lookup"><span data-stu-id="92aaa-264">Unit of measure</span></span>
- <span data-ttu-id="92aaa-265">Produktiv</span><span class="sxs-lookup"><span data-stu-id="92aaa-265">Productive</span></span>

### <a name="worker-data"></a><span data-ttu-id="92aaa-266">Medarbetardata</span><span class="sxs-lookup"><span data-stu-id="92aaa-266">Worker data</span></span>

<span data-ttu-id="92aaa-267">Poster för de olika typer av medarbetare som du har är viktiga för dina personal- och lönesystem.</span><span class="sxs-lookup"><span data-stu-id="92aaa-267">Records for the various types of workers that you have are important to your human resources and payroll systems.</span></span> <span data-ttu-id="92aaa-268">Den information du anger kan användas för att spåra medarbetare och personuppgifter.</span><span class="sxs-lookup"><span data-stu-id="92aaa-268">The information that you enter can be used to track workers and personal information.</span></span>

<span data-ttu-id="92aaa-269">För medarbetare kan du behålla följande information:</span><span class="sxs-lookup"><span data-stu-id="92aaa-269">You can maintain the following information for workers:</span></span>

- <span data-ttu-id="92aaa-270">**Grundläggande** – Grundläggande information om en medarbetare, till exempel kontaktinformation, demografisk information, identifikationsinformation, familjeinformation, status för militärtjänst, exilstatusinformation samt personliga och nödkontakter.</span><span class="sxs-lookup"><span data-stu-id="92aaa-270">**Basic** – Maintain basic information about a worker, such as contact information, demographic information, identification information, family information, military service status, expatriate information, and personal and emergency contacts.</span></span>
- <span data-ttu-id="92aaa-271">**Anställning** – Information om en medarbetares anställning, exempelvis företags- eller organisationstillhörighet, befattningstilldelning, start- och slutdatum, jobbtillgänglighet, anställningsvillkor, pension, semester- samt omplaceringsinformation.</span><span class="sxs-lookup"><span data-stu-id="92aaa-271">**Employment** – Maintain information about a worker's employment, such as company or organization affiliation, position assignment, start and end dates, work eligibility, terms of employment, pension, vacation, and relocation information.</span></span>
- <span data-ttu-id="92aaa-272">**Tjänstledighet och frånvaro** – Information om en medarbetares frånvaro, exempelvis jobbkalendrar, frånvarotransaktioner samt frånvaroinställningar.</span><span class="sxs-lookup"><span data-stu-id="92aaa-272">**Leave and absence** – Maintain information about a worker's absences, such as working calendars, absence transactions, and absence setup.</span></span>
- <span data-ttu-id="92aaa-273">**Ersättning och lön** – Information om en medarbetares ersättningsplaner och löneinformation, exempelvis plananmälan, utmärkelser, resultat, provision, skatteinformation, pensionering samt löneavdrag.</span><span class="sxs-lookup"><span data-stu-id="92aaa-273">**Compensation and payroll** – Maintain information about a worker's compensation plans and payroll information, such as plan enrollment, awards, performance, commission, tax information, retirement, and salary deductions.</span></span>

<span data-ttu-id="92aaa-274">När du anger medarbetarinformation, kom då ihåg följande uppgifter och konfigurationer som används i Dayforce.</span><span class="sxs-lookup"><span data-stu-id="92aaa-274">When you enter worker information, keep in mind the following data and configurations that are used in Dayforce.</span></span>

#### <a name="general-information"></a><span data-ttu-id="92aaa-275">Allmän information</span><span class="sxs-lookup"><span data-stu-id="92aaa-275">General information</span></span>

- <span data-ttu-id="92aaa-276">Anställningsnummer (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="92aaa-276">Personnel number (required)</span></span>
- <span data-ttu-id="92aaa-277">Förnamn (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="92aaa-277">First name (required)</span></span>
- <span data-ttu-id="92aaa-278">Efternamn (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="92aaa-278">Last name (required)</span></span>
- <span data-ttu-id="92aaa-279">Mellannamn</span><span class="sxs-lookup"><span data-stu-id="92aaa-279">Middle name</span></span>
- <span data-ttu-id="92aaa-280">Datum för tjänsteålder</span><span class="sxs-lookup"><span data-stu-id="92aaa-280">Seniority date</span></span>
- <span data-ttu-id="92aaa-281">Känt som</span><span class="sxs-lookup"><span data-stu-id="92aaa-281">Known as</span></span>

#### <a name="personal-information"></a><span data-ttu-id="92aaa-282">Personlig information</span><span class="sxs-lookup"><span data-stu-id="92aaa-282">Personal information</span></span>

- <span data-ttu-id="92aaa-283">Civilstånd (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="92aaa-283">Marital status (required)</span></span>
- <span data-ttu-id="92aaa-284">Födelsedatum (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="92aaa-284">Birth date (required)</span></span>
- <span data-ttu-id="92aaa-285">Könstillhörighet (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="92aaa-285">Gender (required)</span></span>
- <span data-ttu-id="92aaa-286">Person med funktionsnedsättningar</span><span class="sxs-lookup"><span data-stu-id="92aaa-286">Person with disabilities</span></span>
- <span data-ttu-id="92aaa-287">Medborgarskap, land, region (endast för Mexiko)</span><span class="sxs-lookup"><span data-stu-id="92aaa-287">Nationality country region (only for Mexico)</span></span>

#### <a name="address-information"></a><span data-ttu-id="92aaa-288">Adressinformation</span><span class="sxs-lookup"><span data-stu-id="92aaa-288">Address information</span></span>

- <span data-ttu-id="92aaa-289">Primär adress (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="92aaa-289">Primary (required)</span></span>
- <span data-ttu-id="92aaa-290">Land/region (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="92aaa-290">Country/region (required)</span></span>
- <span data-ttu-id="92aaa-291">Postnummer (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="92aaa-291">Postal code (required)</span></span>
- <span data-ttu-id="92aaa-292">Nummer (obligatoriskt) (endast för Mexiko)</span><span class="sxs-lookup"><span data-stu-id="92aaa-292">Street Number (required) (Only for Mexico)</span></span>
- <span data-ttu-id="92aaa-293">Byggnadskomplement (endast för Mexiko)</span><span class="sxs-lookup"><span data-stu-id="92aaa-293">Building Complement (Only for Mexico)</span></span>
- <span data-ttu-id="92aaa-294">Stad (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="92aaa-294">City (required)</span></span>
- <span data-ttu-id="92aaa-295">Delstat (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="92aaa-295">State (required)</span></span>
- <span data-ttu-id="92aaa-296">Region (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="92aaa-296">County (required)</span></span>

#### <a name="contact-information"></a><span data-ttu-id="92aaa-297">Kontaktinformation</span><span class="sxs-lookup"><span data-stu-id="92aaa-297">Contact information</span></span> 

- <span data-ttu-id="92aaa-298">Primär adress (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="92aaa-298">Primary (required)</span></span>
- <span data-ttu-id="92aaa-299">Kontaktnummer (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="92aaa-299">Contact number (required)</span></span>
- <span data-ttu-id="92aaa-300">Anknytning</span><span class="sxs-lookup"><span data-stu-id="92aaa-300">Extension</span></span>

#### <a name="payroll-information-and-earning-codes"></a><span data-ttu-id="92aaa-301">Löneinformation och inkomstkoder</span><span class="sxs-lookup"><span data-stu-id="92aaa-301">Payroll information and earning codes</span></span>

<span data-ttu-id="92aaa-302">Medarbetare kan tilldelas en viss inkomst till en viss betalningsfrekvens och ha en prioriterad betalningsmetod.</span><span class="sxs-lookup"><span data-stu-id="92aaa-302">Employees may be assigned specific earnings at a given frequency of payment and have a preferred payment method.</span></span> <span data-ttu-id="92aaa-303">Följande fält används i Dayforce för att garantera att dessa prioriteringar och inställningar används.</span><span class="sxs-lookup"><span data-stu-id="92aaa-303">The following fields are used in Dayforce to help guarantee that those preferences and settings are used.</span></span>

##### <a name="earning-codes"></a><span data-ttu-id="92aaa-304">Inkomstkoder</span><span class="sxs-lookup"><span data-stu-id="92aaa-304">Earning codes</span></span>

- <span data-ttu-id="92aaa-305">Befattning (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="92aaa-305">Position (required)</span></span>
- <span data-ttu-id="92aaa-306">Inkomstkod (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="92aaa-306">Earning Code (required)</span></span>
- <span data-ttu-id="92aaa-307">Frekvens (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="92aaa-307">Frequency (required)</span></span>
- <span data-ttu-id="92aaa-308">Belopp (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="92aaa-308">Amount (required)</span></span>

##### <a name="payroll-information"></a><span data-ttu-id="92aaa-309">Löneinformation</span><span class="sxs-lookup"><span data-stu-id="92aaa-309">Payroll information</span></span>

- <span data-ttu-id="92aaa-310">Betalningsmetod</span><span class="sxs-lookup"><span data-stu-id="92aaa-310">Payment Method</span></span>
- <span data-ttu-id="92aaa-311">Ekonomisk region (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="92aaa-311">Economic Region (required)</span></span>
- <span data-ttu-id="92aaa-312">ID för anställningsförmåner</span><span class="sxs-lookup"><span data-stu-id="92aaa-312">Employee Benefits ID</span></span>
- <span data-ttu-id="92aaa-313">Nationellt ID-nummer (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="92aaa-313">National ID Number (required)</span></span>
- <span data-ttu-id="92aaa-314">Militärtjänstgöring, nummer</span><span class="sxs-lookup"><span data-stu-id="92aaa-314">Military Service Number</span></span>
- <span data-ttu-id="92aaa-315">Skiftes-ID (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="92aaa-315">Shift ID (required)</span></span>
- <span data-ttu-id="92aaa-316">Skattenummer (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="92aaa-316">Tax Number (required)</span></span>
- <span data-ttu-id="92aaa-317">Fack-ID (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="92aaa-317">Union ID (required)</span></span>
- <span data-ttu-id="92aaa-318">Arbetsdags-ID (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="92aaa-318">Work Day ID (required)</span></span>
- <span data-ttu-id="92aaa-319">Arbetstillståndsnummer</span><span class="sxs-lookup"><span data-stu-id="92aaa-319">Work Permit Number</span></span>

> [!NOTE]
> <span data-ttu-id="92aaa-320">För betalsättet stöder Mexiko **Kontant**, **Check** (företagets fysiska check), samt **Elektronisk betalning**.</span><span class="sxs-lookup"><span data-stu-id="92aaa-320">For the payment method, Mexico supports **Cash**, **Check** (the company's physical check), and **Electronic Payment**.</span></span> <span data-ttu-id="92aaa-321">Om betalsättet np anges används **Check** som standard.</span><span class="sxs-lookup"><span data-stu-id="92aaa-321">If np payment method is specified, **Check** is used by default.</span></span>

#### <a name="employment-details"></a><span data-ttu-id="92aaa-322">Anställningsinformation</span><span class="sxs-lookup"><span data-stu-id="92aaa-322">Employment details</span></span>

<span data-ttu-id="92aaa-323">Detaljerad anställningshistorik används som viktig information i syfte att hämta en medarbetares anställnings-, uppsägnings- och återanställningsstatus i Dayforce.</span><span class="sxs-lookup"><span data-stu-id="92aaa-323">Employment detail history is used as key information to derive an employee's hire, termination, and rehire statuses in Dayforce.</span></span> <span data-ttu-id="92aaa-324">Dayforce stöder endast en aktiv anställningspost åt gången.</span><span class="sxs-lookup"><span data-stu-id="92aaa-324">Dayforce supports only one active employment record at a time.</span></span>

- <span data-ttu-id="92aaa-325">Startdatum för anställning (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="92aaa-325">Employment start date (required)</span></span>
- <span data-ttu-id="92aaa-326">Slutdatum för anställning</span><span class="sxs-lookup"><span data-stu-id="92aaa-326">Employment end date</span></span>
- <span data-ttu-id="92aaa-327">Startdatum</span><span class="sxs-lookup"><span data-stu-id="92aaa-327">Start date</span></span>
- <span data-ttu-id="92aaa-328">Justerat startdatum</span><span class="sxs-lookup"><span data-stu-id="92aaa-328">Adjusted start date</span></span>
- <span data-ttu-id="92aaa-329">Uppsägningsdatum (obligatoriskt vid uppsägning)</span><span class="sxs-lookup"><span data-stu-id="92aaa-329">Termination date (required upon termination)</span></span>
- <span data-ttu-id="92aaa-330">Uppsägningsorsak (obligatoriskt vid uppsägning)</span><span class="sxs-lookup"><span data-stu-id="92aaa-330">Termination reason (required upon termination)</span></span>

<span data-ttu-id="92aaa-331">Medarbetarens viktiga datum beräknas med hjälp av följande information.</span><span class="sxs-lookup"><span data-stu-id="92aaa-331">An employee's key dates are derived by using the following information.</span></span>

| <span data-ttu-id="92aaa-332">Personal</span><span class="sxs-lookup"><span data-stu-id="92aaa-332">Human Resources</span></span>                | <span data-ttu-id="92aaa-333">Dayforce</span><span class="sxs-lookup"><span data-stu-id="92aaa-333">Dayforce</span></span>                                                                                             |
|-----------------------|------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="92aaa-334">Senaste anställningsdatum</span><span class="sxs-lookup"><span data-stu-id="92aaa-334">Most recent hire date</span></span> | <span data-ttu-id="92aaa-335">Anställningsstart för aktuell, icke-uppsagd post för anställningshistorik</span><span class="sxs-lookup"><span data-stu-id="92aaa-335">Employment start of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="92aaa-336">Uppsägningsdatum</span><span class="sxs-lookup"><span data-stu-id="92aaa-336">Termination date</span></span>      | <span data-ttu-id="92aaa-337">Uppsägningsdatum för aktuell, icke-uppsagd post för anställningshistorik</span><span class="sxs-lookup"><span data-stu-id="92aaa-337">Termination date of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="92aaa-338">Startdatum</span><span class="sxs-lookup"><span data-stu-id="92aaa-338">Start date</span></span>            | <span data-ttu-id="92aaa-339">Justerat startdatum, startdatum eller anställningsstart för aktuell, inaktiv post för anställningshistorik</span><span class="sxs-lookup"><span data-stu-id="92aaa-339">Adjusted start date, start date, or employment start of current non-active employment history record</span></span> |
| <span data-ttu-id="92aaa-340">Ursprungligt anställningsdatum</span><span class="sxs-lookup"><span data-stu-id="92aaa-340">Original hire date</span></span>    | <span data-ttu-id="92aaa-341">Anställningsstart för tidigaste anställningshistorikpost</span><span class="sxs-lookup"><span data-stu-id="92aaa-341">Employment start of earliest employment history record</span></span>                                               |

#### <a name="compensation"></a><span data-ttu-id="92aaa-342">Kompensation</span><span class="sxs-lookup"><span data-stu-id="92aaa-342">Compensation</span></span>

<span data-ttu-id="92aaa-343">En fast kompensationsplan måste kopplas till varje medarbetares primära befattning under hela anställningsperioden.</span><span class="sxs-lookup"><span data-stu-id="92aaa-343">A fixed compensation plan must be associated with every employee's primary position throughout an employment period.</span></span> <span data-ttu-id="92aaa-344">Perioden inleds det datum då medarbetaren anställts (eller på anställningens startdatum) och fortsätter till och med uppsägningen.</span><span class="sxs-lookup"><span data-stu-id="92aaa-344">This period starts on the date that the employee was hired (or the employment start date) and continues until termination.</span></span>

- <span data-ttu-id="92aaa-345">Giltighetsdatum (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="92aaa-345">Effective Date (required)</span></span>
- <span data-ttu-id="92aaa-346">Utgångsdatum</span><span class="sxs-lookup"><span data-stu-id="92aaa-346">Expiration date</span></span>
- <span data-ttu-id="92aaa-347">Lönesats (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="92aaa-347">Pay Rate (required)</span></span>
- <span data-ttu-id="92aaa-348">Lönesatskonverteringar (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="92aaa-348">Pay Rate Conversions (required)</span></span>
- <span data-ttu-id="92aaa-349">Årlig motsvarighet (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="92aaa-349">Annual equivalent (required)</span></span>
- <span data-ttu-id="92aaa-350">Motsvarighet per timme (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="92aaa-350">Hourly equivalent (required)</span></span>

<span data-ttu-id="92aaa-351">Om en timanställd har flera befattningar importeras den fasta kompensationen för den primära befattningen till Dayforce som bastariff/-lön för medarbetaren.</span><span class="sxs-lookup"><span data-stu-id="92aaa-351">If an hourly employee has multiple positions, the fixed compensation of the primary position is imported into Dayforce as the employee-level base rate/salary.</span></span> <span data-ttu-id="92aaa-352">För icke-primära befattningar sparas timtariffen i motsvarande befattning i Dayforce.</span><span class="sxs-lookup"><span data-stu-id="92aaa-352">For non-primary positions, the hourly rate is saved to the corresponding position in Dayforce.</span></span>

<span data-ttu-id="92aaa-353">Om en fast anställd tjänsteman har flera befattningar hämtas den ackumulerade timtariffen och årslönen för samtliga aktiva befattningar och används som bastariff/-lön för medarbetarnivån.</span><span class="sxs-lookup"><span data-stu-id="92aaa-353">If a salaried employee has multiple positions, the cumulative hour rate and annual salary across all active positions are derived and used as the employee-level base rate/salary.</span></span>

#### <a name="identification-numbers"></a><span data-ttu-id="92aaa-354">Identifieringsnummer</span><span class="sxs-lookup"><span data-stu-id="92aaa-354">Identification numbers</span></span>

##### <a name="social-security-identifier"></a><span data-ttu-id="92aaa-355">Socialförsäkrings-identifierare</span><span class="sxs-lookup"><span data-stu-id="92aaa-355">Social Security identifier</span></span> 

<span data-ttu-id="92aaa-356">Alla medarbetare måste ha en primär identifierare.</span><span class="sxs-lookup"><span data-stu-id="92aaa-356">Every employee must have one primary identifier.</span></span> <span data-ttu-id="92aaa-357">Denna identifierare måste vara av identifieringstypen **SSN**.</span><span class="sxs-lookup"><span data-stu-id="92aaa-357">This identifier must be of **SSN** identification type.</span></span> <span data-ttu-id="92aaa-358">I Dayforce hämtas den automatiskt som den socialförsäkringsidentifierare för anställd som krävs för anställning.</span><span class="sxs-lookup"><span data-stu-id="92aaa-358">In Dayforce, it's automatically derived as the employee's Social Security identifier that is required for hire.</span></span>

- <span data-ttu-id="92aaa-359">Primär adress (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="92aaa-359">Primary (required)</span></span>
- <span data-ttu-id="92aaa-360">Identifieringstyp = "SSN"</span><span class="sxs-lookup"><span data-stu-id="92aaa-360">Identification Type = "SSN"</span></span>
- <span data-ttu-id="92aaa-361">Utfärdat den</span><span class="sxs-lookup"><span data-stu-id="92aaa-361">Issued Date</span></span>
- <span data-ttu-id="92aaa-362">Utgångsdatum</span><span class="sxs-lookup"><span data-stu-id="92aaa-362">Expiration Date</span></span>

<span data-ttu-id="92aaa-363">Medarbetare kan deklarera flera ID-nummer med ID-typen **SSN**.</span><span class="sxs-lookup"><span data-stu-id="92aaa-363">Employees can declare multiple identification numbers of the **SSN** identification type.</span></span> <span data-ttu-id="92aaa-364">Endast posten som är markerad som **Primär** integreras emellertid i Dayforce, oavsett om numret är aktivt eller har upphört att gälla.</span><span class="sxs-lookup"><span data-stu-id="92aaa-364">However, only the record that is marked as **Primary** is integrated into Dayforce, regardless of whether the number is active or expired.</span></span>

#### <a name="bank-accounts-and-disbursements"></a><span data-ttu-id="92aaa-365">Bankkonton och utbetalningar</span><span class="sxs-lookup"><span data-stu-id="92aaa-365">Bank accounts and disbursements</span></span>

<span data-ttu-id="92aaa-366">Giltig bankkontoinformation måste anges för varje medarbetare som väljer att få sin lön via bankkontoöverföringar.</span><span class="sxs-lookup"><span data-stu-id="92aaa-366">Valid bank account information must be entered for any employee who chooses to be paid via bank account transfers.</span></span>

| <span data-ttu-id="92aaa-367">Personal</span><span class="sxs-lookup"><span data-stu-id="92aaa-367">Human Resources</span></span>                         | <span data-ttu-id="92aaa-368">Dayforce</span><span class="sxs-lookup"><span data-stu-id="92aaa-368">Dayforce</span></span>                                                                                                    |
|--------------------------------|-------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="92aaa-369">Bankkontonummer (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="92aaa-369">Bank account number (required)</span></span> |                                                                                                             |
| <span data-ttu-id="92aaa-370">SWIFT-kod (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="92aaa-370">SWIFT code (required)</span></span>          | <span data-ttu-id="92aaa-371">Fältet **Bank-ID** används när löner bearbetas i Mexiko.</span><span class="sxs-lookup"><span data-stu-id="92aaa-371">**Bank ID** field used when processing payroll in Mexico.</span></span>                                                             |
| <span data-ttu-id="92aaa-372">Filialnummer (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="92aaa-372">Branch number (required)</span></span>       |                                                                                                             |
| <span data-ttu-id="92aaa-373">Bankkontotyp (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="92aaa-373">Bank account type (required)</span></span>   | <span data-ttu-id="92aaa-374">Fältet **Kontotyp** används när löner bearbetas i Mexiko.</span><span class="sxs-lookup"><span data-stu-id="92aaa-374">**Account type** field used when processing payroll in Mexico.</span></span> <span data-ttu-id="92aaa-375">Värden som stöds inkluderar **Check** och **Lönelista**.</span><span class="sxs-lookup"><span data-stu-id="92aaa-375">Supported values include **Checking** and **Payroll**.</span></span> |

> [!NOTE]
> <span data-ttu-id="92aaa-376">Medarbetare som väljer att få lön via bankkontoöverföring måste ange en länk till ett restkonto tillhörande en juridisk person med primär adress i Mexiko och som är associerad med ett giltigt bankkonto från en mexikansk bank.</span><span class="sxs-lookup"><span data-stu-id="92aaa-376">Employees who choose to be paid via bank account transfers must provide a link to a remainder account that is under a legal entity that has its primary address in Mexico and associated with a valid bank account from a Mexican bank.</span></span> <span data-ttu-id="92aaa-377">Alla övriga restkonton ignoreras.</span><span class="sxs-lookup"><span data-stu-id="92aaa-377">All other non-remainder accounts are ignored.</span></span>

#### <a name="address-information"></a><span data-ttu-id="92aaa-378">Adressinformation</span><span class="sxs-lookup"><span data-stu-id="92aaa-378">Address information</span></span>

<span data-ttu-id="92aaa-379">Alla medarbetare måste ha en primär plats.</span><span class="sxs-lookup"><span data-stu-id="92aaa-379">Every employee must have one primary location.</span></span> <span data-ttu-id="92aaa-380">Den här platsen används i Dayforce i syfte att fastställa medarbetarens primära hemort i skattesyfte.</span><span class="sxs-lookup"><span data-stu-id="92aaa-380">In Dayforce, this location is used to determine the employee's primary residence for tax purposes.</span></span>

- <span data-ttu-id="92aaa-381">Primär adress (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="92aaa-381">Primary (required)</span></span>
- <span data-ttu-id="92aaa-382">Land/region (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="92aaa-382">Country/region (required)</span></span>
- <span data-ttu-id="92aaa-383">Postnummer (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="92aaa-383">Zip/postal code (required)</span></span>
- <span data-ttu-id="92aaa-384">Gata (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="92aaa-384">Street (required)</span></span>
- <span data-ttu-id="92aaa-385">Nummer (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="92aaa-385">Street Number (required)</span></span>
- <span data-ttu-id="92aaa-386">Byggnadskomplement</span><span class="sxs-lookup"><span data-stu-id="92aaa-386">Building Complement</span></span>
- <span data-ttu-id="92aaa-387">Stad (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="92aaa-387">City (required)</span></span>
- <span data-ttu-id="92aaa-388">Delstat (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="92aaa-388">State (required)</span></span>
- <span data-ttu-id="92aaa-389">Region (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="92aaa-389">County (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-united-states-and-canada"></a><span data-ttu-id="92aaa-390">Konfigurera dina data för att generera lön i USA och Kanada</span><span class="sxs-lookup"><span data-stu-id="92aaa-390">Configure your data to generate payroll in United States and Canada</span></span>

<span data-ttu-id="92aaa-391">Om du genererar lön för medarbetare i USA och Kanada måste följande element konfigureras:</span><span class="sxs-lookup"><span data-stu-id="92aaa-391">If you're generating pay for employees in the United States and Canada, the following elements must be configured:</span></span>

- <span data-ttu-id="92aaa-392">Avdelningar är obligatoriska vid befattningarna:</span><span class="sxs-lookup"><span data-stu-id="92aaa-392">Departments are required on positions.</span></span>
- <span data-ttu-id="92aaa-393">Kostnadsställen måste ställas in som ekonomiska dimensioner och måste vara det första elementet i standardsträngen för ekonomisk dimension.</span><span class="sxs-lookup"><span data-stu-id="92aaa-393">Cost centers must be set as financial dimensions and must be the first element in the default financial dimension string.</span></span>

> [!NOTE] 
> <span data-ttu-id="92aaa-394">Du kan konfigurera Personal att kräva att befattningar anger en avdelning.</span><span class="sxs-lookup"><span data-stu-id="92aaa-394">You can configure Human Resources to require that Positions specify a Department.</span></span> <span data-ttu-id="92aaa-395">Gör detta genom att gå till **delade befattningar i Personal > befattningar > kräver avdelningar för befattningar**.</span><span class="sxs-lookup"><span data-stu-id="92aaa-395">To do this, go to **Human Resources Shared Positions > Positions > Require departments on positions**.</span></span> <span data-ttu-id="92aaa-396">Vi rekommenderar att den här inställningen tillämpas för integration.</span><span class="sxs-lookup"><span data-stu-id="92aaa-396">We recommend that this setting be enforced for the integration.</span></span>

### <a name="job-types"></a><span data-ttu-id="92aaa-397">Jobbtyper</span><span class="sxs-lookup"><span data-stu-id="92aaa-397">Job types</span></span>

<span data-ttu-id="92aaa-398">Jobbtyper används för att gruppera liknande jobb i kategorier.</span><span class="sxs-lookup"><span data-stu-id="92aaa-398">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="92aaa-399">Jobbtyper krävs för att bearbeta lön i USA och Kanada.</span><span class="sxs-lookup"><span data-stu-id="92aaa-399">Job types are required in order to process payroll in the United States and Canada.</span></span> <span data-ttu-id="92aaa-400">Några exempel på jobbtyper är heltid och deltid, eller fast lön och timpenning.</span><span class="sxs-lookup"><span data-stu-id="92aaa-400">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="92aaa-401">Jobbtyper mappas till Dayforce som lönetyper som anger huruvida en anställd arbetar per timme eller har fast lön.</span><span class="sxs-lookup"><span data-stu-id="92aaa-401">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="92aaa-402">Följande jobbtyper och beskrivningar krävs.</span><span class="sxs-lookup"><span data-stu-id="92aaa-402">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="92aaa-403">Jobbtyp</span><span class="sxs-lookup"><span data-stu-id="92aaa-403">Job type</span></span>   | <span data-ttu-id="92aaa-404">beskrivning</span><span class="sxs-lookup"><span data-stu-id="92aaa-404">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="92aaa-405">Varje timme</span><span class="sxs-lookup"><span data-stu-id="92aaa-405">Hourly</span></span>     | <span data-ttu-id="92aaa-406">Varje timme</span><span class="sxs-lookup"><span data-stu-id="92aaa-406">Hourly</span></span>      |
| <span data-ttu-id="92aaa-407">Fast lön</span><span class="sxs-lookup"><span data-stu-id="92aaa-407">Salaried</span></span>   | <span data-ttu-id="92aaa-408">Fast lön</span><span class="sxs-lookup"><span data-stu-id="92aaa-408">Salaried</span></span>    |

### <a name="position-types"></a><span data-ttu-id="92aaa-409">Befattningstyper</span><span class="sxs-lookup"><span data-stu-id="92aaa-409">Position types</span></span> 

<span data-ttu-id="92aaa-410">Du kan använda befattningstyper för att beskriva huruvida befattningen är på heltid, deltid eller annat.</span><span class="sxs-lookup"><span data-stu-id="92aaa-410">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="92aaa-411">Befattningstyper mappas till Dayforce som löneklasser som anger huruvida en anställd arbetar heltid eller deltid.</span><span class="sxs-lookup"><span data-stu-id="92aaa-411">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="92aaa-412">Följande befattningstyper och beskrivningar krävs.</span><span class="sxs-lookup"><span data-stu-id="92aaa-412">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="92aaa-413">Befattningstyp</span><span class="sxs-lookup"><span data-stu-id="92aaa-413">Position type</span></span>   | <span data-ttu-id="92aaa-414">beskrivning</span><span class="sxs-lookup"><span data-stu-id="92aaa-414">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="92aaa-415">Heltid</span><span class="sxs-lookup"><span data-stu-id="92aaa-415">Full-time</span></span>       | <span data-ttu-id="92aaa-416">Heltidsanställd</span><span class="sxs-lookup"><span data-stu-id="92aaa-416">Full time employee</span></span> |
| <span data-ttu-id="92aaa-417">Deltid</span><span class="sxs-lookup"><span data-stu-id="92aaa-417">Part-time</span></span>       | <span data-ttu-id="92aaa-418">Deltidsanställd</span><span class="sxs-lookup"><span data-stu-id="92aaa-418">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="92aaa-419">Orsakskoder</span><span class="sxs-lookup"><span data-stu-id="92aaa-419">Reason codes</span></span>

<span data-ttu-id="92aaa-420">Orsakskoder innehåller information om statusen för en medarbetare.</span><span class="sxs-lookup"><span data-stu-id="92aaa-420">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="92aaa-421">Orsakskoder mappas till Dayforce som statusanledningar som anger orsaken till ändringar i en medarbetares befattning eller anställningsstatus.</span><span class="sxs-lookup"><span data-stu-id="92aaa-421">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="92aaa-422">Följande orsakskoder och -beskrivningar krävs.</span><span class="sxs-lookup"><span data-stu-id="92aaa-422">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="92aaa-423">Orsakskod</span><span class="sxs-lookup"><span data-stu-id="92aaa-423">Reason code</span></span>    | <span data-ttu-id="92aaa-424">beskrivning</span><span class="sxs-lookup"><span data-stu-id="92aaa-424">Description</span></span>      | <span data-ttu-id="92aaa-425">Tillämpliga scenarier</span><span class="sxs-lookup"><span data-stu-id="92aaa-425">Applicable scenarios</span></span> |
|----------------|------------------|----------------------|
| <span data-ttu-id="92aaa-426">EGEN UPPSÄGNING</span><span class="sxs-lookup"><span data-stu-id="92aaa-426">RESIGNATION</span></span>    | <span data-ttu-id="92aaa-427">Egen uppsägning</span><span class="sxs-lookup"><span data-stu-id="92aaa-427">Resignation</span></span>      | <span data-ttu-id="92aaa-428">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="92aaa-428">Terminate worker</span></span>     |
| <span data-ttu-id="92aaa-429">UPPSÄGNING</span><span class="sxs-lookup"><span data-stu-id="92aaa-429">TERMINATION</span></span>    | <span data-ttu-id="92aaa-430">Uppsägning</span><span class="sxs-lookup"><span data-stu-id="92aaa-430">Termination</span></span>      | <span data-ttu-id="92aaa-431">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="92aaa-431">Terminate worker</span></span>     |
| <span data-ttu-id="92aaa-432">PENSION</span><span class="sxs-lookup"><span data-stu-id="92aaa-432">RETIREMENT</span></span>     | <span data-ttu-id="92aaa-433">Pension</span><span class="sxs-lookup"><span data-stu-id="92aaa-433">Retirement</span></span>       | <span data-ttu-id="92aaa-434">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="92aaa-434">Terminate worker</span></span>     |
| <span data-ttu-id="92aaa-435">ÖVRIGT</span><span class="sxs-lookup"><span data-stu-id="92aaa-435">OTHER</span></span>          | <span data-ttu-id="92aaa-436">Andra orsaker</span><span class="sxs-lookup"><span data-stu-id="92aaa-436">Other Reasons</span></span>    | <span data-ttu-id="92aaa-437">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="92aaa-437">Terminate worker</span></span>     |
| <span data-ttu-id="92aaa-438">DÖDSFALL</span><span class="sxs-lookup"><span data-stu-id="92aaa-438">DEATH</span></span>          | <span data-ttu-id="92aaa-439">Dödsfall</span><span class="sxs-lookup"><span data-stu-id="92aaa-439">Death</span></span>            | <span data-ttu-id="92aaa-440">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="92aaa-440">Terminate worker</span></span>     |
| <span data-ttu-id="92aaa-441">TJÄNSTLEDIGHET</span><span class="sxs-lookup"><span data-stu-id="92aaa-441">LEAVEOFABSENCE</span></span> | <span data-ttu-id="92aaa-442">Tjänstledighet</span><span class="sxs-lookup"><span data-stu-id="92aaa-442">Leave of Absence</span></span> | <span data-ttu-id="92aaa-443">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="92aaa-443">Terminate worker</span></span>     |
| <span data-ttu-id="92aaa-444">KONTRAKTSLUT</span><span class="sxs-lookup"><span data-stu-id="92aaa-444">CONTRACTEND</span></span>    | <span data-ttu-id="92aaa-445">Kontraktslut</span><span class="sxs-lookup"><span data-stu-id="92aaa-445">End of Contract</span></span>  | <span data-ttu-id="92aaa-446">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="92aaa-446">Terminate worker</span></span>     |
| <span data-ttu-id="92aaa-447">LÖNEÄNDRING</span><span class="sxs-lookup"><span data-stu-id="92aaa-447">SALARYCHANGE</span></span>   | <span data-ttu-id="92aaa-448">Löneändring</span><span class="sxs-lookup"><span data-stu-id="92aaa-448">Change of Salary</span></span> | <span data-ttu-id="92aaa-449">Kompensation</span><span class="sxs-lookup"><span data-stu-id="92aaa-449">Compensation</span></span>         |

### <a name="marital-status"></a><span data-ttu-id="92aaa-450">Civilstånd</span><span class="sxs-lookup"><span data-stu-id="92aaa-450">Marital status</span></span>

<span data-ttu-id="92aaa-451">Civilståndsvärden mappas till Dayforce och översätts på lämpligt sätt till giltiga värden i samband med integrering.</span><span class="sxs-lookup"><span data-stu-id="92aaa-451">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="92aaa-452">Följande tabell visar hur civilståndsvärden mappas till Dayforce.</span><span class="sxs-lookup"><span data-stu-id="92aaa-452">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="92aaa-453">Personal</span><span class="sxs-lookup"><span data-stu-id="92aaa-453">Human Resources</span></span>                 | <span data-ttu-id="92aaa-454">Dayforce</span><span class="sxs-lookup"><span data-stu-id="92aaa-454">Dayforce</span></span>             |
|------------------------|----------------------|
| <span data-ttu-id="92aaa-455">Gift</span><span class="sxs-lookup"><span data-stu-id="92aaa-455">Married</span></span>                | <span data-ttu-id="92aaa-456">Gift</span><span class="sxs-lookup"><span data-stu-id="92aaa-456">Married</span></span>              |
| <span data-ttu-id="92aaa-457">Ett</span><span class="sxs-lookup"><span data-stu-id="92aaa-457">Single</span></span>                 | <span data-ttu-id="92aaa-458">Ett</span><span class="sxs-lookup"><span data-stu-id="92aaa-458">Single</span></span>               |
| <span data-ttu-id="92aaa-459">Änka/Änkeman</span><span class="sxs-lookup"><span data-stu-id="92aaa-459">Widowed</span></span>                | <span data-ttu-id="92aaa-460">Änka/Änkeman</span><span class="sxs-lookup"><span data-stu-id="92aaa-460">Widowed</span></span>              |
| <span data-ttu-id="92aaa-461">Skild</span><span class="sxs-lookup"><span data-stu-id="92aaa-461">Divorced</span></span>               | <span data-ttu-id="92aaa-462">Frånskild</span><span class="sxs-lookup"><span data-stu-id="92aaa-462">Divorced</span></span>             |
| <span data-ttu-id="92aaa-463">Registrerat partnerskap</span><span class="sxs-lookup"><span data-stu-id="92aaa-463">Registered Partnership</span></span> | <span data-ttu-id="92aaa-464">Samboförhållande</span><span class="sxs-lookup"><span data-stu-id="92aaa-464">Domestic Partnership</span></span> |
| <span data-ttu-id="92aaa-465">Inga</span><span class="sxs-lookup"><span data-stu-id="92aaa-465">None</span></span>                   | <span data-ttu-id="92aaa-466">Inga</span><span class="sxs-lookup"><span data-stu-id="92aaa-466">None</span></span>                 |
| <span data-ttu-id="92aaa-467">Sambo</span><span class="sxs-lookup"><span data-stu-id="92aaa-467">Cohabiting</span></span>             | <span data-ttu-id="92aaa-468">Sambo</span><span class="sxs-lookup"><span data-stu-id="92aaa-468">Cohabiting</span></span>           |

### <a name="gender"></a><span data-ttu-id="92aaa-469">Kön</span><span class="sxs-lookup"><span data-stu-id="92aaa-469">Gender</span></span>

<span data-ttu-id="92aaa-470">Könsbeteckningar mappas till Dayforce och översätts på lämpligt sätt till giltiga värden i samband med integrering.</span><span class="sxs-lookup"><span data-stu-id="92aaa-470">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="92aaa-471">Följande tabell visar hur könsbeteckningar mappas till Dayforce.</span><span class="sxs-lookup"><span data-stu-id="92aaa-471">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="92aaa-472">Personal</span><span class="sxs-lookup"><span data-stu-id="92aaa-472">Human Resources</span></span>       | <span data-ttu-id="92aaa-473">Dayforce</span><span class="sxs-lookup"><span data-stu-id="92aaa-473">Dayforce</span></span>        |
|--------------|-----------------|
| <span data-ttu-id="92aaa-474">Man</span><span class="sxs-lookup"><span data-stu-id="92aaa-474">Male</span></span>         | <span data-ttu-id="92aaa-475">Man</span><span class="sxs-lookup"><span data-stu-id="92aaa-475">Male</span></span>            |
| <span data-ttu-id="92aaa-476">Kvinna</span><span class="sxs-lookup"><span data-stu-id="92aaa-476">Female</span></span>       | <span data-ttu-id="92aaa-477">Kvinna</span><span class="sxs-lookup"><span data-stu-id="92aaa-477">Female</span></span>          |
| <span data-ttu-id="92aaa-478">Icke-specifik</span><span class="sxs-lookup"><span data-stu-id="92aaa-478">Non-specific</span></span> | <span data-ttu-id="92aaa-479">*Stöds ej*</span><span class="sxs-lookup"><span data-stu-id="92aaa-479">*Not supported*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="92aaa-480">Inkomstkoder</span><span class="sxs-lookup"><span data-stu-id="92aaa-480">Earning codes</span></span>

<span data-ttu-id="92aaa-481">Inkomstkoder identifierar individuellt alla typer av arbetstagarintäkter.</span><span class="sxs-lookup"><span data-stu-id="92aaa-481">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="92aaa-482">Koderna omfattar flera olika parametrar som rör inkomster, till exempel redovisningsbestämmelser, skattelagar, rapporteringskrav och gross up-kapacitet.</span><span class="sxs-lookup"><span data-stu-id="92aaa-482">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="92aaa-483">Om en frekvens som inte stöds används tillämpas frekvensen **Varje lön** som standard för beräkningen.</span><span class="sxs-lookup"><span data-stu-id="92aaa-483">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="92aaa-484">Frekvenser som stöds</span><span class="sxs-lookup"><span data-stu-id="92aaa-484">Supported frequencies</span></span>

- <span data-ttu-id="92aaa-485">Allt</span><span class="sxs-lookup"><span data-stu-id="92aaa-485">All</span></span>
- <span data-ttu-id="92aaa-486">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="92aaa-486">EVERYPAY</span></span>
- <span data-ttu-id="92aaa-487">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="92aaa-487">EACHPAYPERIOD</span></span>
- <span data-ttu-id="92aaa-488">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="92aaa-488">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="92aaa-489">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="92aaa-489">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="92aaa-490">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="92aaa-490">1OFMTH</span></span>
- <span data-ttu-id="92aaa-491">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="92aaa-491">LASTOFMTH</span></span>
- <span data-ttu-id="92aaa-492">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="92aaa-492">2OFMTH</span></span>
- <span data-ttu-id="92aaa-493">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="92aaa-493">3OFMTH</span></span>
- <span data-ttu-id="92aaa-494">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="92aaa-494">4OFMTH</span></span>
- <span data-ttu-id="92aaa-495">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="92aaa-495">5OFMTH</span></span>
- <span data-ttu-id="92aaa-496">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="92aaa-496">1N2OFMTH</span></span>
- <span data-ttu-id="92aaa-497">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="92aaa-497">3N4OFMTH</span></span>
- <span data-ttu-id="92aaa-498">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="92aaa-498">1N3OFMTH</span></span>
- <span data-ttu-id="92aaa-499">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="92aaa-499">1N4OFMTH</span></span>
- <span data-ttu-id="92aaa-500">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="92aaa-500">2N3OFMTH</span></span>
- <span data-ttu-id="92aaa-501">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="92aaa-501">2N4OFMTH</span></span>
- <span data-ttu-id="92aaa-502">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="92aaa-502">1N2N3OFMTH</span></span>
- <span data-ttu-id="92aaa-503">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="92aaa-503">1N2N4OFMTH</span></span>
- <span data-ttu-id="92aaa-504">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="92aaa-504">1N3N4OFMTH</span></span>
- <span data-ttu-id="92aaa-505">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="92aaa-505">2N3N4OFMTH</span></span>
- <span data-ttu-id="92aaa-506">1N2N3N4OFMTH – 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="92aaa-506">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="92aaa-507">2N3N4N5OFMth – 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="92aaa-507">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="92aaa-508">1OFQTR – 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="92aaa-508">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="92aaa-509">LASTOFQTR – LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="92aaa-509">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="92aaa-510">LASTMTHOFQTR – LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="92aaa-510">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="92aaa-511">1OFYEAR – 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="92aaa-511">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="92aaa-512">LASTOFYEAR – LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="92aaa-512">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="92aaa-513">NOVNDECOFYEAR – NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="92aaa-513">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="92aaa-514">Adresser</span><span class="sxs-lookup"><span data-stu-id="92aaa-514">Addresses</span></span>

<span data-ttu-id="92aaa-515">Identifiering av specifika lands-/region-, delstats- och region(kommun)-koder kräver särskilda format som Dayforce och leverantörer i respektive land/region kan känna igen.</span><span class="sxs-lookup"><span data-stu-id="92aaa-515">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="92aaa-516">Även om formatet för städer är flexibelt måste varje stad associeras med en delstat.</span><span class="sxs-lookup"><span data-stu-id="92aaa-516">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="92aaa-517">Personal</span><span class="sxs-lookup"><span data-stu-id="92aaa-517">Human Resources</span></span>          | <span data-ttu-id="92aaa-518">Dayforce</span><span class="sxs-lookup"><span data-stu-id="92aaa-518">Dayforce</span></span>              |
|-----------------|-----------------------|
| <span data-ttu-id="92aaa-519">Land/region</span><span class="sxs-lookup"><span data-stu-id="92aaa-519">Country/Region</span></span>  | <span data-ttu-id="92aaa-520">Landskod</span><span class="sxs-lookup"><span data-stu-id="92aaa-520">Country Code</span></span>          |
| <span data-ttu-id="92aaa-521">Postnummer</span><span class="sxs-lookup"><span data-stu-id="92aaa-521">Zip/Postal Code</span></span> | <span data-ttu-id="92aaa-522">Postnummer</span><span class="sxs-lookup"><span data-stu-id="92aaa-522">Postal Code</span></span>           |
| <span data-ttu-id="92aaa-523">Stat</span><span class="sxs-lookup"><span data-stu-id="92aaa-523">State</span></span>           | <span data-ttu-id="92aaa-524">Delstatskod</span><span class="sxs-lookup"><span data-stu-id="92aaa-524">State Code</span></span>            |
| <span data-ttu-id="92aaa-525">Ort</span><span class="sxs-lookup"><span data-stu-id="92aaa-525">City</span></span>            | <span data-ttu-id="92aaa-526">Ort</span><span class="sxs-lookup"><span data-stu-id="92aaa-526">City</span></span>                  |
| <span data-ttu-id="92aaa-527">Län</span><span class="sxs-lookup"><span data-stu-id="92aaa-527">County</span></span>          | <span data-ttu-id="92aaa-528">Region (kommun)</span><span class="sxs-lookup"><span data-stu-id="92aaa-528">County (Municipality)</span></span> |
| <span data-ttu-id="92aaa-529">Gata</span><span class="sxs-lookup"><span data-stu-id="92aaa-529">Street</span></span>          | <span data-ttu-id="92aaa-530">Adressrad 1</span><span class="sxs-lookup"><span data-stu-id="92aaa-530">Address Line 1</span></span>        |

### <a name="tax-regions"></a><span data-ttu-id="92aaa-531">Skatteregioner</span><span class="sxs-lookup"><span data-stu-id="92aaa-531">Tax regions</span></span>

<span data-ttu-id="92aaa-532">Skatteregioner används för att bestämma vilken skattesats som ska användas vid lönegenerering.</span><span class="sxs-lookup"><span data-stu-id="92aaa-532">Tax regions are used to determine the appropriate tax that should be applied during payroll generation.</span></span> <span data-ttu-id="92aaa-533">Skatteregioner mappas till Dayforce som platsadresser.</span><span class="sxs-lookup"><span data-stu-id="92aaa-533">Tax regions are mapped to Dayforce as location addresses.</span></span> <span data-ttu-id="92aaa-534">Förvald skatteregion måste associeras med medarbetarens aktiva befattning.</span><span class="sxs-lookup"><span data-stu-id="92aaa-534">The default tax region must be associated with the worker's active position.</span></span> 

- <span data-ttu-id="92aaa-535">Skatteregion (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="92aaa-535">Tax region (required)</span></span>
- <span data-ttu-id="92aaa-536">Land/region (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="92aaa-536">Country/Region (required)</span></span>
- <span data-ttu-id="92aaa-537">Delstat (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="92aaa-537">State (required)</span></span>
- <span data-ttu-id="92aaa-538">Län</span><span class="sxs-lookup"><span data-stu-id="92aaa-538">County</span></span> 
- <span data-ttu-id="92aaa-539">Stad (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="92aaa-539">City (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-mexico"></a><span data-ttu-id="92aaa-540">Konfigurera dina data för att generera lön i Mexiko</span><span class="sxs-lookup"><span data-stu-id="92aaa-540">Configure your data to generate payroll in Mexico</span></span>

<span data-ttu-id="92aaa-541">Om du genererar lön för medarbetare i Mexiko måste följande element konfigureras:</span><span class="sxs-lookup"><span data-stu-id="92aaa-541">If you're generating pay for employees in Mexico, the following elements must be configured:</span></span>

- <span data-ttu-id="92aaa-542">Avdelningar är obligatoriska vid befattningarna:</span><span class="sxs-lookup"><span data-stu-id="92aaa-542">Departments are required on positions.</span></span>
- <span data-ttu-id="92aaa-543">Kostnadsställen måste ställas in som ekonomiska dimensioner och måste vara det första elementet i standardsträngen för ekonomisk dimension.</span><span class="sxs-lookup"><span data-stu-id="92aaa-543">Cost centers must be set as financial dimensions and must be the first element in the Default Financial Dimension string.</span></span>

### <a name="job-types"></a><span data-ttu-id="92aaa-544">Jobbtyper</span><span class="sxs-lookup"><span data-stu-id="92aaa-544">Job types</span></span>

<span data-ttu-id="92aaa-545">Jobbtyper används för att gruppera liknande jobb i kategorier.</span><span class="sxs-lookup"><span data-stu-id="92aaa-545">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="92aaa-546">Jobbtyper krävs för att bearbeta löner i Mexiko.</span><span class="sxs-lookup"><span data-stu-id="92aaa-546">Job types are required in order to process payroll in Mexico.</span></span> <span data-ttu-id="92aaa-547">Några exempel på jobbtyper är heltid och deltid, eller fast lön och timpenning.</span><span class="sxs-lookup"><span data-stu-id="92aaa-547">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="92aaa-548">Jobbtyper mappas till Dayforce som lönetyper som anger huruvida en anställd arbetar per timme eller har fast lön.</span><span class="sxs-lookup"><span data-stu-id="92aaa-548">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="92aaa-549">Följande jobbtyper och beskrivningar krävs.</span><span class="sxs-lookup"><span data-stu-id="92aaa-549">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="92aaa-550">Jobbtyp</span><span class="sxs-lookup"><span data-stu-id="92aaa-550">Job type</span></span>   | <span data-ttu-id="92aaa-551">beskrivning</span><span class="sxs-lookup"><span data-stu-id="92aaa-551">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="92aaa-552">Varje timme</span><span class="sxs-lookup"><span data-stu-id="92aaa-552">Hourly</span></span>     | <span data-ttu-id="92aaa-553">MX Varje timme</span><span class="sxs-lookup"><span data-stu-id="92aaa-553">MX Hourly</span></span>   |
| <span data-ttu-id="92aaa-554">Fast lön</span><span class="sxs-lookup"><span data-stu-id="92aaa-554">Salaried</span></span>   | <span data-ttu-id="92aaa-555">MX Fast lön</span><span class="sxs-lookup"><span data-stu-id="92aaa-555">MX Salaried</span></span> |

### <a name="position-types"></a><span data-ttu-id="92aaa-556">Befattningstyper</span><span class="sxs-lookup"><span data-stu-id="92aaa-556">Position types</span></span> 

<span data-ttu-id="92aaa-557">Du kan använda befattningstyper för att beskriva huruvida befattningen är på heltid, deltid eller annat.</span><span class="sxs-lookup"><span data-stu-id="92aaa-557">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="92aaa-558">Befattningstyper mappas till Dayforce som löneklasser som anger huruvida en anställd arbetar heltid eller deltid.</span><span class="sxs-lookup"><span data-stu-id="92aaa-558">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="92aaa-559">Följande befattningstyper och beskrivningar krävs.</span><span class="sxs-lookup"><span data-stu-id="92aaa-559">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="92aaa-560">Befattningstyp</span><span class="sxs-lookup"><span data-stu-id="92aaa-560">Position type</span></span>   | <span data-ttu-id="92aaa-561">beskrivning</span><span class="sxs-lookup"><span data-stu-id="92aaa-561">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="92aaa-562">Heltid</span><span class="sxs-lookup"><span data-stu-id="92aaa-562">Full-time</span></span>       | <span data-ttu-id="92aaa-563">Heltidsanställd</span><span class="sxs-lookup"><span data-stu-id="92aaa-563">Full time employee</span></span> |
| <span data-ttu-id="92aaa-564">Deltid</span><span class="sxs-lookup"><span data-stu-id="92aaa-564">Part-time</span></span>       | <span data-ttu-id="92aaa-565">Deltidsanställd</span><span class="sxs-lookup"><span data-stu-id="92aaa-565">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="92aaa-566">Orsakskoder</span><span class="sxs-lookup"><span data-stu-id="92aaa-566">Reason codes</span></span>

<span data-ttu-id="92aaa-567">Orsakskoder innehåller information om statusen för en medarbetare.</span><span class="sxs-lookup"><span data-stu-id="92aaa-567">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="92aaa-568">Orsakskoder mappas till Dayforce som statusanledningar som anger orsaken till ändringar i en medarbetares befattning eller anställningsstatus.</span><span class="sxs-lookup"><span data-stu-id="92aaa-568">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="92aaa-569">Följande orsakskoder och -beskrivningar krävs.</span><span class="sxs-lookup"><span data-stu-id="92aaa-569">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="92aaa-570">Orsakskod</span><span class="sxs-lookup"><span data-stu-id="92aaa-570">Reason code</span></span>            | <span data-ttu-id="92aaa-571">beskrivning</span><span class="sxs-lookup"><span data-stu-id="92aaa-571">Description</span></span>                    | <span data-ttu-id="92aaa-572">Tillämpliga scenarier</span><span class="sxs-lookup"><span data-stu-id="92aaa-572">Applicable scenarios</span></span> |
|------------------------|--------------------------------|----------------------|
| <span data-ttu-id="92aaa-573">DEPARTUREBEFOREPAYMENT</span><span class="sxs-lookup"><span data-stu-id="92aaa-573">DEPARTUREBEFOREPAYMENT</span></span> | <span data-ttu-id="92aaa-574">Avgick före första lön</span><span class="sxs-lookup"><span data-stu-id="92aaa-574">Departure before first payroll</span></span> | <span data-ttu-id="92aaa-575">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="92aaa-575">Terminate worker</span></span>     |
| <span data-ttu-id="92aaa-576">EGEN UPPSÄGNING</span><span class="sxs-lookup"><span data-stu-id="92aaa-576">RESIGNATION</span></span>            | <span data-ttu-id="92aaa-577">Egen uppsägning</span><span class="sxs-lookup"><span data-stu-id="92aaa-577">Resignation</span></span>                    | <span data-ttu-id="92aaa-578">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="92aaa-578">Terminate worker</span></span>     |
| <span data-ttu-id="92aaa-579">PENSION</span><span class="sxs-lookup"><span data-stu-id="92aaa-579">PENSION</span></span>                | <span data-ttu-id="92aaa-580">Pension</span><span class="sxs-lookup"><span data-stu-id="92aaa-580">Pension</span></span>                        | <span data-ttu-id="92aaa-581">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="92aaa-581">Terminate worker</span></span>     |
| <span data-ttu-id="92aaa-582">UPPSÄGNING</span><span class="sxs-lookup"><span data-stu-id="92aaa-582">TERMINATION</span></span>            | <span data-ttu-id="92aaa-583">Uppsägning</span><span class="sxs-lookup"><span data-stu-id="92aaa-583">Termination</span></span>                    | <span data-ttu-id="92aaa-584">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="92aaa-584">Terminate worker</span></span>     |
| <span data-ttu-id="92aaa-585">PENSION</span><span class="sxs-lookup"><span data-stu-id="92aaa-585">RETIREMENT</span></span>             | <span data-ttu-id="92aaa-586">Pension</span><span class="sxs-lookup"><span data-stu-id="92aaa-586">Retirement</span></span>                     | <span data-ttu-id="92aaa-587">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="92aaa-587">Terminate worker</span></span>     |
| <span data-ttu-id="92aaa-588">FRÅNVARANDE</span><span class="sxs-lookup"><span data-stu-id="92aaa-588">ABSENTEE</span></span>               | <span data-ttu-id="92aaa-589">Frånvarande</span><span class="sxs-lookup"><span data-stu-id="92aaa-589">Absentee</span></span>                       | <span data-ttu-id="92aaa-590">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="92aaa-590">Terminate worker</span></span>     |
| <span data-ttu-id="92aaa-591">ÖVRIGT</span><span class="sxs-lookup"><span data-stu-id="92aaa-591">OTHER</span></span>                  | <span data-ttu-id="92aaa-592">Andra orsaker</span><span class="sxs-lookup"><span data-stu-id="92aaa-592">Other Reasons</span></span>                  | <span data-ttu-id="92aaa-593">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="92aaa-593">Terminate worker</span></span>     |
| <span data-ttu-id="92aaa-594">AVSLUT</span><span class="sxs-lookup"><span data-stu-id="92aaa-594">CLOSURE</span></span>                | <span data-ttu-id="92aaa-595">Verksamheten nedlagd</span><span class="sxs-lookup"><span data-stu-id="92aaa-595">Business Closure</span></span>               | <span data-ttu-id="92aaa-596">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="92aaa-596">Terminate worker</span></span>     |
| <span data-ttu-id="92aaa-597">DÖDSFALL</span><span class="sxs-lookup"><span data-stu-id="92aaa-597">DEATH</span></span>                  | <span data-ttu-id="92aaa-598">Dödsfall</span><span class="sxs-lookup"><span data-stu-id="92aaa-598">Death</span></span>                          | <span data-ttu-id="92aaa-599">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="92aaa-599">Terminate worker</span></span>     |
| <span data-ttu-id="92aaa-600">TJÄNSTLEDIGHET</span><span class="sxs-lookup"><span data-stu-id="92aaa-600">LEAVEOFABSENCE</span></span>         | <span data-ttu-id="92aaa-601">Tjänstledighet</span><span class="sxs-lookup"><span data-stu-id="92aaa-601">Leave of Absence</span></span>               | <span data-ttu-id="92aaa-602">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="92aaa-602">Terminate worker</span></span>     |
| <span data-ttu-id="92aaa-603">KONTRAKTSLUT</span><span class="sxs-lookup"><span data-stu-id="92aaa-603">CONTRACTEND</span></span>            | <span data-ttu-id="92aaa-604">Kontraktslut</span><span class="sxs-lookup"><span data-stu-id="92aaa-604">End of Contract</span></span>                | <span data-ttu-id="92aaa-605">Säg upp arbetare</span><span class="sxs-lookup"><span data-stu-id="92aaa-605">Terminate worker</span></span>     |
| <span data-ttu-id="92aaa-606">LÖNEÄNDRING</span><span class="sxs-lookup"><span data-stu-id="92aaa-606">SALARYCHANGE</span></span>           | <span data-ttu-id="92aaa-607">Löneändring</span><span class="sxs-lookup"><span data-stu-id="92aaa-607">Change of Salary</span></span>               | <span data-ttu-id="92aaa-608">Kompensation</span><span class="sxs-lookup"><span data-stu-id="92aaa-608">Compensation</span></span>         |

### <a name="terms-of-employment"></a><span data-ttu-id="92aaa-609">Anställningsvillkor</span><span class="sxs-lookup"><span data-stu-id="92aaa-609">Terms of employment</span></span>

<span data-ttu-id="92aaa-610">Anställningsvillkor används för att skapa kategorier av anställningsvillkor.</span><span class="sxs-lookup"><span data-stu-id="92aaa-610">Terms of employment are used to create categories of employment terms.</span></span> <span data-ttu-id="92aaa-611">Villkoren mappas till Dayforce som indikatorvärden för anställning.</span><span class="sxs-lookup"><span data-stu-id="92aaa-611">The terms are mapped to Dayforce as employment indicator values.</span></span>

<span data-ttu-id="92aaa-612">Följande anställningsvillkor samt beskrivningar krävs.</span><span class="sxs-lookup"><span data-stu-id="92aaa-612">The following terms of employment and descriptions are required.</span></span>

| <span data-ttu-id="92aaa-613">Anställningsvillkor</span><span class="sxs-lookup"><span data-stu-id="92aaa-613">Terms of employment</span></span>   | <span data-ttu-id="92aaa-614">beskrivning</span><span class="sxs-lookup"><span data-stu-id="92aaa-614">Description</span></span> |
|-----------------------|-------------|
| <span data-ttu-id="92aaa-615">Vanligt</span><span class="sxs-lookup"><span data-stu-id="92aaa-615">Regular</span></span>               | <span data-ttu-id="92aaa-616">Vanligt</span><span class="sxs-lookup"><span data-stu-id="92aaa-616">Regular</span></span>     |
| <span data-ttu-id="92aaa-617">Direkt</span><span class="sxs-lookup"><span data-stu-id="92aaa-617">Direct</span></span>                | <span data-ttu-id="92aaa-618">Direkt</span><span class="sxs-lookup"><span data-stu-id="92aaa-618">Direct</span></span>      |
| <span data-ttu-id="92aaa-619">Praktik</span><span class="sxs-lookup"><span data-stu-id="92aaa-619">Internship</span></span>            | <span data-ttu-id="92aaa-620">Praktik</span><span class="sxs-lookup"><span data-stu-id="92aaa-620">Internship</span></span>  |
| <span data-ttu-id="92aaa-621">Permanent</span><span class="sxs-lookup"><span data-stu-id="92aaa-621">Permanent</span></span>             | <span data-ttu-id="92aaa-622">Permanent</span><span class="sxs-lookup"><span data-stu-id="92aaa-622">Permanent</span></span>   |

### <a name="marital-status"></a><span data-ttu-id="92aaa-623">Civilstånd</span><span class="sxs-lookup"><span data-stu-id="92aaa-623">Marital status</span></span>

<span data-ttu-id="92aaa-624">Civilståndsvärden mappas till Dayforce och översätts på lämpligt sätt till giltiga värden i samband med integrering.</span><span class="sxs-lookup"><span data-stu-id="92aaa-624">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="92aaa-625">Följande tabell visar hur civilståndsvärden mappas till Dayforce.</span><span class="sxs-lookup"><span data-stu-id="92aaa-625">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="92aaa-626">Personal</span><span class="sxs-lookup"><span data-stu-id="92aaa-626">Human Resources</span></span>                 | <span data-ttu-id="92aaa-627">Dayforce</span><span class="sxs-lookup"><span data-stu-id="92aaa-627">Dayforce</span></span>                  |
|------------------------|---------------------------|
| <span data-ttu-id="92aaa-628">Gift</span><span class="sxs-lookup"><span data-stu-id="92aaa-628">Married</span></span>                | <span data-ttu-id="92aaa-629">Gift</span><span class="sxs-lookup"><span data-stu-id="92aaa-629">Married</span></span>                   |
| <span data-ttu-id="92aaa-630">Ett</span><span class="sxs-lookup"><span data-stu-id="92aaa-630">Single</span></span>                 | <span data-ttu-id="92aaa-631">Ett</span><span class="sxs-lookup"><span data-stu-id="92aaa-631">Single</span></span>                    |
| <span data-ttu-id="92aaa-632">Änka/Änkeman</span><span class="sxs-lookup"><span data-stu-id="92aaa-632">Widowed</span></span>                | <span data-ttu-id="92aaa-633">Änka/Änkeman</span><span class="sxs-lookup"><span data-stu-id="92aaa-633">Widowed</span></span>                   |
| <span data-ttu-id="92aaa-634">Skild</span><span class="sxs-lookup"><span data-stu-id="92aaa-634">Divorced</span></span>               | <span data-ttu-id="92aaa-635">Frånskild</span><span class="sxs-lookup"><span data-stu-id="92aaa-635">Divorced</span></span>                  |
| <span data-ttu-id="92aaa-636">Registrerat partnerskap</span><span class="sxs-lookup"><span data-stu-id="92aaa-636">Registered Partnership</span></span> | <span data-ttu-id="92aaa-637">Samboförhållande</span><span class="sxs-lookup"><span data-stu-id="92aaa-637">Domestic Partnership</span></span>      |
| <span data-ttu-id="92aaa-638">Inga</span><span class="sxs-lookup"><span data-stu-id="92aaa-638">None</span></span>                   | <span data-ttu-id="92aaa-639">*Stöds inte i Mexiko*</span><span class="sxs-lookup"><span data-stu-id="92aaa-639">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="92aaa-640">Sambo</span><span class="sxs-lookup"><span data-stu-id="92aaa-640">Cohabiting</span></span>             | <span data-ttu-id="92aaa-641">*Stöds inte i Mexiko*</span><span class="sxs-lookup"><span data-stu-id="92aaa-641">*Not supported by Mexico*</span></span> |

### <a name="gender"></a><span data-ttu-id="92aaa-642">Kön</span><span class="sxs-lookup"><span data-stu-id="92aaa-642">Gender</span></span>

<span data-ttu-id="92aaa-643">Könsbeteckningar mappas till Dayforce och översätts på lämpligt sätt till giltiga värden i samband med integrering.</span><span class="sxs-lookup"><span data-stu-id="92aaa-643">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="92aaa-644">Följande tabell visar hur könsbeteckningar mappas till Dayforce.</span><span class="sxs-lookup"><span data-stu-id="92aaa-644">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="92aaa-645">Personal</span><span class="sxs-lookup"><span data-stu-id="92aaa-645">Human Resources</span></span>       | <span data-ttu-id="92aaa-646">Dayforce</span><span class="sxs-lookup"><span data-stu-id="92aaa-646">Dayforce</span></span>                  |
|--------------|---------------------------|
| <span data-ttu-id="92aaa-647">Man</span><span class="sxs-lookup"><span data-stu-id="92aaa-647">Male</span></span>         | <span data-ttu-id="92aaa-648">Man</span><span class="sxs-lookup"><span data-stu-id="92aaa-648">Male</span></span>                      |
| <span data-ttu-id="92aaa-649">Kvinna</span><span class="sxs-lookup"><span data-stu-id="92aaa-649">Female</span></span>       | <span data-ttu-id="92aaa-650">Kvinna</span><span class="sxs-lookup"><span data-stu-id="92aaa-650">Female</span></span>                    |
| <span data-ttu-id="92aaa-651">Icke-specifik</span><span class="sxs-lookup"><span data-stu-id="92aaa-651">Non-specific</span></span> | <span data-ttu-id="92aaa-652">*Stöds inte i Mexiko*</span><span class="sxs-lookup"><span data-stu-id="92aaa-652">*Not supported by Mexico*</span></span> |

### <a name="payment-method"></a><span data-ttu-id="92aaa-653">Betalningsmetod</span><span class="sxs-lookup"><span data-stu-id="92aaa-653">Payment method</span></span>

<span data-ttu-id="92aaa-654">Betalsätt ger medarbetare och företag ett sätt att beskriva hur medarbetaren ska betalas.</span><span class="sxs-lookup"><span data-stu-id="92aaa-654">Payment methods give the employee and the company a way to describe how employees will be paid.</span></span> <span data-ttu-id="92aaa-655">Betalsätt mappas till Dayforce och översätts på lämpligt sätt till giltiga värden i samband med integrering.</span><span class="sxs-lookup"><span data-stu-id="92aaa-655">Payment methods are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="92aaa-656">Följande tabell visar hur betalsätt mappas till Dayforce.</span><span class="sxs-lookup"><span data-stu-id="92aaa-656">The following table shows how payment methods are mapped to Dayforce.</span></span>

| <span data-ttu-id="92aaa-657">Personal</span><span class="sxs-lookup"><span data-stu-id="92aaa-657">Human Resources</span></span>             | <span data-ttu-id="92aaa-658">Dayforce</span><span class="sxs-lookup"><span data-stu-id="92aaa-658">Dayforce</span></span>                  |
|--------------------|---------------------------|
| <span data-ttu-id="92aaa-659">Kontant</span><span class="sxs-lookup"><span data-stu-id="92aaa-659">Cash</span></span>               | <span data-ttu-id="92aaa-660">Kontant</span><span class="sxs-lookup"><span data-stu-id="92aaa-660">Cash</span></span>                      |
| <span data-ttu-id="92aaa-661">Elektronisk betalning</span><span class="sxs-lookup"><span data-stu-id="92aaa-661">Electronic Payment</span></span> | <span data-ttu-id="92aaa-662">Överför</span><span class="sxs-lookup"><span data-stu-id="92aaa-662">Transfer</span></span>                  |
| <span data-ttu-id="92aaa-663">Check</span><span class="sxs-lookup"><span data-stu-id="92aaa-663">Check</span></span>              | <span data-ttu-id="92aaa-664">Check</span><span class="sxs-lookup"><span data-stu-id="92aaa-664">Cheque</span></span>                    |
| <span data-ttu-id="92aaa-665">Bankutdrag</span><span class="sxs-lookup"><span data-stu-id="92aaa-665">Bank Draft</span></span>         | <span data-ttu-id="92aaa-666">*Stöds inte i Mexiko*</span><span class="sxs-lookup"><span data-stu-id="92aaa-666">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="92aaa-667">Annat</span><span class="sxs-lookup"><span data-stu-id="92aaa-667">Other</span></span>              | <span data-ttu-id="92aaa-668">*Stöds inte i Mexiko*</span><span class="sxs-lookup"><span data-stu-id="92aaa-668">*Not supported by Mexico*</span></span> |

### <a name="bank-account-type"></a><span data-ttu-id="92aaa-669">Bankkontotyp</span><span class="sxs-lookup"><span data-stu-id="92aaa-669">Bank account type</span></span>

<span data-ttu-id="92aaa-670">Bankkontotyper används för elektroniska betalningar till medarbetare.</span><span class="sxs-lookup"><span data-stu-id="92aaa-670">Bank account types are used for electronic payments to employees.</span></span> <span data-ttu-id="92aaa-671">Bankkontotyper mappas till Dayforce som kontoinformation för överföringar.</span><span class="sxs-lookup"><span data-stu-id="92aaa-671">Bank account types are mapped to Dayforce as transfer account information.</span></span> <span data-ttu-id="92aaa-672">Bankkontotyper översätts på lämpligt till giltiga värden i samband med integrering.</span><span class="sxs-lookup"><span data-stu-id="92aaa-672">The bank account types are translated, as appropriate, to the accepted values upon integration.</span></span>

| <span data-ttu-id="92aaa-673">Personal</span><span class="sxs-lookup"><span data-stu-id="92aaa-673">Human Resources</span></span>            | <span data-ttu-id="92aaa-674">Dayforce</span><span class="sxs-lookup"><span data-stu-id="92aaa-674">Dayforce</span></span>                  |
|-------------------|---------------------------|
| <span data-ttu-id="92aaa-675">Checkkonto</span><span class="sxs-lookup"><span data-stu-id="92aaa-675">Checking Account</span></span>  | <span data-ttu-id="92aaa-676">Checkkonto</span><span class="sxs-lookup"><span data-stu-id="92aaa-676">CheckingAccount</span></span>           |
| <span data-ttu-id="92aaa-677">Lönekonto</span><span class="sxs-lookup"><span data-stu-id="92aaa-677">Payroll Account</span></span>   | <span data-ttu-id="92aaa-678">Lönekonto</span><span class="sxs-lookup"><span data-stu-id="92aaa-678">PayrollAccount</span></span>            |
| <span data-ttu-id="92aaa-679">Sparkonto</span><span class="sxs-lookup"><span data-stu-id="92aaa-679">Savings Account</span></span>   | <span data-ttu-id="92aaa-680">*Stöds inte i Mexiko*</span><span class="sxs-lookup"><span data-stu-id="92aaa-680">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="92aaa-681">BankGirot-konto</span><span class="sxs-lookup"><span data-stu-id="92aaa-681">BankGirot account</span></span> | <span data-ttu-id="92aaa-682">*Stöds inte i Mexiko*</span><span class="sxs-lookup"><span data-stu-id="92aaa-682">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="92aaa-683">PlusGirot-konto</span><span class="sxs-lookup"><span data-stu-id="92aaa-683">PlusGirot account</span></span> | <span data-ttu-id="92aaa-684">*Stöds inte i Mexiko*</span><span class="sxs-lookup"><span data-stu-id="92aaa-684">*Not supported by Mexico*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="92aaa-685">Inkomstkoder</span><span class="sxs-lookup"><span data-stu-id="92aaa-685">Earning codes</span></span>

<span data-ttu-id="92aaa-686">Inkomstkoder identifierar individuellt alla typer av arbetstagarintäkter.</span><span class="sxs-lookup"><span data-stu-id="92aaa-686">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="92aaa-687">Koderna omfattar flera olika parametrar som rör inkomster, till exempel redovisningsbestämmelser, skattelagar, rapporteringskrav och gross up-kapacitet.</span><span class="sxs-lookup"><span data-stu-id="92aaa-687">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="92aaa-688">Om en frekvens som inte stöds används tillämpas frekvensen **Varje lön** som standard för beräkningen.</span><span class="sxs-lookup"><span data-stu-id="92aaa-688">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="92aaa-689">Frekvenser som stöds</span><span class="sxs-lookup"><span data-stu-id="92aaa-689">Supported frequencies</span></span>

- <span data-ttu-id="92aaa-690">Allt</span><span class="sxs-lookup"><span data-stu-id="92aaa-690">All</span></span>
- <span data-ttu-id="92aaa-691">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="92aaa-691">EVERYPAY</span></span>
- <span data-ttu-id="92aaa-692">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="92aaa-692">EACHPAYPERIOD</span></span>
- <span data-ttu-id="92aaa-693">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="92aaa-693">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="92aaa-694">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="92aaa-694">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="92aaa-695">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="92aaa-695">1OFMTH</span></span>
- <span data-ttu-id="92aaa-696">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="92aaa-696">LASTOFMTH</span></span>
- <span data-ttu-id="92aaa-697">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="92aaa-697">2OFMTH</span></span>
- <span data-ttu-id="92aaa-698">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="92aaa-698">3OFMTH</span></span>
- <span data-ttu-id="92aaa-699">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="92aaa-699">4OFMTH</span></span>
- <span data-ttu-id="92aaa-700">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="92aaa-700">5OFMTH</span></span>
- <span data-ttu-id="92aaa-701">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="92aaa-701">1N2OFMTH</span></span>
- <span data-ttu-id="92aaa-702">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="92aaa-702">3N4OFMTH</span></span>
- <span data-ttu-id="92aaa-703">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="92aaa-703">1N3OFMTH</span></span>
- <span data-ttu-id="92aaa-704">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="92aaa-704">1N4OFMTH</span></span>
- <span data-ttu-id="92aaa-705">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="92aaa-705">2N3OFMTH</span></span>
- <span data-ttu-id="92aaa-706">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="92aaa-706">2N4OFMTH</span></span>
- <span data-ttu-id="92aaa-707">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="92aaa-707">1N2N3OFMTH</span></span>
- <span data-ttu-id="92aaa-708">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="92aaa-708">1N2N4OFMTH</span></span>
- <span data-ttu-id="92aaa-709">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="92aaa-709">1N3N4OFMTH</span></span>
- <span data-ttu-id="92aaa-710">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="92aaa-710">2N3N4OFMTH</span></span>
- <span data-ttu-id="92aaa-711">1N2N3N4OFMTH – 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="92aaa-711">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="92aaa-712">2N3N4N5OFMth – 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="92aaa-712">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="92aaa-713">1OFQTR – 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="92aaa-713">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="92aaa-714">LASTOFQTR – LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="92aaa-714">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="92aaa-715">LASTMTHOFQTR – LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="92aaa-715">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="92aaa-716">1OFYEAR – 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="92aaa-716">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="92aaa-717">LASTOFYEAR – LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="92aaa-717">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="92aaa-718">NOVNDECOFYEAR – NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="92aaa-718">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="92aaa-719">Adresser</span><span class="sxs-lookup"><span data-stu-id="92aaa-719">Addresses</span></span>

<span data-ttu-id="92aaa-720">Identifiering av specifika lands-/region-, delstats- och region(kommun)-koder kräver särskilda format som Dayforce och leverantörer i respektive land/region kan känna igen.</span><span class="sxs-lookup"><span data-stu-id="92aaa-720">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="92aaa-721">Även om formatet för städer är flexibelt måste varje stad associeras med en delstat.</span><span class="sxs-lookup"><span data-stu-id="92aaa-721">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="92aaa-722">Personal</span><span class="sxs-lookup"><span data-stu-id="92aaa-722">Human Resources</span></span>              | <span data-ttu-id="92aaa-723">Dayforce</span><span class="sxs-lookup"><span data-stu-id="92aaa-723">Dayforce</span></span>              |
|---------------------|-----------------------|
| <span data-ttu-id="92aaa-724">Land/region</span><span class="sxs-lookup"><span data-stu-id="92aaa-724">Country/Region</span></span>      | <span data-ttu-id="92aaa-725">Landskod</span><span class="sxs-lookup"><span data-stu-id="92aaa-725">Country Code</span></span>          |
| <span data-ttu-id="92aaa-726">Postnummer</span><span class="sxs-lookup"><span data-stu-id="92aaa-726">Zip/Postal Code</span></span>     | <span data-ttu-id="92aaa-727">Postnummer</span><span class="sxs-lookup"><span data-stu-id="92aaa-727">Postal Code</span></span>           |
| <span data-ttu-id="92aaa-728">Stat</span><span class="sxs-lookup"><span data-stu-id="92aaa-728">State</span></span>               | <span data-ttu-id="92aaa-729">Delstatskod</span><span class="sxs-lookup"><span data-stu-id="92aaa-729">State Code</span></span>            |
| <span data-ttu-id="92aaa-730">Ort</span><span class="sxs-lookup"><span data-stu-id="92aaa-730">City</span></span>                | <span data-ttu-id="92aaa-731">Ort</span><span class="sxs-lookup"><span data-stu-id="92aaa-731">City</span></span>                  |
| <span data-ttu-id="92aaa-732">Län</span><span class="sxs-lookup"><span data-stu-id="92aaa-732">County</span></span>              | <span data-ttu-id="92aaa-733">Region (kommun)</span><span class="sxs-lookup"><span data-stu-id="92aaa-733">County (Municipality)</span></span> |
| <span data-ttu-id="92aaa-734">Gata</span><span class="sxs-lookup"><span data-stu-id="92aaa-734">Street</span></span>              | <span data-ttu-id="92aaa-735">Adressrad 1</span><span class="sxs-lookup"><span data-stu-id="92aaa-735">Address Line 1</span></span>        |
| <span data-ttu-id="92aaa-736">Gatunummer</span><span class="sxs-lookup"><span data-stu-id="92aaa-736">Street Number</span></span>       | <span data-ttu-id="92aaa-737">Adressrad 2</span><span class="sxs-lookup"><span data-stu-id="92aaa-737">Address Line 2</span></span>        |
| <span data-ttu-id="92aaa-738">Byggnadskomplement</span><span class="sxs-lookup"><span data-stu-id="92aaa-738">Building Complement</span></span> | <span data-ttu-id="92aaa-739">Adressrad 5</span><span class="sxs-lookup"><span data-stu-id="92aaa-739">Address Line 5</span></span>        |

### <a name="passport-number"></a><span data-ttu-id="92aaa-740">Passnummer</span><span class="sxs-lookup"><span data-stu-id="92aaa-740">Passport number</span></span>

<span data-ttu-id="92aaa-741">Medarbetare kan deklarera passinformation.</span><span class="sxs-lookup"><span data-stu-id="92aaa-741">Employees can declare passport information.</span></span> <span data-ttu-id="92aaa-742">Denna information bär ID-typen **Pass** och integreras i Dayforce som en del av medarbetarens Mexikospecifika information.</span><span class="sxs-lookup"><span data-stu-id="92aaa-742">This information is of the **Passport** identification type and is integrated into Dayforce as part of an employee's Mexico-specific information.</span></span>

- <span data-ttu-id="92aaa-743">Identifieringstyp = "Pass"</span><span class="sxs-lookup"><span data-stu-id="92aaa-743">Identification Type = "Passport"</span></span>
- <span data-ttu-id="92aaa-744">Utfärdat den</span><span class="sxs-lookup"><span data-stu-id="92aaa-744">Issued Date</span></span>
- <span data-ttu-id="92aaa-745">Utgångsdatum</span><span class="sxs-lookup"><span data-stu-id="92aaa-745">Expiration Date</span></span>

<span data-ttu-id="92aaa-746">Medarbetare kan deklarera flera ID-nummer med ID-typen **Pass**.</span><span class="sxs-lookup"><span data-stu-id="92aaa-746">Employees can declare multiple identification numbers of the **Passport** identification type.</span></span> <span data-ttu-id="92aaa-747">Endast den aktuella passposten integreras emellertid i Dayforce.</span><span class="sxs-lookup"><span data-stu-id="92aaa-747">However, only the current active passport entry is integrated into Dayforce.</span></span> <span data-ttu-id="92aaa-748">Om alla passposter har upphört att gälla kommer det pass som är utfärdat senast att integreras i Dayforce.</span><span class="sxs-lookup"><span data-stu-id="92aaa-748">If all passport entries are expired, the passport that was most recently issued is integrated into Dayforce.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]