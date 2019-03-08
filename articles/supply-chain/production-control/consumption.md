---
title: Beräkna materialförbrukning
description: Den här artikeln innehåller information om olika alternativ som är relaterade till beräkningen av materialförbrukning.
author: johanhoffmann
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BOMDesignerEditBOM, BOMTable, ProdBOM
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 53401
ms.assetid: 9cff88e4-0425-4707-9178-3c2cb10df7c2
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3e4010b5abb6b5a871d098422f1489cb2db3a071
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "316198"
---
# <a name="calculate-material-consumption"></a><span data-ttu-id="2e72c-103">Beräkna materialförbrukning</span><span class="sxs-lookup"><span data-stu-id="2e72c-103">Calculate material consumption</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2e72c-104">Den här artikeln innehåller information om olika alternativ som är relaterade till beräkningen av materialförbrukning.</span><span class="sxs-lookup"><span data-stu-id="2e72c-104">This article provides information about various options that are related to the calculation of material consumption.</span></span> 

<span data-ttu-id="2e72c-105">Följande alternativ, som är relaterade till beräkningen av materialförbrukning, är tillgängliga på flikarna **Inställningar** och **Stegförbrukning** på snabbfliken **Radinformation** på sidan **Strukturlista**.</span><span class="sxs-lookup"><span data-stu-id="2e72c-105">The following options that are related to the calculation of material consumption are available on the **Setup** and **Step consumption** tabs on the **Line details** FastTab of the **Bill of materials** page.</span></span>

## <a name="variable-and-constant-consumption"></a><span data-ttu-id="2e72c-106">Variabel och konstant förbrukning</span><span class="sxs-lookup"><span data-stu-id="2e72c-106">Variable and constant consumption</span></span>
<span data-ttu-id="2e72c-107">I fältet **Förbrukningen är** kan du välja om förbrukningen ska beräknas som en konstant kvantitet eller en variabel kvantitet.</span><span class="sxs-lookup"><span data-stu-id="2e72c-107">In the **Consumption is** field, you can select whether consumption should be calculated as a constant quantity or a variable quantity.</span></span> <span data-ttu-id="2e72c-108">Välj **Konstant** om en fast kvantitet eller volym krävs för tillverkningen, oavsett den kvantitet som tillverkas.</span><span class="sxs-lookup"><span data-stu-id="2e72c-108">Select **Constant** if a fixed quantity or volume is required for the production, regardless of the quantity that is produced.</span></span> <span data-ttu-id="2e72c-109">Välj **Variabel** som är standardinställningen om det obligatoriska beloppet för material i de färdiga varorna är proportionellt mot antalet färdiga varor som tillverkas.</span><span class="sxs-lookup"><span data-stu-id="2e72c-109">Select **Variable**, which is the default setting, if the required amount of material in the finished goods is proportional to the number of finished goods that are produced.</span></span>

## <a name="calculating-consumption-from-a-formula"></a><span data-ttu-id="2e72c-110">Beräkna förbrukning från en formel</span><span class="sxs-lookup"><span data-stu-id="2e72c-110">Calculating consumption from a formula</span></span>
<span data-ttu-id="2e72c-111">I fältet **Formel** kan du ställa in olika formler för beräkning av materialförbrukning.</span><span class="sxs-lookup"><span data-stu-id="2e72c-111">In the **Formula** field, you can set up various formulas for calculating material consumption.</span></span> <span data-ttu-id="2e72c-112">Om du använder standardvärde **Standard**, beräknas förbrukningen inte från en formel.</span><span class="sxs-lookup"><span data-stu-id="2e72c-112">If you use the default value, **Standard**, the consumption isn't calculated from a formula.</span></span> <span data-ttu-id="2e72c-113">Följande formler fungerar tillsammans med fälten **Höjd**,  **Bredd** **Djup** **Densitet**, och **Konstant**:</span><span class="sxs-lookup"><span data-stu-id="2e72c-113">The following formulas work together with the **Height**, **Width**, **Depth**, **Density**, and **Constant** fields:</span></span>

