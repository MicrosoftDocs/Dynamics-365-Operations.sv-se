---
title: Synkronisera projektuppskattningar från Project Service Automation direkt till Finance and Operations
description: Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera projektets timuppskattningar och projektets utgiftsuppskattningar direkt från Microsoft Dynamics 365 Project Service Automation till Dynamics 365 Finance.
author: KimANelson
manager: AnnBe
ms.date: 07/20/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 7.3.0
ms.openlocfilehash: 3b885610ac9ca8645358ba8ab6d46ab82143a534
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/30/2019
ms.locfileid: "2250494"
---
# <a name="synchronize-project-estimates-directly-from-project-service-automation-to-finance-and-operations"></a><span data-ttu-id="e2c1e-103">Synkronisera projektuppskattningar från Project Service Automation direkt till Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="e2c1e-103">Synchronize project estimates directly from Project Service Automation to Finance and Operations</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="e2c1e-104">Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera projektets timuppskattningar och projektets utgiftsuppskattningar direkt från Dynamics 365 Project Service Automation till Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="e2c1e-104">This topic describes the templates and underlying tasks that are used to synchronize project hour estimates and project expense estimates directly from Dynamics 365 Project Service Automation to Dynamics 365 Finance.</span></span>

> [!NOTE]
> - <span data-ttu-id="e2c1e-105">Projektuppgiftsintegration, utgiftstransationskategorier, uppskattningar av timme, uppskattning av utgifter och funktionslåsning är tillgängliga i version 8.0.</span><span class="sxs-lookup"><span data-stu-id="e2c1e-105">Project task integration, expense transaction categories, hour estimates, expense estimates, and functionality locking is available in version 8.0.</span></span>
> - <span data-ttu-id="e2c1e-106">Integrering av faktiska uppgifter finns i version 8.0.1 eller senare.</span><span class="sxs-lookup"><span data-stu-id="e2c1e-106">Actuals integration is available in version 8.0.1 or later.</span></span>

## <a name="data-flow-for-project-service-automation-to-finance"></a><span data-ttu-id="e2c1e-107">Dataflöde för Project Service Automation till Finance</span><span class="sxs-lookup"><span data-stu-id="e2c1e-107">Data flow for Project Service Automation to Finance</span></span>

<span data-ttu-id="e2c1e-108">Automatisering av integrationslösningen Project Service Automation till Finance-integrationslösningen använder funktionen dataintegration för att synkronisera data mellan instanser av Project Service Automation och Finance.</span><span class="sxs-lookup"><span data-stu-id="e2c1e-108">The Project Service Automation to Finance integration solution uses the Data integration feature to synchronize data across instances of Project Service Automation and Finance.</span></span> <span data-ttu-id="e2c1e-109">Integrationsmallarna som är tillgängliga med dataintegrationsfunktionen möjliggör flödet av data om projektets timuppskattningar och projektets utgiftsuppskattningar från Project Service Automation till Finance.</span><span class="sxs-lookup"><span data-stu-id="e2c1e-109">The integration templates that are available with the Data integration feature enable the flow of data about project hour estimates and project expense estimates from Project Service Automation to Finance.</span></span>

<span data-ttu-id="e2c1e-110">Följande bild visar hur data synkroniseras mellan Project Service Automation och Finance.</span><span class="sxs-lookup"><span data-stu-id="e2c1e-110">The following illustration shows how the data is synchronized between Project Service Automation and Finance.</span></span>

<span data-ttu-id="e2c1e-111">[![Dataflöde för integration av Project Service Automation med Finance](./media/ProjectEstimatesFlow.png)](./media/ProjectEstimatesFlow.png)</span><span class="sxs-lookup"><span data-stu-id="e2c1e-111">[![Data flow for Project Service Automation integration with Finance](./media/ProjectEstimatesFlow.png)](./media/ProjectEstimatesFlow.png)</span></span>

## <a name="project-hour-estimates"></a><span data-ttu-id="e2c1e-112">Timuppskattningar för projekt</span><span class="sxs-lookup"><span data-stu-id="e2c1e-112">Project hour estimates</span></span>

### <a name="template-and-tasks"></a><span data-ttu-id="e2c1e-113">Mall och uppgifter</span><span class="sxs-lookup"><span data-stu-id="e2c1e-113">Template and tasks</span></span>

