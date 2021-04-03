---
title: Åtgärden återkalla order i POS
description: Det här avsnittet handlar om vilka funktioner som finns för att förbättra sidor för orderåterkallning i POS.
author: hhainesms
manager: annbe
ms.date: 03/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: global
ms.author: hhaines
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 174821fce4baf81e4298da4b066f855bfec98ca5
ms.sourcegitcommit: 6c108be3378b365e6ec596a1a8666d59b758db25
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/12/2021
ms.locfileid: "5585140"
---
# <a name="recall-order-operation-in-pos"></a><span data-ttu-id="ab830-103">Åtgärden återkalla order i POS</span><span class="sxs-lookup"><span data-stu-id="ab830-103">Recall order operation in POS</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="ab830-104">Åtgärden **Återkalla order** i Commerce-POS ger uppdaterade funktioner för ordersökning och filtrering, samt orderspecifik information.</span><span class="sxs-lookup"><span data-stu-id="ab830-104">The **Recall order** operation in the Commerce point of sale (POS) provides updated order search and filtering features and order-specific information.</span></span> <span data-ttu-id="ab830-105">Den här funktionen är tillgänglig i Commerce versioner 10.0.15 och senare.</span><span class="sxs-lookup"><span data-stu-id="ab830-105">This feature is available in Commerce versions 10.0.15 and later.</span></span>

<span data-ttu-id="ab830-106">För att aktivera denna funktion, slå på funktionen **Förbättrad åtgärden återkalla order i POS** i arbetsytan **funktionshantering** i Commerce-administration.</span><span class="sxs-lookup"><span data-stu-id="ab830-106">To enable this functionality, turn the **Improved Recall order operation in POS** feature on in **Feature management** workspace in Commerce headquarters.</span></span> <span data-ttu-id="ab830-107">När du har aktiverat funktionen kan du överväga att uppdatera [bildskärmslayouter](pos-screen-layouts.md) i POS för att dra nytta av vissa av de ändrade funktionerna.</span><span class="sxs-lookup"><span data-stu-id="ab830-107">After you enable the feature, consider updating your [screen layouts](pos-screen-layouts.md) in POS to take advantage of some of the changed  capabilities.</span></span>

<span data-ttu-id="ab830-108">Genom att konfigurera knappen **Återkalla order** kan organisationer distribuera operationen med en fördefinierad visning.</span><span class="sxs-lookup"><span data-stu-id="ab830-108">The configuration of the **Recall order** operation button allows organizations to deploy the operation with a pre-defined display.</span></span>

![Konfiguration av knapprutnät](media/recallorderbuttongrid.png)

<span data-ttu-id="ab830-110">Visningsalternativen är följande.</span><span class="sxs-lookup"><span data-stu-id="ab830-110">The display options are as follows.</span></span>
- <span data-ttu-id="ab830-111">**Inget** – det här alternativet distribuerar åtgärden utan specifik visning.</span><span class="sxs-lookup"><span data-stu-id="ab830-111">**None** – This option deploys the operation with no specific display.</span></span> <span data-ttu-id="ab830-112">När en användare öppnar åtgärden med den här konfigurationen uppmanas de att söka efter order eller välja från ett fördefinierat orderfilter.</span><span class="sxs-lookup"><span data-stu-id="ab830-112">When a user opens the operation with this configuration, they will be prompted to search and find orders or choose from a pre-defined order filter.</span></span>
- <span data-ttu-id="ab830-113">**Order som ska uppfyllas** – när en användare startar operationen körs en fråga automatiskt för att söka i och visa en lista med order som ska uppfyllas av användarens nuvarande butik.</span><span class="sxs-lookup"><span data-stu-id="ab830-113">**Orders to fulfill** – When a user launches the operation, a query will run automatically to search and display a list of orders that are to be fulfilled by the user's current store.</span></span> <span data-ttu-id="ab830-114">Dessa order konfigureras för butikshämtning eller butiksleverans och raderna på dessa order har ännu inte plockats eller packats.</span><span class="sxs-lookup"><span data-stu-id="ab830-114">These orders are configured for in-store pickup or store shipment and the lines of these orders have not yet been picked or packed.</span></span>
- <span data-ttu-id="ab830-115">**Order som ska hämtas** – när en användare startar operationen körs en fråga automatiskt för att söka i och visa en lista med order som är konfigurerade för hämtning i butik eller i användarens nuvarande butik.</span><span class="sxs-lookup"><span data-stu-id="ab830-115">**Orders to pick up** – When a user launches the operation, a query will run automatically to search and display a list of orders that are configured for in-store pickup at the user's current store.</span></span>
- <span data-ttu-id="ab830-116">**Order som ska levereras** – när en användare startar operationen körs en fråga automatiskt för att söka i och visa en lista med order som är konfigurerade för leverans från användarens nuvarande butik.</span><span class="sxs-lookup"><span data-stu-id="ab830-116">**Orders to ship** - When a user launches the operation, a query will run automatically to search and display a list of orders that are configured for shipment from the user's current store.</span></span>