-   <span data-ttu-id="2e72c-114">Höjd \* Konstant</span><span class="sxs-lookup"><span data-stu-id="2e72c-114">Height \* Constant</span></span>
-   <span data-ttu-id="2e72c-115">Höjd \* Bredd \* Konstant</span><span class="sxs-lookup"><span data-stu-id="2e72c-115">Height \* Width \* Constant</span></span>
-   <span data-ttu-id="2e72c-116">Höjd \* Bredd \* Djup \* Konstant</span><span class="sxs-lookup"><span data-stu-id="2e72c-116">Height \* Width \* Depth \* Constant</span></span>
-   <span data-ttu-id="2e72c-117">(Höjd \* Bredd \* Djup / Densitet) \* Konstant</span><span class="sxs-lookup"><span data-stu-id="2e72c-117">(Height \* Width \* Depth / Density) \* Constant</span></span>

## <a name="rounding-up-and-multiples"></a><span data-ttu-id="2e72c-118">Avrundning och multipler.</span><span class="sxs-lookup"><span data-stu-id="2e72c-118">Rounding up and multiples</span></span>
<span data-ttu-id="2e72c-119">Tillsammans låter fälten **Avrundning** och **Multipler** avrunda värdet för materialförbrukning.</span><span class="sxs-lookup"><span data-stu-id="2e72c-119">Together, the **Rounding up** and **Multiples** fields let you round up the material consumption value.</span></span> <span data-ttu-id="2e72c-120">Du kan till exempel avrunda värdet enligt hanteringsenheten där råmaterial plockas för produktion.</span><span class="sxs-lookup"><span data-stu-id="2e72c-120">For example, you can round up the value according to the handling unit in which the raw material is picked for production.</span></span> <span data-ttu-id="2e72c-121">Följande alternativ är tillgängliga i fältet **Avrundning**: **Kvantitet** **Mått**, och **Förbrukning**.</span><span class="sxs-lookup"><span data-stu-id="2e72c-121">The following options are available in the **Rounding up** field: **Quantity**, **Measurement**, and **Consumption**.</span></span>

### <a name="quantity"></a><span data-ttu-id="2e72c-122">Kvantitet</span><span class="sxs-lookup"><span data-stu-id="2e72c-122">Quantity</span></span>

<span data-ttu-id="2e72c-123">Om du väljer **Kvantitet** som avrundningsmekanism måste kvantiteten vara en multipel av den angivna kvantiteten.</span><span class="sxs-lookup"><span data-stu-id="2e72c-123">If you select **Quantity** as the rounding-up mechanism, the quantity must be a multiple of the specified quantity.</span></span> <span data-ttu-id="2e72c-124">När till exempel hela tal krävs anger du 1 i fältet **1** i fältet **Multipler**.</span><span class="sxs-lookup"><span data-stu-id="2e72c-124">For example, if whole numbers are required, select **1** in the **Multiples** field.</span></span> <span data-ttu-id="2e72c-125">Nummer avrundas sedan upp till en kvantitet som är delbar med 1.</span><span class="sxs-lookup"><span data-stu-id="2e72c-125">Numbers are then rounded up to a quantity that is divisible by 1.</span></span>

### <a name="measurement"></a><span data-ttu-id="2e72c-126">Mått</span><span class="sxs-lookup"><span data-stu-id="2e72c-126">Measurement</span></span>

