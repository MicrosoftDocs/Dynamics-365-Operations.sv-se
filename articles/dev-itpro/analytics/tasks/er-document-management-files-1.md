--- 
title: "Förbered datamodeller för användning av dokumenthanteringsfiler i ER-utdata"
description: "I följande steg beskrivs hur en användare som tilldelats en roll som systemadministratör eller utvecklare för elektronisk rapportering kan konfigurera ett format för elektronisk rapportering (ER) för att använda dokumenthanteringsfiler (bilagor) i ER-utmatningar."
author: NickSelin
manager: AnnBe
ms.date: 10/28/2016
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
ms.openlocfilehash: fcafaf17315f54594116a143f36e924bc705d839
ms.contentlocale: sv-se
ms.lasthandoff: 08/09/2018

---
# <a name="prepare-data-models-to-use-document-management-files-in-er-output"></a><span data-ttu-id="17e68-103">Förbered datamodeller för användning av dokumenthanteringsfiler i ER-utdata</span><span class="sxs-lookup"><span data-stu-id="17e68-103">Prepare data models to use Document Management files in ER output</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="17e68-104">I följande steg beskrivs hur en användare som tilldelats en roll som systemadministratör eller utvecklare för elektronisk rapportering kan konfigurera ett format för elektronisk rapportering (ER) för att använda dokumenthanteringsfiler (bilagor) i ER-utmatningar.</span><span class="sxs-lookup"><span data-stu-id="17e68-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to use Document Management files (attachments) in ER output.</span></span> <span data-ttu-id="17e68-105">Dessa steg kan utföras på valfritt företag.</span><span class="sxs-lookup"><span data-stu-id="17e68-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="17e68-106">För att slutföra dessa steg måste du först slutföra stegen i proceduren "Skapa en konfigurationsleverantör och välj den som aktiv”.</span><span class="sxs-lookup"><span data-stu-id="17e68-106">To complete these steps, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span>

<span data-ttu-id="17e68-107">Denna procedur är avsedd för en funktion som lades till i Dynamics 365 for Operations version 1611.</span><span class="sxs-lookup"><span data-stu-id="17e68-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="get-access-to-the-list-of-configurations-provided-by-microsoft"></a><span data-ttu-id="17e68-108">Få åtkomst till listan med konfigurationer som tillhandahålls av Microsoft</span><span class="sxs-lookup"><span data-stu-id="17e68-108">Get access to the list of configurations provided by Microsoft</span></span>
1. <span data-ttu-id="17e68-109">Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="17e68-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="17e68-110">Kontrollera att ”Litware Inc."-leverantören</span><span class="sxs-lookup"><span data-stu-id="17e68-110">Make sure that the 'Litware, Inc.'</span></span> <span data-ttu-id="17e68-111">är tillgänglig och markerats som aktiv.</span><span class="sxs-lookup"><span data-stu-id="17e68-111">provider is available and marked as active.</span></span>  
2. <span data-ttu-id="17e68-112">Välj Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="17e68-112">Select the 'Litware, Inc.'</span></span> <span data-ttu-id="17e68-113">leverantör.</span><span class="sxs-lookup"><span data-stu-id="17e68-113">provider.</span></span>
3. <span data-ttu-id="17e68-114">Klicka på Databaser.</span><span class="sxs-lookup"><span data-stu-id="17e68-114">Click Repositories.</span></span>
    * <span data-ttu-id="17e68-115">Om en databas av typen "Operations resources" redan finns, hoppa då över återstående steg för den aktuella underuppgiften.</span><span class="sxs-lookup"><span data-stu-id="17e68-115">If a repository of the 'Operations resources' type already exists, skip the remaining steps of the current sub-task.</span></span>  
4. <span data-ttu-id="17e68-116">Klicka på Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="17e68-116">Click Add to open the drop dialog.</span></span>
5. <span data-ttu-id="17e68-117">Ange "Operations resources" i fältet Configuration repository type.</span><span class="sxs-lookup"><span data-stu-id="17e68-117">In the Configuration repository type field, enter 'Operations resources'.</span></span>
6. <span data-ttu-id="17e68-118">Klicka på Skapa en databas.</span><span class="sxs-lookup"><span data-stu-id="17e68-118">Click Create repository.</span></span>
7. <span data-ttu-id="17e68-119">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="17e68-119">Click OK.</span></span>

