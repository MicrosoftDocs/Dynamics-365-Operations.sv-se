---
title: Orsakskoder för lagerinventering
description: I det här avsnittet beskrivs hur du ställer in och tillämpar orsakskoder och inventeringsuppgifter.
author: Mirzaab
manager: tfehr
ms.date: 03/15/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventCountingReasonCodePolicy, InventCountingReasonCode
audience: Application User
ms.reviewer: kamaybac
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 66e1fb9f32aa31221f85180339b8b6ee55836be1
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4996158"
---
# <a name="reason-codes-for-inventory-counting"></a><span data-ttu-id="dd16d-103">Orsakskoder för lagerinventering</span><span class="sxs-lookup"><span data-stu-id="dd16d-103">Reason codes for inventory counting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="dd16d-104">Orsakskoder låter dig analysera resultatet från en inventeringsprocess och eventuella avvikelser som inträffar under den här processen.</span><span class="sxs-lookup"><span data-stu-id="dd16d-104">Reason codes let you analyze the results of a counting process and any discrepancies that occur during that process.</span></span> <span data-ttu-id="dd16d-105">Du kan ange en orsak till att göra inventeringen, t.ex. en trasig lastpall eller en lagerjustering som baseras på lagerexempel.</span><span class="sxs-lookup"><span data-stu-id="dd16d-105">You can specify the reason for doing the count, such as a broken pallet or a stock adjustment that is based on inventory samples.</span></span>

## <a name="recommendation"></a><span data-ttu-id="dd16d-106">Rekommendation</span><span class="sxs-lookup"><span data-stu-id="dd16d-106">Recommendation</span></span>

<span data-ttu-id="dd16d-107">Innan du ställer in systemet rekommenderar vi att du definierar en strategi för att arbeta med orsakskoder.</span><span class="sxs-lookup"><span data-stu-id="dd16d-107">Before you set up the system, we recommend that you define a strategy for working with reason codes.</span></span> <span data-ttu-id="dd16d-108">Exempelvis försök besvara följande frågor:</span><span class="sxs-lookup"><span data-stu-id="dd16d-108">For example, try to answer the following questions:</span></span>

- <span data-ttu-id="dd16d-109">Orsakskoder ska finnas på lagerställen?</span><span class="sxs-lookup"><span data-stu-id="dd16d-109">Should reason codes be mandatory on warehouses?</span></span>
- <span data-ttu-id="dd16d-110">Orsakskoder ska vara obligatoriska eller valfria över vissa objekt?</span><span class="sxs-lookup"><span data-stu-id="dd16d-110">Should reason codes be mandatory or optional on some items?</span></span>
- <span data-ttu-id="dd16d-111">Hur många orsakskoder behöver du?</span><span class="sxs-lookup"><span data-stu-id="dd16d-111">How many reason codes do you require?</span></span>
- <span data-ttu-id="dd16d-112">Hur ska användarna av streckkodsskannrar använda orsakskoder?</span><span class="sxs-lookup"><span data-stu-id="dd16d-112">How should users of barcode scanners use reason codes?</span></span> <span data-ttu-id="dd16d-113">Orsakskoderna ska vara förvalda, obligatoriska eller inte redigerbara?</span><span class="sxs-lookup"><span data-stu-id="dd16d-113">Should the reason codes be preselected, mandatory, or not editable?</span></span>
- <span data-ttu-id="dd16d-114">Behöver lagerarbetare olika orakskodbeteenden på mobila skannrar?</span><span class="sxs-lookup"><span data-stu-id="dd16d-114">Do warehouse workers require different reason code behavior on mobile scanners?</span></span> <span data-ttu-id="dd16d-115">Om svaret är Ja kan du skapa fler menyalternativ och tilldela dem till olika personer.</span><span class="sxs-lookup"><span data-stu-id="dd16d-115">If the answer is yes, you can create more menu items and assign them to different people.</span></span>

## <a name="where-reason-codes-apply"></a><span data-ttu-id="dd16d-116">Var orsakskoder tillämpas</span><span class="sxs-lookup"><span data-stu-id="dd16d-116">Where reason codes apply</span></span>