<span data-ttu-id="ab830-117">När du startar åtgärden **Återkalla order** från POS, om bildskärmen har konfigurerats till **ingen** kan en användare söka efter och hämta order på något av följande sätt.</span><span class="sxs-lookup"><span data-stu-id="ab830-117">When launching the **Recall order** operation from POS, if the display is configured to **None**, a user will be able to search and retrieve orders in one of the following ways.</span></span>
- <span data-ttu-id="ab830-118">Skanna orderstreckkoder.</span><span class="sxs-lookup"><span data-stu-id="ab830-118">Scan order barcodes.</span></span> <span data-ttu-id="ab830-119">Det här fältet söker efter ordernummer, kanalreferens och kvitto-ID för matchningar.</span><span class="sxs-lookup"><span data-stu-id="ab830-119">This will search order number, channel reference, and receipt ID fields for matches.</span></span>
- <span data-ttu-id="ab830-120">Välj ikonen **Sök order** eller **Sök och filtrera** på AppBar om du vill använda filtreringsfunktionen för att söka efter order som uppfyller filtervillkoren.</span><span class="sxs-lookup"><span data-stu-id="ab830-120">Select **Search orders** or **Search and filter** icon on the AppBar to use the filtering mechanism to locate orders that meet the filter criteria.</span></span>
- <span data-ttu-id="ab830-121">Välj från ett fördefinierat filter på listrutan **Visa order** (order som ska uppfyllas, order som ska hämtas eller order som ska levereras).</span><span class="sxs-lookup"><span data-stu-id="ab830-121">Choose from a pre-defined filter from the **Show Orders** drop-down menu (orders to fulfill, orders to pick up, or orders to ship).</span></span>

![RecallOrderMainMenu](media/recallordermain.png)

<span data-ttu-id="ab830-123">När sökkriterier har tillämpats visas en lista med matchande försäljningsorder i programmet.</span><span class="sxs-lookup"><span data-stu-id="ab830-123">After search criteria are applied, the application will display a list of matching sales orders.</span></span> <span data-ttu-id="ab830-124">Tänk på att när du använder sök-/filteralternativen behöver de hämtade orderna inte vara order som kopplas till användarens aktuella butik.</span><span class="sxs-lookup"><span data-stu-id="ab830-124">It's important to note that when using the search/filter options, the orders retrieved do not have to be orders linked to the user's current store.</span></span> <span data-ttu-id="ab830-125">Den här sökprocessen hämtar och visar alla kundorder som matchar sökkriterierna, även om ordern skapades eller skapades för att uppfyllas av en annan butik/kanal eller lagerställeplats.</span><span class="sxs-lookup"><span data-stu-id="ab830-125">This search process will retrieve and display any customer order that matches the search criteria, even if the order was created or set to be fulfilled by another store/channel or warehouse location.</span></span>

![RecallOrderDetail](media/orderrecalldetail.png)

<span data-ttu-id="ab830-127">En användare kan välja en order i listan om du vill visa mer information.</span><span class="sxs-lookup"><span data-stu-id="ab830-127">A user can select an order on the list to view additional details.</span></span> <span data-ttu-id="ab830-128">Informationspanelen till höger på skärmen visar specifika uppgifter för den valda ordern, inklusive order raddetaljer, leveransinformation och information om uppfyllelse.</span><span class="sxs-lookup"><span data-stu-id="ab830-128">The information panel on the right side of the screen displays specifics on the selected order, including order line details, delivery details, and fulfillment details.</span></span>

