---
title: Inventering i ett lagerställe
description: I den här avsnittet beskrivs hur du kan skapa och bokföra en lagerinventeringsjournal för att kunna räkna en viss artikel på en plats på lagerstället.
author: MarkusFogelberg
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventJournalCount, InventJournalCreate, HcmWorkerLookUp, InventItemIdLookupSimple, InventLocationIdLookup, WMSLocationIdLookup, InventTrans
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 24b8bc2daff2d7df6279c76f4d9a0e83244c7988
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5834059"
---
# <a name="count-inventory-in-a-warehouse"></a><span data-ttu-id="0489e-103">Inventering i ett lagerställe</span><span class="sxs-lookup"><span data-stu-id="0489e-103">Count inventory in a warehouse</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="0489e-104">I den här avsnittet beskrivs hur du kan skapa och bokföra en lagerinventeringsjournal för att kunna räkna en viss artikel på en plats på lagerstället.</span><span class="sxs-lookup"><span data-stu-id="0489e-104">This topic describes the process of creating and posting an inventory counting journal in order to count a specific item at a location in the warehouse.</span></span> <span data-ttu-id="0489e-105">Proceduren gäller grundläggande lagerstyrningsfunktioner som är tillgängliga i lagerhanteringmodulen, inte de lagerfunktioner som finns i lagerstyrningsmodulen.</span><span class="sxs-lookup"><span data-stu-id="0489e-105">The procedure applies to "basic warehousing" functionality, available in the Inventory management module, not to the warehousing functionality that's available in the Warehouse management module.</span></span> <span data-ttu-id="0489e-106">Du kan gå igenom den här proceduren i demonstrationsdataföretaget USMF eller använda dina egna data.</span><span class="sxs-lookup"><span data-stu-id="0489e-106">You can walk through this procedure in demo data company USMF, or using your own data.</span></span> <span data-ttu-id="0489e-107">Om du använder dina egna data, kontrollera att du har konfigurerat produkter och platser och att du har skapat ett lagerjournalnamn för inventeringsjournaler.</span><span class="sxs-lookup"><span data-stu-id="0489e-107">If you're using your own data, make sure that you have products and locations set up, and that you've created an inventory journal name for counting journals.</span></span> <span data-ttu-id="0489e-108">Lagerinventering utförs normalt av en lagerarbetare.</span><span class="sxs-lookup"><span data-stu-id="0489e-108">Inventory counting is normally carried out by a warehouse employee.</span></span>


## <a name="create-an-inventory-counting-journal"></a><span data-ttu-id="0489e-109">Skapa en lagerinventeringsjournal</span><span class="sxs-lookup"><span data-stu-id="0489e-109">Create an inventory counting journal</span></span>
1. <span data-ttu-id="0489e-110">Gå till **Navigeringsfönster > Moduler > Lagerhantering > Journalposter > Artikelräkning > Inventering**.</span><span class="sxs-lookup"><span data-stu-id="0489e-110">Go to **Navigation pane > Modules > Inventory management > Journal entries > Item counting > Counting**.</span></span>
2. <span data-ttu-id="0489e-111">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="0489e-111">Select **New**.</span></span>
3. <span data-ttu-id="0489e-112">I fältet **namn** väljer du det journalnamn för lagerinventering som du vill använda från listrutan.</span><span class="sxs-lookup"><span data-stu-id="0489e-112">In the **Name** field, select the inventory counting journal name you want to use from the drop-down list.</span></span> <span data-ttu-id="0489e-113">Vissa fält kommer att fyllas i baserat på inställningarna för journalnamnet för lagerinventering som du väljer.</span><span class="sxs-lookup"><span data-stu-id="0489e-113">Some other fields will be populated based on the setup of the inventory counting journal name that you select.</span></span>  
4. <span data-ttu-id="0489e-114">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Arbetare**.</span><span class="sxs-lookup"><span data-stu-id="0489e-114">In the **Worker** field, select the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="0489e-115">**Välj** den arbetare som du vill ha i listan.</span><span class="sxs-lookup"><span data-stu-id="0489e-115">In the list, **Select** the worker you want to use.</span></span>
6. <span data-ttu-id="0489e-116">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="0489e-116">Select **OK**.</span></span>

