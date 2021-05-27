---
title: Fraktcontainrar
description: I det här avsnittet beskrivs hur du ställer in leveransbehållare för modulen hemtagningskostnad.
author: sherry-zheng
ms.date: 12/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMContainerTypeTable, ITMContainerTable, ITMContainerUnitTypeTable, ITMRefrigerationTypeTable, ITMContainersListPage, ITMContainers
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-09
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 8f86f3603b64093214bb7cf7d165ba0fc2229ca3
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021550"
---
# <a name="shipping-container-setup"></a><span data-ttu-id="2471f-103">Inställningar för leveransbehållare</span><span class="sxs-lookup"><span data-stu-id="2471f-103">Shipping container setup</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="2471f-104">I det här avsnittet beskrivs hur du ställer in leveransbehållare för modulen **hemtagningskostnad**.</span><span class="sxs-lookup"><span data-stu-id="2471f-104">This topic describes how to set up shipping containers for the **Landed cost** module.</span></span>

## <a name="set-up-shipping-container-types"></a><a id="shipping-container-types"></a><span data-ttu-id="2471f-105">Ange typer av leveransbehållare</span><span class="sxs-lookup"><span data-stu-id="2471f-105">Set up shipping container types</span></span>

<span data-ttu-id="2471f-106">Typer av leveransbehållare definierar de typer av leveransbehållare som är tillgängliga för användning vid frakt och leverans.</span><span class="sxs-lookup"><span data-stu-id="2471f-106">Shipping container types define the types of shipping containers that are available for use during shipping and voyages.</span></span>

<span data-ttu-id="2471f-107">För att arbeta med typer av leveransbehållare, gå till **Hemtagningskostnad \> Inställning av behållare \> Typer av leveransbehållare**.</span><span class="sxs-lookup"><span data-stu-id="2471f-107">To work with the shipping container types, go to **Landed cost \> Containers setup \> Shipping container types**.</span></span> <span data-ttu-id="2471f-108">Där kan du visa, lägga till och ta bort poster för behållartyperna.</span><span class="sxs-lookup"><span data-stu-id="2471f-108">There, you can view, add, and remove records for your container types.</span></span> <span data-ttu-id="2471f-109">Följande register beskriver de fält som är tillgängliga för varje post.</span><span class="sxs-lookup"><span data-stu-id="2471f-109">The following table describes the fields that are available for each record.</span></span>

| <span data-ttu-id="2471f-110">Fält</span><span class="sxs-lookup"><span data-stu-id="2471f-110">Field</span></span> | <span data-ttu-id="2471f-111">beskrivning</span><span class="sxs-lookup"><span data-stu-id="2471f-111">Description</span></span> |
|---|---|
| <span data-ttu-id="2471f-112">Typ av fraktcontainer</span><span class="sxs-lookup"><span data-stu-id="2471f-112">Shipping container type</span></span> | <span data-ttu-id="2471f-113">Ange ett unikt ID-namn/nummer för typen av leveransbehållare.</span><span class="sxs-lookup"><span data-stu-id="2471f-113">Enter a unique identification name/number for the shipping container type.</span></span> |
| <span data-ttu-id="2471f-114">beskrivning</span><span class="sxs-lookup"><span data-stu-id="2471f-114">Description</span></span> | <span data-ttu-id="2471f-115">Ange en beskrivning av typen av leveransbehållare.</span><span class="sxs-lookup"><span data-stu-id="2471f-115">Enter a description of the shipping container type.</span></span> |
| <span data-ttu-id="2471f-116">Volym</span><span class="sxs-lookup"><span data-stu-id="2471f-116">Volume</span></span> | <span data-ttu-id="2471f-117">Ange den maximala volym som är tillåten i leveransbehållare av den här typen.</span><span class="sxs-lookup"><span data-stu-id="2471f-117">Enter the maximum volume that is allowed in shipping containers of this type.</span></span> |
| <span data-ttu-id="2471f-118">Vikt</span><span class="sxs-lookup"><span data-stu-id="2471f-118">Weight</span></span> | <span data-ttu-id="2471f-119">Ange den maximala vikt som är tillåten i leveransbehållare av den här typen.</span><span class="sxs-lookup"><span data-stu-id="2471f-119">Enter the maximum weight that is allowed in shipping containers of this type.</span></span> |
| <span data-ttu-id="2471f-120">Returnerbara</span><span class="sxs-lookup"><span data-stu-id="2471f-120">Returnable</span></span> | <span data-ttu-id="2471f-121">Ange om leveransbehållare av den här typen kan returneras till leverantören när de har använts under en sådan tid.</span><span class="sxs-lookup"><span data-stu-id="2471f-121">Specify whether shipping containers of this type can be returned to the vendor after they are used during a voyage.</span></span> <span data-ttu-id="2471f-122">Om det här alternativet ställs in på *Ja*, kan ytterligare kostnader gälla för retur av leveransbehållare av den här typen till ursprungsporten.</span><span class="sxs-lookup"><span data-stu-id="2471f-122">If this option is set to *Yes*, additional costs might apply for the return of shipping containers of this type to the port of origin.</span></span> |

