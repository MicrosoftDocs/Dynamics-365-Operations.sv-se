---
title: Frågor och svar om publicering
description: Det här avsnittet innehåller en lista med vanliga frågor om hur du arbetar med ett Dynamics 365 Human Resources implementeringsprojekt.
author: rachel-profitt
manager: tfehr
ms.date: 10/13/2020
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
ms.author: raprofit
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 64a85840be328702a06779390fe383fd1896fd04
ms.sourcegitcommit: d66fd72342931fad25a696b251c05781280d36c4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/14/2020
ms.locfileid: "4011440"
---
# <a name="go-live-faq"></a><span data-ttu-id="d90cc-103">Frågor och svar om publicering</span><span class="sxs-lookup"><span data-stu-id="d90cc-103">Go-live FAQ</span></span> 

<span data-ttu-id="d90cc-104">Det här avsnittet innehåller en lista med vanliga frågor om hur du arbetar med ett Dynamics 365 Human Resources implementeringsprojekt.</span><span class="sxs-lookup"><span data-stu-id="d90cc-104">This topic lists frequently asked questions about how to go live with a Dynamics 365 Human Resources implementation project.</span></span> 

## <a name="when-can-i-configure-and-request-my-production-environment"></a><span data-ttu-id="d90cc-105">När kan jag konfigurera och begära produktionsmiljön?</span><span class="sxs-lookup"><span data-stu-id="d90cc-105">When can I configure and request my production environment?</span></span> 

<span data-ttu-id="d90cc-106">Vanligtvis distribueras en produktionsmiljö när följande kriterier är uppfylla:</span><span class="sxs-lookup"><span data-stu-id="d90cc-106">Typically, a production environment is deployed after meeting the following criteria:</span></span>

- <span data-ttu-id="d90cc-107">Alla anpassningar är kodslutförda.</span><span class="sxs-lookup"><span data-stu-id="d90cc-107">All customizations are code-complete.</span></span>
- <span data-ttu-id="d90cc-108">Testning av användargodkännande (UAT) har slutförts.</span><span class="sxs-lookup"><span data-stu-id="d90cc-108">User acceptance testing (UAT) is complete.</span></span>
- <span data-ttu-id="d90cc-109">Kunden har signerat lösningen.</span><span class="sxs-lookup"><span data-stu-id="d90cc-109">The customer has signed off on the solution.</span></span>
- <span data-ttu-id="d90cc-110">Det finns inga blockeringsproblem för publicering.</span><span class="sxs-lookup"><span data-stu-id="d90cc-110">There are no blocking issues for go-live.</span></span> 

<span data-ttu-id="d90cc-111">När kvalificerade kunder är på det här stadiet arbetar Microsoft FastTrack-teamet med projektgruppen för att utföra en publiceringsutvärdering.</span><span class="sxs-lookup"><span data-stu-id="d90cc-111">When qualified customers are at this stage, the Microsoft FastTrack team will work with the project team to do a go-live assessment.</span></span> 

## <a name="what-are-the-prerequisites-to-deploying-a-production-environment"></a><span data-ttu-id="d90cc-112">Vilka förutsättningar är nödvändiga för att driftsätta en produktionsmiljö?</span><span class="sxs-lookup"><span data-stu-id="d90cc-112">What are the prerequisites to deploying a production environment?</span></span> 

<span data-ttu-id="d90cc-113">En lista med förutsättningar finns i  [förbereda för publicering](hr-admin-go-live-prepare.md).</span><span class="sxs-lookup"><span data-stu-id="d90cc-113">For a list of the prerequisites, see [Prepare for go-live](hr-admin-go-live-prepare.md).</span></span> 

## <a name="what-is-a-go-live-assessment"></a><span data-ttu-id="d90cc-114">Vad är en publiceringsutvärdering?</span><span class="sxs-lookup"><span data-stu-id="d90cc-114">What is a go-live assessment?</span></span>  

