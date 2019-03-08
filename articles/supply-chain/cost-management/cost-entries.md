---
title: Kostnadsposter
description: Det här avsnittet innehåller information om kostnadsposter och när de skapas. En kostnadspost är en post för registrering av kvantiteten och kostnaden för en viss händelse.
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventCostOnhandItem
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 19131
ms.assetid: dd2663d8-bcc0-47b1-b36d-57433143487c
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cb1a218dd5e6ab3f8029788af359b89521d6afdc
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "325490"
---
# <a name="cost-entries"></a><span data-ttu-id="04059-104">Kostnadsposter</span><span class="sxs-lookup"><span data-stu-id="04059-104">Cost entries</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="04059-105">Det här avsnittet innehåller information om kostnadsposter och när de skapas.</span><span class="sxs-lookup"><span data-stu-id="04059-105">This article provides information about cost entries and when they are created.</span></span> <span data-ttu-id="04059-106">En kostnadspost är en post för registrering av kvantiteten och kostnaden för en viss händelse.</span><span class="sxs-lookup"><span data-stu-id="04059-106">A cost entry is a record that registers the quantity and cost of a given event.</span></span>

<span data-ttu-id="04059-107">Kostnadsposter är sammansättningar av lagertransaktioner som har registrerats i aktiva ekonomiska lagerdimensioner.</span><span class="sxs-lookup"><span data-stu-id="04059-107">Cost entries are aggregations of inventory transactions that are recorded on active financial inventory dimensions.</span></span>

## <a name="examples"></a><span data-ttu-id="04059-108">Exempel</span><span class="sxs-lookup"><span data-stu-id="04059-108">Examples</span></span>
### <a name="example-1-no-cost-entries-are-created"></a><span data-ttu-id="04059-109">Exempel 1: Inga kostnadsposter skapas</span><span class="sxs-lookup"><span data-stu-id="04059-109">Example 1: No cost entries are created</span></span>

<span data-ttu-id="04059-110">En överföringsjournalhändelse registreras.</span><span class="sxs-lookup"><span data-stu-id="04059-110">A transfer journal event is registered.</span></span> <span data-ttu-id="04059-111">Händelsen överför en del av artikel A från plats A till plats B. Platslagerdimensionen räknas inte som en del av kostnadsobjektet.</span><span class="sxs-lookup"><span data-stu-id="04059-111">The event transfers one piece of item A from location A to location B. The Location inventory dimension isn't considered part of the cost object.</span></span> <span data-ttu-id="04059-112">Därför skapar händelsen två lagertransaktioner och inga kostnadsposter.</span><span class="sxs-lookup"><span data-stu-id="04059-112">Therefore, the event creates two inventory transactions and no cost entries.</span></span>

### <a name="example-2-cost-entries-are-created"></a><span data-ttu-id="04059-113">Exempel 2: Kostnadsposter skapas</span><span class="sxs-lookup"><span data-stu-id="04059-113">Example 2: Cost entries are created</span></span>

<span data-ttu-id="04059-114">En överföringsjournalhändelse registreras.</span><span class="sxs-lookup"><span data-stu-id="04059-114">A transfer journal event is registered.</span></span> <span data-ttu-id="04059-115">Händelsen överför 1 st av artikel A från plats 1 till plats 2.</span><span class="sxs-lookup"><span data-stu-id="04059-115">The event transfers one piece of item A from site 1 to site 2.</span></span> <span data-ttu-id="04059-116">Platsens lagerdimension betraktas som en del av kostnadsobjektet.</span><span class="sxs-lookup"><span data-stu-id="04059-116">The Site inventory dimension is considered part of the cost object.</span></span> <span data-ttu-id="04059-117">Därför skapar händelsen två lagertransaktioner och två kostnadsposter.</span><span class="sxs-lookup"><span data-stu-id="04059-117">Therefore, the event creates two inventory transactions and two cost entries.</span></span>

### <a name="example-3-one-cost-entry-is-created"></a><span data-ttu-id="04059-118">Exempel 3: En kostnadspost skapas</span><span class="sxs-lookup"><span data-stu-id="04059-118">Example 3: One cost entry is created</span></span>

