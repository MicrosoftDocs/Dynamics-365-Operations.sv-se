---
title: Skapa en produktmall
description: Skapa en produktmall för de fördefinierade varianterna.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductListPage, EcoResProductCreate, EcoResProductDetails, EcoResProductInventoryDimensionGroups
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 25c1a50f99070953c86dbff897757fd959beec79
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3208258"
---
# <a name="create-a-product-master"></a><span data-ttu-id="39eb1-103">Skapa en produktmall</span><span class="sxs-lookup"><span data-stu-id="39eb1-103">Create a product master</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="39eb1-104">Skapa en produktmall för de fördefinierade varianterna.</span><span class="sxs-lookup"><span data-stu-id="39eb1-104">Create a product master for the predefined variants.</span></span> <span data-ttu-id="39eb1-105">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="39eb1-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="39eb1-106">Den här proceduren är avsedd för produktplaneraren.</span><span class="sxs-lookup"><span data-stu-id="39eb1-106">This procedure is intended for the product designer.</span></span>


## <a name="create-a-new-product-master"></a><span data-ttu-id="39eb1-107">Skapa en ny produktmall</span><span class="sxs-lookup"><span data-stu-id="39eb1-107">Create a new product master</span></span>
1. <span data-ttu-id="39eb1-108">Gå till **Navigeringsfönstret > Moduler > Produktinformationshantering > Produkter > Produktmallar**.</span><span class="sxs-lookup"><span data-stu-id="39eb1-108">Go to **Navigation pane > Modules > Product information management > Products > Product masters**.</span></span>
2. <span data-ttu-id="39eb1-109">Klicka på **Ny**.</span><span class="sxs-lookup"><span data-stu-id="39eb1-109">Click **New**.</span></span>
3. <span data-ttu-id="39eb1-110">Skriv ett värde i fältet **Produktnummer**.</span><span class="sxs-lookup"><span data-stu-id="39eb1-110">In the **Product number** field, type a value.</span></span> <span data-ttu-id="39eb1-111">Numret måste vara unikt.</span><span class="sxs-lookup"><span data-stu-id="39eb1-111">The number must be unique.</span></span> <span data-ttu-id="39eb1-112">En nummerserie kan ställas in för fältet **Produktnummer**.</span><span class="sxs-lookup"><span data-stu-id="39eb1-112">A number sequence can be set for the **Product number** field.</span></span> <span data-ttu-id="39eb1-113">I det här fallet måste användaren inte ange något värde.</span><span class="sxs-lookup"><span data-stu-id="39eb1-113">In this case, the user doesn't have to enter a value.</span></span>
4. <span data-ttu-id="39eb1-114">Skriv ett värde i fältet **Produktnamn**.</span><span class="sxs-lookup"><span data-stu-id="39eb1-114">In the **Product name** field, type a value.</span></span> <span data-ttu-id="39eb1-115">Ange ett beskrivande namn på produkten.</span><span class="sxs-lookup"><span data-stu-id="39eb1-115">Enter a descriptive product name.</span></span> <span data-ttu-id="39eb1-116">Värdet hämtas som standard i söknamnet, men det kan ändras av användaren.</span><span class="sxs-lookup"><span data-stu-id="39eb1-116">The value defaults to the search name, but this can be changed by the user.</span></span>
5. <span data-ttu-id="39eb1-117">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Produktdimensionsgrupp**.</span><span class="sxs-lookup"><span data-stu-id="39eb1-117">In the **Product dimension group** field, click the drop-down button to open the lookup.</span></span> <span data-ttu-id="39eb1-118">Produktdimensionsgruppen bestämmer vilken av de 4 produktdimensionerna som kan användas för att skapa produktvarianter.</span><span class="sxs-lookup"><span data-stu-id="39eb1-118">The product dimension group determines which of the 4 product dimensions that can be used to create product variants.</span></span> <span data-ttu-id="39eb1-119">I det här exemplet används en grupp med färg och storlek.</span><span class="sxs-lookup"><span data-stu-id="39eb1-119">This example uses a group with color and size.</span></span>
6. <span data-ttu-id="39eb1-120">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="39eb1-120">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="39eb1-121">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="39eb1-121">In the list, click the link in the selected row.</span></span> <span data-ttu-id="39eb1-122">Standardinställda **konfigurationsteknik** är den fördefinierade varianten.</span><span class="sxs-lookup"><span data-stu-id="39eb1-122">The default **Configuration technology** is 'Predefined variant'.</span></span> <span data-ttu-id="39eb1-123">Denna används för det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="39eb1-123">This will be used for this example.</span></span>
8. <span data-ttu-id="39eb1-124">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="39eb1-124">Click **OK**.</span></span>

