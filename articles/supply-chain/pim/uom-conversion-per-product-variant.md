---
title: Måttenhetskonvertering per produktvariant
description: Det här avsnittet beskriver hur måttenhetskonvertering kan ställas in på produktvarianter.
author: johanhoffmann
manager: AnnBe
ms.date: 01/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: UnitOfMeasureConversion
ROBOTS: noindex, nofollow
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-04-01
ms.dyn365.ops.version: 10
ms.openlocfilehash: c8181f0bda9b781a6c2b0feb0aba1beb51bfea65
ms.sourcegitcommit: af36eb17b36092a3101bbfc96486b25036676558
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/06/2020
ms.locfileid: "2935109"
---
# <a name="unit-of-measure-conversion-per-product-variant"></a><span data-ttu-id="a3c0b-103">Måttenhetskonvertering per produktvariant</span><span class="sxs-lookup"><span data-stu-id="a3c0b-103">Unit of measure conversion per product variant</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a3c0b-104">Det här avsnittet beskriver hur måttenhetskonvertering kan ställas in på produktvarianter.</span><span class="sxs-lookup"><span data-stu-id="a3c0b-104">This topic explains how unit of measure conversions can be set up on product variants.</span></span> <span data-ttu-id="a3c0b-105">Den innehåller ett exempel på inställningarna.</span><span class="sxs-lookup"><span data-stu-id="a3c0b-105">It includes an example of the setup.</span></span>

<span data-ttu-id="a3c0b-106">Den här funktionen gör det möjligt för företag att definiera olika enhetskonverteringar mellan varianter av samma produkt.</span><span class="sxs-lookup"><span data-stu-id="a3c0b-106">This feature makes it possible for companies to define different unit conversion between the variants of the same product.</span></span> <span data-ttu-id="a3c0b-107">Följande exempel används i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="a3c0b-107">The following example is used in this topic.</span></span> <span data-ttu-id="a3c0b-108">Ett företag säljer t-shirts i storlek Small, Medium, Large och Extra large.</span><span class="sxs-lookup"><span data-stu-id="a3c0b-108">A company sells T-shirts in sizes Small, Medium, Large, and Extra-Large.</span></span> <span data-ttu-id="a3c0b-109">T-shirten definieras som en produkt och de olika storlekarna definieras som varianter av produkten.</span><span class="sxs-lookup"><span data-stu-id="a3c0b-109">The T-shirt is defined as a product, and the different sizes are defined as variants of the product.</span></span> <span data-ttu-id="a3c0b-110">T-shirts förpackas i lådor och det kan finnas fem T-shirts i en låda, med undantag för Extra large som endast kan fyra T-shirts.</span><span class="sxs-lookup"><span data-stu-id="a3c0b-110">The T-shirts are packed in boxes and there can be five T-shirts in a box, except for the Extra-Large size where there is only space for four T-shirts.</span></span> <span data-ttu-id="a3c0b-111">Företaget vill spåra olika varianter av T-shirts i enheten **enheter** men säljer T-shirts i enheten **lådor**.</span><span class="sxs-lookup"><span data-stu-id="a3c0b-111">The company wants to track the different variants of the T-shirts in the unit **Pieces** but is selling the T-shirts in the unit **Boxes**.</span></span> <span data-ttu-id="a3c0b-112">Konverteringen mellan lagerenheten och försäljningsenheten är 1 låda = 5 enheter utom varianten Extra large där konverteringen är 1 låda = 4 enheter.</span><span class="sxs-lookup"><span data-stu-id="a3c0b-112">The conversion between the inventory unit and the sales unit is 1 Box = 5 Pieces, except for the variant Extra-Large, where the conversion is 1 Box = 4 Pieces.</span></span>

### <a name="set-up-a-product-for-unit-conversion-per-variant"></a><span data-ttu-id="a3c0b-113">Konfigurera en produkt för enhetskonvertering per variant</span><span class="sxs-lookup"><span data-stu-id="a3c0b-113">Set up a product for unit conversion per variant</span></span>

