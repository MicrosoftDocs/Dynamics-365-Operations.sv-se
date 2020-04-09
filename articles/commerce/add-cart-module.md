---
title: Kundvagnsmodul
description: Det här avsnittet handlar om kundvagnsmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 03/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 598b35b1bd365e761d8d4c5ef214935e60b971f4
ms.sourcegitcommit: de5af1912201dd70aa85fdcad0b184c42405802e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/21/2020
ms.locfileid: "3154027"
---
# <a name="cart-module"></a><span data-ttu-id="d383d-103">Kundvagnsmodul</span><span class="sxs-lookup"><span data-stu-id="d383d-103">Cart module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="d383d-104">Det här avsnittet handlar om kundvagnsmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="d383d-104">This topic covers cart modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="d383d-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="d383d-105">Overview</span></span>

<span data-ttu-id="d383d-106">En kundvagnsmodul visar artiklarna som har lagts till i kundvagnen innan kunden fortsätter till kassan.</span><span class="sxs-lookup"><span data-stu-id="d383d-106">A cart module shows the items that have been added to the cart before the customer proceeds to checkout.</span></span> <span data-ttu-id="d383d-107">Modulen visar även en också en ordersammanfattning och gör att kunden kan använda eller ta bort kampanjkoder.</span><span class="sxs-lookup"><span data-stu-id="d383d-107">The module also shows an order summary and lets the customer apply or remove promotional codes.</span></span>

<span data-ttu-id="d383d-108">Kundvagnsmodulen stöder inloggade utcheckning och gästkassa.</span><span class="sxs-lookup"><span data-stu-id="d383d-108">The cart module supports signed-in checkout and guest checkout.</span></span> <span data-ttu-id="d383d-109">Det stöder också en **Tillbaka till shopping**-länk.</span><span class="sxs-lookup"><span data-stu-id="d383d-109">It also supports a **Back to shopping** link.</span></span> <span data-ttu-id="d383d-110">Du kan konfigurera flödet för den här länken när **webbplatsinställningar \> tillägg \> flöden**.</span><span class="sxs-lookup"><span data-stu-id="d383d-110">You can configure the route for this link at **Site Settings \> Extensions \> Routes**.</span></span>

<span data-ttu-id="d383d-111">I modulen kundvagn återges data baserat på vagn-ID:t, som är en webbläsarcookie som är tillgänglig på hela webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="d383d-111">The cart module renders data based on the cart ID, which is a browser cookie available throughout the site.</span></span>

## <a name="cart-module-properties-and-slots"></a><span data-ttu-id="d383d-112">Egenskaper och platser för kundvagnsmodul</span><span class="sxs-lookup"><span data-stu-id="d383d-112">Cart module properties and slots</span></span>

<span data-ttu-id="d383d-113">Kundvagnsmodulen har en egenskap för **Rubrik** som kan ställas in på värden som **Shoppingväska** och **Artiklarna i vagnen**.</span><span class="sxs-lookup"><span data-stu-id="d383d-113">The cart module has a **Heading** property that can be set to values such as **Shopping bag** and **Items in your cart**.</span></span> 

## <a name="modules-that-can-be-used-in-a-cart-module"></a><span data-ttu-id="d383d-114">Moduler kan användas i en kundvagnsmodul</span><span class="sxs-lookup"><span data-stu-id="d383d-114">Modules that can be used in a cart module</span></span>

- <span data-ttu-id="d383d-115">**Textblock** – den här modulen stöder anpassade meddelanden i kundvagnsmodulen.</span><span class="sxs-lookup"><span data-stu-id="d383d-115">**Text block** – This module supports custom messaging in the cart module.</span></span> <span data-ttu-id="d383d-116">Meddelandena styrs av innehållshanteringssystem (CMS).</span><span class="sxs-lookup"><span data-stu-id="d383d-116">The messages are driven by the content management system (CMS).</span></span> <span data-ttu-id="d383d-117">Alla meddelanden kan läggas till, till exempel "för problem med ordern, kontakta 1-800-Fabrikam."</span><span class="sxs-lookup"><span data-stu-id="d383d-117">Any message can be added, such as "For issues with your order, contact 1-800-Fabrikam."</span></span>
- <span data-ttu-id="d383d-118">**Butiksväljare** – i den här modulen visas en lista över närliggande butiker där det finns en artikel tillgänglig för upphämtning.</span><span class="sxs-lookup"><span data-stu-id="d383d-118">**Store selector** – This module shows a list of nearby stores where an item is available for pickup.</span></span> <span data-ttu-id="d383d-119">Användare kan ange en plats för att hitta butiker som finns i närheten.</span><span class="sxs-lookup"><span data-stu-id="d383d-119">It lets users enter a location to find stores that are nearby.</span></span> <span data-ttu-id="d383d-120">Mer information om den här modulen finns i [modulen Butiksväljare](store-selector.md).</span><span class="sxs-lookup"><span data-stu-id="d383d-120">For more information on this module, see [Store Selector module](store-selector.md).</span></span>

