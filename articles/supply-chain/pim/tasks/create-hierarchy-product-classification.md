---
title: Skapa en produktklassificeringshierarki
description: I den här proceduren visas hur du skapar en ny kategorihierarki och tilldelar en typ av artikelkodhierarki.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResCategoryHierarchyListPage, EcoResCategoryHierarchyCreate, EcoResCategory, EcoResCategoryHierarchyRole
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fb49f5f3f8a5a788cb4c6d1be69534ba808e3675
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "346834"
---
# <a name="create-a-hierarchy-of-product-classification"></a><span data-ttu-id="c3d88-103">Skapa en produktklassificeringshierarki</span><span class="sxs-lookup"><span data-stu-id="c3d88-103">Create a hierarchy of product classification</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c3d88-104">I den här proceduren visas hur du skapar en ny kategorihierarki och tilldelar en typ av artikelkodhierarki.</span><span class="sxs-lookup"><span data-stu-id="c3d88-104">This procedure shows how to create a new category hierarchy and assign a commodity code hierarchy type.</span></span> <span data-ttu-id="c3d88-105">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="c3d88-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="c3d88-106">Den här proceduren är avsedd för kategorichefen.</span><span class="sxs-lookup"><span data-stu-id="c3d88-106">This procedure is intended for the category manager.</span></span>


## <a name="create-the-new-category-hierarchy"></a><span data-ttu-id="c3d88-107">Skapa den nya kategorihierarkin</span><span class="sxs-lookup"><span data-stu-id="c3d88-107">Create the new category hierarchy</span></span>
1. <span data-ttu-id="c3d88-108">Gå till Produktinformationshantering > Inställningar > Kategorier och attribut > Kategorihierarkier.</span><span class="sxs-lookup"><span data-stu-id="c3d88-108">Go to Product information management > Setup > Categories and attributes > Category hierarchies.</span></span>
2. <span data-ttu-id="c3d88-109">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="c3d88-109">Click New.</span></span>
3. <span data-ttu-id="c3d88-110">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="c3d88-110">In the Name field, type a value.</span></span>
4. <span data-ttu-id="c3d88-111">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="c3d88-111">In the Description field, type a value.</span></span>
5. <span data-ttu-id="c3d88-112">Klicka på Skapa.</span><span class="sxs-lookup"><span data-stu-id="c3d88-112">Click Create.</span></span>

## <a name="build-the-hierarchy"></a><span data-ttu-id="c3d88-113">Skapa hierarkin</span><span class="sxs-lookup"><span data-stu-id="c3d88-113">Build the hierarchy</span></span>
1. <span data-ttu-id="c3d88-114">Klicka på Ny kategorinod.</span><span class="sxs-lookup"><span data-stu-id="c3d88-114">Click New category node.</span></span>
2. <span data-ttu-id="c3d88-115">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="c3d88-115">In the Name field, type a value.</span></span>
3. <span data-ttu-id="c3d88-116">Skriv ett värde i fältet Kod.</span><span class="sxs-lookup"><span data-stu-id="c3d88-116">In the Code field, type a value.</span></span>
4. <span data-ttu-id="c3d88-117">Skriv ett värde i fältet Eget namn.</span><span class="sxs-lookup"><span data-stu-id="c3d88-117">In the Friendly name field, type a value.</span></span>
5. <span data-ttu-id="c3d88-118">Klicka på Ny kategorinod.</span><span class="sxs-lookup"><span data-stu-id="c3d88-118">Click New category node.</span></span>
6. <span data-ttu-id="c3d88-119">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="c3d88-119">In the Name field, type a value.</span></span>
7. <span data-ttu-id="c3d88-120">Skriv ett värde i fältet Kod.</span><span class="sxs-lookup"><span data-stu-id="c3d88-120">In the Code field, type a value.</span></span>
8. <span data-ttu-id="c3d88-121">Skriv ett värde i fältet Eget namn.</span><span class="sxs-lookup"><span data-stu-id="c3d88-121">In the Friendly name field, type a value.</span></span>
9. <span data-ttu-id="c3d88-122">Klicka på Ny kategorinod.</span><span class="sxs-lookup"><span data-stu-id="c3d88-122">Click New category node.</span></span>
10. <span data-ttu-id="c3d88-123">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="c3d88-123">In the Name field, type a value.</span></span>
11. <span data-ttu-id="c3d88-124">Skriv ett värde i fältet Kod.</span><span class="sxs-lookup"><span data-stu-id="c3d88-124">In the Code field, type a value.</span></span>
12. <span data-ttu-id="c3d88-125">Skriv ett värde i fältet Eget namn.</span><span class="sxs-lookup"><span data-stu-id="c3d88-125">In the Friendly name field, type a value.</span></span>
13. <span data-ttu-id="c3d88-126">Klicka på Ny kategorinod.</span><span class="sxs-lookup"><span data-stu-id="c3d88-126">Click New category node.</span></span>
14. <span data-ttu-id="c3d88-127">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="c3d88-127">In the Name field, type a value.</span></span>
15. <span data-ttu-id="c3d88-128">Skriv ett värde i fältet Kod.</span><span class="sxs-lookup"><span data-stu-id="c3d88-128">In the Code field, type a value.</span></span>
16. <span data-ttu-id="c3d88-129">Skriv ett värde i fältet Eget namn.</span><span class="sxs-lookup"><span data-stu-id="c3d88-129">In the Friendly name field, type a value.</span></span>
17. <span data-ttu-id="c3d88-130">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="c3d88-130">Close the page.</span></span>

## <a name="classify-the-hierarchy"></a><span data-ttu-id="c3d88-131">Klassificera hierarkin</span><span class="sxs-lookup"><span data-stu-id="c3d88-131">Classify the hierarchy</span></span>
1. <span data-ttu-id="c3d88-132">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="c3d88-132">In the list, find and select the desired record.</span></span>
2. <span data-ttu-id="c3d88-133">Klicka på Kategorihierarki i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="c3d88-133">On the Action Pane, click Category hierarchy.</span></span>
3. <span data-ttu-id="c3d88-134">Klicka på Associera hierarkityp.</span><span class="sxs-lookup"><span data-stu-id="c3d88-134">Click Associate hierarchy type.</span></span>
4. <span data-ttu-id="c3d88-135">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="c3d88-135">Click New.</span></span>
5. <span data-ttu-id="c3d88-136">Välj ett alternativ i fältet Kategorihierarkityp.</span><span class="sxs-lookup"><span data-stu-id="c3d88-136">In the Category hierarchy type field, select an option.</span></span>
    * <span data-ttu-id="c3d88-137">Välj kategorihierarkitypen för artikelkoden för produktklassificering.</span><span class="sxs-lookup"><span data-stu-id="c3d88-137">Select the Commodity code category hierarchy type for product classification.</span></span>  
6. <span data-ttu-id="c3d88-138">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Kategorihierarki.</span><span class="sxs-lookup"><span data-stu-id="c3d88-138">In the Category hierarchy field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="c3d88-139">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="c3d88-139">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="c3d88-140">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="c3d88-140">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="c3d88-141">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="c3d88-141">Close the page.</span></span>