## <a name="select-product-dimension-groups"></a><span data-ttu-id="39eb1-125">Välj produktdimensionsgrupper</span><span class="sxs-lookup"><span data-stu-id="39eb1-125">Select product dimension groups</span></span>
1. <span data-ttu-id="39eb1-126">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Färggrupp**.</span><span class="sxs-lookup"><span data-stu-id="39eb1-126">In the **Color group** field, click the drop-down button to open the lookup.</span></span>
2. <span data-ttu-id="39eb1-127">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="39eb1-127">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="39eb1-128">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="39eb1-128">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="39eb1-129">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Storleksgrupp**.</span><span class="sxs-lookup"><span data-stu-id="39eb1-129">In the **Size group** field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="39eb1-130">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="39eb1-130">In the list, find and select the desired record.</span></span>
6. <span data-ttu-id="39eb1-131">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="39eb1-131">In the list, click the link in the selected row.</span></span>

## <a name="add-dimension-groups"></a><span data-ttu-id="39eb1-132">Lägg till dimensionsgrupper</span><span class="sxs-lookup"><span data-stu-id="39eb1-132">Add dimension groups</span></span>
1. <span data-ttu-id="39eb1-133">I **Åtgärdsfönstret**, klicka på **Produkt**.</span><span class="sxs-lookup"><span data-stu-id="39eb1-133">On the **Action Pane**, click **Product**.</span></span>
2. <span data-ttu-id="39eb1-134">Klicka på **Dimensionsgrupper** för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="39eb1-134">Click **Dimension groups** to open the drop dialog.</span></span>
3. <span data-ttu-id="39eb1-135">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Lagringsdimensionsgrupp**.</span><span class="sxs-lookup"><span data-stu-id="39eb1-135">In the **Storage dimension group** field, click the drop-down button to open the lookup.</span></span> <span data-ttu-id="39eb1-136">Lagringsdimensioner bestämmer hur artiklar lagras och tas från lagret.</span><span class="sxs-lookup"><span data-stu-id="39eb1-136">The storage dimensions help you control how items are stored and taken from inventory.</span></span> <span data-ttu-id="39eb1-137">Till exempel kan en lagringsdimension omfatta webbplats och lagerställe.</span><span class="sxs-lookup"><span data-stu-id="39eb1-137">For example, a storage dimension can include Site and Warehouse.</span></span>
4. <span data-ttu-id="39eb1-138">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="39eb1-138">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="39eb1-139">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="39eb1-139">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="39eb1-140">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Spårningsdimensionsgrupp**.</span><span class="sxs-lookup"><span data-stu-id="39eb1-140">In the **Tracking dimension group** field, click the drop-down button to open the lookup.</span></span> <span data-ttu-id="39eb1-141">Spårningsdimensionsgruppen avgör vilka spårningsdimensioner du kan lägga till för en produkt.</span><span class="sxs-lookup"><span data-stu-id="39eb1-141">The tracking dimension group determines which tracking dimensions you can add to a product.</span></span> <span data-ttu-id="39eb1-142">Batchnummer och serienummer används till exempel för att spåra lagerartiklar.</span><span class="sxs-lookup"><span data-stu-id="39eb1-142">For example, the batch number and serial number are used to track inventory items.</span></span>
7. <span data-ttu-id="39eb1-143">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="39eb1-143">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="39eb1-144">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="39eb1-144">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="39eb1-145">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="39eb1-145">Click **OK**.</span></span>
10. <span data-ttu-id="39eb1-146">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="39eb1-146">Click **Save**.</span></span>
11. <span data-ttu-id="39eb1-147">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="39eb1-147">Close the page.</span></span>

