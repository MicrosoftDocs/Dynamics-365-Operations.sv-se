---
title: Betalningstypen måste vara kreditkortsfel på försäljningsordersidan
description: Det här avsnittet innehåller felsökningsvägledning som kan vara till hjälp när ett felmeddelande visas på försäljningsordersidan efter att en order har synkroniserats.
author: Reza-Assadi
manager: AnnBe
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 20f18507dee330fd1affedeee092b3dfa7cc10bc
ms.sourcegitcommit: 6c108be3378b365e6ec596a1a8666d59b758db25
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/12/2021
ms.locfileid: "5585538"
---
# <a name="payment-type-must-be-credit-card-error-on-the-sales-order-page"></a><span data-ttu-id="dd138-103">Betalningstypen måste vara kreditkortsfel på försäljningsordersidan</span><span class="sxs-lookup"><span data-stu-id="dd138-103">"Payment type must be credit card" error on the sales order page</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="dd138-104">Det här avsnittet innehåller felsökningsvägledning som kan vara till hjälp när ett felmeddelande visas på försäljningsordersidan efter att en order har synkroniserats.</span><span class="sxs-lookup"><span data-stu-id="dd138-104">This topic provides troubleshooting guidance that can help when an error message is shown on the sales order page after an order is synced.</span></span>

## <a name="description"></a><span data-ttu-id="dd138-105">beskrivning</span><span class="sxs-lookup"><span data-stu-id="dd138-105">Description</span></span>

<span data-ttu-id="dd138-106">När du öppnar försäljningsordersidan efter att du synkroniserat en order visas följande felmeddelande: "Betalningstypen måste vara kreditkort, eftersom kreditkortsnumret har angetts."</span><span class="sxs-lookup"><span data-stu-id="dd138-106">When you open the sales order page after you sync an order, you receive the following error message: "The payment type must be credit card, since the credit card number has been specified."</span></span>

![Betalningstypen måste vara kreditkortsfel](media/payment-type-must-be-credit-card.jpg)

## <a name="resolution"></a><span data-ttu-id="dd138-108">Upplösning</span><span class="sxs-lookup"><span data-stu-id="dd138-108">Resolution</span></span>

### <a name="set-the-payment-type-in-commerce-headquarters"></a><span data-ttu-id="dd138-109">Ställ in betalningstypen i Commerce-administration</span><span class="sxs-lookup"><span data-stu-id="dd138-109">Set the payment type in Commerce headquarters</span></span>

1. <span data-ttu-id="dd138-110">Gå till **Kundreskontra \> Betalningsinställning \> Betalningsvillkor**.</span><span class="sxs-lookup"><span data-stu-id="dd138-110">Go to **Accounts receivable \> Payment setup \> Terms of payment**.</span></span>
1. <span data-ttu-id="dd138-111">Välj betalningsvillkor i den vänstra navigeringen.</span><span class="sxs-lookup"><span data-stu-id="dd138-111">In the left navigation, select your terms of payment.</span></span>
1. <span data-ttu-id="dd138-112">I fältet **Betalningstyp**, se till att **kreditkort** är valt.</span><span class="sxs-lookup"><span data-stu-id="dd138-112">In the **Payment type** field, make sure that **Credit card** is selected.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="dd138-113">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="dd138-113">Additional resources</span></span>

[<span data-ttu-id="dd138-114">Bokföring av försäljningar och betalningar online</span><span class="sxs-lookup"><span data-stu-id="dd138-114">Posting of online sales and payments</span></span>](../tasks/posting-online-sales-payments.md)