---
title: Lagerställets lagerjustering
description: Detta ämne tillhandahåller information om lagerjusteringsjournal och bearbetning när du använder skalningsenheter.
author: perlynne
ms.date: 04/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSInventoryAdjustmentJournal, InventJournalCount
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: SCM
ms.author: perlynne
ms.search.validFrom: 2021-04-21
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 1bf147ce430d84980516d8d4824081ee2a9321a2
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/17/2021
ms.locfileid: "6271242"
---
# <a name="warehouse-inventory-adjustment"></a><span data-ttu-id="bb31d-103">Lagerställets lagerjustering</span><span class="sxs-lookup"><span data-stu-id="bb31d-103">Warehouse inventory adjustment</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="bb31d-104">Funktionen för lagerjustering används när molnbaserade enheter och kantskalningsenheter körs för [arbetsbelastningar inom tillverkning](cloud-edge-workload-manufacturing.md) samt [arbetsbelastningar inom Warehouse management](cloud-edge-workload-warehousing.md).</span><span class="sxs-lookup"><span data-stu-id="bb31d-104">The Warehouse inventory adjustment feature is used when running cloud and edge scale units for [manufacturing workloads](cloud-edge-workload-manufacturing.md) and [warehouse management workloads](cloud-edge-workload-warehousing.md).</span></span>

<span data-ttu-id="bb31d-105">När en medarbetare utför en lagerjustering med hjälp av Warehouse managementsappen mot en Warehouse managementsarbetsbelastning med skalningsenheter, måste den fysiska uppdateringen av lagerbehållningen bearbetas av batchjobbet **Justeringsjournal för lager**, som du kör och schemalägger via **Warehouse management > Periodiska uppgifter > Justeringsjournal för lagerställe**.</span><span class="sxs-lookup"><span data-stu-id="bb31d-105">When a worker does an inventory adjustment using the warehouse app against a scale unit warehouse management workload, the physical on-hand update must be processed by the **Warehouse inventory adjustment journal** batch job, which you run and schedule by going to **Warehouse management > Periodic tasks > Warehouse inventory adjustment journal**.</span></span>

<span data-ttu-id="bb31d-106">Följande arbetsprocesser i appar för lagerställe använder för närvarande **lagerjusteringsjournalen för lagerställe** på arbetsbelastningar med skalning:</span><span class="sxs-lookup"><span data-stu-id="bb31d-106">The following warehouse app work processes currently use the **Warehouse inventory adjustment journal** on scale unit workloads:</span></span>

- <span data-ttu-id="bb31d-107">Justering in/ut</span><span class="sxs-lookup"><span data-stu-id="bb31d-107">Adjustment in/out</span></span>
- <span data-ttu-id="bb31d-108">Rullande inventering</span><span class="sxs-lookup"><span data-stu-id="bb31d-108">Cycle counting</span></span>
- <span data-ttu-id="bb31d-109">Läs in registreringsskylt</span><span class="sxs-lookup"><span data-stu-id="bb31d-109">License plate loading</span></span>

<span data-ttu-id="bb31d-110">Ett flertal lagertransaktioner skapas som ett led i varje lagerjusteringsprocess, eftersom distributionen för nav och skalningsenheter delar samma lagerposter.</span><span class="sxs-lookup"><span data-stu-id="bb31d-110">Several inventory transactions are created as part of each inventory adjustment process because the hub and scale unit deployments share the inventory records.</span></span>

## <a name="inventory-adjustment-example"></a><span data-ttu-id="bb31d-111">Lagerjusteringsexempel</span><span class="sxs-lookup"><span data-stu-id="bb31d-111">Inventory adjustment example</span></span>

<span data-ttu-id="bb31d-112">I det här exemplet har en lagerställearbetare använt lagerställeappen för att registrera tillägget av lagerbehållning.</span><span class="sxs-lookup"><span data-stu-id="bb31d-112">In this example, a warehouse worker has used the warehouse app to register the adding of on-hand inventory.</span></span>

<span data-ttu-id="bb31d-113">Först skapar arbetsbelastningen för skalningsenheten en lagerjusteringstransaktion för den positiva fysiska justeringen, som sedan synkroniseras med navet och leder till en ökning av lagerbehållningen i navet.</span><span class="sxs-lookup"><span data-stu-id="bb31d-113">First, the scale unit workload creates a warehouse inventory adjustment transaction for the positive physical adjustment, which is then synchronized to the hub and results in an increase of the on-hand inventory on the hub.</span></span>

