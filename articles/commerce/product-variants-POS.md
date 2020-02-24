---
title: Lagersökning i kassan
description: Det här avsnittet beskriver de alternativ som är tillgängliga för visning av lagerinformation i kassan.
author: ashishmsft
manager: AnnBe
ms.date: 03/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2018-03-30
ms.dyn365.ops.version: Application update 5, AX 8.0
ms.openlocfilehash: 1d6133d80d7674a1d896bc19a743a6bd4d0fb40f
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/01/2020
ms.locfileid: "3024111"
---
# <a name="inventory-lookup-in-the-point-of-sale-pos"></a><span data-ttu-id="f70a1-103">Lagersökning i kassan</span><span class="sxs-lookup"><span data-stu-id="f70a1-103">Inventory lookup in the point of sale (POS)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="f70a1-104">Lagersökning i kassan hjälper återförsäljare att effektivisera verksamheten i realtid och få inblick genom att ansluta butiker, kassor och backoffice.</span><span class="sxs-lookup"><span data-stu-id="f70a1-104">Inventory lookup in the point of sale (POS) helps retailers achieve real-time operational excellence and gain insights by connecting stores, the POS, and the back office.</span></span> <span data-ttu-id="f70a1-105">Den här funktionen ger en korrekt produktinformation i realtid genom butiker och distributionscenter.</span><span class="sxs-lookup"><span data-stu-id="f70a1-105">This functionality provides an accurate real-time view of product inventory across stores and distribution centers.</span></span> <span data-ttu-id="f70a1-106">Den underlättar också för återförsäljare att skapa ytterligare effektivitet och kostnadsbesparingar genom att förbättra lagerplanering i realtid.</span><span class="sxs-lookup"><span data-stu-id="f70a1-106">It also helps retailers drive additional efficiencies and cost savings by improving inventory planning in real time.</span></span>

<span data-ttu-id="f70a1-107">En korrekt översikt över lager i realtid i en organisation kan ger snabb, överlägsen kundservice.</span><span class="sxs-lookup"><span data-stu-id="f70a1-107">An accurate real-time view of inventory across an organization helps store associates provide timely, superior customer service.</span></span> <span data-ttu-id="f70a1-108">Den tidpunkt som är viktigast är den tidpunkt när kunden är redo att göra ett inköp.</span><span class="sxs-lookup"><span data-stu-id="f70a1-108">The moment that matters most is the moment when the customer is ready to make a purchase decision.</span></span> <span data-ttu-id="f70a1-109">Det är viktigt att kassörerna i butiken har lagerinformation lättåtkomlig i realtid, så att de korrekt kan lova produktleverans och hämtning.</span><span class="sxs-lookup"><span data-stu-id="f70a1-109">It's important that cashiers in the store have real-time inventory information at their fingertips, so that they can accurately promise product delivery and pickup.</span></span>

<span data-ttu-id="f70a1-110">Du kan öppna sidan **Lagersökning** från arbetsytan **Retail Modern POS** eller arbetsytan **Retail Cloud POS**.</span><span class="sxs-lookup"><span data-stu-id="f70a1-110">You can open the **Inventory lookup** page from the **Retail Modern POS** workspace or the **Retail Cloud POS** workspace.</span></span>

![Lagersökningspanelen i kassans startsida](media/POSHomepage.png)

<span data-ttu-id="f70a1-112">På sidan **Lagersökning** kan du använda det numeriska tangentbordet för att ange ett produktnummer.</span><span class="sxs-lookup"><span data-stu-id="f70a1-112">On the **Inventory lookup** page, you can use the numeric keyboard to enter a product number.</span></span> <span data-ttu-id="f70a1-113">Du kan sedan visa lagerbehållningen för flera butiker och lagerställen.</span><span class="sxs-lookup"><span data-stu-id="f70a1-113">You can then view the on-hand quantity for multiple stores and warehouses.</span></span>

![Standardinställda lagersökningssidan](media/InventoryLookUp.png)

<span data-ttu-id="f70a1-115">Kvantiteterna **Reserverat** och **Beställt** visas också för varje plats.</span><span class="sxs-lookup"><span data-stu-id="f70a1-115">**Reserved** and **Ordered** quantities are also shown for each location.</span></span>

