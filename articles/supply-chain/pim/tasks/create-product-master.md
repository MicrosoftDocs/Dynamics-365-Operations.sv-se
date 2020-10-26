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
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fdb30b46a0e5a6d4fac997588dd47148f2664c03
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/10/2020
ms.locfileid: "3986105"
---
# <a name="create-a-product-master"></a><span data-ttu-id="a5121-103">Skapa en produktmall</span><span class="sxs-lookup"><span data-stu-id="a5121-103">Create a product master</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a5121-104">Skapa en produktmall för de fördefinierade varianterna.</span><span class="sxs-lookup"><span data-stu-id="a5121-104">Create a product master for the predefined variants.</span></span> <span data-ttu-id="a5121-105">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="a5121-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="a5121-106">Den här proceduren är avsedd för produktplaneraren.</span><span class="sxs-lookup"><span data-stu-id="a5121-106">This procedure is intended for the product designer.</span></span>


## <a name="create-a-new-product-master"></a><span data-ttu-id="a5121-107">Skapa en ny produktmall</span><span class="sxs-lookup"><span data-stu-id="a5121-107">Create a new product master</span></span>
1. <span data-ttu-id="a5121-108">Gå till **Navigeringsfönstret > Moduler > Produktinformationshantering > Produkter > Produktmallar**.</span><span class="sxs-lookup"><span data-stu-id="a5121-108">Go to **Navigation pane > Modules > Product information management > Products > Product masters**.</span></span>
2. <span data-ttu-id="a5121-109">Klicka på **Ny**.</span><span class="sxs-lookup"><span data-stu-id="a5121-109">Click **New**.</span></span>
3. <span data-ttu-id="a5121-110">Skriv ett värde i fältet **Produktnummer**.</span><span class="sxs-lookup"><span data-stu-id="a5121-110">In the **Product number** field, type a value.</span></span> <span data-ttu-id="a5121-111">Numret måste vara unikt.</span><span class="sxs-lookup"><span data-stu-id="a5121-111">The number must be unique.</span></span> <span data-ttu-id="a5121-112">En nummerserie kan ställas in för fältet **Produktnummer**.</span><span class="sxs-lookup"><span data-stu-id="a5121-112">A number sequence can be set for the **Product number** field.</span></span> <span data-ttu-id="a5121-113">I det här fallet måste användaren inte ange något värde.</span><span class="sxs-lookup"><span data-stu-id="a5121-113">In this case, the user doesn't have to enter a value.</span></span>
4. <span data-ttu-id="a5121-114">Skriv ett värde i fältet **Produktnamn**.</span><span class="sxs-lookup"><span data-stu-id="a5121-114">In the **Product name** field, type a value.</span></span> <span data-ttu-id="a5121-115">Ange ett beskrivande namn på produkten.</span><span class="sxs-lookup"><span data-stu-id="a5121-115">Enter a descriptive product name.</span></span> <span data-ttu-id="a5121-116">Värdet hämtas som standard i söknamnet, men det kan ändras av användaren.</span><span class="sxs-lookup"><span data-stu-id="a5121-116">The value defaults to the search name, but this can be changed by the user.</span></span>
5. <span data-ttu-id="a5121-117">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Produktdimensionsgrupp**.</span><span class="sxs-lookup"><span data-stu-id="a5121-117">In the **Product dimension group** field, click the drop-down button to open the lookup.</span></span> <span data-ttu-id="a5121-118">Produktdimensionsgruppen bestämmer vilken av de 4 produktdimensionerna som kan användas för att skapa produktvarianter.</span><span class="sxs-lookup"><span data-stu-id="a5121-118">The product dimension group determines which of the 4 product dimensions that can be used to create product variants.</span></span> <span data-ttu-id="a5121-119">I det här exemplet används en grupp med färg och storlek.</span><span class="sxs-lookup"><span data-stu-id="a5121-119">This example uses a group with color and size.</span></span>
6. <span data-ttu-id="a5121-120">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="a5121-120">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="a5121-121">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="a5121-121">In the list, click the link in the selected row.</span></span> <span data-ttu-id="a5121-122">Standardinställda **konfigurationsteknik** är den fördefinierade varianten.</span><span class="sxs-lookup"><span data-stu-id="a5121-122">The default **Configuration technology** is 'Predefined variant'.</span></span> <span data-ttu-id="a5121-123">Denna används för det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="a5121-123">This will be used for this example.</span></span>
8. <span data-ttu-id="a5121-124">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="a5121-124">Click **OK**.</span></span>

