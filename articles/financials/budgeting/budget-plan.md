---
title: Budgetplanering
description: "Målet med den här övningen är att ge en guidad översikt över funktionsuppdateringarna inom området Budgetplanering i Microsoft Dynamics 365 for Finance and Operations. Syftet med övningen är att illustrera ett kort konfigureringsexempel av budgetplaneringsmodulen och visa hur budgetplaneringen kan utföras med hjälp av den här konfigurationen."
author: ShylaThompson
manager: AnnBe
ms.date: 06/25/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BudgetPlanningConfiguration
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 10763
ms.assetid: 0f2ba752-1f6d-4f28-b9e9-b2e97d10b6d1
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: b8f2f3a33dc19c2ebc941d1a504eae0c276f3cdf
ms.openlocfilehash: ac2e98dbbd45becf06e28b6ea4eb9d0ec15e30f6
ms.contentlocale: sv-se
ms.lasthandoff: 06/25/2018

---

# <a name="budget-planning"></a><span data-ttu-id="dc61f-104">Budgetplanering</span><span class="sxs-lookup"><span data-stu-id="dc61f-104">Budget planning</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="dc61f-105">Målet med den här övningen är att ge en guidad översikt över funktionsuppdateringarna inom området Budgetplanering i Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="dc61f-105">The objective of this lab is to provide a guided view of Microsoft Dynamics 365 for Finance and Operations functionality updates in Budget planning area.</span></span> <span data-ttu-id="dc61f-106">Syftet med övningen är att illustrera ett kort konfigureringsexempel av budgetplaneringsmodulen och visa hur budgetplaneringen kan utföras med hjälp av den här konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="dc61f-106">The intent of this lab is to illustrate a quick configuration example of budget planning module and showcase how budget planning can be accomplished using this configuration.</span></span>  <span data-ttu-id="dc61f-107">I det här övningen fokuseras på följande processer och uppgifter:</span><span class="sxs-lookup"><span data-stu-id="dc61f-107">This lab will focus specifically on the following business processes or tasks:</span></span>
- <span data-ttu-id="dc61f-108">Skapa organisationshierarki för budgetplanering och säkerhetsinställningar för användare</span><span class="sxs-lookup"><span data-stu-id="dc61f-108">Creating organizational hierarchy for budget planning and configuring user security</span></span>
- <span data-ttu-id="dc61f-109">Definiera budgetplanscenarier, budgetplankolumner, layouter och Excel-mallar</span><span class="sxs-lookup"><span data-stu-id="dc61f-109">Defining budget plan scenarios, budget plan columns, layouts and Excel templates</span></span>
- <span data-ttu-id="dc61f-110">Skapa och aktivera en budgetplaneringsprocess</span><span class="sxs-lookup"><span data-stu-id="dc61f-110">Creating and activating budget planning process</span></span>
- <span data-ttu-id="dc61f-111">Skapa budgetplandokument genom att dra i verkliga värden från redovisningen</span><span class="sxs-lookup"><span data-stu-id="dc61f-111">Creating budget plan document by pulling in actuals from General ledger</span></span>
- <span data-ttu-id="dc61f-112">Använda allokeringar för att justera dokumentdata för budgetplanen</span><span class="sxs-lookup"><span data-stu-id="dc61f-112">Using allocations to adjust budget plan document data</span></span>
- <span data-ttu-id="dc61f-113">Redigera dokumentdata för budgetplan i Excel</span><span class="sxs-lookup"><span data-stu-id="dc61f-113">Editing budget plan document data in Excel</span></span> 

<a name="prerequisites"></a><span data-ttu-id="dc61f-114">Krav</span><span class="sxs-lookup"><span data-stu-id="dc61f-114">Prerequisites</span></span> 
------------------

<span data-ttu-id="dc61f-115">I den här självstudien måste du ha tillgång till Finance and Operations-miljön med Contoso-demonstrationsdata och vara administratör för instansen.</span><span class="sxs-lookup"><span data-stu-id="dc61f-115">For this tutorial, you’ll need to access the Finance and Operations environment with Contoso demo data, and be provisioned as an administrator on the instance.</span></span> <span data-ttu-id="dc61f-116">Använd inte i webbläsaren i privat läge under övningen – logga ut från alla andra konton i webbläsaren och logga sedan in med administratörsautentiseringsuppgifter för Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="dc61f-116">Do not use In Private browser mode for this lab - sign out from any other account in the browser if needed and sign in with Finance and Operations administrator credentials.</span></span> <span data-ttu-id="dc61f-117">När du loggar in i Finance and Operations **MÅSTE** du markera kryssrutan Håll mig inloggad.</span><span class="sxs-lookup"><span data-stu-id="dc61f-117">When signing into Finance and Operations, you **MUST** check the “Keep me signed in” checkbox.</span></span> <span data-ttu-id="dc61f-118">Då skapas en beständig cookie som Excel-appen behöver.</span><span class="sxs-lookup"><span data-stu-id="dc61f-118">This creates a persistent cookie that the Excel App currently needs.</span></span> <span data-ttu-id="dc61f-119">Om du loggar in i Finance and Operations med en annan webbläsare än IE, uppmanas du att logga in via Excel-appen.</span><span class="sxs-lookup"><span data-stu-id="dc61f-119">If you sign in to the Finance and Operations using a browser other than IE, then you’ll be prompted to sign in within the Excel App.</span></span> <span data-ttu-id="dc61f-120">När du klickar på Logga in i Excel-appen visas ett IE-popup-fönster och när du loggar in **MÅSTE** du markera kryssrutan Håll mig inloggad.</span><span class="sxs-lookup"><span data-stu-id="dc61f-120">When you click “Sign in” in the Excel App, an IE popup window will open and when signing in you **MUST** check the “Keep me signed in” checkbox.</span></span> <span data-ttu-id="dc61f-121">Om det inte händer något när du klickar på logga in i Excel-appen rensar du cookiecachen i IE.</span><span class="sxs-lookup"><span data-stu-id="dc61f-121">If clicking “Sign in” in the Excel App doesn’t appear to do anything then you should clear the IE cookie cache.</span></span>

## <a name="scenario-overview"></a><span data-ttu-id="dc61f-122">**Scenarioöversikt**</span><span class="sxs-lookup"><span data-stu-id="dc61f-122">**Scenario overview**</span></span>
<span data-ttu-id="dc61f-123">Julia arbetar som ekonomichef i Contoso Entertainment Systems i Tyskland (DEMF).</span><span class="sxs-lookup"><span data-stu-id="dc61f-123">Julia works as a finance manager in Contoso Entertainment Systems in Germany (DEMF).</span></span> <span data-ttu-id="dc61f-124">Eftersom FY2016 närmar sig, måste hon arbeta med företagets budget för det kommande året.</span><span class="sxs-lookup"><span data-stu-id="dc61f-124">As FY2016 approaches, she needs to work on setting up the company’s budget for the upcoming year.</span></span> <span data-ttu-id="dc61f-125">Budgetförberedelserna ser ut så här:</span><span class="sxs-lookup"><span data-stu-id="dc61f-125">Budget preparation looks as follows:</span></span>

