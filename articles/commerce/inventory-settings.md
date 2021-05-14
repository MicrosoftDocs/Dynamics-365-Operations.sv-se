---
title: Använd lagerinställningar
description: Det här avsnittet behandlar lagerinställningar och beskriver hur du använder dem i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: dd3db0039525c18521ad6a42b2f281976b7b236a
ms.sourcegitcommit: 593438a145672c55ff6a910eabce2939300b40ad
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/23/2021
ms.locfileid: "5937420"
---
# <a name="apply-inventory-settings"></a><span data-ttu-id="b8226-103">Använd lagerinställningar</span><span class="sxs-lookup"><span data-stu-id="b8226-103">Apply inventory settings</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="b8226-104">Det här avsnittet behandlar lagerinställningar och beskriver hur du använder dem i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="b8226-104">This topic covers inventory settings and describes how to apply them in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="b8226-105">Lagerinställningarna anger om lagret ska kontrolleras innan produkter läggs till i vagnen.</span><span class="sxs-lookup"><span data-stu-id="b8226-105">Inventory settings specify whether inventory should be checked before products are added to the cart.</span></span> <span data-ttu-id="b8226-106">De definierar också lagerrelaterade marknadsföringsmeddelanden, t.ex. "i lagret" och "bara några få kvar".</span><span class="sxs-lookup"><span data-stu-id="b8226-106">They also define inventory-related merchandising messages, such as "In stock" and "Only a few left."</span></span> <span data-ttu-id="b8226-107">Dessa inställningar garanterar att en produkt inte kan köpas om den inte är i lager.</span><span class="sxs-lookup"><span data-stu-id="b8226-107">These settings ensure that a product can't be purchased if it's out of stock.</span></span>

<span data-ttu-id="b8226-108">Dynamics 365 Commerce tillhandahåller uppskattningar av tillgänglig lagerbehållning för produkter.</span><span class="sxs-lookup"><span data-stu-id="b8226-108">Dynamics 365 Commerce provides estimates of on-hand availability for products.</span></span> <span data-ttu-id="b8226-109">Information om hur uppskattad behållnings tillgänglighet beräknas finns i [Beräkna lagerdisposition för butikskanaler](calculated-inventory-retail-channels.md).</span><span class="sxs-lookup"><span data-stu-id="b8226-109">For information about how estimated on-hand availability is calculated, see [Calculate inventory availability for retail channels](calculated-inventory-retail-channels.md).</span></span>

<span data-ttu-id="b8226-110">I Commerce webbplatsskaparen kan lagertrösklar och intervall definieras för en produkt eller en kategori.</span><span class="sxs-lookup"><span data-stu-id="b8226-110">In Commerce site builder, inventory thresholds and ranges can be defined for a product or a category.</span></span> <span data-ttu-id="b8226-111">De bestämmer om lager kan klassificeras som i lager, låglager eller utanför lagret.</span><span class="sxs-lookup"><span data-stu-id="b8226-111">They determine whether inventory can be classified as in stock, low stock, or out of stock.</span></span> <span data-ttu-id="b8226-112">Mer information finns i [Konfigurera inventeringsbuffertar and lagernivåer](inventory-buffers-levels.md).</span><span class="sxs-lookup"><span data-stu-id="b8226-112">For details, see [Configure inventory buffers and inventory levels](inventory-buffers-levels.md).</span></span>

> [!NOTE]
> <span data-ttu-id="b8226-113">Stöd för lagertrösklar och -intervall är tillgängliga i Dynamics 365 Commerce 10.0.12-versionen.</span><span class="sxs-lookup"><span data-stu-id="b8226-113">Support for inventory thresholds and ranges is available in the Dynamics 365 Commerce 10.0.12 release.</span></span>

## <a name="inventory-settings"></a><span data-ttu-id="b8226-114">Lagerinställningar</span><span class="sxs-lookup"><span data-stu-id="b8226-114">Inventory settings</span></span>

<span data-ttu-id="b8226-115">I Commerce, lagerinställningar definieras på **Platsinställningar \> Tillägg \> Lagerhantering** i webbplatsskaparen.</span><span class="sxs-lookup"><span data-stu-id="b8226-115">In Commerce, inventory settings are defined at **Site Settings \> Extensions \> Inventory Management** in site builder.</span></span> <span data-ttu-id="b8226-116">Det finns fem lagerinställningar, varav en är föråldrad (inaktuell):</span><span class="sxs-lookup"><span data-stu-id="b8226-116">There are five inventory settings, one of which is obsolete (deprecated):</span></span>

