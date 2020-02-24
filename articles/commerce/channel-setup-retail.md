---
title: Ställa in en butikskanal
description: I det här avsnittet beskrivs hur du skapar en ny butikskanal i Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 8ac01f36912fa5e8a09bb4f324ef272cec737aa1
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/01/2020
ms.locfileid: "3002391"
---
# <a name="set-up-a-retail-channel"></a><span data-ttu-id="b65c3-103">Ställa in en butikskanal</span><span class="sxs-lookup"><span data-stu-id="b65c3-103">Set up a retail channel</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="b65c3-104">I det här avsnittet beskrivs hur du skapar en ny butikskanal i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="b65c3-104">This topic describes how to create a new retail channel in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="b65c3-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="b65c3-105">Overview</span></span>

<span data-ttu-id="b65c3-106">Dynamics 365 Commerce stöder flera butikskanaler.</span><span class="sxs-lookup"><span data-stu-id="b65c3-106">Dynamics 365 Commerce supports multiple retail channels.</span></span> <span data-ttu-id="b65c3-107">Dessa kanaler inkluderar onlinebutiker, kundtjänst och butiker (kallas också fysiska butiker).</span><span class="sxs-lookup"><span data-stu-id="b65c3-107">These retail channels include online stores, call centers, and retail stores (also known as brick-and-mortar stores).</span></span> <span data-ttu-id="b65c3-108">Varje butikskanal kan ha egna betalningsmetoder, prisgrupper, kassaregister (POS), intäkts- och utgiftskonton och personal.</span><span class="sxs-lookup"><span data-stu-id="b65c3-108">Each retail store channel can have its own payment methods, price groups, point of sale (POS) registers, income accounts and expense accounts, and staff.</span></span> <span data-ttu-id="b65c3-109">Du måste ställa in alla dessa element innan du kan skapa en butikskanel.</span><span class="sxs-lookup"><span data-stu-id="b65c3-109">You must set up all of these elements before you can create a retail store channel.</span></span> 