<span data-ttu-id="dd16d-117">Du kan skapa flera orsakskodprinciper och varje orsakskodprincip kan ha två cykliska orsakskodprinciper.</span><span class="sxs-lookup"><span data-stu-id="dd16d-117">You can create multiple reason code policies, and each reason code policy can have two counting reason code policies.</span></span> <span data-ttu-id="dd16d-118">Orsakskodprinciper för inventering kan användas på lagerställenivå eller artikelnivå.</span><span class="sxs-lookup"><span data-stu-id="dd16d-118">The counting reason code policies can be used at the warehouse level or the item level.</span></span>

## <a name="set-up-reason-code-policies"></a><span data-ttu-id="dd16d-119">Ställa in orsakskodprinciper</span><span class="sxs-lookup"><span data-stu-id="dd16d-119">Set up reason code policies</span></span>

1. <span data-ttu-id="dd16d-120">Välj **lagerhantering**\>**inställningar**\>**lager**\>**orsakskodprinciper för inventering**, och skapa en ny orsakskodprincip.</span><span class="sxs-lookup"><span data-stu-id="dd16d-120">Select **Inventory management** \> **Setup** \> **Inventory** \> **Counting reason code policies**, and create a new reason code policy.</span></span>
2. <span data-ttu-id="dd16d-121">På fältet **Typ av orsakskod för inventering** väljer du antingen **obligatorisk** eller **valfri** för att ange om valet av en orsakskod ska vara en valfri eller obligatorisk åtgärd på något av följande inventeringsjournaler:</span><span class="sxs-lookup"><span data-stu-id="dd16d-121">In the **Counting reason code type** field, select either **Mandatory** or **Optional** to specify whether selection of a reason code should be an optional or mandatory action in one of the following counting journals:</span></span>

    - <span data-ttu-id="dd16d-122">Rullande inventering (mobil enhet)</span><span class="sxs-lookup"><span data-stu-id="dd16d-122">Cycle Count (mobile device)</span></span>
    - <span data-ttu-id="dd16d-123">Punktinventering (mobil enhet)</span><span class="sxs-lookup"><span data-stu-id="dd16d-123">Spot Count (mobile device)</span></span>
    - <span data-ttu-id="dd16d-124">Tröskelinventering (mobil enhet)</span><span class="sxs-lookup"><span data-stu-id="dd16d-124">Threshold Count (mobile device)</span></span>
    - <span data-ttu-id="dd16d-125">Justering in (mobil enhet)</span><span class="sxs-lookup"><span data-stu-id="dd16d-125">Adjustment In (mobile device)</span></span>
    - <span data-ttu-id="dd16d-126">Justering ut (mobil enhet)</span><span class="sxs-lookup"><span data-stu-id="dd16d-126">Adjustment Out (mobile device)</span></span>
    - <span data-ttu-id="dd16d-127">Inventeringsjournal (rich-klient)</span><span class="sxs-lookup"><span data-stu-id="dd16d-127">Counting Journal (rich client)</span></span>

<span data-ttu-id="dd16d-128">Du kan också ställa in orsakskoder för enskilda lagerställen och produkter.</span><span class="sxs-lookup"><span data-stu-id="dd16d-128">You can also set up reason codes for individual warehouses and for products.</span></span> <span data-ttu-id="dd16d-129">Inställningen av orsakskod för produkter kan ignorera inställningarna för lagerställen.</span><span class="sxs-lookup"><span data-stu-id="dd16d-129">The reason code setup for products can disregard the setup for warehouses.</span></span>

## <a name="mandatory-reason-codes"></a><span data-ttu-id="dd16d-130">Obligatoriska orsakskoder</span><span class="sxs-lookup"><span data-stu-id="dd16d-130">Mandatory reason codes</span></span>

<span data-ttu-id="dd16d-131">Om parametern **obligatorisk** anges i konfigurationen för orsakskoder för lager eller artiklar, kan inventeringsjournalen inte slutföras och stängas tills en orsakskod har angetts.</span><span class="sxs-lookup"><span data-stu-id="dd16d-131">If the **Mandatory** parameter is set in the configuration of reason codes for warehouses or items, the counting journal can't be completed and closed until a reason code is provided.</span></span>

### <a name="set-up-reason-codes-for-warehouses"></a><span data-ttu-id="dd16d-132">Ställ in orsakskoder för lagerställen</span><span class="sxs-lookup"><span data-stu-id="dd16d-132">Set up reason codes for warehouses</span></span>