## <a name="select-product-dimension-groups"></a><span data-ttu-id="a5121-125">Välj produktdimensionsgrupper</span><span class="sxs-lookup"><span data-stu-id="a5121-125">Select product dimension groups</span></span>
1. <span data-ttu-id="a5121-126">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Färggrupp**.</span><span class="sxs-lookup"><span data-stu-id="a5121-126">In the **Color group** field, click the drop-down button to open the lookup.</span></span>
2. <span data-ttu-id="a5121-127">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="a5121-127">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="a5121-128">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="a5121-128">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="a5121-129">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Storleksgrupp**.</span><span class="sxs-lookup"><span data-stu-id="a5121-129">In the **Size group** field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="a5121-130">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="a5121-130">In the list, find and select the desired record.</span></span>
6. <span data-ttu-id="a5121-131">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="a5121-131">In the list, click the link in the selected row.</span></span>

## <a name="add-dimension-groups"></a><span data-ttu-id="a5121-132">Lägg till dimensionsgrupper</span><span class="sxs-lookup"><span data-stu-id="a5121-132">Add dimension groups</span></span>
1. <span data-ttu-id="a5121-133">I **Åtgärdsfönstret**, klicka på **Produkt**.</span><span class="sxs-lookup"><span data-stu-id="a5121-133">On the **Action Pane**, click **Product**.</span></span>
2. <span data-ttu-id="a5121-134">Klicka på **Dimensionsgrupper** för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="a5121-134">Click **Dimension groups** to open the drop dialog.</span></span>
3. <span data-ttu-id="a5121-135">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Lagringsdimensionsgrupp**.</span><span class="sxs-lookup"><span data-stu-id="a5121-135">In the **Storage dimension group** field, click the drop-down button to open the lookup.</span></span> <span data-ttu-id="a5121-136">Lagringsdimensioner bestämmer hur artiklar lagras och tas från lagret.</span><span class="sxs-lookup"><span data-stu-id="a5121-136">The storage dimensions help you control how items are stored and taken from inventory.</span></span> <span data-ttu-id="a5121-137">Till exempel kan en lagringsdimension omfatta webbplats och lagerställe.</span><span class="sxs-lookup"><span data-stu-id="a5121-137">For example, a storage dimension can include Site and Warehouse.</span></span>
4. <span data-ttu-id="a5121-138">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="a5121-138">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="a5121-139">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="a5121-139">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="a5121-140">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Spårningsdimensionsgrupp**.</span><span class="sxs-lookup"><span data-stu-id="a5121-140">In the **Tracking dimension group** field, click the drop-down button to open the lookup.</span></span> <span data-ttu-id="a5121-141">Spårningsdimensionsgruppen avgör vilka spårningsdimensioner du kan lägga till för en produkt.</span><span class="sxs-lookup"><span data-stu-id="a5121-141">The tracking dimension group determines which tracking dimensions you can add to a product.</span></span> <span data-ttu-id="a5121-142">Batchnummer och serienummer används till exempel för att spåra lagerartiklar.</span><span class="sxs-lookup"><span data-stu-id="a5121-142">For example, the batch number and serial number are used to track inventory items.</span></span>
7. <span data-ttu-id="a5121-143">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="a5121-143">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="a5121-144">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="a5121-144">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="a5121-145">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="a5121-145">Click **OK**.</span></span>
10. <span data-ttu-id="a5121-146">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="a5121-146">Click **Save**.</span></span>
11. <span data-ttu-id="a5121-147">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="a5121-147">Close the page.</span></span>