- <span data-ttu-id="b8226-117">**Aktivera lagerkontroll i appen** – Den här inställningen aktiverar en produklagerkontroll.</span><span class="sxs-lookup"><span data-stu-id="b8226-117">**Enable stock check in app** – This setting turns on a product inventory check.</span></span> <span data-ttu-id="b8226-118">När du köper kartongen, kundvagnen och hämtningen i butiksmoduler kontrolleras produktlagret och då kan en produkt bara läggas till i kundvagnen om det finns tillgängligt lager.</span><span class="sxs-lookup"><span data-stu-id="b8226-118">Buy box, cart, and pick up in store modules will then check product inventory, and will allow a product to be added to the cart only if inventory is available.</span></span>
- <span data-ttu-id="b8226-119">**Lagernivå baserad på** – den här inställningen definierar hur lagernivåer beräknas.</span><span class="sxs-lookup"><span data-stu-id="b8226-119">**Inventory level based on** – This setting defines how inventory levels are calculated.</span></span> <span data-ttu-id="b8226-120">De tillgängliga värdena är **Total tillgänglig**, **fysiskt tillgänglig** och **tröskel för utanför lagret**.</span><span class="sxs-lookup"><span data-stu-id="b8226-120">The available values are **Total Available**, **Physical Available**, and **Out of stock threshold**.</span></span> <span data-ttu-id="b8226-121">I Commerce, lagertrösklar och intervall definieras för en varje produkt och kategori.</span><span class="sxs-lookup"><span data-stu-id="b8226-121">In Commerce, inventory threshold and ranges can be defined for each product and category.</span></span> <span data-ttu-id="b8226-122">Lager-API:erna returnerar produktinformation för båda egenskap **Total tillgänglig** och egenskap **Fysisk tillgänglig**.</span><span class="sxs-lookup"><span data-stu-id="b8226-122">The inventory APIs return product inventory information for both the **Total Available** property and the **Physical Available** property.</span></span> <span data-ttu-id="b8226-123">Återförsäljaren bestämmer om det **totala tillgängliga** eller **fysiskt tillgängliga** värdet ska användas för att fastställa lagerinventeringen och motsvarande intervall för status som lager och inte artiklar.</span><span class="sxs-lookup"><span data-stu-id="b8226-123">The retailer decides whether the **Total Available** or **Physical Available** value should be used to determine the inventory count and the corresponding ranges for in-stock and out-of-stock statuses.</span></span>

    <span data-ttu-id="b8226-124">Värdet **tröskel för utanför lagret** för inställning **Lagernivå baserad på** är ett gammalt (äldre) föråldrat värde.</span><span class="sxs-lookup"><span data-stu-id="b8226-124">The **Out of stock threshold** value of the **Inventory level based on** setting is an old (legacy), obsolete value.</span></span> <span data-ttu-id="b8226-125">När lagerinventeringen väljs bestäms resultatet av det **totala tillgängliga** värdet, men tröskeln definieras av **inställningen för frånvaro av lagertröskel** som beskrivs senare.</span><span class="sxs-lookup"><span data-stu-id="b8226-125">When it's selected, the inventory count is determined from the results of the **Total Available** value, but the threshold is defined by the **Out of stock threshold** numeric setting that is described later.</span></span> <span data-ttu-id="b8226-126">Den här tröskelinställningen gäller för alla produkter på en näthandelssajt.</span><span class="sxs-lookup"><span data-stu-id="b8226-126">This threshold setting applies to all products across an e-commerce site.</span></span> <span data-ttu-id="b8226-127">Om lagret är lägre än tröskelnumret anses en produkt vara utanför lagret.</span><span class="sxs-lookup"><span data-stu-id="b8226-127">If inventory is below the threshold number, a product is considered out of stock.</span></span> <span data-ttu-id="b8226-128">I annat fall betraktas det som i lager.</span><span class="sxs-lookup"><span data-stu-id="b8226-128">Otherwise, it's considered in stock.</span></span> <span data-ttu-id="b8226-129">Möjligheterna för **tröskelvärdet för frånvaro** är begränsade och vi rekommenderar inte att du använder det i version 10.0.12 och senare.</span><span class="sxs-lookup"><span data-stu-id="b8226-129">The capabilities of the **Out of stock threshold** value are limited, and we don't recommend that you use it in version 10.0.12 and later.</span></span>

