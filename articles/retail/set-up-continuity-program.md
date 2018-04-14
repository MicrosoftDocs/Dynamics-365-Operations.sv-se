---
title: "Ställ in ett kontinuitetsprogram för en kundtjänst"
description: "Det här avsnittet innehåller en beskrivning av hur du ställer in ett kontinuitetsprogram för en kundtjänst."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: MCROrderParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16081
ms.assetid: 426a9be7-a931-4780-b372-e06f6083dd60
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 6f0042bf45354113b2bce22ae81365dee837824d
ms.contentlocale: sv-se
ms.lasthandoff: 04/13/2018

---

# <a name="set-up-a-continuity-program-for-a-call-center"></a><span data-ttu-id="1d6ef-103">Ställ in ett kontinuitetsprogram för en kundtjänst</span><span class="sxs-lookup"><span data-stu-id="1d6ef-103">Set up a continuity program for a call center</span></span>

[!INCLUDE [banner](includes/banner.md)]

<span data-ttu-id="1d6ef-104">Det här avsnittet innehåller en beskrivning av hur du ställer in ett kontinuitetsprogram för en kundtjänst.</span><span class="sxs-lookup"><span data-stu-id="1d6ef-104">This article describes how to set up a continuity program for a call center.</span></span>

<span data-ttu-id="1d6ef-105">I ett kontinuitetsprogram, som kallas också för ett återkommande orderprogram, får kunder vanliga produktleveranser enligt en fördefinierad tidsplan.</span><span class="sxs-lookup"><span data-stu-id="1d6ef-105">In a continuity program, which is also known as a recurring order program, customers receive regular product shipments according to a predefined schedule.</span></span> <span data-ttu-id="1d6ef-106">Varje leverans kan innehålla olika produkter, till exempel månadens bok, eller samma produkt som skickas igen och igen.</span><span class="sxs-lookup"><span data-stu-id="1d6ef-106">Each shipment can contain a different product, as in the case of a book-of-the-month club, or the same product can be sent repeatedly.</span></span> <span data-ttu-id="1d6ef-107">Om du vill ställa in ett kontinuitetsprogram måste du göra följande.</span><span class="sxs-lookup"><span data-stu-id="1d6ef-107">To set up a continuity program, you must complete the following tasks.</span></span>

1.  <span data-ttu-id="1d6ef-108">Ange kontinuitetsparametrarna på sidan **Parametrar för kundtjänst**.</span><span class="sxs-lookup"><span data-stu-id="1d6ef-108">Set the continuity parameters on the **Call center parameters** page.</span></span>
2.  <span data-ttu-id="1d6ef-109">Skapa ett kontinuitetsprogram som anger information, till exempel betalningsplan, leveranstid och om betalningen görs direkt.</span><span class="sxs-lookup"><span data-stu-id="1d6ef-109">Create a continuity program that specifies details such as the payment schedule, the timing of the shipments, and whether billing is up front.</span></span> <span data-ttu-id="1d6ef-110">Du måste även lägga till en lista med produkter som ingår i kontinuitetsprogrammet.</span><span class="sxs-lookup"><span data-stu-id="1d6ef-110">You must also add a list of products that are included in the continuity program.</span></span> <span data-ttu-id="1d6ef-111">Varje produkt får ett händelse-ID-nummer som tilldelas i ordningsföljd med början på 1.</span><span class="sxs-lookup"><span data-stu-id="1d6ef-111">Each product receives an event ID number that is assigned sequentially, beginning with 1.</span></span> <span data-ttu-id="1d6ef-112">Händelsen-ID-numret bestämmer ordningen som produkterna skickas i.</span><span class="sxs-lookup"><span data-stu-id="1d6ef-112">The event IDs determine the order that products are sent in.</span></span>
    -   <span data-ttu-id="1d6ef-113">Om kunder får olika produkter i varje leverans, skickas produkterna i sekventiell ordning enligt deras händelse-id:n, baserat på händelse-id:na och som börjar med den aktuella händelsen.</span><span class="sxs-lookup"><span data-stu-id="1d6ef-113">If customers receive a different product in each shipment, the products are sent in sequential order, based on their event IDs and beginning with the current event.</span></span>
    -   <span data-ttu-id="1d6ef-114">Om kunder får likadana produkten i varje leverans, innehåller listan endast en produkt som har ett händelse-id.</span><span class="sxs-lookup"><span data-stu-id="1d6ef-114">If customers receive the same product in each shipment, the list contains only one product that has one event ID.</span></span> <span data-ttu-id="1d6ef-115">Samma händelsen inträffar flera gånger.</span><span class="sxs-lookup"><span data-stu-id="1d6ef-115">The same event occurs repeatedly.</span></span> <span data-ttu-id="1d6ef-116">Du kan ange hur många gånger varje händelse ska upprepas.</span><span class="sxs-lookup"><span data-stu-id="1d6ef-116">You can specify how many times each event is repeated.</span></span>

