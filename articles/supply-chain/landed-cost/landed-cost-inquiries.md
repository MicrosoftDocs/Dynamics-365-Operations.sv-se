---
title: Förfrågningar om hemtagningskostnad
description: I det här avsnittet beskrivs hur du söker efter och använder de olika typer av förfrågningar som är tillgängliga för modulen hemtagningskostnad.
author: sherry-zheng
manager: tfehr
ms.date: 02/01/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ITMLine, ITMItemTracking, ITMContainerActivityTracking, ITMContainerTracking
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-21
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 10f5948b4e3df089aef982269143254d9ac1e8a9
ms.sourcegitcommit: 2b4809e60974e72df9476ffd62706b1bfc8da4a7
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/04/2021
ms.locfileid: "5500366"
---
# <a name="landed-cost-inquiries"></a><span data-ttu-id="41fc1-103">Förfrågningar om hemtagningskostnad</span><span class="sxs-lookup"><span data-stu-id="41fc1-103">Landed cost inquiries</span></span>

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

## <a name="voyage-line-inquiries"></a><span data-ttu-id="41fc1-104">Förfrågningar om färdrad</span><span class="sxs-lookup"><span data-stu-id="41fc1-104">Voyage line inquiries</span></span>

<span data-ttu-id="41fc1-105">Förfrågan om **färdrader** visar alla färdrader när det gäller inventering.</span><span class="sxs-lookup"><span data-stu-id="41fc1-105">The **Voyage lines** inquiry shows all voyage lines as they pertain to inventory.</span></span> <span data-ttu-id="41fc1-106">Denna förfrågan kan användas som ett filter för att hjälpa dig att hitta en artikel, inköpsorder eller annan användbar information.</span><span class="sxs-lookup"><span data-stu-id="41fc1-106">This inquiry can be used as a filter to help you find an item, purchase order, or other useful piece of information.</span></span> <span data-ttu-id="41fc1-107">Den kan också användas för att identifiera förväntat leveransdatum för en artikel som kan finnas på en eller flera färder.</span><span class="sxs-lookup"><span data-stu-id="41fc1-107">It can also be used to identify the expected delivery date of an item that might be on one or more voyages.</span></span> <span data-ttu-id="41fc1-108">På det här sättet kan det hjälpa dig att hantera förväntad lagerinleverans.</span><span class="sxs-lookup"><span data-stu-id="41fc1-108">In this way, it can help you manage expected inventory receiving.</span></span>

<span data-ttu-id="41fc1-109">Om du vill öppna denna förfrågan går du till **Hemtagningskostnad \> Förfrågningar \> Färdrader**.</span><span class="sxs-lookup"><span data-stu-id="41fc1-109">To open this inquiry, go to **Landed cost \> Inquiries \> Voyage lines**.</span></span>

### <a name="overview-tab"></a><span data-ttu-id="41fc1-110">Fliken Översikt</span><span class="sxs-lookup"><span data-stu-id="41fc1-110">Overview tab</span></span>

<span data-ttu-id="41fc1-111">På fliken **Översikt** på förfrågningssidan **Färdrader** finns ett rutnät som visar grundläggande information om varje relevant färdrad.</span><span class="sxs-lookup"><span data-stu-id="41fc1-111">The **Overview** tab of the **Voyage lines** inquiry page includes a grid that shows basic information about each relevant voyage line.</span></span> <span data-ttu-id="41fc1-112">Följande tabell beskriver kolumnerna i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="41fc1-112">The following table describes the columns in the grid.</span></span>

