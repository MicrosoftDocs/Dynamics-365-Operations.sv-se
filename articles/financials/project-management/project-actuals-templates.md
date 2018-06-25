---
title: "Synkronisera projektets faktiska värden från Project Service Automation direkt till projektets integrationsjournal för bokföring i Finance and Operations "
description: "Det här avsnittet beskriver vilka mallar och underliggande uppgifter som används för att synkronisera projektets faktiska värden direkt från Microsoft Dynamics 365 for Project Service Automation till Dynamics 365 for Finance and Operations."
author: KimANelson
manager: AnnBe
ms.date: 05/21/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 7.3.0
ms.translationtype: HT
ms.sourcegitcommit: bd8feff598cf80ca675c7d2b5dda636799b19e29
ms.openlocfilehash: 85ff049852e0b00623f47a12fb66e2c9bb9c4151
ms.contentlocale: sv-se
ms.lasthandoff: 05/29/2018

---
# <a name="synchronize-project-actuals-from-project-service-automation-directly-to-the-project-integration-journal-for-posting-in-finance-and-operations"></a><span data-ttu-id="cccee-103">Synkronisera projektets faktiska värden från Project Service Automation direkt till projektets integrationsjournal för bokföring i Finance and Operations </span><span class="sxs-lookup"><span data-stu-id="cccee-103">Synchronize project actuals from Project Service Automation directly to the project integration journal for posting in Finance and Operations</span></span>

<span data-ttu-id="cccee-104">Det här avsnittet beskriver vilka mallar och underliggande uppgifter som används för att synkronisera projektets faktiska värden direkt från Microsoft Dynamics 365 for Project Service Automation till Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="cccee-104">This topic describes the templates and underlying tasks that are used to synchronize project actuals directly from Microsoft Dynamics 365 for Project Service Automation to Dynamics 365 for Finance and Operations.</span></span>

<span data-ttu-id="cccee-105">Mallen synkroniserar transaktionerna från Project Service Automation till ett mellanlagringsregister i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="cccee-105">The template syncs transactions from Project Service Automation into a staging table in Finance and Operations.</span></span> <span data-ttu-id="cccee-106">När synkroniseringen är klar måste du importera från mellanlagringsregistret till integrationsjournalen.</span><span class="sxs-lookup"><span data-stu-id="cccee-106">After synchronization is complete, you must import from the staging table to the integration journal.</span></span>

> [!NOTE]
> <span data-ttu-id="cccee-107">Integration av projektets verkliga värden finns i Dynamics 365 for Finance and Operations version 8.01.</span><span class="sxs-lookup"><span data-stu-id="cccee-107">Project actuals integration is available in Dynamics 365 for Finance and Operations version 8.01.</span></span>

> [!NOTE]
> <span data-ttu-id="cccee-108">Om du anger momsbelopp på tid eller utgifter i Project Service Automation, måste du installera Project Service Automation uppdatering 7.</span><span class="sxs-lookup"><span data-stu-id="cccee-108">If you are entering sales tax amounts on time or expense transactions in Project Service Automation, you must install the Project Service Automation Update 7.</span></span> <span data-ttu-id="cccee-109">Om uppdateringen inte har installerats kommer skattemässiga värden inte att kopplas till associerad tid eller verklig kostnad och kommer inte att synkroniseras inte med Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="cccee-109">If this update is not installed, the tax actuals will not be linked to the associated time or expense actuals and will not be synced to Finance and Operations.</span></span> <span data-ttu-id="cccee-110">Kontakta support för mer information.</span><span class="sxs-lookup"><span data-stu-id="cccee-110">Contact Support for more information.</span></span>


## <a name="data-flow-for-project-service-automation-to-finance-and-operations"></a><span data-ttu-id="cccee-111">Dataflöde för Project Service Automation till Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="cccee-111">Data flow for Project Service Automation to Finance and Operations</span></span>

<span data-ttu-id="cccee-112">Automatisering av integrationslösningen Project Service Automation till Finance and Operations använder funktionen dataintegration för att synkronisera data mellan instanser av Project Service Automation och Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="cccee-112">The Project Service Automation to Finance and Operations integration solution uses the Data integration feature to synchronize data across instances of Project Service Automation and Finance and Operations.</span></span> <span data-ttu-id="cccee-113">Integrationsmallen som är tillgänglig med dataintegrationsfunktionen möjliggör flödet av data om projektets faktiska värden från Project Service Automation till Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="cccee-113">The integration templates that are available with the Data integration feature enable the flow of data about project actuals from Project Service Automation to Finance and Operations.</span></span>

