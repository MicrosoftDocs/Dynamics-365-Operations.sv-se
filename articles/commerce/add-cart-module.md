---
title: Kundvagnsmodul
description: Det här avsnittet handlar om kundvagnsmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 01/23/2020
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
ms.openlocfilehash: f6dd8fb56f7342eb9c877eda503a92f4a31e5863
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025446"
---
# <a name="cart-module"></a><span data-ttu-id="492de-103">Kundvagnsmodul</span><span class="sxs-lookup"><span data-stu-id="492de-103">Cart module</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="492de-104">Det här avsnittet handlar om kundvagnsmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="492de-104">This topic covers cart modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="492de-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="492de-105">Overview</span></span>

<span data-ttu-id="492de-106">En kundvagnsmodul används för att visa artiklarna som har lagts till i kundvagnen innan kunden fortsätter till kassan.</span><span class="sxs-lookup"><span data-stu-id="492de-106">A cart module is used to show the items that have been added to the cart before the customer proceeds to checkout.</span></span> <span data-ttu-id="492de-107">Den innehåller till exempel alla artiklar som har lagts till i kundvagnen och en ordersammanfattning.</span><span class="sxs-lookup"><span data-stu-id="492de-107">For example, it includes all the items that have been added to the cart and an order summary.</span></span> <span data-ttu-id="492de-108">Det gör också att kunden kan använda eller ta bort kampanjkoder.</span><span class="sxs-lookup"><span data-stu-id="492de-108">It also lets the customer apply or remove promotional codes.</span></span>

<span data-ttu-id="492de-109">Kundvagnsmodulen stöder inloggade utcheckning och gästkassa.</span><span class="sxs-lookup"><span data-stu-id="492de-109">The cart module supports signed-in checkout and guest checkout.</span></span> <span data-ttu-id="492de-110">Det stöder också en **Tillbaka till shopping**-länk.</span><span class="sxs-lookup"><span data-stu-id="492de-110">It also supports a **Back to shopping** link.</span></span> <span data-ttu-id="492de-111">Du kan konfigurera flödet för den här länken när **webbplatsinställningar \> tillägg \> flöden**.</span><span class="sxs-lookup"><span data-stu-id="492de-111">You can configure the route for this link at **Site Settings \> Extensions \> Routes**.</span></span>

<span data-ttu-id="492de-112">Kundvagnsmodulen återger data baserat på kundvagn-ID.</span><span class="sxs-lookup"><span data-stu-id="492de-112">The cart module renders data based on the cart ID.</span></span> <span data-ttu-id="492de-113">Kundvagn-ID är en webbläsarcookie som finns tillgänglig på hela webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="492de-113">The cart ID is a browser cookie that is available throughout the site.</span></span>

## <a name="cart-module-properties-and-slots"></a><span data-ttu-id="492de-114">Egenskaper och platser för kundvagnsmodul</span><span class="sxs-lookup"><span data-stu-id="492de-114">Cart module properties and slots</span></span>

<span data-ttu-id="492de-115">Kundvagnsmodulen har en egenskap för **Rubrik** som kan ställas in på värden som **Shoppingväska** och **Artiklarna i vagnen**.</span><span class="sxs-lookup"><span data-stu-id="492de-115">The cart module has a **Heading** property that can be set to values such as **Shopping bag** and **Items in your cart**.</span></span> 

## <a name="modules-that-can-be-used-in-a-cart-module"></a><span data-ttu-id="492de-116">Moduler kan användas i en kundvagnsmodul</span><span class="sxs-lookup"><span data-stu-id="492de-116">Modules that can be used in a cart module</span></span>