1. <span data-ttu-id="dd16d-133">Välj **Lagerhantering** \> **Inställningar** \> **Lagerindelning** \> **Lagerställen**</span><span class="sxs-lookup"><span data-stu-id="dd16d-133">Select **Inventory Management** \> **Setup** \> **Inventory breakdown** \> **Warehouses**.</span></span>
2. <span data-ttu-id="dd16d-134">På fliken **lagerställe** i fältet **Policy för orsakskod för inventering** väljer du ett av följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="dd16d-134">On the **Warehouse** tab, in the **Counting reason code policy** field, select one of the following options:</span></span>

    - <span data-ttu-id="dd16d-135">**Tom** - parametern som ställts in för artikeln används för att bestämma om inventeringsjournaler är obligatoriska för produkten.</span><span class="sxs-lookup"><span data-stu-id="dd16d-135">**Blank** – The parameter that is set up for the item is used to determine whether counting journals are mandatory for the product.</span></span>
    - <span data-ttu-id="dd16d-136">**Obligatorisk** – en orsakskod krävs alltid på inventeringsjournaler för lagerstället.</span><span class="sxs-lookup"><span data-stu-id="dd16d-136">**Mandatory** – A reason code is always required on counting journals for the warehouse.</span></span>
    - <span data-ttu-id="dd16d-137">**Tillval** – en orsakskod krävs inte på inventeringsjournaler för lagerstället.</span><span class="sxs-lookup"><span data-stu-id="dd16d-137">**Optional** – A reason code isn't required on counting journals for the warehouse.</span></span>

### <a name="set-up-reason-codes-for-products"></a><span data-ttu-id="dd16d-138">Ställ in orsakskoder för produkter</span><span class="sxs-lookup"><span data-stu-id="dd16d-138">Set up reason codes for products</span></span>

1. <span data-ttu-id="dd16d-139">Välj **Produktinformationshantering** \> **Produkter** \> **Frisläppta produktersamprodukt**.</span><span class="sxs-lookup"><span data-stu-id="dd16d-139">Select **Product information management** \> **Products** \> **Released products**.</span></span>
2. <span data-ttu-id="dd16d-140">På fliken **Produkt** välj **Policy för orsakskod för inventering** och sedan väljer du ett av följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="dd16d-140">On the **Product** tab, select **Counting reason code policy**, and then select one of the following options:</span></span>

    - <span data-ttu-id="dd16d-141">**Tom** - parametern som ställts in för lagerstället används för att bestämma om inventeringsjournaler är obligatoriska för produkten.</span><span class="sxs-lookup"><span data-stu-id="dd16d-141">**Blank** – The parameter that is set up for the warehouse is used to determine whether counting journals are mandatory for the product.</span></span>
    - <span data-ttu-id="dd16d-142">**Obligatorisk** – en orsakskod krävs alltid på inventeringsjournaler för produkten.</span><span class="sxs-lookup"><span data-stu-id="dd16d-142">**Mandatory** – A reason code is always required on counting journals for the product.</span></span> <span data-ttu-id="dd16d-143">Den här inställningen åsidosätter inställningen för varje orsakskod på lagernivå.</span><span class="sxs-lookup"><span data-stu-id="dd16d-143">This setting overrides any reason code setting at the warehouse level.</span></span>
    - <span data-ttu-id="dd16d-144">**Tillval** – en orsakskod krävs inte på inventeringsjournaler för produkten.</span><span class="sxs-lookup"><span data-stu-id="dd16d-144">**Optional** – A reason code isn't required on counting journals for the product.</span></span> <span data-ttu-id="dd16d-145">Den här inställningen åsidosätter inställningen för varje orsakskod på lagernivå.</span><span class="sxs-lookup"><span data-stu-id="dd16d-145">This setting overrides any reason code setting at the warehouse level.</span></span>

### <a name="use-reason-codes-in-counting-journals"></a><span data-ttu-id="dd16d-146">Använd orsakskoder i inventeringsjournaler</span><span class="sxs-lookup"><span data-stu-id="dd16d-146">Use reason codes in counting journals</span></span>

<span data-ttu-id="dd16d-147">I en inventeringsjournal lägger du till orsakskoder för inventeringar av följande typer:</span><span class="sxs-lookup"><span data-stu-id="dd16d-147">In a counting journal, you can add reason codes for counts of the following types:</span></span>

