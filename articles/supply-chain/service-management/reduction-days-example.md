---
title: Exempel på avdragsdagar
description: Exempel på avdragsdagar.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMASubscriptionTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 509d1a9e2abd79938376209d8feab1b935394833
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "5010532"
---
# <a name="reduction-days-example"></a><span data-ttu-id="c12da-103">Exempel på avdragsdagar</span><span class="sxs-lookup"><span data-stu-id="c12da-103">Reduction days example</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="c12da-104">Du har skapat en abonnemangstransaktion för en kunds underhållsabonnemang på det sätt som beskrivs i tabellen nedan.</span><span class="sxs-lookup"><span data-stu-id="c12da-104">You have created a subscription transaction for a customer's maintenance subscription, as described in the following table.</span></span>

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
<th><p><span data-ttu-id="c12da-105">Från-datum</span><span class="sxs-lookup"><span data-stu-id="c12da-105">From date</span></span></p></th>
<th><p><span data-ttu-id="c12da-106">Till-datum</span><span class="sxs-lookup"><span data-stu-id="c12da-106">To date</span></span></p></th>
<th><p><span data-ttu-id="c12da-107">Abonnemang</span><span class="sxs-lookup"><span data-stu-id="c12da-107">Subscription</span></span></p></th>
<th><p><span data-ttu-id="c12da-108">Abonnemangstyp</span><span class="sxs-lookup"><span data-stu-id="c12da-108">Subscription type</span></span></p></th>
<th><p><span data-ttu-id="c12da-109">Project</span><span class="sxs-lookup"><span data-stu-id="c12da-109">Project</span></span></p></th>
<th><p><span data-ttu-id="c12da-110">Kategori</span><span class="sxs-lookup"><span data-stu-id="c12da-110">Category</span></span></p></th>
<th><p><span data-ttu-id="c12da-111">Försäljningsvaluta</span><span class="sxs-lookup"><span data-stu-id="c12da-111">Sales currency</span></span></p></th>
<th><p><span data-ttu-id="c12da-112">Försäljningspris</span><span class="sxs-lookup"><span data-stu-id="c12da-112">Sales price</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c12da-113">01 mars 2011</span><span class="sxs-lookup"><span data-stu-id="c12da-113">March 01, 2011</span></span></p></td>
<td><p><span data-ttu-id="c12da-114">31 mars 2011</span><span class="sxs-lookup"><span data-stu-id="c12da-114">March 31, 2011</span></span></p></td>
<td><p><span data-ttu-id="c12da-115">NR-2</span><span class="sxs-lookup"><span data-stu-id="c12da-115">NR-2</span></span></p></td>
<td><p><span data-ttu-id="c12da-116"><strong>Vanligt</strong></span><span class="sxs-lookup"><span data-stu-id="c12da-116"><strong>Regular</strong></span></span></p></td>
<td><p><span data-ttu-id="c12da-117">9013</span><span class="sxs-lookup"><span data-stu-id="c12da-117">9013</span></span></p></td>
<td><p><span data-ttu-id="c12da-118">Underkategori2</span><span class="sxs-lookup"><span data-stu-id="c12da-118">SubCat2</span></span></p></td>
<td><p><span data-ttu-id="c12da-119">Euro</span><span class="sxs-lookup"><span data-stu-id="c12da-119">EUR</span></span></p></td>
<td><p><span data-ttu-id="c12da-120">200,00</span><span class="sxs-lookup"><span data-stu-id="c12da-120">200.00</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c12da-121">Kunden rapporterar att han eller hon inte behöver servicetäckning under två dagar (10 och 11 mars).</span><span class="sxs-lookup"><span data-stu-id="c12da-121">The customer reports that it does not need service coverage for two days (March 10 and March 11).</span></span> <span data-ttu-id="c12da-122">Du går med på att minska abonnemanget med dessa två dagar.</span><span class="sxs-lookup"><span data-stu-id="c12da-122">You agree to reduce the subscription by these two days.</span></span>

