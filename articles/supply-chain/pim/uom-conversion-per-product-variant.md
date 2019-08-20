---
title: Måttenhetskonvertering per produktvariant
description: Det här avsnittet beskriver hur måttenhetskonvertering kan ställas in på produktvarianter.
author: johanhoffmann
manager: AnnBe
ms.date: 12/18/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
ROBOTS: noindex, nofollow
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-04-01
ms.dyn365.ops.version: 10
ms.openlocfilehash: 36fc98c44625cce03945d76973de67021d53353e
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2019
ms.locfileid: "1844379"
---
# <a name="unit-of-measure-conversion-per-product-variant"></a><span data-ttu-id="db9c0-103">Måttenhetskonvertering per produktvariant</span><span class="sxs-lookup"><span data-stu-id="db9c0-103">Unit of measure conversion per product variant</span></span>

[!include [banner](../includes/banner.md)]

[!include [pivate-preview](../includes/pivate-preview-banner.md)]

<span data-ttu-id="db9c0-104">Det här avsnittet beskriver hur måttenhetskonvertering kan ställas in på produktvarianter.</span><span class="sxs-lookup"><span data-stu-id="db9c0-104">This topic explains how unit of measure conversions can be set up on product variants.</span></span> <span data-ttu-id="db9c0-105">Den innehåller ett exempel på inställningarna.</span><span class="sxs-lookup"><span data-stu-id="db9c0-105">It includes an example of the setup.</span></span>

<span data-ttu-id="db9c0-106">Den här funktionen gör det möjligt för företag att definiera olika enhetskonverteringar mellan varianter av samma produkt.</span><span class="sxs-lookup"><span data-stu-id="db9c0-106">This feature makes it possible for companies to define different unit conversion between the variants of the same product.</span></span> <span data-ttu-id="db9c0-107">Följande exempel används i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="db9c0-107">The following example is used in this topic.</span></span> <span data-ttu-id="db9c0-108">Ett företag säljer t-shirts i storlek Small, Medium, Large och Extra large.</span><span class="sxs-lookup"><span data-stu-id="db9c0-108">A company sells T-shirts in sizes Small, Medium, Large, and Extra-Large.</span></span> <span data-ttu-id="db9c0-109">T-shirten definieras som en produkt och de olika storlekarna definieras som varianter av produkten.</span><span class="sxs-lookup"><span data-stu-id="db9c0-109">The T-shirt is defined as a product, and the different sizes are defined as variants of the product.</span></span> <span data-ttu-id="db9c0-110">T-shirts förpackas i lådor och det kan finnas fem T-shirts i en låda, med undantag för Extra large som endast kan fyra T-shirts.</span><span class="sxs-lookup"><span data-stu-id="db9c0-110">The T-shirts are packed in boxes and there can be five T-shirts in a box, except for the Extra-Large size where there is only space for four T-shirts.</span></span> <span data-ttu-id="db9c0-111">Företaget vill spåra olika varianter av T-shirts i enheten **enheter** men säljer T-shirts i enheten **lådor**.</span><span class="sxs-lookup"><span data-stu-id="db9c0-111">The company wants to track the different variants of the T-shirts in the unit **Pieces** but is selling the T-shirts in the unit **Boxes**.</span></span> <span data-ttu-id="db9c0-112">Konverteringen mellan lagerenheten och försäljningsenheten är 1 låda = 5 enheter utom varianten Extra large där konverteringen är 1 låda = 4 enheter.</span><span class="sxs-lookup"><span data-stu-id="db9c0-112">The conversion between the inventory unit and the sales unit is 1 Box = 5 Pieces, except for the variant Extra-Large, where the conversion is 1 Box = 4 Pieces.</span></span>

## <a name="setup"></a><span data-ttu-id="db9c0-113">Konfigurera</span><span class="sxs-lookup"><span data-stu-id="db9c0-113">Setup</span></span>

