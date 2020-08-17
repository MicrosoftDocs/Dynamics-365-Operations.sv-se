---
title: Använd lagerinställningar
description: Det här avsnittet behandlar lagerinställningar och beskriver hur du använder dem i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 06/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 737e71dc73750bf151629fd904081924ac15b91e
ms.sourcegitcommit: 4a981ee4be6d7e6c0e55541535d386bce2565cba
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/27/2020
ms.locfileid: "3621231"
---
# <a name="apply-inventory-settings"></a><span data-ttu-id="8f484-103">Använd lagerinställningar</span><span class="sxs-lookup"><span data-stu-id="8f484-103">Apply inventory settings</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="8f484-104">Det här avsnittet behandlar lagerinställningar och beskriver hur du använder dem i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="8f484-104">This topic covers inventory settings and describes how to apply them in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="8f484-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="8f484-105">Overview</span></span>

<span data-ttu-id="8f484-106">Lagerinställningarna anger om lagret ska kontrolleras innan produkter läggs till i vagnen.</span><span class="sxs-lookup"><span data-stu-id="8f484-106">Inventory settings specify whether inventory should be checked before products are added to the cart.</span></span> <span data-ttu-id="8f484-107">De definierar också lagerrelaterade marknadsföringsmeddelanden, t.ex. "i lagret" och "bara några få kvar".</span><span class="sxs-lookup"><span data-stu-id="8f484-107">They also define inventory-related merchandising messages, such as "In stock" and "Only a few left."</span></span> <span data-ttu-id="8f484-108">Dessa inställningar garanterar att en produkt inte kan köpas om den inte är i lager.</span><span class="sxs-lookup"><span data-stu-id="8f484-108">These settings ensure that a product can't be purchased if it's out of stock.</span></span>

<span data-ttu-id="8f484-109">Dynamics 365 Commerce tillhandahåller uppskattningar av tillgänglig lagerbehållning för produkter.</span><span class="sxs-lookup"><span data-stu-id="8f484-109">Dynamics 365 Commerce provides estimates of on-hand availability for products.</span></span> <span data-ttu-id="8f484-110">Information om hur uppskattad behållnings tillgänglighet beräknas finns i [Beräkna lagerdisposition för butikskanaler](calculated-inventory-retail-channels.md).</span><span class="sxs-lookup"><span data-stu-id="8f484-110">For information about how estimated on-hand availability is calculated, see [Calculate inventory availability for retail channels](calculated-inventory-retail-channels.md).</span></span>

<span data-ttu-id="8f484-111">I Commerce webbplatsskaparen kan lagertrösklar och intervall definieras för en produkt eller en kategori.</span><span class="sxs-lookup"><span data-stu-id="8f484-111">In Commerce site builder, inventory thresholds and ranges can be defined for a product or a category.</span></span> <span data-ttu-id="8f484-112">De bestämmer om lager kan klassificeras som i lager, låglager eller utanför lagret.</span><span class="sxs-lookup"><span data-stu-id="8f484-112">They determine whether inventory can be classified as in stock, low stock, or out of stock.</span></span> <span data-ttu-id="8f484-113">Mer information finns i [Konfigurera inventeringsbuffertar and lagernivåer](inventory-buffers-levels.md).</span><span class="sxs-lookup"><span data-stu-id="8f484-113">For details, see [Configure inventory buffers and inventory levels](inventory-buffers-levels.md).</span></span>

## <a name="inventory-settings"></a><span data-ttu-id="8f484-114">Lagerinställningar</span><span class="sxs-lookup"><span data-stu-id="8f484-114">Inventory settings</span></span>

<span data-ttu-id="8f484-115">I Commerce, lagerinställningar definieras på **Platsinställningar \> Tillägg \> Lagerhantering** i webbplatsskaparen.</span><span class="sxs-lookup"><span data-stu-id="8f484-115">In Commerce, inventory settings are defined at **Site Settings \> Extensions \> Inventory Management** in site builder.</span></span> <span data-ttu-id="8f484-116">Det finns fyra lagerinställningar, varav en är föråldrad (inaktuell):</span><span class="sxs-lookup"><span data-stu-id="8f484-116">There are four inventory settings, one of which is obsolete (deprecated):</span></span>

