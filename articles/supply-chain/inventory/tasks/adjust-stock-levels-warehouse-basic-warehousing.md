---
title: Justera lagernivåer i lagerstället (grundläggande lagerstyrning)
description: Den här proceduren beskriver hur du kan skapa och bokför en lagerjusteringsjournal för att justera lagernivåer för produkter på lagerstället.
author: MarkusFogelberg
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalLossProfit, InventJournalCreate, InventLocationIdLookup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 330ebacf4a036b2df6ca22728477cae5b347354d
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1550103"
---
# <a name="adjust-stock-levels-in-the-warehouse-basic-warehousing"></a><span data-ttu-id="5e512-103">Justera lagernivåer i lagerstället (grundläggande lagerstyrning)</span><span class="sxs-lookup"><span data-stu-id="5e512-103">Adjust stock levels in the warehouse (basic warehousing)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="5e512-104">Den här proceduren beskriver hur du kan skapa och bokför en lagerjusteringsjournal för att justera lagernivåer för produkter på lagerstället.</span><span class="sxs-lookup"><span data-stu-id="5e512-104">This procedure walks you through the process of creating and posting an inventory adjustment journal in order to adjust stock levels of products in the warehouse.</span></span> <span data-ttu-id="5e512-105">Du måste ha ett lagerjournalnamn konfigurerat för lagerjusteringarna innan du sätter igång.</span><span class="sxs-lookup"><span data-stu-id="5e512-105">You need to have an inventory journal name set up for inventory adjustments before you start this.</span></span> <span data-ttu-id="5e512-106">Du kan gå igenom den här proceduren i demonstrationsdataföretaget USMF eller använda dina egna data.</span><span class="sxs-lookup"><span data-stu-id="5e512-106">You can walk through this procedure in demo data company USMF, or using your own data.</span></span> <span data-ttu-id="5e512-107">Dessa uppgifter utförs vanligtvis av en lagerarbetare.</span><span class="sxs-lookup"><span data-stu-id="5e512-107">These tasks would normally be carried out by a warehouse employee.</span></span>


## <a name="create-an-inventory-adjustment-journal"></a><span data-ttu-id="5e512-108">Skapa en lagerjusteringsjournal</span><span class="sxs-lookup"><span data-stu-id="5e512-108">Create an inventory adjustment journal</span></span>
1. <span data-ttu-id="5e512-109">Gå till Lagerhantering > Journalposter > Artiklar > Lagerjustering.</span><span class="sxs-lookup"><span data-stu-id="5e512-109">Go to Inventory management > Journal entries > Items > Inventory adjustment.</span></span>
2. <span data-ttu-id="5e512-110">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="5e512-110">Click New.</span></span>
3. <span data-ttu-id="5e512-111">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="5e512-111">In the Name field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="5e512-112">Klicka på lagerjusteringsjournalnamnet som du vill använda i listan.</span><span class="sxs-lookup"><span data-stu-id="5e512-112">In the list, click on the inventory adjustment journal name you want to use.</span></span>
    * <span data-ttu-id="5e512-113">Vissa fält kommer att fyllas i baserat på inställningarna för journalnamnet för lagerjustering som du väljer.</span><span class="sxs-lookup"><span data-stu-id="5e512-113">Some other fields will be populated based on the setup of the inventory adjustment journal name you select.</span></span>  
5. <span data-ttu-id="5e512-114">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="5e512-114">Click OK.</span></span>

## <a name="create-journal-lines"></a><span data-ttu-id="5e512-115">Skapa journalrader</span><span class="sxs-lookup"><span data-stu-id="5e512-115">Create journal lines</span></span>
1. <span data-ttu-id="5e512-116">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="5e512-116">Click New.</span></span>
2. <span data-ttu-id="5e512-117">Markera fältet för artikelnummer i listan.</span><span class="sxs-lookup"><span data-stu-id="5e512-117">In the list, mark the item number field.</span></span>
3. <span data-ttu-id="5e512-118">Välj en artikel i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="5e512-118">In the Item number field, Select an item.</span></span> <span data-ttu-id="5e512-119">Om du använder demonstrationsdataföretaget USMF skriver du "D0001".</span><span class="sxs-lookup"><span data-stu-id="5e512-119">If you are using demo data company USMF, type 'D0001'.</span></span>
4. <span data-ttu-id="5e512-120">Öppna sökningen genom att klicka på listruteknappen i fältet Plats.</span><span class="sxs-lookup"><span data-stu-id="5e512-120">In the Site field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="5e512-121">Välj en plats i listan.</span><span class="sxs-lookup"><span data-stu-id="5e512-121">In the list, select a site.</span></span>
6. <span data-ttu-id="5e512-122">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Lagerställe.</span><span class="sxs-lookup"><span data-stu-id="5e512-122">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="5e512-123">Välj ett lagerställe i listan.</span><span class="sxs-lookup"><span data-stu-id="5e512-123">In the list, select a warehouse.</span></span>
    * <span data-ttu-id="5e512-124">Om du har valt en artikel med Plats som en obligatorisk dimension måste du ange platsen här.</span><span class="sxs-lookup"><span data-stu-id="5e512-124">If you have selected an item with Location as a mandatory dimension, you would have to specify the location here.</span></span>  
8. <span data-ttu-id="5e512-125">Ange ett tal i fältet Kvantitet.</span><span class="sxs-lookup"><span data-stu-id="5e512-125">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="5e512-126">Fältet Självkostnad anger kostnaden per enhet för lagerinleveranser.</span><span class="sxs-lookup"><span data-stu-id="5e512-126">The cost price field specifies the cost per unit for inventory receipts.</span></span> <span data-ttu-id="5e512-127">Om kostnaden inte har angetts för artikelnumret eller om du vill ändra det manuellt gör du det här.</span><span class="sxs-lookup"><span data-stu-id="5e512-127">If the cost is not specified for the item number or if you wanted to change it manually, you would do this here.</span></span>  

## <a name="validate-and-post-the-inventory-adjustment-journal"></a><span data-ttu-id="5e512-128">Validera och bokför lagerjusteringsjournalen</span><span class="sxs-lookup"><span data-stu-id="5e512-128">Validate and post the inventory adjustment journal</span></span>
1. <span data-ttu-id="5e512-129">Klicka på Validera.</span><span class="sxs-lookup"><span data-stu-id="5e512-129">Click Validate.</span></span>
2. <span data-ttu-id="5e512-130">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="5e512-130">Click OK.</span></span>
3. <span data-ttu-id="5e512-131">Klicka på Bokför.</span><span class="sxs-lookup"><span data-stu-id="5e512-131">Click Post.</span></span>
    * <span data-ttu-id="5e512-132">När du bokför den här typen av journal bokförs en lagerinleverans eller -utleverans, lagernivån och värdet ändras och redovisningstransaktioner skapas.</span><span class="sxs-lookup"><span data-stu-id="5e512-132">When you post this kind of journal, an inventory receipt or issue is posted, the inventory level and value are changed, and ledger transactions are generated.</span></span>  
4. <span data-ttu-id="5e512-133">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="5e512-133">Click OK.</span></span>
5. <span data-ttu-id="5e512-134">Stäng formuläret.</span><span class="sxs-lookup"><span data-stu-id="5e512-134">Close the form.</span></span>
6. <span data-ttu-id="5e512-135">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="5e512-135">Close the page.</span></span>

