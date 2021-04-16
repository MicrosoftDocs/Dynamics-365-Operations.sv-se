---
title: Skapa en produktklassificeringshierarki
description: I den här proceduren visas hur du skapar en ny kategorihierarki och tilldelar en typ av artikelkodhierarki.
author: ShylaThompson
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResCategoryHierarchyListPage, EcoResCategoryHierarchyCreate, EcoResCategory, EcoResCategoryHierarchyRole, EcoResProductCategory, EcoResCategorySearchList, EcoResCategoryHierarchyFactbox, EcoResCategoryFriendlyName, EcoResCategoryAddProduct
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d4e2fdc62d7faa73efa78092d7754d3fa1213a94
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5809384"
---
# <a name="create-a-hierarchy-of-product-classification"></a><span data-ttu-id="bc1af-103">Skapa en produktklassificeringshierarki</span><span class="sxs-lookup"><span data-stu-id="bc1af-103">Create a hierarchy of product classification</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="bc1af-104">I den här proceduren visas hur du skapar en ny kategorihierarki och tilldelar en typ av artikelkodhierarki.</span><span class="sxs-lookup"><span data-stu-id="bc1af-104">This procedure shows how to create a new category hierarchy and assign a commodity code hierarchy type.</span></span> <span data-ttu-id="bc1af-105">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="bc1af-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="bc1af-106">Den här proceduren är avsedd för kategorichefen.</span><span class="sxs-lookup"><span data-stu-id="bc1af-106">This procedure is intended for the category manager.</span></span>


## <a name="create-the-new-category-hierarchy"></a><span data-ttu-id="bc1af-107">Skapa den nya kategorihierarkin</span><span class="sxs-lookup"><span data-stu-id="bc1af-107">Create the new category hierarchy</span></span>
1. <span data-ttu-id="bc1af-108">Gå till **Navigeringsfönster > Moduler > Produktinformationshantering > Inställningar > Kategorier och attribut > Kategorihierarkier**.</span><span class="sxs-lookup"><span data-stu-id="bc1af-108">Go to **Navigation pane > Modules > Product information management > Setup > Categories and attributes > Category hierarchies**.</span></span>
2. <span data-ttu-id="bc1af-109">Klicka på **Ny**.</span><span class="sxs-lookup"><span data-stu-id="bc1af-109">Click **New**.</span></span>
3. <span data-ttu-id="bc1af-110">Skriv ett värde i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="bc1af-110">In the **Name** field, type a value.</span></span>
4. <span data-ttu-id="bc1af-111">I fältet **Beskrivning** anger du ett värde.</span><span class="sxs-lookup"><span data-stu-id="bc1af-111">In the **Description** field, type a value.</span></span>
5. <span data-ttu-id="bc1af-112">Klicka på **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="bc1af-112">Click **Create**.</span></span>