<span data-ttu-id="db9c0-114">Du kan konfigurera parametrar för att använda funktionen för produkter som har aktiverats för **alla processer** eller bara för produkter som aktiveras för **lagerprocesser** med hjälp av alternativet **Aktivera måttenhetskonverteringar** på sidan **Produktinformationsparametrar**.</span><span class="sxs-lookup"><span data-stu-id="db9c0-114">You can configure the parameters for using the feature for products enabled for **All processes** or only for product enabled for the **Warehouse processes** by using the **Enable unit of measure conversations** option on the **Product information parameters** page.</span></span>

### <a name="set-up-a-product-for-unit-conversion-per-variant"></a><span data-ttu-id="db9c0-115">Konfigurera en produkt för enhetskonvertering per variant</span><span class="sxs-lookup"><span data-stu-id="db9c0-115">Set up a product for unit conversion per variant</span></span>

<span data-ttu-id="db9c0-116">Produktvarianter kan bara skapas för produkter av **undertypen Produkt**: **produktmall**.</span><span class="sxs-lookup"><span data-stu-id="db9c0-116">Product variants can only be created for products of **Product subtype**: **Product master**.</span></span> <span data-ttu-id="db9c0-117">Mer information finns i [Skapa en produktmall](tasks/create-product-master.md).</span><span class="sxs-lookup"><span data-stu-id="db9c0-117">For more information, see [Create a product master](tasks/create-product-master.md).</span></span>

<span data-ttu-id="db9c0-118">Funktionen är inte aktiverad för produkter som har ställts in för faktisk/nominell vikt-processer.</span><span class="sxs-lookup"><span data-stu-id="db9c0-118">The feature is not enabled for products that are set up for Catch Weight processes.</span></span> 

<span data-ttu-id="db9c0-119">När du skapar en produktmall aktiverar du måttenhetskonvertering med hjälp av alternativet **Aktivera måttenhetskonverteringar** på sidan **produktinformation**.</span><span class="sxs-lookup"><span data-stu-id="db9c0-119">During the creation of a product master enable unit of measure conversion by using the **Enable unit of measure conversions** option on the **Product details** page.</span></span>

<span data-ttu-id="db9c0-120">När produktmallen med frisläppta produktvarianter skapas kan enhetskonverteringar per varianter ställas in.</span><span class="sxs-lookup"><span data-stu-id="db9c0-120">When the product master with released products variants is created, unit conversions per variants can be set up.</span></span> <span data-ttu-id="db9c0-121">Du hittar alternativet för att öppna sidan enhetskonvertering i samband med en produkt eller en produktvariant på följande sidor.</span><span class="sxs-lookup"><span data-stu-id="db9c0-121">You can find the menu item for opening the unit conversion page in context of a product or a product variant on the following pages.</span></span>

-   <span data-ttu-id="db9c0-122">Sidan **Produktinformation**</span><span class="sxs-lookup"><span data-stu-id="db9c0-122">**Product details** page</span></span>
-   <span data-ttu-id="db9c0-123">Sidan **Uppgifter om frisläppta produkter**</span><span class="sxs-lookup"><span data-stu-id="db9c0-123">**Released products details** page</span></span>
-   <span data-ttu-id="db9c0-124">Sidan **Frisläppta produktvarianter**</span><span class="sxs-lookup"><span data-stu-id="db9c0-124">**Released product variants** page</span></span>

<span data-ttu-id="db9c0-125">När du öppnar sidan **Enhetskonvertering** i samband med en produktmall eller frisläppt produktvariant kan du välja om du vill ställa in enhetskonvertering för produkten eller för en produktvariant.</span><span class="sxs-lookup"><span data-stu-id="db9c0-125">When you open the **Unit conversion** page in context of a product master or released product variant, you can select if you want to set up the unit conversion for the product or for a product variant.</span></span> <span data-ttu-id="db9c0-126">Du gör detta genom att välja antingen **Produktvariant** eller **Produkt** i fältet **Skapa konvertering för**.</span><span class="sxs-lookup"><span data-stu-id="db9c0-126">You do that by selecting either **Product variant** or **Product** in the **Create conversion for** field.</span></span>

### <a name="product-variant"></a><span data-ttu-id="db9c0-127">Produktvariant</span><span class="sxs-lookup"><span data-stu-id="db9c0-127">Product variant</span></span>

