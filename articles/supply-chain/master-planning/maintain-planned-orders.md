---
title: Underhåll planerade order
description: Detta avsnitt innehåller information om hur du hanterar planerade order. Det beskriver hur du kan uppdatera statusen för planerade order, bekräfta dem och filtrera för planerade order som har samma status som en vald planerad order.
author: roxanadiaconu
manager: AnnBe
ms.date: 09/09/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 19151
ms.assetid: 54123f4c-b4ca-4ce4-9358-b067aa04c968
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5ddf2c7b4c67bec6c29387c78d1fdb021d85d702
ms.sourcegitcommit: 620e15555d176eec3905b48d5001af1c50107ce6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/09/2019
ms.locfileid: "1993450"
---
# <a name="maintain-planned-orders"></a><span data-ttu-id="57927-104">Underhåll planerade order</span><span class="sxs-lookup"><span data-stu-id="57927-104">Maintain planned orders</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="57927-105">Detta avsnitt innehåller information om hur du hanterar planerade order.</span><span class="sxs-lookup"><span data-stu-id="57927-105">This topic provides information about how to manage planned orders.</span></span> <span data-ttu-id="57927-106">Det beskriver hur du kan uppdatera statusen för planerade order, bekräfta dem och filtrera för planerade order som har samma status som en vald planerad order.</span><span class="sxs-lookup"><span data-stu-id="57927-106">It describes how you can update the status of planned orders, firm them, and filter for planned orders that have the same status as a selected planned order.</span></span>

<span data-ttu-id="57927-107">Du kan hantera planerade order från arbetsytan **Huvudplanering**, listan **Planerad order** eller listorna **Planerade produktionsorder**, **Planerade inköpsorder**och **Planerad överföring**.</span><span class="sxs-lookup"><span data-stu-id="57927-107">You can manage planned orders from the **Master planning** workspace, the **Planned order** list, or the **Planned production orders**, **Planned purchase orders**, and **Planned transfer** lists.</span></span> 

## <a name="planned-order-status"></a><span data-ttu-id="57927-108">Status på planerad order</span><span class="sxs-lookup"><span data-stu-id="57927-108">Planned order status</span></span>
<span data-ttu-id="57927-109">Du kan använda fältet **Status** för att följa dina framsteg.</span><span class="sxs-lookup"><span data-stu-id="57927-109">You can use the **Status** field to help track your progress.</span></span> <span data-ttu-id="57927-110">Följande värden används:</span><span class="sxs-lookup"><span data-stu-id="57927-110">The following values are used:</span></span>

-   <span data-ttu-id="57927-111">När huvudplaneringen genererar planerade order, har planerade order statusen **Obearbetad**.</span><span class="sxs-lookup"><span data-stu-id="57927-111">When master planning generates planned orders, the planned orders have a status of **Unprocessed**.</span></span>
-   <span data-ttu-id="57927-112">Om du väljer att inte bekräfta en planerad order kan du ge den statusen **Slutförd**.</span><span class="sxs-lookup"><span data-stu-id="57927-112">If you decide not to firm a planned order, you can give it a status of **Completed**.</span></span>
-   <span data-ttu-id="57927-113">Om du vill bekräfta en planerad order kan du ändra statusen till **godkänd**.</span><span class="sxs-lookup"><span data-stu-id="57927-113">If you want to firm a planned order, you can change the status to **Approved**.</span></span> <span data-ttu-id="57927-114">Planerade order med status **godkänd** respekteras i huvudplaneringen, så att de inte ändras eller tas bort.</span><span class="sxs-lookup"><span data-stu-id="57927-114">Planned orders with **Approved** status are respected by master planning, so they are not modified or deleted.</span></span> 

## <a name="firming-planned-orders"></a><span data-ttu-id="57927-115">Bekräfta planerade order</span><span class="sxs-lookup"><span data-stu-id="57927-115">Firming planned orders</span></span> 
<span data-ttu-id="57927-116">Genom att bekräfta planerade order skapas verkliga order.</span><span class="sxs-lookup"><span data-stu-id="57927-116">By firming planned orders, real orders are created.</span></span> <span data-ttu-id="57927-117">Dessa är också kända som *frisläppta* eller *öppna order*.</span><span class="sxs-lookup"><span data-stu-id="57927-117">These are also know as *released* or *open orders*.</span></span> <span data-ttu-id="57927-118">När en planerad order är bekräftad flyttas den till den relevanta modulens orderavsnitt.</span><span class="sxs-lookup"><span data-stu-id="57927-118">When a planned order is firmed, it's moved to the orders section of the relevant module.</span></span>

