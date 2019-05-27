---
title: Synkronisera projektutgiftskategorier mellan Finance and Operations och Project Service Automation
description: Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera projektutgiftskategorier mellan Microsoft Dynamics 365 for Finance and Operations och Microsoft Dynamics 365 for Project Service Automation.
author: KimANelson
manager: AnnBe
ms.date: 07/20/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: c4d09fde2cf4335553243c136590f9f3135db97a
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1558252"
---
# <a name="synchronize-project-expense-categories-between-finance-and-operations-and-project-service-automation"></a><span data-ttu-id="274d1-103">Synkronisera projektutgiftskategorier mellan Finance and Operations och Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="274d1-103">Synchronize project expense categories between Finance and Operations and Project Service Automation</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="274d1-104">Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera projektutgiftskategorier mellan Microsoft Dynamics 365 for Finance and Operations och Microsoft Dynamics 365 for Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="274d1-104">This topic describes the templates and underlying tasks that are used to synchronize project expense categories between Microsoft Dynamics 365 for Finance and Operations and Microsoft Dynamics 365 for Project Service Automation.</span></span>

> [!NOTE]
> - <span data-ttu-id="274d1-105">Projektuppgiftsintegration, utgiftstransationskategorier, uppskattningar av timme, uppskattning av utgifter och funktionslåsning är tillgängliga i Microsoft Dynamics 365 for Finance and Operations version 8.0.</span><span class="sxs-lookup"><span data-stu-id="274d1-105">Project task integration, expense transaction categories, hour estimates, expense estimates, and functionality locking are available in Microsoft Dynamics 365 for Finance and Operations version 8.0.</span></span>
> - <span data-ttu-id="274d1-106">Integrering av faktiska uppgifter finns i Microsoft Dynamics 365 for Finance and Operations version 8.0.1 eller senare.</span><span class="sxs-lookup"><span data-stu-id="274d1-106">Actuals integration is available in Microsoft Dynamics 365 for Finance and Operations version 8.0.1 or later.</span></span>
> - <span data-ttu-id="274d1-107">Om du använder Microsoft Dynamics 365 for Finance and Operations Enterprise edition 7.3.0, när du har installerat KB 4132657 och KB 4132660, kommer du att kunna använda mallarna för att integrera projektuppgifter, utgiftstransaktionskategorier, timuppskattningar, utgiftsuppskattningar och verkliga värden, och så här konfigurerar du funktionslåsning.</span><span class="sxs-lookup"><span data-stu-id="274d1-107">If you're using Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3.0, after you install KB 4132657 and KB 4132660, you will be able to use the templates to integrate project tasks, expense transaction categories, hour estimates, expense estimates, and actuals, and to configure functionality locking.</span></span> <span data-ttu-id="274d1-108">Om du måste återställa redovisningsfördelningarna rekommenderar vi att du också installerar KB 4131710.</span><span class="sxs-lookup"><span data-stu-id="274d1-108">If you must reset the accounting distributions, we recommend that you also install KB 4131710.</span></span>

## <a name="data-flow-for-project-service-automation-and-finance-and-operations"></a><span data-ttu-id="274d1-109">Dataflöde för Project Service Automation och Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="274d1-109">Data flow for Project Service Automation and Finance and Operations</span></span>

<span data-ttu-id="274d1-110">Automatisering av integrationslösningen Project Service Automation och Finance and Operations använder funktionen dataintegration för att synkronisera data mellan instanser av Project Service Automation och Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="274d1-110">The Project Service Automation and Finance and Operations integration solution uses the Data integration feature to synchronize data across instances of Project Service Automation and Finance and Operations.</span></span> <span data-ttu-id="274d1-111">Integrationsmallarna som är tillgängliga med dataintegrationsfunktionen möjliggör flödet av data om transaktionskategorier för projektutgifter mellan Finance and Operations och Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="274d1-111">The integration templates that are available with the Data integration feature enable the flow of data about project expense transaction categories between Finance and Operations and Project Service Automation.</span></span>