- <span data-ttu-id="b8226-130">**Lagernivå för flera lagerställen** – Med den här inställningen kan lagernivån beräknas mot standardlagerstället eller flera lagerställen.</span><span class="sxs-lookup"><span data-stu-id="b8226-130">**Inventory level for multiple warehouses** – This setting enables the inventory level to be calculated against the default warehouse or multiple warehouses.</span></span> <span data-ttu-id="b8226-131">Alternativet **Baserat på enskilda lagerställen** beräknar lagernivåer baserat på standardlagerstället.</span><span class="sxs-lookup"><span data-stu-id="b8226-131">The **Based on individual warehouse** option will calculate inventory levels based on the default warehouse.</span></span> <span data-ttu-id="b8226-132">Alternativt kan en näthandelsplats peka på flera lagerställen i syfte att underlätta uppfyllelsen.</span><span class="sxs-lookup"><span data-stu-id="b8226-132">Alternatively, an e-commerce site can point to multiple warehouses to facilitate fulfillment.</span></span> <span data-ttu-id="b8226-133">I sådana fall används alternativet **Baserat på aggregering för leverans- och upphämtningslagerställen** för att ange lagertillgänglighet.</span><span class="sxs-lookup"><span data-stu-id="b8226-133">In that case, the **Based on aggregate for Shipping and Pickup warehouses** option is used to indicate stock availability.</span></span> <span data-ttu-id="b8226-134">När en kund till exempel köper in en artikel och väljer "leverans" som leveransläge kan artikeln skeppas från valfritt lagerställe i uppfyllelsegruppen som har tillgängligt lager.</span><span class="sxs-lookup"><span data-stu-id="b8226-134">For example, when a customer purchases an item and selects "shipping" as the delivery mode, the item can be shipped from any warehouse in the fulfillment group that has available inventory.</span></span> <span data-ttu-id="b8226-135">På sidan för produktinformation (PDP) visas ett "I lager"-meddelande för leverans om något tillgängligt leveranslager i uppfyllelsegruppen har lager.</span><span class="sxs-lookup"><span data-stu-id="b8226-135">The product details page (PDP) will show an "In stock" message for shipping if any available shipping warehouse in the fulfillment group has inventory.</span></span> 

> [!IMPORTANT] 
> <span data-ttu-id="b8226-136">Inställningen **Lagernivån för flera lagerställen** är tillgänglig i version 10.0.19 av Commerce.</span><span class="sxs-lookup"><span data-stu-id="b8226-136">The **Inventory level for multiple warehouses** setting is available as of the Commerce version 10.0.19 release.</span></span> <span data-ttu-id="b8226-137">Om du uppdaterar från en äldre version av Commerce måste du uppdatera filen appsettings.json manuellt.</span><span class="sxs-lookup"><span data-stu-id="b8226-137">If you're updating from an older version of Commerce, you must manually update the appsettings.json file.</span></span> <span data-ttu-id="b8226-138">För instruktioner, se [SDK- och modulbiblioteksuppdateringar](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).</span><span class="sxs-lookup"><span data-stu-id="b8226-138">For instructions, see [SDK and module library updates](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).</span></span>

- <span data-ttu-id="b8226-139">**Lagerområden** – med den här inställningen definieras de lagerintervall som meddelandet visas för i moduler.</span><span class="sxs-lookup"><span data-stu-id="b8226-139">**Inventory ranges** – This setting defines the inventory ranges that message are shown for on site modules.</span></span> <span data-ttu-id="b8226-140">Den gäller bara om antingen värdet **totala tillgängliga** eller det **fysiska tillgängliga värdet** har valts för inställning **lagernivån baserat på**.</span><span class="sxs-lookup"><span data-stu-id="b8226-140">It's applicable only if either the **Total Available** value or the **Physical Available** value is selected for the **Inventory level based on** setting.</span></span> <span data-ttu-id="b8226-141">De tillgängliga värdena är **alla**, **låg och ur lagret** och inte **på lagret**.</span><span class="sxs-lookup"><span data-stu-id="b8226-141">The available values are **All**, **Low and out of stock**, and **Out of stock**.</span></span>

    - <span data-ttu-id="b8226-142">När **alla** är markerat visas meddelanden för alla lagerområden, från lagret ("tillgängligt") i brist på lager ("tillgängligt").</span><span class="sxs-lookup"><span data-stu-id="b8226-142">When **All** is selected, messages for all inventory ranges, from in stock ("Available" message) to out of stock ("Out of stock" message), will be shown.</span></span>
    - <span data-ttu-id="b8226-143">När **låg och inte i lager** är markerat visas meddelanden för alla lagerområden förutom från lagret ("tillgängligt").</span><span class="sxs-lookup"><span data-stu-id="b8226-143">When **Low and out of stock** is selected, messages for all inventory ranges except in stock ("Available" message) will be shown.</span></span>
    - <span data-ttu-id="b8226-144">När **inte i lager** är markerat visas endast meddelandet "inte i lager".</span><span class="sxs-lookup"><span data-stu-id="b8226-144">When **Out of stock** is selected, only the "Out of stock" message will be shown.</span></span>

