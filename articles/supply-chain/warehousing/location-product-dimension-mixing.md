---
title: Blandning av produktstorlekar på plats
description: Det här avsnittet innehåller information om hur du hanterar blandning av produktdimension för plats. Den här platsprofilfunktionen hjälper till att förbättra platshanteringen när produktvarianter eller produkter som har dimensioner används, t.ex. inom modebranschen. Med den kan du bestämma om konfigurationer, färger, utföranden och storlekar kan blandas för en viss platsprofil, eller om bara en av dessa dimensioner eller en kombination av dem kan placeras på samma plats.
author: Mirzaab
manager: tfehr
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLocationProfile, WHSReservationHierarchy, WHSInventTableReservationHierarchy
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 73519f3fe79d3d7d917d3044255f735640b8ccfd
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/16/2020
ms.locfileid: "4437991"
---
# <a name="location-product-dimension-mixing"></a><span data-ttu-id="56a3b-105">Blandning av produktstorlekar på plats</span><span class="sxs-lookup"><span data-stu-id="56a3b-105">Location product dimension mixing</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="56a3b-106">Blandning av produktdimension för plats är en platsprofilfunktion som hjälper till att förbättra platshanteringen när produktvarianter eller produkter som har dimensioner används, t.ex. inom modebranschen.</span><span class="sxs-lookup"><span data-stu-id="56a3b-106">Location product dimension mixing is location profile functionality that helps improve location management when product variants or products that have dimensions are used, such as in the fashion industry.</span></span> <span data-ttu-id="56a3b-107">Med den kan du bestämma om konfigurationer, färger, utföranden och storlekar kan blandas för en viss platsprofil, eller om bara en av dessa dimensioner eller en kombination av dem kan placeras på samma plats.</span><span class="sxs-lookup"><span data-stu-id="56a3b-107">It lets you decide whether configurations, colors, styles, and sizes can be mixed for a specific location profile, or whether just one of these dimensions or a combination of them can be put to the same location.</span></span>

## <a name="turn-on-the-location-product-dimension-mixing-feature"></a><span data-ttu-id="56a3b-108">Aktivera funktionen för blandning av produktdimension för plats</span><span class="sxs-lookup"><span data-stu-id="56a3b-108">Turn on the Location product dimension mixing feature</span></span>