1.  <span data-ttu-id="dc61f-126">Julia använder föregående års faktiska belopp som utgångspunkt för att skapa budgeten.</span><span class="sxs-lookup"><span data-stu-id="dc61f-126">Julia uses previous year actuals amounts as a starting point to create the budget.</span></span>
2.  <span data-ttu-id="dc61f-127">Baserat på tidigare år skapar hon uppskattningar för tolv månader i det kommande året.</span><span class="sxs-lookup"><span data-stu-id="dc61f-127">Based on the previous year actuals, she creates estimates for 12 months in the upcoming year</span></span>
3.  <span data-ttu-id="dc61f-128">Julia går igenom budgeten med finansdirektören.</span><span class="sxs-lookup"><span data-stu-id="dc61f-128">Julia reviews the budget with CFO.</span></span> <span data-ttu-id="dc61f-129">När hon är klar gör hon de nödvändiga justeringarna för budgetplanen och slutför budgetförberedelserna.</span><span class="sxs-lookup"><span data-stu-id="dc61f-129">Once done she makes necessary adjustments for the budget plan and finalizes budget preparation.</span></span>

<span data-ttu-id="dc61f-130">Konfigurationsschemat budgetplaneringen för scenariot ser ut på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="dc61f-130">Budget planning configuration schema for the scenario looks as follows:</span></span>

![Konfigurationsschema för budgetplanering](./media/screenshot1-300x152.png)

<span data-ttu-id="dc61f-132">Julia använder följande Excel-mall för att förbereda budgeten:</span><span class="sxs-lookup"><span data-stu-id="dc61f-132">Julia uses the following Excel template to prepare the budget:</span></span>

<span data-ttu-id="dc61f-133">[![Excel-mall](./media/screenshot2-1024x352.png)](./media/screenshot2.png)</span><span class="sxs-lookup"><span data-stu-id="dc61f-133">[![Excel template](./media/screenshot2-1024x352.png)](./media/screenshot2.png)</span></span>

## <a name="exercise-1-configuration"></a><span data-ttu-id="dc61f-134">Övning 1: Konfiguration</span><span class="sxs-lookup"><span data-stu-id="dc61f-134">Exercise 1: Configuration</span></span>

### <a name="task-1-create-organizational-hierarchy"></a><span data-ttu-id="dc61f-135">**Uppgift 1: Skapa en organisationshierarki**</span><span class="sxs-lookup"><span data-stu-id="dc61f-135">**Task 1: Create organizational hierarchy**</span></span>
<span data-ttu-id="dc61f-136">Eftersom all budgetbearbetning bara görs på finansavdelningen, skapar Julia en mycket enkel hierarki som bara består av finansavdelningen.</span><span class="sxs-lookup"><span data-stu-id="dc61f-136">As all the budgeting process happens in the Finance department, therefore Julia needs to create a very simple organizational hierarchy – consisting of Finance department only.</span></span> <span data-ttu-id="dc61f-137">1.1.</span><span class="sxs-lookup"><span data-stu-id="dc61f-137">1.1.</span></span> <span data-ttu-id="dc61f-138">Navigera till organisationshierarkier (Organisationsadministration &gt; Organisationer &gt; Organisationshierarkier) och klickar på knappen Nytt</span><span class="sxs-lookup"><span data-stu-id="dc61f-138">Navigate to Organization hierarchies (Organization administration &gt; Organizations &gt; Organization hierarchies) and click New button</span></span>

![Organisationshierarki](./media/screenshot3.png) 

<span data-ttu-id="dc61f-140">1.2.</span><span class="sxs-lookup"><span data-stu-id="dc61f-140">1.2.</span></span> <span data-ttu-id="dc61f-141">Ange namnet på organisationshierarkin och klicka på knappen Tilldela syfte</span><span class="sxs-lookup"><span data-stu-id="dc61f-141">Type the name for the organizational hierarchy and click button Assign purpose</span></span>

<span data-ttu-id="dc61f-142">[![Namn](./media/screenshot4.png)](./media/screenshot4.png)</span><span class="sxs-lookup"><span data-stu-id="dc61f-142">[![Name](./media/screenshot4.png)](./media/screenshot4.png)</span></span> 

<span data-ttu-id="dc61f-143">1.3.</span><span class="sxs-lookup"><span data-stu-id="dc61f-143">1.3.</span></span> <span data-ttu-id="dc61f-144">Välj Budgetplaneringssyfte, klicka på knappen Lägg till och tilldela den nyligen skapade organisationshierarkin:</span><span class="sxs-lookup"><span data-stu-id="dc61f-144">Select Budget planning purpose, click button Add and assign newly created organizational hierarchy:</span></span> 

<span data-ttu-id="dc61f-145">[![Tilldela syfte](./media/screenshot5.png)](./media/screenshot5.png)</span><span class="sxs-lookup"><span data-stu-id="dc61f-145">[![Assign purpose](./media/screenshot5.png)](./media/screenshot5.png)</span></span>

<span data-ttu-id="dc61f-146">1.4.</span><span class="sxs-lookup"><span data-stu-id="dc61f-146">1.4.</span></span> <span data-ttu-id="dc61f-147">Upprepa steget ovan för säkerhetssyftet.</span><span class="sxs-lookup"><span data-stu-id="dc61f-147">Repeat the step above for Security organizational purpose.</span></span> <span data-ttu-id="dc61f-148">Stäng formuläret när du är klar.</span><span class="sxs-lookup"><span data-stu-id="dc61f-148">Close the form when done.</span></span>

<span data-ttu-id="dc61f-149">[![Säkerhetsorg](./media/screenshot6.png)](./media/screenshot6.png)</span><span class="sxs-lookup"><span data-stu-id="dc61f-149">[![Security org](./media/screenshot6.png)](./media/screenshot6.png)</span></span>

<span data-ttu-id="dc61f-150">1.5.</span><span class="sxs-lookup"><span data-stu-id="dc61f-150">1.5.</span></span> <span data-ttu-id="dc61f-151">I formuläret Organisationshierarkier klickar du på knappen Visa.</span><span class="sxs-lookup"><span data-stu-id="dc61f-151">In the Organizational Hierarchies form click button View.</span></span> <span data-ttu-id="dc61f-152">Klicka på Redigera i hierarkidesignern och skapa en hierarki genom att klicka på knappen Infoga.</span><span class="sxs-lookup"><span data-stu-id="dc61f-152">Click Edit in the Hierarchy designer and create a hierarchy by clicking button Insert.</span></span>

<span data-ttu-id="dc61f-153">[![Infoga](./media/screenshot7.png)](./media/screenshot7.png)</span><span class="sxs-lookup"><span data-stu-id="dc61f-153">[![Insert](./media/screenshot7.png)](./media/screenshot7.png)</span></span> 

<span data-ttu-id="dc61f-154">1.6.</span><span class="sxs-lookup"><span data-stu-id="dc61f-154">1.6.</span></span> <span data-ttu-id="dc61f-155">Välj finansavdelningen för budgethierarkin.</span><span class="sxs-lookup"><span data-stu-id="dc61f-155">Select Finance department for the budgeting hierarchy.</span></span> 

