---
title: "Synkronisera projektuppskattningar från Project Service Automation direkt till projektprognoser i Finance and Operations"
description: "Det här avsnittet beskriver vilka mallar och underliggande uppgifter som används för att synkronisera projektets timuppskattningar och projektets utgiftsupppskattningar från Microsoft Dynamics 365 for Project Service Automation till Dynamics 365 for Finance and Operations."
author: KimANelson
manager: AnnBe
ms.date: 04/02/2018
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
ms.openlocfilehash: 90501f40da0fdc66ad087b3bd746c908cc25711b
ms.contentlocale: sv-se
ms.lasthandoff: 05/29/2018

---
# <a name="synchronize-project-estimates-from-project-service-automation-directly-to-project-forecasts-in-finance-and-operations"></a><span data-ttu-id="786a2-103">Synkronisera projektuppskattningar från Project Service Automation direkt till projektprognoser i Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="786a2-103">Synchronize project estimates from Project Service Automation directly to project forecasts in Finance and Operations</span></span>

<span data-ttu-id="786a2-104">Det här avsnittet beskriver vilka mallar och underliggande uppgifter som används för att synkronisera projektets timuppskattningar och projektets utgiftsupppskattningar från Microsoft Dynamics 365 for Project Service Automation till Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="786a2-104">This topic describes the templates and underlying tasks that are used to synchronize project hour estimates and project expense estimates directly from Microsoft Dynamics 365 for Project Service Automation to Dynamics 365 for Finance and Operations.</span></span>

> [!NOTE]
> <span data-ttu-id="786a2-105">Projektuppgiftsintegration, utgiftstransationskategorier, uppskattningar av timme, uppskattning av utgifter och funktionslåsning är tillgängliga i Dynamics 365 for Finance and Operations version 8.0.</span><span class="sxs-lookup"><span data-stu-id="786a2-105">Project tasks integration, expense transaction categories, hour estimates, expense estimates, and functionality locking is available in Dynamics 365 for Finance and Operations version 8.0.</span></span>


## <a name="data-flow-for-project-service-automation-to-finance-and-operations"></a><span data-ttu-id="786a2-106">Dataflöde för Project Service Automation till Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="786a2-106">Data flow for Project Service Automation to Finance and Operations</span></span>

<span data-ttu-id="786a2-107">Automatisering av integrationslösningen Project Service Automation till Finance and Operations använder funktionen dataintegration för att synkronisera data mellan instanser av Project Service Automation och Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="786a2-107">The Project Service Automation to Finance and Operations integration solution uses the Data integration feature to synchronize data across instances of Project Service Automation and Finance and Operations.</span></span> <span data-ttu-id="786a2-108">Integrationsmallarna som är tillgängliga med dataintegrationsfunktionen möjliggör flödet av data om projektets timuppskattningar och projektets utgiftsupppskattningar från Project Service Automation till Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="786a2-108">The integration templates that are available with the Data integration feature enable the flow of data about project hour estimates and project expense estimates from Project Service Automation to Finance and Operations.</span></span>

<span data-ttu-id="786a2-109">Följande bild visar hur data synkroniseras mellan Project Service Automation och Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="786a2-109">The following illustration shows how the data is synchronized between Project Service Automation and Finance and Operations.</span></span>

<span data-ttu-id="786a2-110">[![Dataflöde för integration av Project Service Automation med Finance and Operations](./media/ProjectEstimatesFlow.png)](./media/ProjectEstimatesFlow.png)</span><span class="sxs-lookup"><span data-stu-id="786a2-110">[![Data flow for Project Service Automation integration with Finance and Operations](./media/ProjectEstimatesFlow.png)](./media/ProjectEstimatesFlow.png)</span></span>


## <a name="templates-and-tasks"></a><span data-ttu-id="786a2-111">Mallar och uppgifter</span><span class="sxs-lookup"><span data-stu-id="786a2-111">Templates and tasks</span></span>

<span data-ttu-id="786a2-112">För att få åtkomst till tillgängliga mallar, i Microsoft PowerApps administratörscenter, välj **projekt**, och i det övre högra hörnet väljer du **nytt projekt** för att välja offentliga mallar.</span><span class="sxs-lookup"><span data-stu-id="786a2-112">To access the available templates, in the Microsoft PowerApps Admin Center, select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="786a2-113">Följande mall och underliggande uppgifter används för att synkronisera projektets timuppskattningar från Project Service Automation till Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="786a2-113">The following template and underlying tasks are used to synchronize project hour estimates from Project Service Automation to Finance and Operations:</span></span>