## <a name="set-up-shipping-containers"></a><span data-ttu-id="2471f-123">Konfigurera leveransbehållare</span><span class="sxs-lookup"><span data-stu-id="2471f-123">Set up shipping containers</span></span>

<span data-ttu-id="2471f-124">Du använder poster för leveransbehållare för att identifiera varje behållare som du använder under färder.</span><span class="sxs-lookup"><span data-stu-id="2471f-124">You use shipping container records to identify each container that you use during voyages.</span></span> <span data-ttu-id="2471f-125">När du skapar en färd kan du välja en specifik behållare för den i listan över alla leveransbehållarposter som du har definierat här.</span><span class="sxs-lookup"><span data-stu-id="2471f-125">When you create a voyage, you can select a specific container for it in the list of all the shipping container records that you've defined here.</span></span> <span data-ttu-id="2471f-126">Den här funktionen är särskilt användbar om ditt företag äger sina egna leveransbehållare.</span><span class="sxs-lookup"><span data-stu-id="2471f-126">This feature is especially useful if your company owns its own shipping containers.</span></span>

<span data-ttu-id="2471f-127">Du behöver inte ange behållarnummer för leverans av behållare som bara används en gång.</span><span class="sxs-lookup"><span data-stu-id="2471f-127">You don't have to enter shipping container numbers for shipping containers that will be used only one time.</span></span> <span data-ttu-id="2471f-128">I stället kan du lägga till leveransbehållarnumret när du skapar en färd.</span><span class="sxs-lookup"><span data-stu-id="2471f-128">Instead, you can add the shipping container number when you create a voyage.</span></span>

<span data-ttu-id="2471f-129">Poster för leveransbehållare används bara i hemtagningskostnad.</span><span class="sxs-lookup"><span data-stu-id="2471f-129">Shipping container records are used only in Landed cost.</span></span> <span data-ttu-id="2471f-130">De är inte tillgängliga i standardmodulen för **transporthantering** (TMS).</span><span class="sxs-lookup"><span data-stu-id="2471f-130">They aren't available in the standard **Transportation management** module (TMS).</span></span>

<span data-ttu-id="2471f-131">För att arbeta med leveransbehållare, gå till **Hemtagningskostnad \> Inställning av behållare \> Leveransbehållare**.</span><span class="sxs-lookup"><span data-stu-id="2471f-131">To work with shipping containers, go to **Landed cost \> Containers setup \> Shipping containers**.</span></span> <span data-ttu-id="2471f-132">Där kan du visa, lägga till och ta bort poster för dina leveransbehållare.</span><span class="sxs-lookup"><span data-stu-id="2471f-132">There, you can view, add, and remove records your shipping containers.</span></span> <span data-ttu-id="2471f-133">Följande register beskriver de fält som är tillgängliga för varje post.</span><span class="sxs-lookup"><span data-stu-id="2471f-133">The following table describes the fields that are available for each record.</span></span>