<span data-ttu-id="a3c0b-114">Produktvarianter kan bara skapas för produkter av **undertypen Produkt**: **produktmall**.</span><span class="sxs-lookup"><span data-stu-id="a3c0b-114">Product variants can only be created for products of **Product subtype**: **Product master**.</span></span> <span data-ttu-id="a3c0b-115">Mer information finns i [Skapa en produktmall](tasks/create-product-master.md).</span><span class="sxs-lookup"><span data-stu-id="a3c0b-115">For more information, see [Create a product master](tasks/create-product-master.md).</span></span>

<span data-ttu-id="a3c0b-116">Funktionen är inte aktiverad för produkter som har ställts in för faktisk/nominell vikt-processer.</span><span class="sxs-lookup"><span data-stu-id="a3c0b-116">The feature is not enabled for products that are set up for Catch Weight processes.</span></span> 

<span data-ttu-id="a3c0b-117">När produktmallen med frisläppta produktvarianter skapas kan enhetskonverteringar per varianter ställas in.</span><span class="sxs-lookup"><span data-stu-id="a3c0b-117">When the product master with released products variants is created, unit conversions per variants can be set up.</span></span> <span data-ttu-id="a3c0b-118">Du hittar alternativet för att öppna sidan enhetskonvertering i samband med en produkt eller en produktvariant på följande sidor.</span><span class="sxs-lookup"><span data-stu-id="a3c0b-118">You can find the menu item for opening the unit conversion page in context of a product or a product variant on the following pages.</span></span>

-   <span data-ttu-id="a3c0b-119">Sidan **Produktinformation**</span><span class="sxs-lookup"><span data-stu-id="a3c0b-119">**Product details** page</span></span>
-   <span data-ttu-id="a3c0b-120">Sidan **Uppgifter om frisläppta produkter**</span><span class="sxs-lookup"><span data-stu-id="a3c0b-120">**Released products details** page</span></span>
-   <span data-ttu-id="a3c0b-121">Sidan **Frisläppta produktvarianter**</span><span class="sxs-lookup"><span data-stu-id="a3c0b-121">**Released product variants** page</span></span>

<span data-ttu-id="a3c0b-122">När du öppnar sidan **Enhetskonvertering** i samband med en produktmall eller frisläppt produktvariant kan du välja om du vill ställa in enhetskonvertering för produkten eller för en produktvariant.</span><span class="sxs-lookup"><span data-stu-id="a3c0b-122">When you open the **Unit conversion** page in context of a product master or released product variant, you can select if you want to set up the unit conversion for the product or for a product variant.</span></span> <span data-ttu-id="a3c0b-123">Du gör detta genom att välja antingen **Produktvariant** eller **Produkt** i fältet **Skapa konvertering för**.</span><span class="sxs-lookup"><span data-stu-id="a3c0b-123">You do that by selecting either **Product variant** or **Product** in the **Create conversion for** field.</span></span>

### <a name="product-variant"></a><span data-ttu-id="a3c0b-124">Produktvariant</span><span class="sxs-lookup"><span data-stu-id="a3c0b-124">Product variant</span></span>

<span data-ttu-id="a3c0b-125">Om du väljer **Produktvariant** kan du sedan välja vilken variant du vill ställa in enhetskonvertering i fältet **Produktvariant**.</span><span class="sxs-lookup"><span data-stu-id="a3c0b-125">If you select **Product variant,** then you can select for which variant you want to set up the unit conversion in the **Product variant** field.</span></span>

### <a name="product"></a><span data-ttu-id="a3c0b-126">Produkt</span><span class="sxs-lookup"><span data-stu-id="a3c0b-126">Product</span></span>

