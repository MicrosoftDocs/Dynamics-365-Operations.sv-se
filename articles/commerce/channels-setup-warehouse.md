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
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 67c0bb169bee8a7ea90edb4db7233111a8ee6e34
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4993663"
---
# <a name="warehouse-set-up"></a><span data-ttu-id="425a6-103">Inställning av lagerställe</span><span class="sxs-lookup"><span data-stu-id="425a6-103">Warehouse set up</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="425a6-104">I det här avsnittet beskrivs hur du ställer in ett lagerställe som ska användas med en ny kanal i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="425a6-104">This topic describes how to set up a warehouse to be used with a new channel in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="425a6-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="425a6-105">Overview</span></span>

<span data-ttu-id="425a6-106">Varje handelskanal kräver ett konfigurerat lagerställe för att det ska associeras med det.</span><span class="sxs-lookup"><span data-stu-id="425a6-106">Each Commerce channel requires a configured warehouse to be associated with it.</span></span> <span data-ttu-id="425a6-107">Följande procedurer ger den minsta konfiguration som krävs för att ställa in ett lager ställe för en handelskanal.</span><span class="sxs-lookup"><span data-stu-id="425a6-107">The following procedures provide the minimum configuration required to set up a warehouse for a Commerce channel.</span></span> <span data-ttu-id="425a6-108">Mer information om inställningar för lagerställen finns i [Lagerstyrning – översikt](../supply-chain/warehousing/warehouse-management-overview.md?toc=/dynamics365/commerce/toc.json).</span><span class="sxs-lookup"><span data-stu-id="425a6-108">For more information regarding warehouse setup, please see the [Warehouse management overview](../supply-chain/warehousing/warehouse-management-overview.md?toc=/dynamics365/commerce/toc.json).</span></span>

## <a name="configure-a-warehouse-site"></a><span data-ttu-id="425a6-109">Konfigurera en lagerställeplats</span><span class="sxs-lookup"><span data-stu-id="425a6-109">Configure a warehouse site</span></span>

<span data-ttu-id="425a6-110">Innan du ställer in ett lagerställe måste du konfigurera en lagerställeplats.</span><span class="sxs-lookup"><span data-stu-id="425a6-110">Before setting up a warehouse, you need to configure a warehouse site.</span></span>

<span data-ttu-id="425a6-111">Konfigurera en lagerställeplats enligt följande instruktioner.</span><span class="sxs-lookup"><span data-stu-id="425a6-111">To configure a warehouse site, follow these steps.</span></span>

1. <span data-ttu-id="425a6-112">I Navigeringsfönstret, gå till **Moduler \> Butik och handel \> Kanalsinställning \> Webbplatser**.</span><span class="sxs-lookup"><span data-stu-id="425a6-112">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Sites**.</span></span>
1. <span data-ttu-id="425a6-113">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="425a6-113">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="425a6-114">I fältet **Webbplatser** anger du ett värde.</span><span class="sxs-lookup"><span data-stu-id="425a6-114">In the **Site** field, enter a value.</span></span>
1. <span data-ttu-id="425a6-115">I fältet **Namn** anger du ett värde.</span><span class="sxs-lookup"><span data-stu-id="425a6-115">In the **Name** field, enter a value.</span></span>
1. <span data-ttu-id="425a6-116">I avsnittet **Allmänt** ange lämplig **Tidszon**.</span><span class="sxs-lookup"><span data-stu-id="425a6-116">In the **General** section, set the appropriate **Time zone**.</span></span>
1. <span data-ttu-id="425a6-117">I avsnittet **Adresser** ange en adress.</span><span class="sxs-lookup"><span data-stu-id="425a6-117">In the **Addresses** section, enter an address.</span></span>
1. <span data-ttu-id="425a6-118">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="425a6-118">On the action pane, select **Save**.</span></span>

<span data-ttu-id="425a6-119">I bilden nedan visas ett exempel på lagerställeplats.</span><span class="sxs-lookup"><span data-stu-id="425a6-119">The following image shows an example warehouse site.</span></span>

![Exempel på lagerställeplats](media/warehouse-site.png)

## <a name="set-up-a-warehouse"></a><span data-ttu-id="425a6-121">Ställ in ett lagerställen</span><span class="sxs-lookup"><span data-stu-id="425a6-121">Set up a warehouse</span></span>

<span data-ttu-id="425a6-122">Så här ställer du in ett lagerställe.</span><span class="sxs-lookup"><span data-stu-id="425a6-122">To set up a warehouse, follow these steps.</span></span>

