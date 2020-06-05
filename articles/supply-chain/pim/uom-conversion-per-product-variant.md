---
title: Måttenhetskonvertering per produktvariant
description: Det här avsnittet beskriver hur du konfigurerar måttenhetskonvertering för produktvarianter. Den innehåller ett exempel på inställningarna.
author: johanhoffmann
manager: tfehr
ms.date: 05/11/2020
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
ms.openlocfilehash: 71d35d47a703f0931ba3b4ab5df21c7199c7ea5b
ms.sourcegitcommit: 92611ec276da6f7211d722cfcd66739b612296dc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/18/2020
ms.locfileid: "3382807"
---
# <a name="unit-of-measure-conversion-per-product-variant"></a><span data-ttu-id="064f9-104">Måttenhetskonvertering per produktvariant</span><span class="sxs-lookup"><span data-stu-id="064f9-104">Unit of measure conversion per product variant</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="064f9-105">Det här avsnittet beskriver hur du konfigurerar måttenhetskonverteringar för diverse produktvarianter.</span><span class="sxs-lookup"><span data-stu-id="064f9-105">This topic explains how to set up unit of measure conversions for various product variants.</span></span>

<span data-ttu-id="064f9-106">I stället för att skapa flera enskilda produkter som måste underhållas kan du använda produktvarianter för att skapa varianter av en enskild produkt.</span><span class="sxs-lookup"><span data-stu-id="064f9-106">Instead of creating multiple individual products that must be maintained, you can use product variants to create variations of a single product.</span></span> <span data-ttu-id="064f9-107">En produktvariant kan till exempel vara en T-shirt med given storlek och färg.</span><span class="sxs-lookup"><span data-stu-id="064f9-107">For example, a product variant might be a T-shirt of a given size and color.</span></span>

<span data-ttu-id="064f9-108">Tidigare kunde enhetskonverteringar endast ställas in i produktmallen.</span><span class="sxs-lookup"><span data-stu-id="064f9-108">Previously, unit conversions could be set up only on the product master.</span></span> <span data-ttu-id="064f9-109">Därför hade alla produktvarianter samma enhetskonverteringsregler.</span><span class="sxs-lookup"><span data-stu-id="064f9-109">Therefore, all product variants had the same unit conversion rules.</span></span> <span data-ttu-id="064f9-110">När funktionen *Måttenhetskonverteringar för produktvarianter* är aktiverad, dina T-shirtar säljs i kartonger och antalet T-shirtar som kan förpackas i en och samma kartong beror på storleken på T-shirtarna, kan du nu ställa in enhetskonverteringar mellan olika tröjstorlekar och de kartonger som används för paketering.</span><span class="sxs-lookup"><span data-stu-id="064f9-110">However, when the *Unit of measure conversions for product variants* feature is turned on, if your T-shirts are sold in boxes, and the number of T-shirts that can be packed in a box depends on the size of the T-shirts, you can now set up unit conversions between the different shirt sizes and the boxes that are used for packaging.</span></span>

## <a name="turn-on-the-feature-in-your-system"></a><span data-ttu-id="064f9-111">Aktivera funktionen i systemet</span><span class="sxs-lookup"><span data-stu-id="064f9-111">Turn on the feature in your system</span></span>

<span data-ttu-id="064f9-112">Om du inte redan ser funktionen i systemet går du till [Funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) och aktiverar funktionen *Måttenhetskonverteringar för produktvarianter*.</span><span class="sxs-lookup"><span data-stu-id="064f9-112">If you don't already see this feature in your system, go to [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), and turn on the *Unit of measure conversions for product variants* feature.</span></span>

## <a name="set-up-a-product-for-unit-conversion-per-variant"></a><span data-ttu-id="064f9-113">Konfigurera en produkt för enhetskonvertering per variant</span><span class="sxs-lookup"><span data-stu-id="064f9-113">Set up a product for unit conversion per variant</span></span>

