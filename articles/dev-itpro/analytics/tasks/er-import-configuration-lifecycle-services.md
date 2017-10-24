--- 
title: "Importera en konfiguration från Lifecycle Services för elektronisk rapportering (ER)"
description: "I följande steg förklaras hur en användare i rollen Systemadministratör eller Utvecklare för elektronisk rapportering kan importera en ny version av en konfiguration för elektronisk rapportering (ER) från Microsoft Lifecycle Services (LCS)."
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
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 9eb4f54897c84b98828c927f0f93613583fd4599
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="import-a-configuration-from-lifecycle-services-for-electronic-reporting-er"></a><span data-ttu-id="fccb0-103">Importera en konfiguration från Lifecycle Services för elektronisk rapportering (ER)</span><span class="sxs-lookup"><span data-stu-id="fccb0-103">Import a configuration from Lifecycle Services for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="fccb0-104">I följande steg förklaras hur en användare i rollen Systemadministratör eller Utvecklare för elektronisk rapportering kan importera en ny version av en konfiguration för elektronisk rapportering (ER) från Microsoft Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="fccb0-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can import a new version of an Electronic reporting (ER) configuration from Microsoft Lifecycle Services (LCS).</span></span>

<span data-ttu-id="fccb0-105">I det här exemplet ska du välja önskad versio av ER-konfigurationen och importera den för exempelföretaget, Litware, Inc. Dessa steg kan utföras i alla företag eftersom ER-konfigureringar delas mellan företag.</span><span class="sxs-lookup"><span data-stu-id="fccb0-105">In this example, you will select the desired version of the ER configuration and import it for sample company, Litware, Inc. These steps can be performed in any company as ER configurations are shared among companies.</span></span> <span data-ttu-id="fccb0-106">För att slutföra dessa steg måste du först slutföra stegen i proceduren "Överföra en ER-konfiguration till Lifecycle Services”.</span><span class="sxs-lookup"><span data-stu-id="fccb0-106">To complete these steps, you must first complete the steps in the “Upload an ER configuration into Lifecycle Services” procedure.</span></span> <span data-ttu-id="fccb0-107">Åtkomst till LCS krävs även för att slutföra dessa steg.</span><span class="sxs-lookup"><span data-stu-id="fccb0-107">Access to LCS is also required for completion of these steps.</span></span>

1. <span data-ttu-id="fccb0-108">Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="fccb0-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="fccb0-109">Klientkonfigurationer.</span><span class="sxs-lookup"><span data-stu-id="fccb0-109">Click Configurations.</span></span>

## <a name="delete-a-shared-version-of-data-model-configuration"></a><span data-ttu-id="fccb0-110">Ta bort en delad version av konfiguration av datamodell</span><span class="sxs-lookup"><span data-stu-id="fccb0-110">Delete a shared version of data model configuration</span></span>
1. <span data-ttu-id="fccb0-111">Välj "Konfiguration av exempelmodell" i trädet.</span><span class="sxs-lookup"><span data-stu-id="fccb0-111">In the tree, select 'Sample model configuration'.</span></span>
    * <span data-ttu-id="fccb0-112">Den första versionen av en konfiguration av exempeldatamodell har skapats och har publicerats till LCS under proceduren "Överför en ER-konfiguration till Lifecycle Services".</span><span class="sxs-lookup"><span data-stu-id="fccb0-112">The first version of a sample data model configuration has been created and published to LCS during the “Upload an ER configuration into Lifecycle Services” procedure.</span></span> <span data-ttu-id="fccb0-113">I den här proceduren kommer du ta bort den här versionen av ER-konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="fccb0-113">In this procedure, you will delete this version of the ER configuration.</span></span> <span data-ttu-id="fccb0-114">Denna version av en konfiguration av exempeldatamodell kommer att importeras senare från LCS.</span><span class="sxs-lookup"><span data-stu-id="fccb0-114">This version of a sample data model configuration will be imported later from LCS.</span></span>  
2. <span data-ttu-id="fccb0-115">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="fccb0-115">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="fccb0-116">Välj versionen av den här konfigurationen som har statusen "Delad".</span><span class="sxs-lookup"><span data-stu-id="fccb0-116">Select the version of this configuration that is in the ‘Shared’ status.</span></span> <span data-ttu-id="fccb0-117">Statusen visar att konfigurationen har publicerats till LCS.</span><span class="sxs-lookup"><span data-stu-id="fccb0-117">This status indicates that the configuration has been published to LCS.</span></span>  
3. <span data-ttu-id="fccb0-118">Klicka på Ändra status.</span><span class="sxs-lookup"><span data-stu-id="fccb0-118">Click Change status.</span></span>
4. <span data-ttu-id="fccb0-119">Klicka på Upphör.</span><span class="sxs-lookup"><span data-stu-id="fccb0-119">Click Discontinue.</span></span>
    * <span data-ttu-id="fccb0-120">Ändra status för den valda versionen från ”Delad" till "Upphörd" om du vill göra det tillgänglig för radering.</span><span class="sxs-lookup"><span data-stu-id="fccb0-120">Change the status of the selected version from ‘Shared’ to ‘Discontinued’ to make it available for deletion.</span></span>  