<span data-ttu-id="e2c1e-114">För att få åtkomst till tillgängliga mallar väljer du i administratörscentret för Microsoft PowerApps **Projekt** och sedan i det övre högra hörnet **Ny projekt** för att välja offentliga mallar.</span><span class="sxs-lookup"><span data-stu-id="e2c1e-114">To access the available templates, in the Microsoft PowerApps admin center, select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="e2c1e-115">Följande mall och underliggande uppgifter används för att synkronisera projektets timuppskattningar från Project Service Automation till Finance:</span><span class="sxs-lookup"><span data-stu-id="e2c1e-115">The following template and underlying tasks are used to synchronize project hour estimates from Project Service Automation to Finance:</span></span>

- <span data-ttu-id="e2c1e-116">**Namnet på mallen i dataintegrering:** projektets timuppskattningar (PSA till Fin och Ops)</span><span class="sxs-lookup"><span data-stu-id="e2c1e-116">**Name of the template in Data integration:** Project hour estimates (PSA to Fin and Ops)</span></span>
- <span data-ttu-id="e2c1e-117">**Namn på aktiviteter i projektet:**</span><span class="sxs-lookup"><span data-stu-id="e2c1e-117">**Name of the tasks in the project:**</span></span>

    - <span data-ttu-id="e2c1e-118">Transaktionsrelationer</span><span class="sxs-lookup"><span data-stu-id="e2c1e-118">Transaction relationships</span></span>
    - <span data-ttu-id="e2c1e-119">Utgiftsuppskattning</span><span class="sxs-lookup"><span data-stu-id="e2c1e-119">Expense estimates</span></span>

### <a name="entity-set"></a><span data-ttu-id="e2c1e-120">Ange entiteten</span><span class="sxs-lookup"><span data-stu-id="e2c1e-120">Entity set</span></span>

| <span data-ttu-id="e2c1e-121">Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="e2c1e-121">Project Service Automation</span></span> | <span data-ttu-id="e2c1e-122">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="e2c1e-122">Finance</span></span>                                       |
|----------------------------|-----------------------------------------------|
| <span data-ttu-id="e2c1e-123">Projektuppgifter</span><span class="sxs-lookup"><span data-stu-id="e2c1e-123">Project tasks</span></span>              | <span data-ttu-id="e2c1e-124">Integrationsenhet för projektets timuppskattningar</span><span class="sxs-lookup"><span data-stu-id="e2c1e-124">Integration entity for project hour estimates</span></span> |

### <a name="entity-flow"></a><span data-ttu-id="e2c1e-125">Flöde för entitet</span><span class="sxs-lookup"><span data-stu-id="e2c1e-125">Entity flow</span></span>

<span data-ttu-id="e2c1e-126">Projektets timuppskattningar hanteras i Project Service Automation och de synkroniseras till Finance som timprognoser i projekt.</span><span class="sxs-lookup"><span data-stu-id="e2c1e-126">Project hour estimates are managed in Project Service Automation, and they are synchronized to Finance as project hour forecasts.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="e2c1e-127">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="e2c1e-127">Prerequisites</span></span>

<span data-ttu-id="e2c1e-128">Innan synkroniseringen av projektets uppskattade timmar kan utföras måste du synkronisera projekt, projektuppgifter och transaktionskategorier för projektutgifter.</span><span class="sxs-lookup"><span data-stu-id="e2c1e-128">Before synchronization of project hour estimates can occur, you must synchronize projects, project tasks, and project expense transaction categories.</span></span>

### <a name="power-query"></a><span data-ttu-id="e2c1e-129">Power Query</span><span class="sxs-lookup"><span data-stu-id="e2c1e-129">Power Query</span></span>

<span data-ttu-id="e2c1e-130">Du måste använda Microsoft Power Query för Excel i uppskattningsmallen för projekttimmar för att kunna slutföra följande uppgifter:</span><span class="sxs-lookup"><span data-stu-id="e2c1e-130">In the project hour estimates template, you must use Microsoft Power Query for Excel to complete these tasks:</span></span>

