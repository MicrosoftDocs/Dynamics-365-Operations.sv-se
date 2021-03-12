---
title: Inventering i ett lagerställe
description: I den här avsnittet beskrivs hur du kan skapa och bokföra en lagerinventeringsjournal för att kunna räkna en viss artikel på en plats på lagerstället.
author: MarkusFogelberg
manager: tfehr
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalCount, InventJournalCreate, HcmWorkerLookUp, InventItemIdLookupSimple, InventLocationIdLookup, WMSLocationIdLookup, InventTrans
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0a7f85cb91f36004a6bd6da714e7baa460a83a66
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "5000115"
---
# <a name="count-inventory-in-a-warehouse"></a><span data-ttu-id="e7b0b-103">Inventering i ett lagerställe</span><span class="sxs-lookup"><span data-stu-id="e7b0b-103">Count inventory in a warehouse</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e7b0b-104">I den här avsnittet beskrivs hur du kan skapa och bokföra en lagerinventeringsjournal för att kunna räkna en viss artikel på en plats på lagerstället.</span><span class="sxs-lookup"><span data-stu-id="e7b0b-104">This topic describes the process of creating and posting an inventory counting journal in order to count a specific item at a location in the warehouse.</span></span> <span data-ttu-id="e7b0b-105">Proceduren gäller grundläggande lagerstyrningsfunktioner som är tillgängliga i lagerhanteringmodulen, inte de lagerfunktioner som finns i lagerstyrningsmodulen.</span><span class="sxs-lookup"><span data-stu-id="e7b0b-105">The procedure applies to "basic warehousing" functionality, available in the Inventory management module, not to the warehousing functionality that's available in the Warehouse management module.</span></span> <span data-ttu-id="e7b0b-106">Du kan gå igenom den här proceduren i demonstrationsdataföretaget USMF eller använda dina egna data.</span><span class="sxs-lookup"><span data-stu-id="e7b0b-106">You can walk through this procedure in demo data company USMF, or using your own data.</span></span> <span data-ttu-id="e7b0b-107">Om du använder dina egna data, kontrollera att du har konfigurerat produkter och platser och att du har skapat ett lagerjournalnamn för inventeringsjournaler.</span><span class="sxs-lookup"><span data-stu-id="e7b0b-107">If you're using your own data, make sure that you have products and locations set up, and that you've created an inventory journal name for counting journals.</span></span> <span data-ttu-id="e7b0b-108">Lagerinventering utförs normalt av en lagerarbetare.</span><span class="sxs-lookup"><span data-stu-id="e7b0b-108">Inventory counting is normally carried out by a warehouse employee.</span></span>


## <a name="create-an-inventory-counting-journal"></a><span data-ttu-id="e7b0b-109">Skapa en lagerinventeringsjournal</span><span class="sxs-lookup"><span data-stu-id="e7b0b-109">Create an inventory counting journal</span></span>
1. <span data-ttu-id="e7b0b-110">Gå till **Navigeringsfönster > Moduler > Lagerhantering > Journalposter > Artikelräkning > Inventering**.</span><span class="sxs-lookup"><span data-stu-id="e7b0b-110">Go to **Navigation pane > Modules > Inventory management > Journal entries > Item counting > Counting**.</span></span>
2. <span data-ttu-id="e7b0b-111">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="e7b0b-111">Select **New**.</span></span>
3. <span data-ttu-id="e7b0b-112">I fältet **namn** väljer du det journalnamn för lagerinventering som du vill använda från listrutan.</span><span class="sxs-lookup"><span data-stu-id="e7b0b-112">In the **Name** field, select the inventory counting journal name you want to use from the drop-down list.</span></span> <span data-ttu-id="e7b0b-113">Vissa fält kommer att fyllas i baserat på inställningarna för journalnamnet för lagerinventering som du väljer.</span><span class="sxs-lookup"><span data-stu-id="e7b0b-113">Some other fields will be populated based on the setup of the inventory counting journal name that you select.</span></span>  
4. <span data-ttu-id="e7b0b-114">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Arbetare**.</span><span class="sxs-lookup"><span data-stu-id="e7b0b-114">In the **Worker** field, select the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="e7b0b-115">**Välj** den arbetare som du vill ha i listan.</span><span class="sxs-lookup"><span data-stu-id="e7b0b-115">In the list, **Select** the worker you want to use.</span></span>
6. <span data-ttu-id="e7b0b-116">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="e7b0b-116">Select **OK**.</span></span>