<span data-ttu-id="dc61f-156">[![Finansiellt](./media/screenshot8.png)](./media/screenshot8.png)</span><span class="sxs-lookup"><span data-stu-id="dc61f-156">[![Finance](./media/screenshot8.png)](./media/screenshot8.png)</span></span>

<span data-ttu-id="dc61f-157">1.7.</span><span class="sxs-lookup"><span data-stu-id="dc61f-157">1.7.</span></span> <span data-ttu-id="dc61f-158">När du är klar klickar du på knappen Publicera och stäng.</span><span class="sxs-lookup"><span data-stu-id="dc61f-158">When done, click button Publish and Close.</span></span> <span data-ttu-id="dc61f-159">Välj 1/1/2015 som giltighetsdatum för hierarkipublicering.</span><span class="sxs-lookup"><span data-stu-id="dc61f-159">Select 1/1/2015 as effective date for hierarchy publishing.</span></span>

<span data-ttu-id="dc61f-160">[![Giltighetsdatum](./media/screenshot9.png)](./media/screenshot9.png)</span><span class="sxs-lookup"><span data-stu-id="dc61f-160">[![Effective date](./media/screenshot9.png)](./media/screenshot9.png)</span></span>

### <a name="task-2-configure-user-security"></a><span data-ttu-id="dc61f-161">Uppgift 2: Konfigurera användarsäkerhet</span><span class="sxs-lookup"><span data-stu-id="dc61f-161">Task 2: Configure user security</span></span>
<span data-ttu-id="dc61f-162">Budgetplaneringen använder särskilda säkerhetsprinciper för att kunna konfigurera åtkomst till budgetplandata.</span><span class="sxs-lookup"><span data-stu-id="dc61f-162">Budget planning uses special security policies to configure access to budget plans data.</span></span> <span data-ttu-id="dc61f-163">Julia måste ge åtkomst till finansbudgetplaner till sig själv.</span><span class="sxs-lookup"><span data-stu-id="dc61f-163">Julia needs to give access to Finance budget plans for herself.</span></span> 

<span data-ttu-id="dc61f-164">2.1.</span><span class="sxs-lookup"><span data-stu-id="dc61f-164">2.1.</span></span> <span data-ttu-id="dc61f-165">Växla till kontexten för juridisk person DEMF.</span><span class="sxs-lookup"><span data-stu-id="dc61f-165">Switch to DEMF legal entity context.</span></span> 


<span data-ttu-id="dc61f-166">2.2.</span><span class="sxs-lookup"><span data-stu-id="dc61f-166">2.2.</span></span> <span data-ttu-id="dc61f-167">Navigera till Budgetering &gt; Inställningar &gt; Budgetplanering &gt; Budgetplaneringskonfiguration.</span><span class="sxs-lookup"><span data-stu-id="dc61f-167">Navigate to Budgeting &gt; Setup &gt; Budget planning &gt; Budget planning configuration.</span></span> <span data-ttu-id="dc61f-168">Navigera till fliken Parametrar och ställ in säkerhetsmodellen på Baserat på säkerhetsorganisationer.</span><span class="sxs-lookup"><span data-stu-id="dc61f-168">In Parameters tab, set the Security model value to Based on security organizations</span></span> 

<span data-ttu-id="dc61f-169">[![Parametrar](./media/screenshot11.png)](./media/screenshot11.png)</span><span class="sxs-lookup"><span data-stu-id="dc61f-169">[![Parameters](./media/screenshot11.png)](./media/screenshot11.png)</span></span> 

<span data-ttu-id="dc61f-170">2.3.</span><span class="sxs-lookup"><span data-stu-id="dc61f-170">2.3.</span></span> <span data-ttu-id="dc61f-171">Navigera till Systemadministration &gt; Användare &gt; Användare.</span><span class="sxs-lookup"><span data-stu-id="dc61f-171">Navigate to System administration &gt; Users &gt; Users.</span></span> <span data-ttu-id="dc61f-172">Ange administratörsanvändaren (Julia Funderburk) rollen som Budgetchef.</span><span class="sxs-lookup"><span data-stu-id="dc61f-172">Give user Admin (Julia Funderburk) Budget manager role.</span></span> 

<span data-ttu-id="dc61f-173">[![Budgetchef](./media/screenshot12.png)](./media/screenshot12.png)</span><span class="sxs-lookup"><span data-stu-id="dc61f-173">[![Budget manager](./media/screenshot12.png)](./media/screenshot12.png)</span></span> 

<span data-ttu-id="dc61f-174">2.4.</span><span class="sxs-lookup"><span data-stu-id="dc61f-174">2.4.</span></span> <span data-ttu-id="dc61f-175">Välj användarroll och klicka på Tilldela organisationer</span><span class="sxs-lookup"><span data-stu-id="dc61f-175">Pick user role and click Assign organizations</span></span> 

<span data-ttu-id="dc61f-176">[![Tilldela org](./media/screenshot13.png)](./media/screenshot13.png)</span><span class="sxs-lookup"><span data-stu-id="dc61f-176">[![Assign org](./media/screenshot13.png)](./media/screenshot13.png)</span></span>

<span data-ttu-id="dc61f-177">2.5.</span><span class="sxs-lookup"><span data-stu-id="dc61f-177">2.5.</span></span> <span data-ttu-id="dc61f-178">Välj Ge tillgång till vissa organisationer.</span><span class="sxs-lookup"><span data-stu-id="dc61f-178">Select “Grant access to specific organizations”.</span></span> <span data-ttu-id="dc61f-179">Välj organisationshierarkin som skapades i det första steget.</span><span class="sxs-lookup"><span data-stu-id="dc61f-179">Pick Organizational hierarchy created in the first step.</span></span> <span data-ttu-id="dc61f-180">Välj finansnoden och klicka på knappen Bevilja med underordnad knapp</span><span class="sxs-lookup"><span data-stu-id="dc61f-180">Pick Finance node and click Grant with children button</span></span> 

<span data-ttu-id="dc61f-181">***Viktigt!***</span><span class="sxs-lookup"><span data-stu-id="dc61f-181">***Important!***</span></span> <span data-ttu-id="dc61f-182">*Se till att du är i kontexten för den juridiska personen DEMF när du genomför den här uppgiften, eftersom organisationssäkerhet tilldelas efter juridisk person*</span><span class="sxs-lookup"><span data-stu-id="dc61f-182">*Make sure you are in DEMF legal entity context when performing this task, as Organizational security is applied per legal entity*</span></span> 

### <a name="task-3-create-scenarios"></a><span data-ttu-id="dc61f-183">Uppgift 3: Skapa scenarier</span><span class="sxs-lookup"><span data-stu-id="dc61f-183">Task 3: Create scenarios</span></span>
<span data-ttu-id="dc61f-184">3.1.</span><span class="sxs-lookup"><span data-stu-id="dc61f-184">3.1.</span></span> <span data-ttu-id="dc61f-185">Navigera till Budgetering&gt;Inställningar &gt; Budgetplanering &gt; Budgetplaneringskonfiguration.</span><span class="sxs-lookup"><span data-stu-id="dc61f-185">Navigate to Budgeting&gt;Setup &gt; Budget planning &gt; Budget planning configuration.</span></span> <span data-ttu-id="dc61f-186">På scenariosidan kan du se scenarierna som vi ska använda i den här labbövningen: Utfall föregående år och Budgeterat.</span><span class="sxs-lookup"><span data-stu-id="dc61f-186">In the Scenarios page note the scenarios we are going to use further in this lab: Previous year actuals and Budgeted.</span></span> 

