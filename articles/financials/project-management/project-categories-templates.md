---
title: "Synkronisera projektuppgiftskategorier från Project Service Automation"
description: "Det här avsnittet beskriver vilka mallar och underliggande uppgifter som används för att synkronisera projektuppgiftskategorier mellan Microsoft Dynamics 365 for Finance and Operations och Dynamics 365 for Project Service Automation."
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
ms.dyn365.ops.version: AX 8.0.0
ms.translationtype: HT
ms.sourcegitcommit: bd8feff598cf80ca675c7d2b5dda636799b19e29
ms.openlocfilehash: dcdb9b6ec296073d511c069cdceb1c61080b6d97
ms.contentlocale: sv-se
ms.lasthandoff: 05/29/2018

---

# <a name="synchronize-project-expense-categories-between-finance-and-operations-and-project-service-automation"></a><span data-ttu-id="fcc48-103">Synkronisera projektutgiftskategorier mellan Finance and Operations och Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="fcc48-103">Synchronize project expense categories between Finance and Operations and Project Service Automation</span></span>

<span data-ttu-id="fcc48-104">Det här avsnittet beskriver vilka mallar och underliggande uppgifter som används för att synkronisera projektuppgiftskategorier mellan Microsoft Dynamics 365 for Finance and Operations och Dynamics 365 for Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="fcc48-104">This topic describes the templates and underlying tasks that are used to synchronize project expense categories between Microsoft Dynamics 365 for Finance and Operations and Dynamics 365 for Project Service Automation.</span></span>

> [!NOTE]
> <span data-ttu-id="fcc48-105">Projektuppgiftsintegration, utgiftstransationskategorier, uppskattningar av timme, uppskattning av utgifter och funktionslåsning är tillgängliga i Dynamics 365 for Finance and Operations version 8.0.</span><span class="sxs-lookup"><span data-stu-id="fcc48-105">Project tasks integration, expense transaction categories, hour estimates, expense estimates, and functionality locking is available in Dynamics 365 for Finance and Operations version 8.0.</span></span>

## <a name="data-flow-for-project-service-automation-and-finance-and-operations"></a><span data-ttu-id="fcc48-106">Dataflöde för Project Service Automation och Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="fcc48-106">Data flow for Project Service Automation and Finance and Operations</span></span>

<span data-ttu-id="fcc48-107">Automatisering av integrationslösningen Project Service Automation och Finance and Operations använder funktionen dataintegration för att synkronisera data mellan instanser av Project Service Automation och Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="fcc48-107">The Project Service Automation and Finance and Operations integration solution uses the Data integration feature to synchronize data across instances of Project Service Automation and Finance and Operations.</span></span> <span data-ttu-id="fcc48-108">Integrationsmallarna som är tillgängliga med dataintegrationsfunktionen möjliggör flödet av data om transaktionskategorier för projektutgifter mellan Finance and Operations och Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="fcc48-108">The integration templates that are available with the Data integration feature enables the flow of data about project expense transaction categories between Finance and Operations and Project Service Automation.</span></span>

<span data-ttu-id="fcc48-109">Om projektets utgiftskategorier hanteras i Finance and Operations, är integrationsflödet först från Finance and Operations till Project Service Automation och sedan uppdateras integrations-ID för projektets utgiftskategorier genom att synkronisera från Project Service Automation till Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="fcc48-109">If the project expense categories are mastered in Finance and Operations, the integration flow is first from Finance and Operations to Project Service Automation, and then updating the project expense categories integration IDs by synchronizing from Project Service Automation to Finance and Operations.</span></span>

<span data-ttu-id="fcc48-110">Om projektets utgiftskategorier hanteras i Project Service Automation, är integrationsflödet först från Project Service Automation till Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="fcc48-110">If the project expense categories are mastered in Project Service Automation, the integration flow is first from Project Service Automation to Finance and Operations.</span></span> <span data-ttu-id="fcc48-111">Projektkategorier måste också vara konfigurerade i Finance and Operations före synkronisering från Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="fcc48-111">The project categories must already be configured in Finance and Operations prior to the synchronization from Project Service Automation.</span></span> <span data-ttu-id="fcc48-112">Synkronisera sedan från Finance and Operations tillbaka till Project Service Automation och sedan från Project Service Automation till Finance and Operations igen.</span><span class="sxs-lookup"><span data-stu-id="fcc48-112">Then synchronize from Finance and Operations back to Project Service Automation and then from Project Service Automation to Finance and Operations again.</span></span> <span data-ttu-id="fcc48-113">Detta säkerställer att kategorier länkas och dubbletter skapas inte.</span><span class="sxs-lookup"><span data-stu-id="fcc48-113">This ensures the categories are linked and duplicates are not created.</span></span>

