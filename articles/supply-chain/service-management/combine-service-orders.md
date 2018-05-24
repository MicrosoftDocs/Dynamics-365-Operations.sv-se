---
title: Kombinera serviceorder
description: Du kan kombinera serviceorder.
author: YuyuScheller
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 8bc28d03d36d184e4bf41de2c50dac15e6d7813c
ms.contentlocale: sv-se
ms.lasthandoff: 05/08/2018

---

# <a name="combine-service-orders"></a><span data-ttu-id="21342-103">Kombinera serviceorder</span><span class="sxs-lookup"><span data-stu-id="21342-103">Combine service orders</span></span>   

[!include [banner](../includes/banner.md)]


<span data-ttu-id="21342-104">När du skapar serviceorderrader automatiskt i formuläret **serviceavtal** kan du välja ett av följande alternativ för att ange hur du vill gruppera dem:</span><span class="sxs-lookup"><span data-stu-id="21342-104">When you create service order lines automatically in the **Service agreements** form, you can choose one of the following options to specify how you want to group them:</span></span>

  - <span data-ttu-id="21342-105">**Per serviceavtal**</span><span class="sxs-lookup"><span data-stu-id="21342-105">**By service agreement**</span></span>

  - <span data-ttu-id="21342-106">**Per serviceuppgift**</span><span class="sxs-lookup"><span data-stu-id="21342-106">**By service task**</span></span>

  - <span data-ttu-id="21342-107">**Per anställd**</span><span class="sxs-lookup"><span data-stu-id="21342-107">**By employee**</span></span>

  - <span data-ttu-id="21342-108">**Per serviceobjekt**</span><span class="sxs-lookup"><span data-stu-id="21342-108">**By service object**</span></span>

## <a name="example"></a><span data-ttu-id="21342-109">Exempel</span><span class="sxs-lookup"><span data-stu-id="21342-109">Example</span></span>

<span data-ttu-id="21342-110">Du skapar ett serviceavtal med startdatum 2007-03-31.</span><span class="sxs-lookup"><span data-stu-id="21342-110">You create a service agreement that has a start date on 03-31-2007.</span></span> <span data-ttu-id="21342-111">I fältet **kombinera serviceorder** väljer du **Per serviceobjekt**.</span><span class="sxs-lookup"><span data-stu-id="21342-111">In the **Combine service orders** field, you specify **By service object**.</span></span> <span data-ttu-id="21342-112">Därefter skapar du följande serviceavtalsrader:</span><span class="sxs-lookup"><span data-stu-id="21342-112">You then create the following service agreement lines:</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="21342-113">Avtalsradnummer</span><span class="sxs-lookup"><span data-stu-id="21342-113">Agreement line number</span></span></p></th>
<th><p><span data-ttu-id="21342-114">transaktionstyp</span><span class="sxs-lookup"><span data-stu-id="21342-114">Transaction type</span></span></p></th>
<th><p><span data-ttu-id="21342-115">beskrivning</span><span class="sxs-lookup"><span data-stu-id="21342-115">Description</span></span></p></th>
<th><p><span data-ttu-id="21342-116">Intervall</span><span class="sxs-lookup"><span data-stu-id="21342-116">Interval</span></span></p></th>
<th><p><span data-ttu-id="21342-117">Serviceobjekt</span><span class="sxs-lookup"><span data-stu-id="21342-117">Service object</span></span></p></th>
<th><p><span data-ttu-id="21342-118">Startdatum</span><span class="sxs-lookup"><span data-stu-id="21342-118">Start date</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="21342-119">1</span><span class="sxs-lookup"><span data-stu-id="21342-119">1</span></span></p></td>
<td><p><span data-ttu-id="21342-120"><strong>Timme</strong></span><span class="sxs-lookup"><span data-stu-id="21342-120"><strong>Hour</strong></span></span></p></td>
<td><p><span data-ttu-id="21342-121">SAL1</span><span class="sxs-lookup"><span data-stu-id="21342-121">SAL1</span></span></p></td>
<td><p><span data-ttu-id="21342-122">Varje vecka</span><span class="sxs-lookup"><span data-stu-id="21342-122">Weekly</span></span></p></td>
<td><p><span data-ttu-id="21342-123">X-1</span><span class="sxs-lookup"><span data-stu-id="21342-123">X-1</span></span></p></td>
<td><p><span data-ttu-id="21342-124">2007-04-01</span><span class="sxs-lookup"><span data-stu-id="21342-124">04-01-2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21342-125">2</span><span class="sxs-lookup"><span data-stu-id="21342-125">2</span></span></p></td>
<td><p><span data-ttu-id="21342-126"><strong>Timme</strong></span><span class="sxs-lookup"><span data-stu-id="21342-126"><strong>Hour</strong></span></span></p></td>
<td><p><span data-ttu-id="21342-127">SAL2</span><span class="sxs-lookup"><span data-stu-id="21342-127">SAL2</span></span></p></td>
<td><p><span data-ttu-id="21342-128">Varannan vecka</span><span class="sxs-lookup"><span data-stu-id="21342-128">Biweekly</span></span></p></td>
<td><p><span data-ttu-id="21342-129">X-2</span><span class="sxs-lookup"><span data-stu-id="21342-129">X-2</span></span></p></td>
<td><p><span data-ttu-id="21342-130">2007-04-01</span><span class="sxs-lookup"><span data-stu-id="21342-130">04-01-2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21342-131">3</span><span class="sxs-lookup"><span data-stu-id="21342-131">3</span></span></p></td>
<td><p><span data-ttu-id="21342-132"><strong>Timme</strong></span><span class="sxs-lookup"><span data-stu-id="21342-132"><strong>Hour</strong></span></span></p></td>
<td><p><span data-ttu-id="21342-133">SAL3</span><span class="sxs-lookup"><span data-stu-id="21342-133">SAL3</span></span></p></td>
<td><p><span data-ttu-id="21342-134">Varje vecka</span><span class="sxs-lookup"><span data-stu-id="21342-134">Weekly</span></span></p></td>
<td><p><span data-ttu-id="21342-135">X-2</span><span class="sxs-lookup"><span data-stu-id="21342-135">X-2</span></span></p></td>
<td><p><span data-ttu-id="21342-136">2007-04-01</span><span class="sxs-lookup"><span data-stu-id="21342-136">04-01-2007</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="21342-137">Du anger inte några tidsfönster för serviceavtalsraderna.</span><span class="sxs-lookup"><span data-stu-id="21342-137">You do not specify time windows for any of the service agreement lines.</span></span> <span data-ttu-id="21342-138">Därför flyttas serviceorderraderna inte från den beräknade dag de infaller.</span><span class="sxs-lookup"><span data-stu-id="21342-138">Therefore, the service order lines will not move from the calculated day on which they fall.</span></span>

