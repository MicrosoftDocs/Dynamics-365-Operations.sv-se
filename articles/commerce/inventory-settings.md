---
title: Använd lagerinställningar
description: Det här avsnittet behandlar lagerinställningar och beskriver hur du använder dem i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
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
ms.openlocfilehash: d7d25fd62efca52dd2d60ed3435104c3507a1d19
ms.sourcegitcommit: 8028fbc5b9585e87d3331ea02577ff82ede090af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/16/2020
ms.locfileid: "3817619"
---
# <a name="apply-inventory-settings"></a><span data-ttu-id="73996-103">Använd lagerinställningar</span><span class="sxs-lookup"><span data-stu-id="73996-103">Apply inventory settings</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="73996-104">Det här avsnittet behandlar lagerinställningar och beskriver hur du använder dem i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="73996-104">This topic covers inventory settings and describes how to apply them in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="73996-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="73996-105">Overview</span></span>

<span data-ttu-id="73996-106">Lagerinställningarna anger om lagret ska kontrolleras innan produkter läggs till i vagnen.</span><span class="sxs-lookup"><span data-stu-id="73996-106">Inventory settings specify whether inventory should be checked before products are added to the cart.</span></span> <span data-ttu-id="73996-107">De definierar också lagerrelaterade marknadsföringsmeddelanden, t.ex. "i lagret" och "bara några få kvar".</span><span class="sxs-lookup"><span data-stu-id="73996-107">They also define inventory-related merchandising messages, such as "In stock" and "Only a few left."</span></span> <span data-ttu-id="73996-108">Dessa inställningar garanterar att en produkt inte kan köpas om den inte är i lager.</span><span class="sxs-lookup"><span data-stu-id="73996-108">These settings ensure that a product can't be purchased if it's out of stock.</span></span>

<span data-ttu-id="73996-109">Dynamics 365 Commerce tillhandahåller uppskattningar av tillgänglig lagerbehållning för produkter.</span><span class="sxs-lookup"><span data-stu-id="73996-109">Dynamics 365 Commerce provides estimates of on-hand availability for products.</span></span> <span data-ttu-id="73996-110">Information om hur uppskattad behållnings tillgänglighet beräknas finns i [Beräkna lagerdisposition för butikskanaler](calculated-inventory-retail-channels.md).</span><span class="sxs-lookup"><span data-stu-id="73996-110">For information about how estimated on-hand availability is calculated, see [Calculate inventory availability for retail channels](calculated-inventory-retail-channels.md).</span></span>

<span data-ttu-id="73996-111">I Commerce webbplatsskaparen kan lagertrösklar och intervall definieras för en produkt eller en kategori.</span><span class="sxs-lookup"><span data-stu-id="73996-111">In Commerce site builder, inventory thresholds and ranges can be defined for a product or a category.</span></span> <span data-ttu-id="73996-112">De bestämmer om lager kan klassificeras som i lager, låglager eller utanför lagret.</span><span class="sxs-lookup"><span data-stu-id="73996-112">They determine whether inventory can be classified as in stock, low stock, or out of stock.</span></span> <span data-ttu-id="73996-113">Mer information finns i [Konfigurera inventeringsbuffertar and lagernivåer](inventory-buffers-levels.md).</span><span class="sxs-lookup"><span data-stu-id="73996-113">For details, see [Configure inventory buffers and inventory levels](inventory-buffers-levels.md).</span></span>

> [!NOTE]
> <span data-ttu-id="73996-114">Stöd för lagertrösklar och -intervall är tillgängliga i Dynamics 365 Commerce 10.0.12-versionen.</span><span class="sxs-lookup"><span data-stu-id="73996-114">Support for inventory thresholds and ranges is available in the Dynamics 365 Commerce 10.0.12 release.</span></span>

## <a name="inventory-settings"></a><span data-ttu-id="73996-115">Lagerinställningar</span><span class="sxs-lookup"><span data-stu-id="73996-115">Inventory settings</span></span>

<span data-ttu-id="73996-116">I Commerce, lagerinställningar definieras på **Platsinställningar \> Tillägg \> Lagerhantering** i webbplatsskaparen.</span><span class="sxs-lookup"><span data-stu-id="73996-116">In Commerce, inventory settings are defined at **Site Settings \> Extensions \> Inventory Management** in site builder.</span></span> <span data-ttu-id="73996-117">Det finns fyra lagerinställningar, varav en är föråldrad (inaktuell):</span><span class="sxs-lookup"><span data-stu-id="73996-117">There are four inventory settings, one of which is obsolete (deprecated):</span></span>

