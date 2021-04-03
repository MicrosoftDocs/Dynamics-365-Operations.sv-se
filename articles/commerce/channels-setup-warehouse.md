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
ms.openlocfilehash: 772c7584549b30a34e371a7911131edc01214ed8
ms.sourcegitcommit: c88b54ba13a4dfe39b844ffaced4dc435560c47d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/19/2021
ms.locfileid: "5477644"
---
# <a name="warehouse-set-up"></a><span data-ttu-id="78d59-103">Inställning av lagerställe</span><span class="sxs-lookup"><span data-stu-id="78d59-103">Warehouse set up</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="78d59-104">I det här avsnittet beskrivs hur du ställer in ett lagerställe som ska användas med en ny kanal i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="78d59-104">This topic describes how to set up a warehouse to be used with a new channel in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="78d59-105">Varje handelskanal kräver ett konfigurerat lagerställe för att det ska associeras med det.</span><span class="sxs-lookup"><span data-stu-id="78d59-105">Each Commerce channel requires a configured warehouse to be associated with it.</span></span> <span data-ttu-id="78d59-106">Följande procedurer ger den minsta konfiguration som krävs för att ställa in ett lager ställe för en handelskanal.</span><span class="sxs-lookup"><span data-stu-id="78d59-106">The following procedures provide the minimum configuration required to set up a warehouse for a Commerce channel.</span></span> <span data-ttu-id="78d59-107">Mer information om inställningar för lagerställen finns i [Lagerstyrning – översikt](../supply-chain/warehousing/warehouse-management-overview.md?toc=/dynamics365/commerce/toc.json).</span><span class="sxs-lookup"><span data-stu-id="78d59-107">For more information regarding warehouse setup, please see the [Warehouse management overview](../supply-chain/warehousing/warehouse-management-overview.md?toc=/dynamics365/commerce/toc.json).</span></span>

## <a name="configure-a-warehouse-site"></a><span data-ttu-id="78d59-108">Konfigurera en lagerställeplats</span><span class="sxs-lookup"><span data-stu-id="78d59-108">Configure a warehouse site</span></span>

<span data-ttu-id="78d59-109">Innan du ställer in ett lagerställe måste du konfigurera en lagerställeplats.</span><span class="sxs-lookup"><span data-stu-id="78d59-109">Before setting up a warehouse, you need to configure a warehouse site.</span></span>

<span data-ttu-id="78d59-110">Konfigurera en lagerställeplats enligt följande instruktioner.</span><span class="sxs-lookup"><span data-stu-id="78d59-110">To configure a warehouse site, follow these steps.</span></span>

1. <span data-ttu-id="78d59-111">I Navigeringsfönstret, gå till **Moduler \> Butik och handel \> Kanalsinställning \> Webbplatser**.</span><span class="sxs-lookup"><span data-stu-id="78d59-111">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Sites**.</span></span>
1. <span data-ttu-id="78d59-112">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="78d59-112">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="78d59-113">I fältet **Webbplatser** anger du ett värde.</span><span class="sxs-lookup"><span data-stu-id="78d59-113">In the **Site** field, enter a value.</span></span>
1. <span data-ttu-id="78d59-114">I fältet **Namn** anger du ett värde.</span><span class="sxs-lookup"><span data-stu-id="78d59-114">In the **Name** field, enter a value.</span></span>
1. <span data-ttu-id="78d59-115">I avsnittet **Allmänt** ange lämplig **Tidszon**.</span><span class="sxs-lookup"><span data-stu-id="78d59-115">In the **General** section, set the appropriate **Time zone**.</span></span>
1. <span data-ttu-id="78d59-116">I avsnittet **Adresser** ange en adress.</span><span class="sxs-lookup"><span data-stu-id="78d59-116">In the **Addresses** section, enter an address.</span></span>
1. <span data-ttu-id="78d59-117">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="78d59-117">On the action pane, select **Save**.</span></span>

<span data-ttu-id="78d59-118">I bilden nedan visas ett exempel på lagerställeplats.</span><span class="sxs-lookup"><span data-stu-id="78d59-118">The following image shows an example warehouse site.</span></span>

![Exempel på lagerställeplats](media/warehouse-site.png)

## <a name="set-up-a-warehouse"></a><span data-ttu-id="78d59-120">Ställ in ett lagerställen</span><span class="sxs-lookup"><span data-stu-id="78d59-120">Set up a warehouse</span></span>

<span data-ttu-id="78d59-121">Så här ställer du in ett lagerställe.</span><span class="sxs-lookup"><span data-stu-id="78d59-121">To set up a warehouse, follow these steps.</span></span>