<span data-ttu-id="21342-139">Därefter skapar du serviceavtalsrader i formuläret **Skapa serviceorder** från 2007-04-01 till 2007-04-30.</span><span class="sxs-lookup"><span data-stu-id="21342-139">Next, you generate service order lines from the **Create service orders** form from 04-01-2007 until 04-30-2007.</span></span>

<span data-ttu-id="21342-140">Totalt skapas 10 serviceorder.</span><span class="sxs-lookup"><span data-stu-id="21342-140">In total, 10 service orders are created.</span></span> <span data-ttu-id="21342-141">Eftersom du valde den kombinerade inställningen **Per serviceobjekt**, har de serviceorder som skapas endast serviceorderrader med ett specifikt serviceobjekt.</span><span class="sxs-lookup"><span data-stu-id="21342-141">Because the combined setting that you selected was **By service object**, all service orders that are created have only service order lines with one specific service object.</span></span> <span data-ttu-id="21342-142">Serviceorderrader som genereras från serviceavtalet och har samma servicedatum och samma objekt kombineras till en serviceorder.</span><span class="sxs-lookup"><span data-stu-id="21342-142">Service order lines that are generated from the service agreement and have the same service date and object are combined on the same service order.</span></span>


> [!NOTE]
> <P><span data-ttu-id="21342-143">I det här exemplet finns det inga stängda dagar i den kalender som angavs i formuläret <STRONG>Servicehanteringsparametrar</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="21342-143">In this example, the calendar that is specified in the <STRONG>Service management parameters</STRONG> form has no closed days.</span></span></P>



<span data-ttu-id="21342-144">Ytterligare gruppering av serviceorderrader till serviceordrar görs enligt de tidsfönster som du anger på serviceavtalsraderna.</span><span class="sxs-lookup"><span data-stu-id="21342-144">Additional grouping of service order lines into service orders occurs according to any time window that you specify on the service agreement lines.</span></span>

## <a name="see-also"></a><span data-ttu-id="21342-145">Se även</span><span class="sxs-lookup"><span data-stu-id="21342-145">See also</span></span>

[<span data-ttu-id="21342-146">Skapa serviceorder automatiskt</span><span class="sxs-lookup"><span data-stu-id="21342-146">Create service orders automatically</span></span>](create-service-orders-automatically.md)

  