- <span data-ttu-id="e2c1e-131">Ange det förvalda prognosmodell-ID som ska användas när integrationen skapar nya timprognoser.</span><span class="sxs-lookup"><span data-stu-id="e2c1e-131">Set the default forecast model ID that will be used when the integration creates new hour forecasts.</span></span>
- <span data-ttu-id="e2c1e-132">Filtrera bort alla resursspecifika poster i uppgiften som kommer att misslyckas med integrationen i timuppskattningar.</span><span class="sxs-lookup"><span data-stu-id="e2c1e-132">Filter out any resource-specific records in the task that will fail the integration into hour forecasts.</span></span>
- <span data-ttu-id="e2c1e-133">Filtrera bort alla tomma transaktionskategorirader.</span><span class="sxs-lookup"><span data-stu-id="e2c1e-133">Filter out any empty transaction category rows.</span></span> <span data-ttu-id="e2c1e-134">Om denna uppgift inte utförs kan detta resultera i fel timprognoserna.</span><span class="sxs-lookup"><span data-stu-id="e2c1e-134">Failure to complete this task might result in incorrect hour forecasts.</span></span>

#### <a name="set-the-default-forecast-model-id"></a><span data-ttu-id="e2c1e-135">Anger standard-ID för prognosmodell</span><span class="sxs-lookup"><span data-stu-id="e2c1e-135">Set the default forecast model ID</span></span>

<span data-ttu-id="e2c1e-136">För att uppdatera standardprognosmodell-ID i mallen, klicka på pilen **Mapp** för att öppna mappningen.</span><span class="sxs-lookup"><span data-stu-id="e2c1e-136">To update the default forecast model ID in the template, click the **Map** arrow to open the mapping.</span></span> <span data-ttu-id="e2c1e-137">Välj sedan länken **Avancerade frågor och filter**.</span><span class="sxs-lookup"><span data-stu-id="e2c1e-137">Then select the **Advanced Query and Filtering** link.</span></span>

- <span data-ttu-id="e2c1e-138">Om du använder mallen för förvalda uppskattningar för projekttimmar ("PSA till Fin och Ops"), markera då **Infört tillstånd** i listan för **Tillämpade steg**.</span><span class="sxs-lookup"><span data-stu-id="e2c1e-138">If you're using the default Project hour estimates (PSA to Fin and Ops) template, select the **Inserted Condition** in the list of **Applied Steps**.</span></span> <span data-ttu-id="e2c1e-139">I posten **Funktion** byter du ut **O\_forecast** mot ID för den prognosmodell som ska användas för integreringen.</span><span class="sxs-lookup"><span data-stu-id="e2c1e-139">In the **Function** entry, replace **O\_forecast** with the name of the forecast model ID that should be used with the integration.</span></span> <span data-ttu-id="e2c1e-140">Standardmallen har en prognosmodell från demonstrationsdata.</span><span class="sxs-lookup"><span data-stu-id="e2c1e-140">The default template has a forecast model ID from the demo data.</span></span>
- <span data-ttu-id="e2c1e-141">Om du skapar en ny mall måste du lägga till den här kolumnen.</span><span class="sxs-lookup"><span data-stu-id="e2c1e-141">If you're creating a new template, you must add this column.</span></span> <span data-ttu-id="e2c1e-142">I Power Query markerar du **Lägg till villkorskolumn** och anger ett namn för den nya kolumnen, till exempel **ModelID**.</span><span class="sxs-lookup"><span data-stu-id="e2c1e-142">In Power Query, select **Add Conditional Column**, and enter a name for the new column, such as **ModelID**.</span></span> <span data-ttu-id="e2c1e-143">Ange villkoret för den nya kolumnen, där – om projektuppgiften inte är noll – \<ange prognosens modell-ID\>; annars noll.</span><span class="sxs-lookup"><span data-stu-id="e2c1e-143">Enter the condition for the column, where, if Project task is not null, then \<enter the forecast model ID\>; else null.</span></span>

#### <a name="filter-out-resource-specific-records"></a><span data-ttu-id="e2c1e-144">Filtrera ut resursspecifika poster</span><span class="sxs-lookup"><span data-stu-id="e2c1e-144">Filter out resource-specific records</span></span>

