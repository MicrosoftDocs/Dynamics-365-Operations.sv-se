---
title: Du kan inte bekräfta en leverans eftersom inga artiklar har plockats
description: Du kan inte bekräfta en leverans eftersom inga artiklar har plockats
author: perlynne
ms.date: 04/21/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSShipConfirm,WHSLoadPlanningListPage_WHSShipConfirm,WHSLoadPlanningWorkbench_WHSShipConfirm,WHSTransportLoad_WHSShipConfirm,WHSShipPlanningListPage_WHSShipConfirm,WHSShipmentDetails_WHSShipConfirm,WHSWorkTable_WHSShipConfirm,WHSWorkTableListPage_WHSShipConfirm,Dialog_WHSOutboundShipConfirmController_WHSOutboundShipConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: lbc
ms.search.validFrom: 2021-04-21
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: f3ebd47ffc85d4ca257b404579d60d679f7929b6
ms.sourcegitcommit: f9b145ef4a81cec81f420871b4130b05db4f4500
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2021
ms.locfileid: "6301315"
---
# <a name="you-cant-confirm-a-shipment-because-items-havent-been-picked"></a><span data-ttu-id="63967-103">Du kan inte bekräfta en leverans eftersom inga artiklar har plockats</span><span class="sxs-lookup"><span data-stu-id="63967-103">You can't confirm a shipment because items haven't been picked</span></span>

<span data-ttu-id="63967-104">Felkod: LoadNotPickedAndMovedToFinalShippingLocation</span><span class="sxs-lookup"><span data-stu-id="63967-104">Error code: LoadNotPickedAndMovedToFinalShippingLocation</span></span>

## <a name="symptoms"></a><span data-ttu-id="63967-105">Symtom</span><span class="sxs-lookup"><span data-stu-id="63967-105">Symptoms</span></span>

<span data-ttu-id="63967-106">När du försöker bekräfta en leverans visas följande felmeddelande i systemet:</span><span class="sxs-lookup"><span data-stu-id="63967-106">When you try to confirm a shipment, the system shows the following error message:</span></span>

> <span data-ttu-id="63967-107">Vissa av de artiklar som behövs för lasten %1 har ännu inte plockats och förflyttats till den slutliga leveransplatsen.</span><span class="sxs-lookup"><span data-stu-id="63967-107">Some of the items that are needed for load %1 have not yet been picked and moved to the final shipping location.</span></span>

<span data-ttu-id="63967-108">Du kan därför inte bekräfta leveransen för beläggningen.</span><span class="sxs-lookup"><span data-stu-id="63967-108">Therefore, you can't confirm the shipment for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="63967-109">Orsak</span><span class="sxs-lookup"><span data-stu-id="63967-109">Cause</span></span>

<span data-ttu-id="63967-110">Beläggningen eller leveransen kan inte bekräftas i sitt aktuella tillstånd eftersom något av följande villkor kan finnas:</span><span class="sxs-lookup"><span data-stu-id="63967-110">The load or shipment can't be confirmed in its current state because one of the following conditions might exist:</span></span>

- <span data-ttu-id="63967-111">Det relaterade arbetet har ännu inte plockats och flyttats till den slutliga leveransplatsen.</span><span class="sxs-lookup"><span data-stu-id="63967-111">The related work hasn't yet been picked and moved to the final shipping location.</span></span>
- <span data-ttu-id="63967-112">Den plockade arbetskvantiteten matchar inte den skapade arbetskvantiteten på beläggningsraden.</span><span class="sxs-lookup"><span data-stu-id="63967-112">The picked work quantity doesn't match the created work quantity on the load line.</span></span>
- <span data-ttu-id="63967-113">Platsdirektivet har konfigurerats med förpackningsplats som den slutliga leveransplatsen vid användning av påfyllnadsmall för skapande av behållare.</span><span class="sxs-lookup"><span data-stu-id="63967-113">The location directive has been configured with packing location as the final shipping location while using Wave template containerization.</span></span>

## <a name="resolution"></a><span data-ttu-id="63967-114">Lösning</span><span class="sxs-lookup"><span data-stu-id="63967-114">Resolution</span></span>

<span data-ttu-id="63967-115">Beläggningen eller leveransen befinner sig för närvarande i ett skick där leveransbekräftelsen misslyckas.</span><span class="sxs-lookup"><span data-stu-id="63967-115">The load or shipment is currently in a state where shipment confirmation fails.</span></span> <span data-ttu-id="63967-116">Utför en eller flera av följande uppgifter för att åtgärda detta problem:</span><span class="sxs-lookup"><span data-stu-id="63967-116">To fix this issue, complete one of the following tasks:</span></span>