- <span data-ttu-id="f70a1-116">**Reserverat** – denna kvantitet syftar till värdet **Reserverat fysiskt** från backoffice för det angivna produktnumret på platsen.</span><span class="sxs-lookup"><span data-stu-id="f70a1-116">**Reserved** – This quantity refers to the **Physical reserved** value from the back office for the specified product number at the location.</span></span>
- <span data-ttu-id="f70a1-117">**Beställt** – denna kvantitet syftar till värdet **Totalt beställt** från backoffice för det angivna produktnumret på platsen.</span><span class="sxs-lookup"><span data-stu-id="f70a1-117">**Ordered** – This quantity refers to the **Ordered in total** value from the back office for the specified product number at the location.</span></span>

## <a name="locations-that-inventory-availability-information-is-shown-for"></a><span data-ttu-id="f70a1-118">Platser som lagertillgänglighetsinformation visas för</span><span class="sxs-lookup"><span data-stu-id="f70a1-118">Locations that inventory availability information is shown for</span></span>

<span data-ttu-id="f70a1-119">Listan över platser innehåller två typer av enheter:</span><span class="sxs-lookup"><span data-stu-id="f70a1-119">The list of locations includes two types of entities:</span></span>

- <span data-ttu-id="f70a1-120">**Butiker** – Listan visar butiker som konfigureras med hjälp av butikslokaliserargruppen för den aktuella butiken i administration.</span><span class="sxs-lookup"><span data-stu-id="f70a1-120">**Stores** – The list shows stores that are configured by using the store locator group for the current store in the Headquarters.</span></span>
- <span data-ttu-id="f70a1-121">**Distributionscenter** – olika typer av distributionscenter (till exempel lagerställen) kan konfigureras i Handel.</span><span class="sxs-lookup"><span data-stu-id="f70a1-121">**Distribution centers** – Various types of distribution centers (such as warehouses) can be configured in Commerce.</span></span> <span data-ttu-id="f70a1-122">I listan visas dock endast lagertillgänglighetsinformation för distributionscenter av standardtypen **Standard**.</span><span class="sxs-lookup"><span data-stu-id="f70a1-122">However, the list shows inventory availability information only for distribution centers of the **Standard** default type.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f70a1-123">Lagertillgänglighetsinformation visas inte för lagerställe av typerna **transport**, **karantän** och **varor på väg** för kassan.</span><span class="sxs-lookup"><span data-stu-id="f70a1-123">Inventory availability information isn't shown for warehouses of the **Transit**, **Quarantine**, and **Goods in Route** types for the POS.</span></span>

<span data-ttu-id="f70a1-124">På sidan **Lagersökning** kan du visa  disponibelt att lova-kvantiteter (ATP) för varje butik, utöver de aktuella lagerbehållningskvantiteterna, reserverade kvantiteter och beställda kvantiteter.</span><span class="sxs-lookup"><span data-stu-id="f70a1-124">On the **Inventory lookup** page, you can view available to promise (ATP) quantities for each store, in addition to the current on-hand quantities, reserved quantities, and ordered quantities.</span></span> <span data-ttu-id="f70a1-125">Välj butiken som du vill visa ATP-information för och välj sedan **Visa tillgänglighet för butik**.</span><span class="sxs-lookup"><span data-stu-id="f70a1-125">Select the store to view the ATP information for, and then select **Show store availability**.</span></span>

![ATP-mängder](media/ATP.png)

## <a name="opening-the-dimension-based-matrix-view-to-show-all-variants"></a><span data-ttu-id="f70a1-127">Öppna vyn Dimensionsbaserad matris för att visa alla varianter</span><span class="sxs-lookup"><span data-stu-id="f70a1-127">Opening the Dimension based matrix view to show all variants</span></span>

<span data-ttu-id="f70a1-128">På sidan **produktinformation** för en produktmall eller på sidan **Lagersökning** anger du **visa alla varianter** från appfältet längst ned på sidan.</span><span class="sxs-lookup"><span data-stu-id="f70a1-128">On the **Product details** page of a product master, or on the **Inventory lookup** page, select **View all variants** from the app-bar at bottom of the page.</span></span> <span data-ttu-id="f70a1-129">Vyn **Dimensionsbaserad matris** för första resultatet från dessa sidor visar lagertillgänglighetsinformation för alla varianter av en produkt för den aktuella butiken.</span><span class="sxs-lookup"><span data-stu-id="f70a1-129">The **Dimension based matrix** view for the initial launch from these pages shows the inventory availability information for all variants of a product for the current store.</span></span>