<span data-ttu-id="cccee-114">Följande bild visar hur data synkroniseras mellan Project Service Automation och Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="cccee-114">The following illustration shows how the data is synchronized between Project Service Automation and Finance and Operations.</span></span>

<span data-ttu-id="cccee-115">[![Dataflöde för integration av Project Service Automation med Finance and Operations](./media/ProjectActualsFlow.jpg)](./media/ProjectActualsFlow.jpg)</span><span class="sxs-lookup"><span data-stu-id="cccee-115">[![Data flow for Project Service Automation integration with Finance and Operations](./media/ProjectActualsFlow.jpg)](./media/ProjectActualsFlow.jpg)</span></span>


## <a name="templates-and-tasks"></a><span data-ttu-id="cccee-116">Mallar och uppgifter</span><span class="sxs-lookup"><span data-stu-id="cccee-116">Templates and tasks</span></span>

<span data-ttu-id="cccee-117">För att få åtkomst till tillgängliga mallar, i Microsoft PowerApps administratörscenter, välj **projekt**, och i det övre högra hörnet väljer du **nytt projekt** för att välja offentliga mallar.</span><span class="sxs-lookup"><span data-stu-id="cccee-117">To access the available templates, in the Microsoft PowerApps Admin Center, select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="cccee-118">Följande mall och underliggande uppgift används för att synkronisera projektets verkliga värden från Project Service Automation till Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="cccee-118">The following template and underlying tasks are used to synchronize project actuals from Project Service Automation to Finance and Operations:</span></span>