> [!NOTE]
> <span data-ttu-id="fcc48-114">Vanligtvis kommer projektets utgiftskategorier att hanteras i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="fcc48-114">Typically, the project expense categories will be mastered in Finance and Operations.</span></span> <span data-ttu-id="fcc48-115">Om detta inte är din situation och du redan har utgiftskategorier skapade i Project Service Automation måste du först synkronisera med projektets utgiftstransaktionskategorier (PSA till Fin and Ops) och sedan synkronisera med projektets utgiftstransaktionskategorier (Fin and Ops till PSA).</span><span class="sxs-lookup"><span data-stu-id="fcc48-115">If that is not your situation, or you already have expense categories created in Project Service Automation, you must first sync using the Project expense transaction categories (PSA to Fin and Ops) and then sync using Project expense transaction categories (Fin and Ops to PSA).</span></span> <span data-ttu-id="fcc48-116">Du bör sedan köra synkroniseringen från PSA till Fin and Ops en gång.</span><span class="sxs-lookup"><span data-stu-id="fcc48-116">You should then run the sync from PSA to Fin and Ops one more time.</span></span>

> <span data-ttu-id="fcc48-117">Om du först synkroniseras från Project Service Automation måste projektkategorier redan ställas in i Finance and Operations och eventuella projektkategorier måste vara synkroniserade med transaktionskategorier i Project Service Automation som måste vara inställda på **Aktiva i journaler**.</span><span class="sxs-lookup"><span data-stu-id="fcc48-117">If synchronizing first from Project Service Automation, the project categories must already be set up in Finance and Operations and any project categories that need to be synched with the Project Service Automation transaction categories must be set up to be **Active in journals**.</span></span>

<span data-ttu-id="fcc48-118">Följande bild visar hur data synkroniseras mellan Project Service Automation och Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="fcc48-118">The following illustration shows how the data is synchronized between Project Service Automation and Finance and Operations.</span></span>

<span data-ttu-id="fcc48-119">[![Dataflöde för integration av Project Service Automation med Finance and Operations](./media/ProjectExpenseCategoriesFlow.png)](./media/ProjectExpenseCategoriesFlow.png)</span><span class="sxs-lookup"><span data-stu-id="fcc48-119">[![Data flow for Project Service Automation integration with Finance and Operations](./media/ProjectExpenseCategoriesFlow.png)](./media/ProjectExpenseCategoriesFlow.png)</span></span>


## <a name="templates-and-tasks"></a><span data-ttu-id="fcc48-120">Mallar och uppgifter</span><span class="sxs-lookup"><span data-stu-id="fcc48-120">Templates and tasks</span></span>

<span data-ttu-id="fcc48-121">För att få åtkomst till tillgängliga mallar, i Microsoft PowerApps administratörscenter, välj **projekt**, och i det övre högra hörnet väljer du **nytt projekt** för att välja offentliga mallar.</span><span class="sxs-lookup"><span data-stu-id="fcc48-121">To access available templates, in the Microsoft PowerApps Admin Center, select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="fcc48-122">Följande mall och underliggande uppgift används för att synkronisera projektets utgiftskategorier från Finance and Operations till Project Service Automation:</span><span class="sxs-lookup"><span data-stu-id="fcc48-122">The following template and underlying task is used to synchronize project expense categories from Finance and Operations to Project Service Automation:</span></span>

-  <span data-ttu-id="fcc48-123">**Namnet på mallen i dataintegrering:**  projektets utgiftstransaktionskategorier (Fin and Ops till PSA)</span><span class="sxs-lookup"><span data-stu-id="fcc48-123">**Name of the template in Data integration:** Project expense transaction categories (Fin and Ops to PSA)</span></span>
-  <span data-ttu-id="fcc48-124">**Namnet på uppgiften i projektet:** synkronisera kategorier till PSA</span><span class="sxs-lookup"><span data-stu-id="fcc48-124">**Name of the task in the project:** Sync categories to PSA</span></span>