<span data-ttu-id="dc61f-187">*Obs! Du kan skapa nya scenarier för den här övningen och använda dem istället.*</span><span class="sxs-lookup"><span data-stu-id="dc61f-187">*Note: You can create new scenarios for this exercise if desired and use those instead.*</span></span> 

<span data-ttu-id="dc61f-188">[![Nya scenarier](./media/screenshot15.png)](./media/screenshot15.png)</span><span class="sxs-lookup"><span data-stu-id="dc61f-188">[![New scenarios](./media/screenshot15.png)](./media/screenshot15.png)</span></span> 

<span data-ttu-id="dc61f-189">*Obs! Eftersom Julia inte använder den formella godkännandeprocessen för budgetförberedelser hoppar vi över inställningsstegen för arbetsflöden, faser och arbetsflödesfaser i övningen. I stället använder vi den befintliga inställningen för automatiskt godkända arbetsflöden. Se appendix för denna arbetsflödeskonfiguration.*</span><span class="sxs-lookup"><span data-stu-id="dc61f-189">*Note: as Julia is not using formal approval process for budget preparation, we will skip Workflows, Stages and Workflow stages setup in this lab and will use existing setup for Auto – approve workflow. See appendix for this workflow configuration.*</span></span>

### <a name="task-4-create-budget-plan-columns"></a><span data-ttu-id="dc61f-190">Uppgift 4: Skapa budgetplankolumner</span><span class="sxs-lookup"><span data-stu-id="dc61f-190">Task 4: Create budget plan columns</span></span>
<span data-ttu-id="dc61f-191">Budgetplankolumner är antingen monetära eller kvantitetsbaserade och kan användas i budgetplandokumentlayouten.</span><span class="sxs-lookup"><span data-stu-id="dc61f-191">Budget plan columns are either Monetary or quantity based columns that can be used in budget plan document layout.</span></span> <span data-ttu-id="dc61f-192">I vårt exempel måste du skapa en kolumn för utfall föregående år och tolv kolumner som ska representera varje månad i ett budgeterat år.</span><span class="sxs-lookup"><span data-stu-id="dc61f-192">In our example we need to create a column for Previous year actuals and 12 columns to represent each month in a budgeted year.</span></span> <span data-ttu-id="dc61f-193">Kolumner kan skapas antingen genom att klicka på knappen Lägg till och sedan ange värden eller med hjälp av Datatabell.</span><span class="sxs-lookup"><span data-stu-id="dc61f-193">Columns can be created either by simply clicking Add button and filling in the values, or with a help of Data entity.</span></span> <span data-ttu-id="dc61f-194">I den här övningen ska vi använda datatabellen för att fylla i värdena.</span><span class="sxs-lookup"><span data-stu-id="dc61f-194">In this lab we will use Data entity to fill in the values.</span></span> 

<span data-ttu-id="dc61f-195">4.1.</span><span class="sxs-lookup"><span data-stu-id="dc61f-195">4.1.</span></span> <span data-ttu-id="dc61f-196">Öppna sidan Kolumner under Budgetering&gt;Inställningar &gt; Budgetplanering &gt; Budgetplaneringskonfiguration.</span><span class="sxs-lookup"><span data-stu-id="dc61f-196">In Budgeting&gt;Setup &gt; Budget planning &gt; Budget planning configuration open Columns page.</span></span> <span data-ttu-id="dc61f-197">Klicka på Office-knappen överst till höger i formuläret och välj Kolumner (ofiltrerade)</span><span class="sxs-lookup"><span data-stu-id="dc61f-197">Click Office button on the top right corner of the form and pick Columns (unfiltered)</span></span> 

<span data-ttu-id="dc61f-198">[![Ofiltrerade kolumner](./media/screenshot16.png)](./media/screenshot16.png)</span><span class="sxs-lookup"><span data-stu-id="dc61f-198">[![Columns unfiltered](./media/screenshot16.png)](./media/screenshot16.png)</span></span> 

<span data-ttu-id="dc61f-199">4.2.</span><span class="sxs-lookup"><span data-stu-id="dc61f-199">4.2.</span></span> <span data-ttu-id="dc61f-200">En Excel-arbetsbok öppnas som ska användas för att fylla i värdena.</span><span class="sxs-lookup"><span data-stu-id="dc61f-200">System will open Excel workbook to be used for filling in the values.</span></span> <span data-ttu-id="dc61f-201">Om du uppmanas aktiverar du redigering och förtroende för den här appen</span><span class="sxs-lookup"><span data-stu-id="dc61f-201">If prompted, click Enable Editing and Trust this app</span></span> 

<span data-ttu-id="dc61f-202">[![Aktivera redigering](./media/screenshot18.png)](./media/screenshot18.png)</span><span class="sxs-lookup"><span data-stu-id="dc61f-202">[![Enable editing](./media/screenshot18.png)](./media/screenshot18.png)</span></span> 

<span data-ttu-id="dc61f-203">[![Lita på den här appen](./media/screenshot17.png)](./media/screenshot17.png)</span><span class="sxs-lookup"><span data-stu-id="dc61f-203">[![Trust this app](./media/screenshot17.png)](./media/screenshot17.png)</span></span>

<span data-ttu-id="dc61f-204">4.3.</span><span class="sxs-lookup"><span data-stu-id="dc61f-204">4.3.</span></span> <span data-ttu-id="dc61f-205">Vi behöver fler kolumner att fylla i värdena i.</span><span class="sxs-lookup"><span data-stu-id="dc61f-205">We will need more columns to fill the values in.</span></span> <span data-ttu-id="dc61f-206">Klicka på Design i höger sidfönster om du vill lägga till kolumnerna i rutnätet:</span><span class="sxs-lookup"><span data-stu-id="dc61f-206">Click Design on the right side pane to add the columns to the grid:</span></span> 

<span data-ttu-id="dc61f-207">[![Design](./media/screenshot19.png)](./media/screenshot19.png)</span><span class="sxs-lookup"><span data-stu-id="dc61f-207">[![Design](./media/screenshot19.png)](./media/screenshot19.png)</span></span> 

<span data-ttu-id="dc61f-208">4.4.</span><span class="sxs-lookup"><span data-stu-id="dc61f-208">4.4.</span></span> <span data-ttu-id="dc61f-209">Klicka på den lilla pennknappen bredvid PlanColumns för att se kolumner som går att lägga till i rutnätet</span><span class="sxs-lookup"><span data-stu-id="dc61f-209">Click little pencil button next to PlanColumns to see available columns to add to the grid</span></span> 

<span data-ttu-id="dc61f-210">[![Redigera](./media/screenshot20.png)](./media/screenshot20.png)</span><span class="sxs-lookup"><span data-stu-id="dc61f-210">[![Edit](./media/screenshot20.png)](./media/screenshot20.png)</span></span> 