## <a name="cart-module-settings"></a><span data-ttu-id="d383d-121">Inställningar för kundvagnsmodul</span><span class="sxs-lookup"><span data-stu-id="d383d-121">Cart module settings</span></span>

<span data-ttu-id="d383d-122">Vagnmoduler har följande inställningar som kan konfigureras på **Platsinställningar \> Tillägg**:</span><span class="sxs-lookup"><span data-stu-id="d383d-122">Cart modules have the following settings that can be configured at **Site Settings \> Extensions**:</span></span>

- <span data-ttu-id="d383d-123">**Maximal kvantitet** – Den här egenskapen används för att ange det maximala antalet för varje objekt som kan läggas till i vagnen.</span><span class="sxs-lookup"><span data-stu-id="d383d-123">**Maximum quantity** – This property is used to specify the maximum number of each item that can be added to the cart.</span></span> <span data-ttu-id="d383d-124">En återförsäljare kan till exempel besluta att endast 10 av varje produkt kan säljas i en enda transaktion.</span><span class="sxs-lookup"><span data-stu-id="d383d-124">For example, a retailer might decide that only 10 of each product can be sold in a single transaction.</span></span>
- <span data-ttu-id="d383d-125">**Inventering** – när värdet är inställt på **Sant** läggs en artikel till i vagnen först när modul för inköpsruta kontrollerar att den finns i lager.</span><span class="sxs-lookup"><span data-stu-id="d383d-125">**Inventory check** – When the value is set to **True**, an item is added to the cart only after the buy box module makes sure that it's in stock.</span></span> <span data-ttu-id="d383d-126">Den här inventeringen görs för scenarier där artikeln ska levereras och för scenarier där den ska hämtas i butiken.</span><span class="sxs-lookup"><span data-stu-id="d383d-126">This inventory check is done for scenarios where the item will be shipped and for scenarios where it will be picked up in the store.</span></span> <span data-ttu-id="d383d-127">Om värdet är inställt på **Falsk** görs ingen lagerkontroll innan en artikel läggs till i vagnen och ordern placeras.</span><span class="sxs-lookup"><span data-stu-id="d383d-127">If the value is set to **False**, no inventory check is done before an item is added to the cart and the order is placed.</span></span>
- <span data-ttu-id="d383d-128">**Lagerkvantitet** – den här egenskapen används för att ange ett buffertnummer för lager.</span><span class="sxs-lookup"><span data-stu-id="d383d-128">**Inventory buffer** – This property is used to specify a buffer number for inventory.</span></span> <span data-ttu-id="d383d-129">Lagret underhålls i realtid och när många kunder gör beställningar kan det vara svårt att underhålla en korrekt inventering.</span><span class="sxs-lookup"><span data-stu-id="d383d-129">Inventory is maintained in real time, and when many customers place orders, it can be difficult to maintain an accurate inventory count.</span></span> <span data-ttu-id="d383d-130">När en lagerkontroll utförs, om lagret är mindre än buffertlagret, behandlas produkten som om den ligger utanför lagret.</span><span class="sxs-lookup"><span data-stu-id="d383d-130">When an inventory check is done, if the inventory is less than the buffer amount, the product is treated as out of stock.</span></span> <span data-ttu-id="d383d-131">När försäljningen går snabbt via flera kanaler, så att lager inventeringen inte fullständigt synkroniseras, finns det därför mindre risk för försäljning av en artikel som ligger utanför lagret.</span><span class="sxs-lookup"><span data-stu-id="d383d-131">Therefore, when sales occur quickly through several channels, and the inventory count isn't fully synced, there is less risk that an item that is out of stock will be sold.</span></span>
- <span data-ttu-id="d383d-132">**Tillbaka till shopping** – den här egenskapen används för att ange vägen för länken **Tillbaka till shopping**.</span><span class="sxs-lookup"><span data-stu-id="d383d-132">**Back to shopping** – This property is used to specify the route for the **Back to shopping** link.</span></span> <span data-ttu-id="d383d-133">Vägen kan konfigureras på webbplatsnivå, vilket gör att återförsäljare kan ta kunden tillbaka till startsidan eller någon annan sida på webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="d383d-133">The route can be configured at the site level, allowing retailers to take the customer back to the home page or any other page on the site.</span></span>

