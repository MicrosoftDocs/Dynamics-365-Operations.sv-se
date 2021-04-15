---
title: Konfigurera och hantera databasloggning
description: Du kan spåra ändringar i register och fält i Dynamics 365 Human Resources med databasloggning.
author: andreabichsel
ms.date: 06/10/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-06-10
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d22ff9f3ce68c81f37840342c795d7d162eb027b
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801345"
---
# <a name="configure-and-manage-database-logging"></a><span data-ttu-id="48027-103">Konfigurera och hantera databasloggning</span><span class="sxs-lookup"><span data-stu-id="48027-103">Configure and manage database logging</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="48027-104">Du kan spåra ändringar i register och fält i Dynamics 365 Human Resources med databasloggning.</span><span class="sxs-lookup"><span data-stu-id="48027-104">You can track changes to tables and fields in Dynamics 365 Human Resources with database logging.</span></span> <span data-ttu-id="48027-105">I det här avsnittet beskrivs hur du:</span><span class="sxs-lookup"><span data-stu-id="48027-105">This topic describes how to:</span></span>

- <span data-ttu-id="48027-106">Hantera säkerhet och prestanda för databasloggning</span><span class="sxs-lookup"><span data-stu-id="48027-106">Manage security and performance for database logging</span></span>
- <span data-ttu-id="48027-107">Ställ in databasloggning</span><span class="sxs-lookup"><span data-stu-id="48027-107">Set up database logging</span></span>
- <span data-ttu-id="48027-108">Rensa databasloggar</span><span class="sxs-lookup"><span data-stu-id="48027-108">Clean up database logs</span></span>

## <a name="overview-of-database-logging"></a><span data-ttu-id="48027-109">Översikt över databasloggning</span><span class="sxs-lookup"><span data-stu-id="48027-109">Overview of database logging</span></span>

<span data-ttu-id="48027-110">Databasloggning spårar specifika ändringar av Microsoft Dynamics 365 Human Resources tabeller och fält.</span><span class="sxs-lookup"><span data-stu-id="48027-110">Database logging tracks specific changes to Microsoft Dynamics 365 Human Resources tables and fields.</span></span> <span data-ttu-id="48027-111">Ändringarna omfattar infogning, uppdatering och borttagning.</span><span class="sxs-lookup"><span data-stu-id="48027-111">These changes include inserting, updating, or deleting.</span></span> <span data-ttu-id="48027-112">Databasloggning lagrar en post med ändringar i register eller fält i databaslogg registret.</span><span class="sxs-lookup"><span data-stu-id="48027-112">Database logging stores a record of changes to tables or fields in the database log table.</span></span>

<span data-ttu-id="48027-113">Databasloggningen omfattar bland annat följande:</span><span class="sxs-lookup"><span data-stu-id="48027-113">The business uses of database logging include:</span></span>

- <span data-ttu-id="48027-114">Skapa en granskningspost av ändringar i specifika register som innehåller känslig information.</span><span class="sxs-lookup"><span data-stu-id="48027-114">Creating an audit record of changes to specific tables that contain sensitive information.</span></span>
- <span data-ttu-id="48027-115">Spåra enskilda transaktioner.</span><span class="sxs-lookup"><span data-stu-id="48027-115">Tracking single transactions.</span></span> <span data-ttu-id="48027-116">Databasloggning är inte avsett för spårning av automatiserade transaktioner som körs i batchjobb.</span><span class="sxs-lookup"><span data-stu-id="48027-116">Database logging isn't intended for tracking automated transactions that run in batch jobs.</span></span>

## <a name="security-for-database-logging"></a><span data-ttu-id="48027-117">Säkerhet vid databasloggning</span><span class="sxs-lookup"><span data-stu-id="48027-117">Security for database logging</span></span>