1. <span data-ttu-id="425a6-123">I navigeringsfönstret, gå till **Moduler \> Butik och handel \> Kanalsinställning \> Lagerställen**.</span><span class="sxs-lookup"><span data-stu-id="425a6-123">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Warehouses**.</span></span>
1. <span data-ttu-id="425a6-124">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="425a6-124">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="425a6-125">I fältet **Lagerställe** ange ett värde.</span><span class="sxs-lookup"><span data-stu-id="425a6-125">In the **Warehouse** field, enter a value.</span></span>  <span data-ttu-id="425a6-126">Om detta är en 1:1-mappning till en butik bör du överväga att använda butiksnamnet eller namnet på ett regionalt distributionscenter.</span><span class="sxs-lookup"><span data-stu-id="425a6-126">If this is a 1:1 mapping to a store, consider using the store name or the name of a regional distribution center.</span></span>
1. <span data-ttu-id="425a6-127">I fältet **Namn** anger du ett värde.</span><span class="sxs-lookup"><span data-stu-id="425a6-127">In the **Name** field, enter a value.</span></span>
1. <span data-ttu-id="425a6-128">I listrutan **Plats** väljer du den lagerställeplats som du skapade tidigare.</span><span class="sxs-lookup"><span data-stu-id="425a6-128">In the **Site** drop-down list, select the warehouse site created previously.</span></span>
1. <span data-ttu-id="425a6-129">I fältet **Typ**, välj **Standard**.</span><span class="sxs-lookup"><span data-stu-id="425a6-129">In the **Type** field, select **Default**.</span></span>
    - <span data-ttu-id="425a6-130">Om du vill ställa in ett **Karantänlagerställe** måste du först följa stegen nedan för att skapa ett ytterligare lagerställe där **Typ** ställs in på **Karantän**.</span><span class="sxs-lookup"><span data-stu-id="425a6-130">If you want to set a **Quarantine warehouse**, first you'll need to follow these steps to create an additional warehouse where the **Type** is set to **Quarantine**.</span></span>
    - <span data-ttu-id="425a6-131">Om du vill ställa in ett **Transitlager** måste du först följa stegen nedan för att skapa ett ytterligare lagerställe där **Typ** ställs in på **Transit**.</span><span class="sxs-lookup"><span data-stu-id="425a6-131">If you want to set a **Transit warehouse**, first you'll need to follow these steps to create an additional warehouse where the **Type** is set to **Transit**.</span></span>
1. <span data-ttu-id="425a6-132">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="425a6-132">On the action pane, select **Save**.</span></span>

## <a name="set-up-inventory-aisles"></a><span data-ttu-id="425a6-133">Ställ in lagergångar</span><span class="sxs-lookup"><span data-stu-id="425a6-133">Set up inventory aisles</span></span>

<span data-ttu-id="425a6-134">Så här ställer du in lagergångar.</span><span class="sxs-lookup"><span data-stu-id="425a6-134">To set up inventory aisles, follow these steps.</span></span>

1. <span data-ttu-id="425a6-135">I navigeringsfönstret, gå till **Moduler \> Butik och handel \> Kanalsinställning \> Platsinställning \> Lagergångar**.</span><span class="sxs-lookup"><span data-stu-id="425a6-135">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Location setup \> Inventory aisles**.</span></span>
1. <span data-ttu-id="425a6-136">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="425a6-136">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="425a6-137">I listrutan **Lagerställe** väljer du det lagerställe som du skapade tidigare.</span><span class="sxs-lookup"><span data-stu-id="425a6-137">In the **Warehouse** drop-down list, select the warehouse created previously.</span></span>
1. <span data-ttu-id="425a6-138">I fältet **Gång** anger du ett namn (till exempel "Def").</span><span class="sxs-lookup"><span data-stu-id="425a6-138">In the **Aisle** field, enter a name (for example, "Def").</span></span>
1. <span data-ttu-id="425a6-139">I fältet **Namn** anger du ett namn (till exempel "Standardgång").</span><span class="sxs-lookup"><span data-stu-id="425a6-139">In the **Name** field, enter a name (for example, "Default aisle").</span></span>
1. <span data-ttu-id="425a6-140">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="425a6-140">On the action pane, select **Save**.</span></span>

## <a name="set-up-warehouse-inventory-locations"></a><span data-ttu-id="425a6-141">Konfigurera lagerplatser på lagerställen</span><span class="sxs-lookup"><span data-stu-id="425a6-141">Set up warehouse inventory locations</span></span>

<span data-ttu-id="425a6-142">Om du vill ställa in lagerplatser för lagerställen för standard, skadat och returnerat lager följer du dessa steg.</span><span class="sxs-lookup"><span data-stu-id="425a6-142">To set up warehouse inventory locations for standard, damaged, and returned inventory, follow these steps.</span></span>

