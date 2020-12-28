---
title: Ställa in en kundtjänstkanal
description: I det här avsnittet beskrivs hur du skapar en ny kundtjänstkanal i Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 03/13/2020
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
ms.openlocfilehash: 3f8c47c00b920dae01213d1d241ac8ee6a18d4e3
ms.sourcegitcommit: 4c6d31f3ebd88212d3d1497a4bba9c64c5300444
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/24/2020
ms.locfileid: "4415984"
---
# <a name="set-up-a-call-center-channel"></a><span data-ttu-id="1c62b-103">Ställa in en kundtjänstkanal</span><span class="sxs-lookup"><span data-stu-id="1c62b-103">Set up a call center channel</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="1c62b-104">I det här avsnittet beskrivs hur du skapar en ny kundtjänstkanal i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="1c62b-104">This topic describes how to create a new call center channel in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="1c62b-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="1c62b-105">Overview</span></span>


<span data-ttu-id="1c62b-106">I Dynamics 365 Commerce, är kundtjänst en typ av Commerce-kanal som kan definieras i programmet.</span><span class="sxs-lookup"><span data-stu-id="1c62b-106">In Dynamics 365 Commerce, a call center is a type of Commerce channel that can be defined in the application.</span></span> <span data-ttu-id="1c62b-107">Om du definierar en kanal för dina kundtjänstenheter kan systemet koppla specifika data och orderbearbetningsstandard till försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="1c62b-107">Defining a channel for your call center entities allows the system to tie specific data and order processing defaults to sales orders.</span></span> <span data-ttu-id="1c62b-108">Ett företag kan definiera flera kundtjänstkanaler i Commerce, men det är viktigt att tänka på att en enskild användare bara kan länkas till en kundtjänstkanal.</span><span class="sxs-lookup"><span data-stu-id="1c62b-108">While a company can define multiple call center channels in Commerce, it is important to note that an individual user may only be linked to one call center channel.</span></span> 

