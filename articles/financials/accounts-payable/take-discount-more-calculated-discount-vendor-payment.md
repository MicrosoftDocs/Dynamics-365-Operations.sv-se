---
title: "Ta en rabatt som är högre än den beräknade rabatten för en leverantörsbetalning"
description: "Den här artikeln går igenom ett scenario där en kassarabatt utnyttjas för ett belopp som är större än den rabatt som ursprungligen var tillgänglig för fakturan. Det här scenariot kan inträffa om en organisation sluter ett avtal med leverantören om att betala ett lägre belopp på fakturan."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 14281
ms.assetid: 7f0a4197-95dd-4969-ade9-154815cf659e
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 39830014593b7b1bc2868afffcca0f77a0c8a029
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="take-a-discount-that-is-more-than-the-calculated-discount-for-a-vendor-payment"></a><span data-ttu-id="5a9c3-104">Ta en rabatt som är högre än den beräknade rabatten för en leverantörsbetalning</span><span class="sxs-lookup"><span data-stu-id="5a9c3-104">Take a discount that is more than the calculated discount for a vendor payment</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="5a9c3-105">Den här artikeln går igenom ett scenario där en kassarabatt utnyttjas för ett belopp som är större än den rabatt som ursprungligen var tillgänglig för fakturan.</span><span class="sxs-lookup"><span data-stu-id="5a9c3-105">This article walks you through a scenario where a cash discount is taken for an amount that is more than the discount that was originally available on the invoice.</span></span> <span data-ttu-id="5a9c3-106">Det här scenariot kan inträffa om en organisation sluter ett avtal med leverantören om att betala ett lägre belopp på fakturan.</span><span class="sxs-lookup"><span data-stu-id="5a9c3-106">This scenario might occur if an organization comes to an agreement with the vendor to pay a smaller amount on the invoice.</span></span> 

<span data-ttu-id="5a9c3-107">Leverantör 3051 ger Fabrikam en kassarabatt på 4 procent, om en faktura betalas inom 7 dagar.</span><span class="sxs-lookup"><span data-stu-id="5a9c3-107">Vendor 3051 gives Fabrikam a cash discount of 4 percent if an invoice is paid in seven days.</span></span> <span data-ttu-id="5a9c3-108">Den 29 juni anger den en faktura på 1 000,00.</span><span class="sxs-lookup"><span data-stu-id="5a9c3-108">On June 29, April enters an invoice for 1,000.00.</span></span> <span data-ttu-id="5a9c3-109">Leverantören låter April göra en rabatt på 60,00 istället för den standardinställda rabatten på 40,00 som är tillgänglig för fakturan.</span><span class="sxs-lookup"><span data-stu-id="5a9c3-109">The vendor lets April take a discount of 60.00 instead of the default discount of 40.00 that is available for the invoice.</span></span> <span data-ttu-id="5a9c3-110">April registrerar en enstaka betalning genom att använda betalningsjournalen för Leverantörsreskontra.</span><span class="sxs-lookup"><span data-stu-id="5a9c3-110">April records a one-off payment by using the Accounts payable payment journal.</span></span> <span data-ttu-id="5a9c3-111">Hon registrerar leverantören för betalningen och öppnar sedan sidan **Kvitta transaktioner**.</span><span class="sxs-lookup"><span data-stu-id="5a9c3-111">She enters the vendor for the payment and then opens the **Settle transactions** page.</span></span> <span data-ttu-id="5a9c3-112">Hon markerar fakturan och ändrar värdet i fältet **Kassarabattbelopp** till **60,00**.</span><span class="sxs-lookup"><span data-stu-id="5a9c3-112">She marks the invoice and changes the value in the **Cash discount amount** field to **60.00**.</span></span>
| <span data-ttu-id="5a9c3-113">Markera</span><span class="sxs-lookup"><span data-stu-id="5a9c3-113">Mark</span></span>     | <span data-ttu-id="5a9c3-114">Använd kassarabatt</span><span class="sxs-lookup"><span data-stu-id="5a9c3-114">Use cash discount</span></span> | <span data-ttu-id="5a9c3-115">Verifikation</span><span class="sxs-lookup"><span data-stu-id="5a9c3-115">Voucher</span></span>   | <span data-ttu-id="5a9c3-116">Konto</span><span class="sxs-lookup"><span data-stu-id="5a9c3-116">Account</span></span> | <span data-ttu-id="5a9c3-117">Datum</span><span class="sxs-lookup"><span data-stu-id="5a9c3-117">Date</span></span>      | <span data-ttu-id="5a9c3-118">Förfallodatum</span><span class="sxs-lookup"><span data-stu-id="5a9c3-118">Due date</span></span>  | <span data-ttu-id="5a9c3-119">Faktura</span><span class="sxs-lookup"><span data-stu-id="5a9c3-119">Invoice</span></span> | <span data-ttu-id="5a9c3-120">Belopp i transaktionsvalutan</span><span class="sxs-lookup"><span data-stu-id="5a9c3-120">Amount in transaction currency</span></span> | <span data-ttu-id="5a9c3-121">Valuta</span><span class="sxs-lookup"><span data-stu-id="5a9c3-121">Currency</span></span> | <span data-ttu-id="5a9c3-122">Belopp att kvitta</span><span class="sxs-lookup"><span data-stu-id="5a9c3-122">Amount to settle</span></span> |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| <span data-ttu-id="5a9c3-123">Markerad</span><span class="sxs-lookup"><span data-stu-id="5a9c3-123">Selected</span></span> | <span data-ttu-id="5a9c3-124">Normal</span><span class="sxs-lookup"><span data-stu-id="5a9c3-124">Normal</span></span>            | <span data-ttu-id="5a9c3-125">Fakt-10040</span><span class="sxs-lookup"><span data-stu-id="5a9c3-125">Inv-10040</span></span> | <span data-ttu-id="5a9c3-126">3051</span><span class="sxs-lookup"><span data-stu-id="5a9c3-126">3051</span></span>    | <span data-ttu-id="5a9c3-127">29/6/2015</span><span class="sxs-lookup"><span data-stu-id="5a9c3-127">6/29/2015</span></span> | <span data-ttu-id="5a9c3-128">29/7/2015</span><span class="sxs-lookup"><span data-stu-id="5a9c3-128">7/29/2015</span></span> | <span data-ttu-id="5a9c3-129">10040</span><span class="sxs-lookup"><span data-stu-id="5a9c3-129">10040</span></span>   | <span data-ttu-id="5a9c3-130">1 000,00</span><span class="sxs-lookup"><span data-stu-id="5a9c3-130">1,000.00</span></span>                       | <span data-ttu-id="5a9c3-131">USD</span><span class="sxs-lookup"><span data-stu-id="5a9c3-131">USD</span></span>      | <span data-ttu-id="5a9c3-132">940,00</span><span class="sxs-lookup"><span data-stu-id="5a9c3-132">940.00</span></span>           |