## <a name="get-the-customer-invoice-model-configurations-provided-by-microsoft"></a><span data-ttu-id="17e68-120">Skaffa modellkonfigurationerna för kundfakturor som tillhandahålls av Microsoft</span><span class="sxs-lookup"><span data-stu-id="17e68-120">Get the Customer invoice model configurations provided by Microsoft</span></span>
1. <span data-ttu-id="17e68-121">Klicka på Visa filter.</span><span class="sxs-lookup"><span data-stu-id="17e68-121">Click Show filters.</span></span>
2. <span data-ttu-id="17e68-122">Använd följande filter: Ange filtervärdet "Operations resources" på fältet "Name" med filteroperatorn "begins with"; ange filtervärdet "" på fältet "Description" med filteroperatorn "begins with".</span><span class="sxs-lookup"><span data-stu-id="17e68-122">Apply the following filters: Enter a filter value of "Operations resources" on the "Name" field using the "begins with" filter operator; Enter a filter value of "" on the "Description" field using the "begins with" filter operator</span></span>
3. <span data-ttu-id="17e68-123">Klicka på Visa filter.</span><span class="sxs-lookup"><span data-stu-id="17e68-123">Click Show filters.</span></span>
4. <span data-ttu-id="17e68-124">Klicka på Öppna.</span><span class="sxs-lookup"><span data-stu-id="17e68-124">Click Open.</span></span>
5. <span data-ttu-id="17e68-125">Välj "Customer invoice model" i trädet.</span><span class="sxs-lookup"><span data-stu-id="17e68-125">In the tree, select 'Customer invoice model'.</span></span>
    * <span data-ttu-id="17e68-126">Välj modellkonfigurationen "Customer invoice model" för att importera den.</span><span class="sxs-lookup"><span data-stu-id="17e68-126">Select the model configuration 'Customer invoice model' to import it.</span></span>  
6. <span data-ttu-id="17e68-127">Klicka på Importera.</span><span class="sxs-lookup"><span data-stu-id="17e68-127">Click Import.</span></span>
    * <span data-ttu-id="17e68-128">Klicka på Import for version 1 för den valda konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="17e68-128">Click Import for version 1 of the selected configuration.</span></span>  
7. <span data-ttu-id="17e68-129">Klicka på Ja.</span><span class="sxs-lookup"><span data-stu-id="17e68-129">Click Yes.</span></span>
8. <span data-ttu-id="17e68-130">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="17e68-130">Close the page.</span></span>
9. <span data-ttu-id="17e68-131">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="17e68-131">Close the page.</span></span>
10. <span data-ttu-id="17e68-132">Klicka på Reporting configurations.</span><span class="sxs-lookup"><span data-stu-id="17e68-132">Click Reporting configurations.</span></span>
11. <span data-ttu-id="17e68-133">Välj "Customer invoice model" i trädet.</span><span class="sxs-lookup"><span data-stu-id="17e68-133">In the tree, select 'Customer invoice model'.</span></span>

## <a name="create-the-derived-model-to-support-access-to-the-document-management-files"></a><span data-ttu-id="17e68-134">Skapa den härledda modellen så att denna stöder åtkomst till dokumenthanteringsfilerna.</span><span class="sxs-lookup"><span data-stu-id="17e68-134">Create the derived model to support access to the Document Management files.</span></span>
    * <span data-ttu-id="17e68-135">Du kan skapa en egen konfiguration av kundfakturamodellen baserat på den konfiguration som tillhandahålls av Microsoft.</span><span class="sxs-lookup"><span data-stu-id="17e68-135">You will create our own configuration of the Customer invoice model deriving it from the configuration provided by Microsoft.</span></span> <span data-ttu-id="17e68-136">Du använder den här konfigurationen för att implementera åtkomst till dokumenthanteringsfilerna och göra dem tillgängliga för elektroniska dokument som du skapar baserat på denna modell.</span><span class="sxs-lookup"><span data-stu-id="17e68-136">You will use this configuration to implement access to the Document Management files and make them available for electronic documents that you will create based on this model.</span></span>  
1. <span data-ttu-id="17e68-137">Klicka på Skapa konfiguration om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="17e68-137">Click Create configuration to open the drop dialog.</span></span>
2. <span data-ttu-id="17e68-138">Ange "Derive from Name: Customer invoice model, Microsoft" i fältet New.</span><span class="sxs-lookup"><span data-stu-id="17e68-138">In the New field, enter 'Derive from Name: Customer invoice model, Microsoft'.</span></span>
3. <span data-ttu-id="17e68-139">Ange "Customer invoice model (custom)" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="17e68-139">In the Name field, type 'Customer invoice model (custom)'.</span></span>
    * <span data-ttu-id="17e68-140">Fakturamodell för kund (anpassad)</span><span class="sxs-lookup"><span data-stu-id="17e68-140">Customer invoice model (custom)</span></span>  
4. <span data-ttu-id="17e68-141">Klicka på Skapa konfiguration.</span><span class="sxs-lookup"><span data-stu-id="17e68-141">Click Create configuration.</span></span>