<span data-ttu-id="d90cc-115">Publiceringsutvärdering är en del av  [Microsoft FastTrack-programmet](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/fasttrack-dynamics-365-overview).</span><span class="sxs-lookup"><span data-stu-id="d90cc-115">The go-live assessment is part of the [Microsoft FastTrack program](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/fasttrack-dynamics-365-overview).</span></span> <span data-ttu-id="d90cc-116">Under den här recensionen bedömer en lösningsarkitekt om ett implementeringsprojekt är klart för en lyckad övergång och publicering.</span><span class="sxs-lookup"><span data-stu-id="d90cc-116">During this review, a solution architect assesses whether an implementation project is ready for a successful cutover and go-live.</span></span> <span data-ttu-id="d90cc-117">Den här recensionen är obligatorisk för varje implementationsprojekt innan du kan begära att bli aktivt i en produktionsmiljö.</span><span class="sxs-lookup"><span data-stu-id="d90cc-117">This review is mandatory for every implementation project before you can request to go live in a production environment.</span></span> 

## <a name="our-sandbox-environments-are-deployed-in-the-central-us-datacenter-we-want-our-production-environments-to-be-deployed-in-the-west-us-datacenter-can-i-select-west-us-as-the-datacenter-in-my-production-configuration"></a><span data-ttu-id="d90cc-118">Våra begränsade miljöer distribueras i det centrala amerikanska datacentret.</span><span class="sxs-lookup"><span data-stu-id="d90cc-118">Our Sandbox environments are deployed in the Central US datacenter.</span></span> <span data-ttu-id="d90cc-119">Vi vill att våra produktionsmiljöer distribueras i det västra amerikanska datacentret.</span><span class="sxs-lookup"><span data-stu-id="d90cc-119">We want our Production environments to be deployed in the West US datacenter.</span></span> <span data-ttu-id="d90cc-120">Kan jag välja västra USA som datacenter i min produktionskonfiguration?</span><span class="sxs-lookup"><span data-stu-id="d90cc-120">Can I select West US as the datacenter in my Production configuration?</span></span> 

<span data-ttu-id="d90cc-121">LCS begränsar dig inte från att välja ett annat datacenter när du distribuerar Human Resources-miljöer, men vi rekommenderar att du inte väljer ett annat datacenter.</span><span class="sxs-lookup"><span data-stu-id="d90cc-121">LCS doesn't restrict you from selecting a different data center when you deploy a Human Resources environment, but we strongly recommend not selecting a different data center.</span></span>  

<span data-ttu-id="d90cc-122">Om du vill att din produktionsmiljö ska finnas i det västra amerikanska datacentret bör du först omdistribuera begränsade miljön till det västra amerikanska datacentret, testa dem och sedan godkänna.</span><span class="sxs-lookup"><span data-stu-id="d90cc-122">If you want your Production environment to be in the West US datacenter, you should first redeploy your Sandbox environments to the West US datacenter, test them, and sign off.</span></span> 