<span data-ttu-id="2e72c-127">Vanligtvis väljer du **Mått** som avrundningsmekanism när råmaterial levereras i bestämda dimensioner.</span><span class="sxs-lookup"><span data-stu-id="2e72c-127">Typically, you select **Measurement** as the rounding-up mechanism when the raw material comes in specific dimensions.</span></span> <span data-ttu-id="2e72c-128">Till exempel krävs en del av metallröret på 2 meter för färdig vara och metallröret lagras i längder på 4,5 meter.</span><span class="sxs-lookup"><span data-stu-id="2e72c-128">For example, a piece of 2-meter metal tube is required for a finished good, and the metal tube is stored in 4.5-meter lengths.</span></span> <span data-ttu-id="2e72c-129">I detta fall kan avrundningsmekanismen **Mått** användas för att beräkna hur många metallrör som krävs för att skapa ett visst antal enheter av den färdiga varan.</span><span class="sxs-lookup"><span data-stu-id="2e72c-129">In this case, the **Measurement** rounding-up mechanism can be used to calculate how many metal tubes are required to produce a specific number of pieces of the finished good.</span></span> <span data-ttu-id="2e72c-130">I det här exemplet anges fältet **Formel** som **höjd \* Konstant**.</span><span class="sxs-lookup"><span data-stu-id="2e72c-130">For this example, the **Formula** field is set to **Height \* Constant**.</span></span> <span data-ttu-id="2e72c-131">Fältet **Höjd** anges som **2** för att ange längden på röret som krävs för den färdiga varan.</span><span class="sxs-lookup"><span data-stu-id="2e72c-131">The **Height** field is set to **2** to indicate the length of the tube that is required for the finished good.</span></span> <span data-ttu-id="2e72c-132">Fältet **Multipel** är inställt på **4,5** för att ange att röret plockas i längder på 4,5 meter.</span><span class="sxs-lookup"><span data-stu-id="2e72c-132">The **Multiple** field is set to **4.5** to indicate that the tube is picked in lengths of 4.5 meters.</span></span> <span data-ttu-id="2e72c-133">Beräkningen är:</span><span class="sxs-lookup"><span data-stu-id="2e72c-133">Here is the calculation:</span></span>

1.  <span data-ttu-id="2e72c-134">Antal multiplar som krävs för 10 delar av den färdiga varan: 10 ÷ 2 = 5 enheter</span><span class="sxs-lookup"><span data-stu-id="2e72c-134">Number of multiples that are required for 10 pieces of the finished good: 10 ÷ 2 = 5 pieces</span></span>
2.  <span data-ttu-id="2e72c-135">Total förbrukning: 4,5 × 5 = 22,5 meter av metallrör</span><span class="sxs-lookup"><span data-stu-id="2e72c-135">Total consumption:  4.5 × 5 = 22.5 meters of metal tube</span></span>

<span data-ttu-id="2e72c-136">Det antas att 0,5 rör kasseras för var femte del av röret som förbrukas.</span><span class="sxs-lookup"><span data-stu-id="2e72c-136">It's assumed that 0.5 meter of tube is scrapped for every five pieces of tube that are consumed.</span></span>

### <a name="consumption"></a><span data-ttu-id="2e72c-137">Förbrukning</span><span class="sxs-lookup"><span data-stu-id="2e72c-137">Consumption</span></span>

<span data-ttu-id="2e72c-138">Vanligtvis väljer du**Förbrukning** som avrundningsmekanism när råmaterial måste plockas i hela kvantiteter för en specifik hanteringsenhet av produkten.</span><span class="sxs-lookup"><span data-stu-id="2e72c-138">Typically, you select **Consumption** as the rounding-up mechanism when raw material must be picked in whole quantities of a specific handling unit of the product.</span></span> <span data-ttu-id="2e72c-139">Till exempel används 2 liter färg för att tillverka en enhet av en färdig vara och målarfärgen plockas i 25 kvartars burkar.</span><span class="sxs-lookup"><span data-stu-id="2e72c-139">For example, 2 quarts of paint are used to produce one piece of a finished good, and the paint is picked in 25-quart cans.</span></span> <span data-ttu-id="2e72c-140">I detta fall kan avundningsmekanismen **Förbrukning** användas för att avrunda förbrukning till heltal i 25 kvartars burkar.</span><span class="sxs-lookup"><span data-stu-id="2e72c-140">In this case, the **Consumption** rounding-up mechanism can be used to round up consumption to whole numbers of 25-quart cans.</span></span> <span data-ttu-id="2e72c-141">Här följer beloppet för beräkningen av färg som krävs, om 180 enheter av den färdiga varan måste produceras:</span><span class="sxs-lookup"><span data-stu-id="2e72c-141">Here is the calculation for the amount of paint that is required if 180 pieces of the finished good must be produced:</span></span>