| <span data-ttu-id="bb31d-114">Typ</span><span class="sxs-lookup"><span data-stu-id="bb31d-114">Type</span></span>                                    | <span data-ttu-id="bb31d-115">Skalningsenhet</span><span class="sxs-lookup"><span data-stu-id="bb31d-115">Scale unit</span></span> | <span data-ttu-id="bb31d-116">Riktning</span><span class="sxs-lookup"><span data-stu-id="bb31d-116">Direction</span></span> | <span data-ttu-id="bb31d-117">Hubb</span><span class="sxs-lookup"><span data-stu-id="bb31d-117">Hub</span></span> |
|-----------------------------------------|------------|-----------|-----|
| <span data-ttu-id="bb31d-118">Lagerställets lagerjustering</span><span class="sxs-lookup"><span data-stu-id="bb31d-118">Warehouse inventory adjustment</span></span>          | <span data-ttu-id="bb31d-119">+1</span><span class="sxs-lookup"><span data-stu-id="bb31d-119">+1</span></span>         | ->        | <span data-ttu-id="bb31d-120">+1</span><span class="sxs-lookup"><span data-stu-id="bb31d-120">+1</span></span>  |

<span data-ttu-id="bb31d-121">Navet bearbetar sedan en inventeringsjournalbokföring som tas emot via [meddelanden i meddelandeprocessorn](cloud-edge-message-processor-messages.md).</span><span class="sxs-lookup"><span data-stu-id="bb31d-121">The hub then processes a counting journal posting, which is received through [message processor messages](cloud-edge-message-processor-messages.md).</span></span> <span data-ttu-id="bb31d-122">Då uppdateras den ytterligare lagerbehållningen.</span><span class="sxs-lookup"><span data-stu-id="bb31d-122">This updates the additional inventory on hand.</span></span> <span data-ttu-id="bb31d-123">För att förhindra dubbel lagerbehållning skapar navet en mottransaktion som en del i processen, och tar bort den tidigare registrerade lagerbehållningen som är kopplad till lagerjusteringen av lagerstället.</span><span class="sxs-lookup"><span data-stu-id="bb31d-123">To prevent double inventory on hand, the hub creates an offset transaction as part of this process and removes the previously recorded on-hand inventory that is related to the warehouse inventory adjustment.</span></span>

| <span data-ttu-id="bb31d-124">Typ</span><span class="sxs-lookup"><span data-stu-id="bb31d-124">Type</span></span>                                    | <span data-ttu-id="bb31d-125">Skalningsenhet</span><span class="sxs-lookup"><span data-stu-id="bb31d-125">Scale unit</span></span> | <span data-ttu-id="bb31d-126">Riktning</span><span class="sxs-lookup"><span data-stu-id="bb31d-126">Direction</span></span> | <span data-ttu-id="bb31d-127">Hubb</span><span class="sxs-lookup"><span data-stu-id="bb31d-127">Hub</span></span> |
|-----------------------------------------|------------|-----------|-----|
| <span data-ttu-id="bb31d-128">Inventering</span><span class="sxs-lookup"><span data-stu-id="bb31d-128">Counting</span></span>                                | <span data-ttu-id="bb31d-129">+1</span><span class="sxs-lookup"><span data-stu-id="bb31d-129">+1</span></span>         | <-        | <span data-ttu-id="bb31d-130">+1</span><span class="sxs-lookup"><span data-stu-id="bb31d-130">+1</span></span>  |
| <span data-ttu-id="bb31d-131">Lagerjustering för lagerställe (motbokning)</span><span class="sxs-lookup"><span data-stu-id="bb31d-131">Warehouse inventory adjustment (Offset)</span></span> | <span data-ttu-id="bb31d-132">-1</span><span class="sxs-lookup"><span data-stu-id="bb31d-132">-1</span></span>         | <-        | <span data-ttu-id="bb31d-133">-1</span><span class="sxs-lookup"><span data-stu-id="bb31d-133">-1</span></span>  |

<span data-ttu-id="bb31d-134">När en skalningsenhet har skapat en **lagerjusteringsjournal** i navet kan du granska både **Inventeringsjournal** och **Motbokningsjournal** som skapas av navet som ett led i justeringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="bb31d-134">After a scale unit has created a **Warehouse inventory adjustment journal** on the hub, you can review both the **Counting journal** and the **Offset journal**, which are created by the hub as part of the adjustment process.</span></span>