<span data-ttu-id="dc61f-211">4.5.</span><span class="sxs-lookup"><span data-stu-id="dc61f-211">4.5.</span></span> <span data-ttu-id="dc61f-212">Dubbelklicka på varje tillgängligt fält för att lägga till dem i rutan för valda fält och klicka på Uppdatera</span><span class="sxs-lookup"><span data-stu-id="dc61f-212">Double click on each available field to add them to Selected fields and click Update</span></span> 

![Uppdatera](./media/screenshot21.png)<span data-ttu-id="dc61f-214">](./Media/screenshot21.png)</span><span class="sxs-lookup"><span data-stu-id="dc61f-214">](./media/screenshot21.png)</span></span> 

<span data-ttu-id="dc61f-215">4.6.</span><span class="sxs-lookup"><span data-stu-id="dc61f-215">4.6.</span></span> <span data-ttu-id="dc61f-216">Lägg till alla kolumner som ska skapas i Excel-tabell.</span><span class="sxs-lookup"><span data-stu-id="dc61f-216">In Excel table add all the columns that need to be created.</span></span> <span data-ttu-id="dc61f-217">Använd autofyllfunktionen i Excel om du vill lägga till raderna snabbt.</span><span class="sxs-lookup"><span data-stu-id="dc61f-217">Use AutoFill feature in Excel to add the lines quickly.</span></span> <span data-ttu-id="dc61f-218">Kontrollera att raderna läggs till som en del av tabellen (när du rullar vertikalt kan du se kolumnrubrikerna överst i rutnätet)</span><span class="sxs-lookup"><span data-stu-id="dc61f-218">Make sure the lines are added as a part of the table (when using vertical scroll, you should be able to see column headers on the top of the grid)</span></span> 

<span data-ttu-id="dc61f-219">[![Autofyll](./media/screenshot22.png)](./media/screenshot22.png)</span><span class="sxs-lookup"><span data-stu-id="dc61f-219">[![Autofill](./media/screenshot22.png)](./media/screenshot22.png)</span></span> 

<span data-ttu-id="dc61f-220">4.7.</span><span class="sxs-lookup"><span data-stu-id="dc61f-220">4.7.</span></span> <span data-ttu-id="dc61f-221">Återgå till Finance and Operations och uppdatera sidan.</span><span class="sxs-lookup"><span data-stu-id="dc61f-221">Return to Finance and Operations and refresh the page.</span></span> <span data-ttu-id="dc61f-222">Publicerade värden visas i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="dc61f-222">Published values will appear in Finance and Operations.</span></span> 

<span data-ttu-id="dc61f-223">[![Förnya](./media/screenshot23.png)](./media/screenshot23.png)</span><span class="sxs-lookup"><span data-stu-id="dc61f-223">[![Refresh](./media/screenshot23.png)](./media/screenshot23.png)</span></span>

### <a name="task-5-create-budget-plan-document-layouts-and-templates"></a><span data-ttu-id="dc61f-224">Uppgift 5: Skapa mallar och dokumentlayouter för budgetplanen</span><span class="sxs-lookup"><span data-stu-id="dc61f-224">Task 5: Create budget plan document layouts and templates</span></span>
<span data-ttu-id="dc61f-225">Layout definierar hur rutnätet med budgetplanens dokumentrader ser ut när du öppnar budgetplansdokumentet.</span><span class="sxs-lookup"><span data-stu-id="dc61f-225">Layout defines how budget plan document lines grid is going to look like when user opens budget plan document.</span></span> <span data-ttu-id="dc61f-226">Det går också att ändra layouten för budgetplandokumentet för att se samma uppgifter ur olika vinklar.</span><span class="sxs-lookup"><span data-stu-id="dc61f-226">It is also possible to switch the layout for budget plan document to see the same data in different angles.</span></span> <span data-ttu-id="dc61f-227">Nu när Julia har definierat kolumnerna som ska användas i budgetplandokumentet, ska hon skapa en dokumentlayout för budgetplanen. Den ska se ut om Excel-tabellen hon använde när hon skapade budgetdata (se avsnittet Översikt över scenario i övningen)</span><span class="sxs-lookup"><span data-stu-id="dc61f-227">Now, as she’s got columns defined to be used with our budget plan document, Julia needs to create a budget plan document layout, that would look similar to the Excel table she uses to create budget data (see section Scenario overview in this lab)</span></span> 

<span data-ttu-id="dc61f-228">5.1.</span><span class="sxs-lookup"><span data-stu-id="dc61f-228">5.1.</span></span> <span data-ttu-id="dc61f-229">Öppna sidan Layouter i Budgetering&gt;Inställningar &gt; Budgetplanering &gt; Budgetplaneringskonfiguration.</span><span class="sxs-lookup"><span data-stu-id="dc61f-229">In Budgeting&gt;Setup &gt; Budget planning &gt; Budget planning configuration open Layouts page.</span></span> <span data-ttu-id="dc61f-230">Skapa en ny layout för den månatliga budgetpost:</span><span class="sxs-lookup"><span data-stu-id="dc61f-230">Create a new layout for Monthly budget entry:</span></span>

-   <span data-ttu-id="dc61f-231">Välj MA+BU-dimensionsuppsättningen om du vill inkludera huvudkonton och affärsenheter i layouten.</span><span class="sxs-lookup"><span data-stu-id="dc61f-231">Pick MA+BU dimension set to include Main accounts and Business units to the layout.</span></span>
-   <span data-ttu-id="dc61f-232">Ange alla budgetplankolumner som skapades i föregående steg i elementavsnittet.</span><span class="sxs-lookup"><span data-stu-id="dc61f-232">List all budget plan columns created in the previous step in the Elements section.</span></span> <span data-ttu-id="dc61f-233">Gör alla utom Utfall föregående år, redigerbara.</span><span class="sxs-lookup"><span data-stu-id="dc61f-233">Make all but Previous year actuals editable.</span></span>
-   <span data-ttu-id="dc61f-234">Klicka på beskrivningsknappen när du vill välja vilka ekonomiska dimensioner ska visa beskrivningar i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="dc61f-234">Click Descriptions button to select which financial dimensions should display Descriptions in the grid.</span></span>

<span data-ttu-id="dc61f-235">[![Beskrivningar](./media/screenshot24.png)](./media/screenshot24.png)</span><span class="sxs-lookup"><span data-stu-id="dc61f-235">[![Descriptions](./media/screenshot24.png)](./media/screenshot24.png)</span></span> 

<span data-ttu-id="dc61f-236">Baserat på layoutdefinitionen av budgetplanen kan vi skapa en Excel-mall som ska användas som en alternativ väg för att redigera budgetdata.</span><span class="sxs-lookup"><span data-stu-id="dc61f-236">Based on the budget plan layout definition we can create an Excel template to be used as an alternative way to edit Budget data.</span></span> <span data-ttu-id="dc61f-237">Eftersom Excel-mallen måste matcha budgetplanens layoutdefinition, kan du inte redigera layouten efter genereringen av Excel-mallen. Därför ska uppgiften göras när alla layoutkomponenter har definierats.</span><span class="sxs-lookup"><span data-stu-id="dc61f-237">As Excel template has to match budget plan layout definition, you won’t be able to edit budget plan layout after generating Excel template, therefore this task should be done after all layout components are defined.</span></span> 

