---
title: "Exempel på avdragsdagar"
description: "Exempel på avdragsdagar."
author: YuyuScheller
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMASubscriptionTable
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
ms.openlocfilehash: 69e4b1b0fe100b17e5b2c59be81604019347956f
ms.contentlocale: sv-se
ms.lasthandoff: 05/08/2018

---


# <a name="reduction-days-example"></a><span data-ttu-id="5cb5d-103">Exempel på avdragsdagar</span><span class="sxs-lookup"><span data-stu-id="5cb5d-103">Reduction days example</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="5cb5d-104">Du har skapat en abonnemangstransaktion för en kunds underhållsabonnemang på det sätt som beskrivs i tabellen nedan.</span><span class="sxs-lookup"><span data-stu-id="5cb5d-104">You have created a subscription transaction for a customer's maintenance subscription, as described in the following table.</span></span>

<table>
<colgroup>
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="5cb5d-105">Från-datum</span><span class="sxs-lookup"><span data-stu-id="5cb5d-105">From date</span></span></p></th>
<th><p><span data-ttu-id="5cb5d-106">Till-datum</span><span class="sxs-lookup"><span data-stu-id="5cb5d-106">To date</span></span></p></th>
<th><p><span data-ttu-id="5cb5d-107">Abonnemang</span><span class="sxs-lookup"><span data-stu-id="5cb5d-107">Subscription</span></span></p></th>
<th><p><span data-ttu-id="5cb5d-108">Abonnemangstyp</span><span class="sxs-lookup"><span data-stu-id="5cb5d-108">Subscription type</span></span></p></th>
<th><p><span data-ttu-id="5cb5d-109">Project</span><span class="sxs-lookup"><span data-stu-id="5cb5d-109">Project</span></span></p></th>
<th><p><span data-ttu-id="5cb5d-110">Kategori</span><span class="sxs-lookup"><span data-stu-id="5cb5d-110">Category</span></span></p></th>
<th><p><span data-ttu-id="5cb5d-111">Försäljningsvaluta</span><span class="sxs-lookup"><span data-stu-id="5cb5d-111">Sales currency</span></span></p></th>
<th><p><span data-ttu-id="5cb5d-112">Försäljningspris</span><span class="sxs-lookup"><span data-stu-id="5cb5d-112">Sales price</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5cb5d-113">01 mars 2011</span><span class="sxs-lookup"><span data-stu-id="5cb5d-113">March 01, 2011</span></span></p></td>
<td><p><span data-ttu-id="5cb5d-114">31 mars 2011</span><span class="sxs-lookup"><span data-stu-id="5cb5d-114">March 31, 2011</span></span></p></td>
<td><p><span data-ttu-id="5cb5d-115">NR-2</span><span class="sxs-lookup"><span data-stu-id="5cb5d-115">NR-2</span></span></p></td>
<td><p><span data-ttu-id="5cb5d-116"><strong>Vanligt</strong></span><span class="sxs-lookup"><span data-stu-id="5cb5d-116"><strong>Regular</strong></span></span></p></td>
<td><p><span data-ttu-id="5cb5d-117">9013</span><span class="sxs-lookup"><span data-stu-id="5cb5d-117">9013</span></span></p></td>
<td><p><span data-ttu-id="5cb5d-118">Underkategori2</span><span class="sxs-lookup"><span data-stu-id="5cb5d-118">SubCat2</span></span></p></td>
<td><p><span data-ttu-id="5cb5d-119">Euro</span><span class="sxs-lookup"><span data-stu-id="5cb5d-119">EUR</span></span></p></td>
<td><p><span data-ttu-id="5cb5d-120">200,00</span><span class="sxs-lookup"><span data-stu-id="5cb5d-120">200.00</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5cb5d-121">Kunden rapporterar att han eller hon inte behöver servicetäckning under två dagar (10 och 11 mars).</span><span class="sxs-lookup"><span data-stu-id="5cb5d-121">The customer reports that it does not need service coverage for two days (March 10 and March 11).</span></span> <span data-ttu-id="5cb5d-122">Du går med på att minska abonnemanget med dessa två dagar.</span><span class="sxs-lookup"><span data-stu-id="5cb5d-122">You agree to reduce the subscription by these two days.</span></span>