<span data-ttu-id="064f9-114">Produktvarianter kan bara skapas för produkter som är produktmallar.</span><span class="sxs-lookup"><span data-stu-id="064f9-114">Product variants can be created only for products that are product masters.</span></span> <span data-ttu-id="064f9-115">Mer information finns i [Skapa en produktmall](tasks/create-product-master.md).</span><span class="sxs-lookup"><span data-stu-id="064f9-115">For more information, see [Create a product master](tasks/create-product-master.md).</span></span> <span data-ttu-id="064f9-116">Funktionen *Måttenhetskonverteringar för produktvarianter* är inte tillgänglig för produkter som har ställts in för faktiska viktprocesser.</span><span class="sxs-lookup"><span data-stu-id="064f9-116">The *Unit of measure conversions for product variants* feature isn't available for products that are set up for catch-weight processes.</span></span>

<span data-ttu-id="064f9-117">Så här konfigurerar du en produktmall till stöd för enhetskonvertering per variant:</span><span class="sxs-lookup"><span data-stu-id="064f9-117">To configure a product master to support unit conversion per variant, follow these steps.</span></span>

1. <span data-ttu-id="064f9-118">Gå till **Hantering av produktinformation \> Produkter \> Produktmallar**.</span><span class="sxs-lookup"><span data-stu-id="064f9-118">Go to **Product information management \> Products \> Product masters**.</span></span>
1. <span data-ttu-id="064f9-119">Skapa eller öppna en produktmall om du vill gå till sidan **Produktinformation**.</span><span class="sxs-lookup"><span data-stu-id="064f9-119">Create or open a product master to go to its **Product details** page.</span></span>
1. <span data-ttu-id="064f9-120">Ställ in alternativet **Aktivera måttenhetskonverteringar** som *Ja*.</span><span class="sxs-lookup"><span data-stu-id="064f9-120">Set the **Enable unit of measure conversions** option to *Yes*.</span></span>
1. <span data-ttu-id="064f9-121">I åtgärdsfönstret, på fliken **Produkt** i gruppen **Konfigurering**, markerar du **Enhetskonverteringar**.</span><span class="sxs-lookup"><span data-stu-id="064f9-121">On the Action Pane, on the **Product** tab, in the **Set up** group, select **Unit conversions**.</span></span>
1. <span data-ttu-id="064f9-122">Sidan **Enhetskonverteringar** öppnas.</span><span class="sxs-lookup"><span data-stu-id="064f9-122">The **Unit conversions** page opens.</span></span> <span data-ttu-id="064f9-123">Välj en av följande flikar:</span><span class="sxs-lookup"><span data-stu-id="064f9-123">Select one of the following tabs:</span></span>

    - <span data-ttu-id="064f9-124">**Konverteringar inom klasser** – Välj den här fliken om du vill konvertera mellan enheter som tillhör samma enhetsklass.</span><span class="sxs-lookup"><span data-stu-id="064f9-124">**Intra-class conversions** – Select this tab to convert between units that belong to the same unit class.</span></span>
    - <span data-ttu-id="064f9-125">**Konverteringar inom klasser** – Välj den här fliken om du vill konvertera mellan enheter som tillhör olika enhetsklasser.</span><span class="sxs-lookup"><span data-stu-id="064f9-125">**Inter-class conversions** – Select this tab to convert between units that belong to different unit classes.</span></span>