<span data-ttu-id="dc61f-238">5.2.</span><span class="sxs-lookup"><span data-stu-id="dc61f-238">5.2.</span></span> <span data-ttu-id="dc61f-239">För layout skapad i steg 5.1.</span><span class="sxs-lookup"><span data-stu-id="dc61f-239">For the layout created in the 5.1.</span></span> <span data-ttu-id="dc61f-240">, klicka på knappen Mall &gt; Generera.</span><span class="sxs-lookup"><span data-stu-id="dc61f-240">step, click button Template &gt; Generate.</span></span> <span data-ttu-id="dc61f-241">Bekräfta varningsmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="dc61f-241">Confirm the warning message.</span></span> <span data-ttu-id="dc61f-242">Visa mallen genom att klicka på Mall &gt; Visa.</span><span class="sxs-lookup"><span data-stu-id="dc61f-242">To view the template, click Template &gt; View.</span></span> 

<span data-ttu-id="dc61f-243">*Obs: Se till att välja "Spara som" och välj den plats där mallen ska sparas, om du vill redigera. Om användaren väljer "Öppna" i dialogrutan utan att spara, behålls inte ändringar som gjorts i filen när filen stängs.* 
[![Mallvy](./media/screenshot25.png)](./media/screenshot25.png)</span><span class="sxs-lookup"><span data-stu-id="dc61f-243">*Note: Make sure to select “Save as” and select the place where template should be stored in order to edit it. If user selects “Open” in the dialog without saving, the changes done to the file will not be retained when the file is closed.* 
[![Template view](./media/screenshot25.png)](./media/screenshot25.png)</span></span> 

<span data-ttu-id="dc61f-244">5.3.</span><span class="sxs-lookup"><span data-stu-id="dc61f-244">5.3.</span></span> <span data-ttu-id="dc61f-245">&lt; Valfritt steg&gt; Ändra Excel-mallen för att göra den mer användarvänlig – lägg till formler för summor, rubrikfält, formatering osv. Spara ändringarna och skicka filen till budgetplanlayouten genom att klicka på Layout &gt; Överför [![Överför](./media/screenshot26.png)](./media/screenshot26.png)</span><span class="sxs-lookup"><span data-stu-id="dc61f-245">&lt; Optional step&gt; Modify Excel template to make it look more user friendly – add total formulas, header fields, formatting, etc. Save the changes and upload the file to budget plan layout by clicking Layout &gt; Upload [![Upload](./media/screenshot26.png)](./media/screenshot26.png)</span></span>

### <a name="task-6-create-a-budget-planning-process"></a><span data-ttu-id="dc61f-246">Uppgift 6: Skapa en budgetplaneringsprocess</span><span class="sxs-lookup"><span data-stu-id="dc61f-246">Task 6: Create a budget planning process</span></span>
<span data-ttu-id="dc61f-247">Julia behöver skapa och aktivera en ny budgetplaneringsprocess som kombinerar alla inställningar ovan för att börja registrera budgetplaner.</span><span class="sxs-lookup"><span data-stu-id="dc61f-247">Julia needs to create and activate a new budget planning process combining all the setup above to start entering budget plans.</span></span> <span data-ttu-id="dc61f-248">Budgetplaneringsprocessen definiera vilka budgeteringsorganisationer, arbetsflöden, layouter och mallar som ska användas för att skapa budgetplaner.</span><span class="sxs-lookup"><span data-stu-id="dc61f-248">Budget planning process defines what budgeting organizations, workflow, layouts and templates will be used for creating budget plans.</span></span> 

<span data-ttu-id="dc61f-249">6.1.</span><span class="sxs-lookup"><span data-stu-id="dc61f-249">6.1.</span></span> <span data-ttu-id="dc61f-250">Navigera till Budgetering &gt; Inställningar &gt; Budgetplanering &gt; Budgetplaneringsprocess och skapa en ny post.</span><span class="sxs-lookup"><span data-stu-id="dc61f-250">Navigate to Budgeting &gt; Setup &gt; Budget planning &gt; Budget planning process and create a new record.</span></span>

-   <span data-ttu-id="dc61f-251">Budgetplaneringsprocess – DEMF budgeterar FY2016</span><span class="sxs-lookup"><span data-stu-id="dc61f-251">Budget planning process – DEMF budgeting FY2016</span></span>
-   <span data-ttu-id="dc61f-252">Budgetcykel – FY2016</span><span class="sxs-lookup"><span data-stu-id="dc61f-252">Budget cycle – FY2016</span></span>
-   <span data-ttu-id="dc61f-253">Redovisning – DEMF</span><span class="sxs-lookup"><span data-stu-id="dc61f-253">Ledger – DEMF</span></span>
-   <span data-ttu-id="dc61f-254">Standardkontostruktur – tillverkningsresultat</span><span class="sxs-lookup"><span data-stu-id="dc61f-254">Default account structure – Manufacturing P&L</span></span>
-   <span data-ttu-id="dc61f-255">Organisationshierarki – välj hierarkin som skapades i början av övningen</span><span class="sxs-lookup"><span data-stu-id="dc61f-255">Organization hierarchy – pick the hierarchy created in the beginning of the lab</span></span>
-   <span data-ttu-id="dc61f-256">Budget planeringsarbetsflöde – tilldela auto – godkänn arbetsflöde för finansavdelningen</span><span class="sxs-lookup"><span data-stu-id="dc61f-256">Budget planning workflow – assign Auto – Approve workflow for Finance department</span></span>
-   <span data-ttu-id="dc61f-257">I regler och mallar för budgetplaneringsfaser ska det väljas om tilläggning av rader och ändring av rader tillåts och vilken layout som ska användas som standard för varje fas i arbetsflödesbudgeteringsplaneringen</span><span class="sxs-lookup"><span data-stu-id="dc61f-257">In budget planning stage rules and templates, for each workflow Budget planning stage pick if Adding lines and Modifying lines is allowed and what Layout should be used by default</span></span>

<span data-ttu-id="dc61f-258">*Obs! Du kan skapa ytterligare dokumentlayouter och göra dem tillgängliga i arbetsflödesfasen för budgetplanering genom att klicka på knappen för alternativa layouter.*</span><span class="sxs-lookup"><span data-stu-id="dc61f-258">*Note: You can create additional document layouts and assign them to be available in budget planning workflow stage by clicking Alternate layouts button.*</span></span> 

<span data-ttu-id="dc61f-259">[![Alternativa layouter](./media/screenshot27.png)](./media/screenshot27.png)</span><span class="sxs-lookup"><span data-stu-id="dc61f-259">[![Alternate layouts](./media/screenshot27.png)](./media/screenshot27.png)</span></span> 

<span data-ttu-id="dc61f-260">6.2.</span><span class="sxs-lookup"><span data-stu-id="dc61f-260">6.2.</span></span> <span data-ttu-id="dc61f-261">Välj Åtgärder &gt; Aktivera för att aktivera budgetplaneringsarbetsflödet </span><span class="sxs-lookup"><span data-stu-id="dc61f-261">Select Actions &gt; Activate to activate this budget planning workflow</span></span> 

