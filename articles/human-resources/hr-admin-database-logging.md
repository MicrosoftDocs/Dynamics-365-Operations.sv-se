---
title: Konfigurera och hantera databasloggning
description: Du kan spåra ändringar i register och fält i Dynamics 365 Human Resources med databasloggning.
author: andreabichsel
manager: tfehr
ms.date: 06/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
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
ms.openlocfilehash: 8057ebd0bc061c6bf78d8674c45e0885ffce681c
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/17/2021
ms.locfileid: "5467659"
---
# <a name="configure-and-manage-database-logging"></a><span data-ttu-id="e0686-103">Konfigurera och hantera databasloggning</span><span class="sxs-lookup"><span data-stu-id="e0686-103">Configure and manage database logging</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="e0686-104">Du kan spåra ändringar i register och fält i Dynamics 365 Human Resources med databasloggning.</span><span class="sxs-lookup"><span data-stu-id="e0686-104">You can track changes to tables and fields in Dynamics 365 Human Resources with database logging.</span></span> <span data-ttu-id="e0686-105">I det här avsnittet beskrivs hur du:</span><span class="sxs-lookup"><span data-stu-id="e0686-105">This topic describes how to:</span></span>

- <span data-ttu-id="e0686-106">Hantera säkerhet och prestanda för databasloggning</span><span class="sxs-lookup"><span data-stu-id="e0686-106">Manage security and performance for database logging</span></span>
- <span data-ttu-id="e0686-107">Ställ in databasloggning</span><span class="sxs-lookup"><span data-stu-id="e0686-107">Set up database logging</span></span>
- <span data-ttu-id="e0686-108">Rensa databasloggar</span><span class="sxs-lookup"><span data-stu-id="e0686-108">Clean up database logs</span></span>

## <a name="overview-of-database-logging"></a><span data-ttu-id="e0686-109">Översikt över databasloggning</span><span class="sxs-lookup"><span data-stu-id="e0686-109">Overview of database logging</span></span>

<span data-ttu-id="e0686-110">Databasloggning spårar specifika ändringar av Microsoft Dynamics 365 Human Resources tabeller och fält.</span><span class="sxs-lookup"><span data-stu-id="e0686-110">Database logging tracks specific changes to Microsoft Dynamics 365 Human Resources tables and fields.</span></span> <span data-ttu-id="e0686-111">Ändringarna omfattar infogning, uppdatering och borttagning.</span><span class="sxs-lookup"><span data-stu-id="e0686-111">These changes include inserting, updating, or deleting.</span></span> <span data-ttu-id="e0686-112">Databasloggning lagrar en post med ändringar i register eller fält i databaslogg registret.</span><span class="sxs-lookup"><span data-stu-id="e0686-112">Database logging stores a record of changes to tables or fields in the database log table.</span></span>

<span data-ttu-id="e0686-113">Databasloggningen omfattar bland annat följande:</span><span class="sxs-lookup"><span data-stu-id="e0686-113">The business uses of database logging include:</span></span>

- <span data-ttu-id="e0686-114">Skapa en granskningspost av ändringar i specifika register som innehåller känslig information.</span><span class="sxs-lookup"><span data-stu-id="e0686-114">Creating an audit record of changes to specific tables that contain sensitive information.</span></span>
- <span data-ttu-id="e0686-115">Spåra enskilda transaktioner.</span><span class="sxs-lookup"><span data-stu-id="e0686-115">Tracking single transactions.</span></span> <span data-ttu-id="e0686-116">Databasloggning är inte avsett för spårning av automatiserade transaktioner som körs i batchjobb.</span><span class="sxs-lookup"><span data-stu-id="e0686-116">Database logging isn't intended for tracking automated transactions that run in batch jobs.</span></span>

## <a name="security-for-database-logging"></a><span data-ttu-id="e0686-117">Säkerhet vid databasloggning</span><span class="sxs-lookup"><span data-stu-id="e0686-117">Security for database logging</span></span>

<span data-ttu-id="e0686-118">Databasloggar kan innehålla känsliga data.</span><span class="sxs-lookup"><span data-stu-id="e0686-118">Database logs can contain sensitive data.</span></span> <span data-ttu-id="e0686-119">Begränsa åtkomsten till inkludera endast säkerhetsroller som behöver åtkomst till loggdata.</span><span class="sxs-lookup"><span data-stu-id="e0686-119">Limit access to include only security roles that need access to the log data.</span></span>

## <a name="database-logging-and-performance"></a><span data-ttu-id="e0686-120">Databasloggning och prestanda</span><span class="sxs-lookup"><span data-stu-id="e0686-120">Database logging and performance</span></span>

<span data-ttu-id="e0686-121">Samtidigt som det är värdefullt från ett affärsperspektiv kan databasloggning vara dyrt att använda och hantera resurser.</span><span class="sxs-lookup"><span data-stu-id="e0686-121">While valuable from a business perspective, database logging can be expensive in resource use and management.</span></span> <span data-ttu-id="e0686-122">Prestandakonsekvenser för databasloggningen omfattar bland annat följande:</span><span class="sxs-lookup"><span data-stu-id="e0686-122">The performance implications of database logging include:</span></span>

- <span data-ttu-id="e0686-123">Tabellen databaslogg kan växa snabbt och leda till att storleken på databasen ökar.</span><span class="sxs-lookup"><span data-stu-id="e0686-123">The database log table can grow quickly and cause an increase in the size of the database.</span></span> <span data-ttu-id="e0686-124">Tillväxten beror på mängden loggade data som du vill behålla.</span><span class="sxs-lookup"><span data-stu-id="e0686-124">Growth depends on the amount of logged data that you decide to keep.</span></span> <span data-ttu-id="e0686-125">Som standard innehåller tabellen databaslogg endast 30 dagars loggdata.</span><span class="sxs-lookup"><span data-stu-id="e0686-125">By default, the database log table maintains only 30 days of log data.</span></span> 