- <span data-ttu-id="63967-117">Granska dina lastrader och se till att allt relaterat arbete har slutförts vid den slutliga leveransplatsen och att kvantiteterna matchar.</span><span class="sxs-lookup"><span data-stu-id="63967-117">Review your load lines and make sure that all the related work has been completed at the final shipping location, and that the quantities match.</span></span>
- <span data-ttu-id="63967-118">Avbryt de arbets-ID som har skapats med förpackningsplatsen som slutlig leveransplats, omkonfigurera plats direktivet och återutsläpp belastningen.</span><span class="sxs-lookup"><span data-stu-id="63967-118">Cancel the work IDs that have been created with the packing location as the final shipping location, reconfigure the location directive, and rerelease the load.</span></span>

### <a name="review-your-load-lines-and-make-sure-that-all-the-related-work-has-been-completed-at-the-final-shipping-location-and-that-the-quantities-match"></a><span data-ttu-id="63967-119">Granska dina lastrader och se till att allt relaterat arbete har slutförts vid den slutliga leveransplatsen och att kvantiteterna matchar</span><span class="sxs-lookup"><span data-stu-id="63967-119">Review your load lines and make sure that all the related work has been completed at the final shipping location, and that the quantities match</span></span>

<span data-ttu-id="63967-120">Använd följande procedur för att granska dina lastrader och se till att allt relaterat arbete har slutförts vid den slutliga leveransplatsen och att kvantiteterna matchar.</span><span class="sxs-lookup"><span data-stu-id="63967-120">Use the following procedure to review your load lines and make sure that all the related work has been completed at the final shipping location, and that the quantities match.</span></span>

1. <span data-ttu-id="63967-121">Gå till **Warehouse management \> Laster \> Alla laster**.</span><span class="sxs-lookup"><span data-stu-id="63967-121">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="63967-122">Välj den beläggning som leveransen inte kan bekräftas för.</span><span class="sxs-lookup"><span data-stu-id="63967-122">Select the load that the shipment can't be confirmed for.</span></span>
1. <span data-ttu-id="63967-123">På snabbfliken **Beläggningsrader** väljer du beläggningsraden.</span><span class="sxs-lookup"><span data-stu-id="63967-123">On the **Load lines** FastTab, select the load line.</span></span>
1. <span data-ttu-id="63967-124">Lägg märke till värdet i fältet **Arbetsskapad kvantitet**.</span><span class="sxs-lookup"><span data-stu-id="63967-124">Make a note of the value of the **Work created quantity** field.</span></span>
1. <span data-ttu-id="63967-125">I åtgärdsfönstret, på fliken **Geläggningar**, i gruppen **Relaterad information**, väljer du **Arbete**.</span><span class="sxs-lookup"><span data-stu-id="63967-125">On the Action Pane, on the **Loads** tab, in the **Related information** group, select **Work**.</span></span>
1. <span data-ttu-id="63967-126">Kontrollera att arbetet har slutförts vid den slutliga leveransplatsen och att den plockade arbetskvantiteten matchar den skapade arbetskvantiteten på beläggningsraden.</span><span class="sxs-lookup"><span data-stu-id="63967-126">Verify that the work has been completed at the final shipping location, and that the picked work quantity matches the created work quantity on the load line.</span></span>
1. <span data-ttu-id="63967-127">Upprepa den här proceduren för alla beläggningsrader för att se till att alla kriterier är uppfyllda.</span><span class="sxs-lookup"><span data-stu-id="63967-127">Repeat this procedure for all load lines to make sure that all criteria are met.</span></span>

### <a name="cancel-the-work-ids-that-have-been-created-with-the-packing-location-as-the-final-shipping-location-reconfigure-the-location-directive-and-rerelease-the-load"></a><span data-ttu-id="63967-128">Avbryt de arbets-ID som har skapats med förpackningsplatsen som slutlig leveransplats, omkonfigurera plats direktivet och återutsläpp belastningen</span><span class="sxs-lookup"><span data-stu-id="63967-128">Cancel the work IDs that have been created with the packing location as the final shipping location, reconfigure the location directive, and rerelease the load</span></span>

<span data-ttu-id="63967-129">Använd följande procedur för att avbryta arbets-ID som har förpackningsplatsen som den slutliga placeringsplatsen med automatiserad skapande av behållare på plats.</span><span class="sxs-lookup"><span data-stu-id="63967-129">Use the following procedure to cancel the work IDs that have the packing location as the final put location with automated containerization in place.</span></span>

