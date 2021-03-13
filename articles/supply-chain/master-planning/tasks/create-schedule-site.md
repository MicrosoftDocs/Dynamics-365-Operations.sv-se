---
title: Skapa en tidsplan för en plats
description: I den här proceduren visas hur du tidsplanerar tillverkningsorder som ännu inte har startat för en site.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdTableListPage, ProdSchedule, ProdRouteJob
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 442826d6611ea4aaedee2e9bae5649ada1cc846d
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "5007901"
---
# <a name="create-a-schedule-for-a-site"></a><span data-ttu-id="a461e-103">Skapa en tidsplan för en plats</span><span class="sxs-lookup"><span data-stu-id="a461e-103">Create a schedule for a site</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a461e-104">I den här proceduren visas hur du tidsplanerar tillverkningsorder som ännu inte har startat för en site.</span><span class="sxs-lookup"><span data-stu-id="a461e-104">This procedure shows how to schedule production orders that are not yet started for a site.</span></span>  <span data-ttu-id="a461e-105">Demonstrationsdataföretaget USMF används för att utföra den här proceduren.</span><span class="sxs-lookup"><span data-stu-id="a461e-105">The demo data company USMF is used to complete this procedure.</span></span>


## <a name="identify-production-orders-that-are-not-started"></a><span data-ttu-id="a461e-106">Identifiera tillverkningsorder som inte har startats</span><span class="sxs-lookup"><span data-stu-id="a461e-106">Identify production orders that are not started</span></span>
1. <span data-ttu-id="a461e-107">Gå till Produktionskontroll > Produktionsorder > Alla produktionsorder.</span><span class="sxs-lookup"><span data-stu-id="a461e-107">Go to Production control > Production orders > All production orders.</span></span>
2. <span data-ttu-id="a461e-108">Använd snabbfiltret för att söka efter poster.</span><span class="sxs-lookup"><span data-stu-id="a461e-108">Use the Quick Filter to find records.</span></span> <span data-ttu-id="a461e-109">Filtrera till exempel på värdet "1" i fältet Site.</span><span class="sxs-lookup"><span data-stu-id="a461e-109">For example, filter on the Site field with a value of '1'.</span></span>
    * <span data-ttu-id="a461e-110">1 representerar en site i USMF.</span><span class="sxs-lookup"><span data-stu-id="a461e-110">1 represents a site in USMF.</span></span> <span data-ttu-id="a461e-111">Om du inte använder USMF väler du en site från ditt eget företag.</span><span class="sxs-lookup"><span data-stu-id="a461e-111">If you are not using USMF, select a site from your own company.</span></span>  
3. <span data-ttu-id="a461e-112">Öppna kolumnfiltret Status.</span><span class="sxs-lookup"><span data-stu-id="a461e-112">Open the Status column filter.</span></span>
4. <span data-ttu-id="a461e-113">Använd ett filter på fältet "Status", med värdet "Tidsplanerad", med hjälp av filteroperatorn "är exakt".</span><span class="sxs-lookup"><span data-stu-id="a461e-113">Apply a filter on the "Status" field, with a value of "Scheduled", using the "is exactly" filter operator.</span></span>

## <a name="create-a-schedule"></a><span data-ttu-id="a461e-114">Skapa en tidsplan</span><span class="sxs-lookup"><span data-stu-id="a461e-114">Create a schedule</span></span>
1. <span data-ttu-id="a461e-115">Markera eller avmarkera alla rader i listan.</span><span class="sxs-lookup"><span data-stu-id="a461e-115">In the list, mark or unmark all rows.</span></span>
2. <span data-ttu-id="a461e-116">Klicka på Tidsplanera i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="a461e-116">On the Action Pane, click Schedule.</span></span>
3. <span data-ttu-id="a461e-117">Klicka på Tidsplanera jobb.</span><span class="sxs-lookup"><span data-stu-id="a461e-117">Click Schedule jobs.</span></span>
4. <span data-ttu-id="a461e-118">Välj ”bakåt från leveransdatum " i fältetPlaneringsriktning.</span><span class="sxs-lookup"><span data-stu-id="a461e-118">In the Scheduling direction field, select 'Backward from delivery date'.</span></span>
5. <span data-ttu-id="a461e-119">Välj Nej i fältet Begränsad kapacitet.</span><span class="sxs-lookup"><span data-stu-id="a461e-119">Select No in the Finite capacity field.</span></span>
6. <span data-ttu-id="a461e-120">Välj Nej i fältet Begränsat material.</span><span class="sxs-lookup"><span data-stu-id="a461e-120">Select No in the Finite material field.</span></span>
7. <span data-ttu-id="a461e-121">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="a461e-121">Click OK.</span></span>
    * <span data-ttu-id="a461e-122">Detta kan ta ett tag.</span><span class="sxs-lookup"><span data-stu-id="a461e-122">This may take a while.</span></span>  

## <a name="view-the-result-of-scheduled-production-orders"></a><span data-ttu-id="a461e-123">Visa resultatet av tidsplanerade tillverkningsorder.</span><span class="sxs-lookup"><span data-stu-id="a461e-123">View the result of scheduled production orders</span></span>
1. <span data-ttu-id="a461e-124">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="a461e-124">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="a461e-125">Du kan markera någon rad rad.</span><span class="sxs-lookup"><span data-stu-id="a461e-125">You can mark any row.</span></span>  
2. <span data-ttu-id="a461e-126">Klicka på Produktionsorder i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="a461e-126">On the Action Pane, click Production order.</span></span>
3. <span data-ttu-id="a461e-127">Klicka på Alla jobb.</span><span class="sxs-lookup"><span data-stu-id="a461e-127">Click All jobs.</span></span>
    * <span data-ttu-id="a461e-128">På den här sidan kan du se en lista med jobb.</span><span class="sxs-lookup"><span data-stu-id="a461e-128">On this page, you can see the list of jobs.</span></span> <span data-ttu-id="a461e-129">På fliken Tidsplanering kan du se Startdatum och Slutdatum för ett jobb.</span><span class="sxs-lookup"><span data-stu-id="a461e-129">On the Scheduling tab, you can see the Start date and End date for a job.</span></span>  
4. <span data-ttu-id="a461e-130">Klicka på Material.</span><span class="sxs-lookup"><span data-stu-id="a461e-130">Click Materials.</span></span>
    * <span data-ttu-id="a461e-131">På den här sidan kan du se den uppskattade materialförbrukningen för operationerna i produktionsordern och det aktuella tillgängliga lagret.</span><span class="sxs-lookup"><span data-stu-id="a461e-131">On this page, you can see the estimated material consumption for the operations on the production order and the current available inventory.</span></span>  

