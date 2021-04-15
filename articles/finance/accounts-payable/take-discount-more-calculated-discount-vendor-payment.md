---
title: Ta mer än den beräknade rabatten för en leverantörsbetalning
description: Den här artikeln går igenom ett scenario där en kassarabatt utnyttjas för ett belopp som är större än den rabatt som ursprungligen var tillgänglig för fakturan. Det här scenariot kan inträffa om en organisation sluter ett avtal med leverantören om att betala ett lägre belopp på fakturan.
author: abruer
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: roschlom
ms.custom: 14281
ms.assetid: 7f0a4197-95dd-4969-ade9-154815cf659e
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 62f2088ff04a0ef5ffe6ffe47b85f47e6957264d
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5810256"
---
# <a name="take-more-than-the-calculated-discount-for-a-vendor-payment"></a><span data-ttu-id="f29b2-104">Ta mer än den beräknade rabatten för en leverantörsbetalning</span><span class="sxs-lookup"><span data-stu-id="f29b2-104">Take more than the calculated discount for a vendor payment</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f29b2-105">Den här artikeln går igenom ett scenario där en kassarabatt utnyttjas för ett belopp som är större än den rabatt som ursprungligen var tillgänglig för fakturan.</span><span class="sxs-lookup"><span data-stu-id="f29b2-105">This article walks you through a scenario where a cash discount is taken for an amount that is more than the discount that was originally available on the invoice.</span></span> <span data-ttu-id="f29b2-106">Det här scenariot kan inträffa om en organisation sluter ett avtal med leverantören om att betala ett lägre belopp på fakturan.</span><span class="sxs-lookup"><span data-stu-id="f29b2-106">This scenario might occur if an organization comes to an agreement with the vendor to pay a smaller amount on the invoice.</span></span> 

<span data-ttu-id="f29b2-107">Leverantör 3051 ger Fabrikam en kassarabatt på 4 procent, om en faktura betalas inom 7 dagar.</span><span class="sxs-lookup"><span data-stu-id="f29b2-107">Vendor 3051 gives Fabrikam a cash discount of 4 percent if an invoice is paid in seven days.</span></span> <span data-ttu-id="f29b2-108">Den 29 juni anger den en faktura på 1 000,00.</span><span class="sxs-lookup"><span data-stu-id="f29b2-108">On June 29, April enters an invoice for 1,000.00.</span></span> <span data-ttu-id="f29b2-109">Leverantören låter April göra en rabatt på 60,00 istället för den standardinställda rabatten på 40,00 som är tillgänglig för fakturan.</span><span class="sxs-lookup"><span data-stu-id="f29b2-109">The vendor lets April take a discount of 60.00 instead of the default discount of 40.00 that is available for the invoice.</span></span> <span data-ttu-id="f29b2-110">April registrerar en enstaka betalning genom att använda betalningsjournalen för Leverantörsreskontra.</span><span class="sxs-lookup"><span data-stu-id="f29b2-110">April records a one-off payment by using the Accounts payable payment journal.</span></span> <span data-ttu-id="f29b2-111">Hon registrerar leverantören för betalningen och öppnar sedan sidan **Kvitta transaktioner**.</span><span class="sxs-lookup"><span data-stu-id="f29b2-111">She enters the vendor for the payment and then opens the **Settle transactions** page.</span></span> <span data-ttu-id="f29b2-112">Hon markerar fakturan och ändrar värdet i fältet **Kassarabattbelopp** till **60,00**.</span><span class="sxs-lookup"><span data-stu-id="f29b2-112">She marks the invoice and changes the value in the **Cash discount amount** field to **60.00**.</span></span>

