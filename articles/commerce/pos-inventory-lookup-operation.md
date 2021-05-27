---
title: Lagersökning i kassan
description: I det här avsnittet beskrivs hur du använder lagersökningsfunktionen i kassan i Dynamics 365 Commerce för att visa lagerbehållning av produkter i butiker och lager.
author: boycezhu
ms.date: 05/11/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2018-03-30
ms.dyn365.ops.version: Application update 5, AX 8.0
ms.openlocfilehash: 873c6413c14d2ee8315c149ee9c495bb59dbd930
ms.sourcegitcommit: 11ca5863175150b6c39f47a9322caa2186727a26
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "6025458"
---
# <a name="inventory-lookup-operation-in-pos"></a><span data-ttu-id="9bfe9-103">Lagersökning i kassan</span><span class="sxs-lookup"><span data-stu-id="9bfe9-103">Inventory lookup operation in POS</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="9bfe9-104">I det här avsnittet beskrivs hur du använder lagersökningsfunktionen i kassan i Dynamics 365 Commerce för att visa lagerbehållning av produkter i butiker och lager.</span><span class="sxs-lookup"><span data-stu-id="9bfe9-104">This topic describes how to use the inventory lookup operation in Dynamics 365 Commerce point of sale (POS) to view the on-hand inventory availability of products across stores and warehouses.</span></span>

<span data-ttu-id="9bfe9-105">En korrekt översikt över lager i en organisation kan ge snabb, effektiv kundservice.</span><span class="sxs-lookup"><span data-stu-id="9bfe9-105">An accurate view of inventory across an organization helps store associates provide timely, effective customer service.</span></span> <span data-ttu-id="9bfe9-106">Den tidpunkt som är viktigast är den tidpunkt när kunden är redo att göra ett inköp.</span><span class="sxs-lookup"><span data-stu-id="9bfe9-106">The moment that matters most is the moment when a customer is ready to make a purchase decision.</span></span> <span data-ttu-id="9bfe9-107">Det är viktigt att kassörerna i butiken har lagerinformation lättåtkomlig i realtid i nästan realtid, så att de korrekt kan lova produktleverans och hämtning.</span><span class="sxs-lookup"><span data-stu-id="9bfe9-107">It's important that cashiers in a retail store have real-time or near real-time inventory information at their fingertips, so that they can accurately promise product delivery and pickup.</span></span>

<span data-ttu-id="9bfe9-108">Lagersökningsfunktionen i Commerce POS hjälper detaljhandlare att uppnå driftsäkerhet och få insikter genom att koppla butiker till Commerce Headquarters.</span><span class="sxs-lookup"><span data-stu-id="9bfe9-108">The inventory lookup operation in Commerce POS helps retailers achieve operational excellence and gain insights by connecting stores with Commerce headquarters.</span></span> <span data-ttu-id="9bfe9-109">Den här funktionen ger en lagertillgänglighetsvy av produkter mellan butiker och lagerställen.</span><span class="sxs-lookup"><span data-stu-id="9bfe9-109">This functionality provides an inventory availability view of products across stores and warehouses.</span></span> <span data-ttu-id="9bfe9-110">Den underlättar också för återförsäljare att skapa ytterligare effektivitet och kostnadsbesparingar genom att förbättra lagerplanering i realtid.</span><span class="sxs-lookup"><span data-stu-id="9bfe9-110">It also helps retailers drive additional efficiencies and cost savings by improving inventory planning in real time.</span></span>

<span data-ttu-id="9bfe9-111">När lagersökningen startas från POS-programmet använder POS-kassören det numeriska tangentbordet för att ange ett produktnummer för att fråga efter lagerinformation.</span><span class="sxs-lookup"><span data-stu-id="9bfe9-111">When the inventory lookup operation is started from the POS application, the POS cashier uses the numeric keyboard to enter a product number to query its inventory information.</span></span> <span data-ttu-id="9bfe9-112">Om den angivna produkten har varianter kan kassören välja dimensioner eller andra värden för att kontrollera lagerinformationen för en specifik produktvariant.</span><span class="sxs-lookup"><span data-stu-id="9bfe9-112">If the product entered has variants, the cashier can optionally select dimensions or other values to check inventory information of a specific product variant.</span></span>