<span data-ttu-id="48027-118">Databasloggar kan innehålla känsliga data.</span><span class="sxs-lookup"><span data-stu-id="48027-118">Database logs can contain sensitive data.</span></span> <span data-ttu-id="48027-119">Begränsa åtkomsten till inkludera endast säkerhetsroller som behöver åtkomst till loggdata.</span><span class="sxs-lookup"><span data-stu-id="48027-119">Limit access to include only security roles that need access to the log data.</span></span>

## <a name="database-logging-and-performance"></a><span data-ttu-id="48027-120">Databasloggning och prestanda</span><span class="sxs-lookup"><span data-stu-id="48027-120">Database logging and performance</span></span>

<span data-ttu-id="48027-121">Samtidigt som det är värdefullt från ett affärsperspektiv kan databasloggning vara dyrt att använda och hantera resurser.</span><span class="sxs-lookup"><span data-stu-id="48027-121">While valuable from a business perspective, database logging can be expensive in resource use and management.</span></span> <span data-ttu-id="48027-122">Prestandakonsekvenser för databasloggningen omfattar bland annat följande:</span><span class="sxs-lookup"><span data-stu-id="48027-122">The performance implications of database logging include:</span></span>

- <span data-ttu-id="48027-123">Tabellen databaslogg kan växa snabbt och leda till att storleken på databasen ökar.</span><span class="sxs-lookup"><span data-stu-id="48027-123">The database log table can grow quickly and cause an increase in the size of the database.</span></span> <span data-ttu-id="48027-124">Tillväxten beror på mängden loggade data som du vill behålla.</span><span class="sxs-lookup"><span data-stu-id="48027-124">Growth depends on the amount of logged data that you decide to keep.</span></span> <span data-ttu-id="48027-125">Som standard innehåller tabellen databaslogg endast 30 dagars loggdata.</span><span class="sxs-lookup"><span data-stu-id="48027-125">By default, the database log table maintains only 30 days of log data.</span></span> 

- <span data-ttu-id="48027-126">Databasloggning kan påverka avancerade automatiserade processer, t.ex. tidskrävande dataimporter.</span><span class="sxs-lookup"><span data-stu-id="48027-126">Database logging can adversely affect long-running automated processes, such as long-running data imports.</span></span>

### <a name="best-practices"></a><span data-ttu-id="48027-127">Regelverk</span><span class="sxs-lookup"><span data-stu-id="48027-127">Best practices</span></span>

<span data-ttu-id="48027-128">För att förbättra prestanda begränsar du loggposter genom att välja specifika fält för att logga istället för hela tabeller..</span><span class="sxs-lookup"><span data-stu-id="48027-128">To improve performance, limit log entries by selecting specific fields to log instead of whole tables.</span></span> <span data-ttu-id="48027-129">Databasloggningen är begränsad till 20 tabeller för att upprätthålla den allmänna prestandan.</span><span class="sxs-lookup"><span data-stu-id="48027-129">To help maintain overall performance, database logging is limited to 20 tables.</span></span>

> [!NOTE]
> <span data-ttu-id="48027-130">Endast uppdateringar kan loggas för enskilda fält.</span><span class="sxs-lookup"><span data-stu-id="48027-130">Only updates can be logged for individual fields.</span></span>

## <a name="set-up-database-logging"></a><span data-ttu-id="48027-131">Ställ in databasloggning</span><span class="sxs-lookup"><span data-stu-id="48027-131">Set up database logging</span></span>

<span data-ttu-id="48027-132">Du kan använda guiden **Loggar databasändringar** när du vill konfigurera databasloggning.</span><span class="sxs-lookup"><span data-stu-id="48027-132">You can use the **Logging database changes** wizard to set up database logging.</span></span> <span data-ttu-id="48027-133">Med hjälp av guiden kan du på ett flexibelt sätt ställa in loggning för register eller fält.</span><span class="sxs-lookup"><span data-stu-id="48027-133">The wizard provides a flexible way to set up logging for tables or fields.</span></span>