- <span data-ttu-id="492de-117">**Textblock** – den här modulen stöder anpassade meddelanden i kundvagnsmodulen.</span><span class="sxs-lookup"><span data-stu-id="492de-117">**Text block** – This module supports custom messaging in the cart module.</span></span> <span data-ttu-id="492de-118">Meddelandena styrs av innehållshanteringssystem (CMS).</span><span class="sxs-lookup"><span data-stu-id="492de-118">The messages are driven by the content management system (CMS).</span></span> <span data-ttu-id="492de-119">Alla meddelanden kan läggas till, till exempel "för problem med ordern, kontakta 1-800-Fabrikam."</span><span class="sxs-lookup"><span data-stu-id="492de-119">Any message can be added, such as "For issues with your order, contact 1-800-Fabrikam."</span></span>
- <span data-ttu-id="492de-120">**Butiksväljare** – i den här modulen visas en lista över närliggande butiker där det finns en artikel tillgänglig för upphämtning.</span><span class="sxs-lookup"><span data-stu-id="492de-120">**Store selector** – This module shows a list of nearby stores where an item is available for pickup.</span></span> <span data-ttu-id="492de-121">Användare kan ange en plats för att hitta butiker som finns i närheten.</span><span class="sxs-lookup"><span data-stu-id="492de-121">It lets users enter a location to find stores that are nearby.</span></span> <span data-ttu-id="492de-122">Butiksväljarmodulen är integrerad med geokodnings-API för Bing Maps för att konvertera platsen till en latitud och longitud.</span><span class="sxs-lookup"><span data-stu-id="492de-122">The store selector module is integrated with the Bing Maps Geocoding application programming interface (API) to convert the location to a latitude and longitude.</span></span> <span data-ttu-id="492de-123">En Bing Maps API-nyckel krävs och måste läggas till på sidan för delade butiksparametrar i Dynamics 365 Retail.</span><span class="sxs-lookup"><span data-stu-id="492de-123">A Bing Maps API key is required and must be added to the Retail shared parameters page in Dynamics 365 Retail.</span></span> <span data-ttu-id="492de-124">Den här modulen har stöd för två egenskaper **Sökradien** och **Länk till användarvillkor**.</span><span class="sxs-lookup"><span data-stu-id="492de-124">This module supports two properties, **Search radius** and **Terms of service link**.</span></span> <span data-ttu-id="492de-125">Egenskapen **Sökradie** definierar sökradien för butiker, i mil.</span><span class="sxs-lookup"><span data-stu-id="492de-125">The **Search radius** property defines the search radius for stores, in miles.</span></span> <span data-ttu-id="492de-126">Om inget värde anges används standardsökradien 50 mil.</span><span class="sxs-lookup"><span data-stu-id="492de-126">If no value is specified, the default search radius, 50 miles, is used.</span></span> <span data-ttu-id="492de-127">Om Bing Maps eller någon extern tjänst används kan egenskapen **Länken för tjänstvillkor** användas för att skapa en länk till villkoren för tjänsten.</span><span class="sxs-lookup"><span data-stu-id="492de-127">If Bings Maps or any external service is used, the **Terms of service link** property can be used to provide a link to the terms of service.</span></span> <span data-ttu-id="492de-128">Det krävs en länk för tjänstvillkors för Bing Maps-tjänsten.</span><span class="sxs-lookup"><span data-stu-id="492de-128">A terms of service link is required for the Bing Maps service.</span></span> 

## <a name="cart-module-settings"></a><span data-ttu-id="492de-129">Inställningar för kundvagnsmodul</span><span class="sxs-lookup"><span data-stu-id="492de-129">Cart module settings</span></span>

<span data-ttu-id="492de-130">Vagnmoduler har följande inställningar som kan konfigureras på **Platsinställningar \> Tillägg**:</span><span class="sxs-lookup"><span data-stu-id="492de-130">Cart modules have the following settings that can be configured at **Site Settings \> Extensions**:</span></span>