## <a name="commerce-scale-unit-interaction"></a><span data-ttu-id="d383d-134">Interaktion för skalningsenhet för handel</span><span class="sxs-lookup"><span data-stu-id="d383d-134">Commerce Scale Unit interaction</span></span>

<span data-ttu-id="d383d-135">Vagnmodul för inköpsruta hämtar produktinformation med hjälp av API:er för skalningsenhet för handel.</span><span class="sxs-lookup"><span data-stu-id="d383d-135">The cart module retrieves product information by using Commerce Scale Unit APIs.</span></span> <span data-ttu-id="d383d-136">Vagn-ID från webbläsarcookien används för att hämta all produktinformation från skalningsenhet för handel.</span><span class="sxs-lookup"><span data-stu-id="d383d-136">The cart ID from the browser cookie is used to retrieve all the product information from Commerce Scale Unit.</span></span>

## <a name="add-a-cart-module-to-a-page"></a><span data-ttu-id="d383d-137">Lägg till en kundvagnsmodul på en ny sida</span><span class="sxs-lookup"><span data-stu-id="d383d-137">Add a cart module to a page</span></span>

<span data-ttu-id="d383d-138">Om du vill lägga till en kundvagnsmodul på en ny sida och ställa in de obligatoriska egenskaperna följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="d383d-138">To add a cart module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="d383d-139">Skapa ett fragment med namnet **vagnfragment**och lägg till en kundvagnsmodul till det nya fragmentet.</span><span class="sxs-lookup"><span data-stu-id="d383d-139">Create a fragment named **Cart fragment**, and add a cart module to the new fragment.</span></span>
1. <span data-ttu-id="d383d-140">Lägg till en rubrik i vagnmodulen.</span><span class="sxs-lookup"><span data-stu-id="d383d-140">Add a heading to the cart module.</span></span>
1. <span data-ttu-id="d383d-141">Lägg till modulen för butiksväljare i vagnmodulen.</span><span class="sxs-lookup"><span data-stu-id="d383d-141">Add a store selector module to the cart module.</span></span>
1. <span data-ttu-id="d383d-142">Spara fragmentet, slutför redigeringen och publicera sedan fragmentet.</span><span class="sxs-lookup"><span data-stu-id="d383d-142">Save the fragment, finish editing, and then publish the fragment.</span></span>
1. <span data-ttu-id="d383d-143">Skapa en mall med namnet **vagnmall** och lägg till det vagnfragment som du precis skapade.</span><span class="sxs-lookup"><span data-stu-id="d383d-143">Create a template named **Cart template**, and add the cart fragment that you just created.</span></span>
1. <span data-ttu-id="d383d-144">Spara mallen, slutför redigeringen och publicera sedan mallen.</span><span class="sxs-lookup"><span data-stu-id="d383d-144">Save the template, finish editing, and then publish the template.</span></span>
1. <span data-ttu-id="d383d-145">Skapa en sida som använder den nya mallen.</span><span class="sxs-lookup"><span data-stu-id="d383d-145">Create a page that uses the new template.</span></span>
1. <span data-ttu-id="d383d-146">Spara och förhandsgranska sidan.</span><span class="sxs-lookup"><span data-stu-id="d383d-146">Save and preview the page.</span></span>
1. <span data-ttu-id="d383d-147">Avsluta redigeringen av sidan och publicera sedan sidan.</span><span class="sxs-lookup"><span data-stu-id="d383d-147">Finish editing the page, and then publish the page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d383d-148">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="d383d-148">Additional resources</span></span>

[<span data-ttu-id="d383d-149">Startpaket – översikt</span><span class="sxs-lookup"><span data-stu-id="d383d-149">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="d383d-150">Behållarmodul</span><span class="sxs-lookup"><span data-stu-id="d383d-150">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="d383d-151">Modul för butiksväljare</span><span class="sxs-lookup"><span data-stu-id="d383d-151">Store selector module</span></span>](store-selector.md)

[<span data-ttu-id="d383d-152">Modul för inköpsruta</span><span class="sxs-lookup"><span data-stu-id="d383d-152">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="d383d-153">Kassamodul</span><span class="sxs-lookup"><span data-stu-id="d383d-153">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="d383d-154">Modul för orderbekräftelse</span><span class="sxs-lookup"><span data-stu-id="d383d-154">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="d383d-155">Modul för sidhuvud</span><span class="sxs-lookup"><span data-stu-id="d383d-155">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="d383d-156">Modul för sidfot</span><span class="sxs-lookup"><span data-stu-id="d383d-156">Footer module</span></span>](author-footer-module.md)