1.  <span data-ttu-id="2e72c-142">Målning som krävs, exklusive kassation: 180 × 2 = 360 liter</span><span class="sxs-lookup"><span data-stu-id="2e72c-142">Paint that is required, excluding scrap: 180 × 2 = 360 quarts</span></span>
2.  <span data-ttu-id="2e72c-143">Antal burkar: 360 ÷ 25 = 14,4, som avrundas uppåt till 15</span><span class="sxs-lookup"><span data-stu-id="2e72c-143">Number of cans: 360 ÷ 25 = 14.4, which is rounded up to 15</span></span>
3.  <span data-ttu-id="2e72c-144">Målning som krävs, inklusive kassation: 15 × 25 = 375 liter</span><span class="sxs-lookup"><span data-stu-id="2e72c-144">Paint that is required, including scrap: 15 × 25 = 375 quarts</span></span>

## <a name="step-consumption"></a><span data-ttu-id="2e72c-145">Stegförbrukning</span><span class="sxs-lookup"><span data-stu-id="2e72c-145">Step consumption</span></span>
<span data-ttu-id="2e72c-146">Stegförbrukning används för att beräkna konstant förbrukning i kvantitetintervall.</span><span class="sxs-lookup"><span data-stu-id="2e72c-146">Step consumption is used to calculate constant consumption in quantity intervals.</span></span> <span data-ttu-id="2e72c-147">Om du väljer **Stegförbrukning** i fältet **Formel** på fliken **Inställningar** kan du lägga till information om stegen i fliken **Stegförbrukning**. Den fasta förbrukade kvantiteten kan anges i intervaller för den framställda kvantiteten.</span><span class="sxs-lookup"><span data-stu-id="2e72c-147">If you select **Step consumption** in the **Formula** field on the **Setup** tab, you can add information about the steps on the **Step consumption** tab. The fixed consumed quantity can be set up in intervals of the produced quantity.</span></span> <span data-ttu-id="2e72c-148">Till exempel stegförbrukning har angetts i tabellen nedan.</span><span class="sxs-lookup"><span data-stu-id="2e72c-148">For example, step consumption is set up as shown in the following table.</span></span>

| <span data-ttu-id="2e72c-149">Från serie</span><span class="sxs-lookup"><span data-stu-id="2e72c-149">From series</span></span> | <span data-ttu-id="2e72c-150">Kvantitet</span><span class="sxs-lookup"><span data-stu-id="2e72c-150">Quantity</span></span> |
|-------------|----------|
| <span data-ttu-id="2e72c-151">0,00</span><span class="sxs-lookup"><span data-stu-id="2e72c-151">0.00</span></span>        | <span data-ttu-id="2e72c-152">10,0000</span><span class="sxs-lookup"><span data-stu-id="2e72c-152">10.0000</span></span>  |
| <span data-ttu-id="2e72c-153">100,00</span><span class="sxs-lookup"><span data-stu-id="2e72c-153">100.00</span></span>      | <span data-ttu-id="2e72c-154">20,0000</span><span class="sxs-lookup"><span data-stu-id="2e72c-154">20.0000</span></span>  |
| <span data-ttu-id="2e72c-155">200,00</span><span class="sxs-lookup"><span data-stu-id="2e72c-155">200.00</span></span>      | <span data-ttu-id="2e72c-156">40,0000</span><span class="sxs-lookup"><span data-stu-id="2e72c-156">40.0000</span></span>  |

<span data-ttu-id="2e72c-157">Kvantiteten för strukturlista (BOM) är 1, och produktionskvantiteten är 110.</span><span class="sxs-lookup"><span data-stu-id="2e72c-157">The bill of materials (BOM) quantity is 1, and the production quantity is 110.</span></span> <span data-ttu-id="2e72c-158">Formeln för förbrukningen är From series (kvantitet) = förbrukning.</span><span class="sxs-lookup"><span data-stu-id="2e72c-158">The formula for the consumption is From series (Quantity) = Consumption.</span></span> <span data-ttu-id="2e72c-159">Eftersom produktionskvantiteten är 110, är den i "Från 100-serien".</span><span class="sxs-lookup"><span data-stu-id="2e72c-159">Because the production quantity is 110, it falls into the "From 100 series."</span></span> <span data-ttu-id="2e72c-160">Därför är kvantiteten 20.</span><span class="sxs-lookup"><span data-stu-id="2e72c-160">Therefore, the quantity is 20.</span></span>



