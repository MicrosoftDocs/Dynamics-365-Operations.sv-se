---
title: Fysiska och ekonomiska uppdateringar
description: I det här avsnittet ges en översikt över vilka transaktionstyper som ökar eller minskar lagerkvantiteterna.
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventTrans, InventTransVoucher
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 75023
ms.assetid: 128340e1-c573-48e6-b835-6c350d8dd0fb
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4360f9132d31c9d0038f51c68c1f6c3fcaaa2025
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/30/2019
ms.locfileid: "2250885"
---
# <a name="physical-and-financial-updates"></a><span data-ttu-id="7d370-103">Fysiska och ekonomiska uppdateringar</span><span class="sxs-lookup"><span data-stu-id="7d370-103">Physical and financial updates</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7d370-104">I det här avsnittet ges en översikt över vilka transaktionstyper som ökar eller minskar lagerkvantiteterna.</span><span class="sxs-lookup"><span data-stu-id="7d370-104">This topic provides an overview of which types of transactions increase or decrease inventory quantities.</span></span> 

<span data-ttu-id="7d370-105">Lagertransaktioner kan uppdateras fysiskt och ekonomiskt i Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="7d370-105">Inventory transactions can be physically updated and financially updated in Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="7d370-106">I vissa typer av fysiska och ekonomiska transaktioner ökar lagerkvantiteterna, medan andra minskar kvantiteten.</span><span class="sxs-lookup"><span data-stu-id="7d370-106">Some types of physical and financial transactions increase inventory quantities, whereas others decrease the quantity.</span></span>

## <a name="physical-increases"></a><span data-ttu-id="7d370-107">Fysiska ökningar</span><span class="sxs-lookup"><span data-stu-id="7d370-107">Physical increases</span></span>
<span data-ttu-id="7d370-108">När en fysisk transaktion bokförs får transaktionsposten statusen **Inlevererad**.</span><span class="sxs-lookup"><span data-stu-id="7d370-108">When a physical transaction is posted, the status of the transaction record is **Received**.</span></span> <span data-ttu-id="7d370-109">Följande transaktioner betraktas som fysiska ökningar:</span><span class="sxs-lookup"><span data-stu-id="7d370-109">The following transactions are considered physical increases:</span></span>

-   <span data-ttu-id="7d370-110">Inleverans av inköpsorder</span><span class="sxs-lookup"><span data-stu-id="7d370-110">Purchase order receipt</span></span>
-   <span data-ttu-id="7d370-111">Försäljningsorder, följesedelsretur</span><span class="sxs-lookup"><span data-stu-id="7d370-111">Sales order packing slip return</span></span>
-   <span data-ttu-id="7d370-112">Rapportera en produktionsorder som färdig</span><span class="sxs-lookup"><span data-stu-id="7d370-112">Reporting a production order as finished</span></span>
-   <span data-ttu-id="7d370-113">Biprodukt på plocklista för tillverkningsorder</span><span class="sxs-lookup"><span data-stu-id="7d370-113">By-product on a production order picking list</span></span>

## <a name="financial-increases"></a><span data-ttu-id="7d370-114">Ekonomiska ökningar</span><span class="sxs-lookup"><span data-stu-id="7d370-114">Financial increases</span></span>
<span data-ttu-id="7d370-115">När en ekonomisk inleveranstransaktion bokförs blir statusen för transaktionen som ökar kvantiteten **Inköpt**.</span><span class="sxs-lookup"><span data-stu-id="7d370-115">When a financial receipt transaction is posted, the status of the transaction record that increases the quantity is **Purchased**.</span></span> <span data-ttu-id="7d370-116">Följande transaktioner betraktas som ekonomiska ökningar:</span><span class="sxs-lookup"><span data-stu-id="7d370-116">The following transactions are considered financial increases:</span></span>

-   <span data-ttu-id="7d370-117">Leverantörsfaktura</span><span class="sxs-lookup"><span data-stu-id="7d370-117">Vendor invoice</span></span>
-   <span data-ttu-id="7d370-118">Inköpsorderfaktura för en retur</span><span class="sxs-lookup"><span data-stu-id="7d370-118">Sales order invoice for a return</span></span>
-   <span data-ttu-id="7d370-119">Kostnadskalkylering för tillverkningsorder</span><span class="sxs-lookup"><span data-stu-id="7d370-119">Production order costing</span></span>
-   <span data-ttu-id="7d370-120">Lagerjournaler med positiv kvantitet, t.ex. förflyttningar, resultat, inventeringsjournaler, strukturlistor och överföringar</span><span class="sxs-lookup"><span data-stu-id="7d370-120">Positive quantity inventory journals, such as movement, profit and loss, counting, bill of materials, and transfer</span></span>

## <a name="transactions-that-increase-quantity"></a><span data-ttu-id="7d370-121">Transaktioner som ökar kvantiteten</span><span class="sxs-lookup"><span data-stu-id="7d370-121">Transactions that increase quantity</span></span>
<span data-ttu-id="7d370-122">Transaktioner som ökar kvantiteten bokförs till den löpande genomsnittliga självkostnaden.</span><span class="sxs-lookup"><span data-stu-id="7d370-122">Transactions that increase quantity are posted at the running average cost price.</span></span> <span data-ttu-id="7d370-123">Den beräknade löpande genomsnittliga självkostnaden baseras på kostnaden för respektive transaktion för alla lagerdimensioner som spåras ekonomiskt.</span><span class="sxs-lookup"><span data-stu-id="7d370-123">The calculated running average cost price is based on the cost of each of these transactions for each inventory dimension that is being tracked financially.</span></span> <span data-ttu-id="7d370-124">Mer information om löpande genomsnittliga självkostnaden finns i [Löpande genomsnittlig självkostnad](running-average-cost-price.md).</span><span class="sxs-lookup"><span data-stu-id="7d370-124">For information about running average cost prices, see [Running average cost price](running-average-cost-price.md).</span></span>