<span data-ttu-id="274d1-112">Om projektets utgiftskategorier hanteras i Finance and Operations sker integrationsflödet först från Project Service Automation till Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="274d1-112">If the project expense categories are mastered in Finance and Operations, the integration flow is first from Finance and Operations to Project Service Automation.</span></span> <span data-ttu-id="274d1-113">Integrations-ID för kategorier för projektutgifter uppdateras sedan genom synkronisering från Project Service Automation till Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="274d1-113">The integration IDs of the project expense categories are then updated through synchronization from Project Service Automation to Finance and Operations.</span></span>

<span data-ttu-id="274d1-114">Om projektets utgiftskategorier hanteras i Project Service Automation, är integrationsflödet först från Project Service Automation till Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="274d1-114">If the project expense categories are mastered in Project Service Automation, the integration flow is first from Project Service Automation to Finance and Operations.</span></span> <span data-ttu-id="274d1-115">Projektkategorierna måste också vara konfigurerade i Finance and Operations före synkronisering från Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="274d1-115">The project categories must already be configured in Finance and Operations before the synchronization from Project Service Automation.</span></span> <span data-ttu-id="274d1-116">Synkronisera sedan från Finance and Operations och tillbaka till Project Service Automation, och sedan från Project Service Automation till Finance and Operations igen.</span><span class="sxs-lookup"><span data-stu-id="274d1-116">Then synchronize from Finance and Operations back to Project Service Automation, and then from Project Service Automation to Finance and Operations again.</span></span> <span data-ttu-id="274d1-117">På så sätt kan du garantera att kategorierna sammankopplas och att inga dubbletter skapas.</span><span class="sxs-lookup"><span data-stu-id="274d1-117">In this way, you help guarantee that the categories are linked, and that no duplicates are created.</span></span>

> [!NOTE]
> <span data-ttu-id="274d1-118">Vanligtvis hanteras projektets utgiftskategorier i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="274d1-118">Typically, the project expense categories are mastered in Finance and Operations.</span></span> <span data-ttu-id="274d1-119">Om de inte hanteras i Finance and Operations, eller om utgiftskategorier redan har skapats i Project Service Automation, måste du dock först synkronisera genom att använda mallen för transaktionskategorier för projektutgifter ("PSA till Fin och Ops").</span><span class="sxs-lookup"><span data-stu-id="274d1-119">However, if they aren't mastered in Finance and Operations, or if expense categories have already been created in Project Service Automation, you must first synchronize by using the Project expense transaction categories (PSA to Fin and Ops) template.</span></span> <span data-ttu-id="274d1-120">Synkronisera sedan genom att använda mallen för transaktionskategorier för projektutgifter ("Fin och Ops till PSA").</span><span class="sxs-lookup"><span data-stu-id="274d1-120">Then synchronize by using the Project expense transaction categories (Fin and Ops to PSA) template.</span></span> <span data-ttu-id="274d1-121">Du bör sedan köra synkroniseringen från Project Service Automation till Finance and Operations en gång till.</span><span class="sxs-lookup"><span data-stu-id="274d1-121">You should then run the synchronization from Project Service Automation to Finance and Operations one more time.</span></span>
>
> <span data-ttu-id="274d1-122">Om du synkroniserar från Project Service Automation först måste följande krav uppfyllas i Finance and Operations innan synkroniseringen körs:</span><span class="sxs-lookup"><span data-stu-id="274d1-122">If you synchronize first from Project Service Automation, the following requirements must be met in Finance and Operations before the synchronization is run:</span></span>
>
> - <span data-ttu-id="274d1-123">Den delade kategori som matchar den projektkategori som skapas i Project Service Automation måste existera, samt måste aktiveras för såväl **Projekt** och **Utgift**.</span><span class="sxs-lookup"><span data-stu-id="274d1-123">The shared category that matches the project category that is set up in Project Service Automation must exist, and it must be enabled for both **Project** and **Expense**.</span></span>
> - <span data-ttu-id="274d1-124">Följande projektkategorier måste finnas för respektive juridisk Finance and Operations-person med vilken integrering ska ske.</span><span class="sxs-lookup"><span data-stu-id="274d1-124">For each Finance and Operations legal entity that must be integrated with, the following project categories must exist:</span></span>
>
>     - <span data-ttu-id="274d1-125">**Projekt/kategori** finns.</span><span class="sxs-lookup"><span data-stu-id="274d1-125">**Project category** exists.</span></span> 
>     - <span data-ttu-id="274d1-126">**Använd i Utgift** har aktiverats.</span><span class="sxs-lookup"><span data-stu-id="274d1-126">**Use in Expense** is enabled.</span></span>
>     - <span data-ttu-id="274d1-127">**Aktiv i journalen** har aktiverats.</span><span class="sxs-lookup"><span data-stu-id="274d1-127">**Active in journal** is enabled.</span></span>
>     - <span data-ttu-id="274d1-128">**Transaktionstyp** anges som **Utgift**.</span><span class="sxs-lookup"><span data-stu-id="274d1-128">**Transaction type** is set to **Expense**.</span></span>