1. <span data-ttu-id="064f9-126">Klicka på **Ny** om du vill lägga till en ny enhetskonvertering.</span><span class="sxs-lookup"><span data-stu-id="064f9-126">Select **New** to add a new unit conversion.</span></span>
1. <span data-ttu-id="064f9-127">Ställ in fältet **Skapa konvertering för** på ett av följande värden:</span><span class="sxs-lookup"><span data-stu-id="064f9-127">Set the **Create conversion for** field to one of the following values:</span></span>

    - <span data-ttu-id="064f9-128">**Produkt** – Om du väljer detta värde kan du ange en enhetskonvertering för produktmallen.</span><span class="sxs-lookup"><span data-stu-id="064f9-128">**Product** – If you select this value, you can set up a unit conversion for the product master.</span></span> <span data-ttu-id="064f9-129">Den enhetskonverteringen kommer att användas som reserv för alla produktvarianter som ingen enhetskonvertering definieras för.</span><span class="sxs-lookup"><span data-stu-id="064f9-129">That unit conversion will be used as a fallback for all product variants that no unit conversion is defined for.</span></span>
    - <span data-ttu-id="064f9-130">**Produktvariant** – Om du väljer detta värde kan du ange en enhetskonvertering för en specifik produktvariant.</span><span class="sxs-lookup"><span data-stu-id="064f9-130">**Product variant** – If you select this value, you can set up a unit conversion for a specific product variant.</span></span> <span data-ttu-id="064f9-131">Använd fältet **Produktvariant** för att välja varianten.</span><span class="sxs-lookup"><span data-stu-id="064f9-131">Use the **Product variant** field to select the variant.</span></span>

    <span data-ttu-id="064f9-132">![Lägga till en ny enhets konvertering](media/uom-new-conversion.png "Lägga till en ny enhetskonvertering")</span><span class="sxs-lookup"><span data-stu-id="064f9-132">![Adding a new unit conversion](media/uom-new-conversion.png "Adding a new unit conversion")</span></span>

1. <span data-ttu-id="064f9-133">Använd de andra fälten som tillhandahålls för att ställa in din enhetskonvertering.</span><span class="sxs-lookup"><span data-stu-id="064f9-133">Use the other fields that are provided to set up your unit conversion.</span></span>
1. <span data-ttu-id="064f9-134">Klicka på **OK** om du vill spara den nya enhetskonverteringen.</span><span class="sxs-lookup"><span data-stu-id="064f9-134">Select **OK** to save the new unit conversion.</span></span>

> [!TIP]
> <span data-ttu-id="064f9-135">Du kan öppna sidan **Enhetskonverteringar** för en produkt eller en produktvariant från någon av följande sidor:</span><span class="sxs-lookup"><span data-stu-id="064f9-135">You can open the **Unit conversions** page for a product or a product variant from any of the following pages:</span></span>
> 
> - <span data-ttu-id="064f9-136">Produktdetaljer</span><span class="sxs-lookup"><span data-stu-id="064f9-136">Product details</span></span>
> - <span data-ttu-id="064f9-137">Information om släppt produkt</span><span class="sxs-lookup"><span data-stu-id="064f9-137">Released products details</span></span>
> - <span data-ttu-id="064f9-138">Frisläppta produktvarianter</span><span class="sxs-lookup"><span data-stu-id="064f9-138">Released product variants</span></span>

## <a name="example-scenario"></a><span data-ttu-id="064f9-139">Exempelscenario</span><span class="sxs-lookup"><span data-stu-id="064f9-139">Example scenario</span></span>

<span data-ttu-id="064f9-140">I detta scenario säljer ett företag T-shirts i storlekarna Small, Medium, Large och Extra large.</span><span class="sxs-lookup"><span data-stu-id="064f9-140">In this scenario, a company sells T-shirts in sizes small, medium, large, and extra-large.</span></span> <span data-ttu-id="064f9-141">T-shirten definieras som en produkt och de olika storlekarna definieras som varianter av den produkten.</span><span class="sxs-lookup"><span data-stu-id="064f9-141">The T-shirt is defined as a product, and the different sizes are defined as variants of that product.</span></span> <span data-ttu-id="064f9-142">Tröjorna förpackas i kartonger.</span><span class="sxs-lookup"><span data-stu-id="064f9-142">The shirts are packed in boxes.</span></span> <span data-ttu-id="064f9-143">För storlekarna Small, Medium och Large kan det finnas fem tröjor per kartong.</span><span class="sxs-lookup"><span data-stu-id="064f9-143">For sizes small, medium, and large, there can be five shirts in each box.</span></span> <span data-ttu-id="064f9-144">För storleken Extra stor finns emellertid plats för endast fyra tröjor per kartong.</span><span class="sxs-lookup"><span data-stu-id="064f9-144">However, for size extra-large, there is space for only four shirts in each box.</span></span>