- <span data-ttu-id="8f484-117">**Aktivera lagerkontroll för appen** – den här inställningen aktiverar en produktinventeringskontroll.</span><span class="sxs-lookup"><span data-stu-id="8f484-117">**Enable inventory check on app** – This setting turns on a product inventory check.</span></span> <span data-ttu-id="8f484-118">När du köper kartongen, kundvagnen och hämtningen i butiksmoduler kontrolleras produktlagret och då kan en produkt bara läggas till i kundvagnen om det finns tillgängligt lager.</span><span class="sxs-lookup"><span data-stu-id="8f484-118">Buy box, cart, and pick up in store modules will then check product inventory, and will allow a product to be added to the cart only if inventory is available.</span></span>
- <span data-ttu-id="8f484-119">**Lagernivå baserad på** – den här inställningen definierar hur lagernivåer beräknas.</span><span class="sxs-lookup"><span data-stu-id="8f484-119">**Inventory level based on** – This setting defines how inventory levels are calculated.</span></span> <span data-ttu-id="8f484-120">De tillgängliga värdena är **Total tillgänglig**, **fysiskt tillgänglig** och **tröskel för utanför lagret**.</span><span class="sxs-lookup"><span data-stu-id="8f484-120">The available values are **Total Available**, **Physical Available**, and **Out of stock threshold**.</span></span> <span data-ttu-id="8f484-121">I Commerce, lagertrösklar och intervall definieras för en varje produkt och kategori.</span><span class="sxs-lookup"><span data-stu-id="8f484-121">In Commerce, inventory threshold and ranges can be defined for each product and category.</span></span> <span data-ttu-id="8f484-122">Lager-API:erna returnerar produktinformation för båda egenskap **Total tillgänglig** och egenskap **Fysisk tillgänglig**.</span><span class="sxs-lookup"><span data-stu-id="8f484-122">The inventory APIs return product inventory information for both the **Total Available** property and the **Physical Available** property.</span></span> <span data-ttu-id="8f484-123">Återförsäljaren bestämmer om det **totala tillgängliga** eller **fysiskt tillgängliga** värdet ska användas för att fastställa lagerinventeringen och motsvarande intervall för status som lager och inte artiklar.</span><span class="sxs-lookup"><span data-stu-id="8f484-123">The retailer decides whether the **Total Available** or **Physical Available** value should be used to determine the inventory count and the corresponding ranges for in-stock and out-of-stock statuses.</span></span>

    <span data-ttu-id="8f484-124">Värdet **tröskel för utanför lagret** för inställning **Lagernivå baserad på** är ett gammalt (äldre) föråldrat värde.</span><span class="sxs-lookup"><span data-stu-id="8f484-124">The **Out of stock threshold** value of the **Inventory level based on** setting is an old (legacy), obsolete value.</span></span> <span data-ttu-id="8f484-125">När lagerinventeringen väljs bestäms resultatet av det **totala tillgängliga** värdet, men tröskeln definieras av **inställningen för frånvaro av lagertröskel** som beskrivs senare.</span><span class="sxs-lookup"><span data-stu-id="8f484-125">When it's selected, the inventory count is determined from the results of the **Total Available** value, but the threshold is defined by the **Out of stock threshold** numeric setting that is described later.</span></span> <span data-ttu-id="8f484-126">Den här tröskelinställningen gäller för alla produkter på en näthandelsplats.</span><span class="sxs-lookup"><span data-stu-id="8f484-126">This threshold setting applies to all products across an e-Commerce site.</span></span> <span data-ttu-id="8f484-127">Om lagret är lägre än tröskelnumret anses en produkt vara utanför lagret.</span><span class="sxs-lookup"><span data-stu-id="8f484-127">If inventory is below the threshold number, a product is considered out of stock.</span></span> <span data-ttu-id="8f484-128">I annat fall betraktas det som i lager.</span><span class="sxs-lookup"><span data-stu-id="8f484-128">Otherwise, it's considered in stock.</span></span> <span data-ttu-id="8f484-129">Möjligheterna för **tröskelvärdet för frånvaro** är begränsade och vi rekommenderar inte att du använder det i version 10.0.12 och senare.</span><span class="sxs-lookup"><span data-stu-id="8f484-129">The capabilities of the **Out of stock threshold** value are limited, and we don't recommend that you use it in version 10.0.12 and later.</span></span>

