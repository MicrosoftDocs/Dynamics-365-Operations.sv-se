---
title: Inventering i ett lagerställe
description: I den här proceduren beskrivs hur du kan skapa och bokföra en lagerinventeringsjournal för att kunna räkna en viss artikel på en plats på lagerstället.
author: MarkusFogelberg
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalCount, InventJournalCreate, HcmWorkerLookUp, InventItemIdLookupSimple, InventLocationIdLookup, WMSLocationIdLookup, InventTrans
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8c0bbfe8f86d27f81b0d577ed89dfa34ebcf3f18
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1549929"
---
# <a name="count-inventory-in-a-warehouse"></a><span data-ttu-id="76a1e-103">Inventering i ett lagerställe</span><span class="sxs-lookup"><span data-stu-id="76a1e-103">Count inventory in a warehouse</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="76a1e-104">I den här proceduren beskrivs hur du kan skapa och bokföra en lagerinventeringsjournal för att kunna räkna en viss artikel på en plats på lagerstället.</span><span class="sxs-lookup"><span data-stu-id="76a1e-104">This procedure walks you through the process of creating and posting an inventory counting journal in order to count a specific item at a location in the warehouse.</span></span> <span data-ttu-id="76a1e-105">Proceduren gäller grundläggande lagerstyrningsfunktioner som är tillgängliga i lagerhanteringmodulen, inte de lagerfunktioner som finns i lagerstyrningsmodulen.</span><span class="sxs-lookup"><span data-stu-id="76a1e-105">The procedure applies to “basic warehousing” functionality, available in the Inventory management module, not to the warehousing functionality that’s available in the Warehouse management module.</span></span> <span data-ttu-id="76a1e-106">Du kan gå igenom den här proceduren i demonstrationsdataföretaget USMF eller använda dina egna data.</span><span class="sxs-lookup"><span data-stu-id="76a1e-106">You can walk through this procedure in demo data company USMF, or using your own data.</span></span> <span data-ttu-id="76a1e-107">Om du använder dina egna data, kontrollera att du har konfigurerat produkter och platser och att du har skapat ett lagerjournalnamn för inventeringsjournaler.</span><span class="sxs-lookup"><span data-stu-id="76a1e-107">If you’re using your own data, make sure that you have products and locations set up, and that you’ve created an inventory journal name for counting journals.</span></span> <span data-ttu-id="76a1e-108">Lagerinventering utförs normalt av en lagerarbetare.</span><span class="sxs-lookup"><span data-stu-id="76a1e-108">Inventory counting is normally carried out by a warehouse employee.</span></span>


## <a name="create-an-inventory-counting-journal"></a><span data-ttu-id="76a1e-109">Skapa en lagerinventeringsjournal</span><span class="sxs-lookup"><span data-stu-id="76a1e-109">Create an inventory counting journal</span></span>
1. <span data-ttu-id="76a1e-110">Gå till Lagerhantering > Journalposter > Artikelräkning > Inventering.</span><span class="sxs-lookup"><span data-stu-id="76a1e-110">Go to Inventory management > Journal entries > Item counting > Counting.</span></span>
2. <span data-ttu-id="76a1e-111">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="76a1e-111">Click New.</span></span>
3. <span data-ttu-id="76a1e-112">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="76a1e-112">In the Name field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="76a1e-113">Klicka på lagerinventeringsjournalnamnet som du vill använda i listan</span><span class="sxs-lookup"><span data-stu-id="76a1e-113">In the list, click on the inventory counting journal name you want to use</span></span>
    * <span data-ttu-id="76a1e-114">Vissa fält kommer att fyllas i baserat på inställningarna för journalnamnet för lagerinventering som du väljer.</span><span class="sxs-lookup"><span data-stu-id="76a1e-114">Some other fields will be populated based on the setup of the inventory counting journal name that you select.</span></span>  
5. <span data-ttu-id="76a1e-115">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Arbetare.</span><span class="sxs-lookup"><span data-stu-id="76a1e-115">In the Worker field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="76a1e-116">Välj den arbetare som du vill ha i listan.</span><span class="sxs-lookup"><span data-stu-id="76a1e-116">In the list, select the worker you want to use.</span></span>
7. <span data-ttu-id="76a1e-117">Klicka på Välj.</span><span class="sxs-lookup"><span data-stu-id="76a1e-117">Click Select.</span></span>
8. <span data-ttu-id="76a1e-118">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="76a1e-118">Click OK.</span></span>