1. <span data-ttu-id="48027-134">Gå till **Systemadministration > Länkar > Databasen > Inställningar för databaslogg**.</span><span class="sxs-lookup"><span data-stu-id="48027-134">Go to **System administration > Links > Database > Database log setup**.</span></span> <span data-ttu-id="48027-135">Välj **Ny** om du vill starta guiden **Loggar databasändringar**.</span><span class="sxs-lookup"><span data-stu-id="48027-135">Select **New** to start the **Logging database changes** wizard.</span></span>
2. <span data-ttu-id="48027-136">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="48027-136">Select **Next**.</span></span> 
3. <span data-ttu-id="48027-137">På sidan **Tabeller och fälten**, markera de tabeller och fält som du vill aktivera databasloggning på och välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="48027-137">On the **Tables and fields** page of the wizard, select the the tables and fields on which you want to enable database logging, and select **Next**.</span></span>

   > [!Note]
   > <span data-ttu-id="48027-138">Databasloggning är inte tillgänglig för alla register i Personal-databasen.</span><span class="sxs-lookup"><span data-stu-id="48027-138">Database logging is not available on all tables in the Human Resources database.</span></span> <span data-ttu-id="48027-139">Välj **Visa alla tabeller** nedanför listan utvidgas listan med tabeller och fält för att visa alla databastabeller för vilka databasloggning är tillgänglig, men detta kommer att vara en delmängd av den fullständiga listan över databastabeller.</span><span class="sxs-lookup"><span data-stu-id="48027-139">Selecting **Show all tables** below the list expands the list of tables and fields to show all database tables for which database logging is available, but this will be a subset of the full list of database tables.</span></span>

4. <span data-ttu-id="48027-140">På sidan **Typer av ändringar** på sidan för guiden, välj de datafunktioner som du vill spåra ändringar för varje tabell och fält och välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="48027-140">On the **Types of change** page of the wizard, select the data operations for which you want to track changes for each of the tables and fields, and select **Next**.</span></span> <span data-ttu-id="48027-141">I tabellen nedan finns en beskrivning av de dataoperationer som är tillgängliga för loggning.</span><span class="sxs-lookup"><span data-stu-id="48027-141">See the table below for a description of the data operations that are available for logging.</span></span>
5. <span data-ttu-id="48027-142">På sidan **Slutför**, granska ändringarna som kommer att göras och välj **Slutför**.</span><span class="sxs-lookup"><span data-stu-id="48027-142">On the **Finish** page, review the changes that will be made, and select **Finish**.</span></span>

| <span data-ttu-id="48027-143">Operation</span><span class="sxs-lookup"><span data-stu-id="48027-143">Operation</span></span> | <span data-ttu-id="48027-144">beskrivning</span><span class="sxs-lookup"><span data-stu-id="48027-144">Description</span></span> |
| -- | -- |
| <span data-ttu-id="48027-145">Spåra nya transaktioner</span><span class="sxs-lookup"><span data-stu-id="48027-145">Track new transactions</span></span> | <span data-ttu-id="48027-146">Skapa en logg för nya poster som skapas i registret.</span><span class="sxs-lookup"><span data-stu-id="48027-146">Create a log for new records that are created in the table.</span></span> |
| <span data-ttu-id="48027-147">Uppdatera</span><span class="sxs-lookup"><span data-stu-id="48027-147">Update</span></span> | <span data-ttu-id="48027-148">Skapa en logg för uppdateringar av registerposter eller uppdateringar av individuellt valda fält i registret.</span><span class="sxs-lookup"><span data-stu-id="48027-148">Create a log for updates to table records, or updates to individually selected fields in the table.</span></span> <span data-ttu-id="48027-149">Om du väljer att logga uppdateringar av registret skapas en loggpost varje gång en uppdatering görs i något av posterna i registret.</span><span class="sxs-lookup"><span data-stu-id="48027-149">If you select to log updates for the table, then a log record is created each time an update is made to any field of any record on the table.</span></span> <span data-ttu-id="48027-150">Om du väljer att logga uppdateringar för specifika fält, skapas en loggpost bara när uppdateringar görs av dessa fält i registerposterna.</span><span class="sxs-lookup"><span data-stu-id="48027-150">If you select to log updates for specific fields, then a log record is created only when updates are made to those fields of table records.</span></span> |
| <span data-ttu-id="48027-151">Delete</span><span class="sxs-lookup"><span data-stu-id="48027-151">Delete</span></span> | <span data-ttu-id="48027-152">Skapa en logg för poster som raderats från registret.</span><span class="sxs-lookup"><span data-stu-id="48027-152">Create a log for records deleted from the table.</span></span> |
| <span data-ttu-id="48027-153">Ändra namn på nyckel</span><span class="sxs-lookup"><span data-stu-id="48027-153">Rename key</span></span> | <span data-ttu-id="48027-154">Skapa en loggpost när du byter namn på en registernyckel.</span><span class="sxs-lookup"><span data-stu-id="48027-154">Create a log record when a table key is renamed.</span></span> |


