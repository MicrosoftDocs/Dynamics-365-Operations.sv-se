---
title: ER Använd dokumenthanteringsfiler i formatutmatningar (Del 1 - Förbered datamodellen)
description: I det här avsnittet beskrivs hur du konfigurerar ett elektroniskt rapporteringsformat (ER) för användning av dokumenthanteringsfiler (bilagor) i ER-utdata. (Del 1)
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionRepositoryTable, ERSolutionRepositoryCreateDropDialog, ERSolutionImport,  ERSolutionTable, ERSolutionCreateDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 35bffd6d3688a9887fcdaf4edbd89c344cb9b18d
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5559807"
---
# <a name="er-use-document-management-files-in-format-outputs-part-1---prepare-data-model"></a><span data-ttu-id="706df-104">ER Använd dokumenthanteringsfiler i formatutmatningar (Del 1 - Förbered datamodellen)</span><span class="sxs-lookup"><span data-stu-id="706df-104">ER Use Document Management files in format outputs (Part 1 - Prepare data model)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="706df-105">I följande steg beskrivs hur en användare som tilldelats en roll som systemadministratör eller utvecklare för elektronisk rapportering kan konfigurera ett format för elektronisk rapportering (ER) för att använda dokumenthanteringsfiler (bilagor) i ER-utmatningar.</span><span class="sxs-lookup"><span data-stu-id="706df-105">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to use Document Management files (attachments) in ER output.</span></span> <span data-ttu-id="706df-106">Dessa steg kan utföras på valfritt företag.</span><span class="sxs-lookup"><span data-stu-id="706df-106">These steps can be performed in any company.</span></span>

<span data-ttu-id="706df-107">För att slutföra dessa steg måste du först slutföra stegen i proceduren "Create a configuration provider and mark it as active”.</span><span class="sxs-lookup"><span data-stu-id="706df-107">To complete these steps, you must first complete the steps in the "Create a configuration provider and mark it as active" procedure.</span></span>

<span data-ttu-id="706df-108">Denna procedur är avsedd för en funktion som lades till i Dynamics 365 for Operations version 1611.</span><span class="sxs-lookup"><span data-stu-id="706df-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="get-access-to-the-list-of-configurations-provided-by-microsoft"></a><span data-ttu-id="706df-109">Få åtkomst till listan med konfigurationer som tillhandahålls av Microsoft</span><span class="sxs-lookup"><span data-stu-id="706df-109">Get access to the list of configurations provided by Microsoft</span></span>
1. <span data-ttu-id="706df-110">Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="706df-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>

    <span data-ttu-id="706df-111">Kontrollera att ”Litware Inc."-leverantören</span><span class="sxs-lookup"><span data-stu-id="706df-111">Make sure that the 'Litware, Inc.'</span></span> <span data-ttu-id="706df-112">är tillgänglig och markerats som aktiv.</span><span class="sxs-lookup"><span data-stu-id="706df-112">provider is available and marked as active.</span></span>  

2. <span data-ttu-id="706df-113">Välj Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="706df-113">Select the 'Litware, Inc.'</span></span> <span data-ttu-id="706df-114">leverantör.</span><span class="sxs-lookup"><span data-stu-id="706df-114">provider.</span></span>
3. <span data-ttu-id="706df-115">Klicka på Databaser.</span><span class="sxs-lookup"><span data-stu-id="706df-115">Click Repositories.</span></span>

    <span data-ttu-id="706df-116">Om en databas av typen "Operations resources" redan finns, hoppa då över återstående steg för den aktuella underuppgiften.</span><span class="sxs-lookup"><span data-stu-id="706df-116">If a repository of the 'Operations resources' type already exists, skip the remaining steps of the current sub-task.</span></span>  

4. <span data-ttu-id="706df-117">Klicka på Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="706df-117">Click Add to open the drop dialog.</span></span>
5. <span data-ttu-id="706df-118">Ange "Operations resources" i fältet Configuration repository type.</span><span class="sxs-lookup"><span data-stu-id="706df-118">In the Configuration repository type field, enter 'Operations resources'.</span></span>
6. <span data-ttu-id="706df-119">Klicka på Skapa en databas.</span><span class="sxs-lookup"><span data-stu-id="706df-119">Click Create repository.</span></span>
7. <span data-ttu-id="706df-120">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="706df-120">Click OK.</span></span>

