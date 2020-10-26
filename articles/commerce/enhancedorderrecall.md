---
title: Åtgärden återkalla order i kassan
description: Det här avsnittet handlar om vilka funktioner som finns för att förbättra sidor för orderåterkallning i kassan.
author: hhainesms
manager: annbe
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: global
ms.author: hhaines
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 41944fb7819b5527f6bc023a60acd9450d9e43c2
ms.sourcegitcommit: 25909c6ad3616e4f75a2fe006057dda18d7cc856
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/09/2020
ms.locfileid: "3974848"
---
# <a name="recall-order-operation-in-pos"></a><span data-ttu-id="b70f2-103">Åtgärden återkalla order i kassan</span><span class="sxs-lookup"><span data-stu-id="b70f2-103">Recall order operation in POS</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="b70f2-104">Åtgärden återkallningsorder i Commerce kassa ger uppdaterade funktioner för ordersökning och filtrering och orderspecifik information.</span><span class="sxs-lookup"><span data-stu-id="b70f2-104">The Recall order operation in the Commerce point of sale (POS) provides updated order search and filtering features and order-specific information.</span></span> <span data-ttu-id="b70f2-105">Den här funktionen är tillgänglig i Commerce versioner 10.0.15 och senare.</span><span class="sxs-lookup"><span data-stu-id="b70f2-105">This feature is available in Commerce versions 10.0.15 and later.</span></span>

<span data-ttu-id="b70f2-106">För att aktivera denna funktion, slå på funktionen **Förbättrad åtgärden återkalla order i kassan** i arbetsytan **funktionshantering** i Commerce-administration.</span><span class="sxs-lookup"><span data-stu-id="b70f2-106">To enable this functionality, turn the **Improved Recall order operation in POS** feature on in **Feature management** workspace in Commerce headquarters.</span></span> <span data-ttu-id="b70f2-107">När du har aktiverat funktionen kan du överväga att uppdatera [bildskärmslayouter](pos-screen-layouts.md) i kassan för att dra nytta av vissa av de ändrade funktionerna.</span><span class="sxs-lookup"><span data-stu-id="b70f2-107">After you enable the feature, consider updating your [screen layouts](pos-screen-layouts.md) in POS to take advantage of some of the changed  capabilities.</span></span>

<span data-ttu-id="b70f2-108">Genom att konfigurera knappen **Återkalla order** kan organisationer distribuera operationen med en fördefinierad visning.</span><span class="sxs-lookup"><span data-stu-id="b70f2-108">The configuration of the **Recall order** operation button allows organizations to deploy the operation with a pre-defined display.</span></span>

![Konfiguration av knapprutnät](media/recallorderbuttongrid.png)

<span data-ttu-id="b70f2-110">Visningsalternativen är följande.</span><span class="sxs-lookup"><span data-stu-id="b70f2-110">The display options are as follows.</span></span>
- <span data-ttu-id="b70f2-111">**Inget** – det här alternativet distribuerar åtgärden utan specifik visning.</span><span class="sxs-lookup"><span data-stu-id="b70f2-111">**None** – This option deploys the operation with no specific display.</span></span> <span data-ttu-id="b70f2-112">När en användare öppnar åtgärden med den här konfigurationen uppmanas de att söka efter order eller välja från ett fördefinierat orderfilter.</span><span class="sxs-lookup"><span data-stu-id="b70f2-112">When a user opens the operation with this configuration, they will be prompted to search and find orders or choose from a pre-defined order filter.</span></span>
- <span data-ttu-id="b70f2-113">**Order som ska uppfyllas** – när en användare startar operationen körs en fråga automatiskt för att söka i och visa en lista med order som ska uppfyllas av butiken.</span><span class="sxs-lookup"><span data-stu-id="b70f2-113">**Orders to fulfill** – When a user launches the operation, a query will run automatically to search and display a list of orders that are to be fulfilled by the store.</span></span> <span data-ttu-id="b70f2-114">Dessa order konfigureras för butikshämtning eller butiksleverans och raderna på dessa order har ännu inte plockats eller packats.</span><span class="sxs-lookup"><span data-stu-id="b70f2-114">These orders are configured for in-store pickup or store shipment and the lines of these orders have not yet been picked or packed.</span></span>
- <span data-ttu-id="b70f2-115">**Order som ska plockas** – när en användare startar operationen körs en fråga automatiskt för att söka i och visa en lista med order som är konfigurerade för hämtning i butik eller i användarens nuvarande butik.</span><span class="sxs-lookup"><span data-stu-id="b70f2-115">**Orders to pick up** – When a user launches the operation, a query will run automatically to search and display a list of orders that are configured for in-store pickup at the user's current store.</span></span>
- <span data-ttu-id="b70f2-116">**Order som ska levereras** – när en användare startar operationen körs en fråga automatiskt för att söka i och visa en lista med order som är konfigurerade för leverans från användarens nuvarande butik.</span><span class="sxs-lookup"><span data-stu-id="b70f2-116">**Orders to ship** - When a user launches the operation, a query will run automatically to search and display a list of orders that are configured for shipment from the user's current store.</span></span>

