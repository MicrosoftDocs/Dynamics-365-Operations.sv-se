---
title: Skapa en produktmall
description: Skapa en produktmall för de fördefinierade varianterna.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductListPage, EcoResProductCreate, EcoResProductDetails, EcoResProductInventoryDimensionGroups
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0ea5c240063bf8f98f07f2149d67730b30e5c0e4
ms.sourcegitcommit: 62d66f98d4bbf916e19184506b90055bb68d219f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/28/2019
ms.locfileid: "1924480"
---
# <a name="create-a-product-master"></a><span data-ttu-id="ab084-103">Skapa en produktmall</span><span class="sxs-lookup"><span data-stu-id="ab084-103">Create a product master</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ab084-104">Skapa en produktmall för de fördefinierade varianterna.</span><span class="sxs-lookup"><span data-stu-id="ab084-104">Create a product master for the predefined variants.</span></span> <span data-ttu-id="ab084-105">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="ab084-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="ab084-106">Den här proceduren är avsedd för produktplaneraren.</span><span class="sxs-lookup"><span data-stu-id="ab084-106">This procedure is intended for the product designer.</span></span>


## <a name="create-a-new-product-master"></a><span data-ttu-id="ab084-107">Skapa en ny produktmall</span><span class="sxs-lookup"><span data-stu-id="ab084-107">Create a new product master</span></span>
1. <span data-ttu-id="ab084-108">Gå till **Navigeringsfönstret > Moduler > Produktinformationshantering > Produkter > Produktmallar**.</span><span class="sxs-lookup"><span data-stu-id="ab084-108">Go to **Navigation pane > Modules > Product information management > Products > Product masters**.</span></span>
2. <span data-ttu-id="ab084-109">Klicka på **Ny**.</span><span class="sxs-lookup"><span data-stu-id="ab084-109">Click **New**.</span></span>
3. <span data-ttu-id="ab084-110">Skriv ett värde i fältet **Produktnummer**.</span><span class="sxs-lookup"><span data-stu-id="ab084-110">In the **Product number** field, type a value.</span></span> <span data-ttu-id="ab084-111">Numret måste vara unikt.</span><span class="sxs-lookup"><span data-stu-id="ab084-111">The number must be unique.</span></span> <span data-ttu-id="ab084-112">En nummerserie kan ställas in för fältet **Produktnummer**.</span><span class="sxs-lookup"><span data-stu-id="ab084-112">A number sequence can be set for the **Product number** field.</span></span> <span data-ttu-id="ab084-113">I det här fallet måste användaren inte ange något värde.</span><span class="sxs-lookup"><span data-stu-id="ab084-113">In this case, the user doesn't have to enter a value.</span></span>
4. <span data-ttu-id="ab084-114">Skriv ett värde i fältet **Produktnamn**.</span><span class="sxs-lookup"><span data-stu-id="ab084-114">In the **Product name** field, type a value.</span></span> <span data-ttu-id="ab084-115">Ange ett beskrivande namn på produkten.</span><span class="sxs-lookup"><span data-stu-id="ab084-115">Enter a descriptive product name.</span></span> <span data-ttu-id="ab084-116">Värdet hämtas som standard i söknamnet, men det kan ändras av användaren.</span><span class="sxs-lookup"><span data-stu-id="ab084-116">The value defaults to the search name, but this can be changed by the user.</span></span>
5. <span data-ttu-id="ab084-117">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Produktdimensionsgrupp**.</span><span class="sxs-lookup"><span data-stu-id="ab084-117">In the **Product dimension group** field, click the drop-down button to open the lookup.</span></span> <span data-ttu-id="ab084-118">Produktdimensionsgruppen bestämmer vilken av de 4 produktdimensionerna som kan användas för att skapa produktvarianter.</span><span class="sxs-lookup"><span data-stu-id="ab084-118">The product dimension group determines which of the 4 product dimensions that can be used to create product variants.</span></span> <span data-ttu-id="ab084-119">I det här exemplet används en grupp med färg och storlek.</span><span class="sxs-lookup"><span data-stu-id="ab084-119">This example uses a group with color and size.</span></span>
6. <span data-ttu-id="ab084-120">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="ab084-120">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="ab084-121">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="ab084-121">In the list, click the link in the selected row.</span></span> <span data-ttu-id="ab084-122">Standardinställda **konfigurationsteknik** är den fördefinierade varianten.</span><span class="sxs-lookup"><span data-stu-id="ab084-122">The default **Configuration technology** is 'Predefined variant'.</span></span> <span data-ttu-id="ab084-123">Denna används för det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="ab084-123">This will be used for this example.</span></span>
8. <span data-ttu-id="ab084-124">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="ab084-124">Click **OK**.</span></span>

