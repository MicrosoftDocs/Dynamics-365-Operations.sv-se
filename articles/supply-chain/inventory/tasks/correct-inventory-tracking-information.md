---
title: "Korrekt information om lagerspårning"
description: "Den här proceduren går igenom processen med att skapa och bokföra en lageröverföringsjournal för att korrigera information om lagerspårning."
author: MarkusFogelberg
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 55f9ae337aac673ae2f80d7bfa9221b6060f9119
ms.contentlocale: sv-se
ms.lasthandoff: 05/08/2018

---
# <a name="correct-inventory-tracking-information"></a><span data-ttu-id="84020-103">Korrekt information om lagerspårning</span><span class="sxs-lookup"><span data-stu-id="84020-103">Correct inventory tracking information</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="84020-104">Den här proceduren går igenom processen med att skapa och bokföra en lageröverföringsjournal för att korrigera information om lagerspårning.</span><span class="sxs-lookup"><span data-stu-id="84020-104">This procedure walks you through the process of creating and posting an inventory transfer journal in order to correct inventory tracking information.</span></span> <span data-ttu-id="84020-105">I det här exemplet ska du uppdatera informationen för en batchkontrollerad artikel genom att ändra en felaktigt bokförd batch till en annan batch.</span><span class="sxs-lookup"><span data-stu-id="84020-105">In this example, we’ll update the information of a batch controlled item by changing an incorrectly registered batch to another batch.</span></span> <span data-ttu-id="84020-106">Du kan gå igenom den här proceduren i demonstrationsdataföretaget USPI eller använda dina egna data.</span><span class="sxs-lookup"><span data-stu-id="84020-106">You can walk through this procedure in demo data company USPI, or using your own data.</span></span> <span data-ttu-id="84020-107">Om du använder dina egna data måste du ha en artikel som är batchaktiverad och den få inte vara platskontrollerad.</span><span class="sxs-lookup"><span data-stu-id="84020-107">If you use your own data, you need to have an item that’s batch-enabled, and it must not be location-controlled.</span></span> <span data-ttu-id="84020-108">Du måste även ha ett lagerjournalnamn inställt för lageröverföringar.</span><span class="sxs-lookup"><span data-stu-id="84020-108">You also need to have an inventory journal name set up for inventory transfers.</span></span> <span data-ttu-id="84020-109">Dessa uppgifter utförs vanligtvis av en lagerarbetare.</span><span class="sxs-lookup"><span data-stu-id="84020-109">These tasks would normally be carried out by a warehouse employee.</span></span>


## <a name="create-an-inventory-transfer-journal"></a><span data-ttu-id="84020-110">Skapa en lageröverföringsjournal</span><span class="sxs-lookup"><span data-stu-id="84020-110">Create an inventory transfer journal</span></span>
1. <span data-ttu-id="84020-111">Gå till Överför.</span><span class="sxs-lookup"><span data-stu-id="84020-111">Go to Transfer.</span></span>
2. <span data-ttu-id="84020-112">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="84020-112">Click New.</span></span>
3. <span data-ttu-id="84020-113">Ange eller välj ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="84020-113">In the Name field, enter or select a value.</span></span>
4. <span data-ttu-id="84020-114">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="84020-114">Click OK.</span></span>

## <a name="create-journal-lines"></a><span data-ttu-id="84020-115">Skapa journalrader</span><span class="sxs-lookup"><span data-stu-id="84020-115">Create journal lines</span></span>
1. <span data-ttu-id="84020-116">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="84020-116">Click New.</span></span>
2. <span data-ttu-id="84020-117">Ange eller välj ett värde i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="84020-117">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="84020-118">Om du använder USPI kan du välja artikeln M5003.</span><span class="sxs-lookup"><span data-stu-id="84020-118">If you are using USPI, select item M5003.</span></span>  
3. <span data-ttu-id="84020-119">Ange ett tal i fältet Kvantitet.</span><span class="sxs-lookup"><span data-stu-id="84020-119">In the Quantity field, enter a number.</span></span>
4. <span data-ttu-id="84020-120">Klicka på fliken Lagerdimensioner.</span><span class="sxs-lookup"><span data-stu-id="84020-120">Click the Inventory dimensions tab.</span></span>
5. <span data-ttu-id="84020-121">I fältet Batchnummer, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="84020-121">In the Batch number field, enter or select a value.</span></span>
6. <span data-ttu-id="84020-122">Ange eller välj ett värde i fältet Plats.</span><span class="sxs-lookup"><span data-stu-id="84020-122">In the Site field, enter or select a value.</span></span>
7. <span data-ttu-id="84020-123">Ange eller välj ett värde i fältet Lagerställe.</span><span class="sxs-lookup"><span data-stu-id="84020-123">In the Warehouse field, enter or select a value.</span></span>
8. <span data-ttu-id="84020-124">I fältet Batchnummer, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="84020-124">In the Batch number field, enter or select a value.</span></span>

## <a name="post-the-journal"></a><span data-ttu-id="84020-125">Bokför journalen</span><span class="sxs-lookup"><span data-stu-id="84020-125">Post the journal</span></span>
1. <span data-ttu-id="84020-126">Klicka på Bokför.</span><span class="sxs-lookup"><span data-stu-id="84020-126">Click Post.</span></span>
2. <span data-ttu-id="84020-127">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="84020-127">Click OK.</span></span>

## <a name="check-tracing-information"></a><span data-ttu-id="84020-128">Kontrollera spårningsinformation</span><span class="sxs-lookup"><span data-stu-id="84020-128">Check tracing information</span></span>
1. <span data-ttu-id="84020-129">Klicka på Lager.</span><span class="sxs-lookup"><span data-stu-id="84020-129">Click Inventory.</span></span>
2. <span data-ttu-id="84020-130">Klicka på Spåra.</span><span class="sxs-lookup"><span data-stu-id="84020-130">Click Trace.</span></span>
3. <span data-ttu-id="84020-131">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="84020-131">Click OK.</span></span>
    * <span data-ttu-id="84020-132">Med denna information om spårning kan du bakåtspåra den batch du korrigeraden lagret från.</span><span class="sxs-lookup"><span data-stu-id="84020-132">Using this tracing information you can back trace which batch you corrected inventory from.</span></span>  <span data-ttu-id="84020-133">Du kan också använda artikelspårningssidan om du vill se den här informationen.</span><span class="sxs-lookup"><span data-stu-id="84020-133">You can also use the Item tracing page to see this information.</span></span>  
4. <span data-ttu-id="84020-134">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="84020-134">Close the page.</span></span>

## <a name="check-inventory-transactions"></a><span data-ttu-id="84020-135">Kontrollera lagertransaktioner</span><span class="sxs-lookup"><span data-stu-id="84020-135">Check inventory transactions</span></span>
1. <span data-ttu-id="84020-136">Klicka på Lager.</span><span class="sxs-lookup"><span data-stu-id="84020-136">Click Inventory.</span></span>
2. <span data-ttu-id="84020-137">Klicka på Transaktioner.</span><span class="sxs-lookup"><span data-stu-id="84020-137">Click Transactions.</span></span>
    * <span data-ttu-id="84020-138">Här kan du se de transaktioner som skapades när du bokförde din journal.</span><span class="sxs-lookup"><span data-stu-id="84020-138">Here you can see the transactions that were created when you posted your journal.</span></span>   

