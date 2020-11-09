---
title: Ställa in klusterplockning
description: Det här avsnittet beskriver hur du konfigurerar klusterplockning och hur du tillämpar artikelbekräftelse med klusterplockning.
author: Mirzaab
manager: tfehr
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSClusterProfile, WHSRFAutoConfirm, WHSWorkCluster
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 009345e608c26887fedbe4a9c268367080593da2
ms.sourcegitcommit: a36a4f9915ae3eb36bf8220111cf1486387713d9
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/16/2020
ms.locfileid: "4017585"
---
# <a name="set-up-cluster-picking"></a><span data-ttu-id="3e9ea-103">Ställa in klusterplockning</span><span class="sxs-lookup"><span data-stu-id="3e9ea-103">Set up cluster picking</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="3e9ea-104">I det här avsnittet beskrivs hur du möjliggör för en arbetare att använda sin mobila enhet för att gruppera plockningarbete till kluster, så att de kan plocka artiklar från en enda plats för flera arbetsordrar samtidigt.</span><span class="sxs-lookup"><span data-stu-id="3e9ea-104">This topic describes how to enable workers to use their mobile devices to group picking work into clusters, so that they can pick items from a single location for multiple work orders at the same time.</span></span> <span data-ttu-id="3e9ea-105">Detta kallas *klusterplockning*.</span><span class="sxs-lookup"><span data-stu-id="3e9ea-105">This is called *cluster picking*.</span></span>

## <a name="about-cluster-picking"></a><span data-ttu-id="3e9ea-106">Om klusterplockning</span><span class="sxs-lookup"><span data-stu-id="3e9ea-106">About cluster picking</span></span>

<span data-ttu-id="3e9ea-107">När arbetsorder har frisläppts till lagerstället kan arbetare använda en mobil enhet för att tilldela order till ett kluster.</span><span class="sxs-lookup"><span data-stu-id="3e9ea-107">After work orders are released to the warehouse, the worker can use a mobile device to assign the orders to a cluster.</span></span> <span data-ttu-id="3e9ea-108">Klustret ordnar plockningsarbetet för arbetaren.</span><span class="sxs-lookup"><span data-stu-id="3e9ea-108">The cluster will organize the picking work for the worker.</span></span> <span data-ttu-id="3e9ea-109">När en arbetsorder tilldelas ett kluster, måste arbetaren använda klusterplockning för att utföra plockningsarbetet för ordern.</span><span class="sxs-lookup"><span data-stu-id="3e9ea-109">When a work order is assigned to a cluster, the worker must use cluster picking to perform the picking work for the order.</span></span> <span data-ttu-id="3e9ea-110">Arbetaren kan inte använda andra plockningsmetoder.</span><span class="sxs-lookup"><span data-stu-id="3e9ea-110">The worker cannot use other picking methods.</span></span> <span data-ttu-id="3e9ea-111">Om en arbetsorder tilldelas ett kluster av misstag måste arbetaren bryta klustret och sedan återskapa det.</span><span class="sxs-lookup"><span data-stu-id="3e9ea-111">If a work order is assigned to a cluster by mistake, the worker must break the cluster and then re-create it.</span></span>

<span data-ttu-id="3e9ea-112">Om det behövs kan en anställd skicka ett kluster till en annan arbetare.</span><span class="sxs-lookup"><span data-stu-id="3e9ea-112">If needed, a worker can pass a cluster to another worker.</span></span> <span data-ttu-id="3e9ea-113">Detta ändrar klusterstatus till Klarat.</span><span class="sxs-lookup"><span data-stu-id="3e9ea-113">This changes the cluster status to Passed.</span></span> <span data-ttu-id="3e9ea-114">När arbetstagaren använder en mobil enhet för att ange att plockningen och det inlagrade arbetet är slutfört måste leveransen eller lasten bekräftas i klienten.</span><span class="sxs-lookup"><span data-stu-id="3e9ea-114">When the worker uses a mobile device to indicate that the picking and put away work is completed, the shipment or load must be confirmed in the client.</span></span>

## <a name="enable-cluster-picking"></a><span data-ttu-id="3e9ea-115">Aktivera klusterplockning</span><span class="sxs-lookup"><span data-stu-id="3e9ea-115">Enable cluster picking</span></span>

<span data-ttu-id="3e9ea-116">Om du vill aktivera klusterplockning måste du ställa in följande:</span><span class="sxs-lookup"><span data-stu-id="3e9ea-116">To enable cluster picking, you must set up the following:</span></span>

- <span data-ttu-id="3e9ea-117">**Klusterprofiler** – Ange om kluster-ID:n ska genereras automatiskt, antalet positioner som ska användas, när kluster ska brytas och plockarbetet ska ordnas och verifieras.</span><span class="sxs-lookup"><span data-stu-id="3e9ea-117">**Cluster profiles** – Specify whether to automatically generate cluster   IDs, the number of positions to use, when to break clusters, and how to   sequence and verify the picking work.</span></span>