1. <span data-ttu-id="78d59-122">I navigeringsfönstret, gå till **Moduler \> Butik och handel \> Kanalsinställning \> Lagerställen**.</span><span class="sxs-lookup"><span data-stu-id="78d59-122">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Warehouses**.</span></span>
1. <span data-ttu-id="78d59-123">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="78d59-123">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="78d59-124">I fältet **Lagerställe** ange ett värde.</span><span class="sxs-lookup"><span data-stu-id="78d59-124">In the **Warehouse** field, enter a value.</span></span>  <span data-ttu-id="78d59-125">Om detta är en 1:1-mappning till en butik bör du överväga att använda butiksnamnet eller namnet på ett regionalt distributionscenter.</span><span class="sxs-lookup"><span data-stu-id="78d59-125">If this is a 1:1 mapping to a store, consider using the store name or the name of a regional distribution center.</span></span>
1. <span data-ttu-id="78d59-126">I fältet **Namn** anger du ett värde.</span><span class="sxs-lookup"><span data-stu-id="78d59-126">In the **Name** field, enter a value.</span></span>
1. <span data-ttu-id="78d59-127">I listrutan **Plats** väljer du den lagerställeplats som du skapade tidigare.</span><span class="sxs-lookup"><span data-stu-id="78d59-127">In the **Site** drop-down list, select the warehouse site created previously.</span></span>
1. <span data-ttu-id="78d59-128">I fältet **Typ**, välj **Standard**.</span><span class="sxs-lookup"><span data-stu-id="78d59-128">In the **Type** field, select **Default**.</span></span>
    - <span data-ttu-id="78d59-129">Om du vill ställa in ett **Karantänlagerställe** måste du först följa stegen nedan för att skapa ett ytterligare lagerställe där **Typ** ställs in på **Karantän**.</span><span class="sxs-lookup"><span data-stu-id="78d59-129">If you want to set a **Quarantine warehouse**, first you'll need to follow these steps to create an additional warehouse where the **Type** is set to **Quarantine**.</span></span>
    - <span data-ttu-id="78d59-130">Om du vill ställa in ett **Transitlager** måste du först följa stegen nedan för att skapa ett ytterligare lagerställe där **Typ** ställs in på **Transit**.</span><span class="sxs-lookup"><span data-stu-id="78d59-130">If you want to set a **Transit warehouse**, first you'll need to follow these steps to create an additional warehouse where the **Type** is set to **Transit**.</span></span>
1. <span data-ttu-id="78d59-131">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="78d59-131">On the action pane, select **Save**.</span></span>

## <a name="set-up-inventory-aisles"></a><span data-ttu-id="78d59-132">Ställ in lagergångar</span><span class="sxs-lookup"><span data-stu-id="78d59-132">Set up inventory aisles</span></span>

<span data-ttu-id="78d59-133">Så här ställer du in lagergångar.</span><span class="sxs-lookup"><span data-stu-id="78d59-133">To set up inventory aisles, follow these steps.</span></span>

1. <span data-ttu-id="78d59-134">I navigeringsfönstret, gå till **Moduler \> Butik och handel \> Kanalsinställning \> Platsinställning \> Lagergångar**.</span><span class="sxs-lookup"><span data-stu-id="78d59-134">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Location setup \> Inventory aisles**.</span></span>
1. <span data-ttu-id="78d59-135">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="78d59-135">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="78d59-136">I listrutan **Lagerställe** väljer du det lagerställe som du skapade tidigare.</span><span class="sxs-lookup"><span data-stu-id="78d59-136">In the **Warehouse** drop-down list, select the warehouse created previously.</span></span>
1. <span data-ttu-id="78d59-137">I fältet **Gång** anger du ett namn (till exempel "Def").</span><span class="sxs-lookup"><span data-stu-id="78d59-137">In the **Aisle** field, enter a name (for example, "Def").</span></span>
1. <span data-ttu-id="78d59-138">I fältet **Namn** anger du ett namn (till exempel "Standardgång").</span><span class="sxs-lookup"><span data-stu-id="78d59-138">In the **Name** field, enter a name (for example, "Default aisle").</span></span>
1. <span data-ttu-id="78d59-139">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="78d59-139">On the action pane, select **Save**.</span></span>

## <a name="set-up-warehouse-inventory-locations"></a><span data-ttu-id="78d59-140">Konfigurera lagerplatser på lagerställen</span><span class="sxs-lookup"><span data-stu-id="78d59-140">Set up warehouse inventory locations</span></span>

<span data-ttu-id="78d59-141">Om du vill ställa in lagerplatser för lagerställen för standard, skadat och returnerat lager följer du dessa steg.</span><span class="sxs-lookup"><span data-stu-id="78d59-141">To set up warehouse inventory locations for standard, damaged, and returned inventory, follow these steps.</span></span>