<span data-ttu-id="04059-119">En produktinleveranshändelse registreras för en inköpsorder.</span><span class="sxs-lookup"><span data-stu-id="04059-119">A product receipt event is registered for a purchase order.</span></span> <span data-ttu-id="04059-120">Händelsen registrerar 100 enheter av artikel A med en enhetskostnad på 10,00 USD.</span><span class="sxs-lookup"><span data-stu-id="04059-120">The event registers 100 pieces of item A at a unit cost of 10.00 U.S. dollars (USD).</span></span> <span data-ttu-id="04059-121">Eftersom artikel A använder serienummer för att spåra syftet med lagerhantering, skapas ett unikt serienummer för varje artikel som tas emot.</span><span class="sxs-lookup"><span data-stu-id="04059-121">Because item A uses a serial number to track the purpose of inventory management, a unique serial number is created for each item that is received.</span></span> <span data-ttu-id="04059-122">Därför skapar händelsen 100 lagertransaktioner och en kostnadspost.</span><span class="sxs-lookup"><span data-stu-id="04059-122">Therefore, the event creates 100 inventory transactions and one cost entry.</span></span>

## <a name="cost-entries-page"></a><span data-ttu-id="04059-123">Sidan Kostnadsposter</span><span class="sxs-lookup"><span data-stu-id="04059-123">Cost entries page</span></span>
<span data-ttu-id="04059-124">Den nya sidan **Kostnadsposter** visar och kontrollerar registreringar för kostnader och kvantiteter.</span><span class="sxs-lookup"><span data-stu-id="04059-124">The new **Cost entries** page lets you view and control registrations of quantities and costs.</span></span> <span data-ttu-id="04059-125">Den här sidan kompletterar sidorna **Lagertransaktion** och **Lagerkvittning**.</span><span class="sxs-lookup"><span data-stu-id="04059-125">This page complements the **Inventory transaction** and **Inventory settlement** pages.</span></span> <span data-ttu-id="04059-126">Poster registreras i kronologisk ordning för en händelse.</span><span class="sxs-lookup"><span data-stu-id="04059-126">Records are registered in chronological order for an event.</span></span> <span data-ttu-id="04059-127">Därför kan du snabbt söka efter och kontrollera ackumulerade kostnader för en viss händelse eller alla händelser som hör till ett dokument.</span><span class="sxs-lookup"><span data-stu-id="04059-127">Therefore, you can quickly find and control the accumulated costs of a specific event or all events that are related to a document.</span></span> <span data-ttu-id="04059-128">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="04059-128">Here is an example:</span></span>

-   <span data-ttu-id="04059-129">En produktinleveranshändelse registreras för artikel A. Etthundra enheter inkommer till en enhetskostnad på 10,00 USD.</span><span class="sxs-lookup"><span data-stu-id="04059-129">A product receipt event is registered for item A. One hundred pieces are received at a unit cost of 10.00 USD.</span></span>
-   <span data-ttu-id="04059-130">Några dagar efter att fakturahändelsen har registrerats ökar kostnaden till 11,00 USD.</span><span class="sxs-lookup"><span data-stu-id="04059-130">A few days after the invoice event is registered, the cost increases to 11.00 USD.</span></span> <span data-ttu-id="04059-131">Därför är totalbeloppet är 1 100 USD.</span><span class="sxs-lookup"><span data-stu-id="04059-131">Therefore, the total amount is 1,100 USD.</span></span> <span data-ttu-id="04059-132">En andra verifikation skapas för att redovisa skillnaden 100 USD.</span><span class="sxs-lookup"><span data-stu-id="04059-132">A second voucher is created to account for the difference of 100 USD.</span></span>
-   <span data-ttu-id="04059-133">Några dagar senare registreras ett tillägg på 15,00 USD på inköpsordern som täcker transportkostnaden.</span><span class="sxs-lookup"><span data-stu-id="04059-133">A few days later, a miscellaneous charge of 15.00 USD to cover the transportation cost is registered on the purchase order.</span></span>