- <span data-ttu-id="8f484-130">**Lagerområden** – med den här inställningen definieras de lagerintervall som meddelandet visas för i moduler.</span><span class="sxs-lookup"><span data-stu-id="8f484-130">**Inventory ranges** – This setting defines the inventory ranges that message are shown for on site modules.</span></span> <span data-ttu-id="8f484-131">Den gäller bara om antingen värdet **totala tillgängliga** eller det **fysiska tillgängliga värdet** har valts för inställning **lagernivån baserat på**.</span><span class="sxs-lookup"><span data-stu-id="8f484-131">It's applicable only if either the **Total Available** value or the **Physical Available** value is selected for the **Inventory level based on** setting.</span></span> <span data-ttu-id="8f484-132">De tillgängliga värdena är **alla**, **låg och ur lagret** och inte **på lagret**.</span><span class="sxs-lookup"><span data-stu-id="8f484-132">The available values are **All**, **Low and out of stock**, and **Out of stock**.</span></span>

    - <span data-ttu-id="8f484-133">När **alla** är markerat visas meddelanden för alla lagerområden, från lagret ("tillgängligt") i brist på lager ("tillgängligt").</span><span class="sxs-lookup"><span data-stu-id="8f484-133">When **All** is selected, messages for all inventory ranges, from in stock ("Available" message) to out of stock ("Out of stock" message), will be shown.</span></span>
    - <span data-ttu-id="8f484-134">När **låg och inte i lager** är markerat visas meddelanden för alla lagerområden förutom från lagret ("tillgängligt").</span><span class="sxs-lookup"><span data-stu-id="8f484-134">When **Low and out of stock** is selected, messages for all inventory ranges except in stock ("Available" message) will be shown.</span></span>
    - <span data-ttu-id="8f484-135">När **inte i lager** är markerat visas endast meddelandet "inte i lager".</span><span class="sxs-lookup"><span data-stu-id="8f484-135">When **Out of stock** is selected, only the "Out of stock" message will be shown.</span></span>

- <span data-ttu-id="8f484-136">**Tröskel för inte i lager** – den här gamla numeriska inställningen börjar gälla först om värdet **tröskelvärdet för inte i lager** har valts för inställningen **lagernivå baserat på**.</span><span class="sxs-lookup"><span data-stu-id="8f484-136">**Out of stock threshold** – This old numeric setting will take effect only if the **Out of stock threshold** value is selected for the **Inventory level based on** setting.</span></span>

## <a name="modules-that-use-inventory-settings"></a><span data-ttu-id="8f484-137">Moduler som använder lagerinställningar</span><span class="sxs-lookup"><span data-stu-id="8f484-137">Modules that use inventory settings</span></span>

<span data-ttu-id="8f484-138">Ikonmodulerna inköpsruta, önskelista, butiksväljare, kundvagn och kundvagnsikon använder lagerinställningar för att visa lagerområden och meddelanden.</span><span class="sxs-lookup"><span data-stu-id="8f484-138">Buy box, wishlist, store selector, cart, and cart icon modules use inventory settings to show the inventory ranges and messages.</span></span>

<span data-ttu-id="8f484-139">Följande bild visar ett exempel på en sida med produktinformation (PDP) som visar ett meddelandet "tillgängligt".</span><span class="sxs-lookup"><span data-stu-id="8f484-139">The following image shows an example of a product details page (PDP) that is showing an in-stock ("Available") message.</span></span>

![Exempel på en PDP-modul som har ett upplagratmeddelande](./media/pdp-InStock.png)

<span data-ttu-id="8f484-141">Följande bild visar ett exempel på en PDP som visar meddelandet "Ej i lager".</span><span class="sxs-lookup"><span data-stu-id="8f484-141">The following image shows an example of a PDP that is showing an "Out of stock" message.</span></span>

![Exempel på en PDP-modul som har ett ej i lager-meddelande](./media/pdp-outofstock.png)

<span data-ttu-id="8f484-143">Följande bild visar ett exempel på en kundvagn som visar meddelandet i lager (tillgänglig).</span><span class="sxs-lookup"><span data-stu-id="8f484-143">The following image shows an example of a cart that is showing an in-stock ("Available") message.</span></span>

![Exempel på en kundvagnmodul som har ett upplagratmeddelande](./media/cart-instock.png)

## <a name="additional-resources"></a><span data-ttu-id="8f484-145">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="8f484-145">Additional resources</span></span>

[<span data-ttu-id="8f484-146">Startpaket – översikt</span><span class="sxs-lookup"><span data-stu-id="8f484-146">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="8f484-147">Konfigurera inventeringsbuffertar and lagernivåer</span><span class="sxs-lookup"><span data-stu-id="8f484-147">Configure inventory buffers and inventory levels</span></span>](inventory-buffers-levels.md)

[<span data-ttu-id="8f484-148">Kundvagnsmodul</span><span class="sxs-lookup"><span data-stu-id="8f484-148">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="8f484-149">Modul för inköpsruta</span><span class="sxs-lookup"><span data-stu-id="8f484-149">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="8f484-150">Sidor och moduler för kontohantering</span><span class="sxs-lookup"><span data-stu-id="8f484-150">Account management pages and modules</span></span>](account-management.md)

[<span data-ttu-id="8f484-151">Modul för butiksväljare</span><span class="sxs-lookup"><span data-stu-id="8f484-151">Store selector module</span></span>](store-selector.md)