- <span data-ttu-id="3e9ea-118">**Arbetsmallar** – Ange hur plockningsarbetet för klusterplockning ska skapas.</span><span class="sxs-lookup"><span data-stu-id="3e9ea-118">**Work templates** – Define how to create the picking work for cluster   picking.</span></span>

- <span data-ttu-id="3e9ea-119">**Platsdirektiv** – Ange var artiklar ska plockas ifrån och var du vill placera dem.</span><span class="sxs-lookup"><span data-stu-id="3e9ea-119">**Location directives** – Specify where to pick items from, and where to put   them.</span></span>

- <span data-ttu-id="3e9ea-120">**Menyalternativ på mobil enhet** – Konfigurera ett menyalternativ för mobila enheter för att använda befintligt arbete som dirigeras av klusterplockning.</span><span class="sxs-lookup"><span data-stu-id="3e9ea-120">**Mobile device menu items** – Configure a mobile device menu item to use existing work that is directed by cluster picking.</span></span> <span data-ttu-id="3e9ea-121">Du måste sedan lägga till menykommandot på en meny för mobil enhet så att det visas på mobila enheter.</span><span class="sxs-lookup"><span data-stu-id="3e9ea-121">You must then add the menu item to a mobile device menu so that it is displayed on mobile devices.</span></span>

- <span data-ttu-id="3e9ea-122">**Parametrar för lagerstyrning** – Ange nummerserien som ska användas, om du vill generera identifierare för kluster.</span><span class="sxs-lookup"><span data-stu-id="3e9ea-122">**Warehouse management parameters** – Specify the number sequence to use if   you want to generate identifiers for clusters.</span></span>

## <a name="set-up-a-cluster-profile"></a><span data-ttu-id="3e9ea-123">Ställa in en klusterprofil</span><span class="sxs-lookup"><span data-stu-id="3e9ea-123">Set up a cluster profile</span></span>

<span data-ttu-id="3e9ea-124">Så här ställer du in en klusterprofil:</span><span class="sxs-lookup"><span data-stu-id="3e9ea-124">To set up a cluster profile, follow these steps:</span></span>

1. <span data-ttu-id="3e9ea-125">Klicka på **Lagerstyrning** \> **Inställningar** \> **Mobil enhet** \>  **Klusterprofiler**.</span><span class="sxs-lookup"><span data-stu-id="3e9ea-125">Click **Warehouse management** \> **Setup** \> **Mobile device** \>  **Cluster profiles**.</span></span>

1. <span data-ttu-id="3e9ea-126">Klicka på **Ny** om du vill skapa en ny profil.</span><span class="sxs-lookup"><span data-stu-id="3e9ea-126">Click **New** to create a new profile.</span></span>

1. <span data-ttu-id="3e9ea-127">Klicka på **Skapa kluster** och under **Klustersortering** , klickar du på **Ny** för att ställa in sorteringskriterier för klustret.</span><span class="sxs-lookup"><span data-stu-id="3e9ea-127">Click **Create cluster** and, under **Cluster sorting** , click **New** to set up the sorting criteria for the cluster.</span></span> <span data-ttu-id="3e9ea-128">Sorteringskriteriet kontrollerar den följd i vilken arbetaren ska utföra plockningsarbetet.</span><span class="sxs-lookup"><span data-stu-id="3e9ea-128">The sorting criteria control the order in which the worker will perform the picking work.</span></span> <span data-ttu-id="3e9ea-129">Du kan lägga till så många villkor du vill.</span><span class="sxs-lookup"><span data-stu-id="3e9ea-129">You can add as many criteria as needed.</span></span>

1. <span data-ttu-id="3e9ea-130">I fältet **Sekvensnummer** anger du ett värde som definierar i vilken ordning sorteringskriterierna ska bearbetas.</span><span class="sxs-lookup"><span data-stu-id="3e9ea-130">In the **Sequence number** field, enter a number to define the order in  which the sorting criteria are processed.</span></span>

1. <span data-ttu-id="3e9ea-131">Markera fältet som fastställer sorteringen i fältet **Fältnamn**.</span><span class="sxs-lookup"><span data-stu-id="3e9ea-131">In the **Field name** field, select the field that will determine the sorting.</span></span> <span data-ttu-id="3e9ea-132">Om du till exempel väljer fältet **WMSLocationId** kommer arbetet att sorteras efter plats.</span><span class="sxs-lookup"><span data-stu-id="3e9ea-132">For example, if you select the **WMSLocationId** field, the work will be sorted by location.</span></span>

