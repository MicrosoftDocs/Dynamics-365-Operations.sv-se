---
title: Kombinera serviceorder
description: Du kan kombinera serviceorder.
author: ShylaThompson
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 41b4a3234e4104372f1052d89c2417984e9cd10d
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5840567"
---
# <a name="combine-service-orders"></a><span data-ttu-id="fadf5-103">Kombinera serviceorder</span><span class="sxs-lookup"><span data-stu-id="fadf5-103">Combine service orders</span></span>   

[!include [banner](../includes/banner.md)]


<span data-ttu-id="fadf5-104">När du skapar serviceorderrader automatiskt i formuläret **serviceavtal** kan du välja ett av följande alternativ för att ange hur du vill gruppera dem:</span><span class="sxs-lookup"><span data-stu-id="fadf5-104">When you create service order lines automatically in the **Service agreements** form, you can choose one of the following options to specify how you want to group them:</span></span>

  - <span data-ttu-id="fadf5-105">**Per serviceavtal**</span><span class="sxs-lookup"><span data-stu-id="fadf5-105">**By service agreement**</span></span>

  - <span data-ttu-id="fadf5-106">**Per serviceuppgift**</span><span class="sxs-lookup"><span data-stu-id="fadf5-106">**By service task**</span></span>

  - <span data-ttu-id="fadf5-107">**Per anställd**</span><span class="sxs-lookup"><span data-stu-id="fadf5-107">**By employee**</span></span>

  - <span data-ttu-id="fadf5-108">**Per serviceobjekt**</span><span class="sxs-lookup"><span data-stu-id="fadf5-108">**By service object**</span></span>

## <a name="example"></a><span data-ttu-id="fadf5-109">Exempel</span><span class="sxs-lookup"><span data-stu-id="fadf5-109">Example</span></span>

<span data-ttu-id="fadf5-110">Du skapar ett serviceavtal med startdatum 2007-03-31.</span><span class="sxs-lookup"><span data-stu-id="fadf5-110">You create a service agreement that has a start date on 03-31-2007.</span></span> <span data-ttu-id="fadf5-111">I fältet **kombinera serviceorder** väljer du **Per serviceobjekt**.</span><span class="sxs-lookup"><span data-stu-id="fadf5-111">In the **Combine service orders** field, you specify **By service object**.</span></span> <span data-ttu-id="fadf5-112">Därefter skapar du följande serviceavtalsrader:</span><span class="sxs-lookup"><span data-stu-id="fadf5-112">You then create the following service agreement lines:</span></span>

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
<th><p><span data-ttu-id="fadf5-113">Avtalsradnummer</span><span class="sxs-lookup"><span data-stu-id="fadf5-113">Agreement line number</span></span></p></th>
<th><p><span data-ttu-id="fadf5-114">transaktionstyp</span><span class="sxs-lookup"><span data-stu-id="fadf5-114">Transaction type</span></span></p></th>
<th><p><span data-ttu-id="fadf5-115">beskrivning</span><span class="sxs-lookup"><span data-stu-id="fadf5-115">Description</span></span></p></th>
<th><p><span data-ttu-id="fadf5-116">Intervall</span><span class="sxs-lookup"><span data-stu-id="fadf5-116">Interval</span></span></p></th>
<th><p><span data-ttu-id="fadf5-117">Serviceobjekt</span><span class="sxs-lookup"><span data-stu-id="fadf5-117">Service object</span></span></p></th>
<th><p><span data-ttu-id="fadf5-118">Startdatum</span><span class="sxs-lookup"><span data-stu-id="fadf5-118">Start date</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fadf5-119">1</span><span class="sxs-lookup"><span data-stu-id="fadf5-119">1</span></span></p></td>
<td><p><span data-ttu-id="fadf5-120"><strong>Timme</strong></span><span class="sxs-lookup"><span data-stu-id="fadf5-120"><strong>Hour</strong></span></span></p></td>
<td><p><span data-ttu-id="fadf5-121">SAL1</span><span class="sxs-lookup"><span data-stu-id="fadf5-121">SAL1</span></span></p></td>
<td><p><span data-ttu-id="fadf5-122">Varje vecka</span><span class="sxs-lookup"><span data-stu-id="fadf5-122">Weekly</span></span></p></td>
<td><p><span data-ttu-id="fadf5-123">X-1</span><span class="sxs-lookup"><span data-stu-id="fadf5-123">X-1</span></span></p></td>
<td><p><span data-ttu-id="fadf5-124">2007-04-01</span><span class="sxs-lookup"><span data-stu-id="fadf5-124">04-01-2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fadf5-125">2</span><span class="sxs-lookup"><span data-stu-id="fadf5-125">2</span></span></p></td>
<td><p><span data-ttu-id="fadf5-126"><strong>Timme</strong></span><span class="sxs-lookup"><span data-stu-id="fadf5-126"><strong>Hour</strong></span></span></p></td>
<td><p><span data-ttu-id="fadf5-127">SAL2</span><span class="sxs-lookup"><span data-stu-id="fadf5-127">SAL2</span></span></p></td>
<td><p><span data-ttu-id="fadf5-128">Varannan vecka</span><span class="sxs-lookup"><span data-stu-id="fadf5-128">Biweekly</span></span></p></td>
<td><p><span data-ttu-id="fadf5-129">X-2</span><span class="sxs-lookup"><span data-stu-id="fadf5-129">X-2</span></span></p></td>
<td><p><span data-ttu-id="fadf5-130">2007-04-01</span><span class="sxs-lookup"><span data-stu-id="fadf5-130">04-01-2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fadf5-131">3</span><span class="sxs-lookup"><span data-stu-id="fadf5-131">3</span></span></p></td>
<td><p><span data-ttu-id="fadf5-132"><strong>Timme</strong></span><span class="sxs-lookup"><span data-stu-id="fadf5-132"><strong>Hour</strong></span></span></p></td>
<td><p><span data-ttu-id="fadf5-133">SAL3</span><span class="sxs-lookup"><span data-stu-id="fadf5-133">SAL3</span></span></p></td>
<td><p><span data-ttu-id="fadf5-134">Varje vecka</span><span class="sxs-lookup"><span data-stu-id="fadf5-134">Weekly</span></span></p></td>
<td><p><span data-ttu-id="fadf5-135">X-2</span><span class="sxs-lookup"><span data-stu-id="fadf5-135">X-2</span></span></p></td>
<td><p><span data-ttu-id="fadf5-136">2007-04-01</span><span class="sxs-lookup"><span data-stu-id="fadf5-136">04-01-2007</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="fadf5-137">Du anger inte några tidsfönster för serviceavtalsraderna.</span><span class="sxs-lookup"><span data-stu-id="fadf5-137">You do not specify time windows for any of the service agreement lines.</span></span> <span data-ttu-id="fadf5-138">Därför flyttas serviceorderraderna inte från den beräknade dag de infaller.</span><span class="sxs-lookup"><span data-stu-id="fadf5-138">Therefore, the service order lines will not move from the calculated day on which they fall.</span></span>

