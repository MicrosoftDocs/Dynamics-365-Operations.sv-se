---
title: Skapa en produktklassificeringshierarki
description: I den här proceduren visas hur du skapar en ny kategorihierarki och tilldelar en typ av artikelkodhierarki.
author: ShylaThompson
manager: tfehr
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResCategoryHierarchyListPage, EcoResCategoryHierarchyCreate, EcoResCategory, EcoResCategoryHierarchyRole, EcoResProductCategory, EcoResCategorySearchList, EcoResCategoryHierarchyFactbox, EcoResCategoryFriendlyName, EcoResCategoryAddProduct
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 59631148dbd2ad27ce2bb5c268d78e625daef6bb
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5224461"
---
# <a name="create-a-hierarchy-of-product-classification"></a><span data-ttu-id="6dd8e-103">Skapa en produktklassificeringshierarki</span><span class="sxs-lookup"><span data-stu-id="6dd8e-103">Create a hierarchy of product classification</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="6dd8e-104">I den här proceduren visas hur du skapar en ny kategorihierarki och tilldelar en typ av artikelkodhierarki.</span><span class="sxs-lookup"><span data-stu-id="6dd8e-104">This procedure shows how to create a new category hierarchy and assign a commodity code hierarchy type.</span></span> <span data-ttu-id="6dd8e-105">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="6dd8e-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="6dd8e-106">Den här proceduren är avsedd för kategorichefen.</span><span class="sxs-lookup"><span data-stu-id="6dd8e-106">This procedure is intended for the category manager.</span></span>


## <a name="create-the-new-category-hierarchy"></a><span data-ttu-id="6dd8e-107">Skapa den nya kategorihierarkin</span><span class="sxs-lookup"><span data-stu-id="6dd8e-107">Create the new category hierarchy</span></span>
1. <span data-ttu-id="6dd8e-108">Gå till **Navigeringsfönster > Moduler > Produktinformationshantering > Inställningar > Kategorier och attribut > Kategorihierarkier**.</span><span class="sxs-lookup"><span data-stu-id="6dd8e-108">Go to **Navigation pane > Modules > Product information management > Setup > Categories and attributes > Category hierarchies**.</span></span>
2. <span data-ttu-id="6dd8e-109">Klicka på **Ny**.</span><span class="sxs-lookup"><span data-stu-id="6dd8e-109">Click **New**.</span></span>
3. <span data-ttu-id="6dd8e-110">Skriv ett värde i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="6dd8e-110">In the **Name** field, type a value.</span></span>
4. <span data-ttu-id="6dd8e-111">I fältet **Beskrivning** anger du ett värde.</span><span class="sxs-lookup"><span data-stu-id="6dd8e-111">In the **Description** field, type a value.</span></span>
5. <span data-ttu-id="6dd8e-112">Klicka på **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="6dd8e-112">Click **Create**.</span></span>

