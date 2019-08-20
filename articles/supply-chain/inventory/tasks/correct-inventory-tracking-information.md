---
title: Korrekt information om lagerspårning
description: Den här proceduren går igenom processen med att skapa och bokföra en lageröverföringsjournal för att korrigera information om lagerspårning.
author: MarkusFogelberg
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalTransfer, InventJournalCreate, InventItemIdLookupSimple, InventBatchIdLookup, InventLocationIdLookup, InventDimTracking, InventTrans
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8269e5119e45522373eca6cb8fb06bfb94a37566
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2019
ms.locfileid: "1845580"
---
# <a name="correct-inventory-tracking-information"></a><span data-ttu-id="464e5-103">Korrekt information om lagerspårning</span><span class="sxs-lookup"><span data-stu-id="464e5-103">Correct inventory tracking information</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="464e5-104">Den här proceduren går igenom processen med att skapa och bokföra en lageröverföringsjournal för att korrigera information om lagerspårning.</span><span class="sxs-lookup"><span data-stu-id="464e5-104">This procedure walks you through the process of creating and posting an inventory transfer journal in order to correct inventory tracking information.</span></span> <span data-ttu-id="464e5-105">I det här exemplet ska du uppdatera informationen för en batchkontrollerad artikel genom att ändra en felaktigt bokförd batch till en annan batch.</span><span class="sxs-lookup"><span data-stu-id="464e5-105">In this example, we’ll update the information of a batch controlled item by changing an incorrectly registered batch to another batch.</span></span> <span data-ttu-id="464e5-106">Du kan gå igenom den här proceduren i demonstrationsdataföretaget USPI eller använda dina egna data.</span><span class="sxs-lookup"><span data-stu-id="464e5-106">You can walk through this procedure in demo data company USPI, or using your own data.</span></span> <span data-ttu-id="464e5-107">Om du använder dina egna data måste du ha en artikel som är batchaktiverad och den få inte vara platskontrollerad.</span><span class="sxs-lookup"><span data-stu-id="464e5-107">If you use your own data, you need to have an item that’s batch-enabled, and it must not be location-controlled.</span></span> <span data-ttu-id="464e5-108">Du måste även ha ett lagerjournalnamn inställt för lageröverföringar.</span><span class="sxs-lookup"><span data-stu-id="464e5-108">You also need to have an inventory journal name set up for inventory transfers.</span></span> <span data-ttu-id="464e5-109">Dessa uppgifter utförs vanligtvis av en lagerarbetare.</span><span class="sxs-lookup"><span data-stu-id="464e5-109">These tasks would normally be carried out by a warehouse employee.</span></span>


## <a name="create-an-inventory-transfer-journal"></a><span data-ttu-id="464e5-110">Skapa en lageröverföringsjournal</span><span class="sxs-lookup"><span data-stu-id="464e5-110">Create an inventory transfer journal</span></span>
1. <span data-ttu-id="464e5-111">Gå till Överför.</span><span class="sxs-lookup"><span data-stu-id="464e5-111">Go to Transfer.</span></span>
2. <span data-ttu-id="464e5-112">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="464e5-112">Click New.</span></span>
3. <span data-ttu-id="464e5-113">Ange eller välj ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="464e5-113">In the Name field, enter or select a value.</span></span>
4. <span data-ttu-id="464e5-114">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="464e5-114">Click OK.</span></span>

## <a name="create-journal-lines"></a><span data-ttu-id="464e5-115">Skapa journalrader</span><span class="sxs-lookup"><span data-stu-id="464e5-115">Create journal lines</span></span>
1. <span data-ttu-id="464e5-116">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="464e5-116">Click New.</span></span>
2. <span data-ttu-id="464e5-117">Ange eller välj ett värde i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="464e5-117">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="464e5-118">Om du använder USPI kan du välja artikeln M5003.</span><span class="sxs-lookup"><span data-stu-id="464e5-118">If you are using USPI, select item M5003.</span></span>  
3. <span data-ttu-id="464e5-119">Ange ett tal i fältet Kvantitet.</span><span class="sxs-lookup"><span data-stu-id="464e5-119">In the Quantity field, enter a number.</span></span>
4. <span data-ttu-id="464e5-120">Klicka på fliken Lagerdimensioner.</span><span class="sxs-lookup"><span data-stu-id="464e5-120">Click the Inventory dimensions tab.</span></span>
5. <span data-ttu-id="464e5-121">I fältet Batchnummer, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="464e5-121">In the Batch number field, enter or select a value.</span></span>
6. <span data-ttu-id="464e5-122">Ange eller välj ett värde i fältet Plats.</span><span class="sxs-lookup"><span data-stu-id="464e5-122">In the Site field, enter or select a value.</span></span>
7. <span data-ttu-id="464e5-123">Ange eller välj ett värde i fältet Lagerställe.</span><span class="sxs-lookup"><span data-stu-id="464e5-123">In the Warehouse field, enter or select a value.</span></span>
8. <span data-ttu-id="464e5-124">I fältet Batchnummer, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="464e5-124">In the Batch number field, enter or select a value.</span></span>

## <a name="post-the-journal"></a><span data-ttu-id="464e5-125">Bokför journalen</span><span class="sxs-lookup"><span data-stu-id="464e5-125">Post the journal</span></span>
1. <span data-ttu-id="464e5-126">Klicka på Bokför.</span><span class="sxs-lookup"><span data-stu-id="464e5-126">Click Post.</span></span>
2. <span data-ttu-id="464e5-127">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="464e5-127">Click OK.</span></span>

## <a name="check-tracing-information"></a><span data-ttu-id="464e5-128">Kontrollera spårningsinformation</span><span class="sxs-lookup"><span data-stu-id="464e5-128">Check tracing information</span></span>
1. <span data-ttu-id="464e5-129">Klicka på Lager.</span><span class="sxs-lookup"><span data-stu-id="464e5-129">Click Inventory.</span></span>
2. <span data-ttu-id="464e5-130">Klicka på Spåra.</span><span class="sxs-lookup"><span data-stu-id="464e5-130">Click Trace.</span></span>
3. <span data-ttu-id="464e5-131">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="464e5-131">Click OK.</span></span>
    * <span data-ttu-id="464e5-132">Med denna information om spårning kan du bakåtspåra den batch du korrigeraden lagret från.</span><span class="sxs-lookup"><span data-stu-id="464e5-132">Using this tracing information you can back trace which batch you corrected inventory from.</span></span>  <span data-ttu-id="464e5-133">Du kan också använda artikelspårningssidan om du vill se den här informationen.</span><span class="sxs-lookup"><span data-stu-id="464e5-133">You can also use the Item tracing page to see this information.</span></span>  
4. <span data-ttu-id="464e5-134">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="464e5-134">Close the page.</span></span>

## <a name="check-inventory-transactions"></a><span data-ttu-id="464e5-135">Kontrollera lagertransaktioner</span><span class="sxs-lookup"><span data-stu-id="464e5-135">Check inventory transactions</span></span>
1. <span data-ttu-id="464e5-136">Klicka på Lager.</span><span class="sxs-lookup"><span data-stu-id="464e5-136">Click Inventory.</span></span>
2. <span data-ttu-id="464e5-137">Klicka på Transaktioner.</span><span class="sxs-lookup"><span data-stu-id="464e5-137">Click Transactions.</span></span>
    * <span data-ttu-id="464e5-138">Här kan du se de transaktioner som skapades när du bokförde din journal.</span><span class="sxs-lookup"><span data-stu-id="464e5-138">Here you can see the transactions that were created when you posted your journal.</span></span>   

