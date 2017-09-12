---
title: "Fördröjningar"
description: "Det här avsnittet innehåller information om fördröjda data i huvudplaneringen. Ett fördröjt datum är ett realistiskt förfallodatum som en transaktion får om det tidigaste uppfyllelsedatumet som huvudplaneringen beräknar infaller efter begärt datum."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqTransFuturesListPage
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 19311
ms.assetid: 5ffb1486-2e08-4cdc-bd34-b47ae795ef0f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 8db5c507fbc68e637dbbc4ef3311d1fbd298f24f
ms.contentlocale: sv-se
ms.lasthandoff: 08/29/2017

---

# <a name="delays"></a><span data-ttu-id="a2963-104">Fördröjningar</span><span class="sxs-lookup"><span data-stu-id="a2963-104">Delays</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="a2963-105">Det här avsnittet innehåller information om fördröjda data i huvudplaneringen.</span><span class="sxs-lookup"><span data-stu-id="a2963-105">This article provides information about delayed dates in master planning.</span></span> <span data-ttu-id="a2963-106">Ett fördröjt datum är ett realistiskt förfallodatum som en transaktion får om det tidigaste uppfyllelsedatumet som huvudplaneringen beräknar infaller efter begärt datum.</span><span class="sxs-lookup"><span data-stu-id="a2963-106">A delayed date is a realistic due date that a transaction receives if the earliest fulfillment date that master planning calculates is later than the requested date.</span></span>

<span data-ttu-id="a2963-107">Huvudplaneringen kan beräkna det tidigaste uppfyllelsedatumet för en transaktion baserat på produktionstiderna, materialtillgänglighet, kapacitettillgänglighet och olika planläggningsparametrar.</span><span class="sxs-lookup"><span data-stu-id="a2963-107">Master planning can calculate the earliest fulfillment date for a transaction, based on lead times, material availability, capacity availability, and various planning parameters.</span></span> 

<span data-ttu-id="a2963-108">Om en huvudplanering beräknar ett orderdatum som infaller före det aktuella datumet, kan inte ordern expedieras i tid.</span><span class="sxs-lookup"><span data-stu-id="a2963-108">If master planning calculates an order date that precedes the current date, the order can't be fulfilled on time.</span></span> <span data-ttu-id="a2963-109">Därför är ordern försenad.</span><span class="sxs-lookup"><span data-stu-id="a2963-109">Therefore, the order is delayed.</span></span> <span data-ttu-id="a2963-110">I det här fallet inkluderar huvudplaneringen framåtplaner för ordern från aktuellt datum och som inkluderar ledtider.</span><span class="sxs-lookup"><span data-stu-id="a2963-110">In this case, master planning forward-plans the order from the current date and includes lead times.</span></span> <span data-ttu-id="a2963-111">Dessa ledtider startar komponentartiklar på lägre nivå.</span><span class="sxs-lookup"><span data-stu-id="a2963-111">These lead times start with any lower-level component items.</span></span> <span data-ttu-id="a2963-112">Ordern får sedan ett försenat datum.</span><span class="sxs-lookup"><span data-stu-id="a2963-112">The order then receives a delayed date.</span></span> <span data-ttu-id="a2963-113">Ett försenat datum är ett realistiskt förfallodatum baserat på aktuella uppgifter.</span><span class="sxs-lookup"><span data-stu-id="a2963-113">A delayed date is a realistic due date, based on the current data.</span></span> <span data-ttu-id="a2963-114">I huvudplaneringen beräknas också antalet fördröjningsdagar.</span><span class="sxs-lookup"><span data-stu-id="a2963-114">Master planning also calculates the number of delay days.</span></span> 

<span data-ttu-id="a2963-115">I vissa fall kan du välja att inte att beräkna fördröjningar, till exempel när användare vet att de kan påskynda ledtider genom att välja alternativa leveranssätt.</span><span class="sxs-lookup"><span data-stu-id="a2963-115">In some situations, you might choose not to calculate delays, such as when users know that they can expedite lead times by selecting alternative modes of delivery.</span></span> 

<span data-ttu-id="a2963-116">Du kan konfigurera hur förseningar beräknas för en disponeringsgrupp.</span><span class="sxs-lookup"><span data-stu-id="a2963-116">You can configure how delays are calculated for a coverage group.</span></span> <span data-ttu-id="a2963-117">Du kan sedan koppla disponeringsgruppen till en artikel vid ett senare tillfälle.</span><span class="sxs-lookup"><span data-stu-id="a2963-117">You can then attach the coverage group to an item later.</span></span> 

<span data-ttu-id="a2963-118">På sidan **Huvudplaneringsparametrar** kan du ange starttiden för beräkningen av förseningar.</span><span class="sxs-lookup"><span data-stu-id="a2963-118">On the **Master planning parameters** page, you can set the start time for the calculation of delays.</span></span> <span data-ttu-id="a2963-119">Om en order expedieras efter den här tiden läggs en försening på en dag till i orderns förseningsdatum.</span><span class="sxs-lookup"><span data-stu-id="a2963-119">If an order is fulfilled after this time, a delay of one day is added to the delay date of the order.</span></span> 

<span data-ttu-id="a2963-120">**Obs!** I tidigare versioner kallades beräknade förseningar *leveransplansmeddelanden*, förseningsdatumet kallades *leveransplansdatum* och en försenad transaktion kallades *en transaktion som är inställd på ett datum i framtiden*.</span><span class="sxs-lookup"><span data-stu-id="a2963-120">**Note:** In earlier versions, calculated delays were known as *futures messages*, the delayed date was known as the *futures date*, and a delayed transaction was referred to as *a transaction that was future set*.</span></span>

<a name="see-also"></a><span data-ttu-id="a2963-121">Se även</span><span class="sxs-lookup"><span data-stu-id="a2963-121">See also</span></span>
--------

[<span data-ttu-id="a2963-122">Disponeringsinställningar</span><span class="sxs-lookup"><span data-stu-id="a2963-122">Coverage settings</span></span>](coverage-settings.md)