## <a name="get-the-customer-invoice-model-configurations-provided-by-microsoft"></a><span data-ttu-id="706df-121">Skaffa modellkonfigurationerna för kundfakturor som tillhandahålls av Microsoft</span><span class="sxs-lookup"><span data-stu-id="706df-121">Get the Customer invoice model configurations provided by Microsoft</span></span>
1. <span data-ttu-id="706df-122">Klicka på Visa filter.</span><span class="sxs-lookup"><span data-stu-id="706df-122">Click Show filters.</span></span>
2. <span data-ttu-id="706df-123">Använd följande filter: Ange filtervärdet "Operations resources" på fältet "Name" med filteroperatorn "begins with"; ange filtervärdet "" på fältet "Description" med filteroperatorn "begins with".</span><span class="sxs-lookup"><span data-stu-id="706df-123">Apply the following filters: Enter a filter value of "Operations resources" on the "Name" field using the "begins with" filter operator; Enter a filter value of "" on the "Description" field using the "begins with" filter operator</span></span>
3. <span data-ttu-id="706df-124">Klicka på Visa filter.</span><span class="sxs-lookup"><span data-stu-id="706df-124">Click Show filters.</span></span>
4. <span data-ttu-id="706df-125">Klicka på Öppna.</span><span class="sxs-lookup"><span data-stu-id="706df-125">Click Open.</span></span>
5. <span data-ttu-id="706df-126">Välj "Customer invoice model" i trädet.</span><span class="sxs-lookup"><span data-stu-id="706df-126">In the tree, select 'Customer invoice model'.</span></span>

    <span data-ttu-id="706df-127">Välj modellkonfigurationen "Customer invoice model" för att importera den.</span><span class="sxs-lookup"><span data-stu-id="706df-127">Select the model configuration 'Customer invoice model' to import it.</span></span>  

6. <span data-ttu-id="706df-128">Klicka på Importera.</span><span class="sxs-lookup"><span data-stu-id="706df-128">Click Import.</span></span>

    <span data-ttu-id="706df-129">Klicka på Import for version 1 för den valda konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="706df-129">Click Import for version 1 of the selected configuration.</span></span>  

7. <span data-ttu-id="706df-130">Klicka på Ja.</span><span class="sxs-lookup"><span data-stu-id="706df-130">Click Yes.</span></span>
8. <span data-ttu-id="706df-131">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="706df-131">Close the page.</span></span>
9. <span data-ttu-id="706df-132">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="706df-132">Close the page.</span></span>
10. <span data-ttu-id="706df-133">Klicka på Reporting configurations.</span><span class="sxs-lookup"><span data-stu-id="706df-133">Click Reporting configurations.</span></span>
11. <span data-ttu-id="706df-134">Välj "Customer invoice model" i trädet.</span><span class="sxs-lookup"><span data-stu-id="706df-134">In the tree, select 'Customer invoice model'.</span></span>

## <a name="create-the-derived-model-to-support-access-to-the-document-management-files"></a><span data-ttu-id="706df-135">Skapa den härledda modellen så att denna stöder åtkomst till dokumenthanteringsfilerna.</span><span class="sxs-lookup"><span data-stu-id="706df-135">Create the derived model to support access to the Document Management files.</span></span>
<span data-ttu-id="706df-136">Du kan skapa en egen konfiguration av kundfakturamodellen baserat på den konfiguration som tillhandahålls av Microsoft.</span><span class="sxs-lookup"><span data-stu-id="706df-136">You will create our own configuration of the Customer invoice model deriving it from the configuration provided by Microsoft.</span></span> <span data-ttu-id="706df-137">Du använder den här konfigurationen för att implementera åtkomst till dokumenthanteringsfilerna och göra dem tillgängliga för elektroniska dokument som du skapar baserat på denna modell.</span><span class="sxs-lookup"><span data-stu-id="706df-137">You will use this configuration to implement access to the Document Management files and make them available for electronic documents that you will create based on this model.</span></span>  
1. <span data-ttu-id="706df-138">Klicka på Skapa konfiguration om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="706df-138">Click Create configuration to open the drop dialog.</span></span>
2. <span data-ttu-id="706df-139">Ange "Derive from Name: Customer invoice model, Microsoft" i fältet New.</span><span class="sxs-lookup"><span data-stu-id="706df-139">In the New field, enter 'Derive from Name: Customer invoice model, Microsoft'.</span></span>
3. <span data-ttu-id="706df-140">Ange "Customer invoice model (custom)" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="706df-140">In the Name field, type 'Customer invoice model (custom)'.</span></span>
4. <span data-ttu-id="706df-141">Klicka på Skapa konfiguration.</span><span class="sxs-lookup"><span data-stu-id="706df-141">Click Create configuration.</span></span>



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]