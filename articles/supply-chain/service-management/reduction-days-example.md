---
title: Exempel på avdragsdagar
description: Exempel på avdragsdagar.
author: ShylaThompson
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMASubscriptionTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 46b38579e8a6246476d0893e1a047ad434f6d399
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1564518"
---
# <a name="reduction-days-example"></a><span data-ttu-id="a6973-103">Exempel på avdragsdagar</span><span class="sxs-lookup"><span data-stu-id="a6973-103">Reduction days example</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="a6973-104">Du har skapat en abonnemangstransaktion för en kunds underhållsabonnemang på det sätt som beskrivs i tabellen nedan.</span><span class="sxs-lookup"><span data-stu-id="a6973-104">You have created a subscription transaction for a customer's maintenance subscription, as described in the following table.</span></span>

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
<th><p><span data-ttu-id="a6973-105">Från-datum</span><span class="sxs-lookup"><span data-stu-id="a6973-105">From date</span></span></p></th>
<th><p><span data-ttu-id="a6973-106">Till-datum</span><span class="sxs-lookup"><span data-stu-id="a6973-106">To date</span></span></p></th>
<th><p><span data-ttu-id="a6973-107">Abonnemang</span><span class="sxs-lookup"><span data-stu-id="a6973-107">Subscription</span></span></p></th>
<th><p><span data-ttu-id="a6973-108">Abonnemangstyp</span><span class="sxs-lookup"><span data-stu-id="a6973-108">Subscription type</span></span></p></th>
<th><p><span data-ttu-id="a6973-109">Project</span><span class="sxs-lookup"><span data-stu-id="a6973-109">Project</span></span></p></th>
<th><p><span data-ttu-id="a6973-110">Kategori</span><span class="sxs-lookup"><span data-stu-id="a6973-110">Category</span></span></p></th>
<th><p><span data-ttu-id="a6973-111">Försäljningsvaluta</span><span class="sxs-lookup"><span data-stu-id="a6973-111">Sales currency</span></span></p></th>
<th><p><span data-ttu-id="a6973-112">Försäljningspris</span><span class="sxs-lookup"><span data-stu-id="a6973-112">Sales price</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a6973-113">01 mars 2011</span><span class="sxs-lookup"><span data-stu-id="a6973-113">March 01, 2011</span></span></p></td>
<td><p><span data-ttu-id="a6973-114">31 mars 2011</span><span class="sxs-lookup"><span data-stu-id="a6973-114">March 31, 2011</span></span></p></td>
<td><p><span data-ttu-id="a6973-115">NR-2</span><span class="sxs-lookup"><span data-stu-id="a6973-115">NR-2</span></span></p></td>
<td><p><span data-ttu-id="a6973-116"><strong>Vanligt</strong></span><span class="sxs-lookup"><span data-stu-id="a6973-116"><strong>Regular</strong></span></span></p></td>
<td><p><span data-ttu-id="a6973-117">9013</span><span class="sxs-lookup"><span data-stu-id="a6973-117">9013</span></span></p></td>
<td><p><span data-ttu-id="a6973-118">Underkategori2</span><span class="sxs-lookup"><span data-stu-id="a6973-118">SubCat2</span></span></p></td>
<td><p><span data-ttu-id="a6973-119">Euro</span><span class="sxs-lookup"><span data-stu-id="a6973-119">EUR</span></span></p></td>
<td><p><span data-ttu-id="a6973-120">200,00</span><span class="sxs-lookup"><span data-stu-id="a6973-120">200.00</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a6973-121">Kunden rapporterar att han eller hon inte behöver servicetäckning under två dagar (10 och 11 mars).</span><span class="sxs-lookup"><span data-stu-id="a6973-121">The customer reports that it does not need service coverage for two days (March 10 and March 11).</span></span> <span data-ttu-id="a6973-122">Du går med på att minska abonnemanget med dessa två dagar.</span><span class="sxs-lookup"><span data-stu-id="a6973-122">You agree to reduce the subscription by these two days.</span></span>

