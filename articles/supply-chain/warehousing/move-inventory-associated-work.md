---
title: Lagerrörelse med tillhörande arbete i lagerstyrning
description: Det här avsnittet beskriver hur du ställer in och använder bekräftelse av komponentplockning från en mobil enhet.
author: Mirzaab
manager: tfehr
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorker
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2aee3af8da6610c16fc2d98091bfa3f01f1bd0f5
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3215733"
---
# <a name="movement-of-inventory-with-associated-work-in-warehouse-management"></a><span data-ttu-id="ce48b-103">Lagerrörelse med tillhörande arbete i lagerstyrning</span><span class="sxs-lookup"><span data-stu-id="ce48b-103">Movement of inventory with associated work in Warehouse management</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ce48b-104">Med hjälp av rörligt lager kan du bestämma vilka lagerarbetare som ska kunna flytta reserverat lager.</span><span class="sxs-lookup"><span data-stu-id="ce48b-104">Using movement of inventory, you can decide which warehouse workers are allowed to move reserved inventory.</span></span> <span data-ttu-id="ce48b-105">Detta ger en flexibilitet i reglerade lagerställen där du kan välja att inte tillåta en arbetare kan välja en ny plockningsplats för plockningsarbete som redan har skapats.</span><span class="sxs-lookup"><span data-stu-id="ce48b-105">This provides a flexibility in regulated warehouses where you can decide to not allow a worker to choose a new pick location for pick work that is already created.</span></span> <span data-ttu-id="ce48b-106">Det gör det också möjligt för en lagerchef att kontrollera vilka funktioner som ska mer ovana arbetare bör ha.</span><span class="sxs-lookup"><span data-stu-id="ce48b-106">It also allows a warehouse manager to control which capabilities some less experienced workers should have.</span></span>

<span data-ttu-id="ce48b-107">Möjligheten att hantera lagerarbetares dagliga verksamhet kan vara användbar i situationer som dessa:</span><span class="sxs-lookup"><span data-stu-id="ce48b-107">The flexibility to manage the daily operations of warehouse workers can be useful in scenarios such as these:</span></span>

## <a name="scenario-1"></a><span data-ttu-id="ce48b-108">Scenario 1</span><span class="sxs-lookup"><span data-stu-id="ce48b-108">Scenario 1</span></span>
<span data-ttu-id="ce48b-109">Ett företag har ett relativt litet mottagnings område som är överbelastat med lastpallar och kartonger som väntar på att förflyttas.</span><span class="sxs-lookup"><span data-stu-id="ce48b-109">A company has a relatively small receiving area, and it’s congested with pallets and boxes awaiting put away.</span></span> <span data-ttu-id="ce48b-110">En stor försändelse förväntas den aktuella dagen, varför mottagande lageransvarige beslutar sig för att rensa inleveransområdet genom att flytta några lastpallar till ett sekundärt inkommande mellanlagringsområde.</span><span class="sxs-lookup"><span data-stu-id="ce48b-110">A large shipment is expected on the current day, so the receiving clerk decides to clear up the receiving area by moving some of the pallets to a secondary inbound staging area.</span></span>

## <a name="scenario-2"></a><span data-ttu-id="ce48b-111">Scenario 2</span><span class="sxs-lookup"><span data-stu-id="ce48b-111">Scenario 2</span></span>
<span data-ttu-id="ce48b-112">En erfaren lagerarbetare upptäcker en möjlighet att på ett lager konsolidera artiklar på en och samma plats, i stället för att sprida ut dem över tre närliggande platser med liten mängd på respektive plats.</span><span class="sxs-lookup"><span data-stu-id="ce48b-112">An experienced warehouse worker notices an opportunity in a warehouse to consolidate items in one location instead of having them divided across 3 nearby locations with little quantity on each.</span></span> <span data-ttu-id="ce48b-113">Arbetaren vill konsolidera kvantiteten genom att flytta artiklar från var och en av dessa platser till samma plats och samma registreringsskylt.</span><span class="sxs-lookup"><span data-stu-id="ce48b-113">The worker wants to consolidate the quantity by moving items from each of these locations into the same location and onto the same license plate.</span></span>

## <a name="scenario-3"></a><span data-ttu-id="ce48b-114">Scenario 3</span><span class="sxs-lookup"><span data-stu-id="ce48b-114">Scenario 3</span></span>
<span data-ttu-id="ce48b-115">En pall inväntar leverans på en lagringsplats, till exempel STAGE01 som ligger nära BAYDOOR01.</span><span class="sxs-lookup"><span data-stu-id="ce48b-115">A pallet is awaiting shipment in a staging location, such as STAGE01, which is near BAYDOOR01.</span></span> <span data-ttu-id="ce48b-116">På grund av ändrade planer kommer dock trucken att anlända till BAYDOOR04.</span><span class="sxs-lookup"><span data-stu-id="ce48b-116">However, due to a change of plans the truck is scheduled to arrive at BAYDOOR04.</span></span> <span data-ttu-id="ce48b-117">Den leveransansvarige är medveten om detta och måste säkerställa att trucken inte behöver vänta på att lastas från STAGE01.</span><span class="sxs-lookup"><span data-stu-id="ce48b-117">The shipping clerk is aware of this and needs to ensure that the truck does not have to wait to be loaded from STAGE01.</span></span> <span data-ttu-id="ce48b-118">Den leveransansvarige bestämmer sig för att flytta artiklar i den sändningen från STAGE01 till STAGE04, vilket ligger närmare den nya destinationen.</span><span class="sxs-lookup"><span data-stu-id="ce48b-118">The shipping clerk decides to move the items in that shipment from STAGE01 to STAGE04, which is closer to the new destination.</span></span>

