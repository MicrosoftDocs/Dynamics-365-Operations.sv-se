---
title: Fördröjningar
description: Det här ämnet innehåller information om fördröjda data i huvudplaneringen. Ett fördröjt datum är ett realistiskt förfallodatum som en transaktion får om det tidigaste uppfyllelsedatumet som huvudplaneringen beräknar infaller efter begärt datum.
author: roxanadiaconu
manager: tfehr
ms.date: 03/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqTransFuturesListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 19311
ms.assetid: 5ffb1486-2e08-4cdc-bd34-b47ae795ef0f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 34252e5cd9ee5151b1cba47975fc0cc612521a17
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3203858"
---
# <a name="delays"></a><span data-ttu-id="b1042-104">Fördröjningar</span><span class="sxs-lookup"><span data-stu-id="b1042-104">Delays</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b1042-105">Det här ämnet innehåller information om fördröjda data i huvudplaneringen.</span><span class="sxs-lookup"><span data-stu-id="b1042-105">This topic provides information about delayed dates in master planning.</span></span> <span data-ttu-id="b1042-106">Ett fördröjt datum är ett realistiskt förfallodatum som en transaktion får om det tidigaste uppfyllelsedatumet som huvudplaneringen beräknar infaller efter begärt datum.</span><span class="sxs-lookup"><span data-stu-id="b1042-106">A delayed date is a realistic due date that a transaction receives if the earliest fulfillment date that master planning calculates is later than the requested date.</span></span>

<span data-ttu-id="b1042-107">Huvudplaneringen kan beräkna det tidigaste uppfyllelsedatumet för en transaktion baserat på produktionstiderna, materialtillgänglighet, kapacitettillgänglighet och olika planläggningsparametrar.</span><span class="sxs-lookup"><span data-stu-id="b1042-107">Master planning can calculate the earliest fulfillment date for a transaction, based on lead times, material availability, capacity availability, and various planning parameters.</span></span> 

<span data-ttu-id="b1042-108">Om en huvudplanering beräknar ett orderdatum som infaller före det aktuella datumet, kan inte ordern expedieras i tid.</span><span class="sxs-lookup"><span data-stu-id="b1042-108">If master planning calculates an order date that precedes the current date, the order can't be fulfilled on time.</span></span> <span data-ttu-id="b1042-109">Därför är ordern försenad.</span><span class="sxs-lookup"><span data-stu-id="b1042-109">Therefore, the order is delayed.</span></span> <span data-ttu-id="b1042-110">I det här fallet inkluderar huvudplaneringen framåtplaner för ordern från aktuellt datum och som inkluderar ledtider.</span><span class="sxs-lookup"><span data-stu-id="b1042-110">In this case, master planning forward-plans the order from the current date and includes lead times.</span></span> <span data-ttu-id="b1042-111">Dessa ledtider startar komponentartiklar på lägre nivå.</span><span class="sxs-lookup"><span data-stu-id="b1042-111">These lead times start with any lower-level component items.</span></span> <span data-ttu-id="b1042-112">Ordern får sedan ett försenat datum.</span><span class="sxs-lookup"><span data-stu-id="b1042-112">The order then receives a delayed date.</span></span> <span data-ttu-id="b1042-113">Ett försenat datum är ett realistiskt förfallodatum baserat på aktuella uppgifter.</span><span class="sxs-lookup"><span data-stu-id="b1042-113">A delayed date is a realistic due date, based on the current data.</span></span> <span data-ttu-id="b1042-114">I huvudplaneringen beräknas också antalet fördröjningsdagar.</span><span class="sxs-lookup"><span data-stu-id="b1042-114">Master planning also calculates the number of delay days.</span></span> 

<span data-ttu-id="b1042-115">I vissa fall kan du välja att inte att beräkna fördröjningar, till exempel när användare vet att de kan påskynda ledtider genom att välja alternativa leveranssätt.</span><span class="sxs-lookup"><span data-stu-id="b1042-115">In some situations, you might choose not to calculate delays, such as when users know that they can expedite lead times by selecting alternative modes of delivery.</span></span> 

<span data-ttu-id="b1042-116">Du kan konfigurera hur förseningar beräknas för en disponeringsgrupp.</span><span class="sxs-lookup"><span data-stu-id="b1042-116">You can configure how delays are calculated for a coverage group.</span></span> <span data-ttu-id="b1042-117">Du kan sedan koppla disponeringsgruppen till en artikel vid ett senare tillfälle.</span><span class="sxs-lookup"><span data-stu-id="b1042-117">You can then attach the coverage group to an item later.</span></span> 

<span data-ttu-id="b1042-118">På sidan **Huvudplaneringsparametrar** kan du ange starttiden för beräkningen av förseningar.</span><span class="sxs-lookup"><span data-stu-id="b1042-118">On the **Master planning parameters** page, you can set the start time for the calculation of delays.</span></span> <span data-ttu-id="b1042-119">Om en order expedieras efter den här tiden läggs en försening på en dag till i orderns förseningsdatum.</span><span class="sxs-lookup"><span data-stu-id="b1042-119">If an order is fulfilled after this time, a delay of one day is added to the delay date of the order.</span></span> 

