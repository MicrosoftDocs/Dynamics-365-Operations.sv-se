---
title: Ställa in en butikskanal
description: I det här avsnittet beskrivs hur du skapar en ny butikskanal i Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 04/23/2021
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
ms.openlocfilehash: 3f1f5dc2c8402d9b6b68a049f804932812eb74c0
ms.sourcegitcommit: 593438a145672c55ff6a910eabce2939300b40ad
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/23/2021
ms.locfileid: "5937544"
---
# <a name="set-up-a-retail-channel"></a><span data-ttu-id="da133-103">Ställa in en återförsäljarkanal</span><span class="sxs-lookup"><span data-stu-id="da133-103">Set up a retail channel</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="da133-104">I det här avsnittet beskrivs hur du skapar en ny butikskanal i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="da133-104">This topic describes how to create a new retail channel in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="da133-105">Dynamics 365 Commerce stöder flera butikskanaler.</span><span class="sxs-lookup"><span data-stu-id="da133-105">Dynamics 365 Commerce supports multiple retail channels.</span></span> <span data-ttu-id="da133-106">Dessa kanaler inkluderar onlinebutiker, kundtjänst och butiker (kallas också fysiska butiker).</span><span class="sxs-lookup"><span data-stu-id="da133-106">These retail channels include online stores, call centers, and retail stores (also known as brick-and-mortar stores).</span></span> <span data-ttu-id="da133-107">Varje butikskanal kan ha egna betalsätt, prisgrupper, kassaregister (POS), intäkts- och utgiftskonton och personal.</span><span class="sxs-lookup"><span data-stu-id="da133-107">Each retail store channel can have its own payment methods, price groups, point of sale (POS) registers, income accounts and expense accounts, and staff.</span></span> <span data-ttu-id="da133-108">Du måste ställa in alla dessa element innan du kan skapa en butikskanel.</span><span class="sxs-lookup"><span data-stu-id="da133-108">You must set up all of these elements before you can create a retail store channel.</span></span> 