## <a name="transactions-that-decrease-quantity"></a><span data-ttu-id="7d370-125">Transaktioner som minskar kvantiteten</span><span class="sxs-lookup"><span data-stu-id="7d370-125">Transactions that decrease quantity</span></span>
<span data-ttu-id="7d370-126">Den beräknade löpande genomsnittliga självkostnaden används när en transaktion som minskar kvantiteten bokförs, oavsett vilken lagermodell som är associerad med lagret.</span><span class="sxs-lookup"><span data-stu-id="7d370-126">The calculated running average cost price is used  when a transaction that decreases quantity is posted, regardless of the inventory model that is associated with that inventory.</span></span> <span data-ttu-id="7d370-127">Transaktionen som minskar kvantiteten får inte tidigare ha markerats till en annan transaktion innan den bokfördes.</span><span class="sxs-lookup"><span data-stu-id="7d370-127">The transaction that decreases quantity must not have been marked to another transaction before it was posted.</span></span> <span data-ttu-id="7d370-128">Om den fysiska lagerbehållningen blir negativ används den lagerkostnad som definierats för artikeln på sidan **Artikel**.</span><span class="sxs-lookup"><span data-stu-id="7d370-128">If the physical on-hand inventory becomes negative, the inventory cost that is defined for the item on the **Item** page is used.</span></span> 

> [!NOTE]
> <span data-ttu-id="7d370-129">Om multisitefunktionen har aktiverats utgörs denna kostnad i stället av den lagerkostnad som definierats för en plats på sidan **Standardorderinställningar** page.</span><span class="sxs-lookup"><span data-stu-id="7d370-129">If multisite functionality is enabled, this cost will instead be the inventory cost that is defined for a site on the **Default order settings** page.</span></span>

## <a name="physical-issues-vs-financial-issues"></a><span data-ttu-id="7d370-130">Fysiska utleveranser kontra ekonomiska problem.</span><span class="sxs-lookup"><span data-stu-id="7d370-130">Physical issues vs. financial issues</span></span>
<span data-ttu-id="7d370-131">När en fysisk utleveranstransaktion bokförs blir transaktionspostens status **Avdragen**.</span><span class="sxs-lookup"><span data-stu-id="7d370-131">When a physical issue transaction is posted, the status of the transaction record is **Deducted**.</span></span> <span data-ttu-id="7d370-132">Följande transaktioner betraktas som fysiska utleveranser:</span><span class="sxs-lookup"><span data-stu-id="7d370-132">The following transactions are considered physical issues:</span></span>

-   <span data-ttu-id="7d370-133">Plocklistejournal för tillverkningsorder</span><span class="sxs-lookup"><span data-stu-id="7d370-133">Production order picking list journal</span></span>
-   <span data-ttu-id="7d370-134">Följesedel för försäljningsorder</span><span class="sxs-lookup"><span data-stu-id="7d370-134">Sales order packing slip</span></span>
-   <span data-ttu-id="7d370-135">Inköpsorder, följesedelsretur</span><span class="sxs-lookup"><span data-stu-id="7d370-135">Purchase order packing slip return</span></span>

<span data-ttu-id="7d370-136">När en ekonomisk transaktion bokförs får transaktionsposten statusen **Såld**.</span><span class="sxs-lookup"><span data-stu-id="7d370-136">When a financial transaction is posted, the status of the transaction record is **Sold**.</span></span> <span data-ttu-id="7d370-137">Följande transaktioner betraktas som ekonomiska utleveranser:</span><span class="sxs-lookup"><span data-stu-id="7d370-137">The following transactions are considered financial issues:</span></span>

-   <span data-ttu-id="7d370-138">Avsluta en produktionsorder</span><span class="sxs-lookup"><span data-stu-id="7d370-138">Ending a production order</span></span>
-   <span data-ttu-id="7d370-139">Försäljningsorderfaktura</span><span class="sxs-lookup"><span data-stu-id="7d370-139">Sales order invoice</span></span>
-   <span data-ttu-id="7d370-140">Leverantörsfakturaretur</span><span class="sxs-lookup"><span data-stu-id="7d370-140">Vendor invoice return</span></span>
-   <span data-ttu-id="7d370-141">Lagerjournaler med negativ kvantitet, t.ex. förflyttningar, resultat, inventeringsjournaler, strukturlistor och överföringar</span><span class="sxs-lookup"><span data-stu-id="7d370-141">Negative quantity inventory journals, such as movement, profit and loss, counting, bill of materials, and transfer</span></span>

<span data-ttu-id="7d370-142">Transaktioner som minskar kvantiteten bokförs till den löpande genomsnittliga självkostnaden.</span><span class="sxs-lookup"><span data-stu-id="7d370-142">Transactions that decrease quantity are posted at the running average cost price.</span></span> <span data-ttu-id="7d370-143">Därför måste lagerstängningsprocessen kvitta utleveranstransaktioner mot inleveranstransaktioner baserat på den lagermodell som har valts för varje artikel.</span><span class="sxs-lookup"><span data-stu-id="7d370-143">Therefore, the inventory close procedure is required in order to settle issue transactions to receipt transactions, based on the inventory model that is assigned to each item.</span></span>
