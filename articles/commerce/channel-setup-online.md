---
title: Ställa in en onlinekanal
description: I det här avsnittet beskrivs hur du skapar en ny onlinekanal i Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 07/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: b6bf158361f95b6551b29f195616cf21f908b802
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5800649"
---
# <a name="set-up-an-online-channel"></a><span data-ttu-id="a0e5d-103">Ställa in en onlinekanal</span><span class="sxs-lookup"><span data-stu-id="a0e5d-103">Set up an online channel</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="a0e5d-104">I det här avsnittet beskrivs hur du skapar en ny onlinekanal i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="a0e5d-104">This topic describes how to create a new online channel in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="a0e5d-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="a0e5d-105">Overview</span></span>

<span data-ttu-id="a0e5d-106">Dynamics 365 Commerce stöder flera butikskanaler.</span><span class="sxs-lookup"><span data-stu-id="a0e5d-106">Dynamics 365 Commerce supports multiple retail channels.</span></span> <span data-ttu-id="a0e5d-107">Dessa kanaler inkluderar onlinebutiker, kundtjänst och butiker (kallas också fysiska butiker).</span><span class="sxs-lookup"><span data-stu-id="a0e5d-107">These retail channels include online stores, call centers, and retail stores (also known as brick-and-mortar stores).</span></span> <span data-ttu-id="a0e5d-108">En onlinebutik ger en kunder alternativet att köpa produkter från återförsäljarens onlinebutik såväl som från deras fysiska butik.</span><span class="sxs-lookup"><span data-stu-id="a0e5d-108">Online stores give customers the option of purchasing products from the retailer's online store in addition to its retail stores.</span></span>