1. <span data-ttu-id="78d59-142">I navigeringsfönstret, gå till **Moduler \> Butik och handel \> Kanalsinställning \> Lagerställen**.</span><span class="sxs-lookup"><span data-stu-id="78d59-142">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Warehouses**.</span></span>
1. <span data-ttu-id="78d59-143">Välj det lagerställe som du skapat tidigare.</span><span class="sxs-lookup"><span data-stu-id="78d59-143">Select the warehouse you created previously.</span></span>
1. <span data-ttu-id="78d59-144">Klicka på **Redigera** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="78d59-144">On the action pane, select **Edit**.</span></span>
1. <span data-ttu-id="78d59-145">I åtgärdsfönstret, välj **Lagerställe** och välj sedan **lagerplats**.</span><span class="sxs-lookup"><span data-stu-id="78d59-145">On the action pane, select **Warehouse**, and then select **Inventory location**.</span></span>
1. <span data-ttu-id="78d59-146">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="78d59-146">On the action pane, select **New**.</span></span> <span data-ttu-id="78d59-147">Listrutan **Lagerställe** bör som standard vara ditt nya lager.</span><span class="sxs-lookup"><span data-stu-id="78d59-147">The **Warehouse** drop-down list should default to your new warehouse.</span></span>
    1. <span data-ttu-id="78d59-148">I rutan **gång** ange namnet på gången du angav tidigare.</span><span class="sxs-lookup"><span data-stu-id="78d59-148">In the **Aisle** box, enter the name of the aisle you specified earlier.</span></span> 
    1. <span data-ttu-id="78d59-149">Ange **manuell uppdatering** till **Ja**</span><span class="sxs-lookup"><span data-stu-id="78d59-149">Set **Manual update** to **Yes**</span></span>
    1. <span data-ttu-id="78d59-150">I rutan **Plats** ange namnet på lagerstället.</span><span class="sxs-lookup"><span data-stu-id="78d59-150">In the **Location** box, enter the name of the warehouse.</span></span>
    1. <span data-ttu-id="78d59-151">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="78d59-151">On the action pane, select **Save**.</span></span>
 1. <span data-ttu-id="78d59-152">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="78d59-152">On the action pane, select **New**.</span></span>  <span data-ttu-id="78d59-153">Listrutan **Lagerställe** bör som standard vara ditt nya lager.</span><span class="sxs-lookup"><span data-stu-id="78d59-153">The **Warehouse** drop-down list should default to your new warehouse.</span></span>
    1. <span data-ttu-id="78d59-154">I rutan **gång** ange namnet på gången du angav tidigare.</span><span class="sxs-lookup"><span data-stu-id="78d59-154">In the **Aisle** box, enter the name of the aisle you specified earlier.</span></span>  
    1. <span data-ttu-id="78d59-155">Ange **manuell uppdatering** till **Ja**</span><span class="sxs-lookup"><span data-stu-id="78d59-155">Set **Manual update** to **Yes**</span></span>
    1. <span data-ttu-id="78d59-156">I rutan **Plats** ange "Skadad".</span><span class="sxs-lookup"><span data-stu-id="78d59-156">In the **Location** box, enter "Damaged".</span></span>
    1. <span data-ttu-id="78d59-157">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="78d59-157">On the action pane, select **Save**.</span></span>
 1. <span data-ttu-id="78d59-158">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="78d59-158">On the action pane, select **New**.</span></span>  <span data-ttu-id="78d59-159">Listrutan **Lagerställe** bör som standard vara ditt nya lager.</span><span class="sxs-lookup"><span data-stu-id="78d59-159">The **Warehouse** drop-down list should default to your new warehouse.</span></span>
    1. <span data-ttu-id="78d59-160">I rutan **gång** ange namnet på gången du angav tidigare.</span><span class="sxs-lookup"><span data-stu-id="78d59-160">In the **Aisle** box, enter the name of the aisle you specified earlier.</span></span> 
    1. <span data-ttu-id="78d59-161">Ange **manuell uppdatering** till **Ja**</span><span class="sxs-lookup"><span data-stu-id="78d59-161">Set **Manual update** to **Yes**</span></span>
    1. <span data-ttu-id="78d59-162">I rutan **Plats** ange "Returer".</span><span class="sxs-lookup"><span data-stu-id="78d59-162">In the **Location** box, enter "Returns".</span></span>
    1. <span data-ttu-id="78d59-163">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="78d59-163">On the action pane, select **Save**.</span></span>
    
<span data-ttu-id="78d59-164">Följande bild visar inställningar av San Francisco-lagerplats.</span><span class="sxs-lookup"><span data-stu-id="78d59-164">The following image shows a San Francisco warehouse inventory location setup.</span></span>

![Exempel på inställningar av lagerplats](media/warehouse-inventory-locations.png)
    
## <a name="complete-warehouse-setup"></a><span data-ttu-id="78d59-166">Slutförd inställning av lagerställe</span><span class="sxs-lookup"><span data-stu-id="78d59-166">Complete warehouse setup</span></span>