<span data-ttu-id="e2c1e-145">Mallen för projektets timuppskattningar ("PSA till Fin och Ops") har ett standardfilter som tar bort alla resursspecifika poster.</span><span class="sxs-lookup"><span data-stu-id="e2c1e-145">The Project hour estimates (PSA to Fin and Ops) template has a default filter that removes any resource-specific records.</span></span> <span data-ttu-id="e2c1e-146">Om du skapar en egen mall måste du lägga till filtret.</span><span class="sxs-lookup"><span data-stu-id="e2c1e-146">If you create your own template, you must add this filter.</span></span> <span data-ttu-id="e2c1e-147">Markera länken **Avancerade frågor och filtrering** att filtrera kolumnen **msdyn\_islinetask** så att endast poster markerade **False** omfattas.</span><span class="sxs-lookup"><span data-stu-id="e2c1e-147">Select the **Advanced Query and Filtering** link to filter on the **msdyn\_islinetask** column so that only **False** records are included.</span></span>

#### <a name="filter-out-empty-transaction-category-rows"></a><span data-ttu-id="e2c1e-148">Filtrera bort alla tomma transaktionskategorirader.</span><span class="sxs-lookup"><span data-stu-id="e2c1e-148">Filter out empty transaction category rows</span></span>

<span data-ttu-id="e2c1e-149">Du måste lägga till ett filter för att ta bort alla rader som har tomma transaktionskategorier.</span><span class="sxs-lookup"><span data-stu-id="e2c1e-149">You must add a filter to remove any rows that have empty transaction categories.</span></span> <span data-ttu-id="e2c1e-150">Denna uppgift krävs oavsett om du använder standardmallen eller om du skapar en egen mall.</span><span class="sxs-lookup"><span data-stu-id="e2c1e-150">This task is required, regardless of whether you're using the default template or creating your own template.</span></span> <span data-ttu-id="e2c1e-151">Detta filter tar bort alla sammanfattningsrader från Project Service Automation som skulle kunna medföra att timprognoser i Finance blir felaktiga.</span><span class="sxs-lookup"><span data-stu-id="e2c1e-151">This filter removes any summary rows from Project Service Automation that might cause the hour forecasts in Finance to be incorrect.</span></span> <span data-ttu-id="e2c1e-152">Marker länken **Avancerade frågor och filter** för att filtrera ut nollposter i kolumnen **msdyn\_transactioncategory\_value**.</span><span class="sxs-lookup"><span data-stu-id="e2c1e-152">Select **Advanced Query and Filtering** link to filter out null records in the **msdyn\_transactioncategory\_value** column.</span></span>

### <a name="template-mapping-in-data-integration"></a><span data-ttu-id="e2c1e-153">Mallmappning i dataintegrering</span><span class="sxs-lookup"><span data-stu-id="e2c1e-153">Template mapping in Data integration</span></span>

<span data-ttu-id="e2c1e-154">I följande illustration visas ett exempel på uppgiftsmallmappning i dataintegrering.</span><span class="sxs-lookup"><span data-stu-id="e2c1e-154">The following illustration shows an example of the template task mapping in Data integration.</span></span> <span data-ttu-id="e2c1e-155">Mappningen visar vilken fältinformation som kommer att synkroniseras från Project Service Automation till Finance.</span><span class="sxs-lookup"><span data-stu-id="e2c1e-155">The mapping shows the field information that will be synchronized from Project Service Automation to Finance.</span></span>

<span data-ttu-id="e2c1e-156">[![Mallmappning](./media/ProjectHourEstimatesMapping.jpg)](./media/ProjectHourEstimatesMapping.jpg)</span><span class="sxs-lookup"><span data-stu-id="e2c1e-156">[![Template mapping](./media/ProjectHourEstimatesMapping.jpg)](./media/ProjectHourEstimatesMapping.jpg)</span></span>

## <a name="project-expense-estimates"></a><span data-ttu-id="e2c1e-157">Uppskattningar av projektutgifter</span><span class="sxs-lookup"><span data-stu-id="e2c1e-157">Project expense estimates</span></span>

### <a name="template-and-tasks"></a><span data-ttu-id="e2c1e-158">Mall och uppgifter</span><span class="sxs-lookup"><span data-stu-id="e2c1e-158">Template and tasks</span></span>

