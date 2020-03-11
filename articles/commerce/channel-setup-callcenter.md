---
title: Ställa in en kundtjänstkanal
description: I det här avsnittet beskrivs hur du skapar en ny kundtjänstkanal i Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 42448bd54c00b8642b158f422e17d2b46ee25579
ms.sourcegitcommit: 12b9d6f2dd24e52e46487748c848864909af6967
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/14/2020
ms.locfileid: "3057889"
---
# <a name="set-up-a-call-center-channel"></a><span data-ttu-id="49089-103">Ställa in en kundtjänstkanal</span><span class="sxs-lookup"><span data-stu-id="49089-103">Set up a call center channel</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="49089-104">I det här avsnittet beskrivs hur du skapar en ny kundtjänstkanal i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="49089-104">This topic describes how to create a new call center channel in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="49089-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="49089-105">Overview</span></span>

<span data-ttu-id="49089-106">I Dynamics 365 Commerce, är kundtjänst en typ av kanal som kan definieras i programmet.</span><span class="sxs-lookup"><span data-stu-id="49089-106">In Dynamics 365 Commerce, a call center is a type of channel that can be defined in the application.</span></span> <span data-ttu-id="49089-107">Om du definierar en kanal för dina kundtjänstenheter kan systemet koppla specifika data och orderbearbetningsstandard till försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="49089-107">Defining a channel for your call center entities allows the system to tie specific data and order processing defaults to sales orders.</span></span> <span data-ttu-id="49089-108">Ett företag kan definiera flera kundtjänstkanaler i Handel.</span><span class="sxs-lookup"><span data-stu-id="49089-108">A company can define multiple call center channels in Commerce.</span></span> 