<span data-ttu-id="56a3b-109">Innan du kan använda funktionen blandning av produktdimension för plats måste den aktiveras i ditt system.</span><span class="sxs-lookup"><span data-stu-id="56a3b-109">Before you can use location product dimension mixing, the feature must be turned on in your system.</span></span> <span data-ttu-id="56a3b-110">Administratörer kan använda arbetsytan [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den om det behövs.</span><span class="sxs-lookup"><span data-stu-id="56a3b-110">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="56a3b-111">Funktionen visas på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="56a3b-111">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="56a3b-112">**Modul:** *Lagerstyrning*</span><span class="sxs-lookup"><span data-stu-id="56a3b-112">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="56a3b-113">**Funktionens namn:** *blandning av produktdimension för plats*</span><span class="sxs-lookup"><span data-stu-id="56a3b-113">**Feature name:** *Location product dimension mixing*</span></span>

## <a name="setup"></a><span data-ttu-id="56a3b-114">Konfigurera</span><span class="sxs-lookup"><span data-stu-id="56a3b-114">Setup</span></span>

<span data-ttu-id="56a3b-115">Varje plats på lagerstället måste ha en platsprofil associerad som beskriver egenskaperna för platsen.</span><span class="sxs-lookup"><span data-stu-id="56a3b-115">Every location in the warehouse needs to have a location profile associated with it that describes the properties of the location.</span></span> <span data-ttu-id="56a3b-116">Därför kan alla platser som använder samma platsprofil tillåta blandning av produktdimensioner när den har ställts in.</span><span class="sxs-lookup"><span data-stu-id="56a3b-116">Therefore, all locations that use the same location profile will be able to allow product dimension mixing after it has been set up.</span></span>

### <a name="configure-location-profiles-to-allow-product-dimension-mixing"></a><span data-ttu-id="56a3b-117">Konfigurera platsprofiler för att tillåta blandning av produktdimensioner</span><span class="sxs-lookup"><span data-stu-id="56a3b-117">Configure location profiles to allow product dimension mixing</span></span>

1. <span data-ttu-id="56a3b-118">Gå till **Lagerstyrning \> Inställningar \> Lagerställe \> Platsprofiler**.</span><span class="sxs-lookup"><span data-stu-id="56a3b-118">Go to **Warehouse management \> Setup \> Warehouse \> Location profiles**.</span></span>
1. <span data-ttu-id="56a3b-119">I listan över platsprofiler, välj **BULK**.</span><span class="sxs-lookup"><span data-stu-id="56a3b-119">In the list of location profiles, select **BULK**.</span></span>
1. <span data-ttu-id="56a3b-120">I åtgärdsfönstret väljer du **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="56a3b-120">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="56a3b-121">På snabbfliken **Allmänt** ange alternativet **Aktivera blandning av produktdimension för plats** till *Ja*.</span><span class="sxs-lookup"><span data-stu-id="56a3b-121">On the **General** FastTab, set the **Enable location product dimension specific mixing** option to *Yes*.</span></span>

    > [!NOTE]
    > <span data-ttu-id="56a3b-122">Du kan ange det här alternativet till *Ja* endast om alternativet **Tillåt blandade artiklar** är inställt på *Nej*.</span><span class="sxs-lookup"><span data-stu-id="56a3b-122">You can set this option to *Yes* only if the **Allow mixed items** option is set to *No*.</span></span>

1. <span data-ttu-id="56a3b-123">På snabbfliken **Tillåten blandning av produktdimensioner** ange alternativet **storlek** till *Ja*.</span><span class="sxs-lookup"><span data-stu-id="56a3b-123">On the **Allowed product dimension mixing** FastTab, set the **Size** option to *Yes*.</span></span> <span data-ttu-id="56a3b-124">I det scenario som beskrivs i det här avsnittet kan blandning endast göras för produkter som har olika dimensioner för **storlek**.</span><span class="sxs-lookup"><span data-stu-id="56a3b-124">In the scenario that is described in this topic, mixing can be done only for products that have different **Size** dimensions.</span></span> <span data-ttu-id="56a3b-125">Andra alternativ är också tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="56a3b-125">However, other options are also available.</span></span>
1. <span data-ttu-id="56a3b-126">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="56a3b-126">Select **Save**.</span></span>

### <a name="create-a-new-product-master-and-product-variants"></a><span data-ttu-id="56a3b-127">Skapa en ny produktmallar och produktvarianter</span><span class="sxs-lookup"><span data-stu-id="56a3b-127">Create a new product master and product variants</span></span>

1. <span data-ttu-id="56a3b-128">Gå till **Hantering av produktinformation \> Produkter \> Produktmallar**.</span><span class="sxs-lookup"><span data-stu-id="56a3b-128">Go to **Product information management \> Products \> Product masters**.</span></span>
1. <span data-ttu-id="56a3b-129">I åtgärdsfönstret, välj **Ny** för att skapa en produktmall.</span><span class="sxs-lookup"><span data-stu-id="56a3b-129">On the Action Pane, select **New** to create a product master.</span></span>
1. <span data-ttu-id="56a3b-130">I dialogrutan **Ny produkt** anger du följande värden:</span><span class="sxs-lookup"><span data-stu-id="56a3b-130">In the **New product** dialog box, set the following values:</span></span>

    - <span data-ttu-id="56a3b-131">**Produkttyp:** *Artikel*</span><span class="sxs-lookup"><span data-stu-id="56a3b-131">**Product type:** *Item*</span></span>
    - <span data-ttu-id="56a3b-132">**Delprodukttyp:** *Produktmall*</span><span class="sxs-lookup"><span data-stu-id="56a3b-132">**Product subtype:** *Product master*</span></span>
    - <span data-ttu-id="56a3b-133">**Produknummer:** *B0001*</span><span class="sxs-lookup"><span data-stu-id="56a3b-133">**Product number:** *B0001*</span></span>
    - <span data-ttu-id="56a3b-134">**Produktnamn:** *B0001 storlek*</span><span class="sxs-lookup"><span data-stu-id="56a3b-134">**Product name:** *B0001 Size*</span></span>
    - <span data-ttu-id="56a3b-135">**Produktdimensionsgrupp:** *Storlek*</span><span class="sxs-lookup"><span data-stu-id="56a3b-135">**Product dimension group:** *Size*</span></span>
    - <span data-ttu-id="56a3b-136">**Konfigurationsteknik:** *fördefinierade varianten*</span><span class="sxs-lookup"><span data-stu-id="56a3b-136">**Configuration technology:** *Predefined variant*</span></span>

1. <span data-ttu-id="56a3b-137">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="56a3b-137">Select **OK**.</span></span>
1. <span data-ttu-id="56a3b-138">På sidan **Produktinformation** på snabbfliken **Allmänt** anger du följande värden:</span><span class="sxs-lookup"><span data-stu-id="56a3b-138">On the **Product details** page, on the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="56a3b-139">**Generera varianter automatiskt:** *Ja*</span><span class="sxs-lookup"><span data-stu-id="56a3b-139">**Generate variants automatically:** *Yes*</span></span>
    - <span data-ttu-id="56a3b-140">**Storleksgrupp:** *CASUALDHIR*</span><span class="sxs-lookup"><span data-stu-id="56a3b-140">**Size group:** *CASUALDHIR*</span></span>

1. <span data-ttu-id="56a3b-141">Om du vill visa de fördefinierade varianterna väljer du **produktvarianter** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="56a3b-141">To view the predefined variants, on the Action Pane, select **Product variants**.</span></span>

    <span data-ttu-id="56a3b-142">Sidan **Produktvarianter** visas och visar en lista med varianter från konfiguration av storleksgruppen.</span><span class="sxs-lookup"><span data-stu-id="56a3b-142">The **Product variants** page appears and shows a list of variants from the configuration of the size group.</span></span>

### <a name="release-products-to-the-usmf-company"></a><span data-ttu-id="56a3b-143">Frisläpp produkter till USMF-företag</span><span class="sxs-lookup"><span data-stu-id="56a3b-143">Release products to the USMF company</span></span>

1. <span data-ttu-id="56a3b-144">Välj **Frisläpp produkter** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="56a3b-144">On the Action Pane, select **Release products**.</span></span>
1. <span data-ttu-id="56a3b-145">På sidan **Välj produkter att frisläppa** bekräftar du att produktnumret *B0001* finns i listan och väljer **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="56a3b-145">On the **Select products to release** page, confirm that product number *B0001* is in the list, and then select **Next**.</span></span>
1. <span data-ttu-id="56a3b-146">Välj **Nästa** för att bekräfta de produktvarianter som ska frisläppas.</span><span class="sxs-lookup"><span data-stu-id="56a3b-146">Select **Next** to confirm the product variants to release.</span></span>
1. <span data-ttu-id="56a3b-147">På sidan **Välj företag att frisläppa till**, välj *USMF* och sedan **Nästa** för att bekräfta valet.</span><span class="sxs-lookup"><span data-stu-id="56a3b-147">On the **Select companies to release to** page, select *USMF*, and then select **Next** to confirm the selection.</span></span>
1. <span data-ttu-id="56a3b-148">På sidan **Bekräfta val** väljer du **slutför** för att slutföra frisläppandet.</span><span class="sxs-lookup"><span data-stu-id="56a3b-148">On the **Confirm selection** page, select **Finish** to complete the release.</span></span>

    <span data-ttu-id="56a3b-149">Du får ett meddelande Operationen är klar.</span><span class="sxs-lookup"><span data-stu-id="56a3b-149">You receive an "Operation completed" message.</span></span>

### <a name="update-a-released-product-in-the-usmf-company"></a><span data-ttu-id="56a3b-150">Uppdatera en frisläppt produkt i USMF företaget</span><span class="sxs-lookup"><span data-stu-id="56a3b-150">Update a released product in the USMF company</span></span>

1. <span data-ttu-id="56a3b-151">Kontrollera att du är inloggad på **USMF**-företaget.</span><span class="sxs-lookup"><span data-stu-id="56a3b-151">Make sure that you're signed in to the **USMF** company.</span></span>
1. <span data-ttu-id="56a3b-152">Gå till **produktinformationshantering \> produkter \> frisläppta produkter** för att avsluta skapa den frisläppta produkten.</span><span class="sxs-lookup"><span data-stu-id="56a3b-152">Go to **Product information management \> Products \> Released products** to finish creating the released product.</span></span>
1. <span data-ttu-id="56a3b-153">Sök och välj artikelnummer *B0001* om du vill öppna sidan **information om frisläppta produkter**.</span><span class="sxs-lookup"><span data-stu-id="56a3b-153">Find and select item number *B0001* to open the **Released product details** page.</span></span>
1. <span data-ttu-id="56a3b-154">I åtgärdsfönstret väljer du **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="56a3b-154">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="56a3b-155">På snabbfliken **Allmänt** ser du till att fältet **artikelmodellgrupp** är inställt på *FIFO*.</span><span class="sxs-lookup"><span data-stu-id="56a3b-155">On the **General** FastTab, make sure that the **Item model group** field is set to *FIFO*.</span></span>
1. <span data-ttu-id="56a3b-156">I åtgärdsfönstret, på fliken **Produkt** i gruppen **Konfigurering**, markerar du **Dimensionsgrupper**.</span><span class="sxs-lookup"><span data-stu-id="56a3b-156">On the Action Pane, on the **Product** tab, in the **Set up** group, select **Dimension groups**.</span></span>
1. <span data-ttu-id="56a3b-157">Ange följande värden.</span><span class="sxs-lookup"><span data-stu-id="56a3b-157">Set the following values:</span></span>

    - <span data-ttu-id="56a3b-158">**Lagringsdimensionsgrupp:** *Lager*</span><span class="sxs-lookup"><span data-stu-id="56a3b-158">**Storage dimension group:** *Ware*</span></span>
    - <span data-ttu-id="56a3b-159">**Spårningsdimensionsgrupp:** *Ingen*</span><span class="sxs-lookup"><span data-stu-id="56a3b-159">**Tracking dimension group:** *None*</span></span>

1. <span data-ttu-id="56a3b-160">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="56a3b-160">Select **OK**.</span></span>
1. <span data-ttu-id="56a3b-161">I åtgärdsfönstret, på fliken **Produkt** i gruppen **Konfigurering**, markerar du **Reservationshierarki**.</span><span class="sxs-lookup"><span data-stu-id="56a3b-161">On the Action Pane, on the **Product** tab, in the **Set up** group, select **Reservation hierarchy**.</span></span>
1. <span data-ttu-id="56a3b-162">Ställ in fältet **Reservationshierarki** till *Standard* och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="56a3b-162">Set the **Reservation hierarchy** field to *Default*, and then select **OK**.</span></span>
1. <span data-ttu-id="56a3b-163">På snabbfliken **Allmänt** i avsnittet **Administration** ser du att dina val har uppdaterats.</span><span class="sxs-lookup"><span data-stu-id="56a3b-163">On the **General** FastTab, in the **Administration** section, notice that your selections have been updated.</span></span>
1. <span data-ttu-id="56a3b-164">På snabbfliken **Inköp** i fältet **Pris** ange *10*.</span><span class="sxs-lookup"><span data-stu-id="56a3b-164">On the **Purchase** FastTab, in the **Price** field, enter *10*.</span></span>
1. <span data-ttu-id="56a3b-165">På fliken **hantera kostnader** i fältet **artikelgrupp** anger du *Ljud*.</span><span class="sxs-lookup"><span data-stu-id="56a3b-165">On the **Manage costs** FastTab, in the **Item group** field, enter *Audio*.</span></span>
1. <span data-ttu-id="56a3b-166">På snabbfliken **Inköp** i fältet **Pris** ange *10*.</span><span class="sxs-lookup"><span data-stu-id="56a3b-166">On the **Purchase** FastTab, in the **Price** field, enter *10*.</span></span>
1. <span data-ttu-id="56a3b-167">På snabbfliken **lagerställe** i fältet **enhetssekvensgrupp- ID** anger du *ea*.</span><span class="sxs-lookup"><span data-stu-id="56a3b-167">On the **Warehouse** FastTab, in the **Unit sequence group ID** field, enter *ea*.</span></span>
1. <span data-ttu-id="56a3b-168">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="56a3b-168">Select **Save**.</span></span>

### <a name="create-a-location-directive"></a><span data-ttu-id="56a3b-169">Skapa ett platsdirektiv</span><span class="sxs-lookup"><span data-stu-id="56a3b-169">Create a location directive</span></span>

1. <span data-ttu-id="56a3b-170">Gå till **Lagerstyrning \> Inställningar \> Platsdirektiv**.</span><span class="sxs-lookup"><span data-stu-id="56a3b-170">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="56a3b-171">I vänstra fönstret i fältet **Typ av arbetsorder** väljer du *Inköpsorder*.</span><span class="sxs-lookup"><span data-stu-id="56a3b-171">In the left pane, in the **Work order type** field, select *Purchase orders*.</span></span>
1. <span data-ttu-id="56a3b-172">I listan väljer du platsdirektivet med namnet *24 PO direkt*.</span><span class="sxs-lookup"><span data-stu-id="56a3b-172">In the list, select the location directive that is named *24 PO Direct*.</span></span>
1. <span data-ttu-id="56a3b-173">På snabbfliken **Platsdirektivåtgärder** välj **Ny** för att lägga till en rad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="56a3b-173">On the **Location Directive Actions** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="56a3b-174">Ställ in följande värden på denna nya rad:</span><span class="sxs-lookup"><span data-stu-id="56a3b-174">On the new line, set the following values:</span></span>

    - <span data-ttu-id="56a3b-175">**Löpnummer:** *1*</span><span class="sxs-lookup"><span data-stu-id="56a3b-175">**Sequence number:** *1*</span></span>

        <span data-ttu-id="56a3b-176">Den nya raden ska ligga framför den befintliga raden.</span><span class="sxs-lookup"><span data-stu-id="56a3b-176">The new line should be in front of the previously existing line.</span></span> <span data-ttu-id="56a3b-177">Om du vill göra ändringen använder du knapparna **Flytta upp** och **Flytta ned** i verktygsfältet eller ändrar värdet för **löpnummer** för den befintliga raden till *2*.</span><span class="sxs-lookup"><span data-stu-id="56a3b-177">To make the change, use the **Move up** and **Move down** buttons on the toolbar, or change the existing line's **Sequence number** value to *2*.</span></span>

    - <span data-ttu-id="56a3b-178">**Namn:** *Placera i BULK platsprofil*</span><span class="sxs-lookup"><span data-stu-id="56a3b-178">**Name:** *Put to BULK Location profile*</span></span>
    - <span data-ttu-id="56a3b-179">**Användning av fast lagerplats:** *Fasta och ej fasta platser*</span><span class="sxs-lookup"><span data-stu-id="56a3b-179">**Fixed location usage:** *Fixed and non-fixed locations*</span></span>
    - <span data-ttu-id="56a3b-180">**Tillåt negativt lager:** *Avmarkera den här kryssrutan (=Nej)*</span><span class="sxs-lookup"><span data-stu-id="56a3b-180">**Allow negative inventory:** *Clear this check box (=No)*</span></span>
    - <span data-ttu-id="56a3b-181">**Batchaktiverad:** *Avmarkera den här kryssrutan (=Nej)*</span><span class="sxs-lookup"><span data-stu-id="56a3b-181">**Batch enabled:** *Clear this check box (=No)*</span></span>
    - <span data-ttu-id="56a3b-182">**Strategi:** *ingen*</span><span class="sxs-lookup"><span data-stu-id="56a3b-182">**Strategy:** *None*</span></span>

1. <span data-ttu-id="56a3b-183">Medan den nya raden fortfarande är markerad väljer du **redigeringsfråga** ovanför rutnätet.</span><span class="sxs-lookup"><span data-stu-id="56a3b-183">While the new line is still selected, select **Edit query** above the grid.</span></span>
1. <span data-ttu-id="56a3b-184">I dialogrutan fråga på fliken **Intervall** välj **Lägg till** om du vill lägga till en rad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="56a3b-184">In the query dialog box, on the **Range** tab, select **Add** to add a line to the grid.</span></span>
1. <span data-ttu-id="56a3b-185">Ställ in följande värden på denna nya rad:</span><span class="sxs-lookup"><span data-stu-id="56a3b-185">On the new line, set the following values:</span></span>

    - <span data-ttu-id="56a3b-186">**Register:** *platser*</span><span class="sxs-lookup"><span data-stu-id="56a3b-186">**Table:** *Locations*</span></span>
    - <span data-ttu-id="56a3b-187">**Härlett register:** *platser*</span><span class="sxs-lookup"><span data-stu-id="56a3b-187">**Derived table:** *Locations*</span></span>
    - <span data-ttu-id="56a3b-188">**Fält:** *platsprofil-ID*</span><span class="sxs-lookup"><span data-stu-id="56a3b-188">**Field:** *Location profile ID*</span></span>
    - <span data-ttu-id="56a3b-189">**Kriterier:** *BULK*</span><span class="sxs-lookup"><span data-stu-id="56a3b-189">**Criteria:** *BULK*</span></span>

1. <span data-ttu-id="56a3b-190">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="56a3b-190">Select **OK**.</span></span>
1. <span data-ttu-id="56a3b-191">På sidan **platsdirektiv** i åtgärdsfönstret, välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="56a3b-191">On the **Location directives** page, on the Action Pane, select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="56a3b-192">På snabbfliken **Platsdirektivåtgärder** i fältet **Strategi** om du använder *Konsolidera* platsstrategi, kommer inställningen av snabbfliken **Tillåten blandning av produktdimensioner** i **Platsprofiler** kommer att åsidosättas och objekt kommer att placeras på samma plats även om detta beteende inte tillåts av installationen.</span><span class="sxs-lookup"><span data-stu-id="56a3b-192">On the **Location Directive Actions** FastTab **Strategy** field, if you use the *Consolidate* location strategy, the setup of the **Allowed product dimension mixing** FastTab on the **Location profiles** will be overridden, and items will be put to the same location even if this behavior isn't allowed by the setup.</span></span>

### <a name="create-a-mobile-device-menu-item"></a><span data-ttu-id="56a3b-193">Skapa ett menykommando för mobila enheter</span><span class="sxs-lookup"><span data-stu-id="56a3b-193">Create a mobile device menu item</span></span>

1. <span data-ttu-id="56a3b-194">Gå till **Lagerstyrning \> Inställningar \> Mobil enhet \> Menyalternativ på mobil enhet**.</span><span class="sxs-lookup"><span data-stu-id="56a3b-194">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="56a3b-195">I åtgärdsfönstret, välj **Ny** för att skapa ett menyalternativ som ska användas för sortering.</span><span class="sxs-lookup"><span data-stu-id="56a3b-195">On the Action Pane, select **New** to create a menu item to use for sorting.</span></span>
1. <span data-ttu-id="56a3b-196">I rubriken anger du följande värden:</span><span class="sxs-lookup"><span data-stu-id="56a3b-196">In the header, set the following values:</span></span>

    - <span data-ttu-id="56a3b-197">**Menyalternativnamn:** *Inleverans av inköpsorderrad*</span><span class="sxs-lookup"><span data-stu-id="56a3b-197">**Menu item name:** *PO line receiving*</span></span>
    - <span data-ttu-id="56a3b-198">**Rubrik:** *Inleverans av inköpsorderrad*</span><span class="sxs-lookup"><span data-stu-id="56a3b-198">**Title:** *PO line receiving*</span></span>
    - <span data-ttu-id="56a3b-199">**Läge:** *arbete*</span><span class="sxs-lookup"><span data-stu-id="56a3b-199">**Mode:** *Work*</span></span>
    - <span data-ttu-id="56a3b-200">**Använd befintligt arbete:** *Nej*</span><span class="sxs-lookup"><span data-stu-id="56a3b-200">**Use existing work:** *No*</span></span>

1. <span data-ttu-id="56a3b-201">Ange följande värden på snabbfliken **Allmänt**:</span><span class="sxs-lookup"><span data-stu-id="56a3b-201">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="56a3b-202">**Arbetsskapandeprocess:** *Inköpsorderrad har inlevererats och inlagrats*</span><span class="sxs-lookup"><span data-stu-id="56a3b-202">**Work creation process:** *Purchase order line receiving and putaway*</span></span>
    - <span data-ttu-id="56a3b-203">**Generera ID-nummer:** *Ja*</span><span class="sxs-lookup"><span data-stu-id="56a3b-203">**Generate license plate:** *Yes*</span></span>

1. <span data-ttu-id="56a3b-204">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="56a3b-204">Select **Save**.</span></span>

### <a name="configure-the-mobile-device-menu"></a><span data-ttu-id="56a3b-205">Konfigurera mobilenhetsmeny</span><span class="sxs-lookup"><span data-stu-id="56a3b-205">Configure the mobile device menu</span></span>

1. <span data-ttu-id="56a3b-206">Gå till **Lagerstyrning \> Inställningar \> Mobil enhet \> Meny på mobil enhet**.</span><span class="sxs-lookup"><span data-stu-id="56a3b-206">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu**.</span></span>
1. <span data-ttu-id="56a3b-207">I listan över menyer, välj **Inkommande**.</span><span class="sxs-lookup"><span data-stu-id="56a3b-207">In the list of menus, select **Inbound**.</span></span>
1. <span data-ttu-id="56a3b-208">I åtgärdsfönstret väljer du **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="56a3b-208">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="56a3b-209">I listan **Tillgängliga menyer och artiklar** hittar du och väljer menyalternativet **Inleverans av inköpsorderrad**.</span><span class="sxs-lookup"><span data-stu-id="56a3b-209">In the **Available Menus And Menu Items** list, find and select the **PO line receiving** menu item.</span></span>
1. <span data-ttu-id="56a3b-210">Klicka på högerpilen för att flytta menyalternativet **Inleverans av inköpsorderrad** till listan **Menystruktur**.</span><span class="sxs-lookup"><span data-stu-id="56a3b-210">Select the right arrow button to move the **PO line receiving** menu item to the **Menu Structure** list.</span></span> <span data-ttu-id="56a3b-211">På det här sättet lägger du till det nya menyalternativet på den valda menyn.</span><span class="sxs-lookup"><span data-stu-id="56a3b-211">In this way, you add your new menu item to the selected menu.</span></span>
1. <span data-ttu-id="56a3b-212">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="56a3b-212">Select **Save**.</span></span>

## <a name="scenario"></a><span data-ttu-id="56a3b-213">Scenario</span><span class="sxs-lookup"><span data-stu-id="56a3b-213">Scenario</span></span>

<span data-ttu-id="56a3b-214">Det här demoscenariot visar hur två olika produktvarianter kan placeras på samma plats när lagerställeprofilen inte tillåter blandade artiklar, men funktionen *blandning av produktdimension för plats* är aktiverad.</span><span class="sxs-lookup"><span data-stu-id="56a3b-214">This demo scenario shows how two different product variants can be put to the same location when the location profile doesn't allow for mixed items, but the *Location product dimension mixing* feature is enabled.</span></span> <span data-ttu-id="56a3b-215">I det här fallet ska du använda varianten **storlek** som kriterium.</span><span class="sxs-lookup"><span data-stu-id="56a3b-215">In this case, you will use the **Size** variant as the criterion.</span></span>

<span data-ttu-id="56a3b-216">Innan du börjar ska du kontrollera att det finns tomma platser i lagerstället *24* som använder platsprofil *BULK*.</span><span class="sxs-lookup"><span data-stu-id="56a3b-216">Before you begin, make sure that there are empty locations in warehouse *24* that use the *BULK* location profile.</span></span>

### <a name="create-a-purchase-order"></a><span data-ttu-id="56a3b-217">Skapa en inköpsorder</span><span class="sxs-lookup"><span data-stu-id="56a3b-217">Create a purchase order</span></span>

<span data-ttu-id="56a3b-218">Du skapar en inköpsorder med tre rader: två rader för samma produktnummer men olika varianter av **storlek** och en tredje rad för en annan produkt utan varianter.</span><span class="sxs-lookup"><span data-stu-id="56a3b-218">You will create a purchase order that has three lines: two lines for the same product number but different **Size** variants, and a third line for a different product that has no variants.</span></span>

1. <span data-ttu-id="56a3b-219">Gå till **Leverantörsreskontra \> Inköpsorder \> Alla inköpsorder**.</span><span class="sxs-lookup"><span data-stu-id="56a3b-219">Go to **Accounts payable \> Purchase orders \> All purchase orders**.</span></span>
1. <span data-ttu-id="56a3b-220">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="56a3b-220">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="56a3b-221">I dialogrutan **Skapa inköpsorder** ställ in följande värden:</span><span class="sxs-lookup"><span data-stu-id="56a3b-221">In the **Create purchase order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="56a3b-222">**Leverantörskonto:** *1001*</span><span class="sxs-lookup"><span data-stu-id="56a3b-222">**Vendor account:** *1001*</span></span>
    - <span data-ttu-id="56a3b-223">**Lagerställe:** *24*</span><span class="sxs-lookup"><span data-stu-id="56a3b-223">**Warehouse:** *24*</span></span>

1. <span data-ttu-id="56a3b-224">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="56a3b-224">Select **OK**.</span></span>
1. <span data-ttu-id="56a3b-225">Inköpsordern skapas och en ny rad läggs till på snabbfliken **inköpsorderrader**.</span><span class="sxs-lookup"><span data-stu-id="56a3b-225">The purchase order is created, and a new line is added on the **Purchase order lines** FastTab.</span></span> <span data-ttu-id="56a3b-226">Anteckna inköpsordernumret.</span><span class="sxs-lookup"><span data-stu-id="56a3b-226">Make a note of the purchase order number.</span></span>
1. <span data-ttu-id="56a3b-227">Ställ in följande värden på denna nya rad:</span><span class="sxs-lookup"><span data-stu-id="56a3b-227">On the new line, set the following values:</span></span>

    - <span data-ttu-id="56a3b-228">**Artikelnummer:** *B0001*</span><span class="sxs-lookup"><span data-stu-id="56a3b-228">**Item number:** *B0001*</span></span>
    - <span data-ttu-id="56a3b-229">**Storlek** *L*</span><span class="sxs-lookup"><span data-stu-id="56a3b-229">**Size** *L*</span></span>
    - <span data-ttu-id="56a3b-230">**Kvantitet:** *2*</span><span class="sxs-lookup"><span data-stu-id="56a3b-230">**Quantity:** *2*</span></span>

1. <span data-ttu-id="56a3b-231">Välj **Lägg till rad** ovanför rutnätet för att lägga till en andra inköpsorderrad och ställa in följande värden:</span><span class="sxs-lookup"><span data-stu-id="56a3b-231">Select **Add line** above the grid to add a second purchase order line, and set the following values:</span></span>

    - <span data-ttu-id="56a3b-232">**Artikelnummer:** *B0001*</span><span class="sxs-lookup"><span data-stu-id="56a3b-232">**Item number:** *B0001*</span></span>
    - <span data-ttu-id="56a3b-233">**Storlek** *XL*</span><span class="sxs-lookup"><span data-stu-id="56a3b-233">**Size** *XL*</span></span>
    - <span data-ttu-id="56a3b-234">**Kvantitet:** *2*</span><span class="sxs-lookup"><span data-stu-id="56a3b-234">**Quantity:** *2*</span></span>

1. <span data-ttu-id="56a3b-235">Välj **Lägg till rad** för att lägga till en tredje inköpsorderrad och ställa in följande värden:</span><span class="sxs-lookup"><span data-stu-id="56a3b-235">Select **Add line** to add a third purchase order line, and set the following values:</span></span>

    - <span data-ttu-id="56a3b-236">**Artikelnummer:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="56a3b-236">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="56a3b-237">**Kvantitet:** *1*</span><span class="sxs-lookup"><span data-stu-id="56a3b-237">**Quantity:** *1*</span></span>

<span data-ttu-id="56a3b-238">1. Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="56a3b-238">1.Select **Save**.</span></span>

### <a name="receive-purchase-order-lines-in-the-warehouse-app"></a><span data-ttu-id="56a3b-239">Ta emot inköpsorderrader i lagerställeappen</span><span class="sxs-lookup"><span data-stu-id="56a3b-239">Receive purchase order lines in the warehouse app</span></span>

1. <span data-ttu-id="56a3b-240">Logga in på lagerställeappen som en användare som är aktiverad för lagerstället *24*.</span><span class="sxs-lookup"><span data-stu-id="56a3b-240">Sign in to the warehouse app as a user who is enabled for warehouse *24*.</span></span>
1. <span data-ttu-id="56a3b-241">Välj menyn **Inkommande**.</span><span class="sxs-lookup"><span data-stu-id="56a3b-241">Select the **Inbound** menu.</span></span>
1. <span data-ttu-id="56a3b-242">Välj **Inleverans av inköpsorderrad**.</span><span class="sxs-lookup"><span data-stu-id="56a3b-242">Select **PO Line receiving**.</span></span>
1. <span data-ttu-id="56a3b-243">Markera fältet **PONUM**, ange inköpsordernummer och bekräfta.</span><span class="sxs-lookup"><span data-stu-id="56a3b-243">Select the **PONUM** field, and then enter the purchase order number.</span></span>
1. <span data-ttu-id="56a3b-244">Bekräfta registreringen genom att välja knappen bekräfta (✔) längst ned på sidan.</span><span class="sxs-lookup"><span data-stu-id="56a3b-244">Confirm your entry by selecting the confirm button ( ✔ ) at the bottom of the page.</span></span>
1. <span data-ttu-id="56a3b-245">Ange radnumret från inköpsordern som ska inlevereras.</span><span class="sxs-lookup"><span data-stu-id="56a3b-245">Enter the line number from the purchase order that is being received.</span></span> <span data-ttu-id="56a3b-246">Markera fältet **LINENUM** och använd sedan det numeriska tangentbordet för att ange *1*.</span><span class="sxs-lookup"><span data-stu-id="56a3b-246">Select the **LINENUM** field, and then use the number pad to enter *1*.</span></span>
1. <span data-ttu-id="56a3b-247">Bekräfta din inmatning.</span><span class="sxs-lookup"><span data-stu-id="56a3b-247">Confirm your entry.</span></span>
1. <span data-ttu-id="56a3b-248">Ange den kvantitet som ska ta emot.</span><span class="sxs-lookup"><span data-stu-id="56a3b-248">Enter the quantity to receive.</span></span> <span data-ttu-id="56a3b-249">Markera knappen plustecken (**+**) två gånger för att öka värdet i fältet **Kvt** till *2*.</span><span class="sxs-lookup"><span data-stu-id="56a3b-249">Select the plus sign (**+**) button two times to increase the value in the **Qty** field to *2*.</span></span>
1. <span data-ttu-id="56a3b-250">Registrera din registrering genom att välja knappen (✔) längst ned på sidan och bekräfta registreringen genom att välja knappen (✔) igen.</span><span class="sxs-lookup"><span data-stu-id="56a3b-250">Register your entry by selecting the button ( ✔ ) at the bottom of the page, and then confirm your entry by selecting the button ( ✔ ) again.</span></span>
1. <span data-ttu-id="56a3b-251">Visa informationen på sidan **Inköpsorder: placera**.</span><span class="sxs-lookup"><span data-stu-id="56a3b-251">View the information on the **Purchase orders: Put** page.</span></span> <span data-ttu-id="56a3b-252">På den här sidan visas det arbete som har skapats för artikelinförseln (arbete 1).</span><span class="sxs-lookup"><span data-stu-id="56a3b-252">This page shows the work that has been created for the put-away (Work 1).</span></span>

    <span data-ttu-id="56a3b-253">Platsen där den mottagna artikeln ska föras in, ID-nummer, artikeln, storleken och kvantiteten för **Inleverans av inköpsorderrad** som du just har slutfört visas.</span><span class="sxs-lookup"><span data-stu-id="56a3b-253">The location where the received item will be put away, the license plate, the item, the size, and the quantity of the **PO Line receiving** task that you just completed are shown.</span></span>

1. <span data-ttu-id="56a3b-254">Bekräfta artikelinförselarbetet.</span><span class="sxs-lookup"><span data-stu-id="56a3b-254">Confirm the put-away work.</span></span>
1. <span data-ttu-id="56a3b-255">Upprepa steg 4 till 11 för inköpsorderraden 2.</span><span class="sxs-lookup"><span data-stu-id="56a3b-255">Repeat the steps 4 through 11 for the purchase order line 2.</span></span> <span data-ttu-id="56a3b-256">I steg 8 ska du emellertid ange en kvantitet på *1*.</span><span class="sxs-lookup"><span data-stu-id="56a3b-256">However, in step 8, specify a quantity of *1*.</span></span>

    <span data-ttu-id="56a3b-257">Nytt artikelinförselarbete (arbete 2) skapas för samma plats som arbete 1.</span><span class="sxs-lookup"><span data-stu-id="56a3b-257">New put-away work (Work 2) is created for the same location as Work 1.</span></span>

1. <span data-ttu-id="56a3b-258">Upprepa steg 4 till 11 för inköpsorderraden 2.</span><span class="sxs-lookup"><span data-stu-id="56a3b-258">Repeat the steps 4 through 11 again for purchase order line 2.</span></span> <span data-ttu-id="56a3b-259">I steg 8 ska du ange kvarvarande kvantitet på *1*.</span><span class="sxs-lookup"><span data-stu-id="56a3b-259">In step 8, specify the remaining quantity of *1*.</span></span>

    <span data-ttu-id="56a3b-260">Nytt artikelinförselarbete (arbete 3) skapas för samma plats som arbete 1 och arbete 2.</span><span class="sxs-lookup"><span data-stu-id="56a3b-260">New put-away work (Work 3) is created for the same location as Work 1 and Work 2.</span></span> <span data-ttu-id="56a3b-261">Det här problemet beror på att den *konsoliderade* platsens direktivstrategi används och snabbfliken **Tillåten blandning av produktdimensioner** i inställningen *Bulk* **Platsprofiler** tillåter att varianten **Storlek** blandas på plats.</span><span class="sxs-lookup"><span data-stu-id="56a3b-261">This behavior occurs because the *Consolidate* location directive strategy is used, and the **Allowed product dimension mixing** FastTab on the *Bulk* **Location profiles** setup allows the **Size** variant to be mixed on a location.</span></span>

1. <span data-ttu-id="56a3b-262">Upprepa steg 4 till 11 för inköpsorderraden 3.</span><span class="sxs-lookup"><span data-stu-id="56a3b-262">Repeat the steps 4 through 11 for purchase order line 3.</span></span> <span data-ttu-id="56a3b-263">I steg 8, ange kvantiteten *1* för artikelnummer *A0001*.</span><span class="sxs-lookup"><span data-stu-id="56a3b-263">In step 8, specify a quantity of *1* for item number *A0001*.</span></span>

    <span data-ttu-id="56a3b-264">Nytt artikelinförselarbete (arbete 4) skapas för en annan plats än den plats som används för inköpsorderraderna 1 och 2.</span><span class="sxs-lookup"><span data-stu-id="56a3b-264">New put-away work (Work 4) is created for a different location than the location that is used for purchase order lines 1 and 2.</span></span> <span data-ttu-id="56a3b-265">Det här problemet beror på att platsprofilen inte tillåter blandade produkter, men den tillåter blandade dimensioner av samma produktmall.</span><span class="sxs-lookup"><span data-stu-id="56a3b-265">This behavior occurs because the location profile doesn't allow for mixed products, but it does allow for mixed dimensions of the same product master.</span></span>

1. <span data-ttu-id="56a3b-266">Välj Meny-knappen överst på sidan (kallas ibland hamburger eller knappen hamburger) och välj sedan **Avbryt** för att avsluta **Inleverans av inköpsorderrad**.</span><span class="sxs-lookup"><span data-stu-id="56a3b-266">Select the Menu button at the top of the page (sometimes referred to as the hamburger or the hamburger button), and then select **Cancel** to exit **PO Line receiving**.</span></span>

> [!TIP]
> <span data-ttu-id="56a3b-267">Du kan upprepa scenariot, men den här gången ändra **Storlek** - *Nej* under snabbfliken **tillåta blandning av produktdimensioner** på *BULK* **platsprofiler**, så att ingen av produkt dimensionerna kan blandas.</span><span class="sxs-lookup"><span data-stu-id="56a3b-267">You can repeat this scenario, but this time, set **Size** - *No* under the **Allow product dimension mixing** FastTab on the *BULK* **Location profiles**, so that none of the product dimensions can be mixed.</span></span> <span data-ttu-id="56a3b-268">I det här fallet, när du tar emot inköpsordern, kommer varje produktvariant att placeras på en ny plats.</span><span class="sxs-lookup"><span data-stu-id="56a3b-268">In this case, when you receive the purchase order, each product variant will be put to a new location.</span></span>