| <span data-ttu-id="04059-134">Verifikation</span><span class="sxs-lookup"><span data-stu-id="04059-134">Voucher</span></span> | <span data-ttu-id="04059-135">Datum</span><span class="sxs-lookup"><span data-stu-id="04059-135">Date</span></span>       | <span data-ttu-id="04059-136">Referens</span><span class="sxs-lookup"><span data-stu-id="04059-136">Reference</span></span>      | <span data-ttu-id="04059-137">Nummer</span><span class="sxs-lookup"><span data-stu-id="04059-137">Number</span></span> | <span data-ttu-id="04059-138">Parti-ID</span><span class="sxs-lookup"><span data-stu-id="04059-138">Lot ID</span></span>  | <span data-ttu-id="04059-139">Kvantitet</span><span class="sxs-lookup"><span data-stu-id="04059-139">Quantity</span></span> | <span data-ttu-id="04059-140">Belopp</span><span class="sxs-lookup"><span data-stu-id="04059-140">Amount</span></span>  |
|---------|------------|----------------|--------|---------|---------------|----|
| <span data-ttu-id="04059-141">00001</span><span class="sxs-lookup"><span data-stu-id="04059-141">00001</span></span>   | <span data-ttu-id="04059-142">01-01-2015</span><span class="sxs-lookup"><span data-stu-id="04059-142">01-01-2015</span></span> | <span data-ttu-id="04059-143">Inköpsorder</span><span class="sxs-lookup"><span data-stu-id="04059-143">Purchase order</span></span> | <span data-ttu-id="04059-144">100001</span><span class="sxs-lookup"><span data-stu-id="04059-144">100001</span></span> | <span data-ttu-id="04059-145">0000101</span><span class="sxs-lookup"><span data-stu-id="04059-145">0000101</span></span> | <span data-ttu-id="04059-146">100,00</span><span class="sxs-lookup"><span data-stu-id="04059-146">100.00</span></span>   | <span data-ttu-id="04059-147">1000,00</span><span class="sxs-lookup"><span data-stu-id="04059-147">1000.00</span></span> |
| <span data-ttu-id="04059-148">00002</span><span class="sxs-lookup"><span data-stu-id="04059-148">00002</span></span>   | <span data-ttu-id="04059-149">20-01-2015</span><span class="sxs-lookup"><span data-stu-id="04059-149">20-01-2015</span></span> | <span data-ttu-id="04059-150">Inköpsorder</span><span class="sxs-lookup"><span data-stu-id="04059-150">Purchase order</span></span> | <span data-ttu-id="04059-151">100001</span><span class="sxs-lookup"><span data-stu-id="04059-151">100001</span></span> | <span data-ttu-id="04059-152">0000101</span><span class="sxs-lookup"><span data-stu-id="04059-152">0000101</span></span> |          | <span data-ttu-id="04059-153">100,00</span><span class="sxs-lookup"><span data-stu-id="04059-153">100.00</span></span>  |
| <span data-ttu-id="04059-154">00003</span><span class="sxs-lookup"><span data-stu-id="04059-154">00003</span></span>   | <span data-ttu-id="04059-155">31-01-2015</span><span class="sxs-lookup"><span data-stu-id="04059-155">31-01-2015</span></span> | <span data-ttu-id="04059-156">Justering</span><span class="sxs-lookup"><span data-stu-id="04059-156">Adjustment</span></span>     | <span data-ttu-id="04059-157">100001</span><span class="sxs-lookup"><span data-stu-id="04059-157">100001</span></span> | <span data-ttu-id="04059-158">0000101</span><span class="sxs-lookup"><span data-stu-id="04059-158">0000101</span></span> |          | <span data-ttu-id="04059-159">15,00</span><span class="sxs-lookup"><span data-stu-id="04059-159">15.00</span></span>   |

<span data-ttu-id="04059-160">Sidan **Kostnadsposter** aktiverar filtrering efter dokument-ID och dokumentdatum.</span><span class="sxs-lookup"><span data-stu-id="04059-160">The **Cost entries** page enables filtering by document ID and document date.</span></span> 

> [!NOTE]
> <span data-ttu-id="04059-161">Obs! Kostnadsposter är endast tillgängliga för [kostnadsobjekt](cost-object.md) eller frisläppta produkter.</span><span class="sxs-lookup"><span data-stu-id="04059-161">Cost entries are available only for [cost objects](cost-object.md) or released products.</span></span>

<a name="additional-resources"></a><span data-ttu-id="04059-162">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="04059-162">Additional resources</span></span>
--------

[<span data-ttu-id="04059-163">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="04059-163">Cost objects</span></span>](cost-object.md)



