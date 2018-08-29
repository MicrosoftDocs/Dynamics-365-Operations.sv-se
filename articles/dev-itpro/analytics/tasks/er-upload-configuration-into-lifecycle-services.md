--- 
title: "Överför konfigurationer för elektronisk rapportering till Lifecycle Services"
description: "I följande steg förklaras hur en användare i rollen Systemadministratör eller Utvecklare för elektronisk rapportering kan skapa en ny formatkonfiguration för elektronisk rapportering (ER) och överföra den till Microsoft Lifecycle Services (LCS)."
author: NickSelin
manager: AnnBe
ms.date: 05/13/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: e782d33f3748524491dace28008cd9148ae70529
ms.openlocfilehash: 6aa6bf7e08285d18210741ba6618878955009280
ms.contentlocale: sv-se
ms.lasthandoff: 08/09/2018

---
# <a name="upload-electronic-reporting-configurations-into-lifecycle-services"></a><span data-ttu-id="5fbcd-103">Överför konfigurationer för elektronisk rapportering till Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="5fbcd-103">Upload Electronic reporting configurations into Lifecycle Services</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="5fbcd-104">I följande steg förklaras hur en användare i rollen Systemadministratör eller Utvecklare för elektronisk rapportering kan skapa en ny formatkonfiguration för elektronisk rapportering (ER) och överföra den till Microsoft Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="5fbcd-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can create a new Electronic reporting (ER) configuration and upload it into Microsoft Lifecycle Services (LCS).</span></span>

<span data-ttu-id="5fbcd-105">I det här exemplet ska du skapa en konfigurering för bildpunktföretaget, Litware, Inc. och överföra den till LCS. Dessa steg kan utföras i alla företag eftersom ER-konfigureringar delas mellan företag.</span><span class="sxs-lookup"><span data-stu-id="5fbcd-105">In this example, you will create a configuration and upload it to LCS for sample company, Litware, Inc. These steps can be performed in any company as ER configurations are shared among companies.</span></span> <span data-ttu-id="5fbcd-106">För att slutföra dessa steg måste du först slutföra stegen i proceduren "Skapa en konfigurationsleverantör och välj den som aktiv”.</span><span class="sxs-lookup"><span data-stu-id="5fbcd-106">To complete these steps, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span> <span data-ttu-id="5fbcd-107">Åtkomst till LCS krävs även för att slutföra dessa steg.</span><span class="sxs-lookup"><span data-stu-id="5fbcd-107">Access to LCS is also required for completion of these steps.</span></span>

1. <span data-ttu-id="5fbcd-108">Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="5fbcd-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="5fbcd-109">Välj Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="5fbcd-109">Select ‘Litware, Inc.’</span></span> <span data-ttu-id="5fbcd-110">och ställ in som aktiv</span><span class="sxs-lookup"><span data-stu-id="5fbcd-110">and set it as active.</span></span>
3. <span data-ttu-id="5fbcd-111">Klientkonfigurationer.</span><span class="sxs-lookup"><span data-stu-id="5fbcd-111">Click Configurations.</span></span>

## <a name="create-a-new-data-model-configuration"></a><span data-ttu-id="5fbcd-112">Skapa en ny datamodellskonfiguration</span><span class="sxs-lookup"><span data-stu-id="5fbcd-112">Create a new data model configuration</span></span>
1. <span data-ttu-id="5fbcd-113">Klicka på Skapa konfiguration om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="5fbcd-113">Click Create configuration to open the drop dialog.</span></span>
    * <span data-ttu-id="5fbcd-114">Du skapar en konfiguration som innehåller en exempeldatamodell för elektroniska dokument.</span><span class="sxs-lookup"><span data-stu-id="5fbcd-114">You will create a configuration that contains a sample data model for electronic documents.</span></span> <span data-ttu-id="5fbcd-115">Denna konfiguration av datamodellen ska överföras till LCS senare.</span><span class="sxs-lookup"><span data-stu-id="5fbcd-115">This data model configuration will be uploaded into LCS later.</span></span>  
