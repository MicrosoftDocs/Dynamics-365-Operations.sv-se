---
title: Kombinera serviceorder
description: Du kan kombinera serviceorder.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 17fbed59b1fe7bec80f25f74451872efd61bed62
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437456"
---
# <a name="combine-service-orders"></a><span data-ttu-id="15ccc-103">Kombinera serviceorder</span><span class="sxs-lookup"><span data-stu-id="15ccc-103">Combine service orders</span></span>   

[!include [banner](../includes/banner.md)]


<span data-ttu-id="15ccc-104">När du skapar serviceorderrader automatiskt i formuläret **serviceavtal** kan du välja ett av följande alternativ för att ange hur du vill gruppera dem:</span><span class="sxs-lookup"><span data-stu-id="15ccc-104">When you create service order lines automatically in the **Service agreements** form, you can choose one of the following options to specify how you want to group them:</span></span>

  - <span data-ttu-id="15ccc-105">**Per serviceavtal**</span><span class="sxs-lookup"><span data-stu-id="15ccc-105">**By service agreement**</span></span>

  - <span data-ttu-id="15ccc-106">**Per serviceuppgift**</span><span class="sxs-lookup"><span data-stu-id="15ccc-106">**By service task**</span></span>

  - <span data-ttu-id="15ccc-107">**Per anställd**</span><span class="sxs-lookup"><span data-stu-id="15ccc-107">**By employee**</span></span>

  - <span data-ttu-id="15ccc-108">**Per serviceobjekt**</span><span class="sxs-lookup"><span data-stu-id="15ccc-108">**By service object**</span></span>

## <a name="example"></a><span data-ttu-id="15ccc-109">Exempel</span><span class="sxs-lookup"><span data-stu-id="15ccc-109">Example</span></span>

<span data-ttu-id="15ccc-110">Du skapar ett serviceavtal med startdatum 2007-03-31.</span><span class="sxs-lookup"><span data-stu-id="15ccc-110">You create a service agreement that has a start date on 03-31-2007.</span></span> <span data-ttu-id="15ccc-111">I fältet **kombinera serviceorder** väljer du **Per serviceobjekt**.</span><span class="sxs-lookup"><span data-stu-id="15ccc-111">In the **Combine service orders** field, you specify **By service object**.</span></span> <span data-ttu-id="15ccc-112">Därefter skapar du följande serviceavtalsrader:</span><span class="sxs-lookup"><span data-stu-id="15ccc-112">You then create the following service agreement lines:</span></span>

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
<th><p><span data-ttu-id="15ccc-113">Avtalsradnummer</span><span class="sxs-lookup"><span data-stu-id="15ccc-113">Agreement line number</span></span></p></th>
<th><p><span data-ttu-id="15ccc-114">transaktionstyp</span><span class="sxs-lookup"><span data-stu-id="15ccc-114">Transaction type</span></span></p></th>
<th><p><span data-ttu-id="15ccc-115">beskrivning</span><span class="sxs-lookup"><span data-stu-id="15ccc-115">Description</span></span></p></th>
<th><p><span data-ttu-id="15ccc-116">Intervall</span><span class="sxs-lookup"><span data-stu-id="15ccc-116">Interval</span></span></p></th>
<th><p><span data-ttu-id="15ccc-117">Serviceobjekt</span><span class="sxs-lookup"><span data-stu-id="15ccc-117">Service object</span></span></p></th>
<th><p><span data-ttu-id="15ccc-118">Startdatum</span><span class="sxs-lookup"><span data-stu-id="15ccc-118">Start date</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="15ccc-119">1</span><span class="sxs-lookup"><span data-stu-id="15ccc-119">1</span></span></p></td>
<td><p><span data-ttu-id="15ccc-120"><strong>Timme</strong></span><span class="sxs-lookup"><span data-stu-id="15ccc-120"><strong>Hour</strong></span></span></p></td>
<td><p><span data-ttu-id="15ccc-121">SAL1</span><span class="sxs-lookup"><span data-stu-id="15ccc-121">SAL1</span></span></p></td>
<td><p><span data-ttu-id="15ccc-122">Varje vecka</span><span class="sxs-lookup"><span data-stu-id="15ccc-122">Weekly</span></span></p></td>
<td><p><span data-ttu-id="15ccc-123">X-1</span><span class="sxs-lookup"><span data-stu-id="15ccc-123">X-1</span></span></p></td>
<td><p><span data-ttu-id="15ccc-124">2007-04-01</span><span class="sxs-lookup"><span data-stu-id="15ccc-124">04-01-2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15ccc-125">2</span><span class="sxs-lookup"><span data-stu-id="15ccc-125">2</span></span></p></td>
<td><p><span data-ttu-id="15ccc-126"><strong>Timme</strong></span><span class="sxs-lookup"><span data-stu-id="15ccc-126"><strong>Hour</strong></span></span></p></td>
<td><p><span data-ttu-id="15ccc-127">SAL2</span><span class="sxs-lookup"><span data-stu-id="15ccc-127">SAL2</span></span></p></td>
<td><p><span data-ttu-id="15ccc-128">Varannan vecka</span><span class="sxs-lookup"><span data-stu-id="15ccc-128">Biweekly</span></span></p></td>
<td><p><span data-ttu-id="15ccc-129">X-2</span><span class="sxs-lookup"><span data-stu-id="15ccc-129">X-2</span></span></p></td>
<td><p><span data-ttu-id="15ccc-130">2007-04-01</span><span class="sxs-lookup"><span data-stu-id="15ccc-130">04-01-2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15ccc-131">3</span><span class="sxs-lookup"><span data-stu-id="15ccc-131">3</span></span></p></td>
<td><p><span data-ttu-id="15ccc-132"><strong>Timme</strong></span><span class="sxs-lookup"><span data-stu-id="15ccc-132"><strong>Hour</strong></span></span></p></td>
<td><p><span data-ttu-id="15ccc-133">SAL3</span><span class="sxs-lookup"><span data-stu-id="15ccc-133">SAL3</span></span></p></td>
<td><p><span data-ttu-id="15ccc-134">Varje vecka</span><span class="sxs-lookup"><span data-stu-id="15ccc-134">Weekly</span></span></p></td>
<td><p><span data-ttu-id="15ccc-135">X-2</span><span class="sxs-lookup"><span data-stu-id="15ccc-135">X-2</span></span></p></td>
<td><p><span data-ttu-id="15ccc-136">2007-04-01</span><span class="sxs-lookup"><span data-stu-id="15ccc-136">04-01-2007</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="15ccc-137">Du anger inte några tidsfönster för serviceavtalsraderna.</span><span class="sxs-lookup"><span data-stu-id="15ccc-137">You do not specify time windows for any of the service agreement lines.</span></span> <span data-ttu-id="15ccc-138">Därför flyttas serviceorderraderna inte från den beräknade dag de infaller.</span><span class="sxs-lookup"><span data-stu-id="15ccc-138">Therefore, the service order lines will not move from the calculated day on which they fall.</span></span>

