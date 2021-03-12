---
title: Underhåll planerade order
description: Detta avsnitt innehåller information om hur du hanterar planerade order. Det beskriver hur du kan uppdatera statusen för planerade order, bekräfta dem och filtrera för planerade order som har samma status som en vald planerad order.
author: roxanadiaconu
manager: tfehr
ms.date: 12/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqTransPo, ReqTransFirmLog
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19151
ms.assetid: 54123f4c-b4ca-4ce4-9358-b067aa04c968
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 039fce86ac9649989df1eaa6179c79dd98b8ae3f
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4967086"
---
# <a name="maintain-planned-orders"></a><span data-ttu-id="ce303-104">Underhåll planerade order</span><span class="sxs-lookup"><span data-stu-id="ce303-104">Maintain planned orders</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ce303-105">Detta avsnitt innehåller information om hur du hanterar planerade order.</span><span class="sxs-lookup"><span data-stu-id="ce303-105">This topic provides information about how to manage planned orders.</span></span> <span data-ttu-id="ce303-106">Det beskriver hur du kan uppdatera statusen för planerade order, bekräfta dem och filtrera för planerade order som har samma status som en vald planerad order.</span><span class="sxs-lookup"><span data-stu-id="ce303-106">It describes how you can update the status of planned orders, firm them, and filter for planned orders that have the same status as a selected planned order.</span></span>

<span data-ttu-id="ce303-107">Du kan hantera planerade order från arbetsytan **Huvudplanering**, listan **Planerad order** eller listorna **Planerade produktionsorder**, **Planerade inköpsorder** och **Planerad överföring**.</span><span class="sxs-lookup"><span data-stu-id="ce303-107">You can manage planned orders from the **Master planning** workspace, the **Planned order** list, or the **Planned production orders**, **Planned purchase orders**, and **Planned transfer** lists.</span></span> 

## <a name="planned-order-status"></a><span data-ttu-id="ce303-108">Status på planerad order</span><span class="sxs-lookup"><span data-stu-id="ce303-108">Planned order status</span></span>
<span data-ttu-id="ce303-109">Du kan använda fältet **Status** för att följa dina framsteg.</span><span class="sxs-lookup"><span data-stu-id="ce303-109">You can use the **Status** field to help track your progress.</span></span> <span data-ttu-id="ce303-110">Följande värden används:</span><span class="sxs-lookup"><span data-stu-id="ce303-110">The following values are used:</span></span>

-   <span data-ttu-id="ce303-111">När huvudplaneringen genererar planerade order, har planerade order statusen **Obearbetad**.</span><span class="sxs-lookup"><span data-stu-id="ce303-111">When master planning generates planned orders, the planned orders have a status of **Unprocessed**.</span></span>
-   <span data-ttu-id="ce303-112">Om du väljer att inte bekräfta en planerad order kan du ge den statusen **Slutförd**.</span><span class="sxs-lookup"><span data-stu-id="ce303-112">If you decide not to firm a planned order, you can give it a status of **Completed**.</span></span>
-   <span data-ttu-id="ce303-113">Om du vill bekräfta en planerad order kan du ändra statusen till **godkänd**.</span><span class="sxs-lookup"><span data-stu-id="ce303-113">If you want to firm a planned order, you can change the status to **Approved**.</span></span> <span data-ttu-id="ce303-114">Planerade order med status **godkänd** respekteras i huvudplaneringen, så att de inte ändras eller tas bort under en senare huvudplaneringskörning.</span><span class="sxs-lookup"><span data-stu-id="ce303-114">Planned orders with **Approved** status are respected by master planning, so they are not modified or deleted during a later master planning run.</span></span> <span data-ttu-id="ce303-115">För att uppnå detta kopierar planeringslogiken de **godkända** planerade orderna från den gamla planversionen till den nya planversionen under huvudplaneringen.</span><span class="sxs-lookup"><span data-stu-id="ce303-115">To achieve this, the planning logic copies the **Approved** planned orders from the old plan version to the new plan version during master planning.</span></span>

## <a name="firming-planned-orders"></a><span data-ttu-id="ce303-116">Bekräfta planerade order</span><span class="sxs-lookup"><span data-stu-id="ce303-116">Firming planned orders</span></span> 
<span data-ttu-id="ce303-117">Genom att bekräfta planerade order skapas verkliga order.</span><span class="sxs-lookup"><span data-stu-id="ce303-117">By firming planned orders, real orders are created.</span></span> <span data-ttu-id="ce303-118">Dessa är också kända som *frisläppta* eller *öppna order*.</span><span class="sxs-lookup"><span data-stu-id="ce303-118">These are also known as *released* or *open orders*.</span></span> <span data-ttu-id="ce303-119">När en planerad order är bekräftad flyttas den till den relevanta modulens orderavsnitt.</span><span class="sxs-lookup"><span data-stu-id="ce303-119">When a planned order is firmed, it's moved to the orders section of the relevant module.</span></span>