- <span data-ttu-id="492de-131">**Maximal kvantitet** – Den här egenskapen används för att ange det maximala antalet för varje objekt som kan läggas till i vagnen.</span><span class="sxs-lookup"><span data-stu-id="492de-131">**Maximum quantity** – This property is used to specify the maximum number of each item that can be added to the cart.</span></span> <span data-ttu-id="492de-132">En återförsäljare kan till exempel besluta att endast 10 av varje produkt kan säljas i en enda transaktion.</span><span class="sxs-lookup"><span data-stu-id="492de-132">For example, a retailer might decide that only 10 of each product can be sold in a single transaction.</span></span>
- <span data-ttu-id="492de-133">**Inventering** – när värdet är inställt på **Sant** läggs en artikel till i vagnen först när modul för inköpsruta kontrollerar att den finns i lager.</span><span class="sxs-lookup"><span data-stu-id="492de-133">**Inventory check** – When the value is set to **True**, an item is added to the cart only after the buy box module makes sure that it's in stock.</span></span> <span data-ttu-id="492de-134">Den här inventeringen görs både för scenarier där artikeln ska levereras och för scenarier där den ska hämtas i butiken.</span><span class="sxs-lookup"><span data-stu-id="492de-134">This inventory check is done both for scenarios where the item will be shipped and for scenarios where it will be picked up in the store.</span></span> <span data-ttu-id="492de-135">Om värdet är inställt på **Falsk** görs ingen lagerkontroll innan en artikel läggs till i vagnen och ordern placeras.</span><span class="sxs-lookup"><span data-stu-id="492de-135">If the value is set to **False**, no inventory check is done before an item is added to the cart and the order is placed.</span></span>
- <span data-ttu-id="492de-136">**Lagerkvantitet** – den här egenskapen används för att ange ett buffertnummer för lager.</span><span class="sxs-lookup"><span data-stu-id="492de-136">**Inventory buffer** – This property is used to specify a buffer number for inventory.</span></span> <span data-ttu-id="492de-137">Lagret underhålls i realtid och när många kunder gör beställningar kan det vara svårt att underhålla en korrekt inventering.</span><span class="sxs-lookup"><span data-stu-id="492de-137">Inventory is maintained in real time, and when many customers place orders, it can be difficult to maintain an accurate inventory count.</span></span> <span data-ttu-id="492de-138">När en lagerkontroll utförs, om lagret är mindre än buffertlagret, behandlas produkten som om den ligger utanför lagret.</span><span class="sxs-lookup"><span data-stu-id="492de-138">When an inventory check is done, if the inventory is less than the buffer amount, the product is treated as out of stock.</span></span> <span data-ttu-id="492de-139">När försäljningen går snabbt via flera kanaler, så att lager inventeringen inte fullständigt synkroniseras, finns det därför mindre risk för försäljning av en artikel som ligger utanför lagret.</span><span class="sxs-lookup"><span data-stu-id="492de-139">Therefore, when sales occur quickly through several channels, and the inventory count isn't fully synced, there is less risk that an item that is out of stock will be sold.</span></span>
- <span data-ttu-id="492de-140">**Tillbaka till shopping** – den här egenskapen används för att ange vägen för länken **Tillbaka till shopping**.</span><span class="sxs-lookup"><span data-stu-id="492de-140">**Back to shopping** – This property is used to specify the route for the **Back to shopping** link.</span></span> <span data-ttu-id="492de-141">Den här vägen kan konfigureras på webbplatsnivå.</span><span class="sxs-lookup"><span data-stu-id="492de-141">This route can be configured at the site level.</span></span> <span data-ttu-id="492de-142">Den här konfigurationen låter återförsäljare kan han eller hon gå tillbaka till startsidan eller någon annan sida på webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="492de-142">This configuration lets retailers take the customer back to the home page or any other page on the site.</span></span>

## <a name="commerce-scale-unit-interaction"></a><span data-ttu-id="492de-143">Interaktion för skalningsenhet för handel</span><span class="sxs-lookup"><span data-stu-id="492de-143">Commerce Scale Unit interaction</span></span>