> [!NOTE]
> <span data-ttu-id="f70a1-130">Knappen **visa alla varianter** är bara tillgängligt för artikelproduktmallar som har produktvarianter.</span><span class="sxs-lookup"><span data-stu-id="f70a1-130">The **View all variants** button is available only for item product masters that have product variants.</span></span> <span data-ttu-id="f70a1-131">De är inte tillgängliga för fristående produkter eller paket.</span><span class="sxs-lookup"><span data-stu-id="f70a1-131">It isn't available for standalone products or kits.</span></span>

![Visa knappen för alla varianter på lagersöksidan](media/StandardToMatrix.png)

<span data-ttu-id="f70a1-133">Välj **Visa alla varianter** på sidan **Produktinformation** för en produktmall eller sidan **Lagersökning** utan att välja en plats för att gå till vyn **Dimensionsbaserad matris** för att visa lagertillgänglighetsinformationen för alla varianter av en produkt för den aktuella butiken.</span><span class="sxs-lookup"><span data-stu-id="f70a1-133">Select **View all variants** on the **Product details** page of a product master, or on the **Inventory lookup** page, without selecting a location, to go to the **Dimension based matrix** view to view the inventory availability information for all variants of a product for the current store.</span></span>

![Vyn Dimensionsbaserad matris för lagersöksidan](media/Matrix.png)

> [!NOTE]
> <span data-ttu-id="f70a1-135">I den föregående bilden är visningsordningen för dimensionerna alfabetiskt, eftersom visningsordningen för dimensioner inte konfigurerats för den valda produkten.</span><span class="sxs-lookup"><span data-stu-id="f70a1-135">In the preceding illustration, the display order of the dimensions is alphabetic, because the display order of dimensions wasn't configured for the selected product.</span></span>

<span data-ttu-id="f70a1-136">I vyn **Dimensionsbaserad matris** inkluderar cellerna för produktvarianter ett lagerbehållningsvärde i det nedre högra hörnet.</span><span class="sxs-lookup"><span data-stu-id="f70a1-136">In the **Dimension based matrix** view, the cells for the product variants include an on-hand value in the lower-right corner.</span></span> <span data-ttu-id="f70a1-137">Följande tabell förklarar innebörden av olika värden.</span><span class="sxs-lookup"><span data-stu-id="f70a1-137">The following table explains the meaning of the various values.</span></span>

| <span data-ttu-id="f70a1-138">Behållningsvärde</span><span class="sxs-lookup"><span data-stu-id="f70a1-138">On-hand value</span></span>                            | <span data-ttu-id="f70a1-139">beskrivning</span><span class="sxs-lookup"><span data-stu-id="f70a1-139">Description</span></span> |
|------------------------------------------|-------------|
| <span data-ttu-id="f70a1-140">Numeriskt värde som är större än 0 (noll)</span><span class="sxs-lookup"><span data-stu-id="f70a1-140">Numeric value that is more than 0 (zero)</span></span> | <span data-ttu-id="f70a1-141">En variant har frisläppts till den angivna platsen och du kan utföra ytterligare åtgärder i cellen.</span><span class="sxs-lookup"><span data-stu-id="f70a1-141">A variant has been released to the selected location, and you can perform additional actions in the cell.</span></span> <span data-ttu-id="f70a1-142">(Dessa åtgärder kommer att beskrivas mer utförligt i detta ämne.)</span><span class="sxs-lookup"><span data-stu-id="f70a1-142">(These actions are described in more detail later in this topic.)</span></span> |
| <span data-ttu-id="f70a1-143">**0** (noll)</span><span class="sxs-lookup"><span data-stu-id="f70a1-143">**0** (zero)</span></span>                             | <span data-ttu-id="f70a1-144">En variant har frisläppts till den valda platsen, men artikeln är inte tillgänglig på den valda platsen.</span><span class="sxs-lookup"><span data-stu-id="f70a1-144">A variant has been released to the selected location, but the item isn't available in selected location.</span></span> <span data-ttu-id="f70a1-145">Du kan emellertid utföra ytterligare åtgärder i cellen.</span><span class="sxs-lookup"><span data-stu-id="f70a1-145">However, you can perform additional actions in the cell.</span></span> <span data-ttu-id="f70a1-146">(Dessa åtgärder kommer att beskrivas mer utförligt i detta ämne.)</span><span class="sxs-lookup"><span data-stu-id="f70a1-146">(These actions are described in more detail later in this topic.)</span></span> |
| <span data-ttu-id="f70a1-147">**Ej tillämpligt** eller en inaktiv cell</span><span class="sxs-lookup"><span data-stu-id="f70a1-147">**n/a** or an inactive cell</span></span>              | <span data-ttu-id="f70a1-148">En variant har inte frisläppts till den angivna platsen och du kan inte utföra ytterligare åtgärder i cellen.</span><span class="sxs-lookup"><span data-stu-id="f70a1-148">A variant hasn't been released to the selected location, and you can't perform additional actions in the cell.</span></span> |