<span data-ttu-id="b70f2-117">När du startar åtgärden **Återkalla order** från kassan, om bildskärmen har konfigurerats till **ingen** kan en användare söka efter och hämta order på något av följande sätt.</span><span class="sxs-lookup"><span data-stu-id="b70f2-117">When launching the **Recall order** operation from POS, if the display is configured to **None**, a user will be able to search and retrieve orders in one of the following ways.</span></span>
- <span data-ttu-id="b70f2-118">Skanna orderstreckkoder.</span><span class="sxs-lookup"><span data-stu-id="b70f2-118">Scan order barcodes.</span></span> <span data-ttu-id="b70f2-119">Det här fältet söker efter ordernummer, kanalreferens och kvitto-ID för matchningar.</span><span class="sxs-lookup"><span data-stu-id="b70f2-119">This will search order number, channel reference, and receipt ID fields for matches.</span></span>
- <span data-ttu-id="b70f2-120">Välj ikonen **Sök order** eller **Sök och filtrera** på AppBar om du vill använda filtreringsfunktionen för att söka efter order som uppfyller filtervillkoren.</span><span class="sxs-lookup"><span data-stu-id="b70f2-120">Select **Search orders** or **Search and filter** icon on the AppBar to use the filtering mechanism to locate orders that meet the filter criteria.</span></span>
- <span data-ttu-id="b70f2-121">Välj från ett fördefinierat filter på listrutan **Visa order** (order som ska uppfyllas, order som ska plockas eller order som ska levereras).</span><span class="sxs-lookup"><span data-stu-id="b70f2-121">Choose from a pre-defined filter from the **Show Orders** drop-down menu (orders to fulfill, orders to pick up, or orders to ship).</span></span>

![RecallOrderMainMenu](media/recallordermain.png)

<span data-ttu-id="b70f2-123">När sökkriterier har tillämpats visas en lista med matchande försäljningsorder i programmet.</span><span class="sxs-lookup"><span data-stu-id="b70f2-123">After search criteria are applied, the application will display a list of matching sales orders.</span></span>

![RecallOrderDetail](media/orderrecalldetail.png)

<span data-ttu-id="b70f2-125">En användare kan välja en order i listan om du vill visa mer information.</span><span class="sxs-lookup"><span data-stu-id="b70f2-125">A user can select an order on the list to view additional details.</span></span> <span data-ttu-id="b70f2-126">Informationspanelen till höger på skärmen visar specifika uppgifter för den valda ordern, inklusive order raddetaljer, leveransinformation och information om uppfyllelse.</span><span class="sxs-lookup"><span data-stu-id="b70f2-126">The information panel on the right side of the screen displays specifics on the selected order, including order line details, delivery details, and fulfillment details.</span></span>

<span data-ttu-id="b70f2-127">En användare kan välja en operation i AppBar.</span><span class="sxs-lookup"><span data-stu-id="b70f2-127">From the AppBar, a user can select an operation.</span></span> <span data-ttu-id="b70f2-128">Beroende på orderns status kan vissa operationer inte aktiveras.</span><span class="sxs-lookup"><span data-stu-id="b70f2-128">Depending on the status of the order, certain operations may not be enabled.</span></span>

- <span data-ttu-id="b70f2-129">**Retur** – kör en retur för en eller flera fakturor som hör till den valda kundordern.</span><span class="sxs-lookup"><span data-stu-id="b70f2-129">**Return** – Executes a return for one or more invoices related to the selected customer order.</span></span>

- <span data-ttu-id="b70f2-130">**Avbryt** – utfärda en fullständig annullering av den valda försäljningsordern.</span><span class="sxs-lookup"><span data-stu-id="b70f2-130">**Cancel** – Issue a full cancellation of the selected sales order.</span></span>

- <span data-ttu-id="b70f2-131">**Uppfyllelse** – överför användaren till sidan orderuppfyllelse, som kommer att filtreras för den valda ordern.</span><span class="sxs-lookup"><span data-stu-id="b70f2-131">**Fulfill** – Transfers the user to the order fulfillment page, which will be pre-filtered for the selected order.</span></span> <span data-ttu-id="b70f2-132">Endast orderrader som är öppna för att fullgöras av användarens butik för den valda ordern kommer att visas.</span><span class="sxs-lookup"><span data-stu-id="b70f2-132">Only order lines that are open for fulfillment by the user's store for the selected order will be displayed.</span></span>

- <span data-ttu-id="b70f2-133">**Redigera** – tillåter att användare ändrar den valda kundordern.</span><span class="sxs-lookup"><span data-stu-id="b70f2-133">**Edit** – Allows users to make changes to the selected customer order.</span></span>

- <span data-ttu-id="b70f2-134">**Hämta** – startar upphämtningsflödet, vilket innebär att användaren kan välja produkter som ska hämtas och skapa en transaktion för upphämtningsförsäljning.</span><span class="sxs-lookup"><span data-stu-id="b70f2-134">**Pick up** – Launches the pickup flow, which allows the user to choose the products to be picked up and creates the pickup sales transaction.</span></span>
