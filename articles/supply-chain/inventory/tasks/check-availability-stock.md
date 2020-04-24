---
title: Kontrollera lagertillgängligheten
description: Den här proceduren visar hur du kontrollerar lagerbehållning och fysisk lagerbehållning för ett visst artikelnummer.
author: ShylaThompson
manager: tfehr
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventOnHandItemListPage, SysQueryForm, InventDimParmFixed, InventSupply, DefaultDashboard, WHSInventPhysicalOnhand, WHSOnHand
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e76c123ffbeb33cbc3ba01b4b2758208ed0c445f
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3204227"
---
# <a name="check-the-availability-of-stock"></a><span data-ttu-id="de95c-103">Kontrollera lagertillgängligheten</span><span class="sxs-lookup"><span data-stu-id="de95c-103">Check the availability of stock</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="de95c-104">Den här proceduren visar hur du kontrollerar lagerbehållning och fysisk lagerbehållning för ett visst artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="de95c-104">This procedure shows you how to check on-hand and physical on-hand inventory for a specific item number.</span></span> <span data-ttu-id="de95c-105">Den visar också hur du kan få leveransinformation relaterad till en artikel.</span><span class="sxs-lookup"><span data-stu-id="de95c-105">It also shows you how to get supply information related to an item.</span></span> <span data-ttu-id="de95c-106">Fysisk lagerbehållning är den lagerbehållning som är tillgänglig – det vill säga den har köpts, mottagits och registrerats.</span><span class="sxs-lookup"><span data-stu-id="de95c-106">Physical on-hand inventory is the on-hand inventory that's available – that is, it's purchased, received and registered.</span></span> <span data-ttu-id="de95c-107">Lagerbehållningen omfattar den tillgängliga lagerbehållningen och även det lager som har beställts och förväntas inkomma, men som ännu inte tagits emot eller registrerats.</span><span class="sxs-lookup"><span data-stu-id="de95c-107">On-hand inventory includes the available on-hand inventory, but also the inventory that's been ordered and is expected, but not yet received or registered.</span></span> <span data-ttu-id="de95c-108">Du kan gå igenom den här proceduren i demonstrationsdataföretaget USMF eller använda dina egna data.</span><span class="sxs-lookup"><span data-stu-id="de95c-108">You can walk through this procedure in demo data company USMF, or using your own data.</span></span> <span data-ttu-id="de95c-109">Om du använder USMF, kan du använda exempelvärdena som visas.</span><span class="sxs-lookup"><span data-stu-id="de95c-109">If you are using USMF you can use the example values that are shown.</span></span> <span data-ttu-id="de95c-110">Dessa uppgifter utförs vanligtvis av en lagerarbetare.</span><span class="sxs-lookup"><span data-stu-id="de95c-110">These tasks would typically be carried out by a warehouse worker.</span></span>


## <a name="check-on-hand-inventory-for-an-item"></a><span data-ttu-id="de95c-111">Kontrollera lagerbehållning för en artikel</span><span class="sxs-lookup"><span data-stu-id="de95c-111">Check on-hand inventory for an item</span></span>
1. <span data-ttu-id="de95c-112">Gå till **Navigeringsfönster > Moduler > Lagerhantering > Förfrågningar och rapporter > Lagerbehållning**.</span><span class="sxs-lookup"><span data-stu-id="de95c-112">Go to **Navigation pane > Modules > Inventory management > Inquiries and reports > On-hand inventory**.</span></span>
2. <span data-ttu-id="de95c-113">Markera raden med **artikelnumret**.</span><span class="sxs-lookup"><span data-stu-id="de95c-113">Select the **Item number** row.</span></span> <span data-ttu-id="de95c-114">Välj det register där raden ställs in på lagerbehållning och angetts i fältet artikelnumret du vill fråga **lagerbehållningen** per **artikelnummer**.</span><span class="sxs-lookup"><span data-stu-id="de95c-114">To query the on-hand inventory by item number, select the row where the Table is set to **On-hand inventory** and Field is set to **Item** number.</span></span>
3. <span data-ttu-id="de95c-115">I fältet **Kriterier** väljer du den artikel du vill lägga söka.</span><span class="sxs-lookup"><span data-stu-id="de95c-115">In the **Criteria** field, select the item you want to query.</span></span> <span data-ttu-id="de95c-116">Om du använder företaget för USMF-demonstrationdata, kan du välja M9201.</span><span class="sxs-lookup"><span data-stu-id="de95c-116">If you're using the USMF demo data company, you can select 'M9201'.</span></span>  
4. <span data-ttu-id="de95c-117">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="de95c-117">Click **OK**.</span></span>
5. <span data-ttu-id="de95c-118">I **åtgärdsfönstret**, klicka på **Dimensioner**.</span><span class="sxs-lookup"><span data-stu-id="de95c-118">On the **Action pane**, click **Dimensions**.</span></span> <span data-ttu-id="de95c-119">Fliken **dimensioner** låter dig välja hur mycket information du vill se om din lagerbehållning.</span><span class="sxs-lookup"><span data-stu-id="de95c-119">The **Dimensions** tab allows you select how much detail you want to see about your on-hand inventory.</span></span> <span data-ttu-id="de95c-120">Om du behöver data som är relaterade till reservation, måste du se alla lagerdimensioner för artiklarna som använder avancerade processer för lagerställe (WHS).</span><span class="sxs-lookup"><span data-stu-id="de95c-120">If you need data related to reservation, you must display all inventory dimensions for the items that use advanced warehouse (WHS) processes.</span></span>
6. <span data-ttu-id="de95c-121">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="de95c-121">Click **OK**.</span></span>
7. <span data-ttu-id="de95c-122">I **åtgärdsfönstret**, klicka på **Relaterad information**.</span><span class="sxs-lookup"><span data-stu-id="de95c-122">On the **Action Pane**, click **Related information**.</span></span> <span data-ttu-id="de95c-123">Om du inte ser det här alternativet kan du behöva klicka på ellipsknappen (…) Om du vill se ytterligare åtgärderfönsterväljare.</span><span class="sxs-lookup"><span data-stu-id="de95c-123">If you don't see this option, you may need to click on the Ellipsis button (…) to see additional action pane options.</span></span>
8. <span data-ttu-id="de95c-124">Klicka på **Leveransöversikt**.</span><span class="sxs-lookup"><span data-stu-id="de95c-124">Click **Supply overview**.</span></span> <span data-ttu-id="de95c-125">Fliken **Leveransöversikt** innehåller information om varor för en viss artikel, till exempel den tillgängliga kvantiteten, produktionstiden och leverantörsinformation.</span><span class="sxs-lookup"><span data-stu-id="de95c-125">The **Supply overview** tab provides supply information for a specific item, such as the quantity on-hand, the lead time, and vendor information.</span></span>  
9. <span data-ttu-id="de95c-126">Expandera avsnittet **I lager**.</span><span class="sxs-lookup"><span data-stu-id="de95c-126">Expand the **On-hand** section.</span></span>
10. <span data-ttu-id="de95c-127">Expandera avsnittet **Leverantörer**.</span><span class="sxs-lookup"><span data-stu-id="de95c-127">Expand the **Vendors** section.</span></span>
11. <span data-ttu-id="de95c-128">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="de95c-128">Close the page.</span></span>
12. <span data-ttu-id="de95c-129">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="de95c-129">Close the page.</span></span>