<span data-ttu-id="e2c1e-159">Följande mall och underliggande uppgifter används för att synkronisera projektets utgiftsupppskattningar från Project Service Automation till Finance:</span><span class="sxs-lookup"><span data-stu-id="e2c1e-159">The following template and underlying tasks are used to synchronize project expense estimates from Project Service Automation to Finance:</span></span>

- <span data-ttu-id="e2c1e-160">**Namnet på mallen i dataintegrering:** projektets utgiftsuppskattningar (PSA till Fin och Ops)</span><span class="sxs-lookup"><span data-stu-id="e2c1e-160">**Name of the template in Data integration:** Project expense estimates (PSA to Fin and Ops)</span></span>
- <span data-ttu-id="e2c1e-161">**Namn på aktiviteter i projektet:**</span><span class="sxs-lookup"><span data-stu-id="e2c1e-161">**Name of the tasks in the project:**</span></span>

    - <span data-ttu-id="e2c1e-162">Transaktionsrelationer</span><span class="sxs-lookup"><span data-stu-id="e2c1e-162">Transaction relationships</span></span> 
    - <span data-ttu-id="e2c1e-163">Utgiftsuppskattning</span><span class="sxs-lookup"><span data-stu-id="e2c1e-163">Expense estimates</span></span>

### <a name="entity-set"></a><span data-ttu-id="e2c1e-164">Ange entiteten</span><span class="sxs-lookup"><span data-stu-id="e2c1e-164">Entity set</span></span>

| <span data-ttu-id="e2c1e-165">Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="e2c1e-165">Project Service Automation</span></span> | <span data-ttu-id="e2c1e-166">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="e2c1e-166">Finance</span></span>                                                  |
|----------------------------|----------------------------------------------------------|
| <span data-ttu-id="e2c1e-167">Transaktionsanslutningar</span><span class="sxs-lookup"><span data-stu-id="e2c1e-167">Transaction Connections</span></span>    | <span data-ttu-id="e2c1e-168">Integrationsenhet för projektets transaktionsrelationer</span><span class="sxs-lookup"><span data-stu-id="e2c1e-168">Integration entity for project transaction relationships</span></span> |
| <span data-ttu-id="e2c1e-169">Uppskattningsrader</span><span class="sxs-lookup"><span data-stu-id="e2c1e-169">Estimate Lines</span></span>             | <span data-ttu-id="e2c1e-170">Integrationsenhet för projektets utgiftsuppskattningar</span><span class="sxs-lookup"><span data-stu-id="e2c1e-170">Integration entity for project expense estimates</span></span>         |

### <a name="entity-flow"></a><span data-ttu-id="e2c1e-171">Flöde för entitet</span><span class="sxs-lookup"><span data-stu-id="e2c1e-171">Entity flow</span></span>

<span data-ttu-id="e2c1e-172">Projektets utgiftsuppskattningar hanteras i Project Service Automation och de synkroniseras till Finance som utgiftsprognoser i projekt.</span><span class="sxs-lookup"><span data-stu-id="e2c1e-172">Project expense estimates are managed in Project Service Automation, and they are synchronized to Finance as project expense forecasts.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="e2c1e-173">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="e2c1e-173">Prerequisites</span></span>

<span data-ttu-id="e2c1e-174">Innan synkroniseringen av projektets utgiftsuppskattningar kan utföras måste du synkronisera projekt, projektuppgifter och transaktionskategorier för projektutgifter.</span><span class="sxs-lookup"><span data-stu-id="e2c1e-174">Before synchronization of project expense estimates can occur, you must synchronize projects, project tasks, and project expense transaction categories.</span></span>

### <a name="power-query"></a><span data-ttu-id="e2c1e-175">Power Query</span><span class="sxs-lookup"><span data-stu-id="e2c1e-175">Power Query</span></span>

<span data-ttu-id="e2c1e-176">Du måste använda Power Query i mallen i projektets utgiftsuppskattningar för att slutföra följande uppgifter:</span><span class="sxs-lookup"><span data-stu-id="e2c1e-176">In the project expense estimates template, you must use Power Query to complete the following tasks:</span></span>