<span data-ttu-id="ab830-129">En användare kan välja en operation i AppBar.</span><span class="sxs-lookup"><span data-stu-id="ab830-129">From the AppBar, a user can select an operation.</span></span> <span data-ttu-id="ab830-130">Beroende på orderns status kan vissa operationer inte aktiveras.</span><span class="sxs-lookup"><span data-stu-id="ab830-130">Depending on the status of the order, certain operations may not be enabled.</span></span>

- <span data-ttu-id="ab830-131">**Retur** – Startar processen för att skapa en retur för någon av de fakturerade produkterna på den valda kundordern.</span><span class="sxs-lookup"><span data-stu-id="ab830-131">**Return** – Initiates the process of creating a return for any of the invoiced products on the selected customer order.</span></span>

- <span data-ttu-id="ab830-132">**Avbryt** – utfärda en fullständig annullering av den valda försäljningsordern.</span><span class="sxs-lookup"><span data-stu-id="ab830-132">**Cancel** – Issue a full cancellation of the selected sales order.</span></span> <span data-ttu-id="ab830-133">Det här alternativet är inte tillgängligt för order som initieras via en kundtjänstkanal och kan inte användas för att annullera en order delvis.</span><span class="sxs-lookup"><span data-stu-id="ab830-133">This option will not be available for orders initiated through a call center channel and cannot be used to partially cancel an order.</span></span>

- <span data-ttu-id="ab830-134">**Uppfyllelse** – överför användaren till sidan orderuppfyllelse, som kommer att filtreras för den valda ordern.</span><span class="sxs-lookup"><span data-stu-id="ab830-134">**Fulfill** – Transfers the user to the order fulfillment page, which will be pre-filtered for the selected order.</span></span> <span data-ttu-id="ab830-135">Endast orderrader som är öppna för att fullgöras av användarens butik för den valda ordern kommer att visas.</span><span class="sxs-lookup"><span data-stu-id="ab830-135">Only order lines that are open for fulfillment by the user's store for the selected order will be displayed.</span></span>

- <span data-ttu-id="ab830-136">**Redigera** – tillåter att användare ändrar den valda kundordern.</span><span class="sxs-lookup"><span data-stu-id="ab830-136">**Edit** – Allows users to make changes to the selected customer order.</span></span> <span data-ttu-id="ab830-137">Order kan endast redigeras i [vissa scenarier](customer-orders-overview.md#edit-an-existing-customer-order).</span><span class="sxs-lookup"><span data-stu-id="ab830-137">Orders are only editable in [certain scenarios](customer-orders-overview.md#edit-an-existing-customer-order).</span></span>

- <span data-ttu-id="ab830-138">**Upphämtning** – Det här alternativet är tillgängligt om ordern har en eller flera rader angivna för upphämtning i användarens aktuella butik.</span><span class="sxs-lookup"><span data-stu-id="ab830-138">**Pick up** – This option will be available if the order has one or more lines designated for pickup at the user's current store.</span></span> <span data-ttu-id="ab830-139">Denna åtgärd startar upphämtningsflödet, vilket innebär att användaren kan välja produkter som ska hämtas och skapa en transaktion för upphämtningsförsäljning.</span><span class="sxs-lookup"><span data-stu-id="ab830-139">This operation launches the pickup flow, which allows the user to choose the products to be picked up and creates the pickup sales transaction.</span></span>

## <a name="add-notifications-to-the-recall-order-operation"></a><span data-ttu-id="ab830-140">Lägga till meddelanden i åtgärden för återkallad order</span><span class="sxs-lookup"><span data-stu-id="ab830-140">Add notifications to the recall order operation</span></span>

<span data-ttu-id="ab830-141">I version 10.0.18 och senare kan du konfigurera POS-meddelanden och live-panelnotifieringar för åtgärden **återkalla order** om så önskas.</span><span class="sxs-lookup"><span data-stu-id="ab830-141">In version 10.0.18 and later, you can configure POS notifications and live tile alerts for the **Order Recall** operation if desired.</span></span> <span data-ttu-id="ab830-142">Mer information finns i [Visa ordermeddelanden i kassan (POS)](notifications-pos.md).</span><span class="sxs-lookup"><span data-stu-id="ab830-142">For more information, see [Show order notifications in the point of sale (POS)](notifications-pos.md).</span></span>  

[!INCLUDE[footer-include](../includes/footer-banner.md)]