## <a name="check-physical-on-hand-inventory"></a><span data-ttu-id="de95c-130">Kontrollera fysisk lagerbehållning</span><span class="sxs-lookup"><span data-stu-id="de95c-130">Check physical on-hand inventory</span></span>
1. <span data-ttu-id="de95c-131">Gå till **Navigeringsfönster > Moduler > Lagerstyrning > Förfrågningar och rapporter > Fysisk lagerbehållning**.</span><span class="sxs-lookup"><span data-stu-id="de95c-131">Go to **Navigation pane > Modules > Warehouse management > Inquiries and reports > Physical on-hand inventory**.</span></span>
2. <span data-ttu-id="de95c-132">I fältet **Artikelnummer**, skriv ett värde.</span><span class="sxs-lookup"><span data-stu-id="de95c-132">In the **Item number** field, type a value.</span></span> <span data-ttu-id="de95c-133">Du kan använda plats- och lagerställesfälten för att filtrera listan med artiklar.</span><span class="sxs-lookup"><span data-stu-id="de95c-133">You can use the Site and Warehouse fields to filter the list of items.</span></span> 
3. <span data-ttu-id="de95c-134">Uppdatera sidan.</span><span class="sxs-lookup"><span data-stu-id="de95c-134">Refresh the page.</span></span>
4. <span data-ttu-id="de95c-135">I **Åtgärdsfönstret**, klicka på **Visa dimensioner**.</span><span class="sxs-lookup"><span data-stu-id="de95c-135">On the **Action pane**, click **Display Dimensions**.</span></span> <span data-ttu-id="de95c-136">På fliken Visa dimensioner kan du välja hur mycket information du vill se om din lagerbehållning.</span><span class="sxs-lookup"><span data-stu-id="de95c-136">The Dimensions Display tab allows you select how much detail you want to see about your on-hand inventory.</span></span>
5. <span data-ttu-id="de95c-137">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="de95c-137">Click **OK**.</span></span>
6. <span data-ttu-id="de95c-138">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="de95c-138">Close the page.</span></span>

## <a name="check-on-hand-inventory-by-location"></a><span data-ttu-id="de95c-139">Kontrollera lagerbehållningen efter plats</span><span class="sxs-lookup"><span data-stu-id="de95c-139">Check on-hand inventory by location</span></span>
1. <span data-ttu-id="de95c-140">Gå till **Navigeringsfönster > Moduler > Lagerstyrning > Förfrågningar och rapporter > Behållning efter plats**.</span><span class="sxs-lookup"><span data-stu-id="de95c-140">Go to **Navigation pane > Modules > Warehouse management > Inquiries and reports > On hand by location**.</span></span>
2. <span data-ttu-id="de95c-141">Ange ett värde i fältet **Lagerställe**.</span><span class="sxs-lookup"><span data-stu-id="de95c-141">In the **Warehouse** field, type a value.</span></span> <span data-ttu-id="de95c-142">Om du använder företaget för USMF-demonstrationdata, kan du använda ”51".</span><span class="sxs-lookup"><span data-stu-id="de95c-142">If you're using the USMF demo data company, you can use '51'.</span></span>  
3. <span data-ttu-id="de95c-143">Uppdatera sidan.</span><span class="sxs-lookup"><span data-stu-id="de95c-143">Refresh the page.</span></span>
4. <span data-ttu-id="de95c-144">Klicka på **Visa dimensioner**.</span><span class="sxs-lookup"><span data-stu-id="de95c-144">Click **Display Dimensions**.</span></span>
5. <span data-ttu-id="de95c-145">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="de95c-145">Click **OK**.</span></span>
6. <span data-ttu-id="de95c-146">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="de95c-146">Close the page.</span></span>

