---
title: Måttenhetskonvertering per produktvariant
description: Det här avsnittet beskriver hur måttenhetskonvertering kan ställas in på produktvarianter.
author: johanhoffmann
manager: tfehr
ms.date: 01/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: UnitOfMeasureConversion
ROBOTS: noindex, nofollow
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-04-01
ms.dyn365.ops.version: 10
ms.openlocfilehash: e50be7fa6fa686a90b2dd5c5200c881e4629f019
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3204503"
---
# <a name="unit-of-measure-conversion-per-product-variant"></a><span data-ttu-id="8922e-103">Måttenhetskonvertering per produktvariant</span><span class="sxs-lookup"><span data-stu-id="8922e-103">Unit of measure conversion per product variant</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8922e-104">Det här avsnittet beskriver hur måttenhetskonvertering kan ställas in på produktvarianter.</span><span class="sxs-lookup"><span data-stu-id="8922e-104">This topic explains how unit of measure conversions can be set up on product variants.</span></span> <span data-ttu-id="8922e-105">Den innehåller ett exempel på inställningarna.</span><span class="sxs-lookup"><span data-stu-id="8922e-105">It includes an example of the setup.</span></span>

<span data-ttu-id="8922e-106">Den här funktionen gör det möjligt för företag att definiera olika enhetskonverteringar mellan varianter av samma produkt.</span><span class="sxs-lookup"><span data-stu-id="8922e-106">This feature makes it possible for companies to define different unit conversion between the variants of the same product.</span></span> <span data-ttu-id="8922e-107">Följande exempel används i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="8922e-107">The following example is used in this topic.</span></span> <span data-ttu-id="8922e-108">Ett företag säljer t-shirts i storlek Small, Medium, Large och Extra large.</span><span class="sxs-lookup"><span data-stu-id="8922e-108">A company sells T-shirts in sizes Small, Medium, Large, and Extra-Large.</span></span> <span data-ttu-id="8922e-109">T-shirten definieras som en produkt och de olika storlekarna definieras som varianter av produkten.</span><span class="sxs-lookup"><span data-stu-id="8922e-109">The T-shirt is defined as a product, and the different sizes are defined as variants of the product.</span></span> <span data-ttu-id="8922e-110">T-shirts förpackas i lådor och det kan finnas fem T-shirts i en låda, med undantag för Extra large som endast kan fyra T-shirts.</span><span class="sxs-lookup"><span data-stu-id="8922e-110">The T-shirts are packed in boxes and there can be five T-shirts in a box, except for the Extra-Large size where there is only space for four T-shirts.</span></span> <span data-ttu-id="8922e-111">Företaget vill spåra olika varianter av T-shirts i enheten **enheter** men säljer T-shirts i enheten **lådor**.</span><span class="sxs-lookup"><span data-stu-id="8922e-111">The company wants to track the different variants of the T-shirts in the unit **Pieces** but is selling the T-shirts in the unit **Boxes**.</span></span> <span data-ttu-id="8922e-112">Konverteringen mellan lagerenheten och försäljningsenheten är 1 låda = 5 enheter utom varianten Extra large där konverteringen är 1 låda = 4 enheter.</span><span class="sxs-lookup"><span data-stu-id="8922e-112">The conversion between the inventory unit and the sales unit is 1 Box = 5 Pieces, except for the variant Extra-Large, where the conversion is 1 Box = 4 Pieces.</span></span>

### <a name="set-up-a-product-for-unit-conversion-per-variant"></a><span data-ttu-id="8922e-113">Konfigurera en produkt för enhetskonvertering per variant</span><span class="sxs-lookup"><span data-stu-id="8922e-113">Set up a product for unit conversion per variant</span></span>

<span data-ttu-id="8922e-114">Produktvarianter kan bara skapas för produkter av **undertypen Produkt**: **produktmall**.</span><span class="sxs-lookup"><span data-stu-id="8922e-114">Product variants can only be created for products of **Product subtype**: **Product master**.</span></span> <span data-ttu-id="8922e-115">Mer information finns i [Skapa en produktmall](tasks/create-product-master.md).</span><span class="sxs-lookup"><span data-stu-id="8922e-115">For more information, see [Create a product master](tasks/create-product-master.md).</span></span>

<span data-ttu-id="8922e-116">Funktionen är inte aktiverad för produkter som har ställts in för faktisk/nominell vikt-processer.</span><span class="sxs-lookup"><span data-stu-id="8922e-116">The feature is not enabled for products that are set up for Catch Weight processes.</span></span> 

<span data-ttu-id="8922e-117">När produktmallen med frisläppta produktvarianter skapas kan enhetskonverteringar per varianter ställas in.</span><span class="sxs-lookup"><span data-stu-id="8922e-117">When the product master with released products variants is created, unit conversions per variants can be set up.</span></span> <span data-ttu-id="8922e-118">Du hittar alternativet för att öppna sidan enhetskonvertering i samband med en produkt eller en produktvariant på följande sidor.</span><span class="sxs-lookup"><span data-stu-id="8922e-118">You can find the menu item for opening the unit conversion page in context of a product or a product variant on the following pages.</span></span>