| <span data-ttu-id="41fc1-113">Kolumn</span><span class="sxs-lookup"><span data-stu-id="41fc1-113">Column</span></span> | <span data-ttu-id="41fc1-114">beskrivning</span><span class="sxs-lookup"><span data-stu-id="41fc1-114">Description</span></span> |
|---|---|
| <span data-ttu-id="41fc1-115">**Artikelnummer**</span><span class="sxs-lookup"><span data-stu-id="41fc1-115">**Item number**</span></span> | <span data-ttu-id="41fc1-116">Artikeln för färdraden.</span><span class="sxs-lookup"><span data-stu-id="41fc1-116">The item for the voyage line.</span></span> |
| <span data-ttu-id="41fc1-117">**Referens**</span><span class="sxs-lookup"><span data-stu-id="41fc1-117">**Reference**</span></span> | <span data-ttu-id="41fc1-118">Ordertypen (inköpsorder eller överföringsorder).</span><span class="sxs-lookup"><span data-stu-id="41fc1-118">The type of order (purchase order or transfer order).</span></span> |
| <span data-ttu-id="41fc1-119">**Antal**</span><span class="sxs-lookup"><span data-stu-id="41fc1-119">**Number**</span></span> | <span data-ttu-id="41fc1-120">Inköpsordernummer eller överföringsordernummer.</span><span class="sxs-lookup"><span data-stu-id="41fc1-120">The purchase order number or transfer order number.</span></span> |
| <span data-ttu-id="41fc1-121">**Folio**</span><span class="sxs-lookup"><span data-stu-id="41fc1-121">**Folio**</span></span> | <span data-ttu-id="41fc1-122">Den folio som är associerad med färdraden.</span><span class="sxs-lookup"><span data-stu-id="41fc1-122">The folio that is associated with the voyage line.</span></span> |
| <span data-ttu-id="41fc1-123">**Fraktcontainer**</span><span class="sxs-lookup"><span data-stu-id="41fc1-123">**Shipping container**</span></span> | <span data-ttu-id="41fc1-124">Den leveransbehållare som är associerad med färdraden.</span><span class="sxs-lookup"><span data-stu-id="41fc1-124">The shipping container that is associated with the voyage line.</span></span> |
| <span data-ttu-id="41fc1-125">**Sjötransport**</span><span class="sxs-lookup"><span data-stu-id="41fc1-125">**Voyage**</span></span> | <span data-ttu-id="41fc1-126">Den färd som är associerad med färdraden.</span><span class="sxs-lookup"><span data-stu-id="41fc1-126">The voyage that is associated with the voyage line.</span></span> |
| <span data-ttu-id="41fc1-127">**Kvantitet**</span><span class="sxs-lookup"><span data-stu-id="41fc1-127">**Quantity**</span></span> | <span data-ttu-id="41fc1-128">Kvantiteten av artiklar för färdraden.</span><span class="sxs-lookup"><span data-stu-id="41fc1-128">The quantity of the item for the voyage line.</span></span> |
| <span data-ttu-id="41fc1-129">(Övriga dimensioner)</span><span class="sxs-lookup"><span data-stu-id="41fc1-129">(Other dimensions)</span></span> | <span data-ttu-id="41fc1-130">Du kan visa kolumner för ytterligare dimensioner om det behövs.</span><span class="sxs-lookup"><span data-stu-id="41fc1-130">You can show columns for additional dimensions as you require.</span></span> <span data-ttu-id="41fc1-131">Dimensionerna inkluderar batchnummer, lagerstatus och lagerställe.</span><span class="sxs-lookup"><span data-stu-id="41fc1-131">Those dimensions include batch number, inventory status, and warehouse.</span></span> <span data-ttu-id="41fc1-132">I åtgärdsfönstret, välj **Lager \> Visa dimensioner** om du vill öppna en dialogruta där du kan välja vilka dimensioner som ska ingå.</span><span class="sxs-lookup"><span data-stu-id="41fc1-132">On the Action Pane, select **Inventory \> Display dimensions** to open a dialog box where you can select the dimensions to include.</span></span> |

### <a name="general-tab"></a><span data-ttu-id="41fc1-133">Fliken Allmänt</span><span class="sxs-lookup"><span data-stu-id="41fc1-133">General tab</span></span>

<span data-ttu-id="41fc1-134">Välj fliken **Allmänt** om du vill visa mer information om raden som har valts på fliken **Översikt**.</span><span class="sxs-lookup"><span data-stu-id="41fc1-134">Select the **General** tab to view more information about the line that is currently selected on the **Overview** tab.</span></span>

### <a name="dimensions-tab"></a><span data-ttu-id="41fc1-135">Fliken Dimensioner</span><span class="sxs-lookup"><span data-stu-id="41fc1-135">Dimensions tab</span></span>