<span data-ttu-id="dc61f-262">[![Aktivera](./media/screenshot28.png)](./media/screenshot28.png)</span><span class="sxs-lookup"><span data-stu-id="dc61f-262">[![Activate](./media/screenshot28.png)](./media/screenshot28.png)</span></span>

## <a name="exercise-2-process-simulation"></a><span data-ttu-id="dc61f-263">Övning 2: Processimulering</span><span class="sxs-lookup"><span data-stu-id="dc61f-263">Exercise 2: Process simulation</span></span>

### <a name="task-7-generate-initial-data-for-budget-plan-from-general-ledger"></a><span data-ttu-id="dc61f-264">Uppgift 7: Generera initiala data för budgetplan från redovisning</span><span class="sxs-lookup"><span data-stu-id="dc61f-264">Task 7: Generate initial data for budget plan from General ledger</span></span>
<span data-ttu-id="dc61f-265">7.1.</span><span class="sxs-lookup"><span data-stu-id="dc61f-265">7.1.</span></span> <span data-ttu-id="dc61f-266">Navigera till Budgetering &gt; Periodisk &gt; Generera budgetplan från huvudbok.</span><span class="sxs-lookup"><span data-stu-id="dc61f-266">Navigate to Budgeting &gt; Periodic &gt; Generate budget plan from General ledger.</span></span> <span data-ttu-id="dc61f-267">Fyll i de periodiska processparametrarna och klicka på Generera.</span><span class="sxs-lookup"><span data-stu-id="dc61f-267">Fill in the periodic process parameters and click button Generate.</span></span> 

<span data-ttu-id="dc61f-268">[![Generera](./media/screenshot29.png)](./media/screenshot29.png)</span><span class="sxs-lookup"><span data-stu-id="dc61f-268">[![Generate](./media/screenshot29.png)](./media/screenshot29.png)</span></span> 

<span data-ttu-id="dc61f-269">7.2.</span><span class="sxs-lookup"><span data-stu-id="dc61f-269">7.2.</span></span> <span data-ttu-id="dc61f-270">Navigera till Budgetering &gt; Budgetplaner för att hitta en budgetplan som har skapats av genereringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="dc61f-270">Navigate to Budgeting &gt; Budget plans to find a budget plan created by Generate process.</span></span> 

<span data-ttu-id="dc61f-271">[![Budgetplan](./media/screenshot30.png)](./media/screenshot30.png)</span><span class="sxs-lookup"><span data-stu-id="dc61f-271">[![Budget plan](./media/screenshot30.png)](./media/screenshot30.png)</span></span> 

<span data-ttu-id="dc61f-272">7.3.</span><span class="sxs-lookup"><span data-stu-id="dc61f-272">7.3.</span></span> <span data-ttu-id="dc61f-273">Öppna dokumentdetaljer genom att klicka på hyperlänken för dokumentnummer.</span><span class="sxs-lookup"><span data-stu-id="dc61f-273">Open document details by clicking on Document number hyperlink.</span></span> <span data-ttu-id="dc61f-274">Budgetplanen visas enligt definitionen i layouten som skapades i den här övningen</span><span class="sxs-lookup"><span data-stu-id="dc61f-274">Budget plan is displayed as defined in the layout created during this lab</span></span> 

<span data-ttu-id="dc61f-275">[![Budgetplandokument](./media/screenshot31.png)](./media/screenshot31.png)</span><span class="sxs-lookup"><span data-stu-id="dc61f-275">[![Budget plan display](./media/screenshot31.png)](./media/screenshot31.png)</span></span>

### <a name="task-8-create-current-year-budget-based-on-previous-year-actuals"></a><span data-ttu-id="dc61f-276">Uppgift 8: Skapa innevarande års budget baserad på utfall för tidigare år</span><span class="sxs-lookup"><span data-stu-id="dc61f-276">Task 8: Create current year budget based on previous year actuals</span></span>
<span data-ttu-id="dc61f-277">Allokeringsmetoder kan användas i budgetplaner för att enkelt kopiera information för budgetplaner från ett scenario till ett annat eller fördela dem över perioder eller allokera till dimensioner.</span><span class="sxs-lookup"><span data-stu-id="dc61f-277">Allocation methods can be used in budget plan to easily copy information for budget plans from one scenario to another/ spread them across periods/ allocate to dimensions.</span></span> <span data-ttu-id="dc61f-278">Vi använder allokeringar för att skapa innevarande års budget från tidigare års utfall.</span><span class="sxs-lookup"><span data-stu-id="dc61f-278">We will use allocations to create current year budget from previous year actuals.</span></span> 

<span data-ttu-id="dc61f-279">8.1.</span><span class="sxs-lookup"><span data-stu-id="dc61f-279">8.1.</span></span> <span data-ttu-id="dc61f-280">Välj alla rader i rutnätet i budgetplandokumentet och klicka på knappen för allokering av budget</span><span class="sxs-lookup"><span data-stu-id="dc61f-280">Pick all lines in the budget plan document grid and click button allocate budget</span></span> 

<span data-ttu-id="dc61f-281">[![Alla rader](./media/screenshot32.png)](./media/screenshot32.png)</span><span class="sxs-lookup"><span data-stu-id="dc61f-281">[![All lines](./media/screenshot32.png)](./media/screenshot32.png)</span></span> 

<span data-ttu-id="dc61f-282">8.2.</span><span class="sxs-lookup"><span data-stu-id="dc61f-282">8.2.</span></span> <span data-ttu-id="dc61f-283">Välj allokeringsmetod, Periodnyckel, käll- och målscenarier och klicka på Allokera</span><span class="sxs-lookup"><span data-stu-id="dc61f-283">Select allocation method, Period key, Source and destination scenarios and click Allocate</span></span> 

<span data-ttu-id="dc61f-284">[![Allokera](./media/screenshot33.png)](./media/screenshot33.png)</span><span class="sxs-lookup"><span data-stu-id="dc61f-284">[![Allocate](./media/screenshot33.png)](./media/screenshot33.png)</span></span>

<span data-ttu-id="dc61f-285">De faktiska beloppen för föregående kopieras till budgeten för aktuellt år och fördelas över perioder via försäljningskurvans periodnyckel.</span><span class="sxs-lookup"><span data-stu-id="dc61f-285">The previous year actual amounts will be copied to current year budget and allocate them across periods using Sales curve period key.</span></span> 

<span data-ttu-id="dc61f-286">[![Försäljningskurva](./media/screenshot34.png)](./media/screenshot34.png)</span><span class="sxs-lookup"><span data-stu-id="dc61f-286">[![Sales curve](./media/screenshot34.png)](./media/screenshot34.png)</span></span>