## <a name="inventory-lookup-list-view-for-individual-products"></a><span data-ttu-id="9bfe9-113">List vy över lagersökning för enskilda produkter</span><span class="sxs-lookup"><span data-stu-id="9bfe9-113">Inventory lookup list view for individual products</span></span>

<span data-ttu-id="9bfe9-114">För en enskild produkt innehåller lagersökningsfunktionen en vy över lagersöklistan som visar följande produktinformation för en lista över platser:</span><span class="sxs-lookup"><span data-stu-id="9bfe9-114">For an individual product, the inventory lookup operation provides an inventory lookup list view showing the following product information for a list of locations:</span></span>

- <span data-ttu-id="9bfe9-115">**Lager** - Refererar till den "tillgängliga fysiska" kvantiteten för en produkt.</span><span class="sxs-lookup"><span data-stu-id="9bfe9-115">**Inventory** - Refers to the "available physical" quantity of a product.</span></span>
- <span data-ttu-id="9bfe9-116">**Reserverad** - Refererar till den "fysiska reserverade" kvantitet som hämtats från huvudkontoret.</span><span class="sxs-lookup"><span data-stu-id="9bfe9-116">**Reserved** - Refers to the "physical reserved" quantity retrieved from headquarters.</span></span>
- <span data-ttu-id="9bfe9-117">**Beställd** - Refererar till den kvantitet som "beställts totalt" som hämtats från huvudkontoret.</span><span class="sxs-lookup"><span data-stu-id="9bfe9-117">**Ordered** - Refers to the "ordered in total" quantity retrieved from headquarters.</span></span>
- <span data-ttu-id="9bfe9-118">**Enhet** - Refererar till den lagermåttenhet som konfigurerats i huvudkontoret.</span><span class="sxs-lookup"><span data-stu-id="9bfe9-118">**Unit** - Refers to the inventory unit of measure configured in headquarters.</span></span>

<span data-ttu-id="9bfe9-119">I listvyn över platser ingår alla butiker och lagerställen som har konfigurerats i uppfyllelsegrupperna som den aktuella butiken är kopplad till, enligt bilden nedan.</span><span class="sxs-lookup"><span data-stu-id="9bfe9-119">The list view of locations includes all stores and warehouses that are configured in the fulfillment groups that the current store is linked to, as shown in the following example image.</span></span>

![Listvy över lagersökningsfunktionen](media/inventory-lookup-list-view.png)

<span data-ttu-id="9bfe9-121">Följande åtgärder är tillgängliga i kassans appfält:</span><span class="sxs-lookup"><span data-stu-id="9bfe9-121">The following actions are available on the POS app bar:</span></span>

- <span data-ttu-id="9bfe9-122">**Sortera** – Med denna åtgärd kan POS-användaren sortera data i listvyn baserat på olika kriterier.</span><span class="sxs-lookup"><span data-stu-id="9bfe9-122">**Sort** - This action lets the POS user sort the data in the list view based on various criteria.</span></span> <span data-ttu-id="9bfe9-123">Platsbaserad sortering är standardsorteringsalternativet.</span><span class="sxs-lookup"><span data-stu-id="9bfe9-123">Location-based sorting is the default sort option.</span></span> 
  - <span data-ttu-id="9bfe9-124">**Geografisk plats** (från närmaste plats till mest avlägsen plats, från den aktuella butiken)</span><span class="sxs-lookup"><span data-stu-id="9bfe9-124">**Geo location** (from the closest location to the farthest location, compared with the current store)</span></span>
  - <span data-ttu-id="9bfe9-125">**Namn** (i stigande eller fallande ordning)</span><span class="sxs-lookup"><span data-stu-id="9bfe9-125">**Name** (in ascending or descending order)</span></span>
  - <span data-ttu-id="9bfe9-126">**Butiksnummer** (i stigande eller fallande ordning)</span><span class="sxs-lookup"><span data-stu-id="9bfe9-126">**Store number** (in ascending or descending order)</span></span>
  - <span data-ttu-id="9bfe9-127">**Lager** (i fallande ordning)</span><span class="sxs-lookup"><span data-stu-id="9bfe9-127">**Inventory** (in descending order)</span></span>
  - <span data-ttu-id="9bfe9-128">**Reserverad** (i fallande ordning)</span><span class="sxs-lookup"><span data-stu-id="9bfe9-128">**Reserved** (in descending order)</span></span>
  - <span data-ttu-id="9bfe9-129">**Beställd** (i fallande ordning)</span><span class="sxs-lookup"><span data-stu-id="9bfe9-129">**Ordered** (in descending order)</span></span>