<span data-ttu-id="a3c0b-127">Om du väljer **Produkt** kan du ställa in en enhetskonvertering för produktmallen.</span><span class="sxs-lookup"><span data-stu-id="a3c0b-127">If you select **Product**, then you can set up a unit conversion for the product master.</span></span> <span data-ttu-id="a3c0b-128">Denna enhetskonvertering gäller för alla produktvarianter utan definierad enhetskonvertering.</span><span class="sxs-lookup"><span data-stu-id="a3c0b-128">This unit conversion will apply for all product variants with no defined unit conversion.</span></span>

### <a name="example"></a><span data-ttu-id="a3c0b-129">Exempel</span><span class="sxs-lookup"><span data-stu-id="a3c0b-129">Example</span></span>

<span data-ttu-id="a3c0b-130">En produktmall **T-Shirt** har fyra frisläppta produktvarianter Small, Medium, Large och X-Large.</span><span class="sxs-lookup"><span data-stu-id="a3c0b-130">A product master, **T-Shirt**, has four released products variants Small, Medium, Large, and X-Large.</span></span> <span data-ttu-id="a3c0b-131">T-shirts förpackas i lådor och det kan finnas fem T-shirts i en låda, med undantag för Extra large som endast kan fyra T-shirts.</span><span class="sxs-lookup"><span data-stu-id="a3c0b-131">The T-shirts are packed in boxes and there can be five T-shirts in a box, except for the Extra-large size where there is only space for four T-shirts.</span></span>

<span data-ttu-id="a3c0b-132">Öppna först sidan **Enhetskonvertering** från sidan Information om frisläppt produkt för **T-shirt.**</span><span class="sxs-lookup"><span data-stu-id="a3c0b-132">First, open the **Unit conversion** page from the Release product details page for **T-shirt.**</span></span>

<span data-ttu-id="a3c0b-133">På sidan **Enhetskonvertering**, ställ in enhetskonvertering för den frisläppta produktvarianten X-Large.</span><span class="sxs-lookup"><span data-stu-id="a3c0b-133">On the **Unit conversion** page, set up the unit conversion for the release product variant X-Large.</span></span>

| <span data-ttu-id="a3c0b-134">**Fält**</span><span class="sxs-lookup"><span data-stu-id="a3c0b-134">**Field**</span></span>             | <span data-ttu-id="a3c0b-135">**Inställning**</span><span class="sxs-lookup"><span data-stu-id="a3c0b-135">**Setting**</span></span>             |
|-----------------------|-------------------------|
| <span data-ttu-id="a3c0b-136">Skapa konvertering för</span><span class="sxs-lookup"><span data-stu-id="a3c0b-136">Create conversion for</span></span> | <span data-ttu-id="a3c0b-137">Produktvariant</span><span class="sxs-lookup"><span data-stu-id="a3c0b-137">Product variant</span></span>         |
| <span data-ttu-id="a3c0b-138">Produktvariant</span><span class="sxs-lookup"><span data-stu-id="a3c0b-138">Product variant</span></span>       | <span data-ttu-id="a3c0b-139">T-Shirt : : X-Large : :</span><span class="sxs-lookup"><span data-stu-id="a3c0b-139">T-Shirt : : X-Large : :</span></span> |
| <span data-ttu-id="a3c0b-140">Från enhet</span><span class="sxs-lookup"><span data-stu-id="a3c0b-140">From unit</span></span>             | <span data-ttu-id="a3c0b-141">Lådor</span><span class="sxs-lookup"><span data-stu-id="a3c0b-141">Boxes</span></span>                   |
| <span data-ttu-id="a3c0b-142">Faktor</span><span class="sxs-lookup"><span data-stu-id="a3c0b-142">Factor</span></span>                | <span data-ttu-id="a3c0b-143">4</span><span class="sxs-lookup"><span data-stu-id="a3c0b-143">4</span></span>                       |
| <span data-ttu-id="a3c0b-144">Till enhet</span><span class="sxs-lookup"><span data-stu-id="a3c0b-144">To Unit</span></span>               | <span data-ttu-id="a3c0b-145">Antal</span><span class="sxs-lookup"><span data-stu-id="a3c0b-145">Pieces</span></span>                  |