-   <span data-ttu-id="8922e-119">Sidan **Produktinformation**</span><span class="sxs-lookup"><span data-stu-id="8922e-119">**Product details** page</span></span>
-   <span data-ttu-id="8922e-120">Sidan **Uppgifter om frisläppta produkter**</span><span class="sxs-lookup"><span data-stu-id="8922e-120">**Released products details** page</span></span>
-   <span data-ttu-id="8922e-121">Sidan **Frisläppta produktvarianter**</span><span class="sxs-lookup"><span data-stu-id="8922e-121">**Released product variants** page</span></span>

<span data-ttu-id="8922e-122">När du öppnar sidan **Enhetskonvertering** i samband med en produktmall eller frisläppt produktvariant kan du välja om du vill ställa in enhetskonvertering för produkten eller för en produktvariant.</span><span class="sxs-lookup"><span data-stu-id="8922e-122">When you open the **Unit conversion** page in context of a product master or released product variant, you can select if you want to set up the unit conversion for the product or for a product variant.</span></span> <span data-ttu-id="8922e-123">Du gör detta genom att välja antingen **Produktvariant** eller **Produkt** i fältet **Skapa konvertering för**.</span><span class="sxs-lookup"><span data-stu-id="8922e-123">You do that by selecting either **Product variant** or **Product** in the **Create conversion for** field.</span></span>

### <a name="product-variant"></a><span data-ttu-id="8922e-124">Produktvariant</span><span class="sxs-lookup"><span data-stu-id="8922e-124">Product variant</span></span>

<span data-ttu-id="8922e-125">Om du väljer **Produktvariant** kan du sedan välja vilken variant du vill ställa in enhetskonvertering i fältet **Produktvariant**.</span><span class="sxs-lookup"><span data-stu-id="8922e-125">If you select **Product variant,** then you can select for which variant you want to set up the unit conversion in the **Product variant** field.</span></span>

### <a name="product"></a><span data-ttu-id="8922e-126">Produkt</span><span class="sxs-lookup"><span data-stu-id="8922e-126">Product</span></span>

<span data-ttu-id="8922e-127">Om du väljer **Produkt** kan du ställa in en enhetskonvertering för produktmallen.</span><span class="sxs-lookup"><span data-stu-id="8922e-127">If you select **Product**, then you can set up a unit conversion for the product master.</span></span> <span data-ttu-id="8922e-128">Denna enhetskonvertering gäller för alla produktvarianter utan definierad enhetskonvertering.</span><span class="sxs-lookup"><span data-stu-id="8922e-128">This unit conversion will apply for all product variants with no defined unit conversion.</span></span>

### <a name="example"></a><span data-ttu-id="8922e-129">Exempel</span><span class="sxs-lookup"><span data-stu-id="8922e-129">Example</span></span>

<span data-ttu-id="8922e-130">En produktmall **T-Shirt** har fyra frisläppta produktvarianter Small, Medium, Large och X-Large.</span><span class="sxs-lookup"><span data-stu-id="8922e-130">A product master, **T-Shirt**, has four released products variants Small, Medium, Large, and X-Large.</span></span> <span data-ttu-id="8922e-131">T-shirts förpackas i lådor och det kan finnas fem T-shirts i en låda, med undantag för Extra large som endast kan fyra T-shirts.</span><span class="sxs-lookup"><span data-stu-id="8922e-131">The T-shirts are packed in boxes and there can be five T-shirts in a box, except for the Extra-large size where there is only space for four T-shirts.</span></span>

<span data-ttu-id="8922e-132">Öppna först sidan **Enhetskonvertering** från sidan Information om frisläppt produkt för **T-shirt.**</span><span class="sxs-lookup"><span data-stu-id="8922e-132">First, open the **Unit conversion** page from the Release product details page for **T-shirt.**</span></span>

<span data-ttu-id="8922e-133">På sidan **Enhetskonvertering**, ställ in enhetskonvertering för den frisläppta produktvarianten X-Large.</span><span class="sxs-lookup"><span data-stu-id="8922e-133">On the **Unit conversion** page, set up the unit conversion for the release product variant X-Large.</span></span>