- <span data-ttu-id="73996-118">**Aktivera lagerkontroll för appen** – den här inställningen aktiverar en produktinventeringskontroll.</span><span class="sxs-lookup"><span data-stu-id="73996-118">**Enable inventory check on app** – This setting turns on a product inventory check.</span></span> <span data-ttu-id="73996-119">När du köper kartongen, kundvagnen och hämtningen i butiksmoduler kontrolleras produktlagret och då kan en produkt bara läggas till i kundvagnen om det finns tillgängligt lager.</span><span class="sxs-lookup"><span data-stu-id="73996-119">Buy box, cart, and pick up in store modules will then check product inventory, and will allow a product to be added to the cart only if inventory is available.</span></span>
- <span data-ttu-id="73996-120">**Lagernivå baserad på** – den här inställningen definierar hur lagernivåer beräknas.</span><span class="sxs-lookup"><span data-stu-id="73996-120">**Inventory level based on** – This setting defines how inventory levels are calculated.</span></span> <span data-ttu-id="73996-121">De tillgängliga värdena är **Total tillgänglig**, **fysiskt tillgänglig** och **tröskel för utanför lagret**.</span><span class="sxs-lookup"><span data-stu-id="73996-121">The available values are **Total Available**, **Physical Available**, and **Out of stock threshold**.</span></span> <span data-ttu-id="73996-122">I Commerce, lagertrösklar och intervall definieras för en varje produkt och kategori.</span><span class="sxs-lookup"><span data-stu-id="73996-122">In Commerce, inventory threshold and ranges can be defined for each product and category.</span></span> <span data-ttu-id="73996-123">Lager-API:erna returnerar produktinformation för båda egenskap **Total tillgänglig** och egenskap **Fysisk tillgänglig**.</span><span class="sxs-lookup"><span data-stu-id="73996-123">The inventory APIs return product inventory information for both the **Total Available** property and the **Physical Available** property.</span></span> <span data-ttu-id="73996-124">Återförsäljaren bestämmer om det **totala tillgängliga** eller **fysiskt tillgängliga** värdet ska användas för att fastställa lagerinventeringen och motsvarande intervall för status som lager och inte artiklar.</span><span class="sxs-lookup"><span data-stu-id="73996-124">The retailer decides whether the **Total Available** or **Physical Available** value should be used to determine the inventory count and the corresponding ranges for in-stock and out-of-stock statuses.</span></span>

    <span data-ttu-id="73996-125">Värdet **tröskel för utanför lagret** för inställning **Lagernivå baserad på** är ett gammalt (äldre) föråldrat värde.</span><span class="sxs-lookup"><span data-stu-id="73996-125">The **Out of stock threshold** value of the **Inventory level based on** setting is an old (legacy), obsolete value.</span></span> <span data-ttu-id="73996-126">När lagerinventeringen väljs bestäms resultatet av det **totala tillgängliga** värdet, men tröskeln definieras av **inställningen för frånvaro av lagertröskel** som beskrivs senare.</span><span class="sxs-lookup"><span data-stu-id="73996-126">When it's selected, the inventory count is determined from the results of the **Total Available** value, but the threshold is defined by the **Out of stock threshold** numeric setting that is described later.</span></span> <span data-ttu-id="73996-127">Den här tröskelinställningen gäller för alla produkter på en näthandelsplats.</span><span class="sxs-lookup"><span data-stu-id="73996-127">This threshold setting applies to all products across an e-Commerce site.</span></span> <span data-ttu-id="73996-128">Om lagret är lägre än tröskelnumret anses en produkt vara utanför lagret.</span><span class="sxs-lookup"><span data-stu-id="73996-128">If inventory is below the threshold number, a product is considered out of stock.</span></span> <span data-ttu-id="73996-129">I annat fall betraktas det som i lager.</span><span class="sxs-lookup"><span data-stu-id="73996-129">Otherwise, it's considered in stock.</span></span> <span data-ttu-id="73996-130">Möjligheterna för **tröskelvärdet för frånvaro** är begränsade och vi rekommenderar inte att du använder det i version 10.0.12 och senare.</span><span class="sxs-lookup"><span data-stu-id="73996-130">The capabilities of the **Out of stock threshold** value are limited, and we don't recommend that you use it in version 10.0.12 and later.</span></span>

- <span data-ttu-id="73996-131">**Lagerområden** – med den här inställningen definieras de lagerintervall som meddelandet visas för i moduler.</span><span class="sxs-lookup"><span data-stu-id="73996-131">**Inventory ranges** – This setting defines the inventory ranges that message are shown for on site modules.</span></span> <span data-ttu-id="73996-132">Den gäller bara om antingen värdet **totala tillgängliga** eller det **fysiska tillgängliga värdet** har valts för inställning **lagernivån baserat på**.</span><span class="sxs-lookup"><span data-stu-id="73996-132">It's applicable only if either the **Total Available** value or the **Physical Available** value is selected for the **Inventory level based on** setting.</span></span> <span data-ttu-id="73996-133">De tillgängliga värdena är **alla**, **låg och ur lagret** och inte **på lagret**.</span><span class="sxs-lookup"><span data-stu-id="73996-133">The available values are **All**, **Low and out of stock**, and **Out of stock**.</span></span>

    - <span data-ttu-id="73996-134">När **alla** är markerat visas meddelanden för alla lagerområden, från lagret ("tillgängligt") i brist på lager ("tillgängligt").</span><span class="sxs-lookup"><span data-stu-id="73996-134">When **All** is selected, messages for all inventory ranges, from in stock ("Available" message) to out of stock ("Out of stock" message), will be shown.</span></span>
    - <span data-ttu-id="73996-135">När **låg och inte i lager** är markerat visas meddelanden för alla lagerområden förutom från lagret ("tillgängligt").</span><span class="sxs-lookup"><span data-stu-id="73996-135">When **Low and out of stock** is selected, messages for all inventory ranges except in stock ("Available" message) will be shown.</span></span>
    - <span data-ttu-id="73996-136">När **inte i lager** är markerat visas endast meddelandet "inte i lager".</span><span class="sxs-lookup"><span data-stu-id="73996-136">When **Out of stock** is selected, only the "Out of stock" message will be shown.</span></span>

