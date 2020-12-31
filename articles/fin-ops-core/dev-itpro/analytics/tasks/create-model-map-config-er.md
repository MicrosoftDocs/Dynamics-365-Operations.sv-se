---
title: Skapa modellmappningskonfigurationer för elektronisk rapportering (ER)
description: Använd den här proceduren för att skapa en ny elektronisk rapportering (ER)-modellmappningskonfiguration och använda inbyggda funktioner för ER för effektiv aggregerade beräkningar.
author: NickSelin
manager: AnnBe
ms.date: 12/12/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 23bc3a525be9f65b7e5100114d02f6b79a286fb5
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2020
ms.locfileid: "4682079"
---
# <a name="create-electronic-reporting-er-model-mapping-configurations"></a><span data-ttu-id="86fec-103">Skapa modellmappningskonfigurationer för elektronisk rapportering (ER)</span><span class="sxs-lookup"><span data-stu-id="86fec-103">Create Electronic reporting (ER) model mapping configurations</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="86fec-104">Använd den här proceduren för att skapa en ny elektronisk rapportering (ER)-modellmappningskonfiguration och använda inbyggda funktioner för ER för effektiv aggregerade beräkningar.</span><span class="sxs-lookup"><span data-stu-id="86fec-104">Use this procedure to design a new Electronic reporting (ER) model mapping configuration and use built-in ER functions for efficient aggregate calculations.</span></span> <span data-ttu-id="86fec-105">I det här exemplet ska du skapa en konfiguration för exempelföretaget, Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="86fec-105">In this procedure, you will create a configuration for sample company, Litware, Inc.</span></span> 

<span data-ttu-id="86fec-106">Den här proceduren har skapats för användare med rollen Systemadministratör eller Utvecklare för elektronisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="86fec-106">This procedure is created for uses with the assigned role of System administrator or Electronic reporting developer.</span></span>

<span data-ttu-id="86fec-107">Stegen kan utföras med hjälp av valfri datauppsättning.</span><span class="sxs-lookup"><span data-stu-id="86fec-107">These steps can be completed using any dataset.</span></span> <span data-ttu-id="86fec-108">För att slutföra dessa steg måste du först slutföra stegen i proceduren "Skapa en konfigurationsleverantör och välj den som aktiv”.</span><span class="sxs-lookup"><span data-stu-id="86fec-108">To complete these steps, you must first complete the steps in the procedure, "Create a configuration provider and mark it as active."</span></span>

1. <span data-ttu-id="86fec-109">Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="86fec-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="86fec-110">Kontrollera att konfigurationsleverantören för exempelföretaget "Litware, Inc." är markerad som aktiv och är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="86fec-110">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as Active.</span></span> <span data-ttu-id="86fec-111">Om du inte ser den här konfigurationsleverantören ska du först slutföra stegen i proceduren Skapa en konfigurationsleverantör och välj den som aktiv.</span><span class="sxs-lookup"><span data-stu-id="86fec-111">If you don't see this configuration provider, complete the steps in the procedure, "Create a configuration provider and mark it as active".</span></span>  
2. <span data-ttu-id="86fec-112">Klicka på Reporting configurations.</span><span class="sxs-lookup"><span data-stu-id="86fec-112">Click Reporting configurations.</span></span>
3. <span data-ttu-id="86fec-113">Klicka på Visa filter.</span><span class="sxs-lookup"><span data-stu-id="86fec-113">Click Show filters.</span></span>
4. <span data-ttu-id="86fec-114">I fältet "Namn" anger du filtervärdet, "Intrastat" och använder filteroperatören "börjar med".</span><span class="sxs-lookup"><span data-stu-id="86fec-114">In the "Name" field, enter the filter value, "Intrastat" and use the filter operator "begins with".</span></span>
    * <span data-ttu-id="86fec-115">Tillämpa det här filtret om du vill hitta datamodellkonfigurationen ”Intrastat”.</span><span class="sxs-lookup"><span data-stu-id="86fec-115">Apply this filter to find the 'Intrastat' data model configuration.</span></span> <span data-ttu-id="86fec-116">Den här modellen finns redan i konfigurationsträdet.</span><span class="sxs-lookup"><span data-stu-id="86fec-116">This model may already exist in the configurations tree.</span></span> <span data-ttu-id="86fec-117">Om så är fallet kan du hoppa över nästa underaktivitet.</span><span class="sxs-lookup"><span data-stu-id="86fec-117">If it does, skip the next sub-task.</span></span>   