<span data-ttu-id="5cb5d-123">Du skapar en ny transaktion av typen **Reduceringsdagar** på det sätt som beskrivs i tabellen nedan.</span><span class="sxs-lookup"><span data-stu-id="5cb5d-123">You create a new transaction of the **Reduction days** type, as described in the following table.</span></span>

<table>
<colgroup>
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="5cb5d-124">Från-datum</span><span class="sxs-lookup"><span data-stu-id="5cb5d-124">From date</span></span></p></th>
<th><p><span data-ttu-id="5cb5d-125">Till-datum</span><span class="sxs-lookup"><span data-stu-id="5cb5d-125">To date</span></span></p></th>
<th><p><span data-ttu-id="5cb5d-126">Abonnemang</span><span class="sxs-lookup"><span data-stu-id="5cb5d-126">Subscription</span></span></p></th>
<th><p><span data-ttu-id="5cb5d-127">Abonnemangstyp</span><span class="sxs-lookup"><span data-stu-id="5cb5d-127">Subscription type</span></span></p></th>
<th><p><span data-ttu-id="5cb5d-128">Project</span><span class="sxs-lookup"><span data-stu-id="5cb5d-128">Project</span></span></p></th>
<th><p><span data-ttu-id="5cb5d-129">Kategori</span><span class="sxs-lookup"><span data-stu-id="5cb5d-129">Category</span></span></p></th>
<th><p><span data-ttu-id="5cb5d-130">Försäljningsvaluta</span><span class="sxs-lookup"><span data-stu-id="5cb5d-130">Sales currency</span></span></p></th>
<th><p><span data-ttu-id="5cb5d-131">Försäljningspris</span><span class="sxs-lookup"><span data-stu-id="5cb5d-131">Sales price</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5cb5d-132">10 mars 2011</span><span class="sxs-lookup"><span data-stu-id="5cb5d-132">March 10, 2011</span></span></p></td>
<td><p><span data-ttu-id="5cb5d-133">11 mars 2011</span><span class="sxs-lookup"><span data-stu-id="5cb5d-133">March 11, 2011</span></span></p></td>
<td><p><span data-ttu-id="5cb5d-134">NR-2</span><span class="sxs-lookup"><span data-stu-id="5cb5d-134">NR-2</span></span></p></td>
<td><p><span data-ttu-id="5cb5d-135"><strong>Reduceringsdagar</strong></span><span class="sxs-lookup"><span data-stu-id="5cb5d-135"><strong>Reduction days</strong></span></span></p></td>
<td><p><span data-ttu-id="5cb5d-136">9013</span><span class="sxs-lookup"><span data-stu-id="5cb5d-136">9013</span></span></p></td>
<td><p><span data-ttu-id="5cb5d-137">Underkategori2</span><span class="sxs-lookup"><span data-stu-id="5cb5d-137">SubCat2</span></span></p></td>
<td><p><span data-ttu-id="5cb5d-138">Euro</span><span class="sxs-lookup"><span data-stu-id="5cb5d-138">EUR</span></span></p></td>
<td><p><span data-ttu-id="5cb5d-139">-12,90</span><span class="sxs-lookup"><span data-stu-id="5cb5d-139">-12.90</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5cb5d-140">När transaktioner för mars 2011 faktureras minskas försäljningspriset på 200 euro med 12,90 euro.</span><span class="sxs-lookup"><span data-stu-id="5cb5d-140">When the transactions for March 2011 are invoiced, the sales price of EUR 200 is reduced by EUR 12.90.</span></span> <span data-ttu-id="5cb5d-141">Det debiterbara beloppet för abonnemangstransaktionen blir därför 187,10 euro, och två transaktioner på sammanlagt 187,10 euro faktureras.</span><span class="sxs-lookup"><span data-stu-id="5cb5d-141">The chargeable amount for the subscription transaction is therefore EUR 187.10, and two transactions are invoiced at a total of EUR 187.10.</span></span>

## <a name="see-also"></a><span data-ttu-id="5cb5d-142">Se även</span><span class="sxs-lookup"><span data-stu-id="5cb5d-142">See also</span></span>

[<span data-ttu-id="5cb5d-143">Minska antalet dagar på abonnemangsavgifter</span><span class="sxs-lookup"><span data-stu-id="5cb5d-143">Reduce the days on subscription fees</span></span>](reduce-the-days-on-subscription-fees.md)

  