<span data-ttu-id="1c62b-109">Innan du skapar en ny kundtjänstkanal måste du kontrollera att du har slutfört [Förutsättningar för att ställa in kanaler](channels-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="1c62b-109">Before you create a new call center channel, ensure that you have completed the [Channel setup prerequisites](channels-prerequisites.md).</span></span>

## <a name="create-and-configure-a-new-call-center-channel"></a><span data-ttu-id="1c62b-110">Skapa och konfigurera en ny kundtjänstkanal</span><span class="sxs-lookup"><span data-stu-id="1c62b-110">Create and configure a new call center channel</span></span>

<span data-ttu-id="1c62b-111">Följ stegen nedan om du vill skapa och konfigurera en ny kundtjänstkanal.</span><span class="sxs-lookup"><span data-stu-id="1c62b-111">To create and configure a new call center channel, follow these steps.</span></span>

1. <span data-ttu-id="1c62b-112">I navigeringsfönstret, gå till **Retail och Commerce \> Kanaler \> Kundtjänster \> Alla kundtjänster**.</span><span class="sxs-lookup"><span data-stu-id="1c62b-112">In the navigation pane, go to **Retail and Commerce \> Channels \> Call centers \> All call centers**.</span></span>
1. <span data-ttu-id="1c62b-113">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="1c62b-113">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="1c62b-114">I fältet **Namn** ange ett namn på den nya kanalen.</span><span class="sxs-lookup"><span data-stu-id="1c62b-114">In the **Name** field, provide a name for the new channel.</span></span>
1. <span data-ttu-id="1c62b-115">Välj lämplig **Juridisk enhet** från listrutan.</span><span class="sxs-lookup"><span data-stu-id="1c62b-115">Select the appropriate **Legal entity** from the drop-down.</span></span>
1. <span data-ttu-id="1c62b-116">Välj lämplig plats för **Lagerställe** från listrutan.</span><span class="sxs-lookup"><span data-stu-id="1c62b-116">Select the appropriate **Warehouse** location from the drop-down.</span></span> <span data-ttu-id="1c62b-117">Den här platsen kommer att användas som standard på försäljningsorder som skapas för den här kundtjänstkanalen, såvida inte andra standardvärden har definierats på kund- eller artikelnivå.</span><span class="sxs-lookup"><span data-stu-id="1c62b-117">This location will be used as the default on sales orders created for this call center channel, unless other defaults have been defined at the customer or item level.</span></span>
1. <span data-ttu-id="1c62b-118">I fältet **Standardkund** ange en giltig standardkund.</span><span class="sxs-lookup"><span data-stu-id="1c62b-118">In the **Default customer** field, provide a valid default customer.</span></span> <span data-ttu-id="1c62b-119">Dessa data används för att hjälpa till att automatiskt fylla i standardvärden när nya kundposter skapas.</span><span class="sxs-lookup"><span data-stu-id="1c62b-119">This data is used to assist in autopopulating defaults when new customer records are created.</span></span> <span data-ttu-id="1c62b-120">När du skapar kundtjänstorder är det inte tillrådligt att skapa order för standardkunden.</span><span class="sxs-lookup"><span data-stu-id="1c62b-120">When creating call center orders, it is not advisable to create orders for the default customer.</span></span>
1. <span data-ttu-id="1c62b-121">I fältet **Meddelandeprofil för e-post** ange en giltig meddelandeprofil för e-post.</span><span class="sxs-lookup"><span data-stu-id="1c62b-121">In the **Email notification profile** field, provide a valid email notification profile.</span></span> <span data-ttu-id="1c62b-122">När order skapas och bearbetas, används e-postprofilen för att utlösa automatiska e-postnotifieringar till kunder med information om deras orderstatus.</span><span class="sxs-lookup"><span data-stu-id="1c62b-122">As call center orders are created and processed, the email notification profile is used to trigger automated email alerts to customers with information about their order status.</span></span>
1. <span data-ttu-id="1c62b-123">Ange informationskoden **prisåsidosättning**.</span><span class="sxs-lookup"><span data-stu-id="1c62b-123">Provide a **Price override** info code.</span></span> <span data-ttu-id="1c62b-124">Du måste skapa en informationskod för denna första.</span><span class="sxs-lookup"><span data-stu-id="1c62b-124">You may need to create an info code for this first.</span></span> <span data-ttu-id="1c62b-125">Den här informations koden anger de orsakskoder som användaren ska uppmanas att välja mellan när funktionen för prisökning används i en kundtjänstorder.</span><span class="sxs-lookup"><span data-stu-id="1c62b-125">This info code provides the set of reason codes that the user will be prompted to choose from when using the price override functionality on a call center order.</span></span>
1. <span data-ttu-id="1c62b-126">Tillhandahåll en informationskod **Spärrkod**.</span><span class="sxs-lookup"><span data-stu-id="1c62b-126">Provide a **Hold code** info code.</span></span> <span data-ttu-id="1c62b-127">Du måste skapa en informationskod för denna första.</span><span class="sxs-lookup"><span data-stu-id="1c62b-127">You may need to create an info code for this first.</span></span> <span data-ttu-id="1c62b-128">Den här informationskoden anger de valfria orsakskoder som användaren ska uppmanas att välja mellan när man spärrar en order.</span><span class="sxs-lookup"><span data-stu-id="1c62b-128">This info code provides the set of optional reason codes that the user will be prompted to choose from when placing an order on hold.</span></span>
1. <span data-ttu-id="1c62b-129">Ange en informationskod **Kredit**.</span><span class="sxs-lookup"><span data-stu-id="1c62b-129">Provide a **Credit** info code.</span></span> <span data-ttu-id="1c62b-130">Du måste skapa en informationskod för denna första.</span><span class="sxs-lookup"><span data-stu-id="1c62b-130">You may need to create an info code for this first.</span></span> <span data-ttu-id="1c62b-131">Den här informationskoden innehåller en uppsättning orsakskoder som användaren kan välja från när du använder funktionen orderkredit i en kundtjänst för att ge diverse återbetalningar till kunden av kundserviceorsaker.</span><span class="sxs-lookup"><span data-stu-id="1c62b-131">This info code provides the set of reason codes that the user can choose from when using the order credit functionality of call center to give misc refunds to the customer for customer service reasons.</span></span>
1. <span data-ttu-id="1c62b-132">Valfritt: ställ in ekonomiska dimensioner på snabbfliken **ekonomiska dimensioner**.</span><span class="sxs-lookup"><span data-stu-id="1c62b-132">Optional: set up financial dimensions on the **Financial dimensions** FastTab.</span></span> <span data-ttu-id="1c62b-133">De dimensioner som anges här kommer att visas som standard på alla försäljningsorder som skapas i den här kundtjänstkanalen.</span><span class="sxs-lookup"><span data-stu-id="1c62b-133">The dimensions entered here will default on any sales order created in this call center channel.</span></span>
1. <span data-ttu-id="1c62b-134">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="1c62b-134">Click **Save**.</span></span>

<span data-ttu-id="1c62b-135">Följande bild visar hur en ny kundtjänstkanal skapas.</span><span class="sxs-lookup"><span data-stu-id="1c62b-135">The following image shows the creation of a new call center channel.</span></span>

![Ny kundtjänstkanal](media/channel-setup-callcenter-1.png)

<span data-ttu-id="1c62b-137">I bilden nedan visas ett exempel på kundtjänstkanal.</span><span class="sxs-lookup"><span data-stu-id="1c62b-137">The following image shows an example call center channel.</span></span>

![Exempel på kundtjänstkanal](media/channel-setup-callcenter-2.png)

## <a name="additional-channel-setup"></a><span data-ttu-id="1c62b-139">Konfiguration av ytterligare kanal</span><span class="sxs-lookup"><span data-stu-id="1c62b-139">Additional channel setup</span></span>

<span data-ttu-id="1c62b-140">Ytterligare uppgifter som krävs för inställningar av kundtjänstkanal inkluderar inställning av betalningsmetoder och leveranssätt.</span><span class="sxs-lookup"><span data-stu-id="1c62b-140">Additional tasks required for call center channel setup include setting up payment methods and modes of delivery.</span></span>

<span data-ttu-id="1c62b-141">I följande bild visas konfigurationsalternativen **leveranssätt** och **betalningsmetoder** på fliken **inställning**.</span><span class="sxs-lookup"><span data-stu-id="1c62b-141">The following image shows **Modes of delivery** and **Payment methods** setup options on the **Set up** tab.</span></span>

![Ytterligare åtgärder för konfigurering av kundtjänstkanal](media/channel-setup-callcenter-3.png)

### <a name="set-up-payment-methods"></a><span data-ttu-id="1c62b-143">Ange betalningsmetoder</span><span class="sxs-lookup"><span data-stu-id="1c62b-143">Set up payment methods</span></span>

<span data-ttu-id="1c62b-144">Om du vill ställa in betalningsmetoder följer du dessa steg för varje betalningstyp som stöds på den här kanalen.</span><span class="sxs-lookup"><span data-stu-id="1c62b-144">To set up payment methods, follow these steps for each payment type supported on this channel.</span></span> <span data-ttu-id="1c62b-145">Användarna måste välja bland fördefinierade betalningsmetoder för att kunna länka dem till kundtjänstkanalen.</span><span class="sxs-lookup"><span data-stu-id="1c62b-145">Users will be required to select from pre-defined payment methods to link them to the call center channel.</span></span> <span data-ttu-id="1c62b-146">Innan du ställer in dina betalningsmetoder för kundtjänst, ställ först in dina betalningsmetoder i **Retail och Commerce \> Kanalinställning \> Betalningsmetoder \> Betalningsmetoder**.</span><span class="sxs-lookup"><span data-stu-id="1c62b-146">Before setting up your call center payment methods, first set up your master methods of payment in **Retail and Commerce \> Channel setup \> Payment methods \> Payment methods**.</span></span>

1. <span data-ttu-id="1c62b-147">I åtgärdsfönstret, välj fliken **Inställningar** och välj sedan **betalningssätt**.</span><span class="sxs-lookup"><span data-stu-id="1c62b-147">On the action pane, select the **Set up** tab, and then select **Payment methods**.</span></span>
1. <span data-ttu-id="1c62b-148">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="1c62b-148">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="1c62b-149">I navigeringsfönstret väljer du en betalningsmetod från tillgängliga fördefinierade betalningar.</span><span class="sxs-lookup"><span data-stu-id="1c62b-149">In the navigation pane, select a payment method from the pre-defined payments available.</span></span>
1. <span data-ttu-id="1c62b-150">Konfigurera eventuella ytterligare inställningar efter behov för betalningstypen.</span><span class="sxs-lookup"><span data-stu-id="1c62b-150">Configure any additional settings as required for the payment type.</span></span> <span data-ttu-id="1c62b-151">För kreditkort, presentkort eller förmånskort behöver du ytterligare inställningar genom att välja funktionen **kortinställningar**.</span><span class="sxs-lookup"><span data-stu-id="1c62b-151">For credit cards, gift cards, or loyalty cards, additional setup is required by selecting the **Card setup** function.</span></span> 
1. <span data-ttu-id="1c62b-152">Konfigurera lämpliga bokföringskonton för betalningstypen avsnittet **bokföring**.</span><span class="sxs-lookup"><span data-stu-id="1c62b-152">Configure proper posting accounts for the payment type in the **Posting** section.</span></span>
1. <span data-ttu-id="1c62b-153">I åtgärdsfönstret, klicka på **spara**.</span><span class="sxs-lookup"><span data-stu-id="1c62b-153">On the action pane, click **Save**.</span></span>

<span data-ttu-id="1c62b-154">I bilden nedan visas ett exempel på en kontantbetalningsmetod.</span><span class="sxs-lookup"><span data-stu-id="1c62b-154">The following image shows an example of a cash payment method.</span></span>

![Exempel på betalningsmetoder](media/channel-setup-callcenter-payments.png)

### <a name="set-up-modes-of-delivery"></a><span data-ttu-id="1c62b-156">Ställ in leveranssätt</span><span class="sxs-lookup"><span data-stu-id="1c62b-156">Set up modes of delivery</span></span>

<span data-ttu-id="1c62b-157">Du kan visa de konfigurerade leveranssätten genom att välja **Leveranssätt** från fliken **Inställningar** i **Åtgärdsfönstret**.</span><span class="sxs-lookup"><span data-stu-id="1c62b-157">You can see the configured modes of delivery by selecting **Modes of delivery** from the **Set up** tab on the **Action pane**.</span></span>  

<span data-ttu-id="1c62b-158">Om du vill ändra eller lägga till ett leveranssätt som ska associeras till den här kundtjänstkanalen följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="1c62b-158">To change or add a mode of delivery to be associated to the call center channel, follow these steps.</span></span>

1. <span data-ttu-id="1c62b-159">I formuläret kundtjänstlägen för leveranssätt väljer du **Hantera leveranssätt**</span><span class="sxs-lookup"><span data-stu-id="1c62b-159">From the Call center modes of delivery form, select **Manage modes of delivery**</span></span>
1. <span data-ttu-id="1c62b-160">I åtgärdsfönstret, välj **Ny** om du vill skapa ett nytt leverans sätt, eller välj ett befintligt läge.</span><span class="sxs-lookup"><span data-stu-id="1c62b-160">On the action pane, select **New** to create a new mode of delivery, or select an existing mode.</span></span>
1. <span data-ttu-id="1c62b-161">I avsnittet **butikskanaler**, klicka på **lägg till rad** om du vill lägga till kundtjänstkanalen.</span><span class="sxs-lookup"><span data-stu-id="1c62b-161">In the **Retail channels** section, click **Add line** to add the call center channel.</span></span> <span data-ttu-id="1c62b-162">Lägga till kanaler med hjälp av organisationsnoder istället för att lägga till varje kanal individuellt kan lägga till kanaler effektivare.</span><span class="sxs-lookup"><span data-stu-id="1c62b-162">Adding channels using organization nodes instead of adding each channel individually can streamline adding channels.</span></span>
1. <span data-ttu-id="1c62b-163">Se till att leveranssättet har konfigurerats med data på snabbfliken **produkter** och på snabbfliken **adresser**.</span><span class="sxs-lookup"><span data-stu-id="1c62b-163">Ensure the mode of delivery has been configured with data on the **Products** FastTab and the **Addresses** FastTab.</span></span> <span data-ttu-id="1c62b-164">Om inga produkter eller leveransadresser är giltiga för leveranssättet, orsakar fel när du väljer det under orderregistrering.</span><span class="sxs-lookup"><span data-stu-id="1c62b-164">If no products or delivery addresses are valid for the mode of delivery, choosing it during order entry will result in errors.</span></span>
1. <span data-ttu-id="1c62b-165">När du har ändrat i konfiguration av kundtjänsts leveranssätt måste jobbet **bearbeta leveranssätt** köras för att ändra matrisen.</span><span class="sxs-lookup"><span data-stu-id="1c62b-165">After any changes have been made to the call center mode of delivery configurations, the **Process delivery modes** job must be run to explode the change matrix.</span></span> <span data-ttu-id="1c62b-166">Det här jobbet hittar du genom att navigera till **Retail och Commerce \> Retail och Commerce IT \> Bearbeta leveranssätt**.</span><span class="sxs-lookup"><span data-stu-id="1c62b-166">This job can be found by navigating to **Retail and Commerce \> Retail and Commerce IT \> Process delivery modes**.</span></span>

<span data-ttu-id="1c62b-167">I bilden nedan visas ett exempel på ett leveranssätt.</span><span class="sxs-lookup"><span data-stu-id="1c62b-167">The following image shows an example of a mode of delivery.</span></span>

![Ställ in leveranssätt](media/channel-setup-retail-7.png)

### <a name="set-up-channel-users"></a><span data-ttu-id="1c62b-169">Ställ in en kanalanvändare</span><span class="sxs-lookup"><span data-stu-id="1c62b-169">Set up channel users</span></span>

<span data-ttu-id="1c62b-170">Om du vill skapa en försäljningsorder som är länkad till en kundtjänstkanal från Commerce-administration måste användaren som skapar försäljningsordern vara kopplad till kundtjänstkanalen.</span><span class="sxs-lookup"><span data-stu-id="1c62b-170">To create a sales order that is linked to the call center channel from Commerce Headquarters, the user creating the sales order must be linked to the call center channel.</span></span> <span data-ttu-id="1c62b-171">Användaren kan inte manuellt länka en försäljningsorder som har skapats i Commerce-administration till kundtjänstkanalen.</span><span class="sxs-lookup"><span data-stu-id="1c62b-171">The user cannot manually link a sales order created in Commerce Headquarters to the call center channel.</span></span> <span data-ttu-id="1c62b-172">Länken är systematisk och baseras på användaren och användarens relation till kundtjänstkanalen.</span><span class="sxs-lookup"><span data-stu-id="1c62b-172">The link is systematic, and is based on the user and the user's relationship to the call center channel.</span></span> <span data-ttu-id="1c62b-173">En användare kan bara länkas till en kundtjänstkanal.</span><span class="sxs-lookup"><span data-stu-id="1c62b-173">A user may only be linked to one call center channel.</span></span>

1. <span data-ttu-id="1c62b-174">I åtgärdsfönstret, välj fliken **Kanal** och välj sedan **Kanalanvändare**.</span><span class="sxs-lookup"><span data-stu-id="1c62b-174">On the action pane, select the **Channel** tab, and then select **Channel users**.</span></span>
1. <span data-ttu-id="1c62b-175">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="1c62b-175">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="1c62b-176">Välj ett befintligt **användar-ID** från listrutan urvalslista för att koppla användaren till kundtjänstkanalen</span><span class="sxs-lookup"><span data-stu-id="1c62b-176">Choose an existing **User ID** from the dropdown selection list to link this user to the call center channel</span></span>

<span data-ttu-id="1c62b-177">När kanalanvändarinställningen är klar och användaren skapar en ny försäljningsorder i Commerce-administration kommer försäljningsorder att kopplas till deras tillhörande kundtjänstkanal.</span><span class="sxs-lookup"><span data-stu-id="1c62b-177">After the channel user setup is done and the user creates a new sales order in Commerce Headquarters, the sales order will be linked to their associated call center channel.</span></span> <span data-ttu-id="1c62b-178">Alla konfigurationer för den här kanalen kommer att tillämpas systematiskt på försäljningsordern.</span><span class="sxs-lookup"><span data-stu-id="1c62b-178">Any configurations for this channel will be applied systematically to the sales order.</span></span> <span data-ttu-id="1c62b-179">En användare kan bekräfta vilken kundtjänstkanal som försäljningsordern är kopplad till genom att visa kanalnamnreferensen i försäljningsorderrubriken.</span><span class="sxs-lookup"><span data-stu-id="1c62b-179">A user can confirm which call center channel the sales order is linked to by viewing the channel name reference on the sales order header.</span></span>


### <a name="set-up-price-groups"></a><span data-ttu-id="1c62b-180">Ställa in prisgrupper</span><span class="sxs-lookup"><span data-stu-id="1c62b-180">Set up price groups</span></span>

<span data-ttu-id="1c62b-181">Prisgrupper är valfria, men om de används kan du kontrollera vilka försäljningspriser som ska erbjudas till kunder som ställer order i den här kundtjänstkanalen.</span><span class="sxs-lookup"><span data-stu-id="1c62b-181">Price groups are optional, but if used, can control which sales prices will be offered to customers placing orders in the call center channel.</span></span> <span data-ttu-id="1c62b-182">Om en prisgrupp inte har konfigurerats för kunden, eller om katalogprisgrupper inte används på försäljningsordern (med hjälp av fältet **Källkod-ID** i orderrubriken för kundtjänst), används kanalprisgruppen för att hitta artikelpriserna.</span><span class="sxs-lookup"><span data-stu-id="1c62b-182">If a price group has not been configured for the customer, or if catalog price groups are not being applied to the sales order (using the **Source code ID** field on the call center order header), then the channel price group is used to locate item prices.</span></span> <span data-ttu-id="1c62b-183">Om en prisgrupp inte finns på kundtjänstkanalen används standardartikelns huvudpriser.</span><span class="sxs-lookup"><span data-stu-id="1c62b-183">If a price group is not found on the call center channel, the default item master prices are used.</span></span> 

<span data-ttu-id="1c62b-184">Om du vill ställa in en prisgrupp gör du följande.</span><span class="sxs-lookup"><span data-stu-id="1c62b-184">To set up a price group, do the following.</span></span>

1. <span data-ttu-id="1c62b-185">I åtgärdsfönstret, välj fliken **Kanal** och välj sedan **Prisgrupper**.</span><span class="sxs-lookup"><span data-stu-id="1c62b-185">On the action pane, click the **Channel** tab, and then select **Price groups**.</span></span>
1. <span data-ttu-id="1c62b-186">Klicka på **Nytt** i Åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="1c62b-186">On the action pane, click **New**.</span></span>
1. <span data-ttu-id="1c62b-187">Välj en **butiksprisgrupp** i listrutans urvalslista.</span><span class="sxs-lookup"><span data-stu-id="1c62b-187">Select a **Retail price group** from the dropdown selection list.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1c62b-188">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="1c62b-188">Additional resources</span></span>

[<span data-ttu-id="1c62b-189">Förutsättningar för kanalinställningar</span><span class="sxs-lookup"><span data-stu-id="1c62b-189">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="1c62b-190">Försäljningsfunktioner för kundtjänst</span><span class="sxs-lookup"><span data-stu-id="1c62b-190">Call center sales functionality</span></span>](call-center-functionality.md)

[<span data-ttu-id="1c62b-191">Ställ in alternativ för orderbearbetning för kundtjänst</span><span class="sxs-lookup"><span data-stu-id="1c62b-191">Set up call center order processing options</span></span>](set-up-order-processing-options.md)

[<span data-ttu-id="1c62b-192">Kundtjänstkataloger</span><span class="sxs-lookup"><span data-stu-id="1c62b-192">Call center catalogs</span></span>](call-center-catalogs.md)

[<span data-ttu-id="1c62b-193">Ställa in och arbeta med bedrägerivarningar</span><span class="sxs-lookup"><span data-stu-id="1c62b-193">Set up and work with fraud alerts</span></span>](set-up-fraud-alerts.md)

[<span data-ttu-id="1c62b-194">Ställa in kontinuitetsprogram för kundtjänster</span><span class="sxs-lookup"><span data-stu-id="1c62b-194">Set up continuity programs for call centers</span></span>](set-up-continuity-program.md)