1. <span data-ttu-id="425a6-143">I navigeringsfönstret, gå till **Moduler \> Butik och handel \> Kanalsinställning \> Lagerställen**.</span><span class="sxs-lookup"><span data-stu-id="425a6-143">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Warehouses**.</span></span>
1. <span data-ttu-id="425a6-144">Välj det lagerställe som du skapat tidigare.</span><span class="sxs-lookup"><span data-stu-id="425a6-144">Select the warehouse you created previously.</span></span>
1. <span data-ttu-id="425a6-145">Klicka på **Redigera** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="425a6-145">On the action pane, select **Edit**.</span></span>
1. <span data-ttu-id="425a6-146">I åtgärdsfönstret, välj **Lagerställe** och välj sedan **lagerplats**.</span><span class="sxs-lookup"><span data-stu-id="425a6-146">On the action pane, select **Warehouse**, and then select **Inventory location**.</span></span>
1. <span data-ttu-id="425a6-147">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="425a6-147">On the action pane, select **New**.</span></span> <span data-ttu-id="425a6-148">Listrutan **Lagerställe** bör som standard vara ditt nya lager.</span><span class="sxs-lookup"><span data-stu-id="425a6-148">The **Warehouse** drop-down list should default to your new warehouse.</span></span>
    1. <span data-ttu-id="425a6-149">I rutan **gång** ange namnet på gången du angav tidigare.</span><span class="sxs-lookup"><span data-stu-id="425a6-149">In the **Aisle** box, enter the name of the aisle you specified earlier.</span></span> 
    1. <span data-ttu-id="425a6-150">Ange **manuell uppdatering** till **Ja**</span><span class="sxs-lookup"><span data-stu-id="425a6-150">Set **Manual update** to **Yes**</span></span>
    1. <span data-ttu-id="425a6-151">I rutan **Plats** ange namnet på lagerstället.</span><span class="sxs-lookup"><span data-stu-id="425a6-151">In the **Location** box, enter the name of the warehouse.</span></span>
    1. <span data-ttu-id="425a6-152">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="425a6-152">On the action pane, select **Save**.</span></span>
 1. <span data-ttu-id="425a6-153">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="425a6-153">On the action pane, select **New**.</span></span>  <span data-ttu-id="425a6-154">Listrutan **Lagerställe** bör som standard vara ditt nya lager.</span><span class="sxs-lookup"><span data-stu-id="425a6-154">The **Warehouse** drop-down list should default to your new warehouse.</span></span>
    1. <span data-ttu-id="425a6-155">I rutan **gång** ange namnet på gången du angav tidigare.</span><span class="sxs-lookup"><span data-stu-id="425a6-155">In the **Aisle** box, enter the name of the aisle you specified earlier.</span></span>  
    1. <span data-ttu-id="425a6-156">Ange **manuell uppdatering** till **Ja**</span><span class="sxs-lookup"><span data-stu-id="425a6-156">Set **Manual update** to **Yes**</span></span>
    1. <span data-ttu-id="425a6-157">I rutan **Plats** ange "Skadad".</span><span class="sxs-lookup"><span data-stu-id="425a6-157">In the **Location** box, enter "Damaged".</span></span>
    1. <span data-ttu-id="425a6-158">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="425a6-158">On the action pane, select **Save**.</span></span>
 1. <span data-ttu-id="425a6-159">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="425a6-159">On the action pane, select **New**.</span></span>  <span data-ttu-id="425a6-160">Listrutan **Lagerställe** bör som standard vara ditt nya lager.</span><span class="sxs-lookup"><span data-stu-id="425a6-160">The **Warehouse** drop-down list should default to your new warehouse.</span></span>
    1. <span data-ttu-id="425a6-161">I rutan **gång** ange namnet på gången du angav tidigare.</span><span class="sxs-lookup"><span data-stu-id="425a6-161">In the **Aisle** box, enter the name of the aisle you specified earlier.</span></span> 
    1. <span data-ttu-id="425a6-162">Ange **manuell uppdatering** till **Ja**</span><span class="sxs-lookup"><span data-stu-id="425a6-162">Set **Manual update** to **Yes**</span></span>
    1. <span data-ttu-id="425a6-163">I rutan **Plats** ange "Returer".</span><span class="sxs-lookup"><span data-stu-id="425a6-163">In the **Location** box, enter "Returns".</span></span>
    1. <span data-ttu-id="425a6-164">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="425a6-164">On the action pane, select **Save**.</span></span>
    
<span data-ttu-id="425a6-165">Följande bild visar inställningar av San Francisco-lagerplats.</span><span class="sxs-lookup"><span data-stu-id="425a6-165">The following image shows a San Francisco warehouse inventory location setup.</span></span>

![Exempel på inställningar av lagerplats](media/warehouse-inventory-locations.png)
    
## <a name="complete-warehouse-setup"></a><span data-ttu-id="425a6-167">Slutförd inställning av lagerställe</span><span class="sxs-lookup"><span data-stu-id="425a6-167">Complete warehouse setup</span></span>