<span data-ttu-id="c12da-123">Du skapar en ny transaktion av typen **Reduceringsdagar** på det sätt som beskrivs i tabellen nedan.</span><span class="sxs-lookup"><span data-stu-id="c12da-123">You create a new transaction of the **Reduction days** type, as described in the following table.</span></span>

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
<th><p><span data-ttu-id="c12da-124">Från-datum</span><span class="sxs-lookup"><span data-stu-id="c12da-124">From date</span></span></p></th>
<th><p><span data-ttu-id="c12da-125">Till-datum</span><span class="sxs-lookup"><span data-stu-id="c12da-125">To date</span></span></p></th>
<th><p><span data-ttu-id="c12da-126">Abonnemang</span><span class="sxs-lookup"><span data-stu-id="c12da-126">Subscription</span></span></p></th>
<th><p><span data-ttu-id="c12da-127">Abonnemangstyp</span><span class="sxs-lookup"><span data-stu-id="c12da-127">Subscription type</span></span></p></th>
<th><p><span data-ttu-id="c12da-128">Project</span><span class="sxs-lookup"><span data-stu-id="c12da-128">Project</span></span></p></th>
<th><p><span data-ttu-id="c12da-129">Kategori</span><span class="sxs-lookup"><span data-stu-id="c12da-129">Category</span></span></p></th>
<th><p><span data-ttu-id="c12da-130">Försäljningsvaluta</span><span class="sxs-lookup"><span data-stu-id="c12da-130">Sales currency</span></span></p></th>
<th><p><span data-ttu-id="c12da-131">Försäljningspris</span><span class="sxs-lookup"><span data-stu-id="c12da-131">Sales price</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c12da-132">10 mars 2011</span><span class="sxs-lookup"><span data-stu-id="c12da-132">March 10, 2011</span></span></p></td>
<td><p><span data-ttu-id="c12da-133">11 mars 2011</span><span class="sxs-lookup"><span data-stu-id="c12da-133">March 11, 2011</span></span></p></td>
<td><p><span data-ttu-id="c12da-134">NR-2</span><span class="sxs-lookup"><span data-stu-id="c12da-134">NR-2</span></span></p></td>
<td><p><span data-ttu-id="c12da-135"><strong>Reduceringsdagar</strong></span><span class="sxs-lookup"><span data-stu-id="c12da-135"><strong>Reduction days</strong></span></span></p></td>
<td><p><span data-ttu-id="c12da-136">9013</span><span class="sxs-lookup"><span data-stu-id="c12da-136">9013</span></span></p></td>
<td><p><span data-ttu-id="c12da-137">Underkategori2</span><span class="sxs-lookup"><span data-stu-id="c12da-137">SubCat2</span></span></p></td>
<td><p><span data-ttu-id="c12da-138">Euro</span><span class="sxs-lookup"><span data-stu-id="c12da-138">EUR</span></span></p></td>
<td><p><span data-ttu-id="c12da-139">-12,90</span><span class="sxs-lookup"><span data-stu-id="c12da-139">-12.90</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c12da-140">När transaktioner för mars 2011 faktureras minskas försäljningspriset på 200 euro med 12,90 euro.</span><span class="sxs-lookup"><span data-stu-id="c12da-140">When the transactions for March 2011 are invoiced, the sales price of EUR 200 is reduced by EUR 12.90.</span></span> <span data-ttu-id="c12da-141">Det debiterbara beloppet för abonnemangstransaktionen blir därför 187,10 euro, och två transaktioner på sammanlagt 187,10 euro faktureras.</span><span class="sxs-lookup"><span data-stu-id="c12da-141">The chargeable amount for the subscription transaction is therefore EUR 187.10, and two transactions are invoiced at a total of EUR 187.10.</span></span>

## <a name="see-also"></a><span data-ttu-id="c12da-142">Se även</span><span class="sxs-lookup"><span data-stu-id="c12da-142">See also</span></span>

[<span data-ttu-id="c12da-143">Minska antalet dagar på abonnemangsavgifter</span><span class="sxs-lookup"><span data-stu-id="c12da-143">Reduce the days on subscription fees</span></span>](reduce-the-days-on-subscription-fees.md)

  