<span data-ttu-id="bb31d-135">Du kan granska alla dessa journalposter och transaktioner i Supply Chain Management genom att göra följande:</span><span class="sxs-lookup"><span data-stu-id="bb31d-135">You can review each of these journal entries and transaction in Supply Chain Management by doing the following steps:</span></span>

1. <span data-ttu-id="bb31d-136">Logga in på skalningsenheten.</span><span class="sxs-lookup"><span data-stu-id="bb31d-136">Sign in on the scale unit.</span></span>
1. <span data-ttu-id="bb31d-137">Gå till **Warehouse management \> Periodiska uppgifter \> Lagerjusteringsjournal**.</span><span class="sxs-lookup"><span data-stu-id="bb31d-137">Go to **Warehouse management \> Periodic tasks \> Warehouse inventory adjustment journal**.</span></span>
1. <span data-ttu-id="bb31d-138">På sidan **Lagerjusteringsjournal** hittar och öppnar du journalen som registrerade lagerbehållningsändringen.</span><span class="sxs-lookup"><span data-stu-id="bb31d-138">On the **Warehouse inventory adjustment journal** page, find and open the journal that recorded the on-hand inventory change.</span></span> <span data-ttu-id="bb31d-139">I avsnittet **Journalradet** visas varje justering som registrerats i den här journalen.</span><span class="sxs-lookup"><span data-stu-id="bb31d-139">The **Journal lines** section shows each adjustment recorded by this journal.</span></span>
1. <span data-ttu-id="bb31d-140">Logga in på navet.</span><span class="sxs-lookup"><span data-stu-id="bb31d-140">Sign in on the hub.</span></span>
1. <span data-ttu-id="bb31d-141">Gå till **Warehouse management \> Periodiska uppgifter \> Lagerjusteringsjournal**.</span><span class="sxs-lookup"><span data-stu-id="bb31d-141">Go to **Warehouse management \> Periodic tasks \> Warehouse inventory adjustment journal**.</span></span>
1. <span data-ttu-id="bb31d-142">På sidan **Lagerjusteringsjournal** bör du se samma journal i listan om navet och skalningsenheten har synkroniserats.</span><span class="sxs-lookup"><span data-stu-id="bb31d-142">On the **Warehouse inventory adjustment journal** page, you should see the same journal listed if the hub and scale unit have synced.</span></span>
1. <span data-ttu-id="bb31d-143">Öppna journalen.</span><span class="sxs-lookup"><span data-stu-id="bb31d-143">Open the journal.</span></span> <span data-ttu-id="bb31d-144">Om [meddelandena i meddelandeprocessorn](cloud-edge-message-processor-messages.md) har bearbetats visas länkar till **inventeringsjournalen** och **motbokningsjournalen** i rubriken.</span><span class="sxs-lookup"><span data-stu-id="bb31d-144">If the [message processor messages](cloud-edge-message-processor-messages.md) have been processed, you will see links to the **Counting journal** and the **Offset journal** in the header.</span></span>
    - <span data-ttu-id="bb31d-145">**Inventeringsjournalen** ska visa samma dimensionsvärden som journalraderna.</span><span class="sxs-lookup"><span data-stu-id="bb31d-145">The **Counting journal** should show the same dimension values as the journal lines.</span></span>
    - <span data-ttu-id="bb31d-146">**Motbokningsjournalen** ska visa motbokningen, vilket tar bort den dubbla lagerjusteringen.</span><span class="sxs-lookup"><span data-stu-id="bb31d-146">The **Offset journal** should show the offset, which removes the double inventory adjustment.</span></span>
    > [!NOTE]
    > <span data-ttu-id="bb31d-147">När all synkronisering och bearbetning är klar synkroniseras **inventeringsjournalen** och **motbokningsjournalen** tillbaka till skalningsenheten.</span><span class="sxs-lookup"><span data-stu-id="bb31d-147">When all syncing and processing is complete, the **Counting journal** and the **Offset journal** are synced back to the scale unit.</span></span> <span data-ttu-id="bb31d-148">Dessa kan även visas från relevant **journalsida för lagerjustering**.</span><span class="sxs-lookup"><span data-stu-id="bb31d-148">These can also be viewed from the relevant **Warehouse inventory adjustment journal** page.</span></span>