<span data-ttu-id="41fc1-136">Välj fliken **Dimensioner** för att visa värden för alla tillgängliga dimensioner för den rad som för närvarande har markerats på fliken **Översikt**, oavsett vilka dimensioner du har valt att visa på den fliken.</span><span class="sxs-lookup"><span data-stu-id="41fc1-136">Select the **Dimensions** tab to view values for all available dimensions for the line that is currently selected on the **Overview** tab, regardless of the dimensions that you've selected to show on that tab.</span></span>

## <a name="cost-estimate-inquiries"></a><span data-ttu-id="41fc1-137">Kostnadsuppskattning förfrågningar</span><span class="sxs-lookup"><span data-stu-id="41fc1-137">Cost estimate inquiries</span></span>

<span data-ttu-id="41fc1-138">Varje gång du genererar en kostnadsuppskattning läggs uppskattningen till på sidan **Kostnadsuppskattningar**.</span><span class="sxs-lookup"><span data-stu-id="41fc1-138">Every time that you generate a cost estimate, the estimate is added to the **Cost estimates** inquiry page.</span></span> <span data-ttu-id="41fc1-139">Detaljerad information om hur du genererar, visar och arbetar med kostnadsuppskattningar (inklusive uppskattningar på förfrågan), finns i [Uppskattning och hantering av hemtagningskostnader](estimate-manage-landed-costs.md).</span><span class="sxs-lookup"><span data-stu-id="41fc1-139">For complete details about how to generate, view, and work with cost estimates (including estimates on the inquiry page), see [Estimate and manage landed costs](estimate-manage-landed-costs.md).</span></span>

## <a name="item-tracking"></a><span data-ttu-id="41fc1-140">Artikelspårning</span><span class="sxs-lookup"><span data-stu-id="41fc1-140">Item tracking</span></span>

<span data-ttu-id="41fc1-141">Använd sidan **Artikelspårning** kan du visa öppna inköpsorderrader och deras aktuella status.</span><span class="sxs-lookup"><span data-stu-id="41fc1-141">Use the **Item tracking** page to view open purchase orders lines and their current status.</span></span> <span data-ttu-id="41fc1-142">Rader behöver inte kopplas till en sådan för att kunna visas här.</span><span class="sxs-lookup"><span data-stu-id="41fc1-142">Lines don't have to be associated with a voyage to appear here.</span></span> <span data-ttu-id="41fc1-143">Om en artikel är kopplad till en rad, visar artikelspårningspostraden emellertid färd-ID.</span><span class="sxs-lookup"><span data-stu-id="41fc1-143">However, if an item is associated with a voyage, the item tracking record line shows the voyage ID.</span></span>

<span data-ttu-id="41fc1-144">Om du vill öppna den här sidan går du **Hemtagningskostnad \> Förfrågningar \> Spårning \> Artikelspårning**.</span><span class="sxs-lookup"><span data-stu-id="41fc1-144">To open this page, go to **Landed cost \> Inquiries \> Tracking \> Item tracking**.</span></span>

<span data-ttu-id="41fc1-145">Eftersom systemet troligen innehåller ett mycket stort antal inköpsorderrader visas inga poster på sidan **artikelspårning**.</span><span class="sxs-lookup"><span data-stu-id="41fc1-145">Because your system probably contains a very large number of purchase order lines, the **Item tracking** page initially shows no records.</span></span> <span data-ttu-id="41fc1-146">Börja med att använda filterfälten överst på sidan för att definiera den uppsättning inköpsorderrader som du vill ha.</span><span class="sxs-lookup"><span data-stu-id="41fc1-146">Start by using the filter fields at the top of the page to define the set of purchase order lines that you're looking for.</span></span> <span data-ttu-id="41fc1-147">Välj sedan **Uppdatera** i åtgärdsfönstret för att generera listan.</span><span class="sxs-lookup"><span data-stu-id="41fc1-147">Then select **Update** on the Action Pane to generate the list.</span></span> <span data-ttu-id="41fc1-148">Du kan använda en asterisk (\*) som jokertecken i något av filterfälten.</span><span class="sxs-lookup"><span data-stu-id="41fc1-148">You can use an asterisk (\*) as a wildcard character in any of the filter fields.</span></span> <span data-ttu-id="41fc1-149">Om du till exempel vill söka efter alla inköpsorderrader för artiklar som innehåller ordet "DVD" i namnet ställer du in fältet **Typ** till **Produknamn** och anger *\*DVD\** i fältet **Fältvärde**.</span><span class="sxs-lookup"><span data-stu-id="41fc1-149">For example, to find all purchase order lines for items that include the word "DVD" in their name, set the **Type** field to **Product name**, and enter *\*DVD\** in the **Field value** field.</span></span>