<span data-ttu-id="f70a1-149">Du kan också ändra pivot för dimensioner genom att välja att använda den nya dimensionen.</span><span class="sxs-lookup"><span data-stu-id="f70a1-149">You can also change the pivot for dimensions by selecting the new dimension to use.</span></span>

![Ändra pivot](media/ChangePivot.png)

![Pivot ändrad](media/PivotChanged.png)

> [!NOTE]
> <span data-ttu-id="f70a1-152">I föregående illustrationer är visningsordningen för dimensionerna för den valda produkten anpassade (icke-alfabetiska).</span><span class="sxs-lookup"><span data-stu-id="f70a1-152">In the preceding illustrations, the display order of the dimensions for the selected product is custom (non-alphabetic).</span></span> <span data-ttu-id="f70a1-153">Den är baserad på visningsordningen för dimensioner som har angetts i backoffice.</span><span class="sxs-lookup"><span data-stu-id="f70a1-153">It's based on the dimension display order that is set in the back office.</span></span>

<span data-ttu-id="f70a1-154">Dessutom i vyn **Dimensionsbaserad matris** kan fler åtgärder utföras för att öka en butiksmedarbetares produktivitet.</span><span class="sxs-lookup"><span data-stu-id="f70a1-154">Additionally, in the **Dimension based matrix** view, more actions can be performed to help boost a store associate's productivity.</span></span> <span data-ttu-id="f70a1-155">Nedan följer några exempel:</span><span class="sxs-lookup"><span data-stu-id="f70a1-155">Here are some examples:</span></span>

- <span data-ttu-id="f70a1-156">Ändra lagringsplats för att slå upp lagerdispositionen för alla produktvarianter på andra platser.</span><span class="sxs-lookup"><span data-stu-id="f70a1-156">Change the store location to look up the inventory availability of all product variants at other locations.</span></span> <span data-ttu-id="f70a1-157">De här platserna inkluderar andra butiker i butikslokaliserargruppen och distributionscenter av standardtypen **Standard**.</span><span class="sxs-lookup"><span data-stu-id="f70a1-157">These locations include other stores in the store locator group and distribution centers of the **Standard** default type.</span></span>
- <span data-ttu-id="f70a1-158">Sälja ett enskild produktvariant till en kund med hjälp av cash and carry, hämtning i butik eller leverans till en adress.</span><span class="sxs-lookup"><span data-stu-id="f70a1-158">Sell an individual product variant to a customer by using cash and carry, in-store pickup, or shipment to an address.</span></span>
- <span data-ttu-id="f70a1-159">Tillhandahålla kunden ATP-information för en enskild produktvariant på en viss plats.</span><span class="sxs-lookup"><span data-stu-id="f70a1-159">Provide the customer with ATP information for an individual product variant at a specific location.</span></span>

![Ytterligare åtgärder för variantpaneler](media/VariantActions.png)

> [!NOTE]
> <span data-ttu-id="f70a1-161">I den föregående bilden är visningsordningen för dimensionerna alfabetiskt, eftersom visningsordningen för dimensioner inte konfigurerats för den valda produkten.</span><span class="sxs-lookup"><span data-stu-id="f70a1-161">In the preceding illustration, the display order of the dimensions is alphabetic, because the display order of dimensions wasn't configured for the selected product.</span></span>