2. <span data-ttu-id="5fbcd-116">Skriv "Konfiguration av exempelmodell" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="5fbcd-116">In the Name field, type 'Sample model configuration'.</span></span>
    * <span data-ttu-id="5fbcd-117">Konfiguration av exempelmodell.</span><span class="sxs-lookup"><span data-stu-id="5fbcd-117">Sample model configuration</span></span>  
3. <span data-ttu-id="5fbcd-118">Skriv "Konfiguration av exempelmodell" i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="5fbcd-118">In the Description field, type 'Sample model configuration'.</span></span>
    * <span data-ttu-id="5fbcd-119">Konfiguration av exempelmodell.</span><span class="sxs-lookup"><span data-stu-id="5fbcd-119">Sample model configuration</span></span>  
4. <span data-ttu-id="5fbcd-120">Klicka på Skapa konfiguration.</span><span class="sxs-lookup"><span data-stu-id="5fbcd-120">Click Create configuration.</span></span>
5. <span data-ttu-id="5fbcd-121">Klicka på Modelldesigner.</span><span class="sxs-lookup"><span data-stu-id="5fbcd-121">Click Model designer.</span></span>
6. <span data-ttu-id="5fbcd-122">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="5fbcd-122">Click New.</span></span>
7. <span data-ttu-id="5fbcd-123">Skriv "Startpunkt" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="5fbcd-123">In the Name field, type 'Entry point'.</span></span>
    * <span data-ttu-id="5fbcd-124">Startpunkt</span><span class="sxs-lookup"><span data-stu-id="5fbcd-124">Entry point</span></span>  
8. <span data-ttu-id="5fbcd-125">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="5fbcd-125">Click Add.</span></span>
9. <span data-ttu-id="5fbcd-126">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="5fbcd-126">Click Save.</span></span>
10. <span data-ttu-id="5fbcd-127">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="5fbcd-127">Close the page.</span></span>
11. <span data-ttu-id="5fbcd-128">Klicka på Ändra status.</span><span class="sxs-lookup"><span data-stu-id="5fbcd-128">Click Change status.</span></span>
12. <span data-ttu-id="5fbcd-129">Klicka på Slutför.</span><span class="sxs-lookup"><span data-stu-id="5fbcd-129">Click Complete.</span></span>
13. <span data-ttu-id="5fbcd-130">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="5fbcd-130">Click OK.</span></span>

## <a name="register-a-new--repository"></a><span data-ttu-id="5fbcd-131">Registrera ett nytt databas</span><span class="sxs-lookup"><span data-stu-id="5fbcd-131">Register a new  repository</span></span>
1. <span data-ttu-id="5fbcd-132">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="5fbcd-132">Close the page.</span></span>
2. <span data-ttu-id="5fbcd-133">Klicka på Databaser.</span><span class="sxs-lookup"><span data-stu-id="5fbcd-133">Click Repositories.</span></span>
    * <span data-ttu-id="5fbcd-134">Detta låter dig öppna listan över databaser för konfigurationsleverantören Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="5fbcd-134">This enables you to open the list of repositories for the Litware, Inc. configuration provider.</span></span>  
3. <span data-ttu-id="5fbcd-135">Klicka på Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="5fbcd-135">Click Add to open the drop dialog.</span></span>
    * <span data-ttu-id="5fbcd-136">Detta låter dig lägga till en ny databas.</span><span class="sxs-lookup"><span data-stu-id="5fbcd-136">This allows you to add a new repository.</span></span>  