1. <span data-ttu-id="63967-130">Gå till **Warehouse management \> Periodiska uppgifter \> Rensa upp \> Avbryt arbete**.</span><span class="sxs-lookup"><span data-stu-id="63967-130">Go to **Warehouse management \> Periodic tasks \> Clean up \> Cancel work**.</span></span>
1. <span data-ttu-id="63967-131">Dialogrutan **Avbryt arbete**.</span><span class="sxs-lookup"><span data-stu-id="63967-131">The **Cancel work** dialog opens.</span></span> <span data-ttu-id="63967-132">I fältet **Arbets-ID** anger du ID-numret för det arbete som du vil avbryta.</span><span class="sxs-lookup"><span data-stu-id="63967-132">In the **Work ID** field, specify the ID of the work that you want to cancel.</span></span> <span data-ttu-id="63967-133">Det valda arbets-ID:t måste ha ett värdet **Arbetsstatus** av *Öppen*, *Pågår*, *Annullerat*, *Kombinerad* eller *Stängd*.</span><span class="sxs-lookup"><span data-stu-id="63967-133">The selected work ID must have a **Work status** value of *Open*, *In progress*, *Canceled*, *Combined*, or *Closed*.</span></span>
1. <span data-ttu-id="63967-134">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="63967-134">Select **OK**.</span></span>
1. <span data-ttu-id="63967-135">Välj **Ja** för att bekräfta att du vill avbryta arbetet.</span><span class="sxs-lookup"><span data-stu-id="63967-135">Select **Yes** to confirm that you want to cancel the work.</span></span>
1. <span data-ttu-id="63967-136">Upprepa denna procedur för övriga arbets-ID:n efter behov.</span><span class="sxs-lookup"><span data-stu-id="63967-136">Repeat this procedure for the other work IDs as needed.</span></span>

<span data-ttu-id="63967-137">Mer information finns i [Avbryt lagerarbete för undantagshantering](../../warehousing/cancel-warehouse-work.md).</span><span class="sxs-lookup"><span data-stu-id="63967-137">For more information, see [Cancel warehouse work for exception handling](../../warehousing/cancel-warehouse-work.md).</span></span>

<span data-ttu-id="63967-138">Använd följande procedur om du vill omkonfigurera platsdirektivet så att förpackningsplatsen inte används som den slutliga leveransplatsen när automatisk skapande av behållare ställs in för påfyllnadsmall.</span><span class="sxs-lookup"><span data-stu-id="63967-138">Use the following procedure to reconfigure the location directive so it won't use the packing location as the final shipping location when automated containerization is set up for the wave template.</span></span>

1. <span data-ttu-id="63967-139">Gå till **Warehouse management \> Inställningar \> Platsdirektiv**.</span><span class="sxs-lookup"><span data-stu-id="63967-139">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="63967-140">Välj **Inköpsorder** i fältet *Försäljningsarbetsorder*.</span><span class="sxs-lookup"><span data-stu-id="63967-140">In the **Work order type** field, select *Sales orders*.</span></span>
1. <span data-ttu-id="63967-141">Välj det platsdirektivet du använder för automatiserad skapande av behållare.</span><span class="sxs-lookup"><span data-stu-id="63967-141">Select the location directive you are using for automated containerization.</span></span>
1. <span data-ttu-id="63967-142">På snabbfliken **Platsdirektivåtgärder** välj **Redigera fråga**.</span><span class="sxs-lookup"><span data-stu-id="63967-142">On the **Location Directive Actions** FastTab toolbar, select **Edit query**.</span></span>
1. <span data-ttu-id="63967-143">I dialogrutan frågeredigera, på **Intervall** hitta raden där **Fält** anges *Platsprofil* och kontrollera att fältet **Villkor** för den raden är inte inställt på en platsprofil som har en **Platstyp** av *Förpackning*.</span><span class="sxs-lookup"><span data-stu-id="63967-143">In the query editor dialog, on the **Range** tab, find the row where **Field** is set to *Location profile*, and verify that the **Criteria** field for that row is not set to a location profile that has a **Location type** of *Packing*.</span></span> <span data-ttu-id="63967-144">Justera fältet **Kriterier** för att korrigera den slutliga placeringsplatsen.</span><span class="sxs-lookup"><span data-stu-id="63967-144">Adjust the **Criteria** field to correct the final put location.</span></span>

<span data-ttu-id="63967-145">Använd följande procedur för att frigöra lasten igen och skapa arbets-ID med rätt slutlig leveransplats.</span><span class="sxs-lookup"><span data-stu-id="63967-145">Use the following procedure to rerelease the load and create work IDs with the correct final shipping location.</span></span>

1. <span data-ttu-id="63967-146">Gå till **Hantering av lagerställe \> Beläggningar \> Workbench för lastplanering**.</span><span class="sxs-lookup"><span data-stu-id="63967-146">Go to **Warehouse management \> Loads \> Load planning workbench**.</span></span>
1. <span data-ttu-id="63967-147">I avsnittet **Laster** hittar du den last som behöver frisläppas.</span><span class="sxs-lookup"><span data-stu-id="63967-147">In the **Loads** section, find the load that needs to be released.</span></span>
1. <span data-ttu-id="63967-148">I avsnittet **Laster** välj **Släpp \> Släpp till lagerställe** om du vill frisläppa den valda beläggningen till lagerstället.</span><span class="sxs-lookup"><span data-stu-id="63967-148">On the **Loads** section toolbar, select **Release \> Release to warehouse** to release the selected load to the warehouse.</span></span>
1. <span data-ttu-id="63967-149">Upprepa denna procedur för övriga laster efter behov.</span><span class="sxs-lookup"><span data-stu-id="63967-149">Repeat this procedure for the other loads as needed.</span></span>