- <span data-ttu-id="dd16d-148">Rullande inventering</span><span class="sxs-lookup"><span data-stu-id="dd16d-148">Cycle Count</span></span>
- <span data-ttu-id="dd16d-149">Punktinventering</span><span class="sxs-lookup"><span data-stu-id="dd16d-149">Spot Count</span></span>
- <span data-ttu-id="dd16d-150">Tröskelinventering</span><span class="sxs-lookup"><span data-stu-id="dd16d-150">Threshold Count</span></span>
- <span data-ttu-id="dd16d-151">Justering in</span><span class="sxs-lookup"><span data-stu-id="dd16d-151">Adjustment In</span></span>
- <span data-ttu-id="dd16d-152">Justering ut</span><span class="sxs-lookup"><span data-stu-id="dd16d-152">Adjustment Out</span></span>

<span data-ttu-id="dd16d-153">Orsakskoderna läggs till journalraderna i inventeringsjournaler av typen **inventeringsjournal**.</span><span class="sxs-lookup"><span data-stu-id="dd16d-153">Reason codes are added to the journal lines in counting journals of the **Counting journal** type.</span></span>

1. <span data-ttu-id="dd16d-154">Välj **Lagerhantering** \> **Journalposter** \> **Artikelräkning** \> **Inventering**.</span><span class="sxs-lookup"><span data-stu-id="dd16d-154">Select **Inventory management** \> **Journal entries** \> **Item counting** \> **Counting**.</span></span>
2. <span data-ttu-id="dd16d-155">I raddetaljerna för inventeringsjournalen, i fältet **Orsakskod för inventering** väljer du ett alternativ.</span><span class="sxs-lookup"><span data-stu-id="dd16d-155">In the line details of the counting journal, in the **Counting reason code** field, select an option.</span></span>

### <a name="view-the-counting-history-as-its-recorded-by-reason-codes"></a><span data-ttu-id="dd16d-156">Visa inventeringshistorik enligt vad som noterats av orsakskoder</span><span class="sxs-lookup"><span data-stu-id="dd16d-156">View the counting history as it's recorded by reason codes</span></span>

- <span data-ttu-id="dd16d-157">Välj **lagerhantering**\>**förfrågningar och rapporter**\>**inventeringshistorik**, och sedan i fältet **Orsakskod för inventering** visar du inventeringshistorik som har registreras via en orsakskod.</span><span class="sxs-lookup"><span data-stu-id="dd16d-157">Select **Inventory management** \> **Inquiries and reports** \> **Counting history**, and then, in the **Counting reason code** field, view the counting history that has been recorded through a reason code.</span></span>

### <a name="use-a-reason-code-for-a-quantity-adjustment"></a><span data-ttu-id="dd16d-158">Använda en orsakskod för en kvantitetsjustering</span><span class="sxs-lookup"><span data-stu-id="dd16d-158">Use a reason code for a quantity adjustment</span></span>

1. <span data-ttu-id="dd16d-159">På sidan **lagerbehållning** ange **Justera kvantitet**.</span><span class="sxs-lookup"><span data-stu-id="dd16d-159">On the **On-hand inventory** page, select **Adjust quantity**.</span></span> <span data-ttu-id="dd16d-160">Du kan öppna sidan **lagerbehållning** på flera olika sätt.</span><span class="sxs-lookup"><span data-stu-id="dd16d-160">You can open the **On-hand inventory** page in several ways.</span></span> <span data-ttu-id="dd16d-161">Välj t.ex. **Lagerhantering** \> **Förfrågningar och rapporter** \> **Lagerbehållning**.</span><span class="sxs-lookup"><span data-stu-id="dd16d-161">For example, select **Inventory management** \> **Inquiries and reports** \> **On-hand inventory**.</span></span>
2. <span data-ttu-id="dd16d-162">Välj **Justera kvantitet** och sedan, i fältet **Orsakskod för inventering** väljer du en orsakskod.</span><span class="sxs-lookup"><span data-stu-id="dd16d-162">Select **Adjust quantity**, and then, in the **Counting reason code** field, select a reason code.</span></span>