4. <span data-ttu-id="5fbcd-137">I fältet Typ av konfigurationsdatabas, välj LCS.</span><span class="sxs-lookup"><span data-stu-id="5fbcd-137">In the Configuration repository type field, select LCS.</span></span>
5. <span data-ttu-id="5fbcd-138">Klicka på Skapa en databas.</span><span class="sxs-lookup"><span data-stu-id="5fbcd-138">Click Create repository.</span></span>
6. <span data-ttu-id="5fbcd-139">Ange eller välj ett värde i fältet Projekt.</span><span class="sxs-lookup"><span data-stu-id="5fbcd-139">In the Project field, enter or select a value.</span></span>
    * <span data-ttu-id="5fbcd-140">Välj önskat LCS-projekt.</span><span class="sxs-lookup"><span data-stu-id="5fbcd-140">Select the desired LCS project.</span></span> <span data-ttu-id="5fbcd-141">Du måste ha åtkomst till projektet.</span><span class="sxs-lookup"><span data-stu-id="5fbcd-141">You must have access to the project.</span></span>  
7. <span data-ttu-id="5fbcd-142">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="5fbcd-142">Click OK.</span></span>
    * <span data-ttu-id="5fbcd-143">Avsluta en ny databaspost.</span><span class="sxs-lookup"><span data-stu-id="5fbcd-143">Complete a new repository entry.</span></span>  
8. <span data-ttu-id="5fbcd-144">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="5fbcd-144">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="5fbcd-145">Välj LCS-databasposten.</span><span class="sxs-lookup"><span data-stu-id="5fbcd-145">Select the LCS repository record.</span></span>  
    * <span data-ttu-id="5fbcd-146">Observera att en registrerad databas markeras av den aktuella leverantören vilket betyder att de enda konfigurationerna som ägs av den leverantören, kan läggas till denna databas och därmed överföras till det valda LCS-projektet.</span><span class="sxs-lookup"><span data-stu-id="5fbcd-146">Note that a registered repository is marked by the current provider meaning that the only configurations owned by that provider can be placed to this repository and, consequently, uploaded into the selected LCS project.</span></span>  
9. <span data-ttu-id="5fbcd-147">Klicka på Öppna.</span><span class="sxs-lookup"><span data-stu-id="5fbcd-147">Click Open.</span></span>
    * <span data-ttu-id="5fbcd-148">Öppna databasen om du vill visa listan över ER-konfigurationer.</span><span class="sxs-lookup"><span data-stu-id="5fbcd-148">Open the repository to view the list of ER configurations.</span></span> <span data-ttu-id="5fbcd-149">Den kommer att vara tom om ett sådant projekt ännu inte har använts för delning av ER-konfigurationer.</span><span class="sxs-lookup"><span data-stu-id="5fbcd-149">It will be empty if this project has not yet been used for ER configurations sharing.</span></span>  
10. <span data-ttu-id="5fbcd-150">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="5fbcd-150">Close the page.</span></span>
11. <span data-ttu-id="5fbcd-151">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="5fbcd-151">Close the page.</span></span>

## <a name="upload-configuration-into-lcs"></a><span data-ttu-id="5fbcd-152">Överför konfigurationen i LCS</span><span class="sxs-lookup"><span data-stu-id="5fbcd-152">Upload configuration into LCS</span></span>
1. <span data-ttu-id="5fbcd-153">Klientkonfigurationer.</span><span class="sxs-lookup"><span data-stu-id="5fbcd-153">Click Configurations.</span></span>
2. <span data-ttu-id="5fbcd-154">Välj "Konfiguration av exempelmodell" i trädet.</span><span class="sxs-lookup"><span data-stu-id="5fbcd-154">In the tree, select 'Sample model configuration'.</span></span>
    * <span data-ttu-id="5fbcd-155">Välj en skapad konfiguration som redan har slutförts.</span><span class="sxs-lookup"><span data-stu-id="5fbcd-155">Select a created configuration that has been already completed.</span></span>  