1. <span data-ttu-id="3e9ea-133">Välj ett av följande alternativ i fältet **Sortering**.</span><span class="sxs-lookup"><span data-stu-id="3e9ea-133">In the **Sorting** field, select one of the following options.</span></span>

| <span data-ttu-id="3e9ea-134">**Alternativ**</span><span class="sxs-lookup"><span data-stu-id="3e9ea-134">**Option**</span></span>     | <span data-ttu-id="3e9ea-135">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="3e9ea-135">**Description**</span></span>                                                                                                                                                                                                                    |
|----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="3e9ea-136">**Stigande**</span><span class="sxs-lookup"><span data-stu-id="3e9ea-136">**Ascending**</span></span>  | <span data-ttu-id="3e9ea-137">Plockningsarbete sorteras i en stigande ordning som baseras på sorteringskriteriet.</span><span class="sxs-lookup"><span data-stu-id="3e9ea-137">Picking work is sequenced in ascending order based on the sorting criteria.</span></span> <span data-ttu-id="3e9ea-138">Om du till exempel använder fältet **WMSLocationId** som sorteringsvillkor och dina plats-ID:n är 1, 2, 3 och 4 ska du plocka från plats 4 först.</span><span class="sxs-lookup"><span data-stu-id="3e9ea-138">For example, if you use the **WMSLocationId** field as sorting criteria, and your location IDs are 1, 2, 3, and 4, you will pick from location 4 first.</span></span> |
| <span data-ttu-id="3e9ea-139">**Fallande**</span><span class="sxs-lookup"><span data-stu-id="3e9ea-139">**Descending**</span></span> | <span data-ttu-id="3e9ea-140">Plockningsarbete sorteras i en fallande ordning som baseras på sorteringskriteriet.</span><span class="sxs-lookup"><span data-stu-id="3e9ea-140">Picking work is sequenced in descending order based on the sorting criteria.</span></span> <span data-ttu-id="3e9ea-141">Om du till exempel använder fältet **WMSLocationId** som sorteringsvillkor och dina plats-ID:n är 1, 2, 3 och 4 ska du plocka från plats 1 först.</span><span class="sxs-lookup"><span data-stu-id="3e9ea-141">For example, if you use the **WMSLocationId** field as sorting criteria, and your location IDs are 1, 2, 3, and 4, you will pick from location 1 first.</span></span> |

## <a name="item-confirmation"></a><span data-ttu-id="3e9ea-142">Artikelbekräftelse</span><span class="sxs-lookup"><span data-stu-id="3e9ea-142">Item confirmation</span></span>

<span data-ttu-id="3e9ea-143">När klusterplockning används, är objektbekräftelse avgörande för att kontrollera de objekt som läggs till ett kluster.</span><span class="sxs-lookup"><span data-stu-id="3e9ea-143">When cluster picking is applied, item confirmation is crucial to verify the items that are added to clusters.</span></span> <span data-ttu-id="3e9ea-144">Du kan kontrollera objekt i klusterplockning vid klusterplockningsprocessen.</span><span class="sxs-lookup"><span data-stu-id="3e9ea-144">You can verify items in cluster picking during the cluster picking process.</span></span> <span data-ttu-id="3e9ea-145">Inställningen är baserad på inställning av produktstreckkoder.</span><span class="sxs-lookup"><span data-stu-id="3e9ea-145">The setup is based on the product bar code setup.</span></span>

### <a name="set-up-item-verification-with-cluster-picking"></a><span data-ttu-id="3e9ea-146">Ställa in objektverifiering med klusterplockning</span><span class="sxs-lookup"><span data-stu-id="3e9ea-146">Set up item verification with cluster picking</span></span>

1. <span data-ttu-id="3e9ea-147">I den mobila enhetens menyalternativ öppnar du inställningsformuläret för arbetsbekräftelse: **Hantering av lagerställe** \> **Hantering av lagerställe** \> **Inställningar** \>  **Mobil enhet** \> **Menyobjekt för mobil enhet**.</span><span class="sxs-lookup"><span data-stu-id="3e9ea-147">On a mobile device menu item, open the setup form for work confirmation:  **Warehouse management** \> **Warehouse management** \> **Setup** \>  **Mobile device** \> **Mobile device menu items**.</span></span>

1. <span data-ttu-id="3e9ea-148">Från mobila enhetens menyalternativ öppnar du **Inställning av arbetsbekräftelse**.</span><span class="sxs-lookup"><span data-stu-id="3e9ea-148">From the mobile device menu item, open **Work confirmation setup**.</span></span> <span data-ttu-id="3e9ea-149">Alternativet **Produktbekräftelse** låter dig kontrollera varje lagerenhet från den mobila enheten när du har skannat.</span><span class="sxs-lookup"><span data-stu-id="3e9ea-149">The **Product confirmation** option allows you to verify each piece of inventory from the mobile device when scanned.</span></span>
