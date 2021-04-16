---
title: Exempel på avdragsdagar
description: Exempel på avdragsdagar.
author: ShylaThompson
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 90a2efff0add508ddb3d750bb3ca27ea35bf113a
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5836072"
---
# <a name="reduction-days-example"></a><span data-ttu-id="d2fba-103">Exempel på avdragsdagar</span><span class="sxs-lookup"><span data-stu-id="d2fba-103">Reduction days example</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="d2fba-104">Du har skapat en abonnemangstransaktion för en kunds underhållsabonnemang på det sätt som beskrivs i tabellen nedan.</span><span class="sxs-lookup"><span data-stu-id="d2fba-104">You have created a subscription transaction for a customer's maintenance subscription, as described in the following table.</span></span>

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
<th><p><span data-ttu-id="d2fba-105">Från-datum</span><span class="sxs-lookup"><span data-stu-id="d2fba-105">From date</span></span></p></th>
<th><p><span data-ttu-id="d2fba-106">Till-datum</span><span class="sxs-lookup"><span data-stu-id="d2fba-106">To date</span></span></p></th>
<th><p><span data-ttu-id="d2fba-107">Abonnemang</span><span class="sxs-lookup"><span data-stu-id="d2fba-107">Subscription</span></span></p></th>
<th><p><span data-ttu-id="d2fba-108">Abonnemangstyp</span><span class="sxs-lookup"><span data-stu-id="d2fba-108">Subscription type</span></span></p></th>
<th><p><span data-ttu-id="d2fba-109">Project</span><span class="sxs-lookup"><span data-stu-id="d2fba-109">Project</span></span></p></th>
<th><p><span data-ttu-id="d2fba-110">Kategori</span><span class="sxs-lookup"><span data-stu-id="d2fba-110">Category</span></span></p></th>
<th><p><span data-ttu-id="d2fba-111">Försäljningsvaluta</span><span class="sxs-lookup"><span data-stu-id="d2fba-111">Sales currency</span></span></p></th>
<th><p><span data-ttu-id="d2fba-112">Försäljningspris</span><span class="sxs-lookup"><span data-stu-id="d2fba-112">Sales price</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d2fba-113">01 mars 2011</span><span class="sxs-lookup"><span data-stu-id="d2fba-113">March 01, 2011</span></span></p></td>
<td><p><span data-ttu-id="d2fba-114">31 mars 2011</span><span class="sxs-lookup"><span data-stu-id="d2fba-114">March 31, 2011</span></span></p></td>
<td><p><span data-ttu-id="d2fba-115">NR-2</span><span class="sxs-lookup"><span data-stu-id="d2fba-115">NR-2</span></span></p></td>
<td><p><span data-ttu-id="d2fba-116"><strong>Vanligt</strong></span><span class="sxs-lookup"><span data-stu-id="d2fba-116"><strong>Regular</strong></span></span></p></td>
<td><p><span data-ttu-id="d2fba-117">9013</span><span class="sxs-lookup"><span data-stu-id="d2fba-117">9013</span></span></p></td>
<td><p><span data-ttu-id="d2fba-118">Underkategori2</span><span class="sxs-lookup"><span data-stu-id="d2fba-118">SubCat2</span></span></p></td>
<td><p><span data-ttu-id="d2fba-119">Euro</span><span class="sxs-lookup"><span data-stu-id="d2fba-119">EUR</span></span></p></td>
<td><p><span data-ttu-id="d2fba-120">200,00</span><span class="sxs-lookup"><span data-stu-id="d2fba-120">200.00</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d2fba-121">Kunden rapporterar att han eller hon inte behöver servicetäckning under två dagar (10 och 11 mars).</span><span class="sxs-lookup"><span data-stu-id="d2fba-121">The customer reports that it does not need service coverage for two days (March 10 and March 11).</span></span> <span data-ttu-id="d2fba-122">Du går med på att minska abonnemanget med dessa två dagar.</span><span class="sxs-lookup"><span data-stu-id="d2fba-122">You agree to reduce the subscription by these two days.</span></span>