> [!NOTE]
> <span data-ttu-id="41fc1-150">Restorder omfattar för närvarande endast försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="41fc1-150">Currently, backorders include only sales orders.</span></span> <span data-ttu-id="41fc1-151">Försäljningsofferter visas eller betraktas inte som restorder.</span><span class="sxs-lookup"><span data-stu-id="41fc1-151">Sales quotations aren't shown or considered backorders.</span></span>

<span data-ttu-id="41fc1-152">I följande tabell beskrivs kolumnerna i rutnätet på sidan **Artikelspårning**.</span><span class="sxs-lookup"><span data-stu-id="41fc1-152">The following table describes the columns in the grid on the **Item tracking** page.</span></span>

| <span data-ttu-id="41fc1-153">Kolumn</span><span class="sxs-lookup"><span data-stu-id="41fc1-153">Column</span></span> | <span data-ttu-id="41fc1-154">beskrivning</span><span class="sxs-lookup"><span data-stu-id="41fc1-154">Description</span></span> |
|---|---|
| <span data-ttu-id="41fc1-155">**Till hamn**</span><span class="sxs-lookup"><span data-stu-id="41fc1-155">**To port**</span></span> | <span data-ttu-id="41fc1-156">Slutdestinationen.</span><span class="sxs-lookup"><span data-stu-id="41fc1-156">The final destination.</span></span> |
| <span data-ttu-id="41fc1-157">**Bekräftat**</span><span class="sxs-lookup"><span data-stu-id="41fc1-157">**Confirmed**</span></span> | <span data-ttu-id="41fc1-158">Bekräftat datum för inköpsordern.</span><span class="sxs-lookup"><span data-stu-id="41fc1-158">The confirmed date of the purchase order line.</span></span> |
| <span data-ttu-id="41fc1-159">**Leveransdatum**</span><span class="sxs-lookup"><span data-stu-id="41fc1-159">**Delivery Date**</span></span> | <span data-ttu-id="41fc1-160">Leveransdatum för inköpsordern.</span><span class="sxs-lookup"><span data-stu-id="41fc1-160">The delivery date of the purchase order line.</span></span> |
| <span data-ttu-id="41fc1-161">**Sjötransport**</span><span class="sxs-lookup"><span data-stu-id="41fc1-161">**Voyage**</span></span> | <span data-ttu-id="41fc1-162">Om raden är associerad med en färd, färd-ID.</span><span class="sxs-lookup"><span data-stu-id="41fc1-162">If the line is associated with a voyage, the voyage ID.</span></span> |
| <span data-ttu-id="41fc1-163">**Leveransbehållare**</span><span class="sxs-lookup"><span data-stu-id="41fc1-163">**Shipping Container**</span></span> | <span data-ttu-id="41fc1-164">Om raden är kopplad till en leveransbehållare, behållar-ID.</span><span class="sxs-lookup"><span data-stu-id="41fc1-164">If the line is attached to a shipping container, the container ID.</span></span> |
| <span data-ttu-id="41fc1-165">**Leveranshamn**</span><span class="sxs-lookup"><span data-stu-id="41fc1-165">**Shipping port**</span></span> | <span data-ttu-id="41fc1-166">Den aktuella porten, baserat på det första steget i spårningsformuläret där inget faktiskt datum har angetts för den skeppningsbehållare som är associerad med inköpsorderraden.</span><span class="sxs-lookup"><span data-stu-id="41fc1-166">The current port, based on the first leg in the tracking form where no actual date is set for the shipping container that is associated with the purchase order line.</span></span> |
| <span data-ttu-id="41fc1-167">**Aktivitet**</span><span class="sxs-lookup"><span data-stu-id="41fc1-167">**Activity**</span></span> | <span data-ttu-id="41fc1-168">Den aktuella aktivitet, baserat på det första steget i spårningsformuläret där inget faktiskt datum har angetts för den skeppningsbehållare som är associerad med inköpsorderraden.</span><span class="sxs-lookup"><span data-stu-id="41fc1-168">The current activity, based on the first leg in the tracking form where no actual date is set for the shipping container that is associated with the purchase order line.</span></span> |
| <span data-ttu-id="41fc1-169">**Uppskattat slutdatum**</span><span class="sxs-lookup"><span data-stu-id="41fc1-169">**Estimated end date**</span></span> | <span data-ttu-id="41fc1-170">Det datum då färden förväntas inlevereras till lagerstället vid destinationen.</span><span class="sxs-lookup"><span data-stu-id="41fc1-170">The date when the voyage is expected to be received at the destination warehouse.</span></span> |
| <span data-ttu-id="41fc1-171">**Namn**</span><span class="sxs-lookup"><span data-stu-id="41fc1-171">**Name**</span></span> | <span data-ttu-id="41fc1-172">Namn på leverantören.</span><span class="sxs-lookup"><span data-stu-id="41fc1-172">The name of the vendor.</span></span> |
| <span data-ttu-id="41fc1-173">**Färdstatus**</span><span class="sxs-lookup"><span data-stu-id="41fc1-173">**Voyage Status**</span></span> | <span data-ttu-id="41fc1-174">Leveransstatusen som bifogas inköpsordern.</span><span class="sxs-lookup"><span data-stu-id="41fc1-174">The shipment status that is attached to the purchase order line.</span></span> |
| <span data-ttu-id="41fc1-175">**Artikelnummer**</span><span class="sxs-lookup"><span data-stu-id="41fc1-175">**Item number**</span></span> | <span data-ttu-id="41fc1-176">Artikelnumret för inköpsorderraden.</span><span class="sxs-lookup"><span data-stu-id="41fc1-176">The item number for the purchase order line.</span></span> |
| <span data-ttu-id="41fc1-177">**Externt**</span><span class="sxs-lookup"><span data-stu-id="41fc1-177">**External**</span></span> | <span data-ttu-id="41fc1-178">Leverantörens artikelnamn.</span><span class="sxs-lookup"><span data-stu-id="41fc1-178">The vendor's item name.</span></span> |
| <span data-ttu-id="41fc1-179">**Produktnamn**</span><span class="sxs-lookup"><span data-stu-id="41fc1-179">**Product Name**</span></span> | <span data-ttu-id="41fc1-180">Namn på artikeln för inköpsorderraden.</span><span class="sxs-lookup"><span data-stu-id="41fc1-180">The name of the item for the purchase order line.</span></span> |
| <span data-ttu-id="41fc1-181">**Kvantitet**</span><span class="sxs-lookup"><span data-stu-id="41fc1-181">**Quantity**</span></span> | <span data-ttu-id="41fc1-182">Inköpsorderradens kvantitet för inköpsorderraden.</span><span class="sxs-lookup"><span data-stu-id="41fc1-182">The purchase order line quantity for the purchase order line.</span></span> |
| <span data-ttu-id="41fc1-183">**Enhet**</span><span class="sxs-lookup"><span data-stu-id="41fc1-183">**Unit**</span></span> | <span data-ttu-id="41fc1-184">Måttenheten för inköpsorderraden.</span><span class="sxs-lookup"><span data-stu-id="41fc1-184">The unit of measure for the purchase order line.</span></span> |
| <span data-ttu-id="41fc1-185">**Referens**</span><span class="sxs-lookup"><span data-stu-id="41fc1-185">**Reference**</span></span> | <span data-ttu-id="41fc1-186">Ordertypen (inköpsorder eller överföringsorder)</span><span class="sxs-lookup"><span data-stu-id="41fc1-186">The type of order (purchase order or transfer order)</span></span> |
| <span data-ttu-id="41fc1-187">**Referensnummer**</span><span class="sxs-lookup"><span data-stu-id="41fc1-187">**Reference number**</span></span> | <span data-ttu-id="41fc1-188">Inköpsordernummer eller överföringsordernummer.</span><span class="sxs-lookup"><span data-stu-id="41fc1-188">The purchase order number or transfer order number.</span></span> |
| <span data-ttu-id="41fc1-189">**Restorder**</span><span class="sxs-lookup"><span data-stu-id="41fc1-189">**Backorder**</span></span> | <span data-ttu-id="41fc1-190">En symbol indikerar att det finns försäljnings restorder för artikeln.</span><span class="sxs-lookup"><span data-stu-id="41fc1-190">A symbol indicates that there are sales backorders for the item.</span></span> |
| <span data-ttu-id="41fc1-191">(Övriga dimensioner)</span><span class="sxs-lookup"><span data-stu-id="41fc1-191">(Other dimensions)</span></span> | <span data-ttu-id="41fc1-192">Du kan visa kolumner för ytterligare dimensioner om det behövs.</span><span class="sxs-lookup"><span data-stu-id="41fc1-192">You can show columns for additional dimensions as you require.</span></span> <span data-ttu-id="41fc1-193">Dimensionerna inkluderar batchnummer, lagerstatus och lagerställe.</span><span class="sxs-lookup"><span data-stu-id="41fc1-193">Those dimensions include batch number, inventory status, and warehouse.</span></span> <span data-ttu-id="41fc1-194">I åtgärdsfönstret, välj **Visa dimensioner** om du vill öppna en dialogruta där du kan välja vilka dimensioner som ska ingå.</span><span class="sxs-lookup"><span data-stu-id="41fc1-194">On the Action Pane, select **Display dimensions** to open a dialog box where you can select the dimensions to include.</span></span> |