<span data-ttu-id="492de-144">Vagnmodul för inköpsruta hämtar produktinformation med hjälp av API:er för skalningsenhet för handel.</span><span class="sxs-lookup"><span data-stu-id="492de-144">The cart module retrieves product information by using Commerce Scale Unit APIs.</span></span> <span data-ttu-id="492de-145">Vagn-ID från webbläsarcookien används för att hämta all produktinformation från skalningsenhet för handel.</span><span class="sxs-lookup"><span data-stu-id="492de-145">The cart ID from the browser cookie is used to retrieve all the product information from Commerce Scale Unit.</span></span>

## <a name="add-a-cart-module-to-a-page"></a><span data-ttu-id="492de-146">Lägg till en kundvagnsmodul på en ny sida</span><span class="sxs-lookup"><span data-stu-id="492de-146">Add a cart module to a page</span></span>

<span data-ttu-id="492de-147">Om du vill lägga till en kundvagnsmodul på en ny sida och ställa in de obligatoriska egenskaperna följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="492de-147">To add a cart module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="492de-148">Skapa ett fragment med namnet **vagnfragment**och lägg till en kundvagnsmodul.</span><span class="sxs-lookup"><span data-stu-id="492de-148">Create a fragment that is named **Cart fragment**, and add a cart module to it.</span></span>
1. <span data-ttu-id="492de-149">Lägg till en rubrik i vagnmodulen.</span><span class="sxs-lookup"><span data-stu-id="492de-149">Add a heading to the cart module.</span></span>
1. <span data-ttu-id="492de-150">Lägg till modulen för butiksväljare i vagnmodulen.</span><span class="sxs-lookup"><span data-stu-id="492de-150">Add a store selector module to the cart module.</span></span>
1. <span data-ttu-id="492de-151">Spara fragmentet, slutför redigeringen och publicera det.</span><span class="sxs-lookup"><span data-stu-id="492de-151">Save the fragment, finish editing it, and publish it.</span></span>
1. <span data-ttu-id="492de-152">Skapa en mall med namnet **vagnmall** och lägg till det vagnfragment som du precis skapade i den.</span><span class="sxs-lookup"><span data-stu-id="492de-152">Create a template that is named **Cart template**, and add the cart fragment that you just created to it.</span></span>
1. <span data-ttu-id="492de-153">Spara mallen, slutför redigeringen och publicera den.</span><span class="sxs-lookup"><span data-stu-id="492de-153">Save the template, finish editing it, and publish it.</span></span>
1. <span data-ttu-id="492de-154">Skapa en sida som använder den nya mallen.</span><span class="sxs-lookup"><span data-stu-id="492de-154">Create a page that uses the new template.</span></span>
1. <span data-ttu-id="492de-155">Spara och förhandsgranska sidan.</span><span class="sxs-lookup"><span data-stu-id="492de-155">Save and preview the page.</span></span>
1. <span data-ttu-id="492de-156">Avsluta redigeringen av sidan och publicera den.</span><span class="sxs-lookup"><span data-stu-id="492de-156">Finish editing the page, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="492de-157">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="492de-157">Additional resources</span></span>

[<span data-ttu-id="492de-158">Startpaket – översikt</span><span class="sxs-lookup"><span data-stu-id="492de-158">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="492de-159">Behållaremodul</span><span class="sxs-lookup"><span data-stu-id="492de-159">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="492de-160">Modul för inköpsruta</span><span class="sxs-lookup"><span data-stu-id="492de-160">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="492de-161">Kassamodul</span><span class="sxs-lookup"><span data-stu-id="492de-161">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="492de-162">Modul för orderbekräftelse</span><span class="sxs-lookup"><span data-stu-id="492de-162">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="492de-163">Modul för sidhuvud</span><span class="sxs-lookup"><span data-stu-id="492de-163">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="492de-164">Modul för sidfot</span><span class="sxs-lookup"><span data-stu-id="492de-164">Footer module</span></span>](author-footer-module.md)