<span data-ttu-id="f70a1-162">Följande tabell visar mer information om ytterligare åtgärder som är tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="f70a1-162">The following table provides more information about the additional actions that are available.</span></span>

| <span data-ttu-id="f70a1-163">Åtgärd</span><span class="sxs-lookup"><span data-stu-id="f70a1-163">Action</span></span>               | <span data-ttu-id="f70a1-164">beskrivning</span><span class="sxs-lookup"><span data-stu-id="f70a1-164">Description</span></span> |
|----------------------|-------------|
| <span data-ttu-id="f70a1-165">Sälj nu</span><span class="sxs-lookup"><span data-stu-id="f70a1-165">Sell now</span></span>             | <span data-ttu-id="f70a1-166">Lägg till vald artikelvariant till transaktionen och omdirigera användaren till skärmbilden för transaktionen.</span><span class="sxs-lookup"><span data-stu-id="f70a1-166">Add the selected item variant to the transaction, and redirect the user to the transaction screen.</span></span> <span data-ttu-id="f70a1-167">(Den här åtgärden är inte tillgänglig när den markerade platsen är ett distributionscenter.)</span><span class="sxs-lookup"><span data-stu-id="f70a1-167">(This action isn't available when the selected location is a distribution center.)</span></span> |
| <span data-ttu-id="f70a1-168">Hämta i butik</span><span class="sxs-lookup"><span data-stu-id="f70a1-168">Pick up in store</span></span>     | <span data-ttu-id="f70a1-169">Skapa kundorder för produktvarianten som ska hämtas från den valda platsen och dirigera om användaren till skärmbilden för transaktionen.</span><span class="sxs-lookup"><span data-stu-id="f70a1-169">Create a customer order for the product variant that will be picked up from the selected location, and redirect the user to the transaction screen.</span></span> <span data-ttu-id="f70a1-170">(Den här åtgärden är inte tillgänglig när den markerade platsen är ett distributionscenter.)</span><span class="sxs-lookup"><span data-stu-id="f70a1-170">(This action isn't available when the selected location is a distribution center.)</span></span> |
| <span data-ttu-id="f70a1-171">Leverera produkt</span><span class="sxs-lookup"><span data-stu-id="f70a1-171">Ship product</span></span>         | <span data-ttu-id="f70a1-172">Skapa kundorder för produktvarianten som ska levereras från den valda platsen och dirigera om användaren till skärmbilden för transaktionen.</span><span class="sxs-lookup"><span data-stu-id="f70a1-172">Create a customer order for the product variant that will be shipped from the selected location, and redirect the user to the transaction screen.</span></span> |
| <span data-ttu-id="f70a1-173">Tillgänglighet</span><span class="sxs-lookup"><span data-stu-id="f70a1-173">Availability</span></span>         | <span data-ttu-id="f70a1-174">Visa ATP-information om den valda variantkombinationen för den valda platsen.</span><span class="sxs-lookup"><span data-stu-id="f70a1-174">Show the ATP information for the selected variant combination for the selected location.</span></span> |
| <span data-ttu-id="f70a1-175">Visa alla platser</span><span class="sxs-lookup"><span data-stu-id="f70a1-175">Show all locations</span></span>   | <span data-ttu-id="f70a1-176">Växla till standardinställda lagersökningsvyn och markera lagertillgänglighetsinformation för artikelvarianten i alla butiker i butikslokaliserargruppen samt i distributionscenter av typen **Standard/standard**.</span><span class="sxs-lookup"><span data-stu-id="f70a1-176">Switch to the standard inventory lookup view, and highlight inventory availability information for the item variant across all stores in the store locator group, and also in distribution centers of the **Standard/Default** type.</span></span> |
| <span data-ttu-id="f70a1-177">Visa produktinformation</span><span class="sxs-lookup"><span data-stu-id="f70a1-177">View product details</span></span> | <span data-ttu-id="f70a1-178">Omdirigera användaren till sidan **produktinformation** med den associerade produktmallen.</span><span class="sxs-lookup"><span data-stu-id="f70a1-178">Redirect the user to the **Product details** page of the associated product master.</span></span> |
