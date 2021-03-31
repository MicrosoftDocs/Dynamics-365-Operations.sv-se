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
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d580d323409d84bab66dc03d39e084f5ee0cfc64
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5218499"
---
# <a name="create-a-product-master"></a><span data-ttu-id="490fc-103">Skapa en produktmall</span><span class="sxs-lookup"><span data-stu-id="490fc-103">Create a product master</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="490fc-104">Skapa en produktmall för de fördefinierade varianterna.</span><span class="sxs-lookup"><span data-stu-id="490fc-104">Create a product master for the predefined variants.</span></span> <span data-ttu-id="490fc-105">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="490fc-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="490fc-106">Den här proceduren är avsedd för produktplaneraren.</span><span class="sxs-lookup"><span data-stu-id="490fc-106">This procedure is intended for the product designer.</span></span>


## <a name="create-a-new-product-master"></a><span data-ttu-id="490fc-107">Skapa en ny produktmall</span><span class="sxs-lookup"><span data-stu-id="490fc-107">Create a new product master</span></span>
1. <span data-ttu-id="490fc-108">Gå till **Navigeringsfönstret > Moduler > Produktinformationshantering > Produkter > Produktmallar**.</span><span class="sxs-lookup"><span data-stu-id="490fc-108">Go to **Navigation pane > Modules > Product information management > Products > Product masters**.</span></span>
2. <span data-ttu-id="490fc-109">Klicka på **Ny**.</span><span class="sxs-lookup"><span data-stu-id="490fc-109">Click **New**.</span></span>
3. <span data-ttu-id="490fc-110">Skriv ett värde i fältet **Produktnummer**.</span><span class="sxs-lookup"><span data-stu-id="490fc-110">In the **Product number** field, type a value.</span></span> <span data-ttu-id="490fc-111">Numret måste vara unikt.</span><span class="sxs-lookup"><span data-stu-id="490fc-111">The number must be unique.</span></span> <span data-ttu-id="490fc-112">En nummerserie kan ställas in för fältet **Produktnummer**.</span><span class="sxs-lookup"><span data-stu-id="490fc-112">A number sequence can be set for the **Product number** field.</span></span> <span data-ttu-id="490fc-113">I det här fallet måste användaren inte ange något värde.</span><span class="sxs-lookup"><span data-stu-id="490fc-113">In this case, the user doesn't have to enter a value.</span></span>
4. <span data-ttu-id="490fc-114">Skriv ett värde i fältet **Produktnamn**.</span><span class="sxs-lookup"><span data-stu-id="490fc-114">In the **Product name** field, type a value.</span></span> <span data-ttu-id="490fc-115">Ange ett beskrivande namn på produkten.</span><span class="sxs-lookup"><span data-stu-id="490fc-115">Enter a descriptive product name.</span></span> <span data-ttu-id="490fc-116">Värdet hämtas som standard i söknamnet, men det kan ändras av användaren.</span><span class="sxs-lookup"><span data-stu-id="490fc-116">The value defaults to the search name, but this can be changed by the user.</span></span>
5. <span data-ttu-id="490fc-117">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Produktdimensionsgrupp**.</span><span class="sxs-lookup"><span data-stu-id="490fc-117">In the **Product dimension group** field, click the drop-down button to open the lookup.</span></span> <span data-ttu-id="490fc-118">Produktdimensionsgruppen bestämmer vilken av de 4 produktdimensionerna som kan användas för att skapa produktvarianter.</span><span class="sxs-lookup"><span data-stu-id="490fc-118">The product dimension group determines which of the 4 product dimensions that can be used to create product variants.</span></span> <span data-ttu-id="490fc-119">I det här exemplet används en grupp med färg och storlek.</span><span class="sxs-lookup"><span data-stu-id="490fc-119">This example uses a group with color and size.</span></span>
6. <span data-ttu-id="490fc-120">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="490fc-120">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="490fc-121">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="490fc-121">In the list, click the link in the selected row.</span></span> <span data-ttu-id="490fc-122">Standardinställda **konfigurationsteknik** är den fördefinierade varianten.</span><span class="sxs-lookup"><span data-stu-id="490fc-122">The default **Configuration technology** is 'Predefined variant'.</span></span> <span data-ttu-id="490fc-123">Denna används för det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="490fc-123">This will be used for this example.</span></span>
8. <span data-ttu-id="490fc-124">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="490fc-124">Click **OK**.</span></span>

