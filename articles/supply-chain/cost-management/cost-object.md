---
title: Kostnadsobjekt
description: Det här avsnittet innehåller information om kostnadsobjekt och en beskrivning av hur kostnader och kvantiteter ackumuleras. Ett kostnadsredovisning är ett objekt som kostnader och kvantiteter ackumuleras för. En kostnadsobjektenhet kan vara antingen en produkt eller produktvarianter såsom varianter för stil och färg.
author: AndersGirke
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventCostOnhandItem
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 19451
ms.assetid: ec776b98-813a-490d-848f-468452d98fac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 85e590322c75cfb2ad21236af56656061037a4b7
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437809"
---
# <a name="cost-objects"></a><span data-ttu-id="2bf95-105">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="2bf95-105">Cost objects</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2bf95-106">Det här avsnittet innehåller information om kostnadsobjekt och en beskrivning av hur kostnader och kvantiteter ackumuleras.</span><span class="sxs-lookup"><span data-stu-id="2bf95-106">This article provides information about costs objects, and explains how costs and quantities are accumulated.</span></span> <span data-ttu-id="2bf95-107">Ett kostnadsredovisning är ett objekt som kostnader och kvantiteter ackumuleras för.</span><span class="sxs-lookup"><span data-stu-id="2bf95-107">A cost object is an entity that costs and quantities are accumulated for.</span></span> <span data-ttu-id="2bf95-108">En kostnadsobjektenhet kan vara antingen en produkt eller produktvarianter såsom varianter för stil och färg.</span><span class="sxs-lookup"><span data-stu-id="2bf95-108">A cost object entity can be either a product or product variants, such as variants for style and color.</span></span>  

## <a name="cost-objects"></a><span data-ttu-id="2bf95-109">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="2bf95-109">Cost objects</span></span>

<span data-ttu-id="2bf95-110">Sidan **Kostnadsobjekt** visar alla kostnadsobjekt som registreras på en produkt.</span><span class="sxs-lookup"><span data-stu-id="2bf95-110">The **Cost objects** page lists all cost objects that are registered on a product.</span></span> <span data-ttu-id="2bf95-111">Kostnadsobjekten definieras av data från följande källor:</span><span class="sxs-lookup"><span data-stu-id="2bf95-111">The cost objects are defined by data from the following sources:</span></span>

-   <span data-ttu-id="2bf95-112">Produkt</span><span class="sxs-lookup"><span data-stu-id="2bf95-112">Product</span></span>
-   <span data-ttu-id="2bf95-113">Produktdimensionsgrupp</span><span class="sxs-lookup"><span data-stu-id="2bf95-113">Product dimension group</span></span>
-   <span data-ttu-id="2bf95-114">Lagringsdimensionsgrupp</span><span class="sxs-lookup"><span data-stu-id="2bf95-114">Storage dimension group</span></span>
-   <span data-ttu-id="2bf95-115">Spårningsdimensionsgrupp</span><span class="sxs-lookup"><span data-stu-id="2bf95-115">Tracking dimension group</span></span>

<span data-ttu-id="2bf95-116">**Notering:** Ett kostnadsobjekt motsvarar ett kostnadselement av typen **Direkt material**.</span><span class="sxs-lookup"><span data-stu-id="2bf95-116">**Note:** A cost object represents a cost element of the **Direct material** type only.</span></span> <span data-ttu-id="2bf95-117">Ett kostnadsobjekt och ett lagerobjekt skiljer på sättet som ett kostnadsobjekt definieras av lagerdimensionerna som har valts för ekonomiskt lager.</span><span class="sxs-lookup"><span data-stu-id="2bf95-117">A cost object and an inventory object differ in the way that a cost object is defined by the inventory dimensions that are selected for financial inventory.</span></span> <span data-ttu-id="2bf95-118">Ett objekt har till exempel följande konfiguration:</span><span class="sxs-lookup"><span data-stu-id="2bf95-118">For example, an item has the following configuration:</span></span>

-   <span data-ttu-id="2bf95-119">**Plats:** Fysiskt lager = Ja, Ekonomiskt lager = Ja</span><span class="sxs-lookup"><span data-stu-id="2bf95-119">**Site:** Physical inventory = Yes, Financial inventory = Yes</span></span>
-   <span data-ttu-id="2bf95-120">**Lagerställe:** Fysiskt lager = Ja, Ekonomiskt lager = Nej</span><span class="sxs-lookup"><span data-stu-id="2bf95-120">**Warehouse:** Physical inventory = Yes, Financial inventory = No</span></span>
-   <span data-ttu-id="2bf95-121">**Buntnr.:** Fysiskt lager = Ja, Ekonomiskt lager = Nej</span><span class="sxs-lookup"><span data-stu-id="2bf95-121">**Batch No.:** Physical inventory = Yes, Financial inventory = No</span></span>

<span data-ttu-id="2bf95-122">Följande tabell visar vad som är ett kostnadsobjekt och vad som är ett lagerobjekt.</span><span class="sxs-lookup"><span data-stu-id="2bf95-122">The following table shows what is a cost object and what is an inventory object.</span></span>