### <a name="current-limitations"></a><span data-ttu-id="ce48b-119">Aktuella begränsningar</span><span class="sxs-lookup"><span data-stu-id="ce48b-119">Current limitations</span></span>

<span data-ttu-id="ce48b-120">De arbetsreservationer som du kan flytta begränsas till försäljningsorder, problem med överföringsorder, överföringsorderkvitto, inköpsorder och lagerpåfyllnadsarbete.</span><span class="sxs-lookup"><span data-stu-id="ce48b-120">The work reservations that you can move are limited to Sales order, Transfer order issue, Transfer order receipt, Purchase order, and Replenishment work.</span></span>

<span data-ttu-id="ce48b-121">Att flytta objekt begränsas i syfte att förhindra delning av arbetsrader.</span><span class="sxs-lookup"><span data-stu-id="ce48b-121">Moving items is restricted to prevent splitting of work lines.</span></span> <span data-ttu-id="ce48b-122">Detta innebär att om du har en arbetsrad på 100 enheter av artikel A från platsen Loc1, så kan du inte flytta endast 30 stycken av artikel A därifrån till en annan plats.</span><span class="sxs-lookup"><span data-stu-id="ce48b-122">This means that if you have a work line for 100 pcs of item A from location Loc1, you won’t be able to move only 30 pcs of item A from there to another location.</span></span> <span data-ttu-id="ce48b-123">Detta skulle leda till en delning av den befintliga arbetsraden till 30 och 70, detta eftersom platserna nu skiljer sig åt.</span><span class="sxs-lookup"><span data-stu-id="ce48b-123">This would lead to a split of the existing work line to 30 and 70, because the locations are now different.</span></span>

<span data-ttu-id="ce48b-124">I syfte att inte dela upp målregistreringsskylten medges endast förflyttning av hela registreringsskylten på de lagringsplatser där den registreringsskylt som du flyttar varor från eller till anges som målregistreringsskylt för en arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="ce48b-124">For staging scenarios, where the license plate you move the goods from or the license plate you move the goods to, are set as a Target LP for a work order, only movement of the entire LP is allowed, so as not to break up the Target LP.</span></span>
<span data-ttu-id="ce48b-125">Endast ad hoc-transport stöds i nuläget.</span><span class="sxs-lookup"><span data-stu-id="ce48b-125">Only the ad hoc movement is currently supported.</span></span> <span data-ttu-id="ce48b-126">Det innebär att du inte kan flytta reserverat lager genom förflyttning via mallmenyalternativen för mobil enhet.</span><span class="sxs-lookup"><span data-stu-id="ce48b-126">That means that you will not be able to move reserved inventory through the movement by template mobile device menu items.</span></span>

### <a name="set-up-permission-to-move-reserved-inventory-for-individual-workers"></a><span data-ttu-id="ce48b-127">Ange behörighet för att flytta reserverade varor för individuella medarbetare</span><span class="sxs-lookup"><span data-stu-id="ce48b-127">Set up permission to move reserved inventory for individual workers</span></span>

<span data-ttu-id="ce48b-128">För den arbetare som ska kunna flytta reserverat lager väljer du kryssrutan **Tillåt flytt av lager med associerat arbete** under **Lagerstyrning** > **Inställningar** > **Arbetstagare**.</span><span class="sxs-lookup"><span data-stu-id="ce48b-128">For the worker who should be allowed to move reserved inventory, select the **Allow movement of inventory with work associated** check box under **Warehouse management** > **Setup** > **Worker**.</span></span>  

### <a name="backported"></a><span data-ttu-id="ce48b-129">Anpassning i efterhand</span><span class="sxs-lookup"><span data-stu-id="ce48b-129">Backported</span></span>

<span data-ttu-id="ce48b-130">Denna funktion har också anpassats i efterhand för Microsoft Dynamics AX 2012 R3 och blir tillgänglig som en del av CU12.</span><span class="sxs-lookup"><span data-stu-id="ce48b-130">This feature has also been back-ported to Microsoft Dynamics AX 2012 R3 and will be available as part of CU12.</span></span>
<span data-ttu-id="ce48b-131">Den kan också hämtas separat via KB-nummer 3192548.</span><span class="sxs-lookup"><span data-stu-id="ce48b-131">It can also be downloaded individually through KB number 3192548.</span></span> 