## <a name="select-product-dimension-groups"></a><span data-ttu-id="490fc-125">Välj produktdimensionsgrupper</span><span class="sxs-lookup"><span data-stu-id="490fc-125">Select product dimension groups</span></span>
1. <span data-ttu-id="490fc-126">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Färggrupp**.</span><span class="sxs-lookup"><span data-stu-id="490fc-126">In the **Color group** field, click the drop-down button to open the lookup.</span></span>
2. <span data-ttu-id="490fc-127">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="490fc-127">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="490fc-128">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="490fc-128">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="490fc-129">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Storleksgrupp**.</span><span class="sxs-lookup"><span data-stu-id="490fc-129">In the **Size group** field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="490fc-130">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="490fc-130">In the list, find and select the desired record.</span></span>
6. <span data-ttu-id="490fc-131">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="490fc-131">In the list, click the link in the selected row.</span></span>

## <a name="add-dimension-groups"></a><span data-ttu-id="490fc-132">Lägg till dimensionsgrupper</span><span class="sxs-lookup"><span data-stu-id="490fc-132">Add dimension groups</span></span>
1. <span data-ttu-id="490fc-133">I **Åtgärdsfönstret**, klicka på **Produkt**.</span><span class="sxs-lookup"><span data-stu-id="490fc-133">On the **Action Pane**, click **Product**.</span></span>
2. <span data-ttu-id="490fc-134">Klicka på **Dimensionsgrupper** för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="490fc-134">Click **Dimension groups** to open the drop dialog.</span></span>
3. <span data-ttu-id="490fc-135">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Lagringsdimensionsgrupp**.</span><span class="sxs-lookup"><span data-stu-id="490fc-135">In the **Storage dimension group** field, click the drop-down button to open the lookup.</span></span> <span data-ttu-id="490fc-136">Lagringsdimensioner bestämmer hur artiklar lagras och tas från lagret.</span><span class="sxs-lookup"><span data-stu-id="490fc-136">The storage dimensions help you control how items are stored and taken from inventory.</span></span> <span data-ttu-id="490fc-137">Till exempel kan en lagringsdimension omfatta webbplats och lagerställe.</span><span class="sxs-lookup"><span data-stu-id="490fc-137">For example, a storage dimension can include Site and Warehouse.</span></span>
4. <span data-ttu-id="490fc-138">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="490fc-138">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="490fc-139">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="490fc-139">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="490fc-140">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Spårningsdimensionsgrupp**.</span><span class="sxs-lookup"><span data-stu-id="490fc-140">In the **Tracking dimension group** field, click the drop-down button to open the lookup.</span></span> <span data-ttu-id="490fc-141">Spårningsdimensionsgruppen avgör vilka spårningsdimensioner du kan lägga till för en produkt.</span><span class="sxs-lookup"><span data-stu-id="490fc-141">The tracking dimension group determines which tracking dimensions you can add to a product.</span></span> <span data-ttu-id="490fc-142">Batchnummer och serienummer används till exempel för att spåra lagerartiklar.</span><span class="sxs-lookup"><span data-stu-id="490fc-142">For example, the batch number and serial number are used to track inventory items.</span></span>
7. <span data-ttu-id="490fc-143">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="490fc-143">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="490fc-144">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="490fc-144">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="490fc-145">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="490fc-145">Click **OK**.</span></span>
10. <span data-ttu-id="490fc-146">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="490fc-146">Click **Save**.</span></span>
11. <span data-ttu-id="490fc-147">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="490fc-147">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]