## <a name="build-the-hierarchy"></a><span data-ttu-id="6dd8e-113">Skapa hierarkin</span><span class="sxs-lookup"><span data-stu-id="6dd8e-113">Build the hierarchy</span></span>
1. <span data-ttu-id="6dd8e-114">Klicka på kategorinoden **Ny**.</span><span class="sxs-lookup"><span data-stu-id="6dd8e-114">Click **New** category node.</span></span>
2. <span data-ttu-id="6dd8e-115">Skriv ett värde i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="6dd8e-115">In the **Name** field, type a value.</span></span>
3. <span data-ttu-id="6dd8e-116">Skriv ett värde i fältet **Kod**.</span><span class="sxs-lookup"><span data-stu-id="6dd8e-116">In the **Code** field, type a value.</span></span>
4. <span data-ttu-id="6dd8e-117">Skriv ett värde i fältet **Eget namn**.</span><span class="sxs-lookup"><span data-stu-id="6dd8e-117">In the **Friendly name** field, type a value.</span></span>
5. <span data-ttu-id="6dd8e-118">Klicka på kategorinoden **Ny**.</span><span class="sxs-lookup"><span data-stu-id="6dd8e-118">Click **New** category node.</span></span>
6. <span data-ttu-id="6dd8e-119">Skriv ett värde i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="6dd8e-119">In the **Name** field, type a value.</span></span>
7. <span data-ttu-id="6dd8e-120">Skriv ett värde i fältet **Kod**.</span><span class="sxs-lookup"><span data-stu-id="6dd8e-120">In the **Code** field, type a value.</span></span>
8. <span data-ttu-id="6dd8e-121">Skriv ett värde i fältet **Eget namn**.</span><span class="sxs-lookup"><span data-stu-id="6dd8e-121">In the **Friendly name** field, type a value.</span></span>
9. <span data-ttu-id="6dd8e-122">Klicka på kategorinoden **Ny**.</span><span class="sxs-lookup"><span data-stu-id="6dd8e-122">Click **New** category node.</span></span>
10. <span data-ttu-id="6dd8e-123">Skriv ett värde i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="6dd8e-123">In the **Name** field, type a value.</span></span>
11. <span data-ttu-id="6dd8e-124">Skriv ett värde i fältet **Kod**.</span><span class="sxs-lookup"><span data-stu-id="6dd8e-124">In the **Code** field, type a value.</span></span>
12. <span data-ttu-id="6dd8e-125">Skriv ett värde i fältet **Eget namn**.</span><span class="sxs-lookup"><span data-stu-id="6dd8e-125">In the **Friendly name** field, type a value.</span></span>
13. <span data-ttu-id="6dd8e-126">Klicka på kategorinoden **Ny**.</span><span class="sxs-lookup"><span data-stu-id="6dd8e-126">Click **New** category node.</span></span>
14. <span data-ttu-id="6dd8e-127">Skriv ett värde i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="6dd8e-127">In the **Name** field, type a value.</span></span>
15. <span data-ttu-id="6dd8e-128">Skriv ett värde i fältet **Kod**.</span><span class="sxs-lookup"><span data-stu-id="6dd8e-128">In the **Code** field, type a value.</span></span>
16. <span data-ttu-id="6dd8e-129">Skriv ett värde i fältet **Eget namn**.</span><span class="sxs-lookup"><span data-stu-id="6dd8e-129">In the **Friendly name** field, type a value.</span></span>
17. <span data-ttu-id="6dd8e-130">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="6dd8e-130">Close the page.</span></span>

## <a name="classify-the-hierarchy"></a><span data-ttu-id="6dd8e-131">Klassificera hierarkin</span><span class="sxs-lookup"><span data-stu-id="6dd8e-131">Classify the hierarchy</span></span>
1. <span data-ttu-id="6dd8e-132">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="6dd8e-132">In the list, find and select the desired record.</span></span>
2. <span data-ttu-id="6dd8e-133">Klicka på **Kategorihierarki** i **åtgärdsfönstret**.</span><span class="sxs-lookup"><span data-stu-id="6dd8e-133">On the **Action Pane**, click **Category hierarchy**.</span></span>
3. <span data-ttu-id="6dd8e-134">Klicka på **Associera hierarkityp**.</span><span class="sxs-lookup"><span data-stu-id="6dd8e-134">Click **Associate hierarchy type**.</span></span>
4. <span data-ttu-id="6dd8e-135">Klicka på **Ny**.</span><span class="sxs-lookup"><span data-stu-id="6dd8e-135">Click **New**.</span></span>
5. <span data-ttu-id="6dd8e-136">Välj ett alternativ i fältet **Kategorihierarkityp**.</span><span class="sxs-lookup"><span data-stu-id="6dd8e-136">In the **Category hierarchy type** field, select an option.</span></span> <span data-ttu-id="6dd8e-137">Välj **kategorihierarkitypen för artikelkoden för produktklassificering**.</span><span class="sxs-lookup"><span data-stu-id="6dd8e-137">Select the **Commodity code category hierarchy type for product classification**.</span></span>  
6. <span data-ttu-id="6dd8e-138">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Kategorihierarki**.</span><span class="sxs-lookup"><span data-stu-id="6dd8e-138">In the **Category hierarchy** field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="6dd8e-139">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="6dd8e-139">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="6dd8e-140">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="6dd8e-140">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="6dd8e-141">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="6dd8e-141">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]