| <span data-ttu-id="8922e-134">**Fält**</span><span class="sxs-lookup"><span data-stu-id="8922e-134">**Field**</span></span>             | <span data-ttu-id="8922e-135">**Inställning**</span><span class="sxs-lookup"><span data-stu-id="8922e-135">**Setting**</span></span>             |
|-----------------------|-------------------------|
| <span data-ttu-id="8922e-136">Skapa konvertering för</span><span class="sxs-lookup"><span data-stu-id="8922e-136">Create conversion for</span></span> | <span data-ttu-id="8922e-137">Produktvariant</span><span class="sxs-lookup"><span data-stu-id="8922e-137">Product variant</span></span>         |
| <span data-ttu-id="8922e-138">Produktvariant</span><span class="sxs-lookup"><span data-stu-id="8922e-138">Product variant</span></span>       | <span data-ttu-id="8922e-139">T-Shirt : : X-Large : :</span><span class="sxs-lookup"><span data-stu-id="8922e-139">T-Shirt : : X-Large : :</span></span> |
| <span data-ttu-id="8922e-140">Från enhet</span><span class="sxs-lookup"><span data-stu-id="8922e-140">From unit</span></span>             | <span data-ttu-id="8922e-141">Lådor</span><span class="sxs-lookup"><span data-stu-id="8922e-141">Boxes</span></span>                   |
| <span data-ttu-id="8922e-142">Faktor</span><span class="sxs-lookup"><span data-stu-id="8922e-142">Factor</span></span>                | <span data-ttu-id="8922e-143">4</span><span class="sxs-lookup"><span data-stu-id="8922e-143">4</span></span>                       |
| <span data-ttu-id="8922e-144">Till enhet</span><span class="sxs-lookup"><span data-stu-id="8922e-144">To Unit</span></span>               | <span data-ttu-id="8922e-145">Antal</span><span class="sxs-lookup"><span data-stu-id="8922e-145">Pieces</span></span>                  |

<span data-ttu-id="8922e-146">De frisläppta produktvarianten Small, Medium och Large har samma enhetskonvertering mellan enheten Låda och Enheter, vilket innebär att du kan definiera enhetskonvertering för dessa produktvarianter för produktmallen.</span><span class="sxs-lookup"><span data-stu-id="8922e-146">The Released product variants Small, Medium, and Large have the same unit conversion between the unit Box and Pieces, which means that you can define the unit conversion for these product variants on the product master.</span></span>

| <span data-ttu-id="8922e-147">**Fält**</span><span class="sxs-lookup"><span data-stu-id="8922e-147">**Field**</span></span>             | <span data-ttu-id="8922e-148">**Inställning**</span><span class="sxs-lookup"><span data-stu-id="8922e-148">**Setting**</span></span> |
|-----------------------|-------------|
| <span data-ttu-id="8922e-149">Skapa konvertering för</span><span class="sxs-lookup"><span data-stu-id="8922e-149">Create conversion for</span></span> | <span data-ttu-id="8922e-150">Produkt</span><span class="sxs-lookup"><span data-stu-id="8922e-150">Product</span></span>     |
| <span data-ttu-id="8922e-151">Produkt</span><span class="sxs-lookup"><span data-stu-id="8922e-151">Product</span></span>               | <span data-ttu-id="8922e-152">T-shirt</span><span class="sxs-lookup"><span data-stu-id="8922e-152">T-Shirt</span></span>     |
| <span data-ttu-id="8922e-153">Från enhet</span><span class="sxs-lookup"><span data-stu-id="8922e-153">From unit</span></span>             | <span data-ttu-id="8922e-154">Lådor</span><span class="sxs-lookup"><span data-stu-id="8922e-154">Boxes</span></span>       |
| <span data-ttu-id="8922e-155">Faktor</span><span class="sxs-lookup"><span data-stu-id="8922e-155">Factor</span></span>                | <span data-ttu-id="8922e-156">5</span><span class="sxs-lookup"><span data-stu-id="8922e-156">5</span></span>           |
| <span data-ttu-id="8922e-157">Till enhet</span><span class="sxs-lookup"><span data-stu-id="8922e-157">To Unit</span></span>               | <span data-ttu-id="8922e-158">Antal</span><span class="sxs-lookup"><span data-stu-id="8922e-158">Pieces</span></span>      |

### <a name="using-excel-to-update-the-unit-conversions"></a><span data-ttu-id="8922e-159">Uppdatera enhetskonverteringarna med Excel</span><span class="sxs-lookup"><span data-stu-id="8922e-159">Using Excel to update the unit conversions</span></span>

<span data-ttu-id="8922e-160">Om en produkt har många produktvarianter med olika enhetskonverteringar, är det en bra idé att exportera enhetskonverteringar från sidan **Enhetskonvertering** till ett Excel-kalkylblad, uppdatera konverteringar och publicera tillbaka dem i Supply Chain Mangement.</span><span class="sxs-lookup"><span data-stu-id="8922e-160">If a product has many product variants with different unit conversions, it's a good idea to export the unit conversions from the **Unit conversion** page to an Excel spreadsheet, update the conversions, and then publish them back to Supply Chain Mangement.</span></span>

<span data-ttu-id="8922e-161">Alternativet för att exportera till Excel och publicera ändringarna tillbaka till Supply Chain Mangement aktiveras från menyobjektet **Öppna i Microsoft Office** i åtgärdsfönstret på sidan **Enhetskonverteringar**.</span><span class="sxs-lookup"><span data-stu-id="8922e-161">The option to export to Excel and publish the edits back to Supply Chain Mangement is enabled from the **Open in Microsoft office** menu item on the Action Pane on the **Unit conversion** page.</span></span>