<span data-ttu-id="db9c0-128">Om du väljer **Produktvariant** kan du sedan välja vilken variant du vill ställa in enhetskonvertering i fältet **Produktvariant**.</span><span class="sxs-lookup"><span data-stu-id="db9c0-128">If you select **Product variant,** then you can select for which variant you want to set up the unit conversion in the **Product variant** field.</span></span>

### <a name="product"></a><span data-ttu-id="db9c0-129">Produkt</span><span class="sxs-lookup"><span data-stu-id="db9c0-129">Product</span></span>

<span data-ttu-id="db9c0-130">Om du väljer **Produkt** kan du ställa in en enhetskonvertering för produktmallen.</span><span class="sxs-lookup"><span data-stu-id="db9c0-130">If you select **Product**, then you can set up a unit conversion for the product master.</span></span> <span data-ttu-id="db9c0-131">Denna enhetskonvertering gäller för alla produktvarianter utan definierad enhetskonvertering.</span><span class="sxs-lookup"><span data-stu-id="db9c0-131">This unit conversion will apply for all product variants with no defined unit conversion.</span></span>

### <a name="example"></a><span data-ttu-id="db9c0-132">Exempel</span><span class="sxs-lookup"><span data-stu-id="db9c0-132">Example</span></span>

<span data-ttu-id="db9c0-133">En produktmall **T-Shirt** har fyra frisläppta produktvarianter Small, Medium, Large och X-Large.</span><span class="sxs-lookup"><span data-stu-id="db9c0-133">A product master, **T-Shirt**, has four released products variants Small, Medium, Large, and X-Large.</span></span> <span data-ttu-id="db9c0-134">T-shirts förpackas i lådor och det kan finnas fem T-shirts i en låda, med undantag för Extra large som endast kan fyra T-shirts.</span><span class="sxs-lookup"><span data-stu-id="db9c0-134">The T-shirts are packed in boxes and there can be five T-shirts in a box, except for the Extra-large size where there is only space for four T-shirts.</span></span>

<span data-ttu-id="db9c0-135">Öppna först sidan **Enhetskonvertering** från sidan Information om frisläppt produkt för **T-shirt.**</span><span class="sxs-lookup"><span data-stu-id="db9c0-135">First, open the **Unit conversion** page from the Release product details page for **T-shirt.**</span></span>

<span data-ttu-id="db9c0-136">På sidan **Enhetskonvertering**, ställ in enhetskonvertering för den frisläppta produktvarianten X-Large.</span><span class="sxs-lookup"><span data-stu-id="db9c0-136">On the **Unit conversion** page, set up the unit conversion for the release product variant X-Large.</span></span>

| <span data-ttu-id="db9c0-137">**Fält**</span><span class="sxs-lookup"><span data-stu-id="db9c0-137">**Field**</span></span>             | <span data-ttu-id="db9c0-138">**Inställning**</span><span class="sxs-lookup"><span data-stu-id="db9c0-138">**Setting**</span></span>             |
|-----------------------|-------------------------|
| <span data-ttu-id="db9c0-139">Skapa konvertering för</span><span class="sxs-lookup"><span data-stu-id="db9c0-139">Create conversion for</span></span> | <span data-ttu-id="db9c0-140">Produktvariant</span><span class="sxs-lookup"><span data-stu-id="db9c0-140">Product variant</span></span>         |
| <span data-ttu-id="db9c0-141">Produktvariant</span><span class="sxs-lookup"><span data-stu-id="db9c0-141">Product variant</span></span>       | <span data-ttu-id="db9c0-142">T-Shirt : : X-Large : :</span><span class="sxs-lookup"><span data-stu-id="db9c0-142">T-Shirt : : X-Large : :</span></span> |
| <span data-ttu-id="db9c0-143">Från enhet</span><span class="sxs-lookup"><span data-stu-id="db9c0-143">From unit</span></span>             | <span data-ttu-id="db9c0-144">Lådor</span><span class="sxs-lookup"><span data-stu-id="db9c0-144">Boxes</span></span>                   |
| <span data-ttu-id="db9c0-145">Faktor</span><span class="sxs-lookup"><span data-stu-id="db9c0-145">Factor</span></span>                | <span data-ttu-id="db9c0-146">4</span><span class="sxs-lookup"><span data-stu-id="db9c0-146">4</span></span>                       |
| <span data-ttu-id="db9c0-147">Till enhet</span><span class="sxs-lookup"><span data-stu-id="db9c0-147">To Unit</span></span>               | <span data-ttu-id="db9c0-148">Antal</span><span class="sxs-lookup"><span data-stu-id="db9c0-148">Pieces</span></span>                  |