- <span data-ttu-id="e2c1e-177">Filtrera med endast uppskattade utgiftsradsposter.</span><span class="sxs-lookup"><span data-stu-id="e2c1e-177">Filter to include only expense estimate line records.</span></span>
- <span data-ttu-id="e2c1e-178">Ange det förvalda prognosmodell-ID som ska användas när integrationen skapar nya timprognoser.</span><span class="sxs-lookup"><span data-stu-id="e2c1e-178">Set the default forecast model ID that will be used when the integration creates new hour forecasts.</span></span>
- <span data-ttu-id="e2c1e-179">Omvandla faktureringstyper.</span><span class="sxs-lookup"><span data-stu-id="e2c1e-179">Transform the billing types.</span></span>
- <span data-ttu-id="e2c1e-180">Omvandla transaktionstyper.</span><span class="sxs-lookup"><span data-stu-id="e2c1e-180">Transform the transaction types.</span></span>

#### <a name="filter-to-include-only-expense-estimate-lines"></a><span data-ttu-id="e2c1e-181">Filtrera med endast uppskattade utgiftsposter</span><span class="sxs-lookup"><span data-stu-id="e2c1e-181">Filter to include only expense estimate lines</span></span>

<span data-ttu-id="e2c1e-182">Mallen för projektets utgiftsupppskattningar ("PSA till Fin och Ops") har ett standardfilter som endast inkluderar utgiftsrader i integrationen.</span><span class="sxs-lookup"><span data-stu-id="e2c1e-182">The Project expense estimates (PSA to Fin and Ops) template has a default filter that includes only expense lines in the integration.</span></span> <span data-ttu-id="e2c1e-183">Om du skapar en egen mall måste du lägga till filtret.</span><span class="sxs-lookup"><span data-stu-id="e2c1e-183">If you create your own template, you must add this filter.</span></span> <span data-ttu-id="e2c1e-184">Markera uppgiften **Transaktionsrelationer** och klicka sedan på pilen **Mappa** för att öppna mappningen.</span><span class="sxs-lookup"><span data-stu-id="e2c1e-184">Select the **Transaction relationships** task, and then click the **Map** arrow to open the mapping.</span></span> <span data-ttu-id="e2c1e-185">Markera länken **Avancerade frågor och filter**.</span><span class="sxs-lookup"><span data-stu-id="e2c1e-185">Select the **Advanced Query and Filtering** link.</span></span> <span data-ttu-id="e2c1e-186">Filtrera kolumnen **msdyn\_transactiontype1** så att den endast omfattar **msdyn\_estimateline**.</span><span class="sxs-lookup"><span data-stu-id="e2c1e-186">Filter the **msdyn\_transactiontype1** column so that it includes only **msdyn\_estimateline**.</span></span>

#### <a name="set-the-default-forecast-model-id"></a><span data-ttu-id="e2c1e-187">Anger standard-ID för prognosmodell</span><span class="sxs-lookup"><span data-stu-id="e2c1e-187">Set the default forecast model ID</span></span>

<span data-ttu-id="e2c1e-188">För att uppdatera förvalt ID för prognosmodell i mallen, markera uppgiften **Utgiftsuppskattningar**, och klicka sedan på pilen **Mappa** för att öppna mappningen.</span><span class="sxs-lookup"><span data-stu-id="e2c1e-188">To update the default forecast model ID in the template, select the **Expense estimates** task, and then click the **Map** arrow to open the mapping.</span></span> <span data-ttu-id="e2c1e-189">Markera länken **Avancerade frågor och filter**.</span><span class="sxs-lookup"><span data-stu-id="e2c1e-189">Select the **Advanced Query and Filtering** link.</span></span>