## <a name="create-journal-lines"></a><span data-ttu-id="e7b0b-117">Skapa journalrader</span><span class="sxs-lookup"><span data-stu-id="e7b0b-117">Create journal lines</span></span>
1. <span data-ttu-id="e7b0b-118">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="e7b0b-118">Select **New**.</span></span>
2. <span data-ttu-id="e7b0b-119">På fält **Artikelnummer** klicka på önskad post från listrutan.</span><span class="sxs-lookup"><span data-stu-id="e7b0b-119">In the **Item number** field, select the desired record from the drop-down list.</span></span> <span data-ttu-id="e7b0b-120">Om du använder demonstrationsföretaget USMF kan du välja **A0001**.</span><span class="sxs-lookup"><span data-stu-id="e7b0b-120">If you are using demo data company USMF, select **A0001**.</span></span>  
3. <span data-ttu-id="e7b0b-121">På fält **site** klicka på önskad post från listrutan.</span><span class="sxs-lookup"><span data-stu-id="e7b0b-121">In the **Site** field, select the desired record from the drop-down list.</span></span> <span data-ttu-id="e7b0b-122">Om du använder demonstrationsföretaget USMF kan du välja plats **2**.</span><span class="sxs-lookup"><span data-stu-id="e7b0b-122">If you are using demo data company USMF, select site **2**.</span></span>
4. <span data-ttu-id="e7b0b-123">På fält **Lagerställe** klicka på önskad post från listrutan.</span><span class="sxs-lookup"><span data-stu-id="e7b0b-123">In the **Warehouse** field, select the desired record from the drop-down list.</span></span> <span data-ttu-id="e7b0b-124">Om du använder demonstrationsföretaget USMF kan du välja lagerställe **24**.</span><span class="sxs-lookup"><span data-stu-id="e7b0b-124">If you are using demo data company USMF, select warehouse **24**.</span></span>  
5. <span data-ttu-id="e7b0b-125">På fält **Plats** klicka på önskad post från listrutan.</span><span class="sxs-lookup"><span data-stu-id="e7b0b-125">In the **Location** field, select the desired record from the drop-down list.</span></span> <span data-ttu-id="e7b0b-126">Om du använder demonstrationsföretaget USMF kan du välja platsen **BULK-001**.</span><span class="sxs-lookup"><span data-stu-id="e7b0b-126">If you are using demo data company USMF, select location **BULK-001**.</span></span>  
6. <span data-ttu-id="e7b0b-127">Ange ett värde i fältet Räknat.</span><span class="sxs-lookup"><span data-stu-id="e7b0b-127">In the Counted field, enter a number.</span></span> <span data-ttu-id="e7b0b-128">Om du anger ett nummer som skiljer sig till antalet i fältet **I lager**, uppdateras fältet **Kvantitet** med diskrepansen.</span><span class="sxs-lookup"><span data-stu-id="e7b0b-128">If you enter a counted number that's different to the number shown in the **On-hand** field, the **Quantity** field is updated to show the discrepancy.</span></span>  
7. <span data-ttu-id="e7b0b-129">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="e7b0b-129">Select **Save**.</span></span>

## <a name="post-the-inventory-counting-journal"></a><span data-ttu-id="e7b0b-130">Bokför lagerinventeringsjournalen</span><span class="sxs-lookup"><span data-stu-id="e7b0b-130">Post the inventory counting journal</span></span>
1. <span data-ttu-id="e7b0b-131">Välj **bokföring**</span><span class="sxs-lookup"><span data-stu-id="e7b0b-131">Select **Post**.</span></span> <span data-ttu-id="e7b0b-132">När du bokför en lagerinventeringsjournal och om det räknade antalet skiljer sig från antalet som rapporteras i fältet **I lager** där en lagerinleverans eller ett lageruttag bokförs, ändras lagernivån och värdet och redovisningstransaktioner genereras.</span><span class="sxs-lookup"><span data-stu-id="e7b0b-132">When you post an inventory counting journal, if the counted amount differs from amount that's reported in the **On-hand** field an inventory receipt or issue is posted, the inventory level and value are changed, and ledger transactions are generated.</span></span>
2. <span data-ttu-id="e7b0b-133">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="e7b0b-133">Select **OK**.</span></span>

## <a name="view-inventory-transactions"></a><span data-ttu-id="e7b0b-134">Visa lagertransaktioner</span><span class="sxs-lookup"><span data-stu-id="e7b0b-134">View inventory transactions</span></span>
1. <span data-ttu-id="e7b0b-135">Välj **Lager**.</span><span class="sxs-lookup"><span data-stu-id="e7b0b-135">Select **Inventory**.</span></span>
2. <span data-ttu-id="e7b0b-136">Markera **transaktioner**</span><span class="sxs-lookup"><span data-stu-id="e7b0b-136">Select **Transactions**.</span></span> <span data-ttu-id="e7b0b-137">Här kan du se alla relaterade transaktioner som skapas när du bokför en lagerinventeringsjournal.</span><span class="sxs-lookup"><span data-stu-id="e7b0b-137">Here you can see any related transactions that will be created when you post your inventory counting journal.</span></span>   