## <a name="get-the-intrastat-model-configuration-provided-by-microsoft"></a><span data-ttu-id="86fec-118">Hämta Intrastat-modellkonfigurationerna som tillhandahålls av Microsoft</span><span class="sxs-lookup"><span data-stu-id="86fec-118">Get the Intrastat model configuration provided by Microsoft</span></span>
1. <span data-ttu-id="86fec-119">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="86fec-119">Close the page.</span></span>
2. <span data-ttu-id="86fec-120">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="86fec-120">Close the page.</span></span>
3. <span data-ttu-id="86fec-121">Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="86fec-121">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
4. <span data-ttu-id="86fec-122">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="86fec-122">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="86fec-123">Välj panelen Microsoft provider.</span><span class="sxs-lookup"><span data-stu-id="86fec-123">Select the Microsoft provider tile.</span></span>  
5. <span data-ttu-id="86fec-124">Klicka på Databaser.</span><span class="sxs-lookup"><span data-stu-id="86fec-124">Click Repositories.</span></span>
    * <span data-ttu-id="86fec-125">Klicka på Databaser i panelen Microsoft-leverantör.</span><span class="sxs-lookup"><span data-stu-id="86fec-125">Click Repositories in the Microsoft provider tile.</span></span>  
6. <span data-ttu-id="86fec-126">Klicka på Visa filter.</span><span class="sxs-lookup"><span data-stu-id="86fec-126">Click Show filters.</span></span>
7. <span data-ttu-id="86fec-127">I fältet "Typnamn" anger du filtervärdet, "resurser" och använder filteroperatören "innehåller".</span><span class="sxs-lookup"><span data-stu-id="86fec-127">In the "Type name" field, enter the filter value, "resources" and use the filter operator "contains".</span></span> 
8. <span data-ttu-id="86fec-128">Klicka på Öppna.</span><span class="sxs-lookup"><span data-stu-id="86fec-128">Click Open.</span></span>
9. <span data-ttu-id="86fec-129">Välj "Intrastat-modell" i trädet.</span><span class="sxs-lookup"><span data-stu-id="86fec-129">In the tree, select 'Intrastat model'.</span></span>
10. <span data-ttu-id="86fec-130">Klicka på Importera.</span><span class="sxs-lookup"><span data-stu-id="86fec-130">Click Import.</span></span>
11. <span data-ttu-id="86fec-131">Klicka på Ja.</span><span class="sxs-lookup"><span data-stu-id="86fec-131">Click Yes.</span></span>
    * <span data-ttu-id="86fec-132">Du har importerat ER-modellkonfigurationen med datamodellen som ska användas för att undersöka hur de nya funktionerna för ER kan användas.</span><span class="sxs-lookup"><span data-stu-id="86fec-132">You imported the ER model configuration that contains the data model that you will use to explore how the new ER functionality can be used.</span></span>  
12. <span data-ttu-id="86fec-133">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="86fec-133">Close the page.</span></span>
13. <span data-ttu-id="86fec-134">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="86fec-134">Close the page.</span></span>
14. <span data-ttu-id="86fec-135">Klicka på Reporting configurations.</span><span class="sxs-lookup"><span data-stu-id="86fec-135">Click Reporting configurations.</span></span>

## <a name="add-a-new-model-mapping-configuration"></a><span data-ttu-id="86fec-136">Lägg till en ny konfiguration för modellmappning</span><span class="sxs-lookup"><span data-stu-id="86fec-136">Add a new model mapping configuration</span></span>
1. <span data-ttu-id="86fec-137">Välj "Intrastat-modell" i trädet.</span><span class="sxs-lookup"><span data-stu-id="86fec-137">In the tree, select 'Intrastat model'.</span></span>
2. <span data-ttu-id="86fec-138">Klicka på Skapa konfiguration om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="86fec-138">Click Create configuration to open the drop dialog.</span></span>
3. <span data-ttu-id="86fec-139">I fältet Nytt anger du "Modellmappning baserat på datamodell Intrastat".</span><span class="sxs-lookup"><span data-stu-id="86fec-139">In the New field, enter 'Model Mapping based on data model Intrastat'.</span></span>
4. <span data-ttu-id="86fec-140">I fältet Namn skriver du "Intrastat-exempelmappning".</span><span class="sxs-lookup"><span data-stu-id="86fec-140">In the Name field, type 'Intrastat sample mapping'.</span></span>
    * <span data-ttu-id="86fec-141">Intrastat-exempelmappning</span><span class="sxs-lookup"><span data-stu-id="86fec-141">Intrastat sample mapping</span></span>  
5. <span data-ttu-id="86fec-142">Klicka på Skapa konfiguration.</span><span class="sxs-lookup"><span data-stu-id="86fec-142">Click Create configuration.</span></span>