### <a name="task-9-adjust-budget-plan-document-using-excel-and-finalize-the-document"></a><span data-ttu-id="dc61f-287">Uppgift 9: Justera budgetplandokumentet med hjälp av Excel och slutför dokumentet</span><span class="sxs-lookup"><span data-stu-id="dc61f-287">Task 9: Adjust budget plan document using Excel and finalize the document</span></span>
<span data-ttu-id="dc61f-288">9.1.</span><span class="sxs-lookup"><span data-stu-id="dc61f-288">9.1.</span></span> <span data-ttu-id="dc61f-289">Klicka på knappen för kalkylbladet för att öppna dokumentinnehållet i Excel</span><span class="sxs-lookup"><span data-stu-id="dc61f-289">Click Button worksheet to open document contents in Excel</span></span>

<span data-ttu-id="dc61f-290">[![Excel](./media/screenshot35.png)](./media/screenshot35.png)</span><span class="sxs-lookup"><span data-stu-id="dc61f-290">[![Excel](./media/screenshot35.png)](./media/screenshot35.png)</span></span>

<span data-ttu-id="dc61f-291">9.2.</span><span class="sxs-lookup"><span data-stu-id="dc61f-291">9.2.</span></span> <span data-ttu-id="dc61f-292">När Excel öppnas justerar du siffrorna i budgetplandokumentet och klickar på knappen Publicera.</span><span class="sxs-lookup"><span data-stu-id="dc61f-292">When Excel workbook opens, adjust the numbers in budget plan document and click button Publish.</span></span>

<span data-ttu-id="dc61f-293">[![Publicera](./media/screenshot36.png)](./media/screenshot36.png)</span><span class="sxs-lookup"><span data-stu-id="dc61f-293">[![Publish](./media/screenshot36.png)](./media/screenshot36.png)</span></span>

<span data-ttu-id="dc61f-294">9.3.</span><span class="sxs-lookup"><span data-stu-id="dc61f-294">9.3.</span></span> <span data-ttu-id="dc61f-295">Återgå till budgetplandokument i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="dc61f-295">Return to budget plan document in Finance and Operations.</span></span> <span data-ttu-id="dc61f-296">Klicka på Arbetsflöde &gt; Skicka för att godkänna dokumentet automatiskt</span><span class="sxs-lookup"><span data-stu-id="dc61f-296">Click Workflow &gt; Submit to Auto-approve the document</span></span>

<span data-ttu-id="dc61f-297">[![Automatiskt godkänd](./media/screenshot37.png)](./media/screenshot37.png)</span><span class="sxs-lookup"><span data-stu-id="dc61f-297">[![Auto-approve](./media/screenshot37.png)](./media/screenshot37.png)</span></span> 

<span data-ttu-id="dc61f-298">När arbetsflödet har slutförts, ändras steget för budgetplandokument till Godkänt.</span><span class="sxs-lookup"><span data-stu-id="dc61f-298">Once workflow completes, budget plan document stage changes to Approved.</span></span> <span data-ttu-id="dc61f-299">[![Godkänd](./media/screenshot38.png)](./media/screenshot38.png)</span><span class="sxs-lookup"><span data-stu-id="dc61f-299">[![Approved](./media/screenshot38.png)](./media/screenshot38.png)</span></span>

## <a name="appendix"></a><span data-ttu-id="dc61f-300">Bilaga</span><span class="sxs-lookup"><span data-stu-id="dc61f-300">Appendix</span></span>

### <a name="auto-approve-workflow-configuration"></a><span data-ttu-id="dc61f-301">Konfiguration för automatiskt godkännande arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="dc61f-301">Auto-Approve workflow configuration</span></span>

<span data-ttu-id="dc61f-302">A.</span><span class="sxs-lookup"><span data-stu-id="dc61f-302">A.</span></span> <span data-ttu-id="dc61f-303">Budgetering &gt; Inställningar &gt; Budgetplanering &gt; Budgeteringsarbetsflöden Skapa ett nytt arbetsflöde med hjälp av mallen Budgetplaneringsarbetsflöden:</span><span class="sxs-lookup"><span data-stu-id="dc61f-303">Budgeting &gt; Setup &gt; Budget planning &gt; Budgeting workflows Create a new workflow using template Budget planning workflows:</span></span>

<span data-ttu-id="dc61f-304">[![Skapa ett nytt arbetsflöde](./media/screenshot39.png)](./media/screenshot39.png)</span><span class="sxs-lookup"><span data-stu-id="dc61f-304">[![Create a new workflow](./media/screenshot39.png)](./media/screenshot39.png)</span></span>

<span data-ttu-id="dc61f-305">Arbetsflödet innehåller endast en aktivitet – Fasövergångsbudgetplan</span><span class="sxs-lookup"><span data-stu-id="dc61f-305">This workflow will contain only one task – Stage transition budget plan</span></span> 

<span data-ttu-id="dc61f-306">[![Fasövergångsbudgetplan](./media/screenshot40.png)](./media/screenshot40.png)</span><span class="sxs-lookup"><span data-stu-id="dc61f-306">[![Stage transition budget plan](./media/screenshot40.png)](./media/screenshot40.png)</span></span> 

<span data-ttu-id="dc61f-307">Spara och aktivera arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="dc61f-307">Save and activate the workflow.</span></span> 

<span data-ttu-id="dc61f-308">B.</span><span class="sxs-lookup"><span data-stu-id="dc61f-308">B.</span></span> <span data-ttu-id="dc61f-309">Navigera till Budgetering &gt; Inställningar &gt; Budgetplanering &gt; Budgetplaneringskonfiguration.</span><span class="sxs-lookup"><span data-stu-id="dc61f-309">Navigate to Budgeting &gt; Setup &gt; Budget planning &gt; Budget planning configuration.</span></span> <span data-ttu-id="dc61f-310">Skapa 2 faser i fliken Faser – Inledande och Skickad</span><span class="sxs-lookup"><span data-stu-id="dc61f-310">In Stages tab create 2 stages – Initial and Submitted</span></span> 

<span data-ttu-id="dc61f-311">[![Ursprungliga och överförda](./media/screenshot41.png)](./media/screenshot41.png)</span><span class="sxs-lookup"><span data-stu-id="dc61f-311">[![Initial and submitted](./media/screenshot41.png)](./media/screenshot41.png)</span></span>

<span data-ttu-id="dc61f-312">C.</span><span class="sxs-lookup"><span data-stu-id="dc61f-312">C.</span></span> <span data-ttu-id="dc61f-313">Navigera till Budgetering &gt; Inställningar &gt; Budgetplanering &gt; Budgetplaneringskonfiguration.</span><span class="sxs-lookup"><span data-stu-id="dc61f-313">Navigate to Budgeting &gt; Setup &gt; Budget planning &gt; Budget planning configuration.</span></span> <span data-ttu-id="dc61f-314">I fliken Arbetsflödesfaser kopplar du arbetsflödet Automatiskt godkänd som skapades i steg A till faserna Inledande och Skickad</span><span class="sxs-lookup"><span data-stu-id="dc61f-314">In Workflow Stages tab Associate the workflow Auto – approve created in A step with the stages Initial and Submitted</span></span> 

<span data-ttu-id="dc61f-315">[![Budgetering och budgetplanering](./media/screenshot42.png)](./media/screenshot42.png)</span><span class="sxs-lookup"><span data-stu-id="dc61f-315">[![Budgeting and budget planning](./media/screenshot42.png)](./media/screenshot42.png)</span></span>  