3.  <span data-ttu-id="1d6ef-117">Skapa en överordnad produkt som motsvarar det kontinuitetsprogram som du skapade i uppgift 2.</span><span class="sxs-lookup"><span data-stu-id="1d6ef-117">Create a parent product that represents the continuity program that you created in task 2.</span></span> <span data-ttu-id="1d6ef-118">Om du lägger till produkten till en försäljningsorder öppnas sidan **Kontinuitet**.</span><span class="sxs-lookup"><span data-stu-id="1d6ef-118">If you add this product to a sales order, the **Continuity** page opens.</span></span> <span data-ttu-id="1d6ef-119">Du kan sedan använda sidan för att skapa kontinuitetsordern.</span><span class="sxs-lookup"><span data-stu-id="1d6ef-119">You can then use that page to create the actual continuity order.</span></span> <span data-ttu-id="1d6ef-120">Överordnad produkt anger inte de enskilda produkter som kunden får i varje leverans.</span><span class="sxs-lookup"><span data-stu-id="1d6ef-120">The parent product doesn't specify the individual products that the customer receives in each shipment.</span></span>

<span data-ttu-id="1d6ef-121">När du har ställt in ett kontinuitetsprogram enligt beskrivningen ovan kan du skapa en kontinuitetsorder för en kund.</span><span class="sxs-lookup"><span data-stu-id="1d6ef-121">After you've set up a continuity program as described above, you can create a continuity order for a customer.</span></span> <span data-ttu-id="1d6ef-122">Du kanske också måste utföra de ytterligare underhållsåtgärderna nedan.</span><span class="sxs-lookup"><span data-stu-id="1d6ef-122">You might also have to perform the following additional maintenance tasks.</span></span>

-   <span data-ttu-id="1d6ef-123">**Uppdatera den aktuella händelseperioden för kontinuitet** – Ställ in ett batchjobb som informerar systemet om vad den aktuella händelseperioden är.</span><span class="sxs-lookup"><span data-stu-id="1d6ef-123">**Update the current continuity event period** – Set up a batch job that tells the system what the current event period is.</span></span>
-   <span data-ttu-id="1d6ef-124">**Skapa underordnade kontinuitetsorder** – Skapa underordnade order från överordnad kontinuitetsorder.</span><span class="sxs-lookup"><span data-stu-id="1d6ef-124">**Create continuity child orders** – Create child orders from the parent continuity order.</span></span>
-   <span data-ttu-id="1d6ef-125">**Bearbeta kontinuitetsbetalningar** – Bearbeta fakturering och meddelanden för betalningar som är associerade med kontinuitetsförsäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="1d6ef-125">**Process continuity payments** – Process billing and notifications for payments that are associated with continuity sales orders.</span></span>
-   <span data-ttu-id="1d6ef-126">**Utöka kontinuitetsrader** (vid behov) – Utöka antalet gånger som en kontinuitetshändelse kan upprepas.</span><span class="sxs-lookup"><span data-stu-id="1d6ef-126">**Extend continuity lines** (if required) – Extend the number of times that a continuity event can be repeated.</span></span> <span data-ttu-id="1d6ef-127">Repetitionen av försändelser kan överskrida tidsgränsen som anges i fältet **Tröskel för upprepa kontinuitet** i kundtjänstparametrarna.</span><span class="sxs-lookup"><span data-stu-id="1d6ef-127">The repetition of shipments can then extend beyond the limit that was set in the **Continuity repeat threshold** field in the call center parameters.</span></span>
-   <span data-ttu-id="1d6ef-128">**Utför en kontinuitetsuppdatering** (vid behov) – Synkronisera ändringar mellan kontinuitetsprogrammet och överordnade kontinuitetsförsäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="1d6ef-128">**Perform a continuity update** (if required) – Synchronize changes between the continuity program and the continuity parent sales orders.</span></span>
-   <span data-ttu-id="1d6ef-129">**Stäng överordnade kontinuitetsrader och kontinuitetsorder** – Stäng kontinuitetsorder.</span><span class="sxs-lookup"><span data-stu-id="1d6ef-129">**Close continuity parent lines and orders** – Close continuity orders.</span></span>