<span data-ttu-id="da133-109">Innan du skapar en butikskanal ska du kontrollera att du följer [kanalförutsättningarna](channels-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="da133-109">Before a retail channel is created, ensure you follow the [channel prerequisites](channels-prerequisites.md).</span></span>

## <a name="create-and-configure-a-new-retail-channel"></a><span data-ttu-id="da133-110">Skapa och konfigurera en ny butikskanal</span><span class="sxs-lookup"><span data-stu-id="da133-110">Create and configure a new retail channel</span></span>

1. <span data-ttu-id="da133-111">I navigeringsfönstret, gå till **Moduler \> Kanaler \> Butiker \> Alla butiker**.</span><span class="sxs-lookup"><span data-stu-id="da133-111">In the navigation pane, go to **Modules \> Channels \> Stores \> All stores**.</span></span>
1. <span data-ttu-id="da133-112">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="da133-112">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="da133-113">I fältet **Namn** ange ett namn på den nya kanalen.</span><span class="sxs-lookup"><span data-stu-id="da133-113">In the **Name** field, provide a name for the new channel.</span></span>
1. <span data-ttu-id="da133-114">Markera ett unikt butiksnummer i fältet **Butiksnummer**.</span><span class="sxs-lookup"><span data-stu-id="da133-114">In the **Store number** field, provide a unique store number.</span></span> <span data-ttu-id="da133-115">Numret kan vara alfanumeriskt och får innehålla högst 10 tecken.</span><span class="sxs-lookup"><span data-stu-id="da133-115">The number can be alphanumeric with a maximum of 10 characters.</span></span>
1. <span data-ttu-id="da133-116">I listrutan **juridisk person** anger du den relevanta juridiska personen.</span><span class="sxs-lookup"><span data-stu-id="da133-116">In the **Legal entity** drop-down list, enter the appropriate legal entity.</span></span>
1. <span data-ttu-id="da133-117">I listrutan **lagerställe** anger du lämpligt lagerställe.</span><span class="sxs-lookup"><span data-stu-id="da133-117">In the **Warehouse** drop-down list, enter the appropriate warehouse.</span></span>
1. <span data-ttu-id="da133-118">Välj lämplig tidszon i fältet **Butikens tidszon** .</span><span class="sxs-lookup"><span data-stu-id="da133-118">In the **Store time zone** field, select the appropriate time zone.</span></span>
1. <span data-ttu-id="da133-119">I listrutan **Momsgrupp**, välj en lämplig momsgrupp för butiken.</span><span class="sxs-lookup"><span data-stu-id="da133-119">In the **Sales tax group** drop-down list, select an appropriate sales tax group for the store.</span></span>
1. <span data-ttu-id="da133-120">Välj lämplig valuta i fältet **valuta**.</span><span class="sxs-lookup"><span data-stu-id="da133-120">In the **Currency** field, select the appropriate currency.</span></span>
1. <span data-ttu-id="da133-121">I fältet **Kundens adressbok** ange en giltig adressbok.</span><span class="sxs-lookup"><span data-stu-id="da133-121">In the **Customer address book** field, provide a valid address book.</span></span>
1. <span data-ttu-id="da133-122">I fältet **Standardkund** ange en giltig standardkund.</span><span class="sxs-lookup"><span data-stu-id="da133-122">In the **Default customer** field, provide a valid default customer.</span></span>
1. <span data-ttu-id="da133-123">I fältet **Funktionsprofil** välj en funktionsprofil om tillämpligt.</span><span class="sxs-lookup"><span data-stu-id="da133-123">In the **Functionality profile** field, select a functionality profile if applicable.</span></span>
1. <span data-ttu-id="da133-124">I fältet **Meddelandeprofil för e-post** ange en giltig meddelandeprofil för e-post.</span><span class="sxs-lookup"><span data-stu-id="da133-124">In the **Email notification profile** field, provide a valid email notification profile.</span></span>
1. <span data-ttu-id="da133-125">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="da133-125">On the Action Pane, select **Save**.</span></span>

<span data-ttu-id="da133-126">Följande bild visar hur en ny butikskanal skapas.</span><span class="sxs-lookup"><span data-stu-id="da133-126">The following image shows the creation of a new retail channel.</span></span>

![Ny butikskanal](media/channel-setup-retail-1.png)

<span data-ttu-id="da133-128">I bilden nedan visas ett exempel på butikskanal.</span><span class="sxs-lookup"><span data-stu-id="da133-128">The following image shows an example retail channel.</span></span>

![Exempel på butikskanal](media/channel-setup-retail-2.png)

## <a name="other-settings"></a><span data-ttu-id="da133-130">Andra inställningar</span><span class="sxs-lookup"><span data-stu-id="da133-130">Other settings</span></span>

<span data-ttu-id="da133-131">Det finns flera andra inställningar som kan ställas in i avsnitten **Utdrag/stängning** och **Diverse**, baserat på butikens behov.</span><span class="sxs-lookup"><span data-stu-id="da133-131">There are numerous other optional settings that can be set in the **Statement/closing** and **Miscellaneous** sections, based on the needs of the retail store.</span></span>

<span data-ttu-id="da133-132">Se även [Skärmlayouter för POS](pos-screen-layouts.md) för information om att ställa in standardskärmlayouten i avsnittet **skärmlayout** och [Konfigurera och installera Retail Hardware Station](retail-hardware-station-configuration-installation.md) för inställningsinformation om avsnittet **Maskinvarustationer**.</span><span class="sxs-lookup"><span data-stu-id="da133-132">In addition, see [Screen layouts for the point of sale (POS)](pos-screen-layouts.md) for information on setting up the default screen layout in the **Screen layout** section and [Configure and install Retail hardware station](retail-hardware-station-configuration-installation.md) for setup information about the **Hardware stations** section.</span></span>

<span data-ttu-id="da133-133">I bilden nedan visas ett exempel på konfiguration av butikskanal.</span><span class="sxs-lookup"><span data-stu-id="da133-133">The following image shows an example retail channel setup configuration.</span></span>

![Exempel på butikskanalkonfiguration](media/channel-setup-retail-3.png)

## <a name="additional-channel-set-up"></a><span data-ttu-id="da133-135">Konfiguration av ytterligare kanal</span><span class="sxs-lookup"><span data-stu-id="da133-135">Additional channel set up</span></span>

<span data-ttu-id="da133-136">Det finns ytterligare artiklar som måste konfigureras för en kanal som kan hittas i åtgärdsfönstret under avsnittet **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="da133-136">There are additional items that need to be set up for a channel that can be found on the Action Pane under the **Set up** section.</span></span>

<span data-ttu-id="da133-137">Ytterligare uppgifter som krävs för online-kanalkonfigurering inkluderar inställning av betalsätt, kontantdeklaration, leveranssätt, inkomst/utgiftskonto, avsnitt, tilldelning av uppfyllelsegrupp och kassaskåp.</span><span class="sxs-lookup"><span data-stu-id="da133-137">Additional tasks required for online channel setup include setting up payment methods, cash declaration, modes of delivery, income/expense account, sections, the fulfillment group assignment, and safes.</span></span>

<span data-ttu-id="da133-138">Följande bild visar olika ytterligare alternativ för inställning av butikskanaler på fliken **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="da133-138">The following image shows various additional retail channel setup options on the **Set up** tab.</span></span>

![Ställ in en kanal](media/channel-setup-retail-4.png)

### <a name="set-up-payment-methods"></a><span data-ttu-id="da133-140">Ange betalsätt</span><span class="sxs-lookup"><span data-stu-id="da133-140">Set up payment methods</span></span>

<span data-ttu-id="da133-141">Om du vill ställa in betalsätt följer du dessa steg för varje betalningstyp som stöds på den här kanalen.</span><span class="sxs-lookup"><span data-stu-id="da133-141">To set up payment methods, for each payment type supported on this channel follow these steps.</span></span>

1. <span data-ttu-id="da133-142">I åtgärdsfönstret väljer du fliken **Inställningar** och sedan **Betalningsmetod**.</span><span class="sxs-lookup"><span data-stu-id="da133-142">On the Action Pane, select the **Set Up** tab, then select **Payment methods**.</span></span>
1. <span data-ttu-id="da133-143">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="da133-143">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="da133-144">I navigeringsfönstret väljer du önskad betalningsmetod.</span><span class="sxs-lookup"><span data-stu-id="da133-144">In the navigation pane, select a desired payment method.</span></span>
1. <span data-ttu-id="da133-145">I avsnittet **Allmänt** anger du ett **åtgärdsnamn** och konfigurerar andra önskade inställningar.</span><span class="sxs-lookup"><span data-stu-id="da133-145">In the **General** section, provide an **Operation name** and configure any other desired settings.</span></span>
1. <span data-ttu-id="da133-146">Konfigurera eventuella ytterligare inställningar efter behov för betalningstypen.</span><span class="sxs-lookup"><span data-stu-id="da133-146">Configure any additional settings as required for the payment type.</span></span>
1. <span data-ttu-id="da133-147">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="da133-147">On the Action Pane, select **Save**.</span></span>

<span data-ttu-id="da133-148">I bilden nedan visas ett exempel på en kontantbetalningsmetod.</span><span class="sxs-lookup"><span data-stu-id="da133-148">The following image shows an example of a cash payment method.</span></span>

![Exempel på betalsätt](media/channel-setup-retail-5.png)

### <a name="set-up-cash-declaration"></a><span data-ttu-id="da133-150">Inställningar för kontantavstämning</span><span class="sxs-lookup"><span data-stu-id="da133-150">Set up cash declaration</span></span>

1. <span data-ttu-id="da133-151">I åtgärdsfönstret väljer du fliken **Inställningar** och sedan **Kontantavstämning**.</span><span class="sxs-lookup"><span data-stu-id="da133-151">On the Action Pane, select the **Set Up** tab, and then select **Cash declaration**.</span></span>
1. <span data-ttu-id="da133-152">I åtgärdsfönstret, väljer du **Ny** och skapar sedan alla beteckningar för **Mynt** och **Sedlar** som kan användas.</span><span class="sxs-lookup"><span data-stu-id="da133-152">On the Action Pane, select **New**, and then create all **Coin** and **Note** denominations that are applicable.</span></span>

<span data-ttu-id="da133-153">I bilden nedan visas ett exempel på en kontantavstämning.</span><span class="sxs-lookup"><span data-stu-id="da133-153">The following image shows an example of a cash declaration.</span></span>

![Inställningar för kontantavstämningar](media/channel-setup-retail-6.png)

### <a name="set-up-modes-of-delivery"></a><span data-ttu-id="da133-155">Ställ in leveranssätt</span><span class="sxs-lookup"><span data-stu-id="da133-155">Set up modes of delivery</span></span>

<span data-ttu-id="da133-156">Du kan visa de konfigurerade leveranssätten genom att välja **Leveranssätt** i fliken **Inställningar** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="da133-156">You can see the configured modes of delivery by selecting **Modes of delivery** from the **Set up** tab on the Action Pane.</span></span>  

<span data-ttu-id="da133-157">Om du vill ändra eller lägga till ett leveranssätt följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="da133-157">To change or add a mode of delivery, follow these steps.</span></span>

1. <span data-ttu-id="da133-158">I navigeringsfönstret, gå till **Moduler \> Lagerhantering \> Leveranssätt**.</span><span class="sxs-lookup"><span data-stu-id="da133-158">In the navigation pane, go to **Modules \> Inventory management \> Modes of delivery**.</span></span>
1. <span data-ttu-id="da133-159">I åtgärdsfönstret väljer du **Ny** om du vill skapa ett nytt leveranssätt, eller också väljer du ett befintligt läge.</span><span class="sxs-lookup"><span data-stu-id="da133-159">On the Action Pane, select **New** to create a new mode of delivery, or select an existing mode.</span></span>
1. <span data-ttu-id="da133-160">I avsnittet **butikskanaler**, välj **lägg till rad** om du vill lägga till kanalen.</span><span class="sxs-lookup"><span data-stu-id="da133-160">In the **Retail channels** section, select **Add line** to add the channel.</span></span> <span data-ttu-id="da133-161">Lägga till kanaler med hjälp av organisationsnoder istället för att lägga till varje kanal individuellt kan lägga till kanaler effektivare.</span><span class="sxs-lookup"><span data-stu-id="da133-161">Adding channels using organization nodes instead of adding each channel individually can streamline adding channels.</span></span>

<span data-ttu-id="da133-162">I bilden nedan visas ett exempel på ett leveranssätt.</span><span class="sxs-lookup"><span data-stu-id="da133-162">The following image shows an example of a mode of delivery.</span></span>

![Ställ in leveranssätt](media/channel-setup-retail-7.png)

### <a name="set-up-incomeexpense-account"></a><span data-ttu-id="da133-164">Ställ in intäkts-/utgiftskonto</span><span class="sxs-lookup"><span data-stu-id="da133-164">Set up income/expense account</span></span>

<span data-ttu-id="da133-165">Så här ställer du in intäkts-/utgiftskonto.</span><span class="sxs-lookup"><span data-stu-id="da133-165">To set up income/expense account, follow these steps.</span></span>

1. <span data-ttu-id="da133-166">I åtgärdsfönstret väljer du fliken **Inställningar** och sedan **Intäkts-/utgiftskonto**.</span><span class="sxs-lookup"><span data-stu-id="da133-166">On the Action Pane, select the **Set Up** tab, and then select **Income/Expense account**.</span></span>
1. <span data-ttu-id="da133-167">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="da133-167">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="da133-168">Under **Namn**, ange ett namn.</span><span class="sxs-lookup"><span data-stu-id="da133-168">Under **Name**, enter a name.</span></span>
1. <span data-ttu-id="da133-169">Under **Söknamn**, ange ett söknamn.</span><span class="sxs-lookup"><span data-stu-id="da133-169">Under **Search name**, enter a search name.</span></span>
1. <span data-ttu-id="da133-170">Under **kontotyp**, ange kontotypen.</span><span class="sxs-lookup"><span data-stu-id="da133-170">Under **Account type**, enter the account type.</span></span>
1. <span data-ttu-id="da133-171">Ange text för **meddelanderad 1**, **meddelanderad 2**, **följesedeltext 1** och **följesedeltext 2** efter behov.</span><span class="sxs-lookup"><span data-stu-id="da133-171">Enter text for **Message line 1**, **Message line 2**, **Slip text 1**, and **Slip text 2** as needed.</span></span>
1. <span data-ttu-id="da133-172">Under **bokföring**, ange bokföringsinformation.</span><span class="sxs-lookup"><span data-stu-id="da133-172">Under **Posting**, enter posting information.</span></span>
1. <span data-ttu-id="da133-173">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="da133-173">On the Action Pane, select **Save**.</span></span>

<span data-ttu-id="da133-174">I följande bild visas ett exempel på ett intäkts-/utgiftskonto.</span><span class="sxs-lookup"><span data-stu-id="da133-174">The following image shows an example of an income/expense account.</span></span>

![Ställ in intäkts-/utgiftskonton](media/channel-setup-retail-8.png)

### <a name="set-up-sections"></a><span data-ttu-id="da133-176">Ställ in avsnitt</span><span class="sxs-lookup"><span data-stu-id="da133-176">Set up sections</span></span>

<span data-ttu-id="da133-177">Så här ställer du in avsnitt.</span><span class="sxs-lookup"><span data-stu-id="da133-177">To set up sections, follow these steps.</span></span>

1. <span data-ttu-id="da133-178">I åtgärdsfönstret väljer du fliken **Inställningar** och väljer sedan **Avsnitt**.</span><span class="sxs-lookup"><span data-stu-id="da133-178">On the Action Pane, select the **Set Up** tab and click **Sections**.</span></span>
1. <span data-ttu-id="da133-179">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="da133-179">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="da133-180">Under **avsnittsnummer**, ange ett avsnittsnummer.</span><span class="sxs-lookup"><span data-stu-id="da133-180">Under **Section number**, enter a section number.</span></span>
1. <span data-ttu-id="da133-181">Under **beskrivning** ange en beskrivning.</span><span class="sxs-lookup"><span data-stu-id="da133-181">Under **Description**, enter a description.</span></span>
1. <span data-ttu-id="da133-182">Under **avsnittsstorlek**, ange en avsnittsstorlek.</span><span class="sxs-lookup"><span data-stu-id="da133-182">Under **Section size**, enter a section size.</span></span>
1. <span data-ttu-id="da133-183">Konfigurera ytterligare inställningar för **allmän** och **försäljningsstatistik** efter behov.</span><span class="sxs-lookup"><span data-stu-id="da133-183">Configure additional settings for **General** and **Sales statistics** as needed.</span></span>
1. <span data-ttu-id="da133-184">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="da133-184">On the Action Pane, select **Save**.</span></span>

### <a name="set-up-a-fulfillment-group-assignment"></a><span data-ttu-id="da133-185">Ange tilldelning av uppfyllelsegrupp</span><span class="sxs-lookup"><span data-stu-id="da133-185">Set up a fulfillment group assignment</span></span>

<span data-ttu-id="da133-186">Så här ställer du in en tilldelning av uppfyllelsegrupp.</span><span class="sxs-lookup"><span data-stu-id="da133-186">To set up a fulfillment group assignment, follow these steps.</span></span>

1. <span data-ttu-id="da133-187">I åtgärdsfönstret väljer du fliken **Inställningar** och sedan **Tilldelning av uppfyllelsegrupp**.</span><span class="sxs-lookup"><span data-stu-id="da133-187">On the Action Pane, select the **Set up** tab, then select **Fulfillment group assignment**.</span></span>
1. <span data-ttu-id="da133-188">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="da133-188">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="da133-189">I listrutan **uppfyllelsegrupp** väljer du en uppfyllelsegrupp.</span><span class="sxs-lookup"><span data-stu-id="da133-189">In the **Fulfillment group** drop-down list, select a fulfillment group.</span></span>
1. <span data-ttu-id="da133-190">I listrutan **Beskrivning**, ange en beskrivning.</span><span class="sxs-lookup"><span data-stu-id="da133-190">In the **Description** drop-down list, enter a description.</span></span>
1. <span data-ttu-id="da133-191">Klicka på **Spara** i åtgärdsfönstret</span><span class="sxs-lookup"><span data-stu-id="da133-191">On the Action Pane, select **Save**</span></span>

<span data-ttu-id="da133-192">I bilden nedan visas ett exempel på en inställning av tilldelning av uppfyllelsegrupp.</span><span class="sxs-lookup"><span data-stu-id="da133-192">The following image shows an example of a fulfillment group assignment setup.</span></span>

![Ange tilldelning av uppfyllelsegrupp](media/channel-setup-retail-9.png)

### <a name="set-up-safes"></a><span data-ttu-id="da133-194">Ställ in kassaskåp</span><span class="sxs-lookup"><span data-stu-id="da133-194">Set up safes</span></span>

<span data-ttu-id="da133-195">Så här ställer du in kassaskåp.</span><span class="sxs-lookup"><span data-stu-id="da133-195">To set up safes, follow these steps.</span></span>

1. <span data-ttu-id="da133-196">I åtgärdsfönstret väljer du fliken **Inställningar** och klickar sedan på **Kassaskåp**.</span><span class="sxs-lookup"><span data-stu-id="da133-196">On the Action Pane, select the **Set Up** tab and click **Safes**.</span></span>
1. <span data-ttu-id="da133-197">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="da133-197">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="da133-198">Ange ett namn på kassaskåp.</span><span class="sxs-lookup"><span data-stu-id="da133-198">Enter a name for the safe.</span></span>
1. <span data-ttu-id="da133-199">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="da133-199">On the Action Pane, select **Save**.</span></span>

### <a name="ensure-unique-transaction-ids"></a><span data-ttu-id="da133-200">Säkerställa unika transaktions-ID</span><span class="sxs-lookup"><span data-stu-id="da133-200">Ensure unique transaction IDs</span></span>

<span data-ttu-id="da133-201">Från och med Commerce-versionen 10.0.18 genereras transaktions-ID för kassan (POS) sekventiellt och inkluderar följande delar:</span><span class="sxs-lookup"><span data-stu-id="da133-201">As of the Commerce version 10.0.18 , transaction IDs generated for the point of sale (POS) are sequential and include the following parts:</span></span>

- <span data-ttu-id="da133-202">En fast del, som utgör en sammanslagning av butiks-ID och terminal-ID.</span><span class="sxs-lookup"><span data-stu-id="da133-202">A fixed part, which is a concatenation of store ID and terminal ID.</span></span> 
- <span data-ttu-id="da133-203">En sekventiell del som är en nummerserie.</span><span class="sxs-lookup"><span data-stu-id="da133-203">A sequential part, which is a number sequence.</span></span> 

<span data-ttu-id="da133-204">Mer specifikt är formatet *{store}-{terminal}-{numbersequence}*.</span><span class="sxs-lookup"><span data-stu-id="da133-204">Specifically, the format is *{store}-{terminal}-{numbersequence}*.</span></span> 

<span data-ttu-id="da133-205">Eftersom transaktions-ID:n kan skapas i offline- och onlinelägen har det hänt att instanser med dubbletter av transaktions-ID:n skapas.</span><span class="sxs-lookup"><span data-stu-id="da133-205">Because transaction IDs can be generated in offline and online modes, there have been instances of duplicate transaction IDs being generated.</span></span> <span data-ttu-id="da133-206">Att undvika dubbletter av transaktions-ID:er kräver omfattande manuella datakorrigeringar.</span><span class="sxs-lookup"><span data-stu-id="da133-206">Eliminating duplicate transaction IDs requires a lot of manual data fixing.</span></span> 

<span data-ttu-id="da133-207">I och med Commerce-version 10.0.19 har transaktions-ID-formatet uppdaterats i syfte att ta bort den sekventiella delen, och använder istället ett 13-siffrigt nummer som genererats genom beräkning av tiden i millisekunder sedan 1970.</span><span class="sxs-lookup"><span data-stu-id="da133-207">With Commerce version 10.0.19, the transaction ID format has been updated to remove the sequential part and instead uses a 13-digit number generated by calculating the time in milliseconds since 1970.</span></span> <span data-ttu-id="da133-208">Genom denna ändring blir det nya transaktions-ID-formatet *{store}-{terminal}-{millisecondsSince1970}*.</span><span class="sxs-lookup"><span data-stu-id="da133-208">With this change, the new transaction ID format is *{store}-{terminal}-{millisecondsSince1970}*.</span></span> <span data-ttu-id="da133-209">Genom denna uppdatering blir transaktions-ID:t icke-sekventiellt och säkerställer att transaktions-ID:n alltid blir unika.</span><span class="sxs-lookup"><span data-stu-id="da133-209">This update makes the transaction ID non-sequential and ensures that transaction IDs are always unique.</span></span> 

> [!NOTE]
> <span data-ttu-id="da133-210">Transaktions-ID:n är endast avsedda för interna system, varför de måste inte vara löpande.</span><span class="sxs-lookup"><span data-stu-id="da133-210">Transaction IDs are meant for internal system use only, so they are not required to be sequential.</span></span> <span data-ttu-id="da133-211">Många länder kräver dock att inleverans-ID:n är sekventiella.</span><span class="sxs-lookup"><span data-stu-id="da133-211">However, many countries require receipt IDs to be sequential.</span></span>

<span data-ttu-id="da133-212">Den nya formatfunktionen för transaktions-ID kan aktiveras från arbetsytan **Funktionshantering**.</span><span class="sxs-lookup"><span data-stu-id="da133-212">The new transaction ID format feature can be enabled from the **Feature management** workspace.</span></span> 

<span data-ttu-id="da133-213">Gör på följande sätt om du vill aktivera användning av nya transaktions-ID:n:</span><span class="sxs-lookup"><span data-stu-id="da133-213">To enable the use of new transaction IDs, follow these steps:</span></span>

1. <span data-ttu-id="da133-214">I Commerce-administrationen går du till **Systemadministration \> Arbetsytor \> Funktionshantering**.</span><span class="sxs-lookup"><span data-stu-id="da133-214">In Commerce headquarters, go to **System administration \> Workspaces \> Feature management**.</span></span>
1. <span data-ttu-id="da133-215">Filtrera fram modulen "Retail och Commerce".</span><span class="sxs-lookup"><span data-stu-id="da133-215">Filter for the "retail and commerce" module.</span></span>
1. <span data-ttu-id="da133-216">Sök efter funktionsnamnet **Aktivera nytt transaktions-ID i syfte att undvika dubbletter av transaktions-ID:n**.</span><span class="sxs-lookup"><span data-stu-id="da133-216">Search for the **Enable new transaction id to avoid duplicate transaction ids** feature name.</span></span>
1. <span data-ttu-id="da133-217">Välj funktionen och sedan **Aktivera nu** i det högra fönstret.</span><span class="sxs-lookup"><span data-stu-id="da133-217">Select the feature, and then select **Enable Now** in the right pane.</span></span>  
1. <span data-ttu-id="da133-218">Gå till **Retail and Commerce \> Retail and Commerce-IT \> Distributionsschema**.</span><span class="sxs-lookup"><span data-stu-id="da133-218">Go to **Retail and Commerce \> Retail and Commerce IT \> Distribution schedule**.</span></span>
1. <span data-ttu-id="da133-219">Kör jobben **1070 Kanalkonfiguration** och **1170 Uppgiftsinspelare för kassa** i syfte att synkronisera den aktiverade funktionen med butikerna.</span><span class="sxs-lookup"><span data-stu-id="da133-219">Run the **1070 Channel configuration** and **1170 POS task recorder** jobs to synchronize the enabled feature to the stores.</span></span>
1. <span data-ttu-id="da133-220">När ändringarna har skickats till butikerna måste kassaterminalerna stängas och öppnas igen för att det nya transaktions-ID-formatet ska kunna användas.</span><span class="sxs-lookup"><span data-stu-id="da133-220">After the changes have been sent to the stores, POS terminals must be closed and reopened to use the new transaction ID format.</span></span> 

> [!NOTE]
> <span data-ttu-id="da133-221">När den nya formatfunktionen för transaktions-ID har aktiverats kan du inte inaktivera funktionen.</span><span class="sxs-lookup"><span data-stu-id="da133-221">After the new transaction ID format feature is enabled, you will not be able to disable this feature.</span></span> <span data-ttu-id="da133-222">Om denna måste inaktiveras kan du kontakta Commerce Support.</span><span class="sxs-lookup"><span data-stu-id="da133-222">If it must be disabled, please contact Commerce Support.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="da133-223">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="da133-223">Additional resources</span></span>

[<span data-ttu-id="da133-224">Översikt över kanaler</span><span class="sxs-lookup"><span data-stu-id="da133-224">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="da133-225">Förutsättningar för kanalinställningar</span><span class="sxs-lookup"><span data-stu-id="da133-225">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="da133-226">Ställ in en onlinekanal</span><span class="sxs-lookup"><span data-stu-id="da133-226">Set up an online channel</span></span>](channel-setup-online.md)

[<span data-ttu-id="da133-227">Ställa in en kundtjänstkanal</span><span class="sxs-lookup"><span data-stu-id="da133-227">Set up a call center channel</span></span>](channel-setup-callcenter.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