### <a name="configure-reason-codes-for-mobile-device-menu-items"></a><span data-ttu-id="dd16d-163">Konfigurera orsakskoder för menyalternativ för mobila enheter</span><span class="sxs-lookup"><span data-stu-id="dd16d-163">Configure reason codes for mobile device menu items</span></span>

<span data-ttu-id="dd16d-164">Du kan konfigurera orsakskoder för alla typer av inventering på ett menyalternativ för mobila enheter.</span><span class="sxs-lookup"><span data-stu-id="dd16d-164">You can configure reason codes for any type of count on a mobile device menu item.</span></span> <span data-ttu-id="dd16d-165">Konfigurationen för menyalternativ för mobil enhet omfattar följande information:</span><span class="sxs-lookup"><span data-stu-id="dd16d-165">The configuration of the mobile device menu item includes the following information:</span></span>

- <span data-ttu-id="dd16d-166">Om orsakskoden visas till mobiltelefonarbetaren under inventering.</span><span class="sxs-lookup"><span data-stu-id="dd16d-166">Whether the reason code is shown to the mobile device worker during counting.</span></span>
- <span data-ttu-id="dd16d-167">Standardorsakskoden som visas på ett menyalternativ för mobila enheter.</span><span class="sxs-lookup"><span data-stu-id="dd16d-167">The default reason code that is shown on a mobile device menu item.</span></span>
- <span data-ttu-id="dd16d-168">Om användaren kan redigera orsakskoden.</span><span class="sxs-lookup"><span data-stu-id="dd16d-168">Whether the user can edit the reason code.</span></span>

### <a name="set-up-reason-codes-on-a-mobile-device"></a><span data-ttu-id="dd16d-169">Ställ in orsakskoder på en mobil enhet</span><span class="sxs-lookup"><span data-stu-id="dd16d-169">Set up reason codes on a mobile device</span></span>

1. <span data-ttu-id="dd16d-170">Välj **Lagerstyrning** \> **InställningarSetup** \> **Mobil enhet** \> **Menyalternativ på mobil enhet**.</span><span class="sxs-lookup"><span data-stu-id="dd16d-170">Select **Warehouse management** \> **Setup** \> **Mobile device** \> **Mobile device menu items**.</span></span>
2. <span data-ttu-id="dd16d-171">På fliken **Rullande inventering** Välj **Rullande inventering**.</span><span class="sxs-lookup"><span data-stu-id="dd16d-171">On the **Cycle count** tab, select **Cycle counting**.</span></span>
3. <span data-ttu-id="dd16d-172">På fältet **Orsakskod för standardinventering**, ställ in standardorsakskoden som ska registreras när inventeringen är klar genom att använda menyalternativet för mobil enhet.</span><span class="sxs-lookup"><span data-stu-id="dd16d-172">In the **Default counting reason code** field, set the default reason code that should be recorded when counting is done by using the mobile device menu item.</span></span>
4. <span data-ttu-id="dd16d-173">I fältet **Visa orsakskod för inventering** välj **Rad** för att visa orsakskoden efter att varje avvikelse har registrerats.</span><span class="sxs-lookup"><span data-stu-id="dd16d-173">In the **Display counting reason code** field, select **Line** to show the reason code after each variance is recorded.</span></span> <span data-ttu-id="dd16d-174">Du kan också välja **Dölj** om orsakskoden inte visas.</span><span class="sxs-lookup"><span data-stu-id="dd16d-174">Alternatively, select **Hide** if the reason code shouldn't be shown.</span></span>
5. <span data-ttu-id="dd16d-175">Ange alternativet **Redigera orsakskod för inventering** till antingen **Ja** eller **Nej**.</span><span class="sxs-lookup"><span data-stu-id="dd16d-175">Set the **Edit counting reason code** option to either **Yes** or **No**.</span></span> <span data-ttu-id="dd16d-176">Om du anger det här alternativet till **Ja** kan arbetaren redigera orsakskoden när det visas på den mobila enheten under inventering.</span><span class="sxs-lookup"><span data-stu-id="dd16d-176">If you set this option to **Yes**, the worker can edit the reason code when it's shown on the mobile device during counting.</span></span>