| <span data-ttu-id="f29b2-113">Markera</span><span class="sxs-lookup"><span data-stu-id="f29b2-113">Mark</span></span>     | <span data-ttu-id="f29b2-114">Använd kassarabatt</span><span class="sxs-lookup"><span data-stu-id="f29b2-114">Use cash discount</span></span> | <span data-ttu-id="f29b2-115">Verifikation</span><span class="sxs-lookup"><span data-stu-id="f29b2-115">Voucher</span></span>   | <span data-ttu-id="f29b2-116">Konto</span><span class="sxs-lookup"><span data-stu-id="f29b2-116">Account</span></span> | <span data-ttu-id="f29b2-117">Datum</span><span class="sxs-lookup"><span data-stu-id="f29b2-117">Date</span></span>      | <span data-ttu-id="f29b2-118">Förfallodatum</span><span class="sxs-lookup"><span data-stu-id="f29b2-118">Due date</span></span>  | <span data-ttu-id="f29b2-119">Faktura</span><span class="sxs-lookup"><span data-stu-id="f29b2-119">Invoice</span></span> | <span data-ttu-id="f29b2-120">Belopp i transaktionsvalutan</span><span class="sxs-lookup"><span data-stu-id="f29b2-120">Amount in transaction currency</span></span> | <span data-ttu-id="f29b2-121">Valuta</span><span class="sxs-lookup"><span data-stu-id="f29b2-121">Currency</span></span> | <span data-ttu-id="f29b2-122">Belopp att kvitta</span><span class="sxs-lookup"><span data-stu-id="f29b2-122">Amount to settle</span></span> |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| <span data-ttu-id="f29b2-123">Markerad</span><span class="sxs-lookup"><span data-stu-id="f29b2-123">Selected</span></span> | <span data-ttu-id="f29b2-124">Normal</span><span class="sxs-lookup"><span data-stu-id="f29b2-124">Normal</span></span>            | <span data-ttu-id="f29b2-125">Fakt-10040</span><span class="sxs-lookup"><span data-stu-id="f29b2-125">Inv-10040</span></span> | <span data-ttu-id="f29b2-126">3051</span><span class="sxs-lookup"><span data-stu-id="f29b2-126">3051</span></span>    | <span data-ttu-id="f29b2-127">29/6/2015</span><span class="sxs-lookup"><span data-stu-id="f29b2-127">6/29/2015</span></span> | <span data-ttu-id="f29b2-128">29/7/2015</span><span class="sxs-lookup"><span data-stu-id="f29b2-128">7/29/2015</span></span> | <span data-ttu-id="f29b2-129">10040</span><span class="sxs-lookup"><span data-stu-id="f29b2-129">10040</span></span>   | <span data-ttu-id="f29b2-130">1 000,00</span><span class="sxs-lookup"><span data-stu-id="f29b2-130">1,000.00</span></span>                       | <span data-ttu-id="f29b2-131">USD</span><span class="sxs-lookup"><span data-stu-id="f29b2-131">USD</span></span>      | <span data-ttu-id="f29b2-132">940,00</span><span class="sxs-lookup"><span data-stu-id="f29b2-132">940.00</span></span>           |

<span data-ttu-id="f29b2-133">Information om rabatten visas längst ned på sidan **Kvitta transaktioner**.</span><span class="sxs-lookup"><span data-stu-id="f29b2-133">Discount information appears at the bottom of the **Settle transactions** page.</span></span>

| <span data-ttu-id="f29b2-134">Fält</span><span class="sxs-lookup"><span data-stu-id="f29b2-134">Field</span></span>                        | <span data-ttu-id="f29b2-135">Värde</span><span class="sxs-lookup"><span data-stu-id="f29b2-135">Value</span></span>     |
|------------------------------|-----------|
| <span data-ttu-id="f29b2-136">Kassarabattdatum</span><span class="sxs-lookup"><span data-stu-id="f29b2-136">Cash discount date</span></span>           | <span data-ttu-id="f29b2-137">2015/07/15</span><span class="sxs-lookup"><span data-stu-id="f29b2-137">7/12/2015</span></span> |
| <span data-ttu-id="f29b2-138">Kassarabattbelopp</span><span class="sxs-lookup"><span data-stu-id="f29b2-138">Cash discount amount</span></span>         | <span data-ttu-id="f29b2-139">60.00</span><span class="sxs-lookup"><span data-stu-id="f29b2-139">60.00</span></span>     |
| <span data-ttu-id="f29b2-140">Använd kassarabatt</span><span class="sxs-lookup"><span data-stu-id="f29b2-140">Use cash discount</span></span>            | <span data-ttu-id="f29b2-141">Normal</span><span class="sxs-lookup"><span data-stu-id="f29b2-141">Normal</span></span>    |
| <span data-ttu-id="f29b2-142">Utnyttjad kassarabatt</span><span class="sxs-lookup"><span data-stu-id="f29b2-142">Cash discount taken</span></span>          | <span data-ttu-id="f29b2-143">0,00</span><span class="sxs-lookup"><span data-stu-id="f29b2-143">0.00</span></span>      |
| <span data-ttu-id="f29b2-144">Kassarabattbelopp att utnyttja</span><span class="sxs-lookup"><span data-stu-id="f29b2-144">Cash discount amount to take</span></span> | <span data-ttu-id="f29b2-145">60,00</span><span class="sxs-lookup"><span data-stu-id="f29b2-145">60.00</span></span>     |

<span data-ttu-id="f29b2-146">April bokför sedan betalningsjournalen.</span><span class="sxs-lookup"><span data-stu-id="f29b2-146">April posts the payment journal.</span></span> <span data-ttu-id="f29b2-147">Fakturan kvittas fullständigt med hjälp av en betalning på 940,00 och en rabatt på 60,00.</span><span class="sxs-lookup"><span data-stu-id="f29b2-147">The invoice is fully settled by using a payment of 940.00 and a discount of 60.00.</span></span>





[!INCLUDE[footer-include](../../includes/footer-banner.md)]