- <span data-ttu-id="e2c1e-190">Om du använder förvald standardmall för projektutgifter ("PSA till Fin och Ops") markerar du första **Infört tillstånd** från avsnittet **Tillämpade steg** i Power Query.</span><span class="sxs-lookup"><span data-stu-id="e2c1e-190">If you're using the default Project expense estimates (PSA to Fin and Ops) template, in Power Query, select the first **Inserted Condition** from the **Applied Steps** section.</span></span> <span data-ttu-id="e2c1e-191">I posten **Funktion** byter du ut **O\_forecast** mot ID för den prognosmodell som ska användas för integreringen.</span><span class="sxs-lookup"><span data-stu-id="e2c1e-191">In the **Function** entry, replace **O\_forecast** with the name of the forecast model ID that should be used with the integration.</span></span> <span data-ttu-id="e2c1e-192">Standardmallen har en prognosmodell från demonstrationsdata.</span><span class="sxs-lookup"><span data-stu-id="e2c1e-192">The default template has a forecast model ID from the demo data.</span></span>
- <span data-ttu-id="e2c1e-193">Om du skapar en ny mall måste du lägga till den här kolumnen.</span><span class="sxs-lookup"><span data-stu-id="e2c1e-193">If you're creating a new template, you must add this column.</span></span> <span data-ttu-id="e2c1e-194">I Power Query markerar du **Lägg till villkorskolumn** och anger ett namn för den nya kolumnen, till exempel **ModelID**.</span><span class="sxs-lookup"><span data-stu-id="e2c1e-194">In Power Query, select **Add Conditional Column**, and enter a name for the new column, such as **ModelID**.</span></span> <span data-ttu-id="e2c1e-195">Ange villkoret för kolumnen där - om ID för uppskattningsraden inte är noll - \<ange ID för prognosmodell\>; annars noll.</span><span class="sxs-lookup"><span data-stu-id="e2c1e-195">Enter the condition for the column, where, if Estimate line ID is not null, then \<enter the forecast model ID\>; else null.</span></span>

#### <a name="transform-the-billing-types"></a><span data-ttu-id="e2c1e-196">Omvandla faktureringstyper.</span><span class="sxs-lookup"><span data-stu-id="e2c1e-196">Transform the billing types</span></span>

<span data-ttu-id="e2c1e-197">Mallen för projektets utgiftsuppskattningar ("PSA till Fin och Ops") omfattar en villkorlig kolumn som används för att omvandla faktureringstyperna som tas emot från Project Service Automation under integreringen.</span><span class="sxs-lookup"><span data-stu-id="e2c1e-197">The Project expense estimates (PSA to Fin and Ops) template includes a conditional column that is used to transform the billing types that are received from Project Service Automation during the integration.</span></span> <span data-ttu-id="e2c1e-198">Om du skapar en egen mall måste du lägga till denna villkorliga kolumn.</span><span class="sxs-lookup"><span data-stu-id="e2c1e-198">If you create your own template, you must add this conditional column.</span></span> <span data-ttu-id="e2c1e-199">Markera länken **Avancerade frågor och filter** och välj sedan **Lägg till villkorskolumn**.</span><span class="sxs-lookup"><span data-stu-id="e2c1e-199">Select the **Advanced Query and Filtering** link and then select **Add Conditional Column**.</span></span> <span data-ttu-id="e2c1e-200">Ange ett namn för den nya kolumnen, till exempel **Faktureringstyp**.</span><span class="sxs-lookup"><span data-stu-id="e2c1e-200">Enter a name for the new column, such as **BillingType**.</span></span> <span data-ttu-id="e2c1e-201">Ange sedan följande tillstånd:</span><span class="sxs-lookup"><span data-stu-id="e2c1e-201">Then enter the following condition:</span></span>

<span data-ttu-id="e2c1e-202">Om **msdyn\_billingtype** = 192350000, så **Ej debiteringsbar**</span><span class="sxs-lookup"><span data-stu-id="e2c1e-202">If **msdyn\_billingtype** = 192350000, then **NonChargeable**</span></span>  
<span data-ttu-id="e2c1e-203">annars om **msdyn\_billingtype** = 192350001, så **Debiteringsbar**</span><span class="sxs-lookup"><span data-stu-id="e2c1e-203">else if **msdyn\_billingtype** = 192350001, then **Chargeable**</span></span>  
<span data-ttu-id="e2c1e-204">annars om **msdyn\_billingtype** = 192350002, så **Kostnadsfri**</span><span class="sxs-lookup"><span data-stu-id="e2c1e-204">else if **msdyn\_billingtype** = 192350002, then **Complimentary**</span></span>  
<span data-ttu-id="e2c1e-205">annars **Ej tillgänglig**</span><span class="sxs-lookup"><span data-stu-id="e2c1e-205">else **NotAvailable**</span></span>

