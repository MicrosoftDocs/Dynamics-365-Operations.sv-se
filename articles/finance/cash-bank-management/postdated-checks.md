---
title: Efterdaterade checkar
description: Det här avsnittet innehåller information om stöd för efterdaterade checkar i Microsoft Dynamics 365 Finance. Postdaterade checkar är checkar som har utfärdats för att skapa och ta emot betalningar vid ett framtida datum. Därför kan checken inte lösas in förrän på angivet datum.
author: ShylaThompson
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendPostDatedChecks, CustPostDatedChecks
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 21741
ms.assetid: 4eb7c7da-1e6b-4d35-9f41-373b66103229
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 38ee6c5b3d258c313a2066b388a83330bf696d39
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4448161"
---
# <a name="postdated-checks"></a><span data-ttu-id="f2a97-105">Efterdaterade checkar</span><span class="sxs-lookup"><span data-stu-id="f2a97-105">Postdated checks</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f2a97-106">Det här avsnittet innehåller information om stöd för efterdaterade checkar.</span><span class="sxs-lookup"><span data-stu-id="f2a97-106">This article provides information about support for postdated checks.</span></span> <span data-ttu-id="f2a97-107">Postdaterade checkar är checkar som har utfärdats för att skapa och ta emot betalningar vid ett framtida datum.</span><span class="sxs-lookup"><span data-stu-id="f2a97-107">Postdated checks are checks that are issued to make and receive payments on a future date.</span></span> <span data-ttu-id="f2a97-108">Därför kan checken inte lösas in förrän på angivet datum.</span><span class="sxs-lookup"><span data-stu-id="f2a97-108">Therefore, the check can't be cashed until the specified date.</span></span>