### <a name="related-information-about-backorders"></a><span data-ttu-id="41fc1-195">Relaterad information om restorder</span><span class="sxs-lookup"><span data-stu-id="41fc1-195">Related information about backorders</span></span>

<span data-ttu-id="41fc1-196">Om du vill visa mer information om restorder markerar du fliken **Relaterad information** till höger på sidan och väljer **Restorder**.</span><span class="sxs-lookup"><span data-stu-id="41fc1-196">To view more information about backorders, select the **Related information** tab on the right side of the page, and then select **Backorders**.</span></span> <span data-ttu-id="41fc1-197">Om du vill visa ännu mer information om en viss restorder markerar du raden för den och väljer sedan länken **Mer**.</span><span class="sxs-lookup"><span data-stu-id="41fc1-197">To view even more information about a specific backorder, select the row for it, and then select the **More** link.</span></span>

## <a name="individual-shipping-container-tracking"></a><span data-ttu-id="41fc1-198">Spårning av enskild fraktcontainer</span><span class="sxs-lookup"><span data-stu-id="41fc1-198">Individual shipping container tracking</span></span>

<span data-ttu-id="41fc1-199">I förfrågan om **individuell spårning av leveransbehållare** finns ett filter som gör att du kan hitta en leveransbehållare och sedan identifiera alla rader i den behållaren.</span><span class="sxs-lookup"><span data-stu-id="41fc1-199">The **Individual shipping container tracking** inquiry provides a filter that lets you find a shipping container and then identify all the voyage lines in that container.</span></span>