- <span data-ttu-id="9bfe9-130">**Filter** – Med den här åtgärden kan POS-användaren visa filtrerade data för en viss plats.</span><span class="sxs-lookup"><span data-stu-id="9bfe9-130">**Filter** - This action lets the POS user view filtered data for a specific location.</span></span>
- <span data-ttu-id="9bfe9-131">**Visa butikstillgänglighet** - Med den här åtgärden kan POS-användaren visa ATP-kvantiteter (disponibelt att lova) för en produkt i den valda butiken.</span><span class="sxs-lookup"><span data-stu-id="9bfe9-131">**Show store availability** - This action lets the POS user view the available-to-promise (ATP) quantities for a product in the selected store.</span></span>
- <span data-ttu-id="9bfe9-132">**Visa butiksplats** – Med den här åtgärden öppnas en separat sida där mappningsvyn, adressen och butikstimmarna för den valda butiken visas.</span><span class="sxs-lookup"><span data-stu-id="9bfe9-132">**Show store location** - This action opens a separate page to show the map view, address, and store hours for the selected store.</span></span>
- <span data-ttu-id="9bfe9-133">**Hämta i butik** - Den här åtgärden skapar en kundorder för produkten som ska hämtas i den valda butiken, och dirigerar användaren till transaktionsskärmen.</span><span class="sxs-lookup"><span data-stu-id="9bfe9-133">**Pick up in store** - This action creates a customer order for the product that will be picked up from the selected store, and redirects the user to the transaction screen.</span></span>
- <span data-ttu-id="9bfe9-134">**Skicka produkt** - Den här åtgärden skapar en kundorder för produkten som ska skickas från den valda butiken, och dirigerar användaren till transaktionsskärmen.</span><span class="sxs-lookup"><span data-stu-id="9bfe9-134">**Ship product** - This action creates a customer order for the product that will be shipped from the selected store, and redirects the user to the transaction screen.</span></span>
- <span data-ttu-id="9bfe9-135">**Visa alla varianter** - För en produkt med varianter växlar den här åtgärden från en listvy till en matris som visar lagerinformation för alla varianter av produkten.</span><span class="sxs-lookup"><span data-stu-id="9bfe9-135">**View all variants** - For a product with variants, this action switches from a list view to a matrix view that displays inventory information for all variants of the product.</span></span>
- <span data-ttu-id="9bfe9-136">**Lägg till i transaktion** - Den här åtgärden lägger till produkten i varukorgen och dirigerar användaren till transaktionsskärmen.</span><span class="sxs-lookup"><span data-stu-id="9bfe9-136">**Add to transaction** - This action adds the product to the cart and redirects the user to the transaction screen.</span></span>