<span data-ttu-id="49089-109">Innan du skapar en ny kundtjänstkanal måste du kontrollera att du har slutfört [Förutsättningar för att ställa in kanaler](channels-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="49089-109">Before you create a new call center channel, ensure that you have completed the [Channel set up prerequisites](channels-prerequisites.md).</span></span>

## <a name="create-and-configure-a-new-call-center-channel"></a><span data-ttu-id="49089-110">Skapa och konfigurera en ny kundtjänstkanal</span><span class="sxs-lookup"><span data-stu-id="49089-110">Create and configure a new call center channel</span></span>

<span data-ttu-id="49089-111">Följ stegen nedan om du vill skapa och konfigurera en ny kundtjänstkanal.</span><span class="sxs-lookup"><span data-stu-id="49089-111">To create and configure a new call center channel, follow these steps.</span></span>

1. <span data-ttu-id="49089-112">I navigeringsfönstret går du till **moduler \> kanaler \> kundtjänst \> alla kundtjänster**.</span><span class="sxs-lookup"><span data-stu-id="49089-112">In the navigation pane, go to **Modules \> Channels \> Call centers \> All call centers**.</span></span>
1. <span data-ttu-id="49089-113">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="49089-113">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="49089-114">I fältet **Namn** ange ett namn på den nya kanalen.</span><span class="sxs-lookup"><span data-stu-id="49089-114">In the **Name** field, provide a name for the new channel.</span></span>
1. <span data-ttu-id="49089-115">Välj lämplig **Juridisk enhet** från listrutan.</span><span class="sxs-lookup"><span data-stu-id="49089-115">Select the appropriate **Legal entity** from the drop down.</span></span>
1. <span data-ttu-id="49089-116">Välj lämplig plats för **Lagerställe** från listrutan.</span><span class="sxs-lookup"><span data-stu-id="49089-116">Select the appropriate **Warehouse** location from the drop down.</span></span>
1. <span data-ttu-id="49089-117">I fältet **Standardkund** ange en giltig standardkund.</span><span class="sxs-lookup"><span data-stu-id="49089-117">In the **Default customer** field, provide a valid default customer.</span></span>
1. <span data-ttu-id="49089-118">I fältet **Meddelandeprofil för e-post** ange en giltig meddelandeprofil för e-post.</span><span class="sxs-lookup"><span data-stu-id="49089-118">In the **Email notification profile** field, provide a valid email notification profile.</span></span>
1. <span data-ttu-id="49089-119">Ange informationskoden **prisåsidosättning**.</span><span class="sxs-lookup"><span data-stu-id="49089-119">Provide a **Price override** info code.</span></span> <span data-ttu-id="49089-120">Observera att du måste skapa en informationskod för denna första.</span><span class="sxs-lookup"><span data-stu-id="49089-120">Note you may need to create an info code for this first.</span></span>
1. <span data-ttu-id="49089-121">Tillhandahåll en informationskod **Spärrkod**.</span><span class="sxs-lookup"><span data-stu-id="49089-121">Provide a **Hold code** info code.</span></span> <span data-ttu-id="49089-122">Observera att du måste skapa en informationskod för denna första.</span><span class="sxs-lookup"><span data-stu-id="49089-122">Note you may need to create an info code for this first.</span></span>
1. <span data-ttu-id="49089-123">Ange en informationskod **Kredit**.</span><span class="sxs-lookup"><span data-stu-id="49089-123">Provide a **Credit** info code.</span></span> <span data-ttu-id="49089-124">Observera att du måste skapa en informationskod för denna första.</span><span class="sxs-lookup"><span data-stu-id="49089-124">Note you may need to create an info code for this first.</span></span>
1. <span data-ttu-id="49089-125">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="49089-125">Select **Save**.</span></span>

<span data-ttu-id="49089-126">Följande bild visar hur en ny kundtjänstkanal skapas.</span><span class="sxs-lookup"><span data-stu-id="49089-126">The following image shows the creation of a new call center channel.</span></span>

![Ny kundtjänstkanal](media/channel-setup-callcenter-1.png)

<span data-ttu-id="49089-128">I bilden nedan visas ett exempel på kundtjänstkanal.</span><span class="sxs-lookup"><span data-stu-id="49089-128">The following image shows an example call center channel.</span></span>

![Exempel på kundtjänstkanal](media/channel-setup-callcenter-2.png)

## <a name="additional-channel-setup"></a><span data-ttu-id="49089-130">Konfiguration av ytterligare kanal</span><span class="sxs-lookup"><span data-stu-id="49089-130">Additional channel setup</span></span>

<span data-ttu-id="49089-131">Ytterligare uppgifter som krävs för inställningar av kundtjänstkanal inkluderar inställning av betalningsmetoder och leveranssätt.</span><span class="sxs-lookup"><span data-stu-id="49089-131">Additional tasks required for call center channel setup include setting up payment methods and modes of delivery.</span></span>

<span data-ttu-id="49089-132">I följande bild visas konfigurationsalternativen **leveranssätt** och **betalningsmetoder** på fliken **inställning**.</span><span class="sxs-lookup"><span data-stu-id="49089-132">The following image shows **Modes of delivery** and **Payment methods** set up options on the **Set up** tab.</span></span>

![Ytterligare åtgärder för konfigurering av kundtjänstkanal](media/channel-setup-callcenter-3.png)

### <a name="set-up-payment-methods"></a><span data-ttu-id="49089-134">Ange betalningsmetoder</span><span class="sxs-lookup"><span data-stu-id="49089-134">Set up payment methods</span></span>

<span data-ttu-id="49089-135">Om du vill ställa in betalningsmetoder följer du dessa steg för varje betalningstyp som stöds på den här kanalen.</span><span class="sxs-lookup"><span data-stu-id="49089-135">To set up payment methods, for each payment type supported on this channel follow these steps.</span></span>

1. <span data-ttu-id="49089-136">I åtgärdsfönstret, välj fliken **Inställningar** och välj sedan **betalningssätt**.</span><span class="sxs-lookup"><span data-stu-id="49089-136">On the action pane, select the **Set up** tab, and then select **Payment methods**.</span></span>
1. <span data-ttu-id="49089-137">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="49089-137">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="49089-138">I navigeringsfönstret väljer du önskad betalningsmetod.</span><span class="sxs-lookup"><span data-stu-id="49089-138">In the navigation pane, select a desired payment method.</span></span>
1. <span data-ttu-id="49089-139">I avsnittet **Allmänt** anger du ett **åtgärdsnamn** och konfigurerar andra önskade inställningar.</span><span class="sxs-lookup"><span data-stu-id="49089-139">In the **General** section, provide an **Operation name** and configure any other desired settings.</span></span>
1. <span data-ttu-id="49089-140">Konfigurera eventuella ytterligare inställningar efter behov för betalningstypen.</span><span class="sxs-lookup"><span data-stu-id="49089-140">Configure any additional settings as required for the payment type.</span></span>
1. <span data-ttu-id="49089-141">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="49089-141">On the action pane, select **Save**.</span></span>

<span data-ttu-id="49089-142">I bilden nedan visas ett exempel på en kontantbetalningsmetod.</span><span class="sxs-lookup"><span data-stu-id="49089-142">The following image shows an example of a cash payment method.</span></span>

![Exempel på betalningsmetoder](media/channel-setup-retail-5.png)

### <a name="set-up-modes-of-delivery"></a><span data-ttu-id="49089-144">Ställ in leveranssätt</span><span class="sxs-lookup"><span data-stu-id="49089-144">Set up modes of delivery</span></span>

<span data-ttu-id="49089-145">Du kan visa de konfigurerade leveranssätten genom att välja **Leveranssätt** från fliken **Inställningar** i **Åtgärdsfönstret**.</span><span class="sxs-lookup"><span data-stu-id="49089-145">You can see the configured modes of delivery by selecting **Modes of delivery** from the **Set up** tab on the **Action pane**.</span></span>  

<span data-ttu-id="49089-146">Om du vill ändra eller lägga till ett leveranssätt följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="49089-146">To change or add a mode of delivery, follow these steps.</span></span>

1. <span data-ttu-id="49089-147">I navigeringsfönstret, gå till **Moduler \> Lagerhantering \> Leveranssätt**.</span><span class="sxs-lookup"><span data-stu-id="49089-147">In the navigation pane, go to **Modules \> Inventory management \> Modes of delivery**.</span></span>
1. <span data-ttu-id="49089-148">I åtgärdsfönstret, välj **Ny** om du vill skapa ett nytt leverans sätt, eller välj ett befintligt läge.</span><span class="sxs-lookup"><span data-stu-id="49089-148">On the action pane, select **New** to create a new mode of delivery, or select an existing mode.</span></span>
1. <span data-ttu-id="49089-149">I avsnittet **butikskanaler**, välj **lägg till rad** om du vill lägga till kanalen.</span><span class="sxs-lookup"><span data-stu-id="49089-149">In the **Retail channels** section, select **Add line** to add the channel.</span></span> <span data-ttu-id="49089-150">Lägga till kanaler med hjälp av organisationsnoder istället för att lägga till varje kanal individuellt kan lägga till kanaler effektivare.</span><span class="sxs-lookup"><span data-stu-id="49089-150">Adding channels using organization nodes instead of adding each channel individually can streamline adding channels.</span></span>

<span data-ttu-id="49089-151">I bilden nedan visas ett exempel på ett leveranssätt.</span><span class="sxs-lookup"><span data-stu-id="49089-151">The following image shows an example of a mode of delivery.</span></span>

![Ställ in leveranssätt](media/channel-setup-retail-7.png)

## <a name="additional-resources"></a><span data-ttu-id="49089-153">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="49089-153">Additional resources</span></span>

[<span data-ttu-id="49089-154">Förutsättningar för att ställa in kanaler</span><span class="sxs-lookup"><span data-stu-id="49089-154">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="49089-155">Försäljningsfunktioner för kundtjänst</span><span class="sxs-lookup"><span data-stu-id="49089-155">Call center sales functionality</span></span>](call-center-functionality.md)

[<span data-ttu-id="49089-156">Ställ in alternativ för orderbearbetning för kundtjänst</span><span class="sxs-lookup"><span data-stu-id="49089-156">Set up call center order processing options</span></span>](set-up-order-processing-options.md)

[<span data-ttu-id="49089-157">Kundtjänstkataloger</span><span class="sxs-lookup"><span data-stu-id="49089-157">Call center catalogs</span></span>](call-center-catalogs.md)

[<span data-ttu-id="49089-158">Ställa in och arbeta med bedrägerivarningar</span><span class="sxs-lookup"><span data-stu-id="49089-158">Set up and work with fraud alerts</span></span>](set-up-fraud-alerts.md)

[<span data-ttu-id="49089-159">Ställa in kontinuitetsprogram för kundtjänster</span><span class="sxs-lookup"><span data-stu-id="49089-159">Set up continuity programs for call centers</span></span>](set-up-continuity-program.md)