<span data-ttu-id="ce303-120">Du kan välja två bekräftelsealternativ på sidan **planerade order**:</span><span class="sxs-lookup"><span data-stu-id="ce303-120">You can select two firming options from the **Planned orders** page:</span></span>

-   <span data-ttu-id="ce303-121">**Bekräfta** – detta kommer att bekräfta en eller flera valda planerade order.</span><span class="sxs-lookup"><span data-stu-id="ce303-121">**Firm** – This will firm one or multiple selected planned orders.</span></span>
-   <span data-ttu-id="ce303-122">**Bekräfta alla** – bekräfta alla planerade order i filtret.</span><span class="sxs-lookup"><span data-stu-id="ce303-122">**Firm all** – This will firm all planned orders in the filter.</span></span> <span data-ttu-id="ce303-123">Med **bekräfta allt** behöver du inte välja den planerade ordern, alla bekräftas inom filtret.</span><span class="sxs-lookup"><span data-stu-id="ce303-123">Using **Firm all** you don’t have to select the planned order, all planned orders within the filter will be firmed.</span></span> <span data-ttu-id="ce303-124">Det här alternativet kan vara användbart om du bekräftar ett stort antal planerade order.</span><span class="sxs-lookup"><span data-stu-id="ce303-124">This option can be useful if you are firming a high number of planned orders.</span></span>

> [!NOTE]
> <span data-ttu-id="ce303-125">Du kan spåra en planerad order som bekräftats genom att **Bekräftelsehistorik** under **Planerade orderformulär > Visa > Bekräftelsehistorik**.</span><span class="sxs-lookup"><span data-stu-id="ce303-125">You can track a planned order that was firmed from **Firming history** under **Planned orders form > View > Firming history**.</span></span>

## <a name="parallelize-firming"></a><span data-ttu-id="ce303-126">Parallell bekräftelse</span><span class="sxs-lookup"><span data-stu-id="ce303-126">Parallelize firming</span></span>
<span data-ttu-id="ce303-127">Om du planerar att bekräfta många order samtidigt kan körningstiden och prestandan öka under tiden för parallellt av körningen.</span><span class="sxs-lookup"><span data-stu-id="ce303-127">If you are planning to firm many orders at the same time, parallelizing the run can improve the run time or performance.</span></span> <span data-ttu-id="ce303-128">Det här alternativet är tillgängligt när du bekräftar flera planerade order med antingen **bekräfta** eller **bekräfta alla**.</span><span class="sxs-lookup"><span data-stu-id="ce303-128">This option is available when firming multiple planned orders with either **Firm** or **Firm all**.</span></span> <span data-ttu-id="ce303-129">Följande parametrar är tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="ce303-129">The following parameters are available:</span></span>

-   <span data-ttu-id="ce303-130">**Parallelliseringsbekräftelse** – om **ja** kommer bekräftelseprocessen att vara parallell med antalet trådar som definierats i **antal trådar**.</span><span class="sxs-lookup"><span data-stu-id="ce303-130">**Parallelize firming** – If **Yes**, the firming process will be parallelized with the number of threads defined in **Number of threads**.</span></span>
-   <span data-ttu-id="ce303-131">**Antal trådar** – styr antalet trådar som används för att parallellisera bekräftelseprocessen.</span><span class="sxs-lookup"><span data-stu-id="ce303-131">**Number of threads** – Controls the number of threads used to parallelize the firming process.</span></span> <span data-ttu-id="ce303-132">Parametern visas endast om **Parallelliseringsbekräftelse** anges till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="ce303-132">The parameter is only shown when **Parallelize firming** is set to **Yes**.</span></span>

> [!NOTE]
> <span data-ttu-id="ce303-133">Alternativet för **parallellisera bekräftelse** visas bara när du har mer än en planerad order som har valts för uppstramande.</span><span class="sxs-lookup"><span data-stu-id="ce303-133">The option for **Parallelize firming** is only shown when you have more than one planned order selected for firming.</span></span>

<a name="additional-resources"></a><span data-ttu-id="ce303-134">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="ce303-134">Additional resources</span></span>
--------

[<span data-ttu-id="ce303-135">Huvudplaner – översikt</span><span class="sxs-lookup"><span data-stu-id="ce303-135">Master plans overview</span></span>](master-plans.md)