| <span data-ttu-id="2471f-134">Fält</span><span class="sxs-lookup"><span data-stu-id="2471f-134">Field</span></span> | <span data-ttu-id="2471f-135">beskrivning</span><span class="sxs-lookup"><span data-stu-id="2471f-135">Description</span></span> |
|---|---|
| <span data-ttu-id="2471f-136">Fraktcontainer</span><span class="sxs-lookup"><span data-stu-id="2471f-136">Shipping container</span></span> | <span data-ttu-id="2471f-137">Ange ett unikt ID-namn/nummer för leveransbehållare.</span><span class="sxs-lookup"><span data-stu-id="2471f-137">Enter a unique identification name/number for the shipping container.</span></span> |
| <span data-ttu-id="2471f-138">Typ av fraktcontainer</span><span class="sxs-lookup"><span data-stu-id="2471f-138">Shipping container type</span></span> | <span data-ttu-id="2471f-139">Välj typ av leveransbehållare.</span><span class="sxs-lookup"><span data-stu-id="2471f-139">Select the type of shipping container.</span></span> <span data-ttu-id="2471f-140">För mer information, se avsnittet [Ställ in typer av leveransbehållare](#shipping-container-types) tidigare i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="2471f-140">For more information, see the [Set up shipping container types](#shipping-container-types) section earlier in this topic.</span></span> |

> [!NOTE]
> - <span data-ttu-id="2471f-141">Inställningarna för leveransbehållare är valfria.</span><span class="sxs-lookup"><span data-stu-id="2471f-141">The shipping container setup is optional.</span></span> <span data-ttu-id="2471f-142">Vanligtvis använder du det bara om ditt företag äger sina egna leveransbehållare eller ofta återanvänder samma leveransbehållare.</span><span class="sxs-lookup"><span data-stu-id="2471f-142">Typically, you will use it only if your company owns its own shipping containers or often reuses the same shipping containers.</span></span>
> - <span data-ttu-id="2471f-143">Inga kontrollsiffror beräknas för leveransbehållarens nummer.</span><span class="sxs-lookup"><span data-stu-id="2471f-143">No check digits are calculated for shipping container numbers.</span></span>

## <a name="set-up-unit-types"></a><a name="unit-types"></a><span data-ttu-id="2471f-144">Ställa in enhetstyper</span><span class="sxs-lookup"><span data-stu-id="2471f-144">Set up unit types</span></span>

<span data-ttu-id="2471f-145">Enhetstyper skapar ytterligare grupperingar och identifieringsmetoder för leveransbehållare.</span><span class="sxs-lookup"><span data-stu-id="2471f-145">Unit types establish additional groupings and identification methods for shipping containers.</span></span> <span data-ttu-id="2471f-146">Enhetstypen används normalt för att identifiera vilken typ av behållare som gods förpackas i, till exempel lastpallar eller trummor.</span><span class="sxs-lookup"><span data-stu-id="2471f-146">The unit type is typically used to identify the type of container that goods are packaged in, such as pallets or drums.</span></span> <span data-ttu-id="2471f-147">Du kan välja en enhetstyp när du ställer in en behållare på sidan **Alla leveransbehållare**.</span><span class="sxs-lookup"><span data-stu-id="2471f-147">You can select a unit type when you set up a container on the **All shipping containers** page.</span></span>

<span data-ttu-id="2471f-148">Enhetstyper används bara för hemtagningskostnad.</span><span class="sxs-lookup"><span data-stu-id="2471f-148">Unit types are used only in Landed cost.</span></span> <span data-ttu-id="2471f-149">De är inte tillgängliga i TMS.</span><span class="sxs-lookup"><span data-stu-id="2471f-149">They aren't available in TMS.</span></span>

<span data-ttu-id="2471f-150">För att arbeta med enhetstyper, gå till **Hemtagningskostnad \> Inställning av behållare \> Enhetstyper**.</span><span class="sxs-lookup"><span data-stu-id="2471f-150">To work with unit types, go to **Landed cost \> Containers setup \> Unit types**.</span></span> <span data-ttu-id="2471f-151">Där kan du visa, lägga till och ta bort poster för enhetstyperna.</span><span class="sxs-lookup"><span data-stu-id="2471f-151">There, you can view, add, and remove records for your unit types.</span></span> <span data-ttu-id="2471f-152">Följande register beskriver de fält som är tillgängliga för varje post.</span><span class="sxs-lookup"><span data-stu-id="2471f-152">The following table describes the fields that are available for each record.</span></span>

| <span data-ttu-id="2471f-153">Fält</span><span class="sxs-lookup"><span data-stu-id="2471f-153">Field</span></span> | <span data-ttu-id="2471f-154">beskrivning</span><span class="sxs-lookup"><span data-stu-id="2471f-154">Description</span></span> |
|---|---|
| <span data-ttu-id="2471f-155">Enhetstyp</span><span class="sxs-lookup"><span data-stu-id="2471f-155">Unit type</span></span> | <span data-ttu-id="2471f-156">Ange ett unikt ID-namn/nummer för enhetstypen.</span><span class="sxs-lookup"><span data-stu-id="2471f-156">Enter a unique identification name/number for the unit type.</span></span> |
| <span data-ttu-id="2471f-157">beskrivning</span><span class="sxs-lookup"><span data-stu-id="2471f-157">Description</span></span> | <span data-ttu-id="2471f-158">Ange en beskrivning av enhetstyp.</span><span class="sxs-lookup"><span data-stu-id="2471f-158">Enter a description of the unit type.</span></span> |

## <a name="set-up-refrigeration-types"></a><a name="refrigeration-types"></a><span data-ttu-id="2471f-159">Ställa in kyltyper</span><span class="sxs-lookup"><span data-stu-id="2471f-159">Set up refrigeration types</span></span>

<span data-ttu-id="2471f-160">Kyltyper skapar ytterligare grupperingar och identifieringsmetoder för leveransbehållare (vanligtvis kylbehållare).</span><span class="sxs-lookup"><span data-stu-id="2471f-160">Refrigeration types establish additional groupings and identification methods for shipping containers (usually refrigerated containers).</span></span> <span data-ttu-id="2471f-161">Du kan välja en kyltyp när du ställer in en behållare på sidan **Alla leveransbehållare**.</span><span class="sxs-lookup"><span data-stu-id="2471f-161">You can select a refrigeration type when you set up a container on the **All shipping containers** page.</span></span>

<span data-ttu-id="2471f-162">För att arbeta med kyltyper, gå till **Hemtagningskostnad \> Inställning av behållare \> Kyltyper**.</span><span class="sxs-lookup"><span data-stu-id="2471f-162">To work with refrigeration types, go to **Landed cost \> Containers setup \> Refrigeration types**.</span></span> <span data-ttu-id="2471f-163">Där kan du visa, lägga till och ta bort poster för kyltyperna.</span><span class="sxs-lookup"><span data-stu-id="2471f-163">There, you can view, add, and remove records for your refrigeration types.</span></span> <span data-ttu-id="2471f-164">Följande register beskriver de fält som är tillgängliga för varje post.</span><span class="sxs-lookup"><span data-stu-id="2471f-164">The following table describes the fields that are available for each record.</span></span>

| <span data-ttu-id="2471f-165">Fält</span><span class="sxs-lookup"><span data-stu-id="2471f-165">Field</span></span> | <span data-ttu-id="2471f-166">beskrivning</span><span class="sxs-lookup"><span data-stu-id="2471f-166">Description</span></span> |
|---|---|
| <span data-ttu-id="2471f-167">Kylningstyp</span><span class="sxs-lookup"><span data-stu-id="2471f-167">Refrigeration type</span></span> | <span data-ttu-id="2471f-168">Ange ett unikt ID-namn/nummer för kyltypen.</span><span class="sxs-lookup"><span data-stu-id="2471f-168">Enter a unique identification name/number for the refrigeration type.</span></span> |
| <span data-ttu-id="2471f-169">beskrivning</span><span class="sxs-lookup"><span data-stu-id="2471f-169">Description</span></span> | <span data-ttu-id="2471f-170">Ange en beskrivning för kyltypen.</span><span class="sxs-lookup"><span data-stu-id="2471f-170">Enter a description of the refrigeration type.</span></span> |