> [!NOTE]
> <span data-ttu-id="b1042-120">I tidigare versioner kallades beräknade förseningar *leveransplansmeddelanden*, förseningsdatumet kallades *leveransplansdatum* och en försenad transaktion kallades *en transaktion som är inställd på ett datum i framtiden*.</span><span class="sxs-lookup"><span data-stu-id="b1042-120">In earlier versions, calculated delays were known as *futures messages*, the delayed date was known as the *futures date*, and a delayed transaction was referred to as *a transaction that was future set*.</span></span>

## <a name="limited-delays-in-production-setup-with-multiple-bom-levels"></a><span data-ttu-id="b1042-121">Begränsade förseningar i produktionsinställningarna med flera strukturlistenivåer</span><span class="sxs-lookup"><span data-stu-id="b1042-121">Limited delays in production setup with multiple BOM levels</span></span>
<span data-ttu-id="b1042-122">När du arbetar med förseningar i en produktionsinställning som har flera strukturlistenivåer, är det viktigt att observera att endast artiklarna direkt ovanför artikeln (i strukturlistan) som orsakar fördröjningen uppdateras med en fördröjning som en del av huvudplaneringskörningen.</span><span class="sxs-lookup"><span data-stu-id="b1042-122">When you work with delays in a production setup that has multiple BOM levels, it is important to note that only the items directly above the item (in the BOM structure) causing the delay, will be updated with a delay as part of the master planning run.</span></span> <span data-ttu-id="b1042-123">Andra artiklar i strukturlistan får inte den fördröjning som används fram till den första huvudplaneringskörningen, när den planerade ordern för den översta nivån har godkänts eller bekräftats.</span><span class="sxs-lookup"><span data-stu-id="b1042-123">Other items in the BOM structure will not get the delay applied until the first master planning run, when the planned order for the top level is approved or firmed.</span></span> 

<span data-ttu-id="b1042-124">För att undvika den här kända begränsningen kan tillverkningsorder högst upp i strukturlistan med förseningar godkännas (eller bekräftas) före nästa huvudplaneringskörning.</span><span class="sxs-lookup"><span data-stu-id="b1042-124">To work around this known limitation, the production orders on the top of the BOM structure with delays can be approved (or firmed) prior to the next master planning run.</span></span> <span data-ttu-id="b1042-125">På så sätt behålls förseningen från den fördröjda godkända planerade tillverkningsordern och alla underliggande komponenter uppdateras enligt detta.</span><span class="sxs-lookup"><span data-stu-id="b1042-125">This way the delay from the delayed approved planned production order will be kept and all underlying components will be updated accordingly.</span></span>
<span data-ttu-id="b1042-126">Åtgärdsmeddelanden kan också användas för att identifiera planerade order som kan flyttas till ett senare datum, på grund av andra förseningar i strukturlistan.</span><span class="sxs-lookup"><span data-stu-id="b1042-126">Action messages can also be used to identify planned orders that can be moved to a later date, due to other delays in the BOM structure.</span></span>

## <a name="desired-date"></a><span data-ttu-id="b1042-127">Önskat datum</span><span class="sxs-lookup"><span data-stu-id="b1042-127">Desired date</span></span>

<span data-ttu-id="b1042-128">På sidan **planerad order** under fliken **Förseningar** är **önskat datum** för den planerade ordern.</span><span class="sxs-lookup"><span data-stu-id="b1042-128">On the **Planned order** page, under the **Delays** tab is the **Desired date** for the planned order.</span></span> <span data-ttu-id="b1042-129">Önskat datum för en planerad order är grunddata för förseningar, vilket är ett beräknat datum som är lika med **begärt datum** beräknat från **nettobehovet**.</span><span class="sxs-lookup"><span data-stu-id="b1042-129">The desired date of a planned order is the base date for delays, which is a computed date that equals the **Requested date** calculated from the **Net Requirement**.</span></span> <span data-ttu-id="b1042-130">Om den planerade ordern är en strukturlisterad, produktionsrad eller kanban-rad, baseras önskat datum på **Behovsdatum** och det önskade datumet visas på sidan **Planerad order**.</span><span class="sxs-lookup"><span data-stu-id="b1042-130">If the planned order is a BOM line, production line or kanban line, the desired date is based on the **Requirement date** and the desired date will not be shown on the **Planned order** page.</span></span>

<a name="additional-resources"></a><span data-ttu-id="b1042-131">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="b1042-131">Additional resources</span></span>
--------

[<span data-ttu-id="b1042-132">Disponeringsinställningar</span><span class="sxs-lookup"><span data-stu-id="b1042-132">Coverage settings</span></span>](coverage-settings.md)