<span data-ttu-id="fadf5-139">Därefter skapar du serviceavtalsrader i formuläret **Skapa serviceorder** från 2007-04-01 till 2007-04-30.</span><span class="sxs-lookup"><span data-stu-id="fadf5-139">Next, you generate service order lines from the **Create service orders** form from 04-01-2007 until 04-30-2007.</span></span>

<span data-ttu-id="fadf5-140">Totalt skapas 10 serviceorder.</span><span class="sxs-lookup"><span data-stu-id="fadf5-140">In total, 10 service orders are created.</span></span> <span data-ttu-id="fadf5-141">Eftersom du valde den kombinerade inställningen **Per serviceobjekt**, har de serviceorder som skapas endast serviceorderrader med ett specifikt serviceobjekt.</span><span class="sxs-lookup"><span data-stu-id="fadf5-141">Because the combined setting that you selected was **By service object**, all service orders that are created have only service order lines with one specific service object.</span></span> <span data-ttu-id="fadf5-142">Serviceorderrader som genereras från serviceavtalet och har samma servicedatum och samma objekt kombineras till en serviceorder.</span><span class="sxs-lookup"><span data-stu-id="fadf5-142">Service order lines that are generated from the service agreement and have the same service date and object are combined on the same service order.</span></span>


> [!NOTE]
> <P><span data-ttu-id="fadf5-143">I det här exemplet finns det inga stängda dagar i den kalender som angavs i formuläret <STRONG>Servicehanteringsparametrar</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="fadf5-143">In this example, the calendar that is specified in the <STRONG>Service management parameters</STRONG> form has no closed days.</span></span></P>



<span data-ttu-id="fadf5-144">Ytterligare gruppering av serviceorderrader till serviceordrar görs enligt de tidsfönster som du anger på serviceavtalsraderna.</span><span class="sxs-lookup"><span data-stu-id="fadf5-144">Additional grouping of service order lines into service orders occurs according to any time window that you specify on the service agreement lines.</span></span>

## <a name="see-also"></a><span data-ttu-id="fadf5-145">Se även</span><span class="sxs-lookup"><span data-stu-id="fadf5-145">See also</span></span>

[<span data-ttu-id="fadf5-146">Skapa serviceorder automatiskt</span><span class="sxs-lookup"><span data-stu-id="fadf5-146">Create service orders automatically</span></span>](create-service-orders-automatically.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]