<span data-ttu-id="274d1-129">Följande bild visar hur data synkroniseras mellan Project Service Automation och Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="274d1-129">The following illustration shows how the data is synchronized between Project Service Automation and Finance and Operations.</span></span>

<span data-ttu-id="274d1-130">[![Dataflöde för integration av Project Service Automation med Finance and Operations](./media/ProjectExpenseCategoriesFlow.png)](./media/ProjectExpenseCategoriesFlow.png)</span><span class="sxs-lookup"><span data-stu-id="274d1-130">[![Data flow for Project Service Automation integration with Finance and Operations](./media/ProjectExpenseCategoriesFlow.png)](./media/ProjectExpenseCategoriesFlow.png)</span></span>

## <a name="project-expense-category-synchronization-from-finance-and-operations-to-project-service-automation"></a><span data-ttu-id="274d1-131">Synkronisering av projektutgiftskategori från Finance and Operations till Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="274d1-131">Project expense category synchronization from Finance and Operations to Project Service Automation</span></span>

### <a name="template-and-task"></a><span data-ttu-id="274d1-132">Mall och uppgift</span><span class="sxs-lookup"><span data-stu-id="274d1-132">Template and task</span></span>

<span data-ttu-id="274d1-133">För att få åtkomst till mallen väljer du i administratörscentret för Microsoft PowerApps **Projekt** och sedan i det övre högra hörnet **Ny projekt** för att välja offentliga mallar.</span><span class="sxs-lookup"><span data-stu-id="274d1-133">To access the template, in the Microsoft PowerApps admin center, select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="274d1-134">Följande mall och underliggande uppgift används för att synkronisera projektets utgiftskategorier från Finance and Operations till Project Service Automation:</span><span class="sxs-lookup"><span data-stu-id="274d1-134">The following template and underlying task are used to synchronize project expense categories from Finance and Operations to Project Service Automation:</span></span>

- <span data-ttu-id="274d1-135">**Namnet på mallen i dataintegrering:**  projektets utgiftstransaktionskategorier (Fin and Ops till PSA)</span><span class="sxs-lookup"><span data-stu-id="274d1-135">**Name of the template in Data integration:** Project expense transaction categories (Fin and Ops to PSA)</span></span>
- <span data-ttu-id="274d1-136">**Namnet på uppgiften i projektet:** synkronisera kategorier till PSA</span><span class="sxs-lookup"><span data-stu-id="274d1-136">**Name of the task in the project:** Sync categories to PSA</span></span>

### <a name="entity-set"></a><span data-ttu-id="274d1-137">Ange entiteten</span><span class="sxs-lookup"><span data-stu-id="274d1-137">Entity set</span></span>

| <span data-ttu-id="274d1-138">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="274d1-138">Finance and Operations</span></span>            | <span data-ttu-id="274d1-139">Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="274d1-139">Project Service Automation</span></span> |
|-----------------------------------|----------------------------|
| <span data-ttu-id="274d1-140">Integrationsenhet för kategorier</span><span class="sxs-lookup"><span data-stu-id="274d1-140">Integration entity for categories</span></span> | <span data-ttu-id="274d1-141">Transaktionskategorier</span><span class="sxs-lookup"><span data-stu-id="274d1-141">Transaction categories</span></span>     |

### <a name="entity-flow"></a><span data-ttu-id="274d1-142">Flöde för entitet</span><span class="sxs-lookup"><span data-stu-id="274d1-142">Entity flow</span></span>