## <a name="entity-set"></a><span data-ttu-id="fcc48-125">Ange entiteten</span><span class="sxs-lookup"><span data-stu-id="fcc48-125">Entity set</span></span>

| <span data-ttu-id="fcc48-126">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="fcc48-126">Finance and Operations</span></span>               | <span data-ttu-id="fcc48-127">Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="fcc48-127">Project Service Automation</span></span>    |
|--------------------------------------|-------------------------------|
| <span data-ttu-id="fcc48-128">Integrationsenhet för kategorier</span><span class="sxs-lookup"><span data-stu-id="fcc48-128">Integration entity for categories</span></span>    | <span data-ttu-id="fcc48-129">Transaktionskategorier</span><span class="sxs-lookup"><span data-stu-id="fcc48-129">Transaction categories</span></span>        |

## <a name="entity-flow"></a><span data-ttu-id="fcc48-130">Flöde för entitet</span><span class="sxs-lookup"><span data-stu-id="fcc48-130">Entity flow</span></span>

<span data-ttu-id="fcc48-131">Projektets utgiftskategorier hanteras i Finance and Operations och de synkroniseras till Project Service Automation som transaktionskategorier.</span><span class="sxs-lookup"><span data-stu-id="fcc48-131">Project expense categories are managed in Finance and Operations, and they are synchronized to Project Service Automation as transaction categories.</span></span>

## <a name="power-query"></a><span data-ttu-id="fcc48-132">Power Query</span><span class="sxs-lookup"><span data-stu-id="fcc48-132">Power Query</span></span>

<span data-ttu-id="fcc48-133">Du måste använda Microsoft Power Query för att ställa in faktureringstypen på transaktionskategorin när du synkroniserar till Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="fcc48-133">You must use Microsoft Power Query to set the billing type on the transaction category when synchronizing to Project Service Automation.</span></span> <span data-ttu-id="fcc48-134">Mallen för projektets utgiftstransaktionskategorier (Fin and Ops till PSA) har en standardkolumn och mappning finns redan.</span><span class="sxs-lookup"><span data-stu-id="fcc48-134">The Project expense transaction categories (Fin and Ops to PSA) template has a default column and mapping already provided.</span></span> <span data-ttu-id="fcc48-135">Om du skapar en egen mall måste du lägga till en villkorlig kolumn i Power Query.</span><span class="sxs-lookup"><span data-stu-id="fcc48-135">If you create your own template, you must add a conditional column in Power Query.</span></span>
- <span data-ttu-id="fcc48-136">Öppna Advance Query och filtreringsformulär inifrån mappningen av projektets utgiftskategoriuppgifter.</span><span class="sxs-lookup"><span data-stu-id="fcc48-136">Open the Advance Query and Filtering form from within the mapping of project expense categories task.</span></span>
- <span data-ttu-id="fcc48-137">Välj **lägga till villkorlig kolumn**.</span><span class="sxs-lookup"><span data-stu-id="fcc48-137">Select **Add Conditional Column**.</span></span>
- <span data-ttu-id="fcc48-138">Namnge den nya kolumnen, till exempel BillingType.</span><span class="sxs-lookup"><span data-stu-id="fcc48-138">Give the new column a name, such as BillingType.</span></span>
- <span data-ttu-id="fcc48-139">Ange följande villkor: om **CATEGORYID inte är lika med noll sedan 19235001, annars noll**.</span><span class="sxs-lookup"><span data-stu-id="fcc48-139">Enter the following condition: if **CATEGORYID not equal to null then 19235001, Otherwise null**.</span></span>
- <span data-ttu-id="fcc48-140">Klicka **OK** på kolumnen.</span><span class="sxs-lookup"><span data-stu-id="fcc48-140">Click **OK** on the column.</span></span>
- <span data-ttu-id="fcc48-141">Måste du mappa den här nya kolumnen på mappningssidan.</span><span class="sxs-lookup"><span data-stu-id="fcc48-141">Be sure to map this new column in the mapping page.</span></span>