## <a name="select-product-dimension-groups"></a><span data-ttu-id="ab084-125">Välj produktdimensionsgrupper</span><span class="sxs-lookup"><span data-stu-id="ab084-125">Select product dimension groups</span></span>
1. <span data-ttu-id="ab084-126">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Färggrupp**.</span><span class="sxs-lookup"><span data-stu-id="ab084-126">In the **Color group** field, click the drop-down button to open the lookup.</span></span>
2. <span data-ttu-id="ab084-127">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="ab084-127">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="ab084-128">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="ab084-128">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="ab084-129">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Storleksgrupp**.</span><span class="sxs-lookup"><span data-stu-id="ab084-129">In the **Size group** field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="ab084-130">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="ab084-130">In the list, find and select the desired record.</span></span>
6. <span data-ttu-id="ab084-131">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="ab084-131">In the list, click the link in the selected row.</span></span>

## <a name="add-dimension-groups"></a><span data-ttu-id="ab084-132">Lägg till dimensionsgrupper</span><span class="sxs-lookup"><span data-stu-id="ab084-132">Add dimension groups</span></span>
1. <span data-ttu-id="ab084-133">I **Åtgärdsfönstret**, klicka på **Produkt**.</span><span class="sxs-lookup"><span data-stu-id="ab084-133">On the **Action Pane**, click **Product**.</span></span>
2. <span data-ttu-id="ab084-134">Klicka på **Dimensionsgrupper** för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="ab084-134">Click **Dimension groups** to open the drop dialog.</span></span>
3. <span data-ttu-id="ab084-135">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Lagringsdimensionsgrupp**.</span><span class="sxs-lookup"><span data-stu-id="ab084-135">In the **Storage dimension group** field, click the drop-down button to open the lookup.</span></span> <span data-ttu-id="ab084-136">Lagringsdimensioner bestämmer hur artiklar lagras och tas från lagret.</span><span class="sxs-lookup"><span data-stu-id="ab084-136">The storage dimensions help you control how items are stored and taken from inventory.</span></span> <span data-ttu-id="ab084-137">Till exempel kan en lagringsdimension omfatta webbplats och lagerställe.</span><span class="sxs-lookup"><span data-stu-id="ab084-137">For example, a storage dimension can include Site and Warehouse.</span></span>
4. <span data-ttu-id="ab084-138">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="ab084-138">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="ab084-139">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="ab084-139">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="ab084-140">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Spårningsdimensionsgrupp**.</span><span class="sxs-lookup"><span data-stu-id="ab084-140">In the **Tracking dimension group** field, click the drop-down button to open the lookup.</span></span> <span data-ttu-id="ab084-141">Spårningsdimensionsgruppen avgör vilka spårningsdimensioner du kan lägga till för en produkt.</span><span class="sxs-lookup"><span data-stu-id="ab084-141">The tracking dimension group determines which tracking dimensions you can add to a product.</span></span> <span data-ttu-id="ab084-142">Batchnummer och serienummer används till exempel för att spåra lagerartiklar.</span><span class="sxs-lookup"><span data-stu-id="ab084-142">For example, the batch number and serial number are used to track inventory items.</span></span>
7. <span data-ttu-id="ab084-143">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="ab084-143">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="ab084-144">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="ab084-144">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="ab084-145">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="ab084-145">Click **OK**.</span></span>
10. <span data-ttu-id="ab084-146">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="ab084-146">Click **Save**.</span></span>
11. <span data-ttu-id="ab084-147">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="ab084-147">Close the page.</span></span>