<span data-ttu-id="41fc1-200">Om du vill öppna den här förfrågan går du **Hemtagningskostnad \> Förfrågningar \> Spårning \> individuell spårning av leveransbehållare**.</span><span class="sxs-lookup"><span data-stu-id="41fc1-200">To open this inquiry, go to **Landed cost \> Inquiries \> Tracking \> Individual shipping container tracking**.</span></span>

## <a name="multiple-shipping-container-tracking"></a><span data-ttu-id="41fc1-201">Spårning av flera fraktcontainrar</span><span class="sxs-lookup"><span data-stu-id="41fc1-201">Multiple shipping container tracking</span></span>

<span data-ttu-id="41fc1-202">I förfrågan om **flera spårning av leveransbehållare** finns ett filter som gör att du kan hitta en samling leveransbehållare och sedan identifiera alla rader i de behållarna.</span><span class="sxs-lookup"><span data-stu-id="41fc1-202">The **Multiple shipping container tracking** inquiry provides a filter that lets you find a collection of shipping containers and then identify all the voyage lines in those containers.</span></span>

<span data-ttu-id="41fc1-203">Om du vill öppna den här förfrågan går du **Hemtagningskostnad \> Förfrågningar \> Spårning \> flera spårning av leveransbehållare**.</span><span class="sxs-lookup"><span data-stu-id="41fc1-203">To open this inquiry, go to **Landed cost \> Inquiries \> Tracking \> Multiple shipping container tracking**.</span></span>