<span data-ttu-id="064f9-145">Företaget vill spåra de olika varianterna i enheten *Stycken*, men man säljer dem i enheten *kartonger*.</span><span class="sxs-lookup"><span data-stu-id="064f9-145">The company wants to track the different variants in the *Pieces* unit, but it's selling them in the *Boxes* unit.</span></span> <span data-ttu-id="064f9-146">För storlekarna Small, Medium och Large är konverteringsförhållandet mellan lagerenhet och försäljningsenhet 1 kartong = 5 stycken.</span><span class="sxs-lookup"><span data-stu-id="064f9-146">For sizes small, medium, and large, the conversion between the inventory unit and the sales unit is 1 Box = 5 Pieces.</span></span> <span data-ttu-id="064f9-147">För storleken Extra large är konverteringen 1 kartong = 4 stycken.</span><span class="sxs-lookup"><span data-stu-id="064f9-147">For size extra-large, the conversion is 1 Box = 4 Pieces.</span></span>

1. <span data-ttu-id="064f9-148">På sidan **Information om frisläppt produkt** för produkten **T-shirt** öppnar du sidan **Enhetskonvertering**.</span><span class="sxs-lookup"><span data-stu-id="064f9-148">From the **Released product details** page for the **T-Shirt** product, open the **Unit conversions** page.</span></span>
1. <span data-ttu-id="064f9-149">På sidan **Enhetskonverteringar** anger du följande enhetskonvertering för produktvarianten **X-Large**.</span><span class="sxs-lookup"><span data-stu-id="064f9-149">On the **Unit conversions** page, set up the following unit conversion for the **X-Large** released product variant.</span></span>

    | <span data-ttu-id="064f9-150">Fält</span><span class="sxs-lookup"><span data-stu-id="064f9-150">Field</span></span>                 | <span data-ttu-id="064f9-151">Inställning</span><span class="sxs-lookup"><span data-stu-id="064f9-151">Setting</span></span>                 |
    |-----------------------|-------------------------|
    | <span data-ttu-id="064f9-152">Skapa konvertering för</span><span class="sxs-lookup"><span data-stu-id="064f9-152">Create conversion for</span></span> | <span data-ttu-id="064f9-153">Produktvariant</span><span class="sxs-lookup"><span data-stu-id="064f9-153">Product variant</span></span>         |
    | <span data-ttu-id="064f9-154">Produktvariant</span><span class="sxs-lookup"><span data-stu-id="064f9-154">Product variant</span></span>       | <span data-ttu-id="064f9-155">T-Shirt : : X-Large : :</span><span class="sxs-lookup"><span data-stu-id="064f9-155">T-Shirt : : X-Large : :</span></span> |
    | <span data-ttu-id="064f9-156">Från enhet</span><span class="sxs-lookup"><span data-stu-id="064f9-156">From unit</span></span>             | <span data-ttu-id="064f9-157">Lådor</span><span class="sxs-lookup"><span data-stu-id="064f9-157">Boxes</span></span>                   |
    | <span data-ttu-id="064f9-158">Faktor</span><span class="sxs-lookup"><span data-stu-id="064f9-158">Factor</span></span>                | <span data-ttu-id="064f9-159">4</span><span class="sxs-lookup"><span data-stu-id="064f9-159">4</span></span>                       |
    | <span data-ttu-id="064f9-160">Till enhet</span><span class="sxs-lookup"><span data-stu-id="064f9-160">To Unit</span></span>               | <span data-ttu-id="064f9-161">Antal</span><span class="sxs-lookup"><span data-stu-id="064f9-161">Pieces</span></span>                  |