<span data-ttu-id="d2fba-123">Du skapar en ny transaktion av typen **Reduceringsdagar** på det sätt som beskrivs i tabellen nedan.</span><span class="sxs-lookup"><span data-stu-id="d2fba-123">You create a new transaction of the **Reduction days** type, as described in the following table.</span></span>

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
<th><p><span data-ttu-id="d2fba-124">Från-datum</span><span class="sxs-lookup"><span data-stu-id="d2fba-124">From date</span></span></p></th>
<th><p><span data-ttu-id="d2fba-125">Till-datum</span><span class="sxs-lookup"><span data-stu-id="d2fba-125">To date</span></span></p></th>
<th><p><span data-ttu-id="d2fba-126">Abonnemang</span><span class="sxs-lookup"><span data-stu-id="d2fba-126">Subscription</span></span></p></th>
<th><p><span data-ttu-id="d2fba-127">Abonnemangstyp</span><span class="sxs-lookup"><span data-stu-id="d2fba-127">Subscription type</span></span></p></th>
<th><p><span data-ttu-id="d2fba-128">Project</span><span class="sxs-lookup"><span data-stu-id="d2fba-128">Project</span></span></p></th>
<th><p><span data-ttu-id="d2fba-129">Kategori</span><span class="sxs-lookup"><span data-stu-id="d2fba-129">Category</span></span></p></th>
<th><p><span data-ttu-id="d2fba-130">Försäljningsvaluta</span><span class="sxs-lookup"><span data-stu-id="d2fba-130">Sales currency</span></span></p></th>
<th><p><span data-ttu-id="d2fba-131">Försäljningspris</span><span class="sxs-lookup"><span data-stu-id="d2fba-131">Sales price</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d2fba-132">10 mars 2011</span><span class="sxs-lookup"><span data-stu-id="d2fba-132">March 10, 2011</span></span></p></td>
<td><p><span data-ttu-id="d2fba-133">11 mars 2011</span><span class="sxs-lookup"><span data-stu-id="d2fba-133">March 11, 2011</span></span></p></td>
<td><p><span data-ttu-id="d2fba-134">NR-2</span><span class="sxs-lookup"><span data-stu-id="d2fba-134">NR-2</span></span></p></td>
<td><p><span data-ttu-id="d2fba-135"><strong>Reduceringsdagar</strong></span><span class="sxs-lookup"><span data-stu-id="d2fba-135"><strong>Reduction days</strong></span></span></p></td>
<td><p><span data-ttu-id="d2fba-136">9013</span><span class="sxs-lookup"><span data-stu-id="d2fba-136">9013</span></span></p></td>
<td><p><span data-ttu-id="d2fba-137">Underkategori2</span><span class="sxs-lookup"><span data-stu-id="d2fba-137">SubCat2</span></span></p></td>
<td><p><span data-ttu-id="d2fba-138">Euro</span><span class="sxs-lookup"><span data-stu-id="d2fba-138">EUR</span></span></p></td>
<td><p><span data-ttu-id="d2fba-139">-12,90</span><span class="sxs-lookup"><span data-stu-id="d2fba-139">-12.90</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d2fba-140">När transaktioner för mars 2011 faktureras minskas försäljningspriset på 200 euro med 12,90 euro.</span><span class="sxs-lookup"><span data-stu-id="d2fba-140">When the transactions for March 2011 are invoiced, the sales price of EUR 200 is reduced by EUR 12.90.</span></span> <span data-ttu-id="d2fba-141">Det debiterbara beloppet för abonnemangstransaktionen blir därför 187,10 euro, och två transaktioner på sammanlagt 187,10 euro faktureras.</span><span class="sxs-lookup"><span data-stu-id="d2fba-141">The chargeable amount for the subscription transaction is therefore EUR 187.10, and two transactions are invoiced at a total of EUR 187.10.</span></span>

## <a name="see-also"></a><span data-ttu-id="d2fba-142">Se även</span><span class="sxs-lookup"><span data-stu-id="d2fba-142">See also</span></span>

[<span data-ttu-id="d2fba-143">Minska antalet dagar på abonnemangsavgifter</span><span class="sxs-lookup"><span data-stu-id="d2fba-143">Reduce the days on subscription fees</span></span>](reduce-the-days-on-subscription-fees.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]