<span data-ttu-id="5a9c3-133">Information om rabatten visas längst ned på sidan **Kvitta transaktioner**.</span><span class="sxs-lookup"><span data-stu-id="5a9c3-133">Discount information appears at the bottom of the **Settle transactions** page.</span></span>
|                              |           |
|------------------------------|-----------|
| <span data-ttu-id="5a9c3-134">Kassarabattdatum</span><span class="sxs-lookup"><span data-stu-id="5a9c3-134">Cash discount date</span></span>           | <span data-ttu-id="5a9c3-135">12/7/2015</span><span class="sxs-lookup"><span data-stu-id="5a9c3-135">7/12/2015</span></span> |
| <span data-ttu-id="5a9c3-136">Kassarabattbelopp</span><span class="sxs-lookup"><span data-stu-id="5a9c3-136">Cash discount amount</span></span>         | <span data-ttu-id="5a9c3-137">60,00</span><span class="sxs-lookup"><span data-stu-id="5a9c3-137">60.00</span></span>     |
| <span data-ttu-id="5a9c3-138">Använd kassarabatt</span><span class="sxs-lookup"><span data-stu-id="5a9c3-138">Use cash discount</span></span>            | <span data-ttu-id="5a9c3-139">Normal</span><span class="sxs-lookup"><span data-stu-id="5a9c3-139">Normal</span></span>    |
| <span data-ttu-id="5a9c3-140">Utnyttjad kassarabatt</span><span class="sxs-lookup"><span data-stu-id="5a9c3-140">Cash discount taken</span></span>          | <span data-ttu-id="5a9c3-141">0,00</span><span class="sxs-lookup"><span data-stu-id="5a9c3-141">0.00</span></span>      |
| <span data-ttu-id="5a9c3-142">Kassarabattbelopp att utnyttja</span><span class="sxs-lookup"><span data-stu-id="5a9c3-142">Cash discount amount to take</span></span> | <span data-ttu-id="5a9c3-143">60,00</span><span class="sxs-lookup"><span data-stu-id="5a9c3-143">60.00</span></span>     |

<span data-ttu-id="5a9c3-144">April bokför sedan betalningsjournalen.</span><span class="sxs-lookup"><span data-stu-id="5a9c3-144">April posts the payment journal.</span></span> <span data-ttu-id="5a9c3-145">Fakturan kvittas fullständigt med hjälp av en betalning på 940,00 och en rabatt på 60,00.</span><span class="sxs-lookup"><span data-stu-id="5a9c3-145">The invoice is fully settled by using a payment of 940.00 and a discount of 60.00.</span></span>