<span data-ttu-id="a6973-123">Du skapar en ny transaktion av typen **Reduceringsdagar** på det sätt som beskrivs i tabellen nedan.</span><span class="sxs-lookup"><span data-stu-id="a6973-123">You create a new transaction of the **Reduction days** type, as described in the following table.</span></span>

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
<th><p><span data-ttu-id="a6973-124">Från-datum</span><span class="sxs-lookup"><span data-stu-id="a6973-124">From date</span></span></p></th>
<th><p><span data-ttu-id="a6973-125">Till-datum</span><span class="sxs-lookup"><span data-stu-id="a6973-125">To date</span></span></p></th>
<th><p><span data-ttu-id="a6973-126">Abonnemang</span><span class="sxs-lookup"><span data-stu-id="a6973-126">Subscription</span></span></p></th>
<th><p><span data-ttu-id="a6973-127">Abonnemangstyp</span><span class="sxs-lookup"><span data-stu-id="a6973-127">Subscription type</span></span></p></th>
<th><p><span data-ttu-id="a6973-128">Project</span><span class="sxs-lookup"><span data-stu-id="a6973-128">Project</span></span></p></th>
<th><p><span data-ttu-id="a6973-129">Kategori</span><span class="sxs-lookup"><span data-stu-id="a6973-129">Category</span></span></p></th>
<th><p><span data-ttu-id="a6973-130">Försäljningsvaluta</span><span class="sxs-lookup"><span data-stu-id="a6973-130">Sales currency</span></span></p></th>
<th><p><span data-ttu-id="a6973-131">Försäljningspris</span><span class="sxs-lookup"><span data-stu-id="a6973-131">Sales price</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a6973-132">10 mars 2011</span><span class="sxs-lookup"><span data-stu-id="a6973-132">March 10, 2011</span></span></p></td>
<td><p><span data-ttu-id="a6973-133">11 mars 2011</span><span class="sxs-lookup"><span data-stu-id="a6973-133">March 11, 2011</span></span></p></td>
<td><p><span data-ttu-id="a6973-134">NR-2</span><span class="sxs-lookup"><span data-stu-id="a6973-134">NR-2</span></span></p></td>
<td><p><span data-ttu-id="a6973-135"><strong>Reduceringsdagar</strong></span><span class="sxs-lookup"><span data-stu-id="a6973-135"><strong>Reduction days</strong></span></span></p></td>
<td><p><span data-ttu-id="a6973-136">9013</span><span class="sxs-lookup"><span data-stu-id="a6973-136">9013</span></span></p></td>
<td><p><span data-ttu-id="a6973-137">Underkategori2</span><span class="sxs-lookup"><span data-stu-id="a6973-137">SubCat2</span></span></p></td>
<td><p><span data-ttu-id="a6973-138">Euro</span><span class="sxs-lookup"><span data-stu-id="a6973-138">EUR</span></span></p></td>
<td><p><span data-ttu-id="a6973-139">-12,90</span><span class="sxs-lookup"><span data-stu-id="a6973-139">-12.90</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a6973-140">När transaktioner för mars 2011 faktureras minskas försäljningspriset på 200 euro med 12,90 euro.</span><span class="sxs-lookup"><span data-stu-id="a6973-140">When the transactions for March 2011 are invoiced, the sales price of EUR 200 is reduced by EUR 12.90.</span></span> <span data-ttu-id="a6973-141">Det debiterbara beloppet för abonnemangstransaktionen blir därför 187,10 euro, och två transaktioner på sammanlagt 187,10 euro faktureras.</span><span class="sxs-lookup"><span data-stu-id="a6973-141">The chargeable amount for the subscription transaction is therefore EUR 187.10, and two transactions are invoiced at a total of EUR 187.10.</span></span>

## <a name="see-also"></a><span data-ttu-id="a6973-142">Se även</span><span class="sxs-lookup"><span data-stu-id="a6973-142">See also</span></span>

[<span data-ttu-id="a6973-143">Minska antalet dagar på abonnemangsavgifter</span><span class="sxs-lookup"><span data-stu-id="a6973-143">Reduce the days on subscription fees</span></span>](reduce-the-days-on-subscription-fees.md)

  


