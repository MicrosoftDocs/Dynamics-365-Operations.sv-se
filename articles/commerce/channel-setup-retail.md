---
title: Ställa in en butikskanal
description: I det här avsnittet beskrivs hur du skapar en ny butikskanal i Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 01/27/2020
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
ms.openlocfilehash: 713cbe68c151b6893519843611089941cabf0e70
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5800601"
---
# <a name="set-up-a-retail-channel"></a><span data-ttu-id="a9247-103">Ställa in en återförsäljarkanal</span><span class="sxs-lookup"><span data-stu-id="a9247-103">Set up a retail channel</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="a9247-104">I det här avsnittet beskrivs hur du skapar en ny butikskanal i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="a9247-104">This topic describes how to create a new retail channel in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="a9247-105">Dynamics 365 Commerce stöder flera butikskanaler.</span><span class="sxs-lookup"><span data-stu-id="a9247-105">Dynamics 365 Commerce supports multiple retail channels.</span></span> <span data-ttu-id="a9247-106">Dessa kanaler inkluderar onlinebutiker, kundtjänst och butiker (kallas också fysiska butiker).</span><span class="sxs-lookup"><span data-stu-id="a9247-106">These retail channels include online stores, call centers, and retail stores (also known as brick-and-mortar stores).</span></span> <span data-ttu-id="a9247-107">Varje butikskanal kan ha egna betalsätt, prisgrupper, kassaregister (POS), intäkts- och utgiftskonton och personal.</span><span class="sxs-lookup"><span data-stu-id="a9247-107">Each retail store channel can have its own payment methods, price groups, point of sale (POS) registers, income accounts and expense accounts, and staff.</span></span> <span data-ttu-id="a9247-108">Du måste ställa in alla dessa element innan du kan skapa en butikskanel.</span><span class="sxs-lookup"><span data-stu-id="a9247-108">You must set up all of these elements before you can create a retail store channel.</span></span> 