## <a name="clean-up-database-logs"></a><span data-ttu-id="48027-155">Rensa databasloggar</span><span class="sxs-lookup"><span data-stu-id="48027-155">Clean up database logs</span></span>

<span data-ttu-id="48027-156">Du kan ta bort alla eller en del av databasloggarna med följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="48027-156">You can delete all or part of the database logs, using the following options:</span></span>

- <span data-ttu-id="48027-157">Välj alla loggar för en viss tabell.</span><span class="sxs-lookup"><span data-stu-id="48027-157">Select all logs for a particular table.</span></span>
- <span data-ttu-id="48027-158">Välj specifika typer av databaslogg.</span><span class="sxs-lookup"><span data-stu-id="48027-158">Select specific types of database log.</span></span>
- <span data-ttu-id="48027-159">Välj ett datum och en tidpunkt då en logg skapas.</span><span class="sxs-lookup"><span data-stu-id="48027-159">Select a date and time that a log was created.</span></span>

<span data-ttu-id="48027-160">Följ dessa steg för att ställa in rensning av databaslogg:</span><span class="sxs-lookup"><span data-stu-id="48027-160">To set up database log cleanup, follow these steps:</span></span> 

1. <span data-ttu-id="48027-161">Gå till **Systemadministration > Länkar > Databasen > Databaslogg**.</span><span class="sxs-lookup"><span data-stu-id="48027-161">Go to **System administration > Links > Database > Database log**.</span></span> <span data-ttu-id="48027-162">Välj **Rensa logg**.</span><span class="sxs-lookup"><span data-stu-id="48027-162">Select **Clean up log**.</span></span>

2. <span data-ttu-id="48027-163">Välj en metod för att välja loggar att ta bort genom att ange något av följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="48027-163">Choose a method of selecting logs to delete by entering one of the following options:</span></span>

   - <span data-ttu-id="48027-164">Register-ID</span><span class="sxs-lookup"><span data-stu-id="48027-164">Table ID</span></span>
   - <span data-ttu-id="48027-165">Typ av logg</span><span class="sxs-lookup"><span data-stu-id="48027-165">Type of log</span></span>
   - <span data-ttu-id="48027-166">Skapat datum och klockslag</span><span class="sxs-lookup"><span data-stu-id="48027-166">Created date and time</span></span>

3. <span data-ttu-id="48027-167">Använd fliken **Rensning i databasloggen** för att bestämma när loggrensningsuppgiften ska köras.</span><span class="sxs-lookup"><span data-stu-id="48027-167">Use the **Database log cleanup** tab to determine when to run the log cleanup task.</span></span> <span data-ttu-id="48027-168">Som standard är databasloggar tillgängliga i 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="48027-168">By default, database logs are available for 30 days.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