> [!NOTE]
> <span data-ttu-id="dd16d-177">Knappen **rullande inventering** kan aktiveras på alla menyalternativ för mobil enhet när inventering kan göras.</span><span class="sxs-lookup"><span data-stu-id="dd16d-177">The **Cycle counting** button can be enabled on any mobile device menu item where counting can be done.</span></span> <span data-ttu-id="dd16d-178">Exempel inkluderar menyalternativ för punktinventeringar, användarstyrt arbete och systemstyrt arbete.</span><span class="sxs-lookup"><span data-stu-id="dd16d-178">Example include the menu items for spot counts, user-directed work, and system-directed work.</span></span>

## <a name="cycle-count-approvals"></a><span data-ttu-id="dd16d-179">Godkännande av rullande inventering</span><span class="sxs-lookup"><span data-stu-id="dd16d-179">Cycle count approvals</span></span>

<span data-ttu-id="dd16d-180">Användaren kan ändra orsakskoden som är kopplad till inventeringen innan inventeringen kan godkännas.</span><span class="sxs-lookup"><span data-stu-id="dd16d-180">Before a count is approved, the user can change the reason code that is associated with the count.</span></span> <span data-ttu-id="dd16d-181">Orsakskoden anges på journalraderna som skapas när inventeringen godkänns.</span><span class="sxs-lookup"><span data-stu-id="dd16d-181">When the count is approved, the reason code is entered on the counting journal lines.</span></span>

### <a name="modify-cycle-count-approvals"></a><span data-ttu-id="dd16d-182">Ändra godkännande av rullande inventering</span><span class="sxs-lookup"><span data-stu-id="dd16d-182">Modify cycle count approvals</span></span>

1. <span data-ttu-id="dd16d-183">Välj **lagerstyrning**\>**rullande inventering**\>**Granskning av väntande rullande inventeringsarbete**.</span><span class="sxs-lookup"><span data-stu-id="dd16d-183">Select **Warehouse management** \> **Cycle counting** \> **Cycle count work pending review**.</span></span>
2. <span data-ttu-id="dd16d-184">Välj **Rullande inventering** och sedan, i fältet **Orsakskod** väljer du en ny orsakskod.</span><span class="sxs-lookup"><span data-stu-id="dd16d-184">Select **Cycle counting**, and then, in the **Reason code** field, select a new reason code.</span></span>

### <a name="modify-the-mobile-device-menu-item-for-adjustment-in-and-adjustment-out"></a><span data-ttu-id="dd16d-185">Ändra menyalternativet för mobil enhet för Justering in och Justering ut</span><span class="sxs-lookup"><span data-stu-id="dd16d-185">Modify the mobile device menu item for Adjustment in and Adjustment out</span></span>

1. <span data-ttu-id="dd16d-186">Välj **lagerstyrning**\>**inställningar**\>**mobil enhet**\>**menyalternativ för mobil enhet**, och välj sedan **justering in och ut**.</span><span class="sxs-lookup"><span data-stu-id="dd16d-186">Select **Warehouse management** \> **Setup** \> **Mobile device** \> **Mobile device menu items**, and then select **Adjustment in and out**.</span></span>
2. <span data-ttu-id="dd16d-187">Ange alternativet **Använd befintligt arbete** till **Nej**.</span><span class="sxs-lookup"><span data-stu-id="dd16d-187">Set the **Use existing work** option to **No**.</span></span>
3. <span data-ttu-id="dd16d-188">I fältet **Process för att skapa arbete** väljer du **justering i**.</span><span class="sxs-lookup"><span data-stu-id="dd16d-188">In the **Work creation process** field, select **Adjustment in**.</span></span>

<span data-ttu-id="dd16d-189">Följande fält läggs till på menyalternativet för mobil enhet när **justering in** eller **justering ut** markeras under process för att skapa arbete:</span><span class="sxs-lookup"><span data-stu-id="dd16d-189">The following fields will be added to the mobile device menu item when **Adjustment in** or **Adjustment out** is selected during the work creation process:</span></span>

- <span data-ttu-id="dd16d-190">Orsakskod för standardinventering</span><span class="sxs-lookup"><span data-stu-id="dd16d-190">Default counting reason code</span></span>
- <span data-ttu-id="dd16d-191">Visa orsakskod för inventering</span><span class="sxs-lookup"><span data-stu-id="dd16d-191">Display counting reason code</span></span>
- <span data-ttu-id="dd16d-192">Redigera orsakskod för inventering</span><span class="sxs-lookup"><span data-stu-id="dd16d-192">Edit counting reason code</span></span>