> [!NOTE]
> <span data-ttu-id="9bfe9-137">För en platsbaserad sortering bestäms avståndet mellan en plats och den aktuella butiken av de koordinater (latitud och longitud) som definierats i Commerce Headquarters.</span><span class="sxs-lookup"><span data-stu-id="9bfe9-137">For a location-based sort, the distance between a location and current store is determined by the coordinates (latitude and longitude) defined in Commerce headquarters.</span></span> <span data-ttu-id="9bfe9-138">För en butik definieras platsinformationen i den primära adressen till den verksamhetsenhet som är kopplad till butiken.</span><span class="sxs-lookup"><span data-stu-id="9bfe9-138">For a store, the location information is defined in the primary address of the operating unit associated with the store.</span></span> <span data-ttu-id="9bfe9-139">För ett lagerställe utan butik anges platsinformationen i lagerställesadressen.</span><span class="sxs-lookup"><span data-stu-id="9bfe9-139">For a non-store warehouse, the location information is defined in the warehouse address.</span></span> <span data-ttu-id="9bfe9-140">Om den aktuella butiken inte har koordinaterna som de ska, visas den aktuella butiken högst upp i listan och andra platser sorteras efter namn i det platsbaserade sorteringsalternativet.</span><span class="sxs-lookup"><span data-stu-id="9bfe9-140">If the current store doesn't have coordinates properly defined, the location-based sort option will display the current store at the top of the list and then sort other locations by name.</span></span>

> [!NOTE]
> <span data-ttu-id="9bfe9-141">Åtgärderna **Visa butikstillgänglighet**, **Visa butiksplats**, **Hämta i butik** och **Skicka produkt** är inte tillgängliga för platser utan butik.</span><span class="sxs-lookup"><span data-stu-id="9bfe9-141">The **Show store availability**, **Show store location**, **Pick up in store**, and **Ship product** actions are not available for non-store locations.</span></span>

## <a name="inventory-lookup-matrix-view-for-variants"></a><span data-ttu-id="9bfe9-142">Matrisvy av lagersökning efter varianter</span><span class="sxs-lookup"><span data-stu-id="9bfe9-142">Inventory lookup matrix view for variants</span></span>

<span data-ttu-id="9bfe9-143">För en huvudprodukt med varianter innehåller lagersökningsfunktionen också en dimensionsbaserad matrisvy som visar lagertillgänglighetsinformation för alla varianter av huvudprodukten på en vald plats.</span><span class="sxs-lookup"><span data-stu-id="9bfe9-143">For a master product with variants, the inventory lookup operation also provides a dimension-based matrix view that displays inventory availability information for all variants of the master product at a selected location.</span></span> <span data-ttu-id="9bfe9-144">Som standard visar matrisvyn data för den aktuella butiken.</span><span class="sxs-lookup"><span data-stu-id="9bfe9-144">By default, the matrix view shows data for the current store.</span></span> <span data-ttu-id="9bfe9-145">Du kan använda åtgärden **Butik** i appfältet för att söka efter lagerinformation från andra butiker som konfigurerats i uppfyllelsegrupperna som den aktuella butiken är kopplad till.</span><span class="sxs-lookup"><span data-stu-id="9bfe9-145">You can use the **Store** action on the app bar to look up inventory information at other stores configured in the fulfillment groups that the current store is linked to.</span></span>

<span data-ttu-id="9bfe9-146">Följande exempelbild visar matrisvyn av lagersökingen i kassan.</span><span class="sxs-lookup"><span data-stu-id="9bfe9-146">The following example image shows the inventory lookup matrix view in POS.</span></span>

![Matrisvy över lagersökningsfunktionen](media/inventory-lookup-matrix-view.png)

<span data-ttu-id="9bfe9-148">I matrisvyn representerar varje cell en enskild variant och visar lagerbehållning (fysiskt tillgängligt) i det nedre högra hörnet samt värden för **reserverade** (fysiskt reserverade) och **beställda** (beställt totalt) i det övre vänstra hörnet.</span><span class="sxs-lookup"><span data-stu-id="9bfe9-148">In the matrix view, each cell represents an individual variant, and displays an on-hand inventory (available physical) value in the lower-right corner, as well as **reserved** (physical reserved) and **ordered** (ordered in total) values in the upper-left corner.</span></span> <span data-ttu-id="9bfe9-149">Följande tabell förklarar innebörden av olika lagerbehållningsvärden.</span><span class="sxs-lookup"><span data-stu-id="9bfe9-149">The following table explains the meaning of the various on-hand values.</span></span>