1. <span data-ttu-id="064f9-162">Eftersom produktvarianterna **Small**, **Medium** och **Large** samtliga har samma enhetskonvertering mellan enheterna *Kartong* och *Stycken* kan du definiera följande enhetskonvertering för dem i produktmallen.</span><span class="sxs-lookup"><span data-stu-id="064f9-162">Because the **Small**, **Medium**, and **Large** product variants all have the same unit conversion between the *Box* and *Pieces* units, you can define the following unit conversion for them on the product master.</span></span>

    | <span data-ttu-id="064f9-163">Fält</span><span class="sxs-lookup"><span data-stu-id="064f9-163">Field</span></span>                 | <span data-ttu-id="064f9-164">Inställning</span><span class="sxs-lookup"><span data-stu-id="064f9-164">Setting</span></span> |
    |-----------------------|---------|
    | <span data-ttu-id="064f9-165">Skapa konvertering för</span><span class="sxs-lookup"><span data-stu-id="064f9-165">Create conversion for</span></span> | <span data-ttu-id="064f9-166">Produkt</span><span class="sxs-lookup"><span data-stu-id="064f9-166">Product</span></span> |
    | <span data-ttu-id="064f9-167">Produkt</span><span class="sxs-lookup"><span data-stu-id="064f9-167">Product</span></span>               | <span data-ttu-id="064f9-168">T-shirt</span><span class="sxs-lookup"><span data-stu-id="064f9-168">T-Shirt</span></span> |
    | <span data-ttu-id="064f9-169">Från enhet</span><span class="sxs-lookup"><span data-stu-id="064f9-169">From unit</span></span>             | <span data-ttu-id="064f9-170">Lådor</span><span class="sxs-lookup"><span data-stu-id="064f9-170">Boxes</span></span>   |
    | <span data-ttu-id="064f9-171">Faktor</span><span class="sxs-lookup"><span data-stu-id="064f9-171">Factor</span></span>                | <span data-ttu-id="064f9-172">5</span><span class="sxs-lookup"><span data-stu-id="064f9-172">5</span></span>       |
    | <span data-ttu-id="064f9-173">Till enhet</span><span class="sxs-lookup"><span data-stu-id="064f9-173">To Unit</span></span>               | <span data-ttu-id="064f9-174">Antal</span><span class="sxs-lookup"><span data-stu-id="064f9-174">Pieces</span></span>  |

## <a name="using-excel-to-update-the-unit-conversions"></a><span data-ttu-id="064f9-175">Uppdatera enhetskonverteringarna med Excel</span><span class="sxs-lookup"><span data-stu-id="064f9-175">Using Excel to update the unit conversions</span></span>

<span data-ttu-id="064f9-176">Om en produkt har många produktvarianter som har olika enhetskonverteringar är det en god idé att exportera enhetskonverteringarna till en Microsoft Excel-arbetsbok, uppdatera dem och sedan publicera dem på nytt i Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="064f9-176">If a product has many product variants that have different unit conversions, it's a good idea to export the unit conversions to a Microsoft Excel workbook, update them, and then publish them back to Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="064f9-177">Om du vill exportera enhetskonverteringar till Excel går du till sidan **Enhetskonverteringar** och väljer **Öppna i Microsoft Office** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="064f9-177">To export unit conversions to Excel, on the **Unit conversions** page, on the Action Pane, select **Open in Microsoft Office**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="064f9-178">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="064f9-178">Additional resources</span></span>

[<span data-ttu-id="064f9-179">Hantera måttenhet</span><span class="sxs-lookup"><span data-stu-id="064f9-179">Manage unit of measure</span></span>](tasks/manage-unit-measure.md)