- <span data-ttu-id="e0686-126">Databasloggning kan påverka avancerade automatiserade processer, t.ex. tidskrävande dataimporter.</span><span class="sxs-lookup"><span data-stu-id="e0686-126">Database logging can adversely affect long-running automated processes, such as long-running data imports.</span></span>

### <a name="best-practices"></a><span data-ttu-id="e0686-127">Regelverk</span><span class="sxs-lookup"><span data-stu-id="e0686-127">Best practices</span></span>

<span data-ttu-id="e0686-128">För att förbättra prestanda begränsar du loggposter genom att välja specifika fält för att logga istället för hela tabeller..</span><span class="sxs-lookup"><span data-stu-id="e0686-128">To improve performance, limit log entries by selecting specific fields to log instead of whole tables.</span></span> <span data-ttu-id="e0686-129">Databasloggningen är begränsad till 20 tabeller för att upprätthålla den allmänna prestandan.</span><span class="sxs-lookup"><span data-stu-id="e0686-129">To help maintain overall performance, database logging is limited to 20 tables.</span></span>

> [!NOTE]
> <span data-ttu-id="e0686-130">Endast uppdateringar kan loggas för enskilda fält.</span><span class="sxs-lookup"><span data-stu-id="e0686-130">Only updates can be logged for individual fields.</span></span>

## <a name="set-up-database-logging"></a><span data-ttu-id="e0686-131">Ställ in databasloggning</span><span class="sxs-lookup"><span data-stu-id="e0686-131">Set up database logging</span></span>

<span data-ttu-id="e0686-132">Du kan använda guiden **Loggar databasändringar** när du vill konfigurera databasloggning.</span><span class="sxs-lookup"><span data-stu-id="e0686-132">You can use the **Logging database changes** wizard to set up database logging.</span></span> <span data-ttu-id="e0686-133">Med hjälp av guiden kan du på ett flexibelt sätt ställa in loggning för register eller fält.</span><span class="sxs-lookup"><span data-stu-id="e0686-133">The wizard provides a flexible way to set up logging for tables or fields.</span></span>

1. <span data-ttu-id="e0686-134">Gå till **Systemadministration > Länkar > Databasen > Inställningar för databaslogg**.</span><span class="sxs-lookup"><span data-stu-id="e0686-134">Go to **System administration > Links > Database > Database log setup**.</span></span> <span data-ttu-id="e0686-135">Välj **Ny** om du vill starta guiden **Loggar databasändringar**.</span><span class="sxs-lookup"><span data-stu-id="e0686-135">Select **New** to start the **Logging database changes** wizard.</span></span>
2. <span data-ttu-id="e0686-136">Slutför guiden.</span><span class="sxs-lookup"><span data-stu-id="e0686-136">Complete the wizard.</span></span>

## <a name="clean-up-database-logs"></a><span data-ttu-id="e0686-137">Rensa databasloggar</span><span class="sxs-lookup"><span data-stu-id="e0686-137">Clean up database logs</span></span>

<span data-ttu-id="e0686-138">Du kan ta bort alla eller en del av databasloggarna med följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="e0686-138">You can delete all or part of the database logs, using the following options:</span></span>

- <span data-ttu-id="e0686-139">Välj alla loggar för en viss tabell.</span><span class="sxs-lookup"><span data-stu-id="e0686-139">Select all logs for a particular table.</span></span>
- <span data-ttu-id="e0686-140">Välj specifika typer av databaslogg.</span><span class="sxs-lookup"><span data-stu-id="e0686-140">Select specific types of database log.</span></span>
- <span data-ttu-id="e0686-141">Välj ett datum och en tidpunkt då en logg skapas.</span><span class="sxs-lookup"><span data-stu-id="e0686-141">Select a date and time that a log was created.</span></span>

<span data-ttu-id="e0686-142">Följ dessa steg för att ställa in rensning av databaslogg:</span><span class="sxs-lookup"><span data-stu-id="e0686-142">To set up database log cleanup, follow these steps:</span></span> 

1. <span data-ttu-id="e0686-143">Gå till **Systemadministration > Länkar > Databasen > Databaslogg**.</span><span class="sxs-lookup"><span data-stu-id="e0686-143">Go to **System administration > Links > Database > Database log**.</span></span> <span data-ttu-id="e0686-144">Välj **Rensa logg**.</span><span class="sxs-lookup"><span data-stu-id="e0686-144">Select **Clean up log**.</span></span>

2. <span data-ttu-id="e0686-145">Välj en metod för att välja loggar att ta bort genom att ange något av följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="e0686-145">Choose a method of selecting logs to delete by entering one of the following options:</span></span>

   - <span data-ttu-id="e0686-146">Register-ID</span><span class="sxs-lookup"><span data-stu-id="e0686-146">Table ID</span></span>
   - <span data-ttu-id="e0686-147">Typ av logg</span><span class="sxs-lookup"><span data-stu-id="e0686-147">Type of log</span></span>
   - <span data-ttu-id="e0686-148">Skapat datum och klockslag</span><span class="sxs-lookup"><span data-stu-id="e0686-148">Created date and time</span></span>

3. <span data-ttu-id="e0686-149">Använd fliken **Rensning i databasloggen** för att bestämma när loggrensningsuppgiften ska köras.</span><span class="sxs-lookup"><span data-stu-id="e0686-149">Use the **Database log cleanup** tab to determine when to run the log cleanup task.</span></span> <span data-ttu-id="e0686-150">Som standard är databasloggar tillgängliga i 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="e0686-150">By default, database logs are available for 30 days.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]