<span data-ttu-id="a3c0b-146">De frisläppta produktvarianten Small, Medium och Large har samma enhetskonvertering mellan enheten Låda och Enheter, vilket innebär att du kan definiera enhetskonvertering för dessa produktvarianter för produktmallen.</span><span class="sxs-lookup"><span data-stu-id="a3c0b-146">The Released product variants Small, Medium, and Large have the same unit conversion between the unit Box and Pieces, which means that you can define the unit conversion for these product variants on the product master.</span></span>

| <span data-ttu-id="a3c0b-147">**Fält**</span><span class="sxs-lookup"><span data-stu-id="a3c0b-147">**Field**</span></span>             | <span data-ttu-id="a3c0b-148">**Inställning**</span><span class="sxs-lookup"><span data-stu-id="a3c0b-148">**Setting**</span></span> |
|-----------------------|-------------|
| <span data-ttu-id="a3c0b-149">Skapa konvertering för</span><span class="sxs-lookup"><span data-stu-id="a3c0b-149">Create conversion for</span></span> | <span data-ttu-id="a3c0b-150">Produkt</span><span class="sxs-lookup"><span data-stu-id="a3c0b-150">Product</span></span>     |
| <span data-ttu-id="a3c0b-151">Produkt</span><span class="sxs-lookup"><span data-stu-id="a3c0b-151">Product</span></span>               | <span data-ttu-id="a3c0b-152">T-shirt</span><span class="sxs-lookup"><span data-stu-id="a3c0b-152">T-Shirt</span></span>     |
| <span data-ttu-id="a3c0b-153">Från enhet</span><span class="sxs-lookup"><span data-stu-id="a3c0b-153">From unit</span></span>             | <span data-ttu-id="a3c0b-154">Lådor</span><span class="sxs-lookup"><span data-stu-id="a3c0b-154">Boxes</span></span>       |
| <span data-ttu-id="a3c0b-155">Faktor</span><span class="sxs-lookup"><span data-stu-id="a3c0b-155">Factor</span></span>                | <span data-ttu-id="a3c0b-156">5</span><span class="sxs-lookup"><span data-stu-id="a3c0b-156">5</span></span>           |
| <span data-ttu-id="a3c0b-157">Till enhet</span><span class="sxs-lookup"><span data-stu-id="a3c0b-157">To Unit</span></span>               | <span data-ttu-id="a3c0b-158">Antal</span><span class="sxs-lookup"><span data-stu-id="a3c0b-158">Pieces</span></span>      |

### <a name="using-excel-to-update-the-unit-conversions"></a><span data-ttu-id="a3c0b-159">Uppdatera enhetskonverteringarna med Excel</span><span class="sxs-lookup"><span data-stu-id="a3c0b-159">Using Excel to update the unit conversions</span></span>

<span data-ttu-id="a3c0b-160">Om en produkt har många produktvarianter med olika enhetskonverteringar, är det en bra idé att exportera enhetskonverteringar från sidan **Enhetskonvertering** till ett Excel-kalkylblad, uppdatera konverteringar och publicera tillbaka dem i Supply Chain Mangement.</span><span class="sxs-lookup"><span data-stu-id="a3c0b-160">If a product has many product variants with different unit conversions, it's a good idea to export the unit conversions from the **Unit conversion** page to an Excel spreadsheet, update the conversions, and then publish them back to Supply Chain Mangement.</span></span>

<span data-ttu-id="a3c0b-161">Alternativet för att exportera till Excel och publicera ändringarna tillbaka till Supply Chain Mangement aktiveras från menyobjektet **Öppna i Microsoft Office** i åtgärdsfönstret på sidan **Enhetskonverteringar**.</span><span class="sxs-lookup"><span data-stu-id="a3c0b-161">The option to export to Excel and publish the edits back to Supply Chain Mangement is enabled from the **Open in Microsoft office** menu item on the Action Pane on the **Unit conversion** page.</span></span>