## <a name="build-the-hierarchy"></a><span data-ttu-id="bc1af-113">Skapa hierarkin</span><span class="sxs-lookup"><span data-stu-id="bc1af-113">Build the hierarchy</span></span>
1. <span data-ttu-id="bc1af-114">Klicka på kategorinoden **Ny**.</span><span class="sxs-lookup"><span data-stu-id="bc1af-114">Click **New** category node.</span></span>
2. <span data-ttu-id="bc1af-115">Skriv ett värde i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="bc1af-115">In the **Name** field, type a value.</span></span>
3. <span data-ttu-id="bc1af-116">Skriv ett värde i fältet **Kod**.</span><span class="sxs-lookup"><span data-stu-id="bc1af-116">In the **Code** field, type a value.</span></span>
4. <span data-ttu-id="bc1af-117">Skriv ett värde i fältet **Eget namn**.</span><span class="sxs-lookup"><span data-stu-id="bc1af-117">In the **Friendly name** field, type a value.</span></span>
5. <span data-ttu-id="bc1af-118">Klicka på kategorinoden **Ny**.</span><span class="sxs-lookup"><span data-stu-id="bc1af-118">Click **New** category node.</span></span>
6. <span data-ttu-id="bc1af-119">Skriv ett värde i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="bc1af-119">In the **Name** field, type a value.</span></span>
7. <span data-ttu-id="bc1af-120">Skriv ett värde i fältet **Kod**.</span><span class="sxs-lookup"><span data-stu-id="bc1af-120">In the **Code** field, type a value.</span></span>
8. <span data-ttu-id="bc1af-121">Skriv ett värde i fältet **Eget namn**.</span><span class="sxs-lookup"><span data-stu-id="bc1af-121">In the **Friendly name** field, type a value.</span></span>
9. <span data-ttu-id="bc1af-122">Klicka på kategorinoden **Ny**.</span><span class="sxs-lookup"><span data-stu-id="bc1af-122">Click **New** category node.</span></span>
10. <span data-ttu-id="bc1af-123">Skriv ett värde i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="bc1af-123">In the **Name** field, type a value.</span></span>
11. <span data-ttu-id="bc1af-124">Skriv ett värde i fältet **Kod**.</span><span class="sxs-lookup"><span data-stu-id="bc1af-124">In the **Code** field, type a value.</span></span>
12. <span data-ttu-id="bc1af-125">Skriv ett värde i fältet **Eget namn**.</span><span class="sxs-lookup"><span data-stu-id="bc1af-125">In the **Friendly name** field, type a value.</span></span>
13. <span data-ttu-id="bc1af-126">Klicka på kategorinoden **Ny**.</span><span class="sxs-lookup"><span data-stu-id="bc1af-126">Click **New** category node.</span></span>
14. <span data-ttu-id="bc1af-127">Skriv ett värde i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="bc1af-127">In the **Name** field, type a value.</span></span>
15. <span data-ttu-id="bc1af-128">Skriv ett värde i fältet **Kod**.</span><span class="sxs-lookup"><span data-stu-id="bc1af-128">In the **Code** field, type a value.</span></span>
16. <span data-ttu-id="bc1af-129">Skriv ett värde i fältet **Eget namn**.</span><span class="sxs-lookup"><span data-stu-id="bc1af-129">In the **Friendly name** field, type a value.</span></span>
17. <span data-ttu-id="bc1af-130">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="bc1af-130">Close the page.</span></span>

## <a name="classify-the-hierarchy"></a><span data-ttu-id="bc1af-131">Klassificera hierarkin</span><span class="sxs-lookup"><span data-stu-id="bc1af-131">Classify the hierarchy</span></span>
1. <span data-ttu-id="bc1af-132">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="bc1af-132">In the list, find and select the desired record.</span></span>
2. <span data-ttu-id="bc1af-133">Klicka på **Kategorihierarki** i **åtgärdsfönstret**.</span><span class="sxs-lookup"><span data-stu-id="bc1af-133">On the **Action Pane**, click **Category hierarchy**.</span></span>
3. <span data-ttu-id="bc1af-134">Klicka på **Associera hierarkityp**.</span><span class="sxs-lookup"><span data-stu-id="bc1af-134">Click **Associate hierarchy type**.</span></span>
4. <span data-ttu-id="bc1af-135">Klicka på **Ny**.</span><span class="sxs-lookup"><span data-stu-id="bc1af-135">Click **New**.</span></span>
5. <span data-ttu-id="bc1af-136">Välj ett alternativ i fältet **Kategorihierarkityp**.</span><span class="sxs-lookup"><span data-stu-id="bc1af-136">In the **Category hierarchy type** field, select an option.</span></span> <span data-ttu-id="bc1af-137">Välj **kategorihierarkitypen för artikelkoden för produktklassificering**.</span><span class="sxs-lookup"><span data-stu-id="bc1af-137">Select the **Commodity code category hierarchy type for product classification**.</span></span>  
6. <span data-ttu-id="bc1af-138">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Kategorihierarki**.</span><span class="sxs-lookup"><span data-stu-id="bc1af-138">In the **Category hierarchy** field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="bc1af-139">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="bc1af-139">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="bc1af-140">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="bc1af-140">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="bc1af-141">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="bc1af-141">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]