5. <span data-ttu-id="fccb0-121">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="fccb0-121">Click OK.</span></span>
6. <span data-ttu-id="fccb0-122">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="fccb0-122">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="fccb0-123">Välj versionen av den här konfigurationen som har statusen "Upphörd".</span><span class="sxs-lookup"><span data-stu-id="fccb0-123">Select the version of this configuration that has a status of ‘Discontinued’.</span></span>  
7. <span data-ttu-id="fccb0-124">Klicka på Ta bort.</span><span class="sxs-lookup"><span data-stu-id="fccb0-124">Click Delete.</span></span>
8. <span data-ttu-id="fccb0-125">Klicka på Ja.</span><span class="sxs-lookup"><span data-stu-id="fccb0-125">Click Yes.</span></span>
    * <span data-ttu-id="fccb0-126">Observera att den enda utkastversionen 2 i den valda konfigurationen av datamodell är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="fccb0-126">Note that the only draft version 2 of the selected data model configuration is available.</span></span>  
9. <span data-ttu-id="fccb0-127">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="fccb0-127">Close the page.</span></span>

## <a name="import-a-shared-version-of-data-model-configuration-from-lcs"></a><span data-ttu-id="fccb0-128">Importera en delad version av konfiguration av datamodell från LCS</span><span class="sxs-lookup"><span data-stu-id="fccb0-128">Import a shared version of data model configuration from LCS</span></span>
1. <span data-ttu-id="fccb0-129">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="fccb0-129">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="fccb0-130">Öppna listan över databaser för Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="fccb0-130">Open the list of repositories for the ‘Litware, Inc.’</span></span> <span data-ttu-id="fccb0-131">konfigurationsleverantör.</span><span class="sxs-lookup"><span data-stu-id="fccb0-131">configuration provider.</span></span>  
2. <span data-ttu-id="fccb0-132">Klicka på Databaser.</span><span class="sxs-lookup"><span data-stu-id="fccb0-132">Click Repositories.</span></span>
3. <span data-ttu-id="fccb0-133">Klicka på Öppna.</span><span class="sxs-lookup"><span data-stu-id="fccb0-133">Click Open.</span></span>
    * <span data-ttu-id="fccb0-134">Välj LCS-databasen och öppna den.</span><span class="sxs-lookup"><span data-stu-id="fccb0-134">Select the LCS repository and open it.</span></span>  
4. <span data-ttu-id="fccb0-135">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="fccb0-135">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="fccb0-136">Välj den första versionen av "Konfiguration av exempelmodell" i versionlistan.</span><span class="sxs-lookup"><span data-stu-id="fccb0-136">Select the first version of the 'Sample model configuration' in the versions list.</span></span>  
5. <span data-ttu-id="fccb0-137">Klicka på Importera.</span><span class="sxs-lookup"><span data-stu-id="fccb0-137">Click Import.</span></span>
6. <span data-ttu-id="fccb0-138">Klicka på Ja.</span><span class="sxs-lookup"><span data-stu-id="fccb0-138">Click Yes.</span></span>
    * <span data-ttu-id="fccb0-139">Bekräfta importen av den valda versionen från LCS.</span><span class="sxs-lookup"><span data-stu-id="fccb0-139">Confirm the import of the selected version from LCS .</span></span>  
    * <span data-ttu-id="fccb0-140">Observera att informationmeddelandet (över formuläret) bekräftar lyckad import av den valda versionen.</span><span class="sxs-lookup"><span data-stu-id="fccb0-140">Note that the information message (above the form) confirms the successful completion of the import of the selected version.</span></span>  
7. <span data-ttu-id="fccb0-141">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="fccb0-141">Close the page.</span></span>
8. <span data-ttu-id="fccb0-142">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="fccb0-142">Close the page.</span></span>
9. <span data-ttu-id="fccb0-143">Klientkonfigurationer.</span><span class="sxs-lookup"><span data-stu-id="fccb0-143">Click Configurations.</span></span>
10. <span data-ttu-id="fccb0-144">Välj "Konfiguration av exempelmodell" i trädet.</span><span class="sxs-lookup"><span data-stu-id="fccb0-144">In the tree, select 'Sample model configuration'.</span></span>
11. <span data-ttu-id="fccb0-145">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="fccb0-145">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="fccb0-146">Välj versionen av den här konfigurationen som har statusen "Delad".</span><span class="sxs-lookup"><span data-stu-id="fccb0-146">Select the version of this configuration that has a status of ‘Shared’.</span></span>  
    * <span data-ttu-id="fccb0-147">Observera att den enda delade versionen 1 i den valda konfigurationen av datamodell nu också är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="fccb0-147">Note that the shared version 1 of the selected data model configuration is available now as well.</span></span>  