-  <span data-ttu-id="786a2-114">**Namnet på mallen i dataintegrering:** projektets timuppskattningar (PSA to Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="786a2-114">**Name of the template in Data integration:** Project hour estimates (PSA to Fin and Ops)</span></span>

-  <span data-ttu-id="786a2-115">**Namn på aktiviteter i projektet:**</span><span class="sxs-lookup"><span data-stu-id="786a2-115">**Name of the tasks in the project:**</span></span> 
    - <span data-ttu-id="786a2-116">Transaktionsrelationer</span><span class="sxs-lookup"><span data-stu-id="786a2-116">Transaction relationships</span></span> 
    - <span data-ttu-id="786a2-117">Utgiftsuppskattning</span><span class="sxs-lookup"><span data-stu-id="786a2-117">Expense estimates</span></span>

## <a name="entity-set"></a><span data-ttu-id="786a2-118">Ange entiteten</span><span class="sxs-lookup"><span data-stu-id="786a2-118">Entity set</span></span>

| <span data-ttu-id="786a2-119">Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="786a2-119">Project Service Automation</span></span>      | <span data-ttu-id="786a2-120">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="786a2-120">Finance and Operations</span></span>                          |
|---------------------------------|-------------------------------------------------|
| <span data-ttu-id="786a2-121">Projektuppgifter</span><span class="sxs-lookup"><span data-stu-id="786a2-121">Project tasks</span></span>                   | <span data-ttu-id="786a2-122">Integrationsenhet för projektets timuppskattningar</span><span class="sxs-lookup"><span data-stu-id="786a2-122">Integration entity for project hour estimates</span></span>   |

## <a name="entity-flow"></a><span data-ttu-id="786a2-123">Flöde för entitet</span><span class="sxs-lookup"><span data-stu-id="786a2-123">Entity flow</span></span>

<span data-ttu-id="786a2-124">Projektets timuppskattningar hanteras i Project Service Automation och de synkroniseras till Finance and Operations som timprognoser i projekt.</span><span class="sxs-lookup"><span data-stu-id="786a2-124">Project hour estimates are managed in Project Service Automation, and they are synchronized to Finance and Operations as project hour forecasts.</span></span>

## <a name="preconditions"></a><span data-ttu-id="786a2-125">Förvillkor</span><span class="sxs-lookup"><span data-stu-id="786a2-125">Preconditions</span></span>

<span data-ttu-id="786a2-126">Innan synkroniseringen av projektets uppskattade timmar kan utföras måste du synkronisera projekt, projektuppgifter och transaktionskategorier för projektutgifter.</span><span class="sxs-lookup"><span data-stu-id="786a2-126">Before synchronization of project hour estimates can occur, you must synchronize projects, project tasks, and project expense transaction categories.</span></span>

## <a name="power-query"></a><span data-ttu-id="786a2-127">Power Query</span><span class="sxs-lookup"><span data-stu-id="786a2-127">Power Query</span></span>

<span data-ttu-id="786a2-128">Du måste använda Microsoft Power Query i mallen för projektets timuppskattningar:</span><span class="sxs-lookup"><span data-stu-id="786a2-128">You must use Microsoft Power Query in the project hour estimates template to:</span></span>
- <span data-ttu-id="786a2-129">Ange det **Prognosmodell-ID** som ska användas när integrationen skapar nya timprognoser.</span><span class="sxs-lookup"><span data-stu-id="786a2-129">Set the **Forecast model ID** that will be used when the integration creates new hour forecasts.</span></span>
- <span data-ttu-id="786a2-130">Filtrera bort alla resursspecifika poster i uppgiften som misslyckas med integrationen i timuppskattningar</span><span class="sxs-lookup"><span data-stu-id="786a2-130">Filter out any resource specific records within the task that will fail the integration into hour forecasts</span></span>
- <span data-ttu-id="786a2-131">Filtrera bort alla tomma transaktionskategorirader.</span><span class="sxs-lookup"><span data-stu-id="786a2-131">Filter out any empty transaction category rows.</span></span> <span data-ttu-id="786a2-132">Om du inte gör detta kan det resultera i fel timprognoser.</span><span class="sxs-lookup"><span data-stu-id="786a2-132">Failure to do this may result in incorrect hour forecasts.</span></span>

### <a name="forecast-model-id"></a><span data-ttu-id="786a2-133">Prognosmodell-ID</span><span class="sxs-lookup"><span data-stu-id="786a2-133">Forecast model ID</span></span>
<span data-ttu-id="786a2-134">För att uppdatera standardprognosmodell-ID i mallen, klicka på pilen **Mapp** för att öppna mappningen.</span><span class="sxs-lookup"><span data-stu-id="786a2-134">To update the default forecast model ID in the template, click the **Map** arrow to open the mapping.</span></span> <span data-ttu-id="786a2-135">Välj för att öppna avancerad fråga och filtrering.</span><span class="sxs-lookup"><span data-stu-id="786a2-135">Select to open the Advanced Query and Filtering.</span></span>
- <span data-ttu-id="786a2-136">Om du använder standardmallen Microsoft mallen timuppskattningar (PSA till Fin and Ops), välj **Infogat villkor** i avsnittet **Tillämpade steg**.</span><span class="sxs-lookup"><span data-stu-id="786a2-136">If you are using the default Microsoft Project hour estimates (PSA to Fin and Ops) template, select the **Inserted Condition** in the **Applied Steps** section.</span></span> <span data-ttu-id="786a2-137">I posten **funktion**, ersätt **O_forecast** med namnet på den **Prognosmodell-ID** som ska användas med integrationen.</span><span class="sxs-lookup"><span data-stu-id="786a2-137">In the **Function** entry, replace **O_forecast** with the name of the **Forecast model ID** that should be used with the integration.</span></span> <span data-ttu-id="786a2-138">Standardmallen har en prognosmodell från demonstrationsdata.</span><span class="sxs-lookup"><span data-stu-id="786a2-138">The default template has a forecast model ID from the demo data.</span></span>
- <span data-ttu-id="786a2-139">Om du skapar en ny mall måste du lägga till den här kolumnen.</span><span class="sxs-lookup"><span data-stu-id="786a2-139">If you are creating a new template, you must add this column.</span></span> <span data-ttu-id="786a2-140">Välj **lägga till villkorlig kolumn** och ge kolumnen ett namn, till exempel ModelID.</span><span class="sxs-lookup"><span data-stu-id="786a2-140">Select **Add Conditional Column** and give the column a name, such as ModelID.</span></span> <span data-ttu-id="786a2-141">Ange villkor för kolumnen där om projectuppgiften inte null <enter the forecast model ID>; annars null.</span><span class="sxs-lookup"><span data-stu-id="786a2-141">Enter the condition for the column where if Project task is not null, then<enter the forecast model ID>; else null.</span></span>

### <a name="filter-out-resource-specific-records"></a><span data-ttu-id="786a2-142">Filtrera ut resursspecifika poster</span><span class="sxs-lookup"><span data-stu-id="786a2-142">Filter out resource specific records</span></span>
<span data-ttu-id="786a2-143">Mallen för projektets timuppskattningar (PSA till Fin and Ops) har ett standardfilter som tar bort alla resursspecifika poster.</span><span class="sxs-lookup"><span data-stu-id="786a2-143">The Project hour estimates (PSA to Fin and Ops) template has a default filter that removes any resource specific records.</span></span> <span data-ttu-id="786a2-144">Om du skapar en egen mall måste du lägga till filtret.</span><span class="sxs-lookup"><span data-stu-id="786a2-144">If you create your own template, you must add this filter.</span></span> <span data-ttu-id="786a2-145">I formuläret för avancerad fråga och filtrering, välj filter på kolumnen **msdyn_islinetask** för att endast inkludera posterna **falsk**.</span><span class="sxs-lookup"><span data-stu-id="786a2-145">In the Advanced Query and Filtering form, select to filter on the column **msdyn_islinetask** to only include **False** records.</span></span>

### <a name="filter-out-empty-transaction-category-rows"></a><span data-ttu-id="786a2-146">Filtrera bort alla tomma transaktionskategorirader.</span><span class="sxs-lookup"><span data-stu-id="786a2-146">Filter out empty transaction category rows</span></span>
<span data-ttu-id="786a2-147">Du måste lägga till ett filter för att ta bort alla rader med tomma transaktionskategorier.</span><span class="sxs-lookup"><span data-stu-id="786a2-147">You must add a filter to remove any rows with empty transaction categories.</span></span> <span data-ttu-id="786a2-148">Det behövs oavsett om du använder standardmallen eller om du skapar en egen mall.</span><span class="sxs-lookup"><span data-stu-id="786a2-148">This is needed regardless if you are using the default template or creating your own template.</span></span> <span data-ttu-id="786a2-149">Detta filter tar bort alla sammanfattningsrader från Project Service Automation som kan medföra att timprognoser i Finance and Operations är felaktiga.</span><span class="sxs-lookup"><span data-stu-id="786a2-149">This filter will remove any summary rows coming from Project Service Automation that could cause the hour forecasts in Finance and Operations to be incorrect.</span></span> <span data-ttu-id="786a2-150">I formuläret avancerad sökning och filtrering väljer du att filtrera bort nullposterna i kolumnen **msdyn_transactioncategory_value**.</span><span class="sxs-lookup"><span data-stu-id="786a2-150">In the Advanced Query and Filtering form, select to filter out the null records in the column **msdyn_transactioncategory_value**.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="786a2-151">Mallmappning i dataintegrering</span><span class="sxs-lookup"><span data-stu-id="786a2-151">Template mapping in Data integration</span></span>

<span data-ttu-id="786a2-152">I följande illustration visas ett exempel på uppgiftsmallmappning i dataintegrering.</span><span class="sxs-lookup"><span data-stu-id="786a2-152">The following illustration shows an example of the template task mapping in Data integration.</span></span> <span data-ttu-id="786a2-153">Mappningen visar vilken fältinformation som kommer att synkroniseras från Project Service Automation till Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="786a2-153">The mapping shows the field information that will be synchronized from Project Service Automation to Finance and Operations.</span></span>

<span data-ttu-id="786a2-154">[![Mallmappning](./media/ProjectHourEstimatesMapping.jpg)](./media/ProjectHourEstimatesMapping.jpg)</span><span class="sxs-lookup"><span data-stu-id="786a2-154">[![Template mapping](./media/ProjectHourEstimatesMapping.jpg)](./media/ProjectHourEstimatesMapping.jpg)</span></span>

<span data-ttu-id="786a2-155">Följande mall och underliggande uppgift används för att synkronisera projektets utgiftsuppskattningar från Project Service Automation till Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="786a2-155">The following template and underlying task is used to synchronize project expense estimates from Project Service Automation to Finance and Operations:</span></span>

-  <span data-ttu-id="786a2-156">**Namnet på mallen i dataintegrering:** projektets utgiftsupppskattningar (PSA to Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="786a2-156">**Name of the template in Data integration:** Project expense estimates (PSA to Fin and Ops)</span></span>
-  <span data-ttu-id="786a2-157">**Namn på aktiviteter i projektet:**</span><span class="sxs-lookup"><span data-stu-id="786a2-157">**Name of the tasks in the project:**</span></span> 
     - <span data-ttu-id="786a2-158">Transaktionsrelationer</span><span class="sxs-lookup"><span data-stu-id="786a2-158">Transaction relationships</span></span> 
     - <span data-ttu-id="786a2-159">Utgiftsuppskattning</span><span class="sxs-lookup"><span data-stu-id="786a2-159">Expense estimates</span></span>

## <a name="entity-set"></a><span data-ttu-id="786a2-160">Ange entiteten</span><span class="sxs-lookup"><span data-stu-id="786a2-160">Entity set</span></span>

| <span data-ttu-id="786a2-161">Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="786a2-161">Project Service Automation</span></span>      | <span data-ttu-id="786a2-162">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="786a2-162">Finance and Operations</span></span>                                     |
|---------------------------------|------------------------------------------------------------|
| <span data-ttu-id="786a2-163">Transaktionsanslutningar</span><span class="sxs-lookup"><span data-stu-id="786a2-163">Transaction Connections</span></span>         | <span data-ttu-id="786a2-164">Integrationsenhet för projektets transaktionsrelationer</span><span class="sxs-lookup"><span data-stu-id="786a2-164">Integration entity for project transaction relationships.</span></span>   |
| <span data-ttu-id="786a2-165">Uppskattningsrader</span><span class="sxs-lookup"><span data-stu-id="786a2-165">Estimate Lines</span></span>                  | <span data-ttu-id="786a2-166">Integrationsenhet för projektets utgiftsupppskattningar</span><span class="sxs-lookup"><span data-stu-id="786a2-166">Integration entity for project expense estimates.</span></span>           |

## <a name="entity-flow"></a><span data-ttu-id="786a2-167">Flöde för entitet</span><span class="sxs-lookup"><span data-stu-id="786a2-167">Entity flow</span></span>

<span data-ttu-id="786a2-168">Projektets utgiftsupppskattningar hanteras i Project Service Automation och de synkroniseras till Finance and Operations som utgiftsprognoser i projekt.</span><span class="sxs-lookup"><span data-stu-id="786a2-168">Project expense estimates are managed in Project Service Automation, and they are synchronized to Finance and Operations as project expense forecasts.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="786a2-169">Krav</span><span class="sxs-lookup"><span data-stu-id="786a2-169">Prerequisites</span></span>

<span data-ttu-id="786a2-170">Innan synkroniseringen av projektets utgiftsupppskattningar kan utföras måste du synkronisera projekt, projektuppgifter och transaktionskategorier för projektutgifter.</span><span class="sxs-lookup"><span data-stu-id="786a2-170">Before synchronization of project expense estimates can occur, you must synchronize Projects, Project tasks and Project expense transaction categories.</span></span>

## <a name="power-query"></a><span data-ttu-id="786a2-171">Power Query</span><span class="sxs-lookup"><span data-stu-id="786a2-171">Power Query</span></span>

<span data-ttu-id="786a2-172">Du måste använda Microsoft Power Query i mallen för projektets utgiftsupppskattningar:</span><span class="sxs-lookup"><span data-stu-id="786a2-172">You must use Microsoft Power Query in the project expense estimates template to:</span></span>
- <span data-ttu-id="786a2-173">Filtrera med endast uppskattade utgiftsradsposter</span><span class="sxs-lookup"><span data-stu-id="786a2-173">Filter to include only expense estimate line records</span></span>
- <span data-ttu-id="786a2-174">Ange det **Prognosmodell-ID** som ska användas när integrationen skapar nya timprognoser.</span><span class="sxs-lookup"><span data-stu-id="786a2-174">Set the **Forecast model ID** that will be used when the integration creates new hour forecasts.</span></span>
- <span data-ttu-id="786a2-175">Omvandla faktureringstyper.</span><span class="sxs-lookup"><span data-stu-id="786a2-175">Transform the billing types.</span></span>
- <span data-ttu-id="786a2-176">Omvandla transaktionstyper.</span><span class="sxs-lookup"><span data-stu-id="786a2-176">Transform the transaction types.</span></span>

### <a name="filter-to-include-only-expense-estimate-lines"></a><span data-ttu-id="786a2-177">Filtrera med endast uppskattade utgiftsposter</span><span class="sxs-lookup"><span data-stu-id="786a2-177">Filter to include only expense estimate lines</span></span>
<span data-ttu-id="786a2-178">Mallen för projektets utgiftsupppskattningar (PSA till Fin and Ops) har ett standardfilter som endast inkluderar endast utgiftsrader i integrationen.</span><span class="sxs-lookup"><span data-stu-id="786a2-178">The Project expense estimates (PSA to Fin and Ops) template has a default filter to only include expense lines in the integration.</span></span> <span data-ttu-id="786a2-179">Om du skapar en egen mall måste du lägga till filtret.</span><span class="sxs-lookup"><span data-stu-id="786a2-179">If you create your own template, you must add this filter.</span></span> <span data-ttu-id="786a2-180">Markera uppgifter för transaktionsrelationer och klicka på pilen **Mapp**.</span><span class="sxs-lookup"><span data-stu-id="786a2-180">Select the Transaction relationships task and click the **Map** arrow.</span></span> <span data-ttu-id="786a2-181">Välj **Avancerad fråga och filtrering**</span><span class="sxs-lookup"><span data-stu-id="786a2-181">Select **Advanced Query and filtering**.</span></span> <span data-ttu-id="786a2-182">Filtrera kolumnen **msdyn_transactiontype1** så att den endast innehåller **msdyn_estimateline**.</span><span class="sxs-lookup"><span data-stu-id="786a2-182">Filter the **msdyn_transactiontype1** column to include only **msdyn_estimateline**.</span></span>

### <a name="forecast-model-id"></a><span data-ttu-id="786a2-183">Prognosmodell-ID</span><span class="sxs-lookup"><span data-stu-id="786a2-183">Forecast model ID</span></span>
<span data-ttu-id="786a2-184">För att uppdatera standardprognosmodell-ID i mallen, för uppgiften utgiftsuppskattningar, klicka på pilen **Mapp** för att öppna mappningen.</span><span class="sxs-lookup"><span data-stu-id="786a2-184">To update the default forecast model ID in the template, for the Expense estimates task, click the **Map** arrow to open the mapping.</span></span> <span data-ttu-id="786a2-185">Välj för att öppna avancerad fråga och filtrering.</span><span class="sxs-lookup"><span data-stu-id="786a2-185">Select to open the Advanced Query and Filtering.</span></span>
- <span data-ttu-id="786a2-186">Om du använder standardmallen Microsoft mallen utgiftsuppskattningar (PSA till Fin and Ops), välj först **Infogat villkor** i avsnittet **Tillämpade steg**.</span><span class="sxs-lookup"><span data-stu-id="786a2-186">If you are using the default Microsoft Project expense estimates (PSA to Fin and Ops) template, select the first **Inserted Condition** in the **Applied Steps** section.</span></span> <span data-ttu-id="786a2-187">I posten **funktion**, ersätt **O_forecast** med namnet på den **Prognosmodell-ID** som ska användas med integrationen.</span><span class="sxs-lookup"><span data-stu-id="786a2-187">In the **Function** entry, replace **O_forecast** with the name of the **Forecast model ID** that should be used with the integration.</span></span> <span data-ttu-id="786a2-188">Standardmallen har en prognosmodell från demonstrationsdata.</span><span class="sxs-lookup"><span data-stu-id="786a2-188">The default template has a forecast model ID from the demo data.</span></span>
- <span data-ttu-id="786a2-189">Om du skapar en ny mall måste du lägga till den här kolumnen.</span><span class="sxs-lookup"><span data-stu-id="786a2-189">If you are creating a new template, you must add this column.</span></span> <span data-ttu-id="786a2-190">Välj **lägga till villkorlig kolumn** och ge kolumnen ett namn, till exempel ModelID.</span><span class="sxs-lookup"><span data-stu-id="786a2-190">Select **Add Conditional Column** and give the column a name, such as ModelID.</span></span> <span data-ttu-id="786a2-191">Ange villkor för kolumnen däruppskattningsrad-ID inte är null och < Ange prognosmodell-ID >; annars null.</span><span class="sxs-lookup"><span data-stu-id="786a2-191">Enter the condition for the column where if Estimate line ID is not null, then < enter the forecast model ID >; else null.</span></span>

### <a name="transform-the-billing-types"></a><span data-ttu-id="786a2-192">Omvandla faktureringstyper.</span><span class="sxs-lookup"><span data-stu-id="786a2-192">Transform the billing types</span></span>
<span data-ttu-id="786a2-193">Mallen för projektets utgiftsupppskattningar (PSA till Fin and Ops) har en villkorlig kolumn tillagd för att omvandla faktureringstyperna som tas emot från Project Service Automation under integreringen.</span><span class="sxs-lookup"><span data-stu-id="786a2-193">The Project expense estimates (PSA to Fin and Ops) template has a conditional column added to transform the billing types received from Project Service Automation during the integration.</span></span>
- <span data-ttu-id="786a2-194">Om du skapar en egen mall måste du lägga till denna villkorliga kolumn.</span><span class="sxs-lookup"><span data-stu-id="786a2-194">If you create your own template, you must add this conditional column.</span></span> <span data-ttu-id="786a2-195">Välj i formuläret avancerad fråga och filtrering, lägg till **lägga till villkorliga kolumnen**.</span><span class="sxs-lookup"><span data-stu-id="786a2-195">In the Advanced Query and Filtering form, select **Add Conditional Column**.</span></span> <span data-ttu-id="786a2-196">Namnge den nya kolumnen, till exempel BillingType.</span><span class="sxs-lookup"><span data-stu-id="786a2-196">Give the column a name, such as "BillingType".</span></span> <span data-ttu-id="786a2-197">Villkoret att ange är följande:</span><span class="sxs-lookup"><span data-stu-id="786a2-197">The condition to enter is as follows:</span></span>

    <span data-ttu-id="786a2-198">Om **msdyn_billingtype** = 192350000, sedan **NonChargeable** annars om **msdyn_billingtype** = 192350001, sedan **Chargeable** annars om **msdyn_billingtype** = 192350002, sedan **Complimentary** annars **NotAvailable**</span><span class="sxs-lookup"><span data-stu-id="786a2-198">If **msdyn_billingtype** = 192350000, then **NonChargeable** else if **msdyn_billingtype** = 192350001, then **Chargeable** else if **msdyn_billingtype** = 192350002, then **Complimentary** else **NotAvailable**</span></span>

### <a name="transform-the-transaction-types"></a><span data-ttu-id="786a2-199">Omvandla transaktionstyper.</span><span class="sxs-lookup"><span data-stu-id="786a2-199">Transform the transaction types</span></span>
<span data-ttu-id="786a2-200">Mallen för projektets utgiftsupppskattningar (PSA till Fin and Ops) har en villkorlig kolumn tillagd för att omvandla transaktionstyperna som tas emot från Project Service Automation under integreringen.</span><span class="sxs-lookup"><span data-stu-id="786a2-200">The Project expense estimates (PSA to Fin and Ops) template has a conditional column added to transform the transaction types received from Project Service Automation during the integration.</span></span>
- <span data-ttu-id="786a2-201">Om du skapar en egen mall måste du lägga till denna villkorliga kolumn.</span><span class="sxs-lookup"><span data-stu-id="786a2-201">If you create your own template, you must add this conditional column.</span></span> <span data-ttu-id="786a2-202">Välj i formuläret avancerad fråga och filtrering, lägg till **lägga till villkorliga kolumnen**.</span><span class="sxs-lookup"><span data-stu-id="786a2-202">In the Advanced Query and Filtering form, select **Add Conditional Column**.</span></span> <span data-ttu-id="786a2-203">Namnge den nya kolumnen, till exempel TransactionType.</span><span class="sxs-lookup"><span data-stu-id="786a2-203">Give the column a name, such as "TransactionType".</span></span> <span data-ttu-id="786a2-204">Villkoret som ska anges är följande: om **msdyn_transactiontypecode** = 192350000, sedan **kostnad** annars om **msdyn_transactiontypecode** = 192350005, sedan **försäljning** annars **null**</span><span class="sxs-lookup"><span data-stu-id="786a2-204">The condition to enter is as follows: If **msdyn_transactiontypecode** = 192350000, then **Cost** else if **msdyn_transactiontypecode** = 192350005, then **Sales** else **null**</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="786a2-205">Mallmappning i dataintegrering</span><span class="sxs-lookup"><span data-stu-id="786a2-205">Template mapping in Data integration</span></span>

<span data-ttu-id="786a2-206">I följande illustrationer visas ett exempel på uppgiftsmallmappning i dataintegrering.</span><span class="sxs-lookup"><span data-stu-id="786a2-206">The following illustrations show examples of the template task mappings in Data integration.</span></span> <span data-ttu-id="786a2-207">Mappningen visar vilken fältinformation som kommer att synkroniseras från Project Service Automation till Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="786a2-207">The mapping shows the field information that will be synchronized from Project Service Automation to Finance and Operations.</span></span>

<span data-ttu-id="786a2-208">[![Mallmappning](./media/ExpenseEstimateTransactionRelationshipsMapping.jpg)](./media/ExpenseEstimateTransactionRelationshipsMapping.jpg)</span><span class="sxs-lookup"><span data-stu-id="786a2-208">[![Template mapping](./media/ExpenseEstimateTransactionRelationshipsMapping.jpg)](./media/ExpenseEstimateTransactionRelationshipsMapping.jpg)</span></span>

<span data-ttu-id="786a2-209">[![Mallmappning](./media/ExpenseEstimatesMapping.jpg)](./media/ExpenseEstimatesMapping.jpg)</span><span class="sxs-lookup"><span data-stu-id="786a2-209">[![Template mapping](./media/ExpenseEstimatesMapping.jpg)](./media/ExpenseEstimatesMapping.jpg)</span></span>