<span data-ttu-id="a9247-109">Innan du skapar en butikskanal ska du kontrollera att du följer [kanalförutsättningarna](channels-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="a9247-109">Before a retail channel is created, ensure you follow the [channel prerequisites](channels-prerequisites.md).</span></span>

## <a name="create-and-configure-a-new-retail-channel"></a><span data-ttu-id="a9247-110">Skapa och konfigurera en ny butikskanal</span><span class="sxs-lookup"><span data-stu-id="a9247-110">Create and configure a new retail channel</span></span>

1. <span data-ttu-id="a9247-111">I navigeringsfönstret, gå till **Moduler \> Kanaler \> Butiker \> Alla butiker**.</span><span class="sxs-lookup"><span data-stu-id="a9247-111">In the navigation pane, go to **Modules \> Channels \> Stores \> All stores**.</span></span>
1. <span data-ttu-id="a9247-112">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="a9247-112">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="a9247-113">I fältet **Namn** ange ett namn på den nya kanalen.</span><span class="sxs-lookup"><span data-stu-id="a9247-113">In the **Name** field, provide a name for the new channel.</span></span>
1. <span data-ttu-id="a9247-114">Markera ett unikt butiksnummer i fältet **Butiksnummer**.</span><span class="sxs-lookup"><span data-stu-id="a9247-114">In the **Store number** field, provide a unique store number.</span></span> <span data-ttu-id="a9247-115">Numret kan vara alfanumeriskt och får innehålla högst 10 tecken.</span><span class="sxs-lookup"><span data-stu-id="a9247-115">The number can be alphanumeric with a maximum of 10 characters.</span></span>
1. <span data-ttu-id="a9247-116">I listrutan **juridisk person** anger du den relevanta juridiska personen.</span><span class="sxs-lookup"><span data-stu-id="a9247-116">In the **Legal entity** drop-down list, enter the appropriate legal entity.</span></span>
1. <span data-ttu-id="a9247-117">I listrutan **lagerställe** anger du lämpligt lagerställe.</span><span class="sxs-lookup"><span data-stu-id="a9247-117">In the **Warehouse** drop-down list, enter the appropriate warehouse.</span></span>
1. <span data-ttu-id="a9247-118">Välj lämplig tidszon i fältet **Butikens tidszon** .</span><span class="sxs-lookup"><span data-stu-id="a9247-118">In the **Store time zone** field, select the appropriate time zone.</span></span>
1. <span data-ttu-id="a9247-119">I listrutan **Momsgrupp**, välj en lämplig momsgrupp för butiken.</span><span class="sxs-lookup"><span data-stu-id="a9247-119">In the **Sales tax group** drop-down list, select an appropriate sales tax group for the store.</span></span>
1. <span data-ttu-id="a9247-120">Välj lämplig valuta i fältet **valuta**.</span><span class="sxs-lookup"><span data-stu-id="a9247-120">In the **Currency** field, select the appropriate currency.</span></span>
1. <span data-ttu-id="a9247-121">I fältet **Kundens adressbok** ange en giltig adressbok.</span><span class="sxs-lookup"><span data-stu-id="a9247-121">In the **Customer address book** field, provide a valid address book.</span></span>
1. <span data-ttu-id="a9247-122">I fältet **Standardkund** ange en giltig standardkund.</span><span class="sxs-lookup"><span data-stu-id="a9247-122">In the **Default customer** field, provide a valid default customer.</span></span>
1. <span data-ttu-id="a9247-123">I fältet **Funktionsprofil** välj en funktionsprofil om tillämpligt.</span><span class="sxs-lookup"><span data-stu-id="a9247-123">In the **Functionality profile** field, select a functionality profile if applicable.</span></span>
1. <span data-ttu-id="a9247-124">I fältet **Meddelandeprofil för e-post** ange en giltig meddelandeprofil för e-post.</span><span class="sxs-lookup"><span data-stu-id="a9247-124">In the **Email notification profile** field, provide a valid email notification profile.</span></span>
1. <span data-ttu-id="a9247-125">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="a9247-125">On the action pane, select **Save**.</span></span>

<span data-ttu-id="a9247-126">Följande bild visar hur en ny butikskanal skapas.</span><span class="sxs-lookup"><span data-stu-id="a9247-126">The following image shows the creation of a new retail channel.</span></span>

![Ny butikskanal](media/channel-setup-retail-1.png)

<span data-ttu-id="a9247-128">I bilden nedan visas ett exempel på butikskanal.</span><span class="sxs-lookup"><span data-stu-id="a9247-128">The following image shows an example retail channel.</span></span>

![Exempel på butikskanal](media/channel-setup-retail-2.png)

## <a name="other-settings"></a><span data-ttu-id="a9247-130">Andra inställningar</span><span class="sxs-lookup"><span data-stu-id="a9247-130">Other settings</span></span>

<span data-ttu-id="a9247-131">Det finns flera andra inställningar som kan ställas in i avsnitten **Utdrag/stängning** och **Diverse**, baserat på butikens behov.</span><span class="sxs-lookup"><span data-stu-id="a9247-131">There are numerous other optional settings that can be set in the **Statement/closing** and **Miscellaneous** sections, based on the needs of the retail store.</span></span>

<span data-ttu-id="a9247-132">Se även [Skärmlayouter för POS](pos-screen-layouts.md) för information om att ställa in standardskärmlayouten i avsnittet **skärmlayout** och [Konfigurera och installera Retail Hardware Station](retail-hardware-station-configuration-installation.md) för inställningsinformation om avsnittet **Maskinvarustationer**.</span><span class="sxs-lookup"><span data-stu-id="a9247-132">In addition, see [Screen layouts for the point of sale (POS)](pos-screen-layouts.md) for information on setting up the default screen layout in the **Screen layout** section and [Configure and install Retail hardware station](retail-hardware-station-configuration-installation.md) for setup information about the **Hardware stations** section.</span></span>

<span data-ttu-id="a9247-133">I bilden nedan visas ett exempel på konfiguration av butikskanal.</span><span class="sxs-lookup"><span data-stu-id="a9247-133">The following image shows an example retail channel setup configuration.</span></span>

![Exempel på butikskanalkonfiguration](media/channel-setup-retail-3.png)

## <a name="additional-channel-set-up"></a><span data-ttu-id="a9247-135">Konfiguration av ytterligare kanal</span><span class="sxs-lookup"><span data-stu-id="a9247-135">Additional channel set up</span></span>

<span data-ttu-id="a9247-136">Det finns ytterligare objekt som måste konfigureras för en kanal som kan hittas i **åtgärdsfönstret** under avsnittet **inställningar**.</span><span class="sxs-lookup"><span data-stu-id="a9247-136">There are additional items that need to be set up for a channel that can be found on the **Action pane** under the **Set up** section.</span></span>

<span data-ttu-id="a9247-137">Ytterligare uppgifter som krävs för online-kanalkonfigurering inkluderar inställning av betalsätt, kontantdeklaration, leveranssätt, inkomst/utgiftskonto, avsnitt, tilldelning av uppfyllelsegrupp och kassaskåp.</span><span class="sxs-lookup"><span data-stu-id="a9247-137">Additional tasks required for online channel setup include setting up payment methods, cash declaration, modes of delivery, income/expense account, sections, the fulfillment group assignment, and safes.</span></span>

<span data-ttu-id="a9247-138">Följande bild visar olika ytterligare alternativ för inställning av butikskanaler på fliken **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="a9247-138">The following image shows various additional retail channel setup options on the **Set up** tab.</span></span>

![Ställ in en kanal](media/channel-setup-retail-4.png)

### <a name="set-up-payment-methods"></a><span data-ttu-id="a9247-140">Ange betalsätt</span><span class="sxs-lookup"><span data-stu-id="a9247-140">Set up payment methods</span></span>

<span data-ttu-id="a9247-141">Om du vill ställa in betalsätt följer du dessa steg för varje betalningstyp som stöds på den här kanalen.</span><span class="sxs-lookup"><span data-stu-id="a9247-141">To set up payment methods, for each payment type supported on this channel follow these steps.</span></span>

1. <span data-ttu-id="a9247-142">I åtgärdsfönstret, välj fliken **Inställningar** och välj sedan **betalningssätt**.</span><span class="sxs-lookup"><span data-stu-id="a9247-142">On the action pane, select the **Set Up** tab, then select **Payment methods**.</span></span>
1. <span data-ttu-id="a9247-143">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="a9247-143">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="a9247-144">I navigeringsfönstret väljer du önskad betalningsmetod.</span><span class="sxs-lookup"><span data-stu-id="a9247-144">In the navigation pane, select a desired payment method.</span></span>
1. <span data-ttu-id="a9247-145">I avsnittet **Allmänt** anger du ett **åtgärdsnamn** och konfigurerar andra önskade inställningar.</span><span class="sxs-lookup"><span data-stu-id="a9247-145">In the **General** section, provide an **Operation name** and configure any other desired settings.</span></span>
1. <span data-ttu-id="a9247-146">Konfigurera eventuella ytterligare inställningar efter behov för betalningstypen.</span><span class="sxs-lookup"><span data-stu-id="a9247-146">Configure any additional settings as required for the payment type.</span></span>
1. <span data-ttu-id="a9247-147">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="a9247-147">On the action pane, select **Save**.</span></span>

<span data-ttu-id="a9247-148">I bilden nedan visas ett exempel på en kontantbetalningsmetod.</span><span class="sxs-lookup"><span data-stu-id="a9247-148">The following image shows an example of a cash payment method.</span></span>

![Exempel på betalsätt](media/channel-setup-retail-5.png)

### <a name="set-up-cash-declaration"></a><span data-ttu-id="a9247-150">Inställningar för kontantavstämning</span><span class="sxs-lookup"><span data-stu-id="a9247-150">Set up cash declaration</span></span>

1. <span data-ttu-id="a9247-151">I åtgärdsfönstret, välj fliken **Inställningar** och välj sedan **Kontantavstämning**.</span><span class="sxs-lookup"><span data-stu-id="a9247-151">On the action pane, select the **Set Up** tab, and then select **Cash declaration**.</span></span>
1. <span data-ttu-id="a9247-152">I åtgärdsfönstret, välj **Ny** och skapa sedan alla beteckningar för **mynt** och **anteckning** som kan användas.</span><span class="sxs-lookup"><span data-stu-id="a9247-152">On the action pane, select **New**, and then create all **Coin** and **Note** denominations that are applicable.</span></span>

<span data-ttu-id="a9247-153">I bilden nedan visas ett exempel på en kontantavstämning.</span><span class="sxs-lookup"><span data-stu-id="a9247-153">The following image shows an example of a cash declaration.</span></span>

![Inställningar för kontantavstämningar](media/channel-setup-retail-6.png)

### <a name="set-up-modes-of-delivery"></a><span data-ttu-id="a9247-155">Ställ in leveranssätt</span><span class="sxs-lookup"><span data-stu-id="a9247-155">Set up modes of delivery</span></span>

<span data-ttu-id="a9247-156">Du kan visa de konfigurerade leveranssätten genom att välja **Leveranssätt** från fliken **Inställningar** i **Åtgärdsfönstret**.</span><span class="sxs-lookup"><span data-stu-id="a9247-156">You can see the configured modes of delivery by selecting **Modes of delivery** from the **Set up** tab on the **Action pane**.</span></span>  

<span data-ttu-id="a9247-157">Om du vill ändra eller lägga till ett leveranssätt följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="a9247-157">To change or add a mode of delivery, follow these steps.</span></span>

1. <span data-ttu-id="a9247-158">I navigeringsfönstret, gå till **Moduler \> Lagerhantering \> Leveranssätt**.</span><span class="sxs-lookup"><span data-stu-id="a9247-158">In the navigation pane, go to **Modules \> Inventory management \> Modes of delivery**.</span></span>
1. <span data-ttu-id="a9247-159">I åtgärdsfönstret, välj **Ny** om du vill skapa ett nytt leverans sätt, eller välj ett befintligt läge.</span><span class="sxs-lookup"><span data-stu-id="a9247-159">On the action pane, select **New** to create a new mode of delivery, or select an existing mode.</span></span>
1. <span data-ttu-id="a9247-160">I avsnittet **butikskanaler**, välj **lägg till rad** om du vill lägga till kanalen.</span><span class="sxs-lookup"><span data-stu-id="a9247-160">In the **Retail channels** section, select **Add line** to add the channel.</span></span> <span data-ttu-id="a9247-161">Lägga till kanaler med hjälp av organisationsnoder istället för att lägga till varje kanal individuellt kan lägga till kanaler effektivare.</span><span class="sxs-lookup"><span data-stu-id="a9247-161">Adding channels using organization nodes instead of adding each channel individually can streamline adding channels.</span></span>

<span data-ttu-id="a9247-162">I bilden nedan visas ett exempel på ett leveranssätt.</span><span class="sxs-lookup"><span data-stu-id="a9247-162">The following image shows an example of a mode of delivery.</span></span>

![Ställ in leveranssätt](media/channel-setup-retail-7.png)

### <a name="set-up-incomeexpense-account"></a><span data-ttu-id="a9247-164">Ställ in intäkts-/utgiftskonto</span><span class="sxs-lookup"><span data-stu-id="a9247-164">Set up income/expense account</span></span>

<span data-ttu-id="a9247-165">Så här ställer du in intäkts-/utgiftskonto.</span><span class="sxs-lookup"><span data-stu-id="a9247-165">To set up income/expense account, follow these steps.</span></span>

1. <span data-ttu-id="a9247-166">I åtgärdsfönstret, välj fliken **Inställningar** och välj sedan **intäkts-/utgiftskonto**.</span><span class="sxs-lookup"><span data-stu-id="a9247-166">On the action pane, select the **Set Up** tab, and then select **Income/Expense account**.</span></span>
1. <span data-ttu-id="a9247-167">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="a9247-167">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="a9247-168">Under **Namn**, ange ett namn.</span><span class="sxs-lookup"><span data-stu-id="a9247-168">Under **Name**, enter a name.</span></span>
1. <span data-ttu-id="a9247-169">Under **Söknamn**, ange ett söknamn.</span><span class="sxs-lookup"><span data-stu-id="a9247-169">Under **Search name**, enter a search name.</span></span>
1. <span data-ttu-id="a9247-170">Under **kontotyp**, ange kontotypen.</span><span class="sxs-lookup"><span data-stu-id="a9247-170">Under **Account type**, enter the account type.</span></span>
1. <span data-ttu-id="a9247-171">Ange text för **meddelanderad 1**, **meddelanderad 2**, **följesedeltext 1** och **följesedeltext 2** efter behov.</span><span class="sxs-lookup"><span data-stu-id="a9247-171">Enter text for **Message line 1**, **Message line 2**, **Slip text 1**, and **Slip text 2** as needed.</span></span>
1. <span data-ttu-id="a9247-172">Under **bokföring**, ange bokföringsinformation.</span><span class="sxs-lookup"><span data-stu-id="a9247-172">Under **Posting**, enter posting information.</span></span>
1. <span data-ttu-id="a9247-173">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="a9247-173">On the action pane, select **Save**.</span></span>

<span data-ttu-id="a9247-174">I följande bild visas ett exempel på ett intäkts-/utgiftskonto.</span><span class="sxs-lookup"><span data-stu-id="a9247-174">The following image shows an example of an income/expense account.</span></span>

![Ställ in intäkts-/utgiftskonton](media/channel-setup-retail-8.png)

### <a name="set-up-sections"></a><span data-ttu-id="a9247-176">Ställ in avsnitt</span><span class="sxs-lookup"><span data-stu-id="a9247-176">Set up sections</span></span>

<span data-ttu-id="a9247-177">Så här ställer du in avsnitt.</span><span class="sxs-lookup"><span data-stu-id="a9247-177">To set up sections, follow these steps.</span></span>

1. <span data-ttu-id="a9247-178">I åtgärdsfönstret, välj fliken **Inställningar** och välj sedan **avsnitt**.</span><span class="sxs-lookup"><span data-stu-id="a9247-178">On the action pane, select the **Set Up** tab and click **Sections**.</span></span>
1. <span data-ttu-id="a9247-179">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="a9247-179">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="a9247-180">Under **avsnittsnummer**, ange ett avsnittsnummer.</span><span class="sxs-lookup"><span data-stu-id="a9247-180">Under **Section number**, enter a section number.</span></span>
1. <span data-ttu-id="a9247-181">Under **beskrivning** ange en beskrivning.</span><span class="sxs-lookup"><span data-stu-id="a9247-181">Under **Description**, enter a description.</span></span>
1. <span data-ttu-id="a9247-182">Under **avsnittsstorlek**, ange en avsnittsstorlek.</span><span class="sxs-lookup"><span data-stu-id="a9247-182">Under **Section size**, enter a section size.</span></span>
1. <span data-ttu-id="a9247-183">Konfigurera ytterligare inställningar för **allmän** och **försäljningsstatistik** efter behov.</span><span class="sxs-lookup"><span data-stu-id="a9247-183">Configure additional settings for **General** and **Sales statistics** as needed.</span></span>
1. <span data-ttu-id="a9247-184">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="a9247-184">On the action pane, select **Save**.</span></span>

### <a name="set-up-a-fulfillment-group-assignment"></a><span data-ttu-id="a9247-185">Ange tilldelning av uppfyllelsegrupp</span><span class="sxs-lookup"><span data-stu-id="a9247-185">Set up a fulfillment group assignment</span></span>

<span data-ttu-id="a9247-186">Så här ställer du in en tilldelning av uppfyllelsegrupp.</span><span class="sxs-lookup"><span data-stu-id="a9247-186">To set up a fulfillment group assignment, follow these steps.</span></span>

1. <span data-ttu-id="a9247-187">I åtgärdsfönstret, välj fliken **Inställningar** och välj sedan **Tilldelning av uppfyllelsegrupp**.</span><span class="sxs-lookup"><span data-stu-id="a9247-187">On the action pane, select the **Set up** tab, then select **Fulfillment group assignment**.</span></span>
1. <span data-ttu-id="a9247-188">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="a9247-188">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="a9247-189">I listrutan **uppfyllelsegrupp** väljer du en uppfyllelsegrupp.</span><span class="sxs-lookup"><span data-stu-id="a9247-189">In the **Fulfillment group** drop-down list, select a fulfillment group.</span></span>
1. <span data-ttu-id="a9247-190">I listrutan **Beskrivning**, ange en beskrivning.</span><span class="sxs-lookup"><span data-stu-id="a9247-190">In the **Description** drop-down list, enter a description.</span></span>
1. <span data-ttu-id="a9247-191">Klicka på **Spara** i åtgärdsfönstret</span><span class="sxs-lookup"><span data-stu-id="a9247-191">On the action pane, select **Save**</span></span>

<span data-ttu-id="a9247-192">I bilden nedan visas ett exempel på en inställning av tilldelning av uppfyllelsegrupp.</span><span class="sxs-lookup"><span data-stu-id="a9247-192">The following image shows an example of a fulfillment group assignment setup.</span></span>

![Ange tilldelning av uppfyllelsegrupp](media/channel-setup-retail-9.png)

### <a name="set-up-safes"></a><span data-ttu-id="a9247-194">Ställ in kassaskåp</span><span class="sxs-lookup"><span data-stu-id="a9247-194">Set up safes</span></span>

<span data-ttu-id="a9247-195">Så här ställer du in kassaskåp.</span><span class="sxs-lookup"><span data-stu-id="a9247-195">To set up safes, follow these steps.</span></span>

1. <span data-ttu-id="a9247-196">I åtgärdsfönstret, välj fliken **Inställningar** och välj sedan **Kassaskåp**.</span><span class="sxs-lookup"><span data-stu-id="a9247-196">On the action pane, select the **Set Up** tab and click **Safes**.</span></span>
1. <span data-ttu-id="a9247-197">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="a9247-197">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="a9247-198">Ange ett namn på kassaskåp.</span><span class="sxs-lookup"><span data-stu-id="a9247-198">Enter a name for the safe.</span></span>
1. <span data-ttu-id="a9247-199">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="a9247-199">On the action pane, select **Save**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a9247-200">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="a9247-200">Additional resources</span></span>

[<span data-ttu-id="a9247-201">Översikt över kanaler</span><span class="sxs-lookup"><span data-stu-id="a9247-201">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="a9247-202">Förutsättningar för att ställa in kanaler</span><span class="sxs-lookup"><span data-stu-id="a9247-202">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="a9247-203">Ställ in en onlinekanal</span><span class="sxs-lookup"><span data-stu-id="a9247-203">Set up an online channel</span></span>](channel-setup-online.md)

[<span data-ttu-id="a9247-204">Ställa in en kundtjänstkanal</span><span class="sxs-lookup"><span data-stu-id="a9247-204">Set up a call center channel</span></span>](channel-setup-callcenter.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