- <span data-ttu-id="b8226-145">**Tröskel för inte i lager** – den här gamla numeriska inställningen börjar gälla först om värdet **tröskelvärdet för inte i lager** har valts för inställningen **lagernivå baserat på**.</span><span class="sxs-lookup"><span data-stu-id="b8226-145">**Out of stock threshold** – This old numeric setting will take effect only if the **Out of stock threshold** value is selected for the **Inventory level based on** setting.</span></span>

> [!IMPORTANT] 
> <span data-ttu-id="b8226-146">Dessa inställningar finns i Dynamics 365 Commerce 10.0.12 versionen.</span><span class="sxs-lookup"><span data-stu-id="b8226-146">These settings are available in the Dynamics 365 Commerce 10.0.12 release.</span></span> <span data-ttu-id="b8226-147">Om du uppdaterar från en äldre version av Dynamics 365 Commerce måste du uppdatera filen appsettings.json manuellt.</span><span class="sxs-lookup"><span data-stu-id="b8226-147">If you are updating from an older version of Dynamics 365 Commerce, you must manually update the appsettings.json file.</span></span> <span data-ttu-id="b8226-148">Information om hur du uppdaterar filen appsettings.json finns i [SDK- och modulens biblioteksuppdateringar](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).</span><span class="sxs-lookup"><span data-stu-id="b8226-148">For instructions on updating the appsettings.json file, see [SDK and module library updates](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).</span></span>

## <a name="modules-that-use-inventory-settings"></a><span data-ttu-id="b8226-149">Moduler som använder lagerinställningar</span><span class="sxs-lookup"><span data-stu-id="b8226-149">Modules that use inventory settings</span></span>

<span data-ttu-id="b8226-150">Ikonmodulerna inköpsruta, önskelista, butiksväljare, kundvagn och kundvagnsikon använder lagerinställningar för att visa lagerområden och meddelanden.</span><span class="sxs-lookup"><span data-stu-id="b8226-150">Buy box, wishlist, store selector, cart, and cart icon modules use inventory settings to show the inventory ranges and messages.</span></span>

<span data-ttu-id="b8226-151">I exemplet i följande illustration visar en PDP ett meddelande om "I lager" ("Tillgänglig").</span><span class="sxs-lookup"><span data-stu-id="b8226-151">In the example in the following illustration, a PDP is showing an in-stock ("Available") message.</span></span>

![Exempel på en PDP-modul som har ett upplagratmeddelande](./media/pdp-InStock.png)

<span data-ttu-id="b8226-153">I exemplet i följande illustration visar en PDP ett meddelande om "Ej i lager".</span><span class="sxs-lookup"><span data-stu-id="b8226-153">In the example in the following illustration, a PDP is showing an "Out of stock" message.</span></span>

![Exempel på en PDP-modul som har ett ej i lager-meddelande](./media/pdp-outofstock.png)

<span data-ttu-id="b8226-155&quot;>I exemplet i följande illustration visar en kundvagn ett meddelande om &quot;I lager&quot; (&quot;Tillgänglig").</span><span class="sxs-lookup"><span data-stu-id="b8226-155">In the example in the following illustration, a cart is showing an in-stock ("Available") message.</span></span>

![Exempel på en kundvagnmodul som har ett upplagratmeddelande](./media/cart-instock.png)

## <a name="additional-resources"></a><span data-ttu-id="b8226-157">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="b8226-157">Additional resources</span></span>

[<span data-ttu-id="b8226-158">Översikt över modulbibliotek</span><span class="sxs-lookup"><span data-stu-id="b8226-158">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="b8226-159">Konfigurera lagerkvantiteter och lagernivåer</span><span class="sxs-lookup"><span data-stu-id="b8226-159">Configure inventory buffers and inventory levels</span></span>](inventory-buffers-levels.md)

[<span data-ttu-id="b8226-160">Kundvagnsmodul</span><span class="sxs-lookup"><span data-stu-id="b8226-160">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="b8226-161">Modul för inköpsruta</span><span class="sxs-lookup"><span data-stu-id="b8226-161">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="b8226-162">Sidor och moduler för kontohantering</span><span class="sxs-lookup"><span data-stu-id="b8226-162">Account management pages and modules</span></span>](account-management.md)

[<span data-ttu-id="b8226-163">Modul för butiksväljare</span><span class="sxs-lookup"><span data-stu-id="b8226-163">Store selector module</span></span>](store-selector.md)

[<span data-ttu-id="b8226-164">Uppdateringar av SDK och modulbibliotek</span><span class="sxs-lookup"><span data-stu-id="b8226-164">SDK and module library updates</span></span>](e-commerce-extensibility/sdk-updates.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
