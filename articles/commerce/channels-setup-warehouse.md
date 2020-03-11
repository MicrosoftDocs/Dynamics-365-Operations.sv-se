---
title: Ställ in ett lagerställen
description: I det här avsnittet beskrivs hur du ställer in ett lagerställe som ska användas med en ny kanal i Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
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
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 9ba12876a8c8f841733d8ec49c33e900211c4ab4
ms.sourcegitcommit: 12b9d6f2dd24e52e46487748c848864909af6967
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/14/2020
ms.locfileid: "3057866"
---
# <a name="warehouse-set-up"></a><span data-ttu-id="82543-103">Inställning av lagerställe</span><span class="sxs-lookup"><span data-stu-id="82543-103">Warehouse set up</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="82543-104">I det här avsnittet beskrivs hur du ställer in ett lagerställe som ska användas med en ny kanal i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="82543-104">This topic describes how to set up a warehouse to be used with a new channel in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="82543-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="82543-105">Overview</span></span>

<span data-ttu-id="82543-106">Varje handelskanal kräver ett konfigurerat lagerställe för att det ska associeras med det.</span><span class="sxs-lookup"><span data-stu-id="82543-106">Each Commerce channel requires a configured warehouse to be associated with it.</span></span> <span data-ttu-id="82543-107">Följande procedurer ger den minsta konfiguration som krävs för att ställa in ett lager ställe för en handelskanal.</span><span class="sxs-lookup"><span data-stu-id="82543-107">The following procedures provide the minimum configuration required to set up a warehouse for a Commerce channel.</span></span> <span data-ttu-id="82543-108">Mer information om inställningar för lagerställen finns i [Lagerstyrning – översikt](https://docs.microsoft.com/en-us/dynamics365/supply-chain/warehousing/warehouse-management-overview).</span><span class="sxs-lookup"><span data-stu-id="82543-108">For more information regarding warehouse setup, please see the [Warehouse management overview](https://docs.microsoft.com/en-us/dynamics365/supply-chain/warehousing/warehouse-management-overview).</span></span>

## <a name="configure-a-warehouse-site"></a><span data-ttu-id="82543-109">Konfigurera en lagerställeplats</span><span class="sxs-lookup"><span data-stu-id="82543-109">Configure a warehouse site</span></span>

<span data-ttu-id="82543-110">Innan du ställer in ett lagerställe måste du konfigurera en lagerställeplats.</span><span class="sxs-lookup"><span data-stu-id="82543-110">Before setting up a warehouse, you need to configure a warehouse site.</span></span>

<span data-ttu-id="82543-111">Konfigurera en lagerställeplats enligt följande instruktioner.</span><span class="sxs-lookup"><span data-stu-id="82543-111">To configure a warehouse site, follow these steps.</span></span>

1. <span data-ttu-id="82543-112">I Navigeringsfönstret, gå till **Moduler \> Butik och handel \> Kanalsinställning \> Webbplatser**.</span><span class="sxs-lookup"><span data-stu-id="82543-112">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Sites**.</span></span>
1. <span data-ttu-id="82543-113">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="82543-113">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="82543-114">I fältet **Webbplatser** anger du ett värde.</span><span class="sxs-lookup"><span data-stu-id="82543-114">In the **Site** field, enter a value.</span></span>
1. <span data-ttu-id="82543-115">I fältet **Namn** anger du ett värde.</span><span class="sxs-lookup"><span data-stu-id="82543-115">In the **Name** field, enter a value.</span></span>
1. <span data-ttu-id="82543-116">I avsnittet **Allmänt** ange lämplig **Tidszon**.</span><span class="sxs-lookup"><span data-stu-id="82543-116">In the **General** section, set the appropriate **Time zone**.</span></span>
1. <span data-ttu-id="82543-117">I avsnittet **Adresser** ange en adress.</span><span class="sxs-lookup"><span data-stu-id="82543-117">In the **Addresses** section, enter an address.</span></span>
1. <span data-ttu-id="82543-118">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="82543-118">On the action pane, select **Save**.</span></span>

<span data-ttu-id="82543-119">I bilden nedan visas ett exempel på lagerställeplats.</span><span class="sxs-lookup"><span data-stu-id="82543-119">The following image shows an example warehouse site.</span></span>

![Exempel på lagerställeplats](media/warehouse-site.png)

## <a name="set-up-a-warehouse"></a><span data-ttu-id="82543-121">Ställ in ett lagerställen</span><span class="sxs-lookup"><span data-stu-id="82543-121">Set up a warehouse</span></span>

<span data-ttu-id="82543-122">Så här ställer du in ett lagerställe.</span><span class="sxs-lookup"><span data-stu-id="82543-122">To set up a warehouse, follow these steps.</span></span>

1. <span data-ttu-id="82543-123">I navigeringsfönstret, gå till **Moduler \> Butik och handel \> Kanalsinställning \> Lagerställen**.</span><span class="sxs-lookup"><span data-stu-id="82543-123">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Warehouses**.</span></span>
1. <span data-ttu-id="82543-124">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="82543-124">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="82543-125">I fältet **Lagerställe** ange ett värde.</span><span class="sxs-lookup"><span data-stu-id="82543-125">In the **Warehouse** field, enter a value.</span></span>  <span data-ttu-id="82543-126">Om detta är en 1:1-mappning till en butik bör du överväga att använda butiksnamnet eller namnet på ett regionalt distributionscenter.</span><span class="sxs-lookup"><span data-stu-id="82543-126">If this is a 1:1 mapping to a store, consider using the store name or the name of a regional distribution center.</span></span>
1. <span data-ttu-id="82543-127">I fältet **Namn** anger du ett värde.</span><span class="sxs-lookup"><span data-stu-id="82543-127">In the **Name** field, enter a value.</span></span>
1. <span data-ttu-id="82543-128">I listrutan **Plats** väljer du den lagerställeplats som du skapade tidigare.</span><span class="sxs-lookup"><span data-stu-id="82543-128">In the **Site** drop-down list, select the warehouse site created previously.</span></span>
1. <span data-ttu-id="82543-129">I fältet **Typ**, välj **Standard**.</span><span class="sxs-lookup"><span data-stu-id="82543-129">In the **Type** field, select **Default**.</span></span>
    - <span data-ttu-id="82543-130">Om du vill ställa in ett **Karantänlagerställe** måste du först följa stegen nedan för att skapa ett ytterligare lagerställe där **Typ** ställs in på **Karantän**.</span><span class="sxs-lookup"><span data-stu-id="82543-130">If you want to set a **Quarantine warehouse**, first you'll need to follow these steps to create an additional warehouse where the **Type** is set to **Quarantine**.</span></span>
    - <span data-ttu-id="82543-131">Om du vill ställa in ett **Transitlager** måste du först följa stegen nedan för att skapa ett ytterligare lagerställe där **Typ** ställs in på **Transit**.</span><span class="sxs-lookup"><span data-stu-id="82543-131">If you want to set a **Transit warehouse**, first you'll need to follow these steps to create an additional warehouse where the **Type** is set to **Transit**.</span></span>
1. <span data-ttu-id="82543-132">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="82543-132">On the action pane, select **Save**.</span></span>

## <a name="set-up-inventory-aisles"></a><span data-ttu-id="82543-133">Ställ in lagergångar</span><span class="sxs-lookup"><span data-stu-id="82543-133">Set up inventory aisles</span></span>

<span data-ttu-id="82543-134">Så här ställer du in lagergångar.</span><span class="sxs-lookup"><span data-stu-id="82543-134">To set up inventory aisles, follow these steps.</span></span>

1. <span data-ttu-id="82543-135">I navigeringsfönstret, gå till **Moduler \> Butik och handel \> Kanalsinställning \> Platsinställning \> Lagergångar**.</span><span class="sxs-lookup"><span data-stu-id="82543-135">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Location setup \> Inventory aisles**.</span></span>
1. <span data-ttu-id="82543-136">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="82543-136">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="82543-137">I listrutan **Lagerställe** väljer du det lagerställe som du skapade tidigare.</span><span class="sxs-lookup"><span data-stu-id="82543-137">In the **Warehouse** drop-down list, select the warehouse created previously.</span></span>
1. <span data-ttu-id="82543-138">I fältet **Gång** anger du ett namn (till exempel "Def").</span><span class="sxs-lookup"><span data-stu-id="82543-138">In the **Aisle** field, enter a name (for example, "Def").</span></span>
1. <span data-ttu-id="82543-139">I fältet **Namn** anger du ett namn (till exempel "Standardgång").</span><span class="sxs-lookup"><span data-stu-id="82543-139">In the **Name** field, enter a name (for example, "Default aisle").</span></span>
1. <span data-ttu-id="82543-140">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="82543-140">On the action pane, select **Save**.</span></span>

## <a name="set-up-warehouse-inventory-locations"></a><span data-ttu-id="82543-141">Konfigurera lagerplatser på lagerställen</span><span class="sxs-lookup"><span data-stu-id="82543-141">Set up warehouse inventory locations</span></span>

<span data-ttu-id="82543-142">Om du vill ställa in lagerplatser för lagerställen för standard, skadat och returnerat lager följer du dessa steg.</span><span class="sxs-lookup"><span data-stu-id="82543-142">To set up warehouse inventory locations for standard, damaged, and returned inventory, follow these steps.</span></span>

1. <span data-ttu-id="82543-143">I navigeringsfönstret, gå till **Moduler \> Butik och handel \> Kanalsinställning \> Lagerställen**.</span><span class="sxs-lookup"><span data-stu-id="82543-143">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Warehouses**.</span></span>
1. <span data-ttu-id="82543-144">Välj det lagerställe som du skapat tidigare.</span><span class="sxs-lookup"><span data-stu-id="82543-144">Select the warehouse you created previously.</span></span>
1. <span data-ttu-id="82543-145">Klicka på **Redigera** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="82543-145">On the action pane, select **Edit**.</span></span>
1. <span data-ttu-id="82543-146">I åtgärdsfönstret, välj **Lagerställe** och välj sedan **lagerplats**.</span><span class="sxs-lookup"><span data-stu-id="82543-146">On the action pane, select **Warehouse**, and then select **Inventory location**.</span></span>
1. <span data-ttu-id="82543-147">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="82543-147">On the action pane, select **New**.</span></span> <span data-ttu-id="82543-148">Listrutan **Lagerställe** bör som standard vara ditt nya lager.</span><span class="sxs-lookup"><span data-stu-id="82543-148">The **Warehouse** drop-down list should default to your new warehouse.</span></span>
    1. <span data-ttu-id="82543-149">I rutan **gång** ange namnet på gången du angav tidigare.</span><span class="sxs-lookup"><span data-stu-id="82543-149">In the **Aisle** box, enter the name of the aisle you specified earlier.</span></span> 
    1. <span data-ttu-id="82543-150">Ange **manuell uppdatering** till **Ja**</span><span class="sxs-lookup"><span data-stu-id="82543-150">Set **Manual update** to **Yes**</span></span>
    1. <span data-ttu-id="82543-151">I rutan **Plats** ange namnet på lagerstället.</span><span class="sxs-lookup"><span data-stu-id="82543-151">In the **Location** box, enter the name of the warehouse.</span></span>
    1. <span data-ttu-id="82543-152">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="82543-152">On the action pane, select **Save**.</span></span>
 1. <span data-ttu-id="82543-153">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="82543-153">On the action pane, select **New**.</span></span>  <span data-ttu-id="82543-154">Listrutan **Lagerställe** bör som standard vara ditt nya lager.</span><span class="sxs-lookup"><span data-stu-id="82543-154">The **Warehouse** drop-down list should default to your new warehouse.</span></span>
    1. <span data-ttu-id="82543-155">I rutan **gång** ange namnet på gången du angav tidigare.</span><span class="sxs-lookup"><span data-stu-id="82543-155">In the **Aisle** box, enter the name of the aisle you specified earlier.</span></span>  
    1. <span data-ttu-id="82543-156">Ange **manuell uppdatering** till **Ja**</span><span class="sxs-lookup"><span data-stu-id="82543-156">Set **Manual update** to **Yes**</span></span>
    1. <span data-ttu-id="82543-157">I rutan **Plats** ange "Skadad".</span><span class="sxs-lookup"><span data-stu-id="82543-157">In the **Location** box, enter "Damaged".</span></span>
    1. <span data-ttu-id="82543-158">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="82543-158">On the action pane, select **Save**.</span></span>
 1. <span data-ttu-id="82543-159">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="82543-159">On the action pane, select **New**.</span></span>  <span data-ttu-id="82543-160">Listrutan **Lagerställe** bör som standard vara ditt nya lager.</span><span class="sxs-lookup"><span data-stu-id="82543-160">The **Warehouse** drop-down list should default to your new warehouse.</span></span>
    1. <span data-ttu-id="82543-161">I rutan **gång** ange namnet på gången du angav tidigare.</span><span class="sxs-lookup"><span data-stu-id="82543-161">In the **Aisle** box, enter the name of the aisle you specified earlier.</span></span> 
    1. <span data-ttu-id="82543-162">Ange **manuell uppdatering** till **Ja**</span><span class="sxs-lookup"><span data-stu-id="82543-162">Set **Manual update** to **Yes**</span></span>
    1. <span data-ttu-id="82543-163">I rutan **Plats** ange "Returer".</span><span class="sxs-lookup"><span data-stu-id="82543-163">In the **Location** box, enter "Returns".</span></span>
    1. <span data-ttu-id="82543-164">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="82543-164">On the action pane, select **Save**.</span></span>
    
<span data-ttu-id="82543-165">Följande bild visar inställningar av San Francisco-lagerplats.</span><span class="sxs-lookup"><span data-stu-id="82543-165">The following image shows a San Francisco warehouse inventory location setup.</span></span>

![Exempel på inställningar av lagerplats](media/warehouse-inventory-locations.png)
    
## <a name="complete-warehouse-setup"></a><span data-ttu-id="82543-167">Slutförd inställning av lagerställe</span><span class="sxs-lookup"><span data-stu-id="82543-167">Complete warehouse setup</span></span>

<span data-ttu-id="82543-168">Om du vill slutföra inställning av lagerställe, följ dessa steg.</span><span class="sxs-lookup"><span data-stu-id="82543-168">To complete warehouse setup, follow these steps.</span></span>

1. <span data-ttu-id="82543-169">I navigeringsfönstret, gå till **Moduler \> Butik och handel \> Kanalsinställning \> Lagerställen**.</span><span class="sxs-lookup"><span data-stu-id="82543-169">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Warehouses**.</span></span>
1. <span data-ttu-id="82543-170">Välj det lagerställe som du skapat tidigare.</span><span class="sxs-lookup"><span data-stu-id="82543-170">Select the warehouse you previously created.</span></span>
1. <span data-ttu-id="82543-171">Klicka på **Redigera** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="82543-171">On the action pane, select **Edit**.</span></span>
1. <span data-ttu-id="82543-172">Under **Hantering av lager och lagerstyrning**:</span><span class="sxs-lookup"><span data-stu-id="82543-172">Under **Inventory and warehouse management**:</span></span>
    1. <span data-ttu-id="82543-173">Ange **Standardinleveransplats** till standardplatsen som skapades ovan.</span><span class="sxs-lookup"><span data-stu-id="82543-173">Set **Default receipt location** to the default location created above.</span></span>
    1. <span data-ttu-id="82543-174">Välj **Standardutleveransplats** till standardplatsen som skapades ovan.</span><span class="sxs-lookup"><span data-stu-id="82543-174">Select **Default issue location** to the default location created above.</span></span>
1. <span data-ttu-id="82543-175">Under avsnittet **adresser** ange en adress till lagerstället.</span><span class="sxs-lookup"><span data-stu-id="82543-175">Under the **Addresses** section, enter a warehouse address.</span></span>
1. <span data-ttu-id="82543-176">Under avsnittet **butik**:</span><span class="sxs-lookup"><span data-stu-id="82543-176">Under the **Retail** section:</span></span> 
    1. <span data-ttu-id="82543-177">I rutan **Standardreturplats** ange den returplats som skapades tidigare.</span><span class="sxs-lookup"><span data-stu-id="82543-177">In the **Default return location** box, enter the returns location created previously.</span></span>
    1. <span data-ttu-id="82543-178">Ange **Butik** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="82543-178">Set **Store** to **Yes**.</span></span>
    1. <span data-ttu-id="82543-179">Ange **Vikt** till **1,00**.</span><span class="sxs-lookup"><span data-stu-id="82543-179">Set **Weight** to **1.00**.</span></span> 
    1. <span data-ttu-id="82543-180">I rutan **Lagringsdimensioner** ange den standardplats som skapades tidigare.</span><span class="sxs-lookup"><span data-stu-id="82543-180">In the **Storage Dimensions** box, enter the default location created previously.</span></span>
1. <span data-ttu-id="82543-181">Under avsnittet **lagerställe** ange **Fysiskt negativt lager** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="82543-181">Under the **Warehouse** section, set **Physical negative inventory** to **Yes**.</span></span>
1. <span data-ttu-id="82543-182">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="82543-182">On the action pane, select **Save**.</span></span>

<span data-ttu-id="82543-183">Följande bild visar information om ett konfigurerat lagerställe.</span><span class="sxs-lookup"><span data-stu-id="82543-183">The following image shows details for a configured warehouse.</span></span>

![Exempel på konfigurerat lagerställe](media/warehouse-sample.png)

## <a name="additional-resources"></a><span data-ttu-id="82543-185">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="82543-185">Additional resources</span></span>

[<span data-ttu-id="82543-186">Lagerstyrning – översikt</span><span class="sxs-lookup"><span data-stu-id="82543-186">Warehouse management overview</span></span>](https://docs.microsoft.com/en-us/dynamics365/supply-chain/warehousing/warehouse-management-overview)

[<span data-ttu-id="82543-187">Översikt över kanaler</span><span class="sxs-lookup"><span data-stu-id="82543-187">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="82543-188">Förutsättningar för att ställa in kanaler</span><span class="sxs-lookup"><span data-stu-id="82543-188">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="82543-189">Ställa in en butikskanal</span><span class="sxs-lookup"><span data-stu-id="82543-189">Set up a retail channel</span></span>](channel-setup-retail.md)
    
[<span data-ttu-id="82543-190">Ställ in en onlinekanal</span><span class="sxs-lookup"><span data-stu-id="82543-190">Set up an online channel</span></span>](channel-setup-online.md)

[<span data-ttu-id="82543-191">Ställa in en kundtjänstkanal</span><span class="sxs-lookup"><span data-stu-id="82543-191">Set up a call center channel</span></span>](channel-setup-callcenter.md)