| <span data-ttu-id="9bfe9-150">Behållningsvärde</span><span class="sxs-lookup"><span data-stu-id="9bfe9-150">On-hand value</span></span>                            | <span data-ttu-id="9bfe9-151">beskrivning</span><span class="sxs-lookup"><span data-stu-id="9bfe9-151">Description</span></span> |
|------------------------------------------|-------------|
| <span data-ttu-id="9bfe9-152">Numeriskt värde som är större än 0 (noll)</span><span class="sxs-lookup"><span data-stu-id="9bfe9-152">Numeric value that is more than 0 (zero)</span></span> | <span data-ttu-id="9bfe9-153">En variant har frisläppts till den angivna platsen och du kan utföra ytterligare åtgärder i cellen.</span><span class="sxs-lookup"><span data-stu-id="9bfe9-153">A variant has been released to the selected location, and you can perform additional actions in the cell.</span></span> |
| <span data-ttu-id="9bfe9-154">**0** (noll)</span><span class="sxs-lookup"><span data-stu-id="9bfe9-154">**0** (zero)</span></span>                             | <span data-ttu-id="9bfe9-155">En variant har frisläppts till den valda platsen, men artikeln är inte tillgänglig på den valda platsen.</span><span class="sxs-lookup"><span data-stu-id="9bfe9-155">A variant has been released to the selected location, but the item isn't available at the selected location.</span></span> <span data-ttu-id="9bfe9-156">Du kan utföra ytterligare åtgärder i cellen.</span><span class="sxs-lookup"><span data-stu-id="9bfe9-156">You can perform additional actions in the cell.</span></span> |
| <span data-ttu-id="9bfe9-157">**Ej tillämpligt** eller en inaktiv cell</span><span class="sxs-lookup"><span data-stu-id="9bfe9-157">**n/a**, or an inactive cell</span></span>              | <span data-ttu-id="9bfe9-158">En variant har inte frisläppts till den angivna platsen och du kan inte utföra ytterligare åtgärder i cellen.</span><span class="sxs-lookup"><span data-stu-id="9bfe9-158">A variant hasn't been released to the selected location, and you can't perform additional actions in the cell.</span></span> |

<span data-ttu-id="9bfe9-159">Visningsordningen för dimensionsvärdena i matrisvyn baseras på konfigurationen av visningsordningen i Commerce Headquarters.</span><span class="sxs-lookup"><span data-stu-id="9bfe9-159">The display order of the dimension values in the matrix view is based on the dimension display order configuration in Commerce headquarters.</span></span> <span data-ttu-id="9bfe9-160">Du kan ändra konfigurationen för visningsordningen genom att välja en ny dimension som ska användas.</span><span class="sxs-lookup"><span data-stu-id="9bfe9-160">You can change the dimension display order configuration by selecting a new dimension to use.</span></span> 

<span data-ttu-id="9bfe9-161">Följande åtgärder finns tillgängliga i matriscellen:</span><span class="sxs-lookup"><span data-stu-id="9bfe9-161">The following actions are available in the matrix view cell:</span></span>