<span data-ttu-id="db9c0-149">De frisläppta produktvarianten Small, Medium och Large har samma enhetskonvertering mellan enheten Låda och Enheter, vilket innebär att du kan definiera enhetskonvertering för dessa produktvarianter för produktmallen.</span><span class="sxs-lookup"><span data-stu-id="db9c0-149">The Released product variants Small, Medium, and Large have the same unit conversion between the unit Box and Pieces, which means that you can define the unit conversion for these product variants on the product master.</span></span>

| <span data-ttu-id="db9c0-150">**Fält**</span><span class="sxs-lookup"><span data-stu-id="db9c0-150">**Field**</span></span>             | <span data-ttu-id="db9c0-151">**Inställning**</span><span class="sxs-lookup"><span data-stu-id="db9c0-151">**Setting**</span></span> |
|-----------------------|-------------|
| <span data-ttu-id="db9c0-152">Skapa konvertering för</span><span class="sxs-lookup"><span data-stu-id="db9c0-152">Create conversion for</span></span> | <span data-ttu-id="db9c0-153">Produkt</span><span class="sxs-lookup"><span data-stu-id="db9c0-153">Product</span></span>     |
| <span data-ttu-id="db9c0-154">Produkt</span><span class="sxs-lookup"><span data-stu-id="db9c0-154">Product</span></span>               | <span data-ttu-id="db9c0-155">T-shirt</span><span class="sxs-lookup"><span data-stu-id="db9c0-155">T-Shirt</span></span>     |
| <span data-ttu-id="db9c0-156">Från enhet</span><span class="sxs-lookup"><span data-stu-id="db9c0-156">From unit</span></span>             | <span data-ttu-id="db9c0-157">Lådor</span><span class="sxs-lookup"><span data-stu-id="db9c0-157">Boxes</span></span>       |
| <span data-ttu-id="db9c0-158">Faktor</span><span class="sxs-lookup"><span data-stu-id="db9c0-158">Factor</span></span>                | <span data-ttu-id="db9c0-159">5</span><span class="sxs-lookup"><span data-stu-id="db9c0-159">5</span></span>           |
| <span data-ttu-id="db9c0-160">Till enhet</span><span class="sxs-lookup"><span data-stu-id="db9c0-160">To Unit</span></span>               | <span data-ttu-id="db9c0-161">Antal</span><span class="sxs-lookup"><span data-stu-id="db9c0-161">Pieces</span></span>      |

### <a name="using-excel-to-update-the-unit-conversions"></a><span data-ttu-id="db9c0-162">Uppdatera enhetskonverteringarna med Excel</span><span class="sxs-lookup"><span data-stu-id="db9c0-162">Using Excel to update the unit conversions</span></span>

<span data-ttu-id="db9c0-163">Om en produkt har många produktvarianter med olika enhetskonverteringar, är det en bra idé att exportera enhetskonverteringar från sidan **Enhetskonvertering** till ett Excel-kalkylblad, uppdatera konverteringar och publicera tillbaka dem i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="db9c0-163">If a product has many product variants with different unit conversions, it's a good idea to export the unit conversions from the **Unit conversion** page to an Excel spreadsheet, update the conversions, and then publish them back to Finance and Operations.</span></span>

<span data-ttu-id="db9c0-164">Alternativet för att exportera till Excel och publicera ändringarna tillbaka till Finance and Operations aktiveras från menyobjektet **Öppna i Microsoft Office** i åtgärdsfönstret på sidan **Enhetskonverteringar**.</span><span class="sxs-lookup"><span data-stu-id="db9c0-164">The option to export to Excel and publish the edits back to Finance and Operations is enabled from the **Open in Microsoft office** menu item on the Action Pane on the **Unit conversion** page.</span></span>