| <span data-ttu-id="2bf95-123">Objekttyp</span><span class="sxs-lookup"><span data-stu-id="2bf95-123">Object type</span></span>      | <span data-ttu-id="2bf95-124">Artikelnummer</span><span class="sxs-lookup"><span data-stu-id="2bf95-124">Item number</span></span> | <span data-ttu-id="2bf95-125">Plats</span><span class="sxs-lookup"><span data-stu-id="2bf95-125">Site</span></span> | <span data-ttu-id="2bf95-126">Lagerställe</span><span class="sxs-lookup"><span data-stu-id="2bf95-126">Warehouse</span></span> | <span data-ttu-id="2bf95-127">Buntnr.</span><span class="sxs-lookup"><span data-stu-id="2bf95-127">Batch No.</span></span> |
|------------------|-------------|------|-----------|-----------|
| <span data-ttu-id="2bf95-128">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="2bf95-128">Cost object</span></span>      | <span data-ttu-id="2bf95-129">§x</span><span class="sxs-lookup"><span data-stu-id="2bf95-129">x</span></span>           | <span data-ttu-id="2bf95-130">§x</span><span class="sxs-lookup"><span data-stu-id="2bf95-130">x</span></span>    |           |           |
| <span data-ttu-id="2bf95-131">Lagerobjekt</span><span class="sxs-lookup"><span data-stu-id="2bf95-131">Inventory object</span></span> | <span data-ttu-id="2bf95-132">§x</span><span class="sxs-lookup"><span data-stu-id="2bf95-132">x</span></span>           | <span data-ttu-id="2bf95-133">§x</span><span class="sxs-lookup"><span data-stu-id="2bf95-133">x</span></span>    |  <span data-ttu-id="2bf95-134">§x</span><span class="sxs-lookup"><span data-stu-id="2bf95-134">x</span></span>        | <span data-ttu-id="2bf95-135">§x</span><span class="sxs-lookup"><span data-stu-id="2bf95-135">x</span></span>         |

## <a name="accumulation-of-costs-and-quantities"></a><span data-ttu-id="2bf95-136">Ackumulering av kostnader och kvantiteter</span><span class="sxs-lookup"><span data-stu-id="2bf95-136">Accumulation of costs and quantities</span></span>
-   <span data-ttu-id="2bf95-137">Värdet i fältet **Värde** är en summa av följande värden:</span><span class="sxs-lookup"><span data-stu-id="2bf95-137">The value in the **Value** fieldis a sum of the following values:</span></span>
    -   <span data-ttu-id="2bf95-138">Fysiskt kostnadsbelopp</span><span class="sxs-lookup"><span data-stu-id="2bf95-138">Physical cost amount</span></span>
    -   <span data-ttu-id="2bf95-139">Ekonomiskt självkostnadsbelopp</span><span class="sxs-lookup"><span data-stu-id="2bf95-139">Financial cost amount</span></span>
    -   <span data-ttu-id="2bf95-140">Justeringar</span><span class="sxs-lookup"><span data-stu-id="2bf95-140">Adjustments</span></span>
-   <span data-ttu-id="2bf95-141">Värdet i fältet **Kvantitet** är en summa av följande värden:</span><span class="sxs-lookup"><span data-stu-id="2bf95-141">The value in the **Quantity** field is a sum of the following values:</span></span>
    -   <span data-ttu-id="2bf95-142">Mottagen</span><span class="sxs-lookup"><span data-stu-id="2bf95-142">Received</span></span>
    -   <span data-ttu-id="2bf95-143">Avdraget</span><span class="sxs-lookup"><span data-stu-id="2bf95-143">Deducted</span></span>
    -   <span data-ttu-id="2bf95-144">Bokförd kvantitet</span><span class="sxs-lookup"><span data-stu-id="2bf95-144">Posted quantity</span></span>
-   <span data-ttu-id="2bf95-145">Fältet **Genomsnittlig enhetskostnad** är ett beräknat fält.</span><span class="sxs-lookup"><span data-stu-id="2bf95-145">The **Average unit cost** field is a calculated field.</span></span> <span data-ttu-id="2bf95-146">Värdet beräknas genom att dela värdet **Värde** genom värdet **Kvantitet**.</span><span class="sxs-lookup"><span data-stu-id="2bf95-146">The value is calculated by dividing the **Value** value by the **Quantity** value.</span></span>

<span data-ttu-id="2bf95-147">**Obs!** Parametern **Inkludera fysiskt värde** påverkar inte de tidigare beräkningarna.</span><span class="sxs-lookup"><span data-stu-id="2bf95-147">**Note:** The \*\*Include physical value \*\*parameter has no effect on the preceding calculations.</span></span>

<a name="additional-resources"></a><span data-ttu-id="2bf95-148">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="2bf95-148">Additional resources</span></span>
--------

[<span data-ttu-id="2bf95-149">Produktdimensionsgrupp</span><span class="sxs-lookup"><span data-stu-id="2bf95-149">Product dimension group</span></span>](https://technet.microsoft.com/library/aa499382.aspx)

[<span data-ttu-id="2bf95-150">Lagringsdimensionsgrupp</span><span class="sxs-lookup"><span data-stu-id="2bf95-150">Storage dimension group</span></span>](https://technet.microsoft.com/library/hh209317.aspx)

[<span data-ttu-id="2bf95-151">Spårningsdimensionsgrupp</span><span class="sxs-lookup"><span data-stu-id="2bf95-151">Tracking dimension group</span></span>](https://technet.microsoft.com/library/hh209465.aspx)

[<span data-ttu-id="2bf95-152">Nyheter eller ändringar</span><span class="sxs-lookup"><span data-stu-id="2bf95-152">What's new or changed</span></span>](../../fin-and-ops/get-started/whats-new-changed.md)

[<span data-ttu-id="2bf95-153">Kostnadsposter</span><span class="sxs-lookup"><span data-stu-id="2bf95-153">Cost entries</span></span>](cost-entries.md)