<span data-ttu-id="15ccc-139">Därefter skapar du serviceavtalsrader i formuläret **Skapa serviceorder** från 2007-04-01 till 2007-04-30.</span><span class="sxs-lookup"><span data-stu-id="15ccc-139">Next, you generate service order lines from the **Create service orders** form from 04-01-2007 until 04-30-2007.</span></span>

<span data-ttu-id="15ccc-140">Totalt skapas 10 serviceorder.</span><span class="sxs-lookup"><span data-stu-id="15ccc-140">In total, 10 service orders are created.</span></span> <span data-ttu-id="15ccc-141">Eftersom du valde den kombinerade inställningen **Per serviceobjekt**, har de serviceorder som skapas endast serviceorderrader med ett specifikt serviceobjekt.</span><span class="sxs-lookup"><span data-stu-id="15ccc-141">Because the combined setting that you selected was **By service object**, all service orders that are created have only service order lines with one specific service object.</span></span> <span data-ttu-id="15ccc-142">Serviceorderrader som genereras från serviceavtalet och har samma servicedatum och samma objekt kombineras till en serviceorder.</span><span class="sxs-lookup"><span data-stu-id="15ccc-142">Service order lines that are generated from the service agreement and have the same service date and object are combined on the same service order.</span></span>


> [!NOTE]
> <P><span data-ttu-id="15ccc-143">I det här exemplet finns det inga stängda dagar i den kalender som angavs i formuläret <STRONG>Servicehanteringsparametrar</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="15ccc-143">In this example, the calendar that is specified in the <STRONG>Service management parameters</STRONG> form has no closed days.</span></span></P>



<span data-ttu-id="15ccc-144">Ytterligare gruppering av serviceorderrader till serviceordrar görs enligt de tidsfönster som du anger på serviceavtalsraderna.</span><span class="sxs-lookup"><span data-stu-id="15ccc-144">Additional grouping of service order lines into service orders occurs according to any time window that you specify on the service agreement lines.</span></span>

## <a name="see-also"></a><span data-ttu-id="15ccc-145">Se även</span><span class="sxs-lookup"><span data-stu-id="15ccc-145">See also</span></span>

[<span data-ttu-id="15ccc-146">Skapa serviceorder automatiskt</span><span class="sxs-lookup"><span data-stu-id="15ccc-146">Create service orders automatically</span></span>](create-service-orders-automatically.md)

  