<span data-ttu-id="b65c3-110">Innan du skapar en butikskanal ska du kontrollera att du följer [kanalförutsättningarna](channels-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="b65c3-110">Before a retail channel is created, ensure you follow the [channel prerequisites](channels-prerequisites.md).</span></span>

## <a name="create-and-configure-a-new-retail-channel"></a><span data-ttu-id="b65c3-111">Skapa och konfigurera en ny butikskanal</span><span class="sxs-lookup"><span data-stu-id="b65c3-111">Create and configure a new retail channel</span></span>

1. <span data-ttu-id="b65c3-112">I navigeringsfönstret, gå till **Moduler \> Kanaler \> Butiker \> Alla butiker**.</span><span class="sxs-lookup"><span data-stu-id="b65c3-112">In the navigation pane, go to **Modules \> Channels \> Stores \> All stores**.</span></span>
1. <span data-ttu-id="b65c3-113">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="b65c3-113">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="b65c3-114">I fältet **Namn** ange ett namn på den nya kanalen.</span><span class="sxs-lookup"><span data-stu-id="b65c3-114">In the **Name** field, provide a name for the new channel.</span></span>
1. <span data-ttu-id="b65c3-115">Markera ett unikt butiksnummer i fältet **Butiksnummer**.</span><span class="sxs-lookup"><span data-stu-id="b65c3-115">In the **Store number** field, provide a unique store number.</span></span> <span data-ttu-id="b65c3-116">Numret kan vara alfanumeriskt och får innehålla högst 10 tecken.</span><span class="sxs-lookup"><span data-stu-id="b65c3-116">The number can be alphanumeric with a maximum of 10 characters.</span></span>
1. <span data-ttu-id="b65c3-117">I listrutan **juridisk person** anger du den relevanta juridiska personen.</span><span class="sxs-lookup"><span data-stu-id="b65c3-117">In the **Legal entity** drop-down list, enter the appropriate legal entity.</span></span>
1. <span data-ttu-id="b65c3-118">I listrutan **lagerställe** anger du lämpligt lagerställe.</span><span class="sxs-lookup"><span data-stu-id="b65c3-118">In the **Warehouse** drop-down list, enter the appropriate warehouse.</span></span>
1. <span data-ttu-id="b65c3-119">Välj lämplig tidszon i fältet **Butikens tidszon** .</span><span class="sxs-lookup"><span data-stu-id="b65c3-119">In the **Store time zone** field, select the appropriate time zone.</span></span>
1. <span data-ttu-id="b65c3-120">I listrutan **Momsgrupp**, välj en lämplig momsgrupp för butiken.</span><span class="sxs-lookup"><span data-stu-id="b65c3-120">In the **Sales tax group** drop-down list, select an appropriate sales tax group for the store.</span></span>
1. <span data-ttu-id="b65c3-121">Välj lämplig valuta i fältet **valuta**.</span><span class="sxs-lookup"><span data-stu-id="b65c3-121">In the **Currency** field, select the appropriate currency.</span></span>
1. <span data-ttu-id="b65c3-122">I fältet **Kundens adressbok** ange en giltig adressbok.</span><span class="sxs-lookup"><span data-stu-id="b65c3-122">In the **Customer address book** field, provide a valid address book.</span></span>
1. <span data-ttu-id="b65c3-123">I fältet **Standardkund** ange en giltig standardkund.</span><span class="sxs-lookup"><span data-stu-id="b65c3-123">In the **Default customer** field, provide a valid default customer.</span></span>
1. <span data-ttu-id="b65c3-124">I fältet **Funktionsprofil** välj en funktionsprofil om tillämpligt.</span><span class="sxs-lookup"><span data-stu-id="b65c3-124">In the **Functionality profile** field, select a functionality profile if applicable.</span></span>
1. <span data-ttu-id="b65c3-125">I fältet **Meddelandeprofil för e-post** ange en giltig meddelandeprofil för e-post.</span><span class="sxs-lookup"><span data-stu-id="b65c3-125">In the **Email notification profile** field, provide a valid email notification profile.</span></span>
1. <span data-ttu-id="b65c3-126">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="b65c3-126">On the action pane, select **Save**.</span></span>

<span data-ttu-id="b65c3-127">Följande bild visar hur en ny butikskanal skapas.</span><span class="sxs-lookup"><span data-stu-id="b65c3-127">The following image shows the creation of a new retail channel.</span></span>

![Ny butikskanal](media/channel-setup-retail-1.png)

<span data-ttu-id="b65c3-129">I bilden nedan visas ett exempel på butikskanal.</span><span class="sxs-lookup"><span data-stu-id="b65c3-129">The following image shows an example retail channel.</span></span>

![Exempel på butikskanal](media/channel-setup-retail-2.png)

## <a name="other-settings"></a><span data-ttu-id="b65c3-131">Andra inställningar</span><span class="sxs-lookup"><span data-stu-id="b65c3-131">Other settings</span></span>

<span data-ttu-id="b65c3-132">Det finns flera andra inställningar som kan ställas in i avsnitten **Utdrag/stängning** och **Diverse**, baserat på butikens behov.</span><span class="sxs-lookup"><span data-stu-id="b65c3-132">There are numerous other optional settings that can be set in the **Statement/closing** and **Miscellaneous** sections, based on the needs of the retail store.</span></span>

<span data-ttu-id="b65c3-133">Se även [Skärmlayouter för kassan (POS)](https://docs.microsoft.com/en-us/dynamics365/retail/pos-screen-layouts?toc=/dynamics365/commerce/toc.json) för information om att ställa in standardskärmlayouten i avsnittet **skärmlayout** och [Konfigurera och installera Retail Hardware Station](https://docs.microsoft.com/en-us/dynamics365/retail/retail-hardware-station-configuration-installation) för inställningsinformation om avsnittet **Maskinvarustationer**.</span><span class="sxs-lookup"><span data-stu-id="b65c3-133">In addition, see [Screen layouts for the point of sale (POS)](https://docs.microsoft.com/en-us/dynamics365/retail/pos-screen-layouts?toc=/dynamics365/commerce/toc.json) for information on setting up the default screen layout in the **Screen layout** section and [Configure and install Retail hardware station](https://docs.microsoft.com/en-us/dynamics365/retail/retail-hardware-station-configuration-installation) for setup information about the **Hardware stations** section.</span></span>

<span data-ttu-id="b65c3-134">I bilden nedan visas ett exempel på konfiguration av butikskanal.</span><span class="sxs-lookup"><span data-stu-id="b65c3-134">The following image shows an example retail channel setup configuration.</span></span>

![Exempel på butikskanalkonfiguration](media/channel-setup-retail-3.png)

## <a name="additional-channel-set-up"></a><span data-ttu-id="b65c3-136">Konfiguration av ytterligare kanal</span><span class="sxs-lookup"><span data-stu-id="b65c3-136">Additional channel set up</span></span>

<span data-ttu-id="b65c3-137">Det finns ytterligare objekt som måste konfigureras för en kanal som kan hittas i **åtgärdsfönstret** under avsnittet **inställningar**.</span><span class="sxs-lookup"><span data-stu-id="b65c3-137">There are additional items that need to be set up for a channel that can be found on the **Action pane** under the **Set up** section.</span></span>

<span data-ttu-id="b65c3-138">Ytterligare uppgifter som krävs för online-kanalkonfigurering inkluderar inställning av betalningsmetoder, kontantdeklaration, leveranssätt, inkomst/utgiftskonto, avsnitt, tilldelning av uppfyllelsegrupp och kassaskåp.</span><span class="sxs-lookup"><span data-stu-id="b65c3-138">Additional tasks required for online channel setup include setting up payment methods, cash declaration, modes of delivery, income/expense account, sections, the fulfillment group assignment, and safes.</span></span>

<span data-ttu-id="b65c3-139">Följande bild visar olika ytterligare alternativ för inställning av butikskanaler på fliken **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="b65c3-139">The following image shows various additional retail channel setup options on the **Set up** tab.</span></span>

![Ställ in en kanal](media/channel-setup-retail-4.png)

### <a name="set-up-payment-methods"></a><span data-ttu-id="b65c3-141">Ange betalningsmetoder</span><span class="sxs-lookup"><span data-stu-id="b65c3-141">Set up payment methods</span></span>

<span data-ttu-id="b65c3-142">Om du vill ställa in betalningsmetoder följer du dessa steg för varje betalningstyp som stöds på den här kanalen.</span><span class="sxs-lookup"><span data-stu-id="b65c3-142">To set up payment methods, for each payment type supported on this channel follow these steps.</span></span>

1. <span data-ttu-id="b65c3-143">I åtgärdsfönstret, välj fliken **Inställningar** och välj sedan **betalningssätt**.</span><span class="sxs-lookup"><span data-stu-id="b65c3-143">On the action pane, select the **Set Up** tab, then select **Payment methods**.</span></span>
1. <span data-ttu-id="b65c3-144">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="b65c3-144">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="b65c3-145">I navigeringsfönstret väljer du önskad betalningsmetod.</span><span class="sxs-lookup"><span data-stu-id="b65c3-145">In the navigation pane, select a desired payment method.</span></span>
1. <span data-ttu-id="b65c3-146">I avsnittet **Allmänt** anger du ett **åtgärdsnamn** och konfigurerar andra önskade inställningar.</span><span class="sxs-lookup"><span data-stu-id="b65c3-146">In the **General** section, provide an **Operation name** and configure any other desired settings.</span></span>
1. <span data-ttu-id="b65c3-147">Konfigurera eventuella ytterligare inställningar efter behov för betalningstypen.</span><span class="sxs-lookup"><span data-stu-id="b65c3-147">Configure any additional settings as required for the payment type.</span></span>
1. <span data-ttu-id="b65c3-148">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="b65c3-148">On the action pane, select **Save**.</span></span>

<span data-ttu-id="b65c3-149">I bilden nedan visas ett exempel på en kontantbetalningsmetod.</span><span class="sxs-lookup"><span data-stu-id="b65c3-149">The following image shows an example of a cash payment method.</span></span>

![Exempel på betalningsmetoder](media/channel-setup-retail-5.png)

### <a name="set-up-cash-declaration"></a><span data-ttu-id="b65c3-151">Inställningar för kontantavstämning</span><span class="sxs-lookup"><span data-stu-id="b65c3-151">Set up cash declaration</span></span>

1. <span data-ttu-id="b65c3-152">I åtgärdsfönstret, välj fliken **Inställningar** och välj sedan **Kontantavstämning**.</span><span class="sxs-lookup"><span data-stu-id="b65c3-152">On the action pane, select the **Set Up** tab, and then select **Cash declaration**.</span></span>
1. <span data-ttu-id="b65c3-153">I åtgärdsfönstret, välj **Ny** och skapa sedan alla beteckningar för **mynt** och **anteckning** som kan användas.</span><span class="sxs-lookup"><span data-stu-id="b65c3-153">On the action pane, select **New**, and then create all **Coin** and **Note** denominations that are applicable.</span></span>

<span data-ttu-id="b65c3-154">I bilden nedan visas ett exempel på en kontantavstämning.</span><span class="sxs-lookup"><span data-stu-id="b65c3-154">The following image shows an example of a cash declaration.</span></span>

![Inställningar för kontantavstämningar](media/channel-setup-retail-6.png)

### <a name="set-up-modes-of-delivery"></a><span data-ttu-id="b65c3-156">Ställ in leveranssätt</span><span class="sxs-lookup"><span data-stu-id="b65c3-156">Set up modes of delivery</span></span>

<span data-ttu-id="b65c3-157">Du kan visa de konfigurerade leveranssätten genom att välja **Leveranssätt** från fliken **Inställningar** i **Åtgärdsfönstret**.</span><span class="sxs-lookup"><span data-stu-id="b65c3-157">You can see the configured modes of delivery by selecting **Modes of delivery** from the **Set up** tab on the **Action pane**.</span></span>  

<span data-ttu-id="b65c3-158">Om du vill ändra eller lägga till ett leveranssätt följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="b65c3-158">To change or add a mode of delivery, follow these steps.</span></span>

1. <span data-ttu-id="b65c3-159">I navigeringsfönstret, gå till **Moduler \> Lagerhantering \> Leveranssätt**.</span><span class="sxs-lookup"><span data-stu-id="b65c3-159">In the navigation pane, go to **Modules \> Inventory management \> Modes of delivery**.</span></span>
1. <span data-ttu-id="b65c3-160">I åtgärdsfönstret, välj **Ny** om du vill skapa ett nytt leverans sätt, eller välj ett befintligt läge.</span><span class="sxs-lookup"><span data-stu-id="b65c3-160">On the action pane, select **New** to create a new mode of delivery, or select an existing mode.</span></span>
1. <span data-ttu-id="b65c3-161">I avsnittet **butikskanaler**, välj **lägg till rad** om du vill lägga till kanalen.</span><span class="sxs-lookup"><span data-stu-id="b65c3-161">In the **Retail channels** section, select **Add line** to add the channel.</span></span> <span data-ttu-id="b65c3-162">Lägga till kanaler med hjälp av organisationsnoder istället för att lägga till varje kanal individuellt kan lägga till kanaler effektivare.</span><span class="sxs-lookup"><span data-stu-id="b65c3-162">Adding channels using organization nodes instead of adding each channel individually can streamline adding channels.</span></span>

<span data-ttu-id="b65c3-163">I bilden nedan visas ett exempel på ett leveranssätt.</span><span class="sxs-lookup"><span data-stu-id="b65c3-163">The following image shows an example of a mode of delivery.</span></span>

![Ställ in leveranssätt](media/channel-setup-retail-7.png)

### <a name="set-up-incomeexpense-account"></a><span data-ttu-id="b65c3-165">Ställ in intäkts-/utgiftskonto</span><span class="sxs-lookup"><span data-stu-id="b65c3-165">Set up income/expense account</span></span>

<span data-ttu-id="b65c3-166">Så här ställer du in intäkts-/utgiftskonto.</span><span class="sxs-lookup"><span data-stu-id="b65c3-166">To set up income/expense account, follow these steps.</span></span>

1. <span data-ttu-id="b65c3-167">I åtgärdsfönstret, välj fliken **Inställningar** och välj sedan **intäkts-/utgiftskonto**.</span><span class="sxs-lookup"><span data-stu-id="b65c3-167">On the action pane, select the **Set Up** tab, and then select **Income/Expense account**.</span></span>
1. <span data-ttu-id="b65c3-168">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="b65c3-168">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="b65c3-169">Under **Namn**, ange ett namn.</span><span class="sxs-lookup"><span data-stu-id="b65c3-169">Under **Name**, enter a name.</span></span>
1. <span data-ttu-id="b65c3-170">Under **Söknamn**, ange ett söknamn.</span><span class="sxs-lookup"><span data-stu-id="b65c3-170">Under **Search name**, enter a search name.</span></span>
1. <span data-ttu-id="b65c3-171">Under **kontotyp**, ange kontotypen.</span><span class="sxs-lookup"><span data-stu-id="b65c3-171">Under **Account type**, enter the account type.</span></span>
1. <span data-ttu-id="b65c3-172">Ange text för **meddelanderad 1**, **meddelanderad 2**, **följesedeltext 1** och **följesedeltext 2** efter behov.</span><span class="sxs-lookup"><span data-stu-id="b65c3-172">Enter text for **Message line 1**, **Message line 2**, **Slip text 1**, and **Slip text 2** as needed.</span></span>
1. <span data-ttu-id="b65c3-173">Under **bokföring**, ange bokföringsinformation.</span><span class="sxs-lookup"><span data-stu-id="b65c3-173">Under **Posting**, enter posting information.</span></span>
1. <span data-ttu-id="b65c3-174">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="b65c3-174">On the action pane, select **Save**.</span></span>

<span data-ttu-id="b65c3-175">I följande bild visas ett exempel på ett intäkts-/utgiftskonto.</span><span class="sxs-lookup"><span data-stu-id="b65c3-175">The following image shows an example of an income/expense account.</span></span>

![Ställ in intäkts-/utgiftskonton](media/channel-setup-retail-8.png)

### <a name="set-up-sections"></a><span data-ttu-id="b65c3-177">Ställ in avsnitt</span><span class="sxs-lookup"><span data-stu-id="b65c3-177">Set up sections</span></span>

<span data-ttu-id="b65c3-178">Så här ställer du in avsnitt.</span><span class="sxs-lookup"><span data-stu-id="b65c3-178">To set up sections, follow these steps.</span></span>

1. <span data-ttu-id="b65c3-179">I åtgärdsfönstret, välj fliken **Inställningar** och välj sedan **avsnitt**.</span><span class="sxs-lookup"><span data-stu-id="b65c3-179">On the action pane, select the **Set Up** tab and click **Sections**.</span></span>
1. <span data-ttu-id="b65c3-180">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="b65c3-180">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="b65c3-181">Under **avsnittsnummer**, ange ett avsnittsnummer.</span><span class="sxs-lookup"><span data-stu-id="b65c3-181">Under **Section number**, enter a section number.</span></span>
1. <span data-ttu-id="b65c3-182">Under **beskrivning** ange en beskrivning.</span><span class="sxs-lookup"><span data-stu-id="b65c3-182">Under **Description**, enter a description.</span></span>
1. <span data-ttu-id="b65c3-183">Under **avsnittsstorlek**, ange en avsnittsstorlek.</span><span class="sxs-lookup"><span data-stu-id="b65c3-183">Under **Section size**, enter a section size.</span></span>
1. <span data-ttu-id="b65c3-184">Konfigurera ytterligare inställningar för **allmän** och **försäljningsstatistik** efter behov.</span><span class="sxs-lookup"><span data-stu-id="b65c3-184">Configure additional settings for **General** and **Sales statistics** as needed.</span></span>
1. <span data-ttu-id="b65c3-185">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="b65c3-185">On the action pane, select **Save**.</span></span>

### <a name="set-up-a-fulfillment-group-assignment"></a><span data-ttu-id="b65c3-186">Ange tilldelning av uppfyllelsegrupp</span><span class="sxs-lookup"><span data-stu-id="b65c3-186">Set up a fulfillment group assignment</span></span>

<span data-ttu-id="b65c3-187">Så här ställer du in en tilldelning av uppfyllelsegrupp.</span><span class="sxs-lookup"><span data-stu-id="b65c3-187">To set up a fulfillment group assignment, follow these steps.</span></span>

1. <span data-ttu-id="b65c3-188">I åtgärdsfönstret, välj fliken **Inställningar** och välj sedan **Tilldelning av uppfyllelsegrupp**.</span><span class="sxs-lookup"><span data-stu-id="b65c3-188">On the action pane, select the **Set up** tab, then select **Fulfillment group assignment**.</span></span>
1. <span data-ttu-id="b65c3-189">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="b65c3-189">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="b65c3-190">I listrutan **uppfyllelsegrupp** väljer du en uppfyllelsegrupp.</span><span class="sxs-lookup"><span data-stu-id="b65c3-190">In the **Fulfillment group** drop-down list, select a fulfillment group.</span></span>
1. <span data-ttu-id="b65c3-191">I listrutan **Beskrivning**, ange en beskrivning.</span><span class="sxs-lookup"><span data-stu-id="b65c3-191">In the **Description** drop-down list, enter a description.</span></span>
1. <span data-ttu-id="b65c3-192">Klicka på **Spara** i åtgärdsfönstret</span><span class="sxs-lookup"><span data-stu-id="b65c3-192">On the action pane, select **Save**</span></span>

<span data-ttu-id="b65c3-193">I bilden nedan visas ett exempel på en inställning av tilldelning av uppfyllelsegrupp.</span><span class="sxs-lookup"><span data-stu-id="b65c3-193">The following image shows an example of a fulfillment group assignment setup.</span></span>

![Ange tilldelning av uppfyllelsegrupp](media/channel-setup-retail-9.png)

### <a name="set-up-safes"></a><span data-ttu-id="b65c3-195">Ställ in kassaskåp</span><span class="sxs-lookup"><span data-stu-id="b65c3-195">Set up safes</span></span>

<span data-ttu-id="b65c3-196">Så här ställer du in kassaskåp.</span><span class="sxs-lookup"><span data-stu-id="b65c3-196">To set up safes, follow these steps.</span></span>

1. <span data-ttu-id="b65c3-197">I åtgärdsfönstret, välj fliken **Inställningar** och välj sedan **Kassaskåp**.</span><span class="sxs-lookup"><span data-stu-id="b65c3-197">On the action pane, select the **Set Up** tab and click **Safes**.</span></span>
1. <span data-ttu-id="b65c3-198">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="b65c3-198">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="b65c3-199">Ange ett namn på kassaskåp.</span><span class="sxs-lookup"><span data-stu-id="b65c3-199">Enter a name for the safe.</span></span>
1. <span data-ttu-id="b65c3-200">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="b65c3-200">On the action pane, select **Save**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b65c3-201">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="b65c3-201">Additional resources</span></span>

[<span data-ttu-id="b65c3-202">Översikt över kanaler</span><span class="sxs-lookup"><span data-stu-id="b65c3-202">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="b65c3-203">Förutsättningar för att ställa in kanaler</span><span class="sxs-lookup"><span data-stu-id="b65c3-203">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="b65c3-204">Ställ in en onlinekanal</span><span class="sxs-lookup"><span data-stu-id="b65c3-204">Set up an online channel</span></span>](channel-setup-online.md)

[<span data-ttu-id="b65c3-205">Ställa in en kundtjänstkanal</span><span class="sxs-lookup"><span data-stu-id="b65c3-205">Set up a call center channel</span></span>](channel-setup-callcenter.md)