<span data-ttu-id="57927-119">Du kan välja två bekräftelsealternativ på sidan **planerade order**:</span><span class="sxs-lookup"><span data-stu-id="57927-119">You can select two firming options from the **Planned orders** page:</span></span>

-   <span data-ttu-id="57927-120">**Bekräfta** – detta kommer att bekräfta en eller flera valda planerade order.</span><span class="sxs-lookup"><span data-stu-id="57927-120">**Firm** – This will firm one or multiple selected planned orders.</span></span>
-   <span data-ttu-id="57927-121">**Bekräfta alla** – bekräfta alla planerade order i filtret.</span><span class="sxs-lookup"><span data-stu-id="57927-121">**Firm all** – This will firm all planned orders in the filter.</span></span> <span data-ttu-id="57927-122">Med **bekräfta allt** behöver du inte välja den planerade ordern, alla bekräftas inom filtret.</span><span class="sxs-lookup"><span data-stu-id="57927-122">Using **Firm all** you don’t have to select the planned order, all planned orders within the filter will be firmed.</span></span> <span data-ttu-id="57927-123">Det här alternativet kan vara användbart om du bekräftar ett stort antal planerade order.</span><span class="sxs-lookup"><span data-stu-id="57927-123">This option can be useful if you are firming a high number of planned orders.</span></span>

> [!NOTE]
> <span data-ttu-id="57927-124">Du kan spåra en planerad order som bekräftats genom att **Bekräftelsehistorik** under **Planerade orderformulär > Visa > Bekräftelsehistorik**.</span><span class="sxs-lookup"><span data-stu-id="57927-124">You can track a planned order that was firmed from **Firming history** under **Planned orders form > View > Firming history**.</span></span>

## <a name="parallelize-firming"></a><span data-ttu-id="57927-125">Parallell bekräftelse</span><span class="sxs-lookup"><span data-stu-id="57927-125">Parallelize firming</span></span>
<span data-ttu-id="57927-126">Om du planerar att bekräfta många order samtidigt kan körningstiden och prestandan öka under tiden för parallellt av körningen.</span><span class="sxs-lookup"><span data-stu-id="57927-126">If you are planning to firm many orders at the same time, parallelizing the run can improve the run time or performance.</span></span> <span data-ttu-id="57927-127">Det här alternativet är tillgängligt när du bekräftar flera planerade order med antingen **bekräfta** eller **bekräfta alla**.</span><span class="sxs-lookup"><span data-stu-id="57927-127">This option is available when firming multiple planned orders with either **Firm** or **Firm all**.</span></span> <span data-ttu-id="57927-128">Följande parametrar är tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="57927-128">The following parameters are available:</span></span>

-   <span data-ttu-id="57927-129">**Parallelliseringsbekräftelse** – om **ja** kommer bekräftelseprocessen att vara parallell med antalet trådar som definierats i **antal trådar**.</span><span class="sxs-lookup"><span data-stu-id="57927-129">**Parallelize firming** – If **Yes**, the firming process will be parallelized with the number of threads defined in **Number of threads**.</span></span>
-   <span data-ttu-id="57927-130">**Antal trådar** – styr antalet trådar som används för att parallellisera bekräftelseprocessen.</span><span class="sxs-lookup"><span data-stu-id="57927-130">**Number of threads** – Controls the number of threads used to parallelize the firming process.</span></span> <span data-ttu-id="57927-131">Parametern visas endast om **Parallelliseringsbekräftelse** anges till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="57927-131">The parameter is only shown when **Parallelize firming** is set to **Yes**.</span></span>


<a name="additional-resources"></a><span data-ttu-id="57927-132">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="57927-132">Additional resources</span></span>
--------

[<span data-ttu-id="57927-133">Huvudplaner</span><span class="sxs-lookup"><span data-stu-id="57927-133">Master plans</span></span>](master-plans.md)