<span data-ttu-id="425a6-168">Om du vill slutföra inställning av lagerställe, följ dessa steg.</span><span class="sxs-lookup"><span data-stu-id="425a6-168">To complete warehouse setup, follow these steps.</span></span>

1. <span data-ttu-id="425a6-169">I navigeringsfönstret, gå till **Moduler \> Butik och handel \> Kanalsinställning \> Lagerställen**.</span><span class="sxs-lookup"><span data-stu-id="425a6-169">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Warehouses**.</span></span>
1. <span data-ttu-id="425a6-170">Välj det lagerställe som du skapat tidigare.</span><span class="sxs-lookup"><span data-stu-id="425a6-170">Select the warehouse you previously created.</span></span>
1. <span data-ttu-id="425a6-171">Klicka på **Redigera** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="425a6-171">On the action pane, select **Edit**.</span></span>
1. <span data-ttu-id="425a6-172">Under **Hantering av lager och lagerstyrning**:</span><span class="sxs-lookup"><span data-stu-id="425a6-172">Under **Inventory and warehouse management**:</span></span>
    1. <span data-ttu-id="425a6-173">Ange **Standardinleveransplats** till standardplatsen som skapades ovan.</span><span class="sxs-lookup"><span data-stu-id="425a6-173">Set **Default receipt location** to the default location created above.</span></span>
    1. <span data-ttu-id="425a6-174">Välj **Standardutleveransplats** till standardplatsen som skapades ovan.</span><span class="sxs-lookup"><span data-stu-id="425a6-174">Select **Default issue location** to the default location created above.</span></span>
1. <span data-ttu-id="425a6-175">Under avsnittet **adresser** ange en adress till lagerstället.</span><span class="sxs-lookup"><span data-stu-id="425a6-175">Under the **Addresses** section, enter a warehouse address.</span></span>
1. <span data-ttu-id="425a6-176">Under avsnittet **butik**:</span><span class="sxs-lookup"><span data-stu-id="425a6-176">Under the **Retail** section:</span></span> 
    1. <span data-ttu-id="425a6-177">I rutan **Standardreturplats** ange den returplats som skapades tidigare.</span><span class="sxs-lookup"><span data-stu-id="425a6-177">In the **Default return location** box, enter the returns location created previously.</span></span>
    1. <span data-ttu-id="425a6-178">Ange **Butik** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="425a6-178">Set **Store** to **Yes**.</span></span>
    1. <span data-ttu-id="425a6-179">Ange **Vikt** till **1,00**.</span><span class="sxs-lookup"><span data-stu-id="425a6-179">Set **Weight** to **1.00**.</span></span> 
    1. <span data-ttu-id="425a6-180">I rutan **Lagringsdimensioner** ange den standardplats som skapades tidigare.</span><span class="sxs-lookup"><span data-stu-id="425a6-180">In the **Storage Dimensions** box, enter the default location created previously.</span></span>
1. <span data-ttu-id="425a6-181">Under avsnittet **lagerställe** ange **Fysiskt negativt lager** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="425a6-181">Under the **Warehouse** section, set **Physical negative inventory** to **Yes**.</span></span>
1. <span data-ttu-id="425a6-182">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="425a6-182">On the action pane, select **Save**.</span></span>

<span data-ttu-id="425a6-183">Följande bild visar information om ett konfigurerat lagerställe.</span><span class="sxs-lookup"><span data-stu-id="425a6-183">The following image shows details for a configured warehouse.</span></span>

![Exempel på konfigurerat lagerställe](media/warehouse-sample.png)

## <a name="additional-resources"></a><span data-ttu-id="425a6-185">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="425a6-185">Additional resources</span></span>

[<span data-ttu-id="425a6-186">Lagerstyrning – översikt</span><span class="sxs-lookup"><span data-stu-id="425a6-186">Warehouse management overview</span></span>](../supply-chain/warehousing/warehouse-management-overview.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="425a6-187">Översikt över kanaler</span><span class="sxs-lookup"><span data-stu-id="425a6-187">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="425a6-188">Förutsättningar för att ställa in kanaler</span><span class="sxs-lookup"><span data-stu-id="425a6-188">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="425a6-189">Ställa in en butikskanal</span><span class="sxs-lookup"><span data-stu-id="425a6-189">Set up a retail channel</span></span>](channel-setup-retail.md)
    
[<span data-ttu-id="425a6-190">Ställ in en onlinekanal</span><span class="sxs-lookup"><span data-stu-id="425a6-190">Set up an online channel</span></span>](channel-setup-online.md)

[<span data-ttu-id="425a6-191">Ställa in en kundtjänstkanal</span><span class="sxs-lookup"><span data-stu-id="425a6-191">Set up a call center channel</span></span>](channel-setup-callcenter.md)