<span data-ttu-id="d90cc-123">Information om hur du väljer rätt datacenter finns i [nätverkskrav](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/system-requirements#network-requirements).</span><span class="sxs-lookup"><span data-stu-id="d90cc-123">For information about selecting the correct datacenter, see [Network requirements](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/system-requirements#network-requirements).</span></span> 

## <a name="what-level-of-access-do-i-have-to-the-azure-resources-for-my-human-resources-environments"></a><span data-ttu-id="d90cc-124">Vilken åtkomstnivå till Azure-resurserna för mina Human Resources-miljöer?</span><span class="sxs-lookup"><span data-stu-id="d90cc-124">What level of access do I have to the Azure resources for my Human Resources environments?</span></span>  

<span data-ttu-id="d90cc-125">Åtkomst till Human Resources-miljöer är begränsad.</span><span class="sxs-lookup"><span data-stu-id="d90cc-125">Access to the Human Resources environments is limited.</span></span> <span data-ttu-id="d90cc-126">Du kan inte komma åt den virtuella datorn (VM) eller Microsoft Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="d90cc-126">You can't access the virtual machine (VM) or Microsoft Internet Information Services (IIS).</span></span> <span data-ttu-id="d90cc-127">Du kan inte heller komma åt databasen via Microsoft SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="d90cc-127">You also can't access the database through Microsoft SQL Server Management Studio.</span></span> 

<span data-ttu-id="d90cc-128">Även om du inte kan komma åt dina Azure-resurser eller din Dynamics 365 Human Resources-miljö direkt, finns det fler funktioner som du kan använda för att komma åt dina data:</span><span class="sxs-lookup"><span data-stu-id="d90cc-128">Although you can't access your Azure resources or Dynamics 365 Human Resources environment directly, there are additional features you can use to access your data:</span></span>

- <span data-ttu-id="d90cc-129">Du kan distribuera en Azure SQL-databas i din egen Azure-klient och använda funktionen ta med din egen databas (BYOD) för att synkronisera data.</span><span class="sxs-lookup"><span data-stu-id="d90cc-129">You can deploy an Azure SQL database in your own Azure tenant and use the Bring Your Own Database (BYOD) feature to synchronize data.</span></span> <span data-ttu-id="d90cc-130">Mer information finns i [ta din egen databas (BYOD)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/export-entities-to-your-own-database).</span><span class="sxs-lookup"><span data-stu-id="d90cc-130">For more information, see [Bring your own database (BYOD)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/export-entities-to-your-own-database).</span></span>

- <span data-ttu-id="d90cc-131">Du kan använda Common Data Service-integrering för att synkronisera valda enheter i Common Data Service-databasen.</span><span class="sxs-lookup"><span data-stu-id="d90cc-131">You can use Common Data Service integration to synchronize select entities into the Common Data Service database.</span></span> <span data-ttu-id="d90cc-132">Mer information finns i [Common Data Service-entiteter](hr-developer-entities.md).</span><span class="sxs-lookup"><span data-stu-id="d90cc-132">For more information, see [Common Data Service entities](hr-developer-entities.md).</span></span> 

## <a name="how-often-is-my-production-database-backed-up"></a><span data-ttu-id="d90cc-133">Hur ofta säkerhetskopieras min produktionsdatabas?</span><span class="sxs-lookup"><span data-stu-id="d90cc-133">How often is my production database backed up?</span></span> 

<span data-ttu-id="d90cc-134">Databaser skyddas med automatiska säkerhetskopieringar enligt följande frekvenser:</span><span class="sxs-lookup"><span data-stu-id="d90cc-134">Databases are protected by automatic backups at the following frequencies:</span></span>

| <span data-ttu-id="d90cc-135">Typ av säkerhetskopiering</span><span class="sxs-lookup"><span data-stu-id="d90cc-135">Type of backup</span></span> | <span data-ttu-id="d90cc-136">Frekvens</span><span class="sxs-lookup"><span data-stu-id="d90cc-136">Frequency</span></span> |
| --- | --- |
| <span data-ttu-id="d90cc-137">Fullständig säkerhetskopia av databaser</span><span class="sxs-lookup"><span data-stu-id="d90cc-137">Full database backup</span></span> | <span data-ttu-id="d90cc-138">Varje vecka</span><span class="sxs-lookup"><span data-stu-id="d90cc-138">Weekly</span></span> |
| <span data-ttu-id="d90cc-139">Säkerhetskopiering av differentiella databaser</span><span class="sxs-lookup"><span data-stu-id="d90cc-139">Differential database backup</span></span> | <span data-ttu-id="d90cc-140">Var 12-24 timme</span><span class="sxs-lookup"><span data-stu-id="d90cc-140">Every 12-24 hours</span></span> |
| <span data-ttu-id="d90cc-141">Säkerhetskopiering av transaktionslogg</span><span class="sxs-lookup"><span data-stu-id="d90cc-141">Transaction log backup</span></span> | <span data-ttu-id="d90cc-142">Var 5 till 10 minuter</span><span class="sxs-lookup"><span data-stu-id="d90cc-142">Every 5 to 10 minutes</span></span> |

<span data-ttu-id="d90cc-143">Microsoft behåller tillräckliga säkerhetskopior för att tillåta återställning till tidpunkt (PITR) under de senaste sju dagarna.</span><span class="sxs-lookup"><span data-stu-id="d90cc-143">Microsoft retains sufficient backups to allow for Point in Time Restore (PITR) within the last seven days.</span></span> 

<span data-ttu-id="d90cc-144">Mer information finns i  [Läs mer om automatisk säkerhetskopiering av SQL databaser](https://docs.microsoft.com/azure/azure-sql/database/automated-backups-overview?tabs=single-database).</span><span class="sxs-lookup"><span data-stu-id="d90cc-144">For more information, see [Learn about automatic SQL Database backups](https://docs.microsoft.com/azure/azure-sql/database/automated-backups-overview?tabs=single-database).</span></span> 

## <a name="can-i-request-a-copy-of-the-backup-of-my-production-database"></a><span data-ttu-id="d90cc-145">Kan jag begära en kopia av säkerhetskopian av min produktionsdatabas?</span><span class="sxs-lookup"><span data-stu-id="d90cc-145">Can I request a copy of the backup of my production database?</span></span> 

<span data-ttu-id="d90cc-146">Nr</span><span class="sxs-lookup"><span data-stu-id="d90cc-146">No.</span></span> <span data-ttu-id="d90cc-147">Du kan skicka en servicebegäran om databasuppdatering för att kopiera din produktionsmiljö till miljö i begränsat läge.</span><span class="sxs-lookup"><span data-stu-id="d90cc-147">You can submit a database refresh service request to copy your Production environment to your Sandbox environment, however.</span></span> <span data-ttu-id="d90cc-148">Du kan distribuera en Azure SQL-databas i din egen Azure-klient och använda BYOD-funktionen för att synkronisera data från din egen produktionsmiljö.</span><span class="sxs-lookup"><span data-stu-id="d90cc-148">You can deploy an Azure SQL database in your own Azure tenant and use the BYOD feature to synchronize data from your Production environment.</span></span> <span data-ttu-id="d90cc-149">Mer information finns i [ta din egen databas (BYOD)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/export-entities-to-your-own-database).</span><span class="sxs-lookup"><span data-stu-id="d90cc-149">For more information, see [Bring your own database (BYOD)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/export-entities-to-your-own-database).</span></span> 

## <a name="how-do-i-move-my-sandbox-environment-to-production-for-go-live"></a><span data-ttu-id="d90cc-150">Hur flyttar jag min miljö i begränsat läge till produktion för publicering?</span><span class="sxs-lookup"><span data-stu-id="d90cc-150">How do I move my Sandbox environment to Production for go-live?</span></span> 

<span data-ttu-id="d90cc-151">Eftersom en kopieringsfunktion inte är tillgänglig för att flytta din miljö från en miljö i begränsat läge till en produktionsmiljö, måste du använda datapaket för att flytta data till din produktionsmiljö.</span><span class="sxs-lookup"><span data-stu-id="d90cc-151">Because a copy feature isn't available to move your environment from a Sandbox to a Production environment, you must use data packages to move data into your Production environment.</span></span>  

<span data-ttu-id="d90cc-152">Vi rekommenderar att du underhåller en rensad lista med enheter som har konfigurerats i din miljö med begränsat läge i hela projektet.</span><span class="sxs-lookup"><span data-stu-id="d90cc-152">We recommend maintaining a clear list of entities configured in your Sandbox throughout the project.</span></span> <span data-ttu-id="d90cc-153">Testa sedan processen för övergång och migrering av alla datapaket som behövs för din publicering.</span><span class="sxs-lookup"><span data-stu-id="d90cc-153">Then test the process of cutover and migration of any data packages needed for your go-live.</span></span> <span data-ttu-id="d90cc-154">Du måste manuellt flytta alla datapaket till produktionsmiljön när du är redo att publicera.</span><span class="sxs-lookup"><span data-stu-id="d90cc-154">You must manually move any data packages into the Production environment when you are ready to go live.</span></span> 

## <a name="what-should-i-do-if-my-production-environment-is-down"></a><span data-ttu-id="d90cc-155">Vad ska jag göra om min produktionsmiljö är ur drift?</span><span class="sxs-lookup"><span data-stu-id="d90cc-155">What should I do if my Production environment is down?</span></span> 

<span data-ttu-id="d90cc-156">Om du vill rapportera ett produktionsavbrott följer du processen som beskrivs i  [rapportera ett produktionsavbrott](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/report-production-outage).</span><span class="sxs-lookup"><span data-stu-id="d90cc-156">To report a Production outage, follow the process described in [Report a production outage](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/report-production-outage).</span></span> 

 ## <a name="see-also"></a><span data-ttu-id="d90cc-157">Se även</span><span class="sxs-lookup"><span data-stu-id="d90cc-157">See also</span></span>

 [<span data-ttu-id="d90cc-158">Förbereda publicering</span><span class="sxs-lookup"><span data-stu-id="d90cc-158">Prepare for go-live</span></span>](hr-admin-go-live-prepare.md)