## <a name="create-journal-lines"></a><span data-ttu-id="76a1e-119">Skapa journalrader</span><span class="sxs-lookup"><span data-stu-id="76a1e-119">Create journal lines</span></span>
1. <span data-ttu-id="76a1e-120">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="76a1e-120">Click New.</span></span>
2. <span data-ttu-id="76a1e-121">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="76a1e-121">In the Item number field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="76a1e-122">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="76a1e-122">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="76a1e-123">Om du använder demonstrationsföretaget USMF kan du välja A0001.</span><span class="sxs-lookup"><span data-stu-id="76a1e-123">If you are using demo data company USMF, select 'A0001'.</span></span>  
4. <span data-ttu-id="76a1e-124">Öppna sökningen genom att klicka på listruteknappen i fältet Plats.</span><span class="sxs-lookup"><span data-stu-id="76a1e-124">In the Site field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="76a1e-125">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="76a1e-125">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="76a1e-126">Om du använder demonstrationsföretaget USMF kan du välja site 2.</span><span class="sxs-lookup"><span data-stu-id="76a1e-126">If you are using demo data company USMF, select site '2'.</span></span>  
6. <span data-ttu-id="76a1e-127">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Lagerställe.</span><span class="sxs-lookup"><span data-stu-id="76a1e-127">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="76a1e-128">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="76a1e-128">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="76a1e-129">Om du använder demonstrationsföretaget USMF kan du välja lagerställe 24.</span><span class="sxs-lookup"><span data-stu-id="76a1e-129">If you are using demo data company USMF, select warehouse '24'.</span></span>  
8. <span data-ttu-id="76a1e-130">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Plats.</span><span class="sxs-lookup"><span data-stu-id="76a1e-130">In the Location field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="76a1e-131">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="76a1e-131">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="76a1e-132">Om du använder demonstrationsföretaget USMF kan du välja platsen BULK-001.</span><span class="sxs-lookup"><span data-stu-id="76a1e-132">If you are using demo data company USMF, select location 'BULK-001'</span></span>  
10. <span data-ttu-id="76a1e-133">Ange ett värde i fältet Räknat.</span><span class="sxs-lookup"><span data-stu-id="76a1e-133">In the Counted field, enter a number.</span></span>
    * <span data-ttu-id="76a1e-134">Om du anger ett nummer som skiljer sig till antalet i fältet I lager, uppdateras fältet Kvantitet med diskrepansen.</span><span class="sxs-lookup"><span data-stu-id="76a1e-134">If you enter a counted number that’s different to the number shown in the On-hand field, the Quantity field is updated to show the discrepancy.</span></span>  
11. <span data-ttu-id="76a1e-135">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="76a1e-135">Click Save.</span></span>

## <a name="post-the-inventory-counting-journal"></a><span data-ttu-id="76a1e-136">Bokför lagerinventeringsjournalen</span><span class="sxs-lookup"><span data-stu-id="76a1e-136">Post the inventory counting journal</span></span>
1. <span data-ttu-id="76a1e-137">Klicka på Bokför.</span><span class="sxs-lookup"><span data-stu-id="76a1e-137">Click Post.</span></span>
    * <span data-ttu-id="76a1e-138">När du bokför en lagerinventeringsjournal och om det räknade antalet skiljer sig från antalet som rapporteras i fältet I lager där en lagerinleverans eller ett lageruttag bokförs, ändras lagernivån och värdet och redovisningstransaktioner genereras.</span><span class="sxs-lookup"><span data-stu-id="76a1e-138">When you post an inventory counting journal, if the counted amount differs from amount that’s reported in the On-hand field an inventory receipt or issue is posted, the inventory level and value are changed, and ledger transactions are generated.</span></span>  
2. <span data-ttu-id="76a1e-139">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="76a1e-139">Click OK.</span></span>

## <a name="view-inventory-transactions"></a><span data-ttu-id="76a1e-140">Visa lagertransaktioner</span><span class="sxs-lookup"><span data-stu-id="76a1e-140">View inventory transactions</span></span>
1. <span data-ttu-id="76a1e-141">Klicka på Lager.</span><span class="sxs-lookup"><span data-stu-id="76a1e-141">Click Inventory.</span></span>
2. <span data-ttu-id="76a1e-142">Klicka på Transaktioner.</span><span class="sxs-lookup"><span data-stu-id="76a1e-142">Click Transactions.</span></span>
    * <span data-ttu-id="76a1e-143">Här kan du se alla relaterade transaktioner som skapas när du bokför en lagerinventeringsjournal.</span><span class="sxs-lookup"><span data-stu-id="76a1e-143">Here you can see any related transactions that will be created when you post your inventory counting journal.</span></span>   