#### <a name="transform-the-transaction-types"></a><span data-ttu-id="e2c1e-206">Omvandla transaktionstyper.</span><span class="sxs-lookup"><span data-stu-id="e2c1e-206">Transform the transaction types</span></span>

<span data-ttu-id="e2c1e-207">Mallen för projektets utgiftsuppskattningar ("PSA till Fin och Ops") omfattar en villkorlig kolumn som används för att omvandla transaktionstyperna som tas emot från Project Service Automation under integreringen.</span><span class="sxs-lookup"><span data-stu-id="e2c1e-207">The Project expense estimates (PSA to Fin and Ops) template includes a conditional column that is used to transform the transaction types that are received from Project Service Automation during the integration.</span></span> <span data-ttu-id="e2c1e-208">Om du skapar en egen mall måste du lägga till denna villkorliga kolumn.</span><span class="sxs-lookup"><span data-stu-id="e2c1e-208">If you create your own template, you must add this conditional column.</span></span> <span data-ttu-id="e2c1e-209">Markera länken **Avancerade frågor och filter** och välj sedan **Lägg till villkorskolumn**.</span><span class="sxs-lookup"><span data-stu-id="e2c1e-209">Select the **Advanced Query and Filtering** link and then select **Add Conditional Column**.</span></span> <span data-ttu-id="e2c1e-210">Ange ett namn för den nya kolumnen, till exempel **Transaktionstyp**.</span><span class="sxs-lookup"><span data-stu-id="e2c1e-210">Enter a name for the new column, such as **TransactionType**.</span></span> <span data-ttu-id="e2c1e-211">Ange sedan följande tillstånd:</span><span class="sxs-lookup"><span data-stu-id="e2c1e-211">Then enter the following condition:</span></span>

<span data-ttu-id="e2c1e-212">Om **msdyn\_transactiontypecode** = 192350000, så **Kostnad**</span><span class="sxs-lookup"><span data-stu-id="e2c1e-212">If **msdyn\_transactiontypecode** = 192350000, then **Cost**</span></span>  
<span data-ttu-id="e2c1e-213">annars om **msdyn\_transactiontypecode** = 192350005, så **Försäljning**</span><span class="sxs-lookup"><span data-stu-id="e2c1e-213">else if **msdyn\_transactiontypecode** = 192350005, then **Sales**</span></span>  
<span data-ttu-id="e2c1e-214">annars **noll**</span><span class="sxs-lookup"><span data-stu-id="e2c1e-214">else **null**</span></span>

### <a name="template-mapping-in-data-integration"></a><span data-ttu-id="e2c1e-215">Mallmappning i dataintegrering</span><span class="sxs-lookup"><span data-stu-id="e2c1e-215">Template mapping in Data integration</span></span>

<span data-ttu-id="e2c1e-216">I följande illustrationer visas ett exempel på uppgiftsmallmappning i dataintegrering.</span><span class="sxs-lookup"><span data-stu-id="e2c1e-216">The following illustrations show examples of the template task mappings in Data integration.</span></span> <span data-ttu-id="e2c1e-217">Mappningen visar vilken fältinformation som kommer att synkroniseras från Project Service Automation till Finance.</span><span class="sxs-lookup"><span data-stu-id="e2c1e-217">The mapping shows the field information that will be synchronized from Project Service Automation to Finance.</span></span>

<span data-ttu-id="e2c1e-218">[![Mallmappning](./media/ExpenseEstimateTransactionRelationshipsMapping.jpg)](./media/ExpenseEstimateTransactionRelationshipsMapping.jpg)</span><span class="sxs-lookup"><span data-stu-id="e2c1e-218">[![Template mapping](./media/ExpenseEstimateTransactionRelationshipsMapping.jpg)](./media/ExpenseEstimateTransactionRelationshipsMapping.jpg)</span></span>

<span data-ttu-id="e2c1e-219">[![Mallmappning](./media/ExpenseEstimatesMapping.jpg)](./media/ExpenseEstimatesMapping.jpg)</span><span class="sxs-lookup"><span data-stu-id="e2c1e-219">[![Template mapping](./media/ExpenseEstimatesMapping.jpg)](./media/ExpenseEstimatesMapping.jpg)</span></span>