## <a name="create-journal-lines"></a><span data-ttu-id="0489e-117">Skapa journalrader</span><span class="sxs-lookup"><span data-stu-id="0489e-117">Create journal lines</span></span>
1. <span data-ttu-id="0489e-118">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="0489e-118">Select **New**.</span></span>
2. <span data-ttu-id="0489e-119">På fält **Artikelnummer** klicka på önskad post från listrutan.</span><span class="sxs-lookup"><span data-stu-id="0489e-119">In the **Item number** field, select the desired record from the drop-down list.</span></span> <span data-ttu-id="0489e-120">Om du använder demonstrationsföretaget USMF kan du välja **A0001**.</span><span class="sxs-lookup"><span data-stu-id="0489e-120">If you are using demo data company USMF, select **A0001**.</span></span>  
3. <span data-ttu-id="0489e-121">På fält **site** klicka på önskad post från listrutan.</span><span class="sxs-lookup"><span data-stu-id="0489e-121">In the **Site** field, select the desired record from the drop-down list.</span></span> <span data-ttu-id="0489e-122">Om du använder demonstrationsföretaget USMF kan du välja plats **2**.</span><span class="sxs-lookup"><span data-stu-id="0489e-122">If you are using demo data company USMF, select site **2**.</span></span>
4. <span data-ttu-id="0489e-123">På fält **Lagerställe** klicka på önskad post från listrutan.</span><span class="sxs-lookup"><span data-stu-id="0489e-123">In the **Warehouse** field, select the desired record from the drop-down list.</span></span> <span data-ttu-id="0489e-124">Om du använder demonstrationsföretaget USMF kan du välja lagerställe **24**.</span><span class="sxs-lookup"><span data-stu-id="0489e-124">If you are using demo data company USMF, select warehouse **24**.</span></span>  
5. <span data-ttu-id="0489e-125">På fält **Plats** klicka på önskad post från listrutan.</span><span class="sxs-lookup"><span data-stu-id="0489e-125">In the **Location** field, select the desired record from the drop-down list.</span></span> <span data-ttu-id="0489e-126">Om du använder demonstrationsföretaget USMF kan du välja platsen **BULK-001**.</span><span class="sxs-lookup"><span data-stu-id="0489e-126">If you are using demo data company USMF, select location **BULK-001**.</span></span>  
6. <span data-ttu-id="0489e-127">Ange ett värde i fältet Räknat.</span><span class="sxs-lookup"><span data-stu-id="0489e-127">In the Counted field, enter a number.</span></span> <span data-ttu-id="0489e-128">Om du anger ett nummer som skiljer sig till antalet i fältet **I lager**, uppdateras fältet **Kvantitet** med diskrepansen.</span><span class="sxs-lookup"><span data-stu-id="0489e-128">If you enter a counted number that's different to the number shown in the **On-hand** field, the **Quantity** field is updated to show the discrepancy.</span></span>  
7. <span data-ttu-id="0489e-129">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="0489e-129">Select **Save**.</span></span>

## <a name="post-the-inventory-counting-journal"></a><span data-ttu-id="0489e-130">Bokför lagerinventeringsjournalen</span><span class="sxs-lookup"><span data-stu-id="0489e-130">Post the inventory counting journal</span></span>
1. <span data-ttu-id="0489e-131">Välj **bokföring**</span><span class="sxs-lookup"><span data-stu-id="0489e-131">Select **Post**.</span></span> <span data-ttu-id="0489e-132">När du bokför en lagerinventeringsjournal och om det räknade antalet skiljer sig från antalet som rapporteras i fältet **I lager** där en lagerinleverans eller ett lageruttag bokförs, ändras lagernivån och värdet och redovisningstransaktioner genereras.</span><span class="sxs-lookup"><span data-stu-id="0489e-132">When you post an inventory counting journal, if the counted amount differs from amount that's reported in the **On-hand** field an inventory receipt or issue is posted, the inventory level and value are changed, and ledger transactions are generated.</span></span>
2. <span data-ttu-id="0489e-133">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="0489e-133">Select **OK**.</span></span>

## <a name="view-inventory-transactions"></a><span data-ttu-id="0489e-134">Visa lagertransaktioner</span><span class="sxs-lookup"><span data-stu-id="0489e-134">View inventory transactions</span></span>
1. <span data-ttu-id="0489e-135">Välj **Lager**.</span><span class="sxs-lookup"><span data-stu-id="0489e-135">Select **Inventory**.</span></span>
2. <span data-ttu-id="0489e-136">Markera **transaktioner**</span><span class="sxs-lookup"><span data-stu-id="0489e-136">Select **Transactions**.</span></span> <span data-ttu-id="0489e-137">Här kan du se alla relaterade transaktioner som skapas när du bokför en lagerinventeringsjournal.</span><span class="sxs-lookup"><span data-stu-id="0489e-137">Here you can see any related transactions that will be created when you post your inventory counting journal.</span></span>   



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]