<span data-ttu-id="f2a97-109">Dynamics 365 Finance stöder den fullständiga cykeln för efterdaterade checkar in både Leverantörsreskontra och Kundreskontra, enligt följande tabell.</span><span class="sxs-lookup"><span data-stu-id="f2a97-109">Dynamics 365 Finance supports the full management cycle for postdated checks in both Accounts receivable and Accounts payable, as shown in the following table.</span></span>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f2a97-110">Scenario</span><span class="sxs-lookup"><span data-stu-id="f2a97-110">Scenario</span></span></th>
<th><span data-ttu-id="f2a97-111">Detaljer</span><span class="sxs-lookup"><span data-stu-id="f2a97-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="f2a97-112">Ställ in efterdaterade checkar</span><span class="sxs-lookup"><span data-stu-id="f2a97-112">Set up postdated checks</span></span></td>
<td><span data-ttu-id="f2a97-113">Du måste ställa in en ny betalningsmetod och ange betalningsrutin för clearingkonton för betalda checkar, mottagna checkar och källskatt.</span><span class="sxs-lookup"><span data-stu-id="f2a97-113">You must set up a new payment method, and specify the payment routine for clearing accounts for issued checks, received checks, and withholding tax.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f2a97-114">Registrera och bokför en efterdaterad check för en leverantör</span><span class="sxs-lookup"><span data-stu-id="f2a97-114">Register and post a postdated check for a vendor</span></span></td>
<td><span data-ttu-id="f2a97-115">Registrera information om en efterdaterad check som du utfärdar till en leverantör.</span><span class="sxs-lookup"><span data-stu-id="f2a97-115">Register the details of a postdated check that you issue to a vendor.</span></span> <span data-ttu-id="f2a97-116">När betalningen bokförs känns leverantörsskulden igen, men bankkontot krediteras inte ännu.</span><span class="sxs-lookup"><span data-stu-id="f2a97-116">When the payment is posted, the vendor liability is recognized, but the bank account isn’t yet credit.</span></span> <span data-ttu-id="f2a97-117">I stället används ett clearingkonto för detta ändamål.</span><span class="sxs-lookup"><span data-stu-id="f2a97-117">Instead, a clearing account is used for this purpose.</span></span> </td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f2a97-118">Registrera och bokför en efterdaterad check för en kund</span><span class="sxs-lookup"><span data-stu-id="f2a97-118">Register and post a postdated check for a customer</span></span></td>
<td><span data-ttu-id="f2a97-119">Registrera information om en efterdaterad check som tas emot från en kund.</span><span class="sxs-lookup"><span data-stu-id="f2a97-119">Register the details of a postdated check that you receive from a customer.</span></span> <span data-ttu-id="f2a97-120">När betalningen bokförs krediteras kundfordringen, men bankkontot debiteras inte ännu.</span><span class="sxs-lookup"><span data-stu-id="f2a97-120">When the payment is posted, the customer receivable is credit, but the bank account isn’t yet debit.</span></span> <span data-ttu-id="f2a97-121">I stället används ett clearingkonto för detta ändamål.</span><span class="sxs-lookup"><span data-stu-id="f2a97-121">Instead, a clearing account is used for this purpose.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f2a97-122">Registrera och bokför ett utbyte av en efterdaterad för en kund eller en leverantör</span><span class="sxs-lookup"><span data-stu-id="f2a97-122">Register and post a replacement postdated check for a customer or a vendor</span></span></td>
<td>
<span data-ttu-id="f2a97-123">Om din ursprungliga check till en leverantör eller från en kund förloras eller skadas kan du utfärda en efterdaterad check som substitut.</span><span class="sxs-lookup"><span data-stu-id="f2a97-123">If your original check to a vendor or from a customer is lost or damaged, you can issue a replacement postdated check.</span></span> <span data-ttu-id="f2a97-124">När du registrerar informationen om checken ska du ange en referens till den ursprungliga checken och indikera att den nya checken ersätter den ursprungliga.</span><span class="sxs-lookup"><span data-stu-id="f2a97-124">When you register the check details, provide a reference to the original check, and indicate that the new check is a replacement for the original.</span></span> <span data-ttu-id="f2a97-125">Du kan även bokföra utbyteschecken.</span><span class="sxs-lookup"><span data-stu-id="f2a97-125">You can also post the replacement check.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f2a97-126">Överför en efterdaterad kundcheck till en leverantör</span><span class="sxs-lookup"><span data-stu-id="f2a97-126">Transfer a customer postdated check to a vendor</span></span></td>
<td><span data-ttu-id="f2a97-127">När du får en efterdaterad check från en kund kan du överföra den till en leverantör som betalning.</span><span class="sxs-lookup"><span data-stu-id="f2a97-127">When you receive a postdated check from a customer, you can transfer that check to a vendor as a payment.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f2a97-128">Betala en postdaterad check för en kund eller leverantör</span><span class="sxs-lookup"><span data-stu-id="f2a97-128">Settle a postdated check for a customer or a vendor</span></span></td>
<td><span data-ttu-id="f2a97-129">Kvitta en efterdaterad check som har bokförts på ett interimskonto för en kund eller leverantör när checken har förfallit.</span><span class="sxs-lookup"><span data-stu-id="f2a97-129">Settle a postdated check that is posted to a bridging account for a customer or a vendor when the check finally matures.</span></span> <span data-ttu-id="f2a97-130">När checken kvittad har banken slutligen debiterats eller krediterats mot clearingkontot som användes tidigare.</span><span class="sxs-lookup"><span data-stu-id="f2a97-130">When the check is settled, the bank is finally debit or credit against the clearing account that was used earlier.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f2a97-131">Annullera en efterdaterad check för en leverantör</span><span class="sxs-lookup"><span data-stu-id="f2a97-131">Cancel a postdated check for a vendor</span></span></td>
<td><span data-ttu-id="f2a97-132">Du kan avbryta en bokförd efterdaterad check i sådana fall: - Checken returneras av banken.</span><span class="sxs-lookup"><span data-stu-id="f2a97-132">You can cancel a posted postdated check in these situations: - The check is returned by the bank.</span></span>
<span data-ttu-id="f2a97-133">- Checken har tillämpats på fel faktura.</span><span class="sxs-lookup"><span data-stu-id="f2a97-133">- The check is applied to an incorrect invoice.</span></span>
<span data-ttu-id="f2a97-134">- En kontantbetalning görs mot checken.</span><span class="sxs-lookup"><span data-stu-id="f2a97-134">- A cash payment is made against the check.</span></span>
  </td>
  </tr>
  <tr class="even">
  <td><span data-ttu-id="f2a97-135">Stoppa betalning för en efterdaterad check</span><span class="sxs-lookup"><span data-stu-id="f2a97-135">Stop payment for a postdated check</span></span></td>
  <td><span data-ttu-id="f2a97-136">Du kan stoppa en efterdaterad checkbetalning som utfärdades till en leverantör av orsaker såsom otillräckliga medel, ändringar av villkoren för avtalet med leverantören, leverans av defekta varor från leverantören eller returnering av varor till leverantören.</span><span class="sxs-lookup"><span data-stu-id="f2a97-136">You can stop payment on a postdated check that was issued to a vendor, for reasons such as not sufficient funds, changes in the terms of the agreement with the vendor, supply of defective goods by the vendor, or return of goods to the vendor.</span></span> <span data-ttu-id="f2a97-137">Du kan enbart stoppa betalning på checkar som inte har reglerats.</span><span class="sxs-lookup"><span data-stu-id="f2a97-137">You can stop payment only on checks that haven’t cleared.</span></span></td>
  </tr>
  </tbody>
  </table>



<span data-ttu-id="f2a97-138">Mer information finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="f2a97-138">For more information, see the following topics:</span></span>

[<span data-ttu-id="f2a97-139">Ställ in efterdaterade checkar</span><span class="sxs-lookup"><span data-stu-id="f2a97-139">Set up postdated checks</span></span>](tasks/set-up-postdated-checks.md)

[<span data-ttu-id="f2a97-140">Registrera och bokför en efterdaterad check för en kund</span><span class="sxs-lookup"><span data-stu-id="f2a97-140">Register and post a postdated check for a customer</span></span>](tasks/register-post-postdated-check-customer.md)

[<span data-ttu-id="f2a97-141">Kvitta en efterdaterad check från en kund</span><span class="sxs-lookup"><span data-stu-id="f2a97-141">Settle a postdated check from a customer</span></span>](tasks/settle-postdated-check-customer.md)

[<span data-ttu-id="f2a97-142">Registrera och bokför en efterdaterad check för en leverantör</span><span class="sxs-lookup"><span data-stu-id="f2a97-142">Register and post a postdated check for a vendor</span></span>](tasks/register-post-postdated-check-vendor.md) 

[<span data-ttu-id="f2a97-143">Kvitta en efterdaterad check för en leverantör</span><span class="sxs-lookup"><span data-stu-id="f2a97-143">Settle a postdated check for a vendor</span></span>](tasks/settle-postdated-check-vendor.md)