<span data-ttu-id="a0e5d-109">Om du vill skapa en onlinebutik i Commerce måste du först skapa en onlinekanal.</span><span class="sxs-lookup"><span data-stu-id="a0e5d-109">To create an online store in Commerce, you must first create an online channel.</span></span> <span data-ttu-id="a0e5d-110">Innan du skapar en ny onlinekanal måste du kontrollera att du har slutfört [Förutsättningar för att ställa in kanaler](channels-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="a0e5d-110">Before you create a new online channel, ensure that you have completed the [Channel set up prerequisites](channels-prerequisites.md).</span></span>

<span data-ttu-id="a0e5d-111">Innan du kan skapa en ny plats måste minst en onlinebutik skapas i Commerce.</span><span class="sxs-lookup"><span data-stu-id="a0e5d-111">Before you can create a new site, at least one online store must be created in Commerce.</span></span> <span data-ttu-id="a0e5d-112">Mer information finns i [skapa en handelsschemaläggare](create-ecommerce-site.md).</span><span class="sxs-lookup"><span data-stu-id="a0e5d-112">For more information, see [Create an e-Commerce site](create-ecommerce-site.md).</span></span>

## <a name="create-and-configure-a-new-online-channel"></a><span data-ttu-id="a0e5d-113">Skapa och konfigurera en ny onlinekanal</span><span class="sxs-lookup"><span data-stu-id="a0e5d-113">Create and configure a new online channel</span></span>

<span data-ttu-id="a0e5d-114">Följ stegen nedan om du vill skapa och konfigurera en ny onlinekanal.</span><span class="sxs-lookup"><span data-stu-id="a0e5d-114">To create and configure a new online channel, follow these steps.</span></span>

1. <span data-ttu-id="a0e5d-115">I navigeringsfönstret, gå till **Moduler \> Kanaler \> Onlinebutiker**.</span><span class="sxs-lookup"><span data-stu-id="a0e5d-115">In the navigation pane, go to **Modules \> Channels \> Online Stores**.</span></span>
1. <span data-ttu-id="a0e5d-116">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="a0e5d-116">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="a0e5d-117">I fältet **Namn** ange ett namn på den nya kanalen.</span><span class="sxs-lookup"><span data-stu-id="a0e5d-117">In the **Name** field, provide a name for the new channel.</span></span>
1. <span data-ttu-id="a0e5d-118">I listrutan **juridisk person** anger du den relevanta juridiska personen.</span><span class="sxs-lookup"><span data-stu-id="a0e5d-118">In the **Legal entity** drop-down, enter the appropriate legal entity.</span></span>
1. <span data-ttu-id="a0e5d-119">I listrutan **lagerställe** anger du lämpligt lagerställe.</span><span class="sxs-lookup"><span data-stu-id="a0e5d-119">In the **Warehouse** drop-down, enter the appropriate warehouse.</span></span>
1. <span data-ttu-id="a0e5d-120">Välj lämplig tidszon i fältet **Butikens tidszon** .</span><span class="sxs-lookup"><span data-stu-id="a0e5d-120">In the **Store time zone** field, select the appropriate time zone.</span></span>
1. <span data-ttu-id="a0e5d-121">Välj lämplig valuta i fältet **valuta**.</span><span class="sxs-lookup"><span data-stu-id="a0e5d-121">In the **Currency** field, select the appropriate currency.</span></span>
1. <span data-ttu-id="a0e5d-122">I fältet **Standardkund** ange en giltig standardkund.</span><span class="sxs-lookup"><span data-stu-id="a0e5d-122">In the **Default customer** field, provide a valid default customer.</span></span>
1. <span data-ttu-id="a0e5d-123">I fältet **Kundens adressbok** ange en giltig adressbok.</span><span class="sxs-lookup"><span data-stu-id="a0e5d-123">In the **Customer address book** field, provide a valid address book.</span></span>
1. <span data-ttu-id="a0e5d-124">I fältet **Funktionsprofil** välj en funktionsprofil om tillämpligt.</span><span class="sxs-lookup"><span data-stu-id="a0e5d-124">In the **Functionality profile** field, select a functionality profile if applicable.</span></span>
1. <span data-ttu-id="a0e5d-125">I fältet **Meddelandeprofil för e-post** ange en giltig meddelandeprofil för e-post.</span><span class="sxs-lookup"><span data-stu-id="a0e5d-125">In the **Email notification profile** field, provide a valid email notification profile.</span></span>
1. <span data-ttu-id="a0e5d-126">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="a0e5d-126">On the action pane, select **Save**.</span></span>

<span data-ttu-id="a0e5d-127">Följande bild visar hur en ny onlinekanal skapas.</span><span class="sxs-lookup"><span data-stu-id="a0e5d-127">The following image shows the creation of a new online channel.</span></span>

![Ny onlinekanal](media/channel-setup-online-1.png)

<span data-ttu-id="a0e5d-129">I bilden nedan visas ett exempel på onlinekanal.</span><span class="sxs-lookup"><span data-stu-id="a0e5d-129">The following image shows an example online channel.</span></span>

![Exempel på onlinekanal](media/channel-setup-online-2.png)

## <a name="set-up-languages"></a><span data-ttu-id="a0e5d-131">Ställ in språk</span><span class="sxs-lookup"><span data-stu-id="a0e5d-131">Set up languages</span></span>

<span data-ttu-id="a0e5d-132">Om din näthandelssajt ska stödja flera språk expanderar du avsnittet **språk** och lägger till ytterligare språk efter behov.</span><span class="sxs-lookup"><span data-stu-id="a0e5d-132">If your e-Commerce site will support multiple languages, expand the **Languages** section and add additional languages as needed.</span></span>

## <a name="set-up-payment-account"></a><span data-ttu-id="a0e5d-133">Ställ in betalningskonto</span><span class="sxs-lookup"><span data-stu-id="a0e5d-133">Set up payment account</span></span>

<span data-ttu-id="a0e5d-134">Från avsnittet **betalningskonto** kan du lägga till en tredje parts betalningsleverantör.</span><span class="sxs-lookup"><span data-stu-id="a0e5d-134">From within the **Payment account** section, you can add a third-party payment provider.</span></span> <span data-ttu-id="a0e5d-135">Information om hur du ställer in en Adyen betalningskoppling finns i [Dynamics 365 betalningskoppling för Adyen](../retail/dev-itpro/adyen-connector.md).</span><span class="sxs-lookup"><span data-stu-id="a0e5d-135">For information on setting up an Adyen payment connector, see [Dynamics 365 Payment Connector for Adyen](../retail/dev-itpro/adyen-connector.md).</span></span>

## <a name="additional-channel-setup"></a><span data-ttu-id="a0e5d-136">Konfiguration av ytterligare kanal</span><span class="sxs-lookup"><span data-stu-id="a0e5d-136">Additional channel setup</span></span>

<span data-ttu-id="a0e5d-137">Ytterligare uppgifter som krävs för inställningar av onlinekanal inkluderar inställning av betalsätt, leveranssätt och tilldelning av uppfyllelsegrupp.</span><span class="sxs-lookup"><span data-stu-id="a0e5d-137">Additional tasks that are required for online channel setup include setting up payment methods, modes of delivery, and the fulfillment group assignment.</span></span>

<span data-ttu-id="a0e5d-138">I följande bild visas alternativen **leveranssätt**, **betalsätt** och **uppfyllelse av grupptilldelning** på fliken **inställning**.</span><span class="sxs-lookup"><span data-stu-id="a0e5d-138">The following image shows **Modes of delivery**, **Payment methods**, and **Fulfillment group assignment** setup options on the **Set up** tab.</span></span>

![Ytterligare åtgärder för konfigurering av onlinekanal](media/channel-setup-online-3.png)

### <a name="set-up-payment-methods"></a><span data-ttu-id="a0e5d-140">Ange betalsätt</span><span class="sxs-lookup"><span data-stu-id="a0e5d-140">Set up payment methods</span></span>

<span data-ttu-id="a0e5d-141">Om du vill ställa in betalsätt följer du dessa steg för varje betalningstyp som stöds på den här kanalen.</span><span class="sxs-lookup"><span data-stu-id="a0e5d-141">To set up payment methods, for each payment type supported on this channel follow these steps.</span></span>

1. <span data-ttu-id="a0e5d-142">I åtgärdsfönstret, välj fliken **Inställningar** och välj sedan **betalningssätt**.</span><span class="sxs-lookup"><span data-stu-id="a0e5d-142">On the action pane, select the **Set Up** tab, then select **Payment methods**.</span></span>
1. <span data-ttu-id="a0e5d-143">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="a0e5d-143">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="a0e5d-144">I navigeringsfönstret väljer du önskad betalningsmetod.</span><span class="sxs-lookup"><span data-stu-id="a0e5d-144">In the navigation pane, select a desired payment method.</span></span>
1. <span data-ttu-id="a0e5d-145">I avsnittet **Allmänt** anger du ett **åtgärdsnamn** och konfigurerar andra önskade inställningar.</span><span class="sxs-lookup"><span data-stu-id="a0e5d-145">In the **General** section, provide an **Operation name** and configure any other desired settings.</span></span>
1. <span data-ttu-id="a0e5d-146">Konfigurera eventuella ytterligare inställningar efter behov för betalningstypen.</span><span class="sxs-lookup"><span data-stu-id="a0e5d-146">Configure any additional settings as required for the payment type.</span></span>
1. <span data-ttu-id="a0e5d-147">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="a0e5d-147">On the action pane, select **Save**.</span></span>

<span data-ttu-id="a0e5d-148">I bilden nedan visas ett exempel på en kontantbetalningsmetod.</span><span class="sxs-lookup"><span data-stu-id="a0e5d-148">The following image shows an example of a cash payment method.</span></span>

![Exempel på betalsätt](media/channel-setup-retail-5.png)

### <a name="set-up-modes-of-delivery"></a><span data-ttu-id="a0e5d-150">Ställ in leveranssätt</span><span class="sxs-lookup"><span data-stu-id="a0e5d-150">Set up modes of delivery</span></span>

<span data-ttu-id="a0e5d-151">Du kan visa de konfigurerade leveranssätten genom att välja **Leveranssätt** från fliken **Inställningar** i **Åtgärdsfönstret**.</span><span class="sxs-lookup"><span data-stu-id="a0e5d-151">You can see the configured modes of delivery by selecting **Modes of delivery** from the **Set up** tab on the **Action pane**.</span></span>  

<span data-ttu-id="a0e5d-152">Om du vill ändra eller lägga till ett leveranssätt följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="a0e5d-152">To change or add a mode of delivery, follow these steps.</span></span>

1. <span data-ttu-id="a0e5d-153">I navigeringsfönstret, gå till **Moduler \> Lagerhantering \> Leveranssätt**.</span><span class="sxs-lookup"><span data-stu-id="a0e5d-153">In the navigation pane, go to **Modules \> Inventory management \> Modes of delivery**.</span></span>
1. <span data-ttu-id="a0e5d-154">I åtgärdsfönstret, välj **Ny** om du vill skapa ett nytt leverans sätt, eller välj ett befintligt läge.</span><span class="sxs-lookup"><span data-stu-id="a0e5d-154">On the action pane, select **New** to create a new mode of delivery, or select an existing mode.</span></span>
1. <span data-ttu-id="a0e5d-155">I avsnittet **butikskanaler**, välj **lägg till rad** om du vill lägga till kanalen.</span><span class="sxs-lookup"><span data-stu-id="a0e5d-155">In the **Retail channels** section, select **Add line** to add the channel.</span></span> <span data-ttu-id="a0e5d-156">Lägga till kanaler med hjälp av organisationsnoder istället för att lägga till varje kanal individuellt kan lägga till kanaler effektivare.</span><span class="sxs-lookup"><span data-stu-id="a0e5d-156">Adding channels using organization nodes instead of adding each channel individually can streamline adding channels.</span></span>

<span data-ttu-id="a0e5d-157">I bilden nedan visas ett exempel på ett leveranssätt.</span><span class="sxs-lookup"><span data-stu-id="a0e5d-157">The following image shows an example of a mode of delivery.</span></span>

![Ställ in leveranssätt](media/channel-setup-retail-7.png)

### <a name="set-up-a-fulfillment-group-assignment"></a><span data-ttu-id="a0e5d-159">Ange tilldelning av uppfyllelsegrupp</span><span class="sxs-lookup"><span data-stu-id="a0e5d-159">Set up a fulfillment group assignment</span></span>

<span data-ttu-id="a0e5d-160">Så här ställer du in en tilldelning av uppfyllelsegrupp.</span><span class="sxs-lookup"><span data-stu-id="a0e5d-160">To set up a fulfillment group assignment, follow these steps.</span></span>

1. <span data-ttu-id="a0e5d-161">I åtgärdsfönstret, välj fliken **Inställningar** och välj sedan **Tilldelning av uppfyllelsegrupp**.</span><span class="sxs-lookup"><span data-stu-id="a0e5d-161">On the action pane, select the **Set up** tab, then select **Fulfillment group assignment**.</span></span>
1. <span data-ttu-id="a0e5d-162">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="a0e5d-162">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="a0e5d-163">I listrutan **uppfyllelsegrupp** väljer du en uppfyllelsegrupp.</span><span class="sxs-lookup"><span data-stu-id="a0e5d-163">In the **Fulfillment group** drop-down list, select a fulfillment group.</span></span>
1. <span data-ttu-id="a0e5d-164">I listrutan **Beskrivning**, ange en beskrivning.</span><span class="sxs-lookup"><span data-stu-id="a0e5d-164">In the **Description** drop-down list, enter a description.</span></span>
1. <span data-ttu-id="a0e5d-165">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="a0e5d-165">On the action pane, select **Save**.</span></span>

<span data-ttu-id="a0e5d-166">I bilden nedan visas ett exempel på en inställning av tilldelning av uppfyllelsegrupp.</span><span class="sxs-lookup"><span data-stu-id="a0e5d-166">The following image shows an example of a fulfillment group assignment setup.</span></span>

![Ange tilldelning av uppfyllelsegrupp](media/channel-setup-retail-9.png)

## <a name="additional-resources"></a><span data-ttu-id="a0e5d-168">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="a0e5d-168">Additional resources</span></span>

[<span data-ttu-id="a0e5d-169">Översikt över kanaler</span><span class="sxs-lookup"><span data-stu-id="a0e5d-169">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="a0e5d-170">Förutsättningar för att ställa in kanaler</span><span class="sxs-lookup"><span data-stu-id="a0e5d-170">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="a0e5d-171">Ställa in en butikskanal</span><span class="sxs-lookup"><span data-stu-id="a0e5d-171">Set up a retail channel</span></span>](channel-setup-retail.md)

[<span data-ttu-id="a0e5d-172">Ställa in en kundtjänstkanal</span><span class="sxs-lookup"><span data-stu-id="a0e5d-172">Set up a call center channel</span></span>](channel-setup-callcenter.md)

[<span data-ttu-id="a0e5d-173">Dynamics 365-betalningskoppling för Adyen</span><span class="sxs-lookup"><span data-stu-id="a0e5d-173">Dynamics 365 Payment Connector for Adyen</span></span>](../retail/dev-itpro/adyen-connector.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]