<span data-ttu-id="78d59-167">Om du vill slutföra inställning av lagerställe, följ dessa steg.</span><span class="sxs-lookup"><span data-stu-id="78d59-167">To complete warehouse setup, follow these steps.</span></span>

1. <span data-ttu-id="78d59-168">I navigeringsfönstret, gå till **Moduler \> Butik och handel \> Kanalsinställning \> Lagerställen**.</span><span class="sxs-lookup"><span data-stu-id="78d59-168">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Warehouses**.</span></span>
1. <span data-ttu-id="78d59-169">Välj det lagerställe som du skapat tidigare.</span><span class="sxs-lookup"><span data-stu-id="78d59-169">Select the warehouse you previously created.</span></span>
1. <span data-ttu-id="78d59-170">Klicka på **Redigera** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="78d59-170">On the action pane, select **Edit**.</span></span>
1. <span data-ttu-id="78d59-171">Under **Hantering av lager och lagerstyrning**:</span><span class="sxs-lookup"><span data-stu-id="78d59-171">Under **Inventory and warehouse management**:</span></span>
    1. <span data-ttu-id="78d59-172">Ange **Standardinleveransplats** till standardplatsen som skapades ovan.</span><span class="sxs-lookup"><span data-stu-id="78d59-172">Set **Default receipt location** to the default location created above.</span></span>
    1. <span data-ttu-id="78d59-173">Välj **Standardutleveransplats** till standardplatsen som skapades ovan.</span><span class="sxs-lookup"><span data-stu-id="78d59-173">Select **Default issue location** to the default location created above.</span></span>
1. <span data-ttu-id="78d59-174">Under avsnittet **adresser** ange en adress till lagerstället.</span><span class="sxs-lookup"><span data-stu-id="78d59-174">Under the **Addresses** section, enter a warehouse address.</span></span>
1. <span data-ttu-id="78d59-175">Under avsnittet **butik**:</span><span class="sxs-lookup"><span data-stu-id="78d59-175">Under the **Retail** section:</span></span> 
    1. <span data-ttu-id="78d59-176">I rutan **Standardreturplats** ange den returplats som skapades tidigare.</span><span class="sxs-lookup"><span data-stu-id="78d59-176">In the **Default return location** box, enter the returns location created previously.</span></span>
    1. <span data-ttu-id="78d59-177">Ange **Butik** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="78d59-177">Set **Store** to **Yes**.</span></span>
    1. <span data-ttu-id="78d59-178">Ange **Vikt** till **1,00**.</span><span class="sxs-lookup"><span data-stu-id="78d59-178">Set **Weight** to **1.00**.</span></span> 
    1. <span data-ttu-id="78d59-179">I rutan **Lagringsdimensioner** ange den standardplats som skapades tidigare.</span><span class="sxs-lookup"><span data-stu-id="78d59-179">In the **Storage Dimensions** box, enter the default location created previously.</span></span>
1. <span data-ttu-id="78d59-180">Under avsnittet **lagerställe** ange **Fysiskt negativt lager** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="78d59-180">Under the **Warehouse** section, set **Physical negative inventory** to **Yes**.</span></span>
1. <span data-ttu-id="78d59-181">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="78d59-181">On the action pane, select **Save**.</span></span>

<span data-ttu-id="78d59-182">Följande bild visar information om ett konfigurerat lagerställe.</span><span class="sxs-lookup"><span data-stu-id="78d59-182">The following image shows details for a configured warehouse.</span></span>

![Exempel på konfigurerat lagerställe](media/warehouse-sample.png)

## <a name="additional-resources"></a><span data-ttu-id="78d59-184">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="78d59-184">Additional resources</span></span>

[<span data-ttu-id="78d59-185">Lagerstyrning – översikt</span><span class="sxs-lookup"><span data-stu-id="78d59-185">Warehouse management overview</span></span>](../supply-chain/warehousing/warehouse-management-overview.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="78d59-186">Översikt över kanaler</span><span class="sxs-lookup"><span data-stu-id="78d59-186">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="78d59-187">Förutsättningar för att ställa in kanaler</span><span class="sxs-lookup"><span data-stu-id="78d59-187">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="78d59-188">Ställa in en butikskanal</span><span class="sxs-lookup"><span data-stu-id="78d59-188">Set up a retail channel</span></span>](channel-setup-retail.md)
    
[<span data-ttu-id="78d59-189">Ställ in en onlinekanal</span><span class="sxs-lookup"><span data-stu-id="78d59-189">Set up an online channel</span></span>](channel-setup-online.md)

[<span data-ttu-id="78d59-190">Ställa in en kundtjänstkanal</span><span class="sxs-lookup"><span data-stu-id="78d59-190">Set up a call center channel</span></span>](channel-setup-callcenter.md)







[!INCLUDE[footer-include](../includes/footer-banner.md)]