-  <span data-ttu-id="cccee-119">**Namnet på mallen i dataintegrering:** projektets verkliga värden (PSA to Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="cccee-119">**Name of the template in Data integration:** Project actuals (PSA to Fin and Ops)</span></span>

-  <span data-ttu-id="cccee-120">**Namn på aktiviteter i projektet:**</span><span class="sxs-lookup"><span data-stu-id="cccee-120">**Name of the tasks in the project:**</span></span> 
    - <span data-ttu-id="cccee-121">Utfall</span><span class="sxs-lookup"><span data-stu-id="cccee-121">Actuals</span></span> 
    - <span data-ttu-id="cccee-122">Transaktionsanslutningar</span><span class="sxs-lookup"><span data-stu-id="cccee-122">TransactionConnections</span></span>

## <a name="entity-set"></a><span data-ttu-id="cccee-123">Ange entiteten</span><span class="sxs-lookup"><span data-stu-id="cccee-123">Entity set</span></span>

| <span data-ttu-id="cccee-124">Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="cccee-124">Project Service Automation</span></span>      | <span data-ttu-id="cccee-125">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="cccee-125">Finance and Operations</span></span>                                      |
|---------------------------------|-------------------------------------------------------------|
| <span data-ttu-id="cccee-126">Utfall</span><span class="sxs-lookup"><span data-stu-id="cccee-126">Actuals</span></span>                         | <span data-ttu-id="cccee-127">Integrationsenhet för projektets faktiska värden</span><span class="sxs-lookup"><span data-stu-id="cccee-127">Integration entity for project actuals</span></span>                      |
| <span data-ttu-id="cccee-128">Transaktionsanslutningar</span><span class="sxs-lookup"><span data-stu-id="cccee-128">Transaction Connections</span></span>         | <span data-ttu-id="cccee-129">Integrationsenhet för projektets transaktionsrelationer</span><span class="sxs-lookup"><span data-stu-id="cccee-129">Integration entity for project transaction relationships</span></span>    |

## <a name="entity-flow"></a><span data-ttu-id="cccee-130">Flöde för entitet</span><span class="sxs-lookup"><span data-stu-id="cccee-130">Entity flow</span></span>

<span data-ttu-id="cccee-131">Projektets verkliga värden hanteras i Project Service Automation och de synkroniseras till Finance and Operations till projektets integrationsjournal.</span><span class="sxs-lookup"><span data-stu-id="cccee-131">Project actuals are managed in Project Service Automation, and they are synchronized to Finance and Operations to the project ingetration journal.</span></span> <span data-ttu-id="cccee-132">Redovisningen används utifrån ekonomiska standarddimensioner och bokföringsinställningarna.</span><span class="sxs-lookup"><span data-stu-id="cccee-132">The accounting will be applied based on default financial dimensions and posting setup.</span></span>

## <a name="preconditions"></a><span data-ttu-id="cccee-133">Förvillkor</span><span class="sxs-lookup"><span data-stu-id="cccee-133">Preconditions</span></span>

<span data-ttu-id="cccee-134">Innan synkroniseringen av verkliga värden kan utföras måste Project Service Automation konfigurera integrationsparametrar och synkronisera projekt, projektuppgifter och kategorier för projektutgiftstransaktioner.</span><span class="sxs-lookup"><span data-stu-id="cccee-134">Before synchronization of actuals can occur, you must configure the Project Service Automation integration parameters and synchronize projects, project tasks, and project expense transaction categories.</span></span>

## <a name="power-query"></a><span data-ttu-id="cccee-135">Power Query</span><span class="sxs-lookup"><span data-stu-id="cccee-135">Power Query</span></span>

<span data-ttu-id="cccee-136">Du måste använda Microsoft Power Query i mallen för projektets faktiska värden:</span><span class="sxs-lookup"><span data-stu-id="cccee-136">You must use Microsoft Power Query in the project actuals template to:</span></span>
- <span data-ttu-id="cccee-137">Omvandla Project Service Automation **transaktionstyp** till rätt **transaktionstyp** i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="cccee-137">Transform the Project Service Automation **transaction type** to the correct **transaction type** in Finance and Operations.</span></span> <span data-ttu-id="cccee-138">Mallen för projektets verkliga värden (PSA till Fin and Ops) har redan den här omvandlingen definierad.</span><span class="sxs-lookup"><span data-stu-id="cccee-138">The Project actuals (PSA to Fin and Ops) template already has this transformation defined.</span></span>
- <span data-ttu-id="cccee-139">Omvandla Project Service Automation **faktureringstyp** till rätt **faktureringstyp** i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="cccee-139">Transform the Project Service Automation **billing type** to the correct **billing type** in Finance and Operations.</span></span> <span data-ttu-id="cccee-140">Mallen för projektets verkliga värden (PSA till Fin and Ops) har redan den här omvandlingen definierad.</span><span class="sxs-lookup"><span data-stu-id="cccee-140">The Project actuals (PSA to Fin and Ops) template already has this transformation defined.</span></span> <span data-ttu-id="cccee-141">Faktureringstypen mappas sedan till **radegenskap** baserat på konfigurationen i Dynamics 365 for Project Service Automation parameterformuläret för integration.</span><span class="sxs-lookup"><span data-stu-id="cccee-141">The billing type is then mapped to the **line property** based on the configuration in the Dynamics 365 for Project Service Automation integration parameters form.</span></span>
- <span data-ttu-id="cccee-142">Filter till specifika **resursorganisationsenheter** som ska synkroniseras med den här mallen.</span><span class="sxs-lookup"><span data-stu-id="cccee-142">Filter to specific **Resource organizational units** that are to be synced with this template.</span></span>
- <span data-ttu-id="cccee-143">Om **koncernintern tid eller koncernintern verklig kostnad** kommer att synkroniseras till Finance and Operations måste du omvandla **kontraktorganisationsenhet** till rätt **juridisk person** i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="cccee-143">If **intercompany time or intercompany expense actuals** will be synced to Finance and Operations, you must transform the **contract organizational unit** to the correct **legal entity** in Finance and Operations.</span></span> <span data-ttu-id="cccee-144">Mallen projektets verkliga värden (PSA till Fin and Ops) har villkorliga kolumn som är definierad utifrån demodata.</span><span class="sxs-lookup"><span data-stu-id="cccee-144">The Project actuals (PSA to Fin and Ops) template has a conditional column defined based on demo data.</span></span> <span data-ttu-id="cccee-145">Du måste uppdatera kolumnens sista infogade villkor till rätt juridiska personer.</span><span class="sxs-lookup"><span data-stu-id="cccee-145">You must update the last inserted condition column to the correct legal entities.</span></span> <span data-ttu-id="cccee-146">Om du inte gör detta kan det resultera i integrationsfel eller felaktiga faktiska transaktioner importeras till Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="cccee-146">Failure to do this may result in either an integration error or incorrect actual transactions imported into Finance and Operations.</span></span>
- <span data-ttu-id="cccee-147">Om **koncernintern tid eller koncernintern verklig kostnad** kommer inte att synkroniseras till Finance and operations måste du ta bort den sista infogade kolumnen från mallen.</span><span class="sxs-lookup"><span data-stu-id="cccee-147">If **intercompany time or intercompany expense actuals** will not be synced to Finance and operations, you must delete the last inserted condition column from your template.</span></span> <span data-ttu-id="cccee-148">Om du inte gör detta kan det resultera i integrationsfel eller felaktiga faktiska transaktioner importeras till Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="cccee-148">Failure to do this may result in either an integration error or incorrect actual transactions imported into Finance and Operations.</span></span>

### <a name="contract-organizational-unit"></a><span data-ttu-id="cccee-149">Kontraktorganisationsenhet</span><span class="sxs-lookup"><span data-stu-id="cccee-149">Contract Organizational Unit</span></span>
<span data-ttu-id="cccee-150">För att uppdatera den infogade kolumnen i mallen, klicka på pilen **Mappa** för att öppna mappningen.</span><span class="sxs-lookup"><span data-stu-id="cccee-150">To update the inserted condition column in the template, click the **Map** arrow to open the mapping.</span></span> <span data-ttu-id="cccee-151">Välj för att öppna avancerad fråga och filtrering.</span><span class="sxs-lookup"><span data-stu-id="cccee-151">Select to open the Advanced Query and Filtering.</span></span>
- <span data-ttu-id="cccee-152">Om du använder standardmallen Microsoft mallen projektets faktiska värden (PSA till Fin and Ops), välj den senaste **Infogat villkor** i avsnittet **Tillämpade steg**.</span><span class="sxs-lookup"><span data-stu-id="cccee-152">If you are using the default Microsoft Project actuals (PSA to Fin and Ops) template, select the lasat **Inserted Condition** in the **Applied Steps** section.</span></span> <span data-ttu-id="cccee-153">I posten **funktion**, ersätt **USSI** med namnet på den **juridiska person** som ska användas med integrationen.</span><span class="sxs-lookup"><span data-stu-id="cccee-153">In the **Function** entry, replace **USSI** with the name of the **Legal entity** that should be used with the integration.</span></span> <span data-ttu-id="cccee-154">Lägg till ytterligare villkor för posten **funktion** och uppdatera villkoret **annat** från **USMF** till rätt **juridisk person**.</span><span class="sxs-lookup"><span data-stu-id="cccee-154">Add additional conditions as needed to the **Function** entry and update the **else** condition from **USMF** to the correct **Legal entity**.</span></span>
- <span data-ttu-id="cccee-155">Om du skapar en ny mall måste du lägga till den här kolumnen för att ge stöd till koncernintern tid och utgifter.</span><span class="sxs-lookup"><span data-stu-id="cccee-155">If you are creating a new template, you must add this column to support intercompany time and expenses.</span></span> <span data-ttu-id="cccee-156">Välj **lägga till villkorlig kolumn** och ge kolumnen ett namn, till exempel LegalEntity.</span><span class="sxs-lookup"><span data-stu-id="cccee-156">Select **Add Conditional Column** and give the column a name, such as LegalEntity.</span></span> <span data-ttu-id="cccee-157">Ange villkor för kolumnen där om msdyn_contractorganizationalunitid.msdyn_name <organizational unit>, sedan <enter the Legal entity>; annars null.</span><span class="sxs-lookup"><span data-stu-id="cccee-157">Enter the condition for the column where if msdyn_contractorganizationalunitid.msdyn_name is <organizational unit>, then <enter the Legal entity>; else null.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="cccee-158">Mallmappning i dataintegrering</span><span class="sxs-lookup"><span data-stu-id="cccee-158">Template mapping in Data integration</span></span>

<span data-ttu-id="cccee-159">I följande illustration visas ett exempel på uppgiftsmallmappning i dataintegrering.</span><span class="sxs-lookup"><span data-stu-id="cccee-159">The following illustration shows an example of the template task mapping in Data integration.</span></span> <span data-ttu-id="cccee-160">Mappningen visar vilken fältinformation som kommer att synkroniseras från Project Service Automation till Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="cccee-160">The mapping shows the field information that will be synchronized from Project Service Automation to Finance and Operations.</span></span>

<span data-ttu-id="cccee-161">[![Mallmappning](./media/ActualsMapping.jpg)](./media/ActualsMapping.jpg)</span><span class="sxs-lookup"><span data-stu-id="cccee-161">[![Template mapping](./media/ActualsMapping.jpg)](./media/ActualsMapping.jpg)</span></span>

<span data-ttu-id="cccee-162">[![Mallmappning](./media/TransactionConnections.jpg)](./media/TransactionConnections.jpg)</span><span class="sxs-lookup"><span data-stu-id="cccee-162">[![Template mapping](./media/TransactionConnections.jpg)](./media/TransactionConnections.jpg)</span></span>

## <a name="import-from-staging-table"></a><span data-ttu-id="cccee-163">Importera från mellanlagringsregister</span><span class="sxs-lookup"><span data-stu-id="cccee-163">Import from staging table</span></span>

<span data-ttu-id="cccee-164">Importen från mellanlagringsregistrets periodiska process måste köras efter synkronisering av verkliga värden från Project Service Automation till Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="cccee-164">The Import from staging table perioidic process must be run after the sychronization of actuals from Project Service Automation to Finance and Operations.</span></span> <span data-ttu-id="cccee-165">Denna process importerar projekttransaktionerna från mellanlagringsregistret till Project Service Automation integrationsjournalen där redovisning används och importerade transaktioner kan bokföras.</span><span class="sxs-lookup"><span data-stu-id="cccee-165">This process will import the project transactions from the staging table into the Project Service Automation integration journal, where the accounting is applied and the imported transactions can be posted.</span></span> <span data-ttu-id="cccee-166">Det rekommenderas att köra den här processen i batchläge och kan eventuellt ställas in att köras som ett återkommande batchjobb.</span><span class="sxs-lookup"><span data-stu-id="cccee-166">It is recommended that you run this process in batch mode and optionally can be set up to run as a recurring batch.</span></span>

## <a name="update-actuals"></a><span data-ttu-id="cccee-167">Uppdatera verkliga värden</span><span class="sxs-lookup"><span data-stu-id="cccee-167">Update Actuals</span></span>

<span data-ttu-id="cccee-168">Följande mall och underliggande uppgift används för att synkronisera kupongnummer och försäljningsskatt för upplagda projekttransaktioner från Finance and Operations till Project Service Automation:</span><span class="sxs-lookup"><span data-stu-id="cccee-168">The following template and underlying tasks are used to synchronize the voucher number and sales taxes for posted project transactions from Finance and Operations to Project Service Automation:</span></span>

-  <span data-ttu-id="cccee-169">**Namnet på mallen i dataintegrering:** projektets verkliga värden (Fin Ops till PSA)</span><span class="sxs-lookup"><span data-stu-id="cccee-169">**Name of the template in Data integration:** Project actuals update (Fin Ops to PSA)</span></span>
-  <span data-ttu-id="cccee-170">**Namn på aktiviteter i projektet:**</span><span class="sxs-lookup"><span data-stu-id="cccee-170">**Name of the tasks in the project:**</span></span> 
     - <span data-ttu-id="cccee-171">Utfall</span><span class="sxs-lookup"><span data-stu-id="cccee-171">Actuals</span></span> 
     - <span data-ttu-id="cccee-172">Transaktionsanslutningar</span><span class="sxs-lookup"><span data-stu-id="cccee-172">TransactionConnections</span></span>

## <a name="entity-set"></a><span data-ttu-id="cccee-173">Ange entiteten</span><span class="sxs-lookup"><span data-stu-id="cccee-173">Entity set</span></span>

| <span data-ttu-id="cccee-174">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="cccee-174">Finance and Operations</span></span>                                         | <span data-ttu-id="cccee-175">Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="cccee-175">Project Service Automation</span></span>        |
|----------------------------------------------------------------|-----------------------------------|
| <span data-ttu-id="cccee-176">Integrationsenhet för projektets faktiska värden</span><span class="sxs-lookup"><span data-stu-id="cccee-176">Integration entity for project actuals</span></span>                         | <span data-ttu-id="cccee-177">Utfall</span><span class="sxs-lookup"><span data-stu-id="cccee-177">Actuals</span></span>                           |
| <span data-ttu-id="cccee-178">Integrationsenhet för projektets transaktionsrelationer</span><span class="sxs-lookup"><span data-stu-id="cccee-178">Integration entity for project transaction relationships</span></span>       | <span data-ttu-id="cccee-179">Transaktionsanslutningar</span><span class="sxs-lookup"><span data-stu-id="cccee-179">Transaction Connections</span></span>           |

## <a name="entity-flow"></a><span data-ttu-id="cccee-180">Flöde för entitet</span><span class="sxs-lookup"><span data-stu-id="cccee-180">Entity flow</span></span>

<span data-ttu-id="cccee-181">Projektets verkliga värden hanteras i Project Service Automation och de synkroniseras till Finance and Operations till projektets integrationsjournal.</span><span class="sxs-lookup"><span data-stu-id="cccee-181">Project actuals are managed in Project Service Automation, and they are synchronized to Finance and Operations to the project integration journal.</span></span> <span data-ttu-id="cccee-182">När de är bokförda i Finance and Operations uppdateras verkliga värden i Project Service Automation med verifikationsnumret från Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="cccee-182">Once posted in Finance and Operations, actuals are updated in Project Service Automation with the voucher number from Finance and Operations.</span></span> <span data-ttu-id="cccee-183">Om moms har lagts till i Finance and Operations kommer nya verkliga värden för skatt att skapas i Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="cccee-183">If sales taxes were added in Finance and Operations, new tax actuals will be created in PRoject Service Automation.</span></span>

## <a name="power-query"></a><span data-ttu-id="cccee-184">Power Query</span><span class="sxs-lookup"><span data-stu-id="cccee-184">Power Query</span></span>

<span data-ttu-id="cccee-185">Du måste använda Microsoft Power Query i uppdateringsmallen för projektets faktiska värden:</span><span class="sxs-lookup"><span data-stu-id="cccee-185">You must use Microsoft Power Query in the project actuals update template to:</span></span>
- <span data-ttu-id="cccee-186">Omvandla Finance and Operations **transaktionstyp** till rätt **transaktionstyp** i Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="cccee-186">Transform the Finance and Operations **transaction type** to the correct **transaction type** in Project Service Automation.</span></span> <span data-ttu-id="cccee-187">Mallen för projektets verkliga värden (Fin Ops till PSA) har redan den här omvandlingen definierad.</span><span class="sxs-lookup"><span data-stu-id="cccee-187">The Project actuals update (Fin Ops to PSA) template already has this transformation defined.</span></span>
- <span data-ttu-id="cccee-188">Omvandla Finance and Operations **faktureringstyp** till rätt **faktureringstyp** i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="cccee-188">Transform the Finance and Operations **billing type** to the correct **billing type** in Project Service Automation.</span></span> <span data-ttu-id="cccee-189">Mallen för projektets verkliga värden (Fin Ops till PSA) har redan den här omvandlingen definierad.</span><span class="sxs-lookup"><span data-stu-id="cccee-189">The Project actuals update (Fin Ops to PSA) template already has this transformation defined.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="cccee-190">Mallmappning i dataintegrering</span><span class="sxs-lookup"><span data-stu-id="cccee-190">Template mapping in Data integration</span></span>

<span data-ttu-id="cccee-191">I följande illustrationer visas ett exempel på uppgiftsmallmappning i dataintegrering.</span><span class="sxs-lookup"><span data-stu-id="cccee-191">The following illustrations show examples of the template task mappings in Data integration.</span></span> <span data-ttu-id="cccee-192">Mappningen visar vilken fältinformation som kommer att synkroniseras från Finance and Operations till Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="cccee-192">The mapping shows the field information that will be synchronized from Finance and Operations to Project Service Automation.</span></span>

<span data-ttu-id="cccee-193">[![Mallmappning](./media/ActualsUpdateMapping.jpg)](./media/ActualsUpdateMapping.jpg)</span><span class="sxs-lookup"><span data-stu-id="cccee-193">[![Template mapping](./media/ActualsUpdateMapping.jpg)](./media/ActualsUpdateMapping.jpg)</span></span>

<span data-ttu-id="cccee-194">[![Mallmappning](./media/TransactionConnectionsUpdate.jpg)](./media/TransactionConnectionsUpdate.jpg)</span><span class="sxs-lookup"><span data-stu-id="cccee-194">[![Template mapping](./media/TransactionConnectionsUpdate.jpg)](./media/TransactionConnectionsUpdate.jpg)</span></span>