<span data-ttu-id="274d1-143">Projektets utgiftskategorier hanteras i Finance and Operations och de synkroniseras till Project Service Automation som transaktionskategorier.</span><span class="sxs-lookup"><span data-stu-id="274d1-143">Project expense categories are managed in Finance and Operations, and they are synchronized to Project Service Automation as transaction categories.</span></span>

### <a name="power-query"></a><span data-ttu-id="274d1-144">Power Query</span><span class="sxs-lookup"><span data-stu-id="274d1-144">Power Query</span></span>

<span data-ttu-id="274d1-145">När du synkroniserar med Project Service Automation måste du använda Microsoft Power Query för Excel för att ange faktureringstyp för transaktionskategorin.</span><span class="sxs-lookup"><span data-stu-id="274d1-145">When you're synchronizing to Project Service Automation, you must use Microsoft Power Query for Excel to set the billing type on the transaction category.</span></span> <span data-ttu-id="274d1-146">Mallen för projektets utgiftstransaktionskategorier ("Fin och Ops till PSA") tillhandahåller en standardkolumn och mappning.</span><span class="sxs-lookup"><span data-stu-id="274d1-146">The Project expense transaction categories (Fin and Ops to PSA) template provides a default column and mapping.</span></span> <span data-ttu-id="274d1-147">Om du skapar en egen mall måste du lägga till en villkorlig kolumn i Power Query.</span><span class="sxs-lookup"><span data-stu-id="274d1-147">If you create your own template, you must add a conditional column in Power Query.</span></span> <span data-ttu-id="274d1-148">Följ dessa steg.</span><span class="sxs-lookup"><span data-stu-id="274d1-148">Follow these steps.</span></span>

1. <span data-ttu-id="274d1-149">Klicka på pilen för att öppna mappningen av projektets utgiftskategoriuppgift i mallen för projektets utgiftstransaktionskategorier ("Fin och Ops till PSA").</span><span class="sxs-lookup"><span data-stu-id="274d1-149">Click the arrow to open the mapping of the project expense categories task in the Project expense transaction categories (Fin and Ops to PSA) template.</span></span>
2. <span data-ttu-id="274d1-150">Klicka på länken **Avancerade frågor och filter** för att öppna Power Query.</span><span class="sxs-lookup"><span data-stu-id="274d1-150">Click the **Advance Query and Filtering** link to open Power Query.</span></span>
2. <span data-ttu-id="274d1-151">Välj **lägga till villkorlig kolumn**.</span><span class="sxs-lookup"><span data-stu-id="274d1-151">Select **Add Conditional Column**.</span></span>
3. <span data-ttu-id="274d1-152">Ange ett namn för den nya kolumnen, till exempel **Faktureringstyp**.</span><span class="sxs-lookup"><span data-stu-id="274d1-152">Enter a name for the new column, such as **BillingType**.</span></span>
4. <span data-ttu-id="274d1-153">Ange följande villkor: **om CATEGORYID ej noll så 19235001, annars noll**.</span><span class="sxs-lookup"><span data-stu-id="274d1-153">Enter the following condition: **if CATEGORYID not equal to null then 19235001, Otherwise null**.</span></span>
5. <span data-ttu-id="274d1-154">Klicka **OK** på kolumnen.</span><span class="sxs-lookup"><span data-stu-id="274d1-154">Click **OK** on the column.</span></span>
6. <span data-ttu-id="274d1-155">Se till att mappa denna nya kolumn på mappningssidan.</span><span class="sxs-lookup"><span data-stu-id="274d1-155">Be sure to map this new column on the mapping page.</span></span>

<span data-ttu-id="274d1-156">I följande illustration visas ett exempel på uppgiftsmallmappning i dataintegrering.</span><span class="sxs-lookup"><span data-stu-id="274d1-156">The following illustration shows an example of the template task mapping in Data integration.</span></span> <span data-ttu-id="274d1-157">Mappningen visar vilken fältinformation som kommer att synkroniseras från Finance and Operations till Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="274d1-157">The mapping shows the field information that will be synchronized from Finance and Operations to Project Service Automation.</span></span>