- <span data-ttu-id="73996-137">**Tröskel för inte i lager** – den här gamla numeriska inställningen börjar gälla först om värdet **tröskelvärdet för inte i lager** har valts för inställningen **lagernivå baserat på**.</span><span class="sxs-lookup"><span data-stu-id="73996-137">**Out of stock threshold** – This old numeric setting will take effect only if the **Out of stock threshold** value is selected for the **Inventory level based on** setting.</span></span>

> [!IMPORTANT] 
> <span data-ttu-id="73996-138">Dessa inställningar finns i Dynamics 365 Commerce 10.0.12 versionen.</span><span class="sxs-lookup"><span data-stu-id="73996-138">These settings are available in the Dynamics 365 Commerce 10.0.12 release.</span></span> <span data-ttu-id="73996-139">Om du uppdaterar från en äldre version av Dynamics 365 Commerce måste du uppdatera filen appsettings.json manuellt.</span><span class="sxs-lookup"><span data-stu-id="73996-139">If you are updating from an older version of Dynamics 365 Commerce, you must manually update the appsettings.json file.</span></span> <span data-ttu-id="73996-140">Information om hur du uppdaterar filen appsettings.json finns i [SDK- och modulens biblioteksuppdateringar](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).</span><span class="sxs-lookup"><span data-stu-id="73996-140">For instructions on updating the appsettings.json file, see [SDK and module library updates](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).</span></span>

## <a name="modules-that-use-inventory-settings"></a><span data-ttu-id="73996-141">Moduler som använder lagerinställningar</span><span class="sxs-lookup"><span data-stu-id="73996-141">Modules that use inventory settings</span></span>

<span data-ttu-id="73996-142">Ikonmodulerna inköpsruta, önskelista, butiksväljare, kundvagn och kundvagnsikon använder lagerinställningar för att visa lagerområden och meddelanden.</span><span class="sxs-lookup"><span data-stu-id="73996-142">Buy box, wishlist, store selector, cart, and cart icon modules use inventory settings to show the inventory ranges and messages.</span></span>

<span data-ttu-id="73996-143">Följande bild visar ett exempel på en sida med produktinformation (PDP) som visar ett meddelandet "tillgängligt".</span><span class="sxs-lookup"><span data-stu-id="73996-143">The following image shows an example of a product details page (PDP) that is showing an in-stock ("Available") message.</span></span>

![Exempel på en PDP-modul som har ett upplagratmeddelande](./media/pdp-InStock.png)

<span data-ttu-id="73996-145">Följande bild visar ett exempel på en PDP som visar meddelandet "Ej i lager".</span><span class="sxs-lookup"><span data-stu-id="73996-145">The following image shows an example of a PDP that is showing an "Out of stock" message.</span></span>

![Exempel på en PDP-modul som har ett ej i lager-meddelande](./media/pdp-outofstock.png)

<span data-ttu-id="73996-147">Följande bild visar ett exempel på en kundvagn som visar meddelandet i lager (tillgänglig).</span><span class="sxs-lookup"><span data-stu-id="73996-147">The following image shows an example of a cart that is showing an in-stock ("Available") message.</span></span>

![Exempel på en kundvagnmodul som har ett upplagratmeddelande](./media/cart-instock.png)

## <a name="additional-resources"></a><span data-ttu-id="73996-149">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="73996-149">Additional resources</span></span>

[<span data-ttu-id="73996-150">Översikt över modulbibliotek</span><span class="sxs-lookup"><span data-stu-id="73996-150">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="73996-151">Konfigurera lagerkvantiteter och lagernivåer</span><span class="sxs-lookup"><span data-stu-id="73996-151">Configure inventory buffers and inventory levels</span></span>](inventory-buffers-levels.md)

[<span data-ttu-id="73996-152">Kundvagnsmodul</span><span class="sxs-lookup"><span data-stu-id="73996-152">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="73996-153">Modul för inköpsruta</span><span class="sxs-lookup"><span data-stu-id="73996-153">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="73996-154">Sidor och moduler för kontohantering</span><span class="sxs-lookup"><span data-stu-id="73996-154">Account management pages and modules</span></span>](account-management.md)

[<span data-ttu-id="73996-155">Modul för butiksväljare</span><span class="sxs-lookup"><span data-stu-id="73996-155">Store selector module</span></span>](store-selector.md)

[<span data-ttu-id="73996-156">Uppdateringar av SDK och modulbibliotek</span><span class="sxs-lookup"><span data-stu-id="73996-156">SDK and module library updates</span></span>](e-commerce-extensibility/sdk-updates.md)