- <span data-ttu-id="9bfe9-162">**Sälj nu** - Den här åtgärden lägger till den valda varianten i varukorgen och dirigerar användaren till transaktionsskärmen.</span><span class="sxs-lookup"><span data-stu-id="9bfe9-162">**Sell now** - This action adds the selected variant to the cart, and redirects the user to the transaction screen.</span></span>
- <span data-ttu-id="9bfe9-163">**Hämta i butik** - Den här åtgärden skapar en kundorder för den valda varianten som ska hämtas i den valda butiken, och dirigerar användaren till transaktionsskärmen.</span><span class="sxs-lookup"><span data-stu-id="9bfe9-163">**Pick up in store** - This action creates a customer order for the selected variant that will be picked up from the selected store, and redirects the user to the transaction screen.</span></span>
- <span data-ttu-id="9bfe9-164">**Skicka produkt** - Den här åtgärden skapar en kundorder för den valda varianten som ska skickas från den valda butiken, och dirigerar användaren till transaktionsskärmen.</span><span class="sxs-lookup"><span data-stu-id="9bfe9-164">**Ship product** - This action creates a customer order for the selected variant that will be shipped from the selected store, and redirects the user to the transaction screen.</span></span>
- <span data-ttu-id="9bfe9-165">**Tillgänglighet** – Med denna åtgärd förs användaren till en separat sida som visar ATP-kvantiteter för den valda varianten i den valda butiken.</span><span class="sxs-lookup"><span data-stu-id="9bfe9-165">**Availability** - This action takes the user to a separate page showing the ATP quantities for the selected variant in the selected store.</span></span>
- <span data-ttu-id="9bfe9-166">**Visa alla platser** - Den här åtgärden växlar till standardvyn för lagertillgänglighetslista som visar lagerinformation för den valda varianten.</span><span class="sxs-lookup"><span data-stu-id="9bfe9-166">**Show all locations** - This action switches to the standard inventory availability list view showing the inventory information for the selected variant.</span></span>
- <span data-ttu-id="9bfe9-167">**Visa produktdetaljer** - Den här åtgärden omdirigerar användaren till produktinformationssidan (PDP) för den valda varianten.</span><span class="sxs-lookup"><span data-stu-id="9bfe9-167">**View product details** - This action redirects the user to the product details page (PDP) of the selected variant.</span></span>

## <a name="access-inventory-lookup-from-other-pages-in-pos"></a><span data-ttu-id="9bfe9-168">Öppna lagersökning från andra sidor i kassan</span><span class="sxs-lookup"><span data-stu-id="9bfe9-168">Access inventory lookup from other pages in POS</span></span>

<span data-ttu-id="9bfe9-169">Kassaanvändarna kan komma åt lagersökningsfunktionen från andra sidor i kassan.</span><span class="sxs-lookup"><span data-stu-id="9bfe9-169">POS users can access the inventory lookup operation from other pages in POS.</span></span>

<span data-ttu-id="9bfe9-170">Följande exempelbild visar lagersökingsresultaten från en PDP i kassan.</span><span class="sxs-lookup"><span data-stu-id="9bfe9-170">The following example image shows inventory lookup results from a PDP in POS.</span></span>

![Lagersökning från produktinformationssidan](media/inventory-lookup-from-product-details-page.png)

<span data-ttu-id="9bfe9-172">På PDP för en huvudprodukt kan du använda åtgärden **Visa alla varianter** i appfältet för att öppna matrisvyn av lagersökningen som visar information om lagertillgänglighet för den aktuella butiken för alla varianter av en produkt.</span><span class="sxs-lookup"><span data-stu-id="9bfe9-172">On the PDP of a master product, you can use the **View all variants** action on the app bar to launch the inventory lookup matrix view that displays inventory availability information for the current store for all variants of a product.</span></span> <span data-ttu-id="9bfe9-173">För en enskild produkt visar PDP lagerbehållningen (tillgängligt fysiskt) för den produkten för den aktuella butiken.</span><span class="sxs-lookup"><span data-stu-id="9bfe9-173">For an individual product, the PDP displays the on-hand inventory (available physical) value of that product for the current store.</span></span> <span data-ttu-id="9bfe9-174">Dessutom kan du välja länken **Lager i andra butiker** för att öppna lagersökningsfunktionen för att kontrollera lagertillgängligheten av en produkt i andra butiker eller lager.</span><span class="sxs-lookup"><span data-stu-id="9bfe9-174">Additionally, you can select the **Other stores inventory** link to launch the inventory lookup operation to check the inventory availability of a product across other stores or warehouses.</span></span>

> [!NOTE]
> <span data-ttu-id="9bfe9-175">Åtgärden **Visa alla varianter** på PDP är bara tillgängligt för huvudprodukter som har varianter.</span><span class="sxs-lookup"><span data-stu-id="9bfe9-175">The **View all variants** action on the PDP is available only for master products that have variants.</span></span> <span data-ttu-id="9bfe9-176">Den är inte tillgänglig för specifika produkter eller paket.</span><span class="sxs-lookup"><span data-stu-id="9bfe9-176">It isn't available for specific products or kits.</span></span>