3. <span data-ttu-id="5fbcd-156">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="5fbcd-156">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="5fbcd-157">Välj vilken version av den valda konfigurationen med statusen "Avslutade".</span><span class="sxs-lookup"><span data-stu-id="5fbcd-157">Select the version of the selected configuration with the status of ‘Completed’.</span></span>  
4. <span data-ttu-id="5fbcd-158">Klicka på Ändra status.</span><span class="sxs-lookup"><span data-stu-id="5fbcd-158">Click Change status.</span></span>
5. <span data-ttu-id="5fbcd-159">Klicka Dela.</span><span class="sxs-lookup"><span data-stu-id="5fbcd-159">Click Share.</span></span>
    * <span data-ttu-id="5fbcd-160">Konfigurationstatusen ändras från "Avslutade” till "Delade" när den publiceras i LCS.</span><span class="sxs-lookup"><span data-stu-id="5fbcd-160">The configuration status will change from ‘Completed’ to ‘Shared’ when it is published in LCS.</span></span>  
6. <span data-ttu-id="5fbcd-161">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="5fbcd-161">Click OK.</span></span>
7. <span data-ttu-id="5fbcd-162">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="5fbcd-162">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="5fbcd-163">Välj konfigurationsversionen som har statusen "Delad".</span><span class="sxs-lookup"><span data-stu-id="5fbcd-163">Select the configuration version with the status of 'Shared'.</span></span>  
    * <span data-ttu-id="5fbcd-164">Observera att statusen för den valda versionen har ändrats från "Slutförd till "Delad".</span><span class="sxs-lookup"><span data-stu-id="5fbcd-164">Note that the status of the selected version has changed from ‘Completed’ to ‘Shared’.</span></span>  
8. <span data-ttu-id="5fbcd-165">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="5fbcd-165">Close the page.</span></span>
9. <span data-ttu-id="5fbcd-166">Klicka på Databaser.</span><span class="sxs-lookup"><span data-stu-id="5fbcd-166">Click Repositories.</span></span>
    * <span data-ttu-id="5fbcd-167">Detta låter dig öppna listan över databaser för konfigurationsleverantören Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="5fbcd-167">This enables you to open the list of repositories for the Litware, Inc. configuration provider.</span></span>  
10. <span data-ttu-id="5fbcd-168">Klicka på Öppna.</span><span class="sxs-lookup"><span data-stu-id="5fbcd-168">Click Open.</span></span>
    * <span data-ttu-id="5fbcd-169">Välj LCS-databasen och öppna den.</span><span class="sxs-lookup"><span data-stu-id="5fbcd-169">Select the LCS repository and open it.</span></span>  
    * <span data-ttu-id="5fbcd-170">Observera att den valda konfigurationen visas som en tillgång för det valda LCS-projektet.</span><span class="sxs-lookup"><span data-stu-id="5fbcd-170">Note that the selected configuration is shown as an asset of the selected LCS project.</span></span>  
    * <span data-ttu-id="5fbcd-171">Öppna LCS med https://lcs.dynamics.com.</span><span class="sxs-lookup"><span data-stu-id="5fbcd-171">Open LCS using https://lcs.dynamics.com.</span></span> <span data-ttu-id="5fbcd-172">Öppna ett projekt som användes tidigare till databasregistrering, öppna "Tillgångbiblioteket" för det här projektet och visa innehållet av tillgångstypen "GER-konfiguration" - den överförda ER-konfigurationen kommer att vara tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="5fbcd-172">Open a project that was used earlier for repository registration, open the ‘Asset library’ of this project, and expand the content of the ‘GER configuration’ asset type – the uploaded ER configuration will be available.</span></span> <span data-ttu-id="5fbcd-173">Observera att den överförda LCS-konfigurationen kan importeras till en annan Microsoft Dynamics 365 for Finance and Operations-instans, om leverantörerna har tillgång till det LCS-projektet.</span><span class="sxs-lookup"><span data-stu-id="5fbcd-173">Note that the uploaded LCS configuration can be imported to another Microsoft Dynamics 365 for Finance and Operations instance if providers have access to this LCS project.</span></span>  


