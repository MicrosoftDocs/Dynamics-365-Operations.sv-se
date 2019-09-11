---
title: Överför fysiskt lager i lagerstället
description: I den här proceduren beskrivs hur du kan skapa och bokföra en lageröverföringsjournal för att kunna lagret registrera förflyttningen av en artikel från en plats till en annan på samma lagerställe.
author: MarkusFogelberg
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalTransfer, InventJournalCreate, InventItemIdLookupSimple, InventLocationIdLookup, WMSLocationIdLookup, InventTrans
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7715c8e7a56703993e8512af03f2ab8d6802a987
ms.sourcegitcommit: cbcf344b3b552acca56c3e27606eac7f2f124afe
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/22/2019
ms.locfileid: "1916586"
---
# <a name="transfer-physical-inventory-within-the-warehouse"></a><span data-ttu-id="2e085-103">Överför fysiskt lager i lagerstället</span><span class="sxs-lookup"><span data-stu-id="2e085-103">Transfer physical inventory within the warehouse</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="2e085-104">I den här proceduren beskrivs hur du kan skapa och bokföra en lageröverföringsjournal för att kunna lagret registrera förflyttningen av en artikel från en plats till en annan på samma lagerställe.</span><span class="sxs-lookup"><span data-stu-id="2e085-104">This procedure walks you through the process of creating and posting an inventory transfer journal in order to register movement of an item from one location in a warehouse to another.</span></span> <span data-ttu-id="2e085-105">Du måste ha ett lagerjournalnamn för lageröverföringar innan du sätter igång.</span><span class="sxs-lookup"><span data-stu-id="2e085-105">You need to have an inventory journal name set up for inventory transfers before you start this.</span></span> <span data-ttu-id="2e085-106">Du kan gå igenom den här proceduren i demonstrationsföretaget USMF med hjälp av exempelvärdena som visas, eller också kan du använda dina egna uppgifter om du har konfigurerat produkter och platser.</span><span class="sxs-lookup"><span data-stu-id="2e085-106">You can walk through this procedure in demo data company USMF using the example values that are shown, or using you can use your own data if you have products and locations set up.</span></span> <span data-ttu-id="2e085-107">Dessa uppgifter utförs vanligtvis av en lagerarbetare.</span><span class="sxs-lookup"><span data-stu-id="2e085-107">These tasks would normally be carried out by a warehouse employee.</span></span>


## <a name="create-an-inventory-transfer-journal"></a><span data-ttu-id="2e085-108">Skapa en lageröverföringsjournal</span><span class="sxs-lookup"><span data-stu-id="2e085-108">Create an inventory transfer journal</span></span>
1. <span data-ttu-id="2e085-109">I **navigeringsfönstret**, gå till **Lagerhantering > Journalposter > Artiklar > Överför**.</span><span class="sxs-lookup"><span data-stu-id="2e085-109">In the **Navigation pane**, go to **Inventory management > Journal entries > Items > Transfer**.</span></span>
2. <span data-ttu-id="2e085-110">Klicka på **Ny**.</span><span class="sxs-lookup"><span data-stu-id="2e085-110">Click **New**.</span></span>
3. <span data-ttu-id="2e085-111">I fältet **Namn**anger eller väljer du ett värde.</span><span class="sxs-lookup"><span data-stu-id="2e085-111">In the **Name** field, enter or select a value.</span></span>
4. <span data-ttu-id="2e085-112">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="2e085-112">Click **OK**.</span></span> <span data-ttu-id="2e085-113">Det finns alternativ för att ange från- och tilldimensioner för varje journalrad.</span><span class="sxs-lookup"><span data-stu-id="2e085-113">There is the option to specify 'From' and 'To' dimensions for each journal line.</span></span> <span data-ttu-id="2e085-114">Dessa är nödvändiga för den här journaltypen.</span><span class="sxs-lookup"><span data-stu-id="2e085-114">These are essential for this journal type.</span></span> <span data-ttu-id="2e085-115">Du kan överföra artiklar till platser med olika regler.</span><span class="sxs-lookup"><span data-stu-id="2e085-115">You can transfer items to locations using different rules.</span></span> <span data-ttu-id="2e085-116">I det här exemplet överför vi en artikel inom samma lagerställe, från en id-nummerstyrd plats till en plats som inte är id-nummerstyrd.</span><span class="sxs-lookup"><span data-stu-id="2e085-116">In this example we’ll transfer an item within the same warehouse, from a license plate controlled location to a location that is not license plate controlled.</span></span>   