<span data-ttu-id="9bfe9-177">Du kan konfigurera lagersökningsfunktionen så att den visas som en länk i knapprutnätet på kassatransaktionsskärmen.</span><span class="sxs-lookup"><span data-stu-id="9bfe9-177">You can configure the inventory lookup operation to appear as a link in the button grid on the POS transaction screen.</span></span> <span data-ttu-id="9bfe9-178">Efter konfigurationen, när användaren väljer en varukorgsrad och sedan väljer knappen **Lagersökning** visas listvyn av lagersökningen för den valda produkten.</span><span class="sxs-lookup"><span data-stu-id="9bfe9-178">After configuration, when the user selects a cart line and then selects the **Inventory lookup** button, the inventory lookup list view for the selected product will be displayed.</span></span> <span data-ttu-id="9bfe9-179">Mer information om hur du konfigurerar knapprutnät med hjälp av verktyget för layout av kassaskärm finns i [Visuella konfigurationer av kassaanvändargränssnitt](pos-screen-layouts.md).</span><span class="sxs-lookup"><span data-stu-id="9bfe9-179">For more information about how to configure button grids using POS screen layout designer tool, see [POS user interface visual configurations](pos-screen-layouts.md).</span></span>

## <a name="inventory-lookup-with-channel-side-calculation"></a><span data-ttu-id="9bfe9-180">Lagersökning med beräkning på kanalsidan</span><span class="sxs-lookup"><span data-stu-id="9bfe9-180">Inventory lookup with channel-side calculation</span></span>

<span data-ttu-id="9bfe9-181">I Commerce-utgåvan 10.0.9 och tidigare hämtas det **tillgängliga fysiska** värdet i lagersökningsfunktionen från Commerce Headquarters via ett servicesamtal i realtid.</span><span class="sxs-lookup"><span data-stu-id="9bfe9-181">In Commerce release 10.0.9 and earlier, the **available physical** value in the inventory lookup operation is retrieved from Commerce headquarters via a real-time service call.</span></span> <span data-ttu-id="9bfe9-182">I Commerce-utgåvan 10.0.10 och senare kan du konfigurera lagersökningsfunktionen i kassan för att använda beräkning på kanalsidan på Commerce-servern för att fastställa det tillgängliga fysiska värdet, vilket kan ge en mer pålitlig och korrekt uppskattning av lagerbehållningen genom att ta transaktionsdata som ännu inte synkroniserats till huvudkontoret i beaktande.</span><span class="sxs-lookup"><span data-stu-id="9bfe9-182">In Commerce release 10.0.10 and later, you can configure the POS inventory lookup operation to use channel-side calculation on the Commerce server to determine the available physical value, which can provide a more reliable and more accurate estimate of the on-hand inventory by factoring in the transactional data that is not yet synchronized to headquarters.</span></span> <span data-ttu-id="9bfe9-183">Mer information om lagerberäkning på kanalsidan och relaterad kassakonfiguration i huvudkontoret finns i [Beräkna lagertillgänglighet för butikskanaler](calculated-inventory-retail-channels.md).</span><span class="sxs-lookup"><span data-stu-id="9bfe9-183">For more information about channel-side inventory calculation and related POS configuration in headquarters, see [Calculate inventory availability for retail channels](calculated-inventory-retail-channels.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9bfe9-184">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="9bfe9-184">Additional resources</span></span>

[<span data-ttu-id="9bfe9-185">Visuella konfigurationer för kassaanvändargränssnitt</span><span class="sxs-lookup"><span data-stu-id="9bfe9-185">POS user interface visual configurations</span></span>](pos-screen-layouts.md)

[<span data-ttu-id="9bfe9-186">Beräkna lagertillgänglighet för butikskanaler</span><span class="sxs-lookup"><span data-stu-id="9bfe9-186">Calculate inventory availability for retail channels</span></span>](calculated-inventory-retail-channels.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]