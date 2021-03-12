---
title: Delleverans av en transportlast
description: Det här avsnittet beskriver hur du delvis levererar en last och skjuter upp planering av kapacitet för lasten.
author: Mirzaab
manager: tfehr
ms.date: 03/15/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSTransportLoad
audience: Application User
ms.reviewer: kamaybac
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 68a3d175e89e89d0909b140863b1aa61a184fce6
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4963295"
---
# <a name="partial-shipment-of-a-transport-load"></a><span data-ttu-id="71f30-103">Delleverans av en transportlast</span><span class="sxs-lookup"><span data-stu-id="71f30-103">Partial shipment of a transport load</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="71f30-104">Genom att ställa in en delleverans av last kan du hantera laster där kapaciteten inte kan bestämmas förrän alla försäljningsrader har lagts till en last.</span><span class="sxs-lookup"><span data-stu-id="71f30-104">By setting up partial shipment of loads, you can handle loads where the capacity can't be determined until all the sales lines have been added to a load.</span></span> <span data-ttu-id="71f30-105">Processen kan sedan slutföras när man vet exakt antal lastpallar.</span><span class="sxs-lookup"><span data-stu-id="71f30-105">The process can then be finalized when the exact pallet count is known.</span></span> <span data-ttu-id="71f30-106">Därför behöver du inte bestämma vilka lastpallar som ska tilldelas till vilket transport tills det ögonblick då en transport fysiskt lastas ur mellanlagret.</span><span class="sxs-lookup"><span data-stu-id="71f30-106">Therefore, you don't have to decide which pallets will be assigned to which transport until the moment when a transport is being physically loaded out of the staged inventory.</span></span>

<span data-ttu-id="71f30-107">Den här funktionen är ett praktiskt alternativ för kontroll av fastare struktur där måste du bestämma vilka lastpallar som tilldelas vilken transport före plockning av arbete eller lastning av arbetet kan skapas.</span><span class="sxs-lookup"><span data-stu-id="71f30-107">This feature offers an alternative to the enforcement of a more rigid structure, where you must determine which pallets will be assigned to which transport before picking work or loading work can be created.</span></span> <span data-ttu-id="71f30-108">Däremot kan användare konfigurera individuella laster för en bekräftelse av delleverans.</span><span class="sxs-lookup"><span data-stu-id="71f30-108">Instead, users can configure individual loads for a partial shipment confirmation.</span></span> <span data-ttu-id="71f30-109">Transportlastningsprocessen för dessa laster kan sedan uppstå.</span><span class="sxs-lookup"><span data-stu-id="71f30-109">The transport loading processes for those loads can then occur.</span></span> <span data-ttu-id="71f30-110">Därför kan transportplaneringsavdelningen planera laster utan att behöva tänka på kapacitet för enskilda transporter.</span><span class="sxs-lookup"><span data-stu-id="71f30-110">Therefore, the transportation planning department can plan loads without having to consider the capacity of individual transports.</span></span>

<span data-ttu-id="71f30-111">Vid lastningen kan arbetarna definiera nya transportlaster som en lastpall kan lastas på.</span><span class="sxs-lookup"><span data-stu-id="71f30-111">At the time of loading, workers can define a new transport load that a pallet can be loaded to.</span></span> <span data-ttu-id="71f30-112">De kan också se en befintlig transportlast.</span><span class="sxs-lookup"><span data-stu-id="71f30-112">Alternatively, they can identify an existing transport load.</span></span> <span data-ttu-id="71f30-113">Dessa data kan registreras av en mobil enhet.</span><span class="sxs-lookup"><span data-stu-id="71f30-113">This data can be recorded via a mobile device.</span></span> <span data-ttu-id="71f30-114">Därför kan flera lagerarbetare lasta lager från samma laster eller olika laster på samma lastbil.</span><span class="sxs-lookup"><span data-stu-id="71f30-114">Therefore, several warehouse workers can load inventory from the same loads or different loads onto the same truck.</span></span> <span data-ttu-id="71f30-115">Lasterna kan sedan helt eller delvis levereras.</span><span class="sxs-lookup"><span data-stu-id="71f30-115">The loads can then be fully or partially shipped.</span></span>

> [!NOTE] 
> <span data-ttu-id="71f30-116">För att kunna lasta lager från en last till en specifik transportlast och skicka lasten måste arbete genereras med hjälp av en lastningsklass i en arbetsmall.</span><span class="sxs-lookup"><span data-stu-id="71f30-116">In order to load inventory from a load to a specific transport load and partially ship the load, work must be generated by using a loading class in a work template.</span></span> <span data-ttu-id="71f30-117">Vanlig plockning av typen **plockning** kan inte lastas på en transportlast på till exempel en lastbil.</span><span class="sxs-lookup"><span data-stu-id="71f30-117">Ordinary picking work of the **Picking** type can't be loaded to a transport load such as a truck.</span></span>

## <a name="set-up-transport-loads-for-partial-shipment"></a><span data-ttu-id="71f30-118">Ange transportlast för en delleverans</span><span class="sxs-lookup"><span data-stu-id="71f30-118">Set up transport loads for partial shipment</span></span>

<span data-ttu-id="71f30-119">Inställningen för delleveranser av last består av följande två procedurer.</span><span class="sxs-lookup"><span data-stu-id="71f30-119">The setup for partial shipment of loads consists of the following two procedures.</span></span>

### <a name="set-the-loading-strategy"></a><span data-ttu-id="71f30-120">Ange lastningsstrategi</span><span class="sxs-lookup"><span data-stu-id="71f30-120">Set the loading strategy</span></span>

<span data-ttu-id="71f30-121">Du måste aktivera delvis lastning genom att ange lastningsstrategin.</span><span class="sxs-lookup"><span data-stu-id="71f30-121">You must enable partial loading by setting the loading strategy.</span></span> <span data-ttu-id="71f30-122">Du kan ange lastningsstrategin när du har skapat en last.</span><span class="sxs-lookup"><span data-stu-id="71f30-122">You can set the loading strategy after you've created a load.</span></span>

1. <span data-ttu-id="71f30-123">Välj **Lagerstyrning**\>**Laster**\>**Alla laster**.</span><span class="sxs-lookup"><span data-stu-id="71f30-123">Select **Warehouse management** \> **Loads** \> **All loads**.</span></span>
2. <span data-ttu-id="71f30-124">Välj en last och klicka sedan på **Rubrik**.</span><span class="sxs-lookup"><span data-stu-id="71f30-124">Select a load, and then click **Header**.</span></span>
3. <span data-ttu-id="71f30-125">I fältet **Lastningsstrategi**, välj **Partiell leverans av last tillåts**.</span><span class="sxs-lookup"><span data-stu-id="71f30-125">In the **Loading strategy** field, select **Partial load shipping allowed**.</span></span>

### <a name="create-a-menu-item-for-loading-of-transport-loads"></a><span data-ttu-id="71f30-126">Skapa ett menyalternativ för lasting av transportlaster</span><span class="sxs-lookup"><span data-stu-id="71f30-126">Create a menu item for loading of transport loads</span></span>

<span data-ttu-id="71f30-127">Du måste skapa ett nytt menyalternativ som kan transportera laster som ska lastas.</span><span class="sxs-lookup"><span data-stu-id="71f30-127">You must create a new menu item that enables transport loads to be loaded.</span></span> <span data-ttu-id="71f30-128">En transportlast låter dig gruppera rader från en last till flera laster.</span><span class="sxs-lookup"><span data-stu-id="71f30-128">A transport load lets you group work lines from one load or multiple loads.</span></span> <span data-ttu-id="71f30-129">Allt som läggs till transportlasten kan sedan skickas med en mobilskanner.</span><span class="sxs-lookup"><span data-stu-id="71f30-129">Everything that is added to the transport load can then be shipped by using a mobile scanner.</span></span>

1. <span data-ttu-id="71f30-130">Välj **Lagerstyrning** \> **InställningarSetup** \> **Mobil enhet** \> **Menyalternativ på mobil enhet**.</span><span class="sxs-lookup"><span data-stu-id="71f30-130">Select **Warehouse management** \> **Setup** \> **Mobile device** \> **Mobile device menu items**.</span></span>
2. <span data-ttu-id="71f30-131">Markera **Ny** och sedan, i fältet **Läge**, markerar du **Arbete**.</span><span class="sxs-lookup"><span data-stu-id="71f30-131">Select **New**, and then, in the **Mode** field, select **Work**.</span></span>
3. <span data-ttu-id="71f30-132">Ange alternativet **Använd befintligt arbete** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="71f30-132">Set the **Use existing work** option to **Yes**.</span></span>
4. <span data-ttu-id="71f30-133">På fliken **Allmänt** i fältet **Dirigerad av**, välj **Transportlastning**.</span><span class="sxs-lookup"><span data-stu-id="71f30-133">On the **General** tab, in the **Directed by** field, select **Transport loading**.</span></span>
5. <span data-ttu-id="71f30-134">Aktivera leveransbekräftelse på en mobilskanner i fältet **Tillåten leveransbekräftelsetyp** och välj **Transportlast**.</span><span class="sxs-lookup"><span data-stu-id="71f30-134">To enable shipment confirmation on a mobile scanner, in the **Allowed ship confirmation type** field, select **Transport load**.</span></span>

## <a name="confirm-shipment-of-a-transport-load-from-the-client"></a><span data-ttu-id="71f30-135">Bekräfta leveransen av en transportlast från klienten</span><span class="sxs-lookup"><span data-stu-id="71f30-135">Confirm shipment of a transport load from the client</span></span>

<span data-ttu-id="71f30-136">Denna inställning låter dig bekräfta en transportlast som inkluderar full last eller delvis lastad last som ska levereras.</span><span class="sxs-lookup"><span data-stu-id="71f30-136">This setup lets you confirm a transport load that includes a full load or a partially loaded load to be shipped.</span></span>

1. <span data-ttu-id="71f30-137">Välj **Lagerstyrning**\>**Laster**\>**Transportlaster**.</span><span class="sxs-lookup"><span data-stu-id="71f30-137">Select **Warehouse management** \> **Loads** \> **Transport loads**.</span></span>
2. <span data-ttu-id="71f30-138">I Åtgärdsfönster, på fliken **Leverera och ta emot** i gruppen **Bekräfta**, välj **Transport**.</span><span class="sxs-lookup"><span data-stu-id="71f30-138">On the Action Pane, on the **Ship and receive** tab, in the **Confirm** group, select **Transport**.</span></span>