<span data-ttu-id="274d1-158">[![Mallmappning](./media/ProjectExpenseCategoriesToPSAMapping.jpg)](./media/ProjectExpenseCategoriesToPSAMapping.jpg)</span><span class="sxs-lookup"><span data-stu-id="274d1-158">[![Template mapping](./media/ProjectExpenseCategoriesToPSAMapping.jpg)](./media/ProjectExpenseCategoriesToPSAMapping.jpg)</span></span>

## <a name="project-expense-category-synchronization-from-project-service-automation-to-finance-and-operations"></a><span data-ttu-id="274d1-159">Synkronisering av projektutgiftskategori från Project Service Automation till Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="274d1-159">Project expense category synchronization from Project Service Automation to Finance and Operations</span></span>

### <a name="template-and-task"></a><span data-ttu-id="274d1-160">Mall och uppgift</span><span class="sxs-lookup"><span data-stu-id="274d1-160">Template and task</span></span>

<span data-ttu-id="274d1-161">Följande mall och underliggande uppgift används för att synkronisera projektets utgiftskategorier från Project Service Automation till Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="274d1-161">The following template and underlying task are used to synchronize project expense categories from Project Service Automation to Finance and Operations:</span></span>

- <span data-ttu-id="274d1-162">**Namn på mallen i dataintegreringen:** Projektets utgiftstransaktionskategorier ("PSA till Fin och Ops")</span><span class="sxs-lookup"><span data-stu-id="274d1-162">**Name of the template in Data integration:** Project expense transaction categories (PSA to Fin and Ops)</span></span>
- <span data-ttu-id="274d1-163">**Namnet på uppgiften i projektet:** Synkronisera kategorier till Fin Ops</span><span class="sxs-lookup"><span data-stu-id="274d1-163">**Name of the task in the project:** Sync categories to Fin Ops</span></span>

### <a name="entity-set"></a><span data-ttu-id="274d1-164">Ange entiteten</span><span class="sxs-lookup"><span data-stu-id="274d1-164">Entity set</span></span>

| <span data-ttu-id="274d1-165">Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="274d1-165">Project Service Automation</span></span> | <span data-ttu-id="274d1-166">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="274d1-166">Finance and Operations</span></span>            |
|----------------------------|-----------------------------------|
| <span data-ttu-id="274d1-167">Transaktionskategorier</span><span class="sxs-lookup"><span data-stu-id="274d1-167">Transaction categories</span></span>     | <span data-ttu-id="274d1-168">Integrationsenhet för kategorier</span><span class="sxs-lookup"><span data-stu-id="274d1-168">Integration entity for categories</span></span> |

### <a name="entity-flow"></a><span data-ttu-id="274d1-169">Flöde för entitet</span><span class="sxs-lookup"><span data-stu-id="274d1-169">Entity flow</span></span>

<span data-ttu-id="274d1-170">Projektets utgiftskategorier hanteras i Finance and Operations och de synkroniseras till Project Service Automation som transaktionskategorier.</span><span class="sxs-lookup"><span data-stu-id="274d1-170">Project expense categories are managed in Finance and Operations, and they are synchronized to Project Service Automation as transaction categories.</span></span> <span data-ttu-id="274d1-171">Synkroniseringen tillbaka till Finance and Operations uppdaterar projektkategorin i Finance and Operations med integrations-ID från Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="274d1-171">The synchronization back to Finance and Operations updates the project category in Finance and Operations with the integration ID from Project Service Automation.</span></span>

### <a name="template-mapping-in-data-integration"></a><span data-ttu-id="274d1-172">Mallmappning i dataintegrering</span><span class="sxs-lookup"><span data-stu-id="274d1-172">Template mapping in Data integration</span></span>

<span data-ttu-id="274d1-173">I följande illustration visas ett exempel på uppgiftsmallmappning i dataintegrering.</span><span class="sxs-lookup"><span data-stu-id="274d1-173">The following illustration shows an example of the template task mapping in Data integration.</span></span>

> [!NOTE]
> <span data-ttu-id="274d1-174">Mappningen visar vilken fältinformation som kommer att synkroniseras från Project Service Automation till Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="274d1-174">The mapping shows the field information that will be synchronized from Project Service Automation to Finance and Operations.</span></span>

<span data-ttu-id="274d1-175">[![Mallmappning](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)</span><span class="sxs-lookup"><span data-stu-id="274d1-175">[![Template mapping](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)</span></span>