## <a name="create-journal-lines"></a><span data-ttu-id="2e085-117">Skapa journalrader</span><span class="sxs-lookup"><span data-stu-id="2e085-117">Create journal lines</span></span>
1. <span data-ttu-id="2e085-118">På snabbfliken **Journalrader** klickar du på **Ny**.</span><span class="sxs-lookup"><span data-stu-id="2e085-118">Int the **Journal lines fastTab**, click **New**.</span></span>
2. <span data-ttu-id="2e085-119">I fältet **artikelnummer** anger du eller väljer ett värde.</span><span class="sxs-lookup"><span data-stu-id="2e085-119">In the **Item number** field, enter or select a value.</span></span> <span data-ttu-id="2e085-120">Om du använder USMF kan du välja A0001.</span><span class="sxs-lookup"><span data-stu-id="2e085-120">If you are using USMF, you can select 'A0001'.</span></span>  
3. <span data-ttu-id="2e085-121">Ange eller välj ett värde i fältet **Från site.**</span><span class="sxs-lookup"><span data-stu-id="2e085-121">In the **From site** field, enter or select a value.</span></span> <span data-ttu-id="2e085-122">Om du använder USMF kan du välja 2.</span><span class="sxs-lookup"><span data-stu-id="2e085-122">If you are using USMF, you can select '2'.</span></span>  
4. <span data-ttu-id="2e085-123">Ange eller välj ett värde i fältet **Till site.**</span><span class="sxs-lookup"><span data-stu-id="2e085-123">In the **To site** field, enter or select a value.</span></span> <span data-ttu-id="2e085-124">Om du använder USMF kan du välja 2.</span><span class="sxs-lookup"><span data-stu-id="2e085-124">If you are using USMF, you can select '2'.</span></span>  
5. <span data-ttu-id="2e085-125">Ange eller välj ett värde i fältet **Från lagerställe.**</span><span class="sxs-lookup"><span data-stu-id="2e085-125">In the **From warehouse** field, enter or select a value.</span></span> <span data-ttu-id="2e085-126">Om du använder USMF kan du välja 24.</span><span class="sxs-lookup"><span data-stu-id="2e085-126">If you are using USMF, you can select '24'.</span></span>  
6. <span data-ttu-id="2e085-127">Ange eller välj ett värde i fältet **Till lagerställe.**</span><span class="sxs-lookup"><span data-stu-id="2e085-127">In the **To warehouse** field, enter or select a value.</span></span> <span data-ttu-id="2e085-128">Om du använder USMF kan du välja 24.</span><span class="sxs-lookup"><span data-stu-id="2e085-128">If you are using USMF, you can select '24'.</span></span>  
7. <span data-ttu-id="2e085-129">Ange eller välj ett värde i fältet **Från plats.**</span><span class="sxs-lookup"><span data-stu-id="2e085-129">In the **From location** field, enter or select a value.</span></span> <span data-ttu-id="2e085-130">Om du använder USMF kan du välja FL-001.</span><span class="sxs-lookup"><span data-stu-id="2e085-130">If you are using USMF, you can select 'FL-001'.</span></span>  
8. <span data-ttu-id="2e085-131">Ange eller välj ett värde i fältet **Till plats.**</span><span class="sxs-lookup"><span data-stu-id="2e085-131">In the **To location** field, enter or select a value.</span></span> <span data-ttu-id="2e085-132">Om du använder USMF kan du välja BULK-001.</span><span class="sxs-lookup"><span data-stu-id="2e085-132">If you are using USMF, you can select 'BULK-001'.</span></span>  
9. <span data-ttu-id="2e085-133">Ange ett nummer i fältet **Kvantitet**.</span><span class="sxs-lookup"><span data-stu-id="2e085-133">In the **Quantity** field, enter a number.</span></span>
10. <span data-ttu-id="2e085-134">På snabbfliken **Radinformation**, klicka på fliken **Lagerdimensioner**.</span><span class="sxs-lookup"><span data-stu-id="2e085-134">In the **Line details** fastTab, click the **Inventory dimensions** tab.</span></span>
11. <span data-ttu-id="2e085-135">Ange eller välj ett värde i **Från lagerdimensioner**, i fältet **ID-nummer**.</span><span class="sxs-lookup"><span data-stu-id="2e085-135">In **From inventory dimensions**, in the **License plate** field, enter or select a value.</span></span> <span data-ttu-id="2e085-136">Om du använder USMF kan du välja 24.</span><span class="sxs-lookup"><span data-stu-id="2e085-136">If you are using USMF, you can select '24'.</span></span>  
12. <span data-ttu-id="2e085-137">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="2e085-137">Click **Save**.</span></span>

## <a name="post-the-inventory-transfer-journal"></a><span data-ttu-id="2e085-138">Bokföra lageröverföringsjournalen</span><span class="sxs-lookup"><span data-stu-id="2e085-138">Post the inventory transfer journal</span></span>
1. <span data-ttu-id="2e085-139">Klicka på **Bokför** i **åtgärdsfönstret**.</span><span class="sxs-lookup"><span data-stu-id="2e085-139">On the **Action pane**, click **Post**.</span></span>
2. <span data-ttu-id="2e085-140">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="2e085-140">Click **OK**.</span></span>

## <a name="view-inventory-transactions"></a><span data-ttu-id="2e085-141">Visa lagertransaktioner</span><span class="sxs-lookup"><span data-stu-id="2e085-141">View inventory transactions</span></span>
1. <span data-ttu-id="2e085-142">Klicka på **Lager**.</span><span class="sxs-lookup"><span data-stu-id="2e085-142">Click **Inventory**.</span></span>
2. <span data-ttu-id="2e085-143">Klicka på **Transaktioner.**</span><span class="sxs-lookup"><span data-stu-id="2e085-143">Click **Transactions**.</span></span> <span data-ttu-id="2e085-144">Här kan du se de transaktioner som skapades när du bokförde din journal.</span><span class="sxs-lookup"><span data-stu-id="2e085-144">Here you can see the transactions that were created when you posted your journal.</span></span>  

