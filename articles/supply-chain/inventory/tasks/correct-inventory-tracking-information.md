---
title: Korrekt information om lagerspårning
description: Den här proceduren går igenom processen med att skapa och bokföra en lageröverföringsjournal för att korrigera information om lagerspårning.
author: MarkusFogelberg
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalTransfer, InventJournalCreate, InventItemIdLookupSimple, InventBatchIdLookup, InventLocationIdLookup, InventDimTracking, InventTrans
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a8a488d4c30923445b3ebc2626a79b8fa45012c7
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437936"
---
# <a name="correct-inventory-tracking-information"></a><span data-ttu-id="81194-103">Korrekt information om lagerspårning</span><span class="sxs-lookup"><span data-stu-id="81194-103">Correct inventory tracking information</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="81194-104">Den här proceduren går igenom processen med att skapa och bokföra en lageröverföringsjournal för att korrigera information om lagerspårning.</span><span class="sxs-lookup"><span data-stu-id="81194-104">This procedure walks you through the process of creating and posting an inventory transfer journal in order to correct inventory tracking information.</span></span> <span data-ttu-id="81194-105">I det här exemplet ska du uppdatera informationen för en batchkontrollerad artikel genom att ändra en felaktigt bokförd batch till en annan batch.</span><span class="sxs-lookup"><span data-stu-id="81194-105">In this example, we'll update the information of a batch controlled item by changing an incorrectly registered batch to another batch.</span></span> <span data-ttu-id="81194-106">Du kan gå igenom den här proceduren i demonstrationsdataföretaget USPI eller använda dina egna data.</span><span class="sxs-lookup"><span data-stu-id="81194-106">You can walk through this procedure in demo data company USPI, or using your own data.</span></span> <span data-ttu-id="81194-107">Om du använder dina egna data måste du ha en artikel som är batchaktiverad och den få inte vara platskontrollerad.</span><span class="sxs-lookup"><span data-stu-id="81194-107">If you use your own data, you need to have an item that's batch-enabled, and it must not be location-controlled.</span></span> <span data-ttu-id="81194-108">Du måste även ha ett lagerjournalnamn inställt för lageröverföringar.</span><span class="sxs-lookup"><span data-stu-id="81194-108">You also need to have an inventory journal name set up for inventory transfers.</span></span> <span data-ttu-id="81194-109">Dessa uppgifter utförs vanligtvis av en lagerarbetare.</span><span class="sxs-lookup"><span data-stu-id="81194-109">These tasks would normally be carried out by a warehouse employee.</span></span>


## <a name="create-an-inventory-transfer-journal"></a><span data-ttu-id="81194-110">Skapa en lageröverföringsjournal</span><span class="sxs-lookup"><span data-stu-id="81194-110">Create an inventory transfer journal</span></span>
1. <span data-ttu-id="81194-111">Gå till Överför.</span><span class="sxs-lookup"><span data-stu-id="81194-111">Go to Transfer.</span></span>
2. <span data-ttu-id="81194-112">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="81194-112">Click New.</span></span>
3. <span data-ttu-id="81194-113">Ange eller välj ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="81194-113">In the Name field, enter or select a value.</span></span>
4. <span data-ttu-id="81194-114">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="81194-114">Click OK.</span></span>

## <a name="create-journal-lines"></a><span data-ttu-id="81194-115">Skapa journalrader</span><span class="sxs-lookup"><span data-stu-id="81194-115">Create journal lines</span></span>
1. <span data-ttu-id="81194-116">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="81194-116">Click New.</span></span>
2. <span data-ttu-id="81194-117">Ange eller välj ett värde i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="81194-117">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="81194-118">Om du använder USPI kan du välja artikeln M5003.</span><span class="sxs-lookup"><span data-stu-id="81194-118">If you are using USPI, select item M5003.</span></span>  
3. <span data-ttu-id="81194-119">Ange ett tal i fältet Kvantitet.</span><span class="sxs-lookup"><span data-stu-id="81194-119">In the Quantity field, enter a number.</span></span>
4. <span data-ttu-id="81194-120">Klicka på fliken Lagerdimensioner.</span><span class="sxs-lookup"><span data-stu-id="81194-120">Click the Inventory dimensions tab.</span></span>
5. <span data-ttu-id="81194-121">I fältet Batchnummer, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="81194-121">In the Batch number field, enter or select a value.</span></span>
6. <span data-ttu-id="81194-122">Ange eller välj ett värde i fältet Plats.</span><span class="sxs-lookup"><span data-stu-id="81194-122">In the Site field, enter or select a value.</span></span>
7. <span data-ttu-id="81194-123">Ange eller välj ett värde i fältet Lagerställe.</span><span class="sxs-lookup"><span data-stu-id="81194-123">In the Warehouse field, enter or select a value.</span></span>
8. <span data-ttu-id="81194-124">I fältet Batchnummer, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="81194-124">In the Batch number field, enter or select a value.</span></span>

## <a name="post-the-journal"></a><span data-ttu-id="81194-125">Bokför journalen</span><span class="sxs-lookup"><span data-stu-id="81194-125">Post the journal</span></span>
1. <span data-ttu-id="81194-126">Klicka på Bokför.</span><span class="sxs-lookup"><span data-stu-id="81194-126">Click Post.</span></span>
2. <span data-ttu-id="81194-127">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="81194-127">Click OK.</span></span>

## <a name="check-tracing-information"></a><span data-ttu-id="81194-128">Kontrollera spårningsinformation</span><span class="sxs-lookup"><span data-stu-id="81194-128">Check tracing information</span></span>
1. <span data-ttu-id="81194-129">Klicka på Lager.</span><span class="sxs-lookup"><span data-stu-id="81194-129">Click Inventory.</span></span>
2. <span data-ttu-id="81194-130">Klicka på Spåra.</span><span class="sxs-lookup"><span data-stu-id="81194-130">Click Trace.</span></span>
3. <span data-ttu-id="81194-131">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="81194-131">Click OK.</span></span>
    * <span data-ttu-id="81194-132">Med denna information om spårning kan du bakåtspåra den batch du korrigeraden lagret från.</span><span class="sxs-lookup"><span data-stu-id="81194-132">Using this tracing information you can back trace which batch you corrected inventory from.</span></span>  <span data-ttu-id="81194-133">Du kan också använda artikelspårningssidan om du vill se den här informationen.</span><span class="sxs-lookup"><span data-stu-id="81194-133">You can also use the Item tracing page to see this information.</span></span>  
4. <span data-ttu-id="81194-134">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="81194-134">Close the page.</span></span>

## <a name="check-inventory-transactions"></a><span data-ttu-id="81194-135">Kontrollera lagertransaktioner</span><span class="sxs-lookup"><span data-stu-id="81194-135">Check inventory transactions</span></span>
1. <span data-ttu-id="81194-136">Klicka på Lager.</span><span class="sxs-lookup"><span data-stu-id="81194-136">Click Inventory.</span></span>
2. <span data-ttu-id="81194-137">Klicka på Transaktioner.</span><span class="sxs-lookup"><span data-stu-id="81194-137">Click Transactions.</span></span>
    * <span data-ttu-id="81194-138">Här kan du se de transaktioner som skapades när du bokförde din journal.</span><span class="sxs-lookup"><span data-stu-id="81194-138">Here you can see the transactions that were created when you posted your journal.</span></span>   