<span data-ttu-id="fcc48-142">I följande illustration visas ett exempel på uppgiftsmallmappning i dataintegrering.</span><span class="sxs-lookup"><span data-stu-id="fcc48-142">The following illustration shows an example of the template task mapping in Data integration.</span></span> <span data-ttu-id="fcc48-143">Mappningen visar vilken fältinformation som kommer att synkroniseras från Finance and Operations till Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="fcc48-143">The mapping shows the field information that will be synchronized from Finance and Operations to Project Service Automation.</span></span>

<span data-ttu-id="fcc48-144">[![Mallmappning](./media/ProjectExpenseCategoriesToPSAMapping.jpg)](./media/ProjectExpenseCategoriesToPSAMapping.jpg)</span><span class="sxs-lookup"><span data-stu-id="fcc48-144">[![Template mapping](./media/ProjectExpenseCategoriesToPSAMapping.jpg)](./media/ProjectExpenseCategoriesToPSAMapping.jpg)</span></span>

<span data-ttu-id="fcc48-145">Följande mall och underliggande uppgift används för att synkronisera projektets utgiftskategorier från Finance and Operations till Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="fcc48-145">The following template and underlying task is used to synchronize project expense categories from Project Service Automation to Finance and Operations:</span></span>

<span data-ttu-id="fcc48-146">-**Namnet på mallen för dataintegrering:** projektets utgiftstransaktionskategorier (PSA till Fin and Ops) -**namnet på uppgiften i projektet:** synkronisera kategorier till Fin Ops</span><span class="sxs-lookup"><span data-stu-id="fcc48-146">-**Name of the template in Data integration:** Project expense transaction categories (PSA to Fin and Ops) -**Name of the task in the project:** Sync categories to Fin Ops</span></span>

## <a name="entity-set"></a><span data-ttu-id="fcc48-147">Ange entiteten</span><span class="sxs-lookup"><span data-stu-id="fcc48-147">Entity set</span></span>

| <span data-ttu-id="fcc48-148">Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="fcc48-148">Project Service Automation</span></span>      | <span data-ttu-id="fcc48-149">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="fcc48-149">Finance and Operations</span></span>             |
|---------------------------------|------------------------------------|
| <span data-ttu-id="fcc48-150">Transaktionskategorier</span><span class="sxs-lookup"><span data-stu-id="fcc48-150">Transaction categories</span></span>          | <span data-ttu-id="fcc48-151">Integrationsenhet för kategorier</span><span class="sxs-lookup"><span data-stu-id="fcc48-151">Integration entity for categories</span></span>  | 

## <a name="entity-flow"></a><span data-ttu-id="fcc48-152">Flöde för entitet</span><span class="sxs-lookup"><span data-stu-id="fcc48-152">Entity flow</span></span>

<span data-ttu-id="fcc48-153">Projektets utgiftskategorier hanteras i Finance and Operations och de synkroniseras till Project Service Automation som transaktionskategorier.</span><span class="sxs-lookup"><span data-stu-id="fcc48-153">Project expense categories are managed in Finance and Operations, and they are synchronized to Project Service Automation as transaction categories.</span></span> <span data-ttu-id="fcc48-154">Synkroniseringen tillbaka till Finance and Operations uppdaterar integrations-ID från Project Service Automation i projektkategorin för Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="fcc48-154">The synchronization back to Finance and Operations updates the integration ID from Project Service Automation on the Finance and Operations project category.</span></span>

<span data-ttu-id="fcc48-155">I följande illustration visas ett exempel på uppgiftsmallmappning i dataintegrering.</span><span class="sxs-lookup"><span data-stu-id="fcc48-155">The following illustration shows an example of the template task mapping in Data integration.</span></span>

> [!NOTE]
> <span data-ttu-id="fcc48-156">Mappningen visar vilken fältinformation som kommer att synkroniseras från Project Service Automation till Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="fcc48-156">The mapping shows the field information that will be synchronized from Project Service Automation to Finance and Operations.</span></span>

<span data-ttu-id="fcc48-157">[![Mallmappning](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)</span><span class="sxs-lookup"><span data-stu-id="fcc48-157">[![Template